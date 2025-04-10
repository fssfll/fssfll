---
title: The robot doesn't work. What now?!? 
subtitle: How to debug your code
---


## Tools you can use to debug your code

### Code Comments
  * A code comment is a text note added to source code to provide information, usually about the function of the code.
  * A comment in Python starts with the hash character, # and extends to the end of the line.
  * An example Python comment is shown below

```python
# This entire line is a Python comment
# Comments are a great way to let other people know how your program works

# You can also use comments to remove one or more lines of code from you program.
# This can be helpful when debugging your program.
# For example, the following line starts with the hash character, # so it is a comment:
# robot.turn(90)

# Removing the hash chararcter turns it into a line of code to be executed:
robot.turn(90)
```

### Print Function: print()
  * Print function calls can be added to your code to display messages to the console.
  * The console is where you can view the results of commands and status like the print() function.
  * In the simulator the console is located at the bottom of the screen and can be expanded by clicking on the inverted "V" (this is called a chevron)
   * In some cases, like when using the simulator or when using Pybricks IDE these can be used to display helpful information about what your code is doing.
  * You print text with the print function by including it in quotes like this:
```python
# A simple text print message
print("Hello World.")
```
  * Print statements can be more advanced like in the example below.
  * A plus sign, + can be used to join variables, text and other elements together.
  * The variable speed is a number and is converted to a text string for printing using the str() function
```python
# Set the variable speed equal to 200
speed = 300
# Print the value of the variable speed
print("Speed= " + str(speed) + " mm/Second")
```

### The wait() Method
  * The wait() method can be used to pause your program for a period of time before continuing
  * The wait() method takes an input time in milliseconds
  * Remember there are 1000 milliseconds in one second.
  * As an example, if you wanted to pause your program for 3.5 seconds you would do the following:
 ```python
 print("The program has started")
 print("Now pausing the program for 3.5 seconds")
 wait(3500)
 print("The program continues...")
 ```


<p align="center">
<IMG ALIGN="CENTER" SRC="https://fssfll.github.io/fssfll/images/finish.jpg">
<BR>
<B>Congratulations, you have completed the lesson!</B><BR>
<A HREF="https://fssfll.github.io/fssfll/spike/lessons/beginner/">Return To Beginner Lessons</A>
<BR>
 </P>
