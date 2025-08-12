# Unidad 2


## 🤔 Fase: Reflect

### ACtividad 6

**Parte 1: recuperación de conocimiento (Retrieval Practice)**

**Describe con tus palabras qué es una máquina de estados. ¿Cuáles son sus cuatro componentes fundamentales que has utilizado en esta unidad?**

* Es una forma de organizar un programa dividiéndolo en estados, solo puede estar en un estado a la vez, y cambia a otros estados según eventos o condiciones.

* Estados, eventos y acciones (no recuerdo el cuarto componente).

**Explica por qué la técnica de máquina de estados es tan útil para gestionar la “concurrencia” (atender un temporizador y botones “al mismo tiempo”) en un dispositivo con un solo hilo de ejecución como el micro:bit. ¿Qué problema soluciona en comparación con usar funciones como sleep()?**

* Porque la máquina de estados permite ir revisando constantemente el estado del sistema sin quedarse bloqueado en una sola tarea. Esto evita problemas como con el sleep(), que congela todo y no permite atender otros eventos mientras espera

**Imagina que tienes que añadir una nueva funcionalidad a la bomba temporizada: si se agita (shake) el micro:bit mientras la cuenta regresiva está activa, el tiempo se reduce a la mitad. ¿Cómo modificarías tu diagrama de máquina de estados para incluir este nuevo evento y acción?**

* Agregaria un nuevo evento que fuese shake_detect en el estado STATE_ARMED y le asociaria una accion que seria time_left = time_left / 2.

**Explica qué es un “vector de prueba” y por qué es una herramienta crucial para verificar que una máquina de estados funciona como se espera.**

* Es una lista organizada de eventos y el resultado esperado para cada uno de ellos. Es crucial porque de este modo podemos verificar paso a paso que la máquina de estados responde correctamente en todas las situaciones previstas.

**Parte 2: reflexión sobre tu proceso (Metacognición)**


**¿Qué parte del diseño de la bomba temporizada te resultó más desafiante: crear el diagrama de estados (Actividad 04) o traducir ese diagrama a código MicroPython (Actividad 05)? ¿Por qué?**

* Para mi la parte mas compleja fue traducir el diagrama a codigo porque generalmente la programacion se me da un poco mal entonces ademas de encontrar muchos errores, a veces se me complicaba seguir mentalmente por el estres.

**Describe un error o “bug” que encontraste al implementar tu programa. ¿Cómo te ayudó pensar en términos de estados, eventos y transiciones a identificar y solucionar el problema?**

* Al principio cuando "referenciaba" los estados siempre me salia un error y no entendia porque sucedia, luego gracias a la ayuda de un amigo pude resolver el problema y el programa ya no me ponia problema por eso.

**El problema de la bomba era complejo. ¿Qué estrategia usaste para abordarlo? ¿Comenzaste con una versión simple y añadiste funcionalidades poco a poco?**

* En un principio si me senti bastante estancado, esto porque desde la vista general del diagrama anterior me empecé a sentir perdido y cuando comencé a realizar mi diagrama de la bomba no sabia por donde irme, de igual manera intenta y mirando por varios lados logre crear un diagrama "convincente" para mi y pude darle detalles sin mucho problema. Las cosas se volvieron a complicar a la hora de realizar el codigo por lo que mencioné anteriormente, pero logre terminarlo.

**Ahora que entiendes el patrón de máquina de estados, ¿En qué otro tipo de proyecto o sistema de entretenimiento digital crees que podrías aplicarlo?**

* Por la perspectiva que me brindo la unidad creo que se podria aplicar para video juegos.

### Actividad 7

* Como compañero de trabajo elegi a Juan David, note que su codigo era mejor que el mio en cuanto al orden en el que organizaba las cosas y de que no tenia cosas que no fueran fundamentales, vi que debo aprender de ese tipo de cosas para mejorar mis futuros trabajos.

### Actividad 8

**Continuar: ¿Qué actividad, explicación o ejemplo de esta unidad te ayudó más a entender el poder de las máquinas de estados? ¿Qué elemento consideras que es indispensable y debería mantener?**

* Aunque fuera complicada la actividad de la bomba fue la que me ayudo a comprender de mejor manera la unidad.

**Dejar de hacer: ¿Hubo algún paso o actividad que te pareció confuso, innecesariamente complicado o que aportó poco a tu aprendizaje? ¿Qué cambiarías o eliminarías?**

* No siento que hubiera algo que realmente haya aportado poco aprendizaje, pero por la parte de la programacion para mi si fue un tanto complicado.

**Empezar a hacer: ¿Qué te habría ayudado a entender mejor?**

* Tal vez practicar mas el programar o hacer mas preguntas en clase.

**Ritmo y dificultad: En una escala del 1 (muy fácil) al 5 (muy difícil), ¿Cómo calificarías la dificultad de pasar del análisis de un programa (Actividad 03) al diseño desde cero de uno complejo (Actividad 04 y 05)? ¿Por qué?**

* 4, porque desde cero al no tener como esas ayuditas a veces se complica la identificacion de los componentes de la maquina de estados.

**Comentario adicional: ¿Hay algo más que te gustaría compartir sobre tu proceso de aprendizaje en esta unidad? ¿Algún momento de frustración o de “¡Aha!” que quieras destacar?**

* Pues gracias a la retroalimentacion del profe se como mejorar mis futuros proyectos.

