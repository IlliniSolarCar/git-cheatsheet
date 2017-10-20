# The Git Cheatsheet

## Basic Commands

### git add
```bash
git add <filename>
```
This is the command which allows us to tell git that we want it to watch this file.

### git commit
```bash
git commit -m "<Some relevant message about the changes>"
```
This is the command which tells saves a current save state, based on the changes we have "git added"

### git checkout
```bash
git checkout (-b) <branch name>
```
This is the command which lets you switch branches. When the "-b" flag is there that means that we are making a new branch, if not we are switching to a branch that has already been made.

### git push
```bash
git push origin <branch name>
```
This is the command which pushes our local changes to the server, and updates the server.

### git pull
```bash
git pull origin <branch name>
```
This is the command which pulls down changes that were pushed to the server, and puts the changes into our local directory.

## The Common Workflow

## Miscellaneous (Less Frequently Used) Commands

## Contact
Feel free to shoot me a slack message @aidan.san or an email at asan2@illinois.edu if you have any questions.
