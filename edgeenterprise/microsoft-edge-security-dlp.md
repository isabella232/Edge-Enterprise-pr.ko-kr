---
title: 데이터 손실 방지의 Microsoft Edge
ms.author: archandr
author: dan-wesley
manager: seanlynd
ms.date: 11/22/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 데이터 손실 방지(DLP)를 Microsoft Edge
ms.openlocfilehash: b20a9eb965256adcebd47a5eb1805fb4f0a5992b
ms.sourcegitcommit: e7f3098d8b7d91cae20b5778a71a87daababc312
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "12297906"
---
# <a name="understand-data-loss-prevention-dlp-in-microsoft-edge"></a>데이터 손실 방지(DLP)를 Microsoft Edge

이 문서에서는 Microsoft Edge DLP 및 WIP(정보 보호)를 사용하여 DLP(데이터 손실 방지)Windows 방법을 설명합니다.

## <a name="dlp-defined"></a>DLP 정의

DLP(데이터 손실 방지)는 무단 노출로부터 기업의 중요한 데이터를 식별하고 보호하는 기술 시스템입니다. 비즈니스 표준 및 산업 규정을 준수하려면 조직에서 중요한 정보를 보호하고 무단 노출을 방지해야 합니다. 중요한 정보에는 재무 데이터 또는 개인 정보가 포함됩니다. 개인 정보의 몇 가지 예로는 신용 카드 번호, 주민등록번호 및 의료 기록이 있습니다.

원격 작업은 DLP 사용에 대한 강조를 증가시켰습니다. 장치에 대한 개인 및 업무 활동의 증가에 따라 기업에서 회사 데이터를 직장 밖으로 무단 공유하는 위험이 증가하고 있습니다.

이러한 혼합된 사용자 활동은 다양한 공용 및 개인 네트워크를 통해 개인 장치와 회사 장치 간에 데이터가 이동되는 디바이스에도 확산되었습니다. 그 결과, 중요한 데이터가 노출되는 위험성이 크게 증가하였습니다.

Microsoft Edge는 기본적으로 두 가지 DLP 솔루션인 Microsoft Endpoint DLP와 WIP(Windows Information Protection)를 지원합니다.

## <a name="microsoft-endpoint-data-loss-prevention-endpoint-dlp"></a>Microsoft 끝점 데이터 손실 방지(끝점 DLP)

Microsoft Endpoint DLP는 데이터 중심 보호와 같은 최신 개념을 사용하는 차세대 데이터 손실 방지 기능입니다. 디바이스에서 더 Windows 10 플러그 인이 Microsoft Edge 필요 없는 기본 제공 기능을 제공합니다.

> [!NOTE]
> 이는 Microsoft Edge 버전 85 이상에 적용됩니다.

Endpoint DLP에 대해 자세히 알아보려면 다음 리소스를 사용하세요.

- [비디오: Microsoft Edge 및 DLP(데이터 손실 방지)](microsoft-edge-video-security-dlp.md)
- [Microsoft 365 끝점 데이터 손실 방지에 대한 자세한 정보](/microsoft-365/compliance/endpoint-dlp-learn-about?preserve-view=true&view=o365-worldwide)
- [끝점 데이터 손실 방지 시작하기](/microsoft-365/compliance/endpoint-dlp-getting-started?preserve-view=true&view=o365-worldwide)

Microsoft Edge 파일에 대해 관리자가 구성한 정책을 적용하고 비호준 활동에 대한 감사 이벤트를 기록합니다.

Windows 10을 실행하는 장치에서 감사하고 관리할 수 있는 일부 사용자 활동에는 다음이 포함됩니다.

- 파일 업로드: 인증되지 않은 클라우드 위치에 중요한 파일 업로드를 보호합니다. <!-- The next 3 screenshots show a sequence where a user tries to drop a sensitive data file on to their local storage.-->
- 클립보드 보호: 중요한 데이터가 파일에서 복사되지 않도록 보호합니다.
- 인쇄 보호: 중요한 파일이 인쇄되지 않도록 보호합니다.
- USB/네트워크에 저장: 중요한 파일이 이동식 USB 저장소 또는 인증되지 않은 네트워크 위치에 저장되지 않도록 보호합니다.

감사 및 관리할 수 있는 사용자 활동에 대한 자세한 정보는 [모니터링 및 조치를 취할 수 있는 Endpoint 활동](/microsoft-365/compliance/endpoint-dlp-learn-about?preserve-view=true&view=o365-worldwide#endpoint-activities-you-can-monitor-and-take-action-on)을 참조하세요.

## <a name="windows-information-protection"></a>Windows Information Protection

Microsoft Edge가 WIP(Windows Information Protection)를 지원하는 방법에 대한 설명은 [Windows Information Protection 지원](./microsoft-edge-security-windows-information-protection.md)을 참조하세요. 다음 섹션에서 시스템 요구 사항, 이점 및 지원되는 기능에 대한 자세한 정보를 확인할 수 있습니다.

- [시스템 요구 사항](./microsoft-edge-security-windows-information-protection.md#system-requirements)
- [Windows Information Protection의 이점](./microsoft-edge-security-windows-information-protection.md#windows-information-protection-benefits)
- [Microsoft Edge에서 지원되는 WIP 기능](./microsoft-edge-security-windows-information-protection.md#wip-features-supported-in-microsoft-edge)

## <a name="see-also"></a>참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [비디오: 데이터 손실 방지 - Microsoft Edge](https://www.youtube.com/watch?v=dLD04U9eTqg)
- [데이터 손실 방지 개요](/microsoft-365/compliance/data-loss-prevention-policies?preserve-view=true&view=o365-worldwide)
- [Windows Information Protection을 사용하여 엔터프라이즈 데이터 보호](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)