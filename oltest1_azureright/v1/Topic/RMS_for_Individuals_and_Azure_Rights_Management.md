---
description: na
keywords: na
title: RMS for Individuals and Azure Rights Management
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 2efcb440-fefd-45e9-872b-f471573aadf2
---
# 개인용 RMS 및 Azure 권한 관리
개인용 RMS는 Microsoft Azure 권한 관리(Azure RMS)를 통해 보호되는 중요한 파일을 전송받았으나 해당 IT 부서가 Azure에서 해당 사용자에 대한 계정을 관리하지 않아 인증이 불가능한 사용자를 위한 무료 셀프 서비스 구독입니다. IT 부서에서 Office 365가 없거나 Azure 서비스를 사용하지 않는 경우를 예로 들 수 있습니다.

이러한 사용자는 Azure RMS에 사용할 무료 회사 또는 학교 계정을 등록하고, Rights Management 공유 응용 프로그램을 다운로드 및 설치할 수 있습니다. 그러면 결과적으로 해당 사용자가 인증을 통해 자신이 보호되는 파일을 받는 사람임을 입증하고 컴퓨터나 모바일 장치에서 보호되는 파일을 읽을 수 있습니다.

Windows 컴퓨터에서 권한 관리 공유 응용 프로그램을 사용하여 현재 위치에서 파일을 보호하거나 조직 내부 또는 외부 사용자에게 전자 메일로 보호된 파일을 보낼 수도 있습니다. 보내는 전자 메일의 받는 사람도 Azure 계정을 관리하지 않는 조직에 속한 경우, 역시 해당 사용자도 개인용 RMS 계정에 등록하여 보호되는 전자 메일 첨부 파일을 읽을 수 있습니다.

> [!IMPORTANT]
> 이 무료 구독을 사용하면 권한이 있는 사용자가 보호된 파일을 항상 읽을 수 있습니다. 현재, 무료 구독을 사용하여 문서를 보호하고 새 보호된 전자 메일 메시지를 만들 수도 있습니다. 하지만 새 보호된 콘텐츠를 작성하는 기능은 평가판에서만 사용할 수 있으며 나중에 제거될 수 있습니다. 개인용 RMS를 사용하여 콘텐츠를 보호하는 방법에 대한 자세한 내용 및 변경 사항은 [Microsoft Rights Management 서비스 약관](https://portal.aadrm.com/Legal/Service)을 참조하세요.

무료 Rights Management 공유 응용 프로그램을 사용하여 파일을 보호하는 방법에 대한 자세한 내용은 [Rights Management 공유 응용 프로그램 사용자 가이드](http://technet.microsoft.com/library/dn339006.aspx)를 참조하세요.

개인용 RMS는 Azure Active Directory에서 지원하는 셀프서비스 등록의 한 예입니다. 작동 방법에 대한 자세한 내용은 Microsoft Azure 문서의 [Azure 셀프서비스 가입이란?](https://azure.microsoft.com/documentation/articles/active-directory-self-service-signup/)을 참조하세요. 개인용 RMS에 해당하는 더 상세한 내용은 다음 섹션을 참조하세요.

-   [개인용 RMS 등록 방법](../Topic/RMS_for_Individuals_and_Azure_Rights_Management.md#BKMK_SignUp)

    -   [기술 개요](../Topic/RMS_for_Individuals_and_Azure_Rights_Management.md#BKMK_TechnicalOverview)

-   [관리자가 개인용 RMS용으로 만들어진 계정을 제어하는 방법](../Topic/RMS_for_Individuals_and_Azure_Rights_Management.md#BKMK_TakeControlofAccounts)

-   [사용자가 개인용 RMS에 등록했는지 확인하는 방법](#BKMK_Detect)

## <a name="BKMK_SignUp"></a>개인용 RMS 등록 방법
이 무료 계정에 등록하려면 [Microsoft Rights Management 페이지](https://portal.aadrm.com/)를 방문하여 계정을 요청하고 회사 또는 학교 전자 메일 주소를 제공합니다. 이 등록 페이지로 이동하는 가장 일반적인 방법은 보호되는 첨부 파일이 포함된 전자 메일 메시지를 받았을 때입니다. 여기에는 등록 방법에 대한 지침이 포함되어 있습니다. Microsoft로부터 전자 메일을 답장을 받으면 세부 정보 입력을 통해 계정을 만들어 등록 프로세스를 완료합니다. Microsoft에서 전자 메일 확인을 받으면 최종 전자 메일 메시지가 다양한 장치에 대한 공유 응용 프로그램을 다운로드할 수 있는 페이지와 사용자 가이드 링크를 전달합니다.

#### 개인용 RMS를 등록하려면

1.  Windows 또는 Mac 컴퓨터에서 [Microsoft Rights Management 페이지](https://portal.aadrm.com)로 이동합니다.

2.  **janetm@contoso.com** 또는 **p.dover@fabrikam.com**과 같은 조직에 사용하는 전자 메일 주소를 입력합니다.

    > [!IMPORTANT]
    > 개인 메일 계정은 지원되지 않으므로 Microsoft 계정(이전의 Microsoft Live ID 계정)이나 가정에서 사용하는 인터넷 공급자가 제공한 다른 개인 계정은 입력하지 마세요.

3.  **시작**을 클릭합니다.

    Microsoft는 기존에 해당 조직에 [Azure RMS가 포함된 유료 구독](https://technet.microsoft.com/library/dn655136.aspx)이 있는지 확인하기 위해 사용자의 전자 메일 주소를 사용합니다. 구독이 있으면 개인용 RMS가 필요하지 않고 즉시 로그인되며 개인용 RMS 셀프서비스 가입이 취소됩니다. Azure RMS 유료 구독이 없으면 다음 단계를 진행합니다.

4.  입력한 주소로 확인 메일 메시지가 전송될 때까지 기다립니다. 이 메일은 Microsoft(DoNotReply@microsoft.com)에서 보내는 것이며 제목은 **Microsoft RMS**입니다.

5.  메일을 받으면 지침의 링크를 클릭하여 등록 프로세스를 완료합니다.

6.  링크를 클릭하면 계정에 대한 세부 정보를 입력하는 새 **Microsoft Rights Management** 페이지로 이동합니다. 이름과 성을 임력하고 선택한 암호를 입력 및 확인한 다음 국가(또는 자신의 국가가 목록에 없으면 가장 인접한 국가)를 드롭다운에서 선택한 다음 **만들기**를 클릭합니다.

7.  이제 Microsoft에서 보낸, 계정을 사용할 준비가 되었음을 확인하는 다른 메일 메시지가 올 때까지 기다립니다.

8.  메일을 받으면 링크를 클릭하여 로그인하고 지침에 따라 공유 응용 프로그램을 다운로드 및 설치하거나, 도움말 링크를 클릭하여 공유 응용 프로그램 사용자 가이드를 읽어봅니다.

이제 계정이 만들어졌으므로 파일을 보호하고 다른 사용자가 보호한 파일을 읽을 수 있습니다. 파일을 보호하거나 보호된 파일을 읽기 위해 로그인하라는 메시지가 나타나면 개인용 RMS 계정을 만들 때 사용한 메일 주소와 암호를 입력하세요.

### <a name="BKMK_TechnicalOverview"></a>기술 개요
개인용 RMS는 Microsoft 클라우드 기반 기술로 사용자를 인증하는 다른 서비스에서도 사용되는 실시간 메일 계정 생성 프로세스를 사용합니다.

이는 사용자가 개인용 RMS에 등록하고 조직에 Office 365 구독 또는 Azure 구독이 없어 Azure에 사용자를 인증할 디렉터리가 없는 경우에 발생합니다.

1.  조직의 첫 번째 사용자가 개인용 RMS 구독을 요청하면 메일 주소에 입력된 도메인 이름을 통해 이미 Azure 테넌트와 연결되어 있는지 여부를 확인합니다. 기존 테넌트가 없으면 해당 조직에 대해 이 첫 번째 사용자의 계정이 담긴 새로운 테넌트와 Azure 디렉터리가 자동 생성됩니다. Azure의 유료 구독과 달리, 이 첫 번째 계정은 전역 관리자가 아니라 표준 사용자입니다. 새 계정에서는 사용자가 제공한 전자 메일 주소와 암호를 사용합니다.

    > [!NOTE]
    > 일부 도메인 이름은 디렉터리를 만드는 데 사용할 수 없으므로 개인용 RMS에 사용할 수 없습니다. 차단된 도메인 이름 목록은  JavaScript 개체 Object Notation 파일([http://portal.aadrm.com/content/blocked_domains.json](http://portal.aadrm.com/content/blocked_domains.json))에서 확인할 수 있습니다.

    기존 테넌트가 있는 경우 Azure RMS에 대한 구독을 보유하고 있는지 확인합니다. 구독이 없으면 개인용 RMS 무료 구독을 추가할 수 있습니다.

2.  조직에 개인용 RMS 구독이 부여됩니다. 이제 이 사용자는 Azure에서 인증되어 파일을 보호하고, Azure 권한 관리를 사용하여 다른 사용자가 보호한 파일을 읽을 수 있습니다. 파일을 보호하고, 보호되는 파일을 읽으려면 RMS 지원 응용 프로그램(예: 무료 [Rights Management 공유 응용 프로그램](https://technet.microsoft.com/library/dn919648.aspx))이 있어야 합니다.

3.  동일한 조직의 두 번째 사용자가 개인용 RMS 구독을 요청하면 조직의 개인용 RMS 구독을 통해 새 사용자 계정이 이전에 만든 Azure 디렉터리에 추가됩니다. 이 두 번째 사용자는 첫 번째 사용자가 할 수 있는 모든 작업(파일 보호 및 보호된 파일 읽기)을 수행할 수 있지만, 이 두 사용자는 이제 해당 조직의 Azure 디렉터리의 계정에 대한 액세스를 제한하는 파일에 기본 템플릿을 빠르게 적용할 수 있으므로 보다 쉽고 안전하게 협력할 수 있습니다.

4.  같은 조직의 후속 사용자는 같은 패턴에 따라 조직의 Azure 디렉터리에 사용자 계정을 추가합니다(새 사용자가 등록한 경우). 디렉터리에 계정을 더 추가할수록 더 많은 사용자가 동료 및 파트너와 안전하게 공동 작업을 수행할 수 있으며, 권한 없는 사용자에게 파일에 대한 액세스 권한이 없어야 하는 경우 더 쉽게 이러한 사용자가 파일을 읽지 못하도록 할 수 있습니다.

이 프로세스 전체에서 조직에 부과되는 요금은 없으며 IT 부서에서 해야 할 작업도 없습니다. 그러나 IT 부서는 다음 중 하나를 수행할 수 있습니다.

-   **계정 및 등록 프로세스 관리**: IT 관리자는 Azure에서 자동으로 만들어진 디렉터리 및 계정의 소유권을 가질 수 있습니다. 그런 다음 암호 동기화 및 Single Sign-On과 같은 디렉터리 통합 솔루션을 구현하여 계정을 관리할 수 있습니다. 또는 사용자가 계정을 만들거나 개인용 RMS에 등록하지 못하도록 할 수 있습니다.

    자세한 내용은 다음 [관리자가 개인용 RMS용으로 만들어진 계정을 제어하는 방법](../Topic/RMS_for_Individuals_and_Azure_Rights_Management.md#BKMK_TakeControlofAccounts) 섹션을 참조하세요.

-   **Rights Management 관리**: IT 관리자는 조직의 개인용 RMS 구독을 Azure 권한 관리가 포함된 유료 구독으로 전환할 수 있습니다. 이렇게 하면 기존 Azure 디렉터리 및 계정이 개인용 RMS를 사용하던 기존 사용자에 대해 원활하게 전환되도록 유지됩니다. 사용자가 이전에 보호한 모든 파일은 계속해서 동일한 정책으로 보호되며, 파일 사용 권한이 부여된 사용자는 계속해서 동일한 방법으로 파일을 사용할 수 있습니다.

    이러한 방침을 취하면 조직은 권한 관리를 해당 워크플로, 서비스 및 데이터 저장소에 통합할 수 있는 이점을 누릴 수 있습니다. 또한 이제 Azure 권한 관리를 위한 조직의 테넌트 키를 제어할 수 있으므로 권한 관리를 수행할 수 있습니다. 이제 다음이 가능합니다.

    -   Exchange 및 SharePoint가 온-프레미스에서 실행되는 경우에도 Azure 권한 관리를 지원하도록 Exchange 및 SharePoint를 구성할 수 있습니다. Exchange 및 SharePoint는 기본적으로 온라인 서비스에 대해 지원되며, 온-프레미스 서버에 대해 커넥터를 통해 지원됩니다. 자세한 내용은 다음 항목을 참조하세요.

        -   [Azure 권한 관리용 응용 프로그램 구성](../Topic/Configuring_Applications_for_Azure_Rights_Management.md) 항목의 [Office 365: 클라이언트 및 온라인 서비스 구성](../Topic/Configuring_Applications_for_Azure_Rights_Management.md#BKMK_O365)에 있는 Exchange Online 및 SharePoint Online 섹션

        -   [Azure 권한 관리 커넥터 배포](../Topic/Deploying_the_Azure_Rights_Management_Connector.md)

    -   필요한 경우, 권한 관리로 보호되는 파일을 암호 해독할 수 있도록 회사 소유의 데이터에 대해 eDiscovery를 수행할 수 있습니다. 자세한 내용은 [Azure 권한 관리 및 검색 서비스 또는 데이터 검색을 위한 슈퍼 사용자 구성](../Topic/Configuring_Super_Users_for_Azure_Rights_Management_and_Discovery_Services_or_Data_Recovery.md)를 참조하세요.

    -   조직에서 사용되는 권한 관리의 모든 활동을 기록할 수 있습니다. 이 기능은 매우 강력한데, 보호되고 있는 파일과 보호된 파일에 성공적으로 액세스하는 사용자를 모니터링할 수 있을 뿐만 아니라 보호된 파일에 액세스하려고 시도하는 권한 없는 사용자의 잠재적으로 의심스러운 동작을 식별할 수 있기 때문입니다. 자세한 내용은 [Azure 권한 관리 사용 현황 로깅 및 분석](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md)를 참조하세요.

    -   [Azure RMS 구독](https://technet.microsoft.com/dn858608)에서 지원한다면 사용자에게 보호되는 문서를 추적하고 취소할 수 있는 기능을 제공합니다.  자세한 내용은 [RMS 공유 응용 프로그램 사용자 가이드](https://technet.microsoft.com/library/dn339006.aspx)에서 [파일 추적 및 취소](https://technet.microsoft.com/library/dn986611.aspx)를 참조하세요.

    -   Azure 권한 관리의 테넌트 키가 IT 정책에 따라 온-프레미스에서 생성되어 HSM(하드웨어 보안 모듈)을 통해 Microsoft로 안전하게 전송되도록 BYOK(Bring Your Own Key) 솔루션을 구현할 수 있습니다. 자세한 내용은 [Azure 권한 관리 테넌트 키 계획 및 구현](../Topic/Planning_and_Implementing_Your_Azure_Rights_Management_Tenant_Key.md)를 참조하세요.

## <a name="BKMK_TakeControlofAccounts"></a>관리자가 개인용 RMS용으로 만들어진 계정을 제어하는 방법
조직의 개인용 RMS 구독을 유료 구독으로 전환하지 않으려는 경우 다음과 같은 방법으로 조직용으로 만들어진 Azure 디렉터리에서 계속해서 사용자 계정을 제어할 수 있습니다.

-   Azure Active Directory 및 Active Directory 도메인 서비스 인프라를 위한 디렉터리 통합 솔루션을 구현합니다. 사용자가 권한 관리를 사용하기 위한 새 계정을 만들지 않아도 되도록 계정과 암호를 동기화할 수 있습니다. 그러면 온-프레미스 암호 정책이 새 Azure 사용자 계정에 적용됩니다. 사용자가 권한 관리를 사용하기 위한 다른 암호를 기억하지 않아도 되도록 암호도 동기화할 수 있습니다.

-   사용자가 개인용 RMS 구독을 위해 Azure 권한 관리에 사용 등록하는 것을 방지할 수 있습니다. 대부분의 경우 이렇게 하는 데에는 이점이 별로 없습니다. 왜냐하면 사용자가 보호 메커니즘 없이 파일을 공유하거나(회사를 위험에 빠뜨릴 수 있음) IT 부서에서 해당 데이터에 액세스할 수 있는 옵션이 제공되지 않는 다른 파일 보호 메커니즘을 사용할 수 있기 때문입니다. 그럼에도 불구하고 사용자가 개인용 RMS를 사용하기 위해 등록하는 것을 방지하려면 조직의 Azure 디렉터리 소유권을 가진 후에 다음 중 하나를 수행합니다.

    -   모든 사용자가 개인용 RMS를 포함한 셀프서비스 구독에 등록하지 못하게 차단합니다.  현재 서비스에서는 이를 설정할 수 없으며 이 설정은 셀프서비스 프로세스를 사용하는 모든 Azure 구독에 적용됩니다. 이 작업을 수행하려면 Azure Active Directory용 Windows PowerShell 모듈의 [Set-MsolCompanySettings](http://technet.microsoft.com/library/dn194127.aspx) cmdlet에서 **AllowAdHocSubscriptions** 매개 변수를 false로 설정합니다. 예: **Set-MsolCompanySettings -AllowAdHocSubscriptions $false**

    -   사용자가 Azure에서 새 계정을 만들지 못하도록 합니다. 이렇게 하면 Azure에 계정이 이미 있는 사용자만 개인용 RMS를 포함한 셀프서비스 구독에 등록할 수 있습니다.  이 작업을 수행하려면 Azure Active Directory용 Windows PowerShell 모듈의 [Set-MsolCompanySettings](http://technet.microsoft.com/library/dn194127.aspx) cmdlet에서 **AllowEmailVerifiedUsers** 매개 변수를 false로 설정합니다. 예: **Set-MsolCompanySettings -AllowEmailVerifiedUsers $false -AllowAdHocSubscriptions $true**

    -   Active Directory 도메인 서비스 인프라를 Azure Active Directory와 동기화합니다. 이렇게 하면 사용자가 개인용 RMS 등의 셀프서비스 구독에 등록할 때 새 계정이 만들어지지 않으며, 이전에 Azure 디렉터리에서 만들어진 계정을 삭제하거나 사용하지 않을 수 있습니다.

Azure 디렉터리에서 사용자 계정을 제어하거나, 사용자가 개인용 RMS에 등록하지 못하도록 하려면 Azure 구독을 얻은 후 디렉터리를 소유해야 합니다. Azure 구독이 없는 경우 무료로 얻을 수 있습니다. 디렉터리가 셀프 서비스 프로세스 중에 자동으로 만들어진 경우에는 해당 디렉터리를 만드는 데 사용한 도메인을 소유해야 합니다. Azure에 이미 디렉터리가 있지만 사용자가 조직에서 사용하는 새 도메인을 지정한 경우 해당 도메인을 기존 디렉터리에 병합합니다. 자세한 내용은 [Azure 셀프서비스 등록이란?](https://azure.microsoft.com/documentation/articles/active-directory-self-service-signup/)을 참조하세요.

## <a name="BKMK_Detect"></a>사용자가 개인용 RMS에 등록했는지 확인하는 방법
관리자는 사용자가 개인용 RMS를 등록했는지 여부를 어떻게 알 수 있을까요? 다음과 같은 방법을 사용할 수 있습니다(한 가지 또는 여러 가지를 함께 사용).

-   사용자에게 중요한 기밀 파일을 어떻게 보호하는지 물어봅니다(특히, 조직 외부의 다른 사용자와 공동 작업할 때).

-   조직에 대한 Azure 구독이 있는 경우 [Get-MsolAccountSku](https://msdn.microsoft.com/library/azure/dn194118.aspx) cmdlet을 사용하여 **RIGHTSMANAGEMENT_ADHOC**이 구독 중 하나로 반환되는지 확인합니다. 구독 중 하나로 반환되는 경우 사용자가 셀프 서비스 등록 프로세스를 사용할 수 있도록 하는 활성 단위 풀과 함께 조직에 부여된 개인용 RMS 구독입니다.

-   시스템 관리 솔루션(예: System Center Configuration Manager)을 사용하여, 설치된 소프트웨어와 사용 중인 소프트웨어의 목록을 만듭니다. Rights Management 공유 응용 프로그램은 **ipviewer.exe** 프로그램을 통해 실행되며, 무료로 [응용 프로그램을 다운로드하고 설치](http://go.microsoft.com/fwlink/?LinkId=303970)하여 소프트웨어 인벤토리에 사용할 이 응용 프로그램에 대한 다른 특성을 확인할 수 있습니다.

-   Rights Management 공유 응용 프로그램이 만든 파일 이름 확장명을 세심히 살펴봅니다. .pfile 및 .ppdf 파일 이름 확장명이 가장 명확한 예이지만, Rights Management에 의해 기본적으로 보호될 때 파일 이름 확장명이 변경되는 파일도 있습니다. 자세한 내용은 [Rights Management 공유 응용 프로그램 관리자 가이드](http://technet.microsoft.com/library/dn339003.aspx)의 [지원되는 파일 형식 및 파일 이름 확장명](http://technet.microsoft.com/library/dn339003.aspx) 섹션을 참조하세요.

## 참고 항목
[Azure Rights Management 시작하기](../Topic/Getting_Started_with_Azure_Rights_Management.md)

