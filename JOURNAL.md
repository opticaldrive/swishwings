---
title: "SwishWings"
author: "random user (U05QJ4CF5QT)"
description: "Two gesture sensing 'wings' on the side of my keyboard as additional HID inputs controlled by swishing your hands around."
created_at: "2025-07-19"
---

# July 19: Init, Xiao,  and eyeballing
Made a new kicad project.
Put a xiao rp2040 on the schematic
The idea is that there will be two "wings", right and left, connected by a STEMMA QT cable.
Right or left wing has the xiao and the right one is just the gesture.
We'll be using a  PAJ7620U2, or specifically 2x of these.
Eyeballing the results on aliexpress show that it has 1x5 2.54mm header rows, 4 are for power, gnd, SDA, and SCL.  Not sure what the 5th is for.
One thing I was worried about was I2C addresses, since I'm using 2x of one type of sensor which probably uses the same I2C address.
I looked stuff up on the datasheets of the RP2040 and Xiao RP2040. The Xiao RP2040 has 1 labeled I2C bus. The RP2040 seems to have two I2C buses that can be assigned to different GPIO.
I found two GPIO: GPIO28 and GPIO29 to use for the second I2C bus on the Xiao.

I have yet to eyeball the size of the PAJ7620U2 from Aliexpress

Also need to figure out how to split the PCB into two - one for the left wing and one for the right

Looking for a STEMMA QT footprint on JLCPCB, haven't found one.


<img width="769" height="849" alt="Screenshot 2025-07-19 at 5 14 40 PM" src="https://github.com/user-attachments/assets/810b43bc-b3a6-4ecb-8d69-fb7f9a4f7198" />

Hours: 2.5 roughly, much more spent at night just thinking.
