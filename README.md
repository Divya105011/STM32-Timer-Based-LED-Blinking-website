# STM32 Timer LED Blinking

A simple demonstration of using STM32 hardware timers to blink an LED without CPU involvement.

## Description
This project shows how to configure STM32's built-in timer peripheral (TIM) to toggle an LED at precise intervals, freeing up the CPU for other tasks.

## Hardware Requirements
- Any STM32 development board (tested with STM32F103 "Blue Pill")
- LED with current-limiting resistor (220Ω recommended)
- ST-Link programmer (or other compatible debugger)

## Software Requirements
- STM32CubeIDE or Keil MDK
- STM32CubeMX (optional for configuration)
- ST-Link Utility (for programming)

## Setup
1. Connect LED to any GPIO pin (default: PA5)
2. Connect ST-Link to SWD pins
3. Build and flash the project

## Usage
1. The LED will blink at 1Hz by default
2. To change blink rate, modify `TIM_Prescaler` and `TIM_Period` in `main.c`
3. For PWM mode, uncomment PWM section in `main.c`

## Code Structure
