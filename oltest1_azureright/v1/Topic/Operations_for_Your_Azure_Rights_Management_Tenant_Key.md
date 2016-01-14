---
description: na
keywords: na
title: Operations for Your Azure Rights Management Tenant Key
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 1284d0ee-0a72-45ba-a64c-3dcb25846c3d
---
# Azure 권한 관리 테넌트 키에 대한 작업
Microsoft Azure 권한 관리(Azure RMS) 테넌트 키를 구현한 후의 제어 및 책임 수준은 테넌트 키 토폴로지(Microsoft 관리 또는 고객 관리)에 따라 다릅니다.

테넌트 키를 직접 관리하는 방식은 대개 BYOK(Bring Your Own Key)라고 합니다. 이 시나리오 및 두 테넌트 키 토폴로지 중 선택하는 방법에 대한 자세한 내용은 [Azure 권한 관리 테넌트 키 계획 및 구현](../Topic/Planning_and_Implementing_Your_Azure_Rights_Management_Tenant_Key.md)을 참조하세요.

다음 표에는 Azure RMS 테넌트 키에 대해 선택한 토폴로지에 따라 수행할 수 있는 작업이 나와 있습니다.

|수명 주기 작업|Microsoft 관리(기본값)|고객 관리(BYOK)|
|------------|---------------------|---------------|
|테넌트 키 해지|아니요(자동)|아니요(자동)|
|테넌트 키 다시 입력|예|예|
|테넌트 키 백업/복구|아니요|예|
|테넌트 키 내보내기|예|아니요|
|위반 사항에 대응|예|예|
구현한 토폴로지를 파악한 후 다음 섹션 중 하나에서 Azure RMS 테넌트 키에 수행할 수 있는 이러한 작업에 대한 자세한 내용을 확인하세요.

## <a name="BKMK_MSManagedOperations"></a>Microsoft 관리: 테넌트 키 수명 주기 작업
Microsoft에서 Azure 권한 관리용 테넌트 키를 관리하는 경우(기본값) 다음 섹션에서 이 토폴로지와 관련된 수명 주기 작업에 대한 자세한 내용을 확인하세요.

-   [테넌트 키 해지](../Topic/Operations_for_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_MSRevoke)

-   [테넌트 키 다시 입력](../Topic/Operations_for_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_MSRekey)

-   [테넌트 키 백업/복구](../Topic/Operations_for_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_MSBackup)

-   [테넌트 키 내보내기](../Topic/Operations_for_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_MSExport)

-   [위반 사항에 대응](../Topic/Operations_for_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_MSBreach)

### <a name="BKMK_MSRevoke"></a>테넌트 키 해지
Azure RMS 구독을 취소하면 Azure RMS에서 테넌트 키 사용을 중지하며 사용자는 아무런 작업을 수행할 필요가 없습니다.

### <a name="BKMK_MSRekey"></a>테넌트 키 다시 입력
키 다시 입력을 키 롤링이라고도 합니다. 반드시 필요한 경우가 아니면 테넌트 키를 다시 입력하지 마세요. Office 2010 등의 이전 클라이언트는 키 변경 내용을 정상적으로 처리하지 못합니다. 이러한 경우에는 그룹 정책 또는 해당하는 메커니즘을 사용하여 컴퓨터에서 RMS 상태를 지워야 합니다. 그러나 테넌트 키를 다시 입력해야 하는 몇 가지 상황도 있습니다. 예를 들면 다음과 같습니다.

-   회사가 둘 이상으로 분할된 경우. 테넌트 키를 다시 입력하면 새 회사에서는 직원이 게시하는 새 콘텐츠에 액세스할 수 없습니다. 이전 테넌트 키의 복사본이 있으면 이전 콘텐츠에는 액세스할 수 있습니다.

-   테넌트 키의 마스터 복사본(현재 소유 중인 복사본)이 노출되었다고 판단되는 경우.

Microsoft CSS(고객 지원 서비스)에 전화를 하여 테넌트 관리자임을 증명하면 테넌트 키를 다시 입력할 수 있습니다.

테넌트 키를 다시 입력하면 새 테넌트 키를 사용하여 새 콘텐츠를 보호합니다. 이 과정은 단계별로 진행되므로 일정 시간 동안에는 일부 새 콘텐츠가 계속해서 이전 테넌트 키로 보호됩니다. 이전에 보호되었던 콘텐츠도 이전 테넌트 키로 계속 보호됩니다. 이 시나리오를 지원하기 위해 Azure RMS에서는 이전 콘텐츠용 라이선스를 발급할 수 있도록 이전 테넌트 키를 보존합니다.

### <a name="BKMK_MSBackup"></a>테넌트 키 백업/복구
Microsoft에서 테넌트 키를 백업하며 사용자는 아무런 작업을 수행할 필요가 없습니다.

### <a name="BKMK_MSExport"></a>테넌트 키 내보내기
다음 3단계의 지침에 따라 Azure RMS 구성 및 테넌트 키를 내보낼 수 있습니다.

##### 1단계: 내보내기 시작

-   이 작업을 수행하려면 Microsoft CSS(고객 지원 서비스)에 문의해야 합니다. 이때 자신이 Azure RMS 테넌트의 관리자임을 증명해야 합니다.

##### 2단계: 확인 대기

-   Microsoft는 RMS 테넌트 키 해제 요청이 합법적인지 확인합니다. 이 프로세스는 최대 3주까지 걸릴 수 있습니다.

##### 3단계: CSS에서 키 관련 지침 받기

-   Microsoft CSS(고객 지원 서비스)에서 Azure RMS 구성 및 테넌트 키를 파일 이름 확장명이 .tpd인 암호로 보호된 파일에 암호화된 상태로 포함하여 전송합니다. 이를 위해 CSS는 먼저 내보내기를 시작한 사용자에게 전자 메일로 도구를 보냅니다. 다음과 같이 명령 프롬프트에서 해당 도구를 실행해야 합니다.

    ```
    AadrmTpd.exe -createkey
    ```
    그러면 RSA 키 쌍이 생성되며 공용 및 개인 키가 현재 폴더에 파일로 저장됩니다. 예를 들어 **PublicKey-FA29D0FE-5049-4C8E-931B-96C6152B0441.txt** 및 **PrivateKey-FA29D0FE-5049-4C8E-931B-96C6152B0441.txt**입니다.

    이름이 **PublicKey**로 시작하는 파일을 첨부하여 CSS의 전자 메일에 회신합니다. 그러면 CSS에서 RSA 키를 사용하여 암호화된 .xml 파일 형태로 TPD 파일을 보냅니다. 원래 AadrmTpd 도구를 실행한 것과 같은 폴더에 이 파일을 복사하고 **PrivateKey**로 시작하는 파일과 CSS의 파일을 사용하여 도구를 다시 실행합니다. 예를 들면 다음과 같습니다.

    ```
    AadrmTpd.exe -key PrivateKey-FA29D0FE-5049-4C8E-931B-96C6152B0441.txt -target TPD-77172C7B-8E21-48B7-9854-7A4CEAC474D0.xml
    ```
    이 명령을 실행하면 두 개의 파일이 출력되어야 합니다. 그 중 하나는 암호로 보호된 TPD의 일반 텍스트 암호가 포함된 파일이고 다른 하나는 암호로 보호된 TPD 자체입니다. 상호 참조를 위해 두 파일의 GUID는 AadrmTpd.exe -createkey 명령을 실행할 때의 공용 키 및 개인 키 파일과 같아야 합니다.

    -   Password-FA29D0FE-5049-4C8E-931B-96C6152B0441.txt

    -   ExportedTPD-FA29D0FE-5049-4C8E-931B-96C6152B0441.xml

    이 테넌트 키로 보호되는 콘텐츠를 해독할 수 있게 이 파일을 백업하여 안전하게 보관합니다. 또한 AD RMS로 마이그레이션하는 경우에는 이 TPD 파일(**ExportedTDP**로 시작하는 파일)을 AD RMS 서버로 가져올 수 있습니다.

##### 4단계: 지속적인 테넌트 키 보호

-   테넌트 키를 받은 후에는 지속적으로 보호해야 합니다. 테넌트 키에 액세스할 수 있으면 보호되는 모든 문서의 암호를 해당 키를 사용하여 해독할 수 있기 때문입니다.

    Azure RMS를 더 이상 사용하지 않아 테넌트 키를 내보내는 경우에는 RMS 테넌트를 즉시 비활성화하는 것이 가장 좋습니다. 테넌트 키를 받을 때까지 기다렸다가 테넌트를 비활성화하지 마세요. 이러한 예방 조치를 취해야 권한이 없는 사람이 테넌트 키에 액세스하는 경우의 영향을 최소화할 수 있습니다. 자세한 내용은 [Azure 권한 관리 해제 및 비활성화](../Topic/Decommissioning_and_Deactivating_Azure_Rights_Management.md)을 참조하십시오.

### <a name="BKMK_MSBreach"></a>위반 사항에 대응
아무리 강력한 보안 시스템이라도 위반 대응 프로세스가 없다면 완벽하다고 할 수 없습니다. 테넌트 키는 노출되거나 도용될 수 있습니다. 테넌트 키를 효율적으로 보호한다고 하더라도 현재 생성 HSM 기술 또는 현재 키 길이/알고리즘에 취약점이 있을 수도 있습니다.

Microsoft에서는 전담 팀이 제품 및 서비스의 보안 문제에 대응하고 있습니다. 이 팀은 신뢰할 만한 문제 보고서가 확인되는 즉시 해당 범위, 근본 원인 및 완화 방법을 조사합니다. 이 문제가 사용자의 자산에 영향을 주는 경우 Microsoft는 구독 시 사용자가 제공한 주소를 사용해 전자 메일로 Azure RMS 테넌트 관리자에게 문제를 알립니다.

보안 위반이 발생한 경우 사용자나 Microsoft에서 수행할 수 있는 최선의 작업은 위반 범위에 따라 다르며, Microsoft는 사용자와 협의하여 이 프로세스를 진행합니다. 다음 표에는 몇 가지 일반적인 상황과 가능한 대응 방법이 나와 있습니다. 정확한 대응 방법은 조사 중에 확인되는 모든 정보에 따라 달라집니다.

|문제 설명|가능한 대응 방법|
|---------|-------------|
|테넌트 키가 유출되었습니다.|테넌트 키를 다시 입력합니다. 이 항목의 [테넌트 키 다시 입력](../Topic/Operations_for_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_MSRekey) 섹션을 참조하세요.|
|권한이 없는 개인이나 맬웨어가 테넌트 키 사용 권한을 확보했으나 키 자체가 유출되지는 않았습니다.|이 경우에는 테넌트 키를 다시 입력해도 도움이 되지 않으며 근본 원인을 분석해야 합니다. 프로세스 또는 소프트웨어 버그로 인해 권한이 없는 개인이 액세스 권한을 얻은 경우에는 해당 상황을 해결해야 합니다.|
|RSA 알고리즘이나 키 길이에 취약점이 있거나 전산상 무차별 암호 대입 공격(brute force attack)이 가능합니다.|Microsoft에서 복원 가능한 더 긴 키 길이와 새 알고리즘을 지원하도록 Azure RMS를 업데이트하고 모든 고객에게 테넌트 키를 갱신하도록 지시해야 합니다.|

## <a name="BKMK_BYOKManagedOperations"></a>고객 관리: 테넌트 키 수명 주기 작업
Azure 권한 관리용 테넌트 키를 직접 관리하는 경우(BYOK(Bring Your Own Key) 시나리오) 다음 섹션에서 이 토폴로지와 관련된 수명 주기 작업에 대한 자세한 내용을 확인하세요.

-   [테넌트 키 해지](../Topic/Operations_for_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_BYOKRevoke)

-   [테넌트 키 다시 입력](../Topic/Operations_for_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_BYOKRekey)

-   [테넌트 키 백업/복구](../Topic/Operations_for_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_BYOKBackup)

-   [테넌트 키 내보내기](../Topic/Operations_for_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_BYOKExport)

-   [위반 사항에 대응](../Topic/Operations_for_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_BYOKBreach)

### <a name="BKMK_BYOKRevoke"></a>테넌트 키 해지
Azure RMS 구독을 취소하면 Azure RMS에서 테넌트 키 사용을 중지하며 사용자는 아무런 작업을 수행할 필요가 없습니다.

### <a name="BKMK_BYOKRekey"></a>테넌트 키 다시 입력
키 다시 입력을 키 롤링이라고도 합니다. 반드시 필요한 경우가 아니면 테넌트 키를 다시 입력하지 마세요. Office 2010 등의 이전 클라이언트는 키 변경 내용을 정상적으로 처리하지 못합니다. 이러한 경우에는 그룹 정책 또는 해당하는 메커니즘을 사용하여 컴퓨터에서 RMS 상태를 지워야 합니다. 그러나 테넌트 키를 다시 입력해야 하는 몇 가지 상황도 있습니다. 예를 들면 다음과 같습니다.

-   회사가 둘 이상으로 분할된 경우. 테넌트 키를 다시 입력하면 새 회사에서는 직원이 게시하는 새 콘텐츠에 액세스할 수 없습니다. 이전 테넌트 키의 복사본이 있으면 이전 콘텐츠에는 액세스할 수 있습니다.

-   테넌트 키의 마스터 복사본(현재 소유 중인 복사본)이 노출되었다고 판단되는 경우.

테넌트 키를 다시 입력하면 새 테넌트 키를 사용하여 새 콘텐츠를 보호합니다. 이 과정은 단계별로 진행되므로 일정 시간 동안에는 일부 새 콘텐츠가 계속해서 이전 테넌트 키로 보호됩니다. 이전에 보호되었던 콘텐츠도 이전 테넌트 키로 계속 보호됩니다. 이 시나리오를 지원하기 위해 Azure RMS에서는 이전 콘텐츠용 라이선스를 발급할 수 있도록 이전 테넌트 키를 보존합니다.

테넌트 키를 다시 입력하려면 [BYOK(Bring Your Own Key) 구현](../Topic/Planning_and_Implementing_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_ImplementBYOK) 항목의 [Azure 권한 관리 테넌트 키 계획 및 구현](../Topic/Planning_and_Implementing_Your_Azure_Rights_Management_Tenant_Key.md) 섹션 절차에 따라 인터넷을 통해 또는 직접 방문하여 새 키를 생성하고 만듭니다.

### <a name="BKMK_BYOKBackup"></a>테넌트 키 백업/복구
테넌트 키를 직접 백업해야 합니다. Thales HSM에서 생성한 테넌트 키를 백업하려면 토큰화된 키 파일, World 파일 및 관리자 카드만 백업하면 됩니다.

[BYOK(Bring Your Own Key) 구현](../Topic/Planning_and_Implementing_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_ImplementBYOK) 항목의 [Azure 권한 관리 테넌트 키 계획 및 구현](../Topic/Planning_and_Implementing_Your_Azure_Rights_Management_Tenant_Key.md) 섹션 절차에 따라 키를 전송한 경우 Azure RMS는 Azure RMS 노드의 오류로부터 보호하기 위해 토큰화된 키 파일을 보존합니다. 그러나 이러한 보존이 전체 백업은 아닙니다. 예를 들어 Thales HSM 외부에서 사용할 키의 일반 텍스트 복사본이 필요한 경우 Azure RMS는 복구 불가능한 복사본만 보존하므로 해당 복사본을 검색할 수 없습니다.

### <a name="BKMK_BYOKExport"></a>테넌트 키 내보내기
BYOK 사용 시에는 Azure RMS에서 테넌트 키를 내보낼 수 없습니다. Azure RMS의 복사본은 복구할 수 없습니다. 더 이상 사용할 수 없도록 이 키를 삭제하려는 경우 Microsoft CSS(고객 지원 서비스)에 문의하세요.

### <a name="BKMK_BYOKBreach"></a>위반 사항에 대응
아무리 강력한 보안 시스템이라도 위반 대응 프로세스가 없다면 완벽하다고 할 수 없습니다. 테넌트 키는 노출되거나 도용될 수 있습니다. 테넌트 키를 효율적으로 보호한다고 하더라도 현재 생성 HSM 기술 또는 현재 키 길이/알고리즘에 취약점이 있을 수도 있습니다.

Microsoft에서는 전담 팀이 제품 및 서비스의 보안 문제에 대응하고 있습니다. 이 팀은 신뢰할 만한 문제 보고서가 확인되는 즉시 해당 범위, 근본 원인 및 완화 방법을 조사합니다. 이 문제가 사용자의 자산에 영향을 주는 경우 Microsoft는 구독 시 사용자가 제공한 주소를 사용해 전자 메일로 Azure RMS 테넌트 관리자에게 문제를 알립니다.

보안 위반이 발생한 경우 사용자나 Microsoft에서 수행할 수 있는 최선의 작업은 위반 범위에 따라 다르며 Microsoft는 사용자와 협의하여 이 프로세스를 진행합니다. 다음 표에는 몇 가지 일반적인 상황과 가능한 대응 방법이 나와 있습니다. 정확한 대응 방법은 조사 중에 확인되는 모든 정보에 따라 달라집니다.

|문제 설명|가능한 대응 방법|
|---------|-------------|
|테넌트 키가 유출되었습니다.|테넌트 키를 다시 입력합니다. 이 항목의 [테넌트 키 다시 입력](../Topic/Operations_for_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_BYOKRekey) 섹션을 참조하세요.|
|권한이 없는 개인이나 맬웨어가 테넌트 키 사용 권한을 확보했으나 키 자체가 유출되지는 않았습니다.|이 경우에는 테넌트 키를 다시 입력해도 도움이 되지 않으며 근본 원인을 분석해야 합니다. 프로세스 또는 소프트웨어 버그로 인해 권한이 없는 개인이 액세스 권한을 얻은 경우에는 해당 상황을 해결해야 합니다.|
|현재 생성 HSM 기술에서 취약점이 발견되었습니다.|Microsoft에서 HSM을 업데이트해야 합니다. 취약점으로 인해 키가 노출되었다고 생각되면 Microsoft는 모든 고객에게 테넌트 키를 갱신할 것을 지시합니다.|
|RSA 알고리즘이나 키 길이에 취약점이 있거나 전산상 무차별 암호 대입 공격(brute force attack)이 가능합니다.|Microsoft에서 복원 가능한 더 긴 키 길이와 새 알고리즘을 지원하도록 Azure RMS를 업데이트하고 모든 고객에게 테넌트 키를 갱신하도록 지시해야 합니다.|

## 참고 항목
[Azure Rights Management 사용](../Topic/Using_Azure_Rights_Management.md)

