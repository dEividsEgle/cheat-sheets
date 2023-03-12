# Processing and Handling Jobs

## Processes

#### Basic commands to handle processes
| Command                                                                                | Description                                                                                                                                                                    |
| -------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `ps`</br>`ps -e`</br>`ps -ef`</br>`ps -eH`</br>`ps -e --forest`</br>`ps -u <username>` | Display processes.</br>Display all processes.</br>Display full list of processes.</br>Display a process tree.</br>Display a process tree.</br>Display user specific processes. |
| `pstree`                                                                               | Display processes in tree view.                                                                                                                                                |
| `top`                                                                                  | Interactive view of processes.                                                                                                                                                 |
| `<command> &`                                                                          | Start a command in background.                                                                                                                                                 |
| `Ctrl + C`                                                                             | Kill processes running in foreground.                                                                                                                                          |
| `Ctrl + Z`                                                                             | Suspend the foreground process.                                                                                                                                                |
| `bg`</br>`bg %<num>`                                                                   | Send the current suspended process to the background.</br>Send a specific suspended process to the background.                                                                 |
| `fg`</br>`fg %<num>`                                                                   | Sames us `bg`, but forgrounds a background process.                                                                                                                            |
| `kill`                                                                                 | Kill the proces either by a job number or PID.                                                                                                                                 |
| `jobs %<num>`                                                                          | List jobs by their number.                                                                                                                                                     |
|                                                                                        |                                                                                                                                                                                |
#### `ps` command options

- Show all running processes.
```bash
ps x
```
- Show all processes on the system not just the ones user owns.
```bash
ps ax
```
- Include more detailed information on process.
```bash
ps u
```
- Show full command names.
```bash
ps w
```


----
## Job handling

#### Cron job scheduling
**Cron
- Cron service is a time based job scheduling system that starts whenever the OS boots. Cron jobs are a great way to automate processes that can be scheduled using the **Crontab**.
**Crontab**
- Crontab is a program to create, read, update, and delete job schedules. 
- Cron table is a configuration file that specifies when the command should be executed by cron. 
- Each line in cront table represnts when to run and what to run.
- The '*when to run*' consists of five fields.
	- Day of the Week (0-6)
	- Month of the Year (1-12)
	- Day of the Month (1-31)
	- House (0-23)
	- Minute (0-59)

- A star `*` in any field means to match every value.
- Use the contab(5) manual page for complete information on the crontab format.

| Command               | Description                      |
| --------------------- | -------------------------------- |
| `crontab <file-name>` | Install new crontab from a file. |
| `contrab -l`          | List cron jobs.                  |
| `crontab -e`          | Edit cron jobs.                  |
| `crontab -r`          | Remove all cron jobs.            |

