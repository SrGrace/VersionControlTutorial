# MERGING AND CONFLICTS


## 1. Merging

At some stage we will want fold our changes in the risky_idea branch back into the master branch. We do
this by “merging” the risky_idea branch into master.

First we checkout the master branch:
```bash
$ git checkout master
```
If you run git lg you should see that none of your commits to the risky_idea branch are present. You can
further confirm this by looking at the contents of paper.tex; The section “The Empire Strikes Back” shouldn’t
be present.

Now merge risky_idea into our current branch using the following command:
```bash
$ git merge risky_idea
```
If everything runs smoothly, running git lg should show your commits from the risky_idea branch.
At this stage you could either checkout the risky_idea branch again and continue working, or if your finished
with it you can delete it.

We no longer need the risky_idea branch, so delete it using:
```bash
$ git branch -d risky_idea
```

## 2. Dealing with conflicts
```bash
$ git commit -a
```


## Command summary

|Command                            |Description                                        |
|-----------------------------------|---------------------------------------------------|
|git merge                          |Merge branches and commits.                        |
|git branch -d                      |Delete a branch.                                   |
|git commit -a                      |Stage all changes in tracked files and commit them.| 


