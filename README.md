# hello-world
new practise
# Learning Git
## _Version Control_
Version Control is a system that allows you to revisit various versions of a file or set of files by recording changes. Through version control, one can revert a file or project to a previous version, track modifications and modifying individuals, and compare changes. By utilizing a Version Control System (VCS), mistakes with files can easily be rectified.
- Local Version Control
- Centralized Version Control
- Distributed Version Control
## _Introduction to Git_
1. **Snapshot** :
 Git is a DVCS that stores data in a file system made up of snapshots. Each time you save a changed version of your project — called commit — Git creates a snapshot of the file and stores a reference to it. If the file has not changed, Git only stores a reference to the already-stored identical version of it.
 2. **Local Operations** :
 Git mostly relies on local operations because most necessary information can be found in local resources. This allows for process expediency because a project’s history resides on the local disk, eliminating the need to fetch history information from the server, and allowing one to continue work on a project even when not online or on a VPN.
 3. **Tracking Changes** :
 Every single change applied to any file or directory is tracked by Git. And, as the gatekeeper, Git will always detect file corruption or loss of information in transit.
 4. **Loss of Data** :
 Git is set up to greatly minimize the possibility of irreversible damage to files, such as accidentally lost data. Git makes it extremely difficult for a snapshot of your file that is committed to be lost.
 5. **States** :
 Files in Git can reside in three main states: committed, modified and staged.
 - _Committed_ : Data is securely stored in a local database
 - _Modified_ : File has been changed but not committed to the database
 - _Staged_ : Flagged a file’s changed version to be committed in the next snapshot
 ![Image](https://blog.udemy.com/wp-content/uploads/2015/08/image066.png)
# Let's start Git !!!
1. Download the latest version 
2. Install in 3 Ways
  - Install as a package
  - Install via another installer
  - Download and compile the source code
## Mac OS X
1. Terminal 
2. [Git Website for Mac](http://git-scm.com/download/mac)
3. [GitHub for Mac](http://mac.github.com)
## Windows
1. [Git Website for Windows](http://git-scm.com/download/win)
2. [GitHub for Windows](http://windows.github.com)
## Linux 
 1. Package Manager
You can try installing Git via your distribution’s inherent package management tool.
- For **Fedora**:
```

$ sudo yum install git

```
- For **Ubuntu**:
```
$ sudo apt-get install git

```
2. [Git Website for Linux](http://git-scm.com/download/linux)

# Graphical Clients

Git includes inherent Graphical User Interface (GUI) tools. However, users can also utilize third-party tools created for particular platforms.
[GUI Clients for Mac, Windows, and Linux please click](https://git-scm.com/downloads/guis)

# Initial Customization
1. **Configuration of Variables** :
An inherent Git tool called git config allows the setting of configuration variables that control aspects of Git’s operation and look.
2. **Identity Setting** :
After installing Git, users should immediately set the user name and email address, which will be used for every Git commit.
_Type the following into Terminal or Command Line:_
```
git config --global user.name "Jane Smith"
git config --global user.email "example@email.com"

```
_To confirm that you have the correct settings, enter the following command:_
```
git config --global user.name (should return Jane Smith)
git config --global user.email (should return example@email.com)

```
3. **Default Text Editor** :
Without configuration of a default text editor, Git will use the system’s default editor–most likely Vim. To configure a different text editor, such as Emacs, _type the following into your Terminal or Command Line:_
```
$ git config --global core.editor emacs

```
Check Settings
To check settings, use the git config below _command:_
```
--list 

```
_Example:_

```
$ git config --list
user.name=Jane Smith
user.email=example@email.com
color.status=auto
color.branch=auto
color.interactive=auto
...
```
4. **Getting Help** :
There are three ways to get more information on a particular command, by _accessing the manual:_
```
git help command
git command --help
man git-command

```
# Setting up a Git Repository
1. **Importing** :
To import an existing project or directory into Git, follow these steps using the Terminal or Command Line:
Switch to the target project’s directory
Example:
```
$ cd test (cd = change directory)
```
Use the git init command
```
$ git init
```
**Note: At this stage, you have created a new subdirectory named .git that has the repository files. Tracking has not commenced.**
To start tracking these repository files, perform an initial commit by _typing the following:_
```
$ git add *.c

```
```
$ git add LICENSE

```
```
$ git commit -m “any message here”

```
# Cloning
You can also create a copy of an existing Git repository from a particular server by _using the clone command with a repository’s URL:_
```
$ git clone https://github.com/test

```
By cloning the file, you have copied all versions of all files for a project. This command leads to the creation of a directory called “test,” with an initialized .git directory inside it, which has copies of all versions of all files for the specified project. The command also automatically checks out — or retrieves for editing — a copy of the newest version of the project.
To clone a repository into a directory with another name of your choosing, _use the following command format:_
```
$ git clone https://github.com/test mydirectory

```
The command above makes a copy of the target repository in a directory named **“mydirectory.”**
# Workflow
## Local Repository Structure
The local Git repository has three components:
1. **Working Directory:** The actual files reside here.
2. **Index:** The area used for staging
3. **Head:** Points to the most recent commit
![Image](https://blog.udemy.com/wp-content/uploads/2015/08/image036.png)

# Saving Changes
All files in a checked out (or working) copy of a project file are either in a tracked or untracked state.
## **Tracked** 
Tracked files can be modified, unmodified, or staged; they were part of the most recent file snapshot.
## **Untracked**
Untracked files were not in the last snapshot and do not currently reside in the staging area.
_*After cloning a repository, files have tracked status and are unmodified because they have been checked out but not edited._

# The Life Cycle of File Status
1. After you edit a file, Git flags it as modified because of changes made after the previous commit.
2. You stage the modified file.
3. Then, you commit staged changes.
![Image](https://blog.udemy.com/wp-content/uploads/2015/08/image006.png)

# Check File Status
To determine the state of files, utilize by below command:
```
$ git status

```
On branch master
nothing to commit, working directory clean
_*This information indicates which branch you’re on (we will cover branches in a later section) and states “working directory clean,” which means that files have tracked or modified status at the moment. Also, no untracked files are present because Git has not listed any._
# Tracking and Staging a New File
## **Single File**
Track one file only by using the following format:
```
git add filename

```
## **All Files**
Track all files in a repository by using the following command:
```
$ git add *

```

_*After using these commands, files are tracked and staged for committing._
After adding a new file called EXAMPLE, you would see information regarding changes to be committed when using below command:
```
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD ..." to unstage)

```
```
new file: EXAMPLE

```
This information tells us that there are changes to be committed and that the file has been staged.

# Committing a File
After staging one or multiple files, you should commit the changes and record what you did within the commit message:
```
$ git commit -m “made change x,y,z”

```
_*This step has committed changes for the file or files (you can have one commit message for multiple files, if applicable) to **the HEAD.**_

# Committing All Changes
```
$ git commit -a

```
_*This command commits a snapshot of all modifications to tracked files in the working directory._
# Pushing Changes
Next, you would push changes to a remote repository. We will discuss remote repositories in more depth in the next section. For now, we will look at a general overview of pushing changes to remotes.
_Example:_
```
$ git push origin master

```
_*This command pushes changes from the local **“master”** branch to the remote repository named **“origin”**.
*For cloned repositories, Git will automatically give the name **“origin”** to the server from which you cloned and the name **“master”** to your local repository. However, these names can be changed by the user._
# Stashing Changes
When you are not ready to commit changes but do not want to lose them either, git stash is a great option. This command temporarily removes changes and hides them, giving you a clean working directory. When you are ready to continue working on the changes, simply use the git stash apply command to retrieve the hidden changes.
