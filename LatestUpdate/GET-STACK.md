# Get the Latest Servicing Stack Update

`Get-LatestServicingStackUpdate` retrieves the latest Servicing Stack updates for Windows 10, Windows Server 2016 and Windows Server 2019 from the Microsoft Update Catalog. Run `Get-LatestServicingStackUpdate` to return Servicing Stack updates for all supported platforms.

```powershell
PS C:\> Get-LatestServicingStackUpdate
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

## Output

`Get-LatestServicingStackUpdate` returns the Windows 10 Servicing Stack updates. This will look similar to output shown below.

```powershell
KB           : KB4498523
Note         : 2019-05 Servicing Stack Update for Windows 10 Version 1903 for x64-based Systems (KB4498523)
URL          : http://download.windowsupdate.com/d/msdownload/update/software/secu/2019/05/windows10.0-kb4498523-x64_a0ff434be44cddb3c4e6c9e3a9a8d150e3ddc5fa.msu
Version      : 1903
Architecture : x64

KB           : KB4498523
Note         : 2019-05 Servicing Stack Update for Windows 10 Version 1903 for x86-based Systems (KB4498523)
URL          : http://download.windowsupdate.com/d/msdownload/update/software/secu/2019/05/windows10.0-kb4498523-x86_ef839686aee13279ed4e3656150eed43d525949c.msu
Version      : 1903
Architecture : x86

KB           : KB4498523
Note         : 2019-05 Servicing Stack Update for Windows Server, version 1903 for x64-based Systems (KB4498523)
URL          : http://download.windowsupdate.com/d/msdownload/update/software/secu/2019/05/windows10.0-kb4498523-x64_a0ff434be44cddb3c4e6c9e3a9a8d150e3ddc5fa.msu
Version      : 1903
Architecture : x64

KB           : KB4498523
Note         : 2019-05 Servicing Stack Update for Windows 10 Version 1903 for ARM64-based Systems (KB4498523)
URL          : http://download.windowsupdate.com/d/msdownload/update/software/secu/2019/05/windows10.0-kb4498523-arm64_4fdda790397f0e8cc11f096e7722346650e92731.msu
Version      : 1903
Architecture : ARM64
```

## Filter Output

Output from `Get-LatestServicingStackUpdate` can be filtered to find updates for a specific processor architecture and Windows version. For example, to filter for only the 32-bit version of Windows 10 1809, use the following syntax:

```powershell
Get-LatestServicingStackUpdate -Version 1809 | Where-Object { $_.Architecture -eq "x86" }
```

This will return output similar to the following:

```powershell
KB           : KB4499728
Note         : 2019-05 Servicing Stack Update for Windows 10 Version 1809 for x86-based Systems (KB4499728)
URL          : http://download.windowsupdate.com/d/msdownload/update/software/secu/2019/05/windows10.0-kb4499728-x86_999cd7a0d2565ce3769afa361c0362e755231108.msu
Version      : 1809
Architecture : x86
```
