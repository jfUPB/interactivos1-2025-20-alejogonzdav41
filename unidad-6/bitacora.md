
# Evidencias de la unidad 6

### Actividad 1

**¿Qué ocurrió en la terminal cuando ejecutaste npm install? ¿Cuál crees que es su propósito?**  

<img width="689" height="251" alt="image" src="https://github.com/user-attachments/assets/adab24b6-d81b-4f81-a32d-23e91629376d" />

- Apareció el texto que se observa en la imagen, tiene la finalidad de descargar las dependencias.

**¿Qué mensaje específico apareció en la terminal después de ejecutar npm start? ¿Qué indica este mensaje?**  

<img width="684" height="129" alt="image" src="https://github.com/user-attachments/assets/7e80f4e4-bf48-47c8-a938-4c29a5dceccd" />

- 

**Describe lo que ves inicialmente en page1 y page2 en tu navegador.**  

<img width="1900" height="606" alt="image" src="https://github.com/user-attachments/assets/3cb542aa-34f6-42ee-a217-6b4195ca9f82" />

- Inicialmente en el navegador 1 y 2 se observan dos bolas rojas de contorno negro que tienen una linea negra que sale de la mitad de cada una y que las conecta.

**¿Qué mensajes aparecieron en la terminal del servidor cuando abriste page1 y page2?**  

<img width="721" height="393" alt="image" src="https://github.com/user-attachments/assets/11ed4100-e80f-4271-9f71-1be35976d09a" />

**Describe qué sucede en ambas páginas del navegador cuando mueves una de las ventanas. ¿Cambia algo visualmente? ¿Qué mensajes aparecen (si los hay) en la consola del navegador (usualmente accesible con F12 -> Pestaña Consola) y en la terminal del servidor?**  

- 

### Actividad 2

**Piensa en cómo te conectas a Internet en casa o en la Universidad. ¿Usas Wi-Fi? ¿Un cable de red? Eso es simplemente tu “rampa de acceso” a la gran red de carreteras. ¿Qué pasaría si esa rampa se corta? Anota tus ideas.**

- Si la rampa de acceso se corta, o sea si no tengo Wi-Fi ni cable de red, básicamente me quedo sin poder entrar a Internet. Eso significaría que no podría usar aplicaciones que dependen de conexión como WhatsApp, redes sociales, YouTube o las plataformas de estudio. También me afectaría para hacer tareas que necesitan buscar información en línea. En  la Universidad sería un problema porque no podría acceder a los recursos virtuales ni enviar trabajos.

**¿Puedes identificar otros ejemplos de relaciones Cliente-Servidor en tu vida diaria (no necesariamente digitales)? Por ejemplo, al pedir comida en un restaurante. ¿Quién es el cliente y quién el servidor? ¿Qué se pide y qué se entrega?**

Un ejemplo claro es cuando voy a una tienda de ropa. Yo soy el cliente porque llego con la intención de pedir o comprar algo, y el vendedor sería el servidor porque me atiende y me entrega lo que solicito.

Otro ejemplo es en el colegio, cuando pido un libro en la biblioteca. Yo solicito un título específico y la bibliotecaria me entrega el libro o me indica cómo conseguirlo (Cliente-Servidor).

En ambos casos se ve que siempre hay una parte que pide y otra que responde, igual que en Internet.

**Toma la URL de tu sitio web favorito. Intenta identificar el protocolo, el nombre de dominio y la ruta (si la hay). ¿Qué crees que pasa si solo escribes el nombre de dominio (ej. www.google.com) sin una ruta específica? ¿Qué “página por defecto” crees que te envía el servidor?**

https://guthib.com

"https://" Este es el protocolo, significa que la comunicación entre mi navegador y el servidor será seguro.

"guthib.com" Este es el nombre de dominio, que identifica al servidor al que quiero conectarme.

En este caso no hay ruta, o sea no aparece algo como /pagina/index.html.

Si solo escribo guthib.com sin ruta, el servidor normalmente me envía una página por defecto, que casi siempre es algo como index.html o la página principal del sitio. Eso sería como la “entrada” del edificio digital, la primera página que muestran al público.

**Piensa en una página web simple, como un formulario de login.
¿Qué parte crees que es HTML (ej. los campos de texto, el botón)?
¿Qué parte es CSS (ej. el color del botón, el tipo de letra)?
¿Qué parte es JavaScript (ej. la comprobación de si escribiste algo antes de enviar, el mensaje de “contraseña incorrecta” que aparece sin recargar la página)?**

En un formulario de login sencillo lo podría dividir así:

- HTML: Sería la estructura básica: la caja donde escribo el usuario, la caja de la contraseña, el botón de “Iniciar sesión” y los textos que dicen qué poner en cada campo.

- CSS: Se encarga de cómo se ve todo: el color del botón, el fondo de la página, el tipo y tamaño de la letra, si los bordes de las cajas son redondeados, etc.

- JavaScript: Controla la parte interactiva: por ejemplo, que no me deje enviar el formulario si dejo un campo vacío, mostrar un aviso de “contraseña incorrecta” sin tener que recargar toda la página, o incluso animar que el botón cambie de color cuando paso el mouse.

**Compara el bucle draw() de p5.js con este modelo de “esperar a que algo pase y reaccionar”.
¿Qué ventajas crees que tiene el modelo basado en eventos para una interfaz de usuario web?
¿Sería eficiente tener un bucle draw() redibujando toda la página 60 veces por segundo si nada ha cambiado?**

Si comparo el bucle draw() de p5.js con el modelo basado en eventos en JavaScript, noto que son formas muy diferentes de trabajar:

En p5.js, draw() corre constantemente, aunque no siempre haya cambios. Es como si estuviera “repintando” la pantalla una y otra vez. Eso es útil para animaciones o gráficos en movimiento, pero puede ser pesado si no hay nada nuevo que mostrar.

En el modelo de eventos de JavaScript, el código solo se ejecuta cuando pasa algo: un clic, una tecla, un mensaje del servidor, etc. El navegador no está gastando energía en redibujar todo, solo reacciona a lo necesario.

La ventaja del modelo basado en eventos es que es más eficiente para interfaces web: no consume recursos de más, responde rápido a las acciones del usuario y hace que la página sea más ligera.

Si tuviéramos un draw() redibujando toda la página 60 veces por segundo aunque nada cambie, sería un desperdicio de memoria y procesador, y la computadora podría ponerse lenta. Por eso, en la web es mejor esperar eventos y reaccionar solo cuando se necesita.

**¿Por qué crees que podría ser útil usar JavaScript tanto en el cliente (navegador) como en el servidor? ¿Se te ocurre alguna ventaja para los desarrolladores?**

- Usar JavaScript en el cliente y en el servidor es útil porque permite trabajar con el mismo lenguaje en ambos lados. Para el usuario hace la página interactiva sin recargar, y en el servidor maneja datos y peticiones. Para los desarrolladores es una ventaja porque ahorra tiempo, se puede reutilizar código y todos trabajan con un mismo lenguaje.

**Resume con tus propias palabras la diferencia fundamental entre una comunicación HTTP tradicional y una comunicación usando WebSockets/Socket.IO. ¿En qué tipo de aplicaciones has visto o podrías imaginar que se usa esta comunicación en tiempo real?**

- La diferencia es que en HTTP tradicional el cliente pide algo y el servidor responde, como un intercambio de correos: no hay conexión continua. En cambio, con WebSockets/Socket.IO se abre una conexión directa y permanente, como una llamada telefónica, donde ambos pueden enviarse mensajes al instante sin tener que pedir cada vez.
- Este tipo de comunicación en tiempo real se usa en aplicaciones como chats, videojuegos en línea, transmisiones en vivo con comentarios, colaboraciones en documentos compartidos o ver la ubicación de alguien en un mapa en tiempo real.

### Actividad 3

