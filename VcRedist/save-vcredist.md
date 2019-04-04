# Download the Redistributables

To download the Visual C++ Redistributables to a local folder, use `Save-VcRedist`. This will read the array of Visual C++ Redistributables returned from `Get-VcList` and download each one to a local folder specified in `-Path`. Use the `-Release` or `-Architecture` parameters in `Get-VcList` to filter for specific Visual C++ Redistributables.

Save-VcRedist downloads the Redistribuables and returns the array passed from Get-VcList to the pipeline so that it can be passed to other functions `Install-VcRedist`.

## Parameters

### Required parameters

* `VcList` - An array containing details of the Visual C++ Redistributables from `Get-VcList`
* `Path` - A folder to downloaded Visual C++ Redistributables into

### Optional parameters

* `ForceWebRequest` - Forces the use of Invoke-WebRequest over Start-BitsTransfer. Useful for when running Server Core 

## Examples

To download the default list of Redistributables to `C:\Temp\VcRedist`, use the following command:

```powershell
New-Item C:\Temp\VcRedist -ItemType Directory
Get-VcList | Save-VcRedist -Path C:\Temp\VcRedist
```

Redistribuables are downloaded into the target folder:

![Microsoft Visual C++ Redistributables installed on the local PC](https://raw.githubusercontent.com/aaronparker/docs/master/images/VcRedist-Folder.PNG)
