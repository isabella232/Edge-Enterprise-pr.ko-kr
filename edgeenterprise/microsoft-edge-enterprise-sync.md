---
title: Microsoft Edge Enterprise 동기화 구성
ms.author: collw
author: dan-wesley
manager: silvanam
ms.date: 06/28/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 즐겨찾기, 암호 및 기타 브라우저 데이터를 동기화하도록 Microsoft Edge를 구성하는 관리자 및 사용자 옵션입니다.
ms.openlocfilehash: 5e3813664d3942e84d38e4ae1b4fd17e41049cda
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642824"
---
# <a name="configure-microsoft-edge-enterprise-sync"></a><span data-ttu-id="c8de8-103">Microsoft Edge Enterprise 동기화 구성</span><span class="sxs-lookup"><span data-stu-id="c8de8-103">Configure Microsoft Edge enterprise sync</span></span>

<span data-ttu-id="c8de8-104">이 문서는 관리자가 로그인한 모든 장치에서 사용자 즐겨찾기, 암호 및 기타 브라우저 데이터를 동기화하도록 Microsoft Edge를 구성하는 방법을 설명합니다. 관리자가 아닌 경우 이 문서를 방문하여 여러 장치에서 Microsoft Edge에 로그인하고 동기화하는 방법에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="c8de8-104">This article explains how admins can configure Microsoft Edge to sync user favorites, passwords, and other browser data across all signed-in devices.If you are not an admin, please visit this article for how to sign-in and sync Microsoft Edge across devices.</span></span> <span data-ttu-id="c8de8-105">[여러 장치에서 Microsoft Edge를 동기화하려면 로그인합니다.](https://support.microsoft.com/microsoft-edge/sign-in-to-sync-microsoft-edge-across-devices-e6ffa79b-ed52-aa32-47e2-5d5597fe4674)</span><span class="sxs-lookup"><span data-stu-id="c8de8-105">[Sign in to sync Microsoft Edge across devices](https://support.microsoft.com/microsoft-edge/sign-in-to-sync-microsoft-edge-across-devices-e6ffa79b-ed52-aa32-47e2-5d5597fe4674).</span></span>

> [!NOTE]
> <span data-ttu-id="c8de8-106">달리 명시되지 않은 한 Microsoft Edge 버전 77 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8de8-106">Applies to Microsoft Edge version 77 or later unless otherwise noted.</span></span>

## <a name="overview"></a><span data-ttu-id="c8de8-107">개요</span><span class="sxs-lookup"><span data-stu-id="c8de8-107">Overview</span></span>

<span data-ttu-id="c8de8-108">Microsoft Edge 동기화를 사용하면 사용자가 로그인한 모든 디바이스에서 자신의 검색 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8de8-108">Microsoft Edge sync enables users to access their browsing data across all their signed-in devices.</span></span> <span data-ttu-id="c8de8-109">동기화에서 지원하는 데이터는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c8de8-109">The data supported by sync includes:</span></span>

- <span data-ttu-id="c8de8-110">즐겨찾기</span><span class="sxs-lookup"><span data-stu-id="c8de8-110">Favorites</span></span>
- <span data-ttu-id="c8de8-111">암호</span><span class="sxs-lookup"><span data-stu-id="c8de8-111">Passwords</span></span>
- <span data-ttu-id="c8de8-112">주소 및 기타(양식 채우기)</span><span class="sxs-lookup"><span data-stu-id="c8de8-112">Addresses and more (form-fill)</span></span>
- <span data-ttu-id="c8de8-113">컬렉션</span><span class="sxs-lookup"><span data-stu-id="c8de8-113">Collections</span></span>
- <span data-ttu-id="c8de8-114">설정</span><span class="sxs-lookup"><span data-stu-id="c8de8-114">Settings</span></span>
- <span data-ttu-id="c8de8-115">확장</span><span class="sxs-lookup"><span data-stu-id="c8de8-115">Extension</span></span>
- <span data-ttu-id="c8de8-116">열린 탭(Microsoft Edge 버전 88에서 사용 가능)</span><span class="sxs-lookup"><span data-stu-id="c8de8-116">Open tabs (available in Microsoft Edge version 88)</span></span>
- <span data-ttu-id="c8de8-117">기록(Microsoft Edge 버전 88에서 사용 가능)</span><span class="sxs-lookup"><span data-stu-id="c8de8-117">History (available in Microsoft Edge version 88)</span></span>

<span data-ttu-id="c8de8-118">동기화 기능은 사용자 동의를 통해 활성화되며 위에 나열된 각 데이터 형식의 동기화를 사용자가 켜거나 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8de8-118">Sync functionality is enabled via user consent and users can turn sync on or off for each of the data types listed above.</span></span> <span data-ttu-id="c8de8-119">사용자가 동기화 문제가 발생하는 경우 **설정** > **프로필** > **동기화 재설정**에서 동기화를 재설정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8de8-119">If a user is experiencing a sync issue they might need to reset sync in **Settings** > **Profiles** > **Reset sync**.</span></span>

> [!NOTE]
> <span data-ttu-id="c8de8-120">동기화 기능을 지원하기 위해 추가 디바이스 연결 및 구성 데이터(예: 디바이스 이름, 제조업체 및 모델)가 업로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8de8-120">Additional device connectivity and configuration data (such as device name, make and model) is uploaded to support sync functionality.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c8de8-121">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="c8de8-121">Prerequisites</span></span>

<span data-ttu-id="c8de8-122">Azure AD(Azure Active Directory) 계정의 Microsoft Edge 동기화는 다음과 같은 모든 구독에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8de8-122">Microsoft Edge sync for Azure Active Directory (Azure AD) accounts is available for any of the following subscriptions:</span></span>

- <span data-ttu-id="c8de8-123">Azure AD Premium(P1 또는 P2)</span><span class="sxs-lookup"><span data-stu-id="c8de8-123">Azure AD Premium (P1 or P2)</span></span>
- <span data-ttu-id="c8de8-124">M365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="c8de8-124">M365 Business Premium</span></span>
- <span data-ttu-id="c8de8-125">Office 365 E1 이상</span><span class="sxs-lookup"><span data-stu-id="c8de8-125">Office 365 E1 and above</span></span>
- <span data-ttu-id="c8de8-126">AIP(Azure Information Protection)(P1 또는 P2)</span><span class="sxs-lookup"><span data-stu-id="c8de8-126">Azure Information Protection (AIP) (P1 or P2)</span></span>
- <span data-ttu-id="c8de8-127">모든 EDU 구독(학생용 또는 교직원용 Microsoft Apps, 학생용 또는 교직원용 Exchange Online, O365 A1 이상, M365 A1 이상, 또는 학생 또는 교직원용 Azure Information Protection P1 또는 P2)</span><span class="sxs-lookup"><span data-stu-id="c8de8-127">All EDU subscriptions (Microsoft Apps for Students or Faculty, Exchange Online for Students or Faculty, O365 A1 or above, M365 A1 or above, or Azure Information Protection P1 or P2 for Students or Faculty)</span></span>

## <a name="sync-group-policies"></a><span data-ttu-id="c8de8-128">동기화 그룹 정책</span><span class="sxs-lookup"><span data-stu-id="c8de8-128">Sync group policies</span></span>

<span data-ttu-id="c8de8-129">관리자는 다음 그룹 정책을 사용하여 Microsoft Edge 동기화를 구성하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8de8-129">Admins can use the following group policies to configure and manage Microsoft Edge sync:</span></span>

- <span data-ttu-id="c8de8-130">[SyncDisabled](./microsoft-edge-policies.md#syncdisabled): 동기화를 완전히 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8de8-130">[SyncDisabled](./microsoft-edge-policies.md#syncdisabled): Disables sync completely.</span></span>
- <span data-ttu-id="c8de8-131">[SavingBrowserHistoryDisabled](./microsoft-edge-policies.md#savingbrowserhistorydisabled): 검색 기록 저장 및 동기화를 사용하지 않습니다. 이 정책은 열린 탭 동기화도 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8de8-131">[SavingBrowserHistoryDisabled](./microsoft-edge-policies.md#savingbrowserhistorydisabled): Disables saving browsing history and sync. This policy also disables open-tabs sync.</span></span>
- <span data-ttu-id="c8de8-132">[AllowDeletingBrowserHistory:](./microsoft-edge-policies.md#allowdeletingbrowserhistory)해당 정책을 사용하지 않도록 설정하면 기록 동기화도 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8de8-132">[AllowDeletingBrowserHistory](./microsoft-edge-policies.md#allowdeletingbrowserhistory): When this policy is set to disabled, history sync will also be disabled.</span></span>
- <span data-ttu-id="c8de8-133">[SyncTypesListDisabled](./microsoft-edge-policies.md#synctypeslistdisabled): 동기화에서 제외된 유형 목록을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c8de8-133">[SyncTypesListDisabled](./microsoft-edge-policies.md#synctypeslistdisabled): Configure the list of types that are excluded from synchronization.</span></span>
- <span data-ttu-id="c8de8-134">[RoamingProfileSupportEnabled](./microsoft-edge-policies.md#roamingprofilesupportenabled): AD(Active Directory) 프로필에서 온-프레미스 저장소를 사용할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="c8de8-134">[RoamingProfileSupportEnabled](./microsoft-edge-policies.md#roamingprofilesupportenabled): Allow Active Directory (AD) profiles to use on-premises storage.</span></span> <span data-ttu-id="c8de8-135">자세한 내용은 [AD(Active Directory) 사용자를 위한 온-프레미스 동기화](./microsoft-edge-on-premises-sync.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c8de8-135">For more information, see [On-premises sync for Active Directory (AD) users](./microsoft-edge-on-premises-sync.md).</span></span>
- <span data-ttu-id="c8de8-136">[ForceSync:](/deployedge/microsoft-edge-policies#forcesync)기본적으로 동기화를 켜고 동기화에 대한 사용자 동의가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8de8-136">[ForceSync](/deployedge/microsoft-edge-policies#forcesync): Turn on sync by default and do not require user consent to sync.</span></span>  

## <a name="configure-microsoft-edge-sync"></a><span data-ttu-id="c8de8-137">Microsoft Edge 동기화 구성</span><span class="sxs-lookup"><span data-stu-id="c8de8-137">Configure Microsoft Edge sync</span></span>

<span data-ttu-id="c8de8-138">Microsoft Edge 동기화에 대한 구성 옵션은 AIP(Azure Information Protection) 서비스를 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8de8-138">Configuration options for Microsoft Edge sync are available through the Azure Information Protection (AIP) service.</span></span> <span data-ttu-id="c8de8-139">테넌트에 AIP 서비스가 사용되는 경우 모든 사용자가 라이선스에 관계없이 Microsoft Edge 데이터를 동기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8de8-139">When AIP is enabled for a tenant, all users can sync Microsoft Edge data, regardless of licensing.</span></span> <span data-ttu-id="c8de8-140">AIP를 활성화하는 방법에 대한 지침은 [여기](/azure/information-protection/activate-office365)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8de8-140">Instructions on how to enable AIP can be found [here](/azure/information-protection/activate-office365).</span></span>

<span data-ttu-id="c8de8-141">특정 사용자 집합에 대한 동기화를 제한하려면 해당 사용자에 대해 [AIP 온보딩 제어 정책](/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?preserve-view=true&view=azureipps) 을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8de8-141">To restrict sync to certain set of users, you can enable the [AIP onboarding control policy](/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?preserve-view=true&view=azureipps) for those users.</span></span> <span data-ttu-id="c8de8-142">필요한 사용자가 모두 온보딩되었는지 확인한 후에도 동기화를 계속 사용할 수 없는 경우, [Get-AIPServiceIPCv3](/powershell/module/aipservice/get-aipserviceipcv3?preserve-view=true&view=azureipps) PowerShell cmdlet을 사용하여 IPCv3Service가 활성화되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c8de8-142">If sync is still not available after ensuring that all necessary users are onboarded, ensure that the IPCv3Service is enabled using the [Get-AIPServiceIPCv3](/powershell/module/aipservice/get-aipserviceipcv3?preserve-view=true&view=azureipps)  PowerShell cmdlet.</span></span>

> [!CAUTION]
> <span data-ttu-id="c8de8-143">Azure Information Protection을 활성화하면 Microsoft Word나 Microsoft Outlook과 같은 다른 응용 프로그램에서도 AIP를 사용하여 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8de8-143">Activating Azure Information Protection will also allow other applications, such as Microsoft Word or Microsoft Outlook, to protect content with AIP.</span></span> <span data-ttu-id="c8de8-144">또한, Microsoft Edge 동기화를 제한하는 데 사용하는 모든 온보딩 제어 정책을 사용하면 다른 응용 프로그램에서 AIP를 사용하여 콘텐츠를 보호할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c8de8-144">In addition, any onboarding control policy used to restrict Edge sync will also restrict other applications from protecting content using AIP.</span></span>

## <a name="microsoft-edge-and-enterprise-state-roaming-esr"></a><span data-ttu-id="c8de8-145">Microsoft Edge 및 엔터프라이즈 상태 로밍(ESR)</span><span class="sxs-lookup"><span data-stu-id="c8de8-145">Microsoft Edge and Enterprise State Roaming (ESR)</span></span>

<span data-ttu-id="c8de8-146">Microsoft Edge는 모든 장치에서 사용자 데이터를 동기화하기 위한 확장된 범위가 있는 플랫폼 간 응용 프로그램으로, 더 이상 Azure AD Enterprise State Roaming의 일부가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c8de8-146">Microsoft Edge is a cross-platform application with an expanded scope for syncing user data across all their devices and is no longer a part of Azure AD Enterprise State Roaming.</span></span> <span data-ttu-id="c8de8-147">그러나 Microsoft Edge는 ESR의 데이터 보호 약속(예: 사용자 키를 가져오는 기능)을 이행합니다.</span><span class="sxs-lookup"><span data-stu-id="c8de8-147">However, the Microsoft Edge will fulfill the data protection promises of ESR, such as the ability to bring your own key.</span></span> <span data-ttu-id="c8de8-148">자세한 내용은 [Microsoft Edge 및 Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c8de8-148">For more information, see [Microsoft Edge and Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c8de8-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c8de8-149">See also</span></span>

- [<span data-ttu-id="c8de8-150">Microsoft Edge Enterprise 동기화</span><span class="sxs-lookup"><span data-stu-id="c8de8-150">Microsoft Edge Enterprise Sync</span></span>](microsoft-edge-enterprise-sync.md)
- [<span data-ttu-id="c8de8-151">Microsoft Edge 동기화 문제 진단 및 해결</span><span class="sxs-lookup"><span data-stu-id="c8de8-151">Diagnose and fix Microsoft Edge sync issues</span></span>](microsoft-edge-troubleshoot-enterprise-sync.md)
- [<span data-ttu-id="c8de8-152">Microsoft Edge 및 Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="c8de8-152">Microsoft Edge and Enterprise State Roaming</span></span>](microsoft-edge-enterprise-state-roaming.md)
- [<span data-ttu-id="c8de8-153">Microsoft Edge Enterprise 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="c8de8-153">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)