---
title: ExtensionSettings 정책에 대한 자세한 가이드
ms.author: aspoddar
author: dan-wesley
manager: balajek
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: ExtensionSettings 정책을 사용하여 Microsoft Edge 확장을 구성하기 위한 자세한 참조 가이드입니다.
ms.openlocfilehash: 7dceff78172626d70863883e0762be2f4cb7e51c
ms.sourcegitcommit: e825c6a1b0e63004288e13f6bb672743b0ecfafb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/05/2021
ms.locfileid: "12069014"
---
# <a name="detailed-guide-to-the-extensionsettings-policy"></a>ExtensionSettings 정책에 대한 자세한 가이드

Microsoft Edge는 확장을 관리하기 위한 여러 방법을 제공합니다. 일반적인 방법은 Windows 그룹 정책 편집기에서 JSON 문자열을 사용하여 한 곳에서 여러 정책을 설정하거나 Windows 레지스트리에서 [ExtensionSettings](/deployedge/microsoft-edge-policies#extensionsettings) 정책을 설정하는 것입니다.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.

## <a name="before-you-begin"></a>시작하기 전에

여기에서 모든 확장 관리 설정을 설정하거나 다른 정책을 통해 컨트롤을 설정할지 결정해야 합니다.
  
ExtensionSettings 정책은 다음 정책을 포함하여 그룹 정책의 다른 위치에서 설정한 다른 정책을 덮어쓸 수 있습니다.

- [ExtensionAllowedTypes](/DeployEdge/microsoft-edge-policies#extensionallowedtypes)
- [ExtensionInstallBlocklist](/DeployEdge/microsoft-edge-policies#extensioninstallblocklist)
- [ExtensionInstallForcelist](/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)
- [ExtensionInstallSources](/DeployEdge/microsoft-edge-policies#extensioninstallsources)
- [ExtensionInstallAllowlist](/DeployEdge/microsoft-edge-policies#extensioninstallsources)

## <a name="extensionsettings-policy-fields"></a>ExtensionSettings 정책 필드

이 정책은 URL 업데이트, 초기 설치를 위해 확장을 다운로드할 위치, 차단된 권한이나 실행하도록 허용되지 않은 권한과 같은 설정을 제어할 수 있습니다. 사용 가능한 정책 필드는 다음 표에 설명되어 있습니다.

| &nbsp; | 설명 |
|--|--|
| **allowed_types** | 기본 구성*을 구성하는 데만 사용할 수 있습니다. Microsoft Edge에서 설치할 수 있는 앱 또는 확장 사용자 유형을 지정합니다. 값은 문자열 목록이며, 각 문자열은 "extension", "theme", "user_script" 및 "hosted_app" 형식 중 하나여야 합니다.   |
| **blocked_install_message**| 사용자가 특정 확장을 설치하지 못하도록 차단하는 경우 사용자가 설치하려고 하면 브라우저에 표시할 사용자 지정 메시지를 지정할 수 있습니다.<br>Microsoft Edge 추가 기능 웹 사이트에 표시되는 일반 오류 메시지에 텍스트를 추가합니다. 예를 들어 IT 부서에 문의하는 방법 또는 특정 확장을 사용할 수 없는 이유를 사용자에게 알릴 수 있습니다. 메시지는 최대 1,000자까지 가능합니다.   |
|**blocked_permissions**  | 사용자가 조직에서 허용하지 않는 특정 API 권한을 요청하는 확장을 설치하고 실행할 수 없도록 합니다. 예를 들어 쿠키에 액세스하는 확장을 차단할 수 있습니다. 확장에 차단한 권한이 필요한 경우 사용자는 확장을 설치할 수 없습니다. 사용자가 이전에 확장을 설치한 경우 더 이상 로드되지 않습니다. 확장에 선택적 요구 사항으로 차단된 사용 권한이 포함된 경우 평소처럼 설치됩니다. 그런 다음 확장이 실행되는 동안 차단된 권한은 자동으로 거부됩니다.<br>사용 가능한 사용 권한 목록은 [사용 권한 선언](/microsoft-edge/extensions-chromium/enterprise/declare-permissions)을 참조하세요.   |
| **installation_mode**| 지정한 확장을 Microsoft Edge에 추가할지 여부와 방법을 제어합니다. 설치 모드를 다음 옵션 중 하나로 설정할 수 있습니다.<br>- allowed: 사용자가 확장을 설치할 수 있습니다. 설치 모드가 정의되지 않은 경우 이 설정이 기본값입니다.<br>- blocked: 사용자가 확장을 설치할 수 없습니다.<br>- force_installed: 사용자 상호 작용 없이 확장을 자동으로 설치합니다. 사용자는 제거할 수 없습니다. 또한 update_url을 사용하여 확장 다운로드 위치를 정의해야 합니다. **참고**: Microsoft Edge가 자동으로 설치할 확장을 알 수 없어 *에서는 이 설정을 사용할 수 없습니다.<br>- normal_installed: 사용자 상호 작용 없이 확장을 자동으로 설치합니다. 사용자가 사용하지 않도록 설정할 수 있습니다. 또한 update_url을 사용하여 확장 다운로드 위치를 정의해야 합니다. **참고**: Microsoft Edge가 자동으로 설치할 확장을 알 수 없어 *에서는 이 설정을 사용할 수 없습니다.<br>- 제거됨: 사용자가 확장을 설치할 수 없습니다. 사용자가 이전에 확장을 설치한 경우 Microsoft Edge가 확장을 제거합니다. |  |
| **install_sources** | 기본 구성 *을(를) 구성하는 데만 사용할 수 있습니다. 확장을 설치할 수 있는 URL을 지정합니다. *.crx 파일의 위치 및 다운로드를 시작하는 페이지(참조 페이지) 모두 해당 패턴에서 허용되어야 합니다. URL 패턴 예제는 [일치 패턴](/microsoft-edge/extensions-chromium/enterprise/match-patterns)을 참조하세요.  |
| **minimum_version_required** |Microsoft Edge는 지정된 최소 버전보다 오래된 버전을 사용하여 강제로 설치된 확장을 비롯한 확장을 사용하지 않도록 설정합니다.<br>버전 문자열의 형식은 확장 매니페스트에 사용된 형식과 동일합니다.     |
| **update_url** | force_installed 및 normal_installed에만 적용됩니다. Microsoft Edge 확장을 다운로드할 위치를 지정합니다. 확장이 Microsoft Edge 추가 기능 웹 사이트에서 호스트되는 경우 `https://edge.microsoft.com/extensionwebstorebase/v1/crx` 위치를 사용합니다.<br>Microsoft Edge는 초기 확장 설치에 지정한 URL을 사용합니다. 후속 확장 업데이트의 경우 Microsoft Edge는 확장 매니페스트의 URL을 사용합니다.   |
| **runtime_allowed_hosts**| 확장이 runtime_blocked_hosts로 정의되어 있더라도 지정된 웹 사이트와 상호 작용할 수 있습니다. 최대 100초를 지정할 수 있습니다. 추가 항목은 삭제됩니다.<br>호스트 패턴 형식은 경로를 정의할 수 없다는 점을 제외하고  [일치 패턴](/microsoft-edge/extensions-chromium/enterprise/match-patterns) 과 동일합니다. 예:<br>- *://*.example.com<br>- *://example.*—eTLD 와일드카드가 지원됩니다.     |
| **runtime_blocked_hosts**| 사용자가 지정한 웹 사이트와 확장 기능이 상호 작용하거나 수정할 수 없도록 합니다. 수정에는 JavaScript 삽입 차단, 쿠키 액세스 및 웹 요청 수정이 포함됩니다.<br>최대 100초를 지정할 수 있습니다. 추가 항목은 삭제됩니다.<br>호스트 패턴 형식은 경로를 정의할 수 없다는 점을 제외하고 일치 패턴과 동일합니다. 예:<br>- *://*.example.com<br>- *://example.*—eTLD 와일드카드가 지원됩니다.   |
| **override_update_url**| Edge 93에서 사용 가능<br>이 로 설정된 경우 Edge는 후속 확장 업데이트에 ExtensionSettings 정책 또는 ExtensionInstallForcelist 정책에 지정된 업데이트 `true` URL을 사용합니다.<br>이 설정이 아니거나 로 설정되어 있는 경우 Edge는 업데이트를 위해 확장의 `false` 매니페스트에 지정된 URL을 사용합니다.|
| **toolbar_state**| Edge 94에서 사용 가능<br>이 정책 설정을 사용하면 도구 모음에 설치된 확장을 강제로 표시하는 데 사용할 수 있습니다. 기본 상태는 `default_shown` 모든 확장에 대한 것입니다. 이 설정에 대해 다음과 같은 상태일 수 있습니다.<br>-`force_shown`: 도구 모음에 설치된 확장을 강제로 표시하는 것을 선택할 수 있습니다. 사용자는 도구 모음에서 특정 확장 아이콘을 숨길 수 없습니다.<br>-`default_hidden`: 이 상태의 경우 설치 시 도구 모음에서 확장이 숨겨집니다. 사용자는 필요한 경우 도구 모음에 표시될 수 있습니다.<br>-`default_shown`: 브라우저에 설치된 모든 확장의 청각 장애 설정입니다.

다음은 전역 범위(*)에서 허용되는 키입니다. 

- blocked_permissions
- installation_mode - 또는 이 범위의 `"blocked"` `"allowed"` 유효한 `"removed"` 값입니다.
- runtime_blocked_hosts
- blocked_install_message
- allowed_types
- runtime_allowed_hosts
- install_sources

다음은 개별 확장 범위에서 허용되는 키입니다. 

- blocked_permissions
- minimum_version_required
- blocked_install_message
- installation_mode - `"blocked"` , `"allowed"` , 및 `"removed"` `"force_installed"` `"normal_installed"` 는 가능한 값입니다.
- runtime_allowed_hosts
- update_url
- override_update_url
- runtime_blocked_hosts
- toolbar_state

업데이트 URL 범위에서 허용되는 키는 다음 키입니다. 

- blocked_permissions
- installation_mode - 또는 이 범위의 `"blocked"` `"allowed"` 유효한 `"removed"` 값입니다.

## <a name="configure-using-a-json-string-in-windows-group-policy-editor"></a>Windows 그룹 정책 편집기에서 JSON 문자열을 사용하여 구성

GPO를 사용하여 확장 설정 정책을 사용하는 단계에서는 Microsoft Edge 정책용 ADMX를 이미 가져온 것으로 가정합니다.

1. 그룹 정책 편집기를 열고 **Microsoft Edge > 확장 > 확장 관리 설정 정책 구성**으로 이동합니다.
2. 정책을 사용하도록 설정하고 텍스트 상자에 줄 바꿈 없이 한 줄로 압축 JSON(JavaScript Object Notation) 데이터를 입력합니다.
3. 정책을 검증하고 한 줄로 압축하려면 JSON 압축 도구를 사용하세요.

### <a name="properly-format-json-for-the-extension-settings-policy"></a>확장 설정 정책에 대한 JSON 형식을 올바르게 지정합니다.

이 정책의 두 부분(기본 범위 및 개별 범위)을 이해해야 합니다. 기본 범위는 자체 범위가 없는 확장에 대한 catch-all입니다. 개별 범위는 해당 확장에만 적용됩니다.  

기본 범위는 별표(*)로 식별됩니다. 다음 예제에서는 기본 범위 및 개별 확장 범위를 정의합니다.

```json
{ 
   “*”: {}, 
   “nckgahadagoaajjgafhacjanaoiihapd”: {} 
} 
```

확장은 한 범위에서만 해당 설정을 가져옵니다. 해당 확장에 대한 개별 확장 범위가 있는 경우 해당 확장에 적용되는 설정이 됩니다. 개별 확장 범위가 없는 경우 확장은 기본 범위를 사용합니다.  

다음 JSON 예제에서는 `.example.com`에서 실행되는 확장을 차단하고 "USB" 사용 권한이 필요한 확장을 차단합니다.

```json
{ 
  "*": { 
    "runtime_blocked_hosts": ["*://*.example.com"], 
    "blocked_permissions": ["usb"] 
  } 
} 
```

**압축 JSON**

```json
{"*":{"runtime_blocked_hosts":["*://*.example.com"],"blocked_permissions":["usb"]}} 
```

### <a name="a-few-more-json-examples-for-extension-settings"></a>확장 설정에 대한 몇 가지 추가 JSON 예제

#### <a name="using-installation_mode-property-to-allow-and-block-extensions"></a>installation_mode 속성을 사용하여 확장 허용 및 차단

- 사용자가 모든 확장을 설치할 수 있음 - 기본 설정입니다. 

  `{ "*": {"installation_mode": "allowed" }}`
- 사용자가 확장을 설치할 수 없습니다.  

  `{ "*": {"installation_mode": "blocked" }}`

- 설치가 차단될 때 표시할 사용자 지정 메시지를 지정합니다.

   `{"*": {"blocked_install_message": ["Call IT(408 - 555 - 1234) for an exception"]}}`

#### <a name="using-installation_mode-property-to-force-install-extensions"></a>installation_mode 속성을 사용하여 확장 강제 설치

installation_mode를 "force_installed"로 사용하면 사용자 상호 작용 없이 확장이 자동으로 설치됩니다. 사용자는 확장을 사용하지 않도록 설정하거나 제거할 수 없습니다. 확장이 "normal" 또는 "force" 설치된 경우 **update_url** 필드도 정의해야 합니다. 이 필드는 확장을 설치할 수 있는 위치를 가리킵니다. **update_url** 필드에 다음 위치를 사용합니다.

- 다운로드하는 확장이 Microsoft Edge 추가 기능 저장소에서 호스트되는 경우 [https://edge.microsoft.com/extensionwebstorebase/v1/crx](https://edge.microsoft.com/extensionwebstorebase/v1/crx)을(를) 사용합니다.
- 다운로드하는 확장이 Chrome 웹 스토어 호스트되는 경우 [https://clients2.google.com/service/update2/crx](https://clients2.google.com/service/update2/crx)을(를) 사용합니다.
- 자체 서버에서 확장을 호스팅하는 경우 Microsoft Edge에서 압축된 확장명(.crx 파일)을 다운로드할 수 있는 URL을 사용합니다. JSON 예제:

   `{"nckgahadagoaajjgafhacjanaoiihapd": {"installation_mode": "force_installed","update_url": "https://edge.microsoft.com/extensionwebstorebase/v1/crx"}}`
  
위의 예제에서 "force_installed" 대신 "normal_installed"를 사용하면 사용자 상호 작용 없이 확장이 자동으로 설치되지만 확장을 사용하지 않도록 설정할 수 있습니다.  

   > [!TIP]
   > JSON 문자열의 서식을 올바르게 지정하는 것은 어려울 수 있습니다. 정책을 구현하기 전에 JSON 검사기를 사용합니다. 또는 [확장 설정 생성기 도구](https://microsoft.github.io/edge-extension-settings-generator/minimal)의 초기 버전을 사용해 보세요.

## <a name="configure-using-the-windows-registry"></a>Windows 레지스트리를 사용하여 구성

ExtensionSettings 정책은 다음 키 아래의 레지스트리에 기록되어야 합니다.

`HKLM\Software\Policies\Microsoft\Edge\`

> [!NOTE]
> HKLM 대신 HKCU를 사용할 수 있습니다. 해당 경로는 GPO(그룹 정책 개체)로 구성할 수 있습니다.  

Microsoft Edge의 경우 모든 설정이 다음 키에서 시작됩니다.

`HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Edge\`

다음으로 만들 키는 개별 범위의 확장 ID 또는 기본 범위의 별표(*)입니다. 예를 들어 Google 행아웃에 적용되는 설정에는 다음 위치를 사용합니다.

`HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Edge\ExtensionSettings\nckgahadagoaajjgafhacjanaoiihapd`

기본 범위에 적용되는 설정의 경우 이 위치를 사용합니다.

`HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Edge\ExtensionSettings\*`

문자열인지 문자열 배열인지에 따라 다른 형식이 필요합니다. 배열 값에는 ["value"]이(가) 필요합니다. 문자열 값을 있는 그대로 입력할 수 있습니다. 다음 목록에서는 배열 또는 문자열 설정을 보여 줍니다.

- Installation_mode = 문자열
- update_url = 문자열
- blocked_permissions = 문자열 배열
- allowed_permissions = 문자열 배열
- minimum_version_required = 문자열
- runtime_blocked_hosts = 문자열 배열
- runtime_allowed_hosts = 문자열 배열
- blocked_install_message = 문자열


## <a name="see-also"></a>참고 항목

- [엔터프라이즈에서 Microsoft Edge 확장 관리](microsoft-edge-manage-extensions.md)
- [그룹 정책을 사용하여 Microsoft Edge 확장 관리](microsoft-edge-manage-extensions-policies.md)
- [Microsoft Edge 확장에 대한 FAQ](microsoft-edge-manage-extensions-faq.md)
- [Microsoft Edge Enterprise 방문 페이지](https://aka.ms/EdgeEnterprise)
