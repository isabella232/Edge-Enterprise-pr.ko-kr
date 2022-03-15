---
title: Windows 10 업데이트로 Microsoft Edge 배포
ms.author: ryhecht
author: RyanHechtMSFT
manager: tinad
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Windows 10 업데이트로 Microsoft Edge 배포
ms.openlocfilehash: 1f3a99259cb28c46e4f6f30de05fade6ac158336
ms.sourcegitcommit: 556aca8dde42dd66364427f095e8e473b86651a0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2022
ms.locfileid: "12445832"
---
# <a name="deploy-microsoft-edge-with-windows-10-updates"></a>Windows 10 업데이트로 Microsoft Edge 배포

이 문서에서는 Windows 10 업데이트를 사용하여 Microsoft Edge를 배포하는 사용자를 위한 정보를 제공합니다.

## <a name="for-windows-10-release-20h2"></a>Windows 10 릴리스 20H2의 경우

Windows 10 20H2 이상에는 Microsoft Edge 브라우저로 미리 설치된 웹 사이트가 포함됩니다. 그러나 Windows 10 20H2와 함께 제공된 에지 버전 84 및 Windows 10 21H2와 함께 제공된 에지 버전 92는 이제 기한이 지났습니다. Microsoft Edge 로그온한 후 새 버전으로 자동 업데이트되는 반면, 업데이트 타이밍은 다양한 요소에 따라 달라지기 때문에 이 방법은 다소 불편할 수 있습니다. 더 높은 제어를 원하는 조직의 경우 에지(안정 채널)가 사용자 로그온 전에 최신 버전으로 업데이트되도록 하려는 조직의 경우 다음 PowerShell 명령을 사용하여 OOBE 중 Edge를 강제로 Windows 있습니다.

`Start-Process -FilePath "C:\Program Files (x86)\Microsoft\EdgeUpdate\MicrosoftEdgeUpdate.exe" -argumentlist "/silent /install appguid={56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}&appname=Microsoft%20Edge&needsadmin=True"`

Autopilot을 Windows [Microsoft Win32](/mem/intune/apps/apps-win32-prepare) 콘텐츠 준비 도구를 사용하여 이 스크립트를 .intunewin 파일로 래핑할 수 있습니다. 그런 다음 원하는 경우 ESP(등록 상태 페이지)에 대한 필수 앱으로 설정할 수 있습니다.

> [!NOTE]
> 현재 대상 채널 다시 설정 또는 대상 버전 [](/deployedge/microsoft-edge-update-policies#target-channel-override) 다시 지정과 같은 정책을 활용하여 [](/deployedge/microsoft-edge-update-policies#targetversionprefix) 이전 버전의 Edge에 남아 있는 경우 위의 스크립트는 정책을 고려하지 않을 뿐만 아니라 단순히 최신 버전으로 업데이트됩니다. 기본적으로 Edge는 나중에 이러한 정책을 수신하는 경우를 포함하여 자체적으로 다운그레이드되지 않습니다.

## <a name="for-windows-10-releases-rs4-through-20h1"></a>Windows 10 릴리스 RS4~20H1의 경우

WSUS(Windows Server Update Services)에는 RS4에서 20H1까지 Windows 10의 각 버전에 대한 업데이트가 있으며, 해당 업데이트는 Microsoft Edge 레거시 데스크톱 앱을 제거하고 Microsoft Edge로 대체합니다. 자세한 내용은 [이 지원 문서](https://support.microsoft.com/topic/update-in-wsus-for-the-new-microsoft-edge-for-windows-10-version-1809-1903-1909-and-2004-october-29-2020-b4980418-4ec4-dee7-3b17-1c6499bd127c)를 참조하여 Windows 버전에 맞는 WSUS 업데이트를 확인하세요.

## <a name="for-windows-10-releases-prior-to-rs4-and-windows-7-81-and-earlier"></a>RS4 이전 Windows 10 릴리스(및 Windows 7, 8.1 이전 버전)의 경우

이 버전에서는 Microsoft Edge를 설치하기 위한 Windows 업데이트를 사용할 수 없습니다. [구성 관리자](/configmgr/apps/deploy-use/deploy-edge?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json) 또는 [Intune](/intune/apps/apps-windows-edge/?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json)과 같은 장치에 Microsoft Edge를 배포하기 위한 다른 옵션을 고려하세요.

## <a name="see-also"></a>참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge 배포 계획](deploy-edge-plan-deployment.md)
