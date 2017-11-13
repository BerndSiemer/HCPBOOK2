#

## [Prerequisites]
- Raspberry Pi 3 
- Micro SD card (at least 8 GB)

## Installing the OS Raspbian on your micro SD card

1. Put the micro SD card into your laptop
2. Download noobs for Raspberry PI from here https://www.raspberrypi.org/downloads/noobs/
3. Follow the installation instructions from here https://www.raspberrypi.org/documentation/installation/noobs.md  
4. Put your SD card into your Raspberry Pi and connect it to the power supply. The installation program of noobs should start
   and follow the instructions.

## Setting up WLan connection to the internal SAP network

1. Figure out the MAC address of your Raspberry Pi (enter ifconfig in a terminal).
2. Request for an exception here https://nac-exception.wdf.sap.corp/request/new and wait until your request is granted.
3. Raspbian doesn't have UI support for WPA2 Enterprise connections. So you have to configure your connection manually in the config files.
   Add the following lines to the file /etc/wpa_supplicant/wpa_supplicant.conf
    ```
    network={
    ssid="SAP-Corporate"  
    scan_ssid=1  
    key_mgmt=WPA-EAP
    eap=PEAP
    identity="YOUR_USER_NAME"
    password="YOUR_PASSWORD"
    phase1="peapver=0"
    phase2="MSCHAPV2"
    }
    ```


4. Now you should have an internet connection but probably you still can't access the internal network of SAP. 
   For that reason you have to change the DNS-Server settings. Enter the command ipconfig /all in a cmd on your laptop. There you should find
   the IPs of SAPs DNS-Servers. Look for the file /etc/resolv.conf on your Raspberry PI and add the following line:
   nameserver <IP from an SAP DNS-Server>
   Make the file immutable by entering
   sudo chatattr +i resolv.conf

