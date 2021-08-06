---
title: 최신 웹 사이트와의 호환성을 위해 Internet Explorer에서 Microsoft Edge로 리디렉션
ms.author: laannade
author: dan-wesley
manager: ratetali
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 최신 웹 사이트와의 호환성을 위해 Internet Explorer에서 Microsoft Edge로 리디렉션
ms.openlocfilehash: 0d60dd2bdef87942087399afd5034454eead66ddc8e244df04c6e86ae2a73700
ms.sourcegitcommit: d44c0997ffe40d67421312ed96e7766da947eaa0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "11724255"
---
# <a name="redirection-from-internet-explorer-to-microsoft-edge-for-compatibility-with-modern-web-sites"></a>최신 웹 사이트와의 호환성을 위해 Internet Explorer에서 Microsoft Edge로 리디렉션

> [!NOTE]
> 이 문서는 Microsoft Edge 안정 버전 87 이상에 적용됩니다.

## <a name="overview"></a>개요

>[!Note]
> Internet Explorer 11 데스크톱 응용 프로그램은 2022년 6월 15일 사용 및 지원이 중단됩니다(범위 내 항목 목록은 [FAQ 참고](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)). 현재 사용하는 동일한 IE11 앱과 사이트는 Internet Explorer 모드에서 Microsoft Edge로 열 수 있습니다. [여기서 자세한 내용을 알아보세요](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/).

많은 최신 웹 사이트에는 Internet Explorer와 호환되지 않는 디자인이 있습니다. Internet Explorer 사용자는 호환되지 않는 공용 사이트를 방문할 때 사이트가 브라우저와 호환되지 않는다는 메시지를 받고 수동으로 다른 브라우저로 전환해야 합니다.

Microsoft Edge 안정 버전 87부터 다른 브라우저로 수동으로 전환할 필요성이 변경됩니다.

사용자가 Internet Explorer와 호환되지 않는 사이트로 이동할 때, 사용자는 자동으로 Microsoft Edge로 리디렉션됩니다. 이 문서에서는 리디렉션에 대한 사용자 환경 및 자동 리디렉션을 구성하거나 해제하는 데 사용되는 그룹 정책을 설명합니다.

> [!NOTE]
> Microsoft는 Internet Explorer와 호환되지 않는 것으로 알려진 모든 사이트 목록을 유지하고 있습니다. 자세한 내용은 [호환되지 않는 사이트 목록 업데이트 요청](/microsoft-edge/web-platform/ie-to-microsoft-edge-redirection#request-an-update-to-the-ie-compatibility-list)을 참조하세요.

## <a name="prerequisites"></a>필수 구성 요소
- Microsoft Edge 안정적인 버전 87 이상
- Windows 버전
    - Windows 10 버전 1709 이상
    - Windows 8.1
    - Windows 7



## <a name="redirection-experience"></a>리디렉션 환경

Microsoft Edge로 리디렉션 시, 사용자에게 다음 스크린샷의 일회성 대화 상자가 표시됩니다. 이 대화 상자는 리디렉션되는 이유를 설명하고 Internet Explorer에서 Microsoft Edge로 그들의 검색 데이터와 기본 설정을 복사하라는 메시지를 표시합니다. 즐겨찾기, 암호, 검색 엔진, 열린 탭, 기록, 설정, 쿠키 및 홈 페이지와 같은 다음의 검색 데이터를 가져올 수 있습니다.

![검색 알림 및 데이터와 기본 설정을 가져올 것인지 묻는 메시지입니다.](media/edge-learnmore-neededge/neededge-dialog1.png)

"검색 데이터를 언제든지 Internet Explorer에서 가져옵니다"를 선택하여 동의하지 않는 경우에도  **계속 탐색** 을 클릭하여 세션을 계속할 수 있습니다.

마지막으로 다음 스크린샷에 표시된 웹 사이트 비호환 배너는 모든 리디렉션 시 주소 표시줄 아래에 표시됩니다.

![최신 사이트에 대한 알림과 Microsoft Edge를 기본 브라우저로 설정하거나 Microsoft Edge를 탐색하라는 메시지입니다.](media/edge-learnmore-neededge/neededge-banner.png)

웹 사이트 비호환 배너:

- 사용자에게 Microsoft Edge로 전환할 것을 권장
- Microsoft Edge를 기본 브라우저로 설정하도록 제안
- 사용자에게 Microsoft Edge를 탐색할 수 있는 옵션을 제공

사이트가 Internet Explorer에서 Microsoft Edge로 리디렉션되는 경우, 이전 콘텐츠가 없는 경우에 사이트를 로드하기 시작한 Internet Explorer 탭은 닫힙니다. 그렇지 않으면 활성 탭 보기가 Microsoft Edge로 리디렉션된 이유를 설명하는 Microsoft [지원](https://support.microsoft.com/office/the-website-you-were-trying-to-reach-doesn-t-work-with-internet-explorer-8f5fc675-cd47-414c-9535-12821ddfc554?ui=en-US&rs=en-US&ad=US) 페이지로 이동합니다.

> [!NOTE]
> 리디렉션 후, 사용자는 Internet Explorer로 돌아가서 비호환 목록에 없는 사이트를 사용할 수 있습니다.  

## <a name="policies-to-configure-redirection-to-microsoft-edge"></a>Microsoft Edge로의 리디렉션 구성 정책

> [!NOTE]
> 이러한 정책은 2020년 10월 26일까지 ADMX 파일 업데이트로 제공될 예정이며 2020년 11월 9일까지 Intune에서 제공될 것입니다.

Microsoft Edge로의 자동 리디렉션을 사용하려면 세 가지 그룹 정책을 구성해야 합니다. 이들 정책은 다음과 같습니다.

- RedirectSitesFromInternetExplorerPreventBHOInstall
- RedirectSitesFromInternetExplorerRedirectMode
- HideInternetExplorerRedirectUXForIncompatibleSitesEnabled

### <a name="policy-redirectsitesfrominternetexplorerpreventbhoinstall"></a>정책: RedirectSitesFromInternetExplorerPreventBHOInstall

Internet Explorer에서 Microsoft Edge로 리디렉션하는 경우 "IEtoEdge BHO" 라는 Internet Explorer BHO(브라우저 도우미 개체)가 필요합니다. **RedirectSitesFromInternetExplorerPreventBHOInstall** 정책은 이 BHO의 설치 여부를 제어합니다.  

- 이 정책을 사용하도록 설정하면 리디렉션에 필요한 BHO가 설치되지 않고 사용자는 Internet Explorer에서 특정 웹 사이트에 대한 비호환 메시지를 계속해서 보게됩니다. BHO가 이미 설치되어 있는 경우, 다음에 Microsoft Edge 안정 채널이 업데이트될 때 제거됩니다.
- 이 정책을 사용하지 않도록 설정하거나 구성하지 않으면 BHO가 설치됩니다. 이것이 기본 동작입니다.

BHO를 필요로 하는 것 외에도 "호환되지 않는 사이트 Sitelist에 따라 사이트를 리디렉션" 또는 "구성되지 않음"으로 설정해야 하는 **RedirectSitesFromInternetExplorerRedirectMode**에 대한 종속성이 있습니다.

### <a name="policy-redirectsitesfrominternetexplorerredirectmode"></a>정책: RedirectSitesFromInternetExplorerRedirectMode

 이 정책은 Microsoft Edge **기본 브라우저** 설정 "Internet Explorer가 Microsoft Edge에서 사이트를 열 수 있도록 허용"에 해당하는 정책입니다. *edge://settings/defaultbrowser* URL로 이동하여 이 설정에 액세스할 수 있습니다.  

- 이 정책을 구성하지 않거나 "Sitelist"로 설정하면 Internet Explorer에서 호환되지 않는 사이트를 Microsoft Edge로 리디렉션합니다. 이것이 기본 동작입니다.
- 이 정책을 사용하지 않도록 설정하려면 **사용**을 선택하고 옵션 아래의 드롭다운 목록, Internet Explorer에서 Microsoft Edge로 호환되지 않는 사이트를 리디렉션에서 **사용 안 함**을 선택합니다. 이 상태에서는 호환되지 않는 사이트가 Microsoft Edge로 리디렉션되지 않습니다.

> [!NOTE]
> 조직에서 관리하지 않는 개인 장치를 사용하고 있는 경우, **Internet Explorer 호환성**에서 "사이트가 Internet Explorer 모드에서 로드되도록 허용"이라는 다른 설정을 볼 수 있습니다.
>
>도메인에 연결되었거나 MDM(모바일 장치 관리)에 등록된 장치를 사용하는 경우에는 이 옵션이 표시되지 않습니다.
>
> 대신 사용자가 Internet Explorer 모드에서 사이트를 로드할 수 있게 하려는 경우에는 [Internet Explorer 모드 테스트 허용](./microsoft-edge-policies.md#intranetredirectbehavior) 정책을 구성할 수 있습니다.

### <a name="policy-hideinternetexplorerredirectuxforincompatiblesitesenabled"></a>정책: HideInternetExplorerRedirectUXForIncompatibleSitesEnabled

이 정책은 Microsoft Edge로의 호환되지 않는 사이트 리디렉션에 대한 사용자 환경을 구성합니다.  

- 이 정책을 사용하도록 설정하면 사용자에게 일회성 리디렉션 대화 상자와 리디렉션 배너가 표시되지 않습니다. 어떠한 브라우저 데이터나 사용자 기본 설정도 가져오지 않습니다.
- 이 정책을 사용하지 않도록 설정하거나 구성하지 않으면 최초 리디렉션 시 리디렉션 대화 상자가 표시되고 리디렉션으로 시작하는 세션에 대해서는 영구적인 리디렉션 배너가 표시됩니다.

  > [!NOTE]
  > 사용자가 새 리디렉션에 직면할 때마다 사용자 검색 데이터를 가져오게 됩니다. 그러나 이는 사용자가 일회성 리디렉션 대화 상자에서 가져오기에 동의한 경우에만 발생합니다.

## <a name="disable-redirection-to-microsoft-edge"></a>Microsoft Edge로의 리디렉션 사용 안 함

Microsoft Edge 안정 버전 87로 업데이트하기 전에 리디렉션을 사용하지 않도록 설정하려면 다음 단계를 사용합니다.

1. **RedirectSitesFromInternetExplorerPreventBHOInstall** 정책을 **사용**으로 설정합니다.

Microsoft Edge 안정 버전 87로 업데이트한 후에 리디렉션을 사용하지 않도록 설정하려면 다음 단계를 사용합니다.

1. **RedirectSitesFromInternetExplorerRedirectMode** 정책을 **사용**으로 선택하고 옵션 아래의 드롭다운 목록, Internet Explorer에서 Microsoft Edge로 호환되지 않는 사이트를 리디렉션에서 **사용 안 함**을 선택합니다. 이 설정은 정책이 적용되는 즉시 리디렉션을 중지합니다.
2. **RedirectSitesFromInternetExplorerPreventBHOInstall** 정책을 **사용**으로 설정합니다. 이 설정은 다음 Microsoft Edge 업데이트 후에 BHO를 제거합니다.

## <a name="see-also"></a>참고 항목

- [호환되지 않는 사이트 목록에 업데이트 요청](/microsoft-edge/web-platform/ie-to-microsoft-edge-redirection#request-an-update-to-the-ie-compatibility-list)
- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge 정책](./microsoft-edge-policies.md)