# poolnodemcu
PoolNodeMCU uses GPIO output pins of a NodeMCU to control preset steps/speeds as well as heater control. Pololu 12v high-side switches take 3.3V GPIO output signals and switch a 12V input signal that feeds the digital input pins of Century Variable Speed motor to tell it which pre-programmed speed to run (4 steps programmable - STEP1, STEP2, STEP3 and OVERRIDE). Another pair of GPIO pins control a set of relays, one of whichturns the Hayward H250 pool heater off/on. I'm using two 10k thermistors for reading intake water temp and output water temp to know if the pump is on.

While the custom PCB wasn't REALLY necessary, but at $25 for 5 boards, I couldn't stop myself. so much neater/cleaner than I could've ever done with wires and jumpers on a breadboard.

The PCB design is somewhat custom to my component choices, but could pretty easily be used for anyone looking for a more 'industrial' breakout board for the NodeMCU GPIO pins. with a few jumpers in place of the pololu switch in/outs and the ADS1115 VCC -> a0-a3 pins, you could access those GPIO pins directly at the connectors. and i made several 'accessory' spots around the top/right for extra 5v.

There is a jumper up at the top to control whether you want 3.3 or 5V to that VCC connector pin at the top right on the board (D3 and D4 relay outputs)

## Parts List
- [NodeMCU](https://www.amazon.com/dp/B010N1SPRK/ref=cm_sw_em_r_mt_dp_U_UXDaFbYY7MGBK)
- [ADS1115 ADC](https://www.amazon.com/dp/B01DLHKMO2/ref=cm_sw_em_r_mt_dp_U_9WDaFbYQ7GVFV)
- [Pololu Mini-Switches](https://www.pololu.com/product/2808/)
- [Pool Temperature Probe](https://www.amazon.com/dp/B001DO18FS/ref=cm_sw_em_r_mt_dp_U_oWDaFbMWCSZ86) or [10k Thermistors](https://www.amazon.com/dp/B01MZ6Y336/ref=cm_sw_em_r_mt_dp_U_zTDaFbTBXMGS3)
- [10k Resistors](https://www.amazon.com/dp/B0792M83JH/ref=cm_sw_em_r_mt_dp_U_MYDaFbBH0YKBG)
- [Relay](https://www.amazon.com/dp/B00LW15F42/ref=cm_sw_em_r_mt_dp_U_paEaFbSS3NDZ3) (Heater dry contact control)
- 4 pin Terminal Blocks [Male](https://lcsc.com/product-detail/Pluggable-System-Terminal-Block_Ningbo-Kangnex-Elec-WJ2EDGVC-5-08-4P_C8436.html) and [Female](https://lcsc.com/product-detail/Pluggable-System-Terminal-Block_Ningbo-Kangnex-Elec-WJ2EDGK-5-08-4P_C71372.html)
- [Power Switch](https://www.amazon.com/dp/B007QAJUUS/ref=cm_sw_em_r_mt_dp_U_62DaFb38D77P6)
- [Various Header Pins/Sockets](https://www.amazon.com/dp/B0775BRB6B/ref=cm_sw_em_r_mt_dp_U_j0DaFbPHE3QDS)
- 5V Power Supply (for NodeMCU)
- 12V Power Supply (for pump control)
- Hookup Wire (I used HVAC/thermostat wire)
- Enclosure

## External Components
This is how the logic on the pump/motor side works, taken directly from the manual of the Century V-Green 165.
![vgreen165 schematic](https://user-images.githubusercontent.com/1414156/86533740-47182c00-bea1-11ea-9fdd-54c8ffac3baa.png)

![vgreen165 controller](https://user-images.githubusercontent.com/1414156/86533790-8ba3c780-bea1-11ea-81df-e61b920463bf.png)

## Schematic
![poolnodemcu schematic](https://user-images.githubusercontent.com/1414156/86533869-30260980-bea2-11ea-9fc8-db5c8036633a.png)

## PCB Layout
![poolnodemcu pcb](https://user-images.githubusercontent.com/1414156/86533942-ba6e6d80-bea2-11ea-8fc6-e9c50956ed82.png)

