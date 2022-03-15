---
title: Microsoft Edge 및 분할 터널 VPN 지원
ms.author: juso
author: dan-wesley
manager: harneets
ms.date: 01/24/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: WebRTC에 Microsoft Edge 및 분할 터널 VPN 지원 사용(Web Real-Time Communication)
ms.openlocfilehash: 73bd6494ebb95db23d2701cc9dab4023af28eb70
ms.sourcegitcommit: 556aca8dde42dd66364427f095e8e473b86651a0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2022
ms.locfileid: "12445935"
---
# <a name="split-tunnel-vpn-support-for-webrtc-web-real-time-communication"></a>WebRTC(Web Real-Time Communication)에 대한 분할 터널 VPN 지원
  
이 문서에서는 WebRTC에 Microsoft Edge 및 분할 터널 VPN 지원에 대해 설명합니다. 이 지원을 통해 엔터프라이즈 고객은 엔터프라이즈에서 피어 투 피어 트래픽에 대한 VPN 분할 터널링의 이점을 Microsoft Edge. VPN 분할 터널링은 사용자의 피어 투 피어 미디어 스트리밍 품질을 개선하고 VPN 서버 부하를 줄입니다.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 96 이상에 적용됩니다.

## <a name="what-is-vpn-split-tunneling-and-why-should-i-use-it"></a>VPN 분할 터널링이란 무엇일까요? 이 터널링을 사용하는 이유는 무엇입니까?

VPN 분할 터널링은 사용자가 모든 트래픽을 VPN을 통해 라우팅하는 대신 두 개의 다른 네트워크를 트래픽에 사용할 수 있도록 하는 기능입니다. Windows 응용 프로그램에 대해 이 기능을 지원하고, 기본 응용 프로그램에서 VPN 분할 터널링을 사용하는 Microsoft 365 응용 프로그램에 대해 VPN 분할 터널링도 Windows. 자세한 내용은 [Overview: VPN split tunneling with Office 365 - Microsoft 365 Enterprise](/microsoft-365/enterprise/microsoft-365-vpn-split-tunnel?view=o365-worldwide&preserve-view=true). Microsoft Edge VPN 분할 터널링 구성도 적용했지만 피어 투 피어 트래픽에 대한 지원이 누락되었습니다.

VPN을 통해 회사 네트워크 또는 클라우드 인프라를 통해 피어 투 피어 사용자 트래픽을 라우팅하는 고객의 요구에 대해 들어왔습니다.기본 응용 프로그램과 비교할 때 브라우저에서 사용자의 화상 회의 통화 품질이 좌절되었습니다.기본 환경의 설명처럼 피어 투 피어 트래픽용 VPN 분할 터널링은 VPN이 아닌 일반 인터넷 연결을 통해 라우팅하여 사용자 비디오 통화의 품질을 향상시킬 수 있습니다. 또한 지정된 트래픽을 VPN에서 라우팅하여 전체 VPN 서버 부하를 줄일 수 있습니다. Microsoft Edge 이제 엔터프라이즈 고객에게 이러한 피어 투 피어 트래픽이 개선됩니다.

## <a name="how-to-configure-vpn-split-tunneling-on-microsoft-edge"></a>사용자 계정에서 VPN 분할 터널링을 구성하는 Microsoft Edge

VPN 분할 터널링을 사용하도록 설정하고 사용자에 대해 네트워크를 구성하려면 사용자에 대한 VPN 분할 터널링 구현 [- Office 365 지침으로 Microsoft 365 Enterprise](/microsoft-365/enterprise/microsoft-365-vpn-implement-split-tunnel?view=o365-worldwide&preserve-view=true). 이전 문서에 설명된 정보에 따라 적절한 라우팅 테이블을 구성한 경우 [WebRtcRespectOsRoutingTableEnabled](/deployedge/microsoft-edge-policies#webrtcrespectosroutingtableenabled) 정책을 사용하도록 설정하는 추가 단계를 실행하면 됩니다. 이 정책은 WebRTC를 Windows 피어 투 피어 연결을 만들 때 OS 라우팅 테이블 규칙에 대한 지원을 사용할 수 있도록 합니다. 이제 사용자에 대해 향상된 피어 투 피어 미디어 스트리밍 환경을 제공할 Microsoft Edge!

## <a name="see-also"></a>참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
