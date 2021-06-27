---
title: 'Microsoft Edge 암호 관리자 보안 '
ms.author: v-andreabarr
author: AndreaLBarr
manager: collw
ms.date: 05/05/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 암호 관리자 보안
ms.openlocfilehash: 830658dd1ff577bfb88be5512c955d556c437bcb
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2021
ms.locfileid: "11618227"
---
# <a name="microsoft-edge-password-manager-security"></a>Microsoft Edge 암호 관리자 보안 

이 문서의 자주 묻는 질문에는 Microsoft Edge에서 기본 제공하는 암호 관리자가 사용자 암호를 보호하는 방법에 대한 설명이 나와 있습니다.

> [!Note]
>이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.

## <a name="how-are-passwords-stored-in-microsoft-edge-and-how-safe-is-this-approach"></a>Microsoft Edge는 어떻게 암호를 저장하고, 그 방식은 얼마나 안전한가요?

Microsoft Edge는 디스크에 암호화된 데이터로 암호를 저장합니다. AES256을 사용하여 암호화되며, 암호화 키는 OS(운영 체제) 저장소 영역에 저장됩니다. 이 기술을 로컬 데이터 암호화라고 합니다. 모든 브라우저 데이터가 암호화되는 것은 아니지만, 암호, 신용 카드 번호 및 쿠키와 같은 중요한 데이터는 저장 시 암호화됩니다.

이 Microsoft Edge 암호 관리자는 사용자가 운영 체제에 로그인할 때만 액세스할 수 있도록 암호를 암호화합니다. 공격자가 관리자 권한 또는 오프라인 액세스 권한을 가지며 로컬에 저장된 데이터에 액세스할 수 있는 경우에도 시스템은 공격자가 로그인하지 않은 사용자의 일반 텍스트 암호를 얻지 못하도록 설계되어 있습니다.

다른 사용자의 암호를 해독하는 방법은 해당 사용자가 로그인한 상태로 공격자가 사용자의 암호를 가지고 있거나 도메인 컨트롤러를 손상시킨 경우입니다.

### <a name="about-the-encryption-method"></a>암호화 방법

프로필의 암호화 키는 Chromium OSCrypt를 사용하여 보호하며, 다음과 같은 플랫폼별 OS 저장소 위치를 사용합니다.

- Windows에서 저장소 영역은 DPAPI입니다.

- Mac에서 저장소 영역은 키체인입니다.

- Linux에서 저장소 영역은 Gnome Keyring 또는 KWallet입니다.

이러한 모든 저장소 영역은 사용자로 실행되는 일부 또는 모든 프로세스에서 액세스할 수 있는 키를 사용하여 AES256 키를 암호화합니다. 때로는 브라우저 위협 모델 및 보안 상태를 잘못 이해하여 이러한 공격 벡터가 '악용' 또는 '취약성'으로 블로그에 실리기도 합니다.

그러나 물리적으로 로컬 공격과 맬웨어는 위협 모델에 속하지 않으며, 이러한 조건에서 암호화된 데이터가 취약할 수 있습니다. 컴퓨터의 맬웨어에 감염된 경우, 공격자는 브라우저의 저장소 영역에 대해 암호가 해독된 액세스를 얻을 수 있습니다. 사용자 계정으로 실행되는 공격자 코드는 사용자에게 가능한 모든 작업을 할 수 있습니다.

## <a name="why-encrypt-data-locally-why-not-store-the-encryption-key-elsewhere-or-make-it-harder-to-obtain"></a>데이터를 로컬에서 암호화하는 이유 왜 암호화 키를 다른 곳에 저장하거나 더 어렵게 만들지 않나요?

인터넷 브라우저(Microsoft Edge 포함)에는 컴퓨터에서 사용자로서 실행되는 맬웨어로 인해 전체 장치가 손상된 위협으로부터 보호할 수 있는 방어 기능이 없습니다. 하지만 Microsoft Defender SmartScreen 및 Windows Defender와 같은 OS 수준의 보호 프로그램은 시작부터 장치가 손상되지 않게 디자인됩니다.

완전히 신뢰를 확보한 맬웨어로부터 보호할 수는 없지만, 로컬 데이터 암호화는 특정 시나리오에서 유용합니다. 예를 들면, 공격자가 코드를 실행할 수 없는 디스크에서 파일을 도용하는 방법을 찾거나, 전체 디스크 암호화로 보호되지 않는 노트북을 도난당한 경우, 로컬 데이터 암호화는 저장된 데이터 가져오기를 더 어렵게 합니다.

## <a name="do-you-recommend-storing-passwords-in-microsoft-edge"></a>Microsoft Edge에 암호를 저장하는 것이 좋은가요?

Microsoft Edge의 기본 제공 암호 관리자에 의지하는 사용자는 암호를 모두 기억하고 자주 입력할 필요가 없기 때문에 보다 강력하고 고유한 암호를 더 많이 사용할 수 있습니다. 또한 암호 관리자는 사용자가 속한 사이트의 암호만 자동으로 채우기 때문에, 사용자가 피싱 공격에 노출될 가능성이 적습니다.

> [!Note]
>업계 보고서에 따르면 온라인 인시던트의 80%는 피싱과 관련이 있으며, 훈련을 거치지 않은 사용자의 37%가 피싱 테스트에 실패한 것으로 나타났습니다.

Microsoft Edge 암호 관리자는 편리하고 쉽게 배포할 수 있어 보안이 강화됩니다. 동기화와 결합하면 모든 장치에서 암호를 얻을 수 있으며, 모든 웹 사이트에 각기 다른 암호를 쉽게 사용할 수 있습니다. 모든 사이트에 기억할 필요 없이 길고 복잡한 암호를 사용할 수 있으며, 매시간 복잡한 문자열을 입력하는 번거로움을 피할 수 있습니다. 암호 관리자의 편리성은 피싱 공격에 대한 위험을 줄인다는 의미입니다.

그러나 사용자의 운영 체제 로그인 세션에 키가 지정된 암호 관리자를 사용하면, 해당 세션의 공격자는 사용자가 저장한 모든 암호를 즉시 검색할 수 있습니다. 훔칠 암호 관리자가 없으면 악의적 사용자는 키 입력을 추적하거나 입력한 암호를 모니터링해야 합니다.

암호 관리자의 사용 여부는 전체 장치가 손상될 가능성에 대비해 설명한 많은 이점의 평가에 달려 있습니다. 대개의 위협 모델에서는 Microsoft Edge 암호 관리자를 사용하는 것이 좋습니다.

> [!Note]
>엔터프라이즈에서 특정 암호 도용이나 도난당한 암호로 인해 사이트가 손상되는 것을 우려하는 경우에는 추가 예방 조치를 취해야 합니다. 이러한 종류의 문제를 줄이는 데 도움이 되는 몇 가지 효과적인 솔루션은 Active Directory, Azure Active Directory 또는 타사 서비스를 통한 SSO(Single Sign On)입니다. 다른 솔루션에는 2단계 인증(예: [MS Authenticator](/azure/active-directory/user-help/user-help-auth-app-download-install)) 또는  [WebAuthN](https://webauthn.guide/)이 있습니다.

## <a name="should-a-password-manager-be-enabled-by-an-organization"></a>조직에서 암호 관리자의 사용을 설정해야 하나요?

간단하고 쉬운 대답은 다음과 같습니다. 예, 브라우저의 암호 관리자를 사용합니다.

더 완전한 응답은 보안 옵션 및 선택이 여러 위협 모델에 따라 달라지기 때문에 위협 모델에 대한 심층적인 지식을 쌓아야 하다는 의미입니다. 조직에서 암호 관리자에 대한 사용 설정 여부를 생각할 때 고려해야 할 몇 가지 관련 질문은 다음과 같습니다.

- 어떤 종류의 공격자에 대해 걱정하나요?

- 사용자가 로그인할 수 있는 웹 사이트는 무엇인가요?

- 사용자가 강력하고 고유한 암호를 선택하나요?

- 사용자의 계정이 2단계 인증으로 보호를 받나요?

- 가장 가능성이 높은 공격은 무엇인가요?

- 어떻게 맬웨어로부터 엔터프라이즈 장치를 보호하나요?

- 불편에 대한 사용자의 개인적인 허용 오차는 어떤가요?

- 데이터 동기화의 영향을 고려합니다.

다양한 사용자 기기와 동기화되므로 사용자 데이터의 보안과 조직에서 자동 완성 데이터 동기화를 제어하는 정도를 고려하는 것이 중요합니다. 

데이터 동기화 및 Microsoft Edge:

- 조직 전체에서 원하는 경우 데이터 동기화 사용을 설정하거나 사용하지 않도록 설정할 수 있습니다.

- 클라우드에서 전송 중 및 미사용 데이터 보안: 동기화된 모든 데이터는 브라우저와 Microsoft 서버 간 전송될 때 HTTPS를 통해 전송되는 암호화됩니다. 동기화된 데이터는 Microsoft 서버의 암호화된 상태로도 저장됩니다. 동기화하기 전에 주소 및 암호와 같은 중요한 데이터 형식이 장치에서 추가로 암호화됩니다. 회사 또는 학교 계정을 사용하는 경우, 모든 데이터 형식은 Microsoft Information Protection을 사용하여 동기화되기 전에 추가로 암호화됩니다.

## <a name="why-do-microsoft-security-baselines-recommend-disabling-the-password-manager"></a>Microsoft 보안 기준에서 암호 관리자를 사용하지 않도록 설정하는 것을 권장하는 이유는 무엇인가요?

Microsoft 보안 팀은 현재 엔터프라이즈 PCS 네트워크를 손상시키는 웜의 영향(모든 장치의 암호 관리자에서 모든 자격 증명 손실)을 단일 사용자 입력 자격 증명을 손상시키는 대상 피싱 공격의 위험(가능성이 높지만 영향이 낮음)보다 더 심각한 것으로 평가했습니다.

이 평가를 논의하는 중이며, Microsoft Edge의 새로운 보안 강화 기능이 추가되어 변경될 수 있습니다.

## <a name="can-malicious-extensions-gain-access-to-passwords"></a>악의적인 확장이 암호에 액세스할 수 있나요?

페이지와 상호 작용할 수 있는 권한이 있는 확장은 기본적으로 자동 입력 암호를 포함하여 해당 페이지의 모든 항목에 액세스할 수 있습니다. 마찬가지로, 악의적인 확장은 양식 필드 및 네트워크 요청/응답의 내용을 수정하여 현재 사용자 로그인 컨텍스트의 권한을 오용할 수 있습니다.

하지만 Microsoft Edge는 설치된 확장을 세부적으로 제어할 수 있는 광범위한 정책 집합을 제공합니다. 다음 표의 정책을 사용하여 회사 데이터를 보호해야 합니다.

| 정책 | 캡션 |
|-|-|
|[BlockExternalExtensions](/deployedge/microsoft-edge-policies#blockexternalextensions)|외부 확장이 설치되지 않도록 차단압니다.|
|[ExtensionAllowedTypes](/deployedge/microsoft-edge-policies#extensionallowedtypes)|허용된 확장 유형 구성|
|[ExtensionInstallAllowlist](/deployedge/microsoft-edge-policies#extensioninstallallowlist)|특정 확장 설치 허용|
|[ExtensionInstallBlocklist](/deployedge/microsoft-edge-policies#extensioninstallblocklist)|설치할 수 없는 확장 제어|
|[ExtensionInstallForcelist](/deployedge/microsoft-edge-policies#extensioninstallforcelist)|자동으로 설치되는 확장 제어|
|[ExtensionInstallSources](/deployedge/microsoft-edge-policies#extensioninstallsources)|확장 및 사용자 스크립트 설치 원본 구성|
| [ExtensionSettings](/deployedge/microsoft-edge-policies#extensionsettings) |확장 관리 설정 구성 |

## <a name="how-does-the-microsoft-edge-password-manager-compare-with-a-third-party-product"></a>Microsoft Edge 암호 관리자를 타사 제품과 비교하면 어떤가요?

다음 표에서 Microsoft Edge 암호 관리자가 타사 암호 관리자와 어떻게 비교되는지 나타냅니다.

| 타사 암호 관리자 | Microsoft Edge 암호 관리자|
|-|-|
| *서버 동기화*. 일부 제품은 모든 장치를 동기화하기 위해 암호를 클라우드에 저장합니다. 이 기능은 유용하지만, 클라우드 서비스가 손상되어 데이터가 노출될 위험이 있습니다. **설명:**   클라우드에서 암호를 암호화하고 장치에 암호화 키를 저장하여 공격자가 키와 암호에 액세스하지 못하게 해서 위험을 완화합니다.| Microsoft Edge를 설치한 Windows 장치 간에 암호가 동기화되기 때문에 클라우드 노출 위험이 있습니다. **설명:**   이 위험은 이 문서에서 다루는 데이터 보안 단계에 따라 완화됩니다.|
| *신뢰*. 타사에서 암호를 다른 당사자에게 보내는 것과 같은 악의적인 작업을 하지 않는 것을 신뢰해야 합니다. **설명:**   소스 코드(오픈 소스 제품의 경우)를 검토하거나 공급업체가 신뢰도와 수익을 중요시할 때 이러한 위험을 완화할 수 있습니다. | **설명:** Microsoft는 수십 년간 엔터프라이즈급 보안 및 생산성을 제공하고 전 세계 암호를 보호하도록 설계한 리소스를 공급하는 명성 있고 신뢰도 높은 공급업체입니다. |
| *공급망 보안*. 공급업체에 소스 코드에 대한 보안 공급망/빌드/릴리스 프로세스가 있는지 확인하기는 어려운 일입니다. |**설명:** Microsoft에는 소스 코드의 위험을 최소화하기 위한 강력한 내부 프로세스가 있습니다. |
| *손상된 클라이언트 또는 계정*. 클라이언트 장치 또는 사용자 계정이 손상된 경우, 공격자는 암호를 가져올 수 있습니다. **설명:** 이 위험은 사용자가 암호를 해독하기 위해 로컬에 저장되지 않은 마스터 암호를 입력해야 하는 일부 암호 관리자에 대해 완화됩니다. 마스터 암호는 공격자가 양식 필드의 입력에서 키 입력을 읽고 마스터 암호를 입력하거나 프로세스 메모리에서 암호를 읽을 수 있기 때문에 부분적인 완화 기능일 뿐입니다. | **설명:** Microsoft는 장치가 손상되지 않도록 설계된 Windows Defender 같은 OS 수준의 보호를 합니다. 그러나 클라이언트 장치가 손상되면 공격자가 암호를 해독할 수 있습니다. |

> [!Note]
> 타사 제품은 추가 위협 모델에 대한 보호를 제공할 수 있지만, 복잡성 또는 사용 편의성의 손실을 감당해야 합니다. Microsoft Edge 암호 관리자는 그룹 정책 사용하여 IT 관리자가 완전히 제어할 수 있고 타사 트러스트가 필요하지 않은 편리하고 사용하기 쉬운 암호 관리를 제공하도록 설계한 것입니다.

## <a name="why-doesnt-microsoft-offer-a-master-password-to-protect-the-data"></a>Microsoft에서 데이터를 보호하기 위해 마스터 암호를 제공하지 않는 이유는 무엇입니까?

브라우저 암호가 디스크에서 암호화되면 로컬로 실행되는 맬웨어를 포함하여 장치의 모든 프로세스에서 암호화 키를 사용할 수 있습니다. 마스터 키로 암호가 ‘자격 증명 모음’에 암호화되어 있는 경우에도 브라우저의 메모리 공간에 로드될 때 암호가 해독되고 자격 증명 모음의 잠금을 해제한 후 수집할 수 있습니다.

데이터를 자동으로 채우기 전에 사용자를 인증하는 마스터 암호 기능은 더 광범위한 위협 완화를 위해 편의상 장단점이 있습니다. 특히 맬웨어 또는 물리적인 로컬 공격자에 대한 데이터 노출 기간을 줄이는 데 도움이 됩니다. 그러나 마스터 암호는 무적이 아니며, 로컬 공격자 및 전용 맬웨어에는 마스터 암호 보호를 우회하기 위한 다각적인 전략이 있습니다.

> [!Note]
> Microsoft는 자동 입력 전에 사용자를 인증하는 데 필요한 값을 인식하며, 향후 릴리스에서 Microsoft Edge에 이 기능을 추가할 예정입니다.

## <a name="can-using-a-password-manager-impact-my-privacy"></a>암호 관리자를 사용한다면 개인 정보 보호에 영향을 줄 수 있나요?

아니요, 저장된 암호에 대한 액세스를 보호하는 단계를 이행하는 경우에는 아닙니다.

일부 광고주가 저장된 암호로 사용자를 고유하게 식별하고 추적하는 데 사용하는 알려진 악용 사례가 있습니다.  [광고 대상 사용자가 브라우저의 암호 관리자에서 데이터를 끌어오고 있습니다](https://www.theverge.com/2017/12/30/16829804/browser-password-manager-adthink-princeton-research)에서 자세한 내용을 알아보세요. 브라우저에서는 이  [개인 정보 문제](https://bugs.chromium.org/p/chromium/issues/detail?id=798492)를 완화하기 위한 조치를 취했습니다.PasswordValueGatekeeper 클래스를 사용하여 브라우저가 로드될 때 자동으로 입력하도록 구성된 경우에도 암호 필드 데이터에 대한 액세스를 제한할 수 있습니다.

이 사용자 정보 수집 위협은 선택적인 edge://flags/#fill-on-account-selec 기능의 사용을 설정하여 쉽게 완화할 수 있습니다. 이 기능은 사용자가 자격 증명을 명시적으로 선택한 후에만 암호를 양식 필드에 추가할 수 있도록 허용하여 사용자가 암호를 받는 대상을 계속 인식할 수 있게 합니다.

## <a name="see-also"></a>참고 항목

[Microsoft Edge Enterprise 방문 페이지](https://www.microsoft.com/edge/business/download)

[Windows 10에서 비즈니스용 Chrome보다 Microsoft Edge가 더 안전한 방법](/DeployEdge/ms-edge-security-for-business)
