
## 1. Clone the repository
```bash
git clone https://github.com/InnovatiffPL/ESPL-ard.git
cd arduino-robot

## 2. Integrate IDE and install required components:
- Visual Studio Code > PlatformIO extension from the VS Code Extension tab (Because it has native GitHub integration)

Useful Libraries for PlatformIO:
- Servo (Standard Arduino servo control)
- NewPing (More accurate and faster than default examples)

## 3. Remember to push commits only to the right branch of the repository or remove them otherwise
arduino-robot/
│
├── firmware/
│   └── arduino-robot.ino         # Arduino sketch (C++ logic for behavior)
│
├── hardware/
│   ├── wiring_diagram.png        # Optional schematic (placeholder)
│   └── components_list.md        # List of parts used (optional)
│
├── docs/
│   ├── design.md                 # Detailed design explanation
│   └── expansion.md              # Optional: multi-behavior or future add-ons
│
├── README.md                     # Project summary + file map
├── LICENSE                       # MIT or other open source license
└── .gitignore                    # Ignore Arduino build artifacts

### How It Works
- The robot can lift itself, rotate on a fixed wheel, then lower back down
- Limit switches prevent over-motion and make the system safer
- Can be expanded to include obstacle avoidance using ultrasonic or IR sensors

For a deeper look into the logic and wiring, [read the DESIGN.md](./DESIGN.md).

## 1. Project Structure

This robot project is designed for modular movement and safety-driven actions.

## 2. Key Files

- `main.ino` – Arduino source code for movement control (lift, rotate, retract)
- [`DESIGN.md`](./DESIGN.md) – Full breakdown of mechanical + electronic design: including - docs/design.md
- `README.md` – Project summary and instructions

## 3. Combined Behavior Logic
1. Normal Mode: Robot drives forward using wheels
2. If obstacle detected by ultrasonic sensor:
    → Stop
    → Execute lift → rotate → retract sequence
3. Resume driving in new direction

## 4. Additional Components Required
| Component         | Description                            |
| ----------------- | -------------------------------------- |
| Ultrasonic Sensor | e.g., HC-SR04, detects front obstacles |
| IR Sensor         | Reflective edge detection (optional)   |

## 5. Integration Tips
Use flags (e.g. movementComplete) to ensure robot doesn’t resume motion too early

Add moveForward(), moveBackward(), or pathfinding logic after repositioning

You can also add IR edge detection to stop movement near edges or cliffs