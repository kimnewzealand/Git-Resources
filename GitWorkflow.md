# GIT Workflow


+ [Initial set up](#initializing-your-repository-set-up)
+ [Basic workflow](#basic-workflow)
+ [Collaberative workflow](#collaberative-workflow)


<br><hr>


## Initial set up

1. Make a new repository on github, which is the `origin` (in this case this is the same as the `upstream`)  
2. Copy the HTTPS link in github.com using the clipboard, as GithubLink.
3. Make a new folder in your working directory if necessary.

```
$ mkdir project
```

4. In the command line, browse to the folder, or browse in explorer right click "Git Bash here" on the folder. 

5. This folder is not currently under version control so the command init will create  a new subdirectory named .git that contains all of your necessary repository files and a Git repository skeleton. At this point you are working on your `master` branch, as a default.

```
#-- Initialize git tracking
$ git init
$ ls -a
.	..	.git
```
Add the remote repository using the link on the clipboard.

```
$ git remote add origin GithubLink
```
<br><hr>

**An existing project on Github**

1. In the command line, browse to the folder, or browse in explorer right click "Git Bash here" on the folder.
2. Make a clone copy of the remote repo. The clone command will create a new directory named after the project with a copy of the files and will also will create  a new subdirectory named .git

```
-- Making a copy of the repository
$ git clone remotelink
```

3. In the command line, browse to the new folder, or browse in explorer right click "Git Bash here" on the folder.

<br><hr>

## Basic workflow

Let's check the status of our project to ensure everything is set up correctly.

```
$ git status
On branch master

No commits yet

nothing added to commit but untracked files present (use "git add" to track)

```

At this point, still nothing in your project is tracked. To start version control we will need to create files or make changes then add and commit files. 

```
$ git add -A
$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

        new file:   filename.md



$ git commit -m "commit message"
[master (root-commit) ba5df6a] Commit git simple example
 1 file changed, 98 insertions(+)
 create mode 100644 filename.md
```

Push the file from the `local repository` `master` branch to the `origin` or `remote repository` `master` branch. The -u is used for the first push to set the `upstream` link between the two repositories.

```
$ git push -u origin master
```

Each file in your `working directory` can be tracked or untracked. 
- Tracked files are files that were in the last snapshot; they can be unmodified, modified, or staged.  
- Untracked files are any files in your working directory that were not in your last snapshot and are not in your staging area.


<br><hr>

## Collaberative workflow

Follow the basic workflow, except first update your local repo using the pull command.

```
git pull origin master
```


