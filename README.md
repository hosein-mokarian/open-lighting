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

<h3>BLE and PCB Antenna</h3>
The BlueNRG-2 is a very low power Bluetooth Low Energy (BLE) single-mode system-on-chip. The BlueNRG-2 includes 256 kB of programming Flash memory, 24 kB of static RAM memory with retention (two 12 kB banks) and SPI, UART, I²C standard communication interface peripherals. It also features multifunction timers, watchdog, RTC and DMA controller. The BlueNRG-2 improves the BlueNRG sleep mode current consumption allowing a further increase in the battery lifetime of the applications.
<br/>
(AN5129) Low cost PCB antenna for 2.4 GHz radio: meander design for STM32WB Series:
<br/>
One of the main reasons to use a PCB (printed circuit board) antenna is the reduced overall cost of the radio module. Well
designed and implemented PCB-printed antennas have a similar performance to the SMD (surface-mounted device) ceramic
equivalence. In general, the footprint for a ceramic SMD antenna is smaller than that for a PCB-printed variant. For a PCB-printed antenna
solution, the increased size of the PCB in relation to space required for the antenna means that the radio module is larger and
the cost of the PCB increased. However the PCB solution is generally cheaper than a SMD ceramic antenna.
<br/>
The PCB antennas, including the electrical parameters of PCB materials used, are layout sensitive. 
<br/>
The electrical parameters and performance of the PCB antenna are also determined by the substrate used, in
particular the thickness of the core and dielectric constants.
<br/>
PCB cross section at antennae area
<br/>
Impedance matching
<br/>
Meander-like PCB antenna can be tuned to the required 50 Ω impedance by matching the impedance circuitry
with the π topology. In Figure 2, the impedance matching area is marked with a dashed line. Under nominal
conditions, this antenna exhibits and impedance very close to the required nominal impedance (50 Ω).
The following changes affect the radiation impedance of the PCB antenna:
• slight board size variation
• metal shielding
• use of plastic cover
• presence of other components in proximity of the antenna


<br/><br/>
<h3>PLC Modem</h3>
Simple and Low-Cost PLC Modem for IoT Applications
<br/>
A vital part of any IoT device is its communication system, since hardware and protocols are required for robust and secure communication between the connected devices and the database. Additionally, an important requirement for IoT communication is to have the lowest cost possible, allowing it to be applied in simple and inexpensive devices, such as smart meters, lights, and simple appliances, such as coffee makers.
One alternative to the wireless technologies in IoT is Power Line Communication (PLC). PLC uses the existing electrical wiring to transmit digital signals between devices attached to the power line. The main advantage of PLC is its low cost, since it does not require the installation of a communication infrastructure. Furthermore, PLC is not subjected to interference due to obstacles, such as walls and furniture, or other communication links, such as radio frequency (Wi-Fi, Bluetooth, ZigBee). These features make PLC, in many cases, the best solution for IoT applications.
Many IoT devices, such as smart meters and presence sensors, do not require high data rate communication. Three design solutions were fundamental to achieve a low cost: (i) full implementation of the modulation and demodulation electronic circuitry with inexpensive components: transistors, resistors, capacitors, and inductors; (ii) implementation of simple communication protocols – not requiring digital processor neither complex filter; and (iii) communication through neutral and ground wires – eliminating the need for complex isolation circuitry.
The proposed PLC modem employs a simple transceiver based on communication through neutral-ground wires. The ground and neutral conductors were chosen because there is no load between them, resulting in lower voltage drop of the coupled signal than in phase-neutral or in phase-ground. Furthermore, the noise levels between neutral-ground are often lower than those between phase-neutral. Another practical advantage of using neutral-ground communication is that the coupling circuit is simpler, since there is no significant voltage between those wires, eliminating the need for complex and expensive isolation circuitry.In the proposed PLC modem, the modulation and demodulation were fully mplemented in hardware with inexpensive discrete components, in contrast to previously discussed solutions that employed FPGA or DSP. The block diagram of the proposed PLC modem is shown in Fig. 1.The modem was connected to an embedded processor unit (a low-cost microcontroller – MCU) through universal asynchronous receiver-transmitter (UART) bus. Although the 
processor unit is not part of the modem proposed, it was used to provide a square wave modulation carrier, and two digital signals to control the gain of the receiver amplifier.
A pulse width modulation (PWM) module, which is embedded in most modern microcontrollers, was employed to generate the modulation carrier. Furthermore, to improve the noise robustness of the proposed modem, a set of simple algorithms to control the gain of the receiver amplifier and the frequency of the modulation carrier were implemented in the 
processor unit. Those algorithms run once during the system setup, not requiring further power processing from the embedded system. 



<br/><br/>
<h3>AC Coupler</h3>
<br/><br/>
<h3>Zero Crossing</h3>
<br/>
As we have already mentioned that there are many ways to design a Zero Crossing Detector. Here, in the below circuit we are using an opto-coupler for the same. By observing the output waveform you can see that the output waveform is getting HIGH only when the input AC wave crosses zero every time.
<br/>


<br/><br/>
<h3>Capacitive Touch Sensor</h3>
<br/>
Capacitive touch sensing is a unique human-machine interface technology that enables the creation ofdifferentiated user interfaces that can bring value to a wide variety of products. With capacitive sensing,mechanical switches and knobs can be replaced with elegant buttons, sliders, and scroll wheels thatintegrate seamlessly into the enclosure of a product to simultaneously improve the aesthetics andfunctionality of the product.These aesthetic and functional improvements come with a different set of challenges for product designers. For example, capacitive touch requires more attention to detail in the PCB design than a simple mechanical switch does. It also requires more firmware to determine the state of the user interface. Factors such as these can make capacitive touch seem like a challenging technology to develop with. However, the reality is that capacitive touch is not extremely challenging—it is just new and different. Like many other technologies, the challenges and risks associated with getting a capacitive touch design concept through development and into production can be reduced by having a proven development flow inplace. If you are a designer who is new to capacitive touch, or an experienced designer that is new to TI's CapTIvate technology for capacitive sensing, this document provides a step-by-step design flow to go from first concept to mass roduction. In addition, this document provides checklists at specific points in the development flow to reduce the risk of unforseen issues late in the development cycle.
<br/>




<br/><br/>
<h3>LED Driver</h3>
This is a very simple led constant current design using only 2 transistors, 2 resistors and an LED. This circuit allows you to use any voltage between 2V and 24V to drive almost any type of LED with power consumption up to 5W. The T2 transistor can be BC547 if you use only usual leds (the 20mA versions) but it is recommended to use BD135, BD137 or BD139 because they have a higher power dissipation.
If the voltage incresease over 2V then a higher current will flow through the collector of T2 and so the base current of T1 will increase too bringing this transistor in the conduction state. But now the collector potential of T1 becomes more and more negative, same thing happens with the base of T2 and so T2 will slowly “closes” thus acting against the initial growth of current. In this way is achieved a stabilizing effect that provides current that is constant through the LED.

Value of R is equal to the LED’s current divided by 0.5

R (Ω) = I (mA)/0.5

The power dissipation of R is

P (W) = I2 (A) x R (Ω)

Example: for a 20mA LED the value of R will be around 39Ω

The current values depending on voltage for a normal red LED:

5V … 15mA
9V … 18mA
12V … 20mA
18V … 24mA
24V … 27 mA

<br/><br/>
<h3>Sensors</h3>
<br/><br/>
<h3>Power Supply</h3>
A transformerless power supply circuit provides a low DC from the mains high voltage AC, without using any form of transformer or inductor. It works by using a high voltage capacitor to drop the mains AC current to the required lower level which may be suitable for the connected electronic circuit or load.

The voltage specification of this capacitor is selected such that it's RMS peak voltage rating is much higher than the peak of the AC mains voltage in order to ensure safe functioning of the capacitor.
This capacitor is applied in series with one of the mains inputs, preferably the phase line of the AC.

When the mains AC enters this capacitor, depending on the value of the capacitor, the reactance of the capacitor comes into action and restricts the mains AC current from exceeding the given level, as specified by the value of the capacitor.

However, although the current is restricted the voltage isn't, therefore if you measure the rectified output of a transformerless power supply you will find the voltage to be equal to the peak value of the mains AC, that's around 310V, and this could be alarming for any new hobbyist.

But since the current may be sufficiently dropped level by the capacitor, this high peak voltage could be easily tackled and stabilized by using a zener diode at the output of the bridge rectifier.

The zener diode wattage must be appropriately selected according to the permissible current level from the capacitor.
<br/><br/>
