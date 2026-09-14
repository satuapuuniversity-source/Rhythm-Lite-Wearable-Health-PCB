# Rhythm Lite Wearable Health PCB

ESP32-C3-based wearable health monitoring PCB, 21x34mm, 4-layer, designed for low-power wearable/IoT sensor applications. Client: Agatsa Software Pvt Ltd.

## System Overview
Organized into 4 hierarchical sheets: MCU/RF, Power, Sensors, Output - driven by an ESP32-C3FH4.

## Hardware

### Processing & Wireless (MCU/RF)
- **U2 - ESP32-C3FH4** (QFN-32) - 2.4GHz Wi-Fi + Bluetooth LE v5.0
- **AE1, L1, C1, L5** - Johanson 2450AT18B100E chip antenna + pi-matching network (2.7nH series / 1.2pF shunt / 3.3nH series) into LNA_IN
- **Y1** - Abracon 32.768kHz RTC crystal (4pF load, deep-sleep timing)
- **Y2** - NDK 40MHz main system oscillator (±10ppm)
- **TP1** - 6-pin programming/debug test pad

### Power Management & Battery Protection
- **J1, U1, Q1** - 130mAh Li-Po/Li-ion battery interface; DW01A protection IC + FS8205A dual N-MOSFET (overcharge/overdischarge)
- **J2, U5** - 2-pin charge pad + TP4057 (SOT23-6) linear charger IC
- **U4, L4, R10** - TPS62A01 buck regulator, 3.3V rail (3.318V nominal, 453kΩ FB resistor)
- **U3, L3, R8** - TPS61023 boost converter, ~4.96V rail for optical sensors (1.10MΩ FB resistor)
- **D1** - PESD5V0S1BA ESD protection diode

### Peripherals & Sensors
- **MAX30101** - PPG sensor (heart rate / SpO2)
- **VEML6030** - ambient light sensor
- **LIS2DH12** - accelerometer
- I2C bus + power distributed via global labels across sheets

## Repo structure
- KiCad 10.0 project files (schematics across MCU/RF, Power, Sensors, Output sheets, PCB, BOM, netlist)

**Scope:** hardware/PCB design only - 4-layer board optimized for low-power wearable/IoT use, JLCPCB fabrication (ENIG, resin-filled copper-capped via-in-pad).
