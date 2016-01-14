---
description: na
keywords: na
title: Helping Users to Protect Files by Using Azure Rights Management
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 58f9a6ff-4121-4c8c-9865-1bb290604ad2
---
# 사용자가 Azure 권한 관리를 사용하여 파일을 보호할 수 있도록 지원
조직에 대해 Azure RMS(Azure 권한 관리)를 배포 및 구성한 후에는 사용자, 관리자 및 지원 센터를 위해 도움말과 지침을 제공합니다.

-   **최종 사용자 정보:**

    중요한 정보가 포함된 문서와 전자 메일을 보호하는 방법 및 시간을 사용자에게 알립니다. 가능한 경우 완전히 새로운 프로세스를 소개하지 말고, 이미 친숙한 프로세스에 추가 단계를 통합할 수 있도록 기존 워크플로에 이 정보를 제공합니다. 그와 동시에 업무와 관련된 이점과 위험을 알리고 파일과 전자 메일을 보호해야 하는 경우에 대한 지침도 제공합니다.[사용자 지정 템플릿](http://technet.microsoft.com/library/dn642472.aspx)을 구성한 경우 템플릿 이름과 설명만으로는 올바른 템플릿을 선택하기가 어렵다면 선택해야 하는 템플릿에 대한 지침을 제공합니다.

    > [!TIP]
    > 최종 사용자를 위한 예제 비디오:
    > 
    > -   [Azure RMS 사용자 환경](http://channel9.msdn.com/Series/Information-Protection/Azure-RMS-user-experience)
    > -   [Azure RMS 문서 추적 및 해지](http://channel9.msdn.com/Series/Information-Protection/Azure-RMS-Document-Tracking-and-Revocation)

-   **관리자 정보:**

    일부 응용 프로그램에서는 관리자가 구성하는 정책과 설정을 사용하여 정보 보호를 자동으로 적용합니다. 이러한 응용 프로그램의 경우에는 해당 응용 프로그램과 서비스를 관리하는 기타 관리자를 위한 지침을 제공해야 할 수 있습니다. 자세한 내용은 [응용 프로그램이 Azure 권한 관리를 지원하는 방식](../Topic/How_Applications_Support_Azure_Rights_Management.md) 및 [Azure 권한 관리용 응용 프로그램 구성](../Topic/Configuring_Applications_for_Azure_Rights_Management.md)을 참조하세요.

-   **지원 센터 정보:**

    지원 센터의 가장 유용한 도구 중 하나는 [RMS 분석기](https://www.microsoft.com/en-us/download/details.aspx?id=46437)입니다.   지원 센터 운영자는 이 도구를 Azure RMS 관리자 옵션을 사용하여 실행할 수 있으며 사용자에게 Azure RMS 사용자 옵션을 사용하여 실행하도록 요청할 수 있습니다. 이 도구는 문제를 식별하는 데 도움이 될 뿐 아니라 찾은 문제를 해결하며 문제가 해결되지 않으면 추적 로그를 기록합니다.

    직원이 조직을 떠난 후에 법률 자문 부서 또는 관리자가 요청하는 경우처럼 보호된 문서의 모든 액세스에 대한 합법적인 요청이 있는 경우 지원 센터는 Azure RMS [슈퍼 사용자 기능](https://technet.microsoft.com/en-us/library/mt147272.aspx)을 사용하여 이를 요청하는 프로세스를 진행해야 합니다.

    또한 사용자가 보고할 수 있는 일반적인 문제 중 일부는 다음과 같습니다.

    -   **로그인 도움말:**

        Azure RMS에서 사용자를 인증해야 하는데 캐시된 자격 증명을 사용할 수 없으면 사용자에게 자격 증명을 입력하라는 메시지가 표시될 수 있습니다. 이 자격 증명은 Office 365 테넌트 또는 Azure Active Directory 테넌트와 연결된 사용자의 회사 또는 학교 계정과 암호입니다. Microsoft 계정(이전의 Microsoft Live ID) 또는 개인 전자 메일 계정은 현재 Azure RMS에서 지원되지 않기 때문에 자격 증명으로 사용할 수 없습니다. 사용자가 Azure RMS에서 이러한 응용 프로그램을 사용할 때 자격 증명을 입력하라는 메시지가 표시되면 사용할 계정에 대한 지침을 사용자와 지원 센터에 제공합니다.

    -   **콘텐츠 보호 또는 사용 문제:**

        사용자가 사용하는 응용 프로그램에 대해 적절한 지침이 있으며 Azure RMS에서 지원하는 응용 프로그램 및 장치를 사용하고 있는지 확인합니다. 지원되는 응용 프로그램 및 장치에 대한 자세한 내용은 [Azure 권한 관리 요구 사항](../Topic/Requirements_for_Azure_Rights_Management.md)을 참조하세요.

        사용자가 콘텐츠를 보호하거나 사용하려고 할 때 오류가 발생하면 Azure RMS 사용자 권한으로 [RMS 분석기](https://www.microsoft.com/en-us/download/details.aspx?id=46437)를 실행할 것을 요청합니다.

        사용자가 보호된 콘텐츠를 열 수 있지만 필요한 권한이 없다고 보고할 경우 Azure RMS 사용자 권한으로 [RMS 분석기](https://www.microsoft.com/en-us/download/details.aspx?id=46437)를 실행하고 템플릿을 다운로드한 후 확인할 것을 요청합니다. 이렇게 하면 템플릿을 성공적으로 다운로드했는지와 템플릿이 제공하는 권한이 확인됩니다. 사용자가 템플릿용으로 구성된 올바른 그룹에 속하지 않거나 템플릿을 사용자에 맞게 다시 구성해야 하는 경우일 수 있습니다.

사용자가 중요한 문서와 전자 메일을 보호할 수 있도록 다음 섹션에서 응용 프로그램 관련 정보를 참조하세요.

## Rights Management 공유 응용 프로그램에서 정보 보호 기능 사용
사용자가 Office 2010을 사용하는 경우 콘텐츠를 보호하고 보호된 콘텐츠를 사용하려면 Rights Management(RMS) 공유 응용 프로그램이 필요합니다. 그러나 Azure RMS를 지원하는 모든 컴퓨터와 모바일 장치에서도 공유 응용 프로그램을 사용하는 것이 좋습니다.

RMS 공유 응용 프로그램은 사용자가 보다 쉽게 중요한 문서를 보호하도록 할 뿐 아니라 보호한 문서를 추적할 수 있도록 하고 필요한 경우 액세스 권한을 취소할 수 있도록 합니다.

Windows 컴퓨터에서 이 응용 프로그램을 사용하는 지침은 [Rights Management 공유 응용 프로그램 사용자 가이드](http://technet.microsoft.com/library/dn339006.aspx)를 참조하세요.

모바일 장치의 경우 [모바일 플랫폼용 Microsoft Rights Management 공유 응용 프로그램 FAQ](http://technet.microsoft.com/dn451248)를 참조하세요.

> [!TIP]
> 스크린샷이 포함된 높은 수준의 예 시나리오를 보려면 [사용자가 모바일 사용자와 안전하게 첨부 파일 공유](../Topic/What_is_Azure_Rights_Management_.md#BKMK_Example_SharingApp) 항목의 [Azure 권한 관리란?](../Topic/What_is_Azure_Rights_Management_.md) 섹션을 참조하세요.

## Office 365, Office 2016 또는 Office 2013에서 정보 보호 기능 사용
Azure RMS를 사용 중이며 Rights Management 공유 응용 프로그램을 설치하지 않은 경우 사용자에게는 파일을 보다 쉽게 보호하는 데 사용할 수 있는 리본 메뉴의 **보호 상태로 공유** 또는 파일 탐색기의 **내부 보호**가 표시되지 않습니다. 이러한 사용자는 다음 지침을 따라야 합니다.

> [!TIP]
> 이러한 응용 프로그램에서 정보 보호 기능을 사용하기 위한 응용 프로그램 관련 도움말과 지침을 찾으려면 **IRM** 및 응용 프로그램 이름과 버전을 검색합니다.

#### Word 2013에서 문서를 보호하려면

1.  Microsoft Word 내에서 새 문서를 만듭니다.

2.  **파일** 메뉴에서 **정보**, **문서 보호**, **액세스 제한**을 차례로 클릭한 다음 적합한 사용 권한을 빠르게 적용할 수 있는 템플릿을 선택하거나 **액세스 제한**을 선택하고 사용 권한을 직접 선택합니다.

    > [!NOTE]
    > Rights Management를 처음 사용하는 경우 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] 서비스에 연결하면 Office IRM 클라이언트를 구성하기 위한 자격 증명을 입력하라는 메시지가 표시됩니다.

3.  문서를 저장합니다.

다른 사용자는 문서를 열 때 먼저 인증하게 됩니다. 해당 사용자에게 문서를 열 권한이 없으면 문서가 열리지 않으며 문서를 열 권한이 있으면 해당 사용자에 대해 지정된 제한적 사용 권한으로 문서가 열립니다. 예를 들어 보기 전용 사용 권한이 있는 사용자는 문서를 다른 위치로 먼저 복사하더라도 편집하거나 저장할 수 없습니다. 사용 권한은 제한 배너를 통해 문서 맨 위에 표시됩니다. 이 배너에는 문서에 적용된 권한이 표시될 수도 있고 해당 권한을 표시할 수 있는 링크가 제공될 수도 있습니다.

#### Outlook 2013 및 Exchange Online을 사용하여 전자 메일 메시지를 보호하려면

1.  Outlook 내에서 조직의 받는 사람 주소를 지정하여 새 메일 메시지를 작성합니다.

2.  **옵션** 탭에서 **권한**을 클릭하고 옵션을 선택합니다. 예를 들면 다음과 같습니다. **전달 금지**, **&lt;회사 이름&gt; - 기밀** 또는 **&lt;회사 이름&gt; - 기밀(보기 전용)**

3.  메시지를 보냅니다.

보호된 문서를 볼 때와 마찬가지로 받는 사람은 전자 메일 메시지를 받으면 먼저 인증하게 됩니다. 전자 메일 메시지를 열 권한이 있으면 해당 사용자에 대해 지정된 제한적 사용 권한으로 메시지가 열립니다. 예를 들어 **전달 금지**를 선택한 경우에는 리본에서 전달 단추를 사용할 수 없습니다.

#### Outlook Web App을 사용하여 전자 메일 메시지를 보호하려면

1.  Outlook Web App 내에서 조직의 받는 사람 주소를 지정하여 새 메일 메시지를 작성합니다.

2.  **…**, **사용 권한 설정**을 차례로 클릭하고 옵션을 선택합니다. 예를 들면 다음과 같습니다. **전달 금지**, **전체 회신 금지**, **&lt;회사 이름&gt; - 기밀** 또는 **&lt;회사 이름&gt; - 기밀(보기 전용)**

3.  메시지를 보냅니다.

보호된 문서를 볼 때와 마찬가지로 받는 사람은 전자 메일 메시지를 받으면 먼저 인증하게 됩니다. 전자 메일 메시지를 열 권한이 있으면 해당 사용자에 대해 지정된 제한적 사용 권한으로 메시지가 열립니다. 예를 들어 **전체 회신 금지**를 선택한 경우에는 메시지 창에서 **전체 회신** 옵션을 사용할 수 없습니다.

## 참고 항목
[Azure Rights Management 사용](../Topic/Using_Azure_Rights_Management.md)

