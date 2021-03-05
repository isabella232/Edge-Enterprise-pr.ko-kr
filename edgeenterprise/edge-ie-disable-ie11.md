---
title: Internet Explorer 11 사용하지 않는 경우
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 03/04/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Internet Explorer 11을 사용하지 않도록 설정하고 Microsoft Edge에서 Internet Explorer 모드를 사용하는 방법을 알아봅니다.
ms.openlocfilehash: be52f33b091977aff0ca29a4e10d4fc6ea4be957
ms.sourcegitcommit: f63a30c3e64e9e57fd76b6675ddff1fc2bbbeac8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2021
ms.locfileid: "11393615"
---
# <a name="disable-internet-explorer-11"></a><span data-ttu-id="1fedd-103">Internet Explorer 11 사용하지 않는 경우</span><span class="sxs-lookup"><span data-stu-id="1fedd-103">Disable Internet Explorer 11</span></span>

<span data-ttu-id="1fedd-104">이 문서에서는 사용자 환경에서 Internet Explorer 11을 독립 실행형 브라우저로 사용하지 않도록 설정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1fedd-104">This article describes how to disable Internet Explorer 11 as a standalone browser in your environment.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1fedd-105">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="1fedd-105">Prerequisites</span></span>

<span data-ttu-id="1fedd-106">다음 Windows 업데이트와 Microsoft Edge 소프트웨어가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1fedd-106">The following Windows updates and Microsoft Edge software are required:</span></span>

- <span data-ttu-id="1fedd-107">Windows 업데이트</span><span class="sxs-lookup"><span data-stu-id="1fedd-107">Windows updates</span></span>

  - <span data-ttu-id="1fedd-108">Windows 10, 버전 2004, Windows Server 버전 2004, Windows 10, 버전 20H2: [KB4598291](https://support.microsoft.com/topic/february-2-2021-kb4598291-os-builds-19041-789-and-19042-789-preview-6a766199-a4f1-616e-1f5c-58bdc3ca5e3b) 이상</span><span class="sxs-lookup"><span data-stu-id="1fedd-108">Windows 10, version 2004, Windows Server version 2004, Windows 10, version 20H2: [KB4598291](https://support.microsoft.com/topic/february-2-2021-kb4598291-os-builds-19041-789-and-19042-789-preview-6a766199-a4f1-616e-1f5c-58bdc3ca5e3b) or later</span></span>
  - <span data-ttu-id="1fedd-109">Windows 10 버전 1909, Windows Server 버전 1909: [KB4598298](https://support.microsoft.com/topic/january-21-2021-kb4598298-os-build-18363-1350-preview-02dfd9ba-91a2-1b82-dede-42f288c02511) 이상</span><span class="sxs-lookup"><span data-stu-id="1fedd-109">Windows 10 version 1909, Windows Server version 1909: [KB4598298](https://support.microsoft.com/topic/january-21-2021-kb4598298-os-build-18363-1350-preview-02dfd9ba-91a2-1b82-dede-42f288c02511) or later</span></span>
  - <span data-ttu-id="1fedd-110">Windows 10, 버전 1809, Windows Server, 버전 1809 및 Windows Server 2019: [KB4598296](https://support.microsoft.com/topic/january-21-2021-kb4598296-os-build-17763-1728-preview-4c0931ff-45b7-ff59-5e00-c03b5afb363d) 이상</span><span class="sxs-lookup"><span data-stu-id="1fedd-110">Windows 10 version 1809, Windows Server version 1809, and Windows Server 2019: [KB4598296](https://support.microsoft.com/topic/january-21-2021-kb4598296-os-build-17763-1728-preview-4c0931ff-45b7-ff59-5e00-c03b5afb363d) or later</span></span>
  - <span data-ttu-id="1fedd-111">Windows 10, 버전 1607, Windows Server 2016: [KB4601318](https://support.microsoft.com/topic/february-9-2021-kb4601318-os-build-14393-4225-c5e3de6c-e3e6-ffb5-6197-48b9ce16446e) 이상</span><span class="sxs-lookup"><span data-stu-id="1fedd-111">Windows 10, version 1607, Windows Server 2016: [KB4601318](https://support.microsoft.com/topic/february-9-2021-kb4601318-os-build-14393-4225-c5e3de6c-e3e6-ffb5-6197-48b9ce16446e) or later</span></span>
   - <span data-ttu-id="1fedd-112">Windows 10 초기 버전(2015년 7월): [KB4601331](https://support.microsoft.com/office/february-9-2021%e2%80%94kb4601331-os-build-10240-18842-6227d078-fef3-8d67-27e0-1882e6cb79ff?ui=en-US&rs=en-US&ad=US) 이상</span><span class="sxs-lookup"><span data-stu-id="1fedd-112">Windows 10 initial version (July 2015): [KB4601331](https://support.microsoft.com/office/february-9-2021%e2%80%94kb4601331-os-build-10240-18842-6227d078-fef3-8d67-27e0-1882e6cb79ff?ui=en-US&rs=en-US&ad=US) or later</span></span>
  - <span data-ttu-id="1fedd-113">Windows 8.1: [KB4601384](https://support.microsoft.com/topic/february-9-2021-kb4601384-monthly-rollup-16bdbb75-dd4b-2910-abc5-7891c9756b96) 이상</span><span class="sxs-lookup"><span data-stu-id="1fedd-113">Windows 8.1: [KB4601384](https://support.microsoft.com/topic/february-9-2021-kb4601384-monthly-rollup-16bdbb75-dd4b-2910-abc5-7891c9756b96) or later</span></span>
  - <span data-ttu-id="1fedd-114">Windows Server 2012: [KB4601348](https://support.microsoft.com/topic/february-9-2021-kb4601348-monthly-rollup-2c338c0c-73d6-fb80-cc91-f1a86e80db0c) 이상</span><span class="sxs-lookup"><span data-stu-id="1fedd-114">Windows Server 2012: [KB4601348](https://support.microsoft.com/topic/february-9-2021-kb4601348-monthly-rollup-2c338c0c-73d6-fb80-cc91-f1a86e80db0c) or later</span></span>
  
- <span data-ttu-id="1fedd-115">Microsoft Edge 안정 채널</span><span class="sxs-lookup"><span data-stu-id="1fedd-115">Microsoft Edge Stable Channel</span></span>


## <a name="overview"></a><span data-ttu-id="1fedd-116">개요</span><span class="sxs-lookup"><span data-stu-id="1fedd-116">Overview</span></span>

<span data-ttu-id="1fedd-117">레거시 호환성을 위해 Internet Explorer 11(IE11)이 필요한 조직의 경우 Microsoft Edge의 IE 모드(Internet Explorer 모드)는 원활한 단일 브라우저 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1fedd-117">For organizations that require Internet Explorer 11 (IE11) for legacy compatibility, Internet Explorer mode (IE mode) on Microsoft Edge provides a seamless, single browser experience.</span></span> <span data-ttu-id="1fedd-118">사용자는 IE11로 다시 전환할 필요 없이 Microsoft Edge 내에서 기존 응용 프로그램에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fedd-118">Users can access legacy applications from within Microsoft Edge without having to switch back to IE11.</span></span>

<span data-ttu-id="1fedd-119">IE 모드를 구성한 후에는 그룹 정책을 사용하여 조직 전체에서 **IE 모드 기능에 영향을 주지 않고** IE11을 독립 실행형 브라우저로 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fedd-119">After you configure IE mode, you can disable IE11 as a standalone browser **without affecting IE mode functionality** across your organization using group policy.</span></span>

> [!NOTE]
> <span data-ttu-id="1fedd-120">특정 사이트에 대한 독립 실행형 IE11 앱이 필요하고 다른 모든 브라우저 트래픽을 Microsoft Edge로 리디렉션하려면 [사이트 목록에 포함되지 않은 모든 사이트를 Microsoft Edge로 보내기](https://docs.microsoft.com/deployedge/edge-ie-mode-policies#redirect-sites-from-ie-to-microsoft-edge) 정책을 구성하여 IE에서 Microsoft Edge로 사이트를 리디렉션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fedd-120">If you need the standalone IE11 app for specific sites, and want to redirect all other browser traffic to Microsoft Edge, you can configure the [Send all sites not included in the site list to Microsoft Edge](https://docs.microsoft.com/deployedge/edge-ie-mode-policies#redirect-sites-from-ie-to-microsoft-edge) policy to redirect sites from IE to Microsoft Edge.</span></span>

## <a name="user-experience-after-redirecting-traffic-to-microsoft-edge"></a><span data-ttu-id="1fedd-121">Microsoft Edge로 트래픽을 리디렉션한 후의 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="1fedd-121">User experience after redirecting traffic to Microsoft Edge</span></span>

<span data-ttu-id="1fedd-122">**Internet Explorer 11을 독립 실행형 브라우저로 사용 안 함** 정책을 실행하면 모든 IE11 활동이 Microsoft Edge로 리디렉션되고 사용자는 다음과 같은 환경이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1fedd-122">When you enable the **Disable Internet Explorer 11 as a standalone browser** policy, all IE11 activity is redirected to Microsoft Edge and users have the following experience:</span></span>

- <span data-ttu-id="1fedd-123">시작 메뉴의 IE11 아이콘은 제거되지만 작업 표시줄의 아이콘은 그대로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="1fedd-123">The IE11 icon on the Start Menu will be removed, but the one on the taskbar will remain.</span></span>
- <span data-ttu-id="1fedd-124">사용자가 IE11을 사용하는 바로 가기 또는 파일 연결을 시작하려고 하면 Microsoft Edge에서 동일한 파일/URL을 열도록 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="1fedd-124">When users try to launch shortcuts or file associations that use IE11, they will be redirected to open the same file/URL in Microsoft Edge.</span></span>
- <span data-ttu-id="1fedd-125">사용자가 iexplore.exe 이진을 직접 호출하여 IE11을 실행하려고 하면 Microsoft Edge가 대신 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="1fedd-125">When users try to launch IE11 by directly invoking the iexplore.exe binary, Microsoft Edge will launch instead.</span></span>

<span data-ttu-id="1fedd-126">이 환경에 대한 정책 설정의 일부로 IE11을 실행하려는 각 사용자에 대한 리디렉션 메시지를 선택적으로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fedd-126">As part of setting the policy for this experience, you can optionally show a redirect message for each user who tries to launch IE11.</span></span> <span data-ttu-id="1fedd-127">이 메시지는 "항상" 또는 "사용자당 한 번"을 표시하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fedd-127">This message can be set to display "Always" or "Once per user".</span></span> <span data-ttu-id="1fedd-128">기본적으로 다음 스크린샷에 표시된 리디렉션 메시지는 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1fedd-128">By default, the redirect message shown in the next screenshot is never shown.</span></span>

:::image type="content" source="media/edge-ie-disable-ie11/disable-ie-redirect-msg.png" alt-text="Microsoft Edge에 대한 리디렉션이 활성화된 후 IE를 열려고 할 때 알림.":::

<span data-ttu-id="1fedd-130">엔터프라이즈 모드 사이트 목록에 IE11 앱에서 열도록 구성된 응용 프로그램이 있고 이 정책으로 IE11을 사용하지 않도록 설정한 경우 Microsoft Edge에서 IE 모드로 열립니다.</span><span class="sxs-lookup"><span data-stu-id="1fedd-130">If your Enterprise Mode Site List contains applications that are configured to open in the IE11 app and you disable IE11 with this policy, they will open in IE mode on Microsoft Edge.</span></span>
> [!NOTE]
> <span data-ttu-id="1fedd-131">사이트가 IE11에서 열리도록 구성되고 IE11 사용 안 함 정책이 설정된 경우 사용자 흐름에 알려진 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fedd-131">There is a known issue with the user flow when a site is configured to open in IE11 and the disable IE11 policy is set.</span></span> <span data-ttu-id="1fedd-132">현재 이 문제를 조사 중입니다.</span><span class="sxs-lookup"><span data-stu-id="1fedd-132">The issue being actively investigated.</span></span>

## <a name="disable-internet-explorer-11-as-a-standalone-browser"></a><span data-ttu-id="1fedd-133">Internet Explorer 11을 독립 실행형 브라우저로 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="1fedd-133">Disable Internet Explorer 11 as a standalone browser</span></span>

<span data-ttu-id="1fedd-134">그룹 정책을 사용하여 Internet Explorer 11을 사용하지 않도록 설정하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="1fedd-134">To disable Internet Explorer 11 using group policy, follow these steps:</span></span>

1. <span data-ttu-id="1fedd-135">최신  [Microsoft Edge 정책 문서 서식 파일](https://www.microsoft.com/edge/business/download)을 다운로드하고 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="1fedd-135">Download and install the latest [Microsoft Edge Policy Template](https://www.microsoft.com/edge/business/download).</span></span>
2. <span data-ttu-id="1fedd-136">그룹 정책 편집기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1fedd-136">Open the Group Policy Editor.</span></span>
3. <span data-ttu-id="1fedd-137">***Computer Configuration/Administrative Templates/Windows Components/Internet Explorer***로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1fedd-137">Go to ***Computer Configuration/Administrative Templates/Windows Components/Internet Explorer***.</span></span> 
4. <span data-ttu-id="1fedd-138"> *\*Internet Explorer 11을 독립 실행형 브라우저로 사용하지 않도록 설정*\*을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1fedd-138">Double-click **Disable Internet Explorer 11 as a standalone browser**.</span></span>
5. <span data-ttu-id="1fedd-139"> *\*사용*\*을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1fedd-139">Select **Enabled**.</span></span>
6. <span data-ttu-id="1fedd-140"> *\*옵션*\*에서 다음 값 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fedd-140">Under **Options**, pick one of the following values:</span></span>

   - <span data-ttu-id="1fedd-141">IE11이 비활성화되었음을 사용자에게 알리지 않으려면 **절대** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1fedd-141">**Never** if you don’t want to notify users that IE11 is disabled.</span></span>
   - <span data-ttu-id="1fedd-142">사용자가 IE11에서 리다이렉션할 때 마다 알림을 보내려는 경우, **항상** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1fedd-142">**Always** if you want to notify users every time they're redirected from IE11.</span></span>
   - <span data-ttu-id="1fedd-143">처음 리디렉션될 때만 사용자에게 알리려는 경우 **사용자당 한 번** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1fedd-143">**Once per user** if you want to notify users only the first time they are redirected.</span></span>

7. <span data-ttu-id="1fedd-144"> *\*확인** 이나  *\*적용** 을 클릭하여 정책 설정을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="1fedd-144">Click **OK** or **Apply** to save this policy setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="1fedd-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1fedd-145">See also</span></span>

- [<span data-ttu-id="1fedd-146">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="1fedd-146">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="1fedd-147">IE 모드 정보</span><span class="sxs-lookup"><span data-stu-id="1fedd-147">About IE mode</span></span>](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [<span data-ttu-id="1fedd-148">추가 엔터프라이즈 모드 정보</span><span class="sxs-lookup"><span data-stu-id="1fedd-148">Additional Enterprise Mode information</span></span>](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
