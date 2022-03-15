---
title: IE(Internet Explorer) 모드에 대한 로컬 사이트 목록
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 03/01/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 로컬 사이트 목록을 사용하도록 설정하고 IE 모드에 쉽게 액세스하는 방법에 대해 자세히 알아보기
ms.openlocfilehash: 831e9f3eac53f53adce37381561c5297e16d5171
ms.sourcegitcommit: 556aca8dde42dd66364427f095e8e473b86651a0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2022
ms.locfileid: "12445692"
---
# <a name="configure-local-site-list-for-internet-explorer-ie-mode"></a>IE(Internet Explorer) 모드에 대한 로컬 사이트 목록 구성

>[!Note]
> Internet Explorer 11 데스크톱 응용 프로그램은 사용 중지되어 2022년 6월 15일에 지원이 중지됩니다(범위에 있는 항목의 목록은 Internet Explorer [11 데스크톱](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549) 앱 사용 중지 FAQ 참조). 현재 사용하는 동일한 IE11 앱과 사이트는 Internet Explorer 모드에서 Microsoft Edge로 열 수 있습니다. 자세한 내용은 2016년 12월 Internet Explorer [Windows 10 참조 Microsoft Edge](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/).

이 문서에서는 IE 모드(Internet Explorer 모드)에 쉽게 액세스할 수 있도록 구성하고 조직에서 로컬 사이트 목록을 사용할 수 있도록 하는 방법을 설명합니다.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 92 이상에 적용됩니다.

## <a name="prerequisites"></a>필수 구성 요소

1. Windows 업데이트

   - Windows 11
   - Windows 10 버전 1909 - [KB5003698](https://support.microsoft.com/topic/june-15-2021-kb5003698-os-build-18363-1645-preview-1ecf117e-1f89-40f9-a0a5-ed5766737620) 이상  

   - Windows 10 버전 2004; Windows 10 버전 20H2 및 Windows 10 버전 21H1 – [KB5003690](https://support.microsoft.com/topic/june-21-2021-kb5003690-os-builds-19041-1081-19042-1081-and-19043-1081-preview-11a7581f-2a01-47d5-ba12-431709ee2248) 이상

2. Microsoft Edge 버전 92(92.0.902.55 이상)

> [!IMPORTANT]
> 이 로컬 사이트 목록 기능은 현재 Windows Server 2016 지원되지 않습니다.

## <a name="overview"></a>개요

IE 모드는 Enterprise 사이트 목록 구성을 통해 지원됩니다. 사이트 목록에서 IE 모드를 사용하기 위해 사이트를 식별하고 구성하는 동안 사용자는 더 이상 독립 실행형 IE11 응용 프로그램으로 돌아가거나 기다릴 필요가 없습니다.

버전 Microsoft Edge 버전 92부터는 구성되지 않은 IE 모드 사이트에 대한 반복 ** 적인 액세스가 더 쉽습니다. 사용자는 IE 모드에서 사이트를 다시 로드할 수 있습니다. 조직의 사이트 목록이 업데이트되는 동안 이러한 사이트를 로컬 사이트 목록에 추가하여 30일 동안 자동으로 IE 모드로 렌더링할 수 있습니다. 환경에서 [IE11](/deployedge/edge-ie-disable-ie11) 을 사용하지 않도록 설정하면 사용자가 더 이상 조직의 사이트 목록에만 의존하지 않습니다.

조직의 그룹 정책을 통해 이 환경을 구성할 수 있습니다.

> [!NOTE]
> 구성*되지* 않은 사이트는 IE 모드가 필요하지만 IE 모드 사이트 목록에서 IE 모드로 열리도록 Enterprise 사이트입니다.

## <a name="enable-the-local-site-list-experience"></a>로컬 사이트 목록 환경 사용

로컬 사이트 목록 환경을 사용하도록 설정*하려면 사용자가 URL* 목록으로 이동하여 edge://settings/defaultBrowser 사이트가 다시 로드될 **** 수 있도록 허용을 Internet Explorer **수 있습니다**.

:::image type="content" source="media/Edge-hybrid-IE-mode/internet-explorer-compatibilitiy.png" alt-text="Internet Explorer 호환성":::

>[!Note]  
>
>1. *InternetExplorerIntegrationTestingAllowed* 정책을 통해 IE 모드 테스트를 사용하도록 설정한 경우 이 설정이 표시되지만 *InternetExplorerIntegrationReloadInIEModeAllowed* 정책을 명시적으로 사용하도록 설정하지 않으면 회색으로 표시됩니다.
>
>2. 사이트 **가** Internet Explorer 모드로 다시 로드될 수 있도록 허용이 **기본값**으로 설정되어 있는 경우 사용자가 기존 11개 사용법이 있는 경우 IE 모드에서 사이트를 Internet Explorer 수 있습니다.  

이 설정을 사용하도록 설정하면 사용자가 설정(타원 아이콘 ...)를 선택하여 IE 모드에서 사이트를 > 다시 로드할 **Internet Explorer 있습니다**. 또한 사용자가 탭을 **마우스 오른쪽** 단추로 클릭할 때 Internet Explorer 모드에서 다시 로드 탭을 선택하거나 링크를 마우스 오른쪽 단추 **** 로 클릭할 때 새 Internet Explorer 모드 탭에서 링크 열기를 선택할 수도 있습니다.

:::image type="content" source="media/Edge-hybrid-IE-mode/reload-in-internet-exploror-mode-screenshot.png" alt-text="Internet Explorer 모드로 다시 로드":::

**Internet Explorer 모드**로 다시 로드 아이콘을 도구 모음에 고정할 수 있습니다. 도구 모음 단추를 사용하면 사용자가 IE 모드를 쉽게 입력하고 종료할 수 있으며 해당 URL을 통해 관리할 *edge://settings/appearance* 있습니다.

:::image type="content" source="media/Edge-hybrid-IE-mode/reload-in-internet-exploror-mode-icon-screenshot.png" alt-text="Internet Explorer 모드 아이콘으로 다시 로드":::

>[!Note]
>사용자가 조직의 Enterprise 모드 사이트 목록에 있는 사이트에 있는 경우 다시 로드(또는 종료) Internet Explorer 옵션이 표시되지만 회색으로 표시됩니다.

옵션을 선택하면 사이트가 IE 모드로 다시 로드됩니다. IE 모드 표시기 아이콘은 주소 표시줄 왼쪽에 표시되어 있으며 플라이아웃에는 사용자가 다음에 다음에 Internet Explorer 모드로 페이지를 열기로 전환할 수 있는 옵션이 표시됩니다. 이렇게 하면 사용자가 로컬 사이트 목록에 있는 특정 페이지가 추가되고 다음 30일 동안 자동으로 IE 모드로 열립니다.

:::image type="content" source="media/Edge-hybrid-IE-mode/site-has-been-reloaded-in-ie-mode-screenshot.png" alt-text="이 페이지는 Internet Explorer 모드에서 열립니다.":::

사이트가 IE 모드로 다시 로드된 후 "페이지 내" 탐색은 IE 모드(예: 링크, 스크립트, 페이지의 양식 또는 다른 "페이지 내" 탐색에서 서버 쪽 리디렉션)로 유지됩니다.  

IE 모드에서는 사용자가 IE 모드임을 나타내는 배너가 표시될 수 있으며, IE 모드를 그대로 두고 IE 모드 아이콘을 도구 모음에 고정하는 옵션(아직 고정되지 않은 경우)을 볼 수 있습니다.

:::image type="content" source="media/Edge-hybrid-IE-mode/ie-mode-banner-screenshot.png" alt-text="IE 모드 배너":::

사용자는 배너의 나가기 단추, 고정된 IE 모드 아이콘 또는 설정 이상(타원 아이콘 **...)** > 종료 Internet Explorer 모드를 사용하여 IE 모드에서 종료할 수 있습니다. 그렇지 않으면 Microsoft Edge "페이지 내"가 아닌 탐색이 발생할 때(예: 주소 표시줄, 뒤로 단추 또는 즐겨찾기 링크 사용) IE 모드에서 자동으로 종료됩니다.

항목은 기본 기간인 30일 동안 로컬 사이트 목록에 남아 있습니다. 조직에 대한 레거시 사이트는 Enterprise 사이트 목록에서 구성하는 것이 좋습니다. 로컬 사이트 목록은 조직의 사이트 목록이 업데이트되는 동안 사용자가 중단되지 않고 워크플로를 계속할 수 있도록 합니다. 사용자가 사이트로 이동하는 31일차에는 사이트가 IE 모드에서 더 이상 로드되지 않습니다.를 설명하는 배너가 표시됩니다. 사용자가 선택한 경우 로컬 사이트 목록에 다시 추가할 수 있습니다.

:::image type="content" source="media/Edge-hybrid-IE-mode/page-will-no-longer-load-in-ie-mode-screenshot.png" alt-text="페이지가 IE 모드에서 더 이상 로드되지 않습니다.":::

## <a name="policies-to-configure-the-use-of-local-site-lists-for-ie-mode"></a>IE 모드에 대한 로컬 사이트 목록 사용을 구성하는 정책

2개의 그룹 정책을 통해 로컬 사이트 목록 환경을 구성할 수 Microsoft Edge. 이들 정책은 다음과 같습니다.

### <a name="policy-internetexplorerintegrationreloadiniemodeallowed"></a>정책: InternetExplorerIntegrationReloadInIEModeAllowed

이 정책은 "Microsoft Edge 모드로 사이트를 다시 로드할 수 있도록 허용" 설정에 Internet Explorer 해당합니다. *edge://settings/defaultbrowser* URL로 이동하여 이 설정에 액세스할 수 있습니다.

- 해당 정책을 사용하면 사용자가 IE 모드로 사이트를 다시 로드할 수 있습니다(설정 아이콘 ... > 모드로 다시 로드) Internet Explorer **있습니다**. 또한 사용자가 탭을 **마우스 오른쪽 단추로 클릭**할 때 Internet Explorer 모드에서 다시 로드 탭을 선택하거나, 링크를 마우스 오른쪽 **** 단추로 클릭할 때 새 Internet Explorer 모드 탭에서 링크 열기를 선택할 수도 있습니다.
사용자는 선택적으로 사이트 Microsoft Edge IE 모드를 사용하게 할 수 있습니다. 이 선택은 기본값인 30일 동안 기억되고 *InternetExplorerIntegrationLocalSiteListExpirationDays* 정책을 사용하여 관리할 수 있습니다.

- 해당 정책을 사용하지 않도록 설정하면 사용자가 IE 모드에서 구성되지 않은 사이트를 다시 로드할 수 없습니다.

- 해당 정책을 구성하지 않은 경우 최근 11개 사용법에 따라 구성되지 않은 사이트를 IE 모드로 다시 로드하는 Internet Explorer 표시됩니다.

이 정책은 [InternetExplorerIntegrationTestingAllowed](/deployedge/microsoft-edge-policies#internetexplorerintegrationtestingallowed) 정책을 구성한 방식보다 우선하며 해당 정책은 사용하지 않도록 설정됩니다.

### <a name="policy-internetexplorerintegrationlocalsitelistexpirationdays"></a>정책: InternetExplorerIntegrationLocalSiteListExpirationDays

이 정책을 사용하여 사이트가 사용자의 로컬 사이트 목록에 남아 있는 일 수를 조정할 수 있습니다.  

- 해당 정책을 사용하지 않도록 설정하거나 구성하지 않은 경우 기본값인 30일이 사용됩니다.

- 정책을 사용하도록 설정하는 경우 사이트를 사용자의 로컬 사이트 목록에 유지하려면 0~90일 사이의 값을 입력해야 합니다.

이 정책은 *InternetExplorerIntegrationReloadInIEModeAllowed* 정책을 사용하지 않도록 설정한 경우 효과가 없습니다.

> [!NOTE]
> 현재 로컬 사이트 목록이 장치 전체에서 동기화되지 않습니다. 이 개선된 기능은 현재 백로그에 있으며 사용할 수 있는 경우 이 기능을 업데이트할 것입니다.

## <a name="see-also"></a>참고 항목

- 11 Internet Explorer 사용 안 하게 - [Internet Explorer 11 사용 안](/deployedge/edge-ie-disable-ie11)
- IE 모드 정책 구성 - [IE 모드 정책 구성](/deployedge/edge-ie-mode-policies)
