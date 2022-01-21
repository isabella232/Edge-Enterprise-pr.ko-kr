---
title: Microsoft Edge에서 혼합 콘텐츠 다운로드를 처리하는 방법 알아보기
ms.author: collw
author: dan-wesley
manager: srugh
ms.date: 11/24/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 혼합 콘텐츠 다운로드 및 Microsoft Edge에서 이를 처리하는 방법에 대해 알아봅니다.
ms.openlocfilehash: c199a8b763e456daac34bd1ba07e64ced50358f5
ms.sourcegitcommit: e7f3098d8b7d91cae20b5778a71a87daababc312
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "12298286"
---
# <a name="learn-how-microsoft-edge-handles-mixed-content-downloads"></a>Microsoft Edge에서 혼합 콘텐츠 다운로드를 처리하는 방법 알아보기

이 문서에서는 혼합 콘텐츠 다운로드를 정의하고 Microsoft Edge에서 이를 처리하는 방법을 설명합니다.

>[!NOTE]
>이 문서는 Microsoft Edge 버전 85 이상에 적용됩니다.

## <a name="what-are-mixed-content-downloads"></a>혼합 콘텐츠 다운로드란?

보안 HTTPS 연결을 통해 로드된 HTML 페이지에서 다운로드를 시작할 때 혼합 콘텐츠 다운로드가 일어납니다. 단, 다음 조건에 부합해야 합니다.

- 하나 이상의 다운로드 위치 리디렉션이 보안되지 않은 HTTP 연결을 통해 로드됩니다.
- 최종 다운로드 위치가 보안되지 않은 HTTP 연결을 통해 로드됩니다.

이전 시나리오 중 하나는 보안 HTTPS를 사용하여 요청이 만들어졌고 HTTP 및 HTTPS 연결이 모두 최종 대상에 도달하는 데 사용되기 때문에 혼합 콘텐츠 다운로드에 해당됩니다. 최신 브라우저는 원본 페이지에 안전하게 액세스한 경우에도 이 다운로드가 안전하지 않게 전송될 수 있음을 나타내기 위해 이러한 유형의 콘텐츠에 대한 경고를 표시합니다.

## <a name="download-warnings-and-user-options"></a>다운로드 경고 및 사용자 옵션

다운로드 경고를 통해 사용자는 다운로드하는 파일을 네트워크에 있는 악의적인 공격자가 읽을 수 있음을 알게 됩니다. 사용자는 이 경고를 보고 파일을 다운로드할 것인지 결정합니다.

Microsoft Edge에서는 혼합 콘텐츠 다운로드가 차단되지만 사용자가 원하면 설정을 재정의하고 파일을 다운로드할 수 있습니다. Microsoft edge 버전 85부터는 혼합 콘텐츠 실행 파일 다운로드를 차단할 예정이며 이후 릴리스에서는 다양한 파일 형식을 차단합니다.

> [!NOTE]
> 이 기능 배포는 릴리스 일정 및 사용자 피드백에 따라 변경될 수 있습니다.

<!-- The schedule of the block for different filetypes is to be determined and may be impacted by usage data and user feedback. -->

다운로드 선반의 차단 경고 메시지는 다음 스크린샷의 예와 같습니다.

 ![다운로드 선반의 혼합 콘텐츠 경고](./media/edge-learnmore-mixed-content-downloads/edge-mixed-content-download-tray-warning.png)

다운로드 페이지의 차단 경고는 다음 스크린 샷의 예와 같습니다.

 ![혼합 콘텐츠 재정의 여부 확인 메시지](./media/edge-learnmore-mixed-content-downloads/edge-mixed-content-download-page-warning.png)

사용자가 계속 다운로드하기로 결정하면 해당 작업을 확인하는 메시지가 표시됩니다. 이 확인 메시지의 예가 다음 스크린샷에 나와 있습니다.

 ![Internet Explorer 모드 선택](./media/edge-learnmore-mixed-content-downloads/edge-mixed-content-download-override.png)

## <a name="supporting-policies"></a>지원 정책

특정 웹 사이트로부터 혼합 콘텐츠가 차단되지 않도록 제외하려는 기업에서는 [InsecureContentAllowedForUrls](./microsoft-edge-policies.md#insecurecontentallowedforurls) 정책을 사용해 다운로드 가능하게 만듭니다.

## <a name="content-license"></a>콘텐츠 라이선스

> [!NOTE]
> 이 페이지의 일부는 Chromium.org에서 생성 및 공유하고 [Creative Commons Attribution 4.0 국제 라이선스](http://creativecommons.org/licenses/by/4.0/)에 규정된 조건에 따라 사용되는 작업을 기반으로 합니다. 원래 페이지는 [여기](https://developers.google.com/web/fundamentals/security/prevent-mixed-content/what-is-mixed-content)에서 찾을 수 있습니다.
  
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />이 작업은 <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 국제 라이선스</a>에서 사용이 허가되었습니다.

## <a name="see-also"></a>참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
