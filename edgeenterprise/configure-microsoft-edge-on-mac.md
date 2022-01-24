---
title: 속성 Microsoft Edge 사용하여 macOS용 설정을 구성합니다.
ms.author: brianalt
author: kelleyvice-msft
manager: laurawi
ms.date: 12/14/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge 배포할 수 있는 속성 목록을 사용하여 macOS에서 Microsoft Intune.
ms.openlocfilehash: 4cb3d635c8fc108a3b81ec17175ce0e3d8fa287a
ms.sourcegitcommit: e7f3098d8b7d91cae20b5778a71a87daababc312
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "12297704"
---
# <a name="configure-microsoft-edge-policy-settings-for-macos-using-a-property-list"></a>속성 Microsoft Edge 사용하여 macOS에 대한 정책 설정 구성

이 문서에서는 속성 목록(\.plist) Microsoft Edge 사용하여 macOS에서 구성하는 방법을 설명합니다. 이 파일을 만든 다음 Microsoft Intune에 배포하는 방법을 알아봅니다.

자세한 내용은 [속성 목록 파일 정보](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html)(Apple의 웹 사이트) 및 [사용자 지정 페이로드 설정](https://support.apple.com/guide/mdm/custom-mdm9abbdbe7/1/web/1)을 참조하세요.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.

## <a name="configure-microsoft-edge-policies-on-macos"></a>macOS에서 Microsoft Edge 설정 구성

첫 번째 단계에서는 제출을 만듭니다. 모든 텍스트 편집기로 plist 파일을 만들 수 있습니다. 또 다른 옵션은 터미널을 사용하여 구성 [프로필을 만드는 것입니다.](#create-a-configuration-profile-using-terminal) 그러나 XML 코드의 형식을 지정하는 도구로 plist 파일을 만들고 편집하는 것이 더 쉽습니다. *Xcode는* 다음 위치에서 사용할 수 있는 무료 통합 개발 환경입니다.

- [Apple 개발자 웹 사이트](https://developer.apple.com/xcode/)
- [Mac App Store](https://apps.apple.com/app/xcode/id497799835?mt=12)

지원되는 정책 및 기본 설정 키 이름의 목록은 [Microsoft Edge 브라우저 정책 참조](./microsoft-edge-policies.md)를 참조하세요. 정책 템플릿 파일에는 Microsoft Edge Enterprise 방문 페이지에서 다운로드할 수 있는 plist 예제(itadminexample.plist)가 예제 **폴더에** 있습니다. [](https://aka.ms/EdgeEnterprise)** 이 파일에는 정책 설정을 정의하기 위해 사용자 지정할 수 있는 지원되는 모든 데이터 형식이 포함되어 있습니다.

plist의 내용을 만든 후 기본 설정 도메인인 *"com.microsoft.Edge Microsoft Edge를*사용하여 plist의 이름을 지정합니다. 이 이름은 대/중/일어가 구분되어 있으며 모든 모든 채널에 적용되어 있기 때문에 대상으로 하는 채널을 포함하지 Microsoft Edge 않습니다. plist 파일 이름은 **_com.microsoft.Edge.plist_** 여야 합니다.

> [!IMPORTANT]
> 빌드 78.0.249.2부터 macOS의 모든 Microsoft Edge 채널이 **com.microsoft.Edge** 기본 설정 도메인에서 읽습니다. 모든 이전 릴리스는 개발 채널용 **com.microsoft.Edge.Dev**와 같은 채널별 도메인에서 읽습니다.

마지막 단계는 Microsoft Intune과 같은 선호하는 MDM 공급자를 사용하여 사용자의 Mac 장치에 plist를 배포하는 것입니다. 자세한 지침은 [plist 배포](#deploy-your-plist)를 참조하세요.

### <a name="create-a-configuration-profile-using-terminal"></a>터미널을 사용하여 구성 프로필 만들기

1. 터미널에서 다음 명령을 사용하여 데스크톱에 Microsoft Edge에 대한 plist를 기본 설정으로 만듭니다.

   ```cmd
   /usr/bin/defaults write ~/Desktop/com.microsoft.Edge.plist RestoreOnStartup -int 1
   ```

2. plist를 바이너리에서 일반 텍스트 형식으로 변환:

   ```cmd
   /usr/bin/plutil -convert xml1 ~/Desktop/com.microsoft.Edge.plist
   ```

파일을 변환한 후 정책 데이터가 올바른지 확인하고 설정을 포함하면 구성 프로필을 원하는 것입니다.

> [!NOTE]
> 키 값 쌍만 plist 또는 xml 파일의 콘텐츠에 있어야 합니다. 파일을 Intune에 업로드하기 전에 \<plist> 및 \<dict> 값과 xml 헤더를 파일에서 모두 제거하세요. 파일에는 키 값 쌍만 포함되어야 합니다.

## <a name="deploy-your-plist"></a>plist 배포

Microsoft Intune 사용하여 macOS 플랫폼을 대상으로 하는 새 장치 구성 프로필을 만들고 기본 설정 파일 *프로필* 유형을 선택합니다. 기본 도메인 이름으로 **com.microsoft.Edge**를 대상으로 하고 plist를 업로드합니다. 자세한 내용은 [add a property list file to macOS devices using Microsoft Intune.](/intune/configuration/preference-file-settings-macos)

Jamf의 경우 \.plist 파일을 사용자 지정 페이로드로 *설정* 업로드합니다.

## <a name="see-also"></a>참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [Jamf를 사용한 macOS용 구성](configure-microsoft-edge-on-mac-jamf.md)
- [Windows용 구성](configure-microsoft-edge.md)
- [Intune을 사용한 Windows용 구성](configure-edge-with-intune.md)