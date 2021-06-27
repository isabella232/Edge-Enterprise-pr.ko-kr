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
ms.openlocfilehash: b9a2190fdff860d9bacf975882469d936891973f
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2021
ms.locfileid: "11617808"
---
# <a name="overview-of-the-microsoft-edge-channels"></a><span data-ttu-id="60c04-103">Microsoft Edge 채널의 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="60c04-103">Overview of the Microsoft Edge channels</span></span>

<span data-ttu-id="60c04-104">다음 버전의 Microsoft Edge의 혜택 중 하나는 Microsoft는 정기적으로 새로운 기능을 제공할 수 있다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="60c04-104">One of the benefits of the next version of Microsoft Edge is that Microsoft can provide new features on a regular basis.</span></span> <span data-ttu-id="60c04-105">그러나 관리자가 조직의 사용자에게 Microsoft Edge를 배포하는 경우 사용자가 새 기능을 사용할 수 있는 빈도를 보다 강력하게 제어할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60c04-105">However, as the admin who deploys Microsoft Edge to the users in your organization, you might want to have more control over how often your users get these new features.</span></span> <span data-ttu-id="60c04-106">Microsoft에서는 채널이라고 하는 네 가지 옵션을 제공하여 Microsoft Edge가 새 기능으로 업데이트되는 빈도를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60c04-106">Microsoft provides you four options, called channels, to control how often Microsoft Edge is updated with new features.</span></span> <span data-ttu-id="60c04-107">네 가지 옵션에 대한 개요는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="60c04-107">Here's an overview of the four options.</span></span>

<span data-ttu-id="60c04-108">각 채널에 대한 지원에 대한 자세한 내용은 [Microsoft Edge 수명 주기](/deployedge/microsoft-edge-support-lifecycle)를 읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="60c04-108">For more information on support for each channel read: [Microsoft Edge Lifecycle](/deployedge/microsoft-edge-support-lifecycle)</span></span>
  
> [!NOTE]
> <span data-ttu-id="60c04-109">이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="60c04-109">This article applies to Microsoft Edge version 77 or later.</span></span>

## <a name="channel-overview"></a><span data-ttu-id="60c04-110">채널 개요</span><span class="sxs-lookup"><span data-stu-id="60c04-110">Channel overview</span></span>

|<span data-ttu-id="60c04-111">채널</span><span class="sxs-lookup"><span data-stu-id="60c04-111">Channel</span></span>|<span data-ttu-id="60c04-112">기본 목적</span><span class="sxs-lookup"><span data-stu-id="60c04-112">Primary purpose</span></span>|<span data-ttu-id="60c04-113">새로운 기능으로 업데이트되는 빈도</span><span class="sxs-lookup"><span data-stu-id="60c04-113">How often updated with new features</span></span>|<span data-ttu-id="60c04-114">지원 여부</span><span class="sxs-lookup"><span data-stu-id="60c04-114">Supported?</span></span>|
|:---:|---|:---:|:---:|
|[<span data-ttu-id="60c04-115">안정</span><span class="sxs-lookup"><span data-stu-id="60c04-115">Stable</span></span>](#stable-channel)|<span data-ttu-id="60c04-116">광범위한 배포</span><span class="sxs-lookup"><span data-stu-id="60c04-116">Broad Deployment</span></span>|<span data-ttu-id="60c04-117">~6주</span><span class="sxs-lookup"><span data-stu-id="60c04-117">~6 weeks</span></span>|<span data-ttu-id="60c04-118">예</span><span class="sxs-lookup"><span data-stu-id="60c04-118">Yes</span></span>|
|[<span data-ttu-id="60c04-119">Beta</span><span class="sxs-lookup"><span data-stu-id="60c04-119">Beta</span></span>](#beta-channel)|<span data-ttu-id="60c04-120">조직의 대표 유효성 검증</span><span class="sxs-lookup"><span data-stu-id="60c04-120">Representative validation in the organization</span></span>|<span data-ttu-id="60c04-121">~6주</span><span class="sxs-lookup"><span data-stu-id="60c04-121">~6 weeks</span></span>|<span data-ttu-id="60c04-122">예</span><span class="sxs-lookup"><span data-stu-id="60c04-122">Yes</span></span>|
|[<span data-ttu-id="60c04-123">Dev</span><span class="sxs-lookup"><span data-stu-id="60c04-123">Dev</span></span>](#dev-channel)|<span data-ttu-id="60c04-124">계획 및 개발</span><span class="sxs-lookup"><span data-stu-id="60c04-124">Planning and developing</span></span>|<span data-ttu-id="60c04-125">매주</span><span class="sxs-lookup"><span data-stu-id="60c04-125">Weekly</span></span>|<span data-ttu-id="60c04-126">아니요</span><span class="sxs-lookup"><span data-stu-id="60c04-126">No</span></span>|
|[<span data-ttu-id="60c04-127">Canary</span><span class="sxs-lookup"><span data-stu-id="60c04-127">Canary</span></span>](#canary-channel)|<span data-ttu-id="60c04-128">최첨단 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="60c04-128">Bleeding edge content</span></span>|<span data-ttu-id="60c04-129">매일</span><span class="sxs-lookup"><span data-stu-id="60c04-129">Daily</span></span>|<span data-ttu-id="60c04-130">아니요</span><span class="sxs-lookup"><span data-stu-id="60c04-130">No</span></span>|

<span data-ttu-id="60c04-131">사용자에게 배포하기로 결정한 업데이트 채널은 사용자가 사용하고 업데이트된 Microsoft Edge 버전이 있을 때마다 테스트해야 하는 업무용 애플리케이션의 수 등 몇 가지 요인에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="60c04-131">Which update channel you decide to deploy to your users depends on several factors, such as how many line of business applications the user leverages and that you need to test any time they have an updated version of Microsoft Edge.</span></span> <span data-ttu-id="60c04-132">이러한 결정을 내리는 데 도움이 되도록 Microsoft Edge에 사용할 수 있는 네 가지 업데이트 채널에 대한 다음 정보를 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="60c04-132">To help you make this decision, review the following information about the four update channels that are available for Microsoft Edge.</span></span>

### <a name="stable-channel"></a><span data-ttu-id="60c04-133">안정 채널</span><span class="sxs-lookup"><span data-stu-id="60c04-133">Stable Channel</span></span>

<span data-ttu-id="60c04-134">안정 채널은 조직 내 광범위한 배포를 위한 것이며, 대부분의 사용자가 사용해야 하는 채널입니다.</span><span class="sxs-lookup"><span data-stu-id="60c04-134">The Stable Channel is intended for broad deployment in your organization, and it is the channel that most users should be on.</span></span> <span data-ttu-id="60c04-135">이는 가장 안정된 채널이며 이전 Beta 채널 릴리스에서 제공되는 기능 집합이 안정화된 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="60c04-135">It is the most stable of the channels and is the a result of the stabilization of the feature set available in the prior Beta Channel release.</span></span> <span data-ttu-id="60c04-136">새로운 기능은 6주에 한 번씩 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="60c04-136">New features ship about every 6 weeks.</span></span> <span data-ttu-id="60c04-137">필요한 경우 보안 및 품질 업데이트가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="60c04-137">Security and quality updates ship as needed.</span></span> <span data-ttu-id="60c04-138">안정 채널의 릴리스는 채널에서 다음 릴리스를 사용할 수 있을 때까지 서비스됩니다.</span><span class="sxs-lookup"><span data-stu-id="60c04-138">A release from the Stable Channel is serviced until the next release from the channel is available.</span></span>

### <a name="beta-channel"></a><span data-ttu-id="60c04-139">Beta 채널</span><span class="sxs-lookup"><span data-stu-id="60c04-139">Beta Channel</span></span>

<span data-ttu-id="60c04-140">Beta 채널은 조직에서 대표적인 샘플 사용자 집합에 대한 프로덕션 배포를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="60c04-140">The Beta Channel is intended for production deployment in your organization to a representative sample set of users.</span></span> <span data-ttu-id="60c04-141">지원되는 릴리스이며, 이 채널의 다음 릴리스를 사용할 수 있을 때까지 Beta에서 각 릴리스가 서비스됩니다.</span><span class="sxs-lookup"><span data-stu-id="60c04-141">It is a supported release, and each release from Beta is serviced until the next release from this channel is available.</span></span> <span data-ttu-id="60c04-142">이를 통해 사용자 환경에서 작업이 제대로 작동하는지 확인할 수 있으며, 릴리스 전에 안정 채널로 게시하기 전에 문제가 발생하는 경우 문제를 해결할 수 있는 좋은 기회입니다.</span><span class="sxs-lookup"><span data-stu-id="60c04-142">This is a great opportunity to validate that things work as expected in your environment, and if you encounter an issue have it remediated prior to the release going publishing to the Stable Channel.</span></span> <span data-ttu-id="60c04-143">새로운 기능은 6주에 한 번씩 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="60c04-143">New features ship about every 6 weeks.</span></span> <span data-ttu-id="60c04-144">필요한 경우 보안 및 품질 업데이트가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="60c04-144">Security and quality updates ship as needed.</span></span>

### <a name="dev-channel"></a><span data-ttu-id="60c04-145">Dev 채널</span><span class="sxs-lookup"><span data-stu-id="60c04-145">Dev Channel</span></span>

<span data-ttu-id="60c04-146">Dev 채널은 Microsoft Edge의 최신 기능을 사용하여 계획하고 개발하는 데 도움을 주기 위해 Canary 채널보다 높은 품질을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="60c04-146">The Dev Channel is intended to help you plan and develop with the latest capabilities of Microsoft Edge, but with higher quality than the Canary Channel.</span></span> <span data-ttu-id="60c04-147">이를 통해 다음에 릴리스되는 항목을 조기에 확인하고 다음 Beta 릴리스를 준비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60c04-147">This is your opportunity to get an early look at what is coming next and prepare for the next Beta release.</span></span>

### <a name="canary-channel"></a><span data-ttu-id="60c04-148">Canary 채널</span><span class="sxs-lookup"><span data-stu-id="60c04-148">Canary Channel</span></span>

<span data-ttu-id="60c04-149">Canary 채널은 매일 제공되며 모든 채널의 최첨단에 위치합니다.</span><span class="sxs-lookup"><span data-stu-id="60c04-149">The Canary Channel ships daily and is the most bleeding edge of all the channels.</span></span> <span data-ttu-id="60c04-150">최신 투자에 대한 액세스를 원하는 경우 여기에 먼저 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="60c04-150">If you want access to the newest investments then they will appear here first.</span></span> <span data-ttu-id="60c04-151">이 흐름의 특성으로 인해 문제가 발생하기 때문에 Canary 릴리스를 활용하는 경우 다른 채널을 나란히 설치해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60c04-151">Because of the nature of this cadence problems will arise overtime, so you may want another channel installed side by side if you are leveraging the Canary releases.</span></span>

## <a name="see-also"></a><span data-ttu-id="60c04-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="60c04-152">See also</span></span>

- [<span data-ttu-id="60c04-153">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="60c04-153">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="60c04-154">채널 다운로드</span><span class="sxs-lookup"><span data-stu-id="60c04-154">Channel downloads</span></span>](https://aka.ms/EdgeEnterprise)
