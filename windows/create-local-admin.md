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