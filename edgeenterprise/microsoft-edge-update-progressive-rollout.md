---
title: Microsoft Edge Stable 채널 업데이트를 위한 점진적 배포
ms.author: aguta
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge Stable 채널 업데이트를 위한 점진적 배포
ms.openlocfilehash: bdcefdc118125d67057fa77513bd732cff6882e3
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642294"
---
# <a name="progressive-rollouts-for-microsoft-edge-stable-channel-updates"></a>Microsoft Edge Stable 채널 업데이트를 위한 점진적 배포

Microsoft Edge 83 릴리스부터 며칠 동안 Microsoft Edge Stable 채널에 대한 주요 업데이트를 점진적으로 배포할 예정입니다. 이 점진적 배포를 통해 업그레이드를 모니터링하고 조직 전체에서 브라우저를 안전하게 업데이트할 수 있습니다.

> [!NOTE]
> 이는 Microsoft Edge Stable 채널 버전 83 이상에 적용됩니다.

## <a name="why-do-we-need-progressive-rollout"></a>점진적 배포가 필요한 이유는 무엇입니까?

며칠 동안 업데이트 상태를 면밀히 모니터링하고 업데이트를 배포하면 새 업데이트에서 발생할 수 있는 문제의 영향을 제한할 수 있습니다. Microsoft Edge 릴리스 83에서는 모든 Windows 7, Windows 8 및 8.1 및 Windows 10 버전의 Microsoft Edge에 대해 점진적 배포가 사용 설정됩니다. Mac에서의 Microsoft Edge도 준비되는대로 지원될 것입니다.

## <a name="how-will-the-updates-work"></a>업데이트는 어떻게 작동되나요?

각 Microsoft Edge 설치에는 업그레이드 값이 할당됩니다. 점진적 배포를 시작할 경우 장치의 값이 업그레이드 값 범위에 포함되면 업데이트를 확인할 수 있습니다. 배포가 진행되면 (며칠 이내에) 최종적으로 모든 사용자가 업데이트를 받게 됩니다. 중요 보안 수정 사항이 포함된 브라우저 업데이트는 중요 보안 수정 사항이 없는 업데이트에 비해 배포 흐름이 더 빠릅니다. 이러한 조치는 취약성으로부터 즉각적인 보호를 보장하기 위해 수행됩니다.

## <a name="how-does-this-affect-enterprises"></a>이것이 기업에 어떤 영향을 미치나요?

Microsoft Edge 아티팩트는 Microsoft Intune, WSUS(Windows Server Update Service) 및 구성 관리자와 같은 여러 메커니즘을 사용하여 기업에 배포됩니다. 이러한 배포 도구는 점진적 배포와 관련해 다른 방식으로 작동합니다.

- Microsoft Intune을 통해 배포를 관리하는 기업은 자동 업데이트를 위해 등록됩니다. 점진적 배포가 사용되고 모든 사용자는 며칠 후에 업데이트를 볼 수 있습니다.
- WSUS(Windows Server Update Services) 또는 구성 관리자를 통해 배포를 관리하는 기업은 자동 업데이트에 등록되지 않습니다. 관리자는 처음부터 사용할 수 있는 업데이트를 관리하고 적용합니다. 점진적 배포는 이 프로세스에 영향을 미치지 않습니다.

사용자 의견, 응용 프로그램 내 피드백 버튼을 통해 귀중한 피드백을 공유하거나 우려 사항이나 질문이 있는 경우 댓글 아래에 공유하세요.

## <a name="see-also"></a>참고 항목

- [Microsoft Edge Enterprise 방문 페이지](https://aka.ms/EdgeEnterprise)
