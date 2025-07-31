# Unidad 2

## 🔎 Fase: Set + Seek

### Actividad 1

**Describe detalladamente cómo funciona este ejemplo.**

* Controla dos leds o pixeles en el microbit y con un temporizador los enciende y apaga dependiendo de un intervalo de tiempo.

**¿Cuáles son los estados en el programa?**

* Init, WaitTimeout.

**¿Cuáles son los eventos/inputs en el programa?**

* Interval, Update.

**¿Cuáles son las acciones en el programa?**

* Iniciar temporizador, mostrar pixel y alternar brillo de los leds.

### Actividad 2

**Escribe el código que soluciona este problema en tu bitácora.**

``` js
from microbit import *
import utime

class Semaforo:
    def __init__(self):
        self.state = "ROJO"
        self.startTime = utime.ticks_ms()
        self.interval = 0
        self.set_state("ROJO")
    def set_state(self, new_state):
        self.state = new_state
        self.startTime = utime.ticks_ms()
        display.clear()
        if self.state == "ROJO":
            display.set_pixel(2, 0, 9)
            self.interval = 3000
        elif self.state == "VERDE":
            display.set_pixel(2, 4, 9)
            self.interval = 3000
        elif self.state == "AMARILLO":
            display.set_pixel(2, 2, 9)
            self.interval = 1000
    def update(self):
        elapsed = utime.ticks_diff(utime.ticks_ms(), self.startTime)
        if elapsed > self.interval:
            if self.state == "ROJO":
                self.set_state("VERDE")
            elif self.state == "VERDE":
                self.set_state("AMARILLO")
            elif self.state == "AMARILLO":
                self.set_state("ROJO")

semaforo = Semaforo()

while True:
    semaforo.update()
```

**Identifica los estados, eventos y acciones en tu código.**

* Estados: VERDE, AMARILLO Y ROJO.

* Eventos: Interval que es el tiempo transcurrido entre los estados.

* Acciones:  Encender el LED correspondiente al estado, actualizar temporizador y cambiar el estado.
