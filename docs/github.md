…or create a new repository on the command line

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
