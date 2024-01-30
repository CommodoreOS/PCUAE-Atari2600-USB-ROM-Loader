How to run Atari 2600, 7800 ROM Games from USB Drive on the Atari2600 Plus
===================================================================

You will need the `Atari2600 Plus and PC` connected via its `UART` on its `main board` using a `USB Serial CP2102`.
and type in a `few commands into Putty`, into its `Linux Shell` to run a script that copies the `modified dmenu.bin file` over to the firmware.

# You will need:

A USB Serial CP21012 Module, you can find them on eBay.

A Mini USB OTGUSB Cable(Sony EC310 Micro USB OTG Cable works).

A screw driver to open the Atari2600 Plus, there is no other way doing this, it does not work via the USB-C connector, I did buy one and it works on my mobile phone(Samsung Galaxy A22) but does not power the Atari2600 Plus.

Putty - A TTY shell for Linux/Windows so you can communicate with the Atari2600+, there is a Windows version, I use it.

Now connect everything - Connect the wire from the `Serial USB CP2102` to the `Atari2600+ UART connector`, `RX to TX` and `TX to RX` and `GND to GND(Ground)` to the `USB Serial CP2102 pins`.

Picture of the Atari2600 Plus Main Board and it UART Debug connector
![MAIN_BOARD_UART](https://i.ibb.co/T8GNsGz/Atari2600-PCB1.png)

Then run Putty and goto Serial Line and pick the right com port that the CP2102 is connected on your PC, look in Device Manager to see what its on: COM1/2/3x, then set: 115200, 8, 8, 1 None, None.

Save its setting in Putty so you do not need to do it again.

Once you see the Atari2600 Plus Linux Shell in Putty then type its user and password thats below:

You should see RK3128:

Buildroot User and Password
============================
User: root 
Password: deeplay
============================

You will need to copy the modified dmenu.bin file over to /oem/vendor/bin folder and replace the dmenu.bin in there for this it work.

Install everything in this exe file to the root of a USB Drive, via its installer or use Winrar and rename it from .exe to rar, make sure the USB is on MBR and formated in FAT32.

Uses the script on the USB drive to copy the dmenu.bin file to the firmware, its called `(Add)-New-dmenu.bin-mod-file.sh` so type:

Press enter after each line

`cd /media/usb0`

`ls` 

Do you see the USB Drive content..?
If so then type the next line and it should run the script to add the modified dmenu.bin on to the firmware:

`sh ./(Add)-New-dmenu.bin-mod-file.sh`

and wait for it to finish, will not take long.

It should now reboot and it should run the ROM in the `Run_From_USB` folder on the USB Drive instead of the cartridge.

It should be done now, make sure you back up the `dmenu-org.bin` file on the root USB Drive so you do not lose it so you can restore it if it gets deleted by actident.

To remove it and restore it back to how it was run the script called `(Remove)-New-dmenu.bin-mod-file.sh` run it the same way as above, so type:

`cd /media/usb0`

`ls`

Do you see the USB Drive content..?
If so then type the next line:

`sh ./(Remove)-New-dmenu.bin-mod-file.sh`

It should now reboot and it should run the game from the cartridge again and has remove the modified dmenu.bin file.

Inside the USB Drive, on its root you should see a file that says `cartdump-enabled=no` change it to `yes` to enable the dumper to load from cartridge or it will load the cartridge if the USB Drive is not pluged in it.	

If it does not find a USB drive then it will load the Dumper instead and load the cartridge thats in the slot.
At the moment the 4 switches on the Atari2600+ do not work, I need to find a way of adding them, they are controlled by the dmenu.bin file and this is bypassing it at the moment so is only loading Retroarch and its cores.
It uses flag files to make it do things, I can not add a menu to the Atari2600+ because its use KSM/DMS for its display so does not use fb0 Framebuffer like the RGL machines so will not work with yaft but maybe later it will be possable.

It does backup of the dmenu.bin file so you can put it back to how it was before, it includes two scripts one for adding the mod and one for removing it.

Enable/Disable Dumper/Core
===========================

Cartridge Dumper Enable = cartdump-enabled=yes

Cartridge Dumper Disable =  cartdump-enabled=no

If you enable the Dumper then it disables the USB Rom Loader.

When you enable the dumper and load a game from a cartridge it will make a backup of it and sent it to the USB Drive too.

You can updated the dmenu.bin file too from the USB Drive using the flag file: dmenu-update-enabled=yes it copies it from the root of the usb drive dmenu.bin.


It now loads the rom file it sees in the `PCUAE USB Drive Letter(H:)\PCUAE-Atari-Games\Run_From_USB` folder so they have to be named correctly so:

Load Rom File from Run_From_USB folder
======================================

Atari VCS 2600 = Atari2600-1.bin

Atari 7800     = Atari7800-1.bin

Copy a game rom into the Run_From_USB folder and then make a copy of it then rename the copy to the right name so say copy the rom `Pole Position II (PAL) (Atari) (1987).a78` so you now have two copies of the file so when you name the copy you know what rom it loading in that folder so you rename `Pole Position II (PAL) (Atari) (1987) - Copy.a78` to `Atari7800-1.bin`
then you always have a copy of the rom in there so you know what `Atari7800-1.bin` is.
 
If it has a different extension its OK `Atari2600-1.bin` or `Atari7800-1.bin`, Retroarch will see what type of game rom is in there so does not matter what extension it is so if its a .a78, it will still load it as a .a78.

You can enable other emulators in the USB Drive too(not added yet) I did add scripts and files for Retroarch 1.7.1 and Stella so they can be added later, you can use the flag files: `ra-mode-enabled=yes` and `stella-mode-enabled=yes` so it loads different modes.

This is just the start of this and will get better in time, as we find out what else we can do on the Atari2600+ and its Linux, things take time to mature... :)
 
Have a nice day, Are you gonna play Atari Today... :)

Spannernick... :)
