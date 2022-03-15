---
title: Internet Explorer(IE) 모드 문제 해결 및 FAQ
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 01/18/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 사용 모드에 대한 문제 해결 Microsoft Edge Internet Explorer FAQ
ms.openlocfilehash: 064174744dbdc8d16912e4c196a8974c243de732
ms.sourcegitcommit: 556aca8dde42dd66364427f095e8e473b86651a0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2022
ms.locfileid: "12445682"
---
# <a name="internet-explorer-ie-mode-troubleshooting-and-faq"></a>Internet Explorer(IE) 모드 문제 해결 및 FAQ

> [!NOTE]
> 11 데스크톱 Internet Explorer 사용이 중지되어 2022년 6월 15일에는 지원이 중지됩니다. 범위에 있는 항목의 목록을 보시고, Internet Explorer 데스크톱 앱 사용 중지 [FAQ를 참조하세요](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549). 현재 사용하는 동일한 IE11 앱과 사이트는 Internet Explorer 모드에서 Microsoft Edge로 열 수 있습니다. 자세한 내용은 Internet Explorer Windows 10 블로그 게시물[에](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/) Microsoft Edge 참조하세요.

이 문서에서는 Microsoft Edge 버전 77 이상에 대한 문제 해결 팁과 FAQ를 제공합니다.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.

## <a name="what-if-i-need-help-with-setting-up-microsoft-edge-or-internet-explorer-mode"></a>Microsoft Edge 또는 Internet Explorer 설정하는 데 도움이 필요한 경우 어떻게 Internet Explorer 있나요?

다양한 지원 옵션을 제공합니다. 이 Microsoft 통합 지원 전환에 대한 지원을 위해 해당 지원 서비스에 도움을 줄 수 있습니다. 또한 유료  [FastTrack](https://www.microsoft.com/en-us/fasttrack/microsoft-365/microsoft-edge?rtc=1) 수가 150명 이상인 고객에게는 추가 요금을 지불하지 Windows 10.

또한 Microsoft Edge + Internet Explorer 모드 시작 [가이드](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RWEHMs)와 [IE 모드 블로그 시리즈도 권장됩니다](https://techcommunity.microsoft.com/t5/windows-10/internet-explorer-to-microsoft-edge-with-ie-mode-blog-series/m-p/2617124).

## <a name="common-ie-mode-issues"></a>일반적인 IE 모드 문제

이 섹션을 가이드로 사용하여 IE 모드로 전환할 때 가장 일반적인 두 가지 문제를 Microsoft Edge 도움이 됩니다. 이러한 문제는 다음입니다.

- 잘못된 문서 모드 구성
- 불완전한 중립 사이트 구성

### <a name="incorrect-document-mode-configurations"></a>잘못된 문서 모드 구성

이 섹션에서는 증상에 대해 설명하고 이 문제를 진단하고 해결하는 단계를 제공합니다.

#### <a name="symptoms"></a>증상

사용자는 다음과 같은 증상을  경험하게 됩니다.
  
- 페이지 요소의 크기 조정 및 위치가 꺼지거나 누락될 수 있습니다. 
- 일부 기능이 손실되거나 예상대로 작동하지 않을 수 있습니다. 예를 들어 작업한 단추는 Internet Explorer 작업을 하지 않습니다. 또는 오류를 반환하지 않습니다.

#### <a name="how-to-troubleshoot-and-fix"></a>문제 해결 방법

일반적인 전략은 IE 모드 사이트 목록의 특정 사이트에 대해 Internet Explorer 11과 동일한 설정을 복제하는 것입니다. 다음 스크린샷에 표시된 IE 11의 F12 개발자 도구 모음 "에뮬ATION" 탭을 사용하여 수정할 시나리오를 조사합니다. 개발자 도구 모음을 열기 위해 F12 키를 누운 다음 **DevTools 열기 를 선택합니다**.

![DevTools 보기의 에뮬ation 탭](./media/edge-ie-mode-faq/edge-ie-mode-emulation-tab.png)

에뮬ation 탭에는 집중할 두 가지 정보, 문서 모드(1) 및 드롭다운 목록 아래의 텍스트(2)가 표시됩니다. 이 정보는 현재 보고 있는 페이지 또는 사이트의 11(기본값) 모드에 있는 이유를 설명하는 데 도움이 될 수 있습니다.

문서 모드에 대해 표시할 수 있는 메시지는 서로 다르며 이 예제에서는 다음과 같습니다.
  
- X-UA 호환 메타 태그를 통해
- X-UA 호환 HTTP 헤더를 통해

두 가지 X-UA 호환 옵션은 사이트가 호스팅되는 웹 서버 또는 웹 서버가 브라우저에서 사용할 문서 모드를 표시하고 있는 것을 나타냅니다.  

거의 모든 경우에 문서 모드를 사용하려는 경우 이를 위해 사이트의 IE 모드 사이트 목록 항목에서 다음 모드 중 하나를 선택해야 합니다.

- Default
- IE8 Enterprise
- IE7 Enterprise

이러한 옵션은 웹 페이지 또는 웹 서버 지시문을 존중합니다. 지정한 문서 모드를 포함하는 옵션을 선택해야 합니다. 스크린샷 예제에서는 지정된 문서 모드가 11이기 때문에 IE8 Enterprise 및 IE7 Enterprise IE 11 문서 모드를 지원하지 Enterprise "기본값"을 선택합니다.  

문서 모드가 사이트에 다음 호환성 보기 중 하나가 필요하다고 나타내는 경우 구성 설정은 간단합니다.

- 로컬 호환성 보기 설정을 통해
- 호환성 보기 목록을 통해
- 인트라넷 호환성 설정을 통해

모든 호환성 보기 설정은 "IE7 Enterprise" 동작으로 이어지기 때문에 IE 모드 사이트 목록 항목의 "호환 모드" 섹션에서 이 설정을 선택합니다.

IE 모드 또는 IE 모드가 Internet Explorer 모드로 전환하는 데 사용하는 논리에 대한 자세한 내용은 사용되지 않습니다. 문서 모드 및 11에서는 더 이상 사용 [되지 Internet Explorer 문서를 참조](/internet-explorer/ie11-deploy-guide/deprecated-document-modes) 하세요.

일반적인 규칙은 특정 사이트가 예상대로 작동할 수 있는 가장 최근 논리 기반 모드를 사용하는 것입니다. 기본 모드로 시작하여 IE8 Enterprise 모드로 이동한 다음 필요한 경우 IE7 Enterprise 모드로 전환합니다. 이 선택을 통해 하위 페이지에서 특정 요구에 대한 기본 제공 논리를 통해 필요한 경우 다양한 문서 모드를 유연하게 사용할 수 있습니다. 따라서 모든 웹 사이트 페이지가 하나의 특정 문서 모드로 잠겨 있지 않습니다.  

다음 표에는 이러한 설정에 사용할 수 있는 문서 모드가 나열되어 있습니다.

| 논리 기반 모드 | Default | IE8 Enterprise | IE7 Enterprise |
|--|--|--|--|
| 사용 가능한 문서 모드 | IE11 Doc 모드<br> IE10 Doc 모드<br>IE9 Doc 모드<br> IE8 Doc 모드<br>IE7 Doc 모드<br>IE5 Quirks 모드 | IE8 Doc 모드<br>IE7 Doc 모드<br>IE5 Quirks 모드   | IE7 Doc 모드<br>IE5 Quirks 모드  |

> [!NOTE]
> 경우에 따라 특정 사이트 또는 페이지에서 특정 문서 모드가 디자인된 것으로 작동해야 하는 경우도 있습니다. 논리 기반 옵션이 유효하지 않은 경우 명시적 문서 모드 옵션을 사용하는 것이 좋습니다.

### <a name="incomplete-neutral-site-configurations"></a>불완전한 중립 사이트 구성

이 섹션에서는 증상에 대해 설명하고 이 문제를 진단하고 해결하는 단계를 제공합니다.

#### <a name="symptoms"></a>증상
  
페이지에는 인증을 위해 SSO가 사용되지만 자격 증명을 입력하라는 메시지가 여러 번 표시되거나, 반복 리디렉션 동작이 발생하거나, 인증 오류가 발생하거나, 이러한 증상이 일부 조합된 경우도 있습니다.
  
#### <a name="how-to-troubleshoot-and-fix"></a>문제 해결 방법
  
오류 워크플로를 분석하기 전에 Microsoft Edge 스크린샷에 표시된 IE 모드 "e" 로고의 주소 표시줄을 살펴보아야 합니다.

![메뉴 표시줄의 Microsoft Edge IE 로고입니다.](./media/edge-ie-mode-faq/edge--ie-mode-logo.png)

SSO 인증 프로세스 중에 "e"가 표시되지만 리디렉션 후에 사라지면 이 동작은 누락된 중립 사이트를 참조합니다. IE Microsoft Edge 드롭다운한 후 세션 및 쿠키 정보를 유지 관리하기 위해 계속 유지해야 합니다. URL이 식별할 수 있을 만큼 긴 주소 표시줄에 표시되면 중립 사이트 구성에 설명된 단계를 사용하여 IE 모드 사이트 목록에 중립 사이트로 추가 [합니다](/deployedge/edge-ie-mode-sitelist#configure-neutral-sites).

종종 리디렉션 주기가 너무 빨리 발생하여 누락된 중립 사이트를 식별하기가 어렵습니다. 이 분석을 지원하기 위해 Chromium 엔진인 **net-export**에 기본 제공되는 도구를 사용합니다.

> [!TIP]
> 네트워크 추적은 본질적으로 시요됩니다. 노이즈를 최소화하려면 조사하는 특정 워크플로에 필요하지 않은 다른 모든 브라우저 인스턴스 및 탭을 닫습니다.

다음 단계에서는 중립 사이트 구성 문제를 해결하는 방법을 설명합니다.
  
1. 새 탭을 열고 Microsoft Edge 탭으로 *edge://net-export*.
2. 디스크 **에 로**깅 시작을 선택한 다음 결과 .json 로그를 저장할 위치를 선택합니다. 문제 해결을 완료한 후 이 로그를 안전하게 삭제할 수 있습니다.
3. 다른 탭을 열고(net-export 탭을 열어 두고) 실패한 워크플로를 반복합니다.
4. 작업을 마친 후 net-export 탭으로 돌아가 로깅 **중지를 선택합니다**.
5. "netlog viewer" 하이퍼링크를 선택합니다.
6. 결과 페이지에서 파일 선택 **을 선택한 다음** 2단계에서 만든 .json 파일을 선택합니다.
7. 로그 파일이 로드된 후 왼쪽 메뉴에서 이벤트를 **** 선택합니다.
8. 네트워크 로그를 스크롤하여 시작 URL을 식별합니다. 검색 함수를 사용하여 시작점을 찾을 수도 있습니다.
9. 시작점에서 아래로 스크롤하여 IE 모드 사이트 목록에 항목이 없는 URL을 워크플로에서 찾아 갑니다. SSO, AUTH, LOGIN에 대한 표시기가 있는 URL에 특히 주의해야 합니다.
10. 후보 URL을 식별한 후 열기 드롭다운에서 없음을 선택하여 IE 모드 사이트 목록에 중립 사이트로 추가 **** 합니다. 워크플로를 다시 테스트합니다.

경우에 따라 특정 사이트 아키텍처에 따라 여러 개의 중립 사이트 항목이 필요한 경우도 있습니다. 새 중립 사이트를 추가한 후에도 워크플로가 계속 실패하면 프로세스를 반복하여 새 net-export 로그를 캡처하고 다른 단계를 수행하십시오.

드물지만 IE 모드 사이트에 필요한 정보가 제공되도록 특정 공유 쿠키를 구성해야 할 수도 있습니다. 필요한 특정 쿠키를 알고 있는 경우 쿠키 공유에 설명된 단계를 사용하여 쿠키 공유를 구성할 Microsoft Edge [Internet Explorer](/deployedge/edge-ie-mode-add-guidance-cookieshare).

### <a name="what-if-these-steps-dont-fix-the-issue"></a>이러한 단계로 문제가 해결되지 않는 경우 어떻게 하나요?

이 문서는 가장 일반적인 IE 모드 구성 문제를 해결하는 데 도움이 되지만 가능한 모든 시나리오를 다루지는 않을 수 있습니다. If you run into an issue that you can't fix and need help with, contact App Assure at [https://aka.ms/AppAssure](https://aka.ms/AppAssure) and we'll help you with your problem.

## <a name="get-general-diagnostic-and-configuration-information"></a>일반 진단 및 구성 정보 확인

Microsoft Edge 호환성 탭에서 Internet Explorer 모드 진단 정보를 볼 수 있습니다. 이 탭을 열려면 *edge://compat/iediagnostic*으로 이동합니다. "Internet Explorer 모드 진단 정보" 페이지에 진단 메시지가 표시될 수 있으며 진단 데이터를 xml 파일로 내보낼 수 있습니다. 이 진단 정보 페이지에서는 다음 범주에 대한 구성 정보도 제공합니다.

- **레지스트리 키를 확인.** (확인에 실패한 경우에만 표시됨) 레지스트리에 Internet Explorer 통합이 올바르게 설정되어 있는지 확인합니다. 그렇지 않은 경우 사용자는 수정을 **선택하여** 문제를 해결할 수 있습니다.
- **Internet Explorer 모드.** 구성 및 OS를 기반으로 사용되는 API 버전을 표시합니다. 문제가 있는 경우 Windows 업데이트를 설치하라는 메시지가 표시될 수 있습니다.
- **Internet Explorer 모드 설정.** Internet Explorer 모드의 활성화 여부 및 구성 방법을 보여줍니다.
- **명령줄.** 명령줄 문자열과 명령줄 문자열을 시작하는 데 사용되는 스위치를 Microsoft Edge.
- **그룹 정책 설정.** IE 모드가 그룹 정책과 적용되는 정책을 사용하여 구성되는지 여부를 표시합니다.

### <a name="error-message-to-open-this-page-in-internet-explorer-mode-reinstall-microsoft-edge-with-administrator-privileges"></a>오류 메시지: "이 페이지를 Internet Explorer 모드에서 열려면 관리자 권한으로 Microsoft Edge를 다시 설치하세요."

업데이트에 필요한 모든 업데이트가 없는 경우 이 Windows 있습니다. 필요한 Windows 및 Microsoft Edge 버전에 대해서는 [IE 모드 정보](./edge-ie-mode.md)에 나열된 필수 구성 요소를 참조하세요.

필요한 모든 Windows 업데이트를 이미 설치한 경우 다음과 같은 경우 이 오류가 표시될 수 있습니다.

- 기본적으로 사용자 수준으로 설치되는 Canary 채널을 사용하고 있습니다.
- Stable, Beta 또는 Dev 채널을 사용하고 있지만 설치할 때 권한 상승 프롬프트가 나타나면 권한 상승이 취소되었습니다. 권한 상승 프롬프트를 취소하면 설치는 사용자 수준에서 계속됩니다.
- Internet Explorer 11은 Windows 기능에서 사용하지 않도록 설정되었습니다.

가능한 해결 방법:

- 모든 채널에 대해 설치 프로그램을 시스템 수준에서 실행합니다. `installer.exe --system-level`
- Windows 기능에서 Internet Explorer 11을 사용 설정합니다.

Microsoft Edge가 시스템 수준에서 설치되어 있는지 확인하려면 Microsoft Edge 주소 표시줄에 "edge://version"을 입력합니다. 실행 파일 경로에 *C:\Program Files*로 시작하는 경로가 표시되면 이는 시스템 설치를 나타냅니다. 실행 경로가 *C:\Users*로 시작하는 경우 관리자 권한으로 Microsoft Edge 다시 설치합니다.

### <a name="error-message-to-open-this-page-in-ie-mode-try-restarting-microsoft-edge"></a>"이 페이지를 IE 모드로 열기 위해 이 페이지를 다시 Microsoft Edge." 오류 메시지가 표시됩니다.

오류 발생 시 예기치 않은 오류가 발생하면 이 오류가 Internet Explorer. Microsoft Edge를 다시 시작하면 일반적으로 이 오류가 해결됩니다.

### <a name="error-message-turn-off-remote-debugging-to-open-this-site-in-ie-mode-otherwise-it-might-not-work-as-expected"></a>오류 메시지: "이 사이트를 IE 모드에서 열려면 원격 디버깅을 사용하지 않도록 설정하세요. 그렇지 않으면 예상대로 작동하지 않을 수 있습니다."

원격 디버깅을 진행하고 IE 모드에서 실행하도록 구성된 웹 페이지로 이동하면 이 오류가 표시될 수 있습니다. 계속할 수 있지만 페이지는 Microsoft Edge를 사용하여 렌더링됩니다.

### <a name="error-message-could-not-retrieve-emie-site-list"></a>오류 메시지: "EMIE 사이트 목록을 검색할 수 없습니다."

사이트 목록 다운로드가 실패했다는 ** edge://compat/enterprise 페이지에 이 오류가 표시될 수 있습니다. Microsoft Edge 버전 87부터 [BlockThirdPartyCookies](/deployedge/microsoft-edge-policies#blockthirdpartycookies) 정책을 사용하여 타사 요청에 대해 쿠키가 차단되는 경우 HTTP 인증도 허용되지 않습니다. 사이트 목록 다운로드가 성공적으로 진행되도록 [CookiesAllowedForURLs](/deployedge/microsoft-edge-policies#cookiesallowedforurls) 정책을 사용하여 엔터프라이즈 모드 사이트 목록을 호스팅하는 특정 도메인에 대한 쿠키를 허용할 수 있습니다.

### <a name="error-message-the-connection-for-this-site-is-not-secure"></a>오류 메시지: "이 사이트에 대한 연결이 안전하지 않습니다."

이 오류는 IE 모드에서 레거시 웹 사이트를 열려고 시도하고 사이트의 TLS 1.0 또는 TLS 1.1에서 실행하도록 구성된 경우 발생할 수 있습니다. 이러한 프로토콜은 기본적으로 사용하지 않도록 설정되어 Microsoft Edge. 자세한 내용은 변경 계획: 기본적으로 사용하지 않도록 설정될 [예정인 TLS 1.0 및 TLS 1.1을 참조하세요.](https://blogs.windows.com/msedgedev/2020/03/31/tls-1-0-tls-1-1-schedule-update-edge-ie11/)

### <a name="error-message-this-form-cannot-be-opened-in-a-web-browser-to-open-this-form-use-microsoft-infopath"></a>오류 메시지: "이 양식을 웹 브라우저에서 열 수 없습니다. 이 양식을 열기 위해 Microsoft InfoPath를 사용하세요."

특정 응용 프로그램에서는 IE 모드로 웹 페이지를 로드해야 할 수 있습니다. IE 모드 기능은 IE 모드 Microsoft Edge.

또한 Enterprise `compat-mode` 모드 사이트 목록에서 특성을 기본값으로 설정해야 할 수도 **있습니다**. 자세한 내용은 Enterprise 모드 및 Enterprise [사이트 목록을 참조하세요](/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#enterprise-mode-and-the-enterprise-mode-site-list-1).

> [!TIP]
> 사용자는 웹 사이트에서 **about:compat**을 입력하여 이 사이트 목록 및 호환성 모드를 Microsoft Edge.

## <a name="frequently-asked-questions"></a>질문과 대답

### <a name="will-ie-mode-replace-internet-explorer-11"></a>IE 모드가 Internet Explorer 11을 대체하나요?

예, Internet Explorer 11 데스크톱 응용 프로그램이 사용 중지되어 2022년 6월 15일에는 지원이 중지됩니다. 범위에 있는 내용은 수명 [주기 FAQ -](/lifecycle/faq/internet-explorer-microsoft-edge) Internet Explorer. 현재 사용하는 동일한 IE11 앱과 사이트는 Internet Explorer 모드에서 Microsoft Edge로 열 수 있습니다. 자세한 내용은 현재 현재 Internet Explorer [Windows 10 더하기를 Microsoft Edge](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/).

### <a name="can-i-use-view-in-file-explorer-in-sharepoint-online-on-microsoft-edge"></a>SharePoint Online에서 "파일 탐색기에서 보기"를 사용할 수 Microsoft Edge?

Microsoft Edge 버전 95부터 온라인 최신 문서 라이브러리에 대해 파일 탐색기에서 보기 **** 기능을 SharePoint 수 있습니다. 이 환경을 표시하고 사용자에게 작동하려면 Microsoft Edge "SharePoint 페이지의 파일 탐색기 기능 구성 SharePoint["](/deployedge/microsoft-edge-policies#configureviewinfileexplorer) 정책을 사용하도록 설정하고 Microsoft Edge Online 테넌트 구성을 업데이트해야 합니다. 자세한 내용은 다음을 SharePoint 파일 탐색기를 사용하여 파일 Microsoft Edge [- SharePoint 보기를 Microsoft 365 | Microsoft Docs](/SharePoint/sharepoint-view-in-edge).

그러나 파일 탐색기에서 보기 옵션을 사용하는 대신 파일 탐색기 외부의 파일 및 폴더를 관리하는 SharePoint 권장되는 방법은 컴퓨터와 파일을 동기화하고 SharePoint Teams [](https://support.microsoft.com/office/sync-sharepoint-and-teams-files-with-your-computer-6de9ede8-5b6e-4503-80b2-6190f3354a88?ui=en-us&rs=en-us&ad=us) 파일을 동기화하거나 파일에서 파일을 이동하거나 복사하는 [SharePoint](https://support.microsoft.com/office/move-or-copy-files-in-sharepoint-00e2f483-4df3-46be-a861-1f5f0c1a87bc?ui=en-us&rs=en-us&ad=us).

### <a name="does-ie-mode-on-microsoft-edge-support-the-no-merge-option-that-was-supported-in-internet-explorer-11"></a>IE 모드가 Microsoft Edge 11에서 지원되는 '병합 안 Internet Explorer' 옵션을 지원하나요?

다음 작업 중 하나는 Microsoft Edge 병합하지 않음 기능에 대한 권장 대안입니다.

1. Microsoft Edge 프로필 사용 - 각 프로필은 IE 모드 페이지에 대해 다른 IE 세션에 매핑되어 병합 금지 옵션과 동일하게 사용됩니다.
2. `--user-data-dir=<path>` 명령줄을 사용하되 각 세션에 대해 다른 경로를 사용합니다. 필요한 경우 사용자가 실행되는 유틸리티를 만들어 세션의 경로를 Microsoft Edge 수 있습니다.

이전 옵션 중 어느 옵션도 시나리오에 대해 작동하지 Microsoft Edge 버전 93부터는 IE 모드가 Microsoft Edge 지원하지 않습니다. 최종 사용자의 경우 IE 모드 응용 프로그램에서 새 브라우저 창을 시작하면 IE11의 병합 금지 동작과 같은 별도의 세션에 있습니다.

각 Microsoft Edge 창에 대해 해당 창 내에서 IE 모드 탭을 처음 방문하면 지정된 "병합 안함" 사이트인 경우 해당 창이 다른 "병합 안 함" IE 세션에 잠겨 있습니다.  이 창은 잠긴 창에서 마지막 IE 모드 Microsoft Edge 닫을 때까지 다른 모든 창에서 잠겨 있습니다. 이는 사용자가 병합하지 않고 IE를 시작하고 다른 메커니즘을 사용하여 병합하지 않고 Microsoft Edge 이전 동작을 따르는 것입니다. window.open을 통해 새 창에서 여는 모든 사이트는 부모 프로세스의 병합 특성을 존중합니다.

> [!NOTE]
> 세션 전환은 지원되지 않습니다. 동일한 IE 모드 탭 내의 탐색은 동일한 세션을 사용합니다.

다음 단계를 수행하여 Microsoft Edge 버전 93 이상에서 병합 없음 동작의 유효성을 검사할 수 있습니다.

1. IE 모드가 버전 93 이상에서 Microsoft Edge 사용하도록 설정되어 있는지 확인합니다.
2. 병합 유형 특성 값을 "병합 안Enterprise 모드 사이트 목록에서 세션 공유를 방지해야 하는 사이트를 구성할 수 있습니다. 이 특성은 open-in 요소가 기본 설정으로 설정된 Microsoft Edge. 기본적으로 모든 사이트에는 병합 형식 값이 있습니다. 참고 **:** 사이트 추가 또는 편집 시 edge://compat/sitelistmanager 통합 사이트 목록 ** 관리자 도구에 병합 안 함을 **** 포함합니다.

   ```
   <site url="contoso.com">
   <open-in merge-type="no-merge">IE11</open-in>
   </site>
   ```

3. 병합 없음으로 구성된 사이트로 이동합니다. 사이트는 자체의 IE 세션에 있습니다. 다른 Microsoft Edge 인스턴스 또는 창을 열고 동일한 사이트로 이동하는 경우 해당 인스턴스가 자체 IE 세션에 있습니다. 작업 관리자에는 여러 iexplore.exe 프로세스가 있습니다.

피드백이 있는 경우 피드백 채널인 Microsoft 지원 또는 [TechCommunity 포럼 중](https://techcommunity.microsoft.com/t5/enterprise/bd-p/EdgeInsiderEnterprise) 하나를 통해 방문하세요.

### <a name="can-i-save-links-as-webpages-in-internet-explorer-mode"></a>Internet Explorer 모드에서 링크를 웹 페이지로 저장할 수 있나요?

예, Microsoft Edge의 Internet Explorer 모드용 바로 가기 메뉴에서 다른 이름으로 대상 저장 옵션을 활성화할 수 있습니다. 이렇게하려면 컴퓨터 구성 > 관리 템플릿 및 구성 요소에 *있는 "다른* Internet Explorer 모드로 대상 저장 허용" 그룹 정책을 *> Windows > Internet Explorer*. 저장 메커니즘은 Internet Explorer 파일에서와 동일하게 작동하며 대상이 html 파일로 저장되는 경우 파일을 다시 열면 페이지가 Microsoft Edge.

링크를 웹 페이지로 저장하려면 다음과 같은 최소 운영 체제 업데이트가 필요합니다.

- Windows 10, 버전 2004, Windows Server 버전 2004, Windows 10, 버전 20H2 : [KB4580364](https://support.microsoft.com/help/4580364/windows-10-update-kb4580364)
- Windows 10, 버전 1903, Windows 10, 버전 1909, Windows Server 버전 1903: [KB4580386](https://support.microsoft.com/help/4580386/windows-10-update-kb4580386)
- Windows 10, 버전 1809, Windows Server 버전 1809, Windows Server 2019: [KB4580390](https://support.microsoft.com/help/4580390/windows-10-update-kb4580390)
- Windows 10, 버전 1803: [KB4586785](https://support.microsoft.com/help/4586785/windows-10-update-kb4586785)
- Windows 10, 버전 1607: [KB4586830](https://support.microsoft.com/help/4586830/windows-10-update-kb4586830)
- Windows 10, 버전 1507: [KB4586787](https://support.microsoft.com/help/4586787/windows-10-update-kb4586787)

### <a name="can-i-test-a-site-in-microsoft-edge-while-it-is-configured-to-open-ie-mode-in-the-enterprise-mode-site-list"></a>사이트가 Microsoft Edge 모드 사이트 목록에서 IE 모드를 열도록 구성된 동안 사이트가 Enterprise 수 있나요?

예, 레거시 사이트를 최신화하는 동안 IE 모드로 구성된 응용 프로그램을 해당 사이트에서 테스트할 Microsoft Edge. 이러한 앱을 테스트하려면 [InternetExplorerModeTabInEdgeModeAllowed 정책을 구성할 수](/deployedge/microsoft-edge-policies#internetexplorermodetabinedgemodeallowed) 있습니다. 해당 정책을 사용하도록 설정하면 사용자가 에지 모드에서 더 많은 도구 열기 Microsoft Edge 이상(설정 아이콘 ...)**** > 을 **** 선택하여 > IE 모드 사이트를 열 **수 있습니다**.

### <a name="how-can-i-debug-my-legacy-application-while-using-ie-mode-on-microsoft-edge"></a>기존 응용 프로그램에서 IE 모드를 사용하는 동안 레거시 응용 프로그램을 디버그하는 Microsoft Edge?

IEChooser를 사용하여 개발자 Internet Explorer 시작하여 IE 모드 탭의 콘텐츠를 디버그할 수 있습니다. IEChooser를 사용 하 고 다음 단계를 수행 합니다.

1. IEChooser를  열 수 있습니다.
   - 실행 대화 상자를 엽니다. 예를 들어 를 누르고 있습니다 `Windows logo key` + `R`.
   - `%systemroot%\system32\f12\IEChooser.exe`를 입력한 다음 확인을 **선택합니다**.
2. IEChooser에서 IE 모드 탭의 항목을 선택합니다.

### <a name="my-application-requires-transferring-post-data-between-ie-mode-and-microsoft-edge-is-this-supported"></a>응용 프로그램에는 IE 모드와 IE 모드 간에 POST 데이터를 전송해야 Microsoft Edge. 가능합니까?

Microsoft Edge Beta 채널 버전 96부터 Internet Explorer 모드와 Microsoft Edge 전환하는 탐색에는 양식 데이터와 추가 HTTP 헤더가 포함됩니다. 그러나 양식 데이터에 첨부 파일이 포함된 경우 엔진 간에 전송되지 않습니다. [InternetExplorerIntegrationComplexNavDataTypes](/deployedge/microsoft-edge-policies#internetexplorerintegrationcomplexnavdatatypes) 그룹 정책을 사용하여 이러한 탐색에 포함될 데이터 형식을 선택할 수 있습니다.

이 Microsoft Edge 버전 96 외에도 이 환경을 위해 다음 Windows 업데이트가 설치되어야 합니다.

- Windows 11 [KB5007262](https://support.microsoft.com/topic/november-22-2021-kb5007262-os-build-22000-348-preview-7f3e18d7-4189-4882-b0e9-afc920253aee) 이상
- Windows Server 2022 [KB5007254](
https://support.microsoft.com/topic/november-22-2021-kb5007254-os-build-20348-380-preview-9a960291-d62e-486a-adcc-6babe5ae6fc1) 이상
- Windows 10 버전 2004; Windows Server 버전 2004; Windows 10 버전; Windows Server 버전 20H2 및 Windows 10 버전 21H1 - [KB5006738](https://support.microsoft.com/topic/october-26-2021-kb5006738-os-builds-19041-1320-19042-1320-and-19043-1320-preview-ccbce6bf-ae00-4e66-9789-ce8e7ea35541) 이상
- Windows 10 버전 1909 [KB5007189](
https://support.microsoft.com/topic/november-9-2021-kb5007189-os-build-18362-1916-91b4647c-9979-4d84-8e64-efc8674e8c1f) 이상

### <a name="where-can-i-find-the-reload-in-internet-explorer-mode-option"></a>"Internet Explorer 모드로 다시 로드" 옵션은 어디에서 찾을 수 있나요?

이 기능은 Microsoft Edge 버전 92 이상에서 사용할 수 있습니다. 이 옵션을 사용하도록 설정하려면 "허용"으로 Internet Explorer 모드 설정으로 사이트를 Microsoft Edge 구성합니다.  자세한 내용은 [Enable the local site list experience을 참조하십시오](/deployedge/edge-ie-mode-local-site-list#enable-the-local-site-list-experience).

### <a name="where-is-the-file--new-session-option-in-microsoft-edge"></a>파일 > "새 세션" 옵션은 Microsoft Edge?

최신 브라우저 솔루션은 브라우저에서 여러 프로필을 사용하여 Microsoft Edge. 이 기능을 사용하면 다른 계정으로 새 세션을 만들 수 있습니다. 다음 리소스에서는 여러 프로필의 이점과 이러한 프로필을 사용하는 방법에 대한 정보를 제공합니다.

- [비디오: Microsoft Edge 및 ID](/deployedge/microsoft-edge-video-identity)
- [이제는 직장과 가정에서 여러 프로필을 사용하는 것이 더 쉬워졌습니다Microsoft Edge](https://blogs.windows.com/msedgedev/2020/04/30/automatic-profile-switching/)

### <a name="why-am-i-getting-multiple-authentication-prompts-when-running-a-page-in-ie-mode-on-microsoft-edge"></a>IE 모드에서 페이지를 실행하면 여러 인증 프롬프트가 표시되고 있는 Microsoft Edge?

클라이언트 인증서는 IE 모드에서 두 번 요청할 수 있습니다. 처음에는 인증서 선택 대화 상자가 IE 모드로 표시되고 두 번째로 이 대화 상자가 IE 모드로 Microsoft Edge. 프레임 프로세스와 창 프로세스 모두 인증을 요청해야 합니다.

favicon 캐시를 만든 후 캐시를 삭제하지 않는 한 클라이언트 인증서를 다시 요청하지 않습니다. 또는 FAVICON에 대한 클라이언트 인증서가 필요하지 않은 서버 구성(예: IIS)에서 규칙을 설정할 수 있습니다.

### <a name="why-are-there-rendering-issues-like-text-wrapping-and-content-truncation-when-child-windows-are-running-in-ie-mode-in-microsoft-edge"></a>자식 창이 IE 모드에서 실행되는 경우 텍스트 줄 바꿈 및 콘텐츠 자르기 같은 렌더링 문제가 Microsoft Edge?

Microsoft Edge IE 모드로 렌더링되는 자식 창의 콘텐츠 영역은 Internet Explorer 11에 있는 영역과 약간 다릅니다. 웹 페이지가 픽셀 기반 맞춤 또는 위치로 디자인된 경우 잘못된 렌더링, 텍스트 줄 바꿈이 표시될 수 있습니다.

이 메서드를 통해 Microsoft Edge 사이트에서 생성되는 팝업 창의 높이와 너비에 대한 사용자 지정 조정을 지정할 수 있는 두 가지 정책 설정이 Microsoft Edge 버전 95에 추가 `window.open` 되었습니다. 다음 정책을 사용하여 창 크기를 조정할 수 있습니다.

- [InternetExplorerIntegrationWindowOpenHeightAdjustment](/deployedge/microsoft-edge-policies#internetexplorerintegrationwindowopenheightadjustment) - 이 설정을 사용하여 Internet Explorer 모드 사이트에서 생성된 팝업 창의 높이를 사용자 지정할 수 있습니다.
- [InternetExplorerIntegrationWindowOpenWidthAdjustment](/deployedge/microsoft-edge-policies#internetexplorerintegrationwindowopenwidthadjustment) - 이 설정을 사용하여 Internet Explorer 모드 사이트에서 생성된 팝업 창의 너비에 대한 사용자 지정 조정을 지정할 수 있습니다.

### <a name="why-arent-pop-ups-or-redirected-websites-loading-in-ie-mode-or-in-internet-explorer-11"></a>IE 모드 또는 IE 11에서 팝업 또는 리디렉션된 웹 사이트가 Internet Explorer 않는 이유는 무엇입니까?

IE 모드를 구성한 후 특정 웹 사이트, 특히 새 창을 만드는 사이트 또는 리디렉션되는 사이트는 IE 모드에서 렌더링되거나 Internet Explorer 11에서 열 수 없습니다.

이러한 종류의 리디렉션된 웹 사이트의 경우 사이트 `allow-redirect="true"` 목록 구성에서 를 사용할 수 있습니다. 자세한 내용은 [업데이트된 schema 요소를 참조하세요](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance#updated-schema-elements).

### <a name="why-arent-websites-loading-in-ie-mode-when-i-launch-microsoft-edge-for-the-first-time"></a>웹 사이트를 처음 시작하면 웹 사이트가 IE 모드로 Microsoft Edge 이유는 무엇입니까?

Microsoft Edge IE 모드 설정을 적용하려면 먼저 IE 모드 사이트 목록을 다운로드해야 합니다. 브라우저가 시작될 때 이 프로세스가 완료되지 않을 수 있습니다. 웹 사이트가 로드되기 전에 사이트 목록을 강제로 로드할 수 있는 정책을 사용할 수 있습니다. 자세한 내용은 [DelayNavigationsForInitialSiteListDownload](/deployedge/microsoft-edge-policies#delaynavigationsforinitialsitelistdownload) policy를 참조하세요.

### <a name="why-cant-i-open-files-or-pages-that-are-found-by-using-file-urls-in-microsoft-edge"></a>이 문서의 URL을 사용하여 찾은 파일이나 페이지를 열 수 file:// 수 Microsoft Edge.

보안 Chromium 때문에 IE 모드를 사용해야 합니다. IE 모드 Microsoft Edge 사용하여 인트라넷 영역 내의 **file:// 호스트된** 웹 페이지를 로드할 수 있습니다. [IntranetFileLinksEnabled](/deployedge/microsoft-edge-policies#intranetfilelinksenabled) 그룹 정책을 사용하여 이 기능을 사용하도록 설정할 수 있습니다.

## <a name="see-also"></a>참고 항목
  
- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [IE 모드 정보](./edge-ie-mode.md)
- [추가 엔터프라이즈 모드 정보](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
