# Download the Latest Update

`Save-LatestUpdate` is used to download the update or updates returned from `Get-LatestCumulativeUpdate` and `Get-LatestAdobeFlash` to a local folder.

Often updates for multiple editions of Windows are returned by the `Get-LatestCumulativeUpdate` and `Get-LatestAdobeFlash` functions; however, in each case these can often be the same update. For example, `Get-LatestCumulativeUpdate -Version 1809` will return updates for Windows 10 x64 and Windows Server 2019, but these updates are the same for both operating systems. Where the updates point to the same URL, `Save-LatestUpdate` will filter the updates and download them once.

## Download Implementation

On Windows `Save-LatestUpdate` uses BITS to transfer the update locally for a robust download. Where BITS is not available (i.e. on PowerShell Core), `Invoke-WebRequest` is used instead. The use of `Invoke-WebRequest` can be forced on Windows PowerShell with the `-ForceWebRequest` parameter.

## Examples

The following example, will download the latest cumulative update for the current release of Windows 10 x64:

```powershell
$Updates = Get-LatestCumulativeUpdate
Save-LatestUpdate -Updates $Updates -Path "C:\Temp\Updates"
```

To download update for a specific version and architecture of Windows, modify the parameters for `Get-LatestCumulativeUpdate`.

```powershell
$Updates = Get-LatestCumulativeUpdate -Version 1809
Save-LatestUpdate -Updates $Updates -Path "C:\Temp\Updates"
```

This can be simplified to a one-line command that will get the latest update and download it to the current folder.

```powershell
Get-LatestCumulativeUpdate | Save-LatestUpdate
```
