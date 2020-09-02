---
title: Microsoft Edge의 PDF 읽기 프로그램
ms.author: adigan
author: dan-wesley
manager: balajek
ms.date: 08/05/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edg의 PDF 읽기 프로그램에 대해 자세히 알아봅니다.
ms.openlocfilehash: c189bc08d4af0c9d5c4d9c573e0b5b7ef32a7fb3
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980753"
---
# Microsoft Edge의 PDF 읽기 프로그램

PDF 파일은 일상 생활의 상당 부분을 구성합니다. 계약, 뉴스레터, 양식, 리서치 문서, 이력서 등의 형태로 제공됩니다. 이러한 파일은 엔터프라이즈에서 채택할 수 있는 신뢰성과 안전성을 갖춘 강력한 PDF 읽기 프로그램에 대한 필요성을 강조합니다.

Microsoft Edge에는 로컬 PDF 파일, 온라인 PDF 파일 또는 웹 페이지에 포함된 PDF 파일을 열 수 있는 기본 제공 PDF 읽기 프로그램이 함께 제공됩니다. 잉크와 강조 표시를 사용하여 이 파일에 주석을 달 수 있습니다. 해당 PDF 읽기 프로그램에서는 웹 페이지 및 PDF 문서 요구 사항을 충족하는 단일 응용 프로그램을 제공합니다. Microsoft Edge PDF 읽기 프로그램은 Windows 및 macOS 데스크톱 플랫폼에서 작동하는 안전하고 신뢰할 수 있는 응용 프로그램입니다.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.

## 필수 구성 요소, 지원 및 제약 조건

다음 표에서는 각 PDF 읽기 프로그램 기능을 지원하는 Microsoft Edge의 채널과 버전을 보여 줍니다.

| 기능 | 안정적인 채널 버전 |
|---------|------------------------|
| 로컬, 온라인 및 포함된 PDF 파일 보기 및 인쇄 | 79.0.309.71                |
| 기본 양식 채우기<br>(JavaScript 폼이 지원되지 않음) | 79.0.309.71           |
| 수동 입력  | 80.0.361.48            |
| 잉크 사용자 지정 | 83.0.478.54  |
| Highlight  | 81.0.416.53         |
| 소리내어 읽기 | [Microsoft Edge 참가자](https://www.microsoftedgeinsider.com/) 채널에서 현재 승격 중 |
| MIP으로 보호된 파일 보기 | 80.0.361.48의 Windows 지원<br>81.0.416.53의 Mac 지원 |
|  IRM으로 보호된 파일 보기  | 83.0.478.37            |

### 제약 조건

현재 PDF 읽기 프로그램에 대해 다음 제한 사항을 확인합니다.

-  XFA(XML Forms Architecture)는 Microsoft Edge에서 지원되지 않는 레거시 형태의 양식입니다.
-  현재 지원되지 않는 접근성 시나리오와 관련된 문서는 [Microsoft 접근성 규칙 보고서](https://cloudblogs.microsoft.com/industry-blog/government/2018/09/11/accessibility-conformance-reports/) 블로그를 참조하세요.

## 기능

### 수동 입력

PDF 파일에서 수동 입력 기능을 사용하여 간편하게 기록하여 손쉽게 참조하거나, 서명하거나, PDF 양식을 작성할 수 있습니다. 이제 Microsoft Edge에서 이 기능을 사용할 수 있습니다. 필요한 경우 PDF 파일의 수동 입력 외에, 색상 및 스트로크 너비를 사용하여 PDF 파일의 여러 부분을 돋보이게 표시할 수 있습니다. 다음 스크린샷은 PDF 페이지에 수동 입력을 추가하는 방법을 보여 줍니다.

<!-- SCREENSHOT -->
![PDF 페이지에 수동 입력 추가](media/microsoft-edge-pdf/pdf-reader-inking.png)

### Highlight

Microsoft Edge의 PDF 읽기 프로그램에서 하이라이트를 추가하고 편집하는 기능을 제공합니다. 강조 표시를 만들려면 텍스트를 선택하여 텍스트를 마우스 오른쪽 단추로 클릭한 다음, 메뉴에서 하이라이트를 선택하고 원하는 색을 선택하면 됩니다. 다음 스크린샷은 사용 가능한 강조 표시 옵션을 보여 줍니다.

![PDF 읽기 프로그램의 강조 표시 옵션 사용](media/microsoft-edge-pdf/pdf-reader-highlight.png)

### 소리내어 읽기

PDF용 소리내어 읽기를 사용하면 사용자에게 중요한 다른 작업을 수행하면서 PDF 콘텐츠를 들을 수 있습니다. 또한 청각 학습자가 콘텐츠에 집중하는 데 도움을 주므로 훨씬 쉽게 배울 수 있습니다. 다음 스크린샷은 소리내어 읽기 예를 보여 줍니다. 강조 표시된 부분은 현재 읽고 있는 텍스트를 보여 줍니다.

![PDF 읽기 프로그램의 강조 표시 옵션 사용](media/microsoft-edge-pdf/pdf-reader-read-aloud-example.png)

### 보호된 PDF

[MIP(Microsoft Information Protection)](https://docs.microsoft.com/microsoft-365/compliance/protect-information?view=o365-worldwide)을 사용하면 조직의 규정 준수 정책을 지키면서 다른 사용자와 안전하게 공동 작업을 할 수 있습니다. 파일이 보호된 경우, 사용자가 해당 파일을 사용할 수 있는 작업은 해당 사용자에게 할당된 사용 권한에 따라 결정됩니다.

이러한 파일은 다른 소프트웨어를 다운로드하거나 추가 기능을 설치할 필요 없이 브라우저에서 바로 열 수 있습니다. 이렇게 하면 MIP에서 제공하는 보안이 브라우저에 바로 통합되어 원활한 워크플로를 제공합니다.

<!-- SCREENSHOT -->
![보호된 PDF 문서.](media/microsoft-edge-pdf/pdf-reader-protected-pdf2.png)

MIP으로 보호된 파일 외에도, [IRM(Information Rights Management)](https://docs.microsoft.com/microsoft-365/compliance/set-up-irm-in-sp-admin-center?view=o365-worldwide)으로 보호된 SharePoint 라이브러리의 PDF 파일을 브라우저에서 열 수 있습니다.

Microsoft Edge를 사용하여, 로컬이나 클라우드에 저장된 MIP으로 보호된 파일을 볼 수 있습니다. 로컬에 저장된 경우 브라우저에서 직접 파일을 열 수 있습니다. 클라우드 서비스에서 SharePoint로 파일을 연 경우에는 "브라우저에서 열기" 옵션을 사용해야 합니다.

Microsoft Edge에 로그인하는 데 사용된 프로필에 적어도 해당 파일에 대한 보기 권한이 있는 경우, 파일이 Microsoft Edge에서 열립니다.

<!-- SCREENSHOT -->
![MIP으로 보호되는 SharePoint PDF 페이지를 저장하라는 메시지가 표시됨](media/microsoft-edge-pdf/pdf-reader-sharepoint-irm.png)

## 접근성

PDF 읽기 프로그램은 Windows 및 macOS 장치에서 키보드 접근성, 고대비 모드 및 화면 읽기 프로그램 지원을 제공합니다.

### 키보드 접근성

사용자가 키보드를 사용하여 양식 필드 및 하이라이트와 같이, 사용자가 상호 작용할 수 있는 문서의 여러 부분을 탐색할 수 있습니다.

<!-- SCREENSHOT -->

### 고대비 모드

PDF 읽기 프로그램은 운영 체제 수준에서 정의된 설정을 사용하여 PDF 콘텐츠를 고대비 모드로 렌더링합니다.

<!-- SCREENSHOT -->
<!--![High contrast mode for pdf file](media/microsoft-edge-pdf/pdf-reader-high-contrast.png)-->

### 화면 읽기 프로그램 지원

Windows 및 Mac 컴퓨터에서 화면 읽기 프로그램을 사용하여 PDF 파일을 탐색하고 읽을 수 있습니다. <!--The next screenshot shows the toolbar that users can use for audio settings when they're using the Read Aloud option in PDF reader. -->

<!-- SCREENSHOT -->
<!--
![Screen reader toolbar](media/microsoft-edge-pdf/pdf-reader-read-aloud.png) -->

## 보안 및 안정성

보안은 모든 조직에서 가장 중요한 개념에 속합니다. PDF 읽기 프로그램 보안은 Microsoft Edge 보안 설계의 필수 요소입니다. PDF 읽기 프로그램에서 가장 중요한 보안 기능 두 가지는 프로세스 격리 및 Application Guard(Microsoft Defender Application Guard)입니다.

- 프로세스 격리. 여러 웹 사이트에서 열린 PDF는 완전히 격리된 프로세스입니다. 브라우저는 다른 원본에서 열린 PDF 파일이나 웹 사이트와 통신할 필요가 없습니다. PDF 검색 기능은 손상된 PDF를 공격 표면으로 사용하려고 계획하는 공격으로부터 안전합니다.

- Application Guard Application Guard를 통해 관리자는 조직에서 신뢰하는 사이트 목록을 설정할 수 있습니다. 사용자가 다른 사이트를 여는 경우, 자체 컨테이너에서 실행되는 별도의 Application Guard 보호 창에서 열립니다. 컨테이너는 회사 네트워크와 사용자 컴퓨터에 있는 모든 데이터가 손상되지 않도록 보호하는 데 도움이 됩니다.<br><br>
이 보호 기능은 보고 있는 모든 온라인 PDF 파일에도 적용됩니다. 또한 Application Guard 창에서 다운로드한 모든 PDF 파일이 저장되고, 필요한 경우 컨테이너에서 다시 열립니다. 이렇게 하면 파일이 다운로드될 때뿐만 아니라, 전체 수명 주기 동안 환경을 안전하게 유지할 수 있습니다. 자세한 내용은 [Application Guard](https://docs.microsoft.com/DeployEdge/microsoft-edge-security-windows-defender-application-guard)를 참조하세요.

### 안정성

Microsoft Edge는 Chromium 기반이므로 Google Chrome에서 볼 때와 동일한 수준의 안정성을 기대할 수 있습니다.

## PDF 읽기 프로그램 배포 및 업데이트

PDF 읽기 프로그램이 배포되고 Microsoft Edge 브라우저의 나머지 부분으로 업데이트됩니다. Microsoft Edge를 배포하는 방법에 대한 자세한 내용은 [수천 대의 장치에 Microsoft Edge 배포](microsoft-edge-video-deploy.md)를 참조하세요. [Microsoft Edge 설명서](https://docs.microsoft.com/DeployEdge/) 랜딩 페이지에서도 더 많은 배포 정보를 확인할 수 있습니다.

> [!TIP]
> Microsoft Edge를 조직의 기본 PDF 읽기 프로그램으로 설정할 수 있습니다. 이렇게 하려면 [다음 단계를 따르세요](https://docs.microsoft.com/deployedge/edge-default-browser).

## 로드맵 및 피드백

Microsoft Edge의 PDF 읽기 프로그램에 대한 로드맵은 [여기](https://techcommunity.microsoft.com/t5/articles/roadmap-for-pdf-reader-in-microsoft-edge/m-p/1467667)에서 사용할 수 있습니다.

사용자가 중요하게 여기는 기능에 대한 피드백을 적극적으로 보고 있습니다. [Microsoft Edge UserVoice](https://microsoftedge.uservoice.com/)를 사용하거나 [Microsoft Edge 참가자](https://techcommunity.microsoft.com/t5/microsoft-edge-insider/ct-p/MicrosoftEdgeInsider) 포럼에서 피드백을 보내 주세요.

## 참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)