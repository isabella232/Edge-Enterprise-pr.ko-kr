---
title: Microsoft Defender SmartScreen에 대한 Microsoft Edge 지원
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 02/05/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Defender SmartScreen에 대한 Microsoft Edge 지원
ms.openlocfilehash: 2de93b4ebe26b4a90592f7ee9143f6f775b682ce
ms.sourcegitcommit: c290b0b0fa6b7d7f94dcdfdda91302da733326ec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "11314691"
---
# Microsoft Defender SmartScreen에 대한 Microsoft Edge 지원

이 문서에서는 Microsoft Defender SmartScreen 사용의 이점에 대해 설명하고 작동 방법을 설명하고 Microsoft Edge 기능을 구성하는 방법을 설명합니다.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.

Microsoft Defender SmartScreen은 웹을 검색하는 동안 Microsoft Edge에서 안전을 유지하기 위해 사용하는 서비스입니다. Windows Defender SmartScreen은 피싱 공격에 가담하거나 포커스 공격을 통해 맬웨어의 배포를 시도할 수 있는 웹 사이트에 대해 초기 경고 시스템을 제공합니다. 자세한 내용은 [비디오: Microsoft Edge에서 보안 검색](microsoft-edge-video-security-smartscreen.md)을 참조하세요.

> [!NOTE]
> Windows 10 버전 1703 이전에는 이 기능을 브라우저 내에서 사용할 경우 SmartScreen 필터, 브라우저 외부에서 사용할 경우 Microsoft SmartScreen으로 불렀습니다.

## Microsoft Defender SmartScreen 이점

Microsoft Defender SmartScreen은 다음 목록으로 요약되어 있는 몇 가지 이점을 제공합니다. 해당 이점에 대한 자세한 내용은 [Microsoft Defender SmartScreen 설명서](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-overview#benefits-of-windows-defender-smartscreen)를 참조하세요. 이점은 다음과 같습니다.

- 피싱 및 맬웨어 방지 지원
- 신뢰도 기반 URL 및 앱 보호
- 운영 체제 통합
- 개선된 추론 및 진단 데이터
- 그룹 정책 및 Microsoft Intune을 통한 관리
- 잠재적으로 원치 않는 응용 프로그램에 연결된 URL 차단

## Microsoft Defender SmartScreen 작동 방식의 이해

다양한 입력 사항이 Microsoft Defender SmartScreen 경고에 영향을 미칩니다. 사용자 의견, 데이터 공급자, 지능형 모델을 비롯하여 다양한 출처로부터 데이터를 받습니다. 해당 데이터는 잠재적인 유해 콘텐츠를 식별하는 데 유용합니다. Microsoft Defender SmartScreen은 또한 다운로드 앱 또는 앱 설치 관리자가 유해한 요소인지 검사합니다. 두 경우 모두에서 Microsoft Defender SmartScreen은 의심스러운 콘텐츠에 대해 사용자에게 적절히 경고를 보냅니다.

### 사이트 분석

Microsoft Defender SmartScreen은 다음을 통해 잠재적인 유해 사이트 여부를 확인합니다.

- 방문 웹 페이지를 분석하여 의심스러운 동작으로 표시합니다.
- 방문 사이트를 보고된 피싱 사이트의 동적 레코드와 대조합니다.

Microsoft Defender SmartScreen이 페이지를 유해한 것으로 확인한 경우 해당 사이트가 안전한 것으로 보고 되었음을 사용자에게 알리는 경고 페이지를 표시합니다. 다음 스크린샷은 사용자가 유해 웹 사이트 열 때 표시되는 Microsoft Defender SmartScreen 경고 페이지의 예시입니다.

![외부 사이트의 링크에 대한 Microsoft Defender SmartScreen 블록 페이지](media/microsoft-edge-security-smartscreen/microsoft-edge-smartscreen-warning.png)

사용자는 경고 메시지 내에서 사이트를 안전한 것으로 보고 또는 안전하지 않은 것으로 보고하는 옵션을 받습니다. 자세한 내용은 [사이트를 보고하는 방법](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-set-individual-device#how-users-can-report-websites-as-safe-or-unsafe)을 참조하세요.

### 파일 분석

Microsoft Defender SmartScreen은 다운로드 트래픽, 다운로드 기록, 지난 바이러스 백신 결과 및 URL 신뢰도 등의 다양한 기준으로 다운로드 앱 또는 앱 설치 관리자가 유해한 요소인지 여부를 확인합니다.

- 안전한 신뢰도의 파일은 어떠한 알림 없이 다운로드할 수 있습니다.  
- 유해한 신뢰도의 파일은 파일이 안전하지 않고 유해한 것으로 보고되었음을 알리는 경고가 표시됩니다. 다음 스크린샷은 유해한 파일에 대한 경고 예시입니다.

  ![유해한 신뢰도의 파일에 대한 Microsoft Defender SmartScreen 차단 알림](media/microsoft-edge-security-smartscreen/ms-edge-smartscreen-known-malicious.png)

- 알 수 없는 파일에는 알려진 발자국 및 경고 알림이 없는 다운로드임을 알리는 경고가 표시됩니다. 다음 스크린샷은 알 수 없는 파일에 대한 경고 예시입니다.

  ![알 수 없는 신뢰도의 파일에 대한 Microsoft Defender SmartScreen 차단 알림](media/microsoft-edge-security-smartscreen/ms-edge-smartscreen-unknown-malicious.png)

알 수 없는 모든 프로그램이 유해한 것은 아닙니다. 알 수 없는 경고는 특히 경고가 예상치 않게 표시된 경우 이를 필요로 하는 사용자를 위한 컨텍스트 및 지침을 제공하기 위한 것입니다.

  ![유해한 신뢰도를 가지는 파일의 유지](media/microsoft-edge-security-smartscreen/ms-edge-smartscreen-unknown-malicious-keep.png)

하지만 사용자는 계속 다운로드할 수 있으며 **... | 유지 | 자세히 보기 | 계속 유지**를 클릭하여 응용 프로그램을 실행할 수 있습니다.

> [!TIP]
> **엔터프라이즈 고객을 위한 참고** Microsoft Defender SmartScreen은 기본적으로 사용자가 경고를 무시할 수 있도록 허용합니다. 해당 사용자 조작은 잠재적으로 위험할 수 있으므로 [권장되는 그룹 정책 설정](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-available-settings#recommended-group-policy-and-mdm-settings-for-your-organization)을 검토하는 것이 좋습니다.

당사의 [데모 사이트](https://demo.smartscreen.msft.net/)를 사용하여 다양한 시나리오별로 Microsoft Defender SmartScreen의 대응 방법을 확인할 수 있습니다.

## Microsoft Defender SmartScreen 및 사용자 개인 정보 보호

Microsoft Defender SmartScreen은 사용자가 신뢰도 검사 시스템을 사용하여 인터넷을 검색하는 동안 사용자를 보호합니다. Microsoft Edge에서는 URL 또는 파일에 대한 관련 정보를 Microsoft Defender SmartScreen 서비스에 전달하여 신뢰도 검사를 시작합니다. 검사는 웹 사이트 또는 파일을 유해한 것으로 알려진 사이트 및 파일의 동적 목록과 비교하여 진행합니다. Microsoft Defender SmartScreen 서비스에 대한 모든 요청은 TLS 암호화로 이루어집니다. 해당 서비스는 신뢰도 검사의 결과를 반환하며 이는 Microsoft Edge로 이어져 해당 사이트 또는 파일에 대해 경고를 표시할 수 있습니다. 해당 결과는 장치에 로컬로 저장됩니다.

Microsoft Defender SmartScreen 서비스는 신뢰도 검사에 대한 데이터를 저장합니다. 새로운 사이트가 식별되면 서비스에서는 알려진 유해 URL 및 파일의 동적 데이터베이스에 해당 사이트를 추가합니다. 이 데이터는 보안 Microsoft 서버에 저장되며 Microsoft 보안 서비스에만 사용됩니다. 이 데이터는 어떤 방식으로도 사용자를 식별하거나 대상으로 지정하는 데는 사용되지 않습니다. 검색 캐시를 지우면 로컬로 저장된 Microsoft Defender SmartScreen URL 데이터가 모두 제거됩니다. 다운로드 기록을 지우면 파일 다운로드에 대한 로컬로 저장된 SmartScreen 데이터가 모두 제거됩니다.

Microsoft Edge의 Microsoft Defender SmartScreen 및 개인 정보 보호에 대한 자세한 내용은 [Microsoft Edge 개인 정보 보호 백서](https://docs.microsoft.com/microsoft-edge/privacy-whitepaper#smartscreen)를 참조하세요.

## 관리자를 위한 Microsoft Defender SmartScreen 설정

관리자는 그룹 정책, Microsoft Intune 또는 MDM (모바일 장치 관리) 설정을 사용하여 Microsoft Defender SmartScreen을 구성할 수 있습니다. Windows Defender SmartScreen을 설정하는 방법에 따라 사용자에게 경고 페이지를 표시하고 해당 사이트를 계속 사용할 수 있도록 설정하거나 사이트를 완전히 차단할 수 있습니다.

### 그룹 정책을 사용하여 Microsoft Defender SmartScreen 설정

SmartScreen 정책의 전체 목록은 [Microsoft Defender SmartScreen 설정](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#smartscreen-settings)을 참조하세요.

### MDM을 사용하여 Microsoft Defender SmartScreen 설정

자세한 내용은 다음을 참조하세요.

- [Microsoft Defender SmartScreen에 대한 Windows Intune 설정](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#windows-defender-smartscreen-settings)
- [MDM 정책 설정](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#windows-defender-smartscreen-settings)

## 사용자를 위한 Microsoft Defender SmartScreen 설정

Microsoft Defender SmartScreen은 기본적으로 Microsoft Edge에 대해 설정되어 있습니다. Microsoft Defender SmartScreen을 해제하려면 *edge://settings/privacy > 서비스 > Microsoft Defender SmartScreen*으로 이동합니다. 해당 설정은 장치의 Microsoft Edge 설치와 연결된 모든 프로필에 대해 동일합니다. 해당 설정은 장치 간에 동기화되지 않습니다. 이 설정은 InPrivate 브라우징 및 게스트 모드에 적용됩니다. 조직이 설정한 그룹 정책을 통해 장치를 관리하는 경우 해당 구성은 *edge://settings/privacy*에 반영됩니다.

> [!NOTE]
> 사용자는 Microsoft Defender SmartScreen을 그룹 정책이나 MDM이 차단하도록 구성하지 않는 한 개별 장치에 설정할 수 있습니다. 자세한 내용은 [개별 장치에서 Microsoft Defender SmartScreen 설정 및 사용](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-set-individual-device)을 참조하세요.

## 질문과 대답

### 신뢰도 검사 시스템은 어떻게 작동하나요?

웹을 검색하면 Microsoft Defender SmartScreen이 웹 사이트 및 다운로드를 상위 트래픽, 위험 또는 알 수 없음으로 분류합니다. 상위 트래픽은 Microsoft Defender SmartScreen이 신뢰할 수 있는 것으로 판단한 사용량이 많은 사이트입니다. 위험으로 표시된 사이트로 이동하면 Microsoft Defender SmartScreen에서 사용자가 사이트에 액세스하는 것을 즉시 차단합니다. 알 수 없는 사이트로 이동하면 Microsoft DefenderSmartScreen에서 해당 신뢰도를 확인하여 사이트에 액세스할 수 있는지 여부를 확인합니다.

## 참고 항목

- [Microsoft Edge Enterprise 방문 페이지](https://aka.ms/EdgeEnterprise)
- [비디오: Microsoft Edge의 보안 검색](microsoft-edge-video-security-smartscreen.md)
- [Windows Defender SmartScreen 개요](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-overview)
- [위협 방지](https://docs.microsoft.com/windows/security/threat-protection/index)
- [잠재적으로 원치 않는 응용 프로그램(PUA)으로부터 보호](https://docs.microsoft.com/DeployEdge/microsoft-edge-potentially-unwanted-apps)