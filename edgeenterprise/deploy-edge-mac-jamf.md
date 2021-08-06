---
title: Jamf를 사용하여 macOS용 Microsoft Edge 배포 자동화
ms.author: kvice
author: dan-wesley
manager: laurawi
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Jamf를 사용하여 macOS용 Microsoft Edge 배포를 자동화하는 방법입니다.
ms.openlocfilehash: ab860bf90aa2472dd3a0437dfc98261421c8b5467d8e2f5cb28d511f5b7b0d51
ms.sourcegitcommit: d44c0997ffe40d67421312ed96e7766da947eaa0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "11726325"
---
# <a name="deploy-to-macos-with-jamf"></a>Jamf로 macOS에 배포

이 문서에서는 Jamf를 사용하여 macOS용 Microsoft Edge를 배포하는 방법을 설명합니다.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.

## <a name="prerequisites"></a>필수 구성 요소

Microsoft Edge를 배포하기 전에 다음 필수 구성 요소를 충족하는지 확인합니다.

- Microsoft Edge 설치 파일인 **MicrosoftEdgeDev-\<version\>.pkg**는 네트워크에서 액세스할 수 있는 위치에 있습니다. [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)에서 Microsoft Edge 엔터프라이즈 설치 파일을 다운로드할 수 있습니다.
- 설치 파일을 만들고 컴퓨터에 배포하는 데 필요한 액세스 수준 및 권한이 있는 Jamf 클라우드 계정이 있어야 합니다.

## <a name="to-deploy-microsoft-edge-using-jamf"></a>Jamf를 사용하여 Microsoft Edge를 배포하려면

1. Jamf에 로그인하고 **모든 설정**으로 이동합니다.

    ![모든 설정 열기](./media/mac-deploy/jamf-dash-main-open-settings.png)

2. **모든 설정**에서 **컴퓨터 관리**를 클릭합니다.

    ![컴퓨터 관리 선택](./media/mac-deploy/jamf-all-settings-computer-mgmt.png)

3. **컴퓨터 관리**에서 **패키지**를 클릭합니다.

    ![패키지 선택](./media/mac-deploy/jamf-all-settings-computer-mgmt-pkgs.png)

4. **패키지** 페이지에서 **+ 새로 만들기**를 클릭하여 새 패키지를 추가합니다.

    ![새로 만들기를 선택하여 새 패키지 추가](./media/mac-deploy/jamf-all-settings-computer-mgmt-new-pkg.png)

5. **새 패키지** 페이지에서 패키지에 대한 세부 정보를 입력한 다음 **저장**을 클릭합니다. (예: 표시 이름, 정보 또는 메모)

    ![저장을 선택하여 패키지 정보 저장](./media/mac-deploy/jamf-all-settings-computer-mgmt-save-pkg-info.png)

6. 메뉴 모음에서 **컴퓨터**를 선택한 다음 탐색 모음에서 **정책**을 선택합니다.

7. **+ 새로 만들기**를 선택하여 **새 정책** 창을 표시합니다.

    ![새로 만들기를 선택하여 새 정책 만들기](./media/mac-deploy/jamf-all-settings-computer-new-policy.png)

8. **옵션** 탭에서 **일반**을 선택합니다.

    - **표시 이름**에 정책의 표시 이름을 입력합니다.
    - **트리거**에서 정책을 트리거할 이벤트를 선택합니다. (다음 예제에서는 이벤트가 시작입니다.)

    ![배포 정보 입력](./media/mac-deploy/jamf-all-settings-computer-cfg-policy.png)

9. **옵션** 탭에서 **패키지**를 클릭합니다.

10. **패키지 구성** 팝업에서 **구성**을 클릭합니다.

    ![패키지 구성](./media/mac-deploy/jamf-all-settings-computer-policy-pkg-configure.png)

11. 추가한 패키지는 **패키지** 창에 표시됩니다. **추가**를 클릭합니다. 이 예제의 경우 다음 스크린샷에서 "MicrosoftEdgeBeta"가 패키지입니다.

    ![패키지 추가](./media/mac-deploy/jamf-all-settings-computer-policy-pkg-add-beta.png)

12. **새 정책** 페이지에서 드롭다운 목록을 사용하여 **배포 지점**과 정책에 수행할 **작업**을 선택합니다. **저장**을 클릭합니다. 다음 스크린샷에서는 "각 컴퓨터의 기본 배포 지점"과 "설치"를 예로 사용합니다.

    ![배포 지점 및 작업 선택](./media/mac-deploy/jamf-all-settings-computer-mgmt-pkg-cfg-distro.png)

13. **새 정책** 페이지에서 **범위** 탭을 선택합니다. 컴퓨터 또는 사용자를 기반으로 배포 범위를 관리할 수 있습니다. 이 예제의 경우 **대상 컴퓨터** 드롭다운 목록에서 **모든 컴퓨터**를 선택한 다음 **저장**을 클릭합니다.

    ![배포 범위 선택](./media/mac-deploy/jamf-all-settings-computer-mgmt-add-target.png)

14. 이제 Microsoft Edge 배포 정책을 검토할 수 있습니다. 배포 옵션이 요구 사항에 맞으면 **완료**를 클릭합니다.

    ![완료 클릭](./media/mac-deploy/jamf-all-settings-computer-mgmt-finish-add-deployment.png)

    > [!NOTE]
    > 언제든지 배포 정책으로 돌아와서 설정을 변경할 수 있습니다.

축하합니다! macOS용 Microsoft Edge 배포를 위한 Jamf 구성을 완료했습니다. 정의한 트리거 조건이 참이면 패키지가 지정한 컴퓨터에 배포됩니다.

## <a name="see-also"></a>기타 참조

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [Jamf.com](https://www.jamf.com/)
- [Microsoft Intune과 Jamf 통합](/intune/conditional-access-integrate-jamf)