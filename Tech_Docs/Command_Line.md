# Table of Contents

- [Basic Commands](#basic-commands)
- [Git Commands](#git-commands)
- [Cloning Repository](#cloning-repository)
- [Committing with Terminal](#committing-with-terminal)

# Basic Commands

| Command | Description |
| :---: | --- |
| **pwd** | Returns the directory you are currently in |
| **cd** | Navigates between files/folders in your computer |
| **ls** | Lists the files and folders in directory |
| **mkdir** | Makes a new directory |
| **code .** | Opens current folder inside of VS Code |

## Short Cuts

**“~”** is used to represent your home directory. Using **“cd ~/Folder”** will take you from your home directory to a new folder.

<img src="images/command_line/home-directory.png" alt="Terminal showing cd ~/Github" width="670">

**“. .”** can be used similarly to navigate back to a previous folder.

<img src="images/command_line/parent-directory.png" alt="Terminal showing cd .." width="656">

# Git Commands

| Command | Description |
| :---: | --- |
| **git init** | Creates a new git repository |
| **git status** | Will show your current branch as well as changed and staged files |
| **git add** | Tells Git what file you want to save in your next commit (staging) |
| **git commit -m “”** | Commits changes with a message inside of the “” |
| **git remote add origin URL** | Connects a local repository (your device) to a remote repository (Github) |
| **git clone URL** | Connects a remote repository to a local repository |
| **git branch -M main** | Sets branch to Main |
| **git push** | Push commits to Github |
| **git diff** | Shows you have made but haven't staged |

# Cloning Repository

1. Navigate to the repository you want to clone and copy the URL.

<img src="images/command_line/copy-repository-url.png" alt="GitHub repository URL highlighted" width="760">

2. Open your terminal and using **cd ~** navigate to your Github folder.

<img src="images/command_line/navigate-github-folder.png" alt="Terminal navigating to Github folder" width="760">

3. Use **git clone** and paste the URL after.

<img src="images/command_line/git-clone.png" alt="Terminal showing git clone command" width="760">

4. To make sure everything was copied successfully use **ls** in terminal; the newly copied repository should appear.

<img src="images/command_line/verify-clone-ls.png" alt="Terminal showing cloned repository after ls" width="760">

# Committing with Terminal

1. Use **git status** to check your branch, what has/hasn't been staged, and untracked files.

<img src="images/command_line/git-status.png" alt="Terminal showing git status" width="760">

2. Use **git add <file>** to stage for commit and then use **git status** after to verify.

<img src="images/command_line/git-add.png" alt="Terminal showing git add and git status" width="760">

3. Run **git commit -m** to commit your staged changes.

<img src="images/command_line/git-commit.png" alt="Terminal showing git commit" width="760">

4. Run **git push** to move all local commits to the remote repository.

<img src="images/command_line/git-push.png" alt="Terminal showing git push" width="760">

5. Check the remote repository to confirm and you are done.

### Author: Amani Murillo
