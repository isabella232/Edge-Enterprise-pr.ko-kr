---
title: Microsoft Edge 업데이트 정책 설명서
ms.author: stmoody
author: brianalt-msft
manager: tahills
ms.date: 06/10/2020
audience: ITPro
ms.topic: reference
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
ms.custom: ''
description: Microsoft Edge 업데이트 프로그램에서 지원하는 모든 정책에 대한 설명서
ms.openlocfilehash: d772d8dd6f60b89e9bd12a77b740e5fad699756a
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980702"
---
# <span data-ttu-id="9be2a-103">Microsoft Edge - 업데이트 정책</span><span class="sxs-lookup"><span data-stu-id="9be2a-103">Microsoft Edge - Update policies</span></span>
<span data-ttu-id="9be2a-104">최신 버전의 Microsoft Edge에는 Microsoft Edge가 업데이트되는 방법 및 시기를 제어하는 데 사용할 수 있는 다음과 같은 정책이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-104">The latest version of Microsoft Edge includes the following policies that you can use to control how and when Microsoft Edge is updated.</span></span>

           
<span data-ttu-id="9be2a-105">Microsoft Edge에서 사용할 수 있는 다른 정책에 대한 자세한 내용은 [Microsoft Edge 브라우저 정책 참조](microsoft-edge-policies.md)를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="9be2a-105">For information about other policies available in Microsoft Edge, check out [Microsoft Edge browser policy reference](microsoft-edge-policies.md)</span></span>
> [!NOTE]
> <span data-ttu-id="9be2a-106">이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-106">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="9be2a-107">사용 가능한 정책</span><span class="sxs-lookup"><span data-stu-id="9be2a-107">Available policies</span></span>
<span data-ttu-id="9be2a-108">다음 표에서는 이번 릴리스의 Microsoft Edge에서 사용할 수 있는 모든 업데이트 관련 그룹 정책을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-108">These tables lists all of the update-related group policies available in this release of Microsoft Edge.</span></span> <span data-ttu-id="9be2a-109">특정 정책에 대해 자세히 알아보려면 표의 링크를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="9be2a-109">Use the links in the table to get more details about specific policies.</span></span>

|||
|-|-|
|[<span data-ttu-id="9be2a-110">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="9be2a-110">Applications</span></span>](#applications)|[<span data-ttu-id="9be2a-111">기본 설정</span><span class="sxs-lookup"><span data-stu-id="9be2a-111">Preferences</span></span>](#preferences)|
|[<span data-ttu-id="9be2a-112">프록시 서버</span><span class="sxs-lookup"><span data-stu-id="9be2a-112">Proxy Server</span></span>](#proxy-server)||

### [<span data-ttu-id="9be2a-113">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="9be2a-113">Applications</span></span>](#applications-policies)
|<span data-ttu-id="9be2a-114">정책 이름</span><span class="sxs-lookup"><span data-stu-id="9be2a-114">Policy Name</span></span>|<span data-ttu-id="9be2a-115">캡션</span><span class="sxs-lookup"><span data-stu-id="9be2a-115">Caption</span></span>|
|-|-|
|[<span data-ttu-id="9be2a-116">InstallDefault</span><span class="sxs-lookup"><span data-stu-id="9be2a-116">InstallDefault</span></span>](#installdefault)|<span data-ttu-id="9be2a-117">설치 허용 기본값</span><span class="sxs-lookup"><span data-stu-id="9be2a-117">Allow installation default</span></span>|
|[<span data-ttu-id="9be2a-118">UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="9be2a-118">UpdateDefault</span></span>](#updatedefault)|<span data-ttu-id="9be2a-119">업데이트 정책 재정의 기본값</span><span class="sxs-lookup"><span data-stu-id="9be2a-119">Update policy override default</span></span>|
|[<span data-ttu-id="9be2a-120">설치</span><span class="sxs-lookup"><span data-stu-id="9be2a-120">Install</span></span>](#install)|<span data-ttu-id="9be2a-121">설치 허용(채널별)</span><span class="sxs-lookup"><span data-stu-id="9be2a-121">Allow installation (per channel)</span></span>|
|[<span data-ttu-id="9be2a-122">업데이트</span><span class="sxs-lookup"><span data-stu-id="9be2a-122">Update</span></span>](#update)|<span data-ttu-id="9be2a-123">업데이트 정책 재정의(채널별)</span><span class="sxs-lookup"><span data-stu-id="9be2a-123">Update policy override (per channel)</span></span>|
|[<span data-ttu-id="9be2a-124">Allowsxs</span><span class="sxs-lookup"><span data-stu-id="9be2a-124">Allowsxs</span></span>](#allowsxs)|<span data-ttu-id="9be2a-125">Microsoft Edge 함께 사용 브라우저 환경 허용</span><span class="sxs-lookup"><span data-stu-id="9be2a-125">Allow Microsoft Edge Side by Side browser experience</span></span>|
|[<span data-ttu-id="9be2a-126">CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="9be2a-126">CreateDesktopShortcutDefault</span></span>](#createdesktopshortcutdefault)|<span data-ttu-id="9be2a-127">기본 설치 시 데스크톱 바로 가기 만들기 방지</span><span class="sxs-lookup"><span data-stu-id="9be2a-127">Prevent Desktop Shortcut creation upon install default</span></span>|
|[<span data-ttu-id="9be2a-128">CreateDesktopShortcut</span><span class="sxs-lookup"><span data-stu-id="9be2a-128">CreateDesktopShortcut</span></span>](#createdesktopshortcut)|<span data-ttu-id="9be2a-129">설치 시 데스크톱 바로 가기 만들기 방지(채널 당)</span><span class="sxs-lookup"><span data-stu-id="9be2a-129">Prevent Desktop Shortcut creation upon install (per channel)</span></span>|
|[<span data-ttu-id="9be2a-130">TargetVersionPrefix</span><span class="sxs-lookup"><span data-stu-id="9be2a-130">TargetVersionPrefix</span></span>](#targetversionprefix)|<span data-ttu-id="9be2a-131">대상 버전 재정의(채널당)</span><span class="sxs-lookup"><span data-stu-id="9be2a-131">Target version override (per channel)</span></span>|

### [<span data-ttu-id="9be2a-132">기본 설정</span><span class="sxs-lookup"><span data-stu-id="9be2a-132">Preferences</span></span>](#preferences-policies)
|<span data-ttu-id="9be2a-133">정책 이름</span><span class="sxs-lookup"><span data-stu-id="9be2a-133">Policy Name</span></span>|<span data-ttu-id="9be2a-134">캡션</span><span class="sxs-lookup"><span data-stu-id="9be2a-134">Caption</span></span>|
|-|-|
|[<span data-ttu-id="9be2a-135">AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="9be2a-135">AutoUpdateCheckPeriodMinutes</span></span>](#autoupdatecheckperiodminutes)|<span data-ttu-id="9be2a-136">자동 업데이트 확인 기간 재정의</span><span class="sxs-lookup"><span data-stu-id="9be2a-136">Auto-update check period override</span></span>|
|[<span data-ttu-id="9be2a-137">UpdatesSuppressed</span><span class="sxs-lookup"><span data-stu-id="9be2a-137">UpdatesSuppressed</span></span>](#updatessuppressed)|<span data-ttu-id="9be2a-138">매일 자동 업데이트 확인 억제 기간</span><span class="sxs-lookup"><span data-stu-id="9be2a-138">Time period in each day to suppress auto-update check</span></span>|

### [<span data-ttu-id="9be2a-139">프록시 서버</span><span class="sxs-lookup"><span data-stu-id="9be2a-139">Proxy Server</span></span>](#proxy-server-policies)
|<span data-ttu-id="9be2a-140">정책 이름</span><span class="sxs-lookup"><span data-stu-id="9be2a-140">Policy Name</span></span>|<span data-ttu-id="9be2a-141">캡션</span><span class="sxs-lookup"><span data-stu-id="9be2a-141">Caption</span></span>|
|-|-|
|[<span data-ttu-id="9be2a-142">ProxyMode</span><span class="sxs-lookup"><span data-stu-id="9be2a-142">ProxyMode</span></span>](#proxymode)|<span data-ttu-id="9be2a-143">프록시 서버 설정 지정 방법 선택</span><span class="sxs-lookup"><span data-stu-id="9be2a-143">Choose how to specify proxy server settings</span></span>|
|[<span data-ttu-id="9be2a-144">ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="9be2a-144">ProxyPacUrl</span></span>](#proxypacurl)|<span data-ttu-id="9be2a-145">프록시 .pac 파일 URL</span><span class="sxs-lookup"><span data-stu-id="9be2a-145">URL to a proxy .pac file</span></span>|
|[<span data-ttu-id="9be2a-146">ProxyServer</span><span class="sxs-lookup"><span data-stu-id="9be2a-146">ProxyServer</span></span>](#proxyserver)|<span data-ttu-id="9be2a-147">프록시 서버 주소 또는 URL</span><span class="sxs-lookup"><span data-stu-id="9be2a-147">Address or URL of proxy server</span></span>|

                 
      
  
             
            
                  

## <span data-ttu-id="9be2a-148">응용 프로그램 정책</span><span class="sxs-lookup"><span data-stu-id="9be2a-148">Applications policies</span></span>

[<span data-ttu-id="9be2a-149">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="9be2a-149">Back to top</span></span>](#microsoft-edge---update-policies)
### <span data-ttu-id="9be2a-150">InstallDefault</span><span class="sxs-lookup"><span data-stu-id="9be2a-150">InstallDefault</span></span>
#### <span data-ttu-id="9be2a-151">설치 허용 기본값</span><span class="sxs-lookup"><span data-stu-id="9be2a-151">Allow installation default</span></span>
><span data-ttu-id="9be2a-152">Microsoft Edge 업데이트 1.2.145.5 이상</span><span class="sxs-lookup"><span data-stu-id="9be2a-152">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="9be2a-153">설명</span><span class="sxs-lookup"><span data-stu-id="9be2a-153">Description</span></span>
<span data-ttu-id="9be2a-154">Microsoft Edge 업데이트를 사용하는 경우 Microsoft Edge 업데이트를 허용하거나 차단하기 위해 모든 채널의 기본 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-154">You can specify the default behavior of all channels to allow or block Microsoft Edge updates when Microsoft Edge Update is used.</span></span>

<span data-ttu-id="9be2a-155">특정 채널에 대한 ‘[설치 허용](#install)’ 정책을 사용하도록 설정하여 개별 채널에 대한 이 정책을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-155">You can override this policy for individual channels by enabling the '[Allow installation](#install)' policy for specific channels.</span></span>

<span data-ttu-id="9be2a-156">이 정책을 사용하지 않도록 설정하면 Microsoft Edge 업데이트를 통한 Microsoft Edge의 설치가 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-156">If you disable this policy, the installation of Microsoft Edge through Microsoft Edge Update is blocked.</span></span> <span data-ttu-id="9be2a-157">이는 사용자가 Microsoft Edge 업데이트를 실행하고 ‘[설치 허용](#install)’ 정책을 구성하지 않은 경우에만 Microsoft Edge 소프트웨어의 설치에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-157">This only affects the installation of Microsoft Edge software only when users are running Microsoft Edge Update and when they haven't configured the '[Allow installation](#install)' policy.</span></span>

<span data-ttu-id="9be2a-158">이 정책은 Microsoft Edge 업데이트 실행을 금지하거나 사용자가 다른 방법으로 Microsoft Edge 소프트웨어를 설치하는 것을 방지하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-158">This policy doesn't prevent Microsoft Edge Update from running or prevent users from installing Microsoft Edge software using other methods.</span></span>
#### <span data-ttu-id="9be2a-159">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="9be2a-159">Windows information and settings</span></span>
##### <span data-ttu-id="9be2a-160">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="9be2a-160">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="9be2a-161">GP 고유 이름: InstallDefault</span><span class="sxs-lookup"><span data-stu-id="9be2a-161">GP unique name: InstallDefault</span></span>
- <span data-ttu-id="9be2a-162">GP 이름: 설치 허용 기본값</span><span class="sxs-lookup"><span data-stu-id="9be2a-162">GP name: Allow installation default</span></span>
- <span data-ttu-id="9be2a-163">GP 경로: 관리 템플릿/Microsoft Edge 업데이트/응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="9be2a-163">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="9be2a-164">GP ADMX 파일 이름: edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="9be2a-164">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="9be2a-165">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="9be2a-165">Windows Registry Settings</span></span>
- <span data-ttu-id="9be2a-166">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="9be2a-166">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="9be2a-167">값 이름: InstallDefault</span><span class="sxs-lookup"><span data-stu-id="9be2a-167">Value Name: InstallDefault</span></span>
- <span data-ttu-id="9be2a-168">값 형식: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="9be2a-168">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="9be2a-169">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="9be2a-169">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="9be2a-170">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="9be2a-170">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="9be2a-171">UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="9be2a-171">UpdateDefault</span></span>
#### <span data-ttu-id="9be2a-172">업데이트 정책 재정의 기본값</span><span class="sxs-lookup"><span data-stu-id="9be2a-172">Update policy override default</span></span>
><span data-ttu-id="9be2a-173">Microsoft Edge 업데이트 1.2.145.5 이상</span><span class="sxs-lookup"><span data-stu-id="9be2a-173">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="9be2a-174">설명</span><span class="sxs-lookup"><span data-stu-id="9be2a-174">Description</span></span>
<span data-ttu-id="9be2a-175">Microsoft Edge 업데이트가 Microsoft Edge에 사용 가능한 업데이트를 처리하는 방식과 관련하여 모든 채널에 대해 기본 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-175">Lets you specify the default behavior for all channels concerning the way Microsoft Edge Update handles available updates for Microsoft Edge.</span></span> <span data-ttu-id="9be2a-176">특정 채널에 ‘[업데이트 정책 재정의](#update)’ 정책을 지정하여 채널별로 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-176">Can be overridden for individual channels by specifying the '[Update policy override](#update)' policy for those specific channels.</span></span>

  <span data-ttu-id="9be2a-177">이 정책을 사용하도록 설정하면 다음 중 구성된 옵션에 따라 Microsoft Edge 업데이트가 Microsoft Edge에 대한 업데이트를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-177">If you enable this policy, Microsoft Edge Update handles Microsoft Edge updates according to how you configure the following options:</span></span>
   - <span data-ttu-id="9be2a-178">항상 업데이트 허용: 업데이트는 정기 업데이트 확인 또는 수동 업데이트 확인을 통해 검색되는 경우 항상 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-178">Always allow updates: Updates are always applied when found, either by periodic update check or by a manual update check.</span></span>
   - <span data-ttu-id="9be2a-179">자동 업데이트만: 업데이트는 정기 업데이트 확인에서 검색된 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-179">Automatic silent updates only: Updates are applied only when they're found by the periodic update check.</span></span>
   - <span data-ttu-id="9be2a-180">수동 업데이트만: 업데이트는 사용자가 수동 업데이트 확인을 실행하는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-180">Manual updates only: Updates are applied only when the user runs a manual update check.</span></span>
   - <span data-ttu-id="9be2a-181">업데이트 사용 안 함: 업데이트가 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-181">Updates disabled: Updates are never applied.</span></span>

  <span data-ttu-id="9be2a-182">수동 업데이트를 선택하는 경우 앱의 수동 업데이트 메커니즘(사용 가능한 경우)을 사용하여 정기적으로 업데이트를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-182">If you select manual updates, make sure you periodically check for updates by using the app's manual update mechanism, if available.</span></span> <span data-ttu-id="9be2a-183">업데이트를 사용하지 않도록 설정하는 경우 정기적으로 업데이트를 확인하여 사용자에게 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-183">If you disable updates, periodically check for updates, and distribute them to users.</span></span>

  <span data-ttu-id="9be2a-184">이 정책을 사용하도록 설정하고 구성하지 않으면 Microsoft Edge 업데이트는 ‘[업데이트 정책 재정의](#update)’ 정책에 지정된 대로 사용 가능한 업데이트를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-184">If you don't enable and configure this policy, Microsoft Edge Update handles available updates as specified by the '[Update policy override](#update)' policy.</span></span>
#### <span data-ttu-id="9be2a-185">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="9be2a-185">Windows information and settings</span></span>
##### <span data-ttu-id="9be2a-186">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="9be2a-186">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="9be2a-187">GP 고유 이름: UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="9be2a-187">GP unique name: UpdateDefault</span></span>
- <span data-ttu-id="9be2a-188">GP 이름: 업데이트 정책 재정의 기본값</span><span class="sxs-lookup"><span data-stu-id="9be2a-188">GP name: Update policy override default</span></span>
- <span data-ttu-id="9be2a-189">GP 경로: 관리 템플릿/Microsoft Edge 업데이트/응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="9be2a-189">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="9be2a-190">GP ADMX 파일 이름: edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="9be2a-190">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="9be2a-191">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="9be2a-191">Windows Registry Settings</span></span>
- <span data-ttu-id="9be2a-192">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="9be2a-192">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="9be2a-193">값 이름: UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="9be2a-193">Value Name: UpdateDefault</span></span>
- <span data-ttu-id="9be2a-194">값 형식: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="9be2a-194">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="9be2a-195">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="9be2a-195">Example value:</span></span>
```
0x00000003
```
[<span data-ttu-id="9be2a-196">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="9be2a-196">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="9be2a-197">설치</span><span class="sxs-lookup"><span data-stu-id="9be2a-197">Install</span></span>
#### <span data-ttu-id="9be2a-198">설치 허용</span><span class="sxs-lookup"><span data-stu-id="9be2a-198">Allow installation</span></span>
><span data-ttu-id="9be2a-199">Microsoft Edge 업데이트 1.2.145.5 이상</span><span class="sxs-lookup"><span data-stu-id="9be2a-199">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="9be2a-200">설명</span><span class="sxs-lookup"><span data-stu-id="9be2a-200">Description</span></span>
<span data-ttu-id="9be2a-201">Microsoft Edge 업데이트를 사용하여 Microsoft Edge 채널을 설치할 수 있는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-201">Specifies whether a Microsoft Edge channel can be installed using Microsoft Edge Update.</span></span>

  <span data-ttu-id="9be2a-202">채널에 대해 이 정책을 사용하도록 설정하면 사용자가 Microsoft Edge 업데이트를 통해 해당 Microsoft Edge 채널을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-202">If you enable this policy for a channel, users can install that channel of Microsoft Edge through Microsoft Edge Update.</span></span>

  <span data-ttu-id="9be2a-203">채널에 대해 이 정책을 사용하지 않도록 설정하면 사용자가 Microsoft Edge 업데이트를 통해 해당 Microsoft Edge 채널을 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-203">If you disable this policy for a channel, users cannot install that channel of Microsoft Edge through Microsoft Edge Update.</span></span>

  <span data-ttu-id="9be2a-204">채널에 대해 이 정책을 구성하지 않으면 ‘[설치 허용](#installdefault)’ 정책 구성이 사용자가 Microsoft Edge 업데이트를 통해 해당 Microsoft Edge 채널을 설치할 수 있는지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-204">If you don't configure this policy for a channel, the '[Allow installation default](#installdefault)' policy configuration determines whether users can install that channel of Microsoft Edge through Microsoft Edge Update.</span></span>
#### <span data-ttu-id="9be2a-205">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="9be2a-205">Windows information and settings</span></span>
##### <span data-ttu-id="9be2a-206">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="9be2a-206">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="9be2a-207">GP 고유 이름: Install</span><span class="sxs-lookup"><span data-stu-id="9be2a-207">GP unique name: Install</span></span>
- <span data-ttu-id="9be2a-208">GP 이름: 설치 허용</span><span class="sxs-lookup"><span data-stu-id="9be2a-208">GP name: Allow installation</span></span>
- <span data-ttu-id="9be2a-209">GP 경로:</span><span class="sxs-lookup"><span data-stu-id="9be2a-209">GP path:</span></span> 
  - <span data-ttu-id="9be2a-210">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="9be2a-210">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="9be2a-211">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="9be2a-211">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="9be2a-212">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="9be2a-212">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="9be2a-213">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="9be2a-213">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="9be2a-214">GP ADMX 파일 이름: edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="9be2a-214">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="9be2a-215">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="9be2a-215">Windows Registry Settings</span></span>
- <span data-ttu-id="9be2a-216">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="9be2a-216">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="9be2a-217">값 이름:</span><span class="sxs-lookup"><span data-stu-id="9be2a-217">Value Name:</span></span> 
  - <span data-ttu-id="9be2a-218">(Stable): Install{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="9be2a-218">(Stable): Install{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="9be2a-219">(Beta): Install{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="9be2a-219">(Beta): Install{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="9be2a-220">(Canary): Install{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="9be2a-220">(Canary): Install{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="9be2a-221">(Dev): Install{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="9be2a-221">(Dev): Install{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="9be2a-222">값 형식: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="9be2a-222">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="9be2a-223">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="9be2a-223">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="9be2a-224">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="9be2a-224">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="9be2a-225">업데이트</span><span class="sxs-lookup"><span data-stu-id="9be2a-225">Update</span></span>
#### <span data-ttu-id="9be2a-226">업데이트 정책 재정의</span><span class="sxs-lookup"><span data-stu-id="9be2a-226">Update policy override</span></span>
><span data-ttu-id="9be2a-227">Microsoft Edge 업데이트 1.2.145.5 이상</span><span class="sxs-lookup"><span data-stu-id="9be2a-227">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="9be2a-228">설명</span><span class="sxs-lookup"><span data-stu-id="9be2a-228">Description</span></span>
<span data-ttu-id="9be2a-229">Microsoft Edge 업데이트가 Microsoft Edge에서 사용 가능한 업데이트를 처리하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-229">Specifies how Microsoft Edge Update handles available updates from Microsoft Edge.</span></span>

  <span data-ttu-id="9be2a-230">이 정책을 사용하도록 설정하면 다음 중 구성된 옵션에 따라 Microsoft Edge 업데이트가 Microsoft Edge에 대한 업데이트를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-230">If you enable this policy, Microsoft Edge Update handles Microsoft Edge updates according to how you configure the following options:</span></span>
   - <span data-ttu-id="9be2a-231">항상 업데이트 허용: 업데이트는 정기 업데이트 확인 또는 수동 업데이트 확인을 통해 검색되는 경우 항상 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-231">Always allow updates: Updates are always applied when found, either by periodic update check or by a manual update check.</span></span>
   - <span data-ttu-id="9be2a-232">자동 업데이트만: 업데이트는 정기 업데이트 확인에서 검색된 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-232">Automatic silent updates only: Updates are applied only when they're found by the periodic update check.</span></span>
   - <span data-ttu-id="9be2a-233">수동 업데이트만: 업데이트는 사용자가 수동 업데이트 확인을 실행하는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-233">Manual updates only: Updates are applied only when the user runs a manual update check.</span></span> <span data-ttu-id="9be2a-234">(일부 앱은 이 옵션에 대한 인터페이스를 제공하지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="9be2a-234">(Not all apps provide an interface for this option.)</span></span>
   - <span data-ttu-id="9be2a-235">업데이트 사용 안 함: 업데이트가 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-235">Updates disabled: Updates are never applied.</span></span>

  <span data-ttu-id="9be2a-236">수동 업데이트를 선택하는 경우 앱의 수동 업데이트 메커니즘(사용 가능한 경우)을 사용하여 정기적으로 업데이트를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-236">If you select manual updates, make sure you periodically check for updates by using the app's manual update mechanism, if available.</span></span> <span data-ttu-id="9be2a-237">업데이트를 사용하지 않도록 설정하는 경우 정기적으로 업데이트를 확인하여 사용자에게 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-237">If you disable updates, periodically check for updates, and distribute them to users.</span></span>

  <span data-ttu-id="9be2a-238">이 정책을 사용하도록 설정하고 구성하지 않으면 Microsoft Edge 업데이트는 ‘[업데이트 정책 재정의 기본값](#updatedefault)’ 정책에 지정된 대로 사용 가능한 업데이트를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-238">If you don't enable and configure this policy, Microsoft Edge Update handles available updates as specified by the '[Update policy override default](#updatedefault)' policy.</span></span>
#### <span data-ttu-id="9be2a-239">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="9be2a-239">Windows information and settings</span></span>
##### <span data-ttu-id="9be2a-240">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="9be2a-240">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="9be2a-241">GP 고유 이름: Update</span><span class="sxs-lookup"><span data-stu-id="9be2a-241">GP unique name: Update</span></span>
- <span data-ttu-id="9be2a-242">GP 이름: 업데이트 정책 재정의</span><span class="sxs-lookup"><span data-stu-id="9be2a-242">GP name: Update policy override</span></span>
- <span data-ttu-id="9be2a-243">GP 경로:</span><span class="sxs-lookup"><span data-stu-id="9be2a-243">GP path:</span></span> 
  - <span data-ttu-id="9be2a-244">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="9be2a-244">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="9be2a-245">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="9be2a-245">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="9be2a-246">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="9be2a-246">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="9be2a-247">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="9be2a-247">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="9be2a-248">GP ADMX 파일 이름: edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="9be2a-248">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="9be2a-249">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="9be2a-249">Windows Registry Settings</span></span>
- <span data-ttu-id="9be2a-250">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="9be2a-250">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="9be2a-251">값 이름:</span><span class="sxs-lookup"><span data-stu-id="9be2a-251">Value Name:</span></span> 
  - <span data-ttu-id="9be2a-252">(Stable): Update{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="9be2a-252">(Stable): Update{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="9be2a-253">(Beta): Update{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="9be2a-253">(Beta): Update{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="9be2a-254">(Canary): Update{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="9be2a-254">(Canary): Update{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="9be2a-255">(Dev): Update{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="9be2a-255">(Dev): Update{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="9be2a-256">값 형식: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="9be2a-256">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="9be2a-257">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="9be2a-257">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="9be2a-258">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="9be2a-258">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="9be2a-259">Allowsxs</span><span class="sxs-lookup"><span data-stu-id="9be2a-259">Allowsxs</span></span>
#### <span data-ttu-id="9be2a-260">Microsoft Edge 함께 사용 브라우저 환경 허용</span><span class="sxs-lookup"><span data-stu-id="9be2a-260">Allow Microsoft Edge Side by Side browser experience</span></span>
><span data-ttu-id="9be2a-261">Microsoft Edge 업데이트 1.2.145.5 이상</span><span class="sxs-lookup"><span data-stu-id="9be2a-261">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="9be2a-262">설명</span><span class="sxs-lookup"><span data-stu-id="9be2a-262">Description</span></span>
<span data-ttu-id="9be2a-263">이 정책은 사용자가 Microsoft Edge(Edge HTML) 및 Microsoft Edge(Chromium 기반)을 함께 실행할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-263">This policy lets a user run Microsoft Edge (Edge HTML) and Microsoft Edge (Chromium-based) side-by-side.</span></span>

<span data-ttu-id="9be2a-264">이 정책을 "구성되지 않음"으로 설정하면 Microsoft Edge(Chromium 기반) 안정 채널 및 2019년 11월 보안 업데이트가 설치된 후 Microsoft Edge(Chromium 기반)가 Microsoft Edge(Edge HTML)를 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-264">If this policy is set to “Not configured”, Microsoft Edge (Chromium-based) will replace Microsoft Edge (Edge HTML) after the Microsoft Edge (Chromium-based) stable channel and the November 2019 security updates are installed.</span></span>  <span data-ttu-id="9be2a-265">이는 "사용 안 함" 설정과 동일한 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-265">This is the same behavior as the “Disabled” setting.</span></span>

<span data-ttu-id="9be2a-266">"사용 안 함" 설정은 함께 사용 환경을 차단하고 Microsoft Edge(Chromium 기반) 안정 채널 및 2019년 11월 보안 업데이트가 설치된 후 Microsoft Edge(Chromium 기반)가 Microsoft Edge(Edge HTML)를 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-266">The “Disabled” setting blocks a side-by-side experience and Microsoft Edge (Chromium-based) will replace Microsoft Edge (Edge HTML) after the Microsoft Edge (Chromium-based) stable channel and the November 2019 security updates are installed.</span></span>  <span data-ttu-id="9be2a-267">이는 "구성되지 않음" 설정과 동일한 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-267">This is the same behavior as the “Not Configured” setting.</span></span>

<span data-ttu-id="9be2a-268">이 정책을 "사용"으로 설정하면 Microsoft Edge(Chromium 기반)이 설치된 후 Microsoft Edge(Chromium 기반)와 Microsoft Edge(Edge HTML)를 함께 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-268">When this policy is “Enabled”, Microsoft Edge (Chromium-based) and Microsoft Edge (Edge HTML) can run side-by-side after Microsoft Edge (Chromium-based) is installed.</span></span>

<span data-ttu-id="9be2a-269">이 그룹 정책을 적용하려면 Windows 업데이트가 Microsoft Edge(Chromium 기반)를 자동으로 설치하기 전에 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-269">For this group policy to take affect, it must be configured before the automatic install of Microsoft Edge (Chromium-based) by Windows Update.</span></span> <span data-ttu-id="9be2a-270">참고: 사용자는 Microsoft Edge(Chromium 기반) 차단 도구 키트를 사용하여 Microsoft Edge(Chromium 기반) 자동 업데이트를 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-270">Note: A user can block the automatic update of Microsoft Edge (Chromium-based) by using the Microsoft Edge (Chromium-based) Blocker Toolkit.</span></span>
#### <span data-ttu-id="9be2a-271">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="9be2a-271">Windows information and settings</span></span>
##### <span data-ttu-id="9be2a-272">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="9be2a-272">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="9be2a-273">GP 고유 이름: Allowsxs</span><span class="sxs-lookup"><span data-stu-id="9be2a-273">GP unique name: Allowsxs</span></span>
- <span data-ttu-id="9be2a-274">GP 이름: Microsoft Edge 함께 사용 브라우저 환경 허용</span><span class="sxs-lookup"><span data-stu-id="9be2a-274">GP name: Allow Microsoft Edge Side by Side browser experience</span></span>
- <span data-ttu-id="9be2a-275">GP 경로: 관리 템플릿/Microsoft Edge 업데이트/응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="9be2a-275">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="9be2a-276">GP ADMX 파일 이름: edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="9be2a-276">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="9be2a-277">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="9be2a-277">Windows Registry Settings</span></span>
- <span data-ttu-id="9be2a-278">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="9be2a-278">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="9be2a-279">값 이름: Allowsxs</span><span class="sxs-lookup"><span data-stu-id="9be2a-279">Value Name: Allowsxs</span></span>
- <span data-ttu-id="9be2a-280">값 형식: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="9be2a-280">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="9be2a-281">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="9be2a-281">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="9be2a-282">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="9be2a-282">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="9be2a-283">CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="9be2a-283">CreateDesktopShortcutDefault</span></span>
#### <span data-ttu-id="9be2a-284">기본 설치 시 데스크톱 바로 가기 만들기 방지</span><span class="sxs-lookup"><span data-stu-id="9be2a-284">Prevent Desktop Shortcut creation upon install default</span></span>
><span data-ttu-id="9be2a-285">Microsoft Edge 업데이트 1.3.128.0 이상</span><span class="sxs-lookup"><span data-stu-id="9be2a-285">Microsoft Edge Update 1.3.128.0 and later</span></span>

#### <span data-ttu-id="9be2a-286">설명</span><span class="sxs-lookup"><span data-stu-id="9be2a-286">Description</span></span>
<span data-ttu-id="9be2a-287">Microsoft Edge가 설치된 경우 데스크톱 바로 가기를 만들기 위한 모든 채널에 대한 기본 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-287">Lets you specify the default behavior for all channels for creating a desktop shortcut when Microsoft Edge is installed.</span></span>

  <span data-ttu-id="9be2a-288">이 정책을 사용하도록 설정하는 경우 Microsoft Edge가 설치될 때 데스크톱 바로 가기가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-288">If you enable this policy a desktop shortcut is created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="9be2a-289">이 정책을 사용하지 않도록 설정하는 경우 Microsoft Edge가 설치될 때 데스크톱 바로 가기가 만들어지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-289">If you disable this policy, no desktop shortcut will be created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="9be2a-290">이 정책을 구성하지 않으면 Microsoft Edge로의 데스크톱 바로 가기가 설치 도중에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-290">If you don’t configure this policy a desktop shortcut to Microsoft Edge will be created during installation.</span></span>
<span data-ttu-id="9be2a-291">Microsoft Edge가 이미 설치되어 있는 경우 이 정책은 아무런 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-291">If Microsoft Edge is already installed, this policy will have no effect.</span></span>
#### <span data-ttu-id="9be2a-292">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="9be2a-292">Windows information and settings</span></span>
##### <span data-ttu-id="9be2a-293">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="9be2a-293">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="9be2a-294">GP 고유 이름: CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="9be2a-294">GP unique name: CreateDesktopShortcutDefault</span></span>
- <span data-ttu-id="9be2a-295">GP 이름: 기본값을 설치 시 데스크톱 바로 가기 만들기를 방지</span><span class="sxs-lookup"><span data-stu-id="9be2a-295">GP name: Prevent Desktop Shortcut creation upon install default</span></span>
- <span data-ttu-id="9be2a-296">GP 경로: 관리 템플릿/Microsoft Edge 업데이트/응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="9be2a-296">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="9be2a-297">GP ADMX 파일 이름: edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="9be2a-297">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="9be2a-298">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="9be2a-298">Windows Registry Settings</span></span>
- <span data-ttu-id="9be2a-299">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="9be2a-299">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="9be2a-300">값 이름: CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="9be2a-300">Value Name: CreateDesktopShortcutDefault</span></span>
- <span data-ttu-id="9be2a-301">값 형식: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="9be2a-301">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="9be2a-302">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="9be2a-302">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="9be2a-303">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="9be2a-303">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="9be2a-304">CreateDesktopShortcut</span><span class="sxs-lookup"><span data-stu-id="9be2a-304">CreateDesktopShortcut</span></span>
#### <span data-ttu-id="9be2a-305">설치 시 데스크톱 바로 가기 만들기를 방지</span><span class="sxs-lookup"><span data-stu-id="9be2a-305">Prevent Desktop Shortcut creation upon install</span></span>
><span data-ttu-id="9be2a-306">Microsoft Edge 업데이트 1.3.128.0 이상</span><span class="sxs-lookup"><span data-stu-id="9be2a-306">Microsoft Edge Update 1.3.128.0 and later</span></span>

#### <span data-ttu-id="9be2a-307">설명</span><span class="sxs-lookup"><span data-stu-id="9be2a-307">Description</span></span>
<span data-ttu-id="9be2a-308">이 정책을 사용하도록 설정하는 경우 Microsoft Edge가 설치될 때 데스크톱 바로 가기가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-308">If you enable this policy a desktop shortcut is created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="9be2a-309">이 정책을 사용하지 않도록 설정하는 경우 Microsoft Edge가 설치될 때 데스크톱 바로 가기가 만들어지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-309">If you disable this policy, no desktop shortcut will be created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="9be2a-310">이 정책을 구성하지 않으면 Microsoft Edge로의 데스크톱 바로 가기가 설치 도중에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-310">If you don’t configure this policy a desktop shortcut to Microsoft Edge will be created during installation.</span></span>
<span data-ttu-id="9be2a-311">Microsoft Edge가 이미 설치되어 있는 경우 이 정책은 아무런 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-311">If Microsoft Edge is already installed, this policy will have no effect.</span></span>

  <span data-ttu-id="9be2a-312">채널에 대한 이 정책을 구성하지 않는 경우 '[설치시 바탕 화면 바로 가기 만들기 방지 기본](#createdesktopshortcutdefault)' 정책 구성에 따라 Microsoft Edge 설치시 바로 가기 만들기를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-312">If you don't configure this policy for a channel, the '[Prevent Desktop Shortcut creation upon install default](#createdesktopshortcutdefault)' policy configuration determines shortcut creation when Microsoft Edge is installed.</span></span>
#### <span data-ttu-id="9be2a-313">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="9be2a-313">Windows information and settings</span></span>
##### <span data-ttu-id="9be2a-314">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="9be2a-314">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="9be2a-315">GP 고유 이름: CreateDesktopShortcut</span><span class="sxs-lookup"><span data-stu-id="9be2a-315">GP unique name: CreateDesktopShortcut</span></span>
- <span data-ttu-id="9be2a-316">GP 이름: 설치 시 데스크톱 바로 가기 만들기를 방지</span><span class="sxs-lookup"><span data-stu-id="9be2a-316">GP name: Prevent Desktop Shortcut creation upon install</span></span>
- <span data-ttu-id="9be2a-317">GP 경로:</span><span class="sxs-lookup"><span data-stu-id="9be2a-317">GP path:</span></span> 
  - <span data-ttu-id="9be2a-318">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="9be2a-318">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="9be2a-319">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="9be2a-319">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="9be2a-320">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="9be2a-320">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="9be2a-321">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="9be2a-321">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="9be2a-322">GP ADMX 파일 이름: edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="9be2a-322">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="9be2a-323">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="9be2a-323">Windows Registry Settings</span></span>
- <span data-ttu-id="9be2a-324">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="9be2a-324">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="9be2a-325">값 이름:</span><span class="sxs-lookup"><span data-stu-id="9be2a-325">Value Name:</span></span> 
  - <span data-ttu-id="9be2a-326">(안정): CreateDesktopShortcut{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="9be2a-326">(Stable): CreateDesktopShortcut{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="9be2a-327">(베타): CreateDesktopShortcut{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="9be2a-327">(Beta): CreateDesktopShortcut{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="9be2a-328">(카나리아): CreateDesktopShortcut{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="9be2a-328">(Canary): CreateDesktopShortcut{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="9be2a-329">(Dev): CreateDesktopShortcut{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="9be2a-329">(Dev): CreateDesktopShortcut{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="9be2a-330">값 형식: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="9be2a-330">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="9be2a-331">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="9be2a-331">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="9be2a-332">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="9be2a-332">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="9be2a-333">TargetVersionPrefix</span><span class="sxs-lookup"><span data-stu-id="9be2a-333">TargetVersionPrefix</span></span>
#### <span data-ttu-id="9be2a-334">대상 버전 재정의</span><span class="sxs-lookup"><span data-stu-id="9be2a-334">Target version override</span></span>
><span data-ttu-id="9be2a-335">Microsoft Edge 업데이트 1.3.119.43 이상</span><span class="sxs-lookup"><span data-stu-id="9be2a-335">Microsoft Edge Update 1.3.119.43 and later</span></span>

#### <span data-ttu-id="9be2a-336">설명</span><span class="sxs-lookup"><span data-stu-id="9be2a-336">Description</span></span>
<span data-ttu-id="9be2a-337">이 정책을 사용하도록 설정하고 자동 업데이트를 사용하도록 설정하면 Microsoft Edge는 이 정책 값이 지정하는 버전으로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-337">When this policy is enabled, and auto-update is enabled, Microsoft Edge will be updated to the version specified by this policy value.</span></span>

<span data-ttu-id="9be2a-338">정책 값은 특정 Microsoft Edge 버전(예: 83.0.499.12) 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-338">The policy value must be a specific Microsoft Edge version, e.g. 83.0.499.12.</span></span>

<span data-ttu-id="9be2a-339">장치에 지정된 값보다 더 최신 버전의 Microsoft Edge가 있는 경우 Microsoft Edge는 최신 버전을 유지하고 지정된 버전으로 다운그레이드되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-339">If a device has newer version of Microsoft Edge than the value specified, Microsoft Edge will remain on the newer version and not downgrade to the specified version.</span></span>

<span data-ttu-id="9be2a-340">지정된 버전이 존재하지 않거나 형식이 잘못된 경우 Microsoft Edge는 현재 버전을 유지하고 이후 버전으로 자동 업데이트되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-340">If the specified version does not exist, or is improperly formatted, then Microsoft Edge will remain on its current version and not update to future versions automatically.</span></span>
#### <span data-ttu-id="9be2a-341">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="9be2a-341">Windows information and settings</span></span>
##### <span data-ttu-id="9be2a-342">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="9be2a-342">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="9be2a-343">GP 고유 이름: TargetVersionPrefix</span><span class="sxs-lookup"><span data-stu-id="9be2a-343">GP unique name: TargetVersionPrefix</span></span>
- <span data-ttu-id="9be2a-344">GP 이름: 대상 버전 재정의</span><span class="sxs-lookup"><span data-stu-id="9be2a-344">GP name: Target version override</span></span>
- <span data-ttu-id="9be2a-345">GP 경로:</span><span class="sxs-lookup"><span data-stu-id="9be2a-345">GP path:</span></span> 
  - <span data-ttu-id="9be2a-346">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="9be2a-346">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="9be2a-347">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="9be2a-347">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="9be2a-348">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="9be2a-348">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="9be2a-349">관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="9be2a-349">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="9be2a-350">GP ADMX 파일 이름: edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="9be2a-350">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="9be2a-351">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="9be2a-351">Windows Registry Settings</span></span>
- <span data-ttu-id="9be2a-352">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="9be2a-352">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="9be2a-353">값 이름:</span><span class="sxs-lookup"><span data-stu-id="9be2a-353">Value Name:</span></span> 
  - <span data-ttu-id="9be2a-354">(Stable): TargetVersionPrefix{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="9be2a-354">(Stable): TargetVersionPrefix{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="9be2a-355">(Beta): TargetVersionPrefix{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="9be2a-355">(Beta): TargetVersionPrefix{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="9be2a-356">(Canary): TargetVersionPrefix{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="9be2a-356">(Canary): TargetVersionPrefix{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="9be2a-357">(Dev): TargetVersionPrefix{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="9be2a-357">(Dev): TargetVersionPrefix{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="9be2a-358">값 형식: REG_SZ</span><span class="sxs-lookup"><span data-stu-id="9be2a-358">Value Type: REG_SZ</span></span>
##### <span data-ttu-id="9be2a-359">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="9be2a-359">Example value:</span></span>
```
83.0.499.12
```
[<span data-ttu-id="9be2a-360">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="9be2a-360">Back to top</span></span>](#microsoft-edge---update-policies)


## <span data-ttu-id="9be2a-361">기본 설정 정책</span><span class="sxs-lookup"><span data-stu-id="9be2a-361">Preferences policies</span></span>

[<span data-ttu-id="9be2a-362">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="9be2a-362">Back to top</span></span>](#microsoft-edge---update-policies)
### <span data-ttu-id="9be2a-363">AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="9be2a-363">AutoUpdateCheckPeriodMinutes</span></span>
#### <span data-ttu-id="9be2a-364">자동 업데이트 확인 기간 재정의</span><span class="sxs-lookup"><span data-stu-id="9be2a-364">Auto-update check period override</span></span>
><span data-ttu-id="9be2a-365">Microsoft Edge 업데이트 1.2.145.5 이상</span><span class="sxs-lookup"><span data-stu-id="9be2a-365">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="9be2a-366">설명</span><span class="sxs-lookup"><span data-stu-id="9be2a-366">Description</span></span>
<span data-ttu-id="9be2a-367">이 정책을 사용하도록 설정하면 자동 업데이트 확인 최소 간격(분) 값을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-367">If enabled, this policy lets you set a value for the minimum number of minutes between automatic update checks.</span></span> <span data-ttu-id="9be2a-368">그렇지 않으면 기본적으로 자동 업데이트는 10시간마다 업데이트를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-368">Otherwise, by default, auto-update checks for updates every 10 hours.</span></span>

  <span data-ttu-id="9be2a-369">모든 자동 업데이트 확인을 사용하지 않도록 설정하려면 이 값을 0으로 설정합니다(권장하지 않음).</span><span class="sxs-lookup"><span data-stu-id="9be2a-369">If you want to disable all auto-update checks, set the value to 0 (not recommended).</span></span>
#### <span data-ttu-id="9be2a-370">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="9be2a-370">Windows information and settings</span></span>
##### <span data-ttu-id="9be2a-371">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="9be2a-371">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="9be2a-372">GP 고유 이름: AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="9be2a-372">GP unique name: AutoUpdateCheckPeriodMinutes</span></span>
- <span data-ttu-id="9be2a-373">GP 이름: 자동 업데이트 확인 기간 재정의</span><span class="sxs-lookup"><span data-stu-id="9be2a-373">GP name: Auto-update check period override</span></span>
- <span data-ttu-id="9be2a-374">GP 경로: 관리 템플릿/Microsoft Edge 업데이트/기본 설정</span><span class="sxs-lookup"><span data-stu-id="9be2a-374">GP path: Administrative Templates/Microsoft Edge Update/Preferences</span></span>
- <span data-ttu-id="9be2a-375">GP ADMX 파일 이름: edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="9be2a-375">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="9be2a-376">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="9be2a-376">Windows Registry Settings</span></span>
- <span data-ttu-id="9be2a-377">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="9be2a-377">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="9be2a-378">값 이름: AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="9be2a-378">Value Name: AutoUpdateCheckPeriodMinutes</span></span>
- <span data-ttu-id="9be2a-379">값 형식: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="9be2a-379">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="9be2a-380">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="9be2a-380">Example value:</span></span>
```
0x00000578
```
[<span data-ttu-id="9be2a-381">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="9be2a-381">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="9be2a-382">UpdatesSuppressed</span><span class="sxs-lookup"><span data-stu-id="9be2a-382">UpdatesSuppressed</span></span>
#### <span data-ttu-id="9be2a-383">매일 자동 업데이트 확인 억제 기간</span><span class="sxs-lookup"><span data-stu-id="9be2a-383">Time period in each day to suppress auto-update check</span></span>
><span data-ttu-id="9be2a-384">Microsoft Edge 업데이트 1.3.33.5 이상</span><span class="sxs-lookup"><span data-stu-id="9be2a-384">Microsoft Edge Update 1.3.33.5 and later</span></span>

#### <span data-ttu-id="9be2a-385">설명</span><span class="sxs-lookup"><span data-stu-id="9be2a-385">Description</span></span>
<span data-ttu-id="9be2a-386">이 정책을 사용하도록 설정하면 업데이트 확인이 시:분부터 시작하여 기간(분) 동안 억제됩니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-386">If you enable this policy, update checks are suppressed each day starting at Hour:Minute for a period of Duration (in minutes).</span></span> <span data-ttu-id="9be2a-387">기간은 일광 절약 시간에 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-387">Duration isn't affected by daylight saving time.</span></span> <span data-ttu-id="9be2a-388">예를 들어 시작 시간이 22:00이고 기간이 480분인 경우 업데이트는 이 기간 동안 일광 절약 시간제가 시작하거나 종료하는지 관계없이 정확히 8시간 동안 억제됩니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-388">For example, if the start time is 22:00 and the duration is 480 minutes, updates will be suppressed for exactly 8 hours, regardless of whether daylight saving time starts or ends during this period.</span></span>

  <span data-ttu-id="9be2a-389">이 정책을 사용하지 않도록 설정하거나 구성하지 않으면 특정 기간 동안 업데이트 검사가 억제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-389">If you disable or don't configure this policy, update checks aren't suppressed during any specific period.</span></span>
#### <span data-ttu-id="9be2a-390">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="9be2a-390">Windows information and settings</span></span>
##### <span data-ttu-id="9be2a-391">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="9be2a-391">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="9be2a-392">GP 고유 이름: UpdatesSuppressed</span><span class="sxs-lookup"><span data-stu-id="9be2a-392">GP unique name: UpdatesSuppressed</span></span>
- <span data-ttu-id="9be2a-393">GP 이름: 매일 자동 업데이트 확인 억제 기간</span><span class="sxs-lookup"><span data-stu-id="9be2a-393">GP name: Time period in each day to suppress auto-update check</span></span>
  - <span data-ttu-id="9be2a-394">Options { Hour, Minute, Duration }</span><span class="sxs-lookup"><span data-stu-id="9be2a-394">Options { Hour, Minute, Duration }</span></span>
- <span data-ttu-id="9be2a-395">GP 경로: 관리 템플릿/Microsoft Edge 업데이트/기본 설정</span><span class="sxs-lookup"><span data-stu-id="9be2a-395">GP path: Administrative Templates/Microsoft Edge Update/Preferences</span></span>
- <span data-ttu-id="9be2a-396">GP ADMX 파일 이름: edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="9be2a-396">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="9be2a-397">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="9be2a-397">Windows Registry Settings</span></span>
- <span data-ttu-id="9be2a-398">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="9be2a-398">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="9be2a-399">값 이름:</span><span class="sxs-lookup"><span data-stu-id="9be2a-399">Value Name:</span></span> 
  - <span data-ttu-id="9be2a-400">UpdatesSuppressedDurationMin</span><span class="sxs-lookup"><span data-stu-id="9be2a-400">UpdatesSuppressedDurationMin</span></span>
  - <span data-ttu-id="9be2a-401">UpdatesSuppressedStartHour</span><span class="sxs-lookup"><span data-stu-id="9be2a-401">UpdatesSuppressedStartHour</span></span>
  - <span data-ttu-id="9be2a-402">UpdatesSuppressedStartMin</span><span class="sxs-lookup"><span data-stu-id="9be2a-402">UpdatesSuppressedStartMin</span></span>
- <span data-ttu-id="9be2a-403">값 형식: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="9be2a-403">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="9be2a-404">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="9be2a-404">Example value:</span></span>
```
duration   : 0x0000003c
start hour : 0x00000001
start min  : 0x00000002
```
[<span data-ttu-id="9be2a-405">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="9be2a-405">Back to top</span></span>](#microsoft-edge---update-policies)


## <span data-ttu-id="9be2a-406">프록시 서버 정책</span><span class="sxs-lookup"><span data-stu-id="9be2a-406">Proxy Server policies</span></span>
  
  

[<span data-ttu-id="9be2a-407">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="9be2a-407">Back to top</span></span>](#microsoft-edge---update-policies)
### <span data-ttu-id="9be2a-408">ProxyMode</span><span class="sxs-lookup"><span data-stu-id="9be2a-408">ProxyMode</span></span>
#### <span data-ttu-id="9be2a-409">프록시 서버 설정 지정 방법 선택</span><span class="sxs-lookup"><span data-stu-id="9be2a-409">Choose how to specify proxy server settings</span></span>
><span data-ttu-id="9be2a-410">Microsoft Edge 업데이트 1.3.21.81 이상</span><span class="sxs-lookup"><span data-stu-id="9be2a-410">Microsoft Edge Update 1.3.21.81 and later</span></span>

#### <span data-ttu-id="9be2a-411">설명</span><span class="sxs-lookup"><span data-stu-id="9be2a-411">Description</span></span>
<span data-ttu-id="9be2a-412">Microsoft Edge 업데이트에서 사용되는 프록시 서버 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-412">Allows you to specify the proxy server settings that are used by Microsoft Edge Update.</span></span>

  <span data-ttu-id="9be2a-413">이 정책을 사용하도록 설정하면 다음 프록시 서버 옵션 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-413">If you enable this policy, you can choose between the following proxy server options:</span></span>
   - <span data-ttu-id="9be2a-414">프록시 서버를 사용하지 않도록 선택하고 항상 직접 연결하는 경우 다른 모든 옵션은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-414">If you choose to never use a proxy server and always connect directly, all other options are ignored.</span></span>
   - <span data-ttu-id="9be2a-415">시스템 프록시 설정을 사용하거나 프록시 서버를 자동으로 검색하도록 선택하는 경우 다른 모든 옵션은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-415">If you choose to use system proxy settings or auto-detect the proxy server, all other options are ignored.</span></span>
   - <span data-ttu-id="9be2a-416">고정 서버 프록시 모드를 선택하는 경우에는 ‘[프록시 서버 주소 또는 URL](#proxyserver)’정책에 추가 옵션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-416">If you choose fixed server proxy mode, you can specify further options in '[Address or URL of proxy server](#proxyserver)' policy.</span></span>
   - <span data-ttu-id="9be2a-417">.pac 프록시 스크립트를 사용하도록 선택하는 경우 ‘[프록시 .pac 파일 URL](#proxypacurl)’ 정책에서 스크립트의 URL을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-417">If you choose to use a .pac proxy script, you must specify the URL for the script in '[URL to a proxy .pac file](#proxypacurl)' policy.</span></span>

  <span data-ttu-id="9be2a-418">이 정책을 사용하도록 설정하면 조직의 사용자가 Microsoft Edge 업데이트에서 프록시 설정을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-418">If you enable this policy, users in your organization can't change the proxy settings in Microsoft Edge Update.</span></span>

  <span data-ttu-id="9be2a-419">이 정책을 사용하지 않도록 설정하거나 구성하지 않으면 프록시 서버 설정이 구성되지 않지만 조직의사용자가 Microsoft Edge 업데이트에 대한 고유한 프록시 설정을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-419">If you disable or don't configure this policy, no proxy server settings are configured, but users in your organization can choose their own proxy settings for Microsoft Edge Update.</span></span>
#### <span data-ttu-id="9be2a-420">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="9be2a-420">Windows information and settings</span></span>
##### <span data-ttu-id="9be2a-421">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="9be2a-421">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="9be2a-422">GP 고유 이름: ProxyMode</span><span class="sxs-lookup"><span data-stu-id="9be2a-422">GP unique name: ProxyMode</span></span>
- <span data-ttu-id="9be2a-423">GP 이름: 프록시 서버 설정 지정 방법 선택</span><span class="sxs-lookup"><span data-stu-id="9be2a-423">GP name: Choose how to specify proxy server settings</span></span>
- <span data-ttu-id="9be2a-424">GP 경로: 관리 템플릿/Microsoft Edge 업데이트/프록시 서버</span><span class="sxs-lookup"><span data-stu-id="9be2a-424">GP path: Administrative Templates/Microsoft Edge Update/Proxy Server</span></span>
- <span data-ttu-id="9be2a-425">GP ADMX 파일 이름: edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="9be2a-425">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="9be2a-426">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="9be2a-426">Windows Registry Settings</span></span>
- <span data-ttu-id="9be2a-427">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="9be2a-427">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="9be2a-428">값 이름: ProxyMode</span><span class="sxs-lookup"><span data-stu-id="9be2a-428">Value Name: ProxyMode</span></span>
- <span data-ttu-id="9be2a-429">값 형식: REG_SZ</span><span class="sxs-lookup"><span data-stu-id="9be2a-429">Value Type: REG_SZ</span></span>
##### <span data-ttu-id="9be2a-430">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="9be2a-430">Example value:</span></span>
```
fixed_servers
```
[<span data-ttu-id="9be2a-431">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="9be2a-431">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="9be2a-432">ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="9be2a-432">ProxyPacUrl</span></span>
#### <span data-ttu-id="9be2a-433">프록시 .pac 파일 URL</span><span class="sxs-lookup"><span data-stu-id="9be2a-433">URL to a proxy .pac file</span></span>
><span data-ttu-id="9be2a-434">Microsoft Edge 업데이트 1.3.21.81 이상</span><span class="sxs-lookup"><span data-stu-id="9be2a-434">Microsoft Edge Update 1.3.21.81 and later</span></span>

#### <span data-ttu-id="9be2a-435">설명</span><span class="sxs-lookup"><span data-stu-id="9be2a-435">Description</span></span>
<span data-ttu-id="9be2a-436">PAC(프록시 자동 구성) 파일의 URL을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-436">Allows you to specify a URL for a proxy auto-config (PAC) file.</span></span>

  <span data-ttu-id="9be2a-437">이 정책을 사용하면 PAC 파일의 URL을 지정하여 Microsoft Edge 업데이트가 특정 웹 사이트를 가져오는 데 적합한 프록시 서버를 선택하는 방법을 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-437">If you enable this policy, you can specify a URL for a PAC file to automate how Microsoft Edge Update selects the appropriate proxy server for fetching a particular website.</span></span>

  <span data-ttu-id="9be2a-438">이 정책은 ‘[프록시 서버 설정 지정 방법 선택](#proxymode)’ 정책에서 수동 프록시 설정을 지정한 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-438">This policy is applied only if you have specified manual proxy settings in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>

  <span data-ttu-id="9be2a-439">‘[프록시 서버 설정 지정 방법 선택](#proxymode)‘ 정책에서 수동 이외의 프록시 설정을 선택한 경우 이 정책을 구성하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="9be2a-439">Don't configure this policy if you have selected a proxy setting other than manual in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>
#### <span data-ttu-id="9be2a-440">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="9be2a-440">Windows information and settings</span></span>
##### <span data-ttu-id="9be2a-441">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="9be2a-441">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="9be2a-442">GP 고유 이름: ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="9be2a-442">GP unique name: ProxyPacUrl</span></span>
- <span data-ttu-id="9be2a-443">GP 이름: 프록시 .pac 파일 URL</span><span class="sxs-lookup"><span data-stu-id="9be2a-443">GP name: URL to a proxy .pac file</span></span>
- <span data-ttu-id="9be2a-444">GP 경로: 관리 템플릿/Microsoft Edge 업데이트/프록시 서버</span><span class="sxs-lookup"><span data-stu-id="9be2a-444">GP path: Administrative Templates/Microsoft Edge Update/Proxy Server</span></span>
- <span data-ttu-id="9be2a-445">GP ADMX 파일 이름: edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="9be2a-445">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="9be2a-446">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="9be2a-446">Windows Registry Settings</span></span>
- <span data-ttu-id="9be2a-447">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="9be2a-447">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="9be2a-448">값 이름: ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="9be2a-448">Value Name: ProxyPacUrl</span></span>
- <span data-ttu-id="9be2a-449">값 형식: REG_SZ</span><span class="sxs-lookup"><span data-stu-id="9be2a-449">Value Type: REG_SZ</span></span>
##### <span data-ttu-id="9be2a-450">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="9be2a-450">Example value:</span></span>
```
https://www.microsoft.com
```
[<span data-ttu-id="9be2a-451">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="9be2a-451">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="9be2a-452">ProxyServer</span><span class="sxs-lookup"><span data-stu-id="9be2a-452">ProxyServer</span></span>
#### <span data-ttu-id="9be2a-453">프록시 서버 주소 또는 URL</span><span class="sxs-lookup"><span data-stu-id="9be2a-453">Address or URL of proxy server</span></span>
><span data-ttu-id="9be2a-454">Microsoft Edge 업데이트 1.3.21.81 이상</span><span class="sxs-lookup"><span data-stu-id="9be2a-454">Microsoft Edge Update 1.3.21.81 and later</span></span>

#### <span data-ttu-id="9be2a-455">설명</span><span class="sxs-lookup"><span data-stu-id="9be2a-455">Description</span></span>
<span data-ttu-id="9be2a-456">Microsoft Edge 업데이트가 사용할 프록시 서버의 URL을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-456">Allows you to specify the URL of the proxy server for Microsoft Edge Update to use.</span></span>

  <span data-ttu-id="9be2a-457">이 정책을 사용하도록 설정하면 조직에서 Microsoft Edge 업데이트가 사용하는 프록시 서버 URL을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-457">If you enable this policy, you can set the proxy server URL used by Microsoft Edge Update in your organization.</span></span>

  <span data-ttu-id="9be2a-458">이 정책은 ‘[프록시 서버 설정 지정 방법 선택](#proxymode)’ 정책에서 수동 프록시 설정을 선택한 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9be2a-458">This policy is applied only if you have selected manual proxy settings in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>

  <span data-ttu-id="9be2a-459">‘[프록시 서버 설정 지정 방법 선택](#proxymode)‘ 정책에서 수동 이외의 프록시 설정을 선택한 경우 이 정책을 구성하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="9be2a-459">Don't configure this policy if you have selected a proxy setting other than manual in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>
#### <span data-ttu-id="9be2a-460">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="9be2a-460">Windows information and settings</span></span>
##### <span data-ttu-id="9be2a-461">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="9be2a-461">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="9be2a-462">GP 고유 이름: ProxyServer</span><span class="sxs-lookup"><span data-stu-id="9be2a-462">GP unique name: ProxyServer</span></span>
- <span data-ttu-id="9be2a-463">GP 이름: 프록시 서버 주소 또는 URL</span><span class="sxs-lookup"><span data-stu-id="9be2a-463">GP name: Address or URL of proxy server</span></span>
- <span data-ttu-id="9be2a-464">GP 경로: 관리 템플릿/Microsoft Edge 업데이트/프록시 서버</span><span class="sxs-lookup"><span data-stu-id="9be2a-464">GP path: Administrative Templates/Microsoft Edge Update/Proxy Server</span></span>
- <span data-ttu-id="9be2a-465">GP ADMX 파일 이름: edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="9be2a-465">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="9be2a-466">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="9be2a-466">Windows Registry Settings</span></span>
- <span data-ttu-id="9be2a-467">경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="9be2a-467">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="9be2a-468">값 이름: ProxyServer</span><span class="sxs-lookup"><span data-stu-id="9be2a-468">Value Name: ProxyServer</span></span>
- <span data-ttu-id="9be2a-469">값 형식: REG_SZ</span><span class="sxs-lookup"><span data-stu-id="9be2a-469">Value Type: REG_SZ</span></span>
##### <span data-ttu-id="9be2a-470">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="9be2a-470">Example value:</span></span>
```
https://www.microsoft.com
```
[<span data-ttu-id="9be2a-471">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="9be2a-471">Back to top</span></span>](#microsoft-edge---update-policies)


## <span data-ttu-id="9be2a-472">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9be2a-472">See also</span></span>
  - [<span data-ttu-id="9be2a-473">Microsoft Edge 구성</span><span class="sxs-lookup"><span data-stu-id="9be2a-473">Configuring Microsoft Edge</span></span>](configure-microsoft-edge.md)
  - [<span data-ttu-id="9be2a-474">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="9be2a-474">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
