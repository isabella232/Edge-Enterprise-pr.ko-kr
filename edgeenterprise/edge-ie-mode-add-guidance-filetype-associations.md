---
title: Internet Explorer 모드와 파일 확장명 연결
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 05/19/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Internet Explorer 모드와 파일 확장명 연결
ms.openlocfilehash: c027b11e426cd665cb9e6cc25b4c9f66a0c6762a
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2021
ms.locfileid: "11617458"
---
# <a name="associate-file-extensions-with-internet-explorer-mode"></a><span data-ttu-id="a2099-103">Internet Explorer 모드와 파일 확장명 연결</span><span class="sxs-lookup"><span data-stu-id="a2099-103">Associate file extensions with Internet Explorer mode</span></span>

>[!Note]
> <span data-ttu-id="a2099-104">Internet Explorer 11 데스크톱 응용 프로그램은 2022년 6월 15일 사용 및 지원이 중단됩니다(범위 내 항목 목록은 [FAQ 참고](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)).</span><span class="sxs-lookup"><span data-stu-id="a2099-104">The Internet Explorer 11 desktop application will be retired and go out of support on June 15, 2022 (for a list of what’s in scope, [see the FAQ](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)).</span></span> <span data-ttu-id="a2099-105">현재 사용하는 동일한 IE11 앱과 사이트는 Internet Explorer 모드에서 Microsoft Edge로 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2099-105">The same IE11 apps and sites you use today can open in Microsoft Edge with Internet Explorer mode.</span></span> <span data-ttu-id="a2099-106">[여기서 자세한 내용을 알아보세요](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/).</span><span class="sxs-lookup"><span data-stu-id="a2099-106">[Learn more here](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/).</span></span>

<span data-ttu-id="a2099-107">이 문서에서는 Microsoft Edge를 데스크톱 응용 프로그램용 파일 확장명과 Internet Explorer 모드와 연결하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a2099-107">This article explains how to associate Microsoft Edge with Internet Explorer mode with file extensions for desktop applications.</span></span>

> [!NOTE]
> <span data-ttu-id="a2099-108">이 문서는 Microsoft Edge 버전 86 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2099-108">This article applies to Microsoft Edge version 86 or later.</span></span>

## <a name="guidance-for-file-extension-association-with-internet-explorer-mode"></a><span data-ttu-id="a2099-109">Internet Explorer 모드와 파일 확장명 연결에 대한 지침</span><span class="sxs-lookup"><span data-stu-id="a2099-109">Guidance for file extension association with Internet Explorer mode</span></span>

<span data-ttu-id="a2099-110">다음 지침에서는 Microsoft Edge와 IE 모드를 .mht 파일 형식으로 연결하는 항목을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a2099-110">The following instructions show an entry that associates Microsoft Edge with IE mode with the .mht file type.</span></span> <span data-ttu-id="a2099-111">파일 연결 설정에 대한 지침으로 다음 단계를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a2099-111">Use the following steps as a guide for setting a file association.</span></span>

> [!NOTE]
> <span data-ttu-id="a2099-112">기본적으로 **기본 연결 구성 파일을 설정**하는 정책을 사용하여 특정 파일 확장명을 Internet Explorer 모드에서 열도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2099-112">You can set specific file extensions to open in Internet Explorer mode by default using the policy to **Set a default associations configuration file**.</span></span> <span data-ttu-id="a2099-113">자세한 내용은 [정책 CSP - ApplicationDefaults](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a2099-113">For more information, see [Policy CSP - ApplicationDefaults](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration).</span></span>

1. <span data-ttu-id="a2099-114">Internet Explorer 모드에서 여는 데 사용할 Microsoft Edge 채널로 새 ProgID를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a2099-114">Define a new ProgID with the Microsoft Edge channel to use to open with Internet Explorer mode.</span></span> <span data-ttu-id="a2099-115">ProgID에는 응용 프로그램 이름 및 아이콘과 msedge.exe에 대한 전체 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2099-115">The ProgID includes the application name and Icon and the full path to msedge.exe.</span></span>

```markdown
[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\Application]
"ApplicationCompany"="Microsoft Corporation"
"ApplicationName"="Microsoft Edge with IE Mode"
"ApplicationIcon"="C:\\<edge_installation_dir>\\msedge.exe,4"
"AppUserModelId"=""
```

```markdown
[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\DefaultIcon]
@="C:\\<edge_installation_dir>\\msedge.exe,4"
```

2. <span data-ttu-id="a2099-116">IE 모드에서 여는 데 필요한 명령줄을 전달하도록 셸 업데이트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a2099-116">Configure shell updates to pass the command line needed to open with IE mode.</span></span>

```markdown
[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\shell\open\command]
@="\"C:\\<edge_installation_dir>\\msedge.exe\" -ie-mode-file-url -- \"%1\""
```

3. <span data-ttu-id="a2099-117">마지막으로 .mht 파일 확장명을 새 ProgID와 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="a2099-117">Finally, associate the .mht file extension with a new ProgID.</span></span> <span data-ttu-id="a2099-118">값 형식이 REG_SZ인 ProgID를 값 이름으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a2099-118">Add your ProgID as a value name, with the value type of REG_SZ.</span></span>

```markdown
[HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\FileExts\.mht\OpenWithProgids]
"MSEdgeIEModeMHT"=hex(0):
```

<span data-ttu-id="a2099-119">앞의 예제에서 설명한 키를 설정한 후에는 사용자가 **다른 프로그램으로 열기** 메뉴에 추가 옵션을 표시하여 Microsoft Edge에서 \<channel\>IE 모드를 사용하여 .mht 파일을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2099-119">After you set the keys described in the previous example, your users will see an additional option on the **Open with** menu to open an .mht file using Microsoft Edge \<channel\> with IE mode.</span></span>

## <a name="registry-example"></a><span data-ttu-id="a2099-120">레지스트리 예제</span><span class="sxs-lookup"><span data-stu-id="a2099-120">Registry Example</span></span>

<span data-ttu-id="a2099-121">다음 코드 조각을 .reg 파일로 저장하고 레지스트리로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2099-121">You can save the following code snippet as a .reg file and import it into the registry.</span></span>

```markdown
Windows Registry Editor Version 5.00

[HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\FileExts\.mht\OpenWithProgids]
"MSEdgeIEModeMHT"=hex(0):

[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT]

[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\Application]
"ApplicationCompany"="Microsoft Corporation"
"ApplicationName"="Microsoft Edge with IE Mode"
"ApplicationIcon"="C:\\<edge_installation_dir>\\msedge.exe,4"
"AppUserModelId"=""

[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\DefaultIcon]
@="C:\\<edge_installation_dir>\\msedge.exe,4"

[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\shell]

[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\shell\open]

[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\shell\open\command]
@="\"C:\\<edge_installation_dir>\\msedge.exe\" -ie-mode-file-url -- \"%1\""

```

## <a name="configuring-file-types-to-open-in-internet-explorer-mode"></a><span data-ttu-id="a2099-122">파일 형식을 구성하여 Internet Explorer 모드로 열기</span><span class="sxs-lookup"><span data-stu-id="a2099-122">Configuring file types to open in Internet Explorer mode</span></span>

<span data-ttu-id="a2099-123">Edge 88부터 [상황에 맞는 메뉴를 표시하여 Internet Explorer 모드에서 링크 열기](./microsoft-edge-policies.md#internetexplorerintegrationreloadiniemodeallowed) 정책을 사용하여 특정 파일 형식 링크를 구성하고 Internet Explorer 모드에서 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2099-123">Starting Edge 88, you can configure specific file type links to open in Internet Explorer mode using the policy [Show context menu to open links in Internet Explorer mode](./microsoft-edge-policies.md#internetexplorerintegrationreloadiniemodeallowed).</span></span>

<span data-ttu-id="a2099-124">이 정책 [Internet Explorer 모드 파일 확장명 허용 목록에서 로컬 파일 열기](./microsoft-edge-policies.md#internetexplorerintegrationlocalfileextensionallowlist)에서 파일 확장명을 지정하여 이 옵션을 적용해야 하는 파일 형식을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2099-124">You can define file types this option should apply to, by specifying file extensions in this policy [Open local files in Internet Explorer mode file extension allow list](./microsoft-edge-policies.md#internetexplorerintegrationlocalfileextensionallowlist).</span></span> 

## <a name="see-also"></a><span data-ttu-id="a2099-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a2099-125">See also</span></span>

- [<span data-ttu-id="a2099-126">IE 모드 정보</span><span class="sxs-lookup"><span data-stu-id="a2099-126">About IE mode</span></span>](./edge-ie-mode.md)
- [<span data-ttu-id="a2099-127">구성 가능한 사이트 정보</span><span class="sxs-lookup"><span data-stu-id="a2099-127">Configurable sites information</span></span>](./edge-learnmore-configurable-sites-ie-mode.md)
- [<span data-ttu-id="a2099-128">추가 엔터프라이즈 모드 정보</span><span class="sxs-lookup"><span data-stu-id="a2099-128">Additional Enterprise Mode information</span></span>](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [<span data-ttu-id="a2099-129">파일 형식 연결 설정</span><span class="sxs-lookup"><span data-stu-id="a2099-129">Setting file type associations</span></span>](/windows/win32/shell/fa-file-types)
- [<span data-ttu-id="a2099-130">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="a2099-130">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)