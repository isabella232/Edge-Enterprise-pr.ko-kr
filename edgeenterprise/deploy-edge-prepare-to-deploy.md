---
title: 사용자 환경의 Microsoft Edge
ms.author: ryhecht
author: RyanHechtMSFT
manager: tinad
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 사용자 환경의 Microsoft Edge
ms.openlocfilehash: 2bcf47330da87775204db700c3f2eb5fe77c10326e6fad89b85ddf546a3002c7
ms.sourcegitcommit: d44c0997ffe40d67421312ed96e7766da947eaa0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "11726611"
---
# <a name="microsoft-edge-in-your-environment"></a>사용자 환경의 Microsoft Edge

이 문서에서는 Microsoft Edge 레거시가 서비스 종료에 도달할 때 Microsoft Edge를 배포하는 방법을 설명합니다.

Microsoft Edge 제품 팀의 [블로그 게시물](https://aka.ms/EdgeLegacyEOS)에 따라 Microsoft Edge 레거시 데스크톱 응용 프로그램에 대한 지원은 2021년 3월 9일에 종료됩니다. 4월에 업데이트 화요일(또는 "B") 릴리스를 적용하면 Windows 10 RS4에서 20H1까지 실행되는 장치에서 Microsoft Edge 레거시가 제거되고 Microsoft Edge로 대체됩니다.

## <a name="how-to-prepare"></a>준비 방법

4월 업데이트 화요일 릴리스와 함께 Windows 10 RS4에서 20H1 장치에 Microsoft Edge 설치 준비를 하려면 [Microsoft Edge의 배포 계획](deploy-edge-plan-deployment.md)을 읽어보시기 바랍니다.

배포를 계획한 후 다음 방법 중 하나를 사용하여 Microsoft Edge 배포를 준비합니다.

- **그룹 정책을 설치하여 Microsoft Edge업데이트 방법을 사용자 지정합니다**. 자세한 내용은 [Windows에서 Microsoft Edge 정책 설정 구성](configure-microsoft-edge.md)을 참조하고 [업데이트 정책 참조](microsoft-edge-update-policies.md)에 특히 주의하세요. 4월의 업데이트 화요일 릴리스를 설치하기 전에 그룹 정책을 설치하여 업데이트를 관리하는 경우 Microsoft Edge는 즉시 정책 준수를 시작됩니다. 설치된 그룹 정책이 없는 경우 Microsoft Edge가 자동으로 업데이트됩니다.

- **서비스 종료일인 2021년 3월 9일전에 Microsoft Edge 레거시 데스크톱 응용 프로그램을 제거하고 Microsoft Edge를 배포합니다**. Windows 10 RS4~20H1의 경우 Windows 업데이트를 사용하여 이 작업을 할 수 있습니다. 자세한 내용은 [Windows 10 업데이트로 Microsoft Edge 배포](deploy-edge-with-windows-10-updates.md)를 참조하세요.

## <a name="see-also"></a>참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge 배포 계획](deploy-edge-plan-deployment.md)