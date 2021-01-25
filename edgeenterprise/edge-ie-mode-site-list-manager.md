---
title: 'Microsoft Edge의 엔터프라이즈 사이트 목록 관리자 '
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 01/20/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 'Microsoft Edge에서 엔터프라이즈 사이트 목록 관리자 활성화 및 사용 '
ms.openlocfilehash: 2d10886624918c97933a841c428ea66ccf5b34c9
ms.sourcegitcommit: a6c58b19976c194299be217c58b9a99b48756fd0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11281054"
---
# Microsoft Edge의 엔터프라이즈 사이트 목록 관리자

이 문서에서는 Microsoft Edge에서 엔터프라이즈 사이트 목록 관리자에 액세스하도록 설정하고 이를 사용하여 Internet Explorer 모드에 대한 엔터프라이즈 모드 사이트 목록을 만들고, 편집하고, 내보내는 방법을 설명합니다.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 89 이상에 적용됩니다.

## 개요

엔터프라이즈 사이트 목록 관리자는 조직의 사이트 목록을 만들고, 편집하고, 내보낼 수 있는 [독립 실행형 Enterprise Mode Site List Manager 도구](https://www.microsoft.com/download/details.aspx?id=49974)의 브라우저 내 버전입니다.

Internet Explorer 모드용 도구의 향후 향상된 기능도 Microsoft Edge의 엔터프라이즈 사이트 목록 관리자를 통해 사용할 수 있습니다. 독립 실행형 도구는 다운로드 센터에서 계속 사용할 수 있지만 기능 업데이트는 받을 수 없습니다.

## 엔터프라이즈 사이트 목록 관리자에 대한 액세스 사용

[EnterpriseModeSiteListManagerAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#enterprisemodesitelistmanagerallowed) 그룹 정책을 사용하여 도구에 대한 액세스를 구성할 수 있습니다.

이 옵션을 사용하도록 설정하면 *edge://compat*에서 사용자의 왼쪽 탐색 창에 엔터프라이즈 사이트 목록 관리자라는 옵션이 표시됩니다. 사용하지 않도록 설정하면 왼쪽 탐색 창의 엔터프라이즈 사이트 목록 관리자에 대한 진입점이 사용자에게 표시되지 않습니다. 이는 기본 동작입니다.

## 엔터프라이즈 사이트 목록 관리자 사용

엔터프라이즈 사이트 목록 관리자 도구는 v.2 버전의 스키마를 사용합니다. v.1 버전의 스키마를 Enterprise Mode Site List Manager(스키마 v.2)로 가져오면 XML이 v.2 버전의 스키마로 저장됩니다.

### 사이트 목록에 단일 사이트 추가  

다음 단계에 따라 사이트 목록에 개별 사이트를 추가합니다.

> [!NOTE]
> 인터넷 또는 인트라넷 영역이 아닌 특정 URL만 추가할 수 있습니다.

1. 엔터프라이즈 사이트 목록 관리자에서  **사이트 추가**를 클릭합니다.
2. 추가할 웹 사이트의 URL(예: URL 상자에  <domain>.com 또는  <domain>.com/<path> )을 입력합니다.
3. 목록의 **열기** 에서 다음 옵션 중 하나를 선택합니다.

   - **IE11**. IE11 응용 프로그램에서 사이트를 엽니다.
   - **IE 모드**. 사용하도록 설정한 경우 Microsoft Edge의 Internet Explorer 모드에서 사이트를 열고, 그렇지 않은 경우, IE11 앱에서 엽니다.  [Microsoft Edge에서 Internet Explorer 모드](https://docs.microsoft.com/deployedge/edge-ie-mode)를 참조합니다.
   - **MSEdge**. Microsoft Edge에서 사이트를 엽니다.
   - **구성 가능**. 사이트가 IE 모드 엔진 결정에 참여할 수 있도록 합니다. [IE 모드에서 구성 가능한 사이트](https://docs.microsoft.com/deployedge/edge-learnmore-configurable-sites-ie-mode)를 참조하세요.
   - **없음**. 사용자가 선택하는 브라우저에서 열립니다.  

4.  **Compat 모드**에서 다음 옵션 중 하나를 선택합니다.

   - **IE8Enterprise**. 사이트를 IE8 엔터프라이즈 모드로 로드합니다.
   - **IE7Enterprise**. 사이트를 IE7 엔터프라이즈 모드로 로드합니다.
   - **IE[x]**. 여기서 [x]는 문서 모드 번호이고 사이트가 지정된 문서 모드로 로드됩니다.
   - **기본 모드**. 사이트를 페이지의 기본 호환 모드를 사용하여 로드합니다.

   도메인 내의 경로로 인해 도메인 자체와 다른 호환 모드가 필요할 수 있습니다. 예를 들어 도메인이 기본 IE11 브라우저에서는 제대로 작동하는 것처럼 보일 수 있지만 경로의 문제가 있어 엔터프라이즈 모드를 사용해야 하는 경우도 있습니다. 도메인을 이전에 추가한 경우 원래 호환성 선택 항목이 여전히 선택되어 있습니다. 그러나 도메인이 새 도메인이면  **IE8 엔터프라이즈 모드** 가 자동으로 선택됩니다.

   엔터프라이즈 모드는 문서 모드보다 우선 적용되므로, 엔터프라이즈 모드 사이트 목록에 이미 포함된 사이트는 이 업데이트의 영향을 받지 않으며, 원래대로 엔터프라이즈 모드로 계속 로드됩니다. 문서 모드 사용에 대한 자세한 내용은  [문서 모드 및 엔터프라이즈 모드 사이트 목록을 사용하여 웹 호환성 문제 해결](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/fix-compat-issues-with-doc-modes-and-enterprise-mode-site-list)을 참조하세요.

5. **리디렉션 허용** 확인란은 서버 쪽 리디렉션 처리에 적용됩니다. 이 확인란을 선택하면 열기 태그에 지정된 브라우저에서 서버 쪽 리디렉션이 열립니다. 자세한 내용은  [여기](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance#updated-schema-attributes)를 참조하세요.
6. 웹 사이트에 대한 설명을  **설명** 상자에 입력합니다. 관리자는 이 도구에 있는 동안에만 설명을 볼 수 있으며 이러한 설명은 사이트 목록 xml에 보존됩니다.
7. 사이트 목록에 사이트를 추가하려면  **추가**를 클릭합니다.

### XML로 사이트 목록 내보내기

엔터프라이즈 사이트 목록 관리자에서 사이트 목록을 만든 후 엔터프라이즈 모드(.EMIE) 또는 XML 파일로 콘텐츠를 내보낼 수 있습니다. 

> [!NOTE]
> 이 파일에는 호환성 모드 선택 항목을 비롯하여 모든 URL이 포함되므로 안전한 곳에 저장해야 합니다.

사이트 목록을 내보내려면 다음 단계를 따릅니다.

1. 엔터프라이즈 사이트 목록 관리자에서 **XML로 내보내기**를 클릭합니다.
2. **버전 번호**와 **파일 이름**을 입력합니다.
3. **내보내기**를 클릭합니다.

파일을 로컬로 저장하거나 네트워크 공유에 저장할 수 있습니다. 그러나 반드시 레지스트리 키에 지정된 위치에 배포해야 합니다. 자세한 내용은  [Internet Explorer 모드 켜기 및 사이트 목록 사용](https://docs.microsoft.com/deployedge/edge-ie-mode-policies)을 참조하세요.

### 사이트 목록으로 여러 사이트 가져오기

.xml 파일을 만든 후 **XML에서 가져오기**를 사용하여 편집기에 사이트를 대량으로 추가할 수 있습니다.

편집기에서 모든 내용을 바꾸려면 생략 부호(...)를 클릭한 다음 **목록 지우기**를 선택합니다. 편집기를 지운 후 다음 단계에 따라 사이트를 가져올 수 있습니다.

1. 엔터프라이즈 사이트 목록 관리자에서 **XML에서 가져오기**를 클릭합니다. 
2. **파일 선택**을 클릭하여 사이트 목록을 선택하고 포함된 사이트를 도구에 추가합니다. 추가할 사이트 목록을 선택하고  **열기**를 클릭합니다. 지원되는 가져오기 형식은 엔터프라이즈 모드 사이트 목록에 대한 v.2 스키마를 포함하는 .xml, .emie 또는 .txt입니다. [엔터프라이즈 모드 스키마 v.2 지침](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)을 참조하세요.
3.  **로드** 를 클릭하여 사이트를 파일에서 편집기로 추가합니다.

파일을 로컬로 저장하거나 네트워크 공유에 저장할 수 있습니다. 그러나 반드시 레지스트리 키에 지정된 위치에 배포해야 합니다. 자세한 내용은  [Internet Explorer 모드 켜기 및 사이트 목록 사용](https://docs.microsoft.com/deployedge/edge-ie-mode-policies)을 참조하세요.

### 사이트 목록에서 사이트 편집

 엔터프라이즈 사이트 목록 관리자에서 기존 사이트 항목의 특성을 편집할 수 있습니다. 또한 연결된 설명을 추가하거나, 제거하거나, 삭제할 수도 있습니다.

1. 엔터프라이즈 사이트 목록 관리자에서 생략 부호(...)를 클릭하고 편집할 URL의 **사이트 편집**을 선택합니다.
2. URL을 제외한 사이트 항목의 특성을 편집할 수 있습니다. 편집을 마친 후 **저장**을 클릭합니다.

   > [!NOTE]
   > 사이트 항목을 삭제하려면 1단계에서 **사이트 삭제**를 선택합니다.

3. **XML로 내보내기**를 클릭하고 업데이트된 파일을 저장합니다.

파일을 로컬로 저장하거나 네트워크 공유에 저장할 수 있습니다. 그러나 반드시 레지스트리 키에 지정된 위치에 배포해야 합니다. 자세한 내용은  [Internet Explorer 모드 켜기 및 사이트 목록 사용](https://docs.microsoft.com/deployedge/edge-ie-mode-policies)을 참조하세요.

### XML 형식으로 사이트 목록 미리 보기

사이트 목록 위치를 내보내고 저장하기 전에 편집기에서 XML 형식으로 사이트를 미리 볼 수 있습니다. **XML 미리 보기**를 클릭하여 새 탭에서 파일을 열 수 있습니다.

### 엔터프라이즈 사이트 목록 관리자에서 검색

특정 사이트가 사이트 목록에 이미 나타나는지 검색하여 다시 추가하지 않도록 할 수 있습니다.

검색을 하려면 URL의 일부를 편집기 오른쪽 위에 있는  **URL로 사이트 필터링** 검색 상자에 입력합니다.

## 참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [IE 모드 정보](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [추가 엔터프라이즈 모드 정보](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [추가 엔터프라이즈 사이트 검색 정보](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/collect-data-using-enterprise-site-discovery)
