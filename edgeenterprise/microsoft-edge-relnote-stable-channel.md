---
title: 안정 채널에 대한 Microsoft Edge 릴리스 정보
ms.author: aguta
author: dan-wesley
manager: srugh
ms.date: 03/08/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 안정 채널에 대한 Microsoft Edge 릴리스 정보
ms.openlocfilehash: bdb38513f15e0ed5d11be4e221ea9d2403d1a956
ms.sourcegitcommit: 6d37cd6dc8618742f4729fc901fc66829dab462e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2021
ms.locfileid: "11406239"
---
# <a name="release-notes-for-microsoft-edge-stable-channel"></a>Microsoft Edge 안정 채널에 대한 릴리스 정보

이 릴리스 정보는 Microsoft Edge 안정 채널에 포함된 새로운 기능 및 비보안 업데이트에 대한 정보를 제공합니다.

- 모든 보안 업데이트는 [여기](microsoft-edge-relnotes-security.md)에서 확인할 수 있습니다.
- Microsoft Edge 안정 채널에 대한 보관된 릴리스 정보는 [여기](microsoft-edge-relnote-archive-stable-channel.md)에 있습니다.

 Microsoft Edge 채널을 이해하려면 [Microsoft Edge 채널 개요](microsoft-edge-channels.md)를 참조하세요.

> [!NOTE]
> 안정 채널의 업데이트는 하루 이상 점진적으로 배포됩니다. 자세한 내용은 [Microsoft Edge 업데이트 점진적 배포](microsoft-edge-update-progressive-rollout.md)를 참조하세요.

## <a name="version-89077450-march-10"></a>버전 89.0.774.50: 3월 10일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-89077448-march-8"></a>버전 89.0.774.48: 3월 8일

다양한 버그와 성능 문제를 해결했습니다.

<!-- begin major 89 -->
## <a name="version-89077445-march-4"></a>버전 89.0.774.45: 3월 4일

> [!IMPORTANT]
> 이 업데이트에는 [CVE-2021-21166](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21166)이 포함되어 있으며 Chromium 팀은 이 취약점이 악용된 것으로 보고했습니다. 자세한 내용은 [보안 업데이트 가이드](https://msrc.microsoft.com/update-guide)를 참조하세요.

안정 채널 보안 업데이트는 [여기](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#march-4-2021)에서 확인할 수 있습니다.

### <a name="resolved-issues"></a>해결된 문제

- **작업 표시줄 및 시작 메뉴 바로 가기 업데이트 및 수정 사항:**
  - 이제 시작 메뉴에서 Microsoft Edge 바로 가기를 마우스 오른쪽 단추로 클릭하면 고정된 경우 작업 표시줄에서 Microsoft Edge를 고정 해제하는 옵션이 제대로 표시됩니다.
  - Microsoft Edge를 작업 표시줄에 고정하는 [작업 표시줄 구성](https://docs.microsoft.com/windows/configuration/configure-windows-10-taskbar)이 포함된 시작 레이아웃은 두 번째 Microsoft Edge 바로 가기에서 더 이상 작업 표시줄을 고정하지 않습니다.
  - Windows 로밍 프로필을 사용하는 조직에서 사용자가 Windows에 로그온할 때 작업 표시줄의 Microsoft Edge 아이콘 대신 빈 흰색 아이콘이 더 이상 표시되지 않습니다.

### <a name="feature-updates"></a>기능 업데이트

- **키오스크 모드에서는 추가 잠금 기능을 사용할 수 있습니다**. Microsoft Edge 버전 89부터는 고객이 생산성과 보안이 강화된 환경에서 작업을 완료할 수 있도록 키오스크 모드에 추가 잠금 모드가 추가되었습니다. [자세한 내용을 알아보세요](microsoft-edge-configure-kiosk-mode.md#kiosk-mode-supported-features).

- **Enterprise Mode Site List Manager 도구는 *edge://compat* 페이지**를 통해 브라우저에서 사용 가능합니다. 이 도구를 사용하여 Microsoft Edge에서 Internet Explorer 모드에 대한 사이트 목록 XML을 만들고 편집하고 내보낼 수 있습니다. 그룹 정책을 통해 필요한 경우 이 도구에 대한 액세스를 사용하도록 설정할 수 있습니다. [자세한 내용을 알아보세요](https://docs.microsoft.com/deployedge/edge-ie-mode-site-list-manager).

- **절전 모드 탭을 사용하여 브라우저 성능을 향상합니다**. 절전 모드 탭은 활성 탭이나 다른 응용 프로그램에서 사용할 수 있도록 메모리 및 CPU와 같은 시스템 리소스를 확보하기 위해 비활성 탭을 절전 모드로 전환하여 브라우저 성능을 향상시킵니다. 사용자는 사이트가 절전 모드로 전환되는 것을 방지하고 비활성 탭이 절전 모드로 전환될 때까지의 시간을 구성할 수 있습니다. 사용자를 흐름에서 유지시키기 위해 인트라넷 사이트와 같은 특정 사이트가 절전 모드로 전환되는 것을 방지하는 [추론](https://techcommunity.microsoft.com/t5/articles/sleeping-tabs-faq/m-p/1705434)도 있습니다. 이 기능은 그룹 정책을 통해 관리할 수 있습니다.

- **클라우드에서 Microsoft Edge 동기화 데이터를 수동으로 다시 설정하세요**. 제품 내에서 Microsoft Edge 동기화 데이터를 다시 설정하는 방법이 도입되었습니다. 이 방법을 사용하면 Microsoft 서비스에서 데이터를 확실히 지우고, 이전에는 지원 티켓이 필요했던 특정 제품 문제를 해결할 수 있습니다.

- **모든 Windows Azure Active Directory(Azure AD) 계정에 대해 SSO(Single Sign-On)를 지능적으로 사용하도록 설정하면 Azure AD Microsoft Edge이 아닌 단일 프로필이 있는 사용자에게 적용됩니다.**  이 기능에서 가장 많은 혜택을 받을 수 있는 사용자에 대해 이 설정을 자동으로 켜면 됩니다. 사용자가 하나의 Microsoft Edge 프로파일(Azure AD 또는 Kids Mode가 아닌 경우)만 있으면 Microsoft Edge가 실행될 때 설정이 자동으로 설정됩니다. 사용자가 나중에 Azure AD 계정으로 다른 Microsoft Edge 프로필에 로그인하도록 선택하는 경우 이 자동 토글도 자동으로 해제됩니다. 사용자는 **설정 > 프로필 환경설정 > 프로필 환경설정 > 이 프로필을 사용하여 직장 또는 학교 사이트에 대한 단일 로그온 허용**에서 이 기능에 대한 환경설정을 수동으로 업데이트할 수 있습니다.

- **PDF 문서 내의 텍스트 선택 환경이 개선됩니다**. Microsoft Edge 버전 89 이상에서 연 PDF 문서 전반에서 더욱 원활하고 일관성 있는 텍스트 선택 환경이 제공됩니다.

- **이제 자동 채우기에서 생년월일 필드가 지원됩니다.** 오늘날 Microsoft Edge는 양식을 작성하거나 계정을 만들 때 주소, 이름, 전화번호 등 데이터를 자동으로 채워 사용자의 시간을 절약하고 수고를 덜어줍니다. Microsoft Edge 버전 89부터는 생년월일도 저장해서 자동 채우기 기능을 사용하실 수 있습니다. 프로필 설정에서 언제든지 이 정보를 보고 편집하고 삭제할 수 있습니다.

### <a name="policy-updates"></a>정책 업데이트

#### <a name="new-policies"></a>새로운 정책

새 정책 7개를 추가했습니다. [Microsoft Edge Enterprise 랜딩 페이지](https://www.microsoft.com/edge/business/download)에서 업데이트된 관리 템플릿을 다운로드합니다. 다음과 같은 새 정책이 추가되었습니다.

- [BrowsingDataLifetime](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#browsingdatalifetime) - 데이터 수명 설정 검색
- [MAMEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#mamenabled) - 모바일 앱 관리 사용
- [DefinePreferredLanguages](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#definepreferredlanguages) - 사이트에서 언어를 지원하는 경우 웹 사이트에서 표시할 기본 설정 언어의 순서가 정해진 목록 정의
- [ShowRecommendationsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#showrecommendationsenabled) - Edge에서 추천 및 홍보 알림 허용
- [PrintingAllowedBackgroundGraphicsModes](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#printingallowedbackgroundgraphicsmodes) - 배경 그래픽 인쇄 모드 제한
- [PrintingBackgroundGraphicsDefault](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#printingbackgroundgraphicsdefault) - 기본 배경 그래픽 인쇄 모드
- [SmartActionsBlockList](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#smartactionsblocklist) - 서비스 목록에 대한 스마트 작업 차단

#### <a name="obsoleted-policies"></a>폐기된 정책

다음 정책은 사용되지 않습니다.

- [ForceLegacyDefaultReferrerPolicy](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#forcelegacydefaultreferrerpolicy) - no-referrer-when-downgrade의 기본 참조자 정책 사용
- [MetricsReportingEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#metricsreportingenabled) - 사용 현황 및 크래시 관련 데이터 보고 사용
- [SendSiteInfoToImproveServices](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sendsiteinfotoimproveservices) - Microsoft 서비스를 개선하기 위해 사이트 정보 보내기
<!-- end major 89 -->
## <a name="version-88070581-february-25"></a>버전 88.0.705.81: 2월 25일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-88070574-february-17"></a>버전 88.0.705.74: 2월 17일

안정 채널 보안 업데이트는 [여기](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#February-17-2021)에서 확인할 수 있습니다.

## <a name="version-88070568-february-11"></a>버전 88.0.705.68: 2월 11일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-88070563-february-5"></a>버전 88.0.705.63: 2월 5일

> [!IMPORTANT]
> 이 업데이트에는 [CVE-2021-21148](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21148)이 포함되어 있으며 Chromium 팀은 이 취약점이 악용된 것으로 보고했습니다.

안정 채널 보안 업데이트는 [여기](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#February-5-2021)에서 확인할 수 있습니다.

## <a name="version-88070562-february-4"></a>버전 88.0.705.62: 2월 4일

안정 채널 보안 업데이트는 [여기](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#February-4-2021)에서 확인할 수 있습니다.

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-88070556-january-28"></a>버전 88.0.705.56: 1월 28일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-88070553-january-26"></a>버전 88.0.705.53: 1월 26일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-88070550-january-21"></a>버전 88.0.705.50: 1월 21일

안정 채널 보안 업데이트는 [여기](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#january-21-2021)에서 확인할 수 있습니다.

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

- **세션을 종료하기 위한 키오스크 모드 옵션입니다**. 이제 "세션 종료" 단추를 키오스크 모드 공개 검색 환경에서 사용할 수 있습니다. 이 기능을 사용하면 Microsoft Edge를 닫을 때 브라우저 데이터 및 설정이 삭제됩니다. 키오스크 모드 기능 및 로드맵, [Microsoft Edge 키오스크 모드 구성](https://docs.microsoft.com/deployedge/microsoft-edge-configure-kiosk-mode)에 대해 자세히 알아보세요요.

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

- [BasicAuthOverHttpEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#basicauthoverhttpenabled) - HTTP에 대해 기본 인증을 허용합니다.
- [BlockExternalExtensions](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#blockexternalextensions) - 외부 확장이 설치되지 않도록 차단합니다.
- [InternetExplorerIntegrationLocalFileAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#internetexplorerintegrationlocalfileallowed) - Internet Explorer 모드에서 로컬 파일 시작을 허용합니다.
- [InternetExplorerIntegrationLocalFileExtensionAllowList](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#internetexplorerintegrationlocalfileextensionallowlist) - Internet Explorer 모드 파일 확장명 허용 목록에서 로컬 파일을 엽니다.
- [InternetExplorerIntegrationLocalFileShowContextMenu](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#internetexplorerintegrationlocalfileshowcontextmenu) - Internet Explorer 모드에서 링크를 열려면 상황에 맞는 메뉴를 표시합니다.
- [IntranetRedirectBehavior](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#intranetredirectbehavior) - 인트라넷 리디렉션 동작입니다.
- [PrinterTypeDenyList](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#printertypedenylist) - 거부 목록에서 프린터 유형을 사용하지 않도록 설정합니다.
- [ShowMicrosoftRewards](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#showmicrosoftrewards) - Microsoft Rewards 환경을 표시합니다.
- [SleepingTabsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sleepingtabsenabled) - 절전 모드 탭을 구성합니다.
- [SleepingTabsTimeout](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sleepingtabstimeout) - 절전 모드 탭에 대한 백그라운드 탭 비활성 시간 제한을 설정합니다.
- [SleepingTabsBlockedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sleepingtabsblockedforurls) - 특정 사이트에서 절전 모드 탭을 차단합니다.
- [StartupBoostEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#startupboostenabled) - 시작 부스트를 사용하도록 설정합니다.
- [TargetBlankImpliesNoOpener](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#targetblankimpliesnoopener) - _blank를 대상으로 하는 링크에 대해 window.opener를 설정하지 않습니다.
- [UpdatePolicyOverride](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#updatepolicyoverride) - Microsoft Edge 업데이트가 Microsoft Edge에서 사용 가능한 업데이트를 처리하는 방법을 지정합니다.
- [VerticalTabsAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#verticaltabsallowed) - 브라우저 측면의 탭에 대한 세로 레이아웃의 가용성을 구성합니다.
- [WebRtcAllowLegacyTLSProtocols](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webrtcallowlegacytlsprotocols) - WebRTC에서 레거시 TLS/DTLS 다운그레이드를 허용합니다.
- [WebWidgetAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webwidgetallowed) - 웹 위젯을 사용하도록 설정합니다.
- [WebWidgetIsEnabledOnStartup](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webwidgetisenabledonstartup) - Windows 시작 시 웹 위젯을 허용합니다.

#### <a name="deprecated-policies"></a>사용되지 않는 정책

- [ProactiveAuthEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proactiveauthenabled) - 사전 인증을 사용하도록 설정합니다.
- [ProxyBypassList](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxybypasslist) - 프록시 우회 규칙을 구성합니다.
- [ProxyMode](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxymode) - 프록시 서버 설정을 구성합니다.
- [ProxyPacUrl](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxypacurl) - 프록시 .pac 파일 URL을 설정합니다.
- [ProxyServer](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxyserver) - 프록시 서버의 주소 또는 URL을 구성합니다.
- [WebDriverOverridesIncompatiblePolicies](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webdriveroverridesincompatiblepolicies) - WebDriver가 호환되지 않는 정책을 재정의할 수 있도록 허용합니다.

### <a name="obsoleted-policies"></a>폐기된 정책

- [AllowPopupsDuringPageUnload](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#allowpopupsduringpageunload) - 페이지가 언로드하는 동안 팝업을 표시하도록 허용합니다.
- [DefaultPluginsSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultpluginssetting) - 기본 Adobe Flash 설정입니다.
- [PluginsAllowedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#pluginsallowedforurls) - 특정 사이트에서 Adobe Flash 플러그 인을 허용합니다.
- [PluginsBlockedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#pluginsblockedforurls) - 특정 사이트에서 Adobe Flash 플러그 인을 차단합니다.
- [RunAllFlashInAllowMode](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#runallflashinallowmode) - Adobe Flash 콘텐츠 설정을 모든 콘텐츠로 확장합니다.
<!--- end major 88  --->
## <a name="version-87066475-january-7"></a>버전 87.0.664.75: 1월 7일

안정 채널 보안 업데이트는 [여기](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#january-7-2021)에서 확인할 수 있습니다.

## <a name="version-87066466-december-17"></a>버전 87.0.664.66: 12월 17일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-87066460-december-10"></a>버전 87.0.664.60: 12월 10일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-87066457-december-7"></a>버전 87.0.664.57: 12월 7일

다양한 버그와 성능 문제를 해결했습니다. 안정 채널 보안 업데이트는 [여기](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#december-7-2020)에서 확인할 수 있습니다.

## <a name="version-87066455-december-3"></a>버전 87.0.664.55: 12월 3일

다양한 버그와 성능 문제를 해결했습니다. 이 릴리스에서는 다음 기능이 업데이트되었습니다.

- **기본적으로 쇼핑은 사용하도록 설정되어 있습니다**. Microsoft Edge 버전 87부터 시작하여, 엔터프라이즈 사용자는 Microsoft Edge에서 쇼핑 기능의 혜택을 누릴 수 있습니다. Microsoft Edge는 쇼핑 기능을 통해 사용자가 온라인으로 쇼핑을 하는 동안 쿠폰 및 더 나은 가격을 찾을 수 있도록 도와줍니다. (이 쿠폰 체험은 Stable 버전 87.0.664.41로 출시되었습니다). 이제 이 업데이트를 통해 가격 비교 환경을 이용할 수 있습니다. 이 기능은 [EdgeShoppingAssistantEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#edgeshoppingassistantenabled) 정책을 사용하여 구성할 수 있습니다. Microsoft 쇼핑에 대한 정보는 [블로그](https://blogs.windows.com/windowsexperience/2020/11/19/finish-up-that-holiday-shopping-with-new-features-from-microsoft-edge-and-bing/) 및 [자세한 정보](https://docs.microsoft.com/microsoft-edge/privacy-whitepaper#shopping)를 참조하세요.

## <a name="version-87066452-november-30"></a>버전 87.0.664.52: 11월 30일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-87066447-november-23"></a>버전 87.0.664.47: 11월 23일

다양한 버그와 성능 문제를 해결했습니다.

<!-- begin major 87 --->
## <a name="version-87066441-november-19"></a>버전 87.0.664.41: 11월 19일

안정 채널 보안 업데이트는 [여기](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#november-19-2020)에서 확인할 수 있습니다.

### <a name="feature-updates"></a>기능 업데이트

- **Internet Explorer에서 Microsoft Edge로 호환되지 않는 사이트에 대해 자동으로 리디렉션**됩니다. Microsoft Edge 87 안정 업데이트부터 시작하여 Internet Explorer에 비호환성 메시지를 표시하는 공용 웹 사이트는 자동으로 Microsoft Edge로 리디렉션됩니다. 자세한 내용을 알아보고 이 환경을 구성하려면 [호환되지 않는 사이트 리디렉션](https://docs.microsoft.com/deployedge/edge-learnmore-neededge)을 참조하세요.

- **키오스크 모드 개인 정보 보호 기능이 사용으로 설정되었습니다**. Microsoft Edge 버전 87부터 시작하여 사용자 데이터의 개인 정보 보호와 관련하여 기업에 도움이 되는 키오스크 모드 기능이 사용으로 설정됩니다. 이 기능을 사용하면 종료 시 사용자 데이터를 지우고 다운로드한 파일을 삭제하고 지정된 유휴 시간 후에 구성된 시작 환경을 재설정하는 등의 작업을 수행할 수 있습니다. [Microsoft Edge 키오스크 모드를 구성](https://docs.microsoft.com/deployedge/microsoft-edge-configure-kiosk-mode)하는 방법에 대해 자세히 알아보기

- **장바구니 기능은 기본적으로 사용하도록 설정**됩니다. Microsoft Edge 버전 87부터 시작하여, 엔터프라이즈 사용자는 Edge에서 쇼핑 기능의 혜택을 누릴 수 있습니다. Microsoft Edge는 쇼핑 기능을 통해 사용자가 온라인으로 쇼핑을 하는 동안 쿠폰 및 더 나은 가격을 찾을 수 있도록 도와줍니다. 이 업데이트로 쿠폰 환경을 사용할 수 있으며, 가격 비교는 향후 Microsoft Edge 87에 예정된 업데이트에서 릴리스될 예정입니다. 이 기능은 [EdgeShoppingAssistantEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#edgeshoppingassistantenabled) 정책을 통해 구성할 수 있습니다. [블로그](https://blogs.windows.com/windowsexperience/2020/11/19/finish-up-that-holiday-shopping-with-new-features-from-microsoft-edge-and-bing/)를 참조하고 Microsoft 쇼핑에 대해 [자세히 알아보세요](https://docs.microsoft.com/microsoft-edge/privacy-whitepaper#shopping).

- **ClickOnce 배포는 기본적으로 사용하도록 설정됩니다**. ClickOnce는 기본적으로 Microsoft Edge 87에서 사용할 수 있습니다. 이로 인해 기업이 소프트웨어를 배포하고 Microsoft Edge 레거시 브라우저 동작에 더 잘 부합할 수 있도록 장벽을 낮출 수 있습니다. Microsoft Edge 87에서 시작하는 ClickOnceEnabled 정책의 "구성되지 않음" 상태는 새 기본 ClickOnce 상태인 사용 허용(이전 기본 상태인 사용 안 함과 비교)을 반영합니다.

- **엔터프라이즈 새 탭 페이지(NTP)는 생산성을 사용자 지정, 작업 관련 피드 콘텐츠로 통합합니다**. 엔터프라이즈 NTP는 회사 또는 학교 계정으로 로그인한 사용자에게 Microsoft에서 제공하는 Office 365 생산성 페이지를 단일 페이지에서 조직되고 맞춤화된 작업 관련 회사 및 업계 피드와 혼합합니다. 사용자는 익숙한 Office 365 콘텐츠 및 Bing에서 제공하는 비즈니스용 Microsoft Search를 인식할 수 있습니다. 또한 조직의 사용 가능한 콘텐츠 및 모듈에서 가장 관련성이 높은 콘텐츠를 선택하여 "내 피드"를 쉽게 사용자 지정할 수 있습니다. IT 관리자는 Microsoft 365 관리 센터로 이동하여 Edge 새 탭 페이지에 대해 선택된 업계를 포함하여 조직의 뉴스 피드 설정을 제어할 수 있습니다. [자세히 알아보기](https://blogs.windows.com/msedgedev/2020/10/29/enterprise-new-tab-page-my-feed/)

- **개인 정보 보호 및 보안:**

  - 정책 구성 사이트에 대한 TLS 토큰 바인딩을 지원합니다. TLS 토큰 바인딩은 토큰 절도 공격을 방지하여 쿠키를 처음 설정했던 장치 외의 다른 장치에서 사용할 수 없도록 하는 데 도움이 됩니다. TLS 토큰 바인딩을 사용하려면 [AllowTokenBindingForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowtokenbindingforurls) 정책을 설정하고 목록의 사이트가 이 기능을 지원해야 합니다.

- **키보드는 PDF 파일의 형광펜을 지원합니다**. 사용자는 키보드 키를 사용하여 PDF에서 텍스트를 강조 표시할 수 있습니다.

- **인쇄:**

  - 양면 인쇄 시 어느 쪽으로 대칭 이동할 것인지 선택합니다. 양면 인쇄 시 사용자는 용지의 긴 면이나 짧은 면으로 대칭 이동할 수 있습니다.
  - 엔터프라이즈에 대한 인쇄 래스터화 모드를 선택합니다. Windows에서 포스트스크립트가 아닌 프린터에 대해 Microsoft Edge의 인쇄 방식을 제어합니다. 포스트스크립트가 아닌 프린터의 인쇄 작업에서 올바르게 인쇄하려면 래스터화를 진행해야 하는 경우가 있습니다. 인쇄 옵션은 "전체" 및 "빠르게"입니다.

### <a name="policy-updates"></a>정책 업데이트

#### <a name="new-policies"></a>새로운 정책

10개의 새 정책을 추가했습니다. [Microsoft Edge Enterprise 랜딩 페이지](https://www.microsoft.com/edge/business/download)에서 업데이트된 관리 템플릿을 다운로드합니다. 다음과 같은 새 정책이 추가되었습니다.

- [ConfigureFriendlyURLFormat](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#configurefriendlyurlformat) - Microsoft Edge에서 복사된 URL의 기본 붙여넣기 서식을 구성하고 추가 서식을 사용자에게 제공할 것인지 여부를 결정합니다.
- [EdgeShoppingAssistantEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#edgeshoppingassistantenabled) - Microsoft Edge에서 쇼핑을 사용하도록 설정합니다.
- [HideInternetExplorerRedirectUXForIncompatibleSitesEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#hideinternetexplorerredirectuxforincompatiblesitesenabled) - Microsoft Edge에서 일회성 리디렉션 대화 상자 및 배너를 숨깁니다.
- [KioskAddressBarEditingEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskaddressbareditingenabled) - 키오스크 모드 공개 검색 환경에 대해 주소 표시줄 편집을 구성합니다.
- [KioskDeleteDownloadsOnExit](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskdeletedownloadsonexit) - Microsoft Edge가 닫히는 경우, 키오스크 세션의 일부로 다운로드된 파일을 삭제합니다.
- [PasswordRevealEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#passwordrevealenabled) - 암호 노출 단추를 사용하도록 설정합니다.
- [RedirectSitesFromInternetExplorerPreventBHOInstall](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#redirectsitesfrominternetexplorerpreventbhoinstall) - Internet Explorer에서 Microsoft Edge로 호환되지 않는 사이트를 리디렉션하는 BHO(브라우저 도우미 개체) 설치를 방지합니다.
- [RedirectSitesFromInternetExplorerRedirectMode](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#redirectsitesfrominternetexplorerredirectmode) - Internet Explorer에서 Microsoft Edge로 호환되지 않는 사이트를 리디렉션합니다.
- [SpeechRecognitionEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#speechrecognitionenabled) - 음성 인식을 구성합니다.
- [WebCaptureEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webcaptureenabled) - Microsoft Edge에서 웹 캡처 기능을 사용으로 설정합니다.

#### <a name="deprecated-policy"></a>더 이상 사용되지 않는 정책

[NewTabPageSetFeedType](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#newtabpagesetfeedtype) - Microsoft Edge 새 탭 페이지 환경을 구성합니다.

#### <a name="obsoleted-policy"></a>폐기된 정책

[EnableDeprecatedWebPlatformFeatures](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#enabledeprecatedwebplatformfeatures) - 제한된 시간 동안 사용되지 않는 웹 플랫폼 기능을 다시 사용하도록 설정합니다.

<!-- end major 87 -->

## <a name="version-86062269-november-13"></a>버전 86.0.622.69: 11월 13일

> [!IMPORTANT]
> 이 업데이트에는 [CVE-2020-16013](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-16013) 및 [CVE-2020-16017](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-16017)이 포함되어 있으며 Chromium 팀은 이 취약점이 악용된 것으로 보고했습니다.

안정 채널 보안 업데이트는 [여기](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#november-13-2020)에서 확인할 수 있습니다.

## <a name="version-86062268-november-11"></a>버전 86.0.622.68: 11월 11일

안정 채널 보안 업데이트는 [여기](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#november-11-2020)에서 확인할 수 있습니다

## <a name="version-86062263-november-4"></a>버전 86.0.622.63: 11월 4일

> [!IMPORTANT]
> 이 업데이트에는 [CVE-2020-16009](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-16009)가 포함되어 있으며 Chromium 팀은 이 취약점이 악용된 것으로 보고했습니다.

안정 채널 보안 업데이트는 [여기](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#november-4-2020)에서 확인할 수 있습니다.

## <a name="version-86062261-november-2"></a>버전 86.0.622.61: 11월 2일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-86062258-october-29"></a>버전 86.0.622.58: 10월 29일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-86062256-october-27"></a>버전 86.0.622.56: 10월 27일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-86062251-october-22"></a>버전 86.0.622.51: 10월 22일

안정 채널 보안 업데이트는 [여기](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#october-22-2020)에서 확인할 수 있습니다

## <a name="version-86062248-october-20"></a>버전 86.0.622.48: 10월 20일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-86062243-october-15"></a>버전 86.0.622.43: 10월 15일

다양한 버그와 성능 문제를 해결했습니다.

<!-- Archive from 86.0.622.38-october-9 to beta 86.0.62.215-september-14  ->
<!-- Archived to version 84.0.522.40: July 16 -->

## <a name="see-also"></a>참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
