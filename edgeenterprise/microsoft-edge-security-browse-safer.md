---
title: Microsoft Edge를 사용하여 더 안전하게 찾아보기
ms.author: pchiquini
author: dan-wesley
manager: robfranco
ms.date: 04/27/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 강화된 보안이 Microsoft Edge를 통한 안전한 검색을 지원하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 48a40a40a1741da1cc89a180535f4bb568060ba8
ms.sourcegitcommit: 592f6e40b13e28af588473b2a75c3ae697e5db2d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2022
ms.locfileid: "12505411"
---
# <a name="browse-more-safely-with-microsoft-edge"></a>Microsoft Edge를 사용하여 더 안전하게 찾아보기

이 문서에서는 Microsoft Edge가 웹에서 강화된 보안을 제공하는 방법을 설명합니다.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 98 이상에 적용됩니다.

## <a name="overview"></a>개요

Microsoft Edge는 웹을 검색하고 낯선 사이트를 방문할 때 추가적인 보호 계층을 제공하기 위해 강화된 보안 보호를 추가하고 있습니다. 웹 플랫폼은 JavaScript와 같은 강력한 기술을 사용하여 풍부한 브라우징 환경을 제공하도록 설계되었습니다. 반면, 악의적인 사이트를 방문할 경우 해당 기능은 더 많은 노출로 이어질 수 있습니다. 강화된 보안 기능을 통해 Microsoft Edge는 낯선 사이트에 보다 보수적인 보안 설정을 자동으로 적용하여 공격의 위험을 줄이고 사용자가 계속 탐색할 때 시간이 지남에 따라 적응합니다.

## <a name="defense-in-depth"></a>심층 방어

Microsoft Edge의 강화된 보안 기능은 JIT(Just-In-Time) JavaScript 컴파일을 사용하지 않도록 설정하고 브라우저에 대한 추가 운영 체제 보호를 활성화하여 메모리 관련 취약성을 완화합니다. 이러한 보호에는 [하드웨어 적용 스택 보호](https://techcommunity.microsoft.com/t5/windows-kernel-internals-blog/developer-guidance-for-hardware-enforced-stack-protection/ba-p/2163340) 및 [ACG(임의 코드 보호)](/microsoft-365/security/defender-endpoint/exploit-protection-reference?view=o365-worldwide#arbitrary-code-guard)가 포함됩니다.

이러한 변경 사항을 결합하면 악성 사이트가 패치되지 않은 취약성을 이용하여 실행 메모리에 쓰고 최종 사용자를 공격하는 것이 그 어느 때보다 어려워지기 때문에 '심층 방어'를 제공할 수 있습니다. Microsoft Edge Security 팀의 [블로그 게시물](https://microsoftedge.github.io/edgevr/posts/Super-Duper-Secure-Mode) 및 [Microsoft Edge 강화된 보안 소개](https://microsoftedge.github.io/edgevr/posts/Introducing-Enhanced-Security-for-Microsoft-Edge/)에서 실험 결과에 대해 자세히 알아볼 수 있습니다.

첫 번째 줄인 [Microsoft Edge의 보안 보호](/deployedge/ms-edge-security-for-business)에 대해 자세히 알아볼 수도 있습니다. 특히 [Microsoft Edge SmartScreen](/deployedge/microsoft-edge-security-smartscreen)이 피싱 사기 및 멀웨어 다운로드로부터 사용자를 보호하는 방법에 대해 자세히 알아볼 수 있습니다.

> [!NOTE]
> WASM(WebAssembly)을 사용하는 사이트는 현재 이 모드에서 지원되지 않습니다. WASM이 필요한 사이트에 액세스해야 하는 경우 [예외 사이트 목록](#exception-site-list)에 설명된 대로 WASM을 예외 사이트 목록에 추가하는 것이 좋습니다.

## <a name="whats-new-in-microsoft-edge-security-settings"></a>Microsoft Edge 보안 설정의 새로운 기능

Microsoft Edge는 **웹에서 보안 강화**를 통해 웹을 검색할 때 추가적인 보호 계층을 제공합니다.

다음 단계를 사용하여 추가된 보안을 구성하세요.

1. Microsoft Edge에서 **설정 및 기타** > **설정** > **개인 정보, 검색 및 서비스**로 이동합니다.
2. **보안**에서 **웹에서 보안 강화**가 사용하도록 설정되어 있는지 확인합니다.
3. 검색하기에 가장 적합한 옵션을 선택합니다.

다음 토글 설정을 사용할 수 있습니다.

- 토글 해제(기본값): 기능이 꺼져 있습니다.
- 토글 켜기 – 균형 조정(권장): Microsoft Edge는 사용자가 낯선 사이트를 방문할 때 추가 보안 보호를 적용하지만 일반적으로 방문하는 사이트에는 이러한 보호를 무시합니다. 이 조합은 공격자에 대한 실질적인 보호 수준을 제공하는 동시에 웹에서 사용자의 일반적인 작업에 대한 사용자 환경을 유지합니다.
- 토글 켜기 – 엄격: Microsoft Edge는 사용자가 방문하는 모든 사이트에 추가 보안 보호를 적용합니다. 사용자는 일반적인 작업을 수행하는 데 몇 가지 어려움이 있다고 보고할 수 있습니다.

다음 스크린샷은 보안 강화가 활성화되어 균형 잡힌 보안을 제공하도록 설정된 "웹에서 보안 강화" 구성 페이지를 보여 줍니다.

:::image type="content" source="media/microsoft-edge-security-browse-safer/browse-safer-enhance-security-dialog.png" alt-text="웹에서 균형 있는 보안을 구성하는 대화 상자입니다.":::

### <a name="how-balanced-mode-works"></a>"균형 조정" 모드가 작동하는 방법

균형 조정 모드는 특정 장치에서 사용자의 행동을 기반으로 하는 적응 모드이며, Microsoft는 웹 전반에 걸친 위험을 파악하여 사용자가 웹 플랫폼에 대한 전체 액세스를 가장 많이 사용하고 신뢰할 수 있는 사이트를 제공하는 동시에 새롭고 낯선 사이트에서 수행할 수 있는 작업을 제한합니다.

### <a name="how-strict-mode-works"></a>"엄격" 모드가 작동하는 방법

이름에서 알 수 있듯이 엄격 모드는 기본적으로 이러한 보안 보호를 모든 사이트에 적용합니다. 그러나 예외 사이트 목록에 사이트를 수동으로 추가할 수 있으며 엔터프라이즈 관리자 구성이 있는 경우 계속 적용됩니다. 엄격 모드는 일반 작업을 완료하기 위해 일정 수준의 구성이 필요할 수 있으므로 대부분의 최종 사용자에게 적합하지 않습니다.

### <a name="exception-site-list"></a>예외 사이트 목록

균형 조정 모드와 엄격 모드 모두에서 신뢰할 수 있는 친숙한 특정 웹 사이트에 대한 예외를 만들 수도 있습니다. 다음 단계를 사용하여 예외 목록에 사이트를 추가합니다.

1. Microsoft Edge에서 **설정 및 기타** > **설정** > **개인 정보, 검색 및 서비스**를 선택합니다.
2. **웹에서 보안 강화**가 켜져 있는지 확인합니다.
3. **웹에서 보안 강화**에서 **예외**를 선택합니다.
4. **사이트 추가**를 선택하고 전체 URL을 입력한 다음 **추가**를 선택합니다.

> [!NOTE]
> 단계(1-3)를 사용하여 **강화된 보안 예외** 사이트를 볼 수 있습니다. 사이트를 **편집**하거나 사이트를 **제거**하거나, 예외를 **모두 제거**할 수 있습니다.

다음 스크린샷은 보안 예외에 대한 설정 페이지를 보여 줍니다.

:::image type="content" source="media/microsoft-edge-security-browse-safer/browse-safer-enhanced-exceptions.png" alt-text="보안 예외를 구성하기 위한 설정 페이지":::

### <a name="enterprise-controls"></a>엔터프라이즈 컨트롤

엔터프라이즈 관리자는 그룹 정책 설정을 사용하여 "허용" 및 "거부" 목록을 만들어 특정 사이트를 방문할 때 사용자의 보안을 명시적으로 강화하거나 다른 사이트에 대한 모드를 비활성화하는 등 이 보안 기능을 구성할 수 있습니다. 정책의 전체 목록은 [Microsoft Edge 브라우저 정책 설명서](/deployedge/microsoft-edge-policies)를 참조하세요.

## <a name="user-experience-with-enhanced-security"></a>강화된 보안을 사용한 사용자 환경

사용자가 강화된 보안 기능을 설정한 후 Microsoft Edge가 특정 사이트에 대해 강화된 보안 기능을 적용할 때 URL 탐색 모음에 "보안 추가됨"이라는 단어가 포함된 배너가 표시됩니다.

:::image type="content" source="media/microsoft-edge-security-browse-safer/browse-safer-added-security-banner.png" alt-text="추가된 보안이 켜져 있음을 보여 주는 배너입니다.":::

배너를 선택하면 다음 플라이아웃이 표시됩니다. "이 사이트에 대한 보안 강화"를 전환하여 특정 사이트에 대해 강화된 보안을 수동으로 사용하거나 사용하지 않도록 설정할 수 있습니다. "이 사이트에 대한 강화된 보안" 토글을 변경하면 Microsoft Edge에서 해당 사이트를 예외 사이트 목록에 추가합니다. 다음 스크린샷은 사이트에 대해 꺼진 기능을 보여 줍니다.  

:::image type="content" source="media/microsoft-edge-security-browse-safer/browse-safer-enhanced-security-off.png" alt-text="강화된 보안 대화 상자가 꺼져 있습니다.":::

> [!NOTE]
> "이 사이트에 대한 보안 강화"는 설정 페이지에서 보안 강화가 설정된 경우에만 나타납니다.

## <a name="send-us-feedback"></a>피드백 보내기

"웹 보안 강화"를 위한 다음 버전에 대한 피드백을 받고자 합니다. 기대했던 대로 작동하지 않거나 변경 사항에 대해 공유할 의견이 있는 경우 의견을 듣고 싶습니다. Microsoft 지원에 문제를 보고하거나 피드백을 남길 수 있습니다. [TechCommunity 포럼](https://techcommunity.microsoft.com/t5/enterprise/bd-p/EdgeInsiderEnterprise)에도 피드백을 남길 수 있습니다.

## <a name="see-also"></a>참고 항목

- [비디오: Microsoft Edge의 보안 검색](microsoft-edge-video-security-smartscreen.md)
- [Super Duper 보안 모드](https://microsoftedge.github.io/edgevr/posts/Super-Duper-Secure-Mode/)
- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
