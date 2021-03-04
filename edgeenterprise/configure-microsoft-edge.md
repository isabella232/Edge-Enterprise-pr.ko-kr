---
title: Windows용 Microsoft Edge 구성
ms.author: brianalt
author: kelleyvice-msft
manager: laurawi
ms.date: 03/02/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Windows 장치에서 Microsoft Edge 정책 설정 구성
ms.openlocfilehash: 27e94a609bb8b01c90e1080c6e8cd521facc8d70
ms.sourcegitcommit: f14286edec59ee9183bdf38c15fc890881efd64f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/03/2021
ms.locfileid: "11385026"
---
# <a name="configure-microsoft-edge-policy-settings-on-windows"></a><span data-ttu-id="28487-103">Windows에서 Microsoft Edge 정책 설정 구성</span><span class="sxs-lookup"><span data-stu-id="28487-103">Configure Microsoft Edge policy settings on Windows</span></span>

<span data-ttu-id="28487-104">Windows 장치에서 Microsoft Edge 정책 설정을 구성하려면 다음 정보를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="28487-104">Use the following information to configure Microsoft Edge policy settings on your Windows devices.</span></span>

> [!NOTE]
> <span data-ttu-id="28487-105">이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="28487-105">This article applies to Microsoft Edge version 77 or later.</span></span>

## <a name="configure-policy-settings-on-windows"></a><span data-ttu-id="28487-106">Windows에서 정책 설정 구성</span><span class="sxs-lookup"><span data-stu-id="28487-106">Configure policy settings on Windows</span></span>

<span data-ttu-id="28487-107">_GPO(그룹 정책 개체)_ 를 사용하여 모든 Windows 버전에서 Microsoft Edge 및 관리되는 Microsoft Edge 업데이트에 대한 정책 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28487-107">You can use _group policy objects (GPO)_ to configure policy settings for Microsoft Edge and managed Microsoft Edge updates on all versions of Windows.</span></span> <span data-ttu-id="28487-108">또한 Microsoft Intune의 장치 관리에 등록된 Microsoft Active Directory 도메인 또는 Windows 10 Pro 및 엔터프라이즈 인스턴스에 가입한 Windows 장치에 대한 레지스트리를 통해 정책을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28487-108">You can also provision policy through the registry for Windows devices that are joined to a Microsoft Active Directory domain, or Windows 10 Pro or Enterprise instances enrolled for device management in Microsoft Intune.</span></span> <span data-ttu-id="28487-109">그룹 정책 개체를 사용하여 Microsoft Edge를 구성하려면 Microsoft Edge에 대한 규칙 및 설정을 추가하는 _관리 템플릿_을 Active Directory 도메인의 그룹 정책 중앙 저장소 또는 개별 컴퓨터의 정책 정의 템플릿 폴더에 설치한 다음 설정하려는 특정 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="28487-109">To configure Microsoft Edge with group policy objects, you install _administrative templates_ that add rules and settings for Microsoft Edge to the group policy Central Store in your Active Directory domain or to the Policy Definition template folder on individual computers and then configure the specific policies you want to set.</span></span>

<span data-ttu-id="28487-110">도메인 수준에서 정책을 관리하려는 경우 Active Directory 그룹 정책을 사용하여 Microsoft Edge 정책 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28487-110">You can use Active Directory group policy to configure Microsoft Edge policy settings if you prefer to manage policy at the domain level.</span></span> <span data-ttu-id="28487-111">이렇게 하면 전역적으로 정책 설정을 관리하거나, 특정 OU에 다양한 정책 설정을 지정하거나, WMI 필터를 사용하여 특정 쿼리에서 반환된 컴퓨터에만 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28487-111">This enables you to manage policy settings globally, targeting different policy settings to specific OUs, or using WMI filters to apply settings only to users or computers returned by a particular query.</span></span> <span data-ttu-id="28487-112">개별 컴퓨터에서 정책을 구성하려는 경우 대상 컴퓨터에서 로컬 그룹 정책 편집기를 사용하여 로컬 장치에만 영향을 주는 정책 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28487-112">If you want to configure policy on individual computers, you can apply policy settings that only affect the local device using the Local Group Policy Editor on the target computer.</span></span>

<span data-ttu-id="28487-113">Microsoft Edge는 _필수_ 및 _권장_ 정책을 모두 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="28487-113">Microsoft Edge supports both _mandatory_ and _recommended_ policies.</span></span> <span data-ttu-id="28487-114">필수 정책은 사용자 기본 설정을 재정의하고 사용자가 변경하지 못하도록 하는 반면, 권장 정책은 사용자가 재정의할 수 있는 기본 설정을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="28487-114">Mandatory policies override user preferences and prevents the user from changing it, while recommended policy provide a default setting that may be overridden by the user.</span></span> <span data-ttu-id="28487-115">대부분의 정책은 필수 사항입니다. 하위 집합은 필수 또는 권장입니다.</span><span class="sxs-lookup"><span data-stu-id="28487-115">Most policies are mandatory only; a subset are mandatory and recommended.</span></span> <span data-ttu-id="28487-116">두 버전의 정책이 모두 설정된 경우에는 필수 설정이 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="28487-116">If both versions of a policy are set, the mandatory setting takes precedence.</span></span> <span data-ttu-id="28487-117">권장 정책은 사용자가 설정을 수정하지 않은 경우 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="28487-117">A recommended policy only takes effect when the user has not modified the setting.</span></span>

>[!TIP]
> <span data-ttu-id="28487-118">Microsoft Intune을 사용하여 Microsoft Edge 정책 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28487-118">You can use Microsoft Intune to configure Microsoft Edge policy settings.</span></span> <span data-ttu-id="28487-119">자세한 내용은 [Microsoft Intune을 사용하여 Microsoft Edge 구성](configure-edge-with-intune.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="28487-119">For more information, see [Configure Microsoft Edge using Microsoft Intune](configure-edge-with-intune.md).</span></span>

<span data-ttu-id="28487-120">두 개의 Microsoft Edge용 관리 템플릿이 있으며, 둘 다 컴퓨터 또는 Active Directory 도메인 수준에서 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28487-120">There are two administrative templates for Microsoft Edge, both of which can be applied either at the computer or Active Directory domain level:</span></span>

- <span data-ttu-id="28487-121">[Microsoft Edge 설정 구성](microsoft-edge-policies.md)을 위한 *msedge.admx*</span><span class="sxs-lookup"><span data-stu-id="28487-121">*msedge.admx* to [configure Microsoft Edge settings](microsoft-edge-policies.md)</span></span>
- <span data-ttu-id="28487-122">[Microsoft Edge 업데이트 관리](microsoft-edge-update-policies.md)를 위한 *msedgeupdate.admx*.</span><span class="sxs-lookup"><span data-stu-id="28487-122">*msedgeupdate.admx* to [manage Microsoft Edge updates](microsoft-edge-update-policies.md).</span></span>

<span data-ttu-id="28487-123">시작하려면 Microsoft Edge 관리 템플릿을 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="28487-123">To get started, download and install the Microsoft Edge administrative template.</span></span>

### <a name="1-download-and-install-the-microsoft-edge-administrative-template"></a><span data-ttu-id="28487-124">1. Microsoft Edge 관리 템플릿 다운로드 및 설치</span><span class="sxs-lookup"><span data-stu-id="28487-124">1. Download and install the Microsoft Edge administrative template</span></span>

<span data-ttu-id="28487-125">Active Directory에서 Microsoft Edge 정책 설정을 구성하려면 도메인 컨트롤러 또는 RSAT(원격 서버 관리 도구)가 설치된 워크스테이션에서 액세스할 수 있는 네트워크 위치에 파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="28487-125">If you want to configure Microsoft Edge policy settings in Active Directory, download the files to a network location you can access from a domain controller or a workstation with the Remote Server Administration Tools (RSAT) installed.</span></span> <span data-ttu-id="28487-126">개별 컴퓨터에서 구성하려면 해당 컴퓨터에 파일을 다운로드하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="28487-126">To configure on an individual computer, simply download the files to that computer.</span></span>

<span data-ttu-id="28487-127">관리 템플릿 파일을 적절한 위치에 추가하면 Microsoft Edge 정책 설정을 그룹 정책 편집기에서 즉시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28487-127">When you add the administrative template files to the appropriate location, Microsoft Edge policy settings are immediately available in the Group Policy Editor.</span></span>

<span data-ttu-id="28487-128">[Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)로 이동하여 Microsoft Edge 정책 템플릿 파일(*MicrosoftEdgePolicyTemplates.cab*)을 다운로드하고 내용을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="28487-128">Go to the [Microsoft Edge Enterprise landing page](https://aka.ms/EdgeEnterprise) to download the Microsoft Edge policy templates file (*MicrosoftEdgePolicyTemplates.cab*) and extract the contents.</span></span>

#### <a name="add-the-administrative-template-to-active-directory"></a><span data-ttu-id="28487-129">Active Directory에 관리 템플릿 추가</span><span class="sxs-lookup"><span data-stu-id="28487-129">Add the administrative template to Active Directory</span></span>

1. <span data-ttu-id="28487-130">도메인 컨트롤러 또는 RSAT가 설치된 워크스테이션에서 도메인의 아무 도메인 컨트롤러에서나 **PolicyDefinition** 폴더( _중앙 저장소_라고도 함)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="28487-130">On a domain controller or workstation with RSAT, browse to the **PolicyDefinition** folder (also known as the _Central Store_) on any domain controller for your domain.</span></span> <span data-ttu-id="28487-131">이전 버전의 Windows Server의 경우에는 PolicyDefinition 폴더를 만들어야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28487-131">For older versions of Windows Server, you may need to create the PolicyDefinition folder.</span></span> <span data-ttu-id="28487-132">자세한 내용은 [Windows에서 그룹 정책 관리 템플릿 중앙 저장소를 만들고 관리하는 방법](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="28487-132">For more information, see [How to create and manage the Central Store for Group Policy Administrative Templates in Windows](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span></span>
2. <span data-ttu-id="28487-133">*MicrosoftEdgePolicyTemplates*를 열고 **windows** > **admx**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="28487-133">Open *MicrosoftEdgePolicyTemplates* and go to **windows** > **admx**.</span></span>
3. <span data-ttu-id="28487-134">*msedge.admx* 파일을 PolicyDefinition 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="28487-134">Copy the *msedge.admx* file to the PolicyDefinition folder.</span></span> <span data-ttu-id="28487-135">(예: %systemroot%\sysvol\domain\policies\PolicyDefinitions)</span><span class="sxs-lookup"><span data-stu-id="28487-135">(Example: %systemroot%\sysvol\domain\policies\PolicyDefinitions)</span></span>
4. <span data-ttu-id="28487-136">*admx* 폴더에서 적절한 언어 폴더를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="28487-136">In the *admx* folder, open the appropriate language folder.</span></span> <span data-ttu-id="28487-137">예를 들어 미국에서는 **en-US** 폴더를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="28487-137">For example, if you’re in the U.S., open the **en-US** folder.</span></span>
5. <span data-ttu-id="28487-138">*msedge.adml* 파일을 PolicyDefinition 폴더의 일치하는 언어 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="28487-138">Copy the *msedge.adml* file to the matching language folder in the PolicyDefinition folder.</span></span> <span data-ttu-id="28487-139">폴더가 없으면 새로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="28487-139">Create the folder if it does not already exist.</span></span> <span data-ttu-id="28487-140">(예: %systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US)</span><span class="sxs-lookup"><span data-stu-id="28487-140">(Example: %systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US)</span></span>
6. <span data-ttu-id="28487-141">도메인에 둘 이상의 도메인 컨트롤러가 있는 경우 다음 도메인 복제 간격에 새 ADMX 파일이 복제됩니다.</span><span class="sxs-lookup"><span data-stu-id="28487-141">If your domain has more than one domain controller, the new ADMX files will be replicated to them at the next domain replication interval.</span></span>
7. <span data-ttu-id="28487-142">파일이 올바로 로드되었는지 확인하려면 Windows 관리 도구에서 **그룹 정책 관리 편집기**를 열고 **컴퓨터 구성** > **정책** > **관리 템플릿** > **Microsoft Edge**를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="28487-142">To confirm the files loaded correctly, open the **Group Policy Management Editor** from Windows Administrative Tools and expand **Computer Configuration** > **Policies** > **Administrative Templates** > **Microsoft Edge**.</span></span> <span data-ttu-id="28487-143">아래와 같이 하나 이상의 Microsoft Edge 노드가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="28487-143">You should see one or more Microsoft Edge nodes as shown below.</span></span>

    ![Microsoft Edge 정책](./media/configure-microsoft-edge/edge-gpo-policies.png)

#### <a name="add-the-administrative-template-to-an-individual-computer"></a><span data-ttu-id="28487-145">개별 컴퓨터에 관리 템플릿 추가</span><span class="sxs-lookup"><span data-stu-id="28487-145">Add the administrative template to an individual computer</span></span>

1. <span data-ttu-id="28487-146">대상 컴퓨터에서 *MicrosoftEdgePolicyTemplates*를 열고 **windows** > **admx**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="28487-146">On the target computer, open *MicrosoftEdgePolicyTemplates* and go to **windows** > **admx**.</span></span>
2. <span data-ttu-id="28487-147">*msedge.admx* 파일을 정책 정의 템플릿 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="28487-147">Copy the *msedge.admx* file to your Policy Definition template folder.</span></span> <span data-ttu-id="28487-148">(예: C:\Windows\PolicyDefinitions)</span><span class="sxs-lookup"><span data-stu-id="28487-148">(Example: C:\Windows\PolicyDefinitions)</span></span>
3. <span data-ttu-id="28487-149">*admx* 폴더에서 적절한 언어 폴더를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="28487-149">In the *admx* folder, open the appropriate language folder.</span></span> <span data-ttu-id="28487-150">예를 들어 미국에서는 **en-US** 폴더를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="28487-150">For example, if you’re in the U.S., open the **en-US** folder.</span></span>
4. <span data-ttu-id="28487-151">*msedge.adml* 파일을 정책 정의 폴더의 일치하는 언어 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="28487-151">Copy the *msedge.adml* file to the matching language folder in your Policy Definition folder.</span></span> <span data-ttu-id="28487-152">(예: C:\Windows\PolicyDefinitions\en-US)</span><span class="sxs-lookup"><span data-stu-id="28487-152">(Example: C:\Windows\PolicyDefinitions\en-US)</span></span>
5. <span data-ttu-id="28487-153">파일이 올바로 로드되었는지 확인하려면 로컬 그룹 정책 편집기를 직접 열거나(Windows 키 + R을 누르고 gpedit.msc를 입력) MMC를 열고 로컬 그룹 정책 편집기 스냅인을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="28487-153">To confirm the files loaded correctly either open Local Group Policy Editor directly (Windows key + R and enter gpedit.msc) or open MMC and load the Local Group Policy Editor snap-in.</span></span> <span data-ttu-id="28487-154">오류가 발생하는 경우 일반적으로 파일이 잘못된 위치에 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="28487-154">If an error occurs, it’s usually because the files are in an incorrect location.</span></span>

### <a name="2-set-mandatory-or-recommended-policies"></a><span data-ttu-id="28487-155">2. 필수 또는 권장 정책 설정</span><span class="sxs-lookup"><span data-stu-id="28487-155">2. Set mandatory or recommended policies</span></span>

<span data-ttu-id="28487-156">Active Directory 및 개별 컴퓨터 모두에 대해 그룹 정책 편집기를 사용하여 필수 또는 권장 정책을 설정해 Microsoft Edge를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28487-156">You can set mandatory or recommended policies to configure Microsoft Edge with the Group Policy Editor for both Active Directory and individual computers.</span></span> <span data-ttu-id="28487-157">아래에 설명된 대로 적절한 노드를 선택하여 정책 설정을 **컴퓨터 구성** 또는 **사용자 구성**으로 범위 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28487-157">You can scope policy settings to either the **Computer Configuration** or **User Configuration** by selecting the appropriate node as described below.</span></span>

- <span data-ttu-id="28487-158">필수 정책을 구성하려면 그룹 정책 편집기를 열고 (**컴퓨터 구성** 또는 **사용자 구성**) > **정책** > **관리 템플릿** > **Microsoft Edge**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="28487-158">To configure a mandatory policy, open the Group Policy Editor and go to (**Computer Configuration** or **User Configuration**) > **Policies** > **Administrative Templates** > **Microsoft Edge**.</span></span>
- <span data-ttu-id="28487-159">권장 정책을 구성하려면 그룹 정책 편집기를 열고 (**컴퓨터 구성** 또는 **사용자 구성**) > **정책** > **관리 템플릿** > **Microsoft Edge – 기본 설정(사용자가 재정의할 수 있음)** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="28487-159">To configure a recommended policy, open the Group Policy Editor and go to (**Computer Configuration** or **User Configuration**) > **Policies** > **Administrative Templates** > **Microsoft Edge – Default Settings (users can override)**.</span></span>

  ![로컬 그룹 정책 편집기 열기](./media/configure-microsoft-edge/edge-ad-policy.png)

### <a name="3-test-your-policies"></a><span data-ttu-id="28487-161">3. 정책 테스트</span><span class="sxs-lookup"><span data-stu-id="28487-161">3. Test your policies</span></span>

<span data-ttu-id="28487-162">대상 클라이언트 장치에서 Microsoft Edge를 열고 **edge://policy**로 이동하여 적용된 모든 정책을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="28487-162">On a target client device, open Microsoft Edge and navigate to **edge://policy** to see all policies that are applied.</span></span> <span data-ttu-id="28487-163">로컬 컴퓨터에서 정책 설정을 적용한 경우 정책이 즉시 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="28487-163">If you applied policy settings on the local computer, policies should appear immediately.</span></span> <span data-ttu-id="28487-164">정책 설정을 구성하는 동안 열려 있던 Microsoft Edge를 닫았다가 다시 열어야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28487-164">You may need to close and reopen Microsoft Edge if it was open while you were configuring policy settings.</span></span>

![브라우저에서 구성된 정책 보기](./media/configure-microsoft-edge/edge-gpEdit.png)

<span data-ttu-id="28487-166">Active Directory 그룹 정책 설정의 경우 정책 설정은 도메인 관리자가 정의한 정기적인 간격으로 도메인 컴퓨터에 전파되고, 대상 컴퓨터가 즉시 정책 업데이트를 받지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28487-166">For Active Directory group policy settings, policy settings are propagated to domain computers at a regular interval defined by your domain administrator, and target computers may not receive policy updates right away.</span></span> <span data-ttu-id="28487-167">대상 컴퓨터에서 Active Directory 그룹 정책 설정을 수동으로 새로 고치려면 대상 컴퓨터의 명령 프롬프트나 PowerShell 세션에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="28487-167">To manually refresh Active Directory group policy settings on a target computer, execute the following command from a command prompt or PowerShell session on the target computer:</span></span>

``` powershell
gpupdate /force
```

<span data-ttu-id="28487-168">새 정책이 표시되려면 Microsoft Edge을 닫았다가 다시 열어야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28487-168">You may need to close and reopen Microsoft Edge before the new policies appear.</span></span>

<span data-ttu-id="28487-169">또한 대상 컴퓨터에서 REGEDIT.exe를 사용하여 그룹 정책 설정을 저장하는 레지스트리 설정을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28487-169">You can also use REGEDIT.exe on a target computer to view the registry settings that store group policy settings.</span></span> <span data-ttu-id="28487-170">이러한 설정은 레지스트리 경로 **HKLM\SOFTWARE\Policies\Microsoft\Edge**에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28487-170">These settings are located at the registry path **HKLM\SOFTWARE\Policies\Microsoft\Edge**.</span></span>

## <a name="see-also"></a><span data-ttu-id="28487-171">참고 항목</span><span class="sxs-lookup"><span data-stu-id="28487-171">See also</span></span>

- [<span data-ttu-id="28487-172">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="28487-172">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="28487-173">Intune을 사용한 Windows용 구성</span><span class="sxs-lookup"><span data-stu-id="28487-173">Configure for Windows with Intune</span></span>](configure-edge-with-intune.md)
- [<span data-ttu-id="28487-174">macOS용 구성</span><span class="sxs-lookup"><span data-stu-id="28487-174">Configure for macOS</span></span>](configure-microsoft-edge-on-mac.md)
- [<span data-ttu-id="28487-175">Microsoft Edge 엔터프라이즈 정책 찾아보기</span><span class="sxs-lookup"><span data-stu-id="28487-175">Browse Microsoft Edge Enterprise Policies</span></span>](microsoft-edge-policies.md)


