---
title: Microsoft Edge의 PDF 읽기 프로그램
ms.author: adigan
author: dan-wesley
manager: balajek
ms.date: 08/05/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edg의 PDF 읽기 프로그램에 대해 자세히 알아봅니다.
ms.openlocfilehash: c189bc08d4af0c9d5c4d9c573e0b5b7ef32a7fb3
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980753"
---
# <span data-ttu-id="b58d4-103">Microsoft Edge의 PDF 읽기 프로그램</span><span class="sxs-lookup"><span data-stu-id="b58d4-103">PDF reader in Microsoft Edge</span></span>

<span data-ttu-id="b58d4-104">PDF 파일은 일상 생활의 상당 부분을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-104">PDF files make up a substantial part of our day-to-day lives.</span></span> <span data-ttu-id="b58d4-105">계약, 뉴스레터, 양식, 리서치 문서, 이력서 등의 형태로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-105">They come in the form of contracts and agreements, newsletters, forms, research articles, resumes, and so on.</span></span> <span data-ttu-id="b58d4-106">이러한 파일은 엔터프라이즈에서 채택할 수 있는 신뢰성과 안전성을 갖춘 강력한 PDF 읽기 프로그램에 대한 필요성을 강조합니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-106">These files highlight the need for a reliable, secure, and powerful PDF reader that can be adopted by Enterprises.</span></span>

<span data-ttu-id="b58d4-107">Microsoft Edge에는 로컬 PDF 파일, 온라인 PDF 파일 또는 웹 페이지에 포함된 PDF 파일을 열 수 있는 기본 제공 PDF 읽기 프로그램이 함께 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-107">Microsoft Edge comes with a built-in PDF reader that lets you open your local pdf files, online pdf files, or pdf files embedded in web pages.</span></span> <span data-ttu-id="b58d4-108">잉크와 강조 표시를 사용하여 이 파일에 주석을 달 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-108">You can annotate these files with ink and highlighting.</span></span> <span data-ttu-id="b58d4-109">해당 PDF 읽기 프로그램에서는 웹 페이지 및 PDF 문서 요구 사항을 충족하는 단일 응용 프로그램을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-109">This PDF reader gives users a single application to meet web page and PDF document needs.</span></span> <span data-ttu-id="b58d4-110">Microsoft Edge PDF 읽기 프로그램은 Windows 및 macOS 데스크톱 플랫폼에서 작동하는 안전하고 신뢰할 수 있는 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-110">The Microsoft Edge PDF reader is a secure and reliable application that works across the Windows and macOS desktop platforms.</span></span>

> [!NOTE]
> <span data-ttu-id="b58d4-111">이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-111">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="b58d4-112">필수 구성 요소, 지원 및 제약 조건</span><span class="sxs-lookup"><span data-stu-id="b58d4-112">Prerequisites, support, and constraints</span></span>

<span data-ttu-id="b58d4-113">다음 표에서는 각 PDF 읽기 프로그램 기능을 지원하는 Microsoft Edge의 채널과 버전을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-113">The following table shows which channels and versions of Microsoft Edge support each PDF reader feature.</span></span>

| <span data-ttu-id="b58d4-114">기능</span><span class="sxs-lookup"><span data-stu-id="b58d4-114">Feature</span></span> | <span data-ttu-id="b58d4-115">안정적인 채널 버전</span><span class="sxs-lookup"><span data-stu-id="b58d4-115">Stable channel version</span></span> |
|---------|------------------------|
| <span data-ttu-id="b58d4-116">로컬, 온라인 및 포함된 PDF 파일 보기 및 인쇄</span><span class="sxs-lookup"><span data-stu-id="b58d4-116">View and print local, online, and embedded PDF files</span></span> | <span data-ttu-id="b58d4-117">79.0.309.71</span><span class="sxs-lookup"><span data-stu-id="b58d4-117">79.0.309.71</span></span>                |
| <span data-ttu-id="b58d4-118">기본 양식 채우기</span><span class="sxs-lookup"><span data-stu-id="b58d4-118">Basic form filling</span></span><br><span data-ttu-id="b58d4-119">(JavaScript 폼이 지원되지 않음)</span><span class="sxs-lookup"><span data-stu-id="b58d4-119">(JavaScript forms aren't supported)</span></span> | <span data-ttu-id="b58d4-120">79.0.309.71</span><span class="sxs-lookup"><span data-stu-id="b58d4-120">79.0.309.71</span></span>           |
| <span data-ttu-id="b58d4-121">수동 입력</span><span class="sxs-lookup"><span data-stu-id="b58d4-121">Inking</span></span>  | <span data-ttu-id="b58d4-122">80.0.361.48</span><span class="sxs-lookup"><span data-stu-id="b58d4-122">80.0.361.48</span></span>            |
| <span data-ttu-id="b58d4-123">잉크 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="b58d4-123">Ink customization</span></span> | <span data-ttu-id="b58d4-124">83.0.478.54</span><span class="sxs-lookup"><span data-stu-id="b58d4-124">83.0.478.54</span></span>  |
| <span data-ttu-id="b58d4-125">Highlight</span><span class="sxs-lookup"><span data-stu-id="b58d4-125">Highlight</span></span>  | <span data-ttu-id="b58d4-126">81.0.416.53</span><span class="sxs-lookup"><span data-stu-id="b58d4-126">81.0.416.53</span></span>         |
| <span data-ttu-id="b58d4-127">소리내어 읽기</span><span class="sxs-lookup"><span data-stu-id="b58d4-127">Read Aloud</span></span> | <span data-ttu-id="b58d4-128">[Microsoft Edge 참가자](https://www.microsoftedgeinsider.com/) 채널에서 현재 승격 중</span><span class="sxs-lookup"><span data-stu-id="b58d4-128">Currently being promoted in [Microsoft Edge Insider](https://www.microsoftedgeinsider.com/) channels</span></span> |
| <span data-ttu-id="b58d4-129">MIP으로 보호된 파일 보기</span><span class="sxs-lookup"><span data-stu-id="b58d4-129">View MIP protected files</span></span> | <span data-ttu-id="b58d4-130">80.0.361.48의 Windows 지원</span><span class="sxs-lookup"><span data-stu-id="b58d4-130">Windows support in 80.0.361.48</span></span><br><span data-ttu-id="b58d4-131">81.0.416.53의 Mac 지원</span><span class="sxs-lookup"><span data-stu-id="b58d4-131">Mac support in 81.0.416.53</span></span> |
|  <span data-ttu-id="b58d4-132">IRM으로 보호된 파일 보기</span><span class="sxs-lookup"><span data-stu-id="b58d4-132">View IRM protected files</span></span>  | <span data-ttu-id="b58d4-133">83.0.478.37</span><span class="sxs-lookup"><span data-stu-id="b58d4-133">83.0.478.37</span></span>            |

### <span data-ttu-id="b58d4-134">제약 조건</span><span class="sxs-lookup"><span data-stu-id="b58d4-134">Constraints</span></span>

<span data-ttu-id="b58d4-135">현재 PDF 읽기 프로그램에 대해 다음 제한 사항을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-135">Note the following constraints for the current PDF reader:</span></span>

-  <span data-ttu-id="b58d4-136">XFA(XML Forms Architecture)는 Microsoft Edge에서 지원되지 않는 레거시 형태의 양식입니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-136">XML Forms Architecture (XFA), is a legacy format of forms that isn't  supported in Microsoft Edge.</span></span>
-  <span data-ttu-id="b58d4-137">현재 지원되지 않는 접근성 시나리오와 관련된 문서는 [Microsoft 접근성 규칙 보고서](https://cloudblogs.microsoft.com/industry-blog/government/2018/09/11/accessibility-conformance-reports/) 블로그를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b58d4-137">Documentation related to Accessibility scenarios that currently aren't supported can be found on the [Microsoft Accessibility Conformance Reports](https://cloudblogs.microsoft.com/industry-blog/government/2018/09/11/accessibility-conformance-reports/) blog.</span></span>

## <span data-ttu-id="b58d4-138">기능</span><span class="sxs-lookup"><span data-stu-id="b58d4-138">Features</span></span>

### <span data-ttu-id="b58d4-139">수동 입력</span><span class="sxs-lookup"><span data-stu-id="b58d4-139">Inking</span></span>

<span data-ttu-id="b58d4-140">PDF 파일에서 수동 입력 기능을 사용하여 간편하게 기록하여 손쉽게 참조하거나, 서명하거나, PDF 양식을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-140">Inking on PDF files comes in handy to take quick notes for easy reference, sign, or fill out PDF forms.</span></span> <span data-ttu-id="b58d4-141">이제 Microsoft Edge에서 이 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-141">This capability is now available in Microsoft Edge.</span></span> <span data-ttu-id="b58d4-142">필요한 경우 PDF 파일의 수동 입력 외에, 색상 및 스트로크 너비를 사용하여 PDF 파일의 여러 부분을 돋보이게 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-142">In addition to inking PDF files as needed, you can use color and stroke width to bring attention to different parts of the PDF file.</span></span> <span data-ttu-id="b58d4-143">다음 스크린샷은 PDF 페이지에 수동 입력을 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-143">The next screenshot shows how a user can add inking to a pdf page.</span></span>

<!-- SCREENSHOT -->
![PDF 페이지에 수동 입력 추가](media/microsoft-edge-pdf/pdf-reader-inking.png)

### <span data-ttu-id="b58d4-145">Highlight</span><span class="sxs-lookup"><span data-stu-id="b58d4-145">Highlight</span></span>

<span data-ttu-id="b58d4-146">Microsoft Edge의 PDF 읽기 프로그램에서 하이라이트를 추가하고 편집하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-146">PDF reader in Microsoft Edge comes with support for adding and editing highlights.</span></span> <span data-ttu-id="b58d4-147">강조 표시를 만들려면 텍스트를 선택하여 텍스트를 마우스 오른쪽 단추로 클릭한 다음, 메뉴에서 하이라이트를 선택하고 원하는 색을 선택하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-147">To create a highlight, the user simply needs to select the text, right-click on it, select highlights in the menu and choose the desired color.</span></span> <span data-ttu-id="b58d4-148">다음 스크린샷은 사용 가능한 강조 표시 옵션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-148">The next screenshot shows the highlight options that are available.</span></span>

![PDF 읽기 프로그램의 강조 표시 옵션 사용](media/microsoft-edge-pdf/pdf-reader-highlight.png)

### <span data-ttu-id="b58d4-150">소리내어 읽기</span><span class="sxs-lookup"><span data-stu-id="b58d4-150">Read Aloud</span></span>

<span data-ttu-id="b58d4-151">PDF용 소리내어 읽기를 사용하면 사용자에게 중요한 다른 작업을 수행하면서 PDF 콘텐츠를 들을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-151">Read Aloud for PDF adds the convenience of listening to PDF content while carrying out other tasks that may be important to users.</span></span> <span data-ttu-id="b58d4-152">또한 청각 학습자가 콘텐츠에 집중하는 데 도움을 주므로 훨씬 쉽게 배울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-152">It also helps auditory learners focus on the content, which makes learning much easier.</span></span> <span data-ttu-id="b58d4-153">다음 스크린샷은 소리내어 읽기 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-153">The next screenshot shows a Read Aloud example.</span></span> <span data-ttu-id="b58d4-154">강조 표시된 부분은 현재 읽고 있는 텍스트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-154">The highlighting shows the text that is currently being read.</span></span>

![PDF 읽기 프로그램의 강조 표시 옵션 사용](media/microsoft-edge-pdf/pdf-reader-read-aloud-example.png)

### <span data-ttu-id="b58d4-156">보호된 PDF</span><span class="sxs-lookup"><span data-stu-id="b58d4-156">Protected PDFs</span></span>

<span data-ttu-id="b58d4-157">[MIP(Microsoft Information Protection)](https://docs.microsoft.com/microsoft-365/compliance/protect-information?view=o365-worldwide)을 사용하면 조직의 규정 준수 정책을 지키면서 다른 사용자와 안전하게 공동 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-157">[Microsoft Information Protection (MIP)](https://docs.microsoft.com/microsoft-365/compliance/protect-information?view=o365-worldwide) enables users to collaborate with others securely, while adhering to your organization's compliance policies.</span></span> <span data-ttu-id="b58d4-158">파일이 보호된 경우, 사용자가 해당 파일을 사용할 수 있는 작업은 해당 사용자에게 할당된 사용 권한에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-158">After a file is protected, the actions users can take on it are determined by the permissions assigned to them.</span></span>

<span data-ttu-id="b58d4-159">이러한 파일은 다른 소프트웨어를 다운로드하거나 추가 기능을 설치할 필요 없이 브라우저에서 바로 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-159">These files can be opened directly in the browser, without the need to download any other software, or install any add-in.</span></span> <span data-ttu-id="b58d4-160">이렇게 하면 MIP에서 제공하는 보안이 브라우저에 바로 통합되어 원활한 워크플로를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-160">This integrates the security provided by MIP directly into the browser, providing a seamless workflow.</span></span>

<!-- SCREENSHOT -->
![보호된 PDF 문서.](media/microsoft-edge-pdf/pdf-reader-protected-pdf2.png)

<span data-ttu-id="b58d4-162">MIP으로 보호된 파일 외에도, [IRM(Information Rights Management)](https://docs.microsoft.com/microsoft-365/compliance/set-up-irm-in-sp-admin-center?view=o365-worldwide)으로 보호된 SharePoint 라이브러리의 PDF 파일을 브라우저에서 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-162">In addition to MIP protected files, PDF files in [Information Rights Management (IRM)](https://docs.microsoft.com/microsoft-365/compliance/set-up-irm-in-sp-admin-center?view=o365-worldwide) protected SharePoint libraries can also be opened natively in the browser.</span></span>

<span data-ttu-id="b58d4-163">Microsoft Edge를 사용하여, 로컬이나 클라우드에 저장된 MIP으로 보호된 파일을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-163">With Microsoft Edge, users can view MIP protected files saved locally, or in the cloud.</span></span> <span data-ttu-id="b58d4-164">로컬에 저장된 경우 브라우저에서 직접 파일을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-164">If saved locally, the file can be opened directly in the browser.</span></span> <span data-ttu-id="b58d4-165">클라우드 서비스에서 SharePoint로 파일을 연 경우에는 "브라우저에서 열기" 옵션을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-165">If the file is opened from a cloud service as SharePoint, the user may need to use the "Open in browser" option.</span></span>

<span data-ttu-id="b58d4-166">Microsoft Edge에 로그인하는 데 사용된 프로필에 적어도 해당 파일에 대한 보기 권한이 있는 경우, 파일이 Microsoft Edge에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-166">If the profile that the user is logged into Microsoft Edge with has at least view permissions to the file, the file will open in Microsoft Edge.</span></span>

<!-- SCREENSHOT -->
![MIP으로 보호되는 SharePoint PDF 페이지를 저장하라는 메시지가 표시됨](media/microsoft-edge-pdf/pdf-reader-sharepoint-irm.png)

## <span data-ttu-id="b58d4-168">접근성</span><span class="sxs-lookup"><span data-stu-id="b58d4-168">Accessibility</span></span>

<span data-ttu-id="b58d4-169">PDF 읽기 프로그램은 Windows 및 macOS 장치에서 키보드 접근성, 고대비 모드 및 화면 읽기 프로그램 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-169">The PDF reader comes with support for Keyboard accessibility, High contrast mode, and screen reader support across Windows and macOS devices.</span></span>

### <span data-ttu-id="b58d4-170">키보드 접근성</span><span class="sxs-lookup"><span data-stu-id="b58d4-170">Keyboard Accessibility</span></span>

<span data-ttu-id="b58d4-171">사용자가 키보드를 사용하여 양식 필드 및 하이라이트와 같이, 사용자가 상호 작용할 수 있는 문서의 여러 부분을 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-171">Users can use navigate to different parts of the document that a user can interact with, such as form fields and highlights, using the keyboard.</span></span>

<!-- SCREENSHOT -->

### <span data-ttu-id="b58d4-172">고대비 모드</span><span class="sxs-lookup"><span data-stu-id="b58d4-172">High contrast mode</span></span>

<span data-ttu-id="b58d4-173">PDF 읽기 프로그램은 운영 체제 수준에서 정의된 설정을 사용하여 PDF 콘텐츠를 고대비 모드로 렌더링합니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-173">PDF reader will use the settings defined at the operating system level to render PDF content in high contrast mode.</span></span>

<!-- SCREENSHOT -->
<!--![High contrast mode for pdf file](media/microsoft-edge-pdf/pdf-reader-high-contrast.png)-->

### <span data-ttu-id="b58d4-174">화면 읽기 프로그램 지원</span><span class="sxs-lookup"><span data-stu-id="b58d4-174">Screen reader support</span></span>

<span data-ttu-id="b58d4-175">Windows 및 Mac 컴퓨터에서 화면 읽기 프로그램을 사용하여 PDF 파일을 탐색하고 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-175">Users can navigate through and read PDF files using screen readers on Windows and Mac computers.</span></span> <!--The next screenshot shows the toolbar that users can use for audio settings when they're using the Read Aloud option in PDF reader. -->

<!-- SCREENSHOT -->
<!--
![Screen reader toolbar](media/microsoft-edge-pdf/pdf-reader-read-aloud.png) -->

## <span data-ttu-id="b58d4-176">보안 및 안정성</span><span class="sxs-lookup"><span data-stu-id="b58d4-176">Security and reliability</span></span>

<span data-ttu-id="b58d4-177">보안은 모든 조직에서 가장 중요한 개념에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-177">Security is among the most important tenets for any organization.</span></span> <span data-ttu-id="b58d4-178">PDF 읽기 프로그램 보안은 Microsoft Edge 보안 설계의 필수 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-178">PDF reader security is an integral part of the Microsoft Edge security design.</span></span> <span data-ttu-id="b58d4-179">PDF 읽기 프로그램에서 가장 중요한 보안 기능 두 가지는 프로세스 격리 및 Application Guard(Microsoft Defender Application Guard)입니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-179">Two of the most important security features From a PDF reader perspective, two important security features are process isolation and Microsoft Defender Application Guard (Application Guard).</span></span>

- <span data-ttu-id="b58d4-180">프로세스 격리.</span><span class="sxs-lookup"><span data-stu-id="b58d4-180">Process isolation.</span></span> <span data-ttu-id="b58d4-181">여러 웹 사이트에서 열린 PDF는 완전히 격리된 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-181">PDFs opened from different web sites are completely process isolated.</span></span> <span data-ttu-id="b58d4-182">브라우저는 다른 원본에서 열린 PDF 파일이나 웹 사이트와 통신할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-182">The browser doesn't have to communicate with any websites, or PDF files opened from another source.</span></span> <span data-ttu-id="b58d4-183">PDF 검색 기능은 손상된 PDF를 공격 표면으로 사용하려고 계획하는 공격으로부터 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-183">PDF browsing is secure from any attacks that plan to use compromised PDFs as an attack surface.</span></span>

- <span data-ttu-id="b58d4-184">Application Guard</span><span class="sxs-lookup"><span data-stu-id="b58d4-184">Application Guard.</span></span> <span data-ttu-id="b58d4-185">Application Guard를 통해 관리자는 조직에서 신뢰하는 사이트 목록을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-185">With Application Guard, admins can set a list of sites that are trusted by their organization.</span></span> <span data-ttu-id="b58d4-186">사용자가 다른 사이트를 여는 경우, 자체 컨테이너에서 실행되는 별도의 Application Guard 보호 창에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-186">If users open any other sites, they are opened in a separate Application Guard window that runs in its own container.</span></span> <span data-ttu-id="b58d4-187">컨테이너는 회사 네트워크와 사용자 컴퓨터에 있는 모든 데이터가 손상되지 않도록 보호하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-187">The container helps protect the corporate network and any data on user's computer from being compromised.</span></span><br><br>
<span data-ttu-id="b58d4-188">이 보호 기능은 보고 있는 모든 온라인 PDF 파일에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-188">This protection also applies to any online PDF files that are viewed.</span></span> <span data-ttu-id="b58d4-189">또한 Application Guard 창에서 다운로드한 모든 PDF 파일이 저장되고, 필요한 경우 컨테이너에서 다시 열립니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-189">Further, any PDF files that are downloaded from an Application Guard window are stored, and when needed, re-opened in the container.</span></span> <span data-ttu-id="b58d4-190">이렇게 하면 파일이 다운로드될 때뿐만 아니라, 전체 수명 주기 동안 환경을 안전하게 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-190">This helps keeps your environment secure not just when the file is downloaded, but through its whole lifecycle.</span></span> <span data-ttu-id="b58d4-191">자세한 내용은 [Application Guard](https://docs.microsoft.com/DeployEdge/microsoft-edge-security-windows-defender-application-guard)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b58d4-191">For more information, see [Application Guard](https://docs.microsoft.com/DeployEdge/microsoft-edge-security-windows-defender-application-guard).</span></span>

### <span data-ttu-id="b58d4-192">안정성</span><span class="sxs-lookup"><span data-stu-id="b58d4-192">Reliability</span></span>

<span data-ttu-id="b58d4-193">Microsoft Edge는 Chromium 기반이므로 Google Chrome에서 볼 때와 동일한 수준의 안정성을 기대할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-193">Because Microsoft Edge is Chromium-based, users can expect the same level of reliability that they're used to seeing in Google Chrome.</span></span>

## <span data-ttu-id="b58d4-194">PDF 읽기 프로그램 배포 및 업데이트</span><span class="sxs-lookup"><span data-stu-id="b58d4-194">Deploy and update PDF reader</span></span>

<span data-ttu-id="b58d4-195">PDF 읽기 프로그램이 배포되고 Microsoft Edge 브라우저의 나머지 부분으로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-195">The PDF reader gets deployed and updated with the rest of the Microsoft Edge browser.</span></span> <span data-ttu-id="b58d4-196">Microsoft Edge를 배포하는 방법에 대한 자세한 내용은 [수천 대의 장치에 Microsoft Edge 배포](microsoft-edge-video-deploy.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b58d4-196">To learn more about deploying Microsoft Edge, watch the [Deploy Microsoft Edge to hundreds or thousands of devices](microsoft-edge-video-deploy.md) video.</span></span> <span data-ttu-id="b58d4-197">[Microsoft Edge 설명서](https://docs.microsoft.com/DeployEdge/) 랜딩 페이지에서도 더 많은 배포 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-197">You can also find more deployment information on the [Microsoft Edge documentation](https://docs.microsoft.com/DeployEdge/) landing page.</span></span>

> [!TIP]
> <span data-ttu-id="b58d4-198">Microsoft Edge를 조직의 기본 PDF 읽기 프로그램으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-198">You can make Microsoft Edge the default PDF reader for your organization.</span></span> <span data-ttu-id="b58d4-199">이렇게 하려면 [다음 단계를 따르세요](https://docs.microsoft.com/deployedge/edge-default-browser).</span><span class="sxs-lookup"><span data-stu-id="b58d4-199">To do this, [follow these steps](https://docs.microsoft.com/deployedge/edge-default-browser).</span></span>

## <span data-ttu-id="b58d4-200">로드맵 및 피드백</span><span class="sxs-lookup"><span data-stu-id="b58d4-200">Roadmap and feedback</span></span>

<span data-ttu-id="b58d4-201">Microsoft Edge의 PDF 읽기 프로그램에 대한 로드맵은 [여기](https://techcommunity.microsoft.com/t5/articles/roadmap-for-pdf-reader-in-microsoft-edge/m-p/1467667)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-201">The roadmap for PDF Reader in Microsoft Edge is available [here](https://techcommunity.microsoft.com/t5/articles/roadmap-for-pdf-reader-in-microsoft-edge/m-p/1467667).</span></span>

<span data-ttu-id="b58d4-202">사용자가 중요하게 여기는 기능에 대한 피드백을 적극적으로 보고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b58d4-202">We're actively looking at feedback from you about the features you find important.</span></span> <span data-ttu-id="b58d4-203">[Microsoft Edge UserVoice](https://microsoftedge.uservoice.com/)를 사용하거나 [Microsoft Edge 참가자](https://techcommunity.microsoft.com/t5/microsoft-edge-insider/ct-p/MicrosoftEdgeInsider) 포럼에서 피드백을 보내 주세요.</span><span class="sxs-lookup"><span data-stu-id="b58d4-203">Feel free to send us feedback through [Microsoft Edge UserVoice](https://microsoftedge.uservoice.com/) and on [Microsoft Edge Insider](https://techcommunity.microsoft.com/t5/microsoft-edge-insider/ct-p/MicrosoftEdgeInsider) forum.</span></span>

## <span data-ttu-id="b58d4-204">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b58d4-204">See also</span></span>

- [<span data-ttu-id="b58d4-205">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="b58d4-205">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)