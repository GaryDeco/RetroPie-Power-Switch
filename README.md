# RetroPie Arcade Power Switch
* The system setup is an 8 Gb  raspberry pi 4 running the latest retropie version as of July 14, 2021.
* This script uses a rocker switch attached to gpio pin 3 on the raspberry pi 4 to allow switch control over the shutdown process and start up process. Since the raspberry pi needs to be shutdown properly through the retropie menu, this provides an easier user interaction which is ideal for an arcade setup. 
* This script provides 2 main functions
1. **Shutdown functionality:** Shut the Pi down safely when the switch is moved to the "off" position. The Pi now consumes zero power.
2. **Wake functionality:** Turn the Pi back on when the switch is returned to the "on" position.

## Installation

1. [Connect to your Raspberry Pi via SSH](https://www.raspberrypi.org/documentation/remote-access/ssh/)
* Note that there are a number of ways to do this. You can use a stand alone application such as winSCP or putty. Read the raspberry pi docs to learn how. 
3. Clone this repo: `git clone https://github.com/KozmoKode/RetroPie-Power-Switch.git`
4. Run the setup script: `./powerSwitch/script/install`

## Uninstallation

If you need to uninstall the power button script in order to use GPIO3 for another project or something:

1. Run the uninstall script: `./powerSwitch/script/uninstall`

## Hardware

A full list of what you'll need can be found $$$

Connect the power button to Pin 5 (GPIO 3/SCL) and Pin 14 (GND) as shown in this diagram (note that any ground pin will work):

![Connection Diagram](https://raw.githubusercontent.com/KozmoKode/RetroPie-Power-Switch/master/diagrams/powerbutton.png)

### Is it possible to use another pin other than Pin 5 (GPIO 3/SCL)?




The **wake functionality** requires the SCL pin, Pin 5 (GPIO 3). There's simply no other pin that can "hardware" wake the Pi from a zero-power state. If you don't care about turning the Pi back _on_ using the power button, you could use a different GPIO pin for the **shutdown functionality** and still have a working shutdown button. Then, to turn the Pi back on, you'll just need to disconnect and reconnect power (or use a cord with a physical switch in it) to "wake" the Pi.

Of course, for the GND connection, you can use [any other ground pin you want](https://pinout.xyz/).
