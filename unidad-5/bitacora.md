
# Evidencias de la unidad 5\

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

