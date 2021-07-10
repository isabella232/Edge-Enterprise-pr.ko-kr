---
title: Microsoft Edge Enterprise 동기화 FAQ
ms.author: collw
author: dan-wesley
manager: silvanam
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge Enterprise 동기화에 대한 질문과 대답
ms.openlocfilehash: a13e1f02f6e871004d45f81159d5cf0a3397b6ad
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2021
ms.locfileid: "11643144"
---
# <a name="microsoft-edge-enterprise-sync-faq"></a>Microsoft Edge Enterprise 동기화 FAQ

이 문서에는 Microsoft Edge 버전 77 이상에 대한 엔터프라이즈 동기화에 대한 질문과 대답이 포함되어 있습니다.

## <a name="security-and-serverdata-compliance"></a>보안 및 서버/데이터 규정 준수

### <a name="is-the-synced-data-encrypted"></a>동기화된 데이터가 암호화되나요?

데이터는 TLS 1.2 이상을 사용하는 전송에서 암호화됩니다. 모든 데이터 형식은 AES128을 사용하여 Microsoft 서비스에 있는 나머지 부분에서 추가로 암호화됩니다. 열려 있는 탭 및 기록 동기화에 사용되는 데이터 형식을 제외한 모든 데이터 형식은 [Azure Information Protection](./microsoft-edge-policies.md#restrictsignintopattern) 정책을 통해 관리되는 키를 사용하여 사용자의 디바이스를 떠나기 전에 추가적으로 암호화됩니다.

### <a name="why-dont-open-tab-and-history-data-have-more-client-side-encryption"></a>열린 탭 및 기록 데이터에 클라이언트 측 암호화가 더 없는 이유는 무엇인가요?

최종 사용자 장치에서 리소스 사용률을 줄이기 위해 열린 탭 로밍 데이터를 기반으로 기록 데이터가 서버 쪽에서 생성됩니다. 해당 데이터의 클라이언트 쪽 암호화로는 이 프로세스가 불가능합니다. 열린 탭 및 기록 동기화를 사용하지 않도록 설정하기 위해 [SavingBrowserHistoryDisabled](./microsoft-edge-policies.md#savingbrowserhistorydisabled) 또는 [SyncTypesListDisabled](./microsoft-edge-policies.md#synctypeslistdisabled) 정책을 적용합니다.

### <a name="can-tenant-admins-bring-their-own-key"></a>테넌트 관리자가 자신의 키를 가져올 수 있나요?

예,  [Azure Information Protection](https://azure.microsoft.com/services/information-protection/)을 통해 할 수 있습니다.

### <a name="where-is-microsoft-edge-sync-data-stored"></a>Microsoft Edge 동기화 데이터는 어디에 저장됩니까?

Azure AD 계정에 대해 동기화된 데이터는 테넌트 ID에 따라 보안 서버에 저장됩니다. 예를 들어 미국에 등록된 테넌트에 대한 데이터는 해당 지역에 지리적으로 위치하는 서버에 저장되며, Office 애플리케이션처럼 동일한 스토리지 솔루션을 활용합니다.

### <a name="does-the-data-ever-leave-microsofts-cloud-aside-from-syncing-to-microsoft-edge"></a>데이터에서 Microsoft Edge로 동기화를 수행하는 것 외에 Microsoft의 클라우드가 계속 유지되나요?

아니요.

### <a name="what-terms-of-service-does-enterprise-sync-fall-under"></a>엔터프라이즈 동기화는 어느 서비스 약관에 속하나요?

Microsoft Edge 동기화에 대한 서비스 약관은 Microsoft Edge에서 볼 수 있는 Microsoft 소프트웨어 라이선스에 속해 있습니다.  *edge://terms* Azure AD 구독 및 서비스 약관은 궁극적으로 Microsoft의 [온라인 서비스 약관](https://www.microsoft.com/licensing/product-licensing/products)에 해당합니다.

### <a name="does-microsoft-edge-support-government-community-cloud-gcc-high-compliance"></a>Microsoft Edge에서 GCC(정부 커뮤니티 클라우드) High의 규제 준수 기능을 지원하나요?

현재 그렇지 않습니다. GCC High 클라우드 고객의 경우 Microsoft Edge 동기화를 사용할 수 없습니다.

## <a name="applying-sync"></a>동기화 적용 중

### <a name="why-isnt-microsoft-edge-sync-supported-in-all-m365-subscriptions"></a>Microsoft Edge 동기화가 모든 M365 구독에서 지원되지 않는 이유는 무엇인가요?

엔터프라이즈 동기화는 일부 M365 구독에서 사용할 수 없는 [Azure Information Protection](https://azure.microsoft.com/services/information-protection/)에 따라 다릅니다.

### <a name="is-microsoft-edge-sync-based-on-enterprise-state-roaming"></a>Microsoft Edge 동기화는 엔터프라이즈 상태 로밍을 기반으로 하나요?

아니요. ESR을 사용하여 동기화를 사용할 수 있지만, Microsoft Edge 동기화는 ESR의 일부가 아닙니다. 자세한 내용은 [Microsoft Edge Sync](/DeployEdge/microsoft-edge-enterprise-sync)와 [Microsoft Edge 및 Enterprise State Roaming](/DeployEdge/microsoft-edge-enterprise-state-roaming)을 참조하세요.

### <a name="will-microsoft-edge-ever-support-syncing-between-microsoft-edge-and-ie"></a>Microsoft Edge는 Microsoft Edge와 IE 간의 동기화를 지원합니까?

이 동기화를 지원할 계획이 없습니다. 레거시 앱을 지원하기 위해 환경에 여전히 IE가 필요한 경우 Microsoft의 [새로운 IE 모드](./edge-ie-mode.md)를 고려하세요.

### <a name="will-microsoft-edge-sync-with-microsoft-edge-legacy"></a>Microsoft Edge가 Microsoft Edge 레거시와 동기화되나요?

아니요, 동기화되지 않습니다. 이 두 가지 에코시스템을 연결하는 것은 Microsoft Edge에서 동기화 안정성을 저하시킬 것입니다. 기존 데이터가 Microsoft Edge로 마이그레이션되는 것을 보장하겠습니다. 사용자는 선택한 브라우저에서 데이터를 가져올 수도 있습니다. 이는 Microsoft Edge가 IE와 동기화할 수 없음을 의미합니다.

## <a name="managing-sync"></a>동기화 관리 중

### <a name="is-it-possible-to-stop-my-users-from-syncing-with-a-personal-tenant"></a>사용자가 개인 테넌트와 동기화하는 것을 중지할 수 있나요?

직접은 아니지만 [RestrictSigninToPattern](./microsoft-edge-policies.md#restrictsignintopattern) 정책을 사용하여 Microsoft Edge에 사인온 할 수 있는 프로파일을 결정할 수 있습니다.

## <a name="see-also"></a>참고 항목

- [Microsoft Edge Enterprise 동기화](microsoft-edge-enterprise-sync.md)
- [Microsoft Edge 및 Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)
- [Microsoft Edge Enterprise 방문 페이지](https://aka.ms/EdgeEnterprise)