1. Open CMD as Adminsitrator
2. Check for compatibility
```
netsh wlan show drivers
```
	Look for hosted network support; Yes means this will be supported
3. Create ad hoc WiFi network
```
netsh wlan set hostednetwork mode=allow

ssid=<ad hoc SSID> key = <password>
```
4. Start ad hoc WiFi network
```
netsh wlan start hostednetwork
```