---
title: Microsoft Edge URL 정책용 필터 형식
ms.author: brianalt
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge URLBlocklist 및 URLAllowlist 정책에 사용되는 필터 형식에 대해 알아봅니다.
ms.openlocfilehash: e178dad518ff4bee07bf89d9faca3231ee6cf246
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642024"
---
# <a name="filter-format-for-url-list-based-policies"></a>URL 목록 기반 정책에 대한 필터 형식

이 문서에서는 Microsoft Edge URL 목록 기반 정책에 사용되는 필터 형식에 대해 설명합니다(예: [URLBlocklist](microsoft-edge-policies.md#urlblocklist), [URLAllowList](microsoft-edge-policies.md#urlallowlist), [CertificateTransparencyEnforcementDisabledForUrls](microsoft-edge-policies.md#certificatetransparencyenforcementdisabledforurls)).

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.

## <a name="the-filter-format"></a>필터 형식

필터 형식은 다음과 같습니다.

```
    [scheme://][.]host[:port][/path][@query]
```

필터 형식의 필드는 다음과 같습니다.

| 필드 | 설명 |
| --- | --- |
| **scheme**(*선택 사항*) | http://, https://, ftp://, edge:// 등일 수 있습니다. |
| **host**(*필수*) | 유효한 호스트 이름이어야 하며 와일드 카드("\*")를 사용할 수 있습니다. 하위 도메인 일치를 사용하지 않도록 설정하려면 **호스트** 앞에 점(".")을 포함합니다. 단일 IP 주소 리터럴 호스트 이름을 지정할 수 있지만 IP 주소 리터럴 호스트 이름에는 와일드카드를 사용할 수 없습니다. |
| **port**(*선택 사항*) | 유효한 값은 1~65535입니다. |
| **path**(*선택 사항*) | 경로에 임의의 문자열을 사용할 수 있습니다. |
| **query**(*선택 사항*) | **쿼리**는 앰퍼샌드("&")로 구분되는 키-값 또는 키-전용 토큰입니다. 키-값 토큰은 등호("=")를 사용하여 구분합니다. 접두사 일치를 표시하려면 **쿼리**끝에 별표("\*")를 사용할 수 있습니다. |

## <a name="comparing-the-filter-format-to-the-url-format"></a>필터 형식과 URL 형식 비교

필터 형식은 다음과 같은 차이를 제외하고 URL 형식과 유사합니다.

- "user:pass"를 포함하는 경우 이는 무시됩니다. 예: http://user:pass@ftp.contoso.com/pub/example.iso.
- 조각 식별자("#")를 포함하는 경우 조각 실별자와 식별자 뒤에 오는 모든 내용이 무시됩니다.
- 와일드 카드("*")를 **호스트**로 사용할 수 있으며 점(".")을 접두사로 사용할 수 있습니다.
- 슬래시("/") 또는 점(".")을 **호스트**의 접미사로 사용할 수 있습니다. 이 경우 접미사는 무시됩니다.

## <a name="filter-selection-criteria"></a>필터 선택 조건

URL에 대해 선택되는 필터는 다음 필터 선택 규칙을 처리한 후 검색된 가장 구체적인 일치 항목입니다.

1. 가장 긴 **host** 일치가 있는 필터가 먼저 선택됩니다.
2. 선택된 필터에서 일치하지 않는 구성표 또는 포트가 있는 필터는 모두 삭제됩니다.
3. 나머지 필터에서 가장 긴 일치하는 **path**가 있는 필터가 선택됩니다.
4. 나머지 필터에서 가장 긴 쿼리 토큰 집합이 있는 필터가 선택됩니다. 이 단계에서는 두 필터 모두 **경로** 길이와 **쿼리** 토큰 수가 동일하면 허용 목록 필터가 차단 목록 필터에 우선합니다.
5. 남은 유효한 필터가 없으면 가장 왼쪽에 있는 하위 도메인이 **host**에서 제거되고 선택 프로세스가 1단계부터 다시 시작됩니다. 특수 별표("*") **호스트**는 마지막으로 검색되고 모든 호스트와 일치합니다.
6. 필터를 사용할 수 있는 경우 해당 필터가 URL 요청을 차단하거나 허용합니다.

   >[!NOTE]
   >일치하는 필터가 없는 경우 기본 동작은 URL 요청을 허용하는 것입니다.

## <a name="example-filter-selection-criteria"></a>필터 선택 조건 예제

이 예제에서 "https://sub.contoso.com/docs"에 일치하는 항목을 검색할 경우 필터 선택은 다음과 같이 진행됩니다.

1. "sub.contoso.com"에 대한 필터를 검색합니다. 필터가 검색되면 검색이 2단계로 넘어갑니다. 필터가 검색되지 않으면 "contoso.com", "com", 그리고 "마지막으로"를 사용하여 다시 시도합니다.
2. 선택된 필터에서 **구성표**에 "http"가 없는 항목은 모두 제거됩니다.
3. 나머지 필터에서 정확한 포트 번호가 "80"이 아닌 항목은 모두 제거됩니다.
4. 나머지 필터에서 **path** 접두사로 "/docs"가 없는 항목은 모두 제거됩니다.
5. 나머지 필터에서 path 접두사가 가장 긴 필터가 선택되고 적용됩니다. 필터가 검색되지 않으면 1단계에서 선택 프로세스가 다시 시작됩니다. 프로세스가 다음 하위 도메인에서 반복됩니다.

### <a name="additional-filter-information"></a>추가 필터 정보

필터에 **호스트** 접두사로 점(".")이 있는 경우 정확히 **호스트**와 일치하는 항목만 필터링됩니다. 예를 들어,

- "contoso.com"(점 없음)은 "contoso.com", "www.contoso.com" 및 "sub.www.contoso.com"과 일치합니다.
- ".www.contoso.com"(점 접두사가 있음)은 "www.contoso.com"과만 일치합니다.

표준 또는 사용자 지정 **스키마**중 하나를 사용할 수 있습니다. 지원되는 표준 스키마는 다음과 같습니다.

- _about_, _blob_, _content_, _edge_, _cid_, _data_, _file_, _filesystem_, _ftp_, _gopher_, _http_, _https_, _javascript_, _mailto_, _ws_, _wss_.

다른 **스키마**는 사용자 지정 **스키마**로 취급되지만 _schema:*_ 및 _schema://*_ 패턴만 사용할 수 있습니다. 예를 들어:

- “custom:\*” 또는 “custom://\*”은 “custom:app”과 일치합니다.
- “custom:app” 또는 “custom://app”은 유효하지 않습니다.

**schema** 및 **host**는 대/소문자를 구분하지 않습니다. 예를 들어,

- “http://contoso.com” 필터는 “HTTP://contoso.com”, “http://contoso.COM” 및 “http://contoso.com”과 일치합니다.

**path** 및 **query**는 대/소문자를 구분합니다. 예를 들어,

- "http://contoso.com/path?query=A" 필터는 "http://contoso.com/Path?query=A" 또는 "http://contoso.com/path?Query=A"와 일치하지 않습니다. “http://contoso.COM/path?query=A”와는 일치합니다.

## <a name="content-license"></a>콘텐츠 라이선스

> [!NOTE]
> 이 페이지의 일부는 Chromium.org에서 생성 및 공유하고 [Creative Commons Attribution 4.0 국제 라이선스](http://creativecommons.org/licenses/by/4.0/)에 규정된 조건에 따라 사용되는 작업을 기반으로 합니다. 원래 [Chromium 페이지는 여기](https://www.chromium.org/administrators/url-blacklist-filter-format)에서 찾을 수 있습니다.
  
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />이 작업은 <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 국제 라이선스</a>에서 사용이 허가되었습니다.

## <a name="see-also"></a>참고 항목

- [Microsoft Edge Enterprise 방문 페이지](https://aka.ms/EdgeEnterprise)
