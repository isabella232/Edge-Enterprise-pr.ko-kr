---
title: Microsoft Edge용 Windows 업데이트
ms.author: jtkim
author: RyanHechtMSFT
manager: srugh
ms.date: 09/23/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge에 대한 Windows 업데이트입니다.
ms.openlocfilehash: 0232e269861430df9a152006d2a8476c353eae46
ms.sourcegitcommit: 8e5294e82cf62abc916cfd24692f55925330d42b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2021
ms.locfileid: "12037208"
---
# <a name="windows-updates-to-support-the-next-version-of-microsoft-edge"></a>다음 버전 Microsoft Edge를 지원하기 위한 Windows 업데이트

이 문서에서는 다음 버전 Microsoft Edge를 지원하기 위해 Windows를 업데이트하는 방법을 설명합니다.

> [!IMPORTANT]
> Microsoft Edge 레거시 서비스 종료에 대한 Microsoft Edge [제품](https://aka.ms/EdgeLegacyEOS) 팀 블로그 게시물을 참조하세요.

> [!NOTE]
> 이 문서는 Microsoft Edge 안정 채널에 적용됩니다.

## <a name="microsoft-edge-and-the-windows-release-cycle"></a>Microsoft Edge 및 Windows 릴리스 주기

다음 버전 Microsoft Edge는 더 빈번하고 더 유연한 업데이트 기능을 제공합니다. 브라우저 릴리스가 Windows 주요 릴리스에 연결되어 있지 않기 때문에 운영 체제는 다음 버전 Microsoft Edge가 Windows에 원활하게 적용되도록 변경됩니다. 따라서 기능 업데이트는 (대략) 4주 주기로 릴리스됩니다. 보안 및 호환성 업데이트는 필요할 때마다 배송됩니다.

## <a name="updates-and-the-user-experience"></a>업데이트와 사용자 환경

업데이트는 다음 버전 Microsoft Edge의 안정 채널이 설치될 때까지 사용자 환경을 변경하지 않습니다. Microsoft Edge Beta, Dev 또는 Canary를 설치하면 Windows 변경 사항이 트리거되지 않습니다. 이러한 브라우저 릴리스는 기존 브라우저와 나란히 설치됩니다.

모든 업데이트가 적용되고 다음 버전 Microsoft Edge의 안정 채널이 시스템 수준에서 설치되면 다음 변경 사항이 시스템에 적용됩니다.

- 현재 버전 Microsoft Edge의 모든 시작 메뉴 핀, 타일 및 바로 가기가 다음 버전 Microsoft Edge으로 마이그레이션됩니다.
- 현재 버전 Microsoft Edge의 모든 작업 표시줄 핀 및 바로 가기가 다음 버전 Microsoft Edge으로 마이그레이션됩니다.
- 다음 버전 Microsoft Edge는 작업 표시줄에 고정됩니다. 현재 버전 Microsoft Edge이 이미 고정되어 있는 경우 대체됩니다.
- 다음 버전 Microsoft Edge가 바탕 화면에 바로 가기를 추가합니다. 현재 버전 Microsoft Edge 바로 가기가 이미 있는 경우 대체됩니다.
- 기본적으로 Microsoft Edge가 처리하는 대부분의 프로토콜이 다음 버전 Microsoft Edge으로 마이그레이션됩니다.
- 현재 버전 Microsoft Edge는 설정, 모든 앱 및 모든 파일 또는 프로토콜 지원 대화 상자를 포함하여 OS의 모든 UX 화면에서 숨겨집니다.
- 현재 버전 Microsoft Edge를 시작하려는 모든 시도는 다음 버전 Microsoft Edge로 리디렉션됩니다.

  > [!NOTE]
  > 사용자 수준 설치는 이러한 동작을 트리거하지 않습니다.

위 변경 내용과 함께 다음 버전 Microsoft Edge의 안정 채널이 설치되어 있는지 여부에 관계없이 발생하는 변경 사항이 있습니다.

- Microsoft Edge는 다음 버전 Microsoft Edge가 지원하지 않는 전자책 및 XML 프로토콜의 등록을 취소합니다. 사용자가 이러한 프로토콜을 열려고 하면 기본 앱을 선택하라는 대화 상자가 표시됩니다. 
            [전자책을 계속 읽으려면 ePub 앱 다운로드](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fsupport.microsoft.com%2Fhelp%2F4517840&data=02%7C01%7Cv-danwes%40microsoft.com%7Cc9f8571b880549c30fcf08d72be5eaf9%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637026138803983526&sdata=qtb3DvVZQ6H%2FFXnBievkl%2B%2BngAQXwl340PcH8kRc3y4%3D&reserved=0)에서 전자책 지원에 대한 자세한 내용을 알아보세요.

## <a name="timeline"></a>타임라인

설명한 환경을 지원하기 위해 필요한 변경 사항은 각 Windows 버전에 대한 세 가지 업데이트와 함께 제공됩니다.

### <a name="windows-versions-1903-and-1909"></a>Windows 버전 1903 및 1909

- 2019년 8월 보안 업데이트와 함께 제공되는 선택적 2019년 7월 업데이트의 첫 번째 변경 내용 집합.
- 2019년 9월 보안 업데이트와 함께 제공되는 선택적 2019년 8월 업데이트의 두 번째 변경 내용 집합.

  > [!NOTE]
  > 이 업데이트에서는 Microsoft Edge가 XML 프로토콜의 등록을 해제합니다.

- 2019년 10월 보안 업데이트와 함께 제공되는 선택적 2019년 9월 업데이트의 세 번째 변경 내용 집합.

  > [!NOTE]
  > 이 업데이트에서는 Microsoft Edge가 더 이상 전자책을 지원하지 않습니다.

### <a name="windows-versions-1709-1803-and-1809"></a>Windows 버전 1709, 1803 및 1809

- 2019년 9월 보안 업데이트와 함께 제공되는 선택적 2019년 8월 업데이트의 첫 번째 변경 내용 집합.
- 2019년 10월 보안 업데이트와 함께 제공되는 선택적 2019년 9월 업데이트의 두 번째 변경 내용 집합.

  > [!NOTE]
  > 이 업데이트에서는 Microsoft Edge가 XML 프로토콜의 등록을 해제합니다.

- 2019년 11월 보안 업데이트와 함께 제공되는 선택적 2019년 10월 업데이트의 세 번째 변경 내용 집합.

  > [!NOTE]
  > 이 업데이트에서는 Microsoft Edge가 더 이상 전자책을 지원하지 않습니다.

다음 표에서는 각 변경 내용 집합의 특정 업데이트에 대한 세부 정보를 보여 줍니다.

| Windows 10 | 추가 정보 | 필수 다운로드 |
|--|--|--|
| 버전 1709 | [KB4525241](https://support.microsoft.com/help/4525241/windows-10-update-kb4525241) | [Windows 10 버전 1709에 대한 누적 업데이트](https://www.catalog.update.microsoft.com/Search.aspx?q=4525241) |
| 버전 1803  | [KB4525237](https://support.microsoft.com/help/4525237/windows-10-update-kb4525237) | [Windows 10 버전 1803에 대한 누적 업데이트](https://www.catalog.update.microsoft.com/Search.aspx?q=KB4525237) |
| 버전 1809  | [KB4523205](https://support.microsoft.com/help/4523205/windows-10-update-kb4523205) | [Windows 10 버전 1809에 대한 누적 업데이트](https://www.catalog.update.microsoft.com/Search.aspx?q=4523205) |
| 버전 1903 및 1909 |[KB4517389](https://support.microsoft.com/help/4517389/windows-10-update-kb4517389)  | [Windows 10 버전 1903 및 1909에 대한 누적 업데이트](https://www.catalog.update.microsoft.com/Search.aspx?q=4517389) |

## <a name="see-also"></a>참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge 설명서](./index.yml)