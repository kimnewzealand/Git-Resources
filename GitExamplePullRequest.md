# GIT Simple Example Pull Request with Branches Using Git Bash and R

+ [Showing remotes](#showing-remotes)
+ [Fork files](#fork-files)
+ [Clone repo](#clone-repo)
+ [Switching branches](#switching-branches)
+ [Add file](#add-file)
+ [Publish file](#publish-file)
+ [Create pull request](#create-pull-request)
+ [Resources](#resources)


<br><hr>

### Showing remotes

In `GitExampleCHanges` we published a crepe recipe **CrepeRecipe.md** after making one change. Before we do any further work, we will consider remotes. So far we have been working with `origin` in kimnewzealand github.

Martha Stewart has got a GitHub account and publishes her recipes there.


### Fork files

1. We are now going to make some proposed changes to push back to her repo. First we need to fork the repo https://github.com/martha/Recipes/ in GitHub github.com using the fork button to https://github.com/kimnewzealand/Recipes.


### Clone repo

1. We then return to the Git Bash command line to prepare our local environment. First clone the repo `Recipes` to download a copy of the repo `Recipes` locally.

```{bash}
git clone https://github.com/kimnewzealand/Recipes 
```

If you are going to work with a remote with a name other than origin, eg upstream then use this command:

```{bash}
git remote add upstream https://github.com/kimnewzealand/Recipes 
```


```{bash}
git cd Recipes 
```

### Switching branches


1. Let's take a look at the details of the remote. This git command lists the URL for the remote repository as well as the tracking branch information. Currently our `HEAD` is pointing to the `master` branch. 

```{bash}
$ git remote show origin
* remote origin
  origin https://github.com/kimnewzealand/Recipes.git (fetch)
  origin https://github.com/kimnewzealand/Recipes.git (push)
  HEAD branch: master
  Remote branches:
    master                               tracked
    dev-branch                           tracked
  Local branch configured for 'git pull':
    master merges with remote master
  Local ref configured for 'git push':
    master pushes to master (up to date)
```


2. As we can see, martha has a `dev-branch` so we will switch to this branch and work on one of her in development crepe recipes.

```{bash}
$ git checkout dev-branch
Switched to branch 'dev-branch'
```

In R if you make changes to an R package then remember to run devtools:check() to regenerate the documentation and rebuild the package.

### Add file

1. Once we have made changes we then add the file `CrepeRecipeProposal.md` to the `Index/Staging` area.

```{bash}
$ git add "CrepeRecipeProposal.md"
```

### Publish file

1. Commit the file to the `local repository` with a new message.

```{bash}
$ git commit -m "Updates to crepe recipe submission to the Recipe Book"
[master eff78f8] Updates to format
 1 file changed, 1 insertion(+), 1 deletions(-)
```

2.  Push the file from the local repository `dev-branch` branch to the remote `origin` repository `dev-branch` branch. 
 
```{bash}
$ git push -u origin dev-branch
Counting objects: 2, done.
Delta compression using up to 5 threads.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 394 bytes | 182.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/kimnewzealand/Recipes.git
   ca5df6a..egf78f8  dev-branch -> dev-branch
```

### Create a pull request

Go to https://github.com/martha/Recipes/ in GitHub and create a new pull request using the "New pull request" button, then "Create pull request" botton adding comments.

## Resources

+ [Happy Git and GitHub for the useR by Jennifer Bryan](http://happygitwithr.com/rmd-test-drive.html) adapted under  [Creative Commons Attribution-NonCommercial 4.0 International License.](https://creativecommons.org/licenses/by/4.0/)
+ [Pro Git book, written by Scott Chacon and Ben Straub ](https://git-scm.com/book/en/v2) adapted under the [Creative Commons Attribution Non Commercial Share Alike 3.0 license](https://creativecommons.org/licenses/by/3.0/).
+ [Version Control with Git by Software Carpentry](http://swcarpentry.github.io/git-novice/) adapted under the [Attribution 4.0 International (CC BY 4.0 license](https://creativecommons.org/licenses/by/4.0/)