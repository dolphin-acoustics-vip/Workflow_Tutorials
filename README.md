# Workflow_Tutorials
This is a repository meant to give some basic tips for students on this project to be set up a clean workflow for code (including things like git and virtual environments). 

# Git
For installing git, first-time setup, and creating a git repository, see: https://git-scm.com/video/get-going.

## Cloning a repository
Go to a directory in which you wish the repo to be cloned over, then run:

`git clone https://github.com/dolphin-acoustics-vip/science-communication`

## Creating a new branch
Create a new branch called "new_branch":
`git branch new_branch`

We can check that the new branch is created by running:
`git branch`

We should see a "main" branch (which you should be in) and the new "new_branch".

Move over to the new_branch:
`git checkout new_branch`

## Git add, commit and push
We can now make changes in "new_branch" which do not affect the main branch.

Make a change to the example_code.py file.

Now we add those changes to what is called the "staging environment".
Run either:

`git add example_code.py`

or more generally (if there were other files):

`git add .`

Next, we record these changes locally by committing the changes with a message (in this case "made changes to example_code.py"):

`git commit -m "made changes to example_code.py"`

This command only commits changes that were added to the staging environment. So if, for example, you created another file, but did not stage it, it would not be committed.

Fianlly, we push the commit to GitHub. This would now add your local branch onto GitHub. (Note: Doing this - especially for the first time - may require a security check from GitHub):

`git push origin new_branch`

## Merging Branches
Say we now want to merge the changes we made in "new_branch" into the main branch. We can do this by first returning to the main branch:

`git checkout main`

then running:

`git merge new_branch`

Note: It is advised that, at least for simple projects, you **do not make edits to the same code on both the main branch and other branches**. 
This may lead to things known as "merge conflicts" in which git cannot decide which changes should be saved.

Finally, we can again push these changes on the main branch to GitHub:

`git push origin main`

## Final notes and additional resources
Note: To avoid conflicts with other students, please **do not push changes to the main branch of this repository**. However, feel to use these commands on your own repositories, or to create your own branches of this repository.

Additional resources that may be useful:

https://git-scm.com/doc

https://www.youtube.com/watch?v=HkdAHXoRtos&t=413s

https://www.w3schools.com/git/default.asp?remote=github
https://git-scm.com/doc
