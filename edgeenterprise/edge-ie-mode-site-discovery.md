---
title: 엔터프라이즈 사이트 검색 단계별 가이드
ms.author: cjacks
author: appcompatguy
manager: saudm
ms.date: 04/07/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 엔터프라이즈 사이트 검색을 사용하여 IE 모드를 준비합니다.
ms.openlocfilehash: 9ec748686b83466cd1c7d92fcc7fdc0f0d136977
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980695"
---
# <span data-ttu-id="8f8be-103">엔터프라이즈 사이트 검색 단계별 가이드</span><span class="sxs-lookup"><span data-stu-id="8f8be-103">Enterprise Site Discovery Step-by-Step Guide</span></span>

<span data-ttu-id="8f8be-104">이 문서에서는 Microsoft 끝점 구성 관리자와 함께 엔터프라이즈 사이트 검색을 사용하는 단계별 가이드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-104">This article provides a step-by-step guide to using Enterprise Site Discovery with Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="8f8be-105">엔터프라이즈 사이트 검색은 엔터프라이즈 모드 사이트 목록을 구성하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-105">Enterprise Site Discovery can help you configure your Enterprise Mode Site List.</span></span> <span data-ttu-id="8f8be-106">엔터프라이즈 사이트 검색을 통해 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-106">Enterprise Site Discovery will help you:</span></span>

- <span data-ttu-id="8f8be-107">레거시 문서 모드를 사용하는 사이트를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-107">Discover which sites are using legacy document modes.</span></span> <span data-ttu-id="8f8be-108">해당 사이트가 최신 브라우저를 검색하고 다양한 HTML을 제공하는 경우가 아니면 IE 모드를 사용해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-108">Unless these sites are detecting modern browsers and providing different HTML, they probably need to use IE mode.</span></span>
- <span data-ttu-id="8f8be-109">ActiveX 컨트롤을 사용하는 사이트를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-109">Discover which sites are using ActiveX controls.</span></span> <span data-ttu-id="8f8be-110">Microsoft Edge는 ActiveX 컨트롤을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-110">Microsoft Edge doesn't support ActiveX controls.</span></span> <span data-ttu-id="8f8be-111">해당 사이트가 최신 브라우저를 검색하고 다양한 HTML을 제공하는 경우가 아니면 IE 모드를 사용해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-111">Unless these sites are detecting modern browsers and providing different HTML, they probably need to use IE mode.</span></span>

> [!NOTE]
> <span data-ttu-id="8f8be-112">이 문서는 Microsoft Edge **안정**, **Beta** 및 **Dev** 채널 버전 77 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-112">This article applies to Microsoft Edge **Stable**, **Beta** and **Dev** Channels, version 77 or later.</span></span>

## <span data-ttu-id="8f8be-113">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="8f8be-113">Prerequisites</span></span>

<span data-ttu-id="8f8be-114">이 가이드에서는 사용자가 Microsoft 끝점 구성 관리자를 사용하고 있으며 다음 서비스 및 역할이 설치되어 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-114">This guide assumes you're experienced with using Microsoft Endpoint Configuration Manager and have the following services and roles installed:</span></span>

1. <span data-ttu-id="8f8be-115">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8f8be-115">Microsoft Endpoint Configuration Manager</span></span>
2. <span data-ttu-id="8f8be-116">Microsoft SQL Server Reporting Services</span><span class="sxs-lookup"><span data-stu-id="8f8be-116">Microsoft SQL Server Reporting Services</span></span>
3. <span data-ttu-id="8f8be-117">(선택 사항) 구성된 서비스 지정 역할을 보고하는 구성 관리자</span><span class="sxs-lookup"><span data-stu-id="8f8be-117">(Optional) Configuration Manager Reporting Services Point Role configured</span></span>

## <span data-ttu-id="8f8be-118">엔터프라이즈 사이트 검색 도구 다운로드</span><span class="sxs-lookup"><span data-stu-id="8f8be-118">Download Enterprise Site Discovery Tools</span></span>

<span data-ttu-id="8f8be-119">다음의 도구를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-119">Download the following tools:</span></span>

- [<span data-ttu-id="8f8be-120">엔터프라이즈 사이트 검색 설정 및 구성 패키지</span><span class="sxs-lookup"><span data-stu-id="8f8be-120">Enterprise Site Discovery Setup and Configuration Package</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=517719)
- [<span data-ttu-id="8f8be-121">Microsoft 보고서 작성기</span><span class="sxs-lookup"><span data-stu-id="8f8be-121">Microsoft Report Builder</span></span>](https://www.microsoft.com/download/details.aspx?id=53613)

## <span data-ttu-id="8f8be-122">엔터프라이즈 사이트 검색 사용</span><span class="sxs-lookup"><span data-stu-id="8f8be-122">Enable Enterprise Site Discovery</span></span>

<span data-ttu-id="8f8be-123">WMI (Windows Management Instrumentation)에 연결하여 사이트 검색 데이터를 검색하기 전에 먼저 WMI 클래스 공급자를 장치에 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-123">Before you can connect to Windows Management Instrumentation (WMI) to retrieve site discovery data, you must first deploy the WMI class provider to the device.</span></span>

<span data-ttu-id="8f8be-124">**엔터프라이즈 사이트 검색 설정 및 구성 패키지**에서 최종 소프트웨어 라이브러리 파일 공유의 폴더로 내용을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-124">From the **Enterprise Site Discovery Setup and Configuration Package**, extract the contents to a folder in your definitive software library file share.</span></span> <span data-ttu-id="8f8be-125">예: **\\\\DSL\\EnterpriseSiteDiscovery**.</span><span class="sxs-lookup"><span data-stu-id="8f8be-125">Example: **\\\\DSL\\EnterpriseSiteDiscovery**.</span></span>

<span data-ttu-id="8f8be-126">다음으로 [문서](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)에서 설명한 대로 Microsoft 끝점 구성 관리자에서 패키지를 만들고 다음의 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-126">Next, create a package in Microsoft Endpoint Configuration Manager, as described in the [documentation](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs), selecting the following options:</span></span>

- <span data-ttu-id="8f8be-127">**패키지** 페이지에서 **이름**을 선택하고 **사이트 검색 사용** 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-127">On the **Package** page, select **Name** and specify the name **Enable Site Discovery**</span></span>
- <span data-ttu-id="8f8be-128">**패키지** 페이지에서 **이 패키지에 원본 파일 포함**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-128">On the **Package** page, select **This package contains source files**</span></span>
- <span data-ttu-id="8f8be-129">**패키지** 페이지에서 파일을 추출한 원본 폴더 (예: **\\\\DSL\\EnterpriseSiteDiscovery**)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-129">On the **Package** page, specify the source folder you extracted the files to (for example, **\\\\DSL\\EnterpriseSiteDiscovery**)</span></span>
- <span data-ttu-id="8f8be-130">**프로그램 유형** 페이지에서 **표준 프로그램**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-130">On the **Program Type** page, choose **Standard Program**</span></span>
- <span data-ttu-id="8f8be-131">**표준 프로그램** 페이지에서 다음과 같이 장치에서 사이트 검색을 구성하는 명령줄을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-131">On the **Standard Program** page, enter the command line to configure Site Discovery on the device as follows:</span></span>
  ```dos
  powershell.exe -ExecutionPolicy Bypass .\IETelemetrySetUp-Win8.ps1
  ```
  > [!NOTE]
  > <span data-ttu-id="8f8be-132">이 스크립트는 `-ZoneAllowList` 및 `-SiteAllowList`에 대한 명령줄 스위치 사용을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-132">The script supports using command line switches for `-ZoneAllowList` and `-SiteAllowList`.</span></span> <span data-ttu-id="8f8be-133">이 단계별 절차에 대해 그룹 정책 (아래)을 통해 해당 옵션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-133">For this step-by-step, we will configure these options via group policy (below).</span></span>
- <span data-ttu-id="8f8be-134">**표준 프로그램** 페이지에서 옵션을 선택하고 **숨김**을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-134">On the **Standard Program** page, select the option to run **Hidden**.</span></span>
- <span data-ttu-id="8f8be-135">**표준 프로그램** 페이지의 **프로그램 실행 가능**에서 **사용자 로그인 여부** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-135">On the **Standard Program** page, under **Program can run**, select the option **Whether or not a user is logged in**</span></span>

<span data-ttu-id="8f8be-136">패키지를 만든 후 **사이트 검색 사용** 패키지 이름을 두 번 클릭하여 속성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-136">After creating the package, double-click on the package name **Enable Site Discovery** to view its properties.</span></span> <span data-ttu-id="8f8be-137">**실행 이후** 속성에서 **구성 관리자가 컴퓨터를 재시작합니다**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-137">In the **After running** property, select **Configuration manager restarts computer**.</span></span> <span data-ttu-id="8f8be-138">장치가 다시 부팅되면 WMI 데이터 수집이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-138">WMI data collection will begin after the devices reboot.</span></span>

> [!NOTE]
> <span data-ttu-id="8f8be-139">[클라이언트 설정 설명서](https://docs.microsoft.com/configmgr/core/clients/deploy/about-client-settings#computer-restart)에서 설명한 대로 사용자가 장치를 다시 시작하는 데 필요한 시간을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-139">You can configure the amount of time a user has to restart the device as described in the [client settings documentation](https://docs.microsoft.com/configmgr/core/clients/deploy/about-client-settings#computer-restart).</span></span>

## <span data-ttu-id="8f8be-140">그룹 정책을 통해 엔터프라이즈 사이트 검색을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-140">Configure Enterprise Site Discovery via Group Policy</span></span>

<span data-ttu-id="8f8be-141">엔터프라이즈 사이트 검색을 사용하는 경우 수집하는 데이터를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-141">With Enterprise Site Discovery enabled, you can configure what data you'll collect.</span></span> <span data-ttu-id="8f8be-142">[여기](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/collect-data-using-enterprise-site-discovery#what-data-is-collected)에 설명된 대로 현지 법률 및 규제 요구 사항을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-142">Consider local laws and regulatory requirements as described [here](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/collect-data-using-enterprise-site-discovery#what-data-is-collected).</span></span>

1. <span data-ttu-id="8f8be-143">그룹 정책 편집기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-143">Open Group Policy Editor</span></span>
2. <span data-ttu-id="8f8be-144">**컴퓨터 구성** > **관리 템플릿** > **Windows 구성 요소** > **Internet Explorer**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-144">Click **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Internet Explorer**</span></span> 
3. <span data-ttu-id="8f8be-145">**사이트 검색 WMI 출력 켜기**를 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-145">Double-click **Turn on Site Discovery WMI output**</span></span>
4. <span data-ttu-id="8f8be-146">**사용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-146">Select **Enabled**</span></span>
5. <span data-ttu-id="8f8be-147">**확인** 또는 **적용**을 클릭하여 이 정책 설정을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-147">Click **OK** or **Apply** to save this policy setting</span></span>

<span data-ttu-id="8f8be-148">사이트 데이터를 수집하는 영역을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-148">You can limit the zones in which you collect site data:</span></span>

1. <span data-ttu-id="8f8be-149">**영역별 사이트 검색 출력 제한**을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-149">Double-click **Limit Site Discovery output by Zone**</span></span>
2. <span data-ttu-id="8f8be-150">**사용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-150">Select **Enabled**</span></span>
3. <span data-ttu-id="8f8be-151">사이트 검색을 설정할 영역을 나타내는 비트 마스크를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-151">Enter a bitmask indicating which zones to enable site discover for:</span></span>
    1. <span data-ttu-id="8f8be-152">제한된 사이트 영역</span><span class="sxs-lookup"><span data-stu-id="8f8be-152">Restricted Sites zone</span></span>
    2. <span data-ttu-id="8f8be-153">인터넷 영역</span><span class="sxs-lookup"><span data-stu-id="8f8be-153">Internet zone</span></span>
    3. <span data-ttu-id="8f8be-154">신뢰할 수 있는 사이트 영역</span><span class="sxs-lookup"><span data-stu-id="8f8be-154">Trusted Sites zone</span></span>
    4. <span data-ttu-id="8f8be-155">로컬 인트라넷 영역</span><span class="sxs-lookup"><span data-stu-id="8f8be-155">Local Intranet zone</span></span>
    5. <span data-ttu-id="8f8be-156">로컬 컴퓨터 영역</span><span class="sxs-lookup"><span data-stu-id="8f8be-156">Local Machine zone</span></span>
    
    <span data-ttu-id="8f8be-157">예제 1: **00010**은 로컬 인트라넷 영역에 대해서만 데이터를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-157">Example 1: **00010** will collect data only for the Local Intranet zone</span></span>

    <span data-ttu-id="8f8be-158">예제 2: **10111**은 인터넷 영역을 제외한 모든 영역에 대한 데이터를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-158">Example 2: **10111** will collect data for all zones except the Internet zone</span></span>
4. <span data-ttu-id="8f8be-159">**확인** 또는 **적용**을 클릭하여 이 정책 설정을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-159">Click **OK** or **Apply** to save this policy setting</span></span>

<span data-ttu-id="8f8be-160">사이트 데이터를 수집하는 도메인을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-160">You can limit the domains for which you collect site data:</span></span>

1. <span data-ttu-id="8f8be-161">**도메인별 사이트 검색 출력 제한**을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-161">Double-click **Limit Site Discovery output by domain**</span></span>
2. <span data-ttu-id="8f8be-162">**사용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-162">Select **Enabled**</span></span>
3. <span data-ttu-id="8f8be-163">데이터를 수집하려는 도메인을 한 줄에 하나의 도메인을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-163">Enter the domains you want to collect data for, one domain per line</span></span>
4. <span data-ttu-id="8f8be-164">**확인** 또는 **적용**을 클릭하여 이 정책 설정을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-164">Click **OK** or **Apply** to save this policy setting</span></span>

## <span data-ttu-id="8f8be-165">구성 관리자를 사용하여 사이트 검색 데이터를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-165">Collect Site Discovery data using Configuration Manager</span></span>

<span data-ttu-id="8f8be-166">이제 장치에서 데이터를 생성하기 때문에 구성 관리자에서 해당 데이터를 수집해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-166">Now that your devices are generating data, it's time to collect this data in Configuration Manager.</span></span>

1. <span data-ttu-id="8f8be-167">구성 관리자 콘솔에서 **관리** > **클라이언트 설정** > **기본 클라이언트 설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-167">In the Configuration Manager console, choose **Administration** > **Client Settings** > **Default Client Settings**</span></span>
2. <span data-ttu-id="8f8be-168">**홈** 탭의 **속성** 그룹에서 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-168">On the **Home** tab, in the **Properties** group, choose **Properties**</span></span>
3. <span data-ttu-id="8f8be-169">**기본 클라이언트 설정** 대화 상자에서 **하드웨어 인벤토리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-169">In the **Default Client Settings** dialog box, choose **Hardware Inventory**</span></span>
4. <span data-ttu-id="8f8be-170">**장치 설정** 목록에서 **집합 클래스**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-170">In the **Device Settings** list, choose **Set Classes**</span></span>
5. <span data-ttu-id="8f8be-171">**하드웨어 인벤터리 클래스** 대화 상자에서 **추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-171">In the **Hardware Inventory Classes** dialog box, choose **Add**</span></span>
6. <span data-ttu-id="8f8be-172">**하드웨어 인벤터리 클래스 추가** 대화 상자에서 **연결**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-172">In the **Add Hardware Inventory Class** dialog box, click **Connect**</span></span>
7. <span data-ttu-id="8f8be-173">**WMI (Windows Management Instrumentation)에 연결** 대화 상자에서 엔터프라이즈 사이트 검색이 구성된 컴퓨터의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-173">In the **Connect to Windows Management Instrumentation (WMI)** dialog box, enter the name of a computer where Enterprise Site Discovery is configured.</span></span> <span data-ttu-id="8f8be-174">다른 컴퓨터에 연결하는 경우 WMI에 액세스하는 데 필요한 권한이 있는 자격 증명이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-174">If you're connecting to another computer, you'll need credentials with permission to access WMI.</span></span>
8. <span data-ttu-id="8f8be-175">**WMI 네임스페이스** 텍스트 상자에 **root\cimv2\IETelemetry**를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-175">In the **WMI Namespace** text box, enter **root\cimv2\IETelemetry**</span></span>
9. <span data-ttu-id="8f8be-176">**연결**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-176">Choose **Connect**</span></span>
10. <span data-ttu-id="8f8be-177">**하드웨어 인벤터리 클래스 추가** 대화 상자의 **인벤터리 수업** 목록에서 WMI 클래스 **IESystemINfo**, **IEUrlInfo** 및 \**IECountInfo*을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-177">In the **Add Hardware Inventory Class** dialog box, in the **Inventory classes** list, select the WMI classes **IESystemINfo**, **IEUrlInfo**, and \**IECountInfo*.</span></span>
11. <span data-ttu-id="8f8be-178">**확인**를 클릭하여 **클래스 한정자** 대화 상자 및 열려 있는 기타 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-178">Click **OK** to close the **Class qualifiers** dialog box and the other open dialogs.</span></span>

<span data-ttu-id="8f8be-179">클라이언트가 관리 지점에서 설정을 업데이트한 후 다음 하드웨어 인벤터리가 실행될 때 데이터가 보고됩니다. (기본적으로 7일 마다)</span><span class="sxs-lookup"><span data-stu-id="8f8be-179">After the client updates settings from the management point, data will be reported when the next hardware inventory runs (by default every seven days).</span></span>

## <span data-ttu-id="8f8be-180">사이트 검색 보고서 가져오기</span><span class="sxs-lookup"><span data-stu-id="8f8be-180">Import Site Discovery reports</span></span>

<span data-ttu-id="8f8be-181">엔터프라이즈 사이트 검색 패키지에는 두 개의 샘플 보고서가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-181">The Enterprise Site Discovery package includes two sample reports.</span></span> <span data-ttu-id="8f8be-182">한 보고서는 ActiveX 컨트롤을 사용하여 사이트를 표시하고 다른 하나는 레거시 문서 모드를 사용하는 사이트를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-182">One report shows sites using ActiveX controls, and another shows sites using legacy document modes.</span></span>

### <span data-ttu-id="8f8be-183">사이트 검색 샘플 보고서 구성</span><span class="sxs-lookup"><span data-stu-id="8f8be-183">Configure the Site Discovery sample report</span></span>

<span data-ttu-id="8f8be-184">다음의 절차를 사용하여 세 가지 데이터 원본 (사용자가 방문한 사이트, 사이트의 시스템에 대한 정보, 사이트에서 사용하는 문서 모드)을 사용하는 샘플 보고서를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-184">Use the following procedure to create a sample report that uses three data sources: the sites a user visits, information about their system, and the document modes used by the sites.</span></span> <span data-ttu-id="8f8be-185">이 보고서는 레거시 문서 모드에 종속될 수 있는 사이트를 식별하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-185">This report helps you identify sites that may depend on legacy document modes.</span></span>

1. <span data-ttu-id="8f8be-186">보고서 **SCCM_Report-Site_Discovery.rdl**을 구성 관리자 서버에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-186">Copy the report **SCCM_Report-Site_Discovery.rdl** to your Configuration Manager server.</span></span>
2. <span data-ttu-id="8f8be-187">[Microsoft 보고서 작성기](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder?view=sql-server-ver15)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-187">Install [Microsoft Report Builder](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder?view=sql-server-ver15).</span></span>
3. <span data-ttu-id="8f8be-188">**SCCM_Report-Site_Discovery.rdl**을 두 번 클릭하여 보고서 작성기에서 보고서를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-188">Double-click **SCCM_Report-Site_Discovery.rdl** to open the report in Report Builder.</span></span>
4. <span data-ttu-id="8f8be-189">처음으로 보고서를 열 때 보고서가 만들어진 서버에 연결을 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-189">The first time you try to open the report, it will try to contact the server where it was created.</span></span> <span data-ttu-id="8f8be-190">**보고서 서버에 연결**하라는 메시지가 표시되면 **아니요**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-190">When prompted to **Connect to Report Server**, click **No**.</span></span>
5. <span data-ttu-id="8f8be-191">보고서가 열리면 **데이터 원본**을 확장하고 **DataSource1**을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-191">After the report opens, expand **Data Sources** and double-click **DataSource1**.</span></span>
6. <span data-ttu-id="8f8be-192">**데이터 원본 속성** 창에서 **보고서에 포함된 연결 사용**을 선택한 다음 **빌드...** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-192">In the **Data Source Properties** window, select **Use a connection embedded in my report** and then click the **Build...** button.</span></span>
7. <span data-ttu-id="8f8be-193">**연결 속성** 창에서 **서버 이름**을 선택하고 구성 관리자 서버 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-193">In the **Connection Properties** window, select **Server Name** and enter the name of the Configuration Manager server.</span></span> <span data-ttu-id="8f8be-194">그런 다음 **데이터베이스 이름 선택 또는 입력**의 드롭다운 목록에서 구성 관리자 데이터베이스의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-194">Then, in **Select or enter a database name** select the name of the Configuration Manager database from the dropdown list.</span></span>
8. <span data-ttu-id="8f8be-195">**확인**을 클릭하여 **연결 속성** 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-195">Click **OK** to close the **Connection Properties** window.</span></span>
9. <span data-ttu-id="8f8be-196">**연결 테스트**를 클릭하여 연결을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-196">Click **Test Connection** to test the connection.</span></span> <span data-ttu-id="8f8be-197">연결에 성공하면 **확인**을 클릭하여 **데이터 원본 속성** 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-197">If the connection is successful, click **OK** to close the **Data Source Properties** window.</span></span>
10. <span data-ttu-id="8f8be-198">**데이터 원본 2**에 대해서도 5~9단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-198">Repeat Steps 5 through 9 for **Data Source 2**.</span></span>
11. <span data-ttu-id="8f8be-199">**데이터 집합**을 확장하고 **DataSet1**을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-199">Expand **Datasets** and double-click **DataSet1**.</span></span>
12. <span data-ttu-id="8f8be-200">**데이터 집합 속성** 창에서 \*\*쿼리: \*\* 텍스트 상자를 클릭하고 **CM_A1B**를 7단계에서 선택한 데이터베이스 이름과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-200">In the **Dataset Properties** window, click in the **Query:** textbox and replace **USE CM_A1B** with the database name you selected in Step 7.</span></span>
13. <span data-ttu-id="8f8be-201">**DataSet2**, **DataSet3**및 **DataSet4**에 대해 11 ~ 12단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-201">Repeat steps 11 through 12 for **DataSet2**, **DataSet3**, and **DataSet4**.</span></span>
14. <span data-ttu-id="8f8be-202">리본의 **홈** 탭에서 **실행** 단추를 클릭하여 보고서를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-202">In the **Home** tab of the ribbon, click the **Run** button to test the report.</span></span>
15. <span data-ttu-id="8f8be-203">보고서를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-203">Save the report.</span></span>
16. <span data-ttu-id="8f8be-204">Microsoft 보고서 작성기를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-204">Close Microsoft Report Builder.</span></span>
17. <span data-ttu-id="8f8be-205">파일 이름을 **사이트 검색.rdl**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-205">Rename the file to **Site Discovery.rdl**</span></span>

### <span data-ttu-id="8f8be-206">ActiveX 샘플 보고서를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-206">Configure the ActiveX sample report</span></span>

<span data-ttu-id="8f8be-207">다음 절차를 사용하여 하나의 데이터 원본(ActiveX 컨트롤을 사용하는 사이트)을 사용하는 샘플 보고서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-207">Use the following procedure to create a sample report that uses one data source: the sites that are using ActiveX controls.</span></span> <span data-ttu-id="8f8be-208">Internet Explorer는 ActiveX 컨트롤을 지원하는 유일한 브라우저이기 때문에 이 사이트에는 IE 모드가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-208">Since Internet Explorer is the only browser that support ActiveX controls, these sites may require IE mode.</span></span>

1. <span data-ttu-id="8f8be-209">보고서 **SCCM Report Sample - ActiveX.rdl**을 구성 관리자 서버에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-209">Copy the report **SCCM Report Sample - ActiveX.rdl** to your Configuration Manager server.</span></span>
2. <span data-ttu-id="8f8be-210">[Microsoft 보고서 작성기](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder?view=sql-server-ver15)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-210">Install [Microsoft Report Builder](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder?view=sql-server-ver15).</span></span>
3. <span data-ttu-id="8f8be-211">**SCCM Report Sample - ActiveX.rdl**을 두 번 클릭하여 보고서 작성기에서 보고서를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-211">Double-click **SCCM Report Sample - ActiveX.rdl** to open the report in Report Builder.</span></span>
4. <span data-ttu-id="8f8be-212">처음으로 보고서를 열 때 보고서가 만들어진 서버에 연결을 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-212">The first time you try to open the report, it will try to contact the server where it was created.</span></span> <span data-ttu-id="8f8be-213">**보고서 서버에 연결**하라는 메시지가 표시되면 **아니요**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-213">When prompted to **Connect to Report Server**, click **No**.</span></span>
5. <span data-ttu-id="8f8be-214">보고서가 열리면 **데이터 원본**를 확장하고 **AutoGen__5C6358F2_4BB6_4a1b_A16E_8D96795D8602_** 를 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-214">After the report opens, expand **Data Sources** and double-click **AutoGen__5C6358F2_4BB6_4a1b_A16E_8D96795D8602_**.</span></span>
6. <span data-ttu-id="8f8be-215">**데이터 원본 속성** 창에서 **보고서에 포함된 연결 사용**을 선택한 다음 **빌드...** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-215">In the **Data Source Properties** window, select **Use a connection embedded in my report** and then click the **Build...** button.</span></span>
7. <span data-ttu-id="8f8be-216">**연결 속성** 창에서 **서버 이름**을 선택하고 구성 관리자 서버 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-216">In the **Connection Properties** window, select **Server Name** and enter the name of the Configuration Manager server.</span></span> <span data-ttu-id="8f8be-217">그런 다음 **데이터베이스 이름 선택 또는 입력**의 드롭다운 목록에서 구성 관리자 데이터베이스의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-217">Then, in **Select or enter a database name** select the name of the Configuration Manager database from the dropdown list.</span></span>
8. <span data-ttu-id="8f8be-218">**확인**을 클릭하여 **연결 속성** 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-218">Click **OK** to close the **Connection Properties** window.</span></span>
9. <span data-ttu-id="8f8be-219">**연결 테스트**를 클릭하여 연결을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-219">Click **Test Connection** to test the connection.</span></span> <span data-ttu-id="8f8be-220">연결에 성공하면 **확인**을 클릭하여 **데이터 원본 속성** 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-220">If the connection is successful, click **OK** to close the **Data Source Properties** window.</span></span>
10. <span data-ttu-id="8f8be-221">**데이터 집합**을 확장하고 **DataSet1**을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-221">Expand **Datasets** and double-click **DataSet1**.</span></span>
11. <span data-ttu-id="8f8be-222">**데이터 집합 속성** 창에서 \*\*쿼리: \*\* 텍스트 상자를 클릭하고 **CM_A1B**를 7단계에서 선택한 데이터베이스 이름과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-222">In the **Dataset Properties** window, click in the **Query:** textbox and replace **USE CM_A1B** with the database name you selected in Step 7.</span></span>
12. <span data-ttu-id="8f8be-223">리본의 **홈** 탭에서 **실행** 단추를 클릭하여 보고서를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-223">In the **Home** tab of the ribbon, click the **Run** button to test the report.</span></span>
13. <span data-ttu-id="8f8be-224">보고서를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-224">Save the report.</span></span>
14. <span data-ttu-id="8f8be-225">Microsoft 보고서 작성기를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-225">Close Microsoft Report Builder.</span></span>
15. <span data-ttu-id="8f8be-226">파일을 **ActiveX**로 이름을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-226">Rename the file to **ActiveX**</span></span>

### <span data-ttu-id="8f8be-227">Microsoft SQL Server Reporting Services에 구성된 보고서를 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-227">Upload configured reports to Microsoft SQL Server Reporting Services</span></span>

<span data-ttu-id="8f8be-228">환경에 대한 보고서를 구성한 후 보고 서버로 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-228">After you've configured the reports for your environment, upload them to the reporting server.</span></span>

1. <span data-ttu-id="8f8be-229">**Reporting Services Configuration Manager** 응용 프로그램을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-229">Launch the **Reporting Services Configuration Manager** application.</span></span>
2. <span data-ttu-id="8f8be-230">**보고서 서버 연결** 창에서 **연결**을 클릭한 다음 **웹 포털 사이트 ID** 아래에 나열된 URL을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-230">In the **Report Server Connection** window, click **Connect** and then click on the URL listed under **Web Portal Site Identification**</span></span>
3. <span data-ttu-id="8f8be-231">열려 있는 브라우저 창에서 사용자는 **SQL Server Reporting Services 페이지**에 있어야 하며 SCCM 사이트 코드를 보려면 **ConfigMgr_SCCMSiteCode** 폴더를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-231">In the browser window that opens, you should be on the **SQL Server Reporting Services Page** - click the **ConfigMgr_SCCMSiteCode** folder for your SCCM Site Code.</span></span>
4. <span data-ttu-id="8f8be-232">리본에서 **+새**를 마우스로 가리키고 **폴더** 메뉴 항목을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-232">In the ribbon, hover over **+New** and click the **Folder** menu item.</span></span>
5. <span data-ttu-id="8f8be-233">**엔터프라이즈 사이트 검색**과 같이 폴더 이름을 입력한 다음 **생성** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-233">Enter a folder name, such as **Enterprise Site Discovery**, and then click the **Create** button.</span></span>
6. <span data-ttu-id="8f8be-234">**엔터프라이즈 사이트 검색** 폴더를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-234">Click on the **Enterprise Site Discovery** folder.</span></span>
7. <span data-ttu-id="8f8be-235">리본에서 **업로드** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-235">In the ribbon, click the **Upload** button.</span></span>
8. <span data-ttu-id="8f8be-236">**사이트 검색** 보고서를 선택하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-236">Select the **Site Discovery** report, and click **OK**.</span></span>
9. <span data-ttu-id="8f8be-237">**ActiveX** 보고서에 대해 7단계 및 8단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-237">Repeat steps 7 and 8 for the **ActiveX** report.</span></span>

### <span data-ttu-id="8f8be-238">구성 관리자에서 보고서를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-238">View reports in Configuration Manager</span></span>

<span data-ttu-id="8f8be-239">이제 보고서를 사용자 지정하고 업로드했으므로 이를 구성 관리자에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-239">Now that you've customized and uploaded the reports, you can view them in Configuration Manager.</span></span>

1. <span data-ttu-id="8f8be-240">구성 관리자 콘솔에서 **모니터링** > **보고** > **보고서** > **엔터프라이즈 사이트 검색**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-240">In the Configuration Manager console, choose **Monitoring** > **Reporting** > **Reports** > **Enterprise Site Discovery**</span></span>
2. <span data-ttu-id="8f8be-241">보고서를 확인하려면 보고서를 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-241">Double-click on a report to view it.</span></span>

## <span data-ttu-id="8f8be-242">엔터프라이즈 사이트 검색 해제</span><span class="sxs-lookup"><span data-stu-id="8f8be-242">Disable Enterprise Site Discovery</span></span>

<span data-ttu-id="8f8be-243">데이터 수집이 완료되면 엔터프라이즈 사이트 검색을 사용하지 않도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-243">When you're finished collecting data, you should disable Enterprise Site Discovery.</span></span> <span data-ttu-id="8f8be-244">[문서](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)에서 설명한 대로 다음의 옵션을 선택하여 Microsoft 끝점 구성 관리자에서 엔터프라이즈 사이트 검색을 사용하지 않도록 설정하는 두 번째 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-244">Create a second package to disable Enterprise Site Discovery in Microsoft Endpoint Configuration Manager, as described in the [documentation](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs), selecting the following options:</span></span>

- <span data-ttu-id="8f8be-245">**패키지** 페이지에서 **이름**을 선택하고 **사이트 검색 해제** 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-245">On the **Package** page, select **Name** and specify the name **Disable Site Discovery**</span></span>
- <span data-ttu-id="8f8be-246">**패키지** 페이지에서 **이 패키지에 원본 파일 포함**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-246">On the **Package** page, select **This package contains source files**</span></span>
- <span data-ttu-id="8f8be-247">**패키지** 페이지에서 파일을 추출한 원본 폴더 (예: **\\\\DSL\\EnterpriseSiteDiscovery**)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-247">On the **Package** page, specify the source folder you extracted the files to (for example, **\\\\DSL\\EnterpriseSiteDiscovery**)</span></span>
- <span data-ttu-id="8f8be-248">**프로그램 유형** 페이지에서 **표준 프로그램**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-248">On the **Program Type** page, choose **Standard Program**</span></span>
- <span data-ttu-id="8f8be-249">**표준 프로그램** 페이지에서 다음과 같이 장치에서 사이트 검색을 해제하는 명령줄을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-249">On the **Standard Program** page, enter the command line that will disable Site Discovery on the device as follows:</span></span>
  ```dos
  powershell.exe -ExecutionPolicy Bypass .\IETelemetrySetUp-Win8.ps1 -IEFeatureOff
  ```
- <span data-ttu-id="8f8be-250">**표준 프로그램** 페이지에서 옵션을 선택하고 **숨김**을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-250">On the **Standard Program** page, select the option to run **Hidden**</span></span>
- <span data-ttu-id="8f8be-251">**표준 프로그램** 페이지의 **프로그램 실행 가능**에서 **사용자 로그인 여부** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8be-251">On the **Standard Program** page, under **Program can run**, select the option **Whether or not a user is logged in**</span></span>

## <span data-ttu-id="8f8be-252">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8f8be-252">See also</span></span>

- [<span data-ttu-id="8f8be-253">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="8f8be-253">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="8f8be-254">IE 모드 정보</span><span class="sxs-lookup"><span data-stu-id="8f8be-254">About IE mode</span></span>](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [<span data-ttu-id="8f8be-255">추가 엔터프라이즈 모드 정보</span><span class="sxs-lookup"><span data-stu-id="8f8be-255">Additional Enterprise Mode information</span></span>](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [<span data-ttu-id="8f8be-256">추가 엔터프라이즈 사이트 검색 정보</span><span class="sxs-lookup"><span data-stu-id="8f8be-256">Additional Enterprise Site Discovery information</span></span>](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/collect-data-using-enterprise-site-discovery)