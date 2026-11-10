# Datos y Persistencia

El juego guarda en local un único archivo JSON con el progreso, las estadísticas, el final elegido y la configuración. Los datos fijos del juego, como las burlas de Sistema.exe, la configuración de cada nivel y los valores de las trampas, no se guardan: viven en *ScriptableObjects* dentro del proyecto.

## Datos fijos (*ScriptableObjects*)

| Asset | Contenido |
| --- | --- |
| `TauntDatabase` | Frases de Sistema.exe agrupadas por momento: al morir, al iniciar cada nivel, al completarlo y en el desenlace. |
| `LevelData` (uno por nivel) | Nombre, escena, orden y puntos de control del nivel. |
| `TrapSettings` | Velocidades, tiempos de espera y distancias de activación de cada tipo de trampa. |

## Datos persistentes (`SaveData`)

| Campo | Tipo | Contenido |
| --- | --- | --- |
| `version` | `int` | Versión del esquema de guardado; la inicial es `1`. |
| `progreso.nivelActual` | `int` | Nivel alcanzado, de `1` a `3`. |
| `progreso.juegoCompletado` | `bool` | Indica si se superó el Nivel 3. |
| `estadisticas.muertesTotales` | `int` | Contador acumulado de muertes de la partida. |
| `estadisticas.tiempoJugado` | `float` | Segundos totales de juego, sin contar la pausa. |
| `desbloqueos.finalElegido` | `int` | `0` = ninguno, `1` = Salir, `2` = Quedarse, `3` = Romper el servidor. |
| `jugador.apodo` | `string` | Apodo para el ranking (máximo `[completar]` caracteres); vacío si el jugador no lo envía. |
| `configuracion.volumenMaster` | `float` | Volumen general, de `0.0` a `1.0`. |
| `configuracion.volumenMusica` | `float` | Volumen de música, de `0.0` a `1.0`. |
| `configuracion.volumenSFX` | `float` | Volumen de efectos, de `0.0` a `1.0`. |
| `configuracion.pantallaCompleta` | `bool` | Pantalla completa o ventana. |
==🟣No hay inventario: el juego no tiene objetos que recolectar ni gestionar.==

## Modelo de datos

#### 1. Estructura local (`SaveData`)
El estado de la partida se serializa en una única clase plana para garantizar consistencia y rendimiento:

```text

SaveData

 ├─ version                (int: control de versión del esquema)

 ├─ progreso

 │    ├─ nivelActual       (int: valor del 1 al 3)

 │    └─ juegoCompletado   (bool: indica si se superó el nivel 3)

 ├─ estadisticas

 │    ├─ muertesTotales    (int: contador global acumulado)

 │    └─ tiempoJugado      (float: segundos totales de juego)

 ├─ desbloqueos

 │    └─ finalElegido      (int: 0=Ninguno, 1=Salir, 2=Quedarse, 3=Romper Servidor)

 └─ configuracion

      ├─ volumenMaster     (float: 0.0 a 1.0)

      ├─ volumenMusica     (float: 0.0 a 1.0)

      ├─ volumenSFX        (float: 0.0 a 1.0)

      └─ pantallaCompleta  (bool: estado de visualización)

```

## Formato y escritura
| Aspecto                        | Decisión                                                                                                                                                                |
| ------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Formato                        | JSON escrito con `JsonUtility`.                                                                                                                                         |
| Ubicación                      | `Application.persistentDataPath/save.json`.                                                                                                                             |
| Respaldo o versionado de datos | En cada guardado exitoso se genera una réplica automática titulada `save.bak` antes de sobrescribir el archivo principal para mitigar pérdidas por apagones repentinos. |
| Momento del guardado           | Al entrar a cada nivel (checkpoint), al completarlo y al cambiar un ajuste en la configuración.                                                                         |
| Escritura segura               | Se escribe primero en `save.tmp` y después se reemplaza `save.json`, para que un corte de luz no deje el archivo a medias.                                              |
## Envío al ranking

Al completar el juego, si el jugador escribe un apodo, `LeaderboardUploader` envía el **apodo, las muertes totales y el tiempo jugado** a la app móvil mediante una petición HTTPS con `UnityWebRequest`. El servicio de destino es ==🔴`[completar: URL o servicio de la app móvil]`==. El envío es opcional y no bloquea el juego si falla.
## Migraciones

Si una versión nueva del juego cambia la estructura:

1. El `GameManager` lee el campo `versión` del JSON
2. Si la versión detectada es anterior a la actual, se conservan los valores existentes de progreso y configuración, inicializando los campos nuevos con valores predeterminados
3. Se sobrescribe el archivo guardando la versión de esquema actualizada sin reiniciar el avance del usuario

> **Navegación:** [[00 - Índice]] · ← [[03 - Requisitos Técnicos]] · [[05 - Seguridad y Riesgos Técnicos]] →
