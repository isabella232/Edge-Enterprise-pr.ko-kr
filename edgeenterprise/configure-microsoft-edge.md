---
title: Windows용 Microsoft Edge 구성
ms.author: brianalt
author: kelleyvice-msft
manager: laurawi
ms.date: 10/09/2019
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Windows 장치에서 Microsoft Edge 정책 설정 구성
ms.openlocfilehash: 99aaf002f868ce29e81aa40024fa1de2e83d76e1
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980583"
---
# Windows에서 Microsoft Edge 정책 설정 구성

Windows 장치에서 Microsoft Edge 정책 설정을 구성하려면 다음 정보를 사용합니다.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.

## Windows에서 정책 설정 구성

_GPO(그룹 정책 개체)_ 를 사용하여 모든 Windows 버전에서 Microsoft Edge 및 관리되는 Microsoft Edge 업데이트에 대한 정책 설정을 구성할 수 있습니다. 또한 Microsoft Intune의 장치 관리에 등록된 Microsoft Active Directory 도메인 또는 Windows 10 Pro 및 엔터프라이즈 인스턴스에 가입한 Windows 장치에 대한 레지스트리를 통해 정책을 제공할 수 있습니다. 그룹 정책 개체를 사용하여 Microsoft Edge를 구성하려면 Microsoft Edge에 대한 규칙 및 설정을 추가하는 _관리 템플릿_을 Active Directory 도메인의 그룹 정책 중앙 저장소 또는 개별 컴퓨터의 정책 정의 템플릿 폴더에 설치한 다음 설정하려는 특정 정책을 구성합니다.

도메인 수준에서 정책을 관리하려는 경우 Active Directory 그룹 정책을 사용하여 Microsoft Edge 정책 설정을 구성할 수 있습니다. 이렇게 하면 전역적으로 정책 설정을 관리하거나, 특정 OU에 다양한 정책 설정을 지정하거나, WMI 필터를 사용하여 특정 쿼리에서 반환된 컴퓨터에만 설정을 적용할 수 있습니다. 개별 컴퓨터에서 정책을 구성하려는 경우 대상 컴퓨터에서 로컬 그룹 정책 편집기를 사용하여 로컬 장치에만 영향을 주는 정책 설정을 적용할 수 있습니다.

Microsoft Edge는 _필수_ 및 _권장_ 정책을 모두 지원합니다. 필수 정책은 사용자 기본 설정을 재정의하고 사용자가 변경하지 못하도록 하는 반면, 권장 정책은 사용자가 재정의할 수 있는 기본 설정을 제공합니다. 대부분의 정책은 필수 사항입니다. 하위 집합은 필수 또는 권장입니다. 두 버전의 정책이 모두 설정된 경우에는 필수 설정이 우선합니다.

>[!TIP]
> Microsoft Intune을 사용하여 Microsoft Edge 정책 설정을 구성할 수 있습니다. 자세한 내용은 [Microsoft Intune을 사용하여 Microsoft Edge 구성](configure-edge-with-intune.md)을 참조하세요.

두 개의 Microsoft Edge용 관리 템플릿이 있으며, 둘 다 컴퓨터 또는 Active Directory 도메인 수준에서 적용할 수 있습니다.

- [Microsoft Edge 설정 구성](microsoft-edge-policies.md)을 위한 *msedge.admx*
- [Microsoft Edge 업데이트 관리](microsoft-edge-update-policies.md)를 위한 *msedgeupdate.admx*.

시작하려면 Microsoft Edge 관리 템플릿을 다운로드하여 설치합니다.

### 1. Microsoft Edge 관리 템플릿 다운로드 및 설치

Active Directory에서 Microsoft Edge 정책 설정을 구성하려면 도메인 컨트롤러 또는 RSAT(원격 서버 관리 도구)가 설치된 워크스테이션에서 액세스할 수 있는 네트워크 위치에 파일을 다운로드합니다. 개별 컴퓨터에서 구성하려면 해당 컴퓨터에 파일을 다운로드하기만 하면 됩니다.

관리 템플릿 파일을 적절한 위치에 추가하면 Microsoft Edge 정책 설정을 그룹 정책 편집기에서 즉시 사용할 수 있습니다.

[Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)로 이동하여 Microsoft Edge 정책 템플릿 파일(*MicrosoftEdgePolicyTemplates.cab*)을 다운로드하고 내용을 추출합니다.

#### Active Directory에 관리 템플릿 추가

1. 도메인 컨트롤러 또는 RSAT가 설치된 워크스테이션에서 도메인의 아무 도메인 컨트롤러에서나 **PolicyDefinition** 폴더( _중앙 저장소_라고도 함)로 이동합니다. 이전 버전의 Windows Server의 경우에는 PolicyDefinition 폴더를 만들어야 할 수 있습니다. 자세한 내용은 [Windows에서 그룹 정책 관리 템플릿 중앙 저장소를 만들고 관리하는 방법](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)을 참조하세요.
1. *MicrosoftEdgePolicyTemplates*를 열고 **windows** > **admx**로 이동합니다.
1. *msedge.admx* 파일을 PolicyDefinition 폴더에 복사합니다. (예: %systemroot%\sysvol\domain\policies\PolicyDefinitions)
1. *admx* 폴더에서 적절한 언어 폴더를 엽니다. 예를 들어 미국에서는 **en-US** 폴더를 엽니다.
1. *msedge.adml* 파일을 PolicyDefinition 폴더의 일치하는 언어 폴더에 복사합니다. 폴더가 없으면 새로 만듭니다. (예: %systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US)
1. 도메인에 둘 이상의 도메인 컨트롤러가 있는 경우 다음 도메인 복제 간격에 새 ADMX 파일이 복제됩니다.
1. 파일이 올바로 로드되었는지 확인하려면 Windows 관리 도구에서 **그룹 정책 관리 편집기**를 열고 **컴퓨터 구성** > **정책** > **관리 템플릿** > **Microsoft Edge**를 확장합니다. 아래와 같이 하나 이상의 Microsoft Edge 노드가 표시됩니다.

    ![Microsoft Edge 정책](./media/configure-microsoft-edge/edge-gpo-policies.png)

#### 개별 컴퓨터에 관리 템플릿 추가

1. 대상 컴퓨터에서 *MicrosoftEdgePolicyTemplates*를 열고 **windows** > **admx**로 이동합니다.
2. *msedge.admx* 파일을 정책 정의 템플릿 폴더에 복사합니다. (예: C:\Windows\PolicyDefinitions)
3. *admx* 폴더에서 적절한 언어 폴더를 엽니다. 예를 들어 미국에서는 **en-US** 폴더를 엽니다.
4. *msedge.adml* 파일을 정책 정의 폴더의 일치하는 언어 폴더에 복사합니다. (예: C:\Windows\PolicyDefinitions\en-US)
5. 파일이 올바로 로드되었는지 확인하려면 로컬 그룹 정책 편집기를 직접 열거나(Windows 키 + R을 누르고 gpedit.msc를 입력) MMC를 열고 로컬 그룹 정책 편집기 스냅인을 로드합니다. 오류가 발생하는 경우 일반적으로 파일이 잘못된 위치에 있기 때문입니다.

<!--
To add the administrative template to manage Microsoft Edge updates:

1. Open the *MicrosoftEdgePolicyTemplates* file and go to **windows** > **admx**.
2. Copy the *msedgeupdate.admx* file to your Policy Definition template folder. (Example: C:\Windows\PolicyDefinitions)
3. In the *updatepolicies* folder, open the appropriate language folder. For example, if you’re in Germany, open the **de-DE** folder.
4. Copy the *msedgeupdate.adml* file to the matching language folder in your Policy Definition folder. (Example: C:\Windows\PolicyDefinitions\de-DE)
5. Open MMC and load the Local Group Policy Editor snap-in to confirm the files loaded correctly. If an error occurs, it’s usually because the files are in an incorrect location.

> [!NOTE]
> Currently the Microsoft Edge update policies are only localized in en-US. Additional language support will be added in a future release.
-->

### 2. 필수 또는 권장 정책 설정

Active Directory 및 개별 컴퓨터 모두에 대해 그룹 정책 편집기를 사용하여 필수 또는 권장 정책을 설정해 Microsoft Edge를 구성할 수 있습니다. 아래에 설명된 대로 적절한 노드를 선택하여 정책 설정을 **컴퓨터 구성** 또는 **사용자 구성**으로 범위 지정할 수 있습니다.

- 필수 정책을 구성하려면 그룹 정책 편집기를 열고 (**컴퓨터 구성** 또는 **사용자 구성**) > **정책** > **관리 템플릿** > **Microsoft Edge**로 이동합니다.
- 권장 정책을 구성하려면 그룹 정책 편집기를 열고 (**컴퓨터 구성** 또는 **사용자 구성**) > **정책** > **관리 템플릿** > **Microsoft Edge – 기본 설정(사용자가 재정의할 수 있음)** 으로 이동합니다.

  ![로컬 그룹 정책 편집기 열기](./media/configure-microsoft-edge/edge-ad-policy.png)

### 3. 정책 테스트

대상 클라이언트 장치에서 Microsoft Edge를 열고 **edge://policy**로 이동하여 적용된 모든 정책을 확인합니다. 로컬 컴퓨터에서 정책 설정을 적용한 경우 정책이 즉시 표시됩니다. 정책 설정을 구성하는 동안 열려 있던 Microsoft Edge를 닫았다가 다시 열어야 할 수 있습니다.

![브라우저에서 구성된 정책 보기](./media/configure-microsoft-edge/edge-gpEdit.png)

Active Directory 그룹 정책 설정의 경우 정책 설정은 도메인 관리자가 정의한 정기적인 간격으로 도메인 컴퓨터에 전파되고, 대상 컴퓨터가 즉시 정책 업데이트를 받지 못할 수 있습니다. 대상 컴퓨터에서 Active Directory 그룹 정책 설정을 수동으로 새로 고치려면 대상 컴퓨터의 명령 프롬프트나 PowerShell 세션에서 다음 명령을 실행합니다.

``` powershell
gpupdate /force
```

새 정책이 표시되려면 Microsoft Edge을 닫았다가 다시 열어야 할 수 있습니다.

또한 대상 컴퓨터에서 REGEDIT.exe를 사용하여 그룹 정책 설정을 저장하는 레지스트리 설정을 볼 수 있습니다. 이러한 설정은 레지스트리 경로 **HKLM\SOFTWARE\Policies\Microsoft\Edge**에 있습니다.

## FAQ

### 마스터 기본 설정을 사용하도록 Microsoft Edge를 구성할 수 있나요?

예, 마스터 기본 설정 파일을 사용하도록 Microsoft Edge를 구성할 수 있습니다.

 마스터 기본 설정 파일을 사용하면 Microsoft Edge가 배포될 때 기본 설정을 구성할 수 있습니다. 또한 마스터 기본 설정 파일을 사용하여 장치 관리 시스템에서 관리하지 않는 컴퓨터에서 설정을 적용할 수 있습니다. 이러한 설정은 사용자가 브라우저를 처음 실행할 때 사용자 프로필에 적용됩니다. 사용자가 브라우저를 실행한 후에는 마스터 기본 설정 파일의 변경 내용이 적용되지 않습니다. 사용자는 브라우저에서 마스터 기본 설정에서 설정을 변경할 수 있습니다. 설정을 필수로 만들거나 브라우저를 처음 실행한 후 설정을 변경하려면 정책을 사용해야 합니다.

마스터 기본 설정 파일을 사용하면 다른 Chromium 기반 브라우저와 공유되는 항목과 Microsoft Edge에 고유한 항목을 포함하여 다양한 설정 및 기본 설정을 사용자 지정할 수 있습니다.  마스터 기본 설정 파일을 사용하여 정책 관련 기본 설정을 구성할 수 있습니다. 정책이 설정되어 있고 해당 마스터 기본 설정 집합이 있는 경우 정책 설정이 우선합니다.

> [!IMPORTANT]
> 사용 가능한 기본 설정 중 일부는 Microsoft Edge 용어 및 명명 규칙과 일치하지 않을 수 있습니다.  이후 릴리스에서 이러한 기본 설정이 예상대로 계속 작동한다는 보장은 없습니다. 이후 버전에서 기본 설정이 변경되거나 무시될 수 있습니다.

마스터 기본 설정 파일은 JSON 태그를 사용하여 서식 지정된 텍스트 파일입니다. 이 파일은 msedge.exe 실행 파일과 동일한 디렉터리에 추가해야 합니다. Windows에서의 시스템 수준 엔터프라이즈 배포인 경우 이 폴더는 일반적으로 *Windows: C:\Program Files\Microsoft\Edge\Application\master_preferences*입니다.

## 기타 참조

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [Intune을 사용한 Windows용 구성](configure-edge-with-intune.md)
- [macOS용 구성](configure-microsoft-edge-on-mac.md)
- [Microsoft Edge 엔터프라이즈 정책 찾아보기](microsoft-edge-policies.md)


