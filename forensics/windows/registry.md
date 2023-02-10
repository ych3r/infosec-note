---
description: '> regedit.exe'
---

# Registry

> Windows Registry is a collection of databases that contains the system's configuration data.

The windows registry consists of Keys and Values. Registry Values are the data stored in these Registry Keys.

**Registry Hive**: a group of Keys, subkeys, and values stored in a single file on the disk.

## Structure of the Registry

The registry on Windows contains the following five root keys:

| root keys             | description                                                                                                         |
| --------------------- | ------------------------------------------------------------------------------------------------------------------- |
| HKEY\_CURRENT\_USER   | Configuration information for the user who is currently logged on.                                                  |
| HKEY\_USERS           | All the actively loaded user profiles on the computer.                                                              |
| HKEY\_LOCAL\_MACHINE  | Configuration information particular to the computer.                                                               |
| HKEY\_CLASSES\_ROOT   | <p>A subkey of HKLM\Software.<br>It makes sure the correct program opens when you open a file through Explorer.</p> |
| HKEY\_CURRENT\_CONFIG | Hardware profile that is used at system startup.                                                                    |

## Accessing registry hives offline

> regedit.exe can only be used on live system.

If we only have access to a disk image, we must know where the registry hives are located on the disk.

<figure><img src="../../.gitbook/assets/Screenshot 2023-01-27 at 11.49.17 AM.png" alt=""><figcaption></figcaption></figure>

In `C:\Windows\System32\Config` directory:

1. DEFAULT -> HKEY\_USERS\DEFAULT
2. SAM -> HKEY\_LOCAL\_MACHINE\SAM
3. SECURITY -> HKEY\_LOCAL\_MACHINE\Security
4. SOFTWARE -> HKEY\_LOCAL\_MACHINE\Software
5. SYSTEM -> HKEY\_LOCAL\_MACHINE\System

**SAM** hive stores user accounts and their password hashes, groups, and domain information.

**SYSTEM** hive contains drive letter designations for internal and external storage devices, the system name, and configuration data for hardware and software. It can help identify a computer and any storage devices that might have been mounted.

There are also two hives containing user information.

In `C:\Users\<username>`:

* NTUSER.DAT -> HKEY\_CURRENT\_USER

**ntuser.dat** contains user-specific information, such as personalized settings.

In `C:\Users\<username>\AppData\Local\Microsoft\Windows`:

* USRCLASS.DAT -> HKEY\_CURRENT\_USER\Software\CLASSES

Apart from them, Windows creates Amcache hive to save information on programs that were recently run on the system.

* `C:\Windows\AppCompat\Programs\Amcache.hve`

### Data Acquisition

> Whether it's a live system or an image, for accuracy, it's recommended to make a copy of it.

{% hint style="info" %}
The registry hives in `%WINDIR%\System32\Config` are restricted files, and can't be copied.
{% endhint %}

Tools we can use:

* Autopsy
* FTK Imager

### Exploring Registry

> After we copied the registry hives, we need a tool to view them. (regedit only works with live system)

Tools we can use:

* AccessData Registry Viewer

## System Information and Accounts

**OS Version**:&#x20;

* `HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion`

**Current control sets:**

> **Current control sets** are used for controlling system startup. **ControlSet001** will point to the Control Set that the machine booted with, **ControlSet002** will be the last known good configuration.

* `HKLM\SYSTEM\CurrentControlSet`

**Computer Name:**

* `HKLM\SYSTEM\CurrentControlSet\Control\ComputerName\ComputerName`

**Time Zone:**

* `HKLM\SYSTEM\CurrentControlSet\Control\TimeZoneInformation`

**Network Interfaces and Past Networks:**

* `HKLM\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters\Interfaces`
* The past networks a given machine was connected to can be found in the following locations:
  * `HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\NetworkList\Signatures\Unmanaged`
  * `HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\NetworkList\Signatures\Managed`

**Autostart Programs (Autoruns):**

* programs or commands that run when a user logs on:
  * `NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Run`
  * `HKLM\NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\RunOnce`
  * `HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\RunOnce`
  * `HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\policies\Explorer\Run`
  * `HKLMSOFTWARE\Microsoft\Windows\CurrentVersion\Run`
* services information:
  * `HKLM\SYSTEM\CurrentControlSet\Services`

**SAM hive and user information:**

* `HKLM\SAM\Domains\Account\Users`

## Usage or knowledge of files/folders

**Recent Files:**

* Recently opened files for each user.
* `NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\RecentDocs`

**Office Recent Files:**

* Microsoft Office recent files.
* `NTUSER.DAT\Software\Microsoft\Office\VERSION\UserMRU\LiveID_####\FileMRU`

**ShellBags:**

* Every user has a specific layout for the folder. This information can identify the Most Recently Used files and folders.
* Use Eric Zimmerman's tool: ShellBags Explorer.
* `USRCLASS.DAT\Local Settings\Software\Microsoft\Windows\Shell\Bags`
* `USRCLASS.DAT\Local Settings\Software\Microsoft\Windows\Shell\BagMRU`
* `NTUSER.DAT\Software\Microsoft\Windows\Shell\BagMRU`
* `NTUSER.DAT\Software\Microsoft\Windows\Shell\Bags`

**Open/Save and LastVisited Dialog MRUs:**

* A dialog box often appears asking for the file location when we open or save a file. Windows remembers that location.
* `NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\OpenSavePIDlMRU`
* `NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\LastVisitedPidlMRU`

**Windows Explorer Address/Search Bars:**

* The paths typed in the Explorer address bar or searches:
* `NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\TypedPaths`
* `NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\WordWheelQuery`

## Evidence of Execution

**UserAssist:**

* Windows Explorer keeps track of applications launched by the user. It contains information about the programs launched, the time of their launch, and the number of times they were executed.
* `NTUSER.DAT\Software\Microsoft\Windows\Currentversion\Explorer\UserAssist{GUID}\Count`

**ShimCache:**

* A mechanism used to keep track of application compatibility with the OS and tracks all applications launched on the machine. Its main purpose in Windows is to ensure the backward compatibility of applications.
* Use AppCompatCache.
* `SYSTEM\CurrentControlSet\Control\Session Manager\AppCompatCache`

**AmCache:**

* AmCache performs a similar function to ShimCache. It stores additional data related to program executions. It includes execution path, installation, execution and deletion times, and SHA1 hash.
* `C:\Windows\appcompat\Programs\Amcache.hve`
* info about the last executed programs: `Amcache.hve\Root\File{Volume GUID}\`

**BAM/DAM:**

* Background Activity Monitor keeps a tab on the activity of background apps.
* Desktop Activity Moderator optimizes the power consumption of the device.
* `SYSTEM\CurrentControlSet\Services\bam\UserSettings\{SID}`
* `SYSTEM\CurrentControlSet\Services\dam\UserSettings\{SID}`

## External Devices/USB device

**Device identification:**

* USK keys plug information.
* `SYSTEM\CurrentControlSet\Enum\USBSTOR`
* `SYSTEM\CurrentControlSet\Enum\USB`

**First/Last Times:**

* First and last time the device was connected.
* `SYSTEM\CurrentControlSet\Enum\USBSTOR\Ven_Prod_Version\USBSerial#\Properties{83da6326-97a6-4088-9453-a19231573b29}####`
* 0064: First connection time
* 0066: Last connection time
* 0067: Last removal time

**USB device Volume Name:**

* `SOFTWARE\Microsoft\Windows Portable Devices\Devices`

