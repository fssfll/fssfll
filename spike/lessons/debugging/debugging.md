---
title: The robot doesn't work. What now?!? 
subtitle: How to debug your code
---

## Lesson Plan:
1. Watch the lesson plan video below
2. Read the informaion and follow the instructions to complete the assignment.  Be sure to complete all the steps!
3. Show or share the completed assignment with a mentor

<p align="center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/d_q8OJwLrRU" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</p>

## Tools you can use to debug your code

### Code Comments
  * A code comment is a text note added to source code to provide information, usually about the function of the code.
  * A comment in Python starts with the hash character, # and extends to the end of the line.
  * An example Python comment is shown below

```python
# This entire line is a Python comment
# Comments are a great way to let other people know how your program works

# You can also use comments to remove one or more lines of code from you program.
# This can be helpful when debugging your program.
# For example, the following line starts with the hash character, # so it is a comment:
# robot.turn(90)

# Removing the hash chararcter turns it into a line of code to be executed:
robot.turn(90)
```

### Print Function: print()
  * Print function calls can be added to your code to display messages to the console.
  * The console is where you can view the results of commands and status like the print() function.
  * In the simulator the console is located at the bottom of the screen and can be expanded by clicking on the inverted "V" (this is called a chevron)
  * In some cases, like when using the simulator or when using Visual Studio Code these can be used to display helpful information about what your code is doing.
  * Print statements are not displayed on the EV3's screen.  We'll cover how to do that in a different lesson.
  * You print text with the print function by including it in quotes like this:
```python
# A simple text print message
print("Hello World.")
```
  * Print statements can be more advanced like in the example below.
  * A plus sign, + can be used to join variables, text and other elements together.
  * The variable speed is a number and is converted to a text string for printing using the str() function
```python
# Set the variable speed equal to 200
speed = 300
# Print the value of the variable speed
print("Speed= " + str(speed) + " mm/Second")
```

### The wait() Method
  * The wait() method can be used to pause your program for a period of time before continuing
  * The wait() method takes an input time in milliseconds
  * Remember there are 1000 milliseconds in one second.
  * As an example, if you wanted to pause your program for 3.5 seconds you would do the following:
 ```python
 print("The program has started")
 print("Now pausing the program for 3.5 seconds")
 wait(3500)
 print("The program continues...")
 ```

## Now it is your turn!

### 1. In a different browser window or browser tab start the simulator: 

  * [Launch FSS FLL Simulator: LESSON 2](https://fssfll.github.io/gears/public/index.html?worldJSON=https%3A%2F%2Ffssfll.github.io%2Ffssfll%2Flessons%2Flesson1%2Flesson1.json)
  * Make sure you are in Python "Pybricks Mode"

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
# Example of using print, comments, and the wait() method
#-----------------------------------------------------------
# Example print message
print("Hello World!")

# Pause the program for half a second
print("Pausing the program for half a second")
wait(500)

# Continuing the program
print("The program resumes...")

#-----------------------------------------------------------
#                           PART 2
#
# Now it is your turn to add on to the program.
# Use the robot.straight() methods to move foward,
# then wait for 5 seconds, then move backwards to return home.
# Use print() to display on the console what your robot is doing
#-----------------------------------------------------------


# Use print() to say your robot will move forward

# Use robot.straight() to move forward

# Use print() to say you are waiting for 5 seconds

# Use wait() to pause for 5 seconds.  Try commenting out the wait() to remove the pause.

# Use print() to say your robot will move backwards

# Use robot.straight() to move backwards

# Use print() to say mission accomplished and you've returned to base!


```


