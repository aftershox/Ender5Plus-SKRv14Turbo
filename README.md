# Ender5Plus-SKRv14Turbo
All things related to my Ender 5 Plus

Change Log :-

Stock Machine BUILT and TESTED - running 1.70.2 firmware from factory.  
- BUG - Auto Home puts NOZZLE and not BL Touch Probe pin at centre of bed.

Firmware upgraded to Kersey Fabs Ender-(5PlusBLTouch_0904_V1.71.0 KF.hex) - to fix the BL Touch probe offset (Probe now in centre of bed)
- To connect to the mainboard from PC to USB - have to install FTDI drivers - https://support.th3dstudio.com/hc/en-us/articles/360043291472-Creality-Printer-Drivers-FT232R-Chip-Most-Models
- - Used the FTDI F232R Windows Drivers to create COM port for accessing the Creality Mainboard 
- Use Pronterface to capture existing setup
- Once Firmware is upgraded - the menus revert back to Chinese Language, so use the control panel / touch screen to set back to English Language. 

25th October 2020 - Next job is SKR Turbo v.1.4 with 5 x TMC2209s and Z-Steppers auto-align G34 and the BTT TFT.

