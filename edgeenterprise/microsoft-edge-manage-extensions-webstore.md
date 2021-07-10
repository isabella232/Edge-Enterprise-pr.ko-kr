---
title: 자체 호스트 Microsoft Edge 확장
ms.author: aspoddar
author: AndreaLBarr
manager: balajek
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 엔터프라이즈에서 Microsoft Edge 확장을 패키지하고 자체 호스팅하는 방법을 알아봅니다.
ms.openlocfilehash: aef4438212829006e39572fa938462f13721c580
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642874"
---
# <a name="self-host-microsoft-edge-extensions"></a><span data-ttu-id="b9043-103">자체 호스트 Microsoft Edge 확장</span><span class="sxs-lookup"><span data-stu-id="b9043-103">Self-host Microsoft Edge extensions</span></span>

<span data-ttu-id="b9043-104">이 문서에서는 자체 웹 사이트에서 호스트할 확장을 패키징하기 위한 기본 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-104">This article provides basic guidance for packaging an extension to host on your own webstore.</span></span> <span data-ttu-id="b9043-105">또한 조직의 장치 및 사용자에게 확장을 배포하는 방법에 대한 지침도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-105">It also includes instructions on how to deploy extensions to devices and users in your organization.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b9043-106">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="b9043-106">Prerequisites</span></span>

<span data-ttu-id="b9043-107">자체 확장을 자체 호스트하려면 확장 및 해당 매니페스트 파일에 대한 자체 웹 호스팅 서비스를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-107">To self-host your own extensions, you will need to provide your own web hosting services for the extensions and their manifest files.</span></span>

 <span data-ttu-id="b9043-108">다음 단계에서는 확장을 이미 만들었고, XML 파일 작업 경험이 있고, 그룹 정책 구성에 대한 실무 지식이 있고, Windows 레지스트리를 사용하는 방법을 알고 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-108">The following steps assume that you’ve already created your extension, have some experience with XML files, have a working knowledge of configuring group policy, and know how to use the Windows registry.</span></span>

## <a name="publish-an-extension"></a><span data-ttu-id="b9043-109">확장 게시</span><span class="sxs-lookup"><span data-stu-id="b9043-109">Publish an extension</span></span>

<span data-ttu-id="b9043-110">확장을 게시하기 전에 CRX(Chrome 확장명) 파일로 압축해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-110">Before you publish an extension it needs to be packed into a CRX (Chrome extension) file.</span></span> <span data-ttu-id="b9043-111">다음 단계를 지침으로 사용하여 확장을 CRX 파일로 압축합니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-111">Use the following steps as a guide to packing an extension as a CRX file.</span></span>

1. <span data-ttu-id="b9043-112">Microsoft Edge 주소 표시줄에서 *edge://extensions*로 이동하여 **개발자 모드**를 사용하도록 설정(아직 사용하도록 설정되지 않은 경우)합니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-112">In the Microsoft Edge address bar, go to *edge://extensions* and turn on **Developer mode** if it’s not already enabled.</span></span>
2. <span data-ttu-id="b9043-113">**설치된 확장**에서 **팩 확장**을 클릭하여 CRX 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-113">Under **Installed extensions**, click **Pack Extension** to create the CRX file.</span></span>
3. <span data-ttu-id="b9043-114">**팩 확장** 대화 상자를 사용하여 확장 원본이 있는 디렉터리를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-114">Use the **Pack extension** dialog to find the directory that has the source for the extension.</span></span> <span data-ttu-id="b9043-115">디렉터리를 선택한 다음 **팩 확장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-115">Select the directory and then click **Pack extension**.</span></span>  <span data-ttu-id="b9043-116">이렇게 하면 PEM 파일과 함께 CRX 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-116">This will create your CRX file, along with a PEM file.</span></span> <span data-ttu-id="b9043-117">확장에 버전을 업데이트하는 데 필요하므로 PEM 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-117">Save the PEM file because it’s needed for making version updates to the extension.</span></span> <span data-ttu-id="b9043-118">다음 스크린샷은 확장의 루트 디렉터리를 찾기 위한 **팩 확장** 대화 상자를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-118">The next screenshot shows the **Pack extension** dialog for locating the root directory of the extension.</span></span>

   :::image type="content" source="media/microsoft-edge-manage-extensions-webstore/manage-extensions-pack-dialog.png" alt-text="확장의 소스 코드를 찾기 위한 팩 확장 대화 상자입니다.":::

   > [!IMPORTANT]
   > <span data-ttu-id="b9043-120">PEM 파일은 확장의 키이며 향후 업데이트에 필요하므로 안전한 위치에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-120">Store the PEM file in a safe location because it’s the key for the extension and it’s needed for future updates.</span></span>

4. <span data-ttu-id="b9043-121">CRX 파일을 확장 창으로 끌어서 로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-121">Drag the CRX file into your extensions window and make sure that it loads.</span></span>
5. <span data-ttu-id="b9043-122">확장을 테스트하고 ID 필드(CRX ID) 및 버전 번호를 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-122">Test the extension and take note of the ID field (this is the CRX ID) and version number.</span></span> <span data-ttu-id="b9043-123">나중에 이 정보가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-123">You’ll need this information later.</span></span> <span data-ttu-id="b9043-124">다음 스크린샷은 CRX ID가 있는 테스트 확장을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-124">The next screenshot shows a test extension with its CRX ID.</span></span>

   :::image type="content" source="media/microsoft-edge-manage-extensions-webstore/manage-extensions-test-extension.png" alt-text="CRX ID를 보여주는 확장 예제":::

6. <span data-ttu-id="b9043-126">CRX 파일을 호스트에 업로드하고 다운로드할 위치의 URL을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-126">Upload the the CRX file to the host and note the URL of the location it will be downloaded from.</span></span> <span data-ttu-id="b9043-127">이 정보는 XML 매니페스트 파일에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-127">This information is needed for the XML manifest file.</span></span>
7. <span data-ttu-id="b9043-128">앱/확장 ID, 다운로드 URL 및 버전을 사용하여 매니페스트 XML 파일을 만들려면 다음 필드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-128">To create a manifest XML file with the app/extension ID, download URL, and version, define the following fields:</span></span>  

   - <span data-ttu-id="b9043-129">**앱 ID** - 5단계의 확장 ID</span><span class="sxs-lookup"><span data-stu-id="b9043-129">**appid** - The extension ID from step 5</span></span>
   - <span data-ttu-id="b9043-130">**코드베이스** - 6단계에서 CRX 파일의 다운로드 위치</span><span class="sxs-lookup"><span data-stu-id="b9043-130">**codebase** - The download location for the CRX file from step 6</span></span>
   - <span data-ttu-id="b9043-131">**버전** - 확장 매니페스트에 지정된 버전과 일치해야 하는 앱/확장 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-131">**version** - The version of the app/extension, which should match the version specified in the manifest of the extension.</span></span>

   <span data-ttu-id="b9043-132">다음 코드 조각은 XML 매니페스트 파일의 예를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-132">The next code snippet shows an example of an XML manifest file.</span></span>

   ```xml
   <?xml version='1.0' encoding='UTF-8'?> 
   <gupdate xmlns='http://www.google.com/update2/response' protocol='2.0'> 
     <app appid='ekilpdeokbpjmminmhfcgkncmmohmfeb'> 
     <updatecheck codebase='https://app.somecompany.com/extensionfolder/helloworld.crx' version='1.0' /> 
     </app> 
   </gupdate> 
   ```

   <span data-ttu-id="b9043-133">자세한 내용은 [Microsoft Edge에서 자동 업데이트 확장 - Microsoft Edge Development](/microsoft-edge/extensions-chromium/enterprise/auto-update)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b9043-133">For more information, see [Auto-update extensions in Microsoft Edge - Microsoft Edge Development](/microsoft-edge/extensions-chromium/enterprise/auto-update).</span></span>

8. <span data-ttu-id="b9043-134">완료된 XML 파일을 다운로드할 수 있는 위치에 업로드하고 URL을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-134">Upload the completed XML file to a location where it can be downloaded from, noting the URL.</span></span> <span data-ttu-id="b9043-135">이 URL은 그룹 정책을 사용하여 확장을 설치할 때 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-135">This URL will be needed when you install the extension using a group policy.</span></span> <span data-ttu-id="b9043-136">[개인적으로 호스팅된 확장 배포](#distribute-a-privately-hosted-extension)를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-136">See [Distribute a privately hosted extension](#distribute-a-privately-hosted-extension).</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="b9043-137">확장의 호스팅 위치에는 인증이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-137">The hosting location for the extension doesn’t need authentication.</span></span> <span data-ttu-id="b9043-138">사용 가능한 모든 위치에서 사용자 장치로 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-138">It needs to be accessible by user devices wherever they might be used.</span></span>

## <a name="publish-updates-to-an-extension"></a><span data-ttu-id="b9043-139">확장에 업데이트 게시</span><span class="sxs-lookup"><span data-stu-id="b9043-139">Publish updates to an extension</span></span>

<span data-ttu-id="b9043-140">업데이트된 확장을 변경하고 테스트한 후 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-140">After you change and test the updated extension you can publish it.</span></span> <span data-ttu-id="b9043-141">다음 단계를 지침으로 사용하여 업데이트를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-141">Use the following steps as a guide for publishing an update.</span></span>

1. <span data-ttu-id="b9043-142">다음 구문을 사용하여 확장 manifest.JSON 파일의 버전 번호를 더 높은 숫자로 변경합니다. `"version":"versionString"`.</span><span class="sxs-lookup"><span data-stu-id="b9043-142">Change the version number in your extension's manifest.JSON file to a higher number using the following syntax: `"version":"versionString"`.</span></span> <span data-ttu-id="b9043-143">"version":"1.0"인 경우 "version":"1.1" 또는 "1.0"보다 높은 숫자로 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-143">If the "version":"1.0", then you can update to "version":"1.1" or any number higher than "1.0".</span></span>
2. <span data-ttu-id="b9043-144">이전 단계에서 매니페스트 파일에 넣은 번호와 일치하도록 XML 파일의 "버전" `<updatecheck>`을(를) 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-144">Update the "version" of `<updatecheck>` in the XML file to match the number that you put in the manifest file in the previous step.</span></span> <span data-ttu-id="b9043-145">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="b9043-145">For example:</span></span><br>`<updatecheck codebase='https://app.somecompany.com/extensionfolder/helloworld.crx' version='1.1' />`
3. <span data-ttu-id="b9043-146">새 변경 내용을 포함하는 CRX 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-146">Create a CRX file that includes the new changes.</span></span> <span data-ttu-id="b9043-147">*edge://extensions*로 이동하여 **개발자 모드**를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-147">Go to *edge://extensions* and enable **Developer mode**.</span></span>
4. <span data-ttu-id="b9043-148">**팩 확장**을 클릭하고 확장 원본의 디렉터리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-148">Click **Pack extension** and go to the directory for the extension source.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="b9043-149">CRX 파일을 처음 만들었을 때 생성 및 저장한 것과 동일한 PEM 파일을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-149">Use the same PEM file that was generated and saved the first time the CRX file was created.</span></span> <span data-ttu-id="b9043-150">동일한 PEM 파일을 사용하지 않는 경우 확장의 앱 ID가 변경되어 업데이트가 새 확장명으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-150">If you don't use the same PEM file the app ID of the extension will change and the update will be treated as a new extension.</span></span>

5. <span data-ttu-id="b9043-151">CRX 파일을 확장 창으로 끌어서 놓고 로드되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-151">Drag and drop the CRX file into the extensions window and verify that it loads.</span></span>
6. <span data-ttu-id="b9043-152">업데이트된 확장을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-152">Test the updated extension.</span></span>
7. <span data-ttu-id="b9043-153">이전 CRX 파일 및 XML 파일을 업데이트된 확장명의 새로운 파일로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-153">Replace the old CRX file and XML file with the new files for the updated extension.</span></span>

<span data-ttu-id="b9043-154">확장의 변경 내용은 다음 정책 동기화 주기 중에 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-154">The extension's changes will be picked up during the next policy sync cycle.</span></span> <span data-ttu-id="b9043-155">확장 업데이트에 대한 자세한 내용은 [URL 업데이트](/microsoft-edge/extensions-chromium/enterprise/auto-update#update-url) 및 [매니페스트 업데이트](/microsoft-edge/extensions-chromium/enterprise/auto-update#updated-manifest)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b9043-155">For more information about updating extensions, see: [Update URL](/microsoft-edge/extensions-chromium/enterprise/auto-update#update-url) and [Update manifest](/microsoft-edge/extensions-chromium/enterprise/auto-update#updated-manifest).</span></span>

## <a name="distribute-a-privately-hosted-extension"></a><span data-ttu-id="b9043-156">개인적으로 호스팅된 확장 배포</span><span class="sxs-lookup"><span data-stu-id="b9043-156">Distribute a privately hosted extension</span></span>

<span data-ttu-id="b9043-157">CRX 파일이 호스트되는 위치의 링크를 공유할 수 있으며, 사용자가 브라우저에 URL을 입력하는 즉시 확장이 다운로드되고 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-157">You can share the link of the location where the CRX file is hosted, and as soon as users enter the URL in their browser the extension will be downloaded and installed.</span></span> <span data-ttu-id="b9043-158">사용자는 edge://extensions 페이지에서 확장을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-158">Users can enable the extension from the edge://extensions page.</span></span> <span data-ttu-id="b9043-159">사용자가 자체 호스팅 확장을 설치할 수 있도록 허용하려면, [ExtensionInstallAllowList](/deployedge/microsoft-edge-policies#extensioninstallallowlist) 정책에 확장 CRX ID를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-159">To allow users to install self-hosted extensions, you need to add the extension CRX IDs to the [ExtensionInstallAllowList](/deployedge/microsoft-edge-policies#extensioninstallallowlist) policy.</span></span>

<span data-ttu-id="b9043-160">또는 그룹 정책 [ExtensionInstallForceList](/deployedge/microsoft-edge-manage-extensions-policies#force-install-an-extension)를 사용하여 사용자 장치에 확장을 강제 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-160">Alternatively, you can use group policy [ExtensionInstallForceList](/deployedge/microsoft-edge-manage-extensions-policies#force-install-an-extension) to Force-install an extension on your users’ devices.</span></span>

<span data-ttu-id="b9043-161">선택한 사용자, 장치 또는 둘 다에 이러한 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-161">You can apply these policies to your selected users, devices, or both.</span></span> <span data-ttu-id="b9043-162">정책 업데이트는 즉각적이지 않으며 정책 설정을 적용하는 데 시간이 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="b9043-162">Remember though that policy updates are not instantaneous, and it will take time for the policy settings to take effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="b9043-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b9043-163">See also</span></span>

- [<span data-ttu-id="b9043-164">엔터프라이즈에서 Microsoft Edge 확장 관리</span><span class="sxs-lookup"><span data-stu-id="b9043-164">Manage Microsoft Edge extensions in the enterprise</span></span>](microsoft-edge-manage-extensions.md)
- [<span data-ttu-id="b9043-165">그룹 정책을 사용하여 Microsoft Edge 확장 관리</span><span class="sxs-lookup"><span data-stu-id="b9043-165">Use group policies to manage Microsoft Edge extensions</span></span>](microsoft-edge-manage-extensions-policies.md)
- [<span data-ttu-id="b9043-166">ExtensionSettings 정책에 대한 자세한 가이드</span><span class="sxs-lookup"><span data-stu-id="b9043-166">Detailed guide to the ExtensionSettings policy</span></span>](microsoft-edge-manage-extensions-ref-guide.md)
- [<span data-ttu-id="b9043-167">Microsoft Edge 확장에 대한 FAQ</span><span class="sxs-lookup"><span data-stu-id="b9043-167">FAQ for Microsoft Edge Extensions</span></span>](microsoft-edge-manage-extensions-faq.md)
- [<span data-ttu-id="b9043-168">Microsoft Edge Enterprise 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="b9043-168">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
