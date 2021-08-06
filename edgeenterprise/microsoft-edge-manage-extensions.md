---
title: 엔터프라이즈에서 Microsoft Edge 확장 관리
ms.author: aspoddar
author: AndreaLBarr
manager: balajek
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 엔터프라이즈에서 Microsoft Edge 확장 관리
ms.openlocfilehash: 69c10bfa1e041d48f99594e6ac85dd39ba66379ca8d6d7fe12f1bdef6f3b54fe
ms.sourcegitcommit: d44c0997ffe40d67421312ed96e7766da947eaa0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "11724918"
---
# <a name="manage-microsoft-edge-extensions-in-the-enterprise"></a>엔터프라이즈에서 Microsoft Edge 확장 관리

이 문서에서는 조직에서 Microsoft Edge 확장을 담당하는 관리자를 위한 모범 사례 지침을 소개합니다. 이 문서의 정보를 사용하여 조직의 확장 관리 전략을 개발할 수 있습니다.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.

## <a name="introduction"></a>소개

조직은 기업 및 사용자 데이터를 보호하고 브라우저 확장을 평가하여 안전하고 자사와 관련이 있는지 확인하려 합니다. 관리자가 하려는 일:

- 잘못된 앱 및 확장을 설치하지 않도록 합니다.
- 사용자가 작업을 하는 데 필요한 확장을 유지합니다.
- 사용자 및 회사 데이터에 대한 액세스를 관리합니다.  

이는 관리자가 사용자에게 안전하고 생산적인 환경을 제공하기 위해 확장을 관리하는 데 도움이 되는 시리즈의 첫 번째 문서입니다. 이 시리즈는 다양한 옵션을 안내하며, 확장 관리에 최적합한 방법을 선택하는 데 유용합니다. 이 시리즈는 다음 문서로 구성됩니다.

- [엔터프라이즈에서 Microsoft Edge 확장을 관리합니다](microsoft-edge-manage-extensions.md). 확장을 관리할 전략을 세우고, 브라우저 관리에 필요한 관리 템플릿을 설정합니다.
- [그룹 정책을 사용하여 Microsoft Edge 확장 관리](microsoft-edge-manage-extensions-policies.md). 그룹 정책을 사용하여 확장을 관리하는 옵션.
- [Microsoft Edge 확장을 호스팅할 웹 저장소 만들기](microsoft-edge-manage-extensions-webstore.md). 확장을 만들고 호스트합니다.
- [Microsoft Edge 확장에 대한 FAQ](microsoft-edge-manage-extensions-faq.md). 자주 묻는 질문.

## <a name="things-to-consider-when-managing-extensions"></a>확장을 관리할 때의 고려 사항

사용자는 특정 앱, 사이트 및 확장에 액세스하여 작업을 하는 동시에 사용자와 회사 데이터를 보호해야 합니다. 효과적인 보안 전략에는 기업에 적합한 질문과 확장이 회사의 필요에 어떻게 부합할 수 있는가를 묻는 과정이 포함됩니다. 주요 질문의 일부는 다음과 같습니다.

- 어떤 규정 및 규정 준수 조치를 지켜야 하나요?
- 일부 확장이 지나치게 광범위한 권한을 요구하여 회사의 데이터 보안 정책에 위배될 수 있나요?
- 얼마나 많은 사용자 데이터 또는 회사 데이터가 사용자의 장치에 저장되나요?

이러한 질문에 답변할 때 Microsoft Edge가 제공하는 세분화된 정책을 사용하여 다음과 같이 할 수 있습니다.

- 데이터 보호 정책에 따라 사용자 컴퓨터에서 확장을 차단 또는 허용합니다.
- 생산성에 필요한 도구를 갖추도록 사용자의 장치에 확장을 강제로 설치합니다.
- 사용자가 작업을 하는 데 필요한 최소한의 권한을 허용하는 허용 목록 또는 차단 목록 확장입니다.

기존 확장 관리 모델에서는 특정 확장에 대해 허용 목록 및 차단 목록 접근 방식을 사용합니다. 그러나 Microsoft Edge 통해 확장에서 요청한 사용 권한도 관리할 수 있습니다. 이 모델을 사용하여 컴퓨터 및 장치에서 확장을 허용할 권한 및 사용 권한을 결정한 다음 요구 사항에 따라 확장을 허용하거나 차단하는 전역 정책을 구현할 수 있습니다.  

## <a name="understand-extension-permissions"></a>확장 권한 이해

확장을 제대로 실행하려면 장치 또는 웹 페이지에서 변경 사항을 적용할 권한이 필요할 수 있습니다. 이러한 권한을 사용 권한이라고 합니다. 개발자는 필요한 권한을 나열하고 확장에 액세스해야 합니다. 사용 권한에는 두 가지 주요 범주가 있으며, 많은 확장에 다음 두 사용 권한이 모두 필요합니다.

- 호스트 사용 권한을 사용하려면 보거나 수정할 수 있는 웹 페이지를 나열하는 확장이 필요합니다.
- 장치 사용 권한은 실행 중인 장치의 확장에 필요한 권한입니다.

이러한 사용 권한의 몇 가지 예로는 USB 포트 액세스, 저장소 또는 화면 보기, 기본 프로그램과의 통신 등이 있습니다.  

## <a name="get-ready-to-manage-extensions"></a>확장 관리 준비

## <a name="before-you-begin"></a>시작하기 전에

확장 옵션은 귀하가 이미 사용자들을 위해 Microsoft Edge를 관리하는 것으로 가정합니다. Microsoft Edge 정책의 관리 템플릿 설정에 대한 추가 정보는 다음에서 살펴보세요.

-   [Windows에서 Microsoft Edge 정책 설정 구성](/DeployEdge/configure-microsoft-edge)
-   [Intune을 사용한 Windows용 구성](/mem/intune/configuration/administrative-templates-configure-edge?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json)
-   [모바일 장치 관리를 사용한 Windows용 구성](/deployedge/configure-edge-with-mdm)
-   [.plist를 사용하여 macOS에 대해 구성](/deployedge/configure-microsoft-edge-on-mac)
-   [Jamf를 사용한 macOS용 구성](/deployedge/configure-microsoft-edge-on-mac-jamf)

이 문서의 구성 단계는 Windows용입니다. MAC/Linux의 해당 구현에 대한 내용은 Microsoft Edge 브라우저 정책 참조에서 알아보세요.

## <a name="decide-which-extensions-to-allow"></a>허용할 확장 결정

대다수 조직에서는 사용 권한 및 액세스 권한이 있는 웹 사이트를 통해 확장을 관리해야 합니다. 이 방법은 더욱 안전하고, 관리하기 쉬우며, 대규모 조직을 위해 확장이 가능합니다.  

- 차단/허용된 사용 권한 – 필요한 사용 권한으로 확장을 제어할 수 있습니다.
- 런타임 차단 호스트 – 이러한 확장이 액세스할 수 있는 웹 사이트 제어가 가능합니다.

이 방법을 사용하면 한 번만 설정하면 되므로 시간을 절약할 수 있습니다. 또한 런타임 호스트 정책을 사용하면 가장 중요한 사이트가 보호됩니다. 다음과 같은 다른 옵션도 있습니다.

-   확장 강제 설치 – 확장을 자동으로 설치할 수 있습니다.
-   허용 목록/차단 목록(필요한 경우) – 설치할 수 있는 확장을 결정합니다.

다음 단계에 따라 조직에서 허용할 확장을 결정할 수 있습니다.

1. 컴퓨터에서 직원들에게 필요한 확장의 목록을 만듭니다. 테스트 환경에서 확장을 테스트하여 내부 앱과의 호환성 문제를 진단합니다.
2. 보안을 더 강화해야 하는 사이트를 선택합니다.

   - 확장이 변경을 하거나 데이터를 읽지 못하게 차단해야 하는 중요한 내부 웹 사이트 또는 도메인을 찾으세요.  
   - 확장이 실행될 때 API 호출을 차단하여 이러한 사이트에 대한 액세스를 방지합니다. 여기에는 웹 요청, 쿠키 읽기, JavaScript 삽입, XHR 차단 등이 포함됩니다.

3. 이러한 확장을 실행하기 위해 필요한 사용 권한을 결정하세요. 사용자에게 잠재적인 위험이 발생하게 하는 사용 권한을 식별합니다.

   - 사용자가 설치한 확장을 점검하고 필요한 사용 권한을 확인합니다. 확장 코드에서 JSON 파일을 나타내는 웹 앱을 볼 수 있습니다. 확장에 필요한 권한을 확인하기 위해 다음 단계를 따르세요.

     - [Microsoft Edge 추가 기능](https://microsoftedge.microsoft.com/addons/) 웹 사이트 또는 [Chrome 웹 스토어](https://chrome.google.com/webstore)에서 확정을 설치합니다.
     - 확장을 테스트하고 조직에서 확장이 작동하는 방법을 이해합니다.
     - *edge://extensions*로 이동하여 확장에 필요한 권한을 검토합니다. 예를 들어 다음 스크린샷에 표시된 Microsoft Office 확장은 ‘검색 기록 읽기’ 및 ‘알림 표시’ 권한을 요청합니다. 이 확장의 유용성을 필요한 사용 권한 수준과 비교해 가늠합니다. 조직에서 사용할 확장을 승인한 후 다음 도구를 사용하여 관리합니다.
   :::image type="content" source="media/microsoft-edge-manage-extensions/manage-extesions-office-extension.png" alt-text="사용 권한이 있는 Microsoft Office 확장.":::

   - 조직에서 승인하기 전에 조직의 사용자가 요청한 확장의 유효성을 검사할 수도 있습니다. 확장에서 사용하는 일부 사용 권한이 모호할 수 있습니다. 업무상 중요한 앱의 경우 앱 개발자 또는 공급업체에 직접 연락하여 확장에 대한 추가 정보를 얻거나 소스 코드를 볼 수 있습니다. 이를 통해 장치 및 웹 사이트에서 확장이 변경할 수 있는 내용에 대한 설명을 자세히 알게 됩니다.
   - 확장에서 사용하는 모든 사용 권한을 나열하는 사용 권한 선언 목록을 검토합니다. 이 목록에서 조직 내에서 허용할 사용 권한을 결정할 수 있습니다.

4. 수집한 데이터에서 마스터 목록을 만들 수 있습니다. 이 목록에는 다음 정보가 포함됩니다.

   - **필수 확장**. 이 목록은 부서, 사무실 위치 또는 기타 관련 정보별로 구성될 수 있습니다.
   - **확장 허용 목록**. 차단할 수 있지만 실행에 필요한 사용 권한이 있는 필수 확장입니다. 이러한 확장은 사용자가 필요하거나 공급업체와의 대화를 통해 위험하지 않은 것으로 확인됩니다.
   - **확장 차단 목록**. 설치가 차단된 확장입니다. 이 목록의 확장에는 실행이 허용되지 않는 사용 권한이 있습니다. 또한 보안을 유지해야 하는 핵심 사이트와 도메인을 포함하며 확장 액세스가 허용되지 않습니다. 나중에 이 차단 목록을 이미 있는 다른 차단 목록과 비교할 수 있습니다. 현재 차단 목록 정책을 완화할 수 있습니다.

5. 이해 관계자와 IT 팀에 목록을 제시하여 동의를 구하세요.
6. 랩에서 또는 조직에서 작은 파일럿으로 새 정책을 테스트합니다.
7. 이러한 새로운 정책군을 단계적으로 직원들에게 롤아웃합니다. 자세한 내용은 [그룹 정책을 사용하여 Microsoft Edge 확장 관리](microsoft-edge-manage-extensions-policies.md)에서 참고하세요.
8. 사용자의 피드백을 검토합니다.
9. 매월, 매분기 또는 매년 해당 프로세스를 반복하고 미세 조정합니다.

허용된 사용 권한 적용 및 중요한 회사 사이트 보호 기준을 사용하여 더 나은 환경을 사용자에게 제공하는 동시에 엔터프라이즈의 보안을 더 강화할 수 있습니다. 직원은 이전에는 설치할 수 없었던 확장을 설치할 수 있지만, 중요한 비즈니스 사이트에서는 실행할 수 없습니다.  

## <a name="see-also"></a>참고 항목

- [그룹 정책을 사용하여 Microsoft Edge 확장 관리](microsoft-edge-manage-extensions-policies.md)
- [Microsoft Edge 확장을 호스팅할 웹 저장소 만들기](microsoft-edge-manage-extensions-webstore.md)
- [ExtensionSettings 정책에 대한 참조 가이드](microsoft-edge-manage-extensions-ref-guide.md)
- [Microsoft Edge 확장에 대한 FAQ](microsoft-edge-manage-extensions-faq.md)
- [Microsoft Edge Enterprise 방문 페이지](https://aka.ms/EdgeEnterprise)