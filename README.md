# Maze-Solving-Robot

This project implements a simple maze solving robot using an ESP32 board, three ultrasonic distance sensors, and two DC motors with an L298N motor driver. The robot can avoid obstacles and navigate around walls using a proportional control strategy.

## Features

- Obstacle detection using front ultrasonic sensor
- Left vs. right decision logic
- Proportional wall-following using side sensors
- Smooth turning and forward movement
- Modular and readable Arduino-style code

## Hardware Used

- ESP32 Dev Board
- 3 × HC-SR04 Ultrasonic Distance Sensors
- 2 × DC Motors
- 1 × L298N Motor Driver Module
- External Power Supply (Battery or Adapter)
- Jumper Wires and Breadboard/Chassis

## Pin Mapping

| Component        | Pin Name     | ESP32 GPIO |
|------------------|--------------|------------|
| Motor 1 IN1      | IN1          | 27         |
| Motor 1 IN2      | IN2          | 26         |
| Motor 1 ENA      | EN           | 14         |
| Motor 2 IN1      | IN3          | 33         |
| Motor 2 IN2      | IN4          | 32         |
| Motor 2 ENB      | EN           | 25         |
| Front Sensor     | TRIG / ECHO  | 19 / 18    |
| Left Sensor      | TRIG / ECHO  | 5 / 4      |
| Right Sensor     | TRIG / ECHO  | 23 / 22    |

## How It Works

- Robot moves forward if no obstacle is detected within 20 cm.
- If an obstacle is detected, it stops and decides to turn based on which side (left or right) has more space.
- While moving forward, the side sensors help maintain balance using a proportional controller.

## Tuning

- `WALL_THRESHOLD` – Adjust for safe wall distance (default: 20 cm)
- `Kp` – Proportional gain for wall-following (default: 0.3)
- `baseSpeedLeft` and `baseSpeedRight` – Adjust for motor balance

## Getting Started

1. Flash the code to your ESP32 using Arduino IDE.
2. Wire the components as per the pin mapping.
3. Power the motors using a separate supply.
4. Place the robot near a wall and observe its behavior.




