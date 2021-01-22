---
title: 베타 채널 용 Microsoft Edge 릴리스 정보
ms.author: aguta
author: dan-wesley
manager: srugh
ms.date: 01/20/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 베타 채널 용 Microsoft Edge 릴리스 정보
ms.openlocfilehash: c1d0b7091655d5ca0893ea11cc0c2fc44bb516dd
ms.sourcegitcommit: a6c58b19976c194299be217c58b9a99b48756fd0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11281007"
---
# Microsoft Edge 베타 채널에 대한 릴리스 정보

이 릴리스 정보는 Microsoft Edge 베타 채널에 포함된 새로운 기능 및 비보안 업데이트에 대한 정보를 제공합니다. 이 릴리스 정보의 보관된 버전은 [여기](microsoft-edge-relnote-archive-beta-channel.md)에서 볼 수 있습니다.

## 버전 88.0.705.49: 1월 20일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 88.0.705.45: 1월 15일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 88.0.705.41: 1월 11일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 88.0.705.29: 12월 21일

다양한 버그와 성능 문제를 해결했습니다.

<!-- begin major 88 -->
## 버전 88.0.705.18: 12월 9일

### 기능 업데이트

- **지원 중단:**

  - FTP 프로토콜을 더 이상 지원하지 않습니다. 레거시 FTP 프로토콜에 대한 지원이 Microsoft Edge에서 제거되었습니다. FTP 링크로 이동하려고 하면 브라우저가 운영 체제에서 FTP 링크를 처리하기 위해 외부 응용 프로그램을 열도록 지시합니다. 또는 IT 관리자가 FTP 프로토콜을 사용하는 사이트에 대해 IE 모드를 사용하도록 Microsoft Edge를 구성할 수 있습니다.
  - Adobe Flash 지원이 제거됩니다. Microsoft Edge 베타 버전 88부터 Adobe Flash 기능과 지원이 제거됩니다. 자세한 정보: [Adobe Flash Player 지원 종료 시 업데이트 - Microsoft Edge 블로그(windows.com)](https://blogs.windows.com/msedgedev/2020/09/04/update-adobe-flash-end-support/)

- **인증:**

  - 이제 macOS 및 하위 수준 Windows에서 Azure AD(Azure Active Directory) 계정 및 MSA(Microsoft 계정)에 SSO(Single Sign On)를 사용할 수 있습니다. 이제 macOS 또는 하위 수준의 Microsoft Windows(7, 8.1)에서 Microsoft Edge에 로그인한 사용자는 회사 및 Microsoft 계정(예: bing.com, office.com, msn.com, outlook.com)으로 Single Sign-On을 허용하도록 구성된 웹 사이트에 자동으로 로그인됩니다.<br>참고: 사용자는 이 기능을 활용하기 위해 Microsoft Edge 88 이전 버전에서 Microsoft Edge에 로그인한 경우, 로그아웃한 후 다시 로그인해야 할 수 있습니다.
  - macOS 사용자를 자신의 회사 계정으로 인증하는 사이트의 회사 프로필로 자동 전환합니다. Microsoft Edge 버전 88부터 macOS에서 사용자의 회사 프로필로 인증하는 사이트를 전환하는 기능을 제공합니다.<br>참고: 사용자는 이 기능을 활용하기 위해 Microsoft Edge 88 이전 버전에서 Microsoft Edge에 로그인한 경우, 로그아웃한 후 다시 로그인해야 할 수 있습니다.

- 세션을 종료하는 키오스크 모드 옵션입니다. 이제 "세션 종료" 단추를 키오스크 모드 공개 검색 환경에서 사용할 수 있습니다. 이 기능을 사용하면 Microsoft Edge를 닫을 때 브라우저 데이터 및 설정이 삭제됩니다. 키오스크 모드 기능 및 로드맵, [Microsoft Edge 키오스크 모드 구성](https://docs.microsoft.com/deployedge/microsoft-edge-configure-kiosk-mode)에 대해 자세히 알아보세요요.

- **보안 및 개인 정보:**

  - 온라인 유출에서 사용자의 암호가 발견되면 경고가 생성됩니다. 사용자 암호는 알려진 위반된 자격 증명의 리포지토리와 대조하여 일치하는 것이 발견되는 경우 사용자에게 경고를 보냅니다. 보안 및 개인 정보 보호를 위해 사용자 암호는 유출된 자격 증명의 데이터베이스와 대조할 때 해시 및 암호화됩니다.
  - 혼합 콘텐츠를 자동으로 업그레이드합니다. HTTPS를 통해 전달되는 보안 페이지에는 비보안 HTTP를 통해 제공되는 참조 이미지를 포함할 수 있습니다. Microsoft Edge 88에서 개인 정보 및 보안을 개선하기 위해 이러한 이미지는 대신 HTTPS를 통해 검색됩니다. HTTPS를 통해 이미지를 사용할 수 없는 경우 이미지가 로드되지 않습니다.
  - 사이트 및 최근 활동으로 사이트 사용 권한을 봅니다. Microsoft Edge 88부터는 사용자가 사이트 사용 권한을 보다 쉽게 관리할 수 있습니다. 권한 유형이 아닌 웹 사이트별로 사용 권한을 볼 수 있습니다. 또한 사용자에게 사이트 사용 권한에 대한 최근 변경 내용을 모두 표시하는 최근 활동 섹션이 추가되었습니다.
  - 브라우저 쿠키에 대한 컨트롤을 향상시켰습니다. Microsoft Edge 88부터 사용자는 타사 쿠키에 영향을 주지 않고 타사 쿠키를 삭제할 수 있습니다. 또한 사용자는 자사 또는 타사별로 쿠키를 필터링하고 이름, 쿠키 수, 저장 및 마지막으로 수정된 데이터의 양을 기준으로 정렬할 수 있습니다.

- **성능:**

  - 절전 모드 탭을 사용하여 브라우저 성능을 향상합니다. 절전 모드 탭은 활성 탭이나 다른 응용 프로그램에서 사용할 수 있도록 메모리 및 CPU와 같은 시스템 리소스를 확보하기 위해 비활성 탭을 절전 모드로 전환하여 브라우저 성능을 향상시킵니다. 사용자는 사이트가 절전 모드로 전환되는 것을 방지하고 비활성 탭이 절전 모드로 전환될 때까지의 시간을 구성할 수 있습니다. 사용자를 흐름에서 유지시키기 위해 인트라넷 사이트와 같은 특정 사이트가 절전 모드로 전환되는 것을 방지하는 추론도 있습니다. 이 기능은 실험을 허락한 임의로 선택된 사용자 그룹으로 제한됩니다. Microsoft Edge 버전 89에서는 기본적으로 절전 모드 탭 기능을 사용하도록 계획하고 있습니다. 이 기능은 그룹 정책을 통해 관리할 수 있습니다.
  - 시작 향상을 통해 Microsoft Edge 시작 속도를 향상합니다. Microsoft Edge 시작 속도를 개선하기 위해 시작 향상이라는 기능을 개발했습니다. 시작 향상을 사용하면 Microsoft Edge가 백그라운드에서 실행되어 Microsoft Edge가 더 빠르게 실행됩니다. 참고: 이 기능은 실험을 활성화한 임의로 선택된 사용자 그룹으로 제한됩니다. 이러한 사용자는 기능 팀에 피드백을 제공합니다.

- **생산성:**

  - 세로 탭을 사용하여 생산성 및 멀티태스킹을 향상합니다. 가로 탭 수가 늘어나면 사이트 제목이 잘리기 시작하고 각 탭이 축소될 때 탭 컨트롤이 손실됩니다. 따라서 사용자가 탭을 검색, 전환 및 관리하는 데 더 많은 시간을 소비하고 당면한 작업에 더 적은 시간을 소비하므로 사용자 워크플로가 중단됩니다. 세로 탭을 통해 사용자가 탭을 측면으로 이동시킬 수 있습니다. 여기서 세로로 정렬된 아이콘과 더 긴 사이트 제목을 통해 열 탭을 빠르게 검색, 식별 및 전환할 수 있습니다.
  - 생년월일 필드를 자동으로 채웁니다. Microsoft Edge는 이미 주소, 이름, 전화 번호 등의 사용자 데이터를 자동으로 채워서 양식을 작성하고 온라인으로 계정을 만드는 동안 시간과 노력을 절약하는 데 도움이 됩니다. Microsoft Edge는 이제 사용자가 저장하고 자동으로 채울 수 있는 생년월일 필드를 지원합니다. 사용자는 프로필 설정에서 언제든지 이 정보를 보고 편집하고 삭제할 수 있습니다.
  - 기록에서 최근에 닫은 탭의 개선된 기능입니다. 최근에 닫은 탭은 이전 세션이 아닌 과거 검색 세션에서 마지막 25개 탭과 창을 유지합니다. 사용자는 새 기록 환경에서 최근에 닫은 항목을 선택하여 열려 있던 모든 탭을 볼 수 있습니다.
  - 기본적으로 "오늘 하루를 한 눈에 보기" 기능이 사용 설정되어 있습니다. Microsoft Edge 버전 88부터 정보 근로자는 새 탭 페이지(NTP)에서 지능형 생산성 기능을 활용할 수 있습니다. 사용자가 회사 또는 학교 계정으로 로그인하여 M365 Graph에서 공급하는 개인 밎춤형 관련 콘텐츠를 사용할 수 있도록 제공합니다. 사용자는 "오늘 하루를 한 눈에 보기" 모듈을 빠르게 스캔하여 모임 및 최근 작업을 쉽게 추적하고, 사용하고자 하는 응용 프로그램을 빠르게 시작할 수 있습니다.

- **PDF:**

  - PDF 문서가 책 보기(두 페이지)로 표시됩니다. Microsoft Edge 버전 88부터 사용자는 단일 페이지 또는 두 페이지 책 보기에서 PDF 문서를 볼 수 있습니다. 보기를 변경하려면 도구 모음에서 **페이지 보기** 단추를 클릭합니다.
  - PDF 파일에 대한 고정된 텍스트 메모를 지원합니다. Microsoft Edge 버전 87부터 사용자는 PDF 파일의 모든 텍스트에 입력된 텍스트 메모를 추가할 수 있습니다.
  - PDF 문서에서 텍스트 선택 환경이 원활해집니다. 사용자는 Microsoft Edge에서 연 PDF 문서에서 더 원활하고 일관된 텍스트 선택 환경을 얻을 수 있습니다.
  - 다운로드 표시줄에서 PDF 파일로 저장된 웹 페이지를 볼 수 있습니다. 이제 사용자는 다운로드 표시줄에서 "PDF로 저장"을 프린터 대상으로 설정하여 생성된 PDF 파일을 볼 수 있습니다.

- **글꼴:**

  - 브라우저 아이콘은 Fluent 디자인 시스템으로 업데이트됩니다. 브라우저에서 Fluent 디자인에 대한 지속적인 작업의 일환으로 새로운 Microsoft 아이콘 시스템에 더 가깝게 아이콘을 정렬하도록 변경했습니다. 이러한 변경 사항은 탭, 주소 표시줄, 다양한 메뉴에 있는 탐색 및 길 찾기 아이콘을 비롯한 많은 하이 터치 사용자 인터페이스에 영향을 미치게 됩니다.
  - 글꼴 렌더링을 향상시켰습니다. 텍스트 렌더링이 향상되어 명확성을 높이고 흐림을 줄입니다.

### 정책 업데이트

#### 새 정책

16개의 새 정책이 추가되었습니다. [Microsoft Edge Enterprise 방문 페이지](https://www.microsoft.com/edge/business/download)에서 업데이트된 관리 템플릿을 다운로드합니다. 다음과 같은 새 정책이 추가되었습니다.

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
- [StartupBoostEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#startupboostenabled) - 시작 향상을 사용하도록 설정합니다.
- [UpdatePolicyOverride](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#updatepolicyoverride) - Microsoft Edge 업데이트가 Microsoft Edge에서 사용 가능한 업데이트를 처리하는 방법을 지정합니다.
- [VerticalTabsAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#verticaltabsallowed) - 브라우저 측면의 탭에 대한 세로 레이아웃의 가용성을 구성합니다.
- [WebRtcAllowLegacyTLSProtocols](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webrtcallowlegacytlsprotocols) - WebRTC에서 레거시 TLS/DTLS 다운그레이드를 허용합니다.

#### 더 이상 사용되지 않는 정책

다음 정책은 더 이상 사용되지 않습니다.

- [ProactiveAuthEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proactiveauthenabled) - 사전 인증을 사용하도록 설정합니다.
- [ProxyBypassList](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxybypasslist) - 프록시 우회 규칙을 구성합니다.
- [ProxyMode](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxymode) - 프록시 서버 설정을 구성합니다.
- [ProxyPacUrl](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxypacurl) - 프록시 .pac 파일 URL을 설정합니다.
- [ProxyServer](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxyserver) - 프록시 서버의 주소 또는 URL을 구성합니다.
- [WebDriverOverridesIncompatiblePolicies](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webdriveroverridesincompatiblepolicies) - WebDriver가 호환되지 않는 정책을 재정의할 수 있도록 허용합니다.

#### 폐기된 정책

다음 정책은 사용되지 않습니다.

- [DefaultPluginsSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultpluginssetting) - 기본 Adobe Flash 설정입니다.
- [PluginsAllowedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#pluginsallowedforurls) - 특정 사이트에서 Adobe Flash 플러그 인을 허용합니다.
- [PluginsBlockedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#pluginsblockedforurls) - 특정 사이트에서 Adobe Flash 플러그 인을 차단합니다.
- [RunAllFlashInAllowMode](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#runallflashinallowmode) - Adobe Flash 콘텐츠 설정을 모든 콘텐츠로 확장합니다.

<!-- end major 88 -->

## 버전 87.0.664.55: 12월 3일

다양한 버그와 성능 문제를 해결했습니다. 이 릴리스에서는 다음과 같은 새로운 기능이 지원됩니다.

- **온라인 유출에서 사용자의 암호가 발견되면 경고 생성됩니다**. 사용자 암호는 알려진 위반된 자격 증명의 리포지토리와 대조하여 일치하는 것이 발견되는 경우 사용자에게 경고를 전송합니다. 보안 및 개인 정보 보호를 위해 사용자 암호는 유출된 자격 증명의 데이터베이스와 대조할 때 해시 및 암호화됩니다.

## 버전 87.0.664.52: 11월 30일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 87.0.664.40: 11월 18일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 87.0.664.36:11 월 16일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 87.0.664.30: 11월 9일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 87.0.664.24: 11월 2일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 87.0.664.18: 10월 26일

다양한 버그와 성능 문제를 해결했습니다.

<!-- begin major 87 -->
## 버전 87.0.664.12: 10월 20일

### 기능 업데이트

- **키오스크 모드 개인 정보 보호 기능을 사용할 수 있습니다**. 사용자 데이터의 개인 정보 보호에 대해 기업에 도움이 되는 Microsoft Edge 버전 87 키오스크 모드 기능으로 시작할 수 있습니다. 이 기능을 사용하면 종료 시 사용자 데이터를 지우고 다운로드한 파일을 삭제하고 지정된 유휴 시간 후에 구성된 시작 환경을 재설정하는 등의 작업을 수행할 수 있습니다. [Microsoft Edge 키오스크 모드를 구성](https://docs.microsoft.com/deployedge/microsoft-edge-configure-kiosk-mode)하는 방법에 대해 자세히 알아보기
- **ClickOnce 배포는 기본적으로 사용하도록 설정됩니다**. ClickOnce는 기본적으로 Microsoft Edge 87에서 사용할 수 있습니다. 이로 인해 기업이 소프트웨어를 배포하고 Microsoft Edge 레거시 브라우저 동작에 더 잘 부합할 수 있도록 장벽을 낮출 수 있습니다. Microsoft Edge 87에서 시작하는 ClickOnceEnabled 정책의 "구성되지 않음" 상태는 새 기본 ClickOnce 상태인 사용 허용(이전 기본 상태인 사용 안 함과 비교)을 반영합니다.
- **엔터프라이즈 새 탭 페이지(NTP)는 생산성을 사용자 지정, 작업 관련 피드 콘텐츠로 통합합니다**. 엔터프라이즈 NTP는 회사 또는 학교 계정으로 로그인한 사용자에게 Microsoft에서 제공하는 Office 365 생산성 페이지를 단일 페이지에서 조직되고 맞춤화된 작업 관련 회사 및 업계 피드와 혼합합니다. 사용자는 익숙한 Office 365 콘텐츠 및 Bing에서 제공하는 비즈니스용 Microsoft Search를 인식할 수 있습니다. 또한 사용자, 회사 또는 업계와 관련된 콘텐츠 및 모듈과 조직에서 사용할 수 있게 된 기타 피드의 선택 항목을 사용자 지정 가능한 "내 피드"로 간편하게 전환할 수 있습니다. [자세한 내용을 알아보세요](https://docs.microsoft.com/microsoft-365/admin/manage/manage-industry-news?view=o365-worldwide&preserve-view=true).

- **개인정보 보호 및 보안:**

  - 정책 구성 사이트에 대한 TLS 토큰 바인딩을 지원합니다. TLS 토큰 바인딩은 토큰 절도 공격을 방지하여 쿠키를 처음 설정했던 장치 외의 다른 장치에서 사용할 수 없도록 하는 데 도움이 됩니다. TLS 토큰 바인딩을 사용하려면 [AllowTokenBindingForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowtokenbindingforurls) 정책을 설정하고 목록의 사이트가 이 기능을 지원해야 합니다.

- **키보드는 PDF 파일의 형광펜을 지원합니다**. 사용자는 키보드 키를 사용하여 PDF에서 텍스트를 강조 표시할 수 있습니다.

- **인쇄:**

  - 양면 인쇄 시 어느 쪽으로 대칭 이동할 것인지 선택합니다. 양면 인쇄 시 사용자는 용지의 긴 면이나 짧은 면으로 대칭 이동할 수 있습니다.
  - 엔터프라이즈에 대한 인쇄 래스터화 모드를 선택합니다. Windows에서 포스트스크립트가 아닌 프린터에 대해 Microsoft Edge의 인쇄 방식을 제어합니다. 포스트스크립트가 아닌 프린터의 인쇄 작업에서 올바르게 인쇄하려면 래스터화를 진행해야 하는 경우가 있습니다. 인쇄 옵션은 "전체" 및 "빠르게"입니다.

### 정책 업데이트

#### 새로운 정책

10개의 새 정책을 추가했습니다. [Microsoft Edge Enterprise 랜딩 페이지](https://www.microsoft.com/edge/business/download)에서 업데이트된 관리 템플릿을 다운로드합니다. 다음과 같은 새 정책이 추가되었습니다.

- [ConfigureFriendlyURLFormat](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#configurefriendlyurlformat) - Microsoft Edge에서 복사된 URL의 기본 붙여넣기 서식을 구성하고 추가 서식을 사용자에게 제공할 것인지 여부를 결정합니다.
- [EdgeShoppingAssistantEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#edgeshoppingassistantenabled) - Microsoft Edge에서 쇼핑을 할 수 있습니다.
- [HideInternetExplorerRedirectUXForIncompatibleSitesEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#hideinternetexplorerredirectuxforincompatiblesitesenabled) - Microsoft Edge에서 일회성 리디렉션 대화 상자 및 배너를 숨깁니다.
- [KioskAddressBarEditingEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskaddressbareditingenabled) - 키오스크 모드 공개 검색 환경에 대해 주소 표시줄 편집을 구성합니다.
- [KioskDeleteDownloadsOnExit](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskdeletedownloadsonexit) - Microsoft Edge가 닫히는 경우 키오스크 세션의 일부로 다운로드된 파일을 삭제합니다.
- [PasswordRevealEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#passwordrevealenabled) - 암호 노출 단추를 사용하도록 설정합니다.
- [RedirectSitesFromInternetExplorerPreventBHOInstall](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#redirectsitesfrominternetexplorerpreventbhoinstall) - BHO 설치를 방지하여 Internet Explorer에서 Microsoft Edge로 호환되지 않는 사이트를 리디렉션합니다.
- [RedirectSitesFromInternetExplorerRedirectMode](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#redirectsitesfrominternetexplorerredirectmode) - Internet Explorer에서 Microsoft Edge로 호환되지 않는 사이트를 리디렉션합니다.
- [SpeechRecognitionEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#speechrecognitionenabled) - 음성 인식을 구성합니다.
- [WebCaptureEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webcaptureenabled) - Microsoft Edge에서 웹 캡처 기능을 사용하도록 설정합니다.

#### 더 이상 사용되지 않는 정책

[NewTabPageSetFeedType](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#newtabpagesetfeedtype) - Microsoft Edge 새 탭 페이지 환경을 구성합니다.

#### 폐기된 정책

[EnableDeprecatedWebPlatformFeatures](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#enabledeprecatedwebplatformfeatures) - 제한된 시간 동안 사용되지 않는 웹 플랫폼 기능을 다시 사용하도록 설정합니다.

<!-- end major 87 -->

## 버전 86.0.622.43: 10월 16일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 86.0.622.36: 10월 7일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 86.0.622.31: 10월 1일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 86.0.622.28: 9월 28일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 86.0.622.15: 9월 14일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 86.0.622.11: 9월 9일

### 기능 업데이트

* **Internet Explorer 모드:**

   * 사용자가 Microsoft UI(사용자 인터페이스)를 사용하여 Internet Explorer 모드에서 사이트를 테스트할 수 있습니다. Microsoft Edge 버전 86부터 관리자는 테스트 목적으로 또는 사이트 목록 XML에 사이트가 추가될 때까지 사용자가 Internet Explorer 모드에서 탭을 로드할 수 있도록 UI 옵션을 사용할 수 있습니다.

* **다운로드 관리자를 사용하여 디스크에서 다운로드를 삭제합니다.** 이제 사용자는 브라우저를 떠나지 않고 디스크에서 다운로드한 파일을 삭제할 수 있습니다. 새로운 다운로드 삭제 기능은 다운로드 쉘프 또는 다운로드 페이지의 컨텍스트 메뉴 내에 있습니다.

* **이전 Microsoft Edge 버전으로 롤백합니다.** 롤백 기능을 통해 관리자는 최신 버전의 Microsoft Edge에 문제가 있는 경우 정상 버전의 Microsoft Edge로 돌아갈 수 있습니다.
[자세한 내용을 알아보세요](edge-learnmore-rollback.md).

* **기업 전체에서 기본적으로 동기화를 사용하도록 강제 설정합니다.**  관리자는 기본적으로 [ForceSync](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#forcesync) 정책을 사용하여 Azure AD(Azure Active Directory) 계정에 대한 동기화를 사용하도록 설정할 수 있습니다.

* **PDF 업데이트:**

  * PDF 문서에 대한 목차입니다. 버전 86부터 Microsoft Edge는 사용자가 PDF 문서를 쉽게 탐색할 수 있도록 목차를 지원합니다.
  * 소형 폼 팩터 화면에서 모든 PDF 기능에 액세스합니다. 화면 크기가 작은 장치에서 Microsoft Edge PDF 판독기의 모든 기능에 액세스합니다.
  * PDF 파일의 형광펜을 지원합니다. 이 업데이트를 통해 사용자는 디지털 펜을 사용하여 실제 형광펜과 용지와 같은 방식으로 PDF 파일의 텍스트를 직접 강조 표시할 수 있습니다.
  * PDF 스크롤이 향상되었습니다. 이제 긴 PDF 문서를 탐색하는 동안 자유롭게 스크롤할 수 있습니다.

* **Windows 7, 8 및 8.1에서 자동으로 프로필이 전환됩니다.** 현재 Windows 10의 Microsoft Edge에서 사용할 수 있는 자동 프로필 스위칭이 하위 수준 Windows(Windows 7, 8, 8.1)로 확장됩니다. 자세한 내용은 [자동 프로필 전환](https://blogs.windows.com/msedgedev/2020/04/30/automatic-profile-switching/) 블로그 게시물을 참조하시기 바랍니다.

* **Microsoft Edge 추가 기능 웹 사이트에서 검색 쿼리를 입력하기 시작하면 자동 완료 제안이 표시됩니다.** 자동 완료를 사용하면 전체 문자열을 입력할 필요 없이 검색 쿼리를 빠르게 완료할 수 있습니다. 이 기능은 사용자가 올바른 철자를 기억할 필요가 없고 표시되는 사용 가능한 옵션 중에서 선택할 수 있으므로 유용합니다.

* **HTML5 Application Cache API를 제거합니다.**  Microsoft Edge 버전 86부터는 웹 페이지를 오프라인으로 사용할 수 있는 기존 Application Cache API가 Microsoft Edge에서 제거되고 있습니다. 웹 개발자는 응용 프로그램 캐시 API를 서비스 작업자로 교체하는 방법에 대한 정보를 위해 [WebDev 문서](https://web.dev/appcache-removal/)을(를) 검토해야 합니다.  중요: Microsoft Edge 버전 90까지 더 이상 사용되지 않는 Application Cache API를 사이트에서 계속 사용할 수 있도록 [AppCache OriginTrial 토큰](https://developers.chrome.com/origintrials/#/view_trial/1776670052997660673)을(를) 요청할 수 있습니다.

* **보안:**

  * 보안 DNS(DNS-over-HTTPS) 지원을 제공합니다.  Microsoft Edge 버전 86부터는 관리되지 않는 디바이스에서 보안 DNS를 제어하는 설정을 사용할 수 있습니다. 이러한 설정은 관리 디바이스의 사용자가 액세스할 수 없지만 IT 관리자는 [damperhtps 모드](https://docs.microsoft.com/deployedge/microsoft-edge-policies#dnsoverhttpsmode) 그룹 정책을 사용하여 보안 DNS를 사용하거나 사용하지 않도록 설정할 수 있습니다.


* **그룹 정책을 사용하여 사용자 지정 이미지를 새 탭 페이지(NTP)에 추가합니다.** Microsoft Edge 버전 86부터 NTP에는 기본 이미지를 사용자 지정 사용자 제공 이미지로 바꾸는 옵션이 있습니다. 이 이미지의 속성을 관리하는 기능도 그룹 정책에서 지원됩니다.

* **사용자 지정된 바로 가기 키를 VS Code에 일치시킵니다.** Microsoft Edge DevTools는 이제 편집기/IDE와 일치하도록 DevTools의 바로 가기 키 사용자 지정을 지원합니다. Microsoft Edge 84에서는 DevTools 바로 가기 키를 VS Code에 일치시키는 기능을 추가했습니다.

* **하위 수준 Windows 및 MacOS에 대해 [MetricsReportingEnabled]( https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#metricsreportingenabled) 및 [SendSiteInformationToEnhancedServices]( https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sendsiteinfotoimproveservices) 정책을 바꿉니다.** 이러한 정책은 Microsoft Edge 버전 86에서 더 이상 사용되지 않으며 Microsoft Edge 버전 89에서는 사용되지 않습니다.<br>
이러한 정책은 Windows 10에서 [원격측정 허용](https://go.microsoft.com/fwlink/?linkid=2099569) 및 다른 모든 플랫폼에 대한 새 [진단 데이터](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#diagnosticdata) 정책으로 대체됩니다. 이를 통해 사용자는 Microsoft for Windows 7, 8, 8.1 및 MacOS로 전송되는 진단 데이터를 관리할 수 있습니다.

* **SameSite=Lax 쿠키(기본값)**. 웹 보안 및 개인 정보 보호를 향상시키기 위해 기본적으로 쿠키 기본값이 [SameSite=Lax](https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie/SameSite) 처리로 설정됩니다.  즉, 쿠키는 타사 컨텍스트에서만 전송되고 타사에 보낸 요청의 경우에는 생략됩니다. 이와 같이 변경하면 타사 리소스에 대한 쿠키가 있어야 제대로 작동하는 웹 사이트에서 호환성에 영향을 줄 수 있습니다. 이와 같은 쿠키를 허용하려면 웹 개발자가 쿠키를 설정할 때 명시적 `SameSite=none` 및 `Secure` 특성을 추가하여 타사 컨텍스트에서 설정하고 해당 컨텍스트로 보내야 하는 쿠키를 표시할 수 있습니다. 해당 변경에서 특정 사이트를 제외하려는 기업에서는 [LegacySameSiteCookieBehaviorEnabledForDomainList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#legacysamesitecookiebehaviorenabledfordomainlist) 정책을 사용하여 해당 작업을 하거나 [LegacySameSiteCookieBehaviorEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#legacysamesitecookiebehaviorenabled) 정책을 사용하여 모든 사이트에서 변경 내용을 옵트아웃할 수 있습니다.

### 정책 업데이트

#### 새로운 정책

19개의 새로운 정책이 추가되었습니다. [Microsoft Edge Enterprise 랜딩 페이지](https://aka.ms/EdgeEnterprise)에서 업데이트된 관리 템플릿을 다운로드합니다. 다음과 같은 새 정책이 추가되었습니다.

- [CollectionsServicesAndExportsBlockList](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#collectionsservicesandexportsblocklist) - 지정된 서비스 목록에 대한 액세스를 차단하고 컬렉션에서 대상을 내보내기합니다.
- [DefaultSensorSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultsensorssetting) - 기본 센서 설정입니다.
- [DefaultSerialGuardSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultserialguardsetting) - 직렬 API의 사용을 제어합니다.
- [진단 데이터](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#diagnosticdata) - 브라우저 사용에 대한 필수 및 선택적 진단 데이터를 전송합니다.
- [EnterpriseModeSiteListManagerAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#enterprisemodesitelistmanagerallowed) - 엔터프라이즈 모드 사이트 목록 관리자 도구에 대한 액세스를 허용합니다.
- [ForceSync](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#forcesync) - 브라우저 데이터의 동기화를 강제 적용하고 동기화 동의 메시지를 표시하지 않습니다.
- [InsecureFormsWarningsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#insecureformswarningsenabled) - 안전하지 않은 양식에 대해 경고를 사용합니다.
- [InternetExplorerIntegrationTestingAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#internetexplorerintegrationtestingallowed) - Internet Explorer 모드 테스트를 허용합니다.
- [SpotlightExperiencesAndRecommendationsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#spotlightexperiencesandrecommendationsenabled) - 사용자가 Microsoft 서비스에 대한 사용자 지정 배경 이미지와 텍스트, 제안 사항, 알림 및 팁을 받을 수 있는지 여부를 선택합니다.
- [NewTabPageAllowedBackgroundTypes](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#newtabpageallowedbackgroundtypes) - 새 탭 페이지 레이아웃에 허용된 배경 유형을 구성합니다.
- [SaveCookiesOnExit](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#savecookiesonexit) - Microsoft Edge가 닫힐 때 쿠키를 저장합니다.
- [SensorsAllowedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sensorsallowedforurls) - 특정 사이트의 센서에 대한 액세스를 허용합니다.
- [SensorsBlockedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sensorsblockedforurls) - 특정 사이트의 센서에 대한 액세스를 차단합니다.
- [SerialAskForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#serialaskforurls) - 특정 사이트에서 직렬 API를 허용합니다.
- [SerialBlockedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#serialblockedforurls) - 특정 사이트에서 직렬 API를 차단합니다.
- [URLBlocklist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#urlblocklist) - URL 목록에 대한 액세스를 차단합니다.
- [URLLowlist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#urlallowlist) - 허용된 URL 목록을 정의합니다.
- [UserAgentClientHintsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#useragentclienthintsenabled) - 사용자-에이전트 클라이언트 힌트 기능을 사용하도록 설정합니다.
- [UserDataSnapshotRetentionLimit](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#userdatasnapshotretentionlimit) - 비상 롤백 시 사용하기 위해 보존된 사용자 데이터 스냅샷 수를 제한합니다.

#### 사용되지 않는 정책

- [MetricsReportingEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#metricsreportingenabled) - 사용 및 충돌 관련 데이터보고를 사용하도록 설정합니다.
- [SendSiteInfoToImproveServices](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sendsiteinfotoimproveservices) - Microsoft 서비스를 개선하기 위해 사이트 정보를 보냅니다.

#### 폐기된 정책

[TLS13HardeningForLocalAnchorsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#tls13hardeningforlocalanchorsenabled) - 로컬 신뢰 앵커에 대한 TLS 1.3 보안 기능을 사용하세요.

#### 변경된 정책 캡션

[NativeWindowCocclusionEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#nativewindowocclusionenabled) - 원본 창 숨김을 사용합니다.

#### 변경된 정책 설명

- [AdsSettingForIntrusiveAdsSites](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#adssettingforintrusiveadssites)
- [AllowTokenBindingForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#allowtokenbindingforurls)
- [AmbientAuthenticationInPrivateModesEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#ambientauthenticationinprivatemodesenabled)
- [ApplicationGuardContainerProxy](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#applicationguardcontainerproxy)
- [AutoImportAtFirstRun](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#autoimportatfirstrun)
- [AutoOpenFileTypes](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#autoopenfiletypes)
- [BrowserSignin](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#browsersignin)
- [ClearBrowsingDataOnExit](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#clearbrowsingdataonexit) 
- [ClickOnceEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#clickonceenabled)
- [CommandLineFlagSecurityWarningsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#commandlineflagsecuritywarningsenabled)
- [ConfigureOnPremisesAccountAutoSignIn](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#configureonpremisesaccountautosignin)
- [ConfigureShare](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#configureshare)
- [CookiesAllowedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#cookiesallowedforurls)
- [CustomHelpLink](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#customhelplink)
- [DefaultCookiesSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultcookiessetting)
- [DefaultGeolocationSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultgeolocationsetting)
- [DefaultImagesSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultimagessetting)
- [DefaultInsecureContentSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultinsecurecontentsetting)
- [DefaultJavaScriptSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultjavascriptsetting)
- [DefaultNotificationsSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultnotificationssetting)
- [DefaultPluginsSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultpluginssetting)
- [DefaultPopupsSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultpopupssetting)
- [DefaultSearchProviderEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultsearchproviderenabled)
- [DefaultWebBluetoothGuardSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultwebbluetoothguardsetting)
- [DefaultWebUsbGuardSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultwebusbguardsetting)
- [DelayNavigationsForInitialSiteListDownload](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#delaynavigationsforinitialsitelistdownload)
- [DeveloperToolsAvailability](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#developertoolsavailability)
- [EnableSha1ForLocalAnchors](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#enablesha1forlocalanchors)
- [DownloadRestrictions](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#downloadrestrictions)
- [EnableDeprecatedWebPlatformFeatures](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#enabledeprecatedwebplatformfeatures)
- [WinHttpProxyResolverEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#winhttpproxyresolverenabled)
- [ExperimentationAndConfigurationServiceControl](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#experimentationandconfigurationservicecontrol)
- [ExternalProtocolDialogShowAlwaysOpenCheckbox](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#externalprotocoldialogshowalwaysopencheckbox)
- [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)
- [ForceBingSafeSearch](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#forcebingsafesearch)
- [ForceYouTubeRestrict](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#forceyoutuberestrict)
- [HomepageIsNewTabPage](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#homepageisnewtabpage)
- [HomepageLocation](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#homepagelocation)
- [InPrivateModeAvailability](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#inprivatemodeavailability)
- [InternetExplorerIntegrationEnhancedHangDetection](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#internetexplorerintegrationenhancedhangdetection)
- [InternetExplorerIntegrationLevel](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#internetexplorerintegrationlevel)
- [InternetExplorerIntegrationSiteRedirect](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#internetexplorerintegrationsiteredirect)
- [LegacySameSiteCookieBehaviorEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#legacysamesitecookiebehaviorenabled)
- [NativeWindowOcclusionEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#nativewindowocclusionenabled)
- [NavigationDelayForInitialSiteListDownloadTimeout](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#navigationdelayforinitialsitelistdownloadtimeout)
- [NetworkPredictionOptions](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#networkpredictionoptions)
- [NewTabPageLocation](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#newtabpagelocation)
- [NewTabPageSearchBox](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#newtabpagesearchbox)
- [NewTabPageSetFeedType](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#newtabpagesetfeedtype)
- [NonRemovableProfileEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#nonremovableprofileenabled)
- [PasswordProtectionWarningTrigger](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#passwordprotectionwarningtrigger)
- [PasswordProtectionLoginURLs](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#passwordprotectionloginurls)
- [PasswordProtectionChangePasswordURL](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#passwordprotectionchangepasswordurl)
- [PluginsAllowedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#pluginsallowedforurls)
- [PluginsBlockedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#pluginsblockedforurls)
- [PreventSmartScreenPromptOverride](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#preventsmartscreenpromptoverride)
- [PreventSmartScreenPromptOverrideForFiles](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#preventsmartscreenpromptoverrideforfiles)
- [ProxyMode](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxymode)
- [RegisteredProtocolHandlers](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#registeredprotocolhandlers)
- [RelaunchNotification](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#relaunchnotification)
- [RestoreOnStartup](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#restoreonstartup)
- [RestoreOnStartupURLs](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#restoreonstartupurls)
- [RestrictSigninToPattern](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#restrictsignintopattern)
- [SSLVersionMin](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sslversionmin)
- [SmartScreenAllowListDomains](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#smartscreenallowlistdomains)
- [SmartScreenEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#smartscreenenabled)
- [SmartScreenForTrustedDownloadsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#smartscreenfortrusteddownloadsenabled)
- [SmartScreenPuaEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled)
- [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled)
- [TrackingPrevention](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#trackingprevention)
- [WebRtcLocalhostIpHandling](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webrtclocalhostiphandling)

<!-- end 86 -->

## 버전 85.0.564.41: 8월 25일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 85.0.564.40: 8월 21일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 85.0.564.36: 8월 17일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 85.0.564.30: 8월 10일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 85.0.564.23: 8월 3일

다양한 버그와 성능 문제를 해결했습니다.

<!--- Archived to version 85.0.564.18: July 28 ---->

## 참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
