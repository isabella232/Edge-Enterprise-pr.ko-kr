---
title: 베타 채널 용 Microsoft Edge 릴리스 정보
ms.author: aguta
author: AndreaLBarr
manager: srugh
ms.date: 08/05/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 베타 채널 용 Microsoft Edge 릴리스 정보
ms.openlocfilehash: bea9c325471617c0ad680b0dabe8cd0d847d5ac0d95941f773471f74ffd0f771
ms.sourcegitcommit: b5093c47bd5e927cde1d486eb71e0ee2483a8bd8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2021
ms.locfileid: "11810472"
---
# <a name="release-notes-for-microsoft-edge-beta-channel"></a>Microsoft Edge 베타 채널에 대한 릴리스 정보

이 릴리스 정보는 Microsoft Edge 베타 채널에 포함된 새로운 기능 및 비보안 업데이트에 대한 정보를 제공합니다. 이 릴리스 정보의 보관된 버전은 [여기](microsoft-edge-relnote-archive-beta-channel.md)에서 볼 수 있습니다.

> [!NOTE]
> Microsoft Edge 웹 플랫폼은 사용자 환경, 보안 및 개인 정보 개선을 위해 지속적으로 진화하고 있습니다. 자세히 알아보려면 [Site compatibility-impacting changes coming to Microsoft Edge](/microsoft-edge/web-platform/site-impacting-changes)(사이트 호환성 - Microsoft Edge에 영향을 미치는 변경 사항)를 참조하세요.

## <a name="version-93096111-august-3"></a>버전 93.0.961.11: 8월 3일

### <a name="feature-updates"></a>기능 업데이트

- **기본 설정의 초기 Microsoft Edge.**  Microsoft Edge 버전 93부터는 초기 Microsoft Edge 추가하여 엔터프라이즈에 배포하는 것이 더 쉬워집니다.

- **IE 모드의 Microsoft Edge "nomerge" 동작을 지원합니다.**  Microsoft Edge 버전 93부터 IE 모드가 Microsoft Edge _를 지원하지 않습니다._ 최종 사용자의 경우 IE 모드 응용 프로그램에서 새 브라우저 창을 시작하면 IE11의 동작과 비슷한 별도의 세션에 있습니다. 세션 공유를 방지해야 하는 사이트를 구성하려면 사이트 목록을 조정해야 합니다. 각 Microsoft Edge 창에 대해 지정된 "nomerge" 사이트 중 하나인 경우 해당 창 내에서 IE 모드 탭을 처음 방문하면 해당 창은 적어도 마지막 IE 모드 탭이 해당 창에서 닫히기 전까지 다른 모든 Microsoft Edge 창에서 다른 "nomerge" IE 세션에 잠겨 있습니다. [여기](/deployedge/edge-ie-mode-faq#does-ie-mode-on-microsoft-edge-support-the--nomerge--option-that-was-supported-in-internet-explorer-11-)에서 자세히 알아보세요.

- **탭 그룹.**  탭을 사용자 정의 그룹으로 분류하는 기능을 사용하면 여러 작업 스트림에서 탭을 보다 효과적으로 찾고 전환하고 관리할 수 있습니다. 이를 위해 버전 93에서 시작하여 탭 Microsoft Edge 켜고 있습니다.

- **세로 탭을 사용하는 동안 제목 표시줄을 숨길 수 있습니다.**  세로 탭에서 브라우저의 제목 표시줄을 숨기면 몇 픽셀의 추가 픽셀을 다시 얻을 수 있습니다. Microsoft Edge 버전 93부터 edge://settings/appearance 도구 모음 사용자 지정 섹션에서 세로 탭 모드에서 제목 표시줄을 숨기는 옵션을 선택합니다.

- **마우스로 끄기 도구 모음의 그림(PiP)에 있는 비디오 그림입니다.**  버전 Microsoft Edge 버전 93부터 PiP(그림) 모드로 전환하기가 훨씬 쉬워집니다. 지원되는 비디오 위에 마우스를 대면 PiP 창에서 해당 비디오를 볼 수 있는 도구 모음이 나타납니다.  참고: 현재 macOS의 Microsoft Edge 사용할 수 있습니다.  사용자에 대한 롤아웃을 계속하는 Windows 다시 확인해보아야 합니다.

- **TLS에서 3DES 제거**  Microsoft Edge 버전 93부터는 TLS_RSA_WITH_3DES_EDE_CBC_SHA 암호 제품군에 대한 지원이 제거됩니다. 이 변경은 Chromium 프로젝트에서 Microsoft Edge 진행됩니다. 자세한 내용은 Chrome 플랫폼 [상태 항목으로 이동합니다.](https://chromestatus.com/feature/6678134168485888) 또한 Microsoft Edge 버전 93에서는 이전 서버와의 호환성을 유지해야 하는 시나리오를 지원하는 [데 TripleDESEnabled](/deployedge/microsoft-edge-policies#tripledesenabled) 정책을 사용할 수 있습니다. 이 호환성 정책은 더 이상 사용되지 않습니다. 버전 95에서는 Microsoft Edge 중지됩니다. 그 전에 영향을 받는 서버를 업데이트해야 합니다.

### <a name="new-policies"></a>새 정책

- [AutoplayAllowlist](/DeployEdge/microsoft-edge-policies#autoplayallowlist) 특정 사이트에서 미디어 자동 재생 허용
- [CECPQ2Enabled](/DeployEdge/microsoft-edge-policies#cecpq2enabled) TLS에 사용할 수 있는 CECPQ2 사후 퀀텀 키 계약
- [ConfigureViewInFileExplorer](/DeployEdge/microsoft-edge-policies#configureviewinfileexplorer) SharePoint 페이지의 파일 탐색기에서 보기 기능 Microsoft Edge
- [DefaultJavaScriptJitSetting](/DeployEdge/microsoft-edge-policies#defaultjavascriptjitsetting) JavaScript JIT 사용 제어
- [ShowPDFDefaultRecommendationsEnabled](/DeployEdge/microsoft-edge-policies#showpdfdefaultrecommendationsenabled) 알림을 기본 PDF Microsoft Edge 설정하도록 허용
- [FeatureFlagOverridesControl](/DeployEdge/microsoft-edge-policies#featureflagoverridescontrol) 기능 플래그를 오버라이드하는 사용자 기능 구성
- [ImplicitSignInEnabled](/DeployEdge/microsoft-edge-policies#implicitsigninenabled) 암시적 로그인 사용
- [InternetExplorerIntegrationCloudSiteList](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationcloudsitelist) Enterprise 모드 클라우드 사이트 목록 구성
- [InternetExplorerIntegrationSiteListRefreshInterval](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationsitelistrefreshinterval) 사이트 목록의 Enterprise 새로 고침되는 자주 구성
- [JavaScriptJitAllowedForSites](/DeployEdge/microsoft-edge-policies#javascriptjitallowedforsites) JavaScript에서 이러한 사이트에서 JIT를 사용할 수 있도록 허용
- [JavaScriptJitBlockedForSites](/DeployEdge/microsoft-edge-policies#javascriptjitblockedforsites) 이러한 사이트에서 JavaScript에서 JIT를 사용하지 차단
- [LocalBrowserDataShareEnabled](/DeployEdge/microsoft-edge-policies#localbrowserdatashareenabled) 로컬 Windows 검색 데이터를 검색할 Microsoft Edge 사용하도록 설정
- [MAUEnabled](/DeployEdge/microsoft-edge-policies#mauenabled) 항상 Microsoft AutoUpdate를 업데이트로 Microsoft Edge
- [MSAWebSiteSSOUsingThisProfileAllowed](/DeployEdge/microsoft-edge-policies#msawebsitessousingthisprofileallowed) 이 프로필을 사용하여 Microsoft 사이트에 Single Sign-On 허용
- [OneAuthAuthenticationEnforced](/DeployEdge/microsoft-edge-policies#oneauthauthenticationenforced) OneAuth 인증 Flow 로그인을 위해 적용
- [PasswordGeneratorEnabled](/DeployEdge/microsoft-edge-policies#passwordgeneratorenabled) 사용자가 온라인으로 계정을 만들 때마다 강력한 암호 제안을 받을 수 있도록 허용
- [PrimaryPasswordSetting](/DeployEdge/microsoft-edge-policies#primarypasswordsetting) 암호 자동 입력을 사용하는 동안 사용자에게 장치 암호를 입력하도록 요청하는 설정을 구성합니다.
- [PrintingWebpageLayout](/DeployEdge/microsoft-edge-policies#printingwebpagelayout) 인쇄용 레이아웃 설정
- [RemoteDebuggingAllowed](/DeployEdge/microsoft-edge-policies#remotedebuggingallowed) 원격 디버깅 허용
- [RelaunchWindow](/DeployEdge/microsoft-edge-policies#relaunchwindow) 다시 시작에 대한 시간 간격 설정
- [TravelAssistanceEnabled](/DeployEdge/microsoft-edge-policies#travelassistanceenabled) 여행 지원 사용
- [TripleDESEnabled](/DeployEdge/microsoft-edge-policies#tripledesenabled) TLS에서 3DES 암호 제품군 사용

#### <a name="deprecated-policy"></a>더 이상 사용되지 않는 정책

- [LegacySameSiteCookieBehaviorEnabled](/DeployEdge/microsoft-edge-policies#legacysamesitecookiebehaviorenabled) 기본 레거시 SameSite 쿠키 동작 설정 사용

#### <a name="obsoleted-policy"></a>폐기된 정책

- [NewTabPageSetFeedType](/DeployEdge/microsoft-edge-policies#newtabpagesetfeedtype) 새 Microsoft Edge 페이지 환경 구성

#### <a name="additional-change"></a>추가 변경

- [ConfigureShare](/DeployEdge/microsoft-edge-policies#configureshare) Mac 플랫폼 지원 추가

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
