---
title: Microsoft Edge 키오스크 모드
ms.author: brianalt
author: brianalt
manager: seanlynd
ms.date: 01/16/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 키오스크 모드
ms.openlocfilehash: 7a690820752b5361349bf394055a737bd8175215
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980750"
---
# <span data-ttu-id="192e9-103">Microsoft Edge 키오스크 모드</span><span class="sxs-lookup"><span data-stu-id="192e9-103">Microsoft Edge kiosk mode</span></span>

<span data-ttu-id="192e9-104">이 문서에서는 Microsoft Edge(버전 77 이상) 키오스크 모드 옵션에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="192e9-104">This article provides an overview of the Microsoft Edge (version 77 or later) kiosk mode options.</span></span> <span data-ttu-id="192e9-105">또한 레거시 Microsoft Edge 키오스크 모드(버전 45 및 이하)을 계속 사용해야 하는 작업에 대해서도 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="192e9-105">It also covers what's required to continue using Microsoft Edge Legacy kiosk mode (version 45 and earlier.)</span></span>

<span data-ttu-id="192e9-106">레거시 Microsoft Edge 키오스크 모드(버전 45 이하)에 대한 자세한 내용은 [Microsoft Edge 키오스크 모드 배포](https://aka.ms/edgekioskmode)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="192e9-106">For information about Microsoft Edge Legacy kiosk mode (version 45 and earlier) see [Deploy Microsoft Edge kiosk mode](https://aka.ms/edgekioskmode).</span></span>

## <span data-ttu-id="192e9-107">할당된 액세스 권한이 있는 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="192e9-107">Microsoft Edge with assigned access</span></span>

<span data-ttu-id="192e9-108">Microsoft Edge는 Windows 10에서 [다중 앱이 할당된 액세스](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps)로 실행할 수 있으며, 이는 레거시 Microsoft Edge "일반 검색" 키오스크 모드 유형에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="192e9-108">Microsoft Edge can be run with [multi-app assigned access](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps) on Windows 10, which is the equivalent of Microsoft Edge Legacy "Normal browsing” kiosk mode type.</span></span> <span data-ttu-id="192e9-109">다중 앱이 할당된 액세스 권한을 사용하여 Microsoft Edge를 구성하려면 [다중 앱 키오스크를 설정](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps)하는 방법에 대한 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="192e9-109">To configure Microsoft Edge with multi-app assigned access follow the instructions on how to [Set up a multi-app kiosk](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps).</span></span> <span data-ttu-id="192e9-110">Microsoft Edge 안정 채널에 대한 AUMID는 **MSEdge**입니다.</span><span class="sxs-lookup"><span data-stu-id="192e9-110">The AUMID for the Microsoft Edge Stable channel is **MSEdge**.</span></span>

<span data-ttu-id="192e9-111">다중 앱이 할당된 액세스 권한으로 Microsoft Edge를 사용하는 경우 [Microsoft Edge 브라우저 정책](microsoft-edge-policies.md)을 사용하여 사용자의 고유한 요구 사항에 맞게 검색 환경을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="192e9-111">When using Microsoft Edge with multi-app assigned access you can use the [Microsoft Edge browser policies](microsoft-edge-policies.md) to configure the browsing experience to meet your unique requirements.</span></span>

<span data-ttu-id="192e9-112">현재 Microsoft Edge는 단일 앱 할당 액세스에 대한 동일한 레거시 Microsoft Edge 키오스크 모드 유형 및 다중 앱 할당 액세스에서 "공개 검색" 키오스크 모드 유형을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="192e9-112">Today Microsoft Edge does not support the same Microsoft Edge Legacy kiosk mode types for single-app assigned access and the "Public browsing" kiosk mode type in multi-app assigned access.</span></span> <span data-ttu-id="192e9-113">단일 앱이 할당된 액세스 키오스크 디바이스에 대한 브라우저가 필요한 경우 [레거시 Microsoft Edge 키오스크 모드](https://aka.ms/edgekioskmode) 또는 [Microsoft 키오스크 브라우저 앱](https://www.microsoft.com/p/kiosk-browser/9ngb5s5xg2kp?activetab=pivot:overviewtab)을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="192e9-113">If you need a browser for your single-app assigned access kiosk device, we recommend using [Microsoft Edge Legacy kiosk mode](https://aka.ms/edgekioskmode) or the [Microsoft Kiosk Browser app](https://www.microsoft.com/p/kiosk-browser/9ngb5s5xg2kp?activetab=pivot:overviewtab).</span></span> 

## <span data-ttu-id="192e9-114">Microsoft Edge "--kiosk" 명령줄 매개 변수</span><span class="sxs-lookup"><span data-stu-id="192e9-114">Microsoft Edge “--kiosk” command line parameter</span></span>

<span data-ttu-id="192e9-115">"`--kiosk`" 명령줄 매개 변수를 사용하여 키오스크 모드에서 Microsoft Edge를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="192e9-115">You can launch Microsoft Edge in kiosk mode using the “`--kiosk`” command line parameter.</span></span> <span data-ttu-id="192e9-116">전체 화면 바로 가기 키가 비활성화(F11)되어 전체 화면에서 브라우저가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="192e9-116">This opens the browser in full screen with the full screen keyboard shortcut disabled (F11).</span></span> <span data-ttu-id="192e9-117">이 작업을 수행하려면 대상이 다음과 같이 설정된 바로 가기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="192e9-117">To accomplish this, create a shortcut with the target set to:</span></span><br>
*`"<local path>\msedge.exe" --kiosk http://bing.com`*

> [!NOTE]
> <span data-ttu-id="192e9-118">"`--kiosk`" 매개 변수는 사용자가 Windows 바로 가기 키에 액세스하는 것을 금지하지 않으며 다른 애플리케이션의 실행을 방해하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="192e9-118">The "`--kiosk`" parameter will not prevent the user from accessing Windows keyboard shortcuts and will not prevent other applications from running.</span></span> <span data-ttu-id="192e9-119">이러한 유형의 제어를 수행하려면 [Windows 10 키오스크를 만드는 AppLocker](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-applocker) 및 [키보드 필터](https://docs.microsoft.com/windows-hardware/customize/enterprise/keyboardfilter)를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="192e9-119">To accomplish this type of control, consider using [AppLocker to create a Windows 10 kiosk](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-applocker) and [Keyboard Filter](https://docs.microsoft.com/windows-hardware/customize/enterprise/keyboardfilter).</span></span>

<span data-ttu-id="192e9-120">키오스크 모드를 종료하고 브라우저를 닫으려면 Alt+F4를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="192e9-120">To exit kiosk mode and close the browser use alt+F4.</span></span>

## <span data-ttu-id="192e9-121">레거시 Microsoft Edge 키오스크 모드에 대한 지원</span><span class="sxs-lookup"><span data-stu-id="192e9-121">Support for Microsoft Edge Legacy kiosk mode</span></span>

<span data-ttu-id="192e9-122">Microsoft Edge 안정 채널의 새 버전이 설치되어 있는 경우 레거시 Microsoft Edge가 숨겨지고 레거시 Microsoft Edge를 시작하려고 시도하면 새 버전으로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="192e9-122">When the new version of Microsoft Edge Stable channel is installed, Microsoft Edge Legacy is hidden and all attempts to launch Microsoft Edge Legacy are redirected to the new version.</span></span> <span data-ttu-id="192e9-123">자세한 내용:</span><span class="sxs-lookup"><span data-stu-id="192e9-123">For information about:</span></span>

- <span data-ttu-id="192e9-124">Windows 업데이트 요구 사항은 [다음 버전 Microsoft Edge를 지원하기 위한 Windows 업데이트](microsoft-edge-sysupdate-windows-updates.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="192e9-124">Windows update requirements, see [Windows updates to support the next version of Microsoft Edge](microsoft-edge-sysupdate-windows-updates.md)</span></span> 
- <span data-ttu-id="192e9-125">Microsoft Edge를 설치한 후 레거시 Microsoft Edge에 액세스하려면 [새 버전의 Microsoft Edge를 설치한 후에 레거시 Microsoft Edge에 액세스](microsoft-edge-sysupdate-access-old-edge.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="192e9-125">Accessing Microsoft Edge Legacy after installing Microsoft Edge,  see [Access Microsoft Edge Legacy after installing the new version of Microsoft Edge](microsoft-edge-sysupdate-access-old-edge.md)</span></span>
 
<span data-ttu-id="192e9-126">키오스크 디바이스에서 레거시 Microsoft Edge 키오스크 모드를 계속 사용하려면 다음 작업 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="192e9-126">To continue using Microsoft Edge Legacy kiosk mode on your kiosk devices take one of the following actions:</span></span> 

- <span data-ttu-id="192e9-127">Microsoft Edge 안정 채널을 설치하거나 설치되도록 허용하려고 하거나, 키오스크 디바이스에 이미 설치되어 있는 경우 Microsoft Edge의 [Microsoft Edge 나란히 브라우저 환경 허용](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#allowsxs) 정책을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="192e9-127">If you plan to install Microsoft Edge Stable channel, want to allow it to be installed, or if it's already installed on your kiosk device deploy the Microsoft Edge [Allow Microsoft Edge Side by Side browser experience](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#allowsxs) policy.</span></span>
- <span data-ttu-id="192e9-128">Microsoft Edge 안정 채널이 키오스크 디바이스에 설치되지 않도록 하려면 안정 채널용 Microsoft Edge [설치 허용 기본값](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#allow-installation-default) 정책을 배포하거나 [차단 도구 키트를 사용하여 Microsoft Edge 자동 배달을 비활성화](microsoft-edge-blocker-toolkit.md)하는 것을 고려하십시오.</span><span class="sxs-lookup"><span data-stu-id="192e9-128">To prevent Microsoft Edge Stable channel from being installed on your kiosk devices deploy the Microsoft Edge [Allow installation default](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#allow-installation-default) policy for Stable channel or consider using the [Blocker toolkit to disable automatic delivery of Microsoft Edge](microsoft-edge-blocker-toolkit.md).</span></span> 

## <span data-ttu-id="192e9-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="192e9-129">See also</span></span>

- [<span data-ttu-id="192e9-130">Windows 데스크톱 버전에서 키오스크 및 디지털 서명 구성</span><span class="sxs-lookup"><span data-stu-id="192e9-130">Configure kiosks and digital signs on Windows desktop editions</span></span>](https://docs.microsoft.com/windows/configuration/kiosk-methods)
- [<span data-ttu-id="192e9-131">레거시 Microsoft Edge 키오스크 모드 배포</span><span class="sxs-lookup"><span data-stu-id="192e9-131">Deploy Microsoft Edge Legacy kiosk mode</span></span>](https://aka.ms/edgekioskmode) 
- [<span data-ttu-id="192e9-132">Microsoft Edge 배포 계획</span><span class="sxs-lookup"><span data-stu-id="192e9-132">Plan your deployment of Microsoft Edge</span></span>](deploy-edge-plan-deployment.md)
- [<span data-ttu-id="192e9-133">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="192e9-133">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
