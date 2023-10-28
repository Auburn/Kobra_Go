# **AnyCubic Kobra Go / Neo  TriGorilla Gen_V.3.0.7**
# Source Files & Firmware
 **_Tons of fixes and improvements_**
  Lots More to Come

# **Hardware Updates & News**
## ( HSDC / XHSC / HC32F460 HC32F460KECA )
- Yes, it's the lower memory HC32F460KECA not HC32F460KETA
- Thats why you see the weird memory offset hack in the Linker file

* Updates and improvements to the hardware support stack
* [Fixed all the broken HSDC Packs](https://github.com/OrloDavid/HC32F460)
* Download, Install and watch the repo schema come back to life
* This allowed updated to the Keil  build environment tools
* I will be uploading more hardware / processor specific files in the near future along with translated source material
* Modified systems clocks, but wasn't worth the effort :(  Reverted


# **Software Updates & News**
## **( Marlin 2.0.x Bugfix  + 2.1.x Bugfix Updates)**
+ Get the software here
+ https://github.com/OrloDavid/Any-Ko-Go
+ Prebuilt Firmware files coming soon
+ TONS of ABL & UBL Fixes
+ Broken links, missing files, functions, classes and so on
+ LCD Menu options are nearly completely restored with every option you could ever want!
+ Linear Advance fixed and updated where code was missing or broken
+ Every fix I have done has been a proper implementation fix
+ When an in-place fix wasn't possible, the code was migrated and updated as far as possible


![IMG_20231028_122144~2](https://github.com/OrloDavid/Any-Ko-Go/assets/26681128/ebfd3f69-85e9-4f17-9ff3-14ba18604051)

![IMG_20231028_122159~3](https://github.com/OrloDavid/Any-Ko-Go/assets/26681128/6e0e1404-5a6d-4b43-8158-0f3bd4195d9a)

![IMG_20231028_115926](https://github.com/OrloDavid/Any-Ko-Go/assets/26681128/00af546c-3c7e-4eea-85a0-58ba34c152ff)

![IMG_20231028_115913](https://github.com/OrloDavid/Any-Ko-Go/assets/26681128/ae592034-aa54-41f1-9dfb-b73b6c81c10c)

![IMG_20231028_121012~2](https://github.com/OrloDavid/Any-Ko-Go/assets/26681128/76d31683-da6c-4ea7-8ec7-8b277c0944f2)



### Thanks to [Auburn](https://github.com/Auburn) for his work on the following 

+ UBL Initial fixes
+ Quick Home
+ M117 & M73 LCD Status fixes
+ Many UI Fixes
+ and more



# %%%% Credit Below Goes To [Auburn](https://github.com/Auburn/Kobra_Go) %%%%

[Jordan Peck / Auburn ](https://github.com/Auburn)


https://github.com/Auburn/Kobra_Go

## Modified Kobra Go Firmware

I've added/enabled several features to make printing from Octoprint a better experience

### Extra Features

- Enable "Quick Home", home X & Y at the same time
- Increased default max acceleration limits
- Enable M117 Gcode for setting messages to printer screen
- Enable M73 Gcode for setting progress bar on printer screen

Normally when printing from Octoprint you don't get a layer count/progress bar on the printer screen. Most slicers have the option to output these Gcodes with the current print progress

- Enabled "Linear Advance" (inactive)
- Disabled "Stealth chop E"
- Added/Enabled "Square wave stepping E"

Experimental, I've found that enabling linear advance can cause the extruder to stop in some prints. By default it's set to 0 (inactive) so if you want to try this you need to set the linear advance factor via the M900 gcode, I recommend about 0.4

- Enable "Host Actions" and "Host Action Prompts"
- Added host action support to the printer UI

Allows starting/pausing/resuming of Octoprint prints

- Increase probing accuracy by doing multiple probes per point
- Enabled UBL bed leveling instead of bilinear (unstable)

This mostly works, some parts of the LCD UI have navigation issues so it's recommended to do setup UBL through GCode.
Saving UBL meshes is what caused the most issues, they seem to get corrupted when saved to the EEPROM so avoid doing this.
Instead you can save it to GCode using `G29 S-1`

### Notes

You will need to recalibrate your E steps after applying this firmware it will be off by a factor of ~2

## Building

https://www.reddit.com/r/anycubic/comments/y2waxu/tutorial_how_to_build_anycubic_marlin_source_code/
