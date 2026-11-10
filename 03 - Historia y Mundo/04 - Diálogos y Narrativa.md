# Diálogos y Narrativa

## Descripción de la sección

Define cómo se presenta la historia al jugador y cómo funcionan los diálogos.

## Métodos narrativos

| Método | ¿Se usa? | Cómo |
| --- | --- | --- |
| Diálogo | Sí | El Sistema es el único personaje que habla. Sus frases aparecen en pantalla letra a letra. |
| Cinemáticas | No | Quedan fuera del alcance (ver [[01 - Alcance]]). |
| Texto ambiental | Sí | Pantallas de texto para el inicio en el bazar y para el mensaje final, con una o dos imágenes fijas en *pixel art* si el tiempo lo permite. |
| Objetos | Sí | Las pruebas que El Novato encuentra en la sala de servidores. |
| Exploración | Sí | La sala de servidores se recorre sin trampas para descubrir la verdad. |
| Entorno | Sí | Las manchas de muerte antiguas, grises y cada vez más frecuentes, son pistas del giro. |
| Audio | Pendiente | La voz sintetizada del Sistema está pendiente de decisión del equipo. El texto en pantalla es el método principal. |
| Narración | No | No hay narrador aparte del Sistema. |

## Funciones del diálogo

El Sistema no puede intervenir en el juego: sus palabras son su única arma para que El Novato se rinda. Cada frase cumple una o varias de estas funciones:

| Función | Qué hace | Ejemplo del Nivel 1 |
| --- | --- | --- |
| Burla | Se ríe de El Novato y de sus muertes. | "Plataformas y pinchos. Hasta un niño podría superarlo." |
| Consejo falso | Empuja a El Novato hacia una trampa. **Solo se usa con algo que el jugador ve por primera vez.** | "¡Mira, un punto de control! Tócalo, es gratis." |
| Enseñar una mecánica | Explica una mecánica a regañadientes, sin tutorial explícito. | "¿Una pared? Qué pena que solo sepas saltar una vez... ¿o no?" |
| Invitar a rendirse | Tienta a El Novato a dejar de intentarlo. | "¿Sigues aquí? Qué terco. Descansa... no tengo prisa." |
| Pista | Se lee primero como burla y cobra sentido tras la revelación (ver [[01 - Premisa y Trama]]). | "Ese hueco no se salta. Créeme: lo sé." |

## Estructura de diálogo

Todos los diálogos siguen la misma estructura:

**Participantes:** el Sistema habla; El Novato escucha y nunca responde.

**Opciones del jugador:** ninguna.

**Consecuencias:** ninguna sobre la jugabilidad. Los diálogos no cambian las trampas, el nivel ni el final.

Hay dos tipos de diálogo:

- **Líneas fijas:** aparecen en un momento concreto del nivel (inicio, antes de una trampa, al coger la llave, al terminar). Llevan el tono de cada nivel, la advertencia de quedarse atrapado y **todas las pistas del giro**, para que cualquier jugador las vea.
- **Burlas al morir:** se usan tres reglas.
    - **Primera muerte del juego:** siempre tiene una frase única.
    - **Primera muerte en una trampa troll:** tiene otra frase única y nunca se repite. Si la primera muerte del juego ocurre en una trampa troll, se muestra la frase de la primera muerte, y la de la trampa troll se reserva para la siguiente muerte en una trampa troll.
    - **Resto de muertes:** aparece una burla cada 3 muertes (3.ª, 6.ª, 9.ª…), elegida al azar entre las frases del nivel, para no saturar al jugador.

**Trampa troll:** plataforma que cae, checkpoint falso y cualquier situación o lugar que engaña al jugador haciéndole creer que está en un sitio seguro. Los pinchos y las caídas al vacío visibles no cuentan.

Las reglas técnicas (cómo se dispara cada frase, qué pasa si coinciden dos y cómo se muestran) se documentan en [[03 - Sistemas]].

> [!info] Estado de las frases
> **Aprobada:** revisada y aprobada por el equipo.
> **Provisional:** ya está implementada en Unity, pero el equipo todavía no la ha aprobado.
> **Propuesta:** sugerida durante la revisión del GDD; no está aprobada ni implementada.

### Inicio — El bazar

Pantallas de texto, con una o dos imágenes fijas si el tiempo lo permite. Emmet no habla y su nombre no aparece.

> [!todo] Pendiente
> Texto de las pantallas del bazar.

### Nivel 1 — El Despertar

**Tono:** burla confiada. El Sistema está seguro de que El Novato no superará ni el nivel básico.

**Líneas fijas**

| # | Momento | Frase | Función | Estado |
| --- | --- | --- | --- | --- |
| 1 | Al aparecer al inicio | "Apenas estamos empezando, Novato." | Burla | Aprobada (corregir en Unity) |
| 2 | Justo después de la frase 1 | "Te lo pondré fácil, Novato: solo hay una salida y está muy, muy lejos. O llegas al final… o te quedas aquí para siempre. Rendirse, en cambio… eso lo tienes aquí mismo." | Advertencia, invitar a rendirse y pista | Aprobada (por implementar) |
| 3 | Antes de la primera trampa (pinchos) | "Un saltito sobre esos pinchos. Sin miedo, Novato." | Consejo falso | Provisional |
| 4 | Muro del doble salto | "¿Una pared? Qué pena que solo sepas saltar una vez... ¿o no?" | Enseñar una mecánica | Provisional |
| 5 | Campo de pinchos | "Plataformas y pinchos. Hasta un niño podría superarlo." | Burla | Aprobada (corregir en Unity) |
| 6 | Checkpoint falso | "¡Mira, un punto de control! Tócalo, es gratis." | Consejo falso | Provisional |
| 7 | Hueco con plataforma invisible | "Ese hueco no se salta. Créeme: lo sé." | Consejo falso y pista | Aprobada |
| 8 | Al recoger la llave | "¿Una llave? Cuídala bien... si te mueres, se queda aquí conmigo." | Burla | Provisional |
| 9 | Antes del checkpoint real | "¿Sigues aquí? Qué terco. Descansa... no tengo prisa." | Invitar a rendirse | Provisional |
| 10 | Antes de la última trampa | "La salida está justo ahí. ¡Salta con todas tus fuerzas!" | Consejo falso | Provisional |
| 11 | Frente al portal | "La puerta solo se abre con su llave. ¿La traes... o la dejaste por ahí?" | Burla | Provisional |
| 12 | Al completar el nivel | "...Eso no debía pasar. Bueno. El siguiente nivel no será tan amable." | Desconcierto | Provisional |

**Burlas al morir**

**Primera muerte del juego:** "Y ahí va la primera. Voy a disfrutar contándolas todas." — Aprobada (por implementar).

**Primera muerte en una trampa troll:** "Esa trampa lleva años esperando a alguien como tú." — Burla y pista. Aprobada (por implementar como evento único).

**Cada 3 muertes (una al azar):**

| Frase | Función | Estado |
| --- | --- | --- |
| "¿Ya? Ni siquiera había empezado a mirar." | Burla  |
| "El suelo no muerde. Bueno... a veces sí." | Burla | 
| "Tómate tu tiempo, Novato. Aquí sobra." | Invitar a rendirse |
| "Muerte registrada. Llevo muy bien la cuenta." | Burla |
| "Tranquilo. A todos nos pasa la primera vez." | Burla y pista | Aprobada 
| "Y este es el nivel fácil. Imagina los demás." | Burla e invitar a rendirse | Aprobada 

### Nivel 2 — Desafío de Datos

**Tono:** burla personal y posesiva. El Sistema deja claro que de ahí nadie sale. Más burlón que en el Nivel 1, para seguir desesperando al jugador.

Las frases deben ser nuevas: no se reutilizan las del Nivel 1.




**Líneas fijas**

| # | Momento | Frase | Función | Estado |
| --- | --- | --- | --- | --- |
| 1 | Al aparecer al inicio | "¿Otra vez tú? Creí que ya te habías cansado, Novato." | Burla | Propuesta |
| 2 | Primeras plataformas temporizadas | "Tranquilo, estas plataformas son de las firmes. Quédate un rato." | Consejo falso | Propuesta |
| 3 | Primer checkpoint | "Un punto de control. Disfrútalo: vas a volver aquí muchas veces." | Burla | Propuesta |
| 4 | Zona de *glitch* | "¿Ves eso? El juego se cae a pedazos. Y aun así puede contigo." | Burla | Propuesta |
| 5 | Primeros nodos de láser | "Los láseres van lentos. Puedes pasar caminando." | Consejo falso | Propuesta |
| 6 | Láser que falla por el deterioro | "Ese láser se atasca cada tanto. Antes no lo hacía." | Pista | Propuesta |
| 7 | Al recoger la llave | "Ya tienes la llave. Ahora solo falta llegar vivo… otra vez." | Burla | Propuesta |
| 8 | Antes del segundo checkpoint | "Puedes parar cuando quieras. Nadie te está mirando… excepto yo." | Invitar a rendirse | Propuesta |
| 9 | Frente a la puerta del Núcleo | "Al otro lado no hay nada mejor que esto, Novato." | Burla | Propuesta |
| 10 | Al completar el nivel | "Disfrútalo. De aquí en adelante, nadie sale." | Burla posesiva | Propuesta |

**Burlas al morir (cada 3 muertes, una al azar)**

| Frase | Función | Estado |
| --- | --- | --- |
| "¿Otra vez? Empiezo a pensar que te gusta estar aquí." | Burla posesiva | Propuesta |
| "Cada muerte te sale mejor, Novato." | Burla | Propuesta |
| "Podrías rendirte. Sería lo más sensato… y lo más cómodo." | Invitar a rendirse | Propuesta |
| "Ya me sé tu forma de morir de memoria." | Burla | Propuesta |
| "Allá afuera nadie te está esperando, Novato. Nadie." | Burla y pista | Propuesta |
| "Muerte número… ya perdí la cuenta. Mentira, nunca la pierdo." | Burla | Propuesta |
| "Tu terquedad es casi admirable. Casi." | Burla | Propuesta |

### Nivel 3 — El Umbral de Salida

**Tono:** control obsesivo, expresado solo con palabras. Es el nivel que el jugador anterior no logró superar.


**Líneas fijas**

| # | Momento | Frase | Función | Estado |
| --- | --- | --- | --- | --- |
| 1 | Al aparecer al inicio | "Último nivel, Novato. Aquí es donde uno se rinde. Créeme." | Burla y pista | Propuesta |
| 2 | Primera caída libre | "Déjate caer. Abajo hay suelo… casi siempre." | Consejo falso | Propuesta |
| 3 | Plataformas fugaces | "Rápido. Estas plataformas no esperan a nadie. Yo sí: tengo todo el tiempo del mundo." | Burla | Propuesta |
| 4 | Circuitos en colapso | "Esta parte se rompía distinto. Ahora es peor. Mucho peor." | Pista | Propuesta |
| 5 | Secuencia de salto milimétrico | "Un píxel de más y se acabó. Aquí no hay segundas oportunidades… bueno, sí: infinitas." | Burla | Propuesta |
| 6 | Checkpoint antes de la antesala | "Último punto de control. Después de esto no hay nada… o eso dicen." | Pista | Propuesta |
| 7 | Antesala del Sistema | "Detente. Aquí se está bien. No necesitas salir." | Control obsesivo | Propuesta |
| 8 | Frente a la entrada de la sala de servidores | "No vas a cruzar esa puerta. Nadie la cruza." | Control obsesivo | Propuesta |

Después de la línea 8, el Sistema no vuelve a hablar: guarda silencio en la sala de servidores.

**Burlas al morir (cada 3 muertes, una al azar)**

| Frase | Función | Estado |
| --- | --- | --- |
| "Ya casi. Eso es lo peor de este nivel: siempre es ya casi." | Burla |
| "¿Cansado? Es normal. Aquí uno se cansa… para siempre." | Invitar a rendirse y pista | 
| "Ríndete. El silencio no es tan malo como crees." | Invitar a rendirse y pista | 
| "Cada vez que mueres, la salida se ve un poquito más lejos, ¿verdad?" | Burla |
| "Yo que tú, me quedaría. Pero tú no eres yo… todavía." | Control obsesivo y pista | 
| "Este nivel no se termina, Novato. Se abandona." | Invitar a rendirse y pista | Propuesta

### Sala de servidores

El Novato recorre la sala sin trampas y encuentra pruebas de que el Sistema fue un jugador como él. **El Sistema guarda silencio por primera vez en todo el juego**: no muestra debilidad, y su silencio cuenta la revelación.



### Final

Mensaje en pantalla : un diálogo o párrafo que indica que el jugador logró salir del juego.

## Tono

- Sarcástico y burlón, sin groserías pesadas.
- **Nunca muestra debilidad ni miedo.** Su actitud cambia en cada nivel (ver [[03 - Personajes]]).
- Los consejos falsos solo se usan con algo que el jugador ve por primera vez.
- Cada pista debe poder leerse primero como una burla (ver la tabla de pistas en [[01 - Premisa y Trama]]).
- Ninguna frase se repite entre niveles.

## Decisiones narrativas

No aplica. El jugador no toma decisiones narrativas: el juego tiene un único final.

## Localización

¿El juego tendrá diferentes idiomas? No.

Idiomas previstos: español.



> **Navegación:** [[00 - Índice]] · ← [[03 - Personajes]] · [[01 - Estructura del Contenido]] →
