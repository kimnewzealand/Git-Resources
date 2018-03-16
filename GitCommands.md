# GIT Commands


+ [GIT Terminology](#git-vocabulary)
+ [Working with branches](#working-with-branches)
+ [GIT Tags](#git-tags)
+ [GIT Stash](#git-stash)
+ [Renaming, moving and deleting files/folders/repos](#renaming-moving-and-deleting)

<br>

## GIT Terminology

+ `origin`:  connection pointing to the remote repository

+ `master`: name of your default branch. A branch in Git is simply a lightweight movable pointer to a commit.

+ `HEAD`: pointer to the last commit of the branch you are currently on. If you are on the master branch, then HEAD and master will refer to the same commit.

## GIT Commands

Initialise  

+ `git init <repository name>` : Initialize a new local repository

Remotes  

+ git remote add <remote name> <url>: Creates a new connection to a remote repository  <remote name> is the shortcut for the <url> and is typically set to 'origin'
+ `git remote show <remote name>` This command shows which branch is automatically pushed to when you run git push while on certain branches. It also shows you which remote branches on the server you don't yet have, which remote branches you have that have been removed from the server, and multiple local branches that are able to merge automatically with their remote-tracking branch when you run git pull.
+ `git remote rename <remote name> <new remote name>` to rename a remote
+ `git remote remove <remote name>` to remove a remote

Branches  

+ `git branch <new branch name>` to add a new branch
+ `git checkout <branch name> <filename>` checks out (i.e., restores) an old version of a file
+ `git checkout -- <file>...` to discard changes in working directory

Status  

+ `git status`: shows which files have changed/new in your repository.  
+ `git diff`: shows the changes you made to the file  
+ `git diff --staged` shows us the difference between the last committed change and what's in the staging area

Add  

+ `git add` to add from your working directory to your staging area
+ `git add <filename>` to stage a file  
+ `git add -A` stages all new, modified and deleted

Commit  

+ `git commit` -m "<message>"

Fetch  

+ `git fetch` to get any new work since last clone or fetch.  Fetch doesn't however merge remote work with our work.

Pull  

+ `git pull` to automatically fetch and then merge that remote branch into your current branch

Push  

+ `git push` to add the files to your remote git 

Cleaning up your working directory:

+ `git clean -n`: dry run, shows all files that will be deleted
+ `git clean -df`: removes all untracked files/folders


Note on adding files to the remote:    

+ When it is your first push from a repo, you will first have to make the link between the local and remote repository via: `git push  --set-upstream origin master`, or shorter `git push -u origin master`. As of then, `git push` will refer to the upstream branch you've set: i.e. origin/master.


<br><hr>


## GIT tags

Git has the ability to tag specific points in history as being important. Typically people use this functionality to mark release points (v1.0, and so on). Use the command tag.

```
$ git tag v0.1
```


<br><hr>

## GIT Aliases

+ `git config --global alias.<shortname> <command>` to set up an alias for each command using git config


<br><hr>

## Resources

+ [Atlassian GIT tutorials](https://www.atlassian.com/git/tutorials/git-stash)

+ [Git in practice, by Mike McQuaid](https://github.com/GitInPractice/GitInPractice#readme)

+ [Youtube tutorials by Corey Schafer](https://www.youtube.com/watch?v=HVsySz-h9r4&list=PL-osiE80TeTuRUfjRe54Eea17-YfnOOAx)