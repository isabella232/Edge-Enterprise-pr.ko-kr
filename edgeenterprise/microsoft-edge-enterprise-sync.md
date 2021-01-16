---
title: Microsoft Edge 동기화 구성 및 문제 해결
ms.author: scottbo
author: dan-wesley
manager: silvanam
ms.date: 01/14/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 동기화 구성 및 문제 해결
ms.openlocfilehash: fa9b9ead6319bceeb95066003a77be7ecf84db46
ms.sourcegitcommit: 68b50c45b2b78acec5a0776ce4ddd11410a4e382
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2021
ms.locfileid: "11270780"
---
# Microsoft Edge 동기화 구성 및 문제 해결

이 문서에서는 로그인한 모든 장치에서 Microsoft Edge를 구성하고 사용하여 즐겨찾기, 암호 및 기타 브라우저 데이터를 동기화하는 방법을 설명합니다. 이 문서에서는 가장 일반적으로 발생하는 동기화 문제에 대한 문제 해결 단계도 제공합니다. 또한 문제 해결에 필요한 로그를 수집하기 위한 권장 도구도 포함되어 있습니다.

> [!NOTE]
> 달리 명시되지 않은 한 Microsoft Edge 버전 77 이상에 적용됩니다.

## 개요

Microsoft Edge 동기화를 사용하면 사용자가 로그인한 모든 디바이스에서 자신의 검색 데이터에 액세스할 수 있습니다. 동기화에서 지원하는 데이터는 다음과 같습니다.

- 즐겨찾기
- 암호
- 주소 및 기타(양식 채우기)
- 컬렉션
- 설정
- 확장
- 열린 탭(Microsoft Edge 버전 88에서 사용 가능)
- 기록(Microsoft Edge 버전 88에서 사용 가능)

동기화 기능은 사용자 동의를 통해 활성화되며 위에 나열된 각 데이터 형식의 동기화를 사용자가 켜거나 끌 수 있습니다.

> [!NOTE]
> 동기화 기능을 지원하기 위해 추가 디바이스 연결 및 구성 데이터(예: 디바이스 이름, 제조업체 및 모델)가 업로드됩니다.

## 필수 구성 요소

Azure AD(Azure Active Directory) 계정의 Microsoft Edge 동기화는 다음과 같은 모든 구독에 사용할 수 있습니다.

- Azure AD Premium(P1 또는 P2)
- M365 Business Premium
- Office 365 E1 이상
- AIP(Azure Information Protection)(P1 또는 P2)
- 모든 EDU 구독(학생용 또는 교직원용 Microsoft Apps, 학생용 또는 교직원용 Exchange Online, O365 A1 이상, M365 A1 이상, 또는 학생 또는 교직원용 Azure Information Protection P1 또는 P2)

## 동기화 그룹 정책

다음 그룹 정책을 사용하여 Microsoft Edge 동기화를 구성하고 관리할 수 있습니다.

- [SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled): 동기화를 완전히 사용하지 않습니다.
- [SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled): 검색 기록 저장 및 동기화를 사용하지 않습니다. 이 정책은 열린 탭 동기화도 사용하지 않습니다.
- [AllowDeletingBrowserHistory:](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowdeletingbrowserhistory)해당 정책을 사용하지 않도록 설정하면 기록 동기화도 사용하지 않도록 설정됩니다.
- [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled): 동기화에서 제외된 유형 목록을 구성합니다.
- [RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled): AD(Active Directory) 프로필에서 온-프레미스 저장소를 사용할 수 있도록 허용합니다. 자세한 내용은 [AD(Active Directory) 사용자를 위한 온-프레미스 동기화](https://docs.microsoft.com/DeployEdge/microsoft-edge-on-premises-sync)를 참조하세요.
- [ForceSync:]( https://docs.microsoft.com/deployedge/microsoft-edge-policies#forcesync)기본적으로 동기화를 켜고 동기화에 대한 사용자 동의가 필요하지 않습니다.  

## Microsoft Edge 동기화 구성

Microsoft Edge 동기화에 대한 구성 옵션은 AIP(Azure Information Protection) 서비스를 통해 사용할 수 있습니다. 테넌트에 AIP 서비스가 사용되는 경우 모든 사용자가 라이선스에 관계없이 Microsoft Edge 데이터를 동기화할 수 있습니다. AIP를 활성화하는 방법에 대한 지침은 [여기](https://docs.microsoft.com/azure/information-protection/activate-office365)에서 확인할 수 있습니다.

특정 사용자 집합에 대한 동기화를 제한하려면 해당 사용자에 대해 [AIP 온보딩 제어 정책](https://docs.microsoft.com/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?view=azureipps&preserve-view=true) 을 사용하도록 설정할 수 있습니다. 필요한 사용자가 모두 온보딩되었는지 확인한 후에도 동기화를 계속 사용할 수 없는 경우, [Get-AIPServiceIPCv3](https://docs.microsoft.com/powershell/module/aipservice/get-aipserviceipcv3?view=azureipps&preserve-view=true) PowerShell cmdlet을 사용하여 IPCv3Service가 활성화되었는지 확인합니다.

> [!CAUTION]
> Azure Information Protection을 활성화하면 Microsoft Word나 Microsoft Outlook과 같은 다른 응용 프로그램에서도 AIP를 사용하여 보호할 수 있습니다. 또한, Microsoft Edge 동기화를 제한하는 데 사용하는 모든 온보딩 제어 정책을 사용하면 다른 응용 프로그램에서 AIP를 사용하여 콘텐츠를 보호할 수 없습니다.

## Microsoft Edge 및 엔터프라이즈 상태 로밍(ESR)

Microsoft Edge는 모든 장치에서 사용자 데이터를 동기화하기 위한 확장된 범위가 있는 플랫폼 간 응용 프로그램으로, 더 이상 Azure AD Enterprise State Roaming의 일부가 아닙니다. 그러나 Microsoft Edge는 ESR의 데이터 보호 약속(예: 사용자 키를 가져오는 기능)을 이행합니다. 자세한 내용은 [Microsoft Edge 및 Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)을 참조하세요.

## 동기화 문제 해결

이 섹션에서는 가장 많이 발생하는 동기화 문제에 대한 문제 해결 단계를 제공합니다. 또한 문제 해결에 필요한 로그를 수집하기 위한 권장 도구도 포함되어 있습니다.

### ID 문제와 동기화 문제

브라우저에서 사용자 ID를 유지하기 위한 인기 있는 사용 사례는 동기화를 지원하는 것입니다. 이러한 이유로 ID 문제는 동기화 문제와 자주 혼동됩니다. 동기화 문제 해결을 시작하기 전에 ID와 동기화 문제의 차이점을 이해합니다.

문제를 동기화 문제로 처리하기 전에 사용자가 유효한 계정으로 브라우저에 로그인했는지 확인하세요.

다음 스크린샷은 다음 **자격 증명**의 *edge://sync-internals*에서 발견된 ID 오류의 예를 보여줍니다.

:::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-identity-issue.png" alt-text="ID 오류":::

### 일반적인 동기화 문제

#### 문제: M365 또는 Azure Information Protection 구독에 액세스할 수 없습니다.

만료된 후 새 구독으로 대체된 이전 M365 또는 AIP(Azure Information Protection) 구독이 있나요? 있는 경우 테넌트 ID가 변경된 것이며 서비스 데이터를 다시 설정해야 합니다. **암호화 오류가 발생했습니다** 문제에서 데이터를 다시 설정하는 방법에 대한 지침을 참조하세요.

#### 문제: "이 계정에 동기화를 사용할 수 없습니다."

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

#### 문제: "동기화 설정..." 또는 "동기화 서버에 연결할 수 없습니다. 다시 시도..."에서 멈춰 있습니다.

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

### 문제: 암호화 오류가 발생했습니다.

이 오류는 *edge://sync-internals*의 **유형 정보** 아래에 표시되며 사용자의 서비스 측 데이터를 다시 설정해야 함을 의미할 수 있습니다. 다음 스크린샷에는 암호화 오류에 대한 세부 정보의 예가 나와 있습니다.

:::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-crypto-error-new.png" alt-text="암호화 오류.":::

1. Microsoft Edge를 다시 시작하고 *edge://sync-internals*로 이동하여 "**AAD 계정 키 상태**" 섹션을 확인합니다.
   - "마지막 MIP 결과"의 "성공": 암호화 오류는 서버 데이터가 분실된 키로 암호화될 수 있음을 의미합니다. 동기화를 다시 시작하려면 데이터 재설정이 필요합니다.
   - "마지막 MIP 결과"의 "사용 권한 없음": Azure AD 변경 또는 테넌트 구독 변경으로 인해 발생할 수 있습니다. 동기화를 다시 시작하려면 데이터 재설정이 필요합니다.
   - 다른 오류는 서버 구성 문제를 의미할 수 있습니다.
2. 데이터 재설정이 필요한 경우 [클라우드에서 Microsoft Edge 데이터 다시 설정](edge-learnmore-reset-data-in-cloud.md)을 참조하세요.

#### 문제: "관리자가 동기화를 해제했습니다."

[SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled) 정책이 설정되지 않았는지 확인하세요.

## 질문과 대답

### 보안 및 서버/데이터 규정 준수

#### 동기화된 데이터가 암호화되나요?

데이터는 TLS 1.2 이상을 사용하는 전송에서 암호화됩니다. 모든 데이터 형식은 AES128을 사용하여 Microsoft 서비스에 있는 나머지 부분에서 추가로 암호화됩니다. 열려 있는 탭 및 기록 동기화에 사용되는 데이터 형식을 제외한 모든 데이터 형식은 [Azure Information Protection](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern) 정책을 통해 관리되는 키를 사용하여 사용자의 디바이스를 떠나기 전에 추가적으로 암호화됩니다.

#### 열린 탭 및 기록 데이터에 클라이언트 측 암호화가 더 없는 이유는 무엇인가요?

최종 사용자 장치에서 리소스 사용률을 줄이기 위해 열린 탭 로밍 데이터를 기반으로 기록 데이터가 서버 쪽에서 생성됩니다. 해당 데이터의 클라이언트 쪽 암호화로는 이 프로세스가 불가능합니다. 열린 탭 및 기록 동기화를 사용하지 않도록 설정하기 위해 [SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled) 또는 [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled) 정책을 적용합니다.

#### 테넌트 관리자가 자신의 키를 가져올 수 있나요?

예,  [Azure Information Protection](https://azure.microsoft.com/services/information-protection/)을 통해 할 수 있습니다.

#### Microsoft Edge 동기화 데이터는 어디에 저장됩니까?

Azure AD 계정에 대해 동기화된 데이터는 테넌트 ID에 따라 보안 서버에 저장됩니다. 예를 들어 미국에 등록된 테넌트에 대한 데이터는 해당 지역에 지리적으로 위치하는 서버에 저장되며, Office 애플리케이션처럼 동일한 스토리지 솔루션을 활용합니다.

#### 데이터에서 Microsoft Edge로 동기화를 수행하는 것 외에 Microsoft의 클라우드가 계속 유지되나요?

아니요.

#### 엔터프라이즈 동기화는 어느 서비스 약관에 속하나요?

Microsoft Edge 동기화에 대한 서비스 약관은 Microsoft Edge에서 볼 수 있는 Microsoft 소프트웨어 라이선스에 속해 있습니다.  *edge://terms* Azure AD 구독 및 서비스 약관은 궁극적으로 Microsoft의 [온라인 서비스 약관](https://www.microsoft.com/licensing/product-licensing/products)에 해당합니다.

#### Microsoft Edge에서 GCC(정부 커뮤니티 클라우드) High의 규제 준수 기능을 지원하나요?

현재 그렇지 않습니다. GCC High 클라우드 고객의 경우 Microsoft Edge 동기화를 사용할 수 없습니다.

### 동기화 적용 중

#### Microsoft Edge 동기화가 모든 M365 구독에서 지원되지 않는 이유는 무엇인가요?

엔터프라이즈 동기화는 일부 M365 구독에서 사용할 수 있는 [Azure Information Protection](https://azure.microsoft.com/services/information-protection/)에 의존합니다.

#### Microsoft Edge 동기화는 Enterprise State Roaming을 기반으로 하나요?

아니요. ESR을 사용하여 동기화를 사용할 수 있지만, Microsoft Edge 동기화는 ESR의 일부가 아닙니다. 자세한 내용은 [Microsoft Edge Sync](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-enterprise-sync)와 [Microsoft Edge 및 Enterprise State Roaming](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-enterprise-state-roaming)을 참조하세요.

#### Microsoft Edge는 Microsoft Edge와 IE 간의 동기화를 지원합니까?

이 동기화를 지원할 계획이 없습니다. 레거시 앱을 지원하기 위해 환경에 여전히 IE가 필요한 경우 Microsoft의 [새로운 IE 모드](https://docs.microsoft.com/deployedge/edge-ie-mode)를 고려하세요.

#### Microsoft Edge가 Microsoft Edge 레거시와 동기화되나요?

아니요, 동기화되지 않습니다. 이 두 가지 에코시스템을 연결하는 것은 Microsoft Edge에서 동기화 안정성을 저하시킬 것입니다. 기존 데이터가 Microsoft Edge로 마이그레이션되는 것을 보장하겠습니다. 사용자는 선택한 브라우저에서 데이터를 가져올 수도 있습니다. 이는 Microsoft Edge가 IE와 동기화할 수 없음을 의미합니다.

### 동기화 관리

#### 사용자가 개인 테넌트와 동기화하는 것을 중지할 수 있나요?

직접은 아니지만 [RestrictSigninToPattern](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern) 정책을 사용하여 Microsoft Edge에 사인온 할 수 있는 프로파일을 결정할 수 있습니다.

## 참고 항목

- [Microsoft Edge Enterprise 동기화](microsoft-edge-enterprise-sync.md)
- [Microsoft Edge 및 Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)
- [Microsoft Edge Enterprise 방문 페이지](https://aka.ms/EdgeEnterprise)
