
# Evidencias de la unidad 7

### NOTA

Estaba haciendo el trabajo con compañera Andre y me salió éste error.

<img width="1295" height="301" alt="image" src="https://github.com/user-attachments/assets/21dd81d4-baa8-4edd-be0f-c2bdf5f87caa" />

***Actvidad 1***

**¿Qué URL de Dev Tunnels obtuviste? ¿Por qué crees que necesitamos usar esta URL en lugar de http://localhost:3000 o la IP local de tu computador para que el celular se conecte?**

* la url que me dió es https://js14dxnz-3000.use.devtunnels.ms/, debemos utilizar esa dirección en vez de http://localhost:3000 o la IP local, ya que el celular no puede acceder al localhost del computador (igual a mi compañera Andre porque no funciona el mio).

**Describe brevemente qué hace npm install y npm start.**

* El comando npm install se utiliza para descargar e instalar todas las dependencias necesarias para que el proyecto funcione, según lo especificado en el archivo package.json.

* Por su parte, el comando npm start se emplea para ejecutar el proyecto, normalmente iniciando el servidor o el programa principal definido en dicho archivo.

**¿Qué mensajes observaste en la terminal del servidor al conectar el cliente de escritorio y el cliente móvil? ¿Eran diferentes los mensajes o identificadores?**


<img width="659" height="180" alt="image" src="https://github.com/user-attachments/assets/5ece69fb-62a8-4887-aac1-2537bba11a62" />

**Describe el comportamiento observado: ¿Funcionó la interacción? ¿Hubo algún retraso (latencia)?**

* Si, funcionó correctamente y respindía a todo lo que se enviaba desde el celular sin retraso.

***Actividad 2***

**Explica con tus propias palabras: ¿Por qué es necesario Dev Tunnels en este escenario y cómo funciona conceptualmente?**

* Se utiliza Dev Tunnels porque el servidor se ejecuta en localhost:3000, una dirección que solo es accesible desde mi propio computador. El celular no puede conectarse a esa ruta, ya que para él “localhost” hace referencia a su propio dispositivo. Con Dev Tunnels es posible establecer una conexión segura y práctica entre ambos equipos, sin necesidad de configurar direcciones IP ni redes manualmente.

**Describe la función de touchMoved() y por qué se usa la variable threshold en el cliente móvil.**

* La función touchMoved() se ejecuta cuando se toca y se desliza el dedo sobre la pantalla. Registra las coordenadas del movimiento y las envía al servidor mediante Socket.IO, el cual las transmite al computador para reflejar los cambios. Además, incluye un límite que evita enviar desplazamientos demasiado pequeños, con el fin de no saturar el túnel con señales innecesarias.

**Compara brevemente Dev Tunnels con simplemente usar la IP local. ¿Cuáles son las ventajas y desventajas de cada uno?**

* Usar la IP local permite conectar el celular y el computador directamente dentro de la misma red Wi-Fi. Es rápido y no depende de servicios externos, pero tiene desventajas: solo funciona si ambos dispositivos están en la misma red y puede requerir configurar el firewall o el router.

* Dev Tunnels, en cambio, crea un enlace seguro a través de Internet. Permite acceder al servidor desde cualquier lugar y evita configuraciones de red complicadas. Sin embargo, depende de conexión externa y puede ser un poco más lento que una conexión local directa.

**Coloca en tu bitácora capturas de pantalla del sistema completo funcionando. Esto lo puedes hacer abriendo tanto el mobile como el desktop en tu computador y tomando una captura de pantalla de todos los involucrados (celular, computador y terminal).**

<img width="1290" height="2796" alt="image" src="https://github.com/user-attachments/assets/4ae29617-2d9a-4955-8f9d-59a2ea0ae76b" />

***Actividad 3***

**¿Cuál es la función principal de express.static(‘public’) en este servidor? ¿Cómo se compara con el uso de app.get(‘/ruta’, …) del servidor de la Unidad 6?**

* express.static('public') permite que el servidor muestre de forma automática los archivos ubicados en la carpeta public. En la unidad 6 era necesario escribir manualmente cada ruta de las vistas para poder acceder a ellas.

**Explica detalladamente el flujo de un mensaje táctil: ¿Qué evento lo envía desde el móvil? ¿Qué evento lo recibe el servidor? ¿Qué hace el servidor con él? ¿Qué evento lo envía el servidor al escritorio? ¿Por qué se usa socket.broadcast.emit en lugar de io.emit o socket.emit en este caso?**

- Cuando deslizo el dedo en la pantalla del celular, la función touchMoved() detecta el movimiento y envía los datos al servidor mediante socket.emit('message', touchData).

- El servidor recibe esa información con socket.on('message', ...) y la reenvía a los demás clientes usando socket.broadcast.emit('message', message).

- En el celular, el mensaje solo se muestra en la consola, mientras que en el computador el círculo se mueve según las coordenadas recibidas.

- Se utiliza broadcast.emit porque envía el mensaje a todos los clientes excepto al que lo originó; io.emit lo enviaría a todos y socket.emit únicamente al emisor.

**Si conectaras dos computadores de escritorio y un móvil a este servidor, y movieras el dedo en el móvil, ¿Quién recibiría el mensaje retransmitido por el servidor? ¿Por qué?**

* Si tengo dos computadores con el programa de escritorio y un celular, al mover el dedo en el celular, ambos computadores reciben el mensaje, ya que el servidor lo envía a todos los clientes conectados excepto al que lo originó.

**¿Qué información útil te proporcionan los mensajes console.log en el servidor durante la ejecución?**

* Muestra cuándo un cliente se conecta, la posición del toque que se detecta y también cuándo alguien se desconecta. Toda esa información sirve para identificar en qué parte del código podría estar ocurriendo un fallo.

***Actividad 4***

**Realiza un diagrama donde muestres el flujo completo de datos y eventos entre los tres componentes: móvil, servidor y escritorio. Puedes ilustrar con un ejemplo de coordenadas táctiles (x, y) y cómo viajan a través del sistema.**

<img width="803" height="922" alt="image" src="https://github.com/user-attachments/assets/0865e20c-b04a-4d2a-bf37-cfdfd9b3adf6" />





