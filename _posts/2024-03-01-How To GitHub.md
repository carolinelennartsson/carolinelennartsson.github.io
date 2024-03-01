# How To Github 
This is a simple tutorial on how to use the key functions in git and github. Enyoj. 

## Install & update git 
* Install; `brew install git` or use your preferred installer, like conda. 
* Check version or succesful installation; `git --version` 
* Update; `brew upgrade git` 

## Link your computer to your GitHub account
1. Create a ssh key [Generate SSH key](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent) 
2. Add key to your github account [Add SSH key to account](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)
3. Configurate by typing; `git config --global user.email "you@example.com"`

Then you should be ready to roll.

## Using git and GitHub
A Git project has three parts:
1. A Working Directory: This is where you create, edit, delete and organise fileseither locally or on GitHub.
2. A Staging Area: Where you’ll list the changes you make to the working directory and prepare for syncing and uploading.
3. A Repository: Here is where Git stores the code and all those changes as different versions of the project. 

The Git workflow consists of editing files in the working directory, adding files to the staging area, and saving changes to a Git repository.

## Main Workflow
1. `git pull` Download updates from remote github repo. Pull is a combined command of fetch and merge.
2. `git add .` List files and add them to uploading list. Specify a file to add or type `.` to add all current changes to your staging area.
3. `git commit -m "message"` Commit specified files and changes. This step takes the updates from the staging area ans prepares an upload.
4. `git push` Upload files to remote repository. Merges you local repository to the main, if on main branch. 

Check status of changes made to working directory; `git status` 
See difference between working directory and last commit; `git diff` 

## Git Branches
If you are working on a large project with many people is involved, you might want to consider with branches. This protects different versions of the code.
* List existing branches; `git branch` 
* Create new branch "BRANCH"; `git branch BRANCH` 
* Switch to branch; `git checkout BRANCH` 
* git push origin BRANCH; `git push origin BRANCH` 
