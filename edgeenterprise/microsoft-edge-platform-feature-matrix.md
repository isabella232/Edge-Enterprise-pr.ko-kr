---
title: Microsoft Edge 기능에 대한 플랫폼 지원
ms.author: collw
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge 기능에 대한 플랫폼 지원 요약
ms.openlocfilehash: c34249e126a1fb27c84a2f025c826654bb9df358
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2021
ms.locfileid: "11643124"
---
# <a name="platform-support-for-microsoft-edge-features"></a>Microsoft Edge 기능에 대한 플랫폼 지원

이 문서에서는 Microsoft Edge 기능에 대한 플랫폼 지원을 요약합니다.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.

## <a name="feature-matrix-for-platforms"></a>플랫폼용 기능 매트릭스

다음 표에는 Windows 및 macOS 플랫폼에 대한 기능 지원이 요약됩니다.

> [!NOTE]
> Android 및 iOS는 현재 지원 테이블에 나타내지 않습니다. 그러나 현재 이 정보에 대한 작업을 계속 진행하고 있으며 그에 따라 업데이트될 예정입니다.

| 보안 기능 |Win 10|Win 8.1|Win 7|macOS|URL|
|--------|-------|--------|-----|-------|---|
|Azure AD(Azure Active Directory) 조건부 액세스|예|예|예|예|[Azure AD 조건부 액세스](/deployedge/ms-edge-security-conditional-access#accessing-conditional-access-protected-resources-in-microsoft-edge)|
|Windows Defender Application Guard|예(1890+)|아니요|아니요|아니요|[Windows Defender Application Guard](/deployedge/microsoft-edge-security-windows-defender-application-guard) |
|Microsoft Defender SmartScreen|예|예|예|예|[Microsoft Defender SmartScreen](/deployedge/microsoft-edge-security-smartscreen) |
|Microsoft Endpoint DLP|예|아니요|아니요|아니요|[Microsoft Endpoint DLP](/deployedge/microsoft-edge-security-dlp#microsoft-endpoint-data-loss-prevention-endpoint-dlp)|
|암호 모니터.|예|예|예|예|[암호 모니터.](https://blogs.windows.com/msedgedev/2021/01/21/edge-88-privacy/)|
|암호 생성기|예|예|예|예|[암호 생성기](https://blogs.windows.com/msedgedev/2021/01/21/edge-88-privacy/)|
|WIP(Windows Information Protection)|예(1607+)|아니요|아니요|아니요|[WIP](/deployedge/microsoft-edge-security-windows-information-protection#system-requirements)|

|ID 기능| Win 10 | Win 8.1 | Win 7 | macOS | URL |
|--|--|--|--|--|--|
|자동 로그인(하이브리드/AAD-J)|예|예|예|아니요|[hybrid/AAD-J](/deployedge/microsoft-edge-security-identity#automatic-sign-in)|
|자동 로그인(조인된 도메인)|예|예|예|아니요|[조인된 도메인](/deployedge/microsoft-edge-security-identity#automatic-sign-in)|
|자동 로그인(OS 기본 계정은 MSA)|예(1709+)|아니요|아니요|아니요|[MSA](/deployedge/microsoft-edge-security-identity#automatic-sign-in)|
|브라우저-웹 SSO(Single Sign-On)|예|예|예|예|[브라우저-웹 SSO](https://www.microsoft.com/microsoft-365/roadmap?featureid=66332)|
|안내 스위치/"자동 프로필 전환"|예|예|예|예|[직장과 집에서 여러 프로필 사용](https://blogs.windows.com/msedgedev/2020/04/30/automatic-profile-switching/) |
|여러 프로필|예|예|예|예|[직장과 집에서 여러 프로필 사용](https://blogs.windows.com/msedgedev/2020/04/30/automatic-profile-switching/) |
|Active Directory(AD)를 위한 온-프레미스 동기화|예|예|예|아니요|[AD(Active Directory) 사용자를 위한 온-프레미스 동기화](/deployedge/microsoft-edge-on-premises-sync) |
|Seamless SSO|예(1709+)|예|예|예|[Seamless SSO](/deployedge/microsoft-edge-security-identity#seamless-sso)|
|주 새로 고침 토큰(PRT)을 사용한 SSO|예(1709+)|예|예|아니요|[PRT가 있는 SSO](/deployedge/microsoft-edge-security-identity#sso-with-primary-refresh-token-prt)|
|Windows 통합 인증(WIA)|예|예|예|Yes*(정책 필요)|[WIA](/deployedge/microsoft-edge-security-identity#windows-integrated-authentication-wia)|

|추가 기능|Win 10|Win 8.1|Win 7|macOS|URL|
|--------|-------|--------|-----|-------|---|
|컬렉션|예|예|예|예|[컬렉션](https://blogs.windows.com/msedgedev/2019/12/09/improvements-collections-sync-microsoft-edge/) |
|엔터프라이즈 새 탭 페이지|예|예|예|예|[새 탭 페이지](https://blogs.windows.com/msedgedev/2020/10/29/enterprise-new-tab-page-my-feed/) |
|IE 모드|예|예|예|아니요|[IE 모드](/deployedge/edge-ie-mode#prerequisites)|
|키오스크 모드|예|아니요|아니요|아니요|[키오스크 모드](/deployedge/microsoft-edge-configure-kiosk-mode)|
|Bing에서 Microsoft Search|예|예|예|예|[Bing의 지능형 검색](https://www.microsoft.com/edge/business/intelligent-search-with-bing) |
|PDF Reader|예|예|예|예|[PDF Reader](/deployedge/microsoft-edge-pdf) |
|쇼핑|예|예|예|예|[쇼핑](https://techcommunity.microsoft.com/t5/articles/introducing-shopping-with-microsoft-edge/m-p/1870080) |
|절전 탭|예|예|예|예|[기능 개요](/deployedge/microsoft-edge-relnote-stable-channel)<br>[최신 블로그 게시물](https://blogs.windows.com/msedgedev/2021/03/04/edge-89-performance/)<br>[그룹 정책](/deployedge/microsoft-edge-policies#sleeping-tabs-settings)|
|동기화|예|예|예|예| [Enterprise Sync](/deployedge/microsoft-edge-enterprise-sync) |
|버전 롤백|예|예|예|아니요|[버전 롤백](/deployedge/edge-learnmore-rollback) |
|세로 탭|예|예|예|예| |

## <a name="see-also"></a>참고 항목

- [Microsoft Edge Enterprise 방문 페이지](https://aka.ms/EdgeEnterprise)