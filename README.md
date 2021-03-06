# Git-Command-and-help-guide

Popular Version Control System
------------------------------
1. GitHub
2. GitLab
3. Perforce
4. Beanstalk
5. AWS CodeCommit
6. Apache Subversion
7. Team Foundation Server
8. Mercurial
9. BitBucket
10. Concurrent Version Control
etc. 

Recommanded IDE
---------------
1. VS Studio Community version
2. VS Code
3. Notepad++
4. Sublimetext
5. Atom

Create a Git Account
--------------------
Got to https://github.com/ and create an account

Git Info
---------

Git Config
----------
$ git config -l
$ git config --global user.name "Name"
$ git config --global user.email "Email"

Save credintial
---------------
Make Git store the username and password and it will never ask for them.
$ git config --global credential.helper store

Save the username and password for a session (cache it);
$ git config --global credential.helper cache

# You can also set a timeout for the above setting
$ git config --global credential.helper 'cache --timeout=600'

Git Add, Commit
---------------
$ git add file_name # (.) for add all
$ git commit -m "commit message"
$ git commit -a -m "your commit message here" # add and commit at the same time

Check Git Logs
--------------
# This command shows the commit history for the current repository:
$ git log
# This command shows the commit's history including all files and their changes:
$ git log -p
# Replace commit-id with the id of the commit that you find in the commit log after the word commit.
$ git show commit-id
# This command will cause the Git log to show some statistics about the changes in each commit, including line(s) changed and file names.
$ git log --stat
# How to show the commit log as a graph in Git:
$ git log --graph --oneline
# How to show the commit log as a graph of all branches in Git:
$ git log --graph --oneline --all


Check Diff
----------
$ git diff
$ git diff --staged

How to remove tracked files from the current working tree in Git:
------------------------------------------------------------------
# This command expects a commit message to explain why the file was deleted.
$ git rm filename

How to rename files in Git:
---------------------------
# This command stages the changes, then it expects a commit message.
$ git mv oldfile newfile

How to ignore files in Git:
--------------------------
Create a .gitignore file and commit it.

How to revert staged changes in Git:
------------------------------------
# You can use the -p option flag to specify the changes you want to reset.
$ git reset HEAD filename
$ git reset HEAD -p

How to amend the most recent commit in Git:
------------------------------------------
# git commit --amend allows you to modify and add changes to the most recent commit.
$ git commit --amend

How to rollback the last commit in Git:
---------------------------------------
# git revert will create a new commit that is the opposite of everything in the given commit.
# We can revert the latest commit by using the head alias like this:
$ git revert HEAD

How to rollback an old commit in Git:
-------------------------------------
# You can revert an old commit using its commit id. This opens the editor so you can add a commit message.
$ git revert comit_id_here

How to create a new branch in Git:
----------------------------------
$ git branch branch_name
# How to switch to a newly created branch in Git:
$ git checkout branch_name
# list branches in Git:
$ git branch

# How to create a branch in Git and switch to it immediately:
$ git checkout -b branch_name
# How to delete a branch in Git:
$ git branch -d branch_name
# How to merge two branches in Git:
$ git merge branch_name

Merge Conflict
--------------
# How to abort a conflicting merge in Git:
# If you want to throw a merge away and start over, you can run the following command:
$ git merge --abort

Create a fork repo and clone it
-------------------------------
# Clone Wint HTTPS
$ git clone https://github.com/YOUR-USERNAME/Spoon-Knife


Configuring a remote for a fork
--------------------------------
$ git remote -v
# List the current configured remote repository for your fork.

> origin  https://github.com/YOUR_USERNAME/YOUR_FORK.git (fetch)
> origin  https://github.com/YOUR_USERNAME/YOUR_FORK.git (push)

# Specify a new remote upstream repository that will be synced with the fork.
$ git remote add upstream https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY.git

# Verify the new upstream repository you've specified for your fork.
$ git remote -v
> origin    https://github.com/YOUR_USERNAME/YOUR_FORK.git (fetch)
> origin    https://github.com/YOUR_USERNAME/YOUR_FORK.git (push)
> upstream  https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY.git (fetch)
> upstream  https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY.git (push)

$ git remote show origin
# How to check remote branches that Git is tracking:
# This command shows the name of all remote branches that Git is tracking for the current repository:
$ git branch -r

Changes on remote Repo
----------------------
# When all your work is ready to be saved on a remote repository, you can push all changes using the command below:
$ git push
# How to pull changes from a remote repo in Git:
$ git pull

How to fetch remote repo changes in Git:
----------------------------------------
$ git fetch upstream
$ git checkout main
$ git merge upstream/main

How to push a new branch to a remote repo in Git:
-------------------------------------------------
# If you want to push a branch to a remote repository you can use the command below. Just remember to add -u to create the branch upstream:
$ git push -u origin branch_name
# How to remove a remote branch in Git:
$ git push --delete origin branch_name_here

How to use Git rebase:
----------------------
# You can transfer completed work from one branch to another using git rebase.
$ git rebase branch_name_here

# Git Rebase can get really messy if you don't do it properly. Before using this command I suggest that you re-read the official documentation here

How to force a push request in Git:
-----------------------------------
# This command will force a push request. This is usually fine for pull request branches because nobody else should have cloned them. But this isn't something that you want to do with public repos.

$ git push -f
