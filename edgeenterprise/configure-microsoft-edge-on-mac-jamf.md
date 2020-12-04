---
title: Jamf를 사용하여 macOS에서 Microsoft Edge 구성
ms.author: brianalt
author: dan-wesley
manager: laurawi
ms.date: 11/30/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Mac 장치에서 Jamf로 Microsoft Edge 정책 설정 구성
ms.openlocfilehash: 1859d9fb1fd3ea8ff6908c41f75df21a8b338769
ms.sourcegitcommit: ed6a5afabf909df87bec48671c4c47bcdfaeb7bc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2020
ms.locfileid: "11194716"
---
# <span data-ttu-id="f5fe9-103">macOS에서 Jamf로 Microsoft Edge 정책 설정 구성</span><span class="sxs-lookup"><span data-stu-id="f5fe9-103">Configure Microsoft Edge policy settings on macOS with Jamf</span></span>

<span data-ttu-id="f5fe9-104">이 문서에서는 Jamf Pro 10.19의 Microsoft Edge 정책 매니페스트 파일을 사용하여 macOS에서 정책 설정을 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-104">This article describes how to configure policy settings on macOS using a Microsoft Edge policy manifest file on Jamf Pro 10.19.</span></span>

<span data-ttu-id="f5fe9-105">속성 목록(.plist) 파일을 사용하여 macOS에서 Microsoft Edge 정책 설정을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-105">You can also configure Microsoft Edge policy settings on macOS by using a property list (.plist) file.</span></span> <span data-ttu-id="f5fe9-106">자세한 내용은 [.plist을 사용하여 macOS 구성](configure-microsoft-edge-on-mac.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-106">For more information, see [Configure for macOS using a .plist](configure-microsoft-edge-on-mac.md)</span></span>


## <span data-ttu-id="f5fe9-107">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="f5fe9-107">Prerequisites</span></span>

<span data-ttu-id="f5fe9-108">다음 소프트웨어가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-108">The following software is required:</span></span>

- <span data-ttu-id="f5fe9-109">Microsoft Edge 안정 채널 81</span><span class="sxs-lookup"><span data-stu-id="f5fe9-109">Microsoft Edge Stable channel 81</span></span>
- <span data-ttu-id="f5fe9-110">정책 템플릿 파일, 버전 81.0.416.3</span><span class="sxs-lookup"><span data-stu-id="f5fe9-110">Policy Templates file, version 81.0.416.3</span></span>
- <span data-ttu-id="f5fe9-111">Jamf Pro, 버전 10.19</span><span class="sxs-lookup"><span data-stu-id="f5fe9-111">Jamf Pro, Version 10.19</span></span>

## <span data-ttu-id="f5fe9-112">Jamf Pro 응용 프로그램 및 사용자 지정 설정 메뉴 정보</span><span class="sxs-lookup"><span data-stu-id="f5fe9-112">About the Jamf Pro Application & Custom Settings menu</span></span>

<span data-ttu-id="f5fe9-113">Jamf Pro 10.18 이전에는 Office 365 관리에 .plist 파일을 수동으로 작성해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-113">Before Jamf Pro 10.18, managing Office 365 involved manually building a .plist file.</span></span> <span data-ttu-id="f5fe9-114">이것은 강력한 기술 배경이 필요한 시간이 많이 소요되는 워크플로우였습니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-114">This was a time-consuming workflow that required a strong technical background.</span></span> <span data-ttu-id="f5fe9-115">Jamf Pro 10.18은 구성 프로세스를 간소화하여 이러한 장벽을 제거했습니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-115">Jamf Pro 10.18 eliminated those barriers by streamlining the configuration process.</span></span> <span data-ttu-id="f5fe9-116">그러나 IT 관리자는 Jamf에서 지정한 특정 응용 프로그램과 기본 설정 도메인에 대해서만 이 새로운 사용자 인터페이스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-116">However, IT Admins could only use this new user interface for specific applications and preference domains specified by Jamf.</span></span>

<span data-ttu-id="f5fe9-117">Jamf Pro 10.19에서 사용자는 JSON 매니페스트를 "사용자 정의 스키마"로 업로드하여 기본 설정 도메인을 대상으로 할 수 있으며 이 매니페스트에서 그래픽 사용자 인터페이스가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-117">In Jamf Pro 10.19, a user can upload a JSON manifest as a "custom schema" to target any preference domain, and the graphical user interface will be generated from this manifest.</span></span> <span data-ttu-id="f5fe9-118">생성된 사용자 지정 스키마는 JSON 스키마 사양을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-118">The custom schema that's created follows the JSON Schema specification.</span></span>

<span data-ttu-id="f5fe9-119">자세한 내용은 Jamf Pro 관리자 안내서의 [컴퓨터 구성 프로파일](https://jamf.it/computer-configuration-profiles)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-119">For more information, see [Computer Configuration Profiles](https://jamf.it/computer-configuration-profiles) in the Jamf Pro Administrator's Guide.</span></span>

## <span data-ttu-id="f5fe9-120">특정 버전의 Microsoft Edge에 대한 정책 매니페스트를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-120">Get the policy manifest for a specific version of Microsoft Edge</span></span>

<span data-ttu-id="f5fe9-121">정책 매니페스트를 얻으려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-121">To get the policy manifest:</span></span>

- <span data-ttu-id="f5fe9-122">[Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-122">Go to the [Microsoft Edge Enterprise landing page](https://aka.ms/EdgeEnterprise).</span></span>
- <span data-ttu-id="f5fe9-123">채널/버전 드롭다운 목록에서 **버전 81 이상을 사용**하는 채널을 선택합니다. _.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-123">On the Channel/Version dropdown list, select **any channel with version 81 or later.**_.</span></span>
- <span data-ttu-id="f5fe9-124">빌드 드롭다운 목록에서 _ *81 빌드 이상을 선택합니다.* \* _</span><span class="sxs-lookup"><span data-stu-id="f5fe9-124">On the Build dropdown list, select any _*81 build or later.*\*_.</span></span>
- <span data-ttu-id="f5fe9-125">정책 파일 얻기를 클릭하여 정책 템플릿 번들을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-125">Click GET POLICY FILES to download our policy templates bundle.</span></span>

  > [!NOTE]
  > <span data-ttu-id="f5fe9-126">현재 정책 템플릿 번들은 CAB 파일로 서명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-126">Currently, the policy templates bundle is signed as a CAB file.</span></span> <span data-ttu-id="f5fe9-127">macOS에서 파일을 열려면 The Unarchiver와 같은 타사 도구를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-127">You'll need to use a 3rd party tool, such as The Unarchiver to open the file on macOS.</span></span>

<span data-ttu-id="f5fe9-128">CAB 파일의 압축을 푼 후 ZIP 파일의 압축을 풀고 "mac"최상위 디렉터리로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-128">After you unpack the CAB file, unpack the ZIP file and navigate to the "mac" top level directory.</span></span> <span data-ttu-id="f5fe9-129">"policy_manifest.json"이라는 매니페스트가 이 디렉토리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-129">The manifest, which is named "policy_manifest.json", is in this directory.</span></span>

<span data-ttu-id="f5fe9-130">이 매니페스트는 빌드 81.0.416.3부터 모든 정책 번들에 게시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-130">This manifest will be published in every policy bundle starting with build 81.0.416.3.</span></span> <span data-ttu-id="f5fe9-131">Dev 채널에서 정책을 테스트하려는 경우 각 Dev 릴리스와 관련된 매니페스트를 가져와서 Jamf Pro에서 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-131">If you want to test policies in the Dev channel, you can take the manifest associated with each Dev release and test it in Jamf Pro.</span></span>  

## <span data-ttu-id="f5fe9-132">Jamf Pro의 정책 목록 사용</span><span class="sxs-lookup"><span data-stu-id="f5fe9-132">Use the policy manifest in Jamf Pro</span></span>

<span data-ttu-id="f5fe9-133">다음 단계를 사용하여 정책 매니페스트를 Jamf Pro에 업로드한 다음 macOS에 대한 정책 프로필을 생성하십시오.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-133">Use the following steps to upload the policy manifest to Jamf Pro and then create a policy profile for macOS.</span></span>

1. <span data-ttu-id="f5fe9-134">Jamf에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-134">Sign in to Jamf.</span></span>
2. <span data-ttu-id="f5fe9-135">_*컴퓨터*\* 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-135">Select the _*Computer*\* tab.</span></span>
3. <span data-ttu-id="f5fe9-136">**콘텐츠 관리**에서 **구성 프로파일**을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-136">Under **Content Management**, select **Configuration Profiles**.</span></span>
4. <span data-ttu-id="f5fe9-137">**구성 프로파일** 페이지에서 **+New**를 클릭하십시오.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-137">On the **Configuration Profiles** page, click **+ New**.</span></span>

   ![Jamf에서 새로운 프로필 추가](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-configuration-profiles.png)

5. <span data-ttu-id="f5fe9-139">**새 macOS 구성 프로파일**>**옵션**에서 **응용 프로그램 및 사용자 지정 설정**을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-139">On **New macOS Configuration Profile**>**Options**, select **Application & Custom Settings**.</span></span>
6. <span data-ttu-id="f5fe9-140">**응용 프로그램 및 사용자 지정 설정** 팝업 창에서 **구성**을 클릭하십시오.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-140">On the **Application & Custom Settings** popup window, click **Configure**.</span></span>

   ![응용 프로그램 및 사용자 지정 설정 구성](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-app-and-custom.png)

7. <span data-ttu-id="f5fe9-142">**응용 프로그램 & 사용자 지정 설정** 섹션에서 다음 스크린샷에 표시된 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-142">In the **Application & Custom Settings** section, set the values shown in the following screen shot.</span></span>

   ![프로파일 소스 및 사용자 지정 스키마](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-app-and-custom-schema.png)

   - <span data-ttu-id="f5fe9-144">**만들기 방법**에 대해 **설정 구성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-144">For **Creation Method**, pick **Configure settings**.</span></span>
   - <span data-ttu-id="f5fe9-145">**소스**에 대해 **사용자 지정 스키마**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-145">For **Source**, pick **Custom Schema**.</span></span>
   - <span data-ttu-id="f5fe9-146">**기본 설정 도메인**에 대해 도메인 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-146">For **Preference Domain**, provide the name of your domain.</span></span> <span data-ttu-id="f5fe9-147">이 예제에서는 *com.microsoft.Edge*을 도메인으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-147">This example uses *com.microsoft.Edge* as the domain.</span></span>
   - <span data-ttu-id="f5fe9-148">**사용자 지정 스키마**의 경우 "policy_manifest json" 매니페스트 파일의 내용을 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-148">For **Custom Schema**, paste the contents of the "policy_manifest.json" manifest file.</span></span>
   - <span data-ttu-id="f5fe9-149">**Save**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-149">Click **Save**.</span></span>

8. <span data-ttu-id="f5fe9-150">프로파일을 저장한 후 Jamf는 다음 스크린 샷에 표시된 **일반** 섹션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-150">After you save the profile, Jamf displays the **General** section shown in the next screen shot.</span></span>

   ![일반 구성 섹션](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-app-and-custom-general-setting.png)

   - <span data-ttu-id="f5fe9-152">프로파일의 표시 **이름** 및 **설명**을 제공하십시오.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-152">Provide a display **Name** for the profile and a **Description**.</span></span>
   - <span data-ttu-id="f5fe9-153">**범주**에 대한 기본 설정인 **없음**을 유지하십시오.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-153">Keep the default setting for **Category**, which is **None**.</span></span>
   - <span data-ttu-id="f5fe9-154">**배포 방법**의 경우, 옵션은 **자동으로 설치** 또는 **셀프 서비스에서 사용 가능하도록 설정**입니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-154">For **Distribution Method**, the options are **Install Automatically** or **Make Available in Self Service**.</span></span>
   - <span data-ttu-id="f5fe9-155">**수준**의 경우 옵션은 **사용자 수준** 또는 **컴퓨터 수준**입니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-155">For **Level**, the options are **User Level** or **Computer Level**.</span></span>
   - <span data-ttu-id="f5fe9-156">**Save**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-156">Click **Save**.</span></span>

9. <span data-ttu-id="f5fe9-157">일반 섹션을 저장하면 Jamf는 예제에 대해 설정된 "Microsoft Edge 베타 채널" 구성 프로필을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-157">After you save the General section, Jamf shows the "Microsoft Edge Beta Channel" configuration profile set up for our example.</span></span> <span data-ttu-id="f5fe9-158">다음 스크린샷에서 **편집**을 클릭하여 프로파일 작업을 계속할 수 있거나 완료한 경우 **완료**를 클릭하십시오.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-158">In the next screen shot, note that you can keep working the profile by clicking **Edit** or if you're finished, click **Done**.</span></span>

   ![옵션이 있는 새로운 구성 프로필](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-configuration-profiles-beta-channel.png)

   > [!NOTE]
   > <span data-ttu-id="f5fe9-160">이 프로필을 저장한 후 다른 Jamf 세션에서 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-160">You can edit this profile after it's been saved and in another Jamf session.</span></span> <span data-ttu-id="f5fe9-161">예를 들어, 배포 방법을 셀프 서비스에서 사용 가능하도록 변경하기로 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-161">For example, you might decide to change the Distribution Method to Make Available in Self Service.</span></span>

   <span data-ttu-id="f5fe9-162">Microsoft Edge 안정 채널에서 후속 편집을 수행하거나 삭제하려면 다음 구성 프로파일 스크린샷에 표시된 프로파일 이름을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-162">To do a follow up edit on the Microsoft Edge Stable Channel, or delete it, select the profile name, shown in the following Configuration Profiles screen shot.</span></span>

   ![구성 프로필 목록](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-configuration-profiles-beta-channel-done.png)

<span data-ttu-id="f5fe9-164">새 구성 프로필을 만든 후에는 계속해서 프로필에 대한 **범위**를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-164">After you create the new configuration profile you still have to configure the **Scope** for the profile.</span></span>

### <span data-ttu-id="f5fe9-165">범위를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="f5fe9-165">To configure the scope</span></span>

1. <span data-ttu-id="f5fe9-166">**대상**의 경우 다음 최소 설정값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-166">For **Targets**, provide the following minimum settings:</span></span>

   - <span data-ttu-id="f5fe9-167">대상 컴퓨터.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-167">TARGET COMPUTERS.</span></span> <span data-ttu-id="f5fe9-168">옵션은 특정 컴퓨터나 모든 컴퓨터입니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-168">The options are Specific Computers or All Computers.</span></span>
   - <span data-ttu-id="f5fe9-169">대상 사용자.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-169">TARGET USERS.</span></span> <span data-ttu-id="f5fe9-170">옵션은 특정 사용자나 모든 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-170">The options are Specific Users or All Users.</span></span>
   - <span data-ttu-id="f5fe9-171">**Save**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-171">Click **Save**.</span></span>
2. <span data-ttu-id="f5fe9-172">**제한**의 경우 기본 설정인 없음을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-172">For **Limitations**, keep the default setting: None.</span></span> <span data-ttu-id="f5fe9-173">**취소**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-173">Click **Cancel**.</span></span>
3. <span data-ttu-id="f5fe9-174">**제외**의 경우 기본 설정인 없음을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-174">For **Exclusions**, keep the default setting: None.</span></span> <span data-ttu-id="f5fe9-175">**취소**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f5fe9-175">Click **Cancel**.</span></span>

## <span data-ttu-id="f5fe9-176">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f5fe9-176">See also</span></span>

- [<span data-ttu-id="f5fe9-177">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="f5fe9-177">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="f5fe9-178">Intune을 사용한 macOS용 구성</span><span class="sxs-lookup"><span data-stu-id="f5fe9-178">Configure for macOS with Intune</span></span>](configure-microsoft-edge-on-mac.md)
- [<span data-ttu-id="f5fe9-179">Windows용 구성</span><span class="sxs-lookup"><span data-stu-id="f5fe9-179">Configure for Windows</span></span>](configure-microsoft-edge.md)
- [<span data-ttu-id="f5fe9-180">Intune을 사용한 Windows용 구성</span><span class="sxs-lookup"><span data-stu-id="f5fe9-180">Configure for Windows with Intune</span></span>](configure-edge-with-intune.md)
