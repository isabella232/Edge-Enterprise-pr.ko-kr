---
title: Microsoft Edge ID 지원 및 구성
ms.author: avvaid
author: dan-wesley
manager: srugh
ms.date: 02/05/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge ID 지원 및 구성
ms.openlocfilehash: 05dc0fabe212f31fe9207c72d097913d5765915f
ms.sourcegitcommit: c290b0b0fa6b7d7f94dcdfdda91302da733326ec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "11314611"
---
# Microsoft Edge ID 지원 및 구성

이 문서에서는 Microsoft Edge에서 ID를 사용하여 동기화 및 SSO(Single Sign-On)와 같은 기능을 지원하는 방법을 설명합니다. Microsoft Edge는 Active Directory 도메인 서비스(AD DS), Azure Active Directory(Azure AD) 및 Microsoft 계정(MSA)을 사용한 로그인을 지원합니다. 현재 Microsoft Edge는 전역 클라우드 또는 GCC 독립 클라우드에 속한 azure Active Directory (Azure AD) 계정만 지원 합니다. 다른 독립 클라우드의 지원을 추가 하는 작업을 진행 중입니다.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.

## 브라우저 로그인 및 인증된 기능

Microsoft Edge에서는 Azure AD, MSA 또는 도메인 계정을 사용하여 브라우저 프로필에 로그인하는 것을 지원합니다. 로그인에 사용된 계정의 유형으로 Microsoft Edge에서 사용자가 사용할 수 있는 인증된 기능이 결정됩니다. 다음 표에는 각 계정 유형에 대한 기능 지원이 요약되어 있습니다.

| 기능   | Azure AD Premium | Azure AD Free | 온-프레미스 AD DS | MSA     |
|----|------------------|---------------|----------------|---------|
| 동기화 | 예 | 아니요 | 아니오 | 예 |
| 주 새로 고침 토큰을 사용한 SSO | 예 | 예 | 아니오 | 예 |
| Seamless SSO | 예 | 예 | 예 | 해당 없음 |
| windows 통합 인증 | 예 | 예 | 예 | 해당 없음 |
| 엔터프라이즈 새 탭 페이지 | O365 필요 |   O365 필요 | 아니오 | 해당 없음 |
| Microsoft Search | O365 필요 | O365 필요 | 아니오 | 해당 없음 |

## 사용자가 Microsoft Edge에 로그인하는 방법

### 자동 로그인

Microsoft Edge에서는 OS 기본 계정을 사용하여 자동으로 브라우저에 로그인합니다. 장치가 구성된 방식에 따라 사용자는 다음 방법 중 하나를 사용하여 Microsoft Edge에 자동으로 로그인할 수 있습니다.

- **하이브리드/AAD-J 장치:** Win10, 하위 버전 Windows 및 해당 서버 버전에서 사용할 수 있습니다.
사용자는 Azure AD 계정을 사용하여 자동으로 로그인됩니다.
- **도메인 연결된 장치:** Win10, 하위 버전 Windows 및 해당 서버 버전에서 사용할 수 있습니다.
기본적으로 사용자는 자동으로 로그인되지 않습니다. 도메인 계정을 사용하여 사용자가 자동 로그인되도록 하려면 [ConfigureOnPremisesAccountAutoSignIn](https://docs.microsoft.com/deployedge/microsoft-edge-policies#configureonpremisesaccountautosignin) 정책을 사용합니다. 해당 Azure AD 계정을 사용하여 사용자가 자동 로그인되도록 하려면 장치 하이브리드 연결을 고려해 보세요.
- **OS 기본 계정이 MSA인 경우:** Win10 RS3(버전 1709/빌드 10.0.16299) 이상. 엔터프라이즈 장치인 경우 이 시나리오는 적용될 가능성이 없습니다. 그러나 OS 기본 계정이 MSA인 경우 Microsoft Edge에서 MSA 계정을 사용하여 자동으로 로그인합니다.

### 수동 로그인

사용자가 자동으로 Microsoft Edge에 로그인되지 않으면 처음 실행할 때 브라우저 설정 과정에서, 아니면 ID 메뉴를 열어서 Microsoft Edge에 수동으로 로그인할 수 있습니다.

### 브라우저 로그인 관리

브라우저 로그인을 관리하려면 다음 정책을 사용할 수 있습니다.

- 사용자가 항상 Microsoft Edge 기반의 작업 프로필을 보유하고 있는지 확인합니다. [NonRemovableProfileEnabled 참조](https://docs.microsoft.com/deployedge/microsoft-edge-policies#nonremovableprofileenabled)
- 신뢰할 수 있는 계정 집합으로 로그인을 제한합니다. [RestrictSigninToPattern 참조](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern)
- 브라우저 로그인을 비활성화하거나 강제 적용합니다. [BrowserSignin 참조](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browsersignin)

## 브라우저-웹 SSO(Single Sign-On)

일부 플랫폼에서는 사용자가 자동으로 웹 사이트에 로그인하도록 Microsoft Edge를 구성할 수 있습니다. 이 옵션을 선택하면 회사 웹 사이트에 액세스하여 생산성을 높이기 위해 해당 자격 증명을 다시 입력하는 문제를 덜어줍니다.

### 주 새로 고침 토큰(PRT)을 사용한 SSO

Microsoft Edge에서 PRT 기반 SSO 지원을 기본 제공하므로 확장이 필요하지 않습니다. Windows 10 RS3 이상에서 사용자가 브라우저 프로필에 로그인되어 있으면 PRT 기반 SSO를 지원하는 웹 사이트에 대한 PRT 메커니즘을 사용하여 SSO 로그인됩니다.

PRT(주 새로 고침 토큰)는 Windows 10, iOS 및 Android 디바이스에서 인증에 사용되는 Azure AD 키입니다. 이 키는 해당 장치에서 사용되는 응용 프로그램 전체에서 SSO(single sign-on)를 사용하도록 설정합니다. 자세한 내용은 [주 새로 고침 토큰이란?](https://docs.microsoft.com/azure/active-directory/devices/concept-primary-refresh-token)을 참조하십시오.

### Seamless SSO

PRT SSO와 마찬가지로 Microsoft Edge는 확장하지 않아도 기본적으로 Seamless SSO 지원을 제공합니다. Windows 10 RS3 이상에서 사용자가 브라우저 프로필에 로그인되어 있으면 PRT 기반 SSO를 지원하는 웹 사이트에 대한 PRT 메커니즘을 사용하여 SSO 로그인됩니다.

Seamless Single Sign-On은 회사 네트워크에 연결된 회사 장치에서 사용자를 자동으로 로그인합니다. 이 설정을 사용하면 사용자는 Azure AD에 로그인하기 위해 암호를 입력할 필요가 없습니다. 일반적으로 사용자 이름을 입력할 필요도 없습니다. 자세한 내용은 [Active Directory Seamless Single Sign-On](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso)을 참조하세요.

### Windows 통합 인증(WIA)

Microsoft Edge는 또한 인증을 위해 브라우저를 사용하는 모든 응용 프로그램에 대해 조직 내부 네트워크에서 발생하는 인증 요청에 대한 Windows 통합 인증을 지원합니다. 이 기능은 모든 버전의 Windows 10 및 하위 수준 Windows에서 지원됩니다. 기본적으로 Microsoft Edge에서는 인트라넷 영역을 WIA용 허용 목록으로 사용합니다. 또는 [AuthServerAllowlist](https://docs.microsoft.com/deployedge/microsoft-edge-policies#authserverallowlist) 정책을 사용하여 통합 인증을 사용하도록 설정된 서버 목록을 사용자 지정할 수 있습니다. macOS에서 이 정책은 통합 인증을 사용하도록 설정하는 데 필요합니다.

Microsoft Edge(버전 77 이상)에서 WIA 기반 SSO를 지원하려면 일부 서버 쪽 구성을 수행해야 할 수도 있습니다. 새 Microsoft Edge 사용자 에이전트 문자열에 대한 지원을 추가하도록 Active Directory Federation 서비스(AD FS) 속성 **WiaSupportedUserAgents**를 구성해야 할 수 있습니다. 구성하는 방법에 대한 자세한 내용은 [WIASupportedUserAgent 설정 보기](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/configure-ad-fs-browser-wia#view-wiasupporteduseragent-settings) 및 [WIASupportedUserAgent 설정 변경](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/configure-ad-fs-browser-wia#change-wiasupporteduseragent-settings)을 참조하세요. Windows 10 기반 Microsoft Edge 사용자 에이전트 문자열의 예는 아래에 나와 있습니다. [여기에서 Microsoft Edge UA 문자열](https://docs.microsoft.com/microsoft-edge/web-platform/user-agent-string)에 대한 자세한 내용을 확인할 수 있습니다. 

다음 UA 문자열은 이 문서를 게시할 때 최신 Dev 채널 빌드의 예입니다.<br> `"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/80.0.3951.0 Safari/537.36 Edg/80.0.334.2"`

협상 자격 증명 위임이 필요한 서비스의 경우 Microsoft Edge에서는 [AuthNegotiateDelegateAllowlist](https://docs.microsoft.com/deployedge/microsoft-edge-policies#authnegotiatedelegateallowlist) 정책을 사용하여 제한 위임을 지원합니다.

## 추가 인증 개념

### 자동 관리 인증

자동 관리 인증은 웹 사이트 SSO에 대한 브라우저 관련 최적화로서, 이를 통해 자사의 특정 웹 사이트에 대한 인증이 우선 로드됩니다. 덕분에 사용자가 Bing을 검색 엔진으로 사용하는 경우에는 주소 표시줄 성능이 향상됩니다. 사용자 개인 설정 및 MSB(비즈니스용 Microsoft Search) 검색 결과를 제공합니다. 또한 Office 새 탭 페이지와 같은 주요 서비스에 대한 인증을 허용하도록 설정할 수도 있습니다. 이 경우 [ProactiveAuthEnabled]( https://docs.microsoft.com/deployedge/microsoft-edge-policies#proactiveauthenabled) 정책을 사용하여 관리할 수 있습니다.

### NTLM 인증용 Windows Hello CredUI

웹 사이트에서 NTLM 또는 협상 메커니즘을 사용하여 사용자 로그인을 시도하고 SSO를 사용할 수 없는 경우 사용자에게 Windows Hello 자격 증명 UI를 사용하여 인증 챌린지를 충족하도록 웹 사이트와 OS 자격 증명을 공유할 수 있는 환경을 제공합니다. 이러한 로그인 흐름은 NTLM 또는 협상 챌린지를 진행하는 동안 single sign-on 로그인되지 않는 Windows 10의 사용자에게만 표시됩니다.

### 저장된 암호를 사용하여 자동으로 로그인

사용자가 Microsoft Edge에 암호를 저장하면 자격 증명이 저장된 웹 사이트에 자동으로 로그인되는 기능을 사용할 수 있습니다. 사용자는 *edge://settings/passwords*로 이동하여 이 기능을 토글 전환할 수 있습니다. 이 기능을 구성하려면 [암호 관리자](https://docs.microsoft.com/deployedge/microsoft-edge-policies#password-manager-and-protection) 정책을 사용하면 됩니다.

## 참고 항목

- [Microsoft Edge Enterprise 방문 페이지](https://aka.ms/EdgeEnterprise)
- [비디오: Microsoft Edge 및 ID](microsoft-edge-video-identity.md)
- [ID 및 액세스 관리](https://www.microsoft.com/security/technology/identity-access-management)
- [ID 플랫폼](https://developer.microsoft.com/identity)
- [Azure Active Directory를 사용한 강력한 ID 기반 4단계](https://docs.microsoft.com/azure/active-directory/hybrid/four-steps)
