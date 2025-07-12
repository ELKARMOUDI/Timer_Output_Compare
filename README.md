# STM32F411 Discovery Timer Output Compare

![STM32F411](https://img.shields.io/badge/STM32F411-Discovery-blue)
![TIM4](https://img.shields.io/badge/TIM4-Output_Compare-green)
![A3543CC7-6F78-41CA-A065-83636B6BBFD4](https://github.com/user-attachments/assets/7f0ef7fc-494a-42e6-b13e-818032b00a0f)


Generate precise square waves using TIM4's output compare mode on STM32F411 Discovery board.

## Features
- **4 Independent Outputs** on PD12-PD15
- **Variable Frequencies**:
  - CH1 (PD12): 10Hz
  - CH2 (PD13): 4Hz
  - CH3 (PD14): 2.66Hz
  - CH4 (PD15): 2Hz
- **HSE Bypass** for accurate timing
- **HAL Implementation** with toggle mode

## Hardware Configuration
| Component | Specification | Discovery Board Ref |
|-----------|---------------|---------------------|
| MCU       | STM32F411VET6 | MB1279 User Manual |
| TIM4 Pins | PD12-PD15     | CN5 connector |
| Clock     | 8MHz HSE      | ST-Link provided |

## Technical Details
### Clock Tree (RM0383 §6.3.3)
```c
HSE (8MHz) → PLL → 96MHz SYSCLK
PLLM = 4, PLLN = 192, PLLP = 4
APB1 Prescaler = 4 → TIM4 Clock = 96MHz
