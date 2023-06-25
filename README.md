# CNC Plotter Machine

Using Arduino Uno and a few resources, we have designed a CNC Plotter Machine that has the ability to draw with a pen via G-Code. This machine can draw with dimensions of 4 * 4 cm, and you can design a drawing machine with larger dimensions than these by enlarging the size of the x axis and y axis according to your requirements.

## Table of Contents

- [Features](#features)
- [Getting Started](#getting-started)
- [Components](#components)
- [Usage](#usage)
- [Configuration](#configuration)

## Features

- **Versatile Drawing Capability**: The CNC plotter machine can draw various patterns, shapes, and text based on the provided input.
- **Precise Movement Control**: The machine uses stepper motors to precisely control the positioning of the pen, ensuring accurate drawing.
- **Easy Control Interface**: The Arduino Uno serves as the control unit, allowing you to send commands to the plotter machine.
- **Customizable Pen Holder**: The plotter machine includes a pen holder that can be adjusted to accommodate different pen sizes and types.
- **Compact and Portable**: The use of an Arduino Uno and a CD-ROM drive makes the CNC plotter machine compact and portable.

## Getting Started

To get started with the CNC plotter machine, follow these steps:

1. Assemble the hardware components according to this [video](https://youtu.be/Gm6bH3p6cNQ).
2. Connect the CD-ROM stepper motors to the motor driver, and then connect the motor driver to the Arduino Uno.
3. Download and install [Arduino IDE](https://www.arduino.cc/en/software), [Inkscape 0.91](https://inkscape.org/release/inkscape-0.91/?latest=1) and [Processing](https://processing.org/download).
4. Install the [AFMotor](AFMotor.rar) Library, you can install it manually by downloading the files and install it into Arduino IDE or directly from library manager.
5. Adjust the pen holder to securely hold the pen or marker.
6. Place a sheet of paper or a drawing surface on the flat surface where you want the plotter to draw.
7. Power on the Arduino Uno and initiate communication with the plotter machine.
8. There is ready gcode to test if you want.
8. If you get stucked with any step, you can give a look for the original article [here](https://electricdiylab.com/how-to-make-arduino-mini-cnc-plotter-machine/).
9. Output, [our machine while drawing](https://drive.google.com/file/d/1T6XbWHDwXpsRdm7keNW0uuRVcscyL0hK/view).
![output](output.jpg)

## Components

- 1 * Arduino Uno
- 1 * Motor Driver L293D Shield
- 1 * Mini Servo Motor
- 2 * CD-ROMs

## Usage

Once the CNC plotter machine is set up and connected, you can use various methods to control its movements and create drawings:

- **Direct Commands**: You can send direct commands to the Arduino Uno via a serial terminal or a custom software interface to control the plotter machine's movements.
- **G-Code**: Generate G-code instructions using software such as Inkscape or CAD programs, and then send the G-code commands to the plotter machine for precise drawing.
- **Predefined Patterns**: Utilize preconfigured patterns or designs by storing them in the Arduino's memory or by creating specific functions in the Arduino sketch.

## Configuration

The CNC plotter machine can be customized to suit your specific needs and preferences. Here are a few customization options:

- **Drawing Size**: Adjust the dimensions of the plotter machine to accommodate larger or smaller drawing surfaces.
- **Pen Options**: Experiment with different pens or markers to achieve various line thicknesses and effects.
- **Control Interface**: Develop a custom software interface to control the plotter machine and send commands more conveniently.
- **Additional Features**: Expand the functionality of the plotter machine by adding sensors, an LCD display, or additional actuators.
