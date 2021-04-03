---
title: IE 모드 정책 구성
ms.author: collw
author: dan-wesley
manager: srugh
ms.date: 03/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: IE 모드 정책 구성
ms.openlocfilehash: a2abf6f6ef71c1f30786031ef19b9633bfafc43f
ms.sourcegitcommit: 93851b83dc11422924646a04a9e0f60ff2554af7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470166"
---
# <a name="configure-ie-mode-policies"></a><span data-ttu-id="96e95-103">IE 모드 정책 구성</span><span class="sxs-lookup"><span data-stu-id="96e95-103">Configure IE mode policies</span></span>

<span data-ttu-id="96e95-104">이 문서에서는 IE 모드 정책을 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-104">This article explains how to configure IE mode policies.</span></span>

> [!NOTE]
> <span data-ttu-id="96e95-105">이 문서는 Microsoft Edge **안정**, **Beta** 및 **Dev** 채널 버전 77 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-105">This article applies to Microsoft Edge **Stable**, **Beta** and **Dev** Channels, version 77 or later.</span></span>

<span data-ttu-id="96e95-106">IE 모드를 구성하려면 세 단계가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-106">Configuring IE mode requires three steps:</span></span>

1. [<span data-ttu-id="96e95-107">Internet Explorer 통합 구성</span><span class="sxs-lookup"><span data-stu-id="96e95-107">Configure Internet Explorer integration</span></span>](#configure-internet-explorer-integration)
2. [<span data-ttu-id="96e95-108">Microsoft Edge에서 IE 모드로 사이트 리디렉션</span><span class="sxs-lookup"><span data-stu-id="96e95-108">Redirect sites from Microsoft Edge to IE mode</span></span>](#redirect-sites-from-microsoft-edge-to-ie-mode)
3. <span data-ttu-id="96e95-109">(선택 사항) [IE에서 Microsoft Edge로 사이트 리디렉션](#redirect-sites-from-ie-to-microsoft-edge)</span><span class="sxs-lookup"><span data-stu-id="96e95-109">(Optional) [Redirect sites from IE to Microsoft Edge](#redirect-sites-from-ie-to-microsoft-edge)</span></span>

    1. <span data-ttu-id="96e95-110">IE11 앱을 사용하지 않도록 설정할 준비가 되면 [Internet Explorer 11 비활성화](https://docs.microsoft.com/deployedge/edge-ie-disable-ie11)의 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="96e95-110">If you are ready to disable the IE11 app, follow the steps in [Disable Internet Explorer 11](https://docs.microsoft.com/deployedge/edge-ie-disable-ie11)</span></span>
    2. <span data-ttu-id="96e95-111">그렇지 않은 경우에는 [IE에서 Microsoft Edge로 사이트 리디렉션](https://docs.microsoft.com/deployedge/edge-ie-mode-policies#redirect-sites-from-ie-to-microsoft-edge)의 나머지 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="96e95-111">Otherwise,  follow the rest of the steps in [Redirect sites from IE to Microsoft Edge](https://docs.microsoft.com/deployedge/edge-ie-mode-policies#redirect-sites-from-ie-to-microsoft-edge)</span></span>

> [!NOTE]
> <span data-ttu-id="96e95-112">IE 모드를 사용하도록 설정하는 정책은 Intune을 통해 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-112">Policies to enable IE mode can be configured through Intune.</span></span> <span data-ttu-id="96e95-113">자세한 내용은 [Microsoft Intune에서 Microsoft Edge를 추가](/intune/apps/apps-windows-edge?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json) 및 [Microsoft Intune을 사용하여 Microsoft Edge 정책 구성](./configure-edge-with-intune.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96e95-113">For more information, see [Add Microsoft Edge to Microsoft Intune](/intune/apps/apps-windows-edge?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json) and [Configure Microsoft Edge policies with Microsoft Intune](./configure-edge-with-intune.md).</span></span>

## <a name="configure-internet-explorer-integration"></a><span data-ttu-id="96e95-114">Internet Explorer 통합 구성</span><span class="sxs-lookup"><span data-stu-id="96e95-114">Configure Internet Explorer integration</span></span>

<span data-ttu-id="96e95-115">Internet Explorer가 Microsoft Edge(IE 모드) 내에서 직접 열리도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-115">You can configure Internet Explorer to open directly within Microsoft Edge (IE mode).</span></span> <span data-ttu-id="96e95-116">독립 실행형 Internet Explorer 11 창에서 열리도록 Internet Explorer를 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-116">You can also configure Internet Explorer to open with a standalone Internet Explorer 11 window.</span></span> <span data-ttu-id="96e95-117">대부분의 사용자는 IE 모드에서 Microsoft Edge 내에서 직접 사이트를 열 때 선호합니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-117">Most users prefer when sites open directly within Microsoft Edge in IE mode.</span></span>

### <a name="enable-internet-explorer-integration-using-group-policy"></a><span data-ttu-id="96e95-118">그룹 정책을 사용하여 Internet Explorer 통합 사용</span><span class="sxs-lookup"><span data-stu-id="96e95-118">Enable Internet Explorer integration using Group Policy</span></span>

1. <span data-ttu-id="96e95-119">최신 [Microsoft Edge 정책 템플릿](https://www.microsoft.com/en-us/edge/business/download)을 다운로드하여 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-119">Download and use the latest [Microsoft Edge Policy Template](https://www.microsoft.com/en-us/edge/business/download).</span></span>
2. <span data-ttu-id="96e95-120">그룹 정책 편집기 열기.</span><span class="sxs-lookup"><span data-stu-id="96e95-120">Open Group Policy Editor.</span></span>
3. <span data-ttu-id="96e95-121">**컴퓨터 구성** > **관리 템플릿** > **Microsoft Edge**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-121">Click **Computer Configuration** > **Administrative Templates** > **Microsoft Edge**.</span></span>
4. <span data-ttu-id="96e95-122">**Internet Explorer 통합 구성**을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-122">Double-click **Configure Internet Explorer integration**.</span></span>
5. <span data-ttu-id="96e95-123">**사용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-123">Select **Enabled**.</span></span>
6. <span data-ttu-id="96e95-124">**옵션**에서 드롭다운 값을 설정</span><span class="sxs-lookup"><span data-stu-id="96e95-124">Under **Options**, set the dropdown value to</span></span> 
   -  <span data-ttu-id="96e95-125">**Internet Explorer 모드** 사이트를 Microsoft Edge에서 IE 모드로 열려면</span><span class="sxs-lookup"><span data-stu-id="96e95-125">**Internet Explorer mode** if you want sites to open in IE mode on Microsoft Edge</span></span>
   -  <span data-ttu-id="96e95-126">**Internet Explorer 11** 독립 실행형 Internet Explorer 11 창에서 사이트를 열려면</span><span class="sxs-lookup"><span data-stu-id="96e95-126">**Internet Explorer 11** if you want sites to open in a standalone Internet Explorer 11 window</span></span>
   -  <span data-ttu-id="96e95-127">**없음** edge://flags 또는 명령 줄을 통해 사용자가 Internet Explorer 모드를 구성하지 못하게하려는 경우</span><span class="sxs-lookup"><span data-stu-id="96e95-127">**None** if you want to stop users from configuring Internet Explorer mode via edge://flags or through the command line</span></span>

   > [!NOTE]
   > <span data-ttu-id="96e95-128">정책을 **사용 안 함**으로 설정하면 IE 모드가 정책에 의해 사용하지 않도록 설정됨을 나타내지만 edge://flags 또는 명령줄 옵션을 통해 설정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-128">Setting the policy to **Disabled** implies IE mode is disabled by policy, but can be set through edge://flags or command line options.</span></span>
7. <span data-ttu-id="96e95-129">**확인**또는 **적용**을 클릭하여 이 정책 설정을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-129">Click **OK** or **Apply** to save this policy setting.</span></span>

## <a name="redirect-sites-from-microsoft-edge-to-ie-mode"></a><span data-ttu-id="96e95-130">Microsoft Edge에서 IE 모드로 사이트 리디렉션</span><span class="sxs-lookup"><span data-stu-id="96e95-130">Redirect sites from Microsoft Edge to IE mode</span></span>

<span data-ttu-id="96e95-131">IE 모드에서 열어야 하는 사이트를 식별하는 데는 두 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-131">There are two options for identifying which sites should open in IE mode:</span></span>

- <span data-ttu-id="96e95-132">(권장) [엔터프라이즈 사이트 목록에서 사이트 구성](#configure-sites-on-the-enterprise-site-list)</span><span class="sxs-lookup"><span data-stu-id="96e95-132">(Recommended) [Configure sites on the Enterprise Site list](#configure-sites-on-the-enterprise-site-list)</span></span>
- [<span data-ttu-id="96e95-133">모든 인트라넷 사이트 구성</span><span class="sxs-lookup"><span data-stu-id="96e95-133">Configure all Intranet sites</span></span>](#configure-all-intranet-sites)

### <a name="configure-sites-on-the-enterprise-site-list"></a><span data-ttu-id="96e95-134">엔터프라이즈 사이트 목록에서 사이트 구성</span><span class="sxs-lookup"><span data-stu-id="96e95-134">Configure sites on the Enterprise Site list</span></span>

<span data-ttu-id="96e95-135">다음 그룹 정책을 사용하여 특정 사이트를 IE 모드에서 열리도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-135">You can use the following group policies to configure specific sites to open in IE mode:</span></span>

- <span data-ttu-id="96e95-136">[엔터프라이즈 모드 IE 웹 사이트 목록 사용](#configure-using-the-use-the-enterprise-mode-ie-website-list-policy)(Internet Explorer)</span><span class="sxs-lookup"><span data-stu-id="96e95-136">[Use the Enterprise Mode IE website list](#configure-using-the-use-the-enterprise-mode-ie-website-list-policy) (Internet Explorer)</span></span>
- <span data-ttu-id="96e95-137">[엔터프라이즈 모드 사이트 목록 구성](#configure-using-the-configure-the-enterprise-mode-site-list-policy)(Microsoft Edge, 버전 78 이상)</span><span class="sxs-lookup"><span data-stu-id="96e95-137">[Configure the Enterprise Mode Site List](#configure-using-the-configure-the-enterprise-mode-site-list-policy) (Microsoft Edge, version 78 or later)</span></span><br/><span data-ttu-id="96e95-138">이 정책을 사용하여 Microsoft Edge용 별도의 엔터프라이즈 모드 사이트 목록을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-138">This policy lets you create a separate Enterprise Mode Site list for Microsoft Edge.</span></span> <span data-ttu-id="96e95-139">"Internet Explorer 통합 구성"을 사용하도록 설정된 경우 이 정책을 사용하도록 설정하면 "엔터프라이즈 모드 IE 웹 사이트 목록 사용" 정책의 설정이 재정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-139">Enabling this policy overrides the settings in the "Use the Enterprise Mode IE website list" policy, if "Configure Internet Explorer integration" is enabled.</span></span> <span data-ttu-id="96e95-140">이 정책을 사용하지 않도록 설정하거나 구성하지 않으면 "Internet Explorer 통합 구성" 정책의 기본 동작에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-140">Disabling or not configuring this policy doesn't affect the default behavior of the "Configure Internet Explorer integration" policy.</span></span>
    > [!NOTE]
    > <span data-ttu-id="96e95-141">Microsoft Edge 정책을 구성할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-141">It is not mandatory to configure the Microsoft Edge policy.</span></span> <span data-ttu-id="96e95-142">많은 조직에서는 이를 재정의로 사용하여 IE 정책을 사용하는 모든 사용자의 현재 사이트 목록을 대상으로 하고 업데이트된 버전을 Microsoft Edge 정책과 함께 파일럿 용도로보다 쉽게 대상으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-142">Many organizations use this as an override, allowing them to target the current Site List at all users with the IE policy, and more easily target an updated version to pilot uses with the Microsoft Edge policy.</span></span>

<span data-ttu-id="96e95-143">엔터프라이즈 모드 사이트 목록에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96e95-143">For more information about Enterprise Mode Site lists, see:</span></span>

- [<span data-ttu-id="96e95-144">Enterprise Mode Site List Manager 사용</span><span class="sxs-lookup"><span data-stu-id="96e95-144">Use the Enterprise Mode Site List Manager</span></span>](/internet-explorer/ie11-deploy-guide/use-the-enterprise-mode-site-list-manager)
- <span data-ttu-id="96e95-145">[파일 및 Enterprise Mode Site List Manager(스키마 v.2)를 사용하여 엔터프라이즈 모드 사이트 목록에 여러 사이트 추가](/internet-explorer/ie11-deploy-guide/add-multiple-sites-to-enterprise-mode-site-list-using-the-version-2-schema-and-enterprise-mode-tool)</span><span class="sxs-lookup"><span data-stu-id="96e95-145">[Add multiple sites to the Enterprise Mode site list using a file and the Enterprise Mode Site List Manager (schema v.2)](/internet-explorer/ie11-deploy-guide/add-multiple-sites-to-enterprise-mode-site-list-using-the-version-2-schema-and-enterprise-mode-tool).</span></span>

### <a name="configure-using-the-use-the-enterprise-mode-ie-website-list-policy"></a><span data-ttu-id="96e95-146">엔터프라이즈 모드 IE 웹 사이트 사용 정책을 사용하여 구성</span><span class="sxs-lookup"><span data-stu-id="96e95-146">Configure using the Use the Enterprise Mode IE website list policy</span></span>

<span data-ttu-id="96e95-147">IE 모드는 Internet Explorer 용 엔터프라이즈 사이트 목록을 구성하는 기존 정책을 사용하여 단일 목록을 만들고 유지 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-147">IE mode can use the existing policy configuring the Enterprise Site List for Internet Explorer, allowing you to create and maintain a single list.</span></span>

1. <span data-ttu-id="96e95-148">사이트 목록 XML 만들기 또는 다시 사용</span><span class="sxs-lookup"><span data-stu-id="96e95-148">Create or reuse a Site List XML</span></span>
    1. <span data-ttu-id="96e95-149">이제 _\<open-in\>IE11\</open-in\>_ 요소가 있는 모든 사이트가 IE 모드에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-149">All sites that have the element _\<open-in\>IE11\</open-in\>_ will now open in IE mode.</span></span>
2. <span data-ttu-id="96e95-150">그룹 정책 편집기 열기.</span><span class="sxs-lookup"><span data-stu-id="96e95-150">Open Group Policy Editor.</span></span>
3. <span data-ttu-id="96e95-151">**컴퓨터 구성** > **관리 템플릿** > **Windows 구성 요소** > **Internet Explorer**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-151">Click **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Internet Explorer**.</span></span>
4. <span data-ttu-id="96e95-152">**엔터프라이즈 모드 IE 웹 사이트 목록 사용**을 두 번 클릭합니다</span><span class="sxs-lookup"><span data-stu-id="96e95-152">Double-click **Use the Enterprise Mode IE website list**.</span></span>
5. <span data-ttu-id="96e95-153">**사용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-153">Select **Enabled**.</span></span>
6. <span data-ttu-id="96e95-154">**옵션** 아래에서 웹 사이트 목록의 위치를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-154">Under **Options**, type the location of website list.</span></span> <span data-ttu-id="96e95-155">다음 위치 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-155">You can use one of the following locations:</span></span>
    - <span data-ttu-id="96e95-156">(권장) HTTPS 위치: **https**:**//iemode/sites.xml**</span><span class="sxs-lookup"><span data-stu-id="96e95-156">(Recommended) HTTPS location: **https**:**//iemode/sites.xml**</span></span>
    - <span data-ttu-id="96e95-157">로컬 네트워크 파일: **\\\network\shares\sites.xml**</span><span class="sxs-lookup"><span data-stu-id="96e95-157">Local network file: **\\\network\shares\sites.xml**</span></span>
    - <span data-ttu-id="96e95-158">로컬 파일: **file:///c:/Users/\<user\>/Documents/sites.xml**</span><span class="sxs-lookup"><span data-stu-id="96e95-158">Local file: **file:///c:/Users/\<user\>/Documents/sites.xml**</span></span>
7. <span data-ttu-id="96e95-159">**확인** 또는 **적용**을 클릭하여 이러한 설정을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-159">Click **OK** or **Apply** to save these settings.</span></span>

### <a name="configure-using-the-configure-the-enterprise-mode-site-list-policy"></a><span data-ttu-id="96e95-160">엔터프라이즈 모드 사이트 목록 구성 정책을 사용하여 구성</span><span class="sxs-lookup"><span data-stu-id="96e95-160">Configure using the Configure the Enterprise Mode Site List policy</span></span>

<span data-ttu-id="96e95-161">Microsoft Edge에 대한 별도의 정책으로 IE 모드를 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-161">You can also configure IE mode with a separate policy for Microsoft Edge.</span></span> <span data-ttu-id="96e95-162">이 추가 정책을 통해 IE 사이트 목록을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-162">This additional policy allows you to override the IE site list.</span></span> <span data-ttu-id="96e95-163">예를 들어, 일부 조직은 프로덕션 사이트 목록을 모든 사용자에게 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-163">For example, some organizations will target the production site list to all users.</span></span> <span data-ttu-id="96e95-164">그런 다음이 정책을 사용하여 파일럿 사이트 목록을 소규모 사용자 그룹에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-164">You can then deploy the pilot site list to a small group of users using this policy.</span></span>

1. <span data-ttu-id="96e95-165">사이트 목록 XML 만들기 또는 다시 사용</span><span class="sxs-lookup"><span data-stu-id="96e95-165">Create or reuse a Site List XML</span></span>
    1. <span data-ttu-id="96e95-166">이제 _\<open-in\>IE11\</open-in\>_ 요소가 있는 모든 사이트가 IE 모드에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-166">All sites that have the element _\<open-in\>IE11\</open-in\>_ will now open in IE mode.</span></span>
2. <span data-ttu-id="96e95-167">그룹 정책 편집기 열기.</span><span class="sxs-lookup"><span data-stu-id="96e95-167">Open Group Policy Editor.</span></span>
3. <span data-ttu-id="96e95-168">**컴퓨터 구성** > **관리 템플릿** > **Microsoft Edge**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-168">Click **Computer Configuration** > **Administrative Templates** > **Microsoft Edge**.</span></span>
4. <span data-ttu-id="96e95-169">**엔터프라이즈 모드 사이트 목록 구성**을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-169">Double-click **Configure the Enterprise Mode Site List**.</span></span>
5. <span data-ttu-id="96e95-170">**사용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-170">Select **Enabled**.</span></span>
6. <span data-ttu-id="96e95-171">**옵션** 아래에서 웹 사이트 목록의 위치를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-171">Under **Options**, type the location of website list.</span></span> <span data-ttu-id="96e95-172">다음 위치 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-172">You can use one of the following locations:</span></span>
    - <span data-ttu-id="96e95-173">(권장) HTTPS 위치: **https**:**//iemode/sites.xml**</span><span class="sxs-lookup"><span data-stu-id="96e95-173">(Recommended) HTTPS location: **https**:**//iemode/sites.xml**</span></span> <!--Trying to keep this from being an active link in MD -->
    - <span data-ttu-id="96e95-174">로컬 네트워크 파일: **\\\network\shares\sites.xml**</span><span class="sxs-lookup"><span data-stu-id="96e95-174">Local network file: **\\\network\shares\sites.xml**</span></span>
    - <span data-ttu-id="96e95-175">로컬 파일: **file:///c:/Users/\<user\>/Documents/sites.xml**</span><span class="sxs-lookup"><span data-stu-id="96e95-175">Local file: **file:///c:/Users/\<user\>/Documents/sites.xml**</span></span>
7. <span data-ttu-id="96e95-176">**확인** 또는 **적용**을 클릭하여 이러한 설정을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-176">Click **OK** or **Apply** to save these settings.</span></span>

### <a name="configure-all-intranet-sites"></a><span data-ttu-id="96e95-177">모든 인트라넷 사이트 구성</span><span class="sxs-lookup"><span data-stu-id="96e95-177">Configure all intranet sites</span></span>

<span data-ttu-id="96e95-178">로컬 모드 인트라넷 영역의 모든 사이트에 대해 IE 모드를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-178">IE mode can be configured as for all sites in the Local Intranet zone.</span></span> <span data-ttu-id="96e95-179">엔터프라이즈 모드 사이트 목록을 사용하여 IE 모드에서 개별 사이트를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-179">You can remove individual sites from IE mode using an Enterprise Mode Site List.</span></span>

>[!NOTE]
>
> <span data-ttu-id="96e95-180">로컬 인트라넷 영역에는 명시적으로 추가된 사이트가 포함되지만 경험적 접근을 사용하여 이 영역에 사이트가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-180">The Local Intranet zone contains explicitly added sites, but also assigns sites to this zone using heuristics.</span></span> <span data-ttu-id="96e95-181">여기에는 점 없는 호스트 이름(예 **https**:**//payroll**)과 프록시 구성 스크립트가 프록시를 무시하도록 구성한 사이트가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-181">This can include dotless host names (e.g. **https**:**//payroll**) and sites that the proxy configuration script configures to bypass the proxy.</span></span> <span data-ttu-id="96e95-182">외부 당사자가 DNS 또는 프록시를 제어하는 경우 웹 사이트를 강제로 IE 모드로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-182">If an external party controls DNS or proxy, they could potentially force websites into IE mode.</span></span>

1. <span data-ttu-id="96e95-183">로컬 그룹 정책 편집기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-183">Open Local Group Policy Editor.</span></span>
2. <span data-ttu-id="96e95-184">**컴퓨터 구성** > **관리 템플릿** > **Microsoft Edge**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-184">Click **Computer Configuration** > **Administrative Templates** > **Microsoft Edge**.</span></span>
3. <span data-ttu-id="96e95-185">**Internet Explorer에 모든 인트라넷 사이트 보내기**를 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-185">Double-click **Send all intranet sites to Internet Explorer**.</span></span>
4. <span data-ttu-id="96e95-186">**사용**을 선택한 다음 **확인** 또는 **적용**을 클릭하여 정책 설정을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-186">Select **Enabled**, and then click **OK** or **Apply** to save the policy settings.</span></span>

## <a name="redirect-sites-from-ie-to-microsoft-edge"></a><span data-ttu-id="96e95-187">IE에서 Microsoft Edge로 사이트 리디렉션</span><span class="sxs-lookup"><span data-stu-id="96e95-187">Redirect sites from IE to Microsoft Edge</span></span>

<span data-ttu-id="96e95-188">사용자가 필요하지 않은 사이트에 Internet Explorer를 사용하지 못하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-188">You can prevent your users from using Internet Explorer for sites that don't need it.</span></span> <span data-ttu-id="96e95-189">Internet Explorer는 사이트 목록에 없는 사이트를 Microsoft Edge로 자동 리디렉션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-189">Internet Explorer can automatically redirect sites to Microsoft Edge if they aren't on your site list.</span></span>

1. <span data-ttu-id="96e95-190">그룹 정책 편집기 열기.</span><span class="sxs-lookup"><span data-stu-id="96e95-190">Open Group Policy Editor.</span></span>
2. <span data-ttu-id="96e95-191">**컴퓨터 구성** > **관리 도구** > **Windows 구성 요소** > **Internet Explorer**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-191">Click **Computer Configuration** > **Administrative Tools** > **Windows Components** > **Internet Explorer**.</span></span>
3. <span data-ttu-id="96e95-192">**엔터프라이즈 모드 사이트 목록에 포함되지 않은 모든 사이트를 Microsoft Edge로 보내기**를 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-192">Double-click **Send all sites not included in the Enterprise Mode Site List to Microsoft Edge.**</span></span>
4. <span data-ttu-id="96e95-193">**사용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-193">Select **Enabled**</span></span>
5. <span data-ttu-id="96e95-194">**확인** 또는 **적용**을 클릭하여 이러한 설정을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-194">Click **OK** or **Apply** to save these settings.</span></span>
6. <span data-ttu-id="96e95-195">**리디렉션된 사이트를 여는 데 사용할 Microsoft Edge 채널 구성**을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-195">Double-click **Configure which channel of Microsoft Edge to use for opening redirected sites**.</span></span>
7. <span data-ttu-id="96e95-196">**사용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-196">Select **Enabled**.</span></span>
8. <span data-ttu-id="96e95-197">**옵션** 아래에서 사용할 채널에 대한 상위 3가지 선택을 선택하세요. Internet Explorer는 사용자가 해당 장치에 설치한 최상위 선택 항목으로 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-197">Under **Options**, select your top three choices for the channel to use - Internet Explorer will redirect to the highest ranked choice that the user has installed on that device:</span></span>
   - <span data-ttu-id="96e95-198">Microsoft Edge 안정</span><span class="sxs-lookup"><span data-stu-id="96e95-198">Microsoft Edge Stable</span></span>
   - <span data-ttu-id="96e95-199">Microsoft Edge Beta 버전 77 이상</span><span class="sxs-lookup"><span data-stu-id="96e95-199">Microsoft Edge Beta version 77 or later</span></span>
   - <span data-ttu-id="96e95-200">Microsoft Edge Dev 버전 77 이상</span><span class="sxs-lookup"><span data-stu-id="96e95-200">Microsoft Edge Dev version 77 or later</span></span>
   - <span data-ttu-id="96e95-201">Microsoft Edge Canary 버전 77 이상</span><span class="sxs-lookup"><span data-stu-id="96e95-201">Microsoft Edge Canary version 77 or later</span></span>
   - <span data-ttu-id="96e95-202">Microsoft Edge 버전 45 이하</span><span class="sxs-lookup"><span data-stu-id="96e95-202">Microsoft Edge version 45 or earlier</span></span>
9. <span data-ttu-id="96e95-203">**확인** 또는 **적용**을 클릭하여 이러한 설정을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="96e95-203">Click **OK** or **Apply** to save these settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="96e95-204">참고 항목</span><span class="sxs-lookup"><span data-stu-id="96e95-204">See also</span></span>

- [<span data-ttu-id="96e95-205">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="96e95-205">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="96e95-206">IE 모드 정보</span><span class="sxs-lookup"><span data-stu-id="96e95-206">About IE mode</span></span>](./edge-ie-mode.md)
- [<span data-ttu-id="96e95-207">추가 엔터프라이즈 모드 정보</span><span class="sxs-lookup"><span data-stu-id="96e95-207">Additional Enterprise Mode information</span></span>](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)