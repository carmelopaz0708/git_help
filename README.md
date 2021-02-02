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

Displays the current working file's code modifications and commit status in the current directory.

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

Ideally, the user should use `git push -u origin branch-name` when pushing commits to the remote repository for the first time. This command will create an upstream link that'll keep track of succeeding commits in the same *branch-name*. Doing so reduces command line input to `git push` for future commits in that repository.

    $ git push
    Enumerating objects: 11, done.
    Counting objects: 100% (11/11), done.
    Delta compression using up to 4 threads
    Compressing objects: 100% (9/9), done.
    Writing objects: 100% (9/9), 2.59 KiB | 1.30 MiB/s, done.
    Total 9 (delta 2), reused 0 (delta 0), pack-reused 0
    remote: Resolving deltas: 100% (2/2), done.
    To https://github.com/carmelopaz0708/test-repo.git
        971be80..3e91136  feature-build-readme -> feature-build-readme

**git pull**

Pulls the latest branch version of the remote repository to the current local directory. If no changes are detected, `git pull` will return nothing.

**git remote**

Commands for communicating with the remote repository. To check the list of remote repositories tied to the current local branch, use `git remote -v`. The command `git remote add origin link` sets the local folder as `master` and ties it to a remote repository in Github. Replace *link* with the repository's URL in Github.

    $ git remote -v
    origin  https://github.com/carmelopaz0708/test-repo.git (fetch)
    origin  https://github.com/carmelopaz0708/test-repo.git (push)

## GIT BRANCHING

Allows developers to create separate branches of the code in the development cycle. These paths will be used to test new features in code without risk of breaking the master branch. Code modified in branches does not affect the master branch nor any other branch separate from itself. Note that in order for changes in branches to be considered, the programmer must create a pull request after pushing the branch to Github.

**git branch**

When used without arguments, `git branch` will return all available branches in the local repository to the command line. This includes `master`/`main` (which is always included) plus any branch created by other developers currently present in the repository. Note that the `*` symbol shows what branch the local repository is currently in.

    $ git branch
    * develop_readme
      main

You can also append *branch-name* at the end of the command (such as `git branch develop_readme` or `git branch main`). By using `git branch branch-name`, Git will create a separate branch called *branch-name* in the local repository.

    $ git branch demo
    $ git branch
      demo
    * develop_readme
      main

Note that if *branch name* already exists, `git branch branch-name` will return a fatal error. 

    $ git branch develop_readme
    fatal: A branch named 'develop_readme' already exists.

Lastly, to delete a branch, use `git branch -d branch-name`, wherein *branch-name* specifies the name of the branch to be deleted. **This action does not have any safety prompt and cannot be undone.**

    $ git branch -d black_hole
    Deleted branch black_hole (was 4fe57c7).

**git checkout** *branch-name*

Like what its namesake implies, `git checkout branch-name` switches the current branch to *branch-name*. The command also displays current modifications made to the code in that branch.

    $ git checkout develop_readme
    Switched to branch 'develop_readme'
    M       README.md

A useful shortcut to creating a nonexistent branch and automatically switching to it can be done with `git checkout -b branch-name`. The command both creates *branch-name* and switches the branch to that name. If *branch-name* already exists, the terminal will return an error.

**git diff** *branch-name*

Displays code revisions between *branch-name* and *master*. Output is displayed to the command line. To exit, enter `q`.

#### git diff branch-name

Compares code between `branch-name` and `master`. Displays output to the command line.

#### git merge branch-name

Merge changes between `branch-name` to `master`

Check if this line of code is included in main.