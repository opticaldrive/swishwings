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


# July 20: QWIIC and more eyeballing
I spent a painful amount of time stuff eyeballing the size of a PAJ7620U2 sensor, heres my slack post about it:
<img width="1016" height="710" alt="Screenshot 2025-07-20 at 7 16 06 PM" src="https://github.com/user-attachments/assets/4bd2bea8-303e-49fb-8c55-a4e23bf428ba" />
Yes I'm a dark mode user lol
I measured a  LOT of things and eyeballed the sensor size, its roughly 15x15mm.

Spent a lot of time wiring QWIIC, asked someone on slack for help with footprints and found a built in one
https://www.sparkfun.com/qwiic?<img width="794" height="657" alt="Screenshot 2025-07-20 at 7 17 24 PM" src="https://github.com/user-attachments/assets/c4dd3cc6-d3c7-4030-97a9-db9f6b645f57" />
I kinda reversed the pinout several times, hope I got it right..

Not sure how I want to manufacture this
Definitely via JLCPCB, not sure if I'll use PCBA.
LCSC shipping it might be expensive if i have to order the JST SH connectors on the side. (Connectors on the side, please!)

Hours might seem inflated here but I actually spent this much time looking around for the right stuff 😭

I thought about panelization but idk how to do that yet, but if i can do that and get PCBA that might be the best solution.<img width="565" height="374" alt="Screenshot 2025-07-20 at 7 20 18 PM" src="https://github.com/user-attachments/assets/751f5445-33d3-4ac7-b829-9718ea7b8835" />
Here I wired up all the QWIIC things which was FUN /halfsarc<img width="833" height="482" alt="Screenshot 2025-07-20 at 7 20 41 PM" src="https://github.com/user-attachments/assets/a967a49c-3f87-449d-b18e-0343a8d3e4a5" />
PCB is okay, routing is all done.

Next I need to panelize and get reading for PCB production.
Might make a 3d printed case? idk if the buttons on the xiao might get clicked or not.

Also I was worried about the PAJ7620U2 sensors not working with 3v3 logic and power, so i did a few searches.
I found a amazon page that said they could work, so i just have to hope they do :Sob:
I also found a "confidential" datasheet from pixart(i think this is the manufacturer of the actual core sensor) that Seeed Studio leeked, haven't checked what it said about voltages again though.

Anyways very fun and I really enjoyed doing this today


Hours: 4.0 roughly - around 1 in the moring and 3 in the afternoon

# July 24: JLCPCB panels
Today I spent like an hour on a support chat with JLCPCB to see if my PCB was manufacturable.
I wanted to combine both the mainboard and the wing onto one PCB with mousebites or vscores so i could use PCBA for cheaper, but my luck didn't work out because JLCPCB said it would be charged more.

I also went shopping on aliexpress and I've found the JST SH connectors so I don't need to use PCBA anymore!


Hours: 1

# July 25: Rounding, silkscreen PCB wrapup
Spent a LONG time today in kicad
<img width="563" height="587" alt="Screenshot 2025-07-25 at 4 52 32 PM" src="https://github.com/user-attachments/assets/fdbbaaf8-2b6d-4278-8652-20c235bcbbe1" />
Might not look much different, but I spent a really long time trying to figure out how to round corners.
I also had to reroute the wing because I messed up. The wing should be better now.

Now I'm writing the BOM :)
I should probably make a case but tbh I don't want to.
Or maybe I want to, idk sorry

Hours: 2.5
