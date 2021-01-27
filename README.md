# TEST REPOSITORY

Repository for testing Git & Github functionality. My personal sandbox. 

## GIT COMMANDS
Entered in the command line.

#### git init

Initializes a local directory as a git repository. Adds git functionality to the specified directory.

#### git clone

Copies the contents of the remote repository to your local machine.

#### git status

Tracks version changes to the file or repository.

#### git add *directory*

Tracks the changes to files and folders in *directory* with the remote repository. Next commit will add the most recent changes to the remote repository.

#### git commit -m *message*

Tells git to set current repository as the latest version. When pushed, will replace remote repository's contents with the last commit.

#### git push origin *directory*

Replaces the **remote** repository with the commit version on your local machine.

#### git push -u origin *directory*

In addition to working the same way as `git push origin directory`, sets an upstream link to your git remote repository. This allows the user to omit `origin directory` in their next `git push`.

#### git remote add origin *link*

Sets the local directory as `master` and associates it to *link*. *Link* is the URL for the Github repository in the remote server.

#### git remote -v

List remote repositories connected to the current directory.

