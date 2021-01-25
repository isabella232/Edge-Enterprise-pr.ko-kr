---
title: 'Microsoft Edge의 엔터프라이즈 사이트 목록 관리자 '
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 01/20/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 'Microsoft Edge에서 엔터프라이즈 사이트 목록 관리자 활성화 및 사용 '
ms.openlocfilehash: 2d10886624918c97933a841c428ea66ccf5b34c9
ms.sourcegitcommit: a6c58b19976c194299be217c58b9a99b48756fd0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11281054"
---
# <span data-ttu-id="90f22-103">Microsoft Edge의 엔터프라이즈 사이트 목록 관리자</span><span class="sxs-lookup"><span data-stu-id="90f22-103">Enterprise Site List Manager in Microsoft Edge</span></span>

<span data-ttu-id="90f22-104">이 문서에서는 Microsoft Edge에서 엔터프라이즈 사이트 목록 관리자에 액세스하도록 설정하고 이를 사용하여 Internet Explorer 모드에 대한 엔터프라이즈 모드 사이트 목록을 만들고, 편집하고, 내보내는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-104">This article explains how to enable access to and use the Enterprise Site List Manager in Microsoft Edge to create, edit and export your Enterprise Mode Site List for Internet Explorer mode.</span></span>

> [!NOTE]
> <span data-ttu-id="90f22-105">이 문서는 Microsoft Edge 버전 89 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-105">This article applies to Microsoft Edge version 89 or later.</span></span>

## <span data-ttu-id="90f22-106">개요</span><span class="sxs-lookup"><span data-stu-id="90f22-106">Overview</span></span>

<span data-ttu-id="90f22-107">엔터프라이즈 사이트 목록 관리자는 조직의 사이트 목록을 만들고, 편집하고, 내보낼 수 있는 [독립 실행형 Enterprise Mode Site List Manager 도구](https://www.microsoft.com/download/details.aspx?id=49974)의 브라우저 내 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-107">The Enterprise Site List Manager is an in-browser version of the [standalone Enterprise Mode Site List Manager tool](https://www.microsoft.com/download/details.aspx?id=49974) that lets you create, edit, and export your organization’s site list.</span></span>

<span data-ttu-id="90f22-108">Internet Explorer 모드용 도구의 향후 향상된 기능도 Microsoft Edge의 엔터프라이즈 사이트 목록 관리자를 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-108">Future improvements to the tool for Internet Explorer mode will be available through Enterprise Site List Manager in Microsoft Edge.</span></span> <span data-ttu-id="90f22-109">독립 실행형 도구는 다운로드 센터에서 계속 사용할 수 있지만 기능 업데이트는 받을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-109">The standalone tool will continue to be available in the Download Center but won't get any feature updates.</span></span>

## <span data-ttu-id="90f22-110">엔터프라이즈 사이트 목록 관리자에 대한 액세스 사용</span><span class="sxs-lookup"><span data-stu-id="90f22-110">Enabling access to Enterprise Site List Manager</span></span>

<span data-ttu-id="90f22-111">[EnterpriseModeSiteListManagerAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#enterprisemodesitelistmanagerallowed) 그룹 정책을 사용하여 도구에 대한 액세스를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-111">You can configure access to the tool by using the [EnterpriseModeSiteListManagerAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#enterprisemodesitelistmanagerallowed) group policy.</span></span>

<span data-ttu-id="90f22-112">이 옵션을 사용하도록 설정하면 *edge://compat*에서 사용자의 왼쪽 탐색 창에 엔터프라이즈 사이트 목록 관리자라는 옵션이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-112">If enabled, your users will see an option named Enterprise Site List Manager on the left navigation pane in *edge://compat*.</span></span> <span data-ttu-id="90f22-113">사용하지 않도록 설정하면 왼쪽 탐색 창의 엔터프라이즈 사이트 목록 관리자에 대한 진입점이 사용자에게 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-113">If Disabled, users will not see the entry point to Enterprise Site List Manager in the left navigation pane.</span></span> <span data-ttu-id="90f22-114">이는 기본 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-114">This is the default behavior.</span></span>

## <span data-ttu-id="90f22-115">엔터프라이즈 사이트 목록 관리자 사용</span><span class="sxs-lookup"><span data-stu-id="90f22-115">Using the Enterprise Site List Manager</span></span>

<span data-ttu-id="90f22-116">엔터프라이즈 사이트 목록 관리자 도구는 v.2 버전의 스키마를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-116">The Enterprise Site List Manager tool uses the v.2 version of the schema.</span></span> <span data-ttu-id="90f22-117">v.1 버전의 스키마를 Enterprise Mode Site List Manager(스키마 v.2)로 가져오면 XML이 v.2 버전의 스키마로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-117">If you import a v.1 version schema into the Enterprise Site List Manager (schema v.2), the XML is saved into the v.2 version of the schema.</span></span>

### <span data-ttu-id="90f22-118">사이트 목록에 단일 사이트 추가</span><span class="sxs-lookup"><span data-stu-id="90f22-118">Add single sites to your site list</span></span>  

<span data-ttu-id="90f22-119">다음 단계에 따라 사이트 목록에 개별 사이트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-119">Use the following steps to add individual sites to your site list.</span></span>

> [!NOTE]
> <span data-ttu-id="90f22-120">인터넷 또는 인트라넷 영역이 아닌 특정 URL만 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-120">You can only add specific URLs, not Internet or Intranet Zones.</span></span>

1. <span data-ttu-id="90f22-121">엔터프라이즈 사이트 목록 관리자에서  **사이트 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-121">In the Enterprise Site List Manager, click **Add a site**.</span></span>
2. <span data-ttu-id="90f22-122">추가할 웹 사이트의 URL(예: URL 상자에  <domain>.com 또는  <domain>.com/<path> )을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-122">Type the URL for the website you’d like to add, for example: <domain>.com or <domain>.com/<path> in the URL box.</span></span>
3. <span data-ttu-id="90f22-123">목록의 **열기** 에서 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-123">Select one of the following options from the **Open in** list:</span></span>

   - <span data-ttu-id="90f22-124">**IE11**.</span><span class="sxs-lookup"><span data-stu-id="90f22-124">**IE11**.</span></span> <span data-ttu-id="90f22-125">IE11 응용 프로그램에서 사이트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-125">Opens the site in the IE11 application.</span></span>
   - <span data-ttu-id="90f22-126">**IE 모드**.</span><span class="sxs-lookup"><span data-stu-id="90f22-126">**IE mode**.</span></span> <span data-ttu-id="90f22-127">사용하도록 설정한 경우 Microsoft Edge의 Internet Explorer 모드에서 사이트를 열고, 그렇지 않은 경우, IE11 앱에서 엽니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-127">Opens the site in Internet Explorer mode on Microsoft Edge if enabled and in the IE11 app otherwise.</span></span> <span data-ttu-id="90f22-128"> [Microsoft Edge에서 Internet Explorer 모드](https://docs.microsoft.com/deployedge/edge-ie-mode)를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-128">See [Internet Explorer mode on Microsoft Edge](https://docs.microsoft.com/deployedge/edge-ie-mode).</span></span>
   - <span data-ttu-id="90f22-129">**MSEdge**.</span><span class="sxs-lookup"><span data-stu-id="90f22-129">**MSEdge**.</span></span> <span data-ttu-id="90f22-130">Microsoft Edge에서 사이트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-130">Opens the site in Microsoft Edge.</span></span>
   - <span data-ttu-id="90f22-131">**구성 가능**.</span><span class="sxs-lookup"><span data-stu-id="90f22-131">**Configurable**.</span></span> <span data-ttu-id="90f22-132">사이트가 IE 모드 엔진 결정에 참여할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-132">Allows the site to participate in IE mode engine determination.</span></span> <span data-ttu-id="90f22-133">[IE 모드에서 구성 가능한 사이트](https://docs.microsoft.com/deployedge/edge-learnmore-configurable-sites-ie-mode)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="90f22-133">See [Configurable sites in IE mode](https://docs.microsoft.com/deployedge/edge-learnmore-configurable-sites-ie-mode)</span></span>
   - <span data-ttu-id="90f22-134">**없음**.</span><span class="sxs-lookup"><span data-stu-id="90f22-134">**None**.</span></span> <span data-ttu-id="90f22-135">사용자가 선택하는 브라우저에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-135">Opens in whatever browser the user chooses.</span></span>  

4. <span data-ttu-id="90f22-136"> *\*Compat 모드*\*에서 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-136">Under **Compat Mode**, choose one of the following options:</span></span>

   - <span data-ttu-id="90f22-137">**IE8Enterprise**.</span><span class="sxs-lookup"><span data-stu-id="90f22-137">**IE8Enterprise**.</span></span> <span data-ttu-id="90f22-138">사이트를 IE8 엔터프라이즈 모드로 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-138">Loads the site in IE8 Enterprise Mode.</span></span>
   - <span data-ttu-id="90f22-139">**IE7Enterprise**.</span><span class="sxs-lookup"><span data-stu-id="90f22-139">**IE7Enterprise**.</span></span> <span data-ttu-id="90f22-140">사이트를 IE7 엔터프라이즈 모드로 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-140">Loads the site in IE7 Enterprise Mode.</span></span>
   - <span data-ttu-id="90f22-141">**IE[x]**.</span><span class="sxs-lookup"><span data-stu-id="90f22-141">**IE[x]**.</span></span> <span data-ttu-id="90f22-142">여기서 [x]는 문서 모드 번호이고 사이트가 지정된 문서 모드로 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-142">Where [x] is the document mode number and the site loads in the specified document mode.</span></span>
   - <span data-ttu-id="90f22-143">**기본 모드**.</span><span class="sxs-lookup"><span data-stu-id="90f22-143">**Default Mode**.</span></span> <span data-ttu-id="90f22-144">사이트를 페이지의 기본 호환 모드를 사용하여 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-144">Loads the site using the default compatibility mode for the page.</span></span>

   <span data-ttu-id="90f22-145">도메인 내의 경로로 인해 도메인 자체와 다른 호환 모드가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-145">The path within a domain can require a different compatibility mode from the domain itself.</span></span> <span data-ttu-id="90f22-146">예를 들어 도메인이 기본 IE11 브라우저에서는 제대로 작동하는 것처럼 보일 수 있지만 경로의 문제가 있어 엔터프라이즈 모드를 사용해야 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-146">For example, the domain might look fine in the default IE11 browser, but the path might have problems and require the use of Enterprise Mode.</span></span> <span data-ttu-id="90f22-147">도메인을 이전에 추가한 경우 원래 호환성 선택 항목이 여전히 선택되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-147">If you added the domain previously, your original compatibility choice is still selected.</span></span> <span data-ttu-id="90f22-148">그러나 도메인이 새 도메인이면  **IE8 엔터프라이즈 모드** 가 자동으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-148">However, if the domain is new, **IE8 Enterprise Mode** is automatically selected.</span></span>

   <span data-ttu-id="90f22-149">엔터프라이즈 모드는 문서 모드보다 우선 적용되므로, 엔터프라이즈 모드 사이트 목록에 이미 포함된 사이트는 이 업데이트의 영향을 받지 않으며, 원래대로 엔터프라이즈 모드로 계속 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-149">Enterprise Mode takes precedence over document modes, so sites that are already included in the Enterprise Mode site list won’t be affected by this update and will continue to load in Enterprise Mode, as usual.</span></span> <span data-ttu-id="90f22-150">문서 모드 사용에 대한 자세한 내용은  [문서 모드 및 엔터프라이즈 모드 사이트 목록을 사용하여 웹 호환성 문제 해결](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/fix-compat-issues-with-doc-modes-and-enterprise-mode-site-list)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="90f22-150">For more specific information about using document modes, see [Fix web compatibility issues using document modes and the Enterprise Mode site list](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/fix-compat-issues-with-doc-modes-and-enterprise-mode-site-list).</span></span>

5. <span data-ttu-id="90f22-151">**리디렉션 허용** 확인란은 서버 쪽 리디렉션 처리에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-151">The **Allow Redirect** checkbox applies to the treatment of server-side redirects.</span></span> <span data-ttu-id="90f22-152">이 확인란을 선택하면 열기 태그에 지정된 브라우저에서 서버 쪽 리디렉션이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-152">If you check this box, server-side redirects will open in the browser specified by the open-in tag.</span></span> <span data-ttu-id="90f22-153">자세한 내용은  [여기](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance#updated-schema-attributes)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="90f22-153">For more information, see [here](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance#updated-schema-attributes).</span></span>
6. <span data-ttu-id="90f22-154">웹 사이트에 대한 설명을  **설명** 상자에 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-154">Type any comments about the website into the **Comment** box.</span></span> <span data-ttu-id="90f22-155">관리자는 이 도구에 있는 동안에만 설명을 볼 수 있으며 이러한 설명은 사이트 목록 xml에 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-155">Administrators can only see comments while they’re in this tool and these comments are retained in the site list xml.</span></span>
7. <span data-ttu-id="90f22-156">사이트 목록에 사이트를 추가하려면  **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-156">Click **Add** to add the site to your site list.</span></span>

### <span data-ttu-id="90f22-157">XML로 사이트 목록 내보내기</span><span class="sxs-lookup"><span data-stu-id="90f22-157">Export site list to XML</span></span>

<span data-ttu-id="90f22-158">엔터프라이즈 사이트 목록 관리자에서 사이트 목록을 만든 후 엔터프라이즈 모드(.EMIE) 또는 XML 파일로 콘텐츠를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-158">After you create your site list in the Enterprise Site List Manager, you can export the contents to an Enterprise Mode (.EMIE) or XML file.</span></span> 

> [!NOTE]
> <span data-ttu-id="90f22-159">이 파일에는 호환성 모드 선택 항목을 비롯하여 모든 URL이 포함되므로 안전한 곳에 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-159">This file includes all of your URLs, including your compatibility mode selections and should be stored somewhere safe.</span></span>

<span data-ttu-id="90f22-160">사이트 목록을 내보내려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-160">To export the site list, follow these steps:</span></span>

1. <span data-ttu-id="90f22-161">엔터프라이즈 사이트 목록 관리자에서 **XML로 내보내기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-161">In the Enterprise Site List Manager, click **Export to XML**.</span></span>
2. <span data-ttu-id="90f22-162">**버전 번호**와 **파일 이름**을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-162">Enter a **Version number** and a **File name**.</span></span>
3. <span data-ttu-id="90f22-163">**내보내기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-163">Click **Export**.</span></span>

<span data-ttu-id="90f22-164">파일을 로컬로 저장하거나 네트워크 공유에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-164">You can save the file locally or to a network share.</span></span> <span data-ttu-id="90f22-165">그러나 반드시 레지스트리 키에 지정된 위치에 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-165">However, you must make sure you deploy it to the location specified in your registry key.</span></span> <span data-ttu-id="90f22-166">자세한 내용은  [Internet Explorer 모드 켜기 및 사이트 목록 사용](https://docs.microsoft.com/deployedge/edge-ie-mode-policies)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="90f22-166">For more information, see [Turn on Internet Explorer mode and use a site list](https://docs.microsoft.com/deployedge/edge-ie-mode-policies).</span></span>

### <span data-ttu-id="90f22-167">사이트 목록으로 여러 사이트 가져오기</span><span class="sxs-lookup"><span data-stu-id="90f22-167">Import multiple sites to your site list</span></span>

<span data-ttu-id="90f22-168">.xml 파일을 만든 후 **XML에서 가져오기**를 사용하여 편집기에 사이트를 대량으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-168">After you create your .xml file, you can bulk add sites to the editor using **Import from XML**.</span></span>

<span data-ttu-id="90f22-169">편집기에서 모든 내용을 바꾸려면 생략 부호(...)를 클릭한 다음 **목록 지우기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-169">If you want to replace all the contents in the editor, click  the ellipsis (…) and then choose **Clear list**.</span></span> <span data-ttu-id="90f22-170">편집기를 지운 후 다음 단계에 따라 사이트를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-170">After you clear the editor, use the following steps to import the site.</span></span>

1. <span data-ttu-id="90f22-171">엔터프라이즈 사이트 목록 관리자에서 **XML에서 가져오기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-171">In the Enterprise Site List Manager, click **Import from XML**.</span></span> 
2. <span data-ttu-id="90f22-172">**파일 선택**을 클릭하여 사이트 목록을 선택하고 포함된 사이트를 도구에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-172">Click **Choose file** to select your site list to add the included sites to the tool.</span></span> <span data-ttu-id="90f22-173">추가할 사이트 목록을 선택하고  **열기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-173">Pick the site list you want to add and then click **Open**.</span></span> <span data-ttu-id="90f22-174">지원되는 가져오기 형식은 엔터프라이즈 모드 사이트 목록에 대한 v.2 스키마를 포함하는 .xml, .emie 또는 .txt입니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-174">Supported formats for Import are .xml, .emie or .txt containing the v.2 schema for Enterprise Mode Site List.</span></span> <span data-ttu-id="90f22-175">[엔터프라이즈 모드 스키마 v.2 지침](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="90f22-175">See [Enterprise Mode schema v.2 guidance](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance).</span></span>
3. <span data-ttu-id="90f22-176"> *\*로드** 를 클릭하여 사이트를 파일에서 편집기로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-176">Click **Load** to add the sites from the file tp the editor.</span></span>

<span data-ttu-id="90f22-177">파일을 로컬로 저장하거나 네트워크 공유에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-177">You can save the file locally or to a network share.</span></span> <span data-ttu-id="90f22-178">그러나 반드시 레지스트리 키에 지정된 위치에 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-178">However, you must make sure you deploy it to the location specified in your registry key.</span></span> <span data-ttu-id="90f22-179">자세한 내용은  [Internet Explorer 모드 켜기 및 사이트 목록 사용](https://docs.microsoft.com/deployedge/edge-ie-mode-policies)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="90f22-179">For more information, see [Turn on Internet Explorer mode and use a site list](https://docs.microsoft.com/deployedge/edge-ie-mode-policies).</span></span>

### <span data-ttu-id="90f22-180">사이트 목록에서 사이트 편집</span><span class="sxs-lookup"><span data-stu-id="90f22-180">Edit sites in your site list</span></span>

 <span data-ttu-id="90f22-181">엔터프라이즈 사이트 목록 관리자에서 기존 사이트 항목의 특성을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-181">You can edit attributes of existing site entries in the Enterprise Site List Manager.</span></span> <span data-ttu-id="90f22-182">또한 연결된 설명을 추가하거나, 제거하거나, 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-182">You can also add, remove, or delete associated comments.</span></span>

1. <span data-ttu-id="90f22-183">엔터프라이즈 사이트 목록 관리자에서 생략 부호(...)를 클릭하고 편집할 URL의 **사이트 편집**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-183">In the Enterprise Site List Manager, click the ellipsis (…) and choose **Edit site** for the URL you want to edit.</span></span>
2. <span data-ttu-id="90f22-184">URL을 제외한 사이트 항목의 특성을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-184">You can edit any attribute of the site entry except the URL.</span></span> <span data-ttu-id="90f22-185">편집을 마친 후 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-185">Click **Save** after you finish editing.</span></span>

   > [!NOTE]
   > <span data-ttu-id="90f22-186">사이트 항목을 삭제하려면 1단계에서 **사이트 삭제**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-186">If you want to delete a site entry, choose **Delete site** in step 1.</span></span>

3. <span data-ttu-id="90f22-187">**XML로 내보내기**를 클릭하고 업데이트된 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-187">Click **Export to XML**, and save the updated file.</span></span>

<span data-ttu-id="90f22-188">파일을 로컬로 저장하거나 네트워크 공유에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-188">You can save the file locally or to a network share.</span></span> <span data-ttu-id="90f22-189">그러나 반드시 레지스트리 키에 지정된 위치에 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-189">However, you must make sure you deploy it to the location specified in your registry key.</span></span> <span data-ttu-id="90f22-190">자세한 내용은  [Internet Explorer 모드 켜기 및 사이트 목록 사용](https://docs.microsoft.com/deployedge/edge-ie-mode-policies)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="90f22-190">For more information, see [Turn on Internet Explorer mode and use a site list](https://docs.microsoft.com/deployedge/edge-ie-mode-policies).</span></span>

### <span data-ttu-id="90f22-191">XML 형식으로 사이트 목록 미리 보기</span><span class="sxs-lookup"><span data-stu-id="90f22-191">Preview your site list in XML format</span></span>

<span data-ttu-id="90f22-192">사이트 목록 위치를 내보내고 저장하기 전에 편집기에서 XML 형식으로 사이트를 미리 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-192">You can preview the sites in the editor in XML format before you export and save to your site list location.</span></span> <span data-ttu-id="90f22-193">**XML 미리 보기**를 클릭하여 새 탭에서 파일을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-193">Click **XML preview** to open the file in a new tab.</span></span>

### <span data-ttu-id="90f22-194">엔터프라이즈 사이트 목록 관리자에서 검색</span><span class="sxs-lookup"><span data-stu-id="90f22-194">Search in the Enterprise Site List Manager</span></span>

<span data-ttu-id="90f22-195">특정 사이트가 사이트 목록에 이미 나타나는지 검색하여 다시 추가하지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-195">You can search to see if a specific site already appears in your site list so you don’t try to add it again.</span></span>

<span data-ttu-id="90f22-196">검색을 하려면 URL의 일부를 편집기 오른쪽 위에 있는  **URL로 사이트 필터링** 검색 상자에 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="90f22-196">To search, type part of the URL into the **Filter sites by URL** search box on the top right-hand corner of the editor.</span></span>

## <span data-ttu-id="90f22-197">참고 항목</span><span class="sxs-lookup"><span data-stu-id="90f22-197">See also</span></span>

- [<span data-ttu-id="90f22-198">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="90f22-198">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="90f22-199">IE 모드 정보</span><span class="sxs-lookup"><span data-stu-id="90f22-199">About IE mode</span></span>](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [<span data-ttu-id="90f22-200">추가 엔터프라이즈 모드 정보</span><span class="sxs-lookup"><span data-stu-id="90f22-200">Additional Enterprise Mode information</span></span>](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [<span data-ttu-id="90f22-201">추가 엔터프라이즈 사이트 검색 정보</span><span class="sxs-lookup"><span data-stu-id="90f22-201">Additional Enterprise Site Discovery information</span></span>](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/collect-data-using-enterprise-site-discovery)
