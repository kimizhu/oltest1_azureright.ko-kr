---
description: na
keywords: na
title: Comparing Azure Rights Management and AD RMS
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 8123bd62-1814-4d79-b306-e20c1a00e264
---
# Azure 권한 관리와 AD RMS 비교
Active Directory Rights Management Services(AD RMS)를 잘 알고 있거나 이전에 배포한 경우 기능 및 요구 사항 측면에서 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)](AD RMS)이 어떻게 다른지 궁금할 수도 있습니다. 아래 테이블에서 Azure RMS 및 AD RMS의 기능과 이점을 비교한 내용을 확인할 수 있습니다. 보안 관련 비교 사항에 대한 문의 사항이 있으면 이 항목의 [서명 및 암호화를 위한 암호화 컨트롤](../Topic/Comparing_Azure_Rights_Management_and_AD_RMS.md#BKMK_CryptographicControls) 섹션을 참조하세요.

> [!NOTE]
> 보다 간편한 비교를 위해 이 표에 나와 있는 일부 정보는 [Azure 권한 관리 요구 사항](../Topic/Requirements_for_Azure_Rights_Management.md)의 정보와 중복됩니다.[!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]의 보다 구체적인 지원 및 버전 정보는 해당 항목을 참조하세요.

|[!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] (Azure RMS)|AD RMS(Active Directory Rights Management Services)|
|-----------------------------------------------------------------------------------------|-------------------------------------------------------|
|Exchange Online, SharePoint Online 등의 Microsoft Online 서비스와 Office 365의 IRM(정보 권한 관리) 기능을 지원합니다.<br /><br />Exchange Server, SharePoint Server 등의 온-프레미스 Microsoft 서버 제품과 Windows Server 및 FCI(파일 분류 인프라)를 실행하는 파일 서버도 지원합니다.|Exchange Server, SharePoint Server 등의 온-프레미스 Microsoft 서버 제품과 Windows Server 및 FCI(파일 분류 인프라)를 실행하는 파일 서버를 지원합니다.|
|조직의 사용자와 조직 간의 암시적 트러스트를 사용하도록 설정합니다. 즉, 같은 조직 내의 사용자 또는 여러 조직의 사용자(사용자가 [!INCLUDE[o365_1](../Token/o365_1_md.md)] 또는 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]를 사용하거나 개인용 RMS에 등록한 경우) 간에 보호된 콘텐츠를 공유할 수 있습니다.|AD FS(Active Directory Federation Services)를 사용하여 만드는 페더레이션 트러스트 또는 TUD(트러스트된 사용자 도메인)를 통해 두 조직 간의 직접 지점 간 관계에서 트러스트를 명시적으로 정의해야 합니다.|
|조직의 콘텐츠 액세스를 제한하는 기본 권한 정책 템플릿 두 개가 제공됩니다. 그 중 하나는 보호된 콘텐츠에 대한 읽기 전용 보기 권한을 제공하고 다른 하나는 보호된 콘텐츠에 대한 쓰기 또는 수정 권한을 제공합니다.<br /><br />또한 하위 집합의 사용자에게만 표시되는 부서별 템플릿을 포함한 사용자 지정 템플릿을 만들 수 있습니다. 자세한 내용은 [Azure 권한 관리용 사용자 지정 템플릿 구성](../Topic/Configuring_Custom_Templates_for_Azure_Rights_Management.md)를 참조하세요.<br /><br />템플릿의 권한만으로는 부족한 경우 사용자가 원하는 권한 집합을 정의할 수도 있습니다.|기본 권한 정책 템플릿은 없습니다. 이러한 템플릿을 만든 후 배포해야 합니다. 자세한 내용은 [AD RMS 정책 템플릿 고려 사항](http://go.microsoft.com/fwlink/?LinkId=154765)을 참조하세요.<br /><br />템플릿의 권한만으로는 부족한 경우 사용자가 원하는 권한 집합을 정의할 수도 있습니다.|
|지원되는 최소 버전의 Microsoft Office는 Office 2010이며, 여기에는 [RMS 공유 응용 프로그램](http://technet.microsoft.com/library/dn339006.aspx)이 필요합니다.<br /><br />Microsoft Office for Mac:<br /><br />-   Microsoft Office for Mac 2016: 지원 여부<br />-   Microsoft Office for Mac 2011: 지원되지 않음|지원되는 최소 Microsoft Office 버전은 Office 2007입니다.<br /><br />Microsoft Office for Mac:<br /><br />-   Microsoft Office for Mac 2016: 지원 여부<br />-   Microsoft Office for Mac 2011: 지원 여부|
|Windows, Mac 컴퓨터 및 모바일 장치용 [RMS 공유 응용 프로그램](https://technet.microsoft.com/library/dn919648%28v=ws.10%29.aspx)이 지원됩니다.<br /><br />또한 RMS 공유 응용 프로그램은 다음을 지원합니다.<br /><br />-   다른 조직의 사용자와 공유합니다.<br />-   전자 메일 알림은 누군가가 보호된 첨부 파일을 열려고 할 때 보낸 사람에게 알려줍니다.<br />-   사용자에 대한 사이트를 추적하는 문서는 해지하는 기능을 포함합니다.|Windows, Mac 컴퓨터 및 모바일 장치용 [RMS 공유 응용 프로그램](https://technet.microsoft.com/library/dn919648%28v=ws.10%29.aspx)이 지원됩니다. 그러나 공유는 다른 조직, 전자 메일 알림 또는 사이트를 추적하는 문서 및 문서를 해지하려는 사용자를 위한 기능을 사람들과 공유하도록 지원하지 않습니다.|
|[RMS 공유 응용 프로그램을 사용하는 경우 네이티브 또는 일반 보호](https://technet.microsoft.com/library/dn339003%28v=ws.10%29.aspx)를 사용하여 모든 파일 형식을 보호할 수 있습니다.<br /><br />다른 응용 프로그램의 경우 [클라이언트 기능 테이블](https://technet.microsoft.com/library/dn655136.aspx)을 확인합니다.|[RMS 공유 응용 프로그램을 사용하는 경우 네이티브 또는 일반 보호](https://technet.microsoft.com/library/dn339003%28v=ws.10%29.aspx)를 사용하여 모든 파일 형식을 보호할 수 있습니다.<br /><br />다른 응용 프로그램의 경우 [클라이언트 기능 테이블](https://technet.microsoft.com/library/dn655136.aspx)을 확인합니다.|
|지원되는 최소 Windows 클라이언트 버전은 Windows 7입니다.|지원되는 최소 Windows 클라이언트 버전은 Windows Vista 서비스 팩 2입니다.|
|Windows Phone, Android, iOS, Windows RT 모바일 장치가 지원됩니다.<br /><br />Exchange ActiveSync IRM을 사용한 메일 지원도 이 프로토콜을 지원하는 모든 모바일 장치 플랫폼에서 지원됩니다.|모바일 장치 지원에는 Windows Phone, Android, iOS 및 Windows RT가 포함되며, [Active Directory Rights Management Services 모바일 장치 확장](http://technet.microsoft.com/library/a69ead9d-7dd3-4b38-9830-4728e9757341)이 필요합니다.<br /><br />이 프로토콜을 지원하는 모든 모바일 장치 플랫폼에서 Exchange ActiveSync IRM을 사용하여 전자 메일을 지원할 수 있습니다.|
|컴퓨터와 모바일 장치용 Multi-Factor Authentication(MFA)을 지원합니다.<br /><br />자세한 내용은 [Multi-Factor Authentication(MFA) 및 Azure RMS](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_MFA) 항목의 [Azure 권한 관리 요구 사항](../Topic/Requirements_for_Azure_Rights_Management.md) 섹션을 참조하세요.|IIS가 인증서를 요청하도록 구성된 경우 스마트 카드 인증을 지원합니다.|
|추가 구성 없이도 암호화 모드 2가 지원되므로 키 길이 및 암호화 알고리즘에 대해 보다 강력한 보안 기능이 제공됩니다.<br /><br />자세한 내용은 이 항목의 [서명 및 암호화를 위한 암호화 컨트롤](../Topic/Comparing_Azure_Rights_Management_and_AD_RMS.md#BKMK_CryptographicControls) 섹션 및 [AD RMS 암호화 모드](http://go.microsoft.com/fwlink/?LinkId=266659)를 참조하세요.|기본적으로 암호화 모드 1을 지원하며, 보안을 강화하기 위해 암호화 모드 2를 지원하려면 추가 구성을 수행해야 합니다.<br /><br />자세한 내용은 이 항목 뒷부분의 [서명 및 암호화를 위한 암호화 컨트롤](../Topic/Comparing_Azure_Rights_Management_and_AD_RMS.md#BKMK_CryptographicControls) 섹션과 [AD RMS 암호화 모드](http://go.microsoft.com/fwlink/?LinkId=266659)를 참조하세요.|
|AD RMS로부터의 마이그레이션을 지원하고 필요한 경우 AD RMS로의 마이그레이션 지원:<br /><br />-   [AD RMS에서 Azure 권한 관리로 마이그레이션](../Topic/Migrating_from_AD_RMS_to_Azure_Rights_Management.md)<br />-   [Azure 권한 관리 해제 및 비활성화](../Topic/Decommissioning_and_Deactivating_Azure_Rights_Management.md)|Azure RMS로부터/Azure RMS로의 마이그레이션 지원:<br /><br />-   [Azure 권한 관리 해제 및 비활성화](../Topic/Decommissioning_and_Deactivating_Azure_Rights_Management.md)<br />-   [AD RMS에서 Azure 권한 관리로 마이그레이션](../Topic/Migrating_from_AD_RMS_to_Azure_Rights_Management.md)|
|콘텐츠를 보호하려면 RMS 라이선스가 필요합니다. Azure RMS로 보호되는 콘텐츠를 사용하는 데 필요한 RMS 라이선스가 없습니다(다른 조직의 사용자 포함).<br /><br />자세한 내용은 [Azure 권한 관리 요구 사항](../Topic/Requirements_for_Azure_Rights_Management.md)에서 [Azure RMS를 지원하는 클라우드 구독](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_SupportedSubscriptions) 섹션을 참조하세요.|콘텐츠를 보호하고 AD RMS로 보호되는 콘텐츠를 사용하려면 RMS 라이선스가 필요합니다.<br /><br />AD RMS 라이선스에 대한 자세한 내용은 일반 정보의 [CAL(클라이언트 액세스 라이선스) 및 라이선스 관리](https://www.microsoft.com/en-us/Licensing/product-licensing/client-access-license.aspx)를 참조하되, 특정 정보는 Microsoft 파트너 또는 Microsoft 담당자에게 문의하세요.|

## <a name="BKMK_CryptographicControls"></a>서명 및 암호화를 위한 암호화 컨트롤
[!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]는 모든 공개 키 암호화에는 RSA 2048을, 서명 작업에는 SHA 256을 항상 사용합니다. 반면 AD RMS는 RSA 1024 및 RSA 2048과 서명 작업을 위한 SHA 1 또는 SHA 256을 지원합니다.

[!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] 및 AD RMS는 모두 대칭 암호화에 AES 128을 사용합니다.

Microsoft에서 테넌트 키를 만들고 관리하거나(기본값) 사용자가 테넌트 키를 직접 관리하는 경우(BYOK 방식) [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]는 FIPS 140-2를 준수합니다. 테넌트 키 관리에 대한 자세한 내용은 [Azure 권한 관리 테넌트 키 계획 및 구현](../Topic/Planning_and_Implementing_Your_Azure_Rights_Management_Tenant_Key.md)을 참조하세요.

## 참고 항목
[Azure Rights Management 시작하기](../Topic/Getting_Started_with_Azure_Rights_Management.md)

