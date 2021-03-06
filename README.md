# Python Smart Meter
Written by James Piggott @ The Universiteit van Twente for the E-Balance project.

Last Updated September 2016, version 1.2

## Introduction
Welcome to my Python Smart Meter page. This program is a small data parser for smart electricity meters. It can read meter packets sent through a P1 to USB connection from any Linux enabled device.
Optionally the choice exists to send the data onwards to another application using a UDP connectionless transfer. A small UDP server program is included for testing. 
To start reading the smart meter packets when the Linux device boots just use the StartUpSmartScript.sh script. Follow the instructions below to register the service.

This software package has been tested on the Raspberry Pi 3 and the BeagleBone Black.

The serial connection can read both DSMR 2.2 and 4.0 messages.

The following smart meters have been tested.
- Kamstrup 162 JxC
- ISKRA MT382
- ISk5
- Landis + Gyr E300
- Landis + Gyr E350



## Installation
1. Copy SmartMeterScript.py to your /root folder.
2. Make sure the P1-to-USB converter cable is plugged into your device.
3. Start the script with typing into the command line 'python SmartMeterScript.py'.
4. Read the UDP datagrams by typing into the command line 'python ./MeterDataReceived.py'.

Optionally you can use the startup script as follows.

1. Place StartUpSmartScript.sh in the init.d folder by using 'cp StartUpSmartScript.s /etc/init.d/'.
2. Use command sequence 'chmod 755 StartUpSmartScript.sh' to assign proper rights.
3. Use 'chmod 755 SmartMeterScript.py' to ensure the script can be used if you have not done so already.
4. Add a service when using dependency-based booting with command 'insserv StartUpSmartScript.sh' or 'update-rc.d StartUpSmartScript.sh defaults'.
5. After reboot use '/etc/init.d/StartUpSmartScript.sh status' to check if the program has started.

## Manifest
- SmartMeterScript.py
- MeterDataReceived.py
- StartUpSmartScript.sh

## Resources

The following pages were very helpful in writing this implementation:

- http://gejanssen.com/howto/Slimme-meter-uitlezen (Dutch)
- http://www.smartmeterdashboard.nl/webshop
