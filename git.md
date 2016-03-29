# Git Cheat Sheet
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
