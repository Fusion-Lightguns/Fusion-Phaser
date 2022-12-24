# Fusion Phaser Setup ------------------- Version 1.00




# LED Setup for Fusion Phaser

    With LED setup you have two choices, USB BAR or Loose.

    USB Bar use IR LEDs in a usb wii bar.

    Loose uses a IR LED Kit or DIY IR LEDS on wires.

# USB Bar Setup

    - Find middle of TV

    - Place USB Bars in center top & bottom of tv/screen.

    - Plug USB Bars into a power supply.

    - Calibrate gun (see below)

    - Enjoy

# Loose LED Setup 

    - Find middle of TV

    - Put two leds on top of tv and on bottom of tv, equal distance from the middle and edge of TV

    - Calibrate gun (see below)
    
    - Enjoy


# Calibration

    - Press Reload to enter pause mode.

    - Press a button to select a profile unless you want to calibration the current profile.

    - Pull the Trigger to begin calibration.

    - Shoot the pointer at center of the screen and hold the trigger down for 1/3 of a second while keeping a steady aim.

    - The mouse should lock to the vertical axis. Use the A/B buttons (can be held down) to adjust the mouse vertical range. A will increase and B will decrease. Track the pointer at the top and bottom edges of the screen while adjusting. You can also move your gun centered & click trigger again.

    - Pull the Trigger for horizontal calibration.
    
    - The mouse should lock to the horizontal axis. Use the A/B buttons (can be held down) to adjust the mouse horizontal range. A will increase and B will decrease. Track the pointer at the left and right edges of the screen while adjusting. You can also move your gun centered & click trigger again.

    - Pull the Trigger to finish and return to run mode. Values will apply to the currently selected profile in memory.

    - Recommended: After confirming the calibration is good, enter pause mode and press Start and Select to save the calibration to non-volatile memory.

    - Optional: Open serial monitor and update the xCenter, yCenter, xScale, and yScale values in the profile data array in the sketch (no need with step 9).

    Calibration can be cancelled during any step by pressing Reload or Start or Select. The gun will return to pause mode if you cancel the calibration.
    
# Advanced calibration

    - During center calibration, press A to skip this step and proceed to the vertical calibration

    - During vertical calibration, tap Up or Down to manually fine tune the vertical offset

    -During horizontal calibration, tap Left or Right to manually fine tune the horizontal offset

# Saving Settings

    - The calibration data and profile settings can be saved in non-volatile memory. The currently selected profile is saved as the default for when the light gun is plugged in.

    - For ItsyBitsy M0 and M4 boards the external on-board SPI flash memory is used. For ATmega32U4 the EEPROM is used.

# LED Fine Tuning

    - Plug in LEDS

    - Download this github : COMING SOON

    - Extract somewhere 

    - Open Fusion-Gun-Tool Folder

    - Open LED-Fine-Tune.mp4 (MAKE SURE THAT IT FULLSCREEN . YES THE WHOLE SCREEN)

    - Follow Video instructions.


