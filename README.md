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
https://github.com/user-attachments/assets/bc5a88b9-e137-413c-80d8-96b1d135919c

### HAL Functions Used

- `HAL_GPIO_TogglePin()` — UM1850, GPIO section, page 228, used it to toggle the state of PC13
- `HAL_Delay()` — UM1850, HAL system driver section, page 50, used it to make a 500ms delay

---

## Milestone 2

**Goal:** Read Engine Temperature and Throttle Position using ADC and display them through UART.  
**Status:** Complete

**Configuration:**
- PA0 / ADC Channel 0 → Engine Temperature
- PA1 / ADC Channel 1 → Throttle Position
- USART1 TX / PA9 → Virtual Terminal RX
- UART Baud Rate: 9600
- Continuous Conversion Mode: Disabled
- DMA: Disabled

**Simulation Video:**  
https://github.com/user-attachments/assets/a5b607df-14f3-4ca9-a293-1a460f671be8

**HAL Functions Used:**  
- `HAL_ADC_ConfigChannel()` — UM1850, ADC Firmware Driver API section 7.2.5, page 68, used to select and configure each ADC channel before conversion.
- `HAL_ADC_Start()` — UM1850, HAL generic APIs section, page 20, used to start ADC1.
- `HAL_ADC_Stop()` — UM1850, HAL generic APIs section, page 21, used to stop ADC1.
- `HAL_ADC_PollForConversion()` — UM1850, HAL generic APIs section, page 21, used to wait for the ADC conversion to finish.
- `HAL_ADC_GetValue()` — UM1850, ADC Firmware Driver API section 7.2.4, page 66, used to retrieve the ADC regular conversion result.
- `HAL_UART_Transmit()` — UM1850, UART Firmware Driver API section 38.2.4, page 556, used to transmit the formatted telemetry values through USART1.
- `HAL_Delay()` — UM1850, HAL Control Functions section, page 50, used to delay 500 ms between telemetry updates.

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

