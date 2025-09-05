# Evidencias de la unidad 4

## Código

[Enlace a la aplicación a modificar](https://editor.p5js.org/generative-design/sketches/Bkqe595pkN)

Código a modificar:

``` js
// P_2_0_02
//
// Generative Gestaltung – Creative Coding im Web
// ISBN: 978-3-87439-902-9, First Edition, Hermann Schmidt, Mainz, 2018
// Benedikt Groß, Hartmut Bohnacker, Julia Laub, Claudius Lazzeroni
// with contributions by Joey Lee and Niels Poldervaart
// Copyright 2018
//
// http://www.generative-gestaltung.de
//
// Licensed under the Apache License, Version 2.0 (the "License");
// you may not use this file except in compliance with the License.
// You may obtain a copy of the License at http://www.apache.org/licenses/LICENSE-2.0
// Unless required by applicable law or agreed to in writing, software
// distributed under the License is distributed on an "AS IS" BASIS,
// WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
// See the License for the specific language governing permissions and
// limitations under the License.

/**
 * drawing with a changing shape by draging the mouse.
 *
 * MOUSE
 * position x          : length
 * position y          : thickness and number of lines
 * drag                : draw
 *
 * KEYS
 * del, backspace      : erase
 * s                   : save png
 */
'use strict';

function setup() {
  createCanvas(720, 720);
  noFill();
  background(255);
  strokeWeight(2);
  stroke(0, 25);
}

function draw() {
  if (mouseIsPressed && mouseButton == LEFT) {
    push();
    translate(width / 2, height / 2);

    var circleResolution = int(map(mouseY + 100, 0, height, 2, 10));
    var radius = mouseX - width / 2;
    var angle = TAU / circleResolution;

    beginShape();
    for (var i = 0; i <= circleResolution; i++) {
      var x = cos(angle * i) * radius;
      var y = sin(angle * i) * radius;
      vertex(x, y);
    }
    endShape();

    pop();
  }
}

function keyReleased() {
  if (keyCode == DELETE || keyCode == BACKSPACE) background(255);
  if (key == 's' || key == 'S') saveCanvas(gd.timestamp(), 'png');
}

```

[Enlace a la aplicación modificada](https://editor.p5js.org/alejogonzdav41/sketches/0CdhgIbQO)

Código modificado:

``` js
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <title>P_2_0_02 + Micro:bit</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      background: #fafafa;
      font-family: sans-serif;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
    }
    canvas {
      border: 1px solid #ccc;
      margin-top: 10px;
    }
    #connect {
      margin-top: 20px;
      padding: 10px 20px;
      border: none;
      background: #0077cc;
      color: white;
      font-size: 16px;
      border-radius: 8px;
      cursor: pointer;
    }
    #connect:hover {
      background: #005fa3;
    }
  </style>
</head>
<body>
  <h2>Dibujo interactivo con p5.js + micro:bit</h2>
  <button id="connect">Conectar micro:bit</button>

  <!-- Librería p5.js -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/1.9.0/p5.min.js"></script>

  <script>
    'use strict';

    // Variables globales para datos del micro:bit
    let microbitX = 0;
    let microbitY = 0;
    let microbitA = false;
    let microbitB = false;

    let port;
    let reader;

    document.getElementById("connect").addEventListener("click", async () => {
      try {
        port = await navigator.serial.requestPort();
        await port.open({ baudRate: 115200 });
        reader = port.readable.getReader();
        readLoop();
      } catch (err) {
        console.error("Error al conectar con el micro:bit:", err);
      }
    });

    async function readLoop() {
      const decoder = new TextDecoder();
      let buffer = "";
      while (true) {
        try {
          const { value, done } = await reader.read();
          if (done) break;
          buffer += decoder.decode(value, { stream: true });
          let lines = buffer.split("\n");
          buffer = lines.pop();
          for (let line of lines) {
            processSerial(line.trim());
          }
        } catch (err) {
          console.error("Error leyendo datos:", err);
          break;
        }
      }
    }

    function processSerial(data) {
      const parts = data.split(",");
      if (parts.length === 4) {
        microbitX = parseInt(parts[0]);
        microbitY = parseInt(parts[1]);
        microbitA = parts[2] === "True" || parts[2] === "1";
        microbitB = parts[3] === "True" || parts[3] === "1";
        if (microbitB) {
          background(255);
        }
      }
    }

    function setup() {
      createCanvas(720, 720);
      noFill();
      background(255);
      strokeWeight(2);
      stroke(0, 25);
    }

    function draw() {
      let xPos = mouseIsPressed ? mouseX : map(microbitX, -1024, 1024, 0, width);
      let yPos = mouseIsPressed ? mouseY : map(microbitY, -1024, 1024, 0, height);
      let isDrawing = mouseIsPressed || microbitA; // Botón A dibuja

      if (isDrawing) {
        push();
        translate(width / 2, height / 2);

        let circleResolution = int(map(yPos + 100, 0, height, 2, 10));
        let radius = xPos - width / 2;
        let angle = TAU / circleResolution;

        beginShape();
        for (let i = 0; i <= circleResolution; i++) {
          let x = cos(angle * i) * radius;
          let y = sin(angle * i) * radius;
          vertex(x, y);
        }
        endShape();

        pop();
      }
    }

    function keyReleased() {
      if (keyCode == DELETE || keyCode == BACKSPACE) background(255);
      if (key == 's' || key == 'S') saveCanvas(Date.now().toString(), 'png');
    }
  </script>
</body>
</html>

```

## Video

[Video demostratativo](https://youtu.be/Upvaz5rrDfU)


