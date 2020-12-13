---
title: Microsoft Edge Enterprise Sync
ms.author: scottbo
author: dan-wesley
manager: silvanam
ms.date: 12/09/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge Enterprise Sync
ms.openlocfilehash: 791188b5d28c867d6409a4d5373ea6c1ec7e49c7
ms.sourcegitcommit: 482b2e440a62cbf974dc45ac817f9d9d187ba1b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "11205467"
---
# <span data-ttu-id="fa445-103">Microsoft Edge Enterprise Sync</span><span class="sxs-lookup"><span data-stu-id="fa445-103">Microsoft Edge Enterprise Sync</span></span>

<span data-ttu-id="fa445-104">이 문서에서는 로그인한 모든 디바이스에서 Microsoft Edge를 사용하여 즐겨찾기, 암호 및 기타 브라우저 데이터를 동기화하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-104">This article explains how to use Microsoft Edge to sync your favorites, passwords, and other browser data across all your signed-in devices.</span></span>

> [!NOTE]
> <span data-ttu-id="fa445-105">이 문서는 다른 명시가 없는 한 Microsoft Edge 버전 77 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-105">This article applies to Microsoft Edge version 77 or later unless otherwise noted.</span></span>

## <span data-ttu-id="fa445-106">개요</span><span class="sxs-lookup"><span data-stu-id="fa445-106">Overview</span></span>

<span data-ttu-id="fa445-107">Microsoft Edge 동기화를 사용하면 사용자가 로그인한 모든 디바이스에서 자신의 검색 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-107">Microsoft Edge sync enables users to access their browsing data across all their signed-in devices.</span></span> <span data-ttu-id="fa445-108">동기화에서 지원하는 데이터는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-108">The data supported by sync includes:</span></span>

- <span data-ttu-id="fa445-109">즐겨찾기</span><span class="sxs-lookup"><span data-stu-id="fa445-109">Favorites</span></span>
- <span data-ttu-id="fa445-110">암호</span><span class="sxs-lookup"><span data-stu-id="fa445-110">Passwords</span></span>
- <span data-ttu-id="fa445-111">주소 및 기타(양식 채우기)</span><span class="sxs-lookup"><span data-stu-id="fa445-111">Addresses and more (form-fill)</span></span>
- <span data-ttu-id="fa445-112">컬렉션</span><span class="sxs-lookup"><span data-stu-id="fa445-112">Collections</span></span>
- <span data-ttu-id="fa445-113">설정</span><span class="sxs-lookup"><span data-stu-id="fa445-113">Settings</span></span>
- <span data-ttu-id="fa445-114">확장</span><span class="sxs-lookup"><span data-stu-id="fa445-114">Extension</span></span>
- <span data-ttu-id="fa445-115">열린 탭(Microsoft Edge 버전 88에서 사용 가능)</span><span class="sxs-lookup"><span data-stu-id="fa445-115">Open tabs (available in Microsoft Edge version 88)</span></span>
- <span data-ttu-id="fa445-116">기록(Microsoft Edge 버전 88에서 사용 가능)</span><span class="sxs-lookup"><span data-stu-id="fa445-116">History (available in Microsoft Edge version 88)</span></span>

<span data-ttu-id="fa445-117">동기화 기능은 사용자 동의를 통해 활성화되며 위에 나열된 각 데이터 형식의 동기화를 사용자가 켜거나 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-117">Sync functionality is enabled via user consent and users can turn sync on or off for each of the data types listed above.</span></span>

> [!NOTE]
> <span data-ttu-id="fa445-118">동기화 기능을 지원하기 위해 추가 디바이스 연결 및 구성 데이터(예: 디바이스 이름, 제조업체 및 모델)가 업로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-118">Additional device connectivity and configuration data (such as device name, make and model) is uploaded to support sync functionality.</span></span>

## <span data-ttu-id="fa445-119">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="fa445-119">Prerequisites</span></span>

<span data-ttu-id="fa445-120">Azure AD(Azure Active Directory) 계정의 Microsoft Edge 동기화는 다음과 같은 모든 구독에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-120">Microsoft Edge sync for Azure Active Directory (Azure AD) accounts is available for any of the following subscriptions:</span></span>

- <span data-ttu-id="fa445-121">Azure AD Premium(P1 또는 P2)</span><span class="sxs-lookup"><span data-stu-id="fa445-121">Azure AD Premium (P1 or P2)</span></span>
- <span data-ttu-id="fa445-122">M365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="fa445-122">M365 Business Premium</span></span>
- <span data-ttu-id="fa445-123">Office 365 E1 이상</span><span class="sxs-lookup"><span data-stu-id="fa445-123">Office 365 E1 and above</span></span>
- <span data-ttu-id="fa445-124">AIP(Azure Information Protection)(P1 또는 P2)</span><span class="sxs-lookup"><span data-stu-id="fa445-124">Azure Information Protection (AIP) (P1 or P2)</span></span>
- <span data-ttu-id="fa445-125">모든 EDU 구독(학생용 또는 교직원용 Microsoft Apps, 학생용 또는 교직원용 Exchange Online, O365 A1 이상, M365 A1 이상, 또는 학생 또는 교직원용 Azure Information Protection P1 또는 P2)</span><span class="sxs-lookup"><span data-stu-id="fa445-125">All EDU subscriptions (Microsoft Apps for Students or Faculty, Exchange Online for Students or Faculty, O365 A1 or above, M365 A1 or above, or Azure Information Protection P1 or P2 for Students or Faculty)</span></span>

## <span data-ttu-id="fa445-126">Microsoft Edge 동기화 구성</span><span class="sxs-lookup"><span data-stu-id="fa445-126">Configuring Microsoft Edge sync</span></span>

<span data-ttu-id="fa445-127">Microsoft Edge 동기화에 대한 구성 옵션은 AIP(Azure Information Protection) 서비스를 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-127">Configuration options for Microsoft Edge sync are available through the Azure Information Protection (AIP) service.</span></span> <span data-ttu-id="fa445-128">테넌트에 AIP 서비스가 사용되는 경우 모든 사용자가 라이선스에 관계없이 Microsoft Edge 데이터를 동기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-128">When AIP is enabled for a tenant, all users can sync Microsoft Edge data, regardless of licensing.</span></span> <span data-ttu-id="fa445-129">AIP를 활성화하는 방법에 대한 지침은 [여기](https://docs.microsoft.com/azure/information-protection/activate-office365)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-129">Instructions on how to enable AIP can be found [here](https://docs.microsoft.com/azure/information-protection/activate-office365).</span></span>

<span data-ttu-id="fa445-130">특정 사용자 집합에 대한 동기화를 제한하려면 해당 사용자에 대해 [AIP 온보딩 제어 정책](https://docs.microsoft.com/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?view=azureipps&preserve-view=true) 을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-130">To restrict sync to certain set of users, you can enable the [AIP onboarding control policy](https://docs.microsoft.com/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?view=azureipps&preserve-view=true) for those users.</span></span> <span data-ttu-id="fa445-131">필요한 사용자가 모두 온보딩되었는지 확인한 후에도 동기화를 계속 사용할 수 없는 경우, [Get-AIPServiceIPCv3](https://docs.microsoft.com/powershell/module/aipservice/get-aipserviceipcv3?view=azureipps&preserve-view=true) PowerShell cmdlet을 사용하여 IPCv3Service가 활성화되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-131">If sync is still not available after ensuring that all necessary users are onboarded, ensure that the IPCv3Service is enabled using the [Get-AIPServiceIPCv3](https://docs.microsoft.com/powershell/module/aipservice/get-aipserviceipcv3?view=azureipps&preserve-view=true)  PowerShell cmdlet.</span></span>

> [!CAUTION]
> <span data-ttu-id="fa445-132">Azure Information Protection을 활성화하면 Microsoft Word나 Microsoft Outlook과 같은 다른 응용 프로그램에서도 AIP를 사용하여 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-132">Activating Azure Information Protection will also allow other applications, such as Microsoft Word or Microsoft Outlook, to protect content with AIP.</span></span> <span data-ttu-id="fa445-133">또한, Edge 동기화를 제한하는 데 사용하는 모든 온보딩 제어 정책을 사용하면 다른 응용 프로그램에서 AIP를 사용하여 콘텐츠를 보호할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-133">In addition, any onboarding control policy used to restrict Edge sync will also restrict other applications from protecting content using AIP.</span></span>

## <span data-ttu-id="fa445-134">Microsoft Edge 및 Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="fa445-134">Microsoft Edge and Enterprise State Roaming</span></span>

<span data-ttu-id="fa445-135">새 Microsoft Edge는 모든 디바이스에서 사용자 데이터를 동기화하는 확장된 범위를 포함하는 교차 플랫폼 애플리케이션이므로 더 이상 Azure AD Enterprise State Roaming의 일부가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-135">The new Microsoft Edge is a cross-platform application with an expanded scope for syncing user data across all their devices and is no longer a part of Azure AD Enterprise State Roaming.</span></span> <span data-ttu-id="fa445-136">그러나 새 Microsoft Edge는 사용자의 고유한 키를 사용하는 기능과 같이 ESR의 데이터 보호 약속을 이행합니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-136">However, the new Microsoft Edge will fulfill the data protection promises of ESR, such as the ability to bring your own key.</span></span> <span data-ttu-id="fa445-137">자세한 내용은 [Microsoft Edge 및 Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa445-137">For more information, see [Microsoft Edge and Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).</span></span>

## <span data-ttu-id="fa445-138">동기화 그룹 정책</span><span class="sxs-lookup"><span data-stu-id="fa445-138">Sync group policies</span></span>

<span data-ttu-id="fa445-139">다음 그룹 정책은 Microsoft Edge 동기화에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-139">The following group policies impact Microsoft Edge sync:</span></span>

- <span data-ttu-id="fa445-140">[SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled): 동기화를 완전히 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-140">[SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled): Disables sync completely.</span></span>
- <span data-ttu-id="fa445-141">[SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled): 검색 기록 저장 및 동기화를 사용하지 않습니다. 이 정책은 열린 탭 동기화도 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-141">[SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled): Disables saving browsing history and sync. This policy also disables open-tabs sync.</span></span>
- <span data-ttu-id="fa445-142">[AllowDeletingBrowserHistory:](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowdeletingbrowserhistory)해당 정책을 사용하지 않도록 설정하면 기록 동기화도 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-142">[AllowDeletingBrowserHistory](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowdeletingbrowserhistory): When this policy is set to disabled, history sync will also be disabled.</span></span>
- <span data-ttu-id="fa445-143">[SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled): 동기화에서 제외된 유형 목록을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-143">[SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled): Configure the list of types that are excluded from synchronization.</span></span>
- <span data-ttu-id="fa445-144">[RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled): AD(Active Directory) 프로필에서 온-프레미스 저장소를 사용할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-144">[RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled): Allow Active Directory (AD) profiles to use on-premises storage.</span></span> <span data-ttu-id="fa445-145">자세한 내용은 [AD(Active Directory) 사용자를 위한 온-프레미스 동기화](https://docs.microsoft.com/DeployEdge/microsoft-edge-on-premises-sync)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa445-145">For more information, see [On-premises sync for Active Directory (AD) users](https://docs.microsoft.com/DeployEdge/microsoft-edge-on-premises-sync).</span></span>
- <span data-ttu-id="fa445-146">[ForceSync]( https://docs.microsoft.com/deployedge/microsoft-edge-policies#forcesync): 기본적으로 동기화를 설정하며 동기화하는 데 사용자 동의가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-146">[ForceSync]( https://docs.microsoft.com/deployedge/microsoft-edge-policies#forcesync): Turn sync on by default and do not require user consent to sync.</span></span>  

## <span data-ttu-id="fa445-147">질문과 대답</span><span class="sxs-lookup"><span data-stu-id="fa445-147">Frequently Asked Questions</span></span>

### <span data-ttu-id="fa445-148">보안 및 서버/데이터 규정 준수</span><span class="sxs-lookup"><span data-stu-id="fa445-148">SECURITY and SERVER/DATA COMPLIANCE</span></span>

#### <span data-ttu-id="fa445-149">동기화된 데이터가 암호화되나요?</span><span class="sxs-lookup"><span data-stu-id="fa445-149">Is the synced data encrypted?</span></span>

<span data-ttu-id="fa445-150">데이터는 TLS 1.2 이상을 사용하는 전송에서 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-150">The data is encrypted in transport using TLS 1.2 or greater.</span></span> <span data-ttu-id="fa445-151">모든 데이터 형식은 AES128을 사용하여 Microsoft 서비스에 있는 나머지 부분에서 추가로 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-151">All data types are additionally encrypted at rest in Microsoft's service using AES128.</span></span> <span data-ttu-id="fa445-152">열린 탭 및 기록 동기화에 사용되는 데이터 형식을 제외한 모든 데이터 형식은 [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/)을 통해 관리되는 키를 사용하여 사용자의 디바이스를 떠나기 전에 추가적으로 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-152">All data types except those used for open tab and history sync are additionally encrypted before leaving the user’s device with keys managed via [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/).</span></span>

#### <span data-ttu-id="fa445-153">열린 탭 및 기록 데이터에 클라이언트 쪽 암호화가 추가적으로 있지 않은 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="fa445-153">Why don’t open tab and history data have additional client-side encryption?</span></span>  

<span data-ttu-id="fa445-154">최종 사용자 장치에서 리소스 사용률을 줄이기 위해서는 열린 탭 로밍 데이터를 기반으로 기록 데이터가 서버 쪽에서 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-154">In order to reduce resource utilization on end user devices, history data is generated server-side based on open tab roaming data.</span></span> <span data-ttu-id="fa445-155">해당 데이터의 클라이언트 쪽 암호화로는 이 프로세스가 불가능합니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-155">This process would not be possible with client-side encryption of this data.</span></span> <span data-ttu-id="fa445-156">열린 탭 및 기록 동기화를 사용하지 않도록 설정하기 위해 [SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled) 또는 [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled) 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-156">To disable open tab and history sync, apply the [SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled) or [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled) policies.</span></span>

#### <span data-ttu-id="fa445-157">테넌트 관리자가 자신의 키를 가져올 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="fa445-157">Can tenant admins bring their own key?</span></span>

<span data-ttu-id="fa445-158">예,  [Azure Information Protection](https://azure.microsoft.com/services/information-protection/)을 통해 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-158">Yes, through [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).</span></span>

#### <span data-ttu-id="fa445-159">Microsoft Edge 동기화 데이터는 어디에 저장됩니까?</span><span class="sxs-lookup"><span data-stu-id="fa445-159">Where is Microsoft Edge sync data stored?</span></span>

<span data-ttu-id="fa445-160">Azure AD 계정에 대해 동기화된 데이터는 테넌트 ID에 따라 보안 서버에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-160">Synced data for Azure AD accounts is stored in secure servers according to the tenant ID.</span></span> <span data-ttu-id="fa445-161">예를 들어 미국에 등록된 테넌트에 대한 데이터는 해당 지역에 지리적으로 위치하는 서버에 저장되며, Office 애플리케이션처럼 동일한 스토리지 솔루션을 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-161">For example, the data for a tenant that is registered in the United States is stored in servers geo-located for that region and uses the same storage solution as Office applications.</span></span>

#### <span data-ttu-id="fa445-162">데이터에서 Microsoft Edge로 동기화를 수행하는 것 외에 Microsoft의 클라우드가 계속 유지되나요?</span><span class="sxs-lookup"><span data-stu-id="fa445-162">Does the data ever leave Microsoft's cloud, aside from syncing to Microsoft Edge?</span></span>

<span data-ttu-id="fa445-163">아니요.</span><span class="sxs-lookup"><span data-stu-id="fa445-163">No.</span></span>

#### <span data-ttu-id="fa445-164">엔터프라이즈 동기화는 어느 서비스 약관에 속하나요?</span><span class="sxs-lookup"><span data-stu-id="fa445-164">What terms of service does enterprise sync fall under?</span></span>

<span data-ttu-id="fa445-165">Microsoft Edge 동기화에 대한 서비스 약관은 Microsoft Edge에서 볼 수 있는 Microsoft 소프트웨어 라이선스에 속해 있습니다.  *edge://terms*</span><span class="sxs-lookup"><span data-stu-id="fa445-165">Terms of service for Microsoft Edge sync falls under the Microsoft software license viewable in Microsoft Edge at *edge://terms*.</span></span> <span data-ttu-id="fa445-166">Azure AD 구독 및 서비스 약관은 궁극적으로 Microsoft의 [온라인 서비스 약관](https://www.microsoft.com/licensing/product-licensing/products)에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-166">Your Azure AD subscription and terms of service ultimately fall under Microsoft's [Online Service Terms](https://www.microsoft.com/licensing/product-licensing/products).</span></span>

#### <span data-ttu-id="fa445-167">Microsoft Edge에서 GCC(정부 커뮤니티 클라우드) High의 규제 준수 기능을 지원하나요?</span><span class="sxs-lookup"><span data-stu-id="fa445-167">Does Microsoft Edge support Government Community Cloud (GCC) High compliance?</span></span>

<span data-ttu-id="fa445-168">현재 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-168">Not today.</span></span> <span data-ttu-id="fa445-169">GCC High 클라우드 고객의 경우 Microsoft Edge 동기화를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-169">For customers in the GCC High cloud, Microsoft Edge sync is disabled.</span></span>

### <span data-ttu-id="fa445-170">동기화 적용 중</span><span class="sxs-lookup"><span data-stu-id="fa445-170">APPLYING SYNC</span></span>

#### <span data-ttu-id="fa445-171">Microsoft Edge 동기화가 모든 M365 구독에서 지원되지 않는 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="fa445-171">Why isn’t Microsoft Edge sync supported in all M365 subscriptions?</span></span>

<span data-ttu-id="fa445-172">엔터프라이즈 동기화는 일부 M365 구독에서는 사용할 수 없는 Azure Information Protection에 종속됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-172">Enterprise sync depends on Azure Information Protection, which is not available in all M365 subscriptions.</span></span>

#### <span data-ttu-id="fa445-173">Microsoft Edge 동기화는 Enterprise State Roaming을 기반으로 하나요?</span><span class="sxs-lookup"><span data-stu-id="fa445-173">Is Microsoft Edge sync based on Enterprise State Roaming?</span></span>

<span data-ttu-id="fa445-174">아니요.</span><span class="sxs-lookup"><span data-stu-id="fa445-174">No.</span></span> <span data-ttu-id="fa445-175">ESR을 사용하여 동기화를 사용할 수 있지만, Microsoft Edge 동기화는 ESR의 일부가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-175">ESR can be used to enable sync, but Microsoft Edge sync is not a part of ESR.</span></span> <span data-ttu-id="fa445-176">자세한 내용은 [Microsoft Edge Sync](microsoft-edge-enterprise-sync.md)와 [Microsoft Edge 및 Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa445-176">For more information, see [Microsoft Edge Sync](microsoft-edge-enterprise-sync.md) and [Microsoft Edge and Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).</span></span>

#### <span data-ttu-id="fa445-177">Microsoft Edge는 Microsoft Edge와 IE 간의 동기화를 지원합니까?</span><span class="sxs-lookup"><span data-stu-id="fa445-177">Will Microsoft Edge ever support syncing between Microsoft Edge and IE?</span></span>

<span data-ttu-id="fa445-178">이 동기화를 지원할 계획이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-178">There are no plans to support this syncing.</span></span> <span data-ttu-id="fa445-179">레거시 앱을 지원하기 위해 환경에 여전히 IE가 필요한 경우 Microsoft의 [새로운 IE 모드](https://docs.microsoft.com/deployedge/edge-ie-mode)를 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="fa445-179">If you still need IE in your environment to support legacy apps, consider our [new IE mode](https://docs.microsoft.com/deployedge/edge-ie-mode).</span></span>

#### <span data-ttu-id="fa445-180">Microsoft Edge가 Microsoft Edge 레거시와 동기화되나요?</span><span class="sxs-lookup"><span data-stu-id="fa445-180">Will Microsoft Edge sync with Microsoft Edge Legacy?</span></span>

<span data-ttu-id="fa445-181">아니요, 동기화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-181">No, it won't.</span></span> <span data-ttu-id="fa445-182">이 두 가지 에코시스템을 연결하는 것은 Microsoft Edge에서 동기화 안정성을 저하시킬 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-182">We believe connecting these two ecosystems will lead to compromises in the reliability of sync in the Microsoft Edge.</span></span> <span data-ttu-id="fa445-183">기존 데이터가 Microsoft Edge로 마이그레이션되는 것을 보장하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-183">We will ensure that existing data is migrated to the Microsoft Edge.</span></span> <span data-ttu-id="fa445-184">또한 사용자는 원하는 브라우저에서 데이터를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-184">Users will also be able to import data from browser of their choice.</span></span> <span data-ttu-id="fa445-185">이는 또한 새 Microsoft Edge 브라우저에서 IE와 동기화하는 방법을 갖고 있지 않음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-185">This also means that new Microsoft Edge browser won't have a way to sync with IE.</span></span>

### <span data-ttu-id="fa445-186">동기화 관리</span><span class="sxs-lookup"><span data-stu-id="fa445-186">MANAGING SYNC</span></span>

#### <span data-ttu-id="fa445-187">사용자가 개인 테넌트와 동기화하는 것을 중지할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="fa445-187">Is it possible to stop my users from syncing with a personal tenant?</span></span>

<span data-ttu-id="fa445-188">직접은 아니지만 [RestrictSigninToPattern](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern) 정책을 사용하여 Microsoft Edge에 사인온 할 수 있는 프로파일을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa445-188">Not directly, but you can determine which profiles can sign on to Microsoft Edge using the [RestrictSigninToPattern](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern) policy.</span></span>

## <span data-ttu-id="fa445-189">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fa445-189">See also</span></span>

- [<span data-ttu-id="fa445-190">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="fa445-190">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="fa445-191">Microsoft Edge 및 Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="fa445-191">Microsoft Edge and Enterprise State Roaming</span></span>](microsoft-edge-enterprise-state-roaming.md)
