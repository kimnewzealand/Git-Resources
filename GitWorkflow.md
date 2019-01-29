# GIT Workflow


+ [Initial set up](#initializing-your-repository-set-up)
+ [Basic workflow](#basic-workflow)
+ [Collaberative workflow](#collaberative-workflow)


<br><hr>


## Initial set up

Once you have [configured Git for use](http://swcarpentry.github.io/git-novice/02-setup/index.html) then you can perform initial set up for the project.

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

Check that this worked running this command to list the remotes that have been configured.

```
$ git remote -v
```

<br><hr>


## Basic workflow

Let's check the status of our project to ensure everything is set up correctly.

```
$ git status
On branch master

No commits yet

nothing added to commit but untracked files present (use "git add" to track)

```

At this point, still nothing in the project is tracked. To start version control we will need to create files or make changes then add and commit files.

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
- Tracked files are files that were in the last snapshot (using the add command); they can be unmodified, modified, or staged.  NOTE Git does not track directories only the files in them.
- Untracked files are any files in your working directory that were not in your last snapshot and are not in your staging area.


<br><hr>

## Collaberative workflow

If you want to propose a change to someone else's repository,`anotherrepo`, then first fork the repo in GitHub.

This creates a copy of the repo `anotherrepo` in your GitHub account.

Go to Git Bash and clone the repo `anotherrepo`.

1. In the command line, go to your root folder, or browse in explorer right click "Git Bash here" on the folder.
2. Make a clone copy of the `anotherrepo` repo. The clone command will create a new directory named after the project with a copy of the files and will also will create  a new subdirectory named .git and a remote called origin.

```
-- Making a copy of the repository
$ git clone anotherrepo
```

Next follow the basic steps above to make changes and push to `anotherrepo`. Ensure you change to the `anotherrepo` folder in Git Bash.

Go to GitHub and the forked `anotherrepo` on your GitHub and create a new pull request.

## Centralised workflow

If you want to work on a centralised repository,`sharedrepo`, at the same time as someone else then you may need to merge your local repo changes with the changes already in the the remote repo before pushing.

```
-- Update the local repo with remote repo
$ git pull origin master
```

remote: Counting objects: 1, done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 1), reused 3 (delta 1)
Unpacking objects: 100% (3/3), done.
From https://github.com/abody/sharedrepo
 * branch            master     -> FETCH_HEAD
Auto-merging abc.txt
CONFLICT (content): Merge conflict in abc.txt
Automatic merge failed; fix conflicts and then commit the result.

Edit the file to and then follow the basic steps above to make changes and push to `sharedrepo`.

Go to GitHub and the forked `anotherrepo` on your GitHub and create a new pull request.

## Resources

+ [Happy Git and GitHub for the useR by Jennifer Bryan](http://happygitwithr.com/rmd-test-drive.html) adapted under  [Creative Commons Attribution-NonCommercial 4.0 International License.](https://creativecommons.org/licenses/by/4.0/)
+ [Pro Git book, written by Scott Chacon and Ben Straub ](https://git-scm.com/book/en/v2) adapted under the [Creative Commons Attribution Non Commercial Share Alike 3.0 license](https://creativecommons.org/licenses/by/3.0/).
+ [Version Control with Git by Software Carpentry](http://swcarpentry.github.io/git-novice/) adapted under the [Attribution 4.0 International (CC BY 4.0 license](https://creativecommons.org/licenses/by/4.0/)
