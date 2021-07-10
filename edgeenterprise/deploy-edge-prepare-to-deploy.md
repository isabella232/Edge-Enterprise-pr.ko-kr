---
title: 사용자 환경의 Microsoft Edge
ms.author: ryhecht
author: RyanHechtMSFT
manager: tinad
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 사용자 환경의 Microsoft Edge
ms.openlocfilehash: 2381380cb399f6a1fbb5efa9378ffeba20fa774f
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641604"
---
# <a name="microsoft-edge-in-your-environment"></a><span data-ttu-id="9f5d7-103">사용자 환경의 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="9f5d7-103">Microsoft Edge in your environment</span></span>

<span data-ttu-id="9f5d7-104">이 문서에서는 Microsoft Edge 레거시가 서비스 종료에 도달할 때 Microsoft Edge를 배포하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9f5d7-104">This article describes how to prepare to deploy Microsoft Edge when Microsoft Edge Legacy reaches its end of service.</span></span>

<span data-ttu-id="9f5d7-105">Microsoft Edge 제품 팀의 [블로그 게시물](https://aka.ms/EdgeLegacyEOS)에 따라 Microsoft Edge 레거시 데스크톱 응용 프로그램에 대한 지원은 2021년 3월 9일에 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f5d7-105">As per the Microsoft Edge Product Team’s [blog post](https://aka.ms/EdgeLegacyEOS), support for the Microsoft Edge Legacy desktop application will end on March 9, 2021.</span></span> <span data-ttu-id="9f5d7-106">4월에 업데이트 화요일(또는 "B") 릴리스를 적용하면 Windows 10 RS4에서 20H1까지 실행되는 장치에서 Microsoft Edge 레거시가 제거되고 Microsoft Edge로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f5d7-106">When you apply the Update Tuesday (or "B") release in April, it will remove Microsoft Edge Legacy from devices running Windows 10 RS4 through 20H1 and replace it with Microsoft Edge.</span></span>

## <a name="how-to-prepare"></a><span data-ttu-id="9f5d7-107">준비 방법</span><span class="sxs-lookup"><span data-stu-id="9f5d7-107">How to Prepare</span></span>

<span data-ttu-id="9f5d7-108">4월 업데이트 화요일 릴리스와 함께 Windows 10 RS4에서 20H1 장치에 Microsoft Edge 설치 준비를 하려면 [Microsoft Edge의 배포 계획](deploy-edge-plan-deployment.md)을 읽어보시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="9f5d7-108">To prepare for Microsoft Edge being installed on Windows 10 RS4 through 20H1 devices with the Update Tuesday release in April, we recommend reading [Plan your deployment of Microsoft Edge](deploy-edge-plan-deployment.md).</span></span>

<span data-ttu-id="9f5d7-109">배포를 계획한 후 다음 방법 중 하나를 사용하여 Microsoft Edge 배포를 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="9f5d7-109">After you plan your deployment, use one of the following approaches to prepare to deploy Microsoft Edge.</span></span>

- <span data-ttu-id="9f5d7-110">**그룹 정책을 설치하여 Microsoft Edge업데이트 방법을 사용자 지정합니다**.</span><span class="sxs-lookup"><span data-stu-id="9f5d7-110">**Install group policies to customize your Microsoft Edge update approach**.</span></span> <span data-ttu-id="9f5d7-111">자세한 내용은 [Windows에서 Microsoft Edge 정책 설정 구성](configure-microsoft-edge.md)을 참조하고 [업데이트 정책 참조](microsoft-edge-update-policies.md)에 특히 주의하세요.</span><span class="sxs-lookup"><span data-stu-id="9f5d7-111">For more information, see [Configure Microsoft Edge policy settings on Windows](configure-microsoft-edge.md), and pay special attention to the [Update Policy reference](microsoft-edge-update-policies.md) material.</span></span> <span data-ttu-id="9f5d7-112">4월의 업데이트 화요일 릴리스를 설치하기 전에 그룹 정책을 설치하여 업데이트를 관리하는 경우 Microsoft Edge는 즉시 정책 준수를 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f5d7-112">If you install group policies to manage your updates before installing April’s Update Tuesday release, Microsoft Edge will immediately start respecting your policy.</span></span> <span data-ttu-id="9f5d7-113">설치된 그룹 정책이 없는 경우 Microsoft Edge가 자동으로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f5d7-113">If there isn't any installed group policy, Microsoft Edge will automatically update itself.</span></span>

- <span data-ttu-id="9f5d7-114">**서비스 종료일인 2021년 3월 9일전에 Microsoft Edge 레거시 데스크톱 응용 프로그램을 제거하고 Microsoft Edge를 배포합니다**.</span><span class="sxs-lookup"><span data-stu-id="9f5d7-114">**Remove the Microsoft Edge Legacy desktop application before its end of service date of March 9, 2021 and deploy Microsoft Edge**.</span></span> <span data-ttu-id="9f5d7-115">Windows 10 RS4~20H1의 경우 Windows 업데이트를 사용하여 이 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f5d7-115">For Windows 10 RS4 through 20H1, you can do this by using Windows Updates.</span></span> <span data-ttu-id="9f5d7-116">자세한 내용은 [Windows 10 업데이트로 Microsoft Edge 배포](deploy-edge-with-windows-10-updates.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9f5d7-116">For more information, see [Deploy Microsoft Edge with Windows 10 updates](deploy-edge-with-windows-10-updates.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9f5d7-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9f5d7-117">See also</span></span>

- [<span data-ttu-id="9f5d7-118">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="9f5d7-118">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="9f5d7-119">Microsoft Edge 배포 계획</span><span class="sxs-lookup"><span data-stu-id="9f5d7-119">Plan your deployment of Microsoft Edge</span></span>](deploy-edge-plan-deployment.md)