---
title: Internet Explorer 모드에서 페이지 내 탐색 유지
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Internet Explorer 모드에서 페이지 내 탐색 유지
ms.openlocfilehash: f1c40977ba07f0a85bc64aab8e609163f9a68dd2eb7487adff6b6a1fcbd110f2
ms.sourcegitcommit: d44c0997ffe40d67421312ed96e7766da947eaa0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "11724295"
---
# <a name="keep-in-page-navigation-in-internet-explorer-mode"></a>Internet Explorer 모드에서 페이지 내 탐색 유지

이 정책을 임시 솔루션으로 사용하여 IE 모드(Internet Explorer 모드)에서 사이트의 모든 페이지 내 탐색을 IE 모드로 유지하도록 강제할 수 있습니다.

페이지 내 탐색은 현재 페이지의 링크, 스크립트 또는 양식에서 시작됩니다. 이전의 페이지 탐색 시도가 서버측으로 리디렉션될 수도 있습니다. 반대로 사용자는 브라우저 컨트롤을 사용하여 여러 가지 방법으로 현재 페이지와는 독립적인 페이지 내가 아닌 탐색을 시작할 수 있습니다. 예를 들어 주소 표시줄, 뒤로 단추 또는 즐겨찾기 링크를 사용합니다.

>[!NOTE]
>이 문서는 Microsoft Edge 버전 81 이상에 적용됩니다.

## <a name="prerequisites"></a>필수 구성 요소

이 정책에는 다음과 같은 Windows 업데이트가 필요합니다.

- Windows 10 버전 1909 & 1903, Windows Server 버전 1909 & 1903 ([KB4532695](https://support.microsoft.com/help/4532695))
- Windows 10 버전 1809, Windows Server 버전 1809, Windows Server 2019 ([KB4534321](https://support.microsoft.com/help/4534321))
- Windows 10 버전 1803 ([KB4534308](https://support.microsoft.com/help/4534308))
- Windows 10 버전 1709 ([KB4534318](https://support.microsoft.com/help/4534318))


## <a name="about-this-policy"></a>이 정책 정보

이 정책은 IE 모드 사이트에서 사용하는 모든 인증 서버를 식별하고 구성할 시간을 제공합니다. 그러나 이 정책을 통해 일부 사이트는 IE 모드로 렌더링되고 다른 사이트는 Microsoft Edge 모드로 렌더링되는 검색 환경이 일관되지 않을 수 있습니다. 이는 사이트 탐색이 IE 모드 페이지에서 시작되었는지에 따라 다릅니다. 특정 렌더링 엔진에서 열도록 명시적으로 구성되지 않은 사이트는 이 불일치의 영향을 받게 됩니다.

이 정책을 사용하도록 설정하는 경우 모든 인증 서버를 식별하고 이를 사이트 목록에 중립으로 추가한 후에는 정책을 해제하는 것이 좋습니다. 이 작업을 수행하면 최신 사이트가 IE 모드로 절대 실수로 렌더링되는 일이 없습니다.

## <a name="keep-in-page-navigation-in-ie-mode"></a>IE 모드에서 페이지 내 탐색 유지

Internet Explorer 모드에서 자동 또는 모든 페이지 내 탐색을 유지하려면 다음 단계를 따릅니다.

1. 로컬 그룹 정책 편집기를 엽니다.
2. **컴퓨터 구성** > **관리 템플릿** > **Microsoft Edge**를 클릭합니다.
3. **설정**에서 **Internet Explorer 모드 페이지에서 시작할 때 구성되지 않은 사이트에 대한 "페이지 내" 탐색 동작 방법 지정**을 두 번 클릭합니다.

   ![페이지 내 정책 설정](media/edge-learnmore-inpage-nav/learnmore-in-page-nav-settings.png)

4. **사용**을 선택합니다. 

   ![페이지 내 정책 활성화](media/edge-learnmore-inpage-nav/learnmore-in-page-nav-enable.png)

5. 드롭다운 목록에서 다음 옵션 중 하나를 선택합니다.

   - **기본** - Internet Explorer 모드에서 열도록 구성된 사이트만 해당 모드에서 열립니다. Internet Explorer 모드에서 열리도록 구성되지 않은 사이트는 Microsoft Edge로 다시 리디렉션됩니다.
   - **Internet Explorer 모드에서 자동 탐색만 유지** - 구성되지 않은 사이트에 대한 모든 자동 탐색(예: 302 리디렉션)이 Internet Explorer 모드로 유지되는 것을 제외하고 기본 환경을 원할 경우 이 옵션을 사용합니다.
   - 모든 페이지 내 탐색을 Internet Explorer 모드(최소 **_권장)_** - IE 모드로 **로드된** 페이지에서 구성되지 않은 사이트로의 모든 탐색은 Internet Explorer 모드로 유지됩니다.

6. **확인**또는 **적용**을 클릭하여 이 정책 설정을 저장합니다.

## <a name="see-also"></a>참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
