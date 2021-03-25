---
title: Microsoft Edge 구성 및 실험
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 02/20/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 구성 및 실험
ms.openlocfilehash: aef19fd9c119926a934a1ab00009a89ce2fe31fc
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447772"
---
# <a name="microsoft-edge-configurations-and-experimentation"></a>Microsoft Edge 구성 및 실험

이 문서에서는 Microsoft Edge와 ECS(실험 및 구성 서비스) 간의 상호 작용에 대해 설명합니다. Microsoft Edge는이 서비스와 통신하여 다양한 종류의 페이로드를 요청하고 받습니다. 이러한 페이로드에는 구성, 기능 출시 및 실험이 포함됩니다.

> [!IMPORTANT]
> 클라이언트가 `https://config.edge.skype.com`에 액세스할 수 있는지 확인하여 페이로드를 받을 수 있도록 합니다.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.

## <a name="configurations"></a>구성

구성은 제품 상태, 보안 및 개인 정보 규정 준수를 보장하기 위한 페이로드이며, (플랫폼 및 채널에 기반하여) 모든 사용자에게 동일한 가치를 제공하기 위한 것입니다. 이는 도메인 작업에 기능 플래그를 사용하도록 설정하기 위한 것일 수 있으며, 버그의 경우 기능 플래그를 사용하지 않도록 설정하는 데도 사용할 수 있습니다.

## <a name="controlled-feature-rollout"></a>제어된 기능 출시

CFR(제어된 기능 출시)은 기능을 수신하는 사용자 그룹의 크기를 천천히 늘리기 위한 절차입니다. 사용자 집단에서 임의로 선택된 하위 집합에 새 기능을 배포하여 기능의 영향을 측정하는 기능 없이 사용자 피드백을 동일한 크기의 컨트롤 그룹과 비교하는 것이 가능합니다.

## <a name="experiments"></a>실험

Microsoft Edge 빌드에는 아직 개발 중이거나 실험적인 기능이 있습니다. 실험은 CFR과 유사하지만 사용자 그룹의 크기는 새로운 개념을 테스트할 때보다 훨씬 작습니다. 이러한 기능은 기능을 출시하거나 실험을 마칠 때까지 기본적으로 숨겨집니다. 실험 플래그는 이러한 기능을 활성화 또는 비활성화하는 데 사용됩니다.

## <a name="about-the-ecs"></a>ECS 정보

앞의 모든 시나리오에서 이 서비스는 기능 플래그 값이 적용될 수 있도록 브라우저 클라이언트에 해당 값을 전달합니다. 업데이트에 따라 구성이 즉시 또는 사용자가 브라우저를 다시 시작할 때 적용됩니다.

Microsoft Edge와 이 서비스 간의 상호 작용은 [ExperimentationAndConfigurationServiceControl](./microsoft-edge-policies.md#experimentationandconfigurationservicecontrol) 정책의 설정에 따라 제어됩니다. 정책 설정을 다음과 같이 구성할 수 있습니다.

- 구성만 검색
- 구성 및 실험을 검색
- 서비스와 통신하지 않도록 설정

  > [!CAUTION]
  > 서비스와의 통신을 사용하지 않도록 설정할 경우 Microsoft가 적시에 심각한 버그에 응답하는 기능에 영향을 미칩니다.

## <a name="see-also"></a>기타 참조

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://www.microsoftedgeinsider.com/enterprise)
- [Microsoft Edge 설명서 방문 페이지](./index.yml)