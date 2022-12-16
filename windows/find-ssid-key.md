1. Show available profiles
```
netsh wlan show profile
```
2. View a specific profile
```
netsh wlan show profile name="<name of the profile>"
```
3. Extract the key from the SSID profile
```
netsh wlan show profile name="<name of the profile>" Key=Clear | find "Key Content"
```

