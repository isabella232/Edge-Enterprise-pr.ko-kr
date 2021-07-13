---
title: Internet Explorer 11 사용하지 않는 경우
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 07/09/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Internet Explorer 11을 사용하지 않도록 설정하고 Microsoft Edge에서 Internet Explorer 모드를 사용하는 방법을 알아봅니다.
ms.openlocfilehash: b70da0ff7437d1f5e70cec40e31211046a66205a
ms.sourcegitcommit: 2a00571483e1d169b2b3b59f4fce43262f460a9a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "11643753"
---
# <a name="disable-internet-explorer-11"></a><span data-ttu-id="9104b-103">Internet Explorer 11 사용하지 않는 경우</span><span class="sxs-lookup"><span data-stu-id="9104b-103">Disable Internet Explorer 11</span></span>

>[!Note]
> <span data-ttu-id="9104b-104">Internet Explorer 11 데스크톱 응용 프로그램은 2022년 6월 15일 사용 및 지원이 중단됩니다(범위 내 항목 목록은 [FAQ 참고](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)).</span><span class="sxs-lookup"><span data-stu-id="9104b-104">The Internet Explorer 11 desktop application will be retired and go out of support on June 15, 2022 (for a list of what’s in scope, [see the FAQ](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)).</span></span> <span data-ttu-id="9104b-105">현재 사용하는 동일한 IE11 앱과 사이트는 Internet Explorer 모드에서 Microsoft Edge로 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9104b-105">The same IE11 apps and sites you use today can open in Microsoft Edge with Internet Explorer mode.</span></span> <span data-ttu-id="9104b-106">[여기서 자세한 내용을 알아보세요](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/).</span><span class="sxs-lookup"><span data-stu-id="9104b-106">[Learn more here](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/).</span></span>

<span data-ttu-id="9104b-107">이 문서에서는 사용자 환경에서 Internet Explorer 11을 독립 실행형 브라우저로 사용하지 않도록 설정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9104b-107">This article describes how to disable Internet Explorer 11 as a standalone browser in your environment.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9104b-108">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="9104b-108">Prerequisites</span></span>

<span data-ttu-id="9104b-109">다음 Windows 업데이트와 Microsoft Edge 소프트웨어가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9104b-109">The following Windows updates and Microsoft Edge software are required:</span></span>

- <span data-ttu-id="9104b-110">Windows 업데이트</span><span class="sxs-lookup"><span data-stu-id="9104b-110">Windows updates</span></span>

  - <span data-ttu-id="9104b-111">Windows 10 버전 21H1 이상</span><span class="sxs-lookup"><span data-stu-id="9104b-111">Windows 10, version 21H1 or later</span></span>
  - <span data-ttu-id="9104b-112">Windows 10 버전 2004; Windows 서버 버전 2004; Windows 10 버전 20H2; Windows 서버 버전 20H2: [KB4598291](https://support.microsoft.com/topic/february-2-2021-kb4598291-os-builds-19041-789-and-19042-789-preview-6a766199-a4f1-616e-1f5c-58bdc3ca5e3b) 이상</span><span class="sxs-lookup"><span data-stu-id="9104b-112">Windows 10, version 2004; Windows Server version 2004; Windows 10, version 20H2; Windows Server version 20H2: [KB4598291](https://support.microsoft.com/topic/february-2-2021-kb4598291-os-builds-19041-789-and-19042-789-preview-6a766199-a4f1-616e-1f5c-58bdc3ca5e3b) or later</span></span>
  - <span data-ttu-id="9104b-113">Windows 10 버전 1909: [KB4598298](https://support.microsoft.com/topic/january-21-2021-kb4598298-os-build-18363-1350-preview-02dfd9ba-91a2-1b82-dede-42f288c02511) 이상</span><span class="sxs-lookup"><span data-stu-id="9104b-113">Windows 10 version 1909: [KB4598298](https://support.microsoft.com/topic/january-21-2021-kb4598298-os-build-18363-1350-preview-02dfd9ba-91a2-1b82-dede-42f288c02511) or later</span></span>
  - <span data-ttu-id="9104b-114">Windows Server 2019; Windows 10 Enterprise LTSC: [KB4598296](https://support.microsoft.com/topic/january-21-2021-kb4598296-os-build-17763-1728-preview-4c0931ff-45b7-ff59-5e00-c03b5afb363d) 이상</span><span class="sxs-lookup"><span data-stu-id="9104b-114">Windows Server 2019; Windows 10 Enterprise 2019 LTSC: [KB4598296](https://support.microsoft.com/topic/january-21-2021-kb4598296-os-build-17763-1728-preview-4c0931ff-45b7-ff59-5e00-c03b5afb363d) or later</span></span>
  - <span data-ttu-id="9104b-115">Windows Server 2016; Windows 10 Enterprise 2016 LTSB: [KB4601318](https://support.microsoft.com/topic/february-9-2021-kb4601318-os-build-14393-4225-c5e3de6c-e3e6-ffb5-6197-48b9ce16446e) 이상</span><span class="sxs-lookup"><span data-stu-id="9104b-115">Windows Server 2016; Windows 10 Enterprise 2016 LTSB: [KB4601318](https://support.microsoft.com/topic/february-9-2021-kb4601318-os-build-14393-4225-c5e3de6c-e3e6-ffb5-6197-48b9ce16446e) or later</span></span>
  - <span data-ttu-id="9104b-116">Windows 10 Enterprise 2015 LTSB: [KB4601331](https://support.microsoft.com/office/february-9-2021%e2%80%94kb4601331-os-build-10240-18842-6227d078-fef3-8d67-27e0-1882e6cb79ff?ui=en-US&rs=en-US&ad=US) 이상</span><span class="sxs-lookup"><span data-stu-id="9104b-116">Windows 10 Enterprise 2015 LTSB: [KB4601331](https://support.microsoft.com/office/february-9-2021%e2%80%94kb4601331-os-build-10240-18842-6227d078-fef3-8d67-27e0-1882e6cb79ff?ui=en-US&rs=en-US&ad=US) or later</span></span>
  - <span data-ttu-id="9104b-117">Windows 8.1; Windows Server 2012 R2: [KB4601384](https://support.microsoft.com/topic/february-9-2021-kb4601384-monthly-rollup-16bdbb75-dd4b-2910-abc5-7891c9756b96) 이상</span><span class="sxs-lookup"><span data-stu-id="9104b-117">Windows 8.1; Windows Server 2012 R2: [KB4601384](https://support.microsoft.com/topic/february-9-2021-kb4601384-monthly-rollup-16bdbb75-dd4b-2910-abc5-7891c9756b96) or later</span></span>
  - <span data-ttu-id="9104b-118">Windows Server 2012: [KB4601348](https://support.microsoft.com/topic/february-9-2021-kb4601348-monthly-rollup-2c338c0c-73d6-fb80-cc91-f1a86e80db0c) 이상</span><span class="sxs-lookup"><span data-stu-id="9104b-118">Windows Server 2012: [KB4601348](https://support.microsoft.com/topic/february-9-2021-kb4601348-monthly-rollup-2c338c0c-73d6-fb80-cc91-f1a86e80db0c) or later</span></span>
  
- <span data-ttu-id="9104b-119">Microsoft Edge 안정 채널</span><span class="sxs-lookup"><span data-stu-id="9104b-119">Microsoft Edge Stable Channel</span></span>


## <a name="overview"></a><span data-ttu-id="9104b-120">개요</span><span class="sxs-lookup"><span data-stu-id="9104b-120">Overview</span></span>

<span data-ttu-id="9104b-121">레거시 호환성을 위해 Internet Explorer 11(IE11)이 필요한 조직의 경우 Microsoft Edge의 IE 모드(Internet Explorer 모드)는 원활한 단일 브라우저 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9104b-121">For organizations that require Internet Explorer 11 (IE11) for legacy compatibility, Internet Explorer mode (IE mode) on Microsoft Edge provides a seamless, single browser experience.</span></span> <span data-ttu-id="9104b-122">사용자는 IE11로 다시 전환할 필요 없이 Microsoft Edge 내에서 기존 응용 프로그램에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9104b-122">Users can access legacy applications from within Microsoft Edge without having to switch back to IE11.</span></span>

<span data-ttu-id="9104b-123">IE 모드를 구성한 후에는 그룹 정책을 사용하여 조직 전체에서 **IE 모드 기능에 영향을 주지 않고** IE11을 독립 실행형 브라우저로 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9104b-123">After you configure IE mode, you can disable IE11 as a standalone browser **without affecting IE mode functionality** across your organization using group policy.</span></span>

> [!NOTE]
> <span data-ttu-id="9104b-124">특정 사이트에 대한 독립 실행형 IE11 앱이 필요하고 다른 모든 브라우저 트래픽을 Microsoft Edge로 리디렉션하려면 [사이트 목록에 포함되지 않은 모든 사이트를 Microsoft Edge로 보내기](./edge-ie-mode-policies.md#redirect-sites-from-ie-to-microsoft-edge) 정책을 구성하여 IE에서 Microsoft Edge로 사이트를 리디렉션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9104b-124">If you need the standalone IE11 app for specific sites, and want to redirect all other browser traffic to Microsoft Edge, you can configure the [Send all sites not included in the site list to Microsoft Edge](./edge-ie-mode-policies.md#redirect-sites-from-ie-to-microsoft-edge) policy to redirect sites from IE to Microsoft Edge.</span></span>

## <a name="user-experience-after-redirecting-traffic-to-microsoft-edge"></a><span data-ttu-id="9104b-125">Microsoft Edge로 트래픽을 리디렉션한 후의 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="9104b-125">User experience after redirecting traffic to Microsoft Edge</span></span>

<span data-ttu-id="9104b-126">**Internet Explorer 11을 독립 실행형 브라우저로 사용 안 함** 정책을 실행하면 모든 IE11 활동이 Microsoft Edge로 리디렉션되고 사용자는 다음과 같은 환경이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9104b-126">When you enable the **Disable Internet Explorer 11 as a standalone browser** policy, all IE11 activity is redirected to Microsoft Edge and users have the following experience:</span></span>

- <span data-ttu-id="9104b-127">시작 메뉴의 IE11 아이콘은 제거되지만 작업 표시줄의 아이콘은 그대로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="9104b-127">The IE11 icon on the Start Menu will be removed, but the one on the taskbar will remain.</span></span>
- <span data-ttu-id="9104b-128">사용자가 IE11을 사용하는 바로 가기 또는 파일 연결을 시작하려고 하면 Microsoft Edge에서 동일한 파일/URL을 열도록 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="9104b-128">When users try to launch shortcuts or file associations that use IE11, they will be redirected to open the same file/URL in Microsoft Edge.</span></span>
- <span data-ttu-id="9104b-129">사용자가 iexplore.exe 이진을 직접 호출하여 IE11을 실행하려고 하면 Microsoft Edge가 대신 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="9104b-129">When users try to launch IE11 by directly invoking the iexplore.exe binary, Microsoft Edge will launch instead.</span></span>

<span data-ttu-id="9104b-130">이 환경에 대한 정책 설정의 일부로 IE11을 실행하려는 각 사용자에 대한 리디렉션 메시지를 선택적으로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9104b-130">As part of setting the policy for this experience, you can optionally show a redirect message for each user who tries to launch IE11.</span></span> <span data-ttu-id="9104b-131">이 메시지는 "항상" 또는 "사용자당 한 번"을 표시하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9104b-131">This message can be set to display "Always" or "Once per user".</span></span> <span data-ttu-id="9104b-132">기본적으로 다음 스크린샷에 표시된 리디렉션 메시지는 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9104b-132">By default, the redirect message shown in the next screenshot is never shown.</span></span>

:::image type="content" source="media/edge-ie-disable-ie11/disable-ie-redirect-msg.png" alt-text="Microsoft Edge에 대한 리디렉션이 활성화된 후 IE를 열려고 할 때 알림.":::

<span data-ttu-id="9104b-134">엔터프라이즈 모드 사이트 목록에 IE11 앱에서 열도록 구성된 응용 프로그램이 있고 이 정책으로 IE11을 사용하지 않도록 설정한 경우 Microsoft Edge에서 IE 모드로 열립니다.</span><span class="sxs-lookup"><span data-stu-id="9104b-134">If your Enterprise Mode Site List contains applications that are configured to open in the IE11 app and you disable IE11 with this policy, they will open in IE mode on Microsoft Edge.</span></span>
> [!NOTE]
> <span data-ttu-id="9104b-135">사이트가 IE11 애플리케이션에서 열리도록 구성되고 IE11 사용 안 함 정책이 설정된 경우 사용자 흐름에 알려진 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9104b-135">There was a known issue with the user flow when a site is configured to open in the IE11 application and the disable IE11 policy is set.</span></span> <span data-ttu-id="9104b-136">이 문제는 Microsoft Edge 버전 91.0.840.0 이상에서 해결되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9104b-136">The issue has been fixed in Microsoft Edge versions 91.0.840.0 or later.</span></span>

## <a name="disable-internet-explorer-11-as-a-standalone-browser"></a><span data-ttu-id="9104b-137">Internet Explorer 11을 독립 실행형 브라우저로 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="9104b-137">Disable Internet Explorer 11 as a standalone browser</span></span>

<span data-ttu-id="9104b-138">그룹 정책을 사용하여 Internet Explorer 11을 사용하지 않도록 설정하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="9104b-138">To disable Internet Explorer 11 using group policy, follow these steps:</span></span>

1. <span data-ttu-id="9104b-139">필요한 운영 체제 업데이트가 필요한지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9104b-139">Ensure you have the pre-requisite operating system updates.</span></span> <span data-ttu-id="9104b-140">이 단계는 컴퓨터의 ADMX 파일을 직접 업데이트합니다(특히 inetres.adml 및 inetres.admx).</span><span class="sxs-lookup"><span data-stu-id="9104b-140">This step will update the ADMX files on your machine directly (specifically inetres.adml and inetres.admx).</span></span> <span data-ttu-id="9104b-141">중앙 저장소를 업데이트하려면 반드시 필요한 업데이트가 있는 컴퓨터의 .adml 및 .admx 파일을 복사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9104b-141">Please note that if you want to update your Central Store, you will need to copy over the .adml and .admx files from a machine that has the pre-requisite updates.</span></span> <span data-ttu-id="9104b-142">자세한 내용은 [중앙 저장소 만들기 및 관리](/troubleshoot/windows-client/group-policy/create-and-manage-central-store)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9104b-142">For more information, see [Create and manage Central Store](/troubleshoot/windows-client/group-policy/create-and-manage-central-store)</span></span>
2. <span data-ttu-id="9104b-143">그룹 정책 편집기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9104b-143">Open the Group Policy Editor.</span></span>
3. <span data-ttu-id="9104b-144">***Computer Configuration/Administrative Templates/Windows Components/Internet Explorer***로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9104b-144">Go to ***Computer Configuration/Administrative Templates/Windows Components/Internet Explorer***.</span></span> 
4. <span data-ttu-id="9104b-145"> *\*Internet Explorer 11을 독립 실행형 브라우저로 사용하지 않도록 설정*\*을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9104b-145">Double-click **Disable Internet Explorer 11 as a standalone browser**.</span></span>
5. <span data-ttu-id="9104b-146"> *\*사용*\*을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9104b-146">Select **Enabled**.</span></span>
6. <span data-ttu-id="9104b-147"> *\*옵션*\*에서 다음 값 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9104b-147">Under **Options**, pick one of the following values:</span></span>

   - <span data-ttu-id="9104b-148">IE11이 비활성화되었음을 사용자에게 알리지 않으려면 **절대** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9104b-148">**Never** if you don’t want to notify users that IE11 is disabled.</span></span>
   - <span data-ttu-id="9104b-149">사용자가 IE11에서 리다이렉션할 때 마다 알림을 보내려는 경우, **항상** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9104b-149">**Always** if you want to notify users every time they're redirected from IE11.</span></span>
   - <span data-ttu-id="9104b-150">처음 리디렉션될 때만 사용자에게 알리려는 경우 **사용자당 한 번** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9104b-150">**Once per user** if you want to notify users only the first time they are redirected.</span></span>

7. <span data-ttu-id="9104b-151"> *\*확인** 이나  *\*적용** 을 클릭하여 정책 설정을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="9104b-151">Click **OK** or **Apply** to save this policy setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="9104b-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9104b-152">See also</span></span>

- [<span data-ttu-id="9104b-153">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="9104b-153">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="9104b-154">IE 모드 정보</span><span class="sxs-lookup"><span data-stu-id="9104b-154">About IE mode</span></span>](./edge-ie-mode.md)
- [<span data-ttu-id="9104b-155">추가 엔터프라이즈 모드 정보</span><span class="sxs-lookup"><span data-stu-id="9104b-155">Additional Enterprise Mode information</span></span>](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
