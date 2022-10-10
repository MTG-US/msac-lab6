# Exercise 3 - Configuring your first repository

1. Enable color

        git config --global color.ui auto

2. Set your name

        git config --global user.name "John Doe"

3. Set your email address

        git config --global user.email "john.doe@somewebsite.com"

4. Why did we use the `--global` flag?  (What does that do?)  

> This flag is among three `local`, `global` and `system` which determine the scope of where the setting is stored and to what repositories the settings within will apply.

>`local` allows you to keep the settings specific to the repository level only so this way you can have different username/email/configurations based on indivdidual projects.

>`global` raises the scope higher to include all or most repositories within a given profile, much as the HKCU branch in the Registry.

>`system` makes it so that it applies to any profile that uses that installation of the Git, this is much like the HKLM branch in the Registry.  

5. Check your git config to show the changes you have made

        git config -l

## Output ##
```
\my_repository> git.exe config --global color.ui auto

\my_repository> git.exe config --global user.name "Michael Taefi"

\my_repository> git.exe config --global user.email "mtaefi@mtsac.edu"

\my_repository> git.exe config -l
core.symlinks=false
core.autocrlf=true
core.fscache=true
color.diff=auto
color.status=auto
color.branch=auto
color.interactive=true
help.format=html
diff.astextplain.textconv=astextplain
rebase.autosquash=true
filter.lfs.clean=git-lfs clean -- %f
filter.lfs.smudge=git-lfs smudge -- %f
filter.lfs.process=git-lfs filter-process
filter.lfs.required=true
credential.helper=!"/mingw64/libexec/git-core/git-credential-manager-core.exe"
user.name=Michael Taefi
user.email=mtaefi@mtsac.edu
safe.directory=/W3s-Tutorial
safe.directory=/msac-lab6
safe.directory=/my_repository
color.ui=auto
core.repositoryformatversion=0
core.filemode=false
core.bare=false
core.logallrefupdates=true
core.symlinks=false
core.ignorecase=true
```
For more information, check out [Customizing Git Configuration](https://www.git-scm.com/book/en/v2/Customizing-Git-Git-Configuration)