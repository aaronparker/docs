# Get the Latest Windows 10 Cumulative

`Get-LatestCumulativeUpdate` retrieves the latest Cumulative update from the Windows 10 Update History page at [https://support.microsoft.com/en-au/help/4464619](https://support.microsoft.com/en-au/help/4464619). Run `Get-LatestCumulativeUpdate` with no additional switches to return the latest update for the most recent Windows 10 build for all processor architectures.

```powershell
PS C:\> Get-LatestCumulativeUpdate
```

This returns the most recent update for Windows 10 x86, x64 and ARM64 as well as Windows Server:

* Windows 10 Semi-annual Channel
* Windows 10 Long Term Servicing Channel
* Windows Server 2016
* Windows Server 2019
* Windows Server Semi-annual Channel

## Filtering for Windows versions

By default, updates for all Windows 10 and Windows Server versions are returned.

* `-Version`: use to specific the version of Windows 10 to search for updates

The `Version` parameter accepts the Windows 10 version numbers - `1903`, `1809`, `1803`, `1709`, `1703`, `1607`.

## Examples

Return the cumulative update for Windows 10 1607 and Windows Server 2016:

```powershell
PS C:\> Get-LatestCumulativeUpdate -Version 1607
```

Return the cumulative update for latest release (Semi-Annual Channel) of Windows 10 and Windows Server:

```powershell
PS C:\> Get-LatestCumulativeUpdate
```

Return the cumulative update for latest release of Windows 10 and Windows Server 1709:

```powershell
PS C:\> Get-LatestCumulativeUpdate -Version 1709
```

## Output

`Get-LatestCumulativeUpdate` returns an array of available updates with KB article (KB), processor architecture (Architecture), update description (Note) and the URL to the update itself (URL). An example output for Windows 10 is shown below.

```powershell
KB           : KB4497935
Note         : 2019-05 Cumulative Update for Windows 10 Version 1903 for x86-based Systems (KB4497935)
URL          : http://download.windowsupdate.com/d/msdownload/update/software/updt/2019/05/windows10.0-kb4497935-x86_8cd569b78eb22e22e5cf5f32b471f170f410ff4f.msu
Version      : 1903
Architecture : x86

KB           : KB4497935
Note         : 2019-05 Cumulative Update for Windows Server, version 1903 for x64-based Systems (KB4497935)
URL          : http://download.windowsupdate.com/c/msdownload/update/software/updt/2019/05/windows10.0-kb4497935-x64_e1e15758afc9d32ca57779428d145cfba3a12e4b.msu
Version      : 1903
Architecture : x64

KB           : KB4497935
Note         : 2019-05 Cumulative Update for Windows 10 Version 1903 for ARM64-based Systems (KB4497935)
URL          : http://download.windowsupdate.com/c/msdownload/update/software/updt/2019/05/windows10.0-kb4497935-arm64_5be4eac50540b54074d4d7e58282f9c28f8472fd.msu
Version      : 1903
Architecture : ARM64

KB           : KB4497935
Note         : 2019-05 Cumulative Update for Windows 10 Version 1903 for x64-based Systems (KB4497935)
URL          : http://download.windowsupdate.com/c/msdownload/update/software/updt/2019/05/windows10.0-kb4497935-x64_e1e15758afc9d32ca57779428d145cfba3a12e4b.msu
Version      : 1903
Architecture : x64
```

## Filter Output

Output from `Get-LatestCumulativeUpdate` can be filtered to find updates for a specific processor architecture or Windows version. For example, to filter for only the 32-bit version of Windows 10, use the following syntax:

```powershell
Get-LatestCumulativeUpdate | Where-Object { $_.Architecture -eq "x86" }
```

This will return output similar to the following:

```powershell
KB           : KB4497935
Note         : 2019-05 Cumulative Update for Windows 10 Version 1903 for x86-based Systems (KB4497935)
URL          : http://download.windowsupdate.com/d/msdownload/update/software/updt/2019/05/windows10.0-kb4497935-x86_8cd569b78eb22e22e5cf5f32b471f170f410ff4f.msu
Version      : 1903
Architecture : x86
```

If this output is passed to `Save-LatestUpdate`, the update package will only be downloaded once; however, if you would still like to filter for a single x64 update, the following syntax could be used:

```powershell
Get-LatestCumulativeUpdate -Version 1809 | Where-Object { ($_.Architecture -eq "x64") | Save-LatestUpdate -Path C:\Updates
```
