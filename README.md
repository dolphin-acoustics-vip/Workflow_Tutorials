# Workflow_Tutorials
This is a repository meant to give some basic tips for students on this project on how to set up a clean workflow for code (including things like git and virtual environments). 

# Git
For installing git, first-time setup, and creating a git repository, see: https://git-scm.com/video/get-going.

## Cloning a repository
Go to a directory in which you wish the repo to be cloned over, then run:

`git clone <repo_url>`

For this tutorial, we will use the example of cloning this repository:

`git clone https://github.com/dolphin-acoustics-vip/Workflow_Tutorials`

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


## Keeping your branch up-to-date
If others have psuhed changes onto a repository after you made your clone of it, you can get the most updated version of the repository by running:

`git push origin main` (assuming in this case that you were in the `main` branch). 

## Final notes and additional resources
Note: To avoid conflicts with other students, please **do not push changes to the main branch of this repository**. However, feel to use these commands on your own repositories, or to create your own branches of this repository.

Additional resources that may be useful:

https://git-scm.com/doc

https://www.youtube.com/watch?v=HkdAHXoRtos&t=413s

https://www.w3schools.com/git/default.asp?remote=github
https://git-scm.com/doc

# Creating a requirements.txt file (Python-specific)
In order for others to easily run your code, it is good practice to create a file which lists its required dependecies. Such a file is typically named "requirements.txt". An example of a "requirements.txt" file can be found in this repository. It gives library names, and the exact versions to be used.

There are several ways this can be done (including manually), but one good way to do this is using the the pipreqs library (https://pypi.org/project/pipreqs/). This has a benefit over alternatives (like pip freeze - https://pip.pypa.io/en/stable/cli/pip_freeze/) in that it saves only the dependencies required for your specific code (as opposed to all dependencies in your environment).

To install pipreqs, run:

`pip install pipreqs` 

in your terminal.

Next, got to your working directory (for which you wish a requirements file to be created), and run:

`pipreqs .`

A "requirements.txt" file should now be created in your directory. Note that if one was there previously, it should be deleted (or renamed) beforehand to avoid issues.


# Creating a Virtual Environment using virtualenv (Python-specific)

First, check that you have virtualenv installed:
`which virtualenv`
if you don't have virtualenv installed enter the following in terminal:
`pip install virtualenv`

Now create a virtual environment:
`virtualenv <virtual_env_name>` (replace <virtual_env_name> with any name. For example you could type: `virtualenv dolphin_acoustics`)

Activate your virtual environment:

`source <virtual_env_name>/bin/activate` for Unix and MacOS

or:

`<virtual_env_name>\Scripts\activate` for Windows

You can verify that you are in the correct virtual environment by typing:
`which python`
`which pip`
The terminal/command-prompt usually shows that you have activated a virtualenv by displaying `(<virtual_env_name)` before the prompt.

Install all the necessary libraries and modules of the correct versions by typing:
`pip install -r requirements.txt`

### Deactivating or deleting your virtual environment

To deactivate the virtual environment:
`deactivate`

To delete an environment enter the following command:
`sudo rm -rf <virtual_env_name>`

## Second step: add virtual enviroment to jupyter notebook

1. activate your venv if you haven't already
2. install ipykernel (this provides the ipython kernel for jupyter, ie allows jupyter to change a kernel based on a virtual enviroment)
3. add the virtual environment to Jupyter by typing:
`python -m ipykernel install --user --name=<virtual_env_name>`
or you can change the kernel with the GUI in the jupyter notebook interface:

## Deleting your virtual environment from the jupyter notebook

if you delete your virtual environment you would need to remove it from the list of kernels:
`jupyter kernelspec list`
`jupyter kernelspec uninstall <my_env_name>`
