---
title: Pybricks IDE and Bolton Robotics Base Code
subtitle: Learn the basics of the Pybricks IDE and the Bolton Robotics Base Code
---

# What is the Bolton Robotics Base Code?

Bolton Robotics Base Code is a set of starter Python files that help students quickly set up and start solving FIRST Lego League Challenges. It provides a simple framework so students can focus more on programming and problem-solving. Here’s what makes it great:

__Foundation for Success:__

The base code includes a ready-made robot class that sets up important details like motor ports, sensor connections, and wheel size. This gives students a solid and organized starting point for their robot projects.

__Ease of Configuration:__

Since the base code already includes key hardware settings, students can configure their robots quickly without worrying about complicated details. This means they can spend more time programming and less time setting things up.

__Program Selection Interface:__

One of the best features is the program select menu. This lets students easily pick from up to 9 different programs they’ve written for different challenges. It makes switching between programs simple and convenient.

__Efficient Problem Solving:__

The goal of the base code is to speed up the coding process so students can focus on solving problems. With a pre-defined robot class and an easy-to-use menu, students can quickly test ideas, experiment, and improve their solutions—key skills for success in Lego League!

In short, the Bolton Robotics Base Code helps students spend less time on setup and more time being creative and solving challenges. It’s a tool designed to make learning robotics faster, easier, and more fun!

# How Do I Get the Base Robot Code?
- Visit the GitHub repository where the Bolton Robotics Base Code is hosted: [Bolton Robotics Base Code Repository](https://github.com/fssfll/spike_basecode).
- On the GitHub page, click on the "Code" button and then select "Download ZIP" to download the entire project as a ZIP file.
- Extract the downloaded ZIP file to a location on your computer.
- Open Visual Studio Code and navigate to the folder where you extracted the Base Code.
- Open the folder in Visual Studio Code.

# What do the files I downloaded do?

__Code Structure__
The Bolton Robotics Base Code is composed of different python files, each responsible for a different function as shown in the graphic below:
<p  align="center"><img src="../../../images/spike_basecode.jpg" width=600></p>

__[main.py](https://github.com/fssfll/spike_basecode/blob/main/main.py)__
<BR>
This is the main python file which instantiates the robot class, initializes the robot, and starts the menu.  When starting out, you should not have to modify this module. 

__[mission_one.py](https://github.com/fssfll/spike_basecode/blob/main/mission_one.py) to [mission_nine.py](https://github.com/fssfll/spike_basecode/blob/main/mission_nine.py)__
<BR>
This is where you tell the robot what to do!  These 9 files are where the code to make the robot move and solve missions goes.  This is setup to allow for multiple students to work in parallel.  While one student works in mission_one.py to solve FLL mission(s) other students could be working in one or more of the other eight mission python files. 

__[menu.py](https://github.com/fssfll/spike_basecode/blob/main/menu.py)__
<BR>
This module creates the 9 mission selector menu system.  When starting out, you should not have to modify this module.       

__[bolton_robotics_robot.py](https://github.com/fssfll/spike_basecode/blob/main/bolton_robotics_robot.py)__
<BR>
This module sets up a robot class that includes key details about your robot, like motor connections, sensor ports, and wheel size. The settings in this file must match your actual robot! If your robot’s wiring and setup match what’s already in the file, you don’t need to change anything. If your robot is different, don’t worry—we’ll go over how to customize this Python file in a later training module.

<p align="center">
<IMG ALIGN="CENTER" SRC="https://fssfll.github.io/fssfll/images/finish.jpg">
<BR>
<B>Congratulations, you have completed the lesson!</B><BR>
<A HREF="https://fssfll.github.io/fssfll/spike/lessons/intermediate/">Return To Intermediate Lessons</A>
<BR>
 </P>
