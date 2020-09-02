---
title: Microsoft Edge URL 정책용 필터 형식
ms.author: brianalt
author: dan-wesley
manager: srugh
ms.date: 05/01/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge URLBlocklist 및 URLAllowlist 정책에 사용되는 필터 형식에 대해 알아봅니다.
ms.openlocfilehash: 5a0eff1ca7be17fccd1087716d426b13ea302847
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980675"
---
# <span data-ttu-id="e8556-103">URL 목록 기반 정책에 대한 필터 형식</span><span class="sxs-lookup"><span data-stu-id="e8556-103">Filter format for URL list-based policies</span></span>

<span data-ttu-id="e8556-104">이 문서에서는 Microsoft Edge URL 목록 기반 정책에 사용되는 필터 형식에 대해 설명합니다(예: [URLBlocklist](microsoft-edge-policies.md#urlblocklist), [URLAllowList](microsoft-edge-policies.md#urlallowlist), [CertificateTransparencyEnforcementDisabledForUrls](microsoft-edge-policies.md#certificatetransparencyenforcementdisabledforurls)).</span><span class="sxs-lookup"><span data-stu-id="e8556-104">This article describes the filter format used for the Microsoft Edge URL list-based policies (For example, [URLBlocklist](microsoft-edge-policies.md#urlblocklist), [URLAllowList](microsoft-edge-policies.md#urlallowlist), and [CertificateTransparencyEnforcementDisabledForUrls](microsoft-edge-policies.md#certificatetransparencyenforcementdisabledforurls) policies.</span></span>

> [!NOTE]
> <span data-ttu-id="e8556-105">이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-105">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="e8556-106">필터 형식</span><span class="sxs-lookup"><span data-stu-id="e8556-106">The filter format</span></span>

<span data-ttu-id="e8556-107">필터 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-107">The filter format is:</span></span>

```
    [scheme://][.]host[:port][/path][@query]
```

<span data-ttu-id="e8556-108">필터 형식의 필드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-108">The fields in the filter format are:</span></span>

| <span data-ttu-id="e8556-109">필드</span><span class="sxs-lookup"><span data-stu-id="e8556-109">Field</span></span> | <span data-ttu-id="e8556-110">설명</span><span class="sxs-lookup"><span data-stu-id="e8556-110">Description</span></span> |
| --- | --- |
| <span data-ttu-id="e8556-111">**scheme**(*선택 사항*)</span><span class="sxs-lookup"><span data-stu-id="e8556-111">**scheme** (*optional*)</span></span> | <span data-ttu-id="e8556-112">http://, https://, ftp://, edge:// 등일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-112">It can be http://, https://, ftp://, edge://, etc.</span></span> |
| <span data-ttu-id="e8556-113">**host**(*필수*)</span><span class="sxs-lookup"><span data-stu-id="e8556-113">**host** (*required*)</span></span> | <span data-ttu-id="e8556-114">유효한 호스트 이름 또는 IP 주소여야 하며 와일드 카드("\*")를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-114">It must be a valid host name or IP address and you can use a wildcard ("\*").</span></span> <span data-ttu-id="e8556-115">하위 도메인 일치를 사용하지 않도록 설정하려면 **호스트** 앞에 점(".")을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-115">To disable subdomain matching, include an optional dot (".") before **host**.</span></span> |
| <span data-ttu-id="e8556-116">**port**(*선택 사항*)</span><span class="sxs-lookup"><span data-stu-id="e8556-116">**port** (*optional*)</span></span> | <span data-ttu-id="e8556-117">유효한 값은 1~65535입니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-117">Valid values range from 1 to 65535.</span></span> |
| <span data-ttu-id="e8556-118">**path**(*선택 사항*)</span><span class="sxs-lookup"><span data-stu-id="e8556-118">**path** (*optional*)</span></span> | <span data-ttu-id="e8556-119">경로에 임의의 문자열을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-119">You can use any string in the path.</span></span> |
| <span data-ttu-id="e8556-120">**query**(*선택 사항*)</span><span class="sxs-lookup"><span data-stu-id="e8556-120">**query** (*optional*)</span></span> | <span data-ttu-id="e8556-121">**쿼리**는 앰퍼샌드("&")로 구분되는 키-값 또는 키-전용 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-121">The **query** is either key-value or key-only tokens separated by an ampersand ("&").</span></span> <span data-ttu-id="e8556-122">키-값 토큰은 등호("=")를 사용하여 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-122">Separate key-value tokens with an equal sign ("=").</span></span> <span data-ttu-id="e8556-123">접두사 일치를 표시하려면 **쿼리**끝에 별표("\*")를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-123">To indicate a prefix match, you can use an asterisk ("\*") at the end of the **query**.</span></span> |

## <span data-ttu-id="e8556-124">필터 형식과 URL 형식 비교</span><span class="sxs-lookup"><span data-stu-id="e8556-124">Comparing the filter format to the URL format</span></span>

<span data-ttu-id="e8556-125">필터 형식은 다음과 같은 차이를 제외하고 URL 형식과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-125">The filter format resembles the URL format, except for the following differences:</span></span>

- <span data-ttu-id="e8556-126">"user:pass"를 포함하는 경우 이는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-126">If you include "user:pass", it will be ignored.</span></span> <span data-ttu-id="e8556-127">예: http://user:pass@ftp.contoso.com/pub/example.iso.</span><span class="sxs-lookup"><span data-stu-id="e8556-127">For example, http://user:pass@ftp.contoso.com/pub/example.iso.</span></span>
- <span data-ttu-id="e8556-128">조각 식별자("#")를 포함하는 경우 조각 실별자와 식별자 뒤에 오는 모든 내용이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-128">If you include a fragment identifier ("#"), it and everything that follows the identifier is ignored.</span></span>
- <span data-ttu-id="e8556-129">와일드 카드("\*")를 **호스트**로 사용할 수 있으며 점(".")을 접두사로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-129">You can use a wildcard ("\*") as the **host** and you can prefix it with a dot (".").</span></span>
- <span data-ttu-id="e8556-130">슬래시("/") 또는 점(".")을 **호스트**의 접미사로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-130">You can use a forward slash ("/") or a dot (".") as a suffix for the **host**.</span></span> <span data-ttu-id="e8556-131">이 경우 접미사는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-131">In this case, the suffix is ignored.</span></span>

## <span data-ttu-id="e8556-132">필터 선택 조건</span><span class="sxs-lookup"><span data-stu-id="e8556-132">Filter selection criteria</span></span>

<span data-ttu-id="e8556-133">URL에 대해 선택되는 필터는 다음 필터 선택 규칙을 처리한 후 검색된 가장 구체적인 일치 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-133">The filter selected for a URL is the most specific match found after processing the following filter selection rules:</span></span>

1. <span data-ttu-id="e8556-134">가장 긴 **host** 일치가 있는 필터가 먼저 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-134">Filters with the longest **host** match are selected first.</span></span>
2. <span data-ttu-id="e8556-135">선택된 필터에서 일치하지 않는 구성표 또는 포트가 있는 필터는 모두 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-135">From the selected filters, any filter with a non-matching scheme or port is discarded.</span></span>
3. <span data-ttu-id="e8556-136">나머지 필터에서 가장 긴 일치하는 **path**가 있는 필터가 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-136">From the remaining filters, the filter with the longest matching **path** is selected.</span></span>
4. <span data-ttu-id="e8556-137">나머지 필터에서 가장 긴 쿼리 토큰 집합이 있는 필터가 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-137">From the remaining filters, the filter with the longest set of query tokens is selected.</span></span> <span data-ttu-id="e8556-138">이 단계에서는 두 필터 모두 **경로** 길이와 **쿼리** 토큰 수가 동일하면 허용 목록 필터가 차단 목록 필터에 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-138">At this step, the allow list filter takes precedence over the block list filter if both filters have the same **path** length and number of **query** tokens.</span></span>
5. <span data-ttu-id="e8556-139">남은 유효한 필터가 없으면 가장 왼쪽에 있는 하위 도메인이 **host**에서 제거되고 선택 프로세스가 1단계부터 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-139">If there's no valid filter remaining, then the left-most subdomain is removed from **host** and the selection process starts over at step 1.</span></span> <span data-ttu-id="e8556-140">특수 별표("\*") **호스트**는 마지막으로 검색되고 모든 호스트와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-140">The special asterisk ("\*") **host** is the last searched and it matches all hosts.</span></span>
6. <span data-ttu-id="e8556-141">필터를 사용할 수 있는 경우 해당 필터가 URL 요청을 차단하거나 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-141">If a filter's available, it blocks or allows the URL request.</span></span>

   >[!NOTE]
   ><span data-ttu-id="e8556-142">일치하는 필터가 없는 경우 기본 동작은 URL 요청을 허용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-142">The default behavior is to allow the URL request if no filter is matched.</span></span>

## <span data-ttu-id="e8556-143">필터 선택 조건 예제</span><span class="sxs-lookup"><span data-stu-id="e8556-143">Example filter selection criteria</span></span>

<span data-ttu-id="e8556-144">이 예제에서 "https://sub.contoso.com/docs"에 일치하는 항목을 검색할 경우 필터 선택은 다음과 같이 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-144">In this example, when searching for a match to "https://sub.contoso.com/docs" the filter selection will:</span></span>

1. <span data-ttu-id="e8556-145">"sub.contoso.com"에 대한 필터를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-145">Search for a filter for "sub.contoso.com".</span></span> <span data-ttu-id="e8556-146">필터가 검색되면 검색이 2단계로 넘어갑니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-146">If it finds a filter, the search moves to step 2.</span></span> <span data-ttu-id="e8556-147">필터가 검색되지 않으면 "contoso.com", "com", 그리고 "마지막으로"를 사용하여 다시 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-147">If a filter isn't found, then it tries again with "contoso.com", "com", and finally "".</span></span>
2. <span data-ttu-id="e8556-148">선택된 필터에서 **구성표**에 "http"가 없는 항목은 모두 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-148">From the selected filters, any that don't have "http" in the **scheme** are removed.</span></span>
3. <span data-ttu-id="e8556-149">나머지 필터에서 정확한 포트 번호가 "80"이 아닌 항목은 모두 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-149">From the remaining filters, any that have an exact port number that isn't "80" are removed.</span></span>
4. <span data-ttu-id="e8556-150">나머지 필터에서 **path** 접두사로 "/docs"가 없는 항목은 모두 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-150">From the remaining filters, any that don't have "/docs" as a prefix of the **path** are removed.</span></span>
5. <span data-ttu-id="e8556-151">나머지 필터에서 path 접두사가 가장 긴 필터가 선택되고 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-151">From the remaining filters, the filter with the longest path prefix is selected and applied.</span></span> <span data-ttu-id="e8556-152">필터가 검색되지 않으면 1단계에서 선택 프로세스가 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-152">If a filter isn't found, the selection process starts over again at step 1.</span></span> <span data-ttu-id="e8556-153">프로세스가 다음 하위 도메인에서 반복됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-153">The process is repeated with the next subdomain.</span></span>

### <span data-ttu-id="e8556-154">추가 필터 정보</span><span class="sxs-lookup"><span data-stu-id="e8556-154">Additional filter information</span></span>

<span data-ttu-id="e8556-155">필터에 **호스트** 접두사로 점(".")이 있는 경우 정확히 **호스트**와 일치하는 항목만 필터링됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-155">If a filter has a dot (".") prefixing the **host** then only exact **host** matches are filtered.</span></span> <span data-ttu-id="e8556-156">예를 들어,</span><span class="sxs-lookup"><span data-stu-id="e8556-156">For example:</span></span>

- <span data-ttu-id="e8556-157">"contoso.com"(점 없음)은 "contoso.com", "www.contoso.com" 및 "sub.www.contoso.com"과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-157">"contoso.com" (no dot) will match "contoso.com", "www.contoso.com", and "sub.www.contoso.com"</span></span>
- <span data-ttu-id="e8556-158">".www.contoso.com"(점 접두사가 있음)은 "www.contoso.com"과만 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-158">".www.contoso.com" (with a dot prefix) will only match "www.contoso.com"</span></span>

<span data-ttu-id="e8556-159">표준 또는 고객 **스키마**중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-159">You can use either a standard or customer **schema**.</span></span> <span data-ttu-id="e8556-160">지원되는 표준 스키마는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-160">Supported standard schemas include:</span></span>

- <span data-ttu-id="e8556-161">_about_, _blob_, _content_, _edge_, _cid_, _data_, _file_, _filesystem_, _ftp_, _gopher_, _http_, _https_, _javascript_, _mailto_, _ws_, _wss_.</span><span class="sxs-lookup"><span data-stu-id="e8556-161">_about_, _blob_, _content_, _edge_, _cid_, _data_, _file_, _filesystem_, _ftp_, _gopher_, _http_, _https_, _javascript_, _mailto_, _ws_, and _wss_.</span></span>

<span data-ttu-id="e8556-162">다른 **스키마**는 사용자 지정 **스키마**로 취급되지만 _schema:\*_ 및 _schema://\*_ 패턴만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-162">Any other **schema** is treated as a custom **schema**, but only the _schema:\*_ and _schema://\*_ patterns are allowed.</span></span> <span data-ttu-id="e8556-163">예를 들어,</span><span class="sxs-lookup"><span data-stu-id="e8556-163">For example:</span></span>

- <span data-ttu-id="e8556-164">“custom:*” 또는 “custom://*”은 “custom:app”과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-164">"custom:*" or "custom://*" will match "custom:app"</span></span>
- <span data-ttu-id="e8556-165">“custom:app” 또는 “custom://app”은 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-165">"custom:app" or "custom://app" are invalid</span></span>

<span data-ttu-id="e8556-166">**schema** 및 **host**는 대/소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-166">**schema** and **host** aren't case-sensitive.</span></span> <span data-ttu-id="e8556-167">예를 들어,</span><span class="sxs-lookup"><span data-stu-id="e8556-167">For example:</span></span>

- <span data-ttu-id="e8556-168">“http://contoso.com” 필터는 “HTTP://contoso.com”, “http://contoso.COM” 및 “http://contoso.com”과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-168">"http://contoso.com" filter matches "HTTP://contoso.com", "http://contoso.COM", and "http://contoso.com"</span></span>

<span data-ttu-id="e8556-169">**path** 및 **query**는 대/소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-169">**path** and **query** are case-sensitive.</span></span> <span data-ttu-id="e8556-170">예를 들어,</span><span class="sxs-lookup"><span data-stu-id="e8556-170">For example:</span></span>

- <span data-ttu-id="e8556-171">"http://contoso.com/path?query=A" 필터는 "http://contoso.com/Path?query=A" 또는 "http://contoso.com/path?Query=A"와 일치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-171">"http://contoso.com/path?query=A" filter doesn't match "http://contoso.com/Path?query=A" or "http://contoso.com/path?Query=A".</span></span> <span data-ttu-id="e8556-172">“http://contoso.COM/path?query=A”와는 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-172">It does match "http://contoso.COM/path?query=A".</span></span>

## <span data-ttu-id="e8556-173">콘텐츠 라이선스</span><span class="sxs-lookup"><span data-stu-id="e8556-173">Content license</span></span>

> [!NOTE]
> <span data-ttu-id="e8556-174">이 페이지의 일부는 Chromium.org에서 생성 및 공유하고 [Creative Commons Attribution 4.0 국제 라이선스](http://creativecommons.org/licenses/by/4.0/)에 규정된 조건에 따라 사용되는 작업을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-174">Portions of this page are modifications based on work created and shared by Chromium.org and used according to terms described in the [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/).</span></span> <span data-ttu-id="e8556-175">원래 [Chromium 페이지는 여기](https://www.chromium.org/administrators/url-blacklist-filter-format)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-175">The original [Chromium page can be found here](https://www.chromium.org/administrators/url-blacklist-filter-format).</span></span>
  
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br /><span data-ttu-id="e8556-176">이 작업은 <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 국제 라이선스</a>에서 사용이 허가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e8556-176">This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.</span></span>

## <span data-ttu-id="e8556-177">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e8556-177">See also</span></span>

- [<span data-ttu-id="e8556-178">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="e8556-178">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
