# Nicolas's Guide to Git
#### Written by someone who sort of understands git for people who don't understand git.

## What is Git?
Git is version control software. Version control software is software that keeps track of changes in files. Git is a distributed version control system, which means it is designed to be used by multiple people working on the same files. Git's goal is to track changes and help coordinate changes by different people to the same files. 
Every developer working on the project has their own local version of the source code (the files that they are concerned with editing) and developers integrate their changes using git. Git will do the integration manually if there are no conflictions in the edits, but if two changes are in conflict with each other, a human has to manually integrate the changes. We'll go into more depth later, this is just to give you an idea of how git operates. 
As a final note, github is a website that hosts git repositories. Each developer's local source code is also a git repository, so the repository on github is actually treated by the git software as the same as anyone's local version of the code. However, as humans, we will treat the repository on github as the **ultimate source of truth**. 

## GUIs
I am not familiar with any git GUIs. Personally, I like the percision and control that stems from using git over the commandline. However, I recognize that not everyone who needs to use git is familiar with the command line, so I will attempt to teach the concepts behind git, with implementations of those concepts in both CLI and GUI. *Auther's note: GUI interface notes will come later, after I can recommend a good GUI and get familiar enough with it*.

## Starting a git repositiory
A git repository lives inside a folder on your filesystem. Any folder on your filesystem can become a git repository with `git init`. Additionally, you can create a repository by using `git clone` to copy another repository to your filesystem.
**CLI Instructions**:
* For making a new repository:
   Navigate to the folder you want to make the root of your project. Enter `git init` into your command line.
* For cloning an existing repository:
   Navigate to the folder you want to contain your project. Ex: if you have a project folder, navigate to that folder.  
   Enter `git clone <link to repository>` into your command line. This will create a new folder in your project folder with the same name as the repository.  
   If you would like the folder containing the repository to have a different name, use `git clone <linkt to repository> <new name>`

## Adding changes
When you make changes to the source files, git doesn't automatically track them. Instead, you must inform git of what files you've changed. The `git add` command tells git to look at changes made in a file, or in all files in a folder. This step is necessary every time you want to track changes, not just the first time you create a file. After telling git all the files and folders that you've changed, use `git commit` to submit your changes. This can be considered like a giant save button. You've now created a backup describing how all of your files are in this moment. You can use this backup to retrieve old states, but that is a little beyond the scope of this tutorial. As a final note, the .gitignore file lists all files that should never be tracked by git. Git will never track changes to a file or folder in the .gitignore file.
**CLI Instructions**
* For tracking files:
   Navigate to your git repository's root folder. `git add <folder or file>` tracks a folder or file.  
   Its worth noting that `git add .` tells git to track every file in the repo for changes.
* For commiting changes:
   Navigate to your git repository's root folder. Ensure all changed files and folders are tracked.  
   `git commit` enters your changes.  
   This command will open up a command line editor to allow you to make a commit message. If you wish to avoid that (unless you're good with a command line editor, I'd try to avoid it) then use `git commit -m "<message>"` to craft your message in the command line. 
 
**PLEASE use good and descriptive commit messages so we know the purpose and changes made in each commit** 

## Syncing changes made somewhere else to your repo
So you've made a couple changes to your source files in your local git repository. How do you go about integrating those changes to your repository with another repository? The `git pull` command will ask a different git repository (henceforth called the remote repository) if there have been any changes to the remote repository since the previous `git pull`. If there have been changes, git attempts to merge the changes into your local repository. If there is any sort of conflict (Ex two people modified the same line in different ways) it will throw an error and require a person to tell it how to merge these two files. This is a little outside the scope of the tutorial, as merging can be complicated. Before using `git pull`, ensure that your local changed are committed, or git may complain about changes in untracked files.
**CLI Instructions**
* Navigate to your git repo's root folder. `git pull <remote> <branch>` pulls the changes to the remote repo, on a given branch. These two topics will be discussed more later.   

## Syncing your changes to somewhere else
Lets start this out with an important note. If you try to push your changes to another repository, but you haven't intergrated the latest changes from that repository to your local repo, the push will not be successfull. Unless you force the push. But please don't do that.

Once you've pull the changes from a remote repo, you sync your changes to that repo with `git push`. This is a little less complicated because all the merging happened on the previous step!
**CLI Instructions**
* Navigate to your git repo's root folder. `git push <remote> <branch>`. Make sure you've committed your changes, as this pushes your latest commit.

## Remote repositories
If you started a repo through `git clone`, the remote repository is already saved with the name origin. If you'd like to add repos, use `git remote add`. The documentation on this is pretty straightforward and this isn't super esstential info, so I'm moving on.

## Branches
This is where my knowledge breaks down a little, and we don't need to go into depth here so I'm not. Branches are different versions of the same repository. You can update branches independantly of each other, then merge branches together. A common use for this is making a development branch so you can keep the master branch clean. The default branch name is called master. **Here's the crucial part**: when you first create a git repository (through init or clone), you are on the master branch. To make sure the edits you make are tracked and commited to a different branch, you must use `git checkout`.
**CLI Instructions**
* Navigate to your git repo's root folder. `git checkout <branch>`. This will put you on the given branch, and you will stay there until you `git checkout <different branch>`, even if you turn off your computer.
* `git branch` lists all your branches. The starred branch is your current branch.


## The usual workflow
This is the way most editing sessions will generally go. If this master plan fails, either dig through git documentation to resolve it, or contact someone who knows more git then you. For this workflow, replace <branch> with your prefered branch. If this is a project with just a master branch, make it master. If it has dev branches, use the name of your dev branch.
1. Pull changes with `git pull origin <branch>`.
2. Make sure you are on the correct branch with `git branch`. Use `git checkout <branch>` if you aren't.
3. **EDITING**
4. Use `git add <folder or file>` to add all folders and files where changes occured. For the lazy, `git add .` will track everything, but this should only be done when there is a good .gitignore file.
5. Use `git commit -m "<message>` to commit changes to tracked files.
6. Use `git pull origin <branch>` just to make sure there haven't been any other changes since you started editing.
7. Use `git push origin <branch> to submit your changes.

You have now made edits to the source code and the **ultimate source of truth** has incorporated those changes!! 

## Goodbye and thanks for all the commits
I designed this tutorial to be accessible to people with little to no git knowledge ( *Author's note: that'll be even better after GUI instructions* ). Tell me if there is something you didn't understand!
