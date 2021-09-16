---
title: 안정 채널에 대한 Microsoft Edge 릴리스 정보
ms.author: aguta
author: AndreaLBarr
manager: srugh
ms.date: 09/09/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 안정 채널에 대한 Microsoft Edge 릴리스 정보
ms.openlocfilehash: 4feb2ae1b1d819e4c8c52421bee68bec6c5cb97c
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "11980224"
---
# <a name="release-notes-for-microsoft-edge-stable-channel"></a>Microsoft Edge 안정 채널에 대한 릴리스 정보

이 릴리스 정보는 Microsoft Edge 안정 채널에 포함된 새로운 기능 및 비보안 업데이트에 대한 정보를 제공합니다.

- 모든 보안 업데이트는 [여기](microsoft-edge-relnotes-security.md)에서 확인할 수 있습니다.
- Microsoft Edge 안정 채널에 대한 보관된 릴리스 정보는 [여기](microsoft-edge-relnote-archive-stable-channel.md)에 있습니다.

 Microsoft Edge 채널을 이해하려면 [Microsoft Edge 채널 개요](microsoft-edge-channels.md)를 참조하세요.

> [!NOTE]
> 안정 채널의 업데이트는 하루 이상 점진적으로 배포됩니다. 자세한 내용은 [Microsoft Edge 업데이트 점진적 배포](microsoft-edge-update-progressive-rollout.md)를 참조하세요.
>
> Microsoft Edge 웹 플랫폼은 사용자 환경, 보안 및 개인 정보 개선을 위해 지속적으로 진화하고 있습니다. 자세히 알아보려면 [사이트 호환성-Microsoft Edge로 들어오는 변화에 영향](/microsoft-edge/web-platform/site-impacting-changes)을 참조하세요.

## <a name="version-93096144-september-9"></a>버전 93.0.961.44: 9월 9일

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#september-09-2021)에서 확인할 수 있습니다.

## <a name="version-93096138-september-2"></a>버전 93.0.961.38: 9월 2일

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#september-02-2021)에서 확인할 수 있습니다.

### <a name="feature-updates"></a>기능 업데이트

- **Microsoft Edge 초기 기본 설정입니다.**  Microsoft Edge는 이제 제한된 수의 초기 환경 설정(이전의 마스터 기본 설정)을 지원합니다. IT 관리자는 브라우저가 사용자에 의해 처음으로 실행되기 전에 이러한 설정을 기본값으로 배포할 수 있습니다. 추가 정보는 [첫 번째 실행에 대한 초기 기본 설정을 사용하여 Microsoft Edge 구성](/deployedge/initial-preferences-support-on-microsoft-edge-browser)을 참조하세요.

- **Microsoft Edge의 IE 모드는 "병합 금지" 동작을 지원합니다.**  최종 사용자의 경우, IE 모드 응용프로그램에서 새 브라우저 창이 시작되면 IE11의 병합 금지 동작과 유사하게 별도의 세션에 있게 됩니다. 세션 공유를 금지해야 하는 사이트를 "병합 안 함"으로 구성하려면 사이트 목록을 조정해야 합니다. 이면에서는 Microsoft Edge의 각 창에서 IE 모드 탭이 해당 창 내에 처음 방문하는 경우 지정된 "병합 금지" 사이트 중 하나일 경우 해당 창에서 마지막 IE 모드 탭이 닫힐 때까지 해당 창이 다른 모든 Microsoft Edge 창과 다른 "병합 금지" IE 세션으로 잠깁니다. 이는 사용자가 병합 없이 IE를 시작할 수 있고 다른 메커니즘을 통해 병합 없이 Microsoft Edge를 시작할 수 있었던 이전 동작에 따른 것입니다.  추가 정보는 [IE 모드 문제 해결 및 FAQ | Microsoft Docs](/deployedge/edge-ie-mode-faq#does-ie-mode-on-microsoft-edge-support-the--nomerge--option-that-was-supported-in-internet-explorer-11-)를 참조하세요.

- **암시적 로그인을 중지하는 새 정책입니다.**  시스템 관리자는 [ImplicitSignInEnabled](/deployedge/microsoft-edge-policies#implicitsigninenabled) 정책을 사용하여 Microsoft Edge 브라우저에서 암시적 로그인을 비활성화할 수 있습니다.

- **ClickOnce 및 DirectInvoke 프롬프트를 바이패스하는 정책입니다.** 지정된 도메인에서 ClickOnce의 프롬프트와 DirectInvoke의 특정 파일 형식 앱을 바이패스할 수 있도록 정책을 업데이트했습니다. 이렇게 하려면 다음을 수행해야 합니다.

  - 
            [ClickOnceEnabled](/deployedge/microsoft-edge-policies#clickonceenabled)나 [DirectInvokeEnabled](/deployedge/microsoft-edge-policies#directinvokeenabled) 사용
  - 
            [AutoOpenFileTypes](/deployedge/microsoft-edge-policies#autoopenfiletypes) 정책을 사용하고 ClickOnce 및 QAZ를 사용하지 않도록 설정해야 하는 특정 파일 형식 목록 설정
  - 
            [AutoOpenAllowedForURLs](/deployedge/microsoft-edge-policies#autoopenallowedforurls) 정책을 사용하고 ClickOnce 및 QAZ를 사용하지 않도록 설정해야 하는 특정 도메인 목록 설정

  참고: AutoOpenAllowedForURLs는 AutoOpenFileTypes에 대한 금지 정책입니다. AutoOpenAllowedForURLs가 설정되지 않고 AutoOpenFileTypes가 설정된 경우 나열된 파일 형식이 모든 URL에서 자동으로 열립니다.

- **탭 그룹**  탭을 사용자 정의 그룹으로 분류하고 여러 작업 스트림에서 탭을 보다 효과적으로 찾고 전환하고 관리하는 기능을 제공하는 탭 그룹화를 설정 중입니다.  

- **세로 탭을 사용하는 동안 제목 표시줄을 숨깁니다.**  세로 탭에서 브라우저의 제목 표시줄을 숨겨 몇 개의 픽셀을 다시 가져옵니다. 이제 edge://settings/appearance로 이동하고 사용자 정의 도구 모음 섹션 아래에서 수직 탭 모드에서 제목 표시줄을 숨기는 옵션을 선택할 수 있습니다.

- **호버 도구 모음의 PiP(사진 비디오 사진)입니다.**  지원되는 비디오 위로 마우스를 가져가면 PiP 창에서 해당 비디오를 볼 수 있는 도구 모음이 나타납니다.  참고: 현재 macOS의 Microsoft Edge 사용자가 사용할 수 있습니다.  

- **TLS에서 3DES 제거 TLS_RSA_WITH_3DES_EDE_CBC_SHA 암호화 그룹에 대한 지원이 제거됩니다.** 이 변경은 Microsoft Edge 기반으로 하는 Chromium 프로젝트에서 발생합니다. 자세한 내용은 [크롬 플랫폼 상태 항목](https://chromestatus.com/feature/6678134168485888)으로 이동합니다. 또한 Microsoft Edge 버전 93에서는 [TripleDESEnabled](/deployedge/microsoft-edge-policies#tripledesenabled) 정책을 사용하여 오래된 서버와의 호환성을 유지해야 하는 시나리오를 지원할 수 있습니다. 이 호환성 정책은 사용되지 않으며 Microsoft Edge 버전 95에서 작동이 중지됩니다. 그 전에 영향을 받는 서버를 업데이트해야 합니다.

***새 정책***

- 
            [AutoplayAllowlist](/DeployEdge/microsoft-edge-policies#autoplayallowlist) 특정 사이트에서 미디어 자동 재생 허용
- 
            [CECPQ2Enabled](/DeployEdge/microsoft-edge-policies#cecpq2enabled) TLS에서 사용할 수 있는 CECPQ2 양자 내성 키 계약
- 
            [ConfigureViewInFileExplorer](/DeployEdge/microsoft-edge-policies#configureviewinfileexplorer) Microsoft Edge의 SharePoint 페이지에서 파일 탐색기 보기 기능 구성
- 
            [DefaultJavaScriptJitSetting](/DeployEdge/microsoft-edge-policies#defaultjavascriptjitsetting) JavaScript JIT 사용 제어
- 
            [ShowPDFDefaultRecommendationsEnabled](/DeployEdge/microsoft-edge-policies#showpdfdefaultrecommendationsenabled) 알림이 Microsoft Edge를 기본 PDF 판독기로 설정하도록 허용
- 
            [FeatureFlagOverridesControl](/DeployEdge/microsoft-edge-policies#featureflagoverridescontrol) 기능 플래그를 재정의하는 사용자 기능 구성
- 
            [ImplicitSignInEnabled](/DeployEdge/microsoft-edge-policies#implicitsigninenabled) 암시적 로그인 사용
- 
            [InternetExplorerIntegrationCloudSiteList](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationcloudsitelist) 엔터프라이즈 모드 클라우드 사이트 목록 구성
- 
            [InternetExplorerIntegrationSiteListRefreshInterval](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationsitelistrefreshinterval) 엔터프라이즈 모드 사이트 목록을 새로 고치는 빈도 구성
- 
            [JavaScriptJitAllowedForSites](/DeployEdge/microsoft-edge-policies#javascriptjitallowedforsites) JavaScript가 이러한 사이트에서 JIT를 사용하도록 허용
- 
            [JavaScriptJitBlockedForSites](/DeployEdge/microsoft-edge-policies#javascriptjitblockedforsites) JavaScript가 이러한 사이트에서 JIT를 사용하지 못하도록 차단
- 
            [LocalBrowserDataShareEnabled](/DeployEdge/microsoft-edge-policies#localbrowserdatashareenabled) Windows에서 로컬 Microsoft Edge 검색 데이터를 검색할 수 있도록 설정
- 
            [MAUEnabled](/DeployEdge/microsoft-edge-policies#mauenabled) 항상 Microsoft 자동 업데이트를 Microsoft Edge 업데이트 프로그램으로 사용 
- 
            [MSAWebSiteSSOUsingThisProfileAllowed](/DeployEdge/microsoft-edge-policies#msawebsitessousingthisprofileallowed) 이 프로필을 사용하여 Microsoft 사이트에 Single Sign-On 허용
- 
            [OneAuthAuthenticationEnforced](/DeployEdge/microsoft-edge-policies#oneauthauthenticationenforced) 로그인을 위해 적용된 OneAuth 인증 흐름
- 
            [PasswordGeneratorEnabled](/DeployEdge/microsoft-edge-policies#passwordgeneratorenabled) 사용자가 온라인으로 계정을 만들 때마다 강력한 암호 제안을 받을 수 있도록 허용
- 
            [PrimaryPasswordSetting](/DeployEdge/microsoft-edge-policies#primarypasswordsetting) 암호 자동 채우기를 사용하는 동안 사용자에게 디바이스 암호를 입력하도록 요청하는 설정 구성
- 
            [PrintingWebpageLayout](/DeployEdge/microsoft-edge-policies#printingwebpagelayout) 인쇄용 레이아웃 설정
- 
            [RemoteDebuggingAllowed](/DeployEdge/microsoft-edge-policies#remotedebuggingallowed) 원격 디버깅 허용
- 
            [RelaunchWindow](/DeployEdge/microsoft-edge-policies#relaunchwindow) 다시 시작 시간 간격 설정
- 
            [TravelAssistanceEnabled](/DeployEdge/microsoft-edge-policies#travelassistanceenabled) 여행 지원 사용
- 
            [TripleDESEnabled](/DeployEdge/microsoft-edge-policies#tripledesenabled) TLS에서 3DES 암호화 제품군을 사용하도록 설정
- 
            [WAMAuthBelowWin10RS3Enabled](/DeployEdge/microsoft-edge-policies#wamauthbelowwin10rs3enabled) Windows 10 RS3 이하 운영체제에서 인증 시 WAM을 사용하도록 설정

***더 이상 사용되지 않는 정책***

- 
            [LegacySameSiteCookieBehaviorEnabled](/DeployEdge/microsoft-edge-policies#legacysamesitecookiebehaviorenabled) 기본 레거시 SameSite 쿠키 동작 설정 사용

***폐기된 정책***

- 
            [NewTabPageSetFeedType](/DeployEdge/microsoft-edge-policies#newtabpagesetfeedtype) 새 Microsoft Edge 탭 페이지 환경 구성

***추가 변경 내용***

- 
            [ConfigureShare](/DeployEdge/microsoft-edge-policies#configureshare) Mac 플랫폼 지원 추가
- 
            [PasswordMonitorAllowed](/DeployEdge/microsoft-edge-policies#passwordmonitorallowed) Mac 플랫폼 지원 추가


## <a name="version-92090284-august-26"></a>버전 92.0.902.84: 8월 26일

다양한 버그와 성능을 수정했습니다.

## <a name="version-92090278-august-19"></a>버전 92.0.902.78: 8월 19일

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#august-19-2021)에서 확인할 수 있습니다.

## <a name="version-92090273-august-12"></a>버전 92.0.902.73: 8월 12일

다양한 버그와 성능을 수정했습니다.

## <a name="version-92090267-august-5"></a>버전 92.0.902.67: 8월 5일

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#august-05-2021)에서 확인할 수 있습니다.

## <a name="version-92090262-july-29"></a>버전 92.0.902.62: 7월 29일

다양한 버그와 성능을 수정했습니다.

### <a name="modified-policy"></a>수정된 정책

- AutoplayAllowed – "사용 안함"으로 설정하면 미디어 자동 재생이 "제한"으로 설정됩니다.

## <a name="version-92090255-july-22"></a>버전 92.0.902.55: 7월 22일

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#july-22-2021)에서 확인할 수 있습니다.

### <a name="feature-updates"></a>기능 업데이트


            **사용자는 Microsoft Edge에서 Internet Explorer 모드로 쉽게 이동할 수 있습니다**. Microsoft Edge 버전 92부터 사용자는 엔터프라이즈 모드 사이트 목록에서 사이트가 구성될 때까지 기다리는 동안 독립 실행형 IE 11 응용 프로그램을 사용하는 대신 Microsoft Edge Internet Explorer 모드로 사이트를 다시 로드할 수 있습니다. 사용자에게 사이트를 로컬 사이트 목록에 추가하라는 메시지가 표시되므로 Microsoft Edge에서 같은 페이지로 이동하면 다음 30일 동안 IE 모드로 자동으로 렌더링됩니다. 
            [InternetExplorerIntegrationReloadInIEModeAllowed](/deployedge/microsoft-edge-policies#internetexplorerintegrationreloadiniemodeallowed) 정책을 사용하여 이 환경을 구성하고 IE 모드 진입점에 대한 액세스와 로컬 사이트 목록에 사이트를 추가하는 기능을 허용할 수 있습니다. 
            [InternetExplorerIntegrationLocalSiteListExpirationDays](/deployedge/microsoft-edge-policies#internetexplorerintegrationlocalsitelistexpirationdays) 정책을 사용하여 사이트를 로컬 사이트 목록에 유지할 일수를 조정할 수 있습니다. Windows 10 버전 1909;에는 KB5003698 이상이 필요합니다. Windows 10, 버전 2004, Windows 10, 버전 20H2 또는 Windows 10 버전 21H1에 종단 간 환경을 사용하려면 KB5003690 이상이 필요합니다. 자세한 내용은 [IE 모드의 로컬 사이트 목록](/deployedge/edge-ie-mode-local-site-list)을 참조하세요.


            **MHTML 파일은 기본적으로 Internet Explorer 모드에서 열립니다**. Microsoft Edge 버전 92 Stable부터 MHTML 파일 형식은 Internet Explorer(IE11) 애플리케이션 대신 Microsoft Edge Internet Explorer 모드로 자동으로 열립니다. 브라우저에서 Outlook 전자 메일을 보는 동안 가장 일반적으로 관찰됩니다. 이 변경은 IE11이 이 파일 형식의 기본 처리기인 경우에만 발생합니다. 이를 변경하려면 [이 지침](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration)을 사용하여 Stable 버전 92 업데이트를 설치하기 전에 이 작업을 수행할 수 있습니다.


            **“개발자 모드 확장을 사용 안 함으로 설정하세요” 경고를 2주 동안 해제할 수 있습니다.** 
           Microsoft Edge 버전 92부터 경고 대화 상자 드롭다운에서 옵션을 선택하여 "개발자 모드 확장 비활성화" 경고를 2주 동안 일시 중지할 수 있습니다.


            **도구 모음에서 바로 확장을 관리하세요.** 
           도구 모음의 새 확장 메뉴를 사용해서 확장을 쉽게 숨기거나 핀으로 고정할 수 있습니다. 확장을 관리하고 새 확장을 찾기 위한 빠른 링크를 사용하면 간편하게 새 확장을 찾고 기존 확장을 관리할 수 있습니다.


            **자동 실행의 기본값이 Limit으로 설정됩니다**.  온라인에서 포커스를 유지하기 위해 자동 실행 미디어의 기본값을 허용에서 제한으로 변경했습니다(Microsoft Edge 버전 92부터 시작).


            **결제 방법이 이제 장치 간에 동기화됩니다**. Microsoft Edge 버전 92부터 로그인한 장치에서 결제 정보를 동기화할 수 있습니다. 참고: 제어된 기능 롤아웃입니다. 이 기능이 표시되지 않으면 계속 롤아웃하므로 잠시 후에 다시 확인하세요.
현재 이 기능은 미국에서만 사용할 수 있으며 MSA 사용자(AAD 아님)에만 사용할 수 있습니다.


            **글꼴 렌더링 개선**. 텍스트 렌더링이 개선되어 선명도를 개선하고 흐릿함을 줄일 수 있습니다. 참고: 제어된 기능 롤아웃입니다. 이 기능이 표시되지 않으면 계속 롤아웃하므로 잠시 후에 다시 확인하세요.


            **즐겨찾기 및 모음과 같은 도구 모음 버튼 기능은 창 측면에 고정하기 위해 사용자가 선택한 것을 기억합니다.** 
           이제 기본적으로 활성화되어 사용자가 도구 모음 버튼을 고정하도록 선택하면 고정 해제를 결정할 때까지 항상 고정된 상태로 열립니다.


            **이제 사용자는 그룹 정책을 통해 '이 프로필을 사용하여 직장 또는 학교 사이트에 Single Sign-On 허용' 옵션을 관리할 수 있습니다**.  '이 프로필을 사용하여 직장 또는 학교 사이트에 Single Sign-On 허용'을 사용하면 비 AAD 프로필이 컴퓨터의 직장 또는 학교 자격 증명을 사용하여 직장 또는 학교 사이트에 대해 Single Sign-On을 사용할 수 있습니다. 이 옵션은 비 AAD 프로필에 대해서만 설정 -> 프로필 -> 프로필 기본 설정의 토글로 최종 사용자에게 표시됩니다.  
            [AADWebSiteSSOUsingThisProfileEnabled](/deployedge/microsoft-edge-policies#aadwebsitessousingthisprofileenabled) 정책을 사용하여 동작을 구성할 수 있습니다.  


            **암호 상태** 온라인을 안전하게 유지하려면 여러 계정에서 강력하고 고유한 암호를 사용하는 것이 중요합니다. 그러나 이러한 원리는 말처럼 쉽지 않으며 대부분의 사용자는 추측하기 쉬운 약한 암호를 사용하거나 여러 계정에서 동일한 강력한 암호를 재사용하는 등 잘못된 암호 습관을 보입니다.

이 최신 버전의 Microsoft Edge를 사용하면 강력하고 고유한 암호를 사용하는 작업이 조금 더 쉬워집니다! 이제 Microsoft Edge는 저장된 암호가 충분히 강력한지 여부를 알려주고 여러 사이트에서 암호가 사용되었는지 여부도 표시하여 온라인에서 더 안전한 상태를 유지하는 데 도움이 됩니다. edge://settings/passwords 페이지의 저장된 암호 목록에서 암호 상태 정보를 찾을 수 있습니다.
  

            **저장된 암호에 대한 개인정보 보호 추가** 다른 사람과 공유하는 장치를 사용 중이거나 어떤 이유로든 컴퓨터를 잠금 해제한 상태로 둔 경우 이제 장치 암호를 사용하여 두 번째 확인을 선택하여 다른 사람이 귀하의 웹사이트 암호에 액세스하지 못하도록 할 수 있습니다. 단순합니다!


            **Outlook 확장 프로그램**.  새 브라우저 창을 열지 않고도 Microsoft Outlook 받은 편지함, 일정, 작업 등을 확인하세요.  새 Outlook 확장 프로그램은 [Microsoft Outlook - Microsoft Edge Addons](https://microsoftedge.microsoft.com/addons/detail/microsoft-outlook/kkpalkknhlklpbflpcpkepmmbnmfailf?hl=en-US)에서 다운로드할 수 있습니다.


            **Chromium 오픈 소스 프로젝트에 따라 Microsoft Edge는 웹 페이지에서 테이블을 렌더링하는 방식을 업데이트하고 있습니다.** 
           이 변경 사항은 알려진 문제를 수정하고 Microsoft Edge를 웹/다른 브라우저에서 테이블이 렌더링되는 지정된 방식에 더 가깝게 만듭니다. 예기치 않은 문제에 대해 환경의 중요한 워크플로를 테스트하는 것이 좋습니다. 전체 설명자는 [여기](https://docs.google.com/document/d/16PFD1GtMI9Zgwu0jtPaKZJ75Q2wyZ9EZnVbBacOfiNA/edit)에서 이용할 수 있습니다.

### <a name="new-policies"></a>새 정책

- 
            [AADWebSiteSSOUsingThisProfileEnabled](/DeployEdge/microsoft-edge-policies#aadwebsitessousingthisprofileenabled) 이 프로필을 사용하도록 설정된 회사 또는 학교 사이트에 대한 Single Sign-On을 사용합니다.
- 
            [AutomaticHttpsDefault](/DeployEdge/microsoft-edge-policies#automatichttpsdefault) 자동 HTTPS 구성
- 
            [HeadlessModeEnabled](/DeployEdge/microsoft-edge-policies#headlessmodeenabled) 비입력 시스템 모드 사용 제어
- 
            [InsecurePrivateNetworkRequestsAllowed](/DeployEdge/microsoft-edge-policies#insecureprivatenetworkrequestsallowed) 비보안 웹 사이트에서 비공개 네트워크 엔드포인트에 대한 요청을 수행할 수 있도록 허용할지 여부를 지정합니다.
- 
            [InsecurePrivateNetworkRequestsAllowedForUrls](/DeployEdge/microsoft-edge-policies#insecureprivatenetworkrequestsallowedforurls) 나열된 사이트가 안전하지 않은 컨텍스트에서 더 많은 개인 네트워크 엔드포인트에 요청을 할 수 있도록 허용
- 
            [InternetExplorerIntegrationLocalSiteListExpirationDays](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationlocalsitelistexpirationdays) 사이트가 로컬 IE 모드 사이트 목록에 남아 있는 일수 지정
- 
            [InternetExplorerIntegrationReloadInIEModeAllowed](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationreloadiniemodeallowed) Internet Explorer 모드에서 구성되지 않은 사이트를 다시 로드할 수 있도록 허용
- 
            [SharedArrayBufferUnrestrictedAccessAllowed](/DeployEdge/microsoft-edge-policies#sharedarraybufferunrestrictedaccessallowed) cross-origin-isolated가 아닌 컨텍스트에서 SharedArrayBuffers를 사용할 수 있는지 여부 지정

### <a name="deprecated-policy"></a>더 이상 사용되지 않는 정책

- 
            [InternetExplorerIntegrationTestingAllowed](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationtestingallowed) - Internet Explorer 모드 테스트를 허용합니다.

### <a name="obsoleted-policy"></a>폐기된 정책

- 
            [EnableSha1ForLocalAchors](/DeployEdge/microsoft-edge-policies#enablesha1forlocalanchors) 로컬 트러스트 앵커에서 발급한 경우 SHA-1을 사용하여 서명한 인증서 허용합니다.

## <a name="version-91086471-july-19"></a>버전 91.0.864.71: 7월 19일

> [!Important]
>이 업데이트에는 [CVE-2021-30563](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-30563)가 포함되어 있으며, Chromium 팀은 이 취약점이 악용된 것으로 보고했습니다. 자세한 내용은 [보안 업데이트 가이드](https://msrc.microsoft.com/update-guide/vulnerability/ADV200002)에서 참고하세요.

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#july-19-2021)에서 확인할 수 있습니다.

## <a name="version-91086467-july-8"></a>버전 91.0.864.67: 7월 8일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-91086464-july-2"></a>버전 91.0.864.64: 7월 2일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-91086459-june-24"></a>버전 91.0.864.59: 6월 24일

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#june-24-2021)에서 확인할 수 있습니다.

## <a name="version-91086454-june-18"></a>버전 91.0.864.54: 6월 18일

> [!Important]
> 이 업데이트에는 [CVE-2021-30554](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-30554)가 포함되어 있으며, Chromium 팀은 이 취약점이 악용된 것으로 보고했습니다. 자세한 내용은 [보안 업데이트 가이드](https://msrc.microsoft.com/update-guide/vulnerability/ADV200002)에서 참고하세요.

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#june-18-2021)에서 확인할 수 있습니다.

## <a name="version-91086448-june-11"></a>버전 91.0.864.48: 6월 11일

> [!Important]
>이 업데이트에는 [CVE-2021-30551](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-30551)이 포함되어 있으며 Chromium 팀은 이 취약점이 악용된 것으로 보고했습니다. 자세한 내용은 [보안 업데이트 가이드](https://msrc.microsoft.com/update-guide/vulnerability/ADV200002)에서 참고하세요.

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#june-11-2021)에서 확인할 수 있습니다.

## <a name="version-91086441-june-3"></a>버전 91.0.864.41: 6월 3일

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#june-3-2021)에서 확인할 수 있습니다.

## <a name="version-91086437-may-27"></a>버전 91.0.864.37: 5월 27일

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#may-27-2021)에서 확인할 수 있습니다.

### <a name="feature-updates"></a>기능 업데이트

- 
            **프록시 수준의 Microsoft Defender Application Guard 컨테이너에서 발생하는 네트워크 트래픽을 식별합니다.** 
           Microsoft Edge 버전 91부터는 Application Guard 컨테이너에서 발생하는 네트워크 트래픽에 태그를 지정하는 지원이 기본적으로 제공되어 기업에서 해당 트래픽을 식별하고 특정 정책을 적용할 수 있습니다.

- 
            **호스트에서 Edge Application Guard 컨테이너의 즐겨찾기 동기화를 허용하는 지원 옵션입니다.** 
           Microsoft Edge 버전 91부터 사용자는 호스트에서 컨테이너로 즐겨찾기를 동기화하도록 Application Guard를 구성할 수 있습니다. 이렇게 하면 새 즐겨찾기도 컨테이너에 표시됩니다.

- 
            **Microsoft Edge 버전 91부터 브라우저는 사용자 상호 작용 없이 다운로드가 시작되고 SmartScreen 응용 프로그램 신뢰도 검사가 지원되지 않는 경우 컴퓨터를 손상시킬 수 있는 유형의 다운로드를 자동으로 중단합니다.** 
           사용자는 다운로드 항목을 마우스 오른쪽 단추로 클릭하고 "유지"를 선택하여 재정의하고 계속 다운로드할 수 있습니다. 엔터프라이즈 관리자는 다음 정책을 구성하여 이 동작을 옵트아웃할 수 있습니다.
  - 
            [ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](/deployedge/microsoft-edge-policies#exemptdomainfiletypepairsfromfiletypedownloadwarnings.md) - 도메인에서 지정된 파일 형식에 대해 파일 형식 확장명 기반 주의 다운로드를 사용설정 해제합니다.

    자세한 내용은 [Microsoft Edge 보안 다운로드 중단](microsoft-edge-security-downloads-interruptions.md)을 참조하세요.

- 
            **음성 인식 API에 대한 지원**
           Microsoft Edge 버전 91부터 Google.com 및 유사한 사이트에서 음성 인식 명령에 대한 API 지원이 추가됩니다. 이 기능은 실험을 허락한 임의로 선택된 사용자 그룹으로 제한됩니다. 이러한 사용자는 기능 팀에 피드백을 제공합니다.

- 
            **새 테마 색으로 브라우저를 개인 설정하세요**. 설정 -> 모양 페이지에서 14가지 새로운 테마 색 중 하나를 사용하여 나만의 Microsoft Edge를 만드세요. Microsoft Edge 추가 기능 사이트에서 사용자 지정 테마를 설치할 수도 있습니다. [자세히 알아보기](https://techcommunity.microsoft.com/t5/articles/make-microsoft-edge-your-own-with-themes/m-p/2083165)

### <a name="policy-updates"></a>정책 업데이트

#### <a name="new-policies"></a>새 정책

6개의 새 정책을 추가했습니다. 
            [Microsoft Edge Enterprise 방문 페이지](https://www.microsoft.com/edge/business/download)에서 업데이트된 관리 템플릿을 다운로드할 수 있습니다. 다음과 같은 새 정책이 추가되었습니다.

- 
            [applicationGuardTrafficIdentificationEnabled](/DeployEdge/microsoft-edge-policies#applicationguardtrafficidentificationenabled) - Application Guard 트래픽 식별
- 
            [ExplicitlyAllowedNetworkPorts](/DeployEdge/microsoft-edge-policies#explicitlyallowednetworkports) - 명시적으로 허용된 네트워크 포트
- 
            [ImportStartupPageSettings](/DeployEdge/microsoft-edge-policies#importstartuppagesettings) - 시작 페이지 설정 가져오기 허용
- 
            [MathSolverEnabled](/DeployEdge/microsoft-edge-policies#mathsolverenabled) - 사용자가 수학 문제를 캡쳐하고 Microsoft Edge에서 단계별 설명을 통해 해결책을 얻을 수 있도록 함
- 
            [NewTabPageContentEnabled](/DeployEdge/microsoft-edge-policies#newtabpagecontentenabled) - 새 탭 페이지에서 Microsoft News 콘텐츠 허용
- 
            [NewTabPageQuickLinksEnabled](/DeployEdge/microsoft-edge-policies#newtabpagequicklinksenabled) - 새 탭 페이지에서 빠른 링크 허용

#### <a name="obsoleted-policy"></a>폐기된 정책

- 
            [ProactiveAuthEnabled](./microsoft-edge-policies.md#proactiveauthenabled) - 사전 인증을 사용하도록 설정합니다.
<!-- end major 91 -->

## <a name="version-90081866-may-20"></a>버전 90.0.818.66: 5월 20일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-90081862-may-13"></a>버전 90.0.818.62: 5월 13일

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#may-13-2021)에서 확인할 수 있습니다.

## <a name="version-90081856-may-6"></a>버전 90.0.818.56: 5월 6일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-90081851-april-29"></a>버전 90.0.818.51: 4월 29일

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#april-29-2021)에서 확인할 수 있습니다.

## <a name="version-90081849-april-26"></a>버전 90.0.818.49: 4월 26일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-90081846-april-22"></a>버전 90.0.818.46: 4월 22일 ##

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#april-22-2021)에서 확인할 수 있습니다.

## <a name="version-90081842-april-19"></a>버전 90.0.818.42: 4월 19일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-90081841-april-16"></a>버전 90.0.818.41: 4월 16일 ##

> [!Important]
>이 업데이트에는 [CVE-2021-21224](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21224)가 포함되어 있으며, Chromium 팀은 이 취약점이 악용된 것으로 보고했습니다. 자세한 내용은 [보안 업데이트 가이드](https://msrc.microsoft.com/update-guide)에서 참고하세요.

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#april-16-2021)에서 확인할 수 있습니다.

## <a name="version-90081839-april-15"></a>버전 90.0.818.39: 4월 15일 ##

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#april-15-2021)에서 확인할 수 있습니다.

## <a name="feature-updates"></a>기능 업데이트 ##

-    **이제 macOS에서 Azure AD(Azure Active Directory) 계정과 Microsoft MSA(Microsoft 계정)에 SSO(Single Sign On)를 사용할 수 있습니다.** macOS에서 Microsoft Edge에 로그인한 사용자는 회사 및 Microsoft 계정(예: bing.com, office.com, msn.com, outlook.com)으로 Single Sign-On을 허용하도록 구성된 웹 사이트에 자동으로 로그인됩니다.

- **키오스크 모드.** Microsoft Edge 버전 90부터 구성된 프린터 및 "PDF로 인쇄" 옵션만 허용하도록 UI 인쇄 설정을 잠갔습니다. 또한 할당된 액세스 단일 앱 키오스크 모드 내에서 향상된 기능을 수행하여 브라우저에서 다른 애플리케이션의 시작을 제한했습니다. 키오스크 모드 기능에 대한 자세한 내용은 [여기](/deployedge/microsoft-edge-configure-kiosk-mode#kiosk-mode-supported-features)를 참보하세요.

- 
            **다운로드 중단** Microsoft Edge 버전 91부터 브라우저는 사용자 상호 작용 없이 다운로드가 시작되고 SmartScreen 응용 프로그램 신뢰도 검사가 지원되지 않는 경우 컴퓨터를 손상시킬 수 있는 유형의 다운로드를 자동으로 중단합니다. 사용자는 다운로드 항목을 마우스 오른쪽 단추로 클릭하고 "유지"를 선택하여 재정의하고 계속 다운로드할 수 있습니다.
엔터프라이즈 관리자는 다음 두 정책 중 하나로 이 동작을 옵트아웃할 수 있습니다.
- 
            [ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](/deployedge/microsoft-edge-policies#exemptdomainfiletypepairsfromfiletypedownloadwarnings) - 도메인에서 지정된 파일 형식에 대해 파일 형식 확장명 기반 주의 다운로드를 사용설정 해제합니다. 자세한 정보는 [Microsoft Edge 보안 다운로드 중단](/deployedge/microsoft-edge-security-downloads-interruptions)을 참조하세요.

- 
            **인쇄**:

    - **포스트스크립트가 아닌 프린터를위한 새로운 인쇄 래스터화 모드.** Microsoft Edge 버전 90부터 관리자는 새 정책을 사용하여 사용자에 대한 인쇄 래스터화 모드를 정의할 수 있습니다. 이 정책은 Windows에서 포스트스크립트가 아닌 프린터에 대해 Microsoft Edge의 인쇄 방식을 제어합니다. PostScript가 아닌 프린터에서 인쇄 작업을 올바르게 인쇄하려면 래스터 화해야하는 경우가 있습니다. 인쇄 옵션은 전체 및 고속입니다.
    
  - **인쇄를 위한 추가 페이지 배율 옵션입니다.** 이제 사용자는 추가 옵션을 사용하여 웹 페이지 및 PDF 문서를 인쇄하는 동안 스케일링을 사용자 지정할 수 있습니다. "페이지에 맞추기" 옵션을 사용하면 웹 페이지나 문서를 인쇄를 위해 선택한 "용지 크기"에서 사용할 수 있는 공간에 맞출 수 있습니다. "실제 크기" 옵션은 선택한 "용지 크기"에 관계없이 인쇄되는 내용의 크기가 변경되지 않도록 합니다.

-   **생산력:**

    -   **자동 완성 제안이 클립 보드의 주소 필드 내용을 포함하도록 확장되었습니다.** 사용자가 프로필/주소란(예: 전화번호, 전자 메일, 우편 번호, 시, 도)을 클릭할 때 자동 채우기 제안을 표시하기 위해 클립보드 콘텐츠를 분석합니다.

    -   **사용자는 양식이나 필드가 감지되지 않는 경우에도 자동 완성 제안을 검색할 수 있습니다.** 오늘날 Microsoft Edge에 정보를 저장한 경우 자동 완성 제안이 자동으로 표시되어 양식을 작성하는 동안 시간을 ​​절약할 수 있습니다. 자동 완성이 양식을 놓친 경우 또는 일반적으로 자동 완성이 없는 양식(예: 임시 양식)에서 데이터를 가져오려는 경우 자동 완성을 사용하여 정보를 검색할 수 있습니다.

-   **메뉴 모음의 플라이 아웃에서 다운로드에 액세스합니다.** 다운로드는 모든 활성 다운로드가 한곳에 있는 오른쪽 상단 모서리에 표시됩니다. 이 메뉴는 쉽게 닫을 수 있으므로 사용자는 중단없이 계속 탐색 할 수 있으며 도구 모음에서 바로 전체 다운로드 진행 상황을 모니터링할 수 있습니다. 
            [자세한 내용을 알아보세요](https://techcommunity.microsoft.com/t5/articles/introducing-the-new-downloads-experience/m-p/2111551).

-   **글꼴 렌더링 개선.** Microsoft Edge 버전 90부터 텍스트 렌더링을 개선하여 선명도를 높이고 흐릿함을 줄였습니다. 글꼴 렌더링 개선의 일부는 베타 버전 90에 제공되지만 기본적으로 비활성화되어 있습니다.

- **어린이 모드.** 정책을 사용하도록 설정하면 가족 보호 기능 외에 어린이 모드 기능을 사용하지 않도록 정책을 업데이트했습니다. 키즈 모드에 대한 자세한 내용은 [여기](https://go.microsoft.com/fwlink/?linkid=2146910)를 참조하세요.

## <a name="policy-updates"></a>정책 업데이트

## <a name="new-policies"></a>새 정책

새 정책 8개를 추가했습니다. 
            [Microsoft Edge Enterprise 방문 페이지](https://www.microsoft.com/edge/business/download)에서 업데이트된 관리 템플릿을 다운로드할 수 있습니다. 다음과 같은 새 정책이 추가되었습니다.
-   
            [ ApplicationGuardFavoritesSyncEnabled ](/DeployEdge/microsoft-edge-policies#applicationguardfavoritessyncenabled)-Application Guard 즐겨 찾기 동기화 사용
- 
            [ApplicationGuardTrafficIdentificationEnabled](/DeployEdge/microsoft-edge-policies#applicationguardtrafficidentificationenabled) Application Guard 트래픽 식별
- 
            [ExplicitlyAllowedNetworkPorts](/DeployEdge/microsoft-edge-policies#explicitlyallowednetworkports) 명시적으로 허용된 네트워크 포트
- 
            [ImportStartupPageSettings](/DeployEdge/microsoft-edge-policies#importstartuppagesettings) 시작 페이지 설정 가져오기 허용
- 
            [MathSolverEnabled](/DeployEdge/microsoft-edge-policies#mathsolverenabled) 사용자가 수학 문제를 캡쳐하고 Microsoft Edge에서 단계별 설명을 통해 해결책을 얻을 수 있도록 함
- 
            [NewTabPageContentEnabled](/DeployEdge/microsoft-edge-policies#newtabpagecontentenabled) 새 탭 페이지에서 Microsoft News 콘텐츠 허용
- 
            [NewTabPageQuickLinksEnabled](/DeployEdge/microsoft-edge-policies#newtabpagequicklinksenabled) 새 탭 페이지에서 빠른 링크 허용
-   
            [FetchKeepaliveDurationSecondsOnShutdown](/DeployEdge/microsoft-edge-policies#fetchkeepalivedurationsecondsonshutdown)- 종료 시 유지 기간 가져오기
-   
            [ ManagedConfigurationPerOrigin ](/DeployEdge/microsoft-edge-policies#managedconfigurationperorigin)-웹 사이트의 관리 구성 값을 특정 원본으로 설정합니다.
-   
            [ PrintRasterizationMode ](/DeployEdge/microsoft-edge-policies#printrasterizationmode) - 래스터화 모드 인쇄
-   
            [QuickViewOfficeFilesEnabled](/DeployEdge/microsoft-edge-policies#quickviewofficefilesenabled) - Microsoft Edge에서 QuickView Office 파일 관리
-   
            [SSLErrorOverrideAllowedForOrigins](/DeployEdge/microsoft-edge-policies#sslerroroverrideallowedfororigins) - 사용자가 특정 출처에 대한 HTTPS 경고 페이지에서 계속할 수 있도록 허용
-   
            [ WindowOcclusionEnabled ](/DeployEdge/microsoft-edge-policies#windowocclusionenabled)-창 폐색 사용
-   
            [ WindowsHelloForHTTPAuthEnabled ](/DeployEdge/microsoft-edge-policies#windowshelloforhttpauthenabled)-HTTP 인증용 Windows Hello 사용

## <a name="deprecated-policies"></a>더 이상 사용되지 않는 정책

- 
            [ProactiveAuthEnabled](/DeployEdge/microsoft-edge-policies#proactiveauthenabled) 사전 인증을 사용하도록 설정합니다.
-   
            [ NativeWindowOcclusionEnabled ](/DeployEdge/microsoft-edge-policies#nativewindowocclusionenabled) - 기본 폐색 활성화
-   
            [ SSL버전Min](/DeployEdge/microsoft-edge-policies#sslversionmin) - 활성화된 최소 TLS 버전

## <a name="version-89077477-april-14"></a>버전 89.0.774.77: 4월 14일

> [!Important]
>이 업데이트에는 [CVE-2021-21206](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21206) 및 [CVE-2021-21220](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21220)이 포함되어 있으며 Chromium 팀은 이 취약점이 악용된 것으로 보고했습니다.  자세한 내용은 [보안 업데이트 가이드](https://msrc.microsoft.com/update-guide)에서 참고하세요.

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#april-14-2021)에서 확인할 수 있습니다.

## <a name="version-89077476-april-12"></a>버전 89.0.774.76: 4월 12일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-89077475-april-8"></a>버전 89.0.774.75: 4월 8일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-89077468-april-1"></a>버전 89.0.774.68: 4월 1일

안정 채널 보안 업데이트는 [여기](./microsoft-edge-relnotes-security.md#april-1-2021)에서 확인할 수 있습니다.

## <a name="version-89077463-march-25"></a>버전 89.0.774.63: 3월 25일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-89077457-march-18"></a>버전 89.0.774.57: 3월 18일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-89077454-march-13"></a>버전 89.0.774.54: 3월 13일

> [!IMPORTANT]
> 이 업데이트에는 [CVE-2021-21193](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21193)이 포함되어 있으며 Chromium 팀은 이 취약점이 악용된 것으로 보고했습니다. 자세한 내용은 [보안 업데이트 가이드](https://msrc.microsoft.com/update-guide)를 참조하세요.

안정 채널 보안 업데이트는 [여기](./microsoft-edge-relnotes-security.md#march-13-2021)에서 확인할 수 있습니다.

## <a name="version-89077450-march-10"></a>버전 89.0.774.50: 3월 10일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-89077448-march-8"></a>버전 89.0.774.48: 3월 8일

다양한 버그와 성능 문제를 해결했습니다.

<!-- begin major 89 -->
## <a name="version-89077445-march-4"></a>버전 89.0.774.45: 3월 4일

> [!IMPORTANT]
> 이 업데이트에는 [CVE-2021-21166](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21166)이 포함되어 있으며 Chromium 팀은 이 취약점이 악용된 것으로 보고했습니다. 자세한 내용은 [보안 업데이트 가이드](https://msrc.microsoft.com/update-guide)를 참조하세요.

안정 채널 보안 업데이트는 [여기](./microsoft-edge-relnotes-security.md#march-4-2021)에서 확인할 수 있습니다.

### <a name="resolved-issues"></a>해결된 문제

- **작업 표시줄 및 시작 메뉴 바로 가기 업데이트 및 수정 사항:**
  - 이제 시작 메뉴에서 Microsoft Edge 바로 가기를 마우스 오른쪽 단추로 클릭하면 고정된 경우 작업 표시줄에서 Microsoft Edge를 고정 해제하는 옵션이 제대로 표시됩니다.
  - Microsoft Edge를 작업 표시줄에 고정하는 [작업 표시줄 구성](/windows/configuration/configure-windows-10-taskbar)이 포함된 시작 레이아웃은 두 번째 Microsoft Edge 바로 가기에서 더 이상 작업 표시줄을 고정하지 않습니다.
  - Windows 로밍 프로필을 사용하는 조직에서 사용자가 Windows에 로그온할 때 작업 표시줄의 Microsoft Edge 아이콘 대신 빈 흰색 아이콘이 더 이상 표시되지 않습니다.

### <a name="feature-updates"></a>기능 업데이트

- 
            **키오스크 모드에서는 추가 잠금 기능을 사용할 수 있습니다**. Microsoft Edge 버전 89부터는 고객이 생산성과 보안이 강화된 환경에서 작업을 완료할 수 있도록 키오스크 모드에 추가 잠금 모드가 추가되었습니다. 
            [자세한 내용을 알아보세요](microsoft-edge-configure-kiosk-mode.md#kiosk-mode-supported-features).

- 
            **Enterprise Mode Site List Manager 도구는 *edge://compat* 페이지**를 통해 브라우저에서 사용 가능합니다. 이 도구를 사용하여 Microsoft Edge에서 Internet Explorer 모드에 대한 사이트 목록 XML을 만들고 편집하고 내보낼 수 있습니다. 그룹 정책을 통해 필요한 경우 이 도구에 대한 액세스를 사용하도록 설정할 수 있습니다. 
            [자세한 내용을 알아보세요](./edge-ie-mode-site-list-manager.md).

- 
            **절전 모드 탭을 사용하여 브라우저 성능을 향상합니다**. 절전 모드 탭은 활성 탭이나 다른 응용 프로그램에서 사용할 수 있도록 메모리 및 CPU와 같은 시스템 리소스를 확보하기 위해 비활성 탭을 절전 모드로 전환하여 브라우저 성능을 향상시킵니다. 사용자는 사이트가 절전 모드로 전환되는 것을 방지하고 비활성 탭이 절전 모드로 전환될 때까지의 시간을 구성할 수 있습니다. 사용자를 흐름에서 유지시키기 위해 인트라넷 사이트와 같은 특정 사이트가 절전 모드로 전환되는 것을 방지하는 [추론](https://techcommunity.microsoft.com/t5/articles/sleeping-tabs-faq/m-p/1705434)도 있습니다. 이 기능은 그룹 정책을 통해 관리할 수 있습니다.

- 
            **클라우드에서 Microsoft Edge 동기화 데이터를 수동으로 다시 설정하세요**. 제품 내에서 Microsoft Edge 동기화 데이터를 다시 설정하는 방법이 도입되었습니다. 이 방법을 사용하면 Microsoft 서비스에서 데이터를 확실히 지우고, 이전에는 지원 티켓이 필요했던 특정 제품 문제를 해결할 수 있습니다.

- 
            **모든 Windows Azure Active Directory(Azure AD) 계정에 대해 SSO(Single Sign-On)를 지능적으로 사용하도록 설정하면 Azure AD Microsoft Edge이 아닌 단일 프로필이 있는 사용자에게 적용됩니다.** 
            이 기능에서 가장 많은 혜택을 받을 수 있는 사용자에 대해 이 설정을 자동으로 켜면 됩니다. 사용자가 하나의 Microsoft Edge 프로파일(Azure AD 또는 Kids Mode가 아닌 경우)만 있으면 Microsoft Edge가 실행될 때 설정이 자동으로 설정됩니다. 사용자가 나중에 Azure AD 계정으로 다른 Microsoft Edge 프로필에 로그인하도록 선택하는 경우 이 자동 토글도 자동으로 해제됩니다. 사용자는 **설정 > 프로필 환경설정 > 프로필 환경설정 > 이 프로필을 사용하여 직장 또는 학교 사이트에 대한 단일 로그온 허용**에서 이 기능에 대한 환경설정을 수동으로 업데이트할 수 있습니다.

- 
            **PDF 문서 내의 텍스트 선택 환경이 개선됩니다**. Microsoft Edge 버전 89 이상에서 연 PDF 문서 전반에서 더욱 원활하고 일관성 있는 텍스트 선택 환경이 제공됩니다.

- 
            **이제 자동 채우기에서 생년월일 필드가 지원됩니다.** 
           오늘날 Microsoft Edge는 양식을 작성하거나 계정을 만들 때 주소, 이름, 전화번호 등 데이터를 자동으로 채워 사용자의 시간을 절약하고 수고를 덜어줍니다. Microsoft Edge 버전 89부터는 생년월일도 저장해서 자동 채우기 기능을 사용하실 수 있습니다. 프로필 설정에서 언제든지 이 정보를 보고 편집하고 삭제할 수 있습니다.

### <a name="policy-updates"></a>정책 업데이트

#### <a name="new-policies"></a>새로운 정책

새 정책 7개를 추가했습니다. 
            [Microsoft Edge Enterprise 랜딩 페이지](https://www.microsoft.com/edge/business/download)에서 업데이트된 관리 템플릿을 다운로드합니다. 다음과 같은 새 정책이 추가되었습니다.

- 
            [BrowsingDataLifetime](./microsoft-edge-policies.md#browsingdatalifetime) - 데이터 수명 설정 검색
- 
            [MAMEnabled](./microsoft-edge-policies.md#mamenabled) - 모바일 앱 관리 사용
- 
            [DefinePreferredLanguages](./microsoft-edge-policies.md#definepreferredlanguages) - 사이트에서 언어를 지원하는 경우 웹 사이트에서 표시할 기본 설정 언어의 순서가 정해진 목록 정의
- 
            [ShowRecommendationsEnabled](./microsoft-edge-policies.md#showrecommendationsenabled) - Edge에서 추천 및 홍보 알림 허용
- 
            [PrintingAllowedBackgroundGraphicsModes](./microsoft-edge-policies.md#printingallowedbackgroundgraphicsmodes) - 배경 그래픽 인쇄 모드 제한
- 
            [PrintingBackgroundGraphicsDefault](./microsoft-edge-policies.md#printingbackgroundgraphicsdefault) - 기본 배경 그래픽 인쇄 모드
- 
            [SmartActionsBlockList](./microsoft-edge-policies.md#smartactionsblocklist) - 서비스 목록에 대한 스마트 작업 차단

#### <a name="obsoleted-policies"></a>폐기된 정책

다음 정책은 사용되지 않습니다.

- 
            [ForceLegacyDefaultReferrerPolicy](./microsoft-edge-policies.md#forcelegacydefaultreferrerpolicy) - no-referrer-when-downgrade의 기본 참조자 정책 사용
- 
            [MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled) - 사용 현황 및 크래시 관련 데이터 보고 사용
- 
            [SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices) - Microsoft 서비스를 개선하기 위해 사이트 정보 보내기
<!-- end major 89 -->

<!-- Archive from 86.0.622.43: October 15 to beta 88.0.705.81: February 25  ->
<!-- Archive from 86.0.622.38-october-9 to beta 86.0.62.215-september-14  ->
<!-- Archived to version 84.0.522.40: July 16 -->

## <a name="see-also"></a>참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
