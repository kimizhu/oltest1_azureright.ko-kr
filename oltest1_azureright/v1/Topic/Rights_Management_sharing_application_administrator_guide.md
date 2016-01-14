---
description: na
keywords: na
title: Rights Management sharing application administrator guide
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: d9992e30-f3d1-48d5-aedc-4e721f7d7c25
---
# Rights Management 공유 응용 프로그램 관리자 가이드
엔터프라이즈 네트워크에서 Microsoft Rights Management 공유 응용 프로그램을 담당하고 있거나, [Rights Management 공유 응용 프로그램 사용자 가이드](../Topic/Rights_Management_sharing_application_user_guide.md) 또는 [Windows용 Microsoft Rights Management 공유 응용 프로그램 FAQ](http://go.microsoft.com/fwlink/?LinkId=303971)에 나와 있는 것보다 자세한 기술 정보를 확인하려는 경우 이 문서의 정보를 참조할 수 있습니다.

-   [Microsoft Rights Management 공유 응용 프로그램 자동 배포](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_ScriptedInstall)

    -   [설치 성공 여부 확인](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_verifyscripted)

    -   [제거 명령](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_uninstallscripted)

    -   [자동 업데이트를 사용하지 않도록 설정](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_SuppressAutomaticUpdates)

    -   [AD RMS만 해당: 문서 추적 기능 구성](#BKMK_DocumentTracking)

    -   [AD RMS만 해당: 조직 내의 여러 메일 도메인 지원](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_FederatedDomains)

-   [Microsoft Rights Management 공유 응용 프로그램 기술 개요](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_AdminOverview)

    -   [보호 수준 - 기본 및 일반](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_LevelsofProtection)

    -   [지원되는 파일 형식 및 파일 이름 확장명](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_SupportFileTypes)

    -   [파일의 기본 보호 수준 변경](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_ChangeDefaultProtection)

> [!TIP]
> RMS 공유 앱을 처음 사용하거나 자세한 정보를 확인하려는 경우에는 [RMS에서 모든 파일 형식을 보호하는 방법 – RMS 공유 앱 사용](https://curah.microsoft.com/191031/how-rms-protects-all-file-types-by-using-the-rms-sharing-app)을 참조하세요.

RMS 공유 응용 프로그램은 Azure RMS에서 가장 효율적으로 작동합니다. 이 배포 구성에서는 다른 조직의 사용자에게 보호된 첨부 파일을 보낼 수 있으며, 메일 알림 및 취소 기능이 포함된 문서 추적 등의 옵션도 지원되기 때문입니다.  그러나 온-프레미스 버전인 AD RMS에서도 해당 응용 프로그램을 사용할 수 있습니다(일부 제한이 적용됨). Azure RMS 및 AD RMS에서 지원하는 기능을 포괄적으로 비교한 내용을 확인하려면 [Azure Rights Management와 AD RMS 비교](https://technet.microsoft.com/library/jj739831.aspx)를 참조하세요. AD RMS를 사용 중이며 Azure RMS로 마이그레이션하려는 경우에는 [AD RMS에서 Azure Rights Management로 마이그레이션](https://technet.microsoft.com/library/dn858447.aspx)을 참조하세요.

## <a name="BKMK_ScriptedInstall"></a>Microsoft Rights Management 공유 응용 프로그램 자동 배포
RMS 공유 응용 프로그램의 Windows 버전은 스크립트 방식 설치를 지원하므로 엔터프라이즈 배포에 적합합니다.

설치의 필수 조건은 컴퓨터에서 Windows 7 서비스 팩 1 이상 버전을 실행해야 하며 Microsoft Framework 4.0 이상 버전이 설치되어 있어야 한다는 것뿐입니다. Microsoft .NET Framework 4.0을 설치해야 하는 경우 [Microsoft 다운로드 센터에서 설치를 위해 해당 버전을 다운로드](http://www.microsoft.com/download/details.aspx?id=17718)할 수 있습니다.

#### 자동 배포용 RMS 공유 응용 프로그램을 다운로드하려면

1.  Microsoft 다운로드 센터의 [Windows용 Microsoft Rights Management 공유 응용 프로그램](http://www.microsoft.com/download/details.aspx?id=40857) 페이지로 이동하여 **다운로드**를 클릭합니다.

2.  필요한 파일을 선택하여 다운로드합니다. Windows 64비트용(Microsoft Rights Management 공유 응용 프로그램 x64.zip) 및 Windows 32비트용(Microsoft Rights Management 공유 응용 프로그램 x86.zip)의 두 가지 클라이언트 설치 패키지가 있습니다.

3.  압축된 설치 패키지를 두 번 클릭하는 등의 방법으로 파일의 압축을 풉니다. 그런 다음 클라이언트 컴퓨터가 액세스할 수 있는 네트워크 위치에 압축을 푼 파일을 복사합니다.

RMS 공유 응용 프로그램의 설치 패키지는 다음과 같은 다양한 배포 시나리오를 지원합니다.

|설명|배포 시나리오|
|------|-----------|
|Microsoft Online 로그인 도우미|다음에 대해 필요합니다.<br /><br />-   Office 2010 및 Azure RMS<br />-   [Office 2013용 2015년 6월 9일 업데이트](https://support.microsoft.com/kb/3054853)(KB3054853)를 설치하지 않은 경우 Office 2013 및 Azure RMS|
|Office용 핫픽스(KB 2596501)|다음에 대해 필요합니다.<br /><br />-   Office 2010 및 Azure RMS<br />-   Office 2010 및 Active Directory RMS|
|AD RMS 클라이언트 1.0이 Azure RMS에서 작동하도록 설정하기 위한 핫픽스(KB 2843630)|다음에 대해 필요합니다.<br /><br />-   Office 2010 및 Azure RMS<br />-   Office 2010 및 Active Directory RMS|
|AD RMS 클라이언트 및 RMS 공유 응용 프로그램|다음에 대해 필요합니다.<br /><br />-   Office 2016 또는 Office 2013 및 Azure RMS 또는 Active Directory RMS<br />-   Office 2010 및 Azure RMS<br />-   Office 2010 및 Active Directory RMS<br />-   RMS 공유 응용 프로그램 및 Office 추가 기능만|
|리본용 Office 추가 기능|다음에 대해 필요합니다.<br /><br />-   Office 2016 또는 Office 2013 및 Azure RMS 또는 Active Directory RMS<br />-   Office 2010 및 Azure RMS<br />-   Office 2010 및 Active Directory RMS<br />-   RMS 공유 응용 프로그램 및 Office 추가 기능만|
|Azure Active Directory Rights Management 준비 도구|다음에 대해 필요합니다.<br /><br />-   Office 2010 및 Azure RMS|
이러한 배포 시나리오용으로 RMS 공유 응용 프로그램을 배포하는 데 필요한 명령을 확인하려면 다음 절차를 수행합니다.

-   **Office 2016 또는 Office 2013 및 Azure RMS 또는 Active Directory RMS**

    사용자가 Office 2016 또는 Office 2013을 실행하고 조직에서 Azure RMS 또는 Active Directory RMS를 사용하며 사용자가 Azure RMS 또는 Active Directory RMS를 사용하는 다른 조직과 공동 작업을 합니다.

-   **Office 2010 및 Azure RMS**

    사용자가 Office 2010을 실행하고 조직에서 Azure RMS를 사용하며 사용자가 Azure RMS 또는 Active Directory RMS를 사용하는 다른 조직과 공동 작업을 합니다.

-   **Office 2010 및 Active Directory RMS**

    사용자가 Office 2010을 실행하고 조직에서 AD RMS를 사용하며 사용자가 Azure RMS를 사용하는 다른 조직과 공동 작업을 합니다.

-   **RMS 공유 응용 프로그램 및 Office 추가 기능만**

    사용자가 Office 2016, Office 2013 또는 Office 2010을 실행하고 조직에서 AD RMS를 사용하며 사용자가 Azure RMS를 사용하는 다른 조직과 공동 작업을 할 필요가 없습니다. 이 설치의 경우 공유 응용 프로그램과 Office 추가 기능만 설치하면 됩니다.

> [!NOTE]
> 이러한 시나리오에서 조직이 AD RMS를 실행하는 경우 사용자는 Azure RMS를 사용하는 다른 조직으로부터 보호된 콘텐츠를 받을 수는 있지만 Azure RMS를 사용하는 조직의 사용자에게 보호된 콘텐츠를 보낼 수는 없습니다. 그러나 조직이 Azure RMS를 실행하는 경우에는 사용자가 다른 조직과 보호된 콘텐츠를 주고받을 수 있습니다.

각 절차에 대해 설치를 완료하려면 컴퓨터를 다시 시작해야 합니다. shutdown /i와 같은 명령을 사용하여 자동 다시 시작을 시작할 수 있습니다.

#### Office 2016 또는 Office 2013 및 Azure RMS 또는 Active Directory RMS용 공유 응용 프로그램을 배포하려면

-   RMS 공유 응용 프로그램 및 관련 구성 요소를 설치하려는 각 컴퓨터에서 상승된 권한으로 다음 명령을 실행합니다.

    ```
    setup.exe /s
    ```

설치 성공 여부를 확인하려면 이 항목의 [설치 성공 여부 확인](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_verifyscripted) 섹션을 참조하세요.

#### Office 2010 및 Azure RMS용 RMS 공유 응용 프로그램을 배포하려면

1.  Azure Active Directory Rights Management 준비 도구를 실행하여 조직의 인증 서비스 URL을 가져올 수 있도록 Office 365 또는 Azure Active Directory 테넌트의 전역 관리자여야 합니다. 이 도구는 단일 컴퓨터에서 한 번만 실행하면 됩니다. 각 컴퓨터에 RMS 공유 응용 프로그램을 설치할 때 인증 서비스 URL을 사용합니다.

    1.  로컬 관리자 계정을 사용하여 컴퓨터에 로그인합니다.

    2.  해당 컴퓨터에서 [Microsoft Online 로그인 도우미를 다운로드하여 설치](http://www.microsoft.com/download/details.aspx?id=28177)합니다.

    3.  다음 명령을 실행하여 화면에 표시되는 인증 서비스 URL을 확인합니다. 이 URL을 복사한 후 다음 단계에서 사용하기 위해 저장할 수 있습니다.

        -   Windows 8.1 및 Windows 8 64비트:

            ```
            x64\aadrmprep.exe /findCertificationUrl /logfile "<log file path and name>"
            ```

        -   Windows 8.1 및 Windows 8 32비트:

            ```
            X86\aadrmprep.exe /findCertificationUrl /logfile "<log file path and name>"
            ```

        -   Windows 7 64비트:

            ```
            x64\win7\aadrmprep.exe /findCertificationUrl /logfile "<log file path and name>"
            ```

        > [!NOTE]
        > 이 명령을 실행하면 Azure용 자격 증명을 입력하라는 메시지가 표시될 수 있습니다. 컴퓨터가 도메인에 가입되어 있지 않으면 이 메시지가 표시됩니다. 컴퓨터가 도메인에 가입되어 있으면 이 도구는 캐시된 자격 증명을 사용할 수 있습니다.

2.  RMS 공유 응용 프로그램을 설치할 각 컴퓨터에서 상승된 권한으로 다음 명령을 실행합니다.

    ```
    setup.exe /s /configureO2010Admin /certificationUrl <certification_url>
    ```

3.  RMS 공유 응용 프로그램을 설치할 각 컴퓨터에서 다음 명령을 실행해야 합니다(상승된 권한은 필요하지 않음). 여러 가지 방법으로 이 작업을 수행할 수 있습니다. 예를 들어 메일 메시지나 지원 센터 포털의 링크를 통해 사용자가 명령을 실행하도록 할 수도 있고 로그온 스크립트에 명령을 추가할 수도 있습니다.

    ```
    bin\RMSSetup.exe /configureO2010Only
    ```

설치 성공 여부를 확인하려면 이 항목의 [설치 성공 여부 확인](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_verifyscripted) 섹션을 참조하세요.

#### Office 2010 및 Active Directory RMS용 RMS 공유 응용 프로그램을 배포하려면

1.  RMS 공유 응용 프로그램을 설치할 각 컴퓨터에서 상승된 권한으로 다음 명령을 실행합니다.

    ```
    setup.exe /s /configureO2010Admin
    ```

2.  RMS 공유 응용 프로그램을 설치할 각 컴퓨터에서 다음 명령을 실행해야 합니다(상승된 권한은 필요하지 않음). 여러 가지 방법으로 이 작업을 수행할 수 있습니다. 예를 들어 메일 메시지나 지원 센터 포털의 링크를 통해 사용자가 명령을 실행하도록 할 수도 있고 로그온 스크립트에 명령을 추가할 수도 있습니다.

    -   Windows 10, Windows 8.1 및 Windows 8 64비트:

        ```
        x64\aadrmprep.exe /configureO2010
        ```

    -   Windows 10, Windows 8.1 및 Windows 8 32비트:

        ```
        X86\aadrmprep.exe /configureO2010
        ```

    -   Windows 7 64비트:

        ```
        x64\win7\aadrmpep.exe /configureO2010
        ```

설치 성공 여부를 확인하려면 이 항목의 [설치 성공 여부 확인](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_verifyscripted) 섹션을 참조하세요.

#### RMS 공유 응용 프로그램 및 Office 추가 기능만 설치하려면

1.  다음 명령을 사용하여 AD RMS 클라이언트 및 RMS 공유 응용 프로그램을 설치합니다.

    -   64비트 Windows:

        ```
        x64\setup_ipviewer.exe /norestart /quiet /msicl "MSIRESTARTMANAGERCONTROL=Disable" /log "<log file path and name>"
        ```

    -   32비트 Windows:

        ```
        X86\setup_ipviewer.exe /norestart /quiet /msicl "MSIRESTARTMANAGERCONTROL=Disable" /log "<log file path and name>"
        ```

    예: `\\server5\apps\rms\x64\setup_ipviewer.exe /norestart /quiet /msicl "MSIRESTARTMANAGERCONTROL=Disable" /log "C:\Log files\ipviewerinstall.log"`

2.  다음 명령을 사용하여 Office 추가 기능을 설치합니다.

    -   64비트 버전 Office:

        ```
        msiexec.exe /norestart /quiet MSIRESTARTMANAGERCONTROL=Disable /i "x64\Setup64.msi" /L*v "<log file path and name>"
        ```

    -   32비트 버전 Office:

        ```
        msiexec.exe /norestart /quiet MSIRESTARTMANAGERCONTROL=Disable /i "x86\Setup.msi" /L*v "<log file path and name>"
        ```

    예: `\\server5\apps\rms\msiexec.exe /norestart /quiet MSIRESTARTMANAGERCONTROL=Disable /i "x64\Setup64.msi" /L*v "C:\Log files\rmsofficeinstall.log"`

설치 성공 여부를 확인하려면 이 항목의 [설치 성공 여부 확인](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_verifyscripted) 섹션을 참조하세요.

### <a name="BKMK_verifyscripted"></a>설치 성공 여부 확인
설치 로그 파일을 통해 제대로 설치되었는지 확인할 수 있습니다.

##### Office 2016 또는 Office 2013 및 Azure RMS 또는 Active Directory RMS용 RMS 공유 응용 프로그램의 설치 성공 여부를 확인하려면

-   Setup.exe 명령이 정상적으로 실행되었는지 확인하려면 각 컴퓨터의*%temp%\RMS_installer_&lt;guid&gt;* 폴더에서 설치 로그 파일 **RMInstaller.log**를 검색한 다음 종료 코드를 확인합니다.

    설치에 성공한 경우에는 종료 코드가 0이고 기타 모든 숫자는 설치가 실패했음을 나타냅니다.

    예제 로그 파일 이름: **C:\temp\RMS_Installer_9352fc91-1982-43bf-958a-2ef1fe9c2ed0\RMInstaller.log**

##### Office 2010 및 Azure RMS용 RMS 공유 응용 프로그램의 설치 성공 여부를 확인하려면

1.  Setup.exe 명령이 정상적으로 실행되었는지 확인하려면 각 컴퓨터의*%temp%\RMS_installer_&lt;guid&gt;* 폴더에서 설치 로그 파일 **RMInstaller.log**를 검색한 다음 종료 코드를 확인합니다.

    설치에 성공한 경우에는 종료 코드가 0이고 기타 모든 숫자는 설치가 실패했음을 나타냅니다.

    예제 로그 파일 이름: **C:\temp\RMS_Installer_9352fc91-1982-43bf-958a-2ef1fe9c2ed0**

2.  RMSSetup.exe 명령이 정상적으로 실행되었는지 확인하려면 사용자가 *%localappdata%\microsoft\drm* 폴더에 다음 파일을 만들어야 합니다.

    -   CERT-Machine-2048.drm

    -   CERT-Machine.drm

    -   CLC-&#42;.drm

    -   GIC-&#42;.drm

    CLC-&#42;.drm 파일 예제:

    **CLC-alice@isvtenant999.onmicrosoft.com-{1b9cfccf;k5b11;k4a10;kac15;k29b2b6980f4c}.drm**

##### Office 2010 및 Active Directory RMS용 RMS 공유 응용 프로그램의 설치 성공 여부를 확인하려면

1.  Setup.exe 명령이 정상적으로 실행되었는지 확인하려면 각 컴퓨터의 *%temp%\RMS_installer_&lt;guid&gt;* 폴더에서 설치 로그 파일을 검색한 다음 종료 코드를 확인합니다.

    설치에 성공한 경우에는 종료 코드가 0이고 기타 모든 숫자는 설치가 실패했음을 나타냅니다.

    예제 로그 파일 이름: **C:\temp\RMS_Installer_9352fc91-1982-43bf-958a-2ef1fe9c2ed0**

2.  aadrmprep.exe 명령이 정상적으로 실행되었는지 확인하려면 설치 로그 파일에서 다음 텍스트를 검색합니다. **aadrmprep.exe가 종료되었습니다(SUCCESS 상태).**

    > [!NOTE]
    > 첫 번째 설치가 실패하고 두 번째 설치가 성공하는 경우와 같이 이 설치가 두 번 실행되는 경우도 있습니다.

    이 도구가 변경하는 레지스트리를 수동으로 확인하려는 경우 다음 레지스트리를 확인하면 됩니다.

    -   [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSDRM\Federation]

        "FederationHomeRealm"="urn:HostedRmsOnlineService:Certification"

    -   [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSDRM\Federation]

        "FederationHomeRealm"="urn:HostedRmsOnlineService:Certification"

    -   [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSDRM\ServiceLocation\Activation]

        @="&lt;certification url&gt;"

    -   [HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\14.0\Common\DRM]

        DefaultUser="&lt;default_user&gt;"

##### RMS 공유 응용 프로그램 및 Office 추가 기능만의 설치 성공 여부를 확인하려면

1.  Setup_ipviewer.exe 명령이 정상적으로 실행되었는지 확인하려면 설치 로그 파일에서 다음 텍스트를 검색합니다. **설치 성공 또는 오류 상태: 0**

    정상적으로 설치된 경우에 표시되는 줄 예제:

    **MSI (s) (F0:B8) [14:19:57:854]: 제품: Active Directory Rights Management Services 클라이언트 2.1 -- 설치를 완료했습니다.**

    **MSI (s) (F0:B8) [14:19:57:854]: Windows Installer에서 제품을 설치했습니다. 제품 이름: Active Directory Rights Management Services 클라이언트 2.1. 제품 버전: 1.0.1179.1. 제품 언어: 1033. 제조업체: Microsoft Corporation. 설치 성공 또는 오류 상태: 0.**

2.  Office 추가 기능의 설치 성공 여부를 각 컴퓨터의 설치 로그 파일에서 다음 텍스트를 검색합니다. **설치 성공 또는 오류 상태: 0**

    정상적으로 설치된 경우에 표시되는 줄 예제:

    **MSI (s) (9C:88) [18:49:04:007]: 제품: Microsoft RMS Office 추가 기능 -- 설치를 완료했습니다.**

    **MSI (s) (9C:88) [18:49:04:007]: Windows Installer에서 제품을 설치했습니다. 제품 이름: Microsoft RMS Office 추가 기능. 제품 버전: 1.0.7. 제품 언어: 1033. 제조업체: Microsoft. 설치 성공 또는 오류 상태: 0.**

### <a name="BKMK_uninstallscripted"></a>제거 명령
이러한 배포에 필요한 설치 명령 중 일부만이 제거 명령을 지원합니다. AD RMS 클라이언트와 공유 응용 프로그램 및 Office 추가 기능을 제거할 수 있습니다. 이러한 요소를 제거하려면 다음 명령을 사용합니다.

##### AD RMS 클라이언트 및 RMS 공유 응용 프로그램을 제거하려면

-   다음 명령을 사용합니다.

    -   64비트 Windows:

        ```
        x64\setup_ipviewer.exe /uninstall /quiet
        ```

    -   32비트 Windows:

        ```
        x86\setup_ipviewer.exe /uninstall /quiet
        ```

##### Office 추가 기능을 제거하려면

-   다음 명령을 사용합니다.

    -   64비트 버전 Office:

        ```
        msiexec /x \x64\Setup[64].msi /quiet
        ```

    -   32비트 버전 Office:

        ```
        msiexec /x \x86\Setup.msi /quiet
        ```

### <a name="BKMK_SuppressAutomaticUpdates"></a>자동 업데이트를 사용하지 않도록 설정
기본적으로는 최신 버전의 RMS 공유 응용 프로그램을 사용할 수 있으면 사용자에게 알림이 표시되며 해당 버전을 다운로드할지를 묻는 메시지가 나타납니다. 다음 레지스트리를 편집하여 이 알림을 표시하지 않도록 설정할 수 있습니다.

1.  **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC**로 이동한 다음 **RmsSharingApp** 키가 아직 없으면 새로 만듭니다.

2.  **RmsSharingApp**을 선택하고 새 DWORD 값 **AllowUpdatePrompt**를 만든 후에 값을 **0**으로 설정합니다.

WSUS에서는 RMS 공유 응용 프로그램을 지원하지 않으므로 다음 기술을 사용하여 새 RMS 공유 응용 프로그램 버전을 모든 사용자에게 배포하기 전에 테스트를 할 수 있습니다.

1.  모든 사용자의 컴퓨터에서 자동 업데이트를 표시하지 않도록 설정하는 스크립트를 실행합니다. 관리자가 새 버전을 테스트하는 데 사용하는 컴퓨터에서는 이 스크립트를 실행하지 마세요.

2.  새 버전을 사용할 수 있게 되면 관리자가 해당 버전을 다운로드하여 테스트합니다.

3.  테스트를 완료하고 모든 문제를 해결한 후 이 가이드에 나와 있는 자동 배포 지침을 사용하여 모든 사용자에게 최신 버전을 배포합니다.

### <a name="BKMK_DocumentTracking"></a>AD RMS만 해당: 문서 추적 기능 구성
[문서 추적 기능을 지원하는 구독](https://technet.microsoft.com/en-us/dn858608)이 있는 경우 기본적으로 조직의 모든 사용자에 대해 문서 추적 사이트를 사용하도록 설정됩니다.  문서 추적 기능에서는 사용자가 공유하는 보호된 문서에 액세스하려고 시도하는 사람의 메일 주소, 해당 문서에 액세스하려고 시도한 시간 및 해당 위치와 같은 정보를 표시합니다. 개인정보취급방침 요구 사항으로 인해 조직에서 이 정보 표시가 금지된 경우 [Disable-AadrmDocumentTrackingFeature](http://go.microsoft.com/fwlink/?LinkId=623032) cmdlet을 사용하여 문서 추적 사이트에 대한 액세스를 사용하지 않도록 설정할 수 있습니다. 언제든 [Enable-AadrmDocumentTrackingFeature](http://go.microsoft.com/fwlink/?LinkId=623037)를 사용하여 사이트에 대한 액세스를 다시 사용하도록 설정할 수 있고 [Get-AadrmDocumentTrackingFeature](http://go.microsoft.com/fwlink/?LinkId=623037)를 사용하여 액세스가 현재 사용하거나 사용하지 않도록 설정되어 있는지 확인할 수 있습니다.

 이러한 cmdlet을 실행하려면 Windows PowerShell용 Azure RMS **2.3.0.0** 이상 버전을 사용하고 있어야 합니다.  설치 지침은 [Azure Rights Management용 Windows PowerShell 설치](https://technet.microsoft.com/library/jj585012.aspx)을 참조하세요.

> [!TIP]
> 이전에 모듈을 다운로드하여 설치한 경우 다음을 실행하여 버전 번호를 확인합니다. `(Get-Module aadrm –ListAvailable).Version`

다음 URL은 문서 추적 기능에 사용되며 예를 들어 보안이 강화된 Internet Explorer를 사용 중인 경우 신뢰할 수 있는 사이트에 추가하는 등의 방법으로 허용해야 합니다.

-   https://&#42;.azurerms.com

-   https://ecn.dev.virtualearth.net

    > [!NOTE]
    > Bing Maps의 URL입니다.

-   https://&#42;.microsoftonline.com

-   https://&#42;.microsoftonline-p.com

### <a name="BKMK_FederatedDomains"></a>AD RMS만 해당: 조직 내의 여러 메일 도메인 지원
AD RMS를 사용 중이며 합병이나 인수 등으로 인해 조직의 사용자에게 메일 도메인이 여러 개 있는 경우 다음 레지스트리를 편집해야 합니다.

1.  **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC**로 이동한 다음 **RmsSharingApp** 키가 아직 없으면 새로 만듭니다.

2.  **RmsSharingApp**을 선택하고 새 다중 문자열 값 **FederatedDomains**를 만든 후 조직에서 사용하는 도메인과 모든 하위 도메인을 추가합니다. 와일드카드는 지원되지 않습니다.

    예를 들면 다음과 같습니다. Coho Vineyard &amp; Winery라는 회사의 표준 메일 도메인은 **cohovineyardandwinery.com**이지만 합병으로 인해 **cohowinery.com**, **eastcoast.cohowinery.com** 및 **cohovineyard** 메일 도메인도 사용합니다.**FederatedDomains** 값 데이터의 경우 관리자는 다음을 입력합니다. **cohowinery.com; eastcoast.cohowinery.com; cohovineyard**

레지스트리를 이와 같이 변경하지 않으면 사용자가 조직의 다른 사용자에 의해 보호된 콘텐츠를 사용하지 못할 수도 있습니다. Azure RMS를 사용하는 경우에는 레지스트리를 이와 같이 편집할 필요가 없습니다.

## <a name="BKMK_AdminOverview"></a>Microsoft Rights Management 공유 응용 프로그램 기술 개요
Microsoft Rights Management 공유 응용 프로그램은 선택적으로 다운로드 가능하며 다음 기능을 제공하는 Microsoft Windows 및 기타 플랫폼용 응용 프로그램입니다.

-   단일 파일을 보호하거나 여러 파일 또는 선택한 폴더 내의 모든 파일을 대량으로 보호합니다.

-   일반적으로 사용되는 텍스트 및 이미지 파일 형식용 기본 제공 뷰어와 모든 파일 형식에 대한 보호를 완벽히 지원합니다.

-   RMS 보호를 지원하지 않는 파일에 대한 일반 보호 기능을 제공합니다.

-   Office IRM(정보 권한 관리)을 사용하여 보호된 파일과의 완벽한 상호 운용성을 제공합니다.

-   SharePoint, FCI 및 지원되는 PDF 작성 도구를 사용하여 보호된 PDF 파일과의 완벽한 상호 운용성을 제공합니다.

Microsoft Rights Management 공유 응용 프로그램은 새로운 [AD RMS 클라이언트 2.1 런타임](http://www.microsoft.com/download/details.aspx?id=38396)을 사용합니다. Microsoft Rights Management 공유 응용 프로그램은 AD RMS 2.1의 기능을 사용하여 최종 사용자에게 단순한 보호 및 사용 환경을 제공합니다.

RMS의 2013년 10월 릴리스를 설치하면 Office 2010을 사용해 문서를 기본적으로 보호할 수 있으며 다른 회사 직원에게 문서를 보낼 수 있습니다. 문서를 받은 사용자는 Azure RMS를 통해 문서를 사용할 수 있습니다. 또한 이 릴리스에서는 암호화 모드 2에서 AD RMS를 사용하는 경우 개별 사용자에 대해 RMS를 사용할 수 있으며 Azure RMS를 사용하는 다른 회사 직원의 콘텐츠도 사용할 수 있습니다. 호화 모드 2에 대한 자세한 내용은 [AD RMS 암호화 모드](http://technet.microsoft.com/library/hh867439%28v=ws.10%29.aspx)를 참조하세요.

### <a name="BKMK_LevelsofProtection"></a>보호 수준 - 기본 및 일반
Microsoft Rights Management 공유 응용 프로그램은 다음 표에서 설명하는 것처럼 각기 다른 두 수준의 보호를 지원합니다.

|보호 유형|네이티브|제네릭|
|---------|--------|-------|
|설명|텍스트, 이미지, Microsoft Office(Word, Excel, PowerPoint) 파일, .pdf 파일 및 AD RMS를 지원하는 기타 응용 프로그램 파일 형식의 경우 기본 보호는 권한 적용 및 암호화를 모두 포함하는 강력한 보호 수준을 제공합니다.|기타 모든 응용 프로그램 및 파일 형식의 경우 일반 보호는 사용자가 파일을 열 권한이 있는지를 확인하는 인증 및 .pfile 파일 형식을 사용하는 파일 캡슐화 기능이 모두 포함된 보호 수준을 제공합니다.|
|보호|파일은 다음과 같은 방식으로 완벽하게 암호화되며 보호가 적용됩니다.<br /><br />-   보호된 콘텐츠를 렌더링하기 전에 메일을 통해 파일을 받았거나 파일 또는 공유 권한을 통해 파일 액세스 권한을 부여받은 사용자가 정상적으로 인증을 해야 합니다.<br />-   또한 IP 뷰어(보호된 텍스트, 이미지 파일의 경우)나 연결된 응용 프로그램(지원되는 기타 모든 파일 형식의 경우)에서 콘텐츠를 렌더링할 때는 파일 보호 시 콘텐츠 소유자가 설정한 사용 권한 및 정책이 완전하게 적용됩니다.|파일 보호는 다음과 같은 방식으로 적용됩니다.<br /><br />-   보호된 콘텐츠를 렌더링하기 전에 파일을 열 권한이 있으며 파일 액세스 권한을 부여받은 사용자가 정상적으로 인증해야 합니다. 권한 부여가 실패하면 파일이 열리지 않습니다.<br />-   콘텐츠 소유자가 설정한 사용 권한 및 정책이 표시되어 해당하는 사용 정책의 권한 있는 사용자를 알려 줍니다.<br />-   지원되지 않는 응용 프로그램의 경우 파일을 열고 액세스하는 권한 있는 사용자의 감사 로깅이 수행되기는 하지만 사용 권한은 적용되지 않습니다.|
|파일 형식에 대한 기본값|이 보호 수준은 다음 파일 형식에 대한 기본 보호 수준입니다.<br /><br />-   텍스트 및 이미지 파일<br />-   Microsoft Office(Word, Excel, PowerPoint) 파일<br />-   Portable Document Format(.pdf)<br /><br />자세한 내용은 [지원되는 파일 형식 및 파일 이름 확장명](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_SupportFileTypes) 섹션을 참조하세요.|이 수준은 전체 보호를 통해 지원되지 않는 .vsdx, .rtf 등의 기타 모든 파일 형식에 대한 기본 보호 수준입니다.|
RMS 공유 응용 프로그램이 적용하는 기본 보호 수준을 변경할 수 있습니다. 기본 수준을 일반 수준으로 변경하거나 그 반대로 변경할 수 있으며, RMS 공유 응용 프로그램이 보호를 적용하지 않도록 차단할 수도 있습니다. 자세한 내용은 이 항목의 [파일의 기본 보호 수준 변경](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_ChangeDefaultProtection) 섹션을 참조하세요.

### <a name="BKMK_SupportFileTypes"></a>지원되는 파일 형식 및 파일 이름 확장명
다음 표에는 Microsoft Rights Management 공유 응용 프로그램에서 기본적으로 지원하는 파일 형식이 나와 있습니다. 이러한 파일 형식의 경우 기본 보호를 적용하면 원래 파일 이름 확장명이 변경되며 해당 파일은 읽기 전용이 됩니다.

또한 사용자가 공유를 통해 보호하는 Word, Excel 또는 PowerPoint 파일을 RMS 공유 응용 프로그램이 기본적으로 보호하는 경우 이 작업을 수행하면 원본과 파일 이름은 같은 복사본이며 파일 이름 확장명은 **.ppdf**인 두 번째 파일이 자동으로 만들어집니다. 이 파일 버전이 만들어지므로 RMS 공유 응용 프로그램을 설치하는 받는 사람은 기본 보호가 적용된 파일을 항상 열 수 있습니다.

일반 수준으로 보호되는 파일의 경우에는 원래 파일 이름 확장명이 항상 .pfile로 변경됩니다.

> [!WARNING]
> 파일 이름 확장명을 검사한 다음 그에 따라 작업을 수행하는 방화벽, 웹 프록시 또는 보안 소프트웨어를 사용하는 경우에는 이러한 새 파일 이름 확장명을 지원하도록 방화벽, 웹 프록시 또는 보안 소프트웨어를 다시 구성해야 할 수 있습니다.

|원래 파일 이름 확장명|RMS로 보호된 파일 이름 확장명|
|----------------|----------------------|
|.txt|.ptxt|
|.xml|.pxml|
|.jpg|.pjpg|
|.jpeg|.ppng|
|.pdf|.ppdf|
|.png|.ppng|
|.tiff|.ptiff|
|.bmp|.pbmp|
|.gif|.pgif|
|.giff|.pgiff|
|.jpe|.pjpe|
|.jfif|.pjfif|
|.jif|.pjif|
|.jt|.pjt|
¹ PDF 렌더링 기능은 Foxit에서 제공합니다. Copyright © 2003–2014 by Foxit Corporation.

다음 표에는 Microsoft Rights Management 공유 응용 프로그램이 Microsoft Office 2016, Office 2013 및 Office 2010에서 기본적으로 지원하는 파일 형식이 나와 있습니다. 이러한 파일의 경우에는 RMS를 통해 파일을 보호한 후에도 파일 이름 확장명이 동일하게 유지됩니다.

|Office에서 지원하는 파일 형식|Office에서 지원하는 파일 형식|
|-----------------------|-----------------------|
|.doc<br /><br />.docm<br /><br />.docx<br /><br />.dot<br /><br />.dotm<br /><br />.dotx<br /><br />.potm<br /><br />.potx<br /><br />.pps<br /><br />.ppsm<br /><br />.ppsx<br /><br />.ppt<br /><br />.pptm|.pptx<br /><br />.thmx<br /><br />.xla<br /><br />.xlam<br /><br />.xls<br /><br />.xlsb<br /><br />.xlt<br /><br />.xlsm<br /><br />.xlsx<br /><br />.xltm<br /><br />.xltx<br /><br />.xps|

### <a name="BKMK_ChangeDefaultProtection"></a>파일의 기본 보호 수준 변경
레지스트리를 편집하여 RMS 공유 응용 프로그램이 파일을 보호하는 방식을 변경할 수 있습니다. 예를 들어 기본 보호를 지원하는 파일을 RMS 공유 응용 프로그램에서 일반적으로 보호하도록 강제 지정할 수 있습니다.

이러한 작업을 수행해야 하는 이유는 다음과 같습니다.

-   모든 사용자가 자신의 모바일 장치에서 파일을 열 수 있도록 설정

-   기본 보호를 지원하는 응용 프로그램을 사용하지 않더라도 모든 사용자가 파일을 열 수 있도록 설정

-   파일 이름 확장명을 기준으로 하여 파일에 대해 작업을 수행하며, .pfile 파일 이름 확장명을 수용하도록 다시 구성할 수는 있지만 기본 보호를 위해 여러 파일 이름 확장명을 수용하도록 다시 구성할 수는 없는 보안 시스템 수용

마찬가지로 일반 보호가 기본적으로 적용되는 파일에 대해 RMS 공유 응용 프로그램이 기본 보호를 적용하도록 강제 지정할 수 있습니다. 부 개발자가 작성한 LOB(기간 업무) 응용 프로그램이나 ISV(Independent Software Vendor)에서 구매한 응용 프로그램 등 RMS API를 지원하는 응용 프로그램을 사용하는 경우 이러한 작업을 수행할 수 있습니다.

RMS 공유 응용 프로그램이 파일 보호를 차단하도록, 즉 기본 보호 또는 일반 보호를 적용하지 않도록 강제 지정할 수도 있습니다. 예를 들어 콘텐츠를 처리하려면 특정 파일을 열 수 있어야 하는 자동화된 응용 프로그램이나 서비스를 사용하는 경우 이러한 작업을 수행해야 할 수 있습니다. 특정 파일 형식에 대한 보호를 차단하면 사용자가 RMS 공유 응용 프로그램을 사용하여 해당 파일 형식의 파일을 보호할 수 없습니다. 이러한 파일을 보호하려고 하면 관리자가 보호를 차단했으므로 파일을 보호하기 위한 작업을 취소해야 한다는 메시지가 표시됩니다.

기본적으로 기본 보호가 적용되는 모든 파일에 대해 RMS 공유 응용 프로그램이 일반 보호를 적용하도록 구성하려면 다음 레지스트리를 편집합니다.

1.  **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\RMSSharingApp\FileProtection**: 새 키 **&#42;**를 만듭니다.

    이 설정은 임의의 파일 이름 확장명이 지정된 파일을 나타냅니다.

2.  새로 추가한 키 **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\RMSSharingApp\FileProtection\&#42;**에서 데이터 값이 **Pfile**인 새 문자열 값(REG_SZ) **Encryption**을 만듭니다.

    이 설정을 사용하는 경우 RMS 공유 응용 프로그램이 일반 보호를 적용하게 됩니다.

이 두 설정을 사용하면 RMS 공유 응용 프로그램이 특정 파일 이름 확장명을 사용하는 모든 파일에 일반 보호를 적용합니다. 이러한 결과를 원하는 경우에는 추가 구성을 수행할 필요가 없습니다. 그러나 계속 기본적으로 보호되도록 특정 파일 형식에 대해 예외를 정의할 수 있습니다. 이렇게 하려면 각 파일 형식에 대해 추가로 3개 레지스트리를 편집해야 합니다.

1.  **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\RMSSharingApp\FileProtection**: 파일 이름 확장명(앞의 마침표는 제외)이 이름으로 지정된 새 키를 추가합니다.

    예를 들어 파일 이름 확장명이 .docx인 파일의 경우 **DOCX** 키를 만듭니다.

2.  새로 추가된 파일 형식 키(예: **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\RMSSharingApp\FileProtection\DOCX**)에서 값이 **0**인 새 DWORD 값 **AllowPFILEEncryption**을 만듭니다.

3.  새로 추가된 파일 형식 키(예: **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\RMSSharingApp\FileProtection\DOCX**)에서 값이 **Native**인 새 문자열 값 **Encryption**을 만듭니다.

이러한 설정을 사용하는 경우 파일 이름 확장명이 .doxc인 파일(RMS 공유 응용 프로그램에 의해 기본적으로 보호됨)을 제외한 모든 파일이 일반적으로 보호됩니다.

기본 보호를 지원하며 RMS 공유 응용 프로그램에서 일반적으로 보호하지 않도록 지정하기 위해 예외로 정의하려는 다른 파일 형식에 대해 이 3단계를 반복합니다.

다음 값을 지원하는 **Encryption** 문자열의 값을 변경하여 다른 시나리오에서도 비슷하게 레지스트리를 편집할 수 있습니다.

-   **Pfile**: 일반 보호

-   **Native**: 기본 보호

-   **Off**: 보호 차단

## 참고 항목
[Rights Management 공유 응용 프로그램 사용자 가이드](../Topic/Rights_Management_sharing_application_user_guide.md)

