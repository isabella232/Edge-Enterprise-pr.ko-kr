---
title: 베타 채널 용 Microsoft Edge 릴리스 정보
ms.author: leahtu
author: dan-wesley
manager: srugh
ms.date: 03/14/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 베타 채널 용 Microsoft Edge 릴리스 정보
ms.openlocfilehash: 8633a5f15fe737a64a0160de714c1c4e53541482
ms.sourcegitcommit: 556aca8dde42dd66364427f095e8e473b86651a0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2022
ms.locfileid: "12445712"
---
# <a name="release-notes-for-microsoft-edge-beta-channel"></a>Microsoft Edge 베타 채널에 대한 릴리스 정보

이 릴리스 정보는 Microsoft Edge 베타 채널에 포함된 새로운 기능 및 비보안 업데이트에 대한 정보를 제공합니다. 이러한 릴리스 정보의 보관된 버전은 채널에 대한 보관된 릴리스 [Microsoft Edge Beta 있습니다](./microsoft-edge-relnote-archive-beta-channel.md).

> [!NOTE]
> Microsoft Edge 웹 플랫폼은 사용자 환경, 보안 및 개인 정보 개선을 위해 지속적으로 진화하고 있습니다. 자세히 알아보려면 [Microsoft Edge에 적용될 사이트 호환성에 영향을 미치는 변경 사항](/microsoft-edge/web-platform/site-impacting-changes)을 참조하세요.

## <a name="version-990115039-march-10"></a>버전 99.0.1150.39: 3월 10일

### <a name="feature-updates"></a>기능 업데이트

- **IE 모드에 대한 클라우드 사이트 목록 관리 환경 개선** [InternetExplorerIntegrationCloudUserSitesReporting](/deployedge/microsoft-edge-policies#internetexplorerintegrationcloudusersitesreporting) 및 [InternetExplorerIntegrationCloudNeutralSitesReporting](/deployedge/microsoft-edge-policies#internetexplorerintegrationcloudneutralsitesreporting) 정책을 사용하여 사이트 피드백 보고를 구성하여 엔터프라이즈 사이트 목록의 간격을 식별합니다. Microsoft Edge 센터의 사이트 목록 환경에서 사용자의 로컬 사이트 목록 URL과 잘못 구성될 수 있는 중립 사이트 URL을 Microsoft 365 관리 있습니다. 자세한 내용은 View [site feedback on the Microsoft 365 관리 참조하세요](/deployedge/edge-ie-mode-cloud-site-list-mgmt#view-site-feedback-on-the-microsoft-365-admin-center-1).  **참고:** 제어된 기능 출시입니다. 이 기능이 없는 경우 롤아웃을 계속할 때 다시 확인해 봐야 합니다.

## <a name="version-990115030-march-2"></a>버전 99.0.1150.30: 3월 2일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-990115025-february-25"></a>버전 99.0.1150.25: 2월 25일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-990115021-february-22"></a>버전 99.0.1150.21: 2월 22일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-990115016-february-14"></a>버전 99.0.1150.16: 2월 14일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-990115011-february-9"></a>버전 99.0.1150.11: 2월 9일

### <a name="feature-updates"></a>기능 업데이트

- **사용자 에이전트 문자열의 예정된 3자리 버전 번호입니다.** 버전 100부터는 Microsoft Edge "Edg/100"와 같은 User-Agent 버전 번호가 전송됩니다. Microsoft Edge 97부터 사이트 소유자는 **#force-major-version-to-100** 실험 플래그를 사용하도록 설정하여 edge://flags User-Agent 구문 분석 논리가 강력하고 예상대로 작동하는지 확인하여 이 예정된 에이전트 ** 문자열을 테스트할 수 있습니다.

- **사이트에 대한 프로필 기본 설정을 사용하여 다중 프로필 환경을 개인 설정** 사용자는 다중 프로필 환경의 사용자 지정 목록에서 자동 프로필 전환을 위한 사이트 목록을 만들 수 Microsoft Edge.

- **IE 모드용 양방향 쿠키 공유.** 이 기능은 이미 사용 가능한 쿠키 공유 기능을 확장하며 사용자가 특정 세션 쿠키를 Internet Explorer/IE 모드와 동기화할 수 Microsoft Edge. 자세한 내용은 사용자와 사용자 간의 쿠키 [Microsoft Edge Internet Explorer](/deployedge/edge-ie-mode-add-guidance-cookieshare).

- **페이지 미리 보기를 사용하여 PDF 문서를 탐색합니다.** 이제 페이지를 나타내는 축소판 그림을 사용하여 PDF 문서를 탐색할 수 있습니다. 이러한 축소판 그림은 PDF 판독기 왼쪽 창에 표시됩니다.

- **저장 및 채우기용 암호 관리자 UI(사용자 인터페이스)를 사용하지 않도록 설정할 도메인 목록을 구성합니다.** [PasswordManagerBlocklist](/deployedge/microsoft-edge-policies#passwordmanagerblocklist) 정책을 사용하여 암호 관리자를 사용하지 않도록 설정해야 하는 도메인 목록(HTTP/HTTPS Microsoft Edge 호스트 이름만)을 구성합니다. 즉, 저장 및 채우기 워크플로가 사용되지 않도록 설정되어 해당 웹 사이트의 암호를 웹 양식에 저장하거나 자동으로 채울 수 없습니다.

- **API의 (Microsoft Edge 미리 보기에서)를 사용하여 추가 기능 저장소에 대한 확장을 업데이트합니다.** 이러한 API를 빌드 파이프라인에 직접 통합하고 패키지 업데이트를 추가 기능 웹 사이트에 Microsoft Edge 수 있습니다. 자세한 내용은 추가 기능 API Microsoft Edge(비공개 미리 보기에서)[를 참조합니다.](/microsoft-edge/extensions-chromium/publish/api/using-addons-api)

### <a name="policy-updates"></a>정책 업데이트

#### <a name="new-policies"></a>새 정책

- [AllowGamesMenu](/DeployEdge/microsoft-edge-policies#allowgamesmenu) - 사용자가 게임 메뉴에 액세스할 수 있도록 허용
- [DoNotSilentlyBlockProtocolsFromOrigins](/DeployEdge/microsoft-edge-policies#donotsilentlyblockprotocolsfromorigins) - 도우미 방지 보호로 자동으로 차단할 수 없는 프로토콜 목록 정의
- [HubsSidebarEnabled](/DeployEdge/microsoft-edge-policies#hubssidebarenabled) - 허브 사이드바 표시
- [InternetExplorerIntegrationCloudNeutralSitesReporting](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationcloudneutralsitesreporting) - M365 관리 센터 사이트 목록 앱에 대해 잘못 구성된 중립 사이트 URL에 대한 보고 구성
- [InternetExplorerIntegrationCloudUserSitesReporting](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationcloudusersitesreporting) - M365 관리 센터 사이트 목록 앱에 대한 IE 모드 사용자 목록 항목 보고 구성
- [PasswordManagerBlocklist](/DeployEdge/microsoft-edge-policies#passwordmanagerblocklist) - 암호 관리자 UI(저장 및 채우기)를 사용하지 않도록 설정할 도메인 목록을 구성합니다.
- [RelatedMatchesCloudServiceEnabled](/DeployEdge/microsoft-edge-policies#relatedmatchescloudserviceenabled) - 페이지에서 찾기에서 관련 일치 구성
- [SignInCtaOnNtpEnabled](/DeployEdge/microsoft-edge-policies#signinctaonntpenabled) - 로그인 클릭으로 작업 대화 상자 사용
- [UserAgentReduction](/DeployEdge/microsoft-edge-policies#useragentreduction) - 축소를 User-Agent 또는 사용하지 않도록 설정

## <a name="version-980110848-february-8"></a>버전 98.0.1108.48: 2월 8일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-980110843-february-3"></a>버전 98.0.1108.43: 2월 3일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-980110842-february-2"></a>버전 98.0.1108.42: 2월 2일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-980110839-january-31"></a>버전 98.0.1108.39: 1월 31일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-980110833-january-24"></a>버전 98.0.1108.33: 1월 24일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-980110827-january-19"></a>버전 98.0.1108.27: 1월 19일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-980110823-january-14"></a>버전 98.0.1108.23: 1월 14일

### <a name="feature-updates"></a>기능 업데이트

- **웹에서 보안을 강화합니다.** 브라우저의 Microsoft Edge 우선 순위가 높은 검색 모드로, 웹을 검색할 때 추가 보호 계층을 제공합니다. 관리자는 최종 사용자 데스크톱(Windows, macOS 및 Linux)에 다음 그룹 정책을 적용하여 제로 데이로부터 보호할 수 있습니다. 또한 이러한 정책을 통해 중요한 사이트 및 업무용 응용 프로그램이 예상대로 계속 작동하게 됩니다. 이 기능은 과거 추세에 따라 예상치 않은 활성 제로일을 완화할 수 있기 때문에 매우 큰 단계입니다. 이 기능을 설정하면 하드웨어 적용 스택 보호, ACG(임의 코드 보호) 및 CFG(Content Flow Guard)가 보안 완화를 지원하여 웹에서 사용자의 보안을 강화합니다.
그룹 정책:
  - [EnhanceSecurityMode](/DeployEdge/microsoft-edge-policies#enhancesecuritymode)
  - [EnhanceSecurityModeBypassListDomains](/DeployEdge/microsoft-edge-policies#enhancesecuritymodebypasslistdomains)
  - [EnhanceSecurityModeEnforceListDomains](/DeployEdge/microsoft-edge-policies#enhancesecuritymodeenforcelistdomains)

- **사용자 지정 기본 암호.** 브라우저에는 저장된 암호가 웹 양식에 자동으로 채워지기 전에 사용자가 인증 단계를 추가할 수 있는 기능이 이미 있습니다. 이렇게 하면 개인 정보 보호 계층이 추가되고 권한이 없는 사용자가 저장된 암호를 사용하여 웹 사이트에 로그온하는 것을 방지할 수 있습니다. 사용자 지정 기본 암호는 동일한 기능의 진화된 기능으로, 이제 사용자가 선택한 사용자 지정 문자열을 기본 암호로 사용할 수 있게 됩니다. 사용하도록 설정하면 사용자가 이 암호를 입력하여 인증을 하게 되고 저장된 암호가 웹 양식에 자동으로 채워집니다.

- **오버레이 스크롤 막대가 추가된 Microsoft Edge.** 스크롤 막대를 오버레이 기반 디자인으로 업데이트했습니다. 사용자는 2016년 8월 1일부로 설정하여 이 *기능을 edge://flags*.

### <a name="policy-updates"></a>정책 업데이트

#### <a name="new-policies"></a>새 정책

- [AddressBarEditingEnabled](/DeployEdge/microsoft-edge-policies#addressbareditingenabled) - 주소 표시줄 편집을 구성합니다.
- [EdgeFollowEnabled](/DeployEdge/microsoft-edge-policies#edgefollowenabled) - 서비스 팔로우를 Microsoft Edge.
- [EnhanceSecurityMode](/DeployEdge/microsoft-edge-policies#enhancesecuritymode) - 보안 상태를 Microsoft Edge.
- [EnhanceSecurityModeBypassListDomains](/DeployEdge/microsoft-edge-policies#enhancesecuritymodebypasslistdomains) - 보안 강화 모드를 적용하지 않을 도메인 목록을 구성합니다.
- [EnhanceSecurityModeEnforceListDomains](/DeployEdge/microsoft-edge-policies#enhancesecuritymodeenforcelistdomains) - 보안 강화 모드가 항상 적용될 도메인 목록을 구성합니다.
- [InAppSupportEnabled](/DeployEdge/microsoft-edge-policies#inappsupportenabled) - 앱 내 지원 사용.
- [MicrosoftEdgeInsiderPromotionEnabled](/DeployEdge/microsoft-edge-policies#microsoftedgeinsiderpromotionenabled) - Microsoft Edge 프로모션을 사용하도록 설정되어 있습니다.
- [PrintStickySettings](/DeployEdge/microsoft-edge-policies#printstickysettings) - 인쇄 미리 보기 고정 설정입니다.
- [SandboxExternalProtocolBlocked](/DeployEdge/microsoft-edge-policies#sandboxexternalprotocolblocked) - Microsoft Edge iframe에서 외부 프로토콜에 대한 탐색을 차단할 수 있도록 허용합니다.
- [U2fSecurityKeyApiEnabled](/DeployEdge/microsoft-edge-policies#u2fsecuritykeyapienabled) - 사용 불가능한 U2F 보안 키 API 사용을 허용합니다.

## <a name="version-970107254-january-5"></a>버전 97.0.1072.54: 1월 5일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-970107252-january-3"></a>버전 97.0.1072.52: 1월 3일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-970107241-december-20"></a>버전 97.0.1072.41: 12월 20일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-970107234-december-13"></a>버전 97.0.1072.34: 12월 13일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-970107228-december-8"></a>버전 97.0.1072.28: 12월 8일

다양한 버그와 성능 문제를 해결했습니다.

<!--- Version 97.0.1072.21: December 1 to Version 96.0.1054.13: November 5  --->
<!--- archive from Version 96.0.1054.8: November 1 to Version 95.0.1020.14: October 5  --->
<!-- archive from version 95.0.1020.9: September 28 to version 94.0.992.14: September 7 ---->
<!-- archive from Version 94.0.992.9: September 2 to Version 92.0.902.40: July 6 -->
<!--Archive on Oct 27 From Version 92.0.902.22: June 21 to Version 89.0.774.23: February 8  -->
<!--- Archived from Version 87.0.664.18: October 26 to to version 89.0.774.18: February 3 ---->
<!--- Archived from Version 87.0.664.12: October 20 to to version 86.0.622.15: September 14 ---->
<!--- Archived to version 86.0.622.11: September 9 ---->
<!--- Archived to version 85.0.564.18: July 28 ---->

## <a name="see-also"></a>참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)

