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


# Operation

    - The light gun operates as a mouse until the button/combination is pressed to enter pause mode. The Arduino serial monitor (or any serial terminal) can be used to see information while the gun is paused and during the calibration procedure.

    - Note that the buttons in pause mode (and to enter pause mode) activate when the last button of the combination releases. This is used to detect and differentiate button combinations vs a single button press.

    - The mouse position updates at 209Hz so it is extremely responsive.

# Run modes

The gun has the following modes of operation:

    - Normal - The mouse position updates from each frame from the IR positioning camera (no averaging)

    - Averaging - The position is calculated from a 2 frame moving average (current + previous position)

    - Averaging2 - The position is calculated from a weighted average of the current frame and 2 previous frames

    - Processing - Test mode for use with the Processing sketch (this mode is prevented from being assigned to a profile)

    - The averaging modes are subtle but do reduce the motion jitter a bit without adding much if any noticeable lag.

# Processing mode

    - The Processing mode is intended for use with the SAMCO Processing sketch. Download Processing from processing.org and find the 4IR Processing sketch from the SAMCO project. The Processing sketch lets you visually see the IR points as seen by the camera. This is very useful aligning the camera when building your light gun and for testing that the camera tracks all 4 points properly. I suppose if you don't want to install Processing then you can just open your favourite serial terminal program and watch the numbers scroll by.

# IR camera sensitivity

    - The IR camera sensitivity can be adjusted. It is recommended to adjust the sensitivity as high as possible. If the IR sensitivity is too low then the pointer precision can suffer. However, too high of a sensitivity can cause the camera to pick up unwanted reflections that will cause the pointer to jump around. It is impossible to know which setting will work best since it is dependent on the specific setup. It depends on how bright the IR emitters are, the distance, camera lens, and if shiny surfaces may cause reflections.

    - A sign that the IR sensitivity is too low is if the pointer moves in noticeable coarse steps, as if it has a low resolution to it. If you have the sensitivity level set to max and you notice this then the IR emitters may not be bright enough.

    - A sign that the IR sensitivity is too high is if the pointer jumps around erratically. If this happens only while aiming at certain areas of the screen then this is a good indication a reflection is being detected by the camera. If the sensitivity is at max, step it down to high or minimum. Obviously the best solution is to eliminate the reflective surface. The Processing sketch can help daignose this problem since it will visually display the 4 IR points.

# Profiles

    - The sketch is configured with 8 profiles available. Each profile has its own calibration data, run mode, and IR camera sensitivity settings. Each profile can be selected from pause mode by assigning a unique button or combination.

# Default Buttons

    - Trigger: Left mouse button

    - A: Right mouse button

    - B: Middle mouse button

    - Start: Enter Key

    - Select: Escape Key 

    - Up/Down/Left/Right: Keyboard arrow keys
    
    - Reload: Enter pause mode

    - Pedal: Mouse button 2


# Default Buttons in Pause mode

    - A, B, Start, Select, Up, Down, Left, Right: select a profile

    - Start + Down: Normal gun mode (averaging disabled)

    - Start + Up: Normal gun with averaging, switch between the 2 averaging modes (use serial monitor to see the setting)

    - Start + A: Processing mode for use with the Processing sketch

    - B + Down: Decrease IR camera sensitivity (use serial monitor to see the setting)

    - B + Up: Increase IR camera sensitivity (use serial monitor to see the setting)

    - Reload: Exit pause mode

    - Trigger: Begin calibration

    - Start + Select: save settings to non-volatile memory (EEPROM or Flash depending on the board configuration)
