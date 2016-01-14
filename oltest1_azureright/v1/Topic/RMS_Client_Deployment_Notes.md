---
description: na
keywords: na
title: RMS Client Deployment Notes
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 03cc8c6f-3b63-4794-8d92-a5df4cdf598f
---
# RMS 클라이언트 배포 참고 사항
RMS 클라이언트(권한 관리 서비스 클라이언트) 버전 2는 MSIPC 클라이언트로도 알려져 있습니다. 이 제품은 온-프레미스 또는 클라우드에서 Microsoft 권한 관리 서비스와 통신하는 Windows 컴퓨터용 소프트웨어로, 조직의 경계 내에서 또는 관리되는 경계 외부에서 응용 프로그램 및 장치를 통과하는 정보에 대한 액세스 및 사용을 보호하는 데 도움이 됩니다.[Windows용 권한 관리 공유 응용 프로그램](https://technet.microsoft.com/library/dn919648.aspx)과 함께 제공되는 RMS 클라이언트는 해당 사용권 계약에 대한 승인 및 동의가 있을 때 타사 소프트웨어와 함께 자유롭게 배포할 수 있는 [선택적 다운로드로](http://www.microsoft.com/download/details.aspx?id=38396)로 사용할 수 있으므로 클라이언트는 권한 관리 서비스에 의해 보호된 콘텐츠를 보호하고 사용할 수 있습니다.

이 항목은 다음과 같은 섹션으로 구성됩니다.

-   [RMS 클라이언트 재배포](#BKMK_RedistributeInstaller)

-   [RMS 클라이언트 설치](#BKMK_InstallClient)

-   [RMS 클라이언트에 대한 질문과 대답](#BKMK_QA)

-   [RMS 클라이언트 설정](#BKMK_Settings)

-   [AD RMS만 해당: 신뢰할 수 있는 AD RMS 서버를 사용하도록 RMS 클라이언트 제한](#BKMK_UsingTrustedServers)

-   [RMS 서비스 검색](#BKMK_ServiceDiscovery)

## <a name="BKMK_RedistributeInstaller"></a>RMS 클라이언트 재배포
RMS 클라이언트는 다른 응용 프로그램 및 IT 솔루션과 함께 자유롭게 재배포하고 번들로 제공될 수 있습니다. RMS 클라이언트를 재배포하려는 응용 프로그램 개발자나 솔루션 공급자는 다음과 같은 두 가지 옵션 중 하나를 사용할 수 있습니다.

-   권장: 응용 프로그램 설치에 RMS 클라이언트 설치 관리자를 포함하고 자동 모드로 실행(다음 섹션에서 자세히 설명되는 **/quiet** 스위치 사용).

-   RMS 클라이언트에 응용 프로그램에 대한 필수 구성 요소를 지정합니다. 이 옵션을 사용할 경우 사용자가 응용 프로그램을 사용하도록 하기 위해 먼저 클라이언트를 구하고 설치하고 클라이언트로 해당 컴퓨터를 업데이트하기 위한 추가 지침을 제공해야 할 수 있습니다.

## <a name="BKMK_InstallClient"></a>RMS 클라이언트 설치
RMS 클라이언트는 **setup_msipc_***&lt;arch&gt;***.exe**라는 설치 관리자 실행 파일에 포함되어 있습니다. 여기서 *&lt;arch&gt;*는 **x86**32비트 클라이언트 컴퓨터 또는 **x64**64비트 클라이언트 컴퓨터입니다. 64비트(x64) 설치 관리자 패키지는 64비트 운영 체제 설치에서 실행되는 32비트 응용 프로그램과의 호환성을 위한 32비트 런타임 실행 파일과 네이티브 64비트 응용 프로그램을 지원하기 위한 64비트 런타임 실행 파일을 모두 설치합니다. 32비트(x86) 설치 관리자는 64비트 Windows 설치에서 실행되지 않습니다.

> [!NOTE]
> RMS 클라이언트를 설치하려면 로컬 컴퓨터에서 Administrators 그룹의 멤버와 같은 상승된 권한이 있어야 합니다.

다음과 같은 설치 방법 중 하나를 사용하여 RMS 클라이언트를 설치할 수 있습니다.

-   **자동 모드.** 명령줄 옵션의 일부로 **/quiet** 스위치를 사용하여 컴퓨터에 RMS 클라이언트를 자동으로 설치할 수 있습니다. 다음 예제에서는 64비트 클라이언트 컴퓨터에서의 RMS 클라이언트에 대한 자동 모드 설치를 보여 줍니다.

    ```
    setup_msipc_x64.exe /quiet
    ```

-   **대화형 모드.** RMS 클라이언트 설치 마법사에서 제공하는 GUI 기반 설치 프로그램을 사용하여 RMS 클라이언트를 설치할 수도 있습니다. 이 작업을 수행하려면 로컬 컴퓨터에 복사 또는 다운로드한 폴더에서 RMS 클라이언트 설치 관리자 패키지(**setup_msipc_***&lt;arch&gt;***.exe**)를 두 번 클릭합니다.

## <a name="BKMK_QA"></a>RMS 클라이언트에 대한 질문과 대답
다음 섹션에는 RMS 클라이언트에 대한 질문과 대답이 포함되어 있습니다.

### 어떤 운영 체제가 RMS 클라이언트를 지원하나요?
RMS 클라이언트는 다음 운영 체제에서 지원됩니다.

|Windows Server 운영 체제|Windows 클라이언트 운영 체제|
|------------------------|-----------------------|
|Windows Server 2012 R2|Windows 8.1|
|Windows Server 2012|Windows 8|
|Windows Server 2008 R2|Windows 7 SP1 이상|
|Windows Server 2008(AD RMS만 해당)|Windows Vista SP2 이상(AD RMS만 해당)|

### 어떤 프로세서 또는 플랫폼이 RMS 클라이언트를 지원하나요?
RMS 클라이언트는 x86 및 x64 컴퓨팅 플랫폼에서 지원됩니다.

### RMS 클라이언트는 어디에 설치되나요?
기본적으로 RMS 클라이언트는 %ProgramFiles%\Active Directory Rights Management Services Client 2.&lt;부 버전 번호&gt;에 설치됩니다.

### 어떤 파일이 RMS 클라이언트 소프트웨어와 연결되어 있나요?
다음 파일은 RMS 클라이언트 소프트웨어의 일부로 설치됩니다.

-   Msipc.dll

-   Ipcsecproc.dll

-   Ipcsecproc_ssp.dll

-   MSIPCEvents.man

이러한 파일 외에도 RMS 클라이언트는 44개 언어로 MUI(다국어 사용자 인터페이스) 지원 파일을 설치합니다. 지원되는 언어를 확인하려면 RMS 클라이언트 설치를 실행하고 설치가 완료되면 기본 경로 아래에서 다국어 지원 폴더의 내용을 검토합니다.

### 지원되는 운영 체제를 설치할 때 기본적으로 RMS 클라이언트가 포함되나요?
아니요. 이 버전의 RMS 클라이언트는 지원되는 Microsoft Windows 운영 체제 버전이 실행되는 컴퓨터에서 따로 설치할 수 있는 선택적 다운로드로 제공됩니다.

### RMS 클라이언트는 Microsoft 업데이트에 의해 자동으로 업데이트되나요?
자동 설치 옵션을 사용하여 이 RMS 클라이언트를 설치한 경우 RMS 클라이언트는 현재 Microsoft 업데이트 설정을 상속합니다. GUI 기반 설치 프로그램을 사용하여 RMS 클라이언트를 설치한 경우 RMS 클라이언트 설치 마법사에서 Microsoft 업데이트를 사용하도록 설정하라는 메시지를 표시합니다.

## <a name="BKMK_Settings"></a>RMS 클라이언트 설정
다음 섹션에는 RMS 클라이언트에 대한 설정 정보가 포함되어 있습니다. 이 정보는 RMS 클라이언트를 사용하는 서비스 또는 응용 프로그램에 문제가 있는 경우에 유용할 수 있습니다.

> [!NOTE]
> 일부 설정은 RMS 지원 응용 프로그램이 클라이언트 모드 응용 프로그램(예: Microsoft Word 및 Outlook 또는 RMS 공유 응용 프로그램)으로 실행되는지 또는 서버 모드 응용 프로그램(예: SharePoint 및 Exchange)으로 실행되는지에 따라 달라집니다.  다음 표에서는 이러한 설정이 각각 **클라이언트 모드** 및 **서버 모드**로 구분되어 있습니다.

### RMS 클라이언트가 클라이언트 컴퓨터에서 라이선스를 저장하는 위치
RMS 클라이언트는 로컬 디스크에 라이선스를 저장하고 Windows 레지스트리의 일부 정보를 캐시하기도 합니다.

|설명|클라이언트 모드 경로|서버 모드 경로|
|------|---------------|------------|
|라이선스 저장소 위치|%localappdata%\Microsoft\MSIPC|%allusersprofile%\Microsoft\MSIPC\Server\*&lt;SID&gt;*\|
|템플릿 저장소 위치|%localappdata%\Microsoft\MSIPC\Templates|%allusersprofile%\Microsoft\MSIPC\Server\Templates\*&lt;SID&gt;*\|
|레지스트리 위치|HKEY_CURRENT_USER<br /> \Software<br /> \Classes<br /> \Local Settings<br /> \Software<br /> \Microsoft<br /> \MSIPC|HKEY_CURRENT_USER<br /> \Software<br /> \Microsoft<br /> \MSIPC<br /> \Server<br /> \*&lt;SID&gt;*|
> [!NOTE]
> *&lt;SID&gt;*는 서버 응용 프로그램이 실행되고 있는 계정의 SID(보안 식별자)입니다. 예를 들어 응용 프로그램이 기본 제공 네트워크 서비스 계정에서 실행 중인 경우 *&lt;SID&gt;*를 해당 계정의 잘 알려진 SID 값(S-1-5-20)으로 바꿉니다.

### RMS 클라이언트에 대한 Windows 레지스트리 설정
Windows 레지스트리 키를 사용하여 일부 RMS 클라이언트 구성을 설정하거나 수정할 수 있습니다. 예를 들어 AD RMS 서버와 통신하는 RMS 지원 응용 프로그램의 관리자는 Active Directory 토폴로지 내에서 클라이언트 컴퓨터의 현재 위치에 따라 엔터프라이즈 서비스 위치를 업데이트하려고 할 수 있습니다(현재 게시를 위해 선택된 AD RMS 서버 재정의). 또는 클라이언트 컴퓨터에서 RMS 추적을 사용하도록 설정하여 RMS 지원 응용 프로그램의 문제를 해결하는 데 도움을 얻을 수 있습니다. 다음 표를 사용하여 RMS 클라이언트에 대해 변경할 수 있는 레지스트리 설정을 알아보세요.

|작업|설정|
|------|------|
|AD RMS만 해당: 클라이언트 컴퓨터에 대한 엔터프라이즈 서비스 위치를 업데이트하려면|다음 레지스트리 키를 업데이트합니다.<br /><br />-   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation\EnterpriseCertification<br />    REG_SZ: default<br />    **값:**&lt;http 또는 https&gt;:// *RMS_Cluster_Name*/_wmcs/Certification<br />-   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation\EnterprisePublishing<br />    REG_SZ: default<br />    **값:** &lt;http 또는 https&gt;:// *RMS_Cluster_Name*/_wmcs/Licensing|
|추적을 사용하거나 사용하지 않도록 설정하려면|다음 레지스트리 키를 업데이트합니다.<br /><br />-   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC<br />    REG_DWORD: Trace<br />    **Value:** 추적을 사용하도록 설정하려면 1, 추적을 사용하지 않도록 설정하려면 0(기본값)|
|템플릿 새로 고침 빈도(일)를 변경하려면|다음 레지스트리 값은 TemplateUpdateFrequencyInSeconds 값이 설정되지 않은 경우 사용자 컴퓨터에서 템플릿을 새로 고치는 빈도를 지정합니다.  이러한 값을 모두 설정하지 않으면 RMS 클라이언트(버전 1.0.1784.0)를 사용하는 응용 프로그램이 템플릿을 다운로드하는 기본 새로 고침 간격은 1일입니다. 이전 버전에서는 기본값이 7일 간격입니다.<br /><br />**클라이언트 모드:**<br /><br />-   HKEY_CURRENT_USER\Software\Classes\Local Settings\Software\Microsoft\MSIPC<br />    REG_DWORD: TemplateUpdateFrequency<br />    **Value:** 다운로드 사이의 일 수(최소 1)를 지정하는 정수 값입니다.<br /><br />**서버 모드:**<br /><br />-   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\Server\*&lt;SID&gt;*<br />    REG_DWORD: TemplateUpdateFrequency<br />    **Value:** 다운로드 사이의 일 수(최소 1)를 지정하는 정수 값입니다.|
|템플릿 새로 고침 빈도(초)를 변경하려면 **Important:** 이 옵션을 지정하는 경우 일 단위의 템플릿 새로 고침 간격은 무시됩니다. 둘 중 하나만 지정합니다.|다음 레지스트리 값은 사용자 컴퓨터에서 템플릿을 새로 고치는 빈도를 지정합니다. 이 값 또는 빈도(일)(TemplateUpdateFrequency)를 변경하기 위한 값을 설정하지 않은 경우 RMS 클라이언트(버전 1.0.1784.0)를 사용하여 응용 프로그램이 템플릿을 다운로드하는 기본 새로 고침 간격은 1일입니다. 이전 버전에서는 기본값이 7일 간격입니다.<br /><br />**클라이언트 모드:**<br /><br />-   HKEY_CURRENT_USER\Software\Classes\Local Settings\Software\Microsoft\MSIPC<br />    REG_DWORD: TemplateUpdateFrequencyInSeconds<br />    **Value:** 다운로드 사이의 초 수(최소 1)를 지정하는 정수 값입니다.<br /><br />**서버 모드:**<br /><br />-   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\Server\*&lt;SID&gt;*<br />    REG_DWORD: TemplateUpdateFrequencyInSeconds<br />    **Value:** 다운로드 사이의 초 수(최소 1)를 지정하는 정수 값입니다.|
|AD RMS만 해당: 다음 게시 요청이 있을 때 템플릿을 즉시 다운로드하려면|테스트 및 평가 동안 RMS 클라이언트에서 가능한 한 빨리 템플릿을 다운로드하는 것을 원할 수 있습니다. 이렇게 하려면 다음 레지스트리 키를 제거합니다. 그러면 RMS 클라이언트가 TemplateUpdateFrequency 레지스트리 설정에 의해 지정된 시간 동안 대기하지 않고 다음 게시 요청이 있을 때 즉시 템플릿을 다운로드합니다.<br /><br />-   HKEY_CURRENT_USER\Software\Classes\Local Settings\Software\Microsoft\MSIPC\&lt;서버 이름&gt;\Template **Note:** &lt;서버 이름&gt;은 외부(corprights.contoso.com) 및 내부(corprights) URL을 모두 포함할 수 있으므로 두 개의 다른 항목일 수 있습니다.|
|AD RMS만 해당: 페더레이션된 인증에 대한 지원을 사용하도록 설정|RMS 클라이언트 컴퓨터가 페더레이션된 트러스트를 사용하여 AD RMS 클러스터에 연결되면 페더레이션 홈 영역을 구성해야 합니다.<br /><br />-   HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\Federation<br />    REG_SZ: FederationHomeRealm<br />    **Value:** 이 레지스트리 항목의 값은 페더레이션 서비스(예: "https://fs-01.contoso.com")에 대한 URI(Uniform Resource Identifier)입니다.|
|AD RMS만 해당: 사용자 입력에 대한 폼 기반 인증을 필요로 하는 파트너 페더레이션 서버를 지원하려면|기본적으로 RMS 클라이언트는 자동 모드에서 작동되며 사용자 입력이 필요하지 않습니다. 그러나 파트너 페더레이션 서버는 폼 기반 인증 등을 통해 사용자 입력을 요구하도록 구성될 수 있습니다. 이 경우 페더레이션된 인증 양식이 브라우저 창에 표시되고 사용자가 인증을 위해 승격될 수 있게 RMS 클라이언트가 자동 모드를 무시하도록 구성해야 합니다.<br /><br />-   HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\Federation<br />    REG_DWORD: EnableBrowser **Note:** 페더레이션 서버가 폼 기반 인증을 사용하도록 구성되면 이 키가 필요합니다. 페더레이션 서버가 Windows 통합 인증을 사용하도록 구성되면 이 키가 필요하지 않습니다.|
|AD RMS만 해당: ILS 서비스 사용을 차단하려면|기본적으로 RMS 클라이언트는 ILS 서비스에 의해 보호되는 콘텐츠의 사용을 허용하지만 다음 레지스트리 키를 설정하여 이 서비스를 차단하도록 클라이언트를 구성할 수 있습니다. 이 레지스트리 키가 ILS 서비스를 차단하도록 설정된 경우 ILS 서비스에 의해 보호되는 콘텐츠를 열어서 사용하려고 하면 다음과 같은 오류가 반환됩니다.<br />HRESULT_FROM_WIN32(ERROR_ACCESS_DISABLED_BY_POLICY)<br /><br />-   HKEY_CURRENT_USER\Software\Classes\Local Settings\Software\Microsoft\MSIPC<br />    REG_DWORD: **DisablePassportCertification**<br />    **Value:** ILS 사용을 차단하려면 1, ILS 사용을 허용하려면 0(기본값)|

### RMS 클라이언트에 대한 템플릿 배포 관리
템플릿을 사용하면 사용자와 관리자는 권한 관리 보호를 쉽고 빠르게 적용할 수 있으며 RMS 클라이언트는 해당 RMS 서버 또는 서비스에서 템플릿을 자동으로 다운로드합니다. 템플릿을 다음 폴더 위치에 두면 RMS 클라이언트는 기본 위치에서 템플릿을 다운로드하지 않고 대신 이 폴더에 넣은 템플릿을 다운로드합니다. RMS 클라이언트는 사용 가능한 다른 RMS 서버에서 템플릿을 계속 다운로드할 수 있습니다.

**클라이언트 모드:** %localappdata%\Microsoft\MSIPC\UnmanagedTemplates

**서버 모드:** %allusersprofile%\Microsoft\MSIPC\Server\UnmanagedTemplates\*&lt;SID&gt;*

이 폴더를 사용하는 경우 RMS 서버 또는 서비스에서 템플릿을 발급해야 하고 템플릿 확장자가 .xml이어야 한다는 점을 제외하고 필요한 특별한 명명 규칙은 없습니다. 예를 들어 Contoso-Confidential.xml 또는 Contoso-ReadOnly.xml은 유효한 이름입니다.

## <a name="BKMK_UsingTrustedServers"></a>AD RMS만 해당: 신뢰할 수 있는 AD RMS 서버를 사용하도록 RMS 클라이언트 제한
RMS 클라이언트는 로컬 컴퓨터에서 Windows 레지스트리를 다음과 같이 변경하여 신뢰할 수 있는 특정 AD RMS 서버만 사용하도록 제한될 수 있습니다.

**신뢰할 수 있는 AD RMS 서버만 사용하도록 RMS 클라이언트를 제한하려면**

-   HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\TrustedServers\
    REG_DWORD: AllowTrustedServersOnly

    **Value:** 0이 아닌 값을 지정하는 경우 RMS 클라이언트는 TrustedServers 목록에 구성된 지정된 서버 및 Azure 권한 관리 서비스만 신뢰합니다.

**신뢰할 수 있는 AD RMS 서버 목록에 멤버를 추가하려면**

-   HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\TrustedServers\
    REG_SZ: *&lt;URL_or_HostName&gt;*

    **Value:** 이 레지스트리 키 위치에 추가된 문자열 값은 DNS 도메인 이름 형식(예: **adrms.contoso.com**) 또는 신뢰할 수 있는 AD RMS 서버에 대한 전체 URL(예: **https://adrms.contoso.com**)일 수 있습니다. 지정된 URL이 **https://**로 시작되면 RMS 클라이언트는 SSL 또는 TLS를 사용하여 지정된 AD RMS 서버에 연결합니다.

## <a name="BKMK_ServiceDiscovery"></a>RMS 서비스 검색
RMS 서비스 검색을 사용하여 RMS 클라이언트는 콘텐츠를 보호하기 전에 통신할 RMS 서버 또는 서비스를 확인할 수 있습니다. RMS 클라이언트가 보호된 콘텐츠를 사용할 때도 서비스 검색이 발생할 수 있지만, 콘텐츠에 연결된 정책에 기본 설정 RMS 서버 또는 서비스가 포함되어 있기 때문에 서비스 검색이 발생할 가능성은 낮으며, 이 검색이 실패하는 경우에만 클라이언트가 서비스 검색을 실행합니다.

서비스 검색은 먼저 온-프레미스 버전의 권한 관리(AD RMS)를 찾습니다. 검색이 실패하면 서비스 검색은 클라우드 버전의 권한 관리(Azure RMS)를 자동으로 찾습니다.

온-프레미스 배포에 대한 서비스 검색을 수행하기 위해 RMS 클라이언트는 다음 사항을 검사합니다.

1.  로컬 컴퓨터의 Windows 레지스트리: 레지스트리에 서비스 검색 설정이 구성된 경우 이러한 설정이 먼저 시도됩니다.  기본적으로 이러한 설정은 레지스트리에서 구성되지 않습니다.

2.  Active Directory 도메인 서비스: 도메인에 연결된 컴퓨터는 Active Directory에서 SCP(서비스 연결 지점)를 쿼리합니다. SCP가 등록되면 RMS 서버의 URL은 사용할 RMS 클라이언트로 반환됩니다.

### AD RMS만 해당: Active Directory를 사용하여 서버 쪽 서비스 검색 사용
계정에 충분한 권한(AD RMS 서버에 대한 엔터프라이즈 관리자 및 로컬 관리자)이 있으면 AD RMS 루트 클러스터 서버를 설치할 때 SCP(서비스 연결 지점)를 자동으로 등록할 수 있습니다. 포리스트에 SCP가 이미 있는 경우 새 SCP를 등록하기 전에 먼저 기존 SCP를 삭제해야 합니다.

다음 절차를 사용하여 AD RMS를 설치한 후 SCP를 등록하고 삭제할 수 있습니다. 시작하기 전에 사용자 계정에 필요한 권한(AD RMS 서버에 대한 엔터프라이즈 관리자 및 로컬 관리자)이 있는지 확인합니다.

##### Active Directory에서 SCP를 등록하여 AD RMS 서비스 검색을 사용하도록 설정하려면

1.  AD RMS 서버에서 Active Directory 관리 서비스 콘솔을 엽니다.

    -   Windows Server 2008 R2 또는 Windows Server 2008을 사용하는 경우 **시작**을 클릭하고 **관리 도구**를 클릭한 후 **Active Directory Rights Management Services**를 클릭합니다.

    -   Windows Server 2012 R2 또는 Windows Server 2012를 사용하는 경우 서버 관리자에서 **도구**를 클릭하고 **Active Directory Rights Management Services**를 클릭합니다.

2.  AD RMS 콘솔에서 AD RMS 클러스터를 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다.

3.  **SCP** 탭을 클릭합니다.

4.  **SCP 변경** 확인란을 선택합니다.

5.  **SCP를 현재 인증서 클러스터에 설정** 옵션을 선택한 다음 **확인**을 클릭합니다.

### Windows 레지스트리를 사용하여 클라이언트 쪽 서비스 검색 사용
SCP를 사용하는 대신에 또는 SCP가 없는 경우 RMS 클라이언트가 해당 AD RMS 서버를 찾을 수 있도록 클라이언트 컴퓨터에서 레지스트리를 구성할 수 있습니다.

##### Windows 레지스트리를 사용하여 클라이언트 쪽 AD RMS 서비스 검색을 사용하도록 설정하려면

1.  Windows 레지스트리 편집기 Regedit.exe를 엽니다.

    -   클라이언트 컴퓨터의 실행 창에 **regedit**를 입력하고 Enter 키를 눌러 레지스트리 편집기를 엽니다.

2.  레지스트리 편집기에서 **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC**로 이동합니다.

    > [!IMPORTANT]
    > 64비트 컴퓨터에는 32비트 응용 프로그램을 실행하는 경우 경로는 다음과 같습니다. 
    > **HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC**

3.  ServiceLocation 하위 키를 만들려면 **MSIPC**를 마우스 오른쪽 단추로 클릭하고 **새로 만들기**를 가리킨 후 **키**를 클릭하고 **ServiceLocation**을 입력합니다.

4.  EnterpriseCertification 하위 키를 만들려면 **ServiceLocation**을 마우스 오른쪽 단추로 클릭하고 **새로 만들기**를 가리킨 후 **키**를 클릭하고 **EnterpriseCertification**을 입력합니다.

5.  엔터프라이즈 인증 URL을 설정하려면 **EnterpriseCertification** 하위 키 아래에서 **(기본값)** 값을 두 번 클릭하고 **문자열 편집** 대화 상자가 나타나면 **값 데이터**에 대해 &lt;http or https&gt;://*AD RMS_cluster_name*/_wmcs/Certification을 입력하고 **확인**을 클릭합니다.

6.  EnterprisePublishing 하위 키를 만들려면 **ServiceLocation**을 마우스 오른쪽 단추로 클릭하고 **새로 만들기**를 가리킨 후 **키**를 클릭하고 EnterprisePublishing을 입력합니다.

7.  엔터프라이즈 게시 URL을 설정하려면 **EnterprisePublishing** 하위 키 아래에서 **(기본값)**을 두 번 클릭하고 **문자열 편집** 대화 상자가 나타나면 **값 데이터**에 대해 다음 &lt;http or https&gt;://*AD RMS_cluster_name*/_wmcs/Licensing을 입력하고 **확인**을 클릭합니다.

8.  레지스트리 편집기를 닫습니다.

RMS 클라이언트가 Active Directory를 쿼리하여 SCP를 찾을 수 없으며 레지스트리에 지정되지 않은 경우 AD RMS에 대한 서비스 검색 호출이 실패합니다.

### 라이선스 서버 트래픽 리디렉션
예를 들어 두 조직이 병합되고 한 조직의 이전 라이선스 서버가 더 이상 사용되지 않고 클라이언트가 새 라이선스 서버로 리디렉션되어야 할 경우 서비스 검색 중에 트래픽을 리디렉션해야 할 수도 있습니다. 또는 AD RMS에서 Azure RMS로 마이그레이션합니다. 라이선스 리디렉션을 사용하도록 설정하려면 다음 절차를 따릅니다.

##### Windows 레지스트리를 사용하여 RMS 라이선스 리디렉션을 사용하도록 설정하려면

1.  Windows 레지스트리 편집기 Regedit.exe를 엽니다.

    -   클라이언트 컴퓨터의 실행 창에 **regedit**를 입력하고 Enter 키를 눌러 레지스트리 편집기를 엽니다.

2.  레지스트리 편집기에서 다음 중 하나로 이동합니다.

    -   x64 플랫폼의 64비트 버전의 Office: HKLM\SOFTWARE\Microsoft\MSIPC\Servicelocation

    -   x64 플랫폼의 32비트 버전의 Office: HKLM\SOFTWARE\Wow6432Node\Microsoft\MSIPC\Servicelocation

3.  **Servicelocation**을 마우스 오른쪽 단추로 클릭하고 **새로 만들기**를 가리킨 후 **키**를 클릭하고 **LicensingRedirection**을 입력하여 LicensingRedirection 하위 키를 만듭니다.

4.  라이선스 리디렉션을 설정하려면 **LicensingRedirection** 하위 키를 마우스 오른쪽 단추로 클릭하고 **새로 만들기**를 선택한 다음 **문자열 값**을 선택합니다.**이름**에 이전 서버 라이선스 URL을 지정하고 **값**에 새 서버 라이선스 URL을 지정합니다.

    예를 들어 Contoso.com의 서버에서 Fabrikam.com의 서버로 라이선스를 리디렉션하려면 다음 값을 입력할 수 있습니다.

    **이름:** `https://contoso.com/_wmcs/licensing`

    **값:** `https://fabrikam.com/_wmcs/licensing`

    > [!NOTE]
    > 이전 라이선스 서버에 인트라넷 및 엑스트라넷 URL이 모두 지정되어 있으면 LicensingRedirection 키 아래에서 이러한 URL 둘 다에 대해 새로운 이름 및 값 매핑이 설정되어야 합니다.

5.  리디렉션되어야 하는 모든 서버에 대해 이전 단계를 반복합니다.

6.  레지스트리 편집기를 닫습니다.

