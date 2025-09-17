
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

<img width="559" height="275" alt="image" src="https://github.com/user-attachments/assets/874652e7-af55-4aab-95cf-c1a3b44a6f69" />

* Cuando pongo la opción de Texto, se ven símbolos raros o “caracteres basura” porque los datos ya no se envían en letras o números que pueda entender directamente el computador, sino en binario. El micro:bit manda bytes crudos y el programa intenta interpretarlos como si fueran letras ASCII, entonces aparecen cosas que no tienen sentido.

**2. Lo que ves ¿Cómo está relacionado con esta línea de código?**

<img width="600" height="312" alt="image" src="https://github.com/user-attachments/assets/8ad5230c-8551-467d-a01a-8a8b3f9daf9e" />

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
