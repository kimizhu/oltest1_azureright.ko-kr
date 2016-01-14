---
description: na
keywords: na
title: Administering Azure Rights Management by Using Windows PowerShell
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: a890e04a-4b70-41b5-8d5f-3c210a669faa
---
# Windows PowerShell을 사용하여 Azure 권한 관리 관리
[!INCLUDE[o365_2](../Token/o365_2_md.md)] 관리 센터 또는 Azure 클래식 포털을 사용하여 Microsoft [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)](Azure RMS)를 활성화할 수도 있지만 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)](AADRM)용 Windows PowerShell 모듈을 사용하여 활성화를 수행할 수도 있습니다.

[!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)]를 활성화하고 나면 서비스를 추가로 관리할 필요가 없을 수도 있습니다. 그러나 일부 고급 구성 시나리오에서는 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]용 Windows PowerShell 모듈을 사용해야 할 수 있습니다. 아래 표에는 Windows PowerShell을 사용하는 몇 가지 고급 구성 시나리오가 나와 있습니다. 사용 가능한 cmdlet의 전체 목록과 각 cmdlet에 대한 자세한 내용은 [Azure 권한 관리 cmdlet](http://msdn.microsoft.com/library/azure/dn629398.aspx)을 참조하세요.

> [!NOTE]
> [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)]용 Windows PowerShell 모듈을 설치해야 하는 경우 [Azure 권한 관리용 Windows PowerShell 설치](../Topic/Installing_Windows_PowerShell_for_Azure_Rights_Management.md)를 참조하세요.

또한 보완 Windows PowerShell 모듈인 **RMSProtection**이 있으며 Azure RMS 및 AD RMS를 모두 지원합니다. 이 모듈은 여러 파일에서 보호를 보호하고 제거하므로 예를 들어 폴더의 모든 파일을 대량-보호할 수 있습니다. 자세한 내용은 [슈퍼 사용자에 대한 스크립팅 옵션](../Topic/Configuring_Super_Users_for_Azure_Rights_Management_and_Discovery_Services_or_Data_Recovery.md#BKMK_RMSProtectionModule) 항목의 [Azure 권한 관리 및 검색 서비스 또는 데이터 검색을 위한 슈퍼 사용자 구성](../Topic/Configuring_Super_Users_for_Azure_Rights_Management_and_Discovery_Services_or_Data_Recovery.md) 섹션을 참조하세요.

|수행할 작업|사용할 cmdlet|
|----------|--------------|
|온-프레미스 Rights Management(AD RMS 또는 Windows RMS)에서 [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)]로 마이그레이션|[Import-AadrmTpd](http://msdn.microsoft.com/library/azure/dn857523.aspx)|
|조직의 [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] 서비스에 연결/서비스 연결 끊기|[Connect-AadrmService](http://msdn.microsoft.com/library/azure/dn629415.aspx)<br /><br />[Disconnect-AadrmService](http://msdn.microsoft.com/library/azure/dn629416.aspx)|
|직접 테넌트 키 생성/관리 - BYOK(Bring Your Own Key) 시나리오|[Add-AadrmKey](http://msdn.microsoft.com/library/azure/dn629418.aspx)<br /><br />[Get-AadrmKeys](http://msdn.microsoft.com/library/azure/dn629420.aspx)|
|조직의 [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] 서비스 활성화/비활성화|[Enable-Aadrm](http://msdn.microsoft.com/library/azure/dn629412.aspx)<br /><br />[Disable-Aadrm](http://msdn.microsoft.com/library/azure/dn629422.aspx)|
|Azure Rights Management에 대한 사이트를 추적하는 문서를 비활성화 또는 활성화합니다.|[Disable-AadrmDocumentTrackingFeature](https://msdn.microsoft.com/library/azure/mt548471.aspx)<br /><br />[Enable-AadrmDocumentTrackingFeature](https://msdn.microsoft.com/library/azure/mt548469.aspx)<br /><br />[Get-AadrmDocumentTrackingFeature](https://msdn.microsoft.com/library/azure/mt548470.aspx)|
|Azure Rights Management의 단계적 배포를 위해 온보딩 컨트롤을 구성합니다.|[Get-AadrmOnboardingControlPolicy](http://msdn.microsoft.com/library/azure/dn857522.aspx)<br /><br />[Set-AadrmOnboardingControlPolicy](http://msdn.microsoft.com/library/azure/dn857521.aspx)|
|조직의 권한 정책 템플릿 만들기/관리|[Add-AadrmTemplate](http://msdn.microsoft.com/library/azure/dn727075.aspx)<br /><br />[Export-AadrmTemplate](http://msdn.microsoft.com/library/azure/dn727078.aspx)<br /><br />[Get-AadrmTemplate](http://msdn.microsoft.com/library/azure/dn727079.aspx)<br /><br />[Get-AadrmTemplateProperty](http://msdn.microsoft.com/library/azure/dn727081.aspx)<br /><br />[Import-AadrmTemplate](http://msdn.microsoft.com/library/azure/dn727077.aspx)<br /><br />[New-AadrmRightsDefinition](http://msdn.microsoft.com/library/azure/dn727080.aspx)<br /><br />[Remove-AadrmTemplate](http://msdn.microsoft.com/library/azure/dn727082.aspx)<br /><br />[Set-AadrmTemplateProperty](http://msdn.microsoft.com/library/azure/dn727076.aspx)|
|조직에서 보호하는 콘텐츠 최대 일 수를 구성하면 인터넷 연결 없이 액세스될 수 있습니다.(사용 라이선스 유효 기간)|[Get-AadrmMaxUseLicenseValidityTime](https://msdn.microsoft.com/library/azure/dn932062.aspx)<br /><br />[Set-AadrmMaxUseLicenseValidityTime](https://msdn.microsoft.com/library/azure/dn932063.aspx)|
|조직의 [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] 슈퍼 사용자 기능 관리|[Enable-AadrmSuperUserFeature](http://msdn.microsoft.com/library/azure/dn629400.aspx)<br /><br />[Disable-AadrmSuperUserFeature](http://msdn.microsoft.com/library/azure/dn629428.aspx)<br /><br />[Add-AadrmSuperUser](http://msdn.microsoft.com/library/azure/dn629411.aspx)<br /><br />[Get-AadrmSuperUser](http://msdn.microsoft.com/library/azure/dn629408.aspx)<br /><br />[Remove-AadrmSuperUser](http://msdn.microsoft.com/library/azure/dn629405.aspx)|
|조직의 [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] 서비스 관리 권한이 있는 사용자 및 그룹 관리|[Add-AadrmRoleBasedAdministrator](http://msdn.microsoft.com/library/azure/dn629417.aspx)<br /><br />[Get-AadrmRoleBasedAdministrator](http://msdn.microsoft.com/library/azure/dn629407.aspx)<br /><br />[Remove-AadrmRoleBasedAdministrator](http://msdn.microsoft.com/library/azure/dn629424.aspx)|
|조직의 [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] 관리 작업 로그 가져오기|[Get-AadrmAdminLog](http://msdn.microsoft.com/library/azure/dn629430.aspx)|
|[!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)]의 사용 현황 로깅 기록 및 분석|[Enable-AadrmUsageLogFeature](http://msdn.microsoft.com/library/azure/dn629421.aspx)<br /><br />[Get-AadrmUsageLog](http://msdn.microsoft.com/library/azure/dn629401.aspx)<br /><br />[Get-AadrmUsageLogFeature](http://msdn.microsoft.com/library/azure/dn629425.aspx)<br /><br />[Get-AadrmUsageLogLastCounterValue](http://msdn.microsoft.com/library/azure/dn629423.aspx)<br /><br />[Get-AadrmUsageLogStorageAccount](http://msdn.microsoft.com/library/azure/dn629419.aspx)<br /><br />[Set-AadrmUsageLogStorageAccount](http://msdn.microsoft.com/library/azure/dn629426.aspx)<br /><br />[Disable-AadrmUsageLogFeature](http://msdn.microsoft.com/library/azure/dn629404.aspx)|
|조직의 현재 [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] 서비스 구성 표시|[Get-AadrmConfiguration](http://msdn.microsoft.com/library/azure/dn629410.aspx)|
|[!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]에서 온-프레미스 AD RMS 배포로 조직 마이그레이션|[Set-AadrmMigrationUrl](http://msdn.microsoft.com/library/azure/dn629429.aspx)<br /><br />[Get-AadrmMigrationUrl](http://msdn.microsoft.com/library/azure/dn629403.aspx)|

## 참고 항목
[Azure  권한 관리](../Topic/Azure_Rights_Management.md)

