---
title: .plist를 사용하여 macOS용 Microsoft Edge 구성
ms.author: brianalt
author: kelleyvice-msft
manager: laurawi
ms.date: 11/30/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: .plist를 사용하여 macOS에서 Microsoft Edge 정책 설정 구성
ms.openlocfilehash: abe110ab3589cc9276f28590273ece2d372be3b8
ms.sourcegitcommit: ed6a5afabf909df87bec48671c4c47bcdfaeb7bc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2020
ms.locfileid: "11194692"
---
# <span data-ttu-id="d1031-103">.plist를 사용하여 macOS에서 Microsoft Edge 정책 설정 구성</span><span class="sxs-lookup"><span data-stu-id="d1031-103">Configure Microsoft Edge policy settings for macOS using a .plist</span></span>

<span data-ttu-id="d1031-104">이 문서에서는 속성 목록(.plist) 파일을 사용하여 macOS에서 Microsoft Edge를 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d1031-104">This article describes how to configure Microsoft Edge on macOS using a property list (.plist) file.</span></span> <span data-ttu-id="d1031-105">이 파일을 만든 다음 Microsoft Intune에 배포하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="d1031-105">You'll learn how to create this file and then deploy it to Microsoft Intune.</span></span>

<span data-ttu-id="d1031-106">자세한 내용은 [속성 목록 파일 정보](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html)(Apple의 웹 사이트) 및 [사용자 지정 페이로드 설정](https://support.apple.com/guide/mdm/custom-mdm9abbdbe7/1/web/1)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1031-106">For more information, see [About Information Property List Files](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) (Apple's website) and [Custom payload settings](https://support.apple.com/guide/mdm/custom-mdm9abbdbe7/1/web/1).</span></span>

> [!NOTE]
> <span data-ttu-id="d1031-107">이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1031-107">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="d1031-108">macOS에서 Microsoft Edge 설정 구성</span><span class="sxs-lookup"><span data-stu-id="d1031-108">Configure Microsoft Edge policies on macOS</span></span>

<span data-ttu-id="d1031-109">첫 번째 단계에서는 제출을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d1031-109">The first step is to create your plist.</span></span> <span data-ttu-id="d1031-110">임의의 텍스트 편집기를 사용하여 plist 파일을 만들거나 [터미널을 사용하여 구성 프로필을 만들](#create-a-configuration-profile-using-terminal) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1031-110">You can create the plist file with any text editor or you can use [Terminal to create the configuration profile](#create-a-configuration-profile-using-terminal).</span></span> <span data-ttu-id="d1031-111">하지만 사용자 대신 XML 코드의 서식을 지정하는 도구를 사용하여 plist 파일을 더 쉽게 만들고 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1031-111">However, it's easier to create and edit a plist file using a tool that formats the XML code for you.</span></span> <span data-ttu-id="d1031-112">*Xcode*는 다음 위치 중 하나에서 얻을 수 있는 무료 통합 개발 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="d1031-112">*Xcode* is a free integrated development environment that you can get from one of the following locations:</span></span>

- [<span data-ttu-id="d1031-113">Apple 개발자 웹 사이트</span><span class="sxs-lookup"><span data-stu-id="d1031-113">Apple developer website</span></span>](https://developer.apple.com/xcode/)
- [<span data-ttu-id="d1031-114">Mac App Store</span><span class="sxs-lookup"><span data-stu-id="d1031-114">Mac App Store</span></span>](https://apps.apple.com/app/xcode/id497799835?mt=12)

<span data-ttu-id="d1031-115">지원되는 정책 및 기본 설정 키 이름의 목록은 [Microsoft Edge 브라우저 정책 참조](microsoft-edge-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1031-115">For a list of supported policies and their preference key names, see [Microsoft Edge browser policies reference](microsoft-edge-policies.md).</span></span> <span data-ttu-id="d1031-116">[Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)에서 다운로드할 수 있는 정책 템플릿 파일에는 **예제** 폴더에 plist 예제(*itadminexample.plist*)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1031-116">In the policy templates file, which can be downloaded from the [Microsoft Edge Enterprise landing page](https://aka.ms/EdgeEnterprise), there's an example plist (*itadminexample.plist*) in the **examples** folder.</span></span> <span data-ttu-id="d1031-117">이 예제 파일에는 정책 설정을 정의하기 위해 사용자 지정할 수 있는 모든 지원되는 데이터 형식이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1031-117">The example file contains all supported data types that you can customize to define your policy settings.</span></span> 

<span data-ttu-id="d1031-118">plist의 콘텐츠를 만든 후 다음 단계는 Microsoft Edge 기본 설정 도메인 *com.microsoft.Edge*를 사용하여 이름을 지정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d1031-118">The next step after you create the contents of your plist, is to name it using the Microsoft Edge preference domain, *com.microsoft.Edge*.</span></span> <span data-ttu-id="d1031-119">이름은 대소문자를 구분하며, 모든 Microsoft Edge 채널에 적용되기 때문에 대상으로 하는 채널을 포함하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1031-119">The name is case sensitive and should not include the channel you are targeting because it applies to all Microsoft Edge channels.</span></span> <span data-ttu-id="d1031-120">plist 파일 이름은 **_com.microsoft.Edge.plist_** 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1031-120">The plist file name must be **_com.microsoft.Edge.plist_**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d1031-121">빌드 78.0.249.2부터 macOS의 모든 Microsoft Edge 채널이 **com.microsoft.Edge** 기본 설정 도메인에서 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="d1031-121">Starting with build 78.0.249.2, all Microsoft Edge channels on macOS read from the **com.microsoft.Edge** preference domain.</span></span> <span data-ttu-id="d1031-122">모든 이전 릴리스는 개발 채널용 **com.microsoft.Edge.Dev**와 같은 채널별 도메인에서 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="d1031-122">All prior releases read from a channel specific domain, such as **com.microsoft.Edge.Dev** for Dev channel.</span></span>

<span data-ttu-id="d1031-123">마지막 단계는 Microsoft Intune과 같은 선호하는 MDM 공급자를 사용하여 사용자의 Mac 장치에 plist를 배포하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d1031-123">The last step is to deploy your plist to your users' Mac devices using your preferred MDM provider, such as Microsoft Intune.</span></span> <span data-ttu-id="d1031-124">자세한 지침은 [plist 배포](#deploy-your-plist)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1031-124">For instructions see [Deploy your plist](#deploy-your-plist).</span></span>

### <span data-ttu-id="d1031-125">터미널을 사용하여 구성 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="d1031-125">Create a configuration profile using Terminal</span></span>

1. <span data-ttu-id="d1031-126">터미널에서 다음 명령을 사용하여 데스크톱에 Microsoft Edge에 대한 plist를 기본 설정으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d1031-126">In Terminal, use the following command to create a plist for Microsoft Edge on your desktop with your preferred settings:</span></span>

   ```cmd
   /usr/bin/defaults write ~/Desktop/com.microsoft.Edge.plist RestoreOnStartup -int 1
   ```

2. <span data-ttu-id="d1031-127">plist를 바이너리에서 일반 텍스트 형식으로 변환:</span><span class="sxs-lookup"><span data-stu-id="d1031-127">Convert the plist from binary to plain text format:</span></span>

   ```cmd
   /usr/bin/plutil -convert xml1 ~/Desktop/com.microsoft.Edge.plist
   ```

<span data-ttu-id="d1031-128">파일을 변환한 후에는 정책 데이터가 올바르고 구성 프로필에 원하는 설정이 포함되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d1031-128">After converting the file verify that your policy data is correct and contains the settings you want for your configuration profile.</span></span>

> [!NOTE]
> <span data-ttu-id="d1031-129">키 값 쌍만 plist 또는 xml 파일의 콘텐츠에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1031-129">Only key value pairs should be in the contents of the plist or xml file.</span></span> <span data-ttu-id="d1031-130">파일을 Intune에 업로드하기 전에 \<plist> 및 \<dict> 값과 xml 헤더를 파일에서 모두 제거하세요.</span><span class="sxs-lookup"><span data-stu-id="d1031-130">Prior to uploading your file into Intune remove all the \<plist> and \<dict> values, and xml headers from your file.</span></span> <span data-ttu-id="d1031-131">파일에는 키 값 쌍만 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1031-131">The file should only contain key value pairs.</span></span>

## <span data-ttu-id="d1031-132">plist 배포</span><span class="sxs-lookup"><span data-stu-id="d1031-132">Deploy your plist</span></span>

<span data-ttu-id="d1031-133">Microsoft Intune에는 macOS 플랫폼을 대상으로 하는 새 장치 구성 프로필을 만들고 *기본 설정 파일* 프로필 유형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1031-133">For Microsoft Intune create a new device configuration profile targeting the macOS platform and select the *Preference file* profile type.</span></span> <span data-ttu-id="d1031-134">기본 도메인 이름으로 **com.microsoft.Edge**를 대상으로 하고 plist를 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="d1031-134">Target **com.microsoft.Edge** as the preference domain name and upload your plist.</span></span> <span data-ttu-id="d1031-135">자세한 내용은 [Microsoft Intune을 사용하여 macOS 장치에 속성 목록 파일 추가](https://docs.microsoft.com/intune/configuration/preference-file-settings-macos)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1031-135">For more information see [Add a property list file to macOS devices using Microsoft Intune](https://docs.microsoft.com/intune/configuration/preference-file-settings-macos).</span></span>

<span data-ttu-id="d1031-136">Jamf의 경우 .plist 파일을 *사용자 지정 설정* 페이로드로 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="d1031-136">For Jamf upload the .plist file as a *Custom Settings* payload.</span></span>

## <span data-ttu-id="d1031-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d1031-137">See also</span></span>

- [<span data-ttu-id="d1031-138">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="d1031-138">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="d1031-139">Jamf를 사용한 macOS용 구성</span><span class="sxs-lookup"><span data-stu-id="d1031-139">Configure for macOS with Jamf</span></span>](configure-microsoft-edge-on-mac-jamf.md)
- [<span data-ttu-id="d1031-140">Windows용 구성</span><span class="sxs-lookup"><span data-stu-id="d1031-140">Configure for Windows</span></span>](configure-microsoft-edge.md)
- [<span data-ttu-id="d1031-141">Intune을 사용한 Windows용 구성</span><span class="sxs-lookup"><span data-stu-id="d1031-141">Configure for Windows with Intune</span></span>](configure-edge-with-intune.md)
