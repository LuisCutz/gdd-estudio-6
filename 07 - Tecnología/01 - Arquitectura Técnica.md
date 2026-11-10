# Arquitectura Técnica

El juego se construye en Unity 6 como un proyecto 2D para Windows. La compilación empieza en la escena `MainMenu` y carga una escena por nivel (`Nivel_01`, `Nivel_02`, `Nivel_03`), seguida de `Desenlace` para la elección final. Cada nivel se monta a partir de *prefabs* de tramo para que varios integrantes trabajen en paralelo sin editar la misma escena.

El proyecto todavía no está montado en Unity. Los nombres de esta página son la **arquitectura planificada** y se actualizarán cuando existan los scripts.

## Arquitectura

```text
Entrada (Teclado)
  ↓
Controlador del jugador (Movimientos, saltos)
  ↓
Lógica de juego (muerte, reaparición, checkpoints, llave, meta)
  ↓
Sistemas (Trampas, contador de muertes, cronómetro, Sistema.exe)
  ↓
Datos / Persistencia (guardado local, configuración, envío al ranking)
  ↓
Presentación (animación, HUD, audio)
```

## Componentes principales

==🔴*aun se tienen que revisar porque puede que no concuerden con lo que se tiene armado en Unity*==

| Responsabilidad            | Componentes planificados (`Assets/Scripts`)                                                                                         | Dependencias                         |
| -------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------ |
| Flujo de partida y escenas | `GameManager`, `SceneLoader`                                                                                                        | `SaveManager`                        |
| Entrada                    | `PlayerInputReader`                                                                                                                 | Input System                         |
| Movimiento                 | `PlayerMotor` (movimiento, salto leve y máximo)                                                                                     | `PlayerInputReader`, `Rigidbody2D`   |
| Muerte y reaparición       | `PlayerDeath`, `RespawnManager`                                                                                                     | `CheckpointManager`                  |
| Puntos de control          | `Checkpoint`, `CheckpointManager`                                                                                                   | —                                    |
| Trampas                    | `TrapBase` y sus variantes: `SpikeTrap`, `FallingSpike`, `LungingPlant`, `LaserTrap`, `FakePlatform`, `FakeDiamond`, `FallingBlock` | —                                    |
| Llave, palanca y meta      | `LevelKey`, `Lever`, `ExitDoor`                                                                                                     | `CheckpointManager`                  |
| Estadísticas               | `DeathCounter`, `RunTimer`                                                                                                          | `SaveManager`                        |
| Sistema.exe                | `SystemNarrator`                                                                                                                    | `TauntDatabase` (*ScriptableObject*) |
| Datos de nivel             | `LevelData` (*ScriptableObject*)                                                                                                    | —                                    |
| Guardado y configuración   | `SaveManager`, `SettingsManager`                                                                                                    | `JsonUtility`                        |
| Ranking                    | `LeaderboardUploader`                                                                                                               | `UnityWebRequest`                    |
| Interfaz                   | `HudView`, `PauseMenu`, `MainMenuView`, `LevelCompleteView`, `EndingView`                                                           | Eventos del juego                    |
| Audio                      | `AudioManager`                                                                                                                      | Eventos del juego                    |
| Cámara                     | *Pixel Perfect Camera* y seguimiento del jugador                                                                                    | —                                    |

## Comunicación

Los sistemas se comunican mediante **eventos de C#** publicados por quien detecta el hecho:

| Evento                         | Lo publica       | Lo escuchan                                                                               |
| ------------------------------ | ---------------- | ----------------------------------------------------------------------------------------- |
| `OnPlayerDied`                 | `PlayerDeath`    | `DeathCounter`, `RespawnManager`, `SystemNarrator`, `AudioManager`, `HudView`, `LevelKey` |
| `OnPlayerRespawned`            | `RespawnManager` | Trampas (vuelven a su estado inicial), `AudioManager`                                     |
| `OnCheckpointReached`          | `Checkpoint`     | `CheckpointManager`, `SaveManager`                                                        |
| `OnKeyCollected` / `OnKeyLost` | `LevelKey`       | `HudView`, `ExitDoor`, puerta activada por la llave                                       |
| `OnLeverActivated`             | `Lever`          | Objetos enlazados a esa palanca                                                           |
| `OnLevelCompleted`             | `ExitDoor`       | `GameManager`, `RunTimer`, `SaveManager`, `SystemNarrator`, `LevelCompleteView`           |

- Las trampas no conocen al contador, al narrador ni al guardado: solo detectan el contacto y avisan a `PlayerDeath`. 
- La reaparición no recarga la escena; `RespawnManager` mueve a Emmet al último punto de control y emite `OnPlayerRespawned` para que cada trampa se reinicie en menos de `0,2 s`.
## Principios técnicos

- **Bajo acoplamiento:** Las trampas no conocen al contador, ni al narrador, ni al guardado
- **Responsabilidades claras:** un script, una tarea.
- **Código mantenible:** nombres claros y clases pequeñas.
- **Datos separados de lógica:**  las burlas de Sistema.exe, la configuración de los niveles y los valores de las trampas viven en *ScriptableObjects*, no en el código
- **Evitar dependencias innecesarias**: Solo paquetes oficiales de Unity que se necesiten.


> **Navegación:** [[00 - Índice]] · ← [[04 - Guardado y Configuración]] · [[02 - Motor y Herramientas]] →
