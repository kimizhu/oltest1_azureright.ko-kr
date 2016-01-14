---
description: na
keywords: na
title: Download and install the Rights Management sharing application
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 2bf09690-9dba-43b7-9e0a-0110915d4081
---
# Rights Management 공유 응용 프로그램 다운로드 및 설치 
로컬 관리자가 아니더라도 RMS 공유 응용 프로그램을 설치할 수 있습니다. 하지만 로컬 관리자가 아닌 사용자가 Office 2010을 사용하는 경우 몇 가지 제한 사항이 있습니다. 자세한 내용은 이 항목의 [로컬 관리자가 아닌 사용자가 Office 2010을 사용하는 경우](#BKMK_SetupOffice2010) 섹션을 참조하세요.

### Rights Management 공유 응용 프로그램을 다운로드 및 설치하려면

1.  Microsoft 웹 사이트에서 [Microsoft Rights Management](http://go.microsoft.com/fwlink/?LinkId=303970) 페이지로 이동합니다.

2.  **컴퓨터** 섹션에서 **Windows용 RMS 앱**의 아이콘을 클릭하고 **Setup.exe** 파일을 저장하여 Microsoft Rights Management 공유 응용 프로그램을 설치합니다.

3.  다운로드된 Setup.exe 파일을 두 번 클릭합니다. 설치를 계속할지 묻는 메시지가 표시되면 **예**를 클릭합니다.

4.  **Microsoft RMS 설치** 페이지에서 **다음**을 클릭하고 설치가 완료될 때까지 기다립니다.

    > [!NOTE]
    > RMS 공유 응용 프로그램에는 Microsoft.NET Framework 버전 4.0 이상이 필요합니다. 설치 프로그램에서 이 버전이 설치되어 있는지 확인하며, 설치되어 있지 않은 경우 설치할 수 있는 링크가 포함된 메시지가 나타납니다.

5.  설치가 완료되면 **다시 시작**을 클릭하여 컴퓨터를 다시 시작하고 설치를 완료합니다. 또는 **닫기**를 클릭하고 나중에 컴퓨터를 다시 시작하여 설치를 완료합니다.

이제 파일을 보호하고 다른 사용자가 보호한 파일을 읽을 수 있습니다.

## <a name="BKMK_SetupOffice2010"></a>로컬 관리자가 아닌 사용자가 Office 2010을 사용하는 경우
컴퓨터에 로그인할 때 로컬 관리 권한이 없으며 설치 프로그램에서 Office 2010이 설치된 것을 감지할 경우 이 구성에서는 일부 시나리오가 작동하지 않는다는 경고 메시지가 표시됩니다. 해당 시나리오는 다음과 같습니다.

-   조직에서 온-프레미스 버전의 RMS가 아닌 Azure RMS를 사용하는 경우

    -   Office의 IRM(정보 권한 관리) 기능을 사용할 수 없습니다. 예를 들면 전자 메일에 대한 **전달 금지** 옵션과 Word 및 Excel의 **파일** 메뉴에서 설정할 수 있는 **액세스 제한** 권한입니다. 리본의 보호된 항목 공유 옵션과 파일 탐색기의 마우스 오른쪽 단추 클릭 옵션을 사용할 수 있습니다.

-   조직에서 Azure RMS가 아닌 온-프레미스 버전의 RMS를 사용하는 경우

    -   Azure RMS를 사용하는 다른 조직의 사용자가 보낸 보호된 문서를 읽을 수 없습니다.

로컬 관리자가 아니며 Office 365 또는 Office 2013을 사용하는 경우에는 이 메시지가 표시되지 않고 이러한 시나리오가 지원됩니다.

이러한 알려진 제한 사항으로 설치를 계속할 수 있습니다. 또는 설치를 중지하고 3단계에서 Setup.exe를 실행할 때 **관리자 권한으로 실행** 옵션을 사용하여 다시 실행하거나 관리자에게 대신 설치하도록 요청할 수 있습니다. 관리자는 자동으로 설치되도록 [이 설치를 스크립팅](https://technet.microsoft.com/library/dn339003.aspx)할 수 있습니다.

## 예제 및 기타 지침
예를 들어 Rights Management 공유 응용 프로그램 및 방법 지침을 사용하는 방법에 대한 예는 Rights Management 공유 응용 프로그램 사용자 가이드에서 다음 섹션을 참조하세요.

-   [RMS 공유 응용 프로그램 사용 예제](../Topic/Rights_Management_sharing_application_user_guide.md#BKMK_SharingExamples)

-   [원하는 옵션을 선택하세요.](../Topic/Rights_Management_sharing_application_user_guide.md#BKMK_SharingInstructions)

## 참고 항목
[Rights Management 공유 응용 프로그램 사용자 가이드](../Topic/Rights_Management_sharing_application_user_guide.md)

