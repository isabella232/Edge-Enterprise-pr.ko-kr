---
title: Internet Explorer 모드와 파일 확장명 연결
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 11/16/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Internet Explorer 모드와 파일 확장명 연결
ms.openlocfilehash: c80732239b911f7cd3d615e9ce1e480db2749f17
ms.sourcegitcommit: fc0ac6bb6655d1f6e2de7c838f275779cd7a5de6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2020
ms.locfileid: "11175181"
---
# <span data-ttu-id="0843c-103">Internet Explorer 모드와 파일 확장명 연결</span><span class="sxs-lookup"><span data-stu-id="0843c-103">Associate file extensions with Internet Explorer mode</span></span>

<span data-ttu-id="0843c-104">이 문서에서는 Microsoft Edge를 데스크톱 응용 프로그램용 파일 확장명과 Internet Explorer 모드와 연결하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0843c-104">This article explains how to associate Microsoft Edge with Internet Explorer mode with file extensions for desktop applications.</span></span>

> [!NOTE]
> <span data-ttu-id="0843c-105">이 문서는 Microsoft Edge 버전 86 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0843c-105">This article applies to Microsoft Edge version 86 or later.</span></span>

## <span data-ttu-id="0843c-106">Internet Explorer 모드와 파일 확장명 연결에 대한 지침</span><span class="sxs-lookup"><span data-stu-id="0843c-106">Guidance for file extension association with Internet Explorer mode</span></span>

<span data-ttu-id="0843c-107">다음 지침에서는 Microsoft Edge와 IE 모드를 .mht 파일 형식으로 연결하는 항목을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0843c-107">The following instructions show an entry that associates Microsoft Edge with IE mode with the .mht file type.</span></span> <span data-ttu-id="0843c-108">파일 연결 설정에 대한 지침으로 다음 단계를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0843c-108">Use the following steps as a guide for setting a file association.</span></span>

> [!NOTE]
> <span data-ttu-id="0843c-109">기본적으로 **기본 연결 구성 파일을 설정**하는 정책을 사용하여 특정 파일 확장명을 Internet Explorer 모드에서 열도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0843c-109">You can set specific file extensions to open in Internet Explorer mode by default using the policy to **Set a default associations configuration file**.</span></span> <span data-ttu-id="0843c-110">자세한 내용은 [정책 CSP - ApplicationDefaults](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0843c-110">For more information, see [Policy CSP - ApplicationDefaults](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration).</span></span>

1. <span data-ttu-id="0843c-111">Internet Explorer 모드에서 여는 데 사용할 Microsoft Edge 채널로 새 ProgID를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0843c-111">Define a new ProgID with the Microsoft Edge channel to use to open with Internet Explorer mode.</span></span> <span data-ttu-id="0843c-112">ProgID에는 응용 프로그램 이름 및 아이콘과 msedge.exe에 대한 전체 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0843c-112">The ProgID includes the application name and Icon and the full path to msedge.exe.</span></span>

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

2. <span data-ttu-id="0843c-113">IE 모드에서 여는 데 필요한 명령줄을 전달하도록 셸 업데이트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0843c-113">Configure shell updates to pass the command line needed to open with IE mode.</span></span>

```markdown
[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\shell\open\command]
@="\"C:\\<edge_installation_dir>\\msedge.exe\" -ie-mode-file-url -- \"%1\""
```

3. <span data-ttu-id="0843c-114">마지막으로 .mht 파일 확장명을 새 ProgID와 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="0843c-114">Finally, associate the .mht file extension with a new ProgID.</span></span> <span data-ttu-id="0843c-115">값 형식이 REG_SZ인 ProgID를 값 이름으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0843c-115">Add your ProgID as a value name, with the value type of REG_SZ.</span></span>

```markdown
[HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\FileExts\.mht\OpenWithProgids]
"MSEdgeIEModeMHT"=hex(0):
```

<span data-ttu-id="0843c-116">앞의 예제에서 설명한 키를 설정한 후에는 사용자가 **다른 프로그램으로 열기** 메뉴에 추가 옵션을 표시하여 Microsoft Edge에서 \<channel\>IE 모드를 사용하여 .mht 파일을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0843c-116">After you set the keys described in the previous example, your users will see an additional option on the **Open with** menu to open an .mht file using Microsoft Edge \<channel\> with IE mode.</span></span>

## <span data-ttu-id="0843c-117">레지스트리 예제</span><span class="sxs-lookup"><span data-stu-id="0843c-117">Registry Example</span></span>

<span data-ttu-id="0843c-118">다음 코드 조각을 .reg 파일로 저장하고 레지스트리로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0843c-118">You can save the following code snippet as a .reg file and import it into the registry.</span></span>

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

## <span data-ttu-id="0843c-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0843c-119">See also</span></span>

- [<span data-ttu-id="0843c-120">IE 모드 정보</span><span class="sxs-lookup"><span data-stu-id="0843c-120">About IE mode</span></span>](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [<span data-ttu-id="0843c-121">구성 가능한 사이트 정보</span><span class="sxs-lookup"><span data-stu-id="0843c-121">Configurable sites information</span></span>](https://docs.microsoft.com/deployedge/edge-learnmore-configurable-sites-ie-mode)
- [<span data-ttu-id="0843c-122">추가 엔터프라이즈 모드 정보</span><span class="sxs-lookup"><span data-stu-id="0843c-122">Additional Enterprise Mode information</span></span>](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [<span data-ttu-id="0843c-123">파일 형식 연결 설정</span><span class="sxs-lookup"><span data-stu-id="0843c-123">Setting file type associations</span></span>](https://docs.microsoft.com/windows/win32/shell/fa-file-types)
- [<span data-ttu-id="0843c-124">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="0843c-124">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
