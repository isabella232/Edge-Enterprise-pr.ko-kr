---
title: Microsoft Edge 엔드포인트에 대한 허용 목록
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 11/02/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge 엔드포인트에 대한 허용 목록
ms.openlocfilehash: 9e6a87290f2f73ba11bc98eecd3aa693c35b5ace
ms.sourcegitcommit: 3e155a4395ae3a2ae478eb4b52c436b1c1f2e5db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "12155214"
---
# <a name="allow-list-for-microsoft-edge-endpoints"></a>Microsoft Edge 엔드포인트에 대한 허용 목록

Microsoft Edge 기능을 지원하려면 인터넷에 연결되어 있어야 합니다. 이 문서에서는 방화벽 및 기타 보안 메커니즘을 통해 통신을 보장하기 위해 허용 목록에 추가해야 하는 도메인 URL에 대해 알아봅니다.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.

## <a name="domain-urls-to-allow"></a>허용할 도메인 URL

Microsoft Edge에 대해 다음 도메인 URL을 허용합니다.

### <a name="update-service"></a>업데이트 서비스

Microsoft Edge에서 새 업데이트를 확인하는 데 사용하는 서비스입니다.

- `https://msedge.api.cdp.microsoft.com`

### <a name="experimentation-and-configuration-service"></a>실험 및 구성 서비스

- `https://config.edge.skype.com`

### <a name="download-locations-for-microsoft-edge"></a>Microsoft Edge의 다운로드 위치

위치 Microsoft Edge는 처음 설치하는 동안 또는 업데이트를 사용할 수 있을 때 다운로드할 수 있습니다. 다운로드 위치는 업데이트 서비스에 의해 결정됩니다.

#### <a name="http"></a>HTTP

- `http://msedge.f.tlu.dl.delivery.mp.microsoft.com`
- `http://msedge.f.dl.delivery.mp.microsoft.com`
- `http://msedge.b.tlu.dl.delivery.mp.microsoft.com`
- `http://msedge.b.dl.delivery.mp.microsoft.com`

#### <a name="https"></a>HTTPS

- `https://msedge.sf.tlu.dl.delivery.mp.microsoft.com`
- `https://msedge.sf.dl.delivery.mp.microsoft.com`
- `https://msedge.sb.tlu.dl.delivery.mp.microsoft.com`
- `https://msedge.sb.dl.delivery.mp.microsoft.com`

  > [!TIP]
  > 다운로드 위치 허용 목록을 단순화하려면 와일드 카드를 사용할 수 있습니다. `*.dl.delivery.mp.microsoft.com`

### <a name="download-locations-for-microsoft-edge-extensions"></a>Microsoft Edge 확장 프로그램의 다운로드 위치

위치 Microsoft Edge 확장 프로그램은 처음 설치하는 동안 또는 업데이트를 사용할 수 있을 때 다운로드할 수 있습니다. 다운로드 위치는 업데이트 서비스에 의해 결정됩니다.

#### <a name="http"></a>HTTP

- `http://msedgeextensions.f.tlu.dl.delivery.mp.microsoft.com`
- `http://msedgeextensions.f.dl.delivery.mp.microsoft.com`
- `http://msedgeextensions.b.tlu.dl.delivery.mp.microsoft.com`
- `http://msedgeextensions.b.dl.delivery.mp.microsoft.com`

#### <a name="https"></a>HTTPS

- `https://msedgeextensions.sf.tlu.dl.delivery.mp.microsoft.com`
- `https://msedgeextensions.sf.dl.delivery.mp.microsoft.com`
- `https://msedgeextensions.sb.tlu.dl.delivery.mp.microsoft.com`
- `https://msedgeextensions.sb.dl.delivery.mp.microsoft.com`

  > [!TIP]
  > 다운로드 위치 허용 목록을 단순화하려면 와일드 카드를 사용할 수 있습니다. `*.dl.delivery.mp.microsoft.com`

### <a name="optionally-for-download-delivery-optimization"></a>선택적으로 다운로드 배달 최적화

배달 최적화에 대한 자세한 내용은 [Windows 10 업데이트에 대한 배달 최적화](/windows/deployment/update/waas-delivery-optimization)를 참조하세요.

- 클라이언트 및 서비스 간 통신: `*.do.dsp.mp.microsoft.com`(HTTP 포트 80, HTTPS 포트 443)
- 클라이언트 간 통신: 인바운드 트래픽에 TCP 포트 7680이 열려 있어야 함

### <a name="sync"></a>Sync

이러한 엔드 포인트는 동기화된 데이터의 읽기 및 쓰기, 보안 데이터에 대한 권한 관리, 새 동기화 데이터가 사용 가능할 때 브라우저에 알림 등을 관리합니다.

- Microsoft Edge 동기화 서비스 엔드포인트:

  - `https://edge-enterprise.activity.windows.com`
  - `https://edge.activity.windows.com`

- Azure Information Protection 엔드포인트:

  - `https://api.aadrm.com` (대부분의 테넌트 경우)
  - `https://api.aadrm.de` (독일의 테넌트 경우)
  - `https://api.aadrm.cn` (중국의 테넌트 경우)

- [Windows 알림 서비스 엔드 포인트](/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)

### <a name="cloud-site-list-management"></a>클라우드 사이트 목록 관리

IE(Microsoft Edge) 모드의 클라우드 호스팅 사이트 목록을 다운로드하는 데 Internet Explorer 서비스입니다. 자세한 내용은 클라우드 사이트 목록 [관리를 참조하세요.](https://aka.ms/CloudSiteList)

- `https://edge.microsoft.com/`

## <a name="other-browser-support-services"></a>기타 브라우저 지원 서비스

추적 방지, 인증서 해지 목록 및 기타 브라우저 구성 요소 업데이트와 같은 브라우저 기능에 대한 메타데이터를 제공합니다. 다운로드 가능한 맞춤법 검사 사전과 광고를 차단하는 차단 목록을 제공합니다. 컬렉션, 자동 채우기 및 확장 프로그램 스토어와 같은 브라우저 기능을 지원하는 서비스를 제공합니다.

- `http://edge.microsoft.com/`
- `https://edge.microsoft.com/`

## <a name="see-also"></a>기타 참조

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge 설명서 방문 페이지](./index.yml)
- [Windows 10 Enterprise, 버전 1903에 대한 연결 엔드포인트 관리](/windows/privacy/manage-windows-1903-endpoints)