---
title: Microsoft Edge 초기 기본 설정을 구성하는 방법을 알아봅니다.
ms.author: collw
author: dan-wesley
manager: srugh
ms.date: 03/23/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge 초기 기본 설정을 구성하는 방법을 알아봅니다.
ms.openlocfilehash: 751097853e02589fe1b900f6af0d290feb5fbe67
ms.sourcegitcommit: dd8cdbd35726c795ddce917e549ddf17ee7f5290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/11/2022
ms.locfileid: "12473402"
---
# <a name="configure-microsoft-edge-using-initial-preferences-settings-for-the-first-run"></a>첫 번째 실행에 대한 초기 기본 설정을 사용하여 Microsoft Edge 구성

이 문서의 정보를 사용하여 Windows 디바이스에서 Microsoft Edge 초기 기본 설정 설정을 구성합니다.

> [!Note]
> 이 문서는 Microsoft Edge 버전 93 이상에 적용됩니다.

## <a name="configure-policy-settings-on-windows"></a>Windows에서 정책 설정 구성

Microsoft Edge 릴리스 93부터 Microsoft는 관리자가 첫 번째 실행을 위해 브라우저를 구성할 수 있도록 이전에 "마스터 기본 설정"이라는 제한된 수의 초기 기본 설정을 지원합니다. 자세한 내용은 다음 [기본 설정](#preference-settings) 표에서 지원되는 설정을 참조하세요.

배포될 때 초기 기본 설정은 관리되는 디바이스에서 기본 브라우저 설정으로 작동합니다. 이러한 기본 설정은 관리자가 첫 번째 실행의 기본 브라우저 설정으로 사용하는 데 선호되는 설정입니다.

> [!NOTE]
> 사용자가 초기 기본 설정을 변경할 수 있으며 일부 디바이스는 Active Directory® 도메인에 가입되어 있지 않으므로 사용할 수 없습니다.

초기 기본 설정의 몇 가지 예로는 기본 홈페이지의 초기 구성 또는 특정 URL이 있는 탭이 있습니다.

기본 설정은 *initial_preferences* 파일에서 한 번만 복사되며 구성 후 이 파일의 변경 내용은 적용되지 않습니다. [설정이 Microsoft Edge 정책에](/deployedge/microsoft-edge-policies) 의해 관리되고 *initial_preferences 파일에* 구성된 경우 정책은 항상 우선합니다.

### <a name="preference-settings"></a>기본 설정

다음 표에는 현재 Microsoft Edge 지원되는 설정이 표시됩니다.

| 기본 설정 범주 | 설정 |
| - | - |
| Bookmark_bar | show_apps_shortcut<br>show_managed_bookmarks<br>show_on_all_tabs |
| Bookmarks | editing_enabled |
| 브라우저/clear_data | browsing_history<br>browsing_history_basic"<br>캐시<br>cache_basic<br>쿠키<br>download_history<br>form_data<br>암호 |
| 기록 | browsing_history<br>캐시<br>쿠키<br>download_history<br>form_data<br>hosted_apps_data<br>암호<br>site_settings |
| Browser | first_run_tabs<br>dark_theme<br>show_toolbar_bookmarks_button<br>show_toolbar_collections_butto<br>show_toolbar_downloads_button<br>show_home_button<br>show_prompt_before_closing_tabs<br>show_toolbar_history_button |
| default_search_provider | [default_search_provider] 사용 |
| 전체 화면 | 허용 |
| 홈 페이지 | Homepage_url |
| homepage_is_newtabpage | homepage_is_newtabpage |
| 세션 | restore_on_startup<br>startup_urls |
| Extensions | 확장: 설정 |

## <a name="1-download-an-example-initial_preferences-file"></a>1: 예제 initial_preferences 파일 다운로드

시작하려면 [Microsoft Edge Enterprise 방문 페이지에서](https://www.microsoft.com/edge/business/download) "정책" 파일을 다운로드합니다. 다운로드에서 파일을 추출한 다음 *예제* 폴더에서 *initial_preferences* 파일을 엽니다. 다음 스크린샷은 다운로드할 수 있는 정책 파일 옵션을 보여줍니다.

:::image type="content" source="media/initial-preferences-support-on-microsoft-edge-browser/edge-policy-files.png" alt-text="Microsoft Edge 정책 파일을 다운로드할 수 있습니다.":::

## <a name="2-customize-and-validate-the-initial_preferences-file"></a>2: initial_preferences 파일 사용자 지정 및 유효성 검사

다운로드한 *initial_preferences* 파일에서 기본 설정 사용자 지정 및 변경 내용의 유효성을 검사하여 JSON 코드에 오류가 없는지 확인합니다. 오류가 발견되면 *initial_preferences* 파일의 구문과 구조를 확인하고 수정한 다음 다시 확인합니다. Visual Studio Code JSON, 온라인 [JSON 도구](https://jsonformatter.org/) 또는 [JSON 편집의 유효성을](https://code.visualstudio.com/docs/languages/json) 검사하는 몇 가지 예제 도구입니다.

## <a name="3-deploy-preferences-to-users-computer"></a>3: 사용자의 컴퓨터에 기본 설정 배포

*Microsoft Edge* 배포되는 동시에 initial_preferences 파일을 사용자의 디바이스에 배포하고 디바이스의 다음 위치에 파일을 배치합니다.

### <a name="windows-amd64-and-arm64"></a>Windows(AMD64 및 ARM64)

| 채널 | 위치 |
| - | - |
| 안정 | `"C:\Program Files (x86)\Microsoft\Edge\Application"` |
| Beta | `"C:\Program Files (x86)\Microsoft\Edge Beta\Application"` |
|Canary | `"%LOCALAPPDATA%\Microsoft\Edge SxS\Application"` |
| Dev | `"C:\Program Files (x86)\Microsoft\Edge Dev\Application"` |

> [!NOTE]
> initial_preferences 파일을 사용자의 *Windows* 컴퓨터에서 *msedge.exe* 파일과 동일한 폴더에 배포해야 합니다.  

### <a name="macos"></a>macOS

| 채널 | 위치 |
| - | - |
| 안정 | `"~/Library/Application Support/Microsoft Edge/Microsoft Edge Initial Preferences"` |
| Beta | `“~/Library/Application Support/Microsoft Edge Beta/Microsoft Edge Initial Preferences"` |
| Canary | `“~/Library/Application Support/Microsoft Edge Canary/Microsoft Edge Initial Preferences"` |
| Dev | `"~/Library/Application Support/Microsoft Edge Dev/Microsoft Edge Initial Preferences"` |

## <a name="important-notes-msi--pkg-deployment-and-initial_preferences-interaction"></a>중요 정보: MSI/Pkg 배포 및 *initial_preferences* 상호 작용

초기 기본 설정은 최종 사용자가 브라우저를 처음 실행하기 전에 *initial_preferences* 파일이 배포된 후에만 적용됩니다.  

## <a name="see-also"></a>참고 항목

- [*initial_prefrences* 예제 템플릿 파일](/edge/business/download)
