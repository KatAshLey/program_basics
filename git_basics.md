#  commands in terminal powershell or gitbash
# list directory
ls

# make a directory called learn_git
mkdir learn_git

# change directory
cd .\learn_git\ 

# to scroll through folders
tab

# go back one folder
cd..

# git started
git init

# list directory includes hidden folders
ls -Force 

# shows status of commits in folder
git status 

# adds all files to folder
git add . 

# adds filename file to folder
git add filename 

# commits files. use a good commit message to describe the change"___"
git commit -m "my first commit comment"

# shows the commits, use q to exit this
git log

# make sure to add before commit as it wont commit properly
# use commitNumber shown in git log
gti checkout commitNumber 

# back to most updated version
git checkout main 


# default branch may be called main or master

# Right click file in source control, stage change is the same as git add, must do this before commit button
source control message is "commit name"

# shows unstaged changes
git diff 

# shows visually staged changes to be committed
source control > filename 

# compares commit to current commit
git diff [commit_hash] 


# to give current commit a tag, version numbers.  Use numbers only. x = major change, y = somewhat change, z = minor change
git tag "vx.y.z" 

# search by tag
git checkout tags/[tag]

# search for branch
git checkout [branch] 

# delete tag name, multiple tags with space between
git tag -d [tag_name] 

# creates a new tag new from old, then can delete old tag with -d
git tag [newname] [oldname] 

# show list of tags
git tag -l 




# branches
# naming conventions, also add task number eg feature/ ACN-XXX-add-cat
feature/______ = adding a new feature
bugfix/_______ = fixing bugs

# creates new branch with name
git branch [branch_name] 

# shows what branch you are on
git status 

# list branches, highlighted shows current branch
git branch -a 

# to move branch, must do commit on current branch before moving
git checkout [branch_name] 

# move branch, make changes, commit, go back to main branch to merge new branch

# to merge branches
git merge [name_of_branch] 

# see past merged branches
git branch -a --merged 

# remove branch, not recommended
git branch -d [branch_name] 




# GitHub
origin refers to local files
remote refers to a remote location for files

# create new repo
web browser
login github
create new repository 
name restart-homework
select add readme
gitignore template python

code >> HTTPS >> copy link

# in vs code
open folder where you want to copy repository to

# pulls repository to local, also creates new folder in current directory.  make sure you are not creating this in a current repository
git clone [link] 

# make sure to move into the repository after creating cloning it
cd [repository_name] 

# opens new window in vscode using the repository created
code .

# push files to remote/web, must add and commit before pushing
git push 

# pulls files down to local/ your computer
git pull request