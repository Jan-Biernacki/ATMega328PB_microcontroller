# ATMega328PB_microcontroller
Introduction
In our project we have decided to make a distance measuring device which uses ultrasonic waves to determine the distance between the sensor and an obstacle and display them on a screen.

Components 

ATMega328PB microcontroller
7 segment display
HC-SR04 ultrasonic sensor 
Connecting wires

Working principles
We have connected our components as shown below in the figure.


How does the HC-SR04 ultrasonic sensor works
It has 2 transducers which are separated by a specific distance. One of the transducers sends out 8 pulses of 40KHz ultrasonic wave when triggered and the other captures the signal if it echoes back to the sensor. And we can measure the time it takes for the wave to travel to the object and bounce back.
In order for us to deduce the distance between the sensor and the object we use this simple formula.
distance (cm) = time(s)0.034/2

The ultrasonic sensor HC-SR04 has 4 pins 
Vcc
Trigger
Echo
Ground

We have connected the power pins to the power supply on the microcontroller and trigger and echo pins are connected to Port E of our microcontroller. 
Trigger pin has to be configured as an output and the echo pin has to be an input. In order for us to start sending pulses we need to assign a button to start the trigger. So we have assigned the button on the ATmega328PB to be the trigger button.
When the button is pressed more than 10 microseconds, it starts to send out pulses of sound waves and when the pulses are completely sent out our echo pin goes to a high state and when it detects the pulses coming back it goes back to low state. And we measure how long the echo pin has been in a high state to deduce our time.

7 segment display
And we have connected our 7-segment display to PortD and PortB. Which are all configured as an output.
Pins on PortB decides which of the 4 digits we want to display and pins on PortD decides what we are going to display on that specific digit.
