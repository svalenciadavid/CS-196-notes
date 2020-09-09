# Git Guide
Git is a Version Control System (VCS), it tracks changes on computer files and allows for collaboration between developers.

[**Slides**](https://docs.google.com/presentation/d/18Jvsq6q1Uaj6YXhvrs2-u-tzp5ocExmF52qVz2vzhRI/edit#slide=id.g7c80c909b0_2_44) 

[**Youtube Video**](https://www.youtube.com/watch?v=P_rISC16nP4&feature=youtu.be)

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

### checkout
-b creates a new branch
