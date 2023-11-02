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

<br/><br/>
<h3>PLC Modem</h3>
<br/><br/>
<h3>AC Coupler</h3>
<br/><br/>
<h3>Zero Crossing</h3>
<br/><br/>
<h3>Capacitive Touch Sensor</h3>
<br/><br/>
<h3>LEDs</h3>
<br/><br/>
<h3>Sensors</h3>
<br/><br/>
<h3>Power Suooly</h3>
<br/><br/>
