---
title: Microsoft Edge 동기화 문제 진단 및 해결
ms.author: scottbo
author: dan-wesley
manager: silvanam
ms.date: 03/08/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 관리자가 일반적인 엔터프라이즈 동기화 문제를 해결하고 해결하는 데 사용할 수 있는 지침 및 도구
ms.openlocfilehash: 767b26c74e91213b407e8264a8ed185f38dfc2e9
ms.sourcegitcommit: 86e0de9b27ad4297a6d5a57c866d7ef4fc7bb0cd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2021
ms.locfileid: "11400203"
---
# <a name="diagnose-and-fix-microsoft-edge-sync-issues"></a>Microsoft Edge 동기화 문제 진단 및 해결

이 문서에서는 Azure AD(Azure Active Directory) 환경에서 가장 일반적으로 발생하는 동기화 문제에 대한 문제 해결 지침을 제공합니다. 동기화 문제 해결에 필요한 로그를 수집하는 권장 도구도 포함되어 있습니다.

사용자가 장치에서 브라우저 데이터를 동기화하는 데 문제가 있는 경우 [동기화 재설정](edge-learnmore-reset-data-in-cloud.md)을 시도할 수 있습니다. 그래도 문제가 해결되지 않는 경우 관리자 또는 지원 직원이 다음 지침을 사용하여 동기화 문제를 해결할 수 있습니다.

> [!NOTE]
> 달리 명시되지 않은 한 Microsoft Edge 버전 77 이상에 적용됩니다.

## <a name="identity-issues-versus-sync-issues"></a>ID 문제와 동기화 문제

시작하기 전에 ID 문제와 동기화 문제의 차이점을 이해하는 것이 중요합니다. 브라우저에서 사용자 ID를 유지하기 위한 인기 있는 사용 사례는 동기화를 지원하는 것입니다. 이러한 이유로 ID 문제는 동기화 문제와 자주 혼동됩니다. 동기화 문제 해결을 시작하기 전에 ID와 동기화 문제의 차이점을 이해합니다.

문제를 동기화 문제로 처리하기 전에 사용자가 유효한 계정으로 브라우저에 로그인했는지 확인하세요.

다음 스크린샷에 ID 오류의 예가 나와 있습니다. 오류는 "**마지막 토큰 오류, EDGE_AUTH_ERROR: 3, 54, 3ea**"이며 *edge://sync-internals*(**자격 증명** 아래)에 있습니다.

:::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-identity-issue.png" alt-text="마지막 토큰 오류 EDGE_AUTH_ERROR: 3,54, 3ea":::

## <a name="common-sync-issues"></a>일반적인 동기화 문제

### <a name="issue-cant-access-m365-or-azure-information-protection-subscription"></a>문제: M365 또는 Azure Information Protection 구독에 액세스할 수 없습니다.

만료된 후 새 구독으로 대체된 이전 M365 또는 AIP(Azure Information Protection) 구독이 있나요? 있는 경우 테넌트 ID가 변경된 것이며 서비스 데이터를 다시 설정해야 합니다. **암호화 오류가 발생했습니다** 문제에서 데이터를 다시 설정하는 방법에 대한 지침을 참조하세요.

### <a name="issue-sync-is-not-available-for-this-account"></a>문제: "이 계정에 동기화를 사용할 수 없습니다."

Azure Active Directory 계정에 이 오류가 발생하거나 DISABLED_BY_ADMIN이 *edge://sync-internals*에 나타나면, 문제가 해결될 때까지 다음 절차의 단계를 순차적으로 수행하세요.

> [!NOTE]
> 이 오류의 원인은 일반적으로 Azure Active Directory 테넌트에서 구성을 변경해야 하므로, 이러한 문제 해결 단계는 최종 사용자가 아니라 테넌트 관리자만 수행할 수 있습니다.

1. 엔터프라이즈 테넌트에 지원되는 M365 구독이 있는지 확인합니다. 사용 가능한 구독 유형의 현재 목록이 [여기에 제공됩니다](https://docs.microsoft.com/azure/information-protection/activate-office365). 테넌트에 지원되는 구독이 없는 경우 Azure Information Protection을 별도로 구매하거나 지원되는 구독 중 하나로 업그레이드할 수 있습니다.
2. 지원되는 구독을 사용할 수 있는 경우 테넌트에 사용 가능한 AIP(Azure Information Protection)가 있는지 확인해야 합니다. AIP 상태를 확인하고 필요한 경우 AIP를 활성화하는 지침은 [여기](https://docs.microsoft.com/azure/information-protection/activate-office365)에서 확인할 수 있습니다.
3. 2단계에서 AIP가 활성 상태이지만 동기화가 여전히 작동하지 않는 것으로 표시되면 ESR(Enterprise State Roaming)을 켜야 합니다. ESR을 사용하도록 설정하는 지침은 [여기](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)에서 확인할 수 있습니다. ESR이 계속 켜져 있을 필요는 없습니다. 이 단계로 문제가 해결될 경우 ESR을 끌 수 있습니다.
4. 온보딩 정책을 통해 Azure Information Protection의 범위가 지정되지 않았는지 확인합니다. [Get-AadrmOnboardingControlPolicy](https://docs.microsoft.com/powershell/module/aadrm/get-aadrmonboardingcontrolpolicy?view=azureipps) PowerShell 애플릿을 사용하여 범위 지정이 활성화되어 있는지 알 수 있습니다. 다음 두 예제에서는 범위가 지정되지 않은 구성과 특정 보안 그룹으로 범위가 지정된 구성을 보여줍니다.

   ```powershell
    PS C:\Work\scripts\PowerShell> Get-AadrmOnboardingControlPolicy
 
    UseRmsUserLicense SecurityGroupObjectId                Scope
    ----------------- ---------------------                -----
                False 
   ```

   ```powershell

    PS C:\Work\scripts\PowerShell> Get-AadrmOnboardingControlPolicy
 
    UseRmsUserLicense SecurityGroupObjectId                Scope
    ----------------- ---------------------                -----
                False f1488a05-8196-40a6-9483-524948b90282   All
   ```

   범위 지정을 사용하도록 설정한 경우 영향을 받는 사용자를 범위의 보안 그룹에 추가하거나 범위를 제거해야 합니다. 아래 예제에서 온보딩은 AIP 범위를 표시된 보안 그룹으로 지정했으며 범위 지정은 [Set-AadrmOnboardingControlPolicy](https://docs.microsoft.com/powershell/module/aadrm/set-aadrmonboardingcontrolpolicy?view=azureipps) PowerShell 애플릿으로 제거해야 합니다.

5. 테넌트에서 IPCv3Service가 켜져 있는지 확인합니다. [Get-AadrmConfiguration](https://docs.microsoft.com/powershell/module/aadrm/get-aadrmconfiguration?view=azureipps) PowerShell 애플릿에는 서비스 상태가 표시됩니다.

   :::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-scoped-cfg-example.png" alt-text="IPCv3Service를 사용하도록 설정되어 있는지 확인합니다.":::

6. 문제가 해결되지 않은 경우 [Microsoft Edge 지원](https://www.microsoftedgeinsider.com/support)에 문의하세요.

### <a name="issue-stuck-at-setting-up-sync-or-couldnt-connect-to-the-sync-server-retrying"></a>문제: "동기화 설정..." 또는 "동기화 서버에 연결할 수 없습니다. 다시 시도..."에서 멈춰 있습니다.

1. 로그아웃을 시도한 다음 로그인합니다.
2. *edge://sync-internals*로 이동합니다. "**유형 정보**" 섹션에 다음 오류가 있는 경우 다음 문제 **암호화 오류가 발생했습니다**로 건너뛰세요.

   `"Error:GenerateCryptoErrorsForTypes@../../components/sync/driver/data_type_manager_impl.cc:42, cryptographer error was encountered"`

3. 서버 엔드포인트 ping을 시도합니다. 클라이언트용 서버 엔드포인트는 *edge://sync-internals*에서 이용 가능합니다. 다음 스크린샷은 **환경 정보**의 엔드포인트 정보를 보여줍니다.

   :::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-endpoint-info.png" alt-text="엔드포인트 정보":::

4. 서버 엔드포인트가 비어 있거나 서버를 ping할 수 없고 환경에 방화벽이 있는 경우 클라이언트 컴퓨터에서 필요한 서비스 엔드포인트를 사용할 수 있는지 확인하세요.

   - Microsoft Edge 동기화 서비스 엔드포인트:
     - [https://edge-enterprise.activity.windows.com](https://edge-enterprise.activity.windows.com)
     - [https://edge.activity.windows.com](https://edge.activity.windows.com)
    - Azure Information Protection 엔드포인트:
      - [https://api.aadrm.com](https://api.aadrm.com)(테넌트 대부분의 경우)
      - [https://api.aadrm.de](https://api.aadrm.de)(독일의 테넌트)
      - [https://api.aadrm.cn](https://api.aadrm.cn)(중국의 테넌트)
   - [Windows 알림 서비스 엔드포인트](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config).

5. 그래도 문제가 해결되지 않은 경우 [Microsoft Edge 지원](https://www.microsoftedgeinsider.com/support)에 문의하세요.

### <a name="issue-cryptographer-error-encountered"></a>문제: 암호화 오류가 발생했습니다.

이 오류는 **유형 정보** 아래 *edge://sync-internals*에서 볼 수 있으며 사용자의 서비스 측 데이터를 다시 설정해야 할 수 있습니다. 다음 예에서는 암호화 오류 메시지를 보여줍니다.
<br>"Error:GenerateCryptoErrorsForTypes@../../components/sync/driver/data_type_manager_impl.cc:42, cryptographer error was encountered".

1. Microsoft Edge를 다시 시작하고 *edge://sync-internals*로 이동하여 "**AAD 계정 키 상태**" 섹션을 확인합니다.
   - "마지막 MIP 결과"의 "성공": 암호화 오류는 서버 데이터가 분실된 키로 암호화될 수 있음을 의미합니다. 동기화를 다시 시작하려면 데이터 재설정이 필요합니다.
   - "마지막 MIP 결과"의 "사용 권한 없음": Azure AD 변경 또는 테넌트 구독 변경으로 인해 발생할 수 있습니다. 동기화를 다시 시작하려면 데이터 재설정이 필요합니다.
   - 다른 오류는 서버 구성 문제를 의미할 수 있습니다.
2. 데이터 재설정이 필요한 경우 [클라우드에서 Microsoft Edge 데이터 다시 설정](edge-learnmore-reset-data-in-cloud.md)을 참조하세요.

### <a name="issue-sync-has-been-turned-off-by-your-administrator"></a>문제: "관리자가 동기화를 해제했습니다."

[SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled) 정책이 설정되지 않았는지 확인하세요.

## <a name="see-also"></a>참고 항목

- [Microsoft Edge Enterprise 동기화](microsoft-edge-enterprise-sync.md)
- [Microsoft Edge 및 Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)
- [Microsoft Edge Enterprise 방문 페이지](https://aka.ms/EdgeEnterprise)
