# DTMF-Controlled Robotic Car

> A telephony-driven edge robotics system that decodes DTMF keypad tones into deterministic motor commands for remote vehicle control.

## Overview

This project implements an end-to-end command pipeline for controlling a robotic car over standard phone networks. Instead of relying on Wi-Fi or Bluetooth, the system uses DTMF tones (from a call keypad) as a low-bandwidth, widely available control channel.

The design focuses on practical engineering concerns:
- Predictable input-to-action mapping for safe actuation
- Minimal-latency command handling on embedded hardware
- Clear separation between signal validation and motion control firmware

Real-world use cases:
- Remote mobility control in low-connectivity environments
- Telephony fallback channel for field robotics prototypes
- Education and demonstrations of signal-to-actuator system design

## Architecture

End-to-end flow:

Phone Keypad Tone -> DTMF Decoder Module -> Arduino Nano Command Interpreter -> Motor Driver -> Wheel Motors

### Architecture Diagram

![DTMF-Controlled Robotic Car Architecture](./assets/Human%20Activity%20Recognition%20System%20Workflow.png)

This diagram visualizes the full command path from keypad tone generation to wheel actuation, with a parallel validation branch to the serial monitor for decoder debugging.

### Components

- Input Layer: A mobile or landline keypad generates DTMF tones during a call.
- Signal Decoding Layer: The DTMF module converts audio tones into a 4-bit digital output.
- Control Logic Layer: Arduino firmware reads the 4-bit state and maps it to movement commands.
- Actuation Layer: Motor driver pins are toggled to drive left/right motor directions.
- Validation Layer: A separate test sketch streams raw decoder bits over serial for debugging and verification.

## Features

- Remote control using standard phone keypad digits
- Deterministic command decoding from digital DTMF outputs
- Directional movement support: forward, backward, left, right, stop
- Dedicated decoder test mode for hardware bring-up and troubleshooting
- Lightweight firmware footprint suitable for low-cost microcontrollers

## Technical Highlights

- System design decision: direct binary-command mapping instead of probabilistic interpretation, reducing ambiguity in actuation.
- Engineering reliability: separate firmware sketches for decoder validation ([DTMF_test/DTMF_test.ino](DTMF_test/DTMF_test.ino)) and drive control ([DTMF_car/DTMF_car.ino](DTMF_car/DTMF_car.ino)).
- Real-time control path: input is processed from GPIO reads to motor output writes within a single loop cycle.
- Field-oriented operation: no dependency on internet access, app ecosystem, or cloud services.
- Extensibility path: command map can be extended to speed, horn, lights, or safety states without redesigning the core pipeline.

## Tech Stack

Hardware:
- Arduino Nano
- DTMF decoder module (4-bit output)
- Motor driver module (dual H-bridge class)
- DC motors and wheeled chassis
- Two phones (caller + receiver path)

Firmware and Tooling:
- Arduino C/C++
- Arduino IDE
- Serial Monitor for decoder diagnostics

## Getting Started

### Prerequisites

- Arduino Nano flashed over USB
- DTMF decoder module wired to Arduino input pins
- Motor driver wired to Arduino output pins and motors

### 1) Clone the Repository

```bash
git clone https://github.com/kershrita/Car-using-DTMF.git
cd Car-using-DTMF
```

### 2) Wire Key Pins (as implemented in firmware)

- Decoder outputs to Arduino inputs:
  - D0 -> A0
  - D1 -> A1
  - D2 -> A2
  - D3 -> A3
- Motor control outputs:
  - M11 -> D3
  - M12 -> D4
  - M21 -> D5
  - M22 -> D6

### 3) Validate Decoder Output

1. Upload [DTMF_test/DTMF_test.ino](DTMF_test/DTMF_test.ino).
2. Open Serial Monitor at 9600 baud.
3. Press keypad digits from the caller phone and verify the 4-bit output changes.

### 4) Run Vehicle Control

1. Upload [DTMF_car/DTMF_car.ino](DTMF_car/DTMF_car.ino).
2. Place the receiver phone near the DTMF module audio input path.
3. Start a call and send keypad digits.

Command mapping used in current firmware:

| Key | Binary | Action |
|-----|--------|--------|
| 2   | 0010   | Forward |
| 4   | 0100   | Right |
| 6   | 0110   | Left |
| 8   | 1000   | Backward |
| 5   | 0101   | Stop |

## Results

- Verified end-to-end control path from telephony tone input to motor actuation.
- Confirmed stable decoder bit reads through serial diagnostics in [DTMF_test/DTMF_test.ino](DTMF_test/DTMF_test.ino).
- Validated directional command execution for forward, backward, left, right, and stop in [DTMF_car/DTMF_car.ino](DTMF_car/DTMF_car.ino).

Current limitations:
- No speed modulation or closed-loop feedback.
- No obstacle sensing or autonomous behavior.
- No full circuit diagram included yet.

## Future Improvements

- Add PWM-based speed control and configurable motion profiles.
- Add fail-safe timeout to auto-stop when no valid command is received.
- Add sensor fusion (ultrasonic/IMU/camera) for semi-autonomous operation.
- Add a complete hardware schematic and pinout diagram for reproducibility.


## License

Released under the [MIT License](LICENSE).