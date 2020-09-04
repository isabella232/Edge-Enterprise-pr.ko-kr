---
title: 엔터프라이즈용 Microsoft Edge 롤백
ms.author: v-danwes
author: dan-wesley
manager: srugh
ms.date: 09/02/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge를 이전 버전으로 롤백하는 방법
ms.openlocfilehash: 9f659b0bcdd82f54a814c8ad4157521061cdfa7c
ms.sourcegitcommit: 827a47d641c7ddc1d89be5d5fc0615373dec18b0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993708"
---
# Microsoft Edge를 이전 버전으로 롤백하는 방법

이 문서에서는 롤백 기능을 사용하여 이전 버전의 Microsoft Edge로 롤백하는 방법에 대해 설명합니다.

>[!NOTE]
>이 문서는 Microsoft Edge 버전 86 이상에 적용됩니다.

## 롤백 소개

롤백을 사용하면 Microsoft Edge 브라우저 버전을 이전 버전으로 바꿀 수 있습니다. 이 기능은 Microsoft Edge를 배포하는 기업을 위한 안전망으로 설계되었습니다. Microsoft Edge에 발생하는 문제를 해결하는 방법을 제공합니다. 롤백의 이점은 이전 브라우저 버전으로 쉽고 빠르게 전환할 수 있다는 점입니다. 롤백을 수행하면 비즈니스 운영에 미치는 Microsoft Edge 문제의 잠재적인 영향을 줄일 수 있습니다.

## 시작하기 전에

롤백 기능이 Microsoft Edge 환경에 설치되는 방법을 이해하는 것이 중요합니다. 직접 MSI를 사용하거나 Microsoft Edge 업데이트와 그룹 정책을 사용하여 다른 두 가지 방법을 사용하여 롤백을 배포할 수 있습니다. 또한 보다 원활한 배포를 위해 다양한 그룹 정책을 사용하는 것이 좋습니다.

### 권장 사항

롤백 기능은 Microsoft Edge 브라우저 업데이트에서 발생할 수 있는 문제를 해결 하는 임시 수정 사항입니다. 최신 버전의 Microsoft Edge 브라우저를 설치하여 최신 보안 업데이트에서 제공하는 보호를 사용하는 것이 좋습니다. 이전 버전으로 롤백하면 알려진 보안 문제에 노출될 수 있습니다.

브라우저 버전을 일시적으로 롤백하려면 먼저 조직의 모든 사용자에 대해 동기화를 설정하는 것이 좋습니다. 동기화를 설정하지 않은 경우 영구적 검색 데이터 손실이 발생할 수 있습니다. 동기화에 대한 자세한 내용은 [Microsoft Edge 동기화](microsoft-edge-enterprise-sync.md)를 참조하세요.

> [!CAUTION]
> 필요한 경우에만 롤백을 사용하세요. 항상 데이터가 손실될 위험이 있습니다.

## MSI를 사용하여 수동으로 롤백 설정

MSI를 사용하여 수동으로 롤백하려면 다음 단계를 수행합니다.

1. Microsoft Edge 업데이트를 사용하지 않도록 설정합니다.

   > [!NOTE]
   > 최신 관리 템플릿을 설치하는 것이 좋습니다. 자세한 내용은 [Microsoft Edge 관리 템플릿 다운로드 및 설치](https://docs.microsoft.com/DeployEdge/configure-microsoft-edge#1-download-and-install-the-microsoft-edge-administrative-template)를 참조하세요.

   - 로컬 그룹 정책 편집기를 열고 *컴퓨터 구성>관리 템플릿>Microsoft Edge 업데이트>응용 프로그램>Microsoft Edge>* 로 이동합니다.
   - **업데이트 정책 재정의**을 선택한 다음 **사용**을 선택합니다.
   - **옵션**의 정책 드롭다운 목록에서 **업데이트 사용 안 함**을 선택합니다.

2. MSI를 다운로드합니다.

   - [여기](https://www.microsoft.com/edge/business/download)에서 롤백할 버전용 MSI를 다운로드합니다.
   - MSI를 바탕 화면에 저장합니다.

3. Rollback 명령을 실행합니다.

   - **관리자 권한으로 실행**을 사용하여 Windows 명령 프롬프트를 엽니다.
   - 다음 명령을 입력합니다. 여기서 *C:\Users\username\Desktop\test* 는 다운로드한 MSI 경로이고 파일 이름은 .msi 파일의 이름입니다.<br>
 `C:\Users\username\Desktop\test>msiexec /I FileName.msi /qn ALLOWDOWNGRADE=1`<br>
     > [!NOTE]
     > Msiexec에 대한 자세한 내용은 [msiexec](https://docs.microsoft.com/windows-server/administration/windows-commands/msiexec)을 참조하세요.
   - Microsoft Edge를 닫고 다시 열어 롤백이 제대로 작동했는지 확인합니다. **설정 및 추가**(ALT + F)에서 **설정**으로 이동하여 **Microsoft Edge 정보**를 선택합니다.

## Microsoft Edge 업데이트 및 그룹 정책을 사용하여 롤백 설정

다음 단계에 따라 Microsoft Edge 업데이트와 그룹 정책을 사용하여 롤백을 설정합니다.

1. 로컬 그룹 정책 편집기를 열고 *컴퓨터 구성>관리 템플릿>Microsoft Edge 업데이트>응용 프로그램>Microsoft Edge>* 로 이동합니다.
2. **대상 버전으로 롤백**을 선택하고 **사용**을 선택합니다.
3. **대상 버전 재정의**를 선택하고 롤백할 브라우저 버전을 선택합니다.
4. **업데이트 정책 재정의**을 선택한 다음 **사용**을 선택합니다. **옵션**의 정책 드롭다운 목록에서 다음 옵션 중 하나를 선택합니다(**업데이트 사용 안 함** 예외).

   - 항상 업데이트 허용
   - 자동 업데이트만

     > [!NOTE]
     > 그룹 정책 업데이트를 강제적으로 실행하려면 `dsregcmd /status`Windows 관리자 명령 프롬프트(관리자 권한으로 실행)에 입력합니다.

5. **확인**을 클릭하여 정책 설정을 저장합니다. 다음에 Microsoft Edge 업데이트에서 업데이트를 확인할 때 롤백이 수행됩니다. 업데이트를 바로 수행하려면 Microsoft Edge 업데이트 폴링 간격을 변경하거나 MSI를 사용하여 롤백을 설정해야 합니다.

### 일반적인 롤백 오류

다음 오류로 인해 롤백이 수행되지 않습니다.

- 입력이 지원되지 않는 대상 버전입니다.
- 입력이 존재하지 않는 대상 버전입니다.
- 입력 서식이 잘못 지정되었습니다.

### 권장되는 그룹 정책

다음 그룹 정책 및 설정은 롤백하는 데 사용하는 것이 매우 좋습니다.

#### 동기화 그룹 정책

- ForceSync. ForceSync를 사용으로 설정합니다. 이 정책은 모든 Azure AD(Azure Active Directory) 사용자에 대해 동기화를 강제로 설정합니다. 이 정책은 Microsoft Edge 버전 86 이상에만 적용됩니다.
- *동기화 정책에서 제외되는 유형의 목록 구성*을 사용하여 관리자는 사용자가 동기화할 수 있는 데이터를 제어할 수 있습니다.

#### 브라우저 다시 시작 그룹 정책

롤백을 사용하도록 설정한 사용자가 다시 시작하는 것이 좋습니다.

- *사용자에게 보류 중인 업데이트에 대해 브라우저의 재시작을 권장하거나 필요함을 알림*을 사용하도록 설정합니다. 옵션에서 **필수**를 선택합니다.
- *업데이트 알림 기간 설정*을 사용하도록 설정한 다음 원하는 시간(밀리초)을 설정합니다.

## 스냅샷

스냅샷은 사용자 데이터 폴더의 버전 스탬프 사본입니다. 버전 업그레이드 중에는 이전 버전의 스냅샷이 만들어져 스냅샷 폴더에 저장됩니다. 롤백이 발생하면 버전이 일치하는 스냅샷이 새 사용자 데이터 폴더에 복사되고 스냅샷 폴더에서 삭제됩니다. 다운그레이드할 때 버전과 일치하는 스냅샷을 사용할 수 없는 경우 롤백은 동기화를 사용하여 사용자 데이터를 새 Microsoft Edge 버전에 채웁니다.

[UserDataSnapshotRetentionLimit] 그룹 정책을 사용하여 지정 된 시간에 보존할 수 있는 스냅샷 수 제한을 설정할 수 있습니다. 기본적으로 세 개의 스냅샷이 유지 됩니다. 0-5개의 스냅샷을 유지하도록 이 정책을 구성할 수 있습니다.

## 질문과 대답

### 수동 MSI 롤백

#### 어떤 일반적인 MSI 오류가 발생할 수 있나요?

1. 업데이트 그룹 정책 설치를 사용하지 않도록 설정하면 롤백이 일어나지 않습니다.

   - 롤백을 사용하려면 설치가 **사용**으로 설정되어 있는지 확인합니다. 이 정책을 사용하지 않도록 설정하면 Microsoft Edge 채널을 설치할 수 없습니다. 자세한 내용은 [설치](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#install)를 참조하세요.

2. Enlightenment 업데이트가 없는 경우, *Microsoft Edge Side by Side 브라우저 환경 허용*을 사용하도록 설정하지 않으면 Microsoft Edge 설치가 차단됩니다.

   - Windows 버전 1903 및 1909의 경우: 마지막 업데이트가 2019년 10월 이전인 경우 이 문제가 발생할 수 있습니다.
   - Windows 버전 1709, 1803 및 1809의 경우: 마지막 업데이트가 2019년 11월 이전인 경우 이 문제가 발생할 수 있습니다.<br>
자세한 내용은 [Microsoft Edge의 다음 버전을 지원하려면 Windows 업데이트](https://docs.microsoft.com/deployedge/microsoft-edge-sysupdate-windows-updates)를 참조하세요.

#### 명령 프롬프트를 사용한 후 다음 오류 메시지가 표시되었고 롤백이 수행되지 않았습니다. 문제가 무엇인가요?

![롤백 상태 메시지](./media/edge-learnmore-rollback/edge-rollback-cmd-flag-error.png)

*ALLOWDOWNGRADE=1*이 실행되지 않았습니다.

### Microsoft Edge 업데이트 및 그룹 정책 롤백

#### *대상 버전으로 롤백*을 설정하고 *업데이트 정책 재정의*를 사용하도록 설정하고 *대상 버전 재정의*에 대해 원하는 브라우저 버전을 입력했지만, 브라우저 버전이 예상했던 버전이 아니었습니다. 문제가 무엇인가요?

다음은 롤백을 방해하는 몇 가지 일반적인 오류입니다.

- 대상 버전으로 롤백이 설정되지 않은 경우 롤백이 실행되지 않습니다.
- 대상 버전 재정의 설정에 다음 문제 중 하나가 있습니다.

  - 대상 버전 재정의가 지원되지 않는 대상 버전으로 설정되어 있습니다.
  - 대상 버전 재정의가 존재하지 않는 대상 버전으로 설정되어 있습니다.
  - 대상 버전 재정의 입력의 서식이 잘못 지정되었습니다.

- 업데이트 정책 재정의가 "업데이트 사용 안 함"으로 설정된 경우, Microsoft Edge 업데이트에서 업데이트를 허용하지 않고 롤백이 실행되지 않습니다.

### 모든 그룹 정책을 올바르게 설정했지만 롤백이 실행되지 않습니다. 경우

Microsoft Edge 업데이트에서 아직 업데이트를 확인하지 않습니다. 기본적으로 자동 업데이트는 10시간마다 업데이트를 확인합니다. 자동 업데이트 확인 기간 재정의 그룹 정책으로 Microsoft Edge 업데이트의 폴링 간격을 변경하여 이 문제를 해결할 수 있습니다. 자세한 내용은 [AutoUpdateCheckPeriodMinutes](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#autoupdatecheckperiodminutes) 정책을 참조하세요.

### IT 관리자로서 롤백에 필요한 모든 단계를 올바르게 수행했습니다. 사용자 그룹의 일부만 롤백되었습니다. 다른 사용자가 아직 롤백되지 않은 이유는 무엇인가요?

그룹 정책 설정이 아직 모든 클라이언트에 동기화되지 않았습니다. 관리자가 그룹 정책을 설정할 때 클라이언트에서 이 설정을 즉시 받지는 않습니다. [원격 그룹 정책 강제 새로 고침](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/jj134201(v=ws.11))을 실행할 수 있습니다.


## 참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
