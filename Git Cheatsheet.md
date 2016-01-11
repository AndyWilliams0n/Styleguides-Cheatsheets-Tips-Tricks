# Git Cheatsheet

Navigate using the terminal to the repository you need.


## TERMINAL COMMANDS

| Command | Description |
| ------- | ----------- |
| git checkout -b dev/master | Switch to a branch, master or create a new branch |
|  |  |
| git checkout 'File path' | Discard the changes to a file and revert from Git |
|  |  |
| git status | View changes to your current branch or master |
|  |  |
| git add . | Adds your changed files to your current branch or master |
|  |  |
| git commit -m 'Your commit message' | Commit your changes and provide a message for this commit |
|  |  |
| git pull | Get the latest from your branch or master |
|  |  |
| git pull --rebase | Get the latest from your branch or master, rebasing your changes |
|  |  |
| git push | Push your commits live |
|  |  |
| git merge dev/master | Merge your branch to master |


| Commands |
| ------- |
| Commiting your changes: |
|  |
| git status (review your changes) |
| git add . |
| git commit -m 'enter your message' |
| git pull --rebase |
| git push |
|  |
| Merging dev into master: |
|  |
| git checkout master |
| git merge dev |
| git push |
| git checkout dev |
