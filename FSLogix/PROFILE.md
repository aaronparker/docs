# Profile Cleanup script

## Warning

Caveat Emptor - this script will **DELETE** target files and folders. Be certain that the targets listed in the XML are OK to be removed. Test and test again before putting the script into production.

## About Remove-ProfileData.ps1

`Remove-ProfileData.ps1` is used to delete files and folders in the user profile to reduce profile size, thus keeping Profile Containers sizes to a minimum. The script runs within the user session and reads an XML file that defines a list of files and folders to remove from the profile.

Actions on a target path can be:

* Prune - the XML can include a number that defines the age in days for last write that the file must be older than to be deleted. Essentially reducing the size of the folder.
* Delete - the target path will be deleted. Where the administrator may want to remove a target path, the Delete action will delete the entire folder.
* Trim - where the target path contains sub-folders, this action will remove all sub-folders except for the newest folder.

Supports `-WhatIf` and `-Verbose` output and returns a list of files removed from the profile. Add `-Verbose` will output the total size of files removed from the user profile and processing time at the end of the script. All targets (files / folders) that are deleted, will be logged to a file.

Deleting files from the profile can potentially result in data loss, so testing is advised and the use of `-Confirm:$False` is required for the script perform a delete.

`Remove-ProfileData.ps1` and supporting files are available on in [the repository on GitHub](https://github.com/aaronparker/FSLogix/tree/master/Profile-Cleanup).

### Usage

To enable the script to report on what would be removed from user's profile, the following example command would be run in the user's context:

```powershell
.\Remove-ProfileData.ps1 -Targets .\targets.xml -WhatIf
```

To enable the script to clean up the user's profile, the following example command would be run:

```powershell
.\Remove-ProfileData.ps1 -Targets .\targets.xml -Confirm:$False
```

![Output from Remove-ProfileData.png](https://raw.githubusercontent.com/aaronparker/docs/master/images/ProfileDataOutput.png "Output from Remove-ProfileData.png")

The age of files specified in the XML can be overridden with the `-Override` switch. This will remove files of any ages as specificed in the XML targets file.

```powershell
.\Remove-ProfileData.ps1 -Targets .\targets.xml -Confirm:$False -Override
```

### Running Remove-ProfileData.ps1

`Remove-ProfileData.ps1` is be run in the user session which could be done in several ways:

* A login script - the script can be run to prune the user profile during login; however, consider potential login storms and impacts on IO and CPU
* A scheduled task - configure Windows Task Scheduler to run the script as the logged on user. Consider using task schedule trigger and condition properties to stagger the task across multiple users or desktop
* A logoff script - run the script during user logoff where applications are typically closed and user logoff actions are likely to be staggered

## About Remove-ContainerData.ps1

`Remove-ContainerData` is used to delete files and folders in a user's FSLogix Profile Container by mounting the Container and pruning files, thus keeping the Container size to a minimum. The script reads an XML file that defines a list of files and folders to remove from the Container. Actions on a target path can be:

* Prune - the XML can include a number that defines the age in days for last write that the file must be older than to be deleted. Essentially reducing the size of the folder.
* Delete - the target path will be deleted. Where the administrator may want to remove a target path, the Delete action will delete the entire folder.
* Trim - where the target path contains sub-folders, this action will remove all sub-folders except for the newest folder.

Supports `-WhatIf` and `-Verbose` output and returns a list of files removed from the profile. Add `-Verbose` will output the total size of files removed from the user profile and processing time at the end of the script. All targets (files / folders) that are deleted, will be logged to a file.

Deleting files from the Container can potentially result in data loss, so testing is advised and the use of `-Confirm:$false` is required for the script perform a delete.

This script depends on the following PowerShell modules:

* `ActiveDirectory` - Installed as a feature in Windows Server or via [RSAT](https://support.microsoft.com/en-us/help/2693643/remote-server-administration-tools-rsat-for-windows-operating-systems)
* `Hyper-V` - Installed as a feature in Windows Server or via [RSAT](https://support.microsoft.com/en-us/help/2693643/remote-server-administration-tools-rsat-for-windows-operating-systems)
* `Fslogix.Powershell.Disk` - this module is found here: [https://github.com/aaronparker/FSLogix/tree/master/Modules/Fslogix.Powershell.Disk](https://github.com/aaronparker/FSLogix/tree/master/Modules/Fslogix.Powershell.Disk)

`Remove-ContainerData.ps1` and supporting files are available on in [the repository on GitHub](https://github.com/aaronparker/FSLogix/tree/master/Profile-Cleanup).

### Usage

```powershell
.\Remove-ContainerData.ps1 -Path \\server\FSLogixContainer -Targets .\targets.xml
```

### Running Remove-ContainerData.ps1

`Remove-ContainerData.ps1` must be run outside the user session when Profile Containers are not in use. The script will require exclusive access to the Container to mount it with read/write access. `Remove-ContainerData.ps1` could be run as a schedule task outside of business hours from a management host.
