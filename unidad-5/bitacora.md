
# Evidencias de la unidad 5

### Activida 1

**Describe cómo se están comunicando el micro:bit y el sketch de p5.js. ¿Qué datos envía el micro:bit?**

El micro:bit se conecta con el computador por el puerto serial. Lo que hace es medir con su acelerómetro los valores en los ejes X y Y, y también leer si los botones A y B están oprimidos o no.

**¿Cómo es la estructura del protocolo ASCII usado?**

Cada paquete tiene cuatro valores separados por comas y termina con un salto de línea *\n*.
El orden siempre es el mismo: primero X, luego Y, después el botón A y al final el botón B.

Muestra y explica la parte del código de p5.js donde lee los datos del micro:bit y los transforma en coordenadas de la pantalla.
```js
let data = port.readUntil("\n");
let values = data.split(",");
microBitX = int(values[0]) + windowWidth / 2;
microBitY = int(values[1]) + windowHeight / 2;
microBitAState = values[2].toLowerCase() === "true";
microBitBState = values[3].toLowerCase() === "true";
```
¿Cómo se generan los eventos A pressed y B released que se generan en p5.js a partir de los datos que envía el micro:bit?

En la función *updateButtonStates*, el programa compara cómo estaba el botón antes y cómo está ahora.
A pressed pasa cuando antes estaba en *false* y ahora cambia a *true*. Ahí el programa guarda la posición y el tamaño de la figura.
B released ocurre cuando antes estaba en *true* y ahora cambió a *false*. En ese caso se cambia el color a uno nuevo.

Capturas de pantalla de los algunos dibujos que hayas hecho con el sketch.
<img width="735" height="724" alt="image" src="https://github.com/user-attachments/assets/76d4e1aa-d6f1-4f2d-926f-4ed3bdbb94b4" />

### Actividad 2

**1. ¿Por qué se ve este resultado?**

* Cuando pongo la opción de Texto, se ven símbolos raros o “caracteres basura” porque los datos ya no se envían en letras o números que pueda entender directamente el computador, sino en binario. El micro:bit manda bytes crudos y el programa intenta interpretarlos como si fueran letras ASCII, entonces aparecen cosas que no tienen sentido.

**2. Lo que ves ¿Cómo está relacionado con esta línea de código?**

* Cuando selecciono la vista en Hex, los datos ya se muestran como números en base 16. Esto sí tiene sentido porque cada número hexadecimal representa un byte de los que se empacaron con struct.pack. La relación es que justo ese formato >2h2B define cuántos bytes se mandan y en qué orden, y por eso el resultado en Hex coincide con lo que se empaquetó.

**3. ¿Qué ventajas y desventajas ves en usar un formato binario en lugar de texto en ASCII?**

***Ventajas del binario:***

* Ocupa menos espacio (más compacto).

* Se transmite más rápido porque son menos bytes.

* Es más eficiente cuando mando muchos datos seguidos.

***Desventajas del binario:***

* Es difícil de leer directamente en la pantalla (se ven símbolos raros).

* Para interpretarlo necesito un programa que sepa cómo decodificar los bytes.

**4. ¿Cuántos bytes se están enviando por mensaje? ¿Cómo se relaciona esto con el formato '>2h2B'? ¿Qué significa cada uno de los bytes que se envían?**

El mensaje manda 6 bytes en total:

* 2h = dos enteros cortos de 2 bytes cada uno → 4 bytes (para xValue y yValue).
* 2B = dos enteros sin signo de 1 byte cada uno → 2 bytes (para aState y bState).

Cada byte corresponde a una parte del dato que el micro:bit está mandando: posición en X, posición en Y, estado del botón A y estado del botón B.

**5. Recuerda de la unidad anterior que es posible enviar números positivos y negativos para los valores de xValue y yValue. ¿Cómo se verían esos números en el formato '>2h2B'?**

En el formato h (entero corto con signo), los números se guardan en complemento a dos.
Si el número es positivo, en Hex se ve como un valor normal (ejemplo: 100 = 00 64).
Si es negativo, se guarda en su versión binaria negativa (ejemplo: -100 = FF 9C).
O sea, los negativos se representan con bytes que parecen grandes en Hex, pero en realidad significan valores negativos.

**6. Captura el resultado del experimento. ¿Qué diferencias ves entre los datos en ASCII y en binario? ¿Qué ventajas y desventajas ves en usar un formato binario en lugar de texto en ASCII? ¿Qué ventajas y desventajas ves en usar un formato ASCII en lugar de binario?**

***Diferencias:***

* En ASCII los datos se ven como números separados por comas (fáciles de leer).

* En binario se ven como bytes en Hex (más compactos, pero difíciles de leer a simple vista).

***Ventajas del binario:***

* Ocupa menos espacio.

* Es más rápido de enviar.

* Ideal para sensores o aplicaciones con muchos datos.

***Desventajas del binario:***

* No se entiende a simple vista.

* Se necesita decodificarlo con código.

***Ventajas del ASCII:***

* Fácil de leer e interpretar por humanos.

* Útil para hacer pruebas rápidas.

***Desventajas del ASCII:***

* Ocupa más espacio (cada número puede tener varios caracteres).

* Es más lento al enviar y procesar.

***Fotos de la actividad***

<img width="1237" height="277" alt="image" src="https://github.com/user-attachments/assets/162ae24b-18b0-496e-acaa-e8b2accfac61" />
<img width="1255" height="255" alt="image" src="https://github.com/user-attachments/assets/9f8b4a06-7c23-4d94-bda9-3762729d908c" />
<img width="1262" height="264" alt="image" src="https://github.com/user-attachments/assets/825fae8b-2429-404d-ae7f-8cf2cb9f7912" />


### Actividad 3

**1. ¿Por qué en la unidad anterior teníamos que enviar la información delimitada y además marcada con un salto de línea y ahora no es necesario?**

En la unidad anterior teníamos que mandar los datos como texto y en una sola línea, entonces el programa de p5.js no sabía dónde terminaba un dato y dónde empezaba el otro. Por eso se usaba un delimitador (una coma, por ejemplo) y un salto de línea para que quedara claro dónde acababa el paquete de datos.
Ahora ya no es necesario porque estamos mandando los datos en binario y el tamaño del paquete es fijo (6 bytes o 8 bytes con framing). Entonces el programa sabe que cada vez que recibe esos 6 u 8 bytes completos ya tiene toda la información, sin importar si llegan seguidos o no.

**2. Compara el código de la unidad anterior relacionado con la recepción de los datos seriales que ves ahora. ¿Qué cambios observas?**

Antes el código recibía los datos como texto, los separaba con split() y luego convertía cada pedazo en número o en booleano.
Ahora en cambio, el código usa readBytes() para leer directamente los bytes, crea un DataView y de ahí saca los números enteros (getInt16) y los estados (getUint8). En resumen: antes se trabajaba con texto y conversiones, ahora se trabaja con binario y estructuras de bytes.

**3. ¿Qué ves en la consola? ¿Por qué crees que se produce este error?**

En la consola a veces aparecen valores raros, como que microBitY no es el mismo que se mandó o que los botones salen apagados aunque estaban encendidos.
Eso pasa porque p5.js a veces agarra 6 bytes que no corresponden exactamente al mismo paquete que mandó el micro:bit. O sea, empieza a leer desde la mitad de un paquete y mezcla bytes de dos mensajes distintos. Eso es un error de sincronización.

**4. Analiza el código con framing, observa los cambios. Ejecuta y luego observa la consola. ¿Qué ves?**

Con framing ahora siempre hay un byte de inicio (0xAA) y un checksum al final para validar que los datos llegaron bien.
En la consola ya no aparecen valores locos ni saltos raros. Si el checksum no cuadra, el programa simplemente descarta ese paquete y espera al siguiente. Entonces los datos de microBitX, microBitY y los botones son más estables y confiables.

**5. ¿Qué cambios tienen los programas y qué puedes observar en la consola del editor de p5.js?**

***Los cambios son:***

En el micro:bit se agregó el header (0xAA) y el checksum al paquete.

En p5.js se implementó un buffer de bytes, se busca siempre el header y se valida el checksum antes de usar los datos.

En la consola del p5.js ahora se ven los valores de microBitX y microBitY bien centrados, y los estados de los botones aparecen correctos (true o false) sin que se “dañen” como antes. Si hay un error, aparece un mensaje de "Checksum error in packet" pero ya no se ve que los datos se mezclen.

### Actividad 4

***Codigo modificado para soportar el codigo de microbit de esa unidad***
```js
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <title>P_2_0_02 + Micro:bit (Binario)</title>
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
  <h2>Dibujo interactivo con p5.js + micro:bit (Binario)</h2>
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
    let buffer = [];

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
      while (true) {
        try {
          const { value, done } = await reader.read();
          if (done) break;
          if (value) {
            for (let byte of value) {
              buffer.push(byte);
              processBuffer();
            }
          }
        } catch (err) {
          console.error("Error leyendo datos:", err);
          break;
        }
      }
    }

    function processBuffer() {
      // Un paquete tiene: header (1) + datos (6) + checksum (1) = 8 bytes
      while (buffer.length >= 8) {
        // Buscar header (0xAA)
        if (buffer[0] !== 0xAA) {
          buffer.shift(); // eliminar bytes basura
          continue;
        }

        let packet = buffer.slice(0, 8);
        let data = packet.slice(1, 7);
        let checksum = packet[7];

        // Calcular checksum esperado
        let sum = data.reduce((a, b) => a + b, 0) % 256;

        if (checksum === sum) {
          // Decodificar datos binarios
          let view = new DataView(new Uint8Array(data).buffer);
          microbitX = view.getInt16(0, false); // big-endian
          microbitY = view.getInt16(2, false);
          microbitA = view.getUint8(4) === 1;
          microbitB = view.getUint8(5) === 1;

          if (microbitB) {
            background(255);
          }

          // quitar paquete procesado del buffer
          buffer.splice(0, 8);
        } else {
          console.warn("Checksum incorrecto, descartando paquete");
          buffer.shift();
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

<img width="1811" height="991" alt="image" src="https://github.com/user-attachments/assets/99bc0d6d-18c9-4643-925b-e95c9f844bb0" />

<img width="1841" height="1001" alt="image" src="https://github.com/user-attachments/assets/decbbb66-543a-49b8-906b-4b908ec40e8d" />

<img width="1868" height="997" alt="image" src="https://github.com/user-attachments/assets/8e21f9de-a41e-4b2d-a189-f0bafb9a3e78" />


Con un poco de ayuda de chatgpt me dí cuenta de varios cambios importantes respecto al original:

* Se eliminó el TextDecoder, ya que no trabajamos con texto.

* Se usa un buffer de bytes (buffer) para armar paquetes de 8 bytes.

* Se valida el header (0xAA) y el checksum antes de usar los datos.

* Se decodifican los datos con DataView en big-endian (false).

* Si el botón B está presionado, se borra el canvas.

| CRITERIOS | NOTA | JUSTIFICACIÓN|
|----------|----------|----------|
| 1. Profundidad de la Indagación  | 4 | Por medio de la información en la guía y también de las investigaciones de conceptos fuera de ella logré conseguir tener una indagación profunda, aunque de igual manera podrá mejorar.  |
| 2. Calidad de la Experimentación | 3.9 | Siento que a pesar de que me tomé mi tiempo para experimentar y ver diferentes ejemplos lo podría haber hecho mucho mejor.. |
| 3. Análisis y Reflexión | 4.1 | Analisé los resultados que iba consiguiendo y a veces tomaba ayuda de la IA para comprender conceptos y demás.|
| 4. Apropiación y Articulación de Conceptos | 4 | Logré aplicar los conceptos adquiridos en multiples casos que fueron aprovechados para las actividades. |
| TOTAL| 4 | |
