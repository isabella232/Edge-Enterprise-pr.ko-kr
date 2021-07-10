---
title: Microsoft Edge를 사용하여 원치 않는 응용 프로그램으로부터 보호
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge를 사용하여 원치 않는 응용 프로그램으로부터 보호
ms.openlocfilehash: 68cd87e85408933212c4b25baa01a9ff8d994089
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2021
ms.locfileid: "11643104"
---
# <a name="protect-against-potentially-unwanted-applications-puas"></a>잠재적으로 원치 않는 응용 프로그램(PUA)으로부터 보호

이 문서에서는 Microsoft Edge 또는 Windows Defender Antivirus를 사용하여 원치 않는 응용 프로그램(PUA)을 차단할 수 있는 방법에 대해 설명합니다.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 80 이상에 적용됩니다.

## <a name="overview"></a>개요

이러한 응용 프로그램은 잠재적으로 원치 않는 응용 프로그램은 바이러스나 맬웨어로 간주되지 않지만 엔드포인트 성능이나 사용에 악영향을 미치는 엔드포인트에 대해 작업을 수행할 수 있습니다. 예를 들어 *Evasion software*은 현재 보안 제품의 감지를 피하려고 합니다. 이러한 유형의 소프트웨어를 사용하면 네트워크에서 실제 맬웨어에 감염 될 가능성이 커집니다. 또한 PUA는 신뢰도가 낮은 것으로 간주되는 응용 프로그램을 나타낼 수도 있습니다.

소프트웨어를 PUA로 분류하는 데 사용되는 기준에 대한 설명은 [잠재적으로 원치 않는 응용 프로그램](/windows/security/threat-protection/intelligence/criteria#potentially-unwanted-application-pua)을 참조하세요.

## <a name="protect-against-pua-with-microsoft-edge"></a>Microsoft Edge로 PUA 방지

Microsoft Edge(버전 80.0.361.50 이상)는 PUA 다운로드 및 관련 리소스 URL을 차단합니다.

Microsoft Edge에서 **잠재적으로 원치 않는 앱 차단** 기능을 사용하여 보호를 설정할 수 있습니다.

> [!NOTE]
> [Microsoft Edge Team 블로그 게시물](https://blogs.windows.com/msedgedev/2020/02/27/protecting-users-potentially-unwanted-apps/)에서는 이 새로운 기능에 대해 설명하고 잘못 레이블이 지정된 앱을 처리하거나 앱을 원치 않는 것으로 보고하는 방법을 설명합니다.

### <a name="to-enable-pua-protection"></a>PUA 보호 기능을 사용하기 위해서는 다음을 수행합니다.

1. 브라우저에서 **설정**을 엽니다.
2. **개인 정보 및 서비스**를 선택합니다.
3. 서비스 섹션에서 **Microsoft Defender SmartScreen**이 켜져 있는지 확인합니다. 그렇지 않으면, Microsoft Defender SmartScreen을 켭니다. 다음 스크린샷에 나와 있는 예제에서는 브라우저가 조직에 의해 관리 되 고 Microsoft Defender SmartScreen이 켜져 있음을 보여줍니다.

   ![설정에서 Microsoft Edge 켜기](./media/microsoft-edge-potentially-unwanted-apps/security-pua-setup.png)

4. **서비스** 구역에서 이전 스크린샷에 표시된 토글을 사용하여 **원치 않는 앱 차단**를 설정합니다.

   > [!TIP]
   > Windows Defender SmartScreen [데모 페이지](https://demo.smartscreen.msft.net/)중 하나에 대해 테스트하여 PUA protection의 URL 차단 기능을 안전하게 탐색할 수 있습니다.

Microsoft Edge가 PUA를 감지하면 다음 스크린샷과 같은 메시지가 표시됩니다.

   ![Microsoft Edge PUA 경고 메시지](./media/microsoft-edge-potentially-unwanted-apps/security-pua-msg.png)

### <a name="to-block-against-pua-associated-urls"></a>PUA 관련 URL 차단

Microsoft Edge에서 PUA protection을 켜면 Windows Defender SmartScreen은 PUA 관련 Url로부터 사용자를 보호합니다.

관리자는 Microsoft Edge와 Windows Defender SmartScreen이 함께 작업하여 PUA 관련 Url로부터 사용자를 보호하는 방법을 여러 가지로 구성할 수 있습니다. 자세한 내용은 다음을 참조하세요.

- [Windows에서 Microsoft Edge 정책 설정 구성](./configure-microsoft-edge.md)
- [SmartScreen 설정](./microsoft-edge-policies.md#smartscreen-settings)
- [SmartScreenPuaEnabled 정책](./microsoft-edge-policies.md#smartscreenpuaenabled)
- [Windows Defender SmartScreen 구성](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen)

관리자는 Microsoft Defender ATP (Advanced Threat Protection) 차단 목록을 사용자 지정할 수도 있습니다. Microsoft Defender ATP 포털을 사용하여 [IP 및 URL에 대한 지표를 생성 및 관리](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators#create-indicators-for-ips-and-urlsdomains-preview)할수 있습니다.

## <a name="protect-against-pua-with-windows-defender-antivirus"></a>Windows Defender Antivirus로 PUA 방지

[잠재적으로 원치 않는 응용 프로그램 검색 및 차단 문서](/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus#windows-defender-antivirus)에서는 PUA 보호를 사용하도록 Windows Defender 바이러스 백신을 구성하는 방법도 설명합니다. 다음 옵션 중 하나를 사용하여 보호를 구성할 수 있습니다.

- [Microsoft Intune](/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus#use-intune-to-configure-pua-protection)
- [Microsoft Endpoint Configuration Manager](/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus#use-configuration-manager-to-configure-pua-protection)
- [그룹 정책](/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus#use-group-policy-to-configure-pua-protection)
- [PowerShell cmdlet](/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus#use-powershell-cmdlets-to-configure-pua-protection)

Windows Defender는 엔드포인트에서 PUA 파일을 감지하면 파일을 격리하고 일반 위협 감지("PUA:"로 시작)와 같은 형식으로 사용자에게 알립니다([알림을 비활성화하지 않은 경우](/windows/security/threat-protection/windows-defender-antivirus/configure-notifications-windows-defender-antivirus)). 감지된 위협도 [Windows Security 앱 격리 목록](/windows/security/threat-protection/windows-defender-antivirus/windows-defender-security-center-antivirus#detection-history)에 나타납니다.

### <a name="pua-notifications-and-events"></a>PUA 알림 및 이벤트

관리자가 PUA 이벤트를 볼 수 있는 몇 가지 방법에는 다음과 같이 여러 가지가 있습니다.

- Windows 이벤트 뷰어, 하지만 Microsoft Endpoint Configuration Manager 또는 Intune에는 없습니다.
- 전자 메일은 PUA 검색에 대한 전자 메일 알림이 설정되어 있는 경우에만 사용할 수 있습니다.
- [Windows Defender 바이러스 백신](/windows/security/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus), 여기에서는 PUA 이벤트가 이벤트 ID 1116에 "맬웨어 방지 플랫폼이 맬웨어 또는 기타 잠재적으로 원치 않는 소프트웨어를 감지했습니다."라는 메시지와 함께 기록됩니다.

> [!NOTE]
> 사용자는 "*.exe가 Microsoft Defender SmartScreen에 의해 잠재적으로 원치 앱으로 차단되었습니다"라는 메시지를 보게 됩니다.

### <a name="allow-list-an-app"></a>앱 목록 허용

Microsoft Edge와 같이 Windows Defender 바이러스 백신은 실수로 차단되되거나 작업을 완료하는 데 필요한 파일을 허용하는 방법을 제공합니다. 이 경우 허용 파일 목록을 입력할 수 있습니다. 자세한 내용은 [구성 관리자에서 Endpoint Protection을 구성하는 방법](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#to-exclude-specific-files-or-folders)을 참조하여 특정 파일이나 폴더를 제외하는 방법에 대해 알아보세요.

## <a name="see-also"></a>참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [위협 방지](/windows/security/threat-protection/index)
- [동작, 추론 및 실시간 보호 구성](/windows/security/threat-protection/windows-defender-antivirus/configure-protection-features-windows-defender-antivirus)
- [차세대 보호](/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)
- [Chromium 기반 Microsoft Edge, 버전 79에 대한 보안 기준](https://techcommunity.microsoft.com/t5/microsoft-security-baselines/security-baseline-final-for-chromium-based-microsoft-edge/ba-p/1111863)