---
description: na
keywords: na
title: Logging and Analyzing Azure Rights Management Usage
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: a735f3f7-6eb2-4901-9084-8c3cd3a9087e
---
# Azure 권한 관리 사용 현황 로깅 및 분석
이 항목의 정보를 통해 Azure RMS(Azure 권한 관리)를 사용한 사용 현황 로깅 방법을 파악할 수 있습니다. Azure 권한 관리 서비스는 조직에 대해 수행하는 모든 요청을 기록할 수 있습니다. 여기에는 사용자의 요청, 조직의 권한 관리 관리자가 수행하는 작업, 그리고 Azure 권한 관리 배포를 지원하기 위해 Microsoft 운영자가 수행하는 작업이 포함됩니다.

이러한 Azure 권한 관리 로그는 다음과 같은 비즈니스 시나리오를 지원하는 데 사용할 수 있습니다.

-   비즈니스 관련 정보 파악

    Azure 권한 관리는 사용자가 입력하는 Azure 저장소 계정에 W3C 확장 로그 형식으로 로그를 기록합니다. 이러한 로그를 데이터베이스, OLAP(온라인 분석 처리) 시스템 또는 맵 감소 시스템과 같은 선택한 리포지토리로 이동하여 정보를 분석하고 보고서를 생성할 수 있습니다. 예를 들어 RMS로 보호된 데이터에 액세스하는 사용자를 파악할 수 있습니다. 그리고 사용자들이 액세스하는 RMS로 보호된 데이터 및 액세스에 사용하는 장치와 액세스 위치를 확인할 수 있습니다. 사용자들이 보호된 콘텐츠를 정상적으로 읽을 수 있는지 확인할 수 있으며, 보호된 중요 문서를 사용자들이 읽었는지도 파악할 수 있습니다.

-   남용 모니터링

    Azure 권한 관리 로깅 정보는 거의 실시간으로 제공되므로 회사의 권한 관리 사용을 지속적으로 모니터링할 수 있습니다. 로그의 99.9%는 RMS에서 작업을 시작한 후 15분 이내에 사용 가능합니다.

    예를 들어 표준 업무 시간 이외의 시간에 RMS로 보호된 데이터를 읽는 사용자 수가 갑자기 증가하면 알림을 받을 수 있습니다. 이러한 현상은 악의적인 사용자가 경쟁자에게 판매하기 위해 정보를 수집하는 것일 수 있기 때문입니다. 또한 같은 사용자가 짧은 시간 내에 서로 다른 두 IP 주소에서 데이터에 액세스하는 경우에는 해당 사용자의 계정이 노출된 것일 수 있습니다.

-   법정 분석 수행

    정보가 유출된 경우 최근 특정 문서에 액세스한 사용자와 유출이 의심되는 사용자가 최근 액세스한 정보를 확인해야 할 가능성이 높습니다. Azure 권한 관리 및 로깅을 사용하는 경우 이러한 유형의 정보를 쉽게 파악할 수 있습니다. 보호된 콘텐츠를 사용하는 사용자는 Azure 권한 관리로 보호되는 문서와 사진을 열려면 항상 권한 관리 라이선스를 받아야 합니다. 전자 메일을 통해 이러한 파일을 이동하거나 USB 드라이브 또는 기타 저장소 장치에 복사하는 경우에도 마찬가지입니다. 즉, Azure 권한 관리를 사용하여 데이터를 보호할 때는 Azure 권한 관리 로그를 법정 분석용의 최종 정보 출처로 사용할 수 있습니다.

> [!NOTE]
> Azure 권한 관리에 대한 관리 작업 로깅만 사용하고 사용자가 권한 관리를 사용하는 방법은 추적하지 않으려는 경우 Azure 권한 관리에 대한 [Get-AadrmAdminLog](https://msdn.microsoft.com/library/azure/dn629430.aspx) Windows PowerShell cmdlet을 사용할 수 있습니다.
> 
> **RMS 사용**, **가장 활동적인 RMS 사용자**, **RMS 장치 사용** 및 **RMS 사용 응용 프로그램 사용**이 포함되어 있는 높은 수준의 사용 현황 보고서에 대해 Azure 클래식 포털을 사용할 수도 있습니다. Azure 클래식 포털에서 이러한 보고서에 액세스하려면 **Active Directory**를 클릭하고 디렉터리를 연 다음 **보고서**를 클릭합니다.

다음 섹션에서 Azure 권한 관리 사용 현황 로깅과 관련된 자세한 내용을 확인할 수 있습니다.

-   [Azure 권한 관리 사용 현황 로깅 사용 방법](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md#BKMK_EnableRMSLogging)

-   [Azure 권한 관리 사용 현황 로그에 액세스 및 사용 방법](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md#BKMK_AccesAndUseLogs)

-   [Azure 권한 관리 로그 저장소를 관리하는 방법](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md#BKMK_ManageStorage)

-   [Azure 권한 관리 사용 현황 로그에 대한 액세스를 위임하는 방법](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md#BKMK_Delegate)

-   [Azure 권한 관리 사용 현황 로그를 해석하는 방법](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md#BKMK_Interpret)

-   [Windows PowerShell 참조](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md#BKMK_PowerShell)

## <a name="BKMK_EnableRMSLogging"></a>Azure 권한 관리 사용 현황 로깅 사용 방법
Azure 권한 관리 사용 현황 로깅은 선택 사항이며 사용하려는 경우 특정 단계를 수행해야 합니다. Azure 권한 관리 사용 현황 로깅 사용 시에도 권한 관리 작동 방식은 변경되지 않으며 로깅 프로세스 자체는 무료입니다. 그러나 로그를 저장할 Azure 저장소 계정을 제공해야 하며 이 저장소에 대해 요금이 청구됩니다.

시작하기 전에 Azure 권한 관리 사용 현황 로깅을 사용하기 위한 다음과 같은 필수 구성 요소를 충족하는지 확인합니다.

|요구 사항|추가 정보|
|---------|---------|
|Azure 권한 관리를 포함하는 IT 관리 구독|조직에서 관리하는 Microsoft Azure 권한 관리 구독이 있어야 합니다. 개인용 RMS를 사용하는 조직은 Azure 권한 관리 사용 현황 로깅을 사용할 수 없습니다.<br /><br />조직에 개인용 RMS 사용자가 있으면 Azure 권한 관리 사용 현황 로깅 기능을 사용하기 위해 개인용 RMS를 Microsoft Azure 권한 관리 구독으로 변환하는 것이 업무상 매우 유리합니다.<br /><br />Azure RMS를 포함하는 구독에 대한 자세한 내용은 [Azure 권한 관리 요구 사항](../Topic/Requirements_for_Azure_Rights_Management.md) 항목의 [Azure RMS를 지원하는 클라우드 구독](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_SupportedSubscriptions) 섹션을 참조하세요.<br /><br />개인용 RMS에 대한 자세한 내용은 [개인용 RMS 및 Azure 권한 관리](../Topic/RMS_for_Individuals_and_Azure_Rights_Management.md)를 참조하세요.|
|구독을|Azure 구독이 있어야 하며 Azure 권한 관리 로그를 저장하기에 충분한 저장소가 Azure에 있어야 합니다.|
|Azure 권한 관리용 Windows PowerShell|Azure 권한 관리용 Windows PowerShell 모듈을 아직 다운로드하여 설치하지 않은 경우 다운로드한 후 설치합니다. Windows PowerShell cmdlet을 사용하여 Azure 권한 관리 사용 현황 로그를 구성하고 관리합니다.<br /><br />자세한 내용은 [Azure 권한 관리용 Windows PowerShell 설치](../Topic/Installing_Windows_PowerShell_for_Azure_Rights_Management.md)를 참조하세요.|
다음 절차에 따라 Azure 권한 관리 사용 현황 로깅을 사용하도록 설정합니다. 이때 Azure 저장소 계정을 만든 다음 권한 관리 로그에 이 저장소 계정을 사용하도록 Azure를 구성하는 단계를 함께 수행합니다.

> [!NOTE]
> 이 절차에서는 사용자에게 Azure 계정이 있다고 가정합니다. Azure 권한 관리 사용 현황 로깅에서는 개별 계정도 지원하지만 회사 또는 학교 계정을 사용하는 것이 가장 좋습니다. 또한 권한 관리 로그용으로 전용 저장소 계정을 만드는 것이 좋습니다. 저장소 액세스 키를 Azure 권한 관리와 공유해야 하며 로그 파일을 사용할 다른 사용자가 있는 경우 해당 사용자와도 키를 공유해야 할 수 있습니다.
> 
> Azure 저장소에 대한 자세한 내용은 [저장소에 대한 Azure 설명서](http://azure.microsoft.com/documentation/services/storage/)를 참조하세요.

#### 저장소 계정을 만들고 Azure 권한 관리 사용 현황 로깅을 사용하는 방법

1.  [Azure 포털](https://portal.azure.com/)에 로그인합니다.

2.  허브 메뉴에서 **새로 만들기** -&gt; **데이터 + 저장소** -&gt; **저장소 계정**을 선택합니다.

    > [!TIP]
    > 이 옵션이 표시되지 않으면 권한 관리에 대한 구독 외에 Azure 구독이 있는지 확인합니다.

3.  기본 배포 모델을 **클래식**으로 유지하고 **만들기**를 클릭합니다.

    저장소 계정에 대한 이름을 지정하고 필요한 경우 **가격 책정 계층**, **리소스 그룹**, **구독**, 및 **대시보드에 고정** 여부에 대해 선택한 옵션을 변경합니다. 그런 다음 **만들기**를 클릭합니다.**저장소 계정 만들기** 작업이 완료될 때까지 기다립니다.

4.  새로 만든 저장소 계정을 클릭한 다음 **설정**을 클릭합니다.

5.  **설정** 블레이드에서 **키** 아이콘을 클릭합니다.

6.  **키 관리** 블레이드에서 **기본 액세스 키** 값을 복사하고 블레이드를 닫습니다.

7.  **관리자 권한으로 실행** 옵션을 사용하여 Windows PowerShell을 시작합니다.[Connect-AadrmService](https://msdn.microsoft.com/library/azure/dn629415.aspx) 명령을 실행하여 Azure 권한 관리 서비스에 연결합니다.

    ```
    Connect-AadrmService
    ```

8.  [Set-AadrmUsageLogStorageAccount](https://msdn.microsoft.com/library/azure/dn629426.aspx) 명령을 사용하여 Azure 권한 관리 사용 현황 로그를 보관할 위치를 지정합니다. 이때 *&lt;Access_Key&gt;*는 6단계에서 복사한 기본 액세스 키로 바꾸고 *&lt;StorageAccount&gt;*는 3단계에서 만든 저장소 계정의 이름으로 바꿉니다.

    ```
    $accesskey = convertto-securestring -asplaintext -force –string <Access_Key> Set-AadrmUsageLogStorageAccount -AccessKey $accesskey -StorageAccount <StorageAccount>
    ```

9. [Enable-AadrmUsageLogFeature](https://msdn.microsoft.com/library/azure/dn629421.aspx) 명령을 사용하여 Azure 권한 관리 사용 현황 로깅을 사용하도록 설정합니다.

    ```
    Enable-AadrmUsageLogFeature
    ```
    그러면 다음 메시지가 표시됩니다. **권한 관리 서비스에 대해 사용 현황 로그 기능을 사용하도록 설정되었습니다.**

이제 사용 현황 로깅을 사용하도록 설정했으므로 Azure 권한 관리 기능이 조직의 모든 작업을 기록하기 시작하며 해당 정보를 저장소 계정에 저장합니다. 이 시점 전에는 로깅 정보를 사용할 수 없습니다.

저장소 계정을 만드는 방법에 대한 자세한 내용은 Azure 설명서에서 [Azure 저장소 계정 정보](https://azure.microsoft.com/documentation/articles/storage-create-storage-account/)의 [저장소 계정 만들기](https://azure.microsoft.com/documentation/articles/storage-create-storage-account/) 섹션을 참조하세요.

## <a name="BKMK_AccesAndUseLogs"></a>Azure 권한 관리 사용 현황 로그에 액세스 및 사용 방법
Azure 권한 관리는 로그를 일련의 Blob으로 Azure 저장소 계정에 기록합니다. 각 Blob에는 W3C 확장 로그 형식의 로그 레코드가 하나 이상 포함됩니다. Blob 이름은 숫자이며 작성된 순서를 나타냅니다. 이 문서 뒷부분의 [Azure 권한 관리 사용 현황 로그를 해석하는 방법](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md#BKMK_Interpret) 섹션에 로그 콘텐츠 및 로그 작성에 대한 자세한 내용이 나와 있습니다.

Azure 권한 관리 작업 이후 저장소 계정에 로그가 표시될 때까지 다소 시간이 걸릴 수 있습니다. 대부분의 로그는 15분 이내에 표시됩니다.

Azure 권한 관리 사용 현황 로그용으로 만든 저장소 계정은 사서함과 비슷하며 저장소 계정에서 직접 읽기를 지원하지만 이러한 방식으로 사용하도록 최적화되어 있지는 않습니다. 그러나 성능을 최대화하고 비용을 줄이려면 로컬 폴더, 데이터베이스 또는 맵 감소 리포지토리와 같은 로컬 저장소에 로그를 다운로드하는 것이 좋습니다.

두 가지 방법으로 사용 현황 로그를 다운로드할 수 있습니다.

-   Windows PowerShell cmdlet [Get-AadrmUsageLog](https://msdn.microsoft.com/library/azure/dn629401.aspx)를 사용합니다.

    이 방법을 사용하면 사용 현황 로그에 가장 간편하게 액세스할 수 있습니다. 이 cmdlet은 로그를 컴퓨터에 다운로드합니다. 즉, 사용자가 지정한 위치에 각 Blob을 파일로 다운로드합니다.

-   [Azure 저장소 SDK](http://www.windowsazure.com/en-us/develop/net/)를 사용하여 로그를 다운로드하는 사용자 지정 응용 프로그램을 직접 작성합니다.

    사용자 지정 응용 프로그램은 Get-AadrmUsageLogs cmdlet에 비해 좀 더 유동적으로 사용할 수 있습니다. 예를 들어, 내 Azure 권한 관리의 관리 자격 증명을 사용해서는 안 되는 프로세스에 또는 다른 사용자에게 로그 다운로드를 위임할 수 있습니다. 또는 오용을 모니터링하기 위해 로그를 실시간으로 폴링할 수도 있습니다.

#### PowerShell을 사용하여 사용 현황 로그를 다운로드하려면

-   **관리자 권한으로 실행** 옵션을 사용하여 Windows PowerShell을 시작하고 **Get-AadrmUsageLog –Path &lt;location&gt;**을 실행합니다. 예를 들어 E 드라이브에 **logs** 폴더를 만든 후에

    -   사용 가능한 모든 로그를 E:\logs 폴더에 다운로드하려면 다음 cmdlet을 실행합니다.`Get-AadrmUsageLog -Path "e:\logs"`

    -   특정 Blob 범위를 다운로드하려면 다음 cmdlet을 실행합니다.`Get-AadrmUsageLog –Path "e:\logs" –FromCounter 1024 –ToCounter 2047`

이러한 cmdlet을 실행하면 Windows PowerShell에 마지막으로 다운로드한 Blob의 이름이 표시됩니다. 이 이름을 변수에 할당할 수 있습니다. 그러면 예약 작업이나 루프에서 Get-AadrmUsageLog를 실행하여 매번 증분 로그만 다운로드할 수 있습니다.

예를 들면 다음과 같습니다.

**PS C:\&gt; $LastBlobName = Get-AadrmUsageLog –Path "e:\logs"**

**1527**

**PS C:\&gt; $LastBlobName**

**1527**

> [!TIP]
> 잘 알려진 여러 로그 형식 간을 변환하는 데 사용할 수 있는 도구인 [Microsoft 로그 구문 분석기](http://www.microsoft.com/download/details.aspx?id=24659)를 사용하면 다운로드한 모든 로그 파일을 CSV 형식으로 집계할 수 있습니다. 이 도구를 사용하여 데이터를 SYSLOG 형식으로 변환하거나 데이터베이스로 가져올 수도 있습니다. 도구를 설치한 후 **LogParser.exe /?**를 실행하면 이 도구 사용을 위한 정보와 도움말을 확인할 수 있습니다. 예를 들어 모든 정보를 .log 파일 형식으로 가져오려면 다음 명령을 실행합니다. **logparser –i:w3c –o:csv “SELECT &#42; INTO AllLogs.csv FROM &#42;.log”**

사용 현황 로깅은 일시 중단하고 다시 시작할 수 있습니다. 로깅을 일시 중단하면 Azure 권한 관리가 저장소 계정 정보를 보존하므로 로깅을 쉽게 다시 시작할 수 있습니다.

#### 사용 현황 로깅을 일시 중단하고 다시 시작하려면

-   로깅을 일시 중단하려면 다음 cmdlet을 사용합니다. [Disable-AadrmUsageLogFeature](https://msdn.microsoft.com/library/azure/dn629404.aspx)

-   로깅을 다시 시작하려면 다음 cmdlet을 사용합니다. [Enable-AadrmUsageLogFeature](https://msdn.microsoft.com/library/azure/dn629421.aspx)

-   로깅을 사용하도록 설정되어 있는지 여부를 확인하려면 다음 cmdlet을 사용합니다. [Get-AadrmUsageLogFeature](https://msdn.microsoft.com/library/azure/dn629425.aspx)

    값이 **True**이면 Azure 권한 관리에 로깅을 사용하도록 설정한 것이고 **False**이면 사용 현황 로깅을 사용하지 않도록 설정한 것입니다.

## <a name="BKMK_ManageStorage"></a>Azure 권한 관리 로그 저장소를 관리하는 방법
Azure 권한 관리 로그를 보관하는 데 사용하는 저장소 공간에는 요금이 청구됩니다.

Azure 권한 관리는 사용 현황 로그 파일을 자동으로 관리하지 않습니다. 사용자가 작업을 수행하지 않으면 로그는 저장소 계정에 계속 남아 있습니다. 그러나 공간을 절약하고 저장소 비용을 줄이려면 로그를 다운로드한 후에 삭제해야 합니다. 삭제할 파일을 선택할 수도 있습니다. 단, Azure 권한 관리는 이러한 로그 파일을 사용하지 않으므로 삭제 가능 시기에는 제한이 없습니다.

삭제하거나 수정해서는 안 되는 파일은 **rms-metadata** 컨테이너에 있는 **메타데이터**입니다. Azure 권한 관리는 이 Blob을 사용하여 마지막으로 사용한 Blob 번호를 추적합니다. 이 파일이 삭제되면 Azure 권한 관리는 로그용으로 새 컨테이너를 시작하며 Blob 번호는 1부터 시작됩니다. 그리고 나면 Get-AadrmUsageLog cmdlet을 사용하는 이후 모든 다운로드에서는 이 새 컨테이너를 사용하여 로그 파일을 다운로드합니다. 따라서 원래 컨테이너의 로그는 모두 유지되지만 분리된 상태가 됩니다. 이처럼 분리된 로그를 다운로드하려면 Azure 저장소 SDK를 사용해야 합니다.

> [!TIP]
> Azure 권한 관리 로그 저장소를 직접 관리하는 대신 저장소 계정 이름과 액세스 키를 공유하여 이 관리 기능을 다른 회사에 위임할 수 있습니다. 자세한 내용은 이 항목의 뒷부분에 나오는 [Azure 권한 관리 사용 현황 로그에 대한 액세스를 위임하는 방법](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md#BKMK_Delegate) 섹션을 참조하세요.

저장소 액세스 키를 다시 생성해야 하는 경우도 있습니다. 예를 들면 다음과 같습니다.

-   Azure 권한 관리 사용 현황 로그를 관리하는 회사를 변경합니다.

-   저장소 액세스 키가 노출된 것으로 의심되는 경우

이러한 상황에서는 보조 액세스 키(이전에 기본 액세스 키를 사용했다고 가정하는 경우)를 사용하여 서비스를 계속 제공할 수 있습니다. 이전에 사용하지 않은 액세스 키를 다시 생성하면 새 키를 사용하도록 Azure 권한 관리를 구성해야 합니다. 다음 절차에 따라 보조 액세스 키를 다시 생성하고 해당 키를 사용하도록 Azure 권한 관리를 구성합니다.

#### 보조 액세스 키를 다시 생성하려면

1.  [Azure 포털](https://portal.azure.com/)에 로그인합니다.

2.  **모든 리소스**를 클릭하고 텍스트 상자에 저장소 이름을 입력하여 저장소를 검색합니다.

3.  저장소를 선택하고 **설정**을 클릭합니다.

4.  **키** 아이콘을 클릭합니다.

5.  **키 관리** 섹션에서 **보조 키 다시 생성**을 클릭하고 예를 클릭하여 보조 액세스 키를 다시 생성할 것인지 확인한 다음 새 보조 액세스 키를 클립보드에 복사합니다.

    Azure 포털을 닫지 마세요.

6.  **관리자 권한으로 실행** 옵션을 사용하여 Windows PowerShell을 시작한 다음 [Set-AadrmUsageLogStorageAccount](https://msdn.microsoft.com/library/azure/dn629426.aspx) cmdlet을 사용하여 이 새 액세스 키를 사용하도록 Azure 권한 관리를 구성합니다. 이때 *&lt;StorageAccount&gt;*는 저장소 계정의 이름으로 바꾸고 *&lt;Access_Key&gt;*는 방금 복사한 다시 생성된 보조 액세스 키로 바꿉니다.

    ```
    Set-AadrmUsageLogStorageAccount -StorageAccount <StorageAccount>-AccessKey <Access_Key>
    ```
    > [!WARNING]
    > 이 명령을 실행할 때 다른 저장소 계정으로 전환할 수도 있지만 이렇게 하면 이전 로그가 분리되며 Set-AadrmUsageLogStorageAccount cmdlet 또는 유사한 관리 명령과 기능을 통해 해당 로그에 더 이상 액세스할 수 없게 됩니다.

7.  다시 Azure 포털의 **키 관리** 섹션에서 기본 액세스 키를 다시 생성합니다.

저장소 액세스 키를 관리하는 방법에 대한 자세한 내용은 Azure 설명서에서 [Azure 저장소 계정 정보](https://azure.microsoft.com/documentation/articles/storage-create-storage-account/)의 [저장소 액세스 키 관리](https://azure.microsoft.com/documentation/articles/storage-create-storage-account/) 섹션을 참조하세요.

## <a name="BKMK_Delegate"></a>Azure 권한 관리 사용 현황 로그에 대한 액세스를 위임하는 방법
저장소 계정 이름과 액세스 키를 공유하여 RMS 로그 액세스를 위임할 수 있습니다. 다른 관리 사용자, 조직 내의 개발자 또는 ISV(Independent Software Vendor)에 액세스를 위임할 수 있습니다. 이러한 위임 대상에게는 RMS 관리자 자격 증명이 없기 때문에 Get-AardrmUsageLog cmdlet을 사용하여 RMS 로그를 다운로드할 수 없습니다. 따라서 Windows 저장소 SDK를 사용하여 로그를 다운로드해야 합니다. 또는 Azure 저장소에서 로그를 직접 읽는 응용 프로그램을 작성할 수도 있습니다.

RMS 로그 전용 저장소 계정을 사용할 때는 이러한 방식으로 저장소 계정 이름과 액세스 키를 공유하는 것이 안전합니다. 그러면 다른 사람이 액세스 키를 확보하더라도 해당 키를 사용하여 다른 저장소 계정에 액세스하거나 RMS 테넌트 계정을 사용할 수 없습니다.

## <a name="BKMK_Interpret"></a>Azure 권한 관리 사용 현황 로그를 해석하는 방법
다음 정보를 참조하여 Azure 권한 관리 사용 현황 로그를 해석할 수 있습니다.

### 저장소 계정 레이아웃
Azure 권한 관리는 저장소 계정에 로그를 처음 기록할 때 다음의 두 컨테이너를 만듭니다.

-   **Rms-metadata**: 이 컨테이너는 Azure 권한 관리용으로 예약되어 있습니다. 수정하거나 삭제해서는 안 됩니다.

-   **Rms-logs-&lt;guid&gt;**: Azure 권한 관리는 이 컨테이너에 로그를 만들고 저장합니다. 이 컨테이너에 포함된 로깅 정보가 더 이상 필요하지 않으면 해당 컨테이너의 파일을 삭제해도 안전합니다.

시간이 지남에 따라 Azure 권한 관리가 **Rms-logs-&lt;guid&gt;** 컨테이너를 추가로 만들 수도 있습니다. 예를 들어 **Rms-metadata** 컨테이너가 손상되거나 실수로 삭제된 경우 Azure 권한 관리는 해당 콘텐츠를 다시 설정하고 이후의 모든 로그를 저장하기 위한 새 **Rms-logs-&lt;guid&gt;** 컨테이너를 만듭니다. 그러면 이전 컨테이너의 이전 로그는 삭제되지는 않으며 분리됩니다.

### 로그 순서
Azure 권한 관리는 일련의 Blob으로 로그를 기록합니다. 각 Blob에는 확장 W3C 로그 형식의 로그 레코드가 하나 이상 포함됩니다.

각 Blob의 이름은 숫자로 되어 있습니다. 각 로그 컨테이너 내에서 첫 번째 blob 이름은 000000001입니다. 각 blob 이름은 만들어진 순서대로 순차적으로 지정됩니다. 각 Blob에는 로그 레코드가 하나 이상 포함됩니다. 각 로그 레코드에는 Azure 권한 관리에서 해당 요청을 처리한 시간을 나타내는 UTC 타임스탬프가 있습니다.

> [!IMPORTANT]
> Azure 권한 관리 로깅 시스템은 엄격한 순서를 지키기보다는 로그를 빠르게 제공하도록 최적화되어 있습니다. 그러므로 Blob의 순서와 Blob 내의 로그 레코드 순서는 시간순이 아닐 수도 있습니다. Blob 이름이 순차적으로 지정되는 이유는 Blob을 효율적으로 증분 다운로드할 수 있도록 하기 위한 것뿐입니다.
> 
> 아래에는 로그 순서로 인해 발생할 수 있는 두 가지 결과의 예가 나와 있습니다.
> 
> -   blob 000000004의 로그 레코드는 blob 000000003의 로그 레코드와 시간상 겹칠 수 있습니다. 극단적인 예로, blob 000000004의 모든 로그 레코드가 blob 000000003의 모든 로그 레코드보다 먼저 생성되었을 수도 있습니다.
> -   Blob의 두 번째 로그 레코드가 첫 번째 로그 레코드보다 먼저 생성되었지만 저장소에는 반대 순서로 기록되었을 수 있습니다.

Azure 권한 관리 사용 현황 로그를 분석하기 전에 로그를 다운로드한 다음 타임스탬프를 기준으로 로그를 정렬할 수 있는 리포지토리로 가져오는 것이 좋습니다. 로그를 다운로드하는 방법에 대한 자세한 내용은 이 항목의 뒷부분에 나오는 [Azure 권한 관리 사용 현황 로그에 액세스 및 사용 방법](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md#BKMK_AccesAndUseLogs) 섹션을 참조하세요.

이처럼 로그가 반드시 시간순인 것은 아니지만 대부분의 로그는 요청 후 15분 이내에 기록되므로 타임스탬프를 사용하여 원하는 로그를 확인할 때는 확인하려는 시간에 15분을 더한 다음 해당 로그를 다운로드하면 됩니다. 이 전략을 사용하면 원하는 거의 모든 로그를 확인할 수 있습니다.

또 한 가지 기억해야 할 사항은, 각 로그 레코드의 타임스탬프는 요청을 처리한 Azure 권한 관리 서비스의 현지 시간이라는 점입니다. Azure 권한 관리가 여러 데이터 센터의 여러 서버에서 실행되므로 로그가 타임스탬프순으로 정렬되었어도 순서가 올바르지 않은 것처럼 보일 수 있습니다. 그러나 시간 차이는 크지 않으며 보통 1분 이내입니다. 대부분의 경우에는 이러한 시간 차이로 인해 로그 분석 시 문제가 발생하지 않습니다.

### Blob 형식
각 Blob은 W3C 확장 로그 형식으로 되어 있으며 다음의 두 줄로 시작됩니다.

**#Software: RMS**

**#Version: 1.1**

첫 번째 줄은 이러한 로그가 Azure 권한 관리 로그임을 나타냅니다. 두 번째 줄은 Blob의 나머지 부분이 버전 1.1 사양을 따름을 나타냅니다. 이러한 로그를 구문 분석하는 응용 프로그램에서 이 두 줄을 먼저 확인한 후에 Blob의 나머지 부분 구문 분석을 계속하도록 하는 것이 좋습니다.

세 번째 줄에는 탭으로 구분된 필드 이름 목록이 열거됩니다.

**#Fields: date            time            row-id        request-type           user-id       result          correlation-id          content-id                owner-email           issuer                     template-id             file-name                  date-published      c-info         c-ip**

그 다음의 각 줄이 로그 레코드입니다. 필드의 값은 위 줄과 같은 순서로 되어 있으며 탭으로 구분됩니다. 다음 표를 참조하여 필드를 해석할 수 있습니다.

|필드 이름|W3C 데이터 형식|설명|예제 값|
|---------|--------------|------|--------|
|date|날짜|요청이 처리된 UTC 날짜입니다.<br /><br />원본은 요청을 처리한 서버의 로컬 시계입니다.|2013-06-25|
|time|시간|요청이 처리된 UTC 시간(24시간 형식)입니다.<br /><br />원본은 요청을 처리한 서버의 로컬 시계입니다.|21:59:28|
|row-id|텍스트|이 로그 레코드의 고유 GUID입니다.<br /><br />로그를 집계하거나 다른 형식으로 복사할 때 이 값을 활용하면 유용합니다.|1c3fe7a9-d9e0-4654-97b7-14fafa72ea63|
|request-type|Name|요청한 RMS API의 이름입니다.|AcquireLicense|
|user-id|문자열|요청을 한 사용자입니다.<br /><br />값은 작은따옴표로 묶입니다. 일부 익명 요청 유형의 경우 값은 "입니다.|‘joe@contoso.com’|
|result|문자열|요청이 정상적으로 처리된 경우 'Success'입니다.<br /><br />요청이 실패한 경우에는 작은따옴표로 묶인 오류 유형이 표시됩니다.|‘Success’|
|correlation-id|텍스트|지정된 요청에 대해 RMS 클라이언트 로그와 서버 로그 간에 공통적으로 사용되는 GUID입니다.<br /><br />이 값은 클라이언트 문제 해결 시 유용할 수 있습니다.|cab52088-8925-4371-be34-4b71a3112356|
|content-id|텍스트|문서 등의 보호된 콘텐츠를 식별하는 중괄호로 묶인 GUID입니다.<br /><br />request-type이 AcquireLicense인 경우에만 이 필드에 값이 포함되며 기타 모든 요청 유형의 경우 이 필드는 비어 있습니다.|{bb4af47b-cfed-4719-831d-71b98191a4f2}|
|owner-email|문자열|문서 소유자의 전자 메일 주소입니다.|alice@contoso.com|
|issuer|문자열|문서 발급자의 전자 메일 주소입니다.|alice@contoso.com (or) FederatedEmail.4c1f4d-93bf-00a95fa1e042@contoso.onmicrosoft.com'|
|Template-id|문자열|문서를 보호하는 데 사용된 템플릿의 ID입니다.|{6d9371a6-4e2d-4e97-9a38-202233fed26e}|
|File-name|문자열|보호된 문서의 파일 이름입니다.|TopSecretDocument.docx|
|Date-published|날짜|문서를 보호한 날짜입니다.|2015-10-15T21:37:00|
|c-info|문자열|요청을 수행하는 클라이언트 플랫폼에 대한 정보입니다.<br /><br />구체적인 문자열은 운영 체제, 브라우저 등의 응용 프로그램에 따라 다릅니다.|'MSIPC;version=1.0.623.47;AppName=WINWORD.EXE;AppVersion=15.0.4753.1000;AppArch=x86;OSName=Windows;OSVersion=6.1.7601;OSArch=amd64'|
|c-ip|주소|요청을 수행하는 클라이언트의 IP 주소입니다.|64.51.202.144|

#### use-id 필드에 대한 예외
user-id 필드는 보통 요청을 수행한 사용자를 나타내지만 해당 값이 실제 사용자에 매핑되지 않는 두 가지 예외가 있습니다.

-   **'microsoftrmsonline@&lt;YourTenantID&gt;.rms.&lt;region&gt;.aadrm.com'** 값

    이 값은 Exchange Online 또는 Sharepoint Online과 같은 Office 365 서비스에서 요청을 수행함을 나타냅니다. 위 문자열에서 *&lt;YourTenantID&gt;*는 테넌트의 GUID이고 *&lt;region&gt;*은 테넌트가 등록된 지역입니다. 예를 들어 **na**는 북미, **eu**는 유럽, **ap**는 아시아를 나타냅니다.

-   RMS 커넥터를 사용하는 경우

    이 커넥터로부터의 요청은 RMS 커넥터 설치 시 RMS에서 자동으로 생성하는 서비스 사용자 이름으로 기록됩니다.

#### 일반적인 요청 형식
Azure 권한 관리에는 다양한 요청 형식이 있습니다. 아래 표에는 가장 일반적으로 사용되는 몇 가지 요청 형식이 나와 있습니다.

|요청 형식|설명|
|---------|------|
|AcquireLicense|클라이언트가 Windows 기반 컴퓨터에서 RMS로 보호된 콘텐츠용 라이선스를 요청합니다.|
|AcquirePreLicense|사용자 대신 클라이언트가 RMS로 보호된 콘텐츠에 대한 라이선스를 요청합니다.|
|AcquireTemplates|템플릿 ID에 따라 템플릿을 얻도록 호출했습니다.|
|AcquireTemplateInformation|서비스에서 템플릿 ID를 가져오도록 호출했습니다.|
|AddTemplate|Azure 클래식 포털에서 템플릿을 추가하도록 호출합니다.|
|BECreateEndUserLicenseV1|모바일 장치에서 최종 사용자 라이선스를 만들도록 호출합니다.|
|BEGetAllTemplatesV1|모바일 장치(백 엔드)에서 모든 템플릿을 가져오도록 호출합니다.|
|Certify|클라이언트가 보호할 콘텐츠를 인증합니다.|
|Decrypt|클라이언트가 RMS로 보호된 콘텐츠의 암호 해독을 시도합니다.|
|DeleteTemplateById|Azure 클래식 포털에서 템플릿 ID별로 템플릿을 삭제하도록 호출합니다.|
|ExportTemplateById|Azure 클래식 포털에서 템플릿 ID에 따라 템플릿을 내보내도록 호출합니다.|
|FECreateEndUserLicenseV1|AcquireLicense 요청과 비슷하지만 모바일 장치에서 수행하는 요청입니다.|
|FECreatePublishingLicenseV1|Certify 및 GetClientLicensorCert가 결합된 형태의 요청으로, 모바일 클라이언트에서 사용됩니다.|
|FEGetAllTemplates|모바일 장치(프런트 엔드)에서 템플릿을 가져오도록 호출합니다.|
|GetAllTemplates|Azure 클래식 포털에서 모든 템플릿을 가져오도록 호출합니다.|
|GetClientLicensorCert|클라이언트가 Windows 기반 컴퓨터에서 게시 인증서(나중에 콘텐츠를 보호하는 데 사용됨)를 요청합니다.|
|GetConfiguration|Azure PowerShell cmdlet은 Azure RMS 테넌트의 구성을 가져오도록 호출됩니다.|
|GetConnectorAuthorizations|RMS 커넥터에서 클라우드로부터 해당 구성을 가져오도록 호출합니다.|
|GetTenantFunctionalState|Azure 클래식 포털에서 Azure RMS 활성화 여부를 확인합니다.|
|GetTemplateById|Azure 클래식 포털에서 템플릿 ID를 지정하여 템플릿을 가져오도록 호출합니다.|
|ExportTemplateById|Azure 클래식 포털에서 템플릿 ID를 지정하여 템플릿을 내보내도록 호출합니다.|
|FindServiceLocationsForUser|Certify 또는 AcquireLicense를 호출하는 데 사용되는 Url을 쿼리하도록 호출합니다.|
|ImportTemplate|Azure 클래식 포털에서 템플릿을 가져오도록 호출합니다.|
|ServerCertify|RMS 사용 클라이언트(예: SharePoint)에서 서버를 인증하도록 호출합니다.|
|SetUsageLogFeatureState|사용 현황 로깅을 사용하도록 호출합니다.|
|SetUsageLogStorageAccount|Azure RMS 로그의 위치를 지정하도록 호출합니다.|
|SignDigest|서명 용도로 키를 사용할 때 호출합니다. 대개 AcquireLicence(또는 FECreateEndUserLicenseV1), Certify 및 GetClientLicensorCert(또는 FECreatePublishingLicenseV1)당 한 번씩만 호출합니다.|
|UpdateTemplate|Azure 클래식 포털에서 기존 템플릿을 업데이트하도록 호출합니다.|

## <a name="BKMK_PowerShell"></a>Windows PowerShell 참조
다음 Windows PowerShell cmdlet을 사용하여 Azure 권한 관리 사용 현황 로깅을 구성 및 사용할 수 있습니다.

-   [Disable-AadrmUsageLogFeature](https://msdn.microsoft.com/library/azure/dn629404.aspx)

-   [Enable-AadrmUsageLogFeature](https://msdn.microsoft.com/library/azure/dn629421.aspx)

-   [Get-AadrmUsageLog](https://msdn.microsoft.com/library/azure/dn629401.aspx)

-   [Get-AadrmUsageLogFeature](https://msdn.microsoft.com/library/azure/dn629425.aspx)

-   [Get-AadrmUsageLogLastCounterValue](https://msdn.microsoft.com/library/azure/dn629423.aspx)

-   [Get-AadrmUsageLogStorageAccount](https://msdn.microsoft.com/library/azure/dn629419.aspx)

-   [Set-AadrmUsageLogStorageAccount](https://msdn.microsoft.com/library/azure/dn629426.aspx)

Azure 권한 관리용 Windows PowerShell 사용에 대한 자세한 내용은 [Windows PowerShell을 사용하여 Azure 권한 관리 관리](../Topic/Administering_Azure_Rights_Management_by_Using_Windows_PowerShell.md)를 참조하세요.

## 참고 항목
[Azure Rights Management 사용](../Topic/Using_Azure_Rights_Management.md)

