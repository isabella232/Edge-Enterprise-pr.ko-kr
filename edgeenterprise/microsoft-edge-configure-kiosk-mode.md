---
title: Microsoft Edge 키오스크 모드 구성
ms.author: aguta
author: aguta
manager: srugh
ms.date: 09/24/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 키오스크 모드 구성
ms.openlocfilehash: 17852cc7c7e4921a0fbef7d09a3f1c3d3cccf49f
ms.sourcegitcommit: b1285b7745eb41b241d706b401f8ce78fa33b227
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2020
ms.locfileid: "11078668"
---
# Microsoft Edge 키오스크 모드 구성

이 문서에서는 시험할 수 있는 Microsoft Edge 키오스크 모드 옵션을 구성하는 방법을 설명합니다. 대상으로 하는 기능 로드맵도 있습니다.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 87 이상에 적용됩니다.

레거시 Microsoft Edge 키오스크 모드(버전 45 이하)에 대한 자세한 내용은 [Microsoft Edge 키오스크 모드 배포](https://aka.ms/edgekioskmode)를 참조하세요.

## 개요

Microsoft Edge 키오스크 모드는 조직이 고객을 위해 최고의 환경을 만들고 관리하고 최상의 환경을 제공할 수 있도록 브라우저에 대한 두 가지 잠금 환경을 제공합니다. 다음과 같은 잠금 환경을 사용할 수 있습니다.  

- 디지털/대화형 간판 설계 환경은 전체 화면 모드에서 특정 사이트를 표시합니다.
- 공개 검색 환경은 Microsoft Edge의 제한된 다중 탭 버전을 실행합니다.

두 가지 환경 모두에서 사용자 데이터를 보호하는 Microsoft Edge InPrivate 세션을 실행합니다.

## Microsoft Edge 키오스크 모드 설정  

Microsoft Edge Canary Channel 버전 87을 사용하여 테스트하는 데 키오스크 모드 기능의 초기 집합을 사용할 수 있습니다. [Microsoft Edge Insider Channels](https://www.microsoftedgeinsider.com/download)에서 Microsoft Edge Canary를 다운로드할 수 있습니다.

### 키오스크 모드 기능

다음과 같은 기능을 사용할 수 있습니다.

- InPrivate 탐색.  세션이 종료되면 브라우저 데이터 및 다운로드를 삭제하여 사용자 데이터를 보호합니다.
- 종료 시 다운로드 삭제를 구성하는 정책
- 특정 기간 동안 비활성 상태 지속된 후 사용자 세션을 다시 설정합니다.
- 초기 잠금 기능 집합입니다. 다음과 같은 함수를 사용할 수 있습니다.

  - 마우스 상황에 맞는 메뉴
  - F12 개발자 도구
  - F11 전체 화면 닫기(전체 화면 모드)
  - *Edge://* 페이지의 초기 집합 차단

> [!NOTE]
> 키오스크 모드가 진화하면서 더 많은 기능을 사용할 수 있습니다.

### 키오스크 모드 기능 사용

다음 Windows 10 명령줄 옵션을 사용하여 Microsoft Edge 키오스크 모드 기능을 호출할 수 있습니다.

- 키오스크 모드 디지털/대화형 간판 설계: `msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen`
- 키오스크 모드 공용 검색: `msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing`

#### 추가 명령줄 옵션

- `--no-first-run` : 첫 번째 Microsoft Edge 실행 환경을 사용하지 않도록 설정합니다.
- `--kiosk-idle-timeout-minutes` : Microsoft Edge 키오스크 모드가 사용자 세션을 다시 설정하기 전에 마지막 사용자 활동에서 시간을 분 단위로 변경합니다. 다음 값이 지원됩니다.

  - 기본값
    - 전체 화면 - 꺼짐
    - 공개 탐색 - 5분
  - 허용되는 값
    - 0 - 타이머가 꺼집니다.
    - 1~1440분 동안 유휴 타이머에서 재설정

## 할당된 액세스 권한을 사용하여 키오스크 모드 설정

할당된 액세스 권한이 있는 Microsoft Edge 키오스크 모드는 현재 최신 [Windows 10 Insider Preview 빌드](https://insider.windows.com/) 버전 20215 이상 및 [Microsoft Edge Dev Channel](https://www.microsoftedgeinsider.com/download) 버전 87.0.644.4 이상에서 테스트할 수 있습니다.

**Windows Insiders 미리 보기를 얻으려면 어떻게 하나요?**

PC에 Windows 10 Insider Preview 빌드를 설치하려면 [Windows 10 Insider Preview 빌드 시작](https://docs.microsoft.com/windows-insider/get-started)에 있는 지침을 따르세요.

### Windows 설정을 사용하여 구성

Windows 설정은 한두 개의 단일 앱 키오스크 장치를 설정하는 가장 간단한 방법입니다. 다음 단계를 사용하여 단일 앱 키오스크 컴퓨터를 설정합니다.

1. 최신 Windows 10 Insider Preview 버전 20215 이상을 설치합니다. [Windows 10 Insider Preview 빌드 시작](https://docs.microsoft.com/windows-insider/get-started)에 있는 지침을 따르세요.
2. [Microsoft Edge Dev 채널](https://www.microsoftedgeinsider.com/download) 87.0.644.4 이상의 최신 버전을 설치합니다.

   > [!IMPORTANT]
   > 장치 수준 설치가 필수이므로 Canary 채널이 아닌 채널은 지원되지 않습니다.

3. 키오스크 컴퓨터에서 Windows 설정을 열고 검색 필드에 "키오스크"를 입력합니다.  **키오스크 설정(할당된 액세스)** 을 선택하면 다음 스크린샷에서 키오스크를 만들 수 있는 대화 상자를 열 수 있습니다.

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-1-assigned-access.png" alt-text="할당된 액세스 권한을 사용하여 키오스크 설정":::

4. **키오스크 설정**  페이지에서  **시작**을 클릭합니다.

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-2-get-started.png" alt-text="할당된 액세스 권한을 사용하여 키오스크 설정":::

5. 이름을 입력하여 새 키오스크 계정을 만들거나 채워진 드롭다운 목록에서 기존 계정을 선택하고  **다음**을 클릭합니다.

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-3-create-account.png" alt-text="할당된 액세스 권한을 사용하여 키오스크 설정":::

6. **키오스크 앱 선택** 페이지에서 **Microsoft Edge**를 선택한 후  **다음**을 클릭합니다.

   > [!NOTE]
   > 이는 Microsoft Edge Dev, 베타 및 Stable 채널에만 적용됩니다.

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-4-pick-app.png" alt-text="할당된 액세스 권한을 사용하여 키오스크 설정":::

7. 키오스크 모드로 실행할 때 Microsoft Edge가 표시되는 방법에 대해 다음 옵션 중 하나를 선택합니다.

   - 디지털/대화형 간판 설계 - Microsoft Edge를 실행하며 전체 화면 모드로 특정 사이트를 표시합니다.
   - 공용 브라우저 - 제한된 다중 탭 버전의 Microsoft Edge를 실행합니다.

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-5a-digital-sign.png" alt-text="할당된 액세스 권한을 사용하여 키오스크 설정":::

8.  **다음**을 선택합니다.
9. 키오스크 시작 시 로드할 URL을 입력합니다.

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-6-enter-url.png" alt-text="할당된 액세스 권한을 사용하여 키오스크 설정":::

10. 대기 시간에 대한 기본값 5분을 수용하거나 직접 값을 제공합니다.

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-7-enter-idle-time.png" alt-text="할당된 액세스 권한을 사용하여 키오스크 설정":::

11.  **다음**을 클릭합니다.
12.  **설정** 창을 닫고 선택 내용을 저장한 후 적용합니다.

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode--8-done.png" alt-text="할당된 액세스 권한을 사용하여 키오스크 설정" 설정 메뉴에서는 필수 옵션(예: 인쇄, 도움말, 피드백, 소리내어 읽기)만 사용할 수 있습니다.
  - 추가 *edge://* 페이지 잠금(예: *edge://settings*)
  - 인쇄 옵션 UI 구성
  - 파일 탐색기를 다운로드 폴더로만 제한합니다.

### 2021년 초

다음과 같은 지원 및 기능이 추가됩니다.

- Windows에서 할당된 액세스 단일 앱을 사용하여 Microsoft Edge 키오스크 모드 출시.
- Microsoft Edge 레거시를 사용 는 패리티에 대한 추가 기능입니다.
- 키오스크 모드 프로필 UX를 사용하여 장치를 구성할 수 있도록 Intune과 통합.

## 참고 항목

- [Windows 데스크톱 버전에서 키오스크 및 디지털 서명 구성](https://docs.microsoft.com/windows/configuration/kiosk-methods)
- [레거시 Microsoft Edge 키오스크 모드 배포](https://aka.ms/edgekioskmode)
- [Microsoft Edge 배포 계획](deploy-edge-plan-deployment.md)
- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)