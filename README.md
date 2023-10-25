
############################################# V1 Edits #############################################

Everything seems to be working currently, I haven't had time to test that much yet but the ABL & UBL functions all seem to be intact. Linear advanced seems to be working for me but again I need to test more. 
I was able to fix a bunch of menu issues and other random issues When I noticed during a search for some information that a member named Auburn had created a fork, so I downloaded it and noticed he had fixed the UBL issues which I just had started working on.
It also appears that the remaining LCD issues that I had not solved yet were also resolved, cheers Auburn.
It almost seems like the version of Marlin that was given to the community is a match-up of a couple of different versions.
According to the version file date, the release should be something around 2.0.3, however some of the syntax does not match up in either direction.
 Where you can find a cutoff between the verbiage of certain commands you may find that same pattern but then you will find where a deprecated feature or function name is still being used. 
Overall it's been a fun 3-day straight nightmare…. , and unless you are insanely familiar with building custom firmware for custom boards with custom environments and custom platforms I HIGHLY recommend that you stay far away from Visual Studio , platform IO , Marlon A$$ed build Sh1t Soft.
Even the examples I found of supposed working releases that use the same processor don’t do sh!t except throw errors and the more I dug into it, the more I questioned my interest in that level of insanity. 
I could probably tell stories for hours of Platform IO Hell right about now, but I’m tired and just wanted to get this bit done. 






############################################# Credit Below Goes To Auburn #############################################

############################################# Credit Below Goes To Auburn #############################################


# Modified Kobra Go Firmware

I've added/enabled several features to make printing from Octoprint a better experience

## Extra Features

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

## Notes

You will need to recalibrate your E steps after applying this firmware it will be off by a factor of ~2

## Building

https://www.reddit.com/r/anycubic/comments/y2waxu/tutorial_how_to_build_anycubic_marlin_source_code/
