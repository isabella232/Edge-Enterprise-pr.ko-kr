---
title: 브라우저에서 초기 Microsoft Edge 지원
ms.author: collw
author: AndreaLBarr
manager: srugh
ms.date: 07/27/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 초기 기본 설정은 브라우저에서 Microsoft Edge 지원됩니다.
ms.openlocfilehash: 39af88d21107ad548166c749c3ba765754270b48
ms.sourcegitcommit: 715cb8c8101a6daed48563f33d2bc40ee7109e0e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2021
ms.locfileid: "11882264"
---
# <a name="configure-microsoft-edge-using-initial-preferences-settings-for-the-first-run"></a>첫 번째 실행에 대한 초기 기본 설정을 사용하여 Microsoft Edge 구성

다음 정보를 사용하여 Microsoft Edge 디바이스에서 초기 기본 Windows 구성합니다.

> [!Note]
> 이 문서는 Microsoft Edge 버전 93 이상에 적용됩니다.

## <a name="configure-policy-settings-on-windows"></a>Windows에서 정책 설정 구성

Microsoft Edge 릴리스 93부터 Microsoft는 관리자가 첫 실행을 위해 브라우저를 구성할 수 있도록 이전의 "마스터 기본 설정"이라는 제한된 수의 초기 기본 설정을 지원하고 있습니다. 아래 지원되는 설정 목록을 참조하세요.  

배포 시 초기 기본 설정은 관리되는 장치에서 기본 브라우저 설정 역할을 합니다. 이러한 설정은 관리자가 기본 설정으로 사용하는 설정이지만 사용자가 변경할 수 있지만 Active Directory® 도메인에 가입되지 않은 일부 장치에서는 사용할 수 없는 설정입니다.

초기 기본 설정의 몇 가지 예로는 기본 홈페이지 또는 특정 URL이 있는 탭의 초기 구성이 있습니다.

기본 설정은 initial_preferences 한 번만 복사하며 구성 후 이 파일에 대한 변경은 적용되지 않습니다. 설정이 Microsoft Edge 관리되고 [](/deployedge/microsoft-edge-policies) initial_preferences 파일에 구성된 경우 정책이 항상 우선합니다.

다음은 현재 해당 사용자에 의해 지원되는 기본 설정 Microsoft Edge.

| 기본 설정 범주 | 설정 |
| - | - |
| Bookmark_bar | show_apps_shortcut<br>show_managed_bookmarks<br>show_on_all_tabs |
| Bookmarks | editing_enabled |
| 브라우저/clear_data | browsing_history<br>browsing_history_basic"<br>cache<br>cache_basic<br>쿠키<br>download_history<br>form_data<br>passwords |
| 기록 | browsing_history<br>cache<br>쿠키<br>download_history<br>form_data<br>hosted_apps_data<br>passwords<br>site_settings |
| Browser | first_run_tabs<br>dark_theme<br>show_toolbar_bookmarks_button<br>show_toolbar_collections_butto<br>show_toolbar_downloads_button<br>show_home_button<br>show_prompt_before_closing_tabs<br>show_toolbar_history_button |
| default_search_provider | [default_search_provider] 사용 |
| 전체 화면 | 허용 |
| 홈 페이지 | Homepage_url |
| homepage_is_newtabpage | homepage_is_newtabpage |
| 세션 | restore_on_startup<br>startup_urls |
| Extensions | 확장 : 설정 |

## <a name="1-download-an-example-initial_preferences-file"></a>1: 파일 예제 initial_preferences 다운로드

시작하려면 이 initial_preferences 방문 페이지를 Microsoft Edge Enterprise 파일 형식의 [](https://www.microsoft.com/edge/business/download) **** 예제를 다운로드하고 아래 단계를 따릅니다. **

## <a name="2-customize-and-validate-the-initial_preferences-file"></a>2: 파일 사용자 지정 initial_preferences 유효성 검사

다운로드한 initial_preferences 파일에서 기본 ** 설정 설정을 사용자 지정하고 변경 내용의 유효성을 검사하여 JSON 코드에 오류가 없는지 확인합니다. 오류가 발견되는 경우 initial_preferences 구문과 구조를 확인하고 ** 수정한 후 다시 유효성을 검사합니다. 에서 JSON, 온라인 [JSON 도구](https://jsonformatter.org/) 또는 JSON 편집의 유효성을 검사하는 몇 가지 [Visual Studio Code.](https://code.visualstudio.com/docs/languages/json)

## <a name="3-deploy-preferences-to-users-computer"></a>3: 사용자 컴퓨터에 기본 설정 배포

브라우저가 ** initial_preferences 장치와 동시에 사용자 장치에 Microsoft Edge 파일을 배포하고 디바이스의 다음 위치에 파일을 배치합니다.

### <a name="windows-amd64-and-arm64"></a>Windows(AMD64 및 ARM64)

| 채널 | 위치 |
| - | - |
| 안정 | `"C:\Program Files (x86)\Microsoft\Edge\Application"` |
| Beta | `"C:\Program Files (x86)\Microsoft\Edge Beta\Application"` |
|Canary | `"%LOCALAPPDATA%\Microsoft\Edge SxS\Application"` |
| Dev | `"C:\Program Files (x86)\Microsoft\Edge Dev\Application"` |

**참고:** *initial_preferences* 파일을 사용자 컴퓨터의 msedge.exe 폴더와 동일한 폴더에 Windows 합니다.  

### <a name="macos"></a>macOS

| 채널 | 위치 |
| - | - |
| 안정 | `"~/Library/Application Support/Microsoft Edge/Microsoft Edge Initial Preferences"` |
| Beta | `“~/Library/Application Support/Microsoft Edge Beta/Microsoft Edge Initial Preferences"` |
| Canary | `“~/Library/Application Support/Microsoft Edge Canary/Microsoft Edge Initial Preferences"` |
| Dev | `"~/Library/Application Support/Microsoft Edge Dev/Microsoft Edge Initial Preferences"` |

## <a name="important-notes-msi--pkg-deployment-and-initial_preferences-interaction"></a>중요 참고 사항: MSI/Pkg 배포 *및* initial_preferences 상호 작용

초기 기본 설정은 최종 사용자가 브라우저를 initial_preferences 배포할 때만 적용됩니다.  

## <a name="see-also"></a>참고 항목

- [예제 *initial_prefrences* 파일](https://www.microsoft.com/edge/business/download)
