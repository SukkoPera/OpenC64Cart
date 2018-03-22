# OpenC64Cart
OpenC64Cart is an Open Hardware Cartridge for the Commodore 64. It only supports 8 KB ROM images. A variant that supports 16 KB ROMs is [available separately](https://github.com/SukkoPera/OpenC64Cart16K).
 
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
OpenC64Cart is Open Hardware. If you make any modifications to the board, please contribute them back.

### Support the Project
Since the project is open you are free to get the PCBs made by your preferred manufacturer, however in case you want to support the development, you can order them from PCBWay through this link:

[![PCB from PCBWay](https://www.pcbway.com/project/img/images/frompcbway.png)](https://www.pcbway.com/project/shareproject/OpenC64Cart_V2__8K_.html)

You get cheap, professionally-made and good quality PCBs, I get some credit that will help with this and [other projects](https://www.pcbway.com/project/member/shareproject/?bmbid=41100). You won't even have to worry about the various PCB options, it's all pre-configured for you!

Also, if you still have to register to that site, [you can use this link](https://www.pcbway.com/setinvite.aspx?inviteid=41100) to get some bonus initial credit (and yield me some more).

Again, if you want to use another manufacturer, feel free to, don't feel obligated :).

### Get Support
If you need help or have questions, you can join [the official Telegram group](https://t.me/joinchat/HUHdWBC9J9JnYIrvTYfZmg).
 
### Thanks
The following links were useful during the development of this project:
- https://www.c64-wiki.com/wiki/Expansion_Port
- http://blog.worldofjani.com/?p=879
- https://ist.uwaterloo.ca/~schepers/roms.html
- http://smisioto.no-ip.org/elettronica/kicad/kicad.htm
