---
title: Microsoft Intune을 사용하여 Windows용 Microsoft Edge 정책 설정 구성
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/18/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Intune을 사용하여 Windows용 Microsoft Edge 정책 설정을 구성합니다.
ms.openlocfilehash: 6200b52e9061f37f85fe0bfe7cf59a2172db97df
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980618"
---
# <span data-ttu-id="0ce99-103">Microsoft Intune을 사용하여 Microsoft Edge 정책 설정 구성</span><span class="sxs-lookup"><span data-stu-id="0ce99-103">Configure Microsoft Edge policy settings with Microsoft Intune</span></span>

<span data-ttu-id="0ce99-104">이 문서에서는 Microsoft Intune을 사용하여 Windows 10용 Microsoft Edge 정책 설정을 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0ce99-104">This article explains how to configure Microsoft Edge policy settings for Windows 10 using Microsoft Intune.</span></span>

> [!NOTE]
> <span data-ttu-id="0ce99-105">이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ce99-105">This article applies to Microsoft Edge version 77 or later.</span></span>

<span data-ttu-id="0ce99-106">Microsoft Intune에 장치 구성 프로필을 추가하여 Microsoft Edge 정책 및 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ce99-106">You can configure Microsoft Edge policies and settings by adding a device configuration profile to Microsoft Intune.</span></span> <span data-ttu-id="0ce99-107">Intune을 사용하여 정책을 관리하고 적용하는 것은 Active Directory 그룹 정책을 사용하거나 사용자 장치에서 로컬 GPO(그룹 정책 개체) 설정을 구성하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0ce99-107">Using Intune to manage and enforce policies is equivalent to using Active Directory Group Policy or configuring local Group Policy Object (GPO) settings on user devices.</span></span>

<span data-ttu-id="0ce99-108">Microsoft Intune을 사용하여 Microsoft Edge 정책을 관리하는 방법에 대한 자세한 내용을 보려면 [Microsoft Intune과 Microsoft Edge를 사용하여 웹 액세스 관리](https://docs.microsoft.com/intune/manage-microsoft-edge)를 읽을 수 있지만, 연결된 문서는 Microsoft Edge 45 이전 버전에만 해당하므로 Microsoft Edge 엔터프라이즈 버전 77 이상에 적용되지 않는 정보와 참조를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ce99-108">For more information about managing Microsoft Edge policies with Microsoft Intune, you can read [Manage web access by using Microsoft Edge with Microsoft Intune](https://docs.microsoft.com/intune/manage-microsoft-edge), but keep in mind that the linked article is specific to Microsoft Edge version 45 and earlier and therefore may contain information and references that don't apply to Microsoft Edge Enterprise version 77 and later.</span></span>

> [!TIP]
> <span data-ttu-id="0ce99-109">Microsoft Intune을 사용하여 macOS에서 Microsoft Edge를 구성하는 방법에 대한 자세한 내용은 [macOS용 구성](configure-microsoft-edge-on-mac.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0ce99-109">For information on how to configure Microsoft Edge on macOS using Microsoft Intune, see [Configure for macOS](configure-microsoft-edge-on-mac.md).</span></span>

## <span data-ttu-id="0ce99-110">Windows 10용 Microsoft Edge 설정을 관리하는 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="0ce99-110">Create a profile to manage settings in Microsoft Edge for Windows 10</span></span>

<span data-ttu-id="0ce99-111">Microsoft Intune의 관리 템플릿을 사용하면 클라우드를 사용하여 Windows 10 장치에서 Microsoft Edge 그룹 정책을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ce99-111">Using Administrative Templates in Microsoft Intune, you can manage Microsoft Edge group policies on your Windows 10 devices using the cloud.</span></span> <span data-ttu-id="0ce99-112">이 섹션에서는 템플릿을 만들어 Microsoft Edge 관련 응용 프로그램 설정을 구성하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ce99-112">This section will help you create a template to configure Microsoft Edge-specific application settings.</span></span> <span data-ttu-id="0ce99-113">템플릿을 만들면 장치 구성 프로필이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="0ce99-113">When you create the template, it creates a device configuration profile.</span></span> <span data-ttu-id="0ce99-114">그런 다음 조직에서 이 프로필을 Windows 10 장치에 할당하거나 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ce99-114">You can then assign or deploy this profile to Windows 10 devices in your organization.</span></span>

### <span data-ttu-id="0ce99-115">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="0ce99-115">Prerequisites</span></span>

- <span data-ttu-id="0ce99-116">다음 최소 시스템 요구 사항을 충족하는 Windows 10:</span><span class="sxs-lookup"><span data-stu-id="0ce99-116">Windows 10 with the following minimum system requirements:</span></span>
  - <span data-ttu-id="0ce99-117">Windows 10, 버전 1909</span><span class="sxs-lookup"><span data-stu-id="0ce99-117">Windows 10, version 1909</span></span>
  - <span data-ttu-id="0ce99-118">[KB4512941](https://support.microsoft.com/kb/4512941)이 설치된 Windows 10, 버전 1903</span><span class="sxs-lookup"><span data-stu-id="0ce99-118">Windows 10, version 1903 with [KB4512941](https://support.microsoft.com/kb/4512941) installed</span></span>
  - <span data-ttu-id="0ce99-119">[KB4512534](https://support.microsoft.com/kb/4512534)이 설치된 Windows 10, 버전 1809</span><span class="sxs-lookup"><span data-stu-id="0ce99-119">Windows 10, version 1809 with [KB4512534](https://support.microsoft.com/kb/4512534) installed</span></span>
  - <span data-ttu-id="0ce99-120">[KB4512509](https://support.microsoft.com/kb/4512509)이 설치된 Windows 10, 버전 1803</span><span class="sxs-lookup"><span data-stu-id="0ce99-120">Windows 10, version 1803 with [KB4512509](https://support.microsoft.com/kb/4512509) installed</span></span>
  - <span data-ttu-id="0ce99-121">[KB4516071](https://support.microsoft.com/kb/4516071)이 설치된 Windows 10, 버전 1709</span><span class="sxs-lookup"><span data-stu-id="0ce99-121">Windows 10, version 1709 with [KB4516071](https://support.microsoft.com/kb/4516071) installed</span></span>

### <span data-ttu-id="0ce99-122">관리 템플릿을 사용하여 Microsoft Edge에 대한 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="0ce99-122">Use Administrative Templates to create a policy for Microsoft Edge</span></span>

<span data-ttu-id="0ce99-123">이 절차에서는 Intune에서 기본 제공되는 관리 템플릿(그룹 정책에서 사용자에게 익숙한 경우)을 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="0ce99-123">This procedure leverages Administrative templates (which you might be familiar with from Group Policy) that are built into Intune.</span></span> <span data-ttu-id="0ce99-124">이 서식 파일을 사용하여 미리 구성된 목록에서 설정을 선택하여 Microsoft Edge에 대한 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ce99-124">You can use these templates to create a policy for Microsoft Edge by selecting settings from a pre-configured list.</span></span>

1. <span data-ttu-id="0ce99-125">[Microsoft 끝점 관리자](https://endpoint.microsoft.com/) 포털에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="0ce99-125">Sign in to the [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) portal.</span></span>
2. <span data-ttu-id="0ce99-126">왼쪽 탐색 창에서 **장치**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0ce99-126">Select **Devices** in the left-hand navigation pane.</span></span>
3. <span data-ttu-id="0ce99-127">**장치에서** | **개요**에서 **구성 프로필**(정책 제목 아래)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0ce99-127">From **Devices** | **Overview**, select **Configuration Profiles** (under Policy heading).</span></span>
4. <span data-ttu-id="0ce99-128">위쪽 명령 모음에서 **프로필 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0ce99-128">On the top command bar, select **Create profile**.</span></span>
5. <span data-ttu-id="0ce99-129">**플랫폼** 아래의 드롭다운 목록에서 **Windows 10 이상**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0ce99-129">In the drop-down list below **Platform**, select **Windows 10 and later**.</span></span>
6. <span data-ttu-id="0ce99-130">**프로필** 아래의 드롭다운 목록에서 **관리 템플릿**을 선택한 다음 **만들기** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0ce99-130">In the drop-down list below **Profile**, select **Administrative Templates** and then click the **Create** button.</span></span> <span data-ttu-id="0ce99-131">다음 스크린샷은 플랫폼 및 프로필 유형을 선택할 수 있는 드롭다운 목록을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0ce99-131">The next screenshot shows the drop-down lists to select the platform and type of profile.</span></span>

    ![플랫폼 및 프로필 유형 선택](./media/configure-edge-with-intune/create-profile-platform.png)

7. <span data-ttu-id="0ce99-133">**기본** 탭에서 Microsoft Edge 정책과 같이 설명 **이름**을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0ce99-133">On the **Basics** tab, enter a descriptive **Name**, such as Microsoft Edge Policy.</span></span> <span data-ttu-id="0ce99-134">원하는 경우 정책에 대한 **설명**을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0ce99-134">Optionally, enter a  **Description** for the policy.</span></span>
<span data-ttu-id="0ce99-135">다음 스크린샷은 **기본** 탭의 모양을 보여 주며 메뉴 표시줄에는 프로필을 만들기 위한 다음 단계(회색으로 표시된 탭)가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ce99-135">The next screenshot shows the form for the **Basics** tab and the menu bar shows the next steps (as grayed out tabs) to create the profile.</span></span>

   ![이름 및 설명 입력](./media/configure-edge-with-intune/create-profile-basics-tab.png)

8. <span data-ttu-id="0ce99-137">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0ce99-137">Select **Next**.</span></span>
9. <span data-ttu-id="0ce99-138">**구성 설정** 탭에서, 다음 위치 중 하나에서 Microsoft Edge 폴더를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0ce99-138">On the **Configuration settings** tab, select the Microsoft Edge folder in one of the following locations:</span></span>

   - <span data-ttu-id="0ce99-139">컴퓨터 구성 폴더 아래</span><span class="sxs-lookup"><span data-stu-id="0ce99-139">below the Computer Configuration folder</span></span>
   - <span data-ttu-id="0ce99-140">사용자 구성 폴더 아래.</span><span class="sxs-lookup"><span data-stu-id="0ce99-140">below the User Configuration folder.</span></span>

   <span data-ttu-id="0ce99-141">Microsoft Edge에 사용 가능한 설정이 오른쪽 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ce99-141">The available settings for Microsoft Edge will be shown on the right pane.</span></span> <span data-ttu-id="0ce99-142">예를 들어, *컴퓨터 구성/Microsoft Edge/다운로드 제한 허용*이 다음 스크린샷에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ce99-142">For example, *Computer Configuration/Microsoft Edge/Allow download restrictions* shown in the following screenshot.</span></span>

   ![구성 설정 탭](./media/configure-edge-with-intune/create-profile-configuration-settings-tab.png)

   > [!NOTE]
   > <span data-ttu-id="0ce99-144">Microsoft Edge에 사용할 수 있는 모든 설정에 대한 최신 전체 목록을 보려면 [Microsoft Edge – 정책](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies) 및 [Microsoft Edge – 업데이트 정책](https://docs.microsoft.com/DeployEdge/microsoft-edge-update-policies)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0ce99-144">See [Microsoft Edge – Policies](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies) and [Microsoft Edge – Update policies](https://docs.microsoft.com/DeployEdge/microsoft-edge-update-policies) for the most complete and up to date list of all the available settings for Microsoft Edge.</span></span>

10. <span data-ttu-id="0ce99-145">검색 필드("검색하여 항목 필터링...")를 사용하여 구성할 특정 설정을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0ce99-145">Use the search field ("Search to filter items ...") to find a specific setting you want to configure.</span></span> <span data-ttu-id="0ce99-146">이 예제에서는 검색 문자열은 "홈 페이지"입니다.</span><span class="sxs-lookup"><span data-stu-id="0ce99-146">In this example, the search string is "home page".</span></span> <span data-ttu-id="0ce99-147">다음 스크린샷은 검색 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0ce99-147">The next screenshot shows the search results.</span></span>

    ![검색 결과](./media/configure-edge-with-intune/create-profile-configuration-settings-tab-search.png)

11. <span data-ttu-id="0ce99-149">구성할 설정을 찾은 후에는 해당 설정을 선택하여 설정할 수 있는 값을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0ce99-149">After you find the setting you intend to configure, select it to expose the values you can set.</span></span> <span data-ttu-id="0ce99-150">다음 스크린샷에서 "홈 페이지 URL 구성"을 예제로 선택했습니다.</span><span class="sxs-lookup"><span data-stu-id="0ce99-150">In the next screenshot, we selected "Configure the home page URL" as an example.</span></span>

    ![홈 페이지 URL 구성 정책](./media/configure-edge-with-intune/create-profile-configuration-settings-tab-edit-pol.png)

12. <span data-ttu-id="0ce99-152">이전 스크린샷과 같이, 정책을 사용하도록 설정하고 홈 페이지 URL의 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0ce99-152">Enable the policy and enter a value for the Home page URL, as shown in the previous screenshot.</span></span>

13. <span data-ttu-id="0ce99-153">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0ce99-153">Click **OK**.</span></span> <span data-ttu-id="0ce99-154">다음 스크린샷 예와 같이, 설정 "상태" 열이 "사용"으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ce99-154">The settings "State" column should appear as "Enabled", as shown in the following screenshot example.</span></span>

    ![설정 상태가 사용 상태입니다.](./media/configure-edge-with-intune/create-profile-configuration-settings-tab-set-enabled.png)

14. <span data-ttu-id="0ce99-156">**다음** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0ce99-156">Click the **Next** button.</span></span>

15. <span data-ttu-id="0ce99-157">**범위 태그** 탭에서, 원하는 경우 범위 태그를 추가하고, 그렇지 않으면 **다음** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0ce99-157">On the **Scope tags** tab, add a Scope tag if wanted, otherwise click the **Next** button.</span></span>

16. <span data-ttu-id="0ce99-158">**과제** 탭에서 **+ 포함할 그룹 선택**을 클릭하여 해당 장치를 포함하는 Azure AD(Azure Active Directory) 그룹이나 이 정책 설정을 받을 사용자에게 해당 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="0ce99-158">On the **Assignments** tab, click **+ Select groups to include** to assign this policy to the Azure Active Directory (Azure AD) group that contains the devices or the users that you want to receive this policy setting.</span></span> <span data-ttu-id="0ce99-159">[Microsoft Intune에서 사용자 및 장치 프로필 할당](https://docs.microsoft.com/intune/device-profile-assign)에서 프로필을 Azure AD 사용자 또는 장치 그룹에 할당하는 방법에 대한 자세한 내용을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0ce99-159">See [Assign user and device profiles in Microsoft Intune](https://docs.microsoft.com/intune/device-profile-assign) for information about how to assign the profile to your Azure AD user or device groups.</span></span>

    ![포함할 그룹 선택](./media/configure-edge-with-intune/create-profile-assignments-tab.png)

17. <span data-ttu-id="0ce99-161">**다음** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0ce99-161">Click the **Next** button.</span></span>

18. <span data-ttu-id="0ce99-162">**검토 + 만들기** 탭에서 변경 내용의 요약을 검토하여 올바른지 확인한 다음 **만들기** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0ce99-162">On the **Review + create** tab, review the summary of your changes to ensure it's correct and then click the **Create** button.</span></span>

19. <span data-ttu-id="0ce99-163">새로 만든 정책(Microsoft Edge 정책)은 다음 스크린샷에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ce99-163">The newly created policy (Microsoft Edge Policy) is shown in the following screenshot.</span></span>

    ![포함할 그룹 선택](./media/configure-edge-with-intune/create-profile-new-policy-finished.png)

<span data-ttu-id="0ce99-165">Windows 10 프로필에 대한 자세한 내용은 [Windows 10 템플릿을 사용하여 Microsoft Intune에서 그룹 정책 설정 구성](https://docs.microsoft.com/intune/administrative-templates-windows)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0ce99-165">For more information about Windows 10 profiles, see [Use Windows 10 templates to configure group policy settings in Microsoft Intune](https://docs.microsoft.com/intune/administrative-templates-windows).</span></span>

## <span data-ttu-id="0ce99-166">기타 참조</span><span class="sxs-lookup"><span data-stu-id="0ce99-166">See also</span></span>

- [<span data-ttu-id="0ce99-167">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="0ce99-167">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="0ce99-168">Microsoft Intune과 Microsoft Edge를 사용하여 웹 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="0ce99-168">Manage web access by using Microsoft Edge with Microsoft Intune</span></span>](https://docs.microsoft.com/intune/manage-microsoft-edge)
- [<span data-ttu-id="0ce99-169">Windows 10 템플릿을 사용하여 Microsoft Intune에서 그룹 정책 설정 구성</span><span class="sxs-lookup"><span data-stu-id="0ce99-169">Use Windows 10 templates to configure group policy settings in Microsoft Intune</span></span>](https://docs.microsoft.com/intune/administrative-templates-windows)
- [<span data-ttu-id="0ce99-170">Microsoft Intune을 사용하여 Microsoft Edge 배포</span><span class="sxs-lookup"><span data-stu-id="0ce99-170">Deploy Microsoft Edge using Microsoft Intune</span></span>](https://docs.microsoft.com/intune/apps/apps-windows-edge/?toc=https://docs.microsoft.com/DeployEdge/toc.json&bc=https://docs.microsoft.com/DeployEdge/breadcrumb/toc.json)
