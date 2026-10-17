# Personajes y Animación

## Descripción de la sección

Documenta cómo deben verse y comportarse visualmente los personajes.

## Requisitos por personaje

| Personaje    | Modelo/Sprite                                                                                                                                            | Animaciones                                                                   | VFX                                                                                                            | Estado                          |
| ------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- | ------------------------------- |
| Protagonista | Sprite 2D _pixel art_ de avatar sencillo y de alta visibilidad visual.                                                                                   | Idle, Caminar, Saltar, Caer, Muerte/Derrota, Reaparición.                     | Partículas de impacto, efecto _glitch_ o fragmentación de píxeles al morir, destello de reaparición.           | En definición visual (Borrador) |
| Sistema      | Entidad omnipresente. Representado visualmente mediante ondas de audio/interfaz de voz, íconos de diálogo sarcásticos o destellos de error en el entorno | Animación de interfaz/onda de sonido al hablar, parpadeo de texto en pantalla | _Glitch_ visual de pantalla, distorsión CRT, parpadeo de alertas cuando se burla o reacciona ante las muertes. | En definición visual (Borrador) |

## Animaciones

### Movimiento

- Idle
- Caminar
- Correr
- Saltar
- Caer

### Interacción

**Acción / Activar:** Animación breve de pulsación de botones, palancas o interacción con elementos del escenario/interfaz.
### Combate
No aplica: El juego está centrado en plataformas de precisión, observación y resolución de trampas, por lo que no cuenta con mecánicas de combate directo.
### Daño
 **Impulso:** Frame de impacto breve con parpadeo rojo/blanco antes de la animación de derrota.
### Muerte / derrota
 **Efecto Muerte Troll - Fragmentación:** Animación instantánea donde el sprite del personaje colapsa, explota en píxeles sueltos o se distorsiona con efecto _glitch_ al colisionar con cualquier trampa o peligro.
**Reaparición (Respawn):** Animación de ensamblado rápido de píxeles o _fade-in_ rápido en el punto de reaparición inicial para permitir reintentos inmediatos sin romper el ritmo del juego.
## Convenciones

Define nombres de archivos, tamaños, esqueletos, rigging, frames o formatos cuando sea necesario.


> **Navegación:** [[00 - Índice]] · ← [[01 - Dirección de Arte]] · [[03 - Entornos]] →
