---
title: 그룹 정책을 사용하여 Microsoft Edge 확장 관리
ms.author: aspoddar
author: AndreaLBarr
manager: balajek
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 엔터프라이즈에서 그룹 정책을 사용하여 Microsoft Edge 확장 관리
ms.openlocfilehash: dad239a448ec1f0ebef60c7072bfaad5c3baed57
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641374"
---
# <a name="use-group-policies-to-manage-microsoft-edge-extensions"></a>그룹 정책을 사용하여 Microsoft Edge 확장 관리

이 문서에서는 그룹 정책을 사용하여 확장을 관리하는 옵션과 단계를 설명합니다. 옵션은 귀하가 이미 사용자들을 위해 Microsoft Edge를 관리하는 것으로 가정합니다. 사용자가 Microsoft Edge를 관리할 수 있도록 아직 설정하지 않은 경우 아래 링크를 클릭하여 지금 관리하세요.

- [엔터프라이즈에서 Microsoft Edge 확장 관리](/deployedge/microsoft-edge-manage-extensions)

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.

## <a name="block-extensions-based-on-their-permissions"></a>사용 권한에 따라 확장 차단

[ExtensionSettings](/deployedge/microsoft-edge-policies#extensionsettings) 정책을 사용하여 권한에 따라 사용자가 설치할 수 있는 확장을 제어할 수 있습니다. 설치된 확장에서 차단된 사용 권한이 필요한 경우 실행되지 않습니다. 확장은 제거되지 않고 사용하지 않도록 설정됩니다.

> [!NOTE]
> 차단된 권한 설정은 확장 설정 정책 내에서만 설정할 수 있습니다.  

확장을 차단하기 위한 지침으로 다음 단계를 사용합니다.

1. 그룹 정책 관리 편집기를 열고 **관리 템플릿 > Microsoft Edge > 확장**으로 이동하고 **확장 관리 설정 구성**을 선택합니다.
2. 정책을 실행한 다음 압축되는 JSON 문자열을 사용하여 허용하거나 차단할 사용 권한을 입력하세요. 다음 스크린샷은 권한 "usb"를 사용하는 확장을 차단하는 방법을 보여줍니다.

    :::image type="content" source="media/microsoft-edge-manage-extensions-policies/manage-extensions-gp-block-1.png" alt-text="확장을 차단하도록 그룹 정책을 구성합니다.":::

다음 예에서는 사용 권한 "usb"와 해당 압축 문자열을 사용해야 하는 확장을 차단하는 JSON을 보여 줍니다.

### <a name="json-example"></a>JSON 예제

   ```json
   { 
        "*": { 
             "blocked_permissions": ["usb"] 
        } 
   } 
   ```

   ```json
   {"*":{"blocked_permissions":["usb"]}} 
   ```

   > [!NOTE]
   > 사용 권한을 사용하는 모든 확장을 차단하려면 이전 예와 같이 확장 ID에 별표를 사용하세요. 확장 ID를 하나만 지정하면 정책이 해당 확장에만 적용됩니다. 둘 이상의 항목을 차단할 수 있지만 이러한 항목은 별도의 항목이어야 합니다.

## <a name="prevent-extensions-from-altering-web-pages"></a>확장이 웹 페이지를 변경하지 못하도록 방지

이 설정을 사용하면 확장이 중요한 웹 사이트 및 도메인의 데이터를 읽고 변경할 수 없습니다. 웹 사이트에 대한 스크립트 삽입, 쿠키 읽기 또는 웹 요청 수정과 같은 작업을 차단하여 원치 않는 작업을 차단합니다. 이 설정은 사용자가 확장을 설치하거나 제거할 수 없도록 하는 것이 아니라 확장이 지정된 웹 사이트를 변경하지 못하게 할 뿐입니다. 
  
> [!NOTE]
> 런타임 허용/차단된 호스트 설정은 확장 설정 정책 내에서만 설정할 수 있습니다.  

웹 사이트 또는 도메인의 변경을 방지하거나 허용하도록 확장 설정 정책에서 다음 설정을 구성할 수 있습니다.

- **Runtime_blocked_hosts**. 이 설정은 사용자가 지정한 웹 사이트에서 확장 기능을 변경하거나 데이터를 읽는 것을 차단합니다.
- **Runtime_allowed_hosts**. 이 설정을 사용하면 사용자가 지정한 웹 사이트에서 확장자가 데이터를 변경하거나 읽을 수 있습니다. 정책의 JSON 문자열에서 사이트를 지정하는 데 사용되는 형식은 다음과 같습니다.

  ```json
  [http|https|ftp|*]://[subdomain|*].[hostname|*].[eTLD|*] [http|https|ftp|*],
  ```

  > [!NOTE]
  > `[hostname|*], and [eTLD|*]` 섹션이 필요하지만 `[subdomain|*]` 섹션은 선택 사항입니다.

다음 표에서는 유효한 호스트 패턴 및 일치 패턴의 예를 보여 줍니다.

|유효한 호스트 패턴|일치 항목|일치하지 않음|
|--|--|--|
|  `*://*.example.*` | `http://example.com`<br>`https://test.example.co.uk`   | `https://example.microsoft.com`<br>`http://example.microsoft.co.uk`  |
| `http://example.*` | `http://example.com`<br>`http://example.ly` | `https://example.com`<br>`http://test.example.com`   |
| `http://example.com`   | `http://example.com` | `https://example.com`<br>`http://test.example.co.uk` |
| `*://*`   | 모든 URL  |   |

다음 단계에 따라 웹 사이트 또는 도메인에 대한 확장을 차단하거나 허용할 수 있습니다..

1. 그룹 정책 관리 편집기를 열고 **관리 템플릿 > Microsoft Edge > 확장**으로 이동하고 **확장 관리 설정 구성**을 선택합니다.  
2. 정책을 실행한 다음 허용하거나 차단할 사용 권한을 입력하여 사용 권한을 단일 JSON 문자열로 압축하세요.

다음 예에서는 호스트 이름에서 확장을 차단하는 방법과 동일한 도메인에서 확장을 차단하는 방법을 보여 줍니다.

### <a name="json-example-to-block-hostname"></a>호스트 이름을 차단하는 JSON 예제

이 예에서는 확장자가 `www.microsoft.com` 호스트 이름에 액세스하지 못하도록 차단하는 JSON 및 압축 JSON 문자열을 보여 줍니다.

```json
{ 
    "*":{ 
            "runtime_blocked_hosts":["www.microsoft.com"] 
    } 
} 
```

```json
{"*":{"runtime_blocked_hosts":["www.microsoft.com"]}} 
```

> [!NOTE]
> 모든 확장자가 웹 페이지에 액세스하지 못하도록 차단하려면 이전 예와 같이 확장 ID에 별표를 사용하세요.  별표 대신 하나의 확장 ID를 지정하면 정책이 해당 확장에만 적용됩니다. 둘 이상의 확장을 차단할 수 있지만 이러한 확장자는 별도의 항목이어야 합니다.

### <a name="json-example-to-block-extensions-on-same-domain"></a>동일한 도메인에서 확장을 차단하는 JSON 예제

이 예에서는 특정 확장이 동일한 도메인 "중요 웹 사이트"에서 실행되지 않도록 차단하는 JSON 및 압축 JSON 문자열을 보여 줍니다.

```json
{ 
    "aapbdbdomjkkjkaonfhkkikfgjllcleb": { 
        "runtime_blocked_hosts": ["*://*.importantwebsite"] 
    }, 
    "bfbmjmiodbnnpllbbbfblcplfjjepjdn": { 
        "runtime_blocked_hosts": ["*://*.importantwebsite"] 
    } 
} 
```

```json
{"aapbdbdomjkkjkaonfhkkikfgjllcleb": {"runtime_blocked_hosts": ["*://,*.importantwebsite"]},"bfbmjmiodbnnpllbbbfblcplfjjepjdn": {"runtime_blocked_hosts": ["*://*.importantwebsite"]}} 
```

## <a name="allow-or-block-extensions-in-group-policy"></a>그룹 정책에서 확장 허용 또는 차단

[ExtensionInstallBlocklist](/DeployEdge/microsoft-edge-policies#extensioninstallblocklist) 및 [ExtensionInstallAllowlist](/DeployEdge/microsoft-edge-policies#extensioninstallallowlist) 정챗을 사용하여 차단되거나 허용된 확장을 제어할 수 있습니다. 다음 단계에 따라 차단할 확장을 제외한 모든 확장을 허용하세요.

1. 그룹 정책 관리 편집기를 열고 **관리 템플릿 > Microsoft Edge > 확장 >** 으로 이동한 다음**설치할 수 없는 확장 제어**를 선택합니다.
2. **사용**을 선택합니다.
3. **표시**를 클릭합니다.
4. 차단할 확장의 앱 ID를 입력합니다. 여러 개의 앱 ID를 추가할 경우 각 ID에 대해 별도의 행을 사용합니다.
5. 모든 확장을 차단하기 위해 정책에 * _를 입력하여 확장이 설치되지 *\** 않도록 합니다. 특정 확장만 설치할 수 있도록 허용 정책과 함께 이 설정을 사용할 수 있습니다. 다음 스크린샷은 제공된 앱 ID를 기준으로 차단되는 확장을 보여줍니다.

   :::image type="content" source="media/microsoft-edge-manage-extensions-policies/manage-extensions-gp-block-2.png" alt-text="앱 ID를 사용하여 확장을 차단합니다.":::

   > [!TIP]
   > 확장의 앱 ID를 찾을 수 없는 경우 Microsoft Edge 추가 기능 웹 사이트에서 확장 기능을 확인하세요. 특정 확장자를 찾으면 옴니박스의 URL 끝에 앱 ID가 표시됩니다.

> [!NOTE]
> 사용자의 시스템에 이미 설치된 차단 목록에 확장을 추가할 수 있습니다. 이렇게 하면 확장이 비활성화되고 사용자가 다시 활성화할 수 없게 됩니다. 제거되지 않고 비활성화만 됩니다.

## <a name="force-install-an-extension"></a>확장 강제 설치

[ExtensionInstallForcelist](/DeployEdge/microsoft-edge-policies#extensioninstallforcelist) 정책을 사용하여 차단되거나 허용되는 확장을 제어합니다. 다음 단계에 따라 확장을 강제로 설치합니다.

1. 그룹 정책 편집기에서 _ 관리 템플릿> Microsoft Edge > 확장 >* 로 이동한 다음*자동으로 *설치되는 확장 **제어를 선택합니다.**
2. **사용**을 선택합니다.  
3. **표시**를 클릭합니다.
4. 강제 설치할 확장의 앱 ID 또는 ID를 입력합니다.  

사용자가 개입할 필요 없이 확장이 자동으로 설치됩니다. 또한 사용자가 확장을 제거하거나 비활성화할 수 없습니다. 이 설정은 사용하도록 설정된 모든 차단 목록 정책을 덮어씁니다.

> [!NOTE]
> Chrome 웹 스토어에서 호스트되는 확장의 경우 `pckdojakecnhhplcgfflhndiffaohfah;https://clients2.google.com/service/update2/crx`와(과) 같은 문자열을 사용합니다.

## <a name="block-extensions-from-a-specific-store-or-update-url"></a>특정 저장소 또는 업데이트 URL에서 확장 차단

저장소 또는 URL에서 확장을 차단하려면 [ExtensionSettings](/deployedge/microsoft-edge-policies#extensionsettings) 정책을 사용하여 해당 스토어에 대한 *update_url*만 차단하면 됩니다.

다음 단계에 따라 특정 저장소 또는 URL의 확장을 차단할 수 있습니다.

1. 그룹 정책 관리 편집기를 열고 **관리 템플릿 > Microsoft Edge > 확장 >** 으로 이동하고 **확장 관리 설정 구성**을 선택합니다.  
2. 정책을 실행한 다음 허용하거나 차단할 사용 권한을 입력하여 단일 JSON 문자열로 압축하세요.

다음 예에서는 업데이트 URL(`https://clients2.google.com/service/update2/crx`)을 사용하여 Chrome 웹 스토어에서 차단할 JSON 및 압축 JSON 문자열을 보여 줍니다.

### <a name="json-example-for-blocking-on-update-url"></a>업데이트 URL 차단에 대한 JSON 예제

```json
{ 
"update_url:https://clients2.google.com/service/update2/crx":{ 
                                                             " installation_mode":"blocked" 
                                                             } 
} 
```

```json
{"update_url:https://clients2.google.com/service/update2/crx":{"installation_mode":"blocked"}} 
```

> [!NOTE]
> 이전 예제의 JSON을 사용하여 스토어가 차단된 경우에도 **ExtensionInstallForcelist** 및 **ExtensionInstallAllowlist를** 사용하여 특정 확장을 허용/강제로 설치할 수 있습니다.

## <a name="see-also"></a>참고 항목

- [엔터프라이즈에서 Microsoft Edge 확장 관리](microsoft-edge-manage-extensions.md)
- [Microsoft Edge 확장을 호스팅할 웹 저장소 만들기](microsoft-edge-manage-extensions-webstore.md)
- [ExtensionSettings 정책에 대한 참조 가이드](microsoft-edge-manage-extensions-ref-guide.md)
- [Microsoft Edge 확장에 대한 FAQ](microsoft-edge-manage-extensions-faq.md)
- [Microsoft Edge Enterprise 방문 페이지](https://aka.ms/EdgeEnterprise)
