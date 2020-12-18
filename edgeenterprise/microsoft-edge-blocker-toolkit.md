---
title: 차단 도구 키트를 사용하여 Microsoft Edge 자동 배달 사용 중지
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 12/16/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 차단 도구 키트를 사용하여 Microsoft Edge 자동 배달 사용 중지
ms.openlocfilehash: 9fb97d2dfec4822f8ce76dc3e37b85118c6572ad
ms.sourcegitcommit: 606282995b466a968bab40c16005a6653323c763
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/16/2020
ms.locfileid: "11229619"
---
# Microsoft Edge 자동 전달을 비활성화하는 Blocker Toolkit(Chromium 기반)

이 문서에서는 Microsoft Edge 자동 배달 및 설치를 사용하지 않도록 설정하는 차단 도구 키트에 대해 설명합니다.

이 문서는 다음과 같이 업데이트되었습니다.

- **2020년 1월 9일** 차단 도구 키트를 사용해야 할 수 있는 장치에 대한 자세한 정보 포함
- **2020년 2월 28일** 이 자동 업데이트에서 제외할 장치 조건에서 "MDM 관리"를 제거
- **2020년 6월 30일** 모든 Windows 업데이트 연결 장치가 이 업데이트를 수신할 수 있는 범위에 있음을 반영(2020년 7월 30일 이전에는 유효하지 않음)
- **2020년 12월 10일** 차단 도구 키트 설정을 무시하는 사전 20H2 상황을 설명

> [!NOTE]
> 이는 Microsoft Edge 안정 채널에 적용됩니다.

## 개요

고객이 보다 안전한 최신 상태를 유지할 수 있도록 Microsoft는 Windows 업데이트를 통해 Microsoft Edge(Chromium 기반)를 Windows 10 버전 1803 이상을 실행하는 장치에 배포합니다. 이 프로세스는 2020년 1월 15일 이후에 시작되며, 해당 날짜에 더 많은 정보가 제공될 예정입니다.

차단 도구 키트는 Windows 10 버전 1803 이후 버전을 실행하는 장치에서 Microsoft Edge(Chromium 기반)의 자동 배달을 차단하려는 조직을 위한 것입니다. WSUS(Windows Server Update Services) 또는 WUfB(비즈니스용 Windows 업데이트) 관리형 장치는 이 자동 Windows 업데이트에서 제외되지만 조직을 통해 새 Microsoft Edge(Chromium 기반)를 받을 수 있습니다.

**다음 사항에 유의해야 합니다.**

- 차단 도구 키트는 사용자가 인터넷 다운로드를 통해 또는 외부 미디어에서 Microsoft Edge(Chromium 기반)를 수동으로 설치하는 것을 금지하지 않습니다.
- 비즈니스용 Windows 업데이트(WUfB)를 통해 업데이트를 관리하는 조직에서는 자동으로 이 업데이트를 수신하지 않으며 차단 도구 키트를 배포할 필요가 없습니다.
- Windows Server Update Services(WSUS) 또는 System Center Configuration Manager(SCCM)와 같은 업데이트 관리 솔루션으로 관리되는 환경을 보유한 조직은 차단 도구 키트를 배포할 필요가 없습니다. 이러한 제품을 사용하여 해당 환경 내에서 [새 Microsoft Edge에 대한 WSUS의 업데이트](https://support.microsoft.com/help/4584642/update-in-wsus-for-the-new-microsoft-edge)를 포함하여 Windows 업데이트 및 Microsoft 업데이트를 통해 릴리스된 업데이트의 배포를 완전히 관리할 수 있습니다.
- 이 업데이트는 독립 실행형 업데이트(월별 누적 업데이트의 일부가 아님)로 엔터프라이즈 고객에게 이 업데이트 배포를 최대한 제어할 수 있는 유연성을 제공합니다.
- 새 Microsoft Edge(Chromium 기반)는 2020년 하반기에 Windows 10, 버전 20H2 기능 업데이트의 일부로 포함됩니다. 차단 도구 키트는 20H2 동작 또는 배포에 영향을 주지 않습니다. Windows 10, 버전 20H2에 대한 자세한 내용은 [여기](https://blogs.windows.com/windowsexperience/2020/06/16/whats-next-for-windows-10-updates/)를 참조하세요.

[https://msedgeblockertoolkit.blob.core.windows.net/blockertoolkit/MicrosoftEdgeChromiumBlockerToolkit.exe](https://msedgeblockertoolkit.blob.core.windows.net/blockertoolkit/MicrosoftEdgeChromiumBlockerToolkit.exe)에서 차단 도구 키트 실행 파일을 다운로드할 수 있습니다.

### 도구 키트 구성 요소

이 도구 키트에는 다음 구성 요소가 포함됩니다.

- 실행 가능한 차단 스크립트(.CMD)
- 그룹 정책 관리 템플릿(.ADMX 및 .ADML)

### 지원되는 운영 체제

Windows 10 버전 1803 이상

## 차단 스크립트

이 스크립트는 레지스트리 키를 만들고 사용된 명령줄 옵션에 따라 연결된 값이 로컬 컴퓨터 또는 원격 대상 머신에서 Microsoft Edge(Chromium 기반)자동 배달을 차단하거나 차단 해제하도록 설정합니다.

**레지스트리 키:** `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\EdgeUpdate`<br>
**키 값 이름:** `DoNotUpdateToEdgeWithChromium`

| 값                | 결과                         |
|----------------------|--------------------------------|
| *키가 정의되지 않습니다.* | 배포가 차단되지 *않습니다*. |
| 0                    | 배포가 차단되지 *않습니다*. |
| 1                    | 배포가 차단됩니다.       |

스크립트에는 다음 명령줄 구문이 포함되어 있습니다.<br>
`EdgeChromium_Blocker.cmd [<machine name>] [/B] [/U] [/H]`

### 머신 이름

`<machine name>` 매개 변수는 선택 사항입니다. 지정하지 않으면 로컬 컴퓨터에서 동작이 수행됩니다. 그렇지 않으면 `REG` 명령의 원격 레지스트리 기능을 통해 원격 컴퓨터에 액세스합니다. 보안 권한으로 인해 원격 레지스트리에 액세스할 수 없거나 원격 컴퓨터를 찾을 수 없는 경우 `REG` 명령에서 오류 메시지가 반환됩니다.

### 스위치

스크립트에 사용되는 스위치는 상호 배타적이며 지정된 명령에서 첫 번째 올바른 스위치만 처리됩니다. 동일한 머신에서 스크립트를 여러 번 실행할 수 있습니다.

| 스위치       | 설명                              |
|--------------|------------------------------------------|
| `/B`         | 배포를 차단합니다.                      |
| `/U`         | 배포를 차단 해제합니다.                    |
| `/H` 또는 `/?` | 다음과 같은 요약 도움말을 표시합니다.<br>`This tool can be used to remotely block or unblock the delivery of Microsoft Edge (Chromium-based) through Automatic Updates.`<br> `Usage:`<br>`EdgeChromium_Blocker.cmd [<machine name>] [/B][/U][/H]`<br>`B = Block Microsoft Edge (Chromium-based) deployment`<br>`U = Allow Microsoft Edge (Chromium-based) deployment`<br>`H = Help`<br>`Examples:`<br>`EdgeChromium_Blocker.cmd mymachine /B (blocks delivery on machine "mymachine")`<br>`EdgeChromium_Blocker.cmd /U (unblocks delivery on the local machine)`<br> |

## 그룹 정책 관리 템플릿(.ADMX 및 .ADML 파일)

그룹 정책 관리 템플릿(.ADMX 및. ADML 파일)를 사용하면 관리자가 새 그룹 정책 설정을 가져와서 그룹 정책 환경에 Microsoft Edge 자동 배달(Chromium 기반)을 차단하거나 차단을 해제할 수 있으며, 그룹 정책을 사용하여 자신의 환경에서 시스템 간 작업을 중앙에서 실행할 수 있습니다.

Windows 10 RS3 Enterprise/EDU 및 RS4 이상을 실행하는 사용자의 경우 다음 경로 아래에 정책이 표시됩니다.

```
/Computer Configuration  
  /Administrative Templates
    /Classic Administrative Templates
      /Windows Components
        /Windows Update  
          /Microsoft Edge (Chromium-based) Blockers  
```

이 설정은 컴퓨터 설정으로만 사용할 수 있으며 사용자별 설정이 없습니다.

> [!IMPORTANT]
> 이 레지스트리 설정은 정책 키에 저장되지 않으며 *기본 설정*으로 간주됩니다. 따라서 설정을 구현하는 그룹 정책 개체가 제거되거나 정책이 **구성되지 않음**으로 설정되면 해당 설정은 그대로 유지됩니다. 그룹 정책을 사용하여 Microsoft Edge(Chromium 기반) 배포의 차단을 해제하려면 정책을 **사용 안 함**으로 설정합니다.

## 기타 참조

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://www.microsoftedgeinsider.com/enterprise)
- [Microsoft Edge를 지원하기 위한 Windows 업데이트](https://docs.microsoft.com/deployedge/microsoft-edge-sysupdate-windows-updates)
- [Microsoft Edge의 이전 버전에 액세스하는 방법](https://docs.microsoft.com/deployedge/microsoft-edge-sysupdate-access-old-edge)
