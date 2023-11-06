ls = list directory
mkdir learn_git = make a directory called learn_git
cd .\learn_git\ = change directory
tab = to scroll through folders
cd.. = go back one folder
git init = git started
ls -Force = list directory includes hidden folders
make sure to use powershell in the terminal
git status = shows status of commits in folder
git add . = adds all files to folder
git add filename = adds filename file to folder
git commit -m "my first commit" = commits files. use a good commit message to describe the change"___"
git log = shows the commits, use q to exit this
make sure to add before commit as it wont commit properly
gti checkout commitNumber =  use commitNumber shown in git log
git checkout main = back to most updated version

** default branch may be called main or master

Right click file in source control, stage change is the same as git add, must do this before commit button
source control message is "commit name"

git diff = shows unstaged changes

source control > filename = shows visually staged changes to be committed

git diff [commit_hash] = compares commit to current commit

git tag "vx.y.z" = to give current commit a tag, version numbers.  Use numbers only. x = major change, y = somewhat change, z = minor change

git checkout tags/[tag]= search by tag

git checkout [branch] search for branch

git tag -d [tag_name] = delete tag name, multiple tags with space between

git tag [newname] [oldname] = creates a new tag new from old, then can delete old tag with -d

git tag -l = show list of tags




branches
naming conventions, also add task number eg feature/ ACN-XXX-add-cat
feature/______ = adding a new feature
bugfix/_______ = fixing bugs

git branch [branch_name] = creates new branch with name

git status = shows what branch you are on

git branch -a = list branches, highlighted shows current branch

git checkout [branch_name] = to move branch, must do commit on current branch before moving

move branch, make changes, commit, go back to main branch to merge new branch

git merge [name_of_branch] = to merge branches

git branch -a --merged = see past merged branches

git branch -d [branch_name] = remove branch, not recommended




GitHub
origin refers to local files
remote refers to a remote location for files

web browser
login github
create new repository 
name restart-homework
select add readme
gitignore template python

code > HTTPS > copy link

vs code
open folder where you want to copy repository to

git clone [link] = pulls repository to local, also creates new folder in current directory.  make sure you are not creating this in a current repository

cd [repository_name] = make sure to move into the repository after creating cloning it

code . = opens new window in vscode using the repository created

git push = to push files to remote, must add and commit before pushing

git pull request