# Git Workflow - help guide

This is thought for being used with GitLab but will work pretty much as well for GitHub.

## General

**⚠** Do not **ever** push on `master`. **⚠**

-   Always add meaningful commits
    
-   Commit should use the present tense to read them as `this commit will <commit msg>`. ex: `add the airport database dat file` will be read as: `this commit will the airport database dat file`
    
-   Commit each meaningful progress; otherwise if you should commit, mark it with `WiP`
    
-   Think about pushing on a regular basis, in order to allow others to check out your progresses
    

## Developping a feature

Before starting the explanations, we will suppose that you are at the **root of your git project** and **on the `master` branch**.

### Select an issue

In this tutorial, we will be assuming that you are working on the issue: `#9 improve unit tests`.

Please note a fiew important things on each issue:

-   The issue number, as `#<number>`
    
-   Its message
    

We will be constructing our workflow using those information.

### Starting to work on the issue

Start by gathering the latest changes: `git pull` or `git pull --all`

We will then create a branch to work on the feature. Each branch name should has a name as: `<issue number>-<issue title>` separated by `-`.
In this case, for `#9 improve unit tests`, the branch will be: `9-improve-unit-tests`.

So let's go ahead and create it: `git branch 9-improve-unit-test`.

That's it ! Let's switch to our branch: `git checkout 9-improve-unit-test`. Just to be sure, you can type: `git branch` and see all branches and your current branch (which should be the one you just created).

### Working on your feature

Work on all your features and implementations, and don't forget to commit each meaningful change. If you just achieved an improvement, use `git status` to see the modified files.

Select the one you want to commit with `git add <file> <file> ...` add as many file as needed, or just one.

Then add a commit message to explain what those modifications do `git commit -m "<message>"`.
 For example: `git commit -m "document all existing tests"`.

Finally, push your local changes to your branch: `git push origin <target>`.
 Here this will be: `git push origin 9-improve-unit-test`.

### Finishing your development

Well done ! Everything's fine and you're done with the development for this issue. Do you last commits, pushes and go ahead !

Before continuing, merge master in your branch to gather all the latest commits:

- `git checkout master`: return on the master branch

- `git pull`: update master with the last version

- `git checkout <your branch>`: go back to your branch

- `git merge master`: import all changes from master in your branch (conflicts may happen)

Go on `Gitlab > your_project > Merge Requests > New merge request`.

As source branch, select yours. You should see `9-improve-unit-test` in the dropdown list.
The target branch will be `master` (usually).

Clic on `compare branches and continue`.

Fill all relevant fields:

-   Title: (should be already filled)
    
-   Description: what did you do to solve your issue; what changed ? Add `Closes #<issue number>` to instantly close the issue when the merge request will be merged
    
-   Assignee: assign the person who will be reviewing your code and validate it
    
-   Milestone: is your issue related to any milestone ? Clic on the dropdown list to specify it
    
-   Labels: (should be filled by the issue labels)
    
-   Approvers: additionnal people required to approve your merge request before it could be merged
    

Then clic on `Submit merge request`.

That's it !
