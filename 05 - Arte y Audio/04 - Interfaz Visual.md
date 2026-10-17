# Interfaz Visual

## Descripción de la sección

Documenta la información que el juego muestra al jugador y las reglas visuales de la interfaz.

## HUD

La interfaz es minimalista para mantener la pantalla despejada y centrar la atención en los obstáculos y trampas del nivel.
Elementos:

- **Vida:** Contador visible de muertes o reintentos acumulados en la partida destacado visualmente para alimentar el reto del juego.
- **Energía:** No aplica
- **Munición:** No aplica
- **Objetivo:** Pequeños textos o mensajes sarcásticos del Sistema que aparecen contextualmente en pantalla al fallar o avanzar.
- **Mapa:** No aplica
- **Recursos:** No aplica
- **Indicadores contextuales:** Prompts e indicaciones de interacción (ejemplo: _"Presiona `[Espacio]` para saltar"_ o _"Presiona `[R]` para reiniciar"_).

## Jerarquía visual

¿Qué información debe verse primero, segundo y tercero?
- **Primero:** El área de juego activa (protagonista, plataformas y trampas directas) para garantizar la jugabilidad y lectura instantánea.
- **Segundo:** Indicadores de vida/intentos y los mensajes o burlas del Sistema emergentes en pantalla.
- **Tercero :** Indicaciones contextuales de interacción y marcos decorativos que simulan la ventana de un programa antiguo/sistema operativo.
## Estados

Documenta estados normales, advertencias, daño, éxito, error y bloqueo.
- **Estado Normal:** Ventanas e interfaz limpias con tipografía clara en tono crema y bordes rectos estilo retro.
- **Advertencias:** Cuadros de diálogo o texto con tinte rojo oscuro que simulan alertas de error de sistema cuando se activan trampas o peligros.
- **Daño / Derrota:** Flash rápido de pantalla con efecto _glitch_ o marco de error de Windows/CRT antiguo al morir.
- **Éxito :** Ventana emergente con mensaje retro de "Nivel Completado" o "Proceso Exitoso", resaltado en verde azulado .
- **Error / Bloqueo:** Simulación de fallo en el programa o congelamiento breve de interfaz usado humorísticamente por el Sistema antes de reaparecer al personaje.
## Convenciones

**Tipografía:** Press Start 2P (o tipografías pixeladas similares) para mantener el estilo retro de los años 2000.

**Iconografía:** Íconos simples en pixel art inspirados en ventanas de sistemas operativos antiguos (botones de cerrar `[X]`, minimizar `[-]`, cursores retro e íconos de advertencia `[!]`).

**Tamaños mínimos:**
- Texto en pantalla _8pt - 10pt para subtítulos e indicaciones.
- Títulos de menús / Mensajes del Sistema: 14pt- 16pt para fácil lectura.

**Contraste:** Contraste elevado asegurado utilizando fondo oscuro gris carbón  con texto en crema o verde azulado

**Animaciones:** Animación de parpadeo de cursor de texto (`_`), apariciones instantáneas tipo "pop-up" sin transiciones suaves, y parpadeo breve (_blink_) en diálogos del Sistema.

## Pantallas

- **Menú principal:** Diseñado como el escritorio o pantalla de inicio de un software antiguo con opciones de "Iniciar Demo", "Opciones" y "Salir".
- **Pausa:** Ventana emergente flotante sobre el juego en ejecución que permite "Continuar", "Reiniciar Nivel" o "Salir al Menú".
- **Configuración:** Subpantalla básica de ajustes de volumen de audio y controles/teclas.
- **Inventario:** No aplica
- **Mapa:** No aplica
- **Victoria:** Pantalla o ventana de finalización de nivel con el tiempo transcurrido, número de muertes/intentos y un mensaje mordaz del Sistema.
- **Derrota:** Pantalla de reinicio instantáneo o breve ventana de "Error de Ejecución" con el botón para reintentar de inmediato sin tiempos de carga prolongados.


> **Navegación:** [[00 - Índice]] · ← [[03 - Entornos]] · [[05 - Audio y Música]] →
