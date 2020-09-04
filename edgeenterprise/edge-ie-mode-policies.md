---
title: IE 모드 정책 구성
ms.author: cjacks
author: cjacks
manager: saudm
ms.date: 03/25/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: IE 모드 정책 구성
ms.openlocfilehash: 2d2ded3a3fb338bdf2d815d681b52249007945ac
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980630"
---
# IE 모드 정책 구성

이 문서에서는 IE 모드 정책을 구성하는 방법에 대해 설명합니다.

> [!NOTE]
> 이 문서는 Microsoft Edge **안정**, **Beta** 및 **Dev** 채널 버전 77 이상에 적용됩니다.

IE 모드를 구성하려면 세 단계가 필요합니다.

1. [Internet Explorer 통합 구성](#configure-internet-explorer-integration)
2. [Microsoft Edge에서 IE 모드로 사이트 리디렉션](#redirect-sites-from-microsoft-edge-to-ie-mode)
3. (선택 사항) [IE에서 Microsoft Edge로 사이트 리디렉션](#redirect-sites-from-ie-to-microsoft-edge)

> [!NOTE]
> IE 모드를 사용하도록 설정하는 정책은 Intune을 통해 구성할 수 있습니다. 자세한 내용은 [Microsoft Intune에서 Microsoft Edge를 추가](https://docs.microsoft.com/intune/apps/apps-windows-edge?toc=https://docs.microsoft.com/DeployEdge/toc.json&bc=https://docs.microsoft.com/DeployEdge/breadcrumb/toc.json) 및 [Microsoft Intune을 사용하여 Microsoft Edge 정책 구성](https://docs.microsoft.com/DeployEdge/configure-edge-with-intune)을 참조하세요.

## Internet Explorer 통합 구성

Internet Explorer가 Microsoft Edge(IE 모드) 내에서 직접 열리도록 구성할 수 있습니다. 독립 실행형 Internet Explorer 11 창에서 열리도록 Internet Explorer를 구성할 수도 있습니다. 대부분의 사용자는 IE 모드에서 Microsoft Edge 내에서 직접 사이트를 열 때 선호합니다.

### 그룹 정책을 사용하여 Internet Explorer 통합 사용

1. 최신 [Microsoft Edge 정책 템플릿](https://www.microsoft.com/en-us/edge/business/download)을 다운로드하여 사용합니다.
2. 그룹 정책 편집기 열기.
3. **컴퓨터 구성** > **관리 템플릿** > **Microsoft Edge**를 클릭합니다.
4. **Internet Explorer 통합 구성**을 두 번 클릭합니다.
5. **사용**을 선택합니다.
6. **옵션**에서 드롭다운 값을 설정 
   -  **Internet Explorer 모드** 사이트를 Microsoft Edge에서 IE 모드로 열려면
   -  **Internet Explorer 11** 독립 실행형 Internet Explorer 11 창에서 사이트를 열려면
   -  **없음** edge://flags 또는 명령 줄을 통해 사용자가 Internet Explorer 모드를 구성하지 못하게하려는 경우

   > [!NOTE]
   > 정책을 **사용 안 함**으로 설정하면 IE 모드가 정책에 의해 사용하지 않도록 설정됨을 나타내지만 edge://flags 또는 명령줄 옵션을 통해 설정될 수 있습니다.
7. **확인**또는 **적용**을 클릭하여 이 정책 설정을 저장합니다.

## Microsoft Edge에서 IE 모드로 사이트 리디렉션

IE 모드에서 열어야 하는 사이트를 식별하는 데는 두 가지 방법이 있습니다.

- (권장) [엔터프라이즈 사이트 목록에서 사이트 구성](#configure-sites-on-the-enterprise-site-list)
- [모든 인트라넷 사이트 구성](#configure-all-intranet-sites)

### 엔터프라이즈 사이트 목록에서 사이트 구성

다음 그룹 정책을 사용하여 특정 사이트를 IE 모드에서 열리도록 구성할 수 있습니다.

- [엔터프라이즈 모드 IE 웹 사이트 목록 사용](#configure-using-the-use-the-enterprise-mode-ie-website-list-policy)(Internet Explorer)
- [엔터프라이즈 모드 사이트 목록 구성](#configure-using-the-configure-the-enterprise-mode-site-list-policy)(Microsoft Edge, 버전 78 이상)<br/>이 정책을 사용하여 Microsoft Edge용 별도의 엔터프라이즈 모드 사이트 목록을 만들 수 있습니다. "Internet Explorer 통합 구성"을 사용하도록 설정된 경우 이 정책을 사용하도록 설정하면 "엔터프라이즈 모드 IE 웹 사이트 목록 사용" 정책의 설정이 재정의됩니다. 이 정책을 사용하지 않도록 설정하거나 구성하지 않으면 "Internet Explorer 통합 구성" 정책의 기본 동작에 영향을 주지 않습니다.
    > [!NOTE]
    > Microsoft Edge 정책을 구성할 필요는 없습니다. 많은 조직에서는 이를 재정의로 사용하여 IE 정책을 사용하는 모든 사용자의 현재 사이트 목록을 대상으로 하고 업데이트된 버전을 Microsoft Edge 정책과 함께 파일럿 용도로보다 쉽게 대상으로 지정할 수 있습니다.

엔터프라이즈 모드 사이트 목록에 대한 자세한 내용은 다음을 참조하세요.

- [Enterprise Mode Site List Manager 사용](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/use-the-enterprise-mode-site-list-manager)
- [파일 및 Enterprise Mode Site List Manager(스키마 v.2)를 사용하여 엔터프라이즈 모드 사이트 목록에 여러 사이트 추가](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/add-multiple-sites-to-enterprise-mode-site-list-using-the-version-2-schema-and-enterprise-mode-tool)

### 엔터프라이즈 모드 IE 웹 사이트 사용 정책을 사용하여 구성

IE 모드는 Internet Explorer 용 엔터프라이즈 사이트 목록을 구성하는 기존 정책을 사용하여 단일 목록을 만들고 유지 관리할 수 있습니다.

1. 사이트 목록 XML 만들기 또는 다시 사용
    1. 이제 _\<open-in\>IE11\</open-in\>_ 요소가 있는 모든 사이트가 IE 모드에서 열립니다.
2. 그룹 정책 편집기 열기.
3. **컴퓨터 구성** > **관리 템플릿** > **Windows 구성 요소** > **Internet Explorer**를 클릭합니다.
4. **엔터프라이즈 모드 IE 웹 사이트 목록 사용**을 두 번 클릭합니다
5. **사용**을 선택합니다.
6. **옵션** 아래에서 웹 사이트 목록의 위치를 입력합니다. 다음 위치 중 하나를 사용할 수 있습니다.
    - (권장) HTTPS 위치: **https**:**//iemode/sites.xml**
    - 로컬 네트워크 파일: **\\\network\shares\sites.xml**
    - 로컬 파일: **file:///c:/Users/\<user\>/Documents/sites.xml**
7. **확인** 또는 **적용**을 클릭하여 이러한 설정을 저장합니다.

### 엔터프라이즈 모드 사이트 목록 구성 정책을 사용하여 구성

Microsoft Edge에 대한 별도의 정책으로 IE 모드를 구성할 수도 있습니다. 이 추가 정책을 통해 IE 사이트 목록을 재정의할 수 있습니다. 예를 들어, 일부 조직은 프로덕션 사이트 목록을 모든 사용자에게 대상으로 합니다. 그런 다음이 정책을 사용하여 파일럿 사이트 목록을 소규모 사용자 그룹에 배포할 수 있습니다.

1. 사이트 목록 XML 만들기 또는 다시 사용
    1. 이제 _\<open-in\>IE11\</open-in\>_ 요소가 있는 모든 사이트가 IE 모드에서 열립니다.
2. 그룹 정책 편집기 열기.
3. **컴퓨터 구성** > **관리 템플릿** > **Microsoft Edge**를 클릭합니다.
4. **엔터프라이즈 모드 사이트 목록 구성**을 두 번 클릭합니다.
5. **사용**을 선택합니다.
6. **옵션** 아래에서 웹 사이트 목록의 위치를 입력합니다. 다음 위치 중 하나를 사용할 수 있습니다.
    - (권장) HTTPS 위치: **https**:**//iemode/sites.xml** <!--Trying to keep this from being an active link in MD -->
    - 로컬 네트워크 파일: **\\\network\shares\sites.xml**
    - 로컬 파일: **file:///c:/Users/\<user\>/Documents/sites.xml**
7. **확인** 또는 **적용**을 클릭하여 이러한 설정을 저장합니다.

### 모든 인트라넷 사이트 구성

로컬 모드 인트라넷 영역의 모든 사이트에 대해 IE 모드를 구성할 수 있습니다. 엔터프라이즈 모드 사이트 목록을 사용하여 IE 모드에서 개별 사이트를 제거할 수 있습니다.

>[!NOTE]
>
> 로컬 인트라넷 영역에는 명시적으로 추가된 사이트가 포함되지만 경험적 접근을 사용하여 이 영역에 사이트가 할당됩니다. 여기에는 점 없는 호스트 이름(예 **https**:**//payroll**)과 프록시 구성 스크립트가 프록시를 무시하도록 구성한 사이트가 포함될 수 있습니다. 외부 당사자가 DNS 또는 프록시를 제어하는 경우 웹 사이트를 강제로 IE 모드로 만들 수 있습니다.

1. 로컬 그룹 정책 편집기를 엽니다.
2. **컴퓨터 구성** > **관리 템플릿** > **Microsoft Edge**를 클릭합니다.
3. **Internet Explorer에 모든 인트라넷 사이트 보내기**를 두 번 클릭합니다.
4. **사용**을 선택한 다음 **확인** 또는 **적용**을 클릭하여 정책 설정을 저장합니다.

## IE에서 Microsoft Edge로 사이트 리디렉션

사용자가 필요하지 않은 사이트에 Internet Explorer를 사용하지 못하게 할 수 있습니다. Internet Explorer는 사이트 목록에 없는 사이트를 Microsoft Edge로 자동 리디렉션할 수 있습니다.

1. 그룹 정책 편집기 열기.
2. **컴퓨터 구성** > **관리 도구** > **Windows 구성 요소** > **Internet Explorer**를 클릭합니다.
3. **엔터프라이즈 모드 사이트 목록에 포함되지 않은 모든 사이트를 Microsoft Edge로 보내기**를 두 번 클릭합니다.
4. **사용**을 선택합니다.
5. **확인** 또는 **적용**을 클릭하여 이러한 설정을 저장합니다.
6. **리디렉션된 사이트를 여는 데 사용할 Microsoft Edge 채널 구성**을 두 번 클릭합니다.
7. **사용**을 선택합니다.
8. **옵션** 아래에서 사용할 채널에 대한 상위 3가지 선택을 선택하세요. Internet Explorer는 사용자가 해당 장치에 설치한 최상위 선택 항목으로 리디렉션합니다.
   - Microsoft Edge 안정
   - Microsoft Edge Beta 버전 77 이상
   - Microsoft Edge Dev 버전 77 이상
   - Microsoft Edge Canary 버전 77 이상
   - Microsoft Edge 버전 45 이하
9. **확인** 또는 **적용**을 클릭하여 이러한 설정을 저장합니다.

## 참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [IE 모드 정보](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [추가 엔터프라이즈 모드 정보](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)