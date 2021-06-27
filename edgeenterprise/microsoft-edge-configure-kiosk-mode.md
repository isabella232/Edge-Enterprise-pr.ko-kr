---
title: Microsoft Edge 키오스크 모드 구성
ms.author: aguta
author: aguta
manager: srugh
ms.date: 04/26/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 키오스크 모드 기능 및 Microsoft Edge 키오스크 모드 옵션을 구성하는 방법에 대해 자세히 알아보세요.
ms.openlocfilehash: 20cb32c0cd27ad6d7437ed8ae0440560f3ed71b2
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2021
ms.locfileid: "11617858"
---
# <a name="configure-microsoft-edge-kiosk-mode"></a>Microsoft Edge 키오스크 모드 구성

이 문서에서는 시험할 수 있는 Microsoft Edge 키오스크 모드 옵션을 구성하는 방법을 설명합니다. 또한 대상으로 하는 기능 로드맵도 있습니다.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 87 이상에 적용됩니다.

> [!IMPORTANT]
> [키오스크 모드 기능 사용](#use-kiosk-mode-features)에 제공된 명령줄 인수를 사용하여 Windows 10에서 Microsoft Edge 키오스크 모드 기능을 호출합니다.

## <a name="overview"></a>개요

Microsoft Edge 키오스크 모드는 조직이 고객을 위해 최고의 환경을 만들고 관리하고 최상의 환경을 제공할 수 있도록 브라우저에 대한 두 가지 잠금 환경을 제공합니다. 다음과 같은 잠금 환경을 사용할 수 있습니다.  

- **디지털/대화형 서명 환경** - 특정 사이트를 전체 화면 모드로 표시합니다.
- **공개 검색** 환경 - 제한된 다중 탭 버전의 Microsoft Edge를 실행합니다.

두 가지 환경 모두에서 사용자 데이터를 보호하는 Microsoft Edge InPrivate 세션을 실행합니다.

## <a name="set-up-microsoft-edge-kiosk-mode"></a>Microsoft Edge 키오스크 모드 설정

초기 키오스크 모드 기능 집합은 Microsoft Edge 안정 채널 버전 87에서 테스트할 수 있습니다. Microsoft Edge(공식 안정 채널)에서 최신 [버전을 다운로드할 수 있습니다.](https://www.microsoft.com/edge)

### <a name="kiosk-mode-supported-features"></a>키오스크 모드 지원 기능

다음 표에는 Microsoft Edge 및 Microsoft Edge 레거시에서 키오스크 모드로 지원되는 기능이 나열됩니다. Microsoft Edge의 두 버전에서 이러한 기능이 어떻게 지원되는지를 비교하여 Microsoft Edge로 전환하기 위한 가이드로 이 표를 사용하세요.

|기능|디지털\대화형 서명|공개 검색|Microsoft Edge 버전 (이상에서 사용 가능)|Microsoft Edge 레거시에서 사용 가능|
|-|-|-|-|-|
|InPrivate 탐색|Y|Y|89|Y|
|비활성 상태로 재설정|Y|Y|89|Y|
|[읽기 전용 주소](./microsoft-edge-policies.md#kioskaddressbareditingenabled)(정책) |N|Y |89|N|
|[종료 시 다운로드 삭제](./microsoft-edge-policies.md#kioskdeletedownloadsonexit)(정책)  | Y|Y |89|N|
|F11 차단(전체 화면 입력/종료) | Y | Y |89|Y|
|F12 차단(개발자 도구 시작) | Y | Y |89|Y|
| 다중 탭 지원 | N| Y|89|Y|
|[URL 지원 허용](./microsoft-edge-policies.md#urlallowlist) (정책)|Y|Y|89|N|
|[URL 지원 차단](./microsoft-edge-policies.md#urlblocklist) (정책)|Y|Y|89|N|
|[홈 단추표시](./microsoft-edge-policies.md#showhomebutton) (정책)|N|Y|89|Y|
|[즐겨찾기 관리](./microsoft-edge-policies.md#managedfavorites) (정책)|N|Y|89|Y|
|[프린터](./microsoft-edge-policies.md#printingenabled) 사용(정책)|Y|Y|89|Y|
|[새 탭 페이지 URL 구성](./microsoft-edge-policies.md#newtabpagelocation) (정책)|N|Y|89|Y|
|세션 종료 단추 * | N| Y|89|Y|
|모든 내부 Microsoft Edge URL이 차단되며 *edge://downloads* 및 *edge://print*는 예외입니다. |N|Y|89|Y|
| Ctrl+N 차단(새 창 열기) * | Y | Y |89|Y|
| Ctrl+T 차단(새 탭 열기) |Y | N |89|Y|
|설정 및 추가(...)에는 필요한 옵션만 표시됩니다.  |Y |Y |89|Y|
|브라우저에서 다른 응용 프로그램 실행 제한|Y|Y|90|Y|
|UI 인쇄 설정 잠금|Y|Y|90|Y|
|[새 탭 페이지를 홈 페이지로 설정](./microsoft-edge-policies.md#homepageisnewtabpage)(정책)|N|Y|90|Y|

> [!NOTE]
> "*" 뒤에 오는 기능은 할당된 액세스 단일 앱 시나리오에서만 사용할 수 있습니다.

## <a name="use-kiosk-mode-features"></a>키오스크 모드 기능 사용

디지털/대화형 간판 및 공개 검색에 대한 다음 Windows 10 명령줄 옵션을 사용하여 Microsoft Edge 키오스크 모드 기능을 호출할 수 있습니다.

### <a name="kiosk-mode-digitalinteractive-signage"></a>키오스크 모드 디지털/대화형 간판
 
```
msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen
```

### <a name="kiosk-mode-public-browsing"></a>키오스크 모드 공개 검색

```
msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing
```

### <a name="additional-command-line-options"></a>추가 명령줄 옵션

- **--no-first-run**: 첫 번째 Microsoft Edge 실행 환경을 사용하지 않도록 설정합니다.

   ```
  msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen --no-first-run
  ```

  ```
  msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing --no-first-run
  ```

- **--kiosk-idle-timeout-minutes=**: Microsoft Edge 키오스크 모드가 사용자 세션을 다시 설정하기 전에 마지막 사용자 활동에서 시간을 분 단위로 변경합니다. 다음 예제의 "값"을 분 수로 바꿉니다.

   ```
   --kiosk-idle-timeout-minutes=value
   ``` 
   다음 "값"이 지원됩니다.

     - 기본값(분)
       - 전체 화면 - 0(꺼짐)
       - 공개 탐색 - 5분
    - 허용되는 값
      - 0 - 타이머가 꺼집니다.
      - 1~1440분 동안 유휴 타이머에서 재설정


    ```
    msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen --kiosk-idle-timeout-minutes=1
   ```

   ```
   msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing --kiosk-idle-timeout-minutes=1
   ```

## <a name="support-policies-for-kiosk-mode"></a>키오스크 모드에 대한 지원 정책

다음 표에 나열된 Microsoft Edge 정책을 사용하여 구성한 Microsoft Edge 키오스크 모드 유형에 대한 키오스크 환경을 개선합니다. 이러한 정책에 대한 자세한 내용은 [Microsoft Edge - 브라우저 정책 참조를 참조하세요.](./microsoft-edge-policies.md)

> [!NOTE]
> 정책 구성은 다음 표에 나열된 정책으로 제한되지는 않습니다. 그러나 키오스크 모드 기능에 부정적인 영향을 주지 않도록 추가 정책을 테스트해야 합니다.

|그룹 정책|디지털\대화형 간판|공개 검색 단일 앱|
|--|--|--|
|[인쇄](./microsoft-edge-policies.md#printing-policies) | Y|Y |
|[HomePageLocation](./microsoft-edge-policies.md#homepagelocation) |N | Y|
|[ShowHomeButton](./microsoft-edge-policies.md#showhomebutton) |N | Y|
|[NewTabPageLocation](./microsoft-edge-policies.md#newtabpagelocation) |N |Y |
|[FavoritesBarEnabled](./microsoft-edge-policies.md#favoritesbarenabled) |N |Y |
|[URLAllowlist](./microsoft-edge-policies.md#urlallowlist) |Y |Y |
|[URLBlocklist](./microsoft-edge-policies.md#urlblocklist) |Y | Y|
|[ManagedSearchEngines](./microsoft-edge-policies.md#managedsearchengines) |N | Y|
|[UserFeedbackAllowed](./microsoft-edge-policies.md#userfeedbackallowed) |N | Y|
|[VerticalTabsAllowed](./microsoft-edge-policies.md#verticaltabsallowed) | N|Y |
|[SmartScreen 설정](./microsoft-edge-policies.md#smartscreen-settings-policies) |Y |Y |
|[EdgeCollectionsEnabled](./microsoft-edge-policies.md#edgecollectionsenabled)|Y|Y|

## <a name="microsoft-edge-with-assigned-access"></a>할당된 액세스 권한이 있는 Microsoft Edge

### <a name="single-app-kiosk"></a>단일 앱 키오스크

Microsoft Edge 버전 90 키오스크 모드는 광범위한 기능 목록을 제공합니다. 키오스크 모드 지원 기능 섹션을 참조하세요.
다음 Windows 업데이트를 사용하면 할당된 액세스 단일 앱을 통해 Microsoft Edge를 구성할 수 있습니다.

|운영 체제|버전|업데이트|
|--|--|--|
|Windows 10 | 2004 이상|[KB4601382 이상](https://support.microsoft.com/topic/february-24-2021-kb4601382-os-builds-19041-844-and-19042-844-preview-1a7ed2b4-017d-2644-a1e8-dd6bf14cba76) |
|Windows 10| 1909| [KB4601380 이상](https://support.microsoft.com/topic/february-16-2021-kb4601380-os-build-18363-1411-preview-2e3c38e1-a947-1033-8006-a30f3806da18)|

[Windows 설정](/deployedge/microsoft-edge-configure-kiosk-mode#configure-using-windows-settings) 및 Intune을 통해 Microsoft Edge 키오스크 모드 할당 액세스 단일 앱을 관리할 수 있습니다.

### <a name="multi-app-kiosk"></a>복수 앱 키오스크

Microsoft Edge는 Windows 10에서 [다중 앱이 할당된 액세스](/windows/configuration/lock-down-windows-10-to-specific-apps)로 실행할 수 있으며, 이는 레거시 Microsoft Edge "일반 검색" 키오스크 모드 유형에 해당합니다. 다중 앱이 할당된 액세스로 Microsoft Edge를 구성하기 위해 다중 앱 키오스크를 설정하는 방법에 대한 [지침을 따릅니다.](/windows/configuration/lock-down-windows-10-to-specific-apps) (Microsoft Edge 안정 채널에 대한 AUMID는 **MSEdge**입니다).

### <a name="configure-using-windows-settings"></a>Windows 설정을 사용하여 구성

Windows 설정은 한두 개의 단일 앱 키오스크 장치를 설정하는 가장 간단한 방법입니다. 다음 단계를 사용하여 단일 앱 키오스크 컴퓨터를 설정합니다.

1. 다음의 표는 운영 체제에 대한 최소 시스템 업데이트를 열거합니다.

|운영 체제|버전|업데이트|
|--|--|--|
|Windows 10 | 2004 이상|[KB4601382 이상](https://support.microsoft.com/topic/february-24-2021-kb4601382-os-builds-19041-844-and-19042-844-preview-1a7ed2b4-017d-2644-a1e8-dd6bf14cba76) |
|Windows 10| 1909| [KB4601380 이상](https://support.microsoft.com/topic/february-16-2021-kb4601380-os-build-18363-1411-preview-2e3c38e1-a947-1033-8006-a30f3806da18)|

2. 최신 기능을 테스트하려면 최신 [Microsoft Edge 안정 채널](https://www.microsoft.com/edge/business/download) 버전 89 이상을 다운로드할 수 있습니다.

3. 키오스크 컴퓨터에서 Windows 설정을 열고 검색 필드에 "키오스크"를 입력합니다.  **키오스크 설정(할당된 액세스)** 을 선택하면 다음 스크린샷에서 키오스크를 만들 수 있는 대화 상자를 열 수 있습니다.

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-1-assigned-access.png" alt-text="할당된 액세스 권한을 사용하여 키오스크 설정":::

4. **키오스크 설정**  페이지에서  **시작**을 클릭합니다.

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-2-get-started.png" alt-text="키오스크 - 시작":::

5. 이름을 입력하여 새 키오스크 계정을 만들거나 채워진 드롭다운 목록에서 기존 계정을 선택하고  **다음**을 클릭합니다.

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-3-create-account.png" alt-text="키오스크 모드 - 계정 만들기":::

6. **키오스크 앱 선택** 페이지에서 **Microsoft Edge**를 선택한 후  **다음**을 클릭합니다.

   > [!NOTE]
   > 이는 Microsoft Edge Dev, 베타 및 Stable 채널에만 적용됩니다.

     :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-5c-choose-a-kiosk-app.png" alt-text="키오스크 모드 디스플레이 - 전체 화면 디지털 기호":::

7. 키오스크 모드로 실행할 때 Microsoft Edge가 표시되는 방법에 대해 다음 옵션 중 하나를 선택합니다.

   - 디지털/대화형 간판 설계 - Microsoft Edge를 실행하며 전체 화면 모드로 특정 사이트를 표시합니다.
   - 공용 브라우저 - 제한된 다중 탭 버전의 Microsoft Edge를 실행합니다.

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-5a-digital-sign.png" alt-text="키오스크 사용 방법 - 전체 화면 디지털 기호":::

8.  **다음**을 선택합니다.
9. 키오스크 시작 시 로드할 URL을 입력합니다.

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-6-enter-url.png" alt-text="키오스크 모드 - URL 입력":::

10. 대기 시간에 대한 기본값 5분을 수용하거나 직접 값을 제공합니다.

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-7-enter-idle-time.png" alt-text="키오스크 모드 - 유휴 시간 입력":::

11.  **다음**을 클릭합니다.
12.  **설정** 창을 닫고 선택 내용을 저장한 후 적용합니다.

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode--8-done.png" alt-text="키오스크 모드 - 설정 마침":::

13. 키오스크 장치에서 로그인하고 로컬 키오스크 계정으로 로그인하여 구성의 유효성을 검사합니다.

## <a name="functional-limitations"></a>기능 제한 사항

미리 보기 버전의 키오스크 모드 출시와 함께, 제품을 개선하고 새 기능을 추가하는 작업을 계속 진행하고 있습니다.

현재는 다음 기능을 지원하지 않으므로 해제하는 것이 좋습니다.

- [InPrivateModeAvailability](./microsoft-edge-policies.md#inprivatemodeavailability)
- [IsolateOrigins](./microsoft-edge-policies.md#isolateorigins)
- [ManagedFavorites](./microsoft-edge-policies.md#managedfavorites)
- [EdgeShoppingAssistantEnabled](./microsoft-edge-policies.md#edgeshoppingassistantenabled)
- [EdgeCollectionsEnabled](./microsoft-edge-policies.md#edgecollectionsenabled)
- [UserFeedbackAllowed](./microsoft-edge-policies.md#userfeedbackallowed)
- [DefaultPopupsSetting](./microsoft-edge-policies.md#defaultpopupssetting)
- [StartupBoostEnabled](./microsoft-edge-policies.md#startupboostenabled)
- [InternetExplorerIntegrationLevel](./microsoft-edge-policies.md#internetexplorerintegrationlevel)
- [Extensions](./microsoft-edge-policies.md#extensions-policies)
- [BackgroundModeEnabled](./microsoft-edge-policies.md#backgroundmodeenabled)
- [UserFeedbackAllowed](./microsoft-edge-policies.md#userfeedbackallowed)

## <a name="see-also"></a>참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge 배포 계획](deploy-edge-plan-deployment.md)
- [Windows 데스크톱 버전에서 키오스크 및 디지털 서명 구성](/windows/configuration/kiosk-methods)
- [키오스크 모드 전환 계획](microsoft-edge-kiosk-mode-transition-plan.md)
