---
title: Windows 10 업데이트로 Microsoft Edge 배포
ms.author: ryhecht
author: RyanHechtMSFT
manager: tinad
ms.date: 05/04/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Windows 10 업데이트로 Microsoft Edge 배포
ms.openlocfilehash: eec21e3f797166b31b0ac632f94103b866491066
ms.sourcegitcommit: 592f6e40b13e28af588473b2a75c3ae697e5db2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2022
ms.locfileid: "12505691"
---
# <a name="deploy-microsoft-edge-with-windows-10-updates"></a>Windows 10 업데이트로 Microsoft Edge 배포

이 문서에서는 Windows 10 업데이트를 사용하여 Microsoft Edge를 배포하는 사용자를 위한 정보를 제공합니다.

## <a name="for-windows-10-release-20h2"></a>Windows 10 릴리스 20H2의 경우

Windows 10 20H2 이상에는 기본 브라우저로 미리 설치된 Microsoft Edge 포함됩니다. 그러나 Windows 10 20H2와 함께 제공된 Edge 버전 84 및 Windows 10 21H2와 함께 제공되는 Edge 버전 92는 이제 오래되었습니다. Microsoft Edge 사용자가 로그온한 후 자동으로 최신 버전으로 업데이트되지만 업데이트 타이밍은 다양한 요인에 따라 달라지기 때문에 다소 예측할 수 없습니다. 더 큰 제어를 원하고 사용자 로그온 전에 Edge(안정적인 채널)가 최신 버전으로 업데이트되도록 하려는 조직의 경우 다음 PowerShell 명령을 사용하여 OOBE를 Windows 동안 Edge 업데이트를 강제 적용할 수 있습니다.

`Start-Process -FilePath "C:\Program Files (x86)\Microsoft\EdgeUpdate\MicrosoftEdgeUpdate.exe" -argumentlist "/silent /install appguid={56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}&appname=Microsoft%20Edge&needsadmin=True"`

Windows Autopilot을 사용하는 경우 [Microsoft Win32 콘텐츠 준비 도구를](/mem/intune/apps/apps-win32-prepare) 사용하여 이 스크립트를 .intunewin 파일로 래핑할 수 있습니다. 그런 다음 원하는 경우 ESP(등록 상태 페이지)에 필요한 앱으로 설정할 수 있습니다.

> [!NOTE]
> 현재 [대상 채널 재정](/deployedge/microsoft-edge-update-policies#target-channel-override)의 또는 [대상 버전 재정](/deployedge/microsoft-edge-update-policies#targetversionprefix)의와 같은 정책을 활용하여 이전 버전의 Microsoft Edge 유지하는 경우 위의 스크립트는 정책을 고려하지 않으며 최신 버전으로 업데이트됩니다. 기본적으로 Microsoft Edge 나중에 이러한 정책을 수신하는 경우를 포함하여 자체 다운그레이드하지 않습니다.

## <a name="for-windows-10-releases-rs4-through-20h1"></a>Windows 10 릴리스 RS4~20H1의 경우

WSUS(Windows Server Update Services)에는 RS4에서 20H1까지 Windows 10의 각 버전에 대한 업데이트가 있으며, 해당 업데이트는 Microsoft Edge 레거시 데스크톱 앱을 제거하고 Microsoft Edge로 대체합니다. 자세한 내용은 [이 지원 문서](https://support.microsoft.com/topic/update-in-wsus-for-the-new-microsoft-edge-for-windows-10-version-1809-1903-1909-and-2004-october-29-2020-b4980418-4ec4-dee7-3b17-1c6499bd127c)를 참조하여 Windows 버전에 맞는 WSUS 업데이트를 확인하세요.

## <a name="for-windows-10-releases-prior-to-rs4-and-windows-7-81-and-earlier"></a>RS4 이전 Windows 10 릴리스(및 Windows 7, 8.1 이전 버전)의 경우

이 버전에서는 Microsoft Edge를 설치하기 위한 Windows 업데이트를 사용할 수 없습니다. [구성 관리자](/configmgr/apps/deploy-use/deploy-edge?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json) 또는 [Intune](/intune/apps/apps-windows-edge/?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json)과 같은 장치에 Microsoft Edge를 배포하기 위한 다른 옵션을 고려하세요.

## <a name="see-also"></a>참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge 배포 계획](deploy-edge-plan-deployment.md)
