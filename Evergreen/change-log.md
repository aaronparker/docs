# Change Log

## 2012.242

* Adds `Get-AdobeAcrobatProDC`, `Get-TelerikFiddlerEverywhere`, `Get-1Password`
* Adds Windows Installer downloads ouput to `Get-FoxitReader`
* Updates `Get-MicrosoftSsms` to query an evergreen update URL to gather new versions from the product releases feed
  * NOTE: the version of SSMS in the releases feed is not the actual current release version - we can only work with what the feed returns
  * See #82
* Updates `Get-MicrosoftSsms` to output all supported languages for downloads - filter output on the `Language` property
* Updates `Get-MozillaFirefox` to return both Exe and Msi versions of the Firefox installer
* Adds SHA256 hash property to output from `Get-MicrosoftVisualStudioCode`
* Fixes an issue with the `URI` output in `Get-Cyberduck` that was returning an additional `/` character
* Refactors private function to query the GitHub releases API (`Get-GitHubRepoRelease`, replacing `ConvertFrom-GitHubReleasesJson`) to use `Invoke-RestMethod` for simpler public functions used to return GitHub releases
* Updates the following functions to use `Get-GitHubRepoRelease` - `Get-Atom`, `Get-AdoptOpenJdk`, `Get-BISF`, `Get-dnGrep`, `Get-GitForWindows`, `Get-GitHubRelease`, `Get-Greenshot`, `Get-Handbrake`, `Get-MicrosoftPowerShellCore`, `Get-MicrosoftPowerToys`, `Get-mRemoteNG`, `Get-NotepadPlusPlus`, `Get-OpenJDK`, `Get-OpenShellMenu`, `Get-ShareX`, `Get-Win32OpenSSH`, `Get-WixToolSet`
* Updates manifest for a number of functions to better align with an updated standard structure (see `Manifests/Template.json`)
* Updates private function `ConvertTo-DateTime` to better handle date/time format conversion. Still some improvements to be made here
* BREAKING CHANGES:
  * Updates `Get-OpenJDK` to return only Msi releases and removes Debug, zip etc. On-going improvements - see #76
  * Removes Beta and Snapshots releases from `Get-Cyberduck`
  * Removes Debug releases from `Get-Greenshot`
  * Removes SafeMode releases from `Get-Handbrake`
  * Removes Beta channel and ARM64 releases from `Get-MicrosoftEdge`
  * Removes Zip format releases from `Get-MicrosoftPowerShellCore`
  * Removes Symbols releases from `Get-Win32OpenSSH`

## 2012.225

* Adds `Get-Microsoft.NET` (.NET 5.0 and .NET Core), `Get-Win32OpenSSH`, `Get-MicrosoftPowerToys`
* Updates `Get-OpenJDK` to return all releases. Further filtering will be added in the future per #76
* Updates `Get-MozillaFirefox` to resolve download URIs for both EXE and MSI Firefox installers and updates output with additional properties (`Architecture`, `Channel` and `Type`) #83.
  * Note: this introduces a breaking change - the `-Platform` switch has been removed, you will need to filter the output on the `Architecture` property
* Updates `Get-AdobeAcrobatReader` to return additional languages #84. Note that Reader DC does not provide the latest version for all languages - it may be a better approach to use the [MUI version of the Reader installer](https://helpx.adobe.com/au/reader/faq.html#Enterprisedeployment) if your language is supported

## 2010.219

* Update `Get-FileZilla` to fix invalid download URI returned from the FileZilla update feed. Fix #75
* Update `Get-Cyberduck` to remove code that replaces `//` with `/`. Returns unfiltered URL from Cyberduck update feed. Fix #75

## 2009.218

* Fix `Get-FoxitReader` with changes to download page in `FoxitReader.json`. Address #72
* Fix `Get-Zoom` with changes to resolved URIs. Address #73
* Update `MicrosoftWvdRtcService.json` to new version of the Microsoft Remote Desktop WebRTC Redirector Service
* Update `Resolve-Uri` with additional verbose output

## 2006.212

* Renames `Get-CitrixXenServerTools` to `Get-CitrixVMTools` and adds `Get-CitrixXenServerTools` alias
* Updates `Get-CitrixVMTools` with new release URL for v7 updates and add v9 updates
* Updates install command lines for `Get-CitrixVMTools`
* Adds `Get-AdoptOpenJDK` - closes #69

## 2006.207

* Fix path in downloads from apps hosted on Source Forge returned in `ConvertFrom-SourceForgeReleasesJson.ps1`. Fixes #67
* Update `Get-MozillaFirefox` to return Extended Support Release as well as Current Release. Address #61
* Update manifests to address #57 #54 #53 #52

## 2006.203

* Removes Size property from `Get-FoxitReader` because this isn't being gathered consistently for each download
* Updates version / releases feed for `Get-MicrosftSsms` to ensure the current version is returned
* Updates the way private function `ConvertFrom-SourceForgeReleasesJson` returns available downloads from SourceForge
* Updates `Get-7zip`, `Get-KeePass`, `Get-PDFForgePDFCreator` and `Get-WinMerge` to support new approach to retrieving SourceForge downloads

## 2005.190

* Adds `Get-MicrosoftWvdBootLoader` - Get the filename and download URL for the Microsoft Windows Virtual Desktop Remote Desktop Boot Loader
* Updates `Get-FoxitReader` to sort release versions correctly and return latest (v10.x)

## 2005.187

* Adds `Get-MicrosoftWvdRtcService` - returns the version, filename and download for the Microsoft Remote Desktop WebRTC Redirector service for Windows Virtual Desktop

## 2005.183

* Updates `Get-VMwareTools` to return the very latest version with updated download URL
* Adds `Get-WixToolset`

## 2005.176

* Fixes an issue where `Get-MicrosoftEdge` was only returning ARM64 downloads
* Updates `Get-MicrosoftEdge` to only return downloads for the Enterprise ring (removed Consumer ring)
* Fixes an issue with `Get-MicrosoftTeams` where it was returning an incorrect download URL

## 2005.172

* Updates `Get-MicrosoftEdge` to correctly return the latest version and policy files for the Enterprise ring
* Updates output for private function `Resolve-Uri` with addition properties
* Updates `Get-FoxitReader`, `Get-MicrosoftFSLogixApps`, and `Get-MicrosoftSsms` to use `Resolve-Uri` instead of `Resolve-RedirectedUri` for improved performance
* Updates `Get-LibreOffice` to retrieve latest version from the update API instead of page scraping
* Updates private function `ConvertTo-DateTime` with improvements in returning localised date (so the rest of us don't need to be stuck with US date formats)
* Aligns `Get-NotepadPlusPlus` with private function `ConvertFrom-GitHubReleasesJson` to return GitHub release data
* Fixes output in `Get-VMwareTools` to ensure correct version and download URL are returned
* Adds date to output in several functions
* General code and inline help improvements
* Adds module icon for display in the PowerShell Gallery

## 2004.161

* Updates `Get-MicrosoftEdge` with the following:
  * Returns Edge for Windows only
  * Removes `-Channels` and `-Platforms` parameters. Filter output with `Where-Object` instead
  * Returns these channels and downloads only `Stable`, `Beta`, `EdgeUpdate`, and `Policy` (administrative templates)
  * Filters and returns only the latest version of each of the above channels and downloads
  * Output includes `Channel` (Stable, Beta etc.) and `Release` (Enterprise, Consumer) to enable filtering

## 2004.157

* Adds `Get-MicrosoftWvdInfraAgent`
* Adds `Get-dnGrep`
* Recode of `Get-PaintDotNet` (or how did I not know about `ConvertFrom-StringData` before?)
* To simplify output, removes Linux, macOS output from `Get-CitrixWorkspaceApp`, `Get-GoogleChrome`, `Get-OracleVirtuaBox`, `Get-LibreOffice`, `Get-MicrosoftVisualStudioCode`, `Get-MozillaFirefox`, `Get-OracleVirtualBox`, `Get-TeamViewer`
* Updates RegEx method to extract version across various functions to simplify code
* Splits Pester tests for Public functions to allow for faster local testing

## 2004.147

* Adds `Get-Handbrake`, `Get-KeePass`, `Get-OpenShellMenu`, `Get-VastLimitsUberAgent`, `Get-WinSCP`
* Removes macOS and Linux output from `Get-AdobeAcrobatReader`, `Get-LibreOffice`
* Filters macOS and Linux output from private function `ConvertFrom-GitHubReleasesJson.ps1`
* Fixes spaces in private function `ConvertFrom-SourceForgeReleasesJson`

## 2004.141

* Adds private function `ConvertFrom-SourceForgeReleasesJson` to convert JSON release info from SourceForge projects and simplify adding additional functions that pull release info from SourceForge projects. Release information is limited by what's provided from SourceForge
* Updates `Get-WinMerge` to use `ConvertFrom-SourceForgeReleasesJson`
* Adds `Get-7Zip`, `Get-PDFForgePDFCreator`
* Renames `-TrustCertificate` parameter in private function `Invoke-WebContent` to `-SkipCertificateCheck` to align with `-SkipCertificateCheck` available in '`Invoke-WebRequest` in PowerShell Core
* Enables `-SkipCertificateCheck` for both PowerShell Core and Windows PowerShell in `Invoke-WebContent`. Previously supported Windows PowerShell only
* Improves code in `Invoke-WebContent`
* Adds `-Uri` parameter validation in `Get-GitHubRelease` to ensure valid GitHub URLs are passed to the function
* Sets function global `ErrorPreference` to `Stop` to ensure better exception output from functions in the event of failures

## 2004.139

* Adds `ConvertFrom-GitHubReleasesJson` to standardise queries to GitHub repositories
* Updates `Get-Atom`, `Get-BISF`, `Get-GitForWindows`, `Get-Greenshot`, `Get-MicrosoftPowerShellCore`, `Get-OpenJDK`, `Get-ShareX`, `Get-mRemoteNG` to use `ConvertFrom-GitHubReleasesJson`
* Updates RegEx for version matching strings for `BISF`, `GitForWindows`, `ShareX`
* Adds `Get-Architecture` and `Get-Platform` private functions
* Adds `Get-GitHubRelease` to enable returning version and downloads from any GitHub repository. Use to get versions of applications on GitHub that aren't yet included in `Evergreen`

## 2004.134

* Fixes an issue where `Get-Zoom` was still returning a URI to downloads with query strings attached.

## 2004.133

* Updates URL to current version for `TeamViewer`. New URL requires different approach to query
* Adds `Invoke-SystemNetRequest` that uses `System.Net.WebRequest` to make a HTTP request and return response
* Updates `Get-TeamViewer` to use `Invoke-SystemNetRequest` to retrieve version from updated URL. Updates code to return version and download URL as a result
* Updates `Get-Zoom` to use `Resolve-Uri` to follow download URLs and find version number. `Get-Zoom` now returns more versions numbers for Zoom downloads than previously. Updates RegEx approach that returns version numbers from download URLs

## 2004.126

* Adds back `Get-FileZilla` using the application update API. Currently returns only the 64-bit version of FileZilla for Windows.

## 2004.125

* Adds `Get-MicrosoftOneDrive`. We recommend validating versions returned by this function with [OneDrive release notes](https://support.office.com/en-us/article/onedrive-release-notes-845dcf18-f921-435e-bf28-4e24b95e5fc0)
* Removes `Get-FileZilla` until a more robust process to return versions and download can be created
* Removes progress bar for `Invoke-WebRequest` for faster query of APIs
* Updates `Get-NotepadPlusPlus` to use the GitHub releases API to find new versions as the application update API can be out of date

## 2002.120

* Updates `Get-GitForWindows` to return correct version number
* Updates `Get-Zoom` to return version number correctly
* Adds `Resolve-Uri` with a new method of returning redirects from 301/302 via @iainbrighton

## 2001.117

* Updates `Get-FileZilla` to return 32-bit and 64-bit download URIs

## 2001.110

* Adds `Get-MicrosoftTeams`
* Update error handling in `Get-VideoLanVlcPlayer`

## 2001.104

* Adds `Get-MicrosoftEdge` for the new Chromium based Microsoft Edge
* Additional verbose output in `Invoke-WebContent`

## 1911.101

* Adds `Get-ScooterBeyondCompare`
* Updates XML parsing approach in `Get-CitrixRssFeed`, `Get-CitrixWorkspaceApp`, `Get-NotepadPlusPlus`, `Get-VideoLanVlcPlayer`

## 1911.97

* Adds private function `Resolve-RedirectedUri` to handle resolving 301/302 redirects on PowerShell Core and Windows PowerShell
* Updates `Get-VideoLanVlcPlayer`, `Get-MicrosoftSsms`, `Get-FoxitReader`, `Get-MicrosoftFSLogixApps`, `Get-Zoom` with full support for PowerShell Core
* Updates logic to filter out prerelease assets in `Get-Atom`, `Get-BISF`, `Get-GitForWindows`, `Get-Greenshot`, `Get-MicrosoftPowerShellCore`, `Get-OpenJDK`, `Get-ShareX`, `Get-mRemoteNG`
* Prevents `Get-MicrosoftSsms`, `Get-CitrixRssFeed`, `Get-Cyberduck`, `Get-OracleJava8` from throwing on error
* Updates to application manifests with some work on silent install commands

## 1911.95

* Adds `Get-MicrosoftFSLogixApps`

## 1911.93

* Fixes version match in `Get-ControlUpAgent`

## 1911.91

* Adds `Get-Cyberduck`

## 1911.87

* Adds `Get-JamTreeSizeFree` and `Get-JamTreeSizeProfessional`
* Fixes URL to [Release notes / CHANGELOG](https://github.com/aaronparker/Evergreen/blob/master/CHANGELOG.md) in module manifest

## 1911.84

* Changes approach used in `Get-ControlUpAgent` to retrieve agent details and enables PowerShell Core support
* Implemented per-application manifests (URLs, RegEx, strings etc.) for simpler function management
* Adds `Export-EvergreenFunctionStrings` to export per-application manifests
* Renames function `Get-Java8` to `Get-OracleJava8`
* Adds Pester tests for Public functions to ensure URI properties are valid

## 1911.75

* Updates `Get-LibreOffice` update query approach to provide a more consistent output
* Updates `Get-LibreOffice` to work on PowerShell Core
* Changes `Get-LibreOffice` output and parameters to align with other functions
* Updates `Get-NotepadPlusPlus` to gracefully handle update server issues (CloudFlare DDOS challenges)
* Fixes version output in `Get-OpenJDK`
* Updates `Get-mRemoteNG` with handling issues when getting Updates
* Updates to Public function Pester tests
* Updates `Evergreen.json` with consistent property naming and corresponding functions

## 1910.62

* Updates `Get-MicrosoftSsms` to ensure that the URI property returns the correct SSMS download for the latest version

## 1910.53

* Adds `Get-WinMerge`

## 1910.50

* Updates `Get-VideoLanVlcPlayer` output to include ZIP and MSI links for VLC Player for Windows

## 1910.49

* Updates `Get-MicrosoftSsms` to URL (e.g. `https://go.microsoft.com/fwlink/?LinkId=761491`) to return actual URI

## 1910.48

* Updates `Get-VideoLanVlcPlayer` to return download mirrors for URI values

## 1910.47

* Adds `Get-Atom` and `Get-TeamViewer`

## 1910.39

* Update `Get-Zoom` to the same HTTP post as `https://zoom.us/support/download` to return the download URI. Returns download for Windows and VDI environments
* Build script changes

## 1910.28

* Adds `Get-mRemoteNG`
* Update version format to `YearMonth.Build` (hopefully we won't change this again)
* Automate versioning in the module to the new format
* Automate update of `appveyor.yml` as `YearMonth` changes
* Output variables in AppVeyor to `\tests\appveyor.md`

## 1910.18.26

* Adds `Get-OpenJDK`
* Changes version notation to: YearMonth.Day.Build

## 19.10.25

* Adds `Get-MicrosoftOffice`

## 19.10.24

* Fixes URIs for updates in `Get-AdobeAcrobatReaderDC`
* Adds additional Pester tests for Public functions to ensure generated URI values are valid

## 19.10.21

* Adds `Get-FoxitReader`

## 19.10.20

* Fixes output in `Get-GitForWindows`, `Get-MicrosoftSmss`

## 19.10.19

* Adds `Get-GitForWindows`, `Get-ShareX`

## 19.10.11

* Adds `Get-Java8`

## 19.10.9

* Adds `Get-BISF`
* Adds `ConvertTo-DateTime` private function to handle DateTime conversion on PowerShell Core / Windows PowerShell

## 19.10.2

* First verison pushed to the PowerShell Gallery
* Initial functions are:

`Export-EvergreenResourceStrings`
`Get-AdobeAcrobatReaderDC`
`Get-CitrixAppLayeringFeed`
`Get-CitrixApplicationDeliveryManagementFeed`
`Get-CitrixEndpointManagementFeed`
`Get-CitrixGatewayFeed`
`Get-CitrixHypervisorFeed`
`Get-CitrixLicensingFeed`
`Get-CitrixReceiverFeed`
`Get-CitrixSdwanFeed`
`Get-CitrixVirtualAppsDesktopsFeed`
`Get-CitrixWorkspaceApp`
`Get-CitrixWorkspaceAppFeed`
`Get-CitrixXenServerTools`
`Get-ControlUpAgent`
`Get-FileZilla`
`Get-GoogleChrome`
`Get-Greenshot`
`Get-LibreOffice`
`Get-MicrosoftPowerShellCore`
`Get-MicrosoftSsms`
`Get-MicrosoftVisualStudioCode`
`Get-MozillaFirefox`
`Get-NotepadPlusPlus`
`Get-OracleVirtualBox`
`Get-PaintDotNet`
`Get-VideoLanVlcPlayer`
`Get-VMwareTools`
`Get-Zoom`
