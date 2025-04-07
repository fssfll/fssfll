---
title: Create Your First Program For the Lego Spike Robot
---

# Review Your Robot Connections
If you have not already done so, confirm your robot port wiring, wheel diameter, and wheel track matches the configuration in bolton_robotics_robot.py

If your robot doesn't match the configuration, you will likely not be able to complete this training module.  Use the [Customizing Your Robot](../../spike_customizing/spike_customizing) training module to determine how to update robot.py to match your robot.

# Training Video
First watch the video below which completes all the steps in this training module.

<p align="center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/HHKFDaXsVDk?si=dgz-9sqzHqFWsJgO" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</p>


# Create and Test Your Program
The instructions below follow the training video above.

- Open up the Pybricks IDE and Load the Bolton Robotics Base Code
- Select the mission_one.py file
- Modify the code to make your robot drive straight and then turn.  You can copy in the example code below if you are stuck.

```python
################################################################################
# mission_one.py
#
# Description:
# [Describe What your mission does here]
#
# Author(s): [Your Name(s)]
# Date: [YYYY-MM-DD]
# Version: 1.0
#
# Dependencies:
# - robot
# - pybricks.tools
#
################################################################################
from robot import robot
from pybricks.tools import wait, StopWatch

def mission_one(r):
    print("Running Mission 1")
    # Drive Straight 10 centimeters
    r.robot.straight(100)
    # Turn right 90 degrees
    r.robot.turn(90)

################################
# KEEP THIS AT THE END OF THE FILE
# This redirects to running main.
################################
if __name__ == "__main__":
    from main import main
    main()
```

- Click the Bluetooth Icon and connect to your robot (make sure you pick the right robot if there is more than one listed!)
- Click the triangle to send your code to the robot
- Use the Spike buttons to select and run mission 1

<BR><BR>
    
# You may be wondering... Why is there an "r." at the beginning of the robot commands? 
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
r = robot.robot()
```

When we talk about instantiation, we're essentially talking about creating an object from a class.  In this case we're creating the robot "r" from the class robot. Remember a class is like a blueprint for your robot. When you want to bring that robot to life and actually use it, you need to create an instance of that class, and that's where instantiation comes in.

<p align="center">
<IMG ALIGN="CENTER" SRC="https://fssfll.github.io/fssfll/images/finish.jpg">
<BR>
<B>Congratulations, you have completed the lesson!</B><BR>
<A HREF="https://fssfll.github.io/fssfll/spike/lessons/intermediate/">Return To Intermediate Lessons</A>
<BR>
 </P>
