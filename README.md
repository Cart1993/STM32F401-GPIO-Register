# [STM32F401]-[GPIO]-[Register] Example.

##  🎯 Overview.

This repository contains a complete, self-contained coding example demonstrating the configuration and usage of the [GPIO] peripheral on the [Nucleo F401RE Board - STM32F401RE].

### 💡 Objective

The primary goal of this exercise is to implement a simple bare-metal gpio input to toggle a LED of Nucleo-F401RE using the user button that the board has. The change of state of the GPIO was build with directly register accesing.

### ⚙️ Hardware & Software Details.
| Component  | Value | Notes |
| ------------- | ------------- | ------------- |
| Microcontroller  | STM32F401RE  | ARM Cortex M4  |
| Development Board  | Nucleo F401RE  | Specific hardware used for testing  |
| Peripheral Used | GPIO Port A and Port C, HSI | Led, User Button and High-Speed Internal Clock |
| Clock Configuration | Internal Clock (16MHz), System Clock (84MHz) |

### Toolchain Used

This project was developed and tested using the following specific toolchain:

IDE: Keil uVision v5.42

Compiler: ArmClang v6.23

Debugger: ST-Link v2

### 🛠️ Implementation Details (The Code)

1. Register Abstraction Level: This project uses Direct Register Access

2. Key Configuration Steps

- Clock Enable: The clock for the GPIO Port A and C was enabled via the RCC AHBxENR register.

- Pin Mode: Pin PA5 was set to Output Mode and pin PC13 was set to input pin by writing to the GPIOx_MODER register

3. Execution Flow

- The main() function enable the clock for GPIO, initializes the peripheral and then enters an infinite loop, where it wait for a change in PC13 applying a software delay to avoid the debouncing and then toggle the state of the LED.

### ➡️ Build and Run Instructions

1. Clone this specific repository:

> git clone git@github.com:cart1993/STM32F401-GPIO-Register.git

2. Open the project file .uvprojx in keil uVision 5.

3. Build the project.

4. Flash the resulting .elf or .hex file to the target board using the STLink V2

### 📄 License

This exercise is part of the main Baremetal : ARM Cortex-M Embedded Coding Exercises project and is released under the MIT License.
