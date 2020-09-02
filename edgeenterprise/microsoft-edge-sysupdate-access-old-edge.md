---
title: 이전 버전의 Microsoft Edge에 액세스
ms.author: jtkim
author: dan-wesley
manager: srugh
ms.date: 08/17/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge의 레거시 버전에 액세스하는 방법을 알아보세요.
ms.openlocfilehash: e5a97a487dc6b3a45504a721e460a69103b0174e
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980713"
---
# <span data-ttu-id="c1237-103">새 버전의 Microsoft Edge를 설치한 후 레거시 Microsoft Edge 액세스</span><span class="sxs-lookup"><span data-stu-id="c1237-103">Access Microsoft Edge Legacy after installing the new version of Microsoft Edge</span></span>

<span data-ttu-id="c1237-104">새 버전의 Microsoft Edge를 설치한 후 레거시 Microsoft Edge 액세스하는 방법을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="c1237-104">Learn how to access Microsoft Edge Legacy after installing the new version of Microsoft Edge.</span></span>

> [!NOTE]
> <span data-ttu-id="c1237-105">이 문서는 Microsoft Edge [안정 채널](microsoft-edge-channels.md)에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-105">This article applies to the Microsoft Edge [Stable channel](microsoft-edge-channels.md).</span></span>

<span data-ttu-id="c1237-106">대부분의 조직에서는 Microsoft Edge 레거시를 새 버전으로 대체하려고 하지만, 사용자가 두 버전 모두에 대한 액세스를 필요로 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-106">While most organizations will want to replace Microsoft Edge Legacy with the new version, there are some situations where users will need access to both versions.</span></span> <span data-ttu-id="c1237-107">예를 들어 다음과 같은 가치를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-107">For example:</span></span>

- <span data-ttu-id="c1237-108">Microsoft Edge 중 하나 또는 두 가지 버전을 모두 사용하는 사용자와 상호 작용하는 고객 지원 및 지원 담당자</span><span class="sxs-lookup"><span data-stu-id="c1237-108">Helpdesk and support staff who interact with users who are using either or both versions of Microsoft Edge.</span></span>
- <span data-ttu-id="c1237-109">두 가지 버전의 Microsoft Edge 중 하나 또는 모두를 사용하는 고객을 지원하는 개발자</span><span class="sxs-lookup"><span data-stu-id="c1237-109">Developers who support customers who are using either or both versions of Microsoft Edge.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c1237-110">프로덕션에서 Microsoft Edge 레거시를 최신 버전의 Microsoft Edge와 함께 실행하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-110">Running Microsoft Edge Legacy side-by-side with the new version of Microsoft Edge is not recommended for use in production.</span></span> <span data-ttu-id="c1237-111">이 구성은 두 브라우저 버전 모두에 대한 테스트가 필요한 경우에만 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-111">This configuration should only be used in specific cases where testing with both browser versions is required.</span></span>
>
> <span data-ttu-id="c1237-112">Microsoft Edge 레거시 데스크톱 앱은 새 Microsoft Edge를 위해 2021년 3월 9일에 지원이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-112">The Microsoft Edge Legacy desktop app will reach end of support on March 9, 2021 in favor of the new Microsoft Edge.</span></span> <span data-ttu-id="c1237-113">이는 Microsoft Edge 레거시가 해당 날짜 이후에는 보안 업데이트를 받지 않음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-113">This means that Microsoft Edge Legacy will not receive security updates after that date.</span></span> <span data-ttu-id="c1237-114">이 변경 내용은 Microsoft Edge 레거시 데스크톱 앱에서 실행하는 모든 환경에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-114">This change is applicable to all experiences that run in the Microsoft Edge Legacy desktop app.</span></span> <span data-ttu-id="c1237-115">[자세한 내용을 알아보세요](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-365-apps-say-farewell-to-internet-explorer-11-and/ba-p/1591666).</span><span class="sxs-lookup"><span data-stu-id="c1237-115">[Learn more](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-365-apps-say-farewell-to-internet-explorer-11-and/ba-p/1591666).</span></span>

## <span data-ttu-id="c1237-116">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="c1237-116">Before you begin</span></span>

<span data-ttu-id="c1237-117">이 문서에 나와 있는 절차는 최신 보안 업데이트로 업데이트된 시스템에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-117">The procedures in this article apply to systems that have been updated with the latest security updates.</span></span> <span data-ttu-id="c1237-118">Microsoft Edge의 새 버전이 설치되면 이전 버전(레거시 Microsoft Edge)이 숨겨집니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-118">When the new version of Microsoft Edge is installed, the old version (Microsoft Edge Legacy) will be hidden.</span></span> <span data-ttu-id="c1237-119">기본적으로, 사용자가 이전 버전을 실행하려고 시도할 때마다 새로 설치된 Microsoft Edge 버전으로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-119">By default, all attempts to launch the old version will redirect the user to the newly installed version of Microsoft Edge.</span></span> <span data-ttu-id="c1237-120">이 문서에서는 Microsoft Edge를 설치한 후에 Microsoft Edge 레거시를 계속 사용할 수 있는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-120">This article describes how you can keep using Microsoft Edge Legacy after you install Microsoft Edge.</span></span>

## <span data-ttu-id="c1237-121">빠른 시작: Microsoft Edge 베타 채널과 Microsoft Edge 레거시를 사용하는 함께 사용 경험</span><span class="sxs-lookup"><span data-stu-id="c1237-121">Quickstart: Side-by-side experience with Microsoft Edge Beta Channel and Microsoft Edge Legacy</span></span>

<span data-ttu-id="c1237-122">이 문서의 자세한 지침을 사용하기 전에 다음 두 단계를 고려하여 사용자가 Microsoft Edge 레거시와 Microsoft Edge [베타 채널](microsoft-edge-channels.md)을 나란히 실행할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-122">Before using the detailed instructions in this article, consider the following two steps to let your users run Microsoft Edge Legacy and the Microsoft Edge [Beta channel](microsoft-edge-channels.md) side-by-side.</span></span>

1. <span data-ttu-id="c1237-123">[Windows 업데이트](https://support.microsoft.com/help/12373/windows-update-faq)에서 Microsoft Edge 안정 채널이 자동으로 설치되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-123">Prevent the automatic install of the Stable Channel of Microsoft Edge by [Windows Update](https://support.microsoft.com/help/12373/windows-update-faq).</span></span>

   > [!TIP]
   > <span data-ttu-id="c1237-124">[차단 도구 키트](microsoft-edge-blocker-toolkit.md)를 사용하여 Microsoft Edge 자동 배달을 비활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-124">Use the [Blocker Toolkit](microsoft-edge-blocker-toolkit.md) to disable automatic delivery of Microsoft Edge.</span></span>

2. <span data-ttu-id="c1237-125">새 버전의 Microsoft Edge의 [베타 채널](https://www.microsoft.com/edge/business/download) 을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-125">Install the [Beta channel](https://www.microsoft.com/edge/business/download) of the new version of Microsoft Edge.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c1237-126">레지스트리 키 설정에 대한 자세한 내용은 [추가 정보](#additional-information)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c1237-126">Read [Additional information](#additional-information) for information about Registry Key settings.</span></span>

<span data-ttu-id="c1237-127">이 함께 사용 솔루션은 덜 복잡하며 이 문서에서 설명하는 세부 솔루션보다 관리를 덜 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-127">This side-by-side solution is less complex and requires less management than the detailed solution described in this article.</span></span> <span data-ttu-id="c1237-128">그러나 이 해결 방법은 안정된 채널이 아니라 베타 채널을 실행하고 있다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-128">However, this solution does mean that you'll be running the Beta Channel rather than the Stable Channel.</span></span>

## <span data-ttu-id="c1237-129">Microsoft Edge 안정 채널과 Microsoft Edge 레거시를 사용하는 함께 사용 경험</span><span class="sxs-lookup"><span data-stu-id="c1237-129">Side-by-side experience with Microsoft Edge Stable Channel and Microsoft Edge Legacy</span></span>

<span data-ttu-id="c1237-130">시스템 수준에서 다음 버전의 Microsoft Edge 안정 채널을 설치하면 현재 버전(Microsoft Edge 레거시)이 숨겨집니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-130">Installing the Stable Channel of the next version of Microsoft Edge at the system-level will cause the current version (Microsoft Edge Legacy) to be hidden.</span></span> <span data-ttu-id="c1237-131">사용자가 두 버전의 Microsoft Edge를 모두 나란히 볼 수 있도록 하려면 **Microsoft Edge 함께 사용 브라우저 환경 허용** 그룹 정책을 **사용**으로 설정하여 이 환경을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-131">If you want to let your users see both versions of Microsoft Edge side by side in Windows, you can enable this experience by setting the **Allow Microsoft Edge Side by Side browser experience** group policy to **Enabled**.</span></span>

<span data-ttu-id="c1237-132">이 그룹 정책에 대한 설명은 [여기](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#allowsxs)에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-132">This group policy is documented [here](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#allowsxs)</span></span>

### <span data-ttu-id="c1237-133">함께 사용 브라우저 환경 정책을 설정하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-133">To set up the side-by-side browser experience policy:</span></span>

1. <span data-ttu-id="c1237-134">[비즈니스용 Microsoft Edge](https://www.microsoft.com/edge/business/download)에서 정책 정의를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-134">Install the Policy Definitions from [Microsoft Edge for Business](https://www.microsoft.com/edge/business/download).</span></span>

   - <span data-ttu-id="c1237-135">사용할 채널/빌드 및 플랫폼을 선택한 다음 정책 파일 가져오기를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-135">Pick the CHANNEL/BUILD and PLATFORM you want to use, and then click GET POLICY FILES.</span></span>
   - <span data-ttu-id="c1237-136">압축 파일의 압축을 풉니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-136">Extract the zipped files.</span></span>
   - <span data-ttu-id="c1237-137">msedge.admx 및 msedgeupdate.admx를 `C:\Windows\PolicyDefinitions` 디렉터리로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-137">Copy msedge.admx and msedgeupdate.admx to the `C:\Windows\PolicyDefinitions` directory.</span></span>
   - <span data-ttu-id="c1237-138">msedge.adml 및 msedgeupdate.adml(해당 언어/로케일 디렉터리부터)을 `C:\Windows\PolicyDefinitions\[APPROPRIATE LANGUAGE/LOCALE]` 디렉터리로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-138">Copy msedge.adml and msedgeupdate.adml (from the appropriate language/locale directory) to the `C:\Windows\PolicyDefinitions\[APPROPRIATE LANGUAGE/LOCALE]` directory.</span></span>

2. <span data-ttu-id="c1237-139">그룹 정책 편집기(gpedit.msc)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-139">Open the Group Policy Editor (gpedit.msc).</span></span>
3. <span data-ttu-id="c1237-140">**컴퓨터 구성**에서 *관리 템플릿 > Microsoft Edge 업데이트 > 애플리케이션*으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-140">Under **Computer Configuration**, go to *Administrative Templates>Microsoft Edge Update>Applications*.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c1237-141">*Microsoft Edge 업데이트* 폴더가 표시되지 않으면 1단계가 올바르게 완료되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-141">If you don't see the *Microsoft Edge Update* folder, verify that step 1 was completed correctly.</span></span>

4. <span data-ttu-id="c1237-142">**애플리케이션** 아래에서 "Microsoft Edge 나란히 브라우저 환경 허용"을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-142">Under **Applications**, double-click "Allow Microsoft Edge Side by Side browser experience".</span></span> <span data-ttu-id="c1237-143">다음 단계를 계속하기 전에 [모범 사례 지침](#best-practice-guidance)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c1237-143">See our [best practice guidance](#best-practice-guidance) before continuing to the next step.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c1237-144">기본적으로 이 그룹 정책은 "구성되지 않음"으로 설정되어 있으며, 이는 새 버전의 Microsoft Edge가 설치되었을 때 레거시 Microsoft Edge를 숨기는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-144">By default, this group policy is set to "Not configured", which results in Microsoft Edge Legacy being hidden when the new version of Microsoft Edge is installed.</span></span>

5. <span data-ttu-id="c1237-145">**사용**을 선택한 후 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-145">Select **Enabled** and then click **OK**.</span></span>  

<span data-ttu-id="c1237-146">이 정책을 설정하면 다음 레지스트리 키가 '00000001'으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-146">Setting this policy will set the following Registry Key  to '00000001':</span></span>

- <span data-ttu-id="c1237-147">키:</span><span class="sxs-lookup"><span data-stu-id="c1237-147">Key:</span></span> `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate`
- <span data-ttu-id="c1237-148">값 이름:</span><span class="sxs-lookup"><span data-stu-id="c1237-148">Value Name:</span></span> `Allowsxs`
- <span data-ttu-id="c1237-149">값 유형:</span><span class="sxs-lookup"><span data-stu-id="c1237-149">Value Type:</span></span> `'REG_DWORD'`

#### <span data-ttu-id="c1237-150">모범 사례 지침</span><span class="sxs-lookup"><span data-stu-id="c1237-150">Best practice guidance</span></span>

<span data-ttu-id="c1237-151">최상의 환경을 위해서는 새 버전의 Microsoft Edge를 사용자의 디바이스에 배포하기 전에 **Microsoft Edge 나란히 브라우저 환경 허용**을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-151">For the best experience, the **Allow Microsoft Edge Side by Side browser experience** should be enabled before the new version of Microsoft Edge is deployed to your users' devices.</span></span>

<span data-ttu-id="c1237-152">Microsoft Edge 배포 후 그룹 정책을 사용하도록 설정한 경우 다음과 같은 부작용과 필수 작업이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-152">If the group policy is enabled after Microsoft Edge is deployed, there are the following side effects and required actions:</span></span>

1. <span data-ttu-id="c1237-153">새 버전의 Microsoft Edge에 대한 설치 프로그램이 다시 실행될 때까지 **Microsoft Edge 나란히 브라우저 환경 허용**이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-153">**Allow Microsoft Edge Side by Side browser experience** won't take effect until after the installer for the new version of Microsoft Edge is run again.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c1237-154">설치 프로그램은 새 버전의 Microsoft Edge가 업데이트될 때 직접 또는 자동으로 실행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-154">The installer can be run directly or automatically when the new version of Microsoft Edge updates.</span></span>

2. <span data-ttu-id="c1237-155">새 버전의 Microsoft Edge를 배포할 때 고정이 마이그레이션되므로 레거시 Microsoft Edge를 시작 또는 작업 표시줄에 다시 고정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-155">Microsoft Edge Legacy will need to be re-pinned to Start or the Taskbar because the pin is migrated when the new version of Microsoft Edge is deployed.</span></span>
3. <span data-ttu-id="c1237-156">레거시 Microsoft Edge에 대해 시작 또는 작업 표시줄에 고정되었던 사이트는 새 버전의 Microsoft Edge로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-156">Sites that were pinned to Start or the Taskbar for Microsoft Edge Legacy will be migrated to the new version of Microsoft Edge.</span></span>

## <span data-ttu-id="c1237-157">추가 정보</span><span class="sxs-lookup"><span data-stu-id="c1237-157">Additional information</span></span>

<span data-ttu-id="c1237-158">시스템이 완전히 업데이트되고 다음 버전의 Microsoft Edge의 안정 채널이 설치되면 다음 레지스트리 키와 값이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-158">After the systems are fully updated and the Stable channel of the next version of Microsoft Edge is installed, the following registry key and value is set:</span></span>

- <span data-ttu-id="c1237-159">키:</span><span class="sxs-lookup"><span data-stu-id="c1237-159">Key:</span></span> `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\EdgeUpdate\ClientState\{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}`
- <span data-ttu-id="c1237-160">키 값:</span><span class="sxs-lookup"><span data-stu-id="c1237-160">Key value:</span></span> `BrowserReplacement`

  > [!IMPORTANT]
  > <span data-ttu-id="c1237-161">이 키는 Microsoft Edge 안정 채널이 업데이트될 때마다 덮어써집니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-161">This key is over-written every time the Microsoft Edge Stable channel is updated.</span></span> <span data-ttu-id="c1237-162">사용자가 두 버전의 Microsoft Edge에 모두 액세스할 수 있도록 이 키를 삭제하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c1237-162">As a best practice, we recommend that you DO NOT delete this key to allow users to access both versions of Microsoft Edge.</span></span>

## <span data-ttu-id="c1237-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c1237-163">See also</span></span>

- [<span data-ttu-id="c1237-164">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="c1237-164">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="c1237-165">Microsoft Edge를 지원하기 위한 Windows 업데이트</span><span class="sxs-lookup"><span data-stu-id="c1237-165">Windows updates to support Microsoft Edge</span></span>](microsoft-edge-sysupdate-windows-updates.md)
