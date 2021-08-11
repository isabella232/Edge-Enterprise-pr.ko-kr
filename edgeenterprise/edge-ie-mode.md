---
title: Internet Explorer 모드란 무엇인가요?
ms.author: kvice
author: dan-wesley
manager: laurawi
ms.date: 08/05/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge의 Internet Explorer 모드를 통해 Internet Explorer 11이 필요한 사이트에 대한 액세스와 최신 사이트에 대한 액세스를 제공하는 방법에 대해 알아보세요.
ms.openlocfilehash: cc88c6745d40bfd33a345d76e2b2090f0f33243271350e4449d698d4a0fab71e
ms.sourcegitcommit: 6e9ce486955bd90db09744307b72245dd4890d01
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2021
ms.locfileid: "11810198"
---
# <a name="what-is-internet-explorer-ie-mode"></a>Internet Explorer(IE) 모드란 무엇인가요?

>[!Note]
> Internet Explorer 11 데스크톱 응용 프로그램은 2022년 6월 15일 사용 및 지원이 중단됩니다(범위 내 항목 목록은 [FAQ 참고](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)). 현재 사용하는 동일한 IE11 앱과 사이트는 Internet Explorer 모드에서 Microsoft Edge로 열 수 있습니다. [여기서 자세한 내용을 알아보세요](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/).

Microsoft Edge에서 기존 웹 사이트와의 이전 버전과의 호환성을 위해 Internet Explorer 11이 여전히 필요하지만 최신 브라우저가 필요한 조직을 위해 IE(Internet Explorer) 모드를 만들었습니다. 이 기능을 사용하면 조직에서 하나의 브라우저를 사용하여 레거시 웹/앱 또는 최신 웹/앱을 이용할 수 있습니다. 이 문서에서는 IE 모드에서 Microsoft Edge를 사용에 대해 소개합니다.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.

## <a name="what-is-ie-mode"></a>IE 모드란 무엇인가요?

Microsoft Edge의 IE 모드를 사용하면 조직에 필요한 모든 사이트를 단일 브라우저에서 쉽게 사용할 수 있습니다. 최신 사이트에는 통합 Chromium 엔진을 사용하고 레거시 사이트에는 IE11 (Internet Explorer 11)의 Trident MSHTML 엔진을 사용합니다.

사이트가 IE 모드로 로드되면 탐색 모음 왼쪽에 IE 로고 표시기가 표시됩니다. 다음과 같이 IE 로고 표시기를 클릭하여 추가 정보를 표시할 수 있습니다.

  ![IE 로고 표시기](./media/ie-mode/ie-logo-indicator1.png)

정책을 통해 특별히 구성한 사이트만 IE 모드를 사용하고 다른 모든 사이트는 최신 웹 사이트로 렌더링됩니다. 사이트가 IE 모드를 사용하려면 다음을 수행해야 합니다.

- 다음 정책 중 하나에 정의된 엔터프라이즈 모드 사이트 목록 XML에 사이트를 나열하세요.
  - Microsoft Edge 78 이상, "엔터프라이즈 모드 사이트 목록 구성"
  - Internet Explorer, "엔터프라이즈 모드 IE 웹 사이트 목록 사용"
  > [!NOTE]
  > 하나의 엔터프라이즈 모드 사이트 목록만 처리합니다. Microsoft Edge 사이트 목록 정책은 Internet Explorer 사이트 목록 정책보다 우선합니다.
- **Internet Explorer에 모든 인트라넷 사이트 보내기** 그룹 정책을 사용하도록 설정된 경우 모든 인트라넷 사이트(Microsoft Edge 77 이상)

### <a name="ie-mode-supports-the-following-internet-explorer-functionality"></a>IE 모드는 다음 Internet Explorer 기능을 지원합니다.

- 모든 문서 모드 및 엔터프라이즈 모드
- ActiveX 컨트롤(예 : Java 또는 Silverlight). **참고:** Silverlight는 2021년 10월 12일에 [지원이 종료](https://support.microsoft.com/windows/silverlight-end-of-support-0a3be3c7-bead-e203-2dfd-74f0a64f1788)됩니다. 
- 브라우저 도우미 개체 
- 보안 영역 설정 및 보호 모드에 영향을 주는 Internet Explorer 설정 및 그룹 정책
- [IEChooser](/deployedge/edge-ie-mode-faq#how-can-i-debug-my-legacy-application-while-using-ie-mode-on-microsoft-edge-)를 사용하여 시작하는 경우 IE용 F12 개발자 도구
- Microsoft Edge 확장 프로그램(IE 페이지 콘텐츠와 직접 상호 작용하는 확장 프로그램이 지원되지 않음)

### <a name="ie-mode-doesnt-support-the-following-internet-explorer-functionality"></a>IE 모드는 다음 Internet Explorer 기능을 지원하지 않습니다.

- Internet Explorer 도구 모음
- Internet Explorer 메뉴를 제어하는 설정 및 그룹 정책을 선택합니다.
- IE11 또는 Microsoft Edge F12 개발자 도구

## <a name="prerequisites"></a>필수 구성 요소

다음 필수 구성 요소는 Microsoft Edge를 IE 모드에서 사용하는 경우에 적용됩니다.

> [!IMPORTANT]
> 성공적인 작업의 수행을 보장하기 위해 Windows 및 Microsoft Edge에 대한 최신 업데이트를 설치합니다. 그렇지 않으면 IE 모드에서 오류가 발생하기 쉽습니다.

1. 다음의 표는 운영 체제에 대한 최소 시스템 업데이트를 열거합니다.

 | 운영 체제 | 버전       | 업데이트 |
 |------------------|---------------|---------|
 | Windows 10       | 1909 이상 |         |
 | Windows 10       | 1903          | [KB4501375](https://support.microsoft.com/help/4501375/windows-10-update-kb4501375) 이상 |
 | Windows Server   | 1903          | [KB4501375](https://support.microsoft.com/help/4501375/windows-10-update-kb4501375) 이상 |
 | Windows 10       | 1809          | [KB4501371](https://support.microsoft.com/help/4501371/windows-10-update-kb4501371) 이상 |
 | Windows Server   | 1809          | [KB4501371](https://support.microsoft.com/help/4501371/windows-10-update-kb4501371) 이상 |
 | Windows Server   | 2019          | [KB4501371](https://support.microsoft.com/help/4501371/windows-10-update-kb4501371) 이상 |
 | Windows 10       | 1803          | [KB4512509](https://support.microsoft.com/help/4512509/windows-10-update-kb4512509) 이상 |
 | Windows 10       | 1709          | [KB4512494](https://support.microsoft.com/help/4512494/windows-10-update-kb4512494) 이상 |
 | Windows 10       | 1607          | [KB4516061](https://support.microsoft.com/help/4516061/windows-10-update-kb4516061) 이상 |
 | Windows Server   | 2016          | [KB4516061](https://support.microsoft.com/help/4516061/windows-10-update-kb4516061) 이상 |
 | Windows 10       | 최초 버전, 2015년 7월 | [KB4520011](https://support.microsoft.com/help/4520011/windows-10-update-kb4520011) 이상 |
 | Windows 8       | 8.1              | [KB4507463](https://support.microsoft.com/help/4507463/july-16-2019-kb4507463-os-build-preview-of-monthly-rollup) 이상 또는 [KB4511872](https://support.microsoft.com/help/4511872/cumulative-security-update-for-internet-explorer) 이상 |
 | Windows Server   | 2012 R2       | [KB4507463](https://support.microsoft.com/help/4507463/july-16-2019-kb4507463-os-build-preview-of-monthly-rollup) 이상 또는 [KB4511872](https://support.microsoft.com/help/4511872/cumulative-security-update-for-internet-explorer) 이상 |
 | Windows 8  | 포함됨            | [KB4492872](https://support.microsoft.com/help/4492872/update-for-internet-explorer-april-16-2019)를 설치하여 Internet Explorer 11로 업그레이드한 후 [KB4507447](https://support.microsoft.com/help/4507447/windows-server-2012-update-kb4507447) 이상 혹은 [KB4511872](https://support.microsoft.com/help/4511872/cumulative-security-update-for-internet-explorer) 이상을 설치 |
 | Windows Server   | 2012           | [KB4492872](https://support.microsoft.com/help/4492872/update-for-internet-explorer-april-16-2019)를 설치하여 Internet Explorer 11로 업그레이드한 후 [KB4507447](https://support.microsoft.com/help/4507447/windows-server-2012-update-kb4507447) 이상 혹은 [KB4511872](https://support.microsoft.com/help/4511872/cumulative-security-update-for-internet-explorer) 이상을 설치 |
 | Windows 7        |  SP1**        | [KB4507437](https://support.microsoft.com/help/4507437/windows-7-update-kb4507437) 이상. 또는 [KB4511872](https://support.microsoft.com/help/4511872/cumulative-security-update-for-internet-explorer) 이상 |
 | Windows Server   |  2008 R2**    | [KB4507437](https://support.microsoft.com/help/4507437/windows-7-update-kb4507437) 이상. 또는 [KB4511872](https://support.microsoft.com/help/4511872/cumulative-security-update-for-internet-explorer) 이상 |
  > [!IMPORTANT]
  > ** Windows 7 및 Windows Server 2008 R2는 해당 운영 체제가 지원되지 않는 경우에도 Microsoft Edge에서 지원됩니다. 이러한 운영 체제에서 IE 모드가 지원되려면 디바이스에 [Windows 7에 대해 연장된 보안 업데이트](https://support.microsoft.com/help/4527878/faq-about-extended-security-updates-for-windows-7)가 있어야 합니다. 보안을 유지하기 위해 가능한 한 빨리 지원되는 운영 체제로 업그레이드할 것을 권장합니다. 확장 보안 업데이트가 포함된 Microsoft Edge에 대한 지원은 지원되는 OS 상태로의 임시 연결 다리로 간주되어야 합니다.

2. Microsoft Edge 관리 템플릿. 자세한 내용은 [Microsoft Edge 구성](./configure-microsoft-edge.md)을 참조하세요.
3. Windows 기능에서 활성화된 Internet Explorer 11.

## <a name="see-also"></a>참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [추가 엔터프라이즈 모드 정보](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
