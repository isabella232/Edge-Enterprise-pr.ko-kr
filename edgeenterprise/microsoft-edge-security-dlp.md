---
title: Microsoft Edge의 데이터 손실 방지
ms.author: archandr
author: dan-wesley
manager: seanlynd
ms.date: 10/08/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge의 DLP(데이터 손실 방지)
ms.openlocfilehash: 59c1b68c0526a49a2ee30283893707852514828d
ms.sourcegitcommit: 2af303fc97e8493024e2359fa2e8be162ab95a59
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104624"
---
# <span data-ttu-id="3ccd6-103">Microsoft Edge의 DLP(데이터 손실 방지)</span><span class="sxs-lookup"><span data-stu-id="3ccd6-103">Data Loss Prevention (DLP) in Microsoft Edge</span></span>

<span data-ttu-id="3ccd6-104">DLP(데이터 손실 방지)는 무단 노출로부터 기업의 중요한 데이터를 식별하고 보호하는 기술 시스템입니다.</span><span class="sxs-lookup"><span data-stu-id="3ccd6-104">Data loss prevention (DLP) is a system of technologies that identify and safeguard sensitive enterprise data from unauthorized disclosure.</span></span> <span data-ttu-id="3ccd6-105">비즈니스 표준 및 산업 규정을 준수하려면 조직에서 중요한 정보를 보호하고 무단 노출을 방지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ccd6-105">To comply with business standards and industry regulations, organizations must protect sensitive information and prevent its unauthorized disclosure.</span></span> <span data-ttu-id="3ccd6-106">중요한 정보에는 재무 데이터 또는 신용 카드 번호, 주민등록번호, 건강 기록 등과 같은 PII(개인 식별 정보)가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ccd6-106">Sensitive information includes financial data or personally identifiable information (PII) such as credit card numbers, social security numbers, or health records, among many other things.</span></span>

<span data-ttu-id="3ccd6-107">원격 작업은 DLP 사용에 대한 강조를 증가시켰습니다.</span><span class="sxs-lookup"><span data-stu-id="3ccd6-107">Remote work has increased the emphasis on using DLP.</span></span> <span data-ttu-id="3ccd6-108">장치에 대한 개인 및 업무 활동의 증가에 따라 기업에서 회사 데이터를 직장 밖으로 무단 공유하는 위험이 증가하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ccd6-108">With the growing use of personal and work activities on devices, enterprises are seeing an increased risk of unauthorized sharing of corporate data outside the workplace.</span></span>

<span data-ttu-id="3ccd6-109">이와 같은 사용자 활동의 혼합은 다양한 공용 및 비공개 네트워크를 통해 개인 및 회사 장치 간에 데이터가 이동하는 장치에도 확산되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3ccd6-109">This blending of user activities has spread to devices as well, where data is moved between personal and corporate devices over a variety of public and private networks.</span></span> <span data-ttu-id="3ccd6-110">그 결과, 중요한 데이터가 노출되는 위험성이 크게 증가하였습니다.</span><span class="sxs-lookup"><span data-stu-id="3ccd6-110">The net result is a dramatically increased risk of exposing sensitive data.</span></span>

<span data-ttu-id="3ccd6-111">Microsoft Edge는 기본적으로 두 가지 DLP 솔루션인 Microsoft Endpoint DLP와 WIP(Windows Information Protection)를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="3ccd6-111">Microsoft Edge natively supports two different DLP solutions, Microsoft Endpoint DLP and Windows Information Protection (WIP).</span></span>

## <span data-ttu-id="3ccd6-112">Microsoft Endpoint DLP</span><span class="sxs-lookup"><span data-stu-id="3ccd6-112">Microsoft Endpoint DLP</span></span>

<span data-ttu-id="3ccd6-113">Microsoft Endpoint DLP는 데이터 중심 보호와 같은 최신 개념을 사용하는 차세대 DLP입니다.</span><span class="sxs-lookup"><span data-stu-id="3ccd6-113">Microsoft Endpoint DLP is the next generation of DLP using modern concepts such as data-centric protection.</span></span> <span data-ttu-id="3ccd6-114">Windows 10 및 Microsoft Edge에 기본 제공되므로 장치에 추가 에이전트나 플러그인이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3ccd6-114">It's  built-in to Windows 10 and Microsoft Edge so it doesn't need additional agents or plugins on the device.</span></span> <span data-ttu-id="3ccd6-115">Endpoint DLP에 대한 자세한 내용은 [Microsoft 365 Endpoint 데이터 손실 방지](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3ccd6-115">To learn more about endpoint DLP, read [Learn about Microsoft 365 Endpoint data loss prevention](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide).</span></span>

> [!NOTE]
> <span data-ttu-id="3ccd6-116">이는 Microsoft Edge 버전 85 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ccd6-116">This applies to Microsoft Edge version 85 or later.</span></span>

<span data-ttu-id="3ccd6-117">Microsoft Edge는 관리자가 중요한 파일에 대해 정책을 적용하고, 비준수 활동에 대한 감사 이벤트를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="3ccd6-117">Microsoft Edge enforces admin configured policies for sensitive files and records audit events for non-compliant activities.</span></span>

<span data-ttu-id="3ccd6-118">Windows 10을 실행하는 장치에서 감사하고 관리할 수 있는 일부 사용자 활동에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ccd6-118">Some of the user activities that you can audit and manage on devices running Windows 10 include the following activities:</span></span>

- <span data-ttu-id="3ccd6-119">파일 업로드: 인증되지 않은 클라우드 위치에 중요한 파일 업로드를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="3ccd6-119">File Upload: Protect sensitive file upload to unauthorized cloud locations.</span></span> <span data-ttu-id="3ccd6-120">다음 3개 스크린샷은 사용자가 중요한 데이터 파일을 로컬 저장소에 가져다 놓는 순서를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3ccd6-120">The next 3 screenshots show a sequence where a user tries to drop a sensitive data file on to their local storage.</span></span>
- <span data-ttu-id="3ccd6-121">클립보드 보호: 중요한 데이터가 파일에서 복사되지 않도록 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="3ccd6-121">Clipboard Protection: Protect sensitive data from being copied out of the file.</span></span>
- <span data-ttu-id="3ccd6-122">인쇄 보호: 중요한 파일이 인쇄되지 않도록 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="3ccd6-122">Print Protection: Protect sensitive file from being printed.</span></span>
- <span data-ttu-id="3ccd6-123">USB/네트워크에 저장: 중요한 파일이 이동식 USB 저장소 또는 인증되지 않은 네트워크 위치에 저장되지 않도록 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="3ccd6-123">Save to USB/Network: Protect sensitive file from being saved to removable USB storage or unauthorized network locations.</span></span>

<span data-ttu-id="3ccd6-124">감사 및 관리할 수 있는 사용자 활동에 대한 자세한 정보는 [모니터링 및 조치를 취할 수 있는 Endpoint 활동](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide#endpoint-activities-you-can-monitor-and-take-action-on)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3ccd6-124">For more detailed information about user activities you can audit and manage, see [Endpoint activities you can monitor and take action on](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide#endpoint-activities-you-can-monitor-and-take-action-on).</span></span>

## <span data-ttu-id="3ccd6-125">Windows Information Protection</span><span class="sxs-lookup"><span data-stu-id="3ccd6-125">Windows Information Protection</span></span>

<span data-ttu-id="3ccd6-126">Microsoft Edge가 WIP(Windows Information Protection)를 지원하는 방법에 대한 설명은 [Windows Information Protection 지원](https://docs.microsoft.com/deployedge/microsoft-edge-security-windows-information-protection)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3ccd6-126">Check out [Support for Windows Information Protection](https://docs.microsoft.com/deployedge/microsoft-edge-security-windows-information-protection), which describes how Microsoft Edge supports Windows Information Protection (WIP).</span></span> <span data-ttu-id="3ccd6-127">다음 섹션에서 시스템 요구 사항, 이점 및 지원되는 기능에 대한 자세한 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ccd6-127">You can learn moe about system requirements, benefits, and supported features in the following sections:</span></span>

- [<span data-ttu-id="3ccd6-128">시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="3ccd6-128">System Requirements</span></span>](https://docs.microsoft.com/deployedge/:microsoft-edge-security-windows-information-protection#system-requirements)
- [<span data-ttu-id="3ccd6-129">Windows Information Protection의 이점</span><span class="sxs-lookup"><span data-stu-id="3ccd6-129">Windows Information Protection Benefits</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-security-windows-information-protection#windows-information-protection-benefits)
- [<span data-ttu-id="3ccd6-130">Microsoft Edge에서 지원되는 WIP 기능</span><span class="sxs-lookup"><span data-stu-id="3ccd6-130">WIP features supported in Microsoft Edge</span></span>](https://docs.microsoft.com/DeployEdge/microsoft-edge-security-windows-information-protection#wip-features-supported-in-microsoft-edge)

## <span data-ttu-id="3ccd6-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3ccd6-131">See also</span></span>

- [<span data-ttu-id="3ccd6-132">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="3ccd6-132">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="3ccd6-133">비디오: 데이터 손실 방지 - Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="3ccd6-133">Video: Data loss prevention - Microsoft Edge</span></span>](https://www.youtube.com/watch?v=dLD04U9eTqg)
- [<span data-ttu-id="3ccd6-134">데이터 손실 방지 개요</span><span class="sxs-lookup"><span data-stu-id="3ccd6-134">Overview of data loss prevention</span></span>](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies?view=o365-worldwide)
- [<span data-ttu-id="3ccd6-135">Windows Information Protection을 사용하여 엔터프라이즈 데이터 보호</span><span class="sxs-lookup"><span data-stu-id="3ccd6-135">Protect your enterprise data using Windows Information Protection</span></span>](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)
