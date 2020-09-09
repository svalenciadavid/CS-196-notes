
# Git Guide
Git is a Version Control System (VCS), it tracks changes on computer files and allows for collaboration between developers.

[**Slides Pt.1**](https://docs.google.com/presentation/d/18Jvsq6q1Uaj6YXhvrs2-u-tzp5ocExmF52qVz2vzhRI/edit#slide=id.g7c80c909b0_2_44) 

[**Youtube Video Pt.1**](https://www.youtube.com/watch?v=P_rISC16nP4&feature=youtu.be)


----
Part 2 (Everything that follows the log command)

[**Slides Pt.2**](https://docs.google.com/presentation/d/1I-xHDehKWuUS2DZcNjOAjn9a1mqk_e-bY5vW_W-V8zQ/edit#slide=id.g97303a99ab_0_87) 

[**Youtube Video Pt.2**](TBA)

---
[On Saving Username and Password-> secure method is SSH](https://stackoverflow.com/questions/35942754/how-to-save-username-and-password-in-git-gitextension)

##  The four environments in Git
**1.  _Working Directory_**
	The environment same as OS knows. All files tracked or un-tracked

**2. _Staging Area_**
	Contains changes that you want git to know about. (added files, deleted, edits)

**3. _Local Repository_**
	The repository in your computer (folder) 

**4. _Remote Repository_**
	A mirror of your local repo, contains the history of your changes- people can see it

## Git commands

### init
Adds a .git to directory- Summons git

```bash
$ git init
```

### clone
Copy a git repo from remote source

On the webpage of the repository, the url is located if you click the green code button and then copy the link underneath " Clone with HTTPS " 

**Note:** Running this command will copy the repo and place it where you currently are in bash.

```bash
$ git clone <web-url-from-remote>
```

### pull
Pulls latest changes done to remote repo
```bash
$ git pull
```

### add
Adds files to staging area so git can track them
```bash
$ git add <file-name>
$ git add <file-name> <another-file-name>
```
In this case we use the **" --all "** flag to stage **all** changes
```bash
$ git add --all
```
Alternatively you can use **" . "** to stage all changes in current directory
```bash
$ git add .
```
The **" -u "** flag stages modifications and deletions, no new files.
```bash
$ git add -u
```

### commit
Saves changes to local repo, makes a "snapshot"

Do this one ALWAYS
```bash
$ git commit -m "insert-message-here"
```
This one is only for modified/deleted files, it does git add -u and git commit -m at the same time!
```bash
$ git commit -a -m "instert-message-here"
```
you can also combine the -a and -m flags together.
If you don't type -m after git commit, it will open a text editor in the terminal for you to write a commit message.

**_Note:_** For better commits, follow this guide on 
[**Conventional Commits**](https://www.conventionalcommits.org/en/v1.0.0/ "https://www.conventionalcommits.org/en/v1.0.0/")

### push
Transfers commits from local repo to a remote repo (changes uploaded online)

This will send your commits off (get uploaded)
```bash
$ git push
```
### log
Shows commit messages

This will show the commit message you just created
```bash
$ git log -1
```
or you can use the --oneline flag to view a condensed version of all the commits
```bash
$ git log --oneline
```
### fetch
Brings in changes, but does not update your local repository working state. 
A good way to understand this is that Git pull finds AND updates your repo with the latest changes but fetch only finds the changes with other branches. 
```bash
$ git fetch
```
You can also specify a specific branch on the remote you want to fetch
```bash
$ git fetch "xyz"
```
https://git-scm.com/docs/git-fetch has more info on how you can use fetch

## About merge conflicts
A merge conflict happens when there are conflicting changes on the same line

In this case, somebody made a change to this python file, as I was making changes in my local repo, as I tried to pull the changes, because we both had worked on the same file and edited the same line, git does not know which change to keep/get rid of, so it lets you choose.
```python
<<<<<<<<<<<< HEAD
print("hello")
============
print("NO I actually wanted to print THIS!")
>>>>>>>>>>>>>a486cae486a
``` 
The solution, is to simply pick what change you want to pick, either one, the other, or both! Then, get rid of the separators git shows(<<<HEAD and the ID)
```python
print("NO I actually wanted to print THIS!")
```

# Branching
How to isolate work in progress, from completed work (in master branch), AKA: Version control. 

## Branching commands
Branching is used to isolate work in progress, from completed work (in master branch), AKA: Version control. 

**Note:** Merging conflics will still happen when merging the branch back into master (aka when pushing a completed feature to the project)

### branch
The first line of code creates a branch, the next, lists all branches.
```bash
$ git branch hello
$ git branch
hello
* master
```
### checkout
How we navigate between branches (moves the HEAD pointer and updates working directory with files stored in the branch).

-b flag will create AND move to the new branch
```bash
$ git checkout <branch-name>
$ git checkout -b <branch-name>
``` 
### merge
When you are done making changes to your branch, you can merge into the master using this command. This also works for merging two non-master branches together.
```bash
$ git merge <branch-you're-merging-into>
``` 
**Tips:** 
* Keep your master branch clean (make sure you can always run it without issues)
* Name your branches well ( feat/feat-name)
