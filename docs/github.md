- go to folder you want to use init
$ git init
Initialized empty Git repository in I:/Projects/Jade_and_me/frank/projects/2017/GithubHowTo/.git/
- get the status of git project
$ git status
On branch master

Initial commit

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        docs/

nothing added to commit but untracked files present (use "git add" to track)

- To tell git which files and directories to ignore (that we don't want stored in repository)
- create file: .gitignore
------------------------------------------------------
File: .gitignore:
------------------------------------------------------
.git
------------------------------------------------------
- add files to local git repository
$ git add .
$ git status
On branch master

Initial commit

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

        new file:   .gitignore
        new file:   docs/github.md
        new file:   docs/sshkey.md
------------------------------------------------------
- commit changes to git respository
------------------------------------------------------
$ git commit -m 'Initial commit'
[master (root-commit) 70a6368] Initial commit
 3 files changed, 53 insertions(+)
 create mode 100644 .gitignore
 create mode 100644 docs/github.md
 create mode 100644 docs/sshkey.md       
------------------------------------------------------
- commit changes to files already being monitored
------------------------------------------------------
git
…or create a new repository on the command line
------------------------------------------------------
echo "# GithubHowTo" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin git@github.com:dzineer/GithubHowTo.git
git push -u origin master
…or push an existing repository from the command line

git remote add origin git@github.com:dzineer/GithubHowTo.git
git push -u origin master


$ git remote -v
origin  git@github.com:dzineer/GithubHowTo.git (fetch)
origin  git@github.com:dzineer/GithubHowTo.git (push)

$ git branch
/i/projects/Jade_and_me/frank/projects/2017/GithubHowTo (master)
