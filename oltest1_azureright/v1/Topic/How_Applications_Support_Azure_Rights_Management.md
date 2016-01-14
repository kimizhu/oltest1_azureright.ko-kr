---
description: na
keywords: na
title: How Applications Support Azure Rights Management
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 2cdc7bde-4044-4021-b887-11476f99afd9
---
# 응용 프로그램이 Azure 권한 관리를 지원하는 방식
다음 정보를 참조하여 Office 응용 프로그램, Word, Excel, PowerPoint, Outlook 등의 최종 사용자 응용 프로그램과 Exchange, SharePoint 등의 서비스에서 Microsoft [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]를 사용하여 조직 데이터를 보호하는 방법을 파악할 수 있습니다.

-   [Windows 및 모바일 플랫폼용 RMS 공유 응용 프로그램](../Topic/How_Applications_Support_Azure_Rights_Management.md#BKMK_SharingAppIntro)

-   [Office 응용 프로그램: Word, Excel, PowerPoint, Outlook](../Topic/How_Applications_Support_Azure_Rights_Management.md#BKMK_OfficeAppsIntro)

    -   [Exchange Online 및 Exchange Server](../Topic/How_Applications_Support_Azure_Rights_Management.md#BKMK_ExchangeIntro)

    -   [SharePoint Online 및 SharePoint Server](../Topic/How_Applications_Support_Azure_Rights_Management.md#BKMK_SharePointIntro)

-   [Windows Server를 실행하고 FCI(파일 분류 인프라)를 사용하는 파일 서버](../Topic/How_Applications_Support_Azure_Rights_Management.md#BKMK_FCIIntro)

-   [RMS API를 지원하는 기타 응용 프로그램](../Topic/How_Applications_Support_Azure_Rights_Management.md#BKMK_APIAppsIntro)

> [!NOTE]
> [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)](Azure RMS)에서 지원하는 응용 프로그램과 버전을 확인하려면 [Azure 권한 관리 요구 사항](../Topic/Requirements_for_Azure_Rights_Management.md)을 참조하세요.

구성된 정책에 따라 정보 보호가 자동으로 적용되는 경우도 있습니다. SharePoint 라이브러리, 분류된 파일, Exchange 전송 규칙 등을 예로 들 수 있습니다. 사용자가 템플릿이나 특정 옵션을 선택하여 응용 프로그램에서 정보 보호를 직접 적용해야 하는 경우도 있습니다. 사용자가 메일로 파일을 공유하거나 조직 외부 사용자 또는 선택한 사용자에 대해 액세스 또는 사용을 제한하여 내부에서 파일을 보호하는 경우를 예로 들 수 있습니다.

정책을 구성하는 관리자와 사용자는 템플릿을 통해 보다 간편하게 올바른 수준의 보호를 적용하고 조직 내 사용자에 대해 액세스를 제한할 수 있습니다.[!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]에서는 기본 템플릿 두 개가 제공되지만 개별 옵션을 지정해야 하는 경우 시간을 단축하기 위해 사용자 지정 템플릿을 만들 수도 있습니다. 자세한 내용은 [Azure 권한 관리용 사용자 지정 템플릿 구성](../Topic/Configuring_Custom_Templates_for_Azure_Rights_Management.md)를 참조하세요.

사용자가 정보 보호를 직접 적용해야 하는 경우에는 적용 방법과 시기에 대한 지침을 제공해야 합니다. 사용자가 사용 중인 응용 프로그램 및 버전과 해당 사용 방법에 따라 구체적인 지침을 제공해야 하며, 업무상 정보 보호를 적용하는 것이 적절한 시기와 적용 방법에 대한 지침도 제공해야 합니다. 자세한 내용은 [사용자가 Azure 권한 관리를 사용하여 파일을 보호할 수 있도록 지원](../Topic/Helping_Users_to_Protect_Files_by_Using_Azure_Rights_Management.md)를 참조하세요.

Azure RMS에 대해 이들 응용 프로그램을 구성하는 방법에 대한 자세한 내용은 [Azure 권한 관리용 응용 프로그램 구성](../Topic/Configuring_Applications_for_Azure_Rights_Management.md)을 참조하세요.

> [!TIP]
> Azure RMS를 사용하여 응용 프로그램의 예와 스크린샷을 보려면 [Azure 권한 관리란?](../Topic/What_is_Azure_Rights_Management_.md) 항목의 [Azure RMS 실행: 관리자와 사용자에게 표시되는 내용](../Topic/What_is_Azure_Rights_Management_.md#BKMK_RMSpictures) 섹션을 참조하세요.

## <a name="BKMK_SharingAppIntro"></a>Windows 및 모바일 플랫폼용 RMS 공유 응용 프로그램
RMS 공유 응용 프로그램은 Office 2010을 지원하는 데 필요하며 Windows 컴퓨터, Mac 컴퓨터, 모바일 장치에서 사용해도 좋은 무료 다운로드 가능 응용 프로그램입니다. 이 응용 프로그램의 장점 중 하나는 기본적으로 [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)]를 지원하지 않는 응용 프로그램과 파일에 대해서도 일반적인 보호를 적용할 수 있으므로 모든 파일을 보호할 수 있다는 것입니다. 다양한 보호 수준에 대한 자세한 내용은 [Rights Management 공유 응용 프로그램 관리자 가이드](http://technet.microsoft.com/library/dn339003.aspx)의 [보호 수준 - 기본 및 일반](http://technet.microsoft.com/library/dn339003.aspx) 섹션을 참조하세요.

사용자가 RMS 공유 응용 프로그램을 사용하여 파일을 보호하면, 보호된 문서를 추적하고 또 필요한 경우 이들 문서에 대한 액세스를 취소할 수도 있습니다.[문서 추적 사이트](http://go.microsoft.com/fwlink/?LinkId=529562)를 사용하여 이를 수행합니다.

Windows 컴퓨터에서 RMS 공유 응용 프로그램은 사용자가 이미 사용 중인 응용 프로그램과 원활하게 통합되며 해당 응용 프로그램의 성능을 향상시켜 줍니다.

-   Word, Excel, PowerPoint 및 Outlook용 Office 추가 기능이 설치됩니다. 그러면 리본 메뉴에 **보호된 항목 공유** 단추가 표시되며, 이 단추를 클릭하면 파일을 보호하는 데 가장 일반적으로 사용되는 설정을 메일로 전송할 수 있는 간편한 대화 상자가 호출됩니다. 이 단추는 또한 문서 추적 사이트를 액세스하는 빠른 방법을 제공합니다.

-   파일 탐색기에 새로운 마우스 오른쪽 클릭 옵션이 추가됩니다. 그러면 **바로 보호** 옵션이 표시되며, 이 옵션을 선택하면 디스크에 저장된 파일을 보호하는 데 가장 일반적으로 사용되는 설정이 포함된 간편한 대화 상자가 호출됩니다.

-   [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)]를 통해 보호된 파일을 열 수 있는 뷰어가 제공됩니다. 보호된 파일을 열 수 있는 다른 응용 프로그램이 설치되어 있지 않으면 이 뷰어가 자동으로 호출됩니다.

-   Office 2010 제품군의 Word, Excel, PowerPoint 및 Outlook이 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]와 원활하게 연동되도록 하는 Office 2010용 백 엔드 구성이 적용됩니다.

[Microsoft Rights Management 페이지](http://go.microsoft.com/fwlink/?LinkId=303970)를 사용하여 단일 컴퓨터에 대해 Windows용 RMS 공유 응용 프로그램을 다운로드하여 설치할 수 있지만 자동 설치 및 사용자 지정 구성에 대한 엔터프라이즈 배포도 지원됩니다. 자세한 내용은 다음 리소스를 참조하세요.

-   [Rights Management 공유 응용 프로그램 관리자 가이드](http://technet.microsoft.com/library/dn339003.aspx)

-   [Rights Management 공유 응용 프로그램 사용자 가이드](http://technet.microsoft.com/library/dn339006.aspx)

모바일 장치용 RMS 공유 응용 프로그램은 iPad/iPhone, Android, Windows Phone, Windows RT 등 널리 사용되는 모바일 장치를 지원합니다. 사용자는 [Microsoft Rights Management 페이지](http://go.microsoft.com/fwlink/?LinkId=303970)의 링크를 통해 관련 스토어에서 이 앱을 다운로드할 수 있습니다.

## <a name="BKMK_OfficeAppsIntro"></a>Office 응용 프로그램: Word, Excel, PowerPoint, Outlook
이러한 응용 프로그램은 정보 권한 관리(IRM)를 사용하여 Rights Management를 기본적으로 지원하며 사용자가 저장된 문서 또는 전송할 메일 메시지에 보호를 적용할 수 있도록 합니다. 사용자는 템플릿을 적용하거나 액세스, 권한 및 사용 제한을 위해 자세하게 사용자 지정된 설정을 선택할 수 있습니다. 예를 들어 사용자는 조직 내의 사용자만 액세스할 수 있도록 파일을 구성할 수도 있고 파일 편집 가능 여부를 제어하거나 파일을 읽기 전용으로 제한하거나 파일 인쇄를 차단할 수도 있습니다. 시간이 중요한 파일의 경우에는 파일에 더 이상 액세스할 수 없는 만료 시간을 구성할 수 있습니다(사용자가 직접 구성하거나 템플릿 적용). Outlook에서는 사용자가 **전달 금지** 옵션을 선택하여 데이터 유출을 방지할 수도 있습니다.

### <a name="BKMK_ExchangeIntro"></a>Exchange Online 및 Exchange Server
Exchange Online 또는 Exchange Server를 사용할 때는 IRM(정보 권한 관리) 통합을 사용하면 정보 보호 솔루션이 추가로 제공됩니다.

-   **Exchange ActiveSync IRM** - 모바일 장치에서 메일 메시지를 보호하고 보호된 메일 메시지를 사용할 수 있습니다.

-   **Outlook Web App**용 RMS 지원 - Outlook 클라이언트와 비슷한 방식으로 구현되며, 사용자가 템플릿을 적용하거나 개별 옵션을 지정하여 메일 메시지를 보호할 수 있으며 자신에게 전송되는 보호된 메일 메시지를 읽고 사용할 수 있습니다.

-   Outlook 클라이언트용 **보호 규칙** - 관리자가 지정된 받는 사람의 메일 메시지에 RMS 템플릿을 자동으로 적용하도록 구성하는 규칙입니다. 예를 들어 법률 자문 부서로 전송하는 내부 메일은 법률 자문 부서 구성원만 읽을 수 있으며 전달할 수 없도록 구성할 수 있습니다. 사용자는 메일 메시지를 보내기 전에 메시지에 적용되는 보호를 확인할 수 있으며 기본적으로 보호가 필요하지 않다고 판단되면 제거할 수 있습니다. 메일은 전송되기 전에 암호화됩니다. 자세한 내용은 Exchange 라이브러리에서 [Outlook 보호 규칙](http://technet.microsoft.com/library/dd638178%28v=exchg.150%29.aspx) 및 [Outlook 보호 규칙 만들기](http://technet.microsoft.com/library/dd638196%28v=exchg.150%29.aspx)를 참조하세요.

-   **전송 규칙** - 관리자가 보낸 사람, 받는 사람, 메시지 제목, 내용 등의 속성을 기준으로 메일 메시지에 RMS 템플릿을 자동으로 적용하도록 구성하는 규칙입니다. 이러한 규칙은 개념상 보호 규칙과 비슷하지만 사용자가 보호를 제거할 수 없고, 모바일 장치에서 보내는 메일과 Outlook Web Access에도 적용 가능하며, 클라이언트에서 메일 메시지를 보내기 전에 암호화하지 않는다는 점이 다릅니다. 자세한 내용은 Exchange 라이브러리에서 [전송 보호 규칙 만들기](http://technet.microsoft.com/library/dd302432.aspx)를 참조하세요.

-   **DLP(데이터 손실 방지) 정책** - 메일 메시지를 필터링하고 기밀 또는 중요한 데이터(예: 개인 정보 또는 신용 카드 정보)에 대해 데이터 손실을 방지하기 위한 작업을 수행하는 조건 집합을 포함하는 정책입니다. 중요한 데이터가 검색되면 정책 팁을 사용하여 메일 메시지의 정보를 기준으로 정보 보호를 적용해야 할 수 있다는 알림을 사용자에게 표시할 수 있습니다. 자세한 내용은 Exchange 라이브러리에서 [데이터 손실 방지](http://technet.microsoft.com/library/jj150527%28v=exchg.150%29.aspx)를 참조하세요.

-   **Office 365 메시지 암호화** - 전송 규칙을 사용하여 회사 외부 사용자에게 암호화된 메일을 보냅니다. 이러한 메일은 Outlook Web App과 비슷한 인터페이스가 포함된 브라우저에서 읽을 수 있습니다. 회사의 암호화된 메일에서 고지 사항 텍스트와 헤더 텍스트를 사용자 지정할 수 있으며 회사 로고도 추가할 수 있습니다. 자세한 내용은 Office 웹사이트에서 [Office 365 메시지 암호화](http://office.microsoft.com/o365-message-encryption-FX104179182.aspx)를 참조하세요.

Exchange Server를 사용하는 경우에는 온-프레미스 서버와 RMS 클라우드 서비스 간의 릴레이 역할을 하는 RMS 커넥터를 배포하여 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]를 통해 정보 보호 기능을 사용할 수 있습니다. 자세한 내용은 [Azure 권한 관리 커넥터 배포](../Topic/Deploying_the_Azure_Rights_Management_Connector.md)를 참조하세요.

### <a name="BKMK_SharePointIntro"></a>SharePoint Online 및 SharePoint Server
SharePoint Online 또는 SharePoint Server를 사용할 때는 IRM(정보 권한 관리) 통합을 사용할 수 있습니다. 그러면 관리자가 목록 또는 라이브러리를 보호할 수 있습니다. 그러므로 사용자가 문서를 체크 아웃할 때 파일이 보호된 상태이기 때문에 지정한 정보 보호 정책에 따라 권한이 있는 사용자만 파일을 확인 및 사용할 수 있습니다. 예를 들어 파일을 읽기 전용으로 지정하고, 텍스트를 복사할 수 없도록 설정하고, 로컬 복사본 저장 및 파일 인쇄를 금지할 수 있습니다.

목록 및 라이브러리의 경우 정보 보호는 항상 최종 사용자가 아닌 관리자에 의해 적용됩니다. 그리고 개별 파일이 아니라 해당 컨테이너의 모든 문서에 대해 목록 또는 라이브러리 수준에서 적용됩니다.  SharePoint Online을 사용하면 사용자는 IRM을 비즈니스 라이브러리용 OneDrive에 적용할 수 있습니다.

이렇게 하려면 먼저 SharePoint에 대해 IRM 서비스를 사용하도록 설정해야 합니다. 그런 다음 라이브러리에 대한 정보 권한 관리를 지정합니다. SharePoint Online 및 비즈니스용 OneDrive의 경우, 사용자는 비즈니스 라이브러리용 OneDrive에 대해 정보 권한 관리도 지정할 수 있습니다. SharePoint는 템플릿에서 지정할 수 있는 설정과 거의 근접하게 선택할 수 있는 SharePoint 구성 설정이 있더라도 권한 정책 템플릿을 사용하지 않습니다.

SharePoint Server를 사용하는 경우에는 온-프레미스 서버와 RMS 클라우드 서비스 간의 릴레이 역할을 하는 RMS 커넥터를 배포하여 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]를 통해 정보 보호 기능을 사용할 수 있습니다. 자세한 내용은 [Azure 권한 관리 커넥터 배포](../Topic/Deploying_the_Azure_Rights_Management_Connector.md)를 참조하세요.

> [!NOTE]
> 현재 SharePoint와 함께 IRM을 사용하는 경우 다음과 같이 몇 가지 제한 사항이 있습니다.
> 
> -   기본값 또는 Azure 클래식 포털에서 관리하는 사용자 지정 템플릿을 사용할 수 없습니다.
> -   보호된 PDF 파일에 대한 .PPDF 파일 이름 확장명을 가진 파일은 지원되지 않습니다. 기본적으로 RMS를 지원하는 PDF Reader를 사용하는 경우 .PDF 파일 이름 확장명을 가지고 RMS에 의해 기본적으로 보호된 파일은 지원됩니다.
> -   모바일 장치의 Office는 아직 RMS를 지원하지 않기 때문에, 이들 장치는 RMS로 보호된 파일을 보려면 브라우저를 사용해야 하며, 파일은 읽기 전용으로 설정합니다.

Azure RMS는 문서를 SharePoint에서 처음 만들거나 라이브러리로 업로드할 때가 아니라 SharePoint에서 다운로드할 때 문서에 사용 제한 및 데이터 암호화를 적용합니다. 문서가 다운로드되기 전에 보호하는 방법에 대한 자세한 내용은 SharePoint 설명서에서 [비즈니스용 OneDrive 및 SharePoint Online의 데이터 암호화](https://technet.microsoft.com/library/dn905447.aspx)를 참조하세요.

SharePoint와 함께 Azure RMS를 사용하는 방법에 대한 자세한 내용은 Office 블로그에서 다음 게시물을 참조하세요. [SharePoint와 SharePoint Online의 정보 권한 관리의 새로운 기능](http://blogs.office.com/2012/11/09/whats-new-with-information-rights-management-in-sharepoint-and-sharepoint-online/)

## <a name="BKMK_FCIIntro"></a>Windows Server를 실행하고 FCI(파일 분류 인프라)를 사용하는 파일 서버
파일 분류 인프라를 사용하도록 Windows Server를 구성하면 이 파일 서버 리소스 관리자 기능이 로컬 파일을 검색하여 중요한 데이터가 포함되어 있는지를 확인할 수 있습니다. 이 기준을 충족하는 파일에는 관리자가 정의하는 분류 속성이 태그로 지정됩니다. 그러면 파일 분류 인프라가 분류에 따라 자동 작업을 수행할 수 있습니다. 이러한 작업 중 하나가 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]를 사용하고 Rights Management 커넥터(RMS 커넥터라고도 알려짐)를 배포하여 정보 보호를 적용하는 것입니다. 그런 다음 Office 파일은 Azure RMS를 통해 자동으로 보호됩니다.

모든 파일 형식을 보호하려면 RMS 커넥터를 사용하는 대신, [RMS 보호 도구](https://www.microsoft.com/en-us/download/details.aspx?id=47256)의 cmdlet를 사용하여 Windows PowerShell 스크립트를 실행합니다.

분류 정책은 완전하게 구성 가능하며 확장성이 뛰어나므로 권한이 있는/없는 사용자의 데이터 유출 가능성을 방지할 수 있습니다. 또한 네트워크 관리자에게 파일 액세스 권한을 요구하지 않는 정책을 구성할 수 있으므로 해당 관리자가 데이터를 유출할 위험도 줄일 수 있습니다.

Office용 RMS 커넥터를 배포하고 구성하는 방법에 대한 지침은 [Azure 권한 관리 커넥터 배포](../Topic/Deploying_the_Azure_Rights_Management_Connector.md)를 참조하세요.

모든 파일 형식에 대한 Windows PowerShell 스크립트를 사용하는 방법에 대한 지침은 [Windows Server FCI&#40;파일 분류 인프라&#41;를 사용하는 RMS 보호](../Topic/RMS_Protection_with_Windows_Server_File_Classification_Infrastructure__FCI_.md)를 참조하세요.

## <a name="BKMK_APIAppsIntro"></a>RMS API를 지원하는 기타 응용 프로그램
내부 개발자는 RMS SDK를 사용하여 기본적으로 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]를 지원하기 위해 LOB(기간 업무) 응용 프로그램을 작성할 수 합니다. 이러한 응용 프로그램과 정보 보호를 통합하는 방법은 응용 프로그램 작성 방법에 따라 다릅니다. 예를 들어 사용자가 최소한의 작업만 수행하면 통합이 자동으로 적용되도록 할 수도 있고, 보다 자세하게 사용자 지정된 환경에서는 파일에 정보 보호를 적용하기 위한 설정을 구성하라는 메시지를 사용자에게 표시할 수도 있습니다. SDK에 대한 자세한 내용은 [Microsoft Rights Management SDK](http://msdn.microsoft.com/library/hh552972%28v=vs.85%29.aspx)를 참조하세요.

마찬가지로 대부분의 소프트웨어 공급업체는 ERM(엔터프라이즈 권한 관리) 제품이라고도 하는 정보 보호 솔루션 제공을 위한 응용 프로그램을 제공합니다. 이러한 응용 프로그램의 널리 알려진 예로 특정 플랫폼에 대해 [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)]를 지원하는 PDF Reader가 있습니다.[Azure 권한 관리 요구 사항](../Topic/Requirements_for_Azure_Rights_Management.md) 항목의 [클라이언트 장치 기능](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_ClientCapabilities) 섹션에 있는 테이블을 사용하여 RMS(RMS 지원 응용 프로그램)를 지원하는 응용 프로그램을 식별한 다음, 웹 검색을 사용하여 응용 프로그램을 구입하거나 다운로드할 수 있습니다.

> [!TIP]
> 새로 릴리스된 응용 프로그램의 경우 [Azure 권한 관리에 대한 정보 및 지원](../Topic/Information_and_Support_for_Azure_Rights_Management.md)에 나와 있는 RMS 커뮤니티 채널을 확인하세요.

## 참고 항목
[Azure Rights Management 시작하기](../Topic/Getting_Started_with_Azure_Rights_Management.md)

