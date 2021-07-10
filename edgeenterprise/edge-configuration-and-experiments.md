---
title: Microsoft Edge 구성 및 실험
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge 구성 및 실험
ms.openlocfilehash: 1ebfe5fc1da107aa7e9e20b629f14aff468bdd6d
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641564"
---
# <a name="microsoft-edge-configurations-and-experimentation"></a><span data-ttu-id="24b25-103">Microsoft Edge 구성 및 실험</span><span class="sxs-lookup"><span data-stu-id="24b25-103">Microsoft Edge configurations and experimentation</span></span>

<span data-ttu-id="24b25-104">이 문서에서는 Microsoft Edge와 ECS(실험 및 구성 서비스) 간의 상호 작용에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="24b25-104">This article describes the interaction between Microsoft Edge and the Experimentation and Configuration Service (ECS).</span></span> <span data-ttu-id="24b25-105">Microsoft Edge는이 서비스와 통신하여 다양한 종류의 페이로드를 요청하고 받습니다.</span><span class="sxs-lookup"><span data-stu-id="24b25-105">Microsoft Edge communicates with this service to request and receive different kinds of payloads.</span></span> <span data-ttu-id="24b25-106">이러한 페이로드에는 구성, 기능 출시 및 실험이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="24b25-106">These payloads include configurations, feature rollouts, and experiments.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="24b25-107">클라이언트가 `https://config.edge.skype.com`에 액세스할 수 있는지 확인하여 페이로드를 받을 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b25-107">Make sure clients are able to access `https://config.edge.skype.com` so payloads can be received.</span></span>

> [!NOTE]
> <span data-ttu-id="24b25-108">이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="24b25-108">This applies to Microsoft Edge version 77 or later.</span></span>

## <a name="configurations"></a><span data-ttu-id="24b25-109">구성</span><span class="sxs-lookup"><span data-stu-id="24b25-109">Configurations</span></span>

<span data-ttu-id="24b25-110">구성은 제품 상태, 보안 및 개인 정보 규정 준수를 보장하기 위한 페이로드이며, (플랫폼 및 채널에 기반하여) 모든 사용자에게 동일한 가치를 제공하기 위한 것입니다. 이는 도메인 작업에 기능 플래그를 사용하도록 설정하기 위한 것일 수 있으며, 버그의 경우 기능 플래그를 사용하지 않도록 설정하는 데도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24b25-110">Configurations are the payload meant to ensure product health, security, and privacy compliance, and are intended to have the same value for all the users (based on platforms and channels.) This could be to enable a feature flag for a domain action, and can also be used to disable a feature flag in the event of a bug.</span></span>

## <a name="controlled-feature-rollout"></a><span data-ttu-id="24b25-111">제어된 기능 출시</span><span class="sxs-lookup"><span data-stu-id="24b25-111">Controlled Feature Rollout</span></span>

<span data-ttu-id="24b25-112">CFR(제어된 기능 출시)은 기능을 수신하는 사용자 그룹의 크기를 천천히 늘리기 위한 절차입니다.</span><span class="sxs-lookup"><span data-stu-id="24b25-112">Controlled Feature Rollout (CFR) is a procedure for slowly increasing the size of the user group that receives a feature.</span></span> <span data-ttu-id="24b25-113">사용자 집단에서 임의로 선택된 하위 집합에 새 기능을 배포하여 기능의 영향을 측정하는 기능 없이 사용자 피드백을 동일한 크기의 컨트롤 그룹과 비교하는 것이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="24b25-113">By distributing a new feature to a randomly selected subset of the user population, it’s possible to compare user feedback to an equally sized control group without the feature to measure the impact of the feature.</span></span>

## <a name="experiments"></a><span data-ttu-id="24b25-114">실험</span><span class="sxs-lookup"><span data-stu-id="24b25-114">Experiments</span></span>

<span data-ttu-id="24b25-115">Microsoft Edge 빌드에는 아직 개발 중이거나 실험적인 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24b25-115">Microsoft Edge builds have features and functionality that are still in development or are experimental.</span></span> <span data-ttu-id="24b25-116">실험은 CFR과 유사하지만 사용자 그룹의 크기는 새로운 개념을 테스트할 때보다 훨씬 작습니다.</span><span class="sxs-lookup"><span data-stu-id="24b25-116">Experiments are like CFR, but the size of the user group is much smaller for testing the new concept.</span></span> <span data-ttu-id="24b25-117">이러한 기능은 기능을 출시하거나 실험을 마칠 때까지 기본적으로 숨겨집니다.</span><span class="sxs-lookup"><span data-stu-id="24b25-117">These features are hidden by default until the feature's rolled out or the experiment's finished.</span></span> <span data-ttu-id="24b25-118">실험 플래그는 이러한 기능을 활성화 또는 비활성화하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="24b25-118">Experiment flags are used to enable and disable these features.</span></span>

## <a name="about-the-ecs"></a><span data-ttu-id="24b25-119">ECS 정보</span><span class="sxs-lookup"><span data-stu-id="24b25-119">About the ECS</span></span>

<span data-ttu-id="24b25-120">앞의 모든 시나리오에서 이 서비스는 기능 플래그 값이 적용될 수 있도록 브라우저 클라이언트에 해당 값을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="24b25-120">In all the preceding scenarios, the service delivers the feature flag values to the browser client so they can be applied.</span></span> <span data-ttu-id="24b25-121">업데이트에 따라 구성이 즉시 또는 사용자가 브라우저를 다시 시작할 때 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="24b25-121">Depending on the update, configurations are applied immediately or when the user restarts the browser.</span></span>

<span data-ttu-id="24b25-122">Microsoft Edge와 이 서비스 간의 상호 작용은 [ExperimentationAndConfigurationServiceControl](./microsoft-edge-policies.md#experimentationandconfigurationservicecontrol) 정책의 설정에 따라 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="24b25-122">Microsoft Edge's interaction with this service is controlled by settings in the [ExperimentationAndConfigurationServiceControl](./microsoft-edge-policies.md#experimentationandconfigurationservicecontrol) policy.</span></span> <span data-ttu-id="24b25-123">정책 설정을 다음과 같이 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24b25-123">You can configure policy settings to:</span></span>

- <span data-ttu-id="24b25-124">구성만 검색</span><span class="sxs-lookup"><span data-stu-id="24b25-124">Retrieve configurations only</span></span>
- <span data-ttu-id="24b25-125">구성 및 실험을 검색</span><span class="sxs-lookup"><span data-stu-id="24b25-125">Retrieve configurations and experiments</span></span>
- <span data-ttu-id="24b25-126">서비스와 통신하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="24b25-126">Disable communication with the service</span></span>

  > [!CAUTION]
  > <span data-ttu-id="24b25-127">서비스와의 통신을 사용하지 않도록 설정할 경우 Microsoft가 적시에 심각한 버그에 응답하는 기능에 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="24b25-127">If you disable communications with the service, this will affect Microsoft’s ability to respond to a severe bug in a timely manner.</span></span>

## <a name="see-also"></a><span data-ttu-id="24b25-128">기타 참조</span><span class="sxs-lookup"><span data-stu-id="24b25-128">See also</span></span>

- [<span data-ttu-id="24b25-129">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="24b25-129">Microsoft Edge Enterprise landing page</span></span>](https://www.microsoftedgeinsider.com/enterprise)
- [<span data-ttu-id="24b25-130">Microsoft Edge 설명서 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="24b25-130">Microsoft Edge documentation landing page</span></span>](./index.yml)