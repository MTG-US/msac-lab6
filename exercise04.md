# Exercise 4 - Adding files

1. Look git status for your directory, and paste the contents below

        git status
---
```
On branch master

No commits yet

nothing to commit (create/copy files and use "git add" to track)
```
2. Using VS Code, the command line, or your favorite code editor, create a new file named `fruits.txt`.
---
```
 echo apple, orange, pear > fruits.txt
 ```
3. Check your git status, and paste the contents here

        git status
---
```
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        fruits.txt

nothing added to commit but untracked files present (use "git add" to track)
```
4. Add the new file to your index

        git add fruits.txt

5. Check git status again, and paste the contents below

        git status
---
```
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   fruits.txt
```