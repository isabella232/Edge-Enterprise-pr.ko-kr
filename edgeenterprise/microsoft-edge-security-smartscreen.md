---
title: Microsoft Defender SmartScreen에 대한 Microsoft Edge 지원
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 04/23/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Defender SmartScreen에 대한 Microsoft Edge 지원
ms.openlocfilehash: d27366409d7792784c360cfee10f96ab174aa375
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980774"
---
# <span data-ttu-id="bc70e-103">Microsoft Defender SmartScreen에 대한 Microsoft Edge 지원</span><span class="sxs-lookup"><span data-stu-id="bc70e-103">Microsoft Edge support for Microsoft Defender SmartScreen</span></span>

<span data-ttu-id="bc70e-104">이 문서에서는 Microsoft Defender SmartScreen 사용의 이점에 대해 설명하고 작동 방법을 설명하고 Microsoft Edge 기능을 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-104">This article describes the benefits of using Microsoft Defender SmartScreen, explains how it works, and describes how to configure this Microsoft Edge feature.</span></span>

> [!NOTE]
> <span data-ttu-id="bc70e-105">이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-105">This article applies to Microsoft Edge version 77 or later.</span></span>

<span data-ttu-id="bc70e-106">Microsoft Defender SmartScreen은 웹을 검색하는 동안 Microsoft Edge에서 안전을 유지하기 위해 사용하는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-106">Microsoft Defender SmartScreen is a service that Microsoft Edge uses to keep you safe while you browse the web.</span></span> <span data-ttu-id="bc70e-107">Windows Defender SmartScreen은 피싱 공격에 가담하거나 포커스 공격을 통해 맬웨어의 배포를 시도할 수 있는 웹 사이트에 대해 초기 경고 시스템을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-107">Microsoft Defender SmartScreen provides an early warning system against websites that might engage in phishing attacks or attempt to distribute malware through a focused attack.</span></span>

> [!NOTE]
> <span data-ttu-id="bc70e-108">Windows 10 버전 1703 이전에는 이 기능을 브라우저 내에서 사용할 경우 SmartScreen 필터, 브라우저 외부에서 사용할 경우 Microsoft SmartScreen으로 불렀습니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-108">Before Windows 10, version 1703, this feature was called the SmartScreen filter when used within the browser and Microsoft SmartScreen when used outside of the browser.</span></span>

## <span data-ttu-id="bc70e-109">Microsoft Defender SmartScreen 이점</span><span class="sxs-lookup"><span data-stu-id="bc70e-109">The benefits of Microsoft Defender SmartScreen</span></span>

<span data-ttu-id="bc70e-110">Microsoft Defender SmartScreen은 다음 목록으로 요약되어 있는 몇 가지 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-110">Microsoft Defender SmartScreen provides several benefits, which are summarized in the following list.</span></span> <span data-ttu-id="bc70e-111">해당 이점에 대한 자세한 내용은 [Microsoft Defender SmartScreen 설명서](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-overview#benefits-of-windows-defender-smartscreen)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bc70e-111">These benefits are described in detail in the [Microsoft Defender SmartScreen documentation](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-overview#benefits-of-windows-defender-smartscreen).</span></span> <span data-ttu-id="bc70e-112">이점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-112">The benefits are:</span></span>

- <span data-ttu-id="bc70e-113">피싱 및 맬웨어 방지 지원</span><span class="sxs-lookup"><span data-stu-id="bc70e-113">Anti-phishing and anti-malware support</span></span>
- <span data-ttu-id="bc70e-114">신뢰도 기반 URL 및 앱 보호</span><span class="sxs-lookup"><span data-stu-id="bc70e-114">Reputation-based URL and app protection</span></span>
- <span data-ttu-id="bc70e-115">운영 체제 통합</span><span class="sxs-lookup"><span data-stu-id="bc70e-115">Operating system integration</span></span>
- <span data-ttu-id="bc70e-116">개선된 추론 및 진단 데이터</span><span class="sxs-lookup"><span data-stu-id="bc70e-116">Improved heuristics and diagnostic data</span></span>
- <span data-ttu-id="bc70e-117">그룹 정책 및 Microsoft Intune을 통한 관리</span><span class="sxs-lookup"><span data-stu-id="bc70e-117">Management through Group Policy and Microsoft Intune</span></span>
- <span data-ttu-id="bc70e-118">잠재적으로 원치 않는 응용 프로그램에 연결된 URL 차단</span><span class="sxs-lookup"><span data-stu-id="bc70e-118">Blocking URLs associated with potentially unwanted applications</span></span>

## <span data-ttu-id="bc70e-119">Microsoft Defender SmartScreen 작동 방식의 이해</span><span class="sxs-lookup"><span data-stu-id="bc70e-119">Understand how Microsoft Defender SmartScreen works</span></span>

<span data-ttu-id="bc70e-120">다양한 입력 사항이 Microsoft Defender SmartScreen 경고에 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-120">A number of inputs contribute to Microsoft Defender SmartScreen warnings.</span></span> <span data-ttu-id="bc70e-121">사용자 의견, 데이터 공급자, 지능형 모델을 비롯하여 다양한 출처로부터 데이터를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-121">Data is received from many sources, including user feedback, data providers, and intelligence models.</span></span> <span data-ttu-id="bc70e-122">해당 데이터는 잠재적인 유해 콘텐츠를 식별하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-122">This data is used to help identify potentially malicious content.</span></span> <span data-ttu-id="bc70e-123">Microsoft Defender SmartScreen은 또한 다운로드 앱 또는 앱 설치 관리자가 유해한 요소인지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-123">Microsoft Defender SmartScreen also checks downloaded apps or app installers to see if they're malicious.</span></span> <span data-ttu-id="bc70e-124">두 경우 모두에서 Microsoft Defender SmartScreen은 의심스러운 콘텐츠에 대해 사용자에게 적절히 경고를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-124">In both scenarios, Microsoft Defender SmartScreen warns users appropriately about suspicious content.</span></span>

### <span data-ttu-id="bc70e-125">사이트 분석</span><span class="sxs-lookup"><span data-stu-id="bc70e-125">Site analysis</span></span>

<span data-ttu-id="bc70e-126">Microsoft Defender SmartScreen은 다음을 통해 잠재적인 유해 사이트 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-126">Microsoft Defender SmartScreen determines whether a site is potentially malicious by:</span></span>

- <span data-ttu-id="bc70e-127">방문 웹 페이지를 분석하여 의심스러운 동작으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-127">Analyzing visited webpages for indications of suspicious behavior.</span></span>
- <span data-ttu-id="bc70e-128">방문 사이트를 보고된 피싱 사이트의 동적 레코드와 대조합니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-128">Checking the visited sites against a dynamic record of reported phishing sites.</span></span>

<span data-ttu-id="bc70e-129">Microsoft Defender SmartScreen이 페이지를 유해한 것으로 확인한 경우 해당 사이트가 안전한 것으로 보고 되었음을 사용자에게 알리는 경고 페이지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-129">If Microsoft Defender SmartScreen determines that a page is malicious, it will show a warning page to notify the user that that site is reported as unsafe.</span></span> <span data-ttu-id="bc70e-130">다음 스크린샷은 사용자가 유해 웹 사이트 열 때 표시되는 Microsoft Defender SmartScreen 경고 페이지의 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-130">The next screenshot shows an example of a Microsoft Defender SmartScreen warning page when a user tries to open a malicious website.</span></span>

![외부 사이트의 링크에 대한 Microsoft Defender SmartScreen 블록 페이지](media/microsoft-edge-security-smartscreen/microsoft-edge-smartscreen-warning.png)

<span data-ttu-id="bc70e-132">사용자는 경고 메시지 내에서 사이트를 안전한 것으로 보고 또는 안전하지 않은 것으로 보고하는 옵션을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-132">Users are given the option of reporting a site as safe or unsafe within the warning message.</span></span> <span data-ttu-id="bc70e-133">자세한 내용은 [사이트를 보고하는 방법](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-set-individual-device#how-users-can-report-websites-as-safe-or-unsafe)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bc70e-133">For more information, see [how to report a site](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-set-individual-device#how-users-can-report-websites-as-safe-or-unsafe).</span></span>

### <span data-ttu-id="bc70e-134">파일 분석</span><span class="sxs-lookup"><span data-stu-id="bc70e-134">File analysis</span></span>

<span data-ttu-id="bc70e-135">Microsoft Defender SmartScreen은 다운로드 트래픽, 다운로드 기록, 지난 바이러스 백신 결과 및 URL 신뢰도 등의 다양한 기준으로 다운로드 앱 또는 앱 설치 관리자가 유해한 요소인지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-135">Microsoft Defender SmartScreen determines whether a downloaded app or app installer is potentially malicious based on many criteria, such as download traffic, download history, past anti-virus results, and URL reputation.</span></span>

- <span data-ttu-id="bc70e-136">안전한 신뢰도의 파일은 어떠한 알림 없이 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-136">Files with a known safe reputation will download without any notification.</span></span>  
- <span data-ttu-id="bc70e-137">유해한 신뢰도의 파일은 파일이 안전하지 않고 유해한 것으로 보고되었음을 알리는 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-137">Files with a known malicious reputation show a warning to let the user know that the file is unsafe and has been reported as malicious.</span></span> <span data-ttu-id="bc70e-138">다음 스크린샷은 유해한 파일에 대한 경고 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-138">The next screenshot is an example of a warning for a malicious file.</span></span>

  ![유해한 신뢰도의 파일에 대한 Microsoft Defender SmartScreen 블록 페이지](media/microsoft-edge-security-smartscreen/ms-edge-smartscreen-known-malicious.png)

- <span data-ttu-id="bc70e-140">알 수 없는 파일에는 알려진 발자국 및 경고 알림이 없는 다운로드임을 알리는 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-140">Files that are unknown show a warning to let the user know that the download doesn't have a known footprint and advise caution.</span></span> <span data-ttu-id="bc70e-141">다음 스크린샷은 알 수 없는 파일에 대한 경고 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-141">The next screenshot is an example of a warning for an unknown file.</span></span>

  ![유해한 신뢰도의 파일에 대한 Microsoft Defender SmartScreen 블록 페이지](media/microsoft-edge-security-smartscreen/ms-edge-smartscreen-unknown-malicious.png)

<span data-ttu-id="bc70e-143">알 수 없는 모든 프로그램이 유해한 것은 아닙니다. 알 수 없는 경고는 특히 경고가 예상치 않게 표시된 경우 이를 필요로 하는 사용자를 위한 컨텍스트 및 지침을 제공하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-143">Not all unknown programs are malicious, and the unknown warning is intended to provide context and guidance for users who need it, especially if the warning is unexpected.</span></span>

  ![유해한 신뢰도를 가지는 파일의 유지](media/microsoft-edge-security-smartscreen/ms-edge-smartscreen-unknown-malicious-keep.png)

<span data-ttu-id="bc70e-145">하지만 사용자는 계속 다운로드할 수 있으며 **... | 유지 | 자세히 보기 | 계속 유지**를 클릭하여 응용 프로그램을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-145">However, users can still download and run the application by clicking **... | Keep | Show More | Keep anyway**.</span></span>

> [!TIP]
> **<span data-ttu-id="bc70e-146">엔터프라이즈 고객을 위한 참고</span><span class="sxs-lookup"><span data-stu-id="bc70e-146">FYI for Enterprise Customers.</span></span>** <span data-ttu-id="bc70e-147">Microsoft Defender SmartScreen은 기본적으로 사용자가 경고를 무시할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-147">By default, Microsoft Defender SmartScreen lets users bypass warnings.</span></span> <span data-ttu-id="bc70e-148">해당 사용자 조작은 잠재적으로 위험할 수 있으므로 [권장되는 그룹 정책 설정](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-available-settings#recommended-group-policy-and-mdm-settings-for-your-organization)을 검토하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-148">Because this user interaction is potentially risky, we recommend that you review these [recommended group policy settings](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-available-settings#recommended-group-policy-and-mdm-settings-for-your-organization).</span></span>

<span data-ttu-id="bc70e-149">당사의 [데모 사이트](https://demo.smartscreen.msft.net/)를 사용하여 다양한 시나리오별로 Microsoft Defender SmartScreen의 대응 방법을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-149">You see how Microsoft Defender SmartScreen responds to different scenarios using our [demo site](https://demo.smartscreen.msft.net/).</span></span>

## <span data-ttu-id="bc70e-150">Microsoft Defender SmartScreen 및 사용자 개인 정보 보호</span><span class="sxs-lookup"><span data-stu-id="bc70e-150">Microsoft Defender SmartScreen and user privacy</span></span>

<span data-ttu-id="bc70e-151">Microsoft Defender SmartScreen은 사용자가 신뢰도 검사 시스템을 사용하여 인터넷을 검색하는 동안 사용자를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-151">Microsoft Defender SmartScreen protects users while they browse the Internet by using a reputation check system.</span></span> <span data-ttu-id="bc70e-152">Microsoft Edge에서는 URL 또는 파일에 대한 관련 정보를 Microsoft Defender SmartScreen 서비스에 전달하여 신뢰도 검사를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-152">Microsoft Edge passes relevant information about the URL or file to the Microsoft Defender SmartScreen service to start the reputation check.</span></span> <span data-ttu-id="bc70e-153">검사는 웹 사이트 또는 파일을 유해한 것으로 알려진 사이트 및 파일의 동적 목록과 비교하여 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-153">The check compares the website or file against dynamic lists of sites and files that are known to be dangerous.</span></span> <span data-ttu-id="bc70e-154">Microsoft Defender SmartScreen 서비스에 대한 모든 요청은 TLS 암호화로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-154">All requests to the Microsoft Defender SmartScreen service are made with TLS encryption.</span></span> <span data-ttu-id="bc70e-155">해당 서비스는 신뢰도 검사의 결과를 반환하며 이는 Microsoft Edge로 이어져 해당 사이트 또는 파일에 대해 경고를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-155">The service returns the results of the reputation check, which might lead to Microsoft Edge showing a warning for the site or file.</span></span> <span data-ttu-id="bc70e-156">해당 결과는 장치에 로컬로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-156">These results are stored locally on the device.</span></span>

<span data-ttu-id="bc70e-157">Microsoft Defender SmartScreen 서비스는 신뢰도 검사에 대한 데이터를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-157">The Microsoft Defender SmartScreen service stores data about reputation checks.</span></span> <span data-ttu-id="bc70e-158">새로운 사이트가 식별되면 서비스에서는 알려진 유해 URL 및 파일의 동적 데이터베이스에 해당 사이트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-158">As new sites are identified, the service adds to a dynamic database of known malicious URLs and files.</span></span> <span data-ttu-id="bc70e-159">이 데이터는 보안 Microsoft 서버에 저장되며 Microsoft 보안 서비스에만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-159">This data is stored on secure Microsoft servers and is only used for Microsoft security services.</span></span> <span data-ttu-id="bc70e-160">이 데이터는 어떤 방식으로도 사용자를 식별하거나 대상으로 지정하는 데는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-160">This data will never be used to identify or target users in any way.</span></span> <span data-ttu-id="bc70e-161">검색 캐시를 지우면 로컬로 저장된 Microsoft Defender SmartScreen URL 데이터가 모두 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-161">Clearing browsing cache clears all locally stored Microsoft Defender SmartScreen URL data.</span></span> <span data-ttu-id="bc70e-162">다운로드 기록을 지우면 파일 다운로드에 대한 로컬로 저장된 SmartScreen 데이터가 모두 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-162">Clearing download history will remove any locally stored SmartScreen data about file downloads.</span></span>

<span data-ttu-id="bc70e-163">Microsoft Edge의 Microsoft Defender SmartScreen 및 개인 정보 보호에 대한 자세한 내용은 [Microsoft Edge 개인 정보 보호 백서](https://docs.microsoft.com/microsoft-edge/privacy-whitepaper#smartscreen)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bc70e-163">For more information about Microsoft Defender SmartScreen and privacy on Microsoft Edge, read the [Microsoft Edge Privacy Whitepaper](https://docs.microsoft.com/microsoft-edge/privacy-whitepaper#smartscreen).</span></span>

## <span data-ttu-id="bc70e-164">관리자를 위한 Microsoft Defender SmartScreen 설정</span><span class="sxs-lookup"><span data-stu-id="bc70e-164">Microsoft Defender SmartScreen setup for admins</span></span>

<span data-ttu-id="bc70e-165">관리자는 그룹 정책, Microsoft Intune 또는 MDM (모바일 장치 관리) 설정을 사용하여 Microsoft Defender SmartScreen을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-165">Admins can configure Microsoft Defender SmartScreen using Group Policy, Microsoft Intune, or mobile device management (MDM) settings.</span></span> <span data-ttu-id="bc70e-166">Windows Defender SmartScreen을 설정하는 방법에 따라 사용자에게 경고 페이지를 표시하고 해당 사이트를 계속 사용할 수 있도록 설정하거나 사이트를 완전히 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-166">Based on how you set up Microsoft Defender SmartScreen, you can show users a warning page and let them continue to the site or block the site entirely.</span></span>

### <span data-ttu-id="bc70e-167">그룹 정책을 사용하여 Microsoft Defender SmartScreen 설정</span><span class="sxs-lookup"><span data-stu-id="bc70e-167">Microsoft Defender SmartScreen set up using Group Policy</span></span>

<span data-ttu-id="bc70e-168">SmartScreen 정책의 전체 목록은 [Microsoft Defender SmartScreen 설정](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#smartscreen-settings)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bc70e-168">For a complete list of SmartScreen policies, see [Microsoft Defender SmartScreen settings](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#smartscreen-settings)</span></span>

### <span data-ttu-id="bc70e-169">MDM을 사용하여 Microsoft Defender SmartScreen 설정</span><span class="sxs-lookup"><span data-stu-id="bc70e-169">Microsoft Defender SmartScreen set up using MDM</span></span>

<span data-ttu-id="bc70e-170">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bc70e-170">For more information, see:</span></span>

- [<span data-ttu-id="bc70e-171">Microsoft Defender SmartScreen에 대한 Windows Intune 설정</span><span class="sxs-lookup"><span data-stu-id="bc70e-171">Windows Intune settings for Microsoft Defender SmartScreen</span></span>](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#windows-defender-smartscreen-settings)
- [<span data-ttu-id="bc70e-172">MDM 정책 설정</span><span class="sxs-lookup"><span data-stu-id="bc70e-172">MDM policy settings</span></span>](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#windows-defender-smartscreen-settings)

## <span data-ttu-id="bc70e-173">사용자를 위한 Microsoft Defender SmartScreen 설정</span><span class="sxs-lookup"><span data-stu-id="bc70e-173">Microsoft Defender SmartScreen setup for users</span></span>

<span data-ttu-id="bc70e-174">Microsoft Defender SmartScreen은 기본적으로 Microsoft Edge에 대해 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-174">Microsoft Defender SmartScreen is turned on by default for Microsoft Edge.</span></span> <span data-ttu-id="bc70e-175">Microsoft Defender SmartScreen을 해제하려면 *edge://settings/privacy > 서비스 > Microsoft Defender SmartScreen*으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-175">To turn off Microsoft Defender SmartScreen, go to *edge://settings/privacy > Services > Microsoft Defender SmartScreen*.</span></span> <span data-ttu-id="bc70e-176">해당 설정은 장치의 Microsoft Edge 설치와 연결된 모든 프로필에 대해 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-176">This setting is the same for all profiles associated with the installation of Microsoft Edge on a device.</span></span> <span data-ttu-id="bc70e-177">해당 설정은 장치 간에 동기화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-177">This setting is not synced across devices.</span></span> <span data-ttu-id="bc70e-178">이 설정은 InPrivate 브라우징 및 게스트 모드에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-178">The setting applies to InPrivate browsing and Guest mode.</span></span> <span data-ttu-id="bc70e-179">조직이 설정한 그룹 정책을 통해 장치를 관리하는 경우 해당 구성은 *edge://settings/privacy*에 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-179">If a device is managed with group policies set by an organization, this configuration will be reflected in *edge://settings/privacy*.</span></span>

> [!NOTE]
> <span data-ttu-id="bc70e-180">사용자는 Microsoft Defender SmartScreen을 그룹 정책이나 MDM이 차단하도록 구성하지 않는 한 개별 장치에 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-180">Users can set up Microsoft Defender SmartScreen for an individual device unless Group Policy or MDM is configured to prevent it.</span></span> <span data-ttu-id="bc70e-181">자세한 내용은 [개별 장치에서 Microsoft Defender SmartScreen 설정 및 사용](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-set-individual-device)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bc70e-181">For more information, see [set up and use Microsoft Defender SmartScreen on individual devices](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-set-individual-device).</span></span>

## <span data-ttu-id="bc70e-182">질문과 대답</span><span class="sxs-lookup"><span data-stu-id="bc70e-182">Frequently asked questions</span></span>

### <span data-ttu-id="bc70e-183">신뢰도 검사 시스템은 어떻게 작동하나요?</span><span class="sxs-lookup"><span data-stu-id="bc70e-183">How does the reputation check system work?</span></span>

<span data-ttu-id="bc70e-184">웹을 검색하면 Microsoft Defender SmartScreen이 웹 사이트 및 다운로드를 상위 트래픽, 위험 또는 알 수 없음으로 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-184">As you browse the web, Microsoft Defender SmartScreen categorizes websites and downloads as top traffic, dangerous, or unknown.</span></span> <span data-ttu-id="bc70e-185">상위 트래픽은 Microsoft Defender SmartScreen이 신뢰할 수 있는 것으로 판단한 사용량이 많은 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-185">Top traffic is popular sites that Microsoft Defender SmartScreen has determined are trustworthy.</span></span> <span data-ttu-id="bc70e-186">위험으로 표시된 사이트로 이동하면 Microsoft Defender SmartScreen에서 사용자가 사이트에 액세스하는 것을 즉시 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-186">If you go to a site marked as dangerous, Microsoft Defender SmartScreen immediately blocks you from accessing the site.</span></span> <span data-ttu-id="bc70e-187">알 수 없는 사이트로 이동하면 Microsoft DefenderSmartScreen에서 해당 신뢰도를 확인하여 사이트에 액세스할 수 있는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bc70e-187">When you go to an unknown site, Microsoft DefenderSmartScreen checks its reputation to determine if you should access the site.</span></span>

## <span data-ttu-id="bc70e-188">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bc70e-188">See also</span></span>

- [<span data-ttu-id="bc70e-189">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="bc70e-189">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="bc70e-190">Windows Defender SmartScreen 개요</span><span class="sxs-lookup"><span data-stu-id="bc70e-190">Microsoft Defender SmartScreen Overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-overview)
- [<span data-ttu-id="bc70e-191">위협 방지</span><span class="sxs-lookup"><span data-stu-id="bc70e-191">Threat protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/index)
- [<span data-ttu-id="bc70e-192">잠재적으로 원치 않는 응용 프로그램(PUA)으로부터 보호</span><span class="sxs-lookup"><span data-stu-id="bc70e-192">Protect against potentially unwanted applications</span></span>](https://docs.microsoft.com/DeployEdge/microsoft-edge-potentially-unwanted-apps)