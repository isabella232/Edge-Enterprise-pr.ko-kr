---
title: Microsoft Edge 업데이트 정책 설명서
ms.author: stmoody
author: dan-wesley
manager: tahills
ms.date: 11/12/2020
audience: ITPro
ms.topic: reference
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
ms.custom: ''
description: Microsoft Edge 업데이트 프로그램에서 지원하는 모든 정책에 대한 설명서
ms.openlocfilehash: 921a95c0a5e80ba08fa745748ffa8b0da714ea7d
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2021
ms.locfileid: "11617888"
---
# <a name="microsoft-edge---update-policies"></a><span data-ttu-id="a92aa-103">Microsoft Edge - 업데이트 정책</span><span class="sxs-lookup"><span data-stu-id="a92aa-103">Microsoft Edge - Update policies</span></span>

<span data-ttu-id="a92aa-104">최신 버전의 Microsoft Edge에는 Microsoft Edge가 업데이트되는 방법 및 시기를 제어하는 데 사용할 수 있는 다음과 같은 정책이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-104">The latest version of Microsoft Edge includes the following policies that you can use to control how and when Microsoft Edge is updated.</span></span>

<span data-ttu-id="a92aa-105">Microsoft Edge에서 사용할 수 있는 다른 정책에 대한 자세한 내용은 [Microsoft Edge 브라우저 정책 참조](microsoft-edge-policies.md)를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="a92aa-105">For information about other policies available in Microsoft Edge, check out [Microsoft Edge browser policy reference](microsoft-edge-policies.md)</span></span>
> [!NOTE]
> <span data-ttu-id="a92aa-106">이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-106">This article applies to Microsoft Edge version 77 or later.</span></span>
## <a name="available-policies"></a><span data-ttu-id="a92aa-107">사용 가능한 정책</span><span class="sxs-lookup"><span data-stu-id="a92aa-107">Available policies</span></span>
<span data-ttu-id="a92aa-108">다음 표에서는 이번 릴리스의 Microsoft Edge에서 사용할 수 있는 모든 업데이트 관련 그룹 정책을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-108">These tables lists all of the update-related group policies available in this release of Microsoft Edge.</span></span> <span data-ttu-id="a92aa-109">특정 정책에 대해 자세히 알아보려면 표의 링크를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="a92aa-109">Use the links in the table to get more details about specific policies.</span></span>

<span data-ttu-id="a92aa-110">|&nbsp;|&nbsp;| |**-**| | |**[애플리케이션](#applications)**|[기본 설정](#preferences)| |**[프록시 서버](#proxy-server)**|[Microsoft Edge WebView](#microsoft-edge-webview)|</span><span class="sxs-lookup"><span data-stu-id="a92aa-110">|&nbsp;|&nbsp;| |**-**|-| |**[Applications](#applications)**|[Preferences](#preferences)| |**[Proxy Server](#proxy-server)**|[Microsoft Edge WebView](#microsoft-edge-webview)|</span></span>
### [<a name="applications"></a><span data-ttu-id="a92aa-111">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="a92aa-111">Applications</span></span>](#applications-policies)
|<span data-ttu-id="a92aa-112">정책 이름</span><span class="sxs-lookup"><span data-stu-id="a92aa-112">Policy Name</span></span>|<span data-ttu-id="a92aa-113">캡션</span><span class="sxs-lookup"><span data-stu-id="a92aa-113">Caption</span></span>|
|-|-|
|[<span data-ttu-id="a92aa-114">InstallDefault</span><span class="sxs-lookup"><span data-stu-id="a92aa-114">InstallDefault</span></span>](#installdefault)|<span data-ttu-id="a92aa-115">설치 허용 기본값</span><span class="sxs-lookup"><span data-stu-id="a92aa-115">Allow installation default</span></span>|
|[<span data-ttu-id="a92aa-116">UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="a92aa-116">UpdateDefault</span></span>](#updatedefault)|<span data-ttu-id="a92aa-117">업데이트 정책 재정의 기본값</span><span class="sxs-lookup"><span data-stu-id="a92aa-117">Update policy override default</span></span>|
|[<span data-ttu-id="a92aa-118">설치</span><span class="sxs-lookup"><span data-stu-id="a92aa-118">Install</span></span>](#install)|<span data-ttu-id="a92aa-119">설치 허용(채널별)</span><span class="sxs-lookup"><span data-stu-id="a92aa-119">Allow installation (per channel)</span></span>|
|[<span data-ttu-id="a92aa-120">업데이트</span><span class="sxs-lookup"><span data-stu-id="a92aa-120">Update</span></span>](#update)|<span data-ttu-id="a92aa-121">업데이트 정책 재정의(채널별)</span><span class="sxs-lookup"><span data-stu-id="a92aa-121">Update policy override (per channel)</span></span>|
|[<span data-ttu-id="a92aa-122">Allowsxs</span><span class="sxs-lookup"><span data-stu-id="a92aa-122">Allowsxs</span></span>](#allowsxs)|<span data-ttu-id="a92aa-123">Microsoft Edge 함께 사용 브라우저 환경 허용</span><span class="sxs-lookup"><span data-stu-id="a92aa-123">Allow Microsoft Edge Side by Side browser experience</span></span>|
|[<span data-ttu-id="a92aa-124">CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="a92aa-124">CreateDesktopShortcutDefault</span></span>](#createdesktopshortcutdefault)|<span data-ttu-id="a92aa-125">기본 설치 시 데스크톱 바로 가기 만들기 방지</span><span class="sxs-lookup"><span data-stu-id="a92aa-125">Prevent Desktop Shortcut creation upon install default</span></span>|
|[<span data-ttu-id="a92aa-126">CreateDesktopShortcut</span><span class="sxs-lookup"><span data-stu-id="a92aa-126">CreateDesktopShortcut</span></span>](#createdesktopshortcut)|<span data-ttu-id="a92aa-127">설치 시 데스크톱 바로 가기 만들기 방지(채널 당)</span><span class="sxs-lookup"><span data-stu-id="a92aa-127">Prevent Desktop Shortcut creation upon install (per channel)</span></span>|
|[<span data-ttu-id="a92aa-128">RollbackToTargetVersion</span><span class="sxs-lookup"><span data-stu-id="a92aa-128">RollbackToTargetVersion</span></span>](#rollbacktotargetversion)|<span data-ttu-id="a92aa-129">대상 버전으로 롤백(채널당)</span><span class="sxs-lookup"><span data-stu-id="a92aa-129">Rollback to Target version (per channel)</span></span>|
|[<span data-ttu-id="a92aa-130">TargetVersionPrefix</span><span class="sxs-lookup"><span data-stu-id="a92aa-130">TargetVersionPrefix</span></span>](#targetversionprefix)|<span data-ttu-id="a92aa-131">대상 버전 재정의(채널당)</span><span class="sxs-lookup"><span data-stu-id="a92aa-131">Target version override (per channel)</span></span>|

### [<a name="preferences"></a><span data-ttu-id="a92aa-132">기본 설정</span><span class="sxs-lookup"><span data-stu-id="a92aa-132">Preferences</span></span>](#preferences-policies)
|<span data-ttu-id="a92aa-133">정책 이름</span><span class="sxs-lookup"><span data-stu-id="a92aa-133">Policy Name</span></span>|<span data-ttu-id="a92aa-134">캡션</span><span class="sxs-lookup"><span data-stu-id="a92aa-134">Caption</span></span>|
|-|-|
|[<span data-ttu-id="a92aa-135">AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="a92aa-135">AutoUpdateCheckPeriodMinutes</span></span>](#autoupdatecheckperiodminutes)|<span data-ttu-id="a92aa-136">자동 업데이트 확인 기간 재정의</span><span class="sxs-lookup"><span data-stu-id="a92aa-136">Auto-update check period override</span></span>|
|[<span data-ttu-id="a92aa-137">UpdatesSuppressed</span><span class="sxs-lookup"><span data-stu-id="a92aa-137">UpdatesSuppressed</span></span>](#updatessuppressed)|<span data-ttu-id="a92aa-138">매일 자동 업데이트 확인 억제 기간</span><span class="sxs-lookup"><span data-stu-id="a92aa-138">Time period in each day to suppress auto-update check</span></span>|

### [<a name="proxy-server"></a><span data-ttu-id="a92aa-139">프록시 서버</span><span class="sxs-lookup"><span data-stu-id="a92aa-139">Proxy Server</span></span>](#proxy-server-policies)
|<span data-ttu-id="a92aa-140">정책 이름</span><span class="sxs-lookup"><span data-stu-id="a92aa-140">Policy Name</span></span>|<span data-ttu-id="a92aa-141">캡션</span><span class="sxs-lookup"><span data-stu-id="a92aa-141">Caption</span></span>|
|-|-|
|[<span data-ttu-id="a92aa-142">ProxyMode</span><span class="sxs-lookup"><span data-stu-id="a92aa-142">ProxyMode</span></span>](#proxymode)|<span data-ttu-id="a92aa-143">프록시 서버 설정 지정 방법 선택</span><span class="sxs-lookup"><span data-stu-id="a92aa-143">Choose how to specify proxy server settings</span></span>|
|[<span data-ttu-id="a92aa-144">ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="a92aa-144">ProxyPacUrl</span></span>](#proxypacurl)|<span data-ttu-id="a92aa-145">프록시 .pac 파일 URL</span><span class="sxs-lookup"><span data-stu-id="a92aa-145">URL to a proxy .pac file</span></span>|
|[<span data-ttu-id="a92aa-146">ProxyServer</span><span class="sxs-lookup"><span data-stu-id="a92aa-146">ProxyServer</span></span>](#proxyserver)|<span data-ttu-id="a92aa-147">프록시 서버 주소 또는 URL</span><span class="sxs-lookup"><span data-stu-id="a92aa-147">Address or URL of proxy server</span></span>|

### [<a name="microsoft-edge-webview"></a><span data-ttu-id="a92aa-148">Microsoft Edge WebView</span><span class="sxs-lookup"><span data-stu-id="a92aa-148">Microsoft Edge WebView</span></span>](#microsoft-edge-webview-policies)
|<span data-ttu-id="a92aa-149">정책 이름</span><span class="sxs-lookup"><span data-stu-id="a92aa-149">Policy Name</span></span>|<span data-ttu-id="a92aa-150">캡션</span><span class="sxs-lookup"><span data-stu-id="a92aa-150">Caption</span></span>|
|-|-|
|[<span data-ttu-id="a92aa-151">설치</span><span class="sxs-lookup"><span data-stu-id="a92aa-151">Install</span></span>](#install-webview)|<span data-ttu-id="a92aa-152">설치 허용</span><span class="sxs-lookup"><span data-stu-id="a92aa-152">Allow installation</span></span>|
|[<span data-ttu-id="a92aa-153">업데이트</span><span class="sxs-lookup"><span data-stu-id="a92aa-153">Update</span></span>](#update-webview)|<span data-ttu-id="a92aa-154">업데이트 정책 재정의</span><span class="sxs-lookup"><span data-stu-id="a92aa-154">Update policy override</span></span>|

## <a name="applications-policies"></a><span data-ttu-id="a92aa-155">응용 프로그램 정책</span><span class="sxs-lookup"><span data-stu-id="a92aa-155">Applications policies</span></span>

[<span data-ttu-id="a92aa-156">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="a92aa-156">Back to top</span></span>](#microsoft-edge---update-policies)
### <a name="installdefault"></a><span data-ttu-id="a92aa-157">InstallDefault</span><span class="sxs-lookup"><span data-stu-id="a92aa-157">InstallDefault</span></span>
#### <a name="allow-installation-default"></a><span data-ttu-id="a92aa-158">설치 허용 기본값</span><span class="sxs-lookup"><span data-stu-id="a92aa-158">Allow installation default</span></span>
><span data-ttu-id="a92aa-159">Microsoft Edge 업데이트 1.2.145.5 이상</span><span class="sxs-lookup"><span data-stu-id="a92aa-159">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <a name="description"></a><span data-ttu-id="a92aa-160">설명</span><span class="sxs-lookup"><span data-stu-id="a92aa-160">Description</span></span>
<span data-ttu-id="a92aa-161">도메인에 가입된 장치에서 Microsoft Edge를 허용하거나 차단하기 위해 모든 채널의 기본 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-161">You can specify the default behavior of all channels to allow or block Microsoft Edge on domain-joined devices.</span></span>

<span data-ttu-id="a92aa-162">특정 채널에 대한 ‘[설치 허용](#install)’ 정책을 사용하도록 설정하여 개별 채널에 대한 이 정책을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-162">You can override this policy for individual channels by enabling the '[Allow installation](#install)' policy for specific channels.</span></span>

<span data-ttu-id="a92aa-163">이 정책을 사용하지 않도록 설정하면 Microsoft Edge의 설치가 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-163">If you disable this policy, the installation of Microsoft Edge is blocked.</span></span> <span data-ttu-id="a92aa-164">이는 '[설치 허용](#install)' 정책이 구성되지 않음으로 설정된 경우에만 Microsoft Edge 소프트웨어 설치에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-164">This only affects the installation of Microsoft Edge software when the '[Allow installation](#install)' policy is set to Not Configured.</span></span>

<span data-ttu-id="a92aa-165">이 정책은 Microsoft Edge 업데이트 실행을 금지하거나 사용자가 다른 방법으로 Microsoft Edge 소프트웨어를 설치하는 것을 방지하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-165">This policy doesn't prevent Microsoft Edge Update from running or prevent users from installing Microsoft Edge software using other methods.</span></span>

<span data-ttu-id="a92aa-166">이 정책은 Microsoft® Active Directory® 도메인에 연결된 Windows 인스턴스에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-166">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="a92aa-167">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="a92aa-167">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="a92aa-168">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="a92aa-168">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="a92aa-169">GP 고유 이름: InstallDefault</span><span class="sxs-lookup"><span data-stu-id="a92aa-169">GP unique name: InstallDefault</span></span>
- <span data-ttu-id="a92aa-170">GP 이름: 설치 허용 기본값</span><span class="sxs-lookup"><span data-stu-id="a92aa-170">GP name: Allow installation default</span></span>
- <span data-ttu-id="a92aa-171">GP 경로: 관리 템플릿/Microsoft Edge 업데이트/응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="a92aa-171">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="a92aa-172">GP ADMX 파일 이름: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="a92aa-172">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="a92aa-173">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="a92aa-173">Windows Registry Settings</span></span>
- <span data-ttu-id="a92aa-174">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="a92aa-174">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="a92aa-175">값 이름: InstallDefault</span><span class="sxs-lookup"><span data-stu-id="a92aa-175">Value Name: InstallDefault</span></span>
- <span data-ttu-id="a92aa-176">값 형식: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="a92aa-176">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="a92aa-177">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="a92aa-177">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="a92aa-178">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="a92aa-178">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="updatedefault"></a><span data-ttu-id="a92aa-179">UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="a92aa-179">UpdateDefault</span></span>
#### <a name="update-policy-override-default"></a><span data-ttu-id="a92aa-180">업데이트 정책 재정의 기본값</span><span class="sxs-lookup"><span data-stu-id="a92aa-180">Update policy override default</span></span>
><span data-ttu-id="a92aa-181">Microsoft Edge 업데이트 1.2.145.5 이상</span><span class="sxs-lookup"><span data-stu-id="a92aa-181">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <a name="description"></a><span data-ttu-id="a92aa-182">설명</span><span class="sxs-lookup"><span data-stu-id="a92aa-182">Description</span></span>
<span data-ttu-id="a92aa-183">Microsoft Edge 업데이트가 Microsoft Edge에 사용 가능한 업데이트를 처리하는 방식과 관련하여 모든 채널에 대해 기본 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-183">Lets you specify the default behavior for all channels concerning the way Microsoft Edge Update handles available updates for Microsoft Edge.</span></span> <span data-ttu-id="a92aa-184">특정 채널에 ‘[업데이트 정책 재정의](#update)’ 정책을 지정하여 채널별로 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-184">Can be overridden for individual channels by specifying the '[Update policy override](#update)' policy for those specific channels.</span></span>

  <span data-ttu-id="a92aa-185">이 정책을 사용하도록 설정하면 다음 중 구성된 옵션에 따라 Microsoft Edge 업데이트가 Microsoft Edge에 대한 업데이트를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-185">If you enable this policy, Microsoft Edge Update handles Microsoft Edge updates according to how you configure the following options:</span></span>
   - <span data-ttu-id="a92aa-186">항상 업데이트 허용: 업데이트는 정기 업데이트 확인 또는 수동 업데이트 확인을 통해 검색되는 경우 항상 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-186">Always allow updates: Updates are always applied when found, either by periodic update check or by a manual update check.</span></span>
   - <span data-ttu-id="a92aa-187">자동 업데이트만: 업데이트는 정기 업데이트 확인에서 검색된 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-187">Automatic silent updates only: Updates are applied only when they're found by the periodic update check.</span></span>
   - <span data-ttu-id="a92aa-188">수동 업데이트만: 업데이트는 사용자가 수동 업데이트 확인을 실행하는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-188">Manual updates only: Updates are applied only when the user runs a manual update check.</span></span>
   - <span data-ttu-id="a92aa-189">업데이트 사용 안 함: 업데이트가 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-189">Updates disabled: Updates are never applied.</span></span>

  <span data-ttu-id="a92aa-190">수동 업데이트를 선택하는 경우 앱의 수동 업데이트 메커니즘(사용 가능한 경우)을 사용하여 정기적으로 업데이트를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-190">If you select manual updates, make sure you periodically check for updates by using the app's manual update mechanism, if available.</span></span> <span data-ttu-id="a92aa-191">업데이트를 사용하지 않도록 설정하는 경우 정기적으로 업데이트를 확인하여 사용자에게 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-191">If you disable updates, periodically check for updates, and distribute them to users.</span></span>

  <span data-ttu-id="a92aa-192">이 정책을 사용하도록 설정하고 구성하지 않으면 Microsoft Edge 업데이트는 ‘[업데이트 정책 재정의](#update)’ 정책에 지정된 대로 사용 가능한 업데이트를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-192">If you don't enable and configure this policy, Microsoft Edge Update handles available updates as specified by the '[Update policy override](#update)' policy.</span></span>

  <span data-ttu-id="a92aa-193">이 정책은 Microsoft® Active Directory® 도메인에 연결된 Windows 인스턴스에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-193">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="a92aa-194">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="a92aa-194">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="a92aa-195">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="a92aa-195">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="a92aa-196">GP 고유 이름: UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="a92aa-196">GP unique name: UpdateDefault</span></span>
- <span data-ttu-id="a92aa-197">GP 이름: 업데이트 정책 재정의 기본값</span><span class="sxs-lookup"><span data-stu-id="a92aa-197">GP name: Update policy override default</span></span>
- <span data-ttu-id="a92aa-198">GP 경로: 관리 템플릿/Microsoft Edge 업데이트/응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="a92aa-198">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="a92aa-199">GP ADMX 파일 이름: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="a92aa-199">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="a92aa-200">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="a92aa-200">Windows Registry Settings</span></span>
- <span data-ttu-id="a92aa-201">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="a92aa-201">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="a92aa-202">값 이름: UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="a92aa-202">Value Name: UpdateDefault</span></span>
- <span data-ttu-id="a92aa-203">값 형식: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="a92aa-203">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="a92aa-204">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="a92aa-204">Example value:</span></span>
```
0x00000003
```
[<span data-ttu-id="a92aa-205">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="a92aa-205">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="install"></a><span data-ttu-id="a92aa-206">설치</span><span class="sxs-lookup"><span data-stu-id="a92aa-206">Install</span></span>
#### <a name="allow-installation"></a><span data-ttu-id="a92aa-207">설치 허용</span><span class="sxs-lookup"><span data-stu-id="a92aa-207">Allow installation</span></span>
><span data-ttu-id="a92aa-208">Microsoft Edge 업데이트 1.2.145.5 이상</span><span class="sxs-lookup"><span data-stu-id="a92aa-208">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <a name="description"></a><span data-ttu-id="a92aa-209">설명</span><span class="sxs-lookup"><span data-stu-id="a92aa-209">Description</span></span>
<span data-ttu-id="a92aa-210">도메인에 가입된 장치에 Microsoft Edge 채널을 설치할 수 있는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-210">Specifies whether a Microsoft Edge channel can be installed on domain-joined devices.</span></span>

  <span data-ttu-id="a92aa-211">채널에 이 정책을 사용하면 Microsoft Edge가 설치에서 차단되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-211">If you enable this policy for a channel, Microsoft Edge will not be blocked from installation.</span></span>

  <span data-ttu-id="a92aa-212">채널에 이 정책을 사용하지 않으면 Microsoft Edge가 설치에서 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-212">If you disable this policy for a channel, Microsoft Edge will be blocked from installation.</span></span>

  <span data-ttu-id="a92aa-213">채널에 대해 이 정책을 구성하지 않으면 ‘[설치 허용](#installdefault)’ 정책 구성이 사용자가 해당 Microsoft Edge 채널을 설치할 수 있는지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-213">If you don't configure this policy for a channel, the '[Allow installation default](#installdefault)' policy configuration determines whether users can install that channel of Microsoft Edge.</span></span>

  <span data-ttu-id="a92aa-214">이 정책은 Microsoft® Active Directory® 도메인에 연결된 Windows 인스턴스에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-214">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="a92aa-215">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="a92aa-215">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="a92aa-216">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="a92aa-216">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="a92aa-217">GP 고유 이름: Install</span><span class="sxs-lookup"><span data-stu-id="a92aa-217">GP unique name: Install</span></span>
- <span data-ttu-id="a92aa-218">GP 이름: 설치 허용</span><span class="sxs-lookup"><span data-stu-id="a92aa-218">GP name: Allow installation</span></span>
- <span data-ttu-id="a92aa-219">GP 경로:</span><span class="sxs-lookup"><span data-stu-id="a92aa-219">GP path:</span></span> 
  - <span data-ttu-id="a92aa-220">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a92aa-220">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="a92aa-221">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="a92aa-221">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="a92aa-222">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="a92aa-222">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="a92aa-223">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="a92aa-223">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="a92aa-224">GP ADMX 파일 이름: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="a92aa-224">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="a92aa-225">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="a92aa-225">Windows Registry Settings</span></span>
- <span data-ttu-id="a92aa-226">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="a92aa-226">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="a92aa-227">값 이름:</span><span class="sxs-lookup"><span data-stu-id="a92aa-227">Value Name:</span></span> 
  - <span data-ttu-id="a92aa-228">(Stable): Install{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="a92aa-228">(Stable): Install{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="a92aa-229">(Beta): Install{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="a92aa-229">(Beta): Install{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="a92aa-230">(Canary): Install{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="a92aa-230">(Canary): Install{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="a92aa-231">(Dev): Install{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="a92aa-231">(Dev): Install{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="a92aa-232">값 형식: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="a92aa-232">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="a92aa-233">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="a92aa-233">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="a92aa-234">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="a92aa-234">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="update"></a><span data-ttu-id="a92aa-235">업데이트</span><span class="sxs-lookup"><span data-stu-id="a92aa-235">Update</span></span>
#### <a name="update-policy-override"></a><span data-ttu-id="a92aa-236">업데이트 정책 재정의</span><span class="sxs-lookup"><span data-stu-id="a92aa-236">Update policy override</span></span>
><span data-ttu-id="a92aa-237">Microsoft Edge 업데이트 1.2.145.5 이상</span><span class="sxs-lookup"><span data-stu-id="a92aa-237">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <a name="description"></a><span data-ttu-id="a92aa-238">설명</span><span class="sxs-lookup"><span data-stu-id="a92aa-238">Description</span></span>
<span data-ttu-id="a92aa-239">Microsoft Edge 업데이트가 Microsoft Edge에서 사용 가능한 업데이트를 처리하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-239">Specifies how Microsoft Edge Update handles available updates from Microsoft Edge.</span></span>

<span data-ttu-id="a92aa-240">이 정책을 사용하도록 설정하면 다음 중 구성된 옵션에 따라 Microsoft Edge 업데이트가 Microsoft Edge에 대한 업데이트를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-240">If you enable this policy, Microsoft Edge Update handles Microsoft Edge updates according to how you configure the following options:</span></span>
  - <span data-ttu-id="a92aa-241">항상 업데이트 허용: 업데이트는 정기 업데이트 확인 또는 수동 업데이트 확인을 통해 검색되는 경우 항상 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-241">Always allow updates: Updates are always applied when found, either by periodic update check or by a manual update check.</span></span>
  - <span data-ttu-id="a92aa-242">자동 업데이트만: 업데이트는 정기 업데이트 확인에서 검색된 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-242">Automatic silent updates only: Updates are applied only when they're found by the periodic update check.</span></span>
  - <span data-ttu-id="a92aa-243">수동 업데이트만: 업데이트는 사용자가 수동 업데이트 확인을 실행하는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-243">Manual updates only: Updates are applied only when the user runs a manual update check.</span></span> <span data-ttu-id="a92aa-244">(일부 앱은 이 옵션에 대한 인터페이스를 제공하지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="a92aa-244">(Not all apps provide an interface for this option.)</span></span>
  - <span data-ttu-id="a92aa-245">업데이트 사용 안 함: 업데이트가 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-245">Updates disabled: Updates are never applied.</span></span>

<span data-ttu-id="a92aa-246">수동 업데이트를 선택하는 경우 앱의 수동 업데이트 메커니즘(사용 가능한 경우)을 사용하여 정기적으로 업데이트를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-246">If you select manual updates, make sure you periodically check for updates by using the app's manual update mechanism, if available.</span></span> <span data-ttu-id="a92aa-247">업데이트를 사용하지 않도록 설정하는 경우 정기적으로 업데이트를 확인하여 사용자에게 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-247">If you disable updates, periodically check for updates, and distribute them to users.</span></span>

<span data-ttu-id="a92aa-248">이 정책을 사용하도록 설정하고 구성하지 않으면 Microsoft Edge 업데이트는 ‘[업데이트 정책 재정의 기본값](#updatedefault)’ 정책에 지정된 대로 사용 가능한 업데이트를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-248">If you don't enable and configure this policy, Microsoft Edge Update handles available updates as specified by the '[Update policy override default](#updatedefault)' policy.</span></span>

<span data-ttu-id="a92aa-249">자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2136406](https://go.microsoft.com/fwlink/?linkid=2136406)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a92aa-249">See [https://go.microsoft.com/fwlink/?linkid=2136406](https://go.microsoft.com/fwlink/?linkid=2136406) for more information.</span></span>

<span data-ttu-id="a92aa-250">이 정책은 Microsoft® Active Directory® 도메인에 연결된 Windows 인스턴스에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-250">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="a92aa-251">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="a92aa-251">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="a92aa-252">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="a92aa-252">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="a92aa-253">GP 고유 이름: Update</span><span class="sxs-lookup"><span data-stu-id="a92aa-253">GP unique name: Update</span></span>
- <span data-ttu-id="a92aa-254">GP 이름: 업데이트 정책 재정의</span><span class="sxs-lookup"><span data-stu-id="a92aa-254">GP name: Update policy override</span></span>
- <span data-ttu-id="a92aa-255">GP 경로:</span><span class="sxs-lookup"><span data-stu-id="a92aa-255">GP path:</span></span> 
  - <span data-ttu-id="a92aa-256">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a92aa-256">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="a92aa-257">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="a92aa-257">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="a92aa-258">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="a92aa-258">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="a92aa-259">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="a92aa-259">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="a92aa-260">GP ADMX 파일 이름: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="a92aa-260">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="a92aa-261">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="a92aa-261">Windows Registry Settings</span></span>
- <span data-ttu-id="a92aa-262">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="a92aa-262">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="a92aa-263">값 이름:</span><span class="sxs-lookup"><span data-stu-id="a92aa-263">Value Name:</span></span> 
  - <span data-ttu-id="a92aa-264">(Stable): Update{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="a92aa-264">(Stable): Update{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="a92aa-265">(Beta): Update{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="a92aa-265">(Beta): Update{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="a92aa-266">(Canary): Update{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="a92aa-266">(Canary): Update{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="a92aa-267">(Dev): Update{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="a92aa-267">(Dev): Update{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="a92aa-268">값 형식: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="a92aa-268">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="a92aa-269">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="a92aa-269">Example value:</span></span>
```
always allow updates 0x00000001
Automatic silent updates only 0x00000003
manual updates only 0x00000002
updates disabled 0x00000000
```
[<span data-ttu-id="a92aa-270">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="a92aa-270">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="allowsxs"></a><span data-ttu-id="a92aa-271">Allowsxs</span><span class="sxs-lookup"><span data-stu-id="a92aa-271">Allowsxs</span></span>
#### <a name="allow-microsoft-edge-side-by-side-browser-experience"></a><span data-ttu-id="a92aa-272">Microsoft Edge 함께 사용 브라우저 환경 허용</span><span class="sxs-lookup"><span data-stu-id="a92aa-272">Allow Microsoft Edge Side by Side browser experience</span></span>
><span data-ttu-id="a92aa-273">Microsoft Edge 업데이트 1.2.145.5 이상</span><span class="sxs-lookup"><span data-stu-id="a92aa-273">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <a name="description"></a><span data-ttu-id="a92aa-274">설명</span><span class="sxs-lookup"><span data-stu-id="a92aa-274">Description</span></span>
<span data-ttu-id="a92aa-275">이 정책은 사용자가 Microsoft Edge(Edge HTML) 및 Microsoft Edge(Chromium 기반)을 함께 실행할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-275">This policy lets a user run Microsoft Edge (Edge HTML) and Microsoft Edge (Chromium-based) side-by-side.</span></span>

<span data-ttu-id="a92aa-276">이 정책을 "구성되지 않음"으로 설정하면 Microsoft Edge(Chromium 기반) 안정 채널 및 2019년 11월 보안 업데이트가 설치된 후 Microsoft Edge(Chromium 기반)가 Microsoft Edge(Edge HTML)를 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-276">If this policy is set to “Not configured”, Microsoft Edge (Chromium-based) will replace Microsoft Edge (Edge HTML) after the Microsoft Edge (Chromium-based) stable channel and the November 2019 security updates are installed.</span></span>  <span data-ttu-id="a92aa-277">이는 "사용 안 함" 설정과 동일한 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-277">This is the same behavior as the “Disabled” setting.</span></span>

<span data-ttu-id="a92aa-278">"사용 안 함" 설정은 함께 사용 환경을 차단하고 Microsoft Edge(Chromium 기반) 안정 채널 및 2019년 11월 보안 업데이트가 설치된 후 Microsoft Edge(Chromium 기반)가 Microsoft Edge(Edge HTML)를 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-278">The “Disabled” setting blocks a side-by-side experience and Microsoft Edge (Chromium-based) will replace Microsoft Edge (Edge HTML) after the Microsoft Edge (Chromium-based) stable channel and the November 2019 security updates are installed.</span></span>  <span data-ttu-id="a92aa-279">이는 "구성되지 않음" 설정과 동일한 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-279">This is the same behavior as the “Not Configured” setting.</span></span>

<span data-ttu-id="a92aa-280">이 정책을 "사용"으로 설정하면 Microsoft Edge(Chromium 기반)이 설치된 후 Microsoft Edge(Chromium 기반)와 Microsoft Edge(Edge HTML)를 함께 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-280">When this policy is “Enabled”, Microsoft Edge (Chromium-based) and Microsoft Edge (Edge HTML) can run side-by-side after Microsoft Edge (Chromium-based) is installed.</span></span>

<span data-ttu-id="a92aa-281">이 그룹 정책을 적용하려면 Windows 업데이트가 Microsoft Edge(Chromium 기반)를 자동으로 설치하기 전에 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-281">For this group policy to take affect, it must be configured before the automatic install of Microsoft Edge (Chromium-based) by Windows Update.</span></span> <span data-ttu-id="a92aa-282">참고: 사용자는 Microsoft Edge(Chromium 기반) 차단 도구 키트를 사용하여 Microsoft Edge(Chromium 기반) 자동 업데이트를 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-282">Note: A user can block the automatic update of Microsoft Edge (Chromium-based) by using the Microsoft Edge (Chromium-based) Blocker Toolkit.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="a92aa-283">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="a92aa-283">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="a92aa-284">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="a92aa-284">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="a92aa-285">GP 고유 이름: Allowsxs</span><span class="sxs-lookup"><span data-stu-id="a92aa-285">GP unique name: Allowsxs</span></span>
- <span data-ttu-id="a92aa-286">GP 이름: Microsoft Edge 함께 사용 브라우저 환경 허용</span><span class="sxs-lookup"><span data-stu-id="a92aa-286">GP name: Allow Microsoft Edge Side by Side browser experience</span></span>
- <span data-ttu-id="a92aa-287">GP 경로: 관리 템플릿/Microsoft Edge 업데이트/응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="a92aa-287">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="a92aa-288">GP ADMX 파일 이름: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="a92aa-288">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="a92aa-289">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="a92aa-289">Windows Registry Settings</span></span>
- <span data-ttu-id="a92aa-290">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="a92aa-290">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="a92aa-291">값 이름: Allowsxs</span><span class="sxs-lookup"><span data-stu-id="a92aa-291">Value Name: Allowsxs</span></span>
- <span data-ttu-id="a92aa-292">값 형식: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="a92aa-292">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="a92aa-293">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="a92aa-293">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="a92aa-294">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="a92aa-294">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="createdesktopshortcutdefault"></a><span data-ttu-id="a92aa-295">CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="a92aa-295">CreateDesktopShortcutDefault</span></span>
#### <a name="prevent-desktop-shortcut-creation-upon-install-default"></a><span data-ttu-id="a92aa-296">기본 설치 시 데스크톱 바로 가기 만들기 방지</span><span class="sxs-lookup"><span data-stu-id="a92aa-296">Prevent Desktop Shortcut creation upon install default</span></span>
><span data-ttu-id="a92aa-297">Microsoft Edge 업데이트 1.3.128.0 이상</span><span class="sxs-lookup"><span data-stu-id="a92aa-297">Microsoft Edge Update 1.3.128.0 and later</span></span>

#### <a name="description"></a><span data-ttu-id="a92aa-298">설명</span><span class="sxs-lookup"><span data-stu-id="a92aa-298">Description</span></span>
<span data-ttu-id="a92aa-299">Microsoft Edge가 설치된 경우 데스크톱 바로 가기를 만들기 위한 모든 채널에 대한 기본 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-299">Lets you specify the default behavior for all channels for creating a desktop shortcut when Microsoft Edge is installed.</span></span>

  <span data-ttu-id="a92aa-300">이 정책을 사용하도록 설정하는 경우 Microsoft Edge가 설치될 때 데스크톱 바로 가기가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-300">If you enable this policy a desktop shortcut is created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="a92aa-301">이 정책을 사용하지 않도록 설정하는 경우 Microsoft Edge가 설치될 때 데스크톱 바로 가기가 만들어지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-301">If you disable this policy, no desktop shortcut will be created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="a92aa-302">이 정책을 구성하지 않으면 Microsoft Edge로의 데스크톱 바로 가기가 설치 도중에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-302">If you don’t configure this policy a desktop shortcut to Microsoft Edge will be created during installation.</span></span>
<span data-ttu-id="a92aa-303">Microsoft Edge가 이미 설치되어 있는 경우 이 정책은 아무런 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-303">If Microsoft Edge is already installed, this policy will have no effect.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="a92aa-304">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="a92aa-304">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="a92aa-305">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="a92aa-305">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="a92aa-306">GP 고유 이름: CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="a92aa-306">GP unique name: CreateDesktopShortcutDefault</span></span>
- <span data-ttu-id="a92aa-307">GP 이름: 기본값을 설치 시 데스크톱 바로 가기 만들기를 방지</span><span class="sxs-lookup"><span data-stu-id="a92aa-307">GP name: Prevent Desktop Shortcut creation upon install default</span></span>
- <span data-ttu-id="a92aa-308">GP 경로: 관리 템플릿/Microsoft Edge 업데이트/응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="a92aa-308">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="a92aa-309">GP ADMX 파일 이름: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="a92aa-309">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="a92aa-310">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="a92aa-310">Windows Registry Settings</span></span>
- <span data-ttu-id="a92aa-311">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="a92aa-311">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="a92aa-312">값 이름: CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="a92aa-312">Value Name: CreateDesktopShortcutDefault</span></span>
- <span data-ttu-id="a92aa-313">값 형식: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="a92aa-313">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="a92aa-314">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="a92aa-314">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="a92aa-315">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="a92aa-315">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="createdesktopshortcut"></a><span data-ttu-id="a92aa-316">CreateDesktopShortcut</span><span class="sxs-lookup"><span data-stu-id="a92aa-316">CreateDesktopShortcut</span></span>
#### <a name="prevent-desktop-shortcut-creation-upon-install"></a><span data-ttu-id="a92aa-317">설치 시 데스크톱 바로 가기 만들기를 방지</span><span class="sxs-lookup"><span data-stu-id="a92aa-317">Prevent Desktop Shortcut creation upon install</span></span>
><span data-ttu-id="a92aa-318">Microsoft Edge 업데이트 1.3.128.0 이상</span><span class="sxs-lookup"><span data-stu-id="a92aa-318">Microsoft Edge Update 1.3.128.0 and later</span></span>

#### <a name="description"></a><span data-ttu-id="a92aa-319">설명</span><span class="sxs-lookup"><span data-stu-id="a92aa-319">Description</span></span>
<span data-ttu-id="a92aa-320">이 정책을 사용하도록 설정하는 경우 Microsoft Edge가 설치될 때 데스크톱 바로 가기가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-320">If you enable this policy a desktop shortcut is created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="a92aa-321">이 정책을 사용하지 않도록 설정하는 경우 Microsoft Edge가 설치될 때 데스크톱 바로 가기가 만들어지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-321">If you disable this policy, no desktop shortcut will be created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="a92aa-322">이 정책을 구성하지 않으면 Microsoft Edge로의 데스크톱 바로 가기가 설치 도중에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-322">If you don’t configure this policy a desktop shortcut to Microsoft Edge will be created during installation.</span></span>
<span data-ttu-id="a92aa-323">Microsoft Edge가 이미 설치되어 있는 경우 이 정책은 아무런 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-323">If Microsoft Edge is already installed, this policy will have no effect.</span></span>

  <span data-ttu-id="a92aa-324">채널에 대한 이 정책을 구성하지 않는 경우 '[설치시 바탕 화면 바로 가기 만들기 방지 기본](#createdesktopshortcutdefault)' 정책 구성에 따라 Microsoft Edge 설치시 바로 가기 만들기를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-324">If you don't configure this policy for a channel, the '[Prevent Desktop Shortcut creation upon install default](#createdesktopshortcutdefault)' policy configuration determines shortcut creation when Microsoft Edge is installed.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="a92aa-325">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="a92aa-325">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="a92aa-326">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="a92aa-326">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="a92aa-327">GP 고유 이름: CreateDesktopShortcut</span><span class="sxs-lookup"><span data-stu-id="a92aa-327">GP unique name: CreateDesktopShortcut</span></span>
- <span data-ttu-id="a92aa-328">GP 이름: 설치 시 데스크톱 바로 가기 만들기를 방지</span><span class="sxs-lookup"><span data-stu-id="a92aa-328">GP name: Prevent Desktop Shortcut creation upon install</span></span>
- <span data-ttu-id="a92aa-329">GP 경로:</span><span class="sxs-lookup"><span data-stu-id="a92aa-329">GP path:</span></span> 
  - <span data-ttu-id="a92aa-330">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a92aa-330">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="a92aa-331">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="a92aa-331">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="a92aa-332">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="a92aa-332">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="a92aa-333">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="a92aa-333">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="a92aa-334">GP ADMX 파일 이름: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="a92aa-334">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="a92aa-335">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="a92aa-335">Windows Registry Settings</span></span>
- <span data-ttu-id="a92aa-336">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="a92aa-336">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="a92aa-337">값 이름:</span><span class="sxs-lookup"><span data-stu-id="a92aa-337">Value Name:</span></span> 
  - <span data-ttu-id="a92aa-338">(안정): CreateDesktopShortcut{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="a92aa-338">(Stable): CreateDesktopShortcut{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="a92aa-339">(베타): CreateDesktopShortcut{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="a92aa-339">(Beta): CreateDesktopShortcut{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="a92aa-340">(카나리아): CreateDesktopShortcut{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="a92aa-340">(Canary): CreateDesktopShortcut{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="a92aa-341">(Dev): CreateDesktopShortcut{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="a92aa-341">(Dev): CreateDesktopShortcut{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="a92aa-342">값 형식: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="a92aa-342">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="a92aa-343">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="a92aa-343">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="a92aa-344">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="a92aa-344">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="rollbacktotargetversion"></a><span data-ttu-id="a92aa-345">RollbackToTargetVersion</span><span class="sxs-lookup"><span data-stu-id="a92aa-345">RollbackToTargetVersion</span></span>
#### <a name="rollback-to-target-version"></a><span data-ttu-id="a92aa-346">대상 버전으로 롤백</span><span class="sxs-lookup"><span data-stu-id="a92aa-346">Rollback to Target version</span></span>
><span data-ttu-id="a92aa-347">Microsoft Edge 업데이트 1.3.133.3 이상</span><span class="sxs-lookup"><span data-stu-id="a92aa-347">Microsoft Edge Update 1.3.133.3 and later</span></span>

#### <a name="description"></a><span data-ttu-id="a92aa-348">설명</span><span class="sxs-lookup"><span data-stu-id="a92aa-348">Description</span></span>
<span data-ttu-id="a92aa-349">Microsoft Edge 업데이트가 '[대상 버전 재정의](#targetversionprefix)'에 표시된 버전으로 Microsoft Edge 설치를 롤백하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-349">Specifies that Microsoft Edge Update should rollback installations of Microsoft Edge to the version indicated in '[Target version override](#targetversionprefix)'.</span></span>

<span data-ttu-id="a92aa-350">'[대상 버전 재정의](#targetversionprefix)'가 설정되고 '[업데이트 정책 재정의](#update)'가 켜짐 상태 중 하나(업데이트 항상 허용, 자동 업데이트만, 수동 업데이트만)로 설정되어 있지 않은 경우에는 이 정책이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-350">This policy has no effect unless '[Target version override](#targetversionprefix)' is set and '[Update policy override](#update)' is set to one of the ON states (Always allow updates, Automatic silent updates only, Manual updates only).</span></span>

<span data-ttu-id="a92aa-351">이 정책을 사용하지 않거나 구성하지 않는 경우 '[대상 버전 재정의](#targetversionprefix)'에서 지정한 것보다 높은 버전이 있는 설치는 그대로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-351">If you disable this policy or don't configure it, installs that have a version higher than that specified by '[Target version override](#targetversionprefix)' will be left as-is.</span></span>

<span data-ttu-id="a92aa-352">이 정책을 사용하면 '[대상 버전 재정의](#targetversionprefix)'에서 지정한 것보다 높은 현재 버전이 있는 설치는 대상 버전으로 다운그레이드됩니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-352">If you enable this policy, installs that have a current version higher than specified by the '[Target version override](#targetversionprefix)' will be downgraded to the target version.</span></span>

<span data-ttu-id="a92aa-353">최신 버전의 Microsoft Edge 브라우저를 설치하여 최신 보안 업데이트를 통해 보호하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-353">We recommend that users install the latest version of the Microsoft Edge browser to ensure protection by the latest security updates.</span></span> <span data-ttu-id="a92aa-354">이전 버전으로 롤백하면 알려진 보안 문제에 노출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-354">Rollback to an earlier version risks exposure to known security issues.</span></span> <span data-ttu-id="a92aa-355">이 정책은 Microsoft Edge 브라우저 업데이트에서 문제를 해결하는 임시 해결 방법으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-355">This policy is meant to be used as a temporary fix to address issues in a Microsoft Edge browser update.</span></span>

<span data-ttu-id="a92aa-356">브라우저 버전을 일시적으로 롤백하려면 먼저 조직의 모든 사용자에 대해 동기화([https://go.microsoft.com/fwlink/?linkid=2133032](https://go.microsoft.com/fwlink/?linkid=2133032))를 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-356">Before temporarily rolling back your browser version, we recommend that you turn on Sync ([https://go.microsoft.com/fwlink/?linkid=2133032](https://go.microsoft.com/fwlink/?linkid=2133032)) for all users in your organization.</span></span> <span data-ttu-id="a92aa-357">동기화를 설정하지 않은 경우 영구적 검색 데이터 손실이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-357">If you don't turn on Sync, there is a risk of permanent browsing data loss.</span></span> <span data-ttu-id="a92aa-358">귀하의 책임하에 이 정책을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="a92aa-358">Use this policy at your own risk.</span></span>

<span data-ttu-id="a92aa-359">참고: 롤백에 사용할 수 있는 모든 버전은 [https://aka.ms/EdgeEnterprise](https://aka.ms/EdgeEnterprise)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-359">Note: All versions available for rollback can be viewed here [https://aka.ms/EdgeEnterprise](https://aka.ms/EdgeEnterprise).</span></span>

<span data-ttu-id="a92aa-360">이 정책은 Microsoft Edge 버전 86 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-360">This policy applies to Microsoft Edge version 86 or later.</span></span>

<span data-ttu-id="a92aa-361">자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2133918](https://go.microsoft.com/fwlink/?linkid=2133918)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a92aa-361">See [https://go.microsoft.com/fwlink/?linkid=2133918](https://go.microsoft.com/fwlink/?linkid=2133918) for more information.</span></span>

<span data-ttu-id="a92aa-362">이 정책은 Microsoft® Active Directory® 도메인에 연결된 Windows 인스턴스에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-362">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="a92aa-363">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="a92aa-363">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="a92aa-364">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="a92aa-364">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="a92aa-365">GP 고유 이름: RollbackToTargetVersion</span><span class="sxs-lookup"><span data-stu-id="a92aa-365">GP unique name: RollbackToTargetVersion</span></span>
- <span data-ttu-id="a92aa-366">GP 이름: 대상 버전으로 롤백</span><span class="sxs-lookup"><span data-stu-id="a92aa-366">GP name: Rollback to Target version</span></span>
- <span data-ttu-id="a92aa-367">GP 경로:</span><span class="sxs-lookup"><span data-stu-id="a92aa-367">GP path:</span></span> 
  - <span data-ttu-id="a92aa-368">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a92aa-368">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="a92aa-369">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="a92aa-369">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="a92aa-370">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="a92aa-370">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="a92aa-371">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="a92aa-371">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="a92aa-372">GP ADMX 파일 이름: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="a92aa-372">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="a92aa-373">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="a92aa-373">Windows Registry Settings</span></span>
- <span data-ttu-id="a92aa-374">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="a92aa-374">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="a92aa-375">값 이름:</span><span class="sxs-lookup"><span data-stu-id="a92aa-375">Value Name:</span></span> 
  - <span data-ttu-id="a92aa-376">(안정): RollbackToTargetVersion{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="a92aa-376">(Stable): RollbackToTargetVersion{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="a92aa-377">(베타): RollbackToTargetVersion{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="a92aa-377">(Beta): RollbackToTargetVersion{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="a92aa-378">(Canary): RollbackToTargetVersion{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="a92aa-378">(Canary): RollbackToTargetVersion{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="a92aa-379">(Dev): RollbackToTargetVersion{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="a92aa-379">(Dev): RollbackToTargetVersion{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="a92aa-380">값 형식: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="a92aa-380">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="a92aa-381">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="a92aa-381">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="a92aa-382">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="a92aa-382">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="targetversionprefix"></a><span data-ttu-id="a92aa-383">TargetVersionPrefix</span><span class="sxs-lookup"><span data-stu-id="a92aa-383">TargetVersionPrefix</span></span>
#### <a name="target-version-override"></a><span data-ttu-id="a92aa-384">대상 버전 재정의</span><span class="sxs-lookup"><span data-stu-id="a92aa-384">Target version override</span></span>
><span data-ttu-id="a92aa-385">Microsoft Edge 업데이트 1.3.119.43 이상</span><span class="sxs-lookup"><span data-stu-id="a92aa-385">Microsoft Edge Update 1.3.119.43 and later</span></span>

#### <a name="description"></a><span data-ttu-id="a92aa-386">설명</span><span class="sxs-lookup"><span data-stu-id="a92aa-386">Description</span></span>
<span data-ttu-id="a92aa-387">이 정책을 사용하도록 설정하고 자동 업데이트를 사용하도록 설정하면 Microsoft Edge는 이 정책 값이 지정하는 버전으로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-387">When this policy is enabled, and auto-update is enabled, Microsoft Edge will be updated to the version specified by this policy value.</span></span>

<span data-ttu-id="a92aa-388">정책 값은 특정 Microsoft Edge 버전(예: 83.0.499.12) 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-388">The policy value must be a specific Microsoft Edge version, e.g. 83.0.499.12.</span></span>

<span data-ttu-id="a92aa-389">장치에 지정된 값보다 더 최신 버전의 Microsoft Edge가 있는 경우 Microsoft Edge는 최신 버전을 유지하고 지정된 버전으로 다운그레이드되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-389">If a device has newer version of Microsoft Edge than the value specified, Microsoft Edge will remain on the newer version and not downgrade to the specified version.</span></span>

<span data-ttu-id="a92aa-390">지정된 버전이 존재하지 않거나 형식이 잘못된 경우 Microsoft Edge는 현재 버전을 유지하고 이후 버전으로 자동 업데이트되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-390">If the specified version does not exist, or is improperly formatted, then Microsoft Edge will remain on its current version and not update to future versions automatically.</span></span>

<span data-ttu-id="a92aa-391">자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2136707](https://go.microsoft.com/fwlink/?linkid=2136707)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a92aa-391">See [https://go.microsoft.com/fwlink/?linkid=2136707](https://go.microsoft.com/fwlink/?linkid=2136707) for more information.</span></span>

<span data-ttu-id="a92aa-392">이 정책은 Microsoft® Active Directory® 도메인에 연결된 Windows 인스턴스에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-392">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="a92aa-393">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="a92aa-393">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="a92aa-394">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="a92aa-394">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="a92aa-395">GP 고유 이름: TargetVersionPrefix</span><span class="sxs-lookup"><span data-stu-id="a92aa-395">GP unique name: TargetVersionPrefix</span></span>
- <span data-ttu-id="a92aa-396">GP 이름: 대상 버전 재정의</span><span class="sxs-lookup"><span data-stu-id="a92aa-396">GP name: Target version override</span></span>
- <span data-ttu-id="a92aa-397">GP 경로:</span><span class="sxs-lookup"><span data-stu-id="a92aa-397">GP path:</span></span> 
  - <span data-ttu-id="a92aa-398">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a92aa-398">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="a92aa-399">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="a92aa-399">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="a92aa-400">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="a92aa-400">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="a92aa-401">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="a92aa-401">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="a92aa-402">GP ADMX 파일 이름: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="a92aa-402">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="a92aa-403">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="a92aa-403">Windows Registry Settings</span></span>
- <span data-ttu-id="a92aa-404">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="a92aa-404">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="a92aa-405">값 이름:</span><span class="sxs-lookup"><span data-stu-id="a92aa-405">Value Name:</span></span> 
  - <span data-ttu-id="a92aa-406">(Stable): TargetVersionPrefix{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="a92aa-406">(Stable): TargetVersionPrefix{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="a92aa-407">(Beta): TargetVersionPrefix{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="a92aa-407">(Beta): TargetVersionPrefix{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="a92aa-408">(Canary): TargetVersionPrefix{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="a92aa-408">(Canary): TargetVersionPrefix{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="a92aa-409">(Dev): TargetVersionPrefix{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="a92aa-409">(Dev): TargetVersionPrefix{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="a92aa-410">값 형식: REG_SZ</span><span class="sxs-lookup"><span data-stu-id="a92aa-410">Value Type: REG_SZ</span></span>
##### <a name="example-value"></a><span data-ttu-id="a92aa-411">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="a92aa-411">Example value:</span></span>
```
83.0.499.12
```
[<span data-ttu-id="a92aa-412">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="a92aa-412">Back to top</span></span>](#microsoft-edge---update-policies)


## <a name="preferences-policies"></a><span data-ttu-id="a92aa-413">기본 설정 정책</span><span class="sxs-lookup"><span data-stu-id="a92aa-413">Preferences policies</span></span>

[<span data-ttu-id="a92aa-414">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="a92aa-414">Back to top</span></span>](#microsoft-edge---update-policies)
### <a name="autoupdatecheckperiodminutes"></a><span data-ttu-id="a92aa-415">AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="a92aa-415">AutoUpdateCheckPeriodMinutes</span></span>
#### <a name="auto-update-check-period-override"></a><span data-ttu-id="a92aa-416">자동 업데이트 확인 기간 재정의</span><span class="sxs-lookup"><span data-stu-id="a92aa-416">Auto-update check period override</span></span>
><span data-ttu-id="a92aa-417">Microsoft Edge 업데이트 1.2.145.5 이상</span><span class="sxs-lookup"><span data-stu-id="a92aa-417">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <a name="description"></a><span data-ttu-id="a92aa-418">설명</span><span class="sxs-lookup"><span data-stu-id="a92aa-418">Description</span></span>
<span data-ttu-id="a92aa-419">이 정책을 사용하도록 설정하면 자동 업데이트 확인 최소 간격(분) 값을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-419">If enabled, this policy lets you set a value for the minimum number of minutes between automatic update checks.</span></span> <span data-ttu-id="a92aa-420">그렇지 않으면 기본적으로 자동 업데이트는 10시간마다 업데이트를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-420">Otherwise, by default, auto-update checks for updates every 10 hours.</span></span>

  <span data-ttu-id="a92aa-421">모든 자동 업데이트 확인을 사용하지 않도록 설정하려면 이 값을 0으로 설정합니다(권장하지 않음).</span><span class="sxs-lookup"><span data-stu-id="a92aa-421">If you want to disable all auto-update checks, set the value to 0 (not recommended).</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="a92aa-422">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="a92aa-422">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="a92aa-423">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="a92aa-423">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="a92aa-424">GP 고유 이름: AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="a92aa-424">GP unique name: AutoUpdateCheckPeriodMinutes</span></span>
- <span data-ttu-id="a92aa-425">GP 이름: 자동 업데이트 확인 기간 재정의</span><span class="sxs-lookup"><span data-stu-id="a92aa-425">GP name: Auto-update check period override</span></span>
- <span data-ttu-id="a92aa-426">GP 경로: 관리 템플릿/Microsoft Edge 업데이트/기본 설정</span><span class="sxs-lookup"><span data-stu-id="a92aa-426">GP path: Administrative Templates/Microsoft Edge Update/Preferences</span></span>
- <span data-ttu-id="a92aa-427">GP ADMX 파일 이름: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="a92aa-427">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="a92aa-428">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="a92aa-428">Windows Registry Settings</span></span>
- <span data-ttu-id="a92aa-429">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="a92aa-429">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="a92aa-430">값 이름: AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="a92aa-430">Value Name: AutoUpdateCheckPeriodMinutes</span></span>
- <span data-ttu-id="a92aa-431">값 형식: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="a92aa-431">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="a92aa-432">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="a92aa-432">Example value:</span></span>
```
0x00000578
```
[<span data-ttu-id="a92aa-433">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="a92aa-433">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="updatessuppressed"></a><span data-ttu-id="a92aa-434">UpdatesSuppressed</span><span class="sxs-lookup"><span data-stu-id="a92aa-434">UpdatesSuppressed</span></span>
#### <a name="time-period-in-each-day-to-suppress-auto-update-check"></a><span data-ttu-id="a92aa-435">매일 자동 업데이트 확인 억제 기간</span><span class="sxs-lookup"><span data-stu-id="a92aa-435">Time period in each day to suppress auto-update check</span></span>
><span data-ttu-id="a92aa-436">Microsoft Edge 업데이트 1.3.33.5 이상</span><span class="sxs-lookup"><span data-stu-id="a92aa-436">Microsoft Edge Update 1.3.33.5 and later</span></span>

#### <a name="description"></a><span data-ttu-id="a92aa-437">설명</span><span class="sxs-lookup"><span data-stu-id="a92aa-437">Description</span></span>
<span data-ttu-id="a92aa-438">이 정책을 사용하도록 설정하면 업데이트 확인이 시:분부터 시작하여 기간(분) 동안 억제됩니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-438">If you enable this policy, update checks are suppressed each day starting at Hour:Minute for a period of Duration (in minutes).</span></span> <span data-ttu-id="a92aa-439">기간은 일광 절약 시간에 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-439">Duration isn't affected by daylight saving time.</span></span> <span data-ttu-id="a92aa-440">예를 들어 시작 시간이 22:00이고 기간이 480분인 경우 업데이트는 이 기간 동안 일광 절약 시간제가 시작하거나 종료하는지 관계없이 정확히 8시간 동안 억제됩니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-440">For example, if the start time is 22:00 and the duration is 480 minutes, updates will be suppressed for exactly 8 hours, regardless of whether daylight saving time starts or ends during this period.</span></span>

  <span data-ttu-id="a92aa-441">이 정책을 사용하지 않도록 설정하거나 구성하지 않으면 특정 기간 동안 업데이트 검사가 억제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-441">If you disable or don't configure this policy, update checks aren't suppressed during any specific period.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="a92aa-442">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="a92aa-442">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="a92aa-443">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="a92aa-443">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="a92aa-444">GP 고유 이름: UpdatesSuppressed</span><span class="sxs-lookup"><span data-stu-id="a92aa-444">GP unique name: UpdatesSuppressed</span></span>
- <span data-ttu-id="a92aa-445">GP 이름: 매일 자동 업데이트 확인 억제 기간</span><span class="sxs-lookup"><span data-stu-id="a92aa-445">GP name: Time period in each day to suppress auto-update check</span></span>
  - <span data-ttu-id="a92aa-446">Options { Hour, Minute, Duration }</span><span class="sxs-lookup"><span data-stu-id="a92aa-446">Options { Hour, Minute, Duration }</span></span>
- <span data-ttu-id="a92aa-447">GP 경로: 관리 템플릿/Microsoft Edge 업데이트/기본 설정</span><span class="sxs-lookup"><span data-stu-id="a92aa-447">GP path: Administrative Templates/Microsoft Edge Update/Preferences</span></span>
- <span data-ttu-id="a92aa-448">GP ADMX 파일 이름: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="a92aa-448">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="a92aa-449">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="a92aa-449">Windows Registry Settings</span></span>
- <span data-ttu-id="a92aa-450">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="a92aa-450">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="a92aa-451">값 이름:</span><span class="sxs-lookup"><span data-stu-id="a92aa-451">Value Name:</span></span> 
  - <span data-ttu-id="a92aa-452">UpdatesSuppressedDurationMin</span><span class="sxs-lookup"><span data-stu-id="a92aa-452">UpdatesSuppressedDurationMin</span></span>
  - <span data-ttu-id="a92aa-453">UpdatesSuppressedStartHour</span><span class="sxs-lookup"><span data-stu-id="a92aa-453">UpdatesSuppressedStartHour</span></span>
  - <span data-ttu-id="a92aa-454">UpdatesSuppressedStartMin</span><span class="sxs-lookup"><span data-stu-id="a92aa-454">UpdatesSuppressedStartMin</span></span>
- <span data-ttu-id="a92aa-455">값 형식: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="a92aa-455">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="a92aa-456">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="a92aa-456">Example value:</span></span>
```
duration   : 0x0000003c
start hour : 0x00000001
start min  : 0x00000002
```
[<span data-ttu-id="a92aa-457">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="a92aa-457">Back to top</span></span>](#microsoft-edge---update-policies)


## <a name="proxy-server-policies"></a><span data-ttu-id="a92aa-458">프록시 서버 정책</span><span class="sxs-lookup"><span data-stu-id="a92aa-458">Proxy Server policies</span></span>

[<span data-ttu-id="a92aa-459">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="a92aa-459">Back to top</span></span>](#microsoft-edge---update-policies)
### <a name="proxymode"></a><span data-ttu-id="a92aa-460">ProxyMode</span><span class="sxs-lookup"><span data-stu-id="a92aa-460">ProxyMode</span></span>
#### <a name="choose-how-to-specify-proxy-server-settings"></a><span data-ttu-id="a92aa-461">프록시 서버 설정 지정 방법 선택</span><span class="sxs-lookup"><span data-stu-id="a92aa-461">Choose how to specify proxy server settings</span></span>
><span data-ttu-id="a92aa-462">Microsoft Edge 업데이트 1.3.21.81 이상</span><span class="sxs-lookup"><span data-stu-id="a92aa-462">Microsoft Edge Update 1.3.21.81 and later</span></span>

#### <a name="description"></a><span data-ttu-id="a92aa-463">설명</span><span class="sxs-lookup"><span data-stu-id="a92aa-463">Description</span></span>
<span data-ttu-id="a92aa-464">Microsoft Edge 업데이트에서 사용되는 프록시 서버 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-464">Allows you to specify the proxy server settings that are used by Microsoft Edge Update.</span></span>

  <span data-ttu-id="a92aa-465">이 정책을 사용하도록 설정하면 다음 프록시 서버 옵션 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-465">If you enable this policy, you can choose between the following proxy server options:</span></span>
   - <span data-ttu-id="a92aa-466">프록시 서버를 사용하지 않도록 선택하고 항상 직접 연결하는 경우 다른 모든 옵션은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-466">If you choose to never use a proxy server and always connect directly, all other options are ignored.</span></span>
   - <span data-ttu-id="a92aa-467">시스템 프록시 설정을 사용하거나 프록시 서버를 자동으로 검색하도록 선택하는 경우 다른 모든 옵션은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-467">If you choose to use system proxy settings or auto-detect the proxy server, all other options are ignored.</span></span>
   - <span data-ttu-id="a92aa-468">고정 서버 프록시 모드를 선택하는 경우에는 ‘[프록시 서버 주소 또는 URL](#proxyserver)’정책에 추가 옵션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-468">If you choose fixed server proxy mode, you can specify further options in '[Address or URL of proxy server](#proxyserver)' policy.</span></span>
   - <span data-ttu-id="a92aa-469">.pac 프록시 스크립트를 사용하도록 선택하는 경우 ‘[프록시 .pac 파일 URL](#proxypacurl)’ 정책에서 스크립트의 URL을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-469">If you choose to use a .pac proxy script, you must specify the URL for the script in '[URL to a proxy .pac file](#proxypacurl)' policy.</span></span>

  <span data-ttu-id="a92aa-470">이 정책을 사용하도록 설정하면 조직의 사용자가 Microsoft Edge 업데이트에서 프록시 설정을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-470">If you enable this policy, users in your organization can't change the proxy settings in Microsoft Edge Update.</span></span>

  <span data-ttu-id="a92aa-471">이 정책을 사용하지 않도록 설정하거나 구성하지 않으면 프록시 서버 설정이 구성되지 않지만 조직의사용자가 Microsoft Edge 업데이트에 대한 고유한 프록시 설정을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-471">If you disable or don't configure this policy, no proxy server settings are configured, but users in your organization can choose their own proxy settings for Microsoft Edge Update.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="a92aa-472">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="a92aa-472">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="a92aa-473">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="a92aa-473">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="a92aa-474">GP 고유 이름: ProxyMode</span><span class="sxs-lookup"><span data-stu-id="a92aa-474">GP unique name: ProxyMode</span></span>
- <span data-ttu-id="a92aa-475">GP 이름: 프록시 서버 설정 지정 방법 선택</span><span class="sxs-lookup"><span data-stu-id="a92aa-475">GP name: Choose how to specify proxy server settings</span></span>
- <span data-ttu-id="a92aa-476">GP 경로: 관리 템플릿/Microsoft Edge 업데이트/프록시 서버</span><span class="sxs-lookup"><span data-stu-id="a92aa-476">GP path: Administrative Templates/Microsoft Edge Update/Proxy Server</span></span>
- <span data-ttu-id="a92aa-477">GP ADMX 파일 이름: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="a92aa-477">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="a92aa-478">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="a92aa-478">Windows Registry Settings</span></span>
- <span data-ttu-id="a92aa-479">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="a92aa-479">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="a92aa-480">값 이름: ProxyMode</span><span class="sxs-lookup"><span data-stu-id="a92aa-480">Value Name: ProxyMode</span></span>
- <span data-ttu-id="a92aa-481">값 형식: REG_SZ</span><span class="sxs-lookup"><span data-stu-id="a92aa-481">Value Type: REG_SZ</span></span>
##### <a name="example-value"></a><span data-ttu-id="a92aa-482">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="a92aa-482">Example value:</span></span>
```
fixed_servers
```
[<span data-ttu-id="a92aa-483">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="a92aa-483">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="proxypacurl"></a><span data-ttu-id="a92aa-484">ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="a92aa-484">ProxyPacUrl</span></span>
#### <a name="url-to-a-proxy-pac-file"></a><span data-ttu-id="a92aa-485">프록시 .pac 파일 URL</span><span class="sxs-lookup"><span data-stu-id="a92aa-485">URL to a proxy .pac file</span></span>
><span data-ttu-id="a92aa-486">Microsoft Edge 업데이트 1.3.21.81 이상</span><span class="sxs-lookup"><span data-stu-id="a92aa-486">Microsoft Edge Update 1.3.21.81 and later</span></span>

#### <a name="description"></a><span data-ttu-id="a92aa-487">설명</span><span class="sxs-lookup"><span data-stu-id="a92aa-487">Description</span></span>
<span data-ttu-id="a92aa-488">PAC(프록시 자동 구성) 파일의 URL을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-488">Allows you to specify a URL for a proxy auto-config (PAC) file.</span></span>

  <span data-ttu-id="a92aa-489">이 정책을 사용하면 PAC 파일의 URL을 지정하여 Microsoft Edge 업데이트가 특정 웹 사이트를 가져오는 데 적합한 프록시 서버를 선택하는 방법을 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-489">If you enable this policy, you can specify a URL for a PAC file to automate how Microsoft Edge Update selects the appropriate proxy server for fetching a particular website.</span></span>

  <span data-ttu-id="a92aa-490">이 정책은 ‘[프록시 서버 설정 지정 방법 선택](#proxymode)’ 정책에서 수동 프록시 설정을 지정한 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-490">This policy is applied only if you have specified manual proxy settings in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>

  <span data-ttu-id="a92aa-491">‘[프록시 서버 설정 지정 방법 선택](#proxymode)‘ 정책에서 수동 이외의 프록시 설정을 선택한 경우 이 정책을 구성하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="a92aa-491">Don't configure this policy if you have selected a proxy setting other than manual in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="a92aa-492">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="a92aa-492">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="a92aa-493">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="a92aa-493">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="a92aa-494">GP 고유 이름: ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="a92aa-494">GP unique name: ProxyPacUrl</span></span>
- <span data-ttu-id="a92aa-495">GP 이름: 프록시 .pac 파일 URL</span><span class="sxs-lookup"><span data-stu-id="a92aa-495">GP name: URL to a proxy .pac file</span></span>
- <span data-ttu-id="a92aa-496">GP 경로: 관리 템플릿/Microsoft Edge 업데이트/프록시 서버</span><span class="sxs-lookup"><span data-stu-id="a92aa-496">GP path: Administrative Templates/Microsoft Edge Update/Proxy Server</span></span>
- <span data-ttu-id="a92aa-497">GP ADMX 파일 이름: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="a92aa-497">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="a92aa-498">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="a92aa-498">Windows Registry Settings</span></span>
- <span data-ttu-id="a92aa-499">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="a92aa-499">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="a92aa-500">값 이름: ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="a92aa-500">Value Name: ProxyPacUrl</span></span>
- <span data-ttu-id="a92aa-501">값 형식: REG_SZ</span><span class="sxs-lookup"><span data-stu-id="a92aa-501">Value Type: REG_SZ</span></span>
##### <a name="example-value"></a><span data-ttu-id="a92aa-502">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="a92aa-502">Example value:</span></span>
```
https://www.microsoft.com
```
[<span data-ttu-id="a92aa-503">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="a92aa-503">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="proxyserver"></a><span data-ttu-id="a92aa-504">ProxyServer</span><span class="sxs-lookup"><span data-stu-id="a92aa-504">ProxyServer</span></span>
#### <a name="address-or-url-of-proxy-server"></a><span data-ttu-id="a92aa-505">프록시 서버 주소 또는 URL</span><span class="sxs-lookup"><span data-stu-id="a92aa-505">Address or URL of proxy server</span></span>
><span data-ttu-id="a92aa-506">Microsoft Edge 업데이트 1.3.21.81 이상</span><span class="sxs-lookup"><span data-stu-id="a92aa-506">Microsoft Edge Update 1.3.21.81 and later</span></span>

#### <a name="description"></a><span data-ttu-id="a92aa-507">설명</span><span class="sxs-lookup"><span data-stu-id="a92aa-507">Description</span></span>
<span data-ttu-id="a92aa-508">Microsoft Edge 업데이트가 사용할 프록시 서버의 URL을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-508">Allows you to specify the URL of the proxy server for Microsoft Edge Update to use.</span></span>

  <span data-ttu-id="a92aa-509">이 정책을 사용하도록 설정하면 조직에서 Microsoft Edge 업데이트가 사용하는 프록시 서버 URL을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-509">If you enable this policy, you can set the proxy server URL used by Microsoft Edge Update in your organization.</span></span>

  <span data-ttu-id="a92aa-510">이 정책은 ‘[프록시 서버 설정 지정 방법 선택](#proxymode)’ 정책에서 수동 프록시 설정을 선택한 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-510">This policy is applied only if you have selected manual proxy settings in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>

  <span data-ttu-id="a92aa-511">‘[프록시 서버 설정 지정 방법 선택](#proxymode)‘ 정책에서 수동 이외의 프록시 설정을 선택한 경우 이 정책을 구성하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="a92aa-511">Don't configure this policy if you have selected a proxy setting other than manual in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="a92aa-512">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="a92aa-512">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="a92aa-513">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="a92aa-513">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="a92aa-514">GP 고유 이름: ProxyServer</span><span class="sxs-lookup"><span data-stu-id="a92aa-514">GP unique name: ProxyServer</span></span>
- <span data-ttu-id="a92aa-515">GP 이름: 프록시 서버 주소 또는 URL</span><span class="sxs-lookup"><span data-stu-id="a92aa-515">GP name: Address or URL of proxy server</span></span>
- <span data-ttu-id="a92aa-516">GP 경로: 관리 템플릿/Microsoft Edge 업데이트/프록시 서버</span><span class="sxs-lookup"><span data-stu-id="a92aa-516">GP path: Administrative Templates/Microsoft Edge Update/Proxy Server</span></span>
- <span data-ttu-id="a92aa-517">GP ADMX 파일 이름: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="a92aa-517">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="a92aa-518">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="a92aa-518">Windows Registry Settings</span></span>
- <span data-ttu-id="a92aa-519">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="a92aa-519">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="a92aa-520">값 이름: ProxyServer</span><span class="sxs-lookup"><span data-stu-id="a92aa-520">Value Name: ProxyServer</span></span>
- <span data-ttu-id="a92aa-521">값 형식: REG_SZ</span><span class="sxs-lookup"><span data-stu-id="a92aa-521">Value Type: REG_SZ</span></span>
##### <a name="example-value"></a><span data-ttu-id="a92aa-522">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="a92aa-522">Example value:</span></span>
```
https://www.microsoft.com
```
[<span data-ttu-id="a92aa-523">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="a92aa-523">Back to top</span></span>](#microsoft-edge---update-policies)


## <a name="microsoft-edge-webview-policies"></a><span data-ttu-id="a92aa-524">Microsoft Edge WebView 정책</span><span class="sxs-lookup"><span data-stu-id="a92aa-524">Microsoft Edge WebView policies</span></span>

[<span data-ttu-id="a92aa-525">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="a92aa-525">Back to top</span></span>](#microsoft-edge---update-policies)
### <a name="install-webview"></a><span data-ttu-id="a92aa-526">설치(WebView)</span><span class="sxs-lookup"><span data-stu-id="a92aa-526">Install (WebView)</span></span>
#### <a name="allow-installation"></a><span data-ttu-id="a92aa-527">설치 허용</span><span class="sxs-lookup"><span data-stu-id="a92aa-527">Allow installation</span></span>
><span data-ttu-id="a92aa-528">Microsoft Edge 업데이트 1.3.127.1 이상</span><span class="sxs-lookup"><span data-stu-id="a92aa-528">Microsoft Edge Update 1.3.127.1 and later</span></span>

#### <a name="description"></a><span data-ttu-id="a92aa-529">설명</span><span class="sxs-lookup"><span data-stu-id="a92aa-529">Description</span></span>
<span data-ttu-id="a92aa-530">Microsoft Edge 업데이트를 사용하여 Microsoft Edge WebView를 설치할 수 있는지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-530">Lets you specify whether Microsoft Edge WebView can be installed using Microsoft Edge Update.</span></span>

  - <span data-ttu-id="a92aa-531">이 정책을 사용하도록 설정하면 사용자가 Microsoft Edge 업데이트를 통해 Microsoft Edge WebView를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-531">If you enable this policy, users can install Microsoft Edge WebView through Microsoft Edge Update.</span></span>
  - <span data-ttu-id="a92aa-532">이 정책을 사용하지 않도록 설정하면 사용자가 Microsoft Edge 업데이트를 통해 Microsoft Edge WebView를 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-532">If you disable this policy, users cannot install Microsoft Edge WebView through Microsoft Edge Update.</span></span>
  - <span data-ttu-id="a92aa-533">이 정책을 구성하지 않으면 ‘[설치 허용 기본](#installdefault)’ 정책 구성이 사용자가 Microsoft Edge 업데이트를 통해 해당 Microsoft Edge Webview를 설치할 수 있는지의 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-533">If you don't configure this policy, the '[Allow installation default](#installdefault)' policy configuration determines whether users can install Microsoft Edge WebView through Microsoft Edge Update.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="a92aa-534">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="a92aa-534">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="a92aa-535">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="a92aa-535">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="a92aa-536">GP 고유 이름: Install</span><span class="sxs-lookup"><span data-stu-id="a92aa-536">GP unique name: Install</span></span>
- <span data-ttu-id="a92aa-537">GP 이름: 설치 허용</span><span class="sxs-lookup"><span data-stu-id="a92aa-537">GP name: Allow installation</span></span>
- <span data-ttu-id="a92aa-538">GP 경로: 관리 템플릿/Microsoft Edge 업데이트/Microsoft Edge WebView</span><span class="sxs-lookup"><span data-stu-id="a92aa-538">GP path: Administrative Templates/Microsoft Edge Update/Microsoft Edge WebView</span></span>
- <span data-ttu-id="a92aa-539">GP ADMX 파일 이름: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="a92aa-539">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="a92aa-540">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="a92aa-540">Windows Registry Settings</span></span>
- <span data-ttu-id="a92aa-541">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="a92aa-541">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="a92aa-542">값 이름:</span><span class="sxs-lookup"><span data-stu-id="a92aa-542">Value Name:</span></span> 
  - <span data-ttu-id="a92aa-543">Install{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}</span><span class="sxs-lookup"><span data-stu-id="a92aa-543">Install{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}</span></span>
- <span data-ttu-id="a92aa-544">값 형식: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="a92aa-544">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="a92aa-545">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="a92aa-545">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="a92aa-546">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="a92aa-546">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="update-webview"></a><span data-ttu-id="a92aa-547">업데이트(WebView)</span><span class="sxs-lookup"><span data-stu-id="a92aa-547">Update (WebView)</span></span>
#### <a name="update-policy-override"></a><span data-ttu-id="a92aa-548">업데이트 정책 재정의</span><span class="sxs-lookup"><span data-stu-id="a92aa-548">Update policy override</span></span>
><span data-ttu-id="a92aa-549">Microsoft Edge 업데이트 1.3.127.1 이상</span><span class="sxs-lookup"><span data-stu-id="a92aa-549">Microsoft Edge Update 1.3.127.1 and later</span></span>

#### <a name="description"></a><span data-ttu-id="a92aa-550">설명</span><span class="sxs-lookup"><span data-stu-id="a92aa-550">Description</span></span>
<span data-ttu-id="a92aa-551">Microsoft Edge WebView에 대해 자동 업데이트를 사용하도록 설정할지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-551">Lets you specify whether or not automatic updates are enabled for Microsoft Edge WebView.</span></span> <span data-ttu-id="a92aa-552">Microsoft Edge WebView는 응용 프로그램에서 웹 콘텐츠를 표시하는 데 사용하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-552">Microsoft Edge WebView is a component used by applications to display web content.</span></span>
<span data-ttu-id="a92aa-553">자동 업데이트는 기본적으로 사용하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-553">Automatic updates are enabled by default.</span></span> <span data-ttu-id="a92aa-554">Microsoft Edge WebView에서 자동 업데이트를 사용하지 않도록 설정하면 이 구성 요소에 종속 된 응용 프로그램과의 호환성 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-554">Disabling automatic updates for Microsoft Edge WebView might cause compatibility issues with applications that depend on this component.</span></span>

  <span data-ttu-id="a92aa-555">이 정책을 사용하도록 설정하면 다음의 옵션을 구성하는 방법에 따라 Microsoft Edge 업데이트가 Microsoft Edge WebView 업데이트를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-555">If you enable this policy, Microsoft Edge Update handles Microsoft Edge WebView updates according to how you configure the following options:</span></span>
  - <span data-ttu-id="a92aa-556">항상 업데이트 허용: 업데이트가 자동으로 다운로드되고 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-556">Always allow updates: Updates are automatically downloaded and applied</span></span>
  - <span data-ttu-id="a92aa-557">업데이트 사용 안 함: 업데이트가 다운로드되거나 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-557">Updates disabled: Updates are never downloaded or applied</span></span>

  <span data-ttu-id="a92aa-558">이 정책을 사용하도록 설정하지 않으면, 업데이트가 자동으로 다운로드되고 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a92aa-558">If you don't enable this policy, updates are automatically downloaded and applied.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="a92aa-559">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="a92aa-559">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="a92aa-560">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="a92aa-560">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="a92aa-561">GP 고유 이름: Update</span><span class="sxs-lookup"><span data-stu-id="a92aa-561">GP unique name: Update</span></span>
- <span data-ttu-id="a92aa-562">GP 이름: 업데이트 정책 재정의</span><span class="sxs-lookup"><span data-stu-id="a92aa-562">GP name: Update policy override</span></span>
- <span data-ttu-id="a92aa-563">GP 경로: 관리 템플릿/Microsoft Edge 업데이트/Microsoft Edge WebView</span><span class="sxs-lookup"><span data-stu-id="a92aa-563">GP path: Administrative Templates/Microsoft Edge Update/Microsoft Edge WebView</span></span>
- <span data-ttu-id="a92aa-564">GP ADMX 파일 이름: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="a92aa-564">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="a92aa-565">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="a92aa-565">Windows Registry Settings</span></span>
- <span data-ttu-id="a92aa-566">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="a92aa-566">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="a92aa-567">값 이름:</span><span class="sxs-lookup"><span data-stu-id="a92aa-567">Value Name:</span></span> 
  - <span data-ttu-id="a92aa-568">Update{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}</span><span class="sxs-lookup"><span data-stu-id="a92aa-568">Update{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}</span></span>
- <span data-ttu-id="a92aa-569">값 형식: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="a92aa-569">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="a92aa-570">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="a92aa-570">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="a92aa-571">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="a92aa-571">Back to top</span></span>](#microsoft-edge---update-policies)


## <a name="see-also"></a><span data-ttu-id="a92aa-572">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a92aa-572">See also</span></span>
  - [<span data-ttu-id="a92aa-573">Microsoft Edge 구성</span><span class="sxs-lookup"><span data-stu-id="a92aa-573">Configuring Microsoft Edge</span></span>](configure-microsoft-edge.md)
  - [<span data-ttu-id="a92aa-574">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="a92aa-574">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
