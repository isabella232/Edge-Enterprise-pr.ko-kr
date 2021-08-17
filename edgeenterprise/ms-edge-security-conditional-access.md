---
title: Microsoft Edge 및 조건부 액세스
ms.author: srugh
author: srugh
manager: seanlyn
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge 및 조건부 액세스
ms.openlocfilehash: 56d593809d9c14a6ecfe58ef67745de78eeba452
ms.sourcegitcommit: a1d30ff66c448db4fd9fdb59ea439c0b0908b1c2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2021
ms.locfileid: "11894131"
---
# <a name="microsoft-edge-and-conditional-access"></a>Microsoft Edge 및 조건부 액세스
  
이 문서에서는 Microsoft Edge에서 조건부 액세스를 지원하는 방법과 조건부 액세스로 보호되는 리소스에 액세스하는 방법을 설명합니다.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.

클라우드 리소스를 관리할 때 클라우드 보안의 주요 측면은 ID와 액세스입니다. 모바일 중심, 클라우드 중심 세계에서 사용자는 어디서나 다양한 장치와 앱을 사용하여 조직의 리소스에 액세스할 수 있습니다. 따라서 누가 리소스에 액세스할 수 있는지에 초점을 맞추는 것만으로는 충분하지 않습니다. 리소스에 액세스하는 방법도 고려해야 합니다. Azure AD(Azure Active Directory) 조건부 액세스를 통해 보안과 생산성 사이의 균형을 유지할 수 있습니다.

## <a name="accessing-conditional-access-protected-resources-in-microsoft-edge"></a>Microsoft Edge에서 조건부 액세스 보호 리소스에 액세스

Microsoft Edge는 Azure AD 조건부 액세스를 기본적으로 지원합니다. 별도의 확장 프로그램을 설치할 필요가 없습니다. 엔터프라이즈 Azure AD 자격 증명을 사용하여 Microsoft Edge 프로필에 로그인하면 Microsoft Edge는 조건부 액세스를 사용하여 보호된 엔터프라이즈 클라우드 리소스에 대한 원활한 액세스를 허용합니다.

규정을 준수하는 장치에서 리소스에 액세스하는 ID는 프로필에서의 ID와 일치해야 합니다.  그렇지 않으면 다음 스크린샷과 같은 메시지가 표시됩니다. 스크린샷 예에서 "testadmin@evostsoneboxtest.com"은 리소스에 액세스하는 데 필요한 로그인 계정입니다.

![브라우저의 조건부 액세스 메시지](./media/edge-security/microsoft-edge-security-conditional-access.png)

계속하려면 필요한 프로필(있는 경우)로 전환하거나 일치하는 ID를 사용하여 프로필을 만들어야 합니다.

로그인하고 프로필 작업을 수행하려면 브라우저의 오른쪽 위 모서리에 있는 계정 사진을 클릭합니다. 드롭다운 메뉴를 사용하여 다음을 수행할 수 있습니다.

- 다른 프로필을 선택합니다. 프로필 이름을 클릭합니다.
- 프로필을 만듭니다. **프로필 추가**를 클릭합니다.
- 프로필을 관리합니다. **프로필 설정 관리**를 클릭합니다.

이 지원은 모든 지원되는 Windows 및 macOS 버전을 포함하여 모든 플랫폼에서 사용할 수 있습니다.

### <a name="how-to-deploy-conditional-access-in-azure-active-directory"></a>Azure Active Directory에서 조건부 액세스를 배포하는 방법

[조건부 액세스 배포](/azure/active-directory/conditional-access/plan-conditional-access)는 Azure Active Directory에서 조건부 액세스를 배포할 수 있는 자세한 지침을 제공합니다.

## <a name="see-also"></a>참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [비디오: 보안, 호환성 및 관리 용이성](/deployedge/microsoft-edge-video-security-compatibility-manageability)