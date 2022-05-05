---
title: Microsoft Edge 'document.domain' 수정을 사용하지 않도록 설정합니다.
ms.author: niarci
author: dan-wesley
manager: erikan
ms.date: 04/25/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge 'document.domain' 수정을 사용하지 않도록 설정합니다.
ms.openlocfilehash: 197334da0f70aa2cfa081a240de383c79fbbf701
ms.sourcegitcommit: 592f6e40b13e28af588473b2a75c3ae697e5db2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2022
ms.locfileid: "12505733"
---
# <a name="microsoft-edge-will-disable-modifying-documentdomain"></a>Microsoft Edge 수정을 사용하지 않도록 설정합니다.`document.domain`

> [!NOTE]
> 이 문서는 Microsoft Edge 안정 버전 106 이상에 적용됩니다.

> [!WARNING]
> 웹 사이트가 동일한 원본 정책을 통해 `document.domain`완화에 의존하는 경우 작업이 필요합니다. 이 변경 이유에 대한 자세한 내용을 계속 읽거나 [원본 간 통신](#alternative-cross-origin-communication) 을 달성하기 위한 대체 메커니즘에 대해 알아보려면 대체 원본 간 통신으로 이동합니다.

## <a name="introduction"></a>소개

문서 인터페이스의 "domain" 속성은 [동일한 원본 정책](https://developer.mozilla.org/docs/Web/Security/Same-origin_policy)에서 사용하는 대로 현재 문서의 원본에 대한 도메인 부분을 가져오거나 설정합니다.

Microsoft Edge 버전 106부터 JavaScript를 사용하여 속성을 수정 `document.domain` 하려는 시도는 무시됩니다. 원본 간 통신을 위해 채널 메시징 API와 같은 `postMessage()` 대체 방법을 사용해야 합니다.

또는 웹 사이트가 제대로 작동하기 위해 동일한 원본 정책 완화 `document.domain` 를 사용하는 경우 사이트에서 헤더를 `Origin-Agent-Cluster: ?0` 보낼 수 있습니다. 이 헤더는 휴식이 필요한 다른 모든 문서에서 보내야 합니다.

> [!NOTE]
> `document.domain` 은 하나의 문서만 설정하는 경우 아무 효과가 없습니다.

## <a name="why-make-documentdomain-immutable"></a>`document.domain` 변경할 수 없는 이유는 무엇인가요?

일부 웹 사이트는 "동일하지만 원본 간" 페이지 간의 통신을 허용하도록 설정 `document.domain` 됩니다. 설정을 `document.domain` 사용하면 동일한 사이트 문서가 보다 쉽게 통신할 수 있습니다. 이 변경으로 [인해 동일한 원본 정책이 완화](https://html.spec.whatwg.org/multipage/origin.html#relaxing-the-same-origin-restriction)되므로 부모 페이지는 동일한 사이트 iframe의 문서에 액세스하고 DOM 트리를 트래버스할 수 있으며 그 반대의 경우도 마찬가지입니다.

> [!IMPORTANT]
> 동일 사이트이지만 원본 간 사이트는 [eTLD+1](https://web.dev/same-site-same-origin/#:~:text=the%20whole%20site%20name%20is%20known%20as%20the%20etld%2B1) 이 동일하지만 하위 도메인은 다릅니다.

의 iframe 페이지를 `https://parent.example.com` 포함하는 페이지를 `https://video.example.com`가정해 보겠습니다. 이러한 페이지에는 서로 다른 하위 도메인이 있는 동일한 eTLD+1(`example.com`)이 있습니다. 두 페이지가 `document.domain` 모두 설정된 `'example.com'`경우 브라우저는 두 페이지를 동일한 원본인 것처럼 처리합니다.

이 기술은 편리합니다. 하지만 보안 위험이 발생합니다.  

## <a name="security-concerns-with-documentdomain"></a>보안 문제 `document.domain`

관련 `document.domain` 보안 문제로 인해 사양이 변경되어 개발자에게 이 문제에 대해 경고하고 가능하면 사용하지 않도록 지시합니다. [다른 브라우저 공급업체](https://github.com/w3ctag/design-reviews/issues/564)와의 현재 논의는 동일한 방향으로 진행되고 있습니다.

다음 예제에서는 공격자가 악용 `document.domain`할 수 있는 방법을 보여 줍니다.

각 고객에게 고유한 하위 도메인을 제공하는 공유 호스팅 서비스를 고려합니다. 개발자가 페이지에 설정하는 `document.domain` 경우 다른 하위 도메인에서 제공된 공격자의 페이지는 동일한 값을 설정하고 피해자 페이지의 콘텐츠를 수정할 수 있습니다.

마찬가지로 각 고객에 대해 다른 포트를 사용하여 페이지를 제공하는 공유 호스팅 서비스를 고려합니다. 개발자가 해당 페이지에서 설정하는 `document.domain` 경우 다른 포트에서 제공된 공격자의 페이지는 동일한 값을 설정하고 피해자 페이지의 콘텐츠를 수정할 수 있습니다. 이 공격은 원본의 포트 번호 구성 요소를 무시하기 때문에 `document.domain` 가능합니다.

> [!NOTE]
>설정 `document.domain`의 보안 영향에 대해 자세히 알아보려면 [MDN의 Document.domain 문서를](https://developer.mozilla.org/docs/Web/API/Document/domain#setter) 참조하세요.

## <a name="how-will-i-know-if-my-site-is-affected"></a>내 사이트가 영향을 받는지 어떻게 알 수 있나요?

웹 사이트가 이 변경의 영향을 받는 경우 Microsoft Edge DevTools 문제 패널에 경고를 표시합니다. 다음 스크린샷은 이 경고의 예를 보여줍니다.

:::image type="content" source="media/edge-learnmore-origin-keyed-agent-cluster/document-domain-modification-warning.png" alt-text="document.domain이 수정될 때 경고입니다.":::

보고 엔드포인트를 설정한 경우 사용 중단 보고서도 전송됩니다. 기존 보고서 수집 서비스에서 또는 고유한 보고 솔루션을 빌드하여 [Reporting API를 사용하는 방법에](https://web.dev/reporting-api/) 대해 자세히 알아봅니다.

> [!TIP]
> [LightHouse 사용되지 않는 API 감사를](https://web.dev/deprecations/) 통해 사이트를 실행하여 Microsoft Edge 제거하도록 예약된 모든 API를 찾을 수 있습니다.

## <a name="alternative-cross-origin-communication"></a>대체 원본 간 통신

현재 웹 사이트를 대체할 `document.domain` 수 있는 두 가지 옵션이 있습니다. 대부분의 사용 사례에서 원본 간 [postMessage()](https://developer.mozilla.org/docs/Web/API/Window/postMessage) 또는 [Channel Messaging API](https://developer.mozilla.org/docs/Web/API/Channel_Messaging_API) 를 대체할 `document.domain`수 있습니다.

다음 목록에서는 원본 간 DOM 조작 대신 `document.domain` 개발자가 사용해야 `postMessage()` 하는 단계를 보여 줍니다.

1. `https://parent.example.com` 는 자체 DOM을 수정하도록 요청하는 메시지를 포함하는 `https://video.example.com` iframe으로 보냅니 `postMessage()` 다.
2. `https://video.example.com` 는 해당 DOM을 조작하고 부모에게 성공 사실을 알리는 데 사용합니다 `postMessage` .
3. `https://parent.example.com` 는 성공을 인정합니다.

1단계의 `https://parent.example.com`경우:

```

// Configure a handler to receive messages from the subframe.
iframe.addEventListener('message', (event) => { 

// Reject all messages except from https://video.example.com 
  if (event.origin !== 'https://video.example.com') return;
  
  // Filter success messages 
    if (event.data === 'succeeded') { 

    // DOM manipulation is succeeded 

  } 

}); 

// Send a message to the subframe at https://video.example.com

iframe.postMessage('Request DOM manipulation', 'https://video.example.com'); 

```

2단계의 `https://video.example.com`경우:

```

// Configure a handler to receive messages from the parent frame.
window.addEventListener('message', (event) => {
 
  // Reject all messages except ones from https://parent.example.com 
  
  if (event.origin !== 'https://parent.example.com') return;
  
  // Perform requested DOM manipulation on https://video.example.com.
  
  if (event.data === "showTheButton") {
     document.getElementById('btnContinue').style.visibility = 'visible';
     // Send a success message back to the parent.

     event.source.postMessage('succeeded', event.origin); 
  }
}); 

```

### <a name="send-the-origin-agent-cluster-0-header-as-a-last-resort"></a>헤더를 최후의 `Origin-Agent-Cluster: ?0` 수단으로 보내기

설정을 계속 `document.domain`해야 하는 강력한 이유가 있는 경우 대상 문서에 응답 헤더를 보낼 `Origin-Agent-Cluster: ?0` 수 있습니다.

```
Origin-Agent-Cluster: ?0 
```

헤더는 `Origin-Agent-Cluster` 원본 키 에이전트 클러스터에서 문서를 처리해야 하는지 여부를 브라우저에 지시합니다. 자세한 `Origin-Agent-Cluster`내용은 [Origin-Agent-Cluster 헤더를 사용하여 성능 격리 요청을](https://web.dev/origin-agent-cluster/) 읽어보세요.

이 헤더를 보내면 문서가 기본적으로 변경할 수 없게 된 후에도 계속 설정할 `document.domain` 수 있습니다.

## <a name="browser-compatibility"></a>브라우저 호환성

다음 조직에서는 브라우저 호환성을 위해 더 이상 사용되지 `document.domain` 않습니다.

- [원본 사양](https://html.spec.whatwg.org/multipage/origin.html#:~:text=Because%20of%20these%20security%20pitfalls%2C%20this%20feature%20is%20in%20the%20process%20of%20being%20removed%20from%20the%20web%20platform)은 기능을 제거해야 한다고 명시합니다.
- [Mozilla 표준 위치](https://github.com/mozilla/standards-positions/issues/601)는 기본적으로 프로토타입을 `document.domain` 작성할 가치가 있는 비활성화를 고려합니다.
- [WebKit](https://github.com/w3ctag/design-reviews/issues/564#issuecomment-768450217) 은 setter의 사용 `document.domain` 중단에 대해 적당히 긍정적임을 나타냅니다.

## <a name="other-resources"></a>다른 리소스

- [Document.domain](https://developer.mozilla.org/docs/Web/API/Document/domain)
- [원본 격리 및 사용 중단 `document.domain`](https://github.com/mikewest/deprecating-document-domain/)
- [setter 사용 중단 `document.domain`](https://github.com/w3ctag/design-reviews/issues/564)

## <a name="content-license"></a>콘텐츠 라이선스

> [!NOTE]
> 이 페이지의 일부는 Chromium.org에서 생성 및 공유하고 [Creative Commons Attribution 4.0 국제 라이선스](http://creativecommons.org/licenses/by/4.0/)에 규정된 조건에 따라 사용되는 작업을 기반으로 합니다. 원래 페이지는 [여기](https://developer.chrome.com/blog/immutable-document-domain/)에서 찾을 수 있습니다.

<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />이 작업은 <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 국제 라이선스</a>에서 사용이 허가되었습니다.
