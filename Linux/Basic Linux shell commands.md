**whoami -** use this command to check which user you are. 

**pwd -** the present working directory command informs you of where you currently are in the directory tree. by default this usually is the home directory. If you are a beginner, it's quite normal to be lost in the directory tree and sudeenly lose track of where you are. This command helps you to keep track of things.

**ls -** command to list the contents of a directory. When used with flags, it's a swiss army knife.
Common flags you might want to take note of are -l (long listing), -a (show hidden files), and -c (show recently modified).

**cd -** you use the Change Directory (cd) command to transverse across the directory tree.

**How to use the 'cat', 'more', and 'less' commands**
All the commands above are output commands. You use them to display the content of files to the terminal.
*'cat'* is commonly used for files with small amounts of text.
*'less'* and *'more'* are likely to be used for files with large amounts of text and output can be controlled with the arrow keys.

**How to use the 'touch' command**
You use the touch command to create files. 
You can make a file using the following syntax: touch <file_name>

**How to use the 'nano' command**
Nano is a popular built-in text editor in Linux. It's very common because it's easy to use and it's supported in many CLI environments. Other common text editor is Vim.
You can edit a file with the following command: nano <file_name>
The nano command is used by hackers to change information in files, edit logs, or if you are a Red Hat hacker, delete essential configuration file lines.

**Command chaining operators**
'Chaining' commands is the concept of writing multiple commands together and executing them in a variety of ways. You usually do this with the use of special characters. Examples include:
1. Ampersand (&) : to run a program in the background.
2. Logical AND (&&) : the following command will run only if the previous one successfully ran.
3. Pipe (|) : the output of the previous command acts as input for the next command.
4. Overwrite (>) : overwrites the content of a file with the output of the previous one.
5. Append (>>) : appends the output from the previous command to a file.

**How to use the 'mv' and 'cp' commands**
You use 'mv' to move a file to another location. you use 'cp' to copy a file to another location.
	mv <file_name>
	cp <file_name>

There isn't a command for renaming files in Linux, so most people use the 'mv' command: mv <original_file_name> <new_file_name>

**How to use the 'mkdir' command**
The 'mkdir' command makes directories. You could use this to make a custom directory that only you can access on a compromised system to keep scripts or tools for persistence. 
	mkdir <directory>

**How to use the 'rm' and 'rmdir' commands**
'rm' is the command to remove files, and 'rmdir' is the command to remove directories. 
	rm <file_name>
	rmdir <directory>
Linux i not too keen on getting folders deleted if they are not empty. To account for this, use the 'ignore-fail-if-non-empty' flag to delete both files and directories.
You'll need to be extremely careful with these commands as they do not send the deleted files or directories to the Trash/Recycle bin.

**How to use the 'stat' command**
You use the stat command to give information about a file.
	stat <file_name>
You can gather information about the file name and extension, permissions, when it was made, modified, last accessed and much more.

**How to use the 'echo' command**
You use the 'echo' command to print out input. Let's use an example to make things clearer.
	echo "<text>"
You can use echo with the > operator to write text to files:
	echo "This is a rondom string" > new_file.txt

**How to use the 'grep' command**
You use the 'grep' command to extract specified text from a file using the pipe operator.
	grep "<text>"
	
	cat random_file.txt | grep "cyber"
We tell the computer to print the contents of a file, and using the pipe operator, tell the 'grep' command to use it as input. This is called piping one command through another and can be done multiple times.
'grep' is commonly used to look for certain texts in large files. A practical example would be if you are looking for credentials for a specific user in a file with a lot of text. You could use 'grep' to look for words like "password", "login" and other keywords that you think would be around the credentials you are looking for.

**How to se the 'help' flag and 'man' pages**
The 'help' flag isn't necessarily a command but it is a great aid if you are confused about an app or tool.
	<app or tool> --help

'Man' gives you all documented information about the app.
	man <app>








