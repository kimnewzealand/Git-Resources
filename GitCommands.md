# GIT Commands

+ [GIT Terminology](#git-terminology)
+ [Working with branches](#working-with-branches)
+ [GIT Tags](#git-tags)
+ [GIT Aliases](#git-aliases)
+ [Edit in UNIX](#edit-in-unix)
+ [Resources](#resources)


<br>

## GIT Terminology

+ `origin` : connection pointing to the remote repository

+ `master` : name of your default branch. A branch in Git is simply a lightweight movable pointer to a commit.

+ `working directory` : local repository

+ `.git directory` : Git stores all of its repository data in the .git directory. This is created when a local repository is initialised using the `init` command.

+ `.git.ignore` : Git uses this file to determine which files and directories to ignore, before you make a commit.

+ `hash`:  the commit command creates a unique ID called a hash, which is an absolute path.

+ `HEAD` : pointer to the last commit of the branch you are currently on. If you are on the master branch, then HEAD and master will refer to the same commit. This is a relative path. To see the previous commit use `HEAD~1`


## GIT Commands

Initialise

+ `git init <local repository name>`initialises a new local repository

Remotes

+ `git remote add <remote name> <url>` creates a new connection to a remote repository  <remote name> is the shortcut for the <url> and is typically set to 'origin'
+ `git remote show <remote name>` shows which branch is automatically pushed to when you run git push while on certain branches. It also shows you which remote branches on the server you don't yet have, which remote branches you have that have been removed from the server, and multiple local branches that are able to merge automatically with their remote-tracking branch when you run git pull.
+ `git remote rename <remote name> <new remote name>` rename a remote
+ `git remote remove <remote name>` remove a remote
+ `git remote -v` lists the remotes that are configured

Branches

+ `git branch <new branch name>` adds a new branch, a structure with trees for saved states of files
+ `git checkout <branch name> <filename>` checks out (i.e. switches to another version) an old version of a file
+ `git branch` lists all of the branches in a repository, with a * next to the branch you are currently on
+ `git checkout <branch-name>` switches to another branch-name
+ `git checkout -b branch-name>` creates the branch and switches you to it
+ `git merge source destination` merges two branches

Status

+ `git status` shows which files have changed/new in your repository
+ `git diff` shows the changes you made to the file
+ `git diff --staged` shows the difference between the last committed change and what's in the staging area
+ `git diff directory` shows the changes to the files in the directory
+ `git diff -r HEAD`  -r flag refers to compare to a particular revision
+ `git log` view the log of the project's history
+ `git show <hash>` view the details of a specific commit, with the first few characters of the commit's hash
+ `git annotate <filename>` shows who made the last change to each line of a file and when

Clone

+ `git clone <remote name>` to clone a repo and download a copy of a repo to a local folder. This automatically creates the remote called origin.

Add

+ `git add` adds from your working directory to your staging area, ie specifies what will go in a snapshot
+ `git add <filename>` stages a file
+ `git add -A` stages all new, modified and deleted
+ `git add <foldername>/*` adds folder and contents to your staging area

Remove

+ `git clean -n` shows a list of files that are in the repository, but whose history Git is not currently tracking.
+ `git clean -f` will then delete those files.

Undo

+ `git reset` undo ALL changes that have been staged with git add
+ `git reset HEAD <filename>` undo changes to a specific filename that have been staged on HEAD

Commit

+ `git commit -m "<message>"` commits the file with the snapshot to the `local repository` locally. The commit records the changes to the file ie actually takes the snapshot and makes a permanent record of it

Fetch

+ `git fetch` gets any new work since last clone or fetch.  Fetch does not however merge remote work with our work.

Pull

+ `git pull` automatically fetches and then merges that remote branch into your current branch

Push

+ `git push` adds the files to your remote git


Note on adding files to the remote:

+ When it is your first push from a repo, you will first have to make the link between the local and remote repository via: `git push  --set-upstream origin master`, or shorter `git push -u origin master`. As of then, `git push` will refer to the upstream branch you've set: i.e. origin / master.


<br>


## GIT tags

Git has the ability to tag specific points in history as being important. Typically people use this functionality to mark release points (v1.0, and so on). Use the command tag.

```
$ git tag v0.1
```


##  GIT Aliases

+ `git config --global alias.<shortname> <command>` to set up an alias for each command using git config.


## Edit in Unix

+ `nano filename` will open filename for editing (or create it if it doesn't already exist). Ctrl-O: save the file ('O' stands for 'output'). Shift zz: exit the editor.

## Resources

+ [Happy Git and GitHub for the useR by Jennifer Bryan](http://happygitwithr.com/rmd-test-drive.html) adapted under  [Creative Commons Attribution-NonCommercial 4.0 International License.](https://creativecommons.org/licenses/by/4.0/)
+ [Pro Git book, written by Scott Chacon and Ben Straub ](https://git-scm.com/book/en/v2) adapted under the [Creative Commons Attribution Non Commercial Share Alike 3.0 license](https://creativecommons.org/licenses/by/3.0/).
+ [Version Control with Git by Software Carpentry](http://swcarpentry.github.io/git-novice/) adapted under the [Attribution 4.0 International (CC BY 4.0 license](https://creativecommons.org/licenses/by/4.0/)
