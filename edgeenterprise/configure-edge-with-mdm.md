---
title: 모바일 장치 관리를 사용하여 Microsoft Edge 구성
ms.author: kvice
author: dan-wesley
manager: laurawi
ms.date: 11/17/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 모바일 장치 관리를 사용하여 Microsoft Edge를 구성합니다.
ms.openlocfilehash: 96fa6f4d096d8acd5369b92de7e1d979191e13ec
ms.sourcegitcommit: e7f3098d8b7d91cae20b5778a71a87daababc312
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "12297736"
---
# <a name="configure-microsoft-edge-using-mobile-device-management"></a>모바일 장치 관리를 사용하여 Microsoft Edge 구성

이 문서에서는 ADMX Microsoft Edge [MDM(모바일](/windows/client-management/mdm/) Windows 10 관리)을 사용하여 모바일 장치 관리를 구성하는 [방법을 설명합니다.](/windows/client-management/mdm/win32-and-centennial-app-policy-configuration) 이 문서에서는 다음 방법도 설명합니다.

- Microsoft Edge 정책에 대한 [OMA-URI(Open Mobile Alliance - Uniform Resource Identifier)를 만드는](#create-an-oma-uri-for-microsoft-edge-policies) 방법.
- [ADMX 수집 및 사용자 지정 OMA-URI를 사용하여 Intune에서 Microsoft Edge를 구성](#configure-microsoft-edge-in-intune-using-admx-ingestion)하는 방법.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.

## <a name="prerequisites"></a>필수 구성 요소

다음 최소 시스템 요구 사항을 충족하는 Windows 10:

- [KB4512941](https://support.microsoft.com/help/4512941/) 및 [KB4517211](https://support.microsoft.com/help/4517211/)이 설치된 Windows 10, 버전 1903
- [KB4512534](https://support.microsoft.com/help/4512534/) 및 [KB4520062](https://support.microsoft.com/help/4520062/)이 설치된 Windows 10, 버전 1809
- [KB4512509](https://support.microsoft.com/help/4512509/) 및 [KB4519978](https://support.microsoft.com/help/4519978)이 설치된 Windows 10, 버전 1803
- [KB4516071](https://support.microsoft.com/help/4516071/) 및 [KB4520006](https://support.microsoft.com/help/4520006)이 설치된 Windows 10, 버전 1709

## <a name="overview"></a>개요

기본 EMM(엔터프라이즈 이동성 관리)이 포함된 MDM 또는[ADMX 수집](/windows/client-management/mdm/win32-and-centennial-app-policy-configuration)을 지원하는 MDM 공급자를 사용하여 Windows 10에서 Microsoft Edge를 구성할 수 있습니다.

MDM으로 Microsoft Edge를 구성하는 과정은 다음 두 부분으로 진행됩니다.

1. Microsoft Edge ADMX 파일을 EMM 또는 MDM 공급자로 수집. ADMX 파일을 수집하는 방법에 대한 지침은 공급자를 참조하세요.

   > [!NOTE]
   > Microsoft Intune의 경우 [ADMX 수집을 사용하여 Intune에서 Microsoft Edge 구성](#configure-microsoft-edge-in-intune-using-admx-ingestion)을 참조하세요.

2. [Microsoft Edge 정책에 대한 OMA-URI 만들기](#create-an-oma-uri-for-microsoft-edge-policies)

## <a name="create-an-oma-uri-for-microsoft-edge-policies"></a>Microsoft Edge 정책에 대한 OMA-URI 만들기

다음 섹션에서는 OMA-URI 경로를 만들고 필수 및 권장 브라우저 정책에 대한 XML 형식의 값을 찾아 정의하는 방법을 설명합니다.

시작하기 전에 Microsoft Edge 방문 페이지에서 MicrosoftEdgePolicyTemplates.cab 정책 템플릿 [파일(Microsoft Edge Enterprise)을](https://aka.ms/EdgeEnterprise) 다운로드하고 콘텐츠를 추출합니다.

OMA-URI를 정의하는 과정은 다음 세 단계로 진행됩니다.

1. [OMA-URI 경로 만들기](#create-the-oma-uri-path)
2. [OMA-URI 데이터 형식 지정](#specify-the-data-type)
3. [OMA-URI 값 설정](#set-the-value-for-a-browser-policy)

### <a name="create-the-oma-uri-path"></a>OMA-URI 경로 만들기

다음 수식을 가이드로 사용하여 OMA-URI 경로를 만듭니다. <br/><br/>
*`./Device/Vendor/MSFT/Policy/Config/<ADMXIngestName>~Policy~<ADMXNamespace>~<ADMXCategory>/<PolicyName>`* <br/><br/>

| 매개 변수         | 설명                                                                                   |
|-------------------|-----------------------------------------------------------------------------------------------|
| \<ADMXIngestName> | 관리 템플릿을 수집할 때 "Edge" 또는 사용자가 정의한 항목을 사용합니다. 예를 들어 "./Device/Vendor/MSFT/Policy/ConfigOperations/ADMXInstall/MicrosoftEdge/Policy/EdgeAdmx"을 사용한 경우 "MicrosoftEdge"를 사용합니다.<br/><br/> `<ADMXIngestionName>`은 ADMX 파일을 수집할 때 사용한 것과 일치해야 합니다. |
| \<ADMXNamespace>  | 필수 또는 권장 정책을 설정하는지 여부에 따라 "microsoft_edge" 또는 "microsoft_edge_recommended" 중 하나를 선택합니다. |
| \<ADMXCategory>   | 정책의 "parentCategory"는 ADMX 파일에 정의되어 있습니다. 정책이 그룹화되지 않은 경우(정의된 "parentCategory"가 없음) `<ADMXCategory>`를 생략합니다. |
| \<PolicyName>     | 정책 이름은 [브라우저 정책 참조](./microsoft-edge-policies.md) 문서에서 찾을 수 있습니다. |

#### <a name="uri-path-example"></a>URI 경로 예:

이 예에서는 `<ADMXIngestName>` 노드의 이름이 "Edge"이고 사용자가 필수 정책을 설정하는 것으로 가정합니다. URI 경로는 다음과 같습니다.<br/><br/>
*`./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~<ADMXCategory>/<PolicyName>`*

정책이 그룹에 있지 않으면(예: DiskCacheSize) "`~<ADMXCategory>`"를 제거합니다. `<PolicyName>`을 정책의 이름 DiskCacheSize로 대체합니다. URI 경로는 다음과 같습니다.<br/><br/>
*`./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge/DiskCacheSize`*

정책이 그룹에 있는 경우 다음 단계를 수행합니다.

1. 임의의 xml 편집기를 사용하여 **msedge.admx**를 엽니다.
2. 설정하려는 정책 이름을 검색합니다. 예: "ExtensionInstallForceList".
3. *parentCategory* 요소에서 *ref* 특성의 값을 사용합니다. 예를 들어 \<parentCategory ref=" Extensions"/>에서의 "확장"이 있습니다.
4. `<ADMXCategory>`를 *ref* 특성 값으로 대체하여 URI 경로를 구성합니다. URI 경로는 다음과 같습니다.<br/><br/>
*`/Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Extensions/ExtensionInstallForcelist`*

### <a name="specify-the-data-type"></a>데이터 형식 지정

OMA-URI 데이터 형식은 항상 "String"입니다.

### <a name="set-the-value-for-a-browser-policy"></a>브라우저 정책에 대한 값 설정

이 섹션에서는 각 데이터 형식에 대한 값을 XML 형식으로 설정하는 방법을 설명합니다. [브라우저 정책 참조](./microsoft-edge-policies.md)로 이동하여 정책의 데이터 형식을 조회합니다.

> [!NOTE]
> 부울 데이터 형식이 아닌 경우 이 값은 항상 `<enabled/>`로 시작합니다.

#### <a name="boolean-data-type"></a>부울 데이터 형식

부울 형식인 정책에 대해서는 `<enabled/>` 또는 `<disabled/>`를 사용합니다.

#### <a name="integer-data-type"></a>정수 데이터 형식

이 값은 항상 `<enabled/>` 요소로 시작하고 `<data id="[valueName]" value="[decimal value]"/>`이 뒤따라야 합니다.

새 탭 페이지에 대한 값 이름과 소수 값을 찾으려면 다음 단계를 사용합니다.

1. 임의의 xml 편집기를 사용하여 **msedge.admx**를 엽니다.
2. 이름 특성이 설정하려는 정책 이름과 일치하는 `<policy>` 요소를 검색합니다. "RestoreOnStartup"의 경우 `name="RestoreOnStartup"`을 검색합니다.
3. `<elements>` 노드에서 설정하려는 값을 찾습니다.
4. `<elements>` 노드에서 "valueName" 특성의 값을 사용합니다. "RestoreOnStartup"의 경우 "valueName"은 "RestoreOnStartup"입니다.
5. `<decimal>` 노드에서 "value" 특성의 값을 사용합니다. "RestoreOnStartup"으로 새 탭 페이지를 열려면 값은 "5"입니다.

시작 시 새 탭 페이지를 열려면 다음을 사용합니다.<br>
`<enabled/> <data id="RestoreOnStartup" value="5"/>`

#### <a name="list-of-strings-data-type"></a>문자열 목록 데이터 형식 목록

이 값은 항상 `<enabled/>` 요소로 시작하고 `<data id="[listID]" value="[string 1];[string 2];[string 3]"/>`이 뒤따라야 합니다.

> [!NOTE]
> 대부분의 경우 정책 이름과 일치하지만 "id=" 특성 이름은 정책 이름이 아닙니다. 이는 ADMX 파일에 있는 \<list> node ID 특성 값입니다.

listID를 찾고 URL을 차단하는 값을 정의하려면 다음 단계를 수행합니다.

1. 임의의 xml 편집기를 사용하여 **msedge.admx**를 엽니다.
2. 이름 특성이 설정하려는 정책 이름과 일치하는 `<policy>` 요소를 검색합니다. "URLBlocklist"의 경우 `name="URLBlocklist"`를 검색합니다.
3. `<list> node for [listID]` 노드에서 "id" 특성의 값을 사용합니다.
4. "값"은 세미콜론(;)으로 구분된 URL 목록입니다.

예를 들어, `contoso.com` 및 `https://ssl.server.com`에 대한 액세스를 차단하려면<br>
`<enabled/> <data id=" URLBlocklistDesc" value="contoso.com;https://ssl.server.com"/>`

#### <a name="dictionary-or-string-data-type"></a>사전 또는 문자열 데이터 형식

이 값은 항상 `<enabled/>`로 시작하고 `<data id="[textID]" value="[string]"/>`이 뒤따라야 합니다.

textID를 찾고 로캘을 차단하는 값을 정의하려면 다음 단계를 수행합니다.

1. 임의의 xml 편집기를 사용하여 **msedge.admx**를 엽니다.
2. 이름 특성이 설정하려는 정책 이름과 일치하는 `<policy>` 요소를 검색합니다. "ApplicationLocaleValue"의 경우 `name="ApplicationLocaleValue"`를 검색합니다.
3. `[textID]`에 대한 `<text>` 노드에서 "id" 특성의 값을 사용합니다.
4. "값"을 문화 코드로 설정합니다.

"ApplicationLocaleValue" 정책을 사용하여 로캘을 "es-US"로 설정하려면<br>
`<enabled/> <data id="ApplicationLocaleValue" value="es-US"/>`

사전 데이터 형식은 큰 문자열로 처리되지만 일반적으로 값을 올바른 양식으로 이스케이프해야 합니다.

예를 들어 ManagedFavorites 정책을 설정하는 경우 값은 다음과 같습니다.

```xml
<enabled/> <data id="ManagedFavorites" value="[{&quot;toplevel_name&quot;: &quot;My managed favorites folder&quot;}, {&quot;name&quot;: &quot;Microsoft&quot;, &quot;url&quot;: &quot;microsoft.com&quot;}, {&quot;name&quot;: &quot;Bing&quot;, &quot;url&quot;: &quot;bing.com&quot;}, {&quot;children&quot;: [{&quot;name&quot;: &quot;Microsoft Edge Insiders&quot;, &quot;url&quot;: &quot;www.microsoftedgeinsider.com&quot;}, {&quot;name&quot;: &quot;Microsoft Edge&quot;, &quot;url&quot;: &quot;www.microsoft.com/windows/microsoft-edge&quot;}], &quot;name&quot;: &quot;Microsoft Edge links&quot;}]"/>
```

### <a name="create-the-oma-uri-for-recommended-policies"></a>권장 정책에 대한 OMA-URI 만들기

권장 정책에 대한 URI 경로 정의는 구성하려는 정책에 따라 달라집니다.

#### <a name="to-define-the-uri-path-for-a-recommended-policy"></a>권장 정책에 대한 URI 경로를 정의하려면

URI 경로 수식(*`./Device/Vendor/MSFT/Policy/Config/<ADMXIngestName>~Policy~<ADMXNamespace>~<ADMXCategory>/<PolicyName>`*)을 사용하고 다음 단계를 수행하여 URI 경로를 정의합니다.
1. 임의의 xml 편집기를 사용하여 **msedge.admx**를 엽니다.
2. 구성하려는 정책이 그룹에 없으면 4단계로 건너뛰고 경로에서 `~<ADMXCategory>`를 제거합니다.
3. 구성하려는 정책이 그룹에 있는 경우:

   - `<ADMXCategory>`를 조회하려면 설정하려는 정책을 검색합니다. 검색할 때 정책 이름에 "_recommended" 추가합니다. 예를 들어 "RegisteredProtocolHandlers_recommended"에 대한 검색 결과는 다음과 같습니다.

        ```xml
         <policy class="Both" displayName="$(string.RegisteredProtocolHandlers)" explainText="$(string.RegisteredProtocolHandlers_Explain)" key="Software\Policies\Microsoft\Edge\Recommended" name="RegisteredProtocolHandlers_recommended" presentation="$(presentation.RegisteredProtocolHandlers)">
           <parentCategory ref="ContentSettings_recommended"/>
           <supportedOn ref="SUPPORTED_WIN7_V77"/>
           <elements>
             <text id="RegisteredProtocolHandlers" maxLength="1000000" valueName="RegisteredProtocolHandlers"/>
           </elements>
         </policy>
        ```

   - `<parentCategory>` 요소에서 *ref* 특성의 값을 복사합니다. "ContentSettings"의 경우 `<parentCategory ref=" ContentSettings_recommended"/>`에서 "ContentSettings_recommended"를 복사합니다.
   - URI 경로 수식에서 `<ADMXCategory>`를 *ref* 특성 값으로 대체하여 URI 경로를 구성합니다.

4. `<PolicyName>`은 "_recommended"가 추가된 정책의 이름입니다.

#### <a name="oma-uri-path-examples-for-recommended-policies"></a>권장 정책에 대한 OMA-URI 경로 예

다음 표에서는 권장 정책에 대한 OMA-URI 경로의 예를 보여 줍니다.

|      정책    |   OMA-URI  |
|-----------------------------------|------------------------------------------|
| [RegisteredProtocolHandlers](./microsoft-edge-policies.md#registeredprotocolhandlers)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~ContentSettings_recommended/RegisteredProtocolHandlers_recommended`                        |
| [PasswordManagerEnabled](./microsoft-edge-policies.md#passwordmanagerenabled)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~PasswordManager_recommended/PasswordManagerEnabled_recommended`                        |
| [PrintHeaderFooter](./microsoft-edge-policies.md#printheaderfooter)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~Printing_recommended/PrintHeaderFooter_recommended`                        |
| [SmartScreenEnabled](./microsoft-edge-policies.md#smartscreenenabled)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~SmartScreen_recommended/SmartScreenEnabled_recommended`                        |
| [HomePageLocation](./microsoft-edge-policies.md#homepagelocation)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~Startup_recommended/HomepageLocation_recommended`                        |
| [ShowHomeButton](./microsoft-edge-policies.md#showhomebutton)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~Startup_recommended/ShowHomeButton_recommended`                        |
| [FavoritesBarEnabled](./microsoft-edge-policies.md#favoritesbarenabled)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~/FavoritesBarEnabled_recommended`                        |

### <a name="oma-uri-examples"></a>OMA-URI 예

URI 경로, 형식 및 예제 값이 포함된 OMA-URI 예입니다.

#### <a name="boolean-data-type-examples"></a>부울 데이터 형식 예

*[ShowHomeButton](./microsoft-edge-policies.md#showhomebutton):*

| 필드   | 값                                                                                |
|---------|--------------------------------------------------------------------------------------|
| 이름    | Microsoft Edge: ShowHomeButton                                                       |
| OMA-URI | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Startup/ShowHomeButton` |
| 형식    | 문자열                                                                               |
| 값   | `<enabled/>`                                                                          |

*[DefaultSearchProviderEnabled](./microsoft-edge-policies.md#defaultsearchproviderenabled):*

| 필드   | 값                                                                                |
|---------|--------------------------------------------------------------------------------------|
| 이름    | Microsoft Edge: DefaultSearchProviderEnabled                                         |
| OMA-URI | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~DefaultSearchProvider/DefaultSearchProviderEnabled`    |
| 형식    | 문자열                                                                               |
| 값   | `<disable/>`                                                                          |

### <a name="integer-data-type-examples"></a>정수 데이터 형식 예

*[AutoImportAtFirstRun](./microsoft-edge-policies.md#autoimportatfirstrun):*

| 필드   | 값                                                                                |
|---------|--------------------------------------------------------------------------------------|
| 이름    | Microsoft Edge: AutoImportAtFirstRun                                                 |
| OMA-URI | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge/AutoImportAtFirstRun`   |
| 형식    | 문자열                                                                               |
| 값   | `<enabled/><data id="AutoImportAtFirstRun" value="1"/>`                             |

*[DefaultImagesSetting](./microsoft-edge-policies.md#defaultimagessetting):*

| 필드   | 값                                                                                |
|---------|--------------------------------------------------------------------------------------|
| 이름    | Microsoft Edge: DefaultImagesSetting                                                 |
| OMA-URI | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~ContentSettings/DefaultImagesSetting`    |
| 형식    | 문자열                                                                               |
| 값   | `<enabled/><data id="DefaultImagesSetting" value="2"/>`                             |

*[DiskCacheSize](./microsoft-edge-policies.md#diskcachesize):*

| 필드   | 값                                                                                |
|---------|--------------------------------------------------------------------------------------|
| 이름    | Microsoft Edge: DiskCacheSize                                                        |
| OMA-URI | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge/DiskCacheSize`        |
| 형식    | 문자열                                                                               |
| 값   | `<enabled/><data id="DiskCacheSize" value="1000000"/>`                               |

#### <a name="list-of-strings-data-type-examples"></a>문자열 목록 데이터 형식 예

*[RestoreOnStartupURLS](./microsoft-edge-policies.md#restoreonstartupurls):*

| 필드   | 값                                                                                |
|---------|--------------------------------------------------------------------------------------|
| 이름    | Microsoft Edge: RestoreOnStartupURLS                                                 |
| OMA-URI | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Startup/RestoreOnStartupURLs`    |
| 형식    | 문자열                                                                               |
| 값   | `<enabled/><data id="RestoreOnStartupURLsDesc" value="1&#xF000;http://www.bing.com"/>`<br>다중 목록 항목의 경우: `<enabled/><data id="RestoreOnStartupURLsDesc" value="1&#xF000;http://www.bing.com&#xF000;2&#xF000;http://www.microsoft.com"/>`  |

*[ExtensionInstallForcelist](./microsoft-edge-policies.md#extensioninstallforcelist):*

| 필드   | 값                                                                                |
|---------|--------------------------------------------------------------------------------------|
| 이름    | Microsoft Edge: ExtensionInstallForcelist                                            |
| OMA-URI | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Extensions/ExtensionInstallForcelist`    |
| 형식    | 문자열                                                                               |
| 값   | `<enabled/><data id="ExtensionInstallForcelistDesc" value="1&#xF000;gbchcmhmhahfdphkhkmpfmihenigjmpp;https://extensionwebstorebase.edgesv.net/v1/crx"/>`                               |

#### <a name="dictionary-and-string-data-type-examples"></a>사전 및 문자열 데이터 형식 예제

*[ProxyMode](./microsoft-edge-policies.md#proxymode):*

| 필드   | 값      |
|---------|------------|
| 이름    | Microsoft Edge: ProxyMode                                                            |
| OMA-URI | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~ProxyMode/ProxyMode`  |
| 형식    | 문자열                                                                               |
| 값   | `<enabled/><data id="ProxyMode" value="auto_detect"/>`                               |

*[ManagedFavorites](./microsoft-edge-policies.md#managedfavorites):*

| 필드   | 값    |
|---------|----------|
| 이름    | Microsoft Edge: ManagedFavorites                                                            |
| OMA-URI | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge/ManagedFavorites`  |
| 형식    | 문자열                                                                               |
| 값   | `<enabled/> <data id="ManagedFavorites" value="[{&quot;toplevel_name&quot;: &quot;My managed favorites folder&quot;}, {&quot;name&quot;: &quot;Microsoft&quot;, &quot;url&quot;: &quot;microsoft.com&quot;}, {&quot;name&quot;: &quot;Bing&quot;, &quot;url&quot;: &quot;bing.com&quot;}, {&quot;children&quot;: [{&quot;name&quot;: &quot;Microsoft Edge Insiders&quot;, &quot;url&quot;: &quot;www.microsoftedgeinsider.com&quot;}, {&quot;name&quot;: &quot;Microsoft Edge&quot;, &quot;url&quot;: &quot;www.microsoft.com/windows/microsoft-edge&quot;}], &quot;name&quot;: &quot;Microsoft Edge links&quot;}]"/>`                               |

## <a name="configure-microsoft-edge-in-intune-using-admx-ingestion"></a>ADMX 수집을 사용하여 Intune에서 Microsoft Edge 구성

관리 템플릿 프로필을 사용하여 Microsoft Edge Microsoft Intune 방법은 관리 템플릿 프로필을 사용하는 것입니다. 이 프로필에 대한 설명은 [Configure Microsoft Edge policy settings with Microsoft Intune.](./configure-edge-with-intune.md) Intune의 Microsoft Edge 관리 템플릿에서 현재 사용할 수 없는 정책을 평가하려면 [Intune의](/intune/configuration/custom-settings-windows-10)Microsoft Edge 장치에 대한 사용자 지정 설정을 사용하여 정책을 Windows 10 수 있습니다.

이 섹션에서는 다음 방법을 설명합니다.

1. [Microsoft Edge ADMX 파일을 Intune으로 수집](#ingest-the-microsoft-edge-admx-file-into-intune)
2. [Intune에서 사용자 지정 OMA-URI를 사용하여 정책 설정](#set-a-policy-using-custom-oma-uri-in-intune)

> [!IMPORTANT]
> 모범 사례는 사용자 지정 OMA-URI 프로필과 관리 템플릿 프로필을 사용하여 Intune에서 동일한 Microsoft Edge 설정을 구성하지 않는 것입니다. 사용자 지정 OMA-URI와 관리 템플릿 프로필을 모두 사용하여 동일한 정책을 배포하지만 값이 다른 경우 사용자는 예기치 않은 결과를 얻게 됩니다. 관리 템플릿 프로필을 사용하기 전에 OMA-URI 프로필을 제거하는 것이 가장 좋습니다.

### <a name="ingest-the-microsoft-edge-admx-file-into-intune"></a>Microsoft Edge ADMX 파일을 Intune으로 수집

이 섹션에서는 Microsoft Edge 관리 템플릿(**msedge.admx** 파일)을 Intune으로 수집하는 방법을 설명합니다.

> [!WARNING]
> 파일을 수집하기 전에 ADMX 파일을 수정하지 마세요.

ADMX 파일을 수집하려면 다음 단계를 수행합니다.

1. [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)에서 Microsoft Edge 정책 템플릿 파일(MicrosoftEdgePolicyTemplates.cab)을 다운로드하고 내용을 추출합니다. 수집하려는 파일은 **msedge.admx**입니다.
2. [Microsoft Azure portal](https://portal.azure.com)에 로그인합니다.
3. _모든 서비스_에서 **Intune**을 선택하거나 포털 검색 상자에서 Intune을 검색합니다.
4. _Microsoft Intune - 개요_에서 **장치 구성** | **프로필**을 선택합니다.
5. 위쪽 명령 모음에서 **+ 프로필 만들기**를 선택합니다.

   ![장치 프로필 만들기](./media/edge-cfg-with-mdm/configure-edge-mdm-intune-create-profile.png)

6. 다음 프로필 정보를 입력합니다.

   - **이름**: 설명하는 이름을 입력합니다. 이 예에서는 "Microsoft Edge ADMX ingested configuration"을 선택합니다.
   - **설명**: 프로필에 대한 선택적 설명을 입력합니다.
   - **플랫폼**: "Windows 10 이상"을 선택합니다.
   - **프로필 유형**: "사용자 지정"을 선택합니다.

7. **사용자 지정 OMA-URI 설정**에서 **추가**를 클릭하여 ADMX 수집을 추가합니다.

   ![OMA-URI에 대한 수집 추가](./media/edge-cfg-with-mdm/configure-edge-mdm-intune-create-profile-add-omauri.png)

8. **행 추가**에서 다음 정보를 입력합니다.

   - **이름**: 설명하는 이름을 입력합니다. 이 예에서는 "Microsoft Edge ADMX ingestion"을 사용합니다.
   - **설명**: 설정에 대한 선택적 설명을 입력합니다.
   - **OMA-URI**: "*./Device/Vendor/MSFT/Policy/ConfigOperations/ADMXInstall/Edge/Policy/EdgeAdmx*"를 입력합니다.
   - **데이터 형식**: "문자열"을 선택합니다.
   - **값**: **데이터 형식**을 선택하면 이 입력 영역이 표시됩니다. 1단계에서 추출한 Microsoft Edge 정책 템플릿 파일에서 msedge.admx 파일을 엽니다. msedge.admx 파일의 **모든 텍스트**를 복사하여 다음 스크린샷에 표시된 **값** 텍스트 영역에 붙여넣습니다.

        ![ADMX 수집 추가](./media/edge-cfg-with-mdm/configure-edge-intune-mdm-omauri-addrow-ingest.png)

   - **확인**을 클릭합니다.

9. **사용자 지정 OMA-URI 설정**에서 **확인**을 클릭합니다.
10. **프로필 만들기**에서 **만들기**를 클릭합니다. 다음 스크린샷은 새로 만든 프로필에 대한 정보를 보여 줍니다.

    ![새 장치 프로필 정보 ](./media/edge-cfg-with-mdm/configure-edge-mdm-intune-create-profile-done.png)

<!--
> [!NOTE]
> You can use the preceding steps to ingest the msedgeupate.admx policy template file.
-->
### <a name="set-a-policy-using-custom-oma-uri-in-intune"></a>Intune에서 사용자 지정 OMA-URI를 사용하여 정책 설정

> [!NOTE]
> 이 섹션의 단계를 사용하기 전에 [Microsoft Edge ADMX 파일을 Intune으로 수집](#ingest-the-microsoft-edge-admx-file-into-intune)에 설명된 단계를 완료해야 합니다.

1. [Microsoft Azure portal](https://portal.azure.com)에 로그인합니다.
2. _모든 서비스_에서 **Intune**을 선택하거나 포털 검색 상자에서 Intune을 검색합니다.
3. **Intune**>**장치 구성**>**프로필**로 이동합니다.
4. "Microsoft Edge ADMX ingested configuration" 프로필 또는 프로필에 사용한 이름을 선택합니다.
5. Microsoft Edge 정책 설정을 추가하려면 **사용자 지정 OMA-URI 설정**을 열어야 합니다. **관리**에서 **속성**, **설정**을 차례로 클릭합니다.

    ![프로필 설정 구성](./media/edge-cfg-with-mdm/configure-edge-mdm-intune-add-policy-settings.png)

6. **사용자 지정 OMA-URI 설정**에서 **추가**를 클릭합니다.

    ![OMA-URI 설정에 행 추가](./media/edge-cfg-with-mdm/configure-edge-mdm-intune-add-policy-settings-add-row.png)

7. **행 추가**에서 다음 정보를 입력합니다.

   - **이름**: 설명하는 이름을 입력합니다. 구성하려는 정책 이름을 사용하는 것이 좋습니다. 이 예에서는 "ShowHomeButton"을 사용합니다.
   - **설명**(선택 사항): 설정에 대한 설명을 입력합니다.
   - **OMA-URI**: 정책에 대한 OMA-URI를 입력합니다. 예를 들어 "ShowHomeButton" 정책의 경우 다음 문자열을 사용합니다. "*./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Startup/ShowHomeButton*"
   - **데이터 형식**: 정책 설정 데이터 형식을 선택합니다. "ShowHomeButton" 정책의 경우 "문자열"을 사용합니다.
   - **값**: 정책에 대해 구성하려는 설정을 입력합니다. "ShowHomeButton" 예의 경우 \<enabled/>을(를) 입력합니다. 다음 스크린샷에서는 정책을 구성하기 위한 옵션을 보여 줍니다.

        ![행 추가, 사용자 지정 OMA-URI 설정](./media/edge-cfg-with-mdm/configure-edge-mdm-custom-omauri-setting.png)

   - **확인**을 클릭합니다.

8. **사용자 지정 OMA-URI 설정**에서 **확인**을 클릭합니다.
9. "**Microsoft Edge ADMX ingested configuration - 속성**" 프로필(또는 사용한 이름)에서 **저장**을 클릭합니다.

프로필을 만들고 속성을 설정한 후에는 [Microsoft Intune에서 프로필을 할당](/intune/configuration/device-profile-assign)해야 합니다.

#### <a name="confirm-that-the-policy-was-set"></a>정책이 설정되었는지 확인

다음 단계를 사용하여 Microsoft Edge 정책이 사용자가 만든 프로필을 사용하는지 확인합니다. (Microsoft Intune이 "Microsoft Edge ADMX ingested configuration" 프로필 예에서 할당한 장치에 정책을 전파하도록 기다립니다.)

1. Microsoft Edge를 열고 *edge://policy*로 이동합니다.
2. **정책** 페이지에서 프로필에 설정된 정책이 나열되는지 확인합니다.
3. 정책이 표시되지 않는 경우 [Windows 10에서 MDM 오류 진단](/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10) 또는 [정책 설정 문제 해결](#troubleshoot-a-policy-setting)을 참조하세요.

#### <a name="troubleshoot-a-policy-setting"></a>정책 설정 문제 해결

Microsoft Edge 정책이 적용되지 않는 경우 다음 단계를 시도해 보세요.

대상 장치( Microsoft Intune에서 프로필을 할당한 장치)에서 *edge://policy* 페이지를 열고 정책을 검색합니다. *edge://policy* 페이지에 정책이 없으면 다음을 시도해 보세요.

- 정책이 레지스트리에 있고 올바른지 확인합니다. 대상 장치에서 Windows 10 레지스트리 편집기를 엽니다(**Windows 키 + r**을 누르고 "*regedit*"를 입력한 다음 **Enter** 키를 누름). *\Software\Policies\ Microsoft\Edge* 경로에 정책이 올바르게 정의되어 있는지 확인합니다. 예상한 경로에서 정책을 찾지 못하면 정책이 장치에 올바르게 푸시되지 않은 것입니다.
- OMA-URI 경로가 올바른지, 값이 유효한 XML 문자열인지 확인합니다. 이러한 두 가지 중 하나가 올바르지 않으면 정책을 대상 장치로 푸시할 수 없습니다.

더 많은 문제 해결 팁은 [Microsoft Intune 설정](/intune/fundamentals/setup-steps) 및 [장치 동기화](/intune/remote-actions/device-sync)를 참조하세요.

## <a name="see-also"></a>기타 참조

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [Microsoft Intune을 사용하여 Microsoft Edge 정책 설정 구성](./configure-edge-with-intune.md)
- [모바일 장치 관리](/windows/client-management/mdm/)
- [Intune에서 Windows 10 장치용 사용자 지정 설정 사용](/intune/configuration/custom-settings-windows-10)
- [Win32 및 데스크톱 브리지 앱 정책 구성](/windows/client-management/mdm/win32-and-centennial-app-policy-configuration)
- [ADMX 지원 정책 이해](/windows/client-management/mdm/understanding-admx-backed-policies)