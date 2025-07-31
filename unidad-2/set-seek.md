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
    def init(self):
        self.state = "Init"
        self.startTime = 0
        self.interval = 0
        self.color = "ROJO"

    def mostrar_color(self):
        display.clear()
        if self.color == "ROJO":
            display.set_pixel(2, 0, 9)
            self.interval = 3000
        elif self.color == "VERDE":
            display.set_pixel(2, 4, 9)
            self.interval = 3000
        elif self.color == "AMARILLO":
            display.set_pixel(2, 2, 9)
            self.interval = 1000

    def cambiar_color(self):
        if self.color == "ROJO":
            self.color = "VERDE"
        elif self.color == "VERDE":
            self.color = "AMARILLO"
        elif self.color == "AMARILLO":
            self.color = "ROJO"

    def update(self):
        if self.state == "Init":
            self.startTime = utime.ticks_ms()
            self.state = "WaitTimeout"
            self.mostrar_color()

        elif self.state == "WaitTimeout":
            if utime.ticks_diff(utime.ticks_ms(), self.startTime) > self.interval:
                self.cambiar_color()
                self.startTime = utime.ticks_ms()
                self.mostrar_color()

semaforo = Semaforo()

while True:
    semaforo.update()
```

**Identifica los estados, eventos y acciones en tu código.**

* Estados: VERDE, AMARILLO Y ROJO.

* Eventos: Que el tiempo necesario para las acciones ocurra.

* Acciones:  Encender el LED correspondiente al estado, actualizar temporizador y cambiar el estado.
