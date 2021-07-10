---
title: 베타 채널 용 Microsoft Edge 릴리스 정보
ms.author: aguta
author: AndreaLBarr
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 베타 채널 용 Microsoft Edge 릴리스 정보
ms.openlocfilehash: 1115c8d7822fef7e3784a465d5d4ddfd7b6bd6b1
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2021
ms.locfileid: "11643164"
---
# <a name="release-notes-for-microsoft-edge-beta-channel"></a><span data-ttu-id="4c1bd-103">Microsoft Edge 베타 채널에 대한 릴리스 정보</span><span class="sxs-lookup"><span data-stu-id="4c1bd-103">Release notes for Microsoft Edge Beta Channel</span></span>

<span data-ttu-id="4c1bd-104">이 릴리스 정보는 Microsoft Edge 베타 채널에 포함된 새로운 기능 및 비보안 업데이트에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-104">These release notes provide information about new features and non-security updates that are included in the Microsoft Edge Beta Channel.</span></span> <span data-ttu-id="4c1bd-105">이 릴리스 정보의 보관된 버전은 [여기](microsoft-edge-relnote-archive-beta-channel.md)에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-105">Archived versions of these release notes are available [here](microsoft-edge-relnote-archive-beta-channel.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4c1bd-106">Microsoft Edge 웹 플랫폼은 사용자 환경, 보안 및 개인 정보 개선을 위해 지속적으로 진화하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-106">Microsoft Edge Web Platform constantly evolves to improve user experience, security, and privacy.</span></span> <span data-ttu-id="4c1bd-107">자세히 알아보려면 [사이트 호환성-Microsoft Edge로 들어오는 변화에 영향](/microsoft-edge/web-platform/site-impacting-changes)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-107">To learn more, see [Site compatibility-impacting changes coming to Microsoft Edge](/microsoft-edge/web-platform/site-impacting-changes).</span></span>

## <a name="version-92090222-june-21"></a><span data-ttu-id="4c1bd-108">버전 92.0.902.22: 6월 21일</span><span class="sxs-lookup"><span data-stu-id="4c1bd-108">Version 92.0.902.22: June 21</span></span>

### <a name="feature-updates"></a><span data-ttu-id="4c1bd-109">기능 업데이트</span><span class="sxs-lookup"><span data-stu-id="4c1bd-109">Feature updates</span></span>

- <span data-ttu-id="4c1bd-110">**사용자는 Microsoft Edge에서 Internet Explorer 모드로 쉽게 이동할 수 있습니다**.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-110">**Users can easily get to Internet Explorer mode on Microsoft Edge**.</span></span> <span data-ttu-id="4c1bd-111">Microsoft Edge 버전 92부터 사용자는 엔터프라이즈 모드 사이트 목록에서 사이트가 구성될 때까지 기다리는 동안 독립 실행형 IE 11 응용 프로그램을 사용하는 대신 Microsoft Edge Internet Explorer 모드로 사이트를 다시 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-111">Starting with Microsoft Edge version 92, users can reload a site in Internet Explorer mode on Microsoft Edge instead of relying on the standalone IE 11 application while waiting for a site to be configured in the Enterprise Mode Site List.</span></span> <span data-ttu-id="4c1bd-112">사용자에게 사이트를 로컬 사이트 목록에 추가하라는 메시지가 표시되므로 Microsoft Edge에서 같은 페이지로 이동하면 다음 30일 동안 IE 모드로 자동으로 렌더링됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-112">Users will be prompted to add the site to their local site list such that navigating to the same page in Microsoft Edge will automatically render in IE mode for the next 30 days.</span></span> <span data-ttu-id="4c1bd-113">*[InternetExplorerIntegrationReloadInIEModeAllowed](/deployedge/microsoft-edge-policies#internetexplorerintegrationreloadiniemodeallowed)* 정책을 사용하여 이 환경을 구성하고 IE 모드 진입점에 대한 액세스와 로컬 사이트 목록에 사이트를 추가하는 기능을 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-113">You can use the *[InternetExplorerIntegrationReloadInIEModeAllowed](/deployedge/microsoft-edge-policies#internetexplorerintegrationreloadiniemodeallowed)* policy to configure this experience and allow access to the IE mode entry points as well as the ability to add sites to the local site list.</span></span> <span data-ttu-id="4c1bd-114">*[InternetExplorerIntegrationLocalSiteListExpirationDays](/deployedge/microsoft-edge-policies#internetexplorerintegrationlocalsitelistexpirationdays)* 정책을 사용하여 사이트를 로컬 사이트 목록에 유지할 일수를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-114">You can use the *[InternetExplorerIntegrationLocalSiteListExpirationDays](/deployedge/microsoft-edge-policies#internetexplorerintegrationlocalsitelistexpirationdays)* policy to adjust the number of days to keep sites on the local site list.</span></span>
<span data-ttu-id="4c1bd-115">Windows 10 버전 1909;에는 KB5003698 이상이 필요합니다. Windows 10, 버전 2004, Windows 10, 버전 20H2 또는 Windows 10 버전 21H1에 종단 간 환경을 사용하려면 KB5003690 이상이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-115">Note that KB5003698 or later is required for Windows 10, version 1909; or KB5003690 or later is required for Windows 10, version 2004, Windows 10, version 20H2, or Windows 10, version 21H1 for the end-to-end experience.</span></span>

- <span data-ttu-id="4c1bd-116">**MHTML 파일은 기본적으로 Internet Explorer 모드에서 열립니다**.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-116">**MHTML files will default to opening in Internet Explorer mode**.</span></span> <span data-ttu-id="4c1bd-117">Microsoft Edge 버전 92 Stable부터 MHTML 파일 형식은 Internet Explorer(IE11) 애플리케이션 대신 Microsoft Edge Internet Explorer 모드로 자동으로 열립니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-117">Starting in Microsoft Edge version 92 Stable, MHTML file types will automatically open in Internet Explorer mode on Microsoft Edge instead of the Internet Explorer (IE11) application.</span></span> <span data-ttu-id="4c1bd-118">브라우저에서 Outlook 전자 메일을 보는 동안 가장 일반적으로 관찰됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-118">This is most commonly observed while trying to view Outlook emails in a browser.</span></span> <span data-ttu-id="4c1bd-119">이 변경은 IE11이 이 파일 형식의 기본 처리기인 경우에만 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-119">This change will occur only if IE11 is the default handler for this file type.</span></span> <span data-ttu-id="4c1bd-120">이를 변경하려면 [이 지침](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration)을 사용하여 Stable 버전 92 업데이트를 설치하기 전에 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-120">If you'd prefer to change this, you can do so prior to installing the Stable version 92 update using [this guidance](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration).</span></span>

- <span data-ttu-id="4c1bd-121">**결제 방법이 이제 장치 간에 동기화됩니다**.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-121">**Payment instruments are now synced across devices**.</span></span> <span data-ttu-id="4c1bd-122">Microsoft Edge 버전 92부터 로그인한 장치에서 결제 정보를 동기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-122">Beginning with Microsoft Edge version 92, you have the option to synchronize your payment information across your signed in devices.</span></span>
<span data-ttu-id="4c1bd-123">참고: 이 항목은 제어된 기능 롤아웃이며 현재 진행률은 50%입니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-123">Please note: this is a Controlled Feature Rollout and we are currently at 50%.</span></span> <span data-ttu-id="4c1bd-124">이 기능이 표시되지 않으면 계속 롤아웃하므로 잠시 후에 다시 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-124">If you don’t see this feature, please check back shortly as we continue our rollout.</span></span>

- <span data-ttu-id="4c1bd-125">**“개발자 모드 확장을 사용 안 함으로 설정하세요” 경고를 영구적으로 해제할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="4c1bd-125">**"Disable developer mode extensions" warning can be permanently dismissed**.</span></span> <span data-ttu-id="4c1bd-126">Microsoft Edge 버전 92부터 '다시 표시 안 함' 옵션을 클릭하여 "개발자 모드 확장을 사용 안 함으로 설정하세요" 경고를 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-126">Beginning with Microsoft Edge version 92, you can turn off the warning "Disable developer mode extensions" by clicking on the 'Don't show this again' option.</span></span>
<span data-ttu-id="4c1bd-127">참고: 이 항목은 제어된 기능 롤아웃이며 현재 진행률은 25%입니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-127">Please note: this is a Controlled Feature Rollout and we are currently at 25%.</span></span> <span data-ttu-id="4c1bd-128">이 기능이 표시되지 않으면 계속 롤아웃하므로 잠시 후에 다시 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-128">If you don’t see this feature, please check back shortly as we continue our rollout.</span></span>

- <span data-ttu-id="4c1bd-129">**도구 모음에서 바로 확장을 관리하세요.**</span><span class="sxs-lookup"><span data-stu-id="4c1bd-129">**Manage your extensions right from the toolbar**.</span></span> <span data-ttu-id="4c1bd-130">도구 모음의 새 확장 메뉴를 사용해서 확장을 쉽게 숨기거나 핀으로 고정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-130">The all-new extensions menu on the toolbar will allow you to hide/pin extensions easily.</span></span> <span data-ttu-id="4c1bd-131">확장을 관리하고 새 확장을 찾기 위한 빠른 링크를 사용하면 간편하게 새 확장을 찾고 기존 확장을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-131">The quick links to manage extensions and find new extensions will make it easy for you to find new extensions and manage your existing ones.</span></span>
<span data-ttu-id="4c1bd-132">참고: 이 항목은 제어된 기능 롤아웃이며 현재 진행률은 25%입니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-132">Please note: this is a Controlled Feature Rollout and we are currently at 25%.</span></span> <span data-ttu-id="4c1bd-133">이 기능이 표시되지 않으면 계속 롤아웃하므로 잠시 후에 다시 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-133">If you don’t see this feature, please check back shortly as we continue our rollout.</span></span>

- <span data-ttu-id="4c1bd-134">**자동 HTTPS**.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-134">**Automatic HTTPS**.</span></span> <span data-ttu-id="4c1bd-135">사용자는 이 보안 프로토콜을 지원할 가능성이 높은 도메인의 HTTP에서 HTTPS로 탐색을 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-135">Users will have the option to upgrade navigation from HTTP to HTTPS on domains likely to support this more secure protocol.</span></span> <span data-ttu-id="4c1bd-136">이 지원은 모든 도메인에 대해 HTTPS를 통해 전달을 시도하도록 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-136">This support can also be configured to attempt delivery over HTTPS for all domains.</span></span>
<span data-ttu-id="4c1bd-137">참고: 이 기능을 실험하는 중이며 실험을 옵트아웃한 경우에는 이 동작이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-137">Please note: we are experimenting with this feature and this behavior won’t be seen if you have opted out of experiments.</span></span>

- <span data-ttu-id="4c1bd-138">**글꼴 렌더링 개선**.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-138">**Improvements to font rendering**.</span></span> <span data-ttu-id="4c1bd-139">텍스트 렌더링이 개선되어 선명도를 개선하고 흐릿함을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-139">Improvements have been made to the rendering of text to improve clarity and reduce blurriness.</span></span>
<span data-ttu-id="4c1bd-140">참고: 이 항목은 제어된 기능 롤아웃이며 현재 진행률은 25%입니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-140">Please note: this is a Controlled Feature Rollout and we are currently at 25%.</span></span> <span data-ttu-id="4c1bd-141">이 기능이 표시되지 않으면 계속 롤아웃하므로 잠시 후에 다시 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-141">If you don’t see this feature, please check back shortly as we continue our rollout.</span></span>

### <a name="policy-updates"></a><span data-ttu-id="4c1bd-142">정책 업데이트</span><span class="sxs-lookup"><span data-stu-id="4c1bd-142">Policy updates</span></span>

#### <a name="new-policies"></a><span data-ttu-id="4c1bd-143">새 정책</span><span class="sxs-lookup"><span data-stu-id="4c1bd-143">New policies</span></span>

<span data-ttu-id="4c1bd-144">새 정책 8개를 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-144">Eight new policies were added.</span></span> <span data-ttu-id="4c1bd-145">[Microsoft Edge Enterprise 방문 페이지](https://www.microsoft.com/edge/business/download)에서 업데이트된 관리 템플릿을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-145">Download the updated Administrative Templates from the [Microsoft Edge Enterprise landing page](https://www.microsoft.com/edge/business/download).</span></span> <span data-ttu-id="4c1bd-146">다음과 같은 새 정책이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-146">The following new policies were added:</span></span>

- <span data-ttu-id="4c1bd-147">[AADWebSiteSSOUsingThisProfileEnabled](/DeployEdge/microsoft-edge-policies#aadwebsitessousingthisprofileenabled) 이 프로필을 사용하도록 설정된 회사 또는 학교 사이트에 대한 Single Sign-On을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-147">[AADWebSiteSSOUsingThisProfileEnabled](/DeployEdge/microsoft-edge-policies#aadwebsitessousingthisprofileenabled) Single sign-on for work or school sites using this profile enabled.</span></span>
- <span data-ttu-id="4c1bd-148">[AutomaticHttpsDefault](/DeployEdge/microsoft-edge-policies#automatichttpsdefault) 자동 HTTPS 구성</span><span class="sxs-lookup"><span data-stu-id="4c1bd-148">[AutomaticHttpsDefault](/DeployEdge/microsoft-edge-policies#automatichttpsdefault) Configure Automatic HTTPS</span></span>
- <span data-ttu-id="4c1bd-149">[HeadlessModeEnabled](/DeployEdge/microsoft-edge-policies#headlessmodeenabled) 비입력 시스템 모드 사용 제어</span><span class="sxs-lookup"><span data-stu-id="4c1bd-149">[HeadlessModeEnabled](/DeployEdge/microsoft-edge-policies#headlessmodeenabled) Control use of the Headless Mode</span></span>
- <span data-ttu-id="4c1bd-150">[InsecurePrivateNetworkRequestsAllowed](/DeployEdge/microsoft-edge-policies#insecureprivatenetworkrequestsallowed) 안전하지 않은 웹사이트가 더 많은 개인 네트워크 엔드포인트에 요청을 할 수 있도록 허용할지 여부를 지정</span><span class="sxs-lookup"><span data-stu-id="4c1bd-150">[InsecurePrivateNetworkRequestsAllowed](/DeployEdge/microsoft-edge-policies#insecureprivatenetworkrequestsallowed)Specifies whether to allow insecure websites to make requests to more-private network endpoints</span></span>
- <span data-ttu-id="4c1bd-151">[InsecurePrivateNetworkRequestsAllowedForUrls](/DeployEdge/microsoft-edge-policies#insecureprivatenetworkrequestsallowedforurls) 나열된 사이트가 안전하지 않은 컨텍스트에서 더 많은 개인 네트워크 엔드포인트에 요청을 할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="4c1bd-151">[InsecurePrivateNetworkRequestsAllowedForUrls](/DeployEdge/microsoft-edge-policies#insecureprivatenetworkrequestsallowedforurls) Allow the listed sites to make requests to more-private network endpoints from insecure contexts</span></span>
- <span data-ttu-id="4c1bd-152">[InternetExplorerIntegrationLocalSiteListExpirationDays](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationlocalsitelistexpirationdays) 사이트가 로컬 IE 모드 사이트 목록에 남아 있는 일수 지정</span><span class="sxs-lookup"><span data-stu-id="4c1bd-152">[InternetExplorerIntegrationLocalSiteListExpirationDays](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationlocalsitelistexpirationdays) Specify the number of days that a site remains on the local IE mode site list</span></span>
- <span data-ttu-id="4c1bd-153">[InternetExplorerIntegrationReloadInIEModeAllowed](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationreloadiniemodeallowed) Internet Explorer 모드에서 구성되지 않은 사이트를 다시 로드할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="4c1bd-153">[InternetExplorerIntegrationReloadInIEModeAllowed](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationreloadiniemodeallowed) Allow unconfigured sites to be reloaded in Internet Explorer mode</span></span>
- <span data-ttu-id="4c1bd-154">[SharedArrayBufferUnrestrictedAccessAllowed](/DeployEdge/microsoft-edge-policies#sharedarraybufferunrestrictedaccessallowed) cross-origin-isolated가 아닌 컨텍스트에서 SharedArrayBuffers를 사용할 수 있는지 여부 지정</span><span class="sxs-lookup"><span data-stu-id="4c1bd-154">[SharedArrayBufferUnrestrictedAccessAllowed](/DeployEdge/microsoft-edge-policies#sharedarraybufferunrestrictedaccessallowed) Specifies whether SharedArrayBuffers can be used in a non cross-origin-isolated context</span></span>

#### <a name="obsoleted-policy"></a><span data-ttu-id="4c1bd-155">폐기된 정책</span><span class="sxs-lookup"><span data-stu-id="4c1bd-155">Obsoleted Policy</span></span>

- <span data-ttu-id="4c1bd-156">[EnableSha1ForLocalAchors](/DeployEdge/microsoft-edge-policies#enablesha1forlocalanchors) 로컬 트러스트 앵커에서 발급한 경우 SHA-1을 사용하여 서명한 인증서 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-156">[EnableSha1ForLocalAnchors](/DeployEdge/microsoft-edge-policies#enablesha1forlocalanchors) Allow certificates signed using SHA-1 when issued by local trust anchors.</span></span>


## <a name="version-9209029-june-8"></a><span data-ttu-id="4c1bd-157">버전 92.0.902.9: 6월 8일</span><span class="sxs-lookup"><span data-stu-id="4c1bd-157">Version 92.0.902.9: June 8</span></span>

<span data-ttu-id="4c1bd-158">다양한 버그와 성능 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-158">Fixed various bugs and performance issues.</span></span>

## <a name="version-91086441-june-3"></a><span data-ttu-id="4c1bd-159">버전 91.0.864.41: 6월 3일</span><span class="sxs-lookup"><span data-stu-id="4c1bd-159">Version 91.0.864.41: June 3</span></span>

<span data-ttu-id="4c1bd-160">다양한 버그와 성능 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-160">Fixed various bugs and performance issues.</span></span>

## <a name="version-91086437-may-27"></a><span data-ttu-id="4c1bd-161">버전 91.0.864.37: 5월 27일</span><span class="sxs-lookup"><span data-stu-id="4c1bd-161">Version 91.0.864.37: May 27</span></span>

<span data-ttu-id="4c1bd-162">다양한 버그와 성능 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-162">Fixed various bugs and performance issues.</span></span>

## <a name="version-91086436-may-26"></a><span data-ttu-id="4c1bd-163">버전 91.0.864.36: 5월 26일</span><span class="sxs-lookup"><span data-stu-id="4c1bd-163">Version 91.0.864.36: May 26</span></span>

<span data-ttu-id="4c1bd-164">다양한 버그와 성능 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-164">Fixed various bugs and performance issues.</span></span>

## <a name="version-91086433-may-21"></a><span data-ttu-id="4c1bd-165">버전 91.0.864.33: 5월 21일</span><span class="sxs-lookup"><span data-stu-id="4c1bd-165">Version 91.0.864.33: May 21</span></span>

<span data-ttu-id="4c1bd-166">다양한 버그와 성능 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-166">Fixed various bugs and performance issues.</span></span>

## <a name="version-91086427-may-14"></a><span data-ttu-id="4c1bd-167">버전 91.0.864.27: 5월 14일</span><span class="sxs-lookup"><span data-stu-id="4c1bd-167">Version 91.0.864.27: May 14</span></span>

<span data-ttu-id="4c1bd-168">다양한 버그와 성능 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-168">Fixed various bugs and performance issues.</span></span>

## <a name="version-91086419-may-7"></a><span data-ttu-id="4c1bd-169">버전 91.0.864.19: 5월 7일</span><span class="sxs-lookup"><span data-stu-id="4c1bd-169">Version 91.0.864.19: May 7</span></span>

<span data-ttu-id="4c1bd-170">다양한 버그와 성능 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-170">Fixed various bugs and performance issues.</span></span>

## <a name="version-91086415-may-3"></a><span data-ttu-id="4c1bd-171">버전 91.0.864.15: 5월 3일</span><span class="sxs-lookup"><span data-stu-id="4c1bd-171">Version 91.0.864.15: May 3</span></span>

<span data-ttu-id="4c1bd-172">다양한 버그와 성능 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-172">Fixed various bugs and performance issues.</span></span>

## <a name="version-91086411-april-30"></a><span data-ttu-id="4c1bd-173">버전 91.0.864.11: 4월 30일</span><span class="sxs-lookup"><span data-stu-id="4c1bd-173">Version 91.0.864.11: April 30</span></span>

### <a name="feature-updates"></a><span data-ttu-id="4c1bd-174">기능 업데이트</span><span class="sxs-lookup"><span data-stu-id="4c1bd-174">Feature updates</span></span>

- <span data-ttu-id="4c1bd-175">**프록시 수준의 Microsoft Defender Application Guard 컨테이너에서 발생하는 네트워크 트래픽을 식별합니다.**</span><span class="sxs-lookup"><span data-stu-id="4c1bd-175">**Identify network traffic originating from Microsoft Defender Application Guard containers at the proxy level**.</span></span> <span data-ttu-id="4c1bd-176">Microsoft Edge 버전 91부터는 Application Guard 컨테이너에서 발생하는 네트워크 트래픽에 태그를 지정하는 지원이 기본적으로 제공되어 기업에서 해당 트래픽을 식별하고 특정 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-176">Starting with Microsoft Edge version 91, there’s built in support to tag network traffic originating from Application Guard containers, allowing enterprises to identify them and apply specific policies.</span></span>

- <span data-ttu-id="4c1bd-177">**호스트에서 Edge Application Guard 컨테이너의 즐겨찾기 동기화를 허용하는 지원 옵션입니다.**</span><span class="sxs-lookup"><span data-stu-id="4c1bd-177">**Support option to allow synchronizing Favorites from the host to the Edge Application Guard container**.</span></span> <span data-ttu-id="4c1bd-178">Microsoft Edge 버전 91부터 사용자는 호스트에서 컨테이너로 즐겨찾기를 동기화하도록 Application Guard를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-178">Starting with Microsoft Edge version 91, users have the option to configure Application Guard to synchronize their favorites from the host to the container.</span></span> <span data-ttu-id="4c1bd-179">이렇게 하면 새 즐겨찾기도 컨테이너에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-179">This ensures new favorites appear on the container as well.</span></span>

- <span data-ttu-id="4c1bd-180">**음성 인식 API에 대한 지원**</span><span class="sxs-lookup"><span data-stu-id="4c1bd-180">**Support for Speech Recognition APIs**.</span></span> <span data-ttu-id="4c1bd-181">Microsoft Edge 버전 91부터 Google.com 및 유사한 사이트에서 음성 인식 명령에 대한 API 지원이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-181">Starting with Microsoft Edge version 91, API support for speech recognition commands on Google.com and similar sites will be added.</span></span> <span data-ttu-id="4c1bd-182">이 기능은 실험을 허락한 임의로 선택된 사용자 그룹으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-182">This feature is limited to a randomly selected group of users who have enabled experimentation.</span></span> <span data-ttu-id="4c1bd-183">이러한 사용자는 기능 팀에 피드백을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-183">These users are giving feedback to the feature team.</span></span>

- <span data-ttu-id="4c1bd-184">**새 테마 색으로 브라우저를 개인 설정하세요**.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-184">**Personalize your browser with new theme colors**.</span></span> <span data-ttu-id="4c1bd-185">설정 -> 모양 페이지에서 14가지 새로운 테마 색 중 하나를 사용하여 나만의 Microsoft Edge를 만드세요.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-185">Make Microsoft Edge your own with one of the fourteen new theme colors on the Settings -> Appearance page.</span></span> <span data-ttu-id="4c1bd-186">Microsoft Edge 추가 기능 사이트에서 사용자 지정 테마를 설치할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-186">You can also install custom themes from the Microsoft Edge Add-on site.</span></span> [<span data-ttu-id="4c1bd-187">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="4c1bd-187">Learn more</span></span>](https://techcommunity.microsoft.com/t5/articles/make-microsoft-edge-your-own-with-themes/m-p/2083165)

- <span data-ttu-id="4c1bd-188">**다운로드 중단** Microsoft Edge 버전 91부터 브라우저는 사용자 상호 작용 없이 다운로드가 시작되고 SmartScreen 응용 프로그램 신뢰도 검사가 지원되지 않는 경우 컴퓨터를 손상시킬 수 있는 유형의 다운로드를 자동으로 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-188">**Interrupt Downloads** Starting with Microsoft Edge version 91 the browser will automatically interrupt downloads of types which could harm your computer if those downloads are started without a user interaction and are not supported by SmartScreen Application Reputation check.</span></span> <span data-ttu-id="4c1bd-189">사용자는 다운로드 항목을 마우스 오른쪽 단추로 클릭하고 "유지"를 선택하여 재정의하고 계속 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-189">Users may override and continue to download by right clicking and choosing “Keep” on the download item.</span></span>
<span data-ttu-id="4c1bd-190">엔터프라이즈 관리자는 다음 두 정책 중 하나로 이 동작을 옵트아웃할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-190">Enterprise administrators may opt out of this behavior one of these two policies:</span></span>
    - <span data-ttu-id="4c1bd-191">[ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](/deployedge/microsoft-edge-policies#exemptdomainfiletypepairsfromfiletypedownloadwarnings) - 도메인에서 지정된 파일 형식에 대해 파일 형식 확장명 기반 주의 다운로드를 사용설정 해제합니다. 자세한 정보는 [Microsoft Edge 보안 다운로드 중단](/deployedge/microsoft-edge-security-downloads-interruptions)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-191">[ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](/deployedge/microsoft-edge-policies#exemptdomainfiletypepairsfromfiletypedownloadwarnings) - Disable download file type extension-based warnings for specified file types on domains For more information, see [Microsoft Edge Security downloads interruptions](/deployedge/microsoft-edge-security-downloads-interruptions)</span></span>

### <a name="policy-updates"></a><span data-ttu-id="4c1bd-192">정책 업데이트</span><span class="sxs-lookup"><span data-stu-id="4c1bd-192">Policy updates</span></span>

#### <a name="new-policies"></a><span data-ttu-id="4c1bd-193">새 정책</span><span class="sxs-lookup"><span data-stu-id="4c1bd-193">New policies</span></span>

<span data-ttu-id="4c1bd-194">6개의 새 정책을 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-194">Six new policies were added.</span></span> <span data-ttu-id="4c1bd-195">[Microsoft Edge Enterprise 방문 페이지](https://www.microsoft.com/edge/business/download)에서 업데이트된 관리 템플릿을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-195">Download the updated Administrative Templates from the [Microsoft Edge Enterprise landing page](https://www.microsoft.com/edge/business/download).</span></span> <span data-ttu-id="4c1bd-196">다음과 같은 새 정책이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-196">The following new policies were added:</span></span>

- <span data-ttu-id="4c1bd-197">[applicationGuardTrafficIdentificationEnabled](/DeployEdge/microsoft-edge-policies#applicationguardtrafficidentificationenabled) - Application Guard 트래픽 식별</span><span class="sxs-lookup"><span data-stu-id="4c1bd-197">[ApplicationGuardTrafficIdentificationEnabled](/DeployEdge/microsoft-edge-policies#applicationguardtrafficidentificationenabled) - Application Guard Traffic Identification</span></span>
- <span data-ttu-id="4c1bd-198">[ExplicitlyAllowedNetworkPorts](/DeployEdge/microsoft-edge-policies#explicitlyallowednetworkports) - 명시적으로 허용된 네트워크 포트</span><span class="sxs-lookup"><span data-stu-id="4c1bd-198">[ExplicitlyAllowedNetworkPorts](/DeployEdge/microsoft-edge-policies#explicitlyallowednetworkports) - Explicitly allowed network ports</span></span>
- <span data-ttu-id="4c1bd-199">[ImportStartupPageSettings](/DeployEdge/microsoft-edge-policies#importstartuppagesettings) - 시작 페이지 설정 가져오기 허용</span><span class="sxs-lookup"><span data-stu-id="4c1bd-199">[ImportStartupPageSettings](/DeployEdge/microsoft-edge-policies#importstartuppagesettings) - Allow importing of startup page settings</span></span>
- <span data-ttu-id="4c1bd-200">[MathSolverEnabled](/DeployEdge/microsoft-edge-policies#mathsolverenabled) - 사용자가 수학 문제를 캡쳐하고 Microsoft Edge에서 단계별 설명을 통해 해결책을 얻을 수 있도록 함</span><span class="sxs-lookup"><span data-stu-id="4c1bd-200">[MathSolverEnabled](/DeployEdge/microsoft-edge-policies#mathsolverenabled) - Let users snip a Math problem and get the solution with a step-by-step explanation in Microsoft Edge</span></span>
- <span data-ttu-id="4c1bd-201">[NewTabPageContentEnabled](/DeployEdge/microsoft-edge-policies#newtabpagecontentenabled) - 새 탭 페이지에서 Microsoft News 콘텐츠 허용</span><span class="sxs-lookup"><span data-stu-id="4c1bd-201">[NewTabPageContentEnabled](/DeployEdge/microsoft-edge-policies#newtabpagecontentenabled) - Allow Microsoft News content on the new tab page</span></span>
- <span data-ttu-id="4c1bd-202">[NewTabPageQuickLinksEnabled](/DeployEdge/microsoft-edge-policies#newtabpagequicklinksenabled) - 새 탭 페이지에서 빠른 링크 허용</span><span class="sxs-lookup"><span data-stu-id="4c1bd-202">[NewTabPageQuickLinksEnabled](/DeployEdge/microsoft-edge-policies#newtabpagequicklinksenabled) - Allow quick links on the new tab page</span></span>

#### <a name="obsoleted-policy"></a><span data-ttu-id="4c1bd-203">폐기된 정책</span><span class="sxs-lookup"><span data-stu-id="4c1bd-203">Obsoleted Policy</span></span>

- <span data-ttu-id="4c1bd-204">[ProactiveAuthEnabled](./microsoft-edge-policies.md#proactiveauthenabled) - 사전 인증을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-204">[ProactiveAuthEnabled](./microsoft-edge-policies.md#proactiveauthenabled) - Enable Proactive Authentication</span></span>
<!-- end major 91 -->

## <a name="version-90081846-april-22"></a><span data-ttu-id="4c1bd-205">버전 90.0.818.46: 4월 22일</span><span class="sxs-lookup"><span data-stu-id="4c1bd-205">Version 90.0.818.46: April 22</span></span>

<span data-ttu-id="4c1bd-206">다양한 버그와 성능 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-206">Fixed various bugs and performance issues.</span></span>

## <a name="version-90081842-april-20"></a><span data-ttu-id="4c1bd-207">버전 90.0.818.42: 4월 20일</span><span class="sxs-lookup"><span data-stu-id="4c1bd-207">Version 90.0.818.42: April 20</span></span>

<span data-ttu-id="4c1bd-208">다양한 버그와 성능 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-208">Fixed various bugs and performance issues.</span></span>

## <a name="version-90081841-april-16"></a><span data-ttu-id="4c1bd-209">버전 90.0.818.41: 4월 16일</span><span class="sxs-lookup"><span data-stu-id="4c1bd-209">Version 90.0.818.41: April 16</span></span>

<span data-ttu-id="4c1bd-210">다양한 버그와 성능 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-210">Fixed various bugs and performance issues.</span></span>

## <a name="version-90081838-april-14"></a><span data-ttu-id="4c1bd-211">버전 90.0.818.38: 4월 14일</span><span class="sxs-lookup"><span data-stu-id="4c1bd-211">Version 90.0.818.38: April 14</span></span>

<span data-ttu-id="4c1bd-212">다양한 버그와 성능 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-212">Fixed various bugs and performance issues.</span></span>

## <a name="version-90081836-april-12"></a><span data-ttu-id="4c1bd-213">버전 90.0.818.36: 4월 12일</span><span class="sxs-lookup"><span data-stu-id="4c1bd-213">Version 90.0.818.36: April 12</span></span>

<span data-ttu-id="4c1bd-214">다양한 버그와 성능 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-214">Fixed various bugs and performance issues.</span></span>

## <a name="version-90081827-april-2"></a><span data-ttu-id="4c1bd-215">버전 90.0.818.27: 4월 2일</span><span class="sxs-lookup"><span data-stu-id="4c1bd-215">Version 90.0.818.27: April 2</span></span>

<span data-ttu-id="4c1bd-216">다양한 버그와 성능 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-216">Fixed various bugs and performance issues.</span></span>

## <a name="version-90081822-march-29"></a><span data-ttu-id="4c1bd-217">버전 90.0.818.22: 3월 29일</span><span class="sxs-lookup"><span data-stu-id="4c1bd-217">Version 90.0.818.22: March 29</span></span>

<span data-ttu-id="4c1bd-218">다양한 버그와 성능 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-218">Fixed various bugs and performance issues.</span></span>

## <a name="version-90081814-march-22"></a><span data-ttu-id="4c1bd-219">버전 90.0.818.14: 3월 22일</span><span class="sxs-lookup"><span data-stu-id="4c1bd-219">Version 90.0.818.14: March 22</span></span>

<span data-ttu-id="4c1bd-220">다양한 버그와 성능 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-220">Fixed various bugs and performance issues.</span></span>
<!-- begin major 90 -->
## <a name="version-9008188-march-16"></a><span data-ttu-id="4c1bd-221">버전 90.0.818.8: 3월 16일</span><span class="sxs-lookup"><span data-stu-id="4c1bd-221">Version 90.0.818.8: March 16</span></span>

### <a name="feature-updates"></a><span data-ttu-id="4c1bd-222">기능 업데이트</span><span class="sxs-lookup"><span data-stu-id="4c1bd-222">Feature updates</span></span>

- <span data-ttu-id="4c1bd-223">**이제 macOS에서 Azure AD(Azure Active Directory) 계정과 Microsoft MSA(Microsoft 계정)에 SSO(Single Sign On)를 사용할 수 있습니다**.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-223">**Single Sign On (SSO) is now available for Azure Active Directory (Azure AD) accounts and Microsoft Account (MSA) on macOS**.</span></span> <span data-ttu-id="4c1bd-224">macOS에서 Microsoft Edge에 로그인한 사용자는 회사 및 Microsoft 계정(예: bing.com, office.com, msn.com, outlook.com)으로 Single Sign-On을 허용하도록 구성된 웹 사이트에 자동으로 로그인됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-224">A user signed in on Microsoft Edge on macOS will now get automatically signed into websites that are configured to allow single sign on with Work and Microsoft accounts (for example, bing.com, office.com, msn.com, and outlook.com).</span></span>

- **<span data-ttu-id="4c1bd-225">키오스크 모드.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-225">Kiosk mode.</span></span>** <span data-ttu-id="4c1bd-226">Microsoft Edge 버전 90부터 구성된 프린터 및 "PDF로 인쇄" 옵션만 허용하도록 UI 인쇄 설정을 잠갔습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-226">Starting with Microsoft Edge version 90, we have locked down the UI print settings to only allow the configured printers and “Print to PDF” options.</span></span> <span data-ttu-id="4c1bd-227">또한 할당된 액세스 단일 앱 키오스크 모드 내에서 향상된 기능을 수행하여 브라우저에서 다른 애플리케이션의 시작을 제한했습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-227">We have also done improvements within the assigned access single app kiosk mode to restrict the launch of other applications from the browser.</span></span> <span data-ttu-id="4c1bd-228">키오스크 모드 기능에 대한 자세한 내용은 [여기](/deployedge/microsoft-edge-configure-kiosk-mode#kiosk-mode-supported-features)를 참보하세요.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-228">For more information about the kiosk mode features please go [here](/deployedge/microsoft-edge-configure-kiosk-mode#kiosk-mode-supported-features).</span></span>

- **<span data-ttu-id="4c1bd-229">인쇄:</span><span class="sxs-lookup"><span data-stu-id="4c1bd-229">Printing:</span></span>**

  - <span data-ttu-id="4c1bd-230">\*\* 포스트스크립트가 아닌 프린터를위한 새로운 인쇄 래스터화 모드 \*\*.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-230">**New print rasterization mode for non-PostScript printers**.</span></span> <span data-ttu-id="4c1bd-231">Microsoft Edge 버전 90부터 관리자는 새 정책을 사용하여 사용자에 대한 인쇄 래스터화 모드를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-231">Starting with Microsoft Edge version 90, Admins can use a new policy to define print rasterization mode for their users.</span></span> <span data-ttu-id="4c1bd-232">이 정책은 Windows에서 포스트스크립트가 아닌 프린터에 대해 Microsoft Edge의 인쇄 방식을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-232">This policy  controls how Microsoft Edge prints to non-PostScript printers on Windows.</span></span>  <span data-ttu-id="4c1bd-233">PostScript가 아닌 프린터에서 인쇄 작업을 올바르게 인쇄하려면 래스터 화해야하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-233">Sometimes print jobs on non-PostScript printers need to be rasterized to print correctly.</span></span> <span data-ttu-id="4c1bd-234">인쇄 옵션은 전체 및 고속입니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-234">The print options are Full and Fast.</span></span>

  - <span data-ttu-id="4c1bd-235">\*\* 인쇄를 위한 추가 페이지 배율 옵션 \*\*.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-235">**Additional page scaling options for printing**.</span></span> <span data-ttu-id="4c1bd-236">이제 사용자는 추가 옵션을 사용하여 웹 페이지 및 PDF 문서를 인쇄하는 동안 스케일링을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-236">Users are now able to customize scaling while printing webpages and PDF documents using additional options.</span></span> <span data-ttu-id="4c1bd-237">"페이지에 맞추기" 옵션을 사용하면 웹 페이지나 문서를 인쇄를 위해 선택한 "용지 크기"에서 사용할 수 있는 공간에 맞출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-237">The "Fit to Page" option ensures that the webpage or document is fit into the space available in the selected "Paper size" for printing.</span></span> <span data-ttu-id="4c1bd-238">"실제 크기" 옵션은 선택한 "용지 크기"에 관계없이 인쇄되는 내용의 크기가 변경되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-238">The "Actual size" option ensures that there are no changes in the size of the contents being printed regardless of the selected "Paper size".</span></span>

- **<span data-ttu-id="4c1bd-239">생산력:</span><span class="sxs-lookup"><span data-stu-id="4c1bd-239">Productivity:</span></span>**

  - <span data-ttu-id="4c1bd-240">\*\* 자동 완성 제안이 클립 보드의 주소 필드 내용을 포함하도록 확장되었습니다 \*\*.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-240">**Autofill suggestions are extended to include address fields content from clipboard**.</span></span> <span data-ttu-id="4c1bd-241">사용자가 프로필/주소란(예: 전화번호, 전자 메일, 우편 번호, 시, 도)을 클릭할 때 자동 채우기 제안을 표시하기 위해 클립보드 콘텐츠를 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-241">Clipboard content is parsed when you click on a profile/address field (for example, phone, email, zip code, city, state, etc.) to show as autofill suggestions.</span></span>

  - <span data-ttu-id="4c1bd-242">\*\* 사용자는 양식이나 필드가 감지되지 않는 경우에도 자동 완성 제안을 검색할 수 있습니다\*\*.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-242">**Users can search for autofill suggestions even if a form or field isn’t detected**.</span></span> <span data-ttu-id="4c1bd-243">오늘날 Microsoft Edge에 정보를 저장한 경우 자동 완성 제안이 자동으로 표시되어 양식을 작성하는 동안 시간을 ​​절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-243">Today if you have your information saved on Microsoft Edge, autofill suggestions pop up automatically and help you save time while filling out forms.</span></span> <span data-ttu-id="4c1bd-244">자동 완성이 양식을 놓친 경우 또는 일반적으로 자동 완성이 없는 양식(예: 임시 양식)에서 데이터를 가져오려는 경우 자동 완성을 사용하여 정보를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-244">In cases where autofill misses a form, or if you want to fetch data in forms that don't typically have autofill (like temporary forms), you can search for your information using autofill.</span></span>

- <span data-ttu-id="4c1bd-245">\*\* 메뉴 모음의 플라이 아웃에서 다운로드에 액세스합니다\*\*.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-245">**Access downloads from a flyout in the menu bar**.</span></span> <span data-ttu-id="4c1bd-246">다운로드는 모든 활성 다운로드가 한곳에 있는 오른쪽 상단 모서리에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-246">Downloads will appear in the top-right corner with all the active downloads in one place.</span></span> <span data-ttu-id="4c1bd-247">이 메뉴는 쉽게 닫을 수 있으므로 사용자는 중단없이 계속 탐색 할 수 있으며 도구 모음에서 바로 전체 다운로드 진행 상황을 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-247">This menu is easily dismissible so users can continue browsing uninterrupted, and they can monitor overall download progress right from the toolbar.</span></span> <span data-ttu-id="4c1bd-248">[자세한 내용을 알아보세요](https://techcommunity.microsoft.com/t5/articles/introducing-the-new-downloads-experience/m-p/2111551).</span><span class="sxs-lookup"><span data-stu-id="4c1bd-248">[Learn more](https://techcommunity.microsoft.com/t5/articles/introducing-the-new-downloads-experience/m-p/2111551).</span></span>


### <a name="policy-updates"></a><span data-ttu-id="4c1bd-249">정책 업데이트</span><span class="sxs-lookup"><span data-stu-id="4c1bd-249">Policy updates</span></span>

#### <a name="new-policies"></a><span data-ttu-id="4c1bd-250">새로운 정책</span><span class="sxs-lookup"><span data-stu-id="4c1bd-250">New policies</span></span>

<span data-ttu-id="4c1bd-251">새 정책 7개를 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-251">Seven new policies were added.</span></span> <span data-ttu-id="4c1bd-252">[Microsoft Edge Enterprise 방문 페이지](https://www.microsoft.com/edge/business/download)에서 업데이트된 관리 템플릿을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-252">Download the updated Administrative Templates from the [Microsoft Edge Enterprise landing page](https://www.microsoft.com/edge/business/download).</span></span> <span data-ttu-id="4c1bd-253">다음과 같은 새 정책이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-253">The following new policies were added:</span></span>

- <span data-ttu-id="4c1bd-254">[ ApplicationGuardFavoritesSyncEnabled ](./microsoft-edge-policies.md#applicationguardfavoritessyncenabled)-Application Guard 즐겨 찾기 동기화 사용</span><span class="sxs-lookup"><span data-stu-id="4c1bd-254">[ApplicationGuardFavoritesSyncEnabled](./microsoft-edge-policies.md#applicationguardfavoritessyncenabled) - Application Guard Favorites Sync Enabled</span></span>
- <span data-ttu-id="4c1bd-255">[ ManagedConfigurationPerOrigin ](./microsoft-edge-policies.md#managedconfigurationperorigin)-웹 사이트의 관리 구성 값을 특정 원본으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-255">[ManagedConfigurationPerOrigin](./microsoft-edge-policies.md#managedconfigurationperorigin) - Sets managed configuration values for websites to specific origins</span></span>
- <span data-ttu-id="4c1bd-256">[ PrintRasterizationMode ](./microsoft-edge-policies.md#printrasterizationmode) - 래스터화 모드 인쇄</span><span class="sxs-lookup"><span data-stu-id="4c1bd-256">[PrintRasterizationMode](./microsoft-edge-policies.md#printrasterizationmode) - Print Rasterization Mode</span></span>
- <span data-ttu-id="4c1bd-257">[QuickViewOfficeFilesEnabled](./microsoft-edge-policies.md#quickviewofficefilesenabled) - Microsoft Edge에서 QuickView Office 파일 관리</span><span class="sxs-lookup"><span data-stu-id="4c1bd-257">[QuickViewOfficeFilesEnabled](./microsoft-edge-policies.md#quickviewofficefilesenabled) - Manage QuickView Office files capability in Microsoft Edge</span></span>
- <span data-ttu-id="4c1bd-258">[SSLErrorOverrideAllowedForOrigins](./microsoft-edge-policies.md#sslerroroverrideallowedfororigins) - 사용자가 특정 출처에 대한 HTTPS 경고 페이지에서 계속할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="4c1bd-258">[SSLErrorOverrideAllowedForOrigins](./microsoft-edge-policies.md#sslerroroverrideallowedfororigins) - Allow users to proceed from the HTTPS warning page for specific origins</span></span>
- <span data-ttu-id="4c1bd-259">[ WindowOcclusionEnabled ](./microsoft-edge-policies.md#windowocclusionenabled)-창 폐색 사용</span><span class="sxs-lookup"><span data-stu-id="4c1bd-259">[WindowOcclusionEnabled](./microsoft-edge-policies.md#windowocclusionenabled) - Enable Window Occlusion</span></span>
- <span data-ttu-id="4c1bd-260">[ WindowsHelloForHTTPAuthEnabled ](./microsoft-edge-policies.md#windowshelloforhttpauthenabled)-HTTP 인증용 Windows Hello 사용</span><span class="sxs-lookup"><span data-stu-id="4c1bd-260">[WindowsHelloForHTTPAuthEnabled](./microsoft-edge-policies.md#windowshelloforhttpauthenabled) - Windows Hello For HTTP Auth Enabled</span></span>

#### <a name="deprecated-policies"></a><span data-ttu-id="4c1bd-261">더 이상 사용되지 않는 정책</span><span class="sxs-lookup"><span data-stu-id="4c1bd-261">Deprecated policies</span></span>

- <span data-ttu-id="4c1bd-262">[ NativeWindowOcclusionEnabled ](./microsoft-edge-policies.md#nativewindowocclusionenabled) - 기본 폐색 활성화</span><span class="sxs-lookup"><span data-stu-id="4c1bd-262">[NativeWindowOcclusionEnabled](./microsoft-edge-policies.md#nativewindowocclusionenabled) - Enable Native Window Occlusion</span></span>
- <span data-ttu-id="4c1bd-263">[ SSLVersionMin](./microsoft-edge-policies.md#sslversionmin) - 활성화된 최소 TLS 버전</span><span class="sxs-lookup"><span data-stu-id="4c1bd-263">[SSLVersionMin](./microsoft-edge-policies.md#sslversionmin)- Minimum TLS version enabled</span></span>
<!-- end major 90 -->

## <a name="version-89077454-march-13"></a><span data-ttu-id="4c1bd-264">버전 89.0.774.54: 3월 13일</span><span class="sxs-lookup"><span data-stu-id="4c1bd-264">Version 89.0.774.54: March 13</span></span>

<span data-ttu-id="4c1bd-265">다양한 버그와 성능 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-265">Fixed various bugs and performance issues.</span></span>

## <a name="version-89077450-march-10"></a><span data-ttu-id="4c1bd-266">버전 89.0.774.50: 3월 10일</span><span class="sxs-lookup"><span data-stu-id="4c1bd-266">Version 89.0.774.50: March 10</span></span>

<span data-ttu-id="4c1bd-267">다양한 버그와 성능 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-267">Fixed various bugs and performance issues.</span></span>

## <a name="version-89077448-march-8"></a><span data-ttu-id="4c1bd-268">버전 89.0.774.48: 3월 8일</span><span class="sxs-lookup"><span data-stu-id="4c1bd-268">Version 89.0.774.48: March 8</span></span>

<span data-ttu-id="4c1bd-269">다양한 버그와 성능 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-269">Fixed various bugs and performance issues.</span></span>

## <a name="version-89077445-march-3"></a><span data-ttu-id="4c1bd-270">버전 89.0.774.45: 3월 3일</span><span class="sxs-lookup"><span data-stu-id="4c1bd-270">Version 89.0.774.45: March 3</span></span>

<span data-ttu-id="4c1bd-271">다양한 버그와 성능 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-271">Fixed various bugs and performance issues.</span></span>

## <a name="version-89077439-february-26"></a><span data-ttu-id="4c1bd-272">버전 89.0.774.39: 2월 26일</span><span class="sxs-lookup"><span data-stu-id="4c1bd-272">Version 89.0.774.39: February 26</span></span>

<span data-ttu-id="4c1bd-273">다양한 버그와 성능 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-273">Fixed various bugs and performance issues.</span></span>

## <a name="version-89077434-february-22"></a><span data-ttu-id="4c1bd-274">버전 89.0.774.34: 2월 22일</span><span class="sxs-lookup"><span data-stu-id="4c1bd-274">Version 89.0.774.34: February 22</span></span>

<span data-ttu-id="4c1bd-275">다양한 버그와 성능 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-275">Fixed various bugs and performance issues.</span></span>

## <a name="version-89077427-february-12"></a><span data-ttu-id="4c1bd-276">버전 89.0.774.27: 2월 12일</span><span class="sxs-lookup"><span data-stu-id="4c1bd-276">Version 89.0.774.27: February 12</span></span>

<span data-ttu-id="4c1bd-277">다양한 버그와 성능 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-277">Fixed various bugs and performance issues.</span></span>

## <a name="version-89077423-february-8"></a><span data-ttu-id="4c1bd-278">버전 89.0.774.23: 2월 8일</span><span class="sxs-lookup"><span data-stu-id="4c1bd-278">Version 89.0.774.23: February 8</span></span>

<span data-ttu-id="4c1bd-279">다양한 버그와 성능 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-279">Fixed various bugs and performance issues.</span></span>

<!-- begin major 89 -->

<!--- Archived from Version 87.0.664.18: October 26 to to version 89.0.774.18: February 3 ---->
<!--- Archived from Version 87.0.664.12: October 20 to to version 86.0.622.15: September 14 ---->
<!--- Archived to version 86.0.622.11: September 9 ---->
<!--- Archived to version 85.0.564.18: July 28 ---->

## <a name="see-also"></a><span data-ttu-id="4c1bd-280">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4c1bd-280">See also</span></span>

- [<span data-ttu-id="4c1bd-281">Microsoft Edge Enterprise 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="4c1bd-281">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
