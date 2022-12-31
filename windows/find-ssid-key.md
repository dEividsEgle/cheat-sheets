## Find SSID keys via CMD
-----------------------
#### Overview
Simple trick to find the key to the SSID profile via CMD.

-----------------------------

1. Show available profiles
```cmd
netsh wlan show profile
```
2. View a specific profile
```cmd
netsh wlan show profile name="<name of the profile>"
```
3. Extract the key from the SSID profile
```cmd
netsh wlan show profile name="<name of the profile>" Key=Clear | find "Key Content"
```

