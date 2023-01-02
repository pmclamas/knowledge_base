https://www.digitalocean.com/community/tutorial_series/an-introduction-to-open-source

This tutorial series will guide you through selecting an open-source project to contribute to, making a pull request to a Git repository through the command line, and taking steps to follow up on your pull request.

**Contributing to Open-Source projects**

Projects that are open source encourage a transparent process that is advanced through distributed peer review. Open Source projects can be updated quickly and as needed, and offer reliable and flexible software that is not built on locked proprietary systems.

When end-users contribute to open-source projects through code or documentation, their diverse perspectives provide added value to the project, the project's end-users, and the larger developer community.

The best way to begin to contribute to Open Source projects is to start by contributing to software that you already use.

Make sure you read any available documentation about the software first. Many Open Source projects will have a [CONTRIBUTING.md](http://contributing.md) file in the root directory, which you should read carefully before you contribute. You may also want to get a sense of the interactions between other developers in the community if there are forums about the project available.

Finally, if you're just starting out with contributing to Open Source software, it is a good idea to start with something small - each contribution is valuable. You may want to start with fixing typos, adding comments, or writing clearer documentation.

**Git**

Many projects maintain their files in a Git repository. Every working directory in Git is a full-fledged repository with complete history and tracking independent of network access or a central server.

Version control has become an indispensable tool in modern software development because these systems allow you to keep track of software at the source level. You and other members of a development team can track changes, revert to previous stages, and branch off from the base code to create alternative versions of files and directories.

Git is so useful for Open Source projects because it facilitates the contributions of many developers. Each contributor can branch off from the main or master branch of the code base repository to isolate their own changes, and can then make a pull request to have these changes integrated into the main project.

**Setting up Git**

You need to do a few things so that the commit messages that will be generated for you will contain your correct information.

The easiest way of doing this is through the 'git config' command. Specifically we need to provide our name and email address because Git embeds this information into each commit we do. We can go ahead and add this information:

`$ git config --global [user.name](<http://user.name>) "Your name"`

`$ git config --global [user.email](<http://user.email>) "youremail@domain.com"`

We can see all of the configuration items that have been set:

`$ git config --list`

