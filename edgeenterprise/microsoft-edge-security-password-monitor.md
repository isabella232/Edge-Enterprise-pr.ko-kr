---
title: 사용자에 대해 암호 모니터 자동 사용
ms.author: supalsul
author: dan-wesley
manager: tulasim
ms.date: 01/26/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 사용자에 대해 암호 모니터 자동 사용
ms.openlocfilehash: d1995735ac7558c1608d427aac70081d4afed3a0
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447282"
---
# <a name="password-monitor-auto-enabled-for-users"></a>사용자에 대해 암호 모니터 자동 사용

이 문서에서는 Microsoft Edge에서 선택한 사용자에 대해 암호 모니터를 설정하는 방법을 설명하고 관리자에게 모니터링 사용 방법을 제어하는 단계를 제공합니다.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 88 이상에 적용됩니다.

## <a name="introduction-benefits-and-availability"></a>소개, 이점 및 가용성

암호 모니터를 사용하면 Microsoft Edge 사용자가 온라인 누출에서 암호를 찾은 경우 이를 알려 온라인 계정을 보호할 수 있습니다. 악의적인 공격자들이 타사 앱 또는 웹 사이트에서 데이터를 도용하면 온라인 누출 또는 데이터 침해가 발생하게 됩니다. 자세한 내용은 Microsoft Research 블로그에서 [암호 모니터: Microsoft Edge의 암호 보호](https://www.microsoft.com/research/blog/password-monitor-safeguarding-passwords-in-microsoft-edge/) 문서를 참조하십시오.

### <a name="benefits"></a>장점

이러한 온라인 공격의 빈도와 범위가 이러한 종류의 보호를 갖는 것이 모든 사람에 대해 필요해지고 있습니다. Microsoft Edge에는 손상된 것으로 알려진 암호에 대해 사용자의 저장된 암호를 안전하게 확인하고 일치가 발견되면 경고하는 기본 제공 기능을 제공합니다.  

### <a name="availability"></a>사용 가능한 시기

암호 모니터는 1/21부터 안정 채널 버전 88에서 사용할 수 있습니다. 출시는 서서히 적용될 예정이니 몇 주가 걸릴 수 있습니다. 설정 **** 프로필 암호 페이지에 다음 메시지와 컨트롤이  >  ****  >  **** 표시됩니다.

:::image type="content" source="media/microsoft-edge-security-password-monitor/monitor-enable-option.png" alt-text="암호 모니터를 사용하도록 설정하는 옵션":::

## <a name="configure-group-policy-for-password-monitor"></a>암호 모니터에 대한 그룹 정책 구성

이 기능은 [PasswordMonitorAllowed](./microsoft-edge-policies.md#passwordmonitorallowed) 그룹 정책을 통해 제어됩니다.

정책을 사용하도록 설정한 후에도 사용자는 기능을 켜는 데 동의해야 합니다. 기능에 사용자의 중요한 개인 데이터(암호)가 포함되어 있기 때문에 동의가 필요합니다. 그룹 정책을 사용하여 기능을 사용하지 않도록 설정한 경우 사용자는 이 설정을 오버라이드할 수 없습니다.  

## <a name="enabling-password-monitor-for-users"></a>사용자에 대해 암호 모니터 사용

암호 모니터 정책을 사용하도록 설정한 후 다양한 방법으로 사용자가 이 기능을 사용할 수 있습니다.

- 자동 사용. 자신의 작업 계정(Active Directory 또는 Azure Active Directory)을 사용하여 로그인하고 암호를 동기화하는 사용자는 이 기능에 대해 자동으로 사용하도록 설정됩니다. 다음 스크린샷에 기능이 켜져 있는 경우 알림이 표시됩니다.

  :::image type="content" source="media/microsoft-edge-security-password-monitor/monitor-enabled-notice.png" alt-text="암호 모니터가 알림을 사용함":::

-  명시적 동의를 얻어야 합니다. 암호 동기화가 설정되지 않은 사용자에게 암호 모니터를 켜는 권한을 요청합니다. 다음 작업이 수행될 때 메시지가 표시될 것입니다.
   - 사용자가 새 암호를 저장하는 경우
 
     :::image type="content" source="media/microsoft-edge-security-password-monitor/monitor-save-pw-prompt.png" alt-text="암호를 저장하라는 메시지 표시":::

   - 사용자가 저장된 암호를 사용하여 브라우저에 로그인한 경우
  
     :::image type="content" source="media/microsoft-edge-security-password-monitor/monitor-after-signin.png" alt-text="로그인 후 확인 메시지":::
   
- 직접 활성화. 사용자는 언제든지 **설정 ** > **암호로** 이동하여 기능을 켜거나 끌 수 있습니다.

## <a name="user-scenarios-with-password-monitor-auto-enabled"></a>암호 모니터 자동 사용이 가능한 사용자 시나리오

다음 표에서는 암호 모니터가 자동으로 사용하도록 설정되는 시나리오와 사용자 장치에서 암호 모니터가 어떻게 작동할지 보여줍니다.

| 시나리오 | 기본 조건 | 영향 |
|--|--|--|
| 동기화가 설정된 1 | 동기화 설정<br>이전에 사용할 수 있는 기능: 아니요<br>동의 UI에 대한 응답: 없음 | 기본적으로 사용하도록 설정된 기능은 브라우저가 시작된 후 2분 후에 풍선형으로 표시됩니다.<br>- 그 이후에 동기화가 꺼져 있는 경우 기능이 사용하지 않도록 설정됩니다.<br>- 동기화를 변경하기 전에 기능이 꺼져 있는 경우 동기화는 기능에 더 이상 영향을 주지 않습니다.   |
| 동기화가 설정된 2 | 동기화 설정<br>이전에 사용할 수 있는 기능: 예<br>동의 UI에 대한 응답: 없음 | 기능은 사용자 선택과 동일하게 유지됩니다.  거품이 표시되지 않는지와 기능 값에 대한 동기화 변경에는 영향을 주지 않습니다.|
| 3 동기화 해제 | 동기화 해제<br>이전에 사용할 수 있는 기능: 아니요<br>동의 UI에 대한 응답: 없음 | 동기화가 해제되어 기능이 계속 비활성화됩니다.<br>- 이후 사용자가 기능을 변경하지 않고 동기화를 켜면 해당 기능이 사용하도록 설정되어 있으며 동기화가 켜진 후 2분 후에 자동 활성화 알림이 표시됩니다. <br> - 동기화가 다시 꺼져 있는 경우 기능이 사용하지 않도록 설정됩니다. <br>- 동기화를 켜기 전에 기능이 변경된 경우 동기화는 암호 모니터에 더 이상 영향을 주지 않습니다.  |  
| 동기화 해제된 4개 | 동기화 해제<br>이전에 사용할 수 있는 기능: 예<br>동의 UI에 대한 응답: 없음 | 기능은 사용자 선택과 동일하게 유지될 수 있으며 거품이 표시되지 않습니다. 또한 기능 값에 동기화 변경이 영향을 미치지 않습니다.  |

또한 다음에 대한 정책을 통해 제한된 작업 계정을 사용하여 사용자가 로그인한 경우 이 기능은 자동으로 사용되지 않습니다.

- 암호 모니터를 사용하지 않도록 설정  
- 암호 동기화를 사용할 수 없습니다.
- Microsoft 서버와 데이터 공유를 사용할 수 없습니다.

## <a name="frequently-asked-questions"></a>질문과 대답

### <a name="how-can-password-monitor-be-disabled-for-my-organization"></a>조직에서 암호 모니터를 사용하지 않도록 설정하는 방법

다음을 통해 조직의 암호 모니터를 사용하지 않도록 설정할 수 있습니다.
- PasswordMonitorAllowed 그룹 정책 사용
- 데이터가 동기화되고 Microsoft 서버로 전송되지 못합니다.

  > [!NOTE]
  > 암호 모니터는 사용자가 설정을 통해 기능을 켜는 데 명시적으로 동의한 경우 암호 동기화를 사용하지 않도록 설정한 경우에도 작동할 수 있습니다.

### <a name="what-happens-if-a-user-for-whom-the-feature-has-been-auto-enabled-turns-password-monitor-off-via-settings"></a>기능을 자동으로 사용하도록 설정한 사용자가 설정을 통해 암호 모니터를 끄면 어떻게 하나요?

사용자 설정이 그대로 유지되어 해당 사용자에 대해 기능이 비활성화된 상태로 유지됩니다. 그러나 이전에 동의 프롬프트에 응답한 적이 없는 경우 동의 대화 상자가 다시 표시될 수 있습니다.

## <a name="see-also"></a>참고 항목

- [Microsoft Edge Enterprise 방문 페이지](https://aka.ms/EdgeEnterprise)