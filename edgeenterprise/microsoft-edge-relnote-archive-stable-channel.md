---
title: Microsoft Edge 안정 채널에 대한 보관된 릴리스 정보
ms.author: aguta
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge 안정 채널에 대한 보관된 릴리스 정보
ms.openlocfilehash: d50da924c3c78e38eb55b30cf219145d19fe9816
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642394"
---
# <a name="archived-release-notes-for-microsoft-edge-stable-channel"></a>Microsoft Edge 안정 채널에 대한 보관된 릴리스 정보

이 릴리스 정보는 Microsoft Edge 안정 채널에 포함된 새로운 기능 및 비보안 업데이트에 대한 정보를 제공합니다. 모든 보안 업데이트는 [여기](microsoft-edge-relnotes-security.md)에서 확인할 수 있습니다.

## <a name="version-88070581-february-25"></a>버전 88.0.705.81: 2월 25일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-88070574-february-17"></a>버전 88.0.705.74: 2월 17일

안정 채널 보안 업데이트는 [여기](./microsoft-edge-relnotes-security.md#february-17-2021)에서 확인할 수 있습니다.

## <a name="version-88070568-february-11"></a>버전 88.0.705.68: 2월 11일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-88070563-february-5"></a>버전 88.0.705.63: 2월 5일

> [!IMPORTANT]
> 이 업데이트에는 [CVE-2021-21148](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21148)이 포함되어 있으며 Chromium 팀은 이 취약점이 악용된 것으로 보고했습니다.

안정 채널 보안 업데이트는 [여기](./microsoft-edge-relnotes-security.md#february-5-2021)에서 확인할 수 있습니다.

## <a name="version-88070562-february-4"></a>버전 88.0.705.62: 2월 4일

안정 채널 보안 업데이트는 [여기](./microsoft-edge-relnotes-security.md#february-4-2021)에서 확인할 수 있습니다.

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-88070556-january-28"></a>버전 88.0.705.56: 1월 28일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-88070553-january-26"></a>버전 88.0.705.53: 1월 26일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-88070550-january-21"></a>버전 88.0.705.50: 1월 21일

안정 채널 보안 업데이트는 [여기](./microsoft-edge-relnotes-security.md#january-21-2021)에서 확인할 수 있습니다.

<!--- begin major 88  --->
### <a name="feature-updates"></a>기능 업데이트

- **지원 중단:**

  - FTP 프로토콜을 더 이상 지원하지 않습니다. 레거시 FTP 프로토콜에 대한 지원이 Microsoft Edge에서 제거되었습니다. FTP 링크로 이동하려고 하면 브라우저가 운영 체제에서 FTP 링크를 처리하기 위해 외부 응용 프로그램을 열도록 지시합니다. 또는 IT 관리자가 FTP 프로토콜을 사용하는 사이트에 대해 IE 모드를 사용하도록 Microsoft Edge를 구성할 수 있습니다.
  - Adobe Flash 지원이 제거됩니다. Microsoft Edge 베타 버전 88부터 Adobe Flash 기능과 지원이 제거됩니다. 자세한 정보: [Adobe Flash Player 지원 종료 시 업데이트 - Microsoft Edge 블로그(windows.com)](https://blogs.windows.com/msedgedev/2020/09/04/update-adobe-flash-end-support/)

- **인증:**

  - 이제 하위 수준 Windows에서 Azure AD(Azure Active Directory) 계정과 Microsoft MSA(Microsoft 계정)에 SSO(Single Sign On)를 사용할 수 있습니다. 하위 수준의 Microsoft Windows(7, 8.1)에서 Microsoft Edge에 로그인한 사용자는 회사 및 Microsoft 계정(예: bing.com, office.com, msn.com, outlook.com)으로 Single Sign-On을 허용하도록 구성된 웹 사이트에 자동으로 로그인됩니다.<br>참고: 사용자는 이 기능을 활용하기 위해 Microsoft Edge 88 이전 버전에서 Microsoft Edge에 로그인한 경우, 로그아웃한 후 다시 로그인해야 할 수 있습니다.
  
  - 비 Azure AD Microsoft Edge 프로필의 시스템에서 모든 Windows Azure Active Directory(Azure AD) 계정을 사용하여 사이트를 작업하는 SSO(Single Sign-On)입니다. 이 기능은 직장/학교 계정으로 로그인하지 않고 게스트 또는 비공개가 아닌 모든 프로필에 사용할 수 있으며 해당 프로필을 사용하여 운영 체제에서 로그인한 모든 직장/학교 계정의 사용을 허용합니다. 이 기능은 **설정** > **프로필** > **프로필 기본 설정** > **프로필을 사용하여 회사 또는 학교에 대한 Sigle Sign-On 허용**에서 구성할 수 있습니다.
  
    > [!NOTE]
    > "Microsoft Edge 프로필을 사용하는 모든 Windows 계정에 대한 SSO(Single Sign-On)"는 1월 21일 릴리스 정보에 대한 업데이트입니다.

- **세션을 종료하기 위한 키오스크 모드 옵션입니다**. 이제 "세션 종료" 단추를 키오스크 모드 공개 검색 환경에서 사용할 수 있습니다. 이 기능을 사용하면 Microsoft Edge를 닫을 때 브라우저 데이터 및 설정이 삭제됩니다. 키오스크 모드 기능 및 로드맵, [Microsoft Edge 키오스크 모드 구성](./microsoft-edge-configure-kiosk-mode.md)에 대해 자세히 알아보세요요.

- **보안 및 개인 정보:**

  - 온라인 유출에서 사용자의 암호가 발견되면 경고가 생성됩니다. 사용자 암호는 알려진 위반된 자격 증명의 리포지토리와 대조하여 일치하는 것이 발견되는 경우 사용자에게 경고를 보냅니다. 보안 및 개인 정보 보호를 위해 사용자 암호는 유출된 자격 증명의 데이터베이스와 대조할 때 해시 및 암호화됩니다.
  - 혼합 콘텐츠를 자동으로 업그레이드합니다. HTTPS를 통해 전달되는 보안 페이지에는 비보안 HTTP를 통해 제공되는 참조 이미지를 포함할 수 있습니다. Microsoft Edge 88에서 개인 정보 및 보안을 개선하기 위해 이러한 이미지는 대신 HTTPS를 통해 검색됩니다. HTTPS를 통해 이미지를 사용할 수 없는 경우 이미지가 로드되지 않습니다.
  - 사이트 및 최근 활동으로 사이트 사용 권한을 봅니다. Microsoft Edge 88부터는 사용자가 사이트 사용 권한을 보다 쉽게 관리할 수 있습니다. 권한 유형이 아닌 웹 사이트별로 사용 권한을 볼 수 있습니다. 또한 사용자에게 사이트 사용 권한에 대한 최근 변경 내용을 모두 표시하는 최근 활동 섹션이 추가되었습니다.
  - 브라우저 쿠키에 대한 컨트롤을 향상시켰습니다. Microsoft Edge 88부터 사용자는 타사 쿠키에 영향을 주지 않고 타사 쿠키를 삭제할 수 있습니다. 또한 사용자는 자사 또는 타사별로 쿠키를 필터링하고 이름, 쿠키 수, 저장 및 마지막으로 수정된 데이터의 양을 기준으로 정렬할 수 있습니다.

- **암호:**

  - 암호 생성기. Microsoft Edge는 새 계정에 등록하거나 기존 암호를 변경할 때 사용할 수 있는 강력한 암호 생성기를 기본 제공합니다. 암호 필드에서 브라우저 추천 암호 드롭다운을 찾고 선택하는 경우, 나중에 쉽게 사용할 수 있도록 브라우저에 자동으로 저장되고 디바이스 전체에서 동기화됩니다.
  - 암호 모니터. 브라우저에 저장된 암호가 유출된 자격 증명 목록에 있는 암호와 일치하는 경우 Microsoft Edge에서 사용자에게 알리고 암호를 업데이트하라는 메시지가 표시됩니다. 암호 모니터는 사용자 대신 일치하는 일치 항목을 검색하며 기본적으로 설정되어 있습니다.
  - 암호 편집. 이제 Microsoft Edge 설정에서 저장된 암호를 직접 편집할 수 있습니다. Microsoft Edge 외부에서 암호를 업데이트할 경우 설정에서 저장된 항목을 편집하여 저장된 이전 암호를 새 암호로 쉽게 바꿀 수 있습니다. 

- **시작 향상을 통해 Microsoft Edge 시작 속도를 개선합니다**. Microsoft Edge 시작 속도를 개선하기 위해 시작 향상이라는 기능을 개발했습니다. 시작 향상을 사용하면 Microsoft Edge가 백그라운드에서 실행되어 Microsoft Edge가 더 빠르게 실행됩니다. 참고: 이 기능은 실험을 활성화한 임의로 선택된 사용자 그룹으로 제한됩니다. 이러한 사용자는 기능 팀에 피드백을 제공합니다.

- **생산성:**

  - 세로 탭을 사용하여 생산성 및 멀티태스킹을 향상합니다. 가로 탭 수가 늘어나면 사이트 제목이 잘리기 시작하고 각 탭이 축소될 때 탭 컨트롤이 손실됩니다. 따라서 사용자가 탭을 검색, 전환 및 관리하는 데 더 많은 시간을 소비하고 당면한 작업에 더 적은 시간을 소비하므로 사용자 워크플로가 중단됩니다. 세로 탭을 통해 사용자가 탭을 측면으로 이동시킬 수 있습니다. 여기서 세로로 정렬된 아이콘과 더 긴 사이트 제목을 통해 열 탭을 빠르게 검색, 식별 및 전환할 수 있습니다.
  - 생년월일 필드를 자동으로 채웁니다. Microsoft Edge는 이미 주소, 이름, 전화 번호 등의 사용자 데이터를 자동으로 채워서 양식을 작성하고 온라인으로 계정을 만드는 동안 시간과 노력을 절약하는 데 도움이 됩니다. Microsoft Edge는 이제 사용자가 저장하고 자동으로 채울 수 있는 생년월일 필드를 지원합니다. 사용자는 프로필 설정에서 언제든지 이 정보를 보고 편집하고 삭제할 수 있습니다.
  - 기록에서 최근에 닫은 탭의 개선된 기능입니다. 최근에 닫은 탭은 이전 세션이 아닌 과거 검색 세션에서 마지막 25개 탭과 창을 유지합니다. 사용자는 새 기록 환경에서 최근에 닫은 항목을 선택하여 열려 있던 모든 탭을 볼 수 있습니다.
  - 기본적으로 "오늘 하루를 한 눈에 보기" 기능이 사용 설정되어 있습니다. Microsoft Edge 버전 88부터 정보 근로자는 새 탭 페이지(NTP)에서 지능형 생산성 기능을 활용할 수 있습니다. Microsoft Edge 87 사용자도 Microsoft Edge 88이 릴리스된 후 2주 이내에 이러한 기능을 경험할 수 있습니다. 사용자는 회사 또는 학교 계정으로 로그인하여 M365 Graph에서 제공하는 개인 밎춤형 관련 콘텐츠를 사용할 수 있습니다. 사용자는 "오늘 하루를 한 눈에 보기" 모듈을 빠르게 스캔하여 모임 및 최근 작업을 쉽게 추적하고, 사용하고자 하는 응용 프로그램을 빠르게 시작할 수 있습니다.

- **기록 및 탭 동기화 열기**. 이제 사용자가 기록 및 탭 동기화 열기를 사용할 수 있습니다. 이러한 기능을 활성화하면 사용자가 모든 동기화 장치에서 검색 기록과 탭 동기화 열기를 사용할 수 있어 하여 중단한 위치를 선택하는 데 도움이 됩니다. 동기화 및 브라우저 기록 정책을 업데이트했으므로 이제 사용자가 Microsoft Edge를 사용하여 모든 장치에 연결되고 생산성이 향상됩니다. [자세한 내용을 알아보세요](https://blogs.windows.com/windowsexperience/2021/01/21/this-year-lets-resolve-to-make-the-most-of-our-time-online-and-better-protect-ourselves-from-online-threats/).

- **PDF:**

  - PDF 문서가 책 보기(두 페이지)로 표시됩니다. Microsoft Edge 버전 88부터 사용자는 단일 페이지 또는 두 페이지 책 보기에서 PDF 문서를 볼 수 있습니다. 보기를 변경하려면 도구 모음에서 **페이지 보기** 단추를 클릭합니다.
  - PDF 파일에 대한 고정된 텍스트 메모를 지원합니다. Microsoft Edge 버전 87부터 사용자는 PDF 파일의 모든 텍스트에 입력된 텍스트 메모를 추가할 수 있습니다.

- **글꼴:**

  - 브라우저 아이콘은 Fluent 디자인 시스템으로 업데이트됩니다. 브라우저에서 Fluent 디자인에 대한 지속적인 작업의 일환으로 새로운 Microsoft 아이콘 시스템에 더 가깝게 아이콘을 정렬하도록 변경했습니다. 이러한 변경 사항은 탭, 주소 표시줄, 다양한 메뉴에 있는 탐색 및 길 찾기 아이콘을 비롯한 많은 하이 터치 사용자 인터페이스에 영향을 미치게 됩니다.
  - 글꼴 렌더링을 향상시켰습니다. 텍스트 렌더링이 향상되어 명확성을 높이고 흐림을 줄입니다.

### <a name="policy-updates"></a>정책 업데이트

#### <a name="new-policies"></a>새 정책

18개의 새 정책이 추가되었습니다. [Microsoft Edge Enterprise 방문 페이지](https://www.microsoft.com/edge/business/download)에서 업데이트된 관리 템플릿을 다운로드할 수 있습니다. 다음과 같은 새 정책이 추가되었습니다.

- [BasicAuthOverHttpEnabled](./microsoft-edge-policies.md#basicauthoverhttpenabled) - HTTP에 대해 기본 인증을 허용합니다.
- [BlockExternalExtensions](./microsoft-edge-policies.md#blockexternalextensions) - 외부 확장이 설치되지 않도록 차단합니다.
- [InternetExplorerIntegrationLocalFileAllowed](./microsoft-edge-policies.md#internetexplorerintegrationlocalfileallowed) - Internet Explorer 모드에서 로컬 파일 시작을 허용합니다.
- [InternetExplorerIntegrationLocalFileExtensionAllowList](./microsoft-edge-policies.md#internetexplorerintegrationlocalfileextensionallowlist) - Internet Explorer 모드 파일 확장명 허용 목록에서 로컬 파일을 엽니다.
- [InternetExplorerIntegrationLocalFileShowContextMenu](./microsoft-edge-policies.md#internetexplorerintegrationlocalfileshowcontextmenu) - Internet Explorer 모드에서 링크를 열려면 상황에 맞는 메뉴를 표시합니다.
- [IntranetRedirectBehavior](./microsoft-edge-policies.md#intranetredirectbehavior) - 인트라넷 리디렉션 동작입니다.
- [PrinterTypeDenyList](./microsoft-edge-policies.md#printertypedenylist) - 거부 목록에서 프린터 유형을 사용하지 않도록 설정합니다.
- [ShowMicrosoftRewards](./microsoft-edge-policies.md#showmicrosoftrewards) - Microsoft Rewards 환경을 표시합니다.
- [SleepingTabsEnabled](./microsoft-edge-policies.md#sleepingtabsenabled) - 절전 모드 탭을 구성합니다.
- [SleepingTabsTimeout](./microsoft-edge-policies.md#sleepingtabstimeout) - 절전 모드 탭에 대한 백그라운드 탭 비활성 시간 제한을 설정합니다.
- [SleepingTabsBlockedForUrls](./microsoft-edge-policies.md#sleepingtabsblockedforurls) - 특정 사이트에서 절전 모드 탭을 차단합니다.
- [StartupBoostEnabled](./microsoft-edge-policies.md#startupboostenabled) - 시작 부스트를 사용하도록 설정합니다.
- [TargetBlankImpliesNoOpener](./microsoft-edge-policies.md#targetblankimpliesnoopener) - _blank를 대상으로 하는 링크에 대해 window.opener를 설정하지 않습니다.
- [UpdatePolicyOverride](./microsoft-edge-policies.md#updatepolicyoverride) - Microsoft Edge 업데이트가 Microsoft Edge에서 사용 가능한 업데이트를 처리하는 방법을 지정합니다.
- [VerticalTabsAllowed](./microsoft-edge-policies.md#verticaltabsallowed) - 브라우저 측면의 탭에 대한 세로 레이아웃의 가용성을 구성합니다.
- [WebRtcAllowLegacyTLSProtocols](./microsoft-edge-policies.md#webrtcallowlegacytlsprotocols) - WebRTC에서 레거시 TLS/DTLS 다운그레이드를 허용합니다.
- [WebWidgetAllowed](./microsoft-edge-policies.md#webwidgetallowed) - 웹 위젯을 사용하도록 설정합니다.
- [WebWidgetIsEnabledOnStartup](./microsoft-edge-policies.md#webwidgetisenabledonstartup) - Windows 시작 시 웹 위젯을 허용합니다.

#### <a name="deprecated-policies"></a>사용되지 않는 정책

- [ProactiveAuthEnabled](./microsoft-edge-policies.md#proactiveauthenabled) - 사전 인증을 사용하도록 설정합니다.
- [ProxyBypassList](./microsoft-edge-policies.md#proxybypasslist) - 프록시 우회 규칙을 구성합니다.
- [ProxyMode](./microsoft-edge-policies.md#proxymode) - 프록시 서버 설정을 구성합니다.
- [ProxyPacUrl](./microsoft-edge-policies.md#proxypacurl) - 프록시 .pac 파일 URL을 설정합니다.
- [ProxyServer](./microsoft-edge-policies.md#proxyserver) - 프록시 서버의 주소 또는 URL을 구성합니다.
- [WebDriverOverridesIncompatiblePolicies](./microsoft-edge-policies.md#webdriveroverridesincompatiblepolicies) - WebDriver가 호환되지 않는 정책을 재정의할 수 있도록 허용합니다.

### <a name="obsoleted-policies"></a>폐기된 정책

- [AllowPopupsDuringPageUnload](./microsoft-edge-policies.md#allowpopupsduringpageunload) - 페이지가 언로드하는 동안 팝업을 표시하도록 허용합니다.
- [DefaultPluginsSetting](./microsoft-edge-policies.md#defaultpluginssetting) - 기본 Adobe Flash 설정입니다.
- [PluginsAllowedForUrls](./microsoft-edge-policies.md#pluginsallowedforurls) - 특정 사이트에서 Adobe Flash 플러그 인을 허용합니다.
- [PluginsBlockedForUrls](./microsoft-edge-policies.md#pluginsblockedforurls) - 특정 사이트에서 Adobe Flash 플러그 인을 차단합니다.
- [RunAllFlashInAllowMode](./microsoft-edge-policies.md#runallflashinallowmode) - Adobe Flash 콘텐츠 설정을 모든 콘텐츠로 확장합니다.
<!--- end major 88  --->
## <a name="version-87066475-january-7"></a>버전 87.0.664.75: 1월 7일

안정 채널 보안 업데이트는 [여기](./microsoft-edge-relnotes-security.md#january-7-2021)에서 확인할 수 있습니다.

## <a name="version-87066466-december-17"></a>버전 87.0.664.66: 12월 17일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-87066460-december-10"></a>버전 87.0.664.60: 12월 10일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-87066457-december-7"></a>버전 87.0.664.57: 12월 7일

다양한 버그와 성능 문제를 해결했습니다. 안정 채널 보안 업데이트는 [여기](./microsoft-edge-relnotes-security.md#december-7-2020)에서 확인할 수 있습니다.

## <a name="version-87066455-december-3"></a>버전 87.0.664.55: 12월 3일

다양한 버그와 성능 문제를 해결했습니다. 이 릴리스에서는 다음 기능이 업데이트되었습니다.

- **기본적으로 쇼핑은 사용하도록 설정되어 있습니다**. Microsoft Edge 버전 87부터 시작하여, 엔터프라이즈 사용자는 Microsoft Edge에서 쇼핑 기능의 혜택을 누릴 수 있습니다. Microsoft Edge는 쇼핑 기능을 통해 사용자가 온라인으로 쇼핑을 하는 동안 쿠폰 및 더 나은 가격을 찾을 수 있도록 도와줍니다. (이 쿠폰 체험은 Stable 버전 87.0.664.41로 출시되었습니다). 이제 이 업데이트를 통해 가격 비교 환경을 이용할 수 있습니다. 이 기능은 [EdgeShoppingAssistantEnabled](./microsoft-edge-policies.md#edgeshoppingassistantenabled) 정책을 사용하여 구성할 수 있습니다. Microsoft 쇼핑에 대한 정보는 [블로그](https://blogs.windows.com/windowsexperience/2020/11/19/finish-up-that-holiday-shopping-with-new-features-from-microsoft-edge-and-bing/) 및 [자세한 정보](/microsoft-edge/privacy-whitepaper#shopping)를 참조하세요.

## <a name="version-87066452-november-30"></a>버전 87.0.664.52: 11월 30일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-87066447-november-23"></a>버전 87.0.664.47: 11월 23일

다양한 버그와 성능 문제를 해결했습니다.

<!-- begin major 87 --->
## <a name="version-87066441-november-19"></a>버전 87.0.664.41: 11월 19일

안정 채널 보안 업데이트는 [여기](./microsoft-edge-relnotes-security.md#november-19-2020)에서 확인할 수 있습니다.

### <a name="feature-updates"></a>기능 업데이트

- **Internet Explorer에서 Microsoft Edge로 호환되지 않는 사이트에 대해 자동으로 리디렉션**됩니다. Microsoft Edge 87 안정 업데이트부터 시작하여 Internet Explorer에 비호환성 메시지를 표시하는 공용 웹 사이트는 자동으로 Microsoft Edge로 리디렉션됩니다. 자세한 내용을 알아보고 이 환경을 구성하려면 [호환되지 않는 사이트 리디렉션](./edge-learnmore-neededge.md)을 참조하세요.

- **키오스크 모드 개인 정보 보호 기능이 사용으로 설정되었습니다**. Microsoft Edge 버전 87부터 시작하여 사용자 데이터의 개인 정보 보호와 관련하여 기업에 도움이 되는 키오스크 모드 기능이 사용으로 설정됩니다. 이 기능을 사용하면 종료 시 사용자 데이터를 지우고 다운로드한 파일을 삭제하고 지정된 유휴 시간 후에 구성된 시작 환경을 재설정하는 등의 작업을 수행할 수 있습니다. [Microsoft Edge 키오스크 모드를 구성](./microsoft-edge-configure-kiosk-mode.md)하는 방법에 대해 자세히 알아보기

- **장바구니 기능은 기본적으로 사용하도록 설정**됩니다. Microsoft Edge 버전 87부터 시작하여, 엔터프라이즈 사용자는 Edge에서 쇼핑 기능의 혜택을 누릴 수 있습니다. Microsoft Edge는 쇼핑 기능을 통해 사용자가 온라인으로 쇼핑을 하는 동안 쿠폰 및 더 나은 가격을 찾을 수 있도록 도와줍니다. 이 업데이트로 쿠폰 환경을 사용할 수 있으며, 가격 비교는 향후 Microsoft Edge 87에 예정된 업데이트에서 릴리스될 예정입니다. 이 기능은 [EdgeShoppingAssistantEnabled](./microsoft-edge-policies.md#edgeshoppingassistantenabled) 정책을 통해 구성할 수 있습니다. [블로그](https://blogs.windows.com/windowsexperience/2020/11/19/finish-up-that-holiday-shopping-with-new-features-from-microsoft-edge-and-bing/)를 참조하고 Microsoft 쇼핑에 대해 [자세히 알아보세요](/microsoft-edge/privacy-whitepaper#shopping).

- **ClickOnce 배포는 기본적으로 사용하도록 설정됩니다**. ClickOnce는 기본적으로 Microsoft Edge 87에서 사용할 수 있습니다. 이로 인해 기업이 소프트웨어를 배포하고 Microsoft Edge 레거시 브라우저 동작에 더 잘 부합할 수 있도록 장벽을 낮출 수 있습니다. Microsoft Edge 87에서 시작하는 ClickOnceEnabled 정책의 "구성되지 않음" 상태는 새 기본 ClickOnce 상태인 사용 허용(이전 기본 상태인 사용 안 함과 비교)을 반영합니다.

- **엔터프라이즈 새 탭 페이지(NTP)는 생산성을 사용자 지정, 작업 관련 피드 콘텐츠로 통합합니다**. 엔터프라이즈 NTP는 회사 또는 학교 계정으로 로그인한 사용자에게 Microsoft에서 제공하는 Office 365 생산성 페이지를 단일 페이지에서 조직되고 맞춤화된 작업 관련 회사 및 업계 피드와 혼합합니다. 사용자는 익숙한 Office 365 콘텐츠 및 Bing에서 제공하는 비즈니스용 Microsoft Search를 인식할 수 있습니다. 또한 조직의 사용 가능한 콘텐츠 및 모듈에서 가장 관련성이 높은 콘텐츠를 선택하여 "내 피드"를 쉽게 사용자 지정할 수 있습니다. IT 관리자는 Microsoft 365 관리 센터로 이동하여 Edge 새 탭 페이지에 대해 선택된 업계를 포함하여 조직의 뉴스 피드 설정을 제어할 수 있습니다. [자세히 알아보기](https://blogs.windows.com/msedgedev/2020/10/29/enterprise-new-tab-page-my-feed/)

- **개인 정보 보호 및 보안:**

  - 정책 구성 사이트에 대한 TLS 토큰 바인딩을 지원합니다. TLS 토큰 바인딩은 토큰 절도 공격을 방지하여 쿠키를 처음 설정했던 장치 외의 다른 장치에서 사용할 수 없도록 하는 데 도움이 됩니다. TLS 토큰 바인딩을 사용하려면 [AllowTokenBindingForUrls](./microsoft-edge-policies.md#allowtokenbindingforurls) 정책을 설정하고 목록의 사이트가 이 기능을 지원해야 합니다.

- **키보드는 PDF 파일의 형광펜을 지원합니다**. 사용자는 키보드 키를 사용하여 PDF에서 텍스트를 강조 표시할 수 있습니다.

- **인쇄:**

  - 양면 인쇄 시 어느 쪽으로 대칭 이동할 것인지 선택합니다. 양면 인쇄 시 사용자는 용지의 긴 면이나 짧은 면으로 대칭 이동할 수 있습니다.
  - 엔터프라이즈에 대한 인쇄 래스터화 모드를 선택합니다. Windows에서 포스트스크립트가 아닌 프린터에 대해 Microsoft Edge의 인쇄 방식을 제어합니다. 포스트스크립트가 아닌 프린터의 인쇄 작업에서 올바르게 인쇄하려면 래스터화를 진행해야 하는 경우가 있습니다. 인쇄 옵션은 "전체" 및 "빠르게"입니다.

### <a name="policy-updates"></a>정책 업데이트

#### <a name="new-policies"></a>새로운 정책

10개의 새 정책을 추가했습니다. [Microsoft Edge Enterprise 랜딩 페이지](https://www.microsoft.com/edge/business/download)에서 업데이트된 관리 템플릿을 다운로드합니다. 다음과 같은 새 정책이 추가되었습니다.

- [ConfigureFriendlyURLFormat](./microsoft-edge-policies.md#configurefriendlyurlformat) - Microsoft Edge에서 복사된 URL의 기본 붙여넣기 서식을 구성하고 추가 서식을 사용자에게 제공할 것인지 여부를 결정합니다.
- [EdgeShoppingAssistantEnabled](./microsoft-edge-policies.md#edgeshoppingassistantenabled) - Microsoft Edge에서 쇼핑을 사용하도록 설정합니다.
- [HideInternetExplorerRedirectUXForIncompatibleSitesEnabled](./microsoft-edge-policies.md#hideinternetexplorerredirectuxforincompatiblesitesenabled) - Microsoft Edge에서 일회성 리디렉션 대화 상자 및 배너를 숨깁니다.
- [KioskAddressBarEditingEnabled](./microsoft-edge-policies.md#kioskaddressbareditingenabled) - 키오스크 모드 공개 검색 환경에 대해 주소 표시줄 편집을 구성합니다.
- [KioskDeleteDownloadsOnExit](./microsoft-edge-policies.md#kioskdeletedownloadsonexit) - Microsoft Edge가 닫히는 경우, 키오스크 세션의 일부로 다운로드된 파일을 삭제합니다.
- [PasswordRevealEnabled](./microsoft-edge-policies.md#passwordrevealenabled) - 암호 노출 단추를 사용하도록 설정합니다.
- [RedirectSitesFromInternetExplorerPreventBHOInstall](./microsoft-edge-policies.md#redirectsitesfrominternetexplorerpreventbhoinstall) - Internet Explorer에서 Microsoft Edge로 호환되지 않는 사이트를 리디렉션하는 BHO(브라우저 도우미 개체) 설치를 방지합니다.
- [RedirectSitesFromInternetExplorerRedirectMode](./microsoft-edge-policies.md#redirectsitesfrominternetexplorerredirectmode) - Internet Explorer에서 Microsoft Edge로 호환되지 않는 사이트를 리디렉션합니다.
- [SpeechRecognitionEnabled](./microsoft-edge-policies.md#speechrecognitionenabled) - 음성 인식을 구성합니다.
- [WebCaptureEnabled](./microsoft-edge-policies.md#webcaptureenabled) - Microsoft Edge에서 웹 캡처 기능을 사용으로 설정합니다.

#### <a name="deprecated-policy"></a>더 이상 사용되지 않는 정책

[NewTabPageSetFeedType](./microsoft-edge-policies.md#newtabpagesetfeedtype) - Microsoft Edge 새 탭 페이지 환경을 구성합니다.

#### <a name="obsoleted-policy"></a>폐기된 정책

[EnableDeprecatedWebPlatformFeatures](./microsoft-edge-policies.md#enabledeprecatedwebplatformfeatures) - 제한된 시간 동안 사용되지 않는 웹 플랫폼 기능을 다시 사용하도록 설정합니다.

<!-- end major 87 -->

## <a name="version-86062269-november-13"></a>버전 86.0.622.69: 11월 13일

> [!IMPORTANT]
> 이 업데이트에는 [CVE-2020-16013](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-16013) 및 [CVE-2020-16017](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-16017)이 포함되어 있으며 Chromium 팀은 이 취약점이 악용된 것으로 보고했습니다.

안정 채널 보안 업데이트는 [여기](./microsoft-edge-relnotes-security.md#november-13-2020)에서 확인할 수 있습니다.

## <a name="version-86062268-november-11"></a>버전 86.0.622.68: 11월 11일

안정 채널 보안 업데이트는 [여기](./microsoft-edge-relnotes-security.md#november-11-2020)에서 확인할 수 있습니다

## <a name="version-86062263-november-4"></a>버전 86.0.622.63: 11월 4일

> [!IMPORTANT]
> 이 업데이트에는 [CVE-2020-16009](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-16009)가 포함되어 있으며 Chromium 팀은 이 취약점이 악용된 것으로 보고했습니다.

안정 채널 보안 업데이트는 [여기](./microsoft-edge-relnotes-security.md#november-4-2020)에서 확인할 수 있습니다.

## <a name="version-86062261-november-2"></a>버전 86.0.622.61: 11월 2일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-86062258-october-29"></a>버전 86.0.622.58: 10월 29일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-86062256-october-27"></a>버전 86.0.622.56: 10월 27일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-86062251-october-22"></a>버전 86.0.622.51: 10월 22일

안정 채널 보안 업데이트는 [여기](./microsoft-edge-relnotes-security.md#october-22-2020)에서 확인할 수 있습니다

## <a name="version-86062248-october-20"></a>버전 86.0.622.48: 10월 20일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-86062243-october-15"></a>버전 86.0.622.43: 10월 15일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-86062238-october-9"></a>버전 86.0.622.38: 10월 9일

보안 업데이트는 [여기](./microsoft-edge-relnotes-security.md#october-9-2020)에서 확인할 수 있습니다

### <a name="feature-updates"></a>기능 업데이트

* **이전 Microsoft Edge 버전으로 롤백합니다.** 롤백 기능을 통해 관리자는 최신 버전의 Microsoft Edge에 문제가 있는 경우 정상 버전의 Microsoft Edge로 돌아갈 수 있습니다. **참고:** 안정적 버전 86.0.622.38은 롤백할 수 있는 첫 번째 버전이며, 안정적 버전 87은 롤백할 수 있는 첫 번째 버전입니다. [자세한 내용을 알아보세요](edge-learnmore-rollback.md).

* **기업 전체에서 기본적으로 동기화를 사용하도록 강제 설정합니다.**  관리자는 기본적으로 [ForceSync](./microsoft-edge-policies.md#forcesync) 정책을 사용하여 Azure AD(Azure Active Directory) 계정에 대한 동기화를 사용하도록 설정할 수 있습니다.

* **Windows 7 및 8.1의 자동 프로필 스위치** 현재 Windows 10의 Microsoft Edge에서 사용할 수 있는 자동 프로필 스위칭이 하위 수준 Windows(Windows 7 및 8.1)로 확장됩니다. 자세한 내용은 [자동 프로필 전환](https://blogs.windows.com/msedgedev/2020/04/30/automatic-profile-switching/) 블로그 게시물을 참조하시기 바랍니다.

* **SameSite=Lax 쿠키(기본값)**. 웹 보안 및 개인 정보 보호를 향상시키기 위해 기본적으로 쿠키 기본값이 [SameSite=Lax](https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie/SameSite) 처리로 설정됩니다.  즉, 쿠키는 타사 컨텍스트에서만 전송되고 타사에 보낸 요청의 경우에는 생략됩니다. 이와 같이 변경하면 타사 리소스에 대한 쿠키가 있어야 제대로 작동하는 웹 사이트에서 호환성에 영향을 줄 수 있습니다. 이와 같은 쿠키를 허용하려면 웹 개발자가 쿠키를 설정할 때 명시적 `SameSite=none` 및 `Secure` 특성을 추가하여 타사 컨텍스트에서 설정하고 해당 컨텍스트로 보내야 하는 쿠키를 표시할 수 있습니다. 해당 변경에서 특정 사이트를 제외하려는 기업에서는 [LegacySameSiteCookieBehaviorEnabledForDomainList](./microsoft-edge-policies.md#legacysamesitecookiebehaviorenabledfordomainlist) 정책을 사용하여 해당 작업을 하거나 [LegacySameSiteCookieBehaviorEnabled](./microsoft-edge-policies.md#legacysamesitecookiebehaviorenabled) 정책을 사용하여 모든 사이트에서 변경 내용을 옵트아웃할 수 있습니다.

* **HTML5 Application Cache API를 제거합니다.**  Microsoft Edge 버전 86부터는 웹 페이지를 오프라인으로 사용할 수 있는 기존 Application Cache API가 Microsoft Edge에서 제거되고 있습니다. 웹 개발자는 응용 프로그램 캐시 API를 서비스 작업자로 교체하는 방법에 대한 정보를 위해 [WebDev 문서](https://web.dev/appcache-removal/)을(를) 검토해야 합니다.  중요: Microsoft Edge 버전 90까지 더 이상 사용되지 않는 Application Cache API를 사이트에서 계속 사용할 수 있도록 [AppCache OriginTrial 토큰](https://developers.chrome.com/origintrials/#/view_trial/1776670052997660673)을(를) 요청할 수 있습니다.

* **개인정보 보호 및 보안:**

  * 하위 수준 Windows 및 MacOS에 대해 [MetricsReportingEnabled](/DeployEdge/microsoft-edge-policies#metricsreportingenabled) 및 [SendSiteInformationToEnhancedServices](/DeployEdge/microsoft-edge-policies#sendsiteinfotoimproveservices) 정책을 바꿉니다. 이러한 정책은 Microsoft Edge 버전 86에서 더 이상 사용되지 않으며 Microsoft Edge 버전 89에서는 사용되지 않습니다.<br>
이러한 정책은 Windows 10에서 [원격측정 허용](/windows/privacy/configure-windows-diagnostic-data-in-your-organization) 및 다른 모든 플랫폼에 대한 새 [진단 데이터](./microsoft-edge-policies.md#diagnosticdata) 정책으로 대체됩니다. 이를 통해 사용자는 Microsoft for Windows 7, 8, 8.1 및 MacOS로 전송되는 진단 데이터를 관리할 수 있습니다.
  * 보안 DNS(DNS-over-HTTPS)를 지원합니다.  Microsoft Edge 버전 86부터는 관리되지 않는 디바이스에서 보안 DNS를 제어하는 설정을 사용할 수 있습니다. 이러한 설정은 관리 디바이스의 사용자가 액세스할 수 없지만 IT 관리자는 [damperhtps 모드](./microsoft-edge-policies.md#dnsoverhttpsmode) 그룹 정책을 사용하여 보안 DNS를 사용하거나 사용하지 않도록 설정할 수 있습니다.

* **Internet Explorer 모드:** 사용자가 Microsoft UI(Edge User Interface)를 사용하여 Internet Explorer 모드에서 사이트를 테스트할 수 있습니다. Microsoft Edge 버전 86부터 관리자는 테스트 목적으로 또는 사이트 목록 XML에 사이트가 추가될 때까지 사용자가 Internet Explorer 모드에서 탭을 로드할 수 있도록 UI 옵션을 사용할 수 있습니다.

* **PDF 업데이트:**

  * PDF 문서에 대한 목차입니다. 버전 86부터 Microsoft Edge는 사용자가 PDF 문서를 쉽게 탐색할 수 있도록 목차를 지원합니다.
  * 소형 폼 팩터 화면에서 모든 PDF 기능에 액세스합니다. 화면 크기가 작은 장치에서 Microsoft Edge PDF 판독기의 모든 기능에 액세스합니다.
  * PDF 파일의 형광펜을 지원합니다. 이 업데이트를 통해 사용자는 디지털 펜을 사용하여 실제 형광펜과 용지와 같은 방식으로 PDF 파일의 텍스트를 직접 강조 표시할 수 있습니다.
  * PDF 스크롤이 향상되었습니다. 이제 긴 PDF 문서를 탐색하는 동안 자유롭게 스크롤할 수 있습니다.

* **Microsoft Edge 추가 기능 웹 사이트에서 검색 쿼리를 입력하기 시작하면 자동 완료 제안이 표시됩니다.** 자동 완료를 사용하면 전체 문자열을 입력할 필요 없이 검색 쿼리를 빠르게 완료할 수 있습니다. 이 기능은 사용자가 올바른 철자를 기억할 필요가 없고 표시되는 사용 가능한 옵션 중에서 선택할 수 있으므로 유용합니다.

* **그룹 정책을 사용하여 사용자 지정 이미지를 새 탭 페이지(NTP)에 추가합니다.** Microsoft Edge 버전 86부터 NTP에는 기본 이미지를 사용자 지정 사용자 제공 이미지로 바꾸는 옵션이 있습니다. 이 이미지의 속성을 관리하는 기능도 그룹 정책에서 지원됩니다.

* **사용자 지정된 바로 가기 키를 VS Code에 일치시킵니다.** Microsoft Edge DevTools는 이제 편집기/IDE와 일치하도록 DevTools의 바로 가기 키 사용자 지정을 지원합니다. Microsoft Edge 84에서는 DevTools 바로 가기 키를 VS Code에 일치시키는 기능을 추가했습니다.

* **다운로드 관리자를 사용하여 디스크에서 다운로드를 삭제합니다.** 이제 사용자는 브라우저를 떠나지 않고 디스크에서 다운로드한 파일을 삭제할 수 있습니다. 새로운 다운로드 삭제 기능은 다운로드 쉘프 또는 다운로드 페이지의 컨텍스트 메뉴 내에 있습니다.

### <a name="policy-updates"></a>정책 업데이트

#### <a name="new-policies"></a>새로운 정책

23개의 새로운 정책이 추가되었습니다. [Microsoft Edge Enterprise 랜딩 페이지](https://aka.ms/EdgeEnterprise)에서 업데이트된 관리 템플릿을 다운로드합니다. 다음과 같은 새 정책이 추가되었습니다.

- [CollectionsServicesAndExportsBlockList](./microsoft-edge-policies.md#collectionsservicesandexportsblocklist) - 지정된 서비스 목록에 대한 액세스를 차단하고 컬렉션에서 대상을 내보내기합니다.
- [DefaultFileSystemReadGuardSetting](./microsoft-edge-policies.md#defaultfilesystemreadguardsetting) - 읽기용 파일 시스템 API 사용을 제어합니다.
- [DefaultFileSystemWriteGuardSetting](./microsoft-edge-policies.md#defaultfilesystemwriteguardsetting) - 쓰기에 대한 파일 시스템 API 사용을 제어합니다.
- [DefaultSensorSetting](./microsoft-edge-policies.md#defaultsensorssetting) - 기본 센서 설정입니다.
- [DefaultSerialGuardSetting](./microsoft-edge-policies.md#defaultserialguardsetting) - 직렬 API의 사용을 제어합니다.
- [DiagnosticData](./microsoft-edge-policies.md#diagnosticdata) - 브라우저 사용에 대한 필수 및 선택적 진단 데이터를 전송합니다.
- [EnterpriseModeSiteListManagerAllowed](./microsoft-edge-policies.md#enterprisemodesitelistmanagerallowed) - 엔터프라이즈 모드 사이트 목록 관리자 도구에 대한 액세스를 허용합니다.
- [FileSystemReadAskForUrls](./microsoft-edge-policies.md#filesystemreadaskforurls) - 이 사이트에서 파일 시스템 API를 통해 읽기 액세스를 허용합니다.
- [FileSystemReadBlockedForUrls](./microsoft-edge-policies.md#filesystemreadblockedforurls) - 이 사이트에서 파일 시스템 API를 통해 읽기 액세스를 차단합니다.
- [FileSystemWriteAskForUrls](./microsoft-edge-policies.md#filesystemwriteaskforurls) - 이 사이트의 파일 및 디렉토리에 대한 쓰기 액세스를 허용합니다.
- [FileSystemWriteBlockedForUrls](./microsoft-edge-policies.md#filesystemwriteblockedforurls) - 이 사이트의 파일 및 디렉토리에 대한 쓰기 액세스를 차단합니다.
- [ForceSync](./microsoft-edge-policies.md#forcesync) - 브라우저 데이터의 동기화를 강제 적용하고 동기화 동의 메시지를 표시하지 않습니다.
- [InsecureFormsWarningsEnabled](./microsoft-edge-policies.md#insecureformswarningsenabled) - 안전하지 않은 양식에 대해 경고를 사용합니다.
- [InternetExplorerIntegrationTestingAllowed](./microsoft-edge-policies.md#internetexplorerintegrationtestingallowed) - Internet Explorer 모드 테스트를 허용합니다.
- [SpotlightExperiencesAndRecommendationsEnabled](./microsoft-edge-policies.md#spotlightexperiencesandrecommendationsenabled) - 사용자가 Microsoft 서비스에 대한 사용자 지정 배경 이미지와 텍스트, 제안 사항, 알림 및 팁을 받을 수 있는지 여부를 선택합니다.
- [NewTabPageAllowedBackgroundTypes](./microsoft-edge-policies.md#newtabpageallowedbackgroundtypes) - 새 탭 페이지 레이아웃에 허용된 배경 유형을 구성합니다.
- [SaveCookiesOnExit](./microsoft-edge-policies.md#savecookiesonexit) - Microsoft Edge가 닫힐 때 쿠키를 저장합니다.
- [SensorsAllowedForUrls](./microsoft-edge-policies.md#sensorsallowedforurls) - 특정 사이트의 센서에 대한 액세스를 허용합니다.
- [SensorsBlockedForUrls](./microsoft-edge-policies.md#sensorsblockedforurls) - 특정 사이트의 센서에 대한 액세스를 차단합니다.
- [SerialAskForUrls](./microsoft-edge-policies.md#serialaskforurls) - 특정 사이트에서 직렬 API를 허용합니다.
- [SerialBlockedForUrls](./microsoft-edge-policies.md#serialblockedforurls) - 특정 사이트에서 직렬 API를 차단합니다.
- [UserAgentClientHintsEnabled](./microsoft-edge-policies.md#useragentclienthintsenabled) - 사용자-에이전트 클라이언트 힌트 기능을 사용하도록 설정합니다.
- [UserDataSnapshotRetentionLimit](./microsoft-edge-policies.md#userdatasnapshotretentionlimit) - 비상 롤백 시 사용하기 위해 보존된 사용자 데이터 스냅샷 수를 제한합니다.

#### <a name="deprecated-policies"></a>사용되지 않는 정책

- [MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled) - 사용 및 충돌 관련 데이터보고를 사용하도록 설정합니다.
- [SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices) - Microsoft 서비스를 개선하기 위해 사이트 정보를 보냅니다.

#### <a name="obsoleted-policy"></a>폐기된 정책

[TLS13HardeningForLocalAnchorsEnabled](./microsoft-edge-policies.md#tls13hardeningforlocalanchorsenabled) - 로컬 신뢰 앵커에 대한 TLS 1.3 보안 기능을 사용하세요.

## <a name="version-85056470-october-6"></a>버전 85.0.564.70: 10월 6일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-85056468-october-1"></a>버전 85.0.564.68: 10월 1일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-85056463-september-23"></a>버전 85.0.564.63: 9월 23일

보안 업데이트는 [여기](./microsoft-edge-relnotes-security.md#september-23-2020)에서 확인할 수 있습니다

## <a name="version-85056451-september-9"></a>버전 85.0.564.51: 9월 9일

보안 업데이트는 [여기](./microsoft-edge-relnotes-security.md#september-9-2020)에서 확인할 수 있습니다

## <a name="version-85056444-august-31"></a>버전 85.0.564.44: 8월 31일

다양한 버그와 성능 문제를 해결했습니다.

<!-- 85.0.564.41: August 27 -->

## <a name="version-85056441-august-27"></a>버전 85.0.564.41: 8월 27일

보안 업데이트는 [여기](./microsoft-edge-relnotes-security.md#august-27-2020)에서 확인할 수 있습니다

### <a name="feature-updates"></a>기능 업데이트

- **즐겨찾기 및 설정의 온-프레미스 동기화** 이제 클라우드 동기화 없이도 사용자 환경 내에서 Active Directory 프로필 간에 브라우저 즐겨찾기 및 설정을 동기화할 수 있습니다.

- **Microsoft Edge 그룹 정책 지원 - 신뢰할 수 있는 사이트 + 앱 콤보가 확인 프롬프트 없이 실행됩니다**. 관리자가 확인 프롬프트 없이 시작할 수 있는 신뢰할 수 있는 사이트 + 앱 조합을 추가할 수 있는 그룹 정책 지원이 추가되었습니다. 이렇게 하면 관리자가 앱 프로토콜이 포함된 URL로 이동할 때 최종 사용자가 확인 메시지를 표시하지 않도록 신뢰할 수 있는 프로토콜/원본 조합(예: Microsoft 365 앱)을 구성할 수 있습니다.

- **PDF 형광펜 도구** 이 도구를 PDF 도구 모음에 추가하여 중요한 텍스트를 쉽게 강조 표시할 수 있습니다.

- **스토리지 Access API를 사용할 수 있습니다**. 사용자가 브라우저의 현재 구성에 의해 차단될 수 있는 스토리지를 허용하려는 직접적인 의도를 제공한 경우 Storage Access API를 통해 타사 컨텍스트에서 타사 스토리지에 액세스할 수 있습니다. 자세한 내용은 [스토리지 액세스 API](https://www.chromestatus.com/feature/5612590694662144)을(를) 참조하시기 바랍니다.

- **Send to OneNote는 Microsoft Edge Collections에서 사용할 수 있습니다**. 모음에서 수집한 정보를 OneNote에 보내 더 큰 프로젝트에 추가하고 다른 사람들과 협업할 수 있게 되어 모두가 들떠 있습니다! 또한 Microsoft Edge 85에서는 Microsoft 계정 및 Azure Active Directory의 *Office for Mac* 제품(Word, Excel 및 OneNote)에 컨텐츠를 전송할 수 있습니다.

- **DevTools가 업데이트** 다음 업데이트에 대한 자세한 내용은 [DevTools의 새로운 기능(Microsoft Edge 85)](/microsoft-edge/devtools-guide-chromium/whats-new/2020/06/devtools)을(를) 참조하시기 바랍니다.

   - Microsoft Edge DevTools는 Surface Duo 에뮬레이션을 지원합니다. Microsoft Edge DevTools는 Surface Duo를 에뮬레이트하여 듀얼 스크린 장치에서 웹 콘텐츠가 어떻게 표시되는지 테스트할 수 있습니다. DevTools에서 이 실험을 실행하려면 Windows에서 Ctrl+Shift+M을 누르거나 MacOS에서 Command+Shift+M을 눌러 장치 모드로 들어간 다음 장치 드롭다운 목록에서 Surface Duo를 선택합니다.
   - Microsoft Edge DevTools를 사용하면 바로 가기 키를 VS Code에 연결할 수 있습니다. Microsoft Edge DevTools는 편집기/IDE와 일치하도록 DevTools의 바로 가기 키 사용자 지정을 지원합니다. Microsoft Edge 85에서는 DevTools 바로 가기 키를 VS Code에 일치시키는 기능을 추가하고 있습니다. 이러한 변경은 VS Code 및 DevTools 전체에서 생산적으로 증가하는 데 도움이 됩니다.

### <a name="policy-updates"></a>정책 업데이트

#### <a name="new-policies"></a>새로운 정책

13개의 새로운 정책이 추가되었습니다. [Microsoft Edge Enterprise 랜딩 페이지](https://aka.ms/EdgeEnterprise)에서 업데이트된 관리 템플릿을 다운로드합니다. 다음과 같은 새 정책이 추가되었습니다.

- [AutoLaunchProtocolsFromOrigins](./microsoft-edge-policies.md#autolaunchprotocolsfromorigins) - 사용자에게 묻지 않고 나열된 원본에서 외부 애플리케이션을 실행할 수 있는 프로토콜 목록 정의
- [AutoOpenAllowedForURLs](./microsoft-edge-policies.md#autoopenallowedforurls) - AutoOpenFileTypes를 적용할 수 있는 URL
- [AutoOpenFileTypes](./microsoft-edge-policies.md#autoopenfiletypes) - 다운로드 시 자동으로 열어야 하는 파일 형식 목록
- [DefaultSearchProviderContextMenuAccess허용됨](./microsoft-edge-policies.md#defaultsearchprovidercontextmenuaccessallowed) - 기본 검색 공급자의 상황에 맞는 메뉴 검색 액세스 허용합니다.
- [EnableSha1ForLocalAchors](./microsoft-edge-policies.md#enablesha1forlocalanchors) - 로컬 트러스트 앵커에서 발급한 경우 SHA-1을 사용하여 서명한 인증서 허용합니다.
- [ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](./microsoft-edge-policies.md#exemptdomainfiletypepairsfromfiletypedownloadwarnings) - 도메인에서 지정된 파일 형식에 대해 파일 형식 확장명 기반 주의 다운로드를 사용설정 해제합니다.
- [IntensiveWakeUpThrottlingEnabled](./microsoft-edge-policies.md#intensivewakeupthrottlingenabled) - IntegratedWakeUpThrotling 기능 제어
- [NewTabPagePrerenderEnabled](./microsoft-edge-policies.md#newtabpageprerenderenabled) - 렌더링 속도를 높이기 위해 새 탭 페이지의 사전 로드 사용
- [NewTabPageSearchBox](./microsoft-edge-policies.md#newtabpagesearchbox) - 새 탭 페이지 검색 상자 환경 구성
- [PasswordMonitorAllowed ](./microsoft-edge-policies.md#passwordmonitorallowed) - 암호가 안전하지 않은 경우 사용자에게 경고를 보낼 수 있도록 허용
- [RoamingProfileSupportEnabled](./microsoft-edge-policies.md#roamingprofilesupportenabled) - Microsoft Edge 프로파일 데이터에 로밍 복사본 사용
- [ RoamingProfileLocation ](./microsoft-edge-policies.md#roamingprofilelocation) - 로밍 프로파일 디렉토리 설정
- [TLSCsipherSuiteDenyList](./microsoft-edge-policies.md#tlsciphersuitedenylist) - 사용하지 않도록 설정할 TLS 암호 그룹을 지정

#### <a name="obsoleted-policies"></a>폐기된 정책

- [EnableDomainActionsDownload](./microsoft-edge-policies.md#enabledomainactionsdownload) - Microsoft에서 도메인 작업 다운로드 사용
- [WebComponentsV0Enabled](./microsoft-edge-policies.md#webcomponentsv0enabled) - M84까지 웹 구성 요소 v0 API를 다시 사용하도록 설정합니다.
- [ WebDriverOverridesIncompatiblePolicies ](./microsoft-edge-policies.md#webdriveroverridesincompatiblepolicies)- 웹 드라이버가 비호환 정책을 재정의하도록 허용

## <a name="version-84052263-august-20"></a>버전 84.0.522.63: 8월 20일

보안 업데이트는 [여기](./microsoft-edge-relnotes-security.md#august-20-2020)에서 확인할 수 있습니다.

## <a name="version-84052261-august-17"></a>버전 84.0.522.61: 8월 17일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-84052259-august-11"></a>버전 84.0.522.59: 8월 11일

보안 업데이트는 [여기](./microsoft-edge-relnotes-security.md#august-11-2020)에서 확인할 수 있습니다

## <a name="version-84052258-august-10"></a>버전 84.0.522.58: 8월 10일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-84052252-august-1"></a>버전 84.0.522.52: 8월 1일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-84052250-july-31"></a>버전 84.0.522.50: 7월 31일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-84052249-july-29"></a>버전 84.0.522.49: 7월 29일

보안 업데이트는 [여기](./microsoft-edge-relnotes-security.md#july-29-2020)에서 확인할 수 있습니다

## <a name="version-84052248-july-28"></a>버전 84.0.522.48: 7월 28일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-84052244-july-23"></a>버전 84.0.522.44: 7월 23일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-84052240-july-16"></a>버전 84.0.522.40: 7월 16일

보안 업데이트는 [여기](./microsoft-edge-relnotes-security.md#july-16-2020)에서 확인할 수 있습니다

### <a name="feature-updates"></a>기능 업데이트

- 이 버전의 Microsoft Edge는 Internet Explore 모드에 대한 개선된 사이트 목록 다운로드 항목을 제공합니다. 캐시 사이트 목록이 없는 경우 Internet Explorere 모드 사이트 목록의 다운로드 지연 시간을 0초(60초 지연에서 개선)로 줄였습니다. Internet Explorer 모드 홈페이지 탐색이 사이트 목록이 다운로드 될 때까지 지연되는 경우 그룹 지원 정책을 추가 했습니다. 자세한 내용은 [DelayNavigationsForInitialSiteListDownload](./microsoft-edge-policies.md#delaynavigationsforinitialsitelistdownload) policy를 참조하세요.

- Microsoft Edge에서 이제 Windows 10에서 "관리자 권한으로 실행"하고 있는 사용자가 브라우저에 로그인 할 수 있도록 허용합니다. 이것은 Windows 서버 혹은 원격 데스크톱 및 샌드박스 시나리오에서 Microsoft Edge를 실행하는 고객에게 도움이 됩니다.

- Microsoft Edge는 이제 전체 화면 모드에서 전체 마우스를 지원합니다. 이제 전체 화면 모드를 종료 하지 않고도 마우스를 사용하여 탭, 주소 표시줄 및 기타 항목에 액세스할 수 있습니다.

- 온라인 구입 개선 저장 된 직불 또는 신용 카드에 소비자 지정 애칭을 추가합니다. 이제 온라인으로 구매할 때 신용 카드를 구별 및 구분할 수 있습니다. 직불 또는 신용 카드에 애칭을 정하면 자동 충전 지불 방식을 선택 할 때 올바른 카드를 선택 할 수 있습니다.

- TLS/1.0 및 TLS/1.1은 기본적으로 사용 하지 않도록 설정 되어 있습니다.  [SSLVersionMin](./microsoft-edge-policies.md#sslversionmin) 정책은 TLS/1.0 및 TLS/1.1을 다시 사용하도록 허용 합니다. 이 정책은 적어도 Microsoft Edge 버전 88 까지는 계속 사용할 수 있습니다. 자세한 내용은 [사이트 호환성-Microsoft Edge로 들어오는 변화에 영향](/microsoft-edge/web-platform/site-impacting-changes)을 참조하세요.

- 컬렉션 개선:

  - 노트 기능이 추가 되어 컬렉션에 있는 항목에 메모 또는 주석을 추가할 수 있습니다. 노트를 그룹화하여 컬렉션의 항목을 정렬 하는 경우에도 항목에 계속 첨부되어 있습니다. 이 새로운 기능을 사용해 보세요. 항목을 마우스 오른쪽 단추로 클릭하고 "메모 추가"를 선택합니다.
  - 컬렉션에서 노트의 배경색을 변경할 수 있습니다. 색 코드를 사용하여 정보를 구성하고 생산성을 향상 시킬 수 있습니다.
  - 성능이 크게 향상 되어 이전 버전의 Microsoft Edge 보다 훨씬 적은 시간에 컬렉션을 Excel로 내보낼 수 있습니다.

- 추가 Microsoft Edge API 지원:

  - 스토리지 액세스 API를 사용하여 실험할 수 있습니다. 이 기능은 [ExperimentationAndConfigurationServiceControl](./microsoft-edge-policies.md#experimentationandconfigurationservicecontrol) 정책을 “전체”로 설정한 개인 사용자 및 엔터프라이즈 사용자에 대해 사용할 수 있습니다. 이 기능은 Microsoft Edge 스테이블 채널 버전 85의 모든 사용자에 대해 기본적으로 사용할 수 있습니다.
  
    사용자에게 개인 정보 보호가 점차 더 중요해 지듯 모든 3자 저장소 액세스를 차단하는 것과 같은 엄격한 브라우저 기본값과 사용자 옵트인 설정이 점차 보편화 되고 있습니다. 이 설정을 사용하면 개인 정보 보호를 개선하고 알 수 없는 사용자나 신뢰하지 않은 사용자로부터의 원치 않는 액세스를 차단함과 동시에 사용자가 보기를 원하는 콘텐츠를 차단하는 원치 않는 부작용이 발생할 수 있습니다 (예: 소셜 미디어 및 미디어 포함된 콘텐츠).

    사용자가 브라우저의 현재 구성에 의해 차단될 수 있는 스토리지를 허용하려는 직접적인 의도를 제공한 경우 스토리지 액세스 API를 통해 타사 컨텍스트에서 타사 스토리지에 액세스할 수 있습니다. 자세한 내용은 [스토리지 액세스 API](https://www.chromestatus.com/feature/5612590694662144)을(를) 참조하시기 바랍니다.

  - 기본 파일 시스템 API을 통해 파일 또는 폴더를 편집 할 수 있는 권한을 사이트에 제공할 수 있는 기본 파일 시스템 API.

- PDF 개선:

  - PDF를 소리 내어 읽기를 사용하면 사용자는 중요한 다른 작업을 수행 하면서 PDF 콘텐츠를 들을 수 있습니다. 오디오 시각적 학습자가 콘텐츠 읽기에 중점을 두고 손쉽게 배울 수도 있습니다.
  - PDF 파일 편집 기능이 개선 되었습니다. 이제 PDF를 편집할 때마다 복사본을 저장하는 대신 PDF 편집 내용을 다시 파일에 저장할 수 있습니다.

- 이제 Microsoft Edge에서 몰입형 독자 번역을 사용할 수 있습니다. 사용자가 몰입형 독자 보기를 열면 페이지를 원하는 언어로 번역하기 옵션이 표시됩니다.

- VS 코드와 고대비 DevTools에 맞는 바로 가기 키를 사용자 지정 하기 위한 지원을 포함한 여러 DevTools가 업데이트.  세부 내용은 [DevTools 새로운 소식(Microsoft Edge 84)](/microsoft-edge/devtools-guide-chromium/whats-new/2020/05/devtools)를 참조하세요.

### <a name="policy-updates"></a>정책 업데이트

#### <a name="new-policies"></a>새로운 정책

새 정책 7개를 추가했습니다. [Microsoft Edge Enterprise 랜딩 페이지](https://aka.ms/EdgeEnterprise)에서 업데이트된 관리 템플릿을 다운로드합니다. 다음과 같은 새 정책이 추가되었습니다.

- [AppCacheForceEnabled](./microsoft-edge-policies.md#appcacheforceenabled) - 이름: AppCache 기능이 기본적으로 해제되어 있더라도 다시 사용할 수 있도록 허용
- [ApplicationGuardContainerProxy](./microsoft-edge-policies.md#applicationguardcontainerproxy) - 응용 프로그램 보호 컨테이너 프록시 설정 구성
- [DelayNavigationsForInitialSiteListDownload](./microsoft-edge-policies.md#delaynavigationsforinitialsitelistdownload) - 탭 탐색 전에 엔터프라이즈 모드 사이트 목록을 사용하도록 요청
- [WinHttpProxyResolverEnabled](./microsoft-edge-policies.md#winhttpproxyresolverenabled) - Windows 프록시 해결 프로그램을 사용
- [InternetExplorerIntegrationEnhancedHangDetection](./microsoft-edge-policies.md#internetexplorerintegrationenhancedhangdetection)-Internet Explorer 모드에 개선된 중지 검색 구성
- [NativeWindowOcclusionEnabled](./microsoft-edge-policies.md#nativewindowocclusionenabled) - Microsoft Edge는 CPU 및 전원 소비량을 줄이기 위해 창이 다른 창에 포함된 경우 이를 감지하고 작업 페인팅 픽셀을 일시 중단합니다.
- [NavigationDelayForInitialSiteListDownloadTimeout](./microsoft-edge-policies.md#navigationdelayforinitialsitelistdownloadtimeout) - 엔터프라이즈 모드 사이트 목록에 대한 탭 탐색 지연 시간 설정

#### <a name="deprecated-policies"></a>더 이상 사용되지 않는 정책

- [AllowSyncXHRInPageDismissal](./microsoft-edge-policies.md#allowsyncxhrinpagedismissal) - 페이지를 해제하는 동안 페이지에서 동기 XHR 요청 전송 허용
- [BuiltinCertificateVerifierEnabled](./microsoft-edge-policies.md#builtincertificateverifierenabled) - 서버 인증서를 확인하는 데 기본 제공 인증서 검증 도구를 사용할지 여부를 결정합니다.
- [ StricterMixedContentTreatmentEnabled ](./microsoft-edge-policies.md#strictermixedcontenttreatmentenabled) -혼합 컨텐츠에 대해 보다 엄격한 처리를 사용합니다.

#### <a name="obsoleted-policy"></a>폐기된 정책

[ForceNetworkInProcess](./microsoft-edge-policies.md#forcenetworkinprocess) 브라우저 프로세스에서 네트워킹 코드의 실행 강제

<!-- End 84 -->
## <a name="version-83047864-july-13"></a>버전 83.0.478.64: 7월 13일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-83047861-july-7"></a>버전 83.0.478.61: 7월 7일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-83047858-june-30"></a>버전 83.0.478.58: 6월 30일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-83047856-june-24"></a>버전 83.0.478.56: 6월 24일

다양한 버그와 성능 문제를 해결했습니다.

보안 업데이트는 [여기](./microsoft-edge-relnotes-security.md#june-24-2020)에서 확인할 수 있습니다

## <a name="version-83047854-june-17"></a>버전 83.0.478.54: 6월 17일

보안 업데이트는 [여기](./microsoft-edge-relnotes-security.md#june-17-2020)에서 확인할 수 있습니다

## <a name="version-83047850-june-15"></a>버전 83.0.478.50: 6월 15일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-83047845-june-4"></a>버전 83.0.478.45: 6월 4일

보안 업데이트는 [여기](./microsoft-edge-relnotes-security.md#june-4-2020)에서 확인할 수 있습니다

## <a name="version-83047844-june-1"></a>버전 83.0.478.44: 6월 1일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-83047837-may-21"></a>버전 83.0.478.37: 5월 21일

보안 업데이트는 [여기](./microsoft-edge-relnotes-security.md#may-21-2020)에서 확인할 수 있습니다

### <a name="feature-updates"></a>기능 업데이트

- 이제 Microsoft Edge 업데이트가 점진적으로 배포 됩니다. 향후에는 Microsoft Edge 업데이트를 며칠에 걸쳐 사용자에게 배포합니다. 따라서 결함 버그 실수로부터 사용자를 더욱 보호하여 사용자의 업데이트 환경을 개선합니다. 사용자는 계속해서 원활한 자동 업데이트를 받습니다. 조직에서 자동 업데이트에 등록하지 않은 경우에는 이 변경 사항으로 인해 영향을 받지 않습니다. 자세한 내용은 [점진적 배포 문서](microsoft-edge-update-progressive-rollout.md)를 참조하세요.
- Microsoft Defender SmartScreen 개선 사항: 로드 시 리디렉션하는 유해 사이트에 대해 강화된 보안, Microsoft Defender SmartScreen 보안 페이지를 사용하여 유해 사이트를 완전히 대체하는 최상위 프레임 차단 기능 등 Microsoft Defender SmartScreen 서비스에 대한 몇 가지 사항을 개선했습니다. 최상위 프레임 차단 기능은 유해 사이트로부터 오디오 및 기타 미디어의 재생을 차단하여 보다 간편하고 복잡하지 않은 환경을 제공합니다.

- 사용자 피드백을 반영하여 사용자는 이제 브라우저를 닫을 때 특정 쿠키가 자동으로 제거되는 것을 제외할 수 있습니다. 이 선택 사항은 해당 기능은 사용자가 로그아웃을 원하지 않지만 브라우저를 닫을 때 다른 모든 쿠키를 제거하기를 원하는 사이트가 있는 경우에 유용합니다. 해당 기능을 사용하려면 *edge://settings/clearBrowsingDataOnClose*로 이동하고 “쿠키 및 기타 사이트 데이터”를 설정하거나 해제합니다.

- 이제 전체 프로필에서 보다 간편하게 작업 콘텐츠를 확인할 수 있도록 자동 프로필 전환 기능을 사용할 수 있습니다. 회사에서 여러 프로필을 사용하는 경우 개인 프로필에서 회사나 학교 계정의 인증이 필요한 사이트로 이동하여 프로필을 확인할 수 있습니다. 해당 활동이 감지된 경우 인증하지 않고 해당 사이트에 액세스할 수 있도록 회사 프로필로 전환하라는 메시지가 표시됩니다. 전환하려는 회사 프로필을 선택하면 해당 웹 사이트는 회사 프로필에서 간단히 열립니다. 프로필 전환 기능이 사용자의 회사 및 개인 데이터를 별도로 유지하고 더욱 간편하게 회사 콘텐츠에 액세스하는 데 도움이 될 것입니다. 이 기능을 통해 프로필을 전환하라는 메시지가 표시되지 않도록 하려면 이 메시지를 다시 표시 안 함 옵션을 선택하여 메시지가 표시되지 않게 할 수 있습니다.

- 컬렉션 기능 개선:
  - 끌어서 놓기를 사용하여 컬렉션을 열지 않고 항목을 컬렉션에 추가할 수 있습니다. 끌어서 놓기를 수행하는 동안 항목을 추가할 컬렉션 목록에서 위치를 선택할 수도 있습니다.
  - 컬렉션에 항목을 한 번에 하나씩 추가하지 않고 여러 항목을 추가할 수 있습니다. 여러 항목을 추가하려면 항목을 선택한 다음 컬렉션으로 끕니다. 또는 항목을 선택한 다음 마우스 오른쪽 단추로 클릭하고 항목을 추가할 컬렉션을 선택할 수 있습니다.

- Edge 창에서 모든 탭을 개별적으로 추가하지 않고도 새 컬렉션에 추가할 수 있습니다. 해당 기능을 수행하려면 아무 탭에서 마우스 오른쪽 단추로 클릭하고 "새 컬렉션에 모든 탭 추가"를 선택합니다.

- 이제 확장 동기화를 사용할 수 있습니다. 이제 모든 장치에서 확장을 동기화할 수 있습니다! Microsoft 및 Chrome 스토어 모두에서 가져온 확장이 Microsoft Edge와 동기화됩니다. 해당 기능을 사용하려면 메뉴 표시줄에서 타원형의 (**…**)을(를) 클릭하고 **설정**을 선택합니다. 사용자의 프로필에서 **동기화**를 클릭하고 동기화 옵션을 확인합니다. **프로필/동기화**에서 설정/해제를 사용하여 확장을 활성화합니다. [SyncTypesListDisabled](./microsoft-edge-policies.md#synctypeslistdisabled) 그룹 정책을 사용하여 확장 동기화를 해제할 수 있습니다.

- 차단된 비보안 다운로드에 대한 다운로드 관리 페이지의 메시지가 개선되었습니다.

- 몰입형 리더 개선 사항:
  - 몰입형 리더에서 말하는 음성 경험 부분의 부사에 대한 지원이 추가되었습니다. 몰입형 리더에서 기사를 읽는 동안 문법 도구를 열고 품사 내 부사를 켜서 페이지의 모든 부사를 강조 표시하세요.
  - 웹 페이지에서 콘텐츠를 선택하고 몰입형 리더에서 여는 기능을 추가했습니다. 이 기능을 사용하면 사용자가 모든 웹 사이트에서 몰입형 리더와 줄 포커스, 소리내어 읽기와 같은 모든 학습 도구를 사용할 수 있습니다.

- 링크 의사는 URL을 잘못 입력한 사용자에게 호스트 수정 및 검색 쿼리를 제공 합니다. 예를 들어 다음과 같은 가치를 제공해야 합니다. <br>
사용자가 "powerbi를 "powerbbi".com으로 잘못 입력함. 링크 의사는 수정사항으로 “powerbi”.com을 제시하며 사용자가 원하는 것이 다를 경우에 대비해 “powerbbi” 링크 검색을 생성합니다.

- 사용자가 특정 사이트에 대한 외부 프로토콜을 실행하기로 한 결정을 저장할 수 있도록 합니다. 사용자는이 기능을 사용 하거나 사용 하지 않도록 [ExternalProtocolDialogShowAlwaysOpenCheckbox](/DeployEdge/microsoft-edge-policies#externalprotocoldialogshowalwaysopencheckbox) 정책을 구성할 수 있습니다.

- 사용자는 Microsoft Edge **설정**에서 직접 Microsoft Edge를 기본 브라우저로 설정할 수 있습니다. 사용자가 운영 시스템 설정에서 검색하는 대신 브라우저 자체에서 기본 브라우저를 변경하기 용이하도록 합니다. 이 기능을 사용하기 위해서는 *edge://settings/defaultBrowser*로 이동하고 **기본으로 설정** 클릭.

- 새로운 신규 디버깅 지원을 포함한 몇 DevTools 업데이트, UI 개선 등. 세부 내용은 [DevTools 새로운 소식 확인(Microsoft Edge 83)](/microsoft-edge/devtools-guide-chromium/whats-new/2020/03/devtools)을 참조하세요.

- MCAS(Microsoft 클라우드 액세스 보안) 경고 시나리오를 사용할 수 있습니다. 관리자가 새로운 MCAS 차단 범주인 경고를 설정하여 MCAS 차단 페이지를 재정의 할 수 있습니다. MDATP E5 차단은 원활한 환경을 위해 Microsoft Edge의 SmartScreen 차단과 기본적으로 통합 되어 있습니다. 이 기능을 사용하면 단순히 알림이 뜨는 것이 아니라 "이 웹 사이트가 조직에 의해 차단 되었습니다"라는 메시지가 포함 된 전체 페이지 적색 차단이 포함됩니다.

- 페이지 철회에 동기 XmlHttpRequest 허용 안 함 웹 페이지가 언로드 되는 동안 동기 XmlHttpRequests 보내기가 제거됩니다. 이 변경으로 인해 브라우저 성능과 안정성이 향상되지만, sendBeacon 및 페치를 포함하여 최신 웹 API를 사용하도록 아직 업데이트되지 않은 웹 응용 프로그램에 영향을 줄 수 있습니다. 이 변경 내용을 사용하지 않도록 설정하고 페이지 철회 중에 동기 XHR을 허용하는 그룹 정책은 Microsoft Edge 88까지 사용할 수 있습니다. 자세한 내용은 [사이트 호환성-Microsoft Edge로 들어오는 변화에 영향](/microsoft-edge/web-platform/site-impacting-changes)을 참조하세요.

### <a name="policy-updates"></a>정책 업데이트

#### <a name="new-policies"></a>새로운 정책

새 정책 15개를 추가했습니다. [Microsoft Edge Enterprise 랜딩 페이지](https://aka.ms/EdgeEnterprise)에서 업데이트된 관리 템플릿을 다운로드합니다. 다음과 같은 새 정책이 추가되었습니다.

- [AllowSurfGame](./microsoft-edge-policies.md#allowsurfgame) - 게임 서핑을 허용합니다.
- [AllowTokenBindingForUrls](./microsoft-edge-policies.md#allowtokenbindingforurls) - Microsoft Edge에서 토큰 바인딩을 설정하려는 사이트 목록을 구성합니다.
- [BingAdsSuppression](./microsoft-edge-policies.md#bingadssuppression) - Bing 검색 결과에 대해 모든 광고를 차단합니다.
- [BuiltinCertificateVerifierEnabled](./microsoft-edge-policies.md#builtincertificateverifierenabled) - 서버 인증서를 확인하는 데 기본 제공 인증서 검증 도구를 사용할지 여부를 결정합니다.
- [ClearCachedImagesAndFilesOnExit](./microsoft-edge-policies.md#clearcachedimagesandfilesonexit) - Microsoft Edge를 종료할 때 캐시된 이미지 및 파일을 삭제합니다.
- [ConfigureShare](./microsoft-edge-policies.md#configureshare) - 공유 환경을 구성합니다.
- [DeleteDataOnMigration](./microsoft-edge-policies.md#deletedataonmigration) - 마이그레이션에서 이전 브라우저 데이터를 삭제합니다.
- [DnsOverHttpsMode](./microsoft-edge-policies.md#dnsoverhttpsmode) - DoH(DNS over HTTPS) 모드를 제어합니다.
- [DnsOverHttpsTemplates](./microsoft-edge-policies.md#dnsoverhttpstemplates) - 원하는 DoH(DNS over HTTPS) 확인자의 URI 서식 파일을 지정합니다.
- [FamilySafetySettingsEnabled](./microsoft-edge-policies.md#familysafetysettingsenabled) - 사용자가 가족 보호를 구성할 수 있도록 허용합니다.
- [LocalProvidersEnabled](./microsoft-edge-policies.md#localprovidersenabled) - 로컬 공급자의 제안을 허용합니다.
- [ScrollToTextFragmentEnabled](./microsoft-edge-policies.md#scrolltotextfragmentenabled) - URL 조각에 지정된 텍스트로 스크롤할 수 있습니다.
- [ScreenCaptureAllowed](./microsoft-edge-policies.md#screencaptureallowed) - 화면 캡처를 허용하거나 거부합니다.
- [SynctypesListdisabled](./microsoft-edge-policies.md#synctypeslistdisabled) - 동기화에서 제외되는 유형의 목록을 구성합니다.
- [NativeWindowOcclusionEnabled](./microsoft-edge-policies.md#nativewindowocclusionenabled) - 원시 창 숨김을 사용합니다.

#### <a name="deprecated-policy"></a>더 이상 사용되지 않는 정책

이 릴리스에서는 다음 정책이 계속 작동합니다. 이 정책들은 향후 릴리스에서는 "폐기"될 것입니다.

[EnableDomainActionsDownload](./microsoft-edge-policies.md#enabledomainactionsdownload) Microsoft에서 도메인 작업 다운로드 가능

<!-- end 83 -->

## <a name="version-81041677-may-18"></a>버전 81.0.416.77: 5월 18일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-81041672-may-7"></a>버전 81.0.416.72: 5월 7일

보안 업데이트는 [여기](./microsoft-edge-relnotes-security.md#may-7-2020)에서 확인할 수 있습니다

## <a name="version-81041668-april-29"></a>버전 81.0.416.68: 4월 29일

보안 업데이트는 [여기](./microsoft-edge-relnotes-security.md#april-29-2020)에서 확인할 수 있습니다

## <a name="version-81041664-april-23"></a>버전 81.0.416.64: 4월 23일

보안 업데이트는 [여기](./microsoft-edge-relnotes-security.md#april-23-2020)에서 확인할 수 있습니다

## <a name="version-81041658-april-17"></a>버전 81.0.416.58: 4월 17일

보안 업데이트는 [여기](./microsoft-edge-relnotes-security.md#april-17-2020)에서 확인할 수 있습니다

## <a name="version-81041653-april-13"></a>버전 81.0.416.53: 4월 13일

보안 업데이트는 [여기](./microsoft-edge-relnotes-security.md#april-13-2020)에서 확인할 수 있습니다

### <a name="feature-updates"></a>기능 업데이트

- 기업에서 무단 공개로부터 중요한 데이터를 보호하는 데 도움이 되는 WIP(Windows Information Protection)에 대한 지원이 추가되었습니다. [자세한 내용을 알아보세요](./microsoft-edge-security-windows-information-protection.md).

- 이제 컬렉션을 사용할 수 있습니다. 시작하려면 주소 표시줄 옆에 있는 컬렉션 아이콘을 클릭하세요. 이 작업을 수행하면 컬렉션을 만들고 편집하고 볼 수 있는 컬렉션 창이 열립니다. 사용자가 웹에서 수행한 작업을 기반으로 컬렉션을 디자인했습니다. 쇼핑객, 여행자, 교사 또는 학생인 경우 컬렉션이 도움이 될 수 있습니다. [자세한 내용을 알아보세요](https://blogs.windows.com/msedgedev/2019/12/09/improvements-collections-sync-microsoft-edge/#LuDPRDUDCgdgdOVt.97).

- 일관성을 유지하려면 Microsoft Edge 도구 모음에서 컬렉션 버튼 제거(도구 모음에서 숨기기)를 허용하세요.

- 온-프레미스 Active Directory 계정 자동 로그인은 이를 설정한 조직만을 대상으로 합니다.  사용자가 이미 온-프레미스 AD 계정으로 로그인한 경우 해당 계정에서 로그아웃될 수 있습니다. 사용자는 운영 체제에서 기본 계정이 Microsoft 계정 또는 Active Directory 계정인 경우에만 기본 계정으로 자동 로그인됩니다. 관리자는 ConfigureOnPremisesAccountAutoSignIn 정책을 사용하는 온-프레미스 AD 계정으로 자동 로그인을 설정할 수 있습니다.

- Application Guard 이제 컨테이너에서 확장 지원을 사용할 수 있습니다.

- Internet Explorer 모드에서 열도록 구성된 페이지로 이동할 때 Internet Explorer가 설치되지 않았음을 사용자에게 알리는 메시지를 추가했습니다.

- z-인덱스 스택 컨텍스트를 디버깅하는 데 도움이 되는 새로운 기능으로 Microsoft Edge DevTools의 3D 보기 도구를 업데이트했습니다. 3D 보기는 색상 및 스태킹을 사용하여 DOM(문서 개체 모델) 깊이를 표시하며 z-인덱스 보기는 페이지의 여러 스태킹 컨텍스트를 분리하는 데 도움이 됩니다. [자세한 내용을 알아보세요](https://blogs.windows.com/msedgedev/2020/01/23/debug-z-index-3d-view-edge-devtools/).

- F12 Dev 도구를 10개의 새로운 언어로 현지화하여 나머지 브라우저에서 사용되는 언어와 일치합니다. [자세한 내용을 알아보세요](https://blogs.windows.com/msedgedev/2020/02/04/localizing-edge-devtools/).

- 돌비 비전 재생에 대한 지원이 추가되었습니다. 돌비 비전 사용 Windows 10 빌드 17134(2018년 4월 업데이트) 웹사이트에서 돌비 비전 콘텐츠를 표시할 수 있습니다. [Netflix](https://help.netflix.com/en/node/42384)에서 Dolby Vision 컨텐츠를 활성화하는 방법을 참조하세요.

- Microsoft Edge는 이제 중복 즐겨찾기를 식별 및 제거하고 동일한 이름의 폴더를 병합할 수 있습니다. 이 도구에 액세스하려면 브라우저 툴바에서 별표를 클릭하고 "중복 즐겨찾기 제거"를 선택하십시오.  변경 사항을 확인할 수 있으며 즐겨찾기에 대한 모든 업데이트가 디바이스 간에 동기화됩니다.

- 어두운 테마의 일반 브라우징 창을 InPrivate 창과 구별하기가 어려울 수 있다고 들었습니다. 두 창 프레임이 모두 어둡기 때문입니다. 오른쪽 상단 모서리에 있는 새로운 솔리드 InPrivate 탄환은 사용자가 InPrivate를 탐색하고 있는지 확인하도록 도와줍니다.

- 올바른 브라우저 프로필에서 외부 링크를 여세요. *edge://settings/multiProfileSettings*에서 외부 앱용으로 열린 링크에 대한 기본 프로필을 선택하십시오.

- 이전에 계정으로 로그인한 후 다른 계정으로 브라우저 프로필에 로그인하는 사용자에게 경고를 보내는 알림 기능이 추가되었습니다. 이러한 경고는 의도하지 않은 데이터 병합을 방지하는 데 도움이 됩니다.

- Microsoft 계정에 결제 카드를 저장한 경우 결제 양식을 작성하는 동안 Microsoft Edge에서 사용할 수 있습니다. Microsoft 계정의 카드는 데스크톱 장치간에 동기화되며 2단계 인증(CVC 코드 및 Microsoft ID) 후 전체 세부 정보가 웹 사이트와 공유됩니다. 더욱 편리하도록 인증하는 동안 장치에서 카드 사본을 안전하게 저장하도록 선택할 수 있습니다.

- 줄 포커스는 컨텐츠를 읽을 때 제한된 부분에 집중하려는 사용자를 위해 설계되었습니다. 사용자는 한 번에 1, 3 또는 5줄에 초점을 유지하고 나머지 페이지는 흐리게 하여 사용자가 방해받지 않고 집중하여 읽을 수 있도록 합니다. 사용자는 터치 또는 화살표 키를 사용하여 스크롤할 수 있으며 그에 따라 초점이 이동합니다.

- Microsoft Edge는 이제 Windows 플랫폼 8.1 이상에서 Windows Speller와 통합되었습니다. 이 통합은 더 많은 언어 사전에 액세스할 수 있고 Windows 사용자 지정 사전을 사용할 수 있는 기능으로 더 많은 언어 지원을 제공합니다. OS 언어 설정에 언어가 추가된 경우 사용자에게 추가 조치가 필요하지 않습니다. 또한 언어 맞춤법 검사 토글이 Microsoft Edge 설정에서 활성화됩니다.

- Microsoft Edge를 사용하여 PDF 문서를 열면 사용자는 하이라이트를 만들고 색상을 변경하고 하이라이트를 삭제할 수 있습니다. 이 기능은 나중에 문서의 중요한 부분을 참조하고 공동 작업하는 데 도움이 됩니다.

- 웹에 최적화된 긴 PDF 문서가 로딩될 때 사용자가 보고 있는 페이지는 나머지 문서가 로딩되는 동안 빠르게 병렬로 로드됩니다.

- 이제 F9 키를 누르기만 하면 웹사이트에 대한 몰입형 리더를 쉽게 시작할 수 있습니다.

- 이제 키보드 단축키(Ctrl + Shift + U)를 사용하여 소리내어 읽기를 더 쉽게 시작할 수 있습니다.

- Microsoft Edge를 설치할 때 데스크탑 아이콘 작성을 억제할 수 있는 MSI 명령줄 매개 변수가 추가되었습니다. 다음 예제에서 이 새로운 매개 변수를 사용하는 방법을 보여 줍니다. <br>
`MicrosoftEdgeEnterpriseX64.msi DONOTCREATEDESKTOPSHORTCUT=true`<br>
다음 릴리스에서 이 기능을 지원하기 위한 그룹 정책이 있습니다.

### <a name="policy-updates"></a>정책 업데이트

#### <a name="new-policies"></a>새로운 정책

새 정책 11개를 추가했습니다. [Microsoft Edge Enterprise 랜딩 페이지](https://aka.ms/EdgeEnterprise)에서 업데이트된 관리 템플릿을 다운로드합니다. 다음과 같은 새 정책이 추가되었습니다.

- [ AmbientAuthenticationInPrivateModesEnabled ](./microsoft-edge-policies.md#ambientauthenticationinprivatemodesenabled)-InPrivate 및 게스트 프로필에 대한 주변 인증을 사용합니다. 
- [AudioSandboxEnabled](./microsoft-edge-policies.md#audiosandboxenabled) - 오디오 샌드박스를 실행할 수 있도록 합니다.
- [ForceLegacyDefaultReferrerPolicy](./microsoft-edge-policies.md#forcelegacydefaultreferrerpolicy) - 다운 그레이드할 때 참조되지 않는 기본 참조 정책을 사용합니다.
- [GloballyScopeHTTPAuthCacheEnabled](./microsoft-edge-policies.md#globallyscopehttpauthcacheenabled) - 전역적으로 범위가 지정된 HTTP 인증 캐시를 활성화합니다.
- [ImportExtensions](./microsoft-edge-policies.md#importextensions) - 확장명 가져오기를 허용합니다.
- [ImportCookies](./microsoft-edge-policies.md#importcookies) - 쿠키를 가져올 수 있습니다.
- [ImportShortcuts](./microsoft-edge-policies.md#importshortcuts) - 바로 가기 가져오기를 허용합니다.
- [InternetExplorerIntegrationSiteRedirect](./microsoft-edge-policies.md#internetexplorerintegrationsiteredirect)-Internet Explorer 모드 페이지에서 시작할 때 구성되지 않은 사이트에 대한 "페이지 내" 탐색 작동 방식을 지정하십시오.
- [ StricterMixedContentTreatmentEnabled ](./microsoft-edge-policies.md#strictermixedcontenttreatmentenabled) -혼합 컨텐츠에 대해 보다 엄격한 처리를 사용합니다.
- [TLS13HardeningForLocalAnchorsEnabled](./microsoft-edge-policies.md#tls13hardeningforlocalanchorsenabled) - 로컬 신뢰 앵커에 대한 TLS 1.3 보안 기능을 사용하세요.
- [ConfigureOnPremisesAccountAutoSignIn](./microsoft-edge-policies.md#configureonpremisesaccountautosignin) - Azure AD 도메인 계정이 없는 경우 Active Directory 도메인 계정으로 자동 로그인을 구성하십시오.

#### <a name="policy-name-and-caption-changes"></a>정책 이름 및 캡션 변경

정책 `OmniboxMSBProviderEnabled`은 [AddressBarMicrosoftSearchInBingProviderEnabled](//DeployEdge/microsoft-edge-policies#addressbarmicrosoftsearchinbingproviderenabled)으로 변경됩니다. 정책의 캡션은 "주소 표시 줄에서 Bing에서 Microsoft 검색 제안 사용"입니다.

#### <a name="deprecated-policies"></a>더 이상 사용되지 않는 정책

이 릴리스에서는 다음 정책이 계속 작동합니다. 이 정책들은 향후 릴리스에서는 "폐기"될 것입니다.

- [WebComponentsV0Enabled](./microsoft-edge-policies.md#webcomponentsv0enabled) - M84까지 웹 구성 요소 v0 API를 다시 사용하도록 설정합니다.
- [WebDriverOverridesIncompatiblePolicies](./microsoft-edge-policies.md#webdriveroverridesincompatiblepolicies)-WebDriver가 호환되지 않는 것으로 다시 정의될 수 있습니다.

#### <a name="resolved-issues"></a>해결된 문제

- Microsoft Edge의 IE 모드가 파일이 다운로드된 후에도 계속해서 다운로드 대화 상자를 표시하는 문제를 해결했습니다.
- 이미 IE 모드에 있는 페이지에서 새 IE 모드 탭을 열도록 트리거할 때 Microsoft Edge가 세션 쿠키를 삭제하던 문제를 수정했습니다.

## <a name="version-800361111-april-7"></a>버전 80.0.361.111: 4월 7일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-800361109-april-1"></a>버전 80.0.361.109: 4월 1일

보안 업데이트는 [여기](./microsoft-edge-relnotes-security.md#april-1-2020)에서 확인할 수 있습니다

## <a name="version-80036169-march-19"></a>버전 80.0.361.69: 3월 19일

보안 업데이트는 [여기](./microsoft-edge-relnotes-security.md#march-19-2020)에서 확인할 수 있습니다

## <a name="version-80036166-march-4"></a>버전 80.0.361.66: 3월 4일

보안 업데이트는 [여기](./microsoft-edge-relnotes-security.md#march-4-2020)에서 확인할 수 있습니다

## <a name="version-80036162-february-25"></a>버전 80.0.361.62: 2월 25일

보안 업데이트는 [여기](./microsoft-edge-relnotes-security.md#february-25-2020)에서 확인할 수 있습니다

## <a name="version-80036157-february-20"></a>버전 80.0.361.57: 2월 20일

보안 업데이트는 [여기](./microsoft-edge-relnotes-security.md#february-20-2020)에서 확인할 수 있습니다

## <a name="version-80036156-february-19"></a>버전 80.0.361.56: 2월 19일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-80036154-february-14"></a>버전 80.0.361.54: 2월 14일

### <a name="resolved-issues"></a>해결된 문제

- Microsoft Edge에서 암호, 결제 및 쿠키를 가져오지 못하는 문제를 해결했습니다.

## <a name="version-80036150-february-11"></a>버전 80.0.361.50: 2월 11일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-80036148-february-7"></a>버전 80.0.361.48: 2월 7일

보안 업데이트는 [여기](./microsoft-edge-relnotes-security.md#february-7-2020)에서 확인할 수 있습니다

### <a name="feature-updates"></a>기능 업데이트

- 잠재적으로 원치 않는 앱을 다운로드하지 못하도록 SmartScreen 보호가 추가되었습니다. [자세히 알아보기](/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus)
- 돌비 비전 재생에 대한 지원이 추가되었습니다.
- Windows Mixed Reality 사용자가 VR 헤드셋에서 360° 동영상을 볼 수 있도록 설정했습니다.
- 텍스트 간격을 늘리기 위해 읽기용 보기에 옵션을 추가했습니다.
- Surface 펜 지우개를 사용하여 링크 지우기에 대한 지원이 추가되었습니다.
- 편집기 모드에서 화살표 키와 스페이스바를 사용하여 피드백 스크린샷에 그리기에 대한 지원이 추가되었습니다.
- 피드백을 제출할 때 모두 검은색으로 표시되는 것을 방지하기 위해 스크린샷 안정성이 개선되었습니다.
- 장치가 인터넷에 연결되어 있지 않을 때 표시되는 로컬 새 탭 페이지에 어두운 테마 지원이 추가되었습니다.
- 업데이트, 충돌 등 후 브라우저 세션이 복원될 때 앱으로 설치된 웹 사이트를 복원할 수 있는 기능을 추가했습니다.
- 브라우저를 그룹 정책으로 관리하는 경우 PDF UI에 어두운 테마 지원이 추가되었습니다.
- Adobe Flash를 버전 32.0.0.321로 업데이트했습니다. [자세히 알아보기](https://helpx.adobe.com/flash-player/release-note/fp_32_air_32_release_notes.html)

### <a name="policy-updates"></a>정책 업데이트

#### <a name="new-policies"></a>새로운 정책

새 정책 16개를 추가했습니다. [Microsoft Edge Enterprise 랜딩 페이지](https://aka.ms/EdgeEnterprise)에서 업데이트된 관리 템플릿을 다운로드합니다. 다음과 같은 새 정책이 추가되었습니다.

- [AlternateErrorPagesEnabled](./microsoft-edge-policies.md#alternateerrorpagesenabled) - 웹 페이지를 찾을 수 없는 경우 비슷한 페이지를 제안합니다.
- [Defaultinsecurecontentsetting 설정](./microsoft-edge-policies.md#defaultinsecurecontentsetting) - 안전하지 않은 콘텐츠 예외의 사용을 제어합니다.
- [DNSInterceptionChecksEnabled](./microsoft-edge-policies.md#dnsinterceptionchecksenabled) - DNS 차단 검사를 사용하도록 설정되었습니다.
- [HideFirstRunExperience](./microsoft-edge-policies.md#hidefirstrunexperience) - 첫 실행 환경 및 시작 화면을 숨깁니다.
- [Insecurecontentallowedforurls](./microsoft-edge-policies.md#insecurecontentallowedforurls) - 지정된 사이트의 안전하지 않은 콘텐츠를 허용합니다.
- [InsecureContentBlockedForUrls](./microsoft-edge-policies.md#insecurecontentblockedforurls) - 지정된 사이트의 안전하지 않은 콘텐츠를 차단합니다.
- [LegacySameSiteCookieBehaviorEnabled](./microsoft-edge-policies.md#legacysamesitecookiebehaviorenabled) - 기본 레거시 SameSite 쿠키 동작 설정을 사용합니다.
- [LegacySameSiteCookieBehaviorEnabledForDomainList](./microsoft-edge-policies.md#legacysamesitecookiebehaviorenabledfordomainlist) - 지정된 사이트의 쿠키에 대한 레거시 SameSite 동작으로 되돌립니다.
- [PaymentMethodQueryEnabled](./microsoft-edge-policies.md#paymentmethodqueryenabled) - 웹 사이트에서 사용 가능한 결제 방법을 쿼리하도록 허용합니다.
- [PersonalizationReportingEnabled](./microsoft-edge-policies.md#personalizationreportingenabled) - Microsoft에 검색 기록을 보내서 광고, 검색, 뉴스를 개인 설정하도록 허용합니다.
- [PinningWizardAllowed](./microsoft-edge-policies.md#pinningwizardallowed) - 작업 표시줄에 고정 마법사를 허용합니다.
- [SmartScreenPuaEnabled](./microsoft-edge-policies.md#smartscreenpuaenabled) - 잠재적으로 원치 않는 앱을 차단하도록 Microsoft Defender SmartScreen을 구성합니다.
- [TotalMemoryLimitMb](./microsoft-edge-policies.md#totalmemorylimitmb) - 단일 Microsoft Edge 인스턴스에서 사용할 수 있는 메모리 크기(mb)를 설정합니다.
- [WebAppInstallForceList](./microsoft-edge-policies.md#webappinstallforcelist) - 강제 설치된 웹 앱 목록을 구성합니다.
- [WebComponentsV0Enabled](./microsoft-edge-policies.md#webcomponentsv0enabled) - M84까지 웹 구성 요소 v0 API를 다시 사용하도록 설정합니다.
- [WebRtcLocalIpsAllowedUrls](./microsoft-edge-policies.md#webrtclocalipsallowedurls) - WebRTC에서 로컬 IP 주소의 노출을 관리합니다.

#### <a name="deprecated-policies"></a>더 이상 사용되지 않는 정책

다음 정책은 사용되지 않습니다.

- [NewTabPageCompanyLogo](./microsoft-edge-policies.md#newtabpagecompanylogo) - 새 탭 페이지의 회사 로고를 설정합니다.

### <a name="resolved-issues"></a>해결된 문제

- 오디오가 Citrix 환경에서 작동하지 않는 문제를 해결했습니다.
- Microsoft Edge와 레거시 Microsoft Edge side-by-side 환경에서 레거시 링크가 손상되고 작동이 중단되는 문제가 해결되었습니다.

## <a name="see-also"></a>참고 항목

- [Microsoft Edge Enterprise 방문 페이지](https://aka.ms/EdgeEnterprise)