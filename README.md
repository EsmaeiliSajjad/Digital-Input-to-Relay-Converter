# Digital-Input-to-Relay-Converter
In this project, we introduced a desined 12 channel a Ditila Input to Relay Converter.
# Table of Centent
1. [Description](#1)
2. [Required Devices](#2)
3. [Circuit Board Design](#3) 
4. [Supported Devices/components](#4)
5. [Upgrades](#5)

<a name="1"></a>
# Description
One may be interested to have a Relay Output Module to be used in a data logger system where a digital input can be inverted into a relay module. A relay outpout module is capable of controlling a device to be on or off. A simple device to be used for this purpose is an air-operator actuator or a soleniod valve. However, a simplest Relay Output modeule can easily cost you at least $400-$800, depending on the number of available channels. The following picture shows one of the cheapest Relay output from National Instrument with 4 channels with electromagnetic relay. This module needs another interface module to connect it to a PC for data logging purposes which can cost you another $600-$800.

![1]<img width="100", (https://user-images.githubusercontent.com/108043716/177024499-856f5c77-24ab-44a6-bb9f-ca4508702136.png)> 

Fig. 1: Example of NI Relay Output Module 

But is there any way to use a low-cost multi-function I/O device like USB-6001 from National Instruments and use its digital output to control a relay directly? The answer is **Yes** but you have to design a circuit board as a converter to get a digital output and control a relay which is a source for power supply. We are not able to directly connect a digital output channel to a relay and control it, because of low-amp low-voltage output of a digital channel. The voltage of a digital output will change beween 0 and 3.3 V with a max current of 10-50 microamp which is not enough to run a relay. So, here we introduce a circuit board which uses a transistor (BD-139) as a driver of a mechanical relay (24 V). Now, we are able to take a digital output module and convert it to a Relay output.

<a name="2"></a>
# Required Devices
In order to go with this project you should have the following items ready:
1. NI-6001 (Universal analog and digital I/O)![1](https://user-images.githubusercontent.com/108043716/177025510-1c7571d7-4a0f-4f32-be89-a403b97a0c09.png) 
2. actuator or soleniod valve
3. Circuit board as a conveter (described in this project)
4. 24 V power supply (other power supply can be use such as 12V or 15V)

<a name="3"></a>
# Circuit Board Design
The followings are a list of items to a circuit board and convert one Ditital Output Channel to a Relay Output Channel.
1. NPN Transister (BD-139)
2. 24V Electromagnetic Relay
3. LED light
4. Resistors (10 Kohm and 2.2. Kohm)

a NPN transistor (e.g., BD-139) is used here where the Base is connected in a series with 2.2 KOhm resistor to a digital output channel of a Digital Output device. There is another resistor (10 KOhm) is connected between the Base and Emitter of the transistor. The coil of the electromagnetic relay is connected to the positive pole (+24 V) and the collector of the transistor (GND). An LED light with a 10KOhm resistor is connected parallel to the relay showing where the channel is ON or OFF.
The following figure demonstrates the desiged circuit board (PCB) for this purpose. The circuit board is designed in **Protel 99SE** software. Here only four channels are ready.
![Picture1](https://user-images.githubusercontent.com/108043716/177025641-1acea2bc-d654-43c1-9f3b-6ef199509e5e.jpg)

![Picture2](https://user-images.githubusercontent.com/108043716/177025663-3593d234-a6d0-4920-8bd1-6165b8377529.jpg)

<a name="3"></a>
# Supported Devices/components
The following components can be connected to the NI-6001 and NI-9221:
1. All PT and DP sensors with 0-10 V or 0-20 mA analog output.
2. All Thermocouple types such as J-type, K_type, ets.
3. All mass flow meters with 0-5 V analog output.
<a name="4"></a>
# Display
The following display can be seen in "Data" tab of the software:
1. Pressure gauges
2. Temperature vertical bar
3. Mass flow meter value
The operator is able to change the limit of the temperature bar or pressure gauges in the software.
<a name="5"></a>
# Calibration
Any sensors such as Pressure transdcuer, Thermocpouple, Mass flow meter or Mass flow Controllers always come with a calibration sheet provided by the manusfacturer. For example for a pressure transdcuer with 0-10V configuration and 0-500 psi pressure variation, a calibration sheet shows the variation of pressure with corresponding voltage. Since most of sensors follow the linear trend between the measured parameter (e.g. pressure) and its analog output (e.g. voltage), a linear regression should be done on pressure versus voltage data.
The operator should enter the slope and intercept of the fitted line in the calibration data of the developed software to configurate the software properly. The following figure shows this option in the software. 

![5](https://user-images.githubusercontent.com/108043716/177008468-624c0bcc-eb8f-42d4-b421-67b793c0fa16.png) 

Fig. 2: calibration configuration setting in the developed data logging software
