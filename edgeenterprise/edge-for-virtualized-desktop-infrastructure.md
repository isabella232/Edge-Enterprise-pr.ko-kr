---
title: 가상화 데스크톱 인프라용 Edge
ms.author: anlake
author: AndreaLBarr
manager: collw
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 가상화된 데스크톱 인프라용 Microsoft Edge입니다.
ms.openlocfilehash: 5dc234b0e6fbba4778f8236399a0ff438f704578
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641854"
---
# <a name="microsoft-edge-for-virtualized-desktop-infrastructure"></a>가상화된 데스크톱 인프라용 Microsoft Edge

이 문서에서는 가상화된 환경에서 Microsoft Edge를 사용하기 위한 요구 사항 및 제한 사항에 대해 설명합니다.

## <a name="what-is-vdi"></a>VDI란 무엇인가요?

VDI(가상 데스크톱 인프라)는 데이터 센터의 중앙 서버에서 데스크톱 운영 체제 및 응용 프로그램을 호스팅하는 가상화 기술입니다. 이렇게 하면 완전히 보호되고 규정을 준수하는 중앙 집중식 원본을 사용하는 사용자가 완전히 개인 설정된 데스크톱 환경을 사용할 수 있습니다.

Microsoft Edge는 보안 및 제어되는 서버 환경에서 실행되는 동안 로컬 디바이스에서 사용할 수 있는 것과 거의 동일한 방식으로 가상화된 환경에서 사용할 수 있습니다. 선택한 VDI 솔루션에 따라 사용자에게 인트라넷 응용 프로그램 및 사이트에 대한 원활한 액세스를 제공할 수도 있습니다.

Edge의 대부분의 기능은 특별한 구성 없이 VDI 환경에서 지원됩니다. 그러나 최적의 환경을 보장하기 위해 아래 지침을 따르는 것이 좋습니다.

## <a name="platforms-certified-for-edge"></a>Edge용으로 인증된 플랫폼

- Azure 가상 데스크톱
- Citrix 가상 앱 및 데스크톱(이전의 XenApp 및 XenDesktop)

Edge 팀에서 아직 다른 VDI 솔루션을 확인하지는 않았지만 Edge에서 가장 일반적인 워크플로가 지원되어야 합니다. 아래에 제공된 지침은 선택한 솔루션에 적용되거나 적용되지 않을 수 있습니다.

## <a name="edge-on-vdi-performance-considerations"></a>VDI용 Edge 성능 고려 사항

VDI 환경을 설계할 때는 서버 구성의 제한뿐만 아니라 최적의 성능을 얻기 위해 사용자의 워크플로와 요구 사항을 신중하게 고려해야 합니다.

Edge는 VDI 환경에 Edge를 배포하기 위해 다음과 같은 최소 요구 사항을 권장합니다.

- vCPU – 사용자당 2-4개의 코어
- RAM – 사용자당 1GB

복잡하고 큰 웹 응용 프로그램 및 확장에는 더 많은 메모리가 필요하며 환경을 구성 시 이를 고려해야 합니다.

## <a name="edge-on-non-persisted-vdi-environments"></a>비지속형 VDI 환경의 Edge

많은 VDI 솔루션은 사용자에게 세션 간에 지속되는 가상 환경이 할당되는 지속형 환경과 사용자가 사용 가능한 여러 컴퓨터 중 하나에 할당되고(아마도 각 세션마다 다른 컴퓨터) 사용자 데이터가 세션 간에 동기화되거나 동기화되지 않을 수 있는 비지속형 환경에 대한 액세스를 허용합니다.

비지속형 환경을 사용하는 경우 일반적으로 필요한 앱 및 구성을 포함하는 각 장치에 사용되는 "골든 이미지"를 만듭니다. 다음은 이러한 이미지에 대해 Edge를 준비하기 위한 권장 사항입니다.

### <a name="deploy-edge"></a>Edge 배포

Windows 10 버전 1803 이상을 사용하는 경우 시스템에 Microsoft Edge가 설치되어 있어야 합니다. 그러나 이전 버전의 Windows 또는 다른 Edge 채널을 배포하려는 경우 다음 단계를 따르는 것이 좋습니다.

1. 다음에서 VDI VM 운영 체제와 일치하는 Edge MSI 패키지를 다운로드합니다.

    - [비즈니스용 Microsoft Edge 다운로드 - Microsoft](https://www.microsoft.com/edge/business/download)

2. 다음 명령을 실행하여 VDI VM에 MSI를 설치합니다.

    - `msiexec /i <path_to_msi> /qn /norestart /l*v <install_logfile_name>`

### <a name="disable-automatic-updates"></a>자동 업데이트를 사용하지 않도록 설정

비지속형 컴퓨터의 경우 자동 업데이트를 사용하지 않도록 설정하고 대신 "골든 이미지"를 업데이트하여 컴퓨터 풀 간에 버전 불일치가 없도록 Edge를 업데이트하는 것이 모범 사례입니다.

자동 업데이트를 사용하지 않도록 설정하려면 다음 정책을 참조하세요.

- [업데이트 정책 재정의 기본값](/deployedge/microsoft-edge-update-policies#updatedefault)

- [업데이트 정책 재정의](/deployedge/microsoft-edge-update-policies#update)

### <a name="profile-management"></a>프로필 관리

비지속형 설정에서는 VM이 세션 간에 사용자 상태를 유지 관리하지 않을 수도 있고 사용자에게 이전에 사용한 적이 없는 VM이 할당될 수 있으므로 사용자 데이터가 없을 수 있다는 점을 고려해야 합니다.

Edge는 Edge에 액세스하는 방법에 관계없이 사용할 수 있도록 사용자 데이터를 동기화하는 여러 가지 방법을 지원합니다.

### <a name="azure-ad-sync"></a>Azure AD Sync

Azure AD 플랜에서 지원하는 경우 엔터프라이즈 동기화는 Edge 사용자 데이터가 모든 사용자 장치에 동기화되도록 하는 가장 빠르고 쉬운 방법입니다.  

요구 사항 및 구성에 대한 자세한 내용은 다음을 참조하세요.  

- [Microsoft Edge 엔터프라이즈 동기화 구성 | Microsoft Docs](/deployedge/microsoft-edge-enterprise-sync)

### <a name="on-premise-sync-for-active-directory-users"></a>Active Directory 사용자를 위한 온-프레미스 동기화

온-프레미스 동기화를 사용하면 Microsoft Edge는 Active Directory 사용자의 즐겨찾기 및 설정을 다른 컴퓨터 간에 쉽게 이동할 수 있는 파일에 저장합니다.  

요구 사항 및 구성에 대한 자세한 내용은 다음을 참조하세요.  

- [AD(Active Directory) 사용자를 위한 온-프레미스 동기화 | Microsoft Docs](/deployedge/microsoft-edge-on-premises-sync)

### <a name="user-profile-redirection"></a>사용자 프로필 리디렉션  

이러한 비지속형 환경에서 사용자 컨텍스트가 유지되도록 전체 사용자 폴더를 마이그레이션하고 리디렉션하는 몇 가지 솔루션이 있습니다. 권장 솔루션을 확인하려면 VDI 공급자에게 문의하세요.

몇 가지 인기 있는 솔루션은 다음과 같습니다.

- [FSLogix 개요 - FSLogix | Microsoft Docs](/fslogix/overview)
- [Citrix 프로필 관리를 구성하는 방법](https://support.citrix.com/article/CTX222893)

이 방법을 사용하는 경우 사용자가 컴퓨터에 로그온하고 프로필을 마이그레이션할 때 초기 로드 시간을 줄이기 위해 백업된 사용자 폴더에서 불필요한 폴더를 제외하는 것이 좋습니다. 이 경우 크기를 줄이기 위해 백업에서 다음 폴더를 제외하는 것이 좋습니다.

- %LocalAppData%\Microsoft\Edge\User Data\Default\Cache
- %LocalAppData%\Microsoft\Edge\User Data\Default\Code Cache
- %LocalAppData%\Microsoft\Edge\User Data\Default\JumpListIconsTopSites
- %LocalAppData%\Microsoft\Edge\User Data\Default\JumpListIconsRecentClosed

## <a name="known-issues"></a>알려진 문제

### <a name="microsoft-edge-crashes-in-older-versions-of-xenapp-and-xendesktop"></a>이전 버전의 XenApp 및 XenDesktop에서 Microsoft Edge 충돌

이 문제는 최신 버전에서 완화해야 하지만 사용자 환경에서 이 문제가 발생하는 경우 Edge용 Citrix API 후크를 사용하지 않도록 설정하여 문제를 해결할 수 있습니다. [애플리케이션별로 Citrix API 후크를 사용하지 않도록 설정하는 방법](https://support.citrix.com/article/CTX107825)을 참조하세요.

### <a name="degraded-performance-when-rendering-pages-with-exceptionally-large-html-tables"></a>매우 큰 HTML 테이블로 페이지를 렌더링할 때 성능이 저하됨

다음 Citrix 정책은 매우 큰(30,000개 이상의 행) 테이블이 있는 html 페이지의 렌더링 속도를 늦추는 것으로 알려져 있습니다.

- 자동 키보드 디스플레이
- 콤보 상자 원격 제어

자세한 내용은 [모바일 환경 정책 설정(citrix.com)](https://docs.citrix.com/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/mobile-experience-policy-settings.html)을 참조하세요. 이러한 정책을 사용하지 않도록 설정하면 문제가 완화됩니다.

### <a name="windows-account-manager-authorization-scenarios-ie--azure-sync-fail-in-edge-when-run-as-a-citrix-seamless-application"></a>Windows 계정 관리자 권한 부여 시나리오(예: Azure 동기화)는 Citrix 원활한 응용 프로그램으로 실행되면 Edge에서 실패합니다.

이는 "원활한" 모드에서 실행할 때 초기화되지 않는 시나리오에 필요한 Windows 구성 요소로 인해 Edge 및 WAM(예: Office)을 사용하는 다른 응용 프로그램에서 알려진 문제입니다. 이 문제를 해결하려면 다음을 수행합니다.

- 원활한 원격 응용 프로그램 대신 원격 데스크톱을 통해 Citrix 호스트에 Edge를 사용합니다.
- 대신 이 문제에 대한 완화 기능이 있는 Azure 가상 데스크톱 원격 앱을 사용합니다.
