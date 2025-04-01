---
title: Pybricks IDE and Bolton Robotics Base Code
subtitle: Learn the basics of the Pybricks IDE and the Bolton Robotics Base Code
---

# What is the Bolton Robotics Base Code?

The Bolton Robotics Base Code is a set of starter python files that serves as a streamlined framework, expediting the process for students to initiate and tackle FIRST Lego League Challenges efficiently. Here are some of the great features of the base code.

__Foundation for Success:__

The base code establishes a foundational robot class. Within this class, critical elements such as motor port connections, sensor port connections, and wheel size are predefined. This groundwork provides a standardized and organized starting point for students.

__Ease of Configuration:__

By encapsulating key hardware configurations within the robot class, students can swiftly configure their robots without delving into intricate details. This simplification accelerates the setup process, allowing students to focus more on coding solutions.

__Program Selection Interface:__

A notable feature is the program select menu interface. This user-friendly menu empowers students to choose from a selection of up to 9 programs they've created to address specific challenges. This streamlined interface enhances accessibility and facilitates easy navigation between different solutions.

__Efficient Problem Solving:__

The overarching goal is to expedite the development cycle. With the base code in place, students can dive straight into coding and problem-solving, leveraging the pre-defined robot class and the intuitive program select menu. This efficiency encourages experimentation and iteration, key elements in mastering Lego League Challenges.
In essence, the Bolton Robotics Base Code acts as a supportive scaffold, allowing students to focus on the creative and problem-solving aspects of FIRST Lego League Challenges without being bogged down by repetitive setup tasks. It's a tool designed to accelerate learning and foster a hands-on, exploratory approach to robotics.

# How Do I Get the Base Robot Code?
- Visit the GitHub repository where the Bolton Robotics Base Code is hosted: [Bolton Robotics Base Code Repository](https://github.com/fssfll/spike_basecode).
- On the GitHub page, click on the "Code" button and then select "Download ZIP" to download the entire project as a ZIP file.
- Extract the downloaded ZIP file to a location on your computer.
- Open Visual Studio Code and navigate to the folder where you extracted the Base Code.
- Open the folder in Visual Studio Code.

# What do the files I downloaded do?

__Code Structure__
The Bolton Robotics Base Code is composed of different python files, each responsible for a different function as shown in the graphic below:
<p  align="center"><img src="../../../images/bolton_robotics_code.jpg" width=600></p>

__[main.py](https://github.com/fssfll/fll_basecode/blob/main/main.py)__
<BR>
This is the only python file used to run the code (this is the one you would select and run on the EV3).  When starting out, you should not have to modify this module. 

__[mission_one.py](https://github.com/fssfll/fll_basecode/blob/main/mission_one.py) to [mission_eight.py](https://github.com/fssfll/fll_basecode/blob/main/mission_eight.py)__
<BR>
This is where you tell the robot what to do!  These 8 files are where the code to make the robot move and solve missions goes.  This is setup to allow for multiple students to work in parallel.  While one student works in mission_one.py to solve FLL mission(s) other students could be working in one or more of the other seven mission python files. 

__[menu.py](https://github.com/fssfll/fll_basecode/blob/main/menu.py)__
<BR>
This module creates the 8 mission selector menu system.  Use the center button to change from missions 1-4 to missions 5-8.  When starting out, you should not have to modify this module.       

__[bolton_robotics_robot.py](https://github.com/fssfll/fll_basecode/blob/main/bolton_robotics_robot.py)__
<BR>
This module creates a robot class which defines important pieces of how your robot is designed like motor connections, sensor connection, and wheel size.  The configuration defined in this file must match your robot!  If your robot wiring and configuration matches what is defined in here you don't need to change anything.  If your robot is different, we'll cover how to customize this python file in a subsequent training module.   

<p align="center">
<IMG ALIGN="CENTER" SRC="https://fssfll.github.io/fssfll/images/finish.jpg">
<BR>
<B>Congratulations, you have completed the lesson!</B><BR>
<A HREF="https://fssfll.github.io/fssfll/spike/lessons/intermediate/">Return To Intermediate Lessons</A>
<BR>
 </P>
