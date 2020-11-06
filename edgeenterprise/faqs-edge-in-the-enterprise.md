---
title: 엔터프라이즈의 Edge에 대한 FAQ
ms.author: jwhit
author: jwhit-MSFT
manager: laurawi
ms.date: 11/04/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 엔터프라이즈에서 Microsoft Edge 배포에 대한 FAQ
ms.openlocfilehash: e689967cbad950e2969535bad0dd63d5d7081798
ms.sourcegitcommit: 12827458f6217f443128e826c1d18d36d401d03b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2020
ms.locfileid: "11154323"
---
# 엔터프라이즈의 Microsoft Edge에 대한 FAQ

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.

## 내가 가진 Microsoft Edge 버전이 무엇인지 확인하려면 어떻게 하나요?

Microsoft Edge의 오른쪽 상단 모서리에서 줄임표(**...**) 아이콘을 클릭한 다음 **설정**을 클릭합니다. **Microsoft Edge 정보**를 선택하여 Microsoft Edge의 버전을 확인합니다.

## Internet Explorer 11에서 계속 업데이트를 받을 수 있나요?

Microsoft는 Internet Explorer를 안정적이고 안전한 브라우저로 계속 지원하기 위해 노력하고 있습니다. Internet Explorer는 여전히 Windows의 구성 요소이며 이 브라우저가 설치된 OS의 지원 수명 주기를 따릅니다. 자세한 내용은 [수명 주기 FAQ - Internet Explorer](https://support.microsoft.com/help/17454/)를 참조하세요. Microsoft에서 계속해서 Internet Explorer를 지원하고 업데이트하지만 최신 기능 및 플랫폼 업데이트는 Microsoft Edge에서만 사용할 수 있습니다.

## 새 버전을 시험 사용할 때 Microsoft Edge(레거시 Microsoft Edge)의 현재 버전을 함께 실행할 수 있나요?

예, 그렇습니다. 2020년 1월 15일 이후 새 버전의 Microsoft Edge(Chromium 기반)는 Windows 10 버전 1803 이상을 실행하는 Home 및 Pro 에디션 디바이스에 배포됩니다. 도메인에 가입된 디바이스는 이 업데이트에서 제외됩니다. 자세한 내용은 [Microsoft Edge 업데이트 개요](https://docs.microsoft.com/deployedge/microsoft-edge-blocker-toolkit#overview)를 참조하세요. Microsoft Edge의 다음 버전을 평가할 때 레거시 Microsoft Edge를 나란히 설치할 수 있습니다. 자세한 내용은 [Microsoft Edge의 이전 버전에 액세스하는 방법](https://docs.microsoft.com/deployedge/microsoft-edge-sysupdate-access-old-edge)을 참조하세요. 또한 각 신규 Microsoft Edge 채널도 모두 나란히 설치를 지원합니다. 자세한 내용은 [Microsoft Edge 채널 개요](https://docs.microsoft.com/deployedge/microsoft-edge-channels)를 참조하세요.

## Microsoft Edge(Chromium 기반)에서 ActiveX 컨트롤이나 Silverlight 또는 Java 같은 BHO를 지원합니까?

아니요. Microsoft Edge에서 ActiveX 컨트롤이나 Silverlight 또는 Java 같은 BHO를 지원하지 않습니다. 그러나 Internet Explorer 11에서 ActiveX 컨트롤, BHOs 또는 레거시 문서 모드를 사용하는 웹 앱을 실행하는 경우 새 Microsoft Edge에서 IE 모드로 실행되도록 구성할 수 있습니다. 자세한 내용은 [Microsoft Edge 구성](https://docs.microsoft.com/DeployEdge/edge-ie-mode)을 참조하세요.

## 현재 버전의 Microsoft Edge에서 즐겨찾기를 가져올 수 있나요, 아니면 다시 추가해야 하나요?

현재 Microsoft Edge는 Microsoft Edge, Chrome, Internet Explorer 및 Firefox의 기존 설치에서 가져오기 작업을 지원합니다(Win10). 가져오기에 대해 다음 설정이 지원됩니다. 책갈피, 기록, 암호 및 자동 채우기(결제, 주소 및 일반 양식)입니다. 첫 실행 경험 또는 브라우저 설정에서 가져오도록 선택할 수 있습니다.  

## 안정, Beta, Dev 및 Canary 채널/빌드의 차이점은 무엇인가요?

다음 버전 Microsoft Edge의 안정 채널은 Microsoft에서 제공하는 가장 안정된 미리 보기 채널이며, 엔터프라이즈 중심 기능을 통해 조직에서 [파일럿 및 평가](https://aka.ms/EdgeEnterprise)를 수행할 수 있습니다. Beta 채널을 사용하면 대표적인 사용자로 다음 안정 릴리스의 유효성을 검사할 수 있습니다. 안정 및 배타 채널은 약 6주마다 업데이트됩니다. Dev 및 Canary 채널은 각각 매주 및 매일 업데이트됩니다. 오프라인 설치 관리자(MSI 및 INSTALLER.PKG 파일)는 안정적인, 베타 및 개발자 채널에만 사용할 수 있습니다. 자세한 내용은 [Microsoft Edge 채널 개요](https://docs.microsoft.com/deployedge/microsoft-edge-channels)를 참조하세요.

## 새 버전의 Microsoft Edge에는 어떤 종류의 확장 지원이 제공되나요?

Microsoft Edge는 [Microsoft Edge 참가자 프로그램 추가 기능](https://go.microsoft.com/fwlink/?linkid=2081222) 및 [Chrome 웹 스토어](https://go.microsoft.com/fwlink/?linkid=2072338)의 확장을 지원합니다.

## MDM(모바일 장치 관리)과 Microsoft Intune을 지원하나요?

그렇습니다. 이제 Microsoft Intune 및 MDM(모바일 장치 관리)을 사용한 Windows 10용 Microsoft Edge 구성이 지원됩니다. 자세한 내용은 [Microsoft Intune을 사용하여 Microsoft Edge 구성](configure-edge-with-intune.md) 및 [모바일 장치 관리를 사용하여 Microsoft Edge 구성](configure-edge-with-mdm.md)을 참조하세요.

## WSUS는 새 Microsoft Edge의 초기 배포를 지원하나요?

예. [Microsoft 업데이트 카탈로그](https://www.catalog.update.microsoft.com/Search.aspx?q=the%20new%20microsoft%20edge%20for%20windows)에는 WSUS를 통해 새 Microsoft Edge를 초기 배포하는 데 사용할 수 있는 패키지가 있습니다. 초기 배포 후 자동 업데이트는 기본적으로 구성됩니다. 자세한 내용은 새로운 Windows 10용 Microsoft Edge, 버전 1809, 1903, 1909, 2004에 대한 [WSUS의 업데이트: 2020년 10월 29일](https://support.microsoft.com/help/4584642/update-in-wsus-for-the-new-microsoft-edge)을 참조하세요.

수동 업데이트는 [ConfigMgr](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-edge?toc=https://docs.microsoft.com/DeployEdge/toc.json&bc=https://docs.microsoft.com/DeployEdge/breadcrumb/toc.json)과 같은 구성 관리 도구를 통해 수행할 수 있습니다.

## 참고 항목

- [Microsoft Edge 설명서 방문 페이지](https://docs.microsoft.com/DeployEdge/)
- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
