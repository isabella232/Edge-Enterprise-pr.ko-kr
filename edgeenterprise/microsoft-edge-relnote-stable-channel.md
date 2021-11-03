---
title: 안정 채널에 대한 Microsoft Edge 릴리스 정보
ms.author: leahtu
author: dan-wesley
manager: srugh
ms.date: 11/01/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 안정 채널에 대한 Microsoft Edge 릴리스 정보
ms.openlocfilehash: 5c8a893254d9c9be0ccf22c76a3f873f31a58756
ms.sourcegitcommit: 42f01cad0bf15224222b2aeadb48f03d46c35723
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2021
ms.locfileid: "12154499"
---
# <a name="release-notes-for-microsoft-edge-stable-channel"></a>Microsoft Edge 안정 채널에 대한 릴리스 정보

이 릴리스 정보는 Microsoft Edge 안정 채널에 포함된 새로운 기능 및 비보안 업데이트에 대한 정보를 제공합니다.

- 모든 보안 업데이트는 [여기](microsoft-edge-relnotes-security.md)에서 확인할 수 있습니다.
- Microsoft Edge 안정 채널에 대한 보관된 릴리스 정보는 [여기](microsoft-edge-relnote-archive-stable-channel.md)에 있습니다.

 Microsoft Edge 채널을 이해하려면 [Microsoft Edge 채널 개요](microsoft-edge-channels.md)를 참조하세요.

> [!NOTE]
> 안정 채널의 업데이트는 하루 이상 점진적으로 배포됩니다. 자세한 내용은 [Microsoft Edge 업데이트 점진적 배포](microsoft-edge-update-progressive-rollout.md)를 참조하세요.
>
> Microsoft Edge 웹 플랫폼은 사용자 환경, 보안 및 개인 정보 개선을 위해 지속적으로 진화하고 있습니다. 자세히 알아보려면 [Microsoft Edge에 적용될 사이트 호환성에 영향을 미치는 변경 사항](/microsoft-edge/web-platform/site-impacting-changes)을 참조하세요.

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
<!-- end major 92 -->
<!-- Archive from Version 92.0.902.55: July 22 to Version 91.0.864.37: May 27 -->
<!-- Archive from 89.0.774.45: March 4 to 90.0.818.66: May 20 ->
<!-- Archive from 86.0.622.43: October 15 to beta 88.0.705.81: February 25  ->
<!-- Archive from 86.0.622.38-october-9 to beta 86.0.62.215-september-14  ->
<!-- Archived to version 84.0.522.40: July 16 -->

## <a name="see-also"></a>참고 항목

- [Microsoft Edge Enterprise 방문 페이지](https://aka.ms/EdgeEnterprise)
