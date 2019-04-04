# Known issues

* 'English - United States' is the only supported language. The module will only download the en-US versions of the Visual C++ Redistributables
* `Get-VcList` will attempt to match the VcRedist version in the manifest to the `ProductVersion` property on the downloaded file. Because Product Version on the 2005 and 2008 VcRedist installers doesn't match the installed VcRedist, the file will be re-downloaded even though the installer is the correct version
