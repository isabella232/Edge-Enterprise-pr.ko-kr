---
title: .plist를 사용하여 macOS용 Microsoft Edge 구성
ms.author: brianalt
author: kelleyvice-msft
manager: laurawi
ms.date: 02/14/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: .plist를 사용하여 macOS에서 Microsoft Edge 정책 설정 구성
ms.openlocfilehash: 84469a4f84deeee0e47b6d8899426fa36cf345aa
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980582"
---
# .plist를 사용하여 macOS에서 Microsoft Edge 정책 설정 구성

이 문서에서는 속성 목록(.plist) 파일을 사용하여 macOS에서 Microsoft Edge를 구성하는 방법을 설명합니다. 이 파일을 만든 다음 Microsoft Intune에 배포하는 방법을 알아봅니다.

자세한 내용은 [속성 목록 파일 정보](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html)(Apple의 웹 사이트) 및 [사용자 지정 페이로드 설정](https://support.apple.com/guide/mdm/custom-mdm9abbdbe7/1/web/1)을 참조하세요.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.

## macOS에서 Microsoft Edge 설정 구성

첫 번째 단계에서는 제출을 만듭니다. 임의의 텍스트 편집기를 사용하여 plist 파일을 만들거나 [터미널을 사용하여 구성 프로필을 만들](#create-a-configuration-profile-using-terminal) 수 있습니다. 하지만 사용자 대신 XML 코드의 서식을 지정하는 도구를 사용하여 plist 파일을 더 쉽게 만들고 편집할 수 있습니다. *Xcode*는 다음 위치 중 하나에서 얻을 수 있는 무료 통합 개발 환경입니다.

- [Apple 개발자 웹 사이트](https://developer.apple.com/xcode/)
- [Mac App Store](https://apps.apple.com/app/xcode/id497799835?mt=12)

지원되는 정책 및 기본 설정 키 이름의 목록은 [Microsoft Edge 브라우저 정책 참조](microsoft-edge-policies.md)를 참조하세요. [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)에서 다운로드할 수 있는 정책 템플릿 파일에는 **예제** 폴더에 plist 예제(*itadminexample.plist*)가 있습니다. 이 예제 파일에는 정책 설정을 정의하기 위해 사용자 지정할 수 있는 모든 지원되는 데이터 형식이 포함되어 있습니다. 

plist의 콘텐츠를 만든 후 다음 단계는 Microsoft Edge 기본 설정 도메인 *com.microsoft.Edge*를 사용하여 이름을 지정하는 것입니다. 이름은 대소문자를 구분하며, 모든 Microsoft Edge 채널에 적용되기 때문에 대상으로 하는 채널을 포함하지 않아야 합니다. plist 파일 이름은 **_com.microsoft.Edge.plist_** 여야 합니다. 

> [!IMPORTANT]
> 빌드 78.0.249.2부터 macOS의 모든 Microsoft Edge 채널이 **com.microsoft.Edge** 기본 설정 도메인에서 읽습니다. 모든 이전 릴리스는 개발 채널용 **com.microsoft.Edge.Dev**와 같은 채널별 도메인에서 읽습니다.

마지막 단계는 Microsoft Intune과 같은 선호하는 MDM 공급자를 사용하여 사용자의 Mac 장치에 plist를 배포하는 것입니다. 자세한 지침은 [plist 배포](#deploy-your-plist)를 참조하세요.

### 터미널을 사용하여 구성 프로필 만들기

1. 터미널에서 다음 명령을 사용하여 데스크톱에 Microsoft Edge에 대한 plist를 기본 설정으로 만듭니다.

   ```cmd
   /usr/bin/defaults write ~/Desktop/com.microsoft.Edge.plist RestoreOnStartup -int 1
   ```

2. plist를 바이너리에서 일반 텍스트 형식으로 변환:

   ```cmd
   /usr/bin/plutil -convert xml1 ~/Desktop/com.microsoft.Edge.plist
   ```
파일을 변환한 후에는 정책 데이터가 올바르고 구성 프로필에 원하는 설정이 포함되어 있는지 확인합니다.

> [!NOTE]
> 키 값 쌍만 plist 또는 xml 파일의 콘텐츠에 있어야 합니다. 파일을 Intune에 업로드하기 전에 \<plist> 및 \<dict> 값과 xml 헤더를 파일에서 모두 제거하세요. 파일에는 키 값 쌍만 포함되어야 합니다.

## plist 배포

Microsoft Intune에는 macOS 플랫폼을 대상으로 하는 새 장치 구성 프로필을 만들고 *기본 설정 파일* 프로필 유형을 선택합니다. 기본 도메인 이름으로 **com.microsoft.Edge**를 대상으로 하고 plist를 업로드합니다. 자세한 내용은 [Microsoft Intune을 사용하여 macOS 장치에 속성 목록 파일 추가](https://docs.microsoft.com/intune/configuration/preference-file-settings-macos)를 참조하세요.

Jamf의 경우 .plist 파일을 *사용자 지정 설정* 페이로드로 업로드합니다.

## 질문과 대답

### 마스터 기본 설정을 사용하도록 Microsoft Edge를 구성할 수 있나요?

예, 마스터 기본 설정 파일을 사용하도록 Microsoft Edge를 구성할 수 있습니다.

마스터 기본 설정 파일을 사용하면 Microsoft Edge가 배포될 때 브라우저 사용자 프로필에 대한 기본 설정을 구성할 수 있습니다. 또한 마스터 기본 설정 파일을 사용하여 장치 관리 시스템에서 관리하지 않는 컴퓨터에서 설정을 적용할 수 있습니다. 이러한 설정은 사용자가 브라우저를 처음 실행할 때 사용자 프로필에 적용됩니다. 사용자가 브라우저를 실행한 후에는 마스터 기본 설정 파일의 변경 내용이 적용되지 않습니다. 사용자는 브라우저에서 마스터 기본 설정에서 설정을 변경할 수 있습니다. 설정을 필수로 만들거나 브라우저를 처음 실행한 후 설정을 변경하려면 정책을 사용해야 합니다.

마스터 기본 설정 파일을 사용하면 다른 Chromium 기반 브라우저와 공유되는 항목과 Microsoft Edge에 고유한 항목을 포함하여 다양한 설정 및 기본 설정을 사용자 지정할 수 있습니다.  마스터 기본 설정 파일을 사용하여 정책 관련 기본 설정을 구성할 수 있습니다. 정책이 설정되어 있고 해당 마스터 기본 설정 집합이 있는 경우 정책 설정이 우선합니다.

> [!IMPORTANT]
> 사용 가능한 기본 설정 중 일부는 Microsoft Edge 용어 및 명명 규칙과 일치하지 않을 수 있습니다.  이후 릴리스에서 이러한 기본 설정이 예상대로 계속 작동한다는 보장은 없습니다. 이후 버전에서 기본 설정이 변경되거나 무시될 수 있습니다.

마스터 기본 설정 파일은 JSON 태그를 사용하여 서식 지정된 텍스트 파일입니다. 이 파일은 msedge.exe 실행 파일과 동일한 디렉터리에 추가해야 합니다. macOS에서의 시스템 수준 엔터프라이즈 배포인 경우 이 폴더는 일반적으로 “*~/Library/Application Support/Microsoft/Microsoft Edge Master Preferences*" 또는 "*/Library/Application Support/Microsoft/Microsoft Edge Master Preferences*”입니다.

## 기타 참조

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [Jamf를 사용한 macOS용 구성](configure-microsoft-edge-on-mac-jamf.md)
- [Windows용 구성](configure-microsoft-edge.md)
- [Intune을 사용한 Windows용 구성](configure-edge-with-intune.md)
