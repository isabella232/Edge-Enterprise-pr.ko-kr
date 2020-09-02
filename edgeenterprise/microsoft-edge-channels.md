---
title: Microsoft Edge 채널 개요
ms.author: srugh
author: srugh
manager: seanlynd
ms.date: 01/13/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 채널 개요
ms.openlocfilehash: 4de456909df3cb5140abfb20ddb884ad9cc84c32
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980749"
---
# <span data-ttu-id="4f874-103">Microsoft Edge 채널의 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="4f874-103">Overview of the Microsoft Edge channels</span></span>

<span data-ttu-id="4f874-104">다음 버전의 Microsoft Edge의 혜택 중 하나는 Microsoft는 정기적으로 새로운 기능을 제공할 수 있다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="4f874-104">One of the benefits of the next version of Microsoft Edge is that Microsoft can provide new features on a regular basis.</span></span> <span data-ttu-id="4f874-105">그러나 관리자가 조직의 사용자에게 Microsoft Edge를 배포하는 경우 사용자가 새 기능을 사용할 수 있는 빈도를 보다 강력하게 제어할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f874-105">However, as the admin who deploys Microsoft Edge to the users in your organization, you might want to have more control over how often your users get these new features.</span></span> <span data-ttu-id="4f874-106">Microsoft에서는 채널이라고 하는 네 가지 옵션을 제공하여 Microsoft Edge가 새 기능으로 업데이트되는 빈도를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f874-106">Microsoft provides you four options, called channels, to control how often Microsoft Edge is updated with new features.</span></span> <span data-ttu-id="4f874-107">네 가지 옵션에 대한 개요는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4f874-107">Here's an overview of the four options.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4f874-108">이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f874-108">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="4f874-109">채널 개요</span><span class="sxs-lookup"><span data-stu-id="4f874-109">Channel overview</span></span>

|<span data-ttu-id="4f874-110">채널</span><span class="sxs-lookup"><span data-stu-id="4f874-110">Channel</span></span>|<span data-ttu-id="4f874-111">기본 목적</span><span class="sxs-lookup"><span data-stu-id="4f874-111">Primary purpose</span></span>|<span data-ttu-id="4f874-112">새로운 기능으로 업데이트되는 빈도</span><span class="sxs-lookup"><span data-stu-id="4f874-112">How often updated with new features</span></span>|<span data-ttu-id="4f874-113">지원 여부</span><span class="sxs-lookup"><span data-stu-id="4f874-113">Supported?</span></span>|
|:---:|---|:---:|:---:|
|[<span data-ttu-id="4f874-114">안정</span><span class="sxs-lookup"><span data-stu-id="4f874-114">Stable</span></span>](#stable-channel)|<span data-ttu-id="4f874-115">광범위한 배포</span><span class="sxs-lookup"><span data-stu-id="4f874-115">Broad Deployment</span></span>|<span data-ttu-id="4f874-116">~6주</span><span class="sxs-lookup"><span data-stu-id="4f874-116">~6 weeks</span></span>|<span data-ttu-id="4f874-117">예</span><span class="sxs-lookup"><span data-stu-id="4f874-117">Yes</span></span>|
|[<span data-ttu-id="4f874-118">Beta</span><span class="sxs-lookup"><span data-stu-id="4f874-118">Beta</span></span>](#beta-channel)|<span data-ttu-id="4f874-119">조직의 대표 유효성 검증</span><span class="sxs-lookup"><span data-stu-id="4f874-119">Representative validation in the organization</span></span>|<span data-ttu-id="4f874-120">~6주</span><span class="sxs-lookup"><span data-stu-id="4f874-120">~6 weeks</span></span>|<span data-ttu-id="4f874-121">예</span><span class="sxs-lookup"><span data-stu-id="4f874-121">Yes</span></span>|
|[<span data-ttu-id="4f874-122">Dev</span><span class="sxs-lookup"><span data-stu-id="4f874-122">Dev</span></span>](#dev-channel)|<span data-ttu-id="4f874-123">계획 및 개발</span><span class="sxs-lookup"><span data-stu-id="4f874-123">Planning and developing</span></span>|<span data-ttu-id="4f874-124">매주</span><span class="sxs-lookup"><span data-stu-id="4f874-124">Weekly</span></span>|<span data-ttu-id="4f874-125">아니요</span><span class="sxs-lookup"><span data-stu-id="4f874-125">No</span></span>|
|[<span data-ttu-id="4f874-126">Canary</span><span class="sxs-lookup"><span data-stu-id="4f874-126">Canary</span></span>](#canary-channel)|<span data-ttu-id="4f874-127">최첨단 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="4f874-127">Bleeding edge content</span></span>|<span data-ttu-id="4f874-128">매일</span><span class="sxs-lookup"><span data-stu-id="4f874-128">Daily</span></span>|<span data-ttu-id="4f874-129">아니요</span><span class="sxs-lookup"><span data-stu-id="4f874-129">No</span></span>|

<span data-ttu-id="4f874-130">사용자에게 배포하기로 결정한 업데이트 채널은 사용자가 사용하고 업데이트된 Microsoft Edge 버전이 있을 때마다 테스트해야 하는 업무용 애플리케이션의 수 등 몇 가지 요인에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="4f874-130">Which update channel you decide to deploy to your users depends on several factors, such as how many line of business applications the user leverages and that you need to test any time they have an updated version of Microsoft Edge.</span></span> <span data-ttu-id="4f874-131">이러한 결정을 내리는 데 도움이 되도록 Microsoft Edge에 사용할 수 있는 네 가지 업데이트 채널에 대한 다음 정보를 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="4f874-131">To help you make this decision, review the following information about the four update channels that are available for Microsoft Edge.</span></span>

### <span data-ttu-id="4f874-132">안정 채널</span><span class="sxs-lookup"><span data-stu-id="4f874-132">Stable Channel</span></span>

<span data-ttu-id="4f874-133">안정 채널은 조직 내 광범위한 배포를 위한 것이며, 대부분의 사용자가 사용해야 하는 채널입니다.</span><span class="sxs-lookup"><span data-stu-id="4f874-133">The Stable Channel is intended for broad deployment in your organization, and it is the channel that most users should be on.</span></span> <span data-ttu-id="4f874-134">이는 가장 안정된 채널이며 이전 Beta 채널 릴리스에서 제공되는 기능 집합이 안정화된 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="4f874-134">It is the most stable of the channels and is the a result of the stabilization of the feature set available in the prior Beta Channel release.</span></span> <span data-ttu-id="4f874-135">새로운 기능은 6주에 한 번씩 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f874-135">New features ship about every 6 weeks.</span></span> <span data-ttu-id="4f874-136">필요한 경우 보안 및 품질 업데이트가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f874-136">Security and quality updates ship as needed.</span></span> <span data-ttu-id="4f874-137">채널에서 다음 릴리스가 제공될 때까지 안정 채널의 릴리스가 지원되는 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f874-137">A release from the Stable Channel is considered supported until the next release from the channel is available.</span></span>

### <span data-ttu-id="4f874-138">Beta 채널</span><span class="sxs-lookup"><span data-stu-id="4f874-138">Beta Channel</span></span>

<span data-ttu-id="4f874-139">Beta 채널은 조직에서 대표적인 샘플 사용자 집합에 대한 프로덕션 배포를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4f874-139">The Beta Channel is intended for production deployment in your organization to a representative sample set of users.</span></span> <span data-ttu-id="4f874-140">지원되는 릴리스이며, 이 채널의 다음 릴리스를 사용할 수 있을 때까지 Beta에서 각 릴리스가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f874-140">It is a supported release, and each release from Beta is supported until the next release from this channel is available.</span></span> <span data-ttu-id="4f874-141">이를 통해 사용자 환경에서 작업이 제대로 작동하는지 확인할 수 있으며, 릴리스 전에 안정 채널로 게시하기 전에 문제가 발생하는 경우 문제를 해결할 수 있는 좋은 기회입니다.</span><span class="sxs-lookup"><span data-stu-id="4f874-141">This is a great opportunity to validate that things work as expected in your environment, and if you encounter an issue have it remediated prior to the release going publishing to the Stable Channel.</span></span> <span data-ttu-id="4f874-142">새로운 기능은 6주에 한 번씩 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f874-142">New features ship about every 6 weeks.</span></span> <span data-ttu-id="4f874-143">필요한 경우 보안 및 품질 업데이트가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f874-143">Security and quality updates ship as needed.</span></span>

### <span data-ttu-id="4f874-144">Dev 채널</span><span class="sxs-lookup"><span data-stu-id="4f874-144">Dev Channel</span></span>

<span data-ttu-id="4f874-145">Dev 채널은 Microsoft Edge의 최신 기능을 사용하여 계획하고 개발하는 데 도움을 주기 위해 Canary 채널보다 높은 품질을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4f874-145">The Dev Channel is intended to help you plan and develop with the latest capabilities of Microsoft Edge, but with higher quality than the Canary Channel.</span></span> <span data-ttu-id="4f874-146">이를 통해 다음에 릴리스되는 항목을 조기에 확인하고 다음 Beta 릴리스를 준비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f874-146">This is your opportunity to get an early look at what is coming next and prepare for the next Beta release.</span></span>

### <span data-ttu-id="4f874-147">Canary 채널</span><span class="sxs-lookup"><span data-stu-id="4f874-147">Canary Channel</span></span>

<span data-ttu-id="4f874-148">Canary 채널은 매일 제공되며 모든 채널의 최첨단에 위치합니다.</span><span class="sxs-lookup"><span data-stu-id="4f874-148">The Canary Channel ships daily and is the most bleeding edge of all the channels.</span></span> <span data-ttu-id="4f874-149">최신 투자에 대한 액세스를 원하는 경우 여기에 먼저 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f874-149">If you want access to the newest investments then they will appear here first.</span></span> <span data-ttu-id="4f874-150">이 흐름의 특성으로 인해 문제가 발생하기 때문에 Canary 릴리스를 활용하는 경우 다른 채널을 나란히 설치해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f874-150">Because of the nature of this cadence problems will arise overtime, so you may want another channel installed side by side if you are leveraging the Canary releases.</span></span>

## <span data-ttu-id="4f874-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4f874-151">See also</span></span>

- [<span data-ttu-id="4f874-152">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="4f874-152">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="4f874-153">채널 다운로드</span><span class="sxs-lookup"><span data-stu-id="4f874-153">Channel downloads</span></span>](https://aka.ms/EdgeEnterprise)
