---
title: Wall Following 
subtitle: Learn how to follow the wall to improve robot consistency.
---

# What is the problem?
As described in the squaring up on mission modules lesson, EV3 robots (both real world and virtual) hardly ever do the same thing every time.  

The inconsistency can be __super frustrating__!  

Fortunately, there are tricks to improve your chances of success even when the robot goes a little off course.  There is a a cool trick called "wall following." It's like the robot's way of hugging the wall and gliding alongside it. This move is a good strategy to keep the robot super accurate.

Typically, a good wall following design will be an attachment that holds the robot away from the wall by some amount.  The pieces in contact with the wall should be smooth and either angled or rounded at the front in case the wall is not perfectly flat.

An important part of wall following is to make sure the robot is always in contact with the wall.  This is typically accomplished by turning slightly into the wall.  For example, if the wall is on the left, have the robot turn slightly left to maintain contact like this:

```python
# Drive forward with speed of 250 and turn left -5 for 7.5 seconds
robot.drive(250,-5)
wait(7500)
robot.stop()
```

__Example wall following attachment on a virtual EV3 robot:__
The wall following attachment which contacts the wall is shown in red.
<p  align="center"><img src="../../../images/wallfollowing_robot.jpg" width=300></P>

# Your Challenge
Your challenge is to determine how much wall following could help to improve robot consistency and accuracy.  To help you determine this, you are going to solve the Bolton Robotics Bolwing virtual robot game.  In this game, your goal is to create a python program so the robot drives from the launch area, pushes a bowling ball, and knocks over as many bowling pins as possible.  It may not be as simple as it seems!  The virtual robot behaves like a real world EV3 robot and won't do the same thing every time.  

In First Lego League, the game table itself may not be setup the same every time, sometimes the table is not perfectly flat or level.  To help prepare you for this, the middle part of the virtual Bowling alley wobbles!:
<p  align="center"><img src="../../../images/bowling_game.jpg" width=300></P>

__Attempt to solve the mission using just the accuracy of the virtual robot__

Use the simulator to come up with a simple robot program that pushes the bowling ball and attampts to knock over as many pins as possible.  After you have the program able to sometimes knock over some pins (it probably won't work every time) stop changing your program.  
- Run your program 3 times and record how many times you were able to knock over all the pins.

[Launch the Bowling Challenge - without wall following](https://fssfll.github.io/gears/public/index.html?worldJSON=https%3A%2F%2Ffssfll.github.io%2Ffssfll%2Fev3%2Flessons%2Fwallfollow%2Fbowling_world.json)

__Add a wall following attachment to improve accuracy__

Now let's try again with a potentially better robot. The link below is the same virtual bowling challenge but now uses a robot that adds a wall following attachment.  
- Like before, run your program 3 times and record how many times you were able to knock over the green tower and leave the two red towers standing.
- Hint: Now that you can wall follow, how far could the robot go?  Could it make it to the where the bowling alley narrows or maybe even much further?

[Launch the Bowling Challenge - with wall following](https://fssfll.github.io/gears/public/index.html?worldJSON=https%3A%2F%2Ffssfll.github.io%2Ffssfll%2Fev3%2Flessons%2Fwallfollow%2Fbowling_world.json&robotJSON=https%3A%2F%2Ffssfll.github.io%2Ffssfll%2Fev3%2Flessons%2Fwallfollow%2Fwallfollow_robot.json)

# Think About The Results
- How many times did you solve the mission with and without the the wall following attachment?  
- Did the wall following attachment help?  Why or why not?
- If you could change the wall following attachment, what would you do to make the robot solve the mission more consistently?

# A Word of Caution
The FLL competition table walls are not flat or smoothe.  They often have bumps, notches, and other inconsistencies which a wall following robot might get stuck on.  To avoid this, use an angled beam, or other curved smoothe surface for the part(s) that touch the wall.  

Also, for best results, the wall follower parts contacting the wall should be slightly in front of the robot.
- Why do you think this is?

<p align="center">
<IMG ALIGN="CENTER" SRC="https://fssfll.github.io/fssfll/images/finish.jpg">
<BR>
<B>Congratulations, you have completed the lesson!</B><BR>
<A HREF="https://fssfll.github.io/fssfll/ev3/lessons/beginner/">Return To Beginner Lessons</A>
<BR>
 </P>
