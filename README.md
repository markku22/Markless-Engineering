# Markless-Engineering
The initial repo for Markless Engineering's debut project

### How do I collaborate on the Markless-Engineering project?

Ask marku22 to add you to the repository as a collaborator. 

You will use Git to make a local copy of the repository on your computer. This will allow you to make small but significant changes and share them with the team without breaking anything. We're using the "Git Feature Branch Workflow." You can learn more about it [here](https://fi.atlassian.com/git/tutorials/comparing-workflows/feature-branch-workflow).

First, think about where you want to store the repository on your computer.

You could call your Markless-Engineering project directory something like this (use your own student number!):

```git
    C:\Users\s1900123\Markless-Engineering
```

This guide describes how to manage a project using the Windows Command Prompt app. A future edit will add the directions for using the Linux command line tool. 

To start Windows Command Prompt click the magnifying glass icon on the bottom left corner of your screen. Type `command prompt` into the Windows search (click the magnifying glass icon on the bottom left corner of your screen). As you begin to type the search result will appear above.  Click the Command Prompt icon highlighted in blue to open the app. 

Understand when using the command prompt you should pay attention to what folder or directory you're in. The cursor usually shows you the present working directory or PWD. 

Your command prompt might open in the H drive so the cursor prompt may look like this:

```git
    H:\>
```

To move to the C drive type this:

```git
    C:
```

Now the cursor prompt looks like this:

```git
    C:\>
```

Now type the following to move to the Users directory:

```git
    cd users
```

Your cursor prompt will look like this:

```git
    C:\Users>
```

Now type the following (using your own student ID number) to enter your user directory:

```git
    cd s100123
```

Your cursor prompt will look like this:

```git
    C:\Users\s1900123>
```

If you want to see a list of the folders that are already in the directory, type the following:

```git
    dir
```

To create a local clone of the Markless-Engineering project repository type:

```git
    git clone https://github.com/marku22/Markless-Engineering.git
```

This creates a local folder for the project, adds a hidden git folder to that folder and pulls the repository code to your local computer. 

To confirm that you created the folder properly, check the current directory again by typing:

```git
    dir
```

You should now see the same list of folders as before, with the new Markless-Engineering folder added.

Move into the Markless-Engineering folder by typing:

```git
    cd Markless-Engineering
```

Your cursor will look like this:

```git
    C:\Users\s1900123\Markless-Engineering>
```

You might not be able to see it, and you don’t necessarily need to see it but there *is* a hidden .git folder in the Markless-Engineering directory. This folder contains the git magic that makes everything work. 

Type the following to see that the remote has automatically been set to origin:

```git
    git remote
```

You should see the following response:

```git
    origin
```

You're good to go!


### Making changes and building new features


Confirm that you are in the correct directory by typing:

```git
    cd
```

You'll see the following:

```git
    C:\Users\s1900123\Markless-Engineering>
```

If you see something else, you are in the wrong directory and you will have to use the `cd` command sequence detailed above to move to the correct directory.

Once you are in the correct directory, type the following to see that you are on the master branch:

```git
    git branch
```

You’ll see the following:

```git
    * master
```
This means you are on the master branch. 

To make sure you are working with the most up to date version of the remote master branch type:

```git
    git pull origin master
```

You'll see something like this:

```git
    remote: Enumerating objects: 7, done.
    remote: Counting objects: 100% (7/7), done.
    remote: Compressing objects: 100% (4/4), done.
    remote: Total 4 (delta 2), reused 0 (delta 0), pack-reused 0
    Unpacking objects: 100% (4/4), done.
    From https://github.com/marku22/Markless-Engineering
    * branch            master     -> FETCH_HEAD
    1050ca6..44e69b1  master     -> origin/master
    Updating 1050ca6..44e69b1
    Fast-forward
```
The updates on the remote master will also be listed. 

**IMPORTANT!!!** Create a new feature branch to start working on and making any changes to the repo. You should work on one task at a time, and have a dedicated branch for any task you're working on. Small, discrete changes are a good thing!

Create a new feature branch by typing `branch` followed by a branch name that describes the task you plan to work on such as game_logic_branch or countdown_view_branch:

```git
    git branch <your branch name- don't include the < > tags!>
```

**IMPORTANT!!!** To work on your new branch (and not the master branch) you must `check out` the new branch. Use the same branch name you used to create the branch to check it out. So type:

```git
    git checkout <your feature branch name- don't include the < > tags!>
```

To see what files and folders are available to work on type:

```git
    dir
```

To work on an existing file, type the name of the file you want to work on. So to update the existing README.md file type:

```git
    README.md
```
That file automatically launches in your default IDE (Visual Studio Code).

To create a new file type:

```git
    type nul > <your file name *with* the extension- don't include the < > tags!>
```

Your new file will be created and launch in Visual Studio.

Start doing stuff!


## How do I stage, commit and push my changes?

You should frequently commit your changes to a local staging area. Later you and other developers will be able to read through the commit messages to understand why changes were made, undo major changes, try different solutions, etc. 

The staging area prepares a commit without having to include every change in the working directory. This lets you create highly focused commits, even if you’ve made a lot of local changes. Commit your changes with a message describing what you have changed. 

You must specify which changed files you want to include in a commit. To check which files you have changed type:

```git
    git status
```

The names of the files you have changed while working on the branch will now appear in RED.

To stage one of the changed files type:

```git
    git add <type your file name and extension here without including the < > tags>
```

To stage *all* the changed files to be committed type:

```git
   git add .
```

To make sure the right files have been staged type:

```git
    git status
```

The names of all the file or files you just staged will now appear in GREEN.

To commit your changes type the following command with a descriptive commit message:
   
```git
   git commit -m "<type your commit message here without including the < > tags>"
```

To check your status again type:

```git
    git status
```

You will see a message stating everything on the branch is up to date. 

**IMPORTANT !!!**

It is good practice to keep your local repo master up to date with the remote repo master. To avoid merge conflicts, make sure you are working with the most up to date version of the remote master branch. Type: 

```git
    git checkout master
```

and type:

```git
    git pull origin master
```

The master branch will update. Then you can switch back to your new feature branch by typing:

```git
    git checkout <your feature branch name- don't include the < > tags!>
```

To share the committed changes to the team you will `git push` the commits staged in your feature branch to the remote repository on Github.

The *first time* you push your branch type:

```git
    git push --set-upstream origin <your branch name without including the < > tags>
```

The next time you want to push the branch, type:

```git
    git push origin <your branch name without including the < > tags>
```

You will now see your changes on the remote repository and you can make a pull request!


## How do I get help with my code or get it merged into the project?

Pull requests let you tell others about changes you've pushed to a branch in a repository on GitHub. Once a pull request is opened, you can discuss and review the potential changes with collaborators and add follow-up commits before your changes are merged into the base branch.

Go to the following web address:

```git
    https://github.com/marku22/Markless-Engineering
```

Go to the `Branch:master` drop down menu and choose your branch. Enter your branch name at the `Switch branches\tags` drop down box or just click on your branch name. Now the drop down menu will say `Branch:<your branch name without including the < > tags>`. Click on the `New Pull Request` box and follow the instructions there. 
    

### Happy coding :)
