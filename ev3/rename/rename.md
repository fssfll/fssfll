# FSS FLL: Renaming The EV3 Robot

In a classroom environment where the bots are wirelessly programmed it is important that each EV3 robot be given a unique name.  A unique name prevents name conflicts allowing students to easily recognize which bot they should select in Visual Studio Code.  A room full of EV3 bots all named 'ev3bot' would present some challenges!

Forunately, it is easy to rename the EV3 using Visual Studio Code.  Follow the instructions and video tutorial below to change the name on your robot.

<p align="center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/ko7NHG5gh2o" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</p>

__Procedure:__
- Connect to your EV3 bot using Visual Studio Code like shown in Lesson #2
- Right click on the name of the robot listed next to the green circle and then click "Open SSH Terminal"
- A ssh session will start in which you edit the text file containing the ev3 name.  To do this type: 
   ```code
  sudo nano /etc/hostname
   ```
- Enter the password 'maker' (do not type the quotes)
- Delete the ev3dev name and replace it with your new unique robot name.  Only use numbers and letters.  Do not use symbols or spaces!
- Type <CTRL>x to exit.  When prompted if you want to save the file type Y
- Press <ENTER> to return to the prompt
- Type exit to end the ssh session
- Reboot the EV3.  Next time the EV3 powers up it will have the newly selected name.  This name will be what is displayed when you try to connect in Visual Studio Code
  
__Alternate Approach:__
The approach described above is recommended however, it is possible to change the name of the EV3 robot using a python program.  The user would first have to change permissions of the hostname file.
This can be accomplished by ssh'ing into the EV3 robot using Visual Studio Code and issuing the following command:
  ```code
  sudo chmod 777 /etc/hostname
  ```
  Then a procedure like the python code snippet below could be used to modify the EV3 robot name:
  ```python
  # Write a new hostname
  ev3_name = "anewname\n"
  file_handler = open("/etc/hostname", "w")
  for line in ev3_name:
      file_handler.write(line)
  file_handler.close()
  ```

  __Reading the EV3 Robot name:__
It may be useful for a student to readback and display the ev3 robot name.  The student could print this to the console for debugging,  use the display, or have the robot speak the name.  
  This can be accomplished with the routine in the following code snippet:
```python
# Read the hostname
try:
        file_handler = open("/etc/hostname", "r")
        ev3_name = file_handler.readlines()
        file_handler.close()
        print(ev3_name)
except OSError:
        print("Oops.  File does not exist")
```
