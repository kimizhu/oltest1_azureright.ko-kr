---
description: na
keywords: na
title: Information and Support for Azure Rights Management
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 7cc73d92-27d6-49ff-a8ab-2fae73519b4b
---
# Azure 권한 관리에 대한 정보 및 지원
다음 리소스에서 Microsoft [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)](Azure RMS)에 대한 추가 정보를 확인할 수 있습니다.

|수행 작업|.. 방법|
|---------|---------|
|… 최신 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] 제품 설명서 확인 →|[Azure  권한 관리](../Topic/Azure_Rights_Management.md)의 TechNet 문서 라이브러리 사용|
|… 문서에 대한 의견 제공 또는 문서 관련 질문 →|[askipteam](mailto:%20askipteam@microsoft.com?subject=Documentation%20feedback)에 전자 메일 보내기|
|… Rights Management에 대한 트윗 및 제품 그룹의 문서 업데이트에 대한 공지 사항 수신→|Microsoft Rights Management 팀 책임자인 Dan Plastina 팔로우.[Dan Plastina @TheRMSGuy](https://twitter.com/TheRMSGuy)를 참조하세요.|
|…[!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] 평가판 받기 →|[30일 무료 평가판 등록](https://portal.microsoftonline.com/Signup/MainSignUp15.aspx?&amp;OfferId=A43415D3-404C-4df3-B31B-AAD28118A778&amp;dl=RIGHTSMANAGEMENT&amp;ali=1)|
다음 섹션에서는 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]에 대한 추가 정보를 제공합니다.

-   [문서 라이브러리 검색](../Topic/Information_and_Support_for_Azure_Rights_Management.md#BKMK_SearchTips)

-   [다운로드 가능 문서](../Topic/Information_and_Support_for_Azure_Rights_Management.md#BKMK_Download)

-   [Rights Management 제품 그룹 블로그](../Topic/Information_and_Support_for_Azure_Rights_Management.md#BKMK_ProductGroupBlog)

-   [지원 옵션 및 커뮤니티 리소스](../Topic/Information_and_Support_for_Azure_Rights_Management.md#BKMK_SupportOptions)

## <a name="BKMK_SearchTips"></a>문서 라이브러리 검색
[범위가 지정된 이 검색 쿼리를 사용](http://www.bing.com/search?q=%28"Rights%20Management"%29%20site:technet.microsoft.com/library%20meta:search.MSCategory%28jj619159%29)하면 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]로 범위가 한정된 TechNet 라이브러리의 문서를 찾을 수 있습니다.

AD RMS(Active Directory Rights Management Services) 또는 Windows Rights Management에 대한 결과나 커뮤니티 리소스는 해당 쿼리의 검색 결과에 포함되지 않습니다. URL에서 "Rights Management" 문자열을 원하는 검색 문자열로 바꾸면 검색 결과의 범위를 좁힐 수 있습니다.

### 검색 예
[이 검색 쿼리를 사용](http://www.bing.com/search?q=%28"Rights%20Management"%29%20site:technet.microsoft.com/library%20meta:search.MSCategory%28jj619159%29)하고, 아래 예제를 참조하여 검색을 사용자 지정합니다.

-   단일 검색 문자열: 검색 문자열 **RMS 커넥터**가 포함된 항목을 검색하려면 **“권한 관리”**를 **“RMS 커넥터”**로 바꿉니다.

    ```
    ("RMS connector") site:technet.microsoft.com/library meta:search.MSCategory(jj619159)
    ```

-   검색 문자열 결합: 검색 문자열 **Exchange** 및 **SharePoint**가 포함된 항목을 검색하려면 **AND** 연산자를 사용합니다.

    ```
    ("Exchange") AND ("SharePoint") site:technet.microsoft.com/library meta:search.MSCategory(jj619159)
    ```

-   대체 검색 문자열: 검색 문자열 **Exchange** 또는 **SharePoint**가 포함된 항목을 검색하려면 **OR** 연산자를 사용합니다.

    ```
    ("Exchange" OR "SharePoint") site:technet.microsoft.com/library meta:search.MSCategory(jj619159)
    ```

-   검색 문자열 제외: 검색 문자열 **Exchange**가 포함된 항목을 검색하고 **SharePoint** 관련 항목은 제외하려면 **NOT** 연산자를 사용합니다.

    ```
    ("Exchange)" NOT ("SharePoint") site:technet.microsoft.com/library meta:search.MSCategory(jj619159)
    ```

### 검색 팁
필요한 정보를 쉽게 찾으려면 다음 검색 팁을 활용하세요.

-   공식 설명서를 검색할 때는 커뮤니티 콘텐츠에 표시되는 약어나 비공식 용어가 아닌 UI(사용자 인터페이스)와 TechNet 문서에 표시되는 것과 일치하는 검색 용어를 사용합니다. 예를 들어 "AADRMS" 또는 이 클라우드 서비스의 기타 비공식 약어가 아닌 "Azure 권한 관리"를 검색합니다. "RMS"라는 용어도 많이 표시 및 사용되기는 하지만 전체 이름은 Rights Management Service이므로 공식 설명서를 찾을 때는 RMS 대신 "Rights Management"를 검색합니다.[Azure 권한 관리 용어](../Topic/Terminology_for_Azure_Rights_Management.md)를 통해 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] 관련 공식 용어를 파악할 수 있습니다.

-   TechNet의 페이지에서 Ctrl+F를 누르고 **찾기** 상자에 검색 용어를 입력하는 방식으로 검색할 때는 축소된 섹션의 텍스트가 결과에서 제외됩니다. 축소된 섹션의 텍스트를 검색하려면 페이지를 검색하기 전에 섹션을 확장합니다. 이렇게 하려면 페이지 위쪽의 **모두 확장** 단추를 클릭하거나 축소된 섹션을 두 번 클릭하면 됩니다. 모든 섹션이 확장되면 페이지 검색 시 해당 페이지의 모든 섹션을 검색합니다.

-   가능하면 항상 다운로드한 설명서가 아닌 온라인 TechNet 라이브러리를 사용합니다. 온라인 TechNet 라이브러리에는 최신 정보가 포함되어 있습니다. 다운로드한 문서에는 검색하는 정보가 포함되어 있지 않을 수도 있고 온라인에서 정보가 수정 또는 추가되었을 수도 있습니다.

-   로컬에 저장된 문서를 검색하는 것이 더 쉽고 빠르다면 TechNet에서 여러 항목을 선택하여 로컬에 저장할 수 있습니다. 자세한 내용은 다음 섹션을 참조하세요.

## <a name="BKMK_Download"></a>다운로드 가능 문서
TechNet에서 페이지를 다운로드하여 로컬에 저장할 수 있습니다. 예를 들어 인터넷에 연결할 수 없을 때 랩톱, 태블릿 또는 휴대폰에서 확인할 수 있도록 항목을 PDF 파일로 저장할 수도 있고 해당 항목에 주석을 추가하거나 정보를 인쇄할 수도 있습니다. 이 방법을 사용하면 특정 작업 집합이나 전체 시나리오에 필요한 항목을 그룹화하여 백서나 프로젝트 문서를 효율적으로 만들 수 있습니다.

[!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]만이 아닌 TechNet의 모든 문서 라이브러리에서 이 방법을 사용할 수 있습니다.

#### TechNet에서 문서를 다운로드합니다.

1.  TechNet에 로그인합니다.

2.  로컬에 저장할 페이지 위쪽의 **인쇄** 옆에 있는 **내보내기**를 클릭합니다.

    그러면 표시되는 **여러 페이지 내보내기** 배너를 통해 저장할 페이지를 추가/제거할 수 있습니다.

3.  **페이지 관리**를 클릭하여 페이지를 내보냅니다.

자세한 내용을 확인하려면 배너의 **도움말**을 클릭하세요.

> [!NOTE]
> TechNet의 정보는 자주 업데이트되므로 가능하면 항상 최신 버전을 확인할 수 있도록 온라인 버전을 사용하세요.
> 
> [Microsoft Rights Management(RMS) 팀 블로그 및 문서 태그](http://blogs.technet.com/b/rms/archive/tags/docs/)에서 월간 문서 공지 사항을 통해 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]용으로 이전에 다운로드했던 항목이 현재 개정되었는지와 어떤 사항이 변경되었는지를 확인할 수 있습니다.

## <a name="BKMK_ProductGroupBlog"></a>Rights Management 제품 그룹 블로그
Rights Management 제품 그룹에서는 [Microsoft Rights Management(RMS) 팀 블로그](http://blogs.technet.com/b/rms/)를 통해 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)], AD RMS 및 관련 기술에 대한 기술 정보와 기타 소식을 제공합니다. 이러한 블로그 게시물은 제품 문서와 지원 정보를 보완합니다.

> [!TIP]
> Azure RMS 또는 AD RMS용 응용 프로그램을 개발 중인 경우에는 [AD RMS(Active Directory Rights Management Services) 개발자 코너 블로그](http://blogs.msdn.com/b/rms/)도 확인할 수 있습니다.

## <a name="BKMK_SupportOptions"></a>지원 옵션 및 커뮤니티 리소스
다음 링크에서는 지원 및 문제 해결 옵션과 커뮤니티 리소스에 대한 정보를 제공합니다.

-   [RMS 분석기 도구](http://www.microsoft.com/en-us/download/details.aspx?id=46437)

-   [Yammer: Microsoft Rights Management(RMS)](http://www.yammer.com/AskIPTeam)

-   [포럼: Microsoft RMS(클라우드)](https://social.technet.microsoft.com/Forums/en-US/home?forum=rmscloud)

-   [포럼: 사용자용 RMS(응용 프로그램)](https://social.technet.microsoft.com/Forums/en-US/home?forum=rmsapps)

-   [Microsoft 도움말 및 지원](http://go.microsoft.com/fwlink/?LinkId=243064)

또한 [Microsoft Rights Management 서비스 포털](http://www.microsoft.com/rms)을 방문하여 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]용 기타 지원 리소스를 확인할 수도 있습니다.

## 참고 항목
[Azure Rights Management 시작하기](../Topic/Getting_Started_with_Azure_Rights_Management.md)

