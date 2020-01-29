# Change log

## v2.0.163

* Update the manifest for VcRedist 2019 version `14.23.27820.0` for Visual Studio 2019 16.3

## v2.0.161

* VcRedists imported into the MDT deployment share don't have the `Hide this application in the Deployment Wizard` option enabled
* Added `-DontHide` parameter to `Import-VcMdtApplication` to not hide applications in the MDT Deployment Wizard

## v2.0.158

* Add default path for `-Path` parameter in `Save-VcRedist` and `Install-VcRedist` to address #53 and ensure function works when parameter is not specified
* Add Begin,Process,End to fix pipeline support in `Save-VcRedist`, `Install-VcRedist`, `Import-VcConfigMgrApplication`, `Import-VcMdtApplication`, `Update-VcMdtApplication` and `Update-VcMdtBundle` and address #53 
* Add function `Uninstall-VcRedist` to manage uninstalling VcRedists
* Update Pester tests for Public functions

## v2.0.147

* Add basic proxy support to `Save-VcRedist`
* Update output for `Import-VcMdtApplication`, `New-VcMdtBundle`, `Update-VcMdtApplication`, `Update-VcMdtBundle` to export all application properties
* General code formatting and quality updates - use of full type names and cmdlet/function parameters, parameter splatting
* Update verbose output messages
* Consistent parameter declaration on Public functions
* Additional Try/Catch statements for better handling of exceptions
* Remove Begin/Process/End statements from functions that don't need to support multiple objects on the pipeline
* Move module manifest location from `/Manifest` to top level module folder and update `Get-VcList` to reflect new location
* Update AppVeyor integration and scripts layout

## v2.0.140

* Update the manifest for VcRedist `2019` version `14.21.27702.2` for Visual Studio 2019 16.1

## v2.0.138

* Fixed issue [#45 Blank Dependency entry on Apps imported from Import-VcMdtApplication](https://github.com/aaronparker/VcRedist/issues/45)
* Fixing issue when importing VcRedists into ConfigMgr [#47](https://github.com/aaronparker/VcRedist/issues/47)

## v2.0.132

* Simplify version semantics to major.minor.build
* Add VcRedist `2019` to the manifest
* Convert the manifest to JSON for easier management and simpler code
* Update function `Get-VcList` to support JSON manifest format
* Combine VcRedists into a single manifest
* Rename `Get-VcRedist` to `Save-VcRedist`
* Rename `Import-VcCmApp` to `Import-VcConfigMgrApplication`
* Rename function `Export-VcXml` to `Export-VcManifest`
* Rename `Import-VcMdtApp` to `Import-VcMdtApplication`
* Split function `Import-VcMdtApplication` into `Import-VcMdtApplication`, `Update-VcMdtApplication`, `New-VcMdtBundle`, `Update-VcMdtBundle` to simplfy code and provide more robust functions
* Update HelpUri property on each function
* Update `Get-InstalledVcRedist` to export additional properties including `Release` and `Architecture`
* Add private functions `New-MdtApplicationFolder`, `New-MdtDrive`
* Update function `Get-VcList` with `-Export` parameter for `All, Supported, Unsupported`
* Add ability to filter `Get-VcList` output with `-Release` and `-Architecture`
* Fix pipeline support for `Install-VcRedist`, `Import-VcMdtApplication` and `Import-VcConfigMgrApplication` to accept output from `Get-VcList` on the pipeline
* Remove `-Release` and `-Architecture` parameters from `Install-VcRedist`, `Import-VcMdtApplication` and `Import-VcConfigMgrApplication`. Use `Get-VcList` to filter for release and architecture instead
* Update Pester tests for public and private functions

## v1.5.2.98

* Update manifests with correct details for VcRedist 2017 `v14.16.27027.1`. v1.5.1.95 included the incorrect manifest commit.

## v1.5.1.95

* Update manifests with VcRedist 2017 `v14.16.27024.1`
* Update module to export alias `Save-VcRedist` for `Get-VcRedist`. Next major version will rename `Get-VcRedist` to `Save-VcRedist`
* Change `-VcList` to use `[PSCustomObject]` instead of `[array]` in `Import-VcCmApp` and `Import-VcMdtApp`
* Update module icon to use new Visual Studio 2019 icon

## v1.5.0.92

* Added private function `Import-MdtModule` to improve MDT module loading code
* Update `Import-VcMdtApp` for more robust error checking
* Update private function `Get-ValidPath` to avoid errors on invalid path
* Update manifest with VcRedist 2017 version `14.16.27024.1`

## v1.4.3.88

* Fix private function `Get-Bitness` to ensure only single output when using no parameters or with `-Architecture`

## v1.4.2.85

* Fixed incorrect working directory when importing VcRedists into MDT in `Import-VcMdtApp`

## v1.4.1.79

* Add private function `Invoke-Process` (by Adam Bertram)
* Update `Install-VcRedist` to use `Invoke-Process` for better `Start-Process` handling
* Fix Resolve-Path / TrimEnd in private function `Get-ValidPath`
* Fix relative path issue in `Import-VcCmApp` * closes issue \#24
* Bundle added to MDT now adds Redistributables as dependencies in order from oldest to newest
* Splatting arguments in `Install-VcRedist`, `Import-VcMdtApp`, `Import-VcCmApp`
* Code formatting updates
* Documentation updates

## v1.4.0.69

* Update manifests for latest `2017` release, version `14.15.26706.0`
* Update manifests with silent install command line arguments
* Added `-Silent` switch to `Install-VcRedist`, `Import-VcMdtApp` & `Import-VcCmApp` to support optional silent install command line arguments
* Added private function `Get-Bitness` to support determining processor architecture of current OS
* Update `Install-VcRedist` to avoid installing 64-bit Redistributables on 32-bit Windows
* Removed pipeline support for `-VcRedist` parameter in `Install-VcRedist`, `Import-VcMdtApp` & `Import-VcCmApp`. Passing output from `Get-VcList` to these commands is not working correctly. Pipeline support may be added back in a future release
* Removed `2015` Redistributables from default value for `-Release` parameter for `Install-VcRedist`, `Import-VcMdtApp` & `Import-VcCmApp` functions to avoid installing `2015` then `2017` Redistributables that are the same major release version

## v1.3.7.60

* Update manifests with `2013`, version `12.0.40664`
* Added `UninstallString` to function `Get-InstalledVcRedist` output
* `Get-VcList` will attempt to match the VcRedist version in the manifest to the `Product Version` property on an existing downloaded file. If the manifest has a higher version, the file will be re-downloaded
* Added private function `Get-FileMetadata` to support retrieving `Product Version` from downloaded file
* Update logic in `Install-VcRedist` when querying for installed VcRedists

## v1.3.6.56

* Add `Get-InstalledVcRedist`, using private function `Get-InstalledSoftware`. Closing issue \#18 with feature request for this function. `Get-InstallSoftware` function by [Adam Bertram](https://4sysops.com/archives/find-the-product-guid-of-installed-software-with-powershell/)
* Update manifests with correct ProductCodes
* Update documentation

## v1.3.5.48

* Update manifests with `2017`, version `14.14`
* Update manifests with `<Version></Version>` to enable better install logic e.g. skipping installing 2015 over 2017 \(same 14.x version\)

## v1.3.4.45

* Fix import of Redistributables with correct x86, x64 platform selection in MDT application in `Import-VcMdtApp`
* Fix import of Redistributables into a folder specified by -AppFolder where the folder already exists in `Import-VcMdtApp`

## v1.3.3.39

* Update manifests with 2017 \(14.13.26020\) release
* Update module `ReleaseNotes` property with a link to changelog [https://docs.stealthpuppy.com/vcredist/change-log](https://docs.stealthpuppy.com/vcredist/change-log)
* Update functions with explicit `Write-Output`

## v1.3.2.35

* Code formatting updates
* Use `Join-Path` to build folder/file paths to better work on PSCore
* Pester tests updates
* Version update to better align with feature changes

## v1.3.1.4

* Fixes to ConfigMgr application import

## v1.3.1.2

* Add `-Bundle` to `Import-VcMdtApp` to create an Application Bundle with the Redistributables as dependencies. Redistributables will be hidden so that only the Bundle is selectable in the deployment wizard
* Updating simple Pester tests and getting Appveyor integration working
* Cleanup inline help
* Generated external help with platyPS

## v1.3.1.0

* Added function `Import-VcCmApp` for importing Visual C++ Redistributables into ConfigMgr.

## v1.3.0.0

* Refactored into a PowerShell module to simplify coding and publishing to the PowerShell Gallery.