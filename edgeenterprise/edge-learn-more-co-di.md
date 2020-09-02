---
title: Microsoft Edge의 ClickOnce 및 DirectInvoke
ms.author: kele
author: dan-wesley
manager: srugh
ms.date: 04/30/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge의 ClickOnce 및 DirectInvoke에 대해 알아봅니다.
ms.openlocfilehash: 8290c34bd29ca72678e3fa68f74b689d0cf797e3
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980685"
---
# Microsoft Edge의 ClickOnce 및 DirectInvoke 기능 이해

ClickOnce 및 DirectInvoke는 파일 처리기를 사용하여 웹 사이트에서 파일을 다운로드할 수 있도록 IE 및 Microsoft Edge(버전 45 이하)에서 사용할 수 있는 기능입니다. 두 기능은 서로 다른 용도로 사용되지만 둘 다 웹 사이트에서 다운로드가 요청된 파일이 사용자 장치의 파일 처리기로 전달되도록 지정하는 데 사용할 수 있습니다. ClickOnce 요청은 Windows의 기본 파일 처리기를 통해 처리됩니다. DirectInvoke 요청은 파일을 호스트하는 웹 사이트에서 지정한 등록된 파일 처리기를 통해 처리됩니다.

이러한 기능에 대한 자세한 내용은 다음을 참조하세요.

- [ClickOnce](https://docs.microsoft.com/visualstudio/deployment/clickonce-security-and-deployment?view=vs-2019)
- [DirectInvoke]( https://technet.microsoft.com/learning/jj215788(v=vs.94).aspx)

> [!NOTE]
> 현재 Chromium은 ClickOnce 또는 DirectInvoke에 대한 기본 지원을 제공하지 않습니다.

## 개요: 필수 구성 요소 및 프로세스

ClickOnce 및 DirectInvoke가 설계대로 작동하고 파일 처리기가 성공적으로 요청되도록 하려면 ClickOnce 또는 DirectInvoke 지원으로 파일 처리기를 운영 체제에 등록해야 합니다. 이 등록은 일반적으로 원래 운영 체제가 설치되어 있거나, 설치된 새 프로그램이 업데이트를 위해 DirectInvoke 사용을 요청하는 경우에 발생합니다.

웹 사이트에서 ClickOnce 또는 DirectInvoke가 필요한 다운로드 요청을 수신하는 경우 다음 작업이 수행됩니다.

- 웹 사이트에서 브라우저가 지정한 파일 처리기를 사용하도록 요청합니다.
- 브라우저는 운영 체제 레지스트리를 검사하여 파일 처리기가 요청된 파일 형식에 대해 등록되어 있는지 확인합니다.
- 파일 처리기가 등록되면 브라우저는 파일 처리기를 호출하고 URL을 인수로 파일 처리기에 전달합니다.
- 파일 처리기는 URL을 처리하고 파일을 다운로드합니다.

  > [!NOTE]
  > URL은 파일의 원본뿐 아니라 파일에 액세스할 때 사용할 매개 변수를 결정하는 데도 사용됩니다.  예: 엔드포인트, 매니페스트 또는 메타데이터.

## 사용 사례

대표적인 사용 사례는 다음과 같습니다.

ClickOnce를 사용하여 사용자 개입을 최소화하며 간편하게 장치에 소프트웨어를 배포 및 업데이트할 수 있습니다. 사용자가 웹 페이지에서 링크를 클릭하여 Windows 애플리케이션을 설치하고 실행할 수 있습니다. 올바르게 구성된 경우 사용자가 설치 프로그램에 대한 구성을 설정하지 않고 ClickOnce 응용 프로그램이 프로그램을 설치할 수 있습니다. 예를 들면 파일 위치, 설치할 옵션 등입니다.

DirectInvoke 사용 사례는 DirectInvoke를 요청하는 웹 사이트의 의도에 따라 달라집니다. 예를 들어 Microsoft Word의 공동 작업 파일 편집 기능입니다. 링크를 클릭하여 동료와 함께 작업 중인 문서의 전체 복사본을 다운로드하는 대신 DirectInvoke를 사용하여 문서에서 변경된 부분을 다운로드할 수 있습니다. 이 전략을 사용하면 전송되는 데이터의 양이 줄어들고 문서를 여는 데 필요한 시간을 단축할 수 있습니다.  

## Microsoft Edge의 ClickOnce 및 DirectInvoke에 대한 현재 지원

ClickOnce 및 DirectInvoke에 대한 지원:

- DirectInvoke는 기본적으로 모든 Windows 사용자에 대해 지원되지만 ClickOnce는 모든 Windows 사용자에 대해 사용하지 않도록 설정되어 있습니다.

  > [!NOTE]
  > ClickOnce 지원이 필요한 사용자는 edge://flags/#edge-click-once로 이동하여 드롭다운 목록에서 **사용**을 선택하세요. 그런 다음 브라우저를 **다시 시작**해야 합니다.

- Windows 이외의 플랫폼에서는 ClickOnce 및 DirectInvoke가 지원되지 않습니다.
- ClickOnce는 특정 고급 사용자 그룹에서 사용되는 기업 중심 기능이고 일반용이 아니므로 기본적으로 ClickOnce는 사용하도록 설정되어 있지 않습니다.

## ClickOnce 및 DirectInvoke 파일 처리 보안

ClickOnce 및 DirectInvoke는 Microsoft Defender SmartScreen의 URL 평판 검사 서비스로 보호됩니다.

ClickOnce 또는 DirectInvoke 요청이 Microsoft Defender SmartScreen URL 평판 서비스에 의해 안전하지 않은 것으로 플래그가 지정된 경우 ClickOnce 또는 DirectInvoke를 사용하도록 설정된 사용자에게는 두 개의 팝업이 표시됩니다.

첫 번째 팝업은 사용자에게 파일을 열 것인지 묻는 메시지를 표시합니다. 이 팝업은 파일이 안전하지 않은 것으로 플래그가 지정되었는지 여부와 관계없이 표시됩니다. 사용자는 **이 파일을 안전하지 않은 것으로 보고**하거나, 요청을 **취소**하거나, **열기**를 클릭하여 계속 진행할 수 있습니다.

   ![파일 열기 프롬프트](./media/edge-learn-more-co-di/edge-clickonce-modal-1.png)

사용자가 안전하지 않은 것으로 플래그가 지정된 파일을 열려고 하는 경우 두 번째 팝업이 표시됩니다.  이 팝업은 파일이 안전하지 않은 것으로 플래그가 지정되었음을 사용자에게 경고하고 파일을 다운로드할지 묻는 메시지를 표시합니다.

두 번째 팝업은 다음과 같은 경우에만 표시됩니다.

- 파일이 ClickOnce 또는 DirectInvoke 파일
- ClickOnce 또는 DirectInvoke를 사용하도록 설정됨
- 파일이 안전하지 않은 것으로 플래그가 지정됨

 ![안전하지 않은 파일 열기 프롬프트](./media/edge-learn-more-co-di/edge-clickonce-modal-2.png)

> [!NOTE]
> ClickOnce 또는 DirectInvoke가 사용하지 않도록 설정된 경우 요청된 파일은 일반 다운로드로 취급되며 안전하지 않은 것으로 플래그가 지정된 경우 안전하지 않은 것으로 표시됩니다. 이는 다른 안전하지 않은 다운로드를 처리하는 방식과 일관됩니다.

## ClickOnce 및 DirectInvoke 정책

기업 사용자용 ClickOnce 및 DirectInvoke를 사용하거나 사용하지 않도록 설정하는 데 사용할 수 있는 그룹 정책이 2개 있습니다. 이러한 정책은 [ClickOnceEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#clickonceenabled) 및 [DirectInvokeEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#directinvokeenabled)입니다. 이 두 정책은 그룹 정책 편집기에서 "ClickOnce 프로토콜을 사용하여 파일을 열 수 있도록 허용" 및 "DirectInvoke 프로토콜을 사용하여 파일을 열 수 있도록 허용"으로 각각 표시되어 있습니다.

## ClickOnce 및 DirectInvoke 동작

다음 예제에서는 ClickOnce 및 DirectInvoke가 사용 또는 사용하지 않도록 설정된 경우의 파일 처리를 보여 줍니다.

### ClickOnce 사용

1. 사용자가 ClickOnce 지원을 요청하는 페이지에 대한 링크를 열면 다음 스크린샷과 같은 프롬프트가 표시됩니다.

   ![안전하지 않은 파일 열기 프롬프트](./media/edge-learn-more-co-di/edge-clickonce-enabled-1.png)

2. 사용자가 **열기**를 클릭하면 ClickOnce가 응용 프로그램을 시작하려고 시도합니다.

   ![ClickOnce에서 응용 프로그램을 시작하려고 시도](./media/edge-learn-more-co-di/edge-clickonce-enabled-launch-app.png)

3. 사용자가 **열기**를 클릭하면 사용자에게 응용 프로그램을 설치할지 묻는 팝업이 브라우저에 표시됩니다.

   ![파일 열기 프롬프트](./media/edge-learn-more-co-di/edge-clickonce-enabled-2.png)

   > [!NOTE]
   > ClickOnce 파일 처리기에 표시되는 인터페이스, 메시지 및 옵션은 액세스하는 파일의 유형 및 구성에 따라 달라집니다.

### ClickOnce 사용 안 함

1. 사용자가 ClickOnce 지원을 요청하는 페이지에 대한 링크를 열면 다운로드 트레이에 다음 스크린샷과 같은 메시지가 표시됩니다.

   ![파일 다운로드 프롬프트](./media/edge-learn-more-co-di/edge-clickonce-disabled-1.png)

### DirectInvoke 사용

1. 사용자가 DirectInvoke 지원을 요청하는 페이지에 대한 링크를 열면 다음 스크린샷과 같은 프롬프트가 표시됩니다.

   ![파일 열기 프롬프트](./media/edge-learn-more-co-di/edge-directinvoke-open-link-1.png)

2. 사용자가 **열기**를 클릭하면 요청된 파일 처리기가 열립니다. 이 예제에서는 Microsoft Word가 이전 스크린샷에 표시된 문서를 여는 데 사용됩니다.

   > [!NOTE]
   > DirectInvoke 파일 처리기에 표시되는 인터페이스, 메시지 및 옵션은 액세스하는 파일의 유형 및 구성에 따라 달라집니다.

### DirectInvoke 사용 안 함

1. 사용자가 DirectInvoke 지원을 요청하는 페이지에 대한 링크를 열면 DirectInvoke가 ClickOnce를 사용하지 않는 경우와 동일하게 동작합니다. 다운로드 트레이에 다음 스크린샷과 같은 메시지가 표시됩니다.

   ![파일 열기 프롬프트](./media/edge-learn-more-co-di/edge-directinvoke-open-link-2.png)

## 기타 참조

- [ClickOnce 보안 및 배포](https://go.microsoft.com/fwlink/?linkid=2099880)
- [Internet Explorer의 DirectInvoke](https://go.microsoft.com/fwlink/?linkid=2099871)
- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
