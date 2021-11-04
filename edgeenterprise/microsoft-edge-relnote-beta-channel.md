---
title: 베타 채널 용 Microsoft Edge 릴리스 정보
ms.author: aguta
author: dan-wesley
manager: srugh
ms.date: 11/03/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 베타 채널 용 Microsoft Edge 릴리스 정보
ms.openlocfilehash: bcc2ecf91c6d90443de26b5bff1c744d7582aa18
ms.sourcegitcommit: 4ec03873a85f065d9bfa6203cfe6c3e938f79bc5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "12155105"
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

- **IE 모드와 최신 브라우저 간의 핸드오프가 개선되어 있습니다.**  이 버전의 Microsoft Edge 버전부터 Microsoft Edge 및 Internet Explorer 모드 간의 탐색에는 양식 데이터와 추가 HTTP 헤더가 포함됩니다. 참조 헤더, 게시 데이터, 양식 데이터 및 요청 메서드는 두 환경 전체에서 올바르게 전달됩니다. [InternetExplorerIntegrationComplexNavDataTypes](/deployedge/microsoft-edge-policies#internetexplorerintegrationcomplexnavdatatypes) 정책을 사용하여 포함해야 하는 데이터 형식을 지정할 수 있습니다. 자세한 내용은 이 FAQ: 응용 프로그램에 IE 모드와 [IE](./edge-ie-mode-faq.md#my-application-requires-transferring-post-data-between-ie-mode-and-microsoft-edge-is-this-supported)모드 간에 POST 데이터를 전송해야 Microsoft Edge.

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

<!-- archive from Version 94.0.992.9: September 2 to Version 92.0.902.40: July 6 -->
<!--Archive on Oct 27 From Version 92.0.902.22: June 21 to Version 89.0.774.23: February 8  -->
<!--- Archived from Version 87.0.664.18: October 26 to to version 89.0.774.18: February 3 ---->
<!--- Archived from Version 87.0.664.12: October 20 to to version 86.0.622.15: September 14 ---->
<!--- Archived to version 86.0.622.11: September 9 ---->
<!--- Archived to version 85.0.564.18: July 28 ---->

## <a name="see-also"></a>참고 항목

- [Microsoft Edge Enterprise 방문 페이지](https://aka.ms/EdgeEnterprise)
