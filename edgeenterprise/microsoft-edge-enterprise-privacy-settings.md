---
title: Microsoft Edge 엔터프라이즈 개인 정보 설정
ms.author: likravit
author: dan-wesley
manager: srugh
ms.date: 05/26/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 엔터프라이즈 개인 정보 설정 구성
ms.openlocfilehash: 2b7a33087ae5110c53d18b3192486d4ae62fa540
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980738"
---
# 엔터프라이즈 개인 정보를 지원하도록 Microsoft Edge 정책 구성

Microsoft는 Microsoft Edge에서 데이터 수집을 선택하는 데 필요한 정보와 컨트롤을 엔터프라이즈에 제공하기 위해 최선을 다하고 있습니다.

## 개요

기본적으로 Windows가 아닌 플랫폼에 배포된 Microsoft Edge는 진단 데이터 또는 사이트 정보가 Microsoft에 전송되지 않습니다. Windows 10에 Microsoft Edge가 배포되면 사용자의 [Windows 진단 데이터 설정](https://go.microsoft.com/fwlink/?linkid=2099569)을 기반으로 진단 데이터를 보내는 것이 기본입니다.

다음 그룹 정책을 사용하여 Microsoft Edge가 조직에 대한 데이터 수집을 처리하는 방법을 구성할 수 있습니다.

- [MetricsReportingEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#metricsreportingenabled) - 사용 및 충돌 관련 데이터보고를 사용하도록 설정합니다.
- [SendSiteInfoToImproveServices](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sendsiteinfotoimproveservices) - Microsoft 서비스를 개선하기 위해 사이트 정보를 보냅니다.

## 정책 설정 구성

시작하기 전에 최신 Microsoft Edge 정책 템플릿을 다운로드하고 사용합니다(자세한 내용은 [Microsoft Edge 구성](configure-microsoft-edge.md) 참조).

### 사용 현황 및 크래시 관련 데이터 보고를 사용하도록 설정

이 정책은 Microsoft Edge에서 Microsoft로의 사용 현황 및 크래시 관련 데이터 보고를 사용하도록 설정합니다.

Microsoft Edge는 제품을 안전한 최신 상태로 유지하고 적절히 실행하는 데 필요한 필수 데이터 집합을 수집합니다. 이 데이터는 Microsoft Edge 설치에 대한 현재 데이터 수집 동의, 앱 버전 및 설치 상태에 대한 Microsoft Edge의 기본 장치 연결 및 구성 정보를 포함합니다. 이 데이터 수집은 정책을 사용하지 않음으로써 해제할 수 있습니다.

사용 현황 및 충돌 관련 데이터 보고를 Microsoft에 보내려면 이 정책을 사용하도록 설정합니다. 이 정책을 사용하지 않도록 설정하여 데이터를 Microsoft에 보내지 않도록 합니다. 두 경우 모두 사용자가 정책 설정을 변경하거나 재정의할 수 없습니다.

Windows 10에서 Microsoft Edge가 실행되고 있는 경우:

- 이 정책이 구성되지 않은 경우에는 기본적으로 Microsoft Edge에서 Windows 진단 데이터 설정이 사용됩니다.
- 이 정책을 사용하도록 설정하면 Microsoft Edge는 Windows 진단 데이터 설정이 **고급** 또는 **전체**로 설정된 경우에만 사용 현황 데이터를 보냅니다.
- 이 정책을 사용하지 않도록 설정하면 Microsoft Edge는 사용 현황 데이터를 보내지 않습니다. 크래시 관련 데이터는 Windows 진단 데이터 설정에 따라 전송됩니다. [Windows 진단 데이터 설정](https://go.microsoft.com/fwlink/?linkid=2099569)에 대해 자세히 알아보세요.

Microsoft Edge가 Windows 7, 8 및 macOS에서 실행되는 경우:

- 이 정책이 구성되지 않은 경우에는 기본적으로 Microsoft Edge에서 사용자의 기본 설정이 사용됩니다.

### Microsoft 서비스를 개선하기 위해 사이트 정보를 보냄

이 정책은 Microsoft Edge에서 방문하는 웹 사이트에 대한 정보를 Microsoft에 전송하여 Microsoft 제품과 서비스를 개선하는 데 사용됩니다.

Microsoft Edge에서 방문하는 웹 사이트에 대한 정보를 Microsoft로 보내려면 이 정책을 사용하도록 설정합니다. Microsoft Edge에서 방문하는 웹 사이트에 대한 정보를 Microsoft로 보내지 않으려면 이 정책을 사용하도록 설정합니다. 두 경우 모두 사용자가 정책 설정을 변경하거나 재정의할 수 없습니다.

Windows 10에서 Microsoft Edge가 실행되고 있는 경우:

- 이 정책이 구성되지 않은 경우에는 기본적으로 Microsoft Edge에서 Windows 진단 데이터 설정이 사용됩니다.
- 이 정책을 사용하도록 설정하면 Microsoft Edge는 Windows 진단 데이터 설정이 **전체**로 설정된 경우에만 방문하는 웹 사이트에 대한 정보를 보냅니다.
- 이 정책을 사용하지 않도록 설정하면 Microsoft Edge는 방문하는 웹 사이트에 대한 정보를 보내지 않습니다. [Windows 진단 데이터 설정에 대해 자세히 알아보십시오](https://go.microsoft.com/fwlink/?linkid=2099569).

Microsoft Edge가 Windows 7, 8 및 macOS에서 실행되는 경우:

- 이 정책이 구성되지 않은 경우에는 기본적으로 Microsoft Edge에서 사용자의 기본 설정이 사용됩니다.

## 구현 세부 정보

Windows 10에서 Windows 진단 데이터 설정에 대한 종속성을 사용하여 구현을 이해하기 위해 다음 표에서는 **사용 현황 및 충돌 관련 데이터 보고를 사용하도록 설정** 및 **Microsoft 서비스를 개선하기 위해 사이트 정보를 보냄**이 구성되지 않은 경우의 구성에 대해 설명합니다.

| Windows 진단 데이터 설정 | 사용 현황 및 크래시 관련 데이터 보고를 사용하도록 설정 | Microsoft 서비스를 개선하기 위해 사이트 정보를 보냄 |
|---------------------------------|-----------------------------------------------|-----------------------------------------------------|
| 보안                        | 전송되지 않음                                      | 전송되지 않음                                            |
| 기본                           | 전송되지 않음                                      | 전송되지 않음                                            |
| 고급                        | 보냄                                          | 전송되지 않음                                            |
| 전체                            | 보냄                                          | 보냄                                                |

Windows 10에 대한 구성이 위의 표에 따라 잘못 구성된 경우 더 낮은 데이터 수집 설정으로 대체됩니다.

예를 들어 다음과 같은 가치를 제공해야 합니다.

- "사용 현황 및 크래시 관련 데이터 보고를 사용하도록 설정" 정책을 **사용**으로 설정했지만 Windows 진단 데이터 설정이 **기본**으로 설정되어 있습니다. 사용 현황 및 크래시 관련 데이터를 전송하지 않습니다.
- "Microsoft 서비스를 개선하기 위해 사이트 정보를 보냄"이 **사용 안 **으로 설정되고 Windows 진단 데이터 설정이 **전체**로 설정되어 있습니다. 사용자가 방문하는 사이트에 대한 정보를 전송하지 않습니다.

이전 설정에 대한 올바른 구현 방법은 "사용 현황 및 크래시 관련 데이터 보고를 사용하도록 설정" 정책을 **사용**으로 설정하고 Windows 진단 데이터 설정을 **고급** 또는 **전체**로 설정하는 것입니다.

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
