# Arduino Dual DC Motor Control with Synchronized LCD Feedback
## ✨ Overview
### This project implements a comprehensive motor control system using an Arduino Uno to drive two DC motors via the L298N Motor Driver. The core functionality involves executing precise motion sequences (forward, backward, alternating turns) while simultaneously providing synchronized visual feedback on an LCD screen, detailing the current motion state.
This project covers key skills in electronics, embedded programming, and interfacing different components (Actuators, Microcontrollers, and Displays).


## 🎯 Task Breakdown
**The project successfully completes two main tasks:**
### Task 1: Motor Movement Programming
Programming two DC motors using the L298N Motor Driver to execute the following precise movements:
 * Forward Motion: Run both motors forward for 30 seconds.
 * Backward Motion: Run both motors backward for 1 minute.
 * Alternating Turns: Alternate between turning right and left for 1 minute.
### Task 2: LCD Synchronization and Interfacing
Interfacing the programmed motors with an LCD screen to display the current movement status in real-time.
 * Synchronization: The text displayed on the LCD must change concurrently with the physical motor movement.
 * Communication Protocol: The system utilizes the I2C communication protocol to efficiently interface the Arduino with the LCD display.


## 🧱 Key Components
| Component | Function | Type |
|---|---|---|
| Arduino UNO | Microcontroller | The brains of the system, running the control logic. |
| L298N Motor Driver | Interface/Actuator | Provides the necessary current and voltage to drive the two DC motors. |
| 2x DC Motors | Actuator | The mechanism performing the required motions. |
| LCD Display (16x2 or 20x4) | Output | Displays the synchronized status of the motor movements. |
| I2C Module (PCF8574) | Communication | Used to simplify wiring between the Arduino and the LCD (essential for Task 2). |


![Design](task1.png)
![Design](task2.png)
![Design](.png)

## 🧠 Software Logic (Pseudocode/Flow)
### The code logic follows a sequential structure controlled by time delays:
 * Initialization: Configure L298N control pins and initialize the I2C LCD.
 * Motion Sequence Loop:
   * Forward (30s): Set motor pins for forward movement. Display "MOVING FORWARD" on LCD. delay(30000).
   * Backward (60s): Set motor pins for reverse movement. Display "MOVING BACKWARD" on LCD. delay(60000).
   * Right/Left Alternate (60s): Loop through setting right turn (one motor forward, one stopped/reverse) then left turn, updating the LCD in each sub-step.
 * Halt: Stop all motors after the sequence is complete.


## 🚀 Potential Applications & Future Scope
### This project is foundational for several applications:
 * Basic Robotics: Forms the core movement and feedback system for wheeled robots.
 * Automated Systems: Applicable in small automated systems requiring timed movement (e.g., conveyor belts, testing rigs).
 * Future Enhancements: Integrating sensors (like encoders or ultrasonic sensors) to move from time-based control to distance-based control and displaying sensor data alongside motion status.
   
