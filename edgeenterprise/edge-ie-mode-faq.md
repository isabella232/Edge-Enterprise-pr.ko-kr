---
title: IE 모드 FAQ
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 03/15/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: IE 모드가 포함된 Microsoft Edge에 대한 FAQ 및 문제 해결
ms.openlocfilehash: 565af265811e0e4814d82859f638ae9abcd0a014
ms.sourcegitcommit: ef30fe37d0d115af0d4402c9005f5d0d1ba54b6c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2021
ms.locfileid: "11431815"
---
# <a name="ie-mode-faq"></a>IE 모드 FAQ

이 문서는 Microsoft Edge 버전 77 이상에 대한 문제 해결 팁과 FAQ를 제공합니다.

> [!NOTE]
> 이 문서는 Microsoft Edge **안정**, **Beta** 및 **Dev** 채널 버전 77 이상에 적용됩니다.


## <a name="troubleshoot-ie-mode"></a>IE 모드 문제 해결

이 섹션의 정보를 사용하여 IE 모드 문제를 진단하고 해결합니다.

### <a name="internet-explorer-mode-diagnostic-information"></a>Internet Explorer 모드 진단 정보

Microsoft Edge 호환성 탭에서 Internet Explorer 모드 진단 정보를 볼 수 있습니다. 이 탭을 열려면 *edge://compat/iediagnostic*으로 이동합니다. 이 페이지에는 진단 메시지가 표시될 수 있습니다. 이 페이지는 다음 범주에 대한 구성 정보도 제공합니다.

- **레지스트리 키를 확인**. (확인에 실패한 경우에만 표시됨) 레지스트리에 Internet Explorer 통합이 올바르게 설정되어 있는지 확인합니다. 그렇지 않을 경우, 사용자는 **수정**을 클릭하여 문제를 해결할 수 있습니다.
- **Internet Explorer 모드**. 구성 및 OS를 기반으로 사용되는 API 버전을 표시합니다. 문제가 있는 경우 **Windows 업데이트**를 설치하라는 메시지가 표시될 수 있습니다.
- **Internet Explorer 모드 설정**. Internet Explorer 모드의 활성화 여부 및 구성 방법을 보여줍니다.
- **명령줄**. Microsoft Edge를 시작하는 데 사용되는 명령줄 문자열과 스위치를 표시합니다.
- **그룹 정책 설정**. IE 모드가 그룹 정책과 적용되는 정책을 사용하여 구성되는지 여부를 표시합니다.

### <a name="error-message-to-open-this-page-in-internet-explorer-mode-reinstall-microsoft-edge-with-administrator-privileges"></a>오류 메시지: "이 페이지를 Internet Explorer 모드에서 열려면 관리자 권한으로 Microsoft Edge를 다시 설치하세요."

필수 Windows 업데이트가 모두 없는 경우 이 오류가 표시될 수 있습니다. 필요한 Windows 및 Microsoft Edge 버전에 대해서는 [IE 모드 정보](https://docs.microsoft.com/deployedge/edge-ie-mode)에 나열된 필수 구성 요소를 참조하세요.

필요한 모든 Windows Update를 이미 설치했다면 다음과 같은 경우에 이 오류가 표시될 수 있습니다.

- 기본적으로 사용자 수준으로 설치되는 Canary 채널을 사용하고 있습니다.
- Stable, Beta 또는 Dev 채널을 사용하고 있지만 설치할 때 권한 상승 프롬프트가 나타나면 권한 상승이 취소되었습니다. 권한 상승 프롬프트를 취소하면 설치는 사용자 수준에서 계속됩니다.
- Internet Explorer 11은 Windows 기능에서 사용하지 않도록 설정되었습니다.

가능한 해결 방법은 다음과 같습니다.

- 모든 채널에 대해 설치 프로그램을 시스템 수준에서 실행합니다. `installer.exe --system-level`
- Windows 기능에서 Internet Explorer 11을 사용 설정합니다.

Microsoft Edge가 시스템 수준에서 설치되어 있는지 확인하려면 Microsoft Edge 주소 표시줄에 "edge://version"을 입력합니다. 실행 파일 경로에 *C:\Program Files*로 시작하는 경로가 표시되면 이는 시스템 설치를 나타냅니다. 실행 파일 경로가 *C:\Users\*로 시작되는 경우 Microsoft Edge을 제거한 다음 관리자 권한으로 다시 설치합니다.

### <a name="error-message-to-open-this-page-in-ie-mode-try-restarting-microsoft-edge"></a>오류 메시지: "IE 모드에서 이 페이지를 열려면 Microsoft Edge를 다시 시작해 보세요."

Internet Explorer에 예기치 않은 오류가 있는 경우 이 오류가 표시될 수 있습니다. Microsoft Edge를 다시 시작하면 일반적으로 이 오류가 해결됩니다.

### <a name="error-message-turn-off-remote-debugging-to-open-this-site-in-ie-mode-otherwise-it-might-not-work-as-expected"></a>오류 메시지: "이 사이트를 IE 모드에서 열려면 원격 디버깅을 사용하지 않도록 설정하세요. 그렇지 않으면 예상대로 작동하지 않을 수 있습니다."

원격 디버깅을 하고 IE 모드에서 실행되도록 구성된 웹 페이지로 이동하면 이 오류가 표시될 수 있습니다. 계속할 수 있지만 페이지는 Microsoft Edge를 사용하여 렌더링됩니다.

### <a name="error-message-error-could-not-retrieve-emie-site-list"></a>오류 메시지: "오류: EMIE 사이트 목록을 검색할 수 없습니다."

*edge://compat/enterprise* 페이지에 사이트 목록을 다운로드하지 못했다는 이 오류가 표시될 수 있습니다. Microsoft Edge 버전 87부터 [BlockThirdPartyCookies](https://docs.microsoft.com/deployedge/microsoft-edge-policies#blockthirdpartycookies) 정책을 사용하여 타사 요청에 대해 쿠키가 차단된 경우 HTTP 인증도 허용되지 않습니다. 사이트 목록 다운로드가 성공적으로 진행되도록 [CookiesAllowedForURLs](https://docs.microsoft.com/deployedge/microsoft-edge-policies#cookiesallowedforurls) 정책을 사용하여 엔터프라이즈 모드 사이트 목록을 호스팅하는 특정 도메인에 대한 쿠키를 허용할 수 있습니다.

## <a name="frequently-asked-questions"></a>자주 묻는 질문

### <a name="will-ie-mode-replace-internet-explorer-11"></a>IE 모드가 Internet Explorer 11을 대체하나요?

Microsoft는 Internet Explorer를 안정적이고 안전한 브라우저로 계속 지원하기 위해 노력하고 있습니다. Internet Explorer는 여전히 Windows의 구성 요소이며 이 브라우저가 설치된 OS의 지원 수명 주기를 따릅니다. 자세한 내용은 [수명 주기 FAQ – Internet Explorer](https://support.microsoft.com/help/17454/)를 참조하세요. Microsoft에서 계속해서 Internet Explorer를 지원하고 업데이트하지만 최신 기능 및 플랫폼 업데이트는 Microsoft Edge에서만 사용할 수 있습니다.

### <a name="can-i-use-open-with-explorer-or-view-in-file-explorer-in-sharepoint-with-ie-mode"></a>IE모드 SharePoint에서 “탐색기로 오픈” 혹은 “파일 탐색기에서 보기”를 사용할 수 있나요?

예, 독립 Internet Explorer 11에서 작동하는 경우 IE 모드에서 작동합니다. 그러나 SharePoint 파일 및 폴더 관리를 위해 탐색기에서 열기 옵션을 사용하는 것 보다 [SharePoint 파일 동기화](https://support.office.com/en-us/article/sync-sharepoint-files-with-the-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88) 혹은 [SharePoint 파일 이동 혹은 복사](https://support.office.com/en-us/article/move-or-copy-files-in-sharepoint-00e2f483-4df3-46be-a861-1f5f0c1a87bc)를 추천합니다.

### <a name="does-ie-mode-on-microsoft-edge-support-the-nomerge-option-that-was-supported-in-internet-explorer-11"></a>Microsoft Edge의 IE 모드가 Internet Explorer 11에서 지원되었던 *nomerge* 옵션을 지원하나요?

Microsoft Edge에는 *nomerge* 옵션을 미러링하는 명시적인 명령줄이 없지만 이 기능을 제공하기 위해 권장하는 몇 가지 대안이 있습니다.

1. Microsoft Edge에서 프로필 사용 - 각 프로필은 IE 모드 페이지에 대해 서로 다른 IE 세션에 매핑되므로 *nomerge* 옵션과 동일하게 작동합니다.
2. `--user-data-dir=<path>` 명령줄을 사용하되 각 세션에 대해 다른 경로를 사용합니다. 필요한 경우, 사용자가 Microsoft Edge를 시작하고 세션의 경로를 변경하는 유틸리티를 만들 수 있습니다.

위의 옵션 중 사용자의 시나리오에 적합한 사항이 없는 경우 Microsoft 지원, [TechCommunity 포럼](https://techcommunity.microsoft.com/t5/enterprise/bd-p/EdgeInsiderEnterprise)와 같은 피드백 채널 중 하나를 통해 문의하세요.

### <a name="can-i-save-links-as-webpages-in-internet-explorer-mode"></a>Internet Explorer 모드에서 링크를 웹 페이지로 저장할 수 있나요?

예, Microsoft Edge의 Internet Explorer 모드용 바로 가기 메뉴에서 다른 이름으로 대상 저장 옵션을 활성화할 수 있습니다. 이렇게 하려면 *컴퓨터 설정 > 관리 템플릿 > Windows 구성 요소 > Internet Explorer*에서 *“Internet Explorer 모드에서 다른 이름으로 대상 저장 허용”* 을 그룹 정책으로 설정하세요.
저장 메커니즘은 Internet Explorer에서와 동일하게 작동하며, 대상이 html 파일로 저장되는 경우 파일을 다시 열면 Microsoft Edge에서 페이지가 렌더링됩니다.
 
이 기능을 사용하려면 다음과 같은 최소 운영 체제 업데이트가 필요합니다.
- Windows 10, 버전 2004, Windows Server 버전 2004, Windows 10, 버전 20H2 : [KB4580364](https://support.microsoft.com/help/4580364/windows-10-update-kb4580364)
- Windows 10, 버전 1903, Windows 10, 버전 1909, Windows Server 버전 1903: [KB4580386](https://support.microsoft.com/help/4580386/windows-10-update-kb4580386)
- Windows 10, 버전 1809, Windows Server 버전 1809, Windows Server 2019: [KB4580390](https://support.microsoft.com/help/4580390/windows-10-update-kb4580390)
- Windows 10, 버전 1803: [KB4586785](https://support.microsoft.com/help/4586785/windows-10-update-kb4586785)
- Windows 10, 버전 1607: [KB4586830](https://support.microsoft.com/help/4586830/windows-10-update-kb4586830)
- Windows 10, 버전 1507: [KB4586787](https://support.microsoft.com/help/4586787/windows-10-update-kb4586787)


## <a name="see-also"></a>참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [IE 모드 정보](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [추가 엔터프라이즈 모드 정보](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
