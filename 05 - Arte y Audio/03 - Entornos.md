# Entornos

## Descripción de la sección

Define la estética y necesidades visuales de escenarios, fondos, objetos y elementos ambientales.

## Zonas

| Zona                                | Estilo                                                                                                          | Elementos                                                                                                | Función                                                                                                                                   |
| ----------------------------------- | --------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| Zona Inicial (Demo del Juego)       | Estética retro limpia de plataformas 2D clásica (años 2000). Colores contrastados y apariencia inofensiva       | Bloques de tierra/piedra simples, plataformas sólidas, fondos estáticos y metas aparentes                | Introducir las mecánicas básicas y generar una falsa sensación de familiaridad y seguridad antes de activar las trampas troll.            |
| Zona Inestable (Código Corrupto)    | Entorno retro con fallos visuales, estructuras desgastadas y fragmentadas.                                      | Plataformas invisibles/falsas, trampas móviles inesperadas, picos emergentes y bloques farsa.            | Desafiar la paciencia y capacidad de observación del jugador mediante el aprendizaje por fallo y la sorpresa                              |
| Zona Colapsada (Sistema Abandonado) | Escenarios oscuros con tonos gris carbón y rojo oscuro, estética de glitch severo y deterioro digital avanzado. | Trampas combinadas de velocidad/precisión, interfaces de alerta del sistema y plataformas destructibles. | Representar el punto culminante de la historia donde el sistema deteriorado intenta evitar a toda costa que el jugador complete el juego. |

## Modularidad

¿Qué elementos pueden reutilizarse?
- **Tilesets de terreno:** Bloques modulares de `16x16` o `32x32` píxeles para construir suelos, techos, paredes y plataformas flotantes.
- **Prefabs de trampas base:** Mecanismos de picos, bloques falsos que se caen o se desplazan, y disparadores de colisión reutilizables en múltiples niveles variando únicamente su comportamiento de sorpresa.
- **Capas de fondo (Parallax Backgrounds):** Fondos retro oscuros tipo rejilla o degrados simples aplicables a toda una zona.
- **Marcadores y metas:** Banderas/puertas de finalización de nivel y puntos de reaparición (_checkpoints_).
## Iluminación

Describe iluminación global, fuentes de luz y cambios durante el juego.
- **Iluminación Global:** Plana y uniforme sin sombras suaves dinámicas, manteniendo la fidelidad visual de los juegos de plataformas 2D de la época de los 2000.
- **Efectos de Luz / Puntos de Atención:** Destellos de contraste en tono crema (`#FDFEC2`) o verde azulado (`#3A9B8D`) para resaltar plataformas interactivas o elementos clave de la interfaz/escenario.
- **Cambios Dinámicos:** En momentos de fallo o activación de trampas troll, la pantalla puede experimentar destellos rápidos de tinte rojo (`#8F2A31`) o microparpadeos tipo monitor CRT para enfatizar el error y la burla del sistema.
## Efectos visuales

- **Partículas:** Polvo retro pixelado al saltar o aterrizar; fragmentos de píxeles al romperse un bloque o destruirse una plataforma.
- **Clima:** No aplica
- **Humo:** No aplica
- **Fuego:** Parpadeo simple de animación en 2-3 frames para trampas de tipo llama o electricidad.
- **Agua / Fluidos:** Haz o zonas de colisión de color plano/pixel art donde la caída provoca la muerte instantánea.
- **Magia / Energía :** Efectos de distorsión digital artefactos visuales, líneas de escaneo CRT, parpadeos de píxeles desalineados cuando el sistema manipula el entorno para engañar al jugador.
- **Impactos:** Explosión o disolución en píxeles sueltos del sprite del jugador al colisionar contra trampas.

## Recursos requeridos

Lista los modelos, sprites, texturas, materiales y efectos necesarios.


> **Navegación:** [[00 - Índice]] · ← [[02 - Personajes y Animación]] · [[04 - Interfaz Visual]] →
