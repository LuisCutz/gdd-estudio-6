# Personajes y Animación
Esta página reúne las fichas visuales de **Emmet**, el protagonista, y de **el Sistema**, la conciencia del juego. Todos los sprites se producen en **PixelLab** sobre una cuadrícula de `32 × 32` píxeles y siguen la paleta y las reglas de [[01 - Dirección de Arte]]

La función narrativa de cada personaje se documenta en [[03 - Personajes]], y el comportamiento y los diálogos del Sistema, en [[03 - Enemigos y NPC]].
## Requisitos por personaje

| Personaje    | Modelo/Sprite                                                                                                          | Animaciones                                                                              | VFX                                                                                                            | Estado                                                      |
| ------------ | ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------- |
| Protagonista | Sprite 2D _pixel art_ de avatar sencillo y de alta visibilidad visual.                                                 | Idle, Caminar, Saltar, Caer, Muerte/Derrota, Reaparición.                                | Partículas de impacto, efecto _glitch_ o fragmentación de píxeles al morir, destello de reaparición.           | Caminar, en reposo, saltar, muerte y reaparicion terminado. |
| Sistema      | Entidad omnipresente. Representado visualmente mediante ondas de audio/interfaz de voz, íconos de diálogo sarcásticos. | Animación de interfaz/onda de sonido al hablar, aparición de cuadro de texto en pantalla | _Glitch_ visual de pantalla, distorsión CRT, parpadeo de alertas cuando se burla o reacciona ante las muertes. | En definición visual (Borrador)                             |
## Emmet el Protagonista
---
Emmet es una figura de cuerpo delgado con una **cabeza grande y redonda** que ocupa casi la mitad de su altura, con un ojo o visor oscuro de gran tamaño en el costado. El cuerpo usa crema como color dominante con un contorno oscuro grueso, lo que lo mantiene legible sobre el gris carbón del fondo y sobre las plataformas marrón rojizo. La silueta simple, de extremidades finas y torso oscuro, permite leer su postura de un vistazo, algo necesario en un plataformero de precisión.

## Animaciones

| Animación   | Dos direcciones                               |
| ----------- | --------------------------------------------- |
| Idle        | ![Animación idle de Emmet](../img/Pasted%20image%2020261109192752.png) |
| Caminar     | ![Animación de caminar de Emmet](../img/Pasted%20image%2020261109193010.png) |
| Saltar      | ![Animación de salto de Emmet](../img/Pasted%20image%2020261109193135.png) |
| Muerte      | ![Animación de muerte de Emmet](../img/Pasted%20image%2020261109193318.png) |
| Reaparicion | ![Animación de reaparición de Emmet](../img/Pasted%20image%2020261109193341.png) |


## Interacción

### Muerte y reaparición
**Cualquier trampa o peligro mata a Emmet al instante**: no hay vida, golpes resistidos ni animación de daño intermedia. Al contacto, el primer fotograma de la muerte se agacha y después el sprite colapsa en píxeles sueltos.

La reaparición es casi inmediata, con un ensamblado rápido de píxeles o un _fade-in_ en el último punto de control. Ambas animaciones son cortas a propósito: el jugador debe poder reintentar sin perder el ritmo, ya que la muerte frecuente forma parte del ciclo de frustración controlada.
### Combate
No aplica: El juego está centrado en plataformas de precisión, observación y resolución de trampas, por lo que no cuenta con mecánicas de combate directo.

## El Sistema
---
El Sistema no tiene cuerpo ni sprite. Se manifiesta únicamente mediante un **cuadro de texto en pantalla** acompañado de **sonido** mientras habla. El cuadro sigue el estilo de la interfaz: fondo gris carbón, borde de píxel y texto en crema con la tipografía **Press Start 2P**, que aparece letra por letra. Su presentación detallada se documenta en [[04 - Interfaz Visual]] y su sonido, en [[05 - Audio y Música]].

## Convenciones

| Aspecto              | Convención                                                                            |
| -------------------- | ------------------------------------------------------------------------------------- |
| Programa             | PixelLab                                                                              |
| Tamaño de celda      | `32 x 32` piceles para personajes y elementos animados                                |
| Fotogramas           | De 6 a 8 por animación de personaje                                                   |
| Importacion en Unity | `32` píxeles por unidad, filtro `Point (no filter)`, sin compresión                   |
| Formato              | Spritesheet  en `.png` horizontal; GIF solo como previsualización en este documento\| |
| Nombres de archivos  | Personaje_Sistema (`retrato_sistema.png`)                                             |
| Ubicacion            | `Sprite/ Personajes/`                                                                 |



> **Navegación:** [[00 - Índice]] · ← [[01 - Dirección de Arte]] · [[03 - Entornos]] →
