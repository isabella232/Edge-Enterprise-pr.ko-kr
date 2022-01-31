---
title: 엔터프라이즈의 비즈니스에 대한 질문과 Microsoft Edge 질문과 대답(FAQ)
ms.author: collw
author: dan-wesley
manager: seanlynd
ms.date: 01/11/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 엔터프라이즈의 비즈니스에 대한 질문과 Microsoft Edge 질문과 대답(FAQ)
ms.openlocfilehash: 86f1fdee4697d8087014e35daf41b600eeb62471
ms.sourcegitcommit: e7f3098d8b7d91cae20b5778a71a87daababc312
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "12298324"
---
# <a name="microsoft-edge-frequently-asked-questions"></a>Microsoft Edge 질문과 대답

이 문서에는 기업의 비즈니스 요구에 대한 FAQ(Microsoft Edge 질문과 대답)가 포함되어 있습니다.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.

## <a name="how-do-i-know-which-version-of-microsoft-edge-i-have"></a>내가 가진 Microsoft Edge 버전이 무엇인지 확인하려면 어떻게 하나요?

오른쪽 위 모서리에서 타원 아이콘(**...**)을 선택하고 Microsoft Edge 를 **설정.** **Microsoft Edge 정보**를 선택하여 Microsoft Edge의 버전을 확인합니다.

## <a name="what-about-internet-explorer-11"></a>11 Internet Explorer 어떻게 하나요?

11 데스크톱 Internet Explorer 사용이 중지되어 2022년 6월 15일에는 지원이 중지됩니다. 범위에 있는 내용은 에 있는 Internet Explorer Windows 10 [를 Microsoft Edge.](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/) 현재 사용하는 동일한 IE11 앱과 사이트는 Internet Explorer 모드에서 Microsoft Edge로 열 수 있습니다. 자세한 내용은 Internet Explorer 데스크톱 앱 사용 중지 [FAQ를 참조하세요.](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)

## <a name="does-microsoft-edge-support-activex-controls-or-browser-helper-objects-like-silverlight-or-java"></a>Microsoft Edge 또는 ActiveX 같은 브라우저 도우미 개체 또는 브라우저 도우미 개체를 Java?

아니요. Microsoft Edge Silverlight 또는 ActiveX BOS(브라우저 도움말 개체)를 지원하지 Java. 그러나 Internet Explorer 11에서 ActiveX 컨트롤, BOS 또는 레거시 문서 모드를 사용하는 웹앱을 실행하는 경우 해당 웹앱을 IE 모드에서 실행하도록 구성할 수 Microsoft Edge. 자세한 내용은 [Microsoft Edge 구성](./edge-ie-mode.md)을 참조하세요.

## <a name="will-favorites-be-ported-over-from-the-current-version-of-microsoft-edge-or-will-i-have-to-re-add-them"></a>즐겨찾기 기능을 현재 버전의 Microsoft Edge 다시 추가해야 하나요?

Microsoft Edge, Chrome, Microsoft Edge Internet Explorer 및 Firefox(Win10의 경우)의 기존 설치에서 가져오기가 지원됩니다. 가져올 수 있는 설정은 책갈피, 기록, 암호 및 자동 입력(결제, 주소 및 일반 양식)입니다. 첫 실행 경험 또는 브라우저 설정에서 가져오도록 선택할 수 있습니다.

## <a name="whats-the-difference-between-the-stable-beta-dev-and-canary-channelsbuilds"></a>안정, Beta, Dev 및 Canary 채널/빌드의 차이점은 무엇인가요?

안정된 Microsoft Edge 채널은 조직 전체에서 파일럿 및 평가를 할 준비가 [](https://aka.ms/EdgeEnterprise) 된 엔터프라이즈 중심 기능을 사용하여 제공하는 가장 안정적인 채널입니다. Beta 채널을 사용하면 대표적인 사용자로 다음 안정 릴리스의 유효성을 검사할 수 있습니다. 안정 및 베타 채널은 약 6주마다 업데이트됩니다. Dev 및 Canary 채널은 각각 매주 및 매일 업데이트됩니다. 오프라인 설치 관리자(MSIS 및 PKG 파일)는 Stable, Beta 및 Dev 채널에서만 사용할 수 있습니다. 자세한 내용은 [Microsoft Edge 채널 개요](./microsoft-edge-channels.md)를 참조하세요.

## <a name="what-kind-of-extension-support-do-i-have-with-microsoft-edge"></a>내선과 함께 어떤 종류의 확장 지원이 Microsoft Edge?

Microsoft Edge 내부자 추가 기능 및 Microsoft Edge [확장을](https://go.microsoft.com/fwlink/?linkid=2081222) [Chrome 웹 스토어.](https://go.microsoft.com/fwlink/?linkid=2072338)

## <a name="do-you-support-mobile-device-management-mdm-and-microsoft-intune"></a>MDM(모바일 장치 관리)과 Microsoft Intune을 지원하나요?

그렇습니다. 이제 Microsoft Intune 및 MDM(모바일 장치 관리)을 사용한 Windows 10용 Microsoft Edge 구성이 지원됩니다. 자세한 내용은 [Microsoft Intune을 사용하여 Microsoft Edge 구성](./configure-edge-with-intune.md) 및 [모바일 장치 관리를 사용하여 Microsoft Edge 구성](./configure-edge-with-mdm.md)을 참조하세요.

## <a name="does-windows-server-update-services-wsus-support-the-initial-deployment-of-microsoft-edge"></a>WSUS(Windows Server Update Services)에서 초기 배포를 Microsoft Edge?

예. [Microsoft](https://www.catalog.update.microsoft.com/Search.aspx?q=the%20new%20microsoft%20edge%20for%20windows) 업데이트 카탈로그에는 WSUS를 통해 초기 배포에 사용할 수 있는 패키지가 Microsoft Edge 있습니다. 초기 배포 후 자동 업데이트는 기본적으로 구성됩니다. 자세한 내용은 새로운 Windows 10용 Microsoft Edge, 버전 1809, 1903, 1909, 2004에 대한 [WSUS의 업데이트: 2020년 10월 29일](https://support.microsoft.com/help/4584642/update-in-wsus-for-the-new-microsoft-edge)을 참조하세요.

 [ConfigMgr과](/configmgr/apps/deploy-use/deploy-edge?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json)같은 구성 관리 도구를 통해 수동 업데이트를 할 수 있습니다.

## <a name="are-initial-preferences-supported"></a>초기 기본 설정이 지원하나요?

예. 자세한 내용은 첫 실행에 Microsoft Edge 기본 설정을 사용하여 기본 설정 [구성을 참조하세요.](./initial-preferences-support-on-microsoft-edge-browser.md)

## <a name="see-also"></a>참고 항목

- [Microsoft Edge 설명서 방문 페이지](./index.yml)
- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
  