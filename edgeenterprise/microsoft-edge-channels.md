---
title: Microsoft Edge 채널 개요
ms.author: srugh
author: RyanHechtMSFT
manager: seanlynd
ms.date: 09/23/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge 채널 개요
ms.openlocfilehash: dd65d932950be90d3d9278fa41ae843335b2074d
ms.sourcegitcommit: 8e5294e82cf62abc916cfd24692f55925330d42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2021
ms.locfileid: "12037191"
---
# <a name="overview-of-the-microsoft-edge-channels"></a>Microsoft Edge 채널의 개요입니다.

다음 버전의 Microsoft Edge의 혜택 중 하나는 Microsoft는 정기적으로 새로운 기능을 제공할 수 있다는 점입니다. 그러나 관리자가 조직의 사용자에게 Microsoft Edge를 배포하는 경우 사용자가 새 기능을 사용할 수 있는 빈도를 보다 강력하게 제어할 수도 있습니다. Microsoft에서는 채널이라고 하는 네 가지 옵션을 제공하여 Microsoft Edge가 새 기능으로 업데이트되는 빈도를 제어할 수 있습니다. 네 가지 옵션에 대한 개요는 다음과 같습니다.

각 채널에 대한 지원에 대한 자세한 내용은 [Microsoft Edge 수명 주기](/deployedge/microsoft-edge-support-lifecycle)를 읽어 보세요.
  
> [!NOTE]
> 이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.

## <a name="channel-overview"></a>채널 개요

|채널|기본 목적|새로운 기능으로 업데이트되는 빈도|지원 여부|
|:---:|---|:---:|:---:|
|[안정](#stable-channel)|광범위한 배포|~4주|예|
|[Extended Stable](#extended-stable-channel)|더 긴 릴리스 주기에 맞춰진 안정을 위한 엔터프라이즈 릴리스 옵션 |~8주|예|
|[Beta](#beta-channel)|조직의 대표 유효성 검증|~4주|예|
|[Dev](#dev-channel)|계획 및 개발|매주|아니요|
|[Canary](#canary-channel)|최첨단 콘텐츠|매일|아니요|

사용자에게 배포하기로 결정한 업데이트 채널은 사용자가 활용하는 기간 업무(기간 업무) 응용 프로그램의 수와 업데이트된 버전의 응용 프로그램을 사용할 때 테스트해야 하는지 여부 등 몇 가지 요소에 따라 Microsoft Edge. 이러한 결정을 내리는 데 도움이 되도록 Microsoft Edge에 사용할 수 있는 네 가지 업데이트 채널에 대한 다음 정보를 검토하세요.

### <a name="stable-channel"></a>안정 채널

안정 채널은 조직 내 광범위한 배포를 위한 것이며, 대부분의 사용자가 사용해야 하는 채널입니다. 이는 채널 중 가장 안정적인 채널이며 이전 베타 채널 릴리스에서 사용할 수 있는 기능 집합의 안정화 결과입니다. 새로운 기능은 4주마다 제공됩니다. 필요한 경우 보안 및 품질 업데이트가 제공됩니다. 안정 채널의 릴리스는 채널에서 다음 릴리스를 사용할 수 있을 때까지 서비스됩니다.

### <a name="beta-channel"></a>Beta 채널

Beta 채널은 조직에서 대표적인 샘플 사용자 집합에 대한 프로덕션 배포를 위한 것입니다. 지원되는 릴리스이며, 이 채널의 다음 릴리스를 사용할 수 있을 때까지 Beta에서 각 릴리스가 서비스됩니다. 이를 통해 사용자 환경에서 작업이 제대로 작동하는지 확인할 수 있으며, 릴리스 전에 안정 채널로 게시하기 전에 문제가 발생하는 경우 문제를 해결할 수 있는 좋은 기회입니다. 새로운 기능은 4주마다 제공됩니다. 필요한 경우 보안 및 품질 업데이트가 제공됩니다.

### <a name="dev-channel"></a>Dev 채널

Dev 채널은 Microsoft Edge의 최신 기능을 사용하여 계획하고 개발하는 데 도움을 주기 위해 Canary 채널보다 높은 품질을 제공합니다. 이를 통해 다음에 릴리스되는 항목을 조기에 확인하고 다음 Beta 릴리스를 준비할 수 있습니다.

### <a name="canary-channel"></a>Canary 채널

Canary 채널은 매일 제공되며 모든 채널의 최첨단에 위치합니다. 새로운 투자에 액세스하려는 경우 여기에 먼저 표시됩니다. 이 케이던스의 특성으로 인하여 문제가 발생하여 Canary 릴리스를 활용하는 경우 다른 채널을 나란히 설치할 수 있습니다.

### <a name="extended-stable-channel"></a>확장 안정 채널

미리 보기 채널(Canary, Dev 및 Beta)과 달리 확장된 안정 채널은 별도의 브라우저 응용 프로그램으로 사용할 수 없습니다. 대신 더 길고 8주간의 주 릴리스 주기(안정에 있는 4주 주 릴리스 주기와 반대)에 맞춰진 Microsoft Edge Stable 응용 프로그램의 엔터프라이즈 릴리스 옵션입니다. 4주 릴리스 주기에 안정을 자동으로 업데이트하는 것이 권장되는 반면, 확장된 안정은 새 브라우저 버전을 테스트하고 유효성을 검사하는 데 더 긴 일정이 필요할 수 있는 조직에 보다 효과적으로 지원하기 위해 존재합니다.

Microsoft Edge Stable에 대한 8주 "확장된 안정" 릴리스 주기 옵션은 Microsoft Edge 94부터 조차도 번호가 매기기 릴리스에 맞춰진 누적 기능 업데이트를 제공합니다. __ 홀수 릴리스의 모든 기능 업데이트는 후속 even-numbered 릴리스의 일부로 패키지화 및 전달됩니다. 예를 들어 조직에서 Microsoft Edge 94와 함께 8주 "확장된 안정" 릴리스 주기를 선택하는 경우 Microsoft Edge 96, Microsoft Edge 98과 같은 후속 기능 업데이트를 받게 됩니다. 기능 업데이트는 선택한 릴리스 주기에 따라 패키지 및 새 버전 릴리스와 함께 제공되는 반면, 중요한 보안 패치 및 수정은 브라우저 보안을 유지하기 위해 선택한 릴리스 옵션과는 독립적으로 필요한 경우 제공됩니다. 고객은 수시로 확장 안정 릴리스 옵션에 옵트인할 수 있으며 다음 확장 안정 릴리스에 적용됩니다.

![안정 및 확장 Microsoft Edge 주기 옵션을 비교하는 예제입니다.](./media/microsoft-edge-channels/extended-stable-explainer.png)

#### <a name="opting-in-to-the-extended-stable-release-cadence"></a>확장된 안정 릴리스 케이던스에 옵트인

##### <a name="opting-in-to-extended-stable-on-windows-with-automatic-updates-recommended"></a>자동 업데이트를 사용하여 Windows 안정 확장에 옵트인(opt in)(권장)

자동 업데이트 Microsoft Edge 그룹 정책 개체를 사용하여 확장된 안정 릴리스 케이던스에 옵트인할 수 있습니다. [최신 그룹](/DeployEdge/configure-microsoft-edge#1-download-and-install-the-microsoft-edge-administrative-template) 정책 관리 템플릿을 다운로드하고 설치하는 Microsoft Edge 자세한 내용은 이 가이드를 따르세요.

1. 로컬 그룹 정책 편집기를 열고 _컴퓨터 구성>관리 템플릿>Microsoft Edge 업데이트>응용 프로그램>Microsoft Edge>_ 로 이동합니다.
2. 대상 **채널 다시 지정을 선택한** 다음 사용 을 **선택합니다.**
3. 옵션 **아래**정책 드롭다운 목록에서 **"확장된** 안정"을 선택합니다.

현재 설치된 장치보다 버전 번호가 큰 확장 안정 채널에 대한 다음 업데이트가 릴리스되면 Microsoft Edge 채널로 자동으로 업데이트됩니다. 버전 문자열이 `edge://settings/help` 으로 표시될 경우 다른 채널을 실행 중입니다.

> [!NOTE]
> 확장된 안정에 옵트인(Opt-in)은 현재 장치에 설치된 버전보다 더 큰 버전 번호(주 또는 부)가 있는 확장된 안정 채널에 새 업데이트가 있는 경우 적용됩니다. 최신 버전의 Microsoft Edge 안정된 안정에 옵트인(opt in)하는 경우 다음 패치 또는 업데이트와 함께 Microsoft Edge.
>
> 기본적으로 Microsoft Edge 다운그레이드되지 않습니다. 현재 홀수 버전의 Microsoft Edge Stable를 실행 중인 경우 Extended Stable에 옵트인(opt in)을 하면 다음 100일까지 업데이트를 받지 Microsoft Edge 있습니다.
>
> 모든 디바이스가 특정 버전의 Extended Stable로 시작되도록 하려는 경우 롤백이 설정된 MSI로 해당 특정 버전의 Edge Stable를 배포할 수 있습니다. 예를 들어 Extended Stable 94로 시작하지만 일부 장치가 이미 Stable 95로 업데이트된 경우 롤백이 사용하도록 설정된 Edge 94의 MSI를 배포할 수 있습니다. 롤백이 사용하도록 설정된 Edge MSIS를 배포하는 방법에 대한 자세한 내용은 롤백 [가이드 를 참조하세요.](/DeployEdge/edge-learnmore-rollback)

##### <a name="opting-in-to-extended-stable-on-windows-via-intune"></a>Intune을 통해 Windows 안정 확장에 옵트인

Microsoft Edge 관리 템플릿은 관리 센터의 로컬 그룹 정책 개체와 Microsoft Endpoint Manager 수 있습니다. [Intune을 통해 사용자 Microsoft Edge 가이드를 따르세요.](/mem/intune/configuration/administrative-templates-configure-edge) 

"**대상 채널에 대한**" 설정은 " Microsoft Edge 업데이트 >_응용_프로그램>Microsoft Edge 하위폴더에서 찾을 수 있습니다. "Extended**Stable"로 설정해야**합니다. 

현재 설치된 장치보다 버전 번호가 큰 확장 안정 채널에 대한 다음 업데이트가 릴리스되면 Microsoft Edge 채널로 자동으로 업데이트됩니다. 버전 문자열이 `edge://settings/help` 으로 표시될 경우 다른 채널을 실행 중입니다.

##### <a name="opting-in-to-extended-stable-on-windows-via-configuration-manager"></a>Configuration Manager를 통해 Windows 안정 확장에 옵트인

[Configuration Manager에서](/mem/configmgr/apps/deploy-use/deploy-edge#update-microsoft-edge) Microsoft Edge 동기화하고 승인하는 방법에 대한 자세한 내용은 Configuration Manager를 Microsoft Edge 가이드를 참조하세요.

확장 안정 업데이트는 Stable, Beta 및 Dev 채널의 기존 업데이트와 유사하게 "Microsoft Edge" 제품 범주의 소프트웨어 라이브러리에 배포됩니다. 그러나 자체 브라우저 응용 프로그램에 적용되는 Beta 및 Dev와 달리 Extended Stable 업데이트는 안정된 응용 프로그램에 Microsoft Edge 적용됩니다. 따라서 Windows 클라이언트에서 안정적 업데이트 또는 확장 안정 업데이트를 적용할지 여부를 결정하기 위해 "대상 채널 다시 설정" 그룹 정책의 상태를 확인합니다. 정책이 구성되지 않은 경우 또는 "Stable"로 설정하면 안정된 업데이트가 적용됩니다. "Extended Stable"로 설정하면 Extended Stable 업데이트가 적용됩니다. 그룹 정책을 올바르게 설정하는 방법에 대한 지침은 자동 업데이트로 확장된 안정에 옵트인(opt in)하는 방법에 대한 위의 지침을 따릅니다. 

## <a name="flighting-pre-release-channels-in-your-organization"></a>조직의 플라이트 사전 릴리스 채널

"대상 채널 다시 지정" 그룹 정책을 사용하여 사용자가 두 번째 웹 브라우저 응용 프로그램을 사용하지 않고도 조직에서 Microsoft Edge 릴리스 전 채널을 원활하게 플라이트할 수 있습니다. 예를 들어 조직의 대표 샘플 집합에 대해 "대상 채널 다시 지정" 정책을 "베타"로 설정할 수 있습니다. 이러한 사용자가 Microsoft Edge 안정적이지 않고 베타 채널 릴리스를 실행하게 됩니다(심지어는 알지 못합니다!). 이렇게 하면 엔터프라이즈에서 다음 버전의 Microsoft Edge 수행하는 방법을 조기 파악하고 모든 것이 환경에서 예상대로 작동하는지 확인할 수 있습니다. 문제가 발생하는 사용자로부터 조기 신호를 받을 수 있으며 안정 채널에 릴리스가 게시될 때 이전에 수정될 수 있습니다. 사용자 문제 해결의 일부로 의 버전 문자열은 사용자의 채널이 기본 안정 채널과 다른지 `edge://settings/help` 알려 줄 것입니다.

> [!NOTE]
> Microsoft Edge "Beta" 및 "Dev" 채널을 빌드할 때 주 버전 번호가 "안정"보다 크기 때문에 "Beta" 또는 "Dev" 채널을 업데이트하고 안정된 채널로 되돌리려 할 경우 Microsoft Edge 롤백 기능이 필요합니다. [](/DeployEdge/edge-learnmore-rollback) "대상 채널 다시 지정"을 Stable로 다시 설정하면 최신 안정 릴리스의 버전 번호가 현재 디바이스에서 실행되고 있는 Microsoft Edge 버전 번호가 될 때까지 업데이트가 수신하지 않습니다.

## <a name="see-also"></a>참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [채널 다운로드](https://aka.ms/EdgeEnterprise)
