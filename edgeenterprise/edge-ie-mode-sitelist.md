---
title: 엔터프라이즈 사이트 목록에서 사이트 구성
ms.author: cjacks
author: cjacks
manager: saudm
ms.date: 05/28/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 엔터프라이즈 사이트 목록 구성
ms.openlocfilehash: 9b1943e4d50dcc770b4a634b99ecbd001d1ffbcc
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447652"
---
# <a name="configure-sites-on-the-enterprise-mode-site-list"></a>엔터프라이즈 사이트 목록에서 사이트 구성

이 문서에서는 Microsoft Edge 버전 77 이상에 대한 IE 모드 구성을 지원하는 엔터프라이즈 모드 사이트 목록의 변경 사항에 대해 설명합니다.

엔터프라이즈 모드 사이트 목록 XML 파일의 스키마에 대한 자세한 정보는 [엔터프라이즈 모드 스키마 v.2 지침](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)을 참조하세요.

> [!NOTE]
> 이 문서는 Microsoft Edge **안정**, **Beta** 및 **Dev** 채널 버전 77 이상에 적용됩니다.

## <a name="updated-schema-elements"></a>업데이트된 스키마 요소

다음 표는 엔터프라이즈 모드 스키마 v.2에 추가된 \<open-in app\> 요소를 설명합니다.

| **요소** | **설명** |
| --- | --- |
| \<open-in app="**true**"\> | 사이트에 사용되는 브라우저를 제어하는 자식 요소입니다. 이 요소는 **IE11에서 열어야 하는** 사이트에 필요합니다.|

**예제:**

``` xml
<site url="contoso.com">

  <open-in app="true">IE11</open-in>

</site>
```

다음 표는 \<open-in\> 요소에 사용할 수 있는 값을 보여 줍니다.

| **값** | **설명** |
| --- | --- |
| **\<open-in\>IE11\</open-in\>** | 사이트를 IE 모드로 열거나 전체 IE11 창으로 엽니다. IE 모드를 활성화하려면 [IE 모드 정책 구성](./edge-ie-mode-policies.md)을 참조하세요.|
| **\<open-in app="**true**"\>IE11\</open-in\>** | 전체 IE11 창에서 사이트를 엽니 다 |
| **\<open-in\>MSEdge\</open-in\>** | Microsoft Edge의 사이트를 엽니다 |
| **\<open-in\>없음 또는 지정하지 않음\</open-in\>** | 기본 브라우저 또는 사용자가 사이트를 탐색한 브라우저에서 사이트를 엽니다 |
|**\<open-in\>구성 가능 여부\</open-in\>** | 사이트가 IE 모드 엔진 결정에 참여할 수 있게합니다. 자세한 내용은 [IE 모드에서 구성 가능한 사이트에 대한 자세한 정보](edge-learnmore-configurable-sites-ie-mode.md)를 참조하세요.  |

>[!NOTE]
> app=**"true"** 특성은 _'open-in' IE11_에 연결된 경우에만 인식됩니다. 다른 'open-in' 요소에 추가해도 브라우저 동작이 변경되지 않습니다.   

## <a name="configure-neutral-sites"></a>중성 사이트 구성

IE 모드가 제대로 작동하려면 인증/Single Sign-on 서버를 중립적 사이트로 명시적으로 구성해야 합니다. 그렇지 않으면 IE 모드 페이지가 Microsoft Edge로 리디렉션을 시도하고 인증이 실패합니다.

중립 사이트는 탐색이 시작된 브라우저(Microsoft Edge 또는 IE 모드)를 사용합니다. 중립 사이트를 구성하면 최신 및 기존 인증 서버를 사용하는 모든 응용 프로그램이 계속 작동합니다.

엔터프라이즈 모드 사이트 목록 관리자 도구에서 *열기* 드롭다운을 '없음'으로 설정하거나 사이트 목록 XML을 직접 업데이트하여 중립 사이트를 구성할 수 있습니다.

``` xml
<site url="login.contoso.com">
   
    <open-in>None</open-in>

</site>
```

인증 서버를 식별하려면 IE11 개발자 도구를 사용하여 응용 프로그램에서 네트워크 트래픽을 검사합니다. 인증 서버를 식별하는 데 시간이 더 필요한 경우 모든 인 페이지 탐색을 IE 모드로 유지하도록 정책을 구성할 수 있습니다. IE 모드 사용을 최소화하려면 인증 서버를 식별하고 사이트 목록에 추가한 후에 이 설정을 비활성화하세요. 자세한 내용은 [IE 모드에 머무르기 위해 페이지 내 탐색 구성](./microsoft-edge-policies.md#internetexplorerintegrationsiteredirect)을 참조하세요.

>[!NOTE]
   >엔터프라이즈 모드 스키마 v.1은 IE 모드 통합에서 지원되지 않습니다. 현재 스키마 v.1을 Internet Explorer 11과 함께 사용하는 경우에는 스키마 v.2로 업그레이드해야 합니다. 자세한 내용은 [엔터프라이즈 모드 스키마 v.2 지침](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)을 참조하세요.

## <a name="see-also"></a>참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [IE 모드 정보](./edge-ie-mode.md)
- [추가 엔터프라이즈 모드 정보](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)