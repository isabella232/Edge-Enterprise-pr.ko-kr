---
title: IE 모드에서 Microsoft Edge 및 구성 가능한 사이트
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: IE 모드에서 Microsoft Edge 및 구성 가능한 사이트
ms.openlocfilehash: 0248ecd394acee5773751c0685969e3d40940431
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "11979989"
---
# <a name="learn-about-configurable-sites-in-ie-mode"></a>IE 모드에서 구성 가능한 사이트 알아보기

이 문서에서는 Microsoft Edge에서 IE 모드를 사용할 때 엔터프라이즈 모드 사이트 목록의 구성 가능한 사이트 기능에 대해 설명합니다.

## <a name="prerequisites"></a>필수 구성 요소

- Windows 업데이트

  - Windows 10 버전 1909, Windows server 버전 1909 – KB4550945 이상
  - Windows 10 버전 1903, Windows server 버전 1903 – KB4550945 이상
  - Windows 10 버전 1809, Windows Server 버전 1809, and Windows Server 2019 - KB4550969 이상
  - Windows 10 버전 1803 – KB4550944 이상
  - Windows 10 버전 1607, Windows Server 2016-KB4556826 이상
  - Windows 10 초기 버전, 2015년 7월 - KB4550947 이상
  - Windows 8.1 – KB4556798 이상

- Microsoft Edge 버전 83 이상
- 엔터프라이즈 모드 사이트 목록으로 구성된 [IE 모드](./edge-ie-mode.md)

## <a name="overview"></a>개요

엔터프라이즈 모드 사이트 목록에서 IE 모드가 필요한 사이트를 구성하면 레거시 응용 프로그램을 사용하는 대부분의 환경에서 잘 작동합니다. 그러나 경우에 따라 IE 모드에서 전체 도메인을 렌더링하지 않고 IE 모드에서 열리도록 사이트 하위 집합을 구성하는 데 적합하지 않습니다. 예를 들어 사용자 환경이 단일 서버에서 실행되는 최신 및 레거시 응용 프로그램을 모두 포함하고 IE 모드에서 레거시 응용 프로그램만 렌더링하고 나머지 응용 프로그램은 Microsoft Edge 모드에서 렌더링할 수 있는 유연성을 원합니다.

해결 방법은 엔터프라이즈 모드 사이트 목록의 구성 가능한 사이트 기능을 사용하는 것입니다. 기능을 사용하게 하려면 Microsoft Edge에서 "구성 가능한" 태그가 있는 사이트를 IE 모드 엔진 결정에 참여하도록 허용합니다.

## <a name="how-configurable-sites-works"></a>구성 가능한 사이트 동작 방식

### <a name="automatic-switching-from-the-microsoft-edge-engine-to-the-ie-mode-engine"></a>Microsoft Edge 엔진에서 IE 모드 엔진으로 자동 전환

구성 가능한 사이트 기능을 사용하려면 `<open-in>Configurable</open-in>` 옵션이 있는 엔터프라이즈 모드 사이트 목록에서 하나 이상의 사이트가 필요합니다.

예제:

```
<site-list version="1">
  <site url="app.com">
    <open-in>Configurable</open-in>
  </site>
</site-list>
```

구성 가능한 사이트 기능을 사용하려면 다음이 동작이 수행됩니다.

1. 구성 가능한 사이트에 요청을 하면 Microsoft Edge에서 HTTP 요청 헤더 "`X-InternetExplorerModeConfigurable: 1`"를 보냅니다.
2. 구성 가능한 사이트는 HTTP 응답 헤더 "`X-InternetExplorerMode: 1`"와 함께 리디렉션 응답(예: HTTP 302)을 보내어 IE 모드에서 Microsoft Edge가 사이트를 로딩하도록 요청할 수 있습니다.
3. 리디렉션 대상 **(즉 위치** 응답 헤더의 값)도 구성 가능한 **또는** 중립 사이트 여야합니다. **그렇지 않으면** IE 모드의 응답 헤더가 무시됩니다. 대게 리디렉션 대상은 원래 URL과 같을 것으로 예상됩니다. 그러나 꼭 그럴 필요는 없습니다.

   > [!NOTE]
   > 리디렉션 응답은 리디렉션에 대한 Microsoft Edge의 일반 HTTP 캐싱 동작에 따라 캐싱이 됩니다.

### <a name="switching-back-from-ie-mode-engine-to-microsoft-edge-engine"></a>IE 모드 엔진에서 Microsoft Edge 엔진으로 다시 전환

Microsoft Edge에서 구성 가능한 사이트를 사용하면 IE 모드 탭에서 자동으로 다음과 같은 동작이 수행됩니다.

1. 구성 가능한 사이트에 요청을 하면 IE 모드 탭은 Microsoft Edge 탭과 동일한 HTTP 요청 헤더 "`X-InternetExplorerModeConfigurable: 1`"를 보냅니다.
2. 구성 가능한 사이트는 HTTP 응답 헤더 "`X-InternetExplorerMode: 0`"와 함께 리디렉션 응답(예: HTTP 302)을 보내 탐색이 Microsoft Edge 모드로 다시 전환되도록 요청할 수 있습니다.
3. 리디렉션 대상 **(즉 위치** 응답 헤더의 값)도 구성 가능한 **또는** 중립 사이트 여야합니다. **그렇지 않으면** IE 모드의 응답 헤더가 무시됩니다. 대게 리디렉션 대상은 원래 URL과 같을 것으로 예상됩니다. 그러나 꼭 그럴 필요는 없습니다.

   > [!NOTE]
   > 리디렉션 응답은 리디렉션에 대한 Microsoft Edge의 일반 HTTP 캐싱 동작에 따라 캐싱이 됩니다.

> [!TIP]
> 두 브라우저 엔진은 구성 가능한 사이트에 동일한 "`X-InternetExplorerModeConfigurable: 1`" 요청 헤더를 보냅니다. 사이트가 올바른 엔진에서 이미 로드될 때 리디렉션하지 않도록 하려면 사용자 에이전트 요청 헤더를 사용하여 Microsoft Edge 모드와 IE 모드의 요청을 구분해야 합니다.

## <a name="see-also"></a>참고 항목

- [IE 모드 정보](./edge-ie-mode.md)
- [추가 엔터프라이즈 모드 정보](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)