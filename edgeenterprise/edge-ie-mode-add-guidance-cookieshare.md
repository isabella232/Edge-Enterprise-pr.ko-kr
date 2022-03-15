---
title: 사용자 및 Microsoft Edge Internet Explorer
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 03/08/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 사용자 및 사이트 간에 쿠키를 공유하는 Microsoft Edge Internet Explorer
ms.openlocfilehash: 7a65979023f8ab96efe6ad30d0f8016055fe46c1
ms.sourcegitcommit: 556aca8dde42dd66364427f095e8e473b86651a0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2022
ms.locfileid: "12445782"
---
# <a name="cookie-sharing-between-microsoft-edge-and-internet-explorer"></a>사용자 및 Microsoft Edge Internet Explorer

>[!Note]
> IE(Internet Explorer) 11 데스크톱 응용 프로그램은 사용 중지되어 2022년 6월 15일에는 지원이 중지됩니다. IE 11이 사용 중지된 경우 범위 및 범위에서 범위를 벗어났는 것을 알려면 Internet Explorer 데스크톱 앱 사용 중지 [FAQ를 참조하세요](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549). 현재 사용하는 동일한 IE 11 앱과 사이트는 Microsoft Edge 모드로 열 Internet Explorer 있습니다. 자세한 내용은 2016년 12월 Internet Explorer [Windows 10 참조 Microsoft Edge](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/).

이 문서에서는 Microsoft Edge 모드를 사용하는 동안 Internet Explorer 프로세스 간에 세션 쿠키 공유를 구성하는 Internet Explorer 설명합니다.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 87 이상에 적용됩니다.

## <a name="prerequisites"></a>필수 구성 요소

세션 쿠키를 공유하는 Microsoft Edge 다음 Internet Explorer.

- Windows 업데이트

  - Windows 11
  - Windows 10 버전 2004, Windows Server 버전 2004 - KB4571744 이상
  - Windows 10 버전 1909, Windows Server 버전 1909 – KB4566116 이상
  - Windows 10 버전 1903, Windows Server 버전 1903 – KB4566116 이상
  - Windows 10 버전 1809, Windows Server 버전 1809 및 Windows Server 2019 - KB4571748 이상
  - Windows 10 버전 1803 – KB4577032 이상
  - Windows 10 Enterprise 2016 LTSC 및 Windows Server 2016 - KB4580346 이상
  - Windows 10 Enterprise 2015 LTSB - KB4580327 이상
  - Windows 8.1 및 Windows Server 2012 R2 - KB4586768 이상
  - Windows 10 Enterprise 2016 LTSC 및 Windows Server 2016 - KB4580346 이상
  - Windows 10 Enterprise 2015 LTSB - KB4580327 이상
  - Windows 8.1 및 Windows Server 2012 R2 - KB4586768 이상
- Microsoft Edge 버전 87 이상
- 엔터프라이즈 모드 사이트 목록으로 구성된 [IE 모드](./edge-ie-mode.md) 

사용자와 사용자 간에 세션 Microsoft Edge 공유 Internet Explorer.

- Windows 업데이트
  
  - Windows 11 - KB5010414 이상
  - Windows Server 2022 - KB5010421 이상
  - Windows 10 버전 20H2 - KB5010415 이상
  - Windows 10 버전 21H1 - KB5010415 이상
  - Windows 10 버전 21H2- KB5010415 이상
- Microsoft Edge 버전 99 이상
- 엔터프라이즈 모드 사이트 목록으로 구성된 [IE 모드](./edge-ie-mode.md) 

## <a name="overview"></a>개요

대규모 조직의 일반적인 구성은 최신 브라우저에서 작동하는 응용 프로그램을 다른 응용 프로그램에 연결하는 것으로, 이는 워크플로의 일부로써 SSO(Single Sign On)를 사용하도록 설정된 Internet Explorer 모드에서 열리도록 구성할 수 있습니다.

기본적으로 Microsoft Edge Internet Explorer 프로세스는 세션 쿠키를 공유하지 않습니다. 이러한 공유 부족은 경우에 따라 불편할 수 있습니다. 예를 들어 사용자가 Internet Explorer 모드에서 다시 Microsoft Edge 세션에서 로그인해도 Internet Explorer 모드 세션에서 Internet Explorer 없습니다. 이러한 시나리오에서는 SSO에서 설정한 특정 쿠키를 Microsoft Edge에서 Internet Explorer로 보내도록 구성할 수 있으므로 재인증할 필요가 없어져서 인증 환경이 더욱 원할해집니다.

> [!NOTE]
> 버전 Microsoft Edge 100을 시작하기 전에 세션 쿠키는 100 버전에서 Microsoft Edge Internet Explorer. Microsoft Edge 버전 100부터 세션 쿠키를 역방향으로 공유할 수 있습니다(Internet Explorer Microsoft Edge).

## <a name="how-cookie-sharing-works"></a>쿠키 공유 작동 방식

Enterprise 모드 사이트 목록 XML이 확장되어 더 많은 요소가 사이트와 사이트 간에 공유해야 하는 세션 쿠키를 Microsoft Edge Internet Explorer.

Microsoft Edge 세션에서 Internet Explorer 모드 탭을 처음 만들 때 일치하는 모든 쿠키가 Internet Explorer 세션에 공유됩니다. 그런 다음 규칙과 일치하는 쿠키를 추가, 삭제 또는 수정하면 언제든지 해당 쿠키가 해당 세션에 대한 업데이트로 Internet Explorer 전송됩니다. 사이트 목록이 업데이트될 때 공유 쿠키 집합도 다시 평가됩니다.

### <a name="updated-schema-elements"></a>업데이트된 스키마 요소

다음 표에서는 쿠키 공유 기능을 지원하기 위해 추가된 \<shared-cookie\> 요소에 대해 설명합니다.

| 요소| 설명 |
|-|-|
| \<shared-cookie **domain**=".contoso.com" **name**="cookie1"\>\</shared-cookie\><br><br>또는<br><br>\<shared-cookie **host**="subdomain.contoso.com" **name**="cookie2"\>\</shared-cookie\>   |**(필수)** \<shared-cookie\>요소에는 최소한 *도메인*(도메인 쿠키에 해당) 또는 *호스트*(호스트 전용 쿠키에 해당) 특성 및 *이름* 특성이 필요합니다.<br>이러한 특성은 각각 쿠키의 도메인 및 이름과 정확히 일치해야 합니다. **하위** 도메인과 일치하지 않는 점에 유의하세요.<br><br>*도메인* 속성은 도메인 쿠키에 사용됩니다(앞에 점이 허용되지만 이는 선택 사항임).<br>*호스트* 특성에는 호스트 전용 쿠키가 사용됩니다(앞에 점은 오류임). 둘 다 지정하지 않거나 둘 다 지정하면 오류가 발생합니다.<br>* 여기서 쿠키는, 쿠키 문자열에 도메인이 지정된 경우(HTTP 집합-쿠키 응답 헤더 또는 document.cookie JS API를 통해)의 도메인 쿠키입니다. 도메인 쿠키는 지정된 도메인 및 모든 하위 도메인에 적용됩니다. 도메인이 쿠키 문자열에 지정되지 않은 경우 쿠키는 호스트 전용 쿠키로, 설정된 특정 호스트에만 적용됩니다. 단일 단어 호스트 이름과 같은 일부 URL http://intranetsite) 클래스(예: IP http://10.0.0.1) 주소)는 호스트 전용 쿠키만 설정할 수 있습니다.    |
| \<shared-cookie **host**="subdomain.contoso.com" **name**="cookie2" **path**="/a/b/c"\>\</shared-cookie\>  | **(선택 사항)** *경로* 특성을 지정할 수 있습니다. 경로 특성을 지정하지 않은 경우(또는 경로 특성이 비어있는 경우), 도메인/호스트 및 이름과 일치하는 모든 쿠키가 경로(와일드 카드 규칙)에 상관없이 정책과 일치합니다.<br><br>경로가 지정되면 쿠키가 정확하게 일치해야 합니다.<br>쿠키가 경로와 일치하는 경우, 경로가 없는 규칙보다 우선합니다. |
| \<shared-cookie **domain**=".contoso.com" **name**="cookie1" **source-engine**="MSEdge"\>\</shared-cookie\><br><br>또는<br><br>\<shared-cookie **domain**=".contoso.com" **name**="cookie1" **source-engine**="IE11"\>\</shared-cookie\><br><br>또는<br><br>\<shared-cookie **domain**=".contoso.com" **name**="cookie1" **source-engine**="Both"\>\</shared-cookie\> | **(선택 사항)** source-engine 특성은 세션 쿠키가 사용자와 사용자 간에 공유되는 Microsoft Edge Internet Explorer. 여기서<br><br>- **MSEdge**. 세션 쿠키를 Microsoft Edge 쿠키를 Internet Explorer.<br>- **IE11**.  세션 쿠키를 Internet Explorer 쿠키를 Microsoft Edge.<br>- **둘 다**. 사용자 및 사용자와 세션 Microsoft Edge Internet Explorer.<br>- **기본값 또는 지정되지 않습니다**. 세션 쿠키는 사용자와 Microsoft Edge 공유 Internet Explorer. |

#### <a name="sharing-example"></a>공유 예

```xml
<site-list version="1"> 
<shared-cookie domain=".contoso.com" name="cookie1"></shared-cookie>  
<shared-cookie host="subdomain.contoso.com" name="cookie2" path="/a/b/c"> 
</shared-cookie> 
<shared-cookie host="subdomain.contoso.com" name="cookie3" source-engine="MSEdge"></shared-cookie> 
</site-list> 
```

## <a name="see-also"></a>참고 항목

- [IE 모드 정보](./edge-ie-mode.md)
- [구성 가능한 사이트 정보](./edge-learnmore-configurable-sites-ie-mode.md)
- [추가 엔터프라이즈 모드 정보](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
