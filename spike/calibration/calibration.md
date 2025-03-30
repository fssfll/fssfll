# Calibration Routine For FSS FLL Spring Training Robot

<p align="center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/zU0HW1fr838" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</p>

Calibrating the color sensor is an part important of line following.  A line following routine will typically attempt to turn the robot to keep 
the color sensor directly above the edge of parallel black and white lines.  The robot does this by calculating the color sensor's reflected light intensity and comparing that to a threshold.
The threshold is calculated based on a value between the black and white values typically (white - black) / 2.

In order for the threshold to be calculated correctly, the white and black values must be determined.  These values will change based on the lighting in the room and game mat so it is recommended to run a calibration routine ahead of each competitive match.

The python program below contains two functions.
- __do_calibration(port):__ Prompts the user to place the robot's color sensor above a black line and then a white line and records the refelected light intensity.  The values are then saved to a file for later use.  This function takes the color sensor port (1 - 4) the user wishes to calibrate as an input.
- __read_calibration(port):__ Retrieves the calibration values for the selected port stored by the do_calibration(port) routine and returns them to the user as [black_value,white_value]

It is recommended that the do_calibration method be assigned to mission_eight.py button 8.  Being in the second tier this button takes a second longer to access, but that is not a problem since the calibration is done before the match clock starts.  And this leaves the easier access lower tier button available for mission programs.  And coaches and team members from all the FSS teams will have a common approach.

The program also contains example function calls.  Execution of the program will perform the do_calibration(port) and read_calibration(port) routines.

This approach is based off of the great example provided here: [https://github.com/bashir2/penguins_fll_2021](https://github.com/bashir2/penguins_fll_2021)
```python
#!/usr/bin/env pybricks-micropython

######################################################
# Basic setup for FSS FLL Spring Training Robot
# !!! -- DO NOT CHANGE THIS PART OF THE PROGRAM -- !!!
######################################################

# Import the necessary libraries
import math
import time
import os
from pybricks.ev3devices import *
from pybricks.parameters import *
from pybricks.robotics import *
from pybricks.tools import wait
from pybricks.hubs import EV3Brick
from pybricks.media.ev3dev import Font
ev3 = EV3Brick()
motorB = Motor(Port.B)
motorC = Motor(Port.C)
left_motor = motorB
right_motor = motorC
robot = DriveBase(left_motor, right_motor, wheel_diameter=56, axle_track=108)
robot.settings(straight_speed=200, straight_acceleration=100, turn_rate=100)



###################################
# Here is where your code starts
###################################

# Read the color sensor Calibration
def read_calibration(port):
    '''
    Reads the previously stored calibration value for the input port
    and returns [black_value,white_value] as the lower
    and upper bounds of the reflected light
    '''
    
    # Setup the Font Type and Size
    ev3.screen.set_font(Font(None,20))

    # Wipe the EV3 display
    ev3.screen.clear()
    
    # Open the Calibration File
    try:
        file_handler = open("Calibration.txt", "r")
        calibration_file = file_handler.readlines()
        file_handler.close()
        [port,black_value,white_value] = [x.strip() for x in calibration_file[port + 1].split(",")]
        ev3.screen.draw_text(0, 0,  "Port " + str(port))
        ev3.screen.draw_text(0, 20, "Reading Stored")
        ev3.screen.draw_text(0, 40, "Calibration Values:")
        ev3.screen.draw_text(0, 60, "BLACK:" + str(black_value))
        ev3.screen.draw_text(0, 80, "WHITE:" + str(white_value))
        wait(2000)
    except OSError:
        # Calibration File was not found.  Use default
        # values of 0 and 100
        ev3.screen.draw_text(0, 0,  "Calibration.txt")
        ev3.screen.draw_text(0, 20, "Does not exist")
        ev3.screen.draw_text(0, 40, "Using Default Values")
        black_value = 0
        white_value = 100
        ev3.screen.draw_text(0, 60, "BLACK:" + str(black_value))
        ev3.screen.draw_text(0, 80, "WHITE:" + str(white_value))
    return black_value, white_value


def do_calibration(port):
    '''
    Calibration routine for color sensor for the selected port input
    '''
    # Set the speaker Volume
    # Volume is set as a percentage of maximum
    # '_all_' signifies this should be used for all types of speaker sounds
    percent_volume = 100
    ev3.speaker.set_volume(percent_volume,'_all_')

    # Setup the voice characteristics
    # 'm1' 'm2' 'm3' are male voices
    # 'f1' 'f2' 'f3' are female voices
    # speed sets the words spoke per minute
    ev3.speaker.set_speech_options(language=None, voice='f2', speed=200, pitch=None)

    # Setup the Font Type and Size
    ev3.screen.set_font(Font(None,20))

    # Select the port for calibration
    if port == 1:
        color_sensor = ColorSensor(Port.S1)
    elif port == 2:
        color_sensor = ColorSensor(Port.S2)
    elif port == 3:
        color_sensor = ColorSensor(Port.S3)
    elif port == 3:
        color_sensor = ColorSensor(Port.S3)
    else:
        ev3.screen.draw_text(20, 40,  "*** ERROR ***")
        ev3.screen.draw_text(20, 80,  "Port " + str(port) + " not valid")
        ev3.speaker.say("ERROR... Calibration not performed...")
        return

    # Prompt the user to calibrate black
    ev3.screen.draw_text(0, 0,   "Place Color Sensor")
    ev3.screen.draw_text(0, 20,  "Port " + str(port))
    ev3.screen.draw_text(0, 40,  "On Black")
    ev3.speaker.say("Place Color Sensor Port... " + str(port) + "... on Black")

    # Loop until the center button in pressed
    # When button pressed, the current value becomes the black value
    center_button_pressed = False
    while center_button_pressed == False:
        ev3.screen.draw_text(0, 0,   "Place Color Sensor")
        ev3.screen.draw_text(0, 20,  "Port " + str(port))
        ev3.screen.draw_text(0, 40,  "On Black")
        ev3.screen.draw_text(0, 60,  "Current Value: " + str(color_sensor.reflection()))
        wait(100)
        ev3.screen.clear()
        if(ev3.buttons.pressed() == [Button.CENTER]):
            center_button_pressed = True
            black_value = color_sensor.reflection()
        else:
            center_button_pressed = False

    # Prompt the user to calibrate white
    ev3.screen.draw_text(0, 0,  "Place Color Sensor")
    ev3.screen.draw_text(0, 20, "Port " + str(port))
    ev3.screen.draw_text(0, 40, "On White")
    ev3.speaker.say("Place Color Sensor Port... " + str(port) + "... on White")

    # Loop until the center button in pressed
    # When button pressed, the current value becomes the white value
    center_button_pressed = False
    while center_button_pressed == False:
        ev3.screen.draw_text(0, 0,   "Place Color Sensor")
        ev3.screen.draw_text(0, 20,  "Port " + str(port))
        ev3.screen.draw_text(0, 40,  "On White")
        ev3.screen.draw_text(0, 60,  "Current Value: " + str(color_sensor.reflection()))
        wait(100)
        ev3.screen.clear()
        if(ev3.buttons.pressed() == [Button.CENTER]):
            center_button_pressed = True
            white_value = color_sensor.reflection()
        else:
            center_button_pressed = False

    # Wait for the user to stop pushing the button
    while ev3.buttons.pressed() == [Button.CENTER]:
        wait(100)

    # Now write the white and black values into the calibration file
    center_button_pressed = False
    ev3.screen.draw_text(0, 0,   "The Stored Calib")
    ev3.screen.draw_text(0, 20,  "Values are")
    ev3.screen.draw_text(0, 60,  "BLACK: " + str(black_value))
    ev3.screen.draw_text(0, 80,  "WHITE: " + str(white_value))
    ev3.screen.draw_text(0, 100, "Press cntr btn to exit")
    wait(100)
    while center_button_pressed == False:
        if(ev3.buttons.pressed() == [Button.CENTER]):
            center_button_pressed = True
        else:
            center_button_pressed = False
    ev3.screen.clear()

    #--------------------------------------
    # Update Stored Values
    # Calibration.txt File Format:
    #--------------------------------------
    # Calibration File V1.0
    # PORT NUMBER, BLACK LEVEL, WHITE LEVEL
    # 1,0,100
    # 2,0,100
    # 3,0,100
    # 4,0,100
    create_new_calibration_file = False

    try:
        file_handler = open("Calibration.txt", "r")
        calibration_file = file_handler.readlines()
        file_handler.close()
        # Check for the correct version of the calibration file
        # This check will allow for updating the file format in the future
        if(calibration_file[0].strip() != "Calibration File V1.0"):
            create_new_calibration_file = True
            print("Need to create new calibration file...")
    except OSError:
        # Set a flag indicating a need to create a new calibration file
        create_new_calibration_file = True

    # Create a new calibration file
    if create_new_calibration_file == True:
        # Create and populate a list with the contents of the new calibration file
        calibration_file = []
        calibration_file.append("Calibration File V1.0\n")
        calibration_file.append("PORT NUMBER,BLACK LEVEL,WHITE LEVEL\n")
        # Fill in default values for all ports
        calibration_file.append("1,0,100\n")
        calibration_file.append("2,0,100\n")
        calibration_file.append("3,0,100\n")
        calibration_file.append("4,0,100\n")
        # Now add the new values for the port we are updating
        # [port+1] is the line number starting from zero in Calibration.txt
        calibration_file[port+1] = str(port) + "," + str(black_value) + "," + str(white_value) + "\n"
        # Write the calibration file contents into Calibration.txt
        file_handler = open("Calibration.txt", "w")
        for line in calibration_file:
            file_handler.write(line)
        file_handler.close()
    else:
        # Calibration file exists, update the port values
        print("Found Valid Calibration File")
        calibration_file[port+1] = str(port) + "," + str(black_value) + "," + str(white_value) + "\n"
        file_handler = open("Calibration.txt", "w")
        for line in calibration_file:
            file_handler.write(line)
        file_handler.close()

########################################
# do_calibration(port)
# Perform sensor calibration routine for
# selected port input.
#
# This is an example of the function call 
# that would be run as needed by the team 
# ahead of a competition match
#########################################
port = 1
do_calibration(port)

########################################
# read_calibration(port)
# Open file and read calibration values
# for selected port input.
#
# This is an example of how to read the
# stored calibration values.  This would
# normally be called a part of running
# a mission. 
########################################
[read_black,read_white] = read_calibration(port)
print("Black/Low Color Sensor Value = " + str(read_black))
print("White/High Color Sensor Value = " + str(read_white))

```
