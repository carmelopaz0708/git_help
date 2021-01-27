# GIT NOTES

This repository contains notes for Git commands I've learned throughout my studies. All of my notes will be compiled here, including examples and their output.

### BASIC COMMANDS

Commands for getting started with Git.

**git init**

Initializes current path as a git repository.

    $ git init
    Initialized empty Git repository in C:/Users/siege/Developer/git/demo/.git/

**git clone** *link*

Copies the contents of the remote repository associated with *link* to your local machine. *Link* refers to the remote repository's URL in Github. The cloned repository will automatically contain the initialization files that enable git commands.

    $ git clone https://github.com/carmelopaz0708/test-repo.git
    Cloning into 'test-repo'...
    remote: Enumerating objects: 67, done.
    remote: Counting objects: 100% (67/67), done.
    remote: Compressing objects: 100% (49/49), done.
    Receiving objects: 100% (67/67), 9.89 KiB | 361.00 KiB/s, done.0Receiving objects:  61% (41/67)

    Resolving deltas: 100% (20/20), done.

**git status**

Displays the current working file's code revisions in the current directory.

**git add** *file-name/directory*

Adds all prior code revisions to the current working file or directory. A file/folder having `git commit` will only consider code changes up to the last `git add`. Common usage involves including the current directory such as `git add .`. The user can also add individual files with `git add file-name`.

**git commit -m** *description*

Set's the current local repository as the latest version of that branch. When the repository is pushed, it will replace the remote repository's version with the latest commit. Commits are required to have a description of the latest changes as indicated by *description*.

    $ git commit -m *Revised README.md*
    [feature-build-readme c3a6351] *Revised
    1 file changed, 17 insertions(+), 6 deletions(-)

The user can opt to have `git commit -m description -m description` to give more detail on the applied changes in code. 

**git push origin** *branch-name*

Copies the current branch's latest commit to Github. *Branch-name* refers to any branch in the repository, including `master`.

Ideally, the user should use `git push -u origin branch-name` when pushing commits to the remote repository for the first time. This command will create an upstream link that'll keep track of succeeding commits in the same *branch-name*. Doing so succintly reduces command line input to `git push` for future commits in that repository.

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