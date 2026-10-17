	# Seguridad y Riesgos Técnicos

## Descripción de la sección

Documenta riesgos técnicos y medidas para reducir fallos, pérdida de datos o abuso de sistemas.

## Riesgos

| Riesgo                                                                      | Probabilidad | Impacto | Mitigación                                                                                                                                                                                                  |
| --------------------------------------------------------------------------- | ------------ | ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Física inconsistente según los FPS (descalibración de saltos en PCs lentas) | Media        | Alto    | Mover y evaluar la física del personaje estrictamente dentro de FixedUpdate, y bloquear la tasa interna de actualización de físicas a 0.02s (50 Hz)                                                         |
| Colisiones rotas por tunneling (atravesar pisos o pinchos a gran velocidad) | Media        | Alto    | Configurar el parámetro Collision Detection del Rigidbody2D del personaje en Continuous y aplicar CompositeCollider2D en las plataformas del escenario                                                      |
| Conflictos de Git en escenas de Unity entre los integrantes                 | Alta         | Medio   | Los niveles se construyen y editan en Prefabs individuales, las escenas raíz solo es integrada y sincronizada por el líder                                                                                  |
| Disparidad de versiones del editor entre los integrantes                    | Media        | Alto    | Estandarizar la versión exacta de Unity 6 en las computadoras de los integrantes y congelar actualizaciones del motor durante el desarrollo                                                                 |
| Pérdida o corrupción del archivo local de guardado                          | Baja         | Alto    | Mantener siempre una copia save.bak, si el archivo principal se corrompe, se restaura el respaldo automáticamente                                                                                           |
| Desalineación o pixel art borroso en diferentes monitores                   | Media        | Bajo    | Implementar el componente Pixel Perfect Camera (URP 2D) fijando una resolución base para que los assets de 32×32 píxeles escalen en múltiplos enteros sin distorsión                                        |
| Fallo o latencia de red al enviar datos a la app movil                      | Alta         | Bajo    | El envío de estadísticas hacia la app móvil se ejecuta en una corrutina en segundo plano, y si no hay conexión o el servidor falla, el juego ignora el error y continúa funcionando al 100% de manera local |
| Desbordamiento de alcance (scope creep) antes de la entrega                 | Alta         | Critico | Alcance congelado en exactamente 3 niveles lineales con mecánicas de ensayo y error, descartando sistemas de combate, tiendas o cinemáticas renderizadas complejas                                          |

## Datos sensibles

No aplica, el juego no pide cuentas, correos ni datos personales, y todo se guarda de forma local en la computadora del jugador.

## Multijugador

No aplica, El juego es de un solo jugador y no usa red.

## Recuperación

- **Corrupción de datos:** Si save.json resulta ilegible al iniciar la aplicación, se intenta cargar save.bak, y si ambos están dañados, el sistema genera automáticamente un nuevo archivo con valores en cero y sitúa al jugador en el Nivel 1 sin congelar la ejecución.

- **Pérdida de foco o cierre inesperado:** Como el guardado se actualiza al inicio de cada nivel, un corte eléctrico o cierre forzado solo reinicia la sala actual, preservando las muertes acumuladas y el progreso general.

- **Bloqueo blando en escenario (Softlock):** Se implementa una tecla de reinicio forzado rápido (tecla R) para que el jugador pueda autodestruirse y reaparecer de inmediato si queda atascado entre colisiones sin recibir daño


> **Navegación:** [[00 - Índice]] · ← [[04 - Datos y Persistencia]] · [[01 - Alcance]] →
