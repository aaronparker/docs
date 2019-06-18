# Profile Cleanup script

`Remove-ProfileData.ps1` is used to delete files and folders in the user profile to reduce profile size, thus keeping Profile Container sizes to a minimum. The script reads an XML file that defines a list of files and folders to remove from the profile and would be run via a scheduled task or as a logoff script.

Actions on a target path can be:

* Prune - the XML can include a number that defines the age in days for last write that the file must be older than to be deleted. Essentially reducing the size of the folder.
* Delete - the target path will be deleted. Where the administrator may want to remove a target path, the Delete action will delete the entire folder.
* Trim - where the target path contains sub-folders, this action will remove all sub-folders except for the newest folder.

Supports `-WhatIf` and `-Verbose` output and returns a list of files removed from the profile. Add `-Verbose` will output the total size of files removed from the user profile and processing time at the end of the script. All targets (files / folders) that are deleted, will be logged to a file.

Deleting files from the profile can potentially result in data loss, so testing is advised and the use of `-Confirm:$False` is required for the script perform a delete.

`Remove-ProfileData.ps1` and supporting files are available on in [the repository on GitHub](https://github.com/aaronparker/FSLogix/tree/master/Profile-Cleanup).

## Usage

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

## Warning

Caveat Emptor - this script will **DELETE** target files and folders. Be certain that the targets listed in the XML are OK to be removed. Test and test again before putting the script into production.
