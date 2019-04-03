# Supported Redistributables

Microsoft publishes a list of supported Visual C++ Redistributables here: [The latest supported Visual C++ downloads](https://support.microsoft.com/en-gb/help/2977003/the-latest-supported-visual-c-downloads). VcRedist includes manifests for the supported Redistributables and the full list of available Redistributbles.

By default Get-VcList will only export the list of supported Redistributables from the internal manifest. The supported list includes the following XML structure.

```markup
<?xml version="1.0" encoding="UTF-8"?>
<!-- https://support.microsoft.com/en-gb/help/2977003/the-latest-supported-visual-c-downloads -->
<Redistributables>
    <Platform Architecture="x64" Release="2008" Install="/Q" SilentInstall="/Q">
        <Redistributable>
            <Name>Visual C++ 2008 Service Pack 1 Redistributable Package MFC Security Update</Name>
            <ShortName>SP1MFC</ShortName>
            <URL>https://www.microsoft.com/en-us/download/details.aspx?id=26368</URL>
            <ProductCode>{5FCE6D76-F5DC-37AB-B2B8-22AB8CEDB1D4}</ProductCode>
            <Version>9.0.30729.5677</Version>
            <Download>https://download.microsoft.com/download/5/D/8/5D8C65CB-C849-4025-8E95-C3966CAFD8AE/vcredist_x64.exe</Download>
        </Redistributable>
    </Platform>
    <Platform Architecture="x86" Release="2008" Install="/Q" SilentInstall="/Q">
        <Redistributable>
            <Name>Visual C++ 2008 Service Pack 1 Redistributable Package MFC Security Update</Name>
            <ShortName>SP1MFC</ShortName>
            <URL>https://www.microsoft.com/en-us/download/details.aspx?id=26368</URL>
            <ProductCode>{9BE518E6-ECC6-35A9-88E4-87755C07200F}</ProductCode>
            <Version>9.0.30729.5677</Version>
            <Download>https://download.microsoft.com/download/5/D/8/5D8C65CB-C849-4025-8E95-C3966CAFD8AE/vcredist_x86.exe</Download>
        </Redistributable>
    </Platform>
    <Platform Architecture="x64" Release="2010" Install="/passive /norestart" SilentInstall="/quiet /norestart">
        <Redistributable>
            <Name>Visual C++ 2010 Service Pack 1 Redistributable Package MFC Security Update</Name>
            <ShortName>SP1</ShortName>
            <URL>https://www.microsoft.com/en-us/download/details.aspx?id=26999</URL>
            <ProductCode>{1D8E6291-B0D5-35EC-8441-6616F567A0F7}</ProductCode>
            <Version>10.0.40219.325</Version>
            <Download>https://download.microsoft.com/download/1/6/5/165255E7-1014-4D0A-B094-B6A430A6BFFC/vcredist_x64.exe</Download>
        </Redistributable>
    </Platform>
    <Platform Architecture="x86" Release="2010" Install="/passive /norestart" SilentInstall="/quiet /norestart">
        <Redistributable>
            <Name>Visual C++ 2010 Service Pack 1 Redistributable Package MFC Security Update</Name>
            <ShortName>SP1</ShortName>
            <URL>https://www.microsoft.com/en-us/download/details.aspx?id=26999</URL>
            <ProductCode>{F0C3E5D1-1ADE-321E-8167-68EF0DE699A5}</ProductCode>
            <Version>10.0.40219.325</Version>
            <Download>https://download.microsoft.com/download/1/6/5/165255E7-1014-4D0A-B094-B6A430A6BFFC/vcredist_x86.exe</Download>
        </Redistributable>
    </Platform>
    <Platform Architecture="x64" Release="2012" Install="/install /passive /norestart" SilentInstall="/quiet /norestart">
        <Redistributable>
            <Name>Visual C++ Redistributable for Visual Studio 2012 Update 4</Name>
            <ShortName>Update4</ShortName>
            <URL>https://www.microsoft.com/en-us/download/details.aspx?id=30679</URL>
            <ProductCode>{ca67548a-5ebe-413a-b50c-4b9ceb6d66c6}</ProductCode>
            <Version>11.0.61030.0</Version>
            <Download>https://download.microsoft.com/download/1/6/B/16B06F60-3B20-4FF2-B699-5E9B7962F9AE/VSU_4/vcredist_x64.exe</Download>
        </Redistributable>
    </Platform>
    <Platform Architecture="x86" Release="2012" Install="/install /passive /norestart" SilentInstall="/install /quiet /norestart">
        <Redistributable>
            <Name>Visual C++ Redistributable for Visual Studio 2012 Update 4</Name>
            <ShortName>Update4</ShortName>
            <URL>https://www.microsoft.com/en-us/download/details.aspx?id=30679</URL>
            <ProductCode>{33d1fd90-4274-48a1-9bc1-97e33d9c2d6f}</ProductCode>
            <Version>11.0.61030.0</Version>
            <Download>https://download.microsoft.com/download/1/6/B/16B06F60-3B20-4FF2-B699-5E9B7962F9AE/VSU_4/vcredist_x86.exe</Download>
        </Redistributable>
    </Platform>
    <Platform Architecture="x64" Release="2013" Install="/install /passive /norestart" SilentInstall="/install /quiet /norestart">
        <Redistributable>
            <Name>Visual C++ 2013 Update 5 Redistributable Package</Name>
            <ShortName>Update5</ShortName>
            <URL>https://support.microsoft.com/en-us/help/4032938/update-for-visual-c-2013-redistributable-package</URL>
            <ProductCode>{042d26ef-3dbe-4c25-95d3-4c1b11b235a7}</ProductCode>
            <Version>12.0.40664.0</Version>
            <Download>https://download.visualstudio.microsoft.com/download/pr/10912041/cee5d6bca2ddbcd039da727bf4acb48a/vcredist_x64.exe</Download>
        </Redistributable>
    </Platform>
    <Platform Architecture="x86" Release="2013" Install="/install /passive /norestart" SilentInstall="/install /quiet /norestart">
        <Redistributable>
            <Name>Visual C++ 2013 Update 5 Redistributable Package</Name>
            <ShortName>Update5</ShortName>
            <URL>https://support.microsoft.com/en-us/help/4032938/update-for-visual-c-2013-redistributable-package</URL>
            <ProductCode>{9dff3540-fc85-4ed5-ac84-9e3c7fd8bece}</ProductCode>
            <Version>12.0.40664.0</Version>
            <Download>https://download.visualstudio.microsoft.com/download/pr/10912113/5da66ddebb0ad32ebd4b922fd82e8e25/vcredist_x86.exe</Download>
        </Redistributable>
    </Platform>
    <Platform Architecture="x64" Release="2015" Install="/install /passive /norestart" SilentInstall="/install /quiet /norestart">
        <Redistributable>
            <Name>Visual C++ 2015 Redistributable Update 3</Name>
            <ShortName>Update3</ShortName>
            <URL>https://www.microsoft.com/en-us/download/details.aspx?id=53840</URL>
            <ProductCode>{d992c12e-cab2-426f-bde3-fb8c53950b0d}</ProductCode>
            <Version>14.0.24215.1</Version>
            <Download>https://download.microsoft.com/download/6/A/A/6AA4EDFF-645B-48C5-81CC-ED5963AEAD48/vc_redist.x64.exe</Download>
        </Redistributable>
    </Platform>
    <Platform Architecture="x86" Release="2015" Install="/install /passive /norestart" SilentInstall="/install /quiet /norestart">
        <Redistributable>
            <Name>Visual C++ 2015 Redistributable Update 3</Name>
            <ShortName>Update3</ShortName>
            <URL>https://www.microsoft.com/en-us/download/details.aspx?id=53840</URL>
            <ProductCode>{e2803110-78b3-4664-a479-3611a381656a}</ProductCode>
            <Version>14.0.24215.1</Version>
            <Download>https://download.microsoft.com/download/6/A/A/6AA4EDFF-645B-48C5-81CC-ED5963AEAD48/vc_redist.x86.exe</Download>
        </Redistributable>
    </Platform>
    <Platform Architecture="x64" Release="2017" Install="/install /passive /norestart" SilentInstall="/install /quiet /norestart">
        <Redistributable>
            <Name>Visual C++ Redistributable for Visual Studio 2017</Name>
            <ShortName>RTM</ShortName>
            <URL>https://www.visualstudio.com/downloads/</URL>
            <ProductCode>{95ac1cfa-f4fb-4d1b-8912-7f9d5fbb140d}</ProductCode>
            <Version>14.15.26706.0</Version>
            <Download>https://aka.ms/vs/15/release/vc_redist.x64.exe</Download>
        </Redistributable>
    </Platform>
    <Platform Architecture="x86" Release="2017" Install="/install /passive /norestart" SilentInstall="/install /quiet /norestart">
        <Redistributable>
            <Name>Visual C++ Redistributable for Visual Studio 2017</Name>
            <ShortName>RTM</ShortName>
            <URL>https://www.visualstudio.com/downloads/</URL>
            <ProductCode>{7e9fae12-5bbf-47fb-b944-09c49e75c061}</ProductCode>
            <Version>14.15.26706.0</Version>
            <Download>https://aka.ms/vs/15/release/vc_redist.x86.exe</Download>
        </Redistributable>
    </Platform>
</Redistributables>
```
