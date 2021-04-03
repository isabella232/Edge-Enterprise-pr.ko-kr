---
title: 엔터프라이즈 사이트 구성 전략
ms.author: shisub
author: shisub
manager: srugh
ms.date: 03/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Internet Explorer 모드에 대한 엔터프라이즈 모드 사이트 목록을 구성하는 단계별 가이드입니다.
ms.openlocfilehash: 1d0b80950439fce77513413c3f5d1143538487d1
ms.sourcegitcommit: 93851b83dc11422924646a04a9e0f60ff2554af7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470156"
---
# <a name="enterprise-site-configuration-strategy"></a><span data-ttu-id="c6848-103">엔터프라이즈 사이트 구성 전략</span><span class="sxs-lookup"><span data-stu-id="c6848-103">Enterprise site configuration strategy</span></span>

<span data-ttu-id="c6848-104">이 문서에서는 Microsoft Edge 버전 77 이상에서 Internet Explorer 모드를 지원하기 위해 엔터프라이즈 모드 사이트 목록의 변경 사항을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c6848-104">This article describes changes to the Enterprise Mode Site List to support Internet Explorer mode for Microsoft Edge version 77 and later.</span></span>

<span data-ttu-id="c6848-105">엔터프라이즈 모드 사이트 목록 XML 파일의 스키마에 대한 자세한 정보는 [엔터프라이즈 모드 스키마 v.2 지침](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c6848-105">For more information on the schema for the Enterprise Mode Site List XML file, see [Enterprise Mode schema v.2 guidance](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance).</span></span>

> [!NOTE]
> <span data-ttu-id="c6848-106">이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6848-106">This article applies to Microsoft Edge version 77 or later.</span></span>
<!--
## Updated schema elements

The following table describes the \<open-in app\> element added to the v.2 of the Enterprise Mode schema:

| **Element** | **Description** |
| --- | --- |
| \<open-in app="**true**"\> | A child element that controls what browser is used for sites. This element is required for sites that need to **open in IE11**.|

**Example:**

``` xml
<site url="contoso.com">

  <open-in app="true">IE11</open-in>

</site>
```

The following table shows the possible values of the \<open-in\> element:

| **Value** | **Description** |
| --- | --- |
| **\<open-in\>IE11\</open-in\>** | Opens the site in IE mode or a full IE11 window. To enable IE mode, see [Configure IE mode policies](./edge-ie-mode-policies.md)|
| **\<open-in app="**true**"\>IE11\</open-in\>** | Opens the site in a full IE11 window |
| **\<open-in\>MSEdge\</open-in\>** | Opens the site in Microsoft Edge |
| **\<open-in\>None or not specified\</open-in\>** | Opens the site in the default browser or in the browser where the user navigated to the site. |
|**\<open-in\>Configurable\</open-in\>** | Allows the site to participate in IE mode engine determination. To learn more, see [Learn about Configurable sites in IE mode](edge-learnmore-configurable-sites-ie-mode.md).  |

>[!NOTE]
> The attribute app=**"true"** is only recognized when associated to _'open-in' IE11_. Adding it to the other 'open-in' elements won't change browser behavior.   -->

## <a name="configuration-strategy"></a><span data-ttu-id="c6848-107">구성 전략</span><span class="sxs-lookup"><span data-stu-id="c6848-107">Configuration strategy</span></span>

<span data-ttu-id="c6848-108">다음 단계는 IE 모드에 대한 사이트 구성 전략의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="c6848-108">The following steps are part of a site configuration strategy for IE mode:</span></span>
1. <span data-ttu-id="c6848-109">사이트 목록 준비</span><span class="sxs-lookup"><span data-stu-id="c6848-109">Prepare your site list</span></span>
2. <span data-ttu-id="c6848-110">중립 사이트 구성</span><span class="sxs-lookup"><span data-stu-id="c6848-110">Configure neutral sites</span></span>
3. <span data-ttu-id="c6848-111">(선택 사항) 필요한 경우 쿠키 공유 사용</span><span class="sxs-lookup"><span data-stu-id="c6848-111">(Optional) Use cookie sharing if necessary</span></span>

<!--
Step 1.  – if you don’t have one use Site Discovery Step-by-Step
Step 2 – Neutral sites + sticky mode
        Use more examples and explain sticky mode better
Step 3 – If that doesn’t cover your needs, then use Cookie sharing -->

## <a name="prepare-your-site-list"></a><span data-ttu-id="c6848-112">사이트 목록 준비</span><span class="sxs-lookup"><span data-stu-id="c6848-112">Prepare your site list</span></span>

<span data-ttu-id="c6848-113">IE11 또는 Microsoft Edge 레거시용 엔터프라이즈 모드 사이트 목록이 이미 있는 경우 다시 사용하여 IE 모드를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6848-113">If you already have an Enterprise Mode site list for IE11 or Microsoft Edge Legacy, you can reuse it to configure IE mode.</span></span>

<span data-ttu-id="c6848-114">그러나 사이트 목록이 없는 경우 [엔터프라이즈 사이트 검색 도구](https://docs.microsoft.com/deployedge/edge-ie-mode-site-discovery)를 사용하여 사이트 목록을 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6848-114">However, if you don't have a site list, you can use the [Enterprise Site Discovery tool](https://docs.microsoft.com/deployedge/edge-ie-mode-site-discovery) to populate your site list.</span></span>

## <a name="configure-neutral-sites"></a><span data-ttu-id="c6848-115">중립 사이트 구성</span><span class="sxs-lookup"><span data-stu-id="c6848-115">Configure neutral sites</span></span>

<span data-ttu-id="c6848-116">IE 모드가 제대로 작동하려면 인증/SSO(Single Sign-On) 서버를 중립 사이트로 명시적으로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6848-116">In order for IE mode to work properly, authentication / Single Sign-On (SSO) servers will need to be explicitly configured as neutral sites.</span></span> <span data-ttu-id="c6848-117">그렇지 않으면 IE 모드 페이지가 Microsoft Edge로 리디렉션을 시도하여 인증에 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="c6848-117">Otherwise, IE mode pages will try to redirect to Microsoft Edge, and authentication will fail.</span></span>

<span data-ttu-id="c6848-118">중립 사이트는 탐색이 시작된 브라우저(Microsoft Edge 또는 IE 모드)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c6848-118">A neutral site will use the browser where the navigation started - either Microsoft Edge or IE mode.</span></span> <span data-ttu-id="c6848-119">중립 사이트를 구성하면 최신 및 기존 인증 서버를 사용하는 모든 응용 프로그램이 계속 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="c6848-119">Configuring neutral sites ensures that all applications using these authentication servers, both modern and legacy, continue to work.</span></span>

<span data-ttu-id="c6848-120">엔터프라이즈 모드 사이트 목록 관리자 도구에서 *열기* 드롭다운을 '없음'으로 설정하거나 사이트 목록 XML을 직접 업데이트하여 중립 사이트를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6848-120">You can configure neutral sites by setting the *Open In* dropdown to 'None' in the Enterprise Mode Site List Manager tool or by directly updating the site list XML:</span></span>

``` xml
<site url="login.contoso.com">
   
    <open-in>None</open-in>

</site>
```

<span data-ttu-id="c6848-121">인증 서버를 식별하려면 IE11 개발자 도구를 사용하여 응용 프로그램에서 네트워크 트래픽을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="c6848-121">To identify authentication servers, inspect the network traffic from an application using the IE11 Developer Tools.</span></span> <span data-ttu-id="c6848-122">인증 서버를 식별하는 데 시간이 더 필요한 경우 사용자가 워크플로를 중단 없이 계속할 수 있도록 모든 페이지 내 탐색을 IE 모드로 유지하도록 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6848-122">If you need more time to identify your authentication servers, you can configure a policy to keep all in-page navigations in IE mode to allow your users to continue their workflows uninterrupted.</span></span> <span data-ttu-id="c6848-123">불필요한 경우 IE 모드 사용을 최소화하기 위해 인증 서버를 식별하고 사이트 목록에 추가한 후 이 설정을 사용하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6848-123">To minimize the use of IE mode when unnecessary, disable this setting once you've identified and added your authentication servers to the site list.</span></span> <span data-ttu-id="c6848-124">자세한 내용은 [IE 모드에서 페이지 내 탐색 유지](https://docs.microsoft.com/deployedge/edge-learnmore-inpage-nav)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c6848-124">For more information, see [Keep in-page navigation in IE mode](https://docs.microsoft.com/deployedge/edge-learnmore-inpage-nav).</span></span>

>[!NOTE]
   ><span data-ttu-id="c6848-125">엔터프라이즈 모드 스키마 v.1은 IE 모드 통합에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c6848-125">Enterprise Mode schema v.1 isn't supported for IE mode integration.</span></span> <span data-ttu-id="c6848-126">현재 스키마 v.1을 Internet Explorer 11과 함께 사용하는 경우에는 스키마 v.2로 업그레이드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6848-126">If you are currently using schema v.1 with Internet Explorer 11, you must upgrade to schema v.2.</span></span> <span data-ttu-id="c6848-127">자세한 내용은 [엔터프라이즈 모드 스키마 v.2 지침](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c6848-127">For more information, see [Enterprise Mode schema v.2 guidance](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance).</span></span>

## <a name="optional-use-cookie-sharing-if-necessary"></a><span data-ttu-id="c6848-128">(선택 사항) 필요한 경우 쿠키 공유 사용</span><span class="sxs-lookup"><span data-stu-id="c6848-128">(Optional) Use cookie sharing if necessary</span></span>

<span data-ttu-id="c6848-129">기본적으로 Microsoft Edge 및 Internet Explorer 프로세스는 세션 쿠키를 공유하지 않습니다. 이러한 공유 부족은 IE 모드를 사용하는 동안 일부 경우에는 불편할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6848-129">By default, the Microsoft Edge and Internet Explorer processes don't share session cookies, and this lack of sharing can be inconvenient in some cases while using IE mode.</span></span> <span data-ttu-id="c6848-130">예를 들어 사용자가 이전에 IE 모드에서 재인증해야 하는 경우 또는 Microsoft Edge 세션에서 로그아웃해도 중요한 트랜잭션에 대한 Internet Explorer 모드 세션에서 로그아웃되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c6848-130">For example, when a user has to reauthenticate in IE mode when previously they are accustomed to doing so or when signing out of a Microsoft Edge session doesn’t sign out of the Internet Explorer mode session for critical transactions.</span></span> <span data-ttu-id="c6848-131">이러한 시나리오에서는 SSO에서 설정한 특정 쿠키를 Microsoft Edge에서 Internet Explorer로 보내도록 구성할 수 있으므로 재인증할 필요가 없어져서 인증 환경이 더욱 원할해집니다.</span><span class="sxs-lookup"><span data-stu-id="c6848-131">In these scenarios, you can configure specific cookies set by SSO to be sent from Microsoft Edge to Internet Explorer so the authentication experience becomes more seamless by eliminating the need to reauthenticate.</span></span> <span data-ttu-id="c6848-132">자세한 내용은 [Microsoft Edge에서 Internet Explorer로 쿠키 공유](https://docs.microsoft.com/deployedge/edge-ie-mode-add-guidance-cookieshare)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c6848-132">For more information, see [Cookie sharing from Microsoft Edge to Internet Explorer](https://docs.microsoft.com/deployedge/edge-ie-mode-add-guidance-cookieshare).</span></span>

## <a name="see-also"></a><span data-ttu-id="c6848-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c6848-133">See also</span></span>

- [<span data-ttu-id="c6848-134">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="c6848-134">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="c6848-135">IE 모드 정보</span><span class="sxs-lookup"><span data-stu-id="c6848-135">About IE mode</span></span>](./edge-ie-mode.md)
- [<span data-ttu-id="c6848-136">추가 엔터프라이즈 모드 정보</span><span class="sxs-lookup"><span data-stu-id="c6848-136">Additional Enterprise Mode information</span></span>](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
