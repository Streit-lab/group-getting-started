
<p align="center">
  <img src='https://github.com/Streit-lab-training/group-getting-started/blob/master/images/R_github_logo.png' width="40%"/>
</p>

Getting started with R is easy. However, before you dive right in it's important to set everything properly to save you time in the future!

<br>

<br>

<p>
  <img src='https://github.com/Streit-lab-training/group-getting-started/blob/master/images/Rlogo.png' width="15%"/>
</p>

***

If you haven't done already, go ahead and download [R](https://cloud.r-project.org/) and [R studio](https://rstudio.com/products/rstudio/download/#download)

*Now before jumping ahead let's take a look at GitHub*

<br>

<br>

<p>
  <img src='https://github.com/Streit-lab-training/group-getting-started/blob/master/images/github_logo.png' width="20%"/>
</p>

***

You can analyse data immediately without using GitHub. However, GitHub helps in a few ways:
* It has [version control](https://www.youtube.com/watch?v=9GKpbI1siow) which keeps a record of any changes you make
* It allows you to easily share and document your code
* You can collaborate on code through creating multiple branches.

Even though GitHub was primarily designed with collaboration in mind, it is good practice to use it for your own code and will make your life significantly easier in the long run - **trust me, I learned the hard way!**

<br>

<br>

<p>
  <img src='https://github.com/Streit-lab-training/group-getting-started/blob/master/images/gitkraken_logo.png' width="35%"/>
</p>

***

GitKraken is a tool to help you interact with GitHub. You can use it for **free** with your GitHub pro account - so go ahead and [download](https://www.gitkraken.com/) 

Through the application you can access and link online repositories to your local machine. This then makes it very easy to **_commit_** changes you make locally which adds them to your **_commit graph_**. You can then easily **_push_** these **_commits_** to GitHub. Once this is done you can access your code from anywhere!

From GitKraken you can also create repository **_branches_** which will will be essential when collaborating on projects. It also generates these beautiful commit graphs which allow you to see *what* changes where made *when* and by *who*.

<p align="center">
  <img src='https://github.com/Streit-lab-training/group-getting-started/blob/master/images/gitkraken_commit_graph.png' width="80%"/>
</p>

It's good practice to regularly commit your changes, as this helps prevent you from breaking your code. It is also possible to use **_git_** directly from the command line to interact with GitHub, however I would recommend using GitKraken as the UI is fantastic.

Here is a short [video](https://www.youtube.com/watch?v=ub9GfRziCtU&t=118s) to help you get started with GitKraken. The GitKraken YouTube [channel](https://www.youtube.com/channel/UCp06FAzrFalo3txskS1gCfA) has many other videos to help you if you get stuck.

Once you're set up with GitKraken you can then make your first **_repository_** and get coding!

After you have initialised you first repository, GitKraken will monitor your local directory for any changes made. GitKraken then flags these changes and asks if you would like to commit them to GitHub.

**However you might NOT want to share all of the files in your repository with GitHub.**

This is particularly important if you are collaborating on a project as different users may have different R packages installed which will not work on another users computer.

Therefore after creating a repository, it is important to create a **.gitignore** file in the base directory of that repository. This file tells GitKraken which files to ignore.

For now, you don't need to worry about this too much - I have created a template *.gitignore* file [here](https://github.com/alexthiery/group-getting-started-R/blob/master/scripts/.gitignore). To download this file, click on the link, then right click on *'raw'* and select *'save link as'*. Save the link as *'.gitignore'* without any file type suffix. Now all you need to do is move this file to the base directory of your repository now.

<br>

<br>

***

Getting started with R
===

The beauty of R lies with the number and variety of packages built on top of it. These provides detailed functions that can be easily implemented in your analysis with minimal effort.

However, the sheer number of packages you will end up using creates other problems - package versioning, package dependency conflicts and in turn reproducibility issues.

R is a **_high-level_** programming language built using **_C_**

When you install packages in R, they are by default installed globally on the host computer. This means that any R session you launch will have access to the same packages.

Most packages are built in R are built using the R language. They are often built ontop of other R packages, but can also be dependent on chunks of **_C_** code. The important thing to note is that R packages are **_dependent_** on other code sources. Different packages or package versions can have conflicting dependencies, and this can cause major headaches. A simple yet elegant way to get around this issue is to use **_Renvironments_** (renv package).

<br>

renv
---

renv allows you to create separate Renvironments for different projects. This allows you to isolate the packages you install within the Renvironment from other repositories. This means that the packages you use in one project will not effect the packages you use in another.

To get started you will first need to install renv globally and then initialise a new Renvironment in your repository of interest.
To do this, open Rstudio and run `install.packaes('renv')`

renv is now globally installed on your computer

##### Creating a new Renvironment

Now that you have installed renv, you are ready to create your first Renvironment. The code below will create a new Renvironment. 

`renv::init(project = "<insert_project_path>")`

R will restart automatically within the new Renvironment.

Any R scripts which are launched from the directory where the Renvironment is located, will automatically load up that environment. Then any future package installations will be contained within this environment.