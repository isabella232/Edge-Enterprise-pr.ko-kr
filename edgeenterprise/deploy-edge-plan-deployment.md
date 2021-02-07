---
title: Microsoft Edge 배포 계획
ms.author: collw
author: appcompatguy
manager: srugh
ms.date: 02/05/2021
audience: ITPro
ms.topic: procedural
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 배포 계획
ms.openlocfilehash: 1b56d9874550c2002cec0577a53a3bf5766e2805
ms.sourcegitcommit: 16a92a51560fdba6f6480e4533453348f026c7ef
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2021
ms.locfileid: "11313878"
---
# <span data-ttu-id="bc6ec-103">Microsoft Edge 배포 계획</span><span class="sxs-lookup"><span data-stu-id="bc6ec-103">Plan your deployment of Microsoft Edge</span></span>

<span data-ttu-id="bc6ec-104">이 문서에서는 엔터프라이즈 환경에서 Microsoft Edge를 배포하는 데 권장되는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-104">This article describes the recommended practices for deploying Microsoft Edge in an enterprise environment.</span></span>

>[!NOTE]
><span data-ttu-id="bc6ec-105">이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-105">This article applies to Microsoft Edge version 77 or later.</span></span>

<span data-ttu-id="bc6ec-106">다음 섹션에서는 Microsoft Edge 배포를 계획하기 위한 구체적인 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-106">The following sections provide specific guidance for planning your Microsoft Edge deployment.</span></span>

- [<span data-ttu-id="bc6ec-107">브라우저 환경 및 요구 사항 평가</span><span class="sxs-lookup"><span data-stu-id="bc6ec-107">Evaluate browser environment and requirements</span></span>](#evaluate-your-existing-browser-environment-and-browser-needs)
- [<span data-ttu-id="bc6ec-108">Windows 10 장치가 준비되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="bc6ec-108">Make sure Windows 10 devices are ready</span></span>](#make-sure-your-windows-10-devices-are-ready)
- [<span data-ttu-id="bc6ec-109">배포 방법 선택</span><span class="sxs-lookup"><span data-stu-id="bc6ec-109">Pick deployment methodology</span></span>](#determine-your-deployment-methodology)
- [<span data-ttu-id="bc6ec-110">사이트 검색 수행</span><span class="sxs-lookup"><span data-stu-id="bc6ec-110">Do site discovery</span></span>](#do-site-discovery)
- [<span data-ttu-id="bc6ec-111">채널 전략 선택</span><span class="sxs-lookup"><span data-stu-id="bc6ec-111">Pick channel strategy</span></span>](#determine-your-channel-strategy)
- [<span data-ttu-id="bc6ec-112">정책 식별 및 구성</span><span class="sxs-lookup"><span data-stu-id="bc6ec-112">Identify and configure policies</span></span>](#define-and-configure-policies)
- [<span data-ttu-id="bc6ec-113">앱 호환성 테스트</span><span class="sxs-lookup"><span data-stu-id="bc6ec-113">Test App compatibility</span></span>](#do-app-compatibility-testing)
- [<span data-ttu-id="bc6ec-114">Microsoft Edge 파일럿</span><span class="sxs-lookup"><span data-stu-id="bc6ec-114">Microsoft Edge pilot</span></span>](#deploy-microsoft-edge-to-a-pilot-group)
- [<span data-ttu-id="bc6ec-115">파일럿 평가</span><span class="sxs-lookup"><span data-stu-id="bc6ec-115">Evaluate pilot</span></span>](#validate-your-deployment)
- [<span data-ttu-id="bc6ec-116">엔터프라이즈에 Microsoft Edge 구축</span><span class="sxs-lookup"><span data-stu-id="bc6ec-116">Deploy Microsoft Edge across the enterprise</span></span>](#broad-deployment-of-microsoft-edge)

## <span data-ttu-id="bc6ec-117">기존 브라우저 환경 및 브라우저 요구 사항 평가</span><span class="sxs-lookup"><span data-stu-id="bc6ec-117">Evaluate your existing browser environment and browser needs</span></span>

<span data-ttu-id="bc6ec-118">현재 브라우저 상태와 프로젝트 비전을 이해하여 모든 프로젝트 이해 관계자가 동일한 결과를 얻기 위해 작업할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-118">Take time to understand your current browser state and project vision to ensure that all project stakeholders are aligned and working towards the same result.</span></span>

<span data-ttu-id="bc6ec-119">현재 상태를 정의하여 시작:</span><span class="sxs-lookup"><span data-stu-id="bc6ec-119">Start by defining your current state:</span></span>

- <span data-ttu-id="bc6ec-120">현재 환경에 배포되어 있는 브라우저는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="bc6ec-120">Which browsers are currently deployed in your environment?</span></span>
- <span data-ttu-id="bc6ec-121">기본 브라우저로 설정된 브라우저는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="bc6ec-121">Which browser is set as the default browser?</span></span>
- <span data-ttu-id="bc6ec-122">일부 앱에 대해 Internet Explorer를 사용해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="bc6ec-122">Do you need to use Internet Explorer for some of your apps?</span></span>
- <span data-ttu-id="bc6ec-123">지금 엔터프라이즈 모드 사이트 목록을 사용하여 Internet Explorer를 구성하십니까?</span><span class="sxs-lookup"><span data-stu-id="bc6ec-123">Do you use an Enterprise Mode Site List to configure Internet Explorer today?</span></span>
- <span data-ttu-id="bc6ec-124">사용자 환경에서 지원되는 OS 플랫폼은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="bc6ec-124">What OS platforms are supported in your environment?</span></span> <span data-ttu-id="bc6ec-125">(Windows 10, macOS, Windows 7, Windows Server, 등)</span><span class="sxs-lookup"><span data-stu-id="bc6ec-125">(Windows 10, macOS, Windows 7, Windows Server, etc.)</span></span>
- <span data-ttu-id="bc6ec-126">브라우저 관리에 사용하는 관리 도구는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="bc6ec-126">What management tools do you use for browser management?</span></span>
- <span data-ttu-id="bc6ec-127">브라우저 구성 및 관리를 담당하는 사람은 누구인가요?</span><span class="sxs-lookup"><span data-stu-id="bc6ec-127">Who is responsible for browser configuration and management?</span></span>
- <span data-ttu-id="bc6ec-128">브라우저 호환성을 확인하는 프로세스는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="bc6ec-128">What is your process for validating browser compatibility?</span></span>

<span data-ttu-id="bc6ec-129">현재 상태를 파악한 후 다음을 고려하여 브라우저 배포에 대한 원하는 목표를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-129">After you understand the current state, you can determine the desired goals for your browser deployment, taking into account the following:</span></span>

- <span data-ttu-id="bc6ec-130">[Microsoft Edge를 기본 브라우저로 설정](https://docs.microsoft.com/DeployEdge/edge-default-browser)하기 원하십니까?</span><span class="sxs-lookup"><span data-stu-id="bc6ec-130">Do you want to [set Microsoft Edge as your default browser](https://docs.microsoft.com/DeployEdge/edge-default-browser)?</span></span>
- <span data-ttu-id="bc6ec-131">어떻게 [Microsoft Edge를 구성](https://docs.microsoft.com/DeployEdge/configure-microsoft-edge)하시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="bc6ec-131">How will you [configure Microsoft Edge](https://docs.microsoft.com/DeployEdge/configure-microsoft-edge)?</span></span>
- <span data-ttu-id="bc6ec-132">초기 배포의 일부로 구성하는 데 중요한 기능은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="bc6ec-132">What features are critical to configure as part of your initial deployment?</span></span>
- <span data-ttu-id="bc6ec-133">식별된 호환성 또는 구성 문제를 해결하는 프로세스는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="bc6ec-133">What is the process for addressing any identified compatibility or configuration issues?</span></span>

<span data-ttu-id="bc6ec-134">또한 다음과 같이 관심 있는 기능에 대한 **사전 요구 사항**을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-134">You should also understand the **pre-requisites** for features you're interested in, such as:</span></span>

- [<span data-ttu-id="bc6ec-135">Windows Defender Application Guard</span><span class="sxs-lookup"><span data-stu-id="bc6ec-135">Windows Defender Application Guard</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-guard/reqs-wd-app-guard)
- [<span data-ttu-id="bc6ec-136">Internet Explorer 모드</span><span class="sxs-lookup"><span data-stu-id="bc6ec-136">Internet Explorer mode</span></span>](https://docs.microsoft.com/DeployEdge/edge-ie-mode)
- [<span data-ttu-id="bc6ec-137">인증 및 동기화</span><span class="sxs-lookup"><span data-stu-id="bc6ec-137">Authentication and sync</span></span>](https://docs.microsoft.com/DeployEdge/microsoft-edge-security-identity)

<span data-ttu-id="bc6ec-138">이러한 답변을 고려하여 Microsoft Edge 배포를 계획할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-138">With these answers in mind, you're ready to planning your Microsoft Edge deployment.</span></span>
<!--bookmark -->

## <span data-ttu-id="bc6ec-139">Windows 10 장치가 준비되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="bc6ec-139">Make sure your Windows 10 devices are ready</span></span>

<span data-ttu-id="bc6ec-140">Edge Stable 채널을 사용하려면 2019년 10월 이후의 LCU(Latest Cumulative Update)가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-140">The Edge Stable channel requires the Latest Cumulative Update (LCU) from October 2019 (or later).</span></span> <span data-ttu-id="bc6ec-141">이전 LCU가 포함된 Windows 10 장치에 배포하는 경우 설치에 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-141">If you attempt to deploy to a Windows 10 device that has an older LCU, then the installation will fail.</span></span> <span data-ttu-id="bc6ec-142">Edge를 배포하기 전에 적용해야 하는 최소 LCU에 대한 자세한 내용은 [다음 버전의 Microsoft Edge를 지원하기 위해 Windows 업데이트](https://docs.microsoft.com/DeployEdge/microsoft-edge-sysupdate-windows-updates)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-142">For more details about the minimum LCU that must be applied before deploying Edge, see [Windows updates to support the next version of Microsoft Edge](https://docs.microsoft.com/DeployEdge/microsoft-edge-sysupdate-windows-updates).</span></span>

## <span data-ttu-id="bc6ec-143">배포 방법 결정</span><span class="sxs-lookup"><span data-stu-id="bc6ec-143">Determine your deployment methodology</span></span>

<span data-ttu-id="bc6ec-144">원하는 종료 상태를 알고 있다면 이를 수행하는 방법을 계획할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-144">After you know your desired end state, you're ready to start planning how to get there.</span></span> <span data-ttu-id="bc6ec-145">Microsoft Edge를 배포하는 두 가지 주요 방법으로는 역할별 및 사이트별이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-145">The two main ways to deploy Microsoft Edge are by role, and by site.</span></span>

### <span data-ttu-id="bc6ec-146">역할별로 최종 사용자에게 배포</span><span class="sxs-lookup"><span data-stu-id="bc6ec-146">Deploy to end users by role</span></span>

<span data-ttu-id="bc6ec-147">앱 호환성이 주요 관심사이고 테스트할 앱을 모르는 경우에는 역할별로 최종 사용자에게 배포하는 것을 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-147">If app compatibility is your main concern, and you don't have a firm grasp on which apps to test, you might want to consider deploying to end users by role.</span></span> <span data-ttu-id="bc6ec-148">이렇게 하면 단계별 배포의 각 웨이브가 호환성 문제를 해결하기 위해 구성을 수정해야 하는 앱에 대한 피드백과 인사이트를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-148">This enables each wave of a phased deployment to provide feedback and insights on apps that might need to have their configuration modified to address compatibility issues.</span></span>

### <span data-ttu-id="bc6ec-149">사이트별로 최종 사용자에게 배포</span><span class="sxs-lookup"><span data-stu-id="bc6ec-149">Deploy to end users by site</span></span>

<span data-ttu-id="bc6ec-150">대역폭이 주요 관심사인 경우에는 응용 프로그램 호환성 테스트를 미리 수행해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-150">If bandwidth is your primary concern, you might want to consider doing application compatibility testing up front.</span></span> <span data-ttu-id="bc6ec-151">테스트를 마친 후에는 다른 소프트웨어 배달 최적화를 이용할 수 있도록 사이트별로 최종 사용자에게 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-151">After you finish testing, deploy to end users by site so you can leverage caching other software delivery optimizations.</span></span>

## <span data-ttu-id="bc6ec-152">사이트 검색 수행</span><span class="sxs-lookup"><span data-stu-id="bc6ec-152">Do site discovery</span></span>

<span data-ttu-id="bc6ec-153">레거시 웹 응용 프로그램에 대한 종속성이 있고, 대부분의 고객이 사용하는 Internet Explorer 모드를 사용하려는 경우에는 몇 가지 추가 사이트 검색을 수행해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-153">If you have a dependency on legacy web applications, and plan to use Internet Explorer mode (which most customers do), then you probably need to do some additional site discovery.</span></span>

### <span data-ttu-id="bc6ec-154">레거시 버전의 Microsoft Edge를 이미 배포하고 구성한 경우</span><span class="sxs-lookup"><span data-stu-id="bc6ec-154">If you've already deployed and configured the legacy version of Microsoft Edge</span></span>

<span data-ttu-id="bc6ec-155">레거시 버전의 Microsoft Edge에 대해 작동하도록 이미 엔터프라이즈 사이트 목록을 구성한 경우 작업이 거의 완료된 것입니다!</span><span class="sxs-lookup"><span data-stu-id="bc6ec-155">If you've already configured your Enterprise Site List to work for the legacy version of Microsoft Edge, then your work is almost done!</span></span> <span data-ttu-id="bc6ec-156">추가해야 할 수 있는 사항은 중립 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-156">The one thing you may need to add are neutral sites.</span></span>

<span data-ttu-id="bc6ec-157">중립 사이트는 일반적으로 SSO(Single Sign-on)를 제공하는 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-157">Neutral sites are typically sites that provide Single Sign-On (SSO).</span></span> <span data-ttu-id="bc6ec-158">Microsoft Edge에서 중립 사이트로 이동한 경우 Microsoft Edge에서 인증을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-158">If you navigate to a neutral site from Microsoft Edge, then you want to stay in Microsoft Edge to authenticate.</span></span> <span data-ttu-id="bc6ec-159">Internet Explorer 모드에서 중립 사이트로 이동한 경우에는 Internet Explorer 모드를 유지하여 인증을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-159">If navigate to a neutral site in Internet Explorer mode, then you want to stay in Internet Explorer mode to authenticate.</span></span>

<span data-ttu-id="bc6ec-160">사용하는 모든 SSO(또는 기타 중립) 사이트를 식별하고 이를 엔터프라이즈 사이트 목록에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-160">Identify any SSO (or other neutral) sites that you use and add these to your Enterprise Site List.</span></span>

### <span data-ttu-id="bc6ec-161">Internet Explorer를 기본 브라우저로 구성한 경우</span><span class="sxs-lookup"><span data-stu-id="bc6ec-161">If you've configured Internet Explorer as your default browser</span></span>

<span data-ttu-id="bc6ec-162">현재 Internet Explorer만 사용하는 경우 최신 웹 표준으로 업그레이드한 사이트와 여전히 Internet Explorer를 사용해야 하는 사이트를 모를 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-162">If you're currently only using Internet Explorer, you might not know which sites have upgraded to modern web standards and which still require Internet Explorer.</span></span> <span data-ttu-id="bc6ec-163">이러한 사이트를 찾아 엔터프라이즈 사이트 목록에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-163">You want to find these sites and add them to the Enterprise Site List.</span></span> <span data-ttu-id="bc6ec-164">이를 통해 Internet Explorer 모드를 필요로 하는 사이트에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-164">This lets you use Internet Explorer mode only on the sites that need it.</span></span>

> [!TIP]
> <span data-ttu-id="bc6ec-165">[엔터프라이즈 사이트 검색](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/collect-data-using-enterprise-site-discovery?redirectedfrom=MSDN) 도구를 사용하여 Internet Explorer 모드가 필요한 사이트를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-165">Use the [Enterprise Site Discovery](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/collect-data-using-enterprise-site-discovery?redirectedfrom=MSDN) tools to discover the sites that might need Internet Explorer mode.</span></span> <span data-ttu-id="bc6ec-166">Windows 10, Windows 8.1 또는 Windows 7에서 Windows Internet Explorer 8부터 Internet Explorer 11을 실행하는 컴퓨터에서 데이터를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-166">You can collect collect data on computers running Windows Internet Explorer 8 through Internet Explorer 11 on Windows 10, Windows 8.1, or Windows 7.</span></span>

### <span data-ttu-id="bc6ec-167">사이트 검색 데이터 분석</span><span class="sxs-lookup"><span data-stu-id="bc6ec-167">Analyze site discovery data</span></span>

<span data-ttu-id="bc6ec-168">사이트 데이터를 수집한 후에는 다음 4단계 프로세스를 통해 데이터를 분석하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-168">After you've collected site data, we recommend the following 4-step process to analyze the data:</span></span>

1. <span data-ttu-id="bc6ec-169">도메인별로 데이터를 정렬한 다음 URL로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-169">Sort the data by domain, and then by URL.</span></span>
2. <span data-ttu-id="bc6ec-170">Internet Explorer 모드를 구성할 "앱"의 경계를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-170">Define the boundaries of an "app" to configure for Internet Explorer mode.</span></span> <span data-ttu-id="bc6ec-171">앱을 정의하는 모든 사이트와 웹 컨트롤을 포함하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-171">You want to include all the sites and web controls that define the app.</span></span> <span data-ttu-id="bc6ec-172">하지만 앱을 너무 광범위하게 정의하여 추가 사이트와 컨트롤을 포함하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-172">But you don't want to include any extra sites and controls by defining the app too broadly.</span></span> <span data-ttu-id="bc6ec-173">일부 사이트는 "http://contoso.com/app1"처럼 단순할 수도 있고, 어떤 사이트는 여러 사이트 및 페이지를 정의해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-173">Some sites may be as simple as "http://contoso.com/app1" while others may require you to define multiple sites and pages.</span></span>
3. <span data-ttu-id="bc6ec-174">앱을 테스트하여 기본적으로 작동하지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-174">Test the app to verify that it doesn't work natively.</span></span> <span data-ttu-id="bc6ec-175">많은 사이트는 최신 브라우저를 감지할 때 최신 콘텐츠를 제공하며 Internet Explorer를 감지하는 경우에만 레거시 콘텐츠를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-175">Many sites will offer modern content when they detect a modern browser, and only offer legacy content when they detect Internet Explorer.</span></span>
4. <span data-ttu-id="bc6ec-176">테스트가 실패하는 경우 엔터프라이즈 사이트 목록에 앱을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-176">Add the app to your Enterprise Site list if it fails testing.</span></span>

   > [!NOTE]
   > <span data-ttu-id="bc6ec-177">가장 좋은 방법은 앱을 구성하는 모든 사이트를 그룹화하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-177">As a best practice, group all of the sites that comprise an app.</span></span> <span data-ttu-id="bc6ec-178">하나의 작업을 수행하는 데 사이트를 모두 사용해야 하고 두 사이트가 함께 업데이트되는 경향이 있는 경우에는 그룹화하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-178">If the sites all need to be used to accomplish one task, and if they tend to be updated together, that is a good indication that they should be grouped.</span></span> <span data-ttu-id="bc6ec-179">이렇게 하면 앱을 업그레이드할 때 Internet Explorer 모드에서 전체 사이트를 제거하고 해당 앱에 최신 브라우저를 사용하는 것이 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-179">This way, when you upgrade an app, it's easier to remove the entire site from Internet Explorer mode and start using a modern browser for that app.</span></span>

## <span data-ttu-id="bc6ec-180">채널 전략 결정</span><span class="sxs-lookup"><span data-stu-id="bc6ec-180">Determine your channel strategy</span></span>

<span data-ttu-id="bc6ec-181">Microsoft Edge는 [여러 채널](https://docs.microsoft.com/DeployEdge/microsoft-edge-channels)에서 릴리스됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-181">Microsoft Edge is released in [multiple channels](https://docs.microsoft.com/DeployEdge/microsoft-edge-channels).</span></span>

> [!NOTE]
> <span data-ttu-id="bc6ec-182">한 디바이스에 두 개 이상의 채널을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-182">You can install more than one channel on a device</span></span>

<span data-ttu-id="bc6ec-183">대부분의 디바이스에 안정 채널을 배포하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-183">The Stable Channel is what you will want to deploy to most devices.</span></span> <span data-ttu-id="bc6ec-184">그러나 여러 디바이스와 여러 채널을 포함하는 배포 전략을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-184">However, you should consider a deployment strategy that includes multiple devices and multiple channels.</span></span>

### <span data-ttu-id="bc6ec-185">여러 디바이스 및 채널</span><span class="sxs-lookup"><span data-stu-id="bc6ec-185">Multiple devices and channels</span></span>

<span data-ttu-id="bc6ec-186">베타 채널을 사용하도록 구성된 디바이스의 대표적인 하위 집합을 보유하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-186">We recommend having a representative subset of devices configured to use the Beta Channel.</span></span> <span data-ttu-id="bc6ec-187">이렇게 하면 예정된 브라우저에 대한 변경 내용을 미리 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-187">This lets you preview upcoming changes to the browser.</span></span> <span data-ttu-id="bc6ec-188">이러한 변경 사항이 최종 사용자 또는 앱에 영향을 줄 것인지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-188">You can see if these changes are going to affect your end users or apps.</span></span>

<span data-ttu-id="bc6ec-189">또한 개발자 채널(또는 Canary 채널)을 웹 개발자와 같은 일부 역할에 사용할 수 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-189">You might also want to make the Dev Channel (or even the Canary Channel) available to some roles, such as web developers.</span></span> <span data-ttu-id="bc6ec-190">더 유동적이며 빠르게 변화하는 채널의 일부 디바이스를 대상으로 할지, 또는 이러한 채널을 사용자가 설치 여부를 선택할 수 있도록 할지 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-190">Consider whether you would like to target some devices with more fluid and rapidly changing channels, or simply make these channels available for users to opt to install.</span></span>

<span data-ttu-id="bc6ec-191">디바이스에 여러 채널을 설치할 수 있으므로 시험판 채널을 설치하기로 결정한 사용자에 대한 테스트 위험을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-191">Because it's possible to install multiple channels on a device, you can mitigate the risk of testing for users who have opted to install a pre-release channel.</span></span> <span data-ttu-id="bc6ec-192">예를 들어, 베타 채널을 사용하는 사용자가 있고 문제가 발생한 경우 안정 채널로 전환하여 작업을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-192">For example, if you have a user who's using the Beta Channel, and there's a problem, they can switch to the Stable Channel and continue working.</span></span> <span data-ttu-id="bc6ec-193">문제를 해결할 수 있을 때까지 이를 차단 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-193">This unblocks them until the issue can be fixed.</span></span>

> [!NOTE]
> <span data-ttu-id="bc6ec-194">사용자가 동기화를 사용하도록 설정한 경우 해당 구성은 채널 간에 동기화되므로 채널 간에 더욱 쉽게 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-194">If the user enabled Sync, then their configuration will sync across channels, making it even easier to transition between channels.</span></span>

## <span data-ttu-id="bc6ec-195">정책 정의 및 구성</span><span class="sxs-lookup"><span data-stu-id="bc6ec-195">Define and configure policies</span></span>

<span data-ttu-id="bc6ec-196">엔터프라이즈 사이트 목록을 만든 후 Microsoft Edge와 함께 배포할 정책을 파악하고 구성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-196">After you've created your Enterprise Site List, we recommend identifying and configuring the policies that you intend to deploy with Microsoft Edge.</span></span> <span data-ttu-id="bc6ec-197">이렇게 하면 테스트를 수행할 때 이러한 정책이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-197">This ensures that these policies are applied when you perform your testing.</span></span>

<span data-ttu-id="bc6ec-198">먼저, 사용자에게 제공하려는 첫 실행 환경을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-198">First, consider the first-run experience you want your users to have.</span></span> <span data-ttu-id="bc6ec-199">현재 브라우저에서 설정을 자동으로 가져오려면 [AutoImportAtFirstRun](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#autoimportatfirstrun)에 대한 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-199">If you want to automatically import settings from the current browser, configure the policy for [AutoImportAtFirstRun](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#autoimportatfirstrun).</span></span>

<span data-ttu-id="bc6ec-200">보안 정책의 경우 Microsoft Edge 보안 기준으로 시작하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-200">For security policies, we recommend starting with the Microsoft Edge Security Baseline.</span></span> <span data-ttu-id="bc6ec-201">보안 기준은 [권장 보안 구성 기준 설정](https://techcommunity.microsoft.com/t5/Microsoft-Security-Baselines/Security-baseline-DRAFT-for-Chromium-based-Microsoft-Edge/ba-p/949991)을 사용하거나 [Microsoft Intune](https://docs.microsoft.com/intune/protect/security-baseline-settings-edge)을 사용하여 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-201">The Security Baseline can be applied using the [recommended security configuration baseline settings](https://techcommunity.microsoft.com/t5/Microsoft-Security-Baselines/Security-baseline-DRAFT-for-Chromium-based-Microsoft-Edge/ba-p/949991) or by using [Microsoft Intune](https://docs.microsoft.com/intune/protect/security-baseline-settings-edge).</span></span>

<span data-ttu-id="bc6ec-202">다른 정책의 경우 [Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policies) 및 [Microsoft Edge 업데이트](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)에 대한 정책 구성을 검토하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-202">For other policies, we recommend reviewing the policy configurations for [Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policies) and [Microsoft Edge Updates](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies).</span></span>

### <span data-ttu-id="bc6ec-203">업데이트 전략 및 정책 정의</span><span class="sxs-lookup"><span data-stu-id="bc6ec-203">Define your update strategy and policies</span></span>

<span data-ttu-id="bc6ec-204">또한 Microsoft Edge를 배포한 후 업데이트를 수행할 방법을 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-204">You also want to determine how you want to do updates after you deploy Microsoft Edge:</span></span>

- <span data-ttu-id="bc6ec-205">**Microsoft Edge가 자동으로 업데이트하도록 허용합니다**(기본값).</span><span class="sxs-lookup"><span data-stu-id="bc6ec-205">**Allow Microsoft Edge to update itself** (default).</span></span> <span data-ttu-id="bc6ec-206">Microsoft Edge의 자동 업데이트를 허용하도록 선택하면 배포한 채널에 의해 결정된 속도로 Microsoft Edge가 자동으로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-206">If you choose to allow automatic updates of Microsoft Edge, then Microsoft Edge will automatically update itself at the pace determined by the channel(s) you deployed.</span></span>
- <span data-ttu-id="bc6ec-207">**사용자가 원하는 대로 Microsoft Edge를 업데이트합니다**.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-207">**Update Microsoft Edge at your own pace**.</span></span> <span data-ttu-id="bc6ec-208">업데이트가 배포되는 시기를 명시적으로 제어하려는 경우 자동 업데이트를 사용하지 않도록 설정하고 직접 배포할 수 있습니다([업데이트 정책 참조](https://docs.microsoft.com/DeployEdge/microsoft-edge-update-policies)를 참조). 자동 업데이트를 사용하지 않도록 설정한 후 다음 도구 중 하나를 사용하여 각 채널에 대한 업데이트를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-208">If you prefer to have explicit control over when updates are deployed, you can disable automatic updates and deploy it yourself (see the [Update Policy reference](https://docs.microsoft.com/DeployEdge/microsoft-edge-update-policies).) After you disable automatic updates you can deploy updates for each channel using one of the following tools:</span></span>

- [<span data-ttu-id="bc6ec-209">Intune</span><span class="sxs-lookup"><span data-stu-id="bc6ec-209">Intune</span></span>](https://docs.microsoft.com/intune/apps/apps-windows-edge?toc=https://docs.microsoft.com/DeployEdge/toc.json&bc=https://docs.microsoft.com/DeployEdge/breadcrumb/toc.json)
- [<span data-ttu-id="bc6ec-210">Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="bc6ec-210">Configuration Manager</span></span>](https://docs.microsoft.com/DeployEdge/deploy-edge-with-configuration-manager)
- <span data-ttu-id="bc6ec-211">선택한 배포 도구.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-211">the deployment tool of your choice.</span></span>

<span data-ttu-id="bc6ec-212">업데이트 전략에 관계없이 고리 형태의 배포 전략을 활용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-212">Regardless of your update strategy, we recommend leveraging a ringed deployment strategy.</span></span> <span data-ttu-id="bc6ec-213">자동 업데이트를 사용하면 베타 채널을 실행하는 사용자를 대표하는 샘플을 확보하여 안정 채널이 되는 채널과 관련한 문제를 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-213">With automatic updates, this means having a representative sample of users running the Beta Channel, to identify issues with what will become the Stable Channel.</span></span> <span data-ttu-id="bc6ec-214">수동 업데이트를 사용하면 안정 채널 빌드가 새로 릴리스된 후 파일럿 그룹에 대한 추가 유효성 검사도 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-214">With manual updates, this might also include additional validation of a pilot group after a new Stable Channel build is released.</span></span> <span data-ttu-id="bc6ec-215">그 다음에는 광범위한 배포를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-215">This is followed by broad deployment.</span></span>

>[!NOTE]
><span data-ttu-id="bc6ec-216">Microsoft Edge 지원은 각 채널의 최신 Microsoft Edge 버전에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-216">Microsoft Edge support will only apply to the most recent version of Microsoft Edge in each channel</span></span>

## <span data-ttu-id="bc6ec-217">앱 호환성 테스트 수행</span><span class="sxs-lookup"><span data-stu-id="bc6ec-217">Do app compatibility testing</span></span>

<span data-ttu-id="bc6ec-218">Microsoft Edge에 대한 응용 프로그램 호환성은 매우 높기 때문에 Microsoft는 다음과 같은 호환성 약속을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-218">Application compatibility for Microsoft Edge is extremely high - so high that Microsoft provides the following compatibility promises:</span></span>

1. <span data-ttu-id="bc6ec-219">Microsoft Edge *버전 45 이하*에서 작동하는 경우 Microsoft Edge *버전 77 이상*에서도 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-219">If it works on Microsoft Edge *version 45 and earlier*, it will work on Microsoft Edge *version 77 and later*.</span></span>
2. <span data-ttu-id="bc6ec-220">Internet Explorer에서 작동하는 경우 Internet Explorer 모드에서도 Microsoft Edge가 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-220">If it works on Internet Explorer, it will work on Microsoft Edge in Internet Explorer mode.</span></span>
3. <span data-ttu-id="bc6ec-221">Google Chrome에서 작동하는 경우 Microsoft Edge에서도 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-221">If it works on Google Chrome, it will work on Microsoft Edge.</span></span>

<span data-ttu-id="bc6ec-222">호환성 약속을 충족하지 못하는 애플리케이션이 있는 경우 [](https://www.microsoft.com/fasttrack/microsoft-365/desktop-app-assure)Microsoft App Assure[](https://www.microsoft.com/fasttrack/microsoft-365/desktop-app-assure)을(를) 사용하여 문제를 수정할 것을 약속합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-222">If you have an application where we don't meet our compatibility promise, then we stand behind the promise to fix it with [Microsoft App Assure](https://www.microsoft.com/fasttrack/microsoft-365/desktop-app-assure).</span></span>

### <span data-ttu-id="bc6ec-223">비즈니스 앱 테스트의 내부 라인</span><span class="sxs-lookup"><span data-stu-id="bc6ec-223">Internal line of business app testing</span></span>

<span data-ttu-id="bc6ec-224">호환성 약속에도 불구하고 많은 조직에서 규정 준수 또는 위험 관리 이유로 일부 애플리케이션의 유효성을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-224">Despite our compatibility promise, we know that many organizations must validate some applications for their compliance or risk management reasons.</span></span> <span data-ttu-id="bc6ec-225">이 방법은 매우 간단하지만 앱 테스트에서 체계적이며 엄격해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-225">Even though we expect this to be very straightforward, it's important to be organized and rigorous in app testing.</span></span>

<span data-ttu-id="bc6ec-226">다음 2가지 방법으로 앱 호환성 테스트를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-226">There are 2 ways to do app compatibility testing:</span></span>

1. <span data-ttu-id="bc6ec-227">랩 테스트.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-227">Lab testing.</span></span> <span data-ttu-id="bc6ec-228">특정 구성으로 엄격하게 제어된 환경에서 응용 프로그램의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-228">Applications are validated in a tightly controlled environment with specific configurations.</span></span>
2. <span data-ttu-id="bc6ec-229">파일럿 테스트.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-229">Pilot testing.</span></span> <span data-ttu-id="bc6ec-230">일상 업무 환경에서 자체 디바이스를 사용하여 제한 된 수의 사용자가 응용 프로그램의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-230">Applications are validated by a limited number of users in their daily work environment using their own devices.</span></span>

<span data-ttu-id="bc6ec-231">호환성 테스트에서 과도한 투자를 하지 않고 위험을 관리하기 위해 각 앱에 가장 적합한 방법을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-231">Choose the method that is most appropriate for each app,  to manage risk without over-investing in compatibility testing.</span></span>

### <span data-ttu-id="bc6ec-232">타사 앱 지원</span><span class="sxs-lookup"><span data-stu-id="bc6ec-232">Third party app support</span></span>

<span data-ttu-id="bc6ec-233">자체 비즈니스 앱 제품군 외에도 많은 조직에서 외부 소스에서 제공하는 앱을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-233">In addition to their own line of business apps, many organizations use apps provided by external sources.</span></span> <span data-ttu-id="bc6ec-234">[Microsoft Edge 준비](deploy-edge-ready-for-edge.md) 문서에는 조직 내에서 사용 중인 웹 응용 프로그램 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-234">The [Ready for Microsoft Edge](deploy-edge-ready-for-edge.md) article contains a list of web applications that may be in use within your organization.</span></span> <span data-ttu-id="bc6ec-235">이 목록에서는 Microsoft Edge와 함께 사용할 경우 해당 제품에 대한 공급자 지원 문에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-235">This list provides links to provider support statements for their products when used with Microsoft Edge.</span></span>

## <span data-ttu-id="bc6ec-236">파일럿 그룹에 Microsoft Edge 배포</span><span class="sxs-lookup"><span data-stu-id="bc6ec-236">Deploy Microsoft Edge to a pilot group</span></span>

<span data-ttu-id="bc6ec-237">정책을 정의하고 초기 앱 호환성 테스트를 완료했으면 파일럿 그룹에 배포할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-237">After you've defined your policies and have finished your initial app compatibility testing, you're ready to deploy to your pilot group.</span></span> <span data-ttu-id="bc6ec-238">다음 도구 중 하나를 사용하여 파일럿 그룹에 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-238">Deploy to your pilot group using one of the following tools:</span></span>

- <span data-ttu-id="bc6ec-239">[Windows용 Microsoft Intune](https://docs.microsoft.com/intune/apps/apps-windows-edge?toc=https://docs.microsoft.com/DeployEdge/toc.json&bc=https://docs.microsoft.com/DeployEdge/breadcrumb/toc.json), 또는 [macOS용 Microsoft Intune](https://docs.microsoft.com/intune/apps/apps-edge-macos?toc=https://docs.microsoft.com/DeployEdge/toc.json&bc=https://docs.microsoft.com/DeployEdge/breadcrumb/toc.json)</span><span class="sxs-lookup"><span data-stu-id="bc6ec-239">[Microsoft Intune for Windows](https://docs.microsoft.com/intune/apps/apps-windows-edge?toc=https://docs.microsoft.com/DeployEdge/toc.json&bc=https://docs.microsoft.com/DeployEdge/breadcrumb/toc.json), or [Microsoft Intune for macOS](https://docs.microsoft.com/intune/apps/apps-edge-macos?toc=https://docs.microsoft.com/DeployEdge/toc.json&bc=https://docs.microsoft.com/DeployEdge/breadcrumb/toc.json)</span></span>
- <span data-ttu-id="bc6ec-240">[Configuration Manager](https://docs.microsoft.com/DeployEdge/deploy-edge-with-configuration-manager).</span><span class="sxs-lookup"><span data-stu-id="bc6ec-240">[Configuration Manager](https://docs.microsoft.com/DeployEdge/deploy-edge-with-configuration-manager).</span></span>
- <span data-ttu-id="bc6ec-241">다른 관리 도구, [Microsoft Edge용 MSI 파일](https://www.microsoftedgeinsider.com/enterprise) 다운로드 및 배포.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-241">Another management tool, download and deploy the [MSI file for Microsoft Edge](https://www.microsoftedgeinsider.com/enterprise).</span></span>

## <span data-ttu-id="bc6ec-242">배포 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="bc6ec-242">Validate your deployment</span></span>

<span data-ttu-id="bc6ec-243">파일럿을 배포한 후 사용자에게서 받은 모든 피드백을 포착할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-243">After you deploy your pilot, you want to capture all the feedback you get from your users.</span></span>

- <span data-ttu-id="bc6ec-244">호환성에 대한 피드백을 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-244">Capture feedback on compatibility.</span></span> <span data-ttu-id="bc6ec-245">사이트를 검색하는 동안 식별되지 않은 엔터프라이즈 사이트 목록에 속하는 사이트를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-245">Identify sites that belong on the Enterprise Site List that weren't identified during site discovery.</span></span>
- <span data-ttu-id="bc6ec-246">정책 구성에 대한 피드백을 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-246">Capture feedback on the policy configuration.</span></span> <span data-ttu-id="bc6ec-247">사용자가 다음 보안 지침을 준수하면서 주요 기능을 사용하고 작업을 수행할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-247">Ensure that users can use key features and do their work while following security guidelines.</span></span>
- <span data-ttu-id="bc6ec-248">사용의 용이성과 새로운 기능에 대한 피드백을 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-248">Capture feedback on ease of use and new features.</span></span> <span data-ttu-id="bc6ec-249">사용자 질문에 따라 교육을 개발하고 제공해야 하는 모든 영역을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-249">Identify any areas where training should be developed and delivered based on user questions.</span></span>

## <span data-ttu-id="bc6ec-250">Microsoft Edge의 폭넓은 배포</span><span class="sxs-lookup"><span data-stu-id="bc6ec-250">Broad deployment of Microsoft Edge</span></span>

<span data-ttu-id="bc6ec-251">파일럿을 완료하고 파일럿에서 얻은 교훈을 사용하여 배포 계획을 업데이트한 후에는 모든 사용자에게 Microsoft Edge 전체 배포를 수행할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ec-251">After a finishing the pilot and updating your deployment plan with lessons learned from the pilot, you're ready to do a full deployment of Microsoft Edge to all your users.</span></span>  <span data-ttu-id="bc6ec-252">축하합니다!</span><span class="sxs-lookup"><span data-stu-id="bc6ec-252">Congratulations!</span></span>

## <span data-ttu-id="bc6ec-253">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bc6ec-253">See also</span></span>

- [<span data-ttu-id="bc6ec-254">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="bc6ec-254">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="bc6ec-255">비디오 - Microsoft Edge 배포</span><span class="sxs-lookup"><span data-stu-id="bc6ec-255">Video - Deploy Microsoft Edge</span></span>](microsoft-edge-video-deploy.md)
