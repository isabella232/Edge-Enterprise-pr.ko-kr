---
title: Windows 및 macOS에서 Microsoft Edge를 기본 브라우저로 설정
ms.author: brianalt
author: dan-wesley
manager: srugh
ms.date: 1/15/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge를 기본 브라우저로 설정하는 방법을 알아봅니다.
ms.openlocfilehash: 9151294c34cb2252a7fb32e660c1e3d9e64b5f76
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447762"
---
# <a name="set-microsoft-edge-as-the-default-browser"></a><span data-ttu-id="729ac-103">Microsoft Edge를 기본 브라우저로 설정</span><span class="sxs-lookup"><span data-stu-id="729ac-103">Set Microsoft Edge as the default browser</span></span>

<span data-ttu-id="729ac-104">이 문서에서는 Windows 및 macOS에서 Microsoft Edge를 기본 브라우저로 설정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-104">This article explains how you can set Microsoft Edge as the default browser on Windows and macOS.</span></span>

> [!NOTE]
> <span data-ttu-id="729ac-105">이 문서는 Windows 8 및 Windows 10에서 Microsoft Edge 버전 77 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-105">This article applies to Microsoft Edge version 77 or later on Windows 8 and Windows 10.</span></span> <span data-ttu-id="729ac-106">Windows 7 및 macOS의 경우 [Microsoft Edge를 기본 브라우저로 설정](./microsoft-edge-policies.md#defaultbrowsersettingenabled) 정책을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="729ac-106">For Windows 7 and macOS, see the [Set Microsoft Edge as default browser](./microsoft-edge-policies.md#defaultbrowsersettingenabled) policy.</span></span>

## <a name="introduction"></a><span data-ttu-id="729ac-107">소개</span><span class="sxs-lookup"><span data-stu-id="729ac-107">Introduction</span></span>

<span data-ttu-id="729ac-108">**기본 연결 구성 파일 설정** 그룹 정책 또는 [DefaultAssociationsConfiguration](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration) 모바일 디바이스 관리 설정을 사용하여 Microsoft Edge를 조직의 기본 브라우저로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-108">You can use the **Set a default associations configuration file** Group Policy or the [DefaultAssociationsConfiguration](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration) Mobile Device Management setting to set Microsoft Edge as the default browser for your organization.</span></span>

<span data-ttu-id="729ac-109">Microsoft Edge 안정을 html 파일, http/https 링크 및 PDF 파일에 대한 기본 브라우저로 설정하려면 다음 애플리케이션 연결 파일 예제를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-109">To set Microsoft Edge Stable as the default browser for html files, http/https links, and PDF files use the following application association file example:</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?>
<DefaultAssociations> 
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier=".html"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier=".htm"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier="http"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier="https"/>  
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgePDF" Identifier=".pdf"/>
</DefaultAssociations>
```

> [!NOTE]
> <span data-ttu-id="729ac-110">Microsoft Edge Beta를 기본 브라우저로 설정하려면 **ApplicationName**을 "Microsoft Edge Beta"로 설정하고 **ProgId**를 "MSEdgeBHTML"로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-110">To set Microsoft Edge Beta as the default browser, set **ApplicationName** to "Microsoft Edge Beta" and **ProgId** to "MSEdgeBHTML".</span></span> <span data-ttu-id="729ac-111">Microsoft Edge Dev를 기본 브라우저로 설정하려면 **ApplicationName**을 "Microsoft Edge Dev"로 설정하고 **ProgId**를 "MSEdgeDHTML"로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-111">To set Microsoft Edge Dev as the default browser, set **ApplicationName** to "Microsoft Edge Dev" and **ProgId** to "MSEdgeDHTML".</span></span>


> [!NOTE]
> <span data-ttu-id="729ac-112">대상 장치에 Microsoft Edge가 설치되어 있지 않으면 기본 파일 연결이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-112">The default file associations aren't applied if Microsoft Edge isn't installed on the target device.</span></span> <span data-ttu-id="729ac-113">이 시나리오에서는 사용자가 링크 또는 htm/html 파일을 열 때 기본 응용 프로그램을 선택하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-113">In this scenario, users are prompted to select their default application when they open a link or a htm/html file.</span></span>

## <a name="set-microsoft-edge-as-the-default-browser-on-domain-joined-devices"></a><span data-ttu-id="729ac-114">도메인 가입 장치에서 Microsoft Edge를 기본 브라우저로 설정</span><span class="sxs-lookup"><span data-stu-id="729ac-114">Set Microsoft Edge as the default browser on domain-joined devices</span></span>

<span data-ttu-id="729ac-115">**기본 연결 구성 파일 설정** 그룹 정책을 구성하여 도메인 가입 장치에서 Microsoft Edge를 기본 브라우저로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-115">You can set Microsoft Edge as the default browser on domain-joined devices by configuring the **Set a default associations configuration file** group policy.</span></span> <span data-ttu-id="729ac-116">이 그룹 정책을 켜면 기본 연결 구성 파일을 만들고 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-116">Turning this group policy on requires you to create and store a default associations configuration file.</span></span> <span data-ttu-id="729ac-117">이 파일은 로컬로 또는 네트워크 공유 위치에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-117">This file is stored locally or on a network share.</span></span> <span data-ttu-id="729ac-118">이 파일을 만드는 방법에 대한 자세한 내용은 [기본 응용 프로그램 연결 내보내기 또는 가져오기](/windows-hardware/manufacture/desktop/export-or-import-default-application-associations)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="729ac-118">For more information about creating this file, see [Export or Import Default Application Associations](/windows-hardware/manufacture/desktop/export-or-import-default-application-associations).</span></span>

### <a name="to-configure-the-group-policy-for-a-default-file-type-and-protocol-associations-configuration-file"></a><span data-ttu-id="729ac-119">기본 파일 형식 및 프로토콜 연결 구성 파일에 대한 그룹 정책을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="729ac-119">To configure the group policy for a default file type and protocol associations configuration file:</span></span>

1. <span data-ttu-id="729ac-120">그룹 정책 편집기를 열고 **Computer Configuration\Administrative Templates\Windows Components\File Explorer**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-120">Open the Group Policy editor and go to the **Computer Configuration\Administrative Templates\Windows Components\File Explorer**.</span></span>
2. <span data-ttu-id="729ac-121">**기본 연결 구성 파일**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-121">Select **Set a default associations configuration file**.</span></span>
3. <span data-ttu-id="729ac-122">**정책 설정**을 클릭한 다음 **사용**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-122">Click **policy setting**, and then click **Enabled**.</span></span>
4. <span data-ttu-id="729ac-123">**옵션**에서 기본 연결 구성 파일의 위치를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-123">Under **Options:**, type the location to your default associations configuration file.</span></span>
5. <span data-ttu-id="729ac-124">**확인**을 클릭하여 정책 설정을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-124">Click **OK** to save the policy settings.</span></span>

<span data-ttu-id="729ac-125">다음 스크린샷의 예제에서는 대상 장치에서 액세스할 수 있는 네트워크 공유에 있는 *appassoc.xml*이라는 연결 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-125">The example in the next screenshot shows an associations file named *appassoc.xml* on a network share that is accessible from the target device.</span></span>

   ![그룹 정책에서 파일 연결 사용](./media/edge-learnmore-make-edge-default-browser/edge-learnmore-app-associations.png)

   > [!NOTE]
   > <span data-ttu-id="729ac-127">이 설정이 사용하도록 설정되고 사용자의 장치가 도메인에 가입되는 경우 다음 번에 사용자가 로그인하면 연결 구성 파일이 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-127">If this setting is enabled and the user's device is domain-joined, the associations configuration file is processed the next time the user signs on.</span></span>

## <a name="set-microsoft-edge-as-the-default-browser-on-azure-active-directory-joined-devices"></a><span data-ttu-id="729ac-128">Azure Active Directory 가입 디바이스에서 Microsoft Edge를 기본 브라우저로 설정</span><span class="sxs-lookup"><span data-stu-id="729ac-128">Set Microsoft Edge as the default browser on Azure Active Directory joined devices</span></span>

<span data-ttu-id="729ac-129">Azure Active Directory 가입 디바이스에서 Microsoft Edge를 기본 브라우저로 설정하려면 다음 애플리케이션 연결 파일을 예제로 사용하여 [DefaultAssociationsConfiguration](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration) 모바일 디바이스 관리 설정의 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-129">To set Microsoft Edge as the default browser on Azure Active Directory joined devices follow the steps in the [DefaultAssociationsConfiguration](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration) Mobile Device Management setting using the following application association file as an example.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?>
<DefaultAssociations>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier=".html"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier=".htm"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier="http"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier="https"/>  
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgePDF" Identifier=".pdf"/>
</DefaultAssociations>
```

> [!NOTE]
> <span data-ttu-id="729ac-130">Microsoft Edge Beta를 기본 브라우저로 설정하려면 **ApplicationName**을 "Microsoft Edge Beta"로 설정하고 **ProgId**를 "MSEdgeBHTML"로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-130">To set Microsoft Edge Beta as the default browser, set **ApplicationName** to "Microsoft Edge Beta" and **ProgId** to "MSEdgeBHTML".</span></span> <span data-ttu-id="729ac-131">Microsoft Edge Dev를 기본 브라우저로 설정하려면 **ApplicationName**을 "Microsoft Edge Dev"로 설정하고 **ProgId**를 "MSEdgeDHTML"로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-131">To set Microsoft Edge Dev as the default browser, set **ApplicationName** to "Microsoft Edge Dev" and **ProgId** to "MSEdgeDHTML".</span></span>

## <a name="set-microsoft-edge-as-the-default-browser-on-macos"></a><span data-ttu-id="729ac-132">macOS에서 Microsoft Edge를 기본 브라우저로 설정</span><span class="sxs-lookup"><span data-stu-id="729ac-132">Set Microsoft Edge as the default browser on macOS</span></span>

<span data-ttu-id="729ac-133">프로그래밍 방식으로 macOS에서 기본 브라우저를 설정하려고 하면 최종 사용자에게 프롬프트가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-133">Attempting to programmatically set the default browser on macOS causes a prompt to appear for the end user.</span></span> <span data-ttu-id="729ac-134">이 프롬프트는 AppleScript를 사용해야만 자동화 할 수 있는 macOS 보안 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-134">This prompt is a macOS security feature that can only be automated away by using an AppleScript.</span></span>

<span data-ttu-id="729ac-135">이 제한으로 인해 macOS에서 Microsoft Edge를 기본 브라우저로 설정하는 두 가지 주요 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-135">Because of this limitation, there are two main methods for setting Microsoft Edge as the default browser on a macOS.</span></span> <span data-ttu-id="729ac-136">첫 번째 옵션은 Microsoft Edge가 이미 기본 브라우저로 설정된 macOS 이미지로 장치를 플래시하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-136">The first option is to flash the device with an image of macOS where Microsoft Edge has already been set as the default browser.</span></span> <span data-ttu-id="729ac-137">다른 옵션은  [Microsoft Edge를 기본 브라우저로 설정](./microsoft-edge-policies.md#defaultbrowsersettingenabled)  정책을 사용하여 Microsoft Edge를 기본값으로 설정하라는 메시지를 표시하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-137">The other option is to use the [Set Microsoft Edge as default browser](./microsoft-edge-policies.md#defaultbrowsersettingenabled) policy, which prompts the user to set Microsoft Edge as the default browser.</span></span>

<span data-ttu-id="729ac-138">이러한 방법 중 하나만 사용하는 경우에도 사용자가 기본 브라우저를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-138">When using either of these methods, it is still possible for a user to change the default browser.</span></span> <span data-ttu-id="729ac-139">보안상의 이유로 기본 브라우저 환경 설정을 프로그래밍 방식으로 차단할 수 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-139">This is because for security reasons, the default browser preference can’t be blocked programmatically.</span></span> <span data-ttu-id="729ac-140">이러한 이유로 Microsoft Edge를 기본 브라우저로 사용하여 이미지를 생성하더라도 \*\*Microsoft Edge를 기본 브라우저로 설정 \*\* 정책을 배포하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-140">For this reason, we recommend that you deploy the **Set Microsoft Edge as default browser** policy even if you create an image with Microsoft Edge as the default browser.</span></span> <span data-ttu-id="729ac-141">정책이 설정되고 다음에 Microsoft Edge를 열 때 사용자가 기본 브라우저를 Microsoft Edge에서 변경하면 기본 브라우저를 설정하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-141">If the policy is set and a user changes the default browser from Microsoft Edge the next time they open Microsoft Edge, they will be prompted to set it as the default.</span></span>

## <a name="see-also"></a><span data-ttu-id="729ac-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="729ac-142">See also</span></span>

- [<span data-ttu-id="729ac-143">Microsoft Edge 배포 계획</span><span class="sxs-lookup"><span data-stu-id="729ac-143">Plan your deployment of Microsoft Edge</span></span>](./deploy-edge-plan-deployment.md)
- [<span data-ttu-id="729ac-144">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="729ac-144">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="729ac-145">Microsoft Edge를 기본 브라우저로 설정(Windows 7 및 macOS)</span><span class="sxs-lookup"><span data-stu-id="729ac-145">Set Microsoft Edge as default browser (Windows 7 and macOS)</span></span>](./microsoft-edge-policies.md#defaultbrowsersettingenabled)
- [<span data-ttu-id="729ac-146">Windows 10 – IT 전문가를 위한 파일 연결을 구성하는 방법</span><span class="sxs-lookup"><span data-stu-id="729ac-146">Windows 10 – How to configure file associations for IT Pros?</span></span>](/archive/blogs/windowsinternals/windows-10-how-to-configure-file-associations-for-it-pros)
- [<span data-ttu-id="729ac-147">기본 애플리케이션 연결 내보내기 또는 가져오기</span><span class="sxs-lookup"><span data-stu-id="729ac-147">Export or Import Default Application Associations</span></span>](/windows-hardware/manufacture/desktop/export-or-import-default-application-associations)
  - [<span data-ttu-id="729ac-148">DISM 개요</span><span class="sxs-lookup"><span data-stu-id="729ac-148">DISM Overview</span></span>](/windows-hardware/manufacture/desktop/what-is-dism)
  - [<span data-ttu-id="729ac-149">DISM - 배포 이미지 서비스 및 관리</span><span class="sxs-lookup"><span data-stu-id="729ac-149">DISM - Deployment Image Servicing and Management</span></span>](/windows-hardware/manufacture/desktop/dism---deployment-image-servicing-and-management-technical-reference-for-windows)