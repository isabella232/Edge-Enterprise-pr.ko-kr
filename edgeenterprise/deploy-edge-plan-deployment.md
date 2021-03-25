---
title: Microsoft Edge 배포 계획
ms.author: collw
author: appcompatguy
manager: srugh
ms.date: 02/05/2021
audience: ITPro
ms.topic: procedural
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 배포 계획
ms.openlocfilehash: aae219bf44e78edabc02974a434d7d7efc1665eb
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447822"
---
# <a name="plan-your-deployment-of-microsoft-edge"></a>Microsoft Edge 배포 계획

이 문서에서는 엔터프라이즈 환경에서 Microsoft Edge를 배포하는 데 권장되는 방법에 대해 설명합니다.

>[!NOTE]
>이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.

다음 섹션에서는 Microsoft Edge 배포를 계획하기 위한 구체적인 지침을 제공합니다.

- [브라우저 환경 및 요구 사항 평가](#evaluate-your-existing-browser-environment-and-browser-needs)
- [Windows 10 장치가 준비되었는지 확인](#make-sure-your-windows-10-devices-are-ready)
- [배포 방법 선택](#determine-your-deployment-methodology)
- [사이트 검색 수행](#do-site-discovery)
- [채널 전략 선택](#determine-your-channel-strategy)
- [정책 식별 및 구성](#define-and-configure-policies)
- [앱 호환성 테스트](#do-app-compatibility-testing)
- [Microsoft Edge 파일럿](#deploy-microsoft-edge-to-a-pilot-group)
- [파일럿 평가](#validate-your-deployment)
- [엔터프라이즈에 Microsoft Edge 구축](#broad-deployment-of-microsoft-edge)

## <a name="evaluate-your-existing-browser-environment-and-browser-needs"></a>기존 브라우저 환경 및 브라우저 요구 사항 평가

현재 브라우저 상태와 프로젝트 비전을 이해하여 모든 프로젝트 이해 관계자가 동일한 결과를 얻기 위해 작업할 수 있도록 합니다.

현재 상태를 정의하여 시작:

- 현재 환경에 배포되어 있는 브라우저는 무엇인가요?
- 기본 브라우저로 설정된 브라우저는 무엇인가요?
- 일부 앱에 대해 Internet Explorer를 사용해야 하나요?
- 지금 엔터프라이즈 모드 사이트 목록을 사용하여 Internet Explorer를 구성하십니까?
- 사용자 환경에서 지원되는 OS 플랫폼은 무엇인가요? (Windows 10, macOS, Windows 7, Windows Server, 등)
- 브라우저 관리에 사용하는 관리 도구는 무엇인가요?
- 브라우저 구성 및 관리를 담당하는 사람은 누구인가요?
- 브라우저 호환성을 확인하는 프로세스는 무엇인가요?

현재 상태를 파악한 후 다음을 고려하여 브라우저 배포에 대한 원하는 목표를 결정할 수 있습니다.

- [Microsoft Edge를 기본 브라우저로 설정](./edge-default-browser.md)하기 원하십니까?
- 어떻게 [Microsoft Edge를 구성](./configure-microsoft-edge.md)하시겠습니까?
- 초기 배포의 일부로 구성하는 데 중요한 기능은 무엇인가요?
- 식별된 호환성 또는 구성 문제를 해결하는 프로세스는 무엇인가요?

또한 다음과 같이 관심 있는 기능에 대한 **사전 요구 사항**을 알고 있어야 합니다.

- [Windows Defender Application Guard](/windows/security/threat-protection/windows-defender-application-guard/reqs-wd-app-guard)
- [Internet Explorer 모드](./edge-ie-mode.md)
- [인증 및 동기화](./microsoft-edge-security-identity.md)

이러한 답변을 고려하여 Microsoft Edge 배포를 계획할 수 있습니다.
<!--bookmark -->

## <a name="make-sure-your-windows-10-devices-are-ready"></a>Windows 10 장치가 준비되었는지 확인

Edge Stable 채널을 사용하려면 2019년 10월 이후의 LCU(Latest Cumulative Update)가 필요합니다. 이전 LCU가 포함된 Windows 10 장치에 배포하는 경우 설치에 실패합니다. Edge를 배포하기 전에 적용해야 하는 최소 LCU에 대한 자세한 내용은 [다음 버전의 Microsoft Edge를 지원하기 위해 Windows 업데이트](./microsoft-edge-sysupdate-windows-updates.md)를 참조하세요.

## <a name="determine-your-deployment-methodology"></a>배포 방법 결정

원하는 종료 상태를 알고 있다면 이를 수행하는 방법을 계획할 준비가 된 것입니다. Microsoft Edge를 배포하는 두 가지 주요 방법으로는 역할별 및 사이트별이 있습니다.

### <a name="deploy-to-end-users-by-role"></a>역할별로 최종 사용자에게 배포

앱 호환성이 주요 관심사이고 테스트할 앱을 모르는 경우에는 역할별로 최종 사용자에게 배포하는 것을 고려할 수 있습니다. 이렇게 하면 단계별 배포의 각 웨이브가 호환성 문제를 해결하기 위해 구성을 수정해야 하는 앱에 대한 피드백과 인사이트를 제공할 수 있습니다.

### <a name="deploy-to-end-users-by-site"></a>사이트별로 최종 사용자에게 배포

대역폭이 주요 관심사인 경우에는 응용 프로그램 호환성 테스트를 미리 수행해 볼 수 있습니다. 테스트를 마친 후에는 다른 소프트웨어 배달 최적화를 이용할 수 있도록 사이트별로 최종 사용자에게 배포합니다.

## <a name="do-site-discovery"></a>사이트 검색 수행

레거시 웹 응용 프로그램에 대한 종속성이 있고, 대부분의 고객이 사용하는 Internet Explorer 모드를 사용하려는 경우에는 몇 가지 추가 사이트 검색을 수행해야 할 수도 있습니다.

### <a name="if-youve-already-deployed-and-configured-the-legacy-version-of-microsoft-edge"></a>레거시 버전의 Microsoft Edge를 이미 배포하고 구성한 경우

레거시 버전의 Microsoft Edge에 대해 작동하도록 이미 엔터프라이즈 사이트 목록을 구성한 경우 작업이 거의 완료된 것입니다! 추가해야 할 수 있는 사항은 중립 사이트입니다.

중립 사이트는 일반적으로 SSO(Single Sign-on)를 제공하는 사이트입니다. Microsoft Edge에서 중립 사이트로 이동한 경우 Microsoft Edge에서 인증을 받을 수 있습니다. Internet Explorer 모드에서 중립 사이트로 이동한 경우에는 Internet Explorer 모드를 유지하여 인증을 받을 수 있습니다.

사용하는 모든 SSO(또는 기타 중립) 사이트를 식별하고 이를 엔터프라이즈 사이트 목록에 추가합니다.

### <a name="if-youve-configured-internet-explorer-as-your-default-browser"></a>Internet Explorer를 기본 브라우저로 구성한 경우

현재 Internet Explorer만 사용하는 경우 최신 웹 표준으로 업그레이드한 사이트와 여전히 Internet Explorer를 사용해야 하는 사이트를 모를 수도 있습니다. 이러한 사이트를 찾아 엔터프라이즈 사이트 목록에 추가할 수 있습니다. 이를 통해 Internet Explorer 모드를 필요로 하는 사이트에서만 사용할 수 있습니다.

> [!TIP]
> [엔터프라이즈 사이트 검색](/internet-explorer/ie11-deploy-guide/collect-data-using-enterprise-site-discovery) 도구를 사용하여 Internet Explorer 모드가 필요한 사이트를 검색할 수 있습니다. Windows 10, Windows 8.1 또는 Windows 7에서 Windows Internet Explorer 8부터 Internet Explorer 11을 실행하는 컴퓨터에서 데이터를 수집할 수 있습니다.

### <a name="analyze-site-discovery-data"></a>사이트 검색 데이터 분석

사이트 데이터를 수집한 후에는 다음 4단계 프로세스를 통해 데이터를 분석하는 것이 좋습니다.

1. 도메인별로 데이터를 정렬한 다음 URL로 정렬합니다.
2. Internet Explorer 모드를 구성할 "앱"의 경계를 정의합니다. 앱을 정의하는 모든 사이트와 웹 컨트롤을 포함하는 것이 좋습니다. 하지만 앱을 너무 광범위하게 정의하여 추가 사이트와 컨트롤을 포함하지 않는 것이 좋습니다. 일부 사이트는 "http://contoso.com/app1"처럼 단순할 수도 있고, 어떤 사이트는 여러 사이트 및 페이지를 정의해야 할 수도 있습니다.
3. 앱을 테스트하여 기본적으로 작동하지 않는지 확인합니다. 많은 사이트는 최신 브라우저를 감지할 때 최신 콘텐츠를 제공하며 Internet Explorer를 감지하는 경우에만 레거시 콘텐츠를 제공합니다.
4. 테스트가 실패하는 경우 엔터프라이즈 사이트 목록에 앱을 추가합니다.

   > [!NOTE]
   > 가장 좋은 방법은 앱을 구성하는 모든 사이트를 그룹화하는 것입니다. 하나의 작업을 수행하는 데 사이트를 모두 사용해야 하고 두 사이트가 함께 업데이트되는 경향이 있는 경우에는 그룹화하는 것이 좋습니다. 이렇게 하면 앱을 업그레이드할 때 Internet Explorer 모드에서 전체 사이트를 제거하고 해당 앱에 최신 브라우저를 사용하는 것이 더 쉽습니다.

## <a name="determine-your-channel-strategy"></a>채널 전략 결정

Microsoft Edge는 [여러 채널](./microsoft-edge-channels.md)에서 릴리스됩니다.

> [!NOTE]
> 한 디바이스에 두 개 이상의 채널을 설치할 수 있습니다.

대부분의 디바이스에 안정 채널을 배포하는 것이 좋습니다. 그러나 여러 디바이스와 여러 채널을 포함하는 배포 전략을 고려해야 합니다.

### <a name="multiple-devices-and-channels"></a>여러 디바이스 및 채널

베타 채널을 사용하도록 구성된 디바이스의 대표적인 하위 집합을 보유하는 것이 좋습니다. 이렇게 하면 예정된 브라우저에 대한 변경 내용을 미리 볼 수 있습니다. 이러한 변경 사항이 최종 사용자 또는 앱에 영향을 줄 것인지 확인할 수 있습니다.

또한 개발자 채널(또는 Canary 채널)을 웹 개발자와 같은 일부 역할에 사용할 수 있도록 할 수 있습니다. 더 유동적이며 빠르게 변화하는 채널의 일부 디바이스를 대상으로 할지, 또는 이러한 채널을 사용자가 설치 여부를 선택할 수 있도록 할지 고려할 수 있습니다.

디바이스에 여러 채널을 설치할 수 있으므로 시험판 채널을 설치하기로 결정한 사용자에 대한 테스트 위험을 줄일 수 있습니다. 예를 들어, 베타 채널을 사용하는 사용자가 있고 문제가 발생한 경우 안정 채널로 전환하여 작업을 계속할 수 있습니다. 문제를 해결할 수 있을 때까지 이를 차단 해제합니다.

> [!NOTE]
> 사용자가 동기화를 사용하도록 설정한 경우 해당 구성은 채널 간에 동기화되므로 채널 간에 더욱 쉽게 전환할 수 있습니다.

## <a name="define-and-configure-policies"></a>정책 정의 및 구성

엔터프라이즈 사이트 목록을 만든 후 Microsoft Edge와 함께 배포할 정책을 파악하고 구성하는 것이 좋습니다. 이렇게 하면 테스트를 수행할 때 이러한 정책이 적용됩니다.

먼저, 사용자에게 제공하려는 첫 실행 환경을 고려합니다. 현재 브라우저에서 설정을 자동으로 가져오려면 [AutoImportAtFirstRun](./microsoft-edge-policies.md#autoimportatfirstrun)에 대한 정책을 구성합니다.

보안 정책의 경우 Microsoft Edge 보안 기준으로 시작하는 것이 좋습니다. 보안 기준은 [권장 보안 구성 기준 설정](https://techcommunity.microsoft.com/t5/Microsoft-Security-Baselines/Security-baseline-DRAFT-for-Chromium-based-Microsoft-Edge/ba-p/949991)을 사용하거나 [Microsoft Intune](/intune/protect/security-baseline-settings-edge)을 사용하여 적용할 수 있습니다.

다른 정책의 경우 [Microsoft Edge](./microsoft-edge-policies.md) 및 [Microsoft Edge 업데이트](./microsoft-edge-update-policies.md)에 대한 정책 구성을 검토하는 것이 좋습니다.

### <a name="define-your-update-strategy-and-policies"></a>업데이트 전략 및 정책 정의

또한 Microsoft Edge를 배포한 후 업데이트를 수행할 방법을 결정해야 합니다.

- **Microsoft Edge가 자동으로 업데이트하도록 허용합니다**(기본값). Microsoft Edge의 자동 업데이트를 허용하도록 선택하면 배포한 채널에 의해 결정된 속도로 Microsoft Edge가 자동으로 업데이트됩니다.
- **사용자가 원하는 대로 Microsoft Edge를 업데이트합니다**. 업데이트가 배포되는 시기를 명시적으로 제어하려는 경우 자동 업데이트를 사용하지 않도록 설정하고 직접 배포할 수 있습니다([업데이트 정책 참조](./microsoft-edge-update-policies.md)를 참조). 자동 업데이트를 사용하지 않도록 설정한 후 다음 도구 중 하나를 사용하여 각 채널에 대한 업데이트를 배포할 수 있습니다.

- [Intune](/intune/apps/apps-windows-edge?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json)
- [Configuration Manager](./deploy-edge-with-configuration-manager.md)
- 선택한 배포 도구.

업데이트 전략에 관계없이 고리 형태의 배포 전략을 활용하는 것이 좋습니다. 자동 업데이트를 사용하면 베타 채널을 실행하는 사용자를 대표하는 샘플을 확보하여 안정 채널이 되는 채널과 관련한 문제를 식별할 수 있습니다. 수동 업데이트를 사용하면 안정 채널 빌드가 새로 릴리스된 후 파일럿 그룹에 대한 추가 유효성 검사도 포함될 수 있습니다. 그 다음에는 광범위한 배포를 수행합니다.

>[!NOTE]
>Microsoft Edge 지원은 각 채널의 최신 Microsoft Edge 버전에만 적용됩니다.

## <a name="do-app-compatibility-testing"></a>앱 호환성 테스트 수행

Microsoft Edge에 대한 응용 프로그램 호환성은 매우 높기 때문에 Microsoft는 다음과 같은 호환성 약속을 제공합니다.

1. Microsoft Edge *버전 45 이하*에서 작동하는 경우 Microsoft Edge *버전 77 이상*에서도 작동합니다.
2. Internet Explorer에서 작동하는 경우 Internet Explorer 모드에서도 Microsoft Edge가 작동합니다.
3. Google Chrome에서 작동하는 경우 Microsoft Edge에서도 작동합니다.

호환성 약속을 충족하지 못하는 애플리케이션이 있는 경우 [](https://www.microsoft.com/fasttrack/microsoft-365/desktop-app-assure)Microsoft App Assure[](https://www.microsoft.com/fasttrack/microsoft-365/desktop-app-assure)을(를) 사용하여 문제를 수정할 것을 약속합니다.

### <a name="internal-line-of-business-app-testing"></a>비즈니스 앱 테스트의 내부 라인

호환성 약속에도 불구하고 많은 조직에서 규정 준수 또는 위험 관리 이유로 일부 애플리케이션의 유효성을 확인해야 합니다. 이 방법은 매우 간단하지만 앱 테스트에서 체계적이며 엄격해야 합니다.

다음 2가지 방법으로 앱 호환성 테스트를 수행할 수 있습니다.

1. 랩 테스트. 특정 구성으로 엄격하게 제어된 환경에서 응용 프로그램의 유효성을 검사합니다.
2. 파일럿 테스트. 일상 업무 환경에서 자체 디바이스를 사용하여 제한 된 수의 사용자가 응용 프로그램의 유효성을 검사합니다.

호환성 테스트에서 과도한 투자를 하지 않고 위험을 관리하기 위해 각 앱에 가장 적합한 방법을 선택합니다.

### <a name="third-party-app-support"></a>타사 앱 지원

자체 비즈니스 앱 제품군 외에도 많은 조직에서 외부 소스에서 제공하는 앱을 사용합니다. [Microsoft Edge 준비](deploy-edge-ready-for-edge.md) 문서에는 조직 내에서 사용 중인 웹 응용 프로그램 목록이 포함되어 있습니다. 이 목록에서는 Microsoft Edge와 함께 사용할 경우 해당 제품에 대한 공급자 지원 문에 대한 링크를 제공합니다.

## <a name="deploy-microsoft-edge-to-a-pilot-group"></a>파일럿 그룹에 Microsoft Edge 배포

정책을 정의하고 초기 앱 호환성 테스트를 완료했으면 파일럿 그룹에 배포할 준비가 된 것입니다. 다음 도구 중 하나를 사용하여 파일럿 그룹에 배포합니다.

- [Windows용 Microsoft Intune](/intune/apps/apps-windows-edge?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json), 또는 [macOS용 Microsoft Intune](/intune/apps/apps-edge-macos?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json)
- [Configuration Manager](./deploy-edge-with-configuration-manager.md).
- 다른 관리 도구, [Microsoft Edge용 MSI 파일](https://www.microsoftedgeinsider.com/enterprise) 다운로드 및 배포.

## <a name="validate-your-deployment"></a>배포 유효성 검사

파일럿을 배포한 후 사용자에게서 받은 모든 피드백을 포착할 수 있습니다.

- 호환성에 대한 피드백을 수집합니다. 사이트를 검색하는 동안 식별되지 않은 엔터프라이즈 사이트 목록에 속하는 사이트를 식별합니다.
- 정책 구성에 대한 피드백을 수집합니다. 사용자가 다음 보안 지침을 준수하면서 주요 기능을 사용하고 작업을 수행할 수 있는지 확인합니다.
- 사용의 용이성과 새로운 기능에 대한 피드백을 수집합니다. 사용자 질문에 따라 교육을 개발하고 제공해야 하는 모든 영역을 식별합니다.

## <a name="broad-deployment-of-microsoft-edge"></a>Microsoft Edge의 폭넓은 배포

파일럿을 완료하고 파일럿에서 얻은 교훈을 사용하여 배포 계획을 업데이트한 후에는 모든 사용자에게 Microsoft Edge 전체 배포를 수행할 준비가 된 것입니다.  축하합니다.

## <a name="see-also"></a>참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [비디오 - Microsoft Edge 배포](microsoft-edge-video-deploy.md)