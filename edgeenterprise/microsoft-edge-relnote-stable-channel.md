---
title: 안정 채널에 대한 Microsoft Edge 릴리스 정보
ms.author: leahtu
author: dan-wesley
manager: srugh
ms.date: 04/07/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 안정 채널에 대한 Microsoft Edge 릴리스 정보
ms.openlocfilehash: 0cf9c2d0ac7a60c03ad6c80d4186629d296a73c6
ms.sourcegitcommit: dd8cdbd35726c795ddce917e549ddf17ee7f5290
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/11/2022
ms.locfileid: "12473663"
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

## <a name="version-1000118536-april-7"></a>버전 100.0.1185.36: 4월 7일

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#april-7-2022)에서 확인할 수 있습니다.

## <a name="version-1000118529-april-1"></a>버전 100.0.1185.29: 4월 1일

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#april-1-2022)에서 확인할 수 있습니다.

### <a name="feature-updates"></a>기능 업데이트

- **User-agent 문자열의 3자리 버전 번호.** 이제 Microsoft Edge는 User-Agent 헤더에 Edg/100과 같은 3자리 버전 번호를 보냅니다. 이로 인해 버그가 있는 파서를 사용하여 User-Agent 문자열 버전 번호를 확인하는 스크립트 또는 서버 쪽 분석에서 혼란이 발생할 수 있습니다. [ForceMajorVersionToMinorPositionInUserAgent](/deployedge/microsoft-edge-policies#forcemajorversiontominorpositioninuseragent) 정책을 사용하여 User-Agent 문자열 주 버전을 99로 고정할지 여부를 제어할 수 있습니다. 또한 **#force-major-version-to-minor** 플래그는 *edge://flags*에서 사용할 수 있으므로 User-Agent 문자열의 주 버전을 99로 고정할 수 있습니다.

- **Microsoft 365 응용 프로그램 프로토콜 활성화 간소화.** 이제 신뢰할 수 있는 Microsoft 클라우드 저장소 서비스의 Microsoft 365 응용 프로그램 프로토콜 활성화가 SharePoint 하위 도메인 및 Microsoft OneDrive URL을 비롯한 특정 Microsoft 365 응용 프로그램을 직접 시작합니다. 원할 경우 [AutoLaunchProtocolsComponentEnabled](/deployedge/microsoft-edge-policies#autolaunchprotocolscomponentenabled) 및 [AutoLaunchProtocolsFromOrigins](/deployedge/microsoft-edge-policies#autolaunchprotocolsfromorigins) 정책을 사용하여 응용 프로그램 프로토콜 활성화 프롬프트를 사용하도록 설정하고, 경고를 사용하거나 사용하지 않도록 설정하는 다른 응용 프로그램 및 서비스를 정의할 수 있습니다.

- **하드웨어 적용 스택 보호** Microsoft Edge는 메모리 손상 취약점을 해결하고 간접 호출을 보호하여 보다 세분화된 보호를 계속 지원할 것입니다. 하드웨어 적용 스택 보호는 Windows 8 이상에서만 지원됩니다. 자세한 내용은 [하드웨어 적용 스택 보호](https://techcommunity.microsoft.com/t5/windows-kernel-internals-blog/developer-guidance-for-hardware-enforced-stack-protection/ba-p/2163340)를 참조하세요. 이 기능 동작은 [ShadowStackCrashRollbackBehavior](/deployedge/microsoft-edge-policies#shadowstackcrashrollbackbehavior) 정책을 사용하여 제어할 수 있습니다.

- **Microsoft Outlook 및 파일 탐색기에서 PDF 파일을 미리 봅니다.** 쉽고 풍부한 읽기 전용 미리 보기로 PDF 파일을 볼 수 있습니다. 이 기능은 Outlook 데스크톱 PDF 첨부 파일 또는 파일 탐색기를 사용하는 로컬 PDF 파일에 사용할 수 있습니다.

- **디지털 서명된 PDF 파일을 엽니다.** 디지털 서명은 문서의 신뢰성과 문서의 변경 내용에 대한 유효성을 검사하기 위해 광범위하게 사용됩니다. [PDFSecureMode](/deployedge/microsoft-edge-policies#pdfsecuremode) 정책을 사용하여 추가 기능 없이 브라우저에서 직접 PDF 파일에 대한 디지털 서명 유효성 검사를 사용하도록 설정할 수 있습니다.

### <a name="policy-updates"></a>정책 업데이트

#### <a name="new-policies"></a>새로운 정책

- [AdsTransparencyEnabled](/DeployEdge/microsoft-edge-policies#adstransparencyenabled) - 광고 투명도 기능을 사용할 수 있는지 구성
- [DefaultWebHidGuardSetting](/DeployEdge/microsoft-edge-policies#defaultwebhidguardsetting) - WebHID API의 사용 제어
- [HideRestoreDialogEnabled](/DeployEdge/microsoft-edge-policies#hiderestoredialogenabled) - 브라우저 충돌 후 복원 페이지 대화 상자 숨기기
- [PDFSecureMode](/DeployEdge/microsoft-edge-policies#pdfsecuremode) - 기본 PDF 판독기에서 보안 모드 및 인증서 기반 디지털 서명 유효성 검사
- [PromptOnMultipleMatchingCertificates](/DeployEdge/microsoft-edge-policies#promptonmultiplematchingcertificates) - 여러 인증서가 일치하는 경우 인증서를 선택하라는 메시지 표시
- [WebHidAskForUrls](/DeployEdge/microsoft-edge-policies#webhidaskforurls) - 이러한 사이트에서 WebHID API 허용
- [WebHidBlockedForUrls](/DeployEdge/microsoft-edge-policies#webhidblockedforurls) - 이러한 사이트에서 WebHID API 차단

#### <a name="deprecated-policy"></a>더 이상 사용되지 않는 정책

- [BackgroundTemplateListUpdatesEnabled](/DeployEdge/microsoft-edge-policies#backgroundtemplatelistupdatesenabled) - 서식 파일을 사용하는 컬렉션 및 기타 기능에 대해 사용 가능한 서식 파일 목록의 백그라운드 업데이트 사용

#### <a name="obsoleted-policy"></a>폐기된 정책

- [AllowSyncXHRInPageDismissal](/DeployEdge/microsoft-edge-policies#allowsyncxhrinpagedismissal) - 페이지를 해제하는 동안 페이지에서 동기 XHR 요청 전송 허용

## <a name="version-980110892-march-26"></a>버전 98.0.1108.92: 3월 26일

확장 안정 릴리스에 대한 다양한 버그 및 성능 문제를 해결했습니다.

## <a name="version-990115055-march-26"></a>버전 99.0.1150.55: 3월 26일

> [!Important]
> 이 업데이트에는 Chromium 팀에서 야생에서 악용되는 것으로 보고된 [CVE-2022-1096](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2022-1096)에 대한 수정 사항이 포함되어 있습니다. 자세한 내용은 [보안 업데이트 가이드](https://msrc.microsoft.com/update-guide)에서 참고하세요.

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#march-26-2022)에서 확인할 수 있습니다.

## <a name="version-990115052-march-24"></a>버전 99.0.1150.52: 3월 24일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-980110884-march-17"></a>버전 98.0.1108.84: 3월 17일

확장 안정 릴리스에 대한 다양한 버그 및 성능 문제를 해결했습니다.

## <a name="version-990115046-march-17"></a>버전 99.0.1150.46: 3월 17일

안정 채널 보안 업데이트는 [여기](/deployedge/microsoft-edge-relnotes-security#march-17-2022)에서 확인할 수 있습니다.

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

<!---- From Version 97.0.1072.55: January 6 to Version 96.0.1054.34: November 23 ---->
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
