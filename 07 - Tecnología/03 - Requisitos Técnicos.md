# Requisitos Técnicos

La plataforma del proyecto es **Windows PC (x64)**, controlado solo con teclado. El juego es 2D en pixel art, con tres niveles y sin efectos de iluminación en tiempo real, por lo que sus requisitos son bajos. Los valores de rendimiento son objetivos que se validarán con la *build* de entrega.

## Requisitos mínimos

| Parámetro         | Mínimo                                   | Recomendado                              |
| ----------------- | ---------------------------------------- | ---------------------------------------- |
| Sistema operativo | Windows 10 (21H1 o posterior) de 64 bits | Windows 11 de 64 bits                    |
| CPU               | x64 con instrucciones SSE2               | x64 de cuatro núcleos                    |
| GPU               | Compatible con DirectX 10                | Compatible con DirectX 11 o 12           |
| RAM               | 4 GB                                     | 8 GB                                     |
| Almacenamiento    | 500 MB libres                            | 1 GB libre (SSD)                         |
| Resolución        | 1280 × 720 (16:9)                        | 1920 × 1080 (16:9)                       |
| Conexión          | No necesaria                             | Solo para enviar el resultado al ranking |
| Entrada           | Teclado                                  | Teclado                                  |
## Objetivos de rendimiento

| Parámetro | Objetivo |
| --- | --- |
| FPS | `60` estables en el perfil mínimo |
| Presupuesto de fotograma | `16,7 ms` o menos |
| Carga de un nivel | Menos de `3 s` |
| Reaparición tras morir | Menos de `0,2 s`, sin recargar la escena |
| Memoria | Menos de `500 MB` de RAM en ejecución |
| Tamaño de la *build* | Menos de `300 MB` |

## Requisitos de desarrollo

| Parámetro | Valor |
| --- | --- |
| Motor | Unity `6000.6.3f1`, la misma versión exacta en todos los equipos |
| Sistema operativo | Windows 10 u 11 de 64 bits |
| RAM | 8 GB mínimo, 16 GB recomendados |
| Almacenamiento | 20 GB libres para Unity, el proyecto y la caché |


## Restricciones

- Solo Windows; no hay versión para consola, móvil ni web.
- Solo teclado; no hay soporte para mando ni pantalla táctil.
- Un solo jugador, sin multijugador ni red, salvo el envío opcional al ranking.
- Resolución fija de 16:9; en otras proporciones aparecen bandas negras para conservar el pixel art en múltiplos enteros.


> **Navegación:** [[00 - Índice]] · ← [[02 - Motor y Herramientas]] · [[04 - Datos y Persistencia]] →
