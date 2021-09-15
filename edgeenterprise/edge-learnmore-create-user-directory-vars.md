---
title: Microsoft Edge 사용자 데이터 디렉터리 변수 만들기
ms.author: brianalt
author: AndreaLBarr
manager: srugh
ms.date: 07/08/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge 사용자 데이터 디렉터리 변수를 만드는 방법을 알아봅니다.
ms.openlocfilehash: 2e85e8eebac4a636d90fd0b5da7520c9a86a2de0
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "11979874"
---
# <a name="create-microsoft-edge-user-data-directory-variables"></a>Microsoft Edge 사용자 데이터 디렉터리 변수 만들기

이 문서에서는 Microsoft Edge를 수정할 때 하드 코드된 경로를 사용하는 대신 데이터 디렉터리 변수를 사용하는 방법을 설명합니다.

>[!NOTE]
>이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.
## <a name="path-variables"></a>경로 변수

데이터 디렉터리 경로를 수정하기 위한 정책(예: [UserDataDir](microsoft-edge-policies.md#userdatadir) 또는 [DownloadDirectory](microsoft-edge-policies.md#downloaddirectory) 지원 변수 구성) 이러한 정책을 구성할 때 하드 코드된 경로 대신 변수를 사용할 수 있습니다. 예를 들어 프로필 데이터를 기본 위치 대신 Windows의 사용자 로컬 응용 프로그램 데이터 아래에 저장합니다. [UserDataDir](microsoft-edge-policies.md#userdatadir) 정책을 **${local_app_data}\Edge\Profile**로 설정합니다. 대부분의 Windows 10 설치에서 이는 *C:\Users\\&lt;Current-user&gt;\AppData\Local\Microsoft\Edge\Profile*로 확인됩니다.

>[!NOTE]
>현재 **프로필 경로**를 보려면 **버전 정보** 페이지를 엽니다("edge://version"을 입력). **프로필 경로**는 다음 형식을 따릅니다. *C:\Users\\&lt;Current-user&gt;\AppData\Local\Microsoft\Edge\User Data\Default*.

### <a name="guidance-for-using-path-variables"></a>경로 변수 사용 지침

경로에 변수를 사용하기 전에 다음 지침을 검토하세요.

- Microsoft Edge가 다양한 데이터를 저장하는 경로를 포함하는 모든 정책은 플랫폼마다 다릅니다. 이러한 정책 중 일부는 특정 플랫폼에서만 사용할 수 있지만 다른 정책은 모든 플랫폼에서 사용할 수 있습니다.
- 응용 프로그램이 경우마다 다른 위치에서 시작하여 발생하는 오류를 방지하려면 절대 경로를 설정해야 합니다.
- 모든 변수는 경로에서 한 번만 발생할 수 있습니다. 대부분의 경우 이들은 절대 경로로 확인되기 때문에 이것이 변수를 사용하는 유일한 방법입니다.
- 거의 모든 정책은 경로가 존재하지 않으면 경로를 만듭니다(기존 환경에서 가능할 경우).
- 일부 정책에 네트워크 위치를 사용하면 각 Microsoft Edge 버전/채널이 폴더 구조를 처리하는 방법의 차이 때문에 예기치 않은 결과가 발생할 수 있습니다.

### <a name="supported-path-variables"></a>지원되는 경로 변수

Microsoft Edge는 다음 경로 변수를 지원합니다.

#### <a name="all-platforms"></a>모든 플랫폼

| 변수 | 설명 |
| --- | --- |
| **${user_name}** | Microsoft Edge를 사용하는 사용자입니다. Microsoft Edge는 SUID(실행 시 소유자 사용자 ID 설정)를 따릅니다. 예: *audreysmall* |
| **${machine_name}** | 컴퓨터 이름입니다(도메인 이름이 포함될 수 있음). 예: *audreysmall* 또는 *audrey.ex.contoso.com* |

#### <a name="windows-only"></a>Windows만 해당

| 변수 | 설명 |
| --- | --- |
| **${documents}** | 현재 사용자의 문서 폴더입니다. 예: *C:\Users\Administrator\Documents* |
|**${local_app_data}** | 현재 사용자의 응용 프로그램 데이터입니다. 예: *C:\Users\Administrator\AppData\Local* |
|**${roaming_app_data}** | 현재 사용자의 로밍된 응용 프로그램 데이터입니다. 예: *C:\Users\Administrator\AppData\Roaming* |
| **${profile}** | 현재 사용자의 홈 폴더입니다. 예: *C:\Users\Administrator* |
| **${global_app_data}** | 시스템 수준 응용 프로그램 데이터 폴더입니다. 예: *C:\AppData* |
| **${program_files}** | 현재 프로세스의 프로그램 파일 폴더입니다. 이 폴더는 32비트 또는 64비트 프로세스인지에 따라 달라집니다. 확인 예: *C:\Program Files (x86)* |
| **${windows}** | Windows 폴더입니다. 예: *C:\Windows* |
| **${client_name}** | RDP 또는 Citrix 세션에 연결된 클라이언트 PC의 이름입니다. 로컬 세션에서 사용되는 경우 이 변수는 비어 있습니다. 경로에서 사용되는 경우 비어 있지 않은 것으로 보장된 항목을 접두사로 추가합니다. 예를 들어 *C:\edge_profiles\session_${client_name}* 은 *C:\edge_profiles\session_&lt;ForlocalSessions&gt;* 및 *C:\edge_profiles\session_&lt;SomePCname&gt;*(원격 세션의 경우)으로 확인됩니다. |
| **${session_name}** | 활성 세션의 이름입니다. 이 이름을 사용하여 단일 사용자 프로필을 사용하는 여러 개의 동시에 연결된 원격 세션을 구분할 수 있습니다. 예: 로컬 데스크톱 세션의 경우 *WinSta0* |

#### <a name="macos-only"></a>MacOS만 해당

| 변수 | 설명 |
| --- | --- |
| **${users}** | 사용자의 프로필이 저장된 폴더입니다. 예: */Users* |
| **${documents}** | 현재 사용자의 문서 폴더입니다. 예: */Users/audreysmall/Documents* |

## <a name="content-license"></a>콘텐츠 라이선스

>[!NOTE]
>이 페이지의 일부는 Chromium.org에서 생성 및 공유하고 [Creative Commons Attribution 4.0 국제 라이선스](http://creativecommons.org/licenses/by/4.0/)에 규정된 조건에 따라 사용되는 작업을 기반으로 합니다. 원래 페이지는 [여기](https://www.chromium.org/administrators/policy-list-3/user-data-directory-variables)에서 찾을 수 있습니다.
  
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br/>이 작업은 <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 국제 라이선스</a>에서 사용이 허가되었습니다.
## <a name="see-also"></a>참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
