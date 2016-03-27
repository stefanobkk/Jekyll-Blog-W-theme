---
layout: post
title:  Github Made Easy
cover: cover.jpg
date:   2016-03-26 21:32:45 +0700
categories: jekyll update
---


### Content 
* What is it?
* Why use it?
* Starting up
* Branching
* Remotes 
* Merging
* Cloning



# What is github?

First to know what github is we should first know what git is. Git is a version control repository that allows developers to share their code and keep it updated. What this means is that when the developer of a plug-in comes up with some fixes and updates they would just have to ‘push’ it into their public repository. This allows every developer to to keep up with changes made to the source-code where they can download it or even contribute to it. 


Now that you know what git does, github is just a service that allows developers to visually manage their git repositories under one account. This not only makes sharing code much easier but also keeps developers up to date and constantly sharing ideas and solutions with each other. 

 
# Getting stared…

So the first thing you want to do is go to the [github][git-hub] page and create a new account. 

When logged in create a new Repository. 

* A repository is sort of like a storage space where you can keep your project. Each repository will represent one project. Whats good about a repository is that you can store it in a local folder on your computer or if you’re doing what we are doing you can store it on a online host in github or any other online hosting site.


* When we are done creating our repository it will initially be empty except for a bunch of git commands. This is now the storage space for your project.

Go back to your terminal and go into your project folder. In our out we juts made a folder called github_blog. 

* ~ stefanocassio$ cd github_blog
* git init
* You should see a statement saying Initialized empty Git repository in /direcotry_here/

What git init does is that it initialies and empty or existing repository on your computer and is ready for use. 

### Important Commands 
There are a few commands that you are going to want to remember right fro the start.

* git status 
* git add .
* git commit -m'message_goes_here_MUST'

**git status** tell you the current state of the repository and will show you all the different files that have been edited. 

**git add .** will add all the files that have been edited into a temporary holding storage and waits for the commit before adding it to your repository.

**git commit** This is when you tell git that you want your records to be changed in your local repository. 



### Branching 
Whats cool about git is that you can branch from the main line of development and continue to do the same work without messing up the main line. This is good when you want to test some feature out but don’t want to cause the program to crash.

**Commands**

* git branch 
* git branch test1
* git checkout test1

* git branch

If you run these 4 git command you should get a better understanding of how branch works.

As you can see with the initial **git branch** you see that we only have 1 branch ‘master’. We then **git branch test1** which creates a new branch for us named test1.

When you run **git checkout test1** you will be in the test1 branch. What this lets us do is mess around with testing out new features or trying to fix a bug because if you end up with something you don't like or you made a mistake you can always go back to your master branch with **git checkout master**

Inline-style: 
![alt text](http://i.stack.imgur.com/MgaV9.png "Logo Title Text 1")

### Merging

* Merging is used when you have branched out from your master branch into, lets say we are currently in *test1* and we have added a form that accepts the user information and we now want to the two branches to merge back together again --> into the *'master'* branch.

**Commands**

* git checkout master
* git merge test1  

**master branch** first we want to go into our master branch because we want to merege to master not merge master to another branch.

**mergre test1** then we merge test1 to master. This should add the forms we made whilst in test1 into our *master branch*


### Remote 

So with remote we are able to link our local git repository to our github page.

**Setting up remote**

* git remote add remote_name https://github.com/your_git_hub_name/repository_name
* git remote -v

**Linking you local git repo with github**

* git push remote_name branch_name # branch name is usually master

**Retrieving repos from github**

* git fetch rpository_name
* git clone https://github.com/git_hub_name/repository_name.git




These there commands can vary in commands depending on the extension added to it. 



[git-hub]: https://github.com/
[img-add-commit]: http://i.stack.imgur.com/MgaV9.png
