---
title: Microsoft Edge의 PDF 읽기 프로그램
ms.author: adigan
author: AndreaLBarr
manager: balajek
ms.date: 07/08/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edg의 PDF 읽기 프로그램에 대해 자세히 알아봅니다.
ms.openlocfilehash: e8cf690f818e0fa103aa4f17154d9f95431287b5
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "11979597"
---
# <a name="pdf-reader-in-microsoft-edge"></a>Microsoft Edge의 PDF 읽기 프로그램

PDF 파일은 일상적인 생활의 많은 부분을 구성합니다. 계약, 뉴스레터, 양식, 리서치 문서, 이력서 등의 형태로 제공됩니다. 이러한 파일은 엔터프라이즈에서 채택할 수 있는 신뢰성과 안전성을 갖춘 강력한 PDF 읽기 프로그램에 대한 필요성을 강조합니다.

Microsoft Edge에는 로컬 PDF 파일, 온라인 PDF 파일 또는 웹 페이지에 포함된 PDF 파일을 열 수 있는 기본 제공 PDF 읽기 프로그램이 함께 제공됩니다. 잉크와 강조 표시를 사용하여 이 파일에 주석을 달 수 있습니다. 해당 PDF 읽기 프로그램에서는 웹 페이지 및 PDF 문서 요구 사항을 충족하는 단일 응용 프로그램을 제공합니다. Microsoft Edge PDF 읽기 프로그램은 Windows 및 macOS 데스크톱 플랫폼에서 작동하는 안전하고 신뢰할 수 있는 응용 프로그램입니다.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.

## <a name="prerequisites-support-and-constraints"></a>필수 구성 요소, 지원 및 제약 조건

다음 표에서는 각 PDF 읽기 프로그램 기능을 지원하는 Microsoft Edge의 채널과 버전을 보여 줍니다.

| 기능 | 안정적인 채널 버전 |
|---------|------------------------|
| 로컬, 온라인 및 포함된 PDF 파일 보기 및 인쇄 | 79.0.309.71                |
| 기본 양식 채우기<br>(JavaScript 폼이 지원되지 않음) | 79.0.309.71           |
|목차| 86.0.622.38 |
| 페이지 보기 | 88.0.705.50 |
| 캐럿 모드 브라우징 |87.0.664.41 |
| 수동 입력  | 80.0.361.48            |
| 잉크 사용자 지정 | 83.0.478.54  |
| Highlight  | 81.0.416.53         |
| 텍스트 메모 | 88.0.705.50 |
| 소리 내어 읽기 | 84.0.522.63  |
| 동일한 비즈니스 테넌트에서 Microsoft Information Protection(MIP) 보기 | 80.0.361.48의 Windows 지원<br>81.0.416.53의 Mac 지원 |
| 비즈니스 테넌트간에 보호돤 파일인 Microsoft Information Protection(MIP) 보기 | 91.0.864.37  |
|  IRM(정보 권한 관리) 보호 파일 보기  | 83.0.478.37            |


### <a name="constraints"></a>제약 조건

현재 PDF 읽기 프로그램에 대해 다음 제한 사항을 확인합니다.

-  XFA(XML Forms Architecture)는 Microsoft Edge에서 지원되지 않는 레거시 형태의 양식입니다.
-  현재 지원되지 않는 접근성 시나리오와 관련된 문서는 [Microsoft 접근성 규칙 보고서](https://cloudblogs.microsoft.com/industry-blog/government/2018/09/11/accessibility-conformance-reports/) 블로그를 참조하세요.

## <a name="features"></a>기능

Microsoft Edge에 기본 제공되는 PDF 읽기 프로그램은 확대/축소, 회전, 페이지/너비에 맞추기, 페이지로 이동 및 검색과 같은 기본적인 읽기 및 탐색 기능과 함께 제공됩니다. 이러한 기능은 PDF 콘텐츠 맨 위에 있는 고정할 수 있는 도구 모음을 통해 액세스할 수 있습니다. 이 섹션에서는 몇 가지 중요한 기능에 대해 간략하게 설명합니다. 다음 스크린샷은 PDF 읽기 프로그램 도구 모음을 보여 줍니다.

![PDF 읽기 프로그램 도구 모음](media/microsoft-edge-pdf/pdf-reader-toolbar.png)

### <a name="table-of-contents"></a>목차

목차를 사용하면 사용자가 목차가 있는 PDF 문서를 쉽게 탐색할 수 있습니다. 사용자가 목차 아이콘을 클릭하면 PDF 문서에 레이블이 지정되어 있는 섹션과 하위 섹션 목록을 표시하는 탐색 창이 표시됩니다. 그러면 사용자가 창에서 레이블을 클릭하여 문서의 해당 섹션으로 이동할 수 있습니다. 창은 필요한 시간만큼 열려 있으며 사용자가 문서 읽기로 돌아가고 싶을 때 닫을 수 있습니다. 다음 스크린샷에서는 열려 있는 문서의 탐색 창을 보여 줍니다.

![목차를 사용하여 PDF 읽기 프로그램 탐색](media/microsoft-edge-pdf/pdf-reader-toc.png)

### <a name="page-view"></a>페이지 보기

Microsoft Edge는 개발자 및 Canary 채널에서 PDF 문서에 대한 다양한 보기를 지원합니다. 문서의 레이아웃을 단일 페이지 보기에서 나란히 표시되는 두 페이지로 변경할 수 있습니다. PDF 문서를 보는 방법을 변경하려면 사용자가 PDF 도구 모음에서 페이지 보기 단추를 클릭한 다음 사용할 보기를 선택할 수 있습니다. 다음 스크린샷에는 두 페이지 보기가 표시됩니다.

![문서의 두 페이지 보기를 사용하는 PDF 뷰어](media/microsoft-edge-pdf/pdf-reader-page-view.png)

### <a name="caret-mode-browsing"></a>커서 모드 브라우징

커서 브라우징은 Microsoft Edge에서 연 PDF 파일에 사용할 수 있습니다. 즉, 사용자가 키보드를 사용하여 PDF 파일을 조작할 수 있습니다. 사용자가 브라우저의 아무 곳에서 F7 키를 누르면 커서 브라우징을 설정해야 하는지 묻습니다. 사용하도록 설정하면 브라우저에서 연 모든 콘텐츠(PDF 파일 또는 웹 페이지)에 커서 브라우징을 사용할 수 있습니다. 사용자가 F7을 다시 누르면 커서 브라우징이 꺼집니다. 커서 브라우징이 활성화되고 콘텐츠에 포커스가 있는 경우 PDF 파일에 깜박이는 커서가 표시됩니다. 커서를 이동하는 동안 Shift 키를 눌러 파일을 탐색하거나 텍스트를 선택하는 데도 캐럿을 사용할 수 있습니다. 이 기능을 사용하면 사용자가 쉽게 강조 표시로 요소를 만들거나, 링크로 요소와 상호작용하고 키보드를 사용하여 필드를 형성할 수 있습니다. 다음 스크린샷은 커서 모드 브라우징을 켜기 위한 팝업 메뉴를 보여 줍니다.

![커서 모드 브라우징을 위한 PDF 읽기 프로그램 메뉴](media/microsoft-edge-pdf/pdf-reader-caret-mode.png)

### <a name="inking"></a>수동 입력

PDF 파일에서 수동 입력 기능을 사용하여 간편하게 기록하여 손쉽게 참조하거나, 서명하거나, PDF 양식을 작성할 수 있습니다. 이제 Microsoft Edge에서 이 기능을 사용할 수 있습니다. 필요한 경우 PDF 파일의 수동 입력 외에, 색상 및 스트로크 너비를 사용하여 PDF 파일의 여러 부분을 돋보이게 표시할 수 있습니다. 다음 스크린샷은 PDF 페이지에 수동 입력을 추가하는 방법을 보여 줍니다.

![PDF 페이지에 수동 입력 추가](media/microsoft-edge-pdf/pdf-reader-inking.png)

### <a name="highlight"></a>Highlight

Microsoft Edge의 PDF 읽기 프로그램에서 하이라이트를 추가하고 편집하는 기능을 제공합니다. 강조 표시를 만들려면 텍스트를 선택하여 텍스트를 마우스 오른쪽 단추로 클릭한 다음, 메뉴에서 하이라이트를 선택하고 원하는 색을 선택하면 됩니다. 펜이나 키보드를 사용하여 강조 표시를 만들 수도 있습니다. 다음 스크린샷은 사용 가능한 강조 표시 옵션을 보여 줍니다.

![PDF 읽기 프로그램의 강조 표시 옵션 사용](media/microsoft-edge-pdf/pdf-reader-highlight.png)

### <a name="text-notes"></a>텍스트 메모

PDF 파일을 읽는 동안 나중에 쉽게 참조할 수 있도록 텍스트 메모를 파일의 텍스트에 추가할 수 있습니다.

사용자는 메모를 추가하고 마우스 오른쪽 단추 클릭 상황에 맞는 메뉴를 호출하여 메모를 추가할 수 있습니다. 메뉴에서 **설명 추가** 옵션을 선택하면 사용자가 설명을 추가할 수 있는 텍스트 상자가 열립니다. 설명을 입력한 다음 확인 표시를 클릭하여 설명을 저장할 수 있습니다.

메모가 추가되면 선택한 텍스트가 강조 표시되어 메모를 나타내는 메모 아이콘이 나타납니다. 사용자는 해당 아이콘 위에 마우스를 대고 메모를 미리 보거나 메모를 클릭하여 메모를 열고 편집할 수 있습니다.

다음 스크린샷에는 강조 표시된 텍스트에 추가되는 메모가 표시됩니다.

![PDF 읽기 프로그램은 문서에 텍스트 메모를 추가합니다.](media/microsoft-edge-pdf/pdf-reader-text-note.png)

### <a name="read-aloud"></a>소리 내어 읽기

PDF를 소리 내어 읽으면 사용자에게 중요할 수 있는 다른 작업을 수행하는 동시에 PDF 콘텐츠를 듣는 편리함이 추가됩니다. 또한 청각 학습자가 콘텐츠에 집중하는 데 도움을 주므로 훨씬 쉽게 배울 수 있습니다. 다음 스크린샷에서는 소리 내어 읽기 예제를 보여 줍니다. 강조 표시된 부분은 현재 읽고 있는 텍스트를 보여 줍니다.

![PDF 읽기 프로그램에서 소리 내어 읽기에 강조 옵션 사용](media/microsoft-edge-pdf/pdf-reader-read-aloud-example.png)

### <a name="protected-pdfs"></a>보호된 PDF

[MIP(Microsoft Information Protection)](/microsoft-365/compliance/protect-information?preserve-view=true&view=o365-worldwide)을 사용하면 조직의 규정 준수 정책을 지키면서 다른 사용자와 안전하게 공동 작업을 할 수 있습니다. 파일이 보호된 경우, 사용자가 해당 파일을 사용할 수 있는 작업은 해당 사용자에게 할당된 사용 권한에 따라 결정됩니다.

> [!IMPORTANT]
> MIP에 라이선스가 필요합니다. 자세한 내용은 이 [Microsoft 365 라이선스 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)을 참조하세요.

이러한 파일은 다른 소프트웨어를 다운로드하거나 추가 기능을 설치할 필요 없이 브라우저에서 바로 열 수 있습니다. 이 기능은 MIP에서 제공하는 보안을 브라우저에 직접 통합하여 원활한 워크플로를 제공합니다.
비즈니스 테넌트 전체에서 MIP 보호 파일을 볼 수 있습니다. 소비자 ID를 사용하여 파일을 보는 것은 현재 지원하지 않습니다.

![보호된 PDF 문서.](media/microsoft-edge-pdf/pdf-reader-protected-pdf2.png)

MIP으로 보호된 파일 외에도, [IRM(Information Rights Management)](/microsoft-365/compliance/set-up-irm-in-sp-admin-center?preserve-view=true&view=o365-worldwide)으로 보호된 SharePoint 라이브러리의 PDF 파일을 브라우저에서 열 수 있습니다.

Microsoft Edge를 사용하여, 로컬이나 클라우드에 저장된 MIP으로 보호된 파일을 볼 수 있습니다. 로컬에 저장된 경우 브라우저에서 직접 파일을 열 수 있습니다. 클라우드 서비스에서 SharePoint로 파일을 연 경우에는 "브라우저에서 열기" 옵션을 사용해야 합니다.

Microsoft Edge에 로그인하는 데 사용된 프로필에 적어도 해당 파일에 대한 보기 권한이 있는 경우, 파일이 Microsoft Edge에서 열립니다.

![MIP로 보호되는 SharePoint PDF 페이지를 저장하라는 메시지가 표시됨](media/microsoft-edge-pdf/pdf-reader-sharepoint-irm.png)

### <a name="view-and-validate-certificate-based-digital-signatures"></a>인증서 기반 디지털 서명 보기 및 유효성 검사

이 디지털 세계에서는 문서에 있는 콘텐츠의 인증 및 소유권을 설정하는 것이 중요합니다. 인증서 기반 디지털 서명은 일반적으로 문서의 콘텐츠가 작성자가 의도한 내용과 동일하며 변경되지 않았는지 확인하기 위해 PDF 문서에서 사용됩니다. Microsoft Edge를 사용하면 PDF에서 인증서 디지털 서명을 보고 유효성을 검사할 수 있습니다.

더 많은 시나리오를 해결하도록 지원을 개선하기 위해 노력 중이며, 이에 대한 피드백을 기다립니다.

## <a name="accessibility"></a>접근성

PDF 읽기 프로그램은 Windows 및 macOS 장치에서 키보드 접근성, 고대비 모드 및 화면 읽기 프로그램 지원을 제공합니다.

### <a name="keyboard-accessibility"></a>키보드 접근성

사용자가 키보드를 사용하여 양식 필드 및 하이라이트와 같이, 사용자가 상호 작용할 수 있는 문서의 여러 부분을 탐색할 수 있습니다. 사용자는 커서 모드를 사용하여 키보드를 사용하여 PDF 파일을 탐색하고 상호작용할 수도 있습니다.

### <a name="high-contrast-mode"></a>고대비 모드

PDF 읽기 프로그램은 운영 체제 수준에서 정의된 설정을 사용하여 PDF 콘텐츠를 고대비 모드로 렌더링합니다.

### <a name="screen-reader-support"></a>화면 읽기 프로그램 지원

Windows 및 Mac 컴퓨터에서 화면 읽기 프로그램을 사용하여 PDF 파일을 탐색하고 읽을 수 있습니다.

## <a name="security-and-reliability"></a>보안 및 안정성

보안은 모든 조직에서 가장 중요한 개념에 속합니다. PDF 읽기 프로그램 보안은 Microsoft Edge 보안 설계의 필수 요소입니다. PDF 읽기 프로그램에서 가장 중요한 보안 기능 두 가지는 프로세스 격리 및 Application Guard(Microsoft Defender Application Guard)입니다.

- 프로세스 격리. 여러 웹 사이트에서 열린 PDF는 완전히 격리된 프로세스입니다. 브라우저는 다른 원본에서 열린 PDF 파일이나 웹 사이트와 통신할 필요가 없습니다. PDF 검색 기능은 손상된 PDF를 공격 표면으로 사용하려고 계획하는 공격으로부터 안전합니다.

- Application Guard Application Guard를 통해 관리자는 조직에서 신뢰하는 사이트 목록을 설정할 수 있습니다. 사용자가 다른 사이트를 여는 경우, 자체 컨테이너에서 실행되는 별도의 Application Guard 보호 창에서 열립니다. 컨테이너는 회사 네트워크와 사용자 컴퓨터에 있는 모든 데이터가 손상되지 않도록 보호하는 데 도움이 됩니다.<br><br>
이 보호 기능은 보고 있는 모든 온라인 PDF 파일에도 적용됩니다. 또한 Application Guard 창에서 다운로드한 모든 PDF 파일이 저장되고, 필요한 경우 컨테이너에서 다시 열립니다. 이렇게 하면 파일이 다운로드될 때뿐만 아니라, 전체 수명 주기 동안 환경을 안전하게 유지할 수 있습니다. 자세한 내용은 [Application Guard](./microsoft-edge-security-windows-defender-application-guard.md)를 참조하세요.

### <a name="reliability"></a>안정성

Microsoft Edge는 Chromium 기반이기 때문에 사용자는 다른 Chromium 기반 브라우저에서 볼 때와 동일한 수준의 안정성을 기대할 수 있습니다.

## <a name="deploy-and-update-pdf-reader"></a>PDF 읽기 프로그램 배포 및 업데이트

PDF 읽기 프로그램이 배포되고 Microsoft Edge 브라우저의 나머지 부분으로 업데이트됩니다. Microsoft Edge를 배포하는 방법에 대한 자세한 내용은 [수천 대의 장치에 Microsoft Edge 배포](microsoft-edge-video-deploy.md)를 참조하세요. [Microsoft Edge 설명서](./index.yml) 랜딩 페이지에서도 더 많은 배포 정보를 확인할 수 있습니다.

> [!TIP]
> Microsoft Edge를 조직의 기본 PDF 읽기 프로그램으로 설정할 수 있습니다. 이렇게 하려면 [다음 단계를 따르세요](./edge-default-browser.md).

## <a name="roadmap-and-feedback"></a>로드맵 및 피드백

Microsoft Edge의 PDF 읽기 프로그램 로드맵은 [여기](https://techcommunity.microsoft.com/t5/articles/roadmap-for-pdf-reader-in-microsoft-edge/m-p/1467667)에서 확인할 수 있습니다.

사용자가 중요하게 여기는 기능에 대한 피드백을 적극적으로 검토하고 있습니다. [Microsoft Edge 참가자](https://techcommunity.microsoft.com/t5/microsoft-edge-insider/ct-p/MicrosoftEdgeInsider) 포럼에서 피드백을 보내 주세요.

## <a name="see-also"></a>참고 항목

- [Microsoft Edge Enterprise 방문 페이지](https://aka.ms/EdgeEnterprise)
- [Microsoft 365 로드맵](https://www.microsoft.com/microsoft-365/roadmap)
- [비디오: Microsoft Edge 엔터프라이즈급 PDF 읽기 프로그램](microsoft-edge-video-pdf-reader.md)