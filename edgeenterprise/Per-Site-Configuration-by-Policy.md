---
title: '정책별 사이트별 구성 '
ms.author: collw
author: AndreaLBarr
manager: laurawi
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: '정책별 사이트별 구성 '
ms.openlocfilehash: 4f1bf9a421f0098ba8105e78f77ac4af62530239
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641694"
---
# <a name="persite-configuration-by-policy"></a><span data-ttu-id="e7d5d-103">정책별 사이트별 구성</span><span class="sxs-lookup"><span data-stu-id="e7d5d-103">PerSite Configuration by Policy</span></span>

## <a name="introduction-browsers-as-decision-makers"></a><span data-ttu-id="e7d5d-104">소개: 의사 결정권자로서의 브라우저</span><span class="sxs-lookup"><span data-stu-id="e7d5d-104">Introduction: Browsers as Decision Makers</span></span>

<span data-ttu-id="e7d5d-105">모든 페이지 로드의 일부로 브라우저는 여러 가지 결정을 내립니다. 특정 API를 사용할 수 있어야 하나요?</span><span class="sxs-lookup"><span data-stu-id="e7d5d-105">As a part of every page load, browsers make many decisions — should a particular API be available?</span></span> <span data-ttu-id="e7d5d-106">리소스 로드를 허용해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="e7d5d-106">Should a resource load be permitted?</span></span> <span data-ttu-id="e7d5d-107">스크립트를 실행할 수 있어야 하나요?</span><span class="sxs-lookup"><span data-stu-id="e7d5d-107">Should script be allowed to run?</span></span> <span data-ttu-id="e7d5d-108">목록이 깁니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-108">The list is long.</span></span>

<span data-ttu-id="e7d5d-109">대부분의 경우 의사 결정에는 사용자 설정과 결정되는 페이지의 URL이라는 두 가지 입력이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-109">In most cases, decisions are governed by two inputs: a user setting, and the URL of the page for which the decision is being made.</span></span>

<span data-ttu-id="e7d5d-110">레거시 Internet Explorer 웹 플랫폼에서 이러한 각 결정은  [URLAction](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537178%28v%3dvs.85%29)이라고 불렀으며 인터넷 제어판 내부의 엔터프라이즈 그룹 정책 및 사용자 설정은 브라우저에서 각 결정을 처리하는 방법을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-110">In the legacy Internet Explorer web platform, each of these decisions was called an [URLAction](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537178%28v%3dvs.85%29), and Enterprise Group Policy and user settings inside the Internet Control Panel controlled how the browser would handle each decision.</span></span>  

<span data-ttu-id="e7d5d-111">Microsoft Edge에서 대부분의 사이트별 권한은 제한된 와일드카드 지원이 있는 간단한 구문을 사용하여 표현된 설정 및 정책에 의해 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-111">In the Microsoft Edge, most per-site permissions are controlled by settings and policies expressed using a simple syntax with limited wild carding support.</span></span> <span data-ttu-id="e7d5d-112">Windows 보안 영역은 여전히 적은 수의 구성 결정에만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-112">Windows Security Zones are still used only for a small number of configuration decisions.</span></span>

## <a name="background-windows-security-zones"></a><span data-ttu-id="e7d5d-113">배경: Windows 보안 영역</span><span class="sxs-lookup"><span data-stu-id="e7d5d-113">Background: Windows Security Zones</span></span>

<span data-ttu-id="e7d5d-114">사용자 또는 해당 관리자의 구성을 간소화하기 위해 레거시 플랫폼은 사이트를 로컬 컴퓨터, 로컬 인트라넷, 신뢰할 수 있는 사이트, 인터넷 및 제한된 사이트 등 5가지 서로 다른  **보안 영역**으로 분류했습니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-114">To simplify configuration for the user or their administrator, the legacy platform classified sites into five different **Security Zones:** Local Machine, Local Intranet, Trusted, Internet, and Restricted Sites.</span></span>

<span data-ttu-id="e7d5d-115">결정을 내릴 때 브라우저는 먼저 웹 사이트를 영역에 매핑한 다음 해당 영역에 대한 해당 URLAction에 대한 설정을 참조하여 수행할 작업을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-115">When making a decision, the browser would first map the website to a Zone, then consult the setting for that URLAction for that Zone to decide what to do.</span></span> <span data-ttu-id="e7d5d-116">"내 인트라넷에서 인증 문제를 자동으로 충족"과 같은 합리적인 기본값은 대부분의 사용자가 기본값에서 설정을 변경할 필요가 없음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-116">Reasonable defaults like “Automatically satisfy authentication challenges from my Intranet” meant that most users never needed to change any settings away from their defaults.</span></span>

<span data-ttu-id="e7d5d-117">사용자는 인터넷 제어판 사용하여 특정 사이트를 영역에 할당하고 각 영역에 대한 사용 권한 결과를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-117">Users can use the Internet Control Panel to assign specific sites to Zones and to configure the permission results for each zone.</span></span> <span data-ttu-id="e7d5d-118">관리되는 환경에서 관리자는 그룹 정책 사용하여 특정 사이트를 영역에 할당하고("사이트 간 할당 목록" 정책을 통해) 영역별로 URLActions에 대한 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-118">In managed environments, administrators can use Group Policy to assign specific sites to Zones (via “Site to Zone Assignment List” policy) and specify the settings for URLActions on a per-zone basis.</span></span> <span data-ttu-id="e7d5d-119">사이트에 대한 수동 관리 또는 사용자 할당 외에도 추가 추론은  [로컬 인트라넷 영역](/archive/blogs/ieinternals/the-intranet-zone)에 사이트를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-119">Beyond manual administrative or user assignment of sites to Zones, additional heuristics could [assign sites to the Local Intranet Zone](/archive/blogs/ieinternals/the-intranet-zone).</span></span> <span data-ttu-id="e7d5d-120">특히 점 없는 호스트 이름(예: `http://payroll`)이 인트라넷 영역에 할당되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-120">In particular, dotless host names (e.g. `http://payroll`) were assigned to the Intranet Zone.</span></span> <span data-ttu-id="e7d5d-121">프록시 구성 스크립트를 사용하는 경우 프록시를 무시하도록 구성된 모든 사이트는 인트라넷 영역에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-121">If a Proxy Configuration script was used, any sites configured to bypass the proxy would be mapped to the Intranet Zone.</span></span>

<span data-ttu-id="e7d5d-122">Microsoft Edge 레거시는 몇 가지 간소화된 변경 내용으로 Internet Explorer 선행 작업에서 영역 아키텍처를 상속했습니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-122">Microsoft Edge Legacy inherited the Zones architecture from its Internet Explorer predecessor with a few simplifying changes:</span></span>

- <span data-ttu-id="e7d5d-123">Windows의 5가지 기본 제공 영역은 인터넷(인터넷), 신뢰할 수 있는 영역(인트라넷+신뢰할 수 있음) 및 로컬 컴퓨터의 3개 영역으로 축소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-123">Windows’ five built-in Zones were collapsed to three: Internet (Internet), Trusted (Intranet+Trusted), and Local Computer.</span></span> <span data-ttu-id="e7d5d-124">제한된 사이트 영역이 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-124">The Restricted Sites Zone was removed.</span></span>

- <span data-ttu-id="e7d5d-125">URLAction 매핑에 대한 영역 간 매핑이 브라우저에 하드 코딩되어 인터넷 제어판 그룹 정책 및 설정을 무시했습니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-125">Zone to URLAction mappings were hardcoded into the browser, ignoring Group Policies and settings in the Internet Control Panel.</span></span>

## <a name="per-site-permissions-in-the-microsoft-edge"></a><span data-ttu-id="e7d5d-126">Microsoft Edge 사이트별 권한</span><span class="sxs-lookup"><span data-stu-id="e7d5d-126">Per-Site Permissions in the Microsoft Edge</span></span>

<span data-ttu-id="e7d5d-127">이전 버전과 달리 새 Microsoft Edge는 Windows 보안 영역을 매우 제한적으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-127">Unlike its predecessors, the new Microsoft Edge makes very limited use of Windows Security Zones.</span></span> <span data-ttu-id="e7d5d-128">대신  [정책](/deployedge/microsoft-edge-policies)을 통해 관리자에게 사이트별 구성을 제공하는 대부분의 사용 권한 및 기능은  [URL 필터 형식](/DeployEdge/edge-learnmmore-url-list-filter%20format) 규칙 목록에 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-128">Instead, most permissions and features that offer administrators per-site configuration via [policy](/deployedge/microsoft-edge-policies) rely on lists of rules in the [URL Filter Format](/DeployEdge/edge-learnmmore-url-list-filter%20format).</span></span>

<span data-ttu-id="e7d5d-129">최종 사용자가  <code>edge://settings/content/siteDetails?site=https://example.com</code>을(를) 열면 다양한 사용 권한에 대한 구성 스위치 및 목록의 긴 목록을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-129">When end-users open <code>edge://settings/content/siteDetails?site=https://example.com</code>, they’ll find a long list of configuration switches and lists for various permissions.</span></span> <span data-ttu-id="e7d5d-130">사용자는 설정 페이지를 직접 사용하는 경우가 거의 없으며, 대신  **페이지 정보** 드롭다운(주소 표시줄에서 잠금 아이콘을 클릭할 때 표시됨) 또는 주소 표시줄의 오른쪽 가장자리에 있는 다양한 프롬프트 또는 단추를 통해 다양한 위젯 및 토글을 사용하여 탐색하는 동안 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-130">Users rarely use the Settings Page directly, instead making choices while browsing using various widgets and toggles in the **Page Info** dropdown (which appears when you click the lock icon in the address bar) or via various prompts or buttons at the right-edge of the address bar.</span></span>

<span data-ttu-id="e7d5d-131">엔터프라이즈는 그룹 정책 사용하여 브라우저의 동작을 제어하는 개별 정책에 대한 사이트 목록을 프로비전할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-131">Enterprises can use Group Policy to provision site lists for individual policies that control the browser’s behavior.</span></span> <span data-ttu-id="e7d5d-132">이러한 정책을 찾으려면 [Microsoft Edge 그룹 정책 설명서](/deployedge/microsoft-edge-policies) 를 열고 **ForUrls** 를 검색하여 로드된 사이트의 URL에 따라 동작을 허용하고 차단하는 정책을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-132">To find these policies, simply open the [Microsoft Edge Group Policy documentation](/deployedge/microsoft-edge-policies) and search for **ForUrls** to find the policies that allow and block behavior based on the loaded site’s URL.</span></span> <span data-ttu-id="e7d5d-133">대부분의 관련 설정은  [콘텐츠 설정에 대한 그룹 정책](/deployedge/microsoft-edge-policies#content-settings) 섹션에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-133">Most of the relevant settings are listed within the [Group Policy for Content Settings](/deployedge/microsoft-edge-policies#content-settings) section.</span></span>

<span data-ttu-id="e7d5d-134">지정된 설정의 기본 동작을 제어하는 여러 정책(이름에 **기본**포함)도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-134">There are also a number of policies (whose names contain **Default**) that control the default behavior for a given setting.</span></span>

<span data-ttu-id="e7d5d-135">대부분의 설정은 매우 모호하며(WebSerial, WebMIDI) 기본값(이미지)에서 설정을 변경할 이유가 없는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-135">Many of the settings are very obscure (WebSerial, WebMIDI) and there’s very often no reason to change a setting away from the default (Images).</span></span>

## <a name="common-questions"></a><span data-ttu-id="e7d5d-136">일반적인 질문</span><span class="sxs-lookup"><span data-stu-id="e7d5d-136">Common Questions</span></span>

## <a name="q-can-the-url-filter-format-match-on-a-sites-ip-address"></a><span data-ttu-id="e7d5d-137">Q: URL 필터 형식이 사이트의 IP 주소와 일치할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="e7d5d-137">Q: Can the URL Filter Format match on a site’s IP address?</span></span>

<span data-ttu-id="e7d5d-138">아니요, 형식은 허용 및 차단 목록에 대한 IP 범위 지정을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-138">No, the format does not support specifying an IP-range for allow and block lists.</span></span> <span data-ttu-id="e7d5d-139">해당 형식은 개별 IP  **리터럴**의 사양을 지원하지만 이러한 규칙은 사용자가 해당 리터럴(예:  <http://127.0.0.1/>)을 사용하여 사이트로 이동하는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-139">It does support specification of individual IP **literals**, but such rules are only respected if the user navigates to the site using said literal (e.g. <http://127.0.0.1/>).</span></span> <span data-ttu-id="e7d5d-140">호스트 이름(<http://localhost>)을 사용하는 경우 호스트의 확인된 IP가 필터 나열 IP와 일치하더라도 IP 리터럴 규칙이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-140">If a hostname is used (<http://localhost>), the IP Literal rule will not be respected even though the resolved IP of the host matches the filter-listed IP.</span></span>

## <a name="q-can-url-filters-matchjustdotless-host-names"></a><span data-ttu-id="e7d5d-141">Q: URL 필터가 점 없는 호스트 이름과만 일치할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="e7d5d-141">Q: Can URL Filters match just dotless host names?</span></span>

<span data-ttu-id="e7d5d-142">아니요.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-142">No.</span></span> <span data-ttu-id="e7d5d-143">원하는 각 호스트 이름(예:`https://payroll`, `https://stock`, `https://who` 등)을 개별적으로 나열해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-143">You must individually list each desired hostname, e.g. (`https://payroll`, `https://stock`, `https://who`, etc).</span></span>

<span data-ttu-id="e7d5d-144">호스트 이름이 형식이 되도록 인트라넷을 구조화할 만큼 미래 지향적인 경우:</span><span class="sxs-lookup"><span data-stu-id="e7d5d-144">If you were forward-thinking enough to structure your intranet such that your host names are of the form:</span></span>

- <div style="display: inline">`https://payroll.contoso-intranet.com`</div>

- <div style="display: inline">`https://timecard.contoso-intranet.com`</div>

- <div style="display: inline">`https://sharepoint.contoso-intranet.com`</div>

<span data-ttu-id="e7d5d-145">축하합니다. 귀하는 모범 사례를 구현했습니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-145">Congratulations, you’ve implemented a best practice.</span></span> <span data-ttu-id="e7d5d-146">\**_.contoso-intranet.com_* 항목을 사용하여 원하는 각 정책을 구성할 수 있으며 전체 인트라넷이   옵트인됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-146">You can configure each desired policy with a \**_.contoso-intranet.com_* entry and your entire Intranet will be opted in.</span></span>

## <a name="use-of-security-zones-inthe-microsoft-edge"></a><span data-ttu-id="e7d5d-147">Microsoft Edge 보안 영역 사용</span><span class="sxs-lookup"><span data-stu-id="e7d5d-147">Use of Security Zones in the Microsoft Edge</span></span>

<span data-ttu-id="e7d5d-148">Microsoft Edge는 대부분 URL 필터 형식을 사용하는 개별 정책을 사용하지만, 이전에는 영역 구성에 의존하던 엔터프라이즈 내에서 배포를 간소화하기 위해 기본적으로 적은 수의 위치에서 Windows의 보안 영역을 계속 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-148">While Microsoft Edge mostly relies upon individual policies using the URL Filter format, it continues to use Windows’ Security Zones by default in a small number of places in order to simplify deployment within Enterprises that have historically relied upon Zones configuration.</span></span> <span data-ttu-id="e7d5d-149">다음 동작은 영역 정책에 의해 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-149">The following behaviors are controlled by Zone policy:</span></span>

1. <span data-ttu-id="e7d5d-150">Kerberos/NTLM(Windows 통합 인증) 자격 증명을 자동으로 해제할지 여부를 결정할 때</span><span class="sxs-lookup"><span data-stu-id="e7d5d-150">When deciding whether to release Windows Integrated Authentication (Kerberos/NTLM) credentials automatically</span></span>

2. <span data-ttu-id="e7d5d-151">파일 다운로드를 처리하는 방법을 결정할 때</span><span class="sxs-lookup"><span data-stu-id="e7d5d-151">When deciding how to handle File Downloads</span></span>

3. <span data-ttu-id="e7d5d-152">Internet Explorer 모드:</span><span class="sxs-lookup"><span data-stu-id="e7d5d-152">For Internet Explorer Mode</span></span>

## <a name="credential-release"></a><span data-ttu-id="e7d5d-153">자격 증명 릴리스</span><span class="sxs-lookup"><span data-stu-id="e7d5d-153">Credential Release</span></span>

<span data-ttu-id="e7d5d-154">기본적으로 Microsoft Edge는 URLACTION_CREDENTIALS_USE를 평가하여 Windows 통합 인증이 자동으로 사용되는지 또는 사용자에게 수동 인증 프롬프트가 표시되는지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-154">By default, Microsoft Edge will evaluate URLACTION_CREDENTIALS_USE to decide whether Windows Integrated Authentication is used automatically, or the user should instead see a manual authentication prompt.</span></span> <span data-ttu-id="e7d5d-155">[AuthServerAllowlist 사이트 목록 정책](/deployedge/microsoft-edge-policies#authserverallowlist)을 구성하면 영역 정책을 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-155">Configuring an [AuthServerAllowlist site list policy](/deployedge/microsoft-edge-policies#authserverallowlist) will prevent Zone Policy from being consulted.</span></span>

## <a name="file-downloads"></a><span data-ttu-id="e7d5d-156">파일 다운로드</span><span class="sxs-lookup"><span data-stu-id="e7d5d-156">File Downloads</span></span>

<span data-ttu-id="e7d5d-157">파일 다운로드 원본에 대한 증거(이 경우 "[웹 표시](https://textslashplain.com/2016/04/04/downloads-and-the-mark-of-the-web/)라고 함)는 인터넷 영역에서 다운로드한 파일에 대해 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-157">Evidence about the origins of a file download (the so-called “[Mark of the Web](https://textslashplain.com/2016/04/04/downloads-and-the-mark-of-the-web/) is recorded for files downloaded from the Internet Zone.</span></span> <span data-ttu-id="e7d5d-158">다른 애플리케이션(예: Windows Shell, Microsoft Office 등)은 파일을 처리하는 방법을 결정할 때 이 원본 증거를 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-158">Other applications (e.g. the Windows Shell, Microsoft Office, etc) may take this origin evidence into account when deciding how to handle a file.</span></span>

<span data-ttu-id="e7d5d-159">Windows 보안 영역 정책이 시작 응용 프로그램 및 안전하지 않은 파일 설정을 사용하지 않도록 구성된 경우 Microsoft Edge 다운로드 관리자는 "다운로드할 수 없음 – 차단됨"이라는 메모와 함께 해당 영역의 사이트에서 파일 다운로드를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-159">If the Windows Security Zone policy is configured to Disable the setting Launching applications and unsafe files, the Microsoft Edge download manager will block file downloads from sites in that Zone with a note: “Couldn’t download – Blocked.”</span></span>  

## <a name="ie-mode"></a><span data-ttu-id="e7d5d-160">IE 모드</span><span class="sxs-lookup"><span data-stu-id="e7d5d-160">IE mode</span></span>

<span data-ttu-id="e7d5d-161"> [IE 모드에서 모든 인트라넷 사이트를 열도록](/deployedge/edge-ie-mode#configure-all-intranet-sites) IE 모드를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-161">IE mode can be configured to [open all Intranet sites in IE mode](/deployedge/edge-ie-mode#configure-all-intranet-sites).</span></span> <span data-ttu-id="e7d5d-162">이 구성에서 Edge는 IE 모드에서 열지 여부를 결정할 때 URL 영역을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-162">When in this configuration, Edge evaluates the Zone of a URL when deciding whether or not it should open in IE mode.</span></span> <span data-ttu-id="e7d5d-163">이 초기 결정 외에도 IE 모드 탭은 실제로 Internet Explorer을 실행하고 있으므로 Internet Explorer 그 자체처럼 모든 정책 결정에 대한 영역 설정을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-163">Beyond this initial decision, IE mode tabs are really running Internet Explorer, and as a consequence they evaluate Zones settings for every policy decision just as Internet Explorer itself did.</span></span>

## <a name="summary"></a><span data-ttu-id="e7d5d-164">요약</span><span class="sxs-lookup"><span data-stu-id="e7d5d-164">Summary</span></span>

<span data-ttu-id="e7d5d-165">대부분의 경우 Microsoft Edge 설정은 기본값으로 둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-165">In most cases, Microsoft Edge settings can be left at their defaults.</span></span> <span data-ttu-id="e7d5d-166">모든 사이트 또는 특정 사이트의 기본값을 변경하려는 관리자는 적절한 그룹 정책을 사용하여 사이트 목록 또는 기본 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-166">Administrators who wish to change the defaults for all sites or specific sites can use the appropriate Group Policies to specify Site Lists or default behaviors.</span></span> <span data-ttu-id="e7d5d-167">몇 가지 경우(자격 증명 릴리스, 파일 다운로드 및 IE 모드)에 관리자는 Windows 보안 영역 설정을 구성하여 동작을 계속 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="e7d5d-167">In a handful of cases (credential release, file download, and IE mode), administrators will continue to control behavior by configuring Windows Security Zones settings.</span></span>
