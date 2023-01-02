https://www.freecodecamp.org/news/command-line-for-beginners/#differencebetweenconsolecommandlinecliterminalandshell

Command Line is also known as the CLI, console, terminal or shell.

**Difference between console, command line (CLI), terminal and Shell**
_Console:_ is the physical device that allows you to interact with the computer. It's your computer screen, keyboard, and mouse. As a user, you interact with your computer through your console.

_Terminal:_ is a text input and output environment. It is a program that acts as a wrapper and allows us to enter commands that the computer processes.
It's the "window" in which you enter the actual commands your computer will process.
Keep in mind the terminal is a program, just like any other.

_Shell:_ a shell is a program that acts as command-line interpreter. It processes commands and outputs the results. It interprets and processes the commands entered by the user.
Different shells come with different syntax and characteristics as well.
In Linux and Mac operating systems the default shell is Bash. While on Windows it's Powershell. Some other common examples of shells are Zsh and Fish.
Shells work also as programming languages, in the sense that with them we can build scripts to make our computer execute a certain task. Scripts are nothing more than a series of instructions (commands) that we can save on a file and later on execute whenever we want.
Also keep in mind that the terminal is the program in which the shell will run. But both programs are independent. That means, I can have any shell run on any terminal. There's no dependance between both programs in that sense.

_Command Line or CLI (Command line Interface):_ the CLI is the interface in which we enter commands for the computer to process. 
This is practically the same as the terminal.

Being comfortable with the command line will help you save time and be able to execute your tasks quicker.

By using commands you can easily automate tasks. This is incredibly useful when dealing with repetitive tasks that we don't want to do over and over again.

Scripting is a great way to save up time with repetitive tasks.

Sometimes the CLI will be the only way in which we'll be able to interact with a computer. Take, for example, the case when you would need to interact with a cloud platform server. In most of these cases, you won't have a GUI available, just a CLI to run commands in.

**How do I know what shell I'm running?**
Open your terminal and enter `echo $0`. 

- Bash is the most widely used and comes installed by default on Mac and Linux.
- Zsh is very similar to Bash, but it was created after it and comes with some nice improvements over it.

The fact that shells add more features makes them easier and friendlier to interact with, but slower to execute scripts and commands.
Shells are customizable. You can edit how the program works, what commands you have available, what information your prompt shows, and more.
Also, there are many plugins available online that allow you to customize your shell in an easier way. Some examples are OhMyZsh and Starship.

These customization options are also true for Terminals.

**Most common and useful commands to use**
_(based on Bash on a Linux OS)_

- **_Echo_** prints in the terminal whatever paramater we pass it.

- **_pwd_** stands for print working directory and it prints the directory we are currently.

- **_ls_** presents the contents on the directory we are currently in. It will present you with both the files and other directories your current directory contains.
	- If you pass this command the flag or parameter '-a', it will also show you hidden files or directories.

- **_cd_** is short for Change Directory, and it will take you from your current directory to another.
	- If you want to go up one directory, meaning go to the directory that contains the current directory, you can enter 'cd ..'

- **_mkdir_** stands for make directory and it will create a new directory for you. You have to pass the command the directory name parameter.
	- If you want to create a new directory called "Test", you would enter 'mkdir test'.

- **_rmdir_** stands for Remove Directory and it does just that. 'rmdir test'.

- **_touch_** allows you to create an empty file in your current directory. As parameters it takes the file name, like 'touch test.txt'.

- **_rm_** allows you to delete files, `rm test.txt`.

- **_cp_** allows you to copy files or directories. This command takes two parameters: the first one is the file or directory you want to copy, and the second one is the destination of your copy (where do you want to copy your file/directory to).
	- If I want to make a copy of my txt file in the same directory, I can enter the following: `cp test.txt testCopy.txt`
	- If I wanted to copy the file into a different directory, but keep the same file name, I can enter this: `cp test.txt ./testFolder/`
	- And if I wanted to copy to a different folder changing the field name, of course I can enter this: `cp test.txt ./testFolder/testCopy.txt`

- **_mv_** is short for move, and lets us move a file or directory from one place to another. That is, create it in a new directory and delete it in the previous one. Again, this command takes two parameters, the file or directory we want to move and the destination. `mv test.txt ./testFolder/`
	- We can change the name of the file too in the same command if we want to: `mv test.txt ./testFolder/testCopy.txt`

##### Git commands
- **_git init_** will create a new local repository for you.
- **_git add_** adds one or more files to staging. You can either detail a specific file to add to staging or add all changed files by typing `git add .`
- **_git commit_** commits your changes to the repository. Commits must always be accompanied by the -m flag and commit message. `git commit -m 'this is a test commit'`
- **_git status_** tells you what branch are you currently on and whether you have changes to commit or not.
- **_git clone_** allows you to clone (copy) a repository into the directory you're currently in. Keep in mind you can clone both remote repositories (GitHub) and local repositories (stored in your computer).
- **_git remote add origin_** is used to detail the URL of the remote repoitory you're going to use for your project. In case you'd like to change it at some point, you can do it by using the command "git remote set-url origin": `git remote add origin https://......`. 
   Keep in mind you need to create your remote repo first in order to get its URL. 
- **_git remote -v_** lets you list the current remote repository you're using.
- **_git push_** uploads your commited changes to your remote repo.
- **_git branch_** lists all the available branches on your repo and tells you what branch you're currently on. If you want to create a new branch, you just have to add the new branch name as parameter like `git branch <branch name>`. 
- **_git checkout_** moves you from one branch to another. It takes your destination branch as paremeter. `git checkout newBranch`.
- **_git pull_** downloads the code from your remote repository and combines it with your local repo. This is particularly useful when working in teams, when many developers are working on the same code base. In this case each developer periodically pulls from the remote repo in order to work in a code base that includes the changes done by all the other devs.
	If there's new code in your remote repo, the command will return the actual files that were modified in the pull. If not, we get "Already up to date".
- **_git diff_** allows you to view the differences between the branch you're currently in and another. `git diff newBranch`.
- **_git merge_** combines the branch you're currently in with another. Keep in mind the changes will be incorporated only to the branch you're currently in, not to the other one. `git merge newBranch`.
- **_git log_** lists all previous commits you've done in the repo.



