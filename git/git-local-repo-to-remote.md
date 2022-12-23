
# Local Repo to Remote Repo

Connect git local repository to remote repository

1. Add remote repository
```
git remote add origin <remote-repo-URL>
```
2. Push all the changes
```
git push --all origin
```
3. Allow all branches to use the remote repository during `git pull` and `git push`.
```
git push --all --set-upstream origin
```
4. If you get the following error message: *fatal: refusing to merge unrelated histories* use the command below
```
git pull --allow-unrelated-histories
```
