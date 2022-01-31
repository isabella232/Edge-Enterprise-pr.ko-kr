---
title: Microsoft Edge VDI(가상 데스크톱 인프라)
ms.author: anlake
author: dan-wesley
manager: collw
ms.date: 11/12/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge VDI(가상 데스크톱 인프라)에 대한 자세한 설명입니다.
ms.openlocfilehash: fe1c1a7acf0b514812ff0aaf8f7a2b307304657d
ms.sourcegitcommit: e7f3098d8b7d91cae20b5778a71a87daababc312
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "12298136"
---
# <a name="microsoft-edge-for-virtual-desktop-infrastructure-vdi"></a>Microsoft Edge VDI(가상 데스크톱 인프라)

이 문서에서는 가상 환경에서 데이터를 사용할 때 Microsoft Edge 제한 사항에 대해 설명하고 있습니다.

## <a name="what-is-vdi"></a>VDI란 무엇인가요?

VDI(가상 데스크톱 인프라)는 데이터 센터의 중앙 서버에서 운영 체제 및 응용 프로그램을 호스팅하는 데스크톱 가상화 기술입니다. 이 기술을 사용하면 안전하고 호환되는 중앙 집중식 소스에서 사용자에게 완전히 개인 설정된 데스크톱 환경을 사용할 수 있습니다.

Microsoft Edge 디바이스에서 사용되는 방식과 거의 동일한 방식으로 가상 환경에서 사용할 수 있습니다. 가상 데스크톱은 보안 및 제어 서버 환경을 활용합니다. 선택한 VDI 솔루션에 따라 사용자에게 인트라넷 응용 프로그램 및 사이트에 대한 원활한 액세스 권한을 부여할 수도 있습니다.

대부분의 Microsoft Edge 기능은 특별한 구성 없이 VDI 환경에서 지원됩니다. 그러나 환경을 최적화하기 위해 다음 지침을 검토하는 것이 좋습니다.

## <a name="platforms-certified-for-microsoft-edge"></a>Microsoft Edge

다음 플랫폼은 인증을 Microsoft Edge.

- Azure 가상 데스크톱
- Citrix 가상 앱 및 데스크톱(이전의 XenApp 및 XenDesktop)

다른 VDI 솔루션은 아직 Microsoft Edge 팀에서 인증하지 않았지만, Microsoft Edge 가장 일반적인 워크플로가 지원될 것으로 예상됩니다. 다음 지침은 선택한 솔루션에 적용되거나 적용되지 않을 수 있습니다.

## <a name="performance-considerations-for-microsoft-edge-on-vdi"></a>VDI에 대한 Microsoft Edge 고려 사항

VDI 환경을 디자인할 때 최적의 성능을 달성하기 위해 사용자의 워크플로와 요구 사항을 신중하게 고려하고 서버 구성의 제한을 이해해야 합니다.

VDI 환경에 배포하는 경우 다음과 같은 최소 Microsoft Edge 권장됩니다.

- vCPU – 사용자당 코어 2-4개
- RAM – 사용자당 1GB

크고 복잡한 웹 응용 프로그램 및 확장에는 더 많은 메모리 및 처리 기능이 필요하며, 가상 환경을 구성할 때 고려해야 합니다.

## <a name="microsoft-edge-on-non-persisted-vdi-environments"></a>Microsoft Edge VDI 환경에서만 사용할 수 있습니다.

많은 VDI 솔루션은 사용자에게 세션 간에 지속되는 가상 환경이 할당되는 지속형 환경과 사용자가 사용 가능한 여러 컴퓨터 중 하나에 할당되고(아마도 각 세션마다 다른 컴퓨터) 사용자 데이터가 세션 간에 동기화되거나 동기화되지 않을 수 있는 비지속형 환경에 대한 액세스를 허용합니다.

비영구 환경을 사용하는 경우 일반적으로 각 디바이스에 배포될 필수 앱 및 구성이 있는 "골든 이미지"를 만듭니다. 골든 이미지를 준비하기 위한 가이드로 다음 권장 사항을 사용하세요.

### <a name="deploy-microsoft-edge"></a>Microsoft Edge 배포

버전 Windows 10 1803 이상을 사용 중이면 시스템에 Microsoft Edge 이미 설치되어 있는 것입니다. 그러나 이전 버전의 Windows 또는 다른 Microsoft Edge 채널을 배포하려는 경우 다음 단계를 수행합니다.

1. 다음 Microsoft Edge VDI VM 운영 체제와 일치하는 MSI 패키지를 다운로드합니다.

    - [비즈니스용 Microsoft Edge 다운로드 - Microsoft](https://www.microsoft.com/edge/business/download)

2. 다음 명령을 실행하여 VDI VM(가상 컴퓨터)에 MSI를 설치합니다.

    - `msiexec /i <path_to_msi> /qn /norestart /l*v <install_logfile_name>`

### <a name="disable-automatic-updates"></a>자동 업데이트를 사용하지 않도록 설정

영구적이지 않은 컴퓨터의 경우 가상 컴퓨터 풀에서 버전 불일치가 Microsoft Edge 업데이트하여 자동 업데이트를 사용하지 않도록 설정하고 골든 이미지를 업데이트하는 것이 가장 좋습니다.

자동 업데이트를 사용할 수 없습니다.에 대한 자세한 내용은 다음 정책을 참조하세요.

- [업데이트 정책 재정의 기본값](/deployedge/microsoft-edge-update-policies#updatedefault)

- [업데이트 정책 재정의](/deployedge/microsoft-edge-update-policies#update)

### <a name="profile-management"></a>프로필 관리

비영구적 설치에서는 VM이 세션 간에 사용자 상태를 유지 관리하지 않을 수 있습니다. 또는 사용자에게 이전과는 다른 VM이 할당될 수 있습니다. 이 시나리오에서는 VM에 사용자 데이터가 없습니다.

Microsoft Edge 사용자 데이터에 액세스하는 방법에 관계없이 사용할 수 있도록 사용자 데이터를 동기화하는 여러 가지 방법을 Microsoft Edge. AD 사용자에 Azure Active Directory(Azure AD) 동기화 및 사내 동기화의 두 가지 방법이 있습니다.

### <a name="azure-ad-sync"></a>Azure AD Sync

Azure AD 계획에서 지원하는 경우 Enterprise 동기화는 사용자 데이터가 모든 사용자 Microsoft Edge 동기화되도록 하는 가장 빠르고 쉬운 방법입니다. 자세한 내용은 엔터프라이즈 동기화 Microsoft Edge [구성을 참조하세요.](/deployedge/microsoft-edge-enterprise-sync)

### <a name="on-premise-sync-for-active-directory-users"></a>Active Directory 사용자를 위한 온-프레미스 동기화

온-프레미스 동기화를 사용하면 Microsoft Edge는 Active Directory 사용자의 즐겨찾기 및 설정을 다른 컴퓨터 간에 쉽게 이동할 수 있는 파일에 저장합니다.  

요구 사항 및 구성에 대한 자세한 내용은 AD(Active Directory) 사용자에 대한 [사내 동기화를 참조하세요.](/deployedge/microsoft-edge-on-premises-sync)

### <a name="user-profile-redirection"></a>사용자 프로필 리디렉션  

사용자 컨텍스트가 비영구적 환경에서 유지되도록 전체 사용자 폴더를 마이그레이션하고 리디렉션하는 몇 가지 솔루션이 있습니다. VDI 공급자에게 문의하여 환경에 권장되는 솔루션을 확인하십시오.

몇 가지 인기 있는 솔루션에는 다음 옵션이 포함됩니다.

- [FSLogix 개요 - FSLogix](/fslogix/overview)
- [Citrix 프로필 관리를 구성하는 방법](https://support.citrix.com/article/CTX222893)

사용자가 컴퓨터에 로그온하고 프로필을 마이그레이션하는 경우 초기 로드 시간을 줄이기 위해 백업된 사용자 폴더에서 불필요한 폴더를 제외해야 하는 경우도 있습니다. 이 경우 크기를 줄이기 위해 백업에서 다음 폴더를 제외하는 것이 좋습니다.

- %LocalAppData%\Microsoft\Edge\User Data\Default\Cache
- %LocalAppData%\Microsoft\Edge\User Data\Default\Code Cache
- %LocalAppData%\Microsoft\Edge\User Data\Default\JumpListIconsTopSites
- %LocalAppData%\Microsoft\Edge\User Data\Default\JumpListIconsRecentClosed

## <a name="known-issues"></a>알려진 문제

### <a name="microsoft-edge-crashes-in-older-versions-of-xenapp-and-xendesktop"></a>이전 버전의 XenApp 및 XenDesktop에서 Microsoft Edge 충돌

이러한 제품의 최신 버전에서는 이 문제를 완화해야 합니다. 그러나 환경에서 이 문제가 발생하는 경우 사용자에 대해 Citrix API 후크를 사용하지 않도록 설정하여 문제를 Microsoft Edge 응용 프로그램 기준에 따라 [Citrix API](https://support.citrix.com/article/CTX107825) 후크를 사용하지 않도록 설정하는 방법을 참조합니다.

### <a name="degraded-performance-when-rendering-pages-with-exceptionally-large-html-tables"></a>매우 큰 HTML 테이블로 페이지를 렌더링할 때 성능이 저하됨

다음 Citrix 정책은 큰(30,000개 이상의 행) 테이블을 사용하여 html 페이지 렌더링을 느리게 하는 것으로 알려져 있습니다.

- 자동 키보드 디스플레이
- 콤보 상자 원격 제어

자세한 내용은 모바일 환경 정책 [설정(citrix.com)을](https://docs.citrix.com/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/mobile-experience-policy-settings.html) 참조하세요. 이러한 정책을 사용하지 않도록 설정하면 문제가 완화됩니다.

### <a name="windows-account-manager-authorization-scenarios-that-is-azure-sync-fail-in-microsoft-edge-when-run-as-a-citrix-seamless-application"></a>Windows 원활한 응용 프로그램으로 실행하면 계정 관리자 권한 부여 시나리오(Microsoft Edge Azure 동기화)가 실패합니다.

이는 "원활한" 모드에서 Microsoft Edge 실행 시 초기화되지 않는 필요한 Windows 구성 요소로 인해 WAM을 사용하는 Office 응용 프로그램 및 기타 응용 프로그램에서 알려진 문제입니다. 이 문제를 해결하기 위해 다음 옵션 중 하나를 시도해 보십시오.

- 원활한 Microsoft Edge 대신 원격 데스크톱을 통해 Citrix 호스트로 전송할 수 있습니다.
- 이 문제를 완화하는 Azure Virtual Desktop 원격 앱을 대신 사용합니다.

## <a name="see-also"></a>참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [Azure Virtual Desktop](https://azure.microsoft.com/services/virtual-desktop/)