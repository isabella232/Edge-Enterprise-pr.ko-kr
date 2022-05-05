---
title: IE(Internet Explorer) 모드 문제 해결 및 FAQ
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 04/25/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge Internet Explorer 모드에 대한 문제 해결 가이드 및 FAQ
ms.openlocfilehash: 076ce09e3ec1c0e392b1bf1f311bbc17a2f62093
ms.sourcegitcommit: 592f6e40b13e28af588473b2a75c3ae697e5db2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2022
ms.locfileid: "12505361"
---
# <a name="internet-explorer-ie-mode-troubleshooting-and-faq"></a>IE(Internet Explorer) 모드 문제 해결 및 FAQ

> [!NOTE]
> Internet Explorer 11 데스크톱 애플리케이션은 사용 중지되고 2022년 6월 15일에 지원되지 않습니다. 범위의 목록을 보려면 [Internet Explorer 11 데스크톱 앱 사용 중지 FAQ](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)를 참조하세요. 현재 사용하는 동일한 IE11 앱과 사이트는 Internet Explorer 모드에서 Microsoft Edge로 열 수 있습니다. 자세한 내용은 Microsoft Edge 블로그 게시물에서 [Windows 10 Internet Explorer의 미래를](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/) 참조하세요.

이 문서에서는 Microsoft Edge 버전 77 이상에 대한 문제 해결 팁 및 FAQ를 제공합니다.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.

## <a name="what-if-i-need-help-with-setting-up-microsoft-edge-or-internet-explorer-mode"></a>Microsoft Edge 또는 Internet Explorer 모드를 설정하는 데 도움이 필요한 경우 어떻게 해야 하나요?

다양한 지원 옵션을 제공합니다. Microsoft 통합 지원 경우 해당 지원 서비스에 연락하여 전환에 대한 도움을 받을 수 있습니다. 또한 [FastTrack](https://www.microsoft.com/en-us/fasttrack/microsoft-365/microsoft-edge?rtc=1) Windows 10 유료 좌석이 150명 이상인 고객에게 추가 비용 없이 사용할 수 있습니다.

Microsoft Edge + Internet Explorer 모드 [시작 가이드](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RWEHMs) 및 [IE 모드 블로그 시리즈](https://techcommunity.microsoft.com/t5/windows-10/internet-explorer-to-microsoft-edge-with-ie-mode-blog-series/m-p/2617124)도 권장합니다.

## <a name="are-there-any-tools-that-i-can-use-to-guide-me-through-ie-mode-troubleshooting"></a>IE 모드 문제 해결을 안내하는 데 사용할 수 있는 도구가 있나요?

예, [Microsoft Virtual Agent](https://go.microsoft.com/fwlink/?linkid=2194137) 는 IE 모드 문제 해결을 위한 시나리오 기반 단계별 연습을 제공합니다.

## <a name="common-ie-mode-issues"></a>일반적인 IE 모드 문제

이 섹션을 가이드로 사용하여 IE 모드를 사용하여 Microsoft Edge 이동할 때 가장 일반적인 두 가지 문제를 해결하고 해결할 수 있습니다. 이러한 문제는 다음과 같습니다.

- 잘못된 문서 모드 구성
- 불완전한 중립 사이트 구성

### <a name="incorrect-document-mode-configurations"></a>잘못된 문서 모드 구성

이 섹션에서는 증상을 설명하고 이 문제를 진단하고 해결하는 단계를 제공합니다.

#### <a name="symptoms"></a>증상

사용자에게는 다음과 같은 증상이 발생합니다.
  
- 페이지 요소의 크기 조정 및 위치 지정이 꺼져 있거나 누락되었을 수 있습니다. 
- 일부 기능이 손실되거나 예상대로 작동하지 않을 수 있습니다. 예를 들어 Internet Explorer에서 작동하는 단추는 아무 작업도 수행하지 않거나 오류를 반환하지 않습니다.

#### <a name="how-to-troubleshoot-and-fix"></a>문제 해결 및 수정 방법

일반적인 전략은 IE 모드 사이트 목록의 특정 사이트에 대해 Internet Explorer 11과 동일한 설정을 복제하는 것입니다. 다음 스크린샷에 표시된 IE 11에서 F12 개발자 도구 모음의 "에뮬레이션" 탭을 사용하여 수정하려는 시나리오를 조사합니다. 개발자 도구 모음을 열려면 F12 키를 누른 다음 **DevTools 열기를** 선택합니다.

![DevTools 보기의 에뮬레이션 탭](./media/edge-ie-mode-faq/edge-ie-mode-emulation-tab.png)

에뮬레이션 탭에는 두 가지 정보, 즉 문서 모드(1)와 드롭다운 목록 아래의 텍스트(2)가 표시됩니다. 이 정보는 현재 보고 있는 페이지 또는 사이트의 11(기본값) 모드에 있는 이유를 설명하는 데 도움이 될 수 있습니다.

문서 모드에 대해 표시할 수 있는 다양한 메시지가 있으며, 이 예제에서는 다음과 같습니다.
  
- X-UA 호환 메타 태그를 통해
- X-UA 호환 HTTP 헤더를 통해

두 X-UA 호환 옵션은 사이트가 호스트되는 웹 페이지 또는 웹 서버가 브라우저에서 사용해야 하는 문서 모드를 표시함을 나타냅니다.  

거의 모든 경우에 문서 모드를 적용하려고 합니다. 이렇게 하려면 사이트의 IE 모드 사이트 목록 항목에서 다음 모드 중 하나를 선택해야 합니다.

- Default
- IE8 Enterprise
- IE7 Enterprise

이러한 옵션은 웹 페이지 또는 웹 서버 지시문을 준수합니다. 지정된 문서 모드를 포함하는 옵션을 선택해야 합니다. 스크린샷 예제에서는 지정된 문서 모드가 11이므로 IE8 Enterprise 및 IE7 Enterprise IE 11 문서 모드를 지원하지 않으므로 "기본값"을 선택합니다.  

문서 모드에서 사이트에 다음 호환성 보기 중 하나가 필요하다고 표시되면 구성 설정이 간단합니다.

- 로컬 호환성 보기 설정을 통해
- 호환성 보기 목록을 통해
- 인트라넷 호환성 설정을 통해

모든 호환성 보기 설정으로 인해 "IE7 Enterprise" 동작이 발생하므로 IE 모드 사이트 목록 항목의 "호환 모드" 섹션에서 이 설정을 선택합니다.

Internet Explorer 또는 IE 모드가 한 문서 모드를 다른 문서 모드로 이동하는 데 사용하는 논리에 대한 자세한 내용은 [사용되지 않는 문서 모드 및 Internet Explorer 11](/internet-explorer/ie11-deploy-guide/deprecated-document-modes) 문서를 참조하세요.

일반적인 규칙은 지정된 사이트가 예상대로 작동할 수 있도록 하는 최신 논리 기반 모드를 사용하는 것입니다. 기본 모드로 시작하고, IE8 Enterprise 모드로 이동한 다음, 필요한 경우 IE7 Enterprise 모드로 이동합니다. 이 옵션을 선택하면 자식 페이지에서 특정 요구 사항에 대한 기본 제공 논리를 통해 필요에 따라 다양한 문서 모드를 유연하게 사용할 수 있습니다. 따라서 모든 웹 사이트 페이지가 하나의 특정 문서 모드로 잠기지 않습니다.  

다음 표에서는 이러한 설정에 사용할 수 있는 문서 모드를 나열합니다.

| 논리 기반 모드 | Default | IE8 Enterprise | IE7 Enterprise |
|--|--|--|--|
| 사용 가능한 문서 모드 | IE11 문서 모드<br> IE10 문서 모드<br>IE9 문서 모드<br> IE8 문서 모드<br>IE7 문서 모드<br>IE5 단점 모드 | IE8 문서 모드<br>IE7 문서 모드<br>IE5 단점 모드   | IE7 문서 모드<br>IE5 단점 모드  |

> [!NOTE]
> 경우에 따라 특정 사이트 또는 페이지에서 디자인된 대로 작동하려면 특정 문서 모드가 필요합니다. 명시적 문서 모드 옵션은 논리 기반 옵션이 유효하지 않은 경우에만 사용하는 것이 좋습니다.

### <a name="incomplete-neutral-site-configurations"></a>불완전한 중립 사이트 구성

이 섹션에서는 증상을 설명하고 이 문제를 진단하고 해결하는 단계를 제공합니다.

#### <a name="symptoms"></a>증상
  
페이지는 인증을 위해 SSO를 사용하지만 사용자에게 자격 증명, 반복 리디렉션 동작, 실패한 인증 오류 또는 이러한 증상의 일부 조합을 경험하라는 메시지가 여러 번 표시됩니다.
  
#### <a name="how-to-troubleshoot-and-fix"></a>문제 해결 및 수정 방법
  
Microsoft Edge 실패한 워크플로 분석을 시작하기 전에 다음 스크린샷에 표시된 IE 모드 "e" 로고의 주소 표시줄을 확인합니다.

![Microsoft Edge 메뉴 모음의 IE 로고입니다.](./media/edge-ie-mode-faq/edge--ie-mode-logo.png)

SSO 인증 프로세스 중에 "e"가 표시되지만 리디렉션 후에 사라지는 경우 이 동작은 누락된 중립 사이트를 가리킵니다. Microsoft Edge IE 모드로 전환되면 세션 및 쿠키 정보를 유지 관리하기 위해 해당 모드에 머물러야 합니다. URL이 주소 표시줄에 표시되어 식별할 수 있을 만큼 긴 경우 중립 사이트 구성에 설명된 단계를 사용하여 IE 모드 사이트 목록에 [중립 사이트](/deployedge/edge-ie-mode-sitelist#configure-neutral-sites)로 추가합니다.

종종 리디렉션 주기가 너무 빨리 발생하므로 누락된 중립 사이트를 식별하기가 어렵습니다. 이 분석을 돕기 위해 Chromium 엔진에 기본 제공되는 도구**인 순 내보내기를** 사용합니다.

> [!TIP]
> 네트워크 추적은 본질적으로 시끄럽습니다. 노이즈를 최소화하려면 조사 중인 특정 워크플로에 필요하지 않은 다른 모든 브라우저 인스턴스와 탭을 닫습니다.

다음 단계에서는 중립 사이트 구성 문제를 해결하는 방법을 설명합니다.
  
1. Microsoft Edge 새 탭을 열고 *edge://net-export* 이동합니다.
2. **디스크에 로깅 시작을** 선택한 다음 결과 .json 로그를 저장할 위치를 선택합니다. 문제 해결을 완료한 후 이 로그를 안전하게 삭제할 수 있습니다.
3. 다른 탭을 열고(순 내보내기 탭을 열어 두고) 실패한 워크플로를 반복합니다.
4. 완료되면 순 내보내기 탭으로 돌아가 **서 로깅 중지를** 선택합니다.
5. "netlog 뷰어" 하이퍼링크를 선택합니다.
6. 결과 페이지에서 **파일 선택을 선택한** 다음, 2단계에서 만든 .json 파일을 선택합니다.
7. 로그 파일을 로드한 후 왼쪽 메뉴에서 **이벤트를** 선택합니다.
8. 네트워크 로그를 스크롤하여 시작 URL을 식별합니다. (검색 함수를 사용하여 시작 지점을 찾을 수도 있습니다.)
9. 시작 지점에서 아래로 스크롤하여 IE 모드 사이트 목록에 항목이 없는 워크플로의 URL을 찾습니다. SSO, AUTH, LOGIN 등에 대한 지표를 사용하여 URL에 특히 주의하세요.
10. 후보 URL을 식별한 후 열기 드롭다운에서 **없음** 을 선택하여 IE 모드 사이트 목록에 중립 사이트로 추가합니다. 워크플로를 다시 테스트합니다.

경우에 따라 특정 사이트 아키텍처에 따라 여러 중립 사이트 항목이 필요합니다. 새 중립 사이트를 추가한 후에도 워크플로가 계속 실패하는 경우 프로세스를 반복하여 새 순 내보내기 로그를 캡처하고 다른 패스를 수행합니다.

일부 드문 경우에서는 필요한 정보가 IE 모드 사이트에 도착하도록 특정 공유 쿠키를 구성해야 할 수 있습니다. 필요한 특정 쿠키를 알고 있는 경우 Microsoft Edge Internet Explorer로 쿠키 공유에 설명된 단계를 사용하여 [쿠키 공유를](/deployedge/edge-ie-mode-add-guidance-cookieshare) 구성할 수 있습니다.

### <a name="what-if-these-steps-dont-fix-the-issue"></a>이러한 단계가 문제를 해결하지 않으면 어떻게 해야 하나요?

이 문서는 가장 일반적인 IE 모드 구성 문제를 해결하는 데 도움이 되도록 설계되었지만 가능한 모든 시나리오는 다루지 않을 수 있습니다. 해결할 수 없는 문제가 발생하여 도움이 필요한 경우 App Assure에 [https://aka.ms/AppAssure](https://aka.ms/AppAssure) 문의하면 문제를 해결할 수 있습니다.

## <a name="get-general-diagnostic-and-configuration-information"></a>일반 진단 및 구성 정보 가져오기

Microsoft Edge 호환성 탭에서 Internet Explorer 모드 진단 정보를 볼 수 있습니다. 이 탭을 열려면 *edge://compat/iediagnostic*으로 이동합니다. "Internet Explorer 모드 진단 정보" 페이지에 진단 메시지가 표시될 수 있으며 진단 데이터를 xml 파일로 내보낼 수 있습니다. 이 진단 정보 페이지에서는 다음 범주에 대한 구성 정보도 제공합니다.

- **레지스트리 키를 확인.** (확인에 실패한 경우에만 표시됨) 레지스트리에 Internet Explorer 통합이 올바르게 설정되어 있는지 확인합니다. 그렇지 않은 경우 사용자는 **해결** 을 선택하여 문제를 해결할 수 있습니다.
- **Internet Explorer 모드.** 구성 및 OS를 기반으로 사용되는 API 버전을 표시합니다. 문제가 있는 경우 Windows 업데이트를 설치하라는 메시지가 표시될 수 있습니다.
- **Internet Explorer 모드 설정.** Internet Explorer 모드의 활성화 여부 및 구성 방법을 보여줍니다.
- **명령줄.** Microsoft Edge 시작하는 데 사용되는 명령줄 문자열 및 스위치를 표시합니다.
- **그룹 정책 설정.** IE 모드가 그룹 정책과 적용되는 정책을 사용하여 구성되는지 여부를 표시합니다.

### <a name="error-message-to-open-this-page-in-internet-explorer-mode-reinstall-microsoft-edge-with-administrator-privileges"></a>오류 메시지: "이 페이지를 Internet Explorer 모드에서 열려면 관리자 권한으로 Microsoft Edge를 다시 설치하세요."

모든 필수 Windows 업데이트가 없는 경우 이 오류가 표시될 수 있습니다. 필요한 Windows 및 Microsoft Edge 버전에 대해서는 [IE 모드 정보](./edge-ie-mode.md)에 나열된 필수 구성 요소를 참조하세요.

모든 필수 Windows 업데이트를 이미 설치한 경우 다음과 같은 경우 이 오류가 표시될 수 있습니다.

- 기본적으로 사용자 수준으로 설치되는 Canary 채널을 사용하고 있습니다.
- Stable, Beta 또는 Dev 채널을 사용하고 있지만 설치할 때 권한 상승 프롬프트가 나타나면 권한 상승이 취소되었습니다. 권한 상승 프롬프트를 취소하면 설치는 사용자 수준에서 계속됩니다.
- Internet Explorer 11은 Windows 기능에서 사용하지 않도록 설정되었습니다.

가능한 해결 방법은 다음과 같습니다.

- 모든 채널에 대해 설치 프로그램을 시스템 수준에서 실행합니다. `installer.exe --system-level`
- Windows 기능에서 Internet Explorer 11을 사용 설정합니다.

Microsoft Edge가 시스템 수준에서 설치되어 있는지 확인하려면 Microsoft Edge 주소 표시줄에 "edge://version"을 입력합니다. 실행 파일 경로에 *C:\Program Files*로 시작하는 경로가 표시되면 이는 시스템 설치를 나타냅니다. 실행 경로가 *C:\Users*로 시작하는 경우 관리자 권한으로 Microsoft Edge 제거한 다음 다시 설치합니다.

### <a name="error-message-to-open-this-page-in-ie-mode-try-restarting-microsoft-edge"></a>오류 메시지 "IE 모드에서 이 페이지를 열려면 Microsoft Edge 다시 시작해 보세요."

Internet Explorer에서 예기치 않은 오류가 발생한 경우 이 오류가 표시될 수 있습니다. Microsoft Edge를 다시 시작하면 일반적으로 이 오류가 해결됩니다.

### <a name="error-message-turn-off-remote-debugging-to-open-this-site-in-ie-mode-otherwise-it-might-not-work-as-expected"></a>오류 메시지: "이 사이트를 IE 모드에서 열려면 원격 디버깅을 사용하지 않도록 설정하세요. 그렇지 않으면 예상대로 작동하지 않을 수 있습니다."

원격 디버깅 중이고 IE 모드에서 실행되도록 구성된 웹 페이지로 이동하면 이 오류가 표시될 수 있습니다. 계속할 수 있지만 페이지는 Microsoft Edge를 사용하여 렌더링됩니다.

### <a name="error-message-could-not-retrieve-emie-site-list"></a>오류 메시지: "EMIE 사이트 목록을 검색할 수 없습니다."

*edge://compat/enterprise* 페이지에 사이트 목록 다운로드가 실패했음을 나타내는 이 오류가 표시될 수 있습니다. Microsoft Edge 버전 87부터[는 BlockThirdPartyCookies](/deployedge/microsoft-edge-policies#blockthirdpartycookies) 정책을 사용하여 타사 요청에 대해 쿠키가 차단되는 경우 HTTP 인증도 허용되지 않습니다. 사이트 목록 다운로드가 성공적으로 진행되도록 [CookiesAllowedForURLs](/deployedge/microsoft-edge-policies#cookiesallowedforurls) 정책을 사용하여 엔터프라이즈 모드 사이트 목록을 호스팅하는 특정 도메인에 대한 쿠키를 허용할 수 있습니다.

### <a name="error-message-the-connection-for-this-site-is-not-secure"></a>오류 메시지: "이 사이트에 대한 연결이 안전하지 않습니다."

이 오류는 IE 모드에서 레거시 웹 사이트를 열려고 하고 사이트가 TLS 1.0 또는 TLS 1.1에서 실행되도록 구성된 경우에 발생할 수 있습니다. 이러한 프로토콜은 기본적으로 Microsoft Edge 사용하지 않도록 설정됩니다. 자세한 내용은 [변경 계획: TLS 1.0 및 TLS 1.1이 기본적으로 사용하지 않도록 설정될 예정입니다.](https://blogs.windows.com/msedgedev/2020/03/31/tls-1-0-tls-1-1-schedule-update-edge-ie11/)

### <a name="error-message-this-form-cannot-be-opened-in-a-web-browser-to-open-this-form-use-microsoft-infopath"></a>오류 메시지: "이 양식은 웹 브라우저에서 열 수 없습니다. 이 양식을 열려면 Microsoft InfoPath를 사용합니다."

특정 애플리케이션에서는 웹 페이지를 IE 모드로 로드해야 할 수 있습니다. Microsoft Edge IE 모드 기능을 사용할 수 있습니다.

Enterprise 모드 사이트 목록의 `compat-mode` 특성을 **기본값**으로 설정해야 할 수도 있습니다. 자세한 내용은 [Enterprise 모드 및 Enterprise 모드 사이트 목록을 참조하세요](/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#enterprise-mode-and-the-enterprise-mode-site-list-1).

> [!TIP]
> 사용자는 Microsoft Edge **about:compat**를 입력하여 이 사이트 목록 및 호환성 모드를 쉽게 볼 수 있습니다.

## <a name="frequently-asked-questions"></a>질문과 대답

### <a name="will-ie-mode-replace-internet-explorer-11"></a>IE 모드가 Internet Explorer 11을 대체하나요?

예, Internet Explorer 11 데스크톱 애플리케이션은 사용 중지되고 2022년 6월 15일에 지원이 중단됩니다. 범위에 있는 내용을 보려면 [수명 주기 FAQ - Internet Explorer](/lifecycle/faq/internet-explorer-microsoft-edge)를 참조하세요. 현재 사용하는 동일한 IE11 앱과 사이트는 Internet Explorer 모드에서 Microsoft Edge로 열 수 있습니다. 자세한 내용은 [Microsoft Edge Windows 10 Internet Explorer의 미래를](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/) 참조하세요.

### <a name="can-i-use-view-in-file-explorer-in-sharepoint-online-on-microsoft-edge"></a>Microsoft Edge SharePoint Online에서 "파일 탐색기 보기"를 사용할 수 있나요?

Microsoft Edge 버전 95부터 SharePoint 온라인 최신 문서 라이브러리**에 대한 파일 탐색기 보기** 기능을 사용하도록 설정할 수 있습니다. 이 환경을 사용자에게 표시하고 작동하려면 [Microsoft Edge "Microsoft Edge SharePoint 페이지에 대한 파일 탐색기 보기 구성" 정책을](/deployedge/microsoft-edge-policies#configureviewinfileexplorer) 사용하도록 설정하고 SharePoint Online 테넌트 구성을 업데이트해야 합니다. 자세한 정보: [Microsoft Edge 파일 탐색기 있는 SharePoint 파일 보기 - Microsoft 365 | SharePoint Microsoft Docs](/SharePoint/sharepoint-view-in-edge).

그러나 파일 탐색기 보기 옵션을 사용하는 대신 SharePoint 외부에서 파일 및 폴더를 관리하는 데 권장되는 방법은 [컴퓨터와 SharePoint 및 Teams 파일을 동기화](https://support.microsoft.com/office/sync-sharepoint-and-teams-files-with-your-computer-6de9ede8-5b6e-4503-80b2-6190f3354a88?ui=en-us&rs=en-us&ad=us)하거나 [SharePoint 파일을 이동하거나 복사하는](https://support.microsoft.com/office/move-or-copy-files-in-sharepoint-00e2f483-4df3-46be-a861-1f5f0c1a87bc?ui=en-us&rs=en-us&ad=us) 것입니다.

### <a name="does-ie-mode-on-microsoft-edge-support-the-no-merge-option-that-was-supported-in-internet-explorer-11"></a>Microsoft Edge IE 모드가 Internet Explorer 11에서 지원된 '병합 안 함' 옵션을 지원하나요?

Microsoft Edge 병합 안 됨 기능에 권장되는 대안은 다음 작업 중 하나입니다.

1. Microsoft Edge 프로필 사용 - 각 프로필은 IE 모드 페이지의 다른 IE 세션에 매핑되므로 병합 안 됨 옵션과 동일하게 동작합니다.
2. `--user-data-dir=<path>` 명령줄을 사용하되 각 세션에 대해 다른 경로를 사용합니다. 필요한 경우 사용자가 Microsoft Edge 시작하고 세션 경로를 변경하는 유틸리티를 실행할 수 있습니다.

이전 옵션 중 어느 것도 시나리오에 대해 작동하지 않는 경우 Microsoft Edge 버전 93부터 Microsoft Edge IE 모드는 병합 없음을 지원합니다. 최종 사용자의 경우 IE 모드 애플리케이션에서 새 브라우저 창이 시작되면 IE11의 병합 안 됨 동작과 같은 별도의 세션에 있습니다.

각 Microsoft Edge 창에 대해 해당 창 내에서 IE 모드 탭을 처음 방문하는 경우 지정된 "병합 안 함" 사이트인 경우 해당 창이 다른 "병합 없음" IE 세션으로 잠깁니다.  이 창은 잠긴 창에서 마지막 IE 모드 탭을 닫을 때까지 다른 모든 Microsoft Edge 창에서 잠깁니다. 이는 사용자가 병합 없이 IE를 시작하고 다른 메커니즘을 사용하여 병합하지 않고 Microsoft Edge 시작할 수 있는 이전 동작을 따릅니다. 새 창에서 열리는 모든 사이트(window.open을 통해)는 부모 프로세스의 병합 특성을 준수합니다.

> [!NOTE]
> 세션 전환은 지원되지 않습니다. 동일한 IE 모드 탭 내의 탐색은 동일한 세션을 사용합니다.

다음 단계를 수행하여 Microsoft Edge 버전 93 이상에서 병합 안 됨 동작의 유효성을 검사할 수 있습니다.

1. Microsoft Edge 버전 93 이상에서 IE 모드가 사용하도록 설정되어 있는지 확인합니다.
2. 병합 형식 특성의 값을 "no-merge"로 설정하여 Enterprise 모드 사이트 목록에서 세션 공유를 방지해야 하는 사이트를 구성할 수 있습니다. 이 특성은 open-in 요소가 Microsoft Edge 설정된 경우에만 적용되지 않습니다. 기본적으로 모든 사이트에는 병합 형식 값이 있습니다. (**참고:** *edge://compat/sitelistmanager* 사용할 수 있는 통합 사이트 목록 관리자 도구에는 사이트를 추가하거나 편집할 때 **병합 안** 됨 확인란이 포함되어 있습니다.)

   ```
   <site url="contoso.com">
   <open-in merge-type="no-merge">IE11</open-in>
   </site>
   ```

3. 병합 안 됨으로 구성된 사이트로 이동합니다. 사이트는 자체적으로 IE 세션에 있어야 합니다. 다른 Microsoft Edge 인스턴스 또는 창을 열고 동일한 사이트로 이동하면 자체 IE 세션에 있어야 합니다. 작업 관리자에는 여러 iexplore.exe 프로세스가 있습니다.

피드백이 있는 경우 Microsoft 지원 또는 [TechCommunity](https://techcommunity.microsoft.com/t5/enterprise/bd-p/EdgeInsiderEnterprise) 포럼의 피드백 채널 중 하나를 통해 연락하세요.

### <a name="can-i-save-links-as-webpages-in-internet-explorer-mode"></a>Internet Explorer 모드에서 링크를 웹 페이지로 저장할 수 있나요?

예, Microsoft Edge의 Internet Explorer 모드용 바로 가기 메뉴에서 다른 이름으로 대상 저장 옵션을 활성화할 수 있습니다. 이렇게 하려면 *컴퓨터 구성 > 관리 템플릿 > Windows 구성 요소 > Internet Explorer*에 있는 그룹 정책 "*Internet Explorer 모드에서 다른 이름으로 저장* 허용"을 구성합니다. 저장 메커니즘은 Internet Explorer에서와 동일하게 작동하며 대상이 html 파일로 저장되면 파일을 다시 열면 페이지가 Microsoft Edge 렌더링됩니다.

웹 페이지로 링크를 저장하는 기능을 사용하려면 다음과 같은 최소 운영 체제 업데이트가 필요합니다.

- Windows 10, 버전 2004, Windows Server 버전 2004, Windows 10, 버전 20H2 : [KB4580364](https://support.microsoft.com/help/4580364/windows-10-update-kb4580364)
- Windows 10, 버전 1903, Windows 10, 버전 1909, Windows Server 버전 1903: [KB4580386](https://support.microsoft.com/help/4580386/windows-10-update-kb4580386)
- Windows 10, 버전 1809, Windows Server 버전 1809, Windows Server 2019: [KB4580390](https://support.microsoft.com/help/4580390/windows-10-update-kb4580390)
- Windows 10, 버전 1803: [KB4586785](https://support.microsoft.com/help/4586785/windows-10-update-kb4586785)
- Windows 10, 버전 1607: [KB4586830](https://support.microsoft.com/help/4586830/windows-10-update-kb4586830)
- Windows 10, 버전 1507: [KB4586787](https://support.microsoft.com/help/4586787/windows-10-update-kb4586787)

### <a name="can-i-test-a-site-in-microsoft-edge-while-it-is-configured-to-open-ie-mode-in-the-enterprise-mode-site-list"></a>Enterprise 모드 사이트 목록에서 IE 모드를 열도록 구성된 동안 Microsoft Edge 사이트를 테스트할 수 있나요?

예, 레거시 사이트를 현대화하는 동안 Microsoft Edge IE 모드로 구성된 애플리케이션을 테스트할 수 있습니다. 이러한 앱을 테스트하려면 [InternetExplorerModeTabInEdgeModeAllowed](/deployedge/microsoft-edge-policies#internetexplorermodetabinedgemodeallowed) 정책을 구성할 수 있습니다. 이 정책을 사용하면 사용자가 에지 모드에서 추가 **ToolsOpen** >  사이트를 > **설정 이상**(줄임표 아이콘 ...)을 선택하여 Microsoft Edge IE **모드 사이트를** 열 수 있습니다.

### <a name="how-can-i-debug-my-legacy-application-while-using-ie-mode-on-microsoft-edge"></a>Microsoft Edge IE 모드를 사용하는 동안 레거시 애플리케이션을 디버그하려면 어떻게 해야 하나요?

IEChooser를 사용하여 Internet Explorer DevTools를 시작하여 IE 모드 탭의 콘텐츠를 디버그할 수 있습니다. IEChooser를 사용하려면 다음 단계를 수행합니다.

1. IEChooser를 엽니다.
   - 실행 대화 상자를 엽니다. 예를 들어 . 키를 누릅니다 `Windows logo key` + `R`.
   - 를 입력 `%systemroot%\system32\f12\IEChooser.exe`한 다음 **확인을** 선택합니다.
2. IEChooser에서 IE 모드 탭의 항목을 선택합니다.

### <a name="my-application-requires-transferring-post-data-between-ie-mode-and-microsoft-edge-is-this-supported"></a>애플리케이션을 사용하려면 IE 모드와 Microsoft Edge 간에 POST 데이터를 전송해야 합니다. 가능합니까?

Microsoft Edge Beta 채널 버전 96부터 Internet Explorer 모드와 Microsoft Edge 간에 전환하는 탐색에는 양식 데이터와 추가 HTTP 헤더가 포함됩니다. 그러나 양식 데이터에 파일 첨부 파일이 포함된 경우 엔진 간에 전송되지 않습니다. [InternetExplorerIntegrationComplexNavDataTypes](/deployedge/microsoft-edge-policies#internetexplorerintegrationcomplexnavdatatypes) 그룹 정책을 사용하여 이러한 탐색에 포함할 데이터 형식을 선택할 수 있습니다.

Microsoft Edge 버전 96 외에도 이 환경에 대해 다음과 같은 Windows 업데이트가 설치되어 있어야 합니다.

- Windows 11 [KB5007262](https://support.microsoft.com/topic/november-22-2021-kb5007262-os-build-22000-348-preview-7f3e18d7-4189-4882-b0e9-afc920253aee) 이상
- Windows Server 2022 [KB5007254](
https://support.microsoft.com/topic/november-22-2021-kb5007254-os-build-20348-380-preview-9a960291-d62e-486a-adcc-6babe5ae6fc1) 이상
- Windows 10 버전 2004; Windows Server 버전 2004; Windows 10 버전; Windows Server 버전 20H2 및 Windows 10 버전 21H1 - [KB5006738](https://support.microsoft.com/topic/october-26-2021-kb5006738-os-builds-19041-1320-19042-1320-and-19043-1320-preview-ccbce6bf-ae00-4e66-9789-ce8e7ea35541) 이상
- Windows 10 버전 1909 [KB5007189](
https://support.microsoft.com/topic/november-9-2021-kb5007189-os-build-18362-1916-91b4647c-9979-4d84-8e64-efc8674e8c1f) 이상

### <a name="where-can-i-find-the-reload-in-internet-explorer-mode-option"></a>"Internet Explorer 모드에서 다시 로드" 옵션은 어디에서 찾을 수 있나요?

이 기능은 Microsoft Edge 버전 92 이상에서 사용할 수 있습니다. 이 옵션을 사용하려면 Microsoft Edge "Internet Explorer 모드 설정에서 사이트를 다시 로드할 수 있도록 허용"을 "허용"으로 구성합니다.  자세한 내용은 [로컬 사이트 목록 환경 사용을 참조하세요](/deployedge/edge-ie-mode-local-site-list#enable-the-local-site-list-experience).

### <a name="where-is-the-file--new-session-option-in-microsoft-edge"></a>Microsoft Edge "파일 > 새 세션" 옵션은 어디에 있나요?

최신 브라우저 솔루션은 Microsoft Edge 여러 프로필을 사용하여 사용할 수 있습니다. 이 기능을 사용하면 다른 계정으로 새 세션을 만들 수 있습니다. 다음 리소스는 여러 프로필의 이점 및 사용 방법에 대한 정보를 제공합니다.

- [비디오: Microsoft Edge 및 ID](/deployedge/microsoft-edge-video-identity)
- [이제 Microsoft Edge 사용하여 직장과 가정에서 여러 프로필을 사용하는 것이 더 쉬워집니다.](https://blogs.windows.com/msedgedev/2020/04/30/automatic-profile-switching/)

### <a name="why-am-i-getting-multiple-authentication-prompts-when-running-a-page-in-ie-mode-on-microsoft-edge"></a>Microsoft Edge IE 모드에서 페이지를 실행할 때 여러 인증 프롬프트가 표시되는 이유는 무엇인가요?

클라이언트 인증서는 IE 모드에서 두 번 요청될 수 있습니다. 처음에는 인증서 선택 대화 상자가 IE 모드로 표시되고 두 번째로 대화 상자가 Microsoft Edge 표시됩니다. 프레임 프로세스와 창 프로세스 모두 인증을 요청해야 합니다.

favicon 캐시를 만든 후에는 캐시를 삭제하지 않는 한 클라이언트 인증서를 다시 요청하지 않습니다. 또는 IIS와 같은 서버 구성에서 favicon에 대한 클라이언트 인증서를 요구하지 않는 규칙을 설정할 수 있습니다.

### <a name="why-are-there-rendering-issues-like-text-wrapping-and-content-truncation-when-child-windows-are-running-in-ie-mode-in-microsoft-edge"></a>자식 창이 Microsoft Edge IE 모드에서 실행되는 경우 텍스트 래핑 및 콘텐츠 잘림과 같은 렌더링 문제가 발생하는 이유는 무엇인가요?

Microsoft Edge IE 모드로 렌더링되는 자식 창의 콘텐츠 영역은 Internet Explorer 11의 콘텐츠 영역과 약간 다릅니다. 웹 페이지가 픽셀 기반 맞춤 또는 위치 지정으로 디자인된 경우 잘못된 렌더링, 텍스트 래핑 등이 발생할 수 있습니다.

Microsoft Edge 버전 95에 두 가지 정책 설정이 추가되어 메서드를 통해 IE 모드 사이트에서 생성된 팝업 창의 높이와 너비에 대한 사용자 지정 조정을 `window.open` 지정할 수 있습니다. 다음 정책을 사용하여 창 크기를 조정할 수 있습니다.

- [InternetExplorerIntegrationWindowOpenHeightAdjustment](/deployedge/microsoft-edge-policies#internetexplorerintegrationwindowopenheightadjustment) - 이 설정을 사용하면 Internet Explorer 모드 사이트에서 생성된 팝업 창의 높이에 대한 사용자 지정 조정을 지정할 수 있습니다.
- [InternetExplorerIntegrationWindowOpenWidthAdjustment](/deployedge/microsoft-edge-policies#internetexplorerintegrationwindowopenwidthadjustment) - 이 설정을 사용하면 Internet Explorer 모드 사이트에서 생성된 팝업 창의 너비에 대한 사용자 지정 조정을 지정할 수 있습니다.

### <a name="why-arent-pop-ups-or-redirected-websites-loading-in-ie-mode-or-in-internet-explorer-11"></a>팝업 또는 리디렉션된 웹 사이트가 IE 모드 또는 Internet Explorer 11에서 로드되지 않는 이유는 무엇인가요?

IE 모드를 구성한 후 특정 웹 사이트, 특히 새 창을 만드는 사이트 또는 리디렉션되는 사이트가 IE 모드로 렌더링되거나 Internet Explorer 11에서 열리지 않을 수 있습니다.

이러한 종류의 리디렉션된 웹 사이트의 경우 사이트 목록 구성에서 사용할 `allow-redirect="true"` 수 있습니다. 자세한 내용은 [업데이트된 스키마 요소를 참조하세요](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance#updated-schema-elements).

### <a name="why-arent-websites-loading-in-ie-mode-when-i-launch-microsoft-edge-for-the-first-time"></a>Microsoft Edge 처음 시작할 때 웹 사이트가 IE 모드로 로드되지 않는 이유는 무엇인가요?

Microsoft Edge IE 모드 설정을 적용하려면 IE 모드 사이트 목록을 다운로드해야 합니다. 브라우저가 시작될 때 이 프로세스가 완료되지 않을 수 있습니다. 웹 사이트를 로드하기 전에 사이트 목록을 강제로 로드할 수 있는 정책을 사용할 수 있습니다. 자세한 내용은 [DelayNavigationsForInitialSiteListDownload](/deployedge/microsoft-edge-policies#delaynavigationsforinitialsitelistdownload) policy를 참조하세요.

### <a name="why-cant-i-open-files-or-pages-that-are-found-by-using-file-urls-in-microsoft-edge"></a>Microsoft Edge file:// URL을 사용하여 찾은 파일이나 페이지를 열 수 없는 이유는 무엇인가요?

Chromium 보안 제한으로 인해 IE 모드를 사용해야 합니다. Microsoft Edge IE 모드 기능을 사용하여 인트라넷 영역 내의 **file://** 프로토콜에 호스트되는 웹 페이지를 로드할 수 있습니다. [IntranetFileLinksEnabled](/deployedge/microsoft-edge-policies#intranetfilelinksenabled) 그룹 정책을 사용하여 이 기능을 사용하도록 설정할 수 있습니다.

## <a name="see-also"></a>참고 항목
  
- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [IE 모드 정보](./edge-ie-mode.md)
- [추가 엔터프라이즈 모드 정보](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
