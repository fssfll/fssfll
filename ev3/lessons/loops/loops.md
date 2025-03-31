---
title: Making repeated actions easy!
subtitle: Introduction to code loops
---

## Lesson Plan:
1. Watch the lesson plan video below
2. Read the informaion and follow the instructions to complete the assignment.  Be sure to complete all the steps!
3. Show or share the completed assignment with a mentor

<p align="center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/EdrdanNYi7Q" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</p>

## What is a programming loop?
 * A loop in a computer program is an instruction that repeats until a specified condition is reached. In a loop structure, the loop asks a question. If the answer requires action, it is executed.
 * In Python, there are two main types of programming loops.  The **for** loopi and the **while** loop.  In this lesson we'll focus on the **while** loop.
 * The **while** loop is a programming concept that will execute a block of code over and over again while a given condition holds true.
 * You need three components to create a while loop:
   1. The **while** keyword
   2. A condition that can be tested to see if it is True or False
   3. A block of code that you want to run repeatedly
 * With that in mind, let's try an example.  
 * Start the [FSS FLL Simulator](https://fssfll.github.io/gears/public/index.html?worldJSON=https%3A%2F%2Ffssfll.github.io%2Ffssfll%2Flessons%2Flesson1%2Flesson1.json)
 * Make sure you are running in Python Pybricks Mode
 * Copy the code in in below (be careful to include it below "Where your code starts")
 * If your computer has speakers, turn up the volume to hear The Count!
 * Goto the simulator tab and hit the play triangle

```python
################################################
# Here is where your code starts
################################################

# Set a variable count to 1
count = 1

# Create a loop which will run as long as the count is
# less than or equal to 3.
while (count <= 3):
    # Print to the console the number followed by  ...ah... ah... ah...
    print(str(count) + " ...ah... ah... ah...")
    # Have the robot say the number followed by  ...ah... ah... ah...
    ev3.speaker.say(str(count) + " ...ah... ah... ah...")
    # Add 1 to the count every time the loop executes
    count = count + 1
```

* There are just a few programming rules which need to be followed (this is called **syntax**) which needs to be followed for the loop to make sense.
* Let's take a look at them using the example above.
* The while loop and condition tested must be followed by a colon **:**

```python
while (count <= 3):
```

* All the lines in the block of code that you want to run repeatedly must be indented by the same amount of spaces.
* In the example below, we can set the variable count back to 1 after the loop runs.

```python
while (count <= 3):
    # Print to the console the number followed by  ...ah... ah... ah...
    print(str(count) + " ...ah... ah... ah...")
    # Have the robot say the number followed by  ...ah... ah... ah...
    ev3.speaker.say(str(count) + " ...ah... ah... ah...")
    # Add 1 to the count every time the loop executes
    count = count + 1

# Set count back to 1.  This is not indented and would not be part of the while loop above.
count = 1
```

* You must follow the correct programming rules (syntax) for you program to run! 

## Now it is your turn!

### 1. In a different browser window or browser tab start the simulator: 

  * [Launch FSS FLL Simulator: Code Loops](https://fssfll.github.io/gears/public/index.html?worldJSON=https%3A%2F%2Ffssfll.github.io%2Ffssfll%2Flessons%2Flesson1%2Flesson1.json)
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
# Drive forward three times using a while loop
#-----------------------------------------------------------
count = 1
while (count <= 3):
  # Drive forward 100 millimeters
  robot.straight(100)
  # Increment the count
  count = count + 1

#-----------------------------------------------------------
#                           PART 2
#
# Now it is your turn to add on to the program.
# Make the robot drive in square shape using a while loop
# A square shape can be made by driving straight and then turning right 4 times
#
# Use the robot.straight() method to move forward
# Use the robot.turn() method to turn 90 degrees
# Use the print() function to debug your program
#-----------------------------------------------------------

# Use print() to say your program is starting
print("Start driving in a square shape")

# Create a variable count and set it to 1

# Define a while loop which will run as long as the count is
# less than or equal to 4.  Remember to end the line with a :

  # Use robot.straight() to move forward.  
  # This needs to be indented.
  
  # Use robot.turn() to turn the robot 90 degrees. 
  # This needs to be indented.
  
  # Increment the count

# Use print() that the program is done.
# This is not part of the block of code to be repeated.
# This should not be indented.

```

<p align="center">
<IMG ALIGN="CENTER" SRC="https://fssfll.github.io/fssfll/images/finish.jpg">
<BR>
<B>Congratulations, you have completed the lesson!</B><BR>
<A HREF="https://fssfll.github.io/fssfll/ev3/lessons/beginner/">Return To Beginner Lessons</A>
<BR>
 </P>




