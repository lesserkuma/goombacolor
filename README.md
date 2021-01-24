# Goomba Color
Originally created by Flubba and Dwedit<br>
Source code imported from https://www.dwedit.org/gba/goombacolor.php

# Modifications
## Batteryless saving
This allows Goomba Color to save its SRAM data on most modern reproduction/bootleg flash cartridges that have an SRAM chip but no battery installed. This works by writing the SRAM data into Flash ROM memory and restoring the data from Flash ROM into SRAM when booting.

The Flash ROM is updated in the following instances:
- Pressing L+R to bring up the main menu (with a prompt)
- Writing a Save State or Quick Save State by pressing R+SELECT
- Deleting a Save State or SRAM
- Exiting

The batteryless Goomba Color SRAM storage area in Flash ROM is dynamically determined and depends on the maximum ROM size of the flash cartridge. In case you need to extract/inject/edit something, you will find the data at ROM address `flash_size - 0x40000` and the length is 0x20000 bytes. Emulators should also be able to extract the SRAM data into a `.sav` file from a re-dumped compilation.

Holding SELECT+UP+B on startup will wipe the save data in case something is not working right.
