# RetroPie Arcade Power Switch
* The system setup is an 8 Gb  raspberry pi 4 running the latest retropie version as of July 14, 2021.
* This script uses a rocker switch attached to GPIO3 (pin 5) on the raspberry pi 4 to allow switch control over the shutdown process and start up process. Since the raspberry pi needs to be shutdown properly through the retropie menu, this provides an easier user interaction which is ideal for an arcade setup. 
* This script provides 2 main functions
1. **Shutdown functionality:** Shut the Pi down safely when the switch is moved to the "off" position. The Pi now consumes zero power.
2. **Wake functionality:** Turn the Pi back on when the switch is returned to the "on" position.

## Installation

1. [Connect to your Raspberry Pi via SSH](https://www.raspberrypi.org/documentation/remote-access/ssh/), 
Note that there are a number of ways to do this. You can use a stand alone application such as winSCP or putty. Read the raspberry pi docs to learn how. 
2. Clone this repo by typing this into the bash terminal: `git clone https://github.com/KozmoKode/RetroPie-Power-Switch.git`
3. Run the setup script in the bash terminal: `./powerSwitch/script/install`

## Uninstallation

If you need to uninstall the power button script in order to use GPIO3 for another project or something:

1. Run the uninstall script in the bash terminal: `./powerSwitch/script/uninstall`

## Hardware

* [Raspberry pi 4 B](https://www.amazon.com/Vilros-Raspberry-Complete-Desktop-Keyboard/dp/B08B1792CL/ref=sr_1_20?dchild=1&keywords=raspberry+pi+4+vilros&qid=1626292183&sr=8-20) 
* [Rocker Switch](https://www.amazon.com/DaierTek-Rocker-Switch-Household-Appliances/dp/B07S1MV462/ref=sr_1_13?crid=RHIY2XUYRN78&dchild=1&keywords=rocker+switch&qid=1626291624&sprefix=rocker+sw%2Caps%2C196&sr=8-13) 
* Some 22 gauge wire and jumper wires soldered to provided connectors to male pins on pi 4. 

Connect the power button to Pin 5 (GPIO 3/SCL) and Pin 14 (GND) as shown in this diagram (note that any ground pin will work):

* GPIO3 (pin 5) is the only pin that will allow both the Shutdown and Wake functionality ([details](https://pinout.xyz/pinout/i2c)).


![Connection Diagram](https://raw.githubusercontent.com/KozmoKode/RetroPie-Power-Switch/master/diagrams/powerbutton.png)
