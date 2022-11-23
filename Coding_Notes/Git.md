# Get into Git (Windows)

##### Basic manual from [Git-scm](https://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository)


#### Initialising a Repository
1. Use a local directory

```
git init
```

##### Specify which file to be track

```
git add *c
git add LICENSE
git commit -m "Initial project version"
```

2. Clone from a remote existing repository

```
git clone [Remote Repository URL]
```

-- Cone a repository for a specified name

```
git clone  [Remote Repository URL] [Repo_Name]
```
-- Clone form another working repository
```
git clone git@work.github.com:workAccountName/project.git
```

##### Check the status of your files: [new / staged / unstaged]

```
git staus

# Short Status  [-s] or [--short]
git status -s

# 
git status --ignored
```

Add a README file with project's introduction

```
# add line to a file
echo "Learning" > README.md

# Append to an existing file
echo "Learning experiences" >> README.md
```

##### Traking new files:

```
git add README.md
```

##### Staging modified / new files:

```
# update modified / new file to be committed
git add <file> 

# unstage file
git reset HEAD <file>

#discard changes in a file
git checkout -- <file>
```

##### Ignoring files

```
# ignore specific file
cat 1.logs

# ignore specific files types [a/ b]
cat *.[ab]

# ignore any files whose name ennds with #
cat *#


# ignore a file in current directory
/File_Name


# ignore all files in any directory name build
build/

# ignore a file in a specific directory
Directory_Name/*.logs

# ignore all .pdf files in any of its subdirectories
doc/**/.pdf

# re-track files which is ignored
git add -f <file or directory>

@REM  Files or directoies that already have been committed to the repository will not be ignored by Git.
```

##### Ignore files from config file (.gitignore)

```
touch .gitignore
```

##### Viewing Your Staged and Unstaged Changes

```
git status

# see what have changed but no yet staged
git diff

# compares staged changes to the last commit
git diff --staged
```

##### Skipping the staging area

```
git commit -a
```

##### Removing files

```
git rm <file>
```

##### Moving files (Rename files)

```
git mv <file>

# ex:
git README.md README
```

##### [Viewing the commit history](https://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History)

```
git log

# [-p/ --patch] shows differences in each commit, 
# [-2 ] shows  only the last two entries
git log -p] -2


git log --stat
```

##### Undoing things

```
git commit -m "Initial commit"
git add forgotten_file

# Show Commit-Comment
# i  entering edit mode | :wd  save & exit
git commit --amend


# Unstage & unmodifying a file
git reset HEAD <file>
git checkout -- <file>
```

##### Undoing things with Git Resotre

```
# unstage file
git restore --staged <file>

# undo modified file
git restore <file>
```

## Undoing commits
```
#  revoke last commit  [soft] keep changes
git reset --soft HEAD~1
git reset --hard HEAD~1

# return to a specific commit with SHA
git reset --hard 0xx1x2x3
```
## Git Remotes

```
# clone frome a remote server
git clone <URL>

# fetch from a branch
git fetch <short_name>
```

##### Showing which remote servers have been configured

```
git remote

# show shortname and URLs
git remote -v
```

##### Adding Remote Repositories

```
git remote add <short_name> <url>
```

##### Fetching and Pulling from Remotes

```
git fetch <short_name>
```

##### Pushing commits to your Remotes

```
git push <remote_name> <branch_name>
```

##### Renaming and Removing Remotes

```
git remote rename <Current_Name> <Name>


git remote remove <Remote_Name>
```

##### Generating Public/ Private  SSH Key 

```
# Generate for local host user
ssh-keygen -o

# generate a key which bind with email
ssh-keygen -t ed25519 -C "your_email@example.com"

ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

# Checking existing SSH Keys [id_rsa.pub/id_ecdsa.pub/id_ed25519.pub]
ls ~/.ssh

# Multiple SSH Keys with remote accounts
ssh-keygen -t rsa -C work@email.com
ssh-keygen -t rsa -C organization@email.com

# Ps: Enter file with 【Abosolute path】 in which to save the key
```

##### Updating SSH Config file

```
# create and edit config file
touch config
nano config
```
-- Nano Editor [Ctrl+S / Ctrl+O) to save, Ctrl+X to exit]
```
# Personal account, - the default config  with alias HostName
Host github.com
   HostName personal.github.com
   User git
   IdentityFile ~/.ssh/id_rsa_personal
   
# Work account
Host github.com-work  #
   HostName github.com
   User git
   IdentityFile ~/.ssh/id_rsa_work
```

##### Add SSH Keys to SSH Agent

```
# Start SSH Agent
eval `ssh-agent -s`

# Add SSH Keys to SSH Agent
ssh-add id_rsa_personal
ssh-add id_rsa_organisation

# Delete existing SSH Keys
ssh-add -D
```
```
# Checkin if it's successfully connected to github
ssh -T git@github.com
```

##### Creating and Updating SSH Config file, Add to SSH Agent

##### Manage credentials

```
# Show current credentials
git config --list
git config user.name

# Add credential 
## [--global] for all repositories ##
git config --global user.name "your name"
git config --global user.email name@example.com

# Replace en existing credential
git config --global --replace-all user.name "your name"
git config --global --replace-all user.email@name.email.com

# Remove credential
git config --global --unset user.name "your name"
git config --global --unset --global user.email "name@example.com"
```
```
# Set Private SSH key path  [--global] apply for all repos
git config --global core.sshCommand "ssh -i /profile/.ssh/privateKey"
```

##### Add Tag to repository's history

```
# [-l]  or [--list]
git tag -l "v1.0.0"
```

## Git Aliases

```
git config --global alias.co chekcout
git config --global alias.br branch
git config --global alias.ci commit
```

## Git Branching

##### Create and Deleting a branch

```
git branch testing
```

##### Switching Branches

```
git checkout testing
```

##### Merge Branches

```
# Switch to 'main' branch
git checkout main

# Merge to 'main' branch
git merge 'branch_21'
```

##### Branch Management

```
# Show branches
git branch

# Delete a branch
git branch -d <Branch_Name>

# Rename a Branch
git branch -m <Old_Name> <New_Name>
```

## Commonly Issues

##### SSH Key Issues
-- Error Message: 
 "Could not open a connection to your authentication agent."
   Reason: SSH Agent isn't running currently.
   Solution: Start SSH Agent
   ```
      eval `ssh-agent -s`
   ```



