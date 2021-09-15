---
title: Windows 및 macOS에서 Microsoft Edge를 기본 브라우저로 설정
ms.author: brianalt
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge를 기본 브라우저로 설정하는 방법을 알아봅니다.
ms.openlocfilehash: 191d7835a0c4aacfc2fde409c57622ff5a351926
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "11980049"
---
# <a name="set-microsoft-edge-as-the-default-browser"></a>Microsoft Edge를 기본 브라우저로 설정

이 문서에서는 Windows 및 macOS에서 Microsoft Edge를 기본 브라우저로 설정하는 방법에 대해 설명합니다.

> [!NOTE]
> 이 문서는 Windows 8 및 Windows 10에서 Microsoft Edge 버전 77 이상에 적용됩니다. Windows 7 및 macOS의 경우 [Microsoft Edge를 기본 브라우저로 설정](./microsoft-edge-policies.md#defaultbrowsersettingenabled) 정책을 참조하세요.

## <a name="introduction"></a>소개

**기본 연결 구성 파일 설정** 그룹 정책 또는 [DefaultAssociationsConfiguration](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration) 모바일 디바이스 관리 설정을 사용하여 Microsoft Edge를 조직의 기본 브라우저로 설정할 수 있습니다.

Microsoft Edge 안정을 html 파일, http/https 링크 및 PDF 파일에 대한 기본 브라우저로 설정하려면 다음 애플리케이션 연결 파일 예제를 사용합니다.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<DefaultAssociations> 
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier=".html"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier=".htm"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier="http"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier="https"/>  
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgePDF" Identifier=".pdf"/>
</DefaultAssociations>
```

> [!NOTE]
> Microsoft Edge Beta를 기본 브라우저로 설정하려면 **ApplicationName**을 "Microsoft Edge Beta"로 설정하고 **ProgId**를 "MSEdgeBHTML"로 설정합니다. Microsoft Edge Dev를 기본 브라우저로 설정하려면 **ApplicationName**을 "Microsoft Edge Dev"로 설정하고 **ProgId**를 "MSEdgeDHTML"로 설정합니다.


> [!NOTE]
> 대상 장치에 Microsoft Edge가 설치되어 있지 않으면 기본 파일 연결이 적용되지 않습니다. 이 시나리오에서는 사용자가 링크 또는 htm/html 파일을 열 때 기본 응용 프로그램을 선택하라는 메시지가 표시됩니다.

## <a name="set-microsoft-edge-as-the-default-browser-on-domain-joined-devices"></a>도메인 가입 장치에서 Microsoft Edge를 기본 브라우저로 설정

**기본 연결 구성 파일 설정** 그룹 정책을 구성하여 도메인 가입 장치에서 Microsoft Edge를 기본 브라우저로 설정할 수 있습니다. 이 그룹 정책을 켜면 기본 연결 구성 파일을 만들고 저장해야 합니다. 이 파일은 로컬로 또는 네트워크 공유 위치에 저장됩니다. 이 파일을 만드는 방법에 대한 자세한 내용은 [기본 응용 프로그램 연결 내보내기 또는 가져오기](/windows-hardware/manufacture/desktop/export-or-import-default-application-associations)를 참조하세요.

### <a name="to-configure-the-group-policy-for-a-default-file-type-and-protocol-associations-configuration-file"></a>기본 파일 형식 및 프로토콜 연결 구성 파일에 대한 그룹 정책을 구성하려면

1. 그룹 정책 편집기를 열고 **Computer Configuration\Administrative Templates\Windows Components\File Explorer**로 이동합니다.
2. **기본 연결 구성 파일**을 선택합니다.
3. **정책 설정**을 클릭한 다음 **사용**을 클릭합니다.
4. **옵션**에서 기본 연결 구성 파일의 위치를 입력합니다.
5. **확인**을 클릭하여 정책 설정을 저장합니다.

다음 스크린샷의 예제에서는 대상 장치에서 액세스할 수 있는 네트워크 공유에 있는 *appassoc.xml*이라는 연결 파일을 보여 줍니다.

   ![그룹 정책에서 파일 연결 사용](./media/edge-learnmore-make-edge-default-browser/edge-learnmore-app-associations.png)

   > [!NOTE]
   > 이 설정이 사용하도록 설정되고 사용자의 장치가 도메인에 가입되는 경우 다음 번에 사용자가 로그인하면 연결 구성 파일이 처리됩니다.

## <a name="set-microsoft-edge-as-the-default-browser-on-azure-active-directory-joined-devices"></a>Azure Active Directory 가입 디바이스에서 Microsoft Edge를 기본 브라우저로 설정

Azure Active Directory 가입 디바이스에서 Microsoft Edge를 기본 브라우저로 설정하려면 다음 애플리케이션 연결 파일을 예제로 사용하여 [DefaultAssociationsConfiguration](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration) 모바일 디바이스 관리 설정의 단계를 수행합니다.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<DefaultAssociations>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier=".html"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier=".htm"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier="http"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier="https"/>  
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgePDF" Identifier=".pdf"/>
</DefaultAssociations>
```

> [!NOTE]
> Microsoft Edge Beta를 기본 브라우저로 설정하려면 **ApplicationName**을 "Microsoft Edge Beta"로 설정하고 **ProgId**를 "MSEdgeBHTML"로 설정합니다. Microsoft Edge Dev를 기본 브라우저로 설정하려면 **ApplicationName**을 "Microsoft Edge Dev"로 설정하고 **ProgId**를 "MSEdgeDHTML"로 설정합니다.

## <a name="set-microsoft-edge-as-the-default-browser-on-macos"></a>macOS에서 Microsoft Edge를 기본 브라우저로 설정

프로그래밍 방식으로 macOS에서 기본 브라우저를 설정하려고 하면 최종 사용자에게 프롬프트가 나타납니다. 이 프롬프트는 AppleScript를 사용해야만 자동화 할 수 있는 macOS 보안 기능입니다.

이 제한으로 인해 macOS에서 Microsoft Edge를 기본 브라우저로 설정하는 두 가지 주요 방법이 있습니다. 첫 번째 옵션은 Microsoft Edge가 이미 기본 브라우저로 설정된 macOS 이미지로 장치를 플래시하는 것입니다. 다른 옵션은  [Microsoft Edge를 기본 브라우저로 설정](./microsoft-edge-policies.md#defaultbrowsersettingenabled)  정책을 사용하여 Microsoft Edge를 기본값으로 설정하라는 메시지를 표시하는 것입니다.

이러한 방법 중 하나만 사용하는 경우에도 사용자가 기본 브라우저를 변경할 수 있습니다. 보안상의 이유로 기본 브라우저 환경 설정을 프로그래밍 방식으로 차단할 수 없기 때문입니다. 이러한 이유로 Microsoft Edge를 기본 브라우저로 사용하여 이미지를 생성하더라도 **Microsoft Edge를 기본 브라우저로 설정 ** 정책을 배포하는 것이 좋습니다. 정책이 설정되고 다음에 Microsoft Edge를 열 때 사용자가 기본 브라우저를 Microsoft Edge에서 변경하면 기본 브라우저를 설정하라는 메시지가 표시됩니다.

## <a name="see-also"></a>참고 항목

- [Microsoft Edge 배포 계획](./deploy-edge-plan-deployment.md)
- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge를 기본 브라우저로 설정(Windows 7 및 macOS)](./microsoft-edge-policies.md#defaultbrowsersettingenabled)
- [Windows 10 – IT 전문가를 위한 파일 연결을 구성하는 방법](/archive/blogs/windowsinternals/windows-10-how-to-configure-file-associations-for-it-pros)
- [기본 애플리케이션 연결 내보내기 또는 가져오기](/windows-hardware/manufacture/desktop/export-or-import-default-application-associations)
  - [DISM 개요](/windows-hardware/manufacture/desktop/what-is-dism)
  - [DISM - 배포 이미지 서비스 및 관리](/windows-hardware/manufacture/desktop/dism---deployment-image-servicing-and-management-technical-reference-for-windows)