# **AnyCubic Kobra Go / Neo  TriGorilla Gen_V.3.0.7**
# Source Files & Firmware
Fixed 
ABL  EXTRAPOLATE_BEYOND_GRID
ABL_BILINEAR_SUBDIVISION
Many Menun Options

Not working
UBL Mesh Saving & Loading
Driver current doesn't report correct until edited
Acceleration in menu is missing last digit
Linear advance shows settings but printer ignores them

Untested
Runout sensor from menu
Power Outage from menu



### Thanks to [Auburn](https://github.com/Auburn) for his work on the following 

+ UBL Initial fixes
+ Quick Home
+ M117 & M73 LCD Status fixes
+ Many UI Fixes



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
