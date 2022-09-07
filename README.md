# allBus-HAT-for-Raspberry-Pi
I developed the expansion board to make all buses of the Raspberry Pi which are useful for the operation with Klipper easily accessible, to avoid wiring errors and to keep the construction as compact as possible.

Another requirement was to design the power management so that a proper startup and shutdown is possible, in addition there should be no standby power.  

## This HAT has no dependencies to Klipper, it can also be used for any other application without restrictions.

## **Power Funtions:**  
The HAT is supplied with 5V via screw terminals and can handle 3A current.  
a push button and an LED can be connected to the HAT on the port provided for this purpose.  

![This is an image](https://myoctocat.com/assets/images/base-octocat.svg)

  
The button triggers a Mosfet circuit that supplies the Pi with power, the LED lights up as soon as the Pi starts.  
If the button is pressed again the LED starts blinking for 3 seconds, if pressed again during this time the Pi will initiate a proper shutdown and then reset the Mosfet, the Pi is now completely powerless.  
A long press of the button leads to a hard disconnect of the power supply.  

In addition, two GPIO(22,27) are led out which can be used, for example, to control a relay for the main power supply of a 3D printer (Attention: this would require a downstream circuit that switches the load with a transistor). 

For this Power ON/OFF function only one GPIO(4) is needed and does not limit the availability of the I2C bus because none of these pins is needed.  
Another GPIO(17) is used for the status LED. 

With a jumper you can choose if the Pi should boot automatically after applying the 5V power supply or if it should stay off.  

The basic idea of the ON/OFF circuit comes from this page:  
http://www.mosaic-industries.com/embedded-systems/microcontroller-projects/raspberry-pi/on-off-power-controller


## **Bus Features:**  
-CAN Bus on SPI0 (e.g. to connect the Pi internally with the MCU)   
-UART (e.g. to connect the Pi internally with the MCU)  
-SPI1 (e.g. for input shaper. Note: it still needs to be tested)  
-I2C (e.g. for input shaper)  



## **Installation:**  
1. preparation in boot/config.txt  
  coming soon
2. installation of the shutdown script  
  coming soon
  
## **Note for Klipper/MainsailOS/Fluidd users:**  
do not try to control the power control line (GPIO4) by software yourself ! This is blocked by the dtoverlay=gpio-poweroff, so it is also prevented that unintentionally a hard shutdown is triggered !  
