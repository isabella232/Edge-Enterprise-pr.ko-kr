---
title: Internet Explorer 모드에서 페이지 내 탐색 유지
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Internet Explorer 모드에서 페이지 내 탐색 유지
ms.openlocfilehash: 20b18d121c3babfaacffd4a08316b25be714d95e
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641364"
---
# <a name="keep-in-page-navigation-in-internet-explorer-mode"></a><span data-ttu-id="c5892-103">Internet Explorer 모드에서 페이지 내 탐색 유지</span><span class="sxs-lookup"><span data-stu-id="c5892-103">Keep in-page navigation in Internet Explorer mode</span></span>

<span data-ttu-id="c5892-104">이 정책을 임시 솔루션으로 사용하여 IE 모드(Internet Explorer 모드)에서 사이트의 모든 페이지 내 탐색을 IE 모드로 유지하도록 강제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5892-104">You can use this policy as a temporary solution to force all in-page navigation from Internet Explorer mode (IE mode) sites to stay in IE mode.</span></span>

<span data-ttu-id="c5892-105">페이지 내 탐색은 현재 페이지의 링크, 스크립트 또는 양식에서 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5892-105">An in-page navigation is started from a link, a script, or a form on the current page.</span></span> <span data-ttu-id="c5892-106">이전의 페이지 탐색 시도가 서버측으로 리디렉션될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5892-106">It can also be a server-side redirect of a previous in-page navigation attempt.</span></span> <span data-ttu-id="c5892-107">반대로 사용자는 브라우저 컨트롤을 사용하여 여러 가지 방법으로 현재 페이지와는 독립적인 페이지 내가 아닌 탐색을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5892-107">Conversely, a user can start a navigation that isn't in-page that's independent of the current page in several ways by using the browser controls.</span></span> <span data-ttu-id="c5892-108">예를 들어 주소 표시줄, 뒤로 단추 또는 즐겨찾기 링크를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c5892-108">For example, using the address bar, the back button, or a favorite link.</span></span>

>[!NOTE]
><span data-ttu-id="c5892-109">이 문서는 Microsoft Edge 버전 81 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5892-109">This article applies to Microsoft Edge version 81 or later.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c5892-110">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="c5892-110">Prerequisites</span></span>

<span data-ttu-id="c5892-111">이 정책에는 다음과 같은 Windows 업데이트가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c5892-111">The following Windows updates are required for this policy:</span></span>

- <span data-ttu-id="c5892-112">Windows 10 버전 1909 & 1903, Windows Server 버전 1909 & 1903 ([KB4532695](https://support.microsoft.com/help/4532695))</span><span class="sxs-lookup"><span data-stu-id="c5892-112">Windows 10 version 1909 & 1903, Windows Server version 1909 & 1903  ([KB4532695](https://support.microsoft.com/help/4532695))</span></span>
- <span data-ttu-id="c5892-113">Windows 10 버전 1809, Windows Server 버전 1809, Windows Server 2019 ([KB4534321](https://support.microsoft.com/help/4534321))</span><span class="sxs-lookup"><span data-stu-id="c5892-113">Windows 10 version 1809, Windows Server version 1809, Windows Server 2019 ([KB4534321](https://support.microsoft.com/help/4534321))</span></span>
- <span data-ttu-id="c5892-114">Windows 10 버전 1803 ([KB4534308](https://support.microsoft.com/help/4534308))</span><span class="sxs-lookup"><span data-stu-id="c5892-114">Windows 10 version 1803 ([KB4534308](https://support.microsoft.com/help/4534308))</span></span>
- <span data-ttu-id="c5892-115">Windows 10 버전 1709 ([KB4534318](https://support.microsoft.com/help/4534318))</span><span class="sxs-lookup"><span data-stu-id="c5892-115">Windows 10 version 1709 ([KB4534318](https://support.microsoft.com/help/4534318))</span></span>


## <a name="about-this-policy"></a><span data-ttu-id="c5892-116">이 정책 정보</span><span class="sxs-lookup"><span data-stu-id="c5892-116">About this policy</span></span>

<span data-ttu-id="c5892-117">이 정책은 IE 모드 사이트에서 사용하는 모든 인증 서버를 식별하고 구성할 시간을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c5892-117">This policy gives you time to identify and configure all of the authentication servers used by your IE mode sites.</span></span> <span data-ttu-id="c5892-118">그러나 이 정책을 통해 일부 사이트는 IE 모드로 렌더링되고 다른 사이트는 Microsoft Edge 모드로 렌더링되는 검색 환경이 일관되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5892-118">However, this policy can result in an inconsistent browsing experience, where some sites are rendered in IE mode and at other times rendered in Microsoft Edge mode.</span></span> <span data-ttu-id="c5892-119">이는 사이트 탐색이 IE 모드 페이지에서 시작되었는지에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="c5892-119">This experience depends on whether the navigation to the site began from an IE mode page.</span></span> <span data-ttu-id="c5892-120">특정 렌더링 엔진에서 열도록 명시적으로 구성되지 않은 사이트는 이 불일치의 영향을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5892-120">Any site that isn't explicitly configured to open in a specific rendering engine will be subject to this inconsistency.</span></span>

<span data-ttu-id="c5892-121">이 정책을 사용하도록 설정하는 경우 모든 인증 서버를 식별하고 이를 사이트 목록에 중립으로 추가한 후에는 정책을 해제하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c5892-121">If you enable this policy, we recommend that you disable it after you've identified all the authentication servers and added them to the site list as neutral.</span></span> <span data-ttu-id="c5892-122">이 작업을 수행하면 최신 사이트가 IE 모드로 절대 실수로 렌더링되는 일이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c5892-122">This action ensures that your modern sites never inadvertently render in IE mode.</span></span>

## <a name="keep-in-page-navigation-in-ie-mode"></a><span data-ttu-id="c5892-123">IE 모드에서 페이지 내 탐색 유지</span><span class="sxs-lookup"><span data-stu-id="c5892-123">Keep in-page navigation in IE mode</span></span>

<span data-ttu-id="c5892-124">Internet Explorer 모드에서 자동 또는 모든 페이지 내 탐색을 유지하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="c5892-124">To keep automatic or all in-page navigation in Internet Explorer mode, follow these steps:</span></span>

1. <span data-ttu-id="c5892-125">로컬 그룹 정책 편집기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c5892-125">Open Local Group Policy Editor.</span></span>
2. <span data-ttu-id="c5892-126">**컴퓨터 구성** > **관리 템플릿** > **Microsoft Edge**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c5892-126">Click **Computer Configuration** > **Administrative Templates** > **Microsoft Edge**.</span></span>
3. <span data-ttu-id="c5892-127">**설정**에서 **Internet Explorer 모드 페이지에서 시작할 때 구성되지 않은 사이트에 대한 "페이지 내" 탐색 동작 방법 지정**을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c5892-127">Under **Setting**, double-click **Specify how "in-page" navigations to unconfigured sites behave when started from Internet Explorer mode pages**.</span></span>

   ![페이지 내 정책 설정](media/edge-learnmore-inpage-nav/learnmore-in-page-nav-settings.png)

4. <span data-ttu-id="c5892-129">**사용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c5892-129">Select **Enabled**</span></span> 

   ![페이지 내 정책 활성화](media/edge-learnmore-inpage-nav/learnmore-in-page-nav-enable.png)

5. <span data-ttu-id="c5892-131">드롭다운 목록에서 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c5892-131">Choose one of the following options from the dropdown list:</span></span>

   - <span data-ttu-id="c5892-132">**기본** - Internet Explorer 모드에서 열도록 구성된 사이트만 해당 모드에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="c5892-132">**Default** - Only sites configured to open in Internet Explorer mode will open in that mode.</span></span> <span data-ttu-id="c5892-133">Internet Explorer 모드에서 열리도록 구성되지 않은 사이트는 Microsoft Edge로 다시 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5892-133">Any site not configured to open in Internet Explorer mode will be redirected back to Microsoft Edge.</span></span>
   - <span data-ttu-id="c5892-134">**Internet Explorer 모드에서 자동 탐색만 유지** - 구성되지 않은 사이트에 대한 모든 자동 탐색(예: 302 리디렉션)이 Internet Explorer 모드로 유지되는 것을 제외하고 기본 환경을 원할 경우 이 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c5892-134">**Keep only automatic navigations in Internet Explorer mode** - Use this option if you want the default experience except that all automatic navigations (such as 302 redirects) to unconfigured sites will be kept in Internet Explorer mode.</span></span>
   - <span data-ttu-id="c5892-135">**모든 페이지 내 탐색을 Internet Explorer 모드로 유지**  \* *_(최소 권장)_*_ - IE 모드로 로드된 페이지에서 구성되지 않은 사이트로의 모든 탐색은 Internet Explorer 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5892-135">**Keep all in-page navigation in Internet Explorer mode** \**_(Least Recommended)_*_ - All navigations from pages loaded in IE mode to unconfigured sites are kept in Internet Explorer mode.</span></span>

6. <span data-ttu-id="c5892-136">_*확인*\* 또는 **적용을 클릭하여** 정책 설정을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="c5892-136">Click _*OK*\* or **Apply** to save the policy settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="c5892-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c5892-137">See also</span></span>

- [<span data-ttu-id="c5892-138">Microsoft Edge Enterprise 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="c5892-138">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
