---
description: na
keywords: na
title: Preparing for Azure Rights Management
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: afbca2d6-32a7-4bda-8aaf-9f93f5da5abc
---
# Azure 권한 관리 준비
클라우드 구독을 등록하고 조직에 [!INCLUDE[o365_1](../Token/o365_1_md.md)] 또는 Azure Active Directory용 계정을 설정하고 나면 [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] 서비스를 사용할 준비가 된 것입니다.

그러나 이렇게 하기 전에 먼저 다음이 설정되어 있는지 확인하세요.

-   수동으로 만들거나 AD DS(Active Directory 도메인 서비스)에서 자동으로 만들어져 동기화된 사용자 계정 및 그룹이 클라우드에 있습니다.

    온-프레미스 계정 및 그룹을 동기화할 때 모든 특성을 동기화할 필요는 없습니다. Azure RMS에 대해 동기화해야 하는 특성 목록은 Azure Active Directory 설명서에서 [Azure RMS 섹션](https://azure.microsoft.com/documentation/articles/active-directory-aadconnectsync-attributes-synchronized/)을 참조하세요. 쉽게 배포하기 위해 [Azure AD Connect](http://azure.microsoft.com/documentation/articles/active-directory-aadconnect/)를 사용하여 온-프레미스 디렉터리와 Azure Active Directory를 연결하는 것이 좋습니다. 하지만 동일한 결과를 달성하는 모든 디렉터리 동기화 방법을 사용할 수 있습니다.

-   권한 관리에 사용할 메일 사용 가능 그룹이 클라우드에 있습니다. 그룹은 기본 제공될 수도 있고, 권한 관리를 이용할 사용자가 포함된 그룹을 수동으로 만들 수도 있습니다.

    Exchange Online이 있는 경우 Exchange 관리 센터를 사용하여 메일 사용 가능 그룹을 만들고 사용할 수 있습니다. AD DS에서 Azure AD로 동기화하는 경우 보안 그룹 또는 배포 그룹 중 하나인 메일 사용 가능 그룹을 만들고 사용할 수 있습니다.

## 권한 관리 사용
[!INCLUDE[o365_2](../Token/o365_2_md.md)] 또는 Azure AD 계정을 등록할 때 기본적으로 [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)]는 사용하지 않도록 설정되어 있습니다. 조직에 [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)]를 사용하려면 서비스를 활성화해야 합니다. 자세한 내용은 [Azure 권한 관리 활성화](../Topic/Activating_Azure_Rights_Management.md)를 참조하세요.

## 참고 항목
[Azure Rights Management 구성](../Topic/Configuring_Azure_Rights_Management.md)

