# open-lighting
It's an open source smart lighting.
One of the most important parts of building automation is lighting. Key lights are the main way to control lights, but the classic ones are really anonying.
They have a limited control of lights and are completely manual. So, using smart ones instaed of them are really neccessary. Smart light switch can have more control to users.
The Open Lighting is a kind of smart key which controls lights by diffrent methodes. It has wireless comunication and lights can be turn off or on by mobile phone.
Also they all make a network which communicate on power line. Actually, it is a wired network.
Fig.1 shows the block diagram of the Open Lighting. It consist diffrent parts like: BLE, PLC Modem, Dimmer and power supply. All will be described in detailes in the following.
<br/><br/>
![alt text](https://github.com/hosein-mokarian/open-lighting/blob/main/Fig/me.jpg?raw=true)
<br/><br/>
There are two diffrent ways to communicate other nodes. BLE wireless communication is for conecting to mobile phonees.
Power line communication is used to connect all smart key lights in a building.
Low cost, ultra low power stm32 BLE MCU is used.
PLC communication is provided by a very low cost circuit. It just uses diecrete electronic parts.
Zero crossing circuit is for detecting whether the main power exist or not. It is im[plemented by an AC optocoupler.
AC coupler circuit is a kind of LC series or parallel circuits. It just passes special frequncies. It is based on PLC standards.
Users can trun off or on lights by capacitive touch sensor which is implwmwted on PCB.
Some LEDs indicated the sesors borders.
All circuit is powred by main AC or batteries.
Sensors gather information from the environment and send it to MCU.
