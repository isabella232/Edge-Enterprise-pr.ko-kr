---
title: Microsoft Edge 업데이트 정책 설명서
ms.author: stmoody
author: RyanHechtMSFT
manager: tahills
ms.date: 09/23/2021
audience: ITPro
ms.topic: reference
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.custom: ''
description: Microsoft Edge 업데이트 프로그램에서 지원하는 모든 정책에 대한 설명서
ms.openlocfilehash: b96fc0e44434b5ab36a16b1bc14f0aebe0deacf4
ms.sourcegitcommit: 8e5294e82cf62abc916cfd24692f55925330d42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2021
ms.locfileid: "12037218"
---
# <a name="microsoft-edge---update-policies"></a>Microsoft Edge - 업데이트 정책

최신 버전의 Microsoft Edge에는 Microsoft Edge가 업데이트되는 방법 및 시기를 제어하는 데 사용할 수 있는 다음과 같은 정책이 포함되어 있습니다.

Microsoft Edge에서 사용할 수 있는 다른 정책에 대한 자세한 내용은 [Microsoft Edge 브라우저 정책 참조](microsoft-edge-policies.md)를 확인하세요.
> [!NOTE]
> 이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.
## <a name="available-policies"></a>사용 가능한 정책
다음 표에서는 이번 릴리스의 Microsoft Edge에서 사용할 수 있는 모든 업데이트 관련 그룹 정책을 보여 줍니다. 특정 정책에 대해 자세히 알아보려면 표의 링크를 사용하세요.

|&nbsp;|&nbsp;| |**-**| | |**[애플리케이션](#applications)**|[기본 설정](#preferences)| |**[프록시 서버](#proxy-server)**|[Microsoft Edge WebView](#microsoft-edge-webview)|
### [<a name="applications"></a>응용 프로그램](#applications-policies)
|정책 이름|캡션|
|-|-|
|[InstallDefault](#installdefault)|설치 허용 기본값|
|[UpdateDefault](#updatedefault)|업데이트 정책 재정의 기본값|
|[설치](#install)|설치 허용(채널별)|
|[업데이트](#update)|업데이트 정책 재정의(채널별)|
|[Allowsxs](#allowsxs)|Microsoft Edge 함께 사용 브라우저 환경 허용|
|[CreateDesktopShortcutDefault](#createdesktopshortcutdefault)|기본 설치 시 데스크톱 바로 가기 만들기 방지|
|[CreateDesktopShortcut](#createdesktopshortcut)|설치 시 데스크톱 바로 가기 만들기 방지(채널 당)|
|[RollbackToTargetVersion](#rollbacktotargetversion)|대상 버전으로 롤백(채널당)|
|[TargetVersionPrefix](#targetversionprefix)|대상 버전 재정의(채널당)|
|[TargetChannelOverride](#targetchanneloverride)|대상 채널 오버라이드(안정만 해당)|
|[UpdaterExperimentationAndConfigurationServiceControl](#UpdaterExperimentationAndConfigurationServiceControl)| 구성 및 실험 검색|
### [<a name="preferences"></a>기본 설정](#preferences-policies)
|정책 이름|캡션|
|-|-|
|[AutoUpdateCheckPeriodMinutes](#autoupdatecheckperiodminutes)|자동 업데이트 확인 기간 재정의|
|[UpdatesSuppressed](#updatessuppressed)|매일 자동 업데이트 확인 억제 기간|

### [<a name="proxy-server"></a>프록시 서버](#proxy-server-policies)
|정책 이름|캡션|
|-|-|
|[ProxyMode](#proxymode)|프록시 서버 설정 지정 방법 선택|
|[ProxyPacUrl](#proxypacurl)|프록시 .pac 파일 URL|
|[ProxyServer](#proxyserver)|프록시 서버 주소 또는 URL|

### [<a name="microsoft-edge-webview"></a>Microsoft Edge WebView](#microsoft-edge-webview-policies)
|정책 이름|캡션|
|-|-|
|[설치](#install-webview)|설치 허용|
|[업데이트](#update-webview)|업데이트 정책 재정의|

## <a name="applications-policies"></a>응용 프로그램 정책

[맨 위로 이동](#microsoft-edge---update-policies)
### <a name="installdefault"></a>InstallDefault
#### <a name="allow-installation-default"></a>설치 허용 기본값
>Microsoft Edge 업데이트 1.2.145.5 이상

#### <a name="description"></a>설명
도메인에 가입된 장치에서 Microsoft Edge를 허용하거나 차단하기 위해 모든 채널의 기본 동작을 지정할 수 있습니다.

특정 채널에 대한 ‘[설치 허용](#install)’ 정책을 사용하도록 설정하여 개별 채널에 대한 이 정책을 재정의할 수 있습니다.

이 정책을 사용하지 않도록 설정하면 Microsoft Edge의 설치가 차단됩니다. 이는 '[설치 허용](#install)' 정책이 구성되지 않음으로 설정된 경우에만 Microsoft Edge 소프트웨어 설치에 영향을 줍니다.

이 정책은 Microsoft Edge 업데이트 실행을 금지하거나 사용자가 다른 방법으로 Microsoft Edge 소프트웨어를 설치하는 것을 방지하지 않습니다.

이 정책은 Microsoft® Active Directory® 도메인에 연결된 Windows 인스턴스에서만 사용할 수 있습니다.
#### <a name="windows-information-and-settings"></a>Windows 정보 및 설정
##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보
- GP 고유 이름: InstallDefault
- GP 이름: 설치 허용 기본값
- GP 경로: 관리 템플릿/Microsoft Edge 업데이트/응용 프로그램
- GP ADMX 파일 이름: msedgeupdate.admx
##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정
- 경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 값 이름: InstallDefault
- 값 형식: REG_DWORD
##### <a name="example-value"></a>예를 들어 값:
```
0x00000001
```
[맨 위로 이동](#microsoft-edge---update-policies)


### <a name="updatedefault"></a>UpdateDefault
#### <a name="update-policy-override-default"></a>업데이트 정책 재정의 기본값
>Microsoft Edge 업데이트 1.2.145.5 이상

#### <a name="description"></a>설명
Microsoft Edge 업데이트가 Microsoft Edge에 사용 가능한 업데이트를 처리하는 방식과 관련하여 모든 채널에 대해 기본 동작을 지정할 수 있습니다. 특정 채널에 ‘[업데이트 정책 재정의](#update)’ 정책을 지정하여 채널별로 재정의할 수 있습니다.

  이 정책을 사용하도록 설정하면 다음 중 구성된 옵션에 따라 Microsoft Edge 업데이트가 Microsoft Edge에 대한 업데이트를 처리합니다.
   - 항상 업데이트 허용: 업데이트는 정기 업데이트 확인 또는 수동 업데이트 확인을 통해 검색되는 경우 항상 적용됩니다.
   - 자동 업데이트만: 업데이트는 정기 업데이트 확인에서 검색된 경우에만 적용됩니다.
   - 수동 업데이트만: 업데이트는 사용자가 수동 업데이트 확인을 실행하는 경우에만 적용됩니다.
   - 업데이트 사용 안 함: 업데이트가 적용되지 않습니다.

  수동 업데이트를 선택하는 경우 앱의 수동 업데이트 메커니즘(사용 가능한 경우)을 사용하여 정기적으로 업데이트를 확인해야 합니다. 업데이트를 사용하지 않도록 설정하는 경우 정기적으로 업데이트를 확인하여 사용자에게 배포합니다.

  이 정책을 사용하도록 설정하고 구성하지 않으면 Microsoft Edge 업데이트는 ‘[업데이트 정책 재정의](#update)’ 정책에 지정된 대로 사용 가능한 업데이트를 처리합니다.

  이 정책은 Microsoft® Active Directory® 도메인에 연결된 Windows 인스턴스에서만 사용할 수 있습니다.
#### <a name="windows-information-and-settings"></a>Windows 정보 및 설정
##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보
- GP 고유 이름: UpdateDefault
- GP 이름: 업데이트 정책 재정의 기본값
- GP 경로: 관리 템플릿/Microsoft Edge 업데이트/응용 프로그램
- GP ADMX 파일 이름: msedgeupdate.admx
##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정
- 경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 값 이름: UpdateDefault
- 값 형식: REG_DWORD
##### <a name="example-value"></a>예를 들어 값:
```
0x00000003
```
[맨 위로 이동](#microsoft-edge---update-policies)


### <a name="install"></a>설치
#### <a name="allow-installation"></a>설치 허용
>Microsoft Edge 업데이트 1.2.145.5 이상

#### <a name="description"></a>설명
도메인에 가입된 장치에 Microsoft Edge 채널을 설치할 수 있는지 여부를 지정합니다.

  채널에 이 정책을 사용하면 Microsoft Edge가 설치에서 차단되지 않습니다.

  채널에 이 정책을 사용하지 않으면 Microsoft Edge가 설치에서 차단됩니다.

  채널에 대해 이 정책을 구성하지 않으면 ‘[설치 허용](#installdefault)’ 정책 구성이 사용자가 해당 Microsoft Edge 채널을 설치할 수 있는지 여부를 결정합니다.

  이 정책은 Microsoft® Active Directory® 도메인에 연결된 Windows 인스턴스에서만 사용할 수 있습니다.
#### <a name="windows-information-and-settings"></a>Windows 정보 및 설정
##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보
- GP 고유 이름: Install
- GP 이름: 설치 허용
- GP 경로: 
  - 관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge
  - 관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Beta
  - 관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Canary
  - 관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Dev
- GP ADMX 파일 이름: msedgeupdate.admx
##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정
- 경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 값 이름: 
  - (Stable): Install{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}
  - (Beta): Install{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}
  - (Canary): Install{65C35B14-6C1D-4122-AC46-7148CC9D6497}
  - (Dev): Install{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}
- 값 형식: REG_DWORD
##### <a name="example-value"></a>예를 들어 값:
```
0x00000001
```
[맨 위로 이동](#microsoft-edge---update-policies)


### <a name="update"></a>업데이트
#### <a name="update-policy-override"></a>업데이트 정책 재정의
>Microsoft Edge 업데이트 1.2.145.5 이상

#### <a name="description"></a>설명
Microsoft Edge 업데이트가 Microsoft Edge에서 사용 가능한 업데이트를 처리하는 방법을 지정합니다.

이 정책을 사용하도록 설정하면 다음 중 구성된 옵션에 따라 Microsoft Edge 업데이트가 Microsoft Edge에 대한 업데이트를 처리합니다.
  - 항상 업데이트 허용: 업데이트는 정기 업데이트 확인 또는 수동 업데이트 확인을 통해 검색되는 경우 항상 적용됩니다.
  - 자동 업데이트만: 업데이트는 정기 업데이트 확인에서 검색된 경우에만 적용됩니다.
  - 수동 업데이트만: 업데이트는 사용자가 수동 업데이트 확인을 실행하는 경우에만 적용됩니다. (일부 앱은 이 옵션에 대한 인터페이스를 제공하지 않습니다.)
  - 업데이트 사용 안 함: 업데이트가 적용되지 않습니다.

수동 업데이트를 선택하는 경우 앱의 수동 업데이트 메커니즘(사용 가능한 경우)을 사용하여 정기적으로 업데이트를 확인해야 합니다. 업데이트를 사용하지 않도록 설정하는 경우 정기적으로 업데이트를 확인하여 사용자에게 배포합니다.

이 정책을 사용하도록 설정하고 구성하지 않으면 Microsoft Edge 업데이트는 ‘[업데이트 정책 재정의 기본값](#updatedefault)’ 정책에 지정된 대로 사용 가능한 업데이트를 처리합니다.

자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2136406](https://go.microsoft.com/fwlink/?linkid=2136406)을 참조하세요.

이 정책은 Microsoft® Active Directory® 도메인에 연결된 Windows 인스턴스에서만 사용할 수 있습니다.
#### <a name="windows-information-and-settings"></a>Windows 정보 및 설정
##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보
- GP 고유 이름: Update
- GP 이름: 업데이트 정책 재정의
- GP 경로: 
  - 관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge
  - 관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Beta
  - 관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Canary
  - 관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Dev
- GP ADMX 파일 이름: msedgeupdate.admx
##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정
- 경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 값 이름:
  - (Stable): Update{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}
  - (Beta): Update{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}
  - (Canary): Update{65C35B14-6C1D-4122-AC46-7148CC9D6497}
  - (Dev): Update{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}
- 값 형식: REG_DWORD
##### <a name="example-value"></a>예를 들어 값:
```
always allow updates 0x00000001
Automatic silent updates only 0x00000003
manual updates only 0x00000002
updates disabled 0x00000000
```
[맨 위로 이동](#microsoft-edge---update-policies)


### <a name="allowsxs"></a>Allowsxs
#### <a name="allow-microsoft-edge-side-by-side-browser-experience"></a>Microsoft Edge 함께 사용 브라우저 환경 허용
>Microsoft Edge 업데이트 1.2.145.5 이상

#### <a name="description"></a>설명
이 정책은 사용자가 Microsoft Edge(Edge HTML) 및 Microsoft Edge(Chromium 기반)을 함께 실행할 수 있게 합니다.

이 정책을 "구성되지 않음"으로 설정하면 Microsoft Edge(Chromium 기반) 안정 채널 및 2019년 11월 보안 업데이트가 설치된 후 Microsoft Edge(Chromium 기반)가 Microsoft Edge(Edge HTML)를 대체합니다.  이는 "사용 안 함" 설정과 동일한 동작입니다.

"사용 안 함" 설정은 함께 사용 환경을 차단하고 Microsoft Edge(Chromium 기반) 안정 채널 및 2019년 11월 보안 업데이트가 설치된 후 Microsoft Edge(Chromium 기반)가 Microsoft Edge(Edge HTML)를 대체합니다.  이는 "구성되지 않음" 설정과 동일한 동작입니다.

이 정책을 "사용"으로 설정하면 Microsoft Edge(Chromium 기반)이 설치된 후 Microsoft Edge(Chromium 기반)와 Microsoft Edge(Edge HTML)를 함께 실행할 수 있습니다.

이 그룹 정책을 적용하려면 Windows 업데이트가 Microsoft Edge(Chromium 기반)를 자동으로 설치하기 전에 구성해야 합니다. 참고: 사용자는 Microsoft Edge(Chromium 기반) 차단 도구 키트를 사용하여 Microsoft Edge(Chromium 기반) 자동 업데이트를 차단할 수 있습니다.
#### <a name="windows-information-and-settings"></a>Windows 정보 및 설정
##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보
- GP 고유 이름: Allowsxs
- GP 이름: Microsoft Edge 함께 사용 브라우저 환경 허용
- GP 경로: 관리 템플릿/Microsoft Edge 업데이트/응용 프로그램
- GP ADMX 파일 이름: msedgeupdate.admx
##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정
- 경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 값 이름: Allowsxs
- 값 형식: REG_DWORD
##### <a name="example-value"></a>예를 들어 값:
```
0x00000001
```
[맨 위로 이동](#microsoft-edge---update-policies)

### <a name="createdesktopshortcutdefault"></a>CreateDesktopShortcutDefault
#### <a name="prevent-desktop-shortcut-creation-upon-install-default"></a>기본 설치 시 데스크톱 바로 가기 만들기 방지
>Microsoft Edge 업데이트 1.3.128.0 이상

#### <a name="description"></a>설명
Microsoft Edge가 설치된 경우 데스크톱 바로 가기를 만들기 위한 모든 채널에 대한 기본 동작을 지정할 수 있습니다.

  이 정책을 사용하도록 설정하는 경우 Microsoft Edge가 설치될 때 데스크톱 바로 가기가 만들어집니다.
이 정책을 사용하지 않도록 설정하는 경우 Microsoft Edge가 설치될 때 데스크톱 바로 가기가 만들어지지 않습니다.
이 정책을 구성하지 않으면 Microsoft Edge로의 데스크톱 바로 가기가 설치 도중에 만들어집니다.
Microsoft Edge가 이미 설치되어 있는 경우 이 정책은 아무런 영향을 주지 않습니다.
#### <a name="windows-information-and-settings"></a>Windows 정보 및 설정
##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보
- GP 고유 이름: CreateDesktopShortcutDefault
- GP 이름: 기본값을 설치 시 데스크톱 바로 가기 만들기를 방지
- GP 경로: 관리 템플릿/Microsoft Edge 업데이트/응용 프로그램
- GP ADMX 파일 이름: msedgeupdate.admx
##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정
- 경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 값 이름: CreateDesktopShortcutDefault
- 값 형식: REG_DWORD
##### <a name="example-value"></a>예를 들어 값:
```
0x00000001
```
[맨 위로 이동](#microsoft-edge---update-policies)


### <a name="createdesktopshortcut"></a>CreateDesktopShortcut
#### <a name="prevent-desktop-shortcut-creation-upon-install"></a>설치 시 데스크톱 바로 가기 만들기를 방지
>Microsoft Edge 업데이트 1.3.128.0 이상

#### <a name="description"></a>설명
이 정책을 사용하도록 설정하는 경우 Microsoft Edge가 설치될 때 데스크톱 바로 가기가 만들어집니다.
이 정책을 사용하지 않도록 설정하는 경우 Microsoft Edge가 설치될 때 데스크톱 바로 가기가 만들어지지 않습니다.
이 정책을 구성하지 않으면 Microsoft Edge로의 데스크톱 바로 가기가 설치 도중에 만들어집니다.
Microsoft Edge가 이미 설치되어 있는 경우 이 정책은 아무런 영향을 주지 않습니다.

  채널에 대한 이 정책을 구성하지 않는 경우 '[설치시 바탕 화면 바로 가기 만들기 방지 기본](#createdesktopshortcutdefault)' 정책 구성에 따라 Microsoft Edge 설치시 바로 가기 만들기를 결정합니다.
#### <a name="windows-information-and-settings"></a>Windows 정보 및 설정
##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보
- GP 고유 이름: CreateDesktopShortcut
- GP 이름: 설치 시 데스크톱 바로 가기 만들기를 방지
- GP 경로: 
  - 관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge
  - 관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Beta
  - 관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Canary
  - 관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Dev
- GP ADMX 파일 이름: msedgeupdate.admx
##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정
- 경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 값 이름: 
  - (안정): CreateDesktopShortcut{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}
  - (베타): CreateDesktopShortcut{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}
  - (카나리아): CreateDesktopShortcut{65C35B14-6C1D-4122-AC46-7148CC9D6497}
  - (Dev): CreateDesktopShortcut{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}
- 값 형식: REG_DWORD
##### <a name="example-value"></a>예를 들어 값:
```
0x00000001
```
[맨 위로 이동](#microsoft-edge---update-policies)


### <a name="rollbacktotargetversion"></a>RollbackToTargetVersion
#### <a name="rollback-to-target-version"></a>대상 버전으로 롤백
>Microsoft Edge 업데이트 1.3.133.3 이상

#### <a name="description"></a>설명
Microsoft Edge 업데이트가 '[대상 버전 재정의](#targetversionprefix)'에 표시된 버전으로 Microsoft Edge 설치를 롤백하도록 지정합니다.

'[대상 버전 재정의](#targetversionprefix)'가 설정되고 '[업데이트 정책 재정의](#update)'가 켜짐 상태 중 하나(업데이트 항상 허용, 자동 업데이트만, 수동 업데이트만)로 설정되어 있지 않은 경우에는 이 정책이 적용되지 않습니다.

이 정책을 사용하지 않거나 구성하지 않는 경우 '[대상 버전 재정의](#targetversionprefix)'에서 지정한 것보다 높은 버전이 있는 설치는 그대로 유지됩니다.

이 정책을 사용하면 '[대상 버전 재정의](#targetversionprefix)'에서 지정한 것보다 높은 현재 버전이 있는 설치는 대상 버전으로 다운그레이드됩니다.

최신 버전의 Microsoft Edge 브라우저를 설치하여 최신 보안 업데이트를 통해 보호하는 것이 좋습니다. 이전 버전으로 롤백하면 알려진 보안 문제에 노출될 수 있습니다. 이 정책은 Microsoft Edge 브라우저 업데이트에서 문제를 해결하는 임시 해결 방법으로 사용할 수 있습니다.

브라우저 버전을 일시적으로 롤백하려면 먼저 조직의 모든 사용자에 대해 동기화([https://go.microsoft.com/fwlink/?linkid=2133032](https://go.microsoft.com/fwlink/?linkid=2133032))를 설정하는 것이 좋습니다. 동기화를 설정하지 않은 경우 영구적 검색 데이터 손실이 발생할 수 있습니다. 귀하의 책임하에 이 정책을 사용하세요.

참고: 롤백에 사용할 수 있는 모든 버전은 [https://aka.ms/EdgeEnterprise](https://aka.ms/EdgeEnterprise)에서 확인할 수 있습니다.

이 정책은 Microsoft Edge 버전 86 이상에 적용됩니다.

자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2133918](https://go.microsoft.com/fwlink/?linkid=2133918)을 참조하세요.

이 정책은 Microsoft® Active Directory® 도메인에 연결된 Windows 인스턴스에서만 사용할 수 있습니다.
#### <a name="windows-information-and-settings"></a>Windows 정보 및 설정
##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보
- GP 고유 이름: RollbackToTargetVersion
- GP 이름: 대상 버전으로 롤백
- GP 경로: 
  - 관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge
  - 관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Beta
  - 관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Canary
  - 관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Dev
- GP ADMX 파일 이름: msedgeupdate.admx
##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정
- 경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 값 이름: 
  - (안정): RollbackToTargetVersion{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}
  - (베타): RollbackToTargetVersion{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}
  - (Canary): RollbackToTargetVersion{65C35B14-6C1D-4122-AC46-7148CC9D6497}
  - (Dev): RollbackToTargetVersion{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}
- 값 형식: REG_DWORD
##### <a name="example-value"></a>예를 들어 값:
```
0x00000001
```
[맨 위로 이동](#microsoft-edge---update-policies)


### <a name="targetversionprefix"></a>TargetVersionPrefix
#### <a name="target-version-override"></a>대상 버전 재정의
>Microsoft Edge 업데이트 1.3.119.43 이상

#### <a name="description"></a>설명
이 정책을 사용하도록 설정하고 자동 업데이트를 사용하도록 설정하면 Microsoft Edge는 이 정책 값이 지정하는 버전으로 업데이트됩니다.

정책 값은 특정 Microsoft Edge 버전(예: 83.0.499.12) 이어야 합니다.

장치에 지정된 값보다 더 최신 버전의 Microsoft Edge가 있는 경우 Microsoft Edge는 최신 버전을 유지하고 지정된 버전으로 다운그레이드되지 않습니다.

지정된 버전이 존재하지 않거나 형식이 잘못된 경우 Microsoft Edge는 현재 버전을 유지하고 이후 버전으로 자동 업데이트되지 않습니다.

자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2136707](https://go.microsoft.com/fwlink/?linkid=2136707)을 참조하세요.

이 정책은 Microsoft® Active Directory® 도메인에 연결된 Windows 인스턴스에서만 사용할 수 있습니다.
#### <a name="windows-information-and-settings"></a>Windows 정보 및 설정
##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보
- GP 고유 이름: TargetVersionPrefix
- GP 이름: 대상 버전 재정의
- GP 경로: 
  - 관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge
  - 관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Beta
  - 관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Canary
  - 관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge Dev
- GP ADMX 파일 이름: msedgeupdate.admx
##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정
- 경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 값 이름: 
  - (Stable): TargetVersionPrefix{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}
  - (Beta): TargetVersionPrefix{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}
  - (Canary): TargetVersionPrefix{65C35B14-6C1D-4122-AC46-7148CC9D6497}
  - (Dev): TargetVersionPrefix{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}
- 값 형식: REG_SZ
##### <a name="example-value"></a>예를 들어 값:
```
83.0.499.12
```
[맨 위로 이동](#microsoft-edge---update-policies)

### <a name="targetchanneloverride"></a>TargetChannelOverride
>Microsoft Edge 업데이트 1.3.147.1 이상

#### <a name="description"></a>설명
업데이트할 채널 Microsoft Edge 지정합니다. 

이 포니를 사용하도록 설정하면 Microsoft Edge 옵션을 구성하는 방법에 따라 채널로 업데이트됩니다.

  - 안정: Microsoft Edge 안정된 최신 버전으로 업데이트됩니다.
  - Beta: Microsoft Edge 최신 베타 버전으로 업데이트됩니다.
  - 개발자: Microsoft Edge 최신 개발 버전으로 업데이트됩니다.
  - Extended Stable: Microsoft Edge 보다 긴 릴리스 케이던스를 따르는 최신 확장 안정 버전으로 업데이트됩니다. 자세한 내용은 을 https://go.microsoft.com/fwlink/?linkid=2163508 방문하세요.

해당 정책을 구성하지 않는 경우 Microsoft Edge 채널에 사용할 수 있는 최신 버전으로 업데이트됩니다.

이 정책은 Stable에서만 Microsoft Edge 있습니다.

이 정책은 Microsoft® Active Directory® 도메인에 연결된 Windows 인스턴스에서만 사용할 수 있습니다.
#### <a name="windows-information-and-settings"></a>Windows 정보 및 설정
##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보
- GP 고유 이름: TargetChannelOverride
- GP 이름: 대상 채널 오버라이드
- GP 경로: 
  - 관리 템플릿/Microsoft Edge 업데이트/응용 프로그램/Microsoft Edge
- GP ADMX 파일 이름: msedgeupdate.admx
##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정
- 경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 값 이름: 
  - (안정): TargetChannel{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}
- 값 형식: REG_SZ
##### <a name="example-value"></a>예를 들어 값:
```
extended
```
[맨 위로 이동](#microsoft-edge---update-policies)

### <a name="updaterexperimentationandconfigurationservicecontrol"></a>UpdaterExperimentationAndConfigurationServiceControl
#### <a name="retrieve-configurations-and-experiments"></a>구성 및 실험 검색
>Microsoft Edge 업데이트 1.3.145.1 이상

#### <a name="description"></a>설명
이 Microsoft Edge 업데이트 실험 및 구성 서비스는 실험 페이로드를 배포하는 데 사용됩니다.

실험 페이로드는 Microsoft에서 피드백 테스트에 사용하도록 설정한 개발 초기 기능 목록으로 구성됩니다.

해당 정책을 사용하면 실험 및 구성 서비스에서 실험 페이로드가 다운로드됩니다.

해당 정책을 사용하지 않도록 설정하면 실험 및 구성 서비스와의 통신이 완전히 중지됩니다.

해당 정책을 구성하지 않는 경우 관리되는 장치에서 동작은 '사용 안 하도록 설정' 정책과 동일합니다.

해당 정책을 구성하지 않는 경우 관리되지 않는 장치에서 동작은 '사용' 정책과 동일합니다.

#### <a name="windows-information-and-settings"></a>Windows 정보 및 설정
##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보
- GP 고유 이름: UpdateExperimentationAndConfigureationServiceControl
- GP 이름: 실험 및 구성 서비스와의 업데이트 통신 제어
- GP 경로: 관리 템플릿/Microsoftt Edge 업데이트/Microsoft Edge 업데이트
- GP ADMX 파일 이름: msedgeupdate.admx
##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정
- 경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 값 이름: UpdaterExperimentationAndConfigurationServiceControl
- 값 형식: REG_DWORD
##### <a name="example-value"></a>예를 들어 값:
```
0x00000001
```
[맨 위로 이동](#microsoft-edge---update-policies)

## <a name="preferences-policies"></a>기본 설정 정책

[맨 위로 이동](#microsoft-edge---update-policies)
### <a name="autoupdatecheckperiodminutes"></a>AutoUpdateCheckPeriodMinutes
#### <a name="auto-update-check-period-override"></a>자동 업데이트 확인 기간 재정의
>Microsoft Edge 업데이트 1.2.145.5 이상

#### <a name="description"></a>설명
이 정책을 사용하도록 설정하면 자동 업데이트 확인 최소 간격(분) 값을 설정할 수 있습니다. 그렇지 않으면 기본적으로 자동 업데이트는 10시간마다 업데이트를 확인합니다.

  모든 자동 업데이트 확인을 사용하지 않도록 설정하려면 이 값을 0으로 설정합니다(권장하지 않음).
#### <a name="windows-information-and-settings"></a>Windows 정보 및 설정
##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보
- GP 고유 이름: AutoUpdateCheckPeriodMinutes
- GP 이름: 자동 업데이트 확인 기간 재정의
- GP 경로: 관리 템플릿/Microsoft Edge 업데이트/기본 설정
- GP ADMX 파일 이름: msedgeupdate.admx
##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정
- 경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 값 이름: AutoUpdateCheckPeriodMinutes
- 값 형식: REG_DWORD
##### <a name="example-value"></a>예를 들어 값:
```
0x00000578
```
[맨 위로 이동](#microsoft-edge---update-policies)


### <a name="updatessuppressed"></a>UpdatesSuppressed
#### <a name="time-period-in-each-day-to-suppress-auto-update-check"></a>매일 자동 업데이트 확인 억제 기간
>Microsoft Edge 업데이트 1.3.33.5 이상

#### <a name="description"></a>설명
이 정책을 사용하도록 설정하면 업데이트 확인이 시:분부터 시작하여 기간(분) 동안 억제됩니다. 기간은 일광 절약 시간에 영향을 받지 않습니다. 예를 들어 시작 시간이 22:00이고 기간이 480분인 경우 업데이트는 이 기간 동안 일광 절약 시간제가 시작하거나 종료하는지 관계없이 정확히 8시간 동안 억제됩니다.

  이 정책을 사용하지 않도록 설정하거나 구성하지 않으면 특정 기간 동안 업데이트 검사가 억제되지 않습니다.
#### <a name="windows-information-and-settings"></a>Windows 정보 및 설정
##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보
- GP 고유 이름: UpdatesSuppressed
- GP 이름: 매일 자동 업데이트 확인 억제 기간
  - Options { Hour, Minute, Duration }
- GP 경로: 관리 템플릿/Microsoft Edge 업데이트/기본 설정
- GP ADMX 파일 이름: msedgeupdate.admx
##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정
- 경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 값 이름: 
  - UpdatesSuppressedDurationMin
  - UpdatesSuppressedStartHour
  - UpdatesSuppressedStartMin
- 값 형식: REG_DWORD
##### <a name="example-value"></a>예를 들어 값:
```
duration   : 0x0000003c
start hour : 0x00000001
start min  : 0x00000002
```
[맨 위로 이동](#microsoft-edge---update-policies)

## <a name="proxy-server-policies"></a>프록시 서버 정책

[맨 위로 이동](#microsoft-edge---update-policies)
### <a name="proxymode"></a>ProxyMode
#### <a name="choose-how-to-specify-proxy-server-settings"></a>프록시 서버 설정 지정 방법 선택
>Microsoft Edge 업데이트 1.3.21.81 이상

#### <a name="description"></a>설명
Microsoft Edge 업데이트에서 사용되는 프록시 서버 설정을 지정할 수 있습니다.

  이 정책을 사용하도록 설정하면 다음 프록시 서버 옵션 중에서 선택할 수 있습니다.
   - 프록시 서버를 사용하지 않도록 선택하고 항상 직접 연결하는 경우 다른 모든 옵션은 무시됩니다.
   - 시스템 프록시 설정을 사용하거나 프록시 서버를 자동으로 검색하도록 선택하는 경우 다른 모든 옵션은 무시됩니다.
   - 고정 서버 프록시 모드를 선택하는 경우에는 ‘[프록시 서버 주소 또는 URL](#proxyserver)’정책에 추가 옵션을 지정할 수 있습니다.
   - .pac 프록시 스크립트를 사용하도록 선택하는 경우 ‘[프록시 .pac 파일 URL](#proxypacurl)’ 정책에서 스크립트의 URL을 지정해야 합니다.

  이 정책을 사용하도록 설정하면 조직의 사용자가 Microsoft Edge 업데이트에서 프록시 설정을 변경할 수 없습니다.

  이 정책을 사용하지 않도록 설정하거나 구성하지 않으면 프록시 서버 설정이 구성되지 않지만 조직의사용자가 Microsoft Edge 업데이트에 대한 고유한 프록시 설정을 선택할 수 있습니다.
#### <a name="windows-information-and-settings"></a>Windows 정보 및 설정
##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보
- GP 고유 이름: ProxyMode
- GP 이름: 프록시 서버 설정 지정 방법 선택
- GP 경로: 관리 템플릿/Microsoft Edge 업데이트/프록시 서버
- GP ADMX 파일 이름: msedgeupdate.admx
##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정
- 경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 값 이름: ProxyMode
- 값 형식: REG_SZ
##### <a name="example-value"></a>예를 들어 값:
```
fixed_servers
```
[맨 위로 이동](#microsoft-edge---update-policies)


### <a name="proxypacurl"></a>ProxyPacUrl
#### <a name="url-to-a-proxy-pac-file"></a>프록시 .pac 파일 URL
>Microsoft Edge 업데이트 1.3.21.81 이상

#### <a name="description"></a>설명
PAC(프록시 자동 구성) 파일의 URL을 지정할 수 있습니다.

  이 정책을 사용하면 PAC 파일의 URL을 지정하여 Microsoft Edge 업데이트가 특정 웹 사이트를 가져오는 데 적합한 프록시 서버를 선택하는 방법을 자동화할 수 있습니다.

  이 정책은 ‘[프록시 서버 설정 지정 방법 선택](#proxymode)’ 정책에서 수동 프록시 설정을 지정한 경우에만 적용됩니다.

  ‘[프록시 서버 설정 지정 방법 선택](#proxymode)‘ 정책에서 수동 이외의 프록시 설정을 선택한 경우 이 정책을 구성하지 마세요.
#### <a name="windows-information-and-settings"></a>Windows 정보 및 설정
##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보
- GP 고유 이름: ProxyPacUrl
- GP 이름: 프록시 .pac 파일 URL
- GP 경로: 관리 템플릿/Microsoft Edge 업데이트/프록시 서버
- GP ADMX 파일 이름: msedgeupdate.admx
##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정
- 경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 값 이름: ProxyPacUrl
- 값 형식: REG_SZ
##### <a name="example-value"></a>예를 들어 값:
```
https://www.microsoft.com
```
[맨 위로 이동](#microsoft-edge---update-policies)


### <a name="proxyserver"></a>ProxyServer
#### <a name="address-or-url-of-proxy-server"></a>프록시 서버 주소 또는 URL
>Microsoft Edge 업데이트 1.3.21.81 이상

#### <a name="description"></a>설명
Microsoft Edge 업데이트가 사용할 프록시 서버의 URL을 지정할 수 있습니다.

  이 정책을 사용하도록 설정하면 조직에서 Microsoft Edge 업데이트가 사용하는 프록시 서버 URL을 설정할 수 있습니다.

  이 정책은 ‘[프록시 서버 설정 지정 방법 선택](#proxymode)’ 정책에서 수동 프록시 설정을 선택한 경우에만 적용됩니다.

  ‘[프록시 서버 설정 지정 방법 선택](#proxymode)‘ 정책에서 수동 이외의 프록시 설정을 선택한 경우 이 정책을 구성하지 마세요.
#### <a name="windows-information-and-settings"></a>Windows 정보 및 설정
##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보
- GP 고유 이름: ProxyServer
- GP 이름: 프록시 서버 주소 또는 URL
- GP 경로: 관리 템플릿/Microsoft Edge 업데이트/프록시 서버
- GP ADMX 파일 이름: msedgeupdate.admx
##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정
- 경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 값 이름: ProxyServer
- 값 형식: REG_SZ
##### <a name="example-value"></a>예를 들어 값:
```
https://www.microsoft.com
```
[맨 위로 이동](#microsoft-edge---update-policies)


## <a name="microsoft-edge-webview-policies"></a>Microsoft Edge WebView 정책

[맨 위로 이동](#microsoft-edge---update-policies)
### <a name="install-webview"></a>설치(WebView)
#### <a name="allow-installation"></a>설치 허용
>Microsoft Edge 업데이트 1.3.127.1 이상

#### <a name="description"></a>설명
Microsoft Edge 업데이트를 사용하여 Microsoft Edge WebView를 설치할 수 있는지 여부를 지정할 수 있습니다.

  - 이 정책을 사용하도록 설정하면 사용자가 Microsoft Edge 업데이트를 통해 Microsoft Edge WebView를 설치할 수 있습니다.
  - 이 정책을 사용하지 않도록 설정하면 사용자가 Microsoft Edge 업데이트를 통해 Microsoft Edge WebView를 설치할 수 없습니다.
  - 이 정책을 구성하지 않으면 ‘[설치 허용 기본](#installdefault)’ 정책 구성이 사용자가 Microsoft Edge 업데이트를 통해 해당 Microsoft Edge Webview를 설치할 수 있는지의 여부를 결정합니다.
#### <a name="windows-information-and-settings"></a>Windows 정보 및 설정
##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보
- GP 고유 이름: Install
- GP 이름: 설치 허용
- GP 경로: 관리 템플릿/Microsoft Edge 업데이트/Microsoft Edge WebView
- GP ADMX 파일 이름: msedgeupdate.admx
##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정
- 경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 값 이름: 
  - Install{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
- 값 형식: REG_DWORD
##### <a name="example-value"></a>예를 들어 값:
```
0x00000001
```
[맨 위로 이동](#microsoft-edge---update-policies)


### <a name="update-webview"></a>업데이트(WebView)
#### <a name="update-policy-override"></a>업데이트 정책 재정의
>Microsoft Edge 업데이트 1.3.127.1 이상

#### <a name="description"></a>설명
Microsoft Edge WebView에 대해 자동 업데이트를 사용하도록 설정할지 여부를 지정할 수 있습니다. Microsoft Edge WebView는 응용 프로그램에서 웹 콘텐츠를 표시하는 데 사용하는 구성 요소입니다.
자동 업데이트는 기본적으로 사용하도록 설정되어 있습니다. Microsoft Edge WebView에서 자동 업데이트를 사용하지 않도록 설정하면 이 구성 요소에 종속 된 응용 프로그램과의 호환성 문제가 발생할 수 있습니다.

  이 정책을 사용하도록 설정하면 다음의 옵션을 구성하는 방법에 따라 Microsoft Edge 업데이트가 Microsoft Edge WebView 업데이트를 처리합니다.
  - 항상 업데이트 허용: 업데이트가 자동으로 다운로드되고 적용됩니다.
  - 업데이트 사용 안 함: 업데이트가 다운로드되거나 적용되지 않습니다.

  이 정책을 사용하도록 설정하지 않으면, 업데이트가 자동으로 다운로드되고 적용됩니다.
#### <a name="windows-information-and-settings"></a>Windows 정보 및 설정
##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보
- GP 고유 이름: Update
- GP 이름: 업데이트 정책 재정의
- GP 경로: 관리 템플릿/Microsoft Edge 업데이트/Microsoft Edge WebView
- GP ADMX 파일 이름: msedgeupdate.admx
##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정
- 경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 값 이름: 
  - Update{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
- 값 형식: REG_DWORD
##### <a name="example-value"></a>예를 들어 값:
```
0x00000001
```
[맨 위로 이동](#microsoft-edge---update-policies)


## <a name="see-also"></a>참고 항목
  - [Microsoft Edge 구성](configure-microsoft-edge.md)
  - [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
