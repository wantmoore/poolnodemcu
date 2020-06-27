# poolnodemcu
PoolNodeMCU uses GPIO output pins of a NodeMCU to control preset steps/speeds as well as heater control. Pololu 12v high-side switches take 3.3V GPIO output signals and switch a 12V input signal that feeds the digital input pins of Century Variable Speed motor to tell it which pre-programmed speed to run (4 steps programmable - STEP1, STEP2, STEP3 and OVERRIDE). Another pair of GPIO pins control a set of relays, one of whichturns the Hayward H250 pool heater off/on. I'm using two 10k thermistors for reading intake water temp and output water temp to know if the pump is on.

While the custom PCB wasn't REALLY necessary, but at $25 for 5 boards, I couldn't stop myself. so much neater/cleaner than I could've ever done with wires and jumpers on a breadboard.

The PCB design is somewhat custom to my component choices, but could pretty easily be used for anyone looking for a more 'industrial' breakout board for the NodeMCU GPIO pins. with a few jumpers in place of the pololu switch in/outs and the ADS1115 VCC -> a0-a3 pins, you could access those GPIO pins directly at the connectors. and i made several 'accessory' spots around the top/right for extra 5v.

There is a jumper up at the top to control whether you want 3.3 or 5V to that VCC connector pin at the top right on the board (D3 and D4 relay outputs)

## Parts List
- NodeMCU (HiLetsGo)
- ADS1115
- Pololu Mini-Switches
- 10k Resistors
- 4 pin male/female connectors
- Power Switch
- Various Header Pins/Sockets
- 5V Power Supply
- 12V Power Supply
- Enclosure

## Schematic

## PCB Layout/Gerber
