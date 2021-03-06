# BRANCHES


## 1. What is a branch?

Branches allow you to diverge from your current development and try something new without altering the history
of your main work. 
For example, you could implement a new code feature whilst leaving the fully functional
(hopefully working and tested) code intact for others to checkout.

In Git, branching is generally quick, flexible and simple. It is a fantastic way to test out ideas, 
try new things and safely develop your repository. This is especially true when collaborating with other people.


## 2. Creating branches

All new repositories, by default, start on a branch called master (you should see this name if you again run git
status).

Let’s now create a new branch called risky_idea by typing the following command inside of our
dummy directory:
```bash
$ git branch risky_idea
```
Well that was simple! However, if a quick check of git status shows that we are still on the master branch.
In order to start working with our new branch we need to perform a checkout; This moves our current “HEAD”
(remember this is what Git calls the pointer to the most recent relevant commit) to the branch risky_idea:
```bash
$ git checkout risky_idea
```
Running git status now should show that you are on the risky_idea branch.
Now run:
```bash
$ git lg
```
and you should see that our earlier commits from the master branch are still there. When running git branch,
the newly created branch inherits the history of the original branch we diverged from (in this case the master
branch). However, any subsequent commits to the new branch will not exist in the original.







