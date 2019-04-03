# All Redistributables

Microsoft publishes a list of supported Visual C++ Redistributables here: [The latest supported Visual C++ downloads](https://support.microsoft.com/en-gb/help/2977003/the-latest-supported-visual-c-downloads). VcRedist includes manifests for the supported Redistributables and the full list of available Redistributbles. This does include Redistributables that are no longer supported or updated, so install these Redistributables only if you have a specific requirement to install them.

By default `Get-VcList` will only export the list of supported Redistributables from the internal manifest. To export the entire list of Redistributables, use `Get-VcList -Export All`. The full list includes the following XML structure.

```markup
<?xml version="1.0" encoding="UTF-8"?>
<!-- https://support.microsoft.com/en-gb/help/2977003/the-latest-supported-visual-c-downloads -->
<Redistributables>
    <Platform Architecture="x64" Release="2005" Install="/Q" SilentInstall="/Q">
        <Redistributable>
            <Name>Visual C++ 2005 Service Pack 1 Redistributable Package MFC Security Update</Name>
            <ShortName>MFC</ShortName>
            <URL>https://www.microsoft.com/en-us/download/details.aspx?id=26347</URL>
            <ProductCode>{ad8a2fa1-06e7-4b0d-927d-6e54b3d31028}</ProductCode>
            <Version>8.0.61000</Version>
            <Download>https://download.microsoft.com/download/8/B/4/8B42259F-5D70-43F4-AC2E-4B208FD8D66A/vcredist_x64.EXE</Download>
        </Redistributable>
        <Redistributable>
            <Name>Visual C++ 2005 Service Pack 1 Redistributable Package ATL Security Update</Name>
            <ShortName>ATL</ShortName>
            <URL>https://www.microsoft.com/en-us/download/details.aspx?id=14431</URL>
            <ProductCode>{6ce5bae9-d3ca-4b99-891a-1dc6c118a5fc}</ProductCode>
            <Version>8.0.59192</Version>
            <Download>https://download.microsoft.com/download/6/B/B/6BB661D6-A8AE-4819-B79F-236472F6070C/vcredist_x64.exe</Download>
        </Redistributable>
        <Redistributable>
            <Name>Visual C++ 2005 SP1 Redistributable Package</Name>
            <ShortName>SP1</ShortName>
            <URL>https://www.microsoft.com/en-us/download/details.aspx?id=18471</URL>
            <ProductCode>{071c9b48-7c32-4621-a0ac-3f809523288f}</ProductCode>
            <Version>8.0.56336</Version>
            <Download>https://download.microsoft.com/download/d/4/1/d41aca8a-faa5-49a7-a5f2-ea0aa4587da0/vcredist_x64.exe</Download>
        </Redistributable>
        <Redistributable>
            <Name>Visual C++ 2005 Redistributable Package</Name>
            <URL>https://www.microsoft.com/en-us/download/details.aspx?id=21254</URL>
            <ShortName>RTM</ShortName>
            <ProductCode>{6E8E85E8-CE4B-4FF5-91F7-04999C9FAE6A}</ProductCode>
            <Version>8.0.50727.42</Version>
            <Download>https://download.microsoft.com/download/9/1/4/914851c6-9141-443b-bdb4-8bad3a57bea9/vcredist_x64.exe</Download>
        </Redistributable>
    </Platform>
    <Platform Architecture="x86" Release="2005" Install="/Q" SilentInstall="/Q">
        <Redistributable>
            <Name>Visual C++ 2005 Service Pack 1 Redistributable Package MFC Security Update</Name>
            <ShortName>MFC</ShortName>
            <URL>https://www.microsoft.com/en-us/download/details.aspx?id=26347</URL>
            <ProductCode>{710f4c1c-cc18-4c49-8cbf-51240c89a1a2}</ProductCode>
            <Version>8.0.61000</Version>
            <Download>https://download.microsoft.com/download/8/B/4/8B42259F-5D70-43F4-AC2E-4B208FD8D66A/vcredist_x86.EXE</Download>
        </Redistributable>
        <Redistributable>
            <Name>Visual C++ 2005 Service Pack 1 Redistributable Package ATL Security Update</Name>
            <ShortName>ATL</ShortName>
            <URL>https://www.microsoft.com/en-us/download/details.aspx?id=14431</URL>
            <ProductCode>{837b34e3-7c30-493c-8f6a-2b0f04e2912c}</ProductCode>
            <Version>8.0.59192</Version>
            <Download>https://download.microsoft.com/download/6/B/B/6BB661D6-A8AE-4819-B79F-236472F6070C/vcredist_x86.exe</Download>
        </Redistributable>
        <Redistributable>
            <Name>Visual C++ 2005 SP1 Redistributable Package</Name>
            <ShortName>SP1</ShortName>
            <URL>https://www.microsoft.com/en-us/download/details.aspx?id=5638</URL>
            <ProductCode>{7299052b-02a4-4627-81f2-1818da5d550d}</ProductCode>
            <Version>8.0.56336</Version>
            <Download>https://download.microsoft.com/download/e/1/c/e1c773de-73ba-494a-a5ba-f24906ecf088/vcredist_x86.exe</Download>
        </Redistributable>
        <Redistributable>
            <Name>Visual C++ 2005 Redistributable Package</Name>
            <ShortName>RTM</ShortName>
            <URL>https://www.microsoft.com/en-us/download/details.aspx?id=3387</URL>
            <ProductCode>{A49F249F-0C91-497F-86DF-B2585E8E76B7}</ProductCode>
            <Version>8.0.50727.42</Version>
            <Download>https://download.microsoft.com/download/d/3/4/d342efa6-3266-4157-a2ec-5174867be706/vcredist_x86.exe</Download>
        </Redistributable>
    </Platform>
    <Platform Architecture="x64" Release="2008" Install="/Q" SilentInstall="/Q">
        <Redistributable>
            <Name>Visual C++ 2008 Redistributable Package</Name>
            <ShortName>RTM</ShortName>
            <URL>https://www.microsoft.com/en-us/download/details.aspx?id=15336</URL>
            <ProductCode>{350AA351-21FA-3270-8B7A-835434E766AD}</ProductCode>
            <Version>9.0.21022</Version>
            <Download>https://download.microsoft.com/download/d/2/4/d242c3fb-da5a-4542-ad66-f9661d0a8d19/vcredist_x64.exe</Download>
        </Redistributable>
        <Redistributable>
            <Name>Visual C++ 2008 Feature Pack Redistributable Package</Name>
            <ShortName>FP</ShortName>
            <URL>https://www.microsoft.com/en-us/download/details.aspx?id=16771</URL>
            <ProductCode>{D93AC9C8-B6CF-391E-BD2F-48AF4727476C}</ProductCode>
            <Version>9.0.21022.218</Version>
            <Download>https://download.microsoft.com/download/1/9/0/190da410-d595-4342-ba2f-2422e78bc84d/vcredist_x64.exe</Download>
        </Redistributable>
        <Redistributable>
            <Name>Visual C++ 2008 Redistributable Package ATL Security Update</Name>
            <ShortName>ATL</ShortName>
            <URL>https://www.microsoft.com/en-us/download/details.aspx?id=10430</URL>
            <ProductCode>{D93AC9C8-B6CF-391E-BD2F-48AF4727476C}</ProductCode>
            <Version>9.0.30411</Version>
            <Download>https://download.microsoft.com/download/A/5/3/A53B40CA-F75C-4678-852A-3C15EA82F186/vcredist_x64.exe</Download>
        </Redistributable>
        <Redistributable>
            <Name>Visual C++ 2008 SP1 Redistributable Package</Name>
            <ShortName>SP1</ShortName>
            <URL>https://www.microsoft.com/en-us/download/details.aspx?id=2092</URL>
            <ProductCode>{8220EEFE-38CD-377E-8595-13398D740ACE}</ProductCode>
            <Version>9.0.30729</Version>
            <Download>https://download.microsoft.com/download/2/d/6/2d61c766-107b-409d-8fba-c39e61ca08e8/vcredist_x64.exe</Download>
        </Redistributable>
        <Redistributable>
            <Name>Visual C++ 2008 Service Pack 1 Redistributable Package ATL Security Update</Name>
            <ShortName>SP1ATL</ShortName>
            <URL>https://www.microsoft.com/en-us/download/details.aspx?id=11895</URL>
            <ProductCode>{4B6C7001-C7D6-3710-913E-5BC23FCE91E6}</ProductCode>
            <Version>9.0.30729.4148</Version>
            <Download>https://download.microsoft.com/download/9/7/7/977B481A-7BA6-4E30-AC40-ED51EB2028F2/vcredist_x64.exe</Download>
        </Redistributable>
        <Redistributable>
            <Name>Visual C++ 2008 Service Pack 1 Redistributable Package MFC Security Update</Name>
            <ShortName>SP1MFC</ShortName>
            <URL>https://www.microsoft.com/en-us/download/details.aspx?id=26368</URL>
            <ProductCode>{5FCE6D76-F5DC-37AB-B2B8-22AB8CEDB1D4}</ProductCode>
            <Version>9.0.30729.6161</Version>
            <Download>https://download.microsoft.com/download/5/D/8/5D8C65CB-C849-4025-8E95-C3966CAFD8AE/vcredist_x64.exe</Download>
        </Redistributable>
    </Platform>
    <Platform Architecture="x86" Release="2008" Install="/Q" SilentInstall="/Q">
        <Redistributable>
            <Name>Visual C++ 2008 Redistributable Package</Name>
            <ShortName>RTM</ShortName>
            <URL>https://www.microsoft.com/en-us/download/details.aspx?id=29</URL>
            <ProductCode>{FF66E9F6-83E7-3A3E-AF14-8DE9A809A6A4}</ProductCode>
            <Version>9.0.21022</Version>
            <Download>https://download.microsoft.com/download/1/1/1/1116b75a-9ec3-481a-a3c8-1777b5381140/vcredist_x86.exe</Download>
        </Redistributable>
        <Redistributable>
            <Name>Visual C++ 2008 Feature Pack Redistributable Package</Name>
            <ShortName>FP</ShortName>
            <URL>https://www.microsoft.com/en-us/download/details.aspx?id=10015</URL>
            <ProductCode>{5DA8F6CD-C70E-39D8-8430-3D9808D6BD17}}</ProductCode>
            <Version>9.0.21022.218</Version>
            <Download>https://download.microsoft.com/download/d/1/0/d10d210e-e0ad-4010-b547-bc5e395ef691/vcredist_x86.exe</Download>
        </Redistributable>
        <Redistributable>
            <Name>Visual C++ 2008 Redistributable Package ATL Security Update</Name>
            <ShortName>ATL</ShortName>
            <URL>https://www.microsoft.com/en-us/download/details.aspx?id=10430</URL>
            <ProductCode>{5DA8F6CD-C70E-39D8-8430-3D9808D6BD17}</ProductCode>
            <Version>9.0.30411</Version>
            <Download>https://download.microsoft.com/download/A/5/3/A53B40CA-F75C-4678-852A-3C15EA82F186/vcredist_x86.exe</Download>
        </Redistributable>
        <Redistributable>
            <Name>Visual C++ 2008 SP1 Redistributable Package</Name>
            <ShortName>SP1</ShortName>
            <URL>https://www.microsoft.com/en-us/download/details.aspx?id=5582</URL>
            <ProductCode>{9A25302D-30C0-39D9-BD6F-21E6EC160475}</ProductCode>
            <Version>9.0.30729</Version>
            <Download>https://download.microsoft.com/download/d/d/9/dd9a82d0-52ef-40db-8dab-795376989c03/vcredist_x86.exe</Download>
        </Redistributable>
        <Redistributable>
            <Name>Visual C++ 2008 Service Pack 1 Redistributable Package ATL Security Update</Name>
            <ShortName>SP1ATL</ShortName>
            <URL>https://www.microsoft.com/en-us/download/details.aspx?id=11895</URL>
            <ProductCode>{1F1C2DFC-2D24-3E06-BCB8-725134ADF989}</ProductCode>
            <Version>9.0.30729.4148</Version>
            <Download>https://download.microsoft.com/download/9/7/7/977B481A-7BA6-4E30-AC40-ED51EB2028F2/vcredist_x86.exe</Download>
        </Redistributable>
        <Redistributable>
            <Name>Visual C++ 2008 Service Pack 1 Redistributable Package MFC Security Update</Name>
            <ShortName>SP1MFC</ShortName>
            <URL>https://www.microsoft.com/en-us/download/details.aspx?id=26368</URL>
            <ProductCode>{9BE518E6-ECC6-35A9-88E4-87755C07200F}</ProductCode>
            <Version>9.0.30729.6161</Version>
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
    <Platform Architecture="x64" Release="2012" Install="/install /passive /norestart" SilentInstall="/install /quiet /norestart">
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
            <Name>Visual C++ Redistributable Packages for Visual Studio 2013</Name>
            <ShortName>RTM</ShortName>
            <URL>https://www.microsoft.com/en-us/download/details.aspx?id=40784</URL>
            <ProductCode>{050d4fc8-5d48-4b8f-8972-47c82c46020f}</ProductCode>
            <Version>12.0.30501.0</Version>
            <Download>https://download.microsoft.com/download/2/E/6/2E61CFA4-993B-4DD4-91DA-3737CD5CD6E3/vcredist_x64.exe</Download>
        </Redistributable>
        <Redistributable>
            <Name>Update for Visual C++ 2013 and Visual C++ Redistributable Package</Name>
            <ShortName>Update</ShortName>
            <URL>https://support.microsoft.com/en-us/help/3179560/update-for-visual-c-2013-and-visual-c-redistributable-package</URL>
            <ProductCode>{ef6b00ec-13e1-4c25-9064-b2f383cb8412}</ProductCode>
            <Version>12.0.40660.0</Version>
            <Download>https://download.microsoft.com/download/0/5/6/056dcda9-d667-4e27-8001-8a0c6971d6b1/vcredist_x64.exe</Download>
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
