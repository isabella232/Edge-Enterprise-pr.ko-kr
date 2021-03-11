---
title: Microsoft Edge WebView2 정책 문서
ms.author: stmoody
author: dan-wesley
manager: tahills
ms.date: 03/10/2021
audience: ITPro
ms.topic: reference
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
ms.custom: ''
description: Microsoft Edge 브라우저에서 지원하는 모든 정책에 대한 Windows 및 Mac 설명서
ms.openlocfilehash: 47072c6e39944bb51fd4c683a9597125d8776d08
ms.sourcegitcommit: e3762b1a204c143b4e2264100affae3d9ddaaffc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2021
ms.locfileid: "11406359"
---
# <a name="microsoft-edge-webview2---policies"></a>Microsoft Edge WebView2 – 정책

최신 버전의 Microsoft Edge WebView2에는 다음과 같은 정책이 포함되어 있습니다. 이러한 정책을 사용하여 조직에서 Microsoft Edge WebView2를 실행하는 방법을 구성할 수 있습니다.

Microsoft Edge WebView2의 업데이트 방법 및 시기를 제어하는 데 사용되는 추가 정책 집합에 대한 자세한 내용은 [Microsoft Edge 업데이트 정책 참조](microsoft-edge-update-policies.md)를 참조하세요.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 87 이상에 적용됩니다.

## <a name="available-policies"></a>사용 가능한 정책

다음 표에는 이 릴리스의 Microsoft Edge WebView2에서 사용할 수 있는 모든 그룹 정책이 나열되어 있습니다. 특정 정책에 대해 자세히 알아보려면 표의 링크를 사용하세요.

- [로더 재정의 설정](#loader-override-settings)


### [*<a name="loader-override-settings"></a>로더 재정의 설정*](#loader-override-settings-policies)

|정책 이름|캡션|
|-|-|
|[BrowserExecutableFolder](#browserexecutablefolder)|브라우저 실행 파일 폴더의 위치 구성|
|[ReleaseChannelPreference](#releasechannelpreference)|릴리스 채널 검색 순서 기본 설정|




  ## <a name="loader-override-settings-policies"></a>로더 재정의 설정 정책

  [맨 위로 이동](#microsoft-edge-webview2---policies)

  ### <a name="browserexecutablefolder"></a>BrowserExecutableFolder

  #### <a name="configure-the-location-of-the-browser-executable-folder"></a>브라우저 실행 파일 폴더의 위치 구성

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows (87 이상)

  #### <a name="description"></a>설명

  이 정책은 WebView2 응용 프로그램이 지정된 경로에서 WebView2 런타임을 사용하도록 구성합니다. 폴더에는 msedgewebview2.exe, msedge.dll 등의 파일이 있어야 합니다.

폴더 경로에 대한 값을 설정하려면 값 이름과 값 쌍을 입력합니다. 값 이름을 응용 프로그램 사용자 모델 ID 또는 실행 파일 이름으로 설정합니다. 값 이름으로 "*" 와일드카드를 사용하여 모든 응용 프로그램에 적용할 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: BrowserExecutableFolder
  - GP 이름: 브라우저 실행 파일 폴더의 위치 구성
  - GP 경로(필수): 관리 템플릿/Microsoft Edge WebView2/로더 재정의 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdgeWebView2.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로(필수): SOFTWARE\정책\Microsoft\Edge\WebView2\BrowserExecutableFolder
  - 경로 (권장): 해당 없음
  - 값 이름: REG_SZ 목록
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\WebView2\BrowserExecutableFolder = "Name: *, Value: C:\\Program Files\\Microsoft Edge WebView2 Runtime Redistributable 85.0.541.0 x64"

```

  

  [맨 위로 이동](#microsoft-edge-webview2---policies)

  ### <a name="releasechannelpreference"></a>ReleaseChannelPreference

  #### <a name="set-the-release-channel-search-order-preference"></a>릴리스 채널 검색 순서 기본 설정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows (87 이상)

  #### <a name="description"></a>설명

  기본 채널 검색 순서는 WebView2 Runtime, 베타, Dev 및 Canary입니다.

기본 검색 순서를 거꾸로 하려면 이 정책을 1로 설정합니다.

릴리스 채널 기본 설정 값을 설정하려면 값 이름과 값 쌍을 입력합니다. 값 이름을 응용 프로그램 사용자 모델 ID 또는 실행 파일 이름으로 설정합니다. 값 이름으로 "*" 와일드카드를 사용하여 모든 응용 프로그램에 적용할 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ReleaseChannelPreference
  - GP 이름: 릴리스 채널 검색 순서 기본 설정
  - GP 경로(필수): 관리 템플릿/Microsoft Edge WebView2/로더 재정의 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdgeWebView2.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로(필수): SOFTWARE\정책\Microsoft\Edge\WebView2\ReleaseChannelPreference
  - 경로 (권장): 해당 없음
  - 값 이름: REG_SZ 목록
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\WebView2\ReleaseChannelPreference = "Name: *, Value: 1"

```

  

  [맨 위로 이동](#microsoft-edge-webview2---policies)


## <a name="see-also"></a>참고 항목

- [Microsoft Edge 구성](configure-microsoft-edge.md)
- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [Microsoft Office 보안 기준 블로그](https://techcommunity.microsoft.com/t5/microsoft-security-baselines/bg-p/Microsoft-Security-Baselines)