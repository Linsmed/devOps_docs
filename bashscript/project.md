### Bash scripting
- shell is a command line interpreter that forward our human readable commands to operating system

- we have different types of shell, but we will be using bash here with the full meaning Bourne Again Shell

- now create a file with vim or any editor of your choi ce:
`vim our_first_script

#### POSITIONAL PARAMETERS BRIEF PROJECT 
- You have been asked to create a bash script that will serve as a basic calculator and
allow you to perform simple arithmetic calculations from the command line.
The calculator needs to be able to do addition, subtraction, multiplication and
division, on a maximum of 9 numbers.
The first command line argument given to the script will contain the operation that is
to be performed on the numbers (either + or -).
The operation chosen will be applied to all the numbers.
For example, if the first command line argument is “+”, then all the other command
line arguments will be added together. If the user picks “-”, then all the other
command line arguments will be subtracted from each other, and so on.
Your script needs to be able to accept the operation as the first command line
argument, and also accept up to 9 numbers (for a total of 10 command line
arguments)

- ### SOLUTION
- Use vim editor or any editor of your choice to make a file named calculator.sh

`vim calculator.sh`

- The command should be like this:
![project](../bashcourse/images/project-1.PNG)

- give the file executable permission

`chmod 744 calculator.sh"

` run the script:
`./calculator.sh + 15 10 5`

![](../bashcourse/images/addition.PNG)

![](../bashcourse/images/arithmetic.PNG)




