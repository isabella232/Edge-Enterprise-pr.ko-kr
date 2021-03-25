---
title: Microsoft Edge 키오스크 모드 구성
ms.author: aguta
author: aguta
manager: srugh
ms.date: 03/16/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 키오스크 모드 기능 및 Microsoft Edge 키오스크 모드 옵션을 구성하는 방법에 대해 자세히 알아보세요.
ms.openlocfilehash: 9d76bfcaebeaf56e627a401cc4f0375bce9d17a3
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "11448132"
---
# <a name="configure-microsoft-edge-kiosk-mode"></a><span data-ttu-id="f40c9-103">Microsoft Edge 키오스크 모드 구성</span><span class="sxs-lookup"><span data-stu-id="f40c9-103">Configure Microsoft Edge kiosk mode</span></span>

<span data-ttu-id="f40c9-104">이 문서에서는 시험할 수 있는 Microsoft Edge 키오스크 모드 옵션을 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-104">This article describes how to configure Microsoft Edge kiosk mode options that you can pilot.</span></span> <span data-ttu-id="f40c9-105">또한 대상으로 하는 기능 로드맵도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-105">There's also a roadmap of features we're targeting.</span></span>

> [!NOTE]
> <span data-ttu-id="f40c9-106">이 문서는 Microsoft Edge 버전 87 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-106">This article applies to Microsoft Edge version 87 or later.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f40c9-107">[키오스크 모드 기능 사용](#use-kiosk-mode-features)에 제공된 명령줄 인수를 사용하여 Windows 10에서 Microsoft Edge 키오스크 모드 기능을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-107">Invoke Microsoft Edge kiosk mode features on Windows 10 using the command line arguments provided in [Use kiosk mode features](#use-kiosk-mode-features).</span></span>

## <a name="overview"></a><span data-ttu-id="f40c9-108">개요</span><span class="sxs-lookup"><span data-stu-id="f40c9-108">Overview</span></span>

<span data-ttu-id="f40c9-109">Microsoft Edge 키오스크 모드는 조직이 고객을 위해 최고의 환경을 만들고 관리하고 최상의 환경을 제공할 수 있도록 브라우저에 대한 두 가지 잠금 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-109">Microsoft Edge kiosk mode offers two lockdown experiences of the browser so organizations can create, manage, and provide the best experience for their customers.</span></span> <span data-ttu-id="f40c9-110">다음과 같은 잠금 환경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-110">The following lockdown experiences are available:</span></span>  

- <span data-ttu-id="f40c9-111">**디지털/대화형 서명 환경** - 특정 사이트를 전체 화면 모드로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-111">**Digital/Interactive Signage** experience - Displays a specific site in full-screen mode.</span></span>
- <span data-ttu-id="f40c9-112">**공개 검색** 환경 - 제한된 다중 탭 버전의 Microsoft Edge를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-112">**Public-Browsing** experience - Runs a limited multi-tab version of Microsoft Edge.</span></span>

<span data-ttu-id="f40c9-113">두 가지 환경 모두에서 사용자 데이터를 보호하는 Microsoft Edge InPrivate 세션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-113">Both experiences are running a Microsoft Edge InPrivate session, which protects user data.</span></span>

## <a name="set-up-microsoft-edge-kiosk-mode"></a><span data-ttu-id="f40c9-114">Microsoft Edge 키오스크 모드 설정</span><span class="sxs-lookup"><span data-stu-id="f40c9-114">Set up Microsoft Edge kiosk mode</span></span>

<span data-ttu-id="f40c9-115">초기 키오스크 모드 기능 집합은 Microsoft Edge 안정 채널 버전 87에서 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-115">An initial set of kiosk mode features is available to test with Microsoft Edge Stable Channel, version 87.</span></span> <span data-ttu-id="f40c9-116">Microsoft Edge(공식 안정 채널)에서 최신 [버전을 다운로드할 수 있습니다.](https://www.microsoft.com/edge)</span><span class="sxs-lookup"><span data-stu-id="f40c9-116">You can download the latest version from [Microsoft Edge (Official Stable Channel)](https://www.microsoft.com/edge).</span></span>

### <a name="kiosk-mode-supported-features"></a><span data-ttu-id="f40c9-117">키오스크 모드 지원 기능</span><span class="sxs-lookup"><span data-stu-id="f40c9-117">Kiosk mode supported features</span></span>

<span data-ttu-id="f40c9-118">다음 표에는 Microsoft Edge 및 Microsoft Edge 레거시에서 키오스크 모드로 지원되는 기능이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-118">The following table lists the features supported by kiosk mode in Microsoft Edge and Microsoft Edge Legacy.</span></span> <span data-ttu-id="f40c9-119">Microsoft Edge의 두 버전에서 이러한 기능이 어떻게 지원되는지를 비교하여 Microsoft Edge로 전환하기 위한 가이드로 이 표를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f40c9-119">Use this table as a guide to transitioning to Microsoft Edge by comparing how these features are supported in both versions of Microsoft Edge.</span></span>

|<span data-ttu-id="f40c9-120">기능</span><span class="sxs-lookup"><span data-stu-id="f40c9-120">Feature</span></span>|<span data-ttu-id="f40c9-121">디지털\대화형 서명</span><span class="sxs-lookup"><span data-stu-id="f40c9-121">Digital\Interactive Signage</span></span>|<span data-ttu-id="f40c9-122">공개 검색</span><span class="sxs-lookup"><span data-stu-id="f40c9-122">Public browsing</span></span>|<span data-ttu-id="f40c9-123">Microsoft Edge 버전 (이상에서 사용 가능)</span><span class="sxs-lookup"><span data-stu-id="f40c9-123">Available with Microsoft Edge version (and higher)</span></span>|<span data-ttu-id="f40c9-124">Microsoft Edge 레거시에서 사용 가능</span><span class="sxs-lookup"><span data-stu-id="f40c9-124">Available with Microsoft Edge Legacy</span></span>|
|-|-|-|-|-|
|<span data-ttu-id="f40c9-125">InPrivate 탐색</span><span class="sxs-lookup"><span data-stu-id="f40c9-125">InPrivate Navigation</span></span>|<span data-ttu-id="f40c9-126">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-126">Y</span></span>|<span data-ttu-id="f40c9-127">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-127">Y</span></span>|<span data-ttu-id="f40c9-128">89</span><span class="sxs-lookup"><span data-stu-id="f40c9-128">89</span></span>|<span data-ttu-id="f40c9-129">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-129">Y</span></span>|
|<span data-ttu-id="f40c9-130">비활성 상태로 재설정</span><span class="sxs-lookup"><span data-stu-id="f40c9-130">Reset on inactivity</span></span>|<span data-ttu-id="f40c9-131">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-131">Y</span></span>|<span data-ttu-id="f40c9-132">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-132">Y</span></span>|<span data-ttu-id="f40c9-133">89</span><span class="sxs-lookup"><span data-stu-id="f40c9-133">89</span></span>|<span data-ttu-id="f40c9-134">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-134">Y</span></span>|
|<span data-ttu-id="f40c9-135">[읽기 전용 주소](./microsoft-edge-policies.md#kioskaddressbareditingenabled)(정책)</span><span class="sxs-lookup"><span data-stu-id="f40c9-135">[Read only address bar](./microsoft-edge-policies.md#kioskaddressbareditingenabled) (policy)</span></span> |<span data-ttu-id="f40c9-136">N</span><span class="sxs-lookup"><span data-stu-id="f40c9-136">N</span></span>|<span data-ttu-id="f40c9-137">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-137">Y</span></span> |<span data-ttu-id="f40c9-138">89</span><span class="sxs-lookup"><span data-stu-id="f40c9-138">89</span></span>|<span data-ttu-id="f40c9-139">N</span><span class="sxs-lookup"><span data-stu-id="f40c9-139">N</span></span>|
|<span data-ttu-id="f40c9-140">[종료 시 다운로드 삭제](./microsoft-edge-policies.md#kioskdeletedownloadsonexit)(정책)</span><span class="sxs-lookup"><span data-stu-id="f40c9-140">[Delete downloads on exit](./microsoft-edge-policies.md#kioskdeletedownloadsonexit) (policy)</span></span>  | <span data-ttu-id="f40c9-141">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-141">Y</span></span>|<span data-ttu-id="f40c9-142">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-142">Y</span></span> |<span data-ttu-id="f40c9-143">89</span><span class="sxs-lookup"><span data-stu-id="f40c9-143">89</span></span>|<span data-ttu-id="f40c9-144">N</span><span class="sxs-lookup"><span data-stu-id="f40c9-144">N</span></span>|
|<span data-ttu-id="f40c9-145">F11 차단(전체 화면 입력/종료)</span><span class="sxs-lookup"><span data-stu-id="f40c9-145">F11 blocked (enter/exit full-screen)</span></span> | <span data-ttu-id="f40c9-146">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-146">Y</span></span> | <span data-ttu-id="f40c9-147">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-147">Y</span></span> | <span data-ttu-id="f40c9-148">89</span><span class="sxs-lookup"><span data-stu-id="f40c9-148">89</span></span> |<span data-ttu-id="f40c9-149">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-149">Y</span></span>|
|<span data-ttu-id="f40c9-150">F12 차단(개발자 도구 시작)</span><span class="sxs-lookup"><span data-stu-id="f40c9-150">F12 blocked (launch Developer Tools)</span></span> | <span data-ttu-id="f40c9-151">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-151">Y</span></span> | <span data-ttu-id="f40c9-152">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-152">Y</span></span> | <span data-ttu-id="f40c9-153">89</span><span class="sxs-lookup"><span data-stu-id="f40c9-153">89</span></span> |<span data-ttu-id="f40c9-154">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-154">Y</span></span>|
| <span data-ttu-id="f40c9-155">다중 탭 지원</span><span class="sxs-lookup"><span data-stu-id="f40c9-155">Multi tab support</span></span> | <span data-ttu-id="f40c9-156">N</span><span class="sxs-lookup"><span data-stu-id="f40c9-156">N</span></span>| <span data-ttu-id="f40c9-157">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-157">Y</span></span>| <span data-ttu-id="f40c9-158">89</span><span class="sxs-lookup"><span data-stu-id="f40c9-158">89</span></span>|<span data-ttu-id="f40c9-159">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-159">Y</span></span>|
|<span data-ttu-id="f40c9-160">[URL 지원 허용](./microsoft-edge-policies.md#urlallowlist) (정책)</span><span class="sxs-lookup"><span data-stu-id="f40c9-160">[Allow URL support](./microsoft-edge-policies.md#urlallowlist) (policy)</span></span>|<span data-ttu-id="f40c9-161">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-161">Y</span></span>|<span data-ttu-id="f40c9-162">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-162">Y</span></span>|<span data-ttu-id="f40c9-163">89</span><span class="sxs-lookup"><span data-stu-id="f40c9-163">89</span></span>|<span data-ttu-id="f40c9-164">N</span><span class="sxs-lookup"><span data-stu-id="f40c9-164">N</span></span>|
|<span data-ttu-id="f40c9-165">[URL 지원 차단](./microsoft-edge-policies.md#urlblocklist) (정책)</span><span class="sxs-lookup"><span data-stu-id="f40c9-165">[Block URL support](./microsoft-edge-policies.md#urlblocklist) (policy)</span></span>|<span data-ttu-id="f40c9-166">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-166">Y</span></span>|<span data-ttu-id="f40c9-167">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-167">Y</span></span>|<span data-ttu-id="f40c9-168">89</span><span class="sxs-lookup"><span data-stu-id="f40c9-168">89</span></span>|<span data-ttu-id="f40c9-169">N</span><span class="sxs-lookup"><span data-stu-id="f40c9-169">N</span></span>|
|<span data-ttu-id="f40c9-170">[홈 단추표시](./microsoft-edge-policies.md#showhomebutton) (정책)</span><span class="sxs-lookup"><span data-stu-id="f40c9-170">[Show home button](./microsoft-edge-policies.md#showhomebutton) (policy)</span></span>|<span data-ttu-id="f40c9-171">N</span><span class="sxs-lookup"><span data-stu-id="f40c9-171">N</span></span>|<span data-ttu-id="f40c9-172">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-172">Y</span></span>|<span data-ttu-id="f40c9-173">89</span><span class="sxs-lookup"><span data-stu-id="f40c9-173">89</span></span>|<span data-ttu-id="f40c9-174">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-174">Y</span></span>|
|<span data-ttu-id="f40c9-175">[즐겨찾기 관리](./microsoft-edge-policies.md#managedfavorites) (정책)</span><span class="sxs-lookup"><span data-stu-id="f40c9-175">[Manage favorites](./microsoft-edge-policies.md#managedfavorites) (policy)</span></span>|<span data-ttu-id="f40c9-176">N</span><span class="sxs-lookup"><span data-stu-id="f40c9-176">N</span></span>|<span data-ttu-id="f40c9-177">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-177">Y</span></span>|<span data-ttu-id="f40c9-178">89</span><span class="sxs-lookup"><span data-stu-id="f40c9-178">89</span></span>|<span data-ttu-id="f40c9-179">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-179">Y</span></span>|
|<span data-ttu-id="f40c9-180">[프린터](./microsoft-edge-policies.md#printingenabled) 사용(정책)</span><span class="sxs-lookup"><span data-stu-id="f40c9-180">[Enable printer](./microsoft-edge-policies.md#printingenabled) (policy)</span></span>|<span data-ttu-id="f40c9-181">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-181">Y</span></span>|<span data-ttu-id="f40c9-182">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-182">Y</span></span>|<span data-ttu-id="f40c9-183">89</span><span class="sxs-lookup"><span data-stu-id="f40c9-183">89</span></span>|<span data-ttu-id="f40c9-184">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-184">Y</span></span>|
|<span data-ttu-id="f40c9-185">[새 탭 페이지 URL 구성](./microsoft-edge-policies.md#newtabpagelocation) (정책)</span><span class="sxs-lookup"><span data-stu-id="f40c9-185">[Configure the new tab page URL](./microsoft-edge-policies.md#newtabpagelocation) (policy)</span></span>|<span data-ttu-id="f40c9-186">N</span><span class="sxs-lookup"><span data-stu-id="f40c9-186">N</span></span>|<span data-ttu-id="f40c9-187">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-187">Y</span></span>||<span data-ttu-id="f40c9-188">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-188">Y</span></span>|
|<span data-ttu-id="f40c9-189">세션 종료 단추 \*</span><span class="sxs-lookup"><span data-stu-id="f40c9-189">End session button \*</span></span> | <span data-ttu-id="f40c9-190">N</span><span class="sxs-lookup"><span data-stu-id="f40c9-190">N</span></span>| <span data-ttu-id="f40c9-191">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-191">Y</span></span>| <span data-ttu-id="f40c9-192">89</span><span class="sxs-lookup"><span data-stu-id="f40c9-192">89</span></span>|<span data-ttu-id="f40c9-193">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-193">Y</span></span>|
|<span data-ttu-id="f40c9-194">모든 내부 Microsoft Edge URL이 차단되며 *edge://downloads* 및 *edge://print*는 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-194">All internal Microsoft Edge URLs are blocked, except for *edge://downloads* and *edge://print*</span></span> |<span data-ttu-id="f40c9-195">N</span><span class="sxs-lookup"><span data-stu-id="f40c9-195">N</span></span>|<span data-ttu-id="f40c9-196">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-196">Y</span></span>|<span data-ttu-id="f40c9-197">89</span><span class="sxs-lookup"><span data-stu-id="f40c9-197">89</span></span>|<span data-ttu-id="f40c9-198">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-198">Y</span></span>|
| <span data-ttu-id="f40c9-199">Ctrl+N 차단(새 창 열기) \*</span><span class="sxs-lookup"><span data-stu-id="f40c9-199">CTRL+N blocked (open a new window) \*</span></span> | <span data-ttu-id="f40c9-200">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-200">Y</span></span> | <span data-ttu-id="f40c9-201">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-201">Y</span></span> | <span data-ttu-id="f40c9-202">89</span><span class="sxs-lookup"><span data-stu-id="f40c9-202">89</span></span> |<span data-ttu-id="f40c9-203">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-203">Y</span></span>|
| <span data-ttu-id="f40c9-204">Ctrl+T 차단(새 탭 열기)</span><span class="sxs-lookup"><span data-stu-id="f40c9-204">CTRL+T blocked (open new tab)</span></span> |<span data-ttu-id="f40c9-205">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-205">Y</span></span> | <span data-ttu-id="f40c9-206">N</span><span class="sxs-lookup"><span data-stu-id="f40c9-206">N</span></span> | <span data-ttu-id="f40c9-207">89</span><span class="sxs-lookup"><span data-stu-id="f40c9-207">89</span></span> |<span data-ttu-id="f40c9-208">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-208">Y</span></span>|
|<span data-ttu-id="f40c9-209">설정 및 추가(...)에는 필요한 옵션만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-209">Settings and more (...) will display only the required options</span></span>  |<span data-ttu-id="f40c9-210">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-210">Y</span></span> |<span data-ttu-id="f40c9-211">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-211">Y</span></span> |<span data-ttu-id="f40c9-212">89</span><span class="sxs-lookup"><span data-stu-id="f40c9-212">89</span></span> |<span data-ttu-id="f40c9-213">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-213">Y</span></span>|
|<span data-ttu-id="f40c9-214">브라우저에서 다른 응용 프로그램 실행 제한</span><span class="sxs-lookup"><span data-stu-id="f40c9-214">Restrict the launch of other applications from the browser</span></span>|<span data-ttu-id="f40c9-215">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-215">Y</span></span>|<span data-ttu-id="f40c9-216">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-216">Y</span></span>|<span data-ttu-id="f40c9-217">90/91</span><span class="sxs-lookup"><span data-stu-id="f40c9-217">90/91</span></span>|<span data-ttu-id="f40c9-218">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-218">Y</span></span>|
|<span data-ttu-id="f40c9-219">UI 인쇄 설정 잠금</span><span class="sxs-lookup"><span data-stu-id="f40c9-219">UI print settings lockdown</span></span>|<span data-ttu-id="f40c9-220">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-220">Y</span></span>|<span data-ttu-id="f40c9-221">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-221">Y</span></span>|<span data-ttu-id="f40c9-222">90/91</span><span class="sxs-lookup"><span data-stu-id="f40c9-222">90/91</span></span>|<span data-ttu-id="f40c9-223">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-223">Y</span></span>|
|<span data-ttu-id="f40c9-224">[새 탭 페이지를 홈 페이지로 설정](./microsoft-edge-policies.md#homepageisnewtabpage)(정책)</span><span class="sxs-lookup"><span data-stu-id="f40c9-224">[Set the new tab page as the home page](./microsoft-edge-policies.md#homepageisnewtabpage) (policy)</span></span>|-|-|<span data-ttu-id="f40c9-225">TBD</span><span class="sxs-lookup"><span data-stu-id="f40c9-225">TBD</span></span>|<span data-ttu-id="f40c9-226">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-226">Y</span></span>|

> [!NOTE]
> <span data-ttu-id="f40c9-227">"\*" 뒤에 오는 기능은 할당된 액세스 단일 앱 시나리오에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-227">Features followed by "\*" are only enabled in an assigned access single app scenario.</span></span>

## <a name="use-kiosk-mode-features"></a><span data-ttu-id="f40c9-228">키오스크 모드 기능 사용</span><span class="sxs-lookup"><span data-stu-id="f40c9-228">Use kiosk mode features</span></span>

<span data-ttu-id="f40c9-229">디지털/대화형 간판 및 공개 검색에 대한 다음 Windows 10 명령줄 옵션을 사용하여 Microsoft Edge 키오스크 모드 기능을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-229">Microsoft Edge kiosk mode features can be invoked with the following Windows 10 command line options for Digital/Interactive signage and Public browsing.</span></span>

### <a name="kiosk-mode-digitalinteractive-signage"></a><span data-ttu-id="f40c9-230">키오스크 모드 디지털/대화형 간판</span><span class="sxs-lookup"><span data-stu-id="f40c9-230">Kiosk mode Digital/Interactive signage</span></span>
 
```
msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen
```

### <a name="kiosk-mode-public-browsing"></a><span data-ttu-id="f40c9-231">키오스크 모드 공개 검색</span><span class="sxs-lookup"><span data-stu-id="f40c9-231">Kiosk mode Public browsing</span></span>

```
msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing
```

### <a name="additional-command-line-options"></a><span data-ttu-id="f40c9-232">추가 명령줄 옵션</span><span class="sxs-lookup"><span data-stu-id="f40c9-232">Additional command line options</span></span>

- <span data-ttu-id="f40c9-233">**--no-first-run**: 첫 번째 Microsoft Edge 실행 환경을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-233">**--no-first-run**: Disable the first Microsoft Edge run experience.</span></span>

   ```
  msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen --no-first-run
  ```

  ```
  msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing --no-first-run
  ```

- <span data-ttu-id="f40c9-234">**--kiosk-idle-timeout-minutes=**: Microsoft Edge 키오스크 모드가 사용자 세션을 다시 설정하기 전에 마지막 사용자 활동에서 시간을 분 단위로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-234">**--kiosk-idle-timeout-minutes=**: Change the time (in minutes) from the last user activity before Microsoft Edge kiosk mode resets the user's session.</span></span> <span data-ttu-id="f40c9-235">다음 예제의 "값"을 분 수로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-235">Replace "value" in the next example with the number of minutes.</span></span>

   ```
   --kiosk-idle-timeout-minutes=value
   ``` 
   <span data-ttu-id="f40c9-236">다음 "값"이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-236">The following "values" are supported:</span></span>

     - <span data-ttu-id="f40c9-237">기본값(분)</span><span class="sxs-lookup"><span data-stu-id="f40c9-237">Default values (in minutes)</span></span>
       - <span data-ttu-id="f40c9-238">전체 화면 - 0(꺼짐)</span><span class="sxs-lookup"><span data-stu-id="f40c9-238">Full screen - 0 (turned off)</span></span>
       - <span data-ttu-id="f40c9-239">공개 탐색 - 5분</span><span class="sxs-lookup"><span data-stu-id="f40c9-239">Public browsing - 5 minutes</span></span>
    - <span data-ttu-id="f40c9-240">허용되는 값</span><span class="sxs-lookup"><span data-stu-id="f40c9-240">Allowed values</span></span>
      - <span data-ttu-id="f40c9-241">0 - 타이머가 꺼집니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-241">0 - turns off the timer</span></span>
      - <span data-ttu-id="f40c9-242">1~1440분 동안 유휴 타이머에서 재설정</span><span class="sxs-lookup"><span data-stu-id="f40c9-242">1-1440 minutes for reset on idle timer</span></span>


    ```
    msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen --kiosk-idle-timeout-minutes=1
   ```

   ```
   msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing --kiosk-idle-timeout-minutes=1
   ```

## <a name="support-policies-for-kiosk-mode"></a><span data-ttu-id="f40c9-243">키오스크 모드에 대한 지원 정책</span><span class="sxs-lookup"><span data-stu-id="f40c9-243">Support policies for kiosk mode</span></span>

<span data-ttu-id="f40c9-244">다음 표에 나열된 Microsoft Edge 정책을 사용하여 구성한 Microsoft Edge 키오스크 모드 유형에 대한 키오스크 환경을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-244">Use any of the Microsoft Edge policies listed in the following table to enhance the kiosk experience for the Microsoft Edge kiosk mode type you configure.</span></span> <span data-ttu-id="f40c9-245">이러한 정책에 대한 자세한 내용은 [Microsoft Edge - 브라우저 정책 참조를 참조하세요.](./microsoft-edge-policies.md)</span><span class="sxs-lookup"><span data-stu-id="f40c9-245">To learn more about these policies, see [Microsoft Edge – Browser policy reference](./microsoft-edge-policies.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f40c9-246">정책 구성은 다음 표에 나열된 정책으로 제한되지는 않습니다. 그러나 키오스크 모드 기능에 부정적인 영향을 주지 않도록 추가 정책을 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-246">Policy configuration isn't limited to the policies listed in the following table, however additional policies should be tested to ensure that kiosk mode functionality isn't negatively affected.</span></span>

|<span data-ttu-id="f40c9-247">그룹 정책</span><span class="sxs-lookup"><span data-stu-id="f40c9-247">Group policy</span></span>|<span data-ttu-id="f40c9-248">디지털\대화형 간판</span><span class="sxs-lookup"><span data-stu-id="f40c9-248">Digital\Interactive signage</span></span>|<span data-ttu-id="f40c9-249">공개 검색 단일 앱</span><span class="sxs-lookup"><span data-stu-id="f40c9-249">Public browsing single-app</span></span>|
|--|--|--|
|[<span data-ttu-id="f40c9-250">인쇄</span><span class="sxs-lookup"><span data-stu-id="f40c9-250">Printing</span></span>](./microsoft-edge-policies.md#printing-policies) | <span data-ttu-id="f40c9-251">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-251">Y</span></span>|<span data-ttu-id="f40c9-252">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-252">Y</span></span> |
|[<span data-ttu-id="f40c9-253">HomePageLocation</span><span class="sxs-lookup"><span data-stu-id="f40c9-253">HomePageLocation</span></span>](./microsoft-edge-policies.md#homepagelocation) |<span data-ttu-id="f40c9-254">N</span><span class="sxs-lookup"><span data-stu-id="f40c9-254">N</span></span> | <span data-ttu-id="f40c9-255">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-255">Y</span></span>|
|[<span data-ttu-id="f40c9-256">ShowHomeButton</span><span class="sxs-lookup"><span data-stu-id="f40c9-256">ShowHomeButton</span></span>](./microsoft-edge-policies.md#showhomebutton) |<span data-ttu-id="f40c9-257">N</span><span class="sxs-lookup"><span data-stu-id="f40c9-257">N</span></span> | <span data-ttu-id="f40c9-258">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-258">Y</span></span>|
|[<span data-ttu-id="f40c9-259">NewTabPageLocation</span><span class="sxs-lookup"><span data-stu-id="f40c9-259">NewTabPageLocation</span></span>](./microsoft-edge-policies.md#newtabpagelocation) |<span data-ttu-id="f40c9-260">N</span><span class="sxs-lookup"><span data-stu-id="f40c9-260">N</span></span> |<span data-ttu-id="f40c9-261">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-261">Y</span></span> |
|[<span data-ttu-id="f40c9-262">FavoritesBarEnabled</span><span class="sxs-lookup"><span data-stu-id="f40c9-262">FavoritesBarEnabled</span></span>](./microsoft-edge-policies.md#favoritesbarenabled) |<span data-ttu-id="f40c9-263">N</span><span class="sxs-lookup"><span data-stu-id="f40c9-263">N</span></span> |<span data-ttu-id="f40c9-264">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-264">Y</span></span> |
|[<span data-ttu-id="f40c9-265">URLAllowlist</span><span class="sxs-lookup"><span data-stu-id="f40c9-265">URLAllowlist</span></span>](./microsoft-edge-policies.md#urlallowlist) |<span data-ttu-id="f40c9-266">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-266">Y</span></span> |<span data-ttu-id="f40c9-267">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-267">Y</span></span> |
|[<span data-ttu-id="f40c9-268">URLBlocklist</span><span class="sxs-lookup"><span data-stu-id="f40c9-268">URLBlocklist</span></span>](./microsoft-edge-policies.md#urlblocklist) |<span data-ttu-id="f40c9-269">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-269">Y</span></span> | <span data-ttu-id="f40c9-270">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-270">Y</span></span>|
|[<span data-ttu-id="f40c9-271">ManagedSearchEngines</span><span class="sxs-lookup"><span data-stu-id="f40c9-271">ManagedSearchEngines</span></span>](./microsoft-edge-policies.md#managedsearchengines) |<span data-ttu-id="f40c9-272">N</span><span class="sxs-lookup"><span data-stu-id="f40c9-272">N</span></span> | <span data-ttu-id="f40c9-273">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-273">Y</span></span>|
|[<span data-ttu-id="f40c9-274">UserFeedbackAllowed</span><span class="sxs-lookup"><span data-stu-id="f40c9-274">UserFeedbackAllowed</span></span>](./microsoft-edge-policies.md#userfeedbackallowed) |<span data-ttu-id="f40c9-275">N</span><span class="sxs-lookup"><span data-stu-id="f40c9-275">N</span></span> | <span data-ttu-id="f40c9-276">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-276">Y</span></span>|
|[<span data-ttu-id="f40c9-277">VerticalTabsAllowed</span><span class="sxs-lookup"><span data-stu-id="f40c9-277">VerticalTabsAllowed</span></span>](./microsoft-edge-policies.md#verticaltabsallowed) | <span data-ttu-id="f40c9-278">N</span><span class="sxs-lookup"><span data-stu-id="f40c9-278">N</span></span>|<span data-ttu-id="f40c9-279">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-279">Y</span></span> |
|[<span data-ttu-id="f40c9-280">SmartScreen 설정</span><span class="sxs-lookup"><span data-stu-id="f40c9-280">SmartScreen settings</span></span>](./microsoft-edge-policies.md#smartscreen-settings-policies) |<span data-ttu-id="f40c9-281">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-281">Y</span></span> |<span data-ttu-id="f40c9-282">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-282">Y</span></span> |
|[<span data-ttu-id="f40c9-283">EdgeCollectionsEnabled</span><span class="sxs-lookup"><span data-stu-id="f40c9-283">EdgeCollectionsEnabled</span></span>](./microsoft-edge-policies.md#edgecollectionsenabled)|<span data-ttu-id="f40c9-284">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-284">Y</span></span>|<span data-ttu-id="f40c9-285">Y</span><span class="sxs-lookup"><span data-stu-id="f40c9-285">Y</span></span>|

## <a name="microsoft-edge-with-assigned-access"></a><span data-ttu-id="f40c9-286">할당된 액세스 권한이 있는 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f40c9-286">Microsoft Edge with assigned access</span></span>

### <a name="single-app-kiosk"></a><span data-ttu-id="f40c9-287">단일 앱 키오스크</span><span class="sxs-lookup"><span data-stu-id="f40c9-287">Single app kiosk</span></span>

<span data-ttu-id="f40c9-288">Microsoft Edge는 현재 디지털/대화형 간판 및 공개 검색과 같은 잠금 환경을 통해 단일 앱이 할당된 액세스에 대해 동일한 Microsoft Edge 레거시 키오스크 모드 유형의 하위 집합을 지원하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-288">Microsoft Edge currently supports a subset of the same Microsoft Edge Legacy kiosk mode types for single-app assigned access with the following lockdown experiences: Digital/Interactive signage, and Public-browsing.</span></span>  

<span data-ttu-id="f40c9-289">할당된 액세스 단일 앱이 있는 Microsoft Edge 키오스크 모드는 현재 최신 [Windows 10 Insider Preview 빌드](https://insider.windows.com/), 버전 20215 이상 및  [Microsoft Edge Beta 채널](https://www.microsoftedgeinsider.com/download) 버전 89 이상에서 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-289">Microsoft Edge kiosk mode with assigned access single app is currently available for testing with the latest [Windows 10 Insider Preview Build](https://insider.windows.com/), version 20215 or higher, and with the [Microsoft Edge Beta Channel](https://www.microsoftedgeinsider.com/download), version 89 or higher.</span></span>

**<span data-ttu-id="f40c9-290">Windows Insiders 미리 보기를 얻으려면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="f40c9-290">How do I get the Windows Insiders preview?</span></span>**

<span data-ttu-id="f40c9-291">PC에 Windows 10 Insider Preview 빌드를 설치하려면  [Windows 10 Insider Preview 빌드 시작](/windows-insider/get-started)에 있는 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="f40c9-291">To install a Windows 10 Insider Preview Build on a PC, follow the instructions in [Getting started with Windows 10 Insider Preview Builds](/windows-insider/get-started).</span></span>

### <a name="multi-app-kiosk"></a><span data-ttu-id="f40c9-292">복수 앱 키오스크</span><span class="sxs-lookup"><span data-stu-id="f40c9-292">Multi-app kiosk</span></span>

<span data-ttu-id="f40c9-293">Microsoft Edge는 Windows 10에서 [다중 앱이 할당된 액세스](/windows/configuration/lock-down-windows-10-to-specific-apps)로 실행할 수 있으며, 이는 레거시 Microsoft Edge "일반 검색" 키오스크 모드 유형에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-293">Microsoft Edge can be run with [multi-app assigned access](/windows/configuration/lock-down-windows-10-to-specific-apps) on Windows 10, which is the equivalent of Microsoft Edge Legacy "Normal browsing" kiosk mode type.</span></span> <span data-ttu-id="f40c9-294">다중 앱이 할당된 액세스로 Microsoft Edge를 구성하기 위해 다중 앱 키오스크를 설정하는 방법에 대한 [지침을 따릅니다.](/windows/configuration/lock-down-windows-10-to-specific-apps)</span><span class="sxs-lookup"><span data-stu-id="f40c9-294">To configure Microsoft Edge with multi-app assigned access, follow the instructions on how to [Set up a multi-app kiosk](/windows/configuration/lock-down-windows-10-to-specific-apps).</span></span> <span data-ttu-id="f40c9-295">(Microsoft Edge 안정 채널에 대한 AUMID는 **MSEdge**입니다).</span><span class="sxs-lookup"><span data-stu-id="f40c9-295">(The AUMID for the Microsoft Edge Stable channel is **MSEdge**).</span></span>

<span data-ttu-id="f40c9-296">다중 앱이 할당된 액세스 권한이 있는 Microsoft Edge를 사용하는 경우 Microsoft Edge 브라우저 정책을 사용하여 고유한 요구 사항을 충족하도록 검색 환경을 구성하도록[Microsoft Edge](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-policies) 키오스크를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-296">When using Microsoft Edge with multi-app assigned access, you can configure Microsoft Edge kiosk to use the[Microsoft Edge browser policies](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-policies) to configure the browsing experience to meet your unique requirements.</span></span>

### <a name="configure-using-windows-settings"></a><span data-ttu-id="f40c9-297">Windows 설정을 사용하여 구성</span><span class="sxs-lookup"><span data-stu-id="f40c9-297">Configure using Windows Settings</span></span>

<span data-ttu-id="f40c9-298">Windows 설정은 한두 개의 단일 앱 키오스크 장치를 설정하는 가장 간단한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-298">Windows Settings is the simplest way to set up one or two single-app kiosk devices.</span></span> <span data-ttu-id="f40c9-299">다음 단계를 사용하여 단일 앱 키오스크 컴퓨터를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-299">Use the following steps to set up a single-app kiosk computer.</span></span>

1. <span data-ttu-id="f40c9-300">최신 Windows 10 Insider Preview 버전 20215 이상을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-300">Install the latest Windows 10 Insider Preview, version 20215 or higher.</span></span> <span data-ttu-id="f40c9-301">[Windows 10 Insider Preview 빌드 시작](/windows-insider/get-started)에 있는 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="f40c9-301">Follow the instructions in [Getting started with Windows 10 Insider Preview Builds](/windows-insider/get-started).</span></span>
2. <span data-ttu-id="f40c9-302">최신 기능을 테스트하기 위해 최신 [Microsoft Edge Beta 채널](https://www.microsoftedgeinsider.com/download) 버전 89 이상을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-302">To test the latest features, you can download the latest [Microsoft Edge Beta channel](https://www.microsoftedgeinsider.com/download), version 89 or higher.</span></span>
3. <span data-ttu-id="f40c9-303">키오스크 컴퓨터에서 Windows 설정을 열고 검색 필드에 "키오스크"를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-303">On the kiosk computer, open Windows Settings, and type "kiosk" in the search field.</span></span> <span data-ttu-id="f40c9-304"> *\*키오스크 설정(할당된 액세스)** 을 선택하면 다음 스크린샷에서 키오스크를 만들 수 있는 대화 상자를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-304">Select  **Set up a kiosk (assigned access)**, shown in the next screenshot to open the dialog for creating the kiosk.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-1-assigned-access.png" alt-text="할당된 액세스 권한을 사용하여 키오스크 설정":::

4. <span data-ttu-id="f40c9-306">**키오스크 설정**  페이지에서  **시작**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-306">On the **Set up a kiosk** page, click **Get started**.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-2-get-started.png" alt-text="키오스크 - 시작":::

5. <span data-ttu-id="f40c9-308">이름을 입력하여 새 키오스크 계정을 만들거나 채워진 드롭다운 목록에서 기존 계정을 선택하고  **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-308">Type a name to create a new kiosk account or choose an existing account from the populated dropdown list and then click **Next**.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-3-create-account.png" alt-text="키오스크 모드 - 계정 만들기":::

6. <span data-ttu-id="f40c9-310">**키오스크 앱 선택** 페이지에서 **Microsoft Edge**를 선택한 후  **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-310">On the **Choose a kiosk app** page, select **Microsoft Edge** and then click **Next**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f40c9-311">이는 Microsoft Edge Dev, 베타 및 Stable 채널에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-311">This only applies to Microsoft Edge Dev, Beta, and Stable channels.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-4-pick-app.png" alt-text="키오스크 모드 - 앱 선택":::

7. <span data-ttu-id="f40c9-313">키오스크 모드로 실행할 때 Microsoft Edge가 표시되는 방법에 대해 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-313">Pick one of the following options for how Microsoft Edge displays when running in kiosk mode:</span></span>

   - <span data-ttu-id="f40c9-314">디지털/대화형 간판 설계 - Microsoft Edge를 실행하며 전체 화면 모드로 특정 사이트를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-314">Digital/Interactive signage - Displays a specific site in full-screen mode, running Microsoft Edge.</span></span>
   - <span data-ttu-id="f40c9-315">공용 브라우저 - 제한된 다중 탭 버전의 Microsoft Edge를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-315">Public browser - Runs a limited multi-tab version of Microsoft Edge.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-5a-digital-sign.png" alt-text="키오스크 모드 디스플레이 - 전체 화면 디지털 기호":::

8. <span data-ttu-id="f40c9-317"> *\*다음*\*을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-317">Select **Next**.</span></span>
9. <span data-ttu-id="f40c9-318">키오스크 시작 시 로드할 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-318">Type the URL to load when the kiosk launches.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-6-enter-url.png" alt-text="키오스크 모드 - URL 입력":::

10. <span data-ttu-id="f40c9-320">대기 시간에 대한 기본값 5분을 수용하거나 직접 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-320">Accept the default value of 5 minutes for the idle time or provide a value of your own.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-7-enter-idle-time.png" alt-text="키오스크 모드 - 유휴 시간 입력":::

11. <span data-ttu-id="f40c9-322"> *\*다음*\*을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-322">Click **Next**.</span></span>
12. <span data-ttu-id="f40c9-323"> *\*설정** 창을 닫고 선택 내용을 저장한 후 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-323">Close the **Settings** window to save and apply your choices.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode--8-done.png" alt-text="키오스크 모드 - 설정 마침":::

13. <span data-ttu-id="f40c9-325">키오스크 장치에서 로그인하고 로컬 키오스크 계정으로 로그인하여 구성의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-325">Sign out from the kiosk device and sign in with the local kiosk account to validate the configuration.</span></span>

## <a name="functional-limitations"></a><span data-ttu-id="f40c9-326">기능 제한 사항</span><span class="sxs-lookup"><span data-stu-id="f40c9-326">Functional limitations</span></span>

<span data-ttu-id="f40c9-327">미리 보기 버전의 키오스크 모드 출시와 함께, 제품을 개선하고 새 기능을 추가하는 작업을 계속 진행하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-327">With the release of this preview version of kiosk mode we're continuing work on improving the product and adding new features.</span></span>

<span data-ttu-id="f40c9-328">현재는 다음 기능을 지원하지 않으므로 해제하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-328">We currently don't support the following features and recommend that you turn off:</span></span>

- [<span data-ttu-id="f40c9-329">InPrivateModeAvailability</span><span class="sxs-lookup"><span data-stu-id="f40c9-329">InPrivateModeAvailability</span></span>](./microsoft-edge-policies.md#inprivatemodeavailability)
- [<span data-ttu-id="f40c9-330">IsolateOrigins</span><span class="sxs-lookup"><span data-stu-id="f40c9-330">IsolateOrigins</span></span>](./microsoft-edge-policies.md#isolateorigins)
- [<span data-ttu-id="f40c9-331">ManagedFavorites</span><span class="sxs-lookup"><span data-stu-id="f40c9-331">ManagedFavorites</span></span>](./microsoft-edge-policies.md#managedfavorites)
- [<span data-ttu-id="f40c9-332">EdgeShoppingAssistantEnabled</span><span class="sxs-lookup"><span data-stu-id="f40c9-332">EdgeShoppingAssistantEnabled</span></span>](./microsoft-edge-policies.md#edgeshoppingassistantenabled)
- [<span data-ttu-id="f40c9-333">EdgeCollectionsEnabled</span><span class="sxs-lookup"><span data-stu-id="f40c9-333">EdgeCollectionsEnabled</span></span>](./microsoft-edge-policies.md#edgecollectionsenabled)
- [<span data-ttu-id="f40c9-334">UserFeedbackAllowed</span><span class="sxs-lookup"><span data-stu-id="f40c9-334">UserFeedbackAllowed</span></span>](./microsoft-edge-policies.md#userfeedbackallowed)
- [<span data-ttu-id="f40c9-335">DefaultPopupsSetting</span><span class="sxs-lookup"><span data-stu-id="f40c9-335">DefaultPopupsSetting</span></span>](./microsoft-edge-policies.md#defaultpopupssetting)
- [<span data-ttu-id="f40c9-336">StartupBoostEnabled</span><span class="sxs-lookup"><span data-stu-id="f40c9-336">StartupBoostEnabled</span></span>](./microsoft-edge-policies.md#startupboostenabled)
- [<span data-ttu-id="f40c9-337">InternetExplorerIntegrationLevel</span><span class="sxs-lookup"><span data-stu-id="f40c9-337">InternetExplorerIntegrationLevel</span></span>](./microsoft-edge-policies.md#internetexplorerintegrationlevel)
- [<span data-ttu-id="f40c9-338">Extensions</span><span class="sxs-lookup"><span data-stu-id="f40c9-338">Extensions</span></span>](./microsoft-edge-policies.md#extensions-policies)
- [<span data-ttu-id="f40c9-339">BackgroundModeEnabled</span><span class="sxs-lookup"><span data-stu-id="f40c9-339">BackgroundModeEnabled</span></span>](./microsoft-edge-policies.md#backgroundmodeenabled)
- [<span data-ttu-id="f40c9-340">UserFeedbackAllowed</span><span class="sxs-lookup"><span data-stu-id="f40c9-340">UserFeedbackAllowed</span></span>](./microsoft-edge-policies.md#userfeedbackallowed)

## <a name="roadmap"></a><span data-ttu-id="f40c9-341">로드맵</span><span class="sxs-lookup"><span data-stu-id="f40c9-341">Roadmap</span></span>

### <a name="in-early-2021"></a><span data-ttu-id="f40c9-342">2021년 초</span><span class="sxs-lookup"><span data-stu-id="f40c9-342">In early 2021</span></span>

<span data-ttu-id="f40c9-343">다음과 같은 지원 및 기능이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-343">We'll add the following support and features:</span></span>

- <span data-ttu-id="f40c9-344">Windows 10 1909 이상에서 할당된 액세스 단일 앱이 있는 Microsoft Edge 키오스크 모드의 일반 가용성</span><span class="sxs-lookup"><span data-stu-id="f40c9-344">General availability of Microsoft Edge kiosk mode with assigned access single app on Windows 10 1909 and higher.</span></span>
- <span data-ttu-id="f40c9-345">Microsoft Edge 레거시를 사용 는 패리티에 대한 추가 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-345">Additional features for parity with Microsoft Edge Legacy.</span></span>
- <span data-ttu-id="f40c9-346">키오스크 모드 프로필 UX를 사용하여 장치를 구성할 수 있도록 Intune과 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-346">Integration with Intune to configure devices using kiosk mode profile UX.</span></span>
- <span data-ttu-id="f40c9-347">브라우저에서 다른 응용 프로그램 실행을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="f40c9-347">Restrict the launch of other applications from the browser.</span></span>
- <span data-ttu-id="f40c9-348">UI 인쇄 설정 잠금</span><span class="sxs-lookup"><span data-stu-id="f40c9-348">UI print settings lockdown.</span></span>

## <a name="see-also"></a><span data-ttu-id="f40c9-349">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f40c9-349">See also</span></span>

- [<span data-ttu-id="f40c9-350">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="f40c9-350">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="f40c9-351">Microsoft Edge 배포 계획</span><span class="sxs-lookup"><span data-stu-id="f40c9-351">Plan your deployment of Microsoft Edge</span></span>](deploy-edge-plan-deployment.md)
- [<span data-ttu-id="f40c9-352">Windows 데스크톱 버전에서 키오스크 및 디지털 서명 구성</span><span class="sxs-lookup"><span data-stu-id="f40c9-352">Configure kiosks and digital signs on Windows desktop editions</span></span>](/windows/configuration/kiosk-methods)
- [<span data-ttu-id="f40c9-353">키오스크 모드 전환 계획</span><span class="sxs-lookup"><span data-stu-id="f40c9-353">Plan your kiosk mode transition</span></span>](microsoft-edge-kiosk-mode-transition-plan.md)