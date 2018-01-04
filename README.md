# AccessControl
Electronics & Software to expand current MK Makerspace access control system.

**Expansion for Paxton Net2 Plus Module**

*Requirements* : 1 Analog Input (Current Sensing)

                 2 Digital Input (Start/Activate signal from Paxton Module)(Out of Service - Switch/Header inside board)
                 
                 3 Digital Outputs - (AC Relay)(Short Exit Switch contacts)(RGB LED)
                 
                 12V Supply via POE supplied by Paxton Module                

*Basic Function*

On startup default to AC off. RGB LED set to BLUE

if out of service switch on, AC relay off until board reset and switch off. Set RGB to Brown (or red)


Look for Start pulse, if seen, flash green, AC Relay on.

  If current not seen in 30 seconds power off
  
  if current seen inside 30 seconds latch, RGB LED set to Solid green
  
  When current becomes sufficiently low (IE 0), flash led blue
  
  If current not seen for 30 Seconds turn off AC relay.
  
Return to beginning of loop


**Project**

Build expansion PCB that mounts on back of existing paxton module using existing mounting holes.

*Proposed Components*

ATMEGA328-PU - Unused pins broken out for future use

Allegro ACS723LLCTR-10AB-T Isolated Current Sensor IC 40A SOIC8

Kudom KSIM380D25-L - Optically Isolated Panel Mount SSR - 40-440V AC 25A Load - States usable for resistive, inductive and capacative loads.

WS2812b or Similar addressable RGB LED, OR Standard RGB LED at cost of IO(Unlikely to be a problem)

5V regulator - Linear or DC-DC

Passives & other support circuitry


