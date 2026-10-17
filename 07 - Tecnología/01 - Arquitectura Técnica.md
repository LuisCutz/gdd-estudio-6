# Arquitectura Técnica

## Descripción de la sección

Explica cómo está construido técnicamente el videojuego y cómo se comunican sus componentes.

## Arquitectura

```text
Entrada (Teclado)
  ↓
Controlador del jugador (Movimientos, saltos)
  ↓
Lógica de juego (Muertes, avance de escenas)
  ↓
Sistemas (Trampas, checkpoints, contador de muertes, narrador)
  ↓
Datos / Persistencia
  ↓
Presentación (animación, UI, audio)
```

## Componentes principales

| Componente | Responsabilidad | Dependencias |
|---|---|---|
| | | |
| | | |

## Comunicación

¿Cómo intercambian información los sistemas?

## Principios técnicos

- Bajo acoplamiento: Las trampas no conocen al contador, ni al narrador, ni al guardado
- Responsabilidades Claras un script, una tarea
- Código mantenible: Nombres claros y clases pequeñas.
- Datos separados de lógica: Las burlas, la configuración de niveles y los valores de las trampas no están hardcodeados dentro del código.
- Evitar dependencias innecesarias: Solo paquetes oficiales de Unity que se necesiten.


> **Navegación:** [[00 - Índice]] · ← [[04 - Guardado y Configuración]] · [[02 - Motor y Herramientas]] →
