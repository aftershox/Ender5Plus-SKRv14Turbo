Configuration files for Ender 5 PLUS - 3dpmarkr (17th November 2020)
====================================================================

Marlin 2.0.7.2.

Configuration.h

Configuration_adv.h

HARDWARE
========
Creality Ender 5 Plus printer

with SKR v.1.4 TURBO Board (LPC1769)

and BTT TFT35 display (running in Marlin mode - 12864-LCD / emulator mode)

Stock Hotend / Stock FAN Assembly

Stock Filament Runout Sensor

Stock BL Touch v.3.1 mount

- MUST be wired to SKR SERVO Port, and Z-Min endstop port (NOT Probe)


TMC2209 stepper drivers x 5

(ALL 5 x Diag pins MUST be cut, bent or removed if NOT using SENSORLESS HOMING)
- X, Y, Z1, Z2 and E0 wired to ports on their own steppers (on the SKR v.1.4. board)

Using physical endstops (NOT SENSORLESS HOMING)

MARLIN 2.0.7.2. Features Enabled
================================
Thermal Runaway Protection - Hotend and Bed ONLY (Not Chamber!)

ABL - G29 - BILINEAR AUTO_BED_LEVELING_BILINEAR x 5 Probe Points (25 total)

Dual Z - G34 Auto Align Steppers *enabled*

PID AutoTune Hotend & Bed *enabled*

*NEW FEATURE* - Z Probe Offset Wizard *enabled*

Printer Info Screen

Software Endstops Menu on LCD

S Curve Acceleration *enabled* 

Probe Z Offset / Babystepping Z COMBINED MODE - double-click LCD knob while printing to access.


BUG's Fixed
===========
Fixed Bed Size - X,Y and Z values

Fixed issues with HOMING - endstops falsely trigger due to noise (ENDSTOP_NOISE_THRESHOLD) 

Sensible default mA values for all of the TMC2209's 

Improved default PID values for Hotend and Bed - based on PLA (205 Hotend / 60 Bed)

Fixed "SD Init Fail" for SKR boards not reading SD Card ONBOARD.

NOTE : All changes to Marlin are noted with comments line of //3dpmarkr

POST-INSTALLATION NOTES
=======================
After you have installed the firmware.bin

A)- Perform an EEPROM reset

B)- Get current PID settings using M503

- PID Tune the hotend for your desired material temperatures (use the built-in Menu on the LCD "Advanced Settings", or the following gCode via a terminal)

>HOTEND

>m303 c5 e0 s205 u1

>(c=5 iterations e=0 hotend s=target temp {205}) u1 store / use settings immediately

>m500

>(save to eeprom)

- PID Tune the BED for your printing adhesion temperatures (60) (use the built-in Menu on the LCD, or the following gCode via a terminal)

>BED

>m303 c5 e-1 s60 u1

>(c=5 iterations e=-1 bed s=target temp {60}) u1 store / use settings immediately

>m500

>(save to eeprom)

C) G34 Auto Z Alignment
- Pre-heat your machine to an appropriate temperature - i.e. 200 nozzle / 60 bed
- From the "Motion" menu, choose "Auto Z Align"
- wait until the LCD display reports "Accuracy Achieved" (If this fails - Level your bed, and re-try)

D) Level your bed
- Pre-heat your machine to an appropriate temperature - i.e. 200 nozzle / 60 bed
- From the "Motion" menu, choose "Level Corners"
- - Follow the procedure for levelling your bed corners / centre

- once complete, select "Level Bed" from the menu
- - Your bed levelling procedure will now measure n/25 points 
- - Once complete, choose "STORE SETTINGS" to store the G34 / Mesh Data from the bed levelling procedures.

E) AUTO-HOME your printer

F) Under "Temperature" - lower the temperature of your hot-end to 150 degrees C (it needs to be WARM, but not oozing filament!)
- Wait until the Hotend reaches the new lower temperature
- Clean your NOZZLE (a dirty nozzle can interfere with Z Probe offset measurements in next step)

F) If required - run the "Probe Offset Wizard" from the LCD menu - "Probe Offsets" menu - to correctly set your Z Probe Offset
- Follow the on-screen instructions.
- Remember to "Store Settings" once complete.

G) From the "Temperature" menu, select "Cooldown"


H) FINALLY - load up, and print a bed tramming / 1st layer test gCode - to ensure your printer is dialled in (especially your Z Offset)
- While it is printing - you can DOUBLE-CLICK the knob / selector wheel to access the Probe Z Offset values, and rotate left / right to "fine-tune" the value (includes Babystepping Z)

CONGRATULATIONS - YOUR ENDER 5 PLUS IS NOW READY TO USE.
========================================================

Don't forget to "tune" your printer.