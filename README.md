# Bluetooth-Car
Project Overview
This Arduino project demonstrates the control of a robot using Bluetooth communication. The robot is powered by a 6-battery power supply and is driven by four DC motors controlled by an L293D motor driver and an Adafruit Motor Shield. The Bluetooth module HC-05 is used to receive commands from a mobile device, allowing the robot to move in different directions (forward, backward, left, and right) and stop.

Components Used
Arduino Uno: The main microcontroller that runs the program and controls the motors via the motor shield.
L293D Motor Driver IC: Used for controlling the motors.
Adafruit Motor Shield: This shield allows you to easily control multiple motors.
HC-05 Bluetooth Module: Used for receiving Bluetooth commands from a mobile device to control the robot.
6 AA Batteries: Power supply for the robot.
DC Motors (4): Motors that drive the robot’s movement.
Libraries Used
AFMotor Library: This library is provided by Adafruit to control DC motors and stepper motors connected to the Adafruit Motor Shield. It simplifies motor control and abstracts away the low-level operations needed for controlling motors.
Code Explanation
Library and Motor Initialization

AFMotor.h library is used to control the motors connected to the Adafruit Motor Shield.
Four motors are initialized using the AF_DCMotor class, each corresponding to one motor on the motor shield.
Bluetooth Communication

The Bluetooth module (HC-05) communicates with the Arduino using the Serial interface.
The mobile device sends single-character commands (e.g., 'F', 'B', 'L', 'R') to control the robot's movements.
Movement Functions

forward(): Moves the robot forward by setting all motors to move in the forward direction with a speed of 150.
back(): Moves the robot backward by setting all motors to move in the backward direction with a speed of 150.
left(): Rotates the robot left by moving the first two motors forward and the last two motors backward.
right(): Rotates the robot right by moving the first two motors backward and the last two motors forward.
Stop(): Stops the robot by setting the speed of all motors to 0 and releasing them.
Main Program Loop

The loop() function constantly checks for incoming data from the Bluetooth module. When data is received, the command variable stores the incoming character.
Based on the value of the command, the robot moves in the corresponding direction. If the command is not recognized, the robot stops.
How It Works
Bluetooth Commands: The robot can be controlled via Bluetooth using commands sent from a mobile device. The commands are as follows:
'F' – Move forward
'B' – Move backward
'L' – Turn left
'R' – Turn right
Any other command – Stop
Arduino Communication: The Arduino Uno receives these commands through the Bluetooth module and processes them to control the motors, causing the robot to move as directed.
Wiring Diagram
Arduino Uno: Connects to the motor shield and the HC-05 Bluetooth module.
Adafruit Motor Shield: Mounted on the Arduino and connected to the DC motors.
DC Motors: Connected to the motor shield’s motor ports.
Bluetooth Module (HC-05): Connected to the Arduino’s RX and TX pins for communication.
Features
Bluetooth Control: The robot can be remotely controlled using a Bluetooth-enabled mobile device.
Directional Movement: The robot can move forward, backward, left, or right with the simple Bluetooth commands.
Stop Function: The robot can stop at any time when no valid command is received.
Possible Improvements
Obstacle Avoidance: Integrate ultrasonic sensors for obstacle detection and avoidance.
Speed Control: Add the ability to control motor speed via Bluetooth commands.
Wireless Camera: Add a wireless camera to the robot for real-time video streaming.
