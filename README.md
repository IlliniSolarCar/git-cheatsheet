# The Git Cheatsheet
This cheatsheet is a general overview of the basics of git. It is an overview of using git. 
If you aren't familiar with what git is you'll want to learn that for this all to make sense: https://git-scm.com/book/en/v2/Getting-Started-What-is-Git%3F

The cheatsheet assumes you are using the git command line interface. As an engineer you should really be using the cli, not an app. (You will have to use the CLI in classes!)

For info on how we organize and utilize our various repos see the relevant pages on the wiki. 

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

d.![Pull Request 3](https://raw.githubusercontent.com/IlliniSolarCar/git-cheatsheet/images/pr3.PNG)

e.![Pull Request 4](https://raw.githubusercontent.com/IlliniSolarCar/git-cheatsheet/images/pr4.PNG)

## Merges
Merging is when you combine two commit histories back into one. There are a couple of different reasons a merge may be neccessary. 
First, if you are collaborating on a branch and someone else pushes after you last pulled and you try to commit you will need to merge. This is because you each created a separate history from that common history. This is why, for collaborative branches especially, you should push/pull often and pull before pushing. If you worked on different things git may be able to merge automatically. Otherwise see the section on merge conflicts.
Second, you may want to merge your branch into another branch. For team-wide persitant branches (such as master) you will need to open a pull request to get permission to merge. In other cases, such as merging a feature into a working branch for a project, you can merge yourself. To initiate this you will use the following command:
```bash
git checkout <name of branch you want to merge code into>
git merge <name of branch you are merging code from>
```
You will then have to push your merge changes to remote so that everyone else has the merged branch. In this situation you have probably changed more things than in the first situation so you are more likely to have a conflict. See the next section for resolving that. 

## Merge Conflicts
Merge conflicts __will__ happen sometimes. Generally either you or git is confused. 
You may be confused about what the actual status of the branch(es) is - for example someone else made a commit you didn't know about or you forgot to first deal with pushing the submodule(s).
Git may be confused about what you actually meant to change and therefore doesn't merge automaticlly. This is common - due to comments, whitespace, etc. git may fail to merge automatically and the fix may be trivial. 
You can see what the conflict is by opening the conflicting file(s) and looking for:
```back 
<<<<<<<  HEAD
__some code from the branch you are merging code into__
=======
__the code from the branch you are merging code from__
>>>>>>> [branch you are merging from]
```
You'll want to figure out what code from there you want. It may be only that from one branch or a combination of it. You can resolve the conflict in the file so it looks as you intend (don't forget to delete all fo the conflict artifacts such as the "======="). Alternatively, depending on what you want you may be able do it from the git cli. 

The variety of causes of merge conflicts makes it impossible to write a guide for all of them here. Once you figure out what you want the internet can help you figure out how to get there. Here are some external resources:

https://www.atlassian.com/git/tutorials/using-branches/merge-conflicts

https://www.git-tower.com/learn/git/ebook/en/command-line/advanced-topics/merge-conflicts

https://git-scm.com/docs/git-merge

Until you are very comfortable with git (meaning you aren't reading this cheatsheet) you should probably ask a more experienced member with help for all but the basic conflicts. 

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

## Help
For help with git for hardware post on <i>#elec-cad</i>. For help with git for firmware post to <i>#elec-code</i>