---
title: 베타 채널 용 Microsoft Edge 릴리스 정보
ms.author: aguta
author: AndreaLBarr
manager: srugh
ms.date: 10/05/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 베타 채널 용 Microsoft Edge 릴리스 정보
ms.openlocfilehash: a2957d3c52d18fe75cb52719896438e6becf6dbd
ms.sourcegitcommit: e825c6a1b0e63004288e13f6bb672743b0ecfafb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/05/2021
ms.locfileid: "12069004"
---
# <a name="release-notes-for-microsoft-edge-beta-channel"></a>Microsoft Edge 베타 채널에 대한 릴리스 정보

이 릴리스 정보는 Microsoft Edge 베타 채널에 포함된 새로운 기능 및 비보안 업데이트에 대한 정보를 제공합니다. 이 릴리스 정보의 보관된 버전은 [여기](microsoft-edge-relnote-archive-beta-channel.md)에서 볼 수 있습니다.

> [!NOTE]
> Microsoft Edge 웹 플랫폼은 사용자 환경, 보안 및 개인 정보 개선을 위해 지속적으로 진화하고 있습니다. 자세히 알아보려면 [Microsoft Edge에 적용될 사이트 호환성에 영향을 미치는 변경 사항](/microsoft-edge/web-platform/site-impacting-changes)을 참조하세요.

## <a name="version-950102014-october-5"></a>버전 95.0.1020.14: 10월 5일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-95010209-september-28"></a>버전 95.0.1020.9: 9월 28일

### <a name="feature-updates"></a>기능 업데이트

- **SharePoint Online 라이브러리에 대한 파일 탐색기 지원에서 Microsoft Edge.**  이제 온라인 최신 문서 라이브러리의 파일 탐색기에서 보기 기능을 SharePoint 수 있습니다. 이 환경을 표시하고 사용자에게 작동하려면 Microsoft Edge 정책 SharePoint "Microsoft Edge 페이지의 파일 탐색기에서 보기 기능 [구성"을](/deployedge/microsoft-edge-policies#configureviewinfileexplorer) 사용하도록 설정하고 SharePoint Online 테넌트 구성을 업데이트해야 합니다. 자세한 내용은 다음을 SharePoint 파일 탐색기를 사용하여 파일 Microsoft Edge - SharePoint [보기를 Microsoft 365 | Microsoft Docs.](/SharePoint/sharepoint-view-in-edge)

- **인트라넷 영역 파일 URL 링크는 파일 탐색기에서 Windows 열립니다.**  인트라넷 영역 HTTPS 웹 사이트에서 시작된 인트라넷 영역 파일에 대한 파일 URL 링크가 해당 파일 또는 디렉터리에 대한 Windows 열 수 있습니다. [IntranetFileLinksEnabled](/deployedge/microsoft-edge-policies#intranetfilelinksenabled) 정책을 사용하여 이 환경을 사용하도록 설정할 수 있습니다.

- **다운로드 환경 개선**  사용자 환경 다운로드에 대한 지원이 점진적 웹 응용 프로그램 PWAS 및 WebView로 확장되고 있습니다. 또한 파일 탐색기 및 데스크톱으로 끌어서 놓기를 지원하기 시작할 것입니다.

- **PDF 문서에서 벗어날 위치를 선택하십시오.**  이제 PDF 문서를 마지막으로 닫은 위치부터 다시 읽을 수 있습니다.

- **효율성 모드는 노트북이 배터리 절약 모드로 전환할 때 배터리 사용 시간을 연장합니다.**  랩톱이 배터리 절약 모드로 전환하면 브라우저에서 리소스 사용을 관리하여 컴퓨터의 배터리 수명을 연장할 수 있도록 효율성 모드가 활성화됩니다. 효율성 모드가 활성화될 때, 배터리가 언플러그되지 않은 상태 및 낮은 배터리, 언플러그된, 항상 및 사용 안 하게 되는 경우의 네 가지 옵션이 있습니다. 참고: 제어된 기능 롤아웃입니다. 배터리가 있는 디바이스에는 기능이 켜져 있습니다.

***새로운 정책***

- [BrowserLegacyExtensionPointsBlockingEnabled](/DeployEdge/microsoft-edge-policies#browserlegacyextensionpointsblockingenabled) 브라우저 레거시 확장 지점 차단 사용
- [CrossOriginWebAssemblyModuleSharingEnabled](/DeployEdge/microsoft-edge-policies#crossoriginwebassemblymodulesharingenabled) WebAssembly 모듈을 원본 간으로 보낼 수 있는지 여부를 지정합니다.
- [DisplayCapturePermissionsPolicyEnabled](/DeployEdge/microsoft-edge-policies#displaycapturepermissionspolicyenabled) 디스플레이 캡처 권한-정책을 검사할지 또는 건너뜁니다.
- [InternetExplorerIntegrationWindowOpenHeightAdjustment](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationwindowopenheightadjustment) IE 모드 페이지와 Edge 모드 페이지에서 원본으로 하는 window.open 높이 사이의 픽셀 조정 구성
- [InternetExplorerIntegrationWindowOpenWidthAdjustment](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationwindowopenwidthadjustment) IE 모드 페이지와 Edge 모드 페이지에서 원본으로 하는 window.open 너비 사이의 픽셀 조정 구성
- [IntranetFileLinksEnabled](/DeployEdge/microsoft-edge-policies#intranetfilelinksenabled) 파일 탐색기에서 인트라넷 영역 파일 URL Microsoft Edge 열 수 Windows 허용
- [ShadowStackCrashRollbackBehavior](/DeployEdge/microsoft-edge-policies#shadowstackcrashrollbackbehavior) ShadowStack 크래시 롤백 동작 구성
- [VisualSearchEnabled](/DeployEdge/microsoft-edge-policies#visualsearchenabled) 시각적 검색 사용

***폐기된 정책***

- [InternetExplorerIntegrationTestingAllowed](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationtestingallowed) - Internet Explorer 모드 테스트를 허용합니다.
- [LegacySameSiteCookieBehaviorEnabled](/DeployEdge/microsoft-edge-policies#legacysamesitecookiebehaviorenabled) 기본 레거시 SameSite 쿠키 동작 설정 사용

## <a name="version-94099223-september-17"></a>버전 94.0.992.23: 9월 17일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-94099219-september-13"></a>버전 94.0.992.19: 9월 13일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-94099214-september-7"></a>버전 94.0.992.14: 9월 7일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-9409929-september-2"></a>버전 94.0.992.9: 9월 2일

### <a name="feature-updates"></a>기능 업데이트

- **Microsoft Edge 및 안정 채널의 업데이트에 대한 4주 케이던스로 이동하는 것이 좋습니다.**  주 버전에 대해 4주간의 새로운 릴리스 주기를 채택할 것입니다. 결정에 대한 자세한 내용은 다음을 읽어 볼 수 있습니다. https://blogs.windows.com/msedgedev/2021/03/12/new-release-cycles-microsoft-edge-extended-stable/

- **새로운 확장 안정 옵션이 제공됩니다.**  Microsoft는 관리되는 엔터프라이즈 고객에게 새로운 확장 안정 옵션을 제공하고 있습니다. 확장 안정 옵션은 짝수 버전으로 유지되며 8주마다 업데이트됩니다. 격주로 보안 업데이트가 있을 예정입니다.  추가 정보: https://blogs.windows.com/msedgedev/2021/07/15/opt-in-extended-stable-release-cycle/

- **MHTML 파일을 여는 기본 동작이 개선되었습니다.**  MHTML 파일이 Microsoft Edge에서 저장되지 않은 경우(Microsoft Edge에서 다른 이름으로 저장 또는 다른 이름으로 페이지 저장 옵션 사용) IE 모드가 활성화된 경우 MHTML 파일은 IE 모드에서 계속 열립니다. 파일이 Microsoft Edge에서 저장되었다면 이제 Microsoft Edge에서 열립니다.  이 변경 사항은 Microsoft Edge에서 저장할 때 IE 모드에서 MHTML 파일을 열 때 관찰된 렌더링 문제를 수정합니다.

- **컨텍스트를 보호하기 위해 사설 네트워크 요청을 제한합니다.** 인터넷 페이지에서 로컬(인트라넷) 네트워크의 리소스에 액세스하려면 해당 페이지가 HTTPS를 통해 전달되어야 합니다. 이 변경은 Microsoft Edge 기반으로 하는 Chromium 프로젝트에서 발생합니다. 자세한 내용은 [크롬 플랫폼 상태 항목](https://chromestatus.com/feature/5436853517811712)으로 이동합니다. 비보안 페이지와의 호환성을 유지해야 하는 시나리오를 지원하기 위해 [InsecurePrivateNetworkRequestAllowed](/deployedge/microsoft-edge-policies#insecureprivatenetworkrequestsallowed) 및 [InsecurePrivateNetworkRequestAllowedForUrls](/deployedge/microsoft-edge-policies#insecureprivatenetworkrequestsallowedforurls)의 두 가지 호환성 정책을 사용할 수 있습니다.

- **혼합 콘텐츠 다운로드를 차단합니다.** 보안 페이지는 다른 보안 페이지에서 호스팅되는 파일만 다운로드하고 비보안(비 HTTPS) 페이지에서 호스팅되는 다운로드는 보안 페이지에서 시작하면 차단됩니다. 이 변경은 Microsoft Edge 기반으로 하는 Chromium 프로젝트에서 발생합니다. 자세한 내용은 [Google 보안 블로그 항목](https://security.googleblog.com/2020/02/protecting-users-from-insecure_6.html)으로 이동하세요.

- **온-프레미스 계정에 대한 암시적 로그인을 활성화합니다.**   OnlyOnPremisesImplicitSigninEnabled 정책을 활성화하면 암시적 로그인에 대해 온-프레미스 계정만 활성화됩니다.  Microsoft Edge는 MSA 또는 AAD 계정에 암시적으로 로그인을 시도하지 않습니다. 온-프레미스 계정에서 AAD 계정으로의 업그레이드도 중지됩니다.

- **PDF 문서에 추가된 무료 양식 텍스트 상자입니다.**  이제 양식을 채우고 표시되는 메모를 추가하는 데 사용할 수 있는 PDF 문서에 무료 양식 텍스트 상자를 추가할 수 있습니다.

- **암호를 쉽게 업데이트합니다.**  이제 브라우저에서 특정 웹 사이트의 암호 변경 페이지로 바로 이동하여 시간을 절약하고 페이지를 수동으로 탐색할 필요가 없습니다. 이 페이지에 있는 경우 브라우저는 기존 암호를 자동으로 입력하고 강력하고 고유한 새 암호를 제안합니다.  참고: 현재 이 기능은 제한된 수의 사이트에서 사용할 수 있습니다.  

- **새 접근성 설정 페이지입니다.** 접근성 관련 설정을 한 페이지에 모았습니다. 기본 설정 목록에서 새로운 edge://settings/accessibility 페이지를 찾을 수 있습니다. 여기에서 웹 페이지를 더 크게 만들고 초점 영역 주위에 높은 가시성 개요를 표시하는 설정 및 웹 탐색 환경을 개선하는 데 도움이 될 수 있는 기타 설정을 찾을 수 있습니다. Microsoft Edge의 향후 버전에서 여기에 새로운 설정을 계속 추가할 예정입니다.

***새로운 정책***

- [ApplicationGuardPassiveModeEnabled](/DeployEdge/microsoft-edge-policies#applicationguardpassivemodeenabled) Application Guard 사이트 목록 구성을 무시하고 Edge를 정상적으로 탐색합니다.
- [OnPremisesImplicitSigninEnabled](/DeployEdge/microsoft-edge-policies#onlyonpremisesimplicitsigninenabled) 암시적 로그인에 대해 사용하도록 설정된 온-프레미스 계정만
- [WebRtcRespectOsRoutingTableEnabled](/DeployEdge/microsoft-edge-policies#webrtcrespectosroutingtableenabled) WebRTC를 통해 피어 투 피어 연결을 만들 때 Windows OS 라우팅 테이블 규칙 지원 활성화

***폐기된 정책***

- [UserAgentClientHintsEnabled](/DeployEdge/microsoft-edge-policies#useragentclienthintsenabled) 사용자 에이전트 클라이언트 힌트 기능 사용

## <a name="version-93096133-august-27"></a>버전 93.0.961.33: 8월 27일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-93096127-august-20"></a>버전 93.0.961.27: 8월 20일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-93096124-august-18"></a>버전 93.0.961.24: 8월 18일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-93096111-august-3"></a>버전 93.0.961.11: 8월 3일

### <a name="feature-updates"></a>기능 업데이트

- **Microsoft Edge 초기 기본 설정입니다.**  Microsoft Edge 버전 93부터 초기 Microsoft Edge 를 추가하면 엔터프라이즈에 배포하는 것이 더 [쉬워집니다.](/deployedge/initial-preferences-support-on-microsoft-edge-browser)

- **Microsoft Edge의 IE 모드는 "병합 금지" 동작을 지원합니다.**  Microsoft Edge 버전 93부터 Microsoft Edge IE 모드는 "병합 안 Microsoft Edge"를 지원합니다. 최종 사용자의 경우 IE 모드 응용 프로그램에서 새 브라우저 창을 시작하면 IE11의 동작과 비슷한 별도의 세션에 있습니다. 세션 공유를 방지해야 하는 사이트를 구성하려면 사이트 목록을 조정해야 합니다. 이면에서는 Microsoft Edge의 각 창에서 IE 모드 탭이 해당 창 내에 처음 방문하는 경우 지정된 "병합 금지" 사이트 중 하나일 경우 해당 창에서 마지막 IE 모드 탭이 닫힐 때까지 해당 창이 다른 모든 Microsoft Edge 창과 다른 "병합 금지" IE 세션으로 잠깁니다. [여기](/deployedge/edge-ie-mode-faq#does-ie-mode-on-microsoft-edge-support-the--no-merge--option-that-was-supported-in-internet-explorer-11-)에서 자세히 알아보세요.

- **탭 그룹**  탭을 사용자 정의 그룹으로 분류하는 기능을 사용하면 여러 작업 스트림에서 탭을 보다 효과적으로 찾고 전환하고 관리할 수 있습니다. 이를 위해 버전 93에서 시작하여 탭 Microsoft Edge 켜고 있습니다.

- **세로 탭을 사용하는 동안 제목 표시줄을 숨깁니다.**  세로 탭에서 브라우저의 제목 표시줄을 숨겨 몇 개의 픽셀을 다시 가져옵니다. Microsoft Edge 버전 93부터 edge://settings/appearance 도구 모음 사용자 지정 섹션에서 세로 탭 모드에서 제목 표시줄을 숨기는 옵션을 선택합니다.

- **호버 도구 모음의 PiP(사진 비디오 사진)입니다.**  버전 Microsoft Edge 버전 93부터 PiP(그림) 모드로 전환하기가 훨씬 쉬워집니다. 지원되는 비디오 위로 마우스를 가져가면 PiP 창에서 해당 비디오를 볼 수 있는 도구 모음이 나타납니다.  참고: 현재 macOS의 Microsoft Edge 사용할 수 있습니다.  사용자에 대한 롤아웃을 계속하는 Windows 다시 확인해보아야 합니다.

- **TLS에서 3DES 제거**  Microsoft Edge 버전 93부터는 TLS_RSA_WITH_3DES_EDE_CBC_SHA 암호 제품군에 대한 지원이 제거됩니다. 이 변경은 Microsoft Edge 기반으로 하는 Chromium 프로젝트에서 발생합니다. 자세한 내용은 [크롬 플랫폼 상태 항목](https://chromestatus.com/feature/6678134168485888)으로 이동합니다. 또한 Microsoft Edge 버전 93에서는 [TripleDESEnabled](/deployedge/microsoft-edge-policies#tripledesenabled) 정책을 사용하여 오래된 서버와의 호환성을 유지해야 하는 시나리오를 지원할 수 있습니다. 이 호환성 정책은 사용되지 않으며 Microsoft Edge 버전 95에서 작동이 중지됩니다. 그 전에 영향을 받는 서버를 업데이트해야 합니다.

- **ClickOnce 및 DirectInvoke 프롬프트를 바이패스하는 정책입니다.**  지정된 도메인에서 ClickOnce의 프롬프트와 DirectInvoke의 특정 파일 형식 앱을 바이패스할 수 있도록 정책을 업데이트했습니다. 이렇게 하려면 다음을 수행해야 합니다.

  - [ClickOnceEnabled](/deployedge/microsoft-edge-policies#clickonceenabled)나 [DirectInvokeEnabled](/deployedge/microsoft-edge-policies#directinvokeenabled) 사용
  - [AutoOpenFileTypes](/deployedge/microsoft-edge-policies#autoopenfiletypes) 정책을 사용하고 ClickOnce 및 QAZ를 사용하지 않도록 설정해야 하는 특정 파일 형식 목록 설정
  - [AutoOpenAllowedForURLs](/deployedge/microsoft-edge-policies#autoopenallowedforurls) 정책을 사용하도록 설정하고 ClickOnce 및 DirectInvoke를 사용하지 않도록 설정할 특정 도메인 목록을 설정

  참고: AutoOpenAllowedForURLs는 AutoOpenFileTypes에 대한 금지 정책입니다. AutoOpenAllowedForURLs가 설정되지 않고 AutoOpenFileTypes가 설정된 경우 나열된 파일 형식이 모든 URL에서 자동으로 열립니다.

### <a name="new-policies"></a>새 정책

- [AutoplayAllowlist](/DeployEdge/microsoft-edge-policies#autoplayallowlist) 특정 사이트에서 미디어 자동 재생 허용
- [CECPQ2Enabled](/DeployEdge/microsoft-edge-policies#cecpq2enabled) TLS에서 사용할 수 있는 CECPQ2 양자 내성 키 계약
- [ConfigureViewInFileExplorer](/DeployEdge/microsoft-edge-policies#configureviewinfileexplorer) Microsoft Edge의 SharePoint 페이지에서 파일 탐색기 보기 기능 구성
- [DefaultJavaScriptJitSetting](/DeployEdge/microsoft-edge-policies#defaultjavascriptjitsetting) JavaScript JIT 사용 제어
- [ShowPDFDefaultRecommendationsEnabled](/DeployEdge/microsoft-edge-policies#showpdfdefaultrecommendationsenabled) 알림이 Microsoft Edge를 기본 PDF 판독기로 설정하도록 허용
- [FeatureFlagOverridesControl](/DeployEdge/microsoft-edge-policies#featureflagoverridescontrol) 기능 플래그를 재정의하는 사용자 기능 구성
- [ImplicitSignInEnabled](/DeployEdge/microsoft-edge-policies#implicitsigninenabled) 암시적 로그인 사용
- [InternetExplorerIntegrationCloudSiteList](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationcloudsitelist) 엔터프라이즈 모드 클라우드 사이트 목록 구성
- [InternetExplorerIntegrationSiteListRefreshInterval](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationsitelistrefreshinterval) 엔터프라이즈 모드 사이트 목록을 새로 고치는 빈도 구성
- [JavaScriptJitAllowedForSites](/DeployEdge/microsoft-edge-policies#javascriptjitallowedforsites) JavaScript가 이러한 사이트에서 JIT를 사용하도록 허용
- [JavaScriptJitBlockedForSites](/DeployEdge/microsoft-edge-policies#javascriptjitblockedforsites) JavaScript가 이러한 사이트에서 JIT를 사용하지 못하도록 차단
- [LocalBrowserDataShareEnabled](/DeployEdge/microsoft-edge-policies#localbrowserdatashareenabled) Windows에서 로컬 Microsoft Edge 검색 데이터를 검색할 수 있도록 설정
- [MAUEnabled](/DeployEdge/microsoft-edge-policies#mauenabled) 항상 Microsoft 자동 업데이트를 Microsoft Edge 업데이트 프로그램으로 사용 
- [MSAWebSiteSSOUsingThisProfileAllowed](/DeployEdge/microsoft-edge-policies#msawebsitessousingthisprofileallowed) 이 프로필을 사용하여 Microsoft 사이트에 Single Sign-On 허용
- [OneAuthAuthenticationEnforced](/DeployEdge/microsoft-edge-policies#oneauthauthenticationenforced) 로그인을 위해 적용된 OneAuth 인증 흐름
- [PasswordGeneratorEnabled](/DeployEdge/microsoft-edge-policies#passwordgeneratorenabled) 사용자가 온라인으로 계정을 만들 때마다 강력한 암호 제안을 받을 수 있도록 허용
- [PrimaryPasswordSetting](/DeployEdge/microsoft-edge-policies#primarypasswordsetting) 암호 자동 채우기를 사용하는 동안 사용자에게 디바이스 암호를 입력하도록 요청하는 설정 구성
- [PrintingWebpageLayout](/DeployEdge/microsoft-edge-policies#printingwebpagelayout) 인쇄용 레이아웃 설정
- [RemoteDebuggingAllowed](/DeployEdge/microsoft-edge-policies#remotedebuggingallowed) 원격 디버깅 허용
- [RelaunchWindow](/DeployEdge/microsoft-edge-policies#relaunchwindow) 다시 시작 시간 간격 설정
- [TravelAssistanceEnabled](/DeployEdge/microsoft-edge-policies#travelassistanceenabled) 여행 지원 사용
- [TripleDESEnabled](/DeployEdge/microsoft-edge-policies#tripledesenabled) TLS에서 3DES 암호화 제품군을 사용하도록 설정

#### <a name="deprecated-policy"></a>더 이상 사용되지 않는 정책

- [LegacySameSiteCookieBehaviorEnabled](/DeployEdge/microsoft-edge-policies#legacysamesitecookiebehaviorenabled) 기본 레거시 SameSite 쿠키 동작 설정 사용

#### <a name="obsoleted-policy"></a>폐기된 정책

- [NewTabPageSetFeedType](/DeployEdge/microsoft-edge-policies#newtabpagesetfeedtype) 새 Microsoft Edge 탭 페이지 환경 구성

#### <a name="additional-change"></a>추가 변경 내용

- [ConfigureShare](/DeployEdge/microsoft-edge-policies#configureshare) Mac 플랫폼 지원 추가

## <a name="version-93096118-august-10"></a>버전 93.0.961.18: 8월 10일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-92090262-july-29"></a>버전 92.0.902.62: 7월 29일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-92090255-july-21"></a>버전 92.0.902.55: 7월 21일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-92090245-july-12"></a>버전 92.0.902.45: 7월 12일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-92090240-july-6"></a>버전 92.0.902.40: 7월 6일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-92090222-june-21"></a>버전 92.0.902.22: 6월 21일

### <a name="feature-updates"></a>기능 업데이트

- **주소 표시줄에서 브라우저 기록을 검색하는 자연어입니다.** 이제 주소 표시줄에서 바로 자연어 검색을 통해 원하는 문서/웹 사이트를 더 쉽게 찾을 수 있습니다. 제목/URL 키워드가 일치하기만 하는 것 외에 페이지 콘텐츠/설명/타이밍(예: "지난 주의 조리법")에 따라 검색 결과를 찾을 수 있습니다.
참고: 제어된 기능 롤아웃입니다. 이 기능이 표시되지 않으면 계속 롤아웃하므로 잠시 후에 다시 확인하세요.

- **사용자는 Microsoft Edge에서 Internet Explorer 모드로 쉽게 이동할 수 있습니다**. Microsoft Edge 버전 92부터 사용자는 엔터프라이즈 모드 사이트 목록에서 사이트가 구성될 때까지 기다리는 동안 독립 실행형 IE 11 응용 프로그램을 사용하는 대신 Microsoft Edge Internet Explorer 모드로 사이트를 다시 로드할 수 있습니다. 사용자에게 사이트를 로컬 사이트 목록에 추가하라는 메시지가 표시되므로 Microsoft Edge에서 같은 페이지로 이동하면 다음 30일 동안 IE 모드로 자동으로 렌더링됩니다. *[InternetExplorerIntegrationReloadInIEModeAllowed](/deployedge/microsoft-edge-policies#internetexplorerintegrationreloadiniemodeallowed)* 정책을 사용하여 이 환경을 구성하고 IE 모드 진입점에 대한 액세스와 로컬 사이트 목록에 사이트를 추가하는 기능을 허용할 수 있습니다. *[InternetExplorerIntegrationLocalSiteListExpirationDays](/deployedge/microsoft-edge-policies#internetexplorerintegrationlocalsitelistexpirationdays)* 정책을 사용하여 사이트를 로컬 사이트 목록에 유지할 일수를 조정할 수 있습니다.
Windows 10 버전 1909;에는 KB5003698 이상이 필요합니다. Windows 10, 버전 2004, Windows 10, 버전 20H2 또는 Windows 10 버전 21H1에 종단 간 환경을 사용하려면 KB5003690 이상이 필요합니다.

- **MHTML 파일은 기본적으로 Internet Explorer 모드에서 열립니다**. Microsoft Edge 버전 92 Stable부터 MHTML 파일 형식은 Internet Explorer(IE11) 애플리케이션 대신 Microsoft Edge Internet Explorer 모드로 자동으로 열립니다. 브라우저에서 Outlook 전자 메일을 보는 동안 가장 일반적으로 관찰됩니다. 이 변경은 IE11이 이 파일 형식의 기본 처리기인 경우에만 발생합니다. 이를 변경하려면 [이 지침](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration)을 사용하여 Stable 버전 92 업데이트를 설치하기 전에 이 작업을 수행할 수 있습니다.

- **결제 방법이 이제 장치 간에 동기화됩니다**. Microsoft Edge 버전 92부터 로그인한 장치에서 결제 정보를 동기화할 수 있습니다.
참고: 제어된 기능 롤아웃입니다. 이 기능이 없는 경우 출시를 계속할 때 바로 다시 확인해 봐야 합니다.

- **“개발자 모드 확장을 사용 안 함으로 설정하세요” 경고를 영구적으로 해제할 수 있습니다.** Microsoft Edge 버전 92부터 '다시 표시 안 함' 옵션을 클릭하여 "개발자 모드 확장을 사용 안 함으로 설정하세요" 경고를 끌 수 있습니다.
참고: 제어된 기능 롤아웃입니다. 이 기능이 없는 경우 출시를 계속할 때 바로 다시 확인해 봐야 합니다.

- **도구 모음에서 바로 확장을 관리하세요.** 도구 모음의 새 확장 메뉴를 사용해서 확장을 쉽게 숨기거나 핀으로 고정할 수 있습니다. 확장을 관리하고 새 확장을 찾기 위한 빠른 링크를 사용하면 간편하게 새 확장을 찾고 기존 확장을 관리할 수 있습니다.
참고: 제어된 기능 롤아웃입니다. 이 기능이 없는 경우 출시를 계속할 때 바로 다시 확인해 봐야 합니다.

- **자동 HTTPS**. 사용자는 이 보안 프로토콜을 지원할 가능성이 높은 도메인의 HTTP에서 HTTPS로 탐색을 업그레이드할 수 있습니다. 이 지원은 모든 도메인에 대해 HTTPS를 통해 전달을 시도하도록 구성할 수도 있습니다.
참고: 이 기능을 실험하는 중이며 실험을 옵트아웃한 경우에는 이 동작이 표시되지 않습니다.

- **글꼴 렌더링 개선**. 텍스트 렌더링이 개선되어 선명도를 개선하고 흐릿함을 줄일 수 있습니다.
참고: 제어된 기능 롤아웃입니다. 이 기능이 없는 경우 출시를 계속할 때 바로 다시 확인해 봐야 합니다.

### <a name="policy-updates"></a>정책 업데이트

#### <a name="new-policies"></a>새 정책

새 정책 8개를 추가했습니다. [Microsoft Edge Enterprise 방문 페이지](https://www.microsoft.com/edge/business/download)에서 업데이트된 관리 템플릿을 다운로드할 수 있습니다. 다음과 같은 새 정책이 추가되었습니다.

- [AADWebSiteSSOUsingThisProfileEnabled](/DeployEdge/microsoft-edge-policies#aadwebsitessousingthisprofileenabled) 이 프로필을 사용하도록 설정된 회사 또는 학교 사이트에 대한 Single Sign-On을 사용합니다.
- [AutomaticHttpsDefault](/DeployEdge/microsoft-edge-policies#automatichttpsdefault) 자동 HTTPS 구성
- [HeadlessModeEnabled](/DeployEdge/microsoft-edge-policies#headlessmodeenabled) 비입력 시스템 모드 사용 제어
- [InsecurePrivateNetworkRequestsAllowed](/DeployEdge/microsoft-edge-policies#insecureprivatenetworkrequestsallowed) 안전하지 않은 웹사이트가 더 많은 개인 네트워크 엔드포인트에 요청을 할 수 있도록 허용할지 여부를 지정
- [InsecurePrivateNetworkRequestsAllowedForUrls](/DeployEdge/microsoft-edge-policies#insecureprivatenetworkrequestsallowedforurls) 나열된 사이트가 안전하지 않은 컨텍스트에서 더 많은 개인 네트워크 엔드포인트에 요청을 할 수 있도록 허용
- [InternetExplorerIntegrationLocalSiteListExpirationDays](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationlocalsitelistexpirationdays) 사이트가 로컬 IE 모드 사이트 목록에 남아 있는 일수 지정
- [InternetExplorerIntegrationReloadInIEModeAllowed](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationreloadiniemodeallowed) Internet Explorer 모드에서 구성되지 않은 사이트를 다시 로드할 수 있도록 허용
- [SharedArrayBufferUnrestrictedAccessAllowed](/DeployEdge/microsoft-edge-policies#sharedarraybufferunrestrictedaccessallowed) cross-origin-isolated가 아닌 컨텍스트에서 SharedArrayBuffers를 사용할 수 있는지 여부 지정

#### <a name="obsoleted-policy"></a>폐기된 정책

- [EnableSha1ForLocalAchors](/DeployEdge/microsoft-edge-policies#enablesha1forlocalanchors) 로컬 트러스트 앵커에서 발급한 경우 SHA-1을 사용하여 서명한 인증서 허용합니다.

## <a name="version-9209029-june-8"></a>버전 92.0.902.9: 6월 8일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-91086441-june-3"></a>버전 91.0.864.41: 6월 3일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-91086437-may-27"></a>버전 91.0.864.37: 5월 27일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-91086436-may-26"></a>버전 91.0.864.36: 5월 26일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-91086433-may-21"></a>버전 91.0.864.33: 5월 21일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-91086427-may-14"></a>버전 91.0.864.27: 5월 14일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-91086419-may-7"></a>버전 91.0.864.19: 5월 7일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-91086415-may-3"></a>버전 91.0.864.15: 5월 3일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-91086411-april-30"></a>버전 91.0.864.11: 4월 30일

### <a name="feature-updates"></a>기능 업데이트

- **프록시 수준의 Microsoft Defender Application Guard 컨테이너에서 발생하는 네트워크 트래픽을 식별합니다.** Microsoft Edge 버전 91부터는 Application Guard 컨테이너에서 발생하는 네트워크 트래픽에 태그를 지정하는 지원이 기본적으로 제공되어 기업에서 해당 트래픽을 식별하고 특정 정책을 적용할 수 있습니다.

- **호스트에서 Edge Application Guard 컨테이너의 즐겨찾기 동기화를 허용하는 지원 옵션입니다.** Microsoft Edge 버전 91부터 사용자는 호스트에서 컨테이너로 즐겨찾기를 동기화하도록 Application Guard를 구성할 수 있습니다. 이렇게 하면 새 즐겨찾기도 컨테이너에 표시됩니다.

- **음성 인식 API에 대한 지원** Microsoft Edge 버전 91부터 Google.com 및 유사한 사이트에서 음성 인식 명령에 대한 API 지원이 추가됩니다. 이 기능은 실험을 허락한 임의로 선택된 사용자 그룹으로 제한됩니다. 이러한 사용자는 기능 팀에 피드백을 제공합니다.

- **새 테마 색으로 브라우저를 개인 설정하세요**. 설정 -> 모양 페이지에서 14가지 새로운 테마 색 중 하나를 사용하여 나만의 Microsoft Edge를 만드세요. Microsoft Edge 추가 기능 사이트에서 사용자 지정 테마를 설치할 수도 있습니다. [자세히 알아보기](https://techcommunity.microsoft.com/t5/articles/make-microsoft-edge-your-own-with-themes/m-p/2083165)

- **다운로드 중단** Microsoft Edge 버전 91부터 브라우저는 사용자 상호 작용 없이 다운로드가 시작되고 SmartScreen 응용 프로그램 신뢰도 검사가 지원되지 않는 경우 컴퓨터를 손상시킬 수 있는 유형의 다운로드를 자동으로 중단합니다. 사용자는 다운로드 항목을 마우스 오른쪽 단추로 클릭하고 "유지"를 선택하여 재정의하고 계속 다운로드할 수 있습니다.
엔터프라이즈 관리자는 다음 두 정책 중 하나로 이 동작을 옵트아웃할 수 있습니다.
    - [ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](/deployedge/microsoft-edge-policies#exemptdomainfiletypepairsfromfiletypedownloadwarnings) - 도메인에서 지정된 파일 형식에 대해 파일 형식 확장명 기반 주의 다운로드를 사용설정 해제합니다. 자세한 정보는 [Microsoft Edge 보안 다운로드 중단](/deployedge/microsoft-edge-security-downloads-interruptions)을 참조하세요.

### <a name="policy-updates"></a>정책 업데이트

#### <a name="new-policies"></a>새 정책

6개의 새 정책을 추가했습니다. [Microsoft Edge Enterprise 방문 페이지](https://www.microsoft.com/edge/business/download)에서 업데이트된 관리 템플릿을 다운로드할 수 있습니다. 다음과 같은 새 정책이 추가되었습니다.

- [applicationGuardTrafficIdentificationEnabled](/DeployEdge/microsoft-edge-policies#applicationguardtrafficidentificationenabled) - Application Guard 트래픽 식별
- [ExplicitlyAllowedNetworkPorts](/DeployEdge/microsoft-edge-policies#explicitlyallowednetworkports) - 명시적으로 허용된 네트워크 포트
- [ImportStartupPageSettings](/DeployEdge/microsoft-edge-policies#importstartuppagesettings) - 시작 페이지 설정 가져오기 허용
- [MathSolverEnabled](/DeployEdge/microsoft-edge-policies#mathsolverenabled) - 사용자가 수학 문제를 캡쳐하고 Microsoft Edge에서 단계별 설명을 통해 해결책을 얻을 수 있도록 함
- [NewTabPageContentEnabled](/DeployEdge/microsoft-edge-policies#newtabpagecontentenabled) - 새 탭 페이지에서 Microsoft News 콘텐츠 허용
- [NewTabPageQuickLinksEnabled](/DeployEdge/microsoft-edge-policies#newtabpagequicklinksenabled) - 새 탭 페이지에서 빠른 링크 허용

#### <a name="obsoleted-policy"></a>폐기된 정책

- [ProactiveAuthEnabled](./microsoft-edge-policies.md#proactiveauthenabled) - 사전 인증을 사용하도록 설정합니다.
<!-- end major 91 -->

## <a name="version-90081846-april-22"></a>버전 90.0.818.46: 4월 22일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-90081842-april-20"></a>버전 90.0.818.42: 4월 20일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-90081841-april-16"></a>버전 90.0.818.41: 4월 16일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-90081838-april-14"></a>버전 90.0.818.38: 4월 14일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-90081836-april-12"></a>버전 90.0.818.36: 4월 12일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-90081827-april-2"></a>버전 90.0.818.27: 4월 2일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-90081822-march-29"></a>버전 90.0.818.22: 3월 29일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-90081814-march-22"></a>버전 90.0.818.14: 3월 22일

다양한 버그와 성능 문제를 해결했습니다.
<!-- begin major 90 -->
## <a name="version-9008188-march-16"></a>버전 90.0.818.8: 3월 16일

### <a name="feature-updates"></a>기능 업데이트

- **이제 macOS에서 Azure AD(Azure Active Directory) 계정과 Microsoft MSA(Microsoft 계정)에 SSO(Single Sign On)를 사용할 수 있습니다**. macOS에서 Microsoft Edge에 로그인한 사용자는 회사 및 Microsoft 계정(예: bing.com, office.com, msn.com, outlook.com)으로 Single Sign-On을 허용하도록 구성된 웹 사이트에 자동으로 로그인됩니다.

- **키오스크 모드.** Microsoft Edge 버전 90부터 구성된 프린터 및 "PDF로 인쇄" 옵션만 허용하도록 UI 인쇄 설정을 잠갔습니다. 또한 할당된 액세스 단일 앱 키오스크 모드 내에서 향상된 기능을 수행하여 브라우저에서 다른 애플리케이션의 시작을 제한했습니다. 키오스크 모드 기능에 대한 자세한 내용은 [여기](/deployedge/microsoft-edge-configure-kiosk-mode#kiosk-mode-supported-features)를 참보하세요.

- **인쇄:**

  - ** 포스트스크립트가 아닌 프린터를위한 새로운 인쇄 래스터화 모드 **. Microsoft Edge 버전 90부터 관리자는 새 정책을 사용하여 사용자에 대한 인쇄 래스터화 모드를 정의할 수 있습니다. 이 정책은 Windows에서 포스트스크립트가 아닌 프린터에 대해 Microsoft Edge의 인쇄 방식을 제어합니다.  PostScript가 아닌 프린터에서 인쇄 작업을 올바르게 인쇄하려면 래스터 화해야하는 경우가 있습니다. 인쇄 옵션은 전체 및 고속입니다.

  - ** 인쇄를 위한 추가 페이지 배율 옵션 **. 이제 사용자는 추가 옵션을 사용하여 웹 페이지 및 PDF 문서를 인쇄하는 동안 스케일링을 사용자 지정할 수 있습니다. "페이지에 맞추기" 옵션을 사용하면 웹 페이지나 문서를 인쇄를 위해 선택한 "용지 크기"에서 사용할 수 있는 공간에 맞출 수 있습니다. "실제 크기" 옵션은 선택한 "용지 크기"에 관계없이 인쇄되는 내용의 크기가 변경되지 않도록 합니다.

- **생산력:**

  - ** 자동 완성 제안이 클립 보드의 주소 필드 내용을 포함하도록 확장되었습니다 **. 사용자가 프로필/주소란(예: 전화번호, 전자 메일, 우편 번호, 시, 도)을 클릭할 때 자동 채우기 제안을 표시하기 위해 클립보드 콘텐츠를 분석합니다.

  - ** 사용자는 양식이나 필드가 감지되지 않는 경우에도 자동 완성 제안을 검색할 수 있습니다**. 오늘날 Microsoft Edge에 정보를 저장한 경우 자동 완성 제안이 자동으로 표시되어 양식을 작성하는 동안 시간을 ​​절약할 수 있습니다. 자동 완성이 양식을 놓친 경우 또는 일반적으로 자동 완성이 없는 양식(예: 임시 양식)에서 데이터를 가져오려는 경우 자동 완성을 사용하여 정보를 검색할 수 있습니다.

- ** 메뉴 모음의 플라이 아웃에서 다운로드에 액세스합니다**. 다운로드는 모든 활성 다운로드가 한곳에 있는 오른쪽 상단 모서리에 표시됩니다. 이 메뉴는 쉽게 닫을 수 있으므로 사용자는 중단없이 계속 탐색 할 수 있으며 도구 모음에서 바로 전체 다운로드 진행 상황을 모니터링할 수 있습니다. [자세한 내용을 알아보세요](https://techcommunity.microsoft.com/t5/articles/introducing-the-new-downloads-experience/m-p/2111551).


### <a name="policy-updates"></a>정책 업데이트

#### <a name="new-policies"></a>새로운 정책

새 정책 7개를 추가했습니다. [Microsoft Edge Enterprise 방문 페이지](https://www.microsoft.com/edge/business/download)에서 업데이트된 관리 템플릿을 다운로드할 수 있습니다. 다음과 같은 새 정책이 추가되었습니다.

- [ ApplicationGuardFavoritesSyncEnabled ](./microsoft-edge-policies.md#applicationguardfavoritessyncenabled)-Application Guard 즐겨 찾기 동기화 사용
- [ ManagedConfigurationPerOrigin ](./microsoft-edge-policies.md#managedconfigurationperorigin)-웹 사이트의 관리 구성 값을 특정 원본으로 설정합니다.
- [ PrintRasterizationMode ](./microsoft-edge-policies.md#printrasterizationmode) - 래스터화 모드 인쇄
- [QuickViewOfficeFilesEnabled](./microsoft-edge-policies.md#quickviewofficefilesenabled) - Microsoft Edge에서 QuickView Office 파일 관리
- [SSLErrorOverrideAllowedForOrigins](./microsoft-edge-policies.md#sslerroroverrideallowedfororigins) - 사용자가 특정 출처에 대한 HTTPS 경고 페이지에서 계속할 수 있도록 허용
- [ WindowOcclusionEnabled ](./microsoft-edge-policies.md#windowocclusionenabled)-창 폐색 사용
- [ WindowsHelloForHTTPAuthEnabled ](./microsoft-edge-policies.md#windowshelloforhttpauthenabled)-HTTP 인증용 Windows Hello 사용

#### <a name="deprecated-policies"></a>더 이상 사용되지 않는 정책

- [ NativeWindowOcclusionEnabled ](./microsoft-edge-policies.md#nativewindowocclusionenabled) - 기본 폐색 활성화
- [ SSLVersionMin](./microsoft-edge-policies.md#sslversionmin) - 활성화된 최소 TLS 버전
<!-- end major 90 -->

## <a name="version-89077454-march-13"></a>버전 89.0.774.54: 3월 13일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-89077450-march-10"></a>버전 89.0.774.50: 3월 10일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-89077448-march-8"></a>버전 89.0.774.48: 3월 8일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-89077445-march-3"></a>버전 89.0.774.45: 3월 3일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-89077439-february-26"></a>버전 89.0.774.39: 2월 26일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-89077434-february-22"></a>버전 89.0.774.34: 2월 22일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-89077427-february-12"></a>버전 89.0.774.27: 2월 12일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-89077423-february-8"></a>버전 89.0.774.23: 2월 8일

다양한 버그와 성능 문제를 해결했습니다.

<!-- begin major 89 -->

<!--- Archived from Version 87.0.664.18: October 26 to to version 89.0.774.18: February 3 ---->
<!--- Archived from Version 87.0.664.12: October 20 to to version 86.0.622.15: September 14 ---->
<!--- Archived to version 86.0.622.11: September 9 ---->
<!--- Archived to version 85.0.564.18: July 28 ---->

## <a name="see-also"></a>참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
