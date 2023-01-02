_This tutorial will guide you through making a pull request to a Git repository through the command line so that you can contribute to open-source projects._

**Create a copy of the repository**

A repository (repo), is essentially the main folder of a project. The repository contains all the relevant project files, including documentation, and also stores the revision history of each file.

In order to work on an open-source project, you will first need to make your own copy of the repository. To do this, you should fork the repository and then clone it so that you have a local working copy.

**Fork the repository**

Click on the fork button to start the forking process.

Once the process is done, your browser will go to a screen similar to the repository image above, except that at the top you will see your username before the repository name, and in the URL it will also say your username before the repository name.

With the repository forked, you're ready to clone it so that you have a local working copy of the code base.

**Clone the Repository**

To make your own local copy of the repository you would like to contribute to, let's first open up a terminal window.

We'll use the 'git clone' command along with the URL that points to your fork of the repository.

$ `git clone [<https://github.com/your-username/repository.git>](<https://github.com/your-username/repository.git>)`

Now that we have a local copy of the code, we can move on to creating a new branch on which to work with the code.

**Create a New Branch**

Whenever you work on a collaborative project, you and other programmers contributing to the repository will have different ideas for new features or fixes at once. Some of these new features will not take significant time to implement, but some of them will be ongoing. Because of this, it is important to branch the repository so that you are able to manage the workflow, isolate your code, and control what features make it back to the main branch of the project repository.

The default main branch of a project repository is usually called the master branch. A common best practice is to consider anything on the master branch as being deployable for others to use at any time.

When creating a branch, it is very important that you create your new branch off of the master branch. You should also make sure that your branch name is a descriptive one. Rather than calling it "my-branch", you should go with "frontend-hook-migration" or "fix-documentation-typos" instead.

To create our branch, from our terminal window, let's change our directory so that we are working in the directory of the repository. ($ cd repository)

Now, we'll create our new branch with the 'git branch' command. Make sure you name it descriptively so that others working on the project understand what you are working on.

`$ git branch new-branch`

Now that our new branch is created, we can switch to make sure that we are working on that branch by using the 'git checkout' command:

`$ git checkout new-branch`

Once you enter the 'git checkout' command, you will receive the following output: "Switched to branch 'new-branch'".

Alternatively, you can condense the above two commands, creating and switching to a new branch, with the following command and '-b' flag:

`$ git checkout -b new-branch`

If you want to switch back to master, you'll use the 'checkout' command with the name of the master branch:

`$ git checkout master`

The 'checkout' command will allow you to switch between multiple branches, so you can potentially work on multiple features at once.

At this point, you can now modify existing files or add new files to the project on your own branch.

**Make changes locally**

Once you have modified existing files or added new files to the project, you can add them to your local repository, which we can do with the 'git add' command. Let's add the -A flag to add all changes that we have made:

`$ git add -A`

Next, we'll want to record the changes that we made to the repository with the 'git commit' command.

The _**commit message**_ is an important aspect of your code contribution; it helps the other contributors fully understand the change you have made, why you made it, and how significant it is. Additionally, commit messages provide a historical record of the changes for the project at large, helping future contributors along the way.

If it's a very short message, we can record that with the '-m' flag and the message in quotes:

`$ git commit -m "Fixed documentation typos"`

But, unless it is a very minor change, we will more than likely want to include a lengthier commit message so that our collaborators are fully up to speed with our contribution. To record this larger message, we will run the 'git commit' command which will open the default text editor:

`$ git commit`

After running the 'git commit' command, depending on the default text editor you're using, your terminal window should display a document ready for you to edit that will look similar to this:

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/ead64307-21f4-4e9c-bc53-7c52972d1617/Screenshot_2020-08-25_at_14.30.25.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/ead64307-21f4-4e9c-bc53-7c52972d1617/Screenshot_2020-08-25_at_14.30.25.png)

Underneath the introductory comments, you should add the commit message to the text file.

To write a useful commit message, you should include a summary on the first line that is around 50 characters long. Under this, and broken up into digestable sections, you should include a description that states the reason you made this change, how the code works, and additional information that will contextualize and clarify it for others to review the work when merging it. Try to be as helpful and proactive as possible to ensure that those maintaining the project are able to fully understand your contribution.

Once you have saved and exited the commit message text file, you can verify what git will be committing with the following command:

`$ git status`

At this point you can use the 'git push' command to push the changes to the current branch of your forked repository:

`$ git push --set-upstream origin new-branch`

The command will provide you with output to let you know of the progress.

You can now navigate to the forked repository on your GitHub page and toggle to the branch you just pushed to see the changes you have made.

At this point, it is possible to make a pull request to the original repository, but if you have not already done so, you'll want to make sure that your local repository is up-to-date with the upstream repository.

**Update Local Repository**

While you are working on a project alongside other contributors, it is important for you to keep your local repository up-to-date with the project as you don't want to make a pull request for code that will cause conflicts. To keep your local copy of the code base updated, you'll need to sync changes.

We'll first go over configuring a remote for the fork, then syncing the fork.

_**Configure a Remote for the Fork**_

Remote repositories make it possible for you to collaborate with others on a Git project. Each remote repository is a version of the project that is hosted on the internet or a network you have access to. Each remote repository should be accessible to you as either read-only or read-write, depending on your user privileges.

In order to be able to sync changes you make in a fork with the original repository you're working with, you need to configure a remote that references the upstream repository. You should set up the remote to the upstream repository only once.

Let's first check which remote servers you have configured. The 'git remote' command will list whatever remote repository you have already specified. You'll at least see the origin repository, which is the default name given by Git for the cloned directory.

From the directory of the repository in our terminal window, let's use the 'git remote' command along with the '-v' flag to display the URLs that Git has stored along with the relevant remote shortnames (as in "origin"):

`$ git remote -v`

If you have previously set up more than one remote, the 'git remote -v' command will provide a list of all of them.

Next, we'll specify a new remote upstream repository for us to sync with the fork. This will be the original repository that we forked from. We'll do this with the 'git remote add' command.

`$ git remote add upstream[<https://github.com/original-owner-username/original-repository.git>](<https://github.com/original-owner-username/original-repository.git>)`

In this example, 'upstream' is the shortname we have supplied for the remote repository since in terms of Git, "upstream" refers to the repository that we cloned from. If we want to add a remote pointer to the repository of a collaborator, we may want to provide that collaborator's username or a shortened nickname for the shortname.

We can verify that our remote pointer to the upstream repository was properly added by using the "git remote -v" command:

`$ git remote -v`

Now you can refer to the 'upstream' on the command line instead of writing the entire URL, and you are ready to sync your fork with the original repository.

**Sync the Fork**

To sync our fork, from the directory of our local repository in a terminal window, we'll use the 'git fetch' command to fetch the branches along with their respective commits from the upstream repository. Since we used the shortname "upstream" to refer to the upstream repository, we'll pass that to the command:

`$ git fetch upstream`

Now, commits to the master branch will be stored in a local branch called 'upstream/master'.

Let's switch to the local master branch of our repository:

`$ git checkout master`

We'll now merge any changes that were made in the original repository's master branch, that we will access through our local upstream/master branch, with our local master branch:

`$ git merge upstream/master`

The output here will vary, but it will begin with 'Updating' if changes have been made, or 'Already up-to-date' if no changes have been made since you forked the repository.

Your fork's master branch is now in sync with the upstream repository, and any local changes you made were not lost.

Depending on your own workflow and the amount of time you spend on making changes, you can sync your fork with the upstream code of the original repository as many times as it makes sense for you. But you should certainly sync your fork right before making a pull request to make sure you don't contribute conflicting code.

**Create Pull Request**

At this point, you are ready to make a Pull Request to the original repository.

You should navigate to your forked repository, and press the "New pull request" button on your left-hand side of the page.

You can modify the branch on the next screen. On either site you can select the appropriate repository from the drop-down menu and the appropriate branch.

Once you have chosen, for example, the master branch of the original repository on the left-hand side, and the 'new-branch' of your forked repository of the right-hand side.

GitHub will alert you that you are able to merge the two branches because there is no competing code. You should add in a title, a comment, and then press the "Create pull request" button.

At this point, the maintainers of the original repository will decide whether or not to accept your pull request. They may ask for you to edit or revise your code prior to accepting the pull request.