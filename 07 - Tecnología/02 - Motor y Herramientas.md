# Motor y Herramientas

## Descripción de la sección

El juego se desarrolla en **Unity 6** con el *pipeline* 2D de URP y se programa en C#. El arte se produce en PixelLab, y el GDD se redacta en Markdown con Obsidian y se versiona en GitHub en un repositorio separado del juego.

## Motor

| Aspecto     | Decisión                                                                                                  |
| ----------- | --------------------------------------------------------------------------------------------------------- |
| Motor       | Unity `6000.6.3f1`                                                                                        |
| Renderizado | URP 2D (Universal Render Pipeline con *Renderer 2D*)                                                      |
| Cámara      | *Pixel Perfect Camera* de URP, resolución de referencia `640 × 360`                                       |
| Física      | Física 2D de Unity (`Rigidbody2D`, `BoxCollider2D`, `CompositeCollider2D`), paso fijo de `0,02 s` (50 Hz) |
| Entrada     | Input System (paquete oficial), solo teclado                                                              |
| Plataforma  | Windows x64                                                                                               |

## Tecnologías

| Tecnología          | Uso en el proyecto                                                    |
| ------------------- | --------------------------------------------------------------------- |
| C#                  | Lógica del juego, interfaz y herramientas del Editor.                 |
| Tilemap 2D          | Construcción de niveles con el tileset de `32 × 32` px.               |
| *ScriptableObjects* | Burlas de Sistema.exe, datos de cada nivel y valores de las trampas.  |
| `JsonUtility`       | Serialización del guardado local (`save.json`).                       |
| `UnityWebRequest`   | Envío opcional de apodo, muertes y tiempo al ranking de la app móvil. |
| TextMesh Pro        | Texto de la interfaz con la fuente *Press Start 2P*.                  |

## Herramientas

| Herramienta         | Propósito                                   | Versión      |
| ------------------- | ------------------------------------------- | ------------ |
| Unity               | Motor, editor de escenas y física           | `6000.6.3f1` |
| Visual Studio Code  | Editor de código                            | `1.145.2`    |
| PixelLab            | Sprites, animaciones y tileset en pixel art | Web          |
| Obsidian / Markdown | Redacción del GDD                           | `1.15.0`     |
| Git y GitHub        | Control de versiones y trabajo remoto       | `2.55.0`     |

## Dependencias

| Paquete             | Uso                                      |
| ------------------- | ---------------------------------------- |
| Universal RP        | Renderizado 2D y *Pixel Perfect Camera*. |
| 2D Tilemap Editor   | Pintado de niveles.                      |
| 2D Sprite           | Corte de hojas de sprites.               |
| Input System        | Lectura del teclado.                     |
| uGUI y TextMesh Pro | Interfaz.                                |
No se usan paquetes de terceros ni de la Asset Store.
## Convenciones del proyecto

- **Estructura de carpetas:** `Assets/Animations`, `Assets/Audio`, `Assets/Materials`, `Assets/Prefabs`, `Assets/Scenes`, `Assets/Scripts`, `Assets/Settings`, `Assets/Sprites`, `Assets/Data` (*ScriptableObjects*).
- **Nomenclatura:** clases y archivos en `PascalCase` e inglés (`PlayerMotor.cs`); sprites como `Personaje_Accion` (`Emmet_Caminar.png`); escenas como `Nivel_01`.
- **Control de versiones:** rama `main` estable, una rama por funcionalidad (`feature/...`) y unión mediante *pull request*. Archivo `.gitignore` oficial de Unity; las escenas raíz solo las integra el líder.
-  **Formato de assets:** PNG con transparencia, `32` píxeles por unidad, filtro *Point* y sin compresión; ==🔴audio en WAV para efectos y OGG para música==
- **Convenciones de código:** campos privados con `[SerializeField]`, un `MonoBehaviour` por archivo y comunicación entre sistemas mediante eventos.


> **Navegación:** [[00 - Índice]] · ← [[01 - Arquitectura Técnica]] · [[03 - Requisitos Técnicos]] →
