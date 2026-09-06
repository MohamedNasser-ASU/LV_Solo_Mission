# Low Voltage Solo Mission

This repository contains my work for the Low Voltage Individual Technical Mission.

## Repository Structure

```text
LV_Solo_Mission/
│
├── STM32/
│   ├── Milestone_1/
│   │   ├── CubeIDE/
│   │   └── Proteus/
│   │
│   ├── Milestone_2/
│   │   ├── CubeIDE/
│   │   └── Proteus/
│   │
│   └── Milestone_3/
│       ├── Master/
│       ├── Slave/
│       └── Proteus/
│
├── PCB/
│
└── README.md
```

# STM32 Project

## Milestone 1

**MCU:** STM32F103C8T6  
**Goal:** Toggle an LED connected to PC13 every 500 ms.  
**Status:** Complete

**Simulation Video:**  
///////////// link here

### HAL Functions Used

- `HAL_GPIO_TogglePin()` — UM1850, GPIO section, page 228, used it to toggle the state of PC13
- `HAL_Delay()` — UM1850, HAL system driver section, page 50, used it to make a 500ms delay

---

## Milestone 2

**Goal:** Read Engine Temperature and Throttle Position using ADC and display them through UART.  
**Status:** Pending

**Simulation Video:**  
To be added

**HAL Functions Used:**  
To be added

---

## Milestone 3

**Goal:** Implement SPI communication between two STM32F103C8T6 microcontrollers.  
**Status:** Pending

**Simulation Video:**  
to be added

**HAL Functions Used:**  
To be added

---

# PCB Project

**Goal:** Complete the required STM32 PCB design in Altium Designer and generate the Gerber and drill files.  
**Status:** Pending

