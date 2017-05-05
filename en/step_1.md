### Sensing light with the Raspberry Pi and Python

An Light Dependent Resistor (LDR) is a component that's resistance changes, depending on the amount of light that is falling upon it. The more light hitting the LDR, the lower the resistance will be.

![ldr](images/ldr.png)

The Raspberry Pi's [GPIO](rpi-gpio-pins) pins can be used with a variety of electronic components. Some components are [analogue and others are digital](generic-analogue-digital) however. Digital components are very easy to use, but becuase the Raspberry Pi's GPIO pins are only capable of being on or off, and in turn detecting whether another device is on or off, you need to do a little more work with analogue components.

The following sections ill show you how o build a circuit and code the raspberry Pi to detect light. If you're interested in the theory of how this works, then you can have a look at [this resource](generic-rc-charging-circuit)

#### Setting up the circuit


