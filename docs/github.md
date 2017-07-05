Using Git Repositry & Git Commands
==================================

git init
--------
Go to folder you want to use init

```
$ git init
Initialized empty Git repository in I:/Projects/Jade_and_me/frank/projects/2017/GithubHowTo/.git/
- get the status of git project

```

git status
----------

```
$ git status
On branch master

Initial commit

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        docs/

nothing added to commit but untracked files present (use "git add" to track)
```

To tell git which files and directories to ignore (that we don't want stored in repository)
-------------------------------------------------------------------------------------------
Create file: .gitignore

File: .gitignore:

```
.git
```

git add - Add files to local git repository
------------------------------------------------------

```
$ git add .
```

Get the status

```
$ git status
On branch master

Initial commit

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

        new file:   .gitignore
        new file:   docs/github.md
        new file:   docs/sshkey.md
```

git commit
----------
Commit changes to git respository

```
$ git commit -m 'Initial commit'
[master (root-commit) 70a6368] Initial commit
 3 files changed, 53 insertions(+)
 create mode 100644 .gitignore
 create mode 100644 docs/github.md
 create mode 100644 docs/sshkey.md       
```

commit changes to files already being monitored
-----------------------------------------------

```
$ git commit -a -m 'Update copy'
[master 77f7ad2] Update copy
 1 file changed, 50 insertions(+), 1 deletion(-)
```

Get the status again

```
$ git status
 On branch master
 nothing to commit, working tree clean
```
 
Add new File for project readme.md (example)
--------------------------------------------
File: readme.md:

```
GitHub How To Documentation With Examples
```

Check the git status again

```
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   docs/github.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        reame.md

no changes added to commit (use "git add" and/or "git commit -a")
```


Add new readme.md file to repository
------------------------------------------------------

```
$ git add .
```
Get the status again

```
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        modified:   docs/github.md
        new file:   reame.md
```

Commit changes for adding readme.md
-----------------------------------

```
$ git commit -m 'Added readme.md file'
[master d2377e7] Added readme.md file
 2 files changed, 9 insertions(+), 1 deletion(-)
 create mode 100644 reame.md
```

Get the status again

```
$ git status
 On branch master
 nothing to commit, working tree clean
``` 

Add a new project to the GitHub repository.
-------------------------------------------
After adding new repository to GitHub You will see this

create a new repository on the command line

```
echo "# GithubHowTo" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin git@github.com:dzineer/GithubHowTo.git
git push -u origin master
```

…or push an existing repository from the command line

```
git remote add origin git@github.com:dzineer/GithubHowTo.git
git push -u origin master
```

Add new remote branch to repository
-----------------------------------

```
git remote add origin git@github.com:dzineer/GithubHowTo.git
```

Confirm git remote was added successfully
-----------------------------------------

```
$ git remote -v
origin  git@github.com:dzineer/GithubHowTo.git (fetch)
origin  git@github.com:dzineer/GithubHowTo.git (push)
```


Display our git remote branch
-----------------------------

```
$ git branch
* master
```

Push our local repository to GitHub remote
------------------------------------------

```
$ git push -u origin master
Counting objects: 15, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (13/13), done.
Writing objects: 100% (15/15), 2.91 KiB | 0 bytes/s, done.
Total 15 (delta 2), reused 0 (delta 0)
remote: Resolving deltas: 100% (2/2), done.
To github.com:dzineer/GithubHowTo.git
 * [new branch]      master -> master
Branch master set up to track remote branch master from origin.
```

Okay what if we make changes ?
------------------------------
Change readme.md file to add author

Get the status again

```
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   docs/github.md
        modified:   reame.md

no changes added to commit (use "git add" and/or "git commit -a")

$ git commit -a -m 'Added Author'
[master 48caf4f] Added Author
 2 files changed, 82 insertions(+), 7 deletions(-)
```

Add changes to Github
---------------------

```
$ git push
Counting objects: 5, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (5/5), done.
Writing objects: 100% (5/5), 1.75 KiB | 0 bytes/s, done.
Total 5 (delta 0), reused 0 (delta 0)
To github.com:dzineer/GithubHowTo.git
   d2377e7..48caf4f  master -> master

$ git push
Everything up-to-date
```

Get the status again

```
$ git status
On branch master

Your branch is up-to-date with 'origin/master'.
nothing to commit, working tree clean

$ git push
Everything up-to-date

```
