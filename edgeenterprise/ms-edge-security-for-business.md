---
title: 비즈니스를 위한 Microsoft Edge 보안
ms.author: seanlynd
author: seanongit
manager: chuckf
ms.date: 02/10/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 비즈니스를 위한 Microsoft Edge 보안
ms.openlocfilehash: 674fad396bed62058c3187e00f4938d99cc57868
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447072"
---
# <a name="microsoft-edge-security-for-your-business"></a>비즈니스를 위한 Microsoft Edge 보안

Microsoft Edge는 Chromium 오픈 소스 프로젝트(Google Chrome의 핵심인 동일한 프로젝트) 기반으로 구축되었으며, 이는 우수한 설계 및 테스트된 보안 아카텍처과 설계를 공유한다는 의미입니다. Microsoft Edge 보안 스토리는 거기서 멈추지 않습니다. 사실 **Microsoft Edge가 Windows 10을 사용하는 비즈니스에는 Google Chrome보다 더 안전합니다**. 피싱과 맬웨어에 대해 기본 제공되는 강력하고 방어 수단이며 Windows 10에서 하드웨어 격리를 기본적으로 지원합니다. 안전한 기준선을 얻기 위해 추가로 필요한 소프트웨어가 없습니다. 또한 Microsoft 365 보안 및 규정 준수 서비스에 대한 기본 지원과 함께 제공되는 경우 Microsoft Edge는 더 많은 혜택을 위해 데이터 손실을 방지하는 데 도움이 되는 강력한 보안 기능과 추가 기능을 제공합니다. 자세한 내용은 [Microsoft Edge 보안, 호환성 및 관리 용이성](microsoft-edge-video-security-compatibility-manageability.md)을 참조하세요.

**외부 위협**부터 시작하여 **내부 위험 및 정보 보호**를 살펴보며 자세한 내용을 참조하세요.

## <a name="external-threat-protection"></a>외부 위협 방지

### <a name="highest-rated-protection-against-phishing-and-malware"></a>피싱 및 맬웨어에 대해 최고 수준의 보호

NSS Labs의 독립 연구에 따르면, Microsoft Edge에 내장된 SmartScreen은 Google Chrome의 세이프 브라우징보다 더 많은 [피싱](https://edgeconsumerproduction.blob.core.windows.net/hostingdocs/NSS_Labs_Browser_Phishing_Report_Q2_2020.pdf) 및 [맬웨어](https://edgeconsumerproduction.blob.core.windows.net/hostingdocs/NSS_Labs_Browser_Malware_Report_Q2_2020.pdf) 시도를 차단합니다. SmartScreen은 사용자가 온라인으로 작업하는 동안 사이트 및 다운로드에 대한 실시간 평판 검사를 제공하며, [Microsoft Intelligent Security Graph](https://www.microsoft.com/microsoft-365/windows/intelligent-security)의 일부로서, 글로벌 자산, 연구자 및 파트너로 이루어진 Microsoft의 대규모 네트워크에서 생성된 신호 및 인사이트를 이끌어냅니다. Microsoft Edge는 위험한 사이트 및 다운로드의 동적, 클라우드 기반 목록에 대한 검사를 실행하여, 금방 사라지는 단기 위협도 감지하고 차단하는 데 도움이 됩니다.  

[SmartScreen이 포함된 Microsoft Edge는](//DeployEdge/microsoft-edge-security-smartscreen) NSS Lab의 피싱 방지 테스트에서 [95.5%의 피싱 시도를 차단했으며,](https://edgeconsumerproduction.blob.core.windows.net/hostingdocs/NSS_Labs_Browser_Phishing_Report_Q2_2020.pdf) NSS Lab의 맬웨어 방지 테스트에서는 [98.5%의 맬웨어 시도를 차단한 반면](https://edgeconsumerproduction.blob.core.windows.net/hostingdocs/NSS_Labs_Browser_Malware_Report_Q2_2020.pdf) Chrome의 세이프 브라우징 비율은 각각 86.9% 및 86.0% 였습니다.

### <a name="the-only-browser-on-windows-10-that-natively-supports-hardware-isolation"></a>하드웨어 격리를 기본적으로 지원하는 Windows 10의 유일한 브라우저

Microsoft Edge는 하드웨어 격리 기능을 기본적으로 지원하는 Windows 10의 유일한 브라우저입니다. Windows 10 Pro 또는 Enterprise의 일부로서, Microsoft Defender Application Guard(Application Guard)는 로컬 장치 및 내부 네트워크에서 격리된 커널에서 신뢰할 수 없는 사이트를 실행합니다. 신뢰할 수 없는 사이트는 "컨테이너"에서 실행되므로 공격이 나타나면 나머지 기업 네트웨크에서 해당 사이트에 샌드박스가 적용됩니다. 자세한 내용은 [Application Guard용 Microsoft Edge 지원](./microsoft-edge-security-windows-defender-application-guard.md)을 참조하세요.

Chrome의 경우, Windows 10 하드웨어 격리(MDAG 확장)를 활용하는 데 확장을 사용할 수 있습니다. 이 확장 기능은 Application Guard의 커널 레벨 격리를 활용하기 위해 Microsoft Edge을 시작합니다. 또한 Chrome 전용 솔루션에 대해 이와 유사한 커널 수준 격리를 구현하기 위해, 타사 격리 소프트웨어가 필요합니다.

> [!NOTE]
> Windows 10, 1809 이상에서 Application Guard를 사용할 수 있습니다. Windows 10 Home Edition에서는 Application Guard를 사용할 수 없습니다.

## <a name="internal-risks-and-information-protection"></a>내부 위험 및 정보 보호

### <a name="native-support-for-microsoft-365-security-without-additional-software"></a>추가 소프트웨어 없이 Microsoft 365 보안에 대한 기본 지원

외부 위협으로부터 보호하는 것 외에도, IT 관리자는 내부 위험을 방지해야 합니다. 특히, 인력이 분산되어 있는 경우에 강력하고 대규모로 중요한 기업 데이터를 보호하는 것이 IT 관리자의 최우선 순위입니다. Microsoft Edge는 추가 소프트웨어 필요 없이 Azure AD 조건부 액세스, Windows Information Protection 및 새 Microsoft Endpoint DLP(Data Loss Prevention)에 대한 기본 지원을 포함하는 유일한 브라우저입니다.

**Microsoft Edge는 조건부 액세스를 기본적으로 지원하는 유일한 브라우저입니다.** [조건부 액세스에 대한 Microsoft Edge의 지원](ms-edge-security-conditional-access.md)을 사용하면 조직에서 액세스 제어 결정의 일부로 ID 신호를 쉽게 활용할 수 있습니다. [조건부 액세스](/azure/active-directory/conditional-access/overview)는 Azure Active Directory에서 신호를 통합하고 의사 결정을 내리고 조직 정책을 적용하는 데 사용하 도구입니다. 조건부 액세스는 새 ID 기반 제어 영역의 핵심에 있습니다. Chrome에서 조건부 액세스 지원을 받으려면 추가 플러그 인이 필요합니다.

> [!NOTE]
> Azure AD 조건부 액세스를 사용하려면 Microsoft 365 E3 이상 구독이 필요합니다.

**Microsoft Edge는 기업 데이터에 대한 보호를 제공하여 Windows 10 장치에서 발생하는 사용자의 우발적 누출을 방지하는 데 도움이 되는 WIP(Windows Information Protection)을 기본적으로 지원하는 유일한 브라우저**입니다. [WIP용 Microsoft Edge 지원](./microsoft-edge-security-windows-information-protection.md)을 IT 조작 앱만 기업 데이터에 액세스할 수 있도록 구성할 수 있습니다. 또한 원활한 사용자 환경을 사용하여 클립보드 보호, 다운로드 시 파일 암호화, 무단 네트워크 공유 또는 클라우드 위치로의 파일 업로드 방지 등의 누출 제어 기능을 제공합니다. WIP는 경계 기반 구성으로 운영되므로 IT 관리자가 회사 경계를 정의하고 해당 경계 내의 모든 데이터가 회사에 속한 것로 간주됩니다. 누출 제어 기능이 있는 WIP에 대해 Chrome은 확실하게 밝혀지지 않았습니다.

> [!NOTE]
> WIP(Windows Information Protection) 구성을 사용하려면 Microsoft Intune 또는 Microsoft Endpoint Configuration Manager에 라이선스를 부여하거나, 타사 MDM(모바일 장치 관리) 솔루션을 사용해야 하며, 이 경우 추가 라이선스 요구 사항이 있을 수 있습니다.

**Microsoft 끝점 데이터 손실 방지(끝점 DLP)는 기본적으로 Microsoft Edge에서만 지원됩니다**. 끝점 DLP는 Microsoft 보안 센터와 통합하고 Microsoft Edge에 대한 정보 보호 기능을 확장하여 사용자가 온라인으로 작업 시 비준수 활동에 대해 알리고 데이터 손실을 방지하는 데 도움이 됩니다. 이 기능은 관리자가 정의한 기준에 맞는 기업 내 중요한 데이터(예: 신용 카드 번호 또는 정부 기관 ID(예: 주민 번호)가 포함된 파일, 재무 정보 등)를 발견하고 레이블을 지정합니다. 추가 재구성 없이 IT 관리자가 이미 사용자 지정한 콘텐츠 ID와 정책을 비롯한 Microsoft Information Protection 정책을 Microsoft Endpoint DLP에 배포할 수 있습니다. IT 관리자에 대한 정보 보호를 원활하게 배포합니다.

끝점 DLP 선행 조건과 이를 설정하는 방법에 대한 자세한 내용은 [끝점 데이터 손실 방지 시작하기](/microsoft-365/compliance/endpoint-dlp-getting-started?preserve-view=true&view=o365-worldwide)를 참조하세요.

> [!NOTE]
> Microsoft 끝점 데이터 손실 방지 기능을 사용하려면 Microsoft 365 E5 또는 Microsoft 365 E5 준수 구독이 필요합니다.

## <a name="see-also"></a>기타 참고 항목

- [Microsoft Edge Enterprise 방문 페이지](https://aka.ms/EdgeEnterprise)
- [비디오: Microsoft Edge 보안, 호환성 및 관리 용이성](microsoft-edge-video-security-compatibility-manageability.md)