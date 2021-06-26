---
title: 가상화 데스크톱 인프라용 Edge
ms.author: anlake
author: AndreaLBarr
manager: collw
ms.date: 06/08/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 가상화된 데스크톱 인프라용 Microsoft Edge입니다.
ms.openlocfilehash: eaad1b72934b336ce86d14dd8da92a6984d21914
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2021
ms.locfileid: "11618208"
---
# <a name="microsoft-edge-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="fbcba-103">가상화된 데스크톱 인프라용 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="fbcba-103">Microsoft Edge for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="fbcba-104">이 문서에서는 가상화된 환경에서 Microsoft Edge를 사용하기 위한 요구 사항 및 제한 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcba-104">This article describes the requirements and limitations for using Microsoft Edge in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="fbcba-105">VDI란 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="fbcba-105">What is VDI?</span></span>

<span data-ttu-id="fbcba-106">VDI(가상 데스크톱 인프라)는 데이터 센터의 중앙 서버에서 데스크톱 운영 체제 및 응용 프로그램을 호스팅하는 가상화 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="fbcba-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="fbcba-107">이렇게 하면 완전히 보호되고 규정을 준수하는 중앙 집중식 원본을 사용하는 사용자가 완전히 개인 설정된 데스크톱 환경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbcba-107">This enables a fully personalized desktop experience for users with a fully secured and compliant centralized source.</span></span>

<span data-ttu-id="fbcba-108">Microsoft Edge는 보안 및 제어되는 서버 환경에서 실행되는 동안 로컬 디바이스에서 사용할 수 있는 것과 거의 동일한 방식으로 가상화된 환경에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbcba-108">Microsoft Edge can be used in such a virtualized environment in much the same ways as it can be used on the local device, all the while running from secure and controlled server environment.</span></span> <span data-ttu-id="fbcba-109">선택한 VDI 솔루션에 따라 사용자에게 인트라넷 응용 프로그램 및 사이트에 대한 원활한 액세스를 제공할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbcba-109">Depending on your chosen VDI solution it may also be possible to give your users seamless access to intranet Applications and Sites.</span></span>

<span data-ttu-id="fbcba-110">Edge의 대부분의 기능은 특별한 구성 없이 VDI 환경에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbcba-110">Most features of Edge are supported on VDI environments without any special configuration.</span></span> <span data-ttu-id="fbcba-111">그러나 최적의 환경을 보장하기 위해 아래 지침을 따르는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fbcba-111">However, to ensure an optimal experience it’s recommended to follow the guidance below.</span></span>

## <a name="platforms-certified-for-edge"></a><span data-ttu-id="fbcba-112">Edge용으로 인증된 플랫폼</span><span class="sxs-lookup"><span data-stu-id="fbcba-112">Platforms certified for Edge</span></span>

- <span data-ttu-id="fbcba-113">Azure 가상 데스크톱</span><span class="sxs-lookup"><span data-stu-id="fbcba-113">Azure Virtual Desktop</span></span>
- <span data-ttu-id="fbcba-114">Citrix 가상 앱 및 데스크톱(이전의 XenApp 및 XenDesktop)</span><span class="sxs-lookup"><span data-stu-id="fbcba-114">Citrix Virtual Apps and Desktops (formerly known as XenApp and XenDesktop)</span></span>

<span data-ttu-id="fbcba-115">Edge 팀에서 아직 다른 VDI 솔루션을 확인하지는 않았지만 Edge에서 가장 일반적인 워크플로가 지원되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcba-115">While other VDI solutions have not yet been verified by the Edge team, it is expected that the most common workflows in Edge should be supported.</span></span> <span data-ttu-id="fbcba-116">아래에 제공된 지침은 선택한 솔루션에 적용되거나 적용되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbcba-116">Guidance provided below may or may not be applicable to your chosen solution.</span></span>

## <a name="edge-on-vdi-performance-considerations"></a><span data-ttu-id="fbcba-117">VDI용 Edge 성능 고려 사항</span><span class="sxs-lookup"><span data-stu-id="fbcba-117">Edge on VDI performance considerations</span></span>

<span data-ttu-id="fbcba-118">VDI 환경을 설계할 때는 서버 구성의 제한뿐만 아니라 최적의 성능을 얻기 위해 사용자의 워크플로와 요구 사항을 신중하게 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcba-118">When designing your VDI environment you should carefully consider the workflows and needs of your users to achieve optimal performance, as well as the limits of your server configuration.</span></span>

<span data-ttu-id="fbcba-119">Edge는 VDI 환경에 Edge를 배포하기 위해 다음과 같은 최소 요구 사항을 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcba-119">Edge recommends the following minimal requirements for deploying Edge to VDI environments:</span></span>

- <span data-ttu-id="fbcba-120">vCPU – 사용자당 2-4개의 코어</span><span class="sxs-lookup"><span data-stu-id="fbcba-120">vCPU – 2-4 Cores per User</span></span>
- <span data-ttu-id="fbcba-121">RAM – 사용자당 1GB</span><span class="sxs-lookup"><span data-stu-id="fbcba-121">RAM – 1 GB per User</span></span>

<span data-ttu-id="fbcba-122">복잡하고 큰 웹 응용 프로그램 및 확장에는 더 많은 메모리가 필요하며 환경을 구성 시 이를 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcba-122">Please note that large complex web applications and extensions will require more memory and will have to be accounted for when configuring your environment.</span></span>

## <a name="edge-on-non-persisted-vdi-environments"></a><span data-ttu-id="fbcba-123">비지속형 VDI 환경의 Edge</span><span class="sxs-lookup"><span data-stu-id="fbcba-123">Edge on non-persisted VDI environments</span></span>

<span data-ttu-id="fbcba-124">많은 VDI 솔루션은 사용자에게 세션 간에 지속되는 가상 환경이 할당되는 지속형 환경과 사용자가 사용 가능한 여러 컴퓨터 중 하나에 할당되고(아마도 각 세션마다 다른 컴퓨터) 사용자 데이터가 세션 간에 동기화되거나 동기화되지 않을 수 있는 비지속형 환경에 대한 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcba-124">Many VDI solutions allow access to persisted environments, where users are assigned a virtual environment that persists between sessions, and non-persisted environments, where users are assigned to one of several available machines, possibly a different machine each session, user data may or may not sync between sessions.</span></span>

<span data-ttu-id="fbcba-125">비지속형 환경을 사용하는 경우 일반적으로 필요한 앱 및 구성을 포함하는 각 장치에 사용되는 "골든 이미지"를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fbcba-125">When using a non-persisted environment, one usually creates a “golden image” which is used for each device that includes the needed apps and configurations.</span></span> <span data-ttu-id="fbcba-126">다음은 이러한 이미지에 대해 Edge를 준비하기 위한 권장 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="fbcba-126">Below are our recommendations for preparing Edge for such an image.</span></span>

### <a name="deploy-edge"></a><span data-ttu-id="fbcba-127">Edge 배포</span><span class="sxs-lookup"><span data-stu-id="fbcba-127">Deploy Edge</span></span>

<span data-ttu-id="fbcba-128">Windows 10 버전 1803 이상을 사용하는 경우 시스템에 Microsoft Edge가 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcba-128">If you are on Windows 10, version 1803 and above, you should have Microsoft Edge installed on your system.</span></span> <span data-ttu-id="fbcba-129">그러나 이전 버전의 Windows 또는 다른 Edge 채널을 배포하려는 경우 다음 단계를 따르는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fbcba-129">However, if you are on an older version of Windows or wish to deploy a different channel of Edge, the following steps are recommended.</span></span>

1. <span data-ttu-id="fbcba-130">다음에서 VDI VM 운영 체제와 일치하는 Edge MSI 패키지를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcba-130">Download the Edge MSI package matching your VDI VM operating system from:</span></span>

    - [<span data-ttu-id="fbcba-131">비즈니스용 Microsoft Edge 다운로드 - Microsoft</span><span class="sxs-lookup"><span data-stu-id="fbcba-131">Download Microsoft Edge for Business - Microsoft</span></span>](https://www.microsoft.com/edge/business/download)

2. <span data-ttu-id="fbcba-132">다음 명령을 실행하여 VDI VM에 MSI를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcba-132">Install the MSI to the VDI VM by running the following command:</span></span>

    - `msiexec /i <path_to_msi> /qn /norestart /l*v <install_logfile_name>`

### <a name="disable-automatic-updates"></a><span data-ttu-id="fbcba-133">자동 업데이트를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="fbcba-133">Disable automatic updates</span></span>

<span data-ttu-id="fbcba-134">비지속형 컴퓨터의 경우 자동 업데이트를 사용하지 않도록 설정하고 대신 "골든 이미지"를 업데이트하여 컴퓨터 풀 간에 버전 불일치가 없도록 Edge를 업데이트하는 것이 모범 사례입니다.</span><span class="sxs-lookup"><span data-stu-id="fbcba-134">For non-persisted machines it is best practice to disable automatic updates and instead update Edge by updating the “golden image” to ensure that there are no version mismatches among the pool of machines.</span></span>

<span data-ttu-id="fbcba-135">자동 업데이트를 사용하지 않도록 설정하려면 다음 정책을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fbcba-135">See the following policies for disabling automatic updates:</span></span>

- [<span data-ttu-id="fbcba-136">업데이트 정책 재정의 기본값</span><span class="sxs-lookup"><span data-stu-id="fbcba-136">Update policy override default</span></span>](/deployedge/microsoft-edge-update-policies#updatedefault)

- [<span data-ttu-id="fbcba-137">업데이트 정책 재정의</span><span class="sxs-lookup"><span data-stu-id="fbcba-137">Update policy override</span></span>](/deployedge/microsoft-edge-update-policies#update)

### <a name="profile-management"></a><span data-ttu-id="fbcba-138">프로필 관리</span><span class="sxs-lookup"><span data-stu-id="fbcba-138">Profile management</span></span>

<span data-ttu-id="fbcba-139">비지속형 설정에서는 VM이 세션 간에 사용자 상태를 유지 관리하지 않을 수도 있고 사용자에게 이전에 사용한 적이 없는 VM이 할당될 수 있으므로 사용자 데이터가 없을 수 있다는 점을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcba-139">On non-persisted setups it is important to consider that VMs may not maintain user state between sessions or users may be assigned a VM they have never used before and as such has none of their user data.</span></span>

<span data-ttu-id="fbcba-140">Edge는 Edge에 액세스하는 방법에 관계없이 사용할 수 있도록 사용자 데이터를 동기화하는 여러 가지 방법을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcba-140">Edge supports several methods for syncing user data such that it is available regardless of how they are accessing Edge.</span></span>

### <a name="azure-ad-sync"></a><span data-ttu-id="fbcba-141">Azure AD Sync</span><span class="sxs-lookup"><span data-stu-id="fbcba-141">Azure AD Sync</span></span>

<span data-ttu-id="fbcba-142">Azure AD 플랜에서 지원하는 경우 엔터프라이즈 동기화는 Edge 사용자 데이터가 모든 사용자 장치에 동기화되도록 하는 가장 빠르고 쉬운 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="fbcba-142">If your Azure AD plan supports it, Enterprise sync is the fastest and easiest method to ensure that Edge user data is synced to all user devices.</span></span>  

<span data-ttu-id="fbcba-143">요구 사항 및 구성에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fbcba-143">See the following for more information on requirements and configuration.</span></span>  

- [<span data-ttu-id="fbcba-144">Microsoft Edge 엔터프라이즈 동기화 구성 | Microsoft Docs</span><span class="sxs-lookup"><span data-stu-id="fbcba-144">Configure Microsoft Edge enterprise sync | Microsoft Docs</span></span>](/deployedge/microsoft-edge-enterprise-sync)

### <a name="on-premise-sync-for-active-directory-users"></a><span data-ttu-id="fbcba-145">Active Directory 사용자를 위한 온-프레미스 동기화</span><span class="sxs-lookup"><span data-stu-id="fbcba-145">On-premise Sync for Active Directory Users</span></span>

<span data-ttu-id="fbcba-146">온-프레미스 동기화를 사용하면 Microsoft Edge는 Active Directory 사용자의 즐겨찾기 및 설정을 다른 컴퓨터 간에 쉽게 이동할 수 있는 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcba-146">With on-premises sync, Microsoft Edge saves an Active Directory user's favorites and settings to a file that can easily be moved between different computers.</span></span>  

<span data-ttu-id="fbcba-147">요구 사항 및 구성에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fbcba-147">See the following for more information on requirements and configuration.</span></span>  

- [<span data-ttu-id="fbcba-148">AD(Active Directory) 사용자를 위한 온-프레미스 동기화 | Microsoft Docs</span><span class="sxs-lookup"><span data-stu-id="fbcba-148">On-premises sync for Active Directory (AD) users | Microsoft Docs</span></span>](/deployedge/microsoft-edge-on-premises-sync)

### <a name="user-profile-redirection"></a><span data-ttu-id="fbcba-149">사용자 프로필 리디렉션</span><span class="sxs-lookup"><span data-stu-id="fbcba-149">User Profile Redirection</span></span>  

<span data-ttu-id="fbcba-150">이러한 비지속형 환경에서 사용자 컨텍스트가 유지되도록 전체 사용자 폴더를 마이그레이션하고 리디렉션하는 몇 가지 솔루션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbcba-150">There are several solutions for migrating and redirecting the entire user folder to ensure that user context is maintained in such non-persisted environments.</span></span> <span data-ttu-id="fbcba-151">권장 솔루션을 확인하려면 VDI 공급자에게 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="fbcba-151">Check with your VDI provider to determine the recommended solution.</span></span>

<span data-ttu-id="fbcba-152">몇 가지 인기 있는 솔루션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fbcba-152">Some popular solutions include:</span></span>

- [<span data-ttu-id="fbcba-153">FSLogix 개요 - FSLogix | Microsoft Docs</span><span class="sxs-lookup"><span data-stu-id="fbcba-153">FSLogix Overview - FSLogix | Microsoft Docs</span></span>](/fslogix/overview)
- [<span data-ttu-id="fbcba-154">Citrix 프로필 관리를 구성하는 방법</span><span class="sxs-lookup"><span data-stu-id="fbcba-154">How to Configure Citrix Profile Management</span></span>](https://support.citrix.com/article/CTX222893)

<span data-ttu-id="fbcba-155">이 방법을 사용하는 경우 사용자가 컴퓨터에 로그온하고 프로필을 마이그레이션할 때 초기 로드 시간을 줄이기 위해 백업된 사용자 폴더에서 불필요한 폴더를 제외하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fbcba-155">It is also may be recommended that when using this method unnecessary folders be excluded from the backed-up user folder to reduce initial loading times when users are logging on to a machine and the profile is being migrated.</span></span> <span data-ttu-id="fbcba-156">이 경우 크기를 줄이기 위해 백업에서 다음 폴더를 제외하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fbcba-156">If so, we recommend the following folders be excluded from your backup to reduce size.</span></span>

- <span data-ttu-id="fbcba-157">%LocalAppData%\Microsoft\Edge\User Data\Default\Cache</span><span class="sxs-lookup"><span data-stu-id="fbcba-157">%LocalAppData%\Microsoft\Edge\User Data\Default\Cache</span></span>
- <span data-ttu-id="fbcba-158">%LocalAppData%\Microsoft\Edge\User Data\Default\Code Cache</span><span class="sxs-lookup"><span data-stu-id="fbcba-158">%LocalAppData%\Microsoft\Edge\User Data\Default\Code Cache</span></span>
- <span data-ttu-id="fbcba-159">%LocalAppData%\Microsoft\Edge\User Data\Default\JumpListIconsTopSites</span><span class="sxs-lookup"><span data-stu-id="fbcba-159">%LocalAppData%\Microsoft\Edge\User Data\Default\JumpListIconsTopSites</span></span>
- <span data-ttu-id="fbcba-160">%LocalAppData%\Microsoft\Edge\User Data\Default\JumpListIconsRecentClosed</span><span class="sxs-lookup"><span data-stu-id="fbcba-160">%LocalAppData%\Microsoft\Edge\User Data\Default\JumpListIconsRecentClosed</span></span>

## <a name="known-issues"></a><span data-ttu-id="fbcba-161">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="fbcba-161">Known issues</span></span>

### <a name="microsoft-edge-crashes-in-older-versions-of-xenapp-and-xendesktop"></a><span data-ttu-id="fbcba-162">이전 버전의 XenApp 및 XenDesktop에서 Microsoft Edge 충돌</span><span class="sxs-lookup"><span data-stu-id="fbcba-162">Microsoft Edge crashes in older versions of XenApp and XenDesktop</span></span>

<span data-ttu-id="fbcba-163">이 문제는 최신 버전에서 완화해야 하지만 사용자 환경에서 이 문제가 발생하는 경우 Edge용 Citrix API 후크를 사용하지 않도록 설정하여 문제를 해결할 수 있습니다. [애플리케이션별로 Citrix API 후크를 사용하지 않도록 설정하는 방법](https://support.citrix.com/article/CTX107825)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fbcba-163">This issue should be mitigated in newer versions however if you are encountering this issue in your environment, you can work around the issue by disabling Citrix API Hooks for Edge, see [How to Disable Citrix API Hooks on a Per-application Basis.](https://support.citrix.com/article/CTX107825)</span></span>

### <a name="degraded-performance-when-rendering-pages-with-exceptionally-large-html-tables"></a><span data-ttu-id="fbcba-164">매우 큰 HTML 테이블로 페이지를 렌더링할 때 성능이 저하됨</span><span class="sxs-lookup"><span data-stu-id="fbcba-164">Degraded performance when rendering pages with exceptionally large HTML tables</span></span>

<span data-ttu-id="fbcba-165">다음 Citrix 정책은 매우 큰(30,000개 이상의 행) 테이블이 있는 html 페이지의 렌더링 속도를 늦추는 것으로 알려져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbcba-165">The following Citrix policies are known to slow rendering of html pages with very large (30,000+ row) tables.</span></span>

- <span data-ttu-id="fbcba-166">자동 키보드 디스플레이</span><span class="sxs-lookup"><span data-stu-id="fbcba-166">Automatic keyboard display</span></span>
- <span data-ttu-id="fbcba-167">콤보 상자 원격 제어</span><span class="sxs-lookup"><span data-stu-id="fbcba-167">Remote the combo box</span></span>

<span data-ttu-id="fbcba-168">자세한 내용은 [모바일 환경 정책 설정(citrix.com)](https://docs.citrix.com/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/mobile-experience-policy-settings.html)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fbcba-168">See [Mobile experience policy settings (citrix.com)](https://docs.citrix.com/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/mobile-experience-policy-settings.html) for more information.</span></span> <span data-ttu-id="fbcba-169">이러한 정책을 사용하지 않도록 설정하면 문제가 완화됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbcba-169">Disabling these policies should mitigate the issue.</span></span>

### <a name="windows-account-manager-authorization-scenarios-ie--azure-sync-fail-in-edge-when-run-as-a-citrix-seamless-application"></a><span data-ttu-id="fbcba-170">Windows 계정 관리자 권한 부여 시나리오(예: Azure 동기화)는 Citrix 원활한 응용 프로그램으로 실행되면 Edge에서 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcba-170">Windows Account Manager authorization scenarios (i.e.  Azure sync) fail in Edge when run as a Citrix seamless application</span></span>

<span data-ttu-id="fbcba-171">이는 "원활한" 모드에서 실행할 때 초기화되지 않는 시나리오에 필요한 Windows 구성 요소로 인해 Edge 및 WAM(예: Office)을 사용하는 다른 응용 프로그램에서 알려진 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="fbcba-171">This is a known issue in Edge and other applications that use WAM (i.e. Office) due to Windows components necessary for such scenarios not being initialized when running in the “seamless” mode.</span></span> <span data-ttu-id="fbcba-172">이 문제를 해결하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcba-172">To work around this issue:</span></span>

- <span data-ttu-id="fbcba-173">원활한 원격 응용 프로그램 대신 원격 데스크톱을 통해 Citrix 호스트에 Edge를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcba-173">Use Edge via a Remote Desktop to the Citrix Host instead of as a seamless remote application.</span></span>
- <span data-ttu-id="fbcba-174">대신 이 문제에 대한 완화 기능이 있는 Azure 가상 데스크톱 원격 앱을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcba-174">Use Azure Virtual Desktop remote apps instead, which has mitigation's for this issue.</span></span>
