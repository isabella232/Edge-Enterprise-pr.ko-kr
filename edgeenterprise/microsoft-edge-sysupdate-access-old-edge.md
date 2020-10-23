---
title: 이전 버전의 Microsoft Edge에 액세스
ms.author: jtkim
author: dan-wesley
manager: srugh
ms.date: 08/17/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge의 레거시 버전에 액세스하는 방법을 알아보세요.
ms.openlocfilehash: e4733d020f3a681ded50e5a087fe086d39362201
ms.sourcegitcommit: f7f7eb69d2298b0f9779a9fd28e3c4e297ef2e05
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125520"
---
# 새 버전의 Microsoft Edge를 설치한 후 레거시 Microsoft Edge 액세스

새 버전의 Microsoft Edge를 설치한 후 레거시 Microsoft Edge 액세스하는 방법을 알아보세요.

> [!NOTE]
> 이 문서는 Microsoft Edge [안정 채널](microsoft-edge-channels.md)에 적용됩니다.

대부분의 조직에서는 Microsoft Edge 레거시를 새 버전으로 대체하려고 하지만, 사용자가 두 버전 모두에 대한 액세스를 필요로 하는 경우가 있습니다. 예를 들어 다음과 같은 가치를 제공해야 합니다.

- Microsoft Edge 중 하나 또는 두 가지 버전을 모두 사용하는 사용자와 상호 작용하는 고객 지원 및 지원 담당자
- 두 가지 버전의 Microsoft Edge 중 하나 또는 모두를 사용하는 고객을 지원하는 개발자

> [!IMPORTANT]
> 프로덕션에서 Microsoft Edge 레거시를 최신 버전의 Microsoft Edge와 함께 실행하지 않는 것이 좋습니다. 이 구성은 두 브라우저 버전 모두에 대한 테스트가 필요한 경우에만 사용해야 합니다.
>
> Microsoft Edge 레거시 데스크톱 앱은 새 Microsoft Edge를 위해 2021년 3월 9일에 지원이 종료됩니다. 이는 Microsoft Edge 레거시가 해당 날짜 이후에는 보안 업데이트를 받지 않음을 의미합니다. 이 변경 내용은 Microsoft Edge 레거시 데스크톱 앱에서 실행하는 모든 환경에 적용됩니다. [자세한 내용을 알아보세요](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-365-apps-say-farewell-to-internet-explorer-11-and/ba-p/1591666).

## 시작하기 전에
> [!NOTE]
> Windows 10 버전 20H2에서 시작하는 Microsoft Edge 레거시는 더 이상 포함되지 않습니다. 이 버전의 Windows 10 부터는 side-by-side 환경이 지원 되지 않습니다.

이 문서에 나와 있는 절차는 최신 보안 업데이트로 업데이트된 시스템에 적용됩니다. Microsoft Edge의 새 버전이 설치되면 이전 버전(레거시 Microsoft Edge)이 숨겨집니다. 기본적으로, 사용자가 이전 버전을 실행하려고 시도할 때마다 새로 설치된 Microsoft Edge 버전으로 리디렉션됩니다. 이 문서에서는 Microsoft Edge를 설치한 후에 Microsoft Edge 레거시를 계속 사용할 수 있는 방법에 대해 설명합니다.

## 빠른 시작: Microsoft Edge 베타 채널과 Microsoft Edge 레거시를 사용하는 함께 사용 경험

이 문서의 자세한 지침을 사용하기 전에 다음 두 단계를 고려하여 사용자가 Microsoft Edge 레거시와 Microsoft Edge [베타 채널](microsoft-edge-channels.md)을 나란히 실행할 수 있도록 합니다.

1. [Windows 업데이트](https://support.microsoft.com/help/12373/windows-update-faq)에서 Microsoft Edge 안정 채널이 자동으로 설치되지 않도록 합니다.

   > [!TIP]
   > [차단 도구 키트](microsoft-edge-blocker-toolkit.md)를 사용하여 Microsoft Edge 자동 배달을 비활성화합니다.

2. 새 버전의 Microsoft Edge의 [베타 채널](https://www.microsoft.com/edge/business/download) 을 설치합니다.

   > [!NOTE]
   > 레지스트리 키 설정에 대한 자세한 내용은 [추가 정보](#additional-information)를 참조하세요.

이 함께 사용 솔루션은 덜 복잡하며 이 문서에서 설명하는 세부 솔루션보다 관리를 덜 필요로 합니다. 그러나 이 해결 방법은 안정된 채널이 아니라 베타 채널을 실행하고 있다는 의미입니다.

## Microsoft Edge 안정 채널과 Microsoft Edge 레거시를 사용하는 함께 사용 경험

시스템 수준에서 다음 버전의 Microsoft Edge 안정 채널을 설치하면 현재 버전(Microsoft Edge 레거시)이 숨겨집니다. 사용자가 두 버전의 Microsoft Edge를 모두 나란히 볼 수 있도록 하려면 **Microsoft Edge 함께 사용 브라우저 환경 허용** 그룹 정책을 **사용**으로 설정하여 이 환경을 사용하도록 설정합니다.

이 그룹 정책에 대한 설명은 [여기](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#allowsxs)에 나와 있습니다.

### 함께 사용 브라우저 환경 정책을 설정하려면 다음을 수행합니다.

1. [비즈니스용 Microsoft Edge](https://www.microsoft.com/edge/business/download)에서 정책 정의를 설치합니다.

   - 사용할 채널/빌드 및 플랫폼을 선택한 다음 정책 파일 가져오기를 클릭합니다.
   - 압축 파일의 압축을 풉니다.
   - msedge.admx 및 msedgeupdate.admx를 `C:\Windows\PolicyDefinitions` 디렉터리로 복사합니다.
   - msedge.adml 및 msedgeupdate.adml(해당 언어/로케일 디렉터리부터)을 `C:\Windows\PolicyDefinitions\[APPROPRIATE LANGUAGE/LOCALE]` 디렉터리로 복사합니다.

2. 그룹 정책 편집기(gpedit.msc)를 엽니다.
3. **컴퓨터 구성**에서 *관리 템플릿 > Microsoft Edge 업데이트 > 애플리케이션*으로 이동합니다.

    > [!NOTE]
    > *Microsoft Edge 업데이트* 폴더가 표시되지 않으면 1단계가 올바르게 완료되었는지 확인합니다.

4. **애플리케이션** 아래에서 "Microsoft Edge 나란히 브라우저 환경 허용"을 두 번 클릭합니다. 다음 단계를 계속하기 전에 [모범 사례 지침](#best-practice-guidance)을 참조하세요.

    > [!NOTE]
    > 기본적으로 이 그룹 정책은 "구성되지 않음"으로 설정되어 있으며, 이는 새 버전의 Microsoft Edge가 설치되었을 때 레거시 Microsoft Edge를 숨기는 것입니다.

5. **사용**을 선택한 후 **확인**을 클릭합니다.  

이 정책을 설정하면 다음 레지스트리 키가 '00000001'으로 설정됩니다.

- 키: `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate`
- 값 이름: `Allowsxs`
- 값 유형: `'REG_DWORD'`

#### 모범 사례 지침

최상의 환경을 위해서는 새 버전의 Microsoft Edge를 사용자의 디바이스에 배포하기 전에 **Microsoft Edge 나란히 브라우저 환경 허용**을 사용하도록 설정해야 합니다.

Microsoft Edge 배포 후 그룹 정책을 사용하도록 설정한 경우 다음과 같은 부작용과 필수 작업이 있습니다.

1. 새 버전의 Microsoft Edge에 대한 설치 프로그램이 다시 실행될 때까지 **Microsoft Edge 나란히 브라우저 환경 허용**이 적용되지 않습니다.

   > [!NOTE]
   > 설치 프로그램은 새 버전의 Microsoft Edge가 업데이트될 때 직접 또는 자동으로 실행될 수 있습니다.

2. 새 버전의 Microsoft Edge를 배포할 때 고정이 마이그레이션되므로 레거시 Microsoft Edge를 시작 또는 작업 표시줄에 다시 고정해야 합니다.
3. 레거시 Microsoft Edge에 대해 시작 또는 작업 표시줄에 고정되었던 사이트는 새 버전의 Microsoft Edge로 마이그레이션됩니다.

## 추가 정보

시스템이 완전히 업데이트되고 다음 버전의 Microsoft Edge의 안정 채널이 설치되면 다음 레지스트리 키와 값이 설정됩니다.

- 키: `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\EdgeUpdate\ClientState\{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}`
- 키 값: `BrowserReplacement`

  > [!IMPORTANT]
  > 이 키는 Microsoft Edge 안정 채널이 업데이트될 때마다 덮어써집니다. 사용자가 두 버전의 Microsoft Edge에 모두 액세스할 수 있도록 이 키를 삭제하지 않는 것이 좋습니다.

## 참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge를 지원하기 위한 Windows 업데이트](microsoft-edge-sysupdate-windows-updates.md)
