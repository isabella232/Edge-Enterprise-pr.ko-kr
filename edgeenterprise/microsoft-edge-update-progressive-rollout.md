---
title: Microsoft Edge Stable 채널 업데이트를 위한 점진적 배포
ms.author: aguta
author: dan-wesley
manager: srugh
ms.date: 05/21/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge Stable 채널 업데이트를 위한 점진적 배포
ms.openlocfilehash: 5b0d2f58318b10538d0470b644d346b5b9b9489b
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980700"
---
# <span data-ttu-id="8471b-103">Microsoft Edge Stable 채널 업데이트를 위한 점진적 배포</span><span class="sxs-lookup"><span data-stu-id="8471b-103">Progressive rollouts for Microsoft Edge Stable channel updates</span></span>

<span data-ttu-id="8471b-104">Microsoft Edge 83 릴리스부터 며칠 동안 Microsoft Edge Stable 채널에 대한 주요 업데이트를 점진적으로 배포할 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="8471b-104">Starting with Microsoft Edge 83 release, we will perform gradual rollouts of major updates to Microsoft Edge Stable channel over the span of a few days.</span></span> <span data-ttu-id="8471b-105">이 점진적 배포를 통해 업그레이드를 모니터링하고 조직 전체에서 브라우저를 안전하게 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8471b-105">This progressive rollout allows us to monitor upgrades and safely update the browser across the organization.</span></span>

> [!NOTE]
> <span data-ttu-id="8471b-106">이는 Microsoft Edge Stable 채널 버전 83 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8471b-106">This applies to Microsoft Edge Stable channel version 83 or later.</span></span>

## <span data-ttu-id="8471b-107">점진적 배포가 필요한 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="8471b-107">Why do we need progressive rollout?</span></span>

<span data-ttu-id="8471b-108">며칠 동안 업데이트 상태를 면밀히 모니터링하고 업데이트를 배포하면 새 업데이트에서 발생할 수 있는 문제의 영향을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8471b-108">By monitoring the health of our updates closely and rolling out the updates over the course of several days, we can limit the impact of issues that might occur with the new update.</span></span> <span data-ttu-id="8471b-109">Microsoft Edge 릴리스 83에서는 모든 Windows 7, Windows 8 및 8.1 및 Windows 10 버전의 Microsoft Edge에 대해 점진적 배포가 사용 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8471b-109">With Microsoft Edge release 83, Progressive Rollouts will be enabled for all Windows 7, Windows 8 & 8.1, and Windows 10 versions of Microsoft Edge.</span></span> <span data-ttu-id="8471b-110">Mac에서의 Microsoft Edge도 준비되는대로 지원될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8471b-110">We will support Microsoft Edge on Mac as soon as it is ready.</span></span>

## <span data-ttu-id="8471b-111">업데이트는 어떻게 작동되나요?</span><span class="sxs-lookup"><span data-stu-id="8471b-111">How will the updates work?</span></span>

<span data-ttu-id="8471b-112">각 Microsoft Edge 설치에는 업그레이드 값이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="8471b-112">Each installation of Microsoft Edge is assigned an upgrade value.</span></span> <span data-ttu-id="8471b-113">점진적 배포를 시작할 경우 장치의 값이 업그레이드 값 범위에 포함되면 업데이트를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8471b-113">When we start rolling out incrementally, you'll see the update when the value on your device falls within the upgrade value range.</span></span> <span data-ttu-id="8471b-114">배포가 진행되면 (며칠 이내에) 최종적으로 모든 사용자가 업데이트를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8471b-114">As the rollout progresses (within a few days), all users will eventually get the update.</span></span> <span data-ttu-id="8471b-115">중요 보안 수정 사항이 포함된 브라우저 업데이트는 중요 보안 수정 사항이 없는 업데이트에 비해 배포 흐름이 더 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="8471b-115">Browser updates with critical security fixes will have a faster rollout cadence than updates that don't have critical security fixes.</span></span> <span data-ttu-id="8471b-116">이러한 조치는 취약성으로부터 즉각적인 보호를 보장하기 위해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="8471b-116">This is done to ensure prompt protection from vulnerabilities.</span></span>

## <span data-ttu-id="8471b-117">이것이 기업에 어떤 영향을 미치나요?</span><span class="sxs-lookup"><span data-stu-id="8471b-117">How does this affect enterprises?</span></span>

<span data-ttu-id="8471b-118">Microsoft Edge 아티팩트는 Microsoft Intune, WSUS(Windows Server Update Service) 및 구성 관리자와 같은 여러 메커니즘을 사용하여 기업에 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="8471b-118">Microsoft Edge artifacts are distributed to enterprises using multiple mechanisms such as Microsoft Intune, Windows Server Update Service (WSUS), and Configuration Manager.</span></span> <span data-ttu-id="8471b-119">이러한 배포 도구는 점진적 배포와 관련해 다른 방식으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="8471b-119">These deployment tools behave differently with respect to Progressive Rollout:</span></span>

- <span data-ttu-id="8471b-120">Microsoft Intune을 통해 배포를 관리하는 기업은 자동 업데이트를 위해 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="8471b-120">Enterprises that manage distribution via Microsoft Intune are registered for auto-updates.</span></span> <span data-ttu-id="8471b-121">점진적 배포가 사용되고 모든 사용자는 며칠 후에 업데이트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8471b-121">Progressive Rollout is used, and all the users will see an update in a few days.</span></span>
- <span data-ttu-id="8471b-122">WSUS(Windows Server Update Services) 또는 구성 관리자를 통해 배포를 관리하는 기업은 자동 업데이트에 등록되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8471b-122">Enterprises that manage distribution through WSUS (Windows Server Update Services) or Configuration Manager are not registered for auto-updates.</span></span> <span data-ttu-id="8471b-123">관리자는 처음부터 사용할 수 있는 업데이트를 관리하고 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="8471b-123">Administrators manage and apply the updates that will be available from the start.</span></span> <span data-ttu-id="8471b-124">점진적 배포는 이 프로세스에 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8471b-124">Progressive Rollout does not affect this process.</span></span>

<span data-ttu-id="8471b-125">사용자 의견, 응용 프로그램 내 피드백 버튼을 통해 귀중한 피드백을 공유하거나 우려 사항이나 질문이 있는 경우 댓글 아래에 공유하세요.</span><span class="sxs-lookup"><span data-stu-id="8471b-125">Please share your valuable feedback through user voice, the in-application feedback button, or below in the comments if you have any concerns or questions.</span></span>

## <span data-ttu-id="8471b-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8471b-126">See also</span></span>

- [<span data-ttu-id="8471b-127">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="8471b-127">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
