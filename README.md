# RetroPie Arcade Power Switch
* The system setup is an 8 Gb  raspberry pi 4 running the latest retropie version as of July 14, 2021.
* This script uses a rocker switch attached to GPIO3 (pin 5) on the raspberry pi 4 to allow switch control over the shutdown process and start up process. Since the raspberry pi needs to be shutdown properly through the retropie menu, this provides an easier user interaction which is ideal for an arcade setup. 
* This script provides 2 main functions
1. **Shutdown:** Shut the Pi down safely when the switch is moved to the "off" position. The Pi now consumes zero power.
2. **Wake:** Turn the Pi back on when the switch is returned to the "on" position.

## Installation
1. Make sure that the rocker switch is initially in the "on" position before turning on the raspberry pi. 
1. Interacting with Raspberry pi
    * Option 1: [Connect to your Raspberry Pi via SSH](https://www.raspberrypi.org/documentation/remote-access/ssh/), 
Note that there are a number of ways to do this. 
    * Option 2: Bring up RetroPie bash terminal by pressing F4 on a keyboard attached to Raspberry pi.  
2. Make sure git is installed by typing this into bash terminal: `sudo apt-get install git`
3. Clone this repo by typing this into the bash terminal: `git clone https://github.com/KozmoKode/RetroPie-Power-Switch.git`
4. To Navigate to the folder containing the install script, type this: `cd RetroPie-Power-Switch/script/`
5. Run the setup script in the bash terminal by typing this: `bash install`
      * The script is now running and listening for the switch to change states
6. Test the shutdown functionality by flipping the switch to the "off" position. The system should shutdown. 
7. Test the wake functionality by flipping the switch to the "on" position. The system should turn on and load properly. 


## Uninstallation

If you need to uninstall the Power Switch script for any reason. 

1. Run the uninstall script in the bash terminal: `cd home/pi/RetroPie-Power-Switch/script/`, and then: `bash uninstall`
2. To remove the directory from the file system: `cd home/pi/`, and then: `rm -rf RetroPie-Power-Switch`
    * You can confirm deletion after you reboot and use `ls` to return a list of all folders in the root directory.

## Hardware

* [Raspberry pi 4 B](https://www.amazon.com/Vilros-Raspberry-Complete-Desktop-Keyboard/dp/B08B1792CL/ref=sr_1_20?dchild=1&keywords=raspberry+pi+4+vilros&qid=1626292183&sr=8-20) 
* [Rocker Switch](https://www.amazon.com/DaierTek-Rocker-Switch-Household-Appliances/dp/B07S1MV462/ref=sr_1_13?crid=RHIY2XUYRN78&dchild=1&keywords=rocker+switch&qid=1626291624&sprefix=rocker+sw%2Caps%2C196&sr=8-13) 
* Some 22 gauge wire and jumper wires soldered to provided connectors to male pins on pi 4. 

Connect the power button to Pin 5 (GPIO 3/SCL) and Pin 14 (GND) as shown in this diagram (note that any ground pin will work):

* GPIO3 (pin 5) is the only pin that will allow both the Shutdown and Wake functionality ([details](https://pinout.xyz/pinout/i2c)).


![Connection Diagram](https://raw.githubusercontent.com/KozmoKode/RetroPie-Power-Switch/master/diagrams/powerbutton.png)
