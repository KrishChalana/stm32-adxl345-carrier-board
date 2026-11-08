# STM32-ADXL343 Carrier Board

A custom 4-layer-ready KiCad PCB (v2) built around a bare **STM32F411CE** microcontroller and an **ADXL343** 3-axis accelerometer over I2C. It has an onboard 12V-to-3.3V buck converter, USB micro-B, SWD debug header and a UART header. Designed as the hardware companion to my [bare-metal STM32 driver work](https://github.com/KrishChalana/stm32-bare-metal-drivers), moving the same STM32 + accelerometer setup from breadboard to an integrated board.

**Status:** Schematic v2 complete (KiCad 10). Design files only, not yet fabricated.

## Overview

The board takes a nominal **12V input** through a screw terminal, protects it, and steps it down to **3.3V** with an MP2359 buck converter. That rail powers the STM32F411 and the ADXL343. The MCU is the bare STM32F411CEU6 (UFQFPN48) with its own crystal, reset, boot and decoupling circuitry, rather than a Black Pill module. The ADXL343 sits on I2C2 and is fixed in I2C mode in hardware.


## Repo contents

- KiCad schematic (`.kicad_sch`)
- KiCad PCB layout (`.kicad_pcb`)
- `renders/`: schematic, routed PCB and 3D render screenshots

## Screenshots

### Schematic
![Schematic](renders/Schematic.png)

### Routed PCB
![PCB Layout](renders/pcb-top-2d.png)

### 3D Render
![3D Render](renders/pcb-3d-render.png)

## Related

- [STM32 Bare-Metal Drivers](https://github.com/KrishChalana/stm32-bare-metal-drivers): register-level GPIO, UART, timers, ADC
- [ADXL345 I2C/SPI Driver](https://github.com/KrishChalana/ADXL345-Drivers): sensor driver used with this board

## Author

Krish Chalana ([@KrishChalana](https://github.com/KrishChalana))
