## Powercfg reference
---------------------------------------
#### Overview
Some days users are adamant that their device is possesed. 

More often or not, if you look in the event log it will be evident that Windows Update had done it's nightly maintenance run that has kicked the fan off.

However, whe ever you feel inquisitive; use the reference below to dive deeper down the rabbit hole. 

Powercfg is a command-line utility that help you managed the computer power settings. It can alos produce some great reports and estimates. In addition to that, you can save the power configuration schema using `import` and `export` commands.

------------------------------------------------------
### Basics
| Command                     | Description                                               |
| --------------------------- | --------------------------------------------------------- |
| `powercfg /?`               | Display help and learn more about the *powercfg* command. |
| `powercfg /q`               | Display the contents of the power scheme                  |
| `powercfg /getactivescheme` | Display GUID of the currently active power scheme         |
| `powercfg /lastwake`        | Generate a report of last event that woke the computer    |
| `powercfg /waketimers`      | Look at the active wake times                             |
|                             |                                                           |

----
### Sleep states
| State | Descriptions  |
|:-----:| ------------- |
|  S1   | Light sleep   |
|  S2   | Deeper sleep  |
|  S3   | Deepest sleep |
|  S4   | Hibernation   |

- [Windows sleep states](https://learn.microsoft.com/en-us/windows-hardware/drivers/kernel/system-sleeping-states)
-------
### Reports
| Command                 | Description                                                                            |     |
| ----------------------- | -------------------------------------------------------------------------------------- | --- |
| `powercfg /srumutil`    | Genereate a report of energy estimation by *System Resource Usage Monitor (SRUM)*      |     |
| `powercfg /sleepstudy`  | Generate a report of system power transition                                           |     |
| powercfg /A             | View supported sleep states. Older devices most likely will not support various states |     |
| powercfg /batteryreport | Generate a report of batery usage                                                                                       |     |

----
### Examples

#### Enable and Disable device *wake* ability
You can also enable certain devices to wake the computer from sleep state. For example I keep my laptop docked and the power button is under the screen which I rarely lift. I have enable my keyboard to wake the laptop from sleep state, however, at the same time, mice is often hard to keep still if you are at you desk so you might want to prevent it from waking the computer.

1. Query the devices that can wake the computer.
```cmd
powercfg /devicequery s3_supported
```
- In the list I found the *HID Keyboard Device* which is the keyboard that I am using.

2. Next I enable the device to wake the computer.
```cmd
powercfg /deviceenablewake 'USB Composite Device (001)'
```

3. Disable the mice to be able to wake the computer.
```cmd
powercfg /devicedisablewake 'USB Composite Device (002)'
```

> [!NOTE] You should verify that these devices are the ones that you expect them to be. In my case, both of the devices are using Logitech Unifying receiver, yet, I can still disable one and leave the other enabled even though they are using one USB port.

----
### Resources

- [MS Documentation on `powercfg` tool.](https://learn.microsoft.com/en-us/windows-hardware/design/device-experiences/powercfg-command-line-options)
