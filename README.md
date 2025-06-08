# ESPL-ard

arduino-robot/
│
├── firmware/
│   └── transformer_bot.ino     # Arduino sketch
│
├── hardware/
│   └── wiring_diagram.png      # Optional schematic image
│
├── docs/
│   └── design.md               # Design explanations
│
├── README.md
└── LICENSE

# Arduino Robot Project

This project uses an Arduino Uno to control a small robot with:
- Two DC motors for movement  
- One servo motor to rotate the robot when lifted  
- A linear actuator to lift the robot off the ground vertically 
- Sensors: IR(optional), Ultrasonic, Limit Switches

---

## 🧠 Core Behaviors

- Move forward and backward  
- Detect edges(optional) and obstacles  
- Rotate when lifted
- Stop when needed

---

## ⚙️ Hardware Used

| Component          | Description                                |
|-------------------|--------------------------------------------|
| Arduino Uno        | Main controller                            |
| 2x DC Motors       | For robot movement                         |
| L298N Motor Driver | To control the DC motors                   |
| 2x Servo Motors    | Arm rotation                               |
| Linear Actuator    | For lifting mechanism                      |
| IR Sensor          | Edge detection                             |
| Ultrasonic Sensor  | Obstacle detection (front/back)           |
| 2x Limit Switches  | Detect if lift is fully up or down         |

---

## 🔌 Wiring Overview

| Arduino Pin | Connected To            |
|-------------|--------------------------|
| D3 (ENA)    | Motor Driver ENA         |
| D5 (ENB)    | Motor Driver ENB         |
| D6-D9       | Motor control IN1–IN4    |
| D10 (TRIG)  | Ultrasonic TRIG          |
| D11 (ECHO)  | Ultrasonic ECHO          |
| D12         | Servo 1                  |
| D13         | Servo 2                  |
| A0          | IR Sensor                |
| D2          | Limit Switch UP          |
| D4          | Limit Switch DOWN        |

---

## 🧪 How to Use

### 1. Clone the repository
```bash
git clone https://github.com/your-username/arduino-robot.git
cd arduino-robot