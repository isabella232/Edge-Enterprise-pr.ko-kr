---
title: Microsoft Intune을 사용하여 Windows용 Microsoft Edge 정책 설정 구성
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Intune을 사용하여 Windows용 Microsoft Edge 정책 설정을 구성합니다.
ms.openlocfilehash: 63eb29018bf4ec9c5a32d11b215f422e150383c9
ms.sourcegitcommit: e811be46e3236534c5fa17c728ffc1005c5cc295
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2021
ms.locfileid: "11907262"
---
# <a name="configure-microsoft-edge-policy-settings-with-microsoft-intune"></a>Microsoft Intune을 사용하여 Microsoft Edge 정책 설정 구성

이 문서에서는 Microsoft Intune을 사용하여 Windows 10용 Microsoft Edge 정책 설정을 구성하는 방법을 설명합니다.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.

Microsoft Intune에 장치 구성 프로필을 추가하여 Microsoft Edge 정책 및 설정을 구성할 수 있습니다. Intune을 사용하여 정책을 관리하고 적용하는 것은 Active Directory 그룹 정책을 사용하거나 사용자 장치에서 로컬 GPO(그룹 정책 개체) 설정을 구성하는 것과 같습니다.

Microsoft Intune을 사용하여 Microsoft Edge 정책을 관리하는 방법에 대한 자세한 내용을 보려면 [Microsoft Intune과 Microsoft Edge를 사용하여 웹 액세스 관리](/intune/manage-microsoft-edge)를 읽을 수 있지만, 연결된 문서는 Microsoft Edge 45 이전 버전에만 해당하므로 Microsoft Edge 엔터프라이즈 버전 77 이상에 적용되지 않는 정보와 참조를 포함할 수 있습니다.

> [!TIP]
> Microsoft Intune을 사용하여 macOS에서 Microsoft Edge를 구성하는 방법에 대한 자세한 내용은 [macOS용 구성](configure-microsoft-edge-on-mac.md)을 참조하세요.

## <a name="create-a-profile-to-manage-settings-in-microsoft-edge-for-windows-10"></a>Windows 10용 Microsoft Edge 설정을 관리하는 프로필 만들기

Microsoft Intune의 관리 템플릿을 사용하면 클라우드를 사용하여 Windows 10 장치에서 Microsoft Edge 그룹 정책을 관리할 수 있습니다. 이 섹션에서는 템플릿을 만들어 Microsoft Edge 관련 응용 프로그램 설정을 구성하는 데 도움이 될 수 있습니다. 템플릿을 만들면 장치 구성 프로필이 만들어집니다. 그런 다음 조직에서 이 프로필을 Windows 10 장치에 할당하거나 배포할 수 있습니다.

### <a name="prerequisites"></a>필수 구성 요소

- 다음 최소 시스템 요구 사항을 충족하는 Windows 10:
  - Windows 10, 버전 1909
  - [KB4512941](https://support.microsoft.com/kb/4512941)이 설치된 Windows 10, 버전 1903
  - [KB4512534](https://support.microsoft.com/kb/4512534)이 설치된 Windows 10, 버전 1809
  - [KB4512509](https://support.microsoft.com/kb/4512509)이 설치된 Windows 10, 버전 1803
  - [KB4516071](https://support.microsoft.com/kb/4516071)이 설치된 Windows 10, 버전 1709

### <a name="use-administrative-templates-to-create-a-policy-for-microsoft-edge"></a>관리 템플릿을 사용하여 Microsoft Edge에 대한 정책 만들기

이 절차에서는 Intune에서 기본 제공되는 관리 템플릿(그룹 정책에서 사용자에게 익숙한 경우)을 활용합니다. 이 서식 파일을 사용하여 미리 구성된 목록에서 설정을 선택하여 Microsoft Edge에 대한 정책을 만들 수 있습니다.

1. [Microsoft 끝점 관리자](https://endpoint.microsoft.com/) 포털에 로그인합니다.
2. 왼쪽 탐색 창에서 **장치**를 선택합니다.
3. **장치에서** | **개요**에서 **구성 프로필**(정책 제목 아래)를 선택합니다.
4. 위쪽 명령 모음에서 **프로필 만들기**를 선택합니다.
5. **플랫폼** 아래의 드롭다운 목록에서 **Windows 10 이상**을 선택합니다.
6. 프로필 유형 아래의 드롭다운 **목록에서**템플릿 **을 선택합니다.**
7. 템플릿 **이름에서**관리 템플릿을 **선택한** 다음 만들기 **단추를** 클릭합니다. 다음 스크린샷은 플랫폼 및 프로필 유형을 선택할 수 있는 드롭다운 목록을 보여 줍니다.

    ![플랫폼 및 프로필 유형 선택](./media/configure-edge-with-intune/create-profile-platform.png)

7. **기본** 탭에서 Microsoft Edge 정책과 같이 설명 **이름**을 입력합니다. 원하는 경우 정책에 대한 **설명**을 입력합니다.
다음 스크린샷은 **기본** 탭의 모양을 보여 주며 메뉴 표시줄에는 프로필을 만들기 위한 다음 단계(회색으로 표시된 탭)가 표시됩니다.

   ![이름 및 설명 입력](./media/configure-edge-with-intune/create-profile-basics-tab.png)

8. **다음**을 선택합니다.
9. **구성 설정** 탭에서, 다음 위치 중 하나에서 Microsoft Edge 폴더를 선택합니다.

   - 컴퓨터 구성 폴더 아래
   - 사용자 구성 폴더 아래.

   Microsoft Edge에 사용 가능한 설정이 오른쪽 창에 표시됩니다. 예를 들어, *컴퓨터 구성/Microsoft Edge/다운로드 제한 허용*이 다음 스크린샷에 나와 있습니다.

   ![구성 설정 탭](./media/configure-edge-with-intune/create-profile-configuration-settings-tab.png)

   > [!NOTE]
   > Microsoft Edge에 사용할 수 있는 모든 설정에 대한 최신 전체 목록을 보려면 [Microsoft Edge – 정책](./microsoft-edge-policies.md) 및 [Microsoft Edge – 업데이트 정책](./microsoft-edge-update-policies.md)을 참조하세요.

10. 검색 필드("검색하여 항목 필터링...")를 사용하여 구성할 특정 설정을 찾습니다. 이 예제에서는 검색 문자열은 "홈 페이지"입니다. 다음 스크린샷은 검색 결과를 보여 줍니다.

    ![검색 결과](./media/configure-edge-with-intune/create-profile-configuration-settings-tab-search.png)

11. 구성할 설정을 찾은 후에는 해당 설정을 선택하여 설정할 수 있는 값을 표시합니다. 다음 스크린샷에서 "홈 페이지 URL 구성"을 예제로 선택했습니다.

    ![홈 페이지 URL 구성 정책](./media/configure-edge-with-intune/create-profile-configuration-settings-tab-edit-pol.png)

12. 이전 스크린샷과 같이, 정책을 사용하도록 설정하고 홈 페이지 URL의 값을 입력합니다.

13. **확인**을 클릭합니다. 다음 스크린샷 예와 같이, 설정 "상태" 열이 "사용"으로 표시됩니다.

    ![설정 상태가 사용 상태입니다.](./media/configure-edge-with-intune/create-profile-configuration-settings-tab-set-enabled.png)

14. **다음** 단추를 클릭합니다.

15. **범위 태그** 탭에서, 원하는 경우 범위 태그를 추가하고, 그렇지 않으면 **다음** 단추를 클릭합니다.

16. **과제** 탭에서 **+ 포함할 그룹 선택**을 클릭하여 해당 장치를 포함하는 Azure AD(Azure Active Directory) 그룹이나 이 정책 설정을 받을 사용자에게 해당 정책을 할당합니다. [Microsoft Intune에서 사용자 및 장치 프로필 할당](/intune/device-profile-assign)에서 프로필을 Azure AD 사용자 또는 장치 그룹에 할당하는 방법에 대한 자세한 내용을 참조하세요.

    ![포함할 그룹 선택](./media/configure-edge-with-intune/create-profile-assignments-tab.png)

17. **다음** 단추를 클릭합니다.

18. **검토 + 만들기** 탭에서 변경 내용의 요약을 검토하여 올바른지 확인한 다음 **만들기** 단추를 클릭합니다.

19. 새로 만든 정책(Microsoft Edge 정책)은 다음 스크린샷에 나와 있습니다.

    ![포함할 그룹 선택](./media/configure-edge-with-intune/create-profile-new-policy-finished.png)

Windows 10 프로필에 대한 자세한 내용은 [Windows 10 템플릿을 사용하여 Microsoft Intune에서 그룹 정책 설정 구성](/intune/administrative-templates-windows)을 참조하세요.

## <a name="see-also"></a>기타 참조

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [Microsoft Intune과 Microsoft Edge를 사용하여 웹 액세스 관리](/intune/manage-microsoft-edge)
- [Windows 10 템플릿을 사용하여 Microsoft Intune에서 그룹 정책 설정 구성](/intune/administrative-templates-windows)
- [Microsoft Intune을 사용하여 Microsoft Edge 배포](/intune/apps/apps-windows-edge/?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json)
