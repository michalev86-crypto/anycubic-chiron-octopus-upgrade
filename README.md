# Anycubic Chiron to BTT Octopus Pro Upgrade

This repository contains the Klipper configuration and documentation for upgrading an Anycubic Chiron 3D printer with a BigTreeTech (BTT) Octopus Pro motherboard.

## Overview

The Anycubic Chiron is a large-format 3D printer that benefit significantly from a control board upgrade. This project replaces the original Trigorilla 8-bit board with a powerful 32-bit BTT Octopus Pro (STM32H723), enabling smoother motion, quieter operation with TMC2209 drivers, and better expandability.

## Hardware Specifications

- **Printer:** Anycubic Chiron (400x400x450mm)
- **Control Board:** BigTreeTech Octopus Pro v1.1
- **MCU:** STM32H723xx
- **Stepper Drivers:** TMC2209 (UART mode)
- **Firmware:** Klipper

## Wiring and Setup

The upgrade involves significant rewiring. Below are photos of the Octopus Pro board mounted and wired within the Chiron's base.

### Board Installation
![Octopus Pro Mounted](./images/media__1773585503539.jpg)
*The Octopus Pro board mounted in the original electronics compartment.*

### Component Wiring
![Wiring Detail](./images/media__1773585503577.jpg)
*Detail of the motor, heater, and sensor connections.*

### Cooling System
![Fan Setup](./images/media__1773585775122.jpg)
*Custom cooling fan arrangement for the stepper drivers and MCU.*

## Configuration Features

- **Dual Z-Axis:** Utilizes two stepper drivers for the Z-axis with independent endstops/alignment.
- **TMC2209 UART:** Full software control over motor current and microstepping.
- **Sensorless Homing (Optional):** Hardware is capable, though physical endstops are used in this specific configuration for reliability.
- **Optimized Macros:** Custom G-code macros for pausing, resuming, and cancelling prints.

## How to Use

1. Flash the Octopus Pro with the generated Klipper firmware (`klipper.bin`).
2. Upload `printer.cfg` to your Klipper host (e.g., Raspberry Pi running Mainsail/Fluidd).
3. Calibrate your Z-offset and Bed Mesh for the large Chiron build plate.

---
*Created as part of the Anycubic Chiron Octopus Upgrade project.*
