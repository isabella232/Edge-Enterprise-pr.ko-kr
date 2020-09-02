---
title: Jamf를 사용하여 macOS에서 Microsoft Edge 구성
ms.author: brianalt
author: dan-wesley
manager: laurawi
ms.date: 02/20/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Mac 장치에서 Jamf로 Microsoft Edge 정책 설정 구성
ms.openlocfilehash: 336bdfed2c53811615b0183dc5ca7db916cd7428
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980588"
---
# <span data-ttu-id="5b3cd-103">macOS에서 Jamf로 Microsoft Edge 정책 설정 구성</span><span class="sxs-lookup"><span data-stu-id="5b3cd-103">Configure Microsoft Edge policy settings on macOS with Jamf</span></span>

<span data-ttu-id="5b3cd-104">이 문서에서는 Jamf Pro 10.19의 Microsoft Edge 정책 매니페스트 파일을 사용하여 macOS에서 정책 설정을 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-104">This article describes how to configure policy settings on macOS using a Microsoft Edge policy manifest file on Jamf Pro 10.19.</span></span>

<span data-ttu-id="5b3cd-105">속성 목록(.plist) 파일을 사용하여 macOS에서 Microsoft Edge 정책 설정을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-105">You can also configure Microsoft Edge policy settings on macOS by using a property list (.plist) file.</span></span> <span data-ttu-id="5b3cd-106">자세한 내용은 [.plist을 사용하여 macOS 구성](configure-microsoft-edge-on-mac.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-106">For more information, see [Configure for macOS using a .plist](configure-microsoft-edge-on-mac.md)</span></span>


## <span data-ttu-id="5b3cd-107">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="5b3cd-107">Prerequisites</span></span>

<span data-ttu-id="5b3cd-108">다음 소프트웨어가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-108">The following software is required:</span></span>

- <span data-ttu-id="5b3cd-109">Microsoft Edge 안정 채널 81</span><span class="sxs-lookup"><span data-stu-id="5b3cd-109">Microsoft Edge Stable channel 81</span></span>
- <span data-ttu-id="5b3cd-110">정책 템플릿 파일, 버전 81.0.416.3</span><span class="sxs-lookup"><span data-stu-id="5b3cd-110">Policy Templates file, version 81.0.416.3</span></span>
- <span data-ttu-id="5b3cd-111">Jamf Pro, 버전 10.19</span><span class="sxs-lookup"><span data-stu-id="5b3cd-111">Jamf Pro, Version 10.19</span></span>

## <span data-ttu-id="5b3cd-112">Jamf Pro 응용 프로그램 및 사용자 지정 설정 메뉴 정보</span><span class="sxs-lookup"><span data-stu-id="5b3cd-112">About the Jamf Pro Application & Custom Settings menu</span></span>

<span data-ttu-id="5b3cd-113">Jamf Pro 10.18 이전에는 Office 365 관리에 .plist 파일을 수동으로 작성해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-113">Before Jamf Pro 10.18, managing Office 365 involved manually building a .plist file.</span></span> <span data-ttu-id="5b3cd-114">이것은 강력한 기술 배경이 필요한 시간이 많이 소요되는 워크플로우였습니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-114">This was a time-consuming workflow that required a strong technical background.</span></span> <span data-ttu-id="5b3cd-115">Jamf Pro 10.18은 구성 프로세스를 간소화하여 이러한 장벽을 제거했습니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-115">Jamf Pro 10.18 eliminated those barriers by streamlining the configuration process.</span></span> <span data-ttu-id="5b3cd-116">그러나 IT 관리자는 Jamf에서 지정한 특정 응용 프로그램과 기본 설정 도메인에 대해서만 이 새로운 사용자 인터페이스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-116">However, IT Admins could only use this new user interface for specific applications and preference domains specified by Jamf.</span></span>

<span data-ttu-id="5b3cd-117">Jamf Pro 10.19에서 사용자는 JSON 매니페스트를 "사용자 정의 스키마"로 업로드하여 기본 설정 도메인을 대상으로 할 수 있으며 이 매니페스트에서 그래픽 사용자 인터페이스가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-117">In Jamf Pro 10.19, a user can upload a JSON manifest as a "custom schema" to target any preference domain, and the graphical user interface will be generated from this manifest.</span></span> <span data-ttu-id="5b3cd-118">생성된 사용자 지정 스키마는 JSON 스키마 사양을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-118">The custom schema that's created follows the JSON Schema specification.</span></span>

<span data-ttu-id="5b3cd-119">자세한 내용은 Jamf Pro 관리자 안내서의 [컴퓨터 구성 프로파일](https://jamf.it/computer-configuration-profiles)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-119">For more information, see [Computer Configuration Profiles](https://jamf.it/computer-configuration-profiles) in the Jamf Pro Administrator's Guide.</span></span>

## <span data-ttu-id="5b3cd-120">특정 버전의 Microsoft Edge에 대한 정책 매니페스트를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-120">Get the policy manifest for a specific version of Microsoft Edge</span></span>

<span data-ttu-id="5b3cd-121">정책 매니페스트를 얻으려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-121">To get the policy manifest:</span></span>

- <span data-ttu-id="5b3cd-122">[Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-122">Go to the [Microsoft Edge Enterprise landing page](https://aka.ms/EdgeEnterprise).</span></span>
- <span data-ttu-id="5b3cd-123">채널/버전 드롭다운 목록에서 \*\*버전 81 이상인 채널\*\*\*을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-123">On the Channel/Version dropdown list, select \*\*any channel with version 81 or later.\*\*\*.</span></span>
- <span data-ttu-id="5b3cd-124">빌드 드롭다운 목록에서 \*\*81 빌드 이상\*\*\*을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-124">On the Build dropdown list, select any \*\*81 build or later.\*\*\*.</span></span>
- <span data-ttu-id="5b3cd-125">정책 파일 얻기를 클릭하여 정책 템플릿 번들을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-125">Click GET POLICY FILES to download our policy templates bundle.</span></span>

  > [!NOTE]
  > <span data-ttu-id="5b3cd-126">현재 정책 템플릿 번들은 CAB 파일로 서명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-126">Currently, the policy templates bundle is signed as a CAB file.</span></span> <span data-ttu-id="5b3cd-127">macOS에서 파일을 열려면 The Unarchiver와 같은 타사 도구를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-127">You'll need to use a 3rd party tool, such as The Unarchiver to open the file on macOS.</span></span>

<span data-ttu-id="5b3cd-128">CAB 파일의 압축을 푼 후 ZIP 파일의 압축을 풀고 "mac"최상위 디렉터리로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-128">After you unpack the CAB file, unpack the ZIP file and navigate to the "mac" top level directory.</span></span> <span data-ttu-id="5b3cd-129">"policy_manifest.json"이라는 매니페스트가 이 디렉토리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-129">The manifest, which is named "policy_manifest.json", is in this directory.</span></span>

<span data-ttu-id="5b3cd-130">이 매니페스트는 빌드 81.0.416.3부터 모든 정책 번들에 게시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-130">This manifest will be published in every policy bundle starting with build 81.0.416.3.</span></span> <span data-ttu-id="5b3cd-131">Dev 채널에서 정책을 테스트하려는 경우 각 Dev 릴리스와 관련된 매니페스트를 가져와서 Jamf Pro에서 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-131">If you want to test policies in the Dev channel, you can take the manifest associated with each Dev release and test it in Jamf Pro.</span></span>  

## <span data-ttu-id="5b3cd-132">Jamf Pro의 정책 목록 사용</span><span class="sxs-lookup"><span data-stu-id="5b3cd-132">Use the policy manifest in Jamf Pro</span></span>

<span data-ttu-id="5b3cd-133">다음 단계를 사용하여 정책 매니페스트를 Jamf Pro에 업로드한 다음 macOS에 대한 정책 프로필을 생성하십시오.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-133">Use the following steps to upload the policy manifest to Jamf Pro and then create a policy profile for macOS.</span></span>

1. <span data-ttu-id="5b3cd-134">Jamf에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-134">Sign in to Jamf.</span></span>
2. <span data-ttu-id="5b3cd-135">**컴퓨터** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-135">Select the **Computer** tab.</span></span>
3. <span data-ttu-id="5b3cd-136">**콘텐츠 관리**에서 **구성 프로파일**을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-136">Under **Content Management**, select **Configuration Profiles**.</span></span>
4. <span data-ttu-id="5b3cd-137">**구성 프로파일** 페이지에서 **+New**를 클릭하십시오.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-137">On the **Configuration Profiles** page, click **+ New**.</span></span>

   ![Jamf에서 새로운 프로필 추가](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-configuration-profiles.png)

5. <span data-ttu-id="5b3cd-139">**새 macOS 구성 프로파일**>**옵션**에서 **응용 프로그램 및 사용자 지정 설정**을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-139">On **New macOS Configuration Profile**>**Options**, select **Application & Custom Settings**.</span></span>
6. <span data-ttu-id="5b3cd-140">**응용 프로그램 및 사용자 지정 설정** 팝업 창에서 **구성**을 클릭하십시오.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-140">On the **Application & Custom Settings** popup window, click **Configure**.</span></span>

   ![응용 프로그램 및 사용자 지정 설정 구성](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-app-and-custom.png)

7. <span data-ttu-id="5b3cd-142">**응용 프로그램 & 사용자 지정 설정** 섹션에서 다음 스크린샷에 표시된 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-142">In the **Application & Custom Settings** section, set the values shown in the following screen shot.</span></span>

   ![프로파일 소스 및 사용자 지정 스키마](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-app-and-custom-schema.png)

   - <span data-ttu-id="5b3cd-144">**만들기 방법**에 대해 **설정 구성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-144">For **Creation Method**, pick **Configure settings**.</span></span>
   - <span data-ttu-id="5b3cd-145">**소스**에 대해 **사용자 지정 스키마**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-145">For **Source**, pick **Custom Schema**.</span></span>
   - <span data-ttu-id="5b3cd-146">**기본 설정 도메인**에 대해 도메인 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-146">For **Preference Domain**, provide the name of your domain.</span></span> <span data-ttu-id="5b3cd-147">이 예제에서는 *com.microsoft.Edge*을 도메인으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-147">This example uses *com.microsoft.Edge* as the domain.</span></span>
   - <span data-ttu-id="5b3cd-148">**사용자 지정 스키마**의 경우 "policy_manifest json" 매니페스트 파일의 내용을 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-148">For **Custom Schema**, paste the contents of the "policy_manifest.json" manifest file.</span></span>
   - <span data-ttu-id="5b3cd-149">**Save**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-149">Click **Save**.</span></span>

8. <span data-ttu-id="5b3cd-150">프로파일을 저장한 후 Jamf는 다음 스크린 샷에 표시된 **일반** 섹션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-150">After you save the profile, Jamf displays the **General** section shown in the next screen shot.</span></span>

   ![일반 구성 섹션](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-app-and-custom-general-setting.png)

   - <span data-ttu-id="5b3cd-152">프로파일의 표시 **이름** 및 **설명**을 제공하십시오.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-152">Provide a display **Name** for the profile and a **Description**.</span></span>
   - <span data-ttu-id="5b3cd-153">**범주**에 대한 기본 설정인 **없음**을 유지하십시오.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-153">Keep the default setting for **Category**, which is **None**.</span></span>
   - <span data-ttu-id="5b3cd-154">**배포 방법**의 경우, 옵션은 **자동으로 설치** 또는 **셀프 서비스에서 사용 가능하도록 설정**입니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-154">For **Distribution Method**, the options are **Install Automatically** or **Make Available in Self Service**.</span></span>
   - <span data-ttu-id="5b3cd-155">**수준**의 경우 옵션은 **사용자 수준** 또는 **컴퓨터 수준**입니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-155">For **Level**, the options are **User Level** or **Computer Level**.</span></span>
   - <span data-ttu-id="5b3cd-156">**Save**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-156">Click **Save**.</span></span>

9. <span data-ttu-id="5b3cd-157">일반 섹션을 저장하면 Jamf는 예제에 대해 설정된 "Microsoft Edge 베타 채널" 구성 프로필을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-157">After you save the General section, Jamf shows the "Microsoft Edge Beta Channel" configuration profile set up for our example.</span></span> <span data-ttu-id="5b3cd-158">다음 스크린샷에서 **편집**을 클릭하여 프로파일 작업을 계속할 수 있거나 완료한 경우 **완료**를 클릭하십시오.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-158">In the next screen shot, note that you can keep working the profile by clicking **Edit** or if you're finished, click **Done**.</span></span>

   ![옵션이 있는 새로운 구성 프로필](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-configuration-profiles-beta-channel.png)

   > [!NOTE]
   > <span data-ttu-id="5b3cd-160">이 프로필을 저장한 후 다른 Jamf 세션에서 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-160">You can edit this profile after it's been saved and in another Jamf session.</span></span> <span data-ttu-id="5b3cd-161">예를 들어, 배포 방법을 셀프 서비스에서 사용 가능하도록 변경하기로 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-161">For example, you might decide to change the Distribution Method to Make Available in Self Service.</span></span>

   <span data-ttu-id="5b3cd-162">Microsoft Edge 안정 채널에서 후속 편집을 수행하거나 삭제하려면 다음 구성 프로파일 스크린샷에 표시된 프로파일 이름을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-162">To do a follow up edit on the Microsoft Edge Stable Channel, or delete it, select the profile name, shown in the following Configuration Profiles screen shot.</span></span>

   ![구성 프로필 목록](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-configuration-profiles-beta-channel-done.png)

<span data-ttu-id="5b3cd-164">새 구성 프로필을 만든 후에는 계속해서 프로필에 대한 **범위**를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-164">After you create the new configuration profile you still have to configure the **Scope** for the profile.</span></span>

### <span data-ttu-id="5b3cd-165">범위를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="5b3cd-165">To configure the scope</span></span>

1. <span data-ttu-id="5b3cd-166">**대상**의 경우 다음 최소 설정값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-166">For **Targets**, provide the following minimum settings:</span></span>

   - <span data-ttu-id="5b3cd-167">대상 컴퓨터.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-167">TARGET COMPUTERS.</span></span> <span data-ttu-id="5b3cd-168">옵션은 특정 컴퓨터나 모든 컴퓨터입니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-168">The options are Specific Computers or All Computers.</span></span>
   - <span data-ttu-id="5b3cd-169">대상 사용자.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-169">TARGET USERS.</span></span> <span data-ttu-id="5b3cd-170">옵션은 특정 사용자나 모든 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-170">The options are Specific Users or All Users.</span></span>
   - <span data-ttu-id="5b3cd-171">**Save**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-171">Click **Save**.</span></span>
2. <span data-ttu-id="5b3cd-172">**제한**의 경우 기본 설정인 없음을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-172">For **Limitations**, keep the default setting: None.</span></span> <span data-ttu-id="5b3cd-173">**취소**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-173">Click **Cancel**.</span></span>
3. <span data-ttu-id="5b3cd-174">**제외**의 경우 기본 설정인 없음을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-174">For **Exclusions**, keep the default setting: None.</span></span> <span data-ttu-id="5b3cd-175">**취소**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-175">Click **Cancel**.</span></span>

## <span data-ttu-id="5b3cd-176">질문과 대답</span><span class="sxs-lookup"><span data-stu-id="5b3cd-176">Frequently Asked Questions</span></span>

### <span data-ttu-id="5b3cd-177">마스터 기본 설정을 사용하도록 Microsoft Edge를 구성할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="5b3cd-177">Can Microsoft Edge be configured to use master preferences?</span></span>

<span data-ttu-id="5b3cd-178">예, 마스터 기본 설정 파일을 사용하도록 Microsoft Edge를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-178">Yes, you can configure Microsoft Edge to use a master preferences file.</span></span>

<span data-ttu-id="5b3cd-179">마스터 기본 설정 파일을 사용하면 Microsoft Edge가 배포될 때 브라우저 사용자 프로필에 대한 기본 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-179">A master preferences file lets you configure default settings for a browser user profile when Microsoft Edge is deployed.</span></span> <span data-ttu-id="5b3cd-180">또한 마스터 기본 설정 파일을 사용하여 장치 관리 시스템에서 관리하지 않는 컴퓨터에서 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-180">You can also use a master preferences file to apply settings on computers that aren't managed by a device management system.</span></span> <span data-ttu-id="5b3cd-181">이러한 설정은 사용자가 브라우저를 처음 실행할 때 사용자 프로필에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-181">These settings are applied to the user’s profile the first time the user runs the browser.</span></span> <span data-ttu-id="5b3cd-182">사용자가 브라우저를 실행한 후에는 마스터 기본 설정 파일의 변경 내용이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-182">After the user runs the browser, changes to the master preferences file aren’t applied.</span></span> <span data-ttu-id="5b3cd-183">사용자는 브라우저에서 마스터 기본 설정에서 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-183">A user can change settings from the master preferences in the browser.</span></span> <span data-ttu-id="5b3cd-184">설정을 필수로 만들거나 브라우저를 처음 실행한 후 설정을 변경하려면 정책을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-184">If you want to make a setting mandatory or change a setting after the first run of the browser, you must use a policy.</span></span>

<span data-ttu-id="5b3cd-185">마스터 기본 설정 파일을 사용하면 다른 Chromium 기반 브라우저와 공유되는 항목과 Microsoft Edge에 고유한 항목을 포함하여 다양한 설정 및 기본 설정을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-185">A master preferences file lets you to customize many different settings and preferences for the browser, including those shared with other Chromium based browsers and specific to Microsoft Edge.</span></span>  <span data-ttu-id="5b3cd-186">마스터 기본 설정 파일을 사용하여 정책 관련 기본 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-186">Policy related preferences can be configured using the master preferences file.</span></span> <span data-ttu-id="5b3cd-187">정책이 설정되어 있고 해당 마스터 기본 설정 집합이 있는 경우 정책 설정이 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-187">In cases where a policy is set and there’s a corresponding master preference set, the policy setting takes precedence.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5b3cd-188">사용 가능한 기본 설정 중 일부는 Microsoft Edge 용어 및 명명 규칙과 일치하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-188">All the available preferences might not be consistent with Microsoft Edge terminology and naming conventions.</span></span>  <span data-ttu-id="5b3cd-189">이후 릴리스에서 이러한 기본 설정이 예상대로 계속 작동한다는 보장은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-189">There’s no guarantee that these preferences will continue to work as expected in future releases.</span></span> <span data-ttu-id="5b3cd-190">이후 버전에서 기본 설정이 변경되거나 무시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-190">Preferences might be changed or ignored in later versions.</span></span>

<span data-ttu-id="5b3cd-191">마스터 기본 설정 파일은 JSON 태그를 사용하여 서식 지정된 텍스트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-191">A master preferences file is a text file that’s formatted using JSON markup.</span></span> <span data-ttu-id="5b3cd-192">이 파일은 msedge.exe 실행 파일과 동일한 디렉터리에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-192">This file needs to be added to the same directory as the msedge.exe executable.</span></span> <span data-ttu-id="5b3cd-193">macOS에서의 시스템 수준 엔터프라이즈 배포인 경우 이 폴더는 일반적으로 “*~/Library/Application Support/Microsoft/Microsoft Edge Master Preferences*" 또는 "*/Library/Microsoft/Microsoft Edge Master Preferences*”입니다.</span><span class="sxs-lookup"><span data-stu-id="5b3cd-193">For system wide enterprise deployments on macOS this is typically: “*~/Library/Application Support/Microsoft/Microsoft Edge Master Preferences*" or "*/Library/Microsoft/Microsoft Edge Master Preferences*”.</span></span>

## <span data-ttu-id="5b3cd-194">기타 참조</span><span class="sxs-lookup"><span data-stu-id="5b3cd-194">See also</span></span>

- [<span data-ttu-id="5b3cd-195">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="5b3cd-195">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="5b3cd-196">Intune을 사용한 macOS용 구성</span><span class="sxs-lookup"><span data-stu-id="5b3cd-196">Configure for macOS with Intune</span></span>](configure-microsoft-edge-on-mac.md)
- [<span data-ttu-id="5b3cd-197">Windows용 구성</span><span class="sxs-lookup"><span data-stu-id="5b3cd-197">Configure for Windows</span></span>](configure-microsoft-edge.md)
- [<span data-ttu-id="5b3cd-198">Intune을 사용한 Windows용 구성</span><span class="sxs-lookup"><span data-stu-id="5b3cd-198">Configure for Windows with Intune</span></span>](configure-edge-with-intune.md)
