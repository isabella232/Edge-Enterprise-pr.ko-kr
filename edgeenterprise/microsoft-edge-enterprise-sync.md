---
title: Microsoft Edge 동기화 구성 및 문제 해결
ms.author: scottbo
author: dan-wesley
manager: silvanam
ms.date: 01/22/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 동기화 구성 및 문제 해결
ms.openlocfilehash: 36912d2fd1c33a227ce1d4b7c912f6ef1dfdcc00
ms.sourcegitcommit: 8a88fd38bdb5e132e89bf17dd2b5fb72f5d1b4b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "11297461"
---
# <span data-ttu-id="c36d9-103">Microsoft Edge 동기화 구성 및 문제 해결</span><span class="sxs-lookup"><span data-stu-id="c36d9-103">Configure and troubleshoot Microsoft Edge sync</span></span>

<span data-ttu-id="c36d9-104">이 문서에서는 로그인한 모든 장치에서 Microsoft Edge를 구성하고 사용하여 즐겨찾기, 암호 및 기타 브라우저 데이터를 동기화하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-104">This article explains how to configure and use Microsoft Edge to sync your favorites, passwords, and other browser data across all your signed-in devices.</span></span> <span data-ttu-id="c36d9-105">이 문서에서는 가장 일반적으로 발생하는 동기화 문제에 대한 문제 해결 단계도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-105">This article also provides troubleshooting steps for the most commonly encountered sync issues.</span></span> <span data-ttu-id="c36d9-106">또한 문제 해결에 필요한 로그를 수집하기 위한 권장 도구도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-106">It also includes the recommended tools for gathering the logs needed for troubleshooting.</span></span>

> [!NOTE]
> <span data-ttu-id="c36d9-107">달리 명시되지 않은 한 Microsoft Edge 버전 77 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-107">Applies to Microsoft Edge version 77 or later unless otherwise noted.</span></span>

## <span data-ttu-id="c36d9-108">개요</span><span class="sxs-lookup"><span data-stu-id="c36d9-108">Overview</span></span>

<span data-ttu-id="c36d9-109">Microsoft Edge 동기화를 사용하면 사용자가 로그인한 모든 디바이스에서 자신의 검색 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-109">Microsoft Edge sync enables users to access their browsing data across all their signed-in devices.</span></span> <span data-ttu-id="c36d9-110">동기화에서 지원하는 데이터는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-110">The data supported by sync includes:</span></span>

- <span data-ttu-id="c36d9-111">즐겨찾기</span><span class="sxs-lookup"><span data-stu-id="c36d9-111">Favorites</span></span>
- <span data-ttu-id="c36d9-112">암호</span><span class="sxs-lookup"><span data-stu-id="c36d9-112">Passwords</span></span>
- <span data-ttu-id="c36d9-113">주소 및 기타(양식 채우기)</span><span class="sxs-lookup"><span data-stu-id="c36d9-113">Addresses and more (form-fill)</span></span>
- <span data-ttu-id="c36d9-114">컬렉션</span><span class="sxs-lookup"><span data-stu-id="c36d9-114">Collections</span></span>
- <span data-ttu-id="c36d9-115">설정</span><span class="sxs-lookup"><span data-stu-id="c36d9-115">Settings</span></span>
- <span data-ttu-id="c36d9-116">확장</span><span class="sxs-lookup"><span data-stu-id="c36d9-116">Extension</span></span>
- <span data-ttu-id="c36d9-117">열린 탭(Microsoft Edge 버전 88에서 사용 가능)</span><span class="sxs-lookup"><span data-stu-id="c36d9-117">Open tabs (available in Microsoft Edge version 88)</span></span>
- <span data-ttu-id="c36d9-118">기록(Microsoft Edge 버전 88에서 사용 가능)</span><span class="sxs-lookup"><span data-stu-id="c36d9-118">History (available in Microsoft Edge version 88)</span></span>

<span data-ttu-id="c36d9-119">동기화 기능은 사용자 동의를 통해 활성화되며 위에 나열된 각 데이터 형식의 동기화를 사용자가 켜거나 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-119">Sync functionality is enabled via user consent and users can turn sync on or off for each of the data types listed above.</span></span>

> [!NOTE]
> <span data-ttu-id="c36d9-120">동기화 기능을 지원하기 위해 추가 디바이스 연결 및 구성 데이터(예: 디바이스 이름, 제조업체 및 모델)가 업로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-120">Additional device connectivity and configuration data (such as device name, make and model) is uploaded to support sync functionality.</span></span>

## <span data-ttu-id="c36d9-121">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="c36d9-121">Prerequisites</span></span>

<span data-ttu-id="c36d9-122">Azure AD(Azure Active Directory) 계정의 Microsoft Edge 동기화는 다음과 같은 모든 구독에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-122">Microsoft Edge sync for Azure Active Directory (Azure AD) accounts is available for any of the following subscriptions:</span></span>

- <span data-ttu-id="c36d9-123">Azure AD Premium(P1 또는 P2)</span><span class="sxs-lookup"><span data-stu-id="c36d9-123">Azure AD Premium (P1 or P2)</span></span>
- <span data-ttu-id="c36d9-124">M365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="c36d9-124">M365 Business Premium</span></span>
- <span data-ttu-id="c36d9-125">Office 365 E1 이상</span><span class="sxs-lookup"><span data-stu-id="c36d9-125">Office 365 E1 and above</span></span>
- <span data-ttu-id="c36d9-126">AIP(Azure Information Protection)(P1 또는 P2)</span><span class="sxs-lookup"><span data-stu-id="c36d9-126">Azure Information Protection (AIP) (P1 or P2)</span></span>
- <span data-ttu-id="c36d9-127">모든 EDU 구독(학생용 또는 교직원용 Microsoft Apps, 학생용 또는 교직원용 Exchange Online, O365 A1 이상, M365 A1 이상, 또는 학생 또는 교직원용 Azure Information Protection P1 또는 P2)</span><span class="sxs-lookup"><span data-stu-id="c36d9-127">All EDU subscriptions (Microsoft Apps for Students or Faculty, Exchange Online for Students or Faculty, O365 A1 or above, M365 A1 or above, or Azure Information Protection P1 or P2 for Students or Faculty)</span></span>

## <span data-ttu-id="c36d9-128">동기화 그룹 정책</span><span class="sxs-lookup"><span data-stu-id="c36d9-128">Sync group policies</span></span>

<span data-ttu-id="c36d9-129">다음 그룹 정책을 사용하여 Microsoft Edge 동기화를 구성하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-129">You can use the following group policies to configure and manage Microsoft Edge sync:</span></span>

- <span data-ttu-id="c36d9-130">[SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled): 동기화를 완전히 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-130">[SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled): Disables sync completely.</span></span>
- <span data-ttu-id="c36d9-131">[SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled): 검색 기록 저장 및 동기화를 사용하지 않습니다. 이 정책은 열린 탭 동기화도 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-131">[SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled): Disables saving browsing history and sync. This policy also disables open-tabs sync.</span></span>
- <span data-ttu-id="c36d9-132">[AllowDeletingBrowserHistory:](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowdeletingbrowserhistory)해당 정책을 사용하지 않도록 설정하면 기록 동기화도 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-132">[AllowDeletingBrowserHistory](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowdeletingbrowserhistory): When this policy is set to disabled, history sync will also be disabled.</span></span>
- <span data-ttu-id="c36d9-133">[SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled): 동기화에서 제외된 유형 목록을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-133">[SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled): Configure the list of types that are excluded from synchronization.</span></span>
- <span data-ttu-id="c36d9-134">[RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled): AD(Active Directory) 프로필에서 온-프레미스 저장소를 사용할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-134">[RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled): Allow Active Directory (AD) profiles to use on-premises storage.</span></span> <span data-ttu-id="c36d9-135">자세한 내용은 [AD(Active Directory) 사용자를 위한 온-프레미스 동기화](https://docs.microsoft.com/DeployEdge/microsoft-edge-on-premises-sync)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c36d9-135">For more information, see [On-premises sync for Active Directory (AD) users](https://docs.microsoft.com/DeployEdge/microsoft-edge-on-premises-sync).</span></span>
- <span data-ttu-id="c36d9-136">[ForceSync:]( https://docs.microsoft.com/deployedge/microsoft-edge-policies#forcesync)기본적으로 동기화를 켜고 동기화에 대한 사용자 동의가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-136">[ForceSync]( https://docs.microsoft.com/deployedge/microsoft-edge-policies#forcesync): Turn on sync by default and do not require user consent to sync.</span></span>  

## <span data-ttu-id="c36d9-137">Microsoft Edge 동기화 구성</span><span class="sxs-lookup"><span data-stu-id="c36d9-137">Configure Microsoft Edge sync</span></span>

<span data-ttu-id="c36d9-138">Microsoft Edge 동기화에 대한 구성 옵션은 AIP(Azure Information Protection) 서비스를 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-138">Configuration options for Microsoft Edge sync are available through the Azure Information Protection (AIP) service.</span></span> <span data-ttu-id="c36d9-139">테넌트에 AIP 서비스가 사용되는 경우 모든 사용자가 라이선스에 관계없이 Microsoft Edge 데이터를 동기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-139">When AIP is enabled for a tenant, all users can sync Microsoft Edge data, regardless of licensing.</span></span> <span data-ttu-id="c36d9-140">AIP를 활성화하는 방법에 대한 지침은 [여기](https://docs.microsoft.com/azure/information-protection/activate-office365)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-140">Instructions on how to enable AIP can be found [here](https://docs.microsoft.com/azure/information-protection/activate-office365).</span></span>

<span data-ttu-id="c36d9-141">특정 사용자 집합에 대한 동기화를 제한하려면 해당 사용자에 대해 [AIP 온보딩 제어 정책](https://docs.microsoft.com/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?view=azureipps&preserve-view=true) 을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-141">To restrict sync to certain set of users, you can enable the [AIP onboarding control policy](https://docs.microsoft.com/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?view=azureipps&preserve-view=true) for those users.</span></span> <span data-ttu-id="c36d9-142">필요한 사용자가 모두 온보딩되었는지 확인한 후에도 동기화를 계속 사용할 수 없는 경우, [Get-AIPServiceIPCv3](https://docs.microsoft.com/powershell/module/aipservice/get-aipserviceipcv3?view=azureipps&preserve-view=true) PowerShell cmdlet을 사용하여 IPCv3Service가 활성화되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-142">If sync is still not available after ensuring that all necessary users are onboarded, ensure that the IPCv3Service is enabled using the [Get-AIPServiceIPCv3](https://docs.microsoft.com/powershell/module/aipservice/get-aipserviceipcv3?view=azureipps&preserve-view=true)  PowerShell cmdlet.</span></span>

> [!CAUTION]
> <span data-ttu-id="c36d9-143">Azure Information Protection을 활성화하면 Microsoft Word나 Microsoft Outlook과 같은 다른 응용 프로그램에서도 AIP를 사용하여 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-143">Activating Azure Information Protection will also allow other applications, such as Microsoft Word or Microsoft Outlook, to protect content with AIP.</span></span> <span data-ttu-id="c36d9-144">또한, Microsoft Edge 동기화를 제한하는 데 사용하는 모든 온보딩 제어 정책을 사용하면 다른 응용 프로그램에서 AIP를 사용하여 콘텐츠를 보호할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-144">In addition, any onboarding control policy used to restrict Edge sync will also restrict other applications from protecting content using AIP.</span></span>

## <span data-ttu-id="c36d9-145">Microsoft Edge 및 엔터프라이즈 상태 로밍(ESR)</span><span class="sxs-lookup"><span data-stu-id="c36d9-145">Microsoft Edge and Enterprise State Roaming (ESR)</span></span>

<span data-ttu-id="c36d9-146">Microsoft Edge는 모든 장치에서 사용자 데이터를 동기화하기 위한 확장된 범위가 있는 플랫폼 간 응용 프로그램으로, 더 이상 Azure AD 엔터프라이즈 상태 로밍의 일부가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-146">Microsoft Edge is a cross-platform application with an expanded scope for syncing user data across all their devices and is no longaer a part of Azure AD Enterprise State Roaming.</span></span> <span data-ttu-id="c36d9-147">그러나 Microsoft Edge는 ESR의 데이터 보호 약속(예: 사용자 키를 가져오는 기능)을 이행합니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-147">However, the Microsoft Edge will fulfill the data protection promises of ESR, such as the ability to bring your own key.</span></span> <span data-ttu-id="c36d9-148">자세한 내용은 [Microsoft Edge 및 Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c36d9-148">For more information, see [Microsoft Edge and Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).</span></span>

## <span data-ttu-id="c36d9-149">동기화 문제 해결</span><span class="sxs-lookup"><span data-stu-id="c36d9-149">Troubleshoot sync issues</span></span>

<span data-ttu-id="c36d9-150">이 섹션에서는 가장 많이 발생하는 동기화 문제에 대한 문제 해결 단계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-150">This section provides troubleshooting steps for the most encountered sync issues.</span></span> <span data-ttu-id="c36d9-151">또한 문제 해결에 필요한 로그를 수집하기 위한 권장 도구도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-151">It also includes the recommended tools for gathering the logs needed for troubleshooting.</span></span>

### <span data-ttu-id="c36d9-152">ID 문제와 동기화 문제</span><span class="sxs-lookup"><span data-stu-id="c36d9-152">Identity issues versus sync issues</span></span>

<span data-ttu-id="c36d9-153">브라우저에서 사용자 ID를 유지하기 위한 인기 있는 사용 사례는 동기화를 지원하는 것입니다. 이러한 이유로 ID 문제는 동기화 문제와 자주 혼동됩니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-153">A popular use case for maintaining user identity in the browser is to support sync. For this reason, identity issues are frequently confused with sync issues.</span></span> <span data-ttu-id="c36d9-154">동기화 문제 해결을 시작하기 전에 ID와 동기화 문제의 차이점을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-154">Understand the difference between identity and sync issue before you start troubleshooting sync.</span></span>

<span data-ttu-id="c36d9-155">문제를 동기화 문제로 처리하기 전에 사용자가 유효한 계정으로 브라우저에 로그인했는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c36d9-155">Before you treat an issue as a sync issue, check to see if the user is signed into the browser with a valid account.</span></span>

<span data-ttu-id="c36d9-156">다음 스크린샷에 ID 오류의 예가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-156">The next screenshot shows an example of an identity error.</span></span> <span data-ttu-id="c36d9-157">오류는 "**마지막 토큰 오류, EDGE_AUTH_ERROR: 3, 54, 3ea**"이며 *edge://sync-internals*(**자격 증명** 아래)에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-157">The error is "**Last Token Error, EDGE_AUTH_ERROR: 3, 54, 3ea**", which is found in *edge://sync-internals* under **Credentials**:</span></span>

:::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-identity-issue.png" alt-text="마지막 토큰 오류 EDGE_AUTH_ERROR: 3,54, 3ea":::

### <span data-ttu-id="c36d9-159">일반적인 동기화 문제</span><span class="sxs-lookup"><span data-stu-id="c36d9-159">Common sync issues</span></span>

#### <span data-ttu-id="c36d9-160">문제: M365 또는 Azure Information Protection 구독에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-160">Issue: Can't access M365 or Azure Information Protection subscription</span></span>

<span data-ttu-id="c36d9-161">만료된 후 새 구독으로 대체된 이전 M365 또는 AIP(Azure Information Protection) 구독이 있나요?</span><span class="sxs-lookup"><span data-stu-id="c36d9-161">Do you have a previous M365 or Azure Information Protection (AIP) subscription that expired and then replaced with a new subscription?</span></span> <span data-ttu-id="c36d9-162">있는 경우 테넌트 ID가 변경된 것이며 서비스 데이터를 다시 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-162">If so, then the tenant ID has changed and the service data needs to be reset.</span></span> <span data-ttu-id="c36d9-163">**암호화 오류가 발생했습니다** 문제에서 데이터를 다시 설정하는 방법에 대한 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c36d9-163">See the instructions for resetting data in the **Cryptographer error encountered** issue.</span></span>

#### <span data-ttu-id="c36d9-164">문제: "이 계정에 동기화를 사용할 수 없습니다."</span><span class="sxs-lookup"><span data-stu-id="c36d9-164">Issue: “Sync is not available for this account.”</span></span>

<span data-ttu-id="c36d9-165">Azure Active Directory 계정에 이 오류가 발생하거나 DISABLED_BY_ADMIN이 *edge://sync-internals*에 나타나면, 문제가 해결될 때까지 다음 절차의 단계를 순차적으로 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="c36d9-165">If this error is encountered for an Azure Active Directory account, or if DISABLED_BY_ADMIN appears in *edge://sync-internals*, follow the steps in the next procedure sequentially until the problem is fixed.</span></span>

> [!NOTE]
> <span data-ttu-id="c36d9-166">이 오류의 원인은 일반적으로 Azure Active Directory 테넌트에서 구성을 변경해야 하므로, 이러한 문제 해결 단계는 최종 사용자가 아니라 테넌트 관리자만 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-166">Because the source of this error is usually requires a configuration change in an Azure Active Directory tenant, these troubleshooting steps can only performed by a tenant admin and not by end users.</span></span>

1. <span data-ttu-id="c36d9-167">엔터프라이즈 테넌트에 지원되는 M365 구독이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-167">Verify that the enterprise tenant has a supported M365 subscription.</span></span> <span data-ttu-id="c36d9-168">사용 가능한 구독 유형의 현재 목록이 [여기에 제공됩니다](https://docs.microsoft.com/azure/information-protection/activate-office365).</span><span class="sxs-lookup"><span data-stu-id="c36d9-168">The current list of available subscription types is [provided here](https://docs.microsoft.com/azure/information-protection/activate-office365).</span></span> <span data-ttu-id="c36d9-169">테넌트에 지원되는 구독이 없는 경우 Azure Information Protection을 별도로 구매하거나 지원되는 구독 중 하나로 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-169">If the tenant doesn't have a supported subscription, they can either purchase Azure Information Protection separately, or upgrade to one of the supported subscriptions.</span></span>
2. <span data-ttu-id="c36d9-170">지원되는 구독을 사용할 수 있는 경우 테넌트에 사용 가능한 AIP(Azure Information Protection)가 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-170">If a supported subscription is available, verify that the tenant has Azure Information Protection (AIP) available.</span></span> <span data-ttu-id="c36d9-171">AIP 상태를 확인하고 필요한 경우 AIP를 활성화하는 지침은 [여기](https://docs.microsoft.com/azure/information-protection/activate-office365)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-171">The instructions for checking the AIP status and, if necessary, activating AIP are [here](https://docs.microsoft.com/azure/information-protection/activate-office365).</span></span>
3. <span data-ttu-id="c36d9-172">2단계에서 AIP가 활성 상태이지만 동기화가 여전히 작동하지 않는 것으로 표시되면 ESR(Enterprise State Roaming)을 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-172">If step 2 shows that AIP is active but sync still doesn't work, turn on Enterprise State Roaming (ESR).</span></span> <span data-ttu-id="c36d9-173">ESR을 사용하도록 설정하는 지침은 [여기](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-173">The instructions for enabling ESR are [here](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span> <span data-ttu-id="c36d9-174">ESR이 계속 켜져 있을 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-174">Note that ESR does not need to stay on.</span></span> <span data-ttu-id="c36d9-175">이 단계로 문제가 해결될 경우 ESR을 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-175">You can turn off ESR if this step fixes the issue.</span></span>
4. <span data-ttu-id="c36d9-176">온보딩 정책을 통해 Azure Information Protection의 범위가 지정되지 않았는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-176">Confirm that Azure Information Protection is not scoped via an onboarding policy.</span></span> <span data-ttu-id="c36d9-177">[Get-AadrmOnboardingControlPolicy](https://docs.microsoft.com/powershell/module/aadrm/get-aadrmonboardingcontrolpolicy?view=azureipps) PowerShell 애플릿을 사용하여 범위 지정이 활성화되어 있는지 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-177">You can use the [Get-AadrmOnboardingControlPolicy](https://docs.microsoft.com/powershell/module/aadrm/get-aadrmonboardingcontrolpolicy?view=azureipps)  PowerShell applet to see if scoping is enabled.</span></span> <span data-ttu-id="c36d9-178">다음 두 예제에서는 범위가 지정되지 않은 구성과 특정 보안 그룹으로 범위가 지정된 구성을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-178">The next two examples show an unscoped configuration and a configuration scoped to a specific security group.</span></span>

   ```powershell
    PS C:\Work\scripts\PowerShell> Get-AadrmOnboardingControlPolicy
 
    UseRmsUserLicense SecurityGroupObjectId                Scope
    ----------------- ---------------------                -----
                False 
   ```

   ```powershell

    PS C:\Work\scripts\PowerShell> Get-AadrmOnboardingControlPolicy
 
    UseRmsUserLicense SecurityGroupObjectId                Scope
    ----------------- ---------------------                -----
                False f1488a05-8196-40a6-9483-524948b90282   All
   ```


   <span data-ttu-id="c36d9-179">범위 지정을 사용하도록 설정한 경우 영향을 받는 사용자를 범위의 보안 그룹에 추가하거나 범위를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-179">If scoping is enabled, the affected user should either be added to the security group for the scope, or the scope should be removed.</span></span> <span data-ttu-id="c36d9-180">아래 예제에서 온보딩은 AIP 범위를 표시된 보안 그룹으로 지정했으며 범위 지정은 [Set-AadrmOnboardingControlPolicy](https://docs.microsoft.com/powershell/module/aadrm/set-aadrmonboardingcontrolpolicy?view=azureipps) PowerShell 애플릿으로 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-180">In the example below, onboarding has scoped AIP to the indicated security group and the scoping should be removed with the [Set-AadrmOnboardingControlPolicy](https://docs.microsoft.com/powershell/module/aadrm/set-aadrmonboardingcontrolpolicy?view=azureipps) PowerShell applet.</span></span>

5. <span data-ttu-id="c36d9-181">테넌트에서 IPCv3Service가 켜져 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-181">Confirm that the IPCv3Service is turned on in the tenant.</span></span> <span data-ttu-id="c36d9-182">[Get-AadrmConfiguration](https://docs.microsoft.com/powershell/module/aadrm/get-aadrmconfiguration?view=azureipps) PowerShell 애플릿에는 서비스 상태가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-182">The [Get-AadrmConfiguration](https://docs.microsoft.com/powershell/module/aadrm/get-aadrmconfiguration?view=azureipps)  PowerShell applet shows the status of the service.</span></span>

   :::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-scoped-cfg-example.png" alt-text="IPCv3Service를 사용하도록 설정되어 있는지 확인합니다.":::

6. <span data-ttu-id="c36d9-184">문제가 해결되지 않은 경우 [Microsoft Edge 지원](https://www.microsoftedgeinsider.com/support)에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="c36d9-184">If the issue isn't fixed, contact [Microsoft Edge support](https://www.microsoftedgeinsider.com/support).</span></span>

#### <span data-ttu-id="c36d9-185">문제: "동기화 설정..." 또는 "동기화 서버에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-185">Issue: Stuck at "Setting up sync..." or “Couldn’t connect to the sync server.</span></span> <span data-ttu-id="c36d9-186">다시 시도..."에서 멈춰 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-186">Retrying…”</span></span>

1. <span data-ttu-id="c36d9-187">로그아웃을 시도한 다음 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-187">Try to sign out and then sign in.</span></span>
2. <span data-ttu-id="c36d9-188">*edge://sync-internals*로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-188">Go to *edge://sync-internals*.</span></span> <span data-ttu-id="c36d9-189">"**유형 정보**" 섹션에 다음 오류가 있는 경우 다음 문제 **암호화 오류가 발생했습니다**로 건너뛰세요.</span><span class="sxs-lookup"><span data-stu-id="c36d9-189">If under the "**Type info**" section the following error is present, then  skip to the following issue, **Cryptographer error encountered**.</span></span>

   `"Error:GenerateCryptoErrorsForTypes@../../components/sync/driver/data_type_manager_impl.cc:42, cryptographer error was encountered"`

3. <span data-ttu-id="c36d9-190">서버 엔드포인트 ping을 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-190">Try pinging the server endpoint.</span></span> <span data-ttu-id="c36d9-191">클라이언트용 서버 엔드포인트는 *edge://sync-internals*에서 이용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-191">The server endpoint for a client is available in *edge://sync-internals*.</span></span> <span data-ttu-id="c36d9-192">다음 스크린샷은 **환경 정보**의 엔드포인트 정보를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-192">The next screenshot shows endpoint information under **Environment Info**.</span></span>

   :::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-endpoint-info.png" alt-text="엔드포인트 정보":::

4. <span data-ttu-id="c36d9-194">서버 엔드포인트가 비어 있거나 서버를 ping할 수 없고 환경에 방화벽이 있는 경우 클라이언트 컴퓨터에서 필요한 서비스 엔드포인트를 사용할 수 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c36d9-194">If the server endpoint is empty, or if server cannot be pinged and a firewall is present in the environment, confirm that the necessary service endpoints are available to the client computer.</span></span>

   - <span data-ttu-id="c36d9-195">Microsoft Edge 동기화 서비스 엔드포인트:</span><span class="sxs-lookup"><span data-stu-id="c36d9-195">Microsoft Edge sync service endpoints:</span></span>
     - [https://edge-enterprise.activity.windows.com](https://edge-enterprise.activity.windows.com)
     - [https://edge.activity.windows.com](https://edge.activity.windows.com)
    - <span data-ttu-id="c36d9-196">Azure Information Protection 엔드포인트:</span><span class="sxs-lookup"><span data-stu-id="c36d9-196">Azure Information Protection endpoints:</span></span>
      - <span data-ttu-id="c36d9-197">[https://api.aadrm.com](https://api.aadrm.com)(테넌트 대부분의 경우)</span><span class="sxs-lookup"><span data-stu-id="c36d9-197">[https://api.aadrm.com](https://api.aadrm.com) (for most tenants)</span></span>
      - <span data-ttu-id="c36d9-198">[https://api.aadrm.de](https://api.aadrm.de)(독일의 테넌트)</span><span class="sxs-lookup"><span data-stu-id="c36d9-198">[https://api.aadrm.de](https://api.aadrm.de) (for tenants in Germany)</span></span>
      - <span data-ttu-id="c36d9-199">[https://api.aadrm.cn](https://api.aadrm.cn)(중국의 테넌트)</span><span class="sxs-lookup"><span data-stu-id="c36d9-199">[https://api.aadrm.cn](https://api.aadrm.cn) (for tenants in China)</span></span>
   - <span data-ttu-id="c36d9-200">[Windows 알림 서비스 엔드포인트](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config).</span><span class="sxs-lookup"><span data-stu-id="c36d9-200">[Windows Notification Service endpoints](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config).</span></span>

5. <span data-ttu-id="c36d9-201">그래도 문제가 해결되지 않은 경우 [Microsoft Edge 지원](https://www.microsoftedgeinsider.com/support)에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="c36d9-201">If the issue still isn't fixed, contact [Microsoft Edge support](https://www.microsoftedgeinsider.com/support).</span></span>

### <span data-ttu-id="c36d9-202">문제: 암호화 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-202">Issue: Cryptographer error encountered</span></span>

<span data-ttu-id="c36d9-203">이 오류는 **유형 정보** 아래 *edge://sync-internals*에서 볼 수 있으며 사용자의 서비스 측 데이터를 다시 설정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-203">This error is visible under **Type info** in *edge://sync-internals* and may mean that the user's service side data needs to be reset.</span></span> <span data-ttu-id="c36d9-204">다음 예에서는 암호화 오류 메시지를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-204">The following example shows a cryptography error message:</span></span>
<br><span data-ttu-id="c36d9-205">"Error:GenerateCryptoErrorsForTypes@../../components/sync/driver/data_type_manager_impl.cc:42, cryptographer error was encountered".</span><span class="sxs-lookup"><span data-stu-id="c36d9-205">"Error:GenerateCryptoErrorsForTypes@../../components/sync/driver/data_type_manager_impl.cc:42, cryptographer error was encountered".</span></span>

1. <span data-ttu-id="c36d9-206">Microsoft Edge를 다시 시작하고 *edge://sync-internals*로 이동하여 "**AAD 계정 키 상태**" 섹션을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-206">Restart Microsoft Edge and navigate to *edge://sync-internals* and check the “**AAD Account Key Status**” section</span></span>
   - <span data-ttu-id="c36d9-207">"마지막 MIP 결과"의 "성공": 암호화 오류는 서버 데이터가 분실된 키로 암호화될 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-207">"Success" in "Last MIP Result": the cryptographer error means server data might be encrypted with a lost key.</span></span> <span data-ttu-id="c36d9-208">동기화를 다시 시작하려면 데이터 재설정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-208">Data reset is needed to resume sync.</span></span>
   - <span data-ttu-id="c36d9-209">"마지막 MIP 결과"의 "사용 권한 없음": Azure AD 변경 또는 테넌트 구독 변경으로 인해 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-209">"No permissions" in "Last MIP Result": It is possibly caused by an Azure AD change or tenant subscription changes.</span></span> <span data-ttu-id="c36d9-210">동기화를 다시 시작하려면 데이터 재설정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-210">Data reset is needed to resume sync.</span></span>
   - <span data-ttu-id="c36d9-211">다른 오류는 서버 구성 문제를 의미할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-211">Other errors may mean server configuration issues.</span></span>
2. <span data-ttu-id="c36d9-212">데이터 재설정이 필요한 경우 [클라우드에서 Microsoft Edge 데이터 다시 설정](edge-learnmore-reset-data-in-cloud.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c36d9-212">If data reset is needed, see [Reset Microsoft Edge data in the cloud](edge-learnmore-reset-data-in-cloud.md).</span></span>

#### <span data-ttu-id="c36d9-213">문제: "관리자가 동기화를 해제했습니다."</span><span class="sxs-lookup"><span data-stu-id="c36d9-213">Issue: “Sync has been turned off by your administrator.”</span></span>

<span data-ttu-id="c36d9-214">[SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled) 정책이 설정되지 않았는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c36d9-214">Make sure that the [SyncDisabled policy](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled)  is not set.</span></span>

## <span data-ttu-id="c36d9-215">질문과 대답</span><span class="sxs-lookup"><span data-stu-id="c36d9-215">Frequently Asked Questions</span></span>

### <span data-ttu-id="c36d9-216">보안 및 서버/데이터 규정 준수</span><span class="sxs-lookup"><span data-stu-id="c36d9-216">SECURITY and SERVER/DATA COMPLIANCE</span></span>

#### <span data-ttu-id="c36d9-217">동기화된 데이터가 암호화되나요?</span><span class="sxs-lookup"><span data-stu-id="c36d9-217">Is the synced data encrypted?</span></span>

<span data-ttu-id="c36d9-218">데이터는 TLS 1.2 이상을 사용하는 전송에서 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-218">The data is encrypted in transport using TLS 1.2 or greater.</span></span> <span data-ttu-id="c36d9-219">모든 데이터 형식은 AES128을 사용하여 Microsoft 서비스에 있는 나머지 부분에서 추가로 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-219">All data types are additionally encrypted at rest in Microsoft's service using AES128.</span></span> <span data-ttu-id="c36d9-220">열려 있는 탭 및 기록 동기화에 사용되는 데이터 형식을 제외한 모든 데이터 형식은 [Azure Information Protection](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern) 정책을 통해 관리되는 키를 사용하여 사용자의 디바이스를 떠나기 전에 추가적으로 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-220">All data types except those used for open tab and history sync are additionally encrypted before leaving the user’s device with keys managed via the [Azure Information Protection](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern) policy.</span></span>

#### <span data-ttu-id="c36d9-221">열린 탭 및 기록 데이터에 클라이언트 측 암호화가 더 없는 이유는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="c36d9-221">Why don’t open tab and history data have more client-side encryption?</span></span>

<span data-ttu-id="c36d9-222">최종 사용자 장치에서 리소스 사용률을 줄이기 위해 열린 탭 로밍 데이터를 기반으로 기록 데이터가 서버 쪽에서 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-222">To reduce resource utilization on end-user devices, history data is generated server-side based on open tab roaming data.</span></span> <span data-ttu-id="c36d9-223">해당 데이터의 클라이언트 쪽 암호화로는 이 프로세스가 불가능합니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-223">This process would not be possible with client-side encryption of this data.</span></span> <span data-ttu-id="c36d9-224">열린 탭 및 기록 동기화를 사용하지 않도록 설정하기 위해 [SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled) 또는 [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled) 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-224">To disable open tab and history sync, apply the [SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled) or [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled) policies.</span></span>

#### <span data-ttu-id="c36d9-225">테넌트 관리자가 자신의 키를 가져올 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="c36d9-225">Can tenant admins bring their own key?</span></span>

<span data-ttu-id="c36d9-226">예,  [Azure Information Protection](https://azure.microsoft.com/services/information-protection/)을 통해 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-226">Yes, through [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).</span></span>

#### <span data-ttu-id="c36d9-227">Microsoft Edge 동기화 데이터는 어디에 저장됩니까?</span><span class="sxs-lookup"><span data-stu-id="c36d9-227">Where is Microsoft Edge sync data stored?</span></span>

<span data-ttu-id="c36d9-228">Azure AD 계정에 대해 동기화된 데이터는 테넌트 ID에 따라 보안 서버에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-228">Synced data for Azure AD accounts is stored in secure servers according to the tenant ID.</span></span> <span data-ttu-id="c36d9-229">예를 들어 미국에 등록된 테넌트에 대한 데이터는 해당 지역에 지리적으로 위치하는 서버에 저장되며, Office 애플리케이션처럼 동일한 스토리지 솔루션을 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-229">For example, the data for a tenant that is registered in the United States is stored in servers geo-located for that region and uses the same storage solution as Office applications.</span></span>

#### <span data-ttu-id="c36d9-230">데이터에서 Microsoft Edge로 동기화를 수행하는 것 외에 Microsoft의 클라우드가 계속 유지되나요?</span><span class="sxs-lookup"><span data-stu-id="c36d9-230">Does the data ever leave Microsoft's cloud, aside from syncing to Microsoft Edge?</span></span>

<span data-ttu-id="c36d9-231">아니요.</span><span class="sxs-lookup"><span data-stu-id="c36d9-231">No.</span></span>

#### <span data-ttu-id="c36d9-232">엔터프라이즈 동기화는 어느 서비스 약관에 속하나요?</span><span class="sxs-lookup"><span data-stu-id="c36d9-232">What terms of service does enterprise sync fall under?</span></span>

<span data-ttu-id="c36d9-233">Microsoft Edge 동기화에 대한 서비스 약관은 Microsoft Edge에서 볼 수 있는 Microsoft 소프트웨어 라이선스에 속해 있습니다.  *edge://terms*</span><span class="sxs-lookup"><span data-stu-id="c36d9-233">Terms of service for Microsoft Edge sync falls under the Microsoft software license viewable in Microsoft Edge at *edge://terms*.</span></span> <span data-ttu-id="c36d9-234">Azure AD 구독 및 서비스 약관은 궁극적으로 Microsoft의 [온라인 서비스 약관](https://www.microsoft.com/licensing/product-licensing/products)에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-234">Your Azure AD subscription and terms of service ultimately fall under Microsoft's [Online Service Terms](https://www.microsoft.com/licensing/product-licensing/products).</span></span>

#### <span data-ttu-id="c36d9-235">Microsoft Edge에서 GCC(정부 커뮤니티 클라우드) High의 규제 준수 기능을 지원하나요?</span><span class="sxs-lookup"><span data-stu-id="c36d9-235">Does Microsoft Edge support Government Community Cloud (GCC) High compliance?</span></span>

<span data-ttu-id="c36d9-236">현재 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-236">Not today.</span></span> <span data-ttu-id="c36d9-237">GCC High 클라우드 고객의 경우 Microsoft Edge 동기화를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-237">For customers in the GCC High cloud, Microsoft Edge sync is disabled.</span></span>

### <span data-ttu-id="c36d9-238">동기화 적용 중</span><span class="sxs-lookup"><span data-stu-id="c36d9-238">APPLYING SYNC</span></span>

#### <span data-ttu-id="c36d9-239">Microsoft Edge 동기화가 모든 M365 구독에서 지원되지 않는 이유는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="c36d9-239">Why isn’t Microsoft Edge sync supported in all M365 subscriptions?</span></span>

<span data-ttu-id="c36d9-240">엔터프라이즈 동기화는 일부 M365 구독에서 사용할 수 없는 [Azure Information Protection](https://azure.microsoft.com/services/information-protection/)에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-240">Enterprise sync depends on [Azure Information Protection](https://azure.microsoft.com/services/information-protection/), which is not available in all M365 subscriptions.</span></span>

#### <span data-ttu-id="c36d9-241">Microsoft Edge 동기화는 엔터프라이즈 상태 로밍을 기반으로 하나요?</span><span class="sxs-lookup"><span data-stu-id="c36d9-241">Is Microsoft Edge sync based on Enterprise State Roaming?</span></span>

<span data-ttu-id="c36d9-242">아니요.</span><span class="sxs-lookup"><span data-stu-id="c36d9-242">No.</span></span> <span data-ttu-id="c36d9-243">ESR을 사용하여 동기화를 사용할 수 있지만, Microsoft Edge 동기화는 ESR의 일부가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-243">ESR can be used to enable sync, but Microsoft Edge sync is not a part of ESR.</span></span> <span data-ttu-id="c36d9-244">자세한 내용은 [Microsoft Edge Sync](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-enterprise-sync)와 [Microsoft Edge 및 Enterprise State Roaming](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-enterprise-state-roaming)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c36d9-244">For more information, see [Microsoft Edge Sync](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-enterprise-sync) and [Microsoft Edge and Enterprise State Roaming](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-enterprise-state-roaming).</span></span>

#### <span data-ttu-id="c36d9-245">Microsoft Edge는 Microsoft Edge와 IE 간의 동기화를 지원합니까?</span><span class="sxs-lookup"><span data-stu-id="c36d9-245">Will Microsoft Edge ever support syncing between Microsoft Edge and IE?</span></span>

<span data-ttu-id="c36d9-246">이 동기화를 지원할 계획이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-246">There are no plans to support this syncing.</span></span> <span data-ttu-id="c36d9-247">레거시 앱을 지원하기 위해 환경에 여전히 IE가 필요한 경우 Microsoft의 [새로운 IE 모드](https://docs.microsoft.com/deployedge/edge-ie-mode)를 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="c36d9-247">If you still need IE in your environment to support legacy apps, consider our [new IE mode](https://docs.microsoft.com/deployedge/edge-ie-mode).</span></span>

#### <span data-ttu-id="c36d9-248">Microsoft Edge가 Microsoft Edge 레거시와 동기화되나요?</span><span class="sxs-lookup"><span data-stu-id="c36d9-248">Will Microsoft Edge sync with Microsoft Edge Legacy?</span></span>

<span data-ttu-id="c36d9-249">아니요, 동기화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-249">No, it won't.</span></span> <span data-ttu-id="c36d9-250">이 두 가지 에코시스템을 연결하는 것은 Microsoft Edge에서 동기화 안정성을 저하시킬 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-250">We believe connecting these two ecosystems will lead to compromises in the reliability of sync in the Microsoft Edge.</span></span> <span data-ttu-id="c36d9-251">기존 데이터가 Microsoft Edge로 마이그레이션되는 것을 보장하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-251">We will ensure that existing data is migrated to the Microsoft Edge.</span></span> <span data-ttu-id="c36d9-252">사용자는 선택한 브라우저에서 데이터를 가져올 수도 있습니다. 이는 Microsoft Edge가 IE와 동기화할 수 없음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-252">Users will also be able to import data from browser of their choice, which also means that Microsoft Edge won't have a way to sync with IE.</span></span>

### <span data-ttu-id="c36d9-253">동기화 관리</span><span class="sxs-lookup"><span data-stu-id="c36d9-253">MANAGING SYNC</span></span>

#### <span data-ttu-id="c36d9-254">사용자가 개인 테넌트와 동기화하는 것을 중지할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="c36d9-254">Is it possible to stop my users from syncing with a personal tenant?</span></span>

<span data-ttu-id="c36d9-255">직접은 아니지만 [RestrictSigninToPattern](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern) 정책을 사용하여 Microsoft Edge에 사인온 할 수 있는 프로파일을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c36d9-255">Not directly, but you can determine which profiles can sign on to Microsoft Edge using the [RestrictSigninToPattern](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern) policy.</span></span>

## <span data-ttu-id="c36d9-256">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c36d9-256">See also</span></span>

- [<span data-ttu-id="c36d9-257">Microsoft Edge Enterprise 동기화</span><span class="sxs-lookup"><span data-stu-id="c36d9-257">Microsoft Edge Enterprise Sync</span></span>](microsoft-edge-enterprise-sync.md)
- [<span data-ttu-id="c36d9-258">Microsoft Edge 및 Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="c36d9-258">Microsoft Edge and Enterprise State Roaming</span></span>](microsoft-edge-enterprise-state-roaming.md)
- [<span data-ttu-id="c36d9-259">Microsoft Edge Enterprise 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="c36d9-259">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
