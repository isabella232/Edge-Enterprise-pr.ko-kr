---
title: Microsoft Edge에서 Internet Explorer로 쿠키 공유
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 'Microsoft Edge에서 Internet Explorer로 쿠키를 공유하는 방법 '
ms.openlocfilehash: 8f1a38106e49f71aa9d27f32cfecbd0df44eaf9f
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641844"
---
# <a name="cookie-sharing-from-microsoft-edge-to-internet-explorer"></a><span data-ttu-id="83010-103">Microsoft Edge에서 Internet Explorer로 쿠키 공유</span><span class="sxs-lookup"><span data-stu-id="83010-103">Cookie sharing from Microsoft Edge to Internet Explorer</span></span>

>[!Note]
> <span data-ttu-id="83010-104">Internet Explorer 11 데스크톱 응용 프로그램은 2022년 6월 15일 사용 및 지원이 중단됩니다(범위 내 항목 목록은 [FAQ 참고](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)).</span><span class="sxs-lookup"><span data-stu-id="83010-104">The Internet Explorer 11 desktop application will be retired and go out of support on June 15, 2022 (for a list of what’s in scope, [see the FAQ](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)).</span></span> <span data-ttu-id="83010-105">현재 사용하는 동일한 IE11 앱과 사이트는 Internet Explorer 모드에서 Microsoft Edge로 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83010-105">The same IE11 apps and sites you use today can open in Microsoft Edge with Internet Explorer mode.</span></span> <span data-ttu-id="83010-106">[여기서 자세한 내용을 알아보세요](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/).</span><span class="sxs-lookup"><span data-stu-id="83010-106">[Learn more here](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/).</span></span>

<span data-ttu-id="83010-107">이 문서에서는 Internet Explorer 모드를 사용하는 동안 Microsoft Edge 프로세스에서 Internet Explorer 프로세스로 세션 쿠키 공유를 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="83010-107">This article explains explains how to configure session cookie sharing from a Microsoft Edge process to Internet Explorer process, while using Internet Explorer mode.</span></span>

> [!NOTE]
> <span data-ttu-id="83010-108">이 문서는 Microsoft Edge 버전 87 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="83010-108">This article applies to Microsoft Edge version 87 or later.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="83010-109">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="83010-109">Prerequisites</span></span>

- <span data-ttu-id="83010-110">Windows 업데이트</span><span class="sxs-lookup"><span data-stu-id="83010-110">Windows updates</span></span>

  - <span data-ttu-id="83010-111">Windows 10 버전 2004, Windows Server 버전 2004 - KB4571744 이상</span><span class="sxs-lookup"><span data-stu-id="83010-111">Windows 10 version 2004, Windows Server version 2004 - KB4571744 or higher</span></span>
  - <span data-ttu-id="83010-112">Windows 10 버전 1909, Windows Server 버전 1909 – KB4566116 이상</span><span class="sxs-lookup"><span data-stu-id="83010-112">Windows 10 version 1909, Windows Server version 1909 – KB4566116 or higher</span></span>
  - <span data-ttu-id="83010-113">Windows 10 버전 1903, Windows Server 버전 1903 – KB4566116 이상</span><span class="sxs-lookup"><span data-stu-id="83010-113">Windows 10 version 1903, Windows Server version 1903 – KB4566116 or higher</span></span>
  - <span data-ttu-id="83010-114">Windows 10 버전 1809, Windows Server 버전 1809 및 Windows Server 2019 - KB4571748 이상</span><span class="sxs-lookup"><span data-stu-id="83010-114">Windows 10 version 1809, Windows Server version 1809, and Windows Server 2019 - KB4571748 or higher</span></span>
  - <span data-ttu-id="83010-115">Windows 10 버전 1803 – KB4577032 이상</span><span class="sxs-lookup"><span data-stu-id="83010-115">Windows 10 version 1803 – KB4577032 or higher</span></span>

- <span data-ttu-id="83010-116">Microsoft Edge 버전 87 이상</span><span class="sxs-lookup"><span data-stu-id="83010-116">Microsoft Edge version 87 or later</span></span>
- <span data-ttu-id="83010-117">엔터프라이즈 모드 사이트 목록으로 구성된 [IE 모드](./edge-ie-mode.md) </span><span class="sxs-lookup"><span data-stu-id="83010-117">[IE mode](./edge-ie-mode.md) configured with Enterprise Mode Site List</span></span>

## <a name="overview"></a><span data-ttu-id="83010-118">개요</span><span class="sxs-lookup"><span data-stu-id="83010-118">Overview</span></span>

<span data-ttu-id="83010-119">대규모 조직의 일반적인 구성은 최신 브라우저에서 작동하는 응용 프로그램을 다른 응용 프로그램에 연결하는 것으로, 이는 워크플로의 일부로써 SSO(Single Sign On)를 사용하도록 설정된 Internet Explorer 모드에서 열리도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83010-119">A common configuration in large organizations is to have an application that works on a modern browser link to another application, which might be configured to open in Internet Explorer mode with Single Sign On (SSO) enabled as part of the workflow.</span></span>

<span data-ttu-id="83010-120">기본적으로 Microsoft Edge 및 Internet Explorer 프로세스는 세션 쿠키를 공유하지 않으며, 경우에 따라 이 프로세스가 번거로울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83010-120">By default, the Microsoft Edge and Internet Explorer processes don't share session cookies, and this can be inconvenient in some cases.</span></span> <span data-ttu-id="83010-121">예를 들어, 사용자가 Internet Explorer 모드로 다시 인증해야 하거나 Microsoft Edge 세션에서 로그아웃할 때 Internet Explorer 모드 세션에서 로그아웃되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83010-121">For example, when a user has to re-authenticate in Internet Explorer mode or when signing out of an Microsoft Edge session doesn’t sign out of the Internet Explorer mode session.</span></span> <span data-ttu-id="83010-122">이러한 시나리오에서는 SSO에 의해 설정된 특정 쿠키를 Microsoft Edge에서 Internet Explorer로 보내도록 구성할 수 있으므로 재인증할 필요없이 인증 환경이 더욱 원활해집니다.</span><span class="sxs-lookup"><span data-stu-id="83010-122">In these scenarios, you can configure specific cookies set by SSO to be sent from Microsoft Edge to Internet Explorer so the authentication experience becomes more seamless by eliminating the need to re-authenticate.</span></span>

> [!NOTE]
> <span data-ttu-id="83010-123">세션 쿠키는 Microsoft Edge에서 Internet Explorer로만 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83010-123">Session cookies can only be shared from Microsoft Edge to Internet Explorer.</span></span> <span data-ttu-id="83010-124">세션 쿠키를 반대로(Internet Explorer에서 Microsoft Edge로) 공유할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="83010-124">Sharing session cookies in reverse (from Internet Explorer to Microsoft Edge) isn't possible.</span></span>

## <a name="how-cookie-sharing-works"></a><span data-ttu-id="83010-125">쿠키 공유 작동 방식</span><span class="sxs-lookup"><span data-stu-id="83010-125">How cookie sharing works</span></span>

<span data-ttu-id="83010-126">Internet Explorer를 사용하여 Microsoft Edge 세션에서 공유되는 쿠키를 추가 요소로 지정할 수 있도록 엔터프라이즈 모드 사이즈 목록 XML이 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="83010-126">The Enterprise Mode site list XML has been extended to allow additional elements to specify cookies that need to be shared from a Microsoft Edge session with Internet Explorer.</span></span>  

<span data-ttu-id="83010-127">Microsoft Edge 세션에서 Internet Explorer 모드 탭을 처음 만들 때 일치하는 모든 쿠키가 Internet Explorer 세션에 공유됩니다.</span><span class="sxs-lookup"><span data-stu-id="83010-127">The first time an Internet Explorer mode tab is created in a Microsoft Edge session, all matching cookies are shared to the Internet Explorer session.</span></span> <span data-ttu-id="83010-128">그런 다음, 규칙과 일치하는 쿠키가 추가, 삭제 또는 수정될 때마다 Internet Explorer 세션에 대한 업데이트로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="83010-128">Subsequently, any time a cookie that matches a rule is added, deleted, or modified it is sent as an update to the Internet Explorer session.</span></span> <span data-ttu-id="83010-129">공유 쿠키 집합은 사이트 목록이 업데이트되는 경우에도 다시 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="83010-129">The set of shared cookies is also re-evaluated when the site list is updated.</span></span>

### <a name="updated-schema-elements"></a><span data-ttu-id="83010-130">업데이트된 스키마 요소</span><span class="sxs-lookup"><span data-stu-id="83010-130">Updated schema elements</span></span>

<span data-ttu-id="83010-131">다음 표에서는 쿠키 공유 기능을 지원하기 위해 추가된 \<shared-cookie\> 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="83010-131">The following table describes the \<shared-cookie\> element added to support the cookie sharing feature.</span></span>

| <span data-ttu-id="83010-132">요소</span><span class="sxs-lookup"><span data-stu-id="83010-132">Element</span></span>| <span data-ttu-id="83010-133">설명</span><span class="sxs-lookup"><span data-stu-id="83010-133">Description</span></span> |
|-|-|
| \<shared-cookie **domain**=".contoso.com" **name**="cookie1"\>\</shared-cookie\><br><br><span data-ttu-id="83010-134">또는</span><span class="sxs-lookup"><span data-stu-id="83010-134">OR</span></span><br><br>\<shared-cookie **host**="subdomain.contoso.com" **name**="cookie2"\>\</shared-cookie\>   |<span data-ttu-id="83010-135">**(필수)** \<shared-cookie\>요소에는 최소한 *도메인*(도메인 쿠키에 해당) 또는 *호스트*(호스트 전용 쿠키에 해당) 특성 및 *이름* 특성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="83010-135">**(Required)** A \<shared-cookie\> element requires, at minimum, a *domain* (for domain cookies) or a *host* (for host-only cookies) attribute and a *name* attribute.</span></span><br><span data-ttu-id="83010-136">이러한 항목은 각각 쿠키의 도메인 및 이름과 정확히 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83010-136">These must be exact matches to the cookie's domain and name respectively.</span></span> <span data-ttu-id="83010-137">**하위** 도메인과 일치하지 않는 점에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="83010-137">**Note** that subdomains do not match.</span></span><br><br><span data-ttu-id="83010-138">*도메인* 속성은 도메인 쿠키에 사용됩니다(앞에 점이 허용되지만 이는 선택 사항임).</span><span class="sxs-lookup"><span data-stu-id="83010-138">The *domain* attribute is used for domain cookies (and a leading dot is allowed but optional).</span></span><br><span data-ttu-id="83010-139">*호스트* 특성에는 호스트 전용 쿠키가 사용됩니다(앞에 점은 오류임).</span><span class="sxs-lookup"><span data-stu-id="83010-139">The *host* attribute is used for host-only cookies (and a leading dot is an error).</span></span> <span data-ttu-id="83010-140">둘 다 지정하지 않거나 둘 다 지정하면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="83010-140">Specifying neither or both will result in an error.</span></span><br><span data-ttu-id="83010-141">\* 여기서 쿠키는, 쿠키 문자열에 도메인이 지정된 경우(HTTP 집합-쿠키 응답 헤더 또는 document.cookie JS API를 통해)의 도메인 쿠키입니다.</span><span class="sxs-lookup"><span data-stu-id="83010-141">\* A cookie is a domain cookie if a domain was specified in the cookie string (via HTTP Set-Cookie response header or document.cookie JS API).</span></span> <span data-ttu-id="83010-142">도메인 쿠키는 지정된 도메인 및 모든 하위 도메인에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="83010-142">A domain cookie applies to the specified domain and all subdomains.</span></span> <span data-ttu-id="83010-143">쿠키 문자열에 도메인이 지정되지 않은 경우, 쿠키는 호스트 전용 쿠키 이며 설정된 특정 호스트에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="83010-143">If a domain was not specified in the cookie string, the cookie is a host-only cookie and only applies to the specific host that it was set for.</span></span> <span data-ttu-id="83010-144">한 단어로 된 호스트 이름(예: http://intranetsite) 및 IP 주소(예: http://10.0.0.1)와 같은 일부 URL 클래스는 호스트 전용 쿠키만 설정할 수 있음에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="83010-144">Note that some classes of URLs such as single-word hostnames (e.g. http://intranetsite) and IP addresses (e.g. http://10.0.0.1) can only set host-only cookies.</span></span>    |
| \<shared-cookie **host**="subdomain.contoso.com" **name**="cookie2" **path**="/a/b/c"\>\</shared-cookie\>  | <span data-ttu-id="83010-145">**(선택 사항)** *경로* 특성을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83010-145">**(Optional)** A *path* attribute may be specified.</span></span> <span data-ttu-id="83010-146">경로 특성을 지정하지 않은 경우(또는 경로 특성이 비어있는 경우), 도메인/호스트 및 이름과 일치하는 모든 쿠키가 경로(와일드 카드 규칙)에 상관없이 정책과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="83010-146">If no path attribute is specified (or if the path attribute is empty), any cookies matching domain/host and name match the policy, regardless of path (wildcard rule).</span></span><br><br><span data-ttu-id="83010-147">경로가 지정되면 쿠키가 정확하게 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83010-147">If a path is specified, it must be an exact match.</span></span><br><span data-ttu-id="83010-148">쿠키가 경로와 일치하는 경우, 경로가 없는 규칙보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="83010-148">If a cookie matches a rule with a path, that takes precedence over a rule without a path.</span></span> |

#### <a name="sharing-example"></a><span data-ttu-id="83010-149">공유 예</span><span class="sxs-lookup"><span data-stu-id="83010-149">Sharing example</span></span>

```xml
<site-list version="1">
<shared-cookie domain=".contoso.com" name="cookie1"></shared-cookie> 
<shared-cookie host="subdomain.contoso.com" name="cookie2" path="/a/b/c">
</shared-cookie>
</site-list>
```

## <a name="see-also"></a><span data-ttu-id="83010-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83010-150">See also</span></span>

- [<span data-ttu-id="83010-151">IE 모드 정보</span><span class="sxs-lookup"><span data-stu-id="83010-151">About IE mode</span></span>](./edge-ie-mode.md)
- [<span data-ttu-id="83010-152">구성 가능한 사이트 정보</span><span class="sxs-lookup"><span data-stu-id="83010-152">Configurable sites information</span></span>](./edge-learnmore-configurable-sites-ie-mode.md)
- [<span data-ttu-id="83010-153">추가 엔터프라이즈 모드 정보</span><span class="sxs-lookup"><span data-stu-id="83010-153">Additional Enterprise Mode information</span></span>](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [<span data-ttu-id="83010-154">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="83010-154">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)