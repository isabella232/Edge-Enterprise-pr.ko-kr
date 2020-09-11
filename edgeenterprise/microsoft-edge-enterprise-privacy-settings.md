---
title: Microsoft Edge 엔터프라이즈 개인 정보 설정
ms.author: likravit
author: dan-wesley
manager: srugh
ms.date: 09/09/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 엔터프라이즈 개인 정보 설정 구성
ms.openlocfilehash: 25b475206734634df9995f568a6d4e8c52e9f9de
ms.sourcegitcommit: 16984537c8f5c9c60e92f41f0f869231fb79ccd0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/09/2020
ms.locfileid: "11005496"
---
# 엔터프라이즈 개인 정보를 지원하도록 Microsoft Edge 정책 구성

Microsoft는 Microsoft Edge에서 데이터 수집을 선택하는 데 필요한 정보와 컨트롤을 엔터프라이즈에 제공하기 위해 최선을 다하고 있습니다.

## 개요

Windows 10에 Microsoft Edge가 배포되면 사용자의 [Windows 진단 데이터 설정](https://go.microsoft.com/fwlink/?linkid=2099569)을 기반으로 진단 데이터를 보내는 것이 기본입니다.

Microsoft Edge가 비 Windows 플랫폼에 배포되면 다음 그룹 정책의 설정에 따라 진단 데이터가 수집됩니다.

- (사용되지 않음) [MetricsReportingEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#metricsreportingenabled) - 사용 및 충돌 관련 데이터보고를 사용하도록 설정합니다. 이 정책은 Microsoft Edge 버전 89에서 더 이상 사용되지 않습니다.
- (사용되지 않음) [SendSiteInfoToImproveServices](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sendsiteinfotoimproveservices) - Microsoft 서비스를 개선하기 위해 사이트 정보를 보냅니다. 이 정책은 Microsoft Edge 버전 89에서 더 이상 사용되지 않습니다.

이전 더 이상 사용되지 않는 정책은 Windows 10에서 [원격 분석 허용](https://go.microsoft.com/fwlink/?linkid=2099569) 및 다른 모든 플랫폼에 대한 [DiagnosticData](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#diagnosticdata) 정책으로 대체됩니다.  

## 정책 설정 구성

시작하기 전에 최신 Microsoft Edge 정책 템플릿을 다운로드하고 사용합니다(자세한 내용은 [Microsoft Edge 구성](configure-microsoft-edge.md) 참조).

### 브라우저를 사용하는 데 필요한 선택적 진단 데이터 보내기

[DiagnosticData](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#diagnosticdata) 정책을 구성하면 [MetricsReportingEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#metricsreportingenabled)  및 [SendSiteInfoToImproveServices](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sendsiteinfotoimproveservices)보다 우선적으로 적용됩니다.

#### 필수 및 선택적 진단 데이터

필요한 진단 데이터가 수집되어 Microsoft Edge를 최신 상태로 유지하고 예상대로 작동합니다.

선택적 진단 데이터에는 Microsoft Edge의 보안, 최신 상태 및 성능을 유지하기 위해 방문하는 웹 사이트 및 충돌 보고서에 대한 데이터가 포함되며 모든 사용자를 위한 Microsoft Edge 및 기타 Microsoft 제품 및 서비스를 개선하는 데 사용됩니다.

> [!NOTE]
> 이 정책은 Windows 10 장치에서 지원되지 않습니다. Windows 10에서 데이터 수집을 제어하려면 IT 관리자가 Windows 진단 데이터 그룹 정책을 사용해야 합니다. 이 정책은 Windows 버전에 따라'**원격 분석 허용** 또는 **진단 데이터 허용**으로 설정됩니다. [Windows 10 진단 데이터 컬렉션](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization)에 대해 자세히 알아보세요.

다음 설정 중 하나를 사용하여 **DiagnosticData**을(를) 구성합니다.

- Off (권장하지 않음)(0)은(는) 필수 및 옵션 진단 데이터 수집을 끕니다. 
- 필수 데이터(1)는 필수 진단 데이터를 전송하지만 선택적 진단 데이터 수집은 해제합니다. Microsoft Edge는 Microsoft Edge의 보안을 최신 상태로 유지하고 예상대로 작동하는 데 필요한 필수 진단 데이터를 전송합니다. 
- 옵션 데이터(2)는 브라우저 사용량, 방문한 웹 사이트, Microsoft에 전송된 충돌 보고서를 포함하여 선택적 진단 데이터를 전송하여 Microsoft Edge를 안전하게 최신 상태로 유지하고 예상대로 작동하도록 지원하며 Microsoft Edge 및 기타 모든 사용자를 위한 Microsoft 제품 및 서비스를 개선하는 데 사용됩니다.

Windows 7, Windows 8/8.1 및 MacOS에서 이 정책은 Microsoft로 필수 및 선택적 데이터 전송을 제어합니다.

이 정책을 구성하지 않거나 사용하지 않도록 설정하면 Microsoft Edge가 기본적으로 사용자의 기본 설정으로 지정됩니다.

### (사용되지 않음) 사용 및 충돌 관련 데이터 보고를 활성화합니다.

**MetricsReportingEnabled** 정책을 사용하면 Microsoft Edge에 대한 사용량 및 충돌 관련 데이터를 Microsoft에 보고할 수 있습니다.

Microsoft Edge는 제품을 최신 상태로 유지하고, 보안을 유지하며, 예상대로 작동하는 데 필요한 일련의 필수 데이터를 수집합니다. 이 데이터는 Microsoft Edge 설치에 대한 현재 데이터 수집 동의, 앱 버전 및 설치 상태에 대한 Microsoft Edge의 기본 장치 연결 및 구성 정보를 포함합니다. 이 데이터 수집은 정책을 사용하지 않음으로써 해제할 수 있습니다.

사용 현황 및 충돌 관련 데이터 보고를 Microsoft에 보내려면 이 정책을 사용하도록 설정합니다. 이 정책을 사용하지 않도록 설정하여 데이터를 Microsoft에 보내지 않도록 합니다. 두 경우 모두 사용자가 정책 설정을 변경하거나 재정의할 수 없습니다.

Windows 10에서 Microsoft Edge가 실행되고 있는 경우:

- 이 정책이 구성되지 않은 경우에는 기본적으로 Microsoft Edge에서 Windows 진단 데이터 설정이 사용됩니다.
- 이 정책을 사용하도록 설정하면 Microsoft Edge는 Windows 진단 데이터 설정이 **고급** 또는 **전체**로 설정된 경우에만 사용 현황 데이터를 보냅니다.
  - 이 정책을 사용하도록 설정한 경우 Microsoft Edge는 [SendSiteInfoToEnhancedServices](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sendsiteinfotoimproveservices)도 사용하도록 설정된 경우에만 사용량 데이터를 보냅니다.
- 이 정책을 사용하지 않도록 설정하면 Microsoft Edge는 사용 현황 데이터를 보내지 않습니다. 크래시 관련 데이터는 Windows 진단 데이터 설정에 따라 전송됩니다. [Windows 진단 데이터 설정](https://go.microsoft.com/fwlink/?linkid=2099569)에 대해 자세히 알아보세요.

Microsoft Edge가 Windows 7, 8 및 macOS에서 실행되는 경우:

- 이 정책이 구성되지 않은 경우 Microsoft Edge는 기본적으로 사용자의 기본 설정으로 설정됩니다.
-  이 정책을 사용하도록 설정한 경우 Microsoft Edge는 [SendSiteInfoToEnhancedServices](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sendsiteinfotoimproveservices)도 사용하도록 설정된 경우에만 사용량 데이터를 보냅니다.

### (사용되지 않음) 사이트 정보를 전송하여 Microsoft 서비스를 개선합니다.

**SendSiteInformationToEnhancedServices** 정책을 사용하면 Microsoft Edge에서 방문한 웹 사이트에 대한 정보를 Microsoft로 보내 Microsoft 제품 및 서비스(예: 검색)를 개선할 수 있습니다.

Microsoft Edge에서 방문하는 웹 사이트에 대한 정보를 Microsoft로 보내려면 이 정책을 사용하도록 설정합니다. Microsoft Edge에서 방문하는 웹 사이트에 대한 정보를 Microsoft로 보내지 않으려면 이 정책을 사용하도록 설정합니다. 두 경우 모두 사용자가 정책 설정을 변경하거나 재정의할 수 없습니다.

Windows 10에서 Microsoft Edge가 실행되고 있는 경우:

- 이 정책이 구성되지 않은 경우에는 기본적으로 Microsoft Edge에서 Windows 진단 데이터 설정이 사용됩니다.
- 이 정책을 사용하도록 설정하면 Microsoft Edge는 Windows 진단 데이터 설정이 **전체**로 설정된 경우에만 방문하는 웹 사이트에 대한 정보를 보냅니다.
  - 이 정책을 사용하도록 설정한 경우 Microsoft Edge는 [MetricsReportingEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#metricsreportingenabled)도 사용하도록 설정된 경우에만 사용량 데이터를 보냅니다. 
- 이 정책을 사용하지 않도록 설정하면 Microsoft Edge는 방문하는 웹 사이트에 대한 정보를 보내지 않습니다. [Windows 진단 데이터 설정에 대해 자세히 알아보십시오](https://go.microsoft.com/fwlink/?linkid=2099569).

Microsoft Edge가 Windows 7, 8 및 macOS에서 실행되는 경우:

- 이 정책을 사용하도록 설정한 경우 Microsoft Edge는 [MetricsReportingEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#metricsreportingenabled)도 사용하도록 설정된 경우에만 사용량 데이터를 보냅니다.
- 이 정책이 구성되지 않은 경우 Microsoft Edge는 기본적으로 사용자의 기본 설정으로 설정됩니다.

## 구현 세부 정보

Windows 10이 아닌 장치의 경우 다음을 수행합니다. 
- [DiagnosticData](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#diagnosticdata) 정책을 구성하면 [MetricsReportingEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#metricsreportingenabled)  및 [SendSiteInfoToImproveServices](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sendsiteinfotoimproveservices)보다 우선적으로 적용됩니다. 
- [DiagnosticData](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#diagnosticdata) 정책이 구성되어 있지 않으면 Microsoft Edge는 [MetricsReportingEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#metricsreportingenabled)  및 [SendSiteInfoToEnhroveServices](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sendsiteinfotoimproveservices)을(를) 수신합니다.  

Windows 10의 경우 Windows 진단 데이터 설정에 대한 종속성을 확인하기 위해 다음 표에서는 **필수** 및 **선택적** 진단 데이터를 Microsoft에 보낼지 여부를 확인합니다.

| Windows 진단 데이터 설정 | 필수적 진단 데이터  | 선택적 진단 데이터 |
|---------------------------------|-----------------------------------------------|-----------------------------------------------------|
| 보안                        | 전송되지 않음                                      | 전송되지 않음                                            |
| 기본                           | 보냄                                      | 전송되지 않음                                            |
| 고급                        | 보냄                                          | 전송되지 않음                                            |
| 전체                            | 보냄                                          | 보냄                                                |

> [!IMPORTANT]
> Microsoft Edge에서는 Microsoft Edge 버전 86-88 포함에 대한 **MetricsReportingEnabled** 및 **SendSiteInfoToImproveServices**를 지원합니다. Microsoft Edge 버전 89에서는 **MetricsReportingEnabled**  및 **SendSiteInfoToEnhancedServices**이(가) 더 이상 지원되지 않으며 Windows 10 플랫폼의 **DiagnosticData** 또는 Windows 10용 **원격 분석 허용**으로 기본 설정됩니다.

## 추가 개인정보처리방침 옵션

데이터 프라이버시와 관련된 다음 그룹 정책을 고려할 수 있습니다.

- 특정 사이트에서 쿠키 차단
- 타사 쿠키 차단
- Do Not Track 구성
- InPrivate 모드 사용 안 함

## 기타 참조

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge 정책](microsoft-edge-policies.md)
- [Microsoft Edge 개인 정보 백서](https://docs.microsoft.com/microsoft-edge/privacy-whitepaper)
