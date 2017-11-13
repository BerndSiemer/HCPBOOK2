# Using a Clewareware Traffic Light on a Raspberry Pi
## [Prerequisites]
- Cleware Traffic Light
- Raspberry Pi ready to use

## Setting up clewarecontrol
1. Download the newest version of clewarecontrol from [here](https://www.vanheusden.com/clewarecontrol/files/)
   on your Raspberry Pi.
2. It needs the library libhidapi-dev. So install the library by entering
 ```sudo apt-get install libhidapi-dev```.
3. Go to your clewarecontrol folder and enter ```make install```.
4. Connect your cleware traffic light to the Raspberry and test your connection by entering
   ```sudo clewarecontrol -l```. It lists all connected cleware devices. The output should look like
   ```
   Cleware library version: 330
   Number of Cleware devices found: 1
   Device: 0, type: Switch1 (8), version: 64, serial number; 901100
   ```
   
   Hint: The device will not be recognized without admin permissions.
5. Write down the serial number of your device for later use.
6. You can control the lights by the command ```sudo clewarecontrol -d <serial number of your device> -as x y```.
The parameter x handles the different LEDs. You control the red light with x=0, the yellow light with x=1 and the green light with x=2.
The parameter y determines if you turn off (y=0) or turn on (y=1) the light.
