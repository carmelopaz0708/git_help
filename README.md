# GIT NOTES

This repository contains notes for Git commands I've learned throughout my studies. All of my notes will be compiled here, including examples and their output.

### BASIC COMMANDS

Commands for getting started with Git.

**git init**

Initializes current path as a git repository.

    $ git init
    Initialized empty Git repository in C:/Users/siege/Developer/git/demo/.git/

**git clone** *link*

Copies the contents of the remote repository to your local machine.

#### git status

Tracks version changes to the file or repository.

#### git add *directory*

Tracks the changes to files and folders in *directory* with the remote repository. Next commit will add the most recent changes to the remote repository.

#### git commit -m *message*

Tells git to set current repository as the latest version. When pushed, will replace remote repository's contents with the last commit.

#### git push origin *directory*

Replaces the **remote** repository with the commit version on your local machine.

#### git pull

Pulls the remote repository and its latest version changes to the local directory.

#### git push -u origin *directory*

In addition to working the same way as `git push origin directory`, sets an upstream link to your git remote repository. This allows the user to omit `origin directory` in their next `git push`.

#### git remote add origin *link*

Sets the local directory as `master` and associates it to *link*. *Link* is the URL for the Github repository in the remote server.

#### git remote -v

List remote repositories connected to the current directory.

## GIT BRANCHING

Allows developers to create separate branches of the code in the development cycle. These paths will be used to test new features in code without risk of breaking the master branch. Code modified in branches does not affect the master branch nor any other branch separate from itself.

#### git branch

List all branches in the local repository (including the master branch). The `*` indicates the active branch in your local repository.

#### git branch branch-name

Switches current branch to `branch-name`.

#### git checkout -b branch-name

Creates a new branch called `branch-name` and switches your current branch to it.

#### git branch -d branch-name

Delete `branch-name`

#### git diff branch-name

Compares code between `branch-name` and `master`. Displays output to the command line.

#### git merge branch-name

Merge changes between `branch-name` to `master`