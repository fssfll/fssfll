---
title: Customizing the Bolton Robotics BaseCode
subtitle: How and why to make changes to bolton_robotics_robot class
---


# What is a Python "class" and why use the bolton_robotics_robot class?
In the realm of programming FLL (First Lego League) robots using Python, a class like "bolton_robotics_robot" acts as a guiding blueprint to describe and control these robots. Picture the class as a set of instructions to create a specific type of robot. 
The robot, being an instance of this class, inherits its defined features and abilities. For an FLL robot, these features, known as attributes, might include details like wheel size, wheel spacing, the number of motors, and types of sensors. Similar to how you might specify the color and model for a car, 
these attributes help tailor the robot's characteristics. 
Additionally, the class may house methods that instruct the robot on how to perform certain actions, such as line following, line squaring, or gyro assisted navigation. This systematic approach streamlines the coding process, making it easier to manage and manipulate FLL robots with precision.

# What do I need to know about the bolton_robotics_robot class?

An EV3 Robot has motor control ports A-D and sensor ports 1-4.  It is up to the robot designer <B>THAT'S YOU!</B> to decide how to use those ports.  The bolton_robotics_robot class assumes a specific configuration of the robot which is described in the comments at the top of the file.  Consider this the 'default' configuration which must be altered as needed to match your robot.

``` python
##########################################################
# bolton_robotics_robot.py
##########################################################
#
# Modify this file if Ev3 wiring differs from the the following
# default configuration:
#
# --- MOTOR WIRING ---
# Port A: left attachment motor
# Port B: left drive motor
# Port C: right drive motor
# Port D: right attachment motor
#
# --- SENSOR WIRING ---
# Port 1: left color Sensor
# Port 2: not connected
# Port 3: not connected
# Port 4: right color Sensor
#
# --- ROBOT WHEEL SIZE AND SPACING---
# wheel_diameter: 56.9mm
# axle_track: 89mm (distance between wheels)
#
##########################################################
```

If your robot differs from this configuration, read on!  We'll cover each part.

__Motor Wiring Connections__

The EV3 Robot has ports A-D for controlling either medium or large motors.  In our FLL experience, drive motors should always use ports "B" and "C" for best driving performance due to the underlying EV3 hardware architecture.  Ports "A" and "B" may optionally be connected to additional large or medium motors to power attachments or whatever else the team can dream up.  
The motor wiring connections defined in the bolton_robotics_robot.py are shown in the code below:    

``` python
        try:
            self.left_attachment_motor = Motor(Port.A)
        except: 
            self.ev3.screen.clear()
            self.ev3.light.off()
            self.ev3.light.on(Color.RED)
            self.ev3.screen.draw_text(0,40,"STARTUP ERROR")
            self.ev3.screen.draw_text(0,80,"CHECK PORT A")
            self.ev3.speaker.beep(frequency=2000, duration=1000)
            wait(4000)
            self.ev3.screen.clear()
            sys.exit()
        try:
            self.left_drive_motor = Motor(Port.B)
        except: 
            self.ev3.screen.clear()
            self.ev3.light.off()
            self.ev3.light.on(Color.RED)
            self.ev3.screen.draw_text(0,40,"STARTUP ERROR")
            self.ev3.screen.draw_text(0,80,"CHECK PORT B")
            self.ev3.speaker.beep(frequency=2000, duration=1000)
            wait(4000)
            self.ev3.screen.clear()
            sys.exit()
        try:
            self.right_drive_motor = Motor(Port.C)
        except: 
            self.ev3.screen.clear()
            self.ev3.light.off()
            self.ev3.light.on(Color.RED)
            self.ev3.screen.draw_text(0,40,"STARTUP ERROR")
            self.ev3.screen.draw_text(0,80,"CHECK PORT C")
            self.ev3.speaker.beep(frequency=2000, duration=1000)
            wait(4000)
            self.ev3.screen.clear()
            sys.exit()
        try:
            self.right_attachment_motor = Motor(Port.D)
        except: 
            self.ev3.screen.clear()
            self.ev3.light.off()
            self.ev3.light.on(Color.RED)
            self.ev3.screen.draw_text(0,40,"STARTUP ERROR")
            self.ev3.screen.draw_text(0,80,"CHECK PORT D")
            self.ev3.speaker.beep(frequency=2000, duration=1000)
            wait(4000)
            self.ev3.screen.clear()
            sys.exit()
```

Let's go ahead and change your bolton_robotics_robot.py module to match how your robot is wired.
You can easily do this by commenting out an unused connection.  To comment out a block of code in visual studio Code use the <SHIFT><ALT><A> key combination.  If you have a different mapping of motors to ports, you can likely make a simply change.  For example you could change ```python self.left_attachment_motor = Motor(Port.A)``` to be ```python self.right_attachment_motor = Motor(Port.A).```

__Sensor Wiring Connections__
The EV3 Robot has ports 1-4 for connecting to input sensors like the push button, the ultrasonic sensor, the gyro, and the color sensor.  The sensor wiring connections defined in the bolton_robotics_robot.py are shown in the code below: 
```python
        try:
            self.left_color_sensor = ColorSensor(Port.S1)
        except: 
            self.ev3.screen.clear()
            self.ev3.light.off()
            self.ev3.light.on(Color.RED)
            self.ev3.screen.draw_text(0,40,"STARTUP ERROR")
            self.ev3.screen.draw_text(0,80,"CHECK PORT 1")
            self.ev3.speaker.beep(frequency=2000, duration=1000)
            wait(4000)
            self.ev3.screen.clear()
            sys.exit()
        try:
            self.right_color_sensor = ColorSensor(Port.S4)
        except: 
            self.ev3.screen.clear()
            self.ev3.light.off()
            self.ev3.light.on(Color.RED)
            self.ev3.screen.draw_text(0,40,"STARTUP ERROR")
            self.ev3.screen.draw_text(0,80,"CHECK PORT 4")
            self.ev3.speaker.beep(frequency=2000, duration=1000)
            wait(4000)
            self.ev3.screen.clear()
            sys.exit()
```

Note that only two of the four ports are used.  As an example, perhaps you would want to add a Gyro Sensor on port 2.  You could do this by simply adding some additional code in between the definition of port 1 and port 4:

```python
        try:
            self.gyro_sensor = GyroSensor(Port.S2)
        except: 
            self.ev3.screen.clear()
            self.ev3.light.off()
            self.ev3.light.on(Color.RED)
            self.ev3.screen.draw_text(0,40,"STARTUP ERROR")
            self.ev3.screen.draw_text(0,80,"CHECK PORT 2")
            self.ev3.speaker.beep(frequency=2000, duration=1000)
            wait(4000)
            self.ev3.screen.clear()
            sys.exit()
```
Pay attention to the indenting of code for the new sensor you are defining.  It should have the same level of indentation as ports 1 and 4. 

__Wheel Size And Spacing__
You control the robot by telling it how far to drive and how much to turn like this:
```python
# Drive Forward 10 centimeters
r.robot.straight(100)

# Turn right 90 degress
r.robot.turn(90)
```

But how does the robot know how far to go or how to turn right exactly 90 degrees?

It does this by keeping track of how much the motors turn and converts this into distance with a little bit of math.  In order for the robot to convert how much the motors turn into how far the robot drives you need to tell it how big the wheels are.  Bigger wheels will make the robot drive further for every rotation of the motor when compared to smaller wheels.
The robot uses the wheels diamter in millimeters as the measure of how big the wheels are.  You can measure your wheel diameter using a ruler or you may be able to find the diameter on the internet.  Remember, to get millimeters, measure in centimeters and then multiply by 10. 

<p  align="center"><img src="../../../images/wheel_diameter.jpg" width=300></P>

In order for the robot to determine how much to spin the motors to turn it also needs to know how far apart the center of the wheels are from each other.  The robot calls this the, "axle track."  You need to measure this on your robot using a ruler.

<p  align="center"><img src="../../../images/axle_track.jpg" width=300></P>

After making the measurements, set the wheel diameter and axle_track for your robot design in the bolton_robotics_robot.py file by changing the following line:

```python
self.robot = DriveBase(self.left_drive_motor, self.right_drive_motor, wheel_diameter=56.9, axle_track=89)
```

You have now customized the base code to match you robot design!  Make sure to save the bolton_robotics_robot.py in Microsoft Visual Studio Code. 

<p align="center">
<IMG ALIGN="CENTER" SRC="https://fssfll.github.io/fssfll/images/finish.jpg">
<BR>
<B>Congratulations, you have completed the lesson!</B><BR>
<A HREF="https://fssfll.github.io/fssfll/ev3/lessons/intermediate/">Return To Intermediate Lessons</A>
<BR>
 </P>
