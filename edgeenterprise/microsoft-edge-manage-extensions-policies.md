---
title: 그룹 정책을 사용하여 Microsoft Edge 확장 관리
ms.author: aspoddar
author: AndreaLBarr
manager: balajek
ms.date: 06/09/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 엔터프라이즈에서 그룹 정책을 사용하여 Microsoft Edge 확장 관리
ms.openlocfilehash: a633b036c1733716dfb257b4711bca57bd6721f0
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2021
ms.locfileid: "11618218"
---
# <a name="use-group-policies-to-manage-microsoft-edge-extensions"></a><span data-ttu-id="382c7-103">그룹 정책을 사용하여 Microsoft Edge 확장 관리</span><span class="sxs-lookup"><span data-stu-id="382c7-103">Use group policies to manage Microsoft Edge extensions</span></span>

<span data-ttu-id="382c7-104">이 문서에서는 그룹 정책을 사용하여 확장을 관리하는 옵션과 단계를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-104">This article describes the options and steps for managing extensions by using group policies.</span></span> <span data-ttu-id="382c7-105">옵션은 귀하가 이미 사용자들을 위해 Microsoft Edge를 관리하는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-105">These options  assume that you already have Microsoft Edge managed for your users.</span></span> <span data-ttu-id="382c7-106">사용자가 Microsoft Edge를 관리할 수 있도록 아직 설정하지 않은 경우 아래 링크를 클릭하여 지금 관리하세요.</span><span class="sxs-lookup"><span data-stu-id="382c7-106">If you have not already set up Microsoft Edge to be managed for your users please follow the below link to do so now.</span></span>

- [<span data-ttu-id="382c7-107">엔터프라이즈에서 Microsoft Edge 확장 관리</span><span class="sxs-lookup"><span data-stu-id="382c7-107">Manage Microsoft Edge extensions in the enterprise</span></span>](/deployedge/microsoft-edge-manage-extensions)

> [!NOTE]
> <span data-ttu-id="382c7-108">이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-108">This article applies to Microsoft Edge version 77 or later.</span></span>

## <a name="block-extensions-based-on-their-permissions"></a><span data-ttu-id="382c7-109">사용 권한에 따라 확장 차단</span><span class="sxs-lookup"><span data-stu-id="382c7-109">Block extensions based on their permissions</span></span>

<span data-ttu-id="382c7-110">[ExtensionSettings](/deployedge/microsoft-edge-policies#extensionsettings) 정책을 사용하여 권한에 따라 사용자가 설치할 수 있는 확장을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-110">You can control what extensions your users can install based on permissions using the [ExtensionSettings](/deployedge/microsoft-edge-policies#extensionsettings) policy.</span></span> <span data-ttu-id="382c7-111">설치된 확장에서 차단된 사용 권한이 필요한 경우 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-111">If an installed extension needs a permission that’s blocked, it just won't run.</span></span> <span data-ttu-id="382c7-112">확장은 제거되지 않고 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-112">The extension isn't removed, just disabled.</span></span>

> [!NOTE]
> <span data-ttu-id="382c7-113">차단된 권한 설정은 확장 설정 정책 내에서만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-113">The blocked permissions setting can only be set within the extension settings policy.</span></span>  

<span data-ttu-id="382c7-114">확장을 차단하기 위한 지침으로 다음 단계를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-114">Use the following steps as a guide for blocking an extension.</span></span>

1. <span data-ttu-id="382c7-115">그룹 정책 관리 편집기를 열고 **관리 템플릿 > Microsoft Edge > 확장**으로 이동하고 **확장 관리 설정 구성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-115">Open the group policy management editor and go to **Administrative Templates > Microsoft Edge > Extensions**  and then select **Configure extension management settings**.</span></span>
2. <span data-ttu-id="382c7-116">정책을 실행한 다음 압축되는 JSON 문자열을 사용하여 허용하거나 차단할 사용 권한을 입력하세요.</span><span class="sxs-lookup"><span data-stu-id="382c7-116">Enable the policy, then enter the permissions that you want allowed or blocked, by using a JSON string that gets compressed.</span></span> <span data-ttu-id="382c7-117">다음 스크린샷은 권한 "usb"를 사용하는 확장을 차단하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-117">The next screenshot shows how to block an extension that uses the permission "usb".</span></span>

    :::image type="content" source="media/microsoft-edge-manage-extensions-policies/manage-extensions-gp-block-1.png" alt-text="확장을 차단하도록 그룹 정책을 구성합니다.":::

<span data-ttu-id="382c7-119">다음 예에서는 사용 권한 "usb"와 해당 압축 문자열을 사용해야 하는 확장을 차단하는 JSON을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-119">The following example shows the JSON to block any extension that needs the use of permission "usb" and its compressed string.</span></span>

### <a name="json-example"></a><span data-ttu-id="382c7-120">JSON 예제</span><span class="sxs-lookup"><span data-stu-id="382c7-120">JSON example</span></span>

   ```json
   { 
        "*": { 
             "blocked_permissions": ["usb"] 
        } 
   } 
   ```

   ```json
   {"*":{"blocked_permissions":["usb"]}} 
   ```

   > [!NOTE]
   > <span data-ttu-id="382c7-121">사용 권한을 사용하는 모든 확장을 차단하려면 이전 예와 같이 확장 ID에 별표를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="382c7-121">To block all extensions that use the permission, use an asterisk for the extension ID, as shown in the previous example.</span></span> <span data-ttu-id="382c7-122">확장 ID를 하나만 지정하면 정책이 해당 확장에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-122">If you specify one extension ID, the policy will only apply to that extension.</span></span> <span data-ttu-id="382c7-123">둘 이상의 항목을 차단할 수 있지만 이러한 항목은 별도의 항목이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-123">You can block more than one, but they need to be separate entries.</span></span>

## <a name="prevent-extensions-from-altering-web-pages"></a><span data-ttu-id="382c7-124">확장이 웹 페이지를 변경하지 못하도록 방지</span><span class="sxs-lookup"><span data-stu-id="382c7-124">Prevent extensions from altering web pages</span></span>

<span data-ttu-id="382c7-125">이 설정을 사용하면 확장이 중요한 웹 사이트 및 도메인의 데이터를 읽고 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-125">This setting prevents extensions from reading and changing  data from sensitive websites and domains.</span></span> <span data-ttu-id="382c7-126">웹 사이트에 대한 스크립트 삽입, 쿠키 읽기 또는 웹 요청 수정과 같은 작업을 차단하여 원치 않는 작업을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-126">Blocking unwanted actions is done by blocking actions such as script injection into your websites, reading the cookies, or making web-request modifications.</span></span> <span data-ttu-id="382c7-127">이 설정은 사용자가 확장을 설치하거나 제거할 수 없도록 하는 것이 아니라 확장이 지정된 웹 사이트를 변경하지 못하게 할 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-127">This setting doesn’t prevent your users from installing or removing extensions, it only prevents extensions from altering the specified websites.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="382c7-128">런타임 허용/차단된 호스트 설정은 확장 설정 정책 내에서만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-128">The Runtime allowed/blocked hosts setting can only be set within the extension settings policy.</span></span>  

<span data-ttu-id="382c7-129">웹 사이트 또는 도메인의 변경을 방지하거나 허용하도록 확장 설정 정책에서 다음 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-129">You can configure the following settings in the ExtensionSettings policy to prevent (or allow) alterations of websites or domains:</span></span>

- <span data-ttu-id="382c7-130">**Runtime_blocked_hosts**.</span><span class="sxs-lookup"><span data-stu-id="382c7-130">**Runtime_blocked_hosts**.</span></span> <span data-ttu-id="382c7-131">이 설정은 사용자가 지정한 웹 사이트에서 확장 기능을 변경하거나 데이터를 읽는 것을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-131">This setting blocks extensions from making changes or reading data from the websites you specify.</span></span>
- <span data-ttu-id="382c7-132">**Runtime_allowed_hosts**.</span><span class="sxs-lookup"><span data-stu-id="382c7-132">**Runtime_allowed_hosts**.</span></span> <span data-ttu-id="382c7-133">이 설정을 사용하면 사용자가 지정한 웹 사이트에서 확장자가 데이터를 변경하거나 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-133">This setting allows extensions to make changes or read data from the websites you specify.</span></span> <span data-ttu-id="382c7-134">정책의 JSON 문자열에서 사이트를 지정하는 데 사용되는 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-134">The following format is used for specifying your site(s) in the JSON string in the policy:</span></span>

  ```json
  [http|https|ftp|*]://[subdomain|*].[hostname|*].[eTLD|*] [http|https|ftp|*],
  ```

  > [!NOTE]
  > `[hostname|*], and [eTLD|*]` <span data-ttu-id="382c7-135">섹션이 필요하지만 `[subdomain|*]` 섹션은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-135">sections are required, but `[subdomain|*]` section is optional.</span></span>

<span data-ttu-id="382c7-136">다음 표에서는 유효한 호스트 패턴 및 일치 패턴의 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-136">The following table shows examples of valid host patterns and matching patterns.</span></span>

|<span data-ttu-id="382c7-137">유효한 호스트 패턴</span><span class="sxs-lookup"><span data-stu-id="382c7-137">Valid host patterns</span></span>|<span data-ttu-id="382c7-138">일치 항목</span><span class="sxs-lookup"><span data-stu-id="382c7-138">Matches</span></span>|<span data-ttu-id="382c7-139">일치하지 않음</span><span class="sxs-lookup"><span data-stu-id="382c7-139">Doesn't match</span></span>|
|--|--|--|
|  `*://*.example.*` | `http://example.com`<br>`https://test.example.co.uk`   | `https://example.microsoft.com`<br>`http://example.microsoft.co.uk`  |
| `http://example.*` | `http://example.com`<br>`http://example.ly` | `https://example.com`<br>`http://test.example.com`   |
| `http://example.com`   | `http://example.com` | `https://example.com`<br>`http://test.example.co.uk` |
| `*://*`   | <span data-ttu-id="382c7-140">모든 URL</span><span class="sxs-lookup"><span data-stu-id="382c7-140">All URLs</span></span>  |   |

<span data-ttu-id="382c7-141">다음 단계에 따라 웹 사이트 또는 도메인에 대한 확장을 차단하거나 허용할 수 있습니다..</span><span class="sxs-lookup"><span data-stu-id="382c7-141">Use the following steps as a guide to block or allow extensions to access a website or domain.</span></span>

1. <span data-ttu-id="382c7-142">그룹 정책 관리 편집기를 열고 **관리 템플릿 > Microsoft Edge > 확장**으로 이동하고 **확장 관리 설정 구성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-142">Open the group policy management editor and go to **Administrative Templates > Microsoft Edge > Extensions**, and then select **Configure extension management settings**.</span></span>  
2. <span data-ttu-id="382c7-143">정책을 실행한 다음 허용하거나 차단할 사용 권한을 입력하여 사용 권한을 단일 JSON 문자열로 압축하세요.</span><span class="sxs-lookup"><span data-stu-id="382c7-143">Enable the policy, then enter the permissions that you want allowed or blocked, compressing the permissions to a single JSON string.</span></span>

<span data-ttu-id="382c7-144">다음 예에서는 호스트 이름에서 확장을 차단하는 방법과 동일한 도메인에서 확장을 차단하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-144">The following examples show how to block extensions on a hostname and how to block extensions on the same domain.</span></span>

### <a name="json-example-to-block-hostname"></a><span data-ttu-id="382c7-145">호스트 이름을 차단하는 JSON 예제</span><span class="sxs-lookup"><span data-stu-id="382c7-145">JSON example to block hostname</span></span>

<span data-ttu-id="382c7-146">이 예에서는 확장자가 `www.microsoft.com` 호스트 이름에 액세스하지 못하도록 차단하는 JSON 및 압축 JSON 문자열을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-146">This example shows the JSON and compressed JSON string to block any extension from accessing the `www.microsoft.com` hostname.</span></span>

```json
{ 
    "*":{ 
            "runtime_blocked_hosts":["www.microsoft.com"] 
    } 
} 
```

```json
{"*":{"runtime_blocked_hosts":["www.microsoft.com"]}} 
```

> [!NOTE]
> <span data-ttu-id="382c7-147">모든 확장자가 웹 페이지에 액세스하지 못하도록 차단하려면 이전 예와 같이 확장 ID에 별표를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="382c7-147">To block all extensions from accessing a webpage, use an asterisk for the extension ID, as shown in the previous example.</span></span>  <span data-ttu-id="382c7-148">별표 대신 하나의 확장 ID를 지정하면 정책이 해당 확장에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-148">If you specify one extension ID instead of an asterisk, the policy will only apply to that extension.</span></span> <span data-ttu-id="382c7-149">둘 이상의 확장을 차단할 수 있지만 이러한 확장자는 별도의 항목이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-149">You can block more than one extension, but they need to be separate entries.</span></span>

### <a name="json-example-to-block-extensions-on-same-domain"></a><span data-ttu-id="382c7-150">동일한 도메인에서 확장을 차단하는 JSON 예제</span><span class="sxs-lookup"><span data-stu-id="382c7-150">JSON example to block extensions on same domain</span></span>

<span data-ttu-id="382c7-151">이 예에서는 특정 확장이 동일한 도메인 "중요 웹 사이트"에서 실행되지 않도록 차단하는 JSON 및 압축 JSON 문자열을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-151">This example shows the JSON and compressed JSON string to block specific extensions from running on the same domain, "importantwebsite".</span></span>

```json
{ 
    "aapbdbdomjkkjkaonfhkkikfgjllcleb": { 
        "runtime_blocked_hosts": ["*://*.importantwebsite"] 
    }, 
    "bfbmjmiodbnnpllbbbfblcplfjjepjdn": { 
        "runtime_blocked_hosts": ["*://*.importantwebsite"] 
    } 
} 
```

```json
{"aapbdbdomjkkjkaonfhkkikfgjllcleb": {"runtime_blocked_hosts": ["*://,*.importantwebsite"]},"bfbmjmiodbnnpllbbbfblcplfjjepjdn": {"runtime_blocked_hosts": ["*://*.importantwebsite"]}} 
```

## <a name="allow-or-block-extensions-in-group-policy"></a><span data-ttu-id="382c7-152">그룹 정책에서 확장 허용 또는 차단</span><span class="sxs-lookup"><span data-stu-id="382c7-152">Allow or block extensions in group policy</span></span>

<span data-ttu-id="382c7-153">[ExtensionInstallBlocklist](/DeployEdge/microsoft-edge-policies#extensioninstallblocklist) 및 [ExtensionInstallAllowlist](/DeployEdge/microsoft-edge-policies#extensioninstallallowlist) 정챗을 사용하여 차단되거나 허용된 확장을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-153">You can use the [ExtensionInstallBlocklist](/DeployEdge/microsoft-edge-policies#extensioninstallblocklist) and [ExtensionInstallAllowlist](/DeployEdge/microsoft-edge-policies#extensioninstallallowlist) policies to control which extensions are blocked or allowed.</span></span> <span data-ttu-id="382c7-154">다음 단계에 따라 차단할 확장을 제외한 모든 확장을 허용하세요.</span><span class="sxs-lookup"><span data-stu-id="382c7-154">Use the following steps as a guide to allow all extensions except those you want to block.</span></span>

1. <span data-ttu-id="382c7-155">그룹 정책 관리 편집기를 열고 **관리 템플릿 > Microsoft Edge > 확장 >** 으로 이동한 다음**설치할 수 없는 확장 제어**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-155">Open the group policy management editor and go to **Administrative Templates > Microsoft Edge > Extensions >** and then select **Control which extensions cannot be installed**.</span></span>
2. <span data-ttu-id="382c7-156">**사용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-156">Select **Enabled**.</span></span>
3. <span data-ttu-id="382c7-157">**표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-157">Click **Show**.</span></span>
4. <span data-ttu-id="382c7-158">차단할 확장의 앱 ID를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-158">Enter the app ID of the extensions that you want to block.</span></span> <span data-ttu-id="382c7-159">여러 개의 앱 ID를 추가할 경우 각 ID에 대해 별도의 행을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-159">When adding multiple app ID’s use a separate row for each ID.</span></span>
5. <span data-ttu-id="382c7-160">모든 확장을 차단하려면 정책에 **\*** 을(를) 입력하여 확장이 설치되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-160">To block all extensions, type **\*** into the policy to prevent any extensions from being installed.</span></span> <span data-ttu-id="382c7-161">특정 확장만 설치할 수 있도록 허용 정책과 함께 이 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-161">You can use this in conjunction with the "Allow specific extensions to be installed" policy to only allow certain extensions to be installed.</span></span> <span data-ttu-id="382c7-162">다음 스크린샷은 제공된 앱 ID를 기준으로 차단되는 확장을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-162">The next screenshot shows an extension that will be blocked based on the app ID that's provided.</span></span>

   :::image type="content" source="media/microsoft-edge-manage-extensions-policies/manage-extensions-gp-block-2.png" alt-text="앱 ID를 사용하여 확장을 차단합니다.":::

   > [!TIP]
   > <span data-ttu-id="382c7-164">확장의 앱 ID를 찾을 수 없는 경우 Microsoft Edge 추가 기능 웹 사이트에서 확장 기능을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="382c7-164">If you can’t find the app ID of an extension, look at the extension in the Microsoft Edge Add-ons website.</span></span> <span data-ttu-id="382c7-165">특정 확장자를 찾으면 옴니박스의 URL 끝에 앱 ID가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-165">Find the specific extension and you will see the app ID at the end of the URL in the omnibox.</span></span>

> [!NOTE]
> <span data-ttu-id="382c7-166">사용자의 시스템에 이미 설치된 차단 목록에 확장을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-166">You can add an extension to the blocklist that’s already installed on a user’s computer.</span></span> <span data-ttu-id="382c7-167">이렇게 하면 확장이 비활성화되고 사용자가 다시 활성화할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-167">This will disable the extension and prevent the user from re-enabling it.</span></span> <span data-ttu-id="382c7-168">제거되지 않고 비활성화만 됩니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-168">It won't be uninstalled, just disabled.</span></span>

## <a name="force-install-an-extension"></a><span data-ttu-id="382c7-169">확장 강제 설치</span><span class="sxs-lookup"><span data-stu-id="382c7-169">Force-install an extension</span></span>

<span data-ttu-id="382c7-170">[ExtensionInstallForcelist](/DeployEdge/microsoft-edge-policies#extensioninstallforcelist) 정책을 사용하여 차단되거나 허용되는 확장을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-170">Use the [ExtensionInstallForcelist](/DeployEdge/microsoft-edge-policies#extensioninstallforcelist) policy to control which extensions are blocked or allowed.</span></span> <span data-ttu-id="382c7-171">다음 단계에 따라 확장을 강제로 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-171">Use the following steps as a guide to force-install an extension.</span></span>

1. <span data-ttu-id="382c7-172">그룹 정책 편집기에서 **관리 템플릿 > Microsoft Edge > 확장 >** 으로 이동한 다음**자동으로 설치할 수 없는 확장 제어**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-172">In the Group Policy Editor, go to **Administrative Templates> Microsoft Edge >  Extensions >** and then select **Control which extensions are installed silently**.</span></span>
2. <span data-ttu-id="382c7-173">**사용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-173">Select **Enabled**.</span></span>  
3. <span data-ttu-id="382c7-174">**표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-174">Click **Show**.</span></span>
4. <span data-ttu-id="382c7-175">강제 설치할 확장의 앱 ID 또는 ID를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-175">Enter the app ID or IDs of the extension or extensions you want to force-install.</span></span>  

<span data-ttu-id="382c7-176">사용자가 개입할 필요 없이 확장이 자동으로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-176">The extension will be installed silently with no need for user interaction.</span></span> <span data-ttu-id="382c7-177">또한 사용자가 확장을 제거하거나 비활성화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-177">The user also won’t be able to uninstall or disable the extension.</span></span> <span data-ttu-id="382c7-178">이 설정은 사용하도록 설정된 모든 차단 목록 정책을 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-178">This setting will overwrite over any blocklist policy that’s enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="382c7-179">Chrome 웹 스토어에서 호스트되는 확장의 경우 `pckdojakecnhhplcgfflhndiffaohfah;https://clients2.google.com/service/update2/crx`와(과) 같은 문자열을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-179">For extensions hosted in the Chrome web store use a string such as: `pckdojakecnhhplcgfflhndiffaohfah;https://clients2.google.com/service/update2/crx`.</span></span>

## <a name="block-extensions-from-a-specific-store-or-update-url"></a><span data-ttu-id="382c7-180">특정 저장소 또는 업데이트 URL에서 확장 차단</span><span class="sxs-lookup"><span data-stu-id="382c7-180">Block extensions from a specific store or update URL</span></span>

<span data-ttu-id="382c7-181">저장소 또는 URL에서 확장을 차단하려면 [ExtensionSettings](/deployedge/microsoft-edge-policies#extensionsettings) 정책을 사용하여 해당 스토어에 대한 *update_url*만 차단하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-181">To block extensions from a particular store or URL, you only need to block the *update_url* for that store using the [ExtensionSettings](/deployedge/microsoft-edge-policies#extensionsettings) policy.</span></span>

<span data-ttu-id="382c7-182">다음 단계에 따라 특정 저장소 또는 URL의 확장을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-182">Use the following steps as a guide to block extensions from an particular store or URL.</span></span>

1. <span data-ttu-id="382c7-183">그룹 정책 관리 편집기를 열고 **관리 템플릿 > Microsoft Edge > 확장 >** 으로 이동하고 **확장 관리 설정 구성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-183">Open the group policy management editor and go to **Administrative Templates > Microsoft Edge > Extensions >** and then select **Configure extension management settings**.</span></span>  
2. <span data-ttu-id="382c7-184">정책을 실행한 다음 허용하거나 차단할 사용 권한을 입력하여 단일 JSON 문자열로 압축하세요.</span><span class="sxs-lookup"><span data-stu-id="382c7-184">Enable the policy, then enter the permissions that you want allowed or blocked, compressing it to a single JSON string.</span></span>

<span data-ttu-id="382c7-185">다음 예에서는 업데이트 URL(`https://clients2.google.com/service/update2/crx`)을 사용하여 Chrome 웹 스토어에서 차단할 JSON 및 압축 JSON 문자열을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-185">The next example shows the JSON and compressed JSON string to block from the Chrome Web Store using its update URL (`https://clients2.google.com/service/update2/crx`).</span></span>

### <a name="json-example-for-blocking-on-update-url"></a><span data-ttu-id="382c7-186">업데이트 URL 차단에 대한 JSON 예제</span><span class="sxs-lookup"><span data-stu-id="382c7-186">JSON example for blocking on update URL</span></span>

```json
{ 
"update_url:https://clients2.google.com/service/update2/crx":{ 
                                                             " installation_mode":"blocked" 
                                                             } 
} 
```

```json
{"update_url:https://clients2.google.com/service/update2/crx":{"installation_mode":"blocked"}} 
```

> [!NOTE]
> <span data-ttu-id="382c7-187">이전 예제의 JSON을 사용하여 스토어가 차단된 경우에도 **ExtensionInstallForcelist** 및 **ExtensionInstallAllowlist를** 사용하여 특정 확장을 허용/강제로 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="382c7-187">You can still use **ExtensionInstallForceList** and **ExtensionInstallAllowList** to allow/force install specific extensions even if the store is blocked using the JSON in the previous example.</span></span>

## <a name="see-also"></a><span data-ttu-id="382c7-188">참고 항목</span><span class="sxs-lookup"><span data-stu-id="382c7-188">See also</span></span>

- [<span data-ttu-id="382c7-189">엔터프라이즈에서 Microsoft Edge 확장 관리</span><span class="sxs-lookup"><span data-stu-id="382c7-189">Manage Microsoft Edge extensions in the enterprise</span></span>](microsoft-edge-manage-extensions.md)
- [<span data-ttu-id="382c7-190">Microsoft Edge 확장을 호스팅할 웹 저장소 만들기</span><span class="sxs-lookup"><span data-stu-id="382c7-190">Create a web store to host Microsoft Edge extensions</span></span>](microsoft-edge-manage-extensions-webstore.md)
- [<span data-ttu-id="382c7-191">ExtensionSettings 정책에 대한 참조 가이드</span><span class="sxs-lookup"><span data-stu-id="382c7-191">Reference guide for the ExtensionSettings policy</span></span>](microsoft-edge-manage-extensions-ref-guide.md)
- [<span data-ttu-id="382c7-192">Microsoft Edge 확장에 대한 FAQ</span><span class="sxs-lookup"><span data-stu-id="382c7-192">FAQ for Microsoft Edge Extensions</span></span>](microsoft-edge-manage-extensions-faq.md)
- [<span data-ttu-id="382c7-193">Microsoft Edge Enterprise 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="382c7-193">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
