Once you submit a pull request, the process of contributing to a project can require some rebasing and reworking of code prior to acceptance, followed by a general clean up of your branches.

This tutorial will guide you through some of the next steps you may need to take after you submit a pull request to an open-source project.

**Rebasing Code and Cleaning Up comments**

While you contribute to open source, you may find that there are conflicts between your branch or pull request and the upstream code.

This may happen if the maintainers do not respond to your pull request for a while, or if many people are contributing to the project at once. When this happens and you still want to merge your pull request, you will have to resolve conflicts and rebase your code.

A _**rebase**_ allows us to move branches around by changing the commit that they are based on. This way, we can rebase our code to make them based on the master branch's more recent commits. Rebasing should be done with care, and you should make sure you are working with the right commits and on the right branch throughout the process. We'll also go over using the 'git reflog' command in case you make an error.

We'll move into the code directory and fetch the most recent upstream version of the code.

`$ cd repository`

`$ git fetch upstream`

Once you have the upstream version of the project fetched, you can clean up your comments by either squashing or rewording your commit messages to make them more digestable to the project maintainers. If you did not do many small commits, this may not be necessary.

To begin this process, you'll perform an interactive rebase. An interactive rebase can be used to edit previous commit messages, combine several commits into one, or delete or revert commits that are not necessary any longer. To do this, we will need to be able to reference the commits that we have made either by number or by a string that references the base of our branch.

To find out the number of commits we have made, we can inspect the total number of commits that have been made to the project with the following command:

`$ git log`

The log shows all the commits made to the given project's repository, so your commits will be mixed it with the commits made by others. For projects that have an extensive history of commits by multiple authors, you'll want to specify yourself as author in the command:

`$ git log —-author=your-username`

By specifying this parameter, you should be able to count up the commits you've made. If you're working on multiple branches you can add `—-branches[=<branch>]` to the end of your command to limit by branch.

Now if you know the number of commits you've made on the branch that you want to rebase, you can simply run the 'git rebase' command:

`$ git rebase -i HEAD~x`

Here, -i refers to the rebase being interactive, and HEAD refers to the latest commit from the master branch. The x will be the number of commits you have made to your branch since you initially fetched it.

If, however, you don't know how many commits you have made on your branch, you'll need to find which commit is the base of your branch, which you can do by running the following command:

`$ git merge-base new-branch master`

This command will return a long string known as a commit hash.

We'll use this commit hash to pass to the 'git rebase' command:

`$ git rebase -i [insert hash here]`

For either of the above commands, your command-line text editor will open with a file that contains a list of all the commits in your branch, and you can now choose whether to squash commits or reword them.

**Squash Commits**

When we squash commit messages, we are squashing or combining several smaller commits into a larger one.

In front of each commit you'll see the word "pick".

Now, for each line of the file except for the first line, you should replace the word "pick" with the word "squash" to combine the commits.

At this point, you can save and close the file, which will open a new file that combines all the commit messages of all of the commits. You can reword the commit message as you see fit, and then save and close the file. You'll receive feedback once you have closed the file.

You now have combined all of the commits into one by squashing them together.

**Reword commits**

Rewording commit messages is great for when you notice a typo, or you realize you were not using parallel language for each of your commits.

Once you perform the interactive rebase as described above with the 'git rebase -i' command, you'll have a file open up.

Now, for each of the commits that you would like to reword, replace the word "pick" with "reword".

Once you save and close the file, a new text file will appear in your terminal editor that shows the modified wording of the commit message. If you would like to edit the file again, you can do so before saving and closing the file. Doing this can ensure that your commit messages are useful and uniform.

**Complete the Rebase**

Once you are satisfied with the number of commits you are making and the relevant commit messages, you should complete the rebase of your branch on top of the latest version of the project's upstream code. To do this, you should run this command from your repository's directory:

`$ git rebase upstream/master`

At this point, Git will begin replaying your commits onto the latest version of master. If you get conflicts while this occurs, Git will pause to prompt you to resolve conflicts prior to continuing.

Once you have fixed the conflicts, you'll run:

`$ git rebase --continue`

This command will indicate to Git that it can now continue replaying your commits.

If you previously combined commits through using the 'squash' command, you will only need to resolve conflicts once.

**Update Pull Request with Force-Push**

Once you perform a rebase, the history of your branch changes, and you are no longer able to use the 'git push' command because the direct path has been modified.

We will have to instead use the —force or -f flag to force-push the changes, informing Git that you are fully aware of what you are pushing.

Let's first insure that our 'push.default' is 'simple':

`$ git config --global push.default simple`

At this point, we should ensure that we are on the correct branch by checking out the branch we are working on:

`$ git checkout new-branch`

Now we can perform the force-push:

`$ git push -f`

Now you should receive feedback of your updates along with the message that this was a 'forced update'. Your pull request is now updated.

**Recovering Lost Commits**

If at some point you threw out a commit that you really wanted to integrate into the larger project, you should be able to use Git to restore commits you may have thrown away by accident.

We'll be using the 'git reflog' command to find our missing commits and then create a new branch from that commit.

Reflog is short for reference logs which record when the tips of branches and other references were last updated within the local repository.

From the local directory of the code repository we are working in, we'll run the command:

`$ git reflog`

Your commit messages will let you know which of the commits is the one that you left behind, and the relevant string will be before the HEAD@{x} information on the left-hand side of your terminal window.

Now you can take that information and create a new branch from the relevant commit:

`$ git checkout -b new-new-branch a1f29a6`

In the example above, we made a new branch from the third commit displayed above, the one that rolled out a "brand new feature", represented by the string a1f29a6.

**Note:** if you recently ran the 'git gc' command to clean up unnecessary files and optimize the local repository, you may be unable to restore lost commits.