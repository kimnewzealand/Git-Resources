# GIT Simple Example File with Changes Using Git Bash and R

+ [Status of file](#status-of-file)
+ [Change file](#change-file)
+ [Add file](#add-file)
+ [Publish file](#publish-file)
+ [Resources](#resources)


<br><hr>


### Status of file

Before we make changes to a file in the `working directory` and add and commit to the `origin`, first we will take a look at the status of the file and the log of our initial commit, in `GitExampleNew.md`.

```{bash}
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.

no changes added to commit (use "git add" and/or "git commit -a")

$ git log
commit ba5df6a41a26433534b011e10a236b50bacda40f (HEAD -> master, origin/master)
Author: Kim Fitter <xx@xxx.com>
Date:   Thu Mar 15 12:22:00 2018 +1300

    My first crepe recipe submission to the Recipe Book
```

### Change file

1. On testing the crepe recipe, the crepes tasted like omelettes so we will change the recipe in the file called **CrepeRecipe.md** in the local `working directory` **MyRecipes**, from 4 eggs to 2 eggs.

```{r}
# Load the package crepe
library(crepe)

# Create a vector with the ingredients
ingredients<- c(1 cup flour,
      1 tablespoon sugar ,
      1/4 teaspoon salt ,
      1 1/2 cups whole milk,
      3 tablespoons butter,
      2 large eggs)

# Cook crepe using crepe functions from the package crepe
melt(butter)
mix(ingredients)
heat(pan)
cook(ingredients,pan)
```



### Add file

1. Add the file to the `Index/Staging` area again.

```{bash}
$ git add "CrepeRecipe.md"
```

### Publish file

1. Commit the file to the `local repository` with a new message.

```{bash}
$ git commit -m "Updates to crepe recipe submission to the Recipe Book"
[master eff78f8] Updates to format
 1 file changed, 1 insertion(+), 1 deletions(-)
```

2.  Push the file from the local repository `master` branch to the remote `origin` repository `master` branch. This time we don't need to use the -u.
 
```{bash}
$ git push  origin master
Counting objects: 3, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 304 bytes | 152.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/kimnewzealand/Recipes.git
   ba5df6a..eff78f8  master -> master
```

## Resources

+ [Happy Git and GitHub for the useR](http://happygitwithr.com/rmd-test-drive.html)
+ [Pro Git book, written by Scott Chacon and Ben Straub ](https://git-scm.com/book/en/v2) under the Creative Commons Attribution Non Commercial Share Alike 3.0 license.
+ [Version Control with Git by Software Carpentry](http://swcarpentry.github.io/git-novice/)
