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

In `C:\Users<username>\AppData\Local\Microsoft\Windows`:

* USRCLASS.DAT -> HKEY\_CURRENT\_USER\Software\CLASSES

Apart from them, Windows creates Amcache hive to save information on programs that were recently run on the system.

* `C:\Windows\AppCompat\Programs\Amcache.hve`

## Data Acquisition

> Whether it's a live system or an image, for accuracy, it's recommended to make a copy of it.

{% hint style="info" %}
The registry hives in  `%WINDIR%\System32\Config` are restricted files, and can't be copied.
{% endhint %}

Tools we can use:

* Autopsy
* FTK Imager

## Exploring Registry

> After we copied the registry hives, we need a tool to view them. (regedit only works with live system)

Tools we can use:

* AccessData Registry Viewer
