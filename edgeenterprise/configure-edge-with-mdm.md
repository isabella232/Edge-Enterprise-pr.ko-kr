---
title: 모바일 장치 관리를 사용하여 Microsoft Edge 구성
ms.author: kvice
author: dan-wesley
manager: laurawi
ms.date: 04/06/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 모바일 장치 관리를 사용하여 Microsoft Edge를 구성합니다.
ms.openlocfilehash: a24e6d171707cdc02b6dbecb573e1238f1273426
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2021
ms.locfileid: "11617608"
---
# <a name="configure-microsoft-edge-using-mobile-device-management"></a><span data-ttu-id="4d2de-103">모바일 장치 관리를 사용하여 Microsoft Edge 구성</span><span class="sxs-lookup"><span data-stu-id="4d2de-103">Configure Microsoft Edge using Mobile Device Management</span></span>

<span data-ttu-id="4d2de-104">이 문서에서는 [ADMX 수집](/windows/client-management/mdm/win32-and-centennial-app-policy-configuration)을 통해 [MDM(모바일 장치 관리)](/windows/client-management/mdm/)을 사용하여 Windows 10에서 Microsoft Edge를 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-104">This article explains how to configure Microsoft Edge on Windows 10 using [Mobile Device Management (MDM)](/windows/client-management/mdm/) by means of [ADMX Ingestion](/windows/client-management/mdm/win32-and-centennial-app-policy-configuration).</span></span> <span data-ttu-id="4d2de-105">이 문서에서는 다음 방법도 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-105">This article also describes:</span></span>

- <span data-ttu-id="4d2de-106">Microsoft Edge 정책에 대한 [OMA-URI(Open Mobile Alliance - Uniform Resource Identifier)를 만드는](#create-an-oma-uri-for-microsoft-edge-policies) 방법.</span><span class="sxs-lookup"><span data-stu-id="4d2de-106">How to [create Open Mobile Alliance Uniform Resource Identifier (OMA-URI) for Microsoft Edge policies](#create-an-oma-uri-for-microsoft-edge-policies).</span></span>
- <span data-ttu-id="4d2de-107">[ADMX 수집 및 사용자 지정 OMA-URI를 사용하여 Intune에서 Microsoft Edge를 구성](#configure-microsoft-edge-in-intune-using-admx-ingestion)하는 방법.</span><span class="sxs-lookup"><span data-stu-id="4d2de-107">How to [configure Microsoft Edge in Intune using ADMX ingestion and custom OMA-URI](#configure-microsoft-edge-in-intune-using-admx-ingestion).</span></span>

> [!NOTE]
> <span data-ttu-id="4d2de-108">이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-108">This article applies to Microsoft Edge version 77 or later.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4d2de-109">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="4d2de-109">Prerequisites</span></span>

<span data-ttu-id="4d2de-110">다음 최소 시스템 요구 사항을 충족하는 Windows 10:</span><span class="sxs-lookup"><span data-stu-id="4d2de-110">Windows 10, with the following minimum system requirements:</span></span>

- <span data-ttu-id="4d2de-111">[KB4512941](https://support.microsoft.com/help/4512941/) 및 [KB4517211](https://support.microsoft.com/help/4517211/)이 설치된 Windows 10, 버전 1903</span><span class="sxs-lookup"><span data-stu-id="4d2de-111">Windows 10, version 1903 with [KB4512941](https://support.microsoft.com/help/4512941/) and [KB4517211](https://support.microsoft.com/help/4517211/) installed</span></span>
- <span data-ttu-id="4d2de-112">[KB4512534](https://support.microsoft.com/help/4512534/) 및 [KB4520062](https://support.microsoft.com/help/4520062/)이 설치된 Windows 10, 버전 1809</span><span class="sxs-lookup"><span data-stu-id="4d2de-112">Windows 10, version 1809 with [KB4512534](https://support.microsoft.com/help/4512534/) and [KB4520062](https://support.microsoft.com/help/4520062/) installed</span></span>
- <span data-ttu-id="4d2de-113">[KB4512509](https://support.microsoft.com/help/4512509/) 및 [KB4519978](https://support.microsoft.com/help/4519978)이 설치된 Windows 10, 버전 1803</span><span class="sxs-lookup"><span data-stu-id="4d2de-113">Windows 10, version 1803 with [KB4512509](https://support.microsoft.com/help/4512509/) and [KB4519978](https://support.microsoft.com/help/4519978) installed</span></span>
- <span data-ttu-id="4d2de-114">[KB4516071](https://support.microsoft.com/help/4516071/) 및 [KB4520006](https://support.microsoft.com/help/4520006)이 설치된 Windows 10, 버전 1709</span><span class="sxs-lookup"><span data-stu-id="4d2de-114">Windows 10, version 1709 with [KB4516071](https://support.microsoft.com/help/4516071/) and [KB4520006](https://support.microsoft.com/help/4520006) installed</span></span>

## <a name="overview"></a><span data-ttu-id="4d2de-115">개요</span><span class="sxs-lookup"><span data-stu-id="4d2de-115">Overview</span></span>

<span data-ttu-id="4d2de-116">기본 EMM(엔터프라이즈 이동성 관리)이 포함된 MDM 또는[ADMX 수집](/windows/client-management/mdm/win32-and-centennial-app-policy-configuration)을 지원하는 MDM 공급자를 사용하여 Windows 10에서 Microsoft Edge를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-116">You can configure Microsoft Edge on Windows 10 using MDM with your preferred Enterprise Mobility Management (EMM) or MDM provider that supports [ADMX Ingestion](/windows/client-management/mdm/win32-and-centennial-app-policy-configuration).</span></span>

<span data-ttu-id="4d2de-117">MDM으로 Microsoft Edge를 구성하는 과정은 다음 두 부분으로 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-117">Configuring Microsoft Edge with MDM is a two part process:</span></span>

1. <span data-ttu-id="4d2de-118">Microsoft Edge ADMX 파일을 EMM 또는 MDM 공급자로 수집.</span><span class="sxs-lookup"><span data-stu-id="4d2de-118">Ingesting the Microsoft Edge ADMX file into your EMM or MDM provider.</span></span> <span data-ttu-id="4d2de-119">ADMX 파일을 수집하는 방법에 대한 지침은 공급자를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4d2de-119">See your provider for instructions on how to ingest an ADMX file.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4d2de-120">Microsoft Intune의 경우 [ADMX 수집을 사용하여 Intune에서 Microsoft Edge 구성](#configure-microsoft-edge-in-intune-using-admx-ingestion)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4d2de-120">For Microsoft Intune, see [Configure Microsoft Edge in Intune using ADMX ingestion](#configure-microsoft-edge-in-intune-using-admx-ingestion).</span></span>

2. <span data-ttu-id="4d2de-121">[Microsoft Edge 정책에 대한 OMA-URI 만들기](#create-an-oma-uri-for-microsoft-edge-policies)</span><span class="sxs-lookup"><span data-stu-id="4d2de-121">[Creating an OMA-URI for a Microsoft Edge policy](#create-an-oma-uri-for-microsoft-edge-policies).</span></span>

## <a name="create-an-oma-uri-for-microsoft-edge-policies"></a><span data-ttu-id="4d2de-122">Microsoft Edge 정책에 대한 OMA-URI 만들기</span><span class="sxs-lookup"><span data-stu-id="4d2de-122">Create an OMA-URI for Microsoft Edge policies</span></span>

<span data-ttu-id="4d2de-123">다음 섹션에서는 OMA-URI 경로를 만들고 필수 및 권장 브라우저 정책에 대한 XML 형식의 값을 조회하고 정의하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-123">The following sections describe how to create the OMA-URI path and look up and define the value in XML format for mandatory and recommended browser polices.</span></span>

<span data-ttu-id="4d2de-124">시작하기 전에 [Microsoft Edge Enterprise landing page](https://aka.ms/EdgeEnterprise)에서 Microsoft Edge 정책 템플릿 파일(MicrosoftEdgePolicyTemplates.cab)을 다운로드하고 내용을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-124">Before you get started download the Microsoft Edge policy templates file (MicrosoftEdgePolicyTemplates.cab) from the [Microsoft Edge Enterprise landing page](https://aka.ms/EdgeEnterprise) and extract the contents.</span></span>

<span data-ttu-id="4d2de-125">OMA-URI를 정의하는 과정은 다음 세 단계로 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-125">There are three steps for defining the OMA-URI:</span></span>

1. [<span data-ttu-id="4d2de-126">OMA-URI 경로 만들기</span><span class="sxs-lookup"><span data-stu-id="4d2de-126">Create the OMA-URI path</span></span>](#create-the-oma-uri-path)
2. [<span data-ttu-id="4d2de-127">OMA-URI 데이터 형식 지정</span><span class="sxs-lookup"><span data-stu-id="4d2de-127">Specify the OMA-URI data type</span></span>](#specify-the-data-type)
3. [<span data-ttu-id="4d2de-128">OMA-URI 값 설정</span><span class="sxs-lookup"><span data-stu-id="4d2de-128">Set the OMA-URI value</span></span>](#set-the-value-for-a-browser-policy)

### <a name="create-the-oma-uri-path"></a><span data-ttu-id="4d2de-129">OMA-URI 경로 만들기</span><span class="sxs-lookup"><span data-stu-id="4d2de-129">Create the OMA-URI path</span></span>

<span data-ttu-id="4d2de-130">다음 수식을 가이드로 사용하여 OMA-URI 경로를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-130">Use the following formula as a guide for creating the OMA-URI paths.</span></span> <br/><br/>
*`./Device/Vendor/MSFT/Policy/Config/<ADMXIngestName>~Policy~<ADMXNamespace>~<ADMXCategory>/<PolicyName>`* <br/><br/>

| <span data-ttu-id="4d2de-131">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4d2de-131">Parameter</span></span>         | <span data-ttu-id="4d2de-132">설명</span><span class="sxs-lookup"><span data-stu-id="4d2de-132">Description</span></span>                                                                                   |
|-------------------|-----------------------------------------------------------------------------------------------|
| \<ADMXIngestName> | <span data-ttu-id="4d2de-133">관리 템플릿을 수집할 때 "Edge" 또는 사용자가 정의한 항목을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-133">Use "Edge" or what you defined when ingesting the administrative template.</span></span> <span data-ttu-id="4d2de-134">예를 들어 "./Device/Vendor/MSFT/Policy/ConfigOperations/ADMXInstall/MicrosoftEdge/Policy/EdgeAdmx"을 사용한 경우 "MicrosoftEdge"를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-134">For example, if you used "./Device/Vendor/MSFT/Policy/ConfigOperations/ADMXInstall/MicrosoftEdge/Policy/EdgeAdmx", then use "MicrosoftEdge".</span></span><br/><br/> <span data-ttu-id="4d2de-135">`<ADMXIngestionName>`은 ADMX 파일을 수집할 때 사용한 것과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-135">The `<ADMXIngestionName>` must match what was used when you ingested the ADMX file.</span></span> |
| \<ADMXNamespace>  | <span data-ttu-id="4d2de-136">필수 또는 권장 정책을 설정하는지 여부에 따라 "microsoft_edge" 또는 "microsoft_edge_recommended" 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-136">Either "microsoft_edge" or "microsoft_edge_recommended" depending on whether you're setting a mandatory or recommended policy.</span></span> |
| \<ADMXCategory>   | <span data-ttu-id="4d2de-137">정책의 "parentCategory"는 ADMX 파일에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-137">The "parentCategory" of the policy is defined in the ADMX file.</span></span> <span data-ttu-id="4d2de-138">정책이 그룹화되지 않은 경우(정의된 "parentCategory"가 없음) `<ADMXCategory>`를 생략합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-138">Omit the `<ADMXCategory>` if the policy isn't grouped (No "parentCategory" defined).</span></span> |
| \<PolicyName>     | <span data-ttu-id="4d2de-139">정책 이름은 [브라우저 정책 참조](./microsoft-edge-policies.md) 문서에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-139">The policy name can be found in the [Browser policy reference](./microsoft-edge-policies.md) article.</span></span> |

#### <a name="uri-path-example"></a><span data-ttu-id="4d2de-140">URI 경로 예:</span><span class="sxs-lookup"><span data-stu-id="4d2de-140">URI path example:</span></span>

<span data-ttu-id="4d2de-141">이 예에서는 `<ADMXIngestName>` 노드의 이름이 "Edge"이고 사용자가 필수 정책을 설정하는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-141">For this example, assume the `<ADMXIngestName>` node was named “Edge" and you're setting a mandatory policy.</span></span> <span data-ttu-id="4d2de-142">URI 경로는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-142">The URI path would be:</span></span><br/><br/>
*`./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~<ADMXCategory>/<PolicyName>`*

<span data-ttu-id="4d2de-143">정책이 그룹에 있지 않으면(예: DiskCacheSize) "`~<ADMXCategory>`"를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-143">If the policy isn't in a group (for example, DiskCacheSize) remove "`~<ADMXCategory>`".</span></span> <span data-ttu-id="4d2de-144">`<PolicyName>`을 정책의 이름 DiskCacheSize로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-144">Replace `<PolicyName>` with the name of the policy, DiskCacheSize.</span></span> <span data-ttu-id="4d2de-145">URI 경로는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-145">The URI path would be:</span></span><br/><br/>
*`./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge/DiskCacheSize`*

<span data-ttu-id="4d2de-146">정책이 그룹에 있는 경우 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-146">If the policy is in a group, follow these steps:</span></span>

1. <span data-ttu-id="4d2de-147">임의의 xml 편집기를 사용하여 **msedge.admx**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-147">Open **msedge.admx** with any xml editor.</span></span>
2. <span data-ttu-id="4d2de-148">설정하려는 정책 이름을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-148">Search for the policy name you want to set.</span></span> <span data-ttu-id="4d2de-149">예: "ExtensionInstallForceList".</span><span class="sxs-lookup"><span data-stu-id="4d2de-149">For example, "ExtensionInstallForceList".</span></span>
3. <span data-ttu-id="4d2de-150">*parentCategory* 요소에서 *ref* 특성의 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-150">Use the value of the *ref* attribute from the *parentCategory* element.</span></span> <span data-ttu-id="4d2de-151">예를 들어 \<parentCategory ref=" Extensions"/>에서의 "확장"이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-151">For example, "Extensions" from \<parentCategory ref=" Extensions"/>.</span></span>
4. <span data-ttu-id="4d2de-152">`<ADMXCategory>`를 *ref* 특성 값으로 대체하여 URI 경로를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-152">Replace `<ADMXCategory>` with the *ref* attribute value to construct the URI path.</span></span> <span data-ttu-id="4d2de-153">URI 경로는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-153">The URI path would be:</span></span><br/><br/>
*`/Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Extensions/ExtensionInstallForcelist`*

### <a name="specify-the-data-type"></a><span data-ttu-id="4d2de-154">데이터 형식 지정</span><span class="sxs-lookup"><span data-stu-id="4d2de-154">Specify the data type</span></span>

<span data-ttu-id="4d2de-155">OMA-URI 데이터 형식은 항상 "문자열"입니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-155">The OMA-URI data type is always “String”.</span></span>

### <a name="set-the-value-for-a-browser-policy"></a><span data-ttu-id="4d2de-156">브라우저 정책에 대한 값 설정</span><span class="sxs-lookup"><span data-stu-id="4d2de-156">Set the value for a browser policy</span></span>

<span data-ttu-id="4d2de-157">이 섹션에서는 각 데이터 형식에 대한 값을 XML 형식으로 설정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-157">This section describes how to set the value, in XML format, for each data type.</span></span> <span data-ttu-id="4d2de-158">[브라우저 정책 참조](./microsoft-edge-policies.md)로 이동하여 정책의 데이터 형식을 조회합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-158">Go to [Browser policy reference](./microsoft-edge-policies.md) to look up the data type of the policy.</span></span>

> [!NOTE]
> <span data-ttu-id="4d2de-159">부울 데이터 형식이 아닌 경우 이 값은 항상 `<enabled/>`로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-159">For non-Boolean data types, the value always starts with `<enabled/>`.</span></span>

#### <a name="boolean-data-type"></a><span data-ttu-id="4d2de-160">부울 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4d2de-160">Boolean data type</span></span>

<span data-ttu-id="4d2de-161">부울 형식인 정책에 대해서는 `<enabled/>` 또는 `<disabled/>`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-161">For policies that are Boolean types use `<enabled/>` or `<disabled/>`.</span></span>

#### <a name="integer-data-type"></a><span data-ttu-id="4d2de-162">정수 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4d2de-162">Integer data type</span></span>

<span data-ttu-id="4d2de-163">이 값은 항상 `<enabled/>` 요소로 시작하고 `<data id="[valueName]" value="[decimal value]"/>`이 뒤따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-163">The value always needs to start with the `<enabled/>` element followed by `<data id="[valueName]" value="[decimal value]"/>`.</span></span>

<span data-ttu-id="4d2de-164">새 탭 페이지에 대한 값 이름과 소수 값을 찾으려면 다음 단계를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-164">To find the value name and decimal value for a new tab page, use the following steps:</span></span>

1. <span data-ttu-id="4d2de-165">임의의 xml 편집기를 사용하여 **msedge.admx**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-165">Open **msedge.admx** with any xml editor.</span></span>
2. <span data-ttu-id="4d2de-166">이름 특성이 설정하려는 정책 이름과 일치하는 `<policy>` 요소를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-166">Search for the `<policy>` element where the name attribute matches the policy name you want to set.</span></span> <span data-ttu-id="4d2de-167">"RestoreOnStartup"의 경우 `name="RestoreOnStartup"`을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-167">For "RestoreOnStartup", search for `name="RestoreOnStartup"`.</span></span>
3. <span data-ttu-id="4d2de-168">`<elements>` 노드에서 설정하려는 값을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-168">In the `<elements>` node, find the value you want to set.</span></span>
4. <span data-ttu-id="4d2de-169">`<elements>` 노드에서 "valueName" 특성의 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-169">Use the value in the "valueName" attribute in the `<elements>` node.</span></span> <span data-ttu-id="4d2de-170">"RestoreOnStartup"의 경우 "valueName"은 "RestoreOnStartup"입니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-170">For "RestoreOnStartup" the "valueName" is "RestoreOnStartup".</span></span>
5. <span data-ttu-id="4d2de-171">`<decimal>` 노드에서 "value" 특성의 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-171">Use the value in the "value" attribute in the `<decimal>` node.</span></span> <span data-ttu-id="4d2de-172">"RestoreOnStartup"으로 새 탭 페이지를 열려면 값은 "5"입니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-172">For "RestoreOnStartup" to open the new tab page the value is "5".</span></span>

<span data-ttu-id="4d2de-173">시작 시 새 탭 페이지를 열려면 다음을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-173">To open the new tab page on startup use:</span></span><br>
`<enabled/> <data id="RestoreOnStartup" value="5"/>`

#### <a name="list-of-strings-data-type"></a><span data-ttu-id="4d2de-174">문자열 목록 데이터 형식 목록</span><span class="sxs-lookup"><span data-stu-id="4d2de-174">List of strings data type</span></span>

<span data-ttu-id="4d2de-175">이 값은 항상 `<enabled/>` 요소로 시작하고 `<data id="[listID]" value="[string 1];[string 2];[string 3]"/>`이 뒤따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-175">The value always needs to start with the `<enabled/>` element followed by `<data id="[listID]" value="[string 1];[string 2];[string 3]"/>`.</span></span>

> [!NOTE]
> <span data-ttu-id="4d2de-176">대부분의 경우 정책 이름과 일치하지만 "id=" 특성 이름은 정책 이름이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-176">The "id=" attribute name isn't the policy name, even though in most cases it matches the policy name.</span></span> <span data-ttu-id="4d2de-177">이는 ADMX 파일에 있는 \<list> node ID 특성 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-177">It's the \<list> node id attribute value, which is found in the ADMX file.</span></span>

<span data-ttu-id="4d2de-178">listID를 찾고 URL을 차단하는 값을 정의하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-178">To find the listID and define the value to block a URL, follow these steps:</span></span>

1. <span data-ttu-id="4d2de-179">임의의 xml 편집기를 사용하여 **msedge.admx**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-179">Open **msedge.admx** with any xml editor.</span></span>
2. <span data-ttu-id="4d2de-180">이름 특성이 설정하려는 정책 이름과 일치하는 `<policy>` 요소를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-180">Search for the `<policy>` element where the name attribute matches the policy name you want to set.</span></span> <span data-ttu-id="4d2de-181">"URLBlocklist"의 경우 `name="URLBlocklist"`를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-181">For "URLBlocklist", search for `name="URLBlocklist"`.</span></span>
3. <span data-ttu-id="4d2de-182">`<list> node for [listID]` 노드에서 "id" 특성의 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-182">Use the value in the "id" attribute of the `<list> node for [listID]`.</span></span>
4. <span data-ttu-id="4d2de-183">"값"은 세미콜론(;)으로 구분된 URL 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-183">The "value" is a list of URLs separated by a semicolon (;)</span></span>

<span data-ttu-id="4d2de-184">예를 들어, `contoso.com` 및 `https://ssl.server.com`에 대한 액세스를 차단하려면</span><span class="sxs-lookup"><span data-stu-id="4d2de-184">For example, to block access to `contoso.com` and `https://ssl.server.com`:</span></span><br>
`<enabled/> <data id=" URLBlocklistDesc" value="contoso.com;https://ssl.server.com"/>`

#### <a name="dictionary-or-string-data-type"></a><span data-ttu-id="4d2de-185">사전 또는 문자열 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4d2de-185">Dictionary or String data type</span></span>

<span data-ttu-id="4d2de-186">이 값은 항상 `<enabled/>`로 시작하고 `<data id="[textID]" value="[string]"/>`이 뒤따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-186">The value always needs to start with the `<enabled/>` followed by `<data id="[textID]" value="[string]"/>` .</span></span>

<span data-ttu-id="4d2de-187">textID를 찾고 로캘을 차단하는 값을 정의하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-187">To find the textID and define the value set the locale, follow these steps:</span></span>

1. <span data-ttu-id="4d2de-188">임의의 xml 편집기를 사용하여 **msedge.admx**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-188">Open **msedge.admx** with any xml editor.</span></span>
2. <span data-ttu-id="4d2de-189">이름 특성이 설정하려는 정책 이름과 일치하는 `<policy>` 요소를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-189">Search for the `<policy>` element where the name attribute matches the policy name you want to set.</span></span> <span data-ttu-id="4d2de-190">"ApplicationLocaleValue"의 경우 `name="ApplicationLocaleValue"`를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-190">For "ApplicationLocaleValue", search for `name="ApplicationLocaleValue"`.</span></span>
3. <span data-ttu-id="4d2de-191">`[textID]`에 대한 `<text>` 노드에서 "id" 특성의 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-191">Use the value in the "id" attribute of the `<text>` node for `[textID]`.</span></span>
4. <span data-ttu-id="4d2de-192">"값"을 문화 코드로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-192">Set the "value" to the culture code.</span></span>

<span data-ttu-id="4d2de-193">"ApplicationLocaleValue" 정책을 사용하여 로캘을 "es-US"로 설정하려면</span><span class="sxs-lookup"><span data-stu-id="4d2de-193">To set the locale to "es-US" with the "ApplicationLocaleValue" policy:</span></span><br>
`<enabled/> <data id="ApplicationLocaleValue" value="es-US"/>`

### <a name="create-the-oma-uri-for-a-recommended-policies"></a><span data-ttu-id="4d2de-194">권장 정책에 대한 OMA-URI를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-194">Create the OMA-URI for a recommended policies</span></span>

<span data-ttu-id="4d2de-195">권장 정책에 대한 URI 경로 정의는 구성하려는 정책에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-195">Defining the URI path for recommended policies depends on the policy you want to configure.</span></span>

#### <a name="to-define-the-uri-path-for-a-recommended-policy"></a><span data-ttu-id="4d2de-196">권장 정책에 대한 URI 경로를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="4d2de-196">To define the URI path for a recommended policy</span></span>

<span data-ttu-id="4d2de-197">URI 경로 수식(*`./Device/Vendor/MSFT/Policy/Config/<ADMXIngestName>~Policy~<ADMXNamespace>~<ADMXCategory>/<PolicyName>`*)을 사용하고 다음 단계를 수행하여 URI 경로를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-197">Use the URI path formula (*`./Device/Vendor/MSFT/Policy/Config/<ADMXIngestName>~Policy~<ADMXNamespace>~<ADMXCategory>/<PolicyName>`*) and the following steps to define the URI path:</span></span>

1. <span data-ttu-id="4d2de-198">임의의 xml 편집기를 사용하여 **msedge.admx**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-198">Open **msedge.admx** with any xml editor.</span></span>
2. <span data-ttu-id="4d2de-199">구성하려는 정책이 그룹에 없으면 4단계로 건너뛰고 경로에서 `~<ADMXCategory>`를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-199">If the policy you want to configure isn't in a group, skip to step 4 and remove `~<ADMXCategory>` from the path.</span></span>
3. <span data-ttu-id="4d2de-200">구성하려는 정책이 그룹에 있는 경우:</span><span class="sxs-lookup"><span data-stu-id="4d2de-200">If the policy you want to configure is in a group:</span></span>

   - <span data-ttu-id="4d2de-201">`<ADMXCategory>`를 조회하려면 설정하려는 정책을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-201">To look up the `<ADMXCategory>`, search for the policy you want to set.</span></span> <span data-ttu-id="4d2de-202">검색할 때 정책 이름에 "_recommended" 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-202">When searching append "_recommended" to the policy name.</span></span> <span data-ttu-id="4d2de-203">예를 들어 "RegisteredProtocolHandlers_recommended"에 대한 검색 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-203">For example, a search for "RegisteredProtocolHandlers_recommended” has the following result:</span></span>

        ```xml
         <policy class="Both" displayName="$(string.RegisteredProtocolHandlers)" explainText="$(string.RegisteredProtocolHandlers_Explain)" key="Software\Policies\Microsoft\Edge\Recommended" name="RegisteredProtocolHandlers_recommended" presentation="$(presentation.RegisteredProtocolHandlers)">
           <parentCategory ref="ContentSettings_recommended"/>
           <supportedOn ref="SUPPORTED_WIN7_V77"/>
           <elements>
             <text id="RegisteredProtocolHandlers" maxLength="1000000" valueName="RegisteredProtocolHandlers"/>
           </elements>
         </policy>
        ```

   - <span data-ttu-id="4d2de-204">`<parentCategory>` 요소에서 *ref* 특성의 값을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-204">Copy the value of the *ref* attribute from the `<parentCategory>` element.</span></span> <span data-ttu-id="4d2de-205">"ContentSettings"의 경우 `<parentCategory ref=" ContentSettings_recommended"/>`에서 "ContentSettings_recommended"를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-205">For "ContentSettings", copy "ContentSettings_recommended" from `<parentCategory ref=" ContentSettings_recommended"/>`.</span></span>
   - <span data-ttu-id="4d2de-206">URI 경로 수식에서 `<ADMXCategory>`를 *ref* 특성 값으로 대체하여 URI 경로를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-206">Replace `<ADMXCategory>` with the *ref* attribute value to construct the URI path in the URI path formula.</span></span>

4. <span data-ttu-id="4d2de-207">`<PolicyName>`은 "_recommended"가 추가된 정책의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-207">The `<PolicyName>` is the name of the policy with "_recommended" appended to it.</span></span>

#### <a name="oma-uri-path-examples-for-recommended-policies"></a><span data-ttu-id="4d2de-208">권장 정책에 대한 OMA-URI 경로 예</span><span class="sxs-lookup"><span data-stu-id="4d2de-208">OMA-URI path examples for recommended policies</span></span>

<span data-ttu-id="4d2de-209">다음 표에서는 권장 정책에 대한 OMA-URI 경로의 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-209">The following table shows examples of OMA-URI paths for recommended policies.</span></span>

|              <span data-ttu-id="4d2de-210">정책</span><span class="sxs-lookup"><span data-stu-id="4d2de-210">Policy</span></span>               |             <span data-ttu-id="4d2de-211">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="4d2de-211">OMA-URI</span></span>                      |
|-----------------------------------|------------------------------------------|
| [<span data-ttu-id="4d2de-212">RegisteredProtocolHandlers</span><span class="sxs-lookup"><span data-stu-id="4d2de-212">RegisteredProtocolHandlers</span></span>](./microsoft-edge-policies.md#registeredprotocolhandlers)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~ContentSettings_recommended/RegisteredProtocolHandlers_recommended`                        |
| [<span data-ttu-id="4d2de-213">PasswordManagerEnabled</span><span class="sxs-lookup"><span data-stu-id="4d2de-213">PasswordManagerEnabled</span></span>](./microsoft-edge-policies.md#passwordmanagerenabled)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~PasswordManager_recommended/PasswordManagerEnabled_recommended`                        |
| [<span data-ttu-id="4d2de-214">PrintHeaderFooter</span><span class="sxs-lookup"><span data-stu-id="4d2de-214">PrintHeaderFooter</span></span>](./microsoft-edge-policies.md#printheaderfooter)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~Printing_recommended/PrintHeaderFooter_recommended`                        |
| [<span data-ttu-id="4d2de-215">SmartScreenEnabled</span><span class="sxs-lookup"><span data-stu-id="4d2de-215">SmartScreenEnabled</span></span>](./microsoft-edge-policies.md#smartscreenenabled)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~SmartScreen_recommended/SmartScreenEnabled_recommended`                        |
| [<span data-ttu-id="4d2de-216">HomePageLocation</span><span class="sxs-lookup"><span data-stu-id="4d2de-216">HomePageLocation</span></span>](./microsoft-edge-policies.md#homepagelocation)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~Startup_recommended/HomepageLocation_recommended`                        |
| [<span data-ttu-id="4d2de-217">ShowHomeButton</span><span class="sxs-lookup"><span data-stu-id="4d2de-217">ShowHomeButton</span></span>](./microsoft-edge-policies.md#showhomebutton)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~Startup_recommended/ShowHomeButton_recommended`                        |
| [<span data-ttu-id="4d2de-218">FavoritesBarEnabled</span><span class="sxs-lookup"><span data-stu-id="4d2de-218">FavoritesBarEnabled</span></span>](./microsoft-edge-policies.md#favoritesbarenabled)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~/FavoritesBarEnabled_recommended`                        |

### <a name="oma-uri-examples"></a><span data-ttu-id="4d2de-219">OMA-URI 예</span><span class="sxs-lookup"><span data-stu-id="4d2de-219">OMA-URI examples</span></span>

<span data-ttu-id="4d2de-220">URI 경로, 형식 및 예제 값이 포함된 OMA-URI 예입니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-220">OMA-URI examples with their URI path, type, and an example value.</span></span>

#### <a name="boolean-data-type-examples"></a><span data-ttu-id="4d2de-221">부울 데이터 형식 예</span><span class="sxs-lookup"><span data-stu-id="4d2de-221">Boolean data type examples</span></span>

*<span data-ttu-id="4d2de-222">[ShowHomeButton](./microsoft-edge-policies.md#showhomebutton):</span><span class="sxs-lookup"><span data-stu-id="4d2de-222">[ShowHomeButton](./microsoft-edge-policies.md#showhomebutton):</span></span>*

| <span data-ttu-id="4d2de-223">필드</span><span class="sxs-lookup"><span data-stu-id="4d2de-223">Field</span></span>   | <span data-ttu-id="4d2de-224">값</span><span class="sxs-lookup"><span data-stu-id="4d2de-224">Value</span></span>                                                                                |
|---------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="4d2de-225">이름</span><span class="sxs-lookup"><span data-stu-id="4d2de-225">Name</span></span>    | <span data-ttu-id="4d2de-226">Microsoft Edge: ShowHomeButton</span><span class="sxs-lookup"><span data-stu-id="4d2de-226">Microsoft Edge: ShowHomeButton</span></span>                                                       |
| <span data-ttu-id="4d2de-227">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="4d2de-227">OMA-URI</span></span> | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Startup/ShowHomeButton` |
| <span data-ttu-id="4d2de-228">형식</span><span class="sxs-lookup"><span data-stu-id="4d2de-228">type</span></span>    | <span data-ttu-id="4d2de-229">문자열</span><span class="sxs-lookup"><span data-stu-id="4d2de-229">String</span></span>                                                                               |
| <span data-ttu-id="4d2de-230">값</span><span class="sxs-lookup"><span data-stu-id="4d2de-230">Value</span></span>   | `<enabled/>`                                                                          |

*<span data-ttu-id="4d2de-231">[DefaultSearchProviderEnabled](./microsoft-edge-policies.md#defaultsearchproviderenabled):</span><span class="sxs-lookup"><span data-stu-id="4d2de-231">[DefaultSearchProviderEnabled](./microsoft-edge-policies.md#defaultsearchproviderenabled):</span></span>*

| <span data-ttu-id="4d2de-232">필드</span><span class="sxs-lookup"><span data-stu-id="4d2de-232">Field</span></span>   | <span data-ttu-id="4d2de-233">값</span><span class="sxs-lookup"><span data-stu-id="4d2de-233">Value</span></span>                                                                                |
|---------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="4d2de-234">이름</span><span class="sxs-lookup"><span data-stu-id="4d2de-234">Name</span></span>    | <span data-ttu-id="4d2de-235">Microsoft Edge: DefaultSearchProviderEnabled</span><span class="sxs-lookup"><span data-stu-id="4d2de-235">Microsoft Edge: DefaultSearchProviderEnabled</span></span>                                         |
| <span data-ttu-id="4d2de-236">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="4d2de-236">OMA-URI</span></span> | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~DefaultSearchProvider/DefaultSearchProviderEnabled`    |
| <span data-ttu-id="4d2de-237">형식</span><span class="sxs-lookup"><span data-stu-id="4d2de-237">type</span></span>    | <span data-ttu-id="4d2de-238">문자열</span><span class="sxs-lookup"><span data-stu-id="4d2de-238">String</span></span>                                                                               |
| <span data-ttu-id="4d2de-239">값</span><span class="sxs-lookup"><span data-stu-id="4d2de-239">Value</span></span>   | `<disable/>`                                                                          |

### <a name="integer-data-type-examples"></a><span data-ttu-id="4d2de-240">정수 데이터 형식 예</span><span class="sxs-lookup"><span data-stu-id="4d2de-240">Integer data type examples</span></span>

*<span data-ttu-id="4d2de-241">[AutoImportAtFirstRun](./microsoft-edge-policies.md#autoimportatfirstrun):</span><span class="sxs-lookup"><span data-stu-id="4d2de-241">[AutoImportAtFirstRun](./microsoft-edge-policies.md#autoimportatfirstrun):</span></span>*

| <span data-ttu-id="4d2de-242">필드</span><span class="sxs-lookup"><span data-stu-id="4d2de-242">Field</span></span>   | <span data-ttu-id="4d2de-243">값</span><span class="sxs-lookup"><span data-stu-id="4d2de-243">Value</span></span>                                                                                |
|---------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="4d2de-244">이름</span><span class="sxs-lookup"><span data-stu-id="4d2de-244">Name</span></span>    | <span data-ttu-id="4d2de-245">Microsoft Edge: AutoImportAtFirstRun</span><span class="sxs-lookup"><span data-stu-id="4d2de-245">Microsoft Edge: AutoImportAtFirstRun</span></span>                                                 |
| <span data-ttu-id="4d2de-246">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="4d2de-246">OMA-URI</span></span> | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge/AutoImportAtFirstRun`   |
| <span data-ttu-id="4d2de-247">형식</span><span class="sxs-lookup"><span data-stu-id="4d2de-247">type</span></span>    | <span data-ttu-id="4d2de-248">문자열</span><span class="sxs-lookup"><span data-stu-id="4d2de-248">String</span></span>                                                                               |
| <span data-ttu-id="4d2de-249">값</span><span class="sxs-lookup"><span data-stu-id="4d2de-249">Value</span></span>   | `<enabled/><data id="AutoImportAtFirstRun" value="1"/>`                             |

*<span data-ttu-id="4d2de-250">[DefaultImagesSetting](./microsoft-edge-policies.md#defaultimagessetting):</span><span class="sxs-lookup"><span data-stu-id="4d2de-250">[DefaultImagesSetting](./microsoft-edge-policies.md#defaultimagessetting):</span></span>*

| <span data-ttu-id="4d2de-251">필드</span><span class="sxs-lookup"><span data-stu-id="4d2de-251">Field</span></span>   | <span data-ttu-id="4d2de-252">값</span><span class="sxs-lookup"><span data-stu-id="4d2de-252">Value</span></span>                                                                                |
|---------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="4d2de-253">이름</span><span class="sxs-lookup"><span data-stu-id="4d2de-253">Name</span></span>    | <span data-ttu-id="4d2de-254">Microsoft Edge: DefaultImagesSetting</span><span class="sxs-lookup"><span data-stu-id="4d2de-254">Microsoft Edge: DefaultImagesSetting</span></span>                                                 |
| <span data-ttu-id="4d2de-255">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="4d2de-255">OMA-URI</span></span> | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~ContentSettings/DefaultImagesSetting`    |
| <span data-ttu-id="4d2de-256">형식</span><span class="sxs-lookup"><span data-stu-id="4d2de-256">type</span></span>    | <span data-ttu-id="4d2de-257">문자열</span><span class="sxs-lookup"><span data-stu-id="4d2de-257">String</span></span>                                                                               |
| <span data-ttu-id="4d2de-258">값</span><span class="sxs-lookup"><span data-stu-id="4d2de-258">Value</span></span>   | `<enabled/><data id="DefaultImagesSetting" value="2"/>`                             |

*<span data-ttu-id="4d2de-259">[DiskCacheSize](./microsoft-edge-policies.md#diskcachesize):</span><span class="sxs-lookup"><span data-stu-id="4d2de-259">[DiskCacheSize](./microsoft-edge-policies.md#diskcachesize):</span></span>*

| <span data-ttu-id="4d2de-260">필드</span><span class="sxs-lookup"><span data-stu-id="4d2de-260">Field</span></span>   | <span data-ttu-id="4d2de-261">값</span><span class="sxs-lookup"><span data-stu-id="4d2de-261">Value</span></span>                                                                                |
|---------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="4d2de-262">이름</span><span class="sxs-lookup"><span data-stu-id="4d2de-262">Name</span></span>    | <span data-ttu-id="4d2de-263">Microsoft Edge: DiskCacheSize</span><span class="sxs-lookup"><span data-stu-id="4d2de-263">Microsoft Edge: DiskCacheSize</span></span>                                                        |
| <span data-ttu-id="4d2de-264">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="4d2de-264">OMA-URI</span></span> | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge/DiskCacheSize`        |
| <span data-ttu-id="4d2de-265">형식</span><span class="sxs-lookup"><span data-stu-id="4d2de-265">type</span></span>    | <span data-ttu-id="4d2de-266">문자열</span><span class="sxs-lookup"><span data-stu-id="4d2de-266">String</span></span>                                                                               |
| <span data-ttu-id="4d2de-267">값</span><span class="sxs-lookup"><span data-stu-id="4d2de-267">Value</span></span>   | `<enabled/><data id="DiskCacheSize" value="1000000"/>`                               |

#### <a name="list-of-strings-data-type-examples"></a><span data-ttu-id="4d2de-268">문자열 목록 데이터 형식 예</span><span class="sxs-lookup"><span data-stu-id="4d2de-268">List of strings data type examples</span></span>
<!--
*[NotificationsAllowedForUrls](./microsoft-edge-policies.md#NotificationsAllowedForUrls):*

| Field   | Value                                                                                |
|---------|--------------------------------------------------------------------------------------|
| Name    | Microsoft Edge: NotificationsAllowedForUrls                                          |
| OMA-URI | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~ContentSettings/NotificationsAllowedForUrls`    |
| Type    | String                                                                               |
| Value   | `<enabled/><data id="NotificationsAllowedForUrlsDesc" value="https://www.contoso.com"/>`<br>For multiple list items: `<data id="NotificationsAllowedForUrlsDesc" value="https://www.contoso.com;[*.]contoso.edu"/>`                           |
-->
*<span data-ttu-id="4d2de-269">[RestoreOnStartupURLS](./microsoft-edge-policies.md#restoreonstartupurls):</span><span class="sxs-lookup"><span data-stu-id="4d2de-269">[RestoreOnStartupURLS](./microsoft-edge-policies.md#restoreonstartupurls):</span></span>*

| <span data-ttu-id="4d2de-270">필드</span><span class="sxs-lookup"><span data-stu-id="4d2de-270">Field</span></span>   | <span data-ttu-id="4d2de-271">값</span><span class="sxs-lookup"><span data-stu-id="4d2de-271">Value</span></span>                                                                                |
|---------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="4d2de-272">이름</span><span class="sxs-lookup"><span data-stu-id="4d2de-272">Name</span></span>    | <span data-ttu-id="4d2de-273">Microsoft Edge: RestoreOnStartupURLS</span><span class="sxs-lookup"><span data-stu-id="4d2de-273">Microsoft Edge: RestoreOnStartupURLS</span></span>                                                 |
| <span data-ttu-id="4d2de-274">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="4d2de-274">OMA-URI</span></span> | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Startup/RestoreOnStartupURLs`    |
| <span data-ttu-id="4d2de-275">형식</span><span class="sxs-lookup"><span data-stu-id="4d2de-275">Type</span></span>    | <span data-ttu-id="4d2de-276">문자열</span><span class="sxs-lookup"><span data-stu-id="4d2de-276">String</span></span>                                                                               |
| <span data-ttu-id="4d2de-277">값</span><span class="sxs-lookup"><span data-stu-id="4d2de-277">Value</span></span>   | `<enabled/><data id="RestoreOnStartupURLsDesc" value="1&#xF000;http://www.bing.com"/>`<br><span data-ttu-id="4d2de-278">다중 목록 항목의 경우:</span><span class="sxs-lookup"><span data-stu-id="4d2de-278">For multiple list items:</span></span> `<enabled/><data id="RestoreOnStartupURLsDesc" value="1&#xF000;http://www.bing.com&#xF000;2&#xF000;http://www.microsoft.com"/>`  |

*<span data-ttu-id="4d2de-279">[ExtensionInstallForcelist](./microsoft-edge-policies.md#extensioninstallforcelist):</span><span class="sxs-lookup"><span data-stu-id="4d2de-279">[ExtensionInstallForcelist](./microsoft-edge-policies.md#extensioninstallforcelist):</span></span>*

| <span data-ttu-id="4d2de-280">필드</span><span class="sxs-lookup"><span data-stu-id="4d2de-280">Field</span></span>   | <span data-ttu-id="4d2de-281">값</span><span class="sxs-lookup"><span data-stu-id="4d2de-281">Value</span></span>                                                                                |
|---------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="4d2de-282">이름</span><span class="sxs-lookup"><span data-stu-id="4d2de-282">Name</span></span>    | <span data-ttu-id="4d2de-283">Microsoft Edge: ExtensionInstallForcelist</span><span class="sxs-lookup"><span data-stu-id="4d2de-283">Microsoft Edge: ExtensionInstallForcelist</span></span>                                            |
| <span data-ttu-id="4d2de-284">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="4d2de-284">OMA-URI</span></span> | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Extensions/ExtensionInstallForcelist`    |
| <span data-ttu-id="4d2de-285">형식</span><span class="sxs-lookup"><span data-stu-id="4d2de-285">Type</span></span>    | <span data-ttu-id="4d2de-286">문자열</span><span class="sxs-lookup"><span data-stu-id="4d2de-286">String</span></span>                                                                               |
| <span data-ttu-id="4d2de-287">값</span><span class="sxs-lookup"><span data-stu-id="4d2de-287">Value</span></span>   | `<enabled/><data id="ExtensionInstallForcelistDesc" value="1&#xF000;gbchcmhmhahfdphkhkmpfmihenigjmpp;https://extensionwebstorebase.edgesv.net/v1/crx"/>`                               |

#### <a name="dictionary-and-string-data-type-example"></a><span data-ttu-id="4d2de-288">사전 및 문자열 데이터 형식 예</span><span class="sxs-lookup"><span data-stu-id="4d2de-288">Dictionary and String data type example</span></span>

*<span data-ttu-id="4d2de-289">[ProxyMode](./microsoft-edge-policies.md#proxymode):</span><span class="sxs-lookup"><span data-stu-id="4d2de-289">[ProxyMode](./microsoft-edge-policies.md#proxymode):</span></span>*

| <span data-ttu-id="4d2de-290">필드</span><span class="sxs-lookup"><span data-stu-id="4d2de-290">Field</span></span>   | <span data-ttu-id="4d2de-291">값</span><span class="sxs-lookup"><span data-stu-id="4d2de-291">Value</span></span>                                                                                |
|---------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="4d2de-292">이름</span><span class="sxs-lookup"><span data-stu-id="4d2de-292">Name</span></span>    | <span data-ttu-id="4d2de-293">Microsoft Edge: ProxyMode</span><span class="sxs-lookup"><span data-stu-id="4d2de-293">Microsoft Edge: ProxyMode</span></span>                                                            |
| <span data-ttu-id="4d2de-294">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="4d2de-294">OMA-URI</span></span> | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~ProxyMode/ProxyMode`  |
| <span data-ttu-id="4d2de-295">형식</span><span class="sxs-lookup"><span data-stu-id="4d2de-295">Type</span></span>    | <span data-ttu-id="4d2de-296">문자열</span><span class="sxs-lookup"><span data-stu-id="4d2de-296">String</span></span>                                                                               |
| <span data-ttu-id="4d2de-297">값</span><span class="sxs-lookup"><span data-stu-id="4d2de-297">Value</span></span>   | `<enabled/><data id="ProxyMode" value="auto_detect"/>`                               |

## <a name="configure-microsoft-edge-in-intune-using-admx-ingestion"></a><span data-ttu-id="4d2de-298">ADMX 수집을 사용하여 Intune에서 Microsoft Edge 구성</span><span class="sxs-lookup"><span data-stu-id="4d2de-298">Configure Microsoft Edge in Intune using ADMX ingestion</span></span>

<span data-ttu-id="4d2de-299">Microsoft Intune을 사용하여 Microsoft Edge를 구성하는 데 권장되는 방법은 [Microsoft Intune을 사용하여 Microsoft Edge 정책 설정 구성](./configure-edge-with-intune.md)에 설명된 대로 관리 템플릿 프로필을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-299">The recommended way to configure Microsoft Edge with Microsoft Intune is to use the Administrative Templates profile as described in [Configure Microsoft Edge policy settings with Microsoft Intune](./configure-edge-with-intune.md).</span></span> <span data-ttu-id="4d2de-300">Intune의 Microsoft Edge 관리 템플릿에서 현재 사용할 수 없는 정책을 평가하려는 경우 [Intune의 Windows 10 장치에 대한 사용자 지정 설정](/intune/configuration/custom-settings-windows-10)을 사용하여 Microsoft Edge를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-300">If you want to evaluate a policy that is currently not available in the Microsoft Edge Administrative Templates in Intune you can configure Microsoft Edge using  [custom settings for Windows 10 devices in Intune](/intune/configuration/custom-settings-windows-10).</span></span>

<span data-ttu-id="4d2de-301">이 섹션에서는 다음 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-301">This section describes how to:</span></span>

1. [<span data-ttu-id="4d2de-302">Microsoft Edge ADMX 파일을 Intune으로 수집</span><span class="sxs-lookup"><span data-stu-id="4d2de-302">Ingest the Microsoft Edge ADMX file into Intune</span></span>](#ingest-the-microsoft-edge-admx-file-into-intune)
2. [<span data-ttu-id="4d2de-303">Intune에서 사용자 지정 OMA-URI를 사용하여 정책 설정</span><span class="sxs-lookup"><span data-stu-id="4d2de-303">Set a policy using custom OMA-URI in Intune</span></span>](#set-a-policy-using-custom-oma-uri-in-intune)

> [!IMPORTANT]
> <span data-ttu-id="4d2de-304">모범 사례는 사용자 지정 OMA-URI 프로필과 관리 템플릿 프로필을 사용하여 Intune에서 동일한 Microsoft Edge 설정을 구성하지 않는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-304">As a best practice, don’t use a custom OMA-URI profile and an Administration templates profile to configure the same Microsoft Edge setting in Intune.</span></span> <span data-ttu-id="4d2de-305">사용자 지정 OMA-URI와 관리 템플릿 프로필을 모두 사용하여 동일한 정책을 배포하지만 값이 다른 경우 사용자는 예기치 않은 결과를 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-305">If you deploy the same policy using both a custom OMA-URI  and an Administrative template profile, but with different values, users will get unpredictable results.</span></span> <span data-ttu-id="4d2de-306">관리 템플릿 프로필을 사용하기 전에 OMA-URI 프로필을 제거하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-306">We strongly recommend removing your OMA-URI profile before using an Administration templates profile.</span></span>

### <a name="ingest-the-microsoft-edge-admx-file-into-intune"></a><span data-ttu-id="4d2de-307">Microsoft Edge ADMX 파일을 Intune으로 수집</span><span class="sxs-lookup"><span data-stu-id="4d2de-307">Ingest the Microsoft Edge ADMX file into Intune</span></span>

<span data-ttu-id="4d2de-308">이 섹션에서는 Microsoft Edge 관리 템플릿(**msedge.admx** 파일)을 Intune으로 수집하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-308">This section describes how to ingest the Microsoft Edge administrative template (**msedge.admx** file) into Intune.</span></span>

> [!WARNING]
> <span data-ttu-id="4d2de-309">파일을 수집하기 전에 ADMX 파일을 수정하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="4d2de-309">Don't modify the ADMX file before ingesting the file.</span></span>

<span data-ttu-id="4d2de-310">ADMX 파일을 수집하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-310">To ingest the ADMX file, follow these steps:</span></span>

1. <span data-ttu-id="4d2de-311">[Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)에서 Microsoft Edge 정책 템플릿 파일(MicrosoftEdgePolicyTemplates.cab)을 다운로드하고 내용을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-311">Download the Microsoft Edge policy templates file (MicrosoftEdgePolicyTemplates.cab) from the [Microsoft Edge Enterprise landing page](https://aka.ms/EdgeEnterprise) and extract the contents.</span></span> <span data-ttu-id="4d2de-312">수집하려는 파일은 **msedge.admx**입니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-312">The file that you want to ingest is **msedge.admx**.</span></span>
2. <span data-ttu-id="4d2de-313">[Microsoft Azure portal](https://portal.azure.com)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-313">Sign in to the [Microsoft Azure portal](https://portal.azure.com).</span></span>
3. <span data-ttu-id="4d2de-314">_모든 서비스_에서 **Intune**을 선택하거나 포털 검색 상자에서 Intune을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-314">Select **Intune** from _All Services_, or search for Intune in the portal search box.</span></span>
4. <span data-ttu-id="4d2de-315">_Microsoft Intune - 개요_에서 **장치 구성** | **프로필**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-315">From _Microsoft Intune - Overview_, select **Device configuration** | **Profiles**.</span></span>
5. <span data-ttu-id="4d2de-316">위쪽 명령 모음에서 **+ 프로필 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-316">On the top command bar, select **+ Create profile**.</span></span>

   ![장치 프로필 만들기](./media/edge-cfg-with-mdm/configure-edge-mdm-intune-create-profile.png)

6. <span data-ttu-id="4d2de-318">다음 프로필 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-318">Provide the following profile information:</span></span>

   - <span data-ttu-id="4d2de-319">**이름**: 설명하는 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-319">**Name**: Enter a descriptive name.</span></span> <span data-ttu-id="4d2de-320">이 예에서는 "Microsoft Edge ADMX ingested configuration"을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-320">For this example, "Microsoft Edge ADMX ingested configuration".</span></span>
   - <span data-ttu-id="4d2de-321">**설명**: 프로필에 대한 선택적 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-321">**Description**: Enter an optional description for the profile.</span></span>
   - <span data-ttu-id="4d2de-322">**플랫폼**: "Windows 10 이상"을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-322">**Platform**: Select "Windows 10 and later"</span></span>
   - <span data-ttu-id="4d2de-323">**프로필 유형**: "사용자 지정"을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-323">**Profile type**: Select "Custom"</span></span>

7. <span data-ttu-id="4d2de-324">**사용자 지정 OMA-URI 설정**에서 **추가**를 클릭하여 ADMX 수집을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-324">On **Custom OMA-URI Settings**, click **Add** to add an ADMX ingestion.</span></span>

   ![OMA-URI에 대한 수집 추가](./media/edge-cfg-with-mdm/configure-edge-mdm-intune-create-profile-add-omauri.png)

8. <span data-ttu-id="4d2de-326">**행 추가**에서 다음 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-326">On **Add Row**, provide the following information:</span></span>

   - <span data-ttu-id="4d2de-327">**이름**: 설명하는 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-327">**Name**: Enter a descriptive name.</span></span> <span data-ttu-id="4d2de-328">이 예에서는 "Microsoft Edge ADMX ingestion"을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-328">For this example, use "Microsoft Edge ADMX ingestion".</span></span>
   - <span data-ttu-id="4d2de-329">**설명**: 설정에 대한 선택적 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-329">**Description**: Enter an optional description for the setting.</span></span>
   - <span data-ttu-id="4d2de-330">**OMA-URI**: "*./Device/Vendor/MSFT/Policy/ConfigOperations/ADMXInstall/Edge/Policy/EdgeAdmx*"를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-330">**OMA-URI**: Enter "*./Device/Vendor/MSFT/Policy/ConfigOperations/ADMXInstall/Edge/Policy/EdgeAdmx*"</span></span>
   - <span data-ttu-id="4d2de-331">**데이터 형식**: "문자열"을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-331">**Data type**: Select "String"</span></span>
   - <span data-ttu-id="4d2de-332">**값**: **데이터 형식**을 선택하면 이 입력 영역이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-332">**Value**: This input area appears after you select the **Data type**.</span></span> <span data-ttu-id="4d2de-333">1단계에서 추출한 Microsoft Edge 정책 템플릿 파일에서 msedge.admx 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-333">Open the msedge.admx file from the Microsoft Edge policy templates file you extracted in step 1.</span></span> <span data-ttu-id="4d2de-334">msedge.admx 파일의 **모든 텍스트**를 복사하여 다음 스크린샷에 표시된 **값** 텍스트 영역에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-334">Copy **ALL the text** from the msedge.admx file and paste it in the **Value** text area shown in the following screenshot.</span></span>

        ![ADMX 수집 추가](./media/edge-cfg-with-mdm/configure-edge-intune-mdm-omauri-addrow-ingest.png)

   - <span data-ttu-id="4d2de-336">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-336">Click **OK**.</span></span>

9. <span data-ttu-id="4d2de-337">**사용자 지정 OMA-URI 설정**에서 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-337">On **Custom OMA-URI Settings**, click **OK**.</span></span>
10. <span data-ttu-id="4d2de-338">**프로필 만들기**에서 **만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-338">On **Create profile**, click **Create**.</span></span> <span data-ttu-id="4d2de-339">다음 스크린샷은 새로 만든 프로필에 대한 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-339">The next screenshot shows information about the newly created profile.</span></span>

    ![<span data-ttu-id="4d2de-340">새 장치 프로필 정보</span><span class="sxs-lookup"><span data-stu-id="4d2de-340">New device profile information</span></span> ](./media/edge-cfg-with-mdm/configure-edge-mdm-intune-create-profile-done.png)

<!--
> [!NOTE]
> You can use the preceding steps to ingest the msedgeupate.admx policy template file.
-->
### <a name="set-a-policy-using-custom-oma-uri-in-intune"></a><span data-ttu-id="4d2de-341">Intune에서 사용자 지정 OMA-URI를 사용하여 정책 설정</span><span class="sxs-lookup"><span data-stu-id="4d2de-341">Set a policy using custom OMA-URI in Intune</span></span>

> [!NOTE]
> <span data-ttu-id="4d2de-342">이 섹션의 단계를 사용하기 전에 [Microsoft Edge ADMX 파일을 Intune으로 수집](#ingest-the-microsoft-edge-admx-file-into-intune)에 설명된 단계를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-342">Before using the steps in this section you must complete the steps described in [Ingest the Microsoft Edge ADMX file into Intune](#ingest-the-microsoft-edge-admx-file-into-intune).</span></span>

1. <span data-ttu-id="4d2de-343">[Microsoft Azure portal](https://portal.azure.com)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-343">Sign in to the [Microsoft Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="4d2de-344">_모든 서비스_에서 **Intune**을 선택하거나 포털 검색 상자에서 Intune을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-344">Select **Intune** from _All Services_, or search for Intune in the portal search box.</span></span>
3. <span data-ttu-id="4d2de-345">**Intune**>**장치 구성**>**프로필**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-345">Go to **Intune**>**Device configuration**>**Profiles**.</span></span>
4. <span data-ttu-id="4d2de-346">"Microsoft Edge ADMX ingested configuration" 프로필 또는 프로필에 사용한 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-346">Select the "Microsoft Edge ADMX ingested configuration" profile or the name you used for the profile.</span></span>
5. <span data-ttu-id="4d2de-347">Microsoft Edge 정책 설정을 추가하려면 **사용자 지정 OMA-URI 설정**을 열어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-347">To add Microsoft Edge policy settings, you have to open **Custom OMA-URI Settings**.</span></span> <span data-ttu-id="4d2de-348">**관리**에서 **속성**, **설정**을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-348">Under **Manage**, click **Properties**, and then click **Settings**.</span></span>

    ![프로필 설정 구성](./media/edge-cfg-with-mdm/configure-edge-mdm-intune-add-policy-settings.png)

6. <span data-ttu-id="4d2de-350">**사용자 지정 OMA-URI 설정**에서 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-350">On **Custom OMA-URI Settings**, click **Add**.</span></span>

    ![OMA-URI 설정에 행 추가](./media/edge-cfg-with-mdm/configure-edge-mdm-intune-add-policy-settings-add-row.png)

7. <span data-ttu-id="4d2de-352">**행 추가**에서 다음 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-352">On **Add Row**, provide the following information:</span></span>

   - <span data-ttu-id="4d2de-353">**이름**: 설명하는 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-353">**Name**: Enter a descriptive name.</span></span> <span data-ttu-id="4d2de-354">구성하려는 정책 이름을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-354">We suggest using the policy name you want to configure.</span></span> <span data-ttu-id="4d2de-355">이 예에서는 "ShowHomeButton"을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-355">For this example, use "ShowHomeButton".</span></span>
   - <span data-ttu-id="4d2de-356">**설명**(선택 사항): 설정에 대한 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-356">**Description** (Optional): Enter a description for the setting.</span></span>
   - <span data-ttu-id="4d2de-357">**OMA-URI**: 정책에 대한 OMA-URI를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-357">**OMA-URI**: Enter the OMA-URI for the policy.</span></span> <span data-ttu-id="4d2de-358">예를 들어 "ShowHomeButton" 정책의 경우 다음 문자열을 사용합니다. "*./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Startup/ShowHomeButton*"</span><span class="sxs-lookup"><span data-stu-id="4d2de-358">Using the for "ShowHomeButton" policy as an example, use this string: "*./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Startup/ShowHomeButton*"</span></span>
   - <span data-ttu-id="4d2de-359">**데이터 형식**: 정책 설정 데이터 형식을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-359">**Data type**: Select the policy settings data type.</span></span> <span data-ttu-id="4d2de-360">"ShowHomeButton" 정책의 경우 "문자열"을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-360">For the "ShowHomeButton" policy, use "String"</span></span>
   - <span data-ttu-id="4d2de-361">**값**: 정책에 대해 구성하려는 설정을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-361">**Value**: Enter the setting that you want to configure for the policy.</span></span> <span data-ttu-id="4d2de-362">"ShowHomeButton" 예의 경우 \<enabled/>을(를) 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-362">For "ShowHomeButton" example, enter "\<enabled/>".</span></span> <span data-ttu-id="4d2de-363">다음 스크린샷에서는 정책을 구성하기 위한 옵션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-363">The following screenshot shows the settings for configuring a policy.</span></span>

        ![행 추가, 사용자 지정 OMA-URI 설정](./media/edge-cfg-with-mdm/configure-edge-mdm-custom-omauri-setting.png)

   - <span data-ttu-id="4d2de-365">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-365">Click **OK**.</span></span>

8. <span data-ttu-id="4d2de-366">**사용자 지정 OMA-URI 설정**에서 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-366">On **Custom OMA-URI Settings**, click **OK**.</span></span>
9. <span data-ttu-id="4d2de-367">"**Microsoft Edge ADMX ingested configuration - 속성**" 프로필(또는 사용한 이름)에서 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-367">On the "**Microsoft Edge ADMX ingested configuration - Properties**" profile (or the name you used), click **Save**.</span></span>

<span data-ttu-id="4d2de-368">프로필을 만들고 속성을 설정한 후에는 [Microsoft Intune에서 프로필을 할당](/intune/configuration/device-profile-assign)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-368">After the profile is created and the properties set, you have to [assign the profile in Microsoft Intune](/intune/configuration/device-profile-assign).</span></span>

#### <a name="confirm-that-the-policy-was-set"></a><span data-ttu-id="4d2de-369">정책이 설정되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="4d2de-369">Confirm that the policy was set</span></span>

<span data-ttu-id="4d2de-370">다음 단계를 사용하여 Microsoft Edge 정책이 사용자가 만든 프로필을 사용하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-370">Use the following steps to confirm that the Microsoft Edge policy is using the profile you created.</span></span> <span data-ttu-id="4d2de-371">(Microsoft Intune이 "Microsoft Edge ADMX ingested configuration" 프로필 예에서 할당한 장치에 정책을 전파하도록 기다립니다.)</span><span class="sxs-lookup"><span data-stu-id="4d2de-371">(Give Microsoft Intune time to propagate the policy to a device you assigned in the "Microsoft Edge ADMX ingested configuration" profile example.)</span></span>

1. <span data-ttu-id="4d2de-372">Microsoft Edge를 열고 *edge://policy*로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-372">Open Microsoft Edge and go to *edge://policy*.</span></span>
2. <span data-ttu-id="4d2de-373">**정책** 페이지에서 프로필에 설정된 정책이 나열되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-373">On the **Policies** page, see if the policy you set in the profile is listed.</span></span>
3. <span data-ttu-id="4d2de-374">정책이 표시되지 않는 경우 [Windows 10에서 MDM 오류 진단](/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10) 또는 [정책 설정 문제 해결](#troubleshoot-a-policy-setting)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4d2de-374">If your policy isn't shown, see [Diagnose MDM failures in Windows 10](/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10) or [Troubleshoot a policy setting](#troubleshoot-a-policy-setting).</span></span>

#### <a name="troubleshoot-a-policy-setting"></a><span data-ttu-id="4d2de-375">정책 설정 문제 해결</span><span class="sxs-lookup"><span data-stu-id="4d2de-375">Troubleshoot a policy setting</span></span>

<span data-ttu-id="4d2de-376">Microsoft Edge 정책이 적용되지 않는 경우 다음 단계를 시도해 보세요.</span><span class="sxs-lookup"><span data-stu-id="4d2de-376">If a Microsoft Edge policy isn’t taking effect, try the following steps:</span></span>

<span data-ttu-id="4d2de-377">대상 장치( Microsoft Intune에서 프로필을 할당한 장치)에서 *edge://policy* 페이지를 열고 정책을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-377">Open the *edge://policy* page on the target device (a device you assigned the profile to in Microsoft Intune) and search for the policy.</span></span> <span data-ttu-id="4d2de-378">*edge://policy* 페이지에 정책이 없으면 다음을 시도해 보세요.</span><span class="sxs-lookup"><span data-stu-id="4d2de-378">If the policy isn’t on the *edge://policy* page, try the following:</span></span>

- <span data-ttu-id="4d2de-379">정책이 레지스트리에 있고 올바른지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-379">Check that the policy is in the registry and is correct.</span></span> <span data-ttu-id="4d2de-380">대상 장치에서 Windows 10 레지스트리 편집기를 엽니다(**Windows 키 + r**을 누르고 "*regedit*"를 입력한 다음 **Enter** 키를 누름). *\Software\Policies\ Microsoft\Edge* 경로에 정책이 올바르게 정의되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-380">On the target device open the Windows 10 Registry Editor (**Windows key + r**, enter “*regedit*” and then press **Enter**.) Check that the policy is correctly defined in the *\Software\Policies\ Microsoft\Edge* path.</span></span> <span data-ttu-id="4d2de-381">예상한 경로에서 정책을 찾지 못하면 정책이 장치에 올바르게 푸시되지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-381">If you don’t find the policy in the expected path, then the policy wasn’t pushed to the device correctly.</span></span>
- <span data-ttu-id="4d2de-382">OMA-URI 경로가 올바른지, 값이 유효한 XML 문자열인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-382">Check that the OMA-URI path is correct, and the value is a valid XML string.</span></span> <span data-ttu-id="4d2de-383">이러한 두 가지 중 하나가 올바르지 않으면 정책을 대상 장치로 푸시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4d2de-383">If either of these are incorrect the policy won’t be pushed to the target device.</span></span>

<span data-ttu-id="4d2de-384">더 많은 문제 해결 팁은 [Microsoft Intune 설정](/intune/fundamentals/setup-steps) 및 [장치 동기화](/intune/remote-actions/device-sync)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4d2de-384">For more trouble shooting tips, see [Set up Microsoft Intune](/intune/fundamentals/setup-steps) and [Sync devices](/intune/remote-actions/device-sync).</span></span>

## <a name="see-also"></a><span data-ttu-id="4d2de-385">기타 참조</span><span class="sxs-lookup"><span data-stu-id="4d2de-385">See also</span></span>

- [<span data-ttu-id="4d2de-386">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="4d2de-386">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="4d2de-387">Microsoft Intune을 사용하여 Microsoft Edge 정책 설정 구성</span><span class="sxs-lookup"><span data-stu-id="4d2de-387">Configure Microsoft Edge policy settings with Microsoft Intune</span></span>](configure-edge-with-intune.md)
- [<span data-ttu-id="4d2de-388">모바일 장치 관리</span><span class="sxs-lookup"><span data-stu-id="4d2de-388">Mobile device management</span></span>](/windows/client-management/mdm/)
- [<span data-ttu-id="4d2de-389">Intune에서 Windows 10 장치용 사용자 지정 설정 사용</span><span class="sxs-lookup"><span data-stu-id="4d2de-389">Use custom settings for Windows 10 devices in Intune</span></span>](/intune/configuration/custom-settings-windows-10)
- [<span data-ttu-id="4d2de-390">Win32 및 데스크톱 브리지 앱 정책 구성</span><span class="sxs-lookup"><span data-stu-id="4d2de-390">Win32 and Desktop Bridge app policy configuration</span></span>](/windows/client-management/mdm/win32-and-centennial-app-policy-configuration)
- [<span data-ttu-id="4d2de-391">ADMX 지원 정책 이해</span><span class="sxs-lookup"><span data-stu-id="4d2de-391">Understanding ADMX-backed policies</span></span>](/windows/client-management/mdm/understanding-admx-backed-policies)