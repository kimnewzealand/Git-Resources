# GIT Simple Example New Project Using Git Bash and R


+ [Start a new project](#start-a-new-project)
+ [Create a new file](#create-a-new-file)
+ [Initialise git tracking](#initialise-git-tracking)
+ [Add file](#add-file)
+ [Publish file](#publish-file)
+ [Resources](#resources)



<br><hr>


### Start a new project

1. Add a new `remote repository` in github.com with repository name **BookRecipes**, which is also known as the `origin`.  
2. Create a new local `working directory` **MyRecipes**. 

### Create a new file

1. Create a a file in called **CrepeRecipe.md**, which is a basic recipe for making crepes, in the local `working directory` **MyRecipes**

```
# Load the package makecrepe
library(makecrepe)

# Create a vector with the ingredients
ingredients <- c(1 cup flour,
      1 tablespoon sugar ,
      1/4 teaspoon salt ,
      1 1/2 cups whole milk,
      3 tablespoons butter,
      4 large eggs)

# Cook crepe using crepe functions from the package crepe
melt(butter)
mix(ingredients)
heat(pan)
cook(ingredients,pan)
```

### Initialise git tracking

1. Open git bash and change directory to `working directory` **MyRecipes**.

```
Home@LAPTOP-222WWW MINGW64 ~
$ cd Documents

Home@LAPTOP-222WWW MINGW64 ~/Documents (master)
$ cd MyRecipes

Home@LAPTOP-222WWW MINGW64 ~/Documents/MyRecipes (master)
```


2. Initialize git tracking and version control on `working directory` **MyRecipes**.

```
$ git init
```

3. Copy the HTTPS link in github.com using the clipboard to add the `remote repository` or `origin`  as https://github.com/kimnewzealand/BookRecipes.git.

```
$ git remote add origin https://github.com/kimnewzealand/BookRecipes.git
```

### Add file

1. Add the file snapshot to the `index / staging area` locally.

```
$ git add "CrepeRecipe.md"
```

### Publish file

1. Commit the file with the snapshot to the `local repository` locally.

```
$ git commit -m "My first crepe recipe submission to the Recipe Book"
```

2.  Push the file from the `local repository` `master` branch to the `origin` or `remote repository` `master` branch. The -u is used for the first push to set the `upstream` link between the two repositories.
 
```
$ git push -u origin master
```

## Resources

+ [Happy Git and GitHub for the useR](http://happygitwithr.com/rmd-test-drive.html)
+ [Pro Git book, written by Scott Chacon and Ben Straub ](https://git-scm.com/book/en/v2) under the Creative Commons Attribution Non Commercial Share Alike 3.0 license.
+ [Version Control with Git by Software Carpentry](http://swcarpentry.github.io/git-novice/)
