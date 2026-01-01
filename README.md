# swishwings
SwishWings WIP :eyes: \
TL;DR Dual Hand Gesture sensor computer/HID interface \

SwishWings is a set of two semimodular gesture sensors. \
There are two modules, one is the core module with the controller/MCU, and one is just a peripheral. \
Both modules have a gesture sensor on top.\
These modules are designed to be positioned next to a keyboard, or in a area where hands are present. \
Actions from the hands will be used to provide HID/keyboard input the computer. \
Could use for WM management, and simple WASD/Arrow gaming. \
The main controller is a xiao rp2040, the modules are connected with a QWIIC cable for I2C. \
The actual gesture sensors are two of the same type connected over I2C. Haven't figured out if it's possible to change the I2C addresses of the sensors so they are on two different buses. \

Originally designed for Highway, but not submitted. \
Needs a case - upgrades in the future are possible. \
OLED/neopixel ports from the controller, and more I2C ports or an expander. \ 
