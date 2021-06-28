---
title: Microsoft Edge 및 Windows Defender Application Guard
ms.author: srugh
author: AndreaLBarr
manager: seanlyn
ms.date: 05/06/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Defender Application Guard에 대한 Microsoft Edge 지원
ms.openlocfilehash: 7374810eb19ada298963817844e52184c0271a8c
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2021
ms.locfileid: "11617998"
---
# <a name="microsoft-edge-support-for-microsoft-defender-application-guard"></a><span data-ttu-id="fd35c-103">Microsoft Defender Application Guard에 대한 Microsoft Edge 지원</span><span class="sxs-lookup"><span data-stu-id="fd35c-103">Microsoft Edge support for Microsoft Defender Application Guard</span></span>

<span data-ttu-id="fd35c-104">이 문서에서는 Microsoft Edge에서 Microsoft Defender Application Guard(Application Guard)를 지원하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-104">This article describes how Microsoft Edge supports Microsoft Defender Application Guard (Application Guard).</span></span>

> [!NOTE]
> <span data-ttu-id="fd35c-105">이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-105">This article applies to Microsoft Edge version 77 or later.</span></span>

## <a name="overview"></a><span data-ttu-id="fd35c-106">개요</span><span class="sxs-lookup"><span data-stu-id="fd35c-106">Overview</span></span>

<span data-ttu-id="fd35c-107">엔터프라이즈의 보안 설계자는 생산성과 보안 사이의 균형을 조율해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-107">Security architects in the enterprise must deal with the tension that exists between productivity and security.</span></span> <span data-ttu-id="fd35c-108">브라우저를 잠그는 것은 비교적 쉬우며 소수의 신뢰할 수 있는 사이트만 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-108">It's relatively easy to lock down a browser and only allow a handful of trusted sites to load.</span></span> <span data-ttu-id="fd35c-109">이 접근 방식은 전반적인 보안 환경을 개선하지만 생산성은 떨어집니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-109">This approach will improve the overall security posture but is arguably less productive.</span></span> <span data-ttu-id="fd35c-110">생산성을 향상시키기 위해 제한을 줄이면 위험 프로파일이 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-110">If you make it less restrictive to improve productivity, you increase the risk profile.</span></span> <span data-ttu-id="fd35c-111">균형을 잘 맞추는 것은 어렵습니다!</span><span class="sxs-lookup"><span data-stu-id="fd35c-111">It's a hard balance to strike!</span></span>

<span data-ttu-id="fd35c-112">끊임없이 변화하는 위협 환경에서 새로운 위협에 대응하는 것은 더욱 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-112">It's even harder to keep up with new emerging threats in this constantly changing threat landscape.</span></span> <span data-ttu-id="fd35c-113">브라우저의 기본 작업은 사용자가 신뢰할 수 없는 출처의 신뢰할 수 없는 콘텐츠에 액세스하고 다운로드하고 실행할 수 있도록 하는 것이기 때문에 브라우저는 클라이언트 장치에서 주된 공격 노출 영역으로 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-113">Browsers remain the primary attack surface on client devices because the browser's basic job is to let users access, download, and open untrusted content from untrusted sources.</span></span> <span data-ttu-id="fd35c-114">악의적인 행위자들은 브라우저를 대상으로 새로운 형태의 공격을 소셜 엔지니어링하기 위해 끊임없이 노력하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-114">Malicious actors are constantly working to social engineer new forms of attacks against the browser.</span></span> <span data-ttu-id="fd35c-115">보안 사고 방지 또는 검색/응답 전략은 100% 안전을 보장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-115">Security incident prevention or detection/response strategies can't guarantee 100% safety.</span></span>

<span data-ttu-id="fd35c-116">고려해야 할 주요 보안 전략은 [침입 가정 방법론](/office365/Enterprise/office-365-monitoring-and-testing#assume-breach-methodology)입니다. 이는 공격을 막기위한 노력과 상관없이 공격이 적어도 한 번은 성공할 것이라는 사실의 수용을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-116">A key security strategy to consider is the [Assume Breach Methodology](/office365/Enterprise/office-365-monitoring-and-testing#assume-breach-methodology), which means there's an acceptance that an attack is going to succeed at least once regardless of efforts to prevent it.</span></span> <span data-ttu-id="fd35c-117">이 방법론에서는 피해를 막기 위해 방어를 구축해야 하므로 이 시나리오에서 회사 네트워크 및 기타 리소스를 보호해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-117">This mindset requires building defenses to contain the damage, which ensures that corporate network and other resources remain protected in this scenario.</span></span>  <span data-ttu-id="fd35c-118">Microsoft Edge용 Application Guard를 배포하는 것이 이 전략에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-118">Deploying Application Guard for Microsoft Edge fits right into this strategy.</span></span>

## <a name="about-application-guard"></a><span data-ttu-id="fd35c-119">Application Guard 정보</span><span class="sxs-lookup"><span data-stu-id="fd35c-119">About Application Guard</span></span>

<span data-ttu-id="fd35c-120">Windows 10 및 Microsoft Edge용으로 설계된 Application Guard는 하드웨어 격리 방식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-120">Designed for Windows 10 and Microsoft Edge, Application Guard uses a hardware isolation approach.</span></span> <span data-ttu-id="fd35c-121">이 방법을 사용하면 컨테이너 내에서 신뢰할 수 없는 사이트 탐색을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-121">This approach lets untrusted site navigation launch inside a container.</span></span> <span data-ttu-id="fd35c-122">하드웨어 격리는 사용자가 손상되거나 악의적인 사이트를 방문하는 경우 기업이 회사 네트워크와 데이터를 보호할 수 있도록 도와줍니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-122">Hardware isolation helps enterprises safeguard their corporate network and data in case users visit a site that is compromised or is malicious.</span></span>

<span data-ttu-id="fd35c-123">엔터프라이즈 관리자는 신뢰할 수 있는 사이트, 클라우드 리소스 및 내부 네트워크를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-123">The enterprise administrator defines what are trusted sites, cloud resources, and internal networks.</span></span> <span data-ttu-id="fd35c-124">신뢰할 수 있는 사이트 목록에 없는 모든 항목은 신뢰할 수 없는 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-124">Everything that's not in the trusted sites list is considered untrusted.</span></span> <span data-ttu-id="fd35c-125">이러한 사이트는 회사 네트워크와 사용자 장치의 데이터에서 격리됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-125">These sites are isolated from the corporate network and data on the user's device.</span></span>

<span data-ttu-id="fd35c-126">자세한 내용을 보려면 다음을 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="fd35c-126">For more information:</span></span>

- <span data-ttu-id="fd35c-127">[Application Guard를 사용하여 Microsoft Edge 브라우저 격리](microsoft-edge-video-security-application-guard.md) 비디오를 시청하세요.</span><span class="sxs-lookup"><span data-stu-id="fd35c-127">watch our video [Microsoft Edge browser isolation using Application Guard](microsoft-edge-video-security-application-guard.md)</span></span>
- <span data-ttu-id="fd35c-128">[Application Guard란 무엇이며 어떤 방식으로 작동합니까?](/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview#what-is-application-guard-and-how-does-it-work)를 읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="fd35c-128">read [What is Application Guard and how does it work?](/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview#what-is-application-guard-and-how-does-it-work)</span></span>

<span data-ttu-id="fd35c-129">다음 스크린샷은 사용자가 안전한 공간에서 탐색하고 있음을 보여주는 Application Guard 메시지의 예를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-129">The next screenshot shows an example of Application Guard's message showing that the user is browsing in a safe space.</span></span>

![Application Guard 안전한 탐색 메시지](media/microsoft-edge-security-windows-defender-application-guard/wd-application-guard-1.png)

## <a name="whats-new"></a><span data-ttu-id="fd35c-131">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="fd35c-131">What's new</span></span>

<span data-ttu-id="fd35c-132">새로운 Microsoft Edge 브라우저의 Application Guard 지원은 Microsoft Edge 레거시와 기능적으로 동등하며 몇 가지 개선 사항이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-132">Application Guard support in the new Microsoft Edge  browser has functional parity with Microsoft Edge Legacy and includes several improvements.</span></span>

### <a name="favorites-synchronizing-from-the-host-to-the-container"></a><span data-ttu-id="fd35c-133">호스트에서 컨테이너로 동기화하는 즐겨찾기</span><span class="sxs-lookup"><span data-stu-id="fd35c-133">Favorites synchronizing from the host to the container</span></span>

<span data-ttu-id="fd35c-134">일부 고객은 호스트 브라우저와 Application Guard의 컨테이너 간에 즐겨찾기 동기화를 요청했습니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-134">Some of our customers have been asking for favorites sync between the host browser and the container in Application Guard.</span></span> <span data-ttu-id="fd35c-135">Microsoft Edge 91부터 사용자는 이제 호스트에서 컨테이너로 즐겨찾기 동기화를 위해 Application Guard를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-135">Starting from Microsoft Edge 91, users now have the option to configure Application Guard to synchronize their favorites from the host to the container.</span></span> <span data-ttu-id="fd35c-136">이렇게 하면 새 즐겨찾기도 컨테이너에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-136">This ensures new favorites appear on the container as well.</span></span>

<span data-ttu-id="fd35c-137">이 지원은 정책을 통해 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-137">This support can be controlled via policy.</span></span> <span data-ttu-id="fd35c-138">[ApplicationGuardFavoritesSyncEnabled](/deployedge/microsoft-edge-policies#applicationguardfavoritessyncenabled) Edge 정책을 업데이트하여 즐겨찾기 동기화를 사용하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-138">You can update the Edge policy [ApplicationGuardFavoritesSyncEnabled](/deployedge/microsoft-edge-policies#applicationguardfavoritessyncenabled) to enable or disable favorites sync.</span></span>

> [!Note]
> <span data-ttu-id="fd35c-139">보안상의 이유로 즐겨찾기 동기화는 호스트에서 컨테이너로만 가능하고 다른 방법과는 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-139">For security reasons, favorites sync is only possible from the host to the container and not the other way around.</span></span> <span data-ttu-id="fd35c-140">호스트와 컨테이너에서 즐겨찾기 목록이 통합되도록 컨테이너 내에서 즐겨찾기 관리를 사용하지 않도록 설정했습니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-140">To ensure a unified list of favorites across the host and the container, we have disabled favorites management inside the container.</span></span>

### <a name="identify-network-traffic-originating-from-the-container"></a><span data-ttu-id="fd35c-141">컨테이너에서 시작된 네트워크 트래픽 식별</span><span class="sxs-lookup"><span data-stu-id="fd35c-141">Identify network traffic originating from the container</span></span>

<span data-ttu-id="fd35c-142">컨테이너에서 오는 네트워크 트래픽을 식별하려는 특정 구성에서 여러 고객이 WDAG를 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-142">Several customers are using WDAG in a specific configuration where they want to identify network traffic coming from the container.</span></span> <span data-ttu-id="fd35c-143">이에 대한 몇 가지 시나리오는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-143">Some of the scenarios for this are:</span></span>

- <span data-ttu-id="fd35c-144">신뢰할 수 없는 소수의 사이트에 대한 액세스만 제한하려면</span><span class="sxs-lookup"><span data-stu-id="fd35c-144">To restrict access to only a handful of untrusted sites</span></span>
- <span data-ttu-id="fd35c-145">컨테이너에서만 인터넷 액세스를 허용하려면</span><span class="sxs-lookup"><span data-stu-id="fd35c-145">To allow internet access from the container only</span></span>

<span data-ttu-id="fd35c-146">Microsoft Edge 버전 91부터는 엔터프라이즈에서 프록시를 사용하여 트래픽을 필터링하고 특정 정책을 적용할 수 있도록 Application Guard 컨테이너에서 발생하는 네트워크 트래픽에 태그를 지정하는 지원이 기본적으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-146">Starting with Microsoft Edge version 91, there’s built in support to tag network traffic originating from Application Guard containers, allowing enterprises to use proxy to filter out traffic and apply specific policies.</span></span> <span data-ttu-id="fd35c-147">헤더를 사용하여 [ApplicationGuardTrafficIdentificationEnabled](/deployedge/microsoft-edge-policies#applicationguardtrafficidentificationenabled)를 사용하여 컨테이너 또는 호스트를 통과하는 트래픽을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-147">You can use the header to identify which traffic is through the container or the host using [ApplicationGuardTrafficIdentificationEnabled](/deployedge/microsoft-edge-policies#applicationguardtrafficidentificationenabled).</span></span>

### <a name="extension-support-inside-the-container"></a><span data-ttu-id="fd35c-148">컨테이너 내부의 확장 프로그램지원</span><span class="sxs-lookup"><span data-stu-id="fd35c-148">Extension support inside the container</span></span>

<span data-ttu-id="fd35c-149">컨테이너 내부의 확장 프로그램 지원은 고객으로부터 받은 최상위 요청 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-149">Extension support inside the container has been one of the top requests from the customers.</span></span> <span data-ttu-id="fd35c-150">시나리오는 컨테이너 내에서 광고 차단기를 실행하고 브라우저 성능을 컨테이너 내에서 자체적으로 확장한 사용자 지정 확장 프로그램을 실행할 수 있는 기능까지 다양합니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-150">Scenarios ranged from wanting to run ad-blockers inside the container to boost browser performance to having the ability to run custom home-grown extensions inside the container.</span></span>

<span data-ttu-id="fd35c-151">컨테이너에서의 확장 프로그램 설치가 이제 Microsoft Edge 버전 81부터 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-151">Extension installs in the container is now supported, starting from Microsoft Edge version 81.</span></span> <span data-ttu-id="fd35c-152">이 지원은 정책을 통해 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-152">This support can be controlled via policy.</span></span> <span data-ttu-id="fd35c-153">[ExtensionInstallForcelist](./microsoft-edge-policies.md#extensioninstallforcelist) 정책에서 사용되는 `updateURL`은(는) Application Guard에서 사용하는 네트워크 격리 정책에서 중립 리소스로 추가되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-153">The `updateURL` that gets used in [ExtensionInstallForcelist](./microsoft-edge-policies.md#extensioninstallforcelist) policy should be added as Neutral Resources in the Network Isolation policies used by Application Guard.</span></span>

<span data-ttu-id="fd35c-154">컨테이너 지원의 몇 가지 예는 다음 시나리오를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-154">Some examples of container support include the following scenarios:</span></span>

- <span data-ttu-id="fd35c-155">호스트에 확장 프로그램 강제 설치</span><span class="sxs-lookup"><span data-stu-id="fd35c-155">Force installs of an extension on the host</span></span>
- <span data-ttu-id="fd35c-156">호스트에서 확장 프로그램 제거</span><span class="sxs-lookup"><span data-stu-id="fd35c-156">Removing an extension from the host</span></span>
- <span data-ttu-id="fd35c-157">호스트에서 확장 프로그램이 차단됨</span><span class="sxs-lookup"><span data-stu-id="fd35c-157">Extensions blocked on the host</span></span>

> [!NOTE]
> <span data-ttu-id="fd35c-158">확장 프로그램 스토어에서 컨테이너 내부의 개별 확장 프로그램을 수동으로 설치할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-158">It's also possible to manually install individual extensions inside the container from the extension store.</span></span> <span data-ttu-id="fd35c-159">[지속성 허용](/windows/security/threat-protection/microsoft-defender-application-guard/configure-md-app-guard#application-specific-settings) 정책이 활성화된 경우 수동으로 설치된 확장 프로그램은 컨테이너에만 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-159">Manually installed extensions will only persist in the container when [Allow Persistence](/windows/security/threat-protection/microsoft-defender-application-guard/configure-md-app-guard#application-specific-settings) policy is enabled.</span></span>

### <a name="identifying-application-guard-traffic-via-dual-proxy"></a><span data-ttu-id="fd35c-160">이중 프록시를 통해 Application Guard 트래픽을 식별</span><span class="sxs-lookup"><span data-stu-id="fd35c-160">Identifying Application Guard traffic via Dual Proxy</span></span>

<span data-ttu-id="fd35c-161">일부 기업 고객은 프록시 수준에서 Microsoft Defender Application Guard 컨테이너에서 나오는 웹 트래픽을 식별해야하는 특정 사용 사례와 함께 Application Guard를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-161">Some enterprise customers are deploying Application Guard with a specific use case where they need to identify web traffic coming out of a Microsoft Defender Application Guard container at the proxy level.</span></span> <span data-ttu-id="fd35c-162">Stable Channel 버전 84를 시작으로 Microsoft Edge는 이 요구 사항을 다루기 위해 이중 프록시를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-162">Starting with Stable Channel version 84, Microsoft Edge will support dual proxy to address this requirement.</span></span> <span data-ttu-id="fd35c-163">[ApplicationGuardContainerProxy](./microsoft-edge-policies.md#applicationguardcontainerproxy) 정책을 사용하여 이 기능을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-163">You can configure this functionality using the [ApplicationGuardContainerProxy](./microsoft-edge-policies.md#applicationguardcontainerproxy) policy.</span></span>

<span data-ttu-id="fd35c-164">다음 그림에서는 Microsoft Edge의 이중 프록시 구조를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-164">The following drawing shows the dual proxy architecture for Microsoft Edge.</span></span>

![Application Guard를 위한 이중 프록시 아키텍처](media/microsoft-edge-security-windows-defender-application-guard/wd-application-guard-dual-proxy.png)

### <a name="diagnostic-page-for-troubleshooting"></a><span data-ttu-id="fd35c-166">문제 해결을 위한 진단 페이지</span><span class="sxs-lookup"><span data-stu-id="fd35c-166">Diagnostic page for troubleshooting</span></span>

<span data-ttu-id="fd35c-167">또 다른 사용자 불만 사항은 문제가 보고될 때 장치의 Application Guard 구성 문제를 해결하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-167">Another user pain point is troubleshooting the Application Guard configuration on a device when a problem is reported.</span></span> <span data-ttu-id="fd35c-168">Microsoft Edge에는 사용자 문제를 해결하기 위한 진단 페이지(`edge://application-guard-internals`)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-168">Microsoft Edge has a diagnostics page (`edge://application-guard-internals`) to troubleshoot user issues.</span></span> <span data-ttu-id="fd35c-169">이러한 진단 중 하나가 사용자 장치의 구성에 따라 URL 신뢰를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-169">One of these diagnostics is being able to check the URL trust based on the configuration on the user's device.</span></span>

<span data-ttu-id="fd35c-170">다음 스크린샷은 장치에서 사용자가 보고한 문제를 진단하는 데 도움이 되는 다중 탭 진단 페이지를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-170">The next screenshot shows a multiple tab diagnostics page to help diagnose user reported issues on the device.</span></span>

![Application Guard 진단 페이지](media/microsoft-edge-security-windows-defender-application-guard/wd-application-guard-2.png)

### <a name="microsoft-edge-updates-in-the-container"></a><span data-ttu-id="fd35c-172">컨테이너의 Microsoft Edge 업데이트</span><span class="sxs-lookup"><span data-stu-id="fd35c-172">Microsoft Edge updates in the container</span></span>

<span data-ttu-id="fd35c-173">컨테이너의 Microsoft Edge 레거시 업데이트는 Windows OS 업데이트 주기의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-173">Microsoft Edge Legacy updates in the container are part of the Windows OS update cycle.</span></span> <span data-ttu-id="fd35c-174">새 버전의 Microsoft Edge는 Windows OS와 독립적으로 자체 업데이트되므로 컨테이너 업데이트에 더 이상 종속되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-174">Because the new version of Microsoft Edge updates itself independent of the Windows OS, there is no longer any dependency on container updates.</span></span> <span data-ttu-id="fd35c-175">호스트 Microsoft Edge의 채널 및 버전은 컨테이너 내부에 복제됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-175">The channel and version of the host Microsoft Edge is replicated inside the container.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fd35c-176">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="fd35c-176">Prerequisites</span></span>

<span data-ttu-id="fd35c-177">다음 요구 사항은 Microsoft Edge와 함께 Application Guard를 사용하는 장치에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-177">The following  requirements apply to devices using Application Guard with Microsoft Edge:</span></span>

- <span data-ttu-id="fd35c-178">Windows 10 1809(RS5) 이상.</span><span class="sxs-lookup"><span data-stu-id="fd35c-178">Windows 10 1809 (RS5) and above.</span></span>
- <span data-ttu-id="fd35c-179">Windows 클라이언트 SKU만</span><span class="sxs-lookup"><span data-stu-id="fd35c-179">Only Windows client SKUs</span></span>

  > [!NOTE]
  > <span data-ttu-id="fd35c-180">Application Guard는 Windows 10 Pro 및 Windows 10 Enterprise SKU에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-180">Application Guard is only supported on Windows 10 Pro and Windows 10 Enterprise SKUs.</span></span>

- <span data-ttu-id="fd35c-181">[소프트웨어 요구 사항](/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard#software-requirements)에 설명된 관리 솔루션 중 하나</span><span class="sxs-lookup"><span data-stu-id="fd35c-181">One of the management solutions described in [Software requirements](/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard#software-requirements)</span></span>

## <a name="how-to-install-application-guard"></a><span data-ttu-id="fd35c-182">Application Guard를 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="fd35c-182">How to install Application Guard</span></span>

<span data-ttu-id="fd35c-183">다음 문서는 Microsoft Edge에서 Application Guard를 설치, 구성 및 테스트하는 데 필요한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-183">The following articles provide the information you need to install, configure, and test Application Guard with Microsoft Edge.</span></span>

- [<span data-ttu-id="fd35c-184">시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="fd35c-184">System requirements</span></span>](/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard)
- [<span data-ttu-id="fd35c-185">Microsoft Defender Application Guard</span><span class="sxs-lookup"><span data-stu-id="fd35c-185">Install Microsoft Defender Application Guard</span></span>](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard)
- [<span data-ttu-id="fd35c-186">Microsoft Defender 그룹 정책 설정 구성</span><span class="sxs-lookup"><span data-stu-id="fd35c-186">Configure Microsoft Defender group policy settings</span></span>](/windows/security/threat-protection/microsoft-defender-application-guard/configure-md-app-guard)
- [<span data-ttu-id="fd35c-187">Application Guard 테스트</span><span class="sxs-lookup"><span data-stu-id="fd35c-187">Test Application Guard</span></span>](/windows/security/threat-protection/microsoft-defender-application-guard/test-scenarios-md-app-guard)

## <a name="frequently-asked-questions"></a><span data-ttu-id="fd35c-188">자주 묻는 질문</span><span class="sxs-lookup"><span data-stu-id="fd35c-188">Frequently Asked Questions</span></span>

### <a name="does-application-guard-work-in-ie-mode"></a><span data-ttu-id="fd35c-189">Application Guard가 IE 모드에서 작동하나요?</span><span class="sxs-lookup"><span data-stu-id="fd35c-189">Does Application Guard work in IE mode?</span></span>

<span data-ttu-id="fd35c-190">IE 모드는 Application Guard 기능을 지원하지만 IE 모드에서는 이 기능을 많이 사용할 것으로 예상되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-190">IE mode supports Application Guard functionality, but we don't anticipate much use of this feature in IE Mode.</span></span> <span data-ttu-id="fd35c-191">IE 모드는 신뢰할 수 있는 내부 사이트 목록에 배포하는 것이 좋습니다. Application Guard는 신뢰할 수 없는 사이트에만 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-191">IE mode is recommended to be deployed for a list of trusted internal sites, and Application Guard is for untrusted sites only.</span></span> <span data-ttu-id="fd35c-192">모든 IE 모드 사이트 또는 IP 주소가 네트워크 격리 정책에 추가되어 Application Guard에서 신뢰할 수 있는 리소스로 간주되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-192">Make sure all the IE mode sites or IP addresses are also added to the Network Isolation policy to be considered as trusted resource by Application Guard.</span></span>

### <a name="do-i-need-to-install-the-application-guard-chrome-extension"></a><span data-ttu-id="fd35c-193">Application Guard Chrome 확장 프로그램을 설치해야 합니까?</span><span class="sxs-lookup"><span data-stu-id="fd35c-193">Do I need to install the Application Guard Chrome extension?</span></span>

<span data-ttu-id="fd35c-194">아니요, Application Guard 기능은 Microsoft Edge에서 기본적으로 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-194">No, the Application Guard feature is natively supported in Microsoft Edge.</span></span> <span data-ttu-id="fd35c-195">사실 Application Guard Chrome 확장 프로그램은 Microsoft Edge에서 지원되는 구성이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="fd35c-195">In fact, the Application Guard Chrome extension isn't a supported configuration in Microsoft Edge.</span></span>

### <a name="are-there-any-other-platform-related-faqs"></a><span data-ttu-id="fd35c-196">다른 플랫폼 관련 FAQ가 있습니까?</span><span class="sxs-lookup"><span data-stu-id="fd35c-196">Are there any other platform related FAQs?</span></span>

<span data-ttu-id="fd35c-197">예.</span><span class="sxs-lookup"><span data-stu-id="fd35c-197">Yes.</span></span> [<span data-ttu-id="fd35c-198">질문과 대답 - Microsoft Defender Application Guard</span><span class="sxs-lookup"><span data-stu-id="fd35c-198">Frequently asked questions - Microsoft Defender Application Guard</span></span>](/windows/security/threat-protection/microsoft-defender-application-guard/faq-md-app-guard) 

## <a name="see-also"></a><span data-ttu-id="fd35c-199">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fd35c-199">See also</span></span>

- [<span data-ttu-id="fd35c-200">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="fd35c-200">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="fd35c-201">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="fd35c-201">Microsoft Defender Advanced Threat Protection</span></span>](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="fd35c-202">비디오: Application Guard를 사용하여 Microsoft Edge 브라우저 격리</span><span class="sxs-lookup"><span data-stu-id="fd35c-202">Video: Microsoft Edge browser isolation using Application Guard</span></span>](https://www.youtube.com/watch?v=zQjaRqNXMqw&t=3s)