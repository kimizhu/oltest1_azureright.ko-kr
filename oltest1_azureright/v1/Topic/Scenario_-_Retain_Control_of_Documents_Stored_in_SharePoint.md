---
description: na
keywords: na
title: Scenario - Retain Control of Documents Stored in SharePoint
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 1b6244c7-5ab9-4881-bc8f-6fa960390d89
---
# 시나리오 - SharePoint에 저장된 문서에 대한 제어 유지
이 섹션에는 관리자 지침이 포함되어 있으며 사용자 지침에 대한 안내도 포함되어 있습니다.사용자에게 이 구성에 대해 알리기 전에 관리자용 지침을 완료해야 합니다.

## 관리자용 지침
![](../Image/AzRMS_AdminBanner.png)

보호된 라이브러리를 사용하여 SharePoint에 저장된 Office 문서를 계속 제어하려면 이러한 지침을 사용합니다.예를 들어 사용자의 우발적이거나 의도적인 누출로부터 문서가 자동으로 보호되며, 문서가 다운로드되거나 동기화된 후에도 콘텐츠에 대한 액세스를 차단할 수 있습니다.보호하려는 파일은 설계 문서 또는 계획에 대한 공동 작업에 사용하거나 결과물로 제공하기 위한 것일 수 있습니다.SharePoint용 보호된 라이브러리를 구성할 때 해당 라이브러리에 저장된 Office 파일은 Azure 권한 관리에 의해 보호됩니다.

지침을 제공하기에 적합한 상황은 다음과 같습니다.

-   직원들이 Office 문서를 사용하여 공유하고 공동 작업을 수행하는 경우

-   문서에 공개 대상이 아닌 정보가 포함되어 있지만 반드시 내부 전용은 아닌 경우

-   직원들이 관리자가 라이브러리 수준에서 설정하는 사용 권한을 설정하거나 변경할 필요가 없는 경우

## 이 시나리오의 요구 사항
이 시나리오가 작동하려면 다음 사항을 준비해야 합니다.

|Check|요구 사항|추가 정보가 필요한 경우 확인 가능한 위치|
|---------|---------|---------------------------|
|![](../Image/4d269a30-a873-45c5-87de-30ee6558e7b0.gif)|Office 365 또는 Azure Active Directory용 계정과 그룹을 준비했는지 여부|[Azure 권한 관리 준비](https://technet.microsoft.com/library/jj585029.aspx)|
|![](../Image/4d269a30-a873-45c5-87de-30ee6558e7b0.gif)|Azure 권한 관리가 활성화되었는지 여부|[Azure 권한 관리 활성화](https://technet.microsoft.com/library/jj658941.aspx)|
|![](../Image/4d269a30-a873-45c5-87de-30ee6558e7b0.gif)|SharePoint Server를 사용할 경우: RMS 커넥터를 배포하고 SharePoint에 대해 구성|[Azure 권한 관리 커넥터 배포](https://technet.microsoft.com/library/dn375964.aspx)|
|![](../Image/4d269a30-a873-45c5-87de-30ee6558e7b0.gif)|IRM 및 보호된 라이브러리에 대해 SharePoint 구성|[SharePoint 관리 센터의 IRM(정보 권한 관리) 설정](https://support.office.com/en-us/article/Set-up-Information-Rights-Management-IRM-in-SharePoint-admin-center-239ce6eb-4e81-42db-bf86-a01362fed65c)<br /><br />[목록이나 라이브러리에 정보 권한 관리 적용](http://office.microsoft.com/sharepoint-help/apply-information-rights-management-to-a-list-or-library-HA102891460.aspx)|

## 사용자 지침
보호된 라이브러리에는 사용자의 특별한 작업이 필요하지 않기 때문에 이 시나리오의 경우 사용자에게 제공할 특정한 지침이 없습니다.SharePoint 관리자가 사이트에 대해 설정하는 사용 권한에 따라 문서가 자동으로 보호됩니다.그러나 어떤 라이브러리가 보호되고 이로 인해 문서 사용이 어떻게 제한될 수 있는지를 사용자와 지원 센터에 알려야 할 수도 있습니다.예를 들어 현재의 제한 때문에 모바일 장치에서 해당 문서를 볼 수 있지만 편집할 수는 없습니다.

다음 예제는 Azure RMS를 사용하도록 SharePoint 라이브러리를 구성한 후 관련 부서나 팀에 표준 메일 통지로 전송될 수 있습니다.

### 예제 사용자 문서
![](../Image/AzRMS_ExampleBanner.png)

##### IT 알림: 판매 예측 및 보고서 사이트에 대한 변경 사항

-   SharePoint 사이트인 **판매 예측 및 보고서**가 이제 안전한 공동 작업에 사용할 수 있도록 구성되었습니다.지금부터 이 사이트에 저장된 스프레드시트와 Word 문서를 직접 편집해야 합니다. 예를 들어 나중에 편집하기 위해 다른 위치에 저장하거나 다른 사람에게 메일로 보낼 수 없습니다.모바일 장치로 해당 문서를 볼 수 있지만 편집하려면 Windows 컴퓨터를 사용해야 합니다.

**도움이 필요하십니까?**

-   지원 센터(helpdesk@vanarsdelltd.com)에 문의하세요.

