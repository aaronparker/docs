# Get the Latest Adobe Flash Player Update

`Get-LatestAdobeFlashUpdate` retrieves the latest Adobe Flash Player updates for Windows 10, Windows 8.1 and Windows Server from the Microsoft Update Catalog. Run `Get-LatestAdobeFlashUpdate` to return Adobe Flash Player updates for all supported platforms.

```powershell
PS C:\> Get-LatestFlash
```

## Output

`Get-LatestFlash | Format-Table` returns the Adobe Flash Player updates for all supported platforms. This will look similar to output shown below.

```powershell
KB           : KB4497932
Note         : 2019-05 Security Update for Adobe Flash Player for Windows 10 Version 1809 for x86-based Systems (KB4497932)
URL          : http://download.windowsupdate.com/c/msdownload/update/software/secu/2019/05/windows10.0-kb4497932-x86_b7c26e2883470ddb6a1f212b7ec1c99150a3731d.msu
Version      : 1809
Architecture : x86

KB           : KB4497932
Note         : 2019-05 Security Update for Adobe Flash Player for Windows Server 2019 for x64-based Systems (KB4497932)
URL          : http://download.windowsupdate.com/d/msdownload/update/software/secu/2019/05/windows10.0-kb4497932-x64_99ab8e9fecca9e9b7a23a42a64d17280377a4497.msu
Version      : 2019
Architecture : x64

KB           : KB4497932
Note         : 2019-05 Security Update for Adobe Flash Player for Windows 10 Version 1809 for ARM64-based Systems (KB4497932)
URL          : http://download.windowsupdate.com/d/msdownload/update/software/secu/2019/05/windows10.0-kb4497932-arm64_2f13d8bc7680905f184964c1fb08c43197c7d2c9.msu
Version      : 1809
Architecture : ARM64

KB           : KB4497932
Note         : 2019-05 Security Update for Adobe Flash Player for Windows 10 Version 1809 for x64-based Systems (KB4497932)
URL          : http://download.windowsupdate.com/d/msdownload/update/software/secu/2019/05/windows10.0-kb4497932-x64_99ab8e9fecca9e9b7a23a42a64d17280377a4497.msu
Version      : 1809
Architecture : x64

KB           : KB4497932
Note         : 2019-05 Security Update for Adobe Flash Player for Windows 10 Version 1903 for ARM64-based Systems (KB4497932)
URL          : http://download.windowsupdate.com/d/msdownload/update/software/secu/2019/05/windows10.0-kb4497932-arm64_c099d3971740be2c38a10c008a488cda45cd27a8.msu
Version      : 1903
Architecture : ARM64

KB           : KB4497932
Note         : 2019-05 Security Update for Adobe Flash Player for Windows 10 Version 1903 for x64-based Systems (KB4497932)
URL          : http://download.windowsupdate.com/d/msdownload/update/software/secu/2019/05/windows10.0-kb4497932-x64_ee950ce8790b36d3a902dcb220b4eb6db7378614.msu
Version      : 1903
Architecture : x64

KB           : KB4497932
Note         : 2019-05 Security Update for Adobe Flash Player for Windows 10 Version 1903 for x86-based Systems (KB4497932)
URL          : http://download.windowsupdate.com/d/msdownload/update/software/secu/2019/05/windows10.0-kb4497932-x86_e556ea736383dba683f099b8adbcde4471f548fe.msu
Version      : 1903
Architecture : x86

KB           : KB4497932
Note         : 2019-05 Security Update for Adobe Flash Player for Windows Server, version 1903 for x64-based Systems (KB4497932)
URL          : http://download.windowsupdate.com/d/msdownload/update/software/secu/2019/05/windows10.0-kb4497932-x64_ee950ce8790b36d3a902dcb220b4eb6db7378614.msu
Version      : 1903
Architecture : x64

KB           : KB4497932
Note         : 2019-05 Security Update for Adobe Flash Player for Windows 10 Version 1607 for x86-based Systems (KB4497932)
URL          : http://download.windowsupdate.com/c/msdownload/update/software/secu/2019/05/windows10.0-kb4497932-x86_4643f98091119039244782e32b0804ceb222e9bb.msu
Version      : 1607
Architecture : x86

KB           : KB4497932
Note         : 2019-05 Security Update for Adobe Flash Player for Windows Server 2016 for x64-based Systems (KB4497932)
URL          : http://download.windowsupdate.com/c/msdownload/update/software/secu/2019/05/windows10.0-kb4497932-x64_4b5444586793a323028d93bd031f4db34c1fc60b.msu
Version      : 2019
Architecture : x64

KB           : KB4497932
Note         : 2019-05 Security Update for Adobe Flash Player for Windows 10 Version 1607 for x64-based Systems (KB4497932)
URL          : http://download.windowsupdate.com/c/msdownload/update/software/secu/2019/05/windows10.0-kb4497932-x64_4b5444586793a323028d93bd031f4db34c1fc60b.msu
Version      : 1607
Architecture : x64

KB           : KB4497932
Note         : 2019-05 Security Update for Adobe Flash Player for Windows 10 Version 1607 for x64-based Systems (KB4497932)
URL          : http://download.windowsupdate.com/c/msdownload/update/software/secu/2019/05/windows10.0-kb4497932-x64_4b5444586793a323028d93bd031f4db34c1fc60b.msu
Version      : 1607
Architecture : x64

KB           : KB4497932
Note         : 2019-05 Security Update for Adobe Flash Player for Windows 10 Version 1607 for x64-based Systems (KB4497932)
URL          : http://download.windowsupdate.com/c/msdownload/update/software/secu/2019/05/windows10.0-kb4497932-x64_4b5444586793a323028d93bd031f4db34c1fc60b.msu
Version      : 1607
Architecture : x64

KB           : KB4497932
Note         : 2019-05 Security Update for Adobe Flash Player for Windows Server 2012 for x64-based Systems (KB4497932)
URL          : http://download.windowsupdate.com/c/msdownload/update/software/secu/2019/05/windows8-rt-kb4497932-x64_268480e79d9a679942fe792ee205f4442a60bc67.msu
Version      : 2019
Architecture : x64

KB           : KB4497932
Note         : 2019-05 Security Update for Adobe Flash Player for Windows Server 2012 for x64-based Systems (KB4497932)
URL          : http://download.windowsupdate.com/c/msdownload/update/software/secu/2019/05/windows8-rt-kb4497932-x64_268480e79d9a679942fe792ee205f4442a60bc67.msu
Version      : 2019
Architecture : x64

KB           : KB4497932
Note         : 2019-05 Security Update for Adobe Flash Player for Windows Server 2012 for x64-based Systems (KB4497932)
URL          : http://download.windowsupdate.com/c/msdownload/update/software/secu/2019/05/windows8-rt-kb4497932-x64_268480e79d9a679942fe792ee205f4442a60bc67.msu
Version      : 2019
Architecture : x64

KB           : KB4497932
Note         : 2019-05 Security Update for Adobe Flash Player for Windows Server 2012 R2 for x64-based Systems (KB4497932)
URL          : http://download.windowsupdate.com/d/msdownload/update/software/secu/2019/05/windows8.1-kb4497932-x64_f415c68ef8dd33f49d9e087368396812b72523b0.msu
Version      : 2019
Architecture : x64

KB           : KB4497932
Note         : 2019-05 Security Update for Adobe Flash Player for Windows 10 Version 1507 for x64-based Systems (KB4497932)
URL          : http://download.windowsupdate.com/c/msdownload/update/software/secu/2019/05/windows10.0-kb4497932-x64_d0073900701b7113ff4fe381f83db95032eb1116.msu
Version      : 1507
Architecture : x64

KB           : KB4497932
Note         : 2019-05 Security Update for Adobe Flash Player for Windows 10 Version 1507 for x86-based Systems (KB4497932)
URL          : http://download.windowsupdate.com/d/msdownload/update/software/secu/2019/05/windows10.0-kb4497932-x86_dc04d2fdf0b737ee78de3be06d79c95d4f6aa00d.msu
Version      : 1507
Architecture : x86

KB           : KB4497932
Note         : 2019-05 Security Update for Adobe Flash Player for Windows 10 Version 1703 for x64-based Systems (KB4497932)
URL          : http://download.windowsupdate.com/c/msdownload/update/software/secu/2019/05/windows10.0-kb4497932-x64_fb92cf786b164082bdad88716f618c050f6b7122.msu
Version      : 1703
Architecture : x64

KB           : KB4497932
Note         : 2019-05 Security Update for Adobe Flash Player for Windows 10 Version 1703 for x86-based Systems (KB4497932)
URL          : http://download.windowsupdate.com/c/msdownload/update/software/secu/2019/05/windows10.0-kb4497932-x86_72bbe9e11b8d585bf79ac5a549575c5bdcebd50c.msu
Version      : 1703
Architecture : x86

KB           : KB4497932
Note         : 2019-05 Security Update for Adobe Flash Player for Windows 10 Version 1709 for x86-based Systems (KB4497932)
URL          : http://download.windowsupdate.com/c/msdownload/update/software/secu/2019/05/windows10.0-kb4497932-x86_a11d91881afd391e8d5b29f41be327f6954bbbba.msu
Version      : 1709
Architecture : x86

KB           : KB4497932
Note         : 2019-05 Security Update for Adobe Flash Player for Windows 10 Version 1709 for ARM64-based Systems (KB4497932)
URL          : http://download.windowsupdate.com/c/msdownload/update/software/secu/2019/05/windows10.0-kb4497932-arm64_c581a0f20ac5d26e0ed54615c83aa52aa8357bd3.msu
Version      : 1709
Architecture : ARM64

KB           : KB4497932
Note         : 2019-05 Security Update for Adobe Flash Player for Windows 10 Version 1709 for x64-based Systems (KB4497932)
URL          : http://download.windowsupdate.com/c/msdownload/update/software/secu/2019/05/windows10.0-kb4497932-x64_820939b48fa19b1191a7d530462e190cb8f9f331.msu
Version      : 1709
Architecture : x64

KB           : KB4497932
Note         : 2019-05 Security Update for Adobe Flash Player for Windows 10 Version 1803 for x64-based Systems (KB4497932)
URL          : http://download.windowsupdate.com/c/msdownload/update/software/secu/2019/05/windows10.0-kb4497932-x64_3bb277ce141a113cb897fc576b96b70ac6e2fac1.msu
Version      : 1803
Architecture : x64
```

## Filter Output

Output from `Get-LatestAdobeFlashUpdate` can be filtered to find updates for a specific processor architecture and Windows version. For example, to filter for only the 32-bit version of Windows 10 1809, use the following syntax:

```powershell
Get-LatestAdobeFlashUpdate | Where-Object { ($_.Architecture -eq "x86") -and ($_.Version -match "1809") }
```

This will return output similar to the following:

```powershell
KB           : KB4497932
Note         : 2019-05 Security Update for Adobe Flash Player for Windows 10 Version 1809 for x86-based Systems (KB4497932)
URL          : http://download.windowsupdate.com/c/msdownload/update/software/secu/2019/05/windows10.0-kb4497932-x86_b7c26e2883470ddb6a1f212b7ec1c99150a3731d.msu
Version      : 1809
Architecture : x86
```
