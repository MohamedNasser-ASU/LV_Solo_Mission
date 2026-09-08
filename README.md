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

**Goal:** Implement SPI communication between a Master and Slave STM32, send a Case ID from the Master, and return the corresponding Battery Voltage and Wheel Speed as a 24-bit telemetry message.  
**Status:** Complete

**Configuration:**
- Master SPI1 → Full-Duplex Master
- Slave SPI1 → Full-Duplex Slave
- PA5 → SPI1 SCK
- PA6 → SPI1 MISO
- PA7 → SPI1 MOSI
- Master PB0 → Manual Chip Select (CS)
- Slave PA4 → SPI1 NSS Hardware Input
- SPI Data Size: 8 bits
- SPI Baud Rate Prescaler: 64
- Master USART1 TX / PA9 → Virtual Terminal RX
- Master USART1 RX / PA10 → Virtual Terminal TX
- UART Baud Rate: 9600
- Case IDs: `0x1001` to `0x1005`
- Battery Voltage and Wheel Speed encoded into 12 bits
- Two SPI communication cycles used for request/response synchronization

**Simulation Video:**  
https://github.com/user-attachments/assets/4955ffba-1f2b-4fc0-b7fc-75255b65803c

**HAL Functions Used:**  
- `HAL_SPI_TransmitReceive()` — UM1850, SPI Firmware Driver API section 35.2.3, page 449, used for full-duplex SPI communication between the Master and Slave.
- `HAL_UART_Receive()` — UM1850, UART Firmware Driver API section 38.2.4, page 556, used to receive the Case ID entered through the Virtual Terminal.
- `HAL_UART_Transmit()` — UM1850, UART Firmware Driver API section 38.2.4, page 556, used to display the decoded Voltage Level and Wheel Speed on the Virtual Terminal.
- `HAL_GPIO_WritePin()` — UM1850, GPIO Firmware Driver API section 20.2.4, page 227, used by the Master to manually control PB0 as the SPI chip-select line.
- `HAL_Delay()` — UM1850, HAL Control Functions section, page 50, used to provide synchronization time between SPI communication cycles.

---

---

# PCB Project

**Goal:** Complete the required STM32 PCB design in Altium Designer and generate the Gerber and drill files.  
**Status:** Pending

