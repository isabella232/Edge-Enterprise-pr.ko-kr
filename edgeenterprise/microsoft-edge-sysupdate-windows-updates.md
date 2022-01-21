---
title: Microsoft Edge를 지원하기 위한 Windows 업데이트
ms.author: jtkim
author: dan-wesley
manager: srugh
ms.date: 11/17/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge를 지원하기 위한 Windows 업데이트입니다.
ms.openlocfilehash: 85f60b3ee09154c702debcfb222567996be9462f
ms.sourcegitcommit: e7f3098d8b7d91cae20b5778a71a87daababc312
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "12298166"
---
# <a name="windows-updates-to-support-the-next-version-of-microsoft-edge"></a>다음 버전 Microsoft Edge를 지원하기 위한 Windows 업데이트

이 문서에서는 다음 버전의 Microsoft Edge를 지원하도록 Windows를 업데이트하는 방법을 설명합니다.

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
  > 사용자 수준 설치는 이전 동작을 트리거하지 않습니다.

위 변경 내용과 함께 다음 버전 Microsoft Edge의 안정 채널이 설치되어 있는지 여부에 관계없이 발생하는 변경 사항이 있습니다.

- Microsoft Edge는 다음 버전 Microsoft Edge가 지원하지 않는 전자책 및 XML 프로토콜의 등록을 취소합니다. 사용자가 이러한 프로토콜을 열려고 하면 기본 앱을 선택하라는 대화 상자가 표시됩니다. Microsoft Store를 방문하여 전자책 독자를 위한 권장 사항을 확인하세요.
  
## <a name="older-versions-of-windows"></a>이전 버전의 Windows

Windows 10 RS4 이전 버전을 실행하는 장치에 Microsoft Edge를 배포하려면 [구성 관리자](https://docs.microsoft.com/mem/configmgr/apps/deploy-use/deploy-edge?bc=https%3A%2F%2Fdocs.microsoft.com%2FDeployEdge%2Fbreadcrumb%2Ftoc.json&toc=https%3A%2F%2Fdocs.microsoft.com%2FDeployEdge%2Ftoc.json), [Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-windows-edge?bc=https%3A%2F%2Fdocs.microsoft.com%2FDeployEdge%2Fbreadcrumb%2Ftoc.json&toc=https%3A%2F%2Fdocs.microsoft.com%2FDeployEdge%2Ftoc.json) 또는 지원되는 Windows 10 버전으로 업그레이드하세요. 다음 문서에서는 현재 지원되는 Windows 10 및 Windows 11 버전이 나열되어 있습니다.

- [지원되는 버전의 Windows 클라이언트](/windows/release-health/supported-versions-windows-client)

> [!NOTE]
> Windows 10 RS4-20H1의 경우 Microsoft Edge를 받으려면 2021년 5월 이후에 나온 Windows LCU를 배포합니다. 자세한 내용은 [Windows 10 업데이트 기록](https://support.microsoft.com/topic/windows-10-update-history-1b6aac92-bf01-42b5-b158-f80c6d93eb11) 참조

> [!IMPORTANT]
> 여기에 나열되지 않은 업데이트가 필요한 경우 Windows 업데이트를 실행하거나 관리자에게 문의하세요.

## <a name="see-also"></a>참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge 설명서](./index.yml)