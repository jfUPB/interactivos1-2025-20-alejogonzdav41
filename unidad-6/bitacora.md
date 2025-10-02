
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

🧐🧪✍️ Experimenta

Detén el servidor si está corriendo.

Cambia la primera ruta de /page1 a /pagina_uno.

Inicia el servidor.

Intenta acceder a http://localhost:3000/page1. ¿Funciona?

- No funciona

Ahora intenta acceder a http://localhost:3000/pagina_uno. ¿Funciona?

- Si funciona

¿Qué te dice esto sobre cómo el servidor asocia URLs con respuestas? Restaura el código.

- Usa el nombre definido para saber que usa o no.

🧐🧪✍️
Experimenta

Asegúrate de que el servidor esté corriendo (npm start).

Abre http://localhost:3000/page1 en una pestaña. Observa la terminal del servidor. ¿Qué mensaje ves? Anota el ID.

<img width="560" height="23" alt="image" src="https://github.com/user-attachments/assets/cb78816a-fb22-49cd-aaff-0e297f575043" />

Abre http://localhost:3000/page2 en OTRA pestaña. Observa la terminal. ¿Qué mensaje ves? ¿El ID es diferente?

<img width="561" height="23" alt="image" src="https://github.com/user-attachments/assets/08865230-5934-422e-bf25-0f59e5b8aff1" />

- Si, el ID es diferente.

Cierra la pestaña de page1. Observa la terminal. ¿Qué mensaje ves? ¿Coincide el ID con el que anotaste?

User disconnected - ID: g3EeSZAQZU7r_VW6AAAB

- Si coincide.

Cierra la pestaña de page2. Observa la terminal.

User disconnected - ID: nfY8TvsM8xpIeQIkAAAD

🧐🧪✍️
Experimenta

Inicia el servidor y abre page1 y page2.

Mueve la ventana de page1. Observa la terminal del servidor. ¿Qué evento se registra (win1update o win2update)? ¿Qué datos (Data:) ves?

- Received win1update from ID: g3EeSZAQZU7r_VW6AAAB Data: { x: 58, y: 220, width: 989, height: 944 }

Mueve la ventana de page2. Observa la terminal. ¿Qué evento se registra ahora? ¿Qué datos ves?

- Received win2update from ID: nfY8TvsM8xpIeQIkAAAD Data: { x: 439, y: 320, width: 989, height: 944 }

Experimento clave: cambia socket.broadcast.emit(‘getdata’, page1); por socket.emit(‘getdata’, page1); (quitando broadcast). Reinicia el servidor, abre ambas páginas. Mueve page1. ¿Se actualiza la visualización en page2? ¿Por qué sí o por qué no? (Pista: ¿A quién le envía el mensaje socket.emit?). Restaura el código a broadcast.emit.

- Si mueves la página 1, se desconecta del todo, como si se perdiera de la otra. Pero si mueves la página 2, la conexión medio que regresa, aunque no queda perfecta. Es como si se viera la otra ventana, pero los datos no se mandan bien. Lo que pasa con los mensajes es que el socket.emit se manda el mensaje a sí mismo.
Por alguna razón, el código ahora se confunde y cuando mueves la página 1, se pierde la señal, y la única forma de que se "reconecte" es moviendo la página 2. Hay que revisar la lógica de la sincronización en el server.js para arreglarlo.

🧐🧪✍️ Experimenta

Detén el servidor.

Cambia const port = 3000; a const port = 3001;.

Inicia el servidor. ¿Qué mensaje ves en la consola? ¿En qué puerto dice que está escuchando?

Intenta abrir http://localhost:3000/page1. ¿Funciona?

- No funciona.

Intenta abrir http://localhost:3001/page1. ¿Funciona?

- SI funciona.

¿Qué aprendiste sobre la variable port y la función listen? Restaura el puerto a 3000.

- Aprendí que la variable port es la que nos muestra en donde se encuentra el servidor mientras que la funcion listen se encarga de inicializar en el puerto especificado.

### Actividad 4

🧐🧪✍️
Experimenta

Abre page2.html en tu navegador (con el servidor corriendo).

Abre la consola de desarrollador (F12).

Detén el servidor Node.js (Ctrl+C).

Refresca la página page2.html. Observa la consola del navegador. ¿Ves algún error relacionado con la conexión? ¿Qué indica?

Vuelve a iniciar el servidor y refresca la página. ¿Desaparecen los errores?

🧐🧪✍️
Experimenta

Comenta la línea socket.emit(‘win2update’, currentPageData, socket.id); dentro del listener connect.

Reinicia el servidor y refresca page1.html y page2.html.

Mueve la ventana de page2 un poco para que envíe una actualización.

¿Qué pasó? ¿Por qué?

🧐🧪✍️
Experimenta

Asegúrate de tener este console.log en page2.js.

Abre ambas páginas.

Mueve la ventana de page1. Observa la consola del navegador de page2. ¿Qué datos muestra?

Mueve la ventana de page2. Observa la consola de page1. ¿Qué pasa? ¿Por qué?

🧐🧪✍️
Experimenta

Observa checkWindowPosition() en page2.js y modifica el código del if para comprobar si el código dentreo de este se ejecuta.
Mueve cada ventana y observa las consolas.
¿Qué puedes concluir y por qué?
🧐🧪✍️
Experimenta
(¡Sé creativo!)

Cambia el background(220) para que dependa de la distancia entre las ventanas. Puedes calcular la magnitud del resultingVector usando let distancia = resultingVector.mag(); y luego usa map() para convertir esa distancia a un valor de gris o color. background(map(distancia, 0, 1000, 255, 0)); (ajusta el rango 0-1000 según sea necesario).

Inventa otra modificación creativa.



### Actividad 5

Mi idea es que en la pagina 1 haya un circulo con un triangulo pegado a un lado (como un cañon) que dispare circulos pequeños cada 4 segundos a la pagina dos, ya en la pagina 2 despues de estar 1 segundo los circulos peequeños explotan en 3 cuadrados que desaparecen a lo largo de 3 segundos.

<img width="938" height="535" alt="image" src="https://github.com/user-attachments/assets/e7dd60b9-f0fd-4e0b-a065-0dea81dbb980" />

<img width="1583" height="494" alt="image" src="https://github.com/user-attachments/assets/c4a4a993-e55f-4c0c-a41c-24c7a1dd87b3" />
<img width="1671" height="493" alt="image" src="https://github.com/user-attachments/assets/07f4caf5-c3c2-47f7-b2d7-e378c88d08b0" />
<img width="1657" height="485" alt="image" src="https://github.com/user-attachments/assets/0d7cb22c-5110-4e79-82b8-afeb7a96b37b" />
<img width="727" height="841" alt="image" src="https://github.com/user-attachments/assets/f55b3679-5d3c-4314-a9fa-ea190067fa72" />
<img width="1745" height="966" alt="image" src="https://github.com/user-attachments/assets/56b2f929-090f-4f32-89b6-baec624f8218" />

***page1.html***
```cpp
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portal de Asalto - Cañón (Page 1)</title>
    <script src="https://cdn.jsdelivr.net/npm/p5@1.11.0/lib/p5.min.js"></script>
    <script src="https://cdn.socket.io/4.7.5/socket.io.min.js"></script>
    <style>
        body {
            margin: 0;
            overflow: hidden;
            background-color: #1e1e1e;
        }
    </style>
</head>
<body>
    <script defer src="page1.js"></script>
</body>
</html>
```

***page1.js***
```cpp
let currentPageData = {
    x: window.screenX,
    y: window.screenY,
    width: window.innerWidth,
    height: window.innerHeight
}

let previousPageData = {
    x: window.screenX,
    y: window.screenY,
    width: window.innerWidth,
    height: window.innerHeight
};

let remotePageData = { x: 0, y: 0, width: 100, height: 100 };
let socket;
let isConnected = false;
let hasRemoteData = false;
let isFullySynced = false;

let cannon;
let lastFireTime = 0;
const fireInterval = 4000;

class Cannon {
    constructor(x, y, size) {
        this.x = x;
        this.y = y;
        this.size = size;
        this.bodyColor = color(50, 50, 200);
        this.barrelColor = color(100, 100, 255);
    }

    draw(targetX, targetY) {
        let angle = atan2(targetY - this.y, targetX - this.x);

        push();
        translate(this.x, this.y);
        rotate(angle);

        fill(this.barrelColor);
        rectMode(CORNER);
        rect(this.size / 2, -this.size / 8, this.size * 1.2, this.size / 4);

        pop();

        fill(this.bodyColor);
        ellipse(this.x, this.y, this.size, this.size);
    }
}

function setup() {
    createCanvas(windowWidth, windowHeight);
    frameRate(60);
    socket = io();
    cannon = new Cannon(width / 2, height / 2, 100); 

    socket.on('connect', () => {
        console.log('Connected with ID:', socket.id);
        isConnected = true;
        socket.emit('win1update', currentPageData, socket.id);
        setTimeout(() => { socket.emit('requestSync'); }, 500);
    });

    socket.on('getdata', (response) => {
        if (response && response.data && isValidRemoteData(response.data)) {
            remotePageData = response.data;
            hasRemoteData = true;
            console.log('Received valid remote data (Page 2):', remotePageData);
            socket.emit('confirmSync');
        }
    });

    socket.on('fullySynced', (synced) => {
        isFullySynced = synced;
        console.log('Sync status:', synced ? 'SYNCED' : 'NOT SYNCED');
    });

    socket.on('peerDisconnected', () => {
        hasRemoteData = false;
        isFullySynced = false;
        console.log('Peer disconnected, waiting for reconnection...');
    });

    socket.on('disconnect', () => {
        isConnected = false;
        hasRemoteData = false;
        isFullySynced = false;
        console.log('Disconnected from server');
    });
}

function isValidRemoteData(data) {
    return data && 
           typeof data.x === 'number' && 
           typeof data.y === 'number' && 
           typeof data.width === 'number' && data.width > 0 &&
           typeof data.height === 'number' && data.height > 0;
}

function checkWindowPosition() {
    currentPageData = {
        x: window.screenX,
        y: window.screenY,
        width: window.innerWidth,
        height: window.innerHeight
    };

    if (currentPageData.x !== previousPageData.x || currentPageData.y !== previousPageData.y || 
        currentPageData.width !== previousPageData.width || currentPageData.height !== previousPageData.height) {

        socket.emit('win1update', currentPageData, socket.id);
        previousPageData = currentPageData;
    }
}

function fireProjectile(startX, startY, targetX, targetY) {
    let angle = atan2(targetY - startY, targetX - startX);
    let fireRadius = cannon.size / 2 + cannon.size * 1.2; 
    let projectileStartX = startX + cos(angle) * fireRadius * 0.5;
    let projectileStartY = startY + sin(angle) * fireRadius * 0.5;

    let screenX = currentPageData.x + projectileStartX;
    let screenY = currentPageData.y + projectileStartY;
    
    const projectileData = {
        id: Date.now(),
        startX: screenX,
        startY: screenY,
        targetX: remotePageData.x + remotePageData.width / 2,
        targetY: remotePageData.y + remotePageData.height / 2,
        timestamp: millis()
    };

    socket.emit('fireProjectile', projectileData);
    console.log('Fired projectile:', projectileData.id);
}

function draw() {
    background(30);

    if (isFullySynced) {
        checkWindowPosition();

        cannon.x = width / 2;
        cannon.y = height / 2;

        let targetX_screen = remotePageData.x + remotePageData.width / 2;
        let targetY_screen = remotePageData.y + remotePageData.height / 2;
        
        let localCannonX_screen = currentPageData.x + cannon.x;
        let localCannonY_screen = currentPageData.y + cannon.y;

        let targetX_local = targetX_screen - localCannonX_screen + cannon.x;
        let targetY_local = targetY_screen - localCannonY_screen + cannon.y;

        cannon.draw(targetX_local, targetY_local);

        stroke(100, 100, 100, 100);
        strokeWeight(1);
        line(cannon.x, cannon.y, targetX_local, targetY_local);

        if (millis() - lastFireTime > fireInterval) {
            fireProjectile(cannon.x, cannon.y, targetX_local, targetY_local);
            lastFireTime = millis();
        }
    }
    
    showStatus(getStatusMessage(), getStatusColor());
}

function getStatusMessage() {
    if (!isConnected) return 'Conectando al servidor...';
    if (!hasRemoteData) return 'Esperando conexión de la otra ventana...';
    if (!isFullySynced) return 'Sincronizando datos...';
    return 'SINCRONIZADO: ¡Cañón Activo! (Disparo en 4s)';
}

function getStatusColor() {
    if (!isConnected || !hasRemoteData || !isFullySynced) return color(255, 165, 0);
    return color(0, 255, 0);
}

function showStatus(message, statusColor) {
    textSize(20);
    textAlign(CENTER, CENTER);
    noStroke();
    fill(0, 0, 0, 150);
    rectMode(CENTER);
    let textW = textWidth(message) + 40;
    let textH = 40;
    rect(width / 2, 1 * height / 10, textW, textH, 10);
    fill(statusColor);
    text(message, width / 2, 1 * height / 10);
}

function windowResized() {
    resizeCanvas(windowWidth, windowHeight);
    if (cannon) {
        cannon.x = width / 2;
        cannon.y = height / 2;
    }
}

```

***page2.html***
```cpp
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portal de Asalto - Receptor (Page 2)</title>
    <script src="https://cdn.jsdelivr.net/npm/p5@1.11.0/lib/p5.min.js"></script>
    <script src="https://cdn.socket.io/4.7.5/socket.io.min.js"></script>
    <style>
        body {
            margin: 0;
            overflow: hidden;
            background-color: #1e1e1e;
        }
    </style>
</head>

<body>
    <script defer src="page2.js"></script>
</body>
</html>
```

***page2.js***
```cpp
let currentPageData = {
    x: window.screenX,
    y: window.screenY,
    width: window.innerWidth,
    height: window.innerHeight

}

let previousPageData = {
    x: window.screenX,
    y: window.screenY,
    width: window.innerWidth,
    height: window.innerHeight
};

let remotePageData = { x: 0, y: 0, width: 100, height: 100 };
let point2 = [currentPageData.width / 2, currentPageData.height / 2];
let socket;
let isConnected = false;
let hasRemoteData = false;
let isFullySynced = false;

let projectiles = [];
let explosions = [];
const projectileSpeed = 0.5;

class Projectile {
    constructor(data) {
        this.id = data.id;
        this.startScreenX = data.startX;
        this.startScreenY = data.startY;
        this.targetScreenX = data.targetX;
        this.targetScreenY = data.targetY;
        this.startTime = data.timestamp;
        this.diameter = 20;
        this.color = color(255, 255, 0);
        this.life = true;
        this.distance = dist(this.startScreenX, this.startScreenY, this.targetScreenX, this.targetScreenY);
        this.travelTime = this.distance / projectileSpeed;
    }

    draw(currentScreenX, currentScreenY) {
        if (!this.life) return false;
        
        let elapsed = millis() - this.startTime;
        let ratio = min(1, elapsed / this.travelTime);

        let currentAbsX = lerp(this.startScreenX, this.targetScreenX, ratio);
        let currentAbsY = lerp(this.startScreenY, this.targetScreenY, ratio);

        this.localX = currentAbsX - currentScreenX;
        this.localY = currentAbsY - currentScreenY;

        fill(this.color);
        noStroke();
        ellipse(this.localX, this.localY, this.diameter, this.diameter);

        if (ratio >= 1) {
            this.life = false;
            return true;
        }
        return false;
    }
}

class Explosion {
    constructor(x, y, id) {
        this.id = id;
        this.x = x;
        this.y = y;
        this.creationTime = millis();
        this.duration = 4000;
        this.preExplosionDuration = 1000;
        this.squareDuration = 3000;
        this.radius = 20; 
        this.squares = [];
        this.colors = [color(255, 0, 0, 200), color(0, 255, 0, 200), color(0, 0, 255, 200)];
        this.squareSize = 30;

        for (let i = 0; i < 3; i++) {
            let angle = random(TWO_PI);
            let distance = random(80, 150);
            this.squares.push({
                x: this.x,
                y: this.y,
                targetX: this.x + cos(angle) * distance,
                targetY: this.y + sin(angle) * distance,
                color: this.colors[i]
            });
        }
    }
    
    draw() {
        let elapsed = millis() - this.creationTime;
        
        if (elapsed < this.preExplosionDuration) { 
            let alpha = map(elapsed, 0, this.preExplosionDuration, 255, 0);
            fill(255, 200, 0, alpha); 
            noStroke();
            ellipse(this.x, this.y, this.radius * 2, this.radius * 2);
            
        } else if (elapsed >= this.preExplosionDuration && elapsed < this.duration) { 
            let explosionElapsed = elapsed - this.preExplosionDuration;
            let ratio = explosionElapsed / this.squareDuration;
            
            for (let i = 0; i < this.squares.length; i++) {
                let sq = this.squares[i];
                let currentX = lerp(this.x, sq.targetX, ratio);
                let currentY = lerp(this.y, sq.targetY, ratio);

                let currentSize = lerp(this.squareSize, 0, ratio); 

                let alpha = map(ratio, 0, 1, 255, 0);
                sq.color.setAlpha(alpha);
                
                fill(sq.color);
                rectMode(CENTER);
                noStroke();
                rect(currentX, currentY, currentSize, currentSize);
            }
        } else {
            return true; 
        }
        return false;
    }
}

function setup() {
    createCanvas(windowWidth, windowHeight);
    frameRate(60);
    socket = io();

    socket.on('connect', () => {
        console.log('Connected with ID:', socket.id);
        isConnected = true;
        socket.emit('win2update', currentPageData, socket.id);
        setTimeout(() => { socket.emit('requestSync'); }, 500);
    });

    socket.on('newProjectile', (data) => {
        console.log('Received projectile data:', data.id);
        if (isFullySynced) {
            projectiles.push(new Projectile(data));
        }
    });


    socket.on('getdata', (response) => {
        if (response && response.data && isValidRemoteData(response.data)) {
            remotePageData = response.data;
            hasRemoteData = true;
            console.log('Received valid remote data (Page 1):', remotePageData);
            socket.emit('confirmSync');
        }
    });

    socket.on('fullySynced', (synced) => {
        isFullySynced = synced;
        console.log('Sync status:', synced ? 'SYNCED' : 'NOT SYNCED');
    });

    socket.on('peerDisconnected', () => {
        hasRemoteData = false;
        isFullySynced = false;
        console.log('Peer disconnected, waiting for reconnection...');
    });

    socket.on('disconnect', () => {
        isConnected = false;
        hasRemoteData = false;
        isFullySynced = false;
        console.log('Disconnected from server');
    });
}

function isValidRemoteData(data) {
    return data && 
           typeof data.x === 'number' && 
           typeof data.y === 'number' && 
           typeof data.width === 'number' && data.width > 0 &&
           typeof data.height === 'number' && data.height > 0;
}

function checkWindowPosition() {
    currentPageData = {
        x: window.screenX,
        y: window.screenY,
        width: window.innerWidth,
        height: window.innerHeight
    };

    if (currentPageData.x !== previousPageData.x || currentPageData.y !== previousPageData.y || 
        currentPageData.width !== previousPageData.width || currentPageData.height !== previousPageData.height) {

        point2 = [currentPageData.width / 2, currentPageData.height / 2]
        socket.emit('win2update', currentPageData, socket.id);
        previousPageData = currentPageData; 
    }
}


function draw() {
    background(30);
    
    if (isFullySynced) {
        checkWindowPosition();

        fill(200, 50, 50);
        ellipse(point2[0], point2[1], 150, 150);

        for (let i = projectiles.length - 1; i >= 0; i--) {
            let p = projectiles[i];

            let hasArrived = p.draw(currentPageData.x, currentPageData.y);
            
            if (hasArrived) {
                explosions.push(new Explosion(p.localX, p.localY, p.id));
                projectiles.splice(i, 1);
            }
        }

        for (let i = explosions.length - 1; i >= 0; i--) {
            let exp = explosions[i];
            let isFinished = exp.draw();
            
            if (isFinished) {
                socket.emit('explosionFinished', exp.id);
                explosions.splice(i, 1);
            }
        }

        let vector2 = createVector(remotePageData.x, remotePageData.y);
        let vector1 = createVector(currentPageData.x, currentPageData.y);
        let resultingVector = createVector(vector2.x - vector1.x, vector2.y - vector1.y);

        fill(50, 50, 200, 150);
        ellipse(resultingVector.x + remotePageData.width / 2, resultingVector.y + remotePageData.height / 2, 100, 100);
    }
    
    showStatus(getStatusMessage(), getStatusColor());
}

function getStatusMessage() {
    if (!isConnected) return 'Conectando al servidor...';
    if (!hasRemoteData) return 'Esperando conexión de la otra ventana...';
    if (!isFullySynced) return 'Sincronizando datos...';
    return `SINCRONIZADO: Proyectiles en tránsito (${projectiles.length}), Explosiones activas (${explosions.length})`;
}

function getStatusColor() {
    if (!isConnected || !hasRemoteData || !isFullySynced) return color(255, 165, 0);
    return color(0, 255, 0);
}

function showStatus(message, statusColor) {
    textSize(20);
    textAlign(CENTER, CENTER);
    noStroke();
    fill(0, 0, 0, 150);
    rectMode(CENTER);
    let textW = textWidth(message) + 40;
    let textH = 40;
    rect(width / 2, 1 * height / 10, textW, textH, 10);
    fill(statusColor);
    text(message, width / 2, 1 * height / 10);
}

function windowResized() {
    resizeCanvas(windowWidth, windowHeight);
    point2 = [width / 2, height / 2];
}
```

***server.js***
```cpp
const express = require('express');
const http = require('http');
const socketIO = require('socket.io');
const path = require('path');
const app = express();
const server = http.createServer(app); 
const io = socketIO(server); 
const port = 3000;

let page1 = { x: 0, y: 0, width: 100, height: 100 };
let page2 = { x: 0, y: 0, width: 100, height: 100 };
let connectedClients = new Map();
let syncedClients = new Set();
let page1SocketId = null;
let page2SocketId = null;

app.use(express.static(path.join(__dirname, 'views')));

app.get('/page1', (req, res) => {
    res.sendFile(path.join(__dirname, 'views', 'page1.html'));
});

app.get('/page2', (req, res) => {
    res.sendFile(path.join(__dirname, 'views', 'page2.html'));
});

io.on('connection', (socket) => {
    console.log('A user connected - ID:', socket.id);
    connectedClients.set(socket.id, { page: null, synced: false });
    
    socket.on('disconnect', () => {
        console.log('User disconnected - ID:', socket.id);
        const clientInfo = connectedClients.get(socket.id);

        if (clientInfo?.page === 'page1') {
            page1SocketId = null;
        } else if (clientInfo?.page === 'page2') {
            page2SocketId = null;
        }

        connectedClients.delete(socket.id);
        syncedClients.delete(socket.id);
        socket.broadcast.emit('peerDisconnected');
        checkAndNotifySyncStatus();
    });

    socket.on('win1update', (window1, sendid) => {
        if (isValidWindowData(window1)) {
            page1 = window1;
            page1SocketId = socket.id;
            connectedClients.set(socket.id, { page: 'page1', synced: false });
            if (page2SocketId) {
                io.to(page2SocketId).emit('getdata', { data: page1, from: 'page1' });
            }
            checkAndNotifySyncStatus();
        }
    });

    socket.on('win2update', (window2, sendid) => {
        if (isValidWindowData(window2)) {
            page2 = window2;
            page2SocketId = socket.id;
            connectedClients.set(socket.id, { page: 'page2', synced: false });
            if (page1SocketId) {
                io.to(page1SocketId).emit('getdata', { data: page2, from: 'page2' });
            }
            checkAndNotifySyncStatus();
        }
    });

    socket.on('requestSync', () => {
        const clientInfo = connectedClients.get(socket.id);
        if (clientInfo?.page === 'page1' && page2SocketId) {
            socket.emit('getdata', { data: page2, from: 'page2' });
        } else if (clientInfo?.page === 'page2' && page1SocketId) {
            socket.emit('getdata', { data: page1, from: 'page1' });
        }
    });

    socket.on('confirmSync', () => {
        syncedClients.add(socket.id);
        const clientInfo = connectedClients.get(socket.id);
        if (clientInfo) {
            connectedClients.set(socket.id, { ...clientInfo, synced: true });
        }
        checkAndNotifySyncStatus();
    }); 
    
    socket.on('fireProjectile', (projectileData) => {
        console.log('Projectile fired:', projectileData.id);
        if (page2SocketId) {
             io.to(page2SocketId).emit('newProjectile', projectileData);
        }
    });

    socket.on('explosionFinished', (id) => {
        console.log('Explosion finished on Page 2 for ID:', id);
    });
});

function isValidWindowData(data) {
    return data && 
           typeof data.x === 'number' && 
           typeof data.y === 'number' && 
           typeof data.width === 'number' && data.width > 0 &&
           typeof data.height === 'number' && data.height > 0;
}

function checkAndNotifySyncStatus() {
    const page1Clients = Array.from(connectedClients.entries()).filter(([id, info]) => info.page === 'page1');
    const page2Clients = Array.from(connectedClients.entries()).filter(([id, info]) => info.page === 'page2');
    
    const bothPagesConnected = page1Clients.length > 0 && page2Clients.length > 0;
    const allClientsSynced = bothPagesConnected && page1Clients.every(([id, info]) => syncedClients.has(id)) && page2Clients.every(([id, info]) => syncedClients.has(id));
    
    const status = bothPagesConnected && allClientsSynced;

    io.emit('fullySynced', status);
    if (status) {
         console.log('All clients are fully synced and ready for interaction.');
    }
}

server.listen(port, () => {
    console.log(`Server is listening on http://localhost:${port}`);
    console.log(`Open in two windows:`);
    console.log(`- Page 1: http://localhost:${port}/page1`);
    console.log(`- Page 2: http://localhost:${port}/page2`);
});
```

### Autoevaluación









