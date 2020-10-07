---
title: Microsoft Edge 키오스크 모드 구성
ms.author: aguta
author: aguta
manager: srugh
ms.date: 10/05/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 키오스크 모드 구성
ms.openlocfilehash: 799b3dd4b7fc96f0b8e5cb718bca98fd4f38ec15
ms.sourcegitcommit: 78905f66f4a6590a57c8f2bf808af92106b62996
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/05/2020
ms.locfileid: "11094865"
---
# <span data-ttu-id="6c2de-103">Microsoft Edge 키오스크 모드 구성</span><span class="sxs-lookup"><span data-stu-id="6c2de-103">Configure Microsoft Edge kiosk mode</span></span>

<span data-ttu-id="6c2de-104">이 문서에서는 시험할 수 있는 Microsoft Edge 키오스크 모드 옵션을 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-104">This article describes how to configure Microsoft Edge kiosk mode options that you can pilot.</span></span> <span data-ttu-id="6c2de-105">대상으로 하는 기능 로드맵도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-105">There's also a roadmap of features we are targeting.</span></span>

> [!NOTE]
> <span data-ttu-id="6c2de-106">이 문서는 Microsoft Edge 버전 87 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-106">This article applies to Microsoft Edge version 87 or later.</span></span>

## <span data-ttu-id="6c2de-107">개요</span><span class="sxs-lookup"><span data-stu-id="6c2de-107">Overview</span></span>

<span data-ttu-id="6c2de-108">Microsoft Edge 키오스크 모드는 조직이 고객을 위해 최고의 환경을 만들고 관리하고 최상의 환경을 제공할 수 있도록 브라우저에 대한 두 가지 잠금 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-108">Microsoft Edge kiosk mode offers two lockdown experiences of the browser so organizations can create, manage, and provide the best experience for their customers.</span></span> <span data-ttu-id="6c2de-109">다음과 같은 잠금 환경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-109">The following lockdown experiences are available:</span></span>  

- <span data-ttu-id="6c2de-110">디지털/대화형 간판 설계 환경은 전체 화면 모드에서 특정 사이트를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-110">The Digital/Interactive signage experience displays a specific site in full-screen mode.</span></span>
- <span data-ttu-id="6c2de-111">공개 검색 환경은 Microsoft Edge의 제한된 다중 탭 버전을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-111">The public-browsing experience runs a limited multi-tab version of Microsoft Edge.</span></span>

<span data-ttu-id="6c2de-112">두 가지 환경 모두에서 사용자 데이터를 보호하는 Microsoft Edge InPrivate 세션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-112">Both experiences are running a Microsoft Edge InPrivate session, which protects user data.</span></span>

## <span data-ttu-id="6c2de-113">Microsoft Edge 키오스크 모드 설정</span><span class="sxs-lookup"><span data-stu-id="6c2de-113">Set up Microsoft Edge kiosk mode</span></span>

<span data-ttu-id="6c2de-114">Microsoft Edge Canary Channel 버전 87을 사용하여 테스트하는 데 키오스크 모드 기능의 초기 집합을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-114">An initial set of kiosk mode features are now available to test with Microsoft Edge Canary Channel, version 87.</span></span> <span data-ttu-id="6c2de-115">[Microsoft Edge Insider Channels](https://www.microsoftedgeinsider.com/download)에서 Microsoft Edge Canary를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-115">You can download Microsoft Edge Canary from the [Microsoft Edge Insider Channels](https://www.microsoftedgeinsider.com/download) page.</span></span>

### <span data-ttu-id="6c2de-116">키오스크 모드 기능</span><span class="sxs-lookup"><span data-stu-id="6c2de-116">Kiosk mode features</span></span>

<span data-ttu-id="6c2de-117">다음과 같은 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-117">The following features are available:</span></span>

- <span data-ttu-id="6c2de-118">InPrivate 탐색은 세션이 종료되면 브라우저 데이터 및 다운로드를 삭제하여 사용자 데이터를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-118">InPrivate navigation protects user data by deleting browser data and downloads when the session ends.</span></span>
- <span data-ttu-id="6c2de-119">종료 시 다운로드 삭제를 구성하는 정책</span><span class="sxs-lookup"><span data-stu-id="6c2de-119">A policy to configure Delete downloads on exit.</span></span>
- <span data-ttu-id="6c2de-120">특정 기간 동안의 비활성 상태 후 사용자 세션을 다시 설정하는 옵션</span><span class="sxs-lookup"><span data-stu-id="6c2de-120">The option to reset a user session after a certain period of inactivity.</span></span>
- <span data-ttu-id="6c2de-121">초기 잠금 기능 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-121">An initial set of lockdown functionality.</span></span> <span data-ttu-id="6c2de-122">다음과 같은 함수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-122">The following functions are available:</span></span>

  - <span data-ttu-id="6c2de-123">마우스 상황에 맞는 메뉴</span><span class="sxs-lookup"><span data-stu-id="6c2de-123">Mouse context menu</span></span>
  - <span data-ttu-id="6c2de-124">F12 개발자 도구</span><span class="sxs-lookup"><span data-stu-id="6c2de-124">F12 Developer Tools</span></span>
  - <span data-ttu-id="6c2de-125">F11 전체 화면 닫기(전체 화면 모드)</span><span class="sxs-lookup"><span data-stu-id="6c2de-125">F11 Exit full screen (while in full screen mode)</span></span>
  - <span data-ttu-id="6c2de-126">*Edge://* 페이지의 초기 집합 차단</span><span class="sxs-lookup"><span data-stu-id="6c2de-126">Blocking of the initial set of *Edge://* pages</span></span>

> [!NOTE]
> <span data-ttu-id="6c2de-127">키오스크 모드가 진화하면서 더 많은 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-127">As kiosk mode evolves, more features will be available.</span></span>

## <span data-ttu-id="6c2de-128">키오스크 모드 기능 사용</span><span class="sxs-lookup"><span data-stu-id="6c2de-128">Use kiosk mode features</span></span>

<span data-ttu-id="6c2de-129">다음 Windows 10 명령줄 옵션을 사용하여 Microsoft Edge 키오스크 모드 기능을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-129">You can invoke Microsoft Edge kiosk mode features can be invoked with the following Windows 10 command line options:</span></span>

- <span data-ttu-id="6c2de-130">키오스크 모드 디지털/대화형 간판 설계:</span><span class="sxs-lookup"><span data-stu-id="6c2de-130">Kiosk mode Digital/Interactive signage:</span></span> `msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen`
- <span data-ttu-id="6c2de-131">키오스크 모드 공용 검색:</span><span class="sxs-lookup"><span data-stu-id="6c2de-131">Kiosk mode public browsing:</span></span> `msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing`

### <span data-ttu-id="6c2de-132">추가 명령줄 옵션</span><span class="sxs-lookup"><span data-stu-id="6c2de-132">Additional command line options</span></span>

- `--no-first-run` <span data-ttu-id="6c2de-133">: 첫 번째 Microsoft Edge 실행 환경을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-133">: Disable the first Microsoft Edge run experience.</span></span>
- `--kiosk-idle-timeout-minutes` <span data-ttu-id="6c2de-134">: Microsoft Edge 키오스크 모드가 사용자 세션을 다시 설정하기 전에 마지막 사용자 활동에서 시간을 분 단위로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-134">: Change the time (in minutes) from the last user activity before Microsoft Edge kiosk mode resets the user's session.</span></span> <span data-ttu-id="6c2de-135">다음 값이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-135">The following values are supported:</span></span>

  - <span data-ttu-id="6c2de-136">기본값</span><span class="sxs-lookup"><span data-stu-id="6c2de-136">Default values</span></span>
    - <span data-ttu-id="6c2de-137">전체 화면 - 꺼짐</span><span class="sxs-lookup"><span data-stu-id="6c2de-137">Full screen - turned off</span></span>
    - <span data-ttu-id="6c2de-138">공개 탐색 - 5분</span><span class="sxs-lookup"><span data-stu-id="6c2de-138">Public browsing - 5 minutes</span></span>
  - <span data-ttu-id="6c2de-139">허용되는 값</span><span class="sxs-lookup"><span data-stu-id="6c2de-139">Allowed values</span></span>
    - <span data-ttu-id="6c2de-140">0 - 타이머가 꺼집니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-140">0 - turns off the timer</span></span>
    - <span data-ttu-id="6c2de-141">1~1440분 동안 유휴 타이머에서 재설정</span><span class="sxs-lookup"><span data-stu-id="6c2de-141">1-1440 minutes for reset on idle timer</span></span>

## <span data-ttu-id="6c2de-142">할당된 액세스 권한이 있는 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="6c2de-142">Microsoft Edge with assigned access</span></span>

### <span data-ttu-id="6c2de-143">단일 앱 키오스크</span><span class="sxs-lookup"><span data-stu-id="6c2de-143">Single app kiosk</span></span>

<span data-ttu-id="6c2de-144">Microsoft Edge는 현재 다음에 나오는 잠금 환경, 디지털/대화형 간판, 공개 검색을 통해 단일 앱 할당 액세스에 사용할 동일한 Microsoft Edge 레거시 키오스크 모드 유형의 하위 집합을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-144">Microsoft Edge currently supports a subset of the same Microsoft Edge Legacy kiosk mode types for single-app assigned access with the following lockdown experiences, Digital/Interactive signage and Public-browsing.</span></span>  

<span data-ttu-id="6c2de-145">할당된 액세스 권한이 있는 키오스크 모드는 현재 최신  [Windows 10 Insider Preview 빌드](https://insider.windows.com/) 버전 20215 이상 및  [Microsoft Edge Dev Channel](https://www.microsoftedgeinsider.com/download) 버전 87.0.644.4 이상에서 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-145">Kiosk mode with assigned access is currently available for testing with the latest [Windows 10 Insider Preview Build](https://insider.windows.com/), version 20215 or higher, and with the [Microsoft Edge Dev Channel](https://www.microsoftedgeinsider.com/download), version 87.0.644.4 or higher.</span></span>

**<span data-ttu-id="6c2de-146">Windows Insiders 미리 보기를 얻으려면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="6c2de-146">How do I get the Windows Insiders preview?</span></span>**

<span data-ttu-id="6c2de-147">PC에 Windows 10 Insider Preview 빌드를 설치하려면  [Windows 10 Insider Preview 빌드 시작](https://docs.microsoft.com/windows-insider/get-started)에 있는 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="6c2de-147">To install a Windows 10 Insider Preview Build on a PC, follow the instructions in [Getting started with Windows 10 Insider Preview Builds](https://docs.microsoft.com/windows-insider/get-started).</span></span>

### <span data-ttu-id="6c2de-148">복수 앱 키오스크</span><span class="sxs-lookup"><span data-stu-id="6c2de-148">Multi-app kiosk</span></span>

<span data-ttu-id="6c2de-149">Microsoft Edge는 Windows 10에서 [다중 앱이 할당된 액세스](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps)로 실행할 수 있으며, 이는 레거시 Microsoft Edge "일반 검색" 키오스크 모드 유형에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-149">Microsoft Edge can be run with [multi-app assigned access](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps) on Windows 10, which is the equivalent of Microsoft Edge Legacy "Normal browsing" kiosk mode type.</span></span> <span data-ttu-id="6c2de-150">다중 앱이 할당된 액세스 권한을 사용하여 Microsoft Edge를 구성하려면 [다중 앱 키오스크를 설정](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps)하는 방법에 대한 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-150">To configure Microsoft Edge with multi-app assigned access follow the instructions on how to [Set up a multi-app kiosk](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps).</span></span> <span data-ttu-id="6c2de-151">(Microsoft Edge 안정 채널에 대한 AUMID는 **MSEdge**입니다).</span><span class="sxs-lookup"><span data-stu-id="6c2de-151">(The AUMID for the Microsoft Edge Stable channel is **MSEdge**).</span></span>

<span data-ttu-id="6c2de-152">Microsoft Edge 키오스크 모드 구성. 다중 앱이 할당된 액세스 권한으로 Microsoft Edge를 사용하는 경우 [Microsoft Edge 브라우저 정책](https://review.docs.microsoft.com/en-us/DeployEdge/microsoft-edge-policies)을 사용하여 사용자의 고유한 요구 사항에 맞게 검색 환경을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-152">Configure Microsoft Edge kiosk mode When using Microsoft Edge with multi-app assigned access you can use the [Microsoft Edge browser policies](https://review.docs.microsoft.com/en-us/DeployEdge/microsoft-edge-policies) to configure the browsing experience to meet your unique requirements.</span></span>

### <span data-ttu-id="6c2de-153">Windows 설정을 사용하여 구성</span><span class="sxs-lookup"><span data-stu-id="6c2de-153">Configure using Windows Settings</span></span>

<span data-ttu-id="6c2de-154">Windows 설정은 한두 개의 단일 앱 키오스크 장치를 설정하는 가장 간단한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-154">Windows Settings is the simplest way to set up one or two single-app kiosk devices.</span></span> <span data-ttu-id="6c2de-155">다음 단계를 사용하여 단일 앱 키오스크 컴퓨터를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-155">Use the following steps to set up a single-app kiosk computer.</span></span>

1. <span data-ttu-id="6c2de-156">최신 Windows 10 Insider Preview 버전 20215 이상을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-156">Install the latest Windows 10 Insider Preview, version 20215 or higher.</span></span> <span data-ttu-id="6c2de-157">[Windows 10 Insider Preview 빌드 시작](https://docs.microsoft.com/windows-insider/get-started)에 있는 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="6c2de-157">Follow the instructions in [Getting started with Windows 10 Insider Preview Builds](https://docs.microsoft.com/windows-insider/get-started).</span></span>
2. <span data-ttu-id="6c2de-158">[Microsoft Edge Dev 채널](https://www.microsoftedgeinsider.com/download) 87.0.644.4 이상의 최신 버전을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-158">Install the latest version of [Microsoft Edge Dev channel](https://www.microsoftedgeinsider.com/download), 87.0.644.4 or higher.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="6c2de-159">장치 수준 설치가 필수이므로 Canary 채널이 아닌 채널은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-159">Because a device level installation is required, only a non-Canary channel is supported.</span></span>

3. <span data-ttu-id="6c2de-160">키오스크 컴퓨터에서 Windows 설정을 열고 검색 필드에 "키오스크"를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-160">On the kiosk computer, open Windows Settings, and type "kiosk" in the search field.</span></span> <span data-ttu-id="6c2de-161"> *\*키오스크 설정(할당된 액세스)** 을 선택하면 다음 스크린샷에서 키오스크를 만들 수 있는 대화 상자를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-161">Select  **Set up a kiosk (assigned access)**, shown in the next screenshot to open the dialog for creating the kiosk.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-1-assigned-access.png" alt-text="할당된 액세스 권한을 사용하여 키오스크 설정":::

4. <span data-ttu-id="6c2de-163">**키오스크 설정**  페이지에서  **시작**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-163">On the **Set up a kiosk** page, click **Get started**.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-2-get-started.png" alt-text="할당된 액세스 권한을 사용하여 키오스크 설정":::

5. <span data-ttu-id="6c2de-165">이름을 입력하여 새 키오스크 계정을 만들거나 채워진 드롭다운 목록에서 기존 계정을 선택하고  **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-165">Type a name to create a new kiosk account or choose an existing account from the populated dropdown list and then click **Next**.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-3-create-account.png" alt-text="할당된 액세스 권한을 사용하여 키오스크 설정":::

6. <span data-ttu-id="6c2de-167">**키오스크 앱 선택** 페이지에서 **Microsoft Edge**를 선택한 후  **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-167">On the **Choose a kiosk app** page, select **Microsoft Edge** and then click **Next**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="6c2de-168">이는 Microsoft Edge Dev, 베타 및 Stable 채널에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-168">This only applies to Microsoft Edge Dev, Beta, and Stable channels.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-4-pick-app.png" alt-text="할당된 액세스 권한을 사용하여 키오스크 설정":::

7. <span data-ttu-id="6c2de-170">키오스크 모드로 실행할 때 Microsoft Edge가 표시되는 방법에 대해 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-170">Pick one of the following options for how Microsoft Edge displays when running in kiosk mode:</span></span>

   - <span data-ttu-id="6c2de-171">디지털/대화형 간판 설계 - Microsoft Edge를 실행하며 전체 화면 모드로 특정 사이트를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-171">Digital/Interactive signage - Displays a specific site in full-screen mode, running Microsoft Edge.</span></span>
   - <span data-ttu-id="6c2de-172">공용 브라우저 - 제한된 다중 탭 버전의 Microsoft Edge를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-172">Public browser - Runs a limited multi-tab version of Microsoft Edge.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-5a-digital-sign.png" alt-text="할당된 액세스 권한을 사용하여 키오스크 설정":::

8. <span data-ttu-id="6c2de-174"> *\*다음*\*을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-174">Select **Next**.</span></span>
9. <span data-ttu-id="6c2de-175">키오스크 시작 시 로드할 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-175">Type the URL to load when the kiosk launches.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-6-enter-url.png" alt-text="할당된 액세스 권한을 사용하여 키오스크 설정":::

10. <span data-ttu-id="6c2de-177">대기 시간에 대한 기본값 5분을 수용하거나 직접 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-177">Accept the default value of 5 minutes for the idle time or provide a value of your own.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-7-enter-idle-time.png" alt-text="할당된 액세스 권한을 사용하여 키오스크 설정":::

11. <span data-ttu-id="6c2de-179"> *\*다음*\*을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-179">Click **Next**.</span></span>
12. <span data-ttu-id="6c2de-180"> *\*설정** 창을 닫고 선택 내용을 저장한 후 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-180">Close the **Settings** window to save and apply your choices.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode--8-done.png" alt-text="할당된 액세스 권한을 사용하여 키오스크 설정":::

13. <span data-ttu-id="6c2de-182">키오스크 장치에서 로그아웃하고 로컬 키오스크 계정으로 로그인하여 구성에 대해 유효성 검사를 실시합니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-182">Sign off from the kiosk device and sign in with the local kiosk account to validate the configuration.</span></span>

## <span data-ttu-id="6c2de-183">기능 제한 사항</span><span class="sxs-lookup"><span data-stu-id="6c2de-183">Functional limitations</span></span>

<span data-ttu-id="6c2de-184">미리 보기 버전의 키오스크 모드 출시와 함께, 제품을 개선하고 새 기능을 추가하는 작업을 계속 진행하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-184">With the release of this preview version of kiosk mode we're continuing work on improving the product and adding new features.</span></span>

<span data-ttu-id="6c2de-185">현재 키오스크 모드에서는 다음 기능을 지원하지는 않지만, 다음 기능에 대해 작업 중입니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-185">Although kiosk mode doesn't currently support the following functionality, work is underway on the following features:</span></span>

- <span data-ttu-id="6c2de-186">컬렉션</span><span class="sxs-lookup"><span data-stu-id="6c2de-186">Collections</span></span>
- <span data-ttu-id="6c2de-187">Extensions</span><span class="sxs-lookup"><span data-stu-id="6c2de-187">Extensions</span></span>
- <span data-ttu-id="6c2de-188">Internet Explorer 모드</span><span class="sxs-lookup"><span data-stu-id="6c2de-188">Internet Explorer mode</span></span>
- <span data-ttu-id="6c2de-189">Windows Defender Application Guard(WDAG)</span><span class="sxs-lookup"><span data-stu-id="6c2de-189">Windows Defender Application Guard (WDAG)</span></span>

## <span data-ttu-id="6c2de-190">로드맵</span><span class="sxs-lookup"><span data-stu-id="6c2de-190">Roadmap</span></span>

### <span data-ttu-id="6c2de-191">올해 말(2020)</span><span class="sxs-lookup"><span data-stu-id="6c2de-191">Later this year (2020)</span></span>

<span data-ttu-id="6c2de-192">다음 기능을 추가 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-192">We'll add the following features:</span></span>

- <span data-ttu-id="6c2de-193">세션 종료 단추</span><span class="sxs-lookup"><span data-stu-id="6c2de-193">End session button</span></span>
- <span data-ttu-id="6c2de-194">주소 표시줄 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="6c2de-194">Read only address bar</span></span>  
  - <span data-ttu-id="6c2de-195">그룹 정책을 사용하여 구성 가능</span><span class="sxs-lookup"><span data-stu-id="6c2de-195">Configurable with group policy</span></span>
  - <span data-ttu-id="6c2de-196">이 설정을 사용하면 주소 표시줄을 편집하여 다른 페이지로 이동하는 것을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-196">When enabled, users will be prevented from editing the address bar and navigating to another page.</span></span>

- <span data-ttu-id="6c2de-197">추가 잠금 기능:</span><span class="sxs-lookup"><span data-stu-id="6c2de-197">More lockdown functions:</span></span>

  - <span data-ttu-id="6c2de-198">추가 가속기가 차단됩니다(예: CTRL + N).</span><span class="sxs-lookup"><span data-stu-id="6c2de-198">Additional accelerators will be blocked (for example, CTRL+N)</span></span>
  - <span data-ttu-id="6c2de-199">"..." 설정 메뉴에서는 필수 옵션(예: 인쇄, 도움말, 피드백, 소리내어 읽기)만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-199">The "…" settings menu will enable only required options (for example, Print, Help,  Feedback, and Read aloud)</span></span>
  - <span data-ttu-id="6c2de-200">추가 *edge://* 페이지 잠금(예: *edge://settings*)</span><span class="sxs-lookup"><span data-stu-id="6c2de-200">Additional *edge://* pages lockdown (for example, *edge://settings*)</span></span>
  - <span data-ttu-id="6c2de-201">인쇄 옵션 UI 구성</span><span class="sxs-lookup"><span data-stu-id="6c2de-201">Configure print options UI</span></span>
  - <span data-ttu-id="6c2de-202">파일 탐색기를 다운로드 폴더로만 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-202">Limiting file explorer to the download folder only.</span></span>

### <span data-ttu-id="6c2de-203">2021년 초</span><span class="sxs-lookup"><span data-stu-id="6c2de-203">In early 2021</span></span>

<span data-ttu-id="6c2de-204">다음과 같은 지원 및 기능이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-204">We'll add the following support and features:</span></span>

- <span data-ttu-id="6c2de-205">Windows에서 할당된 액세스 단일 앱을 사용하여 Microsoft Edge 키오스크 모드 출시.</span><span class="sxs-lookup"><span data-stu-id="6c2de-205">General availability of Microsoft Edge kiosk mode with assigned access single app on Windows.</span></span>
- <span data-ttu-id="6c2de-206">Microsoft Edge 레거시를 사용 는 패리티에 대한 추가 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="6c2de-206">Additional features for parity with Microsoft Edge Legacy.</span></span>
- <span data-ttu-id="6c2de-207">키오스크 모드 프로필 UX를 사용하여 장치를 구성할 수 있도록 Intune과 통합.</span><span class="sxs-lookup"><span data-stu-id="6c2de-207">Integration with Intune to configure devices using kiosk mode profile UX.</span></span>

## <span data-ttu-id="6c2de-208">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6c2de-208">See also</span></span>

- [<span data-ttu-id="6c2de-209">Windows 데스크톱 버전에서 키오스크 및 디지털 서명 구성</span><span class="sxs-lookup"><span data-stu-id="6c2de-209">Configure kiosks and digital signs on Windows desktop editions</span></span>](https://docs.microsoft.com/windows/configuration/kiosk-methods)
- [<span data-ttu-id="6c2de-210">레거시 Microsoft Edge 키오스크 모드 배포</span><span class="sxs-lookup"><span data-stu-id="6c2de-210">Deploy Microsoft Edge Legacy kiosk mode</span></span>](https://aka.ms/edgekioskmode)
- [<span data-ttu-id="6c2de-211">Microsoft Edge 배포 계획</span><span class="sxs-lookup"><span data-stu-id="6c2de-211">Plan your deployment of Microsoft Edge</span></span>](deploy-edge-plan-deployment.md)
- [<span data-ttu-id="6c2de-212">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="6c2de-212">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
