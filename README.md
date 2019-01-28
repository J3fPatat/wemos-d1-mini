# Testcases with 'Wemos D1 mini' and arduino IDE
These are some test cases to show and test the possiblities of the Wemos D1 Mini ESP8266 controller
First of all the installation of the board and 

## Installation on Ubuntu 16.04
### Installation Arduino IDE
Install the Arduino IDE following guidelines on 
https://www.arduino.cc/en/guide/linux

### Install ESP8266 board
1. Open Arduino IDE
2. Add the following link as 'Additional Boards Manager URLs' in 'File > Preferences'
```
http://arduino.esp8266.com/stable/package_esp8266com_index.json
```
3. Go to 'Tools > Boards > Boards Manager', search for ESP8266 and install the board drivers

### Connect your Wemos D1 Mini to Arduino IDE
1. Set-up the right permissions to write to the USB-device.
Add the current user to the group 'dialout'
```
sudo usermod -a -G dialout ${USER}
```
2. Choose the correct board (in my case 'LOLIN(WEMOS) D1 R2 & Mini'
3. Set Tools > Port to /dev/ttyUSB*




## Problem solving
These are the error messages I encountered during the installation:

**Error message** `error: cannot access /dev/ttyUSB0`
+ In case of problems when connecting, add the user to the group 'dialout'
```
sudo usermod -a -G dialout ${USER}
```

**Error message** 
`An error occurred while uploading the sketch` 
`warning: espcomm_sync failed` 
`error: espcomm_open failed`
+ Check if 'Tools > Port' is set to /dev/ttyUSB0 (or other number instead of 0)
