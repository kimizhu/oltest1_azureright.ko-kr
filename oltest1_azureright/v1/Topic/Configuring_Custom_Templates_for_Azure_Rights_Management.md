---
description: na
keywords: na
title: Configuring Custom Templates for Azure Rights Management
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 1775d8d0-9a59-42c8-914f-ce285b71ac1c
---
# Azure 권한 관리용 사용자 지정 템플릿 구성
Azure 권한 관리(Azure RMS)를 활성화하면, 액세스할 권한이 조직의 승인된 사용자로 제한되는 민감한 파일에 정책을 쉽게 적용할 수 있도록 두 가지의 기본 템플릿을 자동으로 사용할 수 있습니다. 이 두 개의 템플릿에는 다음의 권한 정책 제한이 있습니다.

-   보호된 콘텐츠의 읽기 전용 보기

    -   표시 이름: **&lt;조직 이름&gt; - 기밀 보기 전용**

    -   권한 지정: 콘텐츠 보기

-   보호된 콘텐츠의 사용 권한을 읽거나 수정하기

    -   표시 이름: **&lt;조직 이름&gt; - 기밀**

    -   권한 지정: 콘텐츠 보기, 파일 저장하기, 콘텐츠 편집하기, 할당된 권한 보기, 매크로 허용하기, 전달하기, 회신하기, 전체 회신하기

또한 [RMS 공유 응용 프로그램](http://technet.microsoft.com/library/dn339006.aspx)에서는 사용자가 원하는 권한 설정을 정의할 수 있습니다. 그리고 Outlook 클라이언트와 Outlook Web Access의 경우 전자 메일 메시지에 대해 **전달 금지** 옵션을 선택할 수 있습니다.

많은 조직에서는 기본 템플릿만으로도 충분할 수 있습니다. 그러나 원하는 경우 사용자 지정 권한 정책 템플릿을 만들 수 있습니다. 사용자 지정 템플릿을 만드는 이유는 다음과 같습니다.

-   모든 사용자가 아닌 조직의 하위 사용자 집합에 권한을 부여하는 템플릿을 원하는 경우

-   조직의 모든 사용자가 템플릿을 보고 선택할 수 있는 것이 아니라 일부 사용자만 응용 프로그램에서 템플릿(부서별 템플릿)을 보고 선택할 수 있도록 하려는 경우

-   보기와 편집은 허용하나 복사나 인쇄는 금지하는 것과 같이 템플릿에 사용자 지정 권한을 설정하고 싶을 경우

-   템플릿에 인터넷 연결 없이 해당 콘텐츠에 액세스할 수 있는지와 만료 날짜를 포함한 추가 옵션을 구성하고자 하는 경우

이러한 설정을 포함한 사용자 지정 템플릿을 선택하려면 우선 사용자 지정 템플릿을 만들고 구성한 후 이를 게시해야 합니다.

사용자 지정 템플릿을 구성하고 사용하는 도움말을 원하시면 다음 섹션을 참조하세요.

-   [사용자 지정 템플릿을 작성, 구성 및 게시하는 방법](../Topic/Configuring_Custom_Templates_for_Azure_Rights_Management.md#BKMK_HowToConfigureCustomTemplates)

-   [템플릿 복사 방법](../Topic/Configuring_Custom_Templates_for_Azure_Rights_Management.md#BKMK_HowToCopyTemplates)

-   [템플릿 제거(보관) 방법](../Topic/Configuring_Custom_Templates_for_Azure_Rights_Management.md#BKMK_HowToArchiveTemplates)

-   [사용자를 위한 템플릿 새로 고침](../Topic/Configuring_Custom_Templates_for_Azure_Rights_Management.md#BKMK_RefreshingTemplates)

-   [Windows PowerShell 참조](../Topic/Configuring_Custom_Templates_for_Azure_Rights_Management.md#BKMK_PowerShellTemplates)

## <a name="BKMK_HowToConfigureCustomTemplates"></a>사용자 지정 템플릿을 작성, 구성 및 게시하는 방법
Azure 클래식 포털에서 사용자 지정 템플릿을 만들고 관리합니다. 이 작업은 Azure 클래식 포털에서 직접 수행할 수도 있고, Office 365 관리 센터에 로그인하여 Rights Management의 **고급 기능**을 선택해도 됩니다. 그러면 Azure 클래식 포털로 리디렉션됩니다.

Rights Management에 대한 사용자 지정 템플릿을 생성, 구성, 게시하려면 다음 절차를 따르세요.

#### 사용자 지정 템플릿을 만들려면

1.  Office 365 관리 센터 또는 Azure 클래식 포털 중 어디에 로그인했는지에 따라 다음 중 하나를 수행하세요.

    -   [Office 365 관리 센터](https://portal.office.com/):

        1.  왼쪽 창에서 **서비스 설정**을 클릭합니다.

        2.  **서비스 설정** 페이지에서 **권한 관리**를 클릭합니다.

        3.  **정보 보호** 섹션에서 **관리**를 클릭합니다.

        4.  **권한 관리** 섹션에서 **고급 기능**을 클릭합니다.

            > [!NOTE]
            > 아직 권한 관리를 활성화하지 않았다면 우선 **활성화**를 클릭하고 작업을 확인합니다. 자세한 내용은 [Azure 권한 관리 활성화](../Topic/Activating_Azure_Rights_Management.md)를 참조하세요.
            > 
            > **고급 기능**을 이전에 클릭한 적이 없었다면 Rights Management를 활성화한 후 화면의 지침에 따라 Azure 클래식 포털에 액세스하는 데 필요한 무료 Azure 구독을 받습니다.

            **고급 기능**을 클릭하면 조직의 Azure Active Directory에 대한 **Rights Management**를 관리할 수 있는 Azure 클래식 포털이 로드됩니다.

    -   [Azure 클래식 포털](http://go.microsoft.com/fwlink/p/?LinkID=275081)에서 다음을 수행합니다.

        1.  왼쪽 창에서 **ACTIVE DIRECTORY**를 클릭합니다.

        2.  **Active Directory** 페이지에서 **권한 관리**를 클릭합니다.

        3.  Rights Management에 대해 관리할 디렉터리를 선택합니다.

        4.  권한 관리를 아직 활성화하지 않은 경우 **활성화**를 클릭하고 작업을 확인합니다.

            > [!NOTE]
            > 자세한 내용은 [Azure 권한 관리 활성화](../Topic/Activating_Azure_Rights_Management.md)를 참조하세요.

2.  새 템플릿 만들기

    -   Azure 클래식 포털의 **Rights Management 시작** 빠른 시작 페이지에서 **새 권한 정책 템플릿 만들기**를 클릭합니다.

        Office 365에 대한 지침을 진행한 후에 이 페이지를 즉시 표시되지 않으면 Azure 클래식 포털에 대한 위의 탐색 지침을 사용합니다.

3.  **새 권한 정책 템플릿 추가** 페이지에서 사용자에게 표시할 템플릿 이름과 설명을 입력하려는 언어를 선택합니다. 나중에 언어를 더 추가할 수 있습니다. 그 후에 고유한 이름과 설명을 입력하고 완료 단추를 클릭합니다.

이제 **Rights Management가 시작되었습니다.** 빠른 시작 페이지에서 **권한 정책 템플릿 관리**를 클릭합니다. 새로 만든 템플릿이 템플릿 목록에 추가되어 **보관됨** 상태로 표시됩니다. 이 단계에서는 템플릿이 만들어졌지만 구성되지 않아 사용자에게 보이지 않습니다.

#### 사용자 지정 템플릿을 구성 및 게시하려면

1.  Azure 클래식 포털의 **템플릿** 페이지에서 새로 만든 템플릿을 선택합니다.

2.  **템플릿이 추가되었습니다.** 빠른 시작 페이지의 1단계 **사용자 및 그룹 권한 구성**에서 **시작**을 클릭한 다음 **지금 시작** 또는 **추가**를 클릭합니다. 그런 후에 새 템플릿을 통해 보호되는 콘텐츠 사용 권한을 부여할 사용자와 그룹을 선택합니다.

    > [!NOTE]
    > 선택되는 사용자 또는 그룹은 반드시 이메일 주소가 있어야 합니다. 프로덕션 환경에서는 거의 언제나 이메일 주소가 있지만 단순한 테스트 환경에서는 사용자 계정 또는 그룹에 이메일 주소를 추가해야 할 수도 있습니다.

    모범 사례로, 사용자가 아닌 그룹을 사용하면 템플릿의 관리가 간소화됩니다. Active Directory 온-프레미스에서 Azure AD로 동기화하는 경우 보안 그룹 또는 배포 그룹 중 하나인 메일 사용 가능 그룹을 사용할 수 있습니다. 그렇지만 조직 내의 모든 사용자에게 권한을 부여하고자 하는 경우에는 여러 개의 그룹을 지정하는 것 보다 기본 템플릿 중 하나를 복사하는 것이 더 효율적입니다. 자세한 내용은 이 항목의 [템플릿 복사 방법](../Topic/Configuring_Custom_Templates_for_Azure_Rights_Management.md#BKMK_HowToCopyTemplates) 섹션을 참조하세요.

    > [!TIP]
    > 나중에 [Azure 권한 관리에 대한 Windows PowerShell 모듈](https://technet.microsoft.com/library/jj585012.aspx)을 사용하고 다음 방법 중 하나를 사용하여 조직 외부 사용자를 템플릿에 추가할 수 있습니다.
    > 
    > -   **권한 정의 개체를 사용하여 템플릿 업데이트**:    권한 정의 개체에서 외부 전자 메일 주소 및 해당 권한을 지정한 다음 템플릿을 업데이트할 때 사용합니다.[New-AadrmRightsDefinition](https://msdn.microsoft.com/library/azure/dn727080.aspx) cmdlet을 통해 변수를 만든 다음 [Set-AadrmTemplateProperty](https://msdn.microsoft.com/library/azure/dn727076.aspx) cmdlet을 통해 이 변수를 -RightsDefinition 매개 변수에 제공하여 기존 템플릿을 수정하는 방식으로 권한 정의 개체를 지정합니다. 그러나 기존 템플릿에 이러한 사용자를 추가하는 경우 새로운 외부 사용자뿐 아니라 템플릿의 기존 그룹에 대해서도 권한 정의 개체를 정의해야 합니다.
    > -   **업데이트된 템플릿 내보내기, 편집 및 가져오기**: [Export-AadrmTemplate](https://msdn.microsoft.com/library/azure/dn727078.aspx) cmdlet을 사용하여 템플릿을 파일로 내보냅니다. 그런 후 이 파일을 편집하여 이러한 사용자의 외부 전자 메일 주소와 해당 권한을 기존 그룹 및 권한에 추가할 수 있습니다. 그런 후 [Import-AadrmTemplate](https://msdn.microsoft.com/library/azure/dn727077.aspx) cmdlet을 사용하여 이러한 변경 내용을 Azure RMS로 다시 가져올 수 있습니다.

3.  다음 단추를 클릭한 후 선택한 사용자 및 그룹에 나열된 권한 중 하나를 할당합니다.

    각 권한(및 사용자 지정 권한)에 대한 자세한 내용은 표시된 설명을 참조하세요. 더 자세한 내용은 [Azure 권한 관리에 대한 사용 권한 구성](../Topic/Configuring_Usage_Rights_for_Azure_Rights_Management.md)에서 제공합니다. 그러나 RMS를 지원하는 응용 프로그램에서는 이러한 권한의 구현 방법이 다를 수 있습니다. 사용자를 위해 템플릿을 배포하기 전에 해당 설명서를 참조하고 사용자가 동작 확인을 위해 사용하는 응용 프로그램으로 직접 테스트를 수행합니다. 이 테스트 동안 관리자만 이 템플릿을 볼 수 있도록 하려면 템플릿을 부서별 템플릿으로 만듭니다(6단계).

4.  **사용자 지정**을 선택한 경우 다음 단추를 클릭하고 해당 사용자 지정 권한을 선택합니다.

    사용가능한 개별 권한을 원하는 대로 조합하여 사용할 수 있지만 어떤 응용 프로그램에서는 일부 권한이 다른 개별 권한에 종속될 수도 있습니다. 그런 경우 종속 권한은 자동으로 선택됩니다.

    > [!TIP]
    > **콘텐츠 복사 및 추출** 권한을 추가하여 정보 복구를 담당하는 다른 역할의 선택된 관리자 또는 사용자에게 이 권한을 부여하는 것이 좋습니다. 이 권한이 부여된 관리자나 사용자는 이 템플릿을 사용하여 보호될 파일과 메일에서 필요에 따라 보호를 제거할 수 있습니다. 템플릿 수준에서 보호를 제거하는 기능은 슈퍼 사용자 기능을 사용하는 경우보다 세분화된 제어를 제공합니다.

5.  완료 단추를 클릭합니다.

6.  일부 사용자만 응용 프로그램 템플릿 목록에서 해당 템플릿을 볼 수 있도록 하려면 **범위**를 클릭하여 이 템플릿을 부서별 템플릿으로 구성하고 **지금 시작**을 클릭합니다. 그렇지 않은 경우 9단계로 이동합니다.

    부서별 템플릿에 대한 추가 정보: 기본적으로 Azure 디렉터리의 모든 사용자가 게시된 모든 템플릿을 볼 수 있으며 콘텐츠를 보호하려는 경우 응용 프로그램에서 이러한 템플릿을 선택할 수 있습니다. 특정 사용자만 게시된 템플릿의 일부를 볼 수 있도록 하려면 해당 템플릿의 범위를 이러한 사용자로 지정해야 합니다. 그러면 이러한 사용자만 해당 템플릿을 선택할 수 있게 됩니다. 지정하지 않은 다른 사용자는 템플릿을 볼 수 없으므로 선택할 수도 없습니다. 이 방식은 사용자가 특히 특정 그룹 또는 부서에서 사용하도록 고안된 템플릿을 만들 때, 올바른 템플릿을 쉽게 선택할 수 있도록 합니다. 사용자에게는 본인을 위해 고안된 템플릿만 표시됩니다.

    예를 들어 재무 담당 부서의 멤버에게 읽기 전용 권한이 적용되는 인사 관리 부서용 템플릿을 만들었습니다. 인사 관리 부서의 멤버만 권한 관리 공유 응용 프로그램을 사용할 때 이 템플릿을 적용할 수 있으므로 템플릿 범위를 HumanResources라는 전자 메일 사용 가능 그룹으로 지정합니다. 그러면 이 그룹의 구성원만 이 템플릿을 보고 적용할 수 있습니다.

7.  **템플릿 표시 여부** 페이지에서 RMS 지원 응용 프로그램에서 템플릿을 보고 선택할 수 있는 사용자 및 그룹을 선택합니다. 앞에 나온 것처럼 사용자보다는 그룹을 사용하는 것이 좋습니다. 또한 선택한 그룹 또는 사용자에게 전자 메일 주소가 있어야 합니다.

8.  다음 단추를 클릭하고 부서별 템플릿에 대해 응용 프로그램 호환성을 구성해야 하는지 여부를 결정합니다. 응용 프로그램 호환성을 구성해야 하는 경우에는 **응용 프로그램 호환성**을 클릭하고 확인란을 선택한 후에 **완료**를 클릭합니다.

    응용 프로그램 호환성을 구성해야 하는 이유 모든 응용 프로그램에서 부서별 템플릿을 지원할 수 있는 것은 아니기 때문입니다. 이것이 가능하려면 템플릿을 다운로드하기 전에 먼저 응용 프로그램이 RMS 서비스에서 인증을 받아야 합니다. 인증 프로세스가 발생하지 않으면 기본적으로 부서별 템플릿이 전혀 다운로드되지 않습니다. 모든 부서별 템플릿을 다운로드하도록 지정하고, 응용 프로그램 호환성을 구성하고, **응용 프로그램에서 사용자 ID를 지원하지 않는 경우 이 템플릿을 모든 사용자에게 표시** 확인란을 선택하여 이 동작을 재정의할 수 있습니다.

    예를 들어 인사 관리 예제에서 부서별 템플릿에 대한 응용 프로그램 호환성을 구성하지 않으면 Exchange OWA 및 Exchange ActiveSync에서 현재 부서별 템플릿을 지원하지 않으므로 인사 관리 부서의 사용자만 RMS 공유 응용 프로그램을 사용할 때 부서별 템플릿을 볼 수 있고 다른 사용자는 Exchange Server 2013의 OWA(Outlook Web Access)를 사용할 때 부서별 템플릿을 볼 수 없습니다. 응용 프로그램 호환성을 구성하여 이 기본 동작을 재정의하는 경우 인사 관리 부서의 사용자만 RMS 공유 응용 프로그램을 사용할 때 부서별 템플릿을 볼 수 있고 그 외 모든 사용자는 OWA(Outlook Web Access)를 사용할 때 부서별 템플릿을 볼 수 있습니다. 사용자가 Exchange Online의 OWA 또는 Exchange ActiveSync를 사용하는 경우 Exchange Online의 템플릿 상태(보관 또는 게시)에 따라 모든 사용자가 부서별 템플릿을 볼 수 있거나 어떤 사용자도 부서별 템플릿을 볼 수 없습니다.

    Office 2016은 기본적으로 부서별 템플릿을 지원하며 최신 Office 업데이트가 적용된 Office 2013도 그렇습니다([KB 3054853](https://support.microsoft.com/kb/3054853)).

    > [!NOTE]
    > 부서별 템플릿을 아직 기본적으로 지원하지 않는 응용 프로그램을 사용하는 경우에는 사용자 지정 RMS 템플릿 다운로드 스크립트 또는 기타 도구를 사용하여 이러한 템플릿을 로컬 RMS 클라이언트 폴더로 배포할 수 있습니다. 그러면 이러한 응용 프로그램은 템플릿 범위에 대해 선택한 사용자 및 그룹에만 부서별 템플릿을 올바르게 표시합니다.
    > 
    > -   Office 2010에서 클라이언트 폴더는 **%localappdata%\Microsoft\DRM\Templates**입니다.
    > -   모든 템플릿을 다운로드한 클라이언트 컴퓨터에서 템플릿 파일을 복사하여 다른 컴퓨터에 붙여넣습니다.
    > 
    > [Microsoft Connect 사이트에서 사용자 지정 RMS 템플릿 스크립트를 다운로드](http://go.microsoft.com/fwlink/?LinkId=524506)할 수 있습니다. 이 링크를 클릭했을 때 오류가 표시되면 Microsoft Connect에 등록되지 않은 경우일 수 있습니다.   등록하려면 다음을 수행합니다.
    > 
    > 1.  [Microsoft Connect 사이트](http://www.connect.microsoft.com)로 이동하여 Microsoft 계정으로 로그인합니다.
    > 2.  **디렉터리**를 클릭하고 **현재 피드백을 수락하지 않는 Connect 제품 보기** 범주를 선택합니다.
    > 3.  **Rights Management Services**를 검색하고 **Microsoft RMS Enterprise Features** 프로그램에 대해 **가입**을 클릭합니다.

9. **구성**을 클릭하고 이 언어의 템플릿 이름 및 설명과 함께 사용하는 언어를 추가합니다. 여러 가지의 언어를 사용하는 사용자들이 있다면 그들이 사용하는 각 언어를 추가하고 해당 언어로 된 이름과 설명을 준비하는 것이 중요합니다. 사용자는 클라이언트 운영 체제와 같은 언어로 기재된 템플릿 이름과 설명을 보게 되므로 문서 또는 이메일 메시지에 적용된 정책을 이해할 수 있습니다. 클라이언트 운영 체제와 일치하는 언어가 없는 경우에는 템플릿을 처음 만들 때 설정했던 언어 및 설명으로 변경되어 표시됩니다.

    다음 설정을 변경하고 싶은지 확인하세요.

    |Setting|추가 정보|
    |-----------|---------|
    |**콘텐츠 만료**|템플릿으로 보호되는 파일이 열리지 않아야 하는 경우 해당 템플릿에 대해 날짜 또는 일수를 설정합니다. 파일에 보호 기능이 적용되는 시점부터 시작해서 특정 일수를 정하거나 날짜를 지정할 수 있습니다.<br /><br />날짜를 지정하면 현재 표준 시간대에서 자정까지 유효합니다.|
    |**오프라인 액세스**|이 설정을 사용해서 인터넷이 연결되지 않은 경우에도 사용자가 보호된 파일을 반드시 열 수 있어야 한다는 요구 사항으로 인해 제기되는 보안 요구 사항과의 균형을 맞출 수 있습니다.<br /><br />인터넷이 연결되지 않은 경우에는 해당 콘텐츠를 사용할 수 없도록 지정하거나 지정된 일수 동안에만 해당 콘텐츠를 사용할 수 있게 하는 경우, 임계치에 다다르면 사용자는 다시 인증받아야 하며 사용자의 액세스가 기록됩니다. 이런 경우가 발생하고 자격 증명이 캐시되지 않은 경우 파일을 열려고 하면 우선 로그인하라는 메시지가 표시됩니다.<br /><br />재인증과 더불어 정책 및 사용자 그룹 멤버 자격이 재평가됩니다. 이는 사용자가 파일에 마지막으로 액세스한 이후에 정책 또는 그룹 멤버 자격이 변경되었다면 같은 파일에 대해 다른 액세스 결과를 겪을 수도 있다는 의미입니다.|

10. 템플릿이 사용자에 대해 적절하게 구성되어 있으면 **게시**를 클릭하여 사용자에 대해 템플릿을 표시한 다음 **저장**을 클릭합니다.

11. 클래식 포털에서 뒤로 단추를 클릭하여 **템플릿** 페이지로 돌아갑니다. 그러면 이 페이지의 템플릿 상태가 **게시됨**으로 업데이트됩니다.

템플릿을 변경하려면 해당 템플릿을 선택하고 빠른 시작 단계를 다시 사용하거나 다음 옵션 중 하나를 선택합니다.

-   사용자 및 그룹을 추가하고 그 사용자 및 그룹의 권한을 설정하려면: **권한**과 **추가**를 차례로 클릭합니다.

-   이전에 선택했던 사용자 또는 그룹을 제거하려면: **권한**을 클릭하고 목록에서 사용자나 그룹을 선택한 후에 **삭제**를 클릭합니다.

-   템플릿을 보고 응용 프로그램에서 선택할 수 있는 사용자를 변경하려면 **범위**를 클릭한 다음 **추가**, **삭제** 또는 **응용 프로그램 호환성**을 클릭합니다.

-   모든 사용자가 특정 템플릿을 더 이상 볼 수 없도록 하려면 **구성**, **보관**, **저장**을 차례로 클릭합니다.

-   다른 구성을 변경하려면: **구성**을 클릭하고 원하는 대로 변경한 다음 **보관**을 클릭합니다.

> [!WARNING]
> 이전에 저장된 템플릿을 변경하는 경우, 클라이언트는 해당 컴퓨터에서 템플릿이 새로 고침될 때까지 해당 템플릿의 변경을 볼 수 없게 됩니다. 자세한 내용은 이 항목의 [사용자를 위한 템플릿 새로 고침](../Topic/Configuring_Custom_Templates_for_Azure_Rights_Management.md#BKMK_RefreshingTemplates) 섹션을 참조하세요.

## <a name="BKMK_HowToCopyTemplates"></a>템플릿 복사 방법
기존 템플릿과 설정이 매우 비슷한 새 템플릿을 만들려면 **템플릿** 페이지에서 원본 템플릿을 선택하고 **복사**를 클릭한 후에 고유한 이름을 지정하고 필요한 대로 템플릿을 변경합니다.

> [!IMPORTANT]
> 템플릿을 복사하면 **게시됨** 또는 **보관됨** 상태도 함께 복사됩니다. 그러므로 게시된 템플릿을 복사하면 변경하지 않는 한, 해당 상태가 즉시 게시됩니다.

사용자 지정 템플릿과 기본 템플릿을 복사할 수 있습니다. 모범 사례로, 조직 내의 모든 사용자에게 권한을 부여하는 템플릿을 원한다면 새 사용자 지정 템플릿을 만드는 대신에 기본 템플릿 중 하나를 복사하세요. 이 방법을 사용하면 모든 사용자를 지정하기 위해 다수의 그룹을 선택하거나 만들 필요가 없습니다. 그러나 이 시나리오에서는 추가 언어를 위해 복사된 템플릿에 새로운 이름과 설명을 지정해야 함에 유의해 주세요.

## <a name="BKMK_HowToArchiveTemplates"></a>템플릿 제거(보관) 방법
기본 템플릿은 삭제할 수 없지만 사용자에게 보이지 않도록 보관할 수 있습니다.

마찬가지로 사용자 지정 템플릿을 게시했으며 사용자에게 해당 템플릿을 더 이상 표시하지 않으려는 경우 템플릿을 편집하고 **구성** 페이지에서 **보관** 및 **저장**을 선택하면 됩니다. 또는 **템플릿** 페이지에서 템플릿을 선택하고 **보관**을 선택할 수도 있습니다.

기본 템플릿은 편집할 수 없으므로 이러한 템플릿을 보관하려면 **템플릿** 페이지에서 **보관** 옵션을 사용해야 합니다. Outlook **전달 금지** 옵션은 보관할 수 없습니다.

#### 기본 템플릿을 제거하려면

-   **템플릿** 페이지에서 기본 서식 파일을 선택하고 **보관**을 클릭합니다.

상태가 **게시됨**에서 **보관됨**으로 변경됩니다. 템플릿을 다시 게시하려면 해당 템플릿을 선택하고 **게시**를 클릭합니다.

## <a name="BKMK_RefreshingTemplates"></a>사용자를 위한 템플릿 새로 고침
Azure RMS를 사용하는 경우 사용자가 응용 프로그램에서 선택할 수 있도록 템플릿이 자동으로 클라이언트 컴퓨터로 다운로드됩니다. 그렇지만 템플릿을 변경하려면 다음의 추가 단계를 진행해야 할 수도 있습니다.

|응용 프로그램 또는 서비스|템플릿을 변경한 후 새로 고침하는 방법|
|------------------|-------------------------|
|Exchange Online|템플릿을 새로 고침하려면 수동 구성이 필요함<br /><br />구성 단계를 보려면 [Exchange Online 전용: 변경된 사용자 지정 템플릿을 다운로드하기 위한 Exchange 구성 방법](../Topic/Configuring_Custom_Templates_for_Azure_Rights_Management.md#BKMK_ExchangeOnlineTemplatesUpdate) 섹션을 확장하세요.|
|Office 365|자동으로 새로 고침됨 - 추가 단계 불필요|
|Office 2016 및 Office 2013<br /><br />Windows용 RMS 공유 응용 프로그램|자동으로 새로 고침 – 예약형:<br /><br />-   이러한 최신 버전 Office의 경우: 기본 새로 고침 간격은 7일입니다.<br />-   Windows용 RMS 공유 응용 프로그램: 1.0.1784.0 버전부터 기본 새로 고침 간격은 1일입니다. 이전 버전의 기본 새로 고침 간격은 7일입니다.<br /><br />이 일정보다 더 자주 강제로 새로 고침하려면 [Office 2016, Office 2013 및 Windows용 RMS 공유 응용 프로그램: 변경된 사용자 지정 템플릿을 강제로 새로 고침하는 방법](#BKMK_Office2013ForceUpdate) 섹션을 확장하세요.|
|Office 2010|사용자 로그인 시 새로 고침됨<br /><br />강제로 새로 고침하려면 사용자에게 로그오프한 후 다시 로그인하도록 요청하거나 강제로 적용합니다. 또는 다음 섹션, [Office 2010 전용: 변경된 사용자 지정 템플릿을 강제로 새로 고침하는 방법](#BKMK_Office2010ForceUpdate)을 참조하세요.|
RMS 공유 응용 프로그램을 사용하는 모바일 장치의 경우 템플릿은 추가 구성이 필요 없이 자동으로 다운로드되고 필요한 경우 새로 고침됩니다.

### <a name="BKMK_ExchangeOnlineTemplatesUpdate"></a>Exchange Online 전용: 변경된 사용자 지정 템플릿을 다운로드하기 위한 Exchange 구성 방법
Exchange Online을 위해 이미 IRM(정보 Rights Management)을 구성했다면 Exchange Online의 Windows PowerShell을 사용해 다음과 같이 변경할 때까지 사용자는 사용자 지정 템플릿을 다운로드할 수 없습니다.

> [!NOTE]
> Exchange Online에서 Windows PowerShell을 사용하는 방법에 대한 자세한 내용은 [Exchange Online에서 PowerShell 사용](https://technet.microsoft.com/library/jj200677%28v=exchg.160%29.aspx)을 참조하세요.

템플릿을 변경할 때마다 이 절차를 진행해야 합니다.

##### Exchange Online을 위해 템플릿을 업데이트하려면

1.  Exchange Online에서 Windows PowerShell을 사용하여 서비스에 연결:

    1.  Office 365 사용자 이름 및 암호 입력:

        ```
        $Cred = Get-Credential
        ```

    2.  다음 두 명령을 실행하여 Exchange Online 서비스에 연결합니다.

        ```
        $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell/ -Credential $Cred -Authentication Basic –AllowRedirection
        ```

        ```
        Import-PSSession $Session
        ```

2.  Azure RMS에서 TPD(신뢰할 수 있는 게시 도메인)를 다시 가져오기하려면 [Import-RMSTrustedPublishingDomain](http://technet.microsoft.com/library/jj200724%28v=exchg.160%29.aspx) cmdlet을 사용하세요.

    ```
    Import-RMSTrustedPublishingDomain -Name "<TPD name>" -RefreshTemplates -RMSOnline
    ```
    예를 들어 TPD 이름이 대부분의 조직에서 일반적으로 사용하는 이름인 **RMS Online - 1**이라면 다음을 입력합니다. **Import-RMSTrustedPublishingDomain -Name "RMS Online - 1" -RefreshTemplates -RMSOnline**

    > [!NOTE]
    > TPD 이름이 유효한지 확인하려면 [Get-RMSTrustedPublishingDomain](http://technet.microsoft.com/library/jj200707%28v=exchg.160%29.aspx) cmdlet을 사용합니다.

3.  템플릿이 성공적으로 가져오기되었는지 확인하려면 몇 분 정도 기다린 후 [Get-RMSTemplate](http://technet.microsoft.com/library/dd297960%28v=exchg.160%29.aspx) cmdlet을 실행하고 Type을 All로 설정합니다. 예를 들면 다음과 같습니다.

    ```
    Get-RMSTemplate -TrustedPublishingDomain "RMS Online - 1" -Type All
    ```
    > [!TIP]
    > 나중에 템플릿을 보관하는 경우 템플릿 이름이나 GUID를 쉽게 복사할 수 있도록 출력 복사본을 유지하는 것이 유용합니다.

4.  Outlook Web App에서 사용할 수 있게 하려는 가져온 각 템플릿에 대해 [Set-RMSTemplate](http://technet.microsoft.com/library/hh529923%28v=exchg.160%29.aspx) cmdlet을 사용하고 Distributed로 유형을 설정해야 합니다.

    ```
    Set-RMSTemplate -Identity "<name  or GUID of the template>" -Type Distributed
    ```
    Outlook Web Access에서 24시간 동안 UI를 캐시하므로 사용자에게 새 템플릿이 최대 하루 동안 표시되지 않을 수 있습니다.

또한 템플릿(사용자 지정 또는 기본)을 보관하고 Office 365가 포함된 Exchange Online을 사용하는 경우, Exchange ActiveSync 프로토콜을 사용하는 모바일 장치 또는 Outlook Web App을 이용하는 사용자는 보관된 템플릿을 계속 볼 수 있습니다.

그러면 Exchange Online의 Windows PowerShell을 사용하여 서비스에 연결한 템플릿은 사용자에게 더는 표시되지 않습니다. 다음 명령을 실행하여 [Set-RMSTemplate](http://technet.microsoft.com/library/hh529923%28v=exchg.160%29.aspx) cmdlet을 사용하세요.

```
Set-RMSTemplate -Identity "<name or GUID of the template>" -Type Archived
```

### <a name="BKMK_Office2013ForceUpdate"></a>Office 2016, Office 2013 및 Windows용 RMS 공유 응용 프로그램: 변경된 사용자 지정 템플릿을 강제로 새로 고침하는 방법
Office 2016, Office 2013 또는 Windows용 RMS(Rights Management) 공유 응용 프로그램을 실행 중인 컴퓨터에서 레지스트리를 편집하여 컴퓨터에서 변경된 템플릿을 기본값보다 더 자주 새로 고치도록 자동 일정을 변경할 수 있습니다. 또한 레지스트리의 기존 데이터를 삭제하여 즉각적인 새로 고침을 강제 실행할 수 있습니다.

> [!WARNING]
> 레지스트리 편집기를 잘못 사용하면 운영 체제를 재설치해야 할 만큼 심각한 문제가 유발될 수 있습니다. Microsoft는 레지스트리 편집기를 잘못 사용해서 유발된 문제를 사용자가 해결할 수 있으리라고 보장할 수 없습니다. 레지스트리 편집기 사용에 따른 위험은 사용자가 책임져야 합니다.

##### 자동 일정을 변경하려면

1.  레지스트리 편집기를 사용하여 다음 레지스트리 값 중 하나를 만들고 설정합니다.

    -   업데이트 빈도(일)를 설정하려면(최소 1일):  이름이 **TemplateUpdateFrequency**인 새 레지스트 값을 만들고 데이터에 정수 값을 정의합니다. 즉 다운로드한 템플릿에 대한 모든 변경 사항을 다운로드하는 주기를 일 단위로 지정합니다. 다음 표를 사용하여 새 레지스트리 값을 만들기 위한 레지스트리 경로를 확인합니다.

        |레지스트리 경로|Type|값|
        |------------|--------|-----|
        |HKEY_CURRENT_USER\Software\Classes\Local Settings\Software\Microsoft\MSIPC|REG_DWORD|TemplateUpdateFrequency|

    -   업데이트 주기를 초 단위로 설정하려면(최소 1초):  이름이 **TemplateUpdateFrequencyInSeconds**인 새 레지스트 값을 만들고 데이터에 정수 값을 정의합니다. 즉 다운로드한 템플릿에 대한 모든 변경 사항을 다운로드하는 주기를 초 단위로 지정합니다. 다음 표를 사용하여 새 레지스트리 값을 만들기 위한 레지스트리 경로를 확인합니다.

        |레지스트리 경로|Type|값|
        |------------|--------|-----|
        |HKEY_CURRENT_USER\Software\Classes\Local Settings\Software\Microsoft\MSIPC|REG_DWORD|TemplateUpdateFrequencyInSeconds|

    두 레지스트리 값 모두가 아니라 둘 중 하나만 만들어 설정해야 합니다. 모두 있는 경우 **TemplateUpdateFrequency**를 무시합니다.

2.  템플릿의 즉시 새로 고침을 강제 실행한 경우 다음 절차를 진행합니다. 그렇지 않으면 Office 응용 프로그램과 파일 탐색기 인스턴스를 지금 다시 시작합니다.

##### 즉시 새로 고침을 강제 실행하려면

1.  레지스트리 편집기에서 **LastUpdatedTime** 값의 데이터를 삭제합니다. 예를 들어, 데이터가**2015-04-20T15:52**;로 표시된다면 2015-04-20T15:52를 삭제하여 아무 데이터도 표시되지 않게 합니다. 다음 표를 사용하여 이 레지스트리 값 데이터를 삭제하기 위한 레지스트리 경로를 확인합니다.

    |레지스트리 경로|Type|값|
    |------------|--------|-----|
    |HKEY_CURRENT_USER\Software\Classes\Local Settings\Software\Microsoft\MSIPC\&lt;MicrosoftRMS_FQDN&gt;\Template|REG_SZ|LastUpdatedTime|
    > [!TIP]
    > 레지스트리 경로에서 *&lt;MicrosoftRMS_FQDN&gt;*은 사용자의 Microsoft RMS 서비스 FQDN을 나타냅니다. 이 값을 확인하려면:
    > 
    > 1.  Azure RMS에 대해 [Get-AadrmConfiguration](https://msdn.microsoft.com/library/windowsazure/dn629410.aspx) cmdlet을 실행합니다. 아직 Azure RMS용 Windows PowerShell 모듈을 설치하지 않은 경우 [Azure 권한 관리용 Windows PowerShell 설치](../Topic/Installing_Windows_PowerShell_for_Azure_Rights_Management.md)를 참조하세요.
    > 2.  출력에서 **LicensingIntranetDistributionPointUrl** 값을 식별합니다.
    > 
    >     예를 들면 다음과 같습니다. **LicensingIntranetDistributionPointUrl   : https://5c6bb73b-1038-4eec-863d-49bded473437.rms.na.aadrm.com/_wmcs/licensing**
    > 3.  이 값의 문자열에서 **https://** 및 **/_wmcs/licensing**을 제거합니다. 나머지 값이 Microsoft RMS 서비스 FQDN입니다. 이 예에서 Microsoft RMS 서비스 FQDN 값은 다음과 같습니다.
    > 
    >     **5c6bb73b-1038-4eec-863d-49bded473437.rms.na.aadrm.com**

2.  다음 폴더와, 그 안의 모든 파일을 삭제합니다:**%localappdata%\Microsoft\MSIPC\Templates**

3.  Office 응용 프로그램과 파일 탐색기 인스턴스를 지금 시작합니다.

### <a name="BKMK_Office2010ForceUpdate"></a>Office 2010 전용: 변경된 사용자 지정 템플릿을 강제로 새로 고침하는 방법
Office 2010을 실행하는 컴퓨터에서 레지스트리를 편집하면 사용자가 로그오프하고 다시 로그인할 때까지 기다리지 않고 컴퓨터에서 변경된 템플릿을 새로 고치도록 값을 설정할 수 있습니다. 또한 레지스트리의 기존 데이터를 삭제하여 즉각적인 새로 고침을 강제 실행할 수 있습니다.

> [!WARNING]
> 레지스트리 편집기를 잘못 사용하면 운영 체제를 재설치해야 할 만큼 심각한 문제가 유발될 수 있습니다. Microsoft는 레지스트리 편집기를 잘못 사용해서 유발된 문제를 사용자가 해결할 수 있으리라고 보장할 수 없습니다. 레지스트리 편집기 사용에 따른 위험은 사용자가 책임져야 합니다.

##### 업데이트 주기를 변경하려면

1.  레지스트리 편집기에서 이름이 **UpdateFrequency**인 새 레지스트 값을 만들고 데이터에 정수 값을 정의합니다. 즉 다운로드한 템플릿에 대한 모든 변경 사항을 다운로드하는 주기를 일 단위로 지정합니다. 다음 표를 사용하여 새 레지스트리 값을 만들기 위한 레지스트리 경로를 확인합니다.

    |레지스트리 경로|Type|값|
    |------------|--------|-----|
    |HKEY_CURRENT_USER\Software\Microsoft\MSDRM\TemplateManagement|REG_DWORD|UpdateFrequency|

2.  템플릿의 즉시 새로 고침을 강제 실행한 경우 다음 절차를 진행합니다. 그렇지 않은 경우 Office 응용 프로그램을 지금 다시 시작합니다.

##### 즉시 새로 고침을 강제 실행하려면

1.  레지스트리 편집기에서 **LastUpdatedTime** 값의 데이터를 삭제합니다. 예를 들어, 데이터가**2015-04-20T15:52**;로 표시된다면 2015-04-20T15:52를 삭제하여 아무 데이터도 표시되지 않게 합니다. 다음 표를 사용하여 이 레지스트리 값 데이터를 삭제하기 위한 레지스트리 경로를 확인합니다.

    |레지스트리 경로|Type|값|
    |------------|--------|-----|
    |HKEY_CURRENT_USER\Software\Microsoft\MSDRM\TemplateManagement|REG_SZ|lastUpdatedTime|

2.  다음 폴더와, 그 안의 모든 파일을 삭제합니다:**%localappdata%\Microsoft\MSIPC\Templates**

3.  Office 응용 프로그램을 다시 시작합니다.

## <a name="BKMK_PowerShellTemplates"></a>Windows PowerShell 참조
템플릿을 만들고 관리하기 위해 Azure 클래식 포털에서 수행할 수 있는 모든 작업은 Windows PowerShell을 사용하여 명령줄에서도 수행할 수 있습니다. 또한 테넌트 간에 템플릿을 복사하거나 다국어 이름/설명 등 템플릿의 복잡한 속성을 대량으로 편집할 수 있도록 템플릿을 내보내고 가져올 수도 있습니다.

또한 내보내기 및 가져오기를 사용하여 사용자 지정 템플릿을 백업하고 복원할 수도 있습니다. 가장 좋은 방법은 사용자 지정 템플릿을 정기적으로 백업하는 것입니다. 이렇게 하면 의도하지 않은 변경을 수행한 경우 이전 버전으로 쉽게 되돌릴 수 있습니다.

> [!IMPORTANT]
> Windows PowerShell을 사용하여 Azure RMS 권한 정책 템플릿을 만들고 관리하려면 [Azure RMS용 Windows PowerShell 모듈](http://go.microsoft.com/fwlink/?LinkId=257721) 버전 2.0.0.0 이상이 필요합니다.
> 
> 이전에 이 Windows PowerShell 모듈을 설치한 경우 PowerShell 창에서 다음 명령을 실행하여 버전 번호를 확인합니다:`(Get-Module aadrm -ListAvailable).Version`

설치 지침은 [Azure 권한 관리용 Windows PowerShell 설치](../Topic/Installing_Windows_PowerShell_for_Azure_Rights_Management.md)를 참조하세요.

템플릿 만들기 및 관리를 지원하는 cmdlet

-   [Add-AadrmTemplate](https://msdn.microsoft.com/library/azure/dn727075.aspx)

-   [Export-AadrmTemplate](https://msdn.microsoft.com/library/azure/dn727078.aspx)

-   [Get-AadrmTemplate](https://msdn.microsoft.com/library/azure/dn727079.aspx)

-   [Get-AadrmTemplateProperty](https://msdn.microsoft.com/library/azure/dn727081.aspx)

-   [Import-AadrmTemplate](https://msdn.microsoft.com/library/azure/dn727077.aspx)

-   [New-AadrmRightsDefinition](https://msdn.microsoft.com/library/azure/dn727080.aspx)

-   [Remove-AadrmTemplate](https://msdn.microsoft.com/library/azure/dn727082.aspx)

-   [Set-AadrmTemplateProperty](https://msdn.microsoft.com/library/azure/dn727076.aspx)

## 다음 단계
Azure 권한 관리용으로 사용자 지정 템플릿을 구성한 후에는 [Azure 권한 관리 배포 로드맵](../Topic/Azure_Rights_Management_Deployment_Roadmap.md)을 사용하여 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]를 사용자와 관리자에게 배포하기 전에 수행할 수 있는 다른 구성 단계가 있는지 확인합니다. 수행해야 하는 다른 구성 단계가 없는 경우 조직의 성공적인 배포를 지원하기 위한 작업 지침은 [Azure Rights Management 사용](../Topic/Using_Azure_Rights_Management.md)을 참조하세요.

## 참고 항목
[Azure Rights Management 구성](../Topic/Configuring_Azure_Rights_Management.md)

