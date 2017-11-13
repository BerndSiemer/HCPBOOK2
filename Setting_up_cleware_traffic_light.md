# Prerequisites
- Cleware Traffic Light
- Raspberry Pi ready to use in the internal network at SAP

1. Download the newest version of clewarecontrol from here https://www.vanheusden.com/clewarecontrol/files/
   on your Raspberry Pi.
2. It needs the library libhidapi-dev. So install the library by entering
 ```sudo apt-get install libhidapi-dev```
3. Go to your clewarecontrol folder and enter ```make install```
4. Connect your cleware traffic light to the Raspberry and test your connection by entering
   ```sudo clewarecontrol -ls```. The output should be look like
   ```
   Cleware library version: 330
   Number of Cleware devices found: 1
   Device: 0, type: Switch1 (8), version: 64, serial number; 901100
   ```
 
