# Mecánicas

## Descripción de la sección

Una mecánica es una regla o interacción mediante la cual el jugador puede actuar dentro del sistema del juego.

Documenta cada mecánica con suficiente detalle para que otro integrante pueda implementarla.

## Plantilla de mecánica
## Mecánicas principales
### Mecánica 01

### Mecánica: Movimiento Lateral Horizontal

**Propósito:**

Permitir al jugador navegar por el entorno, esquivar amenazas y tomar posicionamiento antes de ejecutar un salto. Es la base de toda la interacción espacial del juego.

**Activación:**

El jugador mantiene presionado el botón o tecla de dirección hacia la izquierda o la derecha.

**Reglas:**

- Al presionar la dirección, el personaje se desplaza horizontalmente hasta alcanzar una velocidad máxima fija.
    
- **Frenado en seco (Tight Control):** Al soltar el botón, el personaje debe detenerse casi de inmediato. No debe haber inercia ni deslizamiento excesivo para garantizar que el jugador tenga control absoluto y evitar muertes accidentales por "resbalar" hacia un pozo.
    
- El movimiento horizontal puede ejecutarse tanto en el suelo como en el aire (control aéreo), permitiendo corregir ligeramente la trayectoria durante un salto.
    
- El personaje no puede atravesar obstáculos sólidos (paredes, bloques).
    

**Entrada:**

Botones de dirección Flechas del teclado, teclas A/D.

**Estado inicial:**

Personaje estático en estado de reposo (_Idle_).

**Estado final:**

Personaje desplazándose a una velocidad horizontal constante hacia la dirección indicada.

**Recursos utilizados:**

Ninguno.

**Recompensa:**

Avanzar por el nivel y esquivar trampas.

**Penalización:**

Un mal posicionamiento resulta en colisiones letales.

**Interacciones con otras mecánicas:**

- **Salto y Doble Salto:** El movimiento lateral define la inercia horizontal del personaje mientras está en el aire.
    
- **Plataformas Inestables:** Caminar sobre ellas activa su temporizador de caída.
    

**Casos límite:**

- **Colisión en el aire:** Si el jugador se mueve horizontalmente contra una pared mientras cae, la fricción del material en Unity debe estar en cero para evitar que el personaje se quede "pegado" a la pared y caiga a su velocidad normal.
    
- **Presionar ambas direcciones:** Si el jugador presiona Izquierda y Derecha al mismo tiempo, el motor debe priorizar la última tecla pulsada o cancelar el movimiento (quedarse quieto) para evitar comportamientos erráticos.
### Mecánica 02
### Salto y Doble Salto

**Propósito:**  
¿Qué aporta a la experiencia?
Brindar al jugador un control medido sobre la trayectoria de su personaje, permitiendo adaptar la altura a las necesidades del obstáculo. Al limitarlo estrictamente a dos alturas predecibles, se mantiene la precisión milimétrica requerida para el diseño de niveles troll

**Activación:**  
¿Qué debe hacer el jugador?
El jugador presiona el botón de salto mientras el personaje está en el suelo (Salto Base). Si lo presiona nuevamente en el aire, ejecuta un segundo impulso (Doble Salto). El tiempo que se mantenga presionado el botón determina el nivel de altura.
**Reglas:**  
¿Qué puede y qué no puede ocurrir?
Dos niveles fijos de altura:
**Salto Leve (Pulsación corta):** Si el botón se presiona rápidamente (ej. menos de un umbral específico de milisegundos), el salto alcanza una altura mínima fija (Referencia de diseño: 2 bloques).
**Salto Máximo (Pulsación sostenida):** Si el jugador mantiene presionado el bo
tón, el personaje alcanza el límite absoluto de altura permitida para un salto (Referencia de diseño: 4 bloques).
**Acumulación en el Doble Salto:** El comportamiento de los dos niveles aplica también para el segundo salto en el aire. Las alturas se suman dependiendo de la ejecución. _(Ejemplo teórico: Salto Máximo de 4 bloques + Doble Salto Leve de 2 bloques = 6 bloques de altura total. Salto Máximo + Doble Salto Máximo = 8 bloques)
**Restricción del Doble Salto:** Solo puede ejecutarse una (1) vez tras abandonar el suelo. Se recarga únicamente cuando el personaje vuelve a tocar una superficie sólida.
**Entrada:**  
¿Qué botón, gesto o acción la activa?
Barra espaciadora 
**Estado inicial:**
Para Salto Base: Personaje tocando el suelo
Para Doble Salto: Personaje en el aire
**Estado final:**
El personaje ejecuta un salto de altura (leve o máxima) dependiendo del tiempo de pulsación. 
**Recursos utilizados:**
Carga de doble salto (1 uso por cada vez que se abandona el suelo).
**Recompensa:**
Libertad para calibrar visualmente si un obstáculo requiere apenas un salto leve para colar al personaje en un pasillo estrecho, o un salto máximo para cruzar un abismo amplio.
**Penalización:**
Fallar en el cálculo mental del tipo de salto (ej. mantener presionado por pánico cuando se requería un salto leve) altera la trayectoria deseada, estrellando al personaje contra trampas en el techo o arruinando el aterrizaje.
**Interacciones con otras mecánicas:**
**Bloques Invisibles Troll:** Si el jugador choca con un bloque oculto mientras ejecuta un Salto Máximo, su fuerza ascendente se corta de inmediato a la altura del impacto. Si no ha gastado su doble salto, puede intentar reaccionar en el aire con un Salto Leve o Máximo para salvarse.
**Casos límite:**  
¿Qué ocurre en situaciones poco comunes?
**Choques prematuros (Techos):** Si el jugador ejecuta un Salto Máximo pero choca la cabeza con una plataforma normal a la altura de un Salto Leve, el salto se interrumpe físicamente y comienza la caída.

### Mecánica 03
### Bloques Invisibles
**Propósito:**
Engañar al jugador interrumpiendo saltos que parecen seguros, generando muertes sorpresivas y cómicamente injustas.

**Activación:**

El jugador colisiona desde abajo con el área (trigger/collider) donde se encuentra posicionado el bloque oculto.

**Reglas:**

- El bloque es completamente transparente y no tiene colisión física activa antes de ser tocado.
    
- Al entrar en contacto con el jugador, el bloque se vuelve instantáneamente visible y su colisión (_box collider_) se vuelve sólida.
    
- Detiene de inmediato cualquier inercia ascendente del jugador.
    
- Una vez revelado, el bloque se queda visible y sólido para el resto del intento actual. Su posición en el nivel es fija (no aleatoria).
    

**Entrada:**

Ninguna entrada directa de botones. Se activa por el movimiento y posicionamiento del personaje.

**Estado inicial:**

Bloque oculto 

**Estado final:**

Bloque revelado .

**Recursos utilizados:**

Ninguno.

**Recompensa:**

Aprender la ubicación de la trampa para el siguiente intento.

**Penalización:**

Pérdida inmediata de la trayectoria del salto, lo que usualmente empuja al jugador a caer en un pozo de pinchos o un abismo.

**Interacciones con otras mecánicas:**

Interrumpe la mecánica de "Salto Variable". Puede usarse a propósito como plataforma de apoyo una vez que el jugador ya lo ha revelado.

**Casos límite:**

Si el jugador impacta exactamente en la esquina del bloque (en el borde de las cajas de colisión), el motor de físicas podría causar un pequeño deslizamiento lateral. Debe ajustarse la fricción del material en Unity para que el choque sea en seco.




### Mecánica 04
### Reaparición Instantánea
**Propósito:**
 Reducir el enojo del jugador al sufrir muertes constantes por culpa del diseño "troll".

**Activación:**

El jugador reaparece o mure tras tocar cualquier elemento letal (pinchos, caída libre, plataforma falsa ).

**Reglas:**

- No hay pantalla de "Game Over" tradicional ni tiempos de carga.
    
- La animación de muerte del jugador (ej. explotar en partículas) ocurre de inmediato.
    
- En menos de 1 segundo, el jugador recobra el control del personaje en las coordenadas exactas del último punto de control (_Checkpoint_) activado.
    

**Entrada:**
Automática (gestionada por el sistema tras recibir daño letal).

**Estado inicial:**
Personaje colisionando con un obstáculo letal.

**Estado final:**
Personaje posicionado en el último _Checkpoint_, con sus físicas y animaciones reiniciadas, listo para moverse.

**Recursos utilizados:**
Ninguno.

**Recompensa:**
Una nueva oportunidad sin tiempos de espera.

**Penalización:**
Retroceder físicamente en el nivel perdiendo el progreso no guardado.

**Interacciones con otras mecánicas:**
Al reaparecer, restablece la posición inicial de elementos móviles (como plataformas que caen), pero los "Bloques Invisibles Troll" que ya habían sido descubiertos pueden configurarse para mantenerse visibles, premiando la memoria del jugador.

**Casos límite:**
Morir en el mismo _frame_ (fotograma) en el que se toca el _collider_ de un nuevo punto de control. El sistema debe registrar primero el punto de control antes de ejecutar la muerte.

### Mecánica 05
### Puntos de control

**Propósito:**

Guardar el progreso del jugador dentro de un nivel para evitar que repita secciones enteras tras cada muerte. En el contexto de su juego, sirven como anclas que mantienen el flujo rápido de prueba y error, dando breves momentos de alivio.

**Activación:**

El jugador colisiona físicamente con el _trigger_ del punto de control (por ejemplo, una bandera, un poste de luz, una fogata).

**Reglas:**

- Al entrar en contacto con el _collider_, el juego actualiza las coordenadas de reaparición (_RespawnPoint_) a la ubicación exacta de ese punto de control.
    
- Solo puede haber un punto de control activo a la vez. Tocar uno nuevo sobrescribe el anterior.
    
- En el diseño _troll_, un punto de control puede tener un disfraz. Algunas "banderas" podrían no ser seguras y en su lugar esconder pinchos o lanzar al jugador al vacío al tocarlas.
    
- El estado activado debe reflejarse visualmente (ej. la bandera cambia de color o se despliega).
    

**Entrada:**
Automática por movimiento espacial (_OnTriggerEnter2D_).

**Estado inicial:**
Punto de control inactivo. El sistema de reaparición guarda una coordenada anterior (o el inicio del nivel).

**Estado final:**
Punto de control activo visualmente. El sistema de reaparición guarda las coordenadas actuales.

**Recursos utilizados:**
Ninguno.

**Recompensa:**
Asegurar el progreso de la sección superada y proporcionar un breve descanso mental.

**Penalización:**
Ninguna directa.

**Interacciones con otras mecánicas:**
Es el complemento directo de la "Reaparición Instantánea". Al activarlo, también debe reiniciar el estado de las trampas móviles (como las plataformas que caen) a su posición original para el siguiente intento.

**Casos límite:**
Si el jugador muere exactamente en el mismo fotograma (_frame_) en el que toca el punto de control, el código en Unity debe priorizar la actualización de las coordenadas antes de ejecutar la secuencia de muerte, garantizando que el progreso se guarde.

### Mecánica 06
### Mecánica: Llave de Nivel (Bloqueo de Progreso)

**Propósito:**
Obligar al jugador a explorar una ruta específica, superar un desafío concreto o sobrevivir a una secuencia de ida y vuelta antes de permitirle terminar el nivel.

**Activación:**
El jugador colisiona con el objeto "Llave" en el mapa, y posteriormente interactúa con la "Puerta de Meta" bloqueada.

**Reglas:**

- La puerta de meta permanece bloqueada (y puede ser letal si se intenta cruzar a la fuerza) hasta que una variable booleana (ej. `HasKey`) se vuelva verdadera.
    
- Al tocar la llave, esta desaparece del entorno físico y pasa a la interfaz de usuario (UI) o flota detrás del personaje.
    
- _Regla de muerte:_ Si el jugador muere mientras lleva la llave y reaparece en un _Checkpoint_ anterior al lugar donde la recogió, **la llave se pierde** y vuelve a su posición original en el nivel. El jugador debe hacer el recorrido de nuevo.
    
- _Diseño Troll:_ Recoger la llave puede actuar como un interruptor (_trigger_) que despierte nuevos enemigos o cambie el comportamiento del escenario en la ruta de regreso hacia la puerta.
    

**Entrada:**
Automática por colisión con el objeto.

**Estado inicial:**

Variable `HasKey` en falso. Objeto físico "Llave" presente en el nivel. Puerta de meta inactiva/bloqueada.

**Estado final:**
Variable `HasKey` en verdadero. La llave desaparece del mundo. Puerta de meta activa/abierta.

**Recursos utilizados:**
Variable de estado en el inventario temporal del nivel (1 Llave).

**Recompensa:**
Obtener la condición necesaria para avanzar al siguiente nivel.

**Penalización:**
Ninguna por agarrarla, pero condiciona al jugador a sobrevivir un tramo extra para hacerla válida.

**Interacciones con otras mecánicas:**
Interactúa fuertemente con la muerte. Perder la vida resetea la llave si no se ha alcanzado un nuevo punto de control.

**Casos límite:**
Agarrar la llave y caer al vacío en el mismo instante. El sistema debe procesar la muerte y reiniciar la llave en su pedestal, evitando que el jugador reaparezca con ella "gratis".

### Mecánica 07
### Mecánica: Plataformas que Caen (Inestables)

**Propósito:**
Castigar la duda y obligar al jugador a moverse rápidamente sin detenerse a pensar. También sirven como un engaño visual al presentar un suelo que parece seguro pero no lo es.

**Activación:**
El jugador entra en contacto físico (aterriza, camina o choca de lado) con la caja de colisión (_collider_) de la plataforma.

**Reglas:**

- Al detectar el impacto (_OnCollisionEnter2D_), se activa un temporizador oculto muy corto (ej. 0.2 a 0.5 segundos).
    
- Mientras el temporizador corre, la plataforma puede temblar visualmente para advertir al jugador (o no, si quieren que sea más _troll_).
    
- Al agotarse el tiempo, la plataforma cambia su estado físico (_Rigidbody2D_ pasa de estático a dinámico/afectado por la gravedad) o simplemente desactiva su colisión y cae fuera de la pantalla.
    
- La plataforma debe volver a su posición original intacta cada vez que el jugador muera y reaparezca en el punto de control.
    

**Entrada:**
Automática por posicionamiento (el peso del personaje sobre la plataforma).

**Estado inicial:**
Plataforma estática, sólida y segura.

**Estado final:**
Plataforma en caída libre, inservible como apoyo.

**Recursos utilizados:**
Ninguno.

**Recompensa:**
Si el jugador reacciona a tiempo, puede usar la fracción de segundo de estabilidad para tomar impulso hacia otra zona.

**Penalización:**
Si el jugador duda o se detiene, perderá el soporte y caerá al vacío o a una trampa.

**Interacciones con otras mecánicas:**
Forzará al jugador a utilizar de forma reactiva el "Doble Salto" para intentar salvarse si la plataforma se cae más rápido de lo que esperaba.

**Casos límite:**
Tocar el borde de la plataforma desde un lateral sin llegar a pararse encima de ella activará el temporizador de caída de todos modos. Esto evita que el jugador abuse de agarrarse de los bordes o deslizarse sin sufrir la trampa




## Mecánicas secundarias

Lista las mecánicas que complementan la experiencia pero no constituyen el núcleo.
    **Cronómetro y Contador de Muertes dinámico:**
- _Propósito:_ Elementos de interfaz que reaccionan a la partida. No afectan el movimiento del personaje, pero complementan la experiencia a largo plazo incentivando el _speedrun_ o generando frustración cómica al ver subir el contador de muertes a cientos.

**Manchas de sangre persistentes (Rastro de muertes):**

- _Propósito:_ Cada vez que el jugador muere, el personaje deja una pequeña mancha de sangre o pintura en esa coordenada exacta. Al reaparecer, la mancha sigue ahí. Sirve como una advertencia visual de dónde ocurrieron errores pasados y alimenta la comedia visual del nivel.

> **Navegación:** [[00 - Índice]] · ← [[01 - Jugabilidad]] · [[03 - Sistemas]] →
