---
title: Microsoft Edge 안정 채널에 대한 보관된 릴리스 정보
ms.author: leahtu
author: leahmsft
manager: srugh
ms.date: 04/28/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge 안정 채널에 대한 보관된 릴리스 정보
ms.openlocfilehash: 9d4efe64eec64e94f5b67c2f4daa317c4752919c
ms.sourcegitcommit: 592f6e40b13e28af588473b2a75c3ae697e5db2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2022
ms.locfileid: "12505441"
---
# <a name="archived-release-notes-for-microsoft-edge-stable-channel"></a>Microsoft Edge 안정 채널에 대한 보관된 릴리스 정보

이 릴리스 정보는 Microsoft Edge 안정 채널에 포함된 새로운 기능 및 비보안 업데이트에 대한 정보를 제공합니다. 모든 보안 업데이트는 [여기](microsoft-edge-relnotes-security.md)에서 확인할 수 있습니다.

## <a name="version-980110843-february-3"></a>버전 98.0.1108.43: 2월 3일

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#february-3-2022)에서 확인할 수 있습니다.

### <a name="feature-updates"></a>기능 업데이트

- **웹에서 보안을 강화하세요.** 이것은 브라우저 보안이 우선하는 Microsoft Edge의 브라우징 모드로, 웹을 탐색할 때 사용자에게 추가 보호 계층을 제공합니다. 관리자는 최종 사용자 데스크톱(Windows, macOS 및 Linux)에 그룹 정책을 적용하여 인-더-야드 익스플로잇(제로 데이라고도 함)으로부터 보호할 수 있습니다. 다음 그룹 정책은 이 탐색 모드를 지원합니다.

  - [EnhanceSecurityMode](/deployedge/microsoft-edge-policies#enhancesecuritymode)
  - [EnhanceSecurityModeBypassListDomains](/deployedge/microsoft-edge-policies#enhancesecuritymodebypasslistdomains)
  - [EnhanceSecurityModeEnforceListDomains](/deployedge/microsoft-edge-policies#enhancesecuritymodeenforcelistdomains)

- **사용자 에이전트 문자열의 향후 3자리 버전 번호.** 버전 100부터 Microsoft Edge는 User-Agent 헤더에 3자리 버전 번호(예: "Edg/**100**")를 보냅니다. Microsoft Edge 97부터 사이트 소유자는 *edge://flags*에서 **#force-major-version-to-100** 실험 플래그를 사용하도록 설정하여 이 예정된 사용자 에이전트 문자열을 테스트하여 해당 User-Agent 구문 분석 논리는 강력하고 예상대로 작동하도록 합니다.

- **WebRTC의 Plan B SDP 의미 체계를 사용하지 않습니다.** 이 변경 내용은 Plan B라고 하는 레거시 SDP(Session Description Protocol) 언어를 더 이상 사용하지 않습니다. 이 SDP 형식은 사양을 준수하고 브라우저 간 호환이 가능한 SDP 형식인 통합 계획으로 대체됩니다. 자세한 내용은 Chrome 플랫폼 상태 항목 [PSA: Plan B는 M96 베타 및 Stable](https://chromestatus.com/feature/5823036655665152) 및 [PSA: Stable and Extended 사용 중지에 플랜 B 실행 평가판 종료 날짜](https://groups.google.com/g/discuss-webrtc/c/gEHrZyYKsfU)를 참조하세요. [RTCPeerConnection 플랜 B SDP 의미 체계 평가판](https://developer.chrome.com/origintrials/#/view_trial/3892235977954951169)을 요청하면 사이트에서 버전 101까지 더 이상 사용되지 않는 API를 계속 사용할 수 있습니다.

- **Microsoft Edge에 오버레이 스크롤바가 추가되었습니다.** 오버레이 기반 디자인으로 스크롤바를 업데이트했습니다. 사용자는 *edge://flags*에서 이 기능을 켤 수 있습니다.

### <a name="policy-updates"></a>정책 업데이트

#### <a name="new-policies"></a>새 정책

- [AddressBarEditingEnabled](/DeployEdge/microsoft-edge-policies#addressbareditingenabled) - 주소 표시줄 편집 구성
- [AllowGamesMenu](/DeployEdge/microsoft-edge-policies#allowgamesmenu) - 사용자가 게임 메뉴에 액세스할 수 있도록 허용
- [EdgeFollowEnabled](/DeployEdge/microsoft-edge-policies#edgefollowenabled) - Microsoft Edge에서 팔로우 서비스 사용하도록 설정
- [EnhanceSecurityMode](/DeployEdge/microsoft-edge-policies#enhancesecuritymode) - Microsoft Edge의 보안 상태 향상
- [EnhanceSecurityModeBypassListDomains](/DeployEdge/microsoft-edge-policies#enhancesecuritymodebypasslistdomains) - 보안 강화 모드가 적용되지 않을 도메인 목록 구성
- [EnhanceSecurityModeEnforceListDomains](/DeployEdge/microsoft-edge-policies#enhancesecuritymodeenforcelistdomains) - 보안 강화 모드가 항상 시행될 도메인 목록 구성
- [InAppSupportEnabled](/DeployEdge/microsoft-edge-policies#inappsupportenabled) - 인앱 지원 사용
- [MicrosoftEdgeInsiderPromotionEnabled](/DeployEdge/microsoft-edge-policies#microsoftedgeinsiderpromotionenabled) - Microsoft Edge 참가자 프로모션 사용
- [PrintStickySettings](/DeployEdge/microsoft-edge-policies#printstickysettings) - 인쇄 미리 보기 고정 설정
- [SandboxExternalProtocolBlocked](/DeployEdge/microsoft-edge-policies#sandboxexternalprotocolblocked) - Microsoft Edge가 샌드박스 처리된 iframe에서 외부 프로토콜 탐색을 차단하도록 허용
- [U2fSecurityKeyApiEnabled](/DeployEdge/microsoft-edge-policies#u2fsecuritykeyapienabled) - 지원 중단된 U2F 보안 키 API 사용 허용

## <a name="version-970107276-january-27"></a>버전 97.0.1072.76: 1월 27일

다양한 버그와 성능 문제를 해결했습니다.

### <a name="feature-updates"></a>기능 업데이트

- **사용자 에이전트 문자열의 향후 3자리 버전 번호.** 버전 100부터 Microsoft Edge는 User-Agent 헤더에 3자리 버전 번호(예: "Edg/**100**")를 보냅니다. Microsoft Edge 97부터 사이트 소유자는 *edge://flags*에서 **#force-major-version-to-100** 실험 플래그를 사용하도록 설정하여 이 예정된 사용자 에이전트 문자열을 테스트하여 해당 User-Agent 구문 분석 논리는 강력하고 예상대로 작동하도록 합니다.

## <a name="version-960105475-january-21"></a>버전 96.0.1054.75: 1월 21일

확장 안정 릴리스에 대한 다양한 버그 및 성능 문제를 해결했습니다.

## <a name="version-970107269-january-20"></a>버전 97.0.1072.69: 1월 20일

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#january-20-2022)에서 확인할 수 있습니다.

## <a name="version-970107262-january-13"></a>버전 97.0.1072.62: 1월 13일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-960105472-january-6"></a>버전 96.0.1054.72: 1월 6일

확장 안정 릴리스에 대한 다양한 버그 및 성능 문제를 해결했습니다.

## <a name="version-970107255-january-6"></a>버전 97.0.1072.55: 1월 6일

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#january-6-2022)에서 확인할 수 있습니다.

### <a name="feature-updates"></a>기능 업데이트

- **여러 회사 또는 학교 계정이 장치에 로그인되어 있는 경우 현재 프로필을 사용하여 웹 사이트에 로그인합니다.** 여러 회사 또는 학교 계정이 장치에 로그인되어 있는 경우 사용자는 웹사이트 방문을 계속하기 위해 계정 선택기에서 계정을 선택하라는 메시지가 표시됩니다. 이 릴리스에서는 Microsoft Edge가 현재 프로필에 로그인한 회사 또는 학교 계정을 사용하여 웹 사이트에 자동으로 로그인하도록 허용하라는 메시지가 표시됩니다. 사용자는 **설정** > **프로필 기본 설정**에서 이 기능을 켜고 끌 수 있습니다.

- **macOS에서 Microsoft 엔드포인트 데이터 손실 방지(DLP)에 대한 지원을 추가합니다.** Microsoft Endpoint DLP 정책 시행은 기본적으로 macOS에서 사용할 수 있습니다.

- **자동 HTTPS.** 사용자는 이 보다 안전한 프로토콜을 지원할 가능성이 있는 도메인에서 HTTP에서 HTTPS로 탐색을 업그레이드할 수 있습니다. 이 지원은 모든 도메인에 대해 HTTPS를 통해 전달을 시도하도록 구성할 수도 있습니다. 참고: 이 기능은 제어된 기능 롤아웃입니다. 이 기능이 표시되지 않으면 롤아웃을 계속할 때 다시 확인하세요.

- **타사 컨텍스트에서 WebSQL을 차단합니다.** 기존 WebSQL 기능의 사용은 타사 프레임에서 차단됩니다. [WebSQLInThirdPartyContextEnabled](/deployedge/microsoft-edge-policies#websqlinthirdpartycontextenabled) 정책은 Microsoft Edge 버전 101까지 옵트아웃 옵션으로 사용할 수 있습니다. 이 변경 내용은 Microsoft Edge가 기반으로 하는 Chromium 프로젝트에서 발생합니다. 자세한 내용은 이 [Chrome 플랫폼 상태](https://chromestatus.com/feature/5684870116278272) 항목을 참조하세요.

- **Microsoft Edge에서의 인용.** 연구를 위해 출처를 인용하는 것은 학생들의 일반적인 요구 사항입니다. 그들은 쉬운 작업이 아닌 많은 연구 참조 및 소스를 관리해야 합니다. 또한 이러한 인용을 APA, MLA 및 Chicago와 같은 적절한 인용 형식으로 번역해야 합니다. 이제 Microsoft Edge에서 미리 보기로 제공되는 이 새로운 "인용" 기능을 통해 학생들은 온라인에서 검색할 때 더 나은 방법으로 인용을 관리하고 생성할 수 있습니다. 컬렉션 또는 **설정 등(Alt-F)** 에서 인용을 켜면 Microsoft Edge는 학생들이 연구에 계속 집중할 수 있도록 나중에 사용할 수 있는 인용을 자동으로 생성합니다. 작업이 완료되면 이러한 인용을 최종 결과물로 쉽게 컴파일할 수 있습니다. 자세한 내용은 [Microsoft Edge에서 인용 미리 보기](https://blogs.windows.com/msedgedev/2021/11/04/preview-citations-feature-edge/)를 참조하세요.

- **제어 흐름 가드(CFG).** Microsoft Edge는 메모리 손상 취약점을 해결하고 간접 호출을 보호하여 보다 세분화된 보호를 지원하기 시작할 것입니다. CFG는 Windows 8 이상에서만 지원됩니다. 자세한 내용은 [제어 흐름 가드](/windows/win32/secbp/control-flow-guard)를 참조하세요.
  
  > [!NOTE]
  > 이것은 진화하는 기술입니다. 지원을 강화하는 데 도움이 되도록 피드백을 공유해 주세요.

### <a name="policy-updates"></a>정책 업데이트

#### <a name="new-policies"></a>새 정책

- [AccessibilityImageLabelsEnabled](/DeployEdge/microsoft-edge-policies#accessibilityimagelabelsenabled) - Microsoft에서 이미지 설명 가져오기 사용
- [CORSNonWildcardRequestHeadersSupport](/DeployEdge/microsoft-edge-policies#corsnonwildcardrequestheaderssupport) - CORS 비 와일드카드 요청 헤더 지원 사용
- [EdgeDiscoverEnabled](/DeployEdge/microsoft-edge-policies#edgediscoverenabled) - Microsoft Edge의 검색 기능
- [EdgeEnhanceImagesEnabled](/DeployEdge/microsoft-edge-policies#edgeenhanceimagesenabled) - 이미지 향상 사용됨
- [InternetExplorerModeTabInEdgeModeAllowed](/DeployEdge/microsoft-edge-policies#internetexplorermodetabinedgemodeallowed) - Internet Explorer 모드로 구성된 사이트가 Microsoft Edge에서 열리도록 허용
- [SameOriginTabCaptureAllowedByOrigins](/DeployEdge/microsoft-edge-policies#sameorigintabcaptureallowedbyorigins) - 이 출처에서 동일한 출처 탭 캡처 허용
- [ScreenCaptureAllowedByOrigins](/DeployEdge/microsoft-edge-policies#screencaptureallowedbyorigins) - 이러한 출처에서 바탕 화면, 창 및 탭 캡처를 허용합니다.
- [SerialAllowAllPortsForUrls](/DeployEdge/microsoft-edge-policies#serialallowallportsforurls) - 모든 직렬 포트를 연결할 수 있는 권한을 사이트에 자동으로 부여합니다.
- [SerialAllowUsbDevicesForUrls](/DeployEdge/microsoft-edge-policies#serialallowusbdevicesforurls) - USB 직렬 장치에 연결할 수 있는 권한을 사이트에 자동으로 부여
- [SmartScreenDnsRequestsEnabled](/DeployEdge/microsoft-edge-policies#smartscreendnsrequestsenabled) - Microsoft Defender SmartScreen DNS 요청 사용
- [TabCaptureAllowedByOrigins](/DeployEdge/microsoft-edge-policies#tabcaptureallowedbyorigins) - 이 출처에 의한 탭 캡처 허용
- [WebSQLInThirdPartyContextEnabled](/DeployEdge/microsoft-edge-policies#websqlinthirdpartycontextenabled) - 타사 컨텍스트의 WebSQL을 강제로 다시 사용하도록 설정
- [WindowCaptureAllowedByOrigins](/DeployEdge/microsoft-edge-policies#windowcaptureallowedbyorigins) - 이러한 출처에서 창 및 탭 캡처 허용

## <a name="version-960105462-december-17"></a>버전 96.0.1054.62: 12월 17일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-960105457-december-14"></a>버전 96.0.1054.57: 12월 14일

> [!Important]
> 이 업데이트에는 Chromium 팀에서 야생에서 악용되는 것으로 보고된 [CVE-2021-4102](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-4102)에 대한 수정 사항이 포함되어 있습니다. 자세한 내용은 [보안 업데이트 가이드](https://msrc.microsoft.com/update-guide)에서 참고하세요.

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#december-14-2021)에서 확인할 수 있습니다.

## <a name="version-960105453-december-10"></a>버전 96.0.1054.53: 12월 10일

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#december-10-2021)에서 확인할 수 있습니다.

## <a name="version-960105443-december-2"></a>버전 96.0.1054.43: 12월 2일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-960105441-november-30"></a>버전 96.0.1054.41: 11월 30일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-960105434-november-23"></a>버전 96.0.1054.34: 11월 23일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-960105429-november-19"></a>버전 96.0.1054.29: 11월 19일

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#november-19-2021)에서 확인할 수 있습니다.

### <a name="feature-updates"></a>기능 업데이트

- **공개 미리 보기의 IE 모드에 대한 클라우드 사이트 목록 관리.** 클라우드 사이트 목록 관리를 사용하면 조직의 사이트 목록을 호스트하는 온-프레미스 인프라 없이도 클라우드에서 IE 모드에 대한 사이트 목록을 관리할 수 있습니다. Microsoft 365 관리 센터의 Microsoft Edge 사이트 목록 환경을 사용하여 클라우드 사이트 목록 관리 기능에 액세스할 수 있습니다. 자세한 내용은 [IE 모드용 클라우드 사이트 목록 관리(공개 미리 보기)](./edge-ie-mode-cloud-site-list-mgmt.md) 문서를 참조하세요.
  
- **IE 모드와 최신 브라우저 간의 핸드오프가 향상되었습니다.** 이 Microsoft Edge 버전부터 Microsoft Edge 및 Internet Explorer 모드 간의 탐색에는 양식 데이터와 추가 HTTP 헤더가 포함됩니다. 참조자 헤더, 게시 데이터, 양식 데이터 및 요청 메서드는 두 환경에서 올바르게 전달됩니다. InternetExplorerIntegrationComplexNavDataTypes 정책을 사용하여 포함할 데이터 형식을 지정할 수 있습니다. 자세한 내용은 이 FAQ를 참조하세요[. 애플리케이션에서 IE 모드와 Microsoft Edge 간에 POST 데이터를 전송해야 합니다. 지원되는가요?](./edge-ie-mode-faq.md#my-application-requires-transferring-post-data-between-ie-mode-and-microsoft-edge-is-this-supported)

- **WSUS를 사용하여 Microsoft Edge WebWiew2를 업데이트합니다.** WSUS(Windows Server Update Services)를 사용하여 Microsoft Edge 업데이트하는 IT 관리자는 WSUS를 사용하여 Microsoft Edge WebView2를 업데이트할 수도 있습니다. 이 기능은 관리자에게 오프라인 디바이스에 대한 보다 쉬운 서비스 프로세스를 제공합니다.

- **서버에 대한 WSUS 업데이트입니다.** 이제 Microsoft Edge 채널(안정, 베타 및 개발)에 대한 WSUS 및 카탈로그 업데이트가 Windows Server 2022를 포함하여 Microsoft Edge 설치된 Windows 서버 SKU에 적용됩니다. Microsoft Edge 대한 WSUS 업데이트를 구성하는 방법에 대한 자세한 내용은 [업데이트 Microsoft Edge](/mem/configmgr/apps/deploy-use/deploy-edge) 참조하세요.

- **Microsoft Edge AutoLaunch 프로토콜 구성 요소입니다.** Microsoft Edge 96에서는 자동으로 허용하거나 차단할 체계 원본 사전 목록이 포함된 AutoLaunch 프로토콜 [구성 요소를](https://textslashplain.com/2019/07/16/updating-browsers-quickly-flags-respins-and-components/) 도입했습니다. 이렇게 하면 알려진 안전한 페어링에서 프롬프트를 제거하면서 위험한 체계(예: 0일 프로토콜 처리기)로부터 고객을 보호합니다(예: Teams 웹 사이트에서 Teams 클라이언트 앱을 열 수 있음). 어떤 이유로든 Microsoft Edge 취약한 프로토콜 처리기를 차단하고 알려진 안전한 페어링을 허용하거나, *edge://settings/content/applicationLinks* 토글을 사용하거나, [AutoLaunchProtocolsComponentEnabled](/deployedge/microsoft-edge-policies#autolaunchprotocolscomponentenabled) 정책을 False로 설정하지 않으려는 경우

- **프로토콜 링크를 통해 직접 프로그레시브 웹앱(PWA)을 시작합니다.** 설치된 PWA가 보다 통합된 환경을 위해 특정 프로토콜을 사용하는 링크를 처리하도록 합니다.

- **브라우저에서 Office 파일을 빠르게 봅니다.** 이제 사용자는 파일을 다운로드한 다음 다른 애플리케이션에서 열 필요 없이 브라우저에서 바로 Microsoft Edge 탐색하는 동안 표시되는 문서, 스프레드시트 및 프레젠테이션을 포함한 Office 파일을 볼 수 있습니다. OneDrive 또는 SharePoint 호스트되는 Office 파일에 대한 파일 열기 환경은 변경되지 않습니다.
  
- **PDF에서 자유형 강조 표시** 자유형 형광펜을 추가하여 PDF 보기 및 태그 환경이 개선되었습니다. 액세스 권한이 없는 PDF의 섹션과 스캔한 문서를 강조 표시할 수 있습니다.

- **하드웨어 적용 스택 보호** Microsoft Edge 지원되는 하드웨어(Intel 11세대)의 브라우저 프로세스에 하드웨어 종속 제어 흐름을 사용하는 더욱 안전한 검색 모드를 지원하기 시작합니다. 또는 AMD Zen 3). 참고: 이 기능은 제어된 기능 롤아웃이므로 이 기능이 모든 디바이스에서 사용하도록 설정된 것을 알 수 없습니다. 그룹 정책을 사용하여 IFEO(이미지 파일 실행 옵션)를 조작하여 하드웨어 적용 스택 보호를 사용하거나 사용하지 않도록 설정할 수 있습니다.

- **오타적 사이트에 대한 새 경고 대화 상자입니다.** 브라우저는 다른 사이트와 매우 유사한 URL이 있는 일부 사이트에 경고를 표시합니다. 이 UI는 클라이언트 쪽 추론을 사용하여 인기 있는 웹 사이트를 스푸핑할 수 있는 사이트에 대해 사용자에게 경고합니다. 자세한 내용은 [오타 쿼팅이란?을 참조하세요](https://support.microsoft.com/topic/what-is-typosquatting-54a18872-8459-4d47-b3e3-d84d9a362eb0).
  
- **몰입형 리더 미니 도구 모음에 추가된 사전입니다.**  읽기 및 연구를 지원하기 위해 미니 도구 모음에 사전 기능을 추가하고 있습니다. 몰입형 리더 환경에서 단어의 맞춤법 및 정의를 더 빠르고 쉽게 조회할 수 있습니다.
  
- **수학 해 찾기를 사용하여 수학 문제를 해결하는 방법을 알아봅니다.** Microsoft Edge 수학 해 찾기를 사용하여 다양한 수학 개념에 대한 도움을 받을 수 있다는 것을 발표하게 되어 기쁩니다. 이러한 개념은 기본 산술 및 이차 방정식에서 삼각 및 미적분에 이르기까지 다양합니다. 수학 해 찾기를 사용하면 필기 또는 인쇄된 수학 문제의 사진을 찍은 다음, 도움 없이 솔루션에 도달하는 방법을 배울 수 있도록 단계별 지침이 포함된 즉각적인 솔루션을 제공합니다. 수학 해 찾기는 수학 문제를 쉽게 입력하는 데 사용할 수있는 수학 키보드와 함께 제공됩니다. 이 키보드를 사용하면 기존 키보드를 검색하여 필요한 수학 문자를 찾을 필요가 없습니다. 문제를 해결한 후 Math Solver는 퀴즈, 워크시트 및 비디오 자습서를 사용하여 학습을 계속하는 옵션을 제공합니다.

- **WebRTC에 대한 분할 터널 VPN 지원** 엔터프라이즈 고객은 Microsoft Edge 피어 투 피어 트래픽에 대한 VPN 분할 터널링의 이점을 얻을 수 있습니다. [WebRtcRespectOsRoutingTableEnabled](/deployedge/microsoft-edge-policies#webrtcrespectosroutingtableenabled) 정책을 사용하여 이 기능을 사용하도록 설정할 수 있습니다.

### <a name="policy-updates"></a>정책 업데이트

#### <a name="new-policies"></a>새 정책

- [ApplicationGuardUploadBlockingEnabled](/DeployEdge/microsoft-edge-policies#applicationguarduploadblockingenabled) - Application Guard에 있는 동안 파일이 업로드되지 않도록 방지
- [AudioProcessHighPriorityEnabled](/DeployEdge/microsoft-edge-policies#audioprocesshighpriorityenabled) - 오디오 프로세스가 Windows 정상보다 우선 순위로 실행되도록 허용
- [AutoLaunchProtocolsComponentEnabled](/DeployEdge/microsoft-edge-policies#autolaunchprotocolscomponentenabled) - AutoLaunch 프로토콜 구성 요소 사용
- [EfficiencyMode](/DeployEdge/microsoft-edge-policies#efficiencymode) - 효율성 모드가 활성화되어야 하는 경우 구성
- [ForceSyncTypes](/DeployEdge/microsoft-edge-policies#forcesynctypes) - 동기화에 포함된 형식 목록 구성
- [InternetExplorerIntegrationComplexNavDataTypes](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationcomplexnavdatatypes) - Internet Explorer 모드를 입력하거나 종료할 때 양식 데이터 및 HTTP 헤더를 보낼지 여부를 구성합니다.
- [InternetExplorerModeToolbarButtonEnabled](/DeployEdge/microsoft-edge-policies#internetexplorermodetoolbarbuttonenabled) - 도구 모음에서 Internet Explorer 모드로 다시 로드 단추 표시
- [PrintPostScriptMode](/DeployEdge/microsoft-edge-policies#printpostscriptmode) - 인쇄 포스트스크립트 모드
- [PrintRasterizePdfDpi](/DeployEdge/microsoft-edge-policies#printrasterizepdfdpi) - 인쇄 래스터화 PDF DPI
- [RendererAppContainerEnabled](/DeployEdge/microsoft-edge-policies#rendererappcontainerenabled) - 앱 컨테이너에서 렌더러 사용
- [SharedLinksEnabled](/DeployEdge/microsoft-edge-policies#sharedlinksenabled) - 기록에서 Microsoft 365 앱에서 공유된 링크 표시
- [TyposquattingCheckerEnabled](/DeployEdge/microsoft-edge-policies#typosquattingcheckerenabled) - Edge TyposquattingChecker 구성

## <a name="version-950102053-november-12"></a>버전 95.0.1020.53: 11월 12일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-950102044-november-4"></a>버전 95.0.1020.44: 11월 4일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-94099258-october-30"></a>버전 94.0.992.58: 10월 30일

확장 안정 릴리스에 대한 다양한 버그 및 성능 문제를 해결했습니다.

## <a name="version-950102040-october-29"></a>버전 95.0.1020.40: 10월 29일

> [!IMPORTANT]
> 이 업데이트에는 Chromium 팀에서 악용이 있는 것으로 보고한 [CVE-2021-38000](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-38000) 및 [CVE-2021-38003](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-38003)에 대한 수정이 포함되어 있습니다. 자세한 내용은 [보안 업데이트 가이드](https://msrc.microsoft.com/update-guide)를 참고하세요.

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#october-29-2021)에서 확인할 수 있습니다.

## <a name="version-950102038-october-28"></a>버전 95.0.1020.38: 10월 28일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-94099257-october-27"></a>버전 94.0.992.57: 10월 27일

확장 안정 릴리스에 대한 다양한 버그 및 성능 문제를 해결했습니다.

## <a name="version-950102030-october-21"></a>버전 95.0.1020.30: 10월 21일

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#october-21-2021)에서 확인할 수 있습니다.

### <a name="feature-updates"></a>기능 업데이트

- **Microsoft Edge SharePoint Online 라이브러리 파일 탐색기 지원에서 보기**  이제 SharePoint Online 최신 문서 라이브러리에서 파일 탐색기 보기 기능을 사용하도록 설정할 수 있습니다. 이 환경을 사용자에게 표시하고 작동하려면 Microsoft Edge 정책 중에[Microsoft Edge에서 SharePoint 페이지 File Explorere 기능에서 보기 구성](/deployedge/microsoft-edge-policies#configureviewinfileexplorer) 및 SharePoint Online 테넌트 구성을 사용하도록 설정합니다. 자세한 정보: [Microsoft Edge 파일 탐색기 있는 SharePoint 파일을 봅니다.](/SharePoint/sharepoint-view-in-edge)

- **인트라넷 영역 파일 URL 링크는 Windows 파일 탐색기에서 열립니다.**  인트라넷 영역 HTTPS 웹 사이트에서 시작된 인트라넷 영역 파일에 대한 파일 URL 링크를 허용하여 해당 파일 또는 디렉터리에 대한 Windows 파일 탐색기를 열 수 있습니다. [IntranetFileLinksEnabled](/deployedge/microsoft-edge-policies#intranetfilelinksenabled) 정책을 사용하여 이 환경을 사용하도록 설정할 수 있습니다.

- **다운로드 환경 개선** 다운로드 사용자 환경에 대한 지원은 점진적 웹 애플리케이션 PWA 및 WebView로 확장됩니다. 또한 파일 탐색기 데스크톱으로 끌어서 놓기를 지원합니다.

- **PDF 문서에서 중단한 위치에서부터 시작합니다.**  이제 PDF 문서를 마지막으로 닫은 위치에서 읽기를 다시 시작할 수 있습니다.

- **효율성 모드는 노트북이 배터리 절약 모드 모드로 전환되면 배터리 사용 시간을 연장합니다.**  노트북이 배터리 절약 모드 모드로 전환되면 효율성 모드가 활성화 되어 브라우저에서 리소스 사용량을 관리하여 컴퓨터의 배터리 사용 시간을 연장할 수 있습니다. 효율성 모드가 활성화 되면 선택 가능한 4가지 옵션: 분리 및 배터리 부족, 분리, 항상 및 안 함.  참고: 이 기능은 제어된 기능 롤아웃입니다. 이 기능이 표시되지 않으면 롤아웃 완료 이후 다시 확인하세요.

- **PDF 문서에 자유 형식 텍스트 상자가 추가되었습니다.** 이제 PDF 문서에 자유 형식 텍스트 상자를 추가할 수 있습니다. 이러한 상자를 사용하여 양식을 작성하고 표시되는 메모를 추가할 수 있습니다.

- **컬렉션에 인용 지원이 추가되었습니다.**  특히 학생과 연구원을 위한 컬렉션 환경을 개선했습니다. 컬렉션은 인용 및 읽기 목록 지원을 시작할 예정입니다.

- **클릭 횟수 감소로 암호를 더 빠르게 업데이트하세요.** 이제 브라우저에서 지정된 웹 사이트의 암호 변경 페이지로 직접 이동할 수 있습니다. 이 작업을 수행하면 페이지를 수동으로 탐색할 필요가 없어 시간과 클릭 횟수가 절약됩니다. 이 페이지에서 브라우저는 기존 암호를 자동으로 채우고 강력하고 고유한 새 암호를 제안합니다.  참고: 현재 이 기능은 제한된 수의 사이트에서만 사용할 수 있습니다.

- **자동 계정 만들기.** 이제 한 번의 클릭으로 온라인 계정을 만들 수 있도록 하여 등록 페이지에 대한 추가 지원을 제공합니다. 등록 양식에서 양식 필드를 클릭할 때 제안 드롭다운을 선택하여 이 작업을 수행할 수 있습니다. 이렇게 하면 등록 양식과 관련된 정보뿐만 아니라 강력한 새 암호 제안도 표시됩니다. 선택하면 모든 관련 정보가 해당 필드에 채워지고 제안된 암호는 웹 사이트 제출 시 자동으로 저장됩니다. 참고: 현재 이 기능은 제한된 수의 사이트에서만 사용할 수 있습니다.

### <a name="policy-updates"></a>정책 업데이트

#### <a name="new-policies"></a>새 정책

- [BrowserLegacyExtensionPointsBlockingEnabled](/DeployEdge/microsoft-edge-policies#browserlegacyextensionpointsblockingenabled) 브라우저 레거시 확장 지점 차단 사용 허용
- [CrossOriginWebAssemblyModuleSharingEnabled](/DeployEdge/microsoft-edge-policies#crossoriginwebassemblymodulesharingenabled) WebAssembly 모듈을 원본 간으로 보낼 수 있는지 여부를 지정합니다.
- [DisplayCapturePermissionsPolicyEnabled](/DeployEdge/microsoft-edge-policies#displaycapturepermissionspolicyenabled) 표시-캡처 권한-정책을 선택하거나 건너뛰는지 여부를 지정합니다.
- [InternetExplorerIntegrationWindowOpenHeightAdjustment](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationwindowopenheightadjustment) IE 모드 페이지와 Edge 모드 페이지에서 가져온 window.open 높이 간의 픽셀 조정 구성
- [InternetExplorerIntegrationWindowOpenWidthAdjustment](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationwindowopenwidthadjustment) IE 모드 페이지와 Edge 모드 페이지에서 가져온 window.open 너비 간의 픽셀 조정 구성
- [IntranetFileLinksEnabled](/DeployEdge/microsoft-edge-policies#intranetfilelinksenabled) Microsoft Edge 인트라넷 영역 파일 URL 링크가 Windows 파일 탐색기에서 열리도록 허용
- [NewSmartScreenLibraryEnabled](/DeployEdge/microsoft-edge-policies#newsmartscreenlibraryenabled) 새 SmartScreen 라이브러리 사용허용
- [ShadowStackCrashRollbackBehavior](/DeployEdge/microsoft-edge-policies#shadowstackcrashrollbackbehavior) ShadowStack 크래시 롤백 동작 구성
- [VisualSearchEnabled](/DeployEdge/microsoft-edge-policies#visualsearchenabled) 시각적 검색 사용

#### <a name="obsoleted-policies"></a>폐기된 정책

- [InternetExplorerIntegrationTestingAllowed](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationtestingallowed) - Internet Explorer 모드 테스트를 허용합니다.
- [LegacySameSiteCookieBehaviorEnabled](/DeployEdge/microsoft-edge-policies#legacysamesitecookiebehaviorenabled) 기본 레거시 SameSite 쿠키 동작 설정 사용

## <a name="version-94099250-october-14"></a>버전 94.0.992.50: 10월 14일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-94099247-october-11"></a>버전 94.0.992.47: 10월 11일

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#october-11-2021)에서 확인할 수 있습니다.

## <a name="version-94099238-october-1"></a>버전 94.0.992.38: 10월 1일

> [!Important]
> 이 업데이트에는 Chromium 팀이 악용된 것으로 보고한 [CVE-2021-37975](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-37975)과 [CVE-2021-37976](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-37976)에 대한 수정 사항이 포함되어 있습니다. 자세한 내용은 [보안 업데이트 가이드](https://msrc.microsoft.com/update-guide)를 참고하세요.

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#october-01-2021)에서 확인할 수 있습니다.

## <a name="version-94099237-september-30"></a>버전 94.0.992.37: 9월 30일

다양한 버그와 성능을 수정했습니다.

## <a name="version-94099231-september-24"></a>버전 94.0.992.31: 9월 24일

> [!Important]
> 이 업데이트에는 Chromium 팀이 악용된 것으로 보고한 [CVE-2021-37973](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-37973)에 대한 수정 사항이 포함되어 있습니다. 자세한 내용은 [보안 업데이트 가이드](https://msrc.microsoft.com/update-guide)를 참고하세요.

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#september-24-2021)에서 확인할 수 있습니다.

### <a name="feature-updates"></a>기능 업데이트

- **Microsoft Edge 업데이트에 대한 4주 주기로의 전환을 완료했습니다.**  주 버전에 대해 새로운 4주 릴리스 주기를 채택했습니다. 자세한 내용은 https://blogs.windows.com/msedgedev/2021/03/12/new-release-cycles-microsoft-edge-extended-stable/을(를) 참조하세요.

- **새로운 확장 안정 옵션이 제공됩니다.**  Microsoft는 관리되는 엔터프라이즈 고객에게 새로운 확장 안정 옵션을 제공하고 있습니다. 확장 안정 옵션은 짝수 버전으로 유지되며 8주마다 업데이트됩니다. 격주로 보안 업데이트가 있을 예정입니다.  추가 정보: https://blogs.windows.com/msedgedev/2021/07/15/opt-in-extended-stable-release-cycle/

- **MHTML 파일을 여는 기본 동작이 개선되었습니다.**  MHTML 파일이 Microsoft Edge에서 저장되지 않은 경우(Microsoft Edge에서 다른 이름으로 저장 또는 다른 이름으로 페이지 저장 옵션 사용) IE 모드가 활성화된 경우 MHTML 파일은 IE 모드에서 계속 열립니다. 파일이 Microsoft Edge에서 저장되었다면 이제 Microsoft Edge에서 열립니다.  이 변경 사항은 Microsoft Edge에서 저장할 때 IE 모드에서 MHTML 파일을 열 때 관찰된 렌더링 문제를 수정합니다.

- **컨텍스트를 보호하기 위해 사설 네트워크 요청을 제한합니다.** 인터넷 페이지에서 로컬(인트라넷) 네트워크의 리소스에 액세스하려면 해당 페이지가 HTTPS를 통해 전달되어야 합니다. 이 변경은 Microsoft Edge 기반으로 하는 Chromium 프로젝트에서 발생합니다. 자세한 내용은 [크롬 플랫폼 상태 항목](https://chromestatus.com/feature/5436853517811712)으로 이동합니다. 비보안 페이지와의 호환성을 유지해야 하는 시나리오를 지원하기 위해 [InsecurePrivateNetworkRequestAllowed](/deployedge/microsoft-edge-policies#insecureprivatenetworkrequestsallowed) 및 [InsecurePrivateNetworkRequestAllowedForUrls](/deployedge/microsoft-edge-policies#insecureprivatenetworkrequestsallowedforurls)의 두 가지 호환성 정책을 사용할 수 있습니다.

- **혼합 콘텐츠 다운로드를 차단합니다.** 보안 페이지는 다른 보안 페이지에서 호스팅되는 파일만 다운로드하고 비보안(비 HTTPS) 페이지에서 호스팅되는 다운로드는 보안 페이지에서 시작하면 차단됩니다. 이 변경은 Microsoft Edge 기반으로 하는 Chromium 프로젝트에서 발생합니다. 자세한 내용은 [Google 보안 블로그 항목](https://security.googleblog.com/2020/02/protecting-users-from-insecure_6.html)으로 이동하세요.

- **온-프레미스 계정에 대한 암시적 로그인을 활성화합니다.** [OnlyOnPremisesImplicitSigninEnabled](/deployedge/microsoft-edge-policies#onlyonpremisesimplicitsigninenabled) 정책을 활성화하면 암시적 로그인에 대해 온-프레미스 계정만 활성화됩니다.  Microsoft Edge는 MSA 또는 AAD 계정에 암시적으로 로그인을 시도하지 않습니다. 온-프레미스 계정에서 AAD 계정으로의 업그레이드도 중지됩니다.

- **새 접근성 설정 페이지입니다.**  접근성 관련 설정을 한 페이지에 모았습니다. 기본 설정 목록에서 새로운 edge://settings/accessibility 페이지를 찾을 수 있습니다. 여기에서 웹 페이지를 더 크게 만들고 초점 영역 주위에 높은 가시성 개요를 표시하는 설정 및 웹 탐색 환경을 개선하는 데 도움이 될 수 있는 기타 설정을 찾을 수 있습니다. Microsoft Edge의 향후 버전에서 여기에 새로운 설정을 계속 추가할 예정입니다.

***새로운 정책***

- [ApplicationGuardPassiveModeEnabled](/DeployEdge/microsoft-edge-policies#applicationguardpassivemodeenabled) Application Guard 사이트 목록 구성을 무시하고 Edge를 정상적으로 탐색합니다.
- [OnPremisesImplicitSigninEnabled](/DeployEdge/microsoft-edge-policies#onlyonpremisesimplicitsigninenabled) 암시적 로그인에 대해 사용하도록 설정된 온-프레미스 계정만
- [WebRtcRespectOsRoutingTableEnabled](/DeployEdge/microsoft-edge-policies#webrtcrespectosroutingtableenabled) WebRTC를 통해 피어 투 피어 연결을 만들 때 Windows OS 라우팅 테이블 규칙 지원 활성화

***폐기된 정책***

- [UserAgentClientHintsEnabled](/DeployEdge/microsoft-edge-policies#useragentclienthintsenabled) 사용자 에이전트 클라이언트 힌트 기능 사용

## <a name="version-93096152-september-16"></a>버전 93.0.961.52: 9월 16일

>[!Important]
>이 업데이트에는 Chromium 팀이 악용된 것으로 보고한 [CVE-2021-30633](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-30632)에 대한 수정 사항이 포함되어 있습니다. 자세한 내용은 [보안 업데이트 가이드](https://msrc.microsoft.com/update-guide)를 참고하세요.

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#september-16-2021)에서 확인할 수 있습니다.

## <a name="version-93096147-september-11"></a>버전 93.0.961.47: 9월 11일

> [!Important]
> 이 업데이트에는 Chromium 팀이 악용된 것으로 보고한 [CVE-2021-30632](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-30632)에 대한 수정 사항이 포함되어 있습니다. 자세한 내용은 [보안 업데이트 가이드](https://msrc.microsoft.com/update-guide)를 참조하세요.

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#september-11-2021)에서 확인할 수 있습니다.

## <a name="version-93096144-september-9"></a>버전 93.0.961.44: 9월 9일

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#september-09-2021)에서 확인할 수 있습니다.

## <a name="version-93096138-september-2"></a>버전 93.0.961.38: 9월 2일

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#september-02-2021)에서 확인할 수 있습니다.

### <a name="feature-updates"></a>기능 업데이트

- **Microsoft Edge 초기 기본 설정입니다.**  Microsoft Edge는 이제 제한된 수의 초기 환경 설정(이전의 마스터 기본 설정)을 지원합니다. IT 관리자는 브라우저가 사용자에 의해 처음으로 실행되기 전에 이러한 설정을 기본값으로 배포할 수 있습니다. 추가 정보는 [첫 번째 실행에 대한 초기 기본 설정을 사용하여 Microsoft Edge 구성](/deployedge/initial-preferences-support-on-microsoft-edge-browser)을 참조하세요.

- **Microsoft Edge의 IE 모드는 "병합 금지" 동작을 지원합니다.**  최종 사용자의 경우, IE 모드 응용프로그램에서 새 브라우저 창이 시작되면 IE11의 병합 금지 동작과 유사하게 별도의 세션에 있게 됩니다. 세션 공유를 금지해야 하는 사이트를 "병합 안 함"으로 구성하려면 사이트 목록을 조정해야 합니다. 이면에서는 Microsoft Edge의 각 창에서 IE 모드 탭이 해당 창 내에 처음 방문하는 경우 지정된 "병합 금지" 사이트 중 하나일 경우 해당 창에서 마지막 IE 모드 탭이 닫힐 때까지 해당 창이 다른 모든 Microsoft Edge 창과 다른 "병합 금지" IE 세션으로 잠깁니다. 이는 사용자가 병합 없이 IE를 시작할 수 있고 다른 메커니즘을 통해 병합 없이 Microsoft Edge를 시작할 수 있었던 이전 동작에 따른 것입니다.  추가 정보는 [IE 모드 문제 해결 및 FAQ | Microsoft Docs](/deployedge/edge-ie-mode-faq#does-ie-mode-on-microsoft-edge-support-the--nomerge--option-that-was-supported-in-internet-explorer-11-)를 참조하세요.

- **암시적 로그인을 중지하는 새 정책입니다.**  시스템 관리자는 [ImplicitSignInEnabled](/deployedge/microsoft-edge-policies#implicitsigninenabled) 정책을 사용하여 Microsoft Edge 브라우저에서 암시적 로그인을 비활성화할 수 있습니다.

- **ClickOnce 및 DirectInvoke 프롬프트를 바이패스하는 정책입니다.** 지정된 도메인에서 ClickOnce의 프롬프트와 DirectInvoke의 특정 파일 형식 앱을 바이패스할 수 있도록 정책을 업데이트했습니다. 이렇게 하려면 다음을 수행해야 합니다.

  - [ClickOnceEnabled](/deployedge/microsoft-edge-policies#clickonceenabled)나 [DirectInvokeEnabled](/deployedge/microsoft-edge-policies#directinvokeenabled) 사용
  - [AutoOpenFileTypes](/deployedge/microsoft-edge-policies#autoopenfiletypes) 정책을 사용하고 ClickOnce 및 QAZ를 사용하지 않도록 설정해야 하는 특정 파일 형식 목록 설정
  - [AutoOpenAllowedForURLs](/deployedge/microsoft-edge-policies#autoopenallowedforurls) 정책을 사용하고 ClickOnce 및 QAZ를 사용하지 않도록 설정해야 하는 특정 도메인 목록 설정

  참고: AutoOpenAllowedForURLs는 AutoOpenFileTypes에 대한 금지 정책입니다. AutoOpenAllowedForURLs가 설정되지 않고 AutoOpenFileTypes가 설정된 경우 나열된 파일 형식이 모든 URL에서 자동으로 열립니다.

- **탭 그룹**  탭을 사용자 정의 그룹으로 분류하고 여러 작업 스트림에서 탭을 보다 효과적으로 찾고 전환하고 관리하는 기능을 제공하는 탭 그룹화를 설정 중입니다.  

- **세로 탭을 사용하는 동안 제목 표시줄을 숨깁니다.**  세로 탭에서 브라우저의 제목 표시줄을 숨겨 몇 개의 픽셀을 다시 가져옵니다. 이제 edge://settings/appearance로 이동하고 사용자 정의 도구 모음 섹션 아래에서 수직 탭 모드에서 제목 표시줄을 숨기는 옵션을 선택할 수 있습니다.

- **호버 도구 모음의 PiP(사진 비디오 사진)입니다.**  지원되는 비디오 위로 마우스를 가져가면 PiP 창에서 해당 비디오를 볼 수 있는 도구 모음이 나타납니다.  참고: 현재 macOS의 Microsoft Edge 사용자가 사용할 수 있습니다.  

- **TLS에서 3DES 제거 TLS_RSA_WITH_3DES_EDE_CBC_SHA 암호화 그룹에 대한 지원이 제거됩니다.** 이 변경은 Microsoft Edge 기반으로 하는 Chromium 프로젝트에서 발생합니다. 자세한 내용은 [크롬 플랫폼 상태 항목](https://chromestatus.com/feature/6678134168485888)으로 이동합니다. 또한 Microsoft Edge 버전 93에서는 [TripleDESEnabled](/deployedge/microsoft-edge-policies#tripledesenabled) 정책을 사용하여 오래된 서버와의 호환성을 유지해야 하는 시나리오를 지원할 수 있습니다. 이 호환성 정책은 사용되지 않으며 Microsoft Edge 버전 95에서 작동이 중지됩니다. 그 전에 영향을 받는 서버를 업데이트해야 합니다.

***새 정책***

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
- [WAMAuthBelowWin10RS3Enabled](/DeployEdge/microsoft-edge-policies#wamauthbelowwin10rs3enabled) Windows 10 RS3 이하 운영체제에서 인증 시 WAM을 사용하도록 설정

***더 이상 사용되지 않는 정책***

- [LegacySameSiteCookieBehaviorEnabled](/DeployEdge/microsoft-edge-policies#legacysamesitecookiebehaviorenabled) 기본 레거시 SameSite 쿠키 동작 설정 사용

***폐기된 정책***

- [NewTabPageSetFeedType](/DeployEdge/microsoft-edge-policies#newtabpagesetfeedtype) 새 Microsoft Edge 탭 페이지 환경 구성

***추가 변경 내용***

- [ConfigureShare](/DeployEdge/microsoft-edge-policies#configureshare) Mac 플랫폼 지원 추가
- [PasswordMonitorAllowed](/DeployEdge/microsoft-edge-policies#passwordmonitorallowed) Mac 플랫폼 지원 추가

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

**사용자는 Microsoft Edge에서 Internet Explorer 모드로 쉽게 이동할 수 있습니다**. Microsoft Edge 버전 92부터 사용자는 엔터프라이즈 모드 사이트 목록에서 사이트가 구성될 때까지 기다리는 동안 독립 실행형 IE 11 응용 프로그램을 사용하는 대신 Microsoft Edge Internet Explorer 모드로 사이트를 다시 로드할 수 있습니다. 사용자에게 사이트를 로컬 사이트 목록에 추가하라는 메시지가 표시되므로 Microsoft Edge에서 같은 페이지로 이동하면 다음 30일 동안 IE 모드로 자동으로 렌더링됩니다. [InternetExplorerIntegrationReloadInIEModeAllowed](/deployedge/microsoft-edge-policies#internetexplorerintegrationreloadiniemodeallowed) 정책을 사용하여 이 환경을 구성하고 IE 모드 진입점에 대한 액세스와 로컬 사이트 목록에 사이트를 추가하는 기능을 허용할 수 있습니다. [InternetExplorerIntegrationLocalSiteListExpirationDays](/deployedge/microsoft-edge-policies#internetexplorerintegrationlocalsitelistexpirationdays) 정책을 사용하여 사이트를 로컬 사이트 목록에 유지할 일수를 조정할 수 있습니다. Windows 10 버전 1909;에는 KB5003698 이상이 필요합니다. Windows 10, 버전 2004, Windows 10, 버전 20H2 또는 Windows 10 버전 21H1에 종단 간 환경을 사용하려면 KB5003690 이상이 필요합니다. 자세한 내용은 [IE 모드의 로컬 사이트 목록](/deployedge/edge-ie-mode-local-site-list)을 참조하세요.

**MHTML 파일은 기본적으로 Internet Explorer 모드에서 열립니다**. Microsoft Edge 버전 92 Stable부터 MHTML 파일 형식은 Internet Explorer(IE11) 애플리케이션 대신 Microsoft Edge Internet Explorer 모드로 자동으로 열립니다. 브라우저에서 Outlook 전자 메일을 보는 동안 가장 일반적으로 관찰됩니다. 이 변경은 IE11이 이 파일 형식의 기본 처리기인 경우에만 발생합니다. 이를 변경하려면 [이 지침](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration)을 사용하여 Stable 버전 92 업데이트를 설치하기 전에 이 작업을 수행할 수 있습니다.

**“개발자 모드 확장을 사용 안 함으로 설정하세요” 경고를 2주 동안 해제할 수 있습니다.** Microsoft Edge 버전 92부터 경고 대화 상자 드롭다운에서 옵션을 선택하여 "개발자 모드 확장 비활성화" 경고를 2주 동안 일시 중지할 수 있습니다.

**도구 모음에서 바로 확장을 관리하세요.** 도구 모음의 새 확장 메뉴를 사용해서 확장을 쉽게 숨기거나 핀으로 고정할 수 있습니다. 확장을 관리하고 새 확장을 찾기 위한 빠른 링크를 사용하면 간편하게 새 확장을 찾고 기존 확장을 관리할 수 있습니다.

**자동 실행의 기본값이 Limit으로 설정됩니다**.  온라인에서 포커스를 유지하기 위해 자동 실행 미디어의 기본값을 허용에서 제한으로 변경했습니다(Microsoft Edge 버전 92부터 시작).

**결제 방법이 이제 장치 간에 동기화됩니다**. Microsoft Edge 버전 92부터 로그인한 장치에서 결제 정보를 동기화할 수 있습니다. 참고: 제어된 기능 롤아웃입니다. 이 기능이 표시되지 않으면 계속 롤아웃하므로 잠시 후에 다시 확인하세요.
현재 이 기능은 미국에서만 사용할 수 있으며 MSA 사용자(AAD 아님)에만 사용할 수 있습니다.

**글꼴 렌더링 개선**. 텍스트 렌더링이 개선되어 선명도를 개선하고 흐릿함을 줄일 수 있습니다. 참고: 제어된 기능 롤아웃입니다. 이 기능이 표시되지 않으면 계속 롤아웃하므로 잠시 후에 다시 확인하세요.

**즐겨찾기 및 모음과 같은 도구 모음 버튼 기능은 창 측면에 고정하기 위해 사용자가 선택한 것을 기억합니다.** 이제 기본적으로 활성화되어 사용자가 도구 모음 버튼을 고정하도록 선택하면 고정 해제를 결정할 때까지 항상 고정된 상태로 열립니다.

**이제 사용자는 그룹 정책을 통해 '이 프로필을 사용하여 직장 또는 학교 사이트에 Single Sign-On 허용' 옵션을 관리할 수 있습니다**.  '이 프로필을 사용하여 직장 또는 학교 사이트에 Single Sign-On 허용'을 사용하면 비 AAD 프로필이 컴퓨터의 직장 또는 학교 자격 증명을 사용하여 직장 또는 학교 사이트에 대해 Single Sign-On을 사용할 수 있습니다. 이 옵션은 비 AAD 프로필에 대해서만 설정 -> 프로필 -> 프로필 기본 설정의 토글로 최종 사용자에게 표시됩니다.  [AADWebSiteSSOUsingThisProfileEnabled](/deployedge/microsoft-edge-policies#aadwebsitessousingthisprofileenabled) 정책을 사용하여 동작을 구성할 수 있습니다.  

**암호 상태** 온라인을 안전하게 유지하려면 여러 계정에서 강력하고 고유한 암호를 사용하는 것이 중요합니다. 그러나 이러한 원리는 말처럼 쉽지 않으며 대부분의 사용자는 추측하기 쉬운 약한 암호를 사용하거나 여러 계정에서 동일한 강력한 암호를 재사용하는 등 잘못된 암호 습관을 보입니다.

이 최신 버전의 Microsoft Edge를 사용하면 강력하고 고유한 암호를 사용하는 작업이 조금 더 쉬워집니다! 이제 Microsoft Edge는 저장된 암호가 충분히 강력한지 여부를 알려주고 여러 사이트에서 암호가 사용되었는지 여부도 표시하여 온라인에서 더 안전한 상태를 유지하는 데 도움이 됩니다. edge://settings/passwords 페이지의 저장된 암호 목록에서 암호 상태 정보를 찾을 수 있습니다.
  
**저장된 암호에 대한 개인정보 보호 추가** 다른 사람과 공유하는 장치를 사용 중이거나 어떤 이유로든 컴퓨터를 잠금 해제한 상태로 둔 경우 이제 장치 암호를 사용하여 두 번째 확인을 선택하여 다른 사람이 귀하의 웹사이트 암호에 액세스하지 못하도록 할 수 있습니다. 단순합니다!

**Outlook 확장 프로그램**.  새 브라우저 창을 열지 않고도 Microsoft Outlook 받은 편지함, 일정, 작업 등을 확인하세요.  새 Outlook 확장 프로그램은 [Microsoft Outlook - Microsoft Edge Addons](https://microsoftedge.microsoft.com/addons/detail/microsoft-outlook/kkpalkknhlklpbflpcpkepmmbnmfailf?hl=en-US)에서 다운로드할 수 있습니다.

**Chromium 오픈 소스 프로젝트에 따라 Microsoft Edge는 웹 페이지에서 테이블을 렌더링하는 방식을 업데이트하고 있습니다.** 이 변경 사항은 알려진 문제를 수정하고 Microsoft Edge를 웹/다른 브라우저에서 테이블이 렌더링되는 지정된 방식에 더 가깝게 만듭니다. 예기치 않은 문제에 대해 환경의 중요한 워크플로를 테스트하는 것이 좋습니다. 전체 설명자는 [여기](https://docs.google.com/document/d/16PFD1GtMI9Zgwu0jtPaKZJ75Q2wyZ9EZnVbBacOfiNA/edit)에서 이용할 수 있습니다.

### <a name="new-policies"></a>새 정책

- [AADWebSiteSSOUsingThisProfileEnabled](/DeployEdge/microsoft-edge-policies#aadwebsitessousingthisprofileenabled) 이 프로필을 사용하도록 설정된 회사 또는 학교 사이트에 대한 Single Sign-On을 사용합니다.
- [AutomaticHttpsDefault](/DeployEdge/microsoft-edge-policies#automatichttpsdefault) 자동 HTTPS 구성
- [HeadlessModeEnabled](/DeployEdge/microsoft-edge-policies#headlessmodeenabled) 비입력 시스템 모드 사용 제어
- [InsecurePrivateNetworkRequestsAllowed](/DeployEdge/microsoft-edge-policies#insecureprivatenetworkrequestsallowed) 비보안 웹 사이트에서 비공개 네트워크 엔드포인트에 대한 요청을 수행할 수 있도록 허용할지 여부를 지정합니다.
- [InsecurePrivateNetworkRequestsAllowedForUrls](/DeployEdge/microsoft-edge-policies#insecureprivatenetworkrequestsallowedforurls) 나열된 사이트가 안전하지 않은 컨텍스트에서 더 많은 개인 네트워크 엔드포인트에 요청을 할 수 있도록 허용
- [InternetExplorerIntegrationLocalSiteListExpirationDays](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationlocalsitelistexpirationdays) 사이트가 로컬 IE 모드 사이트 목록에 남아 있는 일수 지정
- [InternetExplorerIntegrationReloadInIEModeAllowed](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationreloadiniemodeallowed) Internet Explorer 모드에서 구성되지 않은 사이트를 다시 로드할 수 있도록 허용
- [SharedArrayBufferUnrestrictedAccessAllowed](/DeployEdge/microsoft-edge-policies#sharedarraybufferunrestrictedaccessallowed) cross-origin-isolated가 아닌 컨텍스트에서 SharedArrayBuffers를 사용할 수 있는지 여부 지정

### <a name="deprecated-policy"></a>더 이상 사용되지 않는 정책

- [InternetExplorerIntegrationTestingAllowed](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationtestingallowed) - Internet Explorer 모드 테스트를 허용합니다.

### <a name="obsoleted-policy"></a>폐기된 정책

- [EnableSha1ForLocalAchors](/DeployEdge/microsoft-edge-policies#enablesha1forlocalanchors) 로컬 트러스트 앵커에서 발급한 경우 SHA-1을 사용하여 서명한 인증서 허용합니다.

## <a name="version-91086471-july-19"></a>버전 91.0.864.71: 7월 19일

> [!Important]
>이 업데이트에는 Chromium 팀이 악용된 것으로 보고한 [CVE-2021-30563](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-30563)에 대한 수정 사항이 포함되어 있습니다. 자세한 내용은 [보안 업데이트 가이드](https://msrc.microsoft.com/update-guide/vulnerability/ADV200002)를 참고하세요.

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#july-19-2021)에서 확인할 수 있습니다.

## <a name="version-91086467-july-8"></a>버전 91.0.864.67: 7월 8일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-91086464-july-2"></a>버전 91.0.864.64: 7월 2일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-91086459-june-24"></a>버전 91.0.864.59: 6월 24일

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#june-24-2021)에서 확인할 수 있습니다.

## <a name="version-91086454-june-18"></a>버전 91.0.864.54: 6월 18일

> [!Important]
> 이 업데이트에는 Chromium 팀에서 악용되는 것으로 보고한 [CVE-2021-30554](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-30554)에 대한 수정 사항이 포함되어 있습니다. 자세한 내용은 [보안 업데이트 가이드](https://msrc.microsoft.com/update-guide/vulnerability/ADV200002)를 참고하세요.

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#june-18-2021)에서 확인할 수 있습니다.

## <a name="version-91086448-june-11"></a>버전 91.0.864.48: 6월 11일

> [!Important]
>이 업데이트에는 Chromium 팀에서 악용되는 것으로 보고한 [CVE-2021-30551](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-30551)에 대한 수정 사항이 포함되어 있습니다. 자세한 내용은 [보안 업데이트 가이드](https://msrc.microsoft.com/update-guide/vulnerability/ADV200002)를 참고하세요.

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#june-11-2021)에서 확인할 수 있습니다.

## <a name="version-91086441-june-3"></a>버전 91.0.864.41: 6월 3일

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#june-3-2021)에서 확인할 수 있습니다.

## <a name="version-91086437-may-27"></a>버전 91.0.864.37: 5월 27일

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#may-27-2021)에서 확인할 수 있습니다.

### <a name="feature-updates"></a>기능 업데이트

- **프록시 수준의 Microsoft Defender Application Guard 컨테이너에서 발생하는 네트워크 트래픽을 식별합니다.** Microsoft Edge 버전 91부터는 Application Guard 컨테이너에서 발생하는 네트워크 트래픽에 태그를 지정하는 지원이 기본적으로 제공되어 기업에서 해당 트래픽을 식별하고 특정 정책을 적용할 수 있습니다.

- **호스트에서 Edge Application Guard 컨테이너의 즐겨찾기 동기화를 허용하는 지원 옵션입니다.** Microsoft Edge 버전 91부터 사용자는 호스트에서 컨테이너로 즐겨찾기를 동기화하도록 Application Guard를 구성할 수 있습니다. 이렇게 하면 새 즐겨찾기도 컨테이너에 표시됩니다.

- **Microsoft Edge 버전 91부터 브라우저는 사용자 상호 작용 없이 다운로드가 시작되고 SmartScreen 응용 프로그램 신뢰도 검사가 지원되지 않는 경우 컴퓨터를 손상시킬 수 있는 유형의 다운로드를 자동으로 중단합니다.** 사용자는 다운로드 항목을 마우스 오른쪽 단추로 클릭하고 "유지"를 선택하여 재정의하고 계속 다운로드할 수 있습니다. 엔터프라이즈 관리자는 다음 정책을 구성하여 이 동작을 옵트아웃할 수 있습니다.
  - [ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](/deployedge/microsoft-edge-policies#exemptdomainfiletypepairsfromfiletypedownloadwarnings.md) - 도메인에서 지정된 파일 형식에 대해 파일 형식 확장명 기반 주의 다운로드를 사용설정 해제합니다.

    자세한 내용은 [Microsoft Edge 보안 다운로드 중단](microsoft-edge-security-downloads-interruptions.md)을 참조하세요.

- **음성 인식 API에 대한 지원** Microsoft Edge 버전 91부터 Google.com 및 유사한 사이트에서 음성 인식 명령에 대한 API 지원이 추가됩니다. 이 기능은 실험을 허락한 임의로 선택된 사용자 그룹으로 제한됩니다. 이러한 사용자는 기능 팀에 피드백을 제공합니다.

- **새 테마 색으로 브라우저를 개인 설정하세요**. 설정 -> 모양 페이지에서 14가지 새로운 테마 색 중 하나를 사용하여 나만의 Microsoft Edge를 만드세요. Microsoft Edge 추가 기능 사이트에서 사용자 지정 테마를 설치할 수도 있습니다. [자세히 알아보기](https://techcommunity.microsoft.com/t5/articles/make-microsoft-edge-your-own-with-themes/m-p/2083165)

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
>이 업데이트에는 Chromium 팀이 악용된 것으로 보고한 [CVE-2021-21224](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21224)에 대한 수정 사항이 포함되어 있습니다. 자세한 내용은 [보안 업데이트 가이드](https://msrc.microsoft.com/update-guide)를 참고하세요.

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#april-16-2021)에서 확인할 수 있습니다.

## <a name="version-90081839-april-15"></a>버전 90.0.818.39: 4월 15일 ##

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#april-15-2021)에서 확인할 수 있습니다.

## <a name="feature-updates"></a>기능 업데이트 ##

-    **이제 macOS에서 Azure AD(Azure Active Directory) 계정과 Microsoft MSA(Microsoft 계정)에 SSO(Single Sign On)를 사용할 수 있습니다.** macOS에서 Microsoft Edge에 로그인한 사용자는 회사 및 Microsoft 계정(예: bing.com, office.com, msn.com, outlook.com)으로 Single Sign-On을 허용하도록 구성된 웹 사이트에 자동으로 로그인됩니다.

- **키오스크 모드.** Microsoft Edge 버전 90부터 구성된 프린터 및 "PDF로 인쇄" 옵션만 허용하도록 UI 인쇄 설정을 잠갔습니다. 또한 할당된 액세스 단일 앱 키오스크 모드 내에서 향상된 기능을 수행하여 브라우저에서 다른 애플리케이션의 시작을 제한했습니다. 키오스크 모드 기능에 대한 자세한 내용은 [여기](/deployedge/microsoft-edge-configure-kiosk-mode#kiosk-mode-supported-features)를 참보하세요.

- **다운로드 중단** Microsoft Edge 버전 91부터 브라우저는 사용자 상호 작용 없이 다운로드가 시작되고 SmartScreen 응용 프로그램 신뢰도 검사가 지원되지 않는 경우 컴퓨터를 손상시킬 수 있는 유형의 다운로드를 자동으로 중단합니다. 사용자는 다운로드 항목을 마우스 오른쪽 단추로 클릭하고 "유지"를 선택하여 재정의하고 계속 다운로드할 수 있습니다.
엔터프라이즈 관리자는 다음 두 정책 중 하나로 이 동작을 옵트아웃할 수 있습니다.
- [ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](/deployedge/microsoft-edge-policies#exemptdomainfiletypepairsfromfiletypedownloadwarnings) - 도메인에서 지정된 파일 형식에 대해 파일 형식 확장명 기반 주의 다운로드를 사용설정 해제합니다. 자세한 정보는 [Microsoft Edge 보안 다운로드 중단](/deployedge/microsoft-edge-security-downloads-interruptions)을 참조하세요.

- **인쇄**:

    - **포스트스크립트가 아닌 프린터를위한 새로운 인쇄 래스터화 모드.** Microsoft Edge 버전 90부터 관리자는 새 정책을 사용하여 사용자에 대한 인쇄 래스터화 모드를 정의할 수 있습니다. 이 정책은 Windows에서 포스트스크립트가 아닌 프린터에 대해 Microsoft Edge의 인쇄 방식을 제어합니다. PostScript가 아닌 프린터에서 인쇄 작업을 올바르게 인쇄하려면 래스터 화해야하는 경우가 있습니다. 인쇄 옵션은 전체 및 고속입니다.
    
  - **인쇄를 위한 추가 페이지 배율 옵션입니다.** 이제 사용자는 추가 옵션을 사용하여 웹 페이지 및 PDF 문서를 인쇄하는 동안 스케일링을 사용자 지정할 수 있습니다. "페이지에 맞추기" 옵션을 사용하면 웹 페이지나 문서를 인쇄를 위해 선택한 "용지 크기"에서 사용할 수 있는 공간에 맞출 수 있습니다. "실제 크기" 옵션은 선택한 "용지 크기"에 관계없이 인쇄되는 내용의 크기가 변경되지 않도록 합니다.

-   **생산력:**

    -   **자동 완성 제안이 클립 보드의 주소 필드 내용을 포함하도록 확장되었습니다.** 사용자가 프로필/주소란(예: 전화번호, 전자 메일, 우편 번호, 시, 도)을 클릭할 때 자동 채우기 제안을 표시하기 위해 클립보드 콘텐츠를 분석합니다.

    -   **사용자는 양식이나 필드가 감지되지 않는 경우에도 자동 완성 제안을 검색할 수 있습니다.** 오늘날 Microsoft Edge에 정보를 저장한 경우 자동 완성 제안이 자동으로 표시되어 양식을 작성하는 동안 시간을 ​​절약할 수 있습니다. 자동 완성이 양식을 놓친 경우 또는 일반적으로 자동 완성이 없는 양식(예: 임시 양식)에서 데이터를 가져오려는 경우 자동 완성을 사용하여 정보를 검색할 수 있습니다.

-   **메뉴 모음의 플라이 아웃에서 다운로드에 액세스합니다.** 다운로드는 모든 활성 다운로드가 한곳에 있는 오른쪽 상단 모서리에 표시됩니다. 이 메뉴는 쉽게 닫을 수 있으므로 사용자는 중단없이 계속 탐색 할 수 있으며 도구 모음에서 바로 전체 다운로드 진행 상황을 모니터링할 수 있습니다. [자세한 내용을 알아보세요](https://techcommunity.microsoft.com/t5/articles/introducing-the-new-downloads-experience/m-p/2111551).

-   **글꼴 렌더링 개선.** Microsoft Edge 버전 90부터 텍스트 렌더링을 개선하여 선명도를 높이고 흐릿함을 줄였습니다. 글꼴 렌더링 개선의 일부는 베타 버전 90에 제공되지만 기본적으로 비활성화되어 있습니다.

- **어린이 모드.** 정책을 사용하도록 설정하면 가족 보호 기능 외에 어린이 모드 기능을 사용하지 않도록 정책을 업데이트했습니다. 키즈 모드에 대한 자세한 내용은 [여기](https://go.microsoft.com/fwlink/?linkid=2146910)를 참조하세요.

## <a name="policy-updates"></a>정책 업데이트

## <a name="new-policies"></a>새 정책

새 정책 8개를 추가했습니다. [Microsoft Edge Enterprise 방문 페이지](https://www.microsoft.com/edge/business/download)에서 업데이트된 관리 템플릿을 다운로드할 수 있습니다. 다음과 같은 새 정책이 추가되었습니다.
-   [ ApplicationGuardFavoritesSyncEnabled ](/DeployEdge/microsoft-edge-policies#applicationguardfavoritessyncenabled)-Application Guard 즐겨 찾기 동기화 사용
- [ApplicationGuardTrafficIdentificationEnabled](/DeployEdge/microsoft-edge-policies#applicationguardtrafficidentificationenabled) Application Guard 트래픽 식별
- [ExplicitlyAllowedNetworkPorts](/DeployEdge/microsoft-edge-policies#explicitlyallowednetworkports) 명시적으로 허용된 네트워크 포트
- [ImportStartupPageSettings](/DeployEdge/microsoft-edge-policies#importstartuppagesettings) 시작 페이지 설정 가져오기 허용
- [MathSolverEnabled](/DeployEdge/microsoft-edge-policies#mathsolverenabled) 사용자가 수학 문제를 캡쳐하고 Microsoft Edge에서 단계별 설명을 통해 해결책을 얻을 수 있도록 함
- [NewTabPageContentEnabled](/DeployEdge/microsoft-edge-policies#newtabpagecontentenabled) 새 탭 페이지에서 Microsoft News 콘텐츠 허용
- [NewTabPageQuickLinksEnabled](/DeployEdge/microsoft-edge-policies#newtabpagequicklinksenabled) 새 탭 페이지에서 빠른 링크 허용
-   [FetchKeepaliveDurationSecondsOnShutdown](/DeployEdge/microsoft-edge-policies#fetchkeepalivedurationsecondsonshutdown)- 종료 시 유지 기간 가져오기
-   [ ManagedConfigurationPerOrigin ](/DeployEdge/microsoft-edge-policies#managedconfigurationperorigin)-웹 사이트의 관리 구성 값을 특정 원본으로 설정합니다.
-   [ PrintRasterizationMode ](/DeployEdge/microsoft-edge-policies#printrasterizationmode) - 래스터화 모드 인쇄
-   [QuickViewOfficeFilesEnabled](/DeployEdge/microsoft-edge-policies#quickviewofficefilesenabled) - Microsoft Edge에서 QuickView Office 파일 관리
-   [SSLErrorOverrideAllowedForOrigins](/DeployEdge/microsoft-edge-policies#sslerroroverrideallowedfororigins) - 사용자가 특정 출처에 대한 HTTPS 경고 페이지에서 계속할 수 있도록 허용
-   [ WindowOcclusionEnabled ](/DeployEdge/microsoft-edge-policies#windowocclusionenabled)-창 폐색 사용
-   [ WindowsHelloForHTTPAuthEnabled ](/DeployEdge/microsoft-edge-policies#windowshelloforhttpauthenabled)-HTTP 인증용 Windows Hello 사용

## <a name="deprecated-policies"></a>더 이상 사용되지 않는 정책

- [ProactiveAuthEnabled](/DeployEdge/microsoft-edge-policies#proactiveauthenabled) 사전 인증을 사용하도록 설정합니다.
-   [ NativeWindowOcclusionEnabled ](/DeployEdge/microsoft-edge-policies#nativewindowocclusionenabled) - 기본 폐색 활성화
-   [ SSL버전Min](/DeployEdge/microsoft-edge-policies#sslversionmin) - 활성화된 최소 TLS 버전

## <a name="version-89077477-april-14"></a>버전 89.0.774.77: 4월 14일

> [!Important]
>이 업데이트에는 [CVE-2021-21206](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21206) 및 [CVE-2021-21220](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21220)에 대한 수정 사항이 포함되어 있으며, 이 수정 사항은 Chromium 팀에서 악용한 것으로 보고되었습니다.  자세한 내용은 [보안 업데이트 가이드](https://msrc.microsoft.com/update-guide)를 참고하세요.

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

## <a name="version"></a>버전

> [!IMPORTANT]
> 이 업데이트에는 [CVE-2021-21166](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21166)이 포함되어 있으며 Chromium 팀은 이 취약점이 악용된 것으로 보고했습니다. 자세한 내용은 [보안 업데이트 가이드](https://msrc.microsoft.com/update-guide)를 참조하세요.

안정 채널 보안 업데이트는 [여기](./microsoft-edge-relnotes-security.md#march-4-2021)에서 확인할 수 있습니다.

### <a name="resolved-issues"></a>해결된 문제

- **작업 표시줄 및 시작 메뉴 바로 가기 업데이트 및 수정 사항:**
  - 이제 시작 메뉴에서 Microsoft Edge 바로 가기를 마우스 오른쪽 단추로 클릭하면 고정된 경우 작업 표시줄에서 Microsoft Edge를 고정 해제하는 옵션이 제대로 표시됩니다.
  - Microsoft Edge를 작업 표시줄에 고정하는 [작업 표시줄 구성](/windows/configuration/configure-windows-10-taskbar)이 포함된 시작 레이아웃은 두 번째 Microsoft Edge 바로 가기에서 더 이상 작업 표시줄을 고정하지 않습니다.
  - Windows 로밍 프로필을 사용하는 조직에서 사용자가 Windows에 로그온할 때 작업 표시줄의 Microsoft Edge 아이콘 대신 빈 흰색 아이콘이 더 이상 표시되지 않습니다.

### <a name="feature-updates"></a>기능 업데이트

- **키오스크 모드에서는 추가 잠금 기능을 사용할 수 있습니다**. Microsoft Edge 버전 89부터는 고객이 생산성과 보안이 강화된 환경에서 작업을 완료할 수 있도록 키오스크 모드에 추가 잠금 모드가 추가되었습니다. [자세한 내용을 알아보세요](microsoft-edge-configure-kiosk-mode.md#kiosk-mode-supported-features).

- **Enterprise Mode Site List Manager 도구는 *edge://compat* 페이지**를 통해 브라우저에서 사용 가능합니다. 이 도구를 사용하여 Microsoft Edge에서 Internet Explorer 모드에 대한 사이트 목록 XML을 만들고 편집하고 내보낼 수 있습니다. 그룹 정책을 통해 필요한 경우 이 도구에 대한 액세스를 사용하도록 설정할 수 있습니다. [자세한 내용을 알아보세요](./edge-ie-mode-site-list-manager.md).

- **절전 모드 탭을 사용하여 브라우저 성능을 향상합니다**. 절전 모드 탭은 활성 탭이나 다른 응용 프로그램에서 사용할 수 있도록 메모리 및 CPU와 같은 시스템 리소스를 확보하기 위해 비활성 탭을 절전 모드로 전환하여 브라우저 성능을 향상시킵니다. 사용자는 사이트가 절전 모드로 전환되는 것을 방지하고 비활성 탭이 절전 모드로 전환될 때까지의 시간을 구성할 수 있습니다. 사용자를 흐름에서 유지시키기 위해 인트라넷 사이트와 같은 특정 사이트가 절전 모드로 전환되는 것을 방지하는 [추론](https://techcommunity.microsoft.com/t5/articles/sleeping-tabs-faq/m-p/1705434)도 있습니다. 이 기능은 그룹 정책을 통해 관리할 수 있습니다.

- **클라우드에서 Microsoft Edge 동기화 데이터를 수동으로 다시 설정하세요**. 제품 내에서 Microsoft Edge 동기화 데이터를 다시 설정하는 방법이 도입되었습니다. 이 방법을 사용하면 Microsoft 서비스에서 데이터를 확실히 지우고, 이전에는 지원 티켓이 필요했던 특정 제품 문제를 해결할 수 있습니다.

- **모든 Windows Azure Active Directory(Azure AD) 계정에 대해 SSO(Single Sign-On)를 지능적으로 사용하도록 설정하면 Azure AD Microsoft Edge이 아닌 단일 프로필이 있는 사용자에게 적용됩니다.**  이 기능에서 가장 많은 혜택을 받을 수 있는 사용자에 대해 이 설정을 자동으로 켜면 됩니다. 사용자가 하나의 Microsoft Edge 프로파일(Azure AD 또는 Kids Mode가 아닌 경우)만 있으면 Microsoft Edge가 실행될 때 설정이 자동으로 설정됩니다. 사용자가 나중에 Azure AD 계정으로 다른 Microsoft Edge 프로필에 로그인하도록 선택하는 경우 이 자동 토글도 자동으로 해제됩니다. 사용자는 **설정 > 프로필 환경설정 > 프로필 환경설정 > 이 프로필을 사용하여 직장 또는 학교 사이트에 대한 단일 로그온 허용**에서 이 기능에 대한 환경설정을 수동으로 업데이트할 수 있습니다.

- **PDF 문서 내의 텍스트 선택 환경이 개선됩니다**. Microsoft Edge 버전 89 이상에서 연 PDF 문서 전반에서 더욱 원활하고 일관성 있는 텍스트 선택 환경이 제공됩니다.

- **이제 자동 채우기에서 생년월일 필드가 지원됩니다.** 오늘날 Microsoft Edge는 양식을 작성하거나 계정을 만들 때 주소, 이름, 전화번호 등 데이터를 자동으로 채워 사용자의 시간을 절약하고 수고를 덜어줍니다. Microsoft Edge 버전 89부터는 생년월일도 저장해서 자동 채우기 기능을 사용하실 수 있습니다. 프로필 설정에서 언제든지 이 정보를 보고 편집하고 삭제할 수 있습니다.

### <a name="policy-updates"></a>정책 업데이트

#### <a name="new-policies"></a>새로운 정책

새 정책 7개를 추가했습니다. [Microsoft Edge Enterprise 방문 페이지](https://www.microsoft.com/edge/business/download)에서 업데이트된 관리 템플릿을 다운로드할 수 있습니다. 다음과 같은 새 정책이 추가되었습니다.

- [BrowsingDataLifetime](./microsoft-edge-policies.md#browsingdatalifetime) - 데이터 수명 설정 검색
- [MAMEnabled](./microsoft-edge-policies.md#mamenabled) - 모바일 앱 관리 사용
- [DefinePreferredLanguages](./microsoft-edge-policies.md#definepreferredlanguages) - 사이트에서 언어를 지원하는 경우 웹 사이트에서 표시할 기본 설정 언어의 순서가 정해진 목록 정의
- [ShowRecommendationsEnabled](./microsoft-edge-policies.md#showrecommendationsenabled) - Edge에서 추천 및 홍보 알림 허용
- [PrintingAllowedBackgroundGraphicsModes](./microsoft-edge-policies.md#printingallowedbackgroundgraphicsmodes) - 배경 그래픽 인쇄 모드 제한
- [PrintingBackgroundGraphicsDefault](./microsoft-edge-policies.md#printingbackgroundgraphicsdefault) - 기본 배경 그래픽 인쇄 모드
- [SmartActionsBlockList](./microsoft-edge-policies.md#smartactionsblocklist) - 서비스 목록에 대한 스마트 작업 차단

#### <a name="obsoleted-policies"></a>폐기된 정책

다음 정책은 사용되지 않습니다.

- [ForceLegacyDefaultReferrerPolicy](./microsoft-edge-policies.md#forcelegacydefaultreferrerpolicy) - no-referrer-when-downgrade의 기본 참조자 정책 사용
- [MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled) - 사용 현황 및 크래시 관련 데이터 보고 사용
- [SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices) - Microsoft 서비스를 개선하기 위해 사이트 정보 보내기

<!-- end major 89 -->

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

- **시작 부스트를 통해 Microsoft Edge 시작 속도를 개선합니다**. Microsoft Edge 시작 속도를 개선하기 위해 시작 부스트라는 기능을 개발했습니다. 시작 부스트를 사용하면 Microsoft Edge가 백그라운드에서 실행되어 Microsoft Edge가 더 빠르게 실행됩니다. 참고: 이 기능은 실험을 활성화한 임의로 선택된 사용자 그룹으로 제한됩니다. 이러한 사용자는 기능 팀에 피드백을 제공합니다.

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
- [EnableSha1ForLocalAchors](./microsoft-edge-policies.md#enablesha1forlocalanchors) - 로컬 트러스트 앵커에서 발급한 경우 SHA-1을 사용하여 서명한 인증서 허용합니다. <!--- [ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](./microsoft-edge-policies.md#exemptdomainfiletypepairsfromfiletypedownloadwarnings) - Disable download file type extension-based warnings for specified file types on domains. -->
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

새 정책 7개를 추가했습니다. [Microsoft Edge Enterprise 방문 페이지](https://aka.ms/EdgeEnterprise)에서 업데이트된 관리 템플릿을 다운로드할 수 있습니다. 다음과 같은 새 정책이 추가되었습니다.

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

- Microsoft Defender for Cloud Apps 경고 시나리오를 사용할 수 있습니다. 이를 통해 관리자는 사용자가 클라우드용 Defender 앱 블록 페이지를 재정의할 수 있는 클라우드용 Defender Apps 블록의 새 범주인 경고를 설정할 수 있습니다. MDATP E5 차단은 원활한 환경을 위해 Microsoft Edge의 SmartScreen 차단과 기본적으로 통합 되어 있습니다. 이 기능을 사용하면 단순히 알림이 뜨는 것이 아니라 "이 웹 사이트가 조직에 의해 차단 되었습니다"라는 메시지가 포함 된 전체 페이지 적색 차단이 포함됩니다.

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

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)