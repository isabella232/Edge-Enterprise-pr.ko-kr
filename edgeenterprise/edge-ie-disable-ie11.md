---
title: Internet Explorer 11 사용하지 않는 경우
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 04/08/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Internet Explorer 11을 사용하지 않도록 설정하고 Microsoft Edge에서 Internet Explorer 모드를 사용하는 방법을 알아봅니다.
ms.openlocfilehash: 3ddb012b48b0b9d8448cdee910ed28db85a0e044
ms.sourcegitcommit: dd8cdbd35726c795ddce917e549ddf17ee7f5290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/11/2022
ms.locfileid: "12473612"
---
# <a name="disable-internet-explorer-11"></a>Internet Explorer 11 사용하지 않는 경우

>[!Note]
> Internet Explorer 11 데스크톱 응용 프로그램은 2022년 6월 15일 사용 및 지원이 중단됩니다(범위 내 항목 목록은 [FAQ 참고](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)). 현재 사용하는 동일한 IE11 앱과 사이트는 Internet Explorer 모드에서 Microsoft Edge로 열 수 있습니다. [여기서 자세한 내용을 알아보세요](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/).

이 문서에서는 사용자 환경에서 Internet Explorer 11을 독립 실행형 브라우저로 사용하지 않도록 설정하는 방법에 대해 설명합니다.

## <a name="prerequisites"></a>필수 구성 요소

다음 Windows 업데이트와 Microsoft Edge 소프트웨어가 필요합니다.

- Windows 업데이트

  - Windows 10 버전 21H1 이상
  - Windows 10, 버전 2004; Windows Server 버전 2004; Windows 10, 버전 20H2; Windows Server 버전 20H2: [KB4598291](https://support.microsoft.com/topic/february-2-2021-kb4598291-os-builds-19041-789-and-19042-789-preview-6a766199-a4f1-616e-1f5c-58bdc3ca5e3b) 이상
  - Windows 10 버전 1909: [KB4598298](https://support.microsoft.com/topic/january-21-2021-kb4598298-os-build-18363-1350-preview-02dfd9ba-91a2-1b82-dede-42f288c02511) 이상
  - Windows Server 2019; Windows 10 Enterprise 2019 LTSC: [KB4598296](https://support.microsoft.com/topic/january-21-2021-kb4598296-os-build-17763-1728-preview-4c0931ff-45b7-ff59-5e00-c03b5afb363d) 이상
  - Windows Server 2016; Windows 10 Enterprise 2016 LTSB: [KB4601318](https://support.microsoft.com/topic/february-9-2021-kb4601318-os-build-14393-4225-c5e3de6c-e3e6-ffb5-6197-48b9ce16446e) 이상
  - Windows 10 Enterprise 2015 LTSB: [KB4601331](https://support.microsoft.com/office/february-9-2021%e2%80%94kb4601331-os-build-10240-18842-6227d078-fef3-8d67-27e0-1882e6cb79ff?ui=en-US&rs=en-US&ad=US) 이상
  - Windows 8.1; Windows Server 2012 R2: [KB4601384](https://support.microsoft.com/topic/february-9-2021-kb4601384-monthly-rollup-16bdbb75-dd4b-2910-abc5-7891c9756b96) 이상
  - Windows Server 2012: [KB4601348](https://support.microsoft.com/topic/february-9-2021-kb4601348-monthly-rollup-2c338c0c-73d6-fb80-cc91-f1a86e80db0c) 이상
  
- Microsoft Edge 안정 채널

## <a name="overview"></a>개요

레거시 호환성을 위해 Internet Explorer 11(IE11)이 필요한 조직의 경우 Microsoft Edge의 IE 모드(Internet Explorer 모드)는 원활한 단일 브라우저 환경을 제공합니다. 사용자는 IE11로 다시 전환할 필요 없이 Microsoft Edge 내에서 기존 응용 프로그램에 액세스할 수 있습니다.

IE 모드를 구성한 후에는 그룹 정책을 사용하여 조직 전체에서 **IE 모드 기능에 영향을 주지 않고** IE11을 독립 실행형 브라우저로 사용하지 않도록 설정할 수 있습니다.

> [!NOTE]
> 특정 사이트에 대한 독립 실행형 IE11 앱이 필요하고 다른 모든 브라우저 트래픽을 Microsoft Edge로 리디렉션하려면 [사이트 목록에 포함되지 않은 모든 사이트를 Microsoft Edge로 보내기](./edge-ie-mode-policies.md#redirect-sites-from-ie-to-microsoft-edge) 정책을 구성하여 IE에서 Microsoft Edge로 사이트를 리디렉션할 수 있습니다.

## <a name="user-experience-after-redirecting-traffic-to-microsoft-edge"></a>Microsoft Edge로 트래픽을 리디렉션한 후의 사용자 환경

**Internet Explorer 11을 독립 실행형 브라우저로 사용 안 함** 정책을 실행하면 모든 IE11 활동이 Microsoft Edge로 리디렉션되고 사용자는 다음과 같은 환경이 됩니다.

- 시작 메뉴와 작업 표시줄의 IE11 아이콘이 제거됩니다.
- 사용자가 IE11을 사용하는 바로 가기 또는 파일 연결을 시작하려고 하면 Microsoft Edge에서 동일한 파일/URL을 열도록 리디렉션됩니다.
- 사용자가 iexplore.exe 이진을 직접 호출하여 IE11을 실행하려고 하면 Microsoft Edge가 대신 실행됩니다.

이 환경에 대한 정책 설정의 일부로 IE11을 실행하려는 각 사용자에 대한 리디렉션 메시지를 선택적으로 표시할 수 있습니다. 이 메시지는 "항상" 또는 "사용자당 한 번"을 표시하도록 설정할 수 있습니다. 기본적으로 다음 스크린샷에 표시된 리디렉션 메시지는 표시되지 않습니다.

:::image type="content" source="media/edge-ie-disable-ie11/disable-ie-redirect-msg2.png" alt-text="Microsoft Edge에 대한 리디렉션이 활성화된 후 IE를 열려고 할 때 알림.":::

엔터프라이즈 모드 사이트 목록에 IE11 앱에서 열도록 구성된 응용 프로그램이 있고 이 정책으로 IE11을 사용하지 않도록 설정한 경우 Microsoft Edge에서 IE 모드로 열립니다.

> [!NOTE]
> 사이트가 IE11 애플리케이션에서 열리도록 구성되고 IE11 사용 안 함 정책이 설정된 경우 사용자 흐름에 알려진 문제가 있습니다. 이 문제는 Microsoft Edge 버전 91.0.840.0 이상에서 해결되었습니다.

## <a name="disable-internet-explorer-11-as-a-standalone-browser"></a>Internet Explorer 11을 독립 실행형 브라우저로 사용하지 않도록 설정

그룹 정책을 사용하여 Internet Explorer 11을 사용하지 않도록 설정하려면 다음 단계를 따릅니다.

1. 필요한 운영 체제 업데이트가 필요한지 확인합니다. 이 단계는 컴퓨터의 ADMX 파일을 직접 업데이트합니다(특히 inetres.adml 및 inetres.admx). Central Store를 업데이트하려면 필수 구성 요소 업데이트가 있는 컴퓨터에서 .adml 및 .admx 파일을 복사하거나 [여기에서](https://www.microsoft.com/download/details.aspx?id=103124&msclkid=eae4a72fb1fb11ecb97ca3096b36cc06) 최신 Windows 10 관리 템플릿을 다운로드해야 합니다. 자세한 내용은 [중앙 저장소 만들기 및 관리](/troubleshoot/windows-client/group-policy/create-and-manage-central-store)를 참조하세요.
2. 그룹 정책 편집기를 엽니다.
3. ***Computer Configuration/Administrative Templates/Windows Components/Internet Explorer***로 이동합니다.
4.  **Internet Explorer 11을 독립 실행형 브라우저로 사용하지 않도록 설정**을 두 번 클릭합니다.
5.  **사용**을 선택합니다.
6.  **옵션**에서 다음 값 중 하나를 사용할 수 있습니다.

   - IE11이 비활성화되었음을 사용자에게 알리지 않으려면 **절대** 를 선택합니다.
   - 사용자가 IE11에서 리다이렉션할 때 마다 알림을 보내려는 경우, **항상** 을 선택합니다.
   - 처음 리디렉션될 때만 사용자에게 알리려는 경우 **사용자당 한 번** 을 선택합니다.

7.  **SelectOKorApplyto**  **** 는 이 정책 설정을 저장합니다.

## <a name="see-also"></a>참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [IE 모드 정보](./edge-ie-mode.md)
- [추가 엔터프라이즈 모드 정보](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
