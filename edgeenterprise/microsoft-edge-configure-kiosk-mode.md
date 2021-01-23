---
title: Microsoft Edge 키오스크 모드 구성
ms.author: aguta
author: aguta
manager: srugh
ms.date: 01/21/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 키오스크 모드 구성
ms.openlocfilehash: be353a0e13e9234de40296a2e8dcc31b1b800f52
ms.sourcegitcommit: 8a88fd38bdb5e132e89bf17dd2b5fb72f5d1b4b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "11297474"
---
# <span data-ttu-id="cce1e-103">Microsoft Edge 키오스크 모드 구성</span><span class="sxs-lookup"><span data-stu-id="cce1e-103">Configure Microsoft Edge kiosk mode</span></span>

<span data-ttu-id="cce1e-104">이 문서에서는 시험할 수 있는 Microsoft Edge 키오스크 모드 옵션을 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-104">This article describes how to configure Microsoft Edge kiosk mode options that you can pilot.</span></span> <span data-ttu-id="cce1e-105">또한 대상으로 하는 기능 로드맵도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-105">There's also a roadmap of features we're targeting.</span></span>

> [!NOTE]
> <span data-ttu-id="cce1e-106">이 문서는 Microsoft Edge 버전 87 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-106">This article applies to Microsoft Edge version 87 or later.</span></span>

## <span data-ttu-id="cce1e-107">개요</span><span class="sxs-lookup"><span data-stu-id="cce1e-107">Overview</span></span>

<span data-ttu-id="cce1e-108">Microsoft Edge 키오스크 모드는 조직이 고객을 위해 최고의 환경을 만들고 관리하고 최상의 환경을 제공할 수 있도록 브라우저에 대한 두 가지 잠금 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-108">Microsoft Edge kiosk mode offers two lockdown experiences of the browser so organizations can create, manage, and provide the best experience for their customers.</span></span> <span data-ttu-id="cce1e-109">다음과 같은 잠금 환경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-109">The following lockdown experiences are available:</span></span>  

- <span data-ttu-id="cce1e-110">**디지털/대화형 서명 환경** - 특정 사이트를 전체 화면 모드로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-110">**Digital/Interactive Signage** experience - Displays a specific site in full-screen mode.</span></span>
- <span data-ttu-id="cce1e-111">**공개 검색** 환경 - 제한된 다중 탭 버전의 Microsoft Edge를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-111">**Public-Browsing** experience - Runs a limited multi-tab version of Microsoft Edge.</span></span>

<span data-ttu-id="cce1e-112">두 가지 환경 모두에서 사용자 데이터를 보호하는 Microsoft Edge InPrivate 세션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-112">Both experiences are running a Microsoft Edge InPrivate session, which protects user data.</span></span>

## <span data-ttu-id="cce1e-113">Microsoft Edge 키오스크 모드 설정</span><span class="sxs-lookup"><span data-stu-id="cce1e-113">Set up Microsoft Edge kiosk mode</span></span>

<span data-ttu-id="cce1e-114">초기 키오스크 모드 기능 집합은 Microsoft Edge 안정 채널 버전 87에서 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-114">An initial set of kiosk mode features is available to test with Microsoft Edge Stable Channel, version 87.</span></span> <span data-ttu-id="cce1e-115">Microsoft Edge(공식 안정 채널)에서 최신 [버전을 다운로드할 수 있습니다.](https://www.microsoft.com/edge)</span><span class="sxs-lookup"><span data-stu-id="cce1e-115">You can download the latest version from [Microsoft Edge (Official Stable Channel)](https://www.microsoft.com/edge).</span></span>

### <span data-ttu-id="cce1e-116">키오스크 모드 지원 기능</span><span class="sxs-lookup"><span data-stu-id="cce1e-116">Kiosk mode supported features</span></span>

<span data-ttu-id="cce1e-117">다음 표에는 키오스크 모드에서 지원되는 기능이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-117">The following table lists the features supported by kiosk mode.</span></span>

|<span data-ttu-id="cce1e-118">기능</span><span class="sxs-lookup"><span data-stu-id="cce1e-118">Feature</span></span>|<span data-ttu-id="cce1e-119">디지털\대화형 서명</span><span class="sxs-lookup"><span data-stu-id="cce1e-119">Digital\Interactive Signage</span></span>|<span data-ttu-id="cce1e-120">공개 검색</span><span class="sxs-lookup"><span data-stu-id="cce1e-120">Public browsing</span></span>|<span data-ttu-id="cce1e-121">Microsoft Edge 버전 이상에서 사용 가능</span><span class="sxs-lookup"><span data-stu-id="cce1e-121">Available with Microsoft Edge version (and higher)</span></span>|
|-|-|-|-|
|<span data-ttu-id="cce1e-122">InPrivate 탐색</span><span class="sxs-lookup"><span data-stu-id="cce1e-122">InPrivate Navigation</span></span>|<span data-ttu-id="cce1e-123">Y</span><span class="sxs-lookup"><span data-stu-id="cce1e-123">Y</span></span>|<span data-ttu-id="cce1e-124">Y</span><span class="sxs-lookup"><span data-stu-id="cce1e-124">Y</span></span>|<span data-ttu-id="cce1e-125">87</span><span class="sxs-lookup"><span data-stu-id="cce1e-125">87</span></span>|
|<span data-ttu-id="cce1e-126">비활성 상태로 재설정</span><span class="sxs-lookup"><span data-stu-id="cce1e-126">Reset on inactivity</span></span>|<span data-ttu-id="cce1e-127">Y</span><span class="sxs-lookup"><span data-stu-id="cce1e-127">Y</span></span>|<span data-ttu-id="cce1e-128">Y</span><span class="sxs-lookup"><span data-stu-id="cce1e-128">Y</span></span>|<span data-ttu-id="cce1e-129">87</span><span class="sxs-lookup"><span data-stu-id="cce1e-129">87</span></span>|
|<span data-ttu-id="cce1e-130">[읽기 전용 주소](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskaddressbareditingenabled) 표시줄(정책)</span><span class="sxs-lookup"><span data-stu-id="cce1e-130">[Read only address bar](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskaddressbareditingenabled) (policy)</span></span> |<span data-ttu-id="cce1e-131">N</span><span class="sxs-lookup"><span data-stu-id="cce1e-131">N</span></span>|<span data-ttu-id="cce1e-132">Y</span><span class="sxs-lookup"><span data-stu-id="cce1e-132">Y</span></span> |<span data-ttu-id="cce1e-133">87</span><span class="sxs-lookup"><span data-stu-id="cce1e-133">87</span></span>|
|<span data-ttu-id="cce1e-134">[종료 시 다운로드 삭제(정책)](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskdeletedownloadsonexit)</span><span class="sxs-lookup"><span data-stu-id="cce1e-134">[Delete downloads on exit](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskdeletedownloadsonexit) (policy)</span></span>  | <span data-ttu-id="cce1e-135">Y</span><span class="sxs-lookup"><span data-stu-id="cce1e-135">Y</span></span>|<span data-ttu-id="cce1e-136">Y</span><span class="sxs-lookup"><span data-stu-id="cce1e-136">Y</span></span> |<span data-ttu-id="cce1e-137">87</span><span class="sxs-lookup"><span data-stu-id="cce1e-137">87</span></span>|
|<span data-ttu-id="cce1e-138">F11 차단(전체 화면 입력/종료)</span><span class="sxs-lookup"><span data-stu-id="cce1e-138">F11 blocked (enter/exit full-screen)</span></span> | <span data-ttu-id="cce1e-139">Y</span><span class="sxs-lookup"><span data-stu-id="cce1e-139">Y</span></span> | <span data-ttu-id="cce1e-140">Y</span><span class="sxs-lookup"><span data-stu-id="cce1e-140">Y</span></span> | <span data-ttu-id="cce1e-141">87</span><span class="sxs-lookup"><span data-stu-id="cce1e-141">87</span></span> |
|<span data-ttu-id="cce1e-142">F12 차단(개발자 도구 시작)</span><span class="sxs-lookup"><span data-stu-id="cce1e-142">F12 blocked (launch Developer Tools)</span></span> | <span data-ttu-id="cce1e-143">Y</span><span class="sxs-lookup"><span data-stu-id="cce1e-143">Y</span></span> | <span data-ttu-id="cce1e-144">Y</span><span class="sxs-lookup"><span data-stu-id="cce1e-144">Y</span></span> | <span data-ttu-id="cce1e-145">87</span><span class="sxs-lookup"><span data-stu-id="cce1e-145">87</span></span> |
| <span data-ttu-id="cce1e-146">다중 탭 지원</span><span class="sxs-lookup"><span data-stu-id="cce1e-146">Multi tab support</span></span> | <span data-ttu-id="cce1e-147">N</span><span class="sxs-lookup"><span data-stu-id="cce1e-147">N</span></span>| <span data-ttu-id="cce1e-148">Y</span><span class="sxs-lookup"><span data-stu-id="cce1e-148">Y</span></span>| <span data-ttu-id="cce1e-149">87</span><span class="sxs-lookup"><span data-stu-id="cce1e-149">87</span></span>|
|<span data-ttu-id="cce1e-150">세션 종료 단추</span><span class="sxs-lookup"><span data-stu-id="cce1e-150">End session button</span></span> | <span data-ttu-id="cce1e-151">N</span><span class="sxs-lookup"><span data-stu-id="cce1e-151">N</span></span>| <span data-ttu-id="cce1e-152">Y</span><span class="sxs-lookup"><span data-stu-id="cce1e-152">Y</span></span>| <span data-ttu-id="cce1e-153">88</span><span class="sxs-lookup"><span data-stu-id="cce1e-153">88</span></span>|
|<span data-ttu-id="cce1e-154">모든 내부 Microsoft Edge URL이 차단됩니다edge://downloads 및 edge://print \*\* \*\*</span><span class="sxs-lookup"><span data-stu-id="cce1e-154">All internal Microsoft Edge URLs are blocked, except for *edge://downloads* and *edge://print*</span></span> |<span data-ttu-id="cce1e-155">N</span><span class="sxs-lookup"><span data-stu-id="cce1e-155">N</span></span>|<span data-ttu-id="cce1e-156">Y</span><span class="sxs-lookup"><span data-stu-id="cce1e-156">Y</span></span>|<span data-ttu-id="cce1e-157">88</span><span class="sxs-lookup"><span data-stu-id="cce1e-157">88</span></span>|
| <span data-ttu-id="cce1e-158">Ctrl+N 차단(새 창 열기)</span><span class="sxs-lookup"><span data-stu-id="cce1e-158">CTRL+N blocked (open a new window)</span></span> | <span data-ttu-id="cce1e-159">Y</span><span class="sxs-lookup"><span data-stu-id="cce1e-159">Y</span></span> | <span data-ttu-id="cce1e-160">Y</span><span class="sxs-lookup"><span data-stu-id="cce1e-160">Y</span></span> | <span data-ttu-id="cce1e-161">89</span><span class="sxs-lookup"><span data-stu-id="cce1e-161">89</span></span> |
| <span data-ttu-id="cce1e-162">Ctrl+T 차단(새 탭 열기)</span><span class="sxs-lookup"><span data-stu-id="cce1e-162">CTRL+T blocked (open new tab)</span></span> | <span data-ttu-id="cce1e-163">N</span><span class="sxs-lookup"><span data-stu-id="cce1e-163">N</span></span> | <span data-ttu-id="cce1e-164">Y</span><span class="sxs-lookup"><span data-stu-id="cce1e-164">Y</span></span> | <span data-ttu-id="cce1e-165">89</span><span class="sxs-lookup"><span data-stu-id="cce1e-165">89</span></span> |
|<span data-ttu-id="cce1e-166">설정 및 추가(...)에는 필요한 옵션만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-166">Settings and more (...) will display only the required options</span></span>  |<span data-ttu-id="cce1e-167">N</span><span class="sxs-lookup"><span data-stu-id="cce1e-167">N</span></span> |<span data-ttu-id="cce1e-168">Y</span><span class="sxs-lookup"><span data-stu-id="cce1e-168">Y</span></span> |<span data-ttu-id="cce1e-169">89</span><span class="sxs-lookup"><span data-stu-id="cce1e-169">89</span></span> |

> [!NOTE]
> <span data-ttu-id="cce1e-170">키오스크 모드가 진화하면서 더 많은 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-170">As kiosk mode evolves, more features will be available.</span></span>

## <span data-ttu-id="cce1e-171">키오스크 모드 기능 사용</span><span class="sxs-lookup"><span data-stu-id="cce1e-171">Use kiosk mode features</span></span>

<span data-ttu-id="cce1e-172">다음 Windows 10 명령줄 옵션을 사용하여 Microsoft Edge 키오스크 모드 기능을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-172">Microsoft Edge kiosk mode features can be invoked with the following Windows 10 command line options:</span></span>

- <span data-ttu-id="cce1e-173">키오스크 모드 디지털/대화형 간판 설계:</span><span class="sxs-lookup"><span data-stu-id="cce1e-173">Kiosk mode Digital/Interactive signage:</span></span> `msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen`
- <span data-ttu-id="cce1e-174">키오스크 모드 공용 검색:</span><span class="sxs-lookup"><span data-stu-id="cce1e-174">Kiosk mode public browsing:</span></span> `msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing`

### <span data-ttu-id="cce1e-175">추가 명령줄 옵션</span><span class="sxs-lookup"><span data-stu-id="cce1e-175">Additional command line options</span></span>

- `--no-first-run` <span data-ttu-id="cce1e-176">: 첫 번째 Microsoft Edge 실행 환경을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-176">: Disable the first Microsoft Edge run experience.</span></span>
- `--kiosk-idle-timeout-minutes` <span data-ttu-id="cce1e-177">: Microsoft Edge 키오스크 모드가 사용자 세션을 다시 설정하기 전에 마지막 사용자 활동에서 시간을 분 단위로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-177">: Change the time (in minutes) from the last user activity before Microsoft Edge kiosk mode resets the user's session.</span></span> <span data-ttu-id="cce1e-178">다음 값이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-178">The following values are supported:</span></span>

  - <span data-ttu-id="cce1e-179">기본값</span><span class="sxs-lookup"><span data-stu-id="cce1e-179">Default values</span></span>
    - <span data-ttu-id="cce1e-180">전체 화면 - 꺼짐</span><span class="sxs-lookup"><span data-stu-id="cce1e-180">Full screen - turned off</span></span>
    - <span data-ttu-id="cce1e-181">공개 탐색 - 5분</span><span class="sxs-lookup"><span data-stu-id="cce1e-181">Public browsing - 5 minutes</span></span>
  - <span data-ttu-id="cce1e-182">허용되는 값</span><span class="sxs-lookup"><span data-stu-id="cce1e-182">Allowed values</span></span>
    - <span data-ttu-id="cce1e-183">0 - 타이머가 꺼집니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-183">0 - turns off the timer</span></span>
    - <span data-ttu-id="cce1e-184">1~1440분 동안 유휴 타이머에서 재설정</span><span class="sxs-lookup"><span data-stu-id="cce1e-184">1-1440 minutes for reset on idle timer</span></span>

## <span data-ttu-id="cce1e-185">키오스크 모드에 대한 지원 정책</span><span class="sxs-lookup"><span data-stu-id="cce1e-185">Support policies for kiosk mode</span></span>

<span data-ttu-id="cce1e-186">다음 표에 나열된 Microsoft Edge 정책을 사용하여 구성한 Microsoft Edge 키오스크 모드 유형에 대한 키오스크 환경을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-186">Use any of the Microsoft Edge policies listed in the following table to enhance the kiosk experience for the Microsoft Edge kiosk mode type you configure.</span></span> <span data-ttu-id="cce1e-187">이러한 정책에 대한 자세한 내용은 [Microsoft Edge - 브라우저 정책 참조를 참조하세요.](https://docs.microsoft.com/deployedge/microsoft-edge-policies)</span><span class="sxs-lookup"><span data-stu-id="cce1e-187">To learn more about these policies, see [Microsoft Edge – Browser policy reference](https://docs.microsoft.com/deployedge/microsoft-edge-policies).</span></span>

> [!NOTE]
> <span data-ttu-id="cce1e-188">정책 구성은 다음 표에 나열된 정책으로 제한되지는 않습니다. 그러나 키오스크 모드 기능에 부정적인 영향을 주지 않도록 추가 정책을 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-188">Policy configuration isn't limited to the policies listed in the following table, however additional policies should be tested to ensure that kiosk mode functionality isn't negatively affected.</span></span>

|<span data-ttu-id="cce1e-189">그룹 정책</span><span class="sxs-lookup"><span data-stu-id="cce1e-189">Group policy</span></span>|<span data-ttu-id="cce1e-190">디지털\대화형 간판</span><span class="sxs-lookup"><span data-stu-id="cce1e-190">Digital\Interactive signage</span></span>|<span data-ttu-id="cce1e-191">공개 검색 단일 앱</span><span class="sxs-lookup"><span data-stu-id="cce1e-191">Public browsing single-app</span></span>|
|--|--|--|
|[<span data-ttu-id="cce1e-192">인쇄</span><span class="sxs-lookup"><span data-stu-id="cce1e-192">Printing</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printing-policies) | <span data-ttu-id="cce1e-193">Y</span><span class="sxs-lookup"><span data-stu-id="cce1e-193">Y</span></span>|<span data-ttu-id="cce1e-194">Y</span><span class="sxs-lookup"><span data-stu-id="cce1e-194">Y</span></span> |
|[<span data-ttu-id="cce1e-195">HomePageLocation</span><span class="sxs-lookup"><span data-stu-id="cce1e-195">HomePageLocation</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#homepagelocation) |<span data-ttu-id="cce1e-196">N</span><span class="sxs-lookup"><span data-stu-id="cce1e-196">N</span></span> | <span data-ttu-id="cce1e-197">Y</span><span class="sxs-lookup"><span data-stu-id="cce1e-197">Y</span></span>|
|[<span data-ttu-id="cce1e-198">ShowHomeButton</span><span class="sxs-lookup"><span data-stu-id="cce1e-198">ShowHomeButton</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#showhomebutton) |<span data-ttu-id="cce1e-199">N</span><span class="sxs-lookup"><span data-stu-id="cce1e-199">N</span></span> | <span data-ttu-id="cce1e-200">Y</span><span class="sxs-lookup"><span data-stu-id="cce1e-200">Y</span></span>|
|[<span data-ttu-id="cce1e-201">NewTabPageLocation</span><span class="sxs-lookup"><span data-stu-id="cce1e-201">NewTabPageLocation</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagelocation) |<span data-ttu-id="cce1e-202">N</span><span class="sxs-lookup"><span data-stu-id="cce1e-202">N</span></span> |<span data-ttu-id="cce1e-203">Y</span><span class="sxs-lookup"><span data-stu-id="cce1e-203">Y</span></span> |
|[<span data-ttu-id="cce1e-204">FavoritesBarEnabled</span><span class="sxs-lookup"><span data-stu-id="cce1e-204">FavoritesBarEnabled</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#favoritesbarenabled) |<span data-ttu-id="cce1e-205">N</span><span class="sxs-lookup"><span data-stu-id="cce1e-205">N</span></span> |<span data-ttu-id="cce1e-206">Y</span><span class="sxs-lookup"><span data-stu-id="cce1e-206">Y</span></span> |
|[<span data-ttu-id="cce1e-207">URLAllowlist</span><span class="sxs-lookup"><span data-stu-id="cce1e-207">URLAllowlist</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#urlallowlist) |<span data-ttu-id="cce1e-208">Y</span><span class="sxs-lookup"><span data-stu-id="cce1e-208">Y</span></span> |<span data-ttu-id="cce1e-209">Y</span><span class="sxs-lookup"><span data-stu-id="cce1e-209">Y</span></span> |
|[<span data-ttu-id="cce1e-210">URLBlocklist</span><span class="sxs-lookup"><span data-stu-id="cce1e-210">URLBlocklist</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#urlblocklist) |<span data-ttu-id="cce1e-211">Y</span><span class="sxs-lookup"><span data-stu-id="cce1e-211">Y</span></span> | <span data-ttu-id="cce1e-212">Y</span><span class="sxs-lookup"><span data-stu-id="cce1e-212">Y</span></span>|
|[<span data-ttu-id="cce1e-213">ManagedSearchEngines</span><span class="sxs-lookup"><span data-stu-id="cce1e-213">ManagedSearchEngines</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#managedsearchengines) |<span data-ttu-id="cce1e-214">N</span><span class="sxs-lookup"><span data-stu-id="cce1e-214">N</span></span> | <span data-ttu-id="cce1e-215">Y</span><span class="sxs-lookup"><span data-stu-id="cce1e-215">Y</span></span>|
|[<span data-ttu-id="cce1e-216">UserFeedbackAllowed</span><span class="sxs-lookup"><span data-stu-id="cce1e-216">UserFeedbackAllowed</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#userfeedbackallowed) |<span data-ttu-id="cce1e-217">N</span><span class="sxs-lookup"><span data-stu-id="cce1e-217">N</span></span> | <span data-ttu-id="cce1e-218">Y</span><span class="sxs-lookup"><span data-stu-id="cce1e-218">Y</span></span>|
|[<span data-ttu-id="cce1e-219">VerticalTabsAllowed</span><span class="sxs-lookup"><span data-stu-id="cce1e-219">VerticalTabsAllowed</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#verticaltabsallowed) | <span data-ttu-id="cce1e-220">N</span><span class="sxs-lookup"><span data-stu-id="cce1e-220">N</span></span>|<span data-ttu-id="cce1e-221">Y</span><span class="sxs-lookup"><span data-stu-id="cce1e-221">Y</span></span> |
|[<span data-ttu-id="cce1e-222">SmartScreen 설정</span><span class="sxs-lookup"><span data-stu-id="cce1e-222">SmartScreen settings</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#smartscreen-settings-policies) |<span data-ttu-id="cce1e-223">Y</span><span class="sxs-lookup"><span data-stu-id="cce1e-223">Y</span></span> |<span data-ttu-id="cce1e-224">Y</span><span class="sxs-lookup"><span data-stu-id="cce1e-224">Y</span></span> |

## <span data-ttu-id="cce1e-225">할당된 액세스 권한이 있는 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="cce1e-225">Microsoft Edge with assigned access</span></span>

### <span data-ttu-id="cce1e-226">단일 앱 키오스크</span><span class="sxs-lookup"><span data-stu-id="cce1e-226">Single app kiosk</span></span>

<span data-ttu-id="cce1e-227">Microsoft Edge는 현재 디지털/대화형 간판 및 공개 검색과 같은 잠금 환경을 통해 단일 앱이 할당된 액세스에 대해 동일한 Microsoft Edge 레거시 키오스크 모드 유형의 하위 집합을 지원하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-227">Microsoft Edge currently supports a subset of the same Microsoft Edge Legacy kiosk mode types for single-app assigned access with the following lockdown experiences: Digital/Interactive signage, and Public-browsing.</span></span>  

<span data-ttu-id="cce1e-228">할당된 액세스 권한이 있는 키오스크 모드는 현재 최신  [Windows 10 Insider Preview 빌드](https://insider.windows.com/) 버전 20215 이상 및  [Microsoft Edge Dev Channel](https://www.microsoftedgeinsider.com/download) 버전 87.0.644.4 이상에서 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-228">Kiosk mode with assigned access is currently available for testing with the latest [Windows 10 Insider Preview Build](https://insider.windows.com/), version 20215 or higher, and with the [Microsoft Edge Dev Channel](https://www.microsoftedgeinsider.com/download), version 87.0.644.4 or higher.</span></span>

**<span data-ttu-id="cce1e-229">Windows Insiders 미리 보기를 얻으려면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="cce1e-229">How do I get the Windows Insiders preview?</span></span>**

<span data-ttu-id="cce1e-230">PC에 Windows 10 Insider Preview 빌드를 설치하려면  [Windows 10 Insider Preview 빌드 시작](https://docs.microsoft.com/windows-insider/get-started)에 있는 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="cce1e-230">To install a Windows 10 Insider Preview Build on a PC, follow the instructions in [Getting started with Windows 10 Insider Preview Builds](https://docs.microsoft.com/windows-insider/get-started).</span></span>

### <span data-ttu-id="cce1e-231">복수 앱 키오스크</span><span class="sxs-lookup"><span data-stu-id="cce1e-231">Multi-app kiosk</span></span>

<span data-ttu-id="cce1e-232">Microsoft Edge는 Windows 10에서 [다중 앱이 할당된 액세스](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps)로 실행할 수 있으며, 이는 레거시 Microsoft Edge "일반 검색" 키오스크 모드 유형에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-232">Microsoft Edge can be run with [multi-app assigned access](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps) on Windows 10, which is the equivalent of Microsoft Edge Legacy "Normal browsing" kiosk mode type.</span></span> <span data-ttu-id="cce1e-233">다중 앱이 할당된 액세스로 Microsoft Edge를 구성하기 위해 다중 앱 키오스크를 설정하는 방법에 대한 [지침을 따릅니다.](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps)</span><span class="sxs-lookup"><span data-stu-id="cce1e-233">To configure Microsoft Edge with multi-app assigned access, follow the instructions on how to [Set up a multi-app kiosk](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps).</span></span> <span data-ttu-id="cce1e-234">(Microsoft Edge 안정 채널에 대한 AUMID는 **MSEdge**입니다).</span><span class="sxs-lookup"><span data-stu-id="cce1e-234">(The AUMID for the Microsoft Edge Stable channel is **MSEdge**).</span></span>

<span data-ttu-id="cce1e-235">다중 앱이 할당된 액세스 권한이 있는 Microsoft Edge를 사용하는 경우 Microsoft Edge 브라우저 정책을 사용하여 고유한 요구 사항을 충족하도록 검색 환경을 구성하도록[Microsoft Edge](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-policies) 키오스크를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-235">When using Microsoft Edge with multi-app assigned access, you can configure Microsoft Edge kiosk to use the[Microsoft Edge browser policies](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-policies) to configure the browsing experience to meet your unique requirements.</span></span>

### <span data-ttu-id="cce1e-236">Windows 설정을 사용하여 구성</span><span class="sxs-lookup"><span data-stu-id="cce1e-236">Configure using Windows Settings</span></span>

<span data-ttu-id="cce1e-237">Windows 설정은 한두 개의 단일 앱 키오스크 장치를 설정하는 가장 간단한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-237">Windows Settings is the simplest way to set up one or two single-app kiosk devices.</span></span> <span data-ttu-id="cce1e-238">다음 단계를 사용하여 단일 앱 키오스크 컴퓨터를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-238">Use the following steps to set up a single-app kiosk computer.</span></span>

1. <span data-ttu-id="cce1e-239">최신 Windows 10 Insider Preview 버전 20215 이상을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-239">Install the latest Windows 10 Insider Preview, version 20215 or higher.</span></span> <span data-ttu-id="cce1e-240">[Windows 10 Insider Preview 빌드 시작](https://docs.microsoft.com/windows-insider/get-started)에 있는 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="cce1e-240">Follow the instructions in [Getting started with Windows 10 Insider Preview Builds](https://docs.microsoft.com/windows-insider/get-started).</span></span>
2. <span data-ttu-id="cce1e-241">최신 버전의 [Microsoft Edge](https://www.microsoft.com/edge)안정 채널, 버전 87 이상을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-241">Install the latest version of [Microsoft Edge Stable channel](https://www.microsoft.com/edge), version 87 or higher.</span></span>  <span data-ttu-id="cce1e-242">최신 기능을 테스트하려면 최신 Microsoft [Edge](https://www.microsoftedgeinsider.com/download)개발자 채널 버전 89 이상을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-242">To test the latest features, you can download the latest [Microsoft Edge Dev channel](https://www.microsoftedgeinsider.com/download), version 89 or higher.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="cce1e-243">장치 수준 설치가 필수이므로 Canary 채널이 아닌 채널은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-243">Because a device level installation is required, only a non-Canary channel is supported.</span></span>

3. <span data-ttu-id="cce1e-244">키오스크 컴퓨터에서 Windows 설정을 열고 검색 필드에 "키오스크"를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-244">On the kiosk computer, open Windows Settings, and type "kiosk" in the search field.</span></span> <span data-ttu-id="cce1e-245"> *\*키오스크 설정(할당된 액세스)** 을 선택하면 다음 스크린샷에서 키오스크를 만들 수 있는 대화 상자를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-245">Select  **Set up a kiosk (assigned access)**, shown in the next screenshot to open the dialog for creating the kiosk.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-1-assigned-access.png" alt-text="할당된 액세스 권한을 사용하여 키오스크 설정":::

4. <span data-ttu-id="cce1e-247">**키오스크 설정**  페이지에서  **시작**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-247">On the **Set up a kiosk** page, click **Get started**.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-2-get-started.png" alt-text="키오스크 - 시작":::

5. <span data-ttu-id="cce1e-249">이름을 입력하여 새 키오스크 계정을 만들거나 채워진 드롭다운 목록에서 기존 계정을 선택하고  **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-249">Type a name to create a new kiosk account or choose an existing account from the populated dropdown list and then click **Next**.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-3-create-account.png" alt-text="키오스크 모드 - 계정 만들기":::

6. <span data-ttu-id="cce1e-251">**키오스크 앱 선택** 페이지에서 **Microsoft Edge**를 선택한 후  **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-251">On the **Choose a kiosk app** page, select **Microsoft Edge** and then click **Next**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="cce1e-252">이는 Microsoft Edge Dev, 베타 및 Stable 채널에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-252">This only applies to Microsoft Edge Dev, Beta, and Stable channels.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-4-pick-app.png" alt-text="키오스크 모드 - 앱 선택":::

7. <span data-ttu-id="cce1e-254">키오스크 모드로 실행할 때 Microsoft Edge가 표시되는 방법에 대해 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-254">Pick one of the following options for how Microsoft Edge displays when running in kiosk mode:</span></span>

   - <span data-ttu-id="cce1e-255">디지털/대화형 간판 설계 - Microsoft Edge를 실행하며 전체 화면 모드로 특정 사이트를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-255">Digital/Interactive signage - Displays a specific site in full-screen mode, running Microsoft Edge.</span></span>
   - <span data-ttu-id="cce1e-256">공용 브라우저 - 제한된 다중 탭 버전의 Microsoft Edge를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-256">Public browser - Runs a limited multi-tab version of Microsoft Edge.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-5a-digital-sign.png" alt-text="키오스크 모드 디스플레이 - 전체 화면 디지털 기호":::

8. <span data-ttu-id="cce1e-258"> *\*다음*\*을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-258">Select **Next**.</span></span>
9. <span data-ttu-id="cce1e-259">키오스크 시작 시 로드할 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-259">Type the URL to load when the kiosk launches.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-6-enter-url.png" alt-text="키오스크 모드 - URL 입력":::

10. <span data-ttu-id="cce1e-261">대기 시간에 대한 기본값 5분을 수용하거나 직접 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-261">Accept the default value of 5 minutes for the idle time or provide a value of your own.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-7-enter-idle-time.png" alt-text="키오스크 모드 - 유휴 시간 입력":::

11. <span data-ttu-id="cce1e-263"> *\*다음*\*을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-263">Click **Next**.</span></span>
12. <span data-ttu-id="cce1e-264"> *\*설정** 창을 닫고 선택 내용을 저장한 후 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-264">Close the **Settings** window to save and apply your choices.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode--8-done.png" alt-text="키오스크 모드 - 설정 마침":::

13. <span data-ttu-id="cce1e-266">키오스크 장치에서 로그인하고 로컬 키오스크 계정으로 로그인하여 구성의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-266">Sign out from the kiosk device and sign in with the local kiosk account to validate the configuration.</span></span>

## <span data-ttu-id="cce1e-267">기능 제한 사항</span><span class="sxs-lookup"><span data-stu-id="cce1e-267">Functional limitations</span></span>

<span data-ttu-id="cce1e-268">미리 보기 버전의 키오스크 모드 출시와 함께, 제품을 개선하고 새 기능을 추가하는 작업을 계속 진행하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-268">With the release of this preview version of kiosk mode we're continuing work on improving the product and adding new features.</span></span>

<span data-ttu-id="cce1e-269">다음을 해제하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-269">We recommend that you turn off:</span></span>

- [<span data-ttu-id="cce1e-270">StartupBoostEnabled</span><span class="sxs-lookup"><span data-stu-id="cce1e-270">StartupBoostEnabled</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startupboostenabled)
- [<span data-ttu-id="cce1e-271">InternetExplorerIntegrationLevel</span><span class="sxs-lookup"><span data-stu-id="cce1e-271">InternetExplorerIntegrationLevel</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#internetexplorerintegrationlevel)
- [<span data-ttu-id="cce1e-272">Extensions</span><span class="sxs-lookup"><span data-stu-id="cce1e-272">Extensions</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensions-policies)
- [<span data-ttu-id="cce1e-273">BackgroundModeEnabled</span><span class="sxs-lookup"><span data-stu-id="cce1e-273">BackgroundModeEnabled</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#backgroundmodeenabled)

## <span data-ttu-id="cce1e-274">로드맵</span><span class="sxs-lookup"><span data-stu-id="cce1e-274">Roadmap</span></span>

### <span data-ttu-id="cce1e-275">2021년 초</span><span class="sxs-lookup"><span data-stu-id="cce1e-275">In early 2021</span></span>

<span data-ttu-id="cce1e-276">다음과 같은 지원 및 기능이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-276">We'll add the following support and features:</span></span>

- <span data-ttu-id="cce1e-277">Windows 10 1909 이상에서 할당된 액세스 단일 앱이 있는 Microsoft Edge 키오스크 모드의 일반 가용성</span><span class="sxs-lookup"><span data-stu-id="cce1e-277">General availability of Microsoft Edge kiosk mode with assigned access single app on Windows 10 1909 and higher.</span></span>
- <span data-ttu-id="cce1e-278">Microsoft Edge 레거시를 사용 는 패리티에 대한 추가 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-278">Additional features for parity with Microsoft Edge Legacy.</span></span>
- <span data-ttu-id="cce1e-279">키오스크 모드 프로필 UX를 사용하여 장치를 구성할 수 있도록 Intune과 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-279">Integration with Intune to configure devices using kiosk mode profile UX.</span></span>
- <span data-ttu-id="cce1e-280">추가 바로 가기 키가 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-280">Additional keyboard shortcuts will be blocked.</span></span>
- <span data-ttu-id="cce1e-281">브라우저에서 다른 응용 프로그램 실행을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="cce1e-281">Restrict the launch of other applications from the browser.</span></span>

## <span data-ttu-id="cce1e-282">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cce1e-282">See also</span></span>

- [<span data-ttu-id="cce1e-283">Windows 데스크톱 버전에서 키오스크 및 디지털 서명 구성</span><span class="sxs-lookup"><span data-stu-id="cce1e-283">Configure kiosks and digital signs on Windows desktop editions</span></span>](https://docs.microsoft.com/windows/configuration/kiosk-methods)
- [<span data-ttu-id="cce1e-284">레거시 Microsoft Edge 키오스크 모드 배포</span><span class="sxs-lookup"><span data-stu-id="cce1e-284">Deploy Microsoft Edge Legacy kiosk mode</span></span>](https://aka.ms/edgekioskmode)
- [<span data-ttu-id="cce1e-285">Microsoft Edge 배포 계획</span><span class="sxs-lookup"><span data-stu-id="cce1e-285">Plan your deployment of Microsoft Edge</span></span>](deploy-edge-plan-deployment.md)
- [<span data-ttu-id="cce1e-286">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="cce1e-286">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
