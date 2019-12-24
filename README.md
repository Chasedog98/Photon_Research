# Photon_Research
Passed research done for the Anycubic photon. 
Some items are not available due to current/future research.
Some of the papers were for a college course, not written to be published, and a majority of the work was taken out. 
These files are more for reference than citation for future work with slicing and anti-aliasing.

---------------------------------------------------------------
The Photon Web Server is all open source and not close to being finished. These files are for people who want to create their own web server controller.

The current version uses UART 1 on the Original Photon board, UART6 and WIFI port are not connected software wise, currently(V4.2.18).  
This program is also using an ESP8266 from adafruit, other versions may not be 5v compatable.

--------------------------------------------------------------
BE CAUTIOUS WHEN WIRING THE BOARD!!
---------------------------------------------------------------
Alternative to ESP8266 is a Pi Zero W with an ethernet hat to connect to the ethernet port and UART 1. Using both allows for uploading
photon files and control. Possibly could do everything with one or the other but not tested.

---------------------------------------------------------------
#### Confirmed Gcode Commands via Serial:

- M6030 "Photon/AA-TEST-PRINTS/_ShallowAnglesAATest_0X.photon" (starts a print file name imeddiatly)
- M6032 "Photon/AA-TEST-PRINTS/_ShallowAnglesAATest_0X.photon" (Reads a File Into Memory to be started with M6045) R: (file length in bytes)
- M20 (List SD Card)
- M23 (Select File on SD Card)
- M24 (Starts printing the M6032 open file on memory)
- M25 (Pause Print)
- M27 (Report SD print status) (M27 S4 - Report 4 seconds, M27 S0 - Stop reporting, M27 C - Report currently open filename)
- M6045 I4000 "M24" (Waits the Delay set time and Starts Printing the M6032 open file on memory)
- M30 (Delete file from SD Card)
- M33 (Stops print)
- M106 (Turn on Fan, Only works durring print)
- M107 (Turn off Fan, Only works durring print)
- M114 (Get current position)
- M115 (Firmware Info)
- M4001 (returns the configured stepper movement for all axis) R: (X:0.011430 Y:0.011430 Z:0.000625 E:0.001340 T:0/0/0/155/1 U:'GBK' B:1) 
- M105 (returns sensor temperatures) R: (ok T:161 /0 B:164 /0 @:0 B@:0)
- M8512 "configFile.gcode" (Dumps the current config.gcode EEPROM data into a file)
- G28 Z (Home Z Axis)
- G0 Z10 (Move Z axis at max speed)
- G0 Z10 F600 (Move Z axis at F speed)
- M6040 I100 (Reboot I defines the delay before restart)
- M7506 I636264 T0		//0; 1; color_flip, (Changes UI colours Negative/Positive/or switch watever its on)
- M9005 '"Networkname","Password"'
- G90 Absolute Positioning
- G91 Incremental Positioning

_____________________________________________________________________________________________________________________________________
I do not take full credit for anything. This is for refrence for others that have asked me to upload these documents. 
