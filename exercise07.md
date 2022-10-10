# Exercise 7 - More than one changed file

1. Ensure you have a clean working directory

        git status
---
```
On branch master
nothing to commit, working tree clean
```
2. Edit one of your `fruits.txt`, add a few items

        blueberry
        strawberry
        etc.

3. Edit `appliances.txt` and add a few items

        dishwasher
        dryer
        etc.

4. Look at git status, paste the output here

        git status
---
```
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   equipment/appliances.txt
        modified:   fruits.txt

no changes added to commit (use "git add" and/or "git commit -a")
```
5. Can you commit both of the changed files in a single commit?
---
> Yes you can use a wildcard to add all changes at the same time. Using just * will result in only files but if you use a . then you will include the folders as well.

> For the commit log message, you can either use the vim editor to do it or you can do it by using the `-m` flag if you have a single line comment. However, on Mac/Linux, you have the option of using a `'` quotation trick to put comments on multiple lines, or use HEREDOC. On Windows, these tricks will be a bit more tricky/messy but you can use the multiple `-m` flags to have messages on multiple lines in a single command.

`git commit -m "Updated fruits.txt file with additional fruits" -m "Updated appliances file in equipment folder" -m "I also put all this on individual line breaks!"`

```
[master c515da9] Updated fruits.txt file with additional fruits
 2 files changed, 13 insertions(+), 1 deletion(-)
```
6. After you do so, check that you have a clean working directory by running `git status`, and pasting the output here
---
```
On branch master
nothing to commit, working tree clean
```

7. Create a new file `equipment/furniture.txt`. Add content to both `vegetables.txt` and `furniture.txt`
---
`move household\furniture.txt equipment\ & rmdir household & echo "some" >> vegetables.txt & echo "more" >> vegetables.txt`

`git status`
```
On branch master
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    Household/Furniture.txt
        modified:   vegetables.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        equipment/Furniture.txt

no changes added to commit (use "git add" and/or "git commit -a")
```
8. How can you commit just one of the changed files?
---
> You have a couple of approaches, you can do the stage and use the `--only` flag during the commit to do just that/those files. You can also do a `commit -m` with the message and one or more files after to make a single call. I personally prefer the staging method.

9. Check your `git status`
---
> Same as #7 above.
10. What does red text mean in the output of `git status`?
---
> The red text means files that are changed which are either not staged or are untracked.
11. What does green text mean in the output of `git status`?
---
> The green text means the changed files have been staged for the commit.
12. How can you make a single file show in both red and green in the output of `git status`?
---
> This actually happens more often than we care to admit. You make a change to file, say A.file and now it is red. Then you add to stage it which makes it green. But then you make more changes to the same file which makes it red for the new changes, and green for the changes you already staged.