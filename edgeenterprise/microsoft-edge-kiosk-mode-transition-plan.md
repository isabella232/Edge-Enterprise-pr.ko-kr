---
title: 키오스크 모드 전환 계획
ms.author: aguta
author: aguta
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 키오스크 모드 전환 계획
ms.openlocfilehash: 31a127de166e5bff53ad73951b0fd0f29eed094cae5026bf57995ccebcd5784c
ms.sourcegitcommit: d44c0997ffe40d67421312ed96e7766da947eaa0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "11726751"
---
# <a name="plan-your-kiosk-mode-transition"></a>키오스크 모드 전환 계획

이 문서에서는 Microsoft Edge 레거시에서 Microsoft Edge로 키오스크를 전환하는 방법에 대한 지침을 제공합니다.  

> [!NOTE]
> 이 문서는 Microsoft Edge Stable, Beta 및 Dev Channels 버전 87 이상에 적용됩니다.

> [!IMPORTANT]
> 2021년 3월 9일에 Microsoft Edge 레거시에 대한 지원이 종료되면 4월 Windows 업데이트의 일환으로 제거되고 Chromium의 Microsoft Edge로 대체됩니다. 자세한 내용은 이 블로그 [게시물을 참조하세요.](https://aka.ms/EdgeLegacyEOS) 브라우저 기반 키오스크 시나리오를 계속 사용하려면 Chromium에 Microsoft Edge를 설치하고 4월 Windows 업데이트가 장치에 릴리스되기 전에 키오스크 모드를 설정해야 합니다.

## <a name="kiosk-setup-steps"></a>키오스크 설치 단계

다음 단계를 가이드로 사용하여 Microsoft Edge에서 키오스크를 설정할 수 있습니다.

**1단계: 출시 예정인 키오스크 모드 기능에 대한 요구 사항을 평가합니다.** 다음 표에는 Chromium의 Microsoft Edge 및 Microsoft Edge 레거시에서 키오스크 모드로 지원되는 기능이 나열되어 있습니다. 이 표를 참조하여 두 Microsoft Edge 릴리스에서 이러한 기능이 어떻게 지원되는지 비교하여 Microsoft Edge로 전환할 수 있습니다.

|기능|디지털\대화형 서명|공개 검색|Microsoft Edge 버전 (이상에서 사용 가능)|Microsoft Edge 레거시에서 사용 가능|
|-|-|-|-|-|
|InPrivate 탐색|Y|Y|89|Y|
|비활성 상태로 재설정|Y|Y|89|Y|
|[읽기 전용 주소](./microsoft-edge-policies.md#kioskaddressbareditingenabled)(정책) |N|Y |89|N|
|[종료 시 다운로드 삭제](./microsoft-edge-policies.md#kioskdeletedownloadsonexit)(정책)  | Y|Y |89|N|
|F11 차단(전체 화면 입력/종료) | Y | Y | 89 |Y|
|F12 차단(개발자 도구 시작) | Y | Y | 89 |Y|
| 다중 탭 지원 | N| Y| 89|Y|
|[URL 지원 허용](./microsoft-edge-policies.md#urlallowlist) (정책)|Y|Y|89|N|
|[URL 지원 차단](./microsoft-edge-policies.md#urlblocklist) (정책)|Y|Y|89|N|
|[홈 단추표시](./microsoft-edge-policies.md#showhomebutton) (정책)|N|Y|89|Y|
|[즐겨찾기 관리](./microsoft-edge-policies.md#managedfavorites) (정책)|N|Y|89|Y|
|[프린터](./microsoft-edge-policies.md#printingenabled) 사용(정책)|Y|Y|89|Y|
|[새 탭 페이지 URL 구성](./microsoft-edge-policies.md#newtabpagelocation) (정책)|N|Y|89|Y|
|세션 종료 단추 | N| Y| 89|Y|
|모든 내부 Microsoft Edge URL이 차단되며 *edge://downloads* 및 *edge://print*는 예외입니다. |N|Y|89|Y|
| Ctrl+N 차단(새 창 열기) | Y | Y | 89 |Y|
| Ctrl+T 차단(새 탭 열기) |Y | Y | 89 |Y|
|설정 및 추가(...)에는 필요한 옵션만 표시됩니다.  |Y |Y |89 |Y|
|브라우저에서 다른 응용 프로그램 실행 제한|Y|Y|90|Y|
|UI 인쇄 설정 잠금|Y|Y|90|Y|
|[새 탭 페이지를 홈 페이지로 설정](./microsoft-edge-policies.md#homepageisnewtabpage)(정책)|N|Y|90|Y|

> [!NOTE]
> Microsoft Edge 릴리스 일정에 대한 자세한 내용은 Microsoft Edge 릴리스 [일정을 참조하세요.](microsoft-edge-release-schedule.md)

**2단계: Microsoft Edge에서 새 키오스크를 테스트합니다.** Microsoft Edge에서 키오스크 모드 설정을 테스트하는 것이 좋습니다. 키오스크 모드를 테스트하는 빠르고 쉬운 방법은 다음에 설명된 Windows 설정을 사용하여 할당된 액세스 단일 앱을 구성하는 것입니다.

1. 다음의 표는 운영 체제에 대한 최소 시스템 업데이트를 열거합니다.

|운영 체제|버전|업데이트|
|--|--|--|
|Windows 10 | 2004 이상|[KB4601382 이상](https://support.microsoft.com/topic/february-24-2021-kb4601382-os-builds-19041-844-and-19042-844-preview-1a7ed2b4-017d-2644-a1e8-dd6bf14cba76) |
|Windows 10| 1909| [KB4601380 이상](https://support.microsoft.com/topic/february-16-2021-kb4601380-os-build-18363-1411-preview-2e3c38e1-a947-1033-8006-a30f3806da18)|

2. 최신 기능을 테스트하려면 최신 [Microsoft Edge 안정 채널](https://www.microsoftedgeinsider.com/download) 버전 89 이상을 다운로드할 수 있습니다.

   > [!IMPORTANT]
   > 장치 수준의 설치가 필요하기 때문에 Canary 채널은 지원되지 않습니다.

3. 키오스크 컴퓨터에서 Windows 설정을 열고 검색 필드에 "키오스크"를 입력합니다.  **키오스크 설정(할당된 액세스)** 을 선택하면 다음 스크린샷에서 키오스크를 만들 수 있는 대화 상자를 열 수 있습니다.

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-1-assigned-access.png" alt-text="할당된 액세스 권한을 사용하여 키오스크 설정":::

4. **키오스크 설정**  페이지에서  **시작**을 클릭합니다.

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-2-get-started.png" alt-text="키오스크 - 시작":::

5. 이름을 입력하여 새 키오스크 계정을 만들거나 채워진 드롭다운 목록에서 기존 계정을 선택하고  **다음**을 클릭합니다.

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-3-create-account.png" alt-text="키오스크 모드 - 계정 만들기":::

6. **키오스크 앱 선택** 페이지에서 **Microsoft Edge**를 선택한 후  **다음**을 클릭합니다.

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-5c-choose-a-kiosk-app.png" alt-text="키오스크 선택 - 전체 화면 디지털 기호":::

7. 키오스크 모드에서 실행 시 Microsoft Edge가 표시하는 방식에 대해 다음 옵션 중 하나를 선택합니다.

   - 디지털/대화형 간판 - Microsoft Edge를 실행하며 전체 화면 모드로 특정 사이트를 표시합니다.
   - 공용 브라우저 - 제한된 다중 탭 버전의 Microsoft Edge를 실행합니다.
 
    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-5a-digital-sign.png" alt-text="키오스크 모드 디스플레이 - 전체 화면 디지털 기호":::

8.  **다음**을 선택합니다.
9. 키오스크 시작 시 로드할 URL을 입력합니다.

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-6-enter-url.png" alt-text="키오스크 모드 - URL 입력":::

10. 대기 시간에 대한 기본값 5분을 수용하거나 직접 값을 제공합니다.

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-7-enter-idle-time.png" alt-text="키오스크 모드 - 유휴 시간 입력":::

11.  **다음**을 클릭합니다.
12.  **설정** 창을 닫고 선택 내용을 저장한 후 적용합니다.

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode--8-done.png" alt-text="키오스크 모드 - 설정 마침":::

13. 키오스크 장치에서 로그아웃하고 로컬 키오스크 계정으로 로그인하여 구성의 유효성을 검사합니다.

**3단계: 전환 계획을 개발합니다.** 테스트 및 조직 요구에 따라, 2021년 3월 9일 Microsoft Edge 레거시에 대한 지원이 종료되기 전에 Chromium의 Microsoft Edge로 전환 계획을 개발하고 Microsoft Edge로 전환하는 것이 좋습니다.

## <a name="additional-scenarios-that-require-you-to-recreate-an-existing-kiosk-mode"></a>기존 키오스크 모드를 다시 설정해야 하는 추가 시나리오

Windows 10 버전 20H2로 업데이트하면 Chromium의 Microsoft Edge가 설치되어 Microsoft Edge 레거시가 숨겨집니다. 이 경우 Chromium의 Microsoft Edge에서 키오스크 모드를 다시 설정해야 합니다.

## <a name="how-to-get-help"></a>도움을 받는 방법

키오스크 모드는 일상적인 비즈니스에서 중요한 부분이 될 수 있으므로 이러한 전환을 최대한 원활하게 수행하고 중단을 방지하는 데 도움을 드리려 합니다. 비즈니스 요구가 Chromium에서 Microsoft Edge로의 전환에 도움이 되는 경우:

- [Microsoft에서](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=a77ee9b7-b6b6-aa08-d7b9-887ebe228207) 지원을 사용할 수 있습니다. 
- 또한 Windows 10 Enterprise 유료 사용자 수가 150명 이상인 고객에게는 [FastTrack 지원](https://www.microsoft.com/fasttrack/microsoft-365/microsoft-edge?rtc=1)을 추가 비용이 없이도 사용할 수도 있습니다.
- 사이트 또는 앱 호환성 문제가 있는 경우 [App Assure](https://www.microsoft.com/en-us/fasttrack/microsoft-365/app-assure)를 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목

- [Microsoft Edge Enterprise 방문 페이지](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge 레거시를 4월의 Windows 10 업데이트 화요일 릴리스로 대체하는 새로운 Microsoft Edge입니다.](https://techcommunity.microsoft.com/t5/microsoft-365-blog/new-microsoft-edge-to-replace-microsoft-edge-legacy-with-april-s/ba-p/2114224)