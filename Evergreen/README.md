# Introduction

Evergreen is a simple PowerShell module to return the latest version and download URLs for a set of common enterprise applications. The module consists of a number of simple commands to use in scripts when performing several tasks including:

* Retrieve the latest version of a particular software product when comparing against a version already installed or downloaded
* Return the URL for the latest version of a software product if you need to download it locally

All functions consist of the following:

* Get verb - the module provides functions to retrieve data only
* Vendor - the vendor / developer of the application (e.g. Adobe, Google, Microsoft)
* Product name - product names and optionally version (e.g. Reader DC, Chrome, VisualStudioCode)

## How

Evergreen uses a couple of approaches to returning the latest version of software. Instead of scraping web pages, the primary methods used are:

1. Application update APIs - by using the same approach as the application itself, Evergreen can consistently return the latest version number and download URI
2. Web APIs - often a vendor download pages will include a query when listing versions and download links. Evergreen can use the same approach

## Why

There are several community and commercial products that manage application deployment and updates already. This module isn't intended to compete against those. Instead the focus is on simple integration for PowerShell scripts to provide product version numbers and download URLs. Data will only be pulled from the vendor web site and never a third party.

## Who

This module is maintained by the following community members

* Aaron Parker, [@stealthpuppy](https://twitter.com/stealthpuppy)
* Bronson Magnan, [@CIT_Bronson](https://twitter.com/CIT_Bronson)
* Trond Eric Haarvarstein, [@xenappblog](https://twitter.com/xenappblog)

## About Versioning

The module uses a version notation that follows: YearMonth.Build. It is expected that the module will have changes on a regular basis, so the version numbering is intended to make it easy to understand when the last update was made.
