---
title: Windows Information Protection에 대한 Microsoft Edge 지원
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 04/24/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Windows Information Protection에 대한 Microsoft Edge 지원
ms.openlocfilehash: 4ec48d258deb1cf6d4436716f14aa2561cee2a50
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980767"
---
# <span data-ttu-id="aff81-103">Windows Information Protection(WIP)에 대한 Microsoft Edge 지원</span><span class="sxs-lookup"><span data-stu-id="aff81-103">Microsoft Edge support for Windows Information Protection (WIP)</span></span>

<span data-ttu-id="aff81-104">이 문서에서는 Microsoft Edge에서 WIP(Windows Information Protection)를 지 원하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="aff81-104">This article describes how Microsoft Edge supports Windows Information Protection (WIP).</span></span>

> [!NOTE]
> <span data-ttu-id="aff81-105">이 문서는 Microsoft Edge 버전 81 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aff81-105">This applies to Microsoft Edge version 81 or later.</span></span>

## <span data-ttu-id="aff81-106">개요</span><span class="sxs-lookup"><span data-stu-id="aff81-106">Overview</span></span>

<span data-ttu-id="aff81-107">WIP(Windows Information Protection)는 인증되지 않은 또는 우발적인 노출로 부터 엔터프라이즈 데이터를 보호하는 데 도움이 되는 Windows 10 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="aff81-107">Windows Information Protection (WIP) is a Windows 10 feature that helps protect enterprise data from unauthorized or accidental disclosure.</span></span> <span data-ttu-id="aff81-108">원격 작업이 증가함에 따라 회사 데이터를 직장 외부에서 공유할 위험이 높아졌습니다.</span><span class="sxs-lookup"><span data-stu-id="aff81-108">With the rise of remote work, there's an increased risk of sharing corporate data outside the workplace.</span></span> <span data-ttu-id="aff81-109">회사 장치에서 개인 활동 및 작업 활동이 발생할 때 이 위험이 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="aff81-109">This risk increases when personal activities and work activities occur on corporate devices.</span></span>

<span data-ttu-id="aff81-110">Microsoft Edge는 사용자가 콘텐츠를 공유하고 배포하는 웹 환경에서 콘텐츠를 보호하기 위해 WIP를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="aff81-110">Microsoft Edge supports WIP to help protect content in a web environment where users often share and distribute content.</span></span>

### <span data-ttu-id="aff81-111">시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="aff81-111">System requirements</span></span>

<span data-ttu-id="aff81-112">다음 요구 사항은 엔터프라이즈에서 WIP를 사용하는 장치에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aff81-112">The follow requirements apply to devices using WIP in the enterprise:</span></span>

- <span data-ttu-id="aff81-113">Windows 10 버전 1607 이상</span><span class="sxs-lookup"><span data-stu-id="aff81-113">Windows 10, version 1607 or later</span></span>
- <span data-ttu-id="aff81-114">Windows 클라이언트 SKU만</span><span class="sxs-lookup"><span data-stu-id="aff81-114">Only Windows client SKUs</span></span>
- <span data-ttu-id="aff81-115">[WIP 필수 구성 요소](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip#prerequisites)에 설명된 관리 솔루션 중 하나</span><span class="sxs-lookup"><span data-stu-id="aff81-115">One of the management solutions described in [WIP prerequisites](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip#prerequisites)</span></span>

### <span data-ttu-id="aff81-116">Windows Information Protection의 이점</span><span class="sxs-lookup"><span data-stu-id="aff81-116">Windows Information Protection benefits</span></span>

<span data-ttu-id="aff81-117">WIP는 다음과 같은 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="aff81-117">WIP provides the following benefits:</span></span>

- <span data-ttu-id="aff81-118">직원이 환경이나 앱을 전환할 필요 없이 개인 및 회사 데이터를 명확하게 구분.</span><span class="sxs-lookup"><span data-stu-id="aff81-118">Obvious separation between personal and corporate data, without requiring employees to switch environments or apps.</span></span>
- <span data-ttu-id="aff81-119">앱을 업데이트할 필요 없이 기존 LOB(기간 업무) 앱에 대한 추가 데이터 보호 제공.</span><span class="sxs-lookup"><span data-stu-id="aff81-119">Additional data protection for existing line-of-business apps without a need to update the apps.</span></span>
- <span data-ttu-id="aff81-120">개인 데이터에는 영향을 미치지 않으면서 Intune 모바일 장치 관리(MDM) 등록 장치에서 회사 데이터를 원격으로 지우는 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aff81-120">The ability to remote wipes corporate data from Intune Mobile Device Management (MDM) enrolled devices while leaving personal data unaffected.</span></span> 
- <span data-ttu-id="aff81-121">문제 추적 및 사용자 준수 교육과 같은 수정 조치에 대한 감사 보고서</span><span class="sxs-lookup"><span data-stu-id="aff81-121">Audit reports for tracking issues and for remedial actions such as compliance training for users.</span></span>
- <span data-ttu-id="aff81-122">기존 관리 시스템과 통합하여 WIP를 구성, 배포 및 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="aff81-122">Integration with your existing management system to configure, deploy, and manage WIP.</span></span> <span data-ttu-id="aff81-123">예를 들어 Microsoft Intune, Microsoft Endpoint Configuration Manager 또는 현재 모바일 장치 관리(MDM) 시스템이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aff81-123">Some examples are Microsoft Intune, Microsoft Endpoint Configuration Manager, or your current mobile device management (MDM) system.</span></span>

## <span data-ttu-id="aff81-124">WIP 정책 및 보호 모드</span><span class="sxs-lookup"><span data-stu-id="aff81-124">WIP policy and protection modes</span></span>

<span data-ttu-id="aff81-125">정책을 사용하여 다음 표에서 설명하는 네 가지 보호 모드를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aff81-125">Using policies, you can configure the four protection modes described in the following table.</span></span> <span data-ttu-id="aff81-126">자세한 내용은 [WIP 보호 모드](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip#wip-protection-modes)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aff81-126">For more information, see [WIP-protection modes](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip#wip-protection-modes).</span></span>

| <span data-ttu-id="aff81-127">모드</span><span class="sxs-lookup"><span data-stu-id="aff81-127">Mode</span></span> | <span data-ttu-id="aff81-128">설명</span><span class="sxs-lookup"><span data-stu-id="aff81-128">Description</span></span> |
|------|-------------|
| <span data-ttu-id="aff81-129">차단</span><span class="sxs-lookup"><span data-stu-id="aff81-129">Block</span></span> | <span data-ttu-id="aff81-130">WIP에서 부적절한 데이터 공유 사례를 찾아 직원이 작업을 완료할 수 없도록 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="aff81-130">WIP looks for inappropriate data sharing practices and stops the employee from completing the action.</span></span> <span data-ttu-id="aff81-131">이 검색에는 앱 간에 엔터프라이즈 데이터를 공유하거나 조직 네트워크 외부에서 공유하려는 시도 외에도 기업에서 보호하지 않는 앱에 대한 엔터프라이즈 데이터 공유가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aff81-131">This search can include sharing enterprise data to non-enterprise-protected apps in addition to sharing enterprise data between apps or attempting to share outside of your organization's network.</span></span> |
| <span data-ttu-id="aff81-132">재정의 허용</span><span class="sxs-lookup"><span data-stu-id="aff81-132">Allow Overrides</span></span> | <span data-ttu-id="aff81-133">WIP에서 부적절한 데이터 공유를 찾아 직원이 잠재적으로 안전하지 않은 것으로 간주되는 행위를 하는 경우 해당 직원에게 경고합니다.</span><span class="sxs-lookup"><span data-stu-id="aff81-133">WIP looks for inappropriate data sharing, warning employees if they do something deemed potentially unsafe.</span></span> <span data-ttu-id="aff81-134">그러나 이 관리 모드에서는 직원이 정책을 재정의하고 데이터를 공유하여 감사 로그에 작업을 로깅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aff81-134">However, this management mode lets the employee override the policy and share the data, logging the action to your audit log.</span></span> |
| <span data-ttu-id="aff81-135">자동</span><span class="sxs-lookup"><span data-stu-id="aff81-135">Silent</span></span> | <span data-ttu-id="aff81-136">WIP는 자동으로 실행되며, 재정의 허용 모드에서 직원 상호 작용을 위해 메시지로 표시되는 어떤 항목도 중지하지 않고 부적절한 데이터 공유를 로깅합니다.</span><span class="sxs-lookup"><span data-stu-id="aff81-136">WIP runs silently, logging inappropriate data sharing, without stopping anything that would have been prompted for employee interaction while in Allow Overrides mode.</span></span> <span data-ttu-id="aff81-137">네트워크 리소스 또는 WIP로 보호된 데이터에 부적절하게 액세스하려는 앱과 같이 허용되지 않는 작업은 계속 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="aff81-137">Unallowed actions, like apps inappropriately trying to access a network resource or WIP-protected data, are still stopped.</span></span> |
| <span data-ttu-id="aff81-138">꺼짐</span><span class="sxs-lookup"><span data-stu-id="aff81-138">Off</span></span> | <span data-ttu-id="aff81-139">WIP가 꺼져 있으며 데이터를 보호하거나 감사할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aff81-139">WIP is turned off and doesn't help to protect or audit your data.</span></span> <span data-ttu-id="aff81-140">WIP를 끄면 로컬에 연결된 드라이브에서 WIP 태그가 지정된 파일의 암호를 해독하는 작업이 시도됩니다.</span><span class="sxs-lookup"><span data-stu-id="aff81-140">After you turn off WIP, an attempt is made to decrypt any WIP-tagged files on the locally attached drives.</span></span> <span data-ttu-id="aff81-141">WIP 보호를 다시 켜도 이전 암호 해독 및 정책 정보가 자동으로 다시 적용되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aff81-141">Your previous decryption and policy info isn't automatically reapplied if you turn WIP protection back on.</span></span>
 |

## <span data-ttu-id="aff81-142">Microsoft Edge에서 지원되는 WIP 기능</span><span class="sxs-lookup"><span data-stu-id="aff81-142">WIP features supported in Microsoft Edge</span></span>

<span data-ttu-id="aff81-143">Microsoft Edge 버전 81부터 다음 기능이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="aff81-143">Starting with Microsoft Edge version 81, the following features are supported:</span></span>

- <span data-ttu-id="aff81-144">업무용 사이트는 주소 표시줄에 서류 가방 아이콘으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="aff81-144">Work sites will be indicated by a briefcase icon on the address bar.</span></span>  
- <span data-ttu-id="aff81-145">업무 위치에서 다운로드한 파일은 자동으로 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="aff81-145">Files downloaded from a work location are automatically encrypted.</span></span>
- <span data-ttu-id="aff81-146">비업무 위치에 업무 파일 업로드에 대한 자동/차단/재정의 적용.</span><span class="sxs-lookup"><span data-stu-id="aff81-146">Silent/Block/Override enforcement for work file uploads to non-work locations.</span></span>  
- <span data-ttu-id="aff81-147">파일 끌어서 놓기 작업에 대한 자동/차단/재정의 적용.</span><span class="sxs-lookup"><span data-stu-id="aff81-147">Silent/Block/Override enforcement for file Drag & Drop actions.</span></span>
- <span data-ttu-id="aff81-148">클립보드 작업에 대한 자동/차단/재정의 적용.</span><span class="sxs-lookup"><span data-stu-id="aff81-148">Silent/Block/Override enforcement for Clipboard actions.</span></span>
- <span data-ttu-id="aff81-149">비업무용 프로필에서 업무 위치를 탐색하면 자동으로 업무용 프로필(Azure AD ID와 연결됨)로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="aff81-149">Browsing to work locations from non-work profiles automatically redirects to the Work Profile (associated with the Azure AD Identity.)</span></span>
- <span data-ttu-id="aff81-150">IE 모드는 전체 WIP 기능을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="aff81-150">IE Mode supports full WIP functionality.</span></span>

## <span data-ttu-id="aff81-151">Microsoft Edge에서 WIP 작업</span><span class="sxs-lookup"><span data-stu-id="aff81-151">Working with WIP in Microsoft Edge</span></span>

<span data-ttu-id="aff81-152">Microsoft Edge에서 WIP 지원이 활성화되면 업무 관련 정보에 액세스할 때 사용자에게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="aff81-152">After WIP support is enabled for Microsoft Edge, users will see when work-related information is accessed.</span></span> <span data-ttu-id="aff81-153">다음 스크린샷은 주소 표시줄의 서류 가방 아이콘을 표시하여 브라우저를 통해 업무 관련 정보에 액세스할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="aff81-153">The next screenshot shows the briefcase icon in the address bar, indicating that work-related information is accessed via the browser.</span></span>

 !["업무"로 표시 된 사이트의 주소 표시줄 표시기](./media/microsoft-edge-security-windows-information-protection/microsoft-edge-wip-notify.png)

<span data-ttu-id="aff81-155">Microsoft Edge는 사용자가 승인되지 않은 웹 사이트에서 보호된 콘텐츠를 공유할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="aff81-155">Microsoft Edge gives users the ability to share protected content in an unapproved website.</span></span> <span data-ttu-id="aff81-156">다음 스크린샷은 승인되지 않은 웹 사이트에서 보호된 콘텐츠를 사용할 수 있는 Microsoft Edge 프롬프트를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="aff81-156">The next screenshot shows the Microsoft Edge prompt that allows a user to use protected content in an unapproved website.</span></span>

 ![보호된 콘텐츠 재정의를 위한 프롬프트](./media/microsoft-edge-security-windows-information-protection/microsoft-edge-wip-override.png)

## <span data-ttu-id="aff81-158">WIP를 지원하도록 정책 구성</span><span class="sxs-lookup"><span data-stu-id="aff81-158">Configure policies to support WIP</span></span>

<span data-ttu-id="aff81-159">Microsoft Edge와 함께 WIP를 사용하려면 업무용 프로필이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aff81-159">Using WIP with Microsoft Edge requires the presence of a work profile.</span></span>

### <span data-ttu-id="aff81-160">업무용 프로필이 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="aff81-160">Ensure the presence of a work profile</span></span>

<span data-ttu-id="aff81-161">하이브리드에 연결된 컴퓨터에서 Microsoft Edge가 Azure AD(Azure Active Directory) 계정으로 자동 로그인됩니다.</span><span class="sxs-lookup"><span data-stu-id="aff81-161">On hybrid joined machines, Microsoft Edge is automatically signed in with the Azure Active Directory (Azure AD) account.</span></span> <span data-ttu-id="aff81-162">사용자가 WIP에 필요한 이 프로필을 제거하지 않도록 하려면 다음 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="aff81-162">To make sure that users don't remove this profile, which is needed for WIP, configure the following policy:</span></span>

- [<span data-ttu-id="aff81-163">NonRemovableProfileEnabled</span><span class="sxs-lookup"><span data-stu-id="aff81-163">NonRemovableProfileEnabled</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#nonremovableprofileenabled)

> [!NOTE]
> <span data-ttu-id="aff81-164">사용자의 환경이 하이브리드에 연결되어 있지 않은 경우 다음 지침을 사용하여 하이브리드에 연결할 수 있습니다. [하이브리드 Azure Active Directory 연결 구현 계획](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan).</span><span class="sxs-lookup"><span data-stu-id="aff81-164">If your environment isn't hybrid joined, you can hybrid join using these instructions: [Plan your hybrid Azure Active Directory join implementation](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan).</span></span>

<span data-ttu-id="aff81-165">하이브리드 연결을 수행할 수 없는 경우 온-프레미스 Active Directory 계정을 사용하면 Microsoft Edge에서 사용자의 도메인 계정으로 특수 업무용 프로필이 자동 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="aff81-165">If hybrid joining isn't an option, you can use on-prem Active Directory accounts to allow Microsoft Edge to auto create a special work profile with the users' domain accounts.</span></span> <span data-ttu-id="aff81-166">온-프레미스 계정은 클라우드 동기화, Office NTP 등과 같은 모든 Azure AD 기능을 받지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aff81-166">Note that on-premises accounts may not receive all of Azure AD's features, such as cloud sync, Office NTP, and so on.)</span></span>

#### <span data-ttu-id="aff81-167">AD(Active Directory) 계정</span><span class="sxs-lookup"><span data-stu-id="aff81-167">Active Directory (AD) accounts</span></span>

<span data-ttu-id="aff81-168">AD 계정의 경우 Microsoft Edge에서 특수 업무용 프로필을 자동으로 만들도록 다음 정책을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aff81-168">For AD accounts, you must configure the following policy to have the Microsoft Edge auto create a special work profile.</span></span>

- [<span data-ttu-id="aff81-169">ConfigureOnPremisesAccountAutoSignIn</span><span class="sxs-lookup"><span data-stu-id="aff81-169">ConfigureOnPremisesAccountAutoSignIn</span></span>](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#configureonpremisesaccountautosignin)

### <span data-ttu-id="aff81-170">WIP에 대한 Windows 정책</span><span class="sxs-lookup"><span data-stu-id="aff81-170">Windows policies for WIP</span></span>

<span data-ttu-id="aff81-171">Windows 정책을 사용하여 WIP를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aff81-171">You can configure WIP using Windows policies.</span></span> <span data-ttu-id="aff81-172">자세한 내용은 [Microsoft Intune을 사용하여 WIP 정책 만들기 및 배포](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/overview-create-wip-policy)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aff81-172">For more information, see [Create and deploy WIP policies using Microsoft Intune](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/overview-create-wip-policy)</span></span>

## <span data-ttu-id="aff81-173">질문과 대답</span><span class="sxs-lookup"><span data-stu-id="aff81-173">Frequently Asked Questions</span></span>

### <span data-ttu-id="aff81-174">오류 코드 2147024540을 해결하려면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="aff81-174">How do I resolve Error Code -2147024540?</span></span>

<span data-ttu-id="aff81-175">이 오류 코드는 다음 Windows Information Protection 오류에 해당합니다. *ERROR_EDP_POLICY_DENIES_OPERATION: 요청한 작업이 Windows Information Protection 정책에 의해 차단되었습니다. 자세한 내용은 시스템 관리자에게 문의하세요.*</span><span class="sxs-lookup"><span data-stu-id="aff81-175">This error code corresponds to the following Windows Information Protection error: *ERROR_EDP_POLICY_DENIES_OPERATION: The requested operation was blocked by Windows Information Protection policy. For more information, contact your system administrator.*</span></span>

<span data-ttu-id="aff81-176">Microsoft Edge는 조직에서 WIP(Windows Information Protection)를 사용하도록 설정하여 승인된 응용 프로그램의 사용자만 회사 리소스에 액세스할 수 있도록 허용하는 경우 이 오류를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="aff81-176">Microsoft Edge shows this error when the organization has enabled Windows Information Protection (WIP) to only allow users with approved applications to access corporate resources.</span></span> <span data-ttu-id="aff81-177">이 경우 Microsoft Edge는 승인된 응용 프로그램 목록에 없기 때문에 관리자는 Microsoft Edge에 대한 액세스를 허용하도록 WIP 정책을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aff81-177">In this case because Microsoft Edge isn't on the approved applications list, the admin will have to update the WIP policies to grant access to Microsoft Edge.</span></span>

<span data-ttu-id="aff81-178">다음 스크린샷은 Microsoft Intune을 사용하여 Microsoft Edge를 WIP와 관련해 허용되는 앱으로 추가하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="aff81-178">The following screenshot shows how the Microsoft Intune is used to add Microsoft Edge as an allowed app for WIP.</span></span>

 ![Microsoft Edge를 WIP용 앱으로 추가하는 Intune 대화 상자](./media/microsoft-edge-security-windows-information-protection/microsoft-edge-wip-exemption.png)

<span data-ttu-id="aff81-180">Microsoft Intune을 사용하지 않는 경우 [WIP 엔터프라이즈 AppLocker 정책](https://download.microsoft.com/download/8/9/9/8995d820-065c-4ab1-aa2a-9d6dc0cd7ffa/MsEdge%20-%20WIP%20Enterprise%20AppLocker%20Policy%20Files.zip) 파일에서 정책 업데이트를 다운로드하여 적용하세요.</span><span class="sxs-lookup"><span data-stu-id="aff81-180">If you're not using Microsoft Intune, download and apply the policy update in the [WIP Enterprise AppLocker Policy](https://download.microsoft.com/download/8/9/9/8995d820-065c-4ab1-aa2a-9d6dc0cd7ffa/MsEdge%20-%20WIP%20Enterprise%20AppLocker%20Policy%20Files.zip) file.</span></span>

## <span data-ttu-id="aff81-181">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aff81-181">See also</span></span>

- [<span data-ttu-id="aff81-182">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="aff81-182">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise) 
- [<span data-ttu-id="aff81-183">Windows Information Protection을 사용하여 엔터프라이즈 데이터 보호</span><span class="sxs-lookup"><span data-stu-id="aff81-183">Protect enterprise data using Windows Information Protection</span></span>](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)
