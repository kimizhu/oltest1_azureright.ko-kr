---
description: na
keywords: na
title: RMS Protection with Windows Server File Classification Infrastructure (FCI)
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 9aa693db-9727-4284-9f64-867681e114c9
---
# Windows Server FCI(파일 분류 인프라)를 사용하는 RMS 보호
RMS(Rights Management) 클라이언트와 RMS 보호 도구를 사용하여 파일 서버 리소스 관리자 및 FCI(파일 분류 인프라)를 구성하려면 이 문서에 나와 있는 지침과 스크립트를 사용합니다.

이 솔루션을 사용하면 Windows Server를 실행 중인 파일 서버의 폴더에 있는 모든 파일 또는 특정 기준을 충족하는 파일을 자동으로 보호할 수 있습니다. 기밀 정보나 중요 정보를 포함하는 것으로 분류된 파일을 예로 들 수 있습니다. 이 솔루션은 Azure RMS([Azure  권한 관리](../Topic/Azure_Rights_Management.md))를 사용하여 파일을 보호하므로 조직에 이 기술을 배포해야 합니다.

> [!NOTE]
> Azure RMS는 파일 분류 인프라를 지원하는 [커넥터](https://technet.microsoft.com/library/dn375964.aspx)를 포함하므로 해당 솔루션은 Office 파일 등의 기본 보호만 지원합니다.
> 
> 파일 분류 인프라를 사용하는 모든 파일 형식을 지원하려면 이 문서에서 설명하는 Windows PowerShell **RMS 보호** 모듈을 사용해야 합니다. RMS 보호 cmdlet은 RMS 공유 응용 프로그램과 마찬가지로 일반 보호와 기본 보호를 모두 지원하므로 모든 파일을 보호할 수 있습니다. 이와 같은 다양한 보호 수준에 대한 자세한 내용은 [Rights Management 공유 응용 프로그램 관리자 가이드](../Topic/Rights_Management_sharing_application_administrator_guide.md)에서 [보호 수준 - 기본 및 일반](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_LevelsofProtection) 섹션을 참조하세요.

아래의 지침은 Windows Server 2012 R2 또는 Windows Server 2012용입니다. 지원되는 다른 Windows 버전을 실행하는 경우에는 사용 중인 운영 체제 버전과 이 문서에서 설명하는 버전 간의 차이에 맞게 일부 단계를 조정해야 할 수 있습니다.

## Windows Server FCI를 사용하는 Azure RMS 보호를 위한 필수 구성 요소
이러한 지침을 적용하기 위한 필수 구성 요소는 다음과 같습니다.

-   파일 분류 인프라를 사용하여 파일 리소스 관리자를 실행할 각 파일 서버에서 다음을 수행해야 합니다.

    -   파일 서비스 역할에 대한 역할 서비스 중 하나로 파일 서버 리소스 관리자를 설치해야 합니다.

    -   Rights Management를 사용하여 보호할 파일이 포함된 로컬 폴더를 지정해야 합니다. 예를 들어 C:\FileShare 등을 지정할 수 있습니다.

    -   RMS 보호 도구와 해당 도구의 필수 구성 요소(예: RMS 클라이언트) 및 Azure RMS의 필수 구성 요소(예: 서비스 사용자 계정)를 설치해야 합니다. 자세한 내용은 [RMS 보호 cmdlet](https://msdn.microsoft.com/library/azure/mt433195.aspx)을 참조하세요.

    -   특정 파일 이름 확장명에 대해 RMS 보호의 기본 수준(기본 또는 일반)을 변경하려는 경우 [파일 API 구성](https://msdn.microsoft.com/library/dn197834%28v=vs.85%29.aspx) 페이지의 설명에 따라 레지스트리를 편집해야 합니다.

    -   인터넷에 연결할 수 있어야 하며 프록시 서버에 필요한 경우 컴퓨터 설정을 구성해야 합니다. 예를 들어 `netsh winhttp import proxy source=ie`를 구성할 수 있습니다.

-   [about_RMSProtection_AzureRMS](https://msdn.microsoft.com/library/mt433202.aspx)의 설명에 따라 Azure Rights Management 배포에 대한 추가 필수 구성 요소를 구성해야 합니다. 구체적으로는 서비스 계정을 사용하여 Azure RMS에 연결하기 위한 다음 값을 구성해야 합니다.

    -   BposTenantId

    -   AppPrincipalId

    -   대칭 키

-   온-프레미스 Active Directory 사용자 계정을 Azure Active Directory 또는 Office 365와 동기화해야 합니다(각각의 전자 메일 주소를 포함). 이렇게 하려면 모든 사용자가 파일을 FCI 및 Azure RMS로 보호한 후에 해당 파일에 액세스해야 할 수도 있습니다. 이 단계를 수행하지 않으면(예: 테스트 환경) 사용자가 이러한 파일에 액세스하지 못하도록 차단될 수 있습니다. 이 계정을 구성하는 방법에 대해 자세히 알아보려면 [Azure 권한 관리 준비](../Topic/Preparing_for_Azure_Rights_Management.md) 섹션을 참조하세요.

-   파일을 보호하는 데 사용할 Rights Management 템플릿을 지정해야 합니다.[Get-RMSTemplate](https://msdn.microsoft.com/library/azure/mt433197.aspx) cmdlet을 사용하여 이 템플릿의 ID를 확인해야 합니다.

## Azure RMS 보호를 위해 파일 서버 리소스 관리자 FCI를 구성하는 지침
Windows PowerShell 스크립트를 사용자 지정 작업으로 사용하여 폴더의 모든 파일을 자동으로 보호하려면 아래 지침을 따르세요. 다음 절차를 이 순서대로 수행합니다.

1.  Windows PowerShell 스크립트 저장

2.  RMS(Rights Management)용 분류 속성 만들기

3.  분류 규칙(RMS용 분류) 만들기

4.  분류 일정 구성

5.  사용자 지정 파일 관리 작업(RMS로 파일 보호) 만들기

6.  수동으로 규칙 및 작업을 실행하여 구성 테스트

이러한 지침대로 절차를 수행하고 나면 선택한 폴더의 모든 파일이 사용자 지정 속성 RMS를 사용하여 분류되며 Rights Management를 통해 보호됩니다. 일부 파일만 선택적으로 보호하는 더 복잡한 구성을 사용하려는 경우 해당 파일만 보호하는 파일 관리 작업을 통해 다른 분류 속성 및 규칙을 만들거나 사용할 수 있습니다.

#### Windows PowerShell 스크립트 저장

1.  이 문서의 [파일 서버 리소스 관리자 FCI를 사용하는 Azure RMS 보호용 Windows PowerShell 스크립트](#BKMK_RMSProtection_Script) 섹션을 확장하여 해당 내용을 복사합니다. 컴퓨터에서 스크립트의 내용을 붙여넣은 다음 파일 이름을 **RMS-Protect-FCI.ps1**로 지정합니다.

2.  스크립트를 검토하고 다음과 같이 변경합니다.

    -   다음 문자열을 검색하여 Azure RMS에 연결하기 위해 [Set-RMSServerAuthentication](https://msdn.microsoft.com/library/mt433199.aspx)에 사용하는 고유한 AppPrincipalId로 바꿉니다.

        ```
        <enter your AppPrincipalId here>
        ```
        예를 들어 스크립트를 다음과 같이 변경할 수 있습니다.

        `[Parameter(Mandatory = $false)]`

        `[Parameter(Mandatory = $false)] [string]$AppPrincipalId = "b5e3f76a-b5c2-4c96-a594-a0807f65bba4",`

    -   다음 문자열을 검색하여 Azure RMS에 연결하기 위해 [Set-RMSServerAuthentication](https://msdn.microsoft.com/library/mt433199.aspx)에 사용하는 고유한 대칭 키로 바꿉니다.

        ```
        <enter your key here>
        ```
        예를 들어 스크립트를 다음과 같이 변경할 수 있습니다.

        `[Parameter(Mandatory = $false)]`

        `[string]$SymmetricKey = "zIeMu8zNJ6U377CLtppkhkbl4gjodmYSXUVwAO5ycgA="`

    -   다음 문자열을 검색하여 Azure RMS에 연결하기 위해 [Set-RMSServerAuthentication](https://msdn.microsoft.com/library/mt433199.aspx)에 사용하는 고유한 BposTenantId(테넌트 ID)로 바꿉니다.

        ```
        <enter your BposTenantId here>
        ```
        예를 들어 스크립트를 다음과 같이 변경할 수 있습니다.

        `[Parameter(Mandatory = $false)]`

        `[string]$BposTenantId = "23976bc6-dcd4-4173-9d96-dad1f48efd42",`

    -   서버에서 Windows Server 2012를 실행 중인 경우에는 스크립트 시작 부분에서 RMSProtection 모듈을 수동으로 로드해야 할 수 있습니다. 다음 명령을 추가하거나, “Program Files” 폴더가 C: 드라이브가 아닌 다른 드라이브에 있는 경우 해당 드라이브에 맞는 동등한 명령을 추가합니다.

        ```
        Import-Module "C:\Program Files\WindowsPowerShell\Modules\RMSProtection\RMSProtection.dll"
        ```

3.  스크립트에 서명을 합니다. 스크립트에 서명을 하면 보안 수준이 높아집니다. 서명을 하지 않는 경우에는 스크립트를 실행하는 서버에서 Windows PowerShell을 구성해야 합니다. 예를 들어 **관리자 권한으로 실행** 옵션을 사용하여 Windows PowerShell 세션을 실행하고 **Set-ExecutionPolicy Unrestricted**를 입력합니다. 그러나 이 구성에서는 서명되지 않은 모든 스크립트를 실행할 수 있으므로 보안 수준이 낮습니다.

    Windows PowerShell 스크립트에 서명을 하는 방법에 대한 자세한 내용은 PowerShell 문서 라이브러리에서 [about_Signing](https://technet.microsoft.com/library/hh847874.aspx)을 참조하세요.

4.  파일 분류 인프라를 사용하여 파일 리소스 관리자를 실행할 각 파일 서버에서 파일을 로컬에 저장합니다. 예를 들어 **C:\RMS-Protection**에 파일을 저장합니다. 권한이 없는 사용자가 수정할 수 없도록 NTFS 권한을 사용하여 이 파일을 보호합니다.

이제 파일 서버 리소스 관리자 구성을 시작할 준비가 되었습니다.

#### RMS(Rights Management)용 분류 속성 만들기

-   파일 서버 리소스 관리자의 분류 관리에서 새 로컬 속성을 만듭니다.

    -   **이름**: **RMS**를 입력합니다.

    -   설명:   **Rights Management 보호**를 입력합니다.

    -   **속성 형식**: **예/아니요**를 선택합니다.

    -   **값**: **예**를 선택합니다.

이제 이 속성을 사용하는 분류 규칙을 만들 수 있습니다.

#### 분류 규칙(RMS용 분류) 만들기

-   새 분류 규칙을 만듭니다.

    -   **일반** 탭에서 다음을 수행합니다.

        -   **이름**: **RMS용 분류**를 입력합니다.

        -   **사용**: 기본값(이 확인란 선택)을 유지합니다.

        -   설명: **Rights Management에 대해 &lt;폴더 이름&gt; 폴더의 모든 파일 분류**를 입력합니다.

            *&lt;폴더 이름&gt;*은 선택한 폴더 이름으로 바꿉니다. 예를 들어 **Rights Management에 대해 C:\FileShare 폴더의 모든 파일 분류**를 입력합니다.

        -   **범위**: 선택한 폴더를 추가합니다. 예를 들어 **C:\FileShare**를 추가합니다.

            확인란은 선택하지 마세요.

    -   **분류** 탭에서 다음을 수행합니다.

    -   **분류 방법**: **폴더 분류자**를 선택합니다.

    -   **속성** 이름: **RMS**를 선택합니다.

    -   속성 **값**: **예**를 선택합니다.

분류 규칙은 수동으로 실행할 수도 있지만 지속적으로 수행하는 작업의 경우에는 새 파일이 RMS 속성을 사용하여 분류되도록 일정에 따라 이 규칙을 실행할 수도 있습니다.

#### 분류 일정 구성

-   **자동 분류** 탭에서 다음을 수행합니다.

    -   **고정된 일정 사용**: 이 확인란을 선택합니다.

    -   RMS 속성을 사용하여 파일을 분류하는 새 규칙을 비롯해 실행할 모든 분류 규칙에 대한 일정을 구성합니다.

    -   **새 파일에 대해 분류 계속 허용**: 새 파일이 분류되도록 이 확인란을 선택합니다.

    -   선택 사항: 보고서 및 알림 옵션을 구성하는 등의 원하는 기타 변경 작업을 수행합니다.

이제 분류 구성을 완료했으므로 파일에 RMS 보호를 적용하는 관리 작업을 구성할 준비가 되었습니다.

#### 사용자 지정 파일 관리 작업(RMS로 파일 보호) 만들기

-   **파일 관리 작업**에서 새 파일 관리 작업을 만듭니다.

    -   **일반** 탭에서 다음을 수행합니다.

        -   **작업 이름**: **RMS를 사용하여 파일 보호**를 입력합니다.

        -   **사용** 확인란은 선택한 상태로 유지합니다.

        -   설명: Windows PowerShell 스크립트를 사용하여 Rights Management 및 템플릿을 통해 &lt;폴더 이름&gt;의 **파일 보호를 입력합니다.**

            *&lt;폴더 이름&gt;*은 선택한 폴더 이름으로 바꿉니다. 예를 들어 **Windows PowerShell 스크립트를 사용하여 Rights Management 및 템플릿을 통해 C:\FileShare의 파일 보호**를 입력합니다.

        -   **범위**: 원하는 폴더를 선택합니다. 예를 들어 **C:\FileShare**를 추가합니다.

            확인란은 선택하지 마세요.

    -   **동작** 탭에서 다음을 수행합니다.

        -   **유형**: **사용자 지정**을 선택합니다.

        -   **실행 파일**: 다음을 지정합니다.

            ```
            C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe
            ```
            Windows가 C: 드라이브에 설치되어 있지 않으면 이 경로를 수정하거나 이 파일을 찾습니다.

        -   **인수**: 다음을 지정합니다. 이때 &lt;경로&gt;와 &lt;템플릿 ID&gt;에는 고유한 값을 입력합니다.

            ```
            -Noprofile -Command "<path>\RMS-Protect-FCI.ps1 -File '[Source File Path]' -TemplateID <template GUID> -OwnerMail [Source File Owner Email]"
            ```
            예를 들어 C:\RMS-Protection에 스크립트를 복사했으며 필수 구성 요소에서 지정한 템플릿 ID가 e6ee2481-26b9-45e5-b34a-f744eacd53b0인 경우 다음을 지정합니다.

            `-Noprofile -Command "C:\RMS-Protection\RMS-Protect-FCI.ps1 -File '[Source File Path]' -TemplateID e6ee2481-26b9-45e5-b34a-f744eacd53b0 -OwnerMail [Source File Owner Email]"`

            이 명령에서 **[원본 파일 경로]** 및 **[원본 파일 소유자 전자 메일]**은 모두 FCI에 따라 달라지는 변수이므로 위의 명령에 표시되는 그대로 정확하게 입력합니다. 첫 번째 변수는 FCI가 폴더에서 식별된 파일을 자동으로 지정하는 데 사용되고 두 번째 변수는 FCI가 식별된 파일의 명명된 소유자 전자 메일 주소를 자동으로 검색하는 데 사용됩니다. 이 명령은 폴더의 각 파일(이 예에서는 C:\FileShare 폴더의 각 파일)에 대해 반복 실행되며 파일 분류 속성으로 RMS도 추가로 포함합니다.

            > [!NOTE]
            > **-OwnerMail [Source File Owner Email]** 매개 변수와 값이 파일 원래 소유자가 파일을 보호하면 해당 파일의 권한 관리 소유자에게 권한을 부여하는지 확인합니다. 원래 파일 소유자가 자신의 파일에 대한 권한 관리 권한을 모두 보유하고 있는지 확인합니다. 도메인 사용자가 파일을 만들면 전자 메일 주소가 파일의 소유자 속성에 있는 사용자 계정 이름을 이용하여 Active Directory에서 자동으로 검색됩니다. 이렇게 하려면 파일 서버가 사용자와 동일한 도메인 또는 트러스트된 도메인에 있어야 합니다.
            > 
            > 가능한 경우에는 항상 이러한 사용자가 작성한 파일에 대한 모든 권한을 계속 가질 수 있도록 보호된 문서에 원래 소유자를 할당합니다. 그러나 위에 나와 있는 것처럼 [원본 파일 소유자 전자 메일] 변수를 사용하는 경우 로컬 계정을 사용해 파일을 만들어 소유자가 SYSTEM으로 표시되는 등 파일에 도메인 사용자가 소유자로 정의되어 있지 않으면 스크립트가 실패합니다.
            > 
            > 도메인 사용자가 소유자로 정의되어 있지 않은 파일의 경우에는 도메인 사용자로 이러한 파일을 직접 복사 및 저장할 수 있습니다. 이렇게 하면 해당 파일에 대해서만 소유자로 지정됩니다. 또는 권한이 있는 경우 소유자를 수동으로 변경할 수 있습니다.  또는 [원본 파일 소유자 전자 메일] 변수 대신 자신의 전자 메일 주소나 IT 부서의 그룹 주소 같은 특정 전자 메일 주소를 입력할 수도 있습니다. 그러면 이 스크립트를 사용하여 보호하는 모든 파일이 해당 전자 메일 주소를 사용하여 새 소유자를 정의합니다.

    -   **다음 액세스 수준으로 명령 실행**: **로컬 시스템**을 선택합니다.

    -   **조건** 탭에서 다음을 수행합니다.

        -   **속성**: **RMS**를 선택합니다.

        -   **연산자**: **같음**을 선택합니다.

        -   **값**: **예**를 선택합니다.

    -   **일정** 탭에서 다음을 수행합니다.

        -   **실행 날짜**: 원하는 일정을 구성합니다.

            스크립트가 완료될 수 있도록 충분한 시간을 지정합니다. 이 솔루션은 폴더의 모든 파일을 보호하지만 스크립트는 매번 각 파일에 대해 한 번씩 실행됩니다. FCI의 이 파일별 보호 구성은 RMS 보호 도구에서 지원하는 방식인 모든 파일을 동시에 보호하는 것보다 시간은 오래 걸리지만 더욱 강력한 보호를 제공합니다. 예를 들어 [원본 파일 소유자 전자 메일] 변수를 사용할 때는 보호되는 파일의 소유자가 달라질 수 있으며(원래 소유자가 유지됨), 나중에 폴더의 모든 파일이 아니라 선택적으로 파일을 보호하도록 구성을 변경하는 경우에는 이 파일별 보호 작업을 수행해야 합니다.

        -   **새 파일에서 계속 실행**: 이 확인란을 선택합니다.

#### 수동으로 규칙 및 작업을 실행하여 구성 테스트

1.  분류 규칙을 실행합니다.

    1.  **분류 규칙** &gt; **지금 모든 규칙을 사용한 분류 실행**을 클릭합니다.

    2.  **완료할 때까지 분류 대기**를 클릭하고 **확인**을 클릭합니다.

2.  **분류 실행 중** 대화 상자가 닫힐 때까지 기다린 후 자동으로 표시되는 보고서에서 결과를 확인합니다.**속성** 필드와 폴더의 파일 수에 **1**이 표시되어야 합니다. 파일 탐색기를 통해 선택한 폴더의 파일 속성을 점검하여 실행을 확인합니다.**분류** 탭에서는 속성 이름으로 **RMS**가, 속성의 **값**으로 **예**가 표시되어야 합니다.

3.  파일 관리 작업을 실행합니다.

    1.  **파일 관리 작업** &gt; **RMS를 사용하여 파일 보호** &gt; **지금 파일 관리 작업 실행**을 클릭합니다.

    2.  **완료할 때까지 작업 대기**를 클릭하고 **확인**을 클릭합니다.

4.  **파일 관리 작업 실행 중** 대화 상자가 닫힐 때까지 기다린 후 자동으로 표시되는 보고서에서 결과를 확인합니다.**파일** 필드에 선택한 폴더에 포함된 파일의 수가 표시되어야 합니다. 선택한 폴더의 파일이 이제 RMS를 통해 보호되는지 확인합니다. 예를 들어 선택한 폴더가 C:\FileShare인 경우 Windows PowerShell 세션에서 다음을 입력하고 **보호되지 않음** 상태인 파일이 없는지 확인합니다.

    ```
    foreach ($file in (Get-ChildItem -Path C:\FileShare -Force | where {!$_.PSIsContainer})) {Get-RMSFileStatus -f $file.PSPath}
    ```
    > [!TIP]
    > 아래에는 몇 가지 문제 해결 팁이 나와 있습니다.
    > 
    > -   보고서에 폴더의 파일 수가 아닌 **0**이 표시되는 경우 스크립트가 실행되지 않은 것입니다. 먼저 스크립트를 Windows PowerShell ISE에서 로드하여 스크립트 내용의 유효성을 검사하는 방식으로 스크립트 자체를 점검한 다음 스크립트를 실행하여 오류가 표시되는지를 확인합니다. 인수를 지정하지 않는 경우 스크립트는 Azure RMS 연결 및 인증을 시도합니다.
    > 
    >     -   스크립트가 Azure RMS에 연결할 수 없음을 보고하는 경우 스크립트에서 지정한 서비스 사용자 계정에 대해 표시되는 값을 확인합니다.  이 서비스의 사용자 계정을 만드는 방법에 대한 자세한 내용은 [about_RMSProtection_AzureRMS](https://msdn.microsoft.com/library/mt433202.aspx)에서 두 번째 필수 구성 요소를 참조하세요.
    >     -   스크립트가 Azure RMS에 연결할 수 있음을 보고하는 경우 Azure 지역이 북미 외부이면 이 구성에 대해 레지스트리를 올바르게 편집했는지 확인하세요. 이 확인 시에는 서버의 Windows PowerShell에서 Get-RMSTemplate을 직접 실행하면 효율적입니다. 레지스트리 편집에 대한 자세한 내용은 [about_RMSProtection_AzureRMS](https://msdn.microsoft.com/library/mt433202.aspx)에서 세 번째 필수 구성 요소를 참조하세요.
    > -   스크립트 자체는 오류 없이 Windows PowerShell ISE에서 실행되는 경우에는 -OwnerEmail 매개 변수 없이 보호할 파일 이름을 지정하여 PowerShell 세션에서 다음과 같이 스크립트를 실행해 봅니다.
    > 
    >     ```
    >     powershell.exe -Noprofile -Command "<path>\RMS-Protect-FCI.ps1 -File <full path and name of a file>' -TemplateID <template GUID>"
    >     ```
    >     -   이 Windows PowerShell 세션에서 스크립트가 정상적으로 실행되는 경우에는 파일 관리 작업 동작에서 **실행** 및 **인수**의 항목을 확인합니다.**-OwnerEmail [원본 파일 소유자 전자 메일]**을 지정한 경우 이 매개 변수를 제거해 봅니다.
    > 
    >         파일 관리 작업을  **-OwnerEmail [원본 파일 소유자 전자 메일]** 없이 완료한 경우 보호되지 않은 파일에서 도메인 사용자가 **SYSTEM** 대신 파일 소유자로 표시되는지 확인합니다.  이렇게 하려면 파일 속성의 **보안** 탭을 사용한 다음 **고급**을 클릭합니다.**소유자** 값은 파일 **이름** 바로 뒤에 표시됩니다. 또한 파일 서버가 동일한 도메인 또는 트러스트된 도메인에 있어 Active Directory 도메인 서비스에서 사용자의 전자 메일 주소를 조회할 수 있는지 확인합니다.
    > -   보고서에는 파일 수는 올바르게 표시되는데 파일이 보호되지 않는 경우 [Protect-RMSFile](https://msdn.microsoft.com/library/azure/mt433201.aspx) cmdlet을 사용하여 파일을 수동으로 보호한 다음 오류가 표시되는지 확인합니다.

이러한 작업이 성공적으로 실행되었음을 확인한 경우 파일 리소스 관리자를 닫아도 됩니다. 새 파일이 자동으로 보호되고 일정이 실행될 때 모든 파일이 다시 보호됩니다. 파일을 다시 보호하는 경우 템플릿의 모든 변경 사항이 파일에 적용되었는지 확인합니다.

### <a name="BKMK_RMSProtection_Script"></a>파일 서버 리소스 관리자 FCI를 사용하는 Azure RMS 보호용 Windows PowerShell 스크립트
이 섹션에는 이전 섹션에서 설명한 대로 복사 및 편집할 수 있는 샘플 스크립트가 나와 있습니다.

*&#42;&#42;고지 사항&#42;&#42;: 이 샘플 스크립트는 Microsoft 표준 지원 프로그램 또는 서비스를 통해 지원되지 않습니다. 이 샘플 스크립트는 어떤 종류의 보증도 없이 있는 그대로 제공됩니다.*

```
<# .SYNOPSIS Helper script to protect all file types with Azure RMS and FCI. .DESCRIPTION Protect files with Azure RMS and Windows Server FCI, using an RMS template ID. #> param( [Parameter(Mandatory = $false)] [ValidateScript({ If($_ -eq "") {$true} else { if (Test-Path -Path $_ -PathType Leaf) {$true} else {throw "Can't find file specified"} } })] [string]$File, [Parameter(Mandatory = $false)] [string]$TemplateID, [Parameter(Mandatory = $false)] [string]$OwnerMail, [Parameter(Mandatory = $false)] [string]$AppPrincipalId = "<enter your AppPrincipalId here>", [Parameter(Mandatory = $false)] [string]$SymmetricKey = "<enter your key here>", [Parameter(Mandatory = $false)] [string]$BposTenantId = "<enter your BposTenantId here>" ) # script information [String] $Script:Version = 'version 1.0' [String] $Script:Name = "RMS-Protect-FCI.ps1" #global working variables [switch] $Script:isScriptProcess = $False # Controls the script process. If false, the script gracefully stops running. #**Functions (general helper)*************************************** function Get-ScriptName(){ return $MyInvocation.ScriptName.Substring($MyInvocation.ScriptName.LastIndexOf('\') + 1, $MyInvocation.ScriptName.LastIndexOf('.') - $MyInvocation.ScriptName.LastIndexOf('\') - 1) } #**Functions (script specific)************************************** function Check-Module{ param ([String]$Module = $(Throw "Module name not specified")) [bool]$isResult = $False #try to load the module if (get-module -list -name $Module) { import-module $Module if (get-module -name $Module ) { $isResult = $True } else { $isResult = $False } } else { $isResult = $False } return $isResult } function Protect-File ($ffile, $ftemplateId, $fownermail) { [bool] $returnValue = $false try { If ($OwnerMail -eq $null -or $OwnerMail -eq "") { $protectReturn = Protect-RMSFile -File $ffile -TemplateID $ftemplateId $returnValue = $true Write-Host ( "Information: " + "Protected File: $ffile with Template: $ftemplateId") } else { $protectReturn = Protect-RMSFile -File $ffile -TemplateID $ftemplateId -OwnerEmail $fownermail $returnValue = $true Write-Host ( "Information: " + "Protected File: $ffile with Template: $ftemplateId, set Owner: $fownermail") } } catch { Write-Host ( "ERROR" + "During protection of file: $ffile with Template: $ftemplateId") } return $returnValue } function Set-RMSConnection ($fappId, $fkey, $fbposId) { [bool] $returnValue = $false try { Set-RMSServerAuthentication -AppPrincipalId $fappId -Key $fkey -BposTenantId $fbposId Write-Host ("Information: " + "Connected to Azure RMS Service with BposTenantId: $fbposId using AppPrincipalId: $fappId") $returnValue = $true } catch { Write-Host ("ERROR" + "During connection to Azure RMS Service with BposTenantId: $fbposId using AppPrincipalId: $fappId") } return $returnValue } #**Main Script (Script)********************************************* Write-Host ("-== " + $Script:Name + " " + $Version + " ==-") $Script:isScriptProcess = $True # Validate Azure RMS connection by checking the module and then connection if ($Script:isScriptProcess) { if (Check-Module -Module RMSProtection){ $Script:isScriptProcess = $True } else { Write-Host ("The RMSProtection module is not loaded") -foregroundcolor "yellow" -backgroundcolor "black" $Script:isScriptProcess = $False } } if ($Script:isScriptProcess) { #Write-Host ("Try to connect to Azure RMS with AppId: $AppPrincipalId and BPOSID: $BposTenantId" ) if (Set-RMSConnection $AppPrincipalId $SymmetricKey $BposTenantId) { Write-Host ("Connected to Azure RMS") } else { Write-Host ("Couldn't connect to Azure RMS") -foregroundcolor "yellow" -backgroundcolor "black" $Script:isScriptProcess = $False } } #  Start working loop if ($Script:isScriptProcess) { if ( !(($File -eq $null) -or ($File -eq "")) ) { if (!(Protect-File -ffile $File -ftemplateId $TemplateID -fownermail $OwnerMail)) { $Script:isScriptProcess = $False } } } # Closing if (!$Script:isScriptProcess) { Write-Host "ERROR occurred during script process" -foregroundcolor "red" -backgroundcolor "black"} write-host ("-== " + $Script:Name + " " + $Version + "  ==-") if (!$Script:isScriptProcess) { exit(-1) } else {exit(0)}
```

## 파일을 선택적으로 보호하도록 지침 수정
위에서 설명한 지침이 작동하는 경우에는 보다 자세한 구성용으로 지침을 매우 쉽게 수정할 수 있습니다. 예를 들어 같은 스크립트를 사용해 파일을 보호하되 개인 식별이 가능한 정보를 포함하는 파일만 보호할 수 있으며, 권한이 더 제한적인 템플릿을 선택할 수도 있습니다.

이렇게 하려면 기본 제공 분류 속성 중 하나(예: **개인 식별이 가능한 정보**)를 사용하거나 새 속성을 직접 만듭니다. 그런 다음 이 속성을 사용하는 새 규칙을 만듭니다. 예를 들어 **콘텐츠 분류자**를 선택하고 값이 **높음**인 **개인 식별이 가능한 정보** 속성을 선택한 다음 이 속성에 대해 구성할 파일을 식별하는 문자열 또는 표현식 패턴(예: "**생년월일**" 문자열)을 구성할 수 있습니다.

그리고 나면 스크립트는 동일하지만 다른 템플릿을 사용하는 새 파일 관리 작업을 만들고 방금 구성한 분류 속성에 대해 조건을 구성하기만 하면 됩니다. 예를 들어 이전에 구성한 조건(**RMS** 속성, **같음**, **예**) 대신 **연산자** 값을 **같음**으로 설정했으며 **값**이 **높음**인 **개인 식별이 가능한 정보** 속성을 선택할 수 있습니다.

