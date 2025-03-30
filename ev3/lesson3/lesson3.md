# FSS FLL Lesson 3: Line Following

<p align="center">
 <iframe width="560" height="315" src="https://www.youtube.com/embed/0mNdR8Xo3ho" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
 </p>
 
In [Lesson 1](./lesson1.md) you learned how to create a simple program to solve mission M08, run the simulator and save the python program to your computer.  

In [Lesson 2](./lesson2.md) you learned how to load a python program onto the EV3 and run it to again solve mission M08 this time with a real-world robot.  

In this lesson you will solve mission M09 which is to move the food cube at the far side of the game mat into the M09 scoring area.  An example program is provided below.  Copy and paste this into [the FSS FLL Simulator](https://kmortime.github.io/gears_pybricks/public/) to try it out and then try changing it to make it work differently.

When running the example program in the simulator:
  * Notice how the print() function calls in the program are displayed in the console at the bottom of the simulator.  Try adding another print statement
  * Notice there is a wait(time_in_ms) function that can be used to pause the program.  Try change the delay to 2.5 Seconds.  Remember that 1000 mS equals 1 Second.
  * Notice the tank turn function call robot.turn(angle).  Try using both positive and negative turn angles. 
  * Try changing the speed of the robot which is the first number in the robot.drive(speed,turn_angle) function call.
  * Try solving the mission in your own unique way, perhaps without line following.  Can you make this relialble?
  * After solving the mission in your own unique way add additional robot movement to return to launch quarter circle.

Once you have modified the mission so it returns to base and have it working in the simulator, save the python program to your computer, load it into Microsoft Code Studio, download it to your EV3, and try it out.
  * Does it work the same as in the simulator?  
  * If the real-world EV3 doesn't work the same as the simulator, why do you think this is?

## Example Program For FSS FLL Lesson 3
This program moves out of the start area, follows the line to the far side of the game mat, squares up on the wall, and pushes the food block into the M09 scoring circle.


```python
#!/usr/bin/env pybricks-micropython

######################################################
# Basic setup for FSS FLL Spring Training Robot
# !!! -- DO NOT CHANGE THIS PART OF THE PROGRAM -- !!!
######################################################

# Import the necessary libraries
import math
import time
from pybricks.ev3devices import *
from pybricks.parameters import *
from pybricks.robotics import *
from pybricks.tools import wait
from pybricks.hubs import EV3Brick

ev3 = EV3Brick()
motorB = Motor(Port.B)
motorC = Motor(Port.C)
left_motor = motorB
right_motor = motorC
robot = DriveBase(left_motor, right_motor, wheel_diameter=56, axle_track=108)
robot.settings(straight_speed=200, straight_acceleration=100, turn_rate=100)

color_sensor_in1 = ColorSensor(Port.S1)

###################################
# Here is where your code starts
###################################

# Lesson #3
# FSS FLL Spring Training

# Proportional Gain for line following
pd = -0.8

# Move away from the wall without hitting it.
print("------------------------------------------")
print("Move away from the wall...")
while motorB.angle() <= 210:
  robot.drive(80, -40)
robot.stop()
left_motor.brake()
right_motor.brake()
print("MotorB has reached angle " + str(motorB.angle()))
motorB.reset_angle(angle=0)
motorC.reset_angle(angle=0)
print("------------------------------------------\n")


# Drive straight until the line following sensor is above the line
print("------------------------------------------")
print("Drive straight to line...")
while motorB.angle() <= 280:
  robot.drive(100, 0)
robot.stop()
left_motor.brake()
right_motor.brake()
print("MotorB has reached angle " + str(motorB.angle()))
motorB.reset_angle(angle=0)
motorC.reset_angle(angle=0)
print("------------------------------------------\n")

# Follow the line to the end.
print("------------------------------------------")
line_follow_rotations = 3.5
print("Follow the line for " + str(line_follow_rotations) + " rotations...")

while motorB.angle() <= line_follow_rotations * 360:
  turn_direction = pd * (color_sensor_in1.reflection() - 50)
  robot.drive(50, turn_direction)
robot.stop()
left_motor.brake()
right_motor.brake()
print("Pause for one second (1000 mSec)")
wait(1000)
print("MotorB has reached rotations of " + str(motorB.angle()/360))
motorB.reset_angle(angle=0)
motorC.reset_angle(angle=0)
robot.stop()
left_motor.brake()
right_motor.brake()
print("------------------------------------------\n")


# Turn towards the wall
print("------------------------------------------")
print("Tank Turn towards the wall...")
robot.turn(-48)
robot.stop()
left_motor.brake()
right_motor.brake()
print("MotorB has reached angle " + str(motorB.angle()))
motorB.reset_angle(angle=0)
motorC.reset_angle(angle=0)
print("------------------------------------------\n")

# Drive into wall and square up
print("------------------------------------------")
print("Drive into wall and square up...")
while motorB.angle() <= 500:
  robot.drive(50, 0)
robot.stop()
left_motor.brake()
right_motor.brake()
print("MotorB has reached angle " + str(motorB.angle()))
motorB.reset_angle(angle=0)
motorC.reset_angle(angle=0)
print("------------------------------------------\n")


# Back away from wall slightly so the robot can turn
print("------------------------------------------")
print("Back away from wall slightly so the robot can turn...")
while motorB.angle() >= -50:
  robot.drive(-80, 0)
robot.stop()
left_motor.brake()
right_motor.brake()
print("MotorB has reached angle " + str(motorB.angle()))
motorB.reset_angle(angle=0)
motorC.reset_angle(angle=0)
print("------------------------------------------\n")

# Turn 90 degrees to face towards north wall
print("------------------------------------------")
print("Tank Turn 90 degrees to face towards the north wall...")
robot.turn(90)
robot.stop()
left_motor.brake()
right_motor.brake()
print("MotorB has reached angle " + str(motorB.angle()))
motorB.reset_angle(angle=0)
motorC.reset_angle(angle=0)
print("------------------------------------------\n")

# Push block into M09 scoring circle
print("------------------------------------------")
print("Push block into M09 scoring circle...")
while motorB.angle() <= 300:
  robot.drive(100, 0)
robot.stop()
left_motor.brake()
right_motor.brake()
print("MotorB has reached angle " + str(motorB.angle()))
motorB.reset_angle(angle=0)
motorC.reset_angle(angle=0)
print("------------------------------------------\n")

```
