How to run Atari 2600, 7800 ROM Games from USB Drive on the Atari2600 Plus(DEEPLAY MOD)
===================================================================
PCUAE Atari2600 Plus Deeplay USB ROM Loader
============================================

This now has Stella included so you can run it as a Mode on it.
![STELLA_ON_DEEPLAY](https://i.ibb.co/9VC6nNP/Screenshot-2024-02-11-183918.png)
Missle Command from the 10 in 1 Game Cartridge running in Stella.
![STELLA_ON_DEEPLAY](https://i.ibb.co/m6qXQ6B/Screenshot-2024-02-11-172545.png)


This is now in PCUAE and you can flash a update to the Atari2600 Plus so it loads in PCUAE from the USB Drive, More info is in PCUAE, PCUAE is here: https://github.com/CommodoreOS/PCUAE

Always have a cartridge in slot when using PCUAE on the Atari 2600 Plus, its so the switches on the console work and it will not load the ROM file if no cartridge in the slot.

Installing the PCUAE Update on the Atari2600 Plus
==================================================

Its now a lot easier to install PCUAE on the Atari2600 Plus.

You need to flash the `update-boot-pcuae-atari2600-plus.img` to the Atari2600-Plus to boot PCUAE on it, it replaces the dmenu.bin file in the /oem partition so it boots PCUAE from the USB Drive.

Steps:
1. Put Atari2600 Plus Color Switch on Color and Hold Down the Reset switch for 2 to 3 seconds and make sure you can see it on your PC and its driver is installed, if you have updated the Atari2600 Plus with a firmware update before so like 1.1-rev2, 1.1-rev2 and 1.1x-rx2 then you just need do the same but flash the `update-boot-pcuae-atari2600-plus.img` intead to the Atari2600 Plus.

2. You need to click on `RKDevTool.exe` in the `START-PCUAE-ON-ATARI2600-PLUS` folder, you should see the application window open and a status message of 'Found one MASKROM device'.

3. Press the tab Upgrade Firmware button then press the Firmware button.

4. Find `update-boot-pcuae-atari2600-plus.img` thats in the `START-PCUAE-ON-ATARI2600-PLUS` folder and press Open.

5. You should see the IMG prepped in the window, then Press Upgrade button to start flashing the update to the Atari2600 Plus.

The update uploads in about 30 seconds. 

`Start to upgrade firmware...`

`Download Boot Start`

`Download Boot Success`

`Wait For Maskrom Start`

`Wait For Maskrom Success`

`Test Device Start`

`Test Device Success`

`Check Chip Start`

`Check Chip Success`

`Get FlashInfo Start`

`Get FlashInfo Success`

`Prepare IDB Start`

`Prepare IDB Success`

`Download IDB Start`

`Download IDB Success`

`Download Firmware Start`

`Download Image... (100%)`

`Download Firmware Success`


Upgrade firmware finish ok and finish flashing.

All Done.

If you need to install Maskrom driver because `no device found` in the `RKDevTool.exe` app on the PC(Windows) then install the driver thats in the `DriverAssitant_v5.12` folder in `START-PCUAE-ON-ATARI2600-PLUS` folder.

If you need help with installing Maskrom driver and installing the PCUAE update you can look at the 1.1-rev1 install instruction by Ben that are here: https://forums.atariage.com/topic/358796-atari-2600-beta-update-11

Once you have installed the update it should boot PCUAE from the USB drive, make sure you boot from the USB Drive first so it boots PCUAE then after that you will be able to boot without the USB Drive plugged in.


How to run Atari 2600, 7800 Games from USB Drive on the Atari2600 Plus
=======================================================================


When booting from the USB Drive make sure the Color switch is on B/W, USB Drive Mode, if you leave it on Color you should see the USB Drive apear on your Windows PC, if you do its working OK, you just need to switch it on B/W and restart the machine.

Inside the USB Drive, in  `\.options\atari2600_plus_options_flag_file` folder you should see a file that called `mode_settings.txt` you can change PCUAE settings in there to make PCUAE do something like run a Mode, if you do not have a USB Keyboard or THEGamepad to change its settings.

If it does not find a USB Stick then it will load the Dumper instead and load the cartridge thats in the slot.
At the moment the 2 switches(Select and Reset) on the Atari2600 Plus do not work with Retroarch but do with Stella, I need to find a way of adding them, they are controlled by the dmenu.bin file and this bypassing it at the moment so is only loading Retroarch and its cores.

Enable/Disable Dumper/Core
===========================

If you enable the Dumper then it disables the USB Rom Loader.

When you enable the dumper and load a game from a cartridge it will make a backup of it and sent it to the USB Drive too.

You can now switch modes by using THEA500 Gamepad plugged in to a USB Port so you:

Press and hold Menu button and then a button to run a shortcut, if it does nothing when you hold the buttons down let go of them then it will do that shortcut.

You will see what button does what on the screen now.

It now loads the rom file it sees in the PCUAE USB Drive Letter(H:):\PCUAE-Atari-Games\Run_From_USB folder so they have to be named correctly so:

Load Rom File from Run_From_USB folder
======================================

Atari VCS 2600 = Atari2600-1.bin

Atari 7800     = Atari7800-1.bin

Always have a cartridge in slot when using PCUAE on the Atari 2600 Plus, its so the switches on the console work and it will not load the ROM file if no cartridge in the slot.

Copy a game into the Run_From_USB folder and then make a copy of it then rename the copy to the right name so say copy the rom `Pole Position II (PAL) (Atari) (1987).a78` so you now have two copies of the file so when you name the copy you know what rom it loading in that folder so you rename `Pole Position II (PAL) (Atari) (1987) - Copy.a78`to `Atari7800-1.bin`
so you always have a copy of the rom in there so you know what `Atari7800-1.bin`is.
 
If it has a different extension still name it `Atari2600-1.bin` or `Atari7800-1.bin`, Retroarch will see what type of game it is so does not matter what extension it is so if its a .a78, it will still load it.
 
Have a nice day, Are you gonna play Atari Today... :)

Spannernick... :)

Have a nice day, Are you gonna play Atari Today... :)

Spannernick... :)
