# The Git Cheatsheet

## Basic Commands

### git clone
```bash
git clone <repository url>
```
This is the command which copies a repository (a project) from GitHub to our local drive.

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
1. 
a. ![Clone Image](https://raw.githubusercontent.com/IlliniSolarCar/git-cheatsheet/images/clone.PNG)
b.
```bash 
git clone <repository url>
```
2. 
```bash 
git checkout -b <new branch name>
```
3.
Make some changes to some files
4.
```bash
git add <for each file that you modified>
```
5.
```bash
git commit -m "<A relevant commit message>"
```
6.
```bash
git push origin <branch name>
```
7. Repeat steps 3 through 6 until you're finished with the new feature.
8. Submit a pull request.
a. Go to the repository webpage.
b.![Pull Request 1](https://raw.githubusercontent.com/IlliniSolarCar/git-cheatsheet/images/pr1.PNG)
c.![Pull Request 2](https://raw.githubusercontent.com/IlliniSolarCar/git-cheatsheet/images/pr2.PNG)
b.![Pull Request 3](https://raw.githubusercontent.com/IlliniSolarCar/git-cheatsheet/images/pr3.PNG)
c.![Pull Request 4](https://raw.githubusercontent.com/IlliniSolarCar/git-cheatsheet/images/pr4.PNG)

## Merge Conflicts (AHHH!!!!)

https://stackoverflow.com/questions/161813/how-to-resolve-merge-conflicts-in-git
To be honest, if there's a merge conflict, you should ping someone on Slack (ex. @aidan.san)

## Miscellaneous (Less Frequently Used) Commands

### git cherry-pick
```bash
git cherry-pick <commit hash>
```
This command let's us copy a commit from a different branch onto our current branch.
**When to use this:** When we committed to the wrong branch and want to take the commit from the other branch

### git stash
```bash
git stash (pop)
```
This command let's us save the current repository state without making a commit. When we add pop at the end, we take the save state we had and put it back into the working directory.
**When to use this:** We have some changes we want to save, but they are not enouhgh to make a full commit.

## Contact
Feel free to shoot me a slack message @aidan.san or an email at asan2@illinois.edu if you have any questions.
