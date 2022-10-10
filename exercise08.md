# Exercise 8 - Viewing changes before committing

1. Ensure your working directory is clean

`git commit -m "Cleaning my working directory for Exercise 8" .`

---
```
[master 6cac812] Cleaning my working directory for Exercise 8
 2 files changed, 2 insertions(+), 2 deletions(-)
 delete mode 100644 Household/Furniture.txt
[master ff23790] Cleanup
 1 file changed, 2 insertions(+)
 create mode 100644 equipment/Furniture.txt
```
`git status`

---
```
On branch master
nothing to commit, working tree clean
```
2. Add text to any one of your files
---
> added to candies.txt
3. Delete different text from another of your files
---
> deleted from fruits.txt
4. Look at `git status`
---
```
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   Candies.txt
        modified:   fruits.txt

no changes added to commit (use "git add" and/or "git commit -a")
```
5. View all the changes you've made

        git diff
---
```
diff --git a/Candies.txt b/Candies.txt
index e8202dc..2c97456 100644
--- a/Candies.txt
+++ b/Candies.txt
@@ -1,3 +1,5 @@
 M&M
 Kit-Kat
 Snickers
+Heath
+Chocolate
\ No newline at end of file
diff --git a/fruits.txt b/fruits.txt
index 57d3d03..3409b8f 100644
--- a/fruits.txt
+++ b/fruits.txt
@@ -4,6 +4,4 @@ blueberry
 strawberry
 cherry
 orange
-pear
-fig
 tangerine
\ No newline at end of file
:
```
6. Does the following command return anything?

        git diff --staged
---
> NO, we haven't staged any files, so nothing to show.
7. Add one of your changed files to the index

        git commit add <changed file>
---
`fruits.txt`

8. What do these commands show?

        git diff
        git diff --staged
---
```
diff --git a/Candies.txt b/Candies.txt
index e8202dc..2c97456 100644
--- a/Candies.txt
+++ b/Candies.txt
@@ -1,3 +1,5 @@
 M&M
 Kit-Kat
 Snickers
+Heath
+Chocolate
\ No newline at end of file
```
---
```
diff --git a/fruits.txt b/fruits.txt
index 57d3d03..3409b8f 100644
--- a/fruits.txt
+++ b/fruits.txt
@@ -4,6 +4,4 @@ blueberry
 strawberry
 cherry
 orange
-pear
-fig
 tangerine
\ No newline at end of file
```
9. Add the other changed file to the index

        git commit add <other changed file>
---
`candies.txt`

10. What do these commands show?

        git diff
        git diff --staged
---
```
diff --git a/Candies.txt b/Candies.txt
index e8202dc..2c97456 100644
--- a/Candies.txt
+++ b/Candies.txt
@@ -1,3 +1,5 @@
 M&M
 Kit-Kat
 Snickers
+Heath
+Chocolate
\ No newline at end of file
```
---
```
diff --git a/fruits.txt b/fruits.txt
index 57d3d03..3409b8f 100644
--- a/fruits.txt
+++ b/fruits.txt
@@ -4,6 +4,4 @@ blueberry
 strawberry
 cherry
 orange
-pear
-fig
 tangerine
\ No newline at end of file
```
11. Commit the changes
---
`git commit -m "Committing Exercise 8 Step 11" *`
```
[master e9f048e] Committing Exercise 8 Step 11
 2 file changed, 2 deletions(-), 2 insertions(+)
```
12. Check that your working directory is clean
---
`git status`
```
On branch master
nothing to commit, working tree clean
```
13. Create a new file named `clothing.txt`
---
`echo nul > clothing.txt`

14. Does the new untracked file show up in git diff?

        git diff
---
> NO, it does not.
15. Add and commit the new file
---
`git add clothing.txt & git commit -m "Exercise 8 Step 15" *`
```
[master 1738599] Exercise 8 Step 15
 1 file changed, 1 insertion(+)
 create mode 100644 clothing.txt
```
`git status`
```
On branch master
nothing to commit, working tree clean
```