---
title: Microsoft Edge WebView2 정책 문서
ms.author: stmoody
author: dan-wesley
manager: tahills
ms.date: 10/16/2020
audience: ITPro
ms.topic: reference
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
ms.custom: ''
description: Microsoft Edge 브라우저에서 지원하는 모든 정책에 대한 Windows 및 Mac 설명서
ms.openlocfilehash: 4298b25f7f158bc54f798442b4426494f046fa68
ms.sourcegitcommit: 7d160257010f75b86b89c8802d0dd27f1f8761ef
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2020
ms.locfileid: "11134447"
---
# <span data-ttu-id="55bc4-103">Microsoft Edge WebView2 – 정책</span><span class="sxs-lookup"><span data-stu-id="55bc4-103">Microsoft Edge WebView2 - Policies</span></span>

<span data-ttu-id="55bc4-104">최신 버전의 Microsoft Edge WebView2에는 다음과 같은 정책이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55bc4-104">The latest version of Microsoft Edge WebView2 includes the following policies.</span></span> <span data-ttu-id="55bc4-105">이러한 정책을 사용하여 조직에서 Microsoft Edge WebView2를 실행하는 방법을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55bc4-105">You can use these policies to configure how Microsoft Edge WebView2 runs in your organization.</span></span>

<span data-ttu-id="55bc4-106">Microsoft Edge WebView2의 업데이트 방법 및 시기를 제어하는 데 사용되는 추가 정책 집합에 대한 자세한 내용은 [Microsoft Edge 업데이트 정책 참조](microsoft-edge-update-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="55bc4-106">For information about an additional set of policies used to control how and when Microsoft Edge WebView2 is updated, check out [Microsoft Edge update policy reference](microsoft-edge-update-policies.md).</span></span>


> [!NOTE]
> <span data-ttu-id="55bc4-107">이 문서는 Microsoft Edge 버전 87 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="55bc4-107">This article applies to Microsoft Edge version 87 or later.</span></span>

## <span data-ttu-id="55bc4-108">사용 가능한 정책</span><span class="sxs-lookup"><span data-stu-id="55bc4-108">Available policies</span></span>

<span data-ttu-id="55bc4-109">다음 표에는 이 릴리스의 Microsoft Edge WebView2에서 사용할 수 있는 모든 그룹 정책이 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55bc4-109">These tables list all of the group policies available in this release of Microsoft Edge WebView2.</span></span> <span data-ttu-id="55bc4-110">특정 정책에 대해 자세히 알아보려면 표의 링크를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="55bc4-110">Use the links in the table to get more details about specific policies.</span></span>

|||
|-|-|
|[<span data-ttu-id="55bc4-111">로더 재정의 설정</span><span class="sxs-lookup"><span data-stu-id="55bc4-111">Loader Override Settings</span></span>](#loader-override-settings)|

### [*<span data-ttu-id="55bc4-112">로더 재정의 설정</span><span class="sxs-lookup"><span data-stu-id="55bc4-112">Loader Override Settings</span></span>*](#loader-override-settings-policies)

|<span data-ttu-id="55bc4-113">정책 이름</span><span class="sxs-lookup"><span data-stu-id="55bc4-113">Policy Name</span></span>|<span data-ttu-id="55bc4-114">캡션</span><span class="sxs-lookup"><span data-stu-id="55bc4-114">Caption</span></span>|
|-|-|
|[<span data-ttu-id="55bc4-115">browserExecutableFolder</span><span class="sxs-lookup"><span data-stu-id="55bc4-115">browserExecutableFolder</span></span>](#browserexecutablefolder)|<span data-ttu-id="55bc4-116">브라우저 실행 파일 폴더의 위치 구성</span><span class="sxs-lookup"><span data-stu-id="55bc4-116">Configure the location of the browser executable folder</span></span>|
|[<span data-ttu-id="55bc4-117">releaseChannelPreference</span><span class="sxs-lookup"><span data-stu-id="55bc4-117">releaseChannelPreference</span></span>](#releasechannelpreference)|<span data-ttu-id="55bc4-118">릴리스 채널 검색 순서 기본 설정</span><span class="sxs-lookup"><span data-stu-id="55bc4-118">Set the release channel search order preference</span></span>|




  ## <span data-ttu-id="55bc4-119">로더 재정의 설정 정책</span><span class="sxs-lookup"><span data-stu-id="55bc4-119">Loader Override Settings policies</span></span>

  [<span data-ttu-id="55bc4-120">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="55bc4-120">Back to top</span></span>](#microsoft-edge-webview2---policies)

  ### <span data-ttu-id="55bc4-121">browserExecutableFolder</span><span class="sxs-lookup"><span data-stu-id="55bc4-121">browserExecutableFolder</span></span>

  #### <span data-ttu-id="55bc4-122">브라우저 실행 파일 폴더의 위치 구성</span><span class="sxs-lookup"><span data-stu-id="55bc4-122">Configure the location of the browser executable folder</span></span>

  
  
  #### <span data-ttu-id="55bc4-123">지원 버전:</span><span class="sxs-lookup"><span data-stu-id="55bc4-123">Supported versions:</span></span>

  - <span data-ttu-id="55bc4-124">Windows (87 이상)</span><span class="sxs-lookup"><span data-stu-id="55bc4-124">On Windows since 87 or later</span></span>

  #### <span data-ttu-id="55bc4-125">설명</span><span class="sxs-lookup"><span data-stu-id="55bc4-125">Description</span></span>

  <span data-ttu-id="55bc4-126">이 정책은 WebView2 응용 프로그램이 지정된 경로에서 WebView2 런타임을 사용하도록 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="55bc4-126">This policy configures WebView2 applications to use the WebView2 Runtime in the specified path.</span></span> <span data-ttu-id="55bc4-127">폴더에는 msedgewebview2.exe, msedge.dll 등의 파일이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55bc4-127">The folder should contain the following files: msedgewebview2.exe, msedge.dll, and so on.</span></span>

<span data-ttu-id="55bc4-128">폴더 경로에 대한 값을 설정하려면 값 이름과 값 쌍을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="55bc4-128">To set the value for the folder path, provide a Value name and Value pair.</span></span> <span data-ttu-id="55bc4-129">값 이름을 응용 프로그램 사용자 모델 ID 또는 실행 파일 이름으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="55bc4-129">Set value name to the Application User Model ID or the executable file name.</span></span> <span data-ttu-id="55bc4-130">값 이름으로 "\*" 와일드카드를 사용하여 모든 응용 프로그램에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55bc4-130">You can use the "\*" wildcard as value name to apply to all applications.</span></span>

  #### <span data-ttu-id="55bc4-131">지원 기능:</span><span class="sxs-lookup"><span data-stu-id="55bc4-131">Supported features:</span></span>

  - <span data-ttu-id="55bc4-132">필수 사항: 예</span><span class="sxs-lookup"><span data-stu-id="55bc4-132">Can be mandatory: Yes</span></span>
  - <span data-ttu-id="55bc4-133">권장 사항: 아니요</span><span class="sxs-lookup"><span data-stu-id="55bc4-133">Can be recommended: No</span></span>
  - <span data-ttu-id="55bc4-134">동적 정책 새로 고침: 예</span><span class="sxs-lookup"><span data-stu-id="55bc4-134">Dynamic Policy Refresh: Yes</span></span>

  #### <span data-ttu-id="55bc4-135">데이터 형식:</span><span class="sxs-lookup"><span data-stu-id="55bc4-135">Data Type:</span></span>

  - <span data-ttu-id="55bc4-136">문자열 목록</span><span class="sxs-lookup"><span data-stu-id="55bc4-136">List of strings</span></span>

  #### <span data-ttu-id="55bc4-137">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="55bc4-137">Windows information and settings</span></span>

  ##### <span data-ttu-id="55bc4-138">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="55bc4-138">Group Policy (ADMX) info</span></span>

  - <span data-ttu-id="55bc4-139">GP 고유 이름: browserExecutableFolder</span><span class="sxs-lookup"><span data-stu-id="55bc4-139">GP unique name: browserExecutableFolder</span></span>
  - <span data-ttu-id="55bc4-140">GP 이름: 브라우저 실행 파일 폴더의 위치 구성</span><span class="sxs-lookup"><span data-stu-id="55bc4-140">GP name: Configure the location of the browser executable folder</span></span>
  - <span data-ttu-id="55bc4-141">GP 경로(필수): 관리 템플릿/Microsoft Edge WebView2/로더 재정의 설정</span><span class="sxs-lookup"><span data-stu-id="55bc4-141">GP path (Mandatory): Administrative Templates/Microsoft Edge WebView2/Loader Override Settings</span></span>
  - <span data-ttu-id="55bc4-142">GP 경로 (권장): 해당 없음</span><span class="sxs-lookup"><span data-stu-id="55bc4-142">GP path (Recommended): N/A</span></span>
  - <span data-ttu-id="55bc4-143">GP ADMX 파일 이름: MSEdgeWebView2.admx</span><span class="sxs-lookup"><span data-stu-id="55bc4-143">GP ADMX file name: MSEdgeWebView2.admx</span></span>

  ##### <span data-ttu-id="55bc4-144">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="55bc4-144">Windows Registry Settings</span></span>

  - <span data-ttu-id="55bc4-145">경로 (필수): SOFTWARE\정책\Microsoft\Edge\WebView2\browserExecutableFolder</span><span class="sxs-lookup"><span data-stu-id="55bc4-145">Path (Mandatory): SOFTWARE\Policies\Microsoft\Edge\WebView2\browserExecutableFolder</span></span>
  - <span data-ttu-id="55bc4-146">경로 (권장): 해당 없음</span><span class="sxs-lookup"><span data-stu-id="55bc4-146">Path (Recommended): N/A</span></span>
  - <span data-ttu-id="55bc4-147">값 이름: REG_SZ 목록</span><span class="sxs-lookup"><span data-stu-id="55bc4-147">Value Name: list of REG_SZ</span></span>
  - <span data-ttu-id="55bc4-148">값 형식: REG_SZ 목록</span><span class="sxs-lookup"><span data-stu-id="55bc4-148">Value Type: list of REG_SZ</span></span>

  ##### <span data-ttu-id="55bc4-149">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="55bc4-149">Example value:</span></span>

```
SOFTWARE\Policies\Microsoft\Edge\WebView2\browserExecutableFolder = "Name: *, Value: C:\\Program Files\\Microsoft Edge WebView2 Runtime Redistributable 85.0.541.0 x64"

```

  

  [<span data-ttu-id="55bc4-150">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="55bc4-150">Back to top</span></span>](#microsoft-edge-webview2---policies)

  ### <span data-ttu-id="55bc4-151">releaseChannelPreference</span><span class="sxs-lookup"><span data-stu-id="55bc4-151">releaseChannelPreference</span></span>

  #### <span data-ttu-id="55bc4-152">릴리스 채널 검색 순서 기본 설정</span><span class="sxs-lookup"><span data-stu-id="55bc4-152">Set the release channel search order preference</span></span>

  
  
  #### <span data-ttu-id="55bc4-153">지원 버전:</span><span class="sxs-lookup"><span data-stu-id="55bc4-153">Supported versions:</span></span>

  - <span data-ttu-id="55bc4-154">Windows (87 이상)</span><span class="sxs-lookup"><span data-stu-id="55bc4-154">On Windows since 87 or later</span></span>

  #### <span data-ttu-id="55bc4-155">설명</span><span class="sxs-lookup"><span data-stu-id="55bc4-155">Description</span></span>

  <span data-ttu-id="55bc4-156">기본 채널 검색 순서는 WebView2 Runtime, 베타, Dev 및 Canary입니다.</span><span class="sxs-lookup"><span data-stu-id="55bc4-156">The default channel search order is WebView2 Runtime, Beta, Dev, and Canary.</span></span>

<span data-ttu-id="55bc4-157">기본 검색 순서를 거꾸로 하려면 이 정책을 1로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="55bc4-157">To reverse the default search order, set this policy to 1.</span></span>

<span data-ttu-id="55bc4-158">릴리스 채널 기본 설정 값을 설정하려면 값 이름과 값 쌍을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="55bc4-158">To set the value for the release channel preference, provide a Value name and Value pair.</span></span> <span data-ttu-id="55bc4-159">값 이름을 응용 프로그램 사용자 모델 ID 또는 실행 파일 이름으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="55bc4-159">Set value name to the Application User Model ID or the executable file name.</span></span> <span data-ttu-id="55bc4-160">값 이름으로 "\*" 와일드카드를 사용하여 모든 응용 프로그램에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55bc4-160">You can use the "\*" wildcard as value name to apply to all applications.</span></span>

  #### <span data-ttu-id="55bc4-161">지원 기능:</span><span class="sxs-lookup"><span data-stu-id="55bc4-161">Supported features:</span></span>

  - <span data-ttu-id="55bc4-162">필수 사항: 예</span><span class="sxs-lookup"><span data-stu-id="55bc4-162">Can be mandatory: Yes</span></span>
  - <span data-ttu-id="55bc4-163">권장 사항: 아니요</span><span class="sxs-lookup"><span data-stu-id="55bc4-163">Can be recommended: No</span></span>
  - <span data-ttu-id="55bc4-164">동적 정책 새로 고침: 예</span><span class="sxs-lookup"><span data-stu-id="55bc4-164">Dynamic Policy Refresh: Yes</span></span>

  #### <span data-ttu-id="55bc4-165">데이터 형식:</span><span class="sxs-lookup"><span data-stu-id="55bc4-165">Data Type:</span></span>

  - <span data-ttu-id="55bc4-166">문자열 목록</span><span class="sxs-lookup"><span data-stu-id="55bc4-166">List of strings</span></span>

  #### <span data-ttu-id="55bc4-167">Windows 정보 및 설정</span><span class="sxs-lookup"><span data-stu-id="55bc4-167">Windows information and settings</span></span>

  ##### <span data-ttu-id="55bc4-168">그룹 정책(ADMX) 정보</span><span class="sxs-lookup"><span data-stu-id="55bc4-168">Group Policy (ADMX) info</span></span>

  - <span data-ttu-id="55bc4-169">GP 고유 이름: releaseChannelPreference</span><span class="sxs-lookup"><span data-stu-id="55bc4-169">GP unique name: releaseChannelPreference</span></span>
  - <span data-ttu-id="55bc4-170">GP 이름: 릴리스 채널 검색 순서 기본 설정</span><span class="sxs-lookup"><span data-stu-id="55bc4-170">GP name: Set the release channel search order preference</span></span>
  - <span data-ttu-id="55bc4-171">GP 경로(필수): 관리 템플릿/Microsoft Edge WebView2/로더 재정의 설정</span><span class="sxs-lookup"><span data-stu-id="55bc4-171">GP path (Mandatory): Administrative Templates/Microsoft Edge WebView2/Loader Override Settings</span></span>
  - <span data-ttu-id="55bc4-172">GP 경로 (권장): 해당 없음</span><span class="sxs-lookup"><span data-stu-id="55bc4-172">GP path (Recommended): N/A</span></span>
  - <span data-ttu-id="55bc4-173">GP ADMX 파일 이름: MSEdgeWebView2.admx</span><span class="sxs-lookup"><span data-stu-id="55bc4-173">GP ADMX file name: MSEdgeWebView2.admx</span></span>

  ##### <span data-ttu-id="55bc4-174">Windows 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="55bc4-174">Windows Registry Settings</span></span>

  - <span data-ttu-id="55bc4-175">경로 (필수): SOFTWARE\정책\Microsoft\Edge\WebView2\releaseChannelPreference</span><span class="sxs-lookup"><span data-stu-id="55bc4-175">Path (Mandatory): SOFTWARE\Policies\Microsoft\Edge\WebView2\releaseChannelPreference</span></span>
  - <span data-ttu-id="55bc4-176">경로 (권장): 해당 없음</span><span class="sxs-lookup"><span data-stu-id="55bc4-176">Path (Recommended): N/A</span></span>
  - <span data-ttu-id="55bc4-177">값 이름: REG_SZ 목록</span><span class="sxs-lookup"><span data-stu-id="55bc4-177">Value Name: list of REG_SZ</span></span>
  - <span data-ttu-id="55bc4-178">값 형식: REG_SZ 목록</span><span class="sxs-lookup"><span data-stu-id="55bc4-178">Value Type: list of REG_SZ</span></span>

  ##### <span data-ttu-id="55bc4-179">예를 들어 값:</span><span class="sxs-lookup"><span data-stu-id="55bc4-179">Example value:</span></span>

```
SOFTWARE\Policies\Microsoft\Edge\WebView2\releaseChannelPreference = "Name: *, Value: 1"

```

  

  [<span data-ttu-id="55bc4-180">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="55bc4-180">Back to top</span></span>](#microsoft-edge-webview2---policies)


## <span data-ttu-id="55bc4-181">참고 항목</span><span class="sxs-lookup"><span data-stu-id="55bc4-181">See also</span></span>

- [<span data-ttu-id="55bc4-182">Microsoft Edge 구성</span><span class="sxs-lookup"><span data-stu-id="55bc4-182">Configuring Microsoft Edge</span></span>](configure-microsoft-edge.md)
- [<span data-ttu-id="55bc4-183">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="55bc4-183">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="55bc4-184">Microsoft Office 보안 기준 블로그</span><span class="sxs-lookup"><span data-stu-id="55bc4-184">Microsoft Security Baselines Blog</span></span>](https://techcommunity.microsoft.com/t5/microsoft-security-baselines/bg-p/Microsoft-Security-Baselines)