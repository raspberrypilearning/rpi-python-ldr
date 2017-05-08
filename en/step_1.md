### Sensing light with the Raspberry Pi and Python

An Light Dependent Resistor (LDR) is a component that's resistance changes, depending on the amount of light that is falling upon it. The more light hitting the LDR, the lower the resistance will be.

![ldr](images/ldr.png)

The Raspberry Pi's [GPIO](rpi-gpio-pins) pins can be used with a variety of electronic components. Some components are [analogue and others are digital](generic-analogue-digital) however. Digital components are very easy to use, but because the Raspberry Pi's GPIO pins are only capable of being on or off, and in turn detecting whether another device is on or off, you need to do a little more work with analogue components.

The following sections will show you how to build a circuit and code the Raspberry Pi to detect light. If you're interested in the theory of how this works, then you can have a look at [this resource](generic-rc-charging-circuit)

#### Setting up the circuit

You are going to set up a Resistor-Capacitor (RC) circuit, using a 1µF capacitor and an LDR. The two components will need to be in series with each other. One leg of the LDR will be attached to a 3.3V pin of the Raspberry Pi. The **negative** leg of the capacitor will be attached to a *ground* pin. The positive leg of the capacitor will be connected to any of the standard **GPIO** pins on the Raspberry Pi. Here is one configuration of the circuit you could make.

![circuit](images/RC-circuit.png)

#### Detecting relative light levels.

The code for the light sensor is fairly simple. It will provide you with a relative value of the light in the environment as a floating point number between 0 and 1. The higher the value, the more intense the light is falling on the LDR. In the example code below, it is assumed that the LDR has been wired to pin 17.

```python
from gpiozero import LightSensor
ldr = LightSensor(17)
print(ldr.value)
```

#### Other methods

The `LightSensor` class has the following other methods:

```python
## Pause until no light is detected
wait_for_dark()
## Pause until light is dtected
wait_for_light()
## Return True if light is detected
light_detected
## Function to run when it is dark
when_dark = my_function
## Function to run wen it is light
when_light = my_function
```
