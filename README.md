# OpenC64Cart
OpenC64Cart is an Open Hardware 8 KB Cartridge for the Commodore 64.
 
![Board](https://raw.githubusercontent.com/SukkoPera/OpenC64Cart/master/doc/render-top.png)
 
### Summary
OpenC64Cart is designed to accept a 64 KB (512 Kilobit) (E)EPROM with a 27512-style pinout:
![27512 Pinout by Peter Schepers](https://ist.uwaterloo.ca/~schepers/ROMS/PINOUTS/27512.png)

Such chips can hold up to 8 cartridge images, which can then be selected by jumpers. Other jumpers allow the selection ROM type and of EXROM or GAME mode, achieving compatibility with many different types of ROM, from "simple" games to Ultimax cartridges.
 
The recommended part is Winbond W27C512 (or W27E512, I don't understand what differences they have), which is widely available, cheap and electrically erasable, which avoids the need for a clunky UV-eraser. This is the only part that was thoroughly tested. Other parts, even smaller in size, will probably work, but will require an ad-hoc configuration.
 
Usage is straightforward: just insert the EEPROM in the socket making sure that the notch and all pins are aligned, set the jumpers as desired and plug the cartridge in your C64.
 
### Configuration
**IMPORTANT: ALWAYS TURN YOUR C64 OFF BEFORE MOVING THE CONFIGURATION JUMPERS.**
 
When flashing the contents, make sure that every file is exactly 8192 bytes long and just concatenate them. Then use the following table to set the jumper configuration for your image of choice:

| ROM Image # | A13 | A14 | A15 |
|-------------|-----|-----|-----|
| 1           |  L  |  L  |  L  |
| 2           |  H  |  L  |  L  |
| 3           |  L  |  H  |  L  |
| 4           |  H  |  H  |  L  |
| 5           |  L  |  L  |  H  |
| 6           |  H  |  L  |  H  |
| 7           |  L  |  H  |  H  |
| 8           |  H  |  H  |  H  |
 
You will also need to configure the ROM and EXROM/GAME jumpers for the chosen image, according to the following table:

| Mode        | ROM  | GAME  | EXROM | Notes |
|-------------|------|-------|-------|-------|
| ROML        |  LO  | Open  | Close | Most common setting
| ROMH        |  HI  | Open  | Close | Used for 16 KB cartridges, so does not apply here
| Ultimax     |  HI  | Close | Open  | Originally used for cartridges for the Japanese MAX Machine, will work even if the kernal ROM is damaged |
 
Note that GAME and EXROM are NEVER closed at the same time.
 
### License
OpenC64Cart is Open Hardware.
 
### Thanks
The following links were useful during the development of this project:
- https://www.c64-wiki.com/wiki/Expansion_Port
- http://blog.worldofjani.com/?p=879
- https://ist.uwaterloo.ca/~schepers/roms.html
- http://smisioto.no-ip.org/elettronica/kicad/kicad.htm
