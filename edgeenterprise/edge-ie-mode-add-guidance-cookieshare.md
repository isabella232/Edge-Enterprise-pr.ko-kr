---
title: Microsoft Edge에서 Internet Explorer로 쿠키 공유
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 11/05/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 'Microsoft Edge에서 Internet Explorer로 쿠키를 공유하는 방법 '
ms.openlocfilehash: 5740a4ce31a240573b9106e7a20a5c44688aca0a
ms.sourcegitcommit: 2024629929044e2dcf146674058c1d6312c32e9a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/06/2020
ms.locfileid: "11157547"
---
# Microsoft Edge에서 Internet Explorer로 쿠키 공유

이 문서에서는 Internet Explorer 모드를 사용하는 동안 Microsoft Edge 프로세스에서 Internet Explorer 프로세스로 세션 쿠키 공유를 구성하는 방법에 대해 설명합니다.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 87 이상에 적용됩니다.

## 필수 구성 요소

- Windows 업데이트

  - Windows 10 버전 2004, Windows Server 버전 2004 - KB4571744 이상
  - Windows 10 버전 1909, Windows Server 버전 1909 – KB4566116 이상
  - Windows 10 버전 1903, Windows Server 버전 1903 – KB4566116 이상
  - Windows 10 버전 1809, Windows Server 버전 1809 및 Windows Server 2019 - KB4571748 이상
  - Windows 10 버전 1803 – KB4577032 이상

- Microsoft Edge 버전 87 이상
- 엔터프라이즈 모드 사이트 목록으로 구성된 [IE 모드](https://aka.ms/iemodeonedge) 

## 개요

대규모 조직의 일반적인 구성은 최신 브라우저에서 작동하는 응용 프로그램을 다른 응용 프로그램에 연결하는 것으로, 이는 워크플로의 일부로써 SSO(Single Sign On)를 사용하도록 설정된 Internet Explorer 모드에서 열리도록 구성할 수 있습니다.

기본적으로 Microsoft Edge 및 Internet Explorer 프로세스는 세션 쿠키를 공유하지 않으며, 경우에 따라 이 프로세스가 번거로울 수 있습니다. 예를 들어, 사용자가 Internet Explorer 모드로 다시 인증해야 하거나 Microsoft Edge 세션에서 로그아웃할 때 Internet Explorer 모드 세션에서 로그아웃되지 않습니다. 이러한 시나리오에서는 SSO에 의해 설정된 특정 쿠키를 Microsoft Edge에서 Internet Explorer로 보내도록 구성할 수 있으므로 재인증할 필요없이 인증 환경이 더욱 원활해집니다.

> [!NOTE]
> 세션 쿠키는 Microsoft Edge에서 Internet Explorer로만 공유할 수 있습니다. 세션 쿠키를 반대로(Internet Explorer에서 Microsoft Edge로) 공유할 수는 없습니다.

## 쿠키 공유 작동 방식

Internet Explorer를 사용하여 Microsoft Edge 세션에서 공유되는 쿠키를 추가 요소로 지정할 수 있도록 엔터프라이즈 모드 사이즈 목록 XML이 확장됩니다.  

Microsoft Edge 세션에서 Internet Explorer 모드 탭을 처음 만들 때 일치하는 모든 쿠키가 Internet Explorer 세션에 공유됩니다. 그런 다음, 규칙과 일치하는 쿠키가 추가, 삭제 또는 수정될 때마다 Internet Explorer 세션에 대한 업데이트로 전송됩니다. 공유 쿠키 집합은 사이트 목록이 업데이트되는 경우에도 다시 평가됩니다.

### 업데이트된 스키마 요소

다음 표에서는 쿠키 공유 기능을 지원하기 위해 추가된 \<shared-cookie\> 요소에 대해 설명합니다.

| 요소| 설명 |
|-|-|
| \<shared-cookie **domain**=".contoso.com" **name**="cookie1"\>\</shared-cookie\><br><br>또는<br><br>\<shared-cookie **host**="subdomain.contoso.com" **name**="cookie2"\>\</shared-cookie\>   |**(필수)** \<shared-cookie\>요소에는 최소한 *도메인*(도메인 쿠키에 해당) 또는 *호스트*(호스트 전용 쿠키에 해당) 특성 및 *이름* 특성이 필요합니다.<br>이러한 항목은 각각 쿠키의 도메인 및 이름과 정확히 일치해야 합니다. **하위** 도메인과 일치하지 않는 점에 유의하세요.<br><br>*도메인* 속성은 도메인 쿠키에 사용됩니다(앞에 점이 허용되지만 이는 선택 사항임).<br>*호스트* 특성에는 호스트 전용 쿠키가 사용됩니다(앞에 점은 오류임). 둘 다 지정하지 않거나 둘 다 지정하면 오류가 발생합니다.<br>* 여기서 쿠키는, 쿠키 문자열에 도메인이 지정된 경우(HTTP 집합-쿠키 응답 헤더 또는 document.cookie JS API를 통해)의 도메인 쿠키입니다. 도메인 쿠키는 지정된 도메인 및 모든 하위 도메인에 적용됩니다. 쿠키 문자열에 도메인이 지정되지 않은 경우, 쿠키는 호스트 전용 쿠키 이며 설정된 특정 호스트에만 적용됩니다. 한 단어로 된 호스트 이름(예: http://intranetsite) 및 IP 주소(예: http://10.0.0.1)와 같은 일부 URL 클래스는 호스트 전용 쿠키만 설정할 수 있음에 유의하세요.    |
| \<shared-cookie **host**="subdomain.contoso.com" **name**="cookie2" **path**="/a/b/c"\>\</shared-cookie\>  | **(선택 사항)** *경로* 특성을 지정할 수 있습니다. 경로 특성을 지정하지 않은 경우(또는 경로 특성이 비어있는 경우), 도메인/호스트 및 이름과 일치하는 모든 쿠키가 경로(와일드 카드 규칙)에 상관없이 정책과 일치합니다.<br><br>경로가 지정되면 쿠키가 정확하게 일치해야 합니다.<br>쿠키가 경로와 일치하는 경우, 경로가 없는 규칙보다 우선합니다. |

#### 공유 예

```xml
<site-list version="1">
<shared-cookie domain=".contoso.com" name="cookie1"></shared-cookie> 
<shared-cookie host="subdomain.contoso.com" name="cookie2" path="/a/b/c">
</shared-cookie>
</site-list>
```

## 참고 항목

- [IE 모드 정보](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [구성 가능한 사이트 정보](https://docs.microsoft.com/deployedge/edge-learnmore-configurable-sites-ie-mode)
- [추가 엔터프라이즈 모드 정보](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
