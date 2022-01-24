---
title: 베타 채널 용 Microsoft Edge 릴리스 정보
ms.author: aguta
author: dan-wesley
manager: srugh
ms.date: 01/07/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 베타 채널 용 Microsoft Edge 릴리스 정보
ms.openlocfilehash: ddb745c206dc392dc1dbb46a0522db9648ba624e
ms.sourcegitcommit: e7f3098d8b7d91cae20b5778a71a87daababc312
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "12297716"
---
# <a name="release-notes-for-microsoft-edge-beta-channel"></a>Microsoft Edge 베타 채널에 대한 릴리스 정보

이 릴리스 정보는 Microsoft Edge 베타 채널에 포함된 새로운 기능 및 비보안 업데이트에 대한 정보를 제공합니다. 이러한 릴리스 정보의 보관된 버전은 채널에 대한 보관된 릴리스 [Microsoft Edge Beta 있습니다.](./microsoft-edge-relnote-archive-beta-channel.md)

> [!NOTE]
> Microsoft Edge 웹 플랫폼은 사용자 환경, 보안 및 개인 정보 개선을 위해 지속적으로 진화하고 있습니다. 자세히 알아보려면 [Microsoft Edge에 적용될 사이트 호환성에 영향을 미치는 변경 사항](/microsoft-edge/web-platform/site-impacting-changes)을 참조하세요.

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

## <a name="version-970107221-december-1"></a>버전 97.0.1072.21: 12월 1일

### <a name="feature-updates"></a>기능 업데이트

- **디바이스에서 여러 회사 또는 학교 계정이 로그인될 때 현재 프로필을 사용하여 웹 사이트에 로그인합니다.** 디바이스에 여러 회사 또는 학교 계정이 로그인된 경우 사용자는 계정 선택기에서 계정을 선택해 웹 사이트 방문을 계속할지 묻는 요청이 표시됩니다. 이 릴리스에서는 사용자가 현재 프로필에 Microsoft Edge 회사 및 학교 계정을 사용하여 자동으로 웹 사이트에 로그인할 수 있도록 허용하라는 메시지가 표시됩니다. 사용자는 기본 설정/프로필 기본 설정에서 설정 **수 있습니다.**

- **macOS에서 Microsoft 끝점 DLP(데이터 손실 방지)에 대한 지원을 추가합니다.** Microsoft 끝점 DLP 정책 적용은 macOS에서 기본적으로 사용할 수 있습니다.

- **디지털 서명된 PDF 파일을 열 수 있습니다.**  디지털 서명은 문서의 인증 및 변경 내용의 유효성을 검사하는 데 광범위하게 사용됩니다. 사용자는 추가 기능 없이도 브라우저에서 직접 PDF 파일의 서명 유효성을 검사할 수 있습니다.

- **인용은 Microsoft Edge.** 연구를 위한 출처를 인용하는 것은 학생에게 일반적인 요구 사항입니다. 많은 연구 참조 및 출처를 관리해야 하며, 이는 쉬운 작업이 아닙니다. 또한 이러한 인문을 APA, MLA 및 시카고와 같은 적절한 인문 형식으로 번역해야 합니다. 이 새로운 인용"Microsoft Edge(미리 보기로 제공)를 통해 학생들은 온라인으로 조사할 때 인용을 관리하고 생성하는 더 나은 방법을 제공합니다. 컬렉션 또는 **설정(Alt-F)** 등에서 인용을 설정하면 Microsoft Edge 나중에 사용할 수 있는 인용을 자동으로 생성하여 학생이 연구에 집중할 수 있도록 합니다. 인용을 완료하면 이러한 인용을 최종 결과물로 쉽게 컴파일할 수 있습니다. 자세한 내용은 에서 인용 미리 [보기를 Microsoft Edge.](https://blogs.windows.com/msedgedev/2021/11/04/preview-citations-feature-edge/)

### <a name="policy-updates"></a>정책 업데이트

#### <a name="new-policies"></a>새 정책

- [AccessibilityImageLabelsEnabled](/DeployEdge/microsoft-edge-policies#accessibilityimagelabelsenabled) - Microsoft Enabled에서 이미지 설명 다운로드
- [CORSNonWildcardRequestHeadersSupport](/DeployEdge/microsoft-edge-policies#corsnonwildcardrequestheaderssupport) - CORS 비 와일드카드 요청 헤더 지원 사용
- [EdgeDiscoverEnabled](/DeployEdge/microsoft-edge-policies#edgediscoverenabled) - 검색 기능 Microsoft Edge
- [EdgeEnhanceImagesEnabled](/DeployEdge/microsoft-edge-policies#edgeenhanceimagesenabled) - 사용 가능한 이미지 향상
- [InternetExplorerModeTabInEdgeModeAllowed](/DeployEdge/microsoft-edge-policies#internetexplorermodetabinedgemodeallowed) - Internet Explorer 모드로 구성된 사이트가 Microsoft Edge
- [SameOriginTabCaptureAllowedByOrigins](/DeployEdge/microsoft-edge-policies#sameorigintabcaptureallowedbyorigins) - 이러한 원점에서 동일한 원본 탭 캡처 허용
- [ScreenCaptureAllowedByOrigins](/DeployEdge/microsoft-edge-policies#screencaptureallowedbyorigins) - 이러한 원본에 대한 데스크톱, 창 및 탭 캡처 허용
- [SerialAllowAllPortsForUrls](/DeployEdge/microsoft-edge-policies#serialallowallportsforurls) - 모든 직렬 포트를 연결할 수 있는 권한을 사이트가 자동으로 부여합니다.
- [SerialAllowUsbDevicesForUrls](/DeployEdge/microsoft-edge-policies#serialallowusbdevicesforurls) - USB 직렬 장치에 연결할 수 있는 권한을 사이트에 자동으로 부여합니다.
- [SmartScreenDnsRequestsEnabled](/DeployEdge/microsoft-edge-policies#smartscreendnsrequestsenabled) - DNS Microsoft Defender SmartScreen 사용
- [TabCaptureAllowedByOrigins](/DeployEdge/microsoft-edge-policies#tabcaptureallowedbyorigins) - 이러한 원점에 대한 탭 캡처 허용
- [WebSQLInThirdPartyContextEnabled](/DeployEdge/microsoft-edge-policies#websqlinthirdpartycontextenabled) - 타사 컨텍스트에서 WebSQL을 다시 사용하도록 설정
- [WindowCaptureAllowedByOrigins](/DeployEdge/microsoft-edge-policies#windowcaptureallowedbyorigins) - 이러한 원본에 대한 창 및 탭 캡처 허용

## <a name="version-960105434-november-23"></a>버전 96.0.1054.34: 11월 23일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-960105426-november-17"></a>버전 96.0.1054.26: 11월 17일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-960105424-november-16"></a>버전 96.0.1054.24: 11월 16일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-960105413-november-5"></a>버전 96.0.1054.13: 11월 5일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-96010548-november-1"></a>버전 96.0.1054.8: 11월 1일

### <a name="feature-updates"></a>기능 업데이트

- **프로토콜 링크를 통해 PWA(점진적 웹앱)를 직접 실행합니다.** 설치된 PWAS가 보다 통합된 환경을 위해 특정 프로토콜을 사용하는 링크를 처리하도록 합니다.

- **수학 해소를 통해 수학 문제를 해결하는 방법을 학습합니다.** 다양한 수학 개념에 대한 도움말을 Microsoft Edge 수학 해법을 사용할 수 있습니다. 이러한 개념은 기본 연산 및 정방형 수식에서 삼각형 및 계산까지 다양합니다. 수학 해법을 사용하면 필기 또는 인쇄된 수학 문제를 그림으로 찍은 다음 단계별 지침과 함께 즉각적인 해결 방법을 통해 도움이 없이 솔루션에 도달하는 방법을 배울 수 있습니다. 수학 해법은 수학 문제를 쉽게 입력하는 데 사용할 수 있는 수학 키보드도 함께 제공합니다. 이 키보드를 사용하면 기존 키보드를 검색하여 필요한 수학 문자를 찾을 필요가 없습니다. 문제를 해결한 후 수학 해기에서는 퀴즈, 워크시트 및 비디오 자습서를 계속 학습할 수 있는 옵션을 제공합니다.

- **PDF에서 자유형 강조 표시** 자유형 하이퍼링크를 추가하여 PDF 보기 및 마크업 환경이 개선됩니다. 액세스 권한이 없는 PC 및 스캔한 문서의 섹션을 강조할 수 있습니다.

- **하드웨어 적용 스택 보호.**  Microsoft Edge(Intel 11세대)의 브라우저 프로세스에 하드웨어 종속 제어 흐름을 사용하는 더욱 안전한 검색 모드를 지원하기 시작할 것입니다. 또는 AMD Zen 3) 참고: 제어된 기능 롤아웃이기 때문에 일부 장치에서 이 기능을 사용할 수 없는 경우도 있습니다. 그룹 정책을 사용하여 IFEO(이미지 파일 실행 옵션)를 조작하여 하드웨어 적용 스택 보호를 활성화하거나 사용하지 않도록 설정할 수 있습니다.

- **입력 입력 사이트용 새 경고 대화 상자입니다.** 이제 브라우저에서 다른 사이트와 비슷한 URL이 있는 일부 사이트에 경고가 표시됩니다. 이 UI는 클라이언트 쪽 지론을 사용하여 사용자에게 인기 있는 웹 사이트를 스푸핑할 수 있는 사이트에 대해 경고합니다. 자세한 내용은 [Typosquatting이란? 을 참조하세요.](https://support.microsoft.com/topic/what-is-typosquatting-54a18872-8459-4d47-b3e3-d84d9a362eb0)

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

<!-- archive from version 95.0.1020.9: September 28 to version 94.0.992.14: September 7 ---->
<!-- archive from Version 94.0.992.9: September 2 to Version 92.0.902.40: July 6 -->
<!--Archive on Oct 27 From Version 92.0.902.22: June 21 to Version 89.0.774.23: February 8  -->
<!--- Archived from Version 87.0.664.18: October 26 to to version 89.0.774.18: February 3 ---->
<!--- Archived from Version 87.0.664.12: October 20 to to version 86.0.622.15: September 14 ---->
<!--- Archived to version 86.0.622.11: September 9 ---->
<!--- Archived to version 85.0.564.18: July 28 ---->

## <a name="see-also"></a>참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
