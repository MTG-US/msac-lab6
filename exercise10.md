# Exercise 10 - Understanding Commits

1. Look at your commit log

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
2. Choose a commit hash
---
> 1738599
3. See what type of object that hash names

        git cat-file -t <hash>
---
> commit
4. Examine the contents of that commit closely

        git cat-file -p <hash>
---
```
tree 82a7a516103c002f3a5b92021f8d8ca2b0f0d0c2
parent e9f048e352f4ed344a691f8eba0a8680f1d7d001
author Michael Taefi <mtaefi@mtsac.edu> 1665364758 -0700
committer Michael Taefi <mtaefi@mtsac.edu> 1665364758 -0700

Exercise 8 Step 15
```
5. Find the parent's hash in the commit log
---
`git cat-file -p e9f048e352f4ed344a691f8eba0a8680f1d7d001`
```
tree 87a8cb8931a270c0d79cb3f063b4f5fa9d1f1389
parent a84d250dd923b2f46f012857d40d742722ba344b
author Michael Taefi <mtaefi@mtsac.edu> 1665364534 -0700
committer Michael Taefi <mtaefi@mtsac.edu> 1665364534 -0700

Committing Exercise 8 Step 11
```
6. Look at the contents of the tree

        git cat-file -p <hash>
---
```
100644 blob 2c97456adc3740c64275ef115ede161ed66c79fb    Candies.txt
100644 blob ec79702ee320cdb3b9ea3c302ec534a8b3d2fcd0    clothing.txt
040000 tree 808c9dc4c16ffc431cec18d7005b7b7be3ec324d    equipment
100644 blob 3409b8f8d8482cf645e98dc6a2e2f19681824826    fruits.txt
100644 blob ae28696afe8559cc88e15fbba3dc0b1452c3ae66    vegetables.txt
```
7. Examine the contents of one of the blobs
---
`git cat-file -p 3409b8f8d8482cf645e98dc6a2e2f19681824826`
```
apple
banana
blueberry
strawberry
cherry
orange
tangerine
```
8. What type of object does the parent hash represent?

        git cat-file -t <hash>
---
> commit
9. Examine the contents of the parent and its tree
---
`git.exe cat-file -p a84d250dd923b2f46f012857d40d742722ba344b`
```
tree 1dd4d25f11c8185af535fa395df721b3cd691f9d
parent ff23790e00edc9be97027a5c1abccb3aab1c50a3
author Michael Taefi <mtaefi@mtsac.edu> 1665364411 -0700
committer Michael Taefi <mtaefi@mtsac.edu> 1665364411 -0700

Committing Exercise 8 Step 11
```
`git cat-file -p 1dd4d25f11c8185af535fa395df721b3cd691f9d`
```
100644 blob e8202dc6ff1e8abf052222bb902cad131905fd51    Candies.txt
040000 tree 808c9dc4c16ffc431cec18d7005b7b7be3ec324d    equipment
100644 blob 3409b8f8d8482cf645e98dc6a2e2f19681824826    fruits.txt
100644 blob ae28696afe8559cc88e15fbba3dc0b1452c3ae66    vegetables.txt
```
10. Do the trees you looked at have any matching hashes listed?
---
> YES, the blob for `vegetables.txt` is the same.

> 100644 blob ae28696afe8559cc88e15fbba3dc0b1452c3ae66    vegetables.txt