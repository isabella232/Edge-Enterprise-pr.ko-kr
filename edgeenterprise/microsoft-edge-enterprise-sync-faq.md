---
title: Microsoft Edge Enterprise 동기화 FAQ
ms.author: scottbo
author: dan-wesley
manager: silvanam
ms.date: 03/08/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge Enterprise 동기화에 대한 질문과 대답
ms.openlocfilehash: 51f6dfc4cd8f308815ee111c30d5501ec0e44f59
ms.sourcegitcommit: 86e0de9b27ad4297a6d5a57c866d7ef4fc7bb0cd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2021
ms.locfileid: "11400204"
---
# <a name="microsoft-edge-enterprise-sync-faq"></a><span data-ttu-id="2d33b-103">Microsoft Edge Enterprise 동기화 FAQ</span><span class="sxs-lookup"><span data-stu-id="2d33b-103">Microsoft Edge enterprise sync FAQ</span></span>

<span data-ttu-id="2d33b-104">이 문서에는 Microsoft Edge 버전 77 이상에 대한 엔터프라이즈 동기화에 대한 질문과 대답이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d33b-104">This article answers frequently asked questions about enterprise sync for Microsoft Edge version 77 or later.</span></span>

## <a name="security-and-serverdata-compliance"></a><span data-ttu-id="2d33b-105">보안 및 서버/데이터 규정 준수</span><span class="sxs-lookup"><span data-stu-id="2d33b-105">Security and Server/Data Compliance</span></span>

### <a name="is-the-synced-data-encrypted"></a><span data-ttu-id="2d33b-106">동기화된 데이터가 암호화되나요?</span><span class="sxs-lookup"><span data-stu-id="2d33b-106">Is the synced data encrypted?</span></span>

<span data-ttu-id="2d33b-107">데이터는 TLS 1.2 이상을 사용하는 전송에서 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d33b-107">The data is encrypted in transport using TLS 1.2 or greater.</span></span> <span data-ttu-id="2d33b-108">모든 데이터 형식은 AES128을 사용하여 Microsoft 서비스에 있는 나머지 부분에서 추가로 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d33b-108">All data types are additionally encrypted at rest in Microsoft's service using AES128.</span></span> <span data-ttu-id="2d33b-109">열려 있는 탭 및 기록 동기화에 사용되는 데이터 형식을 제외한 모든 데이터 형식은 [Azure Information Protection](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern) 정책을 통해 관리되는 키를 사용하여 사용자의 디바이스를 떠나기 전에 추가적으로 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d33b-109">All data types except those used for open tab and history sync are additionally encrypted before leaving the user’s device with keys managed via the [Azure Information Protection](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern) policy.</span></span>

### <a name="why-dont-open-tab-and-history-data-have-more-client-side-encryption"></a><span data-ttu-id="2d33b-110">열린 탭 및 기록 데이터에 클라이언트 측 암호화가 더 없는 이유는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="2d33b-110">Why don’t open tab and history data have more client-side encryption?</span></span>

<span data-ttu-id="2d33b-111">최종 사용자 장치에서 리소스 사용률을 줄이기 위해 열린 탭 로밍 데이터를 기반으로 기록 데이터가 서버 쪽에서 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d33b-111">To reduce resource utilization on end-user devices, history data is generated server-side based on open tab roaming data.</span></span> <span data-ttu-id="2d33b-112">해당 데이터의 클라이언트 쪽 암호화로는 이 프로세스가 불가능합니다.</span><span class="sxs-lookup"><span data-stu-id="2d33b-112">This process would not be possible with client-side encryption of this data.</span></span> <span data-ttu-id="2d33b-113">열린 탭 및 기록 동기화를 사용하지 않도록 설정하기 위해 [SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled) 또는 [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled) 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="2d33b-113">To disable open tab and history sync, apply the [SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled) or [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled) policies.</span></span>

### <a name="can-tenant-admins-bring-their-own-key"></a><span data-ttu-id="2d33b-114">테넌트 관리자가 자신의 키를 가져올 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="2d33b-114">Can tenant admins bring their own key?</span></span>

<span data-ttu-id="2d33b-115">예,  [Azure Information Protection](https://azure.microsoft.com/services/information-protection/)을 통해 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d33b-115">Yes, through [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).</span></span>

### <a name="where-is-microsoft-edge-sync-data-stored"></a><span data-ttu-id="2d33b-116">Microsoft Edge 동기화 데이터는 어디에 저장됩니까?</span><span class="sxs-lookup"><span data-stu-id="2d33b-116">Where is Microsoft Edge sync data stored?</span></span>

<span data-ttu-id="2d33b-117">Azure AD 계정에 대해 동기화된 데이터는 테넌트 ID에 따라 보안 서버에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d33b-117">Synced data for Azure AD accounts is stored in secure servers according to the tenant ID.</span></span> <span data-ttu-id="2d33b-118">예를 들어 미국에 등록된 테넌트에 대한 데이터는 해당 지역에 지리적으로 위치하는 서버에 저장되며, Office 애플리케이션처럼 동일한 스토리지 솔루션을 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="2d33b-118">For example, the data for a tenant that is registered in the United States is stored in servers geo-located for that region and uses the same storage solution as Office applications.</span></span>

### <a name="does-the-data-ever-leave-microsofts-cloud-aside-from-syncing-to-microsoft-edge"></a><span data-ttu-id="2d33b-119">데이터에서 Microsoft Edge로 동기화를 수행하는 것 외에 Microsoft의 클라우드가 계속 유지되나요?</span><span class="sxs-lookup"><span data-stu-id="2d33b-119">Does the data ever leave Microsoft's cloud, aside from syncing to Microsoft Edge?</span></span>

<span data-ttu-id="2d33b-120">아니요.</span><span class="sxs-lookup"><span data-stu-id="2d33b-120">No.</span></span>

### <a name="what-terms-of-service-does-enterprise-sync-fall-under"></a><span data-ttu-id="2d33b-121">엔터프라이즈 동기화는 어느 서비스 약관에 속하나요?</span><span class="sxs-lookup"><span data-stu-id="2d33b-121">What terms of service does enterprise sync fall under?</span></span>

<span data-ttu-id="2d33b-122">Microsoft Edge 동기화에 대한 서비스 약관은 Microsoft Edge에서 볼 수 있는 Microsoft 소프트웨어 라이선스에 속해 있습니다.  *edge://terms*</span><span class="sxs-lookup"><span data-stu-id="2d33b-122">Terms of service for Microsoft Edge sync falls under the Microsoft software license viewable in Microsoft Edge at *edge://terms*.</span></span> <span data-ttu-id="2d33b-123">Azure AD 구독 및 서비스 약관은 궁극적으로 Microsoft의 [온라인 서비스 약관](https://www.microsoft.com/licensing/product-licensing/products)에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="2d33b-123">Your Azure AD subscription and terms of service ultimately fall under Microsoft's [Online Service Terms](https://www.microsoft.com/licensing/product-licensing/products).</span></span>

### <a name="does-microsoft-edge-support-government-community-cloud-gcc-high-compliance"></a><span data-ttu-id="2d33b-124">Microsoft Edge에서 GCC(정부 커뮤니티 클라우드) High의 규제 준수 기능을 지원하나요?</span><span class="sxs-lookup"><span data-stu-id="2d33b-124">Does Microsoft Edge support Government Community Cloud (GCC) High compliance?</span></span>

<span data-ttu-id="2d33b-125">현재 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d33b-125">Not today.</span></span> <span data-ttu-id="2d33b-126">GCC High 클라우드 고객의 경우 Microsoft Edge 동기화를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2d33b-126">For customers in the GCC High cloud, Microsoft Edge sync is disabled.</span></span>

## <a name="applying-sync"></a><span data-ttu-id="2d33b-127">동기화 적용 중</span><span class="sxs-lookup"><span data-stu-id="2d33b-127">Applying Sync</span></span>

### <a name="why-isnt-microsoft-edge-sync-supported-in-all-m365-subscriptions"></a><span data-ttu-id="2d33b-128">Microsoft Edge 동기화가 모든 M365 구독에서 지원되지 않는 이유는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="2d33b-128">Why isn’t Microsoft Edge sync supported in all M365 subscriptions?</span></span>

<span data-ttu-id="2d33b-129">엔터프라이즈 동기화는 일부 M365 구독에서 사용할 수 없는 [Azure Information Protection](https://azure.microsoft.com/services/information-protection/)에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="2d33b-129">Enterprise sync depends on [Azure Information Protection](https://azure.microsoft.com/services/information-protection/), which is not available in all M365 subscriptions.</span></span>

### <a name="is-microsoft-edge-sync-based-on-enterprise-state-roaming"></a><span data-ttu-id="2d33b-130">Microsoft Edge 동기화는 엔터프라이즈 상태 로밍을 기반으로 하나요?</span><span class="sxs-lookup"><span data-stu-id="2d33b-130">Is Microsoft Edge sync based on Enterprise State Roaming?</span></span>

<span data-ttu-id="2d33b-131">아니요.</span><span class="sxs-lookup"><span data-stu-id="2d33b-131">No.</span></span> <span data-ttu-id="2d33b-132">ESR을 사용하여 동기화를 사용할 수 있지만, Microsoft Edge 동기화는 ESR의 일부가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="2d33b-132">ESR can be used to enable sync, but Microsoft Edge sync is not a part of ESR.</span></span> <span data-ttu-id="2d33b-133">자세한 내용은 [Microsoft Edge Sync](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-enterprise-sync)와 [Microsoft Edge 및 Enterprise State Roaming](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-enterprise-state-roaming)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2d33b-133">For more information, see [Microsoft Edge Sync](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-enterprise-sync) and [Microsoft Edge and Enterprise State Roaming](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-enterprise-state-roaming).</span></span>

### <a name="will-microsoft-edge-ever-support-syncing-between-microsoft-edge-and-ie"></a><span data-ttu-id="2d33b-134">Microsoft Edge는 Microsoft Edge와 IE 간의 동기화를 지원합니까?</span><span class="sxs-lookup"><span data-stu-id="2d33b-134">Will Microsoft Edge ever support syncing between Microsoft Edge and IE?</span></span>

<span data-ttu-id="2d33b-135">이 동기화를 지원할 계획이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2d33b-135">There are no plans to support this syncing.</span></span> <span data-ttu-id="2d33b-136">레거시 앱을 지원하기 위해 환경에 여전히 IE가 필요한 경우 Microsoft의 [새로운 IE 모드](https://docs.microsoft.com/deployedge/edge-ie-mode)를 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="2d33b-136">If you still need IE in your environment to support legacy apps, consider our [new IE mode](https://docs.microsoft.com/deployedge/edge-ie-mode).</span></span>

### <a name="will-microsoft-edge-sync-with-microsoft-edge-legacy"></a><span data-ttu-id="2d33b-137">Microsoft Edge가 Microsoft Edge 레거시와 동기화되나요?</span><span class="sxs-lookup"><span data-stu-id="2d33b-137">Will Microsoft Edge sync with Microsoft Edge Legacy?</span></span>

<span data-ttu-id="2d33b-138">아니요, 동기화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d33b-138">No, it won't.</span></span> <span data-ttu-id="2d33b-139">이 두 가지 에코시스템을 연결하는 것은 Microsoft Edge에서 동기화 안정성을 저하시킬 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2d33b-139">We believe connecting these two ecosystems will lead to compromises in the reliability of sync in the Microsoft Edge.</span></span> <span data-ttu-id="2d33b-140">기존 데이터가 Microsoft Edge로 마이그레이션되는 것을 보장하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="2d33b-140">We will ensure that existing data is migrated to the Microsoft Edge.</span></span> <span data-ttu-id="2d33b-141">사용자는 선택한 브라우저에서 데이터를 가져올 수도 있습니다. 이는 Microsoft Edge가 IE와 동기화할 수 없음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="2d33b-141">Users will also be able to import data from browser of their choice, which also means that Microsoft Edge won't have a way to sync with IE.</span></span>

## <a name="managing-sync"></a><span data-ttu-id="2d33b-142">동기화 관리 중</span><span class="sxs-lookup"><span data-stu-id="2d33b-142">Managing Sync</span></span>

### <a name="is-it-possible-to-stop-my-users-from-syncing-with-a-personal-tenant"></a><span data-ttu-id="2d33b-143">사용자가 개인 테넌트와 동기화하는 것을 중지할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="2d33b-143">Is it possible to stop my users from syncing with a personal tenant?</span></span>

<span data-ttu-id="2d33b-144">직접은 아니지만 [RestrictSigninToPattern](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern) 정책을 사용하여 Microsoft Edge에 사인온 할 수 있는 프로파일을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d33b-144">Not directly, but you can determine which profiles can sign on to Microsoft Edge using the [RestrictSigninToPattern](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern) policy.</span></span>

## <a name="see-also"></a><span data-ttu-id="2d33b-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2d33b-145">See also</span></span>

- [<span data-ttu-id="2d33b-146">Microsoft Edge Enterprise 동기화</span><span class="sxs-lookup"><span data-stu-id="2d33b-146">Microsoft Edge Enterprise Sync</span></span>](microsoft-edge-enterprise-sync.md)
- [<span data-ttu-id="2d33b-147">Microsoft Edge 및 Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="2d33b-147">Microsoft Edge and Enterprise State Roaming</span></span>](microsoft-edge-enterprise-state-roaming.md)
- [<span data-ttu-id="2d33b-148">Microsoft Edge Enterprise 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="2d33b-148">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
