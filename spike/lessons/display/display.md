---
title: Using the EV3 Display 
subtitle: How to use the EV3 Display
---

# Lesson 7:
# Using the Display

## Lesson Plan:
1. Watch the lesson plan video below
2. Read the informaion and follow the instructions to complete the assignment.  Be sure to complete all the steps!
3. Show or share the completed assignment with a mentor

<p align="center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/SJ3Bmar40Kg" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</p>

## About the EV3 Display Screen
 - The EV3 display screen is made up of an array of pixels which is like a piece of graph paper where each box is a pixel that can either be colored in or left blank.
 - The EV3 display is 178 pixels wide by 127 pixels high.
 - The width of the display is the "x" axis
 - The height of the display is the "y" axis
 - The origin of the display is in the top left corner.  This means the top left corner has position x=0 and y=0.
 - The picture below shows the "x" and "y" axis on the EV3 display along with some simple graphics made using turning on some pixels

<p align="center">
<IMG ALIGN="LEFT" SRC="https://fssfll.github.io/fssfll/lessons/display/display.jpg">
 </P>
 
## Displaying a text message
 - Use the **draw_text(x,y,*text*)** method to display text to the EV3 display
 - **x** is how far over from the top-left corner of the display to start your text message
 - **y** is how far down from the top-left corner of the display to start your text message
 - **text** is the text message you want to display.

## A Simple Example
 - Print "Hello World" to the display
 - Notice that the quotes are needed but are not displayed on the screen
 - Give this example a try!

```python
 #!/usr/bin/env pybricks-micropython

# Import the necessary libraries
import math
import time
from pybricks.parameters import *
from pybricks.hubs import EV3Brick
from pybricks.ev3devices import *
from pybricks.tools import wait
from pybricks.robotics import DriveBase

# Create the sensors and motors objects
ev3 = EV3Brick()

motorB = Motor(Port.B)
motorC = Motor(Port.C)
left_motor = motorB
right_motor = motorC

color_sensor_in1 = ColorSensor(Port.S1)


robot = DriveBase(left_motor, right_motor, wheel_diameter=56, axle_track=89)
robot.settings(straight_speed=200, straight_acceleration=100, turn_rate=100, turn_acceleration=100)
###################################
# Here is where your code starts
###################################
# Write "Hello World" on the EV3 Display
# Use the position:
#   x = 0
#   y = 0
ev3.screen.draw_text(0, 0, "Hello World")
# Let the program run for 2 seconds
wait(2000)
# Clear the Screen
ev3.screen.clear()
# Let the program run for 2 more seconds
wait(2000)
```

## Another Example
 - Print the x,y coordinates of the message on the display
 - Add a loop and repeatedly print the message while moving it down and to the right 1 pixel
 - Give this example a try, how could you change it to do something different?

```python
 #!/usr/bin/env pybricks-micropython

# Import the necessary libraries
import math
import time
from pybricks.parameters import *
from pybricks.hubs import EV3Brick
from pybricks.ev3devices import *
from pybricks.tools import wait
from pybricks.robotics import DriveBase

# Create the sensors and motors objects
ev3 = EV3Brick()

motorB = Motor(Port.B)
motorC = Motor(Port.C)
left_motor = motorB
right_motor = motorC

color_sensor_in1 = ColorSensor(Port.S1)


robot = DriveBase(left_motor, right_motor, wheel_diameter=56, axle_track=89)
robot.settings(straight_speed=200, straight_acceleration=100, turn_rate=100, turn_acceleration=100)
###################################
# Here is where your code starts
###################################
# Create a variable i and set it equal to zero
i=0
# Create a loop which will run 128 times
while i < 128:
    # Clear the screen
    ev3.screen.clear()
    # Display the (x,y) location on the screen
    ev3.screen.draw_text(i, i, "(x=" + str(i) + ",y=" + str(i) + ")")
    # Add 1 to i.  This will move the mesage down one and to the right one
    i = i + 1
    # Wait 100 mS (that is 10% or 1/10th of a second!)
    wait(100)
```

## There's More!
 - There's more you can do with the display like drawing shapes and displaying pictures
 - Check out the EV3 Micropython documentation if you'd like to learn more.

## Now it is your turn!

### 1. Start Visual Studio Code and Connect to your EV3 Robot

### 2. Copy in the example program below and try out the already completed "Part 1"

### 3. Follow the instructions in the code comments below to complete "Part 2" of the assignment

```python
 #!/usr/bin/env pybricks-micropython

# Import the necessary libraries
import math
import time
from pybricks.parameters import *
from pybricks.hubs import EV3Brick
from pybricks.ev3devices import *
from pybricks.tools import wait
from pybricks.robotics import DriveBase

# Create the sensors and motors objects
ev3 = EV3Brick()

motorB = Motor(Port.B)
motorC = Motor(Port.C)
left_motor = motorB
right_motor = motorC

color_sensor_in1 = ColorSensor(Port.S1)


robot = DriveBase(left_motor, right_motor, wheel_diameter=56, axle_track=89)
robot.settings(straight_speed=200, straight_acceleration=100, turn_rate=100, turn_acceleration=100)
 
################################################
# Here is where your code starts
################################################

#-----------------------------------------------------------
#                           PART 1
#
# A simple Example of printing to the EV3 screen
#-----------------------------------------------------------
# Write "Hello World" on the EV3 Display
# Use the position:
#   x = 0
#   y = 0
ev3.screen.draw_text(0, 0, "Hello World")
# Let the program run for 2 seconds
wait(2000)
# Clear the Screen
ev3.screen.clear()
# Let the program run for 2 more seconds
wait(2000)

#-----------------------------------------------------------
#                           PART 2
#
# Display 4 new messages to the EV3 Screen
#-----------------------------------------------------------
# Display the text "TL" at (x=0,y=0)

# Display the text "TR" at (x=150,y=0)

# Display the text "BL" at (x=0,y=100)

# Display the text "BR" at (x=150,y=100)

# Wait for 5 seconds

```
