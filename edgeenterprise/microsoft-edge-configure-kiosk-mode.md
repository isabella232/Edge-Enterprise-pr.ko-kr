---
title: Microsoft Edge 키오스크 모드 구성
ms.author: aguta
author: aguta
manager: srugh
ms.date: 03/16/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 키오스크 모드 기능 및 Microsoft Edge 키오스크 모드 옵션을 구성하는 방법에 대해 자세히 알아보세요.
ms.openlocfilehash: 516bc004a516b243e52d4128ae47f3ab9d7498df
ms.sourcegitcommit: 6a3787dead062e4a0860adbc570229974dcaee07
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2021
ms.locfileid: "11442488"
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
|[읽기 전용 주소](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskaddressbareditingenabled)(정책) |N|Y |89|N|
|[종료 시 다운로드 삭제](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskdeletedownloadsonexit)(정책)  | Y|Y |89|N|
|F11 차단(전체 화면 입력/종료) | Y | Y | 89 |Y|
|F12 차단(개발자 도구 시작) | Y | Y | 89 |Y|
| 다중 탭 지원 | N| Y| 89|Y|
|[URL 지원 허용](https://docs.microsoft.com/deployedge/microsoft-edge-policies#urlallowlist) (정책)|Y|Y|89|N|
|[URL 지원 차단](https://docs.microsoft.com/deployedge/microsoft-edge-policies#urlblocklist) (정책)|Y|Y|89|N|
|[홈 단추표시](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#showhomebutton) (정책)|N|Y|89|Y|
|[즐겨찾기 관리](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#managedfavorites) (정책)|N|Y|89|Y|
|[프린터](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printingenabled) 사용(정책)|Y|Y|89|Y|
|[새 탭 페이지 URL 구성](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#newtabpagelocation) (정책)|N|Y||Y|
|세션 종료 단추 * | N| Y| 89|Y|
|모든 내부 Microsoft Edge URL이 차단되며 *edge://downloads* 및 *edge://print*는 예외입니다. |N|Y|89|Y|
| Ctrl+N 차단(새 창 열기) * | Y | Y | 89 |Y|
| Ctrl+T 차단(새 탭 열기) |Y | N | 89 |Y|
|설정 및 추가(...)에는 필요한 옵션만 표시됩니다.  |Y |Y |89 |Y|
|브라우저에서 다른 응용 프로그램 실행 제한|Y|Y|90/91|Y|
|UI 인쇄 설정 잠금|Y|Y|90/91|Y|
|[새 탭 페이지를 홈 페이지로 설정](https://docs.microsoft.com/deployedge/microsoft-edge-policies#homepageisnewtabpage)(정책)|-|-|TBD|Y|

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

다음 표에 나열된 Microsoft Edge 정책을 사용하여 구성한 Microsoft Edge 키오스크 모드 유형에 대한 키오스크 환경을 개선합니다. 이러한 정책에 대한 자세한 내용은 [Microsoft Edge - 브라우저 정책 참조를 참조하세요.](https://docs.microsoft.com/deployedge/microsoft-edge-policies)

> [!NOTE]
> 정책 구성은 다음 표에 나열된 정책으로 제한되지는 않습니다. 그러나 키오스크 모드 기능에 부정적인 영향을 주지 않도록 추가 정책을 테스트해야 합니다.

|그룹 정책|디지털\대화형 간판|공개 검색 단일 앱|
|--|--|--|
|[인쇄](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printing-policies) | Y|Y |
|[HomePageLocation](https://docs.microsoft.com/deployedge/microsoft-edge-policies#homepagelocation) |N | Y|
|[ShowHomeButton](https://docs.microsoft.com/deployedge/microsoft-edge-policies#showhomebutton) |N | Y|
|[NewTabPageLocation](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagelocation) |N |Y |
|[FavoritesBarEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#favoritesbarenabled) |N |Y |
|[URLAllowlist](https://docs.microsoft.com/deployedge/microsoft-edge-policies#urlallowlist) |Y |Y |
|[URLBlocklist](https://docs.microsoft.com/deployedge/microsoft-edge-policies#urlblocklist) |Y | Y|
|[ManagedSearchEngines](https://docs.microsoft.com/deployedge/microsoft-edge-policies#managedsearchengines) |N | Y|
|[UserFeedbackAllowed](https://docs.microsoft.com/deployedge/microsoft-edge-policies#userfeedbackallowed) |N | Y|
|[VerticalTabsAllowed](https://docs.microsoft.com/deployedge/microsoft-edge-policies#verticaltabsallowed) | N|Y |
|[SmartScreen 설정](https://docs.microsoft.com/deployedge/microsoft-edge-policies#smartscreen-settings-policies) |Y |Y |
|[EdgeCollectionsEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#edgecollectionsenabled)|Y|Y|

## <a name="microsoft-edge-with-assigned-access"></a>할당된 액세스 권한이 있는 Microsoft Edge

### <a name="single-app-kiosk"></a>단일 앱 키오스크

Microsoft Edge는 현재 디지털/대화형 간판 및 공개 검색과 같은 잠금 환경을 통해 단일 앱이 할당된 액세스에 대해 동일한 Microsoft Edge 레거시 키오스크 모드 유형의 하위 집합을 지원하고 있습니다.  

할당된 액세스 단일 앱이 있는 Microsoft Edge 키오스크 모드는 현재 최신 [Windows 10 Insider Preview 빌드](https://insider.windows.com/), 버전 20215 이상 및  [Microsoft Edge Beta 채널](https://www.microsoftedgeinsider.com/download) 버전 89 이상에서 테스트할 수 있습니다.

**Windows Insiders 미리 보기를 얻으려면 어떻게 하나요?**

PC에 Windows 10 Insider Preview 빌드를 설치하려면  [Windows 10 Insider Preview 빌드 시작](https://docs.microsoft.com/windows-insider/get-started)에 있는 지침을 따르세요.

### <a name="multi-app-kiosk"></a>복수 앱 키오스크

Microsoft Edge는 Windows 10에서 [다중 앱이 할당된 액세스](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps)로 실행할 수 있으며, 이는 레거시 Microsoft Edge "일반 검색" 키오스크 모드 유형에 해당합니다. 다중 앱이 할당된 액세스로 Microsoft Edge를 구성하기 위해 다중 앱 키오스크를 설정하는 방법에 대한 [지침을 따릅니다.](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps) (Microsoft Edge 안정 채널에 대한 AUMID는 **MSEdge**입니다).

다중 앱이 할당된 액세스 권한이 있는 Microsoft Edge를 사용하는 경우 Microsoft Edge 브라우저 정책을 사용하여 고유한 요구 사항을 충족하도록 검색 환경을 구성하도록[Microsoft Edge](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-policies) 키오스크를 구성할 수 있습니다.

### <a name="configure-using-windows-settings"></a>Windows 설정을 사용하여 구성

Windows 설정은 한두 개의 단일 앱 키오스크 장치를 설정하는 가장 간단한 방법입니다. 다음 단계를 사용하여 단일 앱 키오스크 컴퓨터를 설정합니다.

1. 최신 Windows 10 Insider Preview 버전 20215 이상을 설치합니다. [Windows 10 Insider Preview 빌드 시작](https://docs.microsoft.com/windows-insider/get-started)에 있는 지침을 따르세요.
2. 최신 기능을 테스트하기 위해 최신 [Microsoft Edge Beta 채널](https://www.microsoftedgeinsider.com/download) 버전 89 이상을 다운로드할 수 있습니다.
3. 키오스크 컴퓨터에서 Windows 설정을 열고 검색 필드에 "키오스크"를 입력합니다.  **키오스크 설정(할당된 액세스)** 을 선택하면 다음 스크린샷에서 키오스크를 만들 수 있는 대화 상자를 열 수 있습니다.

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-1-assigned-access.png" alt-text="할당된 액세스 권한을 사용하여 키오스크 설정":::

4. **키오스크 설정**  페이지에서  **시작**을 클릭합니다.

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-2-get-started.png" alt-text="키오스크 - 시작":::

5. 이름을 입력하여 새 키오스크 계정을 만들거나 채워진 드롭다운 목록에서 기존 계정을 선택하고  **다음**을 클릭합니다.

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-3-create-account.png" alt-text="키오스크 모드 - 계정 만들기":::

6. **키오스크 앱 선택** 페이지에서 **Microsoft Edge**를 선택한 후  **다음**을 클릭합니다.

   > [!NOTE]
   > 이는 Microsoft Edge Dev, 베타 및 Stable 채널에만 적용됩니다.

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-4-pick-app.png" alt-text="키오스크 모드 - 앱 선택":::

7. 키오스크 모드로 실행할 때 Microsoft Edge가 표시되는 방법에 대해 다음 옵션 중 하나를 선택합니다.

   - 디지털/대화형 간판 설계 - Microsoft Edge를 실행하며 전체 화면 모드로 특정 사이트를 표시합니다.
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

13. 키오스크 장치에서 로그인하고 로컬 키오스크 계정으로 로그인하여 구성의 유효성을 검사합니다.

## <a name="functional-limitations"></a>기능 제한 사항

미리 보기 버전의 키오스크 모드 출시와 함께, 제품을 개선하고 새 기능을 추가하는 작업을 계속 진행하고 있습니다.

현재는 다음 기능을 지원하지 않으므로 해제하는 것이 좋습니다.

- [InPrivateModeAvailability](https://docs.microsoft.com/deployedge/microsoft-edge-policies#inprivatemodeavailability)
- [IsolateOrigins](https://docs.microsoft.com/deployedge/microsoft-edge-policies#isolateorigins)
- [ManagedFavorites](https://docs.microsoft.com/deployedge/microsoft-edge-policies#managedfavorites)
- [EdgeShoppingAssistantEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#edgeshoppingassistantenabled)
- [EdgeCollectionsEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#edgecollectionsenabled)
- [UserFeedbackAllowed](https://docs.microsoft.com/deployedge/microsoft-edge-policies#userfeedbackallowed)
- [DefaultPopupsSetting](https://docs.microsoft.com/deployedge/microsoft-edge-policies#defaultpopupssetting)
- [StartupBoostEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startupboostenabled)
- [InternetExplorerIntegrationLevel](https://docs.microsoft.com/deployedge/microsoft-edge-policies#internetexplorerintegrationlevel)
- [Extensions](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensions-policies)
- [BackgroundModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#backgroundmodeenabled)
- [UserFeedbackAllowed](https://docs.microsoft.com/deployedge/microsoft-edge-policies#userfeedbackallowed)

## <a name="roadmap"></a>로드맵

### <a name="in-early-2021"></a>2021년 초

다음과 같은 지원 및 기능이 추가됩니다.

- Windows 10 1909 이상에서 할당된 액세스 단일 앱이 있는 Microsoft Edge 키오스크 모드의 일반 가용성
- Microsoft Edge 레거시를 사용 는 패리티에 대한 추가 기능입니다.
- 키오스크 모드 프로필 UX를 사용하여 장치를 구성할 수 있도록 Intune과 통합합니다.
- 브라우저에서 다른 응용 프로그램 실행을 제한합니다.
- UI 인쇄 설정 잠금

## <a name="see-also"></a>참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge 배포 계획](deploy-edge-plan-deployment.md)
- [Windows 데스크톱 버전에서 키오스크 및 디지털 서명 구성](https://docs.microsoft.com/windows/configuration/kiosk-methods)
- [키오스크 모드 전환 계획](microsoft-edge-kiosk-mode-transition-plan.md)
