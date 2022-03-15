---
title: 엔터프라이즈 사이트 검색 단계별 가이드
ms.author: collw
author: appcompatguy
manager: saudm
ms.date: 01/19/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 엔터프라이즈 사이트 검색을 사용하여 IE 모드를 준비합니다.
ms.openlocfilehash: a93569f455e5671a2d4adf8f5f70238d3f23143d
ms.sourcegitcommit: 556aca8dde42dd66364427f095e8e473b86651a0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2022
ms.locfileid: "12445602"
---
# <a name="enterprise-site-discovery-step-by-step-guide"></a>엔터프라이즈 사이트 검색 단계별 가이드

>[!Note]
> Internet Explorer 11 데스크톱 응용 프로그램은 2022년 6월 15일 사용 및 지원이 중단됩니다(범위 내 항목 목록은 [FAQ 참고](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)). 현재 사용하는 동일한 IE11 앱과 사이트는 Internet Explorer 모드에서 Microsoft Edge로 열 수 있습니다. [여기서 자세한 내용을 알아보세요](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/).

이 문서에서는 Microsoft Endpoint Configuration Manager와 함께 엔터프라이즈 사이트 검색을 사용하는 단계별 가이드를 제공합니다.

엔터프라이즈 사이트 검색은 엔터프라이즈 모드 사이트 목록을 구성하는 데 도움이 될 수 있습니다. 엔터프라이즈 사이트 검색을 통해 다음을 수행할 수 있습니다.

- 레거시 문서 모드를 사용하는 사이트를 검색합니다. 해당 사이트가 최신 브라우저를 검색하고 다양한 HTML을 제공하는 경우가 아니면 IE 모드를 사용해야 할 수 있습니다.
- ActiveX 컨트롤을 사용하는 사이트를 검색합니다. Microsoft Edge는 ActiveX 컨트롤을 지원하지 않습니다. 해당 사이트가 최신 브라우저를 검색하고 다양한 HTML을 제공하는 경우가 아니면 IE 모드를 사용해야 할 수 있습니다.

> [!NOTE]
> 이 문서는 Microsoft Edge **안정**, **Beta** 및 **Dev** 채널 버전 77 이상에 적용됩니다.

## <a name="prerequisites"></a>필수 구성 요소

이 가이드에서는 사용자가 Microsoft 끝점 구성 관리자를 사용하고 있으며 다음 서비스 및 역할이 설치되어 있다고 가정합니다.

1. Microsoft Endpoint Configuration Manager
2. Microsoft SQL Server Reporting Services
3. (선택 사항) 구성된 서비스 지정 역할을 보고하는 구성 관리자

## <a name="download-enterprise-site-discovery-tools"></a>엔터프라이즈 사이트 검색 도구 다운로드

다음의 도구를 다운로드합니다.

- [엔터프라이즈 사이트 검색 설정 및 구성 패키지](https://go.microsoft.com/fwlink/p/?LinkId=517719)
- [Microsoft 보고서 작성기](https://www.microsoft.com/download/details.aspx?id=53613)

## <a name="enable-enterprise-site-discovery"></a>엔터프라이즈 사이트 검색 사용

WMI (Windows Management Instrumentation)에 연결하여 사이트 검색 데이터를 검색하기 전에 먼저 WMI 클래스 공급자를 장치에 배포해야 합니다.

**엔터프라이즈 사이트 검색 설정 및 구성 패키지**에서 최종 소프트웨어 라이브러리 파일 공유의 폴더로 내용을 추출합니다. 예: **\\\\DSL\\EnterpriseSiteDiscovery**.

다음으로 [문서](/configmgr/apps/deploy-use/packages-and-programs)에서 설명한 대로 Microsoft 끝점 구성 관리자에서 패키지를 만들고 다음의 옵션을 선택합니다.

- **패키지** 페이지에서 **이름**을 선택하고 **사이트 검색 사용** 이름을 지정합니다.
- **패키지** 페이지에서 **이 패키지에 원본 파일 포함**을 선택합니다.
- **패키지** 페이지에서 파일을 추출한 원본 폴더 (예: **\\\\DSL\\EnterpriseSiteDiscovery**)를 지정합니다.
- **프로그램 유형** 페이지에서 **표준 프로그램**을 선택합니다.
- **표준 프로그램** 페이지에서 다음과 같이 장치에서 사이트 검색을 구성하는 명령줄을 입력합니다.
  ```dos
  powershell.exe -ExecutionPolicy Bypass .\IETelemetrySetUp-Win8.ps1
  ```
  > [!NOTE]
  > 이 스크립트는 `-ZoneAllowList` 및 `-SiteAllowList`에 대한 명령줄 스위치 사용을 지원합니다. 이 단계별 절차에 대해 그룹 정책 (아래)을 통해 해당 옵션을 구성합니다.
- **표준 프로그램** 페이지에서 옵션을 선택하고 **숨김**을 실행합니다.
- **표준 프로그램** 페이지의 **프로그램 실행 가능**에서 **사용자 로그인 여부** 옵션을 선택합니다.

패키지를 만든 후 **사이트 검색 사용** 패키지 이름을 두 번 클릭하여 속성을 확인합니다. **실행 이후** 속성에서 **구성 관리자가 컴퓨터를 재시작합니다**를 선택합니다. 장치가 다시 부팅되면 WMI 데이터 수집이 시작됩니다.

> [!NOTE]
> [클라이언트 설정 설명서](/configmgr/core/clients/deploy/about-client-settings#computer-restart)에서 설명한 대로 사용자가 장치를 다시 시작하는 데 필요한 시간을 구성할 수 있습니다.

## <a name="configure-enterprise-site-discovery-via-group-policy"></a>그룹 정책을 통해 엔터프라이즈 사이트 검색을 구성합니다.

엔터프라이즈 사이트 검색을 사용하는 경우 수집하는 데이터를 구성할 수 있습니다. [여기](/internet-explorer/ie11-deploy-guide/collect-data-using-enterprise-site-discovery#what-data-is-collected)에 설명된 대로 현지 법률 및 규제 요구 사항을 고려합니다.

1. 그룹 정책 편집기를 엽니다.
2. **컴퓨터 구성** > **관리 템플릿** > **Windows 구성 요소** > **Internet Explorer**를 클릭합니다. 
3. **사이트 검색 WMI 출력 켜기**를 두 번 클릭합니다.
4. **사용**을 선택합니다.
5. **확인** 또는 **적용**을 클릭하여 이 정책 설정을 저장합니다.

사이트 데이터를 수집하는 영역을 제한할 수 있습니다.

1. **영역별 사이트 검색 출력 제한**을 두 번 클릭합니다.
2. **사용**을 선택합니다.
3. 사이트 검색을 설정할 영역을 나타내는 비트 마스크를 입력합니다.
    1. 제한된 사이트 영역
    2. 인터넷 영역
    3. 신뢰할 수 있는 사이트 영역
    4. 로컬 인트라넷 영역
    5. 로컬 컴퓨터 영역
    
    예제 1: **00010**은 로컬 인트라넷 영역에 대해서만 데이터를 수집합니다.

    예제 2: **10111**은 인터넷 영역을 제외한 모든 영역에 대한 데이터를 수집합니다.
4. **확인** 또는 **적용**을 클릭하여 이 정책 설정을 저장합니다.

사이트 데이터를 수집하는 도메인을 제한할 수 있습니다.

1. **도메인별 사이트 검색 출력 제한**을 두 번 클릭합니다.
2. **사용**을 선택합니다.
3. 데이터를 수집하려는 도메인을 한 줄에 하나의 도메인을 입력합니다.
4. **확인** 또는 **적용**을 클릭하여 이 정책 설정을 저장합니다.

## <a name="collect-site-discovery-data-using-configuration-manager"></a>구성 관리자를 사용하여 사이트 검색 데이터를 수집합니다.

이제 장치에서 데이터를 생성하기 때문에 구성 관리자에서 해당 데이터를 수집해야 합니다.

1. 구성 관리자 콘솔에서 **관리** > **클라이언트 설정** > **기본 클라이언트 설정**을 선택합니다.
2. **홈** 탭의 **속성** 그룹에서 **속성**을 선택합니다.
3. **기본 클라이언트 설정** 대화 상자에서 **하드웨어 인벤토리**를 선택합니다.
4. **장치 설정** 목록에서 **집합 클래스**를 선택합니다.
5. **하드웨어 인벤터리 클래스** 대화 상자에서 **추가**를 선택합니다.
6. **하드웨어 인벤터리 클래스 추가** 대화 상자에서 **연결**을 클릭합니다.
7. **WMI (Windows Management Instrumentation)에 연결** 대화 상자에서 엔터프라이즈 사이트 검색이 구성된 컴퓨터의 이름을 입력합니다. 다른 컴퓨터에 연결하는 경우 WMI에 액세스하는 데 필요한 권한이 있는 자격 증명이 필요합니다.
8. **WMI 네임스페이스** 텍스트 상자에 **root\cimv2\IETelemetry**를 입력합니다.
9. **연결**을 선택합니다.
10. 하드웨어 **인벤토리** 클래스 추가 대화 상자의 인벤 **** 토리 클래스 목록에서 **WMI 클래스 IESystemINfo**, **IEUrlInfo** 및 **IECountInfo를 선택합니다**.
11. **확인**를 클릭하여 **클래스 한정자** 대화 상자 및 열려 있는 기타 대화 상자를 닫습니다.

클라이언트가 관리 지점에서 설정을 업데이트한 후 다음 하드웨어 인벤터리가 실행될 때 데이터가 보고됩니다. (기본적으로 7일 마다)

## <a name="import-site-discovery-reports"></a>사이트 검색 보고서 가져오기

엔터프라이즈 사이트 검색 패키지에는 두 개의 샘플 보고서가 포함되어 있습니다. 한 보고서는 ActiveX 컨트롤을 사용하여 사이트를 표시하고 다른 하나는 레거시 문서 모드를 사용하는 사이트를 표시합니다.

### <a name="configure-the-site-discovery-sample-report"></a>사이트 검색 샘플 보고서 구성

다음의 절차를 사용하여 세 가지 데이터 원본 (사용자가 방문한 사이트, 사이트의 시스템에 대한 정보, 사이트에서 사용하는 문서 모드)을 사용하는 샘플 보고서를 만들 수 있습니다. 이 보고서는 레거시 문서 모드에 종속될 수 있는 사이트를 식별하는 데 도움이 됩니다.

1. 보고서 **SCCM_Report-Site_Discovery.rdl**을 구성 관리자 서버에 복사합니다.
2. [Microsoft 보고서 작성기](/sql/reporting-services/install-windows/install-report-builder?view=sql-server-ver15)를 설치합니다.
3. **SCCM_Report-Site_Discovery.rdl**을 두 번 클릭하여 보고서 작성기에서 보고서를 엽니다.
4. 처음으로 보고서를 열 때 보고서가 만들어진 서버에 연결을 시도합니다. **보고서 서버에 연결**하라는 메시지가 표시되면 **아니요**를 클릭합니다.
5. 보고서가 열리면 **데이터 원본**을 확장하고 **DataSource1**을 두 번 클릭합니다.
6. **데이터 원본 속성** 창에서 **보고서에 포함된 연결 사용**을 선택한 다음 **빌드...** 단추를 클릭합니다.
7. **연결 속성** 창에서 **서버 이름**을 선택하고 구성 관리자 서버 이름을 입력합니다. 그런 다음 **데이터베이스 이름 선택 또는 입력**의 드롭다운 목록에서 구성 관리자 데이터베이스의 이름을 선택합니다.
8. **확인**을 클릭하여 **연결 속성** 창을 닫습니다.
9. **연결 테스트**를 클릭하여 연결을 테스트합니다. 연결에 성공하면 **확인**을 클릭하여 **데이터 원본 속성** 창을 닫습니다.
10. **데이터 원본 2**에 대해서도 5~9단계를 반복합니다.
11. **데이터 집합**을 확장하고 **DataSet1**을 두 번 클릭합니다.
12. **데이터 집합 속성** 창에서 **쿼리: ** 텍스트 상자를 클릭하고 **CM_A1B**를 7단계에서 선택한 데이터베이스 이름과 함께 사용합니다.
13. **DataSet2**, **DataSet3**및 **DataSet4**에 대해 11 ~ 12단계를 반복 합니다.
14. 리본의 **홈** 탭에서 **실행** 단추를 클릭하여 보고서를 테스트합니다.
15. 보고서를 저장합니다.
16. Microsoft 보고서 작성기를 닫습니다.
17. 파일 이름을 **사이트 검색.rdl**로 변경합니다.

### <a name="configure-the-activex-sample-report"></a>ActiveX 샘플 보고서를 구성합니다.

다음 절차를 사용하여 하나의 데이터 원본(ActiveX 컨트롤을 사용하는 사이트)을 사용하는 샘플 보고서를 만듭니다. Internet Explorer는 ActiveX 컨트롤을 지원하는 유일한 브라우저이기 때문에 이 사이트에는 IE 모드가 필요할 수 있습니다.

1. 보고서 **SCCM Report Sample - ActiveX.rdl**을 구성 관리자 서버에 복사합니다.
2. [Microsoft 보고서 작성기](/sql/reporting-services/install-windows/install-report-builder?view=sql-server-ver15)를 설치합니다.
3. **SCCM Report Sample - ActiveX.rdl**을 두 번 클릭하여 보고서 작성기에서 보고서를 엽니다.
4. 처음으로 보고서를 열 때 보고서가 만들어진 서버에 연결을 시도합니다. **보고서 서버에 연결**하라는 메시지가 표시되면 **아니요**를 클릭합니다.
5. 보고서가 열리면 **데이터 원본**를 확장하고 **AutoGen__5C6358F2_4BB6_4a1b_A16E_8D96795D8602_** 를 두 번 클릭합니다.
6. **데이터 원본 속성** 창에서 **보고서에 포함된 연결 사용**을 선택한 다음 **빌드...** 단추를 클릭합니다.
7. **연결 속성** 창에서 **서버 이름**을 선택하고 구성 관리자 서버 이름을 입력합니다. 그런 다음 **데이터베이스 이름 선택 또는 입력**의 드롭다운 목록에서 구성 관리자 데이터베이스의 이름을 선택합니다.
8. **확인**을 클릭하여 **연결 속성** 창을 닫습니다.
9. **연결 테스트**를 클릭하여 연결을 테스트합니다. 연결에 성공하면 **확인**을 클릭하여 **데이터 원본 속성** 창을 닫습니다.
10. **데이터 집합**을 확장하고 **DataSet1**을 두 번 클릭합니다.
11. **데이터 집합 속성** 창에서 **쿼리: ** 텍스트 상자를 클릭하고 **CM_A1B**를 7단계에서 선택한 데이터베이스 이름과 함께 사용합니다.
12. 리본의 **홈** 탭에서 **실행** 단추를 클릭하여 보고서를 테스트합니다.
13. 보고서를 저장합니다.
14. Microsoft 보고서 작성기를 닫습니다.
15. 파일을 **ActiveX**로 이름을 변경합니다.

### <a name="upload-configured-reports-to-microsoft-sql-server-reporting-services"></a>Microsoft SQL Server Reporting Services에 구성된 보고서를 업로드합니다.

환경에 대한 보고서를 구성한 후 보고 서버로 업로드합니다.

1. **Reporting Services Configuration Manager** 응용 프로그램을 시작합니다.
2. **보고서 서버 연결** 창에서 **연결**을 클릭한 다음 **웹 포털 사이트 ID** 아래에 나열된 URL을 클릭합니다.
3. 열려 있는 브라우저 창에서 사용자는 **SQL Server Reporting Services 페이지**에 있어야 하며 SCCM 사이트 코드를 보려면 **ConfigMgr_SCCMSiteCode** 폴더를 클릭합니다.
4. 리본에서 **+새**를 마우스로 가리키고 **폴더** 메뉴 항목을 클릭합니다.
5. **엔터프라이즈 사이트 검색**과 같이 폴더 이름을 입력한 다음 **생성** 단추를 클릭합니다.
6. **엔터프라이즈 사이트 검색** 폴더를 클릭합니다.
7. 리본에서 **업로드** 단추를 클릭합니다.
8. **사이트 검색** 보고서를 선택하고 **확인**을 클릭합니다.
9. **ActiveX** 보고서에 대해 7단계 및 8단계를 반복합니다.

### <a name="view-reports-in-configuration-manager"></a>구성 관리자에서 보고서를 확인합니다.

이제 보고서를 사용자 지정하고 업로드했으므로 이를 구성 관리자에서 확인할 수 있습니다.

1. 구성 관리자 콘솔에서 **모니터링** > **보고** > **보고서** > **엔터프라이즈 사이트 검색**을 선택합니다.
2. 보고서를 확인하려면 보고서를 두 번 클릭합니다.

## <a name="disable-enterprise-site-discovery"></a>엔터프라이즈 사이트 검색 해제

데이터 수집이 완료되면 엔터프라이즈 사이트 검색을 사용하지 않도록 설정해야 합니다. [문서](/configmgr/apps/deploy-use/packages-and-programs)에서 설명한 대로 다음의 옵션을 선택하여 Microsoft 끝점 구성 관리자에서 엔터프라이즈 사이트 검색을 사용하지 않도록 설정하는 두 번째 패키지를 만듭니다.

- **패키지** 페이지에서 **이름**을 선택하고 **사이트 검색 해제** 이름을 지정합니다.
- **패키지** 페이지에서 **이 패키지에 원본 파일 포함**을 선택합니다.
- **패키지** 페이지에서 파일을 추출한 원본 폴더 (예: **\\\\DSL\\EnterpriseSiteDiscovery**)를 지정합니다.
- **프로그램 유형** 페이지에서 **표준 프로그램**을 선택합니다.
- **표준 프로그램** 페이지에서 다음과 같이 장치에서 사이트 검색을 해제하는 명령줄을 입력합니다.
  ```dos
  powershell.exe -ExecutionPolicy Bypass .\IETelemetrySetUp-Win8.ps1 -IEFeatureOff
  ```
- **표준 프로그램** 페이지에서 옵션을 선택하고 **숨김**을 실행합니다.
- **표준 프로그램** 페이지의 **프로그램 실행 가능**에서 **사용자 로그인 여부** 옵션을 선택합니다.

## <a name="see-also"></a>참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [IE 모드 정보](./edge-ie-mode.md)
- [추가 엔터프라이즈 모드 정보](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [추가 엔터프라이즈 사이트 검색 정보](/internet-explorer/ie11-deploy-guide/collect-data-using-enterprise-site-discovery)