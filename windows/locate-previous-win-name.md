# Find Previous System Name
------------------------------------
#### Overview
Often you notice that devices in AD have gone missing from domain, but then you come across a new device and not sure where how it got here.

There is a chance that you can find the name of the device if it has been re-named by someone, once it was assigned to a new staff member.

------------
1. Open `regedit` from windows run box.
2. Navigate to the following key:
```
HKLM:\SOFTWARE\Microsoft\SchedulingAgent
```
3. Look for `OldName` string value, and the data will be the name of the old device.

>[!NOTE:] I haven't had a chance to test this yet, but I would imagine that after a clean install, the entry would just show the current name of the device.


