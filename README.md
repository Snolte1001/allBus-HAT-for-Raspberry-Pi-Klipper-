# allBus-HAT-for-Raspberry-Pi

Power Funtions:  
The HAT is supplied with 5V via screw terminals and can handle 3A current.  
a push button and an LED can be connected to the HAT on the port provided for this purpose.  
  
The button triggers a Mosfet circuit that supplies the Pi with power, the LED lights up as soon as the Pi starts.  
If the button is pressed again the LED starts blinking for 3 seconds, if pressed again during this time the Pi will initiate a proper shutdown and then reset the Mosfet, the Pi is now completely powerless.  
A long press of the button leads to a hard disconnect of the power supply.  

In addition, two GPIO are led out which can be used, for example, to control a relay for the main power supply of a 3D printer (Attention: this would require a downstream circuit that switches the load with a transistor). 





Bus Features:  
-CAN bus (on SPI0)  
-SPI1 (e.g. for input shaper)  
-I2C  
-UART  


-Installation-  
coming soon
