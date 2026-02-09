---
title: Squaring Up The Robot On A Mission Model 
subtitle: Learn how to square up on the mission model to improve robot consistency.
---

# What is the problem?
EV3 robots (both real world and virtual) hardly ever do the same thing every time.  This is because there are slight variations in how the robot is started, wheel pre-loading, friction and many other factors that result in the robot driving a little more left, right, further, not as far even when the same program is run.  

Anyone who has competed in FLL knows this can be __super frustrating__!  

Fortunately, there are tricks to improve your chances of success even when the robot goes a little off course.  There's a clever maneuver known as "squaring up." Essentially, it involves the robot purposefully driving into the mission model to nail that perfect alignment. To up the robot's game, teams often design in a funnel-like attachment. This contraption acts as a friendly guide, making sure the robot stays on track and hits the mark, even if it had veered a bit off course. With this setup, the robot becomes more consistent in competition.

__Example funnel aligmnent attachment on a real world EV3 robot:__
<p  align="center"><img src="../../../images/alignment_funnel.jpg" width=300></P>

__Example funnel aligmnent attachment on a virtual EV3 robot:__
<p  align="center"><img src="../../../images/alignment_funnel_sim.jpg" width=300></P>

# Your Challenge
Your challenge is to determine how much a funnel alignment attachment might improve robot consistency.  To help you determine this, you are going to solve the Bolton Robotics 3 Towers virtual robot game.  In this game, your goal is to create a python program so the robot drives from the launch area and knocks over the green scoring tower without knocking over either of the two red penalty towers:
<p  align="center"><img src="../../../images/towers.jpg" width=300></P>

__Attempt to solve the mission using just the accuracy of the virtual robot__

Use the simulator to come up with a simple robot program that drives down the road and attempts to knock over the scoring tower.  After you have the program able to sometimes knock over the green scoring tower (it probably won't work every time) stop changing your program.  
- Run your program 10 times and record how many times you were able to knock over the green tower and leave the two red towers standing.

[Launch the 3 Tower Challenge - without funnel attachment](https://fssfll.github.io/gears/public/index.html?worldJSON=https%3A%2F%2Ffssfll.github.io%2Ffssfll%2Fev3%2Flessons%2Fmechsquare%2Fmechsquareworld.json&robotJSON=https%3A%2F%2Ffssfll.github.io%2Ffssfll%2Fev3%2Flessons%2Fmechsquare%2Fwithoutguiderobot.json)

__Add A Funnel Attachment to improve accuracy__

Copy or recreate the same program using the link below. This link is the same 3 tower challenge with an potentially improved robot that adds a funnel alignment guide.  
- Like before, run your program 10 times and record how many times you were able to knock over the green tower and leave the two red towers standing.

[Launch the 3 Tower Challenge - with funnel attachment](https://fssfll.github.io/gears/public/index.html?worldJSON=https%3A%2F%2Ffssfll.github.io%2Ffssfll%2Fev3%2Flessons%2Fmechsquare%2Fmechsquareworld.json&robotJSON=https%3A%2F%2Ffssfll.github.io%2Ffssfll%2Fev3%2Flessons%2Fmechsquare%2Fwithguiderobot.json)

# Think About The Results
- How many times out of 10 did you solve the mission with and without the funnel attachment?  
- Did the funnel attachment help?  Why or why not?
- If you could change the funnel attachment, what would you do to make the robot solve the mission more consistently?

# A Word of Caution
If your python program uses something like robot.straight(500) to drive the robot 50 cm into the mission model and square up you may run into a problem where the robot stops once it hits the mission model and does not continue to execute your program.
- Why do you think this is? (hint: wheel stall)
- What is a way to solve it? (hint: drive using time not distance)


<p align="center">
<IMG ALIGN="CENTER" SRC="https://fssfll.github.io/fssfll/images/finish.jpg">
<BR>
<B>Congratulations, you have completed the lesson!</B><BR>
<A HREF="https://fssfll.github.io/fssfll/ev3/lessons/beginner/">Return To Beginner Lessons</A>
<BR>
 </P>
