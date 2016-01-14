---
description: na
keywords: na
title: Protect a file on a device (protect in-place) by using the Rights Management sharing application
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 33920329-5247-4f6c-8651-6227afb4a1fa
---
# Rights Management 공유 응용 프로그램을 사용하여 장치에서 파일 보호(내부 보호)
파일을 내부에서 보호하면 보호되지 않는 원본 파일을 대체합니다. 그러면 파일을 원 위치에 남겨 두고 다른 폴더나 장치에 복사하거나, 파일이 들어 있는 폴더를 공유하여 파일을 보호할 수 있습니다. 전자 메일로 파일을 보호할 때 권장되는 방법은 파일 탐색기나 Office 응용 프로그램에서 직접 수행하는 것이지만 전자 메일 메시지에 보호되는 파일을 첨부할 수도 있습니다([Rights Management 공유 응용 프로그램을 사용하여 전자 메일을 통해 공유하는 파일 보호](../Topic/Protect_a_file_that_you_share_by_email_by_using_the_Rights_Management_sharing_application.md) 참조).

> [!TIP]
> 파일을 보호하려 할 때 오류가 나타나면 [Windows용 Microsoft Rights Management 공유 응용 프로그램 FAQ](http://go.microsoft.com/fwlink/?LinkId=303971)를 참조하세요.

## 장치에서 파일을 보호하려면(내부 보호)

1.  파일 탐색기에서 보호할 파일을 선택합니다.**RMS로 보호**를 마우스 오른쪽 단추로 선택한 다음 **내부 보호**를 선택합니다. 예를 들면 다음과 같습니다.

    ![](../Image/ADRMS_MSRMSApp_SP_CompanyDefined.png)

    > [!NOTE]
    > **RMS로 보호** 옵션이 표시되지 않는다면 RMS 공유 응용 프로그램이 컴퓨터에 설치되지 않았거나, 설치를 완료하기 위해 컴퓨터를 다시 시작해야 하는 경우입니다. RMS 공유 응용 프로그램 설치 방법에 대한 자세한 내용은 [Rights Management 공유 응용 프로그램 다운로드 및 설치 ](../Topic/Download_and_install_the_Rights_Management_sharing_application.md)를 참조하세요.

2.  다음 중 하나를 수행합니다.

    -   정책 템플릿 선택: 일반적으로 조직 내 사람들에게 액세스 및 사용을 제한하는 사전 정의된 권한입니다. 예를 들어 경우 조직의 이름은 "Contoso, Ltd"이면 **Contoso, Ltd - 기밀 보기 전용**이라고 표시될 수 있습니다. 이 컴퓨터에서 파일을 보호하는 것이 처음일 경우 먼저 **회사 정의 보호**를 선택하여 텀플릿을 다운로드해야 합니다.

        다음번에 **내부 보호** 옵션을 클릭하면 선택 가능한 최대 10개의 템플릿이 표시됩니다. 사용할 수 있는 템플릿이 10개가 넘는데도 원하는 템플릿이 표시되지 않으면 **회사 정의 보호**를 클릭하여 모든 템플릿을 다운로드하여 표시합니다.

        정책 템플릿을 선택하면 여러 파일과 폴더를 보호할 수 있습니다. 폴더를 선택하면 폴더의 모든 파일이 보호 대상으로 자동 선택되지만 해당 폴더에 만든 새 파일은 자동으로 보호되지 않습니다.

    -   **사용자 지정 권한** 선택: 템플릿이 필요한 보호 수준을 제공하지 않거나 직접 보호 옵션을 명시적으로 설정하려는 경우 이 옵션을 선택합니다.[보호 대화 상자 추가](http://technet.microsoft.com/library/dn574738.aspx)에서 이 파일에 대한 옵션을 지정하고 **적용**을 클릭합니다.

3.  파일이 보호되고 있음을 설명하는 대화 상자가 잠시 표시될 수 있으며, 포커스가 파일 탐색기로 돌아갑니다. 이제 선택한 파일이 보호됩니다. 경우에 따라(보호를 추가하면 파일 이름 확장명이 바뀌는 경우) 파일 탐색기의 원본 파일이 Rights Management 보호 잠금 아이콘이 있는 새 파일로 대체됩니다. 예를 들면 다음과 같습니다.

    ![](../Image/ADRMS_MSRMSApp_Pfile.png)

나중에 파일에서 보호를 제거하려는 경우 [Rights Management 공유 응용 프로그램을 사용하여 파일에서 보호 제거](../Topic/Remove_protection_from_a_file_by_using_the_Rights_Management_sharing_application.md)를 참조하세요.

## 예제 및 기타 지침
예를 들어 Rights Management 공유 응용 프로그램 및 방법 지침을 사용하는 방법에 대한 예는 Rights Management 공유 응용 프로그램 사용자 가이드에서 다음 섹션을 참조하세요.

-   [RMS 공유 응용 프로그램 사용 예제](../Topic/Rights_Management_sharing_application_user_guide.md#BKMK_SharingExamples)

-   [원하는 옵션을 선택하세요.](../Topic/Rights_Management_sharing_application_user_guide.md#BKMK_SharingInstructions)

## 참고 항목
[Rights Management 공유 응용 프로그램 사용자 가이드](../Topic/Rights_Management_sharing_application_user_guide.md)

