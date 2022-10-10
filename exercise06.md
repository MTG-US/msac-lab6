# Exercise 6 - Committing a change (full cycle)

1. Look at git status and ensure you have a clean working directory

        git status
---
```
On branch master
nothing to commit, working tree clean
```
2. Open your `fruits.txt` file  in VS Code, your favorite code editor
---
```
notepad fruits.txt
```
3. Add some lines to the file

        apple
        banana
        tomato

4. Save and exit the editor

5. Look at git status

        git status
---
```
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   fruits.txt

no changes added to commit (use "git add" and/or "git commit -a")
```
6. Add the file to the index

        git add fruits.txt

7. Check status

        git status
---
```
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   fruits.txt
```
8. Commit the changes (short commit message included on command line)

        git commit -m "Added more fruit to the list"
---
```
[master 6c97256] Added more fruit to the list
 1 file changed, 3 insertions(+), 1 deletion(-)
```
9. Check status

        git status
---
```
On branch master
nothing to commit, working tree clean
```
10. Which of the steps could be omitted?
> Technically all the `git status` are not necessary, but for beginners it is nice to see their commands had an outcome (something happened) and while it is preferred that you stage the files you want to commit `git add` so that you can select exactly what is included, if you are going to commit everything changed, you technically don't need to stage them (although personally I prefer the staging method and do it no matter what).
11. Why might it be a bad idea to omit them?
> As stated above, while it is annoying, the `status` checks are helpful to make sure the commands had their intended effect and catch and any errors before you get too far, definitely helpful for beginners or simply the less experienced. As also stated, the failure to stage your files `add` before committing can result in you committing files that you didn't intend to be included or pushed out yet. It is always better to be intentional.
12. Repeat the above steps to add a new file with the name `vegetables.txt`
---
```
type nul > vegetables.txt
git add vegetables.txt
```
13. Create a subdirectory named `equipment` and a new file named `appliances.txt` in that subdirectory
---
```
mkdir equipment & type nul > equipment\appliances.txt
git add equipment
```
14. Repeat the above steps to commit the new file and directory
---
`git status`
```
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   equipment/appliances.txt
        new file:   vegetables.txt
```
`git commit -m "Added Vegetables file" -m "Added Equipment folder and appliances file"`
```
[master b04aa4f] Added Vegetables file
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 equipment/appliances.txt
 create mode 100644 vegetables.txt
```
`git status`
```
On branch master
nothing to commit, working tree clean
```
15. Repeat the above steps 1-9, adding data to each of your files a few lines at a time, until you can easily do the steps without referring to the steps. You may want to add vegetables to the vegetables file, and appliances to the appliances - or vice versa
---
`echo nul > Candies.txt & mkdir Household & echo nul > Household\Furniture.txt`

`git status`
```
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        Candies.txt
        Household/

nothing added to commit but untracked files present (use "git add" to track)
```
`echo M^&M > Candies.txt & echo Kit-Kat >> Candies.txt & echo Snickers >> Candies.txt`

`git add Candies.txt`

`git status`
```
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   Candies.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        Household/
```
`echo Couch > Household\Furniture.txt & echo Stool >> Household\Furniture.txt`

`git add Household`

`git status`
```
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   Candies.txt
        new file:   Household/Furniture.txt
```
`git commit -m "Added Candies file" -m "Added Household folder and Furniture file`
```
[master 3586053] Added Candies file
 2 files changed, 5 insertions(+)
 create mode 100644 Candies.txt
 create mode 100644 Household/Furniture.txt
```
`git status`
```
On branch master
nothing to commit, working tree clean
```