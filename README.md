# Ender5Plus-SKRv14Turbo
All things related to my Ender 5 Plus

# 16th October 2020 - _Printer arrives_

![Image of ducks](https://github.com/aftershox/Ender5Plus-SKRv14Turbo/blob/main/images/afraid-of-wet.jpg)

**Stock Machine**
BUILT and TESTED - running 1.70.2 firmware from factory.  
- _**BUG found**_ - Auto Home puts NOZZLE and not BL Touch Probe pin at centre of bed.

---

Communicating with the Mainboard
- To connect to the mainboard from PC to USB - have to install FTDI drivers - https://support.th3dstudio.com/hc/en-us/articles/360043291472-Creality-Printer-Drivers-FT232R-Chip-Most-Models
- - Used the FTDI F232R Windows Drivers to create COM port for accessing the Creality Mainboard 
- Use Pronterface to capture existing setup

Firmware for Stock Creality board
- Firmware upgraded to Kersey Fabs Ender-(5PlusBLTouch_0904_V1.71.0 KF.hex) - to fix the BL Touch probe offset (Probe now in centre of bed)
> Watch the video and check Video Description for download links - https://youtu.be/9pDoxf13_wg

- Once Firmware is upgraded - the menus revert back to Chinese Language, so use the control panel / touch screen to set back to English Language. 

# 25th October 2020 - Next job is to install SKR Turbo v.1.4 with 5 x TMC2209s and Z-Steppers auto-align G34 and the BTT TFT 3.5"

1) Set jumpers on SKR v.1.4 Turbo - as per the BTT Guide for TMC 2209 Drivers in UART mode
- - Remove 3 x jumpers from each stepper installation location - leaving just one

2) If NOT using Stallguard / Sensorless Homing - you'll need to CUT the Diag pins on EACH Driver that uses a Physical Limit Switch
- X-UART (Cut Pin / Uses Physical Switch for X Endstop)
- Y-UART (Cut Pin / Uses Physical Switch for Y Endstop)
- Z-UART (CUT PIN / Uses BL Touch Probe as Z- MIN Endstop)
- E0-UART (Cut Pin / Uses Filament Runout Sensor [Physical Switch] with Extruder)
- E1-UART (used for SECOND Z Stepper Motor) - CUT PIN - as BL Touch Probe uses Z- MIN for Z Endstop

- If using 5 x TMC 2209 - i.e. to setup Z2 for using G34 - Z Steppers Auto-Alignment
- - Install TMC 2209 #5 into the E1-UART (Z2) socket
- - E1-UART [Used for Z2-UART) (DO NOT CUT PIN / Uses BL Touch Probe as Endstop)

