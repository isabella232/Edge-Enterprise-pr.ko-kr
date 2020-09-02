---
title: Windows용 Microsoft Edge 구성
ms.author: brianalt
author: kelleyvice-msft
manager: laurawi
ms.date: 10/09/2019
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Windows 장치에서 Microsoft Edge 정책 설정 구성
ms.openlocfilehash: 99aaf002f868ce29e81aa40024fa1de2e83d76e1
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980583"
---
# <span data-ttu-id="3f8a3-103">Windows에서 Microsoft Edge 정책 설정 구성</span><span class="sxs-lookup"><span data-stu-id="3f8a3-103">Configure Microsoft Edge policy settings on Windows</span></span>

<span data-ttu-id="3f8a3-104">Windows 장치에서 Microsoft Edge 정책 설정을 구성하려면 다음 정보를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-104">Use the following information to configure Microsoft Edge policy settings on your Windows devices.</span></span>

> [!NOTE]
> <span data-ttu-id="3f8a3-105">이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-105">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="3f8a3-106">Windows에서 정책 설정 구성</span><span class="sxs-lookup"><span data-stu-id="3f8a3-106">Configure policy settings on Windows</span></span>

<span data-ttu-id="3f8a3-107">_GPO(그룹 정책 개체)_ 를 사용하여 모든 Windows 버전에서 Microsoft Edge 및 관리되는 Microsoft Edge 업데이트에 대한 정책 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-107">You can use _group policy objects (GPO)_ to configure policy settings for Microsoft Edge and managed Microsoft Edge updates on all versions of Windows.</span></span> <span data-ttu-id="3f8a3-108">또한 Microsoft Intune의 장치 관리에 등록된 Microsoft Active Directory 도메인 또는 Windows 10 Pro 및 엔터프라이즈 인스턴스에 가입한 Windows 장치에 대한 레지스트리를 통해 정책을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-108">You can also provision policy through the registry for Windows devices that are joined to a Microsoft Active Directory domain, or Windows 10 Pro or Enterprise instances enrolled for device management in Microsoft Intune.</span></span> <span data-ttu-id="3f8a3-109">그룹 정책 개체를 사용하여 Microsoft Edge를 구성하려면 Microsoft Edge에 대한 규칙 및 설정을 추가하는 _관리 템플릿_을 Active Directory 도메인의 그룹 정책 중앙 저장소 또는 개별 컴퓨터의 정책 정의 템플릿 폴더에 설치한 다음 설정하려는 특정 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-109">To configure Microsoft Edge with group policy objects, you install _administrative templates_ that add rules and settings for Microsoft Edge to the group policy Central Store in your Active Directory domain or to the Policy Definition template folder on individual computers and then configure the specific policies you want to set.</span></span>

<span data-ttu-id="3f8a3-110">도메인 수준에서 정책을 관리하려는 경우 Active Directory 그룹 정책을 사용하여 Microsoft Edge 정책 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-110">You can use Active Directory group policy to configure Microsoft Edge policy settings if you prefer to manage policy at the domain level.</span></span> <span data-ttu-id="3f8a3-111">이렇게 하면 전역적으로 정책 설정을 관리하거나, 특정 OU에 다양한 정책 설정을 지정하거나, WMI 필터를 사용하여 특정 쿼리에서 반환된 컴퓨터에만 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-111">This enables you to manage policy settings globally, targeting different policy settings to specific OUs, or using WMI filters to apply settings only to users or computers returned by a particular query.</span></span> <span data-ttu-id="3f8a3-112">개별 컴퓨터에서 정책을 구성하려는 경우 대상 컴퓨터에서 로컬 그룹 정책 편집기를 사용하여 로컬 장치에만 영향을 주는 정책 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-112">If you want to configure policy on individual computers, you can apply policy settings that only affect the local device using the Local Group Policy Editor on the target computer.</span></span>

<span data-ttu-id="3f8a3-113">Microsoft Edge는 _필수_ 및 _권장_ 정책을 모두 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-113">Microsoft Edge supports both _mandatory_ and _recommended_ policies.</span></span> <span data-ttu-id="3f8a3-114">필수 정책은 사용자 기본 설정을 재정의하고 사용자가 변경하지 못하도록 하는 반면, 권장 정책은 사용자가 재정의할 수 있는 기본 설정을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-114">Mandatory policies override user preferences and prevents the user from changing it, while recommended policy provide a default setting that may be overridden by the user.</span></span> <span data-ttu-id="3f8a3-115">대부분의 정책은 필수 사항입니다. 하위 집합은 필수 또는 권장입니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-115">Most policies are mandatory only; a subset are mandatory and recommended.</span></span> <span data-ttu-id="3f8a3-116">두 버전의 정책이 모두 설정된 경우에는 필수 설정이 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-116">If both versions of a policy are set, the mandatory setting takes precedence.</span></span>

>[!TIP]
> <span data-ttu-id="3f8a3-117">Microsoft Intune을 사용하여 Microsoft Edge 정책 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-117">You can use Microsoft Intune to configure Microsoft Edge policy settings.</span></span> <span data-ttu-id="3f8a3-118">자세한 내용은 [Microsoft Intune을 사용하여 Microsoft Edge 구성](configure-edge-with-intune.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-118">For more information, see [Configure Microsoft Edge using Microsoft Intune](configure-edge-with-intune.md).</span></span>

<span data-ttu-id="3f8a3-119">두 개의 Microsoft Edge용 관리 템플릿이 있으며, 둘 다 컴퓨터 또는 Active Directory 도메인 수준에서 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-119">There are two administrative templates for Microsoft Edge, both of which can be applied either at the computer or Active Directory domain level:</span></span>

- <span data-ttu-id="3f8a3-120">[Microsoft Edge 설정 구성](microsoft-edge-policies.md)을 위한 *msedge.admx*</span><span class="sxs-lookup"><span data-stu-id="3f8a3-120">*msedge.admx* to [configure Microsoft Edge settings](microsoft-edge-policies.md)</span></span>
- <span data-ttu-id="3f8a3-121">[Microsoft Edge 업데이트 관리](microsoft-edge-update-policies.md)를 위한 *msedgeupdate.admx*.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-121">*msedgeupdate.admx* to [manage Microsoft Edge updates](microsoft-edge-update-policies.md).</span></span>

<span data-ttu-id="3f8a3-122">시작하려면 Microsoft Edge 관리 템플릿을 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-122">To get started, download and install the Microsoft Edge administrative template.</span></span>

### <span data-ttu-id="3f8a3-123">1. Microsoft Edge 관리 템플릿 다운로드 및 설치</span><span class="sxs-lookup"><span data-stu-id="3f8a3-123">1. Download and install the Microsoft Edge administrative template</span></span>

<span data-ttu-id="3f8a3-124">Active Directory에서 Microsoft Edge 정책 설정을 구성하려면 도메인 컨트롤러 또는 RSAT(원격 서버 관리 도구)가 설치된 워크스테이션에서 액세스할 수 있는 네트워크 위치에 파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-124">If you want to configure Microsoft Edge policy settings in Active Directory, download the files to a network location you can access from a domain controller or a workstation with the Remote Server Administration Tools (RSAT) installed.</span></span> <span data-ttu-id="3f8a3-125">개별 컴퓨터에서 구성하려면 해당 컴퓨터에 파일을 다운로드하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-125">To configure on an individual computer, simply download the files to that computer.</span></span>

<span data-ttu-id="3f8a3-126">관리 템플릿 파일을 적절한 위치에 추가하면 Microsoft Edge 정책 설정을 그룹 정책 편집기에서 즉시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-126">When you add the administrative template files to the appropriate location, Microsoft Edge policy settings are immediately available in the Group Policy Editor.</span></span>

<span data-ttu-id="3f8a3-127">[Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)로 이동하여 Microsoft Edge 정책 템플릿 파일(*MicrosoftEdgePolicyTemplates.cab*)을 다운로드하고 내용을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-127">Go to the [Microsoft Edge Enterprise landing page](https://aka.ms/EdgeEnterprise) to download the Microsoft Edge policy templates file (*MicrosoftEdgePolicyTemplates.cab*) and extract the contents.</span></span>

#### <span data-ttu-id="3f8a3-128">Active Directory에 관리 템플릿 추가</span><span class="sxs-lookup"><span data-stu-id="3f8a3-128">Add the administrative template to Active Directory</span></span>

1. <span data-ttu-id="3f8a3-129">도메인 컨트롤러 또는 RSAT가 설치된 워크스테이션에서 도메인의 아무 도메인 컨트롤러에서나 **PolicyDefinition** 폴더( _중앙 저장소_라고도 함)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-129">On a domain controller or workstation with RSAT, browse to the **PolicyDefinition** folder (also known as the _Central Store_) on any domain controller for your domain.</span></span> <span data-ttu-id="3f8a3-130">이전 버전의 Windows Server의 경우에는 PolicyDefinition 폴더를 만들어야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-130">For older versions of Windows Server, you may need to create the PolicyDefinition folder.</span></span> <span data-ttu-id="3f8a3-131">자세한 내용은 [Windows에서 그룹 정책 관리 템플릿 중앙 저장소를 만들고 관리하는 방법](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-131">For more information, see [How to create and manage the Central Store for Group Policy Administrative Templates in Windows](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span></span>
1. <span data-ttu-id="3f8a3-132">*MicrosoftEdgePolicyTemplates*를 열고 **windows** > **admx**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-132">Open *MicrosoftEdgePolicyTemplates* and go to **windows** > **admx**.</span></span>
1. <span data-ttu-id="3f8a3-133">*msedge.admx* 파일을 PolicyDefinition 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-133">Copy the *msedge.admx* file to the PolicyDefinition folder.</span></span> <span data-ttu-id="3f8a3-134">(예: %systemroot%\sysvol\domain\policies\PolicyDefinitions)</span><span class="sxs-lookup"><span data-stu-id="3f8a3-134">(Example: %systemroot%\sysvol\domain\policies\PolicyDefinitions)</span></span>
1. <span data-ttu-id="3f8a3-135">*admx* 폴더에서 적절한 언어 폴더를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-135">In the *admx* folder, open the appropriate language folder.</span></span> <span data-ttu-id="3f8a3-136">예를 들어 미국에서는 **en-US** 폴더를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-136">For example, if you’re in the U.S., open the **en-US** folder.</span></span>
1. <span data-ttu-id="3f8a3-137">*msedge.adml* 파일을 PolicyDefinition 폴더의 일치하는 언어 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-137">Copy the *msedge.adml* file to the matching language folder in the PolicyDefinition folder.</span></span> <span data-ttu-id="3f8a3-138">폴더가 없으면 새로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-138">Create the folder if it does not already exist.</span></span> <span data-ttu-id="3f8a3-139">(예: %systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US)</span><span class="sxs-lookup"><span data-stu-id="3f8a3-139">(Example: %systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US)</span></span>
1. <span data-ttu-id="3f8a3-140">도메인에 둘 이상의 도메인 컨트롤러가 있는 경우 다음 도메인 복제 간격에 새 ADMX 파일이 복제됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-140">If your domain has more than one domain controller, the new ADMX files will be replicated to them at the next domain replication interval.</span></span>
1. <span data-ttu-id="3f8a3-141">파일이 올바로 로드되었는지 확인하려면 Windows 관리 도구에서 **그룹 정책 관리 편집기**를 열고 **컴퓨터 구성** > **정책** > **관리 템플릿** > **Microsoft Edge**를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-141">To confirm the files loaded correctly, open the **Group Policy Management Editor** from Windows Administrative Tools and expand **Computer Configuration** > **Policies** > **Administrative Templates** > **Microsoft Edge**.</span></span> <span data-ttu-id="3f8a3-142">아래와 같이 하나 이상의 Microsoft Edge 노드가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-142">You should see one or more Microsoft Edge nodes as shown below.</span></span>

    ![Microsoft Edge 정책](./media/configure-microsoft-edge/edge-gpo-policies.png)

#### <span data-ttu-id="3f8a3-144">개별 컴퓨터에 관리 템플릿 추가</span><span class="sxs-lookup"><span data-stu-id="3f8a3-144">Add the administrative template to an individual computer</span></span>

1. <span data-ttu-id="3f8a3-145">대상 컴퓨터에서 *MicrosoftEdgePolicyTemplates*를 열고 **windows** > **admx**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-145">On the target computer, open *MicrosoftEdgePolicyTemplates* and go to **windows** > **admx**.</span></span>
2. <span data-ttu-id="3f8a3-146">*msedge.admx* 파일을 정책 정의 템플릿 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-146">Copy the *msedge.admx* file to your Policy Definition template folder.</span></span> <span data-ttu-id="3f8a3-147">(예: C:\Windows\PolicyDefinitions)</span><span class="sxs-lookup"><span data-stu-id="3f8a3-147">(Example: C:\Windows\PolicyDefinitions)</span></span>
3. <span data-ttu-id="3f8a3-148">*admx* 폴더에서 적절한 언어 폴더를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-148">In the *admx* folder, open the appropriate language folder.</span></span> <span data-ttu-id="3f8a3-149">예를 들어 미국에서는 **en-US** 폴더를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-149">For example, if you’re in the U.S., open the **en-US** folder.</span></span>
4. <span data-ttu-id="3f8a3-150">*msedge.adml* 파일을 정책 정의 폴더의 일치하는 언어 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-150">Copy the *msedge.adml* file to the matching language folder in your Policy Definition folder.</span></span> <span data-ttu-id="3f8a3-151">(예: C:\Windows\PolicyDefinitions\en-US)</span><span class="sxs-lookup"><span data-stu-id="3f8a3-151">(Example: C:\Windows\PolicyDefinitions\en-US)</span></span>
5. <span data-ttu-id="3f8a3-152">파일이 올바로 로드되었는지 확인하려면 로컬 그룹 정책 편집기를 직접 열거나(Windows 키 + R을 누르고 gpedit.msc를 입력) MMC를 열고 로컬 그룹 정책 편집기 스냅인을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-152">To confirm the files loaded correctly either open Local Group Policy Editor directly (Windows key + R and enter gpedit.msc) or open MMC and load the Local Group Policy Editor snap-in.</span></span> <span data-ttu-id="3f8a3-153">오류가 발생하는 경우 일반적으로 파일이 잘못된 위치에 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-153">If an error occurs, it’s usually because the files are in an incorrect location.</span></span>

<!--
To add the administrative template to manage Microsoft Edge updates:

1. Open the *MicrosoftEdgePolicyTemplates* file and go to **windows** > **admx**.
2. Copy the *msedgeupdate.admx* file to your Policy Definition template folder. (Example: C:\Windows\PolicyDefinitions)
3. In the *updatepolicies* folder, open the appropriate language folder. For example, if you’re in Germany, open the **de-DE** folder.
4. Copy the *msedgeupdate.adml* file to the matching language folder in your Policy Definition folder. (Example: C:\Windows\PolicyDefinitions\de-DE)
5. Open MMC and load the Local Group Policy Editor snap-in to confirm the files loaded correctly. If an error occurs, it’s usually because the files are in an incorrect location.

> [!NOTE]
> Currently the Microsoft Edge update policies are only localized in en-US. Additional language support will be added in a future release.
-->

### <span data-ttu-id="3f8a3-154">2. 필수 또는 권장 정책 설정</span><span class="sxs-lookup"><span data-stu-id="3f8a3-154">2. Set mandatory or recommended policies</span></span>

<span data-ttu-id="3f8a3-155">Active Directory 및 개별 컴퓨터 모두에 대해 그룹 정책 편집기를 사용하여 필수 또는 권장 정책을 설정해 Microsoft Edge를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-155">You can set mandatory or recommended policies to configure Microsoft Edge with the Group Policy Editor for both Active Directory and individual computers.</span></span> <span data-ttu-id="3f8a3-156">아래에 설명된 대로 적절한 노드를 선택하여 정책 설정을 **컴퓨터 구성** 또는 **사용자 구성**으로 범위 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-156">You can scope policy settings to either the **Computer Configuration** or **User Configuration** by selecting the appropriate node as described below.</span></span>

- <span data-ttu-id="3f8a3-157">필수 정책을 구성하려면 그룹 정책 편집기를 열고 (**컴퓨터 구성** 또는 **사용자 구성**) > **정책** > **관리 템플릿** > **Microsoft Edge**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-157">To configure a mandatory policy, open the Group Policy Editor and go to (**Computer Configuration** or **User Configuration**) > **Policies** > **Administrative Templates** > **Microsoft Edge**.</span></span>
- <span data-ttu-id="3f8a3-158">권장 정책을 구성하려면 그룹 정책 편집기를 열고 (**컴퓨터 구성** 또는 **사용자 구성**) > **정책** > **관리 템플릿** > **Microsoft Edge – 기본 설정(사용자가 재정의할 수 있음)** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-158">To configure a recommended policy, open the Group Policy Editor and go to (**Computer Configuration** or **User Configuration**) > **Policies** > **Administrative Templates** > **Microsoft Edge – Default Settings (users can override)**.</span></span>

  ![로컬 그룹 정책 편집기 열기](./media/configure-microsoft-edge/edge-ad-policy.png)

### <span data-ttu-id="3f8a3-160">3. 정책 테스트</span><span class="sxs-lookup"><span data-stu-id="3f8a3-160">3. Test your policies</span></span>

<span data-ttu-id="3f8a3-161">대상 클라이언트 장치에서 Microsoft Edge를 열고 **edge://policy**로 이동하여 적용된 모든 정책을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-161">On a target client device, open Microsoft Edge and navigate to **edge://policy** to see all policies that are applied.</span></span> <span data-ttu-id="3f8a3-162">로컬 컴퓨터에서 정책 설정을 적용한 경우 정책이 즉시 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-162">If you applied policy settings on the local computer, policies should appear immediately.</span></span> <span data-ttu-id="3f8a3-163">정책 설정을 구성하는 동안 열려 있던 Microsoft Edge를 닫았다가 다시 열어야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-163">You may need to close and reopen Microsoft Edge if it was open while you were configuring policy settings.</span></span>

![브라우저에서 구성된 정책 보기](./media/configure-microsoft-edge/edge-gpEdit.png)

<span data-ttu-id="3f8a3-165">Active Directory 그룹 정책 설정의 경우 정책 설정은 도메인 관리자가 정의한 정기적인 간격으로 도메인 컴퓨터에 전파되고, 대상 컴퓨터가 즉시 정책 업데이트를 받지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-165">For Active Directory group policy settings, policy settings are propagated to domain computers at a regular interval defined by your domain administrator, and target computers may not receive policy updates right away.</span></span> <span data-ttu-id="3f8a3-166">대상 컴퓨터에서 Active Directory 그룹 정책 설정을 수동으로 새로 고치려면 대상 컴퓨터의 명령 프롬프트나 PowerShell 세션에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-166">To manually refresh Active Directory group policy settings on a target computer, execute the following command from a command prompt or PowerShell session on the target computer:</span></span>

``` powershell
gpupdate /force
```

<span data-ttu-id="3f8a3-167">새 정책이 표시되려면 Microsoft Edge을 닫았다가 다시 열어야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-167">You may need to close and reopen Microsoft Edge before the new policies appear.</span></span>

<span data-ttu-id="3f8a3-168">또한 대상 컴퓨터에서 REGEDIT.exe를 사용하여 그룹 정책 설정을 저장하는 레지스트리 설정을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-168">You can also use REGEDIT.exe on a target computer to view the registry settings that store group policy settings.</span></span> <span data-ttu-id="3f8a3-169">이러한 설정은 레지스트리 경로 **HKLM\SOFTWARE\Policies\Microsoft\Edge**에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-169">These settings are located at the registry path **HKLM\SOFTWARE\Policies\Microsoft\Edge**.</span></span>

## <span data-ttu-id="3f8a3-170">FAQ</span><span class="sxs-lookup"><span data-stu-id="3f8a3-170">Frequently Asked Questions</span></span>

### <span data-ttu-id="3f8a3-171">마스터 기본 설정을 사용하도록 Microsoft Edge를 구성할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="3f8a3-171">Can Microsoft Edge be configured to use master preferences?</span></span>

<span data-ttu-id="3f8a3-172">예, 마스터 기본 설정 파일을 사용하도록 Microsoft Edge를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-172">Yes, you can configure Microsoft Edge to use a master preferences file.</span></span>

 <span data-ttu-id="3f8a3-173">마스터 기본 설정 파일을 사용하면 Microsoft Edge가 배포될 때 기본 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-173">A master preferences file lets you configure default settings when Microsoft Edge is deployed.</span></span> <span data-ttu-id="3f8a3-174">또한 마스터 기본 설정 파일을 사용하여 장치 관리 시스템에서 관리하지 않는 컴퓨터에서 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-174">You can also use a master preferences file to apply settings on computers that aren't managed by a device management system.</span></span> <span data-ttu-id="3f8a3-175">이러한 설정은 사용자가 브라우저를 처음 실행할 때 사용자 프로필에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-175">These settings are applied to the user’s profile the first time the user runs the browser.</span></span> <span data-ttu-id="3f8a3-176">사용자가 브라우저를 실행한 후에는 마스터 기본 설정 파일의 변경 내용이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-176">After the user runs the browser, changes to the master preferences file aren’t applied.</span></span> <span data-ttu-id="3f8a3-177">사용자는 브라우저에서 마스터 기본 설정에서 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-177">A user can change settings from the master preferences in the browser.</span></span> <span data-ttu-id="3f8a3-178">설정을 필수로 만들거나 브라우저를 처음 실행한 후 설정을 변경하려면 정책을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-178">If you want to make a setting mandatory or change a setting after the first run of the browser, you must use a policy.</span></span>

<span data-ttu-id="3f8a3-179">마스터 기본 설정 파일을 사용하면 다른 Chromium 기반 브라우저와 공유되는 항목과 Microsoft Edge에 고유한 항목을 포함하여 다양한 설정 및 기본 설정을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-179">A master preferences file lets you to customize many different settings and preferences for the browser, including those shared with other Chromium based browsers and specific to Microsoft Edge.</span></span>  <span data-ttu-id="3f8a3-180">마스터 기본 설정 파일을 사용하여 정책 관련 기본 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-180">Policy related preferences can be configured using the master preferences file.</span></span> <span data-ttu-id="3f8a3-181">정책이 설정되어 있고 해당 마스터 기본 설정 집합이 있는 경우 정책 설정이 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-181">In cases where a policy is set and there’s a corresponding master preference set, the policy setting takes precedence.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3f8a3-182">사용 가능한 기본 설정 중 일부는 Microsoft Edge 용어 및 명명 규칙과 일치하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-182">All the available preferences might not be consistent with Microsoft Edge terminology and naming conventions.</span></span>  <span data-ttu-id="3f8a3-183">이후 릴리스에서 이러한 기본 설정이 예상대로 계속 작동한다는 보장은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-183">There’s no guarantee that these preferences will continue to work as expected in future releases.</span></span> <span data-ttu-id="3f8a3-184">이후 버전에서 기본 설정이 변경되거나 무시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-184">Preferences might be changed or ignored in later versions.</span></span>

<span data-ttu-id="3f8a3-185">마스터 기본 설정 파일은 JSON 태그를 사용하여 서식 지정된 텍스트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-185">A master preferences file is a text file that’s formatted using JSON markup.</span></span> <span data-ttu-id="3f8a3-186">이 파일은 msedge.exe 실행 파일과 동일한 디렉터리에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-186">This file needs to be added to the same directory as the msedge.exe executable.</span></span> <span data-ttu-id="3f8a3-187">Windows에서의 시스템 수준 엔터프라이즈 배포인 경우 이 폴더는 일반적으로 *Windows: C:\Program Files\Microsoft\Edge\Application\master_preferences*입니다.</span><span class="sxs-lookup"><span data-stu-id="3f8a3-187">For system wide enterprise deployments on Windows this is typically: *Windows: C:\Program Files\Microsoft\Edge\Application\master_preferences*.</span></span>

## <span data-ttu-id="3f8a3-188">기타 참조</span><span class="sxs-lookup"><span data-stu-id="3f8a3-188">See also</span></span>

- [<span data-ttu-id="3f8a3-189">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="3f8a3-189">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="3f8a3-190">Intune을 사용한 Windows용 구성</span><span class="sxs-lookup"><span data-stu-id="3f8a3-190">Configure for Windows with Intune</span></span>](configure-edge-with-intune.md)
- [<span data-ttu-id="3f8a3-191">macOS용 구성</span><span class="sxs-lookup"><span data-stu-id="3f8a3-191">Configure for macOS</span></span>](configure-microsoft-edge-on-mac.md)
- [<span data-ttu-id="3f8a3-192">Microsoft Edge 엔터프라이즈 정책 찾아보기</span><span class="sxs-lookup"><span data-stu-id="3f8a3-192">Browse Microsoft Edge Enterprise Policies</span></span>](microsoft-edge-policies.md)


