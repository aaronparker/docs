# Change Log

## v3.0.158

* Added `-Previous` switch to `Get-LatestCumulativeUpdate`, `Get-LatestServicingStackUpdate`, `Get-LatestAdobeFlashUpdate`, and `Get-LatestMonthlyRollup` (and supporting private functions). `-Previous` specifies that the previous to the latest update should be returned so that currently offered updates from Windows Update can be returned in addition to the most recent update See [https://www.osdeploy.com/blog/microsoft-update-releases](https://www.osdeploy.com/blog/microsoft-update-releases) for more info.
* Added Pester tests for `Previous` switch

## v3.0.147

* Add `-OperatingSystem` and `-Version` to all public functions to narrow search results and improve performance
* Add `-OperatingSystem` and `-Version` support to `Get-LatestAdobeFlashUpdate` to narrow search results for each OS and Windows 10 versions so that function returns all available updates
* Add `ParameterValues` in module resource JSON to enable dynamic parameter values and removed hard-coded values in functions
* Add `Register-ArgumentCompleter` in module script to register dynamic parameter values for Get functions
* Update parameters for dynamic parameter values and validation to `Get-LatestAdobeFlashUpdate`, `Get-LatestCumulativeUpdate`, `Get-LatestMonthlyRollup`, `Get-LatestNetFrameworkUpdate`, `Get-LatestServicingStackUpdate`, `Get-LatestWindowsDefenderUpdate`
* Add `Get-ModuleResource` to module script to retrieve module resource strings once during module import rather than in each function
* Update functions to use `$script:resourceStrings` for function scope variable
* Remove `SupportsShouldProcess` from Get and Private functions where `-WhatIf` support does not make sense
* Removed `ValueFromPipeline` support on Private functions as pipeline support is not required
* Splat `Get-UpdateCatalogDownloadInfo` parameters for readability
* Add additional search string support to `Invoke-UpdateCatalogSearch` and `Invoke-UpdateCatalogSearch.ps1` to narrow search results. Some update searches may return more than 25 results which can't easily be expanded to return all required results
* Add additional exceptions to Try/Catch statements in `Get-UpdateFeed` to report correctly on potential exceptions
* Update `Get-LatestNetFrameworkUpdate` to filter .NET Framework update results on the most recent month to ensure that only relevant updates are returned
* Update `Get-LatestServicingStackUpdate` to better support Windows 8 and Windows 7
* Update how `Save-LatestUpdate` writes to the pipeline to ensure correct format for output object
* Escape "." in .NET Framework search string in module resource JSON for correct string matching
* Ensure Public functions don't attempt to send Null to the pipeline
* Add additional verbose output in Public functions
* Update in-line help in Public functions
* Update `PublicFunctions.Tests.ps1` with tests dynamically driven by module resource JSON. This ensures that the tests do not require hard coded tests and use the same strings as the module

## v3.0.131

* Modify `Save-LatestUpdate` output with KB, Note and Path properties
* Update `Save-LatestUpdate` BITS transfer progress display with update Note property
* Add `-Priority` parameter to `Save-LatestUpdate`
* Update public function tests
* Start work on outputting additional Windows version updates from various functions (e.g. NET Framework, Adobe Flash etc.) This feature will be completed in a future release

## v3.0.120

* Added `Get-LatestWindowsDefenderUpdate` to retrieve updates for the Windows Defender antimalware platform
* Additional Pester tests to support `Get-LatestWindowsDefenderUpdate`

## v3.0.119

* Fix `Version` property in `Get-LatestMonthlyUpdate` to reflect Windows 8.1/7 etc.
* Remove `-Version` parameter from `Get-LatestNetFrameworkUpdate` and `Get-LatestAdobeFlashUpdate`
* Change how we check for a successfully downloaded files in `Save-LatestUpdate`, because `Start-BitsTransfer` doesn't return HTTP codes
* Fix `Test-Path 'env:APPVEYOR_BUILD_FOLDER` in `PublicFunctions.Tests.ps1`
* Add additional Pester tests to `PublicFunctions.Tests.ps1`

## v3.0.112

A complete re-write of LatestUpdate to optimise code and ensure a more predictable response when querying the update feeds.

* Public functions are now:
	* `Get-LatestAdobeFlashUpdate`
	* `Get-LatestCumulativeUpdate`
	* `Get-LatestNetFrameworkUpdate` (new)
	* `Get-LatestServicingStackUpdate`
	* `Get-LatestMonthlyRollup` (dedicated for Windows 8/7)
	* `Save-LatestUpdate`
* External strings including feed URLs, search strings etc. are stored in an external manifest instead of embedded into the module
* Simplified parameters
* `Import-LatestUpdate` has been removed so that the function fully supports PowerShell Core. Importing an update into MDT can be easily scripted
* Addresses issues #39 #38 #36 #37 #33 #32. `Save-LatestUpdate` has proxy support to address #16. Will add proxy support to other functions in a future update

## v2.5.0.0

* Added `Get-LatestNETFramework` function to find the latest cumulative update for the .NET Framework.
* The `Get-LatestFlash` now support OS filtering.
* The `Save-LatestUpdate` function now supports the `-Force` parameter to force the download of updates, overwriting them when they already exist.
* The `Save-LatestUpdate` function now supports proxy usage with authentication credentials option when needed.
* Added `Searchstring` parameter to `Get-UpdateCatalogLink` which allows the function to be used for other searches in the catalog besides only KB article numbers

## v2.4.1.97

* Update Microsoft update feed issue handling. The Microsoft Atom/RSS feeds [https://support.microsoft.com/en-au/help/4089498](https://support.microsoft.com/en-au/help/4089498) used by this module do not consistently include the required information to find the update list. `Get-LatestUpdate`, `Get-LatestFlash` and `Get-LatestServicingStack` now exit more gracefully if the required content cannot be found and write a warning to alert of the issue.
* Add `PSPath` alias to `Get-ValidPath`
* A check is performed before running `Save-LatestUpdate` to avoid download if the tests are not running in AppVeyor. This avoids having to wait for downloads on my slow home internet when running tests.

## v2.4.0.89

* Removed support for Windows 10 1511 (build 10586) in `Get-LatestUpdate` as updates for this build are no longer available in the update feed. Support for Windows 10 1511 finished in October 2017 with the last update being made available in April 2018
* Updated `Get-LatestUpdate` to return only .MSU updates. Fixes issue #27  and #23
* Account for missing architecture and version strings in `Get-LatestFlash`
* Updated `Import-LatestUpdate` to create packages folders such as "Windows 10\1803", where the parent folder does not already exist. Fixes issue #30 
* Updated code to fix removing existing packages with -Clean in `Import-LatestUpdate`. Fixes issue #29 
* Updated LINK in comments in public functions to point to https://docs.stealthpuppy.com/latestupdate
* Fix an issue where stepping through multiple KBs was not handled correctly in `Get-LatestServicingStack`
* Add additional error checking to `Get-LatestServicingStack`
* Update private function `Get-UpdateDownloadArray` to fix download URLs returned for .MSU and .EXE updaters for Windows 7
* Update logic in private function `New-MdtPackagesFolder` to cater for multiple paths (e.g. parent\child)

## v2.3.1.81

* Fix version string for Windows Server 2016/2019, Windows Server 2008 R2, Windows 7 in `Get-UpdateDownloadArray`
* Add Pester tests for `Get-LatestUpdate -WindowsBuild Windows8` and `Get-LatestUpdate -WindowsBuild Windows7`

## v2.3.0.78

* Ensure `Get-LatestUpdate`, `Get-LatestServicingStack` & `Get-LatestFlash` return consistent output
* Sort output in `Get-LatestFlash` and `Get-LatestUpdate` on Version property
* Update `Get-UpdateDownloadArray` to add Version property to function outputs
* Add tests for Version property in all public functions

## v2.2.0.74

* Add `Get-LatestServicingStack` Public function to return Servicing Stack updates for Windows 10 versions.
* Update module description
* Add Pester tests for `Get-LatestServicingStack`

## v2.1.0.69

* Added `Get-LastestFlash` public function to return the latest Adobe Flash Player updates for Windows 10, Windows Server 2016 / 2019 etc.
* Update module version to 2.1
* Add -ForceWebRequest parameter to `Save-LatestUpdate` to enable force usage of `Invoke-WebRequest` over `Start-BitsTransfer` even on Windows PowerShell
* Update `Save-WebRequest` to use private function `Test-PSCore` to test whether module is running under PowerShell Core and to use `Invoke-WebRequest` over `Start-BitsTransfer`
* Added private functions `Get-KbUpdateArray`, `Get-RxString`, `Get-UpdateCatalogLink`, `Get-UpdateCatalogLink`, `Get-UpdateDownloadArray`, `Get-UpdateFeed` to optimise shared code across `Get-LastestFlash` and `Get-LatestUpdate` public functions.
* Update Public and Private function Pester tests

## v2.0.0.51

* Changed to use RSS Atom feed for each version of Windows. This feed is kept up to date by Microsoft (Thanks to @BladeFireLight)
* Changed process to determine latest update based on Windows 10 build minor number instead of KB number (Thanks to @BladeFireLight)
* Updated `Get-LatestUpdate` to return an array of all processor architectures. Returns KB, Architecture, Note, URL to the pipeline that can be filtered in a script
* Removed dynamic parameters -Architecture, -SearchString as these are no longer needed
* Updated `Get-LatestUpdate` to support Windows 10 1809
* Improved error handling and feed retrieval in `Get-LatestUpdate`
* Updated `Save-LatestUpdate` to support new output from `Get-LatestUpdate`
* Update Pester tests in `PublicFunctions.Tests.ps1` to support new output format in `Get-LatestUpdate`

## v1.1.0.38

* Modified `Invoke-WebRequest` calls within `Get-LatestUpdate` and `Save-LatestUpdate` to use the `UseBasicParsing` parameter, removing the reliance on Internet Explorer, and enabling the script to work in PowerShell 6

## v1.1.0.37

* Updated `Get-LatestUpdate` to support Windows 10 1803 (17134)

## v1.1.0.36

* Fix inline help examples for `Import-LatestUpdate` to address issue #11
* Update Pester tests in `PublicFunctions.Tests.ps1` to ensure successful tests for `Get-LatestUpdate` using `Should -Not -BeNullOrEmpty`

## v1.1.0.34

* Update module version
* Inline help updates
* Module description updates
* Add support for Windows 8.1 / 7 (and Windows Server 2012 R2 / 2008 R2) to `Get-LatestUpdate`
* Change parameters with `-WindowsVersion`, `-Build`, `-Architecture` in `Get-LatestUpdate` to support Windows OS changes
* Add private function New-DynamicParam to support `-WindowsVersion`, `-Build`, `-Architecture` in `Get-LatestUpdate`
* Update Pester tests

## v1.0.1.27

* Inline help updates, code style formatting
* Update module description
* Update module release notes link
* Add `Test-PSCore` for testing when environment is PowerShell Core
* Add suppression of PSUseDeclaredVarsMoreThanAssignments for PSScriptAnalyzer false positive in `Select-LatestUpdate`
* Pester tests now test `Select-LatestUpdate`
* Update `Get-LatestUpdate` and `Save-LatestUpdate` with support for PowerShell Core
* Better error handling in `Import-LatestUpdate`
* Add Pester tests for `Test-PSCore`

## v1.0.1.20

* Fix ProjectUri
* Rename `Get-ValidPath` (from `Test-UpdateParameter`)
* Simplify `Import-MdtModule` output
* Add `New-MdtDrive`
* Add `Remove-MdtDrive`
* Improve `New-MdtPackagesFolder` robustness, update output
* Update `Select-LatestUpdate` notes
* Update `Select-UniqueUrl` notes
* Update `Get-LatestUpdate` inline help
* Update `Import-LatestUpdate` inline help, parameters, new MDT drive, more robust action when creating the MDT package folder
* Fix pipeline support for `Save-LatestUpdate`
* Detailed Pester tests for Private and Public functions

## v1.0.1.11

* First v1 public release
* Published to the [PowerShell Gallery](https://www.powershellgallery.com/packages/LatestUpdate/)
