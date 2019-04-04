# Import Redistributables into MDT

To install the Visual C++ Redistributables as a part of a reference image or for use with a deployment solution based on the Microsoft Deployment Toolkit, `Import-VcMdtApplication` will import each of the Visual C++ Redistributables as separate applications that includes the passive or silent command lines, platform support and the UninstallKey for detecting whether the Visual C++ Redistributable is already installed. Visual C++ Redistributables can be filtered for release and processor architecture by `Get-VcList` before passing to `Import-VcMdtApplication`.

## Examples

Import the 2008, 2010, 2012, 2013 and 2019 supported Redistributables into an MDT deployment share:

```powershell
$VcList = Get-VcList
Import-VcMdtApplication -VcList $VcList -Path C:\Temp\VcRedist -MdtPath \\server\deployment
```

Each Redistributable will be imported into the deployment share with application properties required for a successful deployment.

![Microsoft Visual C++ Redistributables applications imported into an MDT share](https://raw.githubusercontent.com/aaronparker/docs/master/images/MdtVisualCApplications.png)

The folder structure in the deployment share, will look thus:

![Visual C++ Redistributables in the deployment share Application folder](https://raw.githubusercontent.com/aaronparker/docs/master/images/MdtVisualCApplicationsFolder.PNG)

The install command line arguments used by default are passive. Fully silent install command line arguments can be specified with the `-Silent` parameter when importing the applications into an MDT deployment share.

```powershell
$VcList = Get-VcList
Import-VcMdtApp -VcList $VcList -Path C:\Temp\VcRedist -MdtPath \\server\deployment -Silent
```
