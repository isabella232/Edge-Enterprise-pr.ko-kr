---
title: Microsoft Edge 데이터 다시 설정
ms.author: collw
author: dan-wesley
manager: silvanam
ms.date: 07/09/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 클라우드에서 Microsoft Edge 다시 설정하는 방법
ms.openlocfilehash: 7b1b54bd3e59190d6ff3bdfeb71b8f97080538c224b7dbddb73b9d11708706ac
ms.sourcegitcommit: d44c0997ffe40d67421312ed96e7766da947eaa0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "11725991"
---
# <a name="reset-microsoft-edge-data-in-the-cloud"></a>클라우드에서 Microsoft Edge 데이터 다시 설정하기

이 문서에서는 클라우드에서 Microsoft Edge 데이터를 다시 설정하는 단계를 설명합니다.

> [!NOTE]
> 이 문서는 달리 명시하지 않는 한 Microsoft Edge 버전 88 이상에 적용됩니다.

> [!NOTE]
> 테넌트가 GCC 모드 환경에 있는 경우 테넌트 관리자는 Microsoft에 지원 요청을 제출하여 데이터를 다시 설정해야 합니다.

## <a name="overview"></a>개요

클라우드에서 Microsoft Edge 데이터를 다시 설정해야 하는 상황이 생길 수 있습니다. 예를 들면 데이터를 동기화하려고 하는데 Microsoft Edge가 데이터를 동기화할 수 없다고 할 수 있습니다. 또는 Microsoft 클라우드에서 데이터를 확실히 제거해야 할 수도 있습니다. 두 경우 모두 Microsoft Edge를 사용하여 클라우드 데이터 다시 설정을 수행할 수 있습니다.

## <a name="back-up-your-favorites"></a>즐겨찾기 백업

다시 설정을 수행하기 전에 즐겨찾기 백업을 수행하는 것이 좋습니다. 다음 단계에 따라 즐겨찾기를 백업하세요.

1. Microsoft Edge에서 **Ctrl + Shift + O 누르기 > 점 3개 선택 > 즐겨찾기 내보내기 클릭**을 선택합니다.
2. 즐겨찾기를 저장하려는 파일을 선택합니다. 직접 파일 이름을 입력하거나 Microsoft Edge에서 기본적으로 제공하는 이름인 "favorites_month_day_year.html"을 파일 이름으로 사용할 수 있습니다. For example, "favorites_07_05_21.html". 나중에 즐겨찾기를 복원해야 하는 경우 해당 파일에서 복원할 수 있습니다.
3. **저장**을 클릭합니다.

## <a name="perform-a-reset-to-fix-a-synchronization-problem"></a>다시 설정으로 동기화 문제 해결

Microsoft Edge가 데이터를 동기화할 수 없다고 보고하며 데이터 다시 설정을 제안하는 경우 다시 설정을 수행하여 문제를 해결합니다.

다음 단계에 따라 다시 설정을 수행합니다.

1. 먼저 다시 설정을 수행하는 장치를 제외하고 모바일 장치를 포함해 모든 장치의 Microsoft Edge에서 로그아웃해 주세요. Microsoft Edge에서 로그아웃하려면 **설정 > 프로필 > 로그아웃**을 선택합니다. 로그아웃할 때 로컬 장치에서 즐겨찾기, 설정 등을 지우는 옵션을 선택하지 마세요.
2. 다른 모든 장치에서 로그아웃한 후 데스크톱에서 Microsoft Edge를 여세요. **설정 등 > 동기화 > 동기화 다시 설정**을 선택합니다. 결과 대화 상자에서 데이터를 다시 설정한 후 동기화 재개를 선택하고 **다시 설정**을 선택하세요.

## <a name="perform-a-reset-to-remove-your-data-from-microsofts-cloud"></a>다시 설정을 수행하여 Microsoft 클라우드에서 데이터 제거하기

Microsoft 클라우드에서 데이터를 제거하려면 다음 단계에 따라 다시 설정을 수행합니다.

1. 다시 설정을 수행하는 디바이스를 제외한 디바이스에서 동기화를 중지합니다.  Microsoft Edge에서 **설정 > 프로필 > 동기화 끄기**를 선택합니다.  
2. 동기화를 중지한 후 **설정 > 프로필 > 동기화 재설정**을 선택합니다. 결과 대화 상자에서 동기화를 재설정한 후 이 장치에서 동기화를 재개하도록 선택하지 **마세요**. **다시 설정**을 선택합니다.

## <a name="what-to-expect-during-and-after-a-data-reset"></a>데이터 다시 설정 중 및 이후에 예상되는 일

데이터 다시 설정은 Microsoft 클라우드에 저장한 데이터의 양에 따라 몇 초에서 몇 분까지 걸릴 수 있습니다. 경우에 따라 다시 설정을 완료할 수 없다는 메시지 또는 다시 설정 재시도 제안이 표시될 수 있습니다. 이 경우 몇 시간 정도 기다렸다가 데이터 다시 설정을 재시도해 주세요. 그래도 데이터를 다시 설정할 수 없는 경우 Microsoft Edge 고객 지원팀에 문의합니다.

데이터 다시 설정이 성공적으로 완료된 후 다시 설정 후 동기화 재개를 선택한 경우 장치에서 데이터가 다시 동기화됩니다. 다른 장치에서 동기화를 시작하려면 해당 장치에 다시 로그인해야 합니다. 그러나 동기화 재개를 선택하지 않은 경우 Microsoft Edge 데이터가 클라우드에서 제거되고 데이터가 더 이상 동기화되지 않습니다.

## <a name="see-also"></a>참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge 엔터프라이즈 동기화](microsoft-edge-enterprise-sync.md)
