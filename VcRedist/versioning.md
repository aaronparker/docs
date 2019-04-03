# Understanding VcRedist Versioning

VcRedist uses a major.minor[.maintenance[.build]] versioning scheme.

## Major release

Major releases typically introduce breaking changes. Major releases should may break scripts using the VcRedist module.

## Minor release

Minor releases add new features such as additional public functions, improve code quality or improved output. Minor releases should not break scripts using the VcRedist module.

## Build

The build number in a release tracks the number of builds performed by AppVeyor.
