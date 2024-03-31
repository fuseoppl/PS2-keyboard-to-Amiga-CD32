# PS2 keyboard to Amiga CD32

PS2 to Amiga keyboard translator tested on:
- Amiga CD32
- PS2 keyboard, Brand: Perixx, Model No.:PERIBOARD-409, Part No.:TK525P
- DFRobot Beetle Board compatible with Arduino Leonardo

Keys info:
- Left GUI (Windows key) = Left Amiga
- Menu key = Right Amiga
- ctrl + alt + home = reset keyboard
- ctrl + alt + delete = hard reset Amiga

To do:
- add Amiga "soft reset".
- add ERROR code after resync (except resync after start) and send last known key code.

The project used a modified library: https://github.com/techpaul/PS2KeyAdvanced

PS2KeyAdvanced library is modified, so do not use the original one!
Keep the library files directly in the sketch directory.

You need two 4k7 resistors
and two diodes with a very low voltage drop, maximum 0.3V (eg.: BAS85-GS08).
CapsLock LED:
Unsolder the LED on the Beetle, cut off the CapsLock LED from the keyboard board and connect it to the Beetle LED pads.

Beetle Board <-> Amiga, PS2 keyboard
- '+' <- Pin 4 (Amiga 6-Pin Mini-DIN) & PS2 keyboard Vcc
- '-' <-> Pin 3 (Amiga 3-Pin Mini-DIN) & PS2 keyboard gnd
- D11 <-> PS2 keyboard data line
- SCL <-> PS2 keyboard clock line
- SDA & R_2 4k7 pullup to vcc & anode schottky D_2 <-> Pin 1 (Amiga 6-Pin Mini-DIN) keyboard data line
- D10 & cathode schottky D_1 & R_1 4k7 pullup to vcc
- D9 & cathode schottky D_2
- RX & anode schottky D_1 <-> Pin 5 (Amiga 6-Pin Mini-DIN) keyboard clock line
