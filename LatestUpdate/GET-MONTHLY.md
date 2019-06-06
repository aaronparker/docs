# Get Windows 8.1/7 Monthly Rollup Updates

`Get-LatestMonthlyRollup` retrieves the latest Monthly Rollup updates for Windows 8.1 and 7 from the Microsoft Update Catalog. This function returns the most recent update for legacy Windows versions:

* Windows 8.1
* Windows Server 2012 R2
* Windows 7
* Windows Server 2008 R2

## Output

`Get-LatestMonthlyRollup` returns the latest Windows 8.1 / Windows Server 2012 R2 Monthly Rollup Updates. This will look similar to output shown below.

```powershell
KB           : KB4499151
Note         : 2019-05 Security Monthly Quality Rollup for Windows 8.1 for x64-based Systems (KB4499151)
URL          : http://download.windowsupdate.com/d/msdownload/update/software/secu/2019/05/windows8.1-kb4499151-x64_254432cdd26527f8661cfd58c6f5edec00cdd93f.msu
Version      : 2019
Architecture : x64

KB           : KB4499151
Note         : 2019-05 Security Monthly Quality Rollup for Windows 8.1 for x86-based Systems (KB4499151)
URL          : http://download.windowsupdate.com/d/msdownload/update/software/secu/2019/05/windows8.1-kb4499151-x86_c43de68ce02d9fe445bf9be94344d88e61a8d48f.msu
Version      : 2019
Architecture : x86

KB           : KB4499151
Note         : 2019-05 Security Monthly Quality Rollup for Windows Server 2012 R2 for x64-based Systems (KB4499151)
URL          : http://download.windowsupdate.com/d/msdownload/update/software/secu/2019/05/windows8.1-kb4499151-x64_254432cdd26527f8661cfd58c6f5edec00cdd93f.msu
Version      : 2019
Architecture : x64
```

## Filtering for Windows versions

By default, updates for all Windows 8.1 and Windows Server 2012 R2 versions are returned. Updates can be filtered with the `-Version` parameter and additional filtering with `Where-Object` on the `Architecture` property.

```powershell
Get-LatestMonthlyRollup -Version 'Windows 7' | Where-Object { $_.Architecture -eq "x86" }
```

This will return the latest update for Windows 7 x86:

```powershell
KB           : KB4499164
Note         : 2019-05 Security Monthly Quality Rollup for Windows 7 for x86-based Systems (KB4499164)
URL          : http://download.windowsupdate.com/d/msdownload/update/software/secu/2019/05/windows6.1-kb4499164-x86_0c190847e1570aa3c930187d9f55010a4f711fc4.msu
Version      : 2019
Architecture : x86
```
