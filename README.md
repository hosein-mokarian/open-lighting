# open-lighting

One of the most important parts of building automation is lighting. It has really been wanted to control lights in easier ways. Classic light switches are the main way to control lights, but they are really annoying. They give a limited control of lights and are completely manual. So, using smart ones instead of them are really necessary. Smart light switches have some interesting features. One of them is to control lights wirelessly through a smart phone. It helps them to control keys without considering where they are. Also, users can set up desired time to turn off or on a light automatically. However, designing smart keys have some challenges. In this project, it is tried to describe and give a solution for all of them. 



###### Design Features

- Support the Bluetooth Low Energy (BLE) connection

- Power Line Communication (PLC)

- Low cost PLC modem circuit

- Capacitive touch sensor

- Chip antenna

- Low power devices

  

###### Featured Applications

- Smart building
- Internet of Things (IOT)
- Lighting
<br/><br/>
###### Block Diagram
![alt text](https://github.com/hosein-mokarian/open-lighting/blob/main/Fig/me.jpg?raw=true)
<br/><br/>
The overall view of designed system is shown in Fig.1.



###### Board Image

3D Image of Board ---> Fig.2

Fig.2 shows the 3d view of designed board on the Altium Designer software. 

![alt text](https://github.com/hosein-mokarian/open-lighting/blob/main/Fig/MOKA_smart_light_switch_ctrl_top.JPG?raw=true)
![alt text](https://github.com/hosein-mokarian/open-lighting/blob/main/Fig/MOKA_smart_light_switch_ac_top.JPG?raw=true)
![alt text](https://github.com/hosein-mokarian/open-lighting/blob/main/Fig/MOKA_smart_light_switch_ctrl_bottom.JPG?raw=true)
![alt text](https://github.com/hosein-mokarian/open-lighting/blob/main/Fig/MOKA_smart_light_switch_ac_bottom.JPG?raw=true)

Fig 2. Board Image



###### Key System Specifications

- Input AC power: 220V
- Coin cell battery: 3.3V
- BLE wireless communication
- Wired communication on power line



###### Introduction

This repository provides an open source smart lighting project. The Open Lighting is actually a kind of smart key which controls lights by different methods:

1. a wireless communication
   - It allows users to turn lights off or on by a smart mobile phone through the Bluetooth or the Internet connection.
2. a wired communication
   - It is a network which allows light switches to communicate each other on the main AC power line.

Fig.1 shows the block diagram of the Open Lighting. It consists different parts like:

- Bluetooth Low Energy (BLE)

- Power Line Communication (PLC) Modem

- Dimmer

- Capacitive touch Sensor

- LED Driver

- Sensors

- Power supply

All will be described in details in the following.



###### System Description

In the following, the overall operation of device will be described. Users controls keys through two ways: BLE commands and capacitive touch sensors. Although capacitive touch sensor has a limited operation, most amazing controls can be accessible by a phone, an mobile app and the Bluetooth. The BLE MCU is responsible to handle received user actions. Every smart key connected to a light. If a received command  is for the connected light, MCU turns it on or off directly  through the AC coupler and if the commands are for others lights, it will be sent it through on PLC. Some LEDs are placed around the capacitive touch sensor. They are controlled by MCU and just show some reactions of device to user commands. Zero crossing block helps MCU to detect if the main AC is available or not. It is actually needed to do some operation properly such as to inform user when the power is cut off. A battery is used to supply the MCU whenever the main AC is not accessible. In that situation, all parts  go into low power mode. It helps user to have communication with the device even if there is not any main AC. Sensors get information of the environment and send it to the MCU. They are really helpful when a custom light controlling based on environmental status is needed.



###### Block Diagram

A vital part of any IoT device is its communication system. There are two main ways to communicate with other nodes. The BLE wireless communication is for connecting to mobile phones and power line communication is used to connect all smart light switches in a building together through a wired network. For both methods, low cost and low power devices are used.

###### BLE:

The main part of BLE is BlueNRG-2 whisch is a wireless MCU series of ST Microelectronic. The BlueNRG-2 is a very low power Bluetooth Low Energy (BLE) single-mode system-on-chip. The BlueNRG-2 includes 256 kB of programming Flash memory, 24 kB of static RAM memory with retention (two 12 kB banks) and SPI, UART, I²C standard communication interface peripherals. It also features multifunction timers, watchdog, RTC and DMA controller. The BlueNRG-2 improves the BlueNRG sleep mode current consumption allowing a further increase in the battery lifetime of the applications.



###### PLC:

An important requirement for IoT communication is to have the lowest cost possible. One alternative to the wireless technologies in IoT is Power Line Communication (PLC). PLC uses the existing electrical wiring to transmit digital signals between devices attached to the power line. The main advantage of PLC is its low cost, since it does not require the installation of a communication infrastructure. Furthermore, PLC is not subjected to interference due to obstacles, such as walls and furniture, or other communication links, such as radio frequency (Wi-Fi, Bluetooth, ZigBee). So, these features make PLC a good candidate. PLC communication is provided by a very low cost circuit. It just uses discrete electronic parts like: transistors, resistors, capacitors, and inductors. 

Fig.3 ---> PLC modem block diagram.

The block diagram of PLC modem is shown in Fig. 3. PLC has a very simple protocol. So, it does not need to any digital signal processors (DSPs). Data transmission can be done by a simple MCU which has a UART peripheral. The MCU is used to provide a square wave modulation carrier, and two digital signals to control the gain of the receiver amplifier. A pulse width modulation (PWM) module is employed to generate the modulation carrier. Furthermore, to improve the noise robustness of the modem, a set of simple algorithms to control the gain of the receiver amplifier and the frequency of the modulation carrier are implemented in the MCU. Those algorithms run once during the system setup.



###### AC coupler:

An AC coupler circuit is a kind of LC series or parallel circuits. AC couplers commonly used in electronic circuits to block DC components while allowing AC signals to pass through. It just passes special frequencies. Allowing frequencies are based on PLC standards.



###### Zero crossing:

Zero crossing circuit is for detecting whether the main power exist or not. It is implemented by an AC optocoupler. When the AC power does not exist, a battery is used to supply the MCU. In that situation, all parts go to sleep mode and the MCU has a connection to a smart phone to notify users. The battery is Zinc which can operates for 2 years. Also, there are a lid to change it whenever it is needed.



###### Capacitive touch sensor:

Users can turn off or on lights by capacitive touch sensors which are implemented on PCB. Capacitive touch sensors have some parasitic capacitance value. When someone touches their surface, the capacitance value will be changed. A capacitive touch IC is used to detect if sensor is pressed or not. MCUs can find that like an input interrupt. 

Also some LEDs are used around the the capacitive touch sensors to indicated the sensors borders. They are also used to show a reaction to user's event. 



###### Power Supply:

The main AC is the main way to supply the board. Only special note is the MCU can operate through the AC main power or a battery. For supplying MCU through the main AC, a transformer less power supply is used. The transformer power supply is suitable for application who does not require high current. Also, they are low cost and get lower space on PCB.



###### Sensors:

Sensors gather information from the environment and send it to MCU. They are vital when user wants to control lights based on environmental information. Ambient light sensor(ALS) and temp sensor are used. These two sensors have important effect in a IOT systems. ALS is the best way to control brightness of a light. It helps to control power dissipation of a lamp which is really import factor in a smart building.



###### System Design Theory

bla bla bla



###### Simulation

Most part of designed circuits are simulated in LTSpice software. It is a free software to simulate electronic circuits. Spice model of part numbers can be used to have very accurate simulation. Here, some simulations are documented.



**Schematics**



**Bill of Materials**



**PCB Layout**



**Altium Project**



**Layout Guidelines**



**Test Setup**



**Test Data**



**References**



