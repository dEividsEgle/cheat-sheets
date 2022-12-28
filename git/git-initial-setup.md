Preferd setup on git.

1. Download and install git.

2. Open git bash and verify that installation has been successful.
```
git version
```
- This should return a git version information in the shell.

3. Preper the local system for remote repository
```
git config --global user.name "<username>"

git config --global user.email "<email@address>"

```

4. Confirm that the entered values are correct.
```
git config --global --list
```

5. Set the default git branch name from *master* to *main*.
```
git config --global init.defaultBranch "main"
```

6. Set up and alias to view git logs.
```
git config --global alias.hist "log --all --oneline --graph --decorate"
```

7. Set up core editor in git.
```
git config --global core.editor "notepad++.exe -multiInst -nosession"
```
- You will need to set the environmental system variables first to be able to open *notepad++.exe* from the shell.
- You can now use `git config --global -e` command to edit the config file with the text editor that you have just set.

8. Download and install P4Merge from Perforce website. P4Merge is a visual diff tool to help you compare the commit made in git.
	1. Install the P4Merge file that you just downloaded. You only need to install the *Merge and Diff tool (P4Merge).*
	2. Find the installation path of P4Merge and copy the path to be used to set up environmental variable.
	3. Open advanced system settings `sysdm.cpl` and set the *PATH* variable to the location of the P4Merge executable.

9. Set up P4Merge as the merge tool in git.
```
git config --global merge.tool p4merge

git config --global merrgetool.p4merge.path "C:/Program Files/Perforce/p4merge.exe"

git config --global mergetool.prompt false
```

10. Do the same for the diff tool now.
```
git config --global diff.tool p4merge

git config --global difftool.p4merge.path "C:/Program Files/Perforce/p4merge.exe"

git config --global difftool.prompt false
```