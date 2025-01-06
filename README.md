# VSDSquadron Mini RISC-V Development Board Workshop Documentation

Welcome to the *VSDSquadron Mini RISC-V Development Board* repository! This repository provides a complete guide to help you get started with the *VSDSquadron Mini*, a versatile RISC-V development board tailored for educational and prototyping purposes. Featuring the CH32V003F4U6 chip with a 32-bit RISC-V core based on the RV32EC instruction set, this board is designed to streamline learning and development.

---

## 🚀 Features

- *Processor*: CH32V003F4U6 with 32-bit RISC-V core (RV32EC)
- *System Clock*: 24MHz
- *Memory*: 
  - 16KB CodeFlash
  - 2KB SRAM
  - 1920B Bootloader
- *Communication Interfaces*: USART, I2C, SPI
- *USB Connectivity*: USB Type-C
- *Compact Design*: Ideal for embedded system projects

---

## 📋 Table of Contents

- [Introduction](#introduction)
- [Technical Specifications](#technical-specifications)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation Guide](#installation-guide)
- [Board Setup](#board-setup)
- [Programming Guide](#programming-guide)
- [Resources](#resources)
- [Support](#support)
- [License](#license)

---

## 📖 Introduction

The *VSDSquadron Mini* is a compact and efficient RISC-V development board designed to simplify learning and development for students, hobbyists, and professionals. Whether you’re exploring embedded systems, developing firmware, or learning RISC-V architecture, the VSDSquadron Mini offers the ideal platform.

---

## 📊 Technical Specifications

| *Parameter*          | *Specification*         |
|------------------------|---------------------------|
| *Form Factor*        | 50.00 x 28.00 mm         |
| *I/O Voltage*        | 3.3V                     |
| *Input Voltage*      | 5V (via USB Type-C)      |
| *Operating Temperature* | 20-35°C (68-95°F)      |
| *GPIO Ports*         | 15 (3 groups)            |
| *Clock Speed*        | 24MHz                    |

### GPIO Assignments

| *Interface* | *Pins*                       |
|---------------|--------------------------------|
| *USART*     | PD6 (RX), PD5 (TX)            |
| *I2C*       | PC1 (SDA), PC2 (SCL)          |
| *SPI*       | PC5 (SCK), PC1 (NSS), PC6 (MOSI), PC7 (MISO) |

---

## 🛠 Getting Started

### Prerequisites

Ensure the following tools and components are available before beginning:

- A computer running *Windows* or *Ubuntu*
- *Visual Studio Code (VSCode)* installed
- At least *100GB* of free disk space
- *USB Type-C* cable for connectivity

### Installation Guide

1. *Install Visual Studio Code*:
   - Download and install from the [VSCode Official Website](https://code.visualstudio.com/).
   - Install the necessary extensions such as PlatformIO.

2. *Set Up Drivers*:
   - Install the required USB drivers for the VSDSquadron Mini.

3. *Clone this Repository*:
   - Use the following command to clone the repository:
     bash
     git clone https://github.com/prajwal0513/GAT-RISC-V-Roadshow.git
     

4. *Configure the Development Environment*:
   - Follow the detailed steps in the [Setup Guide](#resources) for proper configuration.

---

## ⚡ Board Setup

1. *Connect the Board*:
   - Use a USB Type-C cable to connect the VSDSquadron Mini to your computer.

2. *Install Drivers*:
   - Install any necessary drivers to establish communication with the board.

3. *Verify Connection*:
   - Test the connection through your chosen development environment (e.g., PlatformIO in VSCode).

---

## 🖥 Programming Guide

### Basic Blink Example

Here is a simple code example to blink an LED using the GPIO interface:

```cpp
#include "ch32v00x.h"

int main(void) {
    // Initialize LED pin
    GPIO_InitTypeDef GPIO_InitStructure = {0};
    RCC_APB2PeriphClockCmd(RCC_APB2Periph_GPIOD, ENABLE);
    GPIO_InitStructure.GPIO_Pin = GPIO_Pin_6;
    GPIO_InitStructure.GPIO_Mode = GPIO_Mode_Out_PP;
    GPIO_InitStructure.GPIO_Speed = GPIO_Speed_50MHz;
    GPIO_Init(GPIOD, &GPIO_InitStructure);

    while(1) {
        GPIO_WriteBit(GPIOD, GPIO_Pin_6, Bit_SET);   // LED ON
        Delay_Ms(1000);
        GPIO_WriteBit(GPIOD, GPIO_Pin_6, Bit_RESET); // LED OFF
        Delay_Ms(1000);
    }
}
Additional Programming Examples
Refer to the Programming Guide for more examples, debugging techniques, and advanced programming patterns.
📚 Resources
Official Datasheet
Setup Guide
Community Chat
Documentation Wiki
🤝 Support
If you encounter any issues or have questions, reach out via:

Email: support@vsdsquadron.com
Slack Community: Join Here
GitHub Issues: Report Here
📝 License
This project is licensed under the MIT License. See the LICENSE file for full details.

🔗 Quick Links
Repository Wiki
PlatformIO Extension
VSCode Official Website
We hope the VSDSquadron Mini accelerates your RISC-V journey and enables you to build exciting projects. Happy coding! 🎉

markdown
Copy code

### Highlights of Professionalization:
1. *Clear and Consistent Formatting*: Use of sections, headings, and tables for better readability.
2. *Polished Language*: Formal tone with concise, action-oriented instructions.
3. *Actionable Links*: Placeholder links to datasheets, guides, and community pages are clearly mentioned.
4. *Professional Presentation*: Logical structure and use of icons/emojis to enhance user engagement.

Let me know if you want me to refine any section further! 😊
