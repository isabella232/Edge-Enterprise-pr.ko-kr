---
title: IE 모드에서 Microsoft Edge 및 구성 가능한 사이트
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 05/28/2020
audience: ITPro
ms.topic: procedural
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: IE 모드에서 Microsoft Edge 및 구성 가능한 사이트
ms.openlocfilehash: 1bffdef8c88b7a83d999b29763fcca258102ed51
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447332"
---
# <a name="learn-about-configurable-sites-in-ie-mode"></a><span data-ttu-id="ab316-103">IE 모드에서 구성 가능한 사이트 알아보기</span><span class="sxs-lookup"><span data-stu-id="ab316-103">Learn about Configurable sites in IE mode</span></span>

<span data-ttu-id="ab316-104">이 문서에서는 Microsoft Edge에서 IE 모드를 사용할 때 엔터프라이즈 모드 사이트 목록의 구성 가능한 사이트 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ab316-104">This article explains the Configurable sites feature of the Enterprise Mode Site List when using IE mode in Microsoft Edge.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ab316-105">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="ab316-105">Prerequisites</span></span>

- <span data-ttu-id="ab316-106">Windows 업데이트</span><span class="sxs-lookup"><span data-stu-id="ab316-106">Windows updates</span></span>

  - <span data-ttu-id="ab316-107">Windows 10 버전 1909, Windows server 버전 1909 – KB4550945 이상</span><span class="sxs-lookup"><span data-stu-id="ab316-107">Windows 10 version 1909, Windows server version 1909 – KB4550945  or higher</span></span>
  - <span data-ttu-id="ab316-108">Windows 10 버전 1903, Windows server 버전 1903 – KB4550945 이상</span><span class="sxs-lookup"><span data-stu-id="ab316-108">Windows 10 version 1903, Windows server version 1903 – KB4550945  or higher</span></span>
  - <span data-ttu-id="ab316-109">Windows 10 버전 1809, Windows Server 버전 1809, and Windows Server 2019 - KB4550969 이상</span><span class="sxs-lookup"><span data-stu-id="ab316-109">Windows 10 version 1809, Windows Server version 1809, and Windows Server 2019 - KB4550969 or higher</span></span>
  - <span data-ttu-id="ab316-110">Windows 10 버전 1803 – KB4550944 이상</span><span class="sxs-lookup"><span data-stu-id="ab316-110">Windows 10 version 1803 – KB4550944 or higher</span></span>
  - <span data-ttu-id="ab316-111">Windows 10 버전 1607, Windows Server 2016-KB4556826 이상</span><span class="sxs-lookup"><span data-stu-id="ab316-111">Windows 10 version 1607, Windows Server 2016 - KB4556826 or higher</span></span>
  - <span data-ttu-id="ab316-112">Windows 10 초기 버전, 2015년 7월 - KB4550947 이상</span><span class="sxs-lookup"><span data-stu-id="ab316-112">Windows 10 initial version, July 2015 - KB4550947 or higher</span></span>
  - <span data-ttu-id="ab316-113">Windows 8.1 – KB4556798 이상</span><span class="sxs-lookup"><span data-stu-id="ab316-113">Windows 8.1 – KB4556798 or higher</span></span>

- <span data-ttu-id="ab316-114">Microsoft Edge 버전 83 이상</span><span class="sxs-lookup"><span data-stu-id="ab316-114">Microsoft Edge version 83 or later</span></span>
- <span data-ttu-id="ab316-115">엔터프라이즈 모드 사이트 목록으로 구성된 [IE 모드](./edge-ie-mode.md)</span><span class="sxs-lookup"><span data-stu-id="ab316-115">[IE mode](./edge-ie-mode.md) configured with Enterprise Mode Site List</span></span>

## <a name="overview"></a><span data-ttu-id="ab316-116">개요</span><span class="sxs-lookup"><span data-stu-id="ab316-116">Overview</span></span>

<span data-ttu-id="ab316-117">엔터프라이즈 모드 사이트 목록에서 IE 모드가 필요한 사이트를 구성하면 레거시 응용 프로그램을 사용하는 대부분의 환경에서 잘 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="ab316-117">Configuring sites needing IE mode in the Enterprise Mode Site List will work well for most environments with legacy applications.</span></span> <span data-ttu-id="ab316-118">그러나 경우에 따라 IE 모드에서 전체 도메인을 렌더링하지 않고 IE 모드에서 열리도록 사이트 하위 집합을 구성하는 데 적합하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab316-118">However, in some cases this approach isn't the best to configure a subset of sites to open in IE mode without rendering an entire domain in IE mode.</span></span> <span data-ttu-id="ab316-119">예를 들어 사용자 환경이 단일 서버에서 실행되는 최신 및 레거시 응용 프로그램을 모두 포함하고 IE 모드에서 레거시 응용 프로그램만 렌더링하고 나머지 응용 프로그램은 Microsoft Edge 모드에서 렌더링할 수 있는 유연성을 원합니다.</span><span class="sxs-lookup"><span data-stu-id="ab316-119">For example, when your environment contains both modern and legacy applications running on a single server and you would like the flexibility to render only the legacy applications in IE mode and the remaining applications to render in Microsoft Edge mode.</span></span>

<span data-ttu-id="ab316-120">해결 방법은 엔터프라이즈 모드 사이트 목록의 구성 가능한 사이트 기능을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ab316-120">The solution is to use the Configurable sites feature of the Enterprise Mode Site List.</span></span> <span data-ttu-id="ab316-121">기능을 사용하게 하려면 Microsoft Edge에서 "구성 가능한" 태그가 있는 사이트를 IE 모드 엔진 결정에 참여하도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="ab316-121">When the feature is enabled, Microsoft Edge will allow sites with the "configurable" tag to participate in IE mode engine determination.</span></span>

## <a name="how-configurable-sites-works"></a><span data-ttu-id="ab316-122">구성 가능한 사이트 동작 방식</span><span class="sxs-lookup"><span data-stu-id="ab316-122">How Configurable sites works</span></span>

### <a name="automatic-switching-from-the-microsoft-edge-engine-to-the-ie-mode-engine"></a><span data-ttu-id="ab316-123">Microsoft Edge 엔진에서 IE 모드 엔진으로 자동 전환</span><span class="sxs-lookup"><span data-stu-id="ab316-123">Automatic switching from the Microsoft Edge engine to the IE mode engine</span></span>

<span data-ttu-id="ab316-124">구성 가능한 사이트 기능을 사용하려면 `<open-in>Configurable</open-in>` 옵션이 있는 엔터프라이즈 모드 사이트 목록에서 하나 이상의 사이트가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ab316-124">To use the Configurable sites feature, you'll need one or more sites in the Enterprise Mode Site List to have the `<open-in>Configurable</open-in>` option.</span></span>

<span data-ttu-id="ab316-125">예제:</span><span class="sxs-lookup"><span data-stu-id="ab316-125">Example:</span></span>

```
<site-list version="1">
  <site url="app.com">
    <open-in>Configurable</open-in>
  </site>
</site-list>
```

<span data-ttu-id="ab316-126">구성 가능한 사이트 기능을 사용하려면 다음이 동작이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab316-126">When the Configurable sites feature is enabled, the following behavior occurs:</span></span>

1. <span data-ttu-id="ab316-127">구성 가능한 사이트에 요청을 하면 Microsoft Edge에서 HTTP 요청 헤더 "`X-InternetExplorerModeConfigurable: 1`"를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="ab316-127">When making a request to a Configurable site, Microsoft Edge will send the HTTP request header "`X-InternetExplorerModeConfigurable: 1`".</span></span>
2. <span data-ttu-id="ab316-128">구성 가능한 사이트는 HTTP 응답 헤더 "`X-InternetExplorerMode: 1`"와 함께 리디렉션 응답(예: HTTP 302)을 보내어 IE 모드에서 Microsoft Edge가 사이트를 로딩하도록 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab316-128">A Configurable site may send a redirect response (for example, HTTP 302) with the HTTP response header "`X-InternetExplorerMode: 1`" to request that Microsoft Edge loads the site in IE mode.</span></span>
3. <span data-ttu-id="ab316-129">리디렉션 대상 **(즉 위치** 응답 헤더의 값)도 구성 가능한 **또는** 중립 사이트 여야합니다. **그렇지 않으면** IE 모드의 응답 헤더가 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab316-129">The target of the redirect (that is, the value of the **Location** response header) must also be a **Configurable** or **Neutral** site, otherwise the IE mode response header will be ignored.</span></span> <span data-ttu-id="ab316-130">대게 리디렉션 대상은 원래 URL과 같을 것으로 예상됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab316-130">It's expected that the target of the redirect will usually be the same as the original URL.</span></span> <span data-ttu-id="ab316-131">그러나 꼭 그럴 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab316-131">However, it doesn't have to be.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ab316-132">리디렉션 응답은 리디렉션에 대한 Microsoft Edge의 일반 HTTP 캐싱 동작에 따라 캐싱이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab316-132">The redirect response is subject to caching according to Microsoft Edge's normal HTTP caching behavior for redirects.</span></span>

### <a name="switching-back-from-ie-mode-engine-to-microsoft-edge-engine"></a><span data-ttu-id="ab316-133">IE 모드 엔진에서 Microsoft Edge 엔진으로 다시 전환</span><span class="sxs-lookup"><span data-stu-id="ab316-133">Switching back from IE mode engine to Microsoft Edge engine</span></span>

<span data-ttu-id="ab316-134">Microsoft Edge에서 구성 가능한 사이트를 사용하면 IE 모드 탭에서 자동으로 다음과 같은 동작이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab316-134">Enabling Configurable sites in Microsoft Edge automatically enables the following behaviors in IE mode tabs:</span></span>

1. <span data-ttu-id="ab316-135">구성 가능한 사이트에 요청을 하면 IE 모드 탭은 Microsoft Edge 탭과 동일한 HTTP 요청 헤더 "`X-InternetExplorerModeConfigurable: 1`"를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="ab316-135">When making a request to a Configurable site, IE mode tabs will send the HTTP request header "`X-InternetExplorerModeConfigurable: 1`", the same as Microsoft Edge tabs.</span></span>
2. <span data-ttu-id="ab316-136">구성 가능한 사이트는 HTTP 응답 헤더 "`X-InternetExplorerMode: 0`"와 함께 리디렉션 응답(예: HTTP 302)을 보내 탐색이 Microsoft Edge 모드로 다시 전환되도록 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab316-136">A Configurable site might send a redirect response (for example, HTTP 302) with the HTTP response header "`X-InternetExplorerMode: 0`" to request that the navigation switch back to Microsoft Edge mode.</span></span>
3. <span data-ttu-id="ab316-137">리디렉션 대상 **(즉 위치** 응답 헤더의 값)도 구성 가능한 **또는** 중립 사이트 여야합니다. **그렇지 않으면** IE 모드의 응답 헤더가 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab316-137">The target of the redirect (that is, the value of the **Location** response header) must also be a **Configurable** or **Neutral** site, otherwise the IE mode response header will be ignored.</span></span> <span data-ttu-id="ab316-138">대게 리디렉션 대상은 원래 URL과 같을 것으로 예상됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab316-138">It's expected that the target of the redirect will usually be the same as the original URL.</span></span> <span data-ttu-id="ab316-139">그러나 꼭 그럴 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab316-139">However, it doesn't have to be.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ab316-140">리디렉션 응답은 리디렉션에 대한 Microsoft Edge의 일반 HTTP 캐싱 동작에 따라 캐싱이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab316-140">The redirect response is subject to caching according to Microsoft Edge's normal HTTP caching behavior for redirects.</span></span>

> [!TIP]
> <span data-ttu-id="ab316-141">두 브라우저 엔진은 구성 가능한 사이트에 동일한 "`X-InternetExplorerModeConfigurable: 1`" 요청 헤더를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="ab316-141">Both browser engines send the same "`X-InternetExplorerModeConfigurable: 1`" request header to Configurable sites.</span></span> <span data-ttu-id="ab316-142">사이트가 올바른 엔진에서 이미 로드될 때 리디렉션하지 않도록 하려면 사용자 에이전트 요청 헤더를 사용하여 Microsoft Edge 모드와 IE 모드의 요청을 구분해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab316-142">You should use the User-Agent request header to distinguish between requests from Microsoft Edge mode vs. IE mode to avoid redirecting when the site is already loading in the correct engine.</span></span>

## <a name="see-also"></a><span data-ttu-id="ab316-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ab316-143">See also</span></span>

- [<span data-ttu-id="ab316-144">IE 모드 정보</span><span class="sxs-lookup"><span data-stu-id="ab316-144">About IE mode</span></span>](./edge-ie-mode.md)
- [<span data-ttu-id="ab316-145">추가 엔터프라이즈 모드 정보</span><span class="sxs-lookup"><span data-stu-id="ab316-145">Additional Enterprise Mode information</span></span>](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [<span data-ttu-id="ab316-146">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="ab316-146">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)