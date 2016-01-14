---
description: na
keywords: na
title: Configuring Applications for Azure Rights Management
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: ea09cbc5-b98b-444e-8b60-5bc3cb199c36
---
# Azure 권한 관리용 응용 프로그램 구성
> [!NOTE]
> 이 정보는 Azure Rights Management를 배포한 IT 관리자 및 컨설턴트를 대상으로 합니다. 특정 응용 프로그램용 권한 관리를 사용하는 방법이나 권한으로 보호된 파일을 여는 방법에 대한 정보와 사용자 도움말을 원하는 경우 응용 프로그램을 함께 제공되는 지침 및 도움말을 사용하세요.
> 
> 예를 들어 Office 응용 프로그램의 경우 도움말 아이콘을 클릭하고 **Rights Management** 또는 **IRM**과 같은 검색 용어를 입력합니다. Windows용 RMS 공유 응용 프로그램에 대해서는 [Rights Management 공유 응용 프로그램 사용자 가이드](http://technet.microsoft.com/library/dn339006.aspx)(영문)를 참조하세요.

조직에 대해 Azure RMS(Azure 권한 관리)가 있는 경우 다음 정보를 사용하여 Azure RMS를 지원하도록 응용 프로그램 및 서비스를 구성하세요. 여기에는 Word 2013 및 Word 2010과 같은 Office 응용 프로그램, Exchange Online(전송 규칙, 데이터 손실 방지, 전달 금지 및 메시지 암호화) 및 SharePoint Online(보호된 라이브러리)과 같은 서비스가 포함됩니다. 이러한 응용 프로그램 및 서비스가 권한 관리를 지원하는 방법에 대한 자세한 내용은 [응용 프로그램이 Azure 권한 관리를 지원하는 방식](../Topic/How_Applications_Support_Azure_Rights_Management.md)을 참조하세요.

> [!IMPORTANT]
> 지원되는 버전 및 기타 요구 사항에 대한 자세한 내용은 [Azure 권한 관리 요구 사항](../Topic/Requirements_for_Azure_Rights_Management.md)을 참조하세요.

-   [Office 365: 클라이언트 및 온라인 서비스 구성](../Topic/Configuring_Applications_for_Azure_Rights_Management.md#BKMK_O365)

    -   [Exchange Online: IRM 구성](../Topic/Configuring_Applications_for_Azure_Rights_Management.md#BKMK_ExchangeOnline)

    -   [SharePoint Online 및 비즈니스용 OneDrive: IRM 구성](#BKMK_SharePointOnline)

-   [Office 2016 및 Office 2013: 클라이언트 구성](#BKMK_Office2013Configuration)

-   [Office 2010: 클라이언트 구성](../Topic/Configuring_Applications_for_Azure_Rights_Management.md#BKMK_Office2010Configuration)

-   [Rights Management 공유 응용 프로그램: 클라이언트 설치 및 구성](../Topic/Configuring_Applications_for_Azure_Rights_Management.md#BKMK_SharingApp)

    -   [Windows용 RMS 공유 응용 프로그램: 설치 및 구성](../Topic/Configuring_Applications_for_Azure_Rights_Management.md#BKMK_SharingAppforWindows)

    -   [모바일 플랫폼용 RMS 공유 응용 프로그램: 설치](../Topic/Configuring_Applications_for_Azure_Rights_Management.md#BKMK_SharingAppMovileDevices)

-   [RMS API를 지원하는 기타 응용 프로그램: 설치 및 구성](../Topic/Configuring_Applications_for_Azure_Rights_Management.md#BKMK_RMSAPIs)

온-프레미스 서버(예: Exchange Server 및 SharePoint Server)를 구성하려면 [Azure 권한 관리 커넥터 배포](../Topic/Deploying_the_Azure_Rights_Management_Connector.md)를 참조하세요.

> [!TIP]
> Azure RMS를 사용하도록 구성된 응용 프로그램에 대한 자세한 예와 스크린샷을 보려면 [Azure 권한 관리란?](../Topic/What_is_Azure_Rights_Management_.md) 항목의 [Azure RMS 실행: 관리자와 사용자에게 표시되는 내용](../Topic/What_is_Azure_Rights_Management_.md#BKMK_RMSpictures) 섹션을 참조하세요.

## <a name="BKMK_O365"></a>Office 365: 클라이언트 및 온라인 서비스 구성
Office 365는 기본적으로 Azure RMS를 지원하므로 Word, Excel, PowerPoint, Outlook 및 Outlook Web App과 같은 응용 프로그램에 대해 IRM(정보 권한 관리) 기능을 지원하기 위해 클라이언트 컴퓨터를 구성할 필요가 없습니다. 사용자는 [!INCLUDE[o365_1](../Token/o365_1_md.md)] 자격 증명을 사용하여 Office 응용 프로그램에 로그인하기만 하면 되며, 로그인하면 파일과 메일을 보호하고 다른 사용자가 보호한 파일과 메일을 사용할 수 있습니다.

그러나 사용자가 Office 추가 기능의 이점을 얻을 수 있도록 권한 관리 공유 응용 프로그램으로 이러한 응용 프로그램을 보완하는 것이 좋습니다. 자세한 내용은 이 항목의 [Rights Management 공유 응용 프로그램: 클라이언트 설치 및 구성](../Topic/Configuring_Applications_for_Azure_Rights_Management.md#BKMK_SharingApp) 섹션을 참조하세요.

### <a name="BKMK_ExchangeOnline"></a>Exchange Online: IRM 구성
Azure RMS를 지원하도록 Exchange Online을 구성하려면 Exchange Online에 대해 IRM(정보 권한 관리) 서비스를 구성해야 합니다. 이렇게 하려면 Windows PowerShell(별도 모듈을 설치할 필요 없음)을 사용하고 [Exchange Online PowerShell 명령](https://technet.microsoft.com/library/jj200677.aspx)을 실행합니다.

> [!NOTE]
> 현재 Azure RMS에 대해 Microsoft에서 관리하는 테넌트 키의 기본 구성이 아니라 고객이 관리하는 테넌트 키(BYOK)를 사용하는 경우 Azure RMS를 지원하도록 Exchange Online을 구성할 수 없습니다. 자세한 내용은 [Azure 권한 관리 테넌트 키 계획 및 구현](../Topic/Planning_and_Implementing_Your_Azure_Rights_Management_Tenant_Key.md) 항목의 [BYOK 가격 및 제한 사항](../Topic/Planning_and_Implementing_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_Pricing) 섹션을 참조하세요.
> 
> Azure RMS가 BYOK를 사용하는 경우 Exchange Online을 구성하려고 하면 키를 가져오는 명령(다음 절차의 5단계)이 오류 메시지 **[FailureCategory=Cmdlet-FailedToGetTrustedPublishingDomainFromRmsOnlineException]**과 함께 실패합니다.

다음 단계에서는 Exchange Online에서 Azure RMS를 사용하도록 하기 위해 실행하는 일반적인 명령 집합을 제공합니다.

1.  컴퓨터에서 Exchange Online에 대해 Windows PowerShell을 처음 사용하는 경우에는 서명된 스크립트를 실행하도록 Windows PowerShell을 구성해야 합니다.**관리자 권한으로 실행** 옵션을 사용하여 Windows PowerShell 세션을 시작한 후 다음을 입력합니다.

    ```
    Set-ExecutionPolicy RemoteSigned
    ```

2.  Windows PowerShell 세션에서 원격 셸 액세스에 대해 사용하도록 설정된 계정을 사용하여 Exchange Online으로 로그인합니다. 기본적으로 Exchange Online에서 만든 모든 계정은 원격 셸 액세스에 사용하도록 설정되지만, [Set-User &lt;UserIdentity&gt; -RemotePowerShellEnabled](https://technet.microsoft.com/library/jj984292%28v=exchg.160%29.aspx) 명령을 이용해 사용하지 않도록 설정(및 사용하도록 설정)할 수 있습니다.

    로그인하려면 다음을 입력합니다.

    ```
    $Cred = Get-Credential
    ```
    **Windows PowerShell 자격 증명 요청** 대화 상자에 Office 365 사용자 이름과 암호를 제공합니다.

3.  다음 두 명령을 실행하여 Exchange Online 서비스에 연결합니다.

    ```
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell/ -Credential $Cred -Authentication Basic –AllowRedirection
    ```

    ```
    Import-PSSession $Session
    ```

4.  사용자의 지역에 따라 Azure RMS 테넌트 키의 위치를 지정합니다.

    북아메리카(및 정부 구독)의 경우:

    ```
    Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
    ```
    유럽의 경우:

    ```
    Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc"
    ```
    아시아의 경우:

    ```
    Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc"
    ```
    남아메리카의 경우:

    ```
    Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc"
    ```

5.  TPD(신뢰할 수 있는 게시 도메인)의 형태로 Azure RMS에서 Exchange Online으로 구성 데이터를 가져옵니다. 여기에는 Azure RMS 테넌트 키와 Azure RMS 템플릿이 포함됩니다.

    ```
    Import-RMSTrustedPublishingDomain -RMSOnline -name "RMS Online"
    ```
    이 명령에서는 Exchange Online의 Azure RMS에 대한 TPD의 기본 이름으로 **RMS 온라인**의 이름을 사용했습니다. TPD를 가져오면 Exchange Online에서 **RMS Online - 1**로 이름이 지정됩니다.

6.  Exchange Online에서 IRM 기능을 사용할 수 있도록 Azure RMS 기능을 사용하도록 설정합니다.

    ```
    Set-IRMConfiguration -InternalLicensingEnabled $true
    ```
    이 명령을 실행한 후 Outlook 클라이언트, Outlook Web App, Exchange Active Sync에 대해 권한 관리가 자동으로 사용되도록 설정됩니다.

7.  필요에 따라 다음 명령을 사용하여 이 구성을 성공적으로 수행되었는지 테스트합니다.

    ```
    Test-IRMConfiguration -Sender <user email address>
    ```
    예를 들면 다음과 같습니다. **Test-IRMConfiguration -Sender  adams@contoso.com**

    이 명령은 서비스에 대한 연결 확인, 구성 검색, URL, 라이선스 및 템플릿 검색을 포함하는 일련의 검사를 실행합니다. Windows PowerShell 세션에 각 검사의 결과가 표시되며 이러한 모든 검사를 통과하면 맨 마지막에 다음 결과가 표시됩니다. **OVERALL RESULT: PASS**

8.  원격 PowerShell 세션 연결 끊기:

    ```
    Remove-PSSession $Session
    ```

이제 사용자는 Azure RMS를 사용하여 자신의 전자 메일 메시지를 보호할 수 있습니다. 예를 들어 Outlook Web App의 확장된 메뉴(**...**)에서 **사용 권한 설정**을 선택한 다음 **전달 금지**를 선택하거나 전자 메일 메시지 및 첨부 파일에 정보 보호를 적용할 사용 가능한 템플릿 중 하나를 선택합니다. 그러나 Outlook Web App은 하루 동안 UI를 캐시하므로, 이러한 구성 명령을 실행하고 하루 동안 기다렸다가 전자 메일 메시지에 정보 보호를 적용합니다. 새 구성을 반영하도록 UI가 업데이트되기 전에는 **사용 권한 설정** 메뉴의 옵션이 표시되지 않습니다.

> [!IMPORTANT]
> Azure RMS용 [사용자 지정 템플릿](https://technet.microsoft.com/library/dn642472.aspx)을 새로 만들거나 템플릿을 업데이트하는 경우 매번 다음 Exchange Online PowerShell 명령을 실행(필요한 경우 2~3단계 먼저 실행)하여 이러한 변경 사항을 Exchange Online과 동기화해야 합니다. `Import-RMSTrustedPublishingDomain -Name "RMS Online - 1" -RefreshTemplates –RMSOnline`

Exchange 관리자는 이제 [전송 규칙](https://technet.microsoft.com/library/dd302432.aspx), [DLP(데이터 손실 방지) 정책](https://technet.microsoft.com/library/jj150527%28v=exchg.150%29.aspx) 및 [보호된 음성 메일](https://technet.microsoft.com/library/dn198211%28v=exchg.150%29.aspx)(통합 메시징)과 같이 정보 보호를 자동으로 적용하는 기능을 구성할 수 있습니다.

IRM 기능을 사용하도록 Exchange Online을 구성하는 방법에 대한 자세한 내용은 Exchange 라이브러리의 문서를 참조하세요. 예를 들면 다음과 같습니다.

-   [원격 PowerShell을 사용하여 Exchange Online에 연결](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx)

-   [Azure 권한 관리를 사용하도록 IRM 구성](https://technet.microsoft.com/library/dn151475%28v=exchg.150%29.aspx)

#### Office 365 메시지 암호화
이전 섹션에 설명된 동일한 단계를 실행합니다. 그렇지만 템플릿을 표시하지 않으려면 6단계 이전에 다음 명령을 실행하여 Outlook Web App 및 Outlook 클라이언트에서 IRM 템플릿을 사용할 수 없게 합니다. `Set-IRMConfiguration -ClientAccessServerEnabled $false`

그런 후에 받는 사람이 조직 외부에 있고 **Office 365 메시지 암호화 적용** 옵션을 선택한 경우 메시지 보안을 자동으로 수정하도록 [전송 규칙](https://technet.microsoft.com/library/dd302432.aspx)을 구성할 수 있습니다.

메시지 암호화에 대한 자세한 내용은 Exchange 라이브러리의 [Office 365의 암호화](https://technet.microsoft.com/library/dn569286.aspx)를 참조하세요.

### <a name="BKMK_SharePointOnline"></a>SharePoint Online 및 비즈니스용 OneDrive: IRM 구성
Azure RMS를 지원하도록 SharePoint Online 및 비즈니스용 OneDrive를 구성하려면 먼저 SharePoint 관리 센터를 통해 SharePoint Online에 대해 IRM(정보 권한 관리) 서비스가 사용되도록 해야 합니다. 그러면 사이트 소유자는 SharePoint 목록 및 문서 라이브러리를 IRM으로 보호할 수 있으며, 사용자는 비즈니스용 OneDrive 라이브러리를 IRM으로 보호하여 해당 라이브러리에 저장된 문서와 다른 사람과 공유하는 문서가 Azure RMS를 통해 자동으로 보호되도록 할 수 있습니다.

SharePoint Online에 대한 IRM(정보 권한 관리) 서비스를 사용하도록 설정하려면 Office 웹 사이트의 다음 지침을 참조하세요.

-   [SharePoint 관리 센터의 IRM(정보 권한 관리) 설정](http://office.microsoft.com/office365-sharepoint-online-enterprise-help/set-up-information-rights-management-irm-insharepoint-online-HA102895193.aspx)

이 구성은 Office 365 관리자가 수행합니다.

#### 라이브러리 및 목록에 대한 IRM 구성
SharePoint용 IRM 서비스를 사용하도록 설정하면 사이트 소유자는 SharePoint 문서 라이브러리 및 목록을 IRM으로 보호할 수 있습니다. 지침을 보려면 Office 웹 사이트의 다음 리소스를 참조하세요.

-   [목록이나 라이브러리에 정보 권한 관리 적용](http://office.microsoft.com/sharepoint-help/apply-information-rights-management-to-a-list-or-library-HA102891460.aspx)

이 구성은 SharePoint 사이트 관리자가 수행합니다.

#### <a name="BKMK_OneDrive"></a>비즈니스용 OneDrive에 대한 IRM 구성
SharePoint Online용 IRM 서비스를 사용하도록 설정하면 사용자의 비즈니스용 OneDrive 문서 라이브러리에서 권한 관리 보호에 대해 구성할 수 있습니다.  사용자는 각각의 OneDrive에서 **설정** 아이콘을 이용해 이 기능을 스스로 구성할 수 있습니다. 관리자가 SharePoint 관리 센터를 이용해 사용자의 비즈니스용 OneDrive에 대한 권한 관리를 구성할 수는 없지만, Windows PowerShell을 이용해 구성할 수는 있습니다.

> [!NOTE]
> 비즈니스용 OneDrive를 구성하는 방법에 대한 자세한 내용은 Office 설명서, [Office 365에서 비즈니스용 OneDrive 설정](https://support.office.com/article/Set-up-OneDrive-for-Business-in-Office-365-3e21f8f0-e0a1-43be-aa3e-8c0236bf11bb)을 참조하세요.

##### 사용자를 위한 구성
사용자가 각각의 비즈니스용 OneDrive와 IRM으로 보호되는 비즈니스 파일을 구성할 수 있도록 사용자에게 이러한 지침을 제공합니다.

1.  OneDrive에서 **설정** 아이콘을 클릭하여 설정 메뉴를 열고 **사이트 콘텐츠**를 클릭합니다.

2.  **문서** 타일 위로 마우스를 가져간 후 줄임표(**...**)를 선택하고 **설정**을 클릭합니다.

3.  **설정** 페이지의 **사용 권한 및 관리** 섹션에서 **정보 권한 관리**를 클릭합니다.

4.  **정보 권한 관리 설정** 페이지에서 **다운로드에 대한 이 라이브러리의 권한 제한** 확인란을 선택하고 권한에 대한 이름 및 설명을 지정한 후 필요에 따라 **옵션 표시**를 클릭하여 선택적 구성을 지정하고 **확인**을 클릭합니다.

    구성 옵션에 대한 자세한 내용은 Office 설명서에서 [목록이나 라이브러리에 정보 권한 관리 적용](https://support.office.com/article/Apply-Information-Rights-Management-to-a-list-or-library-3bdb5c4e-94fc-4741-b02f-4e7cc3c54aa1)의 지침을 참조하세요.

이 구성에서 관리자가 아닌 사용자는 비즈니스용 OneDrive 라이브러리를 IRM으로 보호해야 하므로 파일을 보호할 때의 이점과 보호 방법을 사용자에게 교육합니다. 예를 들어 비즈니스용 OneDrive에서 문서를 공유하는 경우 파일 이름을 바꾸고 다른 위치로 복사하더라도 권한을 받은 사람만 구성된 제한에 따라 문서에 액세스할 수 있습니다.

##### 관리자를 위한 구성
관리자가 SharePoint 관리 센터를 이용해 사용자의 비즈니스용 OneDrive에 대한 IRM을 구성할 수는 없지만, Windows PowerShell을 이용해 구성할 수는 있습니다. 이러한 라이브러리에 대한 IRM을 사용하도록 설정하려면 다음 단계를 수행합니다.

1.  [SharePoint Online 클라이언트 구성 요소 SDK](http://www.microsoft.com/en-us/download/details.aspx?id=42038)를 다운로드하여 설치합니다.

2.  [SharePoint Online 관리 셸](http://www.microsoft.com/en-us/download/details.aspx?id=35588)을 다운로드하여 설치합니다.

3.  다음 스크립트의 콘텐츠를 복사하고 컴퓨터에 Set-IRMOnOneDriveForBusiness.ps1 파일의 이름을 지정합니다.

    *&#42;&#42;고지 사항&#42;&#42;*: 이 샘플 스크립트는 Microsoft 표준 지원 프로그램 또는 서비스를 통해 지원되지 않습니다. 이 샘플 스크립트는 어떤 종류의 보증도 없이 있는 그대로 제공됩니다.

    ```
    # Requires Windows PowerShell version 3 <# Description: Configures IRM policy settings for OneDrive for Business and can also be used for SharePoint Online libraries and lists Script Installation Requirements: SharePoint Online Client Components SDK http://www.microsoft.com/en-us/download/details.aspx?id=42038 SharePoint Online Management Shell http://www.microsoft.com/en-us/download/details.aspx?id=35588 ====== #> # URL will be in the format https://<tenant-name>-admin.sharepoint.com $sharepointAdminCenterUrl = "https://contoso-admin.sharepoint.com" $tenantAdmin = "admin@contoso.com" $webUrls = @("https://contoso-my.sharepoint.com/personal/user1_contoso_com", "https://contoso-my.sharepoint.com/personal/user2_contoso_com", "https://contoso-my.sharepoint.com/personal/user3_contoso_com") <# As an alternative to specifying the URLs as an array, you can import them from a CSV file (no header, single value per row). Then, use: $webUrls = Get-Content -Path "File_path_and_name.csv" #> $listTitle = "Documents" function Load-SharePointOnlineClientComponentAssemblies { [cmdletbinding()] param() process { # assembly location: C:\Program Files\Common Files\microsoft shared\Web Server Extensions\16\ISAPI try { Write-Verbose "Loading Assembly: Microsoft.Office.Client.Policy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.Office.Client.Policy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.Office.Client.TranslationServices, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.Office.Client.TranslationServices, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.DocumentManagement, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.DocumentManagement, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Publishing, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Publishing, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Runtime, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Runtime, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Search.Applications, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Search.Applications, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Search, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Search, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Taxonomy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Taxonomy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.UserProfiles, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.UserProfiles, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null return $true } catch { if($_.Exception.Message -match "Could not load file or assembly") { Write-Error -Message "Unable to load the SharePoint Server 2013 Client Components.`nDownload Location: http://www.microsoft.com/en-us/download/details.aspx?id=42038" } else { Write-Error -Exception $_.Exception } return $false } } } function Load-SharePointOnlineModule { [cmdletbinding()] param() process { do { # Installation location: C:\Program Files\SharePoint Online Management Shell\Microsoft.Online.SharePoint.PowerShell $spoModule = Get-Module -Name Microsoft.Online.SharePoint.PowerShell -ErrorAction SilentlyContinue if(-not $spoModule) { try { Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking return $true } catch { if($_.Exception.Message -match "Could not load file or assembly") { Write-Error -Message "Unable to load the SharePoint Online Management Shell.`nDownload Location: http://www.microsoft.com/en-us/download/details.aspx?id=35588" } else { Write-Error -Exception $_.Exception } return $false } } else { return $true } } while(-not $spoModule) } } function Set-IrmConfiguration { [cmdletbinding()] param( [parameter(Mandatory=$true)][Microsoft.SharePoint.Client.List]$List, [parameter(Mandatory=$true)][string]$PolicyTitle, [parameter(Mandatory=$true)][string]$PolicyDescription, [parameter(Mandatory=$false)][switch]$IrmReject, [parameter(Mandatory=$false)][DateTime]$ProtectionExpirationDate, [parameter(Mandatory=$false)][switch]$DisableDocumentBrowserView, [parameter(Mandatory=$false)][switch]$AllowPrint, [parameter(Mandatory=$false)][switch]$AllowScript, [parameter(Mandatory=$false)][switch]$AllowWriteCopy, [parameter(Mandatory=$false)][int]$DocumentAccessExpireDays, [parameter(Mandatory=$false)][int]$LicenseCacheExpireDays, [parameter(Mandatory=$false)][string]$GroupName ) process { Write-Verbose "Applying IRM Configuration on '$($List.Title)'" # reset the value to the default settings $list.InformationRightsManagementSettings.Reset() $list.IrmEnabled = $true # IRM Policy title and description $list.InformationRightsManagementSettings.PolicyTitle       = $PolicyTitle $list.InformationRightsManagementSettings.PolicyDescription = $PolicyDescription # Set additional IRM library settings # Do not allow users to upload documents that do not support IRM $list.IrmReject = $IrmReject.IsPresent $parsedDate = Get-Date if([DateTime]::TryParse($ProtectionExpirationDate, [ref]$parsedDate)) { # Stop restricting access to the library at <date> $list.IrmExpire = $true $list.InformationRightsManagementSettings.DocumentLibraryProtectionExpireDate = $ProtectionExpirationDate } # Prevent opening documents in the browser for this Document Library $list.InformationRightsManagementSettings.DisableDocumentBrowserView = $DisableDocumentBrowserView.IsPresent # Configure document access rights # Allow viewers to print $list.InformationRightsManagementSettings.AllowPrint = $AllowPrint.IsPresent # Allow viewers to run script and screen reader to function on downloaded documents $list.InformationRightsManagementSettings.AllowScript = $AllowScript.IsPresent # Allow viewers to write on a copy of the downloaded document $list.InformationRightsManagementSettings.AllowWriteCopy = $AllowWriteCopy.IsPresent if($DocumentAccessExpireDays) { # After download, document access rights will expire after these number of days (1-365) $list.InformationRightsManagementSettings.EnableDocumentAccessExpire = $true $list.InformationRightsManagementSettings.DocumentAccessExpireDays   = $DocumentAccessExpireDays } # Set group protection and credentials interval if($LicenseCacheExpireDays) { # Users must verify their credentials using this interval (days) $list.InformationRightsManagementSettings.EnableLicenseCacheExpire = $true $list.InformationRightsManagementSettings.LicenseCacheExpireDays   = $LicenseCacheExpireDays } if($GroupName) { # Allow group protection. Default group: $list.InformationRightsManagementSettings.EnableGroupProtection = $true $list.InformationRightsManagementSettings.GroupName             = $GroupName } } end { if($list) { Write-Verbose "Committing IRM configuration settings on '$($list.Title)'" $list.InformationRightsManagementSettings.Update() $list.Update() $script:clientContext.Load($list) $script:clientContext.ExecuteQuery() } } } function Get-CredentialFromCredentialCache { [cmdletbinding()] param([string]$CredentialName) #if( Test-Path variable:\global:CredentialCache ) if( Get-Variable O365TenantAdminCredentialCache -Scope Global -ErrorAction SilentlyContinue ) { if($global:O365TenantAdminCredentialCache.ContainsKey($CredentialName)) { Write-Verbose "Credential Cache Hit: $CredentialName" return $global:O365TenantAdminCredentialCache[$CredentialName] } } Write-Verbose "Credential Cache Miss: $CredentialName" return $null } function Add-CredentialToCredentialCache { [cmdletbinding()] param([System.Management.Automation.PSCredential]$Credential) if(-not (Get-Variable CredentialCache -Scope Global -ErrorAction SilentlyContinue)) { Write-Verbose "Initializing the Credential Cache" $global:O365TenantAdminCredentialCache = @{} } Write-Verbose "Adding Credential to the Credential Cache" $global:O365TenantAdminCredentialCache[$Credential.UserName] = $Credential } # load the required assemblies and Windows PowerShell modules if(-not ((Load-SharePointOnlineClientComponentAssemblies) -and (Load-SharePointOnlineModule)) ) { return } # Add the credentials to the client context and SharePoint Online service connection # check for cached credentials to use $o365TenantAdminCredential = Get-CredentialFromCredentialCache -CredentialName $tenantAdmin if(-not $o365TenantAdminCredential) { # when credentials are not cached, prompt for the tenant admin credentials $o365TenantAdminCredential = Get-Credential -UserName $tenantAdmin -Message "Enter the password for the Office 365 admin" if(-not $o365TenantAdminCredential -or -not $o365TenantAdminCredential.UserName -or $o365TenantAdminCredential.Password.Length -eq 0 ) { Write-Error -Message "Could not validate the supplied tenant admin credentials" return } # add the credentials to the cache Add-CredentialToCredentialCache -Credential $o365TenantAdminCredential } # connect to Office365 first, required for SharePoint Online cmdlets to run Connect-SPOService -Url $sharepointAdminCenterUrl -Credential $o365TenantAdminCredential # enumerate each of the specified site URLs foreach($webUrl in $webUrls) { $grantedSiteCollectionAdmin = $false try { # establish the client context and set the credentials to connect to the site $script:clientContext = New-Object Microsoft.SharePoint.Client.ClientContext($webUrl) $script:clientContext.Credentials = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($o365TenantAdminCredential.UserName, $o365TenantAdminCredential.Password) # initialize the site and web context $script:clientContext.Load($script:clientContext.Site) $script:clientContext.Load($script:clientContext.Web) $script:clientContext.ExecuteQuery() # load and ensure the tenant admin user account if present on the target SharePoint site $tenantAdminUser = $script:clientContext.Web.EnsureUser($o365TenantAdminCredential.UserName) $script:clientContext.Load($tenantAdminUser) $script:clientContext.ExecuteQuery() # check if the tenant admin is a site admin if( -not $tenantAdminUser.IsSiteAdmin ) { try { # grant the tenant admin temporary admin rights to the site collection Set-SPOUser -Site $script:clientContext.Site.Url -LoginName $o365TenantAdminCredential.UserName -IsSiteCollectionAdmin $true | Out-Null $grantedSiteCollectionAdmin = $true } catch { Write-Error $_.Exception return } } try { # load the list orlibrary using CSOM $list = $null $list = $script:clientContext.Web.Lists.GetByTitle($listTitle) $script:clientContext.Load($list) $script:clientContext.ExecuteQuery() # **************  ADMIN INSTRUCTIONS  ************** # If necessary, modify the following Set-IrmConfiguration parameters to match your required values # The supplied options and values are for example only # Example that shows the Set-IrmConfiguration command with all parameters: Set-IrmConfiguration -List $list -PolicyTitle "Protected Files" -PolicyDescription "This policy restricts access to authorized users" -IrmReject -ProtectionExpirationDate $(Get-Date).AddDays(180) -DisableDocumentBrowserView -AllowPrint -AllowScript -AllowWriteCopy -LicenseCacheExpireDays 25 -DocumentAccessExpireDays 90 Set-IrmConfiguration -List $list -PolicyTitle "Protected Files" -PolicyDescription "This policy restricts access to authorized users" } catch { Write-Error -Message "Error setting IRM configuration on site: $webUrl.`nError Details: $($_.Exception.ToString())" } } finally { if($grantedSiteCollectionAdmin) { # remove the temporary admin rights to the site collection Set-SPOUser -Site $script:clientContext.Site.Url -LoginName $o365TenantAdminCredential.UserName -IsSiteCollectionAdmin $false | Out-Null } } } Disconnect-SPOService -ErrorAction SilentlyContinue
    ```

4.  스크립트를 검토하고 다음과 같이 변경합니다.

    1.  `$sharepointAdminCenterUrl`을 검색하여 SharePoint 관리 센터 URL로 예제 값을 바꿉니다.

        이 값은 SharePoint 관리 센터로 이동할 때 기준 URL로 확인되며, https://*&lt;테넌트 이름&gt;*-admin.sharepoint.com 형식을 사용합니다.

        예를 들어 테넌트 이름이 "contoso"이면 **https://contoso-admin.sharepoint.com**을 지정합니다.

    2.  `$tenantAdmin`을 검색하여 Office 365에 대해 정규화된 전역 관리자 계정으로 예제 값을 바꿉니다.

        이 값은 전역 관리자로 Office 365 관리 포털에 로그인하는 데 사용하는 값과 같으며, user_name@*&lt;테넌트 도메인 이름&gt;*.com 형식을 사용합니다.

        예를 들어 "contoso.com" 테넌트 도메인에 대한 Office 365 전역 관리자 사용자 이름이 "admin"인 경우 **admin@contoso.com**으로 지정합니다.

    3.  `$webUrls`를 검색하여 사용자의 비즈니스용 OneDrive 웹 URL로 예제 값을 바꾸고 필요한 만큼의 항목을 추가 또는 삭제합니다.

        또는 구성하는 데 필요한 URL이 모두 포함된 .CSV 파일을 가져와 이 배열을 바꾸는 방법에 대한 스크립트의 설명을 참조하세요.  자동으로 검색하고 URL을 추출하여 이 .CSV 파일을 채울 수 있는 또 다른 샘플 스크립트를 제공했습니다. 이 작업을 수행할 준비가 되었으면 이러한 단계를 완료한 직후 [모든 비즈니스용 OneDrive URL을 .CSV 파일로 출력하는 추가 스크립트](#BKMK_Script_OD4B_URLS) 섹션을 확장하세요.

        사용자의 비즈니스용 OneDrive에 대한 웹 URL의 형식은 https://*&lt;테넌트 이름&gt;*-my.sharepoint.com/personal/*&lt;사용자 이름&gt;*_*&lt;테넌트 이름&gt;*_com

        예를 들어 contoso 테넌트 사용자의 사용자 이름이 "rsimone"인 경우 **https://contoso-my.sharepoint.com/personal/rsimone_contoso_com**을 지정합니다.

    4.  비즈니스용 OneDrive를 구성하는 스크립트를 사용 중이므로 `$listTitle` 변수에 대한 **Documents** 값은 변경하지 마세요.

    5.  `ADMIN INSTRUCTIONS`를 검색합니다. 이 섹션의 변경 사항을 적용하지 않으면 사용자의 비즈니스용 OneDrive가 "보호된 파일"이라는 정책 제목과 "이 정책은 권한 있는 사용자에 대한 액세스 권한을 제한합니다."라는 설명으로 IRM에 대해 구성됩니다.  대부분의 환경에 적합한 다른 IRM 옵션은 설정되지 않습니다. 그러나 제안된 정책 제목과 설명을 변경할 수 있고, 사용 중인 환경에 적합한 다른 IRM 옵션을 추가할 수도 있습니다. Set-IrmConfiguration 명령에 고유한 매개 변수 집합을 생성하려면 스크립트에 설명된 예제를 참조하세요.

5.  스크립트를 저장한 후 서명합니다. 스크립트에 서명(더 안전)하지 않은 경우 컴퓨터에서 Windows PowerShell을 구성하여 서명되지 않은 스크립트를 실행해야 합니다. 이렇게 하려면 **관리자로 실행** 옵션으로 Windows PowerShell 세션을 실행하고 다음을 입력합니다. **Set-ExecutionPolicy Unrestricted**를 입력합니다. 그러나 이 구성에서는 서명되지 않은 모든 스크립트를 실행할 수 있으므로 보안 수준이 낮습니다.

    Windows PowerShell 스크립트에 서명을 하는 방법에 대한 자세한 내용은 PowerShell 문서 라이브러리에서 [about_Signing](https://technet.microsoft.com/library/hh847874.aspx)을 참조하세요.

6.  스크립트를 실행하고 메시지가 표시되면 Office 365 관리자 계정의 암호를 입력합니다. 스크립트를 수정하고 동일한 Windows PowerShell 세션에서 실행 하는 경우 자격 증명을 입력하라는 메시지가 표시되지 않습니다.

> [!TIP]
> 이 스크립트를 사용하여 SharePoint Online 라이브러리에 대한 IRM도 구성할 수 있습니다. 이 구성에서는 라이브러리에 보호된 문서만 포함하도록 **IRM을 지원하지 않는 문서의 업로드 허용 안 함**이라는 추가 옵션을 사용하도록 설정할 수 있습니다.    이렇게 하려면 `-IrmReject` 매개 변수를 Set-IrmConfiguration 명령으로 스크립트에 추가합니다.
> 
> 또한 `$webUrls` 변수(예: **https://contoso.sharepoint.com**)와 `$listTitle` 변수(예: **$Reports**)를 수정해야 합니다.

사용자의 비즈니스용 OneDrive 라이브러리에 대한 IRM을 사용하지 않도록 설정해야 하는 경우 [비즈니스용 OneDrive에 대한 IRM를 사용하지 않도록 설정하는 스크립트](#BKMK_Script_OD4B_DisableIRM) 섹션을 확장하세요.

###### <a name="BKMK_Script_OD4B_URLS"></a>모든 비즈니스용 OneDrive URL을 .CSV 파일로 출력하는 추가 스크립트
4c 위의 단계에서 다음 Windows PowerShell 스크립트를 사용해 모든 사용자의 Business용 OneDrive 라이브러리의 URL을 추출할 수 있습니다. 그런 다음 확인해서 필요한 경우 편집하여 기본 스크립트로 가져올 수 있습니다.

이 스크립트에는 [SharePoint Online 클라이언트 구성 요소 SDK](http://www.microsoft.com/en-us/download/details.aspx?id=42038)와 [SharePoint Online 관리 셸](http://www.microsoft.com/en-us/download/details.aspx?id=35588)이 필요합니다. 같은 지침에 따라 복사하여 붙여넣고 파일을 로컬로 저장(예: "Report-OneDriveForBusinessSiteInfo.ps1")한 후 `$sharepointAdminCenterUrl` 및 `$tenantAdmin` 값을 이전과 마찬가지로 수정한 다음 스크립트를 실행합니다.

*&#42;&#42;고지 사항&#42;&#42;*: 이 샘플 스크립트는 Microsoft 표준 지원 프로그램 또는 서비스를 통해 지원되지 않습니다. 이 샘플 스크립트는 어떤 종류의 보증도 없이 있는 그대로 제공됩니다.

```
# Requires Windows PowerShell version 3 <# Description: Queries the search service of an Office 365 tenant to retrieve all OneDrive for Business sites. Details of the discovered sites are written to a .CSV file (by default,"OneDriveForBusinessSiteInfo_<date>.csv"). Script Installation Requirements: SharePoint Online Client Components SDK http://www.microsoft.com/en-us/download/details.aspx?id=42038 SharePoint Online Management Shell http://www.microsoft.com/en-us/download/details.aspx?id=35588 ====== #> # URL will be in the format https://<tenant-name>-admin.sharepoint.com $sharepointAdminCenterUrl = "https://contoso-admin.sharepoint.com" $tenantAdmin = "admin@contoso.onmicrosoft.com" $reportName = "OneDriveForBusinessSiteInfo_$((Get-Date).ToString("yyyy-MM-dd_hh.mm.ss")).csv" $oneDriveForBusinessSiteUrls= @() $resultsProcessed = 0 function Load-SharePointOnlineClientComponentAssemblies { [cmdletbinding()] param() process { # assembly location: C:\Program Files\Common Files\microsoft shared\Web Server Extensions\16\ISAPI try { Write-Verbose "Loading Assembly: Microsoft.Office.Client.Policy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.Office.Client.Policy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.Office.Client.TranslationServices, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.Office.Client.TranslationServices, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.DocumentManagement, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.DocumentManagement, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Publishing, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Publishing, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Runtime, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Runtime, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Search.Applications, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Search.Applications, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Search, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Search, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Taxonomy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Taxonomy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.UserProfiles, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.UserProfiles, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null return $true } catch { if($_.Exception.Message -match "Could not load file or assembly") { Write-Error -Message "Unable to load the SharePoint Server 2013 Client Components.`nDownload Location: http://www.microsoft.com/en-us/download/details.aspx?id=42038" } else { Write-Error -Exception $_.Exception } return $false } } } function Load-SharePointOnlineModule { [cmdletbinding()] param() process { do { # Installation location: C:\Program Files\SharePoint Online Management Shell\Microsoft.Online.SharePoint.PowerShell $spoModule = Get-Module -Name Microsoft.Online.SharePoint.PowerShell -ErrorAction SilentlyContinue if(-not $spoModule) { try { Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking return $true } catch { if($_.Exception.Message -match "Could not load file or assembly") { Write-Error -Message "Unable to load the SharePoint Online Management Shell.`nDownload Location: http://www.microsoft.com/en-us/download/details.aspx?id=35588" } else { Write-Error -Exception $_.Exception } return $false } } else { return $true } } while(-not $spoModule) } } function Get-CredentialFromCredentialCache { [cmdletbinding()] param([string]$CredentialName) #if( Test-Path variable:\global:CredentialCache ) if( Get-Variable O365TenantAdminCredentialCache -Scope Global -ErrorAction SilentlyContinue ) { if($global:O365TenantAdminCredentialCache.ContainsKey($CredentialName)) { Write-Verbose "Credential Cache Hit: $CredentialName" return $global:O365TenantAdminCredentialCache[$CredentialName] } } Write-Verbose "Credential Cache Miss: $CredentialName" return $null } function Add-CredentialToCredentialCache { [cmdletbinding()] param([System.Management.Automation.PSCredential]$Credential) if(-not (Get-Variable CredentialCache -Scope Global -ErrorAction SilentlyContinue)) { Write-Verbose "Initializing the Credential Cache" $global:O365TenantAdminCredentialCache = @{} } Write-Verbose "Adding Credential to the Credential Cache" $global:O365TenantAdminCredentialCache[$Credential.UserName] = $Credential } # load the required assemblies and Windows PowerShell modules if(-not ((Load-SharePointOnlineClientComponentAssemblies) -and (Load-SharePointOnlineModule)) ) { return } # Add the credentials to the client context and SharePoint Online service connection # check for cached credentials to use $o365TenantAdminCredential = Get-CredentialFromCredentialCache -CredentialName $tenantAdmin if(-not $o365TenantAdminCredential) { # when credentials are not cached, prompt for the tenant admin credentials $o365TenantAdminCredential = Get-Credential -UserName $tenantAdmin -Message "Enter the password for the Office 365 admin" if(-not $o365TenantAdminCredential -or -not $o365TenantAdminCredential.UserName -or $o365TenantAdminCredential.Password.Length -eq 0 ) { Write-Error -Message "Could not validate the supplied tenant admin credentials" return } # add the credentials to the cache Add-CredentialToCredentialCache -Credential $o365TenantAdminCredential } # establish the client context and set the credentials to connect to the site $clientContext = New-Object Microsoft.SharePoint.Client.ClientContext($sharepointAdminCenterUrl) $clientContext.Credentials = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($o365TenantAdminCredential.UserName, $o365TenantAdminCredential.Password) # run a query against the Office 365 tenant search service to retrieve all OneDrive for Business URLs do { # build the query object $query = New-Object Microsoft.SharePoint.Client.Search.Query.KeywordQuery($clientContext) $query.TrimDuplicates        = $false $query.RowLimit              = 500 $query.QueryText             = "SPSiteUrl:'/personal/' AND contentclass:STS_Site" $query.StartRow              = $resultsProcessed $query.TotalRowsExactMinimum = 500000 # run the query $searchExecutor = New-Object Microsoft.SharePoint.Client.Search.Query.SearchExecutor($clientContext) $queryResults = $searchExecutor.ExecuteQuery($query) $clientContext.ExecuteQuery() # enumerate the search results and store the site URLs $queryResults.Value[0].ResultRows | % { $oneDriveForBusinessSiteUrls += $_.Path $resultsProcessed++ } } while($resultsProcessed -lt $queryResults.Value.TotalRows) $oneDriveForBusinessSiteUrls | Out-File -FilePath $reportName
```

###### <a name="BKMK_Script_OD4B_DisableIRM"></a>비즈니스용 OneDrive에 대한 IRM를 사용하지 않도록 설정하는 스크립트
사용자의 비즈니스용 OneDrive에 대한 IRM을 사용하지 않도록 설정해야 하는 경우 다음 샘플 스크립트를 사용합니다.

이 스크립트에는 [SharePoint Online 클라이언트 구성 요소 SDK](http://www.microsoft.com/en-us/download/details.aspx?id=42038)와 [SharePoint Online 관리 셸](http://www.microsoft.com/en-us/download/details.aspx?id=35588)이 필요합니다. 콘텐츠를 복사하여 붙여넣고 파일을 로컬로 저장(예: "Disable-IRMOnOneDriveForBusiness.ps1")한 후 `$sharepointAdminCenterUrl` 및 `$tenantAdmin` 값을 수정합니다. 비즈니스용 OneDrive URL을 수동으로 지정하거나 이전 섹션의 스크립트를 사용하여 해당 URL을 가져온 다음 스크립트를 실행합니다.

*&#42;&#42;고지 사항&#42;&#42;*: 이 샘플 스크립트는 Microsoft 표준 지원 프로그램 또는 서비스를 통해 지원되지 않습니다. 이 샘플 스크립트는 어떤 종류의 보증도 없이 있는 그대로 제공됩니다.

```
# Requires Windows PowerShell version 3 <# Description: Disables IRM for OneDrive for Business and can also be used for SharePoint Online libraries and lists Script Installation Requirements: SharePoint Online Client Components SDK http://www.microsoft.com/en-us/download/details.aspx?id=42038 SharePoint Online Management Shell http://www.microsoft.com/en-us/download/details.aspx?id=35588 ====== #> $sharepointAdminCenterUrl = "https://contoso-admin.sharepoint.com" $tenantAdmin = "admin@contoso.com" $webUrls = @("https://contoso-my.sharepoint.com/personal/user1_contoso_com", "https://contoso-my.sharepoint.com/personal/user2_contoso_com", "https://contoso-my.sharepoint.com/personal/person3_contoso_com") <# As an alternative to specifying the URLs as an array, you can import them from a CSV file (no header, single value per row). Then, use: $webUrls = Get-Content -Path "File_path_and_name.csv" #> $listTitle = "Documents" function Load-SharePointOnlineClientComponentAssemblies { [cmdletbinding()] param() process { # assembly location: C:\Program Files\Common Files\microsoft shared\Web Server Extensions\16\ISAPI try { Write-Verbose "Loading Assembly: Microsoft.Office.Client.Policy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.Office.Client.Policy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.Office.Client.TranslationServices, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.Office.Client.TranslationServices, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.DocumentManagement, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.DocumentManagement, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Publishing, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Publishing, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Runtime, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Runtime, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Search.Applications, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Search.Applications, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Search, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Search, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Taxonomy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Taxonomy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.UserProfiles, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.UserProfiles, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null return $true } catch { if($_.Exception.Message -match "Could not load file or assembly") { Write-Error -Message "Unable to load the SharePoint Server 2013 Client Components.`nDownload Location: http://www.microsoft.com/en-us/download/details.aspx?id=42038" } else { Write-Error -Exception $_.Exception } return $false } } } function Load-SharePointOnlineModule { [cmdletbinding()] param() process { do { # Installation location: C:\Program Files\SharePoint Online Management Shell\Microsoft.Online.SharePoint.PowerShell $spoModule = Get-Module -Name Microsoft.Online.SharePoint.PowerShell -ErrorAction SilentlyContinue if(-not $spoModule) { try { Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking return $true } catch { if($_.Exception.Message -match "Could not load file or assembly") { Write-Error -Message "Unable to load the SharePoint Online Management Shell.`nDownload Location: http://www.microsoft.com/en-us/download/details.aspx?id=35588" } else { Write-Error -Exception $_.Exception } return $false } } else { return $true } } while(-not $spoModule) } } function Remove-IrmConfiguration { [cmdletbinding()] param( [parameter(Mandatory=$true)][Microsoft.SharePoint.Client.List]$List ) process { Write-Verbose "Disabling IRM Configuration on '$($List.Title)'" $List.IrmEnabled = $false $List.IrmExpire  = $false $List.IrmReject  = $false $List.InformationRightsManagementSettings.Reset() } end { if($List) { Write-Verbose "Committing IRM configuration settings on '$($list.Title)'" $list.InformationRightsManagementSettings.Update() $list.Update() $script:clientContext.Load($list) $script:clientContext.ExecuteQuery() } } } function Get-CredentialFromCredentialCache { [cmdletbinding()] param([string]$CredentialName) #if( Test-Path variable:\global:CredentialCache ) if( Get-Variable O365TenantAdminCredentialCache -Scope Global -ErrorAction SilentlyContinue ) { if($global:O365TenantAdminCredentialCache.ContainsKey($CredentialName)) { Write-Verbose "Credential Cache Hit: $CredentialName" return $global:O365TenantAdminCredentialCache[$CredentialName] } } Write-Verbose "Credential Cache Miss: $CredentialName" return $null } function Add-CredentialToCredentialCache { [cmdletbinding()] param([System.Management.Automation.PSCredential]$Credential) if(-not (Get-Variable CredentialCache -Scope Global -ErrorAction SilentlyContinue)) { Write-Verbose "Initializing the Credential Cache" $global:O365TenantAdminCredentialCache = @{} } Write-Verbose "Adding Credential to the Credential Cache" $global:O365TenantAdminCredentialCache[$Credential.UserName] = $Credential } # load the required assemblies and Windows PowerShell modules if(-not ((Load-SharePointOnlineClientComponentAssemblies) -and (Load-SharePointOnlineModule)) ) { return } # Add the credentials to the client context and SharePoint Online service connection # check for cached credentials to use $o365TenantAdminCredential = Get-CredentialFromCredentialCache -CredentialName $tenantAdmin if(-not $o365TenantAdminCredential) { # when credentials are not cached, prompt for the tenant admin credentials $o365TenantAdminCredential = Get-Credential -UserName $tenantAdmin -Message "Enter the password for the Office 365 admin" if(-not $o365TenantAdminCredential -or -not $o365TenantAdminCredential.UserName -or $o365TenantAdminCredential.Password.Length -eq 0 ) { Write-Error -Message "Could not validate the supplied tenant admin credentials" return } # add the credentials to the cache Add-CredentialToCredentialCache -Credential $o365TenantAdminCredential } # connect to Office365 first, required for SharePoint Online cmdlets to run Connect-SPOService -Url $sharepointAdminCenterUrl -Credential $o365TenantAdminCredential # enumerate each of the specified site URLs foreach($webUrl in $webUrls) { $grantedSiteCollectionAdmin = $false try { # establish the client context and set the credentials to connect to the site $script:clientContext = New-Object Microsoft.SharePoint.Client.ClientContext($webUrl) $script:clientContext.Credentials = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($o365TenantAdminCredential.UserName, $o365TenantAdminCredential.Password) # initialize the site and web context $script:clientContext.Load($script:clientContext.Site) $script:clientContext.Load($script:clientContext.Web) $script:clientContext.ExecuteQuery() # load and ensure the tenant admin user account if present on the target SharePoint site $tenantAdminUser = $script:clientContext.Web.EnsureUser($o365TenantAdminCredential.UserName) $script:clientContext.Load($tenantAdminUser) $script:clientContext.ExecuteQuery() # check if the tenant admin is a site admin if( -not $tenantAdminUser.IsSiteAdmin ) { try { # grant the tenant admin temporary admin rights to the site collection Set-SPOUser -Site $script:clientContext.Site.Url -LoginName $o365TenantAdminCredential.UserName -IsSiteCollectionAdmin $true | Out-Null $grantedSiteCollectionAdmin = $true } catch { Write-Error $_.Exception return } } try { # load the list orlibrary using CSOM $list = $null $list = $script:clientContext.Web.Lists.GetByTitle($listTitle) $script:clientContext.Load($list) $script:clientContext.ExecuteQuery() Remove-IrmConfiguration -List $list } catch { Write-Error -Message "Error setting IRM configuration on site: $webUrl.`nError Details: $($_.Exception.ToString())" } } finally { if($grantedSiteCollectionAdmin) { # remove the temporary admin rights to the site collection Set-SPOUser -Site $script:clientContext.Site.Url -LoginName $o365TenantAdminCredential.UserName -IsSiteCollectionAdmin $false | Out-Null } } } Disconnect-SPOService -ErrorAction SilentlyContinue
```

## <a name="BKMK_Office2013Configuration"></a>Office 2016 및 Office 2013: 클라이언트 구성
이러한 이후 버전의 Office는 기본적으로 Azure RMS를 지원하므로 Word, Excel, PowerPoint, Outlook 및 Outlook Web App과 같은 응용 프로그램에 대해 IRM(정보 권한 관리) 기능을 지원하기 위해 클라이언트 컴퓨터를 구성할 필요가 없습니다. 사용자는 [!INCLUDE[o365_1](../Token/o365_1_md.md)] 자격 증명을 사용하여 Office 응용 프로그램에 로그인하기만 하면 되며, 로그인하면 파일과 메일을 보호하고 다른 사용자가 보호한 파일과 메일을 사용할 수 있습니다.

그러나 사용자가 Office 추가 기능의 이점을 얻을 수 있도록 권한 관리 공유 응용 프로그램으로 이러한 응용 프로그램을 보완하는 것이 좋습니다. 자세한 내용은 이 항목의 [Rights Management 공유 응용 프로그램: 클라이언트 설치 및 구성](../Topic/Configuring_Applications_for_Azure_Rights_Management.md#BKMK_SharingApp) 섹션을 참조하세요.

## <a name="BKMK_Office2010Configuration"></a>Office 2010: 클라이언트 구성
클라이언트 컴퓨터가 Azure RMS를 Office 2010과 함께 사용하도록 하려면 클라이언트 컴퓨터에 Windows용 Rights Management 공유 응용 프로그램을 설치해야 합니다. 사용자가 [!INCLUDE[o365_1](../Token/o365_1_md.md)] 자격 증명을 사용하여 로그인하는 것 외에 추가 구성은 필요하지 않으며, 로그인하면 파일을 보호하고 다른 사용자가 보호한 파일을 사용할 수 있습니다.

Rights Management 공유 응용 프로그램에 대한 자세한 내용은 이 항목의 [Rights Management 공유 응용 프로그램: 클라이언트 설치 및 구성](../Topic/Configuring_Applications_for_Azure_Rights_Management.md#BKMK_SharingApp) 섹션을 참조하세요.

## <a name="BKMK_SharingApp"></a>Rights Management 공유 응용 프로그램: 클라이언트 설치 및 구성
Rights Management(RMS) 공유 응용 프로그램은 클라이언트 응용 프로그램이 Azure RMS를 Office 2010과 함께 사용하는 데 필요하며, Azure RMS를 지원하는 모든 컴퓨터 및 모바일 서비스에 권장됩니다. RMS 공유 응용 프로그램은 사용자가 리본에서 직접 파일과 메일을 쉽게 보호할 수 있도록 Office 추가 기능을 설치하여 Office 응용 프로그램과 통합됩니다. 또한 Azure RMS에서 기본적으로 지원되지 않는 파일 형식에 대해 일반적인 보호를 제공하고 사용자가 보호한 파일을 추적하고 취소할 수 있도록 문서 추적 사이트를 제공합니다.

### <a name="BKMK_SharingAppforWindows"></a>Windows용 RMS 공유 응용 프로그램: 설치 및 구성
엔터프라이즈 배포를 위해 Windows용 RMS 공유 응용 프로그램을 설치하고 구성하려면 [Rights Management 공유 응용 프로그램 관리자 가이드](http://technet.microsoft.com/library/dn339003.aspx)를 참조하세요.

> [!TIP]
> 단일 컴퓨터에 대해 RMS 공유 응용 프로그램을 신속하게 설치하고 테스트하려면 [Rights Management 공유 응용 프로그램 사용자 가이드](http://technet.microsoft.com/library/dn339006.aspx)에서 [Rights Management 공유 응용 프로그램 다운로드 및 설치](http://technet.microsoft.com/library/dn574734.aspx)를 참조하세요.

### <a name="BKMK_SharingAppMovileDevices"></a>모바일 플랫폼용 RMS 공유 응용 프로그램: 설치
모바일 플랫폼용 RMS 공유 응용 프로그램을 설치하려는 경우 [Microsoft 권한 관리 페이지](http://go.microsoft.com/fwlink/?LinkId=303970)의 링크를 사용하여 관련 앱을 다운로드할 수 있습니다. 이 앱에서 Azure RMS를 사용하기 위해 구성할 사항은 없습니다.

## <a name="BKMK_RMSAPIs"></a>RMS API를 지원하는 기타 응용 프로그램: 설치 및 구성
이 범주에는 RMS SDK를 사용하여 내부에서 작성한 LOB(기간 업무) 응용 프로그램과 소프트웨어 공급업체에서 RMS SDK를 사용하여 작성한 응용 프로그램이 포함됩니다. 이러한 응용 프로그램의 경우 응용 프로그램과 함께 제공된 지침을 따르세요.

## 다음 단계
Azure 권한 관리를 지원하도록 응용 프로그램을 구성한 후에는 [Azure 권한 관리 배포 로드맵](../Topic/Azure_Rights_Management_Deployment_Roadmap.md)에서 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]를 사용자 및 관리자에게 롤아웃하기 전에 수행하기를 원하는 다른 구성 단계가 있는지를 확인할 수 있습니다. 그렇지 않은 경우 다음 단계는 [Azure Rights Management 사용](../Topic/Using_Azure_Rights_Management.md)을 참조하세요.

## 참고 항목
[Azure Rights Management 구성](../Topic/Configuring_Azure_Rights_Management.md)

