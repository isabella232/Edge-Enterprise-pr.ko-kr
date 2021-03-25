---
title: Microsoft Edge 프록시 설정
ms.author: brianalt
author: dan-wesley
manager: srugh
ms.date: 05/01/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: '명령줄 옵션을 사용하여 프록시 설정 구성 '
ms.openlocfilehash: d0924f723aab6832e5b4eb70c60e1d329d3c7a9d
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447642"
---
# <a name="how-to-use-microsoft-edge-command-line-options-to-configure-proxy-settings"></a><span data-ttu-id="0e28a-103">Microsoft Edge 명령줄 옵션을 사용하여 프록시 설정을 구성하는 방법</span><span class="sxs-lookup"><span data-stu-id="0e28a-103">How to use Microsoft Edge command-line options to configure proxy settings</span></span>

<span data-ttu-id="0e28a-104">이 문서에서는 명령줄 옵션을 사용하여 기본 시스템 네트워크 설정을 재정의하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0e28a-104">This article describes how you can use command-line options to override the default system network settings.</span></span>

>[!NOTE]
><span data-ttu-id="0e28a-105">이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e28a-105">This article applies to Microsoft Edge version 77 or later.</span></span>

## <a name="system-network-settings"></a><span data-ttu-id="0e28a-106">시스템 네트워크 설정</span><span class="sxs-lookup"><span data-stu-id="0e28a-106">System network settings</span></span>

<span data-ttu-id="0e28a-107">Microsoft Edge 네트워크 스택은 기본적으로 시스템 네트워크 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0e28a-107">The Microsoft Edge network stack uses the system network settings by default.</span></span> <span data-ttu-id="0e28a-108">이러한 설정에는 \* 프록시 설정\*과 *인증서 및 개인 키 저장소*가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e28a-108">These settings include *proxy settings*, and *certificate and private key stores*.</span></span>

<span data-ttu-id="0e28a-109">사용자가 시스템 기본 프록시 설정을 사용하는 대신 다른 방법을 요청하는 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e28a-109">There are scenarios where users request an alternative to using the system's default proxy settings.</span></span> <span data-ttu-id="0e28a-110">이러한 시나리오를 지원하기 위해 Microsoft Edge에서는 사용자 지정 프록시 설정을 구성하는 데 사용할 수 있는 명령줄 옵션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0e28a-110">To support these scenarios, Microsoft Edge supports command-line options that you can use to configure custom proxy settings.</span></span>

<span data-ttu-id="0e28a-111">이러한 명령줄 옵션은 **프록시 서버** 그룹의 다음 정책에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="0e28a-111">These command-line options correspond to the following policies in the **Proxy server** group:</span></span>

- [<span data-ttu-id="0e28a-112">ProxyBypassList</span><span class="sxs-lookup"><span data-stu-id="0e28a-112">ProxyBypassList</span></span>](./microsoft-edge-policies.md#proxybypasslist)
- [<span data-ttu-id="0e28a-113">ProxyMode</span><span class="sxs-lookup"><span data-stu-id="0e28a-113">ProxyMode</span></span>](./microsoft-edge-policies.md#proxymode)
- [<span data-ttu-id="0e28a-114">ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="0e28a-114">ProxyPacUrl</span></span>](./microsoft-edge-policies.md#proxypacurl)
- [<span data-ttu-id="0e28a-115">ProxyServer</span><span class="sxs-lookup"><span data-stu-id="0e28a-115">ProxyServer</span></span>](./microsoft-edge-policies.md#proxyserver)
- [<span data-ttu-id="0e28a-116">ProxySettings</span><span class="sxs-lookup"><span data-stu-id="0e28a-116">ProxySettings</span></span>](./microsoft-edge-policies.md#proxysettings)

## <a name="command-line-options-for-proxy-settings"></a><span data-ttu-id="0e28a-117">프록시 설정 관련 명령줄 옵션</span><span class="sxs-lookup"><span data-stu-id="0e28a-117">Command-line options for proxy settings</span></span>

<span data-ttu-id="0e28a-118">Microsoft Edge는 다음과 같은 프록시 관련 명령줄 옵션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0e28a-118">Microsoft Edge supports the following proxy-related command-line options.</span></span>

 **`--no-proxy-server`**
 
<span data-ttu-id="0e28a-119">시스템이 프록시를 사용하도록 구성되어 있더라도 Microsoft Edge에 프록시를 사용하지 않도록 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="0e28a-119">Tells Microsoft Edge not to use a Proxy, even if the system is otherwise configured to use one.</span></span> <span data-ttu-id="0e28a-120">이는 제공된 다른 모든 프록시 설정을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0e28a-120">It overrides any other proxy settings that are provided.</span></span>

**`--proxy-auto-detect`**

<span data-ttu-id="0e28a-121">Mircrosoft Edge에 프록시 구성을 자동으로 감지하도록 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="0e28a-121">Tells Microsoft Edge to try and automatically detect your proxy configuration.</span></span> <span data-ttu-id="0e28a-122">`--proxy-server`가 구성된 경우 이 인수는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e28a-122">This argument is ignored if `--proxy-server` is configured.</span></span>

**`--proxy-server=<scheme>=<uri>[:<port>][;...] | <uri>[:<port>] | "direct://"`**

<span data-ttu-id="0e28a-123">Microsoft Edge에 사용자 지정 프록시 구성을 사용하도록 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="0e28a-123">Tells Microsoft Edge to use a custom proxy configuration.</span></span> <span data-ttu-id="0e28a-124">사용자 지정 프록시 구성은 세 가지 방법으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e28a-124">You can specify a custom proxy configuration in three ways.</span></span>

1. <span data-ttu-id="0e28a-125">url/포트 쌍에 세미콜론으로 구분된 목록 구성표 매핑을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0e28a-125">Provide a semicolon-separated mapping of list scheme to url/port pairs.</span></span> <span data-ttu-id="0e28a-126">예를 들어 `--proxy-server="http=proxy1:8080;ftp=ftpproxy"`는 http URL에 HTTP 프록시 "proxy1:8080"을 사용하고 ftp URL에 HTTP 프록시 "ftpproxy:80"을 사용하도록 Microsoft Edge에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="0e28a-126">For example, `--proxy-server="http=proxy1:8080;ftp=ftpproxy"` tells Microsoft Edge to use HTTP proxy "proxy1:8080" for http URLs and HTTP proxy "ftpproxy:80" for ftp URLs.</span></span>
2. <span data-ttu-id="0e28a-127">모든 URL에 사용할 선택적 포트가 있는 단일 uri를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0e28a-127">By providing a single uri with optional port to use for all URLs.</span></span> <span data-ttu-id="0e28a-128">예를 들어 `--proxy-server="proxy2:8080"`은 모든 트래픽에 "proxy2:8080" 프록시를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0e28a-128">For example, `--proxy-server="proxy2:8080"` will use the proxy at "proxy2:8080" for all traffic.</span></span>
3. <span data-ttu-id="0e28a-129">특수 "direct://" 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0e28a-129">By using the special "direct://" value.</span></span> <span data-ttu-id="0e28a-130">예를 들어 `--proxy-server="direct://"`는 모든 연결이 프록시를 사용하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e28a-130">For example, `--proxy-server="direct://"` will make all connections not use a proxy.</span></span> 

>[!NOTE]
><span data-ttu-id="0e28a-131">프록시를 사용할 수 없는 경우 프록시 및 대체를 사용하여 직접 이동하도록 Microsoft Edge를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e28a-131">You can configure Microsoft Edge to try using a proxy and fallback to going direct if the proxy isn't available.</span></span> <span data-ttu-id="0e28a-132">예를 들면 `--proxy-server="http://proxy2:8080,direct://`입니다.</span><span class="sxs-lookup"><span data-stu-id="0e28a-132">For example, `--proxy-server="http://proxy2:8080,direct://`.</span></span>

**`--proxy-bypass-list=(<trailing_domain>|<ip-address>)[:<port>][;...]`**

<span data-ttu-id="0e28a-133">Microsoft Edge에 지정한 세미콜론으로 구분된 호스트 목록에 대해 지정하 프록시를 무시하도록 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="0e28a-133">Tells Microsoft Edge to bypass any specified proxy for the specified semicolon-separated list of hosts.</span></span> <span data-ttu-id="0e28a-134">이 플래그는 `--proxy-server`와 함께 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e28a-134">This flag must be used with `--proxy-server`.</span></span>

>[!NOTE]
><span data-ttu-id="0e28a-135">후행 도메인 일치에는 "." 구분 기호가 필요하지 않습니다. "\*microsoft.com"은 "imicrosoft.com"과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="0e28a-135">Trailing-domain matching doesn't require "." separators, "\*microsoft.com" will match "imicrosoft.com".</span></span> <span data-ttu-id="0e28a-136">예를 들어 `--proxy-server="proxy2:8080" --proxy-bypass-list="*.microsoft.com;*example.com;127.0.0.1:8080"`는 포트 8080에서 \*.microsoft.com, example.com 및 127.0.0.1에 대한 요청을 제외하고 모든 호스트의 포트 8080에 프록시 서버 "proxy2"를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0e28a-136">For example, `--proxy-server="proxy2:8080" --proxy-bypass-list="*.microsoft.com;*example.com;127.0.0.1:8080"` will use the proxy server "proxy2" on port 8080 for all hosts except requests for \*.microsoft.com, example.com, and 127.0.0.1 on port 8080.</span></span> <span data-ttu-id="0e28a-137">이전 예제에서 imicrosoft.com 요청은 계속 프록시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e28a-137">In the previous example, imicrosoft.com requests will still be proxied.</span></span> <span data-ttu-id="0e28a-138">그러나 \*.example.com 대신 \*example.com이 지정되었기 때문에 iexample.com 요청은 프록시를 우회합니다.</span><span class="sxs-lookup"><span data-stu-id="0e28a-138">However, iexample.com requests will bypass the proxy because \*example.com was specified instead of \*.example.com.</span></span>

**`--proxy-pac-url=<pac-file-url>`**

<span data-ttu-id="0e28a-139">Microsoft Edge에 지정한 URL에서 PAC 파일을 사용하도록 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="0e28a-139">Tells Microsoft Edge to use the PAC file at the specified URL.</span></span> <span data-ttu-id="0e28a-140">예를 들어 `--proxy-pac-url="https://wpad/proxy.pac"`은 **proxy.pac** 파일을 사용하여 URL 요청에 대한 프록시 정보를 확인하도록 Microsoft Edge에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="0e28a-140">For example, `--proxy-pac-url="https://wpad/proxy.pac"` tells Microsoft Edge to resolve proxy information for URL requests using the **proxy.pac** file.</span></span>

## <a name="content-license"></a><span data-ttu-id="0e28a-141">콘텐츠 라이선스</span><span class="sxs-lookup"><span data-stu-id="0e28a-141">Content license</span></span>

> [!NOTE]
> <span data-ttu-id="0e28a-142">이 페이지의 일부는 Chromium.org에서 생성 및 공유하고 [Creative Commons Attribution 4.0 국제 라이선스](http://creativecommons.org/licenses/by/4.0/)에 규정된 조건에 따라 사용되는 작업을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e28a-142">Portions of this page are modifications based on work created and shared by Chromium.org and used according to terms described in the [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/).</span></span> <span data-ttu-id="0e28a-143">원래 페이지는 [여기](https://www.chromium.org/developers/design-documents/network-settings#TOC-Command-line-options-for-proxy-sett)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e28a-143">The original page can be found [here](https://www.chromium.org/developers/design-documents/network-settings#TOC-Command-line-options-for-proxy-sett).</span></span>
  
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br /><span data-ttu-id="0e28a-144">이 작업은 <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 국제 라이선스</a>에서 사용이 허가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e28a-144">This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.</span></span>

## <a name="see-also"></a><span data-ttu-id="0e28a-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0e28a-145">See also</span></span>

- <span data-ttu-id="0e28a-146">고급 구성 설정 및 추가 옵션을 보려면 Chromium 오픈 소스 프로젝트에서 [프록시 설명서](https://chromium.googlesource.com/chromium/src/+/HEAD/net/docs/proxy.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0e28a-146">To see advanced configuration settings and additional options, consult the [proxy documentation](https://chromium.googlesource.com/chromium/src/+/HEAD/net/docs/proxy.md) in the Chromium Open Source project.</span></span>
- [<span data-ttu-id="0e28a-147">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="0e28a-147">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)