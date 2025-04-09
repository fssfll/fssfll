---
title: Pybricks IDE and Bolton Robotics Base Code
subtitle:
---
# Lesson Video
<p align="center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/V_ngygF9Qgw?si=StNU3at02a4lljdg" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</p>

# What is the Bolton Robotics Base Code?
The Bolton Robotics Base Code is a set of starter Python files designed to help students quickly get their Spike robot ready for FIRST Lego League challenges. It includes a pre-made robot class that handles things like motor ports, sensor setup, and wheel size, so you don’t have to start from scratch. This saves time and lets you focus more on solving problems and writing code. The base code also has a simple menu that lets you choose from up to nine programs, making it easy to switch between different tasks during practice or competition. Overall, it’s a helpful tool for getting organized, experimenting with ideas, and building smarter solutions faster.

# How Do I Get the Base Robot Code?
- Visit the GitHub repository where the Bolton Robotics Base Code is hosted: [Bolton Robotics Base Code - Release 1](https://fssfll.github.io/fssfll/spike/lessons/spike_basecode/spike_basecode-release_1.zip)  
- On the GitHub page, click on the "Code" button and then select "Download ZIP" to download the entire project as a ZIP file.
- Extract the downloaded ZIP file to a location on your computer and extract the contents.
- Open Pybricks IDE or go to [code.pybricks.com](code.pybricks.com), click the "Import a file" icon, navigate to the folder where you extracted the Base Code, and add all the python files.

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
