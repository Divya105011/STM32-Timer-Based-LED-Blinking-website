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
<pre><code>#include "main.h"
void SystemClock_Config(void);
static void MX_GPIO_Init(void);
int main(void)
{
    HAL_Init();
    SystemClock_Config();
    MX_GPIO_Init();

    while (1)
    {
        // LED ON
        HAL_GPIO_WritePin(GPIOA, GPIO_PIN_8, GPIO_PIN_SET);
        HAL_Delay(100);
        // LED OFF
        HAL_GPIO_WritePin(GPIOA, GPIO_PIN_8, GPIO_PIN_RESET);
        HAL_Delay(100);
    }
}
</code></pre>
