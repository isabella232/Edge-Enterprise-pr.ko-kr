---
title: Microsoft Edge 엔드포인트에 대한 허용 목록
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 11/25/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 엔드포인트에 대한 허용 목록
ms.openlocfilehash: 3d46e2e8c85eadc39cf9788df44b45592ea4fb1b
ms.sourcegitcommit: ed6a5afabf909df87bec48671c4c47bcdfaeb7bc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2020
ms.locfileid: "11194695"
---
# <span data-ttu-id="be2e7-103">Microsoft Edge 엔드포인트에 대한 허용 목록</span><span class="sxs-lookup"><span data-stu-id="be2e7-103">Allow list for Microsoft Edge endpoints</span></span>

<span data-ttu-id="be2e7-104">Microsoft Edge 기능을 지원하려면 인터넷에 연결되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be2e7-104">Microsoft Edge requires connectivity to the Internet to support its features.</span></span> <span data-ttu-id="be2e7-105">이 문서에서는 방화벽 및 기타 보안 메커니즘을 통해 통신을 보장하기 위해 허용 목록에 추가해야 하는 도메인 URL에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="be2e7-105">This article identifies the domain URLs that you need to add to the Allow list to ensure communications through firewalls and other security mechanisms.</span></span>

> [!NOTE]
> <span data-ttu-id="be2e7-106">이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="be2e7-106">This applies  to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="be2e7-107">허용할 도메인 URL</span><span class="sxs-lookup"><span data-stu-id="be2e7-107">Domain URLs to allow</span></span>

<span data-ttu-id="be2e7-108">Microsoft Edge에 대해 다음 도메인 URL을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="be2e7-108">Allow the following domain URLs for Microsoft Edge.</span></span>

### <span data-ttu-id="be2e7-109">업데이트 서비스</span><span class="sxs-lookup"><span data-stu-id="be2e7-109">Update Service</span></span>

<span data-ttu-id="be2e7-110">Microsoft Edge에서 새 업데이트를 확인하는 데 사용하는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="be2e7-110">The service that Microsoft Edge uses to check for new updates.</span></span>

- `https://msedge.api.cdp.microsoft.com`

### <span data-ttu-id="be2e7-111">실험 및 구성 서비스</span><span class="sxs-lookup"><span data-stu-id="be2e7-111">Experimentation and Configuration service</span></span>

- `https://config.edge.skype.com`

### <span data-ttu-id="be2e7-112">Microsoft Edge의 다운로드 위치</span><span class="sxs-lookup"><span data-stu-id="be2e7-112">Download locations for Microsoft Edge</span></span>

<span data-ttu-id="be2e7-113">위치 Microsoft Edge는 처음 설치하는 동안 또는 업데이트를 사용할 수 있을 때 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be2e7-113">Locations Microsoft Edge can be downloaded from during an initial install or when an update is available.</span></span> <span data-ttu-id="be2e7-114">다운로드 위치는 업데이트 서비스에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="be2e7-114">The download location is determined by the Update Service.</span></span>

#### <span data-ttu-id="be2e7-115">HTTP</span><span class="sxs-lookup"><span data-stu-id="be2e7-115">HTTP</span></span>

- `http://msedge.f.tlu.dl.delivery.mp.microsoft.com`
- `http://msedge.f.dl.delivery.mp.microsoft.com`
- `http://msedge.b.tlu.dl.delivery.mp.microsoft.com`
- `http://msedge.b.dl.delivery.mp.microsoft.com`

#### <span data-ttu-id="be2e7-116">HTTPS</span><span class="sxs-lookup"><span data-stu-id="be2e7-116">HTTPS</span></span>

- `https://msedge.sf.tlu.dl.delivery.mp.microsoft.com`
- `https://msedge.sf.dl.delivery.mp.microsoft.com`
- `https://msedge.sb.tlu.dl.delivery.mp.microsoft.com`
- `https://msedge.sb.dl.delivery.mp.microsoft.com`

  > [!TIP]
  > <span data-ttu-id="be2e7-117">다운로드 위치 허용 목록을 단순화하려면 와일드 카드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be2e7-117">To simplify the allow list for download locations a wild card can be used:</span></span> `*.dl.delivery.mp.microsoft.com`

### <span data-ttu-id="be2e7-118">Microsoft Edge 확장 프로그램의 다운로드 위치</span><span class="sxs-lookup"><span data-stu-id="be2e7-118">Download locations for Microsoft Edge Extensions</span></span>

<span data-ttu-id="be2e7-119">위치 Microsoft Edge 확장 프로그램은 처음 설치하는 동안 또는 업데이트를 사용할 수 있을 때 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be2e7-119">Locations Microsoft Edge Extensions can be downloaded from during an initial install or when an update is available.</span></span> <span data-ttu-id="be2e7-120">다운로드 위치는 업데이트 서비스에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="be2e7-120">The download location is determined by the Update Service.</span></span>

#### <span data-ttu-id="be2e7-121">HTTP</span><span class="sxs-lookup"><span data-stu-id="be2e7-121">HTTP</span></span>

- `http://msedgeextensions.f.tlu.dl.delivery.mp.microsoft.com`
- `http://msedgeextensions.f.dl.delivery.mp.microsoft.com`
- `http://msedgeextensions.b.tlu.dl.delivery.mp.microsoft.com`
- `http://msedgeextensions.b.dl.delivery.mp.microsoft.com`

#### <span data-ttu-id="be2e7-122">HTTPS</span><span class="sxs-lookup"><span data-stu-id="be2e7-122">HTTPS</span></span>

- `https://msedgeextensions.sf.tlu.dl.delivery.mp.microsoft.com`
- `https://msedgeextensions.sf.dl.delivery.mp.microsoft.com`
- `https://msedgeextensions.sb.tlu.dl.delivery.mp.microsoft.com`
- `https://msedgeextensions.sb.dl.delivery.mp.microsoft.com`

  > [!TIP]
  > <span data-ttu-id="be2e7-123">다운로드 위치 허용 목록을 단순화하려면 와일드 카드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be2e7-123">To simplify the allow list for download locations a wild card can be used:</span></span> `*.dl.delivery.mp.microsoft.com`

### <span data-ttu-id="be2e7-124">선택적으로 다운로드 배달 최적화</span><span class="sxs-lookup"><span data-stu-id="be2e7-124">Optionally for Download Delivery Optimization</span></span>

<span data-ttu-id="be2e7-125">배달 최적화에 대한 자세한 내용은 [Windows 10 업데이트에 대한 배달 최적화](https://aka.ms/waas-do)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="be2e7-125">For information about delivery optimization, see [Delivery Optimization for Windows 10 updates](https://aka.ms/waas-do).</span></span>

- <span data-ttu-id="be2e7-126">클라이언트 및 서비스 간 통신: `*.do.dsp.mp.microsoft.com`(HTTP 포트 80, HTTPS 포트 443)</span><span class="sxs-lookup"><span data-stu-id="be2e7-126">Client to Service communication: `*.do.dsp.mp.microsoft.com` (HTTP Port 80, HTTPS Port 443)</span></span>
- <span data-ttu-id="be2e7-127">클라이언트 간 통신: 인바운드 트래픽에 TCP 포트 7680이 열려 있어야 함</span><span class="sxs-lookup"><span data-stu-id="be2e7-127">Client to Client communication: TCP port 7680 should be open for inbound traffic</span></span>

### <span data-ttu-id="be2e7-128">Sync</span><span class="sxs-lookup"><span data-stu-id="be2e7-128">Sync</span></span>

<span data-ttu-id="be2e7-129">이러한 엔드 포인트는 동기화된 데이터의 읽기 및 쓰기, 보안 데이터에 대한 권한 관리, 새 동기화 데이터가 사용 가능할 때 브라우저에 알림 등을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="be2e7-129">These endpoints manage the reading and writing of synced data, rights management for secure data, and notifying the browser when new sync data is available.</span></span>

- <span data-ttu-id="be2e7-130">Edge 동기화 서비스 엔드 포인트:</span><span class="sxs-lookup"><span data-stu-id="be2e7-130">Edge sync service endpoints:</span></span>

  - `https://edge-enterprise.activity.windows.com`
  - `https://edge.activity.windows.com`

- <span data-ttu-id="be2e7-131">Azure Information Protection 엔드 포인트:</span><span class="sxs-lookup"><span data-stu-id="be2e7-131">Azure Information Protection endpoints:</span></span>

  - `https://api.aadrm.com` <span data-ttu-id="be2e7-132">(대부분의 테넌트 경우)</span><span class="sxs-lookup"><span data-stu-id="be2e7-132">(for most tenants)</span></span>
  - `https://api.aadrm.de` <span data-ttu-id="be2e7-133">(독일의 테넌트 경우)</span><span class="sxs-lookup"><span data-stu-id="be2e7-133">(for tenants in Germany)</span></span>
  - `https://api.aadrm.cn` <span data-ttu-id="be2e7-134">(중국의 테넌트 경우)</span><span class="sxs-lookup"><span data-stu-id="be2e7-134">(for tenants in China)</span></span>

- [<span data-ttu-id="be2e7-135">Windows 알림 서비스 엔드 포인트</span><span class="sxs-lookup"><span data-stu-id="be2e7-135">Windows Notification Service endpoints</span></span>](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)

## <span data-ttu-id="be2e7-136">기타 브라우저 지원 서비스</span><span class="sxs-lookup"><span data-stu-id="be2e7-136">Other browser support services</span></span>

<span data-ttu-id="be2e7-137">추적 방지, 인증서 해지 목록 및 기타 브라우저 구성 요소 업데이트와 같은 브라우저 기능에 대한 메타데이터를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="be2e7-137">Provide metadata for browser features such as tracking protection, certificate revocation lists, and other browser component updates.</span></span> <span data-ttu-id="be2e7-138">다운로드 가능한 맞춤법 검사 사전과 광고를 차단하는 차단 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="be2e7-138">Provide downloadable spellcheck dictionaries and ad-blocking block lists.</span></span> <span data-ttu-id="be2e7-139">컬렉션, 자동 채우기 및 확장 프로그램 스토어와 같은 브라우저 기능을 지원하는 서비스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="be2e7-139">Provide services to support browser features such as collections, autofill, and extension store.</span></span>

- `http://edge.microsoft.com/`
- `https://edge.microsoft.com/`

## <span data-ttu-id="be2e7-140">기타 참조</span><span class="sxs-lookup"><span data-stu-id="be2e7-140">See also</span></span>

- [<span data-ttu-id="be2e7-141">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="be2e7-141">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="be2e7-142">Microsoft Edge 설명서 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="be2e7-142">Microsoft Edge documentation landing page</span></span>](https://docs.microsoft.com/DeployEdge/)
- [<span data-ttu-id="be2e7-143">Windows 10 Enterprise, 버전 1903에 대한 연결 엔드포인트 관리</span><span class="sxs-lookup"><span data-stu-id="be2e7-143">Manage connection endpoints for Windows 10 Enterprise, version 1903</span></span>](https://docs.microsoft.com/windows/privacy/manage-windows-1903-endpoints)
