---
description: run regedit.exe in cmd
---

# Registry

> Windows Registry is a collection of databases that contains the system's configuration data.

The windows registry consists of Keys and Values. Registry Values are the data stored in these Registry Keys.

Registry Hive: a group of Keys, subkeys, and values stored in a single file on the disk.

### Structure of the Registry:

| root keys             | description                                                                                                         |
| --------------------- | ------------------------------------------------------------------------------------------------------------------- |
| HKEY\_CURRENT\_USER   | Configuration information for the user who is currently logged on.                                                  |
| HKEY\_USERS           | All the actively loaded user profiles on the computer.                                                              |
| HKEY\_LOCAL\_MACHINE  | Configuration information particular to the computer.                                                               |
| HKEY\_CLASSES\_ROOT   | <p>A subkey of HKLM\Software.<br>It makes sure the correct program opens when you open a file through Explorer.</p> |
| HKEY\_CURRENT\_CONFIG | Hardware profile that is used at system startup.                                                                    |

