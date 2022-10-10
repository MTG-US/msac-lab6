# Exercise 9 - Viewing history

1. Make a commit with a multi line commit message
   (leaving an empty line after the first line)
---
```
On branch master
nothing to commit, working tree clean
```
`echo nul>.gitignore`

---
```
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .gitignore

nothing added to commit but untracked files present (use "git add" to track)
```
---
```
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   .gitignore
```
`git commit`
```
Exercise 9

Step 1
Multiple Lines with an Empty second line
# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
#
# On branch master
# Changes to be committed:
#       new file:   .gitignore
#
```
---
```
[master 81bfb7c] Exercise 9
 1 file changed, 1 insertion(+)
 create mode 100644 .gitignore
```

2. View that commit in the log

        git log -1
---
```
commit 81bfb7c1fc82adeb4bff31eb06f79a680f5220e6 (HEAD -> master)
Author: Michael Taefi <mtaefi@mtsac.edu>
Date:   Sun Oct 9 18:31:33 2022 -0700

    Exercise 9

    Step 1
    Multiple Lines with an Empty second line
```
3. View the full commit log

        git log
---
```
commit 81bfb7c1fc82adeb4bff31eb06f79a680f5220e6 (HEAD -> master)
Author: Michael Taefi <mtaefi@mtsac.edu>
Date:   Sun Oct 9 18:31:33 2022 -0700

    Exercise 9

    Step 1
    Multiple Lines with an Empty second line

commit 173859955edcd2d3c8c9ecf83caf3f1d7b8ae273
Author: Michael Taefi <mtaefi@mtsac.edu>
Date:   Sun Oct 9 18:19:18 2022 -0700

    Exercise 8 Step 15

commit e9f048e352f4ed344a691f8eba0a8680f1d7d001
Author: Michael Taefi <mtaefi@mtsac.edu>
Date:   Sun Oct 9 18:15:34 2022 -0700

    Committing Exercise 8 Step 11

commit a84d250dd923b2f46f012857d40d742722ba344b
Author: Michael Taefi <mtaefi@mtsac.edu>
Date:   Sun Oct 9 18:13:31 2022 -0700

    Committing Exercise 8 Step 11

commit ff23790e00edc9be97027a5c1abccb3aab1c50a3
Author: Michael Taefi <mtaefi@mtsac.edu>
Date:   Sun Oct 9 17:50:55 2022 -0700

    Cleanup

commit 6cac812b1435702618461c105678651725a616b4
Author: Michael Taefi <mtaefi@mtsac.edu>
Date:   Sun Oct 9 17:45:29 2022 -0700

    Cleaning my working directory for Exercise 8

commit c515da9a92e87b34636271efa1b9a0e447df9097
Author: Michael Taefi <mtaefi@mtsac.edu>
Date:   Sun Oct 9 17:08:18 2022 -0700

    Updated fruits.txt file with additional fruits

    Updated appliances file in equipment folder

    I also put all this on individual line breaks!
:
```
*If the log fills your whole terminal, press `q` to exit*

4. View a shortened version of the commit log

        git log --oneline
---
```
81bfb7c (HEAD -> master) Exercise 9
1738599 Exercise 8 Step 15
e9f048e Committing Exercise 8 Step 11
a84d250 Committing Exercise 8 Step 11
ff23790 Cleanup
6cac812 Cleaning my working directory for Exercise 8
c515da9 Updated fruits.txt file with additional fruits
3586053 Added Candies file
b04aa4f Added Vegetables file
6c97256 Added more fruit to the list
345d5c6 First commit
```
5. Pick a commit hash from the log
---
> a84d250
6. View the commit log from the chosen commit backward

        git log --oneline <commit_hash>
---
```
a84d250 Committing Exercise 8 Step 11
ff23790 Cleanup
6cac812 Cleaning my working directory for Exercise 8
c515da9 Updated fruits.txt file with additional fruits
3586053 Added Candies file
b04aa4f Added Vegetables file
6c97256 Added more fruit to the list
345d5c6 First commit
```
7. How much of the commit hash do you need to specify? Hint, run `git help log`
---
> The hash is about 40 characters long using SHA-1 algorithm. You really only need the first 7 digits in most cases. There are cases where you will need to specify the full hash but most of the time the short is good enough. You also have an option that allows you to choose how many characters you want returned.
8. How can you show just the last three commit messages?
---
> To show the last `x` commits you simply add `-x` to `git log` and so for 3 you would put `git log -3` and there are additional things you can do such as using relative time, so for example `--since=1.week` and using that, along with filtering and formatting options, you can get a pretty response of commits belonging to a specific person or containing specific words, in case you are looking for a specific change.

> For example `git log --pretty="%ar" --author="Michael Taefi" --since="2022-01-01" --before="2022-10-01" --grep="exercise"` would give you relative author date of anything Michael Taefi has done between January 1st of 2022 and October 1st of 2022 that have the word "exercise" in the commit message.