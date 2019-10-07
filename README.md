# SenShoot
*This project is sponsored by [Appiko](https://appiko.org).*
### Objective
To trigger a smartphone camera using a microcontroller.
### Introduction
This project is all about making a small circuit that can be controlled by a microcontroller to trigger a smartphone camera. Few sensors (motion sensor, LDR, etc.) can be interfaced to microcontroller to make it more usable and to make it more interesting. This is just a proof os concept and no practical application will be discussed here. Later, (probably) some application of this will be linked here...
### Working
All smartphones with 3.5mm headphone jack have a feature in the camera settings to take pictures by pressing the volume rocker or Play/Pause button. This works only when the camera app is open and active. But what to do when the phone goes to sleep mode? Well, there's one more feature by which you can wake up the phone and shoot pictures! That's by double-pressing the volume down button (If not working, this function should be selected in the camera settings).

![Settings](https://github.com/sudhi345/SenShoot/blob/master/Images/Camera_settings.jpg)

Below is the image of the schematic where a suitable solder jumper should be shorted (volume down is recommended as waking up the phone and shooting both can be done). AUX cable can be used to connect the phone and this circuit (or just *hack a jack* from an old headphone). No extra power is required by the circuit (Make sure ground connections are proper i.e. Microcontroller ground and phone's ground are shorted to circuit's gound).  
##### Detecting the headphone
As per the standards, a 1.2k ohm resistance between mic and ground pin tells the phone that a headphone is connected (R5&R4).
##### Volume Up button
The volume up signal is asserted by changing the resistance between mic and ground pin to 250 ohms (210 - 290 ohm). Since there is 1.2k ohm, we need to add 330 ohms (R2) resistor in parallel to get the value in the range mentioned.
##### Volume Down button
The volume down signal is asserted by changing the resistance between mic and ground pin to 500 ohms (360 - 680 ohm). Since there is 1.2k ohm, we need to add a 1k ohm (R3) resistor in parallel to get the value in the range mentioned.
##### Play/Pause button
The Play/Pause signal is asserted by shorting the mic and ground pin (70 ohms or less). We can directly short the pins using MOSFET and no external resistor is needed.

The MOSFET SI2302 is chosen in this example because of its Vgs(th) which is compatible with TTL logic levels. Any suitable MOSFET can be chosen according to the need.
![Schematic](https://github.com/sudhi345/SenShoot/blob/master/Images/Schematic.png)
