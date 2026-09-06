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
- `HAL_ADC_Start()` —  UM1850, HAL generic APIs section, page 20, used it to start adc1
- `HAL_ADC_Stop()` —  UM1850, HAL generic APIs section, page 21, used it to stop adc1
- `HAL_ADC_PollForConversion()` —  UM1850, HAL generic APIs section, page 21, used it for waiting for the end of conversions
- `HAL_ADC_GetValue()` —  UM1850, ADC Firmware driver API section 7.2.4, page 66, used it to get ADC regular group conversion result
- `HAL_UART_Transmit()` — UM1850, UART Firmware Driver API section 38.2.4, page 556, used to send the formatted telemetry string through USART1
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

