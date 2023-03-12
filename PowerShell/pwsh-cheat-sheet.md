# PowerShell Cheat Sheet
----------------
# PowerShell execution policy

- Restricted The default powershell execution policy. This policy does not allow execution of scripts.
- AllSigned Only allows to run scripts that have been cryptographically signed by a trusted party.
- RemoteSigned Allows to wirte self-written scripts and downloaded scripts as long as it has been digitally signed by a trusted party.
- Unrestricet Allows to run any script.

| Command       | Description                                      |
| ------------- | ------------------------------------------------ |
| `cd`          | Change directory.                                |
| `dir`         | List the contents of the current directory.      |
| `Get-Alias`   | View all the aliases configured in pwsh.         |
| `Get-Command` | Find exisiting commands available in powershell. |
|               |                                                  |

----------

# Command types
#### Overview
Most powershell command follow the *Verb-Noun* schema and come in different flavours suchs as: cmdlets, functions, aliases, scripts. Most of the built-in commands are refered to as cmdlets most commonly writen in C#. The command type can be identified by looking at the *CommandType* when using `Get-Command`.

- Cmdlet
	- Default powershell commad most commonly writen in C#.
- Functions
	- Command writen in powershell to achive a certain goal.

| Command                    | Description                                                                       |
| -------------------------- | --------------------------------------------------------------------------------- |
| `Get-Help <cmdlet>`        | Retrieve manual page for a specific command.                                      |
| `Get-Help <general_topic>` | Retrieve manual page to learn about specific topic.                               |
| `Get-Help -Name about*`    | List all the available general topic help files.                                  |
| `Update-Help`              | Update the offline help files.                                                    |
| `Set-StrictMode`           | Set powershell to throw errors when you reference a property that doesn't exists. |
| `Get-Variabel`             | Return all variables currently stored in memory.                                                                                  |

### Variables

| Variable      | Description                                                                                          |
| ------------- | ---------------------------------------------------------------------------------------------------- |
| `$null`       | Represents nothing.                                                                                  |
| $lastexitcode | Return the exit code of the last command. `1` typically indicates failure and `0` indicates success. |
| `$Error`      | Stores an array of all the errors returned in the current pwsh sessions.                             |
|               |                                                                                                      |

#### Using Double vs. Single Quotes
When assigning variable a string you must either inclose it in single quotes or doulbe quotes. Single quotes tell that you mean exactly what you type where as double quotes expand the variable and show the value.

### Data structures

#### Arrays
Use the `@` sign when you want to inform powershell that you are creating an array. Array allowes you to define multiple elements in a single variable. When returning an array, powershell will display each of the elements in a new line. Same as string characters, arrays start to number at 0, meaning the first element is equal to *zero*. Using -1 as the index will return the last element. Use the `..` range output to access multiple elements in an array.

- Create an array
```powershell
$array = @('first', 'second', 'third')
```
- Return an element from an array
```powershell
$array[-1]
```
- Change an element within an array
```powershell
$array[2] = 'new element'
```
- Add a new element to an array
```powershell
$array = $array + 'fourth'
```
- Alternatively you can use the `+=` operator to add an element to an existing array
```powershell
$array += 'fifth'
```
- Add multiple elements at once to an array
```powershell
$array += @('sixth', 'seventh')
```

Each time you add an element to an array, a new array is created from the old array and the new elements. Same happens when an element is removed from an array.  This is beacuse the arrays in powershell have fixed size.

#### ArrayList
If there is a need to add and remove elements to an array, the better option is to use *ArrayList*, especially when dealing with array containing more than 100 elements. ArrayLists do not have fixed size making it easier to add and remove elements to an array. Apart from that, both arrays and ArrayLists work very similar.

- Create an *ArrayList*
```powershell
$array = [System.Collections.ArrayList]@('first', 'second', 'third')
```

Use the `Add()` and `Remove()` methods to add or remove items to an *ArrayList*

- Add an element to an ArrayList
```powershell
$array.Add('fourth')
```
- Remove the output when adding to an ArrayList
```powershell
$null = $array.Add('fifth')
```

When removing items from the *ArrayLists* you do not need to use the index, rather, you can just use the value with the method.

- Remove an item from the array
```powershell
$array.Remove('second')
```

#### Hashtables
Hashtable is a powershell data structure containing a list of *key-value pairs*. Duplicate values are not allowed and each key must point to a single value.

Hashtables can help to correlate two pieces of data like an username and full name or even user properties.

- Define user properties in a hashtable
```powershell
$newuser = @{
	FullName = 'Deivids Egle'
	FirstName = 'Deivids'
	LastName = 'Egle'
	Country = 'UK'
	Username = 'deivids.egle'
}
```

- Access a value by reading the key
```powershell
$newuser['fullname']
$newuser.fullname
$newuser.keys
$newuser.values
```

- Add a new element to hashtable
```powershell
$newuser.Add('City', 'London')
$newuser['Phone'] = '0100 785 9567'
```

- Modify an existing key
```powershell
$newuser.ContainsKey('Phone')
$newuser['Phone'] = "0101 821 9910"
```

- Remove key value
```powershell
$newuser.Remove('Phone')
```


### Objects

#### Overview
Object is an individual instance of a specific template, called a class. A class specifies the kinds of types an object will contain. Methods define actions that can be taken on a particular object.

Use the `Select-Object` cmdlet to look at the object's properties using the `-Property` parameter. You can directly reference the properties by using the *dot notation*.

Using the `Get-Member` cmdlet to look at all the properties and methods that exists on the object.

#### Custom object
Create custom objects in powershell using thre `New-Object` cmdlet.

#### Combining Commands
In powershell you chain together the commands by using the *pipeline* `|` tool. This allows to redirect output of one command dirrectly into another command, however, not all commands might accept the pipeline input. In powershell, the pipeline tool can not only pass strings but event objects through the *pipe*.

#### Parameter Binding
Powershell matches each object passed into the command to the various parameters specified with the used cmdlet. Use the `Get-Help` cmdlet to learn more about each cmdlet parameters. This can also reveal if the particular cmdlet parameter can be passed through pipeline.

Powershell will match pipeline input parameters in two ways; first via *ByValue* and second via *ByPropertyName*.

```powershell
$svcObject = [PSCustomObject]@(Name = 'w32tm'; ComputerName = 'srv01')
$svcObject | ps
```

### Control Flow
Control flow allows you to write a flexible single script that can circle back to previous lines and introduce different paths for the script to take.

#### Comparison operators
Use comparison operators to write expressions by placing them between two values.

| Operator    | Use                                                                                                 |
| ----------- | --------------------------------------------------------------------------------------------------- |
| `-eq`       | Compare two values and return True if they are equal.                                               |
| `-ne`       | Compare two values and return True if they are not equal.                                           |
| `-gt`       | Comprate two values and return True if the first value is greater than the second value.            |
| `-ge`       | Compare two values and return True if the first value is greater than or equal to the second value. |
| `-lt`       | Compares two values and returns True if the first value is less than the second value.              |
| `-le`       | Compares two values and returns True if the first value is less than or equal to the second value.  |
| `-contains` | Returns True if the second value is "in" the second value.                                                                                                    |

- Use help to learn more about comparison operators
```powershell
help about_comparison_operators
```

#### The `if` statement
If statements are used to validate if X is true, then do Y.

```powershell
$srv = @('srv1', 'srv2', 'srv3')
if (Test-Connection -ComputerName $srv[0] -Quiet -Count 1) {
	Get-Content -Path "\\$($srv[0]")\c$\config.txt"
}
Get-Content -Path "\\$($srv[1])\c$\config.txt"
```

#### The `else` statement
Else statement works as catchfall: if the first `if` statement fails, do the second statement. 

```powershell
if (Test-Connect -ComputerName $server[0] -Quiet -Count 1) {
	Get-Content -Path "\\$($stv[0])\c$\config.txt"
} 
else {
	Write-Error -Message "The server $($srv[0]) is not responding!"
}
```

#### The `elseif` statement
```powershell
if (Test-Connection -ComputerName $srv[0] -Quiet -Count 1) {
	if ($srv[0] -eq $problemSrv) {
		Write-Error -Message "The server $srv[0] does not have the right file!"
	}
	else {
		Get-Content -Path "\\$srv[0]\c$\config.txt"
		}
		else {
		Write-Error -Message "The server $srv[0] is not responding!"
		}
}
```

```powershell
if (!(Test-Connection -ComputerName $srv[0] -Quiet -Count 1)) {
	Write-Error "The server $srv[0] is not responding!"
} 
elseif ($srv[0] -eq $problemSrv)
		Write-Error "The server $srv[0] does not have the right file!"
	} 
	else {
		Get-Content -Path "\\$srv[0]\c$\config.txt"
	}


```

### Loop

#### Overview
Loops let you execute code repeatedly in powershell until a condition changes.

#### foreach loop
Foreach loop goes through a list of objects and performs the same action for each object. 

```powershell
foreach ($object in $objects) {
	Move-Item -Path "\\srv-fs-01\data$" -Destination "\\srv-fs-01\archive$" 
}
```

The foreach statement contains three elements within parentheses: a **variable**, the **keyword** `in`, and the **object** of array to iterate. As it loops through the list, powershell will copy the object it's looking at into a variable.

#### ForEach-Object cmdlet
Works similar to `foreach` loop but the the objects have to be passed through as parameters.

---------

# Error handling

The `-ErrorAction` parameter controls the output of the errors, the five following actions determin how to handle the error.

 - Continue: Outputs the error message and continues to execute the
	cmdlet. This is the default value.

- Ignore Continues to execute the cmdlet without outputting an error
	or recording it in the $Error variable.

- Inquire Outputs the error message and prompts the user for input
	before continuing.

- SilentlyContinue Continues to execute the cmdlet without outputting
	an error, but records it in the $Error variable.

- Stop Outputs the error message and stops the cmdlet from executing.

The `$ErrorActionPreference` controls the default behavior of the error action, however, the `-ErrorAction` parameter can override the default variable. 

All errors created in the powershell sessions are stored in the `$Error` variable, ordered by the time that they appeared. You can use the index notation to access a specific error.

- Learn more about error handling
```powershell
Get-Help about_try_catch_finnaly
```

-------------

# Functions

#### Overview
Functions can help increase readability and usability of the code.

- Get a list of all the functions stored in PowerShell
```powershell
Get-Command -CommandType Function
```

- Learn more about advanced functions
```powershell
Get-Help about_Functions_Advanced_Parameters
Get-Help about_Functions_Advanced
```

----------

# Modules

#### Overview

PowerShell module is a text file with a `.psm1` file extension. A module is a group of similar functions packaged together into one file. PowerShell ships already with built-in modules, but there are also available 3rd party modules, or modules that you have built yourself.

Modules typically need to be installed and then imported into the PS session prior to use. Powershell can also auto-import a module whenever a command is referenced.

- Find modules in current powershell session
```powershell#
Get-Module
```
- Find all installed but not imported modules
```powershell
Get-Module -ListAvailable
```

All the PS module paths are stored in the `$env:PSModulePath` variable.

The **PowerShellGet** module contains all the commands used to interact with PowerShell Gallery. PowerShell Gallery is an online repository where anyone can find, download and upload modules for use with powershell.

- List all the commands form `PowerShellGet` module
```powershell
Get-Command -Module PowerShellget
```

#### The `.psm1` file
Any text file with the `.psm1` exetension can be a powershell module as long as it has functions within it. 

#### The `.psd1` file
The module manifest is an optional text file written in the form of PS hashtable. This typically contains elements that describe metadata about the module.

- Create a module manifest template
```powershell
New-ModuleManifest -Path <file-path-for-the-manifest> -Author 'Deivids Egle' -RootModule <file.psm1> -Description '<informative-reading>' -ModuleVersion 1.0.0
```

----------

# Running Remote Scripts

#### Overview
Powershell remoting can help user remotely run command or scripts in a session on one or more computers. Powershell remoting uses the Windows Remote Management (WinRM) service. 

Powershell remoting makes excesive use of *scriptblock*. To use a script block, you must place the code to execute between curly brackets.

#### `Invoke-Command` cmdlet

