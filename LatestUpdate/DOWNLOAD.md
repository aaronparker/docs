# Download the Latest Update

`Save-LatestUpdate` is used to download the update or updates returned from `Get-LatestUpdate` and `Get-LatestFlash` to a local folder.

Often updates for multiple editions of Windows are returned by the `Get-LatestUpdate` and `Get-LatestFlash` functions; however, in each case these often be the same update. For example, `Get-LatestUpate -WindowsVersion Windows7` will return updates for Windows 7 x64 and Windows Server 2008 R2, but these updates are the same for both operating systems. Where the updates point to the same URL, `Save-LatestUpdate` will filter the updates and download them once.

## Download Implementation

On Windows `Save-LatestUpdate` uses BITS to transfer the update locally for a robust download. Where BITS is not available (i.e. on PowerShell Core), `Invoke-WebRequest` is used instead. The use of `Invoke-WebRequest` can be forced on Windows PowerShell with the `-ForceWebRequest` parameter.

## Examples

The following example, will download the latest cumulative update for the current release of Windows 10 x64:

```powershell
$Updates = Get-LatestUpdate
Save-LatestUpdate -Updates $Updates -Path "C:\Temp\Updates"
```

To download update for a specific version and architecture of Windows, modify the parameters for `Get-LatestUpdate`.

```powershell
$Updates = Get-LatestUpdate -WindowsVersion Windows8
Save-LatestUpdate -Updates $Updates -Path "C:\Temp\Updates"
```

This can be simplified to a one-line command that will get the latest update and download it to the current folder.

```powershell
Get-LatestUpdate | Save-LatestUpdate
```

To download the Cumulative update for a specific version of Windows 10 and processor architecture, the following syntax can be used:

```powershell
Get-LatestUpdate  -WindowsVersion Windows10 -Build 14393 | Where-Object { ($_.Arch -eq "x64") -and ($_.Note -like "*Windows 10*") }
```

To download the latest Adobe Flash Player update for Windows 10 1809 64-bit, use the following syntax:

```powershell
$Updates = Get-LatestFlash | Where-Object { ($_.Arch -eq "x86") -and ($_.Note -match ".*Windows 10.*1809") }
Save-LatestUpdate -Updates $Updates -Path "C:\Temp\Updates"
```
