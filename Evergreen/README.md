# Introduction

Evergreen is a simple PowerShell module to return the latest version and download URLs for a set of common enterprise applications. The module consists of a number of simple commands to use in scripts when performing several tasks including:

* Retrieve the latest version of a particular application when comparing against a version already installed or downloaded
* Return the URL for the latest version of the application if you need to download it locally for installation or deployment

![leaf by The Icon Z from the Noun Project](https://raw.githubusercontent.com/aaronparker/Evergreen/master/img/EvergreenLeaf.png)

Right now all functions consist of the following:

* `Get` verb - the module provides functions to retrieve data only
* Vendor - the vendor / developer of the application (e.g. `Adobe`, `Google`, `Microsoft`, etc.)
* Product name - product names and optionally version (e.g. `AcrobatReaderDC`, `Chrome`, `VisualStudioCode`, etc.)

This may change in a future release to simplify commands where the application can be a parameter or input into Evergreen to return the details for that application.

## Why

There are several community and commercial products that manage application deployment and updates already. This module isn't intended to compete against those. In fact, they can be complementary - for example, Evergreen can be used with the [Chocolatey Automatic Package Updater Module](https://www.powershellgallery.com/packages/AU/) to find the latest version of an application and then creating and submitting a Chocolatey package.

Evergreen's focus is on simple integration for PowerShell scripts to provide product version numbers and download URLs. Ideal for use with the Microsoft Deployment Toolkit or Microsoft Endpoint Configuration Manager for operating system deployment or with [Packer](https://www.packer.io/) to create evergreen machine images in Azure or AWS.

## How

**Application version and download links are only pulled from official sources (vendor web site, GitHub, SourceForge etc.) and never a third party**.

Scraping web pages to parse text and determine version strings and download URLs can be problematic when text in the page changes or the page is out of date. Evergreen instead uses approaches that should be less prone to failure by querying an API where possible. Evergreen uses several strategies to return the latest version of software:

1. Application update APIs - by using the same approach as the application itself, Evergreen can consistently return the latest version number and download URI - e.g. Microsoft Edge, Mozilla Firefox or Microsoft OneDrive
2. Repository APIs - repo hosters including GitHub and SourceForge have APIs that can be queried to return version and download links - e.g. Atom, Notepad++ or WinMerge
3. Web page queries - often a vendor download pages will include a query when listing versions and download links. Evergreen can use the same approach - e.g. Microsoft FSLogix Apps or Zoom

## Who

This module is maintained by the following community members

* Aaron Parker, [@stealthpuppy](https://twitter.com/stealthpuppy)
* Bronson Magnan, [@CIT_Bronson](https://twitter.com/CIT_Bronson)
* Trond Eric Haarvarstein, [@xenappblog](https://twitter.com/xenappblog)

## Versioning

The module uses a version notation that follows: YearMonth.Build. It is expected that the module will have changes on a regular basis, so the version numbering is intended to make it easy to understand when the last update was made.

---
leaf by The Icon Z from the Noun Project