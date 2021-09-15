---
title: Internet Explorer 모드와 파일 확장명 연결
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Internet Explorer 모드와 파일 확장명 연결
ms.openlocfilehash: 7efa30a6ec3013cf5b1595471f1fb91dca8bdfda
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "11980029"
---
# <a name="associate-file-extensions-with-internet-explorer-mode"></a>Internet Explorer 모드와 파일 확장명 연결

>[!Note]
> Internet Explorer 11 데스크톱 응용 프로그램은 2022년 6월 15일 사용 및 지원이 중단됩니다(범위 내 항목 목록은 [FAQ 참고](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)). 현재 사용하는 동일한 IE11 앱과 사이트는 Internet Explorer 모드에서 Microsoft Edge로 열 수 있습니다. [여기서 자세한 내용을 알아보세요](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/).

이 문서에서는 Microsoft Edge를 데스크톱 응용 프로그램용 파일 확장명과 Internet Explorer 모드와 연결하는 방법에 대해 설명합니다.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 86 이상에 적용됩니다.

## <a name="guidance-for-file-extension-association-with-internet-explorer-mode"></a>Internet Explorer 모드와 파일 확장명 연결에 대한 지침

다음 지침에서는 Microsoft Edge와 IE 모드를 .mht 파일 형식으로 연결하는 항목을 보여 줍니다. 파일 연결 설정에 대한 지침으로 다음 단계를 사용합니다.

> [!NOTE]
> 기본적으로 **기본 연결 구성 파일을 설정**하는 정책을 사용하여 특정 파일 확장명을 Internet Explorer 모드에서 열도록 설정할 수 있습니다. 자세한 내용은 [정책 CSP - ApplicationDefaults](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration)를 참조하세요.

1. Internet Explorer 모드에서 여는 데 사용할 Microsoft Edge 채널로 새 ProgID를 정의합니다. ProgID에는 응용 프로그램 이름 및 아이콘과 msedge.exe에 대한 전체 경로가 포함됩니다.

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

2. IE 모드에서 여는 데 필요한 명령줄을 전달하도록 셸 업데이트를 구성합니다.

```markdown
[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\shell\open\command]
@="\"C:\\<edge_installation_dir>\\msedge.exe\" -ie-mode-file-url -- \"%1\""
```

3. 마지막으로 .mht 파일 확장명을 새 ProgID와 연결합니다. 값 형식이 REG_SZ인 ProgID를 값 이름으로 추가합니다.

```markdown
[HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\FileExts\.mht\OpenWithProgids]
"MSEdgeIEModeMHT"=hex(0):
```

앞의 예제에서 설명한 키를 설정한 후에는 사용자가 **다른 프로그램으로 열기** 메뉴에 추가 옵션을 표시하여 Microsoft Edge에서 \<channel\>IE 모드를 사용하여 .mht 파일을 열 수 있습니다.

## <a name="registry-example"></a>레지스트리 예제

다음 코드 조각을 .reg 파일로 저장하고 레지스트리로 가져올 수 있습니다.

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

## <a name="configuring-file-types-to-open-in-internet-explorer-mode"></a>파일 형식을 구성하여 Internet Explorer 모드로 열기

Edge 88부터 [상황에 맞는 메뉴를 표시하여 Internet Explorer 모드에서 링크 열기](./microsoft-edge-policies.md#internetexplorerintegrationreloadiniemodeallowed) 정책을 사용하여 특정 파일 형식 링크를 구성하고 Internet Explorer 모드에서 열 수 있습니다.

이 정책 [Internet Explorer 모드 파일 확장명 허용 목록에서 로컬 파일 열기](./microsoft-edge-policies.md#internetexplorerintegrationlocalfileextensionallowlist)에서 파일 확장명을 지정하여 이 옵션을 적용해야 하는 파일 형식을 정의할 수 있습니다. 

## <a name="see-also"></a>참고 항목

- [IE 모드 정보](./edge-ie-mode.md)
- [구성 가능한 사이트 정보](./edge-learnmore-configurable-sites-ie-mode.md)
- [추가 엔터프라이즈 모드 정보](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [파일 형식 연결 설정](/windows/win32/shell/fa-file-types)
- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)