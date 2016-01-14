---
description: na
keywords: na
title: Azure Rights Management
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 965581c8-be3c-43b4-8145-5cefd29c7636
---
# Azure  권한 관리
<?xml version="1.0" encoding="utf-8"?>
<caps:SxS xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
  <caps:SxSTarget locale="ko-KR">
    <developerConceptualDocument xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd" xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <introduction>
        <para>
          <caps:sentence sentenceid="62b83eea4fc0746f132ff6c8d4a52b84" id="tgt1" class="tgtSentence">이 페이지는 Microsoft <token>aad_rightsmanagement_1</token>(Azure RMS)용 기술 설명서 집합을 소개하여 조직의 중요한 정보에 무단 액세스하지 못하도록 보호하고 해당 정보가 사용되는 방법을 제어하도록 합니다.</caps:sentence>
          <caps:sentence sentenceid="23b58def11b45727d3351702515f86af" id="tgt2" class="tgtSentence">
            <token>aad_rightsmanagement_1</token>는 클라우드 서비스이며 다른 Microsoft 클라우드 서비스 및 응용 프로그램(Office 365, Azure Active Directory 등)에 통합되었습니다.</caps:sentence>
          <caps:sentence sentenceid="145e719c453fbadadee79768f74667aa" id="tgt3" class="tgtSentence"> 하지만 온-프레미스 응용 프로그램 및 서비스와 함께 사용할 수도 있습니다.</caps:sentence>
        </para>
        <para>
          <caps:sentence sentenceid="c6fa2923fc013e88430215867fa3b41f" id="tgt4" class="tgtSentence">
            <token>aad_rightsmanagement_2</token>은 암호화, ID 및 권한 부여 정책을 사용하여 파일 및 전자 메일을 보호하도록 합니다.</caps:sentence>
          <caps:sentence sentenceid="6cee999ea54670dc3aaf3fa7bfdf7566" id="tgt5" class="tgtSentence"> NTFS 권한 등의 표준 액세스 제어에 비해 <token>aad_rightsmanagement_2</token>를 사용하여 적용하는 보호 기능은 조직, 네트워크, 파일 서버, 응용 프로그램 내/외의 위치에 관계없이 파일과 전자 메일에 계속 적용됩니다.</caps:sentence>
          <caps:sentence sentenceid="3cea98f77e893eb1025f89567a366d77" id="tgt6" class="tgtSentence"> 이 정보 보호 솔루션은 데이터를 다른 사용자와 공유하는 경우에도 데이터에 대한 제어를 유지할 수 있도록 합니다.</caps:sentence>
        </para>
        <para>
          <caps:sentence sentenceid="3d1e430f66ef0a41b3c0d4361753146d" id="tgt7" class="tgtSentence">예를 들어 조직 내의 사용자만 액세스할 수 있도록 파일을 구성할 수도 있고 파일 편집 가능 여부를 제어하거나 파일을 읽기 전용으로 제한하거나 파일 인쇄를 차단할 수도 있습니다.</caps:sentence>
          <caps:sentence sentenceid="a1d4b6ea938e5c3193bcc436be24f8c0" id="tgt8" class="tgtSentence"> 마찬가지로 전자 메일도 구성할 수 있으며 전체 회신 옵션 사용 또는 전자 메일 전달을 차단할 수 있습니다.</caps:sentence>
          <caps:sentence sentenceid="76c61c663112d6aabc8b0558688c8514" id="tgt9" class="tgtSentence"> 표준화된 정책 템플릿을 사용하면 이러한 보호 작업을 단순화하고 간소화할 수 있습니다.</caps:sentence>
        </para>
        <para>
          <caps:sentence sentenceid="31d23eeb49a60f86a1641f17c6570b72" id="tgt10" class="tgtSentence">
      자세한 설명과 일부 예제는 <link xlink:href="aeeebcd7-6646-4405-addf-ee1cc74df5df">What is Azure Rights Management?</link>을 참조하세요.</caps:sentence>
        </para>
        <para>
          <caps:sentence sentenceid="0d618ca3ca5b0a48f105c1e37165a023" id="tgt11" class="tgtSentence">
            <token>aad_rightsmanagement_1</token>를 자세히 살펴보고 조직에 배포하려면 다음 정보를 참조하세요.</caps:sentence>
        </para>
        <list class="bullet">
          <listItem>
            <para>
              <link xlink:href="5214667c-ec69-42ca-8bbf-8cb22da8c62e">Getting started with Azure AD Rights Management</link>
            </para>
          </listItem>
          <listItem>
            <para>
              <link xlink:href="206a0bfe-0912-4e0e-aa15-484b000b264c">Configuring rights management</link>
            </para>
          </listItem>
          <listItem>
            <para>
              <link xlink:href="18564e4a-9364-4ed2-8f17-89d24fc0d878">Using rights management</link>
            </para>
          </listItem>
          <listItem>
            <para>
              <link xlink:href="a890e04a-4b70-41b5-8d5f-3c210a669faa">Administering rights management</link>
            </para>
          </listItem>
          <listItem>
            <para>
              <link xlink:href="c994d616-cff6-4930-9228-a7f7d198a160">Rapid Deployment Guide for Azure Rights Management</link>
            </para>
          </listItem>
        </list>
        <para>
          <caps:sentence sentenceid="8f8764b84fbfe3fb41a1de8bd2151a22" id="tgt12" class="tgtSentence">추가 리소스는 <link xlink:href="7cc73d92-27d6-49ff-a8ab-2fae73519b4b">Information and Support for Azure Rights Management</link>을 참조하세요.</caps:sentence>
        </para>
      </introduction>
      <section>
        <title>
          <caps:sentence sentenceid="b75b1651ff8c1f6e857670d70de57727" id="tgt13" class="tgtSentence">또한 다음이라고 알려집니다.</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="0bb50d5ace4abd536a35235fd9cca548" id="tgt14" class="tgtSentence">또한 Azure Rights Management는 <legacyItalic>Azure 권한 관리 서비스</legacyItalic>라고 알려져 있지만 Azure에서 서비스로 실행하기 때문에 "서비스"는 종종 해당 이름에서 생략됩니다.</caps:sentence>
            <caps:sentence sentenceid="4ec4858d185533976ae0410b2d35079b" id="tgt15" class="tgtSentence">
              <legacyItalic>Active Directory Rights Management Services</legacyItalic>(AD RMS)의 클라우드 버전으로 처음에 <legacyItalic>Windows Rights Management Services</legacyItalic>(Windows RMS)로 릴리스되었습니다.</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="0726a4db7b39858b6c4062cb42e94fe2" id="tgt16" class="tgtSentence">RMS가 선행 작업에 대한 잘 알려진 약어이기 때문에 Azure Rights Management를 종종 약어로 <legacyItalic>Azure RMS</legacyItalic>라고 합니다.</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="951d003f6152823990af843b34aa46e3" id="tgt17" class="tgtSentence">Azure Rights Management의 이름은 원래 <legacyItalic>Windows Azure Active Directory Rights Management</legacyItalic>(종종 약어로 <legacyItalic>Windows Azure AD Rights Management</legacyItalic>라고 함)이었고, 다음 <legacyItalic>Windows Azure Rights Management</legacyItalic>, 이제 마지막으로 <legacyItalic>Azure Rights Management</legacyItalic>입니다.</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="ae8b2b285d98ab9534ef325989bd0813" id="tgt18" class="tgtSentence">또한 종종 약어로 <legacyItalic>IRM</legacyItalic>라고 하는 <legacyItalic>정보 Rights Management</legacyItalic>에서 참조를 볼 수도 있습니다.</caps:sentence>
            <caps:sentence sentenceid="bcf8f7f6e8efe34a2816544f253dc99e" id="tgt19" class="tgtSentence"> Rights Management의 Office 구현이며 Azure RMS 및 AD RMS를 모두 지원할 수 있습니다.</caps:sentence>
            <caps:sentence sentenceid="814cd385574d9159ca8935f57babd54f" id="tgt20" class="tgtSentence">  Azure RMS가 처음 릴리스되었을 때는 Office 365 E3 구독 등을 사용하여 Office 365로 사용할 수 있었습니다.</caps:sentence>
            <caps:sentence sentenceid="21c6900dba0d93d29042f515dd3cd695" id="tgt21" class="tgtSentence"> 이제 Azure RMS는 EMS(Enterprise Mobility Suite)와 같은 다른 구독으로 확장되고 Office 2016, Office 2013, Office 2010, SharePoint 및 Exchange의 온-프레미스 버전 등도 지원하며 모든 형식의 파일을 보호할 수 있습니다.</caps:sentence>
            <caps:sentence sentenceid="3ce055386165dac9a926371c350ecfed" id="tgt22" class="tgtSentence"> 자세한 내용은 <link xlink:href="2cdc7bde-4044-4021-b887-11476f99afd9">How Applications Support Azure Rights Management</link>를 참조하세요.</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="483562e5c3f5a51c6ece6ac16a3e8b0f" id="tgt23" class="tgtSentence">또한 <legacyItalic>Microsoft Rights Management</legacyItalic>, 또는 <legacyItalic>Microsoft Rights Management 서비스</legacyItalic>를 경우에 따라 참조할 수도 있으며 Azure RMS 및 AD RMS를 모두 포함할 수 있는 집합적인 용어입니다.</caps:sentence>
            <caps:sentence sentenceid="62590b7cc80fa58960258871f90025a1" id="tgt24" class="tgtSentence">  "<legacyItalic>새 Microsoft RMS</legacyItalic>"는 Azure Rights Management가 온-프레미스 선행 작업에 비교하여 배포의 용이성을 강조하기 위해 공식적으로 릴리스되었을 때 사용된 인기 있는 레이블이었습니다.</caps:sentence>
          </para>
          <alert class="tip">
            <para>
              <caps:sentence sentenceid="da41105f4520ac7aa5ba99aad81c8f23" id="tgt25" class="tgtSentence">이러한 용어(등)을 <link xlink:href="742877bf-26f5-40e3-b1f7-8475e7c3ce11">Terminology for Azure Rights Management</link>에서 확인할 수 있습니다.</caps:sentence>
            </para>
          </alert>
          <para>
            <caps:sentence sentenceid="d2584214cdff2107001a9881c3f0d321" id="tgt26" class="tgtSentence">엔터프라이즈 정보 보호 솔루션으로 Microsoft Rights Management 서비스는 디지털 소프트웨어의 일반적으로 불법적인 배포에 반해 보호하는 디지털 Rights Management(DRM) 솔루션을 제공하지 않습니다.</caps:sentence>
          </para>
        </content>
      </section>
      <relatedTopics></relatedTopics>
    </developerConceptualDocument>
  </caps:SxSTarget>
  <caps:SxSSource locale="en-US">
    <developerConceptualDocument xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd" xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <introduction>
        <para>
          <caps:sentence id="src1" class="srcSentence">This page introduces the technical documentation set for Microsoft <token>aad_rightsmanagement_1</token> (Azure RMS), to help you protect your organization’s sensitive information from unauthorized access, and control how this information is used.</caps:sentence>
          <caps:sentence id="src2" class="srcSentence">
            <token>aad_rightsmanagement_1</token> is a cloud service, and is integrated into other Microsoft cloud services and applications, such as Office 365 and Azure Active Directory.</caps:sentence>
          <caps:sentence id="src3" class="srcSentence"> However, it can also be used with your on-premises applications and services.</caps:sentence>
        </para>
        <para>
          <caps:sentence id="src4" class="srcSentence">
            <token>aad_rightsmanagement_2</token> uses encryption, identity, and authorization policies to help secure your files and email.</caps:sentence>
          <caps:sentence id="src5" class="srcSentence"> In comparison to standard access controls, such as NTFS permissions, protection that is applied by using <token>aad_rightsmanagement_2</token> stays with the files and emails, independently of the location—inside or outside your organization, networks, file servers, and applications.</caps:sentence>
          <caps:sentence id="src6" class="srcSentence"> This information protection solution keeps you in control of your data, even when it is shared with other people.</caps:sentence>
        </para>
        <para>
          <caps:sentence id="src7" class="srcSentence">For example, you can configure a file so that it can be accessed only by people in your organization, or control whether the file can be edited, or restricted to read-only, or prevent it from being printed.</caps:sentence>
          <caps:sentence id="src8" class="srcSentence"> You can configure emails similarly, and in addition, prevent them from being forwarded or prevent the use of the Reply All option.</caps:sentence>
          <caps:sentence id="src9" class="srcSentence"> These protection tasks can be simplified and streamlined by using standardized policy templates.</caps:sentence>
        </para>
        <para>
          <caps:sentence id="src10" class="srcSentence">
      For a deeper understanding and some examples, see <link xlink:href="aeeebcd7-6646-4405-addf-ee1cc74df5df">What is Azure Rights Management?</link></caps:sentence>
        </para>
        <para>
          <caps:sentence id="src11" class="srcSentence">Use the following information to learn more about <token>aad_rightsmanagement_1</token> and deploy it for your organization:</caps:sentence>
        </para>
        <list class="bullet">
          <listItem>
            <para>
              <link xlink:href="5214667c-ec69-42ca-8bbf-8cb22da8c62e">Getting started with Azure AD Rights Management</link>
            </para>
          </listItem>
          <listItem>
            <para>
              <link xlink:href="206a0bfe-0912-4e0e-aa15-484b000b264c">Configuring rights management</link>
            </para>
          </listItem>
          <listItem>
            <para>
              <link xlink:href="18564e4a-9364-4ed2-8f17-89d24fc0d878">Using rights management</link>
            </para>
          </listItem>
          <listItem>
            <para>
              <link xlink:href="a890e04a-4b70-41b5-8d5f-3c210a669faa">Administering rights management</link>
            </para>
          </listItem>
          <listItem>
            <para>
              <link xlink:href="c994d616-cff6-4930-9228-a7f7d198a160">Rapid Deployment Guide for Azure Rights Management</link>
            </para>
          </listItem>
        </list>
        <para>
          <caps:sentence id="src12" class="srcSentence">For additional resources, see <link xlink:href="7cc73d92-27d6-49ff-a8ab-2fae73519b4b">Information and Support for Azure Rights Management</link>.</caps:sentence>
        </para>
      </introduction>
      <section>
        <title>
          <caps:sentence id="src13" class="srcSentence">Also known as ...</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src14" class="srcSentence">Azure Rights Management is also known as <legacyItalic>Azure Rights Management service</legacyItalic>, but because it runs as a service in Azure, the "service" is often omitted from its name.</caps:sentence>
            <caps:sentence id="src15" class="srcSentence"> It is the cloud version of <legacyItalic>Active Directory Rights Management Services</legacyItalic> (AD RMS), which was first released as <legacyItalic>Windows Rights Management Services</legacyItalic> (Windows RMS).</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src16" class="srcSentence">Because RMS is a well-known abbreviation for its predecessors, Azure Rights Management is often abbreviated to <legacyItalic>Azure RMS</legacyItalic>.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src17" class="srcSentence">Azure Rights Management was originally named <legacyItalic>Windows Azure Active Directory Rights Management</legacyItalic> (often abbreviated to <legacyItalic>Windows Azure AD Rights Management</legacyItalic>), then  <legacyItalic>Windows Azure Rights Management</legacyItalic>, and now finally <legacyItalic>Azure Rights Management</legacyItalic>.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src18" class="srcSentence">You might also see references to <legacyItalic>Information Rights Management,</legacyItalic> often abbreviated to <legacyItalic>IRM</legacyItalic>.</caps:sentence>
            <caps:sentence id="src19" class="srcSentence"> This is the Office implementation of Rights Management, which can support both Azure RMS and AD RMS.</caps:sentence>
            <caps:sentence id="src20" class="srcSentence">  When Azure RMS was first released, it could only be used with Office 365—for example, with an Office 365 E3 subscription.</caps:sentence>
            <caps:sentence id="src21" class="srcSentence"> Now, Azure RMS  is extended to other subscriptions, such as the Enterprise Mobility Suite (EMS) and support now includes Office 2016, Office 2013, Office 2010, on-premises versions of SharePoint and Exchange, and Azure RMS can protect any file type.</caps:sentence>
            <caps:sentence id="src22" class="srcSentence"> For more information, see  <link xlink:href="2cdc7bde-4044-4021-b887-11476f99afd9">How Applications Support Azure Rights Management</link>.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src23" class="srcSentence">You might also see occasional references to <legacyItalic>Microsoft Rights Management</legacyItalic>, or <legacyItalic>Microsoft Rights Management services</legacyItalic>, which is a collective term that can include both Azure RMS and AD RMS.</caps:sentence>
            <caps:sentence id="src24" class="srcSentence">  The "<legacyItalic>NEW Microsoft RMS</legacyItalic>" was a popular label that was sometimes used  when Azure Rights Management was officially released, to emphasize the new ease of deployment in comparison to its on-premises predecessors.</caps:sentence>
          </para>
          <alert class="tip">
            <para>
              <caps:sentence id="src25" class="srcSentence">You'll find these terms (and more) in <link xlink:href="742877bf-26f5-40e3-b1f7-8475e7c3ce11">Terminology for Azure Rights Management</link>.</caps:sentence>
            </para>
          </alert>
          <para>
            <caps:sentence id="src26" class="srcSentence">As an enterprise information protection solution, Microsoft Rights Management services do not provide digital rights management (DRM) solutions that typically protect against illegal distribution of digital software.</caps:sentence>
          </para>
        </content>
      </section>
      <relatedTopics></relatedTopics>
    </developerConceptualDocument>
  </caps:SxSSource>
</caps:SxS>