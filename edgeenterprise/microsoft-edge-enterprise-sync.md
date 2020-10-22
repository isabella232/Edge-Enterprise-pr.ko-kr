---
title: Microsoft Edge Enterprise Sync
ms.author: scottbo
author: dan-wesley
manager: silvanam
ms.date: 10/21/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge Enterprise Sync
ms.openlocfilehash: e51346d9bab83228c42a84a7a14ee45dc9b463a7
ms.sourcegitcommit: b32d8d64ae65dc5a46e47b7c34b0211097a0cc65
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "11133133"
---
# Microsoft Edge Enterprise Sync

이 문서에서는 로그인한 모든 디바이스에서 Microsoft Edge를 사용하여 즐겨찾기, 암호 및 기타 브라우저 데이터를 동기화하는 방법을 설명합니다.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.

## 개요

Microsoft Edge 동기화를 사용하면 사용자가 로그인한 모든 디바이스에서 자신의 검색 데이터에 액세스할 수 있습니다. 동기화에서 지원하는 데이터는 다음과 같습니다.

- 즐겨찾기
- 암호
- 주소 및 기타(양식 채우기)
- 컬렉션
- 설정

동기화 기능은 사용자 동의를 통해 활성화되며 사용자는 위에 나열된 각 데이터 형식에 대해 동기화를 켜거나 끌 수 있습니다.

> [!NOTE]
> 동기화 기능을 지원하기 위해 추가 디바이스 연결 및 구성 데이터(예: 디바이스 이름, 제조업체 및 모델)가 업로드됩니다.

## 필수 구성 요소

AAD(Azure AD) 계정의 Microsoft Edge 동기화는 다음 모든 구독에 사용할 수 있습니다.

- Azure AD Premium P1 또는 P2
- M365 Business Premium
- Office 365 E1 이상
- Azure Information Protection(AIP) (P1& P2)
- 모든 EDU 구독(학생용 또는 교직원용 Microsoft Apps, 학생용 또는 교직원용 Exchange Online, O365 A1 이상, M365 A1 이상, 또는 학생 또는 교직원용 Azure Information Protection P1 또는 P2)

## Microsoft Edge 동기화 구성

Microsoft Edge 동기화에 대한 구성 옵션은 AIP(Azure Information Protection) 서비스를 통해 사용할 수 있습니다. 테넌트에 AIP 서비스가 사용되는 경우 모든 사용자가 라이선스에 관계없이 Microsoft Edge 데이터를 동기화할 수 있습니다. AIP를 활성화하는 방법에 대한 지침은 [여기](https://docs.microsoft.com/azure/information-protection/activate-office365)에서 확인할 수 있습니다.

특정 사용자 집합에 대한 동기화를 제한하려면 해당 사용자에 대해 [AIP 온보딩 제어 정책](https://docs.microsoft.com/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?view=azureipps) 을 사용하도록 설정할 수 있습니다. 필요한 사용자가 모두 온보딩되었는지 확인한 후에도 동기화를 계속 사용할 수 없는 경우, [Get-AIPServiceIPCv3](https://docs.microsoft.com/powershell/module/aipservice/get-aipserviceipcv3?view=azureipps) PowerShell cmdlet을 사용하여 IPCv3Service가 활성화되었는지 확인합니다.

> [!CAUTION]
> Azure Information Protection을 활성화하면 Microsoft Word나 Microsoft Outlook과 같은 다른 응용 프로그램에서도 AIP를 사용하여 보호할 수 있습니다. 또한, Edge 동기화를 제한하는 데 사용하는 모든 온보딩 제어 정책을 사용하면 다른 응용 프로그램에서 AIP를 사용하여 콘텐츠를 보호할 수 없습니다.

## Microsoft Edge 및 Enterprise State Roaming

새 Microsoft Edge는 모든 디바이스에서 사용자 데이터를 동기화하는 확장된 범위를 포함하는 교차 플랫폼 애플리케이션이므로 더 이상 Azure AD Enterprise State Roaming의 일부가 아닙니다. 그러나 새 Microsoft Edge는 사용자의 고유한 키를 사용하는 기능과 같이 ESR의 데이터 보호 약속을 이행합니다. 자세한 내용은 [Microsoft Edge 및 Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)을 참조하세요.

## 동기화 그룹 정책

다음 그룹 정책은 Microsoft Edge 동기화에 영향을 줍니다.

- [SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled): 동기화를 완전히 사용하지 않습니다.
- [SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled): 검색 기록 저장 및 동기화를 사용하지 않습니다. 이 정책은 열린 탭 동기화도 사용하지 않습니다.
- [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled): 동기화에서 제외되는 유형의 목록을 구성합니다.
- [RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled): AD(Active Directory) 프로필에서 온-프레미스 저장소를 사용할 수 있도록 허용합니다. 자세한 내용은 [AD(Active Directory) 사용자를 위한 온-프레미스 동기화](https://docs.microsoft.com/DeployEdge/microsoft-edge-on-premises-sync)를 참조하세요.
- [ForceSync]( https://docs.microsoft.com/deployedge/microsoft-edge-policies#forcesync): 기본적으로 동기화를 설정하며 동기화하는 데 사용자 동의가 필요하지 않습니다.  

## 질문과 대답

### 보안 및 서버/데이터 규정 준수

#### 동기화된 데이터가 암호화되나요? 

데이터는 TLS 1.2 이상을 사용하여 전송에서 암호화됩니다. 대부분의 데이터 유형은 AES256을 사용하여 Microsoft 서비스에서 저장시 추가로 암호화됩니다. 

#### Microsoft Edge 동기화 데이터는 어디에 저장됩니까?

Azure AD 계정에 대해 동기화된 데이터는 테넌트 ID에 따라 보안 서버에 저장됩니다. 예를 들어 미국에 등록된 테넌트에 대한 데이터는 해당 지역에 지리적으로 위치하는 서버에 저장되며, Office 애플리케이션처럼 동일한 스토리지 솔루션을 활용합니다.

#### 데이터에서 Microsoft Edge로 동기화를 수행하는 것 외에 Microsoft의 클라우드가 계속 유지되나요?

아니요.

#### 테넌트 관리자가 자신의 키를 가져올 수 있나요?

네, [Azure Information Protection](https://azure.microsoft.com/services/information-protection/)을 사용합니다.

#### 엔터프라이즈 동기화가 포함된 서비스 조항은 무엇인가요?

서비스 조건은 Azure AD 구독과 동일 합니다. 모든 Azure AD 서비스는 결국 Microsoft의 [온라인 서비스 약관](https://www.microsoft.com/licensing/product-licensing/products)에 해당됩니다.

#### Microsoft Edge에서 GCC(정부 커뮤니티 클라우드) 높은 규제 준수 기능을 지원하나요?

현재는 아닙니다. GCC High는 Tier D이며 Microsoft Edge는 Tier C까지 지원합니다.

### 동기화 적용 중

#### 레거시 Microsoft Edge를 유지하기로 결정한 기업 및 교육 고객은 어떻게 되나요?

현재 버전의 Microsoft Edge 브라우저는 ESR 서비스에 계속 참여하게 됩니다.

#### Premium Azure AD 구독을 동기화해야 하는 이유는 무엇인가요?

엔터프라이즈 동기화는 일부 Azure AD 계층에서 사용할 수 없는 Azure Information Protection에 의존합니다.

#### Microsoft Edge는 Enterprise State Roaming을 기반으로 하나요?

아니요. ESR을 사용하여 동기화를 사용할 수 있지만, Microsoft Edge 동기화는 ESR의 일부가 아닙니다. 자세한 내용은 [Microsoft Edge Sync](microsoft-edge-enterprise-sync.md)와 [Microsoft Edge 및 Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)을 참조하세요.

#### Microsoft Edge는 Microsoft Edge와 IE 간의 동기화를 지원합니까?

이 동기화를 지원할 계획이 없습니다. 레거시 앱을 지원하기 위해 환경에 여전히 IE가 필요한 경우 Microsoft의 [새로운 IE 모드](https://docs.microsoft.com/deployedge/edge-ie-mode)를 고려하세요.

#### 새 Microsoft Edge 브라우저가 Microsoft Edge 레거시와 동기화되나요?

아니요, 동기화되지 않습니다. 이 두 에코시스템을 연결하면 새 Microsoft Edge에서 동기화의 안정성이 손상될 수 있습니다. 기존 데이터가 새 Microsoft Edge로 마이그레이션되도록 보장하겠습니다. 사용자는 또한 원하는 브라우저에서 데이터를 가져올 수 있습니다. 이는 또한 새 Microsoft Edge 브라우저에서 IE와 동기화하는 방법을 갖고 있지 않음을 의미합니다.

### 동기화 관리

#### 사용자가 개인 테넌트와 동기화하는 것을 중지할 수 있나요?

직접은 아니지만 [RestrictSigninToPattern](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern) 정책을 사용하여 Microsoft Edge에 사인온 할 수 있는 프로파일을 결정할 수 있습니다.

## 참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge 및 Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)
