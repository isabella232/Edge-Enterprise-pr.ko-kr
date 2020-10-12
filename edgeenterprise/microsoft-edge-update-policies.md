---
title: Microsoft Edge 업데이트 정책 설명서
ms.author: stmoody
author: brianalt-msft
manager: tahills
ms.date: 10/07/2020
audience: ITPro
ms.topic: reference
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
ms.custom: ''
description: Microsoft Edge 업데이트 프로그램에서 지원하는 모든 정책에 대한 설명서
ms.openlocfilehash: feb7859f062ae39e2bbfe08d8e478386defb85cf
ms.sourcegitcommit: 4e6188ade942ca6fd599a4ce1c8e0d90d3d03399
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2020
ms.locfileid: "11105572"
---
# <span data-ttu-id="1d52c-103">Microsoft Edge - 업데이트 정책</span><span class="sxs-lookup"><span data-stu-id="1d52c-103">Microsoft Edge - Update policies</span></span>
<span data-ttu-id="1d52c-104">최신 버전의 Microsoft Edge에는 Microsoft Edge가 업데이트되는 방법 및 시기를 제어하는 데 사용할 수 있는 다음과 같은 정책이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-104">The latest version of Microsoft Edge includes the following policies that you can use to control how and when Microsoft Edge is updated.</span></span>

<span data-ttu-id="1d52c-105">Microsoft Edge에서 사용할 수 있는 다른 정책에 대한 자세한 내용은 [Microsoft Edge 브라우저 정책 참조](microsoft-edge-policies.md)를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="1d52c-105">For information about other policies available in Microsoft Edge, check out [Microsoft Edge browser policy reference](microsoft-edge-policies.md)</span></span>
> [!NOTE]
> <span data-ttu-id="1d52c-106">이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-106">This article applies to Microsoft Edge version 77 or later.</span></span>
## <span data-ttu-id="1d52c-107">사용 가능한 정책</span><span class="sxs-lookup"><span data-stu-id="1d52c-107">Available policies</span></span>
<span data-ttu-id="1d52c-108">다음 표에서는 이번 릴리스의 Microsoft Edge에서 사용할 수 있는 모든 업데이트 관련 그룹 정책을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-108">These tables lists all of the update-related group policies available in this release of Microsoft Edge.</span></span> <span data-ttu-id="1d52c-109">특정 정책에 대해 자세히 알아보려면 표의 링크를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="1d52c-109">Use the links in the table to get more details about specific policies.</span></span>

|||
|-|-|
|[<span data-ttu-id="1d52c-110">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="1d52c-110">Applications</span></span>](#applications)|[<span data-ttu-id="1d52c-111">기본 설정</span><span class="sxs-lookup"><span data-stu-id="1d52c-111">Preferences</span></span>](#preferences)|
|[<span data-ttu-id="1d52c-112">프록시 서버</span><span class="sxs-lookup"><span data-stu-id="1d52c-112">Proxy Server</span></span>](#proxy-server)|[<span data-ttu-id="1d52c-113">Microsoft Edge WebView</span><span class="sxs-lookup"><span data-stu-id="1d52c-113">Microsoft Edge WebView</span></span>](#microsoft-edge-webview)|

### [<span data-ttu-id="1d52c-114">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="1d52c-114">Applications</span></span>](#applications-policies)
|<span data-ttu-id="1d52c-115">정책 이름</span><span class="sxs-lookup"><span data-stu-id="1d52c-115">Policy Name</span></span>|<span data-ttu-id="1d52c-116">캡션</span><span class="sxs-lookup"><span data-stu-id="1d52c-116">Caption</span></span>|
|-|-|
|[<span data-ttu-id="1d52c-117">InstallDefault</span><span class="sxs-lookup"><span data-stu-id="1d52c-117">InstallDefault</span></span>](#installdefault)|<span data-ttu-id="1d52c-118">설치 허용 기본값</span><span class="sxs-lookup"><span data-stu-id="1d52c-118">Allow installation default</span></span>|
|[<span data-ttu-id="1d52c-119">UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="1d52c-119">UpdateDefault</span></span>](#updatedefault)|<span data-ttu-id="1d52c-120">업데이트 정책 재정의 기본값</span><span class="sxs-lookup"><span data-stu-id="1d52c-120">Update policy override default</span></span>|
|[<span data-ttu-id="1d52c-121">설치</span><span class="sxs-lookup"><span data-stu-id="1d52c-121">Install</span></span>](#install)|<span data-ttu-id="1d52c-122">설치 허용(채널별)</span><span class="sxs-lookup"><span data-stu-id="1d52c-122">Allow installation (per channel)</span></span>|
|[<span data-ttu-id="1d52c-123">업데이트</span><span class="sxs-lookup"><span data-stu-id="1d52c-123">Update</span></span>](#update)|<span data-ttu-id="1d52c-124">업데이트 정책 재정의(채널별)</span><span class="sxs-lookup"><span data-stu-id="1d52c-124">Update policy override (per channel)</span></span>|
|[<span data-ttu-id="1d52c-125">Allowsxs</span><span class="sxs-lookup"><span data-stu-id="1d52c-125">Allowsxs</span></span>](#allowsxs)|<span data-ttu-id="1d52c-126">Microsoft Edge 함께 사용 브라우저 환경 허용</span><span class="sxs-lookup"><span data-stu-id="1d52c-126">Allow Microsoft Edge Side by Side browser experience</span></span>|
|[<span data-ttu-id="1d52c-127">CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="1d52c-127">CreateDesktopShortcutDefault</span></span>](#createdesktopshortcutdefault)|<span data-ttu-id="1d52c-128">기본 설치 시 데스크톱 바로 가기 만들기 방지</span><span class="sxs-lookup"><span data-stu-id="1d52c-128">Prevent Desktop Shortcut creation upon install default</span></span>|
|[<span data-ttu-id="1d52c-129">CreateDesktopShortcut</span><span class="sxs-lookup"><span data-stu-id="1d52c-129">CreateDesktopShortcut</span></span>](#createdesktopshortcut)|<span data-ttu-id="1d52c-130">설치 시 데스크톱 바로 가기 만들기 방지(채널 당)</span><span class="sxs-lookup"><span data-stu-id="1d52c-130">Prevent Desktop Shortcut creation upon install (per channel)</span></span>|
|[<span data-ttu-id="1d52c-131">RollbackToTargetVersion</span><span class="sxs-lookup"><span data-stu-id="1d52c-131">RollbackToTargetVersion</span></span>](#rollbacktotargetversion)|<span data-ttu-id="1d52c-132">대상 버전으로 롤백(채널당)</span><span class="sxs-lookup"><span data-stu-id="1d52c-132">Rollback to Target version (per channel)</span></span>|
|[<span data-ttu-id="1d52c-133">TargetVersionPrefix</span><span class="sxs-lookup"><span data-stu-id="1d52c-133">TargetVersionPrefix</span></span>](#targetversionprefix)|<span data-ttu-id="1d52c-134">대상 버전 재정의(채널당)</span><span class="sxs-lookup"><span data-stu-id="1d52c-134">Target version override (per channel)</span></span>|

### [<span data-ttu-id="1d52c-135">기본 설정</span><span class="sxs-lookup"><span data-stu-id="1d52c-135">Preferences</span></span>](#preferences-policies)
|<span data-ttu-id="1d52c-136">정책 이름</span><span class="sxs-lookup"><span data-stu-id="1d52c-136">Policy Name</span></span>|<span data-ttu-id="1d52c-137">캡션</span><span class="sxs-lookup"><span data-stu-id="1d52c-137">Caption</span></span>|
|-|-|
|[<span data-ttu-id="1d52c-138">AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="1d52c-138">AutoUpdateCheckPeriodMinutes</span></span>](#autoupdatecheckperiodminutes)|<span data-ttu-id="1d52c-139">자동 업데이트 확인 기간 재정의</span><span class="sxs-lookup"><span data-stu-id="1d52c-139">Auto-update check period override</span></span>|
|[<span data-ttu-id="1d52c-140">UpdatesSuppressed</span><span class="sxs-lookup"><span data-stu-id="1d52c-140">UpdatesSuppressed</span></span>](#updatessuppressed)|<span data-ttu-id="1d52c-141">매일 자동 업데이트 확인 억제 기간</span><span class="sxs-lookup"><span data-stu-id="1d52c-141">Time period in each day to suppress auto-update check</span></span>|

### [<span data-ttu-id="1d52c-142">프록시 서버</span><span class="sxs-lookup"><span data-stu-id="1d52c-142">Proxy Server</span></span>](#proxy-server-policies)
|<span data-ttu-id="1d52c-143">정책 이름</span><span class="sxs-lookup"><span data-stu-id="1d52c-143">Policy Name</span></span>|<span data-ttu-id="1d52c-144">캡션</span><span class="sxs-lookup"><span data-stu-id="1d52c-144">Caption</span></span>|
|-|-|
|[<span data-ttu-id="1d52c-145">ProxyMode</span><span class="sxs-lookup"><span data-stu-id="1d52c-145">ProxyMode</span></span>](#proxymode)|<span data-ttu-id="1d52c-146">프록시 서버 설정 지정 방법 선택</span><span class="sxs-lookup"><span data-stu-id="1d52c-146">Choose how to specify proxy server settings</span></span>|
|[<span data-ttu-id="1d52c-147">ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="1d52c-147">ProxyPacUrl</span></span>](#proxypacurl)|<span data-ttu-id="1d52c-148">프록시 .pac 파일 URL</span><span class="sxs-lookup"><span data-stu-id="1d52c-148">URL to a proxy .pac file</span></span>|
|[<span data-ttu-id="1d52c-149">ProxyServer</span><span class="sxs-lookup"><span data-stu-id="1d52c-149">ProxyServer</span></span>](#proxyserver)|<span data-ttu-id="1d52c-150">프록시 서버 주소 또는 URL</span><span class="sxs-lookup"><span data-stu-id="1d52c-150">Address or URL of proxy server</span></span>|

### [<span data-ttu-id="1d52c-151">Microsoft Edge WebView</span><span class="sxs-lookup"><span data-stu-id="1d52c-151">Microsoft Edge WebView</span></span>](#microsoft-edge-webview-policies)
|<span data-ttu-id="1d52c-152">정책 이름</span><span class="sxs-lookup"><span data-stu-id="1d52c-152">Policy Name</span></span>|<span data-ttu-id="1d52c-153">캡션</span><span class="sxs-lookup"><span data-stu-id="1d52c-153">Caption</span></span>|
|-|-|
|[<span data-ttu-id="1d52c-154">설치</span><span class="sxs-lookup"><span data-stu-id="1d52c-154">Install</span></span>](#install-webview)|<span data-ttu-id="1d52c-155">설치 허용</span><span class="sxs-lookup"><span data-stu-id="1d52c-155">Allow installation</span></span>|
|[<span data-ttu-id="1d52c-156">업데이트</span><span class="sxs-lookup"><span data-stu-id="1d52c-156">Update</span></span>](#update-webview)|<span data-ttu-id="1d52c-157">업데이트 정책 재정의</span><span class="sxs-lookup"><span data-stu-id="1d52c-157">Update policy override</span></span>|

## <span data-ttu-id="1d52c-158">응용 프로그램 정책</span><span class="sxs-lookup"><span data-stu-id="1d52c-158">Applications policies</span></span>

[<span data-ttu-id="1d52c-159">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="1d52c-159">Back to top</span></span>](#microsoft-edge---update-policies)
### <span data-ttu-id="1d52c-160">InstallDefault</span><span class="sxs-lookup"><span data-stu-id="1d52c-160">InstallDefault</span></span>
#### <span data-ttu-id="1d52c-161">설치 허용 기본값</span><span class="sxs-lookup"><span data-stu-id="1d52c-161">Allow installation default</span></span>
><span data-ttu-id="1d52c-162">Microsoft Edge 업데이트 1.2.145.5 이상</span><span class="sxs-lookup"><span data-stu-id="1d52c-162">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="1d52c-163">설명</span><span class="sxs-lookup"><span data-stu-id="1d52c-163">Description</span></span>
<span data-ttu-id="1d52c-164">도메인에 가입된 장치에서 Microsoft Edge를 허용하거나 차단하기 위해 모든 채널의 기본 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-164">You can specify the default behavior of all channels to allow or block Microsoft Edge on domain-joined devices.</span></span>

<span data-ttu-id="1d52c-165">특정 채널에 대한 ‘[설치 허용](#install)’ 정책을 사용하도록 설정하여 개별 채널에 대한 이 정책을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-165">You can override this policy for individual channels by enabling the '[Allow installation](#install)' policy for specific channels.</span></span>

<span data-ttu-id="1d52c-166">이 정책을 사용하지 않도록 설정하면 Microsoft Edge의 설치가 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-166">If you disable this policy, the installation of Microsoft Edge is blocked.</span></span> <span data-ttu-id="1d52c-167">이는 '[설치 허용](#install)' 정책이 구성되지 않음으로 설정된 경우에만 Microsoft Edge 소프트웨어 설치에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-167">This only affects the installation of Microsoft Edge software when the '[Allow installation](#install)' policy is set to Not Configured.</span></span>

<span data-ttu-id="1d52c-168">이 정책은 Microsoft Edge 업데이트 실행을 금지하거나 사용자가 다른 방법으로 Microsoft Edge 소프트웨어를 설치하는 것을 방지하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-168">This policy doesn't prevent Microsoft Edge Update from running or prevent users from installing Microsoft Edge software using other methods.</span></span>

<span data-ttu-id="1d52c-169">이 정책은 Microsoft® Active Directory® 도메인에 연결된 Windows 인스턴스에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-169">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <span data-ttu-id="1d52c-170">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="1d52c-170">Windows information and settings</span></span>
##### <span data-ttu-id="1d52c-171">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="1d52c-171">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="1d52c-172">GP 고유 이름: InstallDefault</span><span class="sxs-lookup"><span data-stu-id="1d52c-172">GP unique name: InstallDefault</span></span>
- <span data-ttu-id="1d52c-173">GP 이름: 설치 허용 기본값</span><span class="sxs-lookup"><span data-stu-id="1d52c-173">GP name: Allow installation default</span></span>
- <span data-ttu-id="1d52c-174">GP 경로: 관리 템플릿/Microsoft Edge 업데이트/응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="1d52c-174">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="1d52c-175">GP ADMX 파일 이름: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="1d52c-175">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="1d52c-176">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="1d52c-176">Windows Registry Settings</span></span>
- <span data-ttu-id="1d52c-177">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="1d52c-177">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="1d52c-178">값 이름: InstallDefault</span><span class="sxs-lookup"><span data-stu-id="1d52c-178">Value Name: InstallDefault</span></span>
- <span data-ttu-id="1d52c-179">값 형식: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="1d52c-179">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="1d52c-180">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="1d52c-180">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="1d52c-181">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="1d52c-181">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="1d52c-182">UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="1d52c-182">UpdateDefault</span></span>
#### <span data-ttu-id="1d52c-183">업데이트 정책 재정의 기본값</span><span class="sxs-lookup"><span data-stu-id="1d52c-183">Update policy override default</span></span>
><span data-ttu-id="1d52c-184">Microsoft Edge 업데이트 1.2.145.5 이상</span><span class="sxs-lookup"><span data-stu-id="1d52c-184">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="1d52c-185">설명</span><span class="sxs-lookup"><span data-stu-id="1d52c-185">Description</span></span>
<span data-ttu-id="1d52c-186">Microsoft Edge 업데이트가 Microsoft Edge에 사용 가능한 업데이트를 처리하는 방식과 관련하여 모든 채널에 대해 기본 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-186">Lets you specify the default behavior for all channels concerning the way Microsoft Edge Update handles available updates for Microsoft Edge.</span></span> <span data-ttu-id="1d52c-187">특정 채널에 ‘[업데이트 정책 재정의](#update)’ 정책을 지정하여 채널별로 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-187">Can be overridden for individual channels by specifying the '[Update policy override](#update)' policy for those specific channels.</span></span>

  <span data-ttu-id="1d52c-188">이 정책을 사용하도록 설정하면 다음 중 구성된 옵션에 따라 Microsoft Edge 업데이트가 Microsoft Edge에 대한 업데이트를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-188">If you enable this policy, Microsoft Edge Update handles Microsoft Edge updates according to how you configure the following options:</span></span>
   - <span data-ttu-id="1d52c-189">항상 업데이트 허용: 업데이트는 정기 업데이트 확인 또는 수동 업데이트 확인을 통해 검색되는 경우 항상 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-189">Always allow updates: Updates are always applied when found, either by periodic update check or by a manual update check.</span></span>
   - <span data-ttu-id="1d52c-190">자동 업데이트만: 업데이트는 정기 업데이트 확인에서 검색된 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-190">Automatic silent updates only: Updates are applied only when they're found by the periodic update check.</span></span>
   - <span data-ttu-id="1d52c-191">수동 업데이트만: 업데이트는 사용자가 수동 업데이트 확인을 실행하는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-191">Manual updates only: Updates are applied only when the user runs a manual update check.</span></span>
   - <span data-ttu-id="1d52c-192">업데이트 사용 안 함: 업데이트가 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-192">Updates disabled: Updates are never applied.</span></span>

  <span data-ttu-id="1d52c-193">수동 업데이트를 선택하는 경우 앱의 수동 업데이트 메커니즘(사용 가능한 경우)을 사용하여 정기적으로 업데이트를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-193">If you select manual updates, make sure you periodically check for updates by using the app's manual update mechanism, if available.</span></span> <span data-ttu-id="1d52c-194">업데이트를 사용하지 않도록 설정하는 경우 정기적으로 업데이트를 확인하여 사용자에게 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-194">If you disable updates, periodically check for updates, and distribute them to users.</span></span>

  <span data-ttu-id="1d52c-195">이 정책을 사용하도록 설정하고 구성하지 않으면 Microsoft Edge 업데이트는 ‘[업데이트 정책 재정의](#update)’ 정책에 지정된 대로 사용 가능한 업데이트를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-195">If you don't enable and configure this policy, Microsoft Edge Update handles available updates as specified by the '[Update policy override](#update)' policy.</span></span>

  <span data-ttu-id="1d52c-196">이 정책은 Microsoft® Active Directory® 도메인에 연결된 Windows 인스턴스에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-196">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <span data-ttu-id="1d52c-197">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="1d52c-197">Windows information and settings</span></span>
##### <span data-ttu-id="1d52c-198">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="1d52c-198">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="1d52c-199">GP 고유 이름: UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="1d52c-199">GP unique name: UpdateDefault</span></span>
- <span data-ttu-id="1d52c-200">GP 이름: 업데이트 정책 재정의 기본값</span><span class="sxs-lookup"><span data-stu-id="1d52c-200">GP name: Update policy override default</span></span>
- <span data-ttu-id="1d52c-201">GP 경로: 관리 템플릿/Microsoft Edge 업데이트/응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="1d52c-201">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="1d52c-202">GP ADMX 파일 이름: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="1d52c-202">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="1d52c-203">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="1d52c-203">Windows Registry Settings</span></span>
- <span data-ttu-id="1d52c-204">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="1d52c-204">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="1d52c-205">값 이름: UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="1d52c-205">Value Name: UpdateDefault</span></span>
- <span data-ttu-id="1d52c-206">값 형식: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="1d52c-206">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="1d52c-207">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="1d52c-207">Example value:</span></span>
```
0x00000003
```
[<span data-ttu-id="1d52c-208">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="1d52c-208">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="1d52c-209">설치</span><span class="sxs-lookup"><span data-stu-id="1d52c-209">Install</span></span>
#### <span data-ttu-id="1d52c-210">설치 허용</span><span class="sxs-lookup"><span data-stu-id="1d52c-210">Allow installation</span></span>
><span data-ttu-id="1d52c-211">Microsoft Edge 업데이트 1.2.145.5 이상</span><span class="sxs-lookup"><span data-stu-id="1d52c-211">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="1d52c-212">설명</span><span class="sxs-lookup"><span data-stu-id="1d52c-212">Description</span></span>
<span data-ttu-id="1d52c-213">도메인에 가입된 장치에 Microsoft Edge 채널을 설치할 수 있는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-213">Specifies whether a Microsoft Edge channel can be installed on domain-joined devices.</span></span>

  <span data-ttu-id="1d52c-214">채널에 이 정책을 사용하면 Microsoft Edge가 설치에서 차단되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-214">If you enable this policy for a channel, Microsoft Edge will not be blocked from installation.</span></span>

  <span data-ttu-id="1d52c-215">채널에 이 정책을 사용하지 않으면 Microsoft Edge가 설치에서 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-215">If you disable this policy for a channel, Microsoft Edge will be blocked from installation.</span></span>

  <span data-ttu-id="1d52c-216">채널에 대해 이 정책을 구성하지 않으면 ‘[설치 허용](#installdefault)’ 정책 구성이 사용자가 해당 Microsoft Edge 채널을 설치할 수 있는지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-216">If you don't configure this policy for a channel, the '[Allow installation default](#installdefault)' policy configuration determines whether users can install that channel of Microsoft Edge.</span></span>

  <span data-ttu-id="1d52c-217">이 정책은 Microsoft® Active Directory® 도메인에 연결된 Windows 인스턴스에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-217">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <span data-ttu-id="1d52c-218">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="1d52c-218">Windows information and settings</span></span>
##### <span data-ttu-id="1d52c-219">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="1d52c-219">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="1d52c-220">GP 고유 이름: Install</span><span class="sxs-lookup"><span data-stu-id="1d52c-220">GP unique name: Install</span></span>
- <span data-ttu-id="1d52c-221">GP 이름: 설치 허용</span><span class="sxs-lookup"><span data-stu-id="1d52c-221">GP name: Allow installation</span></span>
- <span data-ttu-id="1d52c-222">GP 경로:</span><span class="sxs-lookup"><span data-stu-id="1d52c-222">GP path:</span></span> 
  - <span data-ttu-id="1d52c-223">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1d52c-223">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="1d52c-224">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="1d52c-224">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="1d52c-225">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="1d52c-225">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="1d52c-226">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="1d52c-226">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="1d52c-227">GP ADMX 파일 이름: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="1d52c-227">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="1d52c-228">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="1d52c-228">Windows Registry Settings</span></span>
- <span data-ttu-id="1d52c-229">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="1d52c-229">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="1d52c-230">값 이름:</span><span class="sxs-lookup"><span data-stu-id="1d52c-230">Value Name:</span></span> 
  - <span data-ttu-id="1d52c-231">(Stable): Install{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="1d52c-231">(Stable): Install{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="1d52c-232">(Beta): Install{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="1d52c-232">(Beta): Install{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="1d52c-233">(Canary): Install{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="1d52c-233">(Canary): Install{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="1d52c-234">(Dev): Install{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="1d52c-234">(Dev): Install{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="1d52c-235">값 형식: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="1d52c-235">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="1d52c-236">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="1d52c-236">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="1d52c-237">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="1d52c-237">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="1d52c-238">업데이트</span><span class="sxs-lookup"><span data-stu-id="1d52c-238">Update</span></span>
#### <span data-ttu-id="1d52c-239">업데이트 정책 재정의</span><span class="sxs-lookup"><span data-stu-id="1d52c-239">Update policy override</span></span>
><span data-ttu-id="1d52c-240">Microsoft Edge 업데이트 1.2.145.5 이상</span><span class="sxs-lookup"><span data-stu-id="1d52c-240">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="1d52c-241">설명</span><span class="sxs-lookup"><span data-stu-id="1d52c-241">Description</span></span>
<span data-ttu-id="1d52c-242">Microsoft Edge 업데이트가 Microsoft Edge에서 사용 가능한 업데이트를 처리하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-242">Specifies how Microsoft Edge Update handles available updates from Microsoft Edge.</span></span>

<span data-ttu-id="1d52c-243">이 정책을 사용하도록 설정하면 다음 중 구성된 옵션에 따라 Microsoft Edge 업데이트가 Microsoft Edge에 대한 업데이트를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-243">If you enable this policy, Microsoft Edge Update handles Microsoft Edge updates according to how you configure the following options:</span></span>
  - <span data-ttu-id="1d52c-244">항상 업데이트 허용: 업데이트는 정기 업데이트 확인 또는 수동 업데이트 확인을 통해 검색되는 경우 항상 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-244">Always allow updates: Updates are always applied when found, either by periodic update check or by a manual update check.</span></span>
  - <span data-ttu-id="1d52c-245">자동 업데이트만: 업데이트는 정기 업데이트 확인에서 검색된 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-245">Automatic silent updates only: Updates are applied only when they're found by the periodic update check.</span></span>
  - <span data-ttu-id="1d52c-246">수동 업데이트만: 업데이트는 사용자가 수동 업데이트 확인을 실행하는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-246">Manual updates only: Updates are applied only when the user runs a manual update check.</span></span> <span data-ttu-id="1d52c-247">(일부 앱은 이 옵션에 대한 인터페이스를 제공하지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="1d52c-247">(Not all apps provide an interface for this option.)</span></span>
  - <span data-ttu-id="1d52c-248">업데이트 사용 안 함: 업데이트가 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-248">Updates disabled: Updates are never applied.</span></span>

<span data-ttu-id="1d52c-249">수동 업데이트를 선택하는 경우 앱의 수동 업데이트 메커니즘(사용 가능한 경우)을 사용하여 정기적으로 업데이트를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-249">If you select manual updates, make sure you periodically check for updates by using the app's manual update mechanism, if available.</span></span> <span data-ttu-id="1d52c-250">업데이트를 사용하지 않도록 설정하는 경우 정기적으로 업데이트를 확인하여 사용자에게 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-250">If you disable updates, periodically check for updates, and distribute them to users.</span></span>

<span data-ttu-id="1d52c-251">이 정책을 사용하도록 설정하고 구성하지 않으면 Microsoft Edge 업데이트는 ‘[업데이트 정책 재정의 기본값](#updatedefault)’ 정책에 지정된 대로 사용 가능한 업데이트를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-251">If you don't enable and configure this policy, Microsoft Edge Update handles available updates as specified by the '[Update policy override default](#updatedefault)' policy.</span></span>

<span data-ttu-id="1d52c-252">자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2136406](https://go.microsoft.com/fwlink/?linkid=2136406)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d52c-252">See [https://go.microsoft.com/fwlink/?linkid=2136406](https://go.microsoft.com/fwlink/?linkid=2136406) for more information.</span></span>

<span data-ttu-id="1d52c-253">이 정책은 Microsoft® Active Directory® 도메인에 연결된 Windows 인스턴스에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-253">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <span data-ttu-id="1d52c-254">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="1d52c-254">Windows information and settings</span></span>
##### <span data-ttu-id="1d52c-255">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="1d52c-255">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="1d52c-256">GP 고유 이름: Update</span><span class="sxs-lookup"><span data-stu-id="1d52c-256">GP unique name: Update</span></span>
- <span data-ttu-id="1d52c-257">GP 이름: 업데이트 정책 재정의</span><span class="sxs-lookup"><span data-stu-id="1d52c-257">GP name: Update policy override</span></span>
- <span data-ttu-id="1d52c-258">GP 경로:</span><span class="sxs-lookup"><span data-stu-id="1d52c-258">GP path:</span></span> 
  - <span data-ttu-id="1d52c-259">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1d52c-259">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="1d52c-260">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="1d52c-260">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="1d52c-261">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="1d52c-261">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="1d52c-262">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="1d52c-262">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="1d52c-263">GP ADMX 파일 이름: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="1d52c-263">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="1d52c-264">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="1d52c-264">Windows Registry Settings</span></span>
- <span data-ttu-id="1d52c-265">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="1d52c-265">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="1d52c-266">값 이름:</span><span class="sxs-lookup"><span data-stu-id="1d52c-266">Value Name:</span></span> 
  - <span data-ttu-id="1d52c-267">(Stable): Update{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="1d52c-267">(Stable): Update{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="1d52c-268">(Beta): Update{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="1d52c-268">(Beta): Update{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="1d52c-269">(Canary): Update{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="1d52c-269">(Canary): Update{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="1d52c-270">(Dev): Update{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="1d52c-270">(Dev): Update{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="1d52c-271">값 형식: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="1d52c-271">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="1d52c-272">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="1d52c-272">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="1d52c-273">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="1d52c-273">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="1d52c-274">Allowsxs</span><span class="sxs-lookup"><span data-stu-id="1d52c-274">Allowsxs</span></span>
#### <span data-ttu-id="1d52c-275">Microsoft Edge 함께 사용 브라우저 환경 허용</span><span class="sxs-lookup"><span data-stu-id="1d52c-275">Allow Microsoft Edge Side by Side browser experience</span></span>
><span data-ttu-id="1d52c-276">Microsoft Edge 업데이트 1.2.145.5 이상</span><span class="sxs-lookup"><span data-stu-id="1d52c-276">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="1d52c-277">설명</span><span class="sxs-lookup"><span data-stu-id="1d52c-277">Description</span></span>
<span data-ttu-id="1d52c-278">이 정책은 사용자가 Microsoft Edge(Edge HTML) 및 Microsoft Edge(Chromium 기반)을 함께 실행할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-278">This policy lets a user run Microsoft Edge (Edge HTML) and Microsoft Edge (Chromium-based) side-by-side.</span></span>

<span data-ttu-id="1d52c-279">이 정책을 "구성되지 않음"으로 설정하면 Microsoft Edge(Chromium 기반) 안정 채널 및 2019년 11월 보안 업데이트가 설치된 후 Microsoft Edge(Chromium 기반)가 Microsoft Edge(Edge HTML)를 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-279">If this policy is set to “Not configured”, Microsoft Edge (Chromium-based) will replace Microsoft Edge (Edge HTML) after the Microsoft Edge (Chromium-based) stable channel and the November 2019 security updates are installed.</span></span>  <span data-ttu-id="1d52c-280">이는 "사용 안 함" 설정과 동일한 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-280">This is the same behavior as the “Disabled” setting.</span></span>

<span data-ttu-id="1d52c-281">"사용 안 함" 설정은 함께 사용 환경을 차단하고 Microsoft Edge(Chromium 기반) 안정 채널 및 2019년 11월 보안 업데이트가 설치된 후 Microsoft Edge(Chromium 기반)가 Microsoft Edge(Edge HTML)를 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-281">The “Disabled” setting blocks a side-by-side experience and Microsoft Edge (Chromium-based) will replace Microsoft Edge (Edge HTML) after the Microsoft Edge (Chromium-based) stable channel and the November 2019 security updates are installed.</span></span>  <span data-ttu-id="1d52c-282">이는 "구성되지 않음" 설정과 동일한 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-282">This is the same behavior as the “Not Configured” setting.</span></span>

<span data-ttu-id="1d52c-283">이 정책을 "사용"으로 설정하면 Microsoft Edge(Chromium 기반)이 설치된 후 Microsoft Edge(Chromium 기반)와 Microsoft Edge(Edge HTML)를 함께 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-283">When this policy is “Enabled”, Microsoft Edge (Chromium-based) and Microsoft Edge (Edge HTML) can run side-by-side after Microsoft Edge (Chromium-based) is installed.</span></span>

<span data-ttu-id="1d52c-284">이 그룹 정책을 적용하려면 Windows 업데이트가 Microsoft Edge(Chromium 기반)를 자동으로 설치하기 전에 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-284">For this group policy to take affect, it must be configured before the automatic install of Microsoft Edge (Chromium-based) by Windows Update.</span></span> <span data-ttu-id="1d52c-285">참고: 사용자는 Microsoft Edge(Chromium 기반) 차단 도구 키트를 사용하여 Microsoft Edge(Chromium 기반) 자동 업데이트를 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-285">Note: A user can block the automatic update of Microsoft Edge (Chromium-based) by using the Microsoft Edge (Chromium-based) Blocker Toolkit.</span></span>
#### <span data-ttu-id="1d52c-286">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="1d52c-286">Windows information and settings</span></span>
##### <span data-ttu-id="1d52c-287">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="1d52c-287">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="1d52c-288">GP 고유 이름: Allowsxs</span><span class="sxs-lookup"><span data-stu-id="1d52c-288">GP unique name: Allowsxs</span></span>
- <span data-ttu-id="1d52c-289">GP 이름: Microsoft Edge 함께 사용 브라우저 환경 허용</span><span class="sxs-lookup"><span data-stu-id="1d52c-289">GP name: Allow Microsoft Edge Side by Side browser experience</span></span>
- <span data-ttu-id="1d52c-290">GP 경로: 관리 템플릿/Microsoft Edge 업데이트/응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="1d52c-290">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="1d52c-291">GP ADMX 파일 이름: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="1d52c-291">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="1d52c-292">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="1d52c-292">Windows Registry Settings</span></span>
- <span data-ttu-id="1d52c-293">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="1d52c-293">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="1d52c-294">값 이름: Allowsxs</span><span class="sxs-lookup"><span data-stu-id="1d52c-294">Value Name: Allowsxs</span></span>
- <span data-ttu-id="1d52c-295">값 형식: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="1d52c-295">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="1d52c-296">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="1d52c-296">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="1d52c-297">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="1d52c-297">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="1d52c-298">CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="1d52c-298">CreateDesktopShortcutDefault</span></span>
#### <span data-ttu-id="1d52c-299">기본 설치 시 데스크톱 바로 가기 만들기 방지</span><span class="sxs-lookup"><span data-stu-id="1d52c-299">Prevent Desktop Shortcut creation upon install default</span></span>
><span data-ttu-id="1d52c-300">Microsoft Edge 업데이트 1.3.128.0 이상</span><span class="sxs-lookup"><span data-stu-id="1d52c-300">Microsoft Edge Update 1.3.128.0 and later</span></span>

#### <span data-ttu-id="1d52c-301">설명</span><span class="sxs-lookup"><span data-stu-id="1d52c-301">Description</span></span>
<span data-ttu-id="1d52c-302">Microsoft Edge가 설치된 경우 데스크톱 바로 가기를 만들기 위한 모든 채널에 대한 기본 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-302">Lets you specify the default behavior for all channels for creating a desktop shortcut when Microsoft Edge is installed.</span></span>

  <span data-ttu-id="1d52c-303">이 정책을 사용하도록 설정하는 경우 Microsoft Edge가 설치될 때 데스크톱 바로 가기가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-303">If you enable this policy a desktop shortcut is created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="1d52c-304">이 정책을 사용하지 않도록 설정하는 경우 Microsoft Edge가 설치될 때 데스크톱 바로 가기가 만들어지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-304">If you disable this policy, no desktop shortcut will be created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="1d52c-305">이 정책을 구성하지 않으면 Microsoft Edge로의 데스크톱 바로 가기가 설치 도중에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-305">If you don’t configure this policy a desktop shortcut to Microsoft Edge will be created during installation.</span></span>
<span data-ttu-id="1d52c-306">Microsoft Edge가 이미 설치되어 있는 경우 이 정책은 아무런 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-306">If Microsoft Edge is already installed, this policy will have no effect.</span></span>
#### <span data-ttu-id="1d52c-307">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="1d52c-307">Windows information and settings</span></span>
##### <span data-ttu-id="1d52c-308">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="1d52c-308">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="1d52c-309">GP 고유 이름: CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="1d52c-309">GP unique name: CreateDesktopShortcutDefault</span></span>
- <span data-ttu-id="1d52c-310">GP 이름: 기본값을 설치 시 데스크톱 바로 가기 만들기를 방지</span><span class="sxs-lookup"><span data-stu-id="1d52c-310">GP name: Prevent Desktop Shortcut creation upon install default</span></span>
- <span data-ttu-id="1d52c-311">GP 경로: 관리 템플릿/Microsoft Edge 업데이트/응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="1d52c-311">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="1d52c-312">GP ADMX 파일 이름: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="1d52c-312">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="1d52c-313">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="1d52c-313">Windows Registry Settings</span></span>
- <span data-ttu-id="1d52c-314">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="1d52c-314">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="1d52c-315">값 이름: CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="1d52c-315">Value Name: CreateDesktopShortcutDefault</span></span>
- <span data-ttu-id="1d52c-316">값 형식: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="1d52c-316">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="1d52c-317">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="1d52c-317">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="1d52c-318">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="1d52c-318">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="1d52c-319">CreateDesktopShortcut</span><span class="sxs-lookup"><span data-stu-id="1d52c-319">CreateDesktopShortcut</span></span>
#### <span data-ttu-id="1d52c-320">설치 시 데스크톱 바로 가기 만들기를 방지</span><span class="sxs-lookup"><span data-stu-id="1d52c-320">Prevent Desktop Shortcut creation upon install</span></span>
><span data-ttu-id="1d52c-321">Microsoft Edge 업데이트 1.3.128.0 이상</span><span class="sxs-lookup"><span data-stu-id="1d52c-321">Microsoft Edge Update 1.3.128.0 and later</span></span>

#### <span data-ttu-id="1d52c-322">설명</span><span class="sxs-lookup"><span data-stu-id="1d52c-322">Description</span></span>
<span data-ttu-id="1d52c-323">이 정책을 사용하도록 설정하는 경우 Microsoft Edge가 설치될 때 데스크톱 바로 가기가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-323">If you enable this policy a desktop shortcut is created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="1d52c-324">이 정책을 사용하지 않도록 설정하는 경우 Microsoft Edge가 설치될 때 데스크톱 바로 가기가 만들어지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-324">If you disable this policy, no desktop shortcut will be created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="1d52c-325">이 정책을 구성하지 않으면 Microsoft Edge로의 데스크톱 바로 가기가 설치 도중에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-325">If you don’t configure this policy a desktop shortcut to Microsoft Edge will be created during installation.</span></span>
<span data-ttu-id="1d52c-326">Microsoft Edge가 이미 설치되어 있는 경우 이 정책은 아무런 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-326">If Microsoft Edge is already installed, this policy will have no effect.</span></span>

  <span data-ttu-id="1d52c-327">채널에 대한 이 정책을 구성하지 않는 경우 '[설치시 바탕 화면 바로 가기 만들기 방지 기본](#createdesktopshortcutdefault)' 정책 구성에 따라 Microsoft Edge 설치시 바로 가기 만들기를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-327">If you don't configure this policy for a channel, the '[Prevent Desktop Shortcut creation upon install default](#createdesktopshortcutdefault)' policy configuration determines shortcut creation when Microsoft Edge is installed.</span></span>
#### <span data-ttu-id="1d52c-328">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="1d52c-328">Windows information and settings</span></span>
##### <span data-ttu-id="1d52c-329">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="1d52c-329">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="1d52c-330">GP 고유 이름: CreateDesktopShortcut</span><span class="sxs-lookup"><span data-stu-id="1d52c-330">GP unique name: CreateDesktopShortcut</span></span>
- <span data-ttu-id="1d52c-331">GP 이름: 설치 시 데스크톱 바로 가기 만들기를 방지</span><span class="sxs-lookup"><span data-stu-id="1d52c-331">GP name: Prevent Desktop Shortcut creation upon install</span></span>
- <span data-ttu-id="1d52c-332">GP 경로:</span><span class="sxs-lookup"><span data-stu-id="1d52c-332">GP path:</span></span> 
  - <span data-ttu-id="1d52c-333">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1d52c-333">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="1d52c-334">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="1d52c-334">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="1d52c-335">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="1d52c-335">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="1d52c-336">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="1d52c-336">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="1d52c-337">GP ADMX 파일 이름: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="1d52c-337">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="1d52c-338">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="1d52c-338">Windows Registry Settings</span></span>
- <span data-ttu-id="1d52c-339">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="1d52c-339">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="1d52c-340">값 이름:</span><span class="sxs-lookup"><span data-stu-id="1d52c-340">Value Name:</span></span> 
  - <span data-ttu-id="1d52c-341">(안정): CreateDesktopShortcut{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="1d52c-341">(Stable): CreateDesktopShortcut{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="1d52c-342">(베타): CreateDesktopShortcut{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="1d52c-342">(Beta): CreateDesktopShortcut{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="1d52c-343">(카나리아): CreateDesktopShortcut{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="1d52c-343">(Canary): CreateDesktopShortcut{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="1d52c-344">(Dev): CreateDesktopShortcut{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="1d52c-344">(Dev): CreateDesktopShortcut{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="1d52c-345">값 형식: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="1d52c-345">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="1d52c-346">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="1d52c-346">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="1d52c-347">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="1d52c-347">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="1d52c-348">RollbackToTargetVersion</span><span class="sxs-lookup"><span data-stu-id="1d52c-348">RollbackToTargetVersion</span></span>
#### <span data-ttu-id="1d52c-349">대상 버전으로 롤백</span><span class="sxs-lookup"><span data-stu-id="1d52c-349">Rollback to Target version</span></span>
><span data-ttu-id="1d52c-350">Microsoft Edge 업데이트 1.3.133.3 이상</span><span class="sxs-lookup"><span data-stu-id="1d52c-350">Microsoft Edge Update 1.3.133.3 and later</span></span>

#### <span data-ttu-id="1d52c-351">설명</span><span class="sxs-lookup"><span data-stu-id="1d52c-351">Description</span></span>
<span data-ttu-id="1d52c-352">Microsoft Edge 업데이트가 '[대상 버전 재정의](#targetversionprefix)'에 표시된 버전으로 Microsoft Edge 설치를 롤백하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-352">Specifies that Microsoft Edge Update should rollback installations of Microsoft Edge to the version indicated in '[Target version override](#targetversionprefix)'.</span></span>

<span data-ttu-id="1d52c-353">'[대상 버전 재정의](#targetversionprefix)'가 설정되고 '[업데이트 정책 재정의](#update)'가 켜짐 상태 중 하나(업데이트 항상 허용, 자동 업데이트만, 수동 업데이트만)로 설정되어 있지 않은 경우에는 이 정책이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-353">This policy has no effect unless '[Target version override](#targetversionprefix)' is set and '[Update policy override](#update)' is set to one of the ON states (Always allow updates, Automatic silent updates only, Manual updates only).</span></span>

<span data-ttu-id="1d52c-354">이 정책을 사용하지 않거나 구성하지 않는 경우 '[대상 버전 재정의](#targetversionprefix)'에서 지정한 것보다 높은 버전이 있는 설치는 그대로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-354">If you disable this policy or don't configure it, installs that have a version higher than that specified by '[Target version override](#targetversionprefix)' will be left as-is.</span></span>

<span data-ttu-id="1d52c-355">이 정책을 사용하면 '[대상 버전 재정의](#targetversionprefix)'에서 지정한 것보다 높은 현재 버전이 있는 설치는 대상 버전으로 다운그레이드됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-355">If you enable this policy, installs that have a current version higher than specified by the '[Target version override](#targetversionprefix)' will be downgraded to the target version.</span></span>

<span data-ttu-id="1d52c-356">최신 버전의 Microsoft Edge 브라우저를 설치하여 최신 보안 업데이트를 통해 보호하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-356">We recommend that users install the latest version of the Microsoft Edge browser to ensure protection by the latest security updates.</span></span> <span data-ttu-id="1d52c-357">이전 버전으로 롤백하면 알려진 보안 문제에 노출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-357">Rollback to an earlier version risks exposure to known security issues.</span></span> <span data-ttu-id="1d52c-358">이 정책은 Microsoft Edge 브라우저 업데이트에서 문제를 해결하는 임시 해결 방법으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-358">This policy is meant to be used as a temporary fix to address issues in a Microsoft Edge browser update.</span></span>

<span data-ttu-id="1d52c-359">브라우저 버전을 일시적으로 롤백하려면 먼저 조직의 모든 사용자에 대해 동기화([https://go.microsoft.com/fwlink/?linkid=2133032](https://go.microsoft.com/fwlink/?linkid=2133032))를 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-359">Before temporarily rolling back your browser version, we recommend that you turn on Sync ([https://go.microsoft.com/fwlink/?linkid=2133032](https://go.microsoft.com/fwlink/?linkid=2133032)) for all users in your organization.</span></span> <span data-ttu-id="1d52c-360">동기화를 설정하지 않은 경우 영구적 검색 데이터 손실이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-360">If you don't turn on Sync, there is a risk of permanent browsing data loss.</span></span> <span data-ttu-id="1d52c-361">귀하의 책임하에 이 정책을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="1d52c-361">Use this policy at your own risk.</span></span>

<span data-ttu-id="1d52c-362">참고: 롤백에 사용할 수 있는 모든 버전은 [https://aka.ms/EdgeEnterprise](https://aka.ms/EdgeEnterprise)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-362">Note: All versions available for rollback can be viewed here [https://aka.ms/EdgeEnterprise](https://aka.ms/EdgeEnterprise).</span></span>

<span data-ttu-id="1d52c-363">이 정책은 Microsoft Edge 버전 86 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-363">This policy applies to Microsoft Edge version 86 or later.</span></span>

<span data-ttu-id="1d52c-364">자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2133918](https://go.microsoft.com/fwlink/?linkid=2133918)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d52c-364">See [https://go.microsoft.com/fwlink/?linkid=2133918](https://go.microsoft.com/fwlink/?linkid=2133918) for more information.</span></span>

<span data-ttu-id="1d52c-365">이 정책은 Microsoft® Active Directory® 도메인에 연결된 Windows 인스턴스에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-365">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <span data-ttu-id="1d52c-366">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="1d52c-366">Windows information and settings</span></span>
##### <span data-ttu-id="1d52c-367">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="1d52c-367">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="1d52c-368">GP 고유 이름: RollbackToTargetVersion</span><span class="sxs-lookup"><span data-stu-id="1d52c-368">GP unique name: RollbackToTargetVersion</span></span>
- <span data-ttu-id="1d52c-369">GP 이름: 대상 버전으로 롤백</span><span class="sxs-lookup"><span data-stu-id="1d52c-369">GP name: Rollback to Target version</span></span>
- <span data-ttu-id="1d52c-370">GP 경로:</span><span class="sxs-lookup"><span data-stu-id="1d52c-370">GP path:</span></span> 
  - <span data-ttu-id="1d52c-371">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1d52c-371">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="1d52c-372">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="1d52c-372">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="1d52c-373">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="1d52c-373">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="1d52c-374">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="1d52c-374">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="1d52c-375">GP ADMX 파일 이름: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="1d52c-375">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="1d52c-376">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="1d52c-376">Windows Registry Settings</span></span>
- <span data-ttu-id="1d52c-377">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="1d52c-377">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="1d52c-378">값 이름:</span><span class="sxs-lookup"><span data-stu-id="1d52c-378">Value Name:</span></span> 
  - <span data-ttu-id="1d52c-379">(안정): RollbackToTargetVersion{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="1d52c-379">(Stable): RollbackToTargetVersion{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="1d52c-380">(베타): RollbackToTargetVersion{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="1d52c-380">(Beta): RollbackToTargetVersion{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="1d52c-381">(Canary): RollbackToTargetVersion{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="1d52c-381">(Canary): RollbackToTargetVersion{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="1d52c-382">(Dev): RollbackToTargetVersion{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="1d52c-382">(Dev): RollbackToTargetVersion{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="1d52c-383">값 형식: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="1d52c-383">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="1d52c-384">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="1d52c-384">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="1d52c-385">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="1d52c-385">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="1d52c-386">TargetVersionPrefix</span><span class="sxs-lookup"><span data-stu-id="1d52c-386">TargetVersionPrefix</span></span>
#### <span data-ttu-id="1d52c-387">대상 버전 재정의</span><span class="sxs-lookup"><span data-stu-id="1d52c-387">Target version override</span></span>
><span data-ttu-id="1d52c-388">Microsoft Edge 업데이트 1.3.119.43 이상</span><span class="sxs-lookup"><span data-stu-id="1d52c-388">Microsoft Edge Update 1.3.119.43 and later</span></span>

#### <span data-ttu-id="1d52c-389">설명</span><span class="sxs-lookup"><span data-stu-id="1d52c-389">Description</span></span>
<span data-ttu-id="1d52c-390">이 정책을 사용하도록 설정하고 자동 업데이트를 사용하도록 설정하면 Microsoft Edge는 이 정책 값이 지정하는 버전으로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-390">When this policy is enabled, and auto-update is enabled, Microsoft Edge will be updated to the version specified by this policy value.</span></span>

<span data-ttu-id="1d52c-391">정책 값은 특정 Microsoft Edge 버전(예: 83.0.499.12) 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-391">The policy value must be a specific Microsoft Edge version, e.g. 83.0.499.12.</span></span>

<span data-ttu-id="1d52c-392">장치에 지정된 값보다 더 최신 버전의 Microsoft Edge가 있는 경우 Microsoft Edge는 최신 버전을 유지하고 지정된 버전으로 다운그레이드되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-392">If a device has newer version of Microsoft Edge than the value specified, Microsoft Edge will remain on the newer version and not downgrade to the specified version.</span></span>

<span data-ttu-id="1d52c-393">지정된 버전이 존재하지 않거나 형식이 잘못된 경우 Microsoft Edge는 현재 버전을 유지하고 이후 버전으로 자동 업데이트되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-393">If the specified version does not exist, or is improperly formatted, then Microsoft Edge will remain on its current version and not update to future versions automatically.</span></span>

<span data-ttu-id="1d52c-394">자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2136707](https://go.microsoft.com/fwlink/?linkid=2136707)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d52c-394">See [https://go.microsoft.com/fwlink/?linkid=2136707](https://go.microsoft.com/fwlink/?linkid=2136707) for more information.</span></span>

<span data-ttu-id="1d52c-395">이 정책은 Microsoft® Active Directory® 도메인에 연결된 Windows 인스턴스에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-395">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <span data-ttu-id="1d52c-396">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="1d52c-396">Windows information and settings</span></span>
##### <span data-ttu-id="1d52c-397">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="1d52c-397">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="1d52c-398">GP 고유 이름: TargetVersionPrefix</span><span class="sxs-lookup"><span data-stu-id="1d52c-398">GP unique name: TargetVersionPrefix</span></span>
- <span data-ttu-id="1d52c-399">GP 이름: 대상 버전 재정의</span><span class="sxs-lookup"><span data-stu-id="1d52c-399">GP name: Target version override</span></span>
- <span data-ttu-id="1d52c-400">GP 경로:</span><span class="sxs-lookup"><span data-stu-id="1d52c-400">GP path:</span></span> 
  - <span data-ttu-id="1d52c-401">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1d52c-401">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="1d52c-402">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="1d52c-402">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="1d52c-403">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="1d52c-403">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="1d52c-404">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="1d52c-404">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="1d52c-405">GP ADMX 파일 이름: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="1d52c-405">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="1d52c-406">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="1d52c-406">Windows Registry Settings</span></span>
- <span data-ttu-id="1d52c-407">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="1d52c-407">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="1d52c-408">값 이름:</span><span class="sxs-lookup"><span data-stu-id="1d52c-408">Value Name:</span></span> 
  - <span data-ttu-id="1d52c-409">(Stable): TargetVersionPrefix{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="1d52c-409">(Stable): TargetVersionPrefix{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="1d52c-410">(Beta): TargetVersionPrefix{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="1d52c-410">(Beta): TargetVersionPrefix{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="1d52c-411">(Canary): TargetVersionPrefix{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="1d52c-411">(Canary): TargetVersionPrefix{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="1d52c-412">(Dev): TargetVersionPrefix{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="1d52c-412">(Dev): TargetVersionPrefix{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="1d52c-413">값 형식: REG_SZ</span><span class="sxs-lookup"><span data-stu-id="1d52c-413">Value Type: REG_SZ</span></span>
##### <span data-ttu-id="1d52c-414">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="1d52c-414">Example value:</span></span>
```
83.0.499.12
```
[<span data-ttu-id="1d52c-415">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="1d52c-415">Back to top</span></span>](#microsoft-edge---update-policies)


## <span data-ttu-id="1d52c-416">기본 설정 정책</span><span class="sxs-lookup"><span data-stu-id="1d52c-416">Preferences policies</span></span>

[<span data-ttu-id="1d52c-417">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="1d52c-417">Back to top</span></span>](#microsoft-edge---update-policies)
### <span data-ttu-id="1d52c-418">AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="1d52c-418">AutoUpdateCheckPeriodMinutes</span></span>
#### <span data-ttu-id="1d52c-419">자동 업데이트 확인 기간 재정의</span><span class="sxs-lookup"><span data-stu-id="1d52c-419">Auto-update check period override</span></span>
><span data-ttu-id="1d52c-420">Microsoft Edge 업데이트 1.2.145.5 이상</span><span class="sxs-lookup"><span data-stu-id="1d52c-420">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="1d52c-421">설명</span><span class="sxs-lookup"><span data-stu-id="1d52c-421">Description</span></span>
<span data-ttu-id="1d52c-422">이 정책을 사용하도록 설정하면 자동 업데이트 확인 최소 간격(분) 값을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-422">If enabled, this policy lets you set a value for the minimum number of minutes between automatic update checks.</span></span> <span data-ttu-id="1d52c-423">그렇지 않으면 기본적으로 자동 업데이트는 10시간마다 업데이트를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-423">Otherwise, by default, auto-update checks for updates every 10 hours.</span></span>

  <span data-ttu-id="1d52c-424">모든 자동 업데이트 확인을 사용하지 않도록 설정하려면 이 값을 0으로 설정합니다(권장하지 않음).</span><span class="sxs-lookup"><span data-stu-id="1d52c-424">If you want to disable all auto-update checks, set the value to 0 (not recommended).</span></span>
#### <span data-ttu-id="1d52c-425">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="1d52c-425">Windows information and settings</span></span>
##### <span data-ttu-id="1d52c-426">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="1d52c-426">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="1d52c-427">GP 고유 이름: AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="1d52c-427">GP unique name: AutoUpdateCheckPeriodMinutes</span></span>
- <span data-ttu-id="1d52c-428">GP 이름: 자동 업데이트 확인 기간 재정의</span><span class="sxs-lookup"><span data-stu-id="1d52c-428">GP name: Auto-update check period override</span></span>
- <span data-ttu-id="1d52c-429">GP 경로: 관리 템플릿/Microsoft Edge 업데이트/기본 설정</span><span class="sxs-lookup"><span data-stu-id="1d52c-429">GP path: Administrative Templates/Microsoft Edge Update/Preferences</span></span>
- <span data-ttu-id="1d52c-430">GP ADMX 파일 이름: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="1d52c-430">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="1d52c-431">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="1d52c-431">Windows Registry Settings</span></span>
- <span data-ttu-id="1d52c-432">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="1d52c-432">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="1d52c-433">값 이름: AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="1d52c-433">Value Name: AutoUpdateCheckPeriodMinutes</span></span>
- <span data-ttu-id="1d52c-434">값 형식: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="1d52c-434">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="1d52c-435">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="1d52c-435">Example value:</span></span>
```
0x00000578
```
[<span data-ttu-id="1d52c-436">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="1d52c-436">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="1d52c-437">UpdatesSuppressed</span><span class="sxs-lookup"><span data-stu-id="1d52c-437">UpdatesSuppressed</span></span>
#### <span data-ttu-id="1d52c-438">매일 자동 업데이트 확인 억제 기간</span><span class="sxs-lookup"><span data-stu-id="1d52c-438">Time period in each day to suppress auto-update check</span></span>
><span data-ttu-id="1d52c-439">Microsoft Edge 업데이트 1.3.33.5 이상</span><span class="sxs-lookup"><span data-stu-id="1d52c-439">Microsoft Edge Update 1.3.33.5 and later</span></span>

#### <span data-ttu-id="1d52c-440">설명</span><span class="sxs-lookup"><span data-stu-id="1d52c-440">Description</span></span>
<span data-ttu-id="1d52c-441">이 정책을 사용하도록 설정하면 업데이트 확인이 시:분부터 시작하여 기간(분) 동안 억제됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-441">If you enable this policy, update checks are suppressed each day starting at Hour:Minute for a period of Duration (in minutes).</span></span> <span data-ttu-id="1d52c-442">기간은 일광 절약 시간에 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-442">Duration isn't affected by daylight saving time.</span></span> <span data-ttu-id="1d52c-443">예를 들어 시작 시간이 22:00이고 기간이 480분인 경우 업데이트는 이 기간 동안 일광 절약 시간제가 시작하거나 종료하는지 관계없이 정확히 8시간 동안 억제됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-443">For example, if the start time is 22:00 and the duration is 480 minutes, updates will be suppressed for exactly 8 hours, regardless of whether daylight saving time starts or ends during this period.</span></span>

  <span data-ttu-id="1d52c-444">이 정책을 사용하지 않도록 설정하거나 구성하지 않으면 특정 기간 동안 업데이트 검사가 억제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-444">If you disable or don't configure this policy, update checks aren't suppressed during any specific period.</span></span>
#### <span data-ttu-id="1d52c-445">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="1d52c-445">Windows information and settings</span></span>
##### <span data-ttu-id="1d52c-446">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="1d52c-446">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="1d52c-447">GP 고유 이름: UpdatesSuppressed</span><span class="sxs-lookup"><span data-stu-id="1d52c-447">GP unique name: UpdatesSuppressed</span></span>
- <span data-ttu-id="1d52c-448">GP 이름: 매일 자동 업데이트 확인 억제 기간</span><span class="sxs-lookup"><span data-stu-id="1d52c-448">GP name: Time period in each day to suppress auto-update check</span></span>
  - <span data-ttu-id="1d52c-449">Options { Hour, Minute, Duration }</span><span class="sxs-lookup"><span data-stu-id="1d52c-449">Options { Hour, Minute, Duration }</span></span>
- <span data-ttu-id="1d52c-450">GP 경로: 관리 템플릿/Microsoft Edge 업데이트/기본 설정</span><span class="sxs-lookup"><span data-stu-id="1d52c-450">GP path: Administrative Templates/Microsoft Edge Update/Preferences</span></span>
- <span data-ttu-id="1d52c-451">GP ADMX 파일 이름: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="1d52c-451">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="1d52c-452">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="1d52c-452">Windows Registry Settings</span></span>
- <span data-ttu-id="1d52c-453">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="1d52c-453">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="1d52c-454">값 이름:</span><span class="sxs-lookup"><span data-stu-id="1d52c-454">Value Name:</span></span> 
  - <span data-ttu-id="1d52c-455">UpdatesSuppressedDurationMin</span><span class="sxs-lookup"><span data-stu-id="1d52c-455">UpdatesSuppressedDurationMin</span></span>
  - <span data-ttu-id="1d52c-456">UpdatesSuppressedStartHour</span><span class="sxs-lookup"><span data-stu-id="1d52c-456">UpdatesSuppressedStartHour</span></span>
  - <span data-ttu-id="1d52c-457">UpdatesSuppressedStartMin</span><span class="sxs-lookup"><span data-stu-id="1d52c-457">UpdatesSuppressedStartMin</span></span>
- <span data-ttu-id="1d52c-458">값 형식: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="1d52c-458">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="1d52c-459">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="1d52c-459">Example value:</span></span>
```
duration   : 0x0000003c
start hour : 0x00000001
start min  : 0x00000002
```
[<span data-ttu-id="1d52c-460">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="1d52c-460">Back to top</span></span>](#microsoft-edge---update-policies)


## <span data-ttu-id="1d52c-461">프록시 서버 정책</span><span class="sxs-lookup"><span data-stu-id="1d52c-461">Proxy Server policies</span></span>

[<span data-ttu-id="1d52c-462">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="1d52c-462">Back to top</span></span>](#microsoft-edge---update-policies)
### <span data-ttu-id="1d52c-463">ProxyMode</span><span class="sxs-lookup"><span data-stu-id="1d52c-463">ProxyMode</span></span>
#### <span data-ttu-id="1d52c-464">프록시 서버 설정 지정 방법 선택</span><span class="sxs-lookup"><span data-stu-id="1d52c-464">Choose how to specify proxy server settings</span></span>
><span data-ttu-id="1d52c-465">Microsoft Edge 업데이트 1.3.21.81 이상</span><span class="sxs-lookup"><span data-stu-id="1d52c-465">Microsoft Edge Update 1.3.21.81 and later</span></span>

#### <span data-ttu-id="1d52c-466">설명</span><span class="sxs-lookup"><span data-stu-id="1d52c-466">Description</span></span>
<span data-ttu-id="1d52c-467">Microsoft Edge 업데이트에서 사용되는 프록시 서버 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-467">Allows you to specify the proxy server settings that are used by Microsoft Edge Update.</span></span>

  <span data-ttu-id="1d52c-468">이 정책을 사용하도록 설정하면 다음 프록시 서버 옵션 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-468">If you enable this policy, you can choose between the following proxy server options:</span></span>
   - <span data-ttu-id="1d52c-469">프록시 서버를 사용하지 않도록 선택하고 항상 직접 연결하는 경우 다른 모든 옵션은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-469">If you choose to never use a proxy server and always connect directly, all other options are ignored.</span></span>
   - <span data-ttu-id="1d52c-470">시스템 프록시 설정을 사용하거나 프록시 서버를 자동으로 검색하도록 선택하는 경우 다른 모든 옵션은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-470">If you choose to use system proxy settings or auto-detect the proxy server, all other options are ignored.</span></span>
   - <span data-ttu-id="1d52c-471">고정 서버 프록시 모드를 선택하는 경우에는 ‘[프록시 서버 주소 또는 URL](#proxyserver)’정책에 추가 옵션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-471">If you choose fixed server proxy mode, you can specify further options in '[Address or URL of proxy server](#proxyserver)' policy.</span></span>
   - <span data-ttu-id="1d52c-472">.pac 프록시 스크립트를 사용하도록 선택하는 경우 ‘[프록시 .pac 파일 URL](#proxypacurl)’ 정책에서 스크립트의 URL을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-472">If you choose to use a .pac proxy script, you must specify the URL for the script in '[URL to a proxy .pac file](#proxypacurl)' policy.</span></span>

  <span data-ttu-id="1d52c-473">이 정책을 사용하도록 설정하면 조직의 사용자가 Microsoft Edge 업데이트에서 프록시 설정을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-473">If you enable this policy, users in your organization can't change the proxy settings in Microsoft Edge Update.</span></span>

  <span data-ttu-id="1d52c-474">이 정책을 사용하지 않도록 설정하거나 구성하지 않으면 프록시 서버 설정이 구성되지 않지만 조직의사용자가 Microsoft Edge 업데이트에 대한 고유한 프록시 설정을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-474">If you disable or don't configure this policy, no proxy server settings are configured, but users in your organization can choose their own proxy settings for Microsoft Edge Update.</span></span>
#### <span data-ttu-id="1d52c-475">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="1d52c-475">Windows information and settings</span></span>
##### <span data-ttu-id="1d52c-476">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="1d52c-476">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="1d52c-477">GP 고유 이름: ProxyMode</span><span class="sxs-lookup"><span data-stu-id="1d52c-477">GP unique name: ProxyMode</span></span>
- <span data-ttu-id="1d52c-478">GP 이름: 프록시 서버 설정 지정 방법 선택</span><span class="sxs-lookup"><span data-stu-id="1d52c-478">GP name: Choose how to specify proxy server settings</span></span>
- <span data-ttu-id="1d52c-479">GP 경로: 관리 템플릿/Microsoft Edge 업데이트/프록시 서버</span><span class="sxs-lookup"><span data-stu-id="1d52c-479">GP path: Administrative Templates/Microsoft Edge Update/Proxy Server</span></span>
- <span data-ttu-id="1d52c-480">GP ADMX 파일 이름: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="1d52c-480">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="1d52c-481">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="1d52c-481">Windows Registry Settings</span></span>
- <span data-ttu-id="1d52c-482">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="1d52c-482">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="1d52c-483">값 이름: ProxyMode</span><span class="sxs-lookup"><span data-stu-id="1d52c-483">Value Name: ProxyMode</span></span>
- <span data-ttu-id="1d52c-484">값 형식: REG_SZ</span><span class="sxs-lookup"><span data-stu-id="1d52c-484">Value Type: REG_SZ</span></span>
##### <span data-ttu-id="1d52c-485">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="1d52c-485">Example value:</span></span>
```
fixed_servers
```
[<span data-ttu-id="1d52c-486">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="1d52c-486">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="1d52c-487">ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="1d52c-487">ProxyPacUrl</span></span>
#### <span data-ttu-id="1d52c-488">프록시 .pac 파일 URL</span><span class="sxs-lookup"><span data-stu-id="1d52c-488">URL to a proxy .pac file</span></span>
><span data-ttu-id="1d52c-489">Microsoft Edge 업데이트 1.3.21.81 이상</span><span class="sxs-lookup"><span data-stu-id="1d52c-489">Microsoft Edge Update 1.3.21.81 and later</span></span>

#### <span data-ttu-id="1d52c-490">설명</span><span class="sxs-lookup"><span data-stu-id="1d52c-490">Description</span></span>
<span data-ttu-id="1d52c-491">PAC(프록시 자동 구성) 파일의 URL을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-491">Allows you to specify a URL for a proxy auto-config (PAC) file.</span></span>

  <span data-ttu-id="1d52c-492">이 정책을 사용하면 PAC 파일의 URL을 지정하여 Microsoft Edge 업데이트가 특정 웹 사이트를 가져오는 데 적합한 프록시 서버를 선택하는 방법을 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-492">If you enable this policy, you can specify a URL for a PAC file to automate how Microsoft Edge Update selects the appropriate proxy server for fetching a particular website.</span></span>

  <span data-ttu-id="1d52c-493">이 정책은 ‘[프록시 서버 설정 지정 방법 선택](#proxymode)’ 정책에서 수동 프록시 설정을 지정한 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-493">This policy is applied only if you have specified manual proxy settings in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>

  <span data-ttu-id="1d52c-494">‘[프록시 서버 설정 지정 방법 선택](#proxymode)‘ 정책에서 수동 이외의 프록시 설정을 선택한 경우 이 정책을 구성하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="1d52c-494">Don't configure this policy if you have selected a proxy setting other than manual in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>
#### <span data-ttu-id="1d52c-495">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="1d52c-495">Windows information and settings</span></span>
##### <span data-ttu-id="1d52c-496">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="1d52c-496">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="1d52c-497">GP 고유 이름: ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="1d52c-497">GP unique name: ProxyPacUrl</span></span>
- <span data-ttu-id="1d52c-498">GP 이름: 프록시 .pac 파일 URL</span><span class="sxs-lookup"><span data-stu-id="1d52c-498">GP name: URL to a proxy .pac file</span></span>
- <span data-ttu-id="1d52c-499">GP 경로: 관리 템플릿/Microsoft Edge 업데이트/프록시 서버</span><span class="sxs-lookup"><span data-stu-id="1d52c-499">GP path: Administrative Templates/Microsoft Edge Update/Proxy Server</span></span>
- <span data-ttu-id="1d52c-500">GP ADMX 파일 이름: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="1d52c-500">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="1d52c-501">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="1d52c-501">Windows Registry Settings</span></span>
- <span data-ttu-id="1d52c-502">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="1d52c-502">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="1d52c-503">값 이름: ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="1d52c-503">Value Name: ProxyPacUrl</span></span>
- <span data-ttu-id="1d52c-504">값 형식: REG_SZ</span><span class="sxs-lookup"><span data-stu-id="1d52c-504">Value Type: REG_SZ</span></span>
##### <span data-ttu-id="1d52c-505">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="1d52c-505">Example value:</span></span>
```
https://www.microsoft.com
```
[<span data-ttu-id="1d52c-506">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="1d52c-506">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="1d52c-507">ProxyServer</span><span class="sxs-lookup"><span data-stu-id="1d52c-507">ProxyServer</span></span>
#### <span data-ttu-id="1d52c-508">프록시 서버 주소 또는 URL</span><span class="sxs-lookup"><span data-stu-id="1d52c-508">Address or URL of proxy server</span></span>
><span data-ttu-id="1d52c-509">Microsoft Edge 업데이트 1.3.21.81 이상</span><span class="sxs-lookup"><span data-stu-id="1d52c-509">Microsoft Edge Update 1.3.21.81 and later</span></span>

#### <span data-ttu-id="1d52c-510">설명</span><span class="sxs-lookup"><span data-stu-id="1d52c-510">Description</span></span>
<span data-ttu-id="1d52c-511">Microsoft Edge 업데이트가 사용할 프록시 서버의 URL을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-511">Allows you to specify the URL of the proxy server for Microsoft Edge Update to use.</span></span>

  <span data-ttu-id="1d52c-512">이 정책을 사용하도록 설정하면 조직에서 Microsoft Edge 업데이트가 사용하는 프록시 서버 URL을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-512">If you enable this policy, you can set the proxy server URL used by Microsoft Edge Update in your organization.</span></span>

  <span data-ttu-id="1d52c-513">이 정책은 ‘[프록시 서버 설정 지정 방법 선택](#proxymode)’ 정책에서 수동 프록시 설정을 선택한 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-513">This policy is applied only if you have selected manual proxy settings in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>

  <span data-ttu-id="1d52c-514">‘[프록시 서버 설정 지정 방법 선택](#proxymode)‘ 정책에서 수동 이외의 프록시 설정을 선택한 경우 이 정책을 구성하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="1d52c-514">Don't configure this policy if you have selected a proxy setting other than manual in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>
#### <span data-ttu-id="1d52c-515">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="1d52c-515">Windows information and settings</span></span>
##### <span data-ttu-id="1d52c-516">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="1d52c-516">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="1d52c-517">GP 고유 이름: ProxyServer</span><span class="sxs-lookup"><span data-stu-id="1d52c-517">GP unique name: ProxyServer</span></span>
- <span data-ttu-id="1d52c-518">GP 이름: 프록시 서버 주소 또는 URL</span><span class="sxs-lookup"><span data-stu-id="1d52c-518">GP name: Address or URL of proxy server</span></span>
- <span data-ttu-id="1d52c-519">GP 경로: 관리 템플릿/Microsoft Edge 업데이트/프록시 서버</span><span class="sxs-lookup"><span data-stu-id="1d52c-519">GP path: Administrative Templates/Microsoft Edge Update/Proxy Server</span></span>
- <span data-ttu-id="1d52c-520">GP ADMX 파일 이름: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="1d52c-520">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="1d52c-521">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="1d52c-521">Windows Registry Settings</span></span>
- <span data-ttu-id="1d52c-522">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="1d52c-522">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="1d52c-523">값 이름: ProxyServer</span><span class="sxs-lookup"><span data-stu-id="1d52c-523">Value Name: ProxyServer</span></span>
- <span data-ttu-id="1d52c-524">값 형식: REG_SZ</span><span class="sxs-lookup"><span data-stu-id="1d52c-524">Value Type: REG_SZ</span></span>
##### <span data-ttu-id="1d52c-525">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="1d52c-525">Example value:</span></span>
```
https://www.microsoft.com
```
[<span data-ttu-id="1d52c-526">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="1d52c-526">Back to top</span></span>](#microsoft-edge---update-policies)


## <span data-ttu-id="1d52c-527">Microsoft Edge WebView 정책</span><span class="sxs-lookup"><span data-stu-id="1d52c-527">Microsoft Edge WebView policies</span></span>

[<span data-ttu-id="1d52c-528">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="1d52c-528">Back to top</span></span>](#microsoft-edge---update-policies)
### <span data-ttu-id="1d52c-529">설치(WebView)</span><span class="sxs-lookup"><span data-stu-id="1d52c-529">Install (WebView)</span></span>
#### <span data-ttu-id="1d52c-530">설치 허용</span><span class="sxs-lookup"><span data-stu-id="1d52c-530">Allow installation</span></span>
><span data-ttu-id="1d52c-531">Microsoft Edge 업데이트 1.3.127.1 이상</span><span class="sxs-lookup"><span data-stu-id="1d52c-531">Microsoft Edge Update 1.3.127.1 and later</span></span>

#### <span data-ttu-id="1d52c-532">설명</span><span class="sxs-lookup"><span data-stu-id="1d52c-532">Description</span></span>
<span data-ttu-id="1d52c-533">Microsoft Edge 업데이트를 사용하여 Microsoft Edge WebView를 설치할 수 있는지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-533">Lets you specify whether Microsoft Edge WebView can be installed using Microsoft Edge Update.</span></span>

  - <span data-ttu-id="1d52c-534">이 정책을 사용하도록 설정하면 사용자가 Microsoft Edge 업데이트를 통해 Microsoft Edge WebView를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-534">If you enable this policy, users can install Microsoft Edge WebView through Microsoft Edge Update.</span></span>
  - <span data-ttu-id="1d52c-535">이 정책을 사용하지 않도록 설정하면 사용자가 Microsoft Edge 업데이트를 통해 Microsoft Edge WebView를 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-535">If you disable this policy, users cannot install Microsoft Edge WebView through Microsoft Edge Update.</span></span>
  - <span data-ttu-id="1d52c-536">이 정책을 구성하지 않으면 ‘[설치 허용 기본](#installdefault)’ 정책 구성이 사용자가 Microsoft Edge 업데이트를 통해 해당 Microsoft Edge Webview를 설치할 수 있는지의 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-536">If you don't configure this policy, the '[Allow installation default](#installdefault)' policy configuration determines whether users can install Microsoft Edge WebView through Microsoft Edge Update.</span></span>
#### <span data-ttu-id="1d52c-537">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="1d52c-537">Windows information and settings</span></span>
##### <span data-ttu-id="1d52c-538">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="1d52c-538">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="1d52c-539">GP 고유 이름: Install</span><span class="sxs-lookup"><span data-stu-id="1d52c-539">GP unique name: Install</span></span>
- <span data-ttu-id="1d52c-540">GP 이름: 설치 허용</span><span class="sxs-lookup"><span data-stu-id="1d52c-540">GP name: Allow installation</span></span>
- <span data-ttu-id="1d52c-541">GP 경로: 관리 템플릿/Microsoft Edge 업데이트/Microsoft Edge WebView</span><span class="sxs-lookup"><span data-stu-id="1d52c-541">GP path: Administrative Templates/Microsoft Edge Update/Microsoft Edge WebView</span></span>
- <span data-ttu-id="1d52c-542">GP ADMX 파일 이름: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="1d52c-542">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="1d52c-543">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="1d52c-543">Windows Registry Settings</span></span>
- <span data-ttu-id="1d52c-544">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="1d52c-544">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="1d52c-545">값 이름:</span><span class="sxs-lookup"><span data-stu-id="1d52c-545">Value Name:</span></span> 
  - <span data-ttu-id="1d52c-546">Install{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}</span><span class="sxs-lookup"><span data-stu-id="1d52c-546">Install{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}</span></span>
- <span data-ttu-id="1d52c-547">값 형식: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="1d52c-547">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="1d52c-548">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="1d52c-548">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="1d52c-549">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="1d52c-549">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="1d52c-550">업데이트(WebView)</span><span class="sxs-lookup"><span data-stu-id="1d52c-550">Update (WebView)</span></span>
#### <span data-ttu-id="1d52c-551">업데이트 정책 재정의</span><span class="sxs-lookup"><span data-stu-id="1d52c-551">Update policy override</span></span>
><span data-ttu-id="1d52c-552">Microsoft Edge 업데이트 1.3.127.1 이상</span><span class="sxs-lookup"><span data-stu-id="1d52c-552">Microsoft Edge Update 1.3.127.1 and later</span></span>

#### <span data-ttu-id="1d52c-553">설명</span><span class="sxs-lookup"><span data-stu-id="1d52c-553">Description</span></span>
<span data-ttu-id="1d52c-554">Microsoft Edge WebView에 대해 자동 업데이트를 사용하도록 설정할지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-554">Lets you specify whether or not automatic updates are enabled for Microsoft Edge WebView.</span></span> <span data-ttu-id="1d52c-555">Microsoft Edge WebView는 응용 프로그램에서 웹 콘텐츠를 표시하는 데 사용하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-555">Microsoft Edge WebView is a component used by applications to display web content.</span></span>
<span data-ttu-id="1d52c-556">자동 업데이트는 기본적으로 사용하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-556">Automatic updates are enabled by default.</span></span> <span data-ttu-id="1d52c-557">Microsoft Edge WebView에서 자동 업데이트를 사용하지 않도록 설정하면 이 구성 요소에 종속 된 응용 프로그램과의 호환성 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-557">Disabling automatic updates for Microsoft Edge WebView might cause compatibility issues with applications that depend on this component.</span></span>

  <span data-ttu-id="1d52c-558">이 정책을 사용하도록 설정하면 다음의 옵션을 구성하는 방법에 따라 Microsoft Edge 업데이트가 Microsoft Edge WebView 업데이트를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-558">If you enable this policy, Microsoft Edge Update handles Microsoft Edge WebView updates according to how you configure the following options:</span></span>
  - <span data-ttu-id="1d52c-559">항상 업데이트 허용: 업데이트가 자동으로 다운로드되고 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-559">Always allow updates: Updates are automatically downloaded and applied</span></span>
  - <span data-ttu-id="1d52c-560">업데이트 사용 안 함: 업데이트가 다운로드되거나 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-560">Updates disabled: Updates are never downloaded or applied</span></span>

  <span data-ttu-id="1d52c-561">이 정책을 사용하도록 설정하지 않으면, 업데이트가 자동으로 다운로드되고 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d52c-561">If you don't enable this policy, updates are automatically downloaded and applied.</span></span>
#### <span data-ttu-id="1d52c-562">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="1d52c-562">Windows information and settings</span></span>
##### <span data-ttu-id="1d52c-563">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="1d52c-563">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="1d52c-564">GP 고유 이름: Update</span><span class="sxs-lookup"><span data-stu-id="1d52c-564">GP unique name: Update</span></span>
- <span data-ttu-id="1d52c-565">GP 이름: 업데이트 정책 재정의</span><span class="sxs-lookup"><span data-stu-id="1d52c-565">GP name: Update policy override</span></span>
- <span data-ttu-id="1d52c-566">GP 경로: 관리 템플릿/Microsoft Edge 업데이트/Microsoft Edge WebView</span><span class="sxs-lookup"><span data-stu-id="1d52c-566">GP path: Administrative Templates/Microsoft Edge Update/Microsoft Edge WebView</span></span>
- <span data-ttu-id="1d52c-567">GP ADMX 파일 이름: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="1d52c-567">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="1d52c-568">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="1d52c-568">Windows Registry Settings</span></span>
- <span data-ttu-id="1d52c-569">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="1d52c-569">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="1d52c-570">값 이름:</span><span class="sxs-lookup"><span data-stu-id="1d52c-570">Value Name:</span></span> 
  - <span data-ttu-id="1d52c-571">Update{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}</span><span class="sxs-lookup"><span data-stu-id="1d52c-571">Update{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}</span></span>
- <span data-ttu-id="1d52c-572">값 형식: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="1d52c-572">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="1d52c-573">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="1d52c-573">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="1d52c-574">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="1d52c-574">Back to top</span></span>](#microsoft-edge---update-policies)


## <span data-ttu-id="1d52c-575">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d52c-575">See also</span></span>
  - [<span data-ttu-id="1d52c-576">Microsoft Edge 구성</span><span class="sxs-lookup"><span data-stu-id="1d52c-576">Configuring Microsoft Edge</span></span>](configure-microsoft-edge.md)
  - [<span data-ttu-id="1d52c-577">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="1d52c-577">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)