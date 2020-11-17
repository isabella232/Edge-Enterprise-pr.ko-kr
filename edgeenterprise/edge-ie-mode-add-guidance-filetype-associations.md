---
title: 다른 프로그램으로 열기 상황에 맞는 메뉴에 Internet Explorer 모드 추가
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 11/13/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 다른 프로그램으로 열기 상황에 맞는 메뉴에 Internet Explorer 모드 추가
ms.openlocfilehash: 6453cd2587e3bec10404d2491914debb999fcf3f
ms.sourcegitcommit: e3c80274a9b8ef15761c968214b3cba593476132
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2020
ms.locfileid: "11168491"
---
# “다른 프로그램으로 열기” 상황에 맞는 메뉴에 Internet Explorer 모드 추가

이 문서에서는 Microsoft Edge를 데스크톱 응용 프로그램용 파일 확장명과 Internet Explorer 모드와 연결하는 방법에 대해 설명합니다.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 86 이상에 적용됩니다.

## Internet Explorer 모드와 파일 확장명 연결에 대한 지침

다음 지침에서는 Microsoft Edge와 IE 모드를 .mht 파일 형식으로 연결하는 항목을 보여 줍니다. 파일 연결 설정에 대한 지침으로 다음 단계를 사용합니다.

> [!NOTE]
> 기본적으로 **기본 연결 구성 파일을 설정**하는 정책을 사용하여 특정 파일 확장명을 Internet Explorer 모드에서 열도록 설정할 수 있습니다. 자세한 내용은 [정책 CSP - ApplicationDefaults](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration)를 참조하세요.

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

## 레지스트리 예제

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

## 참고 항목

- [IE 모드 정보](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [구성 가능한 사이트 정보](https://docs.microsoft.com/deployedge/edge-learnmore-configurable-sites-ie-mode)
- [추가 엔터프라이즈 모드 정보](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [파일 형식 연결 설정](https://docs.microsoft.com/windows/win32/shell/fa-file-types)
- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
