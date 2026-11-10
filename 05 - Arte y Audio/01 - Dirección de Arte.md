# Dirección de Arte

El juego adopta un estilo **pixel art 2D** basándose en la estética de plataformas creadas a principios de los 2000. Toma como referencia a _Level Devil_, _Not a Troll Game_ y _Never Give Up_ en tres aspectos: el plataformeo de precisión, las trampas engañosas y la dificultad alta. El objetivo visual es mantener un ciclo competitivo de **frustración controlada, curiosidad y burla juguetona**, en el que el escenario parece sencillo y confiable hasta que deja de serlo, y el jugador quiere superar el nivel en lugar de abandonarlo.

El nivel de realismo es **sencillo**: no se busca construir el juego con detalles  ni texturas complejas, sino con formas limpias y legibles. Todo el escenario se construye con **formas geométricas estructuradas** (rectángulos, bloques y bordes rectos de píxel) para plataformas e interfaz, mientras que los peligros usan **formas puntiagudas ,objetos que no parecen ofensivos, plataformas movedizas **. La iluminación es **plana**, sin sombras dinámicas ni luces en tiempo real; la jerarquía visual se logra únicamente mediante el contraste de color.

La cámara es **ortográfica y de desplazamiento lateral**, centrada en el protagonista con un tamaño ortográfico de `[completar]` unidades. Los sprites se importan en Unity con filtro `Point (no filter)`, sin compresión y con 12 píxeles por unidad, de modo que todo el arte comparte la misma cuadrícula y no aparecen píxeles de tamaños distintos en pantalla.

## Paleta de color

| Color                        | Código      | Función                                                                                |
| ---------------------------- | ----------- | -------------------------------------------------------------------------------------- |
| **Verde azulado (principal)  | `#3A9B8D`   | Utilizado para elementos interactivos y detalles relacionados con el sistema.          |
| **Gris carbón (principal)    | `#342F33`   | Fondos oscuros, estructuras base y elementos que transmitan antigüedad o deterioro.    |
| **Marrón rojizo (secundario) | `#7C423B`   | Detalles del entorno, superficies de plataformas y ambientación secundaria.            |
| **Crema (secundario)         | `#FDFEC2`   | Textos, tipografía retro, elementos destacados y contraste principal del protagonista. |
| **Rojo oscuro (acento)       | `#8F2A31`   | Peligro, trampas activadas, advertencias y amenazas.                                   |
| **Azúl oscuro (principal)    | `#001c3bfc` | Utilizado en detalles para todas las plataformas rectangulares y cubos.                |

## Tratamiento Visual

| Uso                      | Tratamiento presente                                                                                                                        |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------- |
| Fondo                    | Gris carbón plano, sin degradados ni capas de parallax recargadas, para que nada compita con la zona de juego.                              |
| Plataformas y materiales | Bloques de azul oscuro y verde azulado con borde de píxel definido y textura mínima de uno o dos tonos, sin sombreado volumétrico.          |
| Jugador                  | Silueta compacta con gris carbón como color dominante, legible sobre cualquier fondo de la paleta.                                          |
| Elementos interactivos   | Azul oscuro y verde azulado en paredes y plataformas.                                                                                       |
| Peligros Visibles        | Picos en rojo oscuro, identificables de un vistazo.                                                                                         |
| Trampas ocultas          | Verde azulado y formas del entorno (cristales, bloques translúcidos, falsos coleccionables), indistinguibles del escenario hasta activarse. |
| Interfaz y texto         | Tipografía **Press Start 2P** en crema sobre gris carbón, sin elementos fuera del estilo pixel art.                                         |

## Reglas visuales

1.**Claridad de lectura:** el protagonista, los elementos interactivos y los peligros visibles siempre deben distinguirse del fondo, incluso en movimiento.

2.**Consistencia retro:** Todo recurso gráfico e interfaz debe mantener el estilo _pixel art_ y la tipografía de corte clásico (como _Press Start 2P_).

3.**Visibilidad engañosa:** las trampas ocultas se integran en el escenario, pero su comportamiento sorprende al jugador. La sorpresa debe venir de la mecánica y no de un problema de lectura: una vez activada, la trampa se reconoce de inmediato como amenaza.

## Referencias
Las imágenes de referencia de _Level Devil_, _Not a Troll Game_ y _Never Give Up_ , se guardan en [[02 - Referencias e Inspiración]]. Los tamaños de sprite y las animaciones del protagonista se detallan en [[02 - Personajes y Animación]].


> **Navegación:** [[00 - Índice]] · ← [[05 - Misiones y Desafíos]] · [[02 - Personajes y Animación]] →
