---
title: 최신 웹 사이트와의 호환성을 위해 Internet Explorer에서 Microsoft Edge로 리디렉션
ms.author: laannade
author: dan-wesley
manager: ratetali
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 최신 웹 사이트와의 호환성을 위해 Internet Explorer에서 Microsoft Edge로 리디렉션
ms.openlocfilehash: ec59380b82dc975ba3075d6e008bc0da05136f72
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642114"
---
# <a name="redirection-from-internet-explorer-to-microsoft-edge-for-compatibility-with-modern-web-sites"></a><span data-ttu-id="4d69f-103">최신 웹 사이트와의 호환성을 위해 Internet Explorer에서 Microsoft Edge로 리디렉션</span><span class="sxs-lookup"><span data-stu-id="4d69f-103">Redirection from Internet Explorer to Microsoft Edge for compatibility with modern web sites</span></span>

> [!NOTE]
> <span data-ttu-id="4d69f-104">이 문서는 Microsoft Edge 안정 버전 87 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-104">This article applies to Microsoft Edge Stable version 87 or later.</span></span>

## <a name="overview"></a><span data-ttu-id="4d69f-105">개요</span><span class="sxs-lookup"><span data-stu-id="4d69f-105">Overview</span></span>

>[!Note]
> <span data-ttu-id="4d69f-106">Internet Explorer 11 데스크톱 응용 프로그램은 2022년 6월 15일 사용 및 지원이 중단됩니다(범위 내 항목 목록은 [FAQ 참고](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)).</span><span class="sxs-lookup"><span data-stu-id="4d69f-106">The Internet Explorer 11 desktop application will be retired and go out of support on June 15, 2022 (for a list of what’s in scope, [see the FAQ](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)).</span></span> <span data-ttu-id="4d69f-107">현재 사용하는 동일한 IE11 앱과 사이트는 Internet Explorer 모드에서 Microsoft Edge로 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-107">The same IE11 apps and sites you use today can open in Microsoft Edge with Internet Explorer mode.</span></span> <span data-ttu-id="4d69f-108">[여기서 자세한 내용을 알아보세요](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/).</span><span class="sxs-lookup"><span data-stu-id="4d69f-108">[Learn more here](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/).</span></span>

<span data-ttu-id="4d69f-109">많은 최신 웹 사이트에는 Internet Explorer와 호환되지 않는 디자인이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-109">Many modern websites have designs that are incompatible with Internet Explorer.</span></span> <span data-ttu-id="4d69f-110">Internet Explorer 사용자는 호환되지 않는 공용 사이트를 방문할 때 사이트가 브라우저와 호환되지 않는다는 메시지를 받고 수동으로 다른 브라우저로 전환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-110">Whenever an Internet Explorer user visits an incompatible public site, they get a message that tells them the site is incompatible with their browser, and they need to manually switch to a different browser.</span></span>

<span data-ttu-id="4d69f-111">Microsoft Edge 안정 버전 87부터 다른 브라우저로 수동으로 전환할 필요성이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-111">The need to  manually switch to a different browser changes starting with Microsoft Edge Stable version 87.</span></span>

<span data-ttu-id="4d69f-112">사용자가 Internet Explorer와 호환되지 않는 사이트로 이동할 때, 사용자는 자동으로 Microsoft Edge로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-112">When a user goes to a site that is incompatible with Internet Explorer, they will be automatically redirected to Microsoft Edge.</span></span> <span data-ttu-id="4d69f-113">이 문서에서는 리디렉션에 대한 사용자 환경 및 자동 리디렉션을 구성하거나 해제하는 데 사용되는 그룹 정책을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-113">This article describes the user experience for redirection and the group policies that are used to configure or disable automatic redirection.</span></span>

> [!NOTE]
> <span data-ttu-id="4d69f-114">Microsoft는 Internet Explorer와 호환되지 않는 것으로 알려진 모든 사이트 목록을 유지하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-114">Microsoft maintains a list of all sites that are known to be incompatible with Internet Explorer.</span></span> <span data-ttu-id="4d69f-115">자세한 내용은 [호환되지 않는 사이트 목록 업데이트 요청](/microsoft-edge/web-platform/ie-to-microsoft-edge-redirection#request-an-update-to-the-ie-compatibility-list)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4d69f-115">For more information, see [Request updates to the incompatible sites list](/microsoft-edge/web-platform/ie-to-microsoft-edge-redirection#request-an-update-to-the-ie-compatibility-list)</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4d69f-116">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="4d69f-116">Prerequisites</span></span>
- <span data-ttu-id="4d69f-117">Microsoft Edge 안정적인 버전 87 이상</span><span class="sxs-lookup"><span data-stu-id="4d69f-117">Microsoft Edge Stable version 87 or later</span></span>
- <span data-ttu-id="4d69f-118">Windows 버전</span><span class="sxs-lookup"><span data-stu-id="4d69f-118">Windows versions</span></span>
    - <span data-ttu-id="4d69f-119">Windows 10 버전 1709 이상</span><span class="sxs-lookup"><span data-stu-id="4d69f-119">Windows 10 version 1709 or later</span></span>
    - <span data-ttu-id="4d69f-120">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="4d69f-120">Windows 8.1</span></span>
    - <span data-ttu-id="4d69f-121">Windows 7</span><span class="sxs-lookup"><span data-stu-id="4d69f-121">Windows 7</span></span>



## <a name="redirection-experience"></a><span data-ttu-id="4d69f-122">리디렉션 환경</span><span class="sxs-lookup"><span data-stu-id="4d69f-122">Redirection experience</span></span>

<span data-ttu-id="4d69f-123">Microsoft Edge로 리디렉션 시, 사용자에게 다음 스크린샷의 일회성 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-123">On redirection to Microsoft Edge, users are shown the one-time dialog in the next screenshot.</span></span> <span data-ttu-id="4d69f-124">이 대화 상자는 리디렉션되는 이유를 설명하고 Internet Explorer에서 Microsoft Edge로 그들의 검색 데이터와 기본 설정을 복사하라는 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-124">This dialog explains why they're getting redirected and prompts for consent to copy their browsing data and preferences from Internet Explorer to Microsoft Edge.</span></span> <span data-ttu-id="4d69f-125">즐겨찾기, 암호, 검색 엔진, 열린 탭, 기록, 설정, 쿠키 및 홈 페이지와 같은 다음의 검색 데이터를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-125">The following browsing data will be imported: Favorites, Passwords, Search engines, open tabs, History, settings, cookies, and the Home Page.</span></span>

![검색 알림 및 데이터와 기본 설정을 가져올 것인지 묻는 메시지입니다.](media/edge-learnmore-neededge/neededge-dialog1.png)

<span data-ttu-id="4d69f-127">"검색 데이터를 언제든지 Internet Explorer에서 가져옵니다"를 선택하여 동의하지 않는 경우에도  **계속 탐색** 을 클릭하여 세션을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-127">Even if they don't give their consent by checking "Always bring over my browsing data and preferences from Internet Explorer", they can click **Continue browsing** to continue their session.</span></span>

<span data-ttu-id="4d69f-128">마지막으로 다음 스크린샷에 표시된 웹 사이트 비호환 배너는 모든 리디렉션 시 주소 표시줄 아래에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-128">Finally, a website incompatibility banner, shown in the next screenshot, appears below the address bar for every redirection.</span></span>

![최신 사이트에 대한 알림과 Microsoft Edge를 기본 브라우저로 설정하거나 Microsoft Edge를 탐색하라는 메시지입니다.](media/edge-learnmore-neededge/neededge-banner.png)

<span data-ttu-id="4d69f-130">웹 사이트 비호환 배너:</span><span class="sxs-lookup"><span data-stu-id="4d69f-130">The website incompatibility banner:</span></span>

- <span data-ttu-id="4d69f-131">사용자에게 Microsoft Edge로 전환할 것을 권장</span><span class="sxs-lookup"><span data-stu-id="4d69f-131">encourages the user to switch to Microsoft Edge</span></span>
- <span data-ttu-id="4d69f-132">Microsoft Edge를 기본 브라우저로 설정하도록 제안</span><span class="sxs-lookup"><span data-stu-id="4d69f-132">offers to make Microsoft Edge as the default browser</span></span>
- <span data-ttu-id="4d69f-133">사용자에게 Microsoft Edge를 탐색할 수 있는 옵션을 제공</span><span class="sxs-lookup"><span data-stu-id="4d69f-133">gives the user the option to explore Microsoft Edge</span></span>

<span data-ttu-id="4d69f-134">사이트가 Internet Explorer에서 Microsoft Edge로 리디렉션되는 경우, 이전 콘텐츠가 없는 경우에 사이트를 로드하기 시작한 Internet Explorer 탭은 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-134">When a site is redirected from Internet Explorer to Microsoft Edge, the Internet Explorer tab that started loading the site is closed if it had no prior content.</span></span> <span data-ttu-id="4d69f-135">그렇지 않으면 활성 탭 보기가 Microsoft Edge로 리디렉션된 이유를 설명하는 Microsoft [지원](https://support.microsoft.com/office/the-website-you-were-trying-to-reach-doesn-t-work-with-internet-explorer-8f5fc675-cd47-414c-9535-12821ddfc554?ui=en-US&rs=en-US&ad=US) 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-135">Otherwise, the active tab view goes to a  Microsoft [support](https://support.microsoft.com/office/the-website-you-were-trying-to-reach-doesn-t-work-with-internet-explorer-8f5fc675-cd47-414c-9535-12821ddfc554?ui=en-US&rs=en-US&ad=US) page that explains why the site was redirected to Microsoft Edge.</span></span>

> [!NOTE]
> <span data-ttu-id="4d69f-136">리디렉션 후, 사용자는 Internet Explorer로 돌아가서 비호환 목록에 없는 사이트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-136">After a redirection users can go back to using Internet Explorer for sites that are not on the Internet Explorer incompatibility list.</span></span>  

## <a name="policies-to-configure-redirection-to-microsoft-edge"></a><span data-ttu-id="4d69f-137">Microsoft Edge로의 리디렉션 구성 정책</span><span class="sxs-lookup"><span data-stu-id="4d69f-137">Policies to configure redirection to Microsoft Edge</span></span>

> [!NOTE]
> <span data-ttu-id="4d69f-138">이러한 정책은 2020년 10월 26일까지 ADMX 파일 업데이트로 제공될 예정이며 2020년 11월 9일까지 Intune에서 제공될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-138">These policies will be available as ADMX file updates by October 26, 2020 and will be available in Intune by November 9, 2020.</span></span>

<span data-ttu-id="4d69f-139">Microsoft Edge로의 자동 리디렉션을 사용하려면 세 가지 그룹 정책을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-139">Three group policies must be configured to enable automatic redirection to Microsoft Edge.</span></span> <span data-ttu-id="4d69f-140">이들 정책은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-140">These policies are:</span></span>

- <span data-ttu-id="4d69f-141">RedirectSitesFromInternetExplorerPreventBHOInstall</span><span class="sxs-lookup"><span data-stu-id="4d69f-141">RedirectSitesFromInternetExplorerPreventBHOInstall</span></span>
- <span data-ttu-id="4d69f-142">RedirectSitesFromInternetExplorerRedirectMode</span><span class="sxs-lookup"><span data-stu-id="4d69f-142">RedirectSitesFromInternetExplorerRedirectMode</span></span>
- <span data-ttu-id="4d69f-143">HideInternetExplorerRedirectUXForIncompatibleSitesEnabled</span><span class="sxs-lookup"><span data-stu-id="4d69f-143">HideInternetExplorerRedirectUXForIncompatibleSitesEnabled</span></span>

### <a name="policy-redirectsitesfrominternetexplorerpreventbhoinstall"></a><span data-ttu-id="4d69f-144">정책: RedirectSitesFromInternetExplorerPreventBHOInstall</span><span class="sxs-lookup"><span data-stu-id="4d69f-144">Policy: RedirectSitesFromInternetExplorerPreventBHOInstall</span></span>

<span data-ttu-id="4d69f-145">Internet Explorer에서 Microsoft Edge로 리디렉션하는 경우 "IEtoEdge BHO" 라는 Internet Explorer BHO(브라우저 도우미 개체)가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-145">Redirection from Internet Explorer to Microsoft Edge requires an Internet Explorer Browser Helper Object (BHO) named "IEtoEdge BHO".</span></span> <span data-ttu-id="4d69f-146">**RedirectSitesFromInternetExplorerPreventBHOInstall** 정책은 이 BHO의 설치 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-146">The **RedirectSitesFromInternetExplorerPreventBHOInstall** policy controls whether or not this BHO is installed.</span></span>  

- <span data-ttu-id="4d69f-147">이 정책을 사용하도록 설정하면 리디렉션에 필요한 BHO가 설치되지 않고 사용자는 Internet Explorer에서 특정 웹 사이트에 대한 비호환 메시지를 계속해서 보게됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-147">If you enable this policy, the BHO required for redirection will not be installed and your users will continue to see incompatibility messages for certain websites on Internet Explorer.</span></span> <span data-ttu-id="4d69f-148">BHO가 이미 설치되어 있는 경우, 다음에 Microsoft Edge 안정 채널이 업데이트될 때 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-148">If the BHO is already installed, it will be uninstalled the next time the Microsoft Edge Stable channel is updated.</span></span>
- <span data-ttu-id="4d69f-149">이 정책을 사용하지 않도록 설정하거나 구성하지 않으면 BHO가 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-149">If you disable or don't configure this policy, the BHO will be installed.</span></span> <span data-ttu-id="4d69f-150">이것이 기본 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-150">This is the default behavior.</span></span>

<span data-ttu-id="4d69f-151">BHO를 필요로 하는 것 외에도 "호환되지 않는 사이트 Sitelist에 따라 사이트를 리디렉션" 또는 "구성되지 않음"으로 설정해야 하는 **RedirectSitesFromInternetExplorerRedirectMode**에 대한 종속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-151">In addition to needing the BHO, there is a dependency on the **RedirectSitesFromInternetExplorerRedirectMode**, which needs to be set to "Redirect sites based on the incompatible sites sitelist" or "Not Configured".</span></span>

### <a name="policy-redirectsitesfrominternetexplorerredirectmode"></a><span data-ttu-id="4d69f-152">정책: RedirectSitesFromInternetExplorerRedirectMode</span><span class="sxs-lookup"><span data-stu-id="4d69f-152">Policy: RedirectSitesFromInternetExplorerRedirectMode</span></span>

 <span data-ttu-id="4d69f-153">이 정책은 Microsoft Edge **기본 브라우저** 설정 "Internet Explorer가 Microsoft Edge에서 사이트를 열 수 있도록 허용"에 해당하는 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-153">This policy corresponds to the Microsoft Edge **Default browser** setting "Let Internet Explorer open sites in Microsoft Edge".</span></span> <span data-ttu-id="4d69f-154">*edge://settings/defaultbrowser* URL로 이동하여 이 설정에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-154">You can access this setting by going to the *edge://settings/defaultbrowser* URL.</span></span>  

- <span data-ttu-id="4d69f-155">이 정책을 구성하지 않거나 "Sitelist"로 설정하면 Internet Explorer에서 호환되지 않는 사이트를 Microsoft Edge로 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-155">If you don't configure this policy or set it to "Sitelist", Internet Explorer will redirect incompatible sites to Microsoft Edge.</span></span> <span data-ttu-id="4d69f-156">이것이 기본 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-156">This is the default behavior.</span></span>
- <span data-ttu-id="4d69f-157">이 정책을 사용하지 않도록 설정하려면 **사용**을 선택하고 옵션 아래의 드롭다운 목록, Internet Explorer에서 Microsoft Edge로 호환되지 않는 사이트를 리디렉션에서 **사용 안 함**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-157">To disable this policy, select **Enabled** AND then in the dropdown under Options: Redirect incompatible sites from Internet Explorer to Microsoft Edge, select **Disable**.</span></span> <span data-ttu-id="4d69f-158">이 상태에서는 호환되지 않는 사이트가 Microsoft Edge로 리디렉션되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-158">In this state, incompatible sites aren't redirected to Microsoft Edge.</span></span>

> [!NOTE]
> <span data-ttu-id="4d69f-159">조직에서 관리하지 않는 개인 장치를 사용하고 있는 경우, **Internet Explorer 호환성**에서 "사이트가 Internet Explorer 모드에서 로드되도록 허용"이라는 다른 설정을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-159">If you're on a personal device that isn't  managed by your organization, you'll see another setting named "Allow sites to be loaded in Internet Explorer mode" under **Internet Explorer compatibility**.</span></span>
>
><span data-ttu-id="4d69f-160">도메인에 연결되었거나 MDM(모바일 장치 관리)에 등록된 장치를 사용하는 경우에는 이 옵션이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-160">If you're on a domain joined or Mobile Device Management (MDM) enrolled device, you won't see this option.</span></span>
>
> <span data-ttu-id="4d69f-161">대신 사용자가 Internet Explorer 모드에서 사이트를 로드할 수 있게 하려는 경우에는 [Internet Explorer 모드 테스트 허용](./microsoft-edge-policies.md#intranetredirectbehavior) 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-161">Instead, if you want to let your users load sites in Internet Explorer mode, you can do so by configuring the policy [Allow Internet Explorer mode testing](./microsoft-edge-policies.md#intranetredirectbehavior).</span></span>

### <a name="policy-hideinternetexplorerredirectuxforincompatiblesitesenabled"></a><span data-ttu-id="4d69f-162">정책: HideInternetExplorerRedirectUXForIncompatibleSitesEnabled</span><span class="sxs-lookup"><span data-stu-id="4d69f-162">Policy: HideInternetExplorerRedirectUXForIncompatibleSitesEnabled</span></span>

<span data-ttu-id="4d69f-163">이 정책은 Microsoft Edge로의 호환되지 않는 사이트 리디렉션에 대한 사용자 환경을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-163">This policy configures the user experience for incompatible site redirection to Microsoft Edge.</span></span>  

- <span data-ttu-id="4d69f-164">이 정책을 사용하도록 설정하면 사용자에게 일회성 리디렉션 대화 상자와 리디렉션 배너가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-164">If you enable this policy, users never see the one-time redirection dialog and the redirection banner.</span></span> <span data-ttu-id="4d69f-165">어떠한 브라우저 데이터나 사용자 기본 설정도 가져오지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-165">No browser data or user preferences are imported.</span></span>
- <span data-ttu-id="4d69f-166">이 정책을 사용하지 않도록 설정하거나 구성하지 않으면 최초 리디렉션 시 리디렉션 대화 상자가 표시되고 리디렉션으로 시작하는 세션에 대해서는 영구적인 리디렉션 배너가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-166">If you disable or don't configure this policy, the redirection dialog will be shown on the first redirection and the persistent redirection banner will be shown for sessions that start with a redirection.</span></span>

  > [!NOTE]
  > <span data-ttu-id="4d69f-167">사용자가 새 리디렉션에 직면할 때마다 사용자 검색 데이터를 가져오게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-167">User browsing data will be imported every time a user encounters a new redirection.</span></span> <span data-ttu-id="4d69f-168">그러나 이는 사용자가 일회성 리디렉션 대화 상자에서 가져오기에 동의한 경우에만 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-168">However, this only happens if the user consented to the import on the one-time redirection dialog.</span></span>

## <a name="disable-redirection-to-microsoft-edge"></a><span data-ttu-id="4d69f-169">Microsoft Edge로의 리디렉션 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="4d69f-169">Disable redirection to Microsoft Edge</span></span>

<span data-ttu-id="4d69f-170">Microsoft Edge 안정 버전 87로 업데이트하기 전에 리디렉션을 사용하지 않도록 설정하려면 다음 단계를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-170">If you want to disable redirection BEFORE updating to Microsoft Edge Stable version 87, use the following step:</span></span>

1. <span data-ttu-id="4d69f-171">**RedirectSitesFromInternetExplorerPreventBHOInstall** 정책을 **사용**으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-171">Set the **RedirectSitesFromInternetExplorerPreventBHOInstall** policy to **Enabled**.</span></span>

<span data-ttu-id="4d69f-172">Microsoft Edge 안정 버전 87로 업데이트한 후에 리디렉션을 사용하지 않도록 설정하려면 다음 단계를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-172">If you want to disable redirection AFTER updating to Microsoft Edge Stable version 87, use the following steps:</span></span>

1. <span data-ttu-id="4d69f-173">**RedirectSitesFromInternetExplorerRedirectMode** 정책을 **사용**으로 선택하고 옵션 아래의 드롭다운 목록, Internet Explorer에서 Microsoft Edge로 호환되지 않는 사이트를 리디렉션에서 **사용 안 함**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-173">Set the **RedirectSitesFromInternetExplorerRedirectMode** policy to **Enabled** AND then in the dropdown under Options: Redirect incompatible sites from Internet Explorer to Microsoft Edge, select **Disable**.</span></span> <span data-ttu-id="4d69f-174">이 설정은 정책이 적용되는 즉시 리디렉션을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-174">This setting will stop redirecting as soon as the policy takes effect.</span></span>
2. <span data-ttu-id="4d69f-175">**RedirectSitesFromInternetExplorerPreventBHOInstall** 정책을 **사용**으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-175">Set the **RedirectSitesFromInternetExplorerPreventBHOInstall** policy to **Enabled**.</span></span> <span data-ttu-id="4d69f-176">이 설정은 다음 Microsoft Edge 업데이트 후에 BHO를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="4d69f-176">This will uninstall the BHO after the next Microsoft Edge update.</span></span>

## <a name="see-also"></a><span data-ttu-id="4d69f-177">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4d69f-177">See also</span></span>

- [<span data-ttu-id="4d69f-178">호환되지 않는 사이트 목록에 업데이트 요청</span><span class="sxs-lookup"><span data-stu-id="4d69f-178">Request updates to the incompatible sites list</span></span>](/microsoft-edge/web-platform/ie-to-microsoft-edge-redirection#request-an-update-to-the-ie-compatibility-list)
- [<span data-ttu-id="4d69f-179">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="4d69f-179">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="4d69f-180">Microsoft Edge 정책</span><span class="sxs-lookup"><span data-stu-id="4d69f-180">Microsoft Edge Policies</span></span>](./microsoft-edge-policies.md)