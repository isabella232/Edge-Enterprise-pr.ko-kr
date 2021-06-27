---
title: 안정 채널에 대한 Microsoft Edge 릴리스 정보
ms.author: aguta
author: AndreaLBarr
manager: srugh
ms.date: 06/24/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 안정 채널에 대한 Microsoft Edge 릴리스 정보
ms.openlocfilehash: ef059624339f4b50b92fb187023991ae0526afa7
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2021
ms.locfileid: "11617948"
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

- **키오스크 모드에서는 추가 잠금 기능을 사용할 수 있습니다**. Microsoft Edge 버전 89부터는 고객이 생산성과 보안이 강화된 환경에서 작업을 완료할 수 있도록 키오스크 모드에 추가 잠금 모드가 추가되었습니다. [자세한 내용을 알아보세요](microsoft-edge-configure-kiosk-mode.md#kiosk-mode-supported-features).

- **Enterprise Mode Site List Manager 도구는 *edge://compat* 페이지**를 통해 브라우저에서 사용 가능합니다. 이 도구를 사용하여 Microsoft Edge에서 Internet Explorer 모드에 대한 사이트 목록 XML을 만들고 편집하고 내보낼 수 있습니다. 그룹 정책을 통해 필요한 경우 이 도구에 대한 액세스를 사용하도록 설정할 수 있습니다. [자세한 내용을 알아보세요](./edge-ie-mode-site-list-manager.md).

- **절전 모드 탭을 사용하여 브라우저 성능을 향상합니다**. 절전 모드 탭은 활성 탭이나 다른 응용 프로그램에서 사용할 수 있도록 메모리 및 CPU와 같은 시스템 리소스를 확보하기 위해 비활성 탭을 절전 모드로 전환하여 브라우저 성능을 향상시킵니다. 사용자는 사이트가 절전 모드로 전환되는 것을 방지하고 비활성 탭이 절전 모드로 전환될 때까지의 시간을 구성할 수 있습니다. 사용자를 흐름에서 유지시키기 위해 인트라넷 사이트와 같은 특정 사이트가 절전 모드로 전환되는 것을 방지하는 [추론](https://techcommunity.microsoft.com/t5/articles/sleeping-tabs-faq/m-p/1705434)도 있습니다. 이 기능은 그룹 정책을 통해 관리할 수 있습니다.

- **클라우드에서 Microsoft Edge 동기화 데이터를 수동으로 다시 설정하세요**. 제품 내에서 Microsoft Edge 동기화 데이터를 다시 설정하는 방법이 도입되었습니다. 이 방법을 사용하면 Microsoft 서비스에서 데이터를 확실히 지우고, 이전에는 지원 티켓이 필요했던 특정 제품 문제를 해결할 수 있습니다.

- **모든 Windows Azure Active Directory(Azure AD) 계정에 대해 SSO(Single Sign-On)를 지능적으로 사용하도록 설정하면 Azure AD Microsoft Edge이 아닌 단일 프로필이 있는 사용자에게 적용됩니다.**  이 기능에서 가장 많은 혜택을 받을 수 있는 사용자에 대해 이 설정을 자동으로 켜면 됩니다. 사용자가 하나의 Microsoft Edge 프로파일(Azure AD 또는 Kids Mode가 아닌 경우)만 있으면 Microsoft Edge가 실행될 때 설정이 자동으로 설정됩니다. 사용자가 나중에 Azure AD 계정으로 다른 Microsoft Edge 프로필에 로그인하도록 선택하는 경우 이 자동 토글도 자동으로 해제됩니다. 사용자는 **설정 > 프로필 환경설정 > 프로필 환경설정 > 이 프로필을 사용하여 직장 또는 학교 사이트에 대한 단일 로그온 허용**에서 이 기능에 대한 환경설정을 수동으로 업데이트할 수 있습니다.

- **PDF 문서 내의 텍스트 선택 환경이 개선됩니다**. Microsoft Edge 버전 89 이상에서 연 PDF 문서 전반에서 더욱 원활하고 일관성 있는 텍스트 선택 환경이 제공됩니다.

- **이제 자동 채우기에서 생년월일 필드가 지원됩니다.** 오늘날 Microsoft Edge는 양식을 작성하거나 계정을 만들 때 주소, 이름, 전화번호 등 데이터를 자동으로 채워 사용자의 시간을 절약하고 수고를 덜어줍니다. Microsoft Edge 버전 89부터는 생년월일도 저장해서 자동 채우기 기능을 사용하실 수 있습니다. 프로필 설정에서 언제든지 이 정보를 보고 편집하고 삭제할 수 있습니다.

### <a name="policy-updates"></a>정책 업데이트

#### <a name="new-policies"></a>새로운 정책

새 정책 7개를 추가했습니다. [Microsoft Edge Enterprise 랜딩 페이지](https://www.microsoft.com/edge/business/download)에서 업데이트된 관리 템플릿을 다운로드합니다. 다음과 같은 새 정책이 추가되었습니다.

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

<!-- Archive from 86.0.622.43: October 15 to beta 88.0.705.81: February 25  ->
<!-- Archive from 86.0.622.38-october-9 to beta 86.0.62.215-september-14  ->
<!-- Archived to version 84.0.522.40: July 16 -->

## <a name="see-also"></a>참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)