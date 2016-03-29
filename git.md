# Git Cheat Sheet
* [Installing Git on Linux](git.md#installing-git-on-linux)
* [First-Time Git Setup](git.md#first-time-git-setup)
* [Getting Help](git.md#getting-help)
* [Getting a Git Repository](git.md#getting-a-git-repository)
* [Recording Changes to the Repository](git.md#recording-changes-to-the-repository)
* [Viewing the Commit History](git.md#viewing-the-commit-history)
* [Undoing Things](git.md#undoing-things)

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
