# VIEWING AND COMPARING COMMITS


## 1. The commit history

The command git log displays the commit history of the current branch.
```bash
$ git log
```
e.g 

```bash
commit e86942deecc0eee280a47a96687aeebdf5e20169
Author: Sourav Verma <souravverma095@gmail.com>
Date:   Thu Dec 28 22:32:41 2017 +0530

    Add modified3 dummy.txt and deleted dummy11.txt

commit fb45a7ac6b2857723c3d06f8299a7dc0d519e7b2
Author: Sourav Verma <souravverma095@gmail.com>
Date:   Thu Dec 28 22:01:42 2017 +0530

    Add Modified2 dummy.txt

commit 216f0d502150984b71ace866607848f4d062d237
Author: Sourav Verma <souravverma095@gmail.com>
Date:   Thu Dec 28 21:55:20 2017 +0530

    Add modified1 dummy.txt

commit 271f9a1fba3cddce2b8581b9cce2f3a6472a1afa
Author: Sourav Verma <souravverma095@gmail.com>
Date:   Thu Dec 28 21:50:00 2017 +0530

    Add new dummy1.txt
```

OR,

```bash
$ git log --pretty=format:"%h %s <%an>" --graph
```
will give concise commit history
eg.
```bash
* e86942d Add modified3 dummy.txt and deleted dummy11.txt <Sourav Verma>
* fb45a7a Add Modified2 dummy.txt <Sourav Verma>
* 216f0d5 Add modified1 dummy.txt <Sourav Verma>
* 271f9a1 Add new dummy1.txt <Sourav Verma>
* aa939e1 Add modified version of dummy.txt <Sourav Verma>
* 1fe3e17 Add basic dummy file <Sourav Verma>
```
Its useful to be able to have this concise view of the log without having to type the long command every time. 
We can achieve this by adding the command as an alias. Try this command:
```bash
$ git config --global alias.lg ’log --pretty=format:"%h %s <%an>" --graph’
```
Now you can get the concise log view by simply typing:
```bash
$ git lg
```

## 2. Comparing commits
```bash
$ git diff e86942d
```
will results:
```bash
diff --git a/chapter_1.txt b/chapter_1.txt
new file mode 100644
index 0000000..d45272e
--- /dev/null
+++ b/chapter_1.txt
@@ -0,0 +1,138 @@
+
+                                      Version control
+
+
+Version control is a system that records changes to a file or set of files over time so that
+you can recall specific versions later.
+
+Type the following in a terminal, making the obvious substitutions:
+
+$ git config --global user.name "Sourav Verma"
+$ git config --global user.email souravverma095@gmail.com
+
+Next you need to tell Git what editor you want to use when Git needs you to type something:
+
+$ git config --global core.editor code               (for visual studio code)
+
+You should replace vim with what ever your favorite editor is (e.g. emacs, nano, subl, etc.).
+
+You can also make things a little easier on the eyes by telling Git to add some color to its messages:
+$ git config --global color.ui true
+
+
+1. Creating a repository
+
+create a new directory for thr project
+$ mkdir dummy
+$ cd dummy
+
+Now initialise your empty repository by typing:
:
:
```


## 3. Playing the blame game

Another useful way to visualise the history to is to look at a single file and see in which commit each line
was last changed. Imagine that we identified a bug in a line of code. We could then use this technique to 
see how long ago that bug was introduced (and by who!). Try this:
```bash
$ git blame dummy.txt --date=relative
```
and you should see a copy of dummy.txt with the reference, author and time of the last commit where each line
was modified.


## Command summary

|Command                              |Description                                    |
|-------------------------------------|---------------------------------------------- |
|git log                              |View the commit history for the current branch.|
|git diff <commit> <commit>           |Compare (difference) two commits.              |
|gitk                                 |View the commit history in a GUI.              |
|git blame <file>                     |See when each line of a file was last changed. |





