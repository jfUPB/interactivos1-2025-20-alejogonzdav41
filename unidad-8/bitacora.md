
# Evidencias de la unidad 8

### Actividad 1

**Documenta los referentes visuales que te inspiren.**
<img width="860" height="638" alt="image" src="https://github.com/user-attachments/assets/3a687d33-5b97-4183-a1b2-02aee25da652" />
https://www.youtube.com/watch?v=HeBQVWMOXHk

**Define el concepto de las visuales que quieres crear.**

Quiero que cuando oprima un boton A tanto en el microbit como en el celular salga un gif de esqueleto bailando, lo mismo para el boton B pero con un gif diferente, y si no le doy a nada sale un gif normalillo.

**Explica cómo el móvil y el micro:bit controlarán las visuales.**

Con un boton A y B (visibles en el celular)/

**Haz un bocetos de todas las interfaces del sistema.**

<img width="1095" height="608" alt="image" src="https://github.com/user-attachments/assets/e84235e6-814a-4b1f-b7d3-de32a8b5e333" />

**Haz un diagrama que explique cómo se comunicarán los diferentes componentes del sistema.**

### Actividad 2

<img width="159" height="303" alt="image" src="https://github.com/user-attachments/assets/17ffc502-8b81-42e6-b015-b42fb172943d" />

***indec.html***
```js
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <title>Visual interactiva</title>
  <script src="https://cdn.jsdelivr.net/npm/p5@1.9.0/lib/p5.min.js"></script>
  <script src="https://cdn.socket.io/4.3.2/socket.io.min.js"></script>
  <script src="sketch.js"></script>
</head>
<body style="margin:0; overflow:hidden;">
</body>
</html>
```

***index.js***
```js
let socket;
let estado = "idle";
let idleGif, bailarinA, bailarinB;
let song;

function preload() {
  idleGif = loadImage("assets/idle0.gif");
  bailarinA = loadImage("assets/bailarinA.gif");
  bailarinB = loadImage("assets/bailarinB.gif");
  song = loadSound("assets/desdeelcielocayeroncaguamas.mp4");
}

function setup() {
  createCanvas(windowWidth, windowHeight);
  socket = io.connect("http://localhost:3000");
  song.loop();
  song.rate(0.7);

  socket.on("boton", (data) => {
    if (data == "A") {
      estado = "A";
      song.rate(2.0);
    } else if (data == "B") {
      estado = "B";
      song.rate(0.5);
    } else if (data == "idle") {
      estado = "idle";
      song.rate(0.7);
    }
  });
}

function draw() {
  background(0);
  imageMode(CENTER);
  let gif;

  if (estado === "A") {
    background(random(255), random(255), random(255));
    gif = bailarinA;
  } else if (estado === "B") {
    background(255, 0, 0);
    gif = bailarinB;
  } else {
    background(0);
    gif = idleGif;
  }

  image(gif, width / 2, height / 2, gif.width, gif.height);
}
```

***MOBILE***
***index.html***
```js
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <title>Control móvil</title>
  <script src="https://cdn.jsdelivr.net/npm/p5@1.9.0/lib/p5.min.js"></script>
  <script src="https://cdn.socket.io/4.3.2/socket.io.min.js"></script>
  <script src="sketch.js"></script>
</head>
<body style="margin:0; overflow:hidden; background:black;">
</body>
</html>
```

***sketch.js***
```js
let socket;

function setup() {
  createCanvas(windowWidth, windowHeight);
  socket = io.connect("http://localhost:3000");
}

function draw() {
  background(0);
  fill(255);
  textAlign(CENTER, CENTER);
  textSize(32);
  text("Presiona A o B", width / 2, 50);

  fill(0, 255, 0);
  rect(width / 4 - 100, height / 2 - 100, 200, 200);
  fill(0);
  text("A", width / 4, height / 2);

  fill(255, 0, 0);
  rect((3 * width) / 4 - 100, height / 2 - 100, 200, 200);
  fill(0);
  text("B", (3 * width) / 4, height / 2);
}

function touchStarted() {
  if (
    mouseX > width / 4 - 100 && mouseX < width / 4 + 100 &&
    mouseY > height / 2 - 100 && mouseY < height / 2 + 100
  ) {
    socket.emit("boton", "A");
  } else if (
    mouseX > (3 * width) / 4 - 100 && mouseX < (3 * width) / 4 + 100 &&
    mouseY > height / 2 - 100 && mouseY < height / 2 + 100
  ) {
    socket.emit("boton", "B");
  }
}

function touchEnded() {
  socket.emit("boton", "idle");
}
```

Me pondría 3.5, porque aunque el código no funcionó del todo bien, realicé toda la actividad y presenté el proyecto completo. Hice los bocetos, el diagrama y el código del celular y del computador. Faltó ajustar algunos detalles técnicos, pero logré mostrar la idea principal.
