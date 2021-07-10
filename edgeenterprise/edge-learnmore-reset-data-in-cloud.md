---
title: Microsoft Edge 데이터 다시 설정
ms.author: collw
author: dan-wesley
manager: silvanam
ms.date: 06/28/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 클라우드에서 Microsoft Edge 다시 설정하는 방법
ms.openlocfilehash: 19ee60926e36371bd710937fcafc43de7ea035f4
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642044"
---
# <a name="reset-microsoft-edge-data-in-the-cloud"></a><span data-ttu-id="b0c42-103">클라우드에서 Microsoft Edge 데이터 다시 설정하기</span><span class="sxs-lookup"><span data-stu-id="b0c42-103">Reset Microsoft Edge data in the cloud</span></span>

<span data-ttu-id="b0c42-104">이 문서에서는 클라우드에서 Microsoft Edge 데이터를 다시 설정하는 단계를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b0c42-104">This article describes the steps for resetting your Microsoft Edge data in the cloud.</span></span>

> [!NOTE]
> <span data-ttu-id="b0c42-105">이 문서는 달리 명시하지 않는 한 Microsoft Edge 버전 88 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0c42-105">This article applies to Microsoft Edge version 88 or later unless otherwise noted.</span></span>

> [!NOTE]
> <span data-ttu-id="b0c42-106">테넌트가 GCC 모드 환경에 있는 경우 테넌트 관리자는 Microsoft에 지원 요청을 제출하여 데이터를 다시 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0c42-106">If your tenant is in a GCC Mod environment, your tenant admin will need to file a support request with Microsoft to reset your data.</span></span>

## <a name="overview"></a><span data-ttu-id="b0c42-107">개요</span><span class="sxs-lookup"><span data-stu-id="b0c42-107">Overview</span></span>

<span data-ttu-id="b0c42-108">클라우드에서 Microsoft Edge 데이터를 다시 설정해야 하는 상황이 생길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0c42-108">There are situations in which you want to reset your Microsoft Edge data in the cloud.</span></span> <span data-ttu-id="b0c42-109">예를 들면 데이터를 동기화하려고 하는데 Microsoft Edge가 데이터를 동기화할 수 없다고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0c42-109">For example,  you want to synchronize your data, but Microsoft Edge reports that it is unable to synchronize the data.</span></span> <span data-ttu-id="b0c42-110">또는 Microsoft 클라우드에서 데이터를 확실히 제거해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0c42-110">Or you might want to make sure that your data is removed from Microsoft’s cloud.</span></span> <span data-ttu-id="b0c42-111">두 경우 모두 Microsoft Edge를 사용하여 클라우드 데이터 다시 설정을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0c42-111">In both cases, Microsoft Edge lets you perform a cloud data reset.</span></span>

## <a name="back-up-your-favorites"></a><span data-ttu-id="b0c42-112">즐겨찾기 백업</span><span class="sxs-lookup"><span data-stu-id="b0c42-112">Back up your favorites</span></span>

<span data-ttu-id="b0c42-113">다시 설정을 수행하기 전에 즐겨찾기 백업을 수행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b0c42-113">Before performing a reset, we recommend that you back up your favorites.</span></span> <span data-ttu-id="b0c42-114">다음 단계에 따라 즐겨찾기를 백업하세요.</span><span class="sxs-lookup"><span data-stu-id="b0c42-114">Use the following steps to back up your favorites.</span></span>

1. <span data-ttu-id="b0c42-115">Microsoft Edge에서 **설정 등 > 즐겨찾기 > 추가 옵션 > 즐겨찾기 내보내기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b0c42-115">In Microsoft Edge, select **Settings and more > Favorites > More options > Export favorites**.</span></span>
2. <span data-ttu-id="b0c42-116">즐겨찾기를 저장하고자 하는 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b0c42-116">Choose the file to where you want to save your favorites.</span></span> <span data-ttu-id="b0c42-117">직접 파일 이름을 입력하거나 Microsoft Edge에서 기본적으로 제공하는 이름인 "favorites_month_day_year.html"을 파일 이름으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0c42-117">You can type your own filename or use the name that Microsoft Edge provides by default,  "favorites_month_day_year.html" as a filename.</span></span> <span data-ttu-id="b0c42-118">예를 들면 "favorites_12_17_20.html"과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b0c42-118">For example, "favorites_12_17_20.html".</span></span> <span data-ttu-id="b0c42-119">나중에 즐겨찾기를 복원해야 하는 경우 해당 파일에서 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0c42-119">If you need to restore your favorites later, you can do so from that file.</span></span>
3. <span data-ttu-id="b0c42-120">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b0c42-120">Click **Save**.</span></span>

## <a name="perform-a-reset-to-fix-a-synchronization-problem"></a><span data-ttu-id="b0c42-121">다시 설정으로 동기화 문제 해결</span><span class="sxs-lookup"><span data-stu-id="b0c42-121">Perform a reset to fix a synchronization problem</span></span>

<span data-ttu-id="b0c42-122">Microsoft Edge가 데이터를 동기화할 수 없다고 보고하며 데이터 다시 설정을 제안하는 경우 다시 설정을 수행하여 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="b0c42-122">If Microsoft Edge reports that it can't synchronize your data and suggests resetting your data, perform a reset to fix the problem.</span></span>

<span data-ttu-id="b0c42-123">다음 단계에 따라 다시 설정을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b0c42-123">Use the following steps to do a reset.</span></span>

1. <span data-ttu-id="b0c42-124">먼저 다시 설정을 수행하는 장치를 제외하고 모바일 장치를 포함해 모든 장치의 Microsoft Edge에서 로그아웃해 주세요.</span><span class="sxs-lookup"><span data-stu-id="b0c42-124">First, make sure that you’re signed out of Microsoft Edge on all your devices, including your mobile devices, except the device you are performing the reset on.</span></span> <span data-ttu-id="b0c42-125">Microsoft Edge에서 로그인하려면 **설정 등 > 설정 > 로그아웃**을 선택합니다. 로그아웃할 때는 로컬 장치에서 즐겨찾기, 설정 등을 삭제하는 옵션을 선택하지 말아 주세요.</span><span class="sxs-lookup"><span data-stu-id="b0c42-125">To sign out of Microsoft Edge, select **Settings and more > Settings > Sign out**. When signing out, do not select the option to clear favorites, settings, and etc. from your local device.</span></span>
2. <span data-ttu-id="b0c42-126">다른 모든 장치에서 로그아웃한 후 데스크톱에서 Microsoft Edge를 여세요.</span><span class="sxs-lookup"><span data-stu-id="b0c42-126">After you sign out of all your other devices, open Microsoft Edge on your desktop.</span></span> <span data-ttu-id="b0c42-127">**설정 등 > 동기화 > 동기화 다시 설정**을 선택합니다. 결과 대화 상자에서 데이터를 다시 설정한 후 동기화 재개를 선택하고 **다시 설정**을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="b0c42-127">**Select Settings and more > Sync > Reset sync**. In the resulting dialog box, choose to resume sync after resetting data, and then select **Reset**.</span></span>

## <a name="perform-a-reset-to-remove-your-data-from-microsofts-cloud"></a><span data-ttu-id="b0c42-128">다시 설정으로 Microsoft 클라우드에서 데이터 제거하기</span><span class="sxs-lookup"><span data-stu-id="b0c42-128">Perform a reset to remove your data from Microsoft’s cloud</span></span>

<span data-ttu-id="b0c42-129">Microsoft 클라우드에서 데이터를 제거하려면 다음 단계에 따라 다시 설정을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b0c42-129">If you want to remove your data from Microsoft’s cloud, use the following steps to do a reset.</span></span>

1. <span data-ttu-id="b0c42-130">다시 설정을 수행하는 장치를 제외한 장치에서 동기화를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="b0c42-130">Stop synchronization on devices except the device you are performing the reset on.</span></span>  <span data-ttu-id="b0c42-131">Microsoft Edge에서 **설정 등 > 설정 > 동기화 > 동기화 끄기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b0c42-131">In Microsoft Edge, select **Settings and more > Settings > Sync > Turn off sync**.</span></span>  
2. <span data-ttu-id="b0c42-132">동기화를 멈춘 후 **설정 등 > 동기화 > 동기화 다시 설정**을 선택합니다. 결과 대화 상자에서 데이터를 다시 설정한 후 동기화 재개 옵션을 선택하지 **않습니다**.</span><span class="sxs-lookup"><span data-stu-id="b0c42-132">After you stop synchronization, select **Settings and more > Sync > Reset sync**. In the resulting dialog box, **do not** choose to resume sync after resetting data.</span></span> <span data-ttu-id="b0c42-133">**다시 설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b0c42-133">Select **Reset**.</span></span>

## <a name="what-to-expect-during-and-after-a-data-reset"></a><span data-ttu-id="b0c42-134">데이터 다시 설정 중 및 이후에 예상되는 일</span><span class="sxs-lookup"><span data-stu-id="b0c42-134">What to expect during and after a data reset</span></span>

<span data-ttu-id="b0c42-135">데이터 다시 설정은 Microsoft 클라우드에 저장한 데이터의 양에 따라 몇 초에서 몇 분까지 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0c42-135">A data reset can take from a few seconds to a few minutes, depending on how much data you have stored in Microsoft’s cloud.</span></span> <span data-ttu-id="b0c42-136">경우에 따라 다시 설정을 완료할 수 없다는 메시지 또는 다시 설정 재시도 제안이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0c42-136">In some cases, you might see a message saying that a reset could not be completed and a suggestion to reset again.</span></span> <span data-ttu-id="b0c42-137">이 경우 몇 시간 정도 기다렸다가 데이터 다시 설정을 재시도해 주세요.</span><span class="sxs-lookup"><span data-stu-id="b0c42-137">In this case, wait a few hours and try to reset the data again.</span></span> <span data-ttu-id="b0c42-138">그래도 데이터를 다시 설정할 수 없는 경우 Microsoft Edge 고객 지원팀에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="b0c42-138">If you are still unable to reset your data, contact Microsoft Edge Support.</span></span>

<span data-ttu-id="b0c42-139">데이터 다시 설정이 성공적으로 완료된 후 다시 설정 후 동기화 재개를 선택한 경우 장치에서 데이터가 다시 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0c42-139">After a data reset has been successfully completed, data will once again synchronize from your device if you chose to resume sync after the reset.</span></span> <span data-ttu-id="b0c42-140">다른 장치에서 동기화를 시작하려면 해당 장치에 다시 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0c42-140">You will need to sign back in on your other devices if you want to sync from those devices.</span></span> <span data-ttu-id="b0c42-141">그러나 동기화 재개를 선택하지 않은 경우 Microsoft Edge 데이터가 클라우드에서 제거되고 데이터가 더 이상 동기화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0c42-141">However, if you didn’t choose to resume sync, then your Microsoft Edge data is removed from the cloud and your data will no longer synchronize.</span></span>

## <a name="see-also"></a><span data-ttu-id="b0c42-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b0c42-142">See also</span></span>

- [<span data-ttu-id="b0c42-143">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="b0c42-143">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="b0c42-144">Microsoft Edge 엔터프라이즈 동기화</span><span class="sxs-lookup"><span data-stu-id="b0c42-144">Microsoft Edge Enterprise Sync</span></span>](microsoft-edge-enterprise-sync.md)