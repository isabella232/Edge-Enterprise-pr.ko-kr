---
title: .plist를 사용하여 macOS용 Microsoft Edge 구성
ms.author: brianalt
author: kelleyvice-msft
manager: laurawi
ms.date: 02/14/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: .plist를 사용하여 macOS에서 Microsoft Edge 정책 설정 구성
ms.openlocfilehash: 84469a4f84deeee0e47b6d8899426fa36cf345aa
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980582"
---
# <span data-ttu-id="eb3a5-103">.plist를 사용하여 macOS에서 Microsoft Edge 정책 설정 구성</span><span class="sxs-lookup"><span data-stu-id="eb3a5-103">Configure Microsoft Edge policy settings for macOS using a .plist</span></span>

<span data-ttu-id="eb3a5-104">이 문서에서는 속성 목록(.plist) 파일을 사용하여 macOS에서 Microsoft Edge를 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-104">This article describes how to configure Microsoft Edge on macOS using a property list (.plist) file.</span></span> <span data-ttu-id="eb3a5-105">이 파일을 만든 다음 Microsoft Intune에 배포하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-105">You'll learn how to create this file and then deploy it to Microsoft Intune.</span></span>

<span data-ttu-id="eb3a5-106">자세한 내용은 [속성 목록 파일 정보](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html)(Apple의 웹 사이트) 및 [사용자 지정 페이로드 설정](https://support.apple.com/guide/mdm/custom-mdm9abbdbe7/1/web/1)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-106">For more information, see [About Information Property List Files](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) (Apple's website) and [Custom payload settings](https://support.apple.com/guide/mdm/custom-mdm9abbdbe7/1/web/1).</span></span>

> [!NOTE]
> <span data-ttu-id="eb3a5-107">이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-107">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="eb3a5-108">macOS에서 Microsoft Edge 설정 구성</span><span class="sxs-lookup"><span data-stu-id="eb3a5-108">Configure Microsoft Edge policies on macOS</span></span>

<span data-ttu-id="eb3a5-109">첫 번째 단계에서는 제출을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-109">The first step is to create your plist.</span></span> <span data-ttu-id="eb3a5-110">임의의 텍스트 편집기를 사용하여 plist 파일을 만들거나 [터미널을 사용하여 구성 프로필을 만들](#create-a-configuration-profile-using-terminal) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-110">You can create the plist file with any text editor or you can use [Terminal to create the configuration profile](#create-a-configuration-profile-using-terminal).</span></span> <span data-ttu-id="eb3a5-111">하지만 사용자 대신 XML 코드의 서식을 지정하는 도구를 사용하여 plist 파일을 더 쉽게 만들고 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-111">However, it's easier to create and edit a plist file using a tool that formats the XML code for you.</span></span> <span data-ttu-id="eb3a5-112">*Xcode*는 다음 위치 중 하나에서 얻을 수 있는 무료 통합 개발 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-112">*Xcode* is a free integrated development environment that you can get from one of the following locations:</span></span>

- [<span data-ttu-id="eb3a5-113">Apple 개발자 웹 사이트</span><span class="sxs-lookup"><span data-stu-id="eb3a5-113">Apple developer website</span></span>](https://developer.apple.com/xcode/)
- [<span data-ttu-id="eb3a5-114">Mac App Store</span><span class="sxs-lookup"><span data-stu-id="eb3a5-114">Mac App Store</span></span>](https://apps.apple.com/app/xcode/id497799835?mt=12)

<span data-ttu-id="eb3a5-115">지원되는 정책 및 기본 설정 키 이름의 목록은 [Microsoft Edge 브라우저 정책 참조](microsoft-edge-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-115">For a list of supported policies and their preference key names, see [Microsoft Edge browser policies reference](microsoft-edge-policies.md).</span></span> <span data-ttu-id="eb3a5-116">[Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)에서 다운로드할 수 있는 정책 템플릿 파일에는 **예제** 폴더에 plist 예제(*itadminexample.plist*)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-116">In the policy templates file, which can be downloaded from the [Microsoft Edge Enterprise landing page](https://aka.ms/EdgeEnterprise), there's an example plist (*itadminexample.plist*) in the **examples** folder.</span></span> <span data-ttu-id="eb3a5-117">이 예제 파일에는 정책 설정을 정의하기 위해 사용자 지정할 수 있는 모든 지원되는 데이터 형식이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-117">The example file contains all supported data types that you can customize to define your policy settings.</span></span> 

<span data-ttu-id="eb3a5-118">plist의 콘텐츠를 만든 후 다음 단계는 Microsoft Edge 기본 설정 도메인 *com.microsoft.Edge*를 사용하여 이름을 지정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-118">The next step after you create the contents of your plist, is to name it using the Microsoft Edge preference domain, *com.microsoft.Edge*.</span></span> <span data-ttu-id="eb3a5-119">이름은 대소문자를 구분하며, 모든 Microsoft Edge 채널에 적용되기 때문에 대상으로 하는 채널을 포함하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-119">The name is case sensitive and should not include the channel you are targeting because it applies to all Microsoft Edge channels.</span></span> <span data-ttu-id="eb3a5-120">plist 파일 이름은 **_com.microsoft.Edge.plist_** 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-120">The plist file name must be **_com.microsoft.Edge.plist_**.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="eb3a5-121">빌드 78.0.249.2부터 macOS의 모든 Microsoft Edge 채널이 **com.microsoft.Edge** 기본 설정 도메인에서 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-121">Starting with build 78.0.249.2, all Microsoft Edge channels on macOS read from the **com.microsoft.Edge** preference domain.</span></span> <span data-ttu-id="eb3a5-122">모든 이전 릴리스는 개발 채널용 **com.microsoft.Edge.Dev**와 같은 채널별 도메인에서 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-122">All prior releases read from a channel specific domain, such as **com.microsoft.Edge.Dev** for Dev channel.</span></span>

<span data-ttu-id="eb3a5-123">마지막 단계는 Microsoft Intune과 같은 선호하는 MDM 공급자를 사용하여 사용자의 Mac 장치에 plist를 배포하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-123">The last step is to deploy your plist to your users' Mac devices using your preferred MDM provider, such as Microsoft Intune.</span></span> <span data-ttu-id="eb3a5-124">자세한 지침은 [plist 배포](#deploy-your-plist)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-124">For instructions see [Deploy your plist](#deploy-your-plist).</span></span>

### <span data-ttu-id="eb3a5-125">터미널을 사용하여 구성 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="eb3a5-125">Create a configuration profile using Terminal</span></span>

1. <span data-ttu-id="eb3a5-126">터미널에서 다음 명령을 사용하여 데스크톱에 Microsoft Edge에 대한 plist를 기본 설정으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-126">In Terminal, use the following command to create a plist for Microsoft Edge on your desktop with your preferred settings:</span></span>

   ```cmd
   /usr/bin/defaults write ~/Desktop/com.microsoft.Edge.plist RestoreOnStartup -int 1
   ```

2. <span data-ttu-id="eb3a5-127">plist를 바이너리에서 일반 텍스트 형식으로 변환:</span><span class="sxs-lookup"><span data-stu-id="eb3a5-127">Convert the plist from binary to plain text format:</span></span>

   ```cmd
   /usr/bin/plutil -convert xml1 ~/Desktop/com.microsoft.Edge.plist
   ```
<span data-ttu-id="eb3a5-128">파일을 변환한 후에는 정책 데이터가 올바르고 구성 프로필에 원하는 설정이 포함되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-128">After converting the file verify that your policy data is correct and contains the settings you want for your configuration profile.</span></span>

> [!NOTE]
> <span data-ttu-id="eb3a5-129">키 값 쌍만 plist 또는 xml 파일의 콘텐츠에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-129">Only key value pairs should be in the contents of the plist or xml file.</span></span> <span data-ttu-id="eb3a5-130">파일을 Intune에 업로드하기 전에 \<plist> 및 \<dict> 값과 xml 헤더를 파일에서 모두 제거하세요.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-130">Prior to uploading your file into Intune remove all the \<plist> and \<dict> values, and xml headers from your file.</span></span> <span data-ttu-id="eb3a5-131">파일에는 키 값 쌍만 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-131">The file should only contain key value pairs.</span></span>

## <span data-ttu-id="eb3a5-132">plist 배포</span><span class="sxs-lookup"><span data-stu-id="eb3a5-132">Deploy your plist</span></span>

<span data-ttu-id="eb3a5-133">Microsoft Intune에는 macOS 플랫폼을 대상으로 하는 새 장치 구성 프로필을 만들고 *기본 설정 파일* 프로필 유형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-133">For Microsoft Intune create a new device configuration profile targeting the macOS platform and select the *Preference file* profile type.</span></span> <span data-ttu-id="eb3a5-134">기본 도메인 이름으로 **com.microsoft.Edge**를 대상으로 하고 plist를 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-134">Target **com.microsoft.Edge** as the preference domain name and upload your plist.</span></span> <span data-ttu-id="eb3a5-135">자세한 내용은 [Microsoft Intune을 사용하여 macOS 장치에 속성 목록 파일 추가](https://docs.microsoft.com/intune/configuration/preference-file-settings-macos)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-135">For more information see [Add a property list file to macOS devices using Microsoft Intune](https://docs.microsoft.com/intune/configuration/preference-file-settings-macos).</span></span>

<span data-ttu-id="eb3a5-136">Jamf의 경우 .plist 파일을 *사용자 지정 설정* 페이로드로 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-136">For Jamf upload the .plist file as a *Custom Settings* payload.</span></span>

## <span data-ttu-id="eb3a5-137">질문과 대답</span><span class="sxs-lookup"><span data-stu-id="eb3a5-137">Frequently Asked Questions</span></span>

### <span data-ttu-id="eb3a5-138">마스터 기본 설정을 사용하도록 Microsoft Edge를 구성할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="eb3a5-138">Can Microsoft Edge be configured to use master preferences?</span></span>

<span data-ttu-id="eb3a5-139">예, 마스터 기본 설정 파일을 사용하도록 Microsoft Edge를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-139">Yes, you can configure Microsoft Edge to use a master preferences file.</span></span>

<span data-ttu-id="eb3a5-140">마스터 기본 설정 파일을 사용하면 Microsoft Edge가 배포될 때 브라우저 사용자 프로필에 대한 기본 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-140">A master preferences file lets you configure default settings for a browser user profile when Microsoft Edge is deployed.</span></span> <span data-ttu-id="eb3a5-141">또한 마스터 기본 설정 파일을 사용하여 장치 관리 시스템에서 관리하지 않는 컴퓨터에서 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-141">You can also use a master preferences file to apply settings on computers that aren't managed by a device management system.</span></span> <span data-ttu-id="eb3a5-142">이러한 설정은 사용자가 브라우저를 처음 실행할 때 사용자 프로필에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-142">These settings are applied to the user’s profile the first time the user runs the browser.</span></span> <span data-ttu-id="eb3a5-143">사용자가 브라우저를 실행한 후에는 마스터 기본 설정 파일의 변경 내용이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-143">After the user runs the browser, changes to the master preferences file aren’t applied.</span></span> <span data-ttu-id="eb3a5-144">사용자는 브라우저에서 마스터 기본 설정에서 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-144">A user can change settings from the master preferences in the browser.</span></span> <span data-ttu-id="eb3a5-145">설정을 필수로 만들거나 브라우저를 처음 실행한 후 설정을 변경하려면 정책을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-145">If you want to make a setting mandatory or change a setting after the first run of the browser, you must use a policy.</span></span>

<span data-ttu-id="eb3a5-146">마스터 기본 설정 파일을 사용하면 다른 Chromium 기반 브라우저와 공유되는 항목과 Microsoft Edge에 고유한 항목을 포함하여 다양한 설정 및 기본 설정을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-146">A master preferences file lets you to customize many different settings and preferences for the browser, including those shared with other Chromium based browsers and specific to Microsoft Edge.</span></span>  <span data-ttu-id="eb3a5-147">마스터 기본 설정 파일을 사용하여 정책 관련 기본 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-147">Policy related preferences can be configured using the master preferences file.</span></span> <span data-ttu-id="eb3a5-148">정책이 설정되어 있고 해당 마스터 기본 설정 집합이 있는 경우 정책 설정이 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-148">In cases where a policy is set and there’s a corresponding master preference set, the policy setting takes precedence.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eb3a5-149">사용 가능한 기본 설정 중 일부는 Microsoft Edge 용어 및 명명 규칙과 일치하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-149">All the available preferences might not be consistent with Microsoft Edge terminology and naming conventions.</span></span>  <span data-ttu-id="eb3a5-150">이후 릴리스에서 이러한 기본 설정이 예상대로 계속 작동한다는 보장은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-150">There’s no guarantee that these preferences will continue to work as expected in future releases.</span></span> <span data-ttu-id="eb3a5-151">이후 버전에서 기본 설정이 변경되거나 무시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-151">Preferences might be changed or ignored in later versions.</span></span>

<span data-ttu-id="eb3a5-152">마스터 기본 설정 파일은 JSON 태그를 사용하여 서식 지정된 텍스트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-152">A master preferences file is a text file that’s formatted using JSON markup.</span></span> <span data-ttu-id="eb3a5-153">이 파일은 msedge.exe 실행 파일과 동일한 디렉터리에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-153">This file needs to be added to the same directory as the msedge.exe executable.</span></span> <span data-ttu-id="eb3a5-154">macOS에서의 시스템 수준 엔터프라이즈 배포인 경우 이 폴더는 일반적으로 “*~/Library/Application Support/Microsoft/Microsoft Edge Master Preferences*" 또는 "*/Library/Application Support/Microsoft/Microsoft Edge Master Preferences*”입니다.</span><span class="sxs-lookup"><span data-stu-id="eb3a5-154">For system wide enterprise deployments on macOS this is typically: “*~/Library/Application Support/Microsoft/Microsoft Edge Master Preferences*" or "*/Library/Application Support/Microsoft/Microsoft Edge Master Preferences*”.</span></span>

## <span data-ttu-id="eb3a5-155">기타 참조</span><span class="sxs-lookup"><span data-stu-id="eb3a5-155">See also</span></span>

- [<span data-ttu-id="eb3a5-156">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="eb3a5-156">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="eb3a5-157">Jamf를 사용한 macOS용 구성</span><span class="sxs-lookup"><span data-stu-id="eb3a5-157">Configure for macOS with Jamf</span></span>](configure-microsoft-edge-on-mac-jamf.md)
- [<span data-ttu-id="eb3a5-158">Windows용 구성</span><span class="sxs-lookup"><span data-stu-id="eb3a5-158">Configure for Windows</span></span>](configure-microsoft-edge.md)
- [<span data-ttu-id="eb3a5-159">Intune을 사용한 Windows용 구성</span><span class="sxs-lookup"><span data-stu-id="eb3a5-159">Configure for Windows with Intune</span></span>](configure-edge-with-intune.md)
