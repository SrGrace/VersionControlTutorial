# FIRST STEPS


Version control is a system that records changes to a file or set of files over time so that 
you can recall specific versions later.

Type the following in a terminal, making the obvious substitutions:
```bash
$ git config --global user.name "Sourav Verma"

$ git config --global user.email souravverma095@gmail.com
```

Next you need to tell Git what editor you want to use when Git needs you to type something:
```bash
$ git config --global core.editor code               (for visual studio code)
```

You should replace vim with what ever your favorite editor is (e.g. emacs, nano, subl, etc.).

You can also make things a little easier on the eyes by telling Git to add some color to its messages:
```bash
$ git config --global color.ui true
```

## 1. Creating a repository

create a new directory for thr project
```bash
$ mkdir dummy
$ cd dummy
```
Now initialise your empty repository by typing:
```bash
$ git init
```
To check everything has been successful type:
```bash
$ ls -a
```
and you should see the directory .git. This special folder is where Git will store and manage the version 
control history of your project.


## 2. Adding files

Now we have our fresh Git repository. The next step is to start adding files!
Use your editor of choice to start a LaTeX file named paper.tex in your project directory (dummy).
Add the following to your file and save your changes:
```bash
$ code dummy.txt                    (to open the editor with dummy.txt file and write something in it.)
```
In order to tell Git to start tracking our new file, use the following command:
```bash
$ git add dummy.txt
```
Now let’s check the status of our repository using the following command
```bash
$ git status
```
You should see something similar to the following:
On branch master
```bash
Initial commit

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

        new file:   dummy.txt
```

## 3. Committing changes

At this point, type:
```bash
$ git commit          (Will open the editor, Now provide "commit message" (usually <=80 chars), save it & exit)
```

## 4. Staging modified files

Add another things to dummy to txt

Now, run 
```bash
$ git status
```
you will see
```bash
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   dummy.txt
 ```

no changes added to commit (use "git add" and/or "git commit -a")

What Git now tells us is that dummy.txt falls under the category of “Changes not staged for commit”. This
means the file has changed since the last commit, however, we haven’t told Git that we want to include 
these new changes in our next commit. To do that, we must “stage” the file using git add again:
```bash
$ git add dummy.txt
```
A final check with git status should show that dummy.txt now falls under the category of “Changes to be
committed”.


## 5. Dealing with mistakes

Perhaps you make a typo in your commit message, or maybe you forget to stage an important change before
committing. In this case you can easily amend your last commit using the git commit --amend command.

Let’s imagine that we forgot to add the file bibliography.tex to our repository when we made our last
commit. To fix this, first create the file and then stage it into the index. Finally, run git commit --amend:
```bash
$ code bibliography.tex
$ git add bibliography.tex
$ git commit --amend
```
You will then be given the opportunity to change the last commit message if you want to.

## 6. Deleting and moving files
```bash
(Delete)  $ git rm <file>                (Will delete and stage this delete action for your next commit)

(Move/Rename)  $ git mv <source file> <destination file>
```

## 7. The circle of life

At this point we have covered the basic “life cycle” of files and changes in Git. Each file can have one of four
different states:

• Untracked: It’s not listed in the last commit <br>
• Unmodified: It hasn’t changed since the last commit <br>
• Modified: It has changed since the last commit <br>
• Staged: The changes will be recorded in the next commit made


## Command summary

|Command                     |Description                               |
|----------------------------|------------------------------------------|  
|git init                    |Initialise a new Git repository.          |
|git status                  |Check the current status of a repository. |
|git add                     |Stage new and modified files.             |
|git commit                  |Commit staged changes.                    |
|git commit --amend          |Amend the last commit.                    |
|git rm                      |Delete a file and stage this change.      | 
|git mv                      |Move a file and stage this change.        |



