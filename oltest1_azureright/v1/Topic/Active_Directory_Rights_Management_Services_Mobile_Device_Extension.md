---
description: na
keywords: na
title: Active Directory Rights Management Services Mobile Device Extension
search: na
ms.date: na
ms.tgt_pltfrm: na
ms.assetid: a69ead9d-7dd3-4b38-9830-4728e9757341
robots: noindex,nofollow
---
# Active Directory Rights Management Services 모바일 장치 확장
AD RMS(Active Directory Rights Management Services) 모바일 장치 확장은 기존 AD RMS 배포를 기반으로 하여 실행됩니다. 장치에서 최신 RMS 클라이언트를 지원하고 RMS 지원 앱을 사용하는 경우 모바일 장치를 가진 사용자가 이 확장을 통해 중요한 데이터를 보호하고 사용할 수 있습니다. 예를 들어 이러한 장치의 사용자는 다음을 수행할 수 있습니다.

-   RMS 공유 앱을 통해 다양한 형식(.txt, .csv, .xml 등)의 보호된 텍스트 파일을 사용합니다.

-   RMS 공유 앱을 통해 보호된 이미지 파일(.jpg, .gif, .tif 등)을 사용합니다.

-   RMS 공유 앱을 통해 일반적으로 보호된 파일(.pfile 형식)을 엽니다.

-   RMS 공유 앱을 통해 장치의 이미지 파일을 보호합니다.

-   모바일 장치용 RMS 지원 PDF 뷰어를 사용하여 Windows용 RMS 공유 응용 프로그램이나 다른 RMS 지원 응용 프로그램으로 보호된 PDF 파일을 엽니다.

-   기본적으로 RMS를 지원하는 파일 형식을 지원하는 RMS 지원 앱을 제공하는 소프트웨어 공급업체의 다른 앱을 사용합니다.

-   RMS SDK로 작성된 내부에서 개발한 RMS 지원 앱을 사용합니다.

> [!NOTE]
> Microsoft 웹 사이트의 [Microsoft Rights Management](http://go.microsoft.com/fwlink/?LinkId=303970) 페이지에서 RMS 공유 앱을 다운로드할 수 있습니다.
> 
> RMS에서 지원하는 다양한 파일 형식에 대한 자세한 내용은 Rights Management 공유 응용 프로그램 관리자 가이드의 [지원되는 파일 형식 및 파일 이름 확장명](http://technet.microsoft.com/library/dn339003.aspx) 섹션을 참조하세요.

장치에서 Exchange ActiveSync IRM을 지원하는 메일 응용 프로그램을 사용하는 경우 모바일 장치 확장이 없어도 보호된 메일을 사용하거나 작성할 수 있습니다. 이러한 RMS 및 모바일 장치에 대한 기본 지원은 Exchange 2010 서비스 팩 1에서 도입되었습니다.

다음 섹션을 사용하여 AD RMS(Active Directory Rights Management Services) 모바일 장치 확장을 배포합니다.

-   [AD RMS 모바일 장치 확장에 대한 필수 조건](../Topic/Active_Directory_Rights_Management_Services_Mobile_Device_Extension.md#BKMK_Preqs)

    -   [AD RMS 모바일 장치 확장에 대해 AD FS 구성](../Topic/Active_Directory_Rights_Management_Services_Mobile_Device_Extension.md#BKMK_ADFS)

    -   [AD RMS 모바일 장치 확장에 대해 AD FS 구성](../Topic/Active_Directory_Rights_Management_Services_Mobile_Device_Extension.md#BKMK_ADFS)

-   [AD RMS 모바일 장치 확장에 대한 DNS SRV 레코드 지정](../Topic/Active_Directory_Rights_Management_Services_Mobile_Device_Extension.md#BKMK_SRV)

-   [AD RMS 모바일 장치 확장 배포](../Topic/Active_Directory_Rights_Management_Services_Mobile_Device_Extension.md#BKMK_Deploy)

## <a name="BKMK_Preqs"></a>AD RMS 모바일 장치 확장에 대한 필수 조건
AD RMS 모바일 장치 확장을 설치하기 전에 이러한 종속성이 구현되어 있는지 확인합니다.

|요구 사항|추가 정보|
|---------|---------|
|Windows Server 2012 R2 또는 Windows Server 2012의 기존 AD RMS 배포 **Note:** AD RMS는 동일한 서버의 테스트에 자주 사용되는 Windows 내부 데이터베이스가 아니라 별도의 서버에 있는 전체 Microsoft SQL Server 기반 데이터베이스를 사용해야 합니다.|AD RMS에 대한 설명서는 Windows Server 라이브러리의 [Active Directory Rights Management Services](http://technet.microsoft.com/library/hh831364.aspx)를 참조하세요.|
|Windows Server 2012 R2에 배포된 AD FS|AD FS에 대한 설명서는 Windows Server 라이브러리의 [Windows Server 2012 R2 AD FS 배포 가이드](http://technet.microsoft.com/library/dn486820.aspx)를 참조하세요.<br /><br />모바일 장치 확장에 대해 AD FS를 구성해야 합니다. 지침은 이 항목의 [AD RMS 모바일 장치 확장에 대해 AD FS 구성](../Topic/Active_Directory_Rights_Management_Services_Mobile_Device_Extension.md#BKMK_ADFS) 섹션을 참조하세요.|
|DNS의 SRV 레코드|회사 도메인에 SRV 레코드를 하나 이상 만듭니다.<br /><br />-   사용자가 사용하는 각 메일 도메인 접미사에 대해 레코드 하나씩<br />-   RMS 클러스터에서 콘텐츠를 보호하는 데 사용하는 각 FQDN에 대해 레코드 하나씩<br /><br />사용자가 모바일 장치에서 메일 주소를 제공하는 경우 AD RMS 인프라 또는 Azure RMS를 사용해야 하는지를 식별하기 위해 도메인 접미사를 사용합니다. SRV 레코드가 발견되면 클라이언트가 해당 URL에 응답하는 AD RMS 서버로 리디렉션됩니다.<br /><br />사용자가 모바일 장치에서 보호된 콘텐츠를 사용하는 경우 클라이언트 응용 프로그램은 DNS에서 콘텐츠를 보호한 클러스터의 URL에 있는 FQDN과 일치하는 레코드를 찾습니다. 그런 다음 장치가 DNS 레코드에 지정된 AD RMS 클러스터로 보내지고 라이선스를 획득하여 콘텐츠를 엽니다. 대부분의 경우 RMS 클러스터는 콘텐츠를 보호한 RMS 클러스터와 같습니다.<br /><br />SRV 레코드를 지정하는 방법에 대한 자세한 내용은 이 항목의 [AD RMS 모바일 장치 확장에 대한 DNS SRV 레코드 지정](../Topic/Active_Directory_Rights_Management_Services_Mobile_Device_Extension.md#BKMK_SRV) 섹션을 참조하세요.|
|현재 지원되는 클라이언트:<br /><br />-   최신 버전의 Android용 RMS 공유 앱을 사용하는 Android 장치|최소 버전 Android 4.0.3.<br /><br />Android용 RMS 공유 앱을 [Microsoft Connect 사이트](https://connect.microsoft.com/site1170/Downloads) 에서 다운로드하고 테스트용으로 장치에 로드합니다.|

### <a name="BKMK_ADFS"></a>AD RMS 모바일 장치 확장에 대해 AD FS 구성
먼저 AD FS를 구성한 다음 Android용 RMS 공유 앱에 권한을 부여해야 합니다.

##### 1단계: AD FS 구성

-   Windows PowerShell 스크립트를 실행하여 AD RMS 모바일 장치 확장을 지원하도록 AD FS를 자동으로 구성하거나 구성 옵션 및 값을 수동으로 지정할 수 있습니다.

    -   AD FS를 자동으로 구성하려면 다음 내용을 복사하여 Windows PowerShell 스크립트 파일에 붙여 넣고 실행합니다.

        ```
        # This Script Configures the Microsoft Rights Management Mobile Device Extension and Claims used in the ADFS Server

        # Check if Microsoft Rights Management Mobile Device Extension is configured on the Server 
        $CheckifConfigured = Get-AdfsRelyingPartyTrust -Identifier "api.rms.rest.com"
        if ($CheckifConfigured)
        {
        Write-Host "api.rms.rest.com Identifer used for Microsoft Rights Management Mobile Device Extension is already configured on this Server"
        Write-Host $CheckifConfigured 
        }
        else
        {
        Write-Host "Configuring  Microsoft Rights Management Mobile Device Extension "

        # TransformaRules used by Microsoft Rights Management Mobile Device Extension
        # Claims: E-mail, UPN and ProxyAddresses
        $TransformRules = @"
        @RuleTemplate = "LdapClaims"
        @RuleName = "Jwt Token"
        c:[Type ==
        "http://schemas.microsoft.com/ws/2008/06/identity/claims/windowsaccountname",
        Issuer == "AD AUTHORITY"]
         => issue(store = "Active Directory", types =
        ("http://schemas.xmlsoap.org/ws/2005/05/identity/claims/emailaddress",
        "http://schemas.xmlsoap.org/ws/2005/05/identity/claims/upn",
        "http://schemas.xmlsoap.org/claims/ProxyAddresses"), query =
        ";mail,userPrincipalName,proxyAddresses;{0}", param = c.Value);

        @RuleTemplate = "PassThroughClaims"
        @RuleName = "JWT pass through"
        c:[Type == "http://schemas.xmlsoap.org/ws/2005/05/identity/claims/emailaddress"]
         => issue(claim = c);

        @RuleTemplate = "PassThroughClaims"
        @RuleName = "JWT pass through"
        c:[Type == "http://schemas.xmlsoap.org/ws/2005/05/identity/claims/upn"]
         => issue(claim = c);

        @RuleTemplate = "PassThroughClaims"
        @RuleName = "JWT pass through Proxy addresses"
        c:[Type == "http://schemas.xmlsoap.org/claims/ProxyAddresses"]
         => issue(claim = c);
        "@

        # AuthorizationRules used by Microsoft Rights Management Mobile Device Extension
        # Allow All users
        $AuthorizationRules = @"
        @RuleTemplate = "AllowAllAuthzRule"
         => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit",
        Value = "true");
        "@

        # Add a Relying Part Truest with Name -"Microsoft Rights Management Mobile Device Extension" Identifier "api.rms.rest.com"
        Add-ADFSRelyingPartyTrust -Name "Microsoft Rights Management Mobile Device Extension" -Identifier "api.rms.rest.com" -IssuanceTransformRules $TransformRules -IssuanceAuthorizationRules  $AuthorizationRules

        Write-Host "Microsoft Rights Management Mobile Device Extension Configured"
        }
        ```

    -   AD FS를 수동으로 구성하려면 다음 설정을 사용합니다.

        |구성|Value|
        |------|---------|
        |**신뢰 당사자 트러스트**|api.rms.rest.com|
        |**클레임 규칙**|**특성 저장소**:  Active Directory<br /><br />**메일 주소**:  E-Mail-Address<br /><br />**사용자 보안 주체 이름**:  UPN<br /><br />**프록시 주소**:  https://schemas.xmlsoap.org/claims/ProxyAddresses|

##### 2단계: Android용 RMS 공유 앱에 권한 부여

-   Android 장치에 대한 지원을 추가하려면 다음 Windows PowerShell 명령을 실행합니다.

    ```
    Add-AdfsClient -Name "RMSsharingAndroid" -ClientId "com.microsoft.ipviewer" -RedirectUri @("com.microsoft.ipviewer://authorize")
    ```

### <a name="BKMK_SRV"></a>AD RMS 모바일 장치 확장에 대한 DNS SRV 레코드 지정
사용자가 사용하는 각 메일 도메인에 대한 DNS SRV 레코드를 만들어야 합니다. 모든 사용자가 단일 상위 도메인의 하위 도메인을 사용하며 이 연속 네임스페이스의 모든 사용자가 동일한 RMS 클러스터를 사용하는 경우 상위 도메인의 SRV 레코드를 하나만 사용하면 RMS에서 해당 DNS 레코드를 찾을 수 있습니다.

SRV 레코드는 다음 형식을 사용합니다. _rmsdisco._http._tcp. *&lt;emailsuffix&gt;**&lt;portnumber&gt;**&lt;RMSClusterFQDN&gt;*

예를 들어 조직에 메일 주소가

-   user@contoso.com

-   user@sales.contoso.com

-   user@fabrikam.com

인 사용자가 있고 **rmsserver.contoso.com** 클러스터가 아닌 다른 RMS 클러스터를 사용하는 contoso.com의 다른 하위 도메인이 없는 경우 다음 값을 가진 DNS SRV 레코드 2개를 만듭니다.

-   _rmsdisco._http._tcp.contoso.com 443 rmsserver.contoso.com

-   _rmsdisco._http._tcp.fabrikam.com 443 rmsserver.contoso.com

메일 도메인에 대한 이러한 DNS SRV 레코드 외에도 사용자 도메인에 다른 DNS SRV 레코드를 만들어야 합니다. 이 레코드는 콘텐츠를 보호하는 RMS 클러스터의 URL을 지정해야 합니다. RMS로 보호된 각 파일에 해당 파일을 보호한 클러스터의 URL이 포함됩니다. 모바일 장치는 DNS SRV 레코드와 레코드에 지정된 URL FQDN을 사용하여 모바일 장치를 지원할 수 있는 해당 RMS 클러스터를 찾습니다.

예를 들어 RMS 클러스터가 **rmsserver.contoso.com**이면 다음 값을 가진 DNS SRV 레코드를 만듭니다. **_rmsdisco._http._tcp.rmsserver.contoso.com 443 rmsserver.contoso.com**

## <a name="BKMK_Deploy"></a>AD RMS 모바일 장치 확장 배포
AD RMS 모바일 장치 확장을 설치하기 전에 이전 섹션의 필수 조건이 먼저 구현되어 있고 AD FS 서버의 URL을 알고 있어야 합니다. 그런 후에 다음을 수행합니다.

1.  AD RMS 모바일 장치 확장을 [Microsoft Connect 사이트](http://go.microsoft.com/fwlink/?LinkId=397245)에서 다운로드합니다.

2.  Setup.exe를 실행하여 Active Directory Rights Management Services 모바일 장치 확장 설치 마법사를 시작합니다.

3.  메시지가 표시되면 이전에 구성한 AD FS 서버의 URL을 입력합니다.

4.  마법사를 완료합니다.

RMS 클러스터의 모든 노드에서 이 마법사를 실행합니다.

