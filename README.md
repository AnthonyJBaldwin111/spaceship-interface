Arduino Spaceship Interface
Background: Arduino Microcontroller

Arduino is an open source microcontroller platform designed for building interactive electronics and embedded systems. A microcontroller is a small programmable computer that can read inputs from sensors or buttons, process that information using code, and control outputs such as LEDs, motors, or displays.

The Arduino board contains a processor, digital input and output pins, and a programming interface that allows developers to write code using the Arduino IDE, which is based on C and C++. Because of its simplicity and flexibility, Arduino is commonly used for prototyping hardware systems, learning embedded programming, and developing small control systems.

In this project, the Arduino acts as the system controller. It reads a button input and changes the behavior of LEDs based on that input.


Project Overview: Spaceship Interface

The Spaceship Interface project simulates a simple spaceship control panel using LEDs and a push button. The goal of the project is to demonstrate how a microcontroller can respond to user input and control hardware outputs.

The interface has two main system states:

Idle State
When the button is not pressed, one LED remains on to represent the system being ready or in standby mode.

Alert State
When the button is pressed, the system switches into an alert mode where two LEDs blink back and forth. This simulates a warning system or launch sequence similar to what might be seen on a control panel.

This project introduces core concepts in computer science and embedded systems, including input detection, conditional logic, and hardware control.


Hardware Components

Arduino Uno
Breadboard
Push button switch
3 LEDs
Resistors (220Ω for LEDs, 10kΩ for button)
Jumper wires

How the Circuit Works

The circuit is built on a breadboard and connected to the Arduino's digital pins.

Three LEDs are connected to pins 3, 4, and 5 on the Arduino. Each LED is placed in series with a resistor to limit electrical current and prevent damage to the LED.

A push button is connected to pin 2. The button allows the user to send input to the Arduino by either completing or breaking the circuit when pressed.

When the button is not pressed, the input pin reads a LOW signal. When the button is pressed, the input changes and the Arduino detects that change through the digital input pin.

The Arduino then responds by controlling the LEDs connected to the output pins.


How the Code Works

The program begins by creating a variable called switchState to store the current state of the button.

In the setup function, the Arduino defines which pins will act as inputs and outputs. Pins 3, 4, and 5 are set as outputs for the LEDs, and pin 2 is set as an input for the push button.

The main behavior occurs inside the loop function, which runs continuously while the Arduino is powered on.

At the start of each loop, the Arduino reads the button using digitalRead() and stores the result in switchState.

An if else statement is then used to determine how the LEDs should behave.

If the button is not pressed (LOW), the LED connected to pin 3 is turned on while the others remain off. This represents the idle state.

If the button is pressed, the program enters the alert state. The LED on pin 3 turns off and the LEDs on pins 4 and 5 alternate blinking. Short delays are used so the LEDs visibly switch back and forth, creating a flashing warning pattern.

Because the loop function runs continuously, the Arduino constantly checks the button and updates the LED behavior in real time.
