---
title: Microsoft Edge 및 혼합 콘텐츠 다운로드
ms.author: collw
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge 및 혼합 콘텐츠 다운로드
ms.openlocfilehash: 4871b23145d365e814c5cf1cac7699044f3da35e
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642144"
---
# <a name="learn-about-microsoft-edge-and-mixed-content-downloads"></a><span data-ttu-id="e2485-103">Microsoft Edge 및 혼합 콘텐츠 다운로드 정보</span><span class="sxs-lookup"><span data-stu-id="e2485-103">Learn about Microsoft Edge and mixed content downloads</span></span>

<span data-ttu-id="e2485-104">이 문서에서는 혼합 콘텐츠 다운로드와 Microsoft Edge에서 이러한 다운로드를 처리하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e2485-104">This article explains mixed content downloads and how Microsoft Edge handles them.</span></span>

>[!NOTE]
><span data-ttu-id="e2485-105">이 문서는 Microsoft Edge 버전 85 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2485-105">This article applies to Microsoft Edge version 85 or later.</span></span>

## <a name="what-are-mixed-content-downloads"></a><span data-ttu-id="e2485-106">혼합 콘텐츠 다운로드란?</span><span class="sxs-lookup"><span data-stu-id="e2485-106">What are mixed content downloads?</span></span>

<span data-ttu-id="e2485-107">보안 HTTPS 연결을 통해 로드된 HTML 페이지에서 다운로드를 시작할 때 혼합 콘텐츠 다운로드가 일어납니다. 단, 다음 조건에 부합해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2485-107">A mixed content download happens when you start a download from an HTML page that was loaded over a secure HTTPS connection, but one of the following conditions exists:</span></span>

- <span data-ttu-id="e2485-108">하나 이상의 다운로드 위치 리디렉션이 보안되지 않은 HTTP 연결을 통해 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2485-108">One or more of the download location's redirects was loaded over an insecure HTTP connection.</span></span>
- <span data-ttu-id="e2485-109">최종 다운로드 위치가 보안되지 않은 HTTP 연결을 통해 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2485-109">The final download location was loaded over an insecure HTTP connection.</span></span>

<span data-ttu-id="e2485-110">보안 HTTPS를 사용하여 요청이 이루어졌고 HTTP 및 HTTPS 콘텐츠가 모두 최종 다운로드 목적지에 도달하는 데 관여하였으므로 각각의 상황이 혼합 콘텐츠에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="e2485-110">Either scenario is a mixed content because the request was made using secure HTTPS and both HTTP and HTTPS content are involved in reaching the final download destination.</span></span> <span data-ttu-id="e2485-111">최신 브라우저는 액세스한 원본 페이지가 안전한 경우에도 다운로드가 안전하지 않게 전송될 수 있음을 사용자에게 보여주기 위해 이런 유형의 콘텐츠에 대한 경고를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="e2485-111">Modern browsers display warnings about this type of content to indicate to the user that this download may be transferred insecurely even though the original page accessed was secure.</span></span>

## <a name="download-warnings-and-user-options"></a><span data-ttu-id="e2485-112">다운로드 경고 및 사용자 옵션</span><span class="sxs-lookup"><span data-stu-id="e2485-112">Download warnings and user options</span></span>

<span data-ttu-id="e2485-113">다운로드 경고를 통해 사용자는 다운로드하는 파일을 네트워크에 있는 악의적인 공격자가 읽을 수 있음을 알게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2485-113">The download warning ensures that users know that the file they're downloading could be read by malicious attackers on their network.</span></span> <span data-ttu-id="e2485-114">사용자는 이 경고를 보고 파일을 다운로드할 것인지 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2485-114">This warning lets a user make an informed decision on whether to download the file.</span></span>

<span data-ttu-id="e2485-115">Microsoft Edge에서는 혼합 콘텐츠 다운로드가 차단되지만 사용자가 원하면 설정을 재정의하고 파일을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2485-115">In Microsoft Edge, mixed content downloads will be blocked but users can override and download the file if they want to.</span></span> <span data-ttu-id="e2485-116">Microsoft edge 버전 85부터는 혼합 콘텐츠 실행 파일 다운로드를 차단할 예정이며 이후 릴리스에서는 다양한 파일 형식을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="e2485-116">Microsoft Edge plans on starting to block mixed content executable file downloads starting with Microsoft Edge version 85 and will block different filetypes in future releases.</span></span>

> [!NOTE]
> <span data-ttu-id="e2485-117">이 기능 배포는 릴리스 일정 및 사용자 피드백에 따라 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2485-117">Deployment of this feature is subject to change based on release schedule and user feedback.</span></span>

<!-- The schedule of the block for different filetypes is to be determined and may be impacted by usage data and user feedback. -->

<span data-ttu-id="e2485-118">다운로드 선반의 차단 경고 메시지는 다음 스크린샷의 예와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e2485-118">In the download shelf, the block warning message looks like the example in the next screenshot.</span></span>

 ![다운로드 선반의 혼합 콘텐츠 경고](./media/edge-learnmore-mixed-content-downloads/edge-mixed-content-download-tray-warning.png)

<span data-ttu-id="e2485-120">다운로드 페이지의 차단 경고는 다음 스크린 샷의 예와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e2485-120">On the download page, the block warning looks like the following screenshot example:</span></span>

 ![혼합 콘텐츠 재정의 여부 확인 메시지](./media/edge-learnmore-mixed-content-downloads/edge-mixed-content-download-page-warning.png)

<span data-ttu-id="e2485-122">사용자가 계속 다운로드하기로 결정하면 해당 작업을 확인하는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2485-122">If a user decides to keep the download, they are prompted to confirm their action.</span></span> <span data-ttu-id="e2485-123">이 확인 메시지의 예가 다음 스크린샷에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2485-123">The next screenshot shows an example of this confirmation prompt.</span></span>

 ![Internet Explorer 모드 선택](./media/edge-learnmore-mixed-content-downloads/edge-mixed-content-download-override.png)

## <a name="supporting-policies"></a><span data-ttu-id="e2485-125">지원 정책</span><span class="sxs-lookup"><span data-stu-id="e2485-125">Supporting policies</span></span>

<span data-ttu-id="e2485-126">특정 웹 사이트로부터 혼합 콘텐츠가 차단되지 않도록 제외하려는 기업에서는 [InsecureContentAllowedForUrls](./microsoft-edge-policies.md#insecurecontentallowedforurls) 정책을 사용해 다운로드 가능하게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e2485-126">Enterprises that want to exclude mixed content blocking from specific websites can use the [InsecureContentAllowedForUrls](./microsoft-edge-policies.md#insecurecontentallowedforurls) policy to do so.</span></span>

## <a name="content-license"></a><span data-ttu-id="e2485-127">콘텐츠 라이선스</span><span class="sxs-lookup"><span data-stu-id="e2485-127">Content license</span></span>

> [!NOTE]
> <span data-ttu-id="e2485-128">이 페이지의 일부는 Chromium.org에서 생성 및 공유하고 [Creative Commons Attribution 4.0 국제 라이선스](http://creativecommons.org/licenses/by/4.0/)에 규정된 조건에 따라 사용되는 작업을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2485-128">Portions of this page are modifications based on work created and shared by Chromium.org and used according to terms described in the [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/).</span></span> <span data-ttu-id="e2485-129">원래 페이지는 [여기](https://developers.google.com/web/fundamentals/security/prevent-mixed-content/what-is-mixed-content)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2485-129">The original page can be found [here](https://developers.google.com/web/fundamentals/security/prevent-mixed-content/what-is-mixed-content).</span></span>
  
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br /><span data-ttu-id="e2485-130">이 작업은 <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 국제 라이선스</a>에서 사용이 허가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e2485-130">This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.</span></span>

## <a name="see-also"></a><span data-ttu-id="e2485-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e2485-131">See also</span></span>

- [<span data-ttu-id="e2485-132">Microsoft Edge Enterprise 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="e2485-132">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)