# Windows Configuration Settings
-----------------------------------------
#### Overview
Some settings I would like to automate in Windows 11 22H2. There are more settings to be adjusted, this is just a rough list to go over of most common settings visible in the Settings UI. 

>[!NOTE] Try to keep settings user related and so that they can be adjusted once applied during initial setup.

---------------------------------------------
## Privacy Settings

- [x] Do not let apps show personalized ads using ID
- [x] Do not let websites show local content
- [x] Do not let windows improve start and search results by tracking apps
- [x] Do not show suggested content in settings
- [x] Do not send diagnostic data
- [ ] Disbale inking and typing
- [x] Disable tailored experience
- [x] Disable feedback
- [x] Do not send activity history to microsoft
- [x] Disable windows safe search
	- Added 3 new functions
		- SafeSearchModerate
		- SafeSearchStrict
		- SafeSearchDisabled
- [ ] Disable cloud content search
- [x] Disable search history
	- Added 2 new functions
		- DeviceLocalSearchDisabled
		- DeviceLocalSearchEnabled
- [ ] Do not show search highlights
	- Something is already preventing this from being enabled [???]
- [x] Disable location services
- [x] Disable camer access (Through API)
- [x] Disable mic access (Through API)
- [x] Disable Online Speech Recognition
	- Added 2 new functions
		- DisableOnlineSpeechRecognition
		- EnableOnlineSpeechRecognition
- [x] Do not share apps across various devices (MS Connected)
	- Added 2 new functions
		- AppSharingOff
		- AppSharingMyDevice
- [x] Do not share with nearby devices
	- Added 2 new functions
		- NearbySharingOff
		- NearbySharingMyDevices
-----------------------------------------
## Network Setting Tweaks

- [x] Set network profile to private
- [x] Turn off network discovery
	- Set network to *Public*
- [x] Turn off file and print sharing
	- Set network to *Public*

## Service Tweaks (Windows Update)

- [x] Get MS App updates together with Windows Update
- [x] Disable Maintenance Wake-up
- [x] App sharing across devices
	- Added 2 new functions
		- AppSharingOff
		- AppSharingMyDevices
- [x] Nearby sharing
	- Added 2 new functions
		- NearbySharingOff
		- NearbySharingMyDevices
- [ ] NoDriveTypeAutorun
	- Chech the meaning behind the values
-----------------------------------------------
## Personalization Settings

- [x] Remove Widgets from taskbar
	- Added 2 new functions
		- HideWidgetsIcon
		- ShowWidgetsIcon
- [x] Show task view icon on taskbar
	- Added 2 new functions
		- ShowTaskView
		- HideTaskView
- [x] Do not show system tray icons
	- Default behavior - couldn't find a key that would work.
- [x] Center align taskbar
	- Added 2 new functions
		- CenterAlignTaskbar
		- LeftAlignTaskbar
- [x] Remove search from taskbar
	- Added 2 new functions
		- HideTaskbarSearch
		- ShowTaskbarSearch
- [x] Do not show chat on taskbar
	- Added 2 new functions
		- HideTaskbarChatIcon
		- ShowTaskbarChatIcon
- [x] Set start menu to show more pins
	- Added 3 new functions
		- EvenStartMenu
		- ShowMorePinsInStartMenu
		- ShowMoreRecommendationsInStartMenu
- [x] Do not show new apps in recommendations
	- Added 2 new functions
		- HideRecentlyAddedApps
		- ShowRecentlyAddeApps
> [!CAUTION] Both functions will disable the settings as well.
 
- [ ] Do not show recent files in recommendations  
- [x] Do not show most used apps in recommendations
	- Added 2 new functions
		- HideMostUsedApps
		- ShowMostUsedApps
> [!CAUTION] Both functions will disable the settings as well.

- [ ] Enable HDR
	- Couldn't find an option for this.
- [x] Set control panel icons to small (Classic)
- [ ] Set windows theme to dark
- [ ] Set app theme to dark
- [x] Enable transperency effect
	- Part of visual settings
- [x] Enable annimation effects 
	- Part of visual settings
- [x] Hide desktop icons
- [ ] Set high performance
	- [ ] Do nothing when power button is pressed
	- [ ] Do nothing when lid is closed
	- Look into doing an export of current settings and see if can be imported with `powercfg /import`

- [ ] Add personal folder to start menu
- [ ] Add settings to start menu
- [ ] Add networks to start menu
- [ ] Set region format to english US

- [ ] Add optional feature RSAT (Maybe to be added in software installation script.)
-------------------------------------
##  Explorer Tweaks

- [x] Disable AutoPlay 
- [x] Disable AutoRun 
- [ ] Pin user folder to quick access
	- Looks to be a bit too brute for this script
- [ ] Show details pane in file explorer
- [x] Open file explorer to home
- [x] Do not show recently used files
- [x] Do not show frequently used folders
- [x] Do not show files from office.com
	- Added 2 new functions
		- ShowCloudFiles
		- HideCloudFiles
- [x] Use *Compact View* in explorer
- [x] Show hidden files
	- See if can be prevented from being changed by user
- [ ] do not hide empty drives
- [x] Show file extensions
	- See if can be prevented from being changed by user
- [ ] Show This PC in navigation pane
	- Looks to be a bit too brute for this script
- [ ] Hide network in navigation pane
	- Looks to be a bit too brute for this script