# WSN Reader PCB Design

A custom 2-layer PCB for a Wireless Sensor Network (WSN) reader node, designed in **Proteus 8 Professional**. The board is built around an **STM32F401RE** ARM Cortex-M4 microcontroller and communicates wirelessly via a **LoRa** module, making it suitable for long-range IoT sensor data collection.

---

## Overview

### PCB Layout

![PCB Layout](exports/WSN%20READER%20PCB%20(5).SVG)

### Additional Views

![View](exports/WSN%20READER%20PCB%20(1).SVG)

### Schematic Views

![Schematic](exports/WSN%20READER%20PCB%20(2).SVG)



| Parameter | Value |
|-----------|-------|
| MCU | STM32F401RE (ARM Cortex-M4, 84 MHz) |
| Wireless | LoRa module (J4 – 1×10 header) |
| Sensor | STS121RA04 (Temperature / Humidity) |
| Supply voltage | 3.3 V (regulated via MIC29150-3.3WU LDO) |
| Crystal | 16 MHz ABM3 |
| PCB layers | 2 (Top + Bottom copper) |
| Substrate | FR4, 1.55 mm core |
| Gerber format | X2, metric |
| Design tool | Proteus 8 Professional |
| Generated | July 28, 2025 |

---

## Repository Structure

```
WSN_READER_PCB_DESIGN/
├── proteus/                   # Proteus 8 project files
│   ├── WSN READER PCB.pdsprj  # PCB layout
│   └── WSN reader.pdsprj      # Schematic
├── gerber/                    # Manufacturing files (Gerber X2)
│   ├── WSN READER PCB - CADCAM Top Copper.GBR
│   ├── WSN READER PCB - CADCAM Bottom Copper.GBR
│   ├── WSN READER PCB - CADCAM Top Silk Screen.GBR
│   ├── WSN READER PCB - CADCAM Top Solder Resist.GBR
│   ├── WSN READER PCB - CADCAM Bottom Solder Resist.GBR
│   ├── WSN READER PCB - CADCAM Top SMT Paste.GBR
│   ├── WSN READER PCB - CADCAM Top Assembly.GBR
│   ├── WSN READER PCB - CADCAM Mechanical 1.GBR
│   ├── WSN READER PCB - CADCAM Drill TOP-BOT Plated.GBR
│   ├── WSN READER PCB - CADCAM Netlist.IPC
│   └── WSN READER PCB - CADCAM READ-ME.TXT
├── bom/                       # Bill of Materials
│   ├── WSN READER PCB.csv     # Pick-and-place / component list
│   ├── BOM TSOTLHE SEIPHEPI_ WSN READER PCB.xlsx
│   └── Bill Of Materials WSN READER PCB.pdf
├── exports/
│   └── WSN READER PCB.SVG     # PCB layout SVG export
└── docs/
    └── PCB DESIGN WSN READER.pdf
```

---

## Key Components

| Ref | Part | Description |
|-----|------|-------------|
| U1 | STM32F401RE | 64-pin ARM Cortex-M4 MCU @ 84 MHz |
| U2 | ABM3 16.000 MHz | MCU system clock crystal |
| U3 | MIC29150-3.3WU | 1.5 A LDO voltage regulator, 3.3 V |
| U6 | STS121RA04 | Temperature & humidity sensor (TE Connectivity) |
| J4 | LoRa connector | 1×10 header for LoRa wireless module |
| J3 | CON20 (2×10) | FCI expansion connector |
| J5 | CON16 (2×8) | FCI expansion connector |
| J1 | CON2 (1×2) | Power input connector |
| J2 | CON6 (1×6) | UART / programming header |
| D5 | 1N4747A | 20 V Zener – reverse-voltage protection |

---

## PCB Stackup

| Layer | Material | Thickness |
|-------|----------|-----------|
| Top Solder Resist | LPI resist | 0.01 mm |
| Top Copper | Copper | 0.018 mm |
| Core | FR4 | 1.55 mm |
| Bottom Copper | Copper | 0.018 mm |
| Bottom Solder Resist | LPI resist | 0.01 mm |

Board dimensions: **~56 mm × ~58 mm** (from Gerber bounds).

---

## How to Open

1. Install **Proteus 8 Professional**.
2. Open `proteus/WSN READER PCB.pdsprj` for the PCB layout.
3. Open `proteus/WSN reader.pdsprj` for the schematic.

## How to Fabricate

Send the contents of the `gerber/` folder to your PCB manufacturer. The Gerber files are in **X2 format** (metric, absolute coordinates). See `gerber/WSN READER PCB - CADCAM READ-ME.TXT` for the full layer list and photoplotter setup details.

---

## Author

**Tsotlhe Seiphepi**
