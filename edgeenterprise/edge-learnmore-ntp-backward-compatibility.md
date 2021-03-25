---
title: 엔터프라이즈 새 탭 페이지의 이전 버전과의 호환성
ms.author: ruchir
author: dan-wesley
manager: vwehren
ms.date: 10/28/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 엔터프라이즈 새 탭 페이지의 이전 버전과의 호환성
ms.openlocfilehash: 5721db16c634250b3a586f6bd1b6b531a07815a5
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447262"
---
# <a name="backwards-compatibility-for-the-enterprise-new-tab-page"></a>엔터프라이즈 새 탭 페이지의 이전 버전과의 호환성

이 문서에서는 새 탭 페이지의 변경 내용과 사용자가 Microsoft Edge 버전 87 및 이전 버전과 호환하는 방법을 설명합니다.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 87 이상에 적용됩니다.

## <a name="information-feeds-from-single-endpoint"></a>단일 엔드포인트에서 정보 피드

새 버전의 엔터프라이즈 새 탭 페이지는 호환되는 Microsoft 365 콘텐츠를 MSN.com 엔드포인트를 통해 제공되는 업계와 관련된 호환되는 정보 피드와 결합합니다.

> [!NOTE]
> Office 365 콘텐츠는 원래 [Office.com](https://www.office.com) 도메인을 사용하여 서비스를 제공했습니다.

조직에 MSN.com 도메인에 대한 액세스가 제한된 경우 사용자에게 이 [URL](https://ntp.msn.com)에 대한 액세스 권한을 부여하는 것이 좋습니다.

MSN 도메인에 대한 액세스를 설정하는 데 더 많은 시간이 필요한 경우에는 새 탭 페이지에 Microsoft 뉴스 또는 Office 365 피드 환경을 선택할 수 있게 하는 [NewTabPageSetFeedType](./microsoft-edge-policies.md#newtabpagesetfeedtype)을 사용하는 것이 좋습니다.

### <a name="keep-using-officecom"></a>Office.com 계속 사용하기

 더 이상 사용되지 않는 Office.com 도메인을 계속 사용하도록 **NewTabPageSetFeedType** 정책을 구성할 수 있습니다.

> [!IMPORTANT]
> Microsoft Edge 버전 90이 릴리스되면 Office 365 콘텐츠를 제공하는 **NewTabPageSetFeedType** 정책과 Office.com 도메인의 작동이 중단됩니다.

다음 정책 설정은 엔터프라이즈 새 탭 페이지에서 Office.com 도메인의 Office 문서 콘텐츠를 렌더링하도록 합니다.

- 정책을 **필수**로 설정합니다.
- 정책 매핑의 값을 **Office (1) = Office 365 피드 환경**으로 설정합니다.

Office.com 전환을 사용할 수 없는 경우에는 Microsoft에 연락하여 피드백을 보내주세요. 또 다른 옵션은 [NewTabPageLocation](./microsoft-edge-policies.md#newtabpagelocation)을 구성하여 조직에서 허용하는 엔드포인트 URL을 가리키도록 하는 것입니다.

> [!NOTE]
> **NewTabPageLocation** 정책은 **NewTabPageSetFeedType** 정책도 구성된 경우 우선합니다.

## <a name="enterprise-users-will-now-get-microsoft-news-content-via-my-feed"></a>이제 엔터프라이즈 사용자가 내 피드를 통해 Microsoft 뉴스 콘텐츠를 받을 수 있습니다.

엔터프라이즈 새 탭 페이지에서는 Azure AD(azure Active Directory) 계정으로 로그인한 사용자에게 단일 보기로 **내 피드** 및 Office 365 콘텐츠의 업계 관련 정보를 제공합니다. 설정 플라이아웃에서 Microsoft 뉴스 옵션을 선택한 Azure AD(Azure Active Directory)로 로그인한 사용자의 경우 새 탭 페이지 보기가 **내 피드** 콘텐츠로 바뀝니다. 브라우저에서 새 탭 페이지를 열면 다음 스크린샷에 나와 있는 예제와 같이 표시됩니다.

![내 피드에서 콘텐츠를 보여 주는 새 탭 페이지.](media/microsoft-edge-ntp-backward-compatibility/microsoft-edge-ntp-myfeed-view.png)

> [!NOTE]
> Azure AD로 로그인하지 않은 사용자는 새 탭을 열 때 계속해서 MSN 뉴스 피드를 보게 됩니다.

## <a name="page-layout"></a>페이지 레이아웃

새 탭 페이지에 대한 변경으로 페이지 레이아웃에서 더 이상 두 가지 특정 콘텐츠 형식(Office 365 및 Microsoft 뉴스)을 제어하지 않아도 되므로 콘텐츠 토글을 사용할 수 없습니다. 다음 스크린샷은 페이지 레이아웃의 플라이아웃을 보여 줍니다.

![새 탭 페이지의 페이지 레이아웃 보기.](media/microsoft-edge-ntp-backward-compatibility/microsoft-edge-ntp-page-layout.png)

조직에 연결되지 않은 Microsoft 뉴스 콘텐츠에 계속 액세스하려면 다른 브라우저 프로필을 사용해야 합니다. *edge://settings/profiles*로 이동하고 Azure AD 프로필에서 로그아웃합니다. 이 작업을 수행하면 엔터프라이즈 새 탭 페이지의 표준 보기가 표시됩니다. 

## <a name="see-also"></a>참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [Internet Explorer 11의 엔터프라이즈 모드](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)