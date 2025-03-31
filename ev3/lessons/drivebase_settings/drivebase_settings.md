---
title: Going Faster!
subtitle: Changing Speed By Using the Drivebase Settings
---

## Lesson Plan:
1. Read the informaion and follow the instructions to complete the assignment.  Be sure to complete all the steps!
2. Show or share the completed assignment with a mentor


## How to make your robot drive at different speeds
 * There are several ways to accomplish this goal.  
 * This lesson will teach you how to change the speed of your robot when using the **straight()** and **turn()** methods.
 * You may have noticed the following line in the example python programs:
```python
robot.settings(straight_speed=200, straight_acceleration=100, turn_rate=100, turn_acceleration=100)
```
 * The line above configures the speed and acceleration used by **straight()** and **turn()**
 * Don’t worry about the straight_acceleration and the turn_acceleration entries for now, you will not need use these while you’re still a beginner, but might do more with them as you gain experience
 * **straight_speed(speed in mm/s)** - Speed of the robot during **straight()**
 * **turn_rate(rotational speed in deg/s)** - Turn rate of the robot during **turn()**
 * This is described in additional detail here [https://pybricks.com/ev3-micropython/robotics.html](https://pybricks.com/ev3-micropython/robotics.html)
 * Not only can this can be used at the beginning of the program before robot moves, but it can be used throughout the program to change speeds.
 * Before changing the robot speed in your program you must use the **stop()** method.
 * Let's try an example!
 * Start the [FSS FLL Simulator: Speed Run Map](https://fssfll.github.io/gears/public/index.html?worldJSON=https%3A%2F%2Ffssfll.github.io%2Ffssfll%2Flessons%2Fdrivebase_settings%2Fspeed_run.json)
 * Make sure you are running in Python Pybricks Mode
 * Copy the code in in below (be careful to include it below "Where your code starts")
 * Goto the simulator tab and hit the play triangle


```python
################################################
# Here is where your code starts
################################################

# Drive forward for 300 mm with a speed of 50mm/s
robot.settings(straight_speed=50, straight_acceleration=100, turn_rate=100, turn_acceleration=100)
robot.straight(300)
robot.stop()

# Drive backwards for 300 mm with a speed of 250mm/s
robot.settings(straight_speed=250, straight_acceleration=100, turn_rate=100, turn_acceleration=100)
robot.straight(-300)
```
 * Try changing the speed.  Note that there are limits to how fast the robot's motors can move.
 * Add a **robot.turn()** method and try changing the turn angle rate.  
 * Generally it is not a good idea to run the motors at full speed as the accuracy of the robot decreases the faster you go.

## Now it is your turn!


### 1. In a different browser window or browser tab start the simulator: 

 * Start the [FSS FLL Simulator: Speed Run Map](https://fssfll.github.io/gears/public/index.html?worldJSON=https%3A%2F%2Ffssfll.github.io%2Ffssfll%2Flessons%2Fdrivebase_settings%2Fspeed_run.json)
 * Make sure you are in Python "Pybricks Mode"
 * Take a look at the game map in the Simulator tab
 * This is a timed trial.  Your goal is to have your bot finish at the center of the map completely behind the black and yellow striped zone before time expires.
 * When complete share your solution to a mentor or coach.
 * Record the time remaining on the clock at the end of the mission.  Try to get the most unused time you can!    

### 2. Copy in the example program below and try out the already completed Part 1
 * You can change the code in part 1!

### 3. Follow the instructions in the code comments below to complete Part 2 of the assignment


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
# Here is a slow start to the completing the timed trial.
# You may want to speed this part up!
#-----------------------------------------------------------

# Make the robot drive slowly and carefully
robot.settings(straight_speed=100, straight_acceleration=100, turn_rate=100, turn_acceleration=100)
robot.straight(1050)
robot.turn(-90)

#-----------------------------------------------------------
#                           PART 2
#
# Now it is your turn to add on to the program.
# Your goal is to get the robot fully behind the yellow and black striped zone
# before the timer expires.
#
# Use the robot.straight() method to move forward
# Use the robot.turn() method to turn 90 degrees
# Use the robot.settings() to change the speed of your robot
# Use the print() function to debug your program
#-----------------------------------------------------------

# Use print() to say your program is starting
print("Start driving in a square shape")

# Use robot.stright() and robot.turn() to get the robot into the
# finish area behind the yellow and black striped zone before the
# timer expires.

# Use a print() to say your program is done
print("Program complete!")

```

<p align="center">
<IMG ALIGN="CENTER" SRC="https://fssfll.github.io/fssfll/images/finish.jpg">
<BR>
<B>Congratulations, you have completed the lesson!</B><BR>
<A HREF="https://fssfll.github.io/fssfll/ev3/lessons/beginner/">Return To Beginner Lessons</A>
<BR>
</P>
