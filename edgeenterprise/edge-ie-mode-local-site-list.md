---
title: IE(Internet Explorer) 모드에 대한 로컬 사이트 목록
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 03/24/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 로컬 사이트 목록을 사용하도록 설정하고 IE 모드에 쉽게 액세스하는 방법을 알아봅니다.
ms.openlocfilehash: 85aa6baa1abaa1a59f4e9cf9f2414f54ccf70cbb
ms.sourcegitcommit: dd8cdbd35726c795ddce917e549ddf17ee7f5290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/11/2022
ms.locfileid: "12473630"
---
# <a name="configure-local-site-list-for-internet-explorer-ie-mode"></a>IE(Internet Explorer) 모드에 대한 로컬 사이트 목록 구성

>[!Note]
> Internet Explorer 11 데스크톱 애플리케이션은 사용 중지되고 2022년 6월 15일에 지원되지 않습니다(범위에 있는 항목 목록은 [Internet Explorer 11 데스크톱 앱 사용 중지 FAQ](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549) 참조). 현재 사용하는 동일한 IE11 앱과 사이트는 Internet Explorer 모드에서 Microsoft Edge로 열 수 있습니다. 자세한 내용은 [Windows 10 Internet Explorer의 미래가 Microsoft Edge](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/) 참조하세요.

이 문서에서는 IE 모드(Internet Explorer 모드)에 쉽게 액세스하도록 구성하고 조직에서 로컬 사이트 목록을 사용하도록 허용하는 방법을 설명합니다.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 92 이상에 적용됩니다.

## <a name="prerequisites"></a>필수 구성 요소

1. Windows 업데이트

   - Windows 11

   - Windows 10 버전 1909 - [KB5003974](https://support.microsoft.com/topic/kb5003974-servicing-stack-update-for-windows-10-version-1909-june-15-2021-0e65680e-2d21-4a31-b97a-e24c022aeccf) 및 [KB5003698](https://support.microsoft.com/topic/june-15-2021-kb5003698-os-build-18363-1645-preview-1ecf117e-1f89-40f9-a0a5-ed5766737620) 이상

   - Windows 10, 버전 2004; Windows 10 버전 20H2 및 Windows 10 버전 21H - [KB5005260](https://support.microsoft.com/topic/kb5005260-servicing-stack-update-for-windows-10-version-2004-20h2-and-21h1-august-10-2021-ec4c5daa-2cec-4b06-be93-037f150fe3ba) 및 [KB5005101](https://support.microsoft.com/topic/september-1-2021-kb5005101-os-builds-19041-1202-19042-1202-and-19043-1202-preview-82a50f27-a56f-4212-96ce-1554e8058dc1) 이상

2. Microsoft Edge 버전 92(92.0.902.55 이상)

> [!IMPORTANT]
> 이 로컬 사이트 목록 기능은 현재 Windows Server 2016 지원되지 않습니다.

## <a name="overview"></a>개요

IE 모드는 Enterprise 모드 사이트 목록의 구성에 의해 구동됩니다. IE 모드를 사용하도록 사이트 목록에서 사이트를 식별하고 구성하는 동안 사용자는 더 이상 독립 실행형 IE11 애플리케이션을 기다리거나 되돌릴 필요가 없습니다.

Microsoft Edge 버전 92부터 *구성되지 않은* IE 모드 사이트에 반복적으로 액세스하는 것이 더 쉽습니다. 사용자는 IE 모드에서 사이트를 다시 로드할 수 있습니다. 조직의 사이트 목록이 업데이트되는 동안 이러한 사이트를 로컬 사이트 목록에 추가하여 30일 동안 IE 모드로 자동으로 렌더링할 수 있습니다. 사용자 환경에서 [IE11을 사용하지 않도록 설정](/deployedge/edge-ie-disable-ie11) 하면 사용자는 더 이상 조직의 사이트 목록에만 의존하지 않습니다.

조직의 그룹 정책을 통해 이 환경을 구성할 수 있습니다.

> [!NOTE]
> *구성되지 않은* 사이트는 IE 모드가 필요하지만 Enterprise 모드 사이트 목록에서 IE 모드로 열리도록 구성되지 않은 사이트입니다.

## <a name="enable-the-local-site-list-experience"></a>로컬 사이트 목록 환경 사용

로컬 사이트 목록 환경을 사용하도록 설정하려면 사용자가 URL *edge://settings/defaultBrowser* 이동하여 **Internet Explorer 모드에서 사이트를 다시 로드하도록 허용 모드** 로 설정할 **수 있습니다**.

:::image type="content" source="media/Edge-hybrid-IE-mode/internet-explorer-compatibilitiy.png" alt-text="Internet Explorer 호환성":::

>[!Note]  
>
>1. *InternetExplorerIntegrationTestingAllowed* 정책을 통해 IE 모드 테스트를 사용하도록 설정한 경우 이 설정이 표시되지만 *InternetExplorerIntegrationReloadInIEModeAllowed* 정책을 명시적으로 사용하도록 설정하지 않으면 회색으로 표시됩니다.
>
>2. **Internet Explorer 모드에서 사이트를 다시 로드할 수 있도록 허용**이 **기본값**으로 설정된 경우 사용자는 기존 Internet Explorer 11 사용량이 있는 경우 IE 모드로 사이트를 다시 로드할 수 있습니다.  

이 설정을 사용하도록 설정하면 사용자는 **Internet Explorer 모드에서 설정(줄임표 아이콘 ...) > 다시 로드하여 사이트를 IE 모드로 다시 로드**할 수 있습니다. 사용자는 탭을 마우스 오른쪽 단추로 클릭할 때 **Internet Explorer 모드에서 다시 로드 탭** 을 선택하거나 링크를 마우스 오른쪽 단추로 클릭할 때 **새 Internet Explorer 모드 탭에서 링크 열기** 를 선택할 수도 있습니다.

:::image type="content" source="media/Edge-hybrid-IE-mode/reload-in-internet-exploror-mode-screenshot.png" alt-text="Internet Explorer 모드에서 다시 로드":::

**Internet Explorer 모드에서 다시 로드** 아이콘을 도구 모음에 고정할 수 있습니다. 도구 모음 단추를 사용하면 사용자가 IE 모드를 쉽게 입력하고 종료할 수 있으며 *edge://settings/appearance* URL을 통해 관리할 수 있습니다.

:::image type="content" source="media/Edge-hybrid-IE-mode/reload-in-internet-exploror-mode-icon-screenshot.png" alt-text="Internet Explorer 모드에서 다시 로드 아이콘":::

>[!Note]
>사용자가 조직의 Enterprise 모드 사이트 목록에 이미 있는 사이트에 있는 경우 Internet Explorer 모드를 다시 로드(또는 종료)하는 옵션이 표시되지만 회색으로 표시됩니다.

옵션을 선택하면 사이트가 IE 모드로 다시 로드됩니다. IE 모드 표시기 아이콘은 주소 표시줄의 왼쪽에 표시되며 플라이아웃은 사용자가 다음에 Internet Explorer 모드에서 페이지를 열기로 전환할 수 있는 옵션을 표시합니다. 이렇게 하면 사용자가 로컬 사이트 목록에 있는 특정 페이지가 추가되고 다음 30일 동안 IE 모드에서 자동으로 열립니다.

:::image type="content" source="media/Edge-hybrid-IE-mode/site-has-been-reloaded-in-ie-mode-screenshot.png" alt-text="이 페이지는 Internet Explorer 모드에서 열립니다.":::

사이트가 IE 모드로 다시 로드되면 "페이지 내" 탐색은 IE 모드(예: 링크, 스크립트, 페이지의 양식 또는 다른 "페이지 내" 탐색에서 서버 쪽 리디렉션)로 유지됩니다.  

IE 모드에서는 사용자가 IE 모드에 있음을 나타내는 배너가 표시되고, IE 모드를 벗어나 도구 모음에 IE 모드 아이콘을 고정하는 옵션이 표시됩니다(아직 고정되지 않은 경우).

:::image type="content" source="media/Edge-hybrid-IE-mode/ie-mode-banner-screenshot.png" alt-text="IE 모드 배너":::

사용자는 배너의 나가기 단추, 고정된 IE 모드 아이콘 또는 **설정 이상(타원 아이콘 ...) > Internet Explorer 모드를 종료**하도록 선택할 수 있습니다. 그렇지 않으면 "페이지 내"가 아닌 탐색이 발생할 때(예: 주소 표시줄, 뒤로 단추 또는 즐겨찾기 링크 사용) Microsoft Edge 자동으로 IE 모드에서 종료됩니다.

항목은 30일의 기본 기간 동안 로컬 사이트 목록에 남아 있습니다. Enterprise 모드 사이트 목록에서 조직의 레거시 사이트를 구성하는 것이 좋습니다. 로컬 사이트 목록은 조직의 사이트 목록이 업데이트되는 동안 사용자가 중단 없이 워크플로를 계속할 수 있도록 합니다. 31일째에 사용자가 사이트로 이동하면 사이트가 더 이상 IE 모드로 로드되지 않음을 설명하는 배너가 표시됩니다. 사용자가 선택한 경우 로컬 사이트 목록에 다시 추가할 수 있습니다.

:::image type="content" source="media/Edge-hybrid-IE-mode/page-will-no-longer-load-in-ie-mode-screenshot.png" alt-text="IE 모드에서 페이지가 더 이상 로드되지 않습니다.":::

## <a name="policies-to-configure-the-use-of-local-site-lists-for-ie-mode"></a>IE 모드에 로컬 사이트 목록 사용을 구성하는 정책

Microsoft Edge 로컬 사이트 목록 환경을 구성하는 데 두 개의 그룹 정책을 사용할 수 있습니다. 이들 정책은 다음과 같습니다.

### <a name="policy-internetexplorerintegrationreloadiniemodeallowed"></a>정책: InternetExplorerIntegrationReloadInIEModeAllowed

이 정책은 "Internet Explorer 모드에서 사이트를 다시 로드할 수 있도록 허용" Microsoft Edge 설정에 해당합니다. *edge://settings/defaultbrowser* URL로 이동하여 이 설정에 액세스할 수 있습니다.

- 이 정책을 사용하도록 설정하면 사용자는 **설정 이상(줄임표 아이콘 ... > Internet Explorer 모드에서 다시 로드**)을 선택하여 IE 모드에서 사이트를 다시 로드할 수 있습니다. 사용자는 탭을 마우스 오른쪽 단추로 클릭할 때 **Internet Explorer 모드에서 다시 로드** 탭을 선택하거나 링크를 마우스 오른쪽 단추로 클릭할 때 **새 Internet Explorer 모드 탭에서 링크 열기** 를 선택할 수도 있습니다.
사용자는 필요에 따라 Microsoft Edge 나중에 사이트에 IE 모드를 사용하도록 지시할 수 있습니다. 이 선택은 기본값인 30일 동안 기억되며 *InternetExplorerIntegrationLocalSiteListExpirationDays* 정책을 사용하여 관리할 수 있습니다.

- 이 정책을 사용하지 않도록 설정하면 사용자는 IE 모드에서 구성되지 않은 사이트를 다시 로드할 수 없습니다.

- 이 정책을 구성하지 않으면 최근 Internet Explorer 11 사용량에 따라 구성된 사이트를 IE 모드로 다시 로드하는 옵션이 사용자에게 표시됩니다.

이 정책은 [InternetExplorerIntegrationTestingAllowed](/deployedge/microsoft-edge-policies#internetexplorerintegrationtestingallowed) 정책을 구성한 방법보다 우선하며 해당 정책은 사용하지 않도록 설정됩니다.

### <a name="policy-internetexplorerintegrationlocalsitelistexpirationdays"></a>정책: InternetExplorerIntegrationLocalSiteListExpirationDays

이 정책을 사용하여 사용자의 로컬 사이트 목록에 사이트가 남아 있는 일 수를 조정할 수 있습니다.  

- 이 정책을 사용하지 않거나 구성하지 않으면 기본값인 30일이 사용됩니다.

- 정책을 사용하도록 설정하는 경우 사용자의 로컬 사이트 목록에 사이트를 유지하려면 0-90일 사이의 값을 입력해야 합니다.

*InternetExplorerIntegrationReloadInIEModeAllowed* 정책을 사용하지 않도록 설정한 경우에는 이 정책이 적용되지 않습니다.

> [!NOTE]
> 로컬 사이트 목록은 현재 디바이스 간에 동기화되지 않습니다. 이러한 개선 사항은 현재 백로그에 있으며 이 기능을 사용할 수 있게 되면 업데이트할 예정입니다.

## <a name="see-also"></a>참고 항목

- Internet Explorer 11 사용 [안 함 - Internet Explorer 11 사용 안 함](/deployedge/edge-ie-disable-ie11)
- IE 모드 정책 구성 - [IE 모드 정책 구성](/deployedge/edge-ie-mode-policies)
