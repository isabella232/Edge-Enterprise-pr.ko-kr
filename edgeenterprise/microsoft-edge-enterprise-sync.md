---
title: Microsoft Edge Enterprise Sync
ms.author: scottbo
author: dan-wesley
manager: silvanam
ms.date: 09/15/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge Enterprise Sync
ms.openlocfilehash: d9cd643142d0f6744664a5071c5000b820583e41
ms.sourcegitcommit: 06c365faeea6070f103fe867cc2da13539ae4680
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2020
ms.locfileid: "11016347"
---
# <span data-ttu-id="8b3b8-103">Microsoft Edge Enterprise Sync</span><span class="sxs-lookup"><span data-stu-id="8b3b8-103">Microsoft Edge Enterprise Sync</span></span>

<span data-ttu-id="8b3b8-104">이 문서에서는 로그인한 모든 디바이스에서 Microsoft Edge를 사용하여 즐겨찾기, 암호 및 기타 브라우저 데이터를 동기화하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-104">This article explains how to use Microsoft Edge to sync your favorites, passwords, and other browser data across all your signed-in devices.</span></span>

> [!NOTE]
> <span data-ttu-id="8b3b8-105">이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-105">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="8b3b8-106">개요</span><span class="sxs-lookup"><span data-stu-id="8b3b8-106">Overview</span></span>

<span data-ttu-id="8b3b8-107">Microsoft Edge 동기화를 사용하면 사용자가 로그인한 모든 디바이스에서 자신의 검색 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-107">Microsoft Edge sync enables users to access their browsing data across all their signed-in devices.</span></span> <span data-ttu-id="8b3b8-108">동기화에서 지원하는 데이터는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-108">The data supported by sync includes:</span></span>

- <span data-ttu-id="8b3b8-109">즐겨찾기</span><span class="sxs-lookup"><span data-stu-id="8b3b8-109">Favorites</span></span>
- <span data-ttu-id="8b3b8-110">암호</span><span class="sxs-lookup"><span data-stu-id="8b3b8-110">Passwords</span></span>
- <span data-ttu-id="8b3b8-111">주소 및 기타(양식 채우기)</span><span class="sxs-lookup"><span data-stu-id="8b3b8-111">Addresses and more (form-fill)</span></span>
- <span data-ttu-id="8b3b8-112">컬렉션</span><span class="sxs-lookup"><span data-stu-id="8b3b8-112">Collections</span></span>
- <span data-ttu-id="8b3b8-113">설정</span><span class="sxs-lookup"><span data-stu-id="8b3b8-113">Settings</span></span>
- <span data-ttu-id="8b3b8-114">검색 기록</span><span class="sxs-lookup"><span data-stu-id="8b3b8-114">Browsing history</span></span>
- <span data-ttu-id="8b3b8-115">탭 열기</span><span class="sxs-lookup"><span data-stu-id="8b3b8-115">Open tabs</span></span>

<span data-ttu-id="8b3b8-116">동기화 기능은 사용자 동의를 통해 활성화되며 사용자는 위에 나열된 각 데이터 형식에 대해 동기화를 켜거나 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-116">Sync functionality is enabled via user consent and users can turn sync on or off for each of the data types listed above.</span></span>

> [!NOTE]
> <span data-ttu-id="8b3b8-117">동기화 기능을 지원하기 위해 추가 디바이스 연결 및 구성 데이터(예: 디바이스 이름, 제조업체 및 모델)가 업로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-117">Additional device connectivity and configuration data (such as device name, make and model) is uploaded to support sync functionality.</span></span>

## <span data-ttu-id="8b3b8-118">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="8b3b8-118">Prerequisites</span></span>

<span data-ttu-id="8b3b8-119">AAD(Azure AD) 계정의 Microsoft Edge 동기화는 다음 모든 구독에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-119">Microsoft Edge sync for Azure Active Directory (Azure AD) accounts is available for any of the following subscriptions:</span></span>

- <span data-ttu-id="8b3b8-120">Azure AD Premium P1 또는 P2</span><span class="sxs-lookup"><span data-stu-id="8b3b8-120">Azure AD Premium (P1 and P2)</span></span>
- <span data-ttu-id="8b3b8-121">M365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="8b3b8-121">M365 Business Premium</span></span>
- <span data-ttu-id="8b3b8-122">Office 365 E3 이상</span><span class="sxs-lookup"><span data-stu-id="8b3b8-122">Office 365 E3 and above</span></span>
- <span data-ttu-id="8b3b8-123">Azure Information Protection(AIP) (P1& P2)</span><span class="sxs-lookup"><span data-stu-id="8b3b8-123">Azure Information Protection (AIP) (P1& P2)</span></span>
- <span data-ttu-id="8b3b8-124">모든 EDU 구독(학생용 또는 교직원용 Microsoft Apps, 학생용 또는 교직원용 Exchange Online, O365 A1 이상, M365 A1 이상, 또는 학생 또는 교직원용 Azure Information Protection P1 또는 P2)</span><span class="sxs-lookup"><span data-stu-id="8b3b8-124">All EDU subscriptions (Microsoft Apps for Students or Faculty, Exchange Online for Students or Faculty, O365 A1 or above, M365 A1 or above, or Azure Information Protection P1 or P2 for Students or Faculty)</span></span>

## <span data-ttu-id="8b3b8-125">Microsoft Edge 동기화 구성</span><span class="sxs-lookup"><span data-stu-id="8b3b8-125">Configuring Microsoft Edge sync</span></span>

<span data-ttu-id="8b3b8-126">Microsoft Edge 동기화에 대한 구성 옵션은 AIP(Azure Information Protection) 서비스를 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-126">Configuration options for Microsoft Edge sync are available through the Azure Information Protection (AIP) service.</span></span> <span data-ttu-id="8b3b8-127">테넌트에 AIP 서비스가 사용되는 경우 모든 사용자가 라이선스에 관계없이 Microsoft Edge 데이터를 동기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-127">When AIP is enabled for a tenant, all users can sync Microsoft Edge data, regardless of licensing.</span></span> <span data-ttu-id="8b3b8-128">AIP를 활성화하는 방법에 대한 지침은 [여기](https://docs.microsoft.com/azure/information-protection/activate-office365)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-128">Instructions on how to enable AIP can be found [here](https://docs.microsoft.com/azure/information-protection/activate-office365).</span></span>

<span data-ttu-id="8b3b8-129">특정 사용자 집합에 대한 동기화를 제한하려면 해당 사용자에 대해 [AIP 온보딩 제어 정책](https://docs.microsoft.com/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?view=azureipps) 을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-129">To restrict sync to certain set of users, you can enable the [AIP onboarding control policy](https://docs.microsoft.com/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?view=azureipps) for those users.</span></span> <span data-ttu-id="8b3b8-130">필요한 사용자가 모두 온보딩되었는지 확인한 후에도 동기화를 계속 사용할 수 없는 경우, [Get-AIPServiceIPCv3](https://docs.microsoft.com/powershell/module/aipservice/get-aipserviceipcv3?view=azureipps) PowerShell cmdlet을 사용하여 IPCv3Service가 활성화되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-130">If sync is still not available after ensuring that all necessary users are onboarded, ensure that the IPCv3Service is enabled using the [Get-AIPServiceIPCv3](https://docs.microsoft.com/powershell/module/aipservice/get-aipserviceipcv3?view=azureipps)  PowerShell cmdlet.</span></span>

> [!CAUTION]
> <span data-ttu-id="8b3b8-131">Azure Information Protection을 활성화하면 Microsoft Word나 Microsoft Outlook과 같은 다른 응용 프로그램에서도 AIP를 사용하여 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-131">Activating Azure Information Protection will also allow other applications, such as Microsoft Word or Microsoft Outlook, to protect content with AIP.</span></span> <span data-ttu-id="8b3b8-132">또한, Edge 동기화를 제한하는 데 사용하는 모든 온보딩 제어 정책을 사용하면 다른 응용 프로그램에서 AIP를 사용하여 콘텐츠를 보호할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-132">In addition, any onboarding control policy used to restrict Edge sync will also restrict other applications from protecting content using AIP.</span></span>

## <span data-ttu-id="8b3b8-133">Microsoft Edge 및 Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="8b3b8-133">Microsoft Edge and Enterprise State Roaming</span></span>

<span data-ttu-id="8b3b8-134">새 Microsoft Edge는 모든 디바이스에서 사용자 데이터를 동기화하는 확장된 범위를 포함하는 교차 플랫폼 애플리케이션이므로 더 이상 Azure AD Enterprise State Roaming의 일부가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-134">The new Microsoft Edge is a cross-platform application with an expanded scope for syncing user data across all their devices and is no longer a part of Azure AD Enterprise State Roaming.</span></span> <span data-ttu-id="8b3b8-135">그러나 새 Microsoft Edge는 사용자의 고유한 키를 사용하는 기능과 같이 ESR의 데이터 보호 약속을 이행합니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-135">However, the new Microsoft Edge will fulfill the data protection promises of ESR, such as the ability to bring your own key.</span></span> <span data-ttu-id="8b3b8-136">자세한 내용은 [Microsoft Edge 및 Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-136">For more information, see [Microsoft Edge and Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).</span></span>

## <span data-ttu-id="8b3b8-137">동기화 그룹 정책</span><span class="sxs-lookup"><span data-stu-id="8b3b8-137">Sync group policies</span></span>

<span data-ttu-id="8b3b8-138">다음 그룹 정책은 Microsoft Edge 동기화에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-138">The following group policies impact Microsoft Edge sync:</span></span>

- <span data-ttu-id="8b3b8-139">[SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled): 동기화를 완전히 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-139">[SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled): Disables sync completely.</span></span>
- <span data-ttu-id="8b3b8-140">[SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled): 검색 기록 저장 및 동기화를 사용하지 않습니다. 이 정책은 열린 탭 동기화도 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-140">[SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled): Disables saving browsing history and sync. This policy also disables open-tabs sync.</span></span>
- <span data-ttu-id="8b3b8-141">[SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled): 동기화에서 제외되는 유형의 목록을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-141">[SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled): Configure the list of types that are excluded from synchronization.</span></span>
- <span data-ttu-id="8b3b8-142">[RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled): AD(Active Directory) 프로필에서 온-프레미스 저장소를 사용할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-142">[RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled): Allow Active Directory (AD) profiles to use on-premises storage.</span></span> <span data-ttu-id="8b3b8-143">자세한 내용은 [AD(Active Directory) 사용자를 위한 온-프레미스 동기화](https://docs.microsoft.com/DeployEdge/microsoft-edge-on-premises-sync)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-143">For more information, see [On-premises sync for Active Directory (AD) users](https://docs.microsoft.com/DeployEdge/microsoft-edge-on-premises-sync).</span></span>
- <span data-ttu-id="8b3b8-144">[ForceSync]( https://docs.microsoft.com/deployedge/microsoft-edge-policies#forcesync): 기본적으로 동기화를 설정하며 동기화하는 데 사용자 동의가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-144">[ForceSync]( https://docs.microsoft.com/deployedge/microsoft-edge-policies#forcesync): Turn sync on by default and do not require user consent to sync.</span></span>  

## <span data-ttu-id="8b3b8-145">질문과 대답</span><span class="sxs-lookup"><span data-stu-id="8b3b8-145">Frequently Asked Questions</span></span>

### <span data-ttu-id="8b3b8-146">보안 및 서버/데이터 규정 준수</span><span class="sxs-lookup"><span data-stu-id="8b3b8-146">SECURITY and SERVER/DATA COMPLIANCE</span></span>

#### <span data-ttu-id="8b3b8-147">동기화된 데이터가 암호화되나요?</span><span class="sxs-lookup"><span data-stu-id="8b3b8-147">Is the synced data encrypted?</span></span> 

<span data-ttu-id="8b3b8-148">데이터는 TLS 1.2 이상을 사용하여 전송에서 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-148">The data is encrypted in transport using TLS 1.2 or greater.</span></span> <span data-ttu-id="8b3b8-149">브라우저 기록 및 열기 탭 데이터 유형을 제외하고 대부분의 데이터 유형은 AES256을 사용하여 Microsoft 서비스에서 유휴 상태로 추가 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-149">Most data types are additionally encrypted at rest in Microsoft's service using AES256, with the exception of the browser history and open tabs datatypes.</span></span> <span data-ttu-id="8b3b8-150">이러한 데이터 형식의 동기화를 방지하려면 [SavingBrowserHistoryDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#savingbrowserhistorydisabled) 정책을 적용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-150">To prevent these data types from syncing, you can apply the [SavingBrowserHistoryDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#savingbrowserhistorydisabled) policy.</span></span>

#### <span data-ttu-id="8b3b8-151">Microsoft Edge 동기화 데이터는 어디에 저장됩니까?</span><span class="sxs-lookup"><span data-stu-id="8b3b8-151">Where is Microsoft Edge sync data stored?</span></span>

<span data-ttu-id="8b3b8-152">Azure AD 계정에 대해 동기화된 데이터는 테넌트 ID에 따라 보안 서버에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-152">Synced data for Azure AD accounts is stored in secure servers according to the tenant ID.</span></span> <span data-ttu-id="8b3b8-153">예를 들어 미국에 등록된 테넌트에 대한 데이터는 해당 지역에 지리적으로 위치하는 서버에 저장되며, Office 애플리케이션처럼 동일한 스토리지 솔루션을 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-153">For example, the data for a tenant that is registered in the United States is stored in servers geo-located for that region and uses the same storage solution as Office applications.</span></span>

#### <span data-ttu-id="8b3b8-154">데이터에서 Microsoft Edge로 동기화를 수행하는 것 외에 Microsoft의 클라우드가 계속 유지되나요?</span><span class="sxs-lookup"><span data-stu-id="8b3b8-154">Does the data ever leave Microsoft's cloud, aside from syncing to Microsoft Edge?</span></span>

<span data-ttu-id="8b3b8-155">아니요.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-155">No.</span></span>

#### <span data-ttu-id="8b3b8-156">테넌트 관리자가 자신의 키를 가져올 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="8b3b8-156">Can tenant admins bring their own key?</span></span>

<span data-ttu-id="8b3b8-157">네, [Azure Information Protection](https://azure.microsoft.com/services/information-protection/)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-157">Yes, through [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).</span></span>

#### <span data-ttu-id="8b3b8-158">엔터프라이즈 동기화가 포함된 서비스 조항은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="8b3b8-158">What terms of service does enterprise sync fall under?</span></span>

<span data-ttu-id="8b3b8-159">서비스 조건은 Azure AD 구독과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-159">The terms of service are the same terms as your Azure AD subscription.</span></span> <span data-ttu-id="8b3b8-160">모든 Azure AD 서비스는 결국 Microsoft의 [온라인 서비스 약관](https://www.microsoft.com/licensing/product-licensing/products)에 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-160">All the Azure AD terms of service ultimately fall under Microsoft's [Online Service Terms](https://www.microsoft.com/licensing/product-licensing/products).</span></span>

#### <span data-ttu-id="8b3b8-161">Microsoft Edge에서 GCC(정부 커뮤니티 클라우드) 높은 규제 준수 기능을 지원하나요?</span><span class="sxs-lookup"><span data-stu-id="8b3b8-161">Does Microsoft Edge support Government Community Cloud (GCC) High compliance?</span></span>

<span data-ttu-id="8b3b8-162">현재는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-162">Not today.</span></span> <span data-ttu-id="8b3b8-163">GCC High는 Tier D이며 Microsoft Edge는 Tier C까지 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-163">GCC High is Tier D, while Microsoft Edge supports up to Tier C.</span></span>

### <span data-ttu-id="8b3b8-164">동기화 적용 중</span><span class="sxs-lookup"><span data-stu-id="8b3b8-164">APPLYING SYNC</span></span>

#### <span data-ttu-id="8b3b8-165">레거시 Microsoft Edge를 유지하기로 결정한 기업 및 교육 고객은 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="8b3b8-165">What happens with enterprise and educational customers who decide to stay with Microsoft Edge Legacy?</span></span>

<span data-ttu-id="8b3b8-166">현재 버전의 Microsoft Edge 브라우저는 ESR 서비스에 계속 참여하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-166">The current version of Microsoft Edge browser will continue to participate in the ESR offering.</span></span>

#### <span data-ttu-id="8b3b8-167">Premium Azure AD 구독을 동기화해야 하는 이유는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="8b3b8-167">Why do I need a premium Azure AD subscription to sync?</span></span>

<span data-ttu-id="8b3b8-168">엔터프라이즈 동기화는 일부 Azure AD 계층에서 사용할 수 없는 Azure Information Protection에 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-168">Enterprise sync depends on Azure Information Protection, which is not available in all Azure AD tiers.</span></span>

#### <span data-ttu-id="8b3b8-169">Microsoft Edge는 Enterprise State Roaming을 기반으로 하나요?</span><span class="sxs-lookup"><span data-stu-id="8b3b8-169">Is Microsoft Edge sync based on Enterprise State Roaming?</span></span>

<span data-ttu-id="8b3b8-170">아니요.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-170">No.</span></span> <span data-ttu-id="8b3b8-171">ESR을 사용하여 동기화를 사용할 수 있지만, Microsoft Edge 동기화는 ESR의 일부가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-171">ESR can be used to enable sync, but Microsoft Edge sync is not a part of ESR.</span></span> <span data-ttu-id="8b3b8-172">자세한 내용은 [Microsoft Edge Sync](microsoft-edge-enterprise-sync.md)와 [Microsoft Edge 및 Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-172">For more information, see [Microsoft Edge Sync](microsoft-edge-enterprise-sync.md) and [Microsoft Edge and Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).</span></span>

#### <span data-ttu-id="8b3b8-173">Microsoft Edge는 Microsoft Edge와 IE 간의 동기화를 지원합니까?</span><span class="sxs-lookup"><span data-stu-id="8b3b8-173">Will Microsoft Edge ever support syncing between Microsoft Edge and IE?</span></span>

<span data-ttu-id="8b3b8-174">이 동기화를 지원할 계획이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-174">There are no plans to support this syncing.</span></span> <span data-ttu-id="8b3b8-175">레거시 앱을 지원하기 위해 환경에 여전히 IE가 필요한 경우 Microsoft의 [새로운 IE 모드](https://docs.microsoft.com/deployedge/edge-ie-mode)를 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-175">If you still need IE in your environment to support legacy apps, consider our [new IE mode](https://docs.microsoft.com/deployedge/edge-ie-mode).</span></span>

#### <span data-ttu-id="8b3b8-176">새 Microsoft Edge 브라우저가 Microsoft Edge 레거시와 동기화되나요?</span><span class="sxs-lookup"><span data-stu-id="8b3b8-176">Will the new Microsoft Edge browser sync with Microsoft Edge Legacy?</span></span>

<span data-ttu-id="8b3b8-177">아니요, 동기화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-177">No, it won't.</span></span> <span data-ttu-id="8b3b8-178">이 두 에코시스템을 연결하면 새 Microsoft Edge에서 동기화의 안정성이 손상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-178">We believe connecting these two ecosystems will lead to compromises in the reliability of sync in the new Microsoft Edge.</span></span> <span data-ttu-id="8b3b8-179">기존 데이터가 새 Microsoft Edge로 마이그레이션되도록 보장하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-179">We will ensure that existing data is migrated to the new Microsoft Edge.</span></span> <span data-ttu-id="8b3b8-180">사용자는 또한 원하는 브라우저에서 데이터를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-180">Users will also be able to import data from browser of their choice.</span></span> <span data-ttu-id="8b3b8-181">이는 또한 새 Microsoft Edge 브라우저에서 IE와 동기화하는 방법을 갖고 있지 않음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-181">This also means that new Microsoft Edge browser won't have a way to sync with IE.</span></span>

### <span data-ttu-id="8b3b8-182">동기화 관리</span><span class="sxs-lookup"><span data-stu-id="8b3b8-182">MANAGING SYNC</span></span>

#### <span data-ttu-id="8b3b8-183">사용자가 개인 테넌트와 동기화하는 것을 중지할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="8b3b8-183">Is it possible to stop my users from syncing with a personal tenant?</span></span>

<span data-ttu-id="8b3b8-184">직접은 아니지만 [RestrictSigninToPattern](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern) 정책을 사용하여 Microsoft Edge에 사인온 할 수 있는 프로파일을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b3b8-184">Not directly, but you can determine which profiles can sign on to Microsoft Edge using the [RestrictSigninToPattern](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern) policy.</span></span>

## <span data-ttu-id="8b3b8-185">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8b3b8-185">See also</span></span>

- [<span data-ttu-id="8b3b8-186">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="8b3b8-186">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="8b3b8-187">Microsoft Edge 및 Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="8b3b8-187">Microsoft Edge and Enterprise State Roaming</span></span>](microsoft-edge-enterprise-state-roaming.md)
