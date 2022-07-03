# Digital-Input-to-Relay-Inverter
In this project, we introduced a desined 12 channel a Ditila Input to Relay Inverter.
# Table of Centent
1. [Description](#1)
2. [Circuit Board Design](#2) 
3. [Supported Devices/components](#3)
4. [Upgrades](#4)

<a name="1"></a>
# Description
One may be interested to have a Relay Output Module to be used in a data logger system where a digital input can be inverted into a relay module. A relay outpout module is capable of controlling a device to be on or off. A simple device to be used for this purpose is an air-operator actuator or a soleniod valve. However, a simplest Relay Output modeule can easily cost you at least $400-$800, depending on the number of available channels. The following is one of the cheapest Relay output from National Instrument. This model needs another interface module to connect it to a PC for data logging purposes. 

<img width="970" alt="Screenshot 2022-07-02 100359" src="https://user-images.githubusercontent.com/108043716/177009139-7ff1c7f0-4c8d-4330-8f01-22d6b7b12a8f.png">

![1](https://user-images.githubusercontent.com/108043716/177024499-856f5c77-24ab-44a6-bb9f-ca4508702136.png) <img width="100">


Fig. 1: Developed data logging software. 
<a name="2"></a>
# Required analog I/O modules
The followings are a list of modules and component you may need to develop and test this software:
1. NI-6001 (universal analog and digital I/O)
2. Cdaq 9171
3. NI-9221 (temperature reading) 
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
