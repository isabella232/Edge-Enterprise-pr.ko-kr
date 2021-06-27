---
title: Microsoft Edge Enterprise 동기화 구성
ms.author: collw
author: dan-wesley
manager: silvanam
ms.date: 03/08/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 즐겨찾기, 암호 및 기타 브라우저 데이터를 동기화하도록 Microsoft Edge를 구성하는 관리자 및 사용자 옵션입니다.
ms.openlocfilehash: 99edc97bd5f4bab7bf421e0d15e512c5f6f76cc0
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2021
ms.locfileid: "11617758"
---
# <a name="configure-microsoft-edge-enterprise-sync"></a>Microsoft Edge Enterprise 동기화 구성

이 문서는 관리자가 로그인한 모든 장치에서 사용자 즐겨찾기, 암호 및 기타 브라우저 데이터를 동기화하도록 Microsoft Edge를 구성하는 방법을 설명합니다. 관리자가 아닌 경우 이 문서를 방문하여 여러 장치에서 Microsoft Edge에 로그인하고 동기화하는 방법에 대해 알아보세요. [여러 장치에서 Microsoft Edge를 동기화하려면 로그인합니다.](https://support.microsoft.com/microsoft-edge/sign-in-to-sync-microsoft-edge-across-devices-e6ffa79b-ed52-aa32-47e2-5d5597fe4674)

> [!NOTE]
> 달리 명시되지 않은 한 Microsoft Edge 버전 77 이상에 적용됩니다.

## <a name="overview"></a>개요

Microsoft Edge 동기화를 사용하면 사용자가 로그인한 모든 디바이스에서 자신의 검색 데이터에 액세스할 수 있습니다. 동기화에서 지원하는 데이터는 다음과 같습니다.

- 즐겨찾기
- 암호
- 주소 및 기타(양식 채우기)
- 컬렉션
- 설정
- 확장
- 열린 탭(Microsoft Edge 버전 88에서 사용 가능)
- 기록(Microsoft Edge 버전 88에서 사용 가능)

동기화 기능은 사용자 동의를 통해 활성화되며 위에 나열된 각 데이터 형식의 동기화를 사용자가 켜거나 끌 수 있습니다. 사용자가 동기화 문제가 발생하는 경우 **설정** > **프로필** > **동기화 재설정**에서 동기화를 재설정해야 할 수 있습니다.

> [!NOTE]
> 동기화 기능을 지원하기 위해 추가 디바이스 연결 및 구성 데이터(예: 디바이스 이름, 제조업체 및 모델)가 업로드됩니다.

## <a name="prerequisites"></a>필수 구성 요소

Azure AD(Azure Active Directory) 계정의 Microsoft Edge 동기화는 다음과 같은 모든 구독에 사용할 수 있습니다.

- Azure AD Premium(P1 또는 P2)
- M365 Business Premium
- Office 365 E1 이상
- AIP(Azure Information Protection)(P1 또는 P2)
- 모든 EDU 구독(학생용 또는 교직원용 Microsoft Apps, 학생용 또는 교직원용 Exchange Online, O365 A1 이상, M365 A1 이상, 또는 학생 또는 교직원용 Azure Information Protection P1 또는 P2)

## <a name="sync-group-policies"></a>동기화 그룹 정책

관리자는 다음 그룹 정책을 사용하여 Microsoft Edge 동기화를 구성하고 관리할 수 있습니다.

- [SyncDisabled](./microsoft-edge-policies.md#syncdisabled): 동기화를 완전히 사용하지 않습니다.
- [SavingBrowserHistoryDisabled](./microsoft-edge-policies.md#savingbrowserhistorydisabled): 검색 기록 저장 및 동기화를 사용하지 않습니다. 이 정책은 열린 탭 동기화도 사용하지 않습니다.
- [AllowDeletingBrowserHistory:](./microsoft-edge-policies.md#allowdeletingbrowserhistory)해당 정책을 사용하지 않도록 설정하면 기록 동기화도 사용하지 않도록 설정됩니다.
- [SyncTypesListDisabled](./microsoft-edge-policies.md#synctypeslistdisabled): 동기화에서 제외된 유형 목록을 구성합니다.
- [RoamingProfileSupportEnabled](./microsoft-edge-policies.md#roamingprofilesupportenabled): AD(Active Directory) 프로필에서 온-프레미스 저장소를 사용할 수 있도록 허용합니다. 자세한 내용은 [AD(Active Directory) 사용자를 위한 온-프레미스 동기화](./microsoft-edge-on-premises-sync.md)를 참조하세요.
- [ForceSync:](/deployedge/microsoft-edge-policies#forcesync)기본적으로 동기화를 켜고 동기화에 대한 사용자 동의가 필요하지 않습니다.  

## <a name="configure-microsoft-edge-sync"></a>Microsoft Edge 동기화 구성

Microsoft Edge 동기화에 대한 구성 옵션은 AIP(Azure Information Protection) 서비스를 통해 사용할 수 있습니다. 테넌트에 AIP 서비스가 사용되는 경우 모든 사용자가 라이선스에 관계없이 Microsoft Edge 데이터를 동기화할 수 있습니다. AIP를 활성화하는 방법에 대한 지침은 [여기](/azure/information-protection/activate-office365)에서 확인할 수 있습니다.

특정 사용자 집합에 대한 동기화를 제한하려면 해당 사용자에 대해 [AIP 온보딩 제어 정책](/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?preserve-view=true&view=azureipps) 을 사용하도록 설정할 수 있습니다. 필요한 사용자가 모두 온보딩되었는지 확인한 후에도 동기화를 계속 사용할 수 없는 경우, [Get-AIPServiceIPCv3](/powershell/module/aipservice/get-aipserviceipcv3?preserve-view=true&view=azureipps) PowerShell cmdlet을 사용하여 IPCv3Service가 활성화되었는지 확인합니다.

> [!CAUTION]
> Azure Information Protection을 활성화하면 Microsoft Word나 Microsoft Outlook과 같은 다른 응용 프로그램에서도 AIP를 사용하여 보호할 수 있습니다. 또한, Microsoft Edge 동기화를 제한하는 데 사용하는 모든 온보딩 제어 정책을 사용하면 다른 응용 프로그램에서 AIP를 사용하여 콘텐츠를 보호할 수 없습니다.

## <a name="microsoft-edge-and-enterprise-state-roaming-esr"></a>Microsoft Edge 및 엔터프라이즈 상태 로밍(ESR)

Microsoft Edge는 모든 장치에서 사용자 데이터를 동기화하기 위한 확장된 범위가 있는 플랫폼 간 응용 프로그램으로, 더 이상 Azure AD Enterprise State Roaming의 일부가 아닙니다. 그러나 Microsoft Edge는 ESR의 데이터 보호 약속(예: 사용자 키를 가져오는 기능)을 이행합니다. 자세한 내용은 [Microsoft Edge 및 Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

- [Microsoft Edge Enterprise 동기화](microsoft-edge-enterprise-sync.md)
- [Microsoft Edge 동기화 문제 진단 및 해결](microsoft-edge-troubleshoot-enterprise-sync.md)
- [Microsoft Edge 및 Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)
- [Microsoft Edge Enterprise 방문 페이지](https://aka.ms/EdgeEnterprise)