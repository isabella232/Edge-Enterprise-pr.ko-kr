---
title: 안정 채널에 대한 Microsoft Edge 릴리스 정보
ms.author: leahtu
author: dan-wesley
manager: srugh
ms.date: 03/10/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 안정 채널에 대한 Microsoft Edge 릴리스 정보
ms.openlocfilehash: a7e11586c77b600253f25c2819a26e72e18f4b28
ms.sourcegitcommit: 556aca8dde42dd66364427f095e8e473b86651a0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2022
ms.locfileid: "12445642"
---
# <a name="release-notes-for-microsoft-edge-stable-channel"></a>Microsoft Edge 안정 채널에 대한 릴리스 정보

이 릴리스 정보는 Microsoft Edge 안정 채널에 포함된 새로운 기능 및 비보안 업데이트에 대한 정보를 제공합니다.

- 모든 보안 업데이트는 [Microsoft Edge 보안 업데이트에 대한 릴리스 정보](./microsoft-edge-relnotes-security.md)에 나열되어 있습니다.
- Microsoft Edge 안정 채널의 보관된 릴리스 정보는 [Microsoft Edge 안정 채널의 보관된 릴리스 정보](./microsoft-edge-relnote-archive-stable-channel.md)에 있습니다.

 Microsoft Edge 채널을 이해하려면 [Microsoft Edge 채널 개요](./microsoft-edge-channels.md)를 참조하세요.

> [!NOTE]
> 안정 채널의 업데이트는 하루 이상 점진적으로 배포됩니다. 자세한 내용은 [Microsoft Edge 업데이트 점진적 배포](./microsoft-edge-update-progressive-rollout.md)를 참조하세요.
>
> Microsoft Edge 웹 플랫폼은 사용자 환경, 보안 및 개인 정보 개선을 위해 지속적으로 진화하고 있습니다. 자세히 알아보려면 [Microsoft Edge에 적용될 사이트 호환성에 영향을 미치는 변경 사항](/microsoft-edge/web-platform/site-impacting-changes)을 참조하세요.

## <a name="version-990115039-march-10"></a>버전 99.0.1150.39: 3월 10일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-980110876-march-9"></a>버전 98.0.1108.76: 3월 9일

확장 안정 릴리스에 대한 다양한 버그 및 성능 문제를 해결했습니다.

## <a name="version-990115036-march-7"></a>버전 99.0.1150.36: 3월 7일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-990115030-march-3"></a>버전 99.0.1150.30: 3월 3일

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#march-3-2022)에서 확인할 수 있습니다.

### <a name="feature-updates"></a>기능 업데이트

- **사용자 에이전트 문자열의 향후 3자리 버전 번호.** 버전 100부터 Microsoft Edge는 "Edg/100"과 같이 User-Agent 헤더에 3자리 버전 번호를 보냅니다. Microsoft Edge 97부터 사이트 소유자는 *edge://flags*에서 **#force-major-version-to-100** 실험 플래그를 사용하도록 설정하여 이 예정된 에이전트 문자열을 테스트하여 사용자 에이전트 구문 분석 논리는 강력하고 예상대로 작동합니다.

- **사이트에 대한 프로필 기본 설정으로 다중 프로필 환경을 개인 설정하세요.** 사용자는 Microsoft Edge에서 자동 프로필 전환을 위해 사용자 지정된 사이트 목록을 만드는 기능을 사용하여 다중 프로필 환경을 개인 설정할 수 있습니다.

- **페이지 축소판을 사용하여 PDF 문서를 탐색합니다.** 이제 페이지를 나타내는 축소판을 사용하여 PDF 문서를 탐색할 수 있습니다. 이러한 축소판은 PDF 리더의 왼쪽 창에 나타납니다.

- **저장 및 채우기에 대한 암호 관리자 UI(사용자 인터페이스)가 비활성화될 도메인 목록을 구성합니다.** [PasswordManagerBlocklist](/deployedge/microsoft-edge-policies#passwordmanagerblocklist) 정책을 사용하여 Microsoft Edge에서 암호 관리자를 비활성화해야 하는 도메인 목록(HTTP/HTTPS 스키마 및 호스트 이름만 해당)을 구성합니다. 즉, 저장 및 채우기 워크플로가 비활성화되어 해당 웹 사이트의 암호를 저장하거나 웹 양식에 자동으로 채울 수 없습니다.

- **사용자 지정 기본 암호.** 브라우저에는 웹 양식에 저장된 암호가 자동으로 채워지기 전에 사용자가 인증 단계를 추가할 수 있는 기능이 이미 있습니다. 이것은 또 다른 개인 정보 보호 계층을 추가하고 승인되지 않은 사용자가 저장된 암호를 사용하여 웹 사이트에 로그온하는 것을 방지하는 데 도움이 됩니다. 사용자 지정 기본 암호는 동일한 기능의 발전된 것으로 사용자는 이제 사용자가 선택한 사용자 지정 문자열을 기본 암호로 사용할 수 있습니다. 사용하도록 설정되면 사용자는 이 암호를 입력하여 자신을 인증하고 저장된 암호를 웹 양식에 자동으로 입력합니다.

### <a name="policy-updates"></a>정책 업데이트

#### <a name="new-policies"></a>새 정책

- [DoNotSilentlyBlockProtocolsFromOrigins](/DeployEdge/microsoft-edge-policies#donotsilentlyblockprotocolsfromorigins) - 홍수 방지 보호로 자동으로 차단할 수 없는 프로토콜 목록 정의
- [ForceMajorVersionToMinorPositionInUserAgent](/DeployEdge/microsoft-edge-policies#forcemajorversiontominorpositioninuseragent) - 주 버전 99에서 사용자 에이전트 문자열 고정 사용 또는 비활성화
- [HubsSidebarEnabled](/DeployEdge/microsoft-edge-policies#hubssidebarenabled) - 허브 사이드바 표시
- [InternetExplorerIntegrationCloudNeutralSitesReporting](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationcloudneutralsitesreporting) - M365 관리 센터 사이트 목록 앱에 대한 잠재적으로 잘못 구성된 중립 사이트 URL의 보고 구성
- [InternetExplorerIntegrationCloudUserSitesReporting](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationcloudusersitesreporting) - M365 관리 센터 사이트 목록 앱에 대한 IE 모드 사용자 목록 항목의 보고 구성
- [PasswordManagerBlocklist](/DeployEdge/microsoft-edge-policies#passwordmanagerblocklist) - 암호 관리자 UI(저장 및 채우기)가 비활성화될 도메인 목록을 구성합니다.
- [RelatedMatchesCloudServiceEnabled](/DeployEdge/microsoft-edge-policies#relatedmatchescloudserviceenabled) - 페이지에서 찾기에서 관련 일치 구성
- [SignInCtaOnNtpEnabled](/DeployEdge/microsoft-edge-policies#signinctaonntpenabled) - 로그인 활성화 클릭 투 액션 대화상자
- [UserAgentReduction](/DeployEdge/microsoft-edge-policies#useragentreduction) - 사용자 에이전트 감소 사용 또는 비활성화


## <a name="version-980110862-february-24"></a>버전 98.0.1108.62: 2월 24일

안정 및 확장 안정 릴리스에 대한 다양한 버그 및 성능 문제를 수정했습니다.

## <a name="version-980110856-february-17"></a>버전 98.0.1108.56: 2월 17일

안정 및 확장 안정 릴리스에 대한 다양한 버그 및 성능 문제를 수정했습니다.

## <a name="version-980110855-february-16"></a>버전 98.0.1108.55: 2월 16일

> [!Important]
> 이 업데이트에는 Chromium 팀에서 야생에서 악용되는 것으로 보고된 [CVE-2022-0609](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2022-0609)에 대한 수정 사항이 포함되어 있습니다. 자세한 내용은 [보안 업데이트 가이드](https://msrc.microsoft.com/update-guide)를 참조하세요.

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#february-16-2022)에서 확인할 수 있습니다.

## <a name="version-980110850-february-10"></a>버전 98.0.1108.50: 2월 10일

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#february-10-2022)에서 확인할 수 있습니다.

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

<!---archive from Version 96.0.1054.29: November 19 to Version 94.0.992.57: October 27 --->
<!-- archive from Version 95.0.1020.30: October 21 to Version 94.0.992.37: September 30 -->
<!-- archive from Version 94.0.992.31: September 24 to Version 93.0.961.44: September 9  -->
<!--- Archive from Version 93.0.961.38: September 2 to Version 92.0.902.62: July 29 --->
<!-- Archive from Version 92.0.902.55: July 22 to Version 91.0.864.37: May 27 -->
<!-- Archive from 89.0.774.45: March 4 to 90.0.818.66: May 20 ->
<!-- Archive from 86.0.622.43: October 15 to beta 88.0.705.81: February 25  ->
<!-- Archive from 86.0.622.38-october-9 to beta 86.0.62.215-september-14  ->
<!-- Archived to version 84.0.522.40: July 16 -->

## <a name="see-also"></a>참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
