---
title: Microsoft Edge 키오스크 모드 구성
ms.author: aguta
author: aguta
manager: srugh
ms.date: 04/26/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 키오스크 모드 기능 및 Microsoft Edge 키오스크 모드 옵션을 구성하는 방법에 대해 자세히 알아보세요.
ms.openlocfilehash: 20cb32c0cd27ad6d7437ed8ae0440560f3ed71b2
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2021
ms.locfileid: "11617858"
---
# <a name="configure-microsoft-edge-kiosk-mode"></a><span data-ttu-id="2afe7-103">Microsoft Edge 키오스크 모드 구성</span><span class="sxs-lookup"><span data-stu-id="2afe7-103">Configure Microsoft Edge kiosk mode</span></span>

<span data-ttu-id="2afe7-104">이 문서에서는 시험할 수 있는 Microsoft Edge 키오스크 모드 옵션을 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-104">This article describes how to configure Microsoft Edge kiosk mode options that you can pilot.</span></span> <span data-ttu-id="2afe7-105">또한 대상으로 하는 기능 로드맵도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-105">There's also a roadmap of features we're targeting.</span></span>

> [!NOTE]
> <span data-ttu-id="2afe7-106">이 문서는 Microsoft Edge 버전 87 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-106">This article applies to Microsoft Edge version 87 or later.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2afe7-107">[키오스크 모드 기능 사용](#use-kiosk-mode-features)에 제공된 명령줄 인수를 사용하여 Windows 10에서 Microsoft Edge 키오스크 모드 기능을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-107">Invoke Microsoft Edge kiosk mode features on Windows 10 using the command line arguments provided in [Use kiosk mode features](#use-kiosk-mode-features).</span></span>

## <a name="overview"></a><span data-ttu-id="2afe7-108">개요</span><span class="sxs-lookup"><span data-stu-id="2afe7-108">Overview</span></span>

<span data-ttu-id="2afe7-109">Microsoft Edge 키오스크 모드는 조직이 고객을 위해 최고의 환경을 만들고 관리하고 최상의 환경을 제공할 수 있도록 브라우저에 대한 두 가지 잠금 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-109">Microsoft Edge kiosk mode offers two lockdown experiences of the browser so organizations can create, manage, and provide the best experience for their customers.</span></span> <span data-ttu-id="2afe7-110">다음과 같은 잠금 환경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-110">The following lockdown experiences are available:</span></span>  

- <span data-ttu-id="2afe7-111">**디지털/대화형 서명 환경** - 특정 사이트를 전체 화면 모드로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-111">**Digital/Interactive Signage** experience - Displays a specific site in full-screen mode.</span></span>
- <span data-ttu-id="2afe7-112">**공개 검색** 환경 - 제한된 다중 탭 버전의 Microsoft Edge를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-112">**Public-Browsing** experience - Runs a limited multi-tab version of Microsoft Edge.</span></span>

<span data-ttu-id="2afe7-113">두 가지 환경 모두에서 사용자 데이터를 보호하는 Microsoft Edge InPrivate 세션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-113">Both experiences are running a Microsoft Edge InPrivate session, which protects user data.</span></span>

## <a name="set-up-microsoft-edge-kiosk-mode"></a><span data-ttu-id="2afe7-114">Microsoft Edge 키오스크 모드 설정</span><span class="sxs-lookup"><span data-stu-id="2afe7-114">Set up Microsoft Edge kiosk mode</span></span>

<span data-ttu-id="2afe7-115">초기 키오스크 모드 기능 집합은 Microsoft Edge 안정 채널 버전 87에서 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-115">An initial set of kiosk mode features is available to test with Microsoft Edge Stable Channel, version 87.</span></span> <span data-ttu-id="2afe7-116">Microsoft Edge(공식 안정 채널)에서 최신 [버전을 다운로드할 수 있습니다.](https://www.microsoft.com/edge)</span><span class="sxs-lookup"><span data-stu-id="2afe7-116">You can download the latest version from [Microsoft Edge (Official Stable Channel)](https://www.microsoft.com/edge).</span></span>

### <a name="kiosk-mode-supported-features"></a><span data-ttu-id="2afe7-117">키오스크 모드 지원 기능</span><span class="sxs-lookup"><span data-stu-id="2afe7-117">Kiosk mode supported features</span></span>

<span data-ttu-id="2afe7-118">다음 표에는 Microsoft Edge 및 Microsoft Edge 레거시에서 키오스크 모드로 지원되는 기능이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-118">The following table lists the features supported by kiosk mode in Microsoft Edge and Microsoft Edge Legacy.</span></span> <span data-ttu-id="2afe7-119">Microsoft Edge의 두 버전에서 이러한 기능이 어떻게 지원되는지를 비교하여 Microsoft Edge로 전환하기 위한 가이드로 이 표를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="2afe7-119">Use this table as a guide to transitioning to Microsoft Edge by comparing how these features are supported in both versions of Microsoft Edge.</span></span>

|<span data-ttu-id="2afe7-120">기능</span><span class="sxs-lookup"><span data-stu-id="2afe7-120">Feature</span></span>|<span data-ttu-id="2afe7-121">디지털\대화형 서명</span><span class="sxs-lookup"><span data-stu-id="2afe7-121">Digital\Interactive Signage</span></span>|<span data-ttu-id="2afe7-122">공개 검색</span><span class="sxs-lookup"><span data-stu-id="2afe7-122">Public browsing</span></span>|<span data-ttu-id="2afe7-123">Microsoft Edge 버전 (이상에서 사용 가능)</span><span class="sxs-lookup"><span data-stu-id="2afe7-123">Available with Microsoft Edge version (and higher)</span></span>|<span data-ttu-id="2afe7-124">Microsoft Edge 레거시에서 사용 가능</span><span class="sxs-lookup"><span data-stu-id="2afe7-124">Available with Microsoft Edge Legacy</span></span>|
|-|-|-|-|-|
|<span data-ttu-id="2afe7-125">InPrivate 탐색</span><span class="sxs-lookup"><span data-stu-id="2afe7-125">InPrivate Navigation</span></span>|<span data-ttu-id="2afe7-126">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-126">Y</span></span>|<span data-ttu-id="2afe7-127">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-127">Y</span></span>|<span data-ttu-id="2afe7-128">89</span><span class="sxs-lookup"><span data-stu-id="2afe7-128">89</span></span>|<span data-ttu-id="2afe7-129">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-129">Y</span></span>|
|<span data-ttu-id="2afe7-130">비활성 상태로 재설정</span><span class="sxs-lookup"><span data-stu-id="2afe7-130">Reset on inactivity</span></span>|<span data-ttu-id="2afe7-131">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-131">Y</span></span>|<span data-ttu-id="2afe7-132">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-132">Y</span></span>|<span data-ttu-id="2afe7-133">89</span><span class="sxs-lookup"><span data-stu-id="2afe7-133">89</span></span>|<span data-ttu-id="2afe7-134">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-134">Y</span></span>|
|<span data-ttu-id="2afe7-135">[읽기 전용 주소](./microsoft-edge-policies.md#kioskaddressbareditingenabled)(정책)</span><span class="sxs-lookup"><span data-stu-id="2afe7-135">[Read only address bar](./microsoft-edge-policies.md#kioskaddressbareditingenabled) (policy)</span></span> |<span data-ttu-id="2afe7-136">N</span><span class="sxs-lookup"><span data-stu-id="2afe7-136">N</span></span>|<span data-ttu-id="2afe7-137">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-137">Y</span></span> |<span data-ttu-id="2afe7-138">89</span><span class="sxs-lookup"><span data-stu-id="2afe7-138">89</span></span>|<span data-ttu-id="2afe7-139">N</span><span class="sxs-lookup"><span data-stu-id="2afe7-139">N</span></span>|
|<span data-ttu-id="2afe7-140">[종료 시 다운로드 삭제](./microsoft-edge-policies.md#kioskdeletedownloadsonexit)(정책)</span><span class="sxs-lookup"><span data-stu-id="2afe7-140">[Delete downloads on exit](./microsoft-edge-policies.md#kioskdeletedownloadsonexit) (policy)</span></span>  | <span data-ttu-id="2afe7-141">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-141">Y</span></span>|<span data-ttu-id="2afe7-142">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-142">Y</span></span> |<span data-ttu-id="2afe7-143">89</span><span class="sxs-lookup"><span data-stu-id="2afe7-143">89</span></span>|<span data-ttu-id="2afe7-144">N</span><span class="sxs-lookup"><span data-stu-id="2afe7-144">N</span></span>|
|<span data-ttu-id="2afe7-145">F11 차단(전체 화면 입력/종료)</span><span class="sxs-lookup"><span data-stu-id="2afe7-145">F11 blocked (enter/exit full-screen)</span></span> | <span data-ttu-id="2afe7-146">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-146">Y</span></span> | <span data-ttu-id="2afe7-147">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-147">Y</span></span> |<span data-ttu-id="2afe7-148">89</span><span class="sxs-lookup"><span data-stu-id="2afe7-148">89</span></span>|<span data-ttu-id="2afe7-149">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-149">Y</span></span>|
|<span data-ttu-id="2afe7-150">F12 차단(개발자 도구 시작)</span><span class="sxs-lookup"><span data-stu-id="2afe7-150">F12 blocked (launch Developer Tools)</span></span> | <span data-ttu-id="2afe7-151">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-151">Y</span></span> | <span data-ttu-id="2afe7-152">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-152">Y</span></span> |<span data-ttu-id="2afe7-153">89</span><span class="sxs-lookup"><span data-stu-id="2afe7-153">89</span></span>|<span data-ttu-id="2afe7-154">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-154">Y</span></span>|
| <span data-ttu-id="2afe7-155">다중 탭 지원</span><span class="sxs-lookup"><span data-stu-id="2afe7-155">Multi tab support</span></span> | <span data-ttu-id="2afe7-156">N</span><span class="sxs-lookup"><span data-stu-id="2afe7-156">N</span></span>| <span data-ttu-id="2afe7-157">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-157">Y</span></span>|<span data-ttu-id="2afe7-158">89</span><span class="sxs-lookup"><span data-stu-id="2afe7-158">89</span></span>|<span data-ttu-id="2afe7-159">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-159">Y</span></span>|
|<span data-ttu-id="2afe7-160">[URL 지원 허용](./microsoft-edge-policies.md#urlallowlist) (정책)</span><span class="sxs-lookup"><span data-stu-id="2afe7-160">[Allow URL support](./microsoft-edge-policies.md#urlallowlist) (policy)</span></span>|<span data-ttu-id="2afe7-161">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-161">Y</span></span>|<span data-ttu-id="2afe7-162">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-162">Y</span></span>|<span data-ttu-id="2afe7-163">89</span><span class="sxs-lookup"><span data-stu-id="2afe7-163">89</span></span>|<span data-ttu-id="2afe7-164">N</span><span class="sxs-lookup"><span data-stu-id="2afe7-164">N</span></span>|
|<span data-ttu-id="2afe7-165">[URL 지원 차단](./microsoft-edge-policies.md#urlblocklist) (정책)</span><span class="sxs-lookup"><span data-stu-id="2afe7-165">[Block URL support](./microsoft-edge-policies.md#urlblocklist) (policy)</span></span>|<span data-ttu-id="2afe7-166">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-166">Y</span></span>|<span data-ttu-id="2afe7-167">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-167">Y</span></span>|<span data-ttu-id="2afe7-168">89</span><span class="sxs-lookup"><span data-stu-id="2afe7-168">89</span></span>|<span data-ttu-id="2afe7-169">N</span><span class="sxs-lookup"><span data-stu-id="2afe7-169">N</span></span>|
|<span data-ttu-id="2afe7-170">[홈 단추표시](./microsoft-edge-policies.md#showhomebutton) (정책)</span><span class="sxs-lookup"><span data-stu-id="2afe7-170">[Show home button](./microsoft-edge-policies.md#showhomebutton) (policy)</span></span>|<span data-ttu-id="2afe7-171">N</span><span class="sxs-lookup"><span data-stu-id="2afe7-171">N</span></span>|<span data-ttu-id="2afe7-172">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-172">Y</span></span>|<span data-ttu-id="2afe7-173">89</span><span class="sxs-lookup"><span data-stu-id="2afe7-173">89</span></span>|<span data-ttu-id="2afe7-174">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-174">Y</span></span>|
|<span data-ttu-id="2afe7-175">[즐겨찾기 관리](./microsoft-edge-policies.md#managedfavorites) (정책)</span><span class="sxs-lookup"><span data-stu-id="2afe7-175">[Manage favorites](./microsoft-edge-policies.md#managedfavorites) (policy)</span></span>|<span data-ttu-id="2afe7-176">N</span><span class="sxs-lookup"><span data-stu-id="2afe7-176">N</span></span>|<span data-ttu-id="2afe7-177">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-177">Y</span></span>|<span data-ttu-id="2afe7-178">89</span><span class="sxs-lookup"><span data-stu-id="2afe7-178">89</span></span>|<span data-ttu-id="2afe7-179">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-179">Y</span></span>|
|<span data-ttu-id="2afe7-180">[프린터](./microsoft-edge-policies.md#printingenabled) 사용(정책)</span><span class="sxs-lookup"><span data-stu-id="2afe7-180">[Enable printer](./microsoft-edge-policies.md#printingenabled) (policy)</span></span>|<span data-ttu-id="2afe7-181">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-181">Y</span></span>|<span data-ttu-id="2afe7-182">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-182">Y</span></span>|<span data-ttu-id="2afe7-183">89</span><span class="sxs-lookup"><span data-stu-id="2afe7-183">89</span></span>|<span data-ttu-id="2afe7-184">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-184">Y</span></span>|
|<span data-ttu-id="2afe7-185">[새 탭 페이지 URL 구성](./microsoft-edge-policies.md#newtabpagelocation) (정책)</span><span class="sxs-lookup"><span data-stu-id="2afe7-185">[Configure the new tab page URL](./microsoft-edge-policies.md#newtabpagelocation) (policy)</span></span>|<span data-ttu-id="2afe7-186">N</span><span class="sxs-lookup"><span data-stu-id="2afe7-186">N</span></span>|<span data-ttu-id="2afe7-187">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-187">Y</span></span>|<span data-ttu-id="2afe7-188">89</span><span class="sxs-lookup"><span data-stu-id="2afe7-188">89</span></span>|<span data-ttu-id="2afe7-189">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-189">Y</span></span>|
|<span data-ttu-id="2afe7-190">세션 종료 단추 \*</span><span class="sxs-lookup"><span data-stu-id="2afe7-190">End session button \*</span></span> | <span data-ttu-id="2afe7-191">N</span><span class="sxs-lookup"><span data-stu-id="2afe7-191">N</span></span>| <span data-ttu-id="2afe7-192">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-192">Y</span></span>|<span data-ttu-id="2afe7-193">89</span><span class="sxs-lookup"><span data-stu-id="2afe7-193">89</span></span>|<span data-ttu-id="2afe7-194">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-194">Y</span></span>|
|<span data-ttu-id="2afe7-195">모든 내부 Microsoft Edge URL이 차단되며 *edge://downloads* 및 *edge://print*는 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-195">All internal Microsoft Edge URLs are blocked, except for *edge://downloads* and *edge://print*</span></span> |<span data-ttu-id="2afe7-196">N</span><span class="sxs-lookup"><span data-stu-id="2afe7-196">N</span></span>|<span data-ttu-id="2afe7-197">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-197">Y</span></span>|<span data-ttu-id="2afe7-198">89</span><span class="sxs-lookup"><span data-stu-id="2afe7-198">89</span></span>|<span data-ttu-id="2afe7-199">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-199">Y</span></span>|
| <span data-ttu-id="2afe7-200">Ctrl+N 차단(새 창 열기) \*</span><span class="sxs-lookup"><span data-stu-id="2afe7-200">CTRL+N blocked (open a new window) \*</span></span> | <span data-ttu-id="2afe7-201">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-201">Y</span></span> | <span data-ttu-id="2afe7-202">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-202">Y</span></span> |<span data-ttu-id="2afe7-203">89</span><span class="sxs-lookup"><span data-stu-id="2afe7-203">89</span></span>|<span data-ttu-id="2afe7-204">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-204">Y</span></span>|
| <span data-ttu-id="2afe7-205">Ctrl+T 차단(새 탭 열기)</span><span class="sxs-lookup"><span data-stu-id="2afe7-205">CTRL+T blocked (open new tab)</span></span> |<span data-ttu-id="2afe7-206">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-206">Y</span></span> | <span data-ttu-id="2afe7-207">N</span><span class="sxs-lookup"><span data-stu-id="2afe7-207">N</span></span> |<span data-ttu-id="2afe7-208">89</span><span class="sxs-lookup"><span data-stu-id="2afe7-208">89</span></span>|<span data-ttu-id="2afe7-209">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-209">Y</span></span>|
|<span data-ttu-id="2afe7-210">설정 및 추가(...)에는 필요한 옵션만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-210">Settings and more (...) will display only the required options</span></span>  |<span data-ttu-id="2afe7-211">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-211">Y</span></span> |<span data-ttu-id="2afe7-212">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-212">Y</span></span> |<span data-ttu-id="2afe7-213">89</span><span class="sxs-lookup"><span data-stu-id="2afe7-213">89</span></span>|<span data-ttu-id="2afe7-214">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-214">Y</span></span>|
|<span data-ttu-id="2afe7-215">브라우저에서 다른 응용 프로그램 실행 제한</span><span class="sxs-lookup"><span data-stu-id="2afe7-215">Restrict the launch of other applications from the browser</span></span>|<span data-ttu-id="2afe7-216">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-216">Y</span></span>|<span data-ttu-id="2afe7-217">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-217">Y</span></span>|<span data-ttu-id="2afe7-218">90</span><span class="sxs-lookup"><span data-stu-id="2afe7-218">90</span></span>|<span data-ttu-id="2afe7-219">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-219">Y</span></span>|
|<span data-ttu-id="2afe7-220">UI 인쇄 설정 잠금</span><span class="sxs-lookup"><span data-stu-id="2afe7-220">UI print settings lockdown</span></span>|<span data-ttu-id="2afe7-221">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-221">Y</span></span>|<span data-ttu-id="2afe7-222">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-222">Y</span></span>|<span data-ttu-id="2afe7-223">90</span><span class="sxs-lookup"><span data-stu-id="2afe7-223">90</span></span>|<span data-ttu-id="2afe7-224">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-224">Y</span></span>|
|<span data-ttu-id="2afe7-225">[새 탭 페이지를 홈 페이지로 설정](./microsoft-edge-policies.md#homepageisnewtabpage)(정책)</span><span class="sxs-lookup"><span data-stu-id="2afe7-225">[Set the new tab page as the home page](./microsoft-edge-policies.md#homepageisnewtabpage) (policy)</span></span>|<span data-ttu-id="2afe7-226">N</span><span class="sxs-lookup"><span data-stu-id="2afe7-226">N</span></span>|<span data-ttu-id="2afe7-227">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-227">Y</span></span>|<span data-ttu-id="2afe7-228">90</span><span class="sxs-lookup"><span data-stu-id="2afe7-228">90</span></span>|<span data-ttu-id="2afe7-229">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-229">Y</span></span>|

> [!NOTE]
> <span data-ttu-id="2afe7-230">"\*" 뒤에 오는 기능은 할당된 액세스 단일 앱 시나리오에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-230">Features followed by "\*" are only enabled in an assigned access single app scenario.</span></span>

## <a name="use-kiosk-mode-features"></a><span data-ttu-id="2afe7-231">키오스크 모드 기능 사용</span><span class="sxs-lookup"><span data-stu-id="2afe7-231">Use kiosk mode features</span></span>

<span data-ttu-id="2afe7-232">디지털/대화형 간판 및 공개 검색에 대한 다음 Windows 10 명령줄 옵션을 사용하여 Microsoft Edge 키오스크 모드 기능을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-232">Microsoft Edge kiosk mode features can be invoked with the following Windows 10 command line options for Digital/Interactive signage and Public browsing.</span></span>

### <a name="kiosk-mode-digitalinteractive-signage"></a><span data-ttu-id="2afe7-233">키오스크 모드 디지털/대화형 간판</span><span class="sxs-lookup"><span data-stu-id="2afe7-233">Kiosk mode Digital/Interactive signage</span></span>
 
```
msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen
```

### <a name="kiosk-mode-public-browsing"></a><span data-ttu-id="2afe7-234">키오스크 모드 공개 검색</span><span class="sxs-lookup"><span data-stu-id="2afe7-234">Kiosk mode Public browsing</span></span>

```
msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing
```

### <a name="additional-command-line-options"></a><span data-ttu-id="2afe7-235">추가 명령줄 옵션</span><span class="sxs-lookup"><span data-stu-id="2afe7-235">Additional command line options</span></span>

- <span data-ttu-id="2afe7-236">**--no-first-run**: 첫 번째 Microsoft Edge 실행 환경을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-236">**--no-first-run**: Disable the first Microsoft Edge run experience.</span></span>

   ```
  msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen --no-first-run
  ```

  ```
  msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing --no-first-run
  ```

- <span data-ttu-id="2afe7-237">**--kiosk-idle-timeout-minutes=**: Microsoft Edge 키오스크 모드가 사용자 세션을 다시 설정하기 전에 마지막 사용자 활동에서 시간을 분 단위로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-237">**--kiosk-idle-timeout-minutes=**: Change the time (in minutes) from the last user activity before Microsoft Edge kiosk mode resets the user's session.</span></span> <span data-ttu-id="2afe7-238">다음 예제의 "값"을 분 수로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-238">Replace "value" in the next example with the number of minutes.</span></span>

   ```
   --kiosk-idle-timeout-minutes=value
   ``` 
   <span data-ttu-id="2afe7-239">다음 "값"이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-239">The following "values" are supported:</span></span>

     - <span data-ttu-id="2afe7-240">기본값(분)</span><span class="sxs-lookup"><span data-stu-id="2afe7-240">Default values (in minutes)</span></span>
       - <span data-ttu-id="2afe7-241">전체 화면 - 0(꺼짐)</span><span class="sxs-lookup"><span data-stu-id="2afe7-241">Full screen - 0 (turned off)</span></span>
       - <span data-ttu-id="2afe7-242">공개 탐색 - 5분</span><span class="sxs-lookup"><span data-stu-id="2afe7-242">Public browsing - 5 minutes</span></span>
    - <span data-ttu-id="2afe7-243">허용되는 값</span><span class="sxs-lookup"><span data-stu-id="2afe7-243">Allowed values</span></span>
      - <span data-ttu-id="2afe7-244">0 - 타이머가 꺼집니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-244">0 - turns off the timer</span></span>
      - <span data-ttu-id="2afe7-245">1~1440분 동안 유휴 타이머에서 재설정</span><span class="sxs-lookup"><span data-stu-id="2afe7-245">1-1440 minutes for reset on idle timer</span></span>


    ```
    msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen --kiosk-idle-timeout-minutes=1
   ```

   ```
   msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing --kiosk-idle-timeout-minutes=1
   ```

## <a name="support-policies-for-kiosk-mode"></a><span data-ttu-id="2afe7-246">키오스크 모드에 대한 지원 정책</span><span class="sxs-lookup"><span data-stu-id="2afe7-246">Support policies for kiosk mode</span></span>

<span data-ttu-id="2afe7-247">다음 표에 나열된 Microsoft Edge 정책을 사용하여 구성한 Microsoft Edge 키오스크 모드 유형에 대한 키오스크 환경을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-247">Use any of the Microsoft Edge policies listed in the following table to enhance the kiosk experience for the Microsoft Edge kiosk mode type you configure.</span></span> <span data-ttu-id="2afe7-248">이러한 정책에 대한 자세한 내용은 [Microsoft Edge - 브라우저 정책 참조를 참조하세요.](./microsoft-edge-policies.md)</span><span class="sxs-lookup"><span data-stu-id="2afe7-248">To learn more about these policies, see [Microsoft Edge – Browser policy reference](./microsoft-edge-policies.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2afe7-249">정책 구성은 다음 표에 나열된 정책으로 제한되지는 않습니다. 그러나 키오스크 모드 기능에 부정적인 영향을 주지 않도록 추가 정책을 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-249">Policy configuration isn't limited to the policies listed in the following table, however additional policies should be tested to ensure that kiosk mode functionality isn't negatively affected.</span></span>

|<span data-ttu-id="2afe7-250">그룹 정책</span><span class="sxs-lookup"><span data-stu-id="2afe7-250">Group policy</span></span>|<span data-ttu-id="2afe7-251">디지털\대화형 간판</span><span class="sxs-lookup"><span data-stu-id="2afe7-251">Digital\Interactive signage</span></span>|<span data-ttu-id="2afe7-252">공개 검색 단일 앱</span><span class="sxs-lookup"><span data-stu-id="2afe7-252">Public browsing single-app</span></span>|
|--|--|--|
|[<span data-ttu-id="2afe7-253">인쇄</span><span class="sxs-lookup"><span data-stu-id="2afe7-253">Printing</span></span>](./microsoft-edge-policies.md#printing-policies) | <span data-ttu-id="2afe7-254">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-254">Y</span></span>|<span data-ttu-id="2afe7-255">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-255">Y</span></span> |
|[<span data-ttu-id="2afe7-256">HomePageLocation</span><span class="sxs-lookup"><span data-stu-id="2afe7-256">HomePageLocation</span></span>](./microsoft-edge-policies.md#homepagelocation) |<span data-ttu-id="2afe7-257">N</span><span class="sxs-lookup"><span data-stu-id="2afe7-257">N</span></span> | <span data-ttu-id="2afe7-258">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-258">Y</span></span>|
|[<span data-ttu-id="2afe7-259">ShowHomeButton</span><span class="sxs-lookup"><span data-stu-id="2afe7-259">ShowHomeButton</span></span>](./microsoft-edge-policies.md#showhomebutton) |<span data-ttu-id="2afe7-260">N</span><span class="sxs-lookup"><span data-stu-id="2afe7-260">N</span></span> | <span data-ttu-id="2afe7-261">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-261">Y</span></span>|
|[<span data-ttu-id="2afe7-262">NewTabPageLocation</span><span class="sxs-lookup"><span data-stu-id="2afe7-262">NewTabPageLocation</span></span>](./microsoft-edge-policies.md#newtabpagelocation) |<span data-ttu-id="2afe7-263">N</span><span class="sxs-lookup"><span data-stu-id="2afe7-263">N</span></span> |<span data-ttu-id="2afe7-264">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-264">Y</span></span> |
|[<span data-ttu-id="2afe7-265">FavoritesBarEnabled</span><span class="sxs-lookup"><span data-stu-id="2afe7-265">FavoritesBarEnabled</span></span>](./microsoft-edge-policies.md#favoritesbarenabled) |<span data-ttu-id="2afe7-266">N</span><span class="sxs-lookup"><span data-stu-id="2afe7-266">N</span></span> |<span data-ttu-id="2afe7-267">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-267">Y</span></span> |
|[<span data-ttu-id="2afe7-268">URLAllowlist</span><span class="sxs-lookup"><span data-stu-id="2afe7-268">URLAllowlist</span></span>](./microsoft-edge-policies.md#urlallowlist) |<span data-ttu-id="2afe7-269">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-269">Y</span></span> |<span data-ttu-id="2afe7-270">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-270">Y</span></span> |
|[<span data-ttu-id="2afe7-271">URLBlocklist</span><span class="sxs-lookup"><span data-stu-id="2afe7-271">URLBlocklist</span></span>](./microsoft-edge-policies.md#urlblocklist) |<span data-ttu-id="2afe7-272">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-272">Y</span></span> | <span data-ttu-id="2afe7-273">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-273">Y</span></span>|
|[<span data-ttu-id="2afe7-274">ManagedSearchEngines</span><span class="sxs-lookup"><span data-stu-id="2afe7-274">ManagedSearchEngines</span></span>](./microsoft-edge-policies.md#managedsearchengines) |<span data-ttu-id="2afe7-275">N</span><span class="sxs-lookup"><span data-stu-id="2afe7-275">N</span></span> | <span data-ttu-id="2afe7-276">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-276">Y</span></span>|
|[<span data-ttu-id="2afe7-277">UserFeedbackAllowed</span><span class="sxs-lookup"><span data-stu-id="2afe7-277">UserFeedbackAllowed</span></span>](./microsoft-edge-policies.md#userfeedbackallowed) |<span data-ttu-id="2afe7-278">N</span><span class="sxs-lookup"><span data-stu-id="2afe7-278">N</span></span> | <span data-ttu-id="2afe7-279">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-279">Y</span></span>|
|[<span data-ttu-id="2afe7-280">VerticalTabsAllowed</span><span class="sxs-lookup"><span data-stu-id="2afe7-280">VerticalTabsAllowed</span></span>](./microsoft-edge-policies.md#verticaltabsallowed) | <span data-ttu-id="2afe7-281">N</span><span class="sxs-lookup"><span data-stu-id="2afe7-281">N</span></span>|<span data-ttu-id="2afe7-282">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-282">Y</span></span> |
|[<span data-ttu-id="2afe7-283">SmartScreen 설정</span><span class="sxs-lookup"><span data-stu-id="2afe7-283">SmartScreen settings</span></span>](./microsoft-edge-policies.md#smartscreen-settings-policies) |<span data-ttu-id="2afe7-284">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-284">Y</span></span> |<span data-ttu-id="2afe7-285">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-285">Y</span></span> |
|[<span data-ttu-id="2afe7-286">EdgeCollectionsEnabled</span><span class="sxs-lookup"><span data-stu-id="2afe7-286">EdgeCollectionsEnabled</span></span>](./microsoft-edge-policies.md#edgecollectionsenabled)|<span data-ttu-id="2afe7-287">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-287">Y</span></span>|<span data-ttu-id="2afe7-288">Y</span><span class="sxs-lookup"><span data-stu-id="2afe7-288">Y</span></span>|

## <a name="microsoft-edge-with-assigned-access"></a><span data-ttu-id="2afe7-289">할당된 액세스 권한이 있는 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="2afe7-289">Microsoft Edge with assigned access</span></span>

### <a name="single-app-kiosk"></a><span data-ttu-id="2afe7-290">단일 앱 키오스크</span><span class="sxs-lookup"><span data-stu-id="2afe7-290">Single app kiosk</span></span>

<span data-ttu-id="2afe7-291">Microsoft Edge 버전 90 키오스크 모드는 광범위한 기능 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-291">Microsoft Edge version 90 kiosk mode offers an extensive list of features.</span></span> <span data-ttu-id="2afe7-292">키오스크 모드 지원 기능 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2afe7-292">See the section of Kiosk mode supported features.</span></span>
<span data-ttu-id="2afe7-293">다음 Windows 업데이트를 사용하면 할당된 액세스 단일 앱을 통해 Microsoft Edge를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-293">With the following Windows updates you can configure Microsoft Edge via assigned access single app.</span></span>

|<span data-ttu-id="2afe7-294">운영 체제</span><span class="sxs-lookup"><span data-stu-id="2afe7-294">Operating System</span></span>|<span data-ttu-id="2afe7-295">버전</span><span class="sxs-lookup"><span data-stu-id="2afe7-295">Version</span></span>|<span data-ttu-id="2afe7-296">업데이트</span><span class="sxs-lookup"><span data-stu-id="2afe7-296">Updates</span></span>|
|--|--|--|
|<span data-ttu-id="2afe7-297">Windows 10</span><span class="sxs-lookup"><span data-stu-id="2afe7-297">Windows 10</span></span> | <span data-ttu-id="2afe7-298">2004 이상</span><span class="sxs-lookup"><span data-stu-id="2afe7-298">2004 or later</span></span>|[<span data-ttu-id="2afe7-299">KB4601382 이상</span><span class="sxs-lookup"><span data-stu-id="2afe7-299">KB4601382 or later</span></span>](https://support.microsoft.com/topic/february-24-2021-kb4601382-os-builds-19041-844-and-19042-844-preview-1a7ed2b4-017d-2644-a1e8-dd6bf14cba76) |
|<span data-ttu-id="2afe7-300">Windows 10</span><span class="sxs-lookup"><span data-stu-id="2afe7-300">Windows 10</span></span>| <span data-ttu-id="2afe7-301">1909</span><span class="sxs-lookup"><span data-stu-id="2afe7-301">1909</span></span>| [<span data-ttu-id="2afe7-302">KB4601380 이상</span><span class="sxs-lookup"><span data-stu-id="2afe7-302">KB4601380 or later</span></span>](https://support.microsoft.com/topic/february-16-2021-kb4601380-os-build-18363-1411-preview-2e3c38e1-a947-1033-8006-a30f3806da18)|

<span data-ttu-id="2afe7-303">[Windows 설정](/deployedge/microsoft-edge-configure-kiosk-mode#configure-using-windows-settings) 및 Intune을 통해 Microsoft Edge 키오스크 모드 할당 액세스 단일 앱을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-303">You can manage Microsoft Edge kiosk mode assigned access single app via [Windows Settings](/deployedge/microsoft-edge-configure-kiosk-mode#configure-using-windows-settings) and Intune.</span></span>

### <a name="multi-app-kiosk"></a><span data-ttu-id="2afe7-304">복수 앱 키오스크</span><span class="sxs-lookup"><span data-stu-id="2afe7-304">Multi-app kiosk</span></span>

<span data-ttu-id="2afe7-305">Microsoft Edge는 Windows 10에서 [다중 앱이 할당된 액세스](/windows/configuration/lock-down-windows-10-to-specific-apps)로 실행할 수 있으며, 이는 레거시 Microsoft Edge "일반 검색" 키오스크 모드 유형에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-305">Microsoft Edge can be run with [multi-app assigned access](/windows/configuration/lock-down-windows-10-to-specific-apps) on Windows 10, which is the equivalent of Microsoft Edge Legacy "Normal browsing" kiosk mode type.</span></span> <span data-ttu-id="2afe7-306">다중 앱이 할당된 액세스로 Microsoft Edge를 구성하기 위해 다중 앱 키오스크를 설정하는 방법에 대한 [지침을 따릅니다.](/windows/configuration/lock-down-windows-10-to-specific-apps)</span><span class="sxs-lookup"><span data-stu-id="2afe7-306">To configure Microsoft Edge with multi-app assigned access, follow the instructions on how to [Set up a multi-app kiosk](/windows/configuration/lock-down-windows-10-to-specific-apps).</span></span> <span data-ttu-id="2afe7-307">(Microsoft Edge 안정 채널에 대한 AUMID는 **MSEdge**입니다).</span><span class="sxs-lookup"><span data-stu-id="2afe7-307">(The AUMID for the Microsoft Edge Stable channel is **MSEdge**).</span></span>

### <a name="configure-using-windows-settings"></a><span data-ttu-id="2afe7-308">Windows 설정을 사용하여 구성</span><span class="sxs-lookup"><span data-stu-id="2afe7-308">Configure using Windows Settings</span></span>

<span data-ttu-id="2afe7-309">Windows 설정은 한두 개의 단일 앱 키오스크 장치를 설정하는 가장 간단한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-309">Windows Settings is the simplest way to set up one or two single-app kiosk devices.</span></span> <span data-ttu-id="2afe7-310">다음 단계를 사용하여 단일 앱 키오스크 컴퓨터를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-310">Use the following steps to set up a single-app kiosk computer.</span></span>

1. <span data-ttu-id="2afe7-311">다음의 표는 운영 체제에 대한 최소 시스템 업데이트를 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-311">The minimum system updates for the operating systems listed in the next table.</span></span>

|<span data-ttu-id="2afe7-312">운영 체제</span><span class="sxs-lookup"><span data-stu-id="2afe7-312">Operating System</span></span>|<span data-ttu-id="2afe7-313">버전</span><span class="sxs-lookup"><span data-stu-id="2afe7-313">Version</span></span>|<span data-ttu-id="2afe7-314">업데이트</span><span class="sxs-lookup"><span data-stu-id="2afe7-314">Updates</span></span>|
|--|--|--|
|<span data-ttu-id="2afe7-315">Windows 10</span><span class="sxs-lookup"><span data-stu-id="2afe7-315">Windows 10</span></span> | <span data-ttu-id="2afe7-316">2004 이상</span><span class="sxs-lookup"><span data-stu-id="2afe7-316">2004 or later</span></span>|[<span data-ttu-id="2afe7-317">KB4601382 이상</span><span class="sxs-lookup"><span data-stu-id="2afe7-317">KB4601382 or later</span></span>](https://support.microsoft.com/topic/february-24-2021-kb4601382-os-builds-19041-844-and-19042-844-preview-1a7ed2b4-017d-2644-a1e8-dd6bf14cba76) |
|<span data-ttu-id="2afe7-318">Windows 10</span><span class="sxs-lookup"><span data-stu-id="2afe7-318">Windows 10</span></span>| <span data-ttu-id="2afe7-319">1909</span><span class="sxs-lookup"><span data-stu-id="2afe7-319">1909</span></span>| [<span data-ttu-id="2afe7-320">KB4601380 이상</span><span class="sxs-lookup"><span data-stu-id="2afe7-320">KB4601380 or later</span></span>](https://support.microsoft.com/topic/february-16-2021-kb4601380-os-build-18363-1411-preview-2e3c38e1-a947-1033-8006-a30f3806da18)|

2. <span data-ttu-id="2afe7-321">최신 기능을 테스트하려면 최신 [Microsoft Edge 안정 채널](https://www.microsoft.com/edge/business/download) 버전 89 이상을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-321">To test the latest features, you can download the latest [Microsoft Edge Stable channel](https://www.microsoft.com/edge/business/download), version 89 or higher.</span></span>

3. <span data-ttu-id="2afe7-322">키오스크 컴퓨터에서 Windows 설정을 열고 검색 필드에 "키오스크"를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-322">On the kiosk computer, open Windows Settings, and type "kiosk" in the search field.</span></span> <span data-ttu-id="2afe7-323"> *\*키오스크 설정(할당된 액세스)** 을 선택하면 다음 스크린샷에서 키오스크를 만들 수 있는 대화 상자를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-323">Select  **Set up a kiosk (assigned access)**, shown in the next screenshot to open the dialog for creating the kiosk.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-1-assigned-access.png" alt-text="할당된 액세스 권한을 사용하여 키오스크 설정":::

4. <span data-ttu-id="2afe7-325">**키오스크 설정**  페이지에서  **시작**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-325">On the **Set up a kiosk** page, click **Get started**.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-2-get-started.png" alt-text="키오스크 - 시작":::

5. <span data-ttu-id="2afe7-327">이름을 입력하여 새 키오스크 계정을 만들거나 채워진 드롭다운 목록에서 기존 계정을 선택하고  **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-327">Type a name to create a new kiosk account or choose an existing account from the populated dropdown list and then click **Next**.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-3-create-account.png" alt-text="키오스크 모드 - 계정 만들기":::

6. <span data-ttu-id="2afe7-329">**키오스크 앱 선택** 페이지에서 **Microsoft Edge**를 선택한 후  **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-329">On the **Choose a kiosk app** page, select **Microsoft Edge** and then click **Next**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="2afe7-330">이는 Microsoft Edge Dev, 베타 및 Stable 채널에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-330">This only applies to Microsoft Edge Dev, Beta, and Stable channels.</span></span>

     :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-5c-choose-a-kiosk-app.png" alt-text="키오스크 모드 디스플레이 - 전체 화면 디지털 기호":::

7. <span data-ttu-id="2afe7-332">키오스크 모드로 실행할 때 Microsoft Edge가 표시되는 방법에 대해 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-332">Pick one of the following options for how Microsoft Edge displays when running in kiosk mode:</span></span>

   - <span data-ttu-id="2afe7-333">디지털/대화형 간판 설계 - Microsoft Edge를 실행하며 전체 화면 모드로 특정 사이트를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-333">Digital/Interactive signage - Displays a specific site in full-screen mode, running Microsoft Edge.</span></span>
   - <span data-ttu-id="2afe7-334">공용 브라우저 - 제한된 다중 탭 버전의 Microsoft Edge를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-334">Public browser - Runs a limited multi-tab version of Microsoft Edge.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-5a-digital-sign.png" alt-text="키오스크 사용 방법 - 전체 화면 디지털 기호":::

8. <span data-ttu-id="2afe7-336"> *\*다음*\*을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-336">Select **Next**.</span></span>
9. <span data-ttu-id="2afe7-337">키오스크 시작 시 로드할 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-337">Type the URL to load when the kiosk launches.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-6-enter-url.png" alt-text="키오스크 모드 - URL 입력":::

10. <span data-ttu-id="2afe7-339">대기 시간에 대한 기본값 5분을 수용하거나 직접 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-339">Accept the default value of 5 minutes for the idle time or provide a value of your own.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-7-enter-idle-time.png" alt-text="키오스크 모드 - 유휴 시간 입력":::

11. <span data-ttu-id="2afe7-341"> *\*다음*\*을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-341">Click **Next**.</span></span>
12. <span data-ttu-id="2afe7-342"> *\*설정** 창을 닫고 선택 내용을 저장한 후 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-342">Close the **Settings** window to save and apply your choices.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode--8-done.png" alt-text="키오스크 모드 - 설정 마침":::

13. <span data-ttu-id="2afe7-344">키오스크 장치에서 로그인하고 로컬 키오스크 계정으로 로그인하여 구성의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-344">Sign out from the kiosk device and sign in with the local kiosk account to validate the configuration.</span></span>

## <a name="functional-limitations"></a><span data-ttu-id="2afe7-345">기능 제한 사항</span><span class="sxs-lookup"><span data-stu-id="2afe7-345">Functional limitations</span></span>

<span data-ttu-id="2afe7-346">미리 보기 버전의 키오스크 모드 출시와 함께, 제품을 개선하고 새 기능을 추가하는 작업을 계속 진행하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-346">With the release of this preview version of kiosk mode we're continuing work on improving the product and adding new features.</span></span>

<span data-ttu-id="2afe7-347">현재는 다음 기능을 지원하지 않으므로 해제하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2afe7-347">We currently don't support the following features and recommend that you turn off:</span></span>

- [<span data-ttu-id="2afe7-348">InPrivateModeAvailability</span><span class="sxs-lookup"><span data-stu-id="2afe7-348">InPrivateModeAvailability</span></span>](./microsoft-edge-policies.md#inprivatemodeavailability)
- [<span data-ttu-id="2afe7-349">IsolateOrigins</span><span class="sxs-lookup"><span data-stu-id="2afe7-349">IsolateOrigins</span></span>](./microsoft-edge-policies.md#isolateorigins)
- [<span data-ttu-id="2afe7-350">ManagedFavorites</span><span class="sxs-lookup"><span data-stu-id="2afe7-350">ManagedFavorites</span></span>](./microsoft-edge-policies.md#managedfavorites)
- [<span data-ttu-id="2afe7-351">EdgeShoppingAssistantEnabled</span><span class="sxs-lookup"><span data-stu-id="2afe7-351">EdgeShoppingAssistantEnabled</span></span>](./microsoft-edge-policies.md#edgeshoppingassistantenabled)
- [<span data-ttu-id="2afe7-352">EdgeCollectionsEnabled</span><span class="sxs-lookup"><span data-stu-id="2afe7-352">EdgeCollectionsEnabled</span></span>](./microsoft-edge-policies.md#edgecollectionsenabled)
- [<span data-ttu-id="2afe7-353">UserFeedbackAllowed</span><span class="sxs-lookup"><span data-stu-id="2afe7-353">UserFeedbackAllowed</span></span>](./microsoft-edge-policies.md#userfeedbackallowed)
- [<span data-ttu-id="2afe7-354">DefaultPopupsSetting</span><span class="sxs-lookup"><span data-stu-id="2afe7-354">DefaultPopupsSetting</span></span>](./microsoft-edge-policies.md#defaultpopupssetting)
- [<span data-ttu-id="2afe7-355">StartupBoostEnabled</span><span class="sxs-lookup"><span data-stu-id="2afe7-355">StartupBoostEnabled</span></span>](./microsoft-edge-policies.md#startupboostenabled)
- [<span data-ttu-id="2afe7-356">InternetExplorerIntegrationLevel</span><span class="sxs-lookup"><span data-stu-id="2afe7-356">InternetExplorerIntegrationLevel</span></span>](./microsoft-edge-policies.md#internetexplorerintegrationlevel)
- [<span data-ttu-id="2afe7-357">Extensions</span><span class="sxs-lookup"><span data-stu-id="2afe7-357">Extensions</span></span>](./microsoft-edge-policies.md#extensions-policies)
- [<span data-ttu-id="2afe7-358">BackgroundModeEnabled</span><span class="sxs-lookup"><span data-stu-id="2afe7-358">BackgroundModeEnabled</span></span>](./microsoft-edge-policies.md#backgroundmodeenabled)
- [<span data-ttu-id="2afe7-359">UserFeedbackAllowed</span><span class="sxs-lookup"><span data-stu-id="2afe7-359">UserFeedbackAllowed</span></span>](./microsoft-edge-policies.md#userfeedbackallowed)

## <a name="see-also"></a><span data-ttu-id="2afe7-360">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2afe7-360">See also</span></span>

- [<span data-ttu-id="2afe7-361">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="2afe7-361">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="2afe7-362">Microsoft Edge 배포 계획</span><span class="sxs-lookup"><span data-stu-id="2afe7-362">Plan your deployment of Microsoft Edge</span></span>](deploy-edge-plan-deployment.md)
- [<span data-ttu-id="2afe7-363">Windows 데스크톱 버전에서 키오스크 및 디지털 서명 구성</span><span class="sxs-lookup"><span data-stu-id="2afe7-363">Configure kiosks and digital signs on Windows desktop editions</span></span>](/windows/configuration/kiosk-methods)
- [<span data-ttu-id="2afe7-364">키오스크 모드 전환 계획</span><span class="sxs-lookup"><span data-stu-id="2afe7-364">Plan your kiosk mode transition</span></span>](microsoft-edge-kiosk-mode-transition-plan.md)
