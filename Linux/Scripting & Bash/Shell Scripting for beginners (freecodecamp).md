[FreeCodeCamp link](https://www.freecodecamp.org/news/shell-scripting-crash-course-how-to-write-bash-scripts-in-linux/)

Shell scripting is an important part of process automation in Linux. Scripting helps you write a sequence of commands in a file and then execute them. This saves you time because you don't have to write certain commands again and again. You can perform daily tasks efficiently and even schedule them for automatic execution.

**Introduction to the Bash Shell**
When you first launch the shell, it uses a startup script located in the .bashrc or .bash_profile file which allows you to customize the behaviour of the shell.

When a shell is used interactively, it displays a $ when it is waiting for a command from the user. This is called the shell prompt.
If shell is running as root, the prompt is changed to #.

**What is a Bash Script?**
A bash script is a series of commands written in a file. These are read and executed by the bash program. The program executes line by line.
You can do the same sequence of steps by saving the commands in a bash script and running it. You can run the script any number of times.

**How do you identify a bash script?**
By naming conventions, bash scripts end with a .sh extension.
However, bash scripts can run perfectly fine without the .sh extension.
Scripts are also identified with a "shebang". Shebang is a combination of bash # and bang ! followed by the bash shell path. This is the first line of the script. Shebang tells the shell to execute it via bash shell. Shebang is simply an absolute path to the bash interpreter.
Below is an example of the shebang statement:
#! /bin/bash

**Execution rights**
An execution right is represented by x. In the example below, my user has the rwx (read, write, execute) rights for the file 'test_script.sh'
![Screenshot 2022-08-24 at 14.08.52.png](app://local/Users/pedrolamas/MEGA/Work%20directory/GitHub/learning_base/notebooks/screenshots/Screenshot%202022-08-24%20at%2014.08.52.png?1661346535852)

##### How to create your first bash script
*Let's create a simple script in bash that outputs Hello World.*

**Create a file named "hello_world.sh"**
	$ touch hello_world.sh

**Find the path to your bash shell**
	$ which bash

Include the outcome in the shebang.

**Write the command**
We will echo "hello world" to the console.
Our script will look something like this:
	```#! usr/bin/bash
	echo "Hello World"```
Edit the file "hello_world.sh" using a text editor of your choice and add the above lines in it.

**Provide execution rights to your user**
Modify the file permissions and allow execution of the script by using the command below:
	$ chmod u+x hello_world.sh
'chmod' modifies the existing rights of a file for a particular user. We are adding +x to user u.

**Run the script**
You can run the script in the following ways:
	$ ./hello_world.sh
	$ bash hello_world.sh

##### The basic syntax of Bash Scripting
**How to define variables**
We can define a variable by using the syntax ```variable_name=value```. 
To get the value of the variable, add $ before the variable.
	```#!/bin/bash
	# A simple variable example
	greeting=Hello
	name=Tux
	echo $greeting $name```
	(Tux is the name of the Linux mascot, the penguin).

**Arithmetic Expressions**
Numerical expressions can also be calculated and stored in a variable using the syntax: var=$((expression))
Example:
	```#!/bin/bash
	var=$((3+9))
	echo $var ```

Fractions are not correctly calculated using the above methods and truncated.

For decimal calculations, we can use 'bc' command to get the output to  particular number of decimal places. 'bc' (bash calculator) is a command line calculator that supports calculation up to a certain number of decimal points.

	```echo "scale=2;22/7" | bc```
Where 'scale' defines the number of decimal places required in the output.

**How to read user input**
In bash, we can take user input using the 'read' command.
	```read variable_name```
To prompt the user with a custom message, use the '-p' flag.
	```read -p "Enter your age" variable_name```
Example:
	```#!/bin/bash
	echo "Enter a number"
	read a
	echo "Enter a number"
	read b
	var=$((a+b))
	echo $var```

**Numeric comparison logical operators**
Comparison is used to check if statements evaluate to true or false.
![Screenshot 2022-08-26 at 11.33.12.png](app://local/Users/pedrolamas/MEGA/Work%20directory/GitHub/learning_base/notebooks/screenshots/Screenshot%202022-08-26%20at%2011.33.12.png?1661510009090)

Syntax:
	```if [conditions]
		then
				commands
	fi```
Let's compare two numbers and find their relationship:
	```read x
	read y
	if [$x -gt $y]
	then
	echo X is greater than Y
	elif [$x -lt $y]
	then
	echo X is less than Y
	elif [$x -eq $y]
	then
	echo X is equal to Y
	fi```

**Conditional Statements (decision making)**
Conditions are expressions that evaluate to a boolean expression (true or false). To check conditions, we can use 'if', 'if-else', 'if-elif-else' and nested conditionals.
The structure of conditional statements is as follows:
- if...then...fi statements
- if...then...else...fi statements
- if...elif...else...fi
- if...then...else...if...then...fi...fi... (nested conditionals)

Syntax:
	```if [[conditions]]
	then
		statement
	elif [[condition]]; then
		statement
	else
		do this by default
	fi```

To create meaningful comparisons, we can use AND '-a' and OR '-o' as well.

**Looping and skipping**
For loops allow you to execute statements  specific number of times.

***Looping with numbers:***
In the example below, the loop will iterate 5 times.
	```#!/bin/bash
	for i in {1..5}
	do
		echo $i
	done```

***Looping with strings:***
	```#!/bin/bash
	for X in cyan magenta yellow
	do
		echo $X
	done```

**While loop**
While loops check for a condition and loop until the condition remains 'true'. We need to provide a counter statement that increments the counter to control loop execution.
In the example below, ((i+=1)) is the counter statement that increments the value of i.
	```#!/bin/bash
	i=1
	while [[$i -le 10]]; do
		echo "$i"
		((i+=1))
	done```

**Reading files**
We can read a file line by line and print the output on the screen.
	```#!/bin/bash
	LINE=1
	while read -r CURRENT_LINE
		do
			echo "$LINE: $CURRENT_LINE"
		((LINE++))
	done < "sample_file.txt"```

**How to execute commands with back ticks**
If you need to include the output of a complex command in your script, you can write the statement inside back ticks.
Syntax:
	```var=`commands`
	```
Suppose we want to get the output of a list of mountpoints with 'tmpfs' in their name. We can craft a statement like this: 'df -h | grep tmpfs'.
To include it in the bash script, we can enclose it in back ticks.
	```#!/bin/bash
	var= df -h | grep tmpfs
	echo $var ```

**How to get arguments for scripts from the command line**
It is possible to give arguments to the script on execution.
'$@' represents the position of the parameters, starting from one.
	```#!/bin/bash
	for x in $@
	do
		echo "Entered arg is $x"
	done```
*Run like this:*
$ ./script arg1 arg2

**How to automate scripts by scheduling via cron jobs**
Cron is a job scheduling utility present in Unix like systems. You can schedule jobs to execute daily, weekly, monthly or in a specific time of the day. Automation in Linux heavily relies on cron jobs.
![Screenshot 2022-08-26 at 15.32.55.png](app://local/Users/pedrolamas/MEGA/Work%20directory/GitHub/learning_base/notebooks/screenshots/Screenshot%202022-08-26%20at%2015.32.55.png?1661524379585)
Here, * represents minute(s) hour(s) day(s) month(s) weekday(s), respectively.

Below are some examples of scheduling cron jobs:![Screenshot 2022-08-26 at 15.34.15.png](app://local/Users/pedrolamas/MEGA/Work%20directory/GitHub/learning_base/notebooks/screenshots/Screenshot%202022-08-26%20at%2015.34.15.png?1661524462883)

**How to check existing scripts in a system**
***Using crontab***
'crontab -l' lists the already scheduled scripts for  particular user.

**Using the find command**
The 'find' command helps to locate files based on certain patterns. As most of the scripts end with .sh, we can use the find script like this:
	$find . -type f -name *.sh
