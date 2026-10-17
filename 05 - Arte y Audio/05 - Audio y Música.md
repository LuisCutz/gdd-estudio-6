# Audio y Música

## Descripción de la sección

Define la identidad sonora y cómo el audio comunica información al jugador.

## Música

**Estilo:**  Chiptune retro de los 2000 mezclado con filtros de baja frecuencia (low-pass filters) y efectos de glitch intermitentes para generar una atmósfera claustrofóbica, misteriosa y tensa.
**Instrumentación:**  Sintetizadores de onda cuadrada/triangular de 8 y 16 bits, cajas de ritmo chiptune sintetizadas (FM/PCM retro), generadores de ruido blanco para percusiones secas y moduladores de frecuencia/efectos de distorsión digital (glitch/bitcrush).

**Temas principales:**
- Tema del Menú Principal: Melodía pegadiza pero inquietante que anticipa la dificultad.
- Tema de Niveles: Base rítmica repetitiva y acelerada que impulsa al jugador a avanzar, incrementando la tensión en zonas con trampas dinámicas.
- Tema de Frustración / Game Over: Sutil tono sarcástico o silencio repentino seguido de un efecto molesto.
**Música dinámica:** No

## Efectos de sonido

| Evento                         | Sonido                                                                | Propósito                                                                           |
| ------------------------------ | --------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| Salto del personaje            | Bip ascendente retro de 8-bits                                        | Dar retroalimentación física e inmediata al jugador sobre el control del personaje. |
| Muerte del personaje           | Distorsión glitch pantallazo estático                                 | Reforzar el fracaso y la frustración inmediata tras caer en un obstáculo.           |
| Activación de trampa           | Chasquido mecánico rápido o tono grave de error de sistema.<br><br>   | Alertar de forma instantánea al jugador que ha activado un peligro inesperado.      |
| Reaparición                    | Tono electrónico descendente rápido o "rewind" retro.                 | Indicar la reintegración del personaje para volver a intentar el nivel sin demoras. |
| Superación de nivel / Victoria | Fanfarria chiptune corta distorsionada o interrumpida por el Sistema. | Dar una recompensa sonora rápida antes de pasar al siguiente reto.                  |

## Audio espacial

¿Se utilizará audio posicional?
No., al ser un videojuego de plataformas en 2D con vista lateral y enfoque arcade retro, todos los efectos de sonido y la música se procesarán en estéreo uniforme (2D) para garantizar que los avisos sonoros y trampas se escuchen con total claridad desde cualquier punto de la pantalla.
## Voz

**Narración:** Voz sintetizada por computadora (text-to-speech) o modulada con procesador de voz de baja fidelidad.%%%%

**Diálogos hablados:**
- Intervenciones sonoras breves y frases sarcásticas desencadenadas por eventos clave (muertes consecutivas en el mismo punto, fallos absurdos, victoria de nivel o inactividad del jugador).
- Se combinan con cuadros de diálogo o texto de tipo alerta en la interfaz para asegurar que la burla sea clara tanto en audio como en texto.

**Idiomas:** Español

## Mezcla

Define prioridades, volumen relativo y comportamiento de la música ante eventos importantes.
- Efectos de Sonido (SFX): Prioridad máxima (100% de volumen) para dar señales claras de juego y trampas.
- Burlas del Sistema: Prioridad media-alta (85% de volumen) para asegurar la legibilidad del tono narrativo.
- Música de fondo: Prioridad base (60-70% de volumen) con atenuación automática cuando ocurren eventos de muerte o mensajes del sistema.

> **Navegación:** [[00 - Índice]] · ← [[04 - Interfaz Visual]] · [[01 - UX y Flujo del Jugador]] →
