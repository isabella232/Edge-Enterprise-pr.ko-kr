---
title: 베타 채널 용 Microsoft Edge 릴리스 정보
ms.author: aguta
author: dan-wesley
manager: srugh
ms.date: 11/01/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 베타 채널 용 Microsoft Edge 릴리스 정보
ms.openlocfilehash: 57ea92fde42d4ad4c63f238c3b30fa218ee5b360
ms.sourcegitcommit: 42f01cad0bf15224222b2aeadb48f03d46c35723
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2021
ms.locfileid: "12154520"
---
# <a name="release-notes-for-microsoft-edge-beta-channel"></a>Microsoft Edge 베타 채널에 대한 릴리스 정보

이 릴리스 정보는 Microsoft Edge 베타 채널에 포함된 새로운 기능 및 비보안 업데이트에 대한 정보를 제공합니다. 이 릴리스 정보의 보관된 버전은 [여기](microsoft-edge-relnote-archive-beta-channel.md)에서 볼 수 있습니다.

> [!NOTE]
> Microsoft Edge 웹 플랫폼은 사용자 환경, 보안 및 개인 정보 개선을 위해 지속적으로 진화하고 있습니다. 자세히 알아보려면 [Microsoft Edge에 적용될 사이트 호환성에 영향을 미치는 변경 사항](/microsoft-edge/web-platform/site-impacting-changes)을 참조하세요.

## <a name="version-96010548-november-1"></a>버전 96.0.1054.8: 11월 1일

### <a name="feature-updates"></a>기능 업데이트

- **프로토콜 링크를 통해 PWA(점진적 웹앱)를 직접 실행합니다.** 설치된 PWAS가 보다 통합된 환경을 위해 특정 프로토콜을 사용하는 링크를 처리하도록 합니다.

- **수학 해소를 통해 수학 문제를 해결하는 방법을 학습합니다.** 다양한 수학 개념에 대한 도움말을 Microsoft Edge 수학 해법을 사용할 수 있습니다. 이러한 개념은 기본 연산 및 정방형 수식에서 삼각형 및 계산까지 다양합니다. 수학 해법을 사용하면 필기 또는 인쇄된 수학 문제를 그림으로 찍은 다음 단계별 지침과 함께 즉각적인 해결 방법을 통해 도움이 없이 솔루션에 도달하는 방법을 배울 수 있습니다. 수학 해법은 수학 문제를 쉽게 입력하는 데 사용할 수 있는 수학 키보드도 함께 제공합니다. 이 키보드를 사용하면 기존 키보드를 검색하여 필요한 수학 문자를 찾을 필요가 없습니다. 문제를 해결한 후 수학 해기에서는 퀴즈, 워크시트 및 비디오 자습서를 계속 학습할 수 있는 옵션을 제공합니다.

- **PDF 문서의 스크롤 향상** PDF 문서에서 더 원활한 스크롤 환경을 제공하기 위해 스크롤 성능을 개선하고 있습니다. 스크롤하는 동안 흰색 막대가 나타나지 않습니다.

- **PDF에서 자유형 강조 표시** 자유형 하이퍼링크를 추가하여 PDF 보기 및 마크업 환경이 개선됩니다. 액세스 권한이 없는 PC 및 스캔한 문서의 섹션을 강조할 수 있습니다.

- **CET(제어 흐름 적용 기술).**  Microsoft Edge 프로세스에 하드웨어 종속 제어 흐름을 사용하는 더욱 안전한 검색 모드를 지원하기 시작할 것입니다. 제어 흐름은 Intel 11세대의 지원되는 하드웨어에서 제공됩니다. 또는 AMD Zen 3. 그룹 정책을 사용하여 IFEO(이미지 파일 실행 옵션)를 구성하여 CET을 사용하지 않도록 설정할 수 있습니다.

- **입력 입력 사이트용 새 경고 대화 상자입니다.** 이제 브라우저에서 다른 사이트와 매우 유사한 URL이 있는 일부 사이트에 경고가 표시됩니다. 이 UI는 클라이언트 쪽 지론을 사용하여 사용자에게 인기 있는 웹 사이트를 스푸핑할 수 있는 사이트에 대해 경고합니다. 자세한 내용은 [Typosquatting이란? 을 참조하세요.](https://support.microsoft.com/topic/what-is-typosquatting-54a18872-8459-4d47-b3e3-d84d9a362eb0)

- **IE 모드와 최신 브라우저 간의 핸드오프가 개선되어 있습니다.**  이 버전의 Microsoft Edge 버전부터 Microsoft Edge 및 Internet Explorer 모드 간의 탐색에는 양식 데이터와 추가 HTTP 헤더가 포함됩니다. 참조 헤더, 게시 데이터, 양식 데이터 및 요청 메서드는 두 환경 전체에서 올바르게 전달됩니다. [InternetExplorerIntegrationComplexNavDataTypes](/deployedge/microsoft-edge-policies#internetexplorerintegrationcomplexnavdatatypes) 정책을 사용하여 포함해야 하는 데이터 형식을 지정할 수 있습니다.

- **공개 미리 보기의 IE 모드에 대한 클라우드 사이트 목록 관리**  클라우드 사이트 목록 관리를 사용하면 조직의 사이트 목록을 호스팅하기 위해 사내 인프라 없이도 클라우드에서 IE 모드에 대한 사이트 목록을 관리할 수 있습니다. Microsoft Edge 센터의 사이트 목록 환경을 사용하여 클라우드 사이트 목록 관리 기능에 액세스할 Microsoft 365 관리 있습니다. 자세한 내용은 클라우드 사이트 목록 [관리 for IE 모드(공개](./edge-ie-mode-cloud-site-list-mgmt.md) 미리 보기) 문서를 참조하세요.

- **WSUS를 Microsoft Edge WebWiew2를 업데이트합니다.** WSUS를 사용하여 업데이트를 하는 IT Microsoft Edge WSUS를 사용하여 WebView2를 Microsoft Edge 수 있습니다. 이 기능을 사용하면 관리자가 오프라인 디바이스를 보다 쉽게 서비스할 수 있습니다.

- **서버용 WSUS 업데이트.** 이제 Microsoft Edge 채널(Stable, Beta, Dev)에 대한 WSUS 및 카탈로그 업데이트가 Windows Windows Server 2022를 포함하여 Microsoft Edge 서버 SKUS에 적용됩니다. 사용자에 대해 WSUS 업데이트를 구성하는 방법에 대한 자세한 Microsoft Edge 업데이트 [Microsoft Edge.](https://docs.microsoft.com/mem/configmgr/apps/deploy-use/deploy-edge?bc=https%3A%2F%2Fdocs.microsoft.com%2FDeployEdge%2Fbreadcrumb%2Ftoc.json&toc=https%3A%2F%2Fdocs.microsoft.com%2FDeployEdge%2Ftoc.json#update-microsoft-edge)

### <a name="policy-updates"></a>정책 업데이트

#### <a name="new-policies"></a>새 정책

- [ApplicationGuardUploadBlockingEnabled](/DeployEdge/microsoft-edge-policies#applicationguarduploadblockingenabled) - Application Guard에 있는 동안 파일이 업로드되지 않도록 합니다.
- [AudioProcessHighPriorityEnabled](/DeployEdge/microsoft-edge-policies#audioprocesshighpriorityenabled) - 오디오 프로세스가 오디오 프로세스에서 보통보다 높은 우선 순위로 Windows.
- [AutoLaunchProtocolsComponentEnabled](/DeployEdge/microsoft-edge-policies#autolaunchprotocolscomponentenabled) - AutoLaunch 프로토콜 구성 요소 사용.
- [EfficiencyMode](/DeployEdge/microsoft-edge-policies#efficiencymode) - 효율성 모드가 활성화될 때를 구성합니다.
- [ForceSyncTypes](/DeployEdge/microsoft-edge-policies#forcesynctypes) - 동기화에 포함된 형식 목록을 구성합니다.
- [InternetExplorerIntegrationComplexNavDataTypes](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationcomplexnavdatatypes) - 양식 모드로 들어갈 때 양식 데이터와 HTTP 헤더를 보낼지 여부를 Internet Explorer 구성합니다.
- [InternetExplorerModeToolbarButtonEnabled](/DeployEdge/microsoft-edge-policies#internetexplorermodetoolbarbuttonenabled) - 도구 모음의 Internet Explorer 모드 단추로 다시 로드를 표시
- [PrintPostScriptMode](/DeployEdge/microsoft-edge-policies#printpostscriptmode) - 포스트스크립트 인쇄합니다.
- [PrintRasterizePdfDpi](/DeployEdge/microsoft-edge-policies#printrasterizepdfdpi) - PDF DPI 래스터화로 인쇄합니다.
- [RendererAppContainerEnabled](/DeployEdge/microsoft-edge-policies#rendererappcontainerenabled) - 앱 컨테이너에서 렌더러를 사용하도록 설정
- [SharedLinksEnabled](/DeployEdge/microsoft-edge-policies#sharedlinksenabled) - 기록에 Microsoft 365 공유된 링크를 표시
- [TyposquattingCheckerEnabled](/DeployEdge/microsoft-edge-policies#typosquattingcheckerenabled) - Edge TyposquattingChecker를 구성합니다.

<!-- end major 96 --->

## <a name="version-950102038-october-28"></a>버전 95.0.1020.38: 10월 28일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-950102020-october-11"></a>버전 95.0.1020.20: 10월 11일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-950102014-october-5"></a>버전 95.0.1020.14: 10월 5일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-95010209-september-28"></a>버전 95.0.1020.9: 9월 28일

### <a name="feature-updates"></a>기능 업데이트

- **Microsoft Edge SharePoint Online 라이브러리 파일 탐색기 지원에서 보기**  이제 온라인 최신 문서 라이브러리에 대해 파일 탐색기에서 보기 기능을 SharePoint 수 있습니다. 이 환경을 표시하고 사용자에게 작동하려면 "Microsoft Edge SharePoint 페이지의 파일 탐색기 기능 구성 [SharePoint"](/deployedge/microsoft-edge-policies#configureviewinfileexplorer) 정책을 사용하도록 설정하고 Microsoft Edge Online 테넌트 구성을 업데이트해야 합니다. 자세한 내용은 다음을 SharePoint 파일 탐색기를 사용하여 파일 Microsoft Edge - SharePoint [보기를 Microsoft 365 | Microsoft Docs.](/SharePoint/sharepoint-view-in-edge)

- **인트라넷 영역 파일 URL 링크는 Windows 파일 탐색기에서 열립니다.**  인트라넷 영역 HTTPS 웹 사이트에서 시작된 인트라넷 영역 파일에 대한 파일 URL 링크를 허용하여 해당 파일 또는 디렉터리에 대한 Windows 파일 탐색기를 열 수 있습니다. [IntranetFileLinksEnabled](/deployedge/microsoft-edge-policies#intranetfilelinksenabled) 정책을 사용하여 이 환경을 사용하도록 설정할 수 있습니다.

- **다운로드 환경 개선**  사용자 환경 다운로드에 대한 지원이 점진적 웹 응용 프로그램 PWAS 및 WebView로 확장되고 있습니다. 또한 파일 탐색기 데스크톱으로 끌어서 놓기를 지원합니다.

- **PDF 문서에서 중단한 위치에서부터 시작합니다.**  PDF 문서를 마지막으로 닫은 위치에서 읽기를 다시 시작할 수 있습니다.

- **효율성 모드는 노트북이 배터리 절약 모드 모드로 전환되면 배터리 사용 시간을 연장합니다.**  노트북이 배터리 절약 모드 모드로 전환되면 효율성 모드가 활성화 되어 브라우저에서 리소스 사용량을 관리하여 컴퓨터의 배터리 사용 시간을 연장할 수 있습니다. 효율성 모드가 활성화될 때, 배터리가 언플러그되지 않은 상태 및 낮은 배터리, 언플러그된, 항상 및 사용 안 하게 되는 경우의 네 가지 옵션이 있습니다. 참고: 제어된 기능 출시입니다. 배터리가 있는 디바이스에는 기능이 켜져 있습니다.

***새 정책***

- [BrowserLegacyExtensionPointsBlockingEnabled](/DeployEdge/microsoft-edge-policies#browserlegacyextensionpointsblockingenabled) - 브라우저 레거시 확장 지점 차단을 사용하도록 설정.
- [CrossOriginWebAssemblyModuleSharingEnabled](/DeployEdge/microsoft-edge-policies#crossoriginwebassemblymodulesharingenabled) - WebAssembly 모듈을 원본 간으로 보낼 수 있는지 여부를 지정합니다.
- [DisplayCapturePermissionsPolicyEnabled](/DeployEdge/microsoft-edge-policies#displaycapturepermissionspolicyenabled) - 디스플레이 캡처 권한-정책을 선택하거나 건너뜁니다.
- [InternetExplorerIntegrationWindowOpenHeightAdjustment](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationwindowopenheightadjustment) - IE 모드 페이지에서 원본으로 하는 window.open 높이와 Microsoft Edge 모드 페이지 간의 픽셀 조정을 구성합니다.
- [InternetExplorerIntegrationWindowOpenWidthAdjustment](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationwindowopenheightadjustment) - IE 모드 페이지에서 원본으로 하는 window.open 너비와 Microsoft Edge 모드 페이지 사이의 픽셀 조정을 구성합니다.
- [IntranetFileLinksEnabled](/DeployEdge/microsoft-edge-policies#intranetfilelinksenabled) - 파일 탐색기에서 Microsoft Edge 인트라넷 영역 파일 URL Windows 허용합니다.
- [ShadowStackCrashRollbackBehavior](/DeployEdge/microsoft-edge-policies#shadowstackcrashrollbackbehavior) - ShadowStack 크래시 롤백 동작을 구성합니다.
- [VisualSearchEnabled](/DeployEdge/microsoft-edge-policies#visualsearchenabled) - 시각적 검색을 사용하도록 설정

***폐기된 정책***

- [InternetExplorerIntegrationTestingAllowed](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationtestingallowed) - Internet Explorer 모드 테스트를 허용합니다.
- [LegacySameSiteCookieBehaviorEnabled](/DeployEdge/microsoft-edge-policies#legacysamesitecookiebehaviorenabled) - 기본 레거시 SameSite 쿠키 동작 설정을 사용합니다.

## <a name="version-94099223-september-17"></a>버전 94.0.992.23: 9월 17일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-94099219-september-13"></a>버전 94.0.992.19: 9월 13일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-94099214-september-7"></a>버전 94.0.992.14: 9월 7일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-9409929-september-2"></a>버전 94.0.992.9: 9월 2일

### <a name="feature-updates"></a>기능 업데이트

- **Microsoft Edge 및 안정 채널의 업데이트에 대한 4주 케이던스로 이동하는 것이 좋습니다.**  주 버전에 대해 4주간의 새로운 릴리스 주기를 채택할 것입니다. 결정에 대한 자세한 내용은 다음을 읽어 볼 수 있습니다. https://blogs.windows.com/msedgedev/2021/03/12/new-release-cycles-microsoft-edge-extended-stable/

- **새로운 확장 안정 옵션이 제공됩니다.**  Microsoft는 관리되는 엔터프라이즈 고객에게 새로운 확장 안정 옵션을 제공하고 있습니다. 확장 안정 옵션은 짝수 버전으로 유지되며 8주마다 업데이트됩니다. 격주로 보안 업데이트가 있을 예정입니다.  추가 정보: https://blogs.windows.com/msedgedev/2021/07/15/opt-in-extended-stable-release-cycle/

- **MHTML 파일을 여는 기본 동작이 개선되었습니다.**  MHTML 파일이 Microsoft Edge에서 저장되지 않은 경우(Microsoft Edge에서 다른 이름으로 저장 또는 다른 이름으로 페이지 저장 옵션 사용) IE 모드가 활성화된 경우 MHTML 파일은 IE 모드에서 계속 열립니다. 파일이 Microsoft Edge에서 저장되었다면 이제 Microsoft Edge에서 열립니다.  이 변경 사항은 Microsoft Edge에서 저장할 때 IE 모드에서 MHTML 파일을 열 때 관찰된 렌더링 문제를 수정합니다.

- **컨텍스트를 보호하기 위해 사설 네트워크 요청을 제한합니다.** 인터넷 페이지에서 로컬(인트라넷) 네트워크의 리소스에 액세스하려면 해당 페이지가 HTTPS를 통해 전달되어야 합니다. 이 변경은 Microsoft Edge 기반으로 하는 Chromium 프로젝트에서 발생합니다. 자세한 내용은 [크롬 플랫폼 상태 항목](https://chromestatus.com/feature/5436853517811712)으로 이동합니다. 비보안 페이지와의 호환성을 유지해야 하는 시나리오를 지원하기 위해 [InsecurePrivateNetworkRequestAllowed](/deployedge/microsoft-edge-policies#insecureprivatenetworkrequestsallowed) 및 [InsecurePrivateNetworkRequestAllowedForUrls](/deployedge/microsoft-edge-policies#insecureprivatenetworkrequestsallowedforurls)의 두 가지 호환성 정책을 사용할 수 있습니다.

- **혼합 콘텐츠 다운로드를 차단합니다.** 보안 페이지는 다른 보안 페이지에서 호스팅되는 파일만 다운로드하고 비보안(비 HTTPS) 페이지에서 호스팅되는 다운로드는 보안 페이지에서 시작하면 차단됩니다. 이 변경은 Microsoft Edge 기반으로 하는 Chromium 프로젝트에서 발생합니다. 자세한 내용은 [Google 보안 블로그 항목](https://security.googleblog.com/2020/02/protecting-users-from-insecure_6.html)으로 이동하세요.

- **온-프레미스 계정에 대한 암시적 로그인을 활성화합니다.**   OnlyOnPremisesImplicitSigninEnabled 정책을 활성화하면 암시적 로그인에 대해 온-프레미스 계정만 활성화됩니다.  Microsoft Edge는 MSA 또는 AAD 계정에 암시적으로 로그인을 시도하지 않습니다. 온-프레미스 계정에서 AAD 계정으로의 업그레이드도 중지됩니다.

- **PDF 문서에 자유 형식 텍스트 상자가 추가되었습니다.**  이제 양식을 채우고 표시되는 메모를 추가하는 데 사용할 수 있는 PDF 문서에 무료 양식 텍스트 상자를 추가할 수 있습니다.

- **암호를 쉽게 업데이트합니다.**  이제 브라우저에서 특정 웹 사이트의 암호 변경 페이지로 바로 이동하여 시간을 절약하고 페이지를 수동으로 탐색할 필요가 없습니다. 이 페이지에 있는 경우 브라우저는 기존 암호를 자동으로 입력하고 강력하고 고유한 새 암호를 제안합니다.  참고: 현재 이 기능은 제한된 수의 사이트에서 사용할 수 있습니다.  

- **새 접근성 설정 페이지입니다.** 접근성 관련 설정을 한 페이지에 모았습니다. 기본 설정 목록에서 새로운 edge://settings/accessibility 페이지를 찾을 수 있습니다. 여기에서 웹 페이지를 더 크게 만들고 초점 영역 주위에 높은 가시성 개요를 표시하는 설정 및 웹 탐색 환경을 개선하는 데 도움이 될 수 있는 기타 설정을 찾을 수 있습니다. Microsoft Edge의 향후 버전에서 여기에 새로운 설정을 계속 추가할 예정입니다.

***새로운 정책***

- [ApplicationGuardPassiveModeEnabled](/DeployEdge/microsoft-edge-policies#applicationguardpassivemodeenabled) Application Guard 사이트 목록 구성을 무시하고 Edge를 정상적으로 탐색합니다.
- [OnPremisesImplicitSigninEnabled](/DeployEdge/microsoft-edge-policies#onlyonpremisesimplicitsigninenabled) 암시적 로그인에 대해 사용하도록 설정된 온-프레미스 계정만
- [WebRtcRespectOsRoutingTableEnabled](/DeployEdge/microsoft-edge-policies#webrtcrespectosroutingtableenabled) WebRTC를 통해 피어 투 피어 연결을 만들 때 Windows OS 라우팅 테이블 규칙 지원 활성화

***폐기된 정책***

- [UserAgentClientHintsEnabled](/DeployEdge/microsoft-edge-policies#useragentclienthintsenabled) 사용자 에이전트 클라이언트 힌트 기능 사용

## <a name="version-93096133-august-27"></a>버전 93.0.961.33: 8월 27일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-93096127-august-20"></a>버전 93.0.961.27: 8월 20일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-93096124-august-18"></a>버전 93.0.961.24: 8월 18일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-93096111-august-3"></a>버전 93.0.961.11: 8월 3일

### <a name="feature-updates"></a>기능 업데이트

- **Microsoft Edge 초기 기본 설정입니다.**  Microsoft Edge 버전 93부터 초기 Microsoft Edge 를 추가하면 엔터프라이즈에 배포하는 것이 더 [쉬워집니다.](/deployedge/initial-preferences-support-on-microsoft-edge-browser)

- **Microsoft Edge의 IE 모드는 "병합 금지" 동작을 지원합니다.**  Microsoft Edge 버전 93부터 Microsoft Edge IE 모드는 "병합 안 Microsoft Edge"를 지원합니다. 최종 사용자의 경우 IE 모드 응용 프로그램에서 새 브라우저 창을 시작하면 IE11의 동작과 비슷한 별도의 세션에 있습니다. 세션 공유를 방지해야 하는 사이트를 구성하려면 사이트 목록을 조정해야 합니다. 이면에서는 Microsoft Edge의 각 창에서 IE 모드 탭이 해당 창 내에 처음 방문하는 경우 지정된 "병합 금지" 사이트 중 하나일 경우 해당 창에서 마지막 IE 모드 탭이 닫힐 때까지 해당 창이 다른 모든 Microsoft Edge 창과 다른 "병합 금지" IE 세션으로 잠깁니다. [여기](/deployedge/edge-ie-mode-faq#does-ie-mode-on-microsoft-edge-support-the--no-merge--option-that-was-supported-in-internet-explorer-11-)에서 자세히 알아보세요.

- **탭 그룹**  탭을 사용자 정의 그룹으로 분류하는 기능을 사용하면 여러 작업 스트림에서 탭을 보다 효과적으로 찾고 전환하고 관리할 수 있습니다. 이를 위해 버전 93에서 시작하여 탭 Microsoft Edge 켜고 있습니다.

- **세로 탭을 사용하는 동안 제목 표시줄을 숨깁니다.**  세로 탭에서 브라우저의 제목 표시줄을 숨겨 몇 개의 픽셀을 다시 가져옵니다. Microsoft Edge 버전 93부터 edge://settings/appearance 도구 모음 사용자 지정 섹션에서 세로 탭 모드에서 제목 표시줄을 숨기는 옵션을 선택합니다.

- **호버 도구 모음의 PiP(사진 비디오 사진)입니다.**  버전 Microsoft Edge 버전 93부터 PiP(그림) 모드로 전환하기가 훨씬 쉬워집니다. 지원되는 비디오 위로 마우스를 가져가면 PiP 창에서 해당 비디오를 볼 수 있는 도구 모음이 나타납니다.  참고: 현재 macOS의 Microsoft Edge 사용할 수 있습니다.  사용자에 대한 롤아웃을 계속하는 Windows 다시 확인해보아야 합니다.

- **TLS에서 3DES 제거**  Microsoft Edge 버전 93부터는 TLS_RSA_WITH_3DES_EDE_CBC_SHA 암호 제품군에 대한 지원이 제거됩니다. 이 변경은 Microsoft Edge 기반으로 하는 Chromium 프로젝트에서 발생합니다. 자세한 내용은 [크롬 플랫폼 상태 항목](https://chromestatus.com/feature/6678134168485888)으로 이동합니다. 또한 Microsoft Edge 버전 93에서는 [TripleDESEnabled](/deployedge/microsoft-edge-policies#tripledesenabled) 정책을 사용하여 오래된 서버와의 호환성을 유지해야 하는 시나리오를 지원할 수 있습니다. 이 호환성 정책은 사용되지 않으며 Microsoft Edge 버전 95에서 작동이 중지됩니다. 그 전에 영향을 받는 서버를 업데이트해야 합니다.

- **ClickOnce 및 DirectInvoke 프롬프트를 바이패스하는 정책입니다.**  지정된 도메인에서 ClickOnce의 프롬프트와 DirectInvoke의 특정 파일 형식 앱을 바이패스할 수 있도록 정책을 업데이트했습니다. 이렇게 하려면 다음을 수행해야 합니다.

  - [ClickOnceEnabled](/deployedge/microsoft-edge-policies#clickonceenabled)나 [DirectInvokeEnabled](/deployedge/microsoft-edge-policies#directinvokeenabled) 사용
  - [AutoOpenFileTypes](/deployedge/microsoft-edge-policies#autoopenfiletypes) 정책을 사용하고 ClickOnce 및 QAZ를 사용하지 않도록 설정해야 하는 특정 파일 형식 목록 설정
  - [AutoOpenAllowedForURLs](/deployedge/microsoft-edge-policies#autoopenallowedforurls) 정책을 사용하도록 설정하고 ClickOnce 및 DirectInvoke를 사용하지 않도록 설정할 특정 도메인 목록을 설정

  참고: AutoOpenAllowedForURLs는 AutoOpenFileTypes에 대한 금지 정책입니다. AutoOpenAllowedForURLs가 설정되지 않고 AutoOpenFileTypes가 설정된 경우 나열된 파일 형식이 모든 URL에서 자동으로 열립니다.

### <a name="new-policies"></a>새 정책

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

#### <a name="deprecated-policy"></a>더 이상 사용되지 않는 정책

- [LegacySameSiteCookieBehaviorEnabled](/DeployEdge/microsoft-edge-policies#legacysamesitecookiebehaviorenabled) 기본 레거시 SameSite 쿠키 동작 설정 사용

#### <a name="obsoleted-policy"></a>폐기된 정책

- [NewTabPageSetFeedType](/DeployEdge/microsoft-edge-policies#newtabpagesetfeedtype) 새 Microsoft Edge 탭 페이지 환경 구성

#### <a name="additional-change"></a>추가 변경 내용

- [ConfigureShare](/DeployEdge/microsoft-edge-policies#configureshare) Mac 플랫폼 지원 추가

## <a name="version-93096118-august-10"></a>버전 93.0.961.18: 8월 10일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-92090262-july-29"></a>버전 92.0.902.62: 7월 29일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-92090255-july-21"></a>버전 92.0.902.55: 7월 21일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-92090245-july-12"></a>버전 92.0.902.45: 7월 12일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-92090240-july-6"></a>버전 92.0.902.40: 7월 6일

다양한 버그와 성능 문제를 해결했습니다.

<!--Archive on Oct 27 From Version 92.0.902.22: June 21 to Version 89.0.774.23: February 8  -->
<!--- Archived from Version 87.0.664.18: October 26 to to version 89.0.774.18: February 3 ---->
<!--- Archived from Version 87.0.664.12: October 20 to to version 86.0.622.15: September 14 ---->
<!--- Archived to version 86.0.622.11: September 9 ---->
<!--- Archived to version 85.0.564.18: July 28 ---->

## <a name="see-also"></a>참고 항목

- [Microsoft Edge Enterprise 방문 페이지](https://aka.ms/EdgeEnterprise)
