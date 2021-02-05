---
title: IE 모드 FAQ
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 02/02/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: IE 모드가 포함된 Microsoft Edge에 대한 FAQ 및 문제 해결
ms.openlocfilehash: aeae79dfd1745c754fb5ab690338f87fd25c080b
ms.sourcegitcommit: ff67ccc93d07588a9128e9b1fe007d5393a9d6af
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2021
ms.locfileid: "11312594"
---
# <span data-ttu-id="ed51e-103">IE 모드 FAQ</span><span class="sxs-lookup"><span data-stu-id="ed51e-103">IE mode FAQ</span></span>

<span data-ttu-id="ed51e-104">이 문서는 Microsoft Edge 버전 77 이상에 대한 문제 해결 팁과 FAQ를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-104">This article provides troubleshooting tips and an FAQ for Microsoft Edge version 77 or later.</span></span>

> [!NOTE]
> <span data-ttu-id="ed51e-105">이 문서는 Microsoft Edge **안정**, **Beta** 및 **Dev** 채널 버전 77 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-105">This article applies to Microsoft Edge **Stable**, **Beta** and **Dev** Channels, version 77 or later.</span></span>

## <span data-ttu-id="ed51e-106">IE 모드 문제 해결</span><span class="sxs-lookup"><span data-stu-id="ed51e-106">Troubleshoot IE mode</span></span>

<span data-ttu-id="ed51e-107">이 섹션의 정보를 사용하여 IE 모드 문제를 진단하고 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-107">Use the information in this section to diagnose and fix IE mode problems.</span></span>

### <span data-ttu-id="ed51e-108">Internet Explorer 모드 진단 정보</span><span class="sxs-lookup"><span data-stu-id="ed51e-108">Internet Explorer mode diagnostic information</span></span>

<span data-ttu-id="ed51e-109">Microsoft Edge 호환성 탭에서 Internet Explorer 모드 진단 정보를 볼 수 있습니다. 이 탭을 열려면 *edge://compat/iediagnostic*으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-109">You can get Internet Explorer mode diagnostic information on the Microsoft Edge Compatibility tab. To open this tab, go to *edge://compat/iediagnostic*.</span></span> <span data-ttu-id="ed51e-110">이 페이지에는 진단 메시지가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-110">This page may show diagnostic messages.</span></span> <span data-ttu-id="ed51e-111">이 페이지는 다음 범주에 대한 구성 정보도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-111">This page also provides configuration information for the following categories:</span></span>

- <span data-ttu-id="ed51e-112">**레지스트리 키를 확인**.</span><span class="sxs-lookup"><span data-stu-id="ed51e-112">**Registry key check**.</span></span> <span data-ttu-id="ed51e-113">(확인에 실패한 경우에만 표시됨) 레지스트리에 Internet Explorer 통합이 올바르게 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-113">(Displayed only if the check fails.) Checks to see if Internet Explorer integration is set up correctly in the registry.</span></span> <span data-ttu-id="ed51e-114">그렇지 않을 경우, 사용자는 **수정**을 클릭하여 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-114">If not, the user can click **Fix it** to resolve the problem.</span></span>
- <span data-ttu-id="ed51e-115">**Internet Explorer 모드**.</span><span class="sxs-lookup"><span data-stu-id="ed51e-115">**Internet Explorer mode**.</span></span> <span data-ttu-id="ed51e-116">구성 및 OS를 기반으로 사용되는 API 버전을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-116">Shows the API version that's used, based on the configuration and OS.</span></span> <span data-ttu-id="ed51e-117">문제가 있는 경우 **Windows 업데이트**를 설치하라는 메시지가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-117">If there's a problem, the user may be prompted to install a **Windows Update**.</span></span>
- <span data-ttu-id="ed51e-118">**Internet Explorer 모드 설정**.</span><span class="sxs-lookup"><span data-stu-id="ed51e-118">**Internet Explorer mode setting**.</span></span> <span data-ttu-id="ed51e-119">Internet Explorer 모드의 활성화 여부 및 구성 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-119">Shows whether Internet Explorer mode is enabled, and how it's configured.</span></span>
- <span data-ttu-id="ed51e-120">**명령줄**.</span><span class="sxs-lookup"><span data-stu-id="ed51e-120">**Command line**.</span></span> <span data-ttu-id="ed51e-121">Microsoft Edge를 시작하는 데 사용되는 명령줄 문자열과 스위치를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-121">Shows the command line string and switches used to start Microsoft Edge.</span></span>
- <span data-ttu-id="ed51e-122">**그룹 정책 설정**.</span><span class="sxs-lookup"><span data-stu-id="ed51e-122">**Group policy settings**.</span></span> <span data-ttu-id="ed51e-123">IE 모드가 그룹 정책과 적용되는 정책을 사용하여 구성되는지 여부를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-123">Shows whether IE mode is configured using group policies, and the policies that are applied.</span></span>

### <span data-ttu-id="ed51e-124">오류 메시지: "이 페이지를 Internet Explorer 모드에서 열려면 관리자 권한으로 Microsoft Edge를 다시 설치하세요."</span><span class="sxs-lookup"><span data-stu-id="ed51e-124">Error message: "To open this page in Internet Explorer mode, reinstall Microsoft Edge with administrator privileges."</span></span>

<span data-ttu-id="ed51e-125">필수 Windows 업데이트가 모두 없는 경우 이 오류가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-125">You may see this error if you don't have all required Windows Updates.</span></span> <span data-ttu-id="ed51e-126">필요한 Windows 및 Microsoft Edge 버전에 대해서는 [IE 모드 정보](https://docs.microsoft.com/deployedge/edge-ie-mode)에 나열된 필수 구성 요소를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed51e-126">See the prerequisites listed in [About IE mode](https://docs.microsoft.com/deployedge/edge-ie-mode) for the required versions of Windows and Microsoft Edge.</span></span>

<span data-ttu-id="ed51e-127">필요한 모든 Windows Update를 이미 설치했다면 다음과 같은 경우에 이 오류가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-127">If you've already installed all required Windows Updates, you may see this error if:</span></span>

- <span data-ttu-id="ed51e-128">기본적으로 사용자 수준으로 설치되는 Canary 채널을 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-128">You're using the Canary channel, which is installed at the user level by default.</span></span>
- <span data-ttu-id="ed51e-129">Stable, Beta 또는 Dev 채널을 사용하고 있지만 설치할 때 권한 상승 프롬프트가 나타나면 권한 상승이 취소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-129">You're using the Stable, Beta, or Dev channel, but when prompted for elevation when installing the elevation was canceled.</span></span> <span data-ttu-id="ed51e-130">권한 상승 프롬프트를 취소하면 설치는 사용자 수준에서 계속됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-130">When you cancel the elevation prompt, the installation will continue at the user level.</span></span>
- <span data-ttu-id="ed51e-131">Internet Explorer 11은 Windows 기능에서 사용하지 않도록 설정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-131">Internet Explorer 11 has been disabled in Windows Features.</span></span>

<span data-ttu-id="ed51e-132">가능한 해결 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-132">Possible solutions:</span></span>

- <span data-ttu-id="ed51e-133">모든 채널에 대해 설치 프로그램을 시스템 수준에서 실행합니다. `installer.exe --system-level`</span><span class="sxs-lookup"><span data-stu-id="ed51e-133">Run the installer for any channel at the system level: `installer.exe --system-level`.</span></span>
- <span data-ttu-id="ed51e-134">Windows 기능에서 Internet Explorer 11을 사용 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-134">Enable Internet Explorer 11 in Windows Features.</span></span>

<span data-ttu-id="ed51e-135">Microsoft Edge가 시스템 수준에서 설치되어 있는지 확인하려면 Microsoft Edge 주소 표시줄에 "edge://version"을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-135">To check if Microsoft Edge is installed at the systems level, type "edge://version" in the Microsoft Edge address bar.</span></span> <span data-ttu-id="ed51e-136">실행 파일 경로에 *C:\Program Files*로 시작하는 경로가 표시되면 이는 시스템 설치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-136">The Executable path will show a path starting with *C:\Program Files*, which indicates a system install.</span></span> <span data-ttu-id="ed51e-137">실행 파일 경로가 \*C:\Users\*로 시작되는 경우 Microsoft Edge을 제거한 다음 관리자 권한으로 다시 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-137">If the Executable path begins with \*C:\Users\*, uninstall and then reinstall Microsoft Edge with administrator privileges.</span></span>

### <span data-ttu-id="ed51e-138">오류 메시지: "IE 모드에서 이 페이지를 열려면 Microsoft Edge를 다시 시작해 보세요."</span><span class="sxs-lookup"><span data-stu-id="ed51e-138">Error message: "To open this page in IE mode, try restarting Microsoft Edge."</span></span>

<span data-ttu-id="ed51e-139">Internet Explorer에 예기치 않은 오류가 있는 경우 이 오류가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-139">You may see this error if there was an unexpected error in Internet Explorer.</span></span> <span data-ttu-id="ed51e-140">Microsoft Edge를 다시 시작하면 일반적으로 이 오류가 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-140">Restarting Microsoft Edge usually fixes this error.</span></span>

### <span data-ttu-id="ed51e-141">오류 메시지: "이 사이트를 IE 모드에서 열려면 원격 디버깅을 사용하지 않도록 설정하세요. 그렇지 않으면 예상대로 작동하지 않을 수 있습니다."</span><span class="sxs-lookup"><span data-stu-id="ed51e-141">Error message: "Turn off remote debugging to open this site in IE mode otherwise it might not work as expected."</span></span>

<span data-ttu-id="ed51e-142">원격 디버깅을 하고 IE 모드에서 실행되도록 구성된 웹 페이지로 이동하면 이 오류가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-142">You may see this error if you're remote debugging and navigate to a web page configured to run in IE mode.</span></span> <span data-ttu-id="ed51e-143">계속할 수 있지만 페이지는 Microsoft Edge를 사용하여 렌더링됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-143">You can continue, but the page will be rendered using Microsoft Edge.</span></span>

### <span data-ttu-id="ed51e-144">오류 메시지: "오류: EMIE 사이트 목록을 검색할 수 없습니다."</span><span class="sxs-lookup"><span data-stu-id="ed51e-144">Error message: "Error: Could not retrieve EMIE site list."</span></span>

<span data-ttu-id="ed51e-145">*edge://compat/enterprise* 페이지에 사이트 목록을 다운로드하지 못했다는 이 오류가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-145">You may see this error on the *edge://compat/enterprise* page indicating that the site list download failed.</span></span> <span data-ttu-id="ed51e-146">Microsoft Edge 버전 87부터 [BlockThirdPartyCookies](https://docs.microsoft.com/deployedge/microsoft-edge-policies#blockthirdpartycookies) 정책을 사용하여 타사 요청에 대해 쿠키가 차단된 경우 HTTP 인증도 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-146">Starting with Microsoft Edge version 87, when cookies are blocked for third party requests using the [BlockThirdPartyCookies](https://docs.microsoft.com/deployedge/microsoft-edge-policies#blockthirdpartycookies) policy, HTTP authentication is also disallowed.</span></span> <span data-ttu-id="ed51e-147">사이트 목록 다운로드가 성공적으로 진행되도록 [CookiesAllowedForURLs](https://docs.microsoft.com/deployedge/microsoft-edge-policies#cookiesallowedforurls) 정책을 사용하여 엔터프라이즈 모드 사이트 목록을 호스팅하는 특정 도메인에 대한 쿠키를 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-147">You can allow cookies for the specific domain hosting your Enterprise Mode Site List using the [CookiesAllowedForURLs](https://docs.microsoft.com/deployedge/microsoft-edge-policies#cookiesallowedforurls) policy to ensure that site list downloads are successful.</span></span>

## <span data-ttu-id="ed51e-148">자주 묻는 질문</span><span class="sxs-lookup"><span data-stu-id="ed51e-148">Frequently Asked Questions</span></span>

### <span data-ttu-id="ed51e-149">IE 모드가 Internet Explorer 11을 대체하나요?</span><span class="sxs-lookup"><span data-stu-id="ed51e-149">Will IE mode replace Internet Explorer 11?</span></span>

<span data-ttu-id="ed51e-150">Microsoft는 Internet Explorer를 안정적이고 안전한 브라우저로 계속 지원하기 위해 노력하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-150">We're committed to keeping Internet Explorer a supported, reliable, and safe browser.</span></span> <span data-ttu-id="ed51e-151">Internet Explorer는 여전히 Windows의 구성 요소이며 이 브라우저가 설치된 OS의 지원 수명 주기를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-151">Internet Explorer is still a component of Windows and follows the support lifecycle of the OS on which it's installed.</span></span> <span data-ttu-id="ed51e-152">자세한 내용은 [수명 주기 FAQ – Internet Explorer](https://support.microsoft.com/help/17454/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed51e-152">For details, see [Lifecycle FAQ - Internet Explorer](https://support.microsoft.com/help/17454/).</span></span> <span data-ttu-id="ed51e-153">Microsoft에서 계속해서 Internet Explorer를 지원하고 업데이트하지만 최신 기능 및 플랫폼 업데이트는 Microsoft Edge에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-153">While Microsoft continues to support and update Internet Explorer, the latest features and platform updates will only be available in Microsoft Edge.</span></span>

### <span data-ttu-id="ed51e-154">IE모드 SharePoint에서 “탐색기로 오픈” 혹은 “파일 탐색기에서 보기”를 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="ed51e-154">Can I use "Open with Explorer" or "View in File Explorer" in SharePoint with IE mode?</span></span>

<span data-ttu-id="ed51e-155">예, 독립 Internet Explorer 11에서 작동하는 경우 IE 모드에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-155">Yes, if this works in standalone Internet Explorer 11 it will work in IE mode.</span></span> <span data-ttu-id="ed51e-156">그러나 SharePoint 파일 및 폴더 관리를 위해 탐색기에서 열기 옵션을 사용하는 것 보다 [SharePoint 파일 동기화](https://support.office.com/en-us/article/sync-sharepoint-files-with-the-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88) 혹은 [SharePoint 파일 이동 혹은 복사](https://support.office.com/en-us/article/move-or-copy-files-in-sharepoint-00e2f483-4df3-46be-a861-1f5f0c1a87bc)를 추천합니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-156">However, rather than use the Open with Explorer option, the recommended approach to managing files and folders outside of SharePoint is to [sync your SharePoint files](https://support.office.com/en-us/article/sync-sharepoint-files-with-the-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88) or [move or copy files in SharePoint](https://support.office.com/en-us/article/move-or-copy-files-in-sharepoint-00e2f483-4df3-46be-a861-1f5f0c1a87bc).</span></span>

### <span data-ttu-id="ed51e-157">Microsoft Edge의 IE 모드가 Internet Explorer 11에서 지원되었던 *nomerge* 옵션을 지원하나요?</span><span class="sxs-lookup"><span data-stu-id="ed51e-157">Does IE mode on Microsoft Edge support the *nomerge* option that was supported in Internet Explorer 11?</span></span>

<span data-ttu-id="ed51e-158">Microsoft Edge에는 *nomerge* 옵션을 미러링하는 명시적인 명령줄이 없지만 이 기능을 제공하기 위해 권장하는 몇 가지 대안이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-158">There is no explicit command line in Microsoft Edge to mirror the *nomerge* option, but there are a couple of alternatives that we recommend to provide this functionality.</span></span>

1. <span data-ttu-id="ed51e-159">Microsoft Edge에서 프로필 사용 - 각 프로필은 IE 모드 페이지에 대해 서로 다른 IE 세션에 매핑되므로 *nomerge* 옵션과 동일하게 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-159">Use Profiles in Microsoft Edge - Each profile maps to a different IE session for IE mode pages, so it behaves identically to the *nomerge* option.</span></span>
2. <span data-ttu-id="ed51e-160">`--user-data-dir=<path>` 명령줄을 사용하되 각 세션에 대해 다른 경로를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-160">Use the `--user-data-dir=<path>` command line, but with a different path for each session.</span></span> <span data-ttu-id="ed51e-161">필요한 경우, 사용자가 Microsoft Edge를 시작하고 세션의 경로를 변경하는 유틸리티를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-161">If needed, you can create a utility for the user to run that both launches Microsoft Edge and changes the path for the session.</span></span>

<span data-ttu-id="ed51e-162">위의 옵션 중 사용자의 시나리오에 적합한 사항이 없는 경우 Microsoft 지원, [TechCommunity 포럼](https://techcommunity.microsoft.com/t5/enterprise/bd-p/EdgeInsiderEnterprise) 또는 [Microsoft Edge UserVoice](https://microsoftedge.uservoice.com/forums/928825-enterprise)와 같은 피드백 채널 중 하나를 통해 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="ed51e-162">If neither of the above options works for your scenario, reach out through one of our feedback channels:  Microsoft support, [TechCommunity forum](https://techcommunity.microsoft.com/t5/enterprise/bd-p/EdgeInsiderEnterprise), or [Microsoft Edge UserVoice](https://microsoftedge.uservoice.com/forums/928825-enterprise).</span></span>

### <span data-ttu-id="ed51e-163">Internet Explorer 모드에서 링크를 웹 페이지로 저장할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="ed51e-163">Can I save links as webpages in Internet Explorer mode?</span></span>
 
<span data-ttu-id="ed51e-164">예, Microsoft Edge의 Internet Explorer 모드용 바로 가기 메뉴에서 다른 이름으로 대상 저장 옵션을 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-164">Yes, you can enable the Save Target As option in the context menu for Internet Explorer mode in Microsoft Edge.</span></span> <span data-ttu-id="ed51e-165">이렇게 하려면 *컴퓨터 설정 > 관리 템플릿 > Windows 구성 요소 > Internet Explorer*에서 *“Internet Explorer 모드에서 다른 이름으로 대상 저장 허용”* 을 그룹 정책으로 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="ed51e-165">To do this, configure the group policy *"Allow Save Target As in Internet Explorer mode"* located at *Computer Configuration > Administrative Templates > Windows Components > Internet Explorer*.</span></span>
<span data-ttu-id="ed51e-166">저장 메커니즘은 Internet Explorer에서와 동일하게 작동하며, 대상이 html 파일로 저장되는 경우 파일을 다시 열면 Microsoft Edge에서 페이지가 렌더링됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-166">The save mechanism works the same as it does in Internet Explorer and if the target is saved as an html file, re-opening the file will render the page in Microsoft Edge.</span></span>
 
<span data-ttu-id="ed51e-167">이 기능을 사용하려면 다음과 같은 최소 운영 체제 업데이트가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ed51e-167">Note that this functionality requires the following minimum operating system updates:</span></span>
- <span data-ttu-id="ed51e-168">Windows 10, 버전 2004, Windows Server 버전 2004, Windows 10, 버전 20H2 : [KB4580364](https://support.microsoft.com/help/4580364/windows-10-update-kb4580364)</span><span class="sxs-lookup"><span data-stu-id="ed51e-168">Windows 10, version 2004, Windows Server version 2004, Windows 10, version 20H2 : [KB4580364](https://support.microsoft.com/help/4580364/windows-10-update-kb4580364)</span></span>
- <span data-ttu-id="ed51e-169">Windows 10, 버전 1903, Windows 10, 버전 1909, Windows Server 버전 1903: [KB4580386](https://support.microsoft.com/help/4580386/windows-10-update-kb4580386)</span><span class="sxs-lookup"><span data-stu-id="ed51e-169">Windows 10, version 1903, Windows 10, version 1909, Windows Server version 1903: [KB4580386](https://support.microsoft.com/help/4580386/windows-10-update-kb4580386)</span></span>
- <span data-ttu-id="ed51e-170">Windows 10, 버전 1809, Windows Server 버전 1809, Windows Server 2019: [KB4580390](https://support.microsoft.com/help/4580390/windows-10-update-kb4580390)</span><span class="sxs-lookup"><span data-stu-id="ed51e-170">Windows 10, version 1809, Windows Server version 1809, Windows Server 2019: [KB4580390](https://support.microsoft.com/help/4580390/windows-10-update-kb4580390)</span></span>
- <span data-ttu-id="ed51e-171">Windows 10, 버전 1803: [KB4586785](https://support.microsoft.com/help/4586785/windows-10-update-kb4586785)</span><span class="sxs-lookup"><span data-stu-id="ed51e-171">Windows 10, version 1803: [KB4586785](https://support.microsoft.com/help/4586785/windows-10-update-kb4586785)</span></span>
- <span data-ttu-id="ed51e-172">Windows 10, 버전 1607: [KB4586830](https://support.microsoft.com/help/4586830/windows-10-update-kb4586830)</span><span class="sxs-lookup"><span data-stu-id="ed51e-172">Windows 10, version 1607: [KB4586830](https://support.microsoft.com/help/4586830/windows-10-update-kb4586830)</span></span>
- <span data-ttu-id="ed51e-173">Windows 10, 버전 1507: [KB4586787](https://support.microsoft.com/help/4586787/windows-10-update-kb4586787)</span><span class="sxs-lookup"><span data-stu-id="ed51e-173">Windows 10, version 1507: [KB4586787](https://support.microsoft.com/help/4586787/windows-10-update-kb4586787)</span></span>


## <span data-ttu-id="ed51e-174">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ed51e-174">See also</span></span>

- [<span data-ttu-id="ed51e-175">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="ed51e-175">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="ed51e-176">IE 모드 정보</span><span class="sxs-lookup"><span data-stu-id="ed51e-176">About IE mode</span></span>](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [<span data-ttu-id="ed51e-177">추가 엔터프라이즈 모드 정보</span><span class="sxs-lookup"><span data-stu-id="ed51e-177">Additional Enterprise Mode information</span></span>](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
