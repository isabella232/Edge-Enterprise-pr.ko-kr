---
title: Microsoft Edge의 ClickOnce 및 DirectInvoke
ms.author: collw
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge의 ClickOnce 및 DirectInvoke에 대해 알아봅니다.
ms.openlocfilehash: 3d124f141e9212ba5ab25d4b725d32add62077a3
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642054"
---
# <a name="understand-the-clickonce-and-directinvoke-features-in-microsoft-edge"></a><span data-ttu-id="11162-103">Microsoft Edge의 ClickOnce 및 DirectInvoke 기능 이해</span><span class="sxs-lookup"><span data-stu-id="11162-103">Understand the ClickOnce and DirectInvoke features in Microsoft Edge</span></span>

<span data-ttu-id="11162-104">ClickOnce 및 DirectInvoke는 파일 처리기를 사용하여 웹 사이트에서 파일을 다운로드할 수 있도록 IE 및 Microsoft Edge(버전 45 이하)에서 사용할 수 있는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="11162-104">ClickOnce and DirectInvoke are features available in IE and Microsoft Edge (version 45 and earlier) that support the use of a file handler to download files from a website.</span></span> <span data-ttu-id="11162-105">두 기능은 서로 다른 용도로 사용되지만 둘 다 웹 사이트에서 다운로드가 요청된 파일이 사용자 장치의 파일 처리기로 전달되도록 지정하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11162-105">Although they serve different purposes, both features let websites specify that a file requested for download is passed to a file handler on the user's device.</span></span> <span data-ttu-id="11162-106">ClickOnce 요청은 Windows의 기본 파일 처리기를 통해 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="11162-106">ClickOnce requests are handled by the native file handler in Windows.</span></span> <span data-ttu-id="11162-107">DirectInvoke 요청은 파일을 호스트하는 웹 사이트에서 지정한 등록된 파일 처리기를 통해 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="11162-107">DirectInvoke requests are handled by a registered file handler specified by the website hosting the file.</span></span>

<span data-ttu-id="11162-108">이러한 기능에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="11162-108">For more information about these features, see:</span></span>

- [<span data-ttu-id="11162-109">ClickOnce</span><span class="sxs-lookup"><span data-stu-id="11162-109">ClickOnce</span></span>](/visualstudio/deployment/clickonce-security-and-deployment?view=vs-2019)
- [<span data-ttu-id="11162-110">DirectInvoke</span><span class="sxs-lookup"><span data-stu-id="11162-110">DirectInvoke</span></span>]( https://technet.microsoft.com/learning/jj215788(v=vs.94).aspx)

> [!NOTE]
> <span data-ttu-id="11162-111">현재 Chromium은 ClickOnce 또는 DirectInvoke에 대한 기본 지원을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11162-111">Currently, Chromium doesn't provide native support for ClickOnce or DirectInvoke.</span></span>

## <a name="overview-prerequisites-and-process"></a><span data-ttu-id="11162-112">개요: 필수 구성 요소 및 프로세스</span><span class="sxs-lookup"><span data-stu-id="11162-112">Overview: prerequisites and process</span></span>

<span data-ttu-id="11162-113">ClickOnce 및 DirectInvoke가 설계대로 작동하고 파일 처리기가 성공적으로 요청되도록 하려면 ClickOnce 또는 DirectInvoke 지원으로 파일 처리기를 운영 체제에 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11162-113">For ClickOnce and DirectInvoke to work as designed and for the file handler to be successfully requested, the file handler must be registered to the operating system as supporting ClickOnce or DirectInvoke.</span></span> <span data-ttu-id="11162-114">이 등록은 일반적으로 원래 운영 체제가 설치되어 있거나, 설치된 새 프로그램이 업데이트를 위해 DirectInvoke 사용을 요청하는 경우에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="11162-114">This registration typically happens when the original operating system is installed or when a new program that's installed requests the ability to use DirectInvoke for updates.</span></span>

<span data-ttu-id="11162-115">웹 사이트에서 ClickOnce 또는 DirectInvoke가 필요한 다운로드 요청을 수신하는 경우 다음 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="11162-115">When a website receives a download request that requires ClickOnce or DirectInvoke, the following actions happen:</span></span>

- <span data-ttu-id="11162-116">웹 사이트에서 브라우저가 지정한 파일 처리기를 사용하도록 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="11162-116">The website requests that the browser use a specified file handler.</span></span>
- <span data-ttu-id="11162-117">브라우저는 운영 체제 레지스트리를 검사하여 파일 처리기가 요청된 파일 형식에 대해 등록되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="11162-117">The browser checks the operating system registry to see if the file handler is registered for the requested file type.</span></span>
- <span data-ttu-id="11162-118">파일 처리기가 등록되면 브라우저는 파일 처리기를 호출하고 URL을 인수로 파일 처리기에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="11162-118">If the file handler is registered, the browser calls the file handler and passes the URL as an argument to the file handler.</span></span>
- <span data-ttu-id="11162-119">파일 처리기는 URL을 처리하고 파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="11162-119">The file handler processes the URL and downloads the file.</span></span>

  > [!NOTE]
  > <span data-ttu-id="11162-120">URL은 파일의 원본뿐 아니라 파일에 액세스할 때 사용할 매개 변수를 결정하는 데도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="11162-120">The URL is used to determine the source of the file, as well as any parameters to use when accessing the file.</span></span>  <span data-ttu-id="11162-121">예: 엔드포인트, 매니페스트 또는 메타데이터.</span><span class="sxs-lookup"><span data-stu-id="11162-121">For example: endpoints, a manifest, or metadata.</span></span>

## <a name="use-cases"></a><span data-ttu-id="11162-122">사용 사례</span><span class="sxs-lookup"><span data-stu-id="11162-122">Use cases</span></span>

<span data-ttu-id="11162-123">대표적인 사용 사례는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="11162-123">The following use cases are representative.</span></span>

<span data-ttu-id="11162-124">ClickOnce를 사용하여 사용자 개입을 최소화하며 간편하게 장치에 소프트웨어를 배포 및 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11162-124">You can use ClickOnce to easily deploy and update software on devices with minimal user interaction.</span></span> <span data-ttu-id="11162-125">사용자가 웹 페이지에서 링크를 클릭하여 Windows 애플리케이션을 설치하고 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11162-125">Users can install and run a Windows application by clicking a link in a web page.</span></span> <span data-ttu-id="11162-126">올바르게 구성된 경우 사용자가 설치 프로그램에 대한 구성을 설정하지 않고 ClickOnce 응용 프로그램이 프로그램을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11162-126">If configured correctly, the ClickOnce application can install programs without having users set configurations for the installer.</span></span> <span data-ttu-id="11162-127">예를 들면 파일 위치, 설치할 옵션 등입니다.</span><span class="sxs-lookup"><span data-stu-id="11162-127">For example, file locations, what options to install, and so on.</span></span>

<span data-ttu-id="11162-128">DirectInvoke 사용 사례는 DirectInvoke를 요청하는 웹 사이트의 의도에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="11162-128">DirectInvoke use cases depend on the intent of the website requesting DirectInvoke.</span></span> <span data-ttu-id="11162-129">예를 들어 Microsoft Word의 공동 작업 파일 편집 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="11162-129">For example, the collaborative file-editing feature of Microsoft Word.</span></span> <span data-ttu-id="11162-130">링크를 클릭하여 동료와 함께 작업 중인 문서의 전체 복사본을 다운로드하는 대신 DirectInvoke를 사용하여 문서에서 변경된 부분을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11162-130">Instead of clicking a link and downloading the entire copy of a document you're working on with your colleagues, DirectInvoke lets you download the parts of the document that have been changed.</span></span> <span data-ttu-id="11162-131">이 전략을 사용하면 전송되는 데이터의 양이 줄어들고 문서를 여는 데 필요한 시간을 단축할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11162-131">This strategy reduces the amount of data transferred and can reduce the time needed to open the document.</span></span>  

## <a name="current-support-for-clickonce-and-directinvoke-in-microsoft-edge"></a><span data-ttu-id="11162-132">Microsoft Edge의 ClickOnce 및 DirectInvoke에 대한 현재 지원</span><span class="sxs-lookup"><span data-stu-id="11162-132">Current support for ClickOnce and DirectInvoke in Microsoft Edge</span></span>

<span data-ttu-id="11162-133">ClickOnce 및 DirectInvoke에 대한 지원:</span><span class="sxs-lookup"><span data-stu-id="11162-133">Support for ClickOnce and DirectInvoke:</span></span>

- <span data-ttu-id="11162-134">ClickOnce 및 DirectInvoke는 모든 Windows 사용자의 상자에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11162-134">ClickOnce and DirectInvoke are supported out of the box for all Windows users.</span></span>

  > [!NOTE]
  > <span data-ttu-id="11162-135">ClickOnce을 지원을 사용하지 않도록 설정하려면 *edge://flags/#edge-click-once*로 이동하여 드롭다운 목록에서 **사용하지 않음**을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="11162-135">Users that want to disable ClickOnce support can go to *edge://flags/#edge-click-once* and select **Disabled** from the dropdown list.</span></span> <span data-ttu-id="11162-136">그런 다음 브라우저를 **다시 시작**해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11162-136">You'll have to **Restart** the browser.</span></span>

- <span data-ttu-id="11162-137">Windows 이외의 플랫폼에서는 ClickOnce 및 DirectInvoke가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11162-137">ClickOnce and DirectInvoke aren't supported on any platforms other than Windows.</span></span>

## <a name="clickonce-and-directinvoke-file-handling-security"></a><span data-ttu-id="11162-138">ClickOnce 및 DirectInvoke 파일 처리 보안</span><span class="sxs-lookup"><span data-stu-id="11162-138">ClickOnce and DirectInvoke file handling security</span></span>

<span data-ttu-id="11162-139">ClickOnce 및 DirectInvoke는 Microsoft Defender SmartScreen의 URL 평판 검사 서비스로 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="11162-139">ClickOnce and DirectInvoke are protected by Microsoft Defender SmartScreen's URL reputation scanning service.</span></span>

<span data-ttu-id="11162-140">ClickOnce 또는 DirectInvoke 요청이 Microsoft Defender SmartScreen URL 평판 서비스에 의해 안전하지 않은 것으로 플래그가 지정된 경우 ClickOnce 또는 DirectInvoke를 사용하도록 설정된 사용자에게는 두 개의 팝업이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="11162-140">If a ClickOnce or a DirectInvoke request is flagged by the Microsoft Defender SmartScreen URL reputation service as unsafe, users with ClickOnce or DirectInvoke enabled will see two popups.</span></span>

<span data-ttu-id="11162-141">첫 번째 팝업은 사용자에게 파일을 열 것인지 묻는 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="11162-141">The first popup asks the user if they want to open the file.</span></span> <span data-ttu-id="11162-142">이 팝업은 파일이 안전하지 않은 것으로 플래그가 지정되었는지 여부와 관계없이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="11162-142">This popup is displayed regardless of whether the file was flagged as safe or unsafe.</span></span> <span data-ttu-id="11162-143">사용자는 **이 파일을 안전하지 않은 것으로 보고**하거나, 요청을 **취소**하거나, **열기**를 클릭하여 계속 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11162-143">The user can **Report the file as unsafe**, **Cancel** the request, or click **Open** to continue.</span></span>

   ![파일 열기 프롬프트](./media/edge-learn-more-co-di/edge-clickonce-modal-1.png)

<span data-ttu-id="11162-145">사용자가 안전하지 않은 것으로 플래그가 지정된 파일을 열려고 하는 경우 두 번째 팝업이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="11162-145">If the user tries to open the file, and the file was flagged as unsafe, a second popup is displayed.</span></span>  <span data-ttu-id="11162-146">이 팝업은 파일이 안전하지 않은 것으로 플래그가 지정되었음을 사용자에게 경고하고 파일을 다운로드할지 묻는 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="11162-146">This popup warns the user that the file was flagged as unsafe, and asks them if they're sure they want to download the file.</span></span>

<span data-ttu-id="11162-147">두 번째 팝업은 다음과 같은 경우에만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="11162-147">The second popup only shows up if:</span></span>

- <span data-ttu-id="11162-148">파일이 ClickOnce 또는 DirectInvoke 파일</span><span class="sxs-lookup"><span data-stu-id="11162-148">the file is a ClickOnce or DirectInvoke file</span></span>
- <span data-ttu-id="11162-149">ClickOnce 또는 DirectInvoke를 사용하도록 설정됨</span><span class="sxs-lookup"><span data-stu-id="11162-149">ClickOnce or DirectInvoke are enabled</span></span>
- <span data-ttu-id="11162-150">파일이 안전하지 않은 것으로 플래그가 지정됨</span><span class="sxs-lookup"><span data-stu-id="11162-150">the file is flagged as unsafe</span></span>

 ![안전하지 않은 파일 열기 프롬프트](./media/edge-learn-more-co-di/edge-clickonce-modal-2.png)

> [!NOTE]
> <span data-ttu-id="11162-152">ClickOnce 또는 DirectInvoke가 사용하지 않도록 설정된 경우 요청된 파일은 일반 다운로드로 취급되며 안전하지 않은 것으로 플래그가 지정된 경우 안전하지 않은 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="11162-152">If ClickOnce or DirectInvoke are disabled, requested files are treated as regular downloads and if flagged as unsafe, will be marked as unsafe.</span></span> <span data-ttu-id="11162-153">이는 다른 안전하지 않은 다운로드를 처리하는 방식과 일관됩니다.</span><span class="sxs-lookup"><span data-stu-id="11162-153">This is consistent with the treatment of other unsafe downloads.</span></span>

## <a name="clickonce-and-directinvoke-policies"></a><span data-ttu-id="11162-154">ClickOnce 및 DirectInvoke 정책</span><span class="sxs-lookup"><span data-stu-id="11162-154">ClickOnce and DirectInvoke policies</span></span>

<span data-ttu-id="11162-155">기업 사용자용 ClickOnce 및 DirectInvoke를 사용하거나 사용하지 않도록 설정하는 데 사용할 수 있는 그룹 정책이 2개 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11162-155">There are two group policies that you can use to enable or disable ClickOnce and DirectInvoke for enterprise users.</span></span> <span data-ttu-id="11162-156">이러한 정책은 [ClickOnceEnabled](./microsoft-edge-policies.md#clickonceenabled) 및 [DirectInvokeEnabled](./microsoft-edge-policies.md#directinvokeenabled)입니다.</span><span class="sxs-lookup"><span data-stu-id="11162-156">These two policies are [ClickOnceEnabled](./microsoft-edge-policies.md#clickonceenabled) and [DirectInvokeEnabled](./microsoft-edge-policies.md#directinvokeenabled).</span></span> <span data-ttu-id="11162-157">이 두 정책은 그룹 정책 편집기에서 "ClickOnce 프로토콜을 사용하여 파일을 열 수 있도록 허용" 및 "DirectInvoke 프로토콜을 사용하여 파일을 열 수 있도록 허용"으로 각각 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11162-157">These two policies are labeled in the Group Policy Editor as "Allow users to open files using the ClickOnce protocol" and "Allow users to open files using the DirectInvoke protocol" respectively.</span></span>

## <a name="clickonce-and-directinvoke-behavior"></a><span data-ttu-id="11162-158">ClickOnce 및 DirectInvoke 동작</span><span class="sxs-lookup"><span data-stu-id="11162-158">ClickOnce and DirectInvoke behavior</span></span>

<span data-ttu-id="11162-159">다음 예제에서는 ClickOnce 및 DirectInvoke가 사용 또는 사용하지 않도록 설정된 경우의 파일 처리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="11162-159">The following examples show file handling when ClickOnce and DirectInvoke are enabled or disabled.</span></span>

### <a name="clickonce-enabled"></a><span data-ttu-id="11162-160">ClickOnce 사용</span><span class="sxs-lookup"><span data-stu-id="11162-160">ClickOnce enabled</span></span>

1. <span data-ttu-id="11162-161">사용자가 ClickOnce 지원을 요청하는 페이지에 대한 링크를 열면 다음 스크린샷과 같은 프롬프트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="11162-161">A user opens a link to a page that requests ClickOnce support and gets the prompt in the next screenshot.</span></span>

   ![안전하지 않은 파일 열기 프롬프트](./media/edge-learn-more-co-di/edge-clickonce-enabled-1.png)

2. <span data-ttu-id="11162-163">사용자가 **열기**를 클릭하면 ClickOnce가 응용 프로그램을 시작하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="11162-163">After the user clicks **Open**, ClickOnce attempts to launch the application.</span></span>

   ![ClickOnce에서 응용 프로그램을 시작하려고 시도](./media/edge-learn-more-co-di/edge-clickonce-enabled-launch-app.png)

3. <span data-ttu-id="11162-165">사용자가 **열기**를 클릭하면 사용자에게 응용 프로그램을 설치할지 묻는 팝업이 브라우저에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="11162-165">After the user clicks **Open**, the browser shows a popup that asks the user if they're sure they want to install the application.</span></span>

   ![파일 열기 프롬프트](./media/edge-learn-more-co-di/edge-clickonce-enabled-2.png)

   > [!NOTE]
   > <span data-ttu-id="11162-167">ClickOnce 파일 처리기에 표시되는 인터페이스, 메시지 및 옵션은 액세스하는 파일의 유형 및 구성에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="11162-167">The interface, messaging, and options shown by the ClickOnce file handler will vary depending on the type and configuration of the file that's accessed.</span></span>

### <a name="clickonce-disabled"></a><span data-ttu-id="11162-168">ClickOnce 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="11162-168">ClickOnce disabled</span></span>

1. <span data-ttu-id="11162-169">사용자가 ClickOnce 지원을 요청하는 페이지에 대한 링크를 열면 다운로드 트레이에 다음 스크린샷과 같은 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="11162-169">When a user opens a link to a page that requests ClickOnce support, they will see a message in the download tray that is similar to the one in the next screenshot.</span></span>

   ![파일 다운로드 프롬프트](./media/edge-learn-more-co-di/edge-clickonce-disabled-1.png)

### <a name="directinvoke-enabled"></a><span data-ttu-id="11162-171">DirectInvoke 사용</span><span class="sxs-lookup"><span data-stu-id="11162-171">DirectInvoke enabled</span></span>

1. <span data-ttu-id="11162-172">사용자가 DirectInvoke 지원을 요청하는 페이지에 대한 링크를 열면 다음 스크린샷과 같은 프롬프트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="11162-172">A user opens a link to a page that requests DirectInvoke support and gets the prompt in the next screenshot.</span></span>

   ![파일 열기 프롬프트](./media/edge-learn-more-co-di/edge-directinvoke-open-link-1.png)

2. <span data-ttu-id="11162-174">사용자가 **열기**를 클릭하면 요청된 파일 처리기가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="11162-174">When the user clicks **Open**, the requested file handler is opened.</span></span> <span data-ttu-id="11162-175">이 예제에서는 Microsoft Word가 이전 스크린샷에 표시된 문서를 여는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="11162-175">In this example, Microsoft Word is used to open the document that's shown in the previous screenshot.</span></span>

   > [!NOTE]
   > <span data-ttu-id="11162-176">DirectInvoke 파일 처리기에 표시되는 인터페이스, 메시지 및 옵션은 액세스하는 파일의 유형 및 구성에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="11162-176">The interface, messaging, and options shown by the DirectInvoke file handler will vary depending on the type and configuration of the file that's accessed.</span></span>

### <a name="directinvoke-disabled"></a><span data-ttu-id="11162-177">DirectInvoke 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="11162-177">DirectInvoke disabled</span></span>

1. <span data-ttu-id="11162-178">사용자가 DirectInvoke 지원을 요청하는 페이지에 대한 링크를 열면 DirectInvoke가 ClickOnce를 사용하지 않는 경우와 동일하게 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="11162-178">When a user opens a link to a page that requests DirectInvoke support, DirectInvoke behaves the same as when ClickOnce is disabled.</span></span> <span data-ttu-id="11162-179">다운로드 트레이에 다음 스크린샷과 같은 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="11162-179">They will see a message in the download tray that's similar to the one in the next screenshot.</span></span>

   ![파일 열기 프롬프트](./media/edge-learn-more-co-di/edge-directinvoke-open-link-2.png)

## <a name="see-also"></a><span data-ttu-id="11162-181">기타 참조</span><span class="sxs-lookup"><span data-stu-id="11162-181">See also</span></span>

- [<span data-ttu-id="11162-182">ClickOnce 보안 및 배포</span><span class="sxs-lookup"><span data-stu-id="11162-182">ClickOnce security and deployment</span></span>](/visualstudio/deployment/clickonce-security-and-deployment)
- [<span data-ttu-id="11162-183">Internet Explorer의 DirectInvoke</span><span class="sxs-lookup"><span data-stu-id="11162-183">DirectInvoke in Internet Explorer</span></span>](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/jj215788(v=vs.85))
- [<span data-ttu-id="11162-184">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="11162-184">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)