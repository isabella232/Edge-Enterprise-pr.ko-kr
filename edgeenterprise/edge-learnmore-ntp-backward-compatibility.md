---
title: 엔터프라이즈 새 탭 페이지의 이전 버전과의 호환성
ms.author: ruchir
author: dan-wesley
manager: vwehren
ms.date: 10/28/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 엔터프라이즈 새 탭 페이지의 이전 버전과의 호환성
ms.openlocfilehash: c10671a6ec8e1ff4dcb0db3f3c085f82ae973122
ms.sourcegitcommit: af6ab070d0c09bca4a9cf505b107ed7e04839763
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/29/2020
ms.locfileid: "11144493"
---
# <span data-ttu-id="bef85-103">엔터프라이즈 새 탭 페이지의 이전 버전과의 호환성</span><span class="sxs-lookup"><span data-stu-id="bef85-103">Backwards compatibility for the Enterprise New tab page</span></span>

<span data-ttu-id="bef85-104">이 문서에서는 새 탭 페이지의 변경 내용과 사용자가 Microsoft Edge 버전 87 및 이전 버전과 호환하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bef85-104">This article describes the change to the New tab page and how users can be backwards compatible with Microsoft Edge version 87 and earlier.</span></span>

> [!NOTE]
> <span data-ttu-id="bef85-105">이 문서는 Microsoft Edge 버전 87 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bef85-105">This article applies to Microsoft Edge version 87 or later.</span></span>

## <span data-ttu-id="bef85-106">단일 엔드포인트에서 정보 피드</span><span class="sxs-lookup"><span data-stu-id="bef85-106">Information feeds from single endpoint</span></span>

<span data-ttu-id="bef85-107">새 버전의 엔터프라이즈 새 탭 페이지는 호환되는 Microsoft 365 콘텐츠를 MSN.com 엔드포인트를 통해 제공되는 업계와 관련된 호환되는 정보 피드와 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="bef85-107">The new version of the Enterprise New tab page combines compliant Microsoft 365 content with industry relevant and compliant information feeds that are served via the MSN.com endpoint.</span></span>

> [!NOTE]
> <span data-ttu-id="bef85-108">Office 365 콘텐츠는 원래 [Office.com](https://www.office.com) 도메인을 사용하여 서비스를 제공했습니다.</span><span class="sxs-lookup"><span data-stu-id="bef85-108">Office 365 content was originally served using the [Office.com](https://www.office.com) domain.</span></span>

<span data-ttu-id="bef85-109">조직에 MSN.com 도메인에 대한 액세스가 제한된 경우 사용자에게 이 [URL](https://ntp.msn.com)에 대한 액세스 권한을 부여하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bef85-109">If access to the MSN.com domain is restricted for your organization, we strongly recommend giving users access to this [url](https://ntp.msn.com).</span></span>

<span data-ttu-id="bef85-110">MSN 도메인에 대한 액세스를 설정하는 데 더 많은 시간이 필요한 경우에는 새 탭 페이지에 Microsoft 뉴스 또는 Office 365 피드 환경을 선택할 수 있게 하는 [NewTabPageSetFeedType](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bef85-110">If you need more time to enable access to the MSN domain, we recommend using the [NewTabPageSetFeedType](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagesetfeedtype), that lets you choose either the Microsoft News or Office 365 feed experience for the new tab page.</span></span>

### <span data-ttu-id="bef85-111">Office.com 계속 사용하기</span><span class="sxs-lookup"><span data-stu-id="bef85-111">Keep using Office.com</span></span>

 <span data-ttu-id="bef85-112">더 이상 사용되지 않는 Office.com 도메인을 계속 사용하도록 **NewTabPageSetFeedType** 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bef85-112">You can configure the **NewTabPageSetFeedType** policy to keep using the deprecated Office.com domain.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bef85-113">Microsoft Edge 버전 90이 릴리스되면 Office 365 콘텐츠를 제공하는 **NewTabPageSetFeedType** 정책과 Office.com 도메인의 작동이 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="bef85-113">The **NewTabPageSetFeedType** policy and the Office.com domain that serves Office 365 content will quit working when Microsoft Edge version 90 is released.</span></span>

<span data-ttu-id="bef85-114">다음 정책 설정은 엔터프라이즈 새 탭 페이지에서 Office.com 도메인의 Office 문서 콘텐츠를 렌더링하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef85-114">The following policy settings will force the Enterprise New tab page to render Office document content from the Office.com domain.</span></span>

- <span data-ttu-id="bef85-115">정책을 **필수**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bef85-115">Set the policy as **Mandatory**.</span></span>
- <span data-ttu-id="bef85-116">정책 매핑의 값을 **Office (1) = Office 365 피드 환경**으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bef85-116">Set the value of the policy mapping to **Office (1) = Office 365 feed experience**.</span></span>

<span data-ttu-id="bef85-117">Office.com 전환을 사용할 수 없는 경우에는 Microsoft에 연락하여 피드백을 보내주세요.</span><span class="sxs-lookup"><span data-stu-id="bef85-117">If the switch to the Office.com isn't possible, reach out and send us feedback.</span></span> <span data-ttu-id="bef85-118">또 다른 옵션은 [NewTabPageLocation](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagelocation)을 구성하여 조직에서 허용하는 엔드포인트 URL을 가리키도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bef85-118">Another option is to configure the [NewTabPageLocation](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagelocation) so it points to an endpoint URL that's allowed by your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="bef85-119">**NewTabPageLocation** 정책은 **NewTabPageSetFeedType** 정책도 구성된 경우 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="bef85-119">The **NewTabPageLocation** policy has precedence if the **NewTabPageSetFeedType** policy is also configured.</span></span>

## <span data-ttu-id="bef85-120">이제 엔터프라이즈 사용자가 내 피드를 통해 Microsoft 뉴스 콘텐츠를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bef85-120">Enterprise users will now get Microsoft news content via My Feed</span></span>

<span data-ttu-id="bef85-121">엔터프라이즈 새 탭 페이지에서는 Azure AD(azure Active Directory) 계정으로 로그인한 사용자에게 단일 보기로 **내 피드** 및 Office 365 콘텐츠의 업계 관련 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bef85-121">The Enterprise New tab page will offer industry relevant information in **My Feed** and Office 365 content in a single view for users signed in with their Azure Active Directory (Azure AD) account.</span></span> <span data-ttu-id="bef85-122">설정 플라이아웃에서 Microsoft 뉴스 옵션을 선택한 Azure AD(Azure Active Directory)로 로그인한 사용자의 경우 새 탭 페이지 보기가 **내 피드** 콘텐츠로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="bef85-122">For users signed in with their Azure Active Directory (Azure AD) who selected the Microsoft News option in the settings flyout, their new tab page view will be replaced with **My Feed** content.</span></span> <span data-ttu-id="bef85-123">브라우저에서 새 탭 페이지를 열면 다음 스크린샷에 나와 있는 예제와 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bef85-123">When they open a new tab page in the browser it will look like the example in the next screenshot.</span></span>

![내 피드에서 콘텐츠를 보여 주는 새 탭 페이지.](media/microsoft-edge-ntp-backward-compatibility/microsoft-edge-ntp-myfeed-view.png)

> [!NOTE]
> <span data-ttu-id="bef85-125">Azure AD로 로그인하지 않은 사용자는 새 탭을 열 때 계속해서 MSN 뉴스 피드를 보게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bef85-125">Users who aren't signed in with Azure AD will continue to see the MSN News feed when they open a new tab.</span></span>

## <span data-ttu-id="bef85-126">페이지 레이아웃</span><span class="sxs-lookup"><span data-stu-id="bef85-126">Page layout</span></span>

<span data-ttu-id="bef85-127">새 탭 페이지에 대한 변경으로 페이지 레이아웃에서 더 이상 두 가지 특정 콘텐츠 형식(Office 365 및 Microsoft 뉴스)을 제어하지 않아도 되므로 콘텐츠 토글을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bef85-127">With the changes to the New tab page, the Page layout no longer has to control two specific content types (Office 365 and Microsoft News), so the content toggle isn't available.</span></span> <span data-ttu-id="bef85-128">다음 스크린샷은 페이지 레이아웃의 플라이아웃을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bef85-128">The next screenshot shows the flyout for the Page layout.</span></span>

![새 탭 페이지의 페이지 레이아웃 보기.](media/microsoft-edge-ntp-backward-compatibility/microsoft-edge-ntp-page-layout.png)

<span data-ttu-id="bef85-130">조직에 연결되지 않은 Microsoft 뉴스 콘텐츠에 계속 액세스하려면 다른 브라우저 프로필을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef85-130">If you want to keep accessing Microsoft News content that isn't tied to your organization, you must use a different browser profile.</span></span> <span data-ttu-id="bef85-131">*edge://settings/profiles*로 이동하고 Azure AD 프로필에서 로그아웃합니다.</span><span class="sxs-lookup"><span data-stu-id="bef85-131">Go to  *edge://settings/profiles* and sign out of your Azure AD profile.</span></span> <span data-ttu-id="bef85-132">이 작업을 수행하면 엔터프라이즈 새 탭 페이지의 표준 보기가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bef85-132">This action will bring up the  standard view for the Enterprise new tab page.</span></span> 

## <span data-ttu-id="bef85-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bef85-133">See also</span></span>

- [<span data-ttu-id="bef85-134">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="bef85-134">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="bef85-135">Internet Explorer 11의 엔터프라이즈 모드</span><span class="sxs-lookup"><span data-stu-id="bef85-135">Enterprise Mode for Internet Explorer 11</span></span>](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
