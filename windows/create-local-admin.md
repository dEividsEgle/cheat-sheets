## Create local admin account via CMD.
---------------------------
#### Overview
Sometimes when you need access to the computer but it has been kicked off the domain and you do not poses the local admin credentials, however, you do poses the right tools.

----------------------------------
1. Create the account
```
net user /add [username] [password]
```
2. Add newly created user to the group: administrators
```
net localgroup administrators [username] /add
```
3. Enable the administrator account
```
net user administrator /active:yes
```