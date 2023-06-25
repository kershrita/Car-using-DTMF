# DTMF (dual tone multi-frequency) Car Control

The DTMF Car Control Project combines telecommunications technology with a remote-controlled car, allowing you to operate the car's movements from a distance. It utilizes DTMF tones generated by a mobile phone or landline phone to control the car's forward, backward, left, and right movements.

**Illustrative example**: If we send a number 2, the other phone (the receiver) sends this value to the DTMF Module, then the DTMF Module converts it to binary number and sends it to the Arduino Nano and executes the required code of it if we press the number 2 and so on with the rest of the numbers.

## Table of Contents

- [Features](#features)
- [Getting Started](#getting-started)
- [Components](#components)
- [Usage](#usage)
- [Configuration](#configuration)
- [Contributing](#contributing)

## Features

- **Remote Control**: Control the car's movements remotely using DTMF signals sent via telecommunications networks.
- **DTMF Decoding**: Decode the received DTMF signals to interpret the desired car movements.
- **Directional Movements**: Enable forward, backward, left, and right movements for precise control of the car.
- **Real-Time Responsiveness**: Receive and process DTMF signals in real-time, ensuring immediate response from the car.
- **Compatibility**: Works with standard mobile phones and landline phones that can generate DTMF tones.

## Getting Started

To get started with the DTMF Car Control Project, follow these steps:

1. Connect the DTMF decoder module to the Arduino board.
2. Connect the motor driver module to the Arduino board and wire it to the car's motors.
3. Upload the Arduino sketch to the Arduino board.
4. Power on the Arduino board and ensure that the DTMF decoder module is functioning correctly.
5. Place the mobile phone or landline phone near the DTMF decoder module to receive the DTMF signals.
6. Dial the designated phone number and use the phone's keypad to generate DTMF tones for controlling the car.

**[Robot While Movinf](https://drive.google.com/file/d/1MkTyPqT7drrVki1eYvzhlTXANotOzHaV/view?usp=sharing)**.

**Note**: I'm sorry that the project circuit isn't available

## Components

- 1 * Arduino Nano
- 1 * DTMF Module
- 1 * Motor Driver
- 2 * Mobile phone or landline phone capable of generating DTMF tones

## Usage

Once the DTMF Car Control system is set up, you can control the car's movements by following these instructions:

1. Dial the designated phone number connected to the DTMF Car Control system.
2. Use the phone's keypad to generate DTMF tones corresponding to the desired car movements:
- Press "2" to move the car forward.
- Press "4" to turn the car left.
- Press "6" to turn the car right.
- Press "8" to move the car backward.
3. The DTMF decoder module will interpret the received DTMF tones and send corresponding signals to the Arduino.
4. The Arduino will process the signals and control the motor driver module to perform the desired car movements.

## Configuration

The DTMF Car Control Project can be customized to suit your specific requirements. Here are a few customization options:

- **Additional Controls**: Extend the control system to include more advanced features such as speed control, horn activation, or lights control.
- **Remote Communication**: Explore wireless communication options to establish the control link between the phone and the car, such as Bluetooth or Wi-Fi.
- **Integration with Other Systems**: Integrate the DTMF Car Control system with other home automation or IoT systems to enhance functionality and automation capabilities.

## Contributing

Contributions to the DTMF Car Control Project are welcome! If you have any ideas, improvements, or bug fixes, feel free to open an issue or submit a pull request. Your contributions can help enhance the project and make it more accessible and reliable for others.