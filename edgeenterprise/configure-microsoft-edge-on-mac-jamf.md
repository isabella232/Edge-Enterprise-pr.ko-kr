---
title: Jamf를 사용하여 macOS에서 Microsoft Edge 구성
ms.author: brianalt
author: dan-wesley
manager: laurawi
ms.date: 11/30/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Mac 장치에서 Jamf로 Microsoft Edge 정책 설정 구성
ms.openlocfilehash: 1859d9fb1fd3ea8ff6908c41f75df21a8b338769
ms.sourcegitcommit: ed6a5afabf909df87bec48671c4c47bcdfaeb7bc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2020
ms.locfileid: "11194716"
---
# macOS에서 Jamf로 Microsoft Edge 정책 설정 구성

이 문서에서는 Jamf Pro 10.19의 Microsoft Edge 정책 매니페스트 파일을 사용하여 macOS에서 정책 설정을 구성하는 방법에 대해 설명합니다.

속성 목록(.plist) 파일을 사용하여 macOS에서 Microsoft Edge 정책 설정을 구성할 수도 있습니다. 자세한 내용은 [.plist을 사용하여 macOS 구성](configure-microsoft-edge-on-mac.md)을 참조하세요.


## 필수 구성 요소

다음 소프트웨어가 필요합니다.

- Microsoft Edge 안정 채널 81
- 정책 템플릿 파일, 버전 81.0.416.3
- Jamf Pro, 버전 10.19

## Jamf Pro 응용 프로그램 및 사용자 지정 설정 메뉴 정보

Jamf Pro 10.18 이전에는 Office 365 관리에 .plist 파일을 수동으로 작성해야 했습니다. 이것은 강력한 기술 배경이 필요한 시간이 많이 소요되는 워크플로우였습니다. Jamf Pro 10.18은 구성 프로세스를 간소화하여 이러한 장벽을 제거했습니다. 그러나 IT 관리자는 Jamf에서 지정한 특정 응용 프로그램과 기본 설정 도메인에 대해서만 이 새로운 사용자 인터페이스를 사용할 수 있습니다.

Jamf Pro 10.19에서 사용자는 JSON 매니페스트를 "사용자 정의 스키마"로 업로드하여 기본 설정 도메인을 대상으로 할 수 있으며 이 매니페스트에서 그래픽 사용자 인터페이스가 생성됩니다. 생성된 사용자 지정 스키마는 JSON 스키마 사양을 따릅니다.

자세한 내용은 Jamf Pro 관리자 안내서의 [컴퓨터 구성 프로파일](https://jamf.it/computer-configuration-profiles)을 참조하십시오.

## 특정 버전의 Microsoft Edge에 대한 정책 매니페스트를 가져옵니다.

정책 매니페스트를 얻으려면 다음을 수행합니다.

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)로 이동합니다.
- 채널/버전 드롭다운 목록에서 **버전 81 이상을 사용**하는 채널을 선택합니다. _.
- 빌드 드롭다운 목록에서 _ *81 빌드 이상을 선택합니다.* * _
- 정책 파일 얻기를 클릭하여 정책 템플릿 번들을 다운로드합니다.

  > [!NOTE]
  > 현재 정책 템플릿 번들은 CAB 파일로 서명되어 있습니다. macOS에서 파일을 열려면 The Unarchiver와 같은 타사 도구를 사용해야 합니다.

CAB 파일의 압축을 푼 후 ZIP 파일의 압축을 풀고 "mac"최상위 디렉터리로 이동하십시오. "policy_manifest.json"이라는 매니페스트가 이 디렉토리에 있습니다.

이 매니페스트는 빌드 81.0.416.3부터 모든 정책 번들에 게시됩니다. Dev 채널에서 정책을 테스트하려는 경우 각 Dev 릴리스와 관련된 매니페스트를 가져와서 Jamf Pro에서 테스트할 수 있습니다.  

## Jamf Pro의 정책 목록 사용

다음 단계를 사용하여 정책 매니페스트를 Jamf Pro에 업로드한 다음 macOS에 대한 정책 프로필을 생성하십시오.

1. Jamf에 로그인합니다.
2. _*컴퓨터** 탭을 선택합니다.
3. **콘텐츠 관리**에서 **구성 프로파일**을 선택하십시오.
4. **구성 프로파일** 페이지에서 **+New**를 클릭하십시오.

   ![Jamf에서 새로운 프로필 추가](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-configuration-profiles.png)

5. **새 macOS 구성 프로파일**>**옵션**에서 **응용 프로그램 및 사용자 지정 설정**을 선택하십시오.
6. **응용 프로그램 및 사용자 지정 설정** 팝업 창에서 **구성**을 클릭하십시오.

   ![응용 프로그램 및 사용자 지정 설정 구성](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-app-and-custom.png)

7. **응용 프로그램 & 사용자 지정 설정** 섹션에서 다음 스크린샷에 표시된 값을 설정합니다.

   ![프로파일 소스 및 사용자 지정 스키마](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-app-and-custom-schema.png)

   - **만들기 방법**에 대해 **설정 구성**을 선택합니다.
   - **소스**에 대해 **사용자 지정 스키마**를 선택합니다.
   - **기본 설정 도메인**에 대해 도메인 이름을 입력합니다. 이 예제에서는 *com.microsoft.Edge*을 도메인으로 사용합니다.
   - **사용자 지정 스키마**의 경우 "policy_manifest json" 매니페스트 파일의 내용을 붙여넣습니다.
   - **Save**을 클릭합니다.

8. 프로파일을 저장한 후 Jamf는 다음 스크린 샷에 표시된 **일반** 섹션을 표시합니다.

   ![일반 구성 섹션](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-app-and-custom-general-setting.png)

   - 프로파일의 표시 **이름** 및 **설명**을 제공하십시오.
   - **범주**에 대한 기본 설정인 **없음**을 유지하십시오.
   - **배포 방법**의 경우, 옵션은 **자동으로 설치** 또는 **셀프 서비스에서 사용 가능하도록 설정**입니다.
   - **수준**의 경우 옵션은 **사용자 수준** 또는 **컴퓨터 수준**입니다.
   - **Save**을 클릭합니다.

9. 일반 섹션을 저장하면 Jamf는 예제에 대해 설정된 "Microsoft Edge 베타 채널" 구성 프로필을 표시합니다. 다음 스크린샷에서 **편집**을 클릭하여 프로파일 작업을 계속할 수 있거나 완료한 경우 **완료**를 클릭하십시오.

   ![옵션이 있는 새로운 구성 프로필](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-configuration-profiles-beta-channel.png)

   > [!NOTE]
   > 이 프로필을 저장한 후 다른 Jamf 세션에서 편집할 수 있습니다. 예를 들어, 배포 방법을 셀프 서비스에서 사용 가능하도록 변경하기로 결정할 수 있습니다.

   Microsoft Edge 안정 채널에서 후속 편집을 수행하거나 삭제하려면 다음 구성 프로파일 스크린샷에 표시된 프로파일 이름을 선택하십시오.

   ![구성 프로필 목록](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-configuration-profiles-beta-channel-done.png)

새 구성 프로필을 만든 후에는 계속해서 프로필에 대한 **범위**를 구성해야 합니다.

### 범위를 구성하려면

1. **대상**의 경우 다음 최소 설정값을 입력합니다.

   - 대상 컴퓨터. 옵션은 특정 컴퓨터나 모든 컴퓨터입니다.
   - 대상 사용자. 옵션은 특정 사용자나 모든 사용자입니다.
   - **Save**을 클릭합니다.
2. **제한**의 경우 기본 설정인 없음을 유지 합니다. **취소**를 클릭합니다.
3. **제외**의 경우 기본 설정인 없음을 유지 합니다. **취소**를 클릭합니다.

## 참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [Intune을 사용한 macOS용 구성](configure-microsoft-edge-on-mac.md)
- [Windows용 구성](configure-microsoft-edge.md)
- [Intune을 사용한 Windows용 구성](configure-edge-with-intune.md)
