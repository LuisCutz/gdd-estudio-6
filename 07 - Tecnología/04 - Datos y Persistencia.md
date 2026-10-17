# Datos y Persistencia

## Descripción de la sección

Define qué información necesita conservar el juego y cómo se estructura.

## Datos persistentes

- Progreso: Nivel actual alcanzado (del nivel 1 al 3)
- Estadísticas: Contador acumulativo de muertes de la partida y cronómetro de tiempo transcurrido
- Desbloqueos: Registro booleano de los finales completados (Final 1: Desconexión, Final 2: Permanencia, Final 3: Liberación de Datos)
- Configuración: Volumen general (Master), volumen de música de fondo, volumen de efectos de sonido (SFX) y modo de pantalla completa
- Inventario: No aplica, el diseño no maneja recolección ni gestión de ítems

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

Las burlas del sistema y los valores de cada nivel no se guardan aquí, viven aparte como datos fijos del juego.
## Formato

**Formato de guardado:** JSON, escrito con JsonUtility de Unity

**Ubicación:**  Ruta de datos locales del usuario (Application.persistentDataPath), bajo el nombre save.json.

**Versionado de datos:** En cada guardado exitoso se genera una réplica automática titulada `save.bak` antes de sobrescribir el archivo principal para mitigar pérdidas por apagones repentinos.

**Momento del guardado:** Automático al entrar a cada nivel (checkpoint de sala) y al modificar cualquier ajuste en el menú de pausa.

**Versionado de datos:** Habrá un campo versión dentro del JSON.
## Migraciones

¿Qué ocurre si cambia la estructura de los datos entre versiones?
Si una versión nueva del juego cambia la estructura:

1. El GameManager lee el campo versión del JSON
2. Si la versión detectada es anterior a la actual, se conservan los valores existentes de progreso y configuración, inicializando los campos nuevos con valores predeterminados
3. Se sobrescribe el archivo guardando la versión de esquema actualizada sin reiniciar el avance del usuario

> **Navegación:** [[00 - Índice]] · ← [[03 - Requisitos Técnicos]] · [[05 - Seguridad y Riesgos Técnicos]] →
