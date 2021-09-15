---
title: AD(Active Directory) 사용자를 위한 온-프레미스 동기화
ms.author: collw
author: dan-wesley
manager: silvanam
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: AD(Active Directory) 사용자를 위한 온-프레미스 동기화
ms.openlocfilehash: f595c863193f2b3d383a6215ab7817a53bbf5ca6
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "11979934"
---
# <a name="on-premises-sync-for-active-directory-ad-users"></a>AD(Active Directory) 사용자를 위한 온-프레미스 동기화

이 문서에서는 AD(Active Directory) 사용자가 Microsoft 클라우드 서비스에 연결하지 않고 Microsoft Edge 즐겨찾기 및 컴퓨터 설정을 로밍하는 방법을 설명합니다.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 85 이상에 적용됩니다.

## <a name="introduction"></a>소개

Microsoft Edge에서 사용자 데이터를 동기화하려면 일반적으로 Microsoft 계정 또는 Azure Active Directory(Azure AD) 계정과 Microsoft 클라우드 서비스에 연결해야 합니다. Microsoft Edge는 온-프레미스 동기화를 통해 Active Directory 사용자의 즐겨찾기 및 설정을 서로 다른 컴퓨터 간에 이동할 수 있는 파일에 저장합니다. 온-프레미스 동기화는 이를 허용하는 프로파일에 대해 클라우드 동기화를 방해하지 않습니다.

## <a name="how-it-works"></a>작동 방식

Microsoft Edge를 사용하면 프로필을 AD(Active Directory) 계정에 연결할 수 있으므로 클라우드 동기화에 사용할 수 없습니다. 온-프레미스 동기화를 사용하도록 설정하면 AD 프로필의 데이터가 profile.pb라는 파일에 저장됩니다. 기본적으로 이 파일은 *%APPDATA%/Microsoft/Edge*에 저장됩니다. 이 파일을 작성한 후 다른 컴퓨터 간에 파일을 이동할 수 있으며 각 컴퓨터에서 사용자 데이터를 읽고 쓸 수 있습니다. Microsoft Edge는 이 파일에서만 읽기 및 쓰기를 합니다. 필요에 따라 파일이 이동되는지 확인하는 것은 관리자의 책임입니다.

## <a name="use-on-premises-sync"></a>온-프레미스 동기화 사용

온-프레미스 동기화를 사용하려면 동기화를 활성화하고, 프로파일을 AD 계정에 연결한 후 선택적으로 사용자 데이터의 위치를 변경해야 합니다.

### <a name="enable-on-premises-sync"></a>온-프레미스 동기화 사용

Microsoft Edge에서 온사이트 동기화를 사용하도록 설정하려면[RoamingProfileSupportEnabled](./microsoft-edge-policies.md#roamingprofilesupportenabled) 정책을 구성합니다.

### <a name="ensure-that-a-profile-is-associated-with-an-active-directory-account"></a>프로필이 Active Directory 계정과 연결되어 있는지 확인합니다.

온-프레미스 동기화는 AD(Active Directory) 계정과 연결된 프로필에서만 작동합니다. 이러한 프로필이 없으면 온-프레미스 동기화가 작동하지 않습니다. 사용자가 AD 계정으로 로그인하도록 하려면 [ConfigureOnPremisesAccountAutoSignIn](./microsoft-edge-policies.md#configureonpremisesaccountautosignin) 정책을 구성합니다. 온-프레미스 동기화의 경우 Microsoft Edge는 AD에만 의존하여 사용자 데이터에 대한 ID를 설정하며 Microsoft Edge가 온-프레미스 데이터를 읽고 쓰는 방법과 관리자가 AD 사용자에 대해 로밍을 구성한 방법 간에는 직접적인 관계가 없습니다.

### <a name="change-the-location-of-the-user-data-optional"></a>사용자 데이터의 위치 변경(선택적)

기본적으로 사용자 데이터는 *%APPDATA%/Microsoft/Edge*에 있는 **profile.pb**라는 이름의 파일에 저장됩니다. 이 파일의 위치를 변경하려면[RoamingProfileLocation](./microsoft-edge-policies.md#roamingprofilelocation) 정책을 구성합니다.

## <a name="changes-in-the-user-experience-when-on-premises-sync-is-enabled"></a>온-프레미스 동기화를 사용하도록 설정한 경우 사용자 환경이 변경됩니다.

온-프레미스 동기화를 사용하도록 설정하면 사용자에게 동기화를 사용하도록 요청되지 않습니다. 또한 사용자는 동기화 설정에서 동기화를 해제할 수 없으며 온-프레미스 동기화가 지원하지 않는 동기화 유형을 설정할 수 없습니다.

## <a name="on-premises-sync-usage-notes"></a>사내에서 사용 정보를 동기화합니다.

### <a name="running-cloud-sync-and-on-premises-sync-on-the-same-computer"></a>동일한 컴퓨터에서 클라우드 동기화 및 온-프레미스 동기화를 실행하고 있습니다.

온-프레미스 동기화는 클라우드 동기화를 방해하지 않습니다. Microsoft Edge에 클라우드에 동기화하는 여러 Microsoft 계정 또는 Azure Active Directory 프로파일이 있는 경우 온-프레미스 동기화가 설정된 동안 이러한 프로파일이 계속 동기화됩니다.

### <a name="running-microsoft-edge-on-more-than-one-computer-at-a-time-isnt-recommended"></a>한 번에 둘 이상의 컴퓨터에서 Microsoft Edge를 실행하는 것은 권장되지 않습니다.

온-프레미스 동기화는 컴퓨터 간에 사용자 데이터 파일을 이동하는 방식으로 작동하므로 온-프레미스 동기화는 동시 세션 간의 변경 내용을 동기화하지 않습니다. 이러한 이유로 한 번에 한 대의 컴퓨터에서 사용할 경우 온-프레미스 동기화가 가장 잘 작동합니다. 동시에 실행되는 온-프레미스 세션이 있는 경우 다음에 브라우저 세션을 시작할 때 컴퓨터의 데이터를 다른 컴퓨터의 데이터로 예기치 않게 덮어쓸 수 있습니다.

> [!NOTE]
> 온-프레미스 동기화를 사용하도록 설정하면 Microsoft Edge가 **profile.pb** 파일을 잠급니다. 폴더 리디렉션을 사용하여 서로 다른 시스템 간에 단일 **profile.pb** 파일을 공유하는 경우 해당 파일을 사용하는 Microsoft Edge 인스턴스 하나만 시작할 수 있습니다.

### <a name="using-other-sync-policies-with-on-premises-sync"></a>온-프레미스 동기화와 함께 다른 동기화 정책을 사용합니다.

[SyncTypesListDisabled](./microsoft-edge-policies.md#synctypeslistdisabled) 정책을 사용하여 원하는 경우 즐겨찾기 또는 설정 동기화를 선택적으로 사용하지 않도록 설정할 수 있습니다. [SyncDisabled](./microsoft-edge-policies.md#syncdisabled) 정책은 온-프레미스 동기화에 영향을 미치지 않습니다.

## <a name="see-also"></a>참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge 및 Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)
- [Microsoft Edge Enterprise Sync](microsoft-edge-enterprise-sync.md)