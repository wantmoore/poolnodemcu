# poolnodemcu

This is a work-in-progress...

PoolNodeMCU uses GPIO output pins of a NodeMCU to control preset pump steps (motor speeds) as well as heater control via a dry contact. Pololu 12v high-side switches take 3.3V GPIO output signals from the NodeMCU and switch a +12V signal (provided by the pump). The switched +12V goes to input pins of Century Variable Speed motor to tell it which pre-programmed speed to run (Four programmable steps STEP1, STEP2, STEP3 and OVERRIDE). Another pair of GPIO pins control a set of relays, one of whichturns the Hayward H250 pool heater off/on. I'm using three 10k thermistors for reading intake water temp, output water temp, and ambient temp inside the NodeMCU enclosure.

The custom PCB wasn't REALLY necessary, but at $25 for 5 boards, I couldn't stop myself. The final product is much neater/cleaner than I could've ever done with wires and jumpers on a breadboard/protoboard. The PCB design is somewhat custom to my component choices, but could pretty easily be modified for use by anyone looking for a more 'industrial' breakout board for the NodeMCU GPIO pins. D0 is already available at pins 2 and 4 of P5 and P6. D1 and D2 can be jumpered to P5 and P6 as well by connecting the SCL and/or SDA pins to the "outside" mounting hole for the 10K resistors (R1-R4). To get access to GPIO pins D5-D8, jumper across CTRL and VOUT pins of each Pololu switch (U2/U3/U4/U5) to connect P4 pins 1-4.

In addition to those GPIO pins, there are several accessory loctions for 3V3, 5V and GND around the board. There is a jumper up at the top (J2) to control whether you want 3V3 or 5V to the VCC pin (P2-4) at the top right on the board.

## Parts List
- [NodeMCU](https://www.amazon.com/dp/B010N1SPRK/ref=cm_sw_em_r_mt_dp_U_UXDaFbYY7MGBK)
- [ADS1115 ADC](https://www.amazon.com/dp/B01DLHKMO2/ref=cm_sw_em_r_mt_dp_U_9WDaFbYQ7GVFV)
- [Pololu Mini-Switches](https://www.pololu.com/product/2808/)
- [Pentair Temperature Probe](https://www.amazon.com/dp/B001DO18FS/ref=cm_sw_em_r_mt_dp_U_oWDaFbMWCSZ86) or [NTC Temperature Sensor](https://www.amazon.com/dp/B01MZ6Y336/ref=cm_sw_em_r_mt_dp_U_zTDaFbTBXMGS3)
- [10k Resistors](https://www.amazon.com/dp/B0792M83JH/ref=cm_sw_em_r_mt_dp_U_MYDaFbBH0YKBG)
- [Relay](https://www.amazon.com/dp/B00LW15F42/ref=cm_sw_em_r_mt_dp_U_paEaFbSS3NDZ3) (Heater dry contact control)
- 4 pin Terminal Blocks [Male](https://lcsc.com/product-detail/Pluggable-System-Terminal-Block_Ningbo-Kangnex-Elec-WJ2EDGVC-5-08-4P_C8436.html) and [Female](https://lcsc.com/product-detail/Pluggable-System-Terminal-Block_Ningbo-Kangnex-Elec-WJ2EDGK-5-08-4P_C71372.html)
- [Power Switch](https://www.amazon.com/dp/B007QAJUUS/ref=cm_sw_em_r_mt_dp_U_62DaFb38D77P6)
- [Various Header Pins/Sockets](https://www.amazon.com/dp/B0775BRB6B/ref=cm_sw_em_r_mt_dp_U_j0DaFbPHE3QDS)
- 5V Power Supply (for NodeMCU)
- 12V Power Supply (for pump control)
- Hookup Wire for the outside connections(HVAC/thermostat wire or sprinkler control cable)
- Enclosure

## Installed Project
![poolnodemcu_v1](https://user-images.githubusercontent.com/1414156/124680081-a2ee0a00-de93-11eb-9326-f96653a3f3dd.jpeg)

DIY temperature sensor made from a PVC Tee, adapter and screw-in plug
![IMG_3473](https://user-images.githubusercontent.com/1414156/138919447-d8006176-1d68-4d1c-9218-c87cf54afa85.jpeg)

Pentair sensor
![IMG_3471](https://user-images.githubusercontent.com/1414156/138919477-00dadafb-c118-4bb7-875b-6dd875c09966.jpeg)


## External Components
This is how the logic on the pump/motor side works, taken directly from the manual of the Century V-Green 165.
![vgreen165 schematic](https://user-images.githubusercontent.com/1414156/86533740-47182c00-bea1-11ea-9fdd-54c8ffac3baa.png)

![vgreen165 controller](https://user-images.githubusercontent.com/1414156/86533790-8ba3c780-bea1-11ea-81df-e61b920463bf.png)

## Schematic
![poolnodemcu schematic](https://user-images.githubusercontent.com/1414156/86533869-30260980-bea2-11ea-9fc8-db5c8036633a.png)

## PCB Layout
![poolnodemcu pcb](https://user-images.githubusercontent.com/1414156/86533942-ba6e6d80-bea2-11ea-8fc6-e9c50956ed82.png)

