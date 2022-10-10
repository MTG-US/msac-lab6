# Exercise 1 - Setting up your first repository

1. Create a new, empty directory

        mkdir my_repository

2. `cd` into it

        cd my_repository

3. Initialize it as a git repository.

        git init

4. Where are the internals of the repository stored? Paste the output of the following command on ~~macOS & Linux~~ Windows.

        dir /ah   <-- show all files including hidden
        dir /ahd  <-- show all files, directories including hidden
        dir /ahds <-- show all files, directories, sub-dirs including hidden

## Output ##
```
10/09/2022  02:14 PM    <DIR>          .git
               0 File(s)              0 bytes
               1 Dir(s)  1,504,870,137,856 bytes free
```