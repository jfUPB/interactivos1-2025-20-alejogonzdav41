
# Evidencias de la unidad 5

### Reflect

1.
| Aspecto             | Protocolo ASCII                                                                                     | Protocolo Binario                                                                                          |
| ------------------- | --------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| **Eficiencia**      | Menos eficiente porque cada dato se convierte en texto.                   | Más eficiente porque los números se envían directamente en binario, por ejemplo el número 123 ocupa solo 1 byte.            |
| **Velocidad**       | Más lento, porque se debe pasar de texto a número.                                                 | Más rápido, porque se lee el número tal cual está en la memoria.                                              |
| **Facilidad**       | Más fácil de entender y depurar, porque los datos se pueden leer directamente. | Más difícil de leer a simple vista porque los datos no son visibles como texto, aparecen como bytes un poco extraños. |
| **Uso de recursos** | Usa más memoria y procesador por las conversiones.                                                  | Usa menos memoria y procesador, por lo que es mas eficiente para datos en tiempo real como lo son los sensores.                             |

2. ¿Por qué fue necesario introducir framing en el protocolo binario?

* Se usan bytes especiales al inicio (y a veces al final) que indican: “aquí comienza un paquete”. Así, el receptor sabe cuándo leer los datos completos.
   
3. ¿Cómo funciona el framing?

* Es un valor fijo que se usa al inicio para decir “este es el principio del paquete”. Sirve para que el receptor se sincronice.

4. ¿Qué es un carácter de sincronización?

* Es una suma de los datos enviada junto al paquete. El receptor vuelve a calcular la suma y la compara: si son iguales, el paquete está bien; si no, hubo un error en la transmisión.

5. ¿Qué es el checksum y para qué sirve?

* Une los nuevos bytes leídos (newData) con los que ya estaban en el buffer (serialBuffer). Se hace para no perder información cuando los datos llegan en partes.
