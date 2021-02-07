---
title: Windows 10 업데이트로 Microsoft Edge 배포
ms.author: ryhecht
author: RyanHechtMSFT
manager: tinad
ms.date: 02/05/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Windows 10 업데이트로 Microsoft Edge 배포
ms.openlocfilehash: a000e3426792df79d1450c838b7848be10d6b0ca
ms.sourcegitcommit: 16a92a51560fdba6f6480e4533453348f026c7ef
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2021
ms.locfileid: "11313953"
---
# Windows 10 업데이트로 Microsoft Edge 배포

이 문서에서는 Windows 10 업데이트를 사용하여 Microsoft Edge를 배포하는 사용자를 위한 정보를 제공합니다.

## Windows 10 릴리스 20H2의 경우

Windows 10 버전 20H2에는 Microsoft Edge가 기본 브라우저로 이미 설치되어 있습니다.

## Windows 10 릴리스 RS4~20H1의 경우

WSUS(Windows Server Update Services)에는 RS4에서 20H1까지 Windows 10의 각 버전에 대한 업데이트가 있으며, 해당 업데이트는 Microsoft Edge 레거시 데스크톱 앱을 제거하고 Microsoft Edge로 대체합니다. 자세한 내용은 [이 지원 문서](https://support.microsoft.com/topic/update-in-wsus-for-the-new-microsoft-edge-for-windows-10-version-1809-1903-1909-and-2004-october-29-2020-b4980418-4ec4-dee7-3b17-1c6499bd127c)를 참조하여 Windows 버전에 맞는 WSUS 업데이트를 확인하세요.

## RS4 이전 Windows 10 릴리스(및 Windows 7, 8.1 이전 버전)의 경우

이 버전에서는 Microsoft Edge를 설치하기 위한 Windows 업데이트를 사용할 수 없습니다. [구성 관리자](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-edge?toc=https://docs.microsoft.com/DeployEdge/toc.json&bc=https://docs.microsoft.com/DeployEdge/breadcrumb/toc.json) 또는 [Intune](https://docs.microsoft.com/intune/apps/apps-windows-edge/?toc=https://docs.microsoft.com/DeployEdge/toc.json&bc=https://docs.microsoft.com/DeployEdge/breadcrumb/toc.json)과 같은 장치에 Microsoft Edge를 배포하기 위한 다른 옵션을 고려하세요.

## 참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge 배포 계획](deploy-edge-plan-deployment.md)