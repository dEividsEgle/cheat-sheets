# Git cheat-sheet

![image](https://miro.medium.com/max/1652/1*D9HHDrEDw54JV741QkUx_w.png)

## Git Setup
| Command                                                   | Description                                        |
| --------------------------------------------------------- | -------------------------------------------------- |
| `git config --global --list`                              | List currently assigned username and email address. |
| `git config --global user.name "<username>"`              | Set the username in git config.                     |
| `git config --global user.email "<useremail@domain.com>"` | Set the user email in git config.                   |
| `git --global alias.<alias-to-be-set> "<git-command>"`    | Set alias in git config.                            |
| `git config --global init.defaultBranch <name>`           | I have set up my branch name to be *main* by default. Historicaly git had used *master* as the default branch name.                                                   |

-----------------------
## Basic Git Commands
| Command                                                                         | Description                                                                                                                                                                                                               |
| ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `git help <command>` | Bring up the manual page for any specified git command. |
| `git version`                                                                   | Show currently installed git version.                                                                                                                                                                                      |
| `git config -global -list`                                                      | List the currently assigned username and password.                                                                                                                                                                         |
| `git clone <url>`                                                               | Clone the repository from GitHub. Git will create a folder named after the GitHub repository.                                                                                                                              |
| `git add <file-name>`                                                           | Add new file to the staging area. Also used to add any changed that have been made to an already tracked file.                                                                                                             |
| `git add .`                                                                     | Add all the files recursively with the directory.                                                                                                                                                                          |
| `git commit -m "Commit message"`                                                | Commit the file from the staging area to the local repository.                                                                                                                                                             |
| `git commit -am "Commit message"`                                               | Add any changes made to a file into the staging area and commit them directly. Can only be done with files that are already being tracked.                                                                                 |
| `git ls-files`                                                                  | Get list of all files that git is tracking within the given repository (git add will add files into the staging area, therefor, the files become tracked files).                                                           |
| `git push <GitHub copy of repository><branch>` <br/> e.g.`git push origin main` | Push the changes to remote GitHub repository (It is a good practice to do pull prior to pushin any changed to the remote repository).                                                                                      |
| `git init`                                                                      | Add an existing project to git ( `git init` will create a *.git* folder in the current directory). You can follow up with `git add .` & `git commit -m <Comment line>`.                                                    |
| `rm -rf .git`                                                                   | Deleting the *.git* folder will remove the project from the git repository.                                                                                                                                                |
| `git pull <repository><brach>` <br/> `git pull origin master`                   | Pull down any changes made in the remote repository. It is best practice to do this prior to every `git push`. This will ensure that the repository is all up to data and that all the changes have been synced correctly. |
| `git reset HEAD <file-name>`                                                    | Un-stage a file from git staging area (revert changes made to the file; move the file to the working directory).                                                                                                           |
| `git checkout --<file-name>`                                                    | Get back to the last commit state.                                                                                                                                                                                         |
| `git mv <current-file-name> <new-file=name>`                                    | Rename a file. Git will stage the file' you can back out the rename or commit the file with the new name `git commit -m "File renamed"`.                                                                                   |
| `git add -A`                                                                    | If a file has been renamed outside of git (at the OS level) use `git add -A` to recursively add any changed and update any file names that have been changed, moved, and/or deleted.                                       |
| `git add -u`                                                                    | Update the index; let's git know that you have re-named a file rather than just adding the file.                                                                                                                           |
| `git rm <file-name>`                                                            | Delete already tracked file. Follow up with `git commit`. Use `git reset HEAD` to un-stage the deletion. Use `git checkout` to get the file back in the git directory.                                                     |
| `git log`                                                                       | Look at the commit history. Each commit is identified by SHA key, author details, commit data, and comment made during the commit.                                                                                         |
| `git log --all --graph --decorate --online`                                     | Create a simplified table with all the commits made.                                                                                                                                                                       |
| `.gitignore`                                                                    | Create a file within git directory where you can add specific files and/or folders to be ignored by git. File paterns can also be specified.                                                                               |

------------------------------------
## Git Comparisons
| Command | Description |
| --- | --- |
| `git diff` | Compare any modified files with the file currently in the directory and the staging area. You can set uo a tool like *p4merge* to visually compare the two files. |
| `git diff HEAD` | Comprate the differences in the working directory and the last commit. |
| `git diff --staged HEAD` | Compare the staging area with the last commit on the branch (HEAD). |
| `git diff --<filename>` | Limit the difference to only specific files |
| `git diff <ref ID> HEAD` | Compare all the changes made between the last commit and specified commit using the SHA identifiable key (`git log --oneline`). |
| `git diff HEAD HEAD^` | Compare the head and -1. You can use any SHA ID to compare any of the files and their differences. |
| `git diff <master of HEAD (local)><remote (github)>` <br/> `git diff main origin/main` | Compare the local repository to the remote repository |

-----------------------
## Git Branching and Merging
| Command | Description |
| --- | --- |
| `git branch -a` | List both the local and remote branches. |
| `git branch`  | List all global branches. |
| `git branch <branch name>` | Create a new branch. |
| `git checkout <branch name>` | Change branches to move away from the main branch. |
| `git branch -m <old-name> <new-name>` | Rename a git branch. |
| `git chekcout -b <branch name>` | Create and change to the new branch immediately.
| `git diff <master branch> <new branch>` | View the changes between the two branches prior to merging. |
| `git merge <branch name>` | From the master branch - merge the newly created branch to the master once all the work has been completed (fast forward merge). |
| `git rebase <source base>` </b> `git rebase master` | Apply any changes to the feature branch from the master branch. |
| `git rebase --abort` | Abort rebase during a conflict. |
| `git rebase --continue` | Proceed with the rebase once the conflict issues have been resolved by comparing the differences. |
| `git fetch` | Update references between the local and remote repository. |
| `git pull --rebase`  | Rebase the changes from remote repository (GitHub). |

--------------------------------
## Stashing
| Command | Description |
| --- | --- |
| `git stash` | Stash away any changes that are a work in progress. |
| `git stash apply` | Put the file back in it's original state. Continue editing the file. |
| `git stash list` | View the stashed away files. |
| `git stash drop` | Drop the last stash after you have done `git commit`. |
| `git stash -u` | Stash any untracked files that are not excluded by *.gitignore*. |
| `git stash pop` | Apply the stash and drop the last stash from the list. |
| `git stash show stash @{#}` | Look at a specific stash when dealing with multiple files that contained in stash list. |
| `git stash apply stash @{#}` | Apply a specific change that has been captured in a stash and is stored in the stash list. |
| `git stash drop stash @{#}` | Drop a specific file from the stash list. |
| `git stash clear` | Drop all stashes from the stash list. |
| `git stash branch <branch name>` | Stash files in different branch. |

------------------------------
## Git Tagging
| Command | Description |
| --- | ---|
| `git tag <name-of-the-tag>` | Create a lightweight tag on a particular commit. |
| `git tag --list` | View all created tags. |
| `git show <tag-name>` | Show commit that is at the tag. |
| `git tag --delete <tag-name>` | Delete the tag. |
| `git tag -a v-1.0` | Add annotated tag. Annotated tags can be used for major milestones or version numbers in source code. |
| `git commit --amend` | Amend the commit message. |
| `git tag <tag> -m "<comment>"` | Add message to the tag. |
| `git diff <tag-name> <tag-name>` | Compare the differences between the two tags. |
| `git tag -a <tag> <commit ID>` | Add a tag to a previous commit using the SHA identifier ID. |
| `git tag -a <tag-name> -f <commit ID>` | Edit the tag (update). |
| `git push origin <tag-name>` | Sync the commit and push the tag to GitHub. |
| `git push origin <branch name> --tags` | Sync the master branch and push all the tags to the remote repository. |
| `git push origin :<tag-name>` | Delete a tag from the remote repository. (The tag will remain within the local repository.) |

----------------------------------------------------


