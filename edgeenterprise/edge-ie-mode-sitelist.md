---
title: 엔터프라이즈 사이트 목록에서 사이트 구성
ms.author: cjacks
author: cjacks
manager: saudm
ms.date: 05/28/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 엔터프라이즈 사이트 목록 구성
ms.openlocfilehash: 969a4f6001dbe08a51c26ecf35812b101d315a59
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980729"
---
# <span data-ttu-id="101b3-103">엔터프라이즈 사이트 목록에서 사이트 구성</span><span class="sxs-lookup"><span data-stu-id="101b3-103">Configure Sites on the Enterprise Mode Site List</span></span>

<span data-ttu-id="101b3-104">이 문서에서는 Microsoft Edge 버전 77 이상에 대한 IE 모드 구성을 지원하는 엔터프라이즈 모드 사이트 목록의 변경 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="101b3-104">This article describes changes to the Enterprise Mode Site List that support configuring IE mode for Microsoft Edge version 77 and later.</span></span>

<span data-ttu-id="101b3-105">엔터프라이즈 모드 사이트 목록 XML 파일의 스키마에 대한 자세한 정보는 [엔터프라이즈 모드 스키마 v.2 지침](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="101b3-105">For more information on the schema for the Enterprise Mode Site List XML file, see [Enterprise Mode schema v.2 guidance](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance).</span></span>

> [!NOTE]
> <span data-ttu-id="101b3-106">이 문서는 Microsoft Edge **안정**, **Beta** 및 **Dev** 채널 버전 77 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="101b3-106">This article applies to Microsoft Edge **Stable**, **Beta** and **Dev** Channels, version 77 or later.</span></span>

## <span data-ttu-id="101b3-107">업데이트된 스키마 요소</span><span class="sxs-lookup"><span data-stu-id="101b3-107">Updated schema elements</span></span>

<span data-ttu-id="101b3-108">다음 표는 엔터프라이즈 모드 스키마 v.2에 추가된 \<open-in app\> 요소를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="101b3-108">The following table describes the \<open-in app\> element added to the v.2 of the Enterprise Mode schema:</span></span>

| **<span data-ttu-id="101b3-109">요소</span><span class="sxs-lookup"><span data-stu-id="101b3-109">Element</span></span>** | **<span data-ttu-id="101b3-110">설명</span><span class="sxs-lookup"><span data-stu-id="101b3-110">Description</span></span>** |
| --- | --- |
| \<open-in app="**true**"\> | <span data-ttu-id="101b3-111">사이트에 사용되는 브라우저를 제어하는 자식 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="101b3-111">A child element that controls what browser is used for sites.</span></span> <span data-ttu-id="101b3-112">이 요소는 **IE11에서 열어야 하는** 사이트에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="101b3-112">This element is required for sites that need to **open in IE11**.</span></span>|

**<span data-ttu-id="101b3-113">예제:</span><span class="sxs-lookup"><span data-stu-id="101b3-113">Example:</span></span>**

``` xml
<site url="contoso.com">

  <open-in app="true">IE11</open-in>

</site>
```

<span data-ttu-id="101b3-114">다음 표는 \<open-in\> 요소에 사용할 수 있는 값을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="101b3-114">The following table shows the possible values of the \<open-in\> element:</span></span>

| **<span data-ttu-id="101b3-115">값</span><span class="sxs-lookup"><span data-stu-id="101b3-115">Value</span></span>** | **<span data-ttu-id="101b3-116">설명</span><span class="sxs-lookup"><span data-stu-id="101b3-116">Description</span></span>** |
| --- | --- |
| **\<open-in\><span data-ttu-id="101b3-117">IE11</span><span class="sxs-lookup"><span data-stu-id="101b3-117">IE11</span></span>\</open-in\>** | <span data-ttu-id="101b3-118">사이트를 IE 모드로 열거나 전체 IE11 창으로 엽니다.</span><span class="sxs-lookup"><span data-stu-id="101b3-118">Opens the site in IE mode or a full IE11 window.</span></span> <span data-ttu-id="101b3-119">IE 모드를 활성화하려면 [IE 모드 정책 구성](https://docs.microsoft.com/deployedge/edge-ie-mode-policies)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="101b3-119">To enable IE mode, see [Configure IE mode policies](https://docs.microsoft.com/deployedge/edge-ie-mode-policies)</span></span>|
| **\<open-in app="**true**"\><span data-ttu-id="101b3-120">IE11</span><span class="sxs-lookup"><span data-stu-id="101b3-120">IE11</span></span>\</open-in\>** | <span data-ttu-id="101b3-121">전체 IE11 창에서 사이트를 엽니 다</span><span class="sxs-lookup"><span data-stu-id="101b3-121">Opens the site in a full IE11 window</span></span> |
| **\<open-in\><span data-ttu-id="101b3-122">MSEdge</span><span class="sxs-lookup"><span data-stu-id="101b3-122">MSEdge</span></span>\</open-in\>** | <span data-ttu-id="101b3-123">Microsoft Edge의 사이트를 엽니다</span><span class="sxs-lookup"><span data-stu-id="101b3-123">Opens the site in Microsoft Edge</span></span> |
| **\<open-in\><span data-ttu-id="101b3-124">없음 또는 지정하지 않음</span><span class="sxs-lookup"><span data-stu-id="101b3-124">None or not specified</span></span>\</open-in\>** | <span data-ttu-id="101b3-125">기본 브라우저 또는 사용자가 사이트를 탐색한 브라우저에서 사이트를 엽니다</span><span class="sxs-lookup"><span data-stu-id="101b3-125">Opens the site in the default browser or in the browser where the user navigated to the site.</span></span> |
|**\<open-in\><span data-ttu-id="101b3-126">구성 가능 여부</span><span class="sxs-lookup"><span data-stu-id="101b3-126">Configurable</span></span>\</open-in\>** | <span data-ttu-id="101b3-127">사이트가 IE 모드 엔진 결정에 참여할 수 있게합니다.</span><span class="sxs-lookup"><span data-stu-id="101b3-127">Allows the site to participate in IE mode engine determination.</span></span> <span data-ttu-id="101b3-128">자세한 내용은 [IE 모드에서 구성 가능한 사이트에 대한 자세한 정보](edge-learnmore-configurable-sites-ie-mode.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="101b3-128">To learn more, see [Learn about Configurable sites in IE mode](edge-learnmore-configurable-sites-ie-mode.md).</span></span>  |

>[!NOTE]
> <span data-ttu-id="101b3-129">app=**"true"** 특성은 _'open-in' IE11_에 연결된 경우에만 인식됩니다.</span><span class="sxs-lookup"><span data-stu-id="101b3-129">The attribute app=**"true"** is only recognized when associated to _'open-in' IE11_.</span></span> <span data-ttu-id="101b3-130">다른 'open-in' 요소에 추가해도 브라우저 동작이 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="101b3-130">Adding it to the other 'open-in' elements won't change browser behavior.</span></span>   

## <span data-ttu-id="101b3-131">중성 사이트 구성</span><span class="sxs-lookup"><span data-stu-id="101b3-131">Configure neutral sites</span></span>

<span data-ttu-id="101b3-132">IE 모드가 제대로 작동하려면 인증/Single Sign-on 서버를 중립적 사이트로 명시적으로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="101b3-132">In order for IE mode to work properly, authentication / Single Sign-On servers will need to be explicitly configured as neutral sites.</span></span> <span data-ttu-id="101b3-133">그렇지 않으면 IE 모드 페이지가 Microsoft Edge로 리디렉션을 시도하고 인증이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="101b3-133">Otherwise, IE mode pages will try to redirect to Microsoft Edge, and authentication will fail.</span></span>

<span data-ttu-id="101b3-134">중립 사이트는 탐색이 시작된 브라우저(Microsoft Edge 또는 IE 모드)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="101b3-134">A neutral site will use the browser where the navigation started - either Microsoft Edge or IE mode.</span></span> <span data-ttu-id="101b3-135">중립 사이트를 구성하면 최신 및 기존 인증 서버를 사용하는 모든 응용 프로그램이 계속 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="101b3-135">Configuring neutral sites ensures that all applications using these authentication servers, both modern and legacy, continue to work.</span></span>

<span data-ttu-id="101b3-136">엔터프라이즈 모드 사이트 목록 관리자 도구에서 *열기* 드롭다운을 '없음'으로 설정하거나 사이트 목록 XML을 직접 업데이트하여 중립 사이트를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="101b3-136">You can configure neutral sites by setting the *Open In* dropdown to 'None' in the Enterprise Mode Site List Manager tool or by directly updating the site list XML:</span></span>

``` xml
<site url="login.contoso.com">
   
    <open-in>None</open-in>

</site>
```

<span data-ttu-id="101b3-137">인증 서버를 식별하려면 IE11 개발자 도구를 사용하여 응용 프로그램에서 네트워크 트래픽을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="101b3-137">To identify authentication servers, inspect the network traffic from an application using the IE11 Developer Tools.</span></span> <span data-ttu-id="101b3-138">인증 서버를 식별하는 데 시간이 더 필요한 경우 모든 인 페이지 탐색을 IE 모드로 유지하도록 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="101b3-138">If you need more time to identify your authentication servers, you can configure a policy to keep all in-page navigation in IE mode.</span></span> <span data-ttu-id="101b3-139">IE 모드 사용을 최소화하려면 인증 서버를 식별하고 사이트 목록에 추가한 후에 이 설정을 비활성화하세요.</span><span class="sxs-lookup"><span data-stu-id="101b3-139">To minimize the use of IE mode, disable this setting once you've identified and added your authentication servers to the site list.</span></span> <span data-ttu-id="101b3-140">자세한 내용은 [IE 모드에 머무르기 위해 페이지 내 탐색 구성](https://docs.microsoft.com/deployedge/microsoft-edge-policies#internetexplorerintegrationsiteredirect)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="101b3-140">For more information, see [Configure in-page navigation to remain in IE mode](https://docs.microsoft.com/deployedge/microsoft-edge-policies#internetexplorerintegrationsiteredirect).</span></span>

>[!NOTE]
   ><span data-ttu-id="101b3-141">엔터프라이즈 모드 스키마 v.1은 IE 모드 통합에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="101b3-141">Enterprise Mode schema v.1 isn't supported for IE mode integration.</span></span> <span data-ttu-id="101b3-142">현재 스키마 v.1을 Internet Explorer 11과 함께 사용하는 경우에는 스키마 v.2로 업그레이드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="101b3-142">If you are currently using schema v.1 with Internet Explorer 11, you must upgrade to schema v.2.</span></span> <span data-ttu-id="101b3-143">자세한 내용은 [엔터프라이즈 모드 스키마 v.2 지침](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="101b3-143">For more information, see [Enterprise Mode schema v.2 guidance](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance).</span></span>

## <span data-ttu-id="101b3-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="101b3-144">See also</span></span>

- [<span data-ttu-id="101b3-145">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="101b3-145">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="101b3-146">IE 모드 정보</span><span class="sxs-lookup"><span data-stu-id="101b3-146">About IE mode</span></span>](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [<span data-ttu-id="101b3-147">추가 엔터프라이즈 모드 정보</span><span class="sxs-lookup"><span data-stu-id="101b3-147">Additional Enterprise Mode information</span></span>](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)