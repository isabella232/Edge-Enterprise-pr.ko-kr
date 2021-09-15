---
title: Microsoft Edge 및 Enterprise State Roaming
ms.author: kvice
author: dan-wesley
manager: laurawi
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge 및 Enterprise State Roaming
ms.openlocfilehash: 34ee5bf7970834a2e2211db9e2c0bc6ae99bcd6b
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "11980314"
---
# <a name="microsoft-edge-and-enterprise-state-roaming"></a>Microsoft Edge 및 Enterprise State Roaming

이 문서에서는 Enterprise State Roaming(ESR) 서비스에 대한 Microsoft Edge의 참여가 어떻게 플랫폼과 디바이스 간에 동기화가 더욱 잘 이루어지도록 변화하고 있는지 설명합니다.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.

## <a name="introduction"></a>소개

Windows 10에서 [Azure Active Directory(Azure AD)](/azure/active-directory/fundamentals/active-directory-whatis) 사용자에게는 사용자 설정 및 애플리케이션 설정 데이터를 클라우드와 안전하게 동기화하는 기능이 제공됩니다. [Enterprise State Roaming(ESR)](/azure/active-directory/devices/enterprise-state-roaming-overview)은 사용자에게 Windows 디바이스에서 통일된 환경을 제공하고 새 디바이스를 구성하는 데 필요한 시간을 단축합니다.

Chromium 플랫폼을 채택하는 Microsoft Edge의 일부로 이제 이 동기화 솔루션은 Windows Sync Framework에서 연결이 해제됩니다. 이는 ESR 서비스와 Microsoft Edge의 관계에 영향을 줍니다.

> [!IMPORTANT]
> 새 Microsoft Edge는 ESR 서비스에 참여하지 않습니다.

## <a name="whats-changing-with-microsoft-edge"></a>Microsoft Edge와 관련하여 무엇이 변경되나요?

새 Microsoft Edge를 사용하면 동기화 솔루션이 Windows 동기화 에코시스템과 연결되지 않습니다. 이를 통해 Windows 7, Windows 8.1, iOS, Android 및 macOS와 같은 모든 플랫폼에서 Microsoft Edge를 제공할 수 있습니다. 또한 Windows의 기본이 아닌 계정에 대한 동기화를 제공할 수도 있습니다. 이에 더해, Windows보다 더 빈번하고 유연한 릴리스 흐름으로 Microsoft Edge을 제공할 수 있습니다. (자세한 내용은 [다음 버전 Microsoft Edge를 지원하기 위한 Windows 업데이트](microsoft-edge-sysupdate-windows-updates.md)를 참조하세요. 이러한 요소는 모두 Microsoft Edge에서 ESR 서비스에 참여하는 데 필요한 사항을 다시 평가해야 한다는 것을 강조했습니다.

ESR은 Windows 디바이스에서 데이터를 처리하는 방법에 대한 약속을 제공하는 Windows 제품 서비스로 인식되어 있지만, Microsoft Edge 동기화는 Windows 디바이스를 넘어 확장됩니다. 또한 데이터가 이러한 디바이스 간에 로밍됨에 따라, ESR 컨텍스트에서 Microsoft Edge 동기화 제공을 정의하기가 어렵습니다. 동기화가 작동하고 관리되는 방식을 단순화하고, 강조되는 변경 내용을 수용하기 위해 ESR 서비스에서 Microsoft Edge를 가져오는 결정을 내려야 했습니다.

## <a name="does-this-mean-enterprises-will-lose-the-abilities-they-had-as-part-of-esr"></a>이로 인해 기언이 ESR의 일부로 보유했던 기능을 잃게 되나요?

아니요. Microsoft Edge는 ESR 서비스에서 제공하는 대부분의 기능을 계속 지원합니다.

### <a name="unified-experience-across-devices-and-new-device-configuration-time"></a>디바이스 간 통합 환경 및 새 디바이스 구성 시간

사용자가 Azure Active Directory(Azure AD 계정)를 사용하여 Windows 디바이스에 로그인하면 Microsoft Edge는 새 브라우저를 처음 시작할 때 해당 ID를 암시적으로 상속합니다.

사용자가 명시적으로 새 Microsoft Edge에서 동기화를 켜는 것에 동의한 후 브라우저는 즐겨찾기, 암호 및 기록과 같은 모든 브라우저 데이터를 동기화합니다. 이렇게 하면 디바이스 간에 통일된 환경이 제공되고 브라우저를 개인 설정하는 데 소요되는 시간이 줄어듭니다.

### <a name="separation-of-corporate-and-consumer-data"></a>기업 및 소비자 데이터 분리

조직은 자신의 데이터를 관리할 수 있으며, 소비자 클라우드 계정에 기업 데이터가 혼합되거나 기업 클라우드 계정에 소비자 데이터가 혼합되어 있지 않습니다.

### <a name="enhanced-security"></a>강화된 보안

Azure Information Protection을 사용하여 사용자가 Windows 10 디바이스를 종료하기 전에 데이터가 자동으로 암호화되며 사용되지 않는 데이터는 클라우드에서 암호화 상태로 유지됩니다. 모든 콘텐츠는 설정 이름과 같은 네임스페이스를 제외하고 클라우드에서 미사용 암호화 상태로 유지됩니다.

### <a name="monitoring"></a>모니터링

Microsoft에서는 조직의 설정을 동기화하는 사람과 Azure AD 포털과의 통합을 통해 어떤 디바이스에서 동기화가 이루어지는지에 대한 제어 및 가시성을 제공합니다. 이 기능은 향후 릴리스에서 구현될 예정입니다.

### <a name="management"></a>관리

관리자는 조직에서 동기화를 활성화할 수 있는 구성원을 제어할 수 있습니다. [Microsoft Edge 동기화 구성](microsoft-edge-enterprise-sync.md#configure-microsoft-edge-sync) 및 [동기화 그룹 정책](microsoft-edge-enterprise-sync.md#sync-group-policies)을 참조 하세요. 또한 사용자는 각 디바이스에 대해 동기화를 켜거나 끌 수 있을 뿐만 아니라 각 데이터 특성을 동기화에 대해 개별적으로 전환할 수도 있습니다.

### <a name="key-management"></a>키 관리

동기화 기능은 사용자 및 엔터프라이즈 관리자에 대해서만 동기화된 데이터를 보호하기 위해 Azure Information Protection(AIP)을 활용합니다. AIP는 클라우드 키 관리에 Microsoft 관리(기본값) 및 고유한 키 사용을 모두 지원합니다. 조직에서 사용하는 클라우드 키 관리 전략은 Microsoft Edge에서 투명하며 동기화 기능에 영향을 주지 않습니다.

> [!IMPORTANT]
> [HYOK(Hold Your Own Key)](/azure/information-protection/configure-adrms-restrictions) 및 Active Directory Rights Management Services는 지원되지 않습니다.

## <a name="summary-of-sync-attributes"></a>동기화 특성 요약

다음 데이터 특성은 새 버전의 Microsoft Edge를 처음 시작할 때 동기화됩니다.

- 즐겨찾기
- 암호
- 양식 채우기
- 기록
- 열린 탭(세션)
- 설정(기본 설정)
- 확장 프로그램

위의 특성 목록은 레거시 Microsoft Edge에서 동기화할 수 있는 특성과 다릅니다. (레거시 Microsoft Edge 설정에 대한 자세한 내용은 [Windows 10 로밍 설정](/azure/active-directory/devices/enterprise-state-roaming-windows-settings-reference)을 참조하세요.) 사용자는 Microsoft Edge 설정을 사용하여 이러한 특성을 선택적으로 사용하거나 사용하지 않도록 설정할 수 있습니다. 두 버전 간의 특성 차이가 있는 경우(예: 기록) 사용자에게 동기화 동의를 다시 제공하라는 메시지가 표시될 수 있습니다.

> [!NOTE]
> 레거시 Microsoft Edge와 달리 새 Microsoft Edge는 암호에 Windows 자격 증명 관리자를 사용하지 않으며, Internet Explorer 또는 Windows 자격 증명 관리자를 사용하는 다른 앱을 사용하여 암호를 동기화하지 않습니다.

## <a name="terms-of-service"></a>서비스 약관

Microsoft Edge 동기화에 대한 서비스 약관은 *edge://terms*의 Microsoft Edge에서 볼 수 있는 Microsoft 소프트웨어 라이선스의 적용을 받습니다.

## <a name="see-also"></a>기타 참조

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge 동기화](microsoft-edge-enterprise-sync.md)