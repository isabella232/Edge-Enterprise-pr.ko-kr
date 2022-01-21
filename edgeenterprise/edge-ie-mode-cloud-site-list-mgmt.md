---
title: IE(Internet Explorer) 모드용 클라우드 사이트 목록 관리
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 12/15/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft 365 관리 센터를 사용하여 IE 모드에 클라우드 사이트 목록 관리를 구성하고 사용하는 방법을 알아봅니다.
ms.openlocfilehash: 4c37c2b3ec98252f430bf635456c6849def0a0e3
ms.sourcegitcommit: e7f3098d8b7d91cae20b5778a71a87daababc312
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "12298110"
---
# <a name="cloud-site-list-management-for-internet-explorer-ie-mode"></a>IE(Internet Explorer) 모드용 클라우드 사이트 목록 관리

이 문서에서는 Microsoft 365 관리 센터를 통해 IE(Internet Explorer) 모드의 클라우드 사이트 목록 관리를 구성하고 사용하는 방법을 설명합니다.

> [!NOTE]
> 이 환경은 현재 전 세계 클라우드 인스턴스에서만 사용할 수 있습니다.

## <a name="overview"></a>개요

워크플로 및 애플리케이션을 IE11에서 IE 모드로 전환하면 **클라우드 사이트 목록 관리**를 통해 클라우드에서 IE 모드의 사이트 목록을 관리할 수 있습니다. **Microsoft 365 관리 센터**의 **Microsoft Edge 사이트 목록** 환경을 사용하여 사이트 목록을 사용할 수 있습니다.

자세한 내용은 다음 동영상을 시청하세요.

[ ![IE 모드의 새 클라우드 사이트 목록 관리](media/edge-ie-mode-cloud-site-list-mgmt/0.png)](https://www.youtube.com/watch?v=p3FyGvsNKC8 "|::ref1::|").

> [!NOTE]
> 이 환경은 현재 모든 사용자에게 제공되고 있으며, 12월 중순에 완료될 것으로 예상됩니다.

이 환경을 사용하면 사이트 목록을 호스트하기 위해 온-프레미스 인프라가 필요하지 않고, 조직의 사이트 목록을 규격 클라우드 위치에 저장할 수 있습니다. Microsoft 365 관리 센터를 통해 사이트 목록을 만들고, 가져오고, 내보내고, 사이트 목록 항목에 대한 변경 내용을 감사할 수 있습니다. 여러 사이트 목록을 클라우드에 게시하고, 그룹 정책으로 여러 장치 그룹을 할당하여 다양한 목록을 사용할 수 있습니다.

## <a name="prerequisites"></a>필수 구성 요소

이 기능을 사용하려면 다음 필수 구성 요소가 필요합니다.

1. 고객이 Azure Active Directory 테넌트를 보유해야 합니다.
2. 관리자는 Microsoft Edge 버전 93 이상을 설치하고, [정책 파일](https://aka.ms/edgeenterprise) 최신 버전을 보유해야 합니다.
3. Microsoft Edge 사이트 목록 환경에 액세스하려면 관리자는 테넌트의 [Edge 관리자](/azure/active-directory/roles/permissions-reference#edge-administrator)이거나 [전역 관리자](/azure/active-directory/roles/permissions-reference#global-administrator)여야 합니다.

## <a name="cloud-site-list-management-experience"></a>클라우드 사이트 목록 관리 환경

이 환경에는 세 가지 측면이 있습니다.

### <a name="publish-enterprise-site-list-to-the-cloud"></a>클라우드에 엔터프라이즈 사이트 목록 게시

관리자는 해당 테넌트 내 Microsoft Edge 클라이언트가 IE 모드 환경을 위해 다운로드할 수 있는 인증된 엔드포인트에 사이트를 하나 이상 게시할 수 있습니다. 관리자는 기존 엔터프라이즈 사이트 목록 XML을 Microsoft 365 관리 센터의 Microsoft Edge 사이트 목록 환경으로 가져온 다음 클라우드 위치에 게시할 수 있습니다.

### <a name="associate-the-cloud-hosted-site-list-with-microsoft-edge"></a>클라우드 호스팅된 사이트 목록을 Microsoft Edge와 연결

Microsoft Edge 버전 93에서는 관리자가 [InternetExplorerIntegrationCloudSiteList](/deployedge/microsoft-edge-policies#internetexplorerintegrationcloudsitelist) 설정을 사용하여 Microsoft Edge가 IE 모드에 사용할 수 있는 클라우드 호스팅된 사이트 목록 중 하나를 구성할 수 있습니다. 클라이언트가 클라우드의 사이트 목록을 사용하려면 사용자가 Microsoft Edge에 로그인한 상태여야 합니다.

> [!IMPORTANT]
> 이 정책이 구성되면 원래 [InternetExplorerIntegrationSiteList](/deployedge/microsoft-edge-policies#internetexplorerintegrationsitelist) 정책을 재정의합니다.

### <a name="manage-site-list-contents-on-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터에서 사이트 목록 콘텐츠 관리

관리자는 새 목록을 만들거나 기존 사이트 목록을 Microsoft Edge 사이트 목록 환경으로 가져올 수 있습니다. 사이트 목록 콘텐츠를 추가, 편집, 삭제하고, 설명 기록을 확인해서 개별 항목의 변경 내용을 추적할 수 있습니다. 다음 구역에서는 공개 미리 보기에 옵트인하고 Microsoft 365 관리 센터에서 Microsoft Edge 사이트 목록 환경에 액세스하는 방법을 설명합니다.

## <a name="publish-enterprise-site-list-to-the-cloud"></a>클라우드에 엔터프라이즈 사이트 목록 게시

다음 단계를 가이드로 사용하여 사이트 목록을 만들고, 사이트 목록을 가져오고, 사이트 목록을 게시하세요. 이 단계를 완료하기 전에 Microsoft 365 관리 센터에 로그인합니다.

1. 관리자 로그인 정보를 사용해 [Microsoft 365 관리 센터](https://admin.microsoft.com)에 로그인합니다.
2. 왼쪽 탐색 창에서 **설정 > 조직 설정**을 선택합니다.
3. **Microsoft Edge 사이트 목록** 옵션이 표시됩니다.

   > [!NOTE]
   > 모든 프로덕션 인스턴스에 출시하는 동안 조직 설정 페이지에 이 옵션이 표시되지 않는 경우 **대상 지정 릴리스**에 옵트인해야 합니다. **Microsoft Edge 사이트 목록** 옵션이 표시되지 않는 경우 [Microsoft 365 관리 센터의 “조직 설정” 페이지에 “Microsoft Edge 사이트 목록”이 표시되지 않습니다. 이유가 무엇인가요?](#i-do-not-see-the-microsoft-edge-site-lists-option-in-the-org-settings-page-on-microsoft-365-admin-center-why-is-that) FAQ를 확인합니다.

### <a name="steps-to-create-a-site-list"></a>사이트 목록 만들기 단계

1. 조직 설정 페이지에서 **Microsoft Edge 사이트 목록**을 선택합니다.
2. 다음에 표시되는 페이지에서 **새 목록 만들기**를 선택합니다.
3. **사이트 목록 이름**과 **설명**을 입력한 다음 **만들기**를 선택합니다.
4. 확인 메시지가 표시되면 **창 닫기**를 선택합니다.

### <a name="steps-to-import-a-site-list"></a>사이트 목록 가져오기 단계

1. 사용할 사이트 목록을 선택합니다.
2. 다음에 표시되는 페이지에서 **목록 가져오기**를 선택합니다.
3. 오른쪽 창에서 **찾아보기**를 선택합니다.
4. 가져올 파일을 선택한 다음 창 맨 아래의 **업로드**를 선택합니다.
5. 업로드된 파일의 URL을 훑어볼 수 있습니다. 다른 파일을 선택하려면 창 맨 위의 **다른 파일 업로드**를 선택합니다. 더 수정할 내용이 없으면 창 맨 아래의 **추가**를 선택합니다.
6. 목록을 가져온 후 **창 닫기**를 선택합니다. 

### <a name="steps-to-publish-a-site-list"></a>사이트 목록 게시 단계

1. 사이트 목록을 게시하려면 이전 수준으로 돌아가 Microsoft Edge 목록 페이지로 이동합니다. 사이트 목록 이름 위의 이동 경로를 선택해 이전 수준으로 올라갑니다.
2. Microsoft Edge 사이트 목록 페이지에서 클라우드에 게시할 사이트 목록을 선택한 다음 **사이트 목록 게시**를 선택합니다.
3. 오른쪽 창에서 **버전 숫자**를 업데이트하고 창 맨 아래의 **게시**를 선택합니다.
4. 확인 후 **창 닫기**를 선택합니다.
5. **게시 상태** 열과 **마지막 게시 시간**, **마지막 게시자**가 모두 업데이트됩니다.

## <a name="associate-the-cloud-hosted-site-list-with-microsoft-edge"></a>클라우드 호스팅된 사이트 목록을 Microsoft Edge와 연결

다음 단계에 따라 클라우드 호스팅된 사이트 목록을 Microsoft Edge와 연결합니다.

1. 게시된 사이트 목록을 사용하도록 장치를 구성하려면 장치에 할당하려는 사이트 목록을 선택합니다.
2. 다음에 표시되는 페이지에서 **사이트 목록 ID**를 복사합니다.
3. 선택한 장치 그룹에 대해 **사용**을 선택하고 [엔터프라이즈 모드 클라우드 사이트 목록 구성](/deployedge/microsoft-edge-policies#internetexplorerintegrationcloudsitelist) 정책에 **사이트 목록 ID**를 입력합니다.
4. 명령 프롬프트에서 **gpupdate/force**를 실행하여 정책으로 장치를 업데이트하거나 그룹 정책이 적용될 때까지 기다립니다. 정책이 업데이트된 후 [edge://compat/enterprise](edge://compat/enterprise)로 이동해서 Microsoft Edge가 클라우드 사이트 목록을 읽고 있는지를 확인할 수 있습니다. Microsoft Edge에 로그인해야 합니다.

> [!NOTE]
> 사이트 목록을 처음 게시하고 그룹 정책을 업데이트하고 나면 Microsoft Edge를 다시 시작해야 합니다. 60초간 기다리거나 [edge://compat/enterprise](edge://compat/enterprise)에서 업데이트 적용 버튼을 선택합니다. 이미 연결된 사이트 목록에 업데이트를 게시하는 경우 캐시에 사이트 목록 이전 버전이 있을 수 있습니다. 이 항목은 60초 후에 새로 고쳐집니다. 자세한 내용은 [사용자가 Microsoft Edge에서 로그아웃하면 어떻게 되나요?](#what-happens-if-users-log-out-of-microsoft-edge)를 참조하세요.

## <a name="manage-site-list-contents-on-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터에서 사이트 목록 콘텐츠 관리

개별 사이트 항목을 추가하고, 사이트 항목을 삭제하고, 주석 설명 기록을 볼 수 있습니다.
사이트 목록을 온-프레미스에서 호스트해야 하는 하이브리드 시나리오가 있는 경우 Microsoft 365 관리 센터에서 사이트 목록을 내보낼 수 있습니다. 다음 단계 안내에 따라 사이트 목록 콘텐츠를 관리하세요.

### <a name="add-individual-sites-to-the-site-list"></a>사이트 목록에 개별 사이트 추가

모든 사이트 목록에 개별 사이트를 추가할 수 있습니다. 목록에 사이트를 추가한 후 **필터** 버튼(검색 입력 영역 옆)으로 미리 지정된 필터를 사용해 목록에 대한 업데이트를 볼 수 있습니다.

1. 사이트를 추가할 사이트 목록으로 이동합니다.
2. **사이트 추가**를 선택합니다.
3. 사이트 주소를 입력하고 사이트를 여는 데 사용할 엔진을 선택합니다. 필요한 경우 설명을 추가하고 **저장**을 선택합니다.

   > [!NOTE]
   > 게시된 사이트 목록에 추가된 모든 항목의 **상태 열**이 **추가 보류 중**을 표시합니다. 화면 맨 위의 **Microsoft Edge 사이트 목록**을 선택해 사이트 목록으로 이동할 경우 **게시 상태** 열이 **변경 내용 게시 보류 중**으로 표시된 것을 볼 수 있을 겁니다. 이는 사용자가 사이트 목록에 대한 최신 업데이트를 받으려면 해당 업데이트를 게시해야 한다는 것을 뜻합니다. **필터** 버튼(검색창 옆)으로 **추가 보류 중**을 선택해 게시를 보류 중인 모든 추가된 항목을 볼 수 있습니다.

### <a name="view-the-change-history-for-site-entries"></a>사이트 항목에 대한 변경 기록 보기

사이트 항목에 대한 변경 기록을 보려면 다음을 수행합니다.

- 변경 기록을 볼 사이트 항목을 선택한 다음 **설명 보기**를 선택합니다.

### <a name="delete-a-site-from-the-site-list"></a>사이트 목록에서 사이트 삭제

다음 단계에 따라 사이트 항목을 삭제합니다.

1. 사이트를 삭제할 사이트 목록 항목을 선택합니다. **사이트 삭제**를 선택합니다.
2. 창 맨 아래의 **삭제**를 선택합니다.
3. 사이트 항목이 삭제되었다는 확인 메시지가 표시된 후 해당 항목은 사이트 목록이 클라우드 위치에 게시될 때까지 목록에 유지됩니다. 게시 전에 필터 버튼을 선택해서 **삭제 보류 중** 상태의 사이트를 필터링하고 삭제된 사이트 목록을 확인할 수 있습니다.

   > [!NOTE]
   > 게시된 사이트 목록에서 삭제된 모든 항목의 **상태 열**이 **삭제 보류 중**을 표시합니다. 화면 맨 위의 **Microsoft Edge 사이트 목록**을 선택해 사이트 목록으로 이동할 경우 **게시 상태** 열이 **변경 내용 게시 보류 중**으로 표시된 것을 볼 수 있을 겁니다. 이는 사용자가 사이트 목록에 대한 최신 업데이트를 받으려면 해당 업데이트를 게시해야 한다는 것을 뜻합니다. **필터** 버튼(검색창 옆)으로 **삭제 보류 중**을 선택해 게시를 보류 중인 모든 삭제된 항목을 볼 수 있습니다.

### <a name="copy-a-site-to-other-site-lists"></a>다른 사이트 목록에 사이트 복사

사이트 목록의 사이트 항목을 하나 이상의 사이트 목록으로 복사하려면 다음 단계를 사용합니다.

1. 다른 목록에 복사할 사이트 항목을 선택합니다. **더 많은 목록으로 복사**를 선택합니다.
2. 드롭다운 목록에서 복사할 하나 이상의 사이트 목록을 선택합니다.
3. 창 아래쪽에서 **사이트 복사**를 선택합니다.
4. 사이트 항목이 복사되었다는 확인 메시지가 표시되고, 해당 사이트 항목은 사이트 항목을 복사해서 가져온 사이트 목록에 유지됩니다. 그리고 이 사이트 항목 복사본을 추가한 사이트 목록에도 표시됩니다.

   > [!NOTE]
   > 게시된 사이트 목록에 복사한 모든 항목의 **상태 열**이 **추가 보류 중**으로 표시됩니다. 화면 맨 위의 **Microsoft Edge 사이트 목록**을 선택해 사이트 목록으로 이동할 경우 게시 상태 열이 **변경 내용 게시 보류 중**으로 표시된 것을 볼 수 있을 겁니다. 이는 사용자가 사이트 목록에 대한 최신 업데이트를 받으려면 해당 업데이트를 게시해야 한다는 것을 뜻합니다. **필터** 버튼(검색창 옆)으로 **추가 보류 중**을 선택해 게시를 보류 중인 모든 추가된 항목을 볼 수 있습니다.

### <a name="export-a-site-list"></a>사이트 목록 내보내기

사용자가 사이트 목록을 내보내야 할 때가 있습니다. 예를 들어 사이트 목록을 클라우드로 바로 이동할 수 없거나, 클라우드와 온-프레미스의 사이트 목록으로 하이브리드 환경을 유지 관리해야 하는 경우가 여기 해당합니다. 클라우드 사이트 목록 관리 환경을 사용해 중앙 위치에서 사이트 목록에 대한 업데이트를 관리하고, 사이트 목록을 온-프레미스 호스트로 내보낼 수 있습니다.

1. Microsoft Edge 사이트 목록 페이지에서 내보낼 사이트 목록을 선택합니다.
2. 다음에 표시되는 페이지에 사이트 항목과 **목록 내보내기** 옵션이 표시됩니다.
3. **목록 내보내기**를 선택하여 사이트 목록 XML 파일을 다운로드합니다.

## <a name="faq"></a>FAQ

### <a name="i-do-not-see-the-microsoft-edge-site-lists-option-in-the-org-settings-page-on-microsoft-365-admin-center-why-is-that"></a>Microsoft 365 관리 센터의 "조직 설정" 페이지에 "Microsoft Edge 사이트 목록" 옵션이 표시되지 않습니다. 이유가 무엇인가요?

12월 중순에 출시가 완료되면 환경을 사용할 수 있습니다. 환경을 출시하는 동안 Microsoft 365 관리 센터에서 이 환경을 보려면 옵트인해야 합니다. 옵트인하려면 Microsoft 365 전역 관리자여야 합니다.

옵트인하려면 다음 단계를 수행합니다.

1. [Microsoft 365 관리 센터](https://admin.microsoft.com)에 로그인한 다음  **설정 > 조직 설정**으로 이동합니다.  **조직 프로필** 탭에서  **릴리스 기본 설정**을 선택합니다.
2. 대상 릴리스를 사용하지 않으려면  **표준 릴리스**를 선택한 다음  **변경 내용 저장**을 선택합니다.
3. 조직의 모든 사용자가 대상 릴리스를 사용하도록 하려면  **모든 사용자 대상 릴리스 사용**을 선택한 다음  **변경 내용 저장**을 선택합니다.
4. 조직의 일부 사용자가 대상 릴리스를 사용하도록 하려면  **일부 사용자 대상 릴리스 사용**을 선택한 다음  **변경 내용 저장**을 선택합니다.
5.  **사용자 선택** 을 선택해서 한 번에 한 사용자씩 추가하거나  **사용자 업로드** 를 사용해 대량으로 추가합니다.
6. 사용자 추가를 마치면  **변경 내용 저장**을 선택합니다.

자세한 내용은 [표준 또는 대상 릴리스 옵션 설정 - Microsoft 365 관리자](/microsoft-365/admin/manage/release-options-in-office-365)를 참조하세요.

### <a name="when-i-select-microsoft-edge-site-lists-and-try-to-create-a-new-list-i-get-this-error---request-failed-with-status-code-500-why-is-that"></a>"Microsoft Edge 사이트 목록"을 선택하고 새 목록을 만들려고 하면 "요청이 상태 코드 500으로 실패했습니다"라는 오류가 발생합니다. 이유가 무엇인가요?

Microsoft Edge 사이트 목록은 Exchange Online, SharePoint Online, Teams 및 Azure Active Directory와 같은 엔터프라이즈 클라우드 서비스와 공유되는 서비스 인프라에 데이터와 구성을 저장합니다. 드문 경우이지만 Microsoft Edge 사이트 목록이 이 인프라를 사용하는 첫 번째 기능인 경우 프로비전에 다소 시간이 걸릴 수 있습니다. 이러한 경우 Microsoft 365 관리 센터의 초기 요청이 실패합니다. 요청이 실패하면 문제를 해결하기 위해 프로비전 시스템으로 경고가 전송됩니다. 일반적으로 프로비전은 3일 후에 완료됩니다. 따라서 이 오류가 발생하면 며칠 후에 다시 시도하고 새 목록을 만드세요. 여전히 새 목록을 만들 수 없거나 긴급 지원이 필요한 경우 Microsoft 지원에 문의하세요.

### <a name="can-users-who-havent-signed-in-to-microsoft-edge-download-the-site-list"></a>Microsoft Edge에 로그인하지 않은 사용자가 사이트 목록을 다운로드할 수 있나요?

아니요. 클라우드 호스팅된 사이트 목록을 다운로드하려면 사용자가 브라우저에 로그인해야 합니다. 사용자 환경 중단을 방지하기 위해 암시적 로그인을 허용하도록 정책을 구성할 수 있습니다. 자세한 내용은 [ImplicitSignInEnabled](/DeployEdge/microsoft-edge-policies#implicitsigninenabled)를 참조하세요.

### <a name="what-is-the-default-refresh-interval-after-updates-are-made-to-site-list-contents"></a>사이트 목록 콘텐츠를 업데이트한 후 기본 새로 고침 간격이 뭔가요?

사이트 목록은 Microsoft Edge에서 2시간마다 새로 고쳐집니다. [InternetExplorerIntegrationSiteListRefreshInterval](/deployedge/microsoft-edge-policies#internetexplorerintegrationsitelistrefreshinterval) 정책에서 이 간격을 변경할 수 있습니다. 최소 새로 고침 간격은 30분입니다.

### <a name="what-happens-if-users-log-out-of-microsoft-edge"></a>사용자가 Microsoft Edge에서 로그아웃하면 어떻게 되나요?

사이트 목록에 액세스하려면 첫 다운로드 시 확실히 브라우저에 로그인해야 합니다. 사용자가 로그인 후 로그아웃하는 경우 사이트 목록이 Microsoft Edge에 캐시됩니다. 사용자가 Azure Active Directory(Azure AD) 계정의 Microsoft Edge에서 로그아웃하는 경우에도 목록은 캐시된 상태를 유지합니다. 클라우드 사이트 목록 정책이 구성된 동안에는 Microsoft Edge가 클라우드가 아닌 다운로드 위치로 대체하려고 시도하지 않습니다. Microsoft Edge는 다음 시간에 캐시된 사이트 목록을 업데이트하려고 시도합니다(사용자가 Microsoft Edge에 로그인하지 않으면 모든 시도가 실패함).

- 브라우저를 다시 시작한 후 60초. 60초의 시작 지연 시간을 더 짧게 하려면 [InternetExplorerIntegrationSiteListRefreshInterval](/deployedge/microsoft-edge-policies#internetexplorerintegrationsitelistrefreshinterval) 정책을 사용하여 지연 시간을 변경할 수 있습니다.
- Microsoft Edge가 실행되는 동안 2시간마다.

## <a name="support-and-feedback"></a>지원 및 피드백

클라우드 사이트 목록 관리 환경에 대한 지원은 기존 [Microsoft 프리미어 지원](https://www.microsoft.com/unifiedsupport/premier) 계약에 포함됩니다. Microsoft 지원에 문제를 보고하거나 피드백을 남길 수 있습니다. [TechCommunity 포럼](https://techcommunity.microsoft.com/t5/enterprise/bd-p/EdgeInsiderEnterprise)에도 피드백을 남길 수 있습니다.

## <a name="see-also"></a>참고 항목

- [IE 모드 정보](./edge-ie-mode.md)
- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
  
