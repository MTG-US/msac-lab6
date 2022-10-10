# Exercise 2 - Checking status

1. Run the git status command

        git status

2. Paste the output below

```
\my_repository> git.exe status
fatal: detected dubious ownership in repository at '/my_repository'
'/my_repository' is on a file system that doesnot record ownership
To add an exception for this directory, call:

        git config --global --add safe.directory /my_repository

\my_repository> git.exe config --global --add safe.directory /my_repository

\my_repository> git.exe status
On branch master

No commits yet

nothing to commit (create/copy files and use "git add" to track)

\my_repository>
```