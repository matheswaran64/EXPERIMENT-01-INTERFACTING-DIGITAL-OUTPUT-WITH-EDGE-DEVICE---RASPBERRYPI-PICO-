# EXPERIMENT-01 INTERFACTING DIGITAL OUTPUT WITH EDGE DEVICE RASPBERRYPI PICO

## AIM
To interface a digital output device (LED) with the Raspberry Pi Pico and control it using MicroPython.

## APPARATUS REQUIRED
1. Raspberry Pi Pico
2. LED (Light Emitting Diode)
3. 330Ω Resistor
4. Breadboard
5. Jumper Wires
5. USB Cable
6. Computer with Thonny IDE
   
## THEORY

FIGURE-01 RASPI PICO PINOUT DIAGRAM
Raspberry Pi Pico is a microcontroller board based on the RP2040 chip. It supports MicroPython, making it suitable for IoT and embedded applications. The Raspberry Pi Pico is a compact microcontroller board featuring a 40-pin layout, including power, ground, GPIO, and communication interface pins. It operates with a dual-core ARM Cortex-M0+ processor and supports MicroPython and C/C++ programming. The power pins include VBUS (5V from USB), VSYS (1.8V to 5.5V input), 3V3(OUT) (regulated 3.3V output), and multiple ground (GND) connections. The board offers 26 multi-purpose GPIO pins (GP0 to GP28), which can be used for digital input, output, PWM, and communication interfaces such as I2C, SPI, and UART. It also features three analog-to-digital converter (ADC) pins (GP26, GP27, GP28), used for reading analog sensor values, along with an ADC_VREF pin to set the reference voltage. For communication, I2C (SDA, SCL), SPI (MOSI, MISO, SCK), and UART (TX, RX) interfaces are mapped across different GPIO pins, allowing seamless connectivity with sensors and peripherals. All GPIO pins support PWM (Pulse Width Modulation), making it useful for motor control, LED brightness adjustment, and sound applications. The BOOTSEL button enables USB mass storage mode for firmware flashing, while the DEBUG pins (SWD interface) provide debugging capabilities. With its low power consumption, flexible GPIO options, and rich interface support, the Raspberry Pi Pico is widely used for IoT, embedded systems, robotics, and automation projects.

## WORKING PRINCIPLE:

The LED is connected to one of the GPIO pins of the Pico. The MicroPython script sets the GPIO pin HIGH to turn the LED ON and LOW to turn it OFF. 
### CIRCUIT DIAGRAM 
Connect the anode (longer leg) of the LED to GP15 via a 330Ω resistor. Connect the cathode (shorter leg) of the LED to GND (ground).


## PROGRAM (MicroPython)
### 1. 
```
from machine import Pin
from utime import sleep
print("Pi Pico")
led=Pin(0,Pin.OUT)
while True:
  led.Toggle()
  sleep(0.5)
```
### 2.
```
from machine import Pin
from utime import sleep
led1=Pin(0,Pin.OUT)
led2=Pin(3,Pin.OUT)
led3=Pin(9,Pin.OUT)
while True:
  led1.toggle()
  sleep(0.5)
  led2.toggle()
  sleep(0.5)
  led3.toggle()
  sleep(2)
```
### 3.
```
from machine import Pin
from utime import sleep
led1=Pin(0,Pin.OUT)
led2=Pin(3,Pin.OUT)
led3=Pin(9,Pin.OUT)
buzzer=Pin(9,Pin.OUT)
while True:
  led1.toggle()
  sleep(0.5)
  led2.toggle()
  sleep(0.5)
  led3.toggle()
  buzzer.toggle()
  sleep(2)
```
## OUPUT 
### 1. 
![image](https://github.com/user-attachments/assets/1d2b85ab-358a-45f5-a4b1-8a44dcc9e43d)

### 2.
![image](https://github.com/user-attachments/assets/67232426-d8ea-4c63-a2e4-983b2d558203)

### 3.
![image](https://github.com/user-attachments/assets/5d11aad7-4a87-499f-9f74-6cf7f3e1d0ca)


## RESULTS
The LED connected to the Raspberry Pi Pico successfully turns ON and OFF at 1-second intervals, confirming the proper interfacing of a digital output.
