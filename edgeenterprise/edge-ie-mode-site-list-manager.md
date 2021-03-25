---
title: 'Microsoft Edge의 엔터프라이즈 사이트 목록 관리자 '
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 02/02/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 'Microsoft Edge에서 엔터프라이즈 사이트 목록 관리자 활성화 및 사용 '
ms.openlocfilehash: 51d431f838bcb385a5cd8f4ef85651e9254aed62
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447352"
---
# <a name="enterprise-site-list-manager-in-microsoft-edge"></a><span data-ttu-id="93ba3-103">Microsoft Edge의 엔터프라이즈 사이트 목록 관리자</span><span class="sxs-lookup"><span data-stu-id="93ba3-103">Enterprise Site List Manager in Microsoft Edge</span></span>

<span data-ttu-id="93ba3-104">이 문서에서는 Microsoft Edge에서 엔터프라이즈 사이트 목록 관리자에 액세스하도록 설정하고 이를 사용하여 Internet Explorer 모드에 대한 엔터프라이즈 모드 사이트 목록을 만들고, 편집하고, 내보내는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-104">This article explains how to enable access to and use the Enterprise Site List Manager in Microsoft Edge to create, edit and export your Enterprise Mode Site List for Internet Explorer mode.</span></span>

> [!NOTE]
> <span data-ttu-id="93ba3-105">이 문서는 Microsoft Edge 버전 89 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-105">This article applies to Microsoft Edge version 89 or later.</span></span> 

## <a name="overview"></a><span data-ttu-id="93ba3-106">개요</span><span class="sxs-lookup"><span data-stu-id="93ba3-106">Overview</span></span>

<span data-ttu-id="93ba3-107">엔터프라이즈 사이트 목록 관리자는 조직의 사이트 목록을 만들고, 편집하고, 내보낼 수 있는 [독립 실행형 Enterprise Mode Site List Manager 도구](https://www.microsoft.com/download/details.aspx?id=49974)의 브라우저 내 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-107">The Enterprise Site List Manager is an in-browser version of the [standalone Enterprise Mode Site List Manager tool](https://www.microsoft.com/download/details.aspx?id=49974) that lets you create, edit, and export your organization’s site list.</span></span>

<span data-ttu-id="93ba3-108">Internet Explorer 모드용 도구의 향후 향상된 기능도 Microsoft Edge의 엔터프라이즈 사이트 목록 관리자를 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-108">Future improvements to the tool for Internet Explorer mode will be available through Enterprise Site List Manager in Microsoft Edge.</span></span> <span data-ttu-id="93ba3-109">독립 실행형 도구는 다운로드 센터에서 계속 사용할 수 있지만 기능 업데이트는 받을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-109">The standalone tool will continue to be available in the Download Center but won't get any feature updates.</span></span>

## <a name="enabling-access-to-enterprise-site-list-manager"></a><span data-ttu-id="93ba3-110">엔터프라이즈 사이트 목록 관리자에 대한 액세스 사용</span><span class="sxs-lookup"><span data-stu-id="93ba3-110">Enabling access to Enterprise Site List Manager</span></span>

<span data-ttu-id="93ba3-111">[EnterpriseModeSiteListManagerAllowed](./microsoft-edge-policies.md#enterprisemodesitelistmanagerallowed) 그룹 정책을 사용하여 도구에 대한 액세스를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-111">You can configure access to the tool by using the [EnterpriseModeSiteListManagerAllowed](./microsoft-edge-policies.md#enterprisemodesitelistmanagerallowed) group policy.</span></span>

<span data-ttu-id="93ba3-112">이 옵션을 사용하도록 설정하면 *edge://compat*에서 사용자의 왼쪽 탐색 창에 엔터프라이즈 사이트 목록 관리자라는 옵션이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-112">If enabled, your users will see an option named Enterprise Site List Manager on the left navigation pane in *edge://compat*.</span></span> <span data-ttu-id="93ba3-113">이 기능을 사용하지 않도록 설정하면 왼쪽 탐색 창에 Enterprise Site List Manager에 대한 진입점이 사용자에게 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-113">If disabled, users will not see the entry point to Enterprise Site List Manager in the left navigation pane.</span></span> <span data-ttu-id="93ba3-114">이는 기본 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-114">This is the default behavior.</span></span>

## <a name="using-the-enterprise-site-list-manager"></a><span data-ttu-id="93ba3-115">엔터프라이즈 사이트 목록 관리자 사용</span><span class="sxs-lookup"><span data-stu-id="93ba3-115">Using the Enterprise Site List Manager</span></span>

<span data-ttu-id="93ba3-116">엔터프라이즈 사이트 목록 관리자 도구는 v.2 버전의 스키마를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-116">The Enterprise Site List Manager tool uses the v.2 version of the schema.</span></span> <span data-ttu-id="93ba3-117">v.1 버전의 스키마를 Enterprise Mode Site List Manager(스키마 v.2)로 가져오면 XML이 v.2 버전의 스키마로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-117">If you import a v.1 version schema into the Enterprise Site List Manager (schema v.2), the XML is saved into the v.2 version of the schema.</span></span> <span data-ttu-id="93ba3-118">[엔터프라이즈 모드 스키마 v.2 지침](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="93ba3-118">See [Enterprise Mode schema v.2 guidance](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance).</span></span>

### <a name="add-single-sites-to-your-site-list"></a><span data-ttu-id="93ba3-119">사이트 목록에 단일 사이트 추가</span><span class="sxs-lookup"><span data-stu-id="93ba3-119">Add single sites to your site list</span></span>  

<span data-ttu-id="93ba3-120">다음 단계에 따라 사이트 목록에 개별 사이트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-120">Use the following steps to add individual sites to your site list.</span></span>

> [!NOTE]
> <span data-ttu-id="93ba3-121">인터넷 또는 인트라넷 영역이 아닌 특정 URL만 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-121">You can only add specific URLs, not Internet or Intranet Zones.</span></span>

1. <span data-ttu-id="93ba3-122">엔터프라이즈 사이트 목록 관리자에서  **사이트 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-122">In the Enterprise Site List Manager, click **Add a site**.</span></span>
2. <span data-ttu-id="93ba3-123">추가할 웹 사이트의 URL(예: URL 상자에  <domain>.com 또는  <domain>.com/<path> )을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-123">Type the URL for the website you’d like to add, for example: <domain>.com or <domain>.com/<path> in the URL box.</span></span>
3. <span data-ttu-id="93ba3-124">목록의 **열기** 에서 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-124">Select one of the following options from the **Open in** list:</span></span>

   - <span data-ttu-id="93ba3-125">**IE11**.</span><span class="sxs-lookup"><span data-stu-id="93ba3-125">**IE11**.</span></span> <span data-ttu-id="93ba3-126">IE11 응용 프로그램에서 사이트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-126">Opens the site in the IE11 application.</span></span>
   - <span data-ttu-id="93ba3-127">**IE 모드**.</span><span class="sxs-lookup"><span data-stu-id="93ba3-127">**IE mode**.</span></span> <span data-ttu-id="93ba3-128">사용하도록 설정한 경우 Microsoft Edge의 Internet Explorer 모드에서 사이트를 열고, 그렇지 않은 경우, IE11 앱에서 엽니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-128">Opens the site in Internet Explorer mode on Microsoft Edge if enabled and in the IE11 app otherwise.</span></span> <span data-ttu-id="93ba3-129"> [Microsoft Edge에서 Internet Explorer 모드](./edge-ie-mode.md)를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-129">See [Internet Explorer mode on Microsoft Edge](./edge-ie-mode.md).</span></span>
   - <span data-ttu-id="93ba3-130">**MSEdge**.</span><span class="sxs-lookup"><span data-stu-id="93ba3-130">**MSEdge**.</span></span> <span data-ttu-id="93ba3-131">Microsoft Edge에서 사이트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-131">Opens the site in Microsoft Edge.</span></span>
   - <span data-ttu-id="93ba3-132">**구성 가능**.</span><span class="sxs-lookup"><span data-stu-id="93ba3-132">**Configurable**.</span></span> <span data-ttu-id="93ba3-133">사이트가 IE 모드 엔진 결정에 참여할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-133">Allows the site to participate in IE mode engine determination.</span></span> <span data-ttu-id="93ba3-134">[IE 모드에서 구성 가능한 사이트](./edge-learnmore-configurable-sites-ie-mode.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="93ba3-134">See [Configurable sites in IE mode](./edge-learnmore-configurable-sites-ie-mode.md)</span></span>
   - <span data-ttu-id="93ba3-135">**없음**.</span><span class="sxs-lookup"><span data-stu-id="93ba3-135">**None**.</span></span> <span data-ttu-id="93ba3-136">사용자가 선택하는 브라우저에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-136">Opens in whatever browser the user chooses.</span></span>  

4. <span data-ttu-id="93ba3-137"> *\*Compat 모드*\*에서 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-137">Under **Compat Mode**, choose one of the following options:</span></span>

   - <span data-ttu-id="93ba3-138">**IE8Enterprise**.</span><span class="sxs-lookup"><span data-stu-id="93ba3-138">**IE8Enterprise**.</span></span> <span data-ttu-id="93ba3-139">사이트를 IE8 엔터프라이즈 모드로 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-139">Loads the site in IE8 Enterprise Mode.</span></span>
   - <span data-ttu-id="93ba3-140">**IE7Enterprise**.</span><span class="sxs-lookup"><span data-stu-id="93ba3-140">**IE7Enterprise**.</span></span> <span data-ttu-id="93ba3-141">사이트를 IE7 엔터프라이즈 모드로 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-141">Loads the site in IE7 Enterprise Mode.</span></span>
   - <span data-ttu-id="93ba3-142">**IE[x]**.</span><span class="sxs-lookup"><span data-stu-id="93ba3-142">**IE[x]**.</span></span> <span data-ttu-id="93ba3-143">여기서 [x]는 문서 모드 번호이고 사이트가 지정된 문서 모드로 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-143">Where [x] is the document mode number and the site loads in the specified document mode.</span></span>
   - <span data-ttu-id="93ba3-144">**기본 모드**.</span><span class="sxs-lookup"><span data-stu-id="93ba3-144">**Default Mode**.</span></span> <span data-ttu-id="93ba3-145">사이트를 페이지의 기본 호환 모드를 사용하여 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-145">Loads the site using the default compatibility mode for the page.</span></span>

   <span data-ttu-id="93ba3-146">도메인 내의 경로로 인해 도메인 자체와 다른 호환 모드가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-146">The path within a domain can require a different compatibility mode from the domain itself.</span></span> <span data-ttu-id="93ba3-147">예를 들어 도메인이 기본 IE11 브라우저에서는 제대로 작동하는 것처럼 보일 수 있지만 경로의 문제가 있어 엔터프라이즈 모드를 사용해야 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-147">For example, the domain might look fine in the default IE11 browser, but the path might have problems and require the use of Enterprise Mode.</span></span> <span data-ttu-id="93ba3-148">도메인을 이전에 추가한 경우 원래 호환성 선택 항목이 여전히 선택되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-148">If you added the domain previously, your original compatibility choice is still selected.</span></span> <span data-ttu-id="93ba3-149">그러나 도메인이 새 도메인이면  **IE8 엔터프라이즈 모드** 가 자동으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-149">However, if the domain is new, **IE8 Enterprise Mode** is automatically selected.</span></span>

   <span data-ttu-id="93ba3-150">엔터프라이즈 모드는 문서 모드보다 우선 적용되므로, 엔터프라이즈 모드 사이트 목록에 이미 포함된 사이트는 이 업데이트의 영향을 받지 않으며, 원래대로 엔터프라이즈 모드로 계속 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-150">Enterprise Mode takes precedence over document modes, so sites that are already included in the Enterprise Mode site list won’t be affected by this update and will continue to load in Enterprise Mode, as usual.</span></span> <span data-ttu-id="93ba3-151">문서 모드 사용에 대한 자세한 내용은  [문서 모드 및 엔터프라이즈 모드 사이트 목록을 사용하여 웹 호환성 문제 해결](/internet-explorer/ie11-deploy-guide/fix-compat-issues-with-doc-modes-and-enterprise-mode-site-list)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="93ba3-151">For more specific information about using document modes, see [Fix web compatibility issues using document modes and the Enterprise Mode site list](/internet-explorer/ie11-deploy-guide/fix-compat-issues-with-doc-modes-and-enterprise-mode-site-list).</span></span>

5. <span data-ttu-id="93ba3-152">**리디렉션 허용** 확인란은 서버 쪽 리디렉션 처리에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-152">The **Allow Redirect** checkbox applies to the treatment of server-side redirects.</span></span> <span data-ttu-id="93ba3-153">이 확인란을 선택하면 열기 태그에 지정된 브라우저에서 서버 쪽 리디렉션이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-153">If you check this box, server-side redirects will open in the browser specified by the open-in tag.</span></span> <span data-ttu-id="93ba3-154">자세한 내용은  [여기](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance#updated-schema-attributes)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="93ba3-154">For more information, see [here](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance#updated-schema-attributes).</span></span>
6. <span data-ttu-id="93ba3-155">웹 사이트에 대한 설명을  **설명** 상자에 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-155">Type any comments about the website into the **Comment** box.</span></span> <span data-ttu-id="93ba3-156">관리자는 이 도구에 있는 동안에만 설명을 볼 수 있으며 이러한 설명은 사이트 목록 xml에 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-156">Administrators can only see comments while they’re in this tool and these comments are retained in the site list xml.</span></span>
7. <span data-ttu-id="93ba3-157">사이트 목록에 사이트를 추가하려면  **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-157">Click **Add** to add the site to your site list.</span></span>

### <a name="export-site-list-to-xml"></a><span data-ttu-id="93ba3-158">XML로 사이트 목록 내보내기</span><span class="sxs-lookup"><span data-stu-id="93ba3-158">Export site list to XML</span></span>

<span data-ttu-id="93ba3-159">엔터프라이즈 사이트 목록 관리자에서 사이트 목록을 만든 후 엔터프라이즈 모드(.EMIE) 또는 XML 파일로 콘텐츠를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-159">After you create your site list in the Enterprise Site List Manager, you can export the contents to an Enterprise Mode (.EMIE) or XML file.</span></span> 

> [!NOTE]
> <span data-ttu-id="93ba3-160">이 파일에는 호환성 모드 선택 항목을 비롯하여 모든 URL이 포함되므로 안전한 곳에 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-160">This file includes all of your URLs, including your compatibility mode selections and should be stored somewhere safe.</span></span>

<span data-ttu-id="93ba3-161">사이트 목록을 내보내려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-161">To export the site list, follow these steps:</span></span>

1. <span data-ttu-id="93ba3-162">엔터프라이즈 사이트 목록 관리자에서 **XML로 내보내기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-162">In the Enterprise Site List Manager, click **Export to XML**.</span></span>
2. <span data-ttu-id="93ba3-163">**버전 번호**와 **파일 이름**을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-163">Enter a **Version number** and a **File name**.</span></span>
3. <span data-ttu-id="93ba3-164">**내보내기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-164">Click **Export**.</span></span>

<span data-ttu-id="93ba3-165">파일을 로컬로 저장하거나 네트워크 공유에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-165">You can save the file locally or to a network share.</span></span> <span data-ttu-id="93ba3-166">그러나 반드시 레지스트리 키에 지정된 위치에 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-166">However, you must make sure you deploy it to the location specified in your registry key.</span></span> <span data-ttu-id="93ba3-167">자세한 내용은  [Internet Explorer 모드 켜기 및 사이트 목록 사용](./edge-ie-mode-policies.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="93ba3-167">For more information, see [Turn on Internet Explorer mode and use a site list](./edge-ie-mode-policies.md).</span></span>

### <a name="import-multiple-sites-to-your-site-list"></a><span data-ttu-id="93ba3-168">사이트 목록으로 여러 사이트 가져오기</span><span class="sxs-lookup"><span data-stu-id="93ba3-168">Import multiple sites to your site list</span></span>

<span data-ttu-id="93ba3-169">.xml 파일을 만든 후 **XML에서 가져오기**를 사용하여 편집기에 사이트를 대량으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-169">After you create your .xml file, you can bulk add sites to the editor using **Import from XML**.</span></span>

<span data-ttu-id="93ba3-170">편집기에서 모든 내용을 바꾸려면 생략 부호(...)를 클릭한 다음 **목록 지우기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-170">If you want to replace all the contents in the editor, click  the ellipsis (…) and then choose **Clear list**.</span></span> <span data-ttu-id="93ba3-171">편집기를 지운 후 다음 단계에 따라 사이트를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-171">After you clear the editor, use the following steps to import the site.</span></span>

1. <span data-ttu-id="93ba3-172">엔터프라이즈 사이트 목록 관리자에서 **XML에서 가져오기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-172">In the Enterprise Site List Manager, click **Import from XML**.</span></span> 
2. <span data-ttu-id="93ba3-173">**파일 선택**을 클릭하여 사이트 목록을 선택하고 포함된 사이트를 도구에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-173">Click **Choose file** to select your site list to add the included sites to the tool.</span></span> <span data-ttu-id="93ba3-174">추가할 사이트 목록을 선택하고  **열기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-174">Pick the site list you want to add and then click **Open**.</span></span> <span data-ttu-id="93ba3-175">지원되는 가져오기 형식은 엔터프라이즈 모드 사이트 목록에 대한 v.2 스키마를 포함하는 .xml, .emie 또는 .txt입니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-175">Supported formats for Import are .xml, .emie or .txt containing the v.2 schema for Enterprise Mode Site List.</span></span> <span data-ttu-id="93ba3-176">[엔터프라이즈 모드 스키마 v.2 지침](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="93ba3-176">See [Enterprise Mode schema v.2 guidance](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance).</span></span>
3. <span data-ttu-id="93ba3-177"> *\*로드** 를 클릭하여 사이트를 파일에서 편집기로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-177">Click **Load** to add the sites from the file tp the editor.</span></span>

<span data-ttu-id="93ba3-178">파일을 로컬로 저장하거나 네트워크 공유에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-178">You can save the file locally or to a network share.</span></span> <span data-ttu-id="93ba3-179">그러나 반드시 레지스트리 키에 지정된 위치에 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-179">However, you must make sure you deploy it to the location specified in your registry key.</span></span> <span data-ttu-id="93ba3-180">자세한 내용은  [Internet Explorer 모드 켜기 및 사이트 목록 사용](./edge-ie-mode-policies.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="93ba3-180">For more information, see [Turn on Internet Explorer mode and use a site list](./edge-ie-mode-policies.md).</span></span>

### <a name="edit-sites-in-your-site-list"></a><span data-ttu-id="93ba3-181">사이트 목록에서 사이트 편집</span><span class="sxs-lookup"><span data-stu-id="93ba3-181">Edit sites in your site list</span></span>

 <span data-ttu-id="93ba3-182">엔터프라이즈 사이트 목록 관리자에서 기존 사이트 항목의 특성을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-182">You can edit attributes of existing site entries in the Enterprise Site List Manager.</span></span> <span data-ttu-id="93ba3-183">또한 연결된 설명을 추가하거나, 제거하거나, 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-183">You can also add, remove, or delete associated comments.</span></span>

1. <span data-ttu-id="93ba3-184">엔터프라이즈 사이트 목록 관리자에서 생략 부호(...)를 클릭하고 편집할 URL의 **사이트 편집**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-184">In the Enterprise Site List Manager, click the ellipsis (…) and choose **Edit site** for the URL you want to edit.</span></span>
2. <span data-ttu-id="93ba3-185">URL을 제외한 사이트 항목의 특성을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-185">You can edit any attribute of the site entry except the URL.</span></span> <span data-ttu-id="93ba3-186">편집을 마친 후 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-186">Click **Save** after you finish editing.</span></span>

   > [!NOTE]
   > <span data-ttu-id="93ba3-187">사이트 항목을 삭제하려면 1단계에서 **사이트 삭제**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-187">If you want to delete a site entry, choose **Delete site** in step 1.</span></span>

3. <span data-ttu-id="93ba3-188">**XML로 내보내기**를 클릭하고 업데이트된 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-188">Click **Export to XML**, and save the updated file.</span></span>

<span data-ttu-id="93ba3-189">파일을 로컬로 저장하거나 네트워크 공유에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-189">You can save the file locally or to a network share.</span></span> <span data-ttu-id="93ba3-190">그러나 반드시 레지스트리 키에 지정된 위치에 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-190">However, you must make sure you deploy it to the location specified in your registry key.</span></span> <span data-ttu-id="93ba3-191">자세한 내용은  [Internet Explorer 모드 켜기 및 사이트 목록 사용](./edge-ie-mode-policies.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="93ba3-191">For more information, see [Turn on Internet Explorer mode and use a site list](./edge-ie-mode-policies.md).</span></span>

### <a name="preview-your-site-list-in-xml-format"></a><span data-ttu-id="93ba3-192">XML 형식으로 사이트 목록 미리 보기</span><span class="sxs-lookup"><span data-stu-id="93ba3-192">Preview your site list in XML format</span></span>

<span data-ttu-id="93ba3-193">사이트 목록 위치를 내보내고 저장하기 전에 편집기에서 XML 형식으로 사이트를 미리 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-193">You can preview the sites in the editor in XML format before you export and save to your site list location.</span></span> <span data-ttu-id="93ba3-194">**XML 미리 보기**를 클릭하여 새 탭에서 파일을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-194">Click **XML preview** to open the file in a new tab.</span></span>

### <a name="search-in-the-enterprise-site-list-manager"></a><span data-ttu-id="93ba3-195">엔터프라이즈 사이트 목록 관리자에서 검색</span><span class="sxs-lookup"><span data-stu-id="93ba3-195">Search in the Enterprise Site List Manager</span></span>

<span data-ttu-id="93ba3-196">특정 사이트가 사이트 목록에 이미 나타나는지 검색하여 다시 추가하지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-196">You can search to see if a specific site already appears in your site list so you don’t try to add it again.</span></span>

<span data-ttu-id="93ba3-197">검색을 하려면 URL의 일부를 편집기 오른쪽 위에 있는  **URL로 사이트 필터링** 검색 상자에 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="93ba3-197">To search, type part of the URL into the **Filter sites by URL** search box on the top right-hand corner of the editor.</span></span>

## <a name="see-also"></a><span data-ttu-id="93ba3-198">참고 항목</span><span class="sxs-lookup"><span data-stu-id="93ba3-198">See also</span></span>

- [<span data-ttu-id="93ba3-199">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="93ba3-199">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="93ba3-200">IE 모드 정보</span><span class="sxs-lookup"><span data-stu-id="93ba3-200">About IE mode</span></span>](./edge-ie-mode.md)
- [<span data-ttu-id="93ba3-201">엔터프라이즈 모드 스키마 v.2 지침</span><span class="sxs-lookup"><span data-stu-id="93ba3-201">Enterprise Mode schema v.2 guidance</span></span>](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)
- [<span data-ttu-id="93ba3-202">추가 엔터프라이즈 모드 정보</span><span class="sxs-lookup"><span data-stu-id="93ba3-202">Additional Enterprise Mode information</span></span>](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)