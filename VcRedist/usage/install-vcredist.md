# Install the Redistributables

To install the Visual C++ Redistributables on the local machine, use `Install-VcRedist`. This function accepts the array of Visual C++ Redistributables passed from `Get-VcList` and installs the Visual C++ Redistributables downloaded to a local path with `Save-VcRedist`.

`Install-VcRedist` supports both passive installs (default) or silent installs with the `-Silent` parameter.

## Examples

The following command will install the Visual C++ Redistributables already downloaded locally with `Save-VcRedist` to C:\Temp\VcRedist.

```powershell
$VcList = Get-VcList
Install-VcRedist -Path C:\Temp\VcRedist -VcList $VcList
```

Fully silent install command line arguments can be specified with the `-Silent` parameter when installing the Redistributables.

```powershell
Install-VcRedist -Path C:\Temp\VcRedist -VcList (Get-VcList) -Silent
```

![Microsoft Visual C++ Redistributables installed on the local PC](https://raw.githubusercontent.com/aaronparker/docs/master/images/VisualCPrograms.PNG)
