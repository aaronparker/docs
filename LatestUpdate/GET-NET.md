# Get the Latest .NET Framework Cumulative Update

`Get-LatestNetFrameworkUpdate` retrieves the latest .NET Framework Cumulative update for Windows 10, Windows Server 2016 and Windows Server 2019 from the Microsoft Update Catalog. Run `Get-LatestNetFrameworkUpdate` to return .NET Framework Cumulative update for all supported platforms.

```powershell
PS C:\> Get-LatestNetFrameworkUpdate
```

This returns the most recent update for Windows 10 x86, x64 and ARM64 as well as Windows Server:

* Windows 10 Semi-annual Channel
* Windows 10 Long Term Servicing Channel
* Windows Server 2016
* Windows Server 2019
* Windows Server Semi-annual Channel

## Output

`Get-LatestNetFrameworkUpdate` returns the Windows 10 .NET Framework Cumulative update. This will look similar to output shown below.

```powershell
KB           : KB4495590
Note         : 2019-05 Cumulative Update for .NET Framework 3.5 and 4.7.2 for Windows 10 Version 1809 (KB4495590)
URL          : http://download.windowsupdate.com/d/msdownload/update/software/secu/2019/05/windows10.0-kb4495590-x86_5fd58f430ab750b5579d30aeaa38fcf08346c3a5.msu
Version      : 1809
Architecture : x86

KB           : KB4495590
Note         : 2019-05 Cumulative Update for .NET Framework 3.5 and 4.7.2 for Windows 10 Version 1809 for x64 (KB4495590)
URL          : http://download.windowsupdate.com/d/msdownload/update/software/secu/2019/05/windows10.0-kb4495590-x64_d746e135ff19912a8fd20a53bcc89fd20cbd3b6a.msu
Version      : 1809
Architecture : x64

KB           : KB4495618
Note         : 2019-05 Cumulative Update for .NET Framework 3.5 and 4.8 for Windows 10 Version 1809 (KB4495618)
URL          : http://download.windowsupdate.com/d/msdownload/update/software/secu/2019/05/windows10.0-kb4495618-x86_6483d6f46c3c81e24b9e0ab74ca87fea6464bfe4.msu
Version      : 1809
Architecture : x86

KB           : KB4495618
Note         : 2019-05 Cumulative Update for .NET Framework 3.5 and 4.8 for Windows 10 Version 1809 for x64 (KB4495618)
URL          : http://download.windowsupdate.com/d/msdownload/update/software/secu/2019/05/windows10.0-kb4495618-x64_2d3245836cfd2467024a907947837e7879463a3b.msu
Version      : 1809
Architecture : x64

KB           : KB4499405
Note         : 2019-05 Cumulative Update for .NET Framework 3.5, 4.7.2 and 4.8 for Windows 10 Version 1809 (KB4499405)
URL          : {http://download.windowsupdate.com/d/msdownload/update/software/secu/2019/05/windows10.0-kb4495618-x86_6483d6f46c3c81e24b9e0ab74ca87fea6464bfe4.msu, 
               http://download.windowsupdate.com/d/msdownload/update/software/secu/2019/05/windows10.0-kb4495590-x86_5fd58f430ab750b5579d30aeaa38fcf08346c3a5.msu}
Version      : 1809
Architecture : x86

KB           : KB4499405
Note         : 2019-05 Cumulative Update for .NET Framework 3.5, 4.7.2 and 4.8 for Windows 10 Version 1809 for x64 (KB4499405)
URL          : {http://download.windowsupdate.com/d/msdownload/update/software/secu/2019/05/windows10.0-kb4495618-x64_2d3245836cfd2467024a907947837e7879463a3b.msu, 
               http://download.windowsupdate.com/d/msdownload/update/software/secu/2019/05/windows10.0-kb4495590-x64_d746e135ff19912a8fd20a53bcc89fd20cbd3b6a.msu}
Version      : 1809
Architecture : x64
```

## Filtering for Windows versions

By default, updates for all Windows 10 and Windows Server versions are returned. Updates can be filtered with `Where-Object` for the `Architecture` and `Version` properties.

## Filter Output

Output from `Get-LatestNetFrameworkUpdate` can be filtered to find updates for a specific processor architecture and Windows version. For example, to filter for only the 32-bit version of Windows 10 1809, use the following syntax:

```powershell
Get-LatestNetFrameworkUpdate -Version 1809 | Where-Object { $_.Architecture -eq "x86" }
```
