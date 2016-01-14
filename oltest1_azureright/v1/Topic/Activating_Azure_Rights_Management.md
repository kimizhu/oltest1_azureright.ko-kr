---
description: na
keywords: na
title: Activating Azure Rights Management
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: f8707e01-b239-4d1a-a1ea-0d1cf9a8d214
---
# Azure 권한 관리 활성화
[!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)](Azure RMS)를 활성화하면 조직에서 이 정보 보호 솔루션을 지원하는 응용 프로그램 및 서비스를 사용하여 중요한 데이터를 보호할 수 있습니다. 또한 관리자는 조직에서 소유한 보호된 파일 및 전자 메일을 관리하고 모니터링할 수 있습니다. Office, SharePoint 및 Exchange 내에서 IRM(정보 권한 관리) 기능을 사용하고 중요한 파일이나 기밀 파일을 보호하려면 먼저 [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)]를 사용하도록 설정해야 합니다.

서비스를 활성화하기 전에 해결되는 비즈니스 문제, 일반적인 몇 가지 사용 사례, 작동 방법 등 Azure 권한 관리에 대해 자세히 알아보려면 [Azure 권한 관리란?](../Topic/What_is_Azure_Rights_Management_.md)을 참조하세요.

> [!IMPORTANT]
> [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)]를 활성화하기 전 조직에 [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] 서비스가 포함된 서비스 계획이 있는지 확인합니다. 서비스 계획이 없는 경우 Azure RMS를 활성화할 수 없습니다.
> 
> 자세한 내용은 [Azure 권한 관리 요구 사항](../Topic/Requirements_for_Azure_Rights_Management.md) 항목의 [Azure RMS를 지원하는 클라우드 구독](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_SupportedSubscriptions) 섹션을 참조하세요.

Azure RMS를 활성화한 후 조직의 모든 사용자는 해당 파일에 정보 보호를 적용할 수 있으며 모든 사용자가 Azure RMS로 보호되는 파일을 열거나 사용할 수 있습니다. 하지만 원하는 경우 단계적 배포용 등록 컨트롤을 사용하여 정보 보호를 적용할 수 있는 사용자를 제한할 수 있습니다. 자세한 내용은 이 항목의 [단계적 배포용 등록 컨트롤 구성](../Topic/Activating_Azure_Rights_Management.md#BKMK_OnboardingControls) 섹션을 참조하세요.

## 권한 관리 활성화
[!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)]를 활성화하려면 다음 절차 중 하나를 사용하세요.

> [!TIP]
> Windows PowerShell cmdlet, [Enable-Aadrm](http://msdn.microsoft.com/library/windowsazure/dn629412.aspx)을 사용하여 [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)]를 활성화할 수도 있습니다.

#### Office 365 관리 센터에서 권한 관리를 활성화하려면

1.  Rights Management가 포함된 Office 365 계획에 등록한 후 Office 365 배포의 관리자인 [회사 또는 학교 계정으로 Office 365에 로그인](https://portal.office.com/)합니다.

2.  Office 365 관리 센터가 자동으로 표시되지 않으면 왼쪽 위에서 앱 시작 관리자를 선택하고 **관리자**를 선택합니다.**관리자** 타일은 Office 365 관리자에게만 나타납니다.

    > [!TIP]
    > 관리 센터 도움말은 [Office 365 관리 센터 정보 - 관리자 도움말](https://support.office.com/article/About-the-Office-365-admin-center-Admin-Help-58537702-d421-4d02-8141-e128e3703547)을 참조하세요.

3.  왼쪽 창에서 **서비스 설정**을 확장합니다.

4.  **Rights Management**를 클릭합니다.

    > [!NOTE]
    > 이 옵션이 표시되지 않는 경우 서비스 계획 또는 제품 버전이 권한 관리를 지원할 수 없기 때문이거나 아직 권한 관리를 지원하도록 업그레이드되지 않았기 때문일 수 있습니다.
    > 
    > [Azure 권한 관리 요구 사항](../Topic/Requirements_for_Azure_Rights_Management.md) 항목의 [Azure RMS를 지원하는 클라우드 구독](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_SupportedSubscriptions) 섹션 정보에서 지원을 확인하세요. 서비스 계획 또는 제품 버전이 지원되지만 권한 관리 옵션이 표시되지 않는 경우 서비스가 아직 업그레이드되지 않았기 때문일 수 있습니다. 이 문제에 대한 도움이 필요한 경우 [askipteam](mailto:askipteam@microsoft.com?subject=I%20cannot%20activate%20RMS)으로 전자 메일 메시지를 보내 주세요.

5.  **Rights Management** 페이지에서 **관리**를 클릭합니다.

6.  **Rights Management** 페이지에서 **활성화**를 클릭합니다.

7.  **Rights Management를 활성화하시겠습니까?**라는 메시지가 나타나면 **활성화**를 클릭합니다.

이제 **Rights Management가 활성화되었음**이 표시되고 비활성화 옵션이 나타납니다.

#### Azure 클래식 포털에서 Rights Management를 활성화하려면

1.  Azure 계정에 등록한 후 [Azure 클래식 포털에 로그인](http://go.microsoft.com/fwlink/p/?LinkID=275081)합니다.

2.  왼쪽 창에서 **ACTIVE DIRECTORY**를 클릭합니다.

3.  **Active Directory** 페이지에서 **Rights Management**를 클릭합니다.

4.  [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)]에 대해 관리할 디렉터리를 선택하고 **활성화**를 클릭한 후 작업을 확인합니다.

    > [!NOTE]
    > 활성화 오류가 표시되는 경우 서비스 계획이나 제품 버전이 [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)]를 지원할 수 없기 때문일 수 있습니다.
    > 
    > [Azure 권한 관리 요구 사항](../Topic/Requirements_for_Azure_Rights_Management.md) 항목의 [Azure RMS를 지원하는 클라우드 구독](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_SupportedSubscriptions) 섹션 정보를 사용하여 RMS 지원을 확인하세요. 이 문제에 대한 도움이 필요한 경우 [askipteam](mailto:askipteam?subject=I%20cannot%20activate%20RMS)으로 전자 메일 메시지를 보내 주세요.

이제 **Rights Management 상태**가 **활성**으로 표시되고 **활성화** 옵션이 **비활성화**로 바뀝니다.

### Azure 클래식 포털의 Rights Management 상태 값 및 설명
Rights Management 서비스가 사용되도록 설정되고 사용할 준비가 되었음을 나타내는 **활성** 상태뿐만 아니라 **비활성**, **사용할 수 없음** 또는 **권한 없음**도 확인할 수 있습니다.

|상태 값|설명|
|--------|------|
|**활성**|[!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)]가 사용할 준비가 되었습니다.|
|**비활성**|[!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)]가 사용되지 않도록 설정되어 있으며 조직에서 파일을 보호하려면 활성화되어야 합니다.|
|**Unavailable**|[!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] 서비스가 중지되었습니다. 나중에 다시 시도하세요.|
|**권한 없음**|[!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] 서비스 상태를 볼 권한이 없습니다. 예를 들어 계정이 잠겼거나 선택한 테넌트에 대한 전역 관리자가 아닙니다.|

## <a name="BKMK_OnboardingControls"></a>단계적 배포용 등록 컨트롤 구성
일부 사용자만 Azure RMS를 사용하여 즉시 파일을 보호할 수 있게 하려면 [Set-AadrmOnboardingControlPolicy](http://msdn.microsoft.com/library/azure/dn857521.aspx) Windows PowerShell 명령을 사용하여 사용자 등록 컨트롤을 구성할 수 있습니다. Azure RMS를 활성화하기 전이나 후에 이 명령을 실행할 수 있습니다.

> [!IMPORTANT]
> 이 명령을 사용하려면 **2.1.0.0** 버전 이상의 [Azure RMS Windows PowerShell 모듈(영문)](http://go.microsoft.com/fwlink/?LinkId=257721)이 있어야 합니다.
> 
> 설치한 버전을 확인하려면 다음을 실행하세요. **(Get-Module aadrm –ListAvailable).Version**

예를 들어 초기에 개체 ID가 fbb99ded-32a0-45f1-b038-38b519009503인 "IT 부서" 그룹의 관리자만 테스트 목적으로 콘텐츠를 보호할 수 있도록 하려면 다음 명령을 사용합니다.

```
Set-AadrmOnboardingControlPolicy – SecurityGroupObjectId fbb99ded-32a0-45f1-b038-38b519009503
```
이 구성 옵션에 대해서는 그룹을 지정해야 하며 개별 사용자를 지정할 수는 없습니다.

또는 Azure RMS를 사용할 수 있는 라이선스가 부여된 사용자만 콘텐츠를 보호할 수 있게 하려면 다음 명령을 사용합니다.

```
Set-AadrmOnboardingControlPolicy -UseRmsUserLicense $true
```
이러한 등록 컨트롤을 사용할 경우 조직의 모든 사용자는 항상 하위 사용자가 보호하는 보호된 콘텐츠를 사용할 수 있지만 클라이언트 응용 프로그램에서 자체적으로 정보 보호를 적용할 수는 없습니다. 예를 들어 Azure RMS가 활성화되면 자동으로 게시된 기본 템플릿 또는 사용자가 구성할 수 있는 사용자 지정 템플릿이 Office 클라이언트에 표시되지 않습니다.  Exchange 등의 서버 쪽 응용 프로그램은 같은 결과를 달성하기 위해 RMS 통합을 위한 자체 사용자별 컨트롤을 구현할 수 있습니다.

## 다음 단계
이제 조직의 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]를 활성화했으므로 [Azure 권한 관리 배포 로드맵](../Topic/Azure_Rights_Management_Deployment_Roadmap.md)에서 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]를 사용자 및 관리자에게 롤아웃하기 전에 수행해야 하는 다른 구성 단계가 있는지 확인합니다. 예를 들어 [사용자 지정 템플릿](http://technet.microsoft.com/library/dn642472.aspx)을 이용하여 사용자가 좀 더 쉽게 파일에 정보 보호를 적용하고, [RMS 커넥터](http://technet.microsoft.com/library/dn375964.aspx)를 설치하여 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]를 사용할 온-프레미스 서버를 연결하며, 모든 장치에서 모든 파일 형식 보호를 지원하는 [Rights Management 공유 응용 프로그램](http://technet.microsoft.com/library/jj585031.aspx)을 배포하도록 할 수 있습니다. Exchange Online, SharePoint Online 등의 Office 서비스의 경우 해당 IRM(정보 권한 관리) 기능을 사용하려면 추가 구성이 필요합니다. 하지만 수행해야 하는 다른 구성 단계가 없는 경우 조직의 성공적인 배포를 지원하기 위한 작업 지침은 [Azure Rights Management 사용](../Topic/Using_Azure_Rights_Management.md)을 참조하세요.

응용 프로그램이 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]와 작동하는 방법에 대한 자세한 내용은 [응용 프로그램이 Azure 권한 관리를 지원하는 방식](../Topic/How_Applications_Support_Azure_Rights_Management.md)을 참조하세요.

## 참고 항목
[Azure Rights Management 구성](../Topic/Configuring_Azure_Rights_Management.md)

