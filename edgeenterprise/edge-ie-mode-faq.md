---
title: IE 모드 문제 해결 및 FAQ
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 11/03/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge Internet Explorer 모드에 대한 문제 해결 및 FAQ
ms.openlocfilehash: 651fc438e64c21e33787724fb3d5931f0f5b75fa
ms.sourcegitcommit: 4ec03873a85f065d9bfa6203cfe6c3e938f79bc5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "12155152"
---
# <a name="internet-explorer-ie-mode-troubleshooting-and-faq"></a>Internet Explorer(IE) 모드 문제 해결 및 FAQ

> [!NOTE]
> 11 데스크톱 Internet Explorer 사용이 중지되어 2022년 6월 15일에는 지원이 중지됩니다. 범위에 있는 항목의 목록을 보시고 Internet Explorer 데스크톱 앱 사용 중지 [FAQ를 참조하세요.](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549) 현재 사용하는 동일한 IE11 앱과 사이트는 Internet Explorer 모드에서 Microsoft Edge로 열 수 있습니다. 자세한 내용은 Internet Explorer Windows 10 [블로그 게시물에](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/) Microsoft Edge 참조하세요.

이 문서는 Microsoft Edge 버전 77 이상에 대한 문제 해결 팁과 FAQ를 제공합니다.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.

## <a name="troubleshoot-ie-mode"></a>IE 모드 문제 해결

이 섹션의 정보를 사용하여 IE 모드 문제를 진단하고 해결합니다.

### <a name="internet-explorer-mode--general-diagnostic-information"></a>Internet Explorer 모드 일반 진단 정보

Microsoft Edge 호환성 탭에서 Internet Explorer 모드 진단 정보를 볼 수 있습니다. 이 탭을 열려면 *edge://compat/iediagnostic*으로 이동합니다. 이 페이지에는 진단 메시지가 표시될 수 있습니다. 이 페이지는 다음 범주에 대한 구성 정보도 제공합니다.

- **레지스트리 키를 확인.** (확인에 실패한 경우에만 표시됨) 레지스트리에 Internet Explorer 통합이 올바르게 설정되어 있는지 확인합니다. 그렇지 않은 경우 사용자는 수정을 **선택하여** 문제를 해결할 수 있습니다.
- **Internet Explorer 모드.** 구성 및 OS를 기반으로 사용되는 API 버전을 표시합니다. 문제가 있는 경우 Windows 업데이트를 설치하라는 메시지가 표시될 수 있습니다.
- **Internet Explorer 모드 설정.** Internet Explorer 모드의 활성화 여부 및 구성 방법을 보여줍니다.
- **명령줄.** 명령줄 문자열과 명령줄 문자열을 시작하는 데 사용되는 스위치를 Microsoft Edge.
- **그룹 정책 설정.** IE 모드가 그룹 정책과 적용되는 정책을 사용하여 구성되는지 여부를 표시합니다.

### <a name="error-message-to-open-this-page-in-internet-explorer-mode-reinstall-microsoft-edge-with-administrator-privileges"></a>오류 메시지: "이 페이지를 Internet Explorer 모드에서 열려면 관리자 권한으로 Microsoft Edge를 다시 설치하세요."

필요한 업데이트가 모두 없는 경우 이 Windows 있습니다. 필요한 Windows 및 Microsoft Edge 버전에 대해서는 [IE 모드 정보](./edge-ie-mode.md)에 나열된 필수 구성 요소를 참조하세요.

필요한 모든 업데이트를 이미 Windows 다음과 같은 경우 이 오류가 표시될 수 있습니다.

- 기본적으로 사용자 수준으로 설치되는 Canary 채널을 사용하고 있습니다.
- Stable, Beta 또는 Dev 채널을 사용하고 있지만 설치할 때 권한 상승 프롬프트가 나타나면 권한 상승이 취소되었습니다. 권한 상승 프롬프트를 취소하면 설치는 사용자 수준에서 계속됩니다.
- Internet Explorer 11은 Windows 기능에서 사용하지 않도록 설정되었습니다.

가능한 해결 방법:

- 모든 채널에 대해 설치 프로그램을 시스템 수준에서 실행합니다. `installer.exe --system-level`
- Windows 기능에서 Internet Explorer 11을 사용 설정합니다.

Microsoft Edge가 시스템 수준에서 설치되어 있는지 확인하려면 Microsoft Edge 주소 표시줄에 "edge://version"을 입력합니다. 실행 파일 경로에 *C:\Program Files*로 시작하는 경로가 표시되면 이는 시스템 설치를 나타냅니다. 실행 가능 경로가 *C:\Users로*시작하는 경우 관리자 권한으로 Microsoft Edge 다시 설치합니다.

### <a name="error-message-to-open-this-page-in-ie-mode-try-restarting-microsoft-edge"></a>"이 페이지를 IE 모드로 열기 위해 이 페이지를 다시 Microsoft Edge." 오류 메시지가 표시됩니다.

오류가 발생하면 이 오류가 표시될 Internet Explorer. Microsoft Edge를 다시 시작하면 일반적으로 이 오류가 해결됩니다.

### <a name="error-message-turn-off-remote-debugging-to-open-this-site-in-ie-mode-otherwise-it-might-not-work-as-expected"></a>오류 메시지: "이 사이트를 IE 모드에서 열려면 원격 디버깅을 사용하지 않도록 설정하세요. 그렇지 않으면 예상대로 작동하지 않을 수 있습니다."

원격 디버깅을 진행하고 IE 모드에서 실행하도록 구성된 웹 페이지로 이동하면 이 오류가 표시될 수 있습니다. 계속할 수 있지만 페이지는 Microsoft Edge를 사용하여 렌더링됩니다.

### <a name="error-message-could-not-retrieve-emie-site-list"></a>오류 메시지: "EMIE 사이트 목록을 검색할 수 없습니다."

사이트 목록 다운로드가 ** 실패했다는 edge://compat/enterprise 페이지에 이 오류가 표시될 수 있습니다. Microsoft Edge 버전 87부터 [BlockThirdPartyCookies](/deployedge/microsoft-edge-policies#blockthirdpartycookies) 정책을 사용하여 타사 요청에 대해 쿠키가 차단된 경우 HTTP 인증도 허용되지 않습니다. 사이트 목록 다운로드가 성공적으로 진행되도록 [CookiesAllowedForURLs](/deployedge/microsoft-edge-policies#cookiesallowedforurls) 정책을 사용하여 엔터프라이즈 모드 사이트 목록을 호스팅하는 특정 도메인에 대한 쿠키를 허용할 수 있습니다.

## <a name="frequently-asked-questions"></a>자주 묻는 질문

### <a name="will-ie-mode-replace-internet-explorer-11"></a>IE 모드가 Internet Explorer 11을 대체하나요?

예, Internet Explorer 11 데스크톱 응용 프로그램은 사용 중지되어 2022년 6월 15일에는 지원이 중지됩니다. 범위에 있는 내용은 수명 [주기 FAQ -](/lifecycle/faq/internet-explorer-microsoft-edge)Internet Explorer. 현재 사용하는 동일한 IE11 앱과 사이트는 Internet Explorer 모드에서 Microsoft Edge로 열 수 있습니다. 자세한 내용은 에 있는 Internet Explorer [Windows 10 를 Microsoft Edge.](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/)

### <a name="how-can-i-debug-my-legacy-application-while-using-ie-mode-on-microsoft-edge"></a>기존 응용 프로그램에서 IE 모드를 사용하는 동안 레거시 응용 프로그램을 디버그하는 Microsoft Edge?

IEChooser를 사용하여 개발자 Internet Explorer 실행하여 IE 모드 탭의 콘텐츠를 디버그할 수 있습니다. IEChooser를 사용 하 고 다음 단계를 수행 합니다.

1. IEChooser를 열 수 있습니다.
   - 실행 대화 상자를 엽니다. 예를 들어 를 `Windows logo key`  +  `R` 누르고 있습니다.
   - 를 `%systemroot%\system32\f12\IEChooser.exe` 입력하고 확인 을 **선택합니다.**
2. IEChooser에서 IE 모드 탭의 항목을 선택합니다.

### <a name="can-i-test-a-site-in-microsoft-edge-while-it-is-configured-to-open-ie-mode-in-the-enterprise-mode-site-list"></a>사이트가 Microsoft Edge 모드 사이트 목록에서 IE 모드를 열도록 구성된 동안 사이트가 Enterprise 수 있나요?

예, 레거시 사이트를 최신화하는 동안 IE 모드로 구성된 응용 프로그램을 해당 사이트에서 테스트할 Microsoft Edge. 이를 위해 명령줄 플래그를 Microsoft Edge `--ie-mode-test` 실행하면 됩니다. 실행 중인 다른 Microsoft Edge 없는지 확인 그런 다음 **** 추가 설정(타원 아이콘 ...)를 선택할 수 있습니다. **> 에지 모드에서 > 열기 도구를 제공합니다.**

### <a name="can-i-use-view-in-file-explorer-in-sharepoint-online-on-microsoft-edge"></a>SharePoint Online에서 "파일 탐색기에서 보기"를 사용할 수 Microsoft Edge?

Microsoft Edge 버전 95부터 온라인 최신 문서 **** 라이브러리에 대해 파일 탐색기에서 보기 기능을 SharePoint 수 있습니다. 이 환경을 표시하고 사용자에게 작동하려면 "Microsoft Edge SharePoint 페이지의 파일 탐색기 기능 구성 [SharePoint"](/deployedge/microsoft-edge-policies#configureviewinfileexplorer) 정책을 사용하도록 설정하고 Microsoft Edge Online 테넌트 구성을 업데이트해야 합니다. 자세한 내용은 다음을 SharePoint 파일 탐색기를 사용하여 파일 Microsoft Edge - SharePoint [보기를 Microsoft 365 | Microsoft Docs.](/SharePoint/sharepoint-view-in-edge)

그러나 파일 탐색기에서 보기 옵션을 사용하는 대신 파일 탐색기 외부의 파일 및 폴더를 관리하는 SharePoint 권장되는 방법은 컴퓨터와 파일을 동기화하고 SharePoint Teams 파일을 동기화하거나 에서 파일을 이동하거나 [복사하는 SharePoint.](https://support.microsoft.com/office/move-or-copy-files-in-sharepoint-00e2f483-4df3-46be-a861-1f5f0c1a87bc?ui=en-us&rs=en-us&ad=us) [](https://support.microsoft.com/office/sync-sharepoint-and-teams-files-with-your-computer-6de9ede8-5b6e-4503-80b2-6190f3354a88?ui=en-us&rs=en-us&ad=us)

### <a name="does-ie-mode-on-microsoft-edge-support-the-no-merge-option-that-was-supported-in-internet-explorer-11"></a>IE 모드가 Microsoft Edge 11에서 지원되는 '병합 없음' 옵션을 Internet Explorer 있습니까?

다음 작업 중 하나는 Microsoft Edge 병합하지 않음 기능에 대한 권장 대안입니다.

1. 프로필 Microsoft Edge - 각 프로필은 IE 모드 페이지의 다른 IE 세션에 매핑되어 병합 금지 옵션과 동일하게 사용됩니다.
2. `--user-data-dir=<path>` 명령줄을 사용하되 각 세션에 대해 다른 경로를 사용합니다. 필요한 경우, 사용자가 Microsoft Edge를 시작하고 세션의 경로를 변경하는 유틸리티를 만들 수 있습니다.

이전 옵션 중 어느 옵션도 시나리오에 대해 작동하지 Microsoft Edge 버전 93부터는 IE 모드가 Microsoft Edge 지원하지 않습니다. 최종 사용자의 경우 IE 모드 응용 프로그램에서 새 브라우저 창을 시작하면 IE11의 병합 금지 동작과 같은 별도의 세션에 있습니다.

각 Microsoft Edge 창에 대해 해당 창 내에서 IE 모드 탭을 처음 방문하면 지정된 "병합 안함" 사이트인 경우 해당 창이 다른 "병합 안 함" IE 세션에 잠겨 있습니다.  이 창은 잠긴 창에서 마지막 IE 모드 Microsoft Edge 닫을 때까지 다른 모든 창에서 잠겨 있습니다. 이는 사용자가 병합하지 않고 IE를 시작하고 다른 메커니즘을 사용하여 병합하지 않고 Microsoft Edge 수 있는 이전 동작과 같습니다. window.open을 통해 새 창에서 여는 모든 사이트는 부모 프로세스의 병합 특성을 존중합니다.

> [!NOTE]
> 세션 전환은 지원되지 않습니다. 동일한 IE 모드 탭 내의 탐색은 동일한 세션을 사용합니다.

다음 단계를 수행하여 Microsoft Edge 버전 93 이상에서 병합 없음 동작의 유효성을 검사할 수 있습니다.

1. IE 모드가 버전 93 이상에서 Microsoft Edge 설정되어 있는지 확인합니다.
2. 병합 유형 특성 값을 "병합 안Enterprise 모드 사이트 목록에서 세션 공유를 방지해야 하는 사이트를 구성할 수 있습니다. 이 특성은 open-in 요소가 기본 설정으로 설정된 Microsoft Edge. 기본적으로 모든 사이트에는 병합 형식 값이 있습니다. (참고: 사이트에서 사용할 수 있는 ** 통합 사이트 목록 **** 관리자 edge://compat/sitelistmanager 추가하거나 편집할 때 병합 안 함을 선택합니다.)****

   ```
   <site url="contoso.com">
   <open-in merge-type="no-merge">IE11</open-in>
   </site>
   ```

3. 병합 없음으로 구성된 사이트로 이동합니다. 사이트는 자체의 IE 세션에 있습니다. 다른 Microsoft Edge 인스턴스 또는 창을 열고 동일한 사이트로 이동하는 경우 해당 사이트는 자체 IE 세션에 있습니다. 작업 관리자의 iexplore.exe 프로세스가 여러 개 있습니다.

피드백이 있는 경우 피드백 채널인 Microsoft 지원 또는 [TechCommunity](https://techcommunity.microsoft.com/t5/enterprise/bd-p/EdgeInsiderEnterprise) 포럼 중 하나를 통해 방문하세요.

### <a name="can-i-save-links-as-webpages-in-internet-explorer-mode"></a>Internet Explorer 모드에서 링크를 웹 페이지로 저장할 수 있나요?

예, Microsoft Edge의 Internet Explorer 모드용 바로 가기 메뉴에서 다른 이름으로 대상 저장 옵션을 활성화할 수 있습니다. 이렇게하려면 컴퓨터 구성 >** 관리 템플릿 및 구성 요소 Internet Explorer 모드에 있는 "다른 Internet Explorer 대상 저장 허용" 그룹 정책을 *> Windows > Internet Explorer.* 저장 메커니즘은 Internet Explorer에서와 동일하게 작동하며, 대상이 html 파일로 저장되는 경우 파일을 다시 열면 Microsoft Edge에서 페이지가 렌더링됩니다.

링크를 웹 페이지로 저장하려면 다음과 같은 최소 운영 체제 업데이트가 필요합니다.

- Windows 10, 버전 2004, Windows Server 버전 2004, Windows 10, 버전 20H2 : [KB4580364](https://support.microsoft.com/help/4580364/windows-10-update-kb4580364)
- Windows 10, 버전 1903, Windows 10, 버전 1909, Windows Server 버전 1903: [KB4580386](https://support.microsoft.com/help/4580386/windows-10-update-kb4580386)
- Windows 10, 버전 1809, Windows Server 버전 1809, Windows Server 2019: [KB4580390](https://support.microsoft.com/help/4580390/windows-10-update-kb4580390)
- Windows 10, 버전 1803: [KB4586785](https://support.microsoft.com/help/4586785/windows-10-update-kb4586785)
- Windows 10, 버전 1607: [KB4586830](https://support.microsoft.com/help/4586830/windows-10-update-kb4586830)
- Windows 10, 버전 1507: [KB4586787](https://support.microsoft.com/help/4586787/windows-10-update-kb4586787)

### <a name="can-i-test-a-site-in-microsoft-edge-while-it-is-configured-to-open-ie-mode-in-the-enterprise-mode-site-list"></a>사이트가 Microsoft Edge 모드 사이트 목록에서 IE 모드를 열도록 구성된 동안 사이트가 Enterprise 수 있나요?

예, 레거시 사이트를 최신화하는 동안 기존 사이트에서 IE 모드 사이트를 테스트할 Microsoft Edge. 이를 위해 명령줄 플래그를 Microsoft Edge `--ie-mode-test` 실행하면 됩니다. 실행 중인 다른 Microsoft Edge 없는지 확인 그런 **** 다음 설정 이상(타원 아이콘) ...을 선택합니다. **> 에지 모드에서 > 열기 도구를 제공합니다.**

### <a name="my-application-requires-transferring-post-data-between-ie-mode-and-microsoft-edge-is-this-supported"></a>응용 프로그램에는 IE 모드와 IE 모드 간에 POST 데이터를 전송해야 Microsoft Edge. 가능합니까?

Microsoft Edge Beta 채널 버전 96부터 Internet Explorer 모드와 Microsoft Edge 전환하는 탐색에는 양식 데이터와 추가 HTTP 헤더가 포함됩니다. 그러나 양식 데이터에 첨부 파일이 포함된 경우 엔진 간에 전송되지 않습니다. [InternetExplorerIntegrationComplexNavDataTypes](/deployedge/microsoft-edge-policies#internetexplorerintegrationcomplexnavdatatypes) 그룹 정책을 사용하여 이러한 탐색에 포함될 데이터 형식을 선택할 수 있습니다.

이 Microsoft Edge 버전 96 외에도 이 환경을 위해 다음 Windows 업데이트가 설치되어야 합니다.

- Windows 10 버전 2004; Windows 서버 버전 2004; Windows 10 버전; Windows 서버 버전 20H2 및 Windows 10 버전 21H1 - KB5006738 이상

  > [!NOTE]
  > Windows 10 19H2, Windows Server 2022 및 Windows 11 업데이트가 곧 제공될 예정입니다.

## <a name="see-also"></a>참고 항목
  
- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [IE 모드 정보](./edge-ie-mode.md)
- [추가 엔터프라이즈 모드 정보](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
