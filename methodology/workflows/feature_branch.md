# Git feature branch workflow

## General

**⚠** Do not **ever** push on `master`. **⚠**

See other good practices rules on [the dedicated markdown file](https://github.com/pBouillon/git_tutorials/blob/master/methodology/commit_rules.md).

### 🛠 Developing a feature

Before starting the explanations, we will suppose that you are at the
**root of your git project** and **on the `master` branch**.

<details>
<summary>
📍 Select an issue
</summary>
<p>

In this tutorial, we will be assuming that you are working on the issue:
`#9 improve unit tests`.

Please note a few important things on each issue:

- The issue number, as `#<number>`
- Its message

We will be initializing our workflow using those informations.
</p>
</details>

<details>
<summary>
🔧 Starting to work on the issue
</summary>
<p>

Start by gathering the latest changes: `git pull` or `git pull --all`

We will then create a branch to work on the feature. Each branch name should
has a name as: `<issue number>-<issue title>` separated by `-`.
In this case, for `#9 improve unit tests`, the branch will be:
`9-improve-unit-tests`.

So let's go ahead and create it: `git branch 9-improve-unit-test`.

That's it ! Let's switch to our branch: `git checkout 9-improve-unit-test`.
Just to be sure, you can type: `git branch` and see all branches and your
current branch (which should be the one you just created).
</p>
</details>

<details>
<summary>
🚧 Working on your feature
</summary>
<p>

Work on all your features and implementations, and don't forget to commit each
meaningful change. If you just achieved an improvement, use `git status` to see
the modified files.

Select the one you want to commit with `git add <file> <file> ...` add as many
file as needed, or just one.

Then add a commit message to explain what those modifications do
`git commit -m "<message>"`.
For example: `git commit -m "document all existing tests"`.

Finally, push your local changes to your branch: `git push origin <target>`.
Here this will be: `git push origin 9-improve-unit-test`.
</p>
</details>

<details>
<summary>
    🎁 Finishing your development
</summary>
<p>

Well done ! Everything's fine and you're done with the development for this
issue. Do you last commits, pushes and go ahead !

Before continuing, merge master in your branch to gather all the latest commits:

- `git checkout master`: return on the master branch
- `git pull`: update master with the last version
- `git checkout <your branch>`: go back to your branch
- `git merge master`: import all changes from master in your branch
(conflicts may happen)

Go on `GitLab > your_project > Merge Requests > New merge request`.

As source branch, select yours. You should see `9-improve-unit-test` in the
dropdown list.
The target branch will be `master` (usually).

Clic on `compare branches and continue`.

Fill all relevant fields:

- Title: (should be already filled)
- Description: what did you do to solve your issue; what changed ? Add
`Closes #<issue number>` to instantly close the issue when the merge request
will be merged
- Assignee: assign the person who will be reviewing your code and validate it
- Milestone: is your issue related to any milestone ? Clic on the dropdown list
to specify it
- Labels: (should be filled by the issue labels)
- Approvers: additional people required to approve your merge request before it
could be merged

Then clic on `Submit merge request` and pray for your CI not to break.

🏆 That's it, time to move on your next issue !
</p>
</details>
