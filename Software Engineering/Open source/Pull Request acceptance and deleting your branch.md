If your pull request has been accepted, you have successfully made a contribution to an open-source software project!

At this point, you will need to pull the changes you made back into your fork through your local repository. This is what you have already done when you went through the process to sync your fork. You can do this with the following commands in your terminal window:

`$ git checkout master`

`$ git pull --rebase upstream master`

`$ git push -f origin master`

Now, you should clean up both your local and remote branches by removing the branch you created in both places as they are no longer needed. First, let's remove the local branch:

`$ git branch -d new-branch`

The -d flag added to the 'git branch' command will delete the branch that you pass to the command. In the example above, it is called 'new-branch'.

Next, we'll remove the remote branch:

`$ git push origin --delete new-branch`

With the branches deleted you have cleaned up the repository and your changes now live in the main repository. You should keep in mind that just because the changes you made through your pull request are now part of the main repository, they may not be available to the average end user who is downloading public releases. Generally speaking, software maintainers will bundle several new features and fixes together into a single public release.