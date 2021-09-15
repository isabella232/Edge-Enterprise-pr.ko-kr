---
title: Microsoft Edge 수명 주기
ms.author: srugh
author: AndreaLBarr
manager: seanlynd
ms.date: 07/15/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge 수명 주기
ms.openlocfilehash: 941b77920978bba82dd5edcb192ddfab898f4053
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "11980069"
---
# <a name="microsoft-edge-lifecycle-policy"></a>Microsoft Edge 수명 주기 정책

이 문서에서는 Microsoft Edge에 적용되는 수명 주기 정책에 대해 설명합니다.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.

> [!NOTE]
> 안정적인 채널 버전 94을 시작으로 Microsoft Edge는 4주 간의 주 릴리스 주기 케이던스로 이동합니다. 그러나 복잡한 환경을 관리하는 엔터프라이즈 고객은 Microsoft Edge 업데이트를 계획하고 테스트하는 데 더 많은 시간이 필요하다고 판단됩니다. 업데이트를 관리하기 위해 확장된 일정이 필요한 엔터프라이즈 고객이 Microsoft Edge 연장된 안정 옵션을 제공합니다. **이** 옵션은 관리되는 환경이 있는 고객에게만 제공됩니다. [공지 블로그 게시물 참조](https://blogs.windows.com/msedgedev/2021/07/15/opt-in-extended-stable-release-cycle/)

## <a name="overview-of-the-lifecycle-policy-for-microsoft-edge"></a>Microsoft Edge에 대한 수명 주기 정책 개요

Microsoft Edge 보다 자주 사용할 수 있는 업데이트 기능을 제공합니다. 브라우저 릴리스가 Windows 주 릴리스에 연결되어 있지 않기 때문에 이를 반영하기 위해 관리 수명 주기 정책이 업데이트되어 있어야 합니다. 앞으로 Microsoft Edge 최신 수명 [주기 정책을 따르게 됩니다.](https://support.microsoft.com/help/30881/modern-lifecycle-policy) 보안 업데이트 및 서비스 업데이트는 최신 안정 채널 릴리스 및 최신 베타 채널 릴리스에서만 사용할 수 있습니다. 이전 버전의 Microsoft Edge를 사용하는 경우 최신 품질 및 보안 업데이트를 놓칠 가능성이 있으므로 권장되지 않습니다.  지원은 아래 설명에 따라 제공됩니다.

## <a name="servicing-and-assisted-support-timeline-for-microsoft-edge-77-93"></a>77-93에 대한 서비스 Microsoft Edge 지원 일정

Microsoft Edge 채널 버전 77에 대한 6주 주 릴리스 주기 주기가 있으며 버전 93까지 계속됩니다.  가장 최근 3개의 안정 채널 릴리스 및 최신 베타 채널 릴리스에 대한 보조 지원을 제공합니다. 안정 채널 릴리스의 유효 보조 지원 기간은 약 18주입니다. 베타 채널 릴리스의 유효 지원 기간은 ~6주입니다. 이전 베타 채널 릴리스는 지원되지 않습니다.  아래 표를 참조하세요.

|     릴리스 옵션              |     지원되는 주 버전 릴리스    |     서비스된 주 버전 릴리스    |     릴리스 전반의 지원 범위    |     서비스 범위    |
|---------------------------------|----------------------------------------|---------------------------------------|-----------------------------------------|---------------------------|
|     Daily "Canary"              |     없음                               |     없음                              |     없음                                |     없음                  |
|     매주 "개발자"                |     없음                               |     없음                              |     없음                                |     없음                  |
|     6주 "베타"               |     현재                            |     현재                           |     6주                             |     6주               |
|     6주 "안정"             |     현재 및 2 이전             |     현재                           |     18주                            |     6주               |


## <a name="servicing-and-assisted-support-timeline-changes-in-microsoft-edge-94"></a>Microsoft Edge 94에서 서비스 및 지원 일정 변경

안정적인 채널 버전 94을 시작으로 Microsoft Edge는 4주 간의 주 릴리스 주기 케이던스로 이동합니다. 최신 3개의 안정 채널 릴리스 및 최신 베타 채널 릴리스에 대한 지원이 계속 제공될 것입니다. 안정 채널 릴리스의 유효 지원 기간은 약 12주입니다.

복잡한 환경을 관리하는 엔터프라이즈 고객은 복잡한 업데이트를 계획하고 테스트하는 데 더 Microsoft Edge 있습니다. 업데이트를 관리하기 위해 확장된 일정이 필요한 엔터프라이즈 고객에게 Microsoft Edge **8주간의**주요 릴리스 주기에 맞춰 확장된 안정 옵션을 제공합니다. 지원은 가장 최근의 두 개의 확장 안정 채널 릴리스에 사용할 수 있습니다. 확장 안정 채널 릴리스의 유효 지원 기간은 약 16주입니다. 아래 표를 참조하세요.

|     릴리스 옵션              |     지원되는 주 버전 릴리스    |     서비스된 주 버전 릴리스    |     릴리스 전반의 지원 범위    |     서비스 범위    |
|---------------------------------|----------------------------------------|---------------------------------------|-----------------------------------------|---------------------------|
|     Daily "Canary"              |     없음                               |     없음                              |     없음                                |     없음                  |
|     매주 "개발자"                |     없음                               |     없음                              |     없음                                |     없음                  |
|     4주 "베타"               |     현재                            |     현재                           |     4주                             |     4주               |
|     4주 "안정"             |     현재 및 2 이전             |     현재                           |     12주                            |     4주               |
|     8주 "확장 안정"    |     현재 및 1 이전             |     현재                           |     16주                            |     8주               |

## <a name="see-also"></a>참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge 설명서](./index.yml)
- [Microsoft 최신 수명 주기 정책](https://support.microsoft.com/help/30881/modern-lifecycle-policy)
- [Microsoft Edge를 지원하는 운영 체제](./microsoft-edge-supported-operating-systems.md)