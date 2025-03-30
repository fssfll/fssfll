---
title: Create Your First Program For the Lego EV3 
subtitle: Use The Bolton Robotics Base Code, Microsoft Visual Studio, and Program the EV3 Robot
---

# Review Your Robot Connections
If you have not already done so, confirm your robot port wiring, wheel diameter, and wheel track matches the configuration in bolton_robotics_robot.py

If your robot doesn't match the configuration, you will likely not be able to complete this training module.  Use the [Customizing Your Robot](../../ev3_customizing/ev3_customizing) training module to determine how to update bolton_robotics_robot.py to match your robot.

# Training Video
First watch the video below which completes all the steps in this training module.

<p align="center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/HHKFDaXsVDk?si=dgz-9sqzHqFWsJgO" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</p>


# Create and Test Your Program
The instructions below follow the training video above.

- Open up Microsoft Visual Studio Code and Load the Bolton Robotics Base Code
- Select the mission_one.py file
- Modify the code to make your robot drive straight and then turn.  Make sure keep the same level of indentation:

```python
################################
# mission_one.py
################################

import math
import time
from pybricks.ev3devices import *
from pybricks.parameters import *
from pybricks.robotics import *
from pybricks.iodevices import *
from pybricks.tools import wait
from pybricks.hubs import EV3Brick
from robot_18300 import robot_18300

def mission_one(r):
    print("Running Mission 1")
    ##########################
    # My First Python Program
    ##########################
    # Drive Straight 10 centimeters
    r.robot.straight(100)
    # Turn right 90 degrees
    r.robot.turn(90)
```

- Use the EV3DEV device browser to Connect to your robot
- Select "Run and Debug" and "Start Debugging" to both download and then the bolton robotics base code
- Use the EV3 buttons to select and run mission 1
    
# Why is there an "r." at the beginning of the robot commands? 
You may have noticed in the training video the instructions to make the robot drive straight and turn are preceeded with "r." like this:  

```python
# Drive Straight 10 centimeters
r.robot.straight(100)
# Turn right 90 degrees
r.robot.turn(90)
```

This is because in main.py, the robot is "instantiated" and given the name "r" as shown in the python code below:

```python
# Instantiate the Robot
r = bolton_robotics_robot()
```

When we talk about instantiation, we're essentially talking about creating an object from a class.  In this case we're creating the robot "r" from the class bolton_robotics_robot. Remember a class is like a blueprint for your robot. When you want to bring that robot to life and actually use it, you need to create an instance of that class, and that's where instantiation comes in.

<p align="center">
<IMG ALIGN="CENTER" SRC="https://fssfll.github.io/fssfll/images/finish.jpg">
<BR>
<B>Congratulations, you have completed the lesson!</B><BR>
<A HREF="https://fssfll.github.io/fssfll/lessons/intermediate/">Return To Intermediate Lessons</A>
<BR>
 </P>
