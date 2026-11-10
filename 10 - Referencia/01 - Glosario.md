# Glosario

## Términos del juego

| Término                              | Definición                                                                                                                                 |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------ |
| Emmet                                | Protagonista controlado por el jugador. Muere al instante con cualquier trampa o peligro.                                                  |
| Sistema.exe                          | Conciencia del juego. No tiene sprite: habla mediante un cuadro de texto con sonido, se burla del jugador y le presenta la elección final. |
| Trampa *troll*                       | Trampa diseñada para engañar: parece un elemento seguro o inofensivo hasta que se activa.                                                  |
| Peligro visible                      | Trampa que se reconoce a simple vista; en el juego, solo los picos rojos.                                                                  |
| Plataforma falsa                     | Bloque translúcido que parece sólido y desaparece al pisarlo.                                                                              |
| Bloque invisible                     | Bloque oculto que corta el salto al chocar con él; puede quedar visible tras descubrirlo.                                                  |
| Diamante falso                       | Trampa que imita un objeto valioso y mata al tocarlo.                                                                                      |
| Llave                                | Objeto necesario para abrir la puerta de meta. Se pierde si Emmet muere y reaparece en un punto de control anterior a donde la recogió.    |
| Puerta de meta                       | Salida del nivel; permanece bloqueada hasta llevar la llave.                                                                               |
| Palanca                              | Único elemento interactivo con animación propia; Emmet la activa al empujarla.                                                             |
| Punto de control (*checkpoint*)      | Lugar donde Emmet reaparece tras morir.                                                                                                    |
| Reaparición instantánea              | Vuelta de Emmet al último punto de control en menos de `0,2 s`, sin recargar la escena.                                                    |
| Salto leve / salto máximo            | Las dos alturas fijas de salto según el tiempo de pulsación: `2` y `4` bloques.                                                            |
| Contador de muertes                  | Número acumulado de muertes de la partida, visible en el HUD.                                                                              |
| Zona Inicial / Inestable / Colapsada | Los tres estados visuales del sistema, que se mezclan en los niveles y muestran un deterioro creciente.                                    |
| Desenlace                            | Escena final en la que el jugador elige entre salir o quedarse con Sistema.exe.                                                            |
|                                      |                                                                                                                                            |
## Términos de diseño y producción

| Término | Definición |
| --- | --- |
| GDD | Documento de Diseño de Videojuego. |
| Mecánica | Regla o interacción mediante la cual el jugador puede actuar. |
| Sistema | Conjunto de componentes y reglas que trabajan juntos. No confundir con Sistema.exe. |
| Bucle principal (*core loop*) | Ciclo de avanzar, caer en una trampa, morir, reaparecer y aprender la ruta. |
| MVP | Producto Mínimo Viable: Nivel 1 en geometría básica con las mecánicas esenciales. |
| *Vertical Slice* | Muestra pequeña pero representativa del producto final: Nivel 1 completo con arte y audio finales. |
| *Greybox* | Nivel construido con formas básicas sin arte final, para probar la jugabilidad. |
| *Scope creep* | Crecimiento descontrolado del alcance del proyecto. |
## Términos técnicos

| Término | Definición |
| --- | --- |
| Tile / celda | Unidad de la cuadrícula del nivel: `32 × 32` px, equivalente a `1` unidad de Unity. |
| Tileset | Conjunto de piezas de `32 × 32` px con las que se construyen los niveles. |
| PPU | Píxeles por unidad de Unity; en el proyecto, `32`. |
| *Pixel Perfect Camera* | Componente de URP que mantiene el pixel art nítido escalándolo en múltiplos enteros. |
| *Prefab* | Objeto de Unity reutilizable; cada trampa, la palanca, la llave y la puerta de meta son *prefabs*. |
| *ScriptableObject* | Archivo de datos de Unity; guarda las burlas de Sistema.exe y los valores de niveles y trampas. |
| `FixedUpdate` | Ciclo de física de Unity, a `50` Hz; ahí se calcula el movimiento de Emmet. |
| *Tunneling* | Error de física en el que un objeto rápido atraviesa una colisión. |
| *Softlock* | Situación en la que el jugador queda atascado sin poder avanzar ni morir; se resuelve con la tecla `R`. |
| `save.json` / `save.bak` | Archivo de guardado local y su copia de respaldo. |

## Convenciones de nombres

- **Emmet** y **Sistema.exe** se escriben siempre así, con mayúscula y, en el caso de Sistema.exe, con la extensión.
- Los niveles se nombran **Nivel 1 - El Despertar**, **Nivel 2 - Desafío de Datos** y **Nivel 3 - El Umbral de Salida**.
- En el texto se usa **punto de control**; *checkpoint* solo entre paréntesis o en nombres de código.
- Las trampas se nombran como en [[03 - Entornos]]: picos, pico que cae, planta, láser, plataforma falsa, diamante falso y bloque que cae.
- Los nombres de scripts, clases y archivos van en inglés y `PascalCase` (`PlayerMotor`), como se define en [[02 - Motor y Herramientas]].


> **Navegación:** [[00 - Índice]] · ← [[04 - Criterios de Aceptación]] · [[02 - Referencias e Inspiración]] →
