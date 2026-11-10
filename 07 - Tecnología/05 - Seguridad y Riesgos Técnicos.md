
# Seguridad y Riesgos Técnicos
El juego es de un solo jugador y guarda todo en local, por lo que sus riesgos principales no son de seguridad, sino de precisión del movimiento, pérdida del guardado y coordinación del equipo en Unity. Esta página recoge esos riesgos y las salvaguardas previstas en el código.

## Riesgos

| Riesgo                                                                      | Probabilidad | Impacto | Mitigación                                                                                                                                                                                                  |
| --------------------------------------------------------------------------- | ------------ | ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Física inconsistente según los FPS (descalibración de saltos en PCs lentas) | Media        | Alto    | Mover y evaluar la física del personaje estrictamente dentro de FixedUpdate, y bloquear la tasa interna de actualización de físicas a 0.02s (50 Hz)                                                         |
| Colisiones rotas por tunneling (atravesar pisos o pinchos a gran velocidad) | Media        | Alto    | Configurar el parámetro `Collision Detection` del `Rigidbody2D` del personaje en `Continuous` y aplicar `CompositeCollider2D` en las plataformas del escenario                                              |
| Conflictos de Git en escenas de Unity entre los integrantes                 | Alta         | Medio   | Los niveles se construyen y editan en Prefabs individuales; solo el líder integra las escenas raíz.                                                                                                         |
| Disparidad de versiones del editor entre los integrantes                    | Media        | Alto    | Misma versión exacta de Unity (`6000.6.3f1`) en todos los equipos y sin actualizar el motor durante el desarrollo.                                                                                          |
| Pérdida o corrupción del archivo local de guardado                          | Baja         | Alto    | Mantener siempre una copia save.bak, si el archivo principal se corrompe, se restaura el respaldo automáticamente                                                                                           |
| Pixel art borroso o desalineado en monitores distintos                      | Media        | Bajo    | Pixel Perfect Camera* con resolución base `640 × 360`, para que los assets de `32 × 32` escalen en múltiplos enteros.                                                                                       |
| Fallo o latencia de red al enviar datos a la app movil                      | Alta         | Bajo    | El envío de estadísticas hacia la app móvil se ejecuta en una corrutina en segundo plano, y si no hay conexión o el servidor falla, el juego ignora el error y continúa funcionando al 100% de manera local |
| Trampas que no vuelven a su estado inicial tras la reaparición              | Media        | Alto    | Cada trampa guarda su estado inicial y lo restaura al recibir `OnPlayerRespawned`.                                                                                                                          |
| Desbordamiento de alcance (*scope creep*) antes de la entrega               | Alta         | Crítico | Alcance congelado en tres niveles lineales; sin combate, tiendas ni cinemáticas complejas ([[01 - Alcance]]).                                                                                               |
## Salvaguardas previstas en el código

- **Muerte única por contacto:** `PlayerDeath` ignora cualquier contacto nuevo hasta terminar la reaparición, para que el contador no sume dos muertes por un mismo golpe.
- **Llave y muerte simultáneas:** si Emmet recoge la llave y muere en el mismo instante, la muerte se procesa primero y la llave vuelve a su pedestal ([[02 - Mecánicas]]).
- **Pausa sin tiempo extra:** `RunTimer` se detiene durante la pausa y mientras la ventana pierde el foco.
- **Ranking no bloqueante:** `LeaderboardUploader` usa un tiempo de espera de `[completar]` s; un error de red nunca impide llegar al desenlace.

## Datos sensibles

No aplica. El juego no pide cuentas, correos ni datos personales. El único dato que sale del equipo es el apodo opcional del ranking, junto con las muertes y el tiempo.

## Multijugador

No aplica. El juego es de un solo jugador y solo usa la red para el envío opcional al ranking.

## Recuperación

- **Corrupción de datos:** Si `save.json` resulta ilegible al iniciar la aplicación, se intenta cargar save.bak, y si ambos están dañados, el sistema genera automáticamente un nuevo archivo con valores en cero y el jugador empieza en el Nivel 1, sin bloquear el juego.

- **Pérdida de foco o cierre inesperado:** Como el guardado se actualiza al inicio de cada nivel, un corte eléctrico o cierre forzado solo reinicia la sala actual, preservando las muertes acumuladas y el progreso general.

- **Bloqueo blando en escenario (Softlock):** Se implementa una tecla de reinicio forzado rápido `(tecla R)` para que el jugador pueda autodestruirse y reaparecer de inmediato si queda atascado entre colisiones sin recibir daño.


> **Navegación:** [[00 - Índice]] · ← [[04 - Datos y Persistencia]] · [[01 - Alcance]] →
