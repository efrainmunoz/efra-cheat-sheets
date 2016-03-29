# Git Cheat Sheet
* [Installing Git on Linux](git.md#installing-git-on-linux)
* [First-Time Git Setup](git.md#first-time-git-setup)
* [Getting Help](git.md#getting-help)
* [Getting a Git Repository](git.md#getting-a-git-repository)
* [Recording Changes to the Repository](git.md#recording-changes-to-the-repository)
* [Viewing the Commit History](git.md#viewing-the-commit-history)
* [Undoing Things](git.md#undoing-things)
* [Working with Remotes](git.md#working-with-remotes)
* [Tagging](git.md#tagging)

## Installing Git on Linux
```
$ sudo apt-get install git-all
```
## First-Time Git Setup
#### Your Identity
```
$ git config --global user.name "Efra Muñoz"
$ git config --global user.email munozcoreano@gmail.com
```
#### Your Editor
```
$ git config --global core.editor emacs
```
#### Checking Your Settings
```
$ git config --list
...
```
## Getting Help
```
$ git help <command>
```
## Getting a Git Repository
#### Initializing a Repository in an Existing Directory
```
$ git init
```
#### Cloning an Existing Repository
```
$ git clone https://github.com/efrainmunoz/efra-cheat-sheets
```
## Recording Changes to the Repository
#### Checking the Status
```
$ git status
```
#### Tracking New Files
```
$ git add <filename>
```
#### Staging Modified Files
```
$ git add <filename>
````
#### Ignoring Files
Create (or edit) the `.gitignore` file.
Here's a .gitignore file example:
```
# no .a files
*.a

# but do track lib.a, even though you're ignoring .a files above
!lib.a

# only ignore the TODO file in the current directory, not subdir/TODO
/TODO

# ignore all files in the build/ directory
build/

# ignore doc/notes.txt, but not doc/server/arch.txt
doc/*.txt

# ignore all .pdf files in the doc/ directory
doc/**/*.pdf
```
#### Viewing Your Staged and Unstaged Changes
```
$ git status
```
To see not staged changes:
```
$ git diff
```
To see staged changes:
```
$d git diff --staged
```
#### Commiting Your Changes
```
$ git commit -m "Some description"
```
#### Removing Files
```
$ git rm <filename>
```
#### Moving Files
```
$ git mv file_from file_to
```
## Viewing the Commit History
```
$ git log
```
## Undoing Things
The `--amend` option takes your staging area and uses it for the commit. If you’ve made no changes since your last commit, then your snapshot will look exactly the same, and all you’ll change is your commit message.
```
$ git commit -m 'initial commit'
$ git add forgotten_file
$ git commit --amend
```
#### Unstaging a Staged File
```
$ git reset HEAD <filename>
```
#### Unmodifying a Modified File
```
$ git checkout -- <filename>
```
## Working with Remotes
#### Showing Your Remotes
```
$ git remote -v
```
#### Adding Remote Repositories
```
$ git remote add <shortname> <url>
```
#### Fetching and Pulling from Your Remotes
The `fetch` command only downloads the data to your local repository.
```
$ git fetch [remote-name]
```
The `pull` command automatically fetch and then merge that remote branch into your current branch.
```
$ git pull [remote-name]
```
The `clone` command automatically sets up your local master branch to track the remote master branch (or whatever the default branch is called) on the server you cloned from.
```
$ git clone [remote-url]
```
#### Pushing to Your Remotes
```
$ git push [remote-name] [branch-name]
```
#### Inspecting a Remote
```
$ git remote show [remote-name]
```
#### Removing and Renaming Remotes
```
$ git remote rename [old-name] [new-name]
```
```
$ git remote rm [remote-name]
```
## Tagging
#### Listing Your Tags
```
$ git tag
```
#### Creating Lightweight Tags
```
$ git tag <tag>
```
#### Creating Annotated Tags
```
$ git tag -a <tag> -m "my version 1.4"
```
#### Show Commit by Tag
```
$ git show <tag>
```
#### Tagging Later
```
$ git tag -a <tag> <commit-checksum>
```
#### Sharing Tags
To share one tag
```
$ git push origin [tagname]
```
To share all tags
```
$ git push origin --tags
```
#### Checking out Tags
```
$ git checkout -b [branchname] [tagname]
Switched to a new branch 'branchname'
```
