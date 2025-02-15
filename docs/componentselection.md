# Component Selection

## Objective
The purpose of this pageis to compare, and contrast multiple solutions for each major component in my subsystem design. This includes identifying off-the-shelf and custom electrical or mechanical components, assessing compatibility with project specifications, and articulating rationale for final choices.

---

## Role Description
As part of the project team, my role involves designing and integrating the sensor subsystem. This includes selecting an appropriate distance sensor, ensuring compatibility with the **PIC18F47Q10**, and configuring I²C communication. Additionally, I will assist with the microcontroller's programming, actuation, and communication subsystems.

---

## Electrical Block Diagram

![Smith Individual Block Diagram](https://github.com/user-attachments/assets/205f7cd8-9876-49a6-9849-721d542834f1)

This diagram outlines the key components and subsystems: microcontroller, distance sensor (via I²C), motor driver, and actuators. Each subsystem requires separate research and component selection.

---

## Major Component Selections

### **Microcontroller: PIC18F47Q10**
![image](https://github.com/user-attachments/assets/75a595da-e7bf-443a-b91f-c7affd50d812)  
[Datasheet](https://arizonastateu-my.sharepoint.com/:b:/g/personal/jasmi157_sundevils_asu_edu/EY412CZrEBFCm1RPcBUdK0ABFQC27qYPnXhWjqNXUzvurw?e=bMb4OQ)  

| **Pros**                                                  | **Cons**                                                |
|-----------------------------------------------------------|---------------------------------------------------------|
| Compatible with **MPLab Snap Programmer**                 | Requires **MCC configuration** for all peripherals       |
| Supports **multiple communication protocols** (UART, I²C) | Higher complexity than simpler microcontrollers          |
| Extensively documented with **sample code**               | Surface-mount version may be difficult to solder         |
| Integrated **ADC, PWM, and GPIO**                        | Slightly higher cost than lower-performance alternatives |

---

### **Programmer: MPLab Snap Programmer**
![image](https://github.com/user-attachments/assets/1ad9faf8-0440-4068-9b8d-6f026b02ac68)  
[Datasheet](https://arizonastateu-my.sharepoint.com/:b:/g/personal/jasmi157_sundevils_asu_edu/EQGcT4hhqEpHhpjXQ1mo-LEBesul2oAfO8pAhaCQ58yQCQ?e=vgC0Pv)  

| **Pros**                                                  | **Cons**                                                |
|-----------------------------------------------------------|---------------------------------------------------------|
| Affordable and **official Microchip support**             | May require **firmware updates**                        |
| **Compatible** with multiple PIC microcontrollers         | Limited debugging features                              |
| Easy to integrate with **MPLab X IDE**                    | Not as durable as other higher-end programmers          |

---

### **Distance Sensor Options**

#### **Option 1: VL53L1CXV0FY/1**
![image](https://github.com/user-attachments/assets/22add513-4aa3-4a45-926c-3bb4cddefcbf)  
[Datasheet](https://arizonastateu-my.sharepoint.com/:b:/g/personal/jasmi157_sundevils_asu_edu/EbF6q-VkyolOulMk80JgWMkB3oZ_hcvkSHapQ7gW-guFWQ?e=OiwQhq)  
[Product Link](https://www.digikey.com/en/products/detail/stmicroelectronics/VL53L1CXV0FY-1/8258055)  
**Cost:** $5.77  
**Max Range:** 4 Meters  
**Operating Voltage:** 2.6V - 3.5V  
**Communication:** I²C  
**Mount:** Surface  

| **Pros**                                                 | **Cons**                                                 |
|----------------------------------------------------------|----------------------------------------------------------|
| **Extended range** up to 4 meters                        | Surface-mount **LGA-16** package may require reflow soldering |
| **I²C communication** simplifies integration with MCUs   | Requires **precise alignment** for accurate measurements  |
| Supports **variable timing budgets** for power efficiency| More expensive than **VL53L0X**                          |
| **Multi-target detection** with programmable distance modes | Sensitive to ambient lighting conditions in some environments |

---

#### **Option 2: VL53L0X**
![image](https://github.com/user-attachments/assets/e787c161-59c0-4130-a716-be647bf55d72)  
[Datasheet](https://arizonastateu-my.sharepoint.com/:b:/g/personal/jasmi157_sundevils_asu_edu/EVZtUUkWE9xGhCSLo-Ec1scBudzi0_jGqGujjsDPeXDivA?e=c6nOMb)  
[Product Link](https://estore.st.com/en/products/imaging-and-photonics-solutions/time-of-flight-sensors/vl53l0x.html)  
**Cost:** $2.64  
**Max Range:** 2 Meters  
**Operating Voltage:** 2.8V - 3.3V  
**Communication:** I²C  
**Mount:** Surface  

| **Pros**                                                | **Cons**                                               |
|---------------------------------------------------------|--------------------------------------------------------|
| Compact and **low-cost** sensor for short-range sensing | **Limited range** (up to 1.2 meters)                   |
| **I²C communication** for easy integration              | **LGA package** can be difficult to solder manually     |
| **Low power consumption** ideal for portable devices    | Sensitive to ambient lighting interference              |

---

#### **Option 3: VL53L5CX**
![image](https://github.com/user-attachments/assets/1aa3bbe1-f7fd-4b78-8c1a-2a87a2839143)  
[Datasheet](https://arizonastateu-my.sharepoint.com/:b:/g/personal/jasmi157_sundevils_asu_edu/ETmD_ntduohApG-p0T8vbO0BsWPYG0gU-rsxDNol8xd_AQ?e=xIRxcY)  
[Product Link](https://www.digikey.com/en/products/detail/ams-osram-usa-inc/TMF8801-1B-OLGA12-LF-T-RDP/11477805)  
**Cost:** $5.91  
**Max Range:** 4 Meters  
**Operating Voltage:** 2.8V - 3.3V  
**Communication:** I²C  
**Mount:** Surface  

| **Pros**                                                   | **Cons**                                                  |
|------------------------------------------------------------|-----------------------------------------------------------|
| Measures up to **4 meters** with high accuracy             | Surface-mount **LGA-16** package requires reflow soldering |
| **Multi-zone detection** (up to 64 zones)                  | May require precise alignment for accurate measurements    |
| **Low power consumption** suitable for battery-powered systems | Sensitive to environmental conditions (e.g., ambient light)|
| Compatible with **I²C communication**                      | Complex multi-zone data handling may need additional processing power |
| Supports both **short-range and long-range modes**         | Higher price than simpler sensors                          |
| Reliable integration with **Microchip PIC microcontrollers** using MCC | Documentation may require some technical expertise to fully understand |

---

### **Final Sensor Choice**
Based on the evaluation of range, cost, and ease of integration, I have selected the **VL53L1CXV0FY/1** sensor. It offers extended range capabilities and multi-target detection, making it suitable for our project requirements.

---

## MCC Configuration

---

## Power Budget
The power budget shown below demonstrates that the project is well within the power supply's capacity, allowing for additional components or design modifications if needed.
<img width="668" alt="image" src="https://github.com/user-attachments/assets/5516459e-cac8-411d-bb32-c080b8c06e2c" />

[Link to Spreadsheet](https://docs.google.com/spreadsheets/d/12uf9W3mrbqPYXF1pln1ugqOVY8jhmh9nDuVUHxvh6Tg/edit?usp=sharing)

---


