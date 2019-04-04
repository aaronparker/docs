# List of Redistributables

The table below lists the Visual C++ Redistributables includes in the manifest. This list can be exported to CSV format from `Get-VcList` using the following command:

```powershell
Get-VcList -Export All | Select Name, Version, Release, Architecture, ProductCode | Sort Release | Export-Csv -Path C:\Temp\VcRedists.csv
```

| Name                                                                       | Version        | Release | Architecture | ProductCode                          | 
|------------------------------------------------------------------------------|------------------|-----------|----------------|----------------------------------------| 
| Visual C++ 2005 SP1 Redistributable Package                                | 8.0.56336      | 2005    | x86          | 7299052b-02a4-4627-81f2-1818da5d550d | 
| Visual C++ 2005 Redistributable Package                                    | 8.0.50727.42   | 2005    | x86          | A49F249F-0C91-497F-86DF-B2585E8E76B7 | 
| Visual C++ 2005 Redistributable Package                                    | 8.0.50727.42   | 2005    | x64          | 6E8E85E8-CE4B-4FF5-91F7-04999C9FAE6A | 
| Visual C++ 2005 Service Pack 1 Redistributable Package ATL Security Update | 8.0.59192      | 2005    | x86          | 837b34e3-7c30-493c-8f6a-2b0f04e2912c | 
| Visual C++ 2005 Service Pack 1 Redistributable Package MFC Security Update | 8.0.61000      | 2005    | x86          | 710f4c1c-cc18-4c49-8cbf-51240c89a1a2 | 
| Visual C++ 2005 Service Pack 1 Redistributable Package ATL Security Update | 8.0.59192      | 2005    | x64          | 6ce5bae9-d3ca-4b99-891a-1dc6c118a5fc | 
| Visual C++ 2005 Service Pack 1 Redistributable Package MFC Security Update | 8.0.61000      | 2005    | x64          | ad8a2fa1-06e7-4b0d-927d-6e54b3d31028 | 
| Visual C++ 2005 SP1 Redistributable Package                                | 8.0.56336      | 2005    | x64          | 071c9b48-7c32-4621-a0ac-3f809523288f | 
| Visual C++ 2008 SP1 Redistributable Package                                | 9.0.30729      | 2008    | x86          | 9A25302D-30C0-39D9-BD6F-21E6EC160475 | 
| Visual C++ 2008 Redistributable Package ATL Security Update                | 9.0.30411      | 2008    | x86          | 5DA8F6CD-C70E-39D8-8430-3D9808D6BD17 | 
| Visual C++ 2008 Redistributable Package ATL Security Update                | 9.0.30411      | 2008    | x64          | D93AC9C8-B6CF-391E-BD2F-48AF4727476C | 
| Visual C++ 2008 Service Pack 1 Redistributable Package ATL Security Update | 9.0.30729.4148 | 2008    | x86          | 1F1C2DFC-2D24-3E06-BCB8-725134ADF989 | 
| Visual C++ 2008 Feature Pack Redistributable Package                       | 9.0.21022.218  | 2008    | x86          | 5DA8F6CD-C70E-39D8-8430-3D9808D6BD17 | 
| Visual C++ 2008 Service Pack 1 Redistributable Package ATL Security Update | 9.0.30729.4148 | 2008    | x64          | 4B6C7001-C7D6-3710-913E-5BC23FCE91E6 | 
| Visual C++ 2008 SP1 Redistributable Package                                | 9.0.30729      | 2008    | x64          | 8220EEFE-38CD-377E-8595-13398D740ACE | 
| Visual C++ 2008 Feature Pack Redistributable Package                       | 9.0.21022.218  | 2008    | x64          | D93AC9C8-B6CF-391E-BD2F-48AF4727476C | 
| Visual C++ 2008 Redistributable Package                                    | 9.0.21022      | 2008    | x86          | FF66E9F6-83E7-3A3E-AF14-8DE9A809A6A4 | 
| Visual C++ 2008 Redistributable Package                                    | 9.0.21022      | 2008    | x64          | 350AA351-21FA-3270-8B7A-835434E766AD | 
| Visual C++ 2008 Service Pack 1 Redistributable Package MFC Security Update | 9.0.30729.6161 | 2008    | x86          | 9BE518E6-ECC6-35A9-88E4-87755C07200F | 
| Visual C++ 2008 Service Pack 1 Redistributable Package MFC Security Update | 9.0.30729.6161 | 2008    | x64          | 5FCE6D76-F5DC-37AB-B2B8-22AB8CEDB1D4 | 
| Visual C++ 2010 Service Pack 1 Redistributable Package MFC Security Update | 10.0.40219.325 | 2010    | x86          | F0C3E5D1-1ADE-321E-8167-68EF0DE699A5 | 
| Visual C++ 2010 Service Pack 1 Redistributable Package MFC Security Update | 10.0.40219.325 | 2010    | x64          | 1D8E6291-B0D5-35EC-8441-6616F567A0F7 | 
| Visual C++ Redistributable for Visual Studio 2012 Update 4                 | 11.0.61030.0   | 2012    | x64          | ca67548a-5ebe-413a-b50c-4b9ceb6d66c6 | 
| Visual C++ Redistributable for Visual Studio 2012 Update 4                 | 11.0.61030.0   | 2012    | x86          | 33d1fd90-4274-48a1-9bc1-97e33d9c2d6f | 
| Visual C++ Redistributable Packages for Visual Studio 2013                 | 12.0.30501.0   | 2013    | x86          | 050d4fc8-5d48-4b8f-8972-47c82c46020f | 
| Visual C++ Redistributable Packages for Visual Studio 2013                 | 12.0.30501.0   | 2013    | x64          | 050d4fc8-5d48-4b8f-8972-47c82c46020f | 
| Visual C++ 2013 Update 5 Redistributable Package                           | 12.0.40664.0   | 2013    | x64          | 042d26ef-3dbe-4c25-95d3-4c1b11b235a7 | 
| Visual C++ 2013 Update 5 Redistributable Package                           | 12.0.40664.0   | 2013    | x86          | 9dff3540-fc85-4ed5-ac84-9e3c7fd8bece | 
| Visual C++ 2015 Redistributable Update 3                                   | 14.0.24215.1   | 2015    | x86          | e2803110-78b3-4664-a479-3611a381656a | 
| Visual C++ 2015 Redistributable Update 3                                   | 14.0.24215.1   | 2015    | x64          | d992c12e-cab2-426f-bde3-fb8c53950b0d | 
| Visual C++ Redistributable for Visual Studio 2017                          | 14.16.27027.1  | 2017    | x86          | 39e28474-b67b-4209-af1b-e9ad0a83d8ca | 
| Visual C++ Redistributable for Visual Studio 2017                          | 14.16.27027.1  | 2017    | x64          | fd9b6070-d13e-45dc-819b-41806bf45b6b | 
| Visual C++ Redistributable for Visual Studio 2019                          | 14.20.27508.1  | 2019    | x86          | 8c3f057e-d6a6-4338-ac6a-f1c795a6577b | 
| Visual C++ Redistributable for Visual Studio 2019                          | 14.20.27508.1  | 2019    | x64          | 7b178cda-9740-4701-a92a-f168d213b343 | 
