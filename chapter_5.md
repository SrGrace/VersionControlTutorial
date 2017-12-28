# ONLINE HOSTING AND COLLABORATION


## 1. Online hosting

Git uses a “distributed” model that allows everyone working on a project to have their own independent 
copy of the entire repository. To collaborate effectively though we need a central version of the code
base which is used to unify everyones’ efforts. Typically the best place for such a central repository is online.

There are a number of excellent options for online hosting of git repositories.
However, there are two options in particular which stand out in my opinion:

* Bitbucket: This site overs unlimited free public repositories (where anyone can see and checkout your
project). If you have an email address from an academic institution though, then you can also get unlimited
free private repositories! These repositories only allow users who you specify to have access.

* Github: This is site also offers unlimited free public repositories. With an academic institution email address
you can also get 5 free private repositories. Github is probably the place for new open source software and
tools. It’s a fantastic service and well worth using, especially if you want to take your own code open source.
You can also use Github to serve web pages for free. This tutorial is open sourced on Github.



## 2. Cloning a repository

If you have the address (and correct permissions) for an online repository then you can grab your own copy using
the clone command. Try cloning your own copy of the source for this tutorial:

$ git clone https://github.com/srgrace/VersionControlTutorial
$ cd VersionControlTutorial

You are now inside your own personal copy of the repository and can do whatever you want with it. Try:
$ git lg

and you will see that you also have the full commit history


## 3. Collaboration strategies

The basic work-flow is almost always the same though:

* Make your changes in your own personal copy of the repository, ideally in a new branch.

* “Pull” (using the command git pull) the most recent version of the central repository into your master
branch. This makes sure you are up-to-date with any changes which were made by someone else subsequent
to when you last pulled (or made your original clone).

* Merge your changes from your new branch into master.

* Once any conflicts are resolved you can update the central repository with your new code (using for example
git push).



