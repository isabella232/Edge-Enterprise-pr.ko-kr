---
title: Jamf를 사용하여 macOS용 Microsoft Edge 배포 자동화
ms.author: kvice
author: dan-wesley
manager: laurawi
ms.date: 09/30/2019
audience: ITPro
ms.topic: technical
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Jamf를 사용하여 macOS용 Microsoft Edge 배포를 자동화하는 방법입니다.
ms.openlocfilehash: 3065e4f02dbfed70b887a60b1cf076335dbff19a
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980569"
---
# <span data-ttu-id="b7faa-103">Jamf로 macOS에 배포</span><span class="sxs-lookup"><span data-stu-id="b7faa-103">Deploy to macOS with Jamf</span></span>

<span data-ttu-id="b7faa-104">이 문서에서는 Jamf를 사용하여 macOS용 Microsoft Edge를 배포하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b7faa-104">This article describes how to deploy Microsoft Edge for macOS using Jamf.</span></span>

> [!NOTE]
> <span data-ttu-id="b7faa-105">이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7faa-105">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="b7faa-106">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="b7faa-106">Prerequisites</span></span>

<span data-ttu-id="b7faa-107">Microsoft Edge를 배포하기 전에 다음 필수 구성 요소를 충족하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b7faa-107">Before you deploy Microsoft Edge, make sure you meet the following prerequisites:</span></span>

- <span data-ttu-id="b7faa-108">Microsoft Edge 설치 파일인 **MicrosoftEdgeDev-\<version\>.pkg**는 네트워크에서 액세스할 수 있는 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7faa-108">The Microsoft Edge installation file,  **MicrosoftEdgeDev-\<version\>.pkg** is in an accessible location on your network.</span></span> <span data-ttu-id="b7faa-109">[Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)에서 Microsoft Edge 엔터프라이즈 설치 파일을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7faa-109">You can download the Microsoft Edge Enterprise installation files from the [Microsoft Edge Enterprise landing page](https://aka.ms/EdgeEnterprise).</span></span>
- <span data-ttu-id="b7faa-110">설치 파일을 만들고 컴퓨터에 배포하는 데 필요한 액세스 수준 및 권한이 있는 Jamf 클라우드 계정이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7faa-110">You have a Jamf Cloud account with the level of access and privileges needed to create and deploy installation files to computers.</span></span>

## <span data-ttu-id="b7faa-111">Jamf를 사용하여 Microsoft Edge를 배포하려면</span><span class="sxs-lookup"><span data-stu-id="b7faa-111">To deploy Microsoft Edge using Jamf:</span></span>

1. <span data-ttu-id="b7faa-112">Jamf에 로그인하고 **모든 설정**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b7faa-112">Sign on to Jamf and go to **All Settings**.</span></span>

    ![모든 설정 열기](./media/mac-deploy/jamf-dash-main-open-settings.png)

2. <span data-ttu-id="b7faa-114">**모든 설정**에서 **컴퓨터 관리**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b7faa-114">Under **All Settings**, click **Computer Management**.</span></span>

    ![컴퓨터 관리 선택](./media/mac-deploy/jamf-all-settings-computer-mgmt.png)

3. <span data-ttu-id="b7faa-116">**컴퓨터 관리**에서 **패키지**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b7faa-116">Under **Computer Management**, click **Packages**.</span></span>

    ![패키지 선택](./media/mac-deploy/jamf-all-settings-computer-mgmt-pkgs.png)

4. <span data-ttu-id="b7faa-118">**패키지** 페이지에서 **+ 새로 만들기**를 클릭하여 새 패키지를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b7faa-118">On the **Packages** page, click **+ New** to add a new package.</span></span>

    ![새로 만들기를 선택하여 새 패키지 추가](./media/mac-deploy/jamf-all-settings-computer-mgmt-new-pkg.png)

5. <span data-ttu-id="b7faa-120">**새 패키지** 페이지에서 패키지에 대한 세부 정보를 입력한 다음 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b7faa-120">On the **New Package** page, enter the details about the package and then click **Save**.</span></span> <span data-ttu-id="b7faa-121">(예: 표시 이름, 정보 또는 메모)</span><span class="sxs-lookup"><span data-stu-id="b7faa-121">(For example, DISPLAY NAME, INFO, or NOTES.)</span></span>

    ![저장을 선택하여 패키지 정보 저장](./media/mac-deploy/jamf-all-settings-computer-mgmt-save-pkg-info.png)

6. <span data-ttu-id="b7faa-123">메뉴 모음에서 **컴퓨터**를 선택한 다음 탐색 모음에서 **정책**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b7faa-123">Select **Computers** on the menu bar, and then select **Policies** in the navigation bar.</span></span>

7. <span data-ttu-id="b7faa-124">**+ 새로 만들기**를 선택하여 **새 정책** 창을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b7faa-124">Select **+ New** to display the **New Policy** pane.</span></span>

    ![새로 만들기를 선택하여 새 정책 만들기](./media/mac-deploy/jamf-all-settings-computer-new-policy.png)

8. <span data-ttu-id="b7faa-126">**옵션** 탭에서 **일반**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b7faa-126">On the **Options** tab, select **General**.</span></span>

    - <span data-ttu-id="b7faa-127">**표시 이름**에 정책의 표시 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b7faa-127">Under **DISPLAY NAME**, enter the display name for the policy.</span></span>
    - <span data-ttu-id="b7faa-128">**트리거**에서 정책을 트리거할 이벤트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b7faa-128">Under **Trigger**, select the event that will trigger the policy.</span></span> <span data-ttu-id="b7faa-129">(다음 예제에서는 이벤트가 시작입니다.)</span><span class="sxs-lookup"><span data-stu-id="b7faa-129">(In the following example, the event is Startup.)</span></span>

    ![배포 정보 입력](./media/mac-deploy/jamf-all-settings-computer-cfg-policy.png)

9. <span data-ttu-id="b7faa-131">**옵션** 탭에서 **패키지**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b7faa-131">On the **Options** tab, click **Packages**.</span></span>

10. <span data-ttu-id="b7faa-132">**패키지 구성** 팝업에서 **구성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b7faa-132">On the **Configure Packages** popup, click **Configure**.</span></span>

    ![패키지 구성](./media/mac-deploy/jamf-all-settings-computer-policy-pkg-configure.png)

11. <span data-ttu-id="b7faa-134">추가한 패키지는 **패키지** 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7faa-134">The package that you added shows on the **Packages** pane.</span></span> <span data-ttu-id="b7faa-135">**추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b7faa-135">Click **Add**.</span></span> <span data-ttu-id="b7faa-136">이 예제의 경우 다음 스크린샷에서 "MicrosoftEdgeBeta"가 패키지입니다.</span><span class="sxs-lookup"><span data-stu-id="b7faa-136">For this example, the package is "MicrosoftEdgeBeta" in the following screenshot.</span></span>

    ![패키지 추가](./media/mac-deploy/jamf-all-settings-computer-policy-pkg-add-beta.png)

12. <span data-ttu-id="b7faa-138">**새 정책** 페이지에서 드롭다운 목록을 사용하여 **배포 지점**과 정책에 수행할 **작업**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b7faa-138">On the **New Policy** page, uUse the drop-down lists to select the **DISTRIBUTION POINT** and **ACTION** to take for the policy.</span></span> <span data-ttu-id="b7faa-139">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b7faa-139">Click **Save**.</span></span> <span data-ttu-id="b7faa-140">다음 스크린샷에서는 "각 컴퓨터의 기본 배포 지점"과 "설치"를 예로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b7faa-140">The following screenshot uses "Each computer's default distribution point" and "Install" as an example.</span></span>

    ![배포 지점 및 작업 선택](./media/mac-deploy/jamf-all-settings-computer-mgmt-pkg-cfg-distro.png)

13. <span data-ttu-id="b7faa-142">**새 정책** 페이지에서 **범위** 탭을 선택합니다. 컴퓨터 또는 사용자를 기반으로 배포 범위를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7faa-142">On the **New Policy** page, select the **Scope** tab. You can manage the scope of the deployment based on computers or users.</span></span> <span data-ttu-id="b7faa-143">이 예제의 경우 **대상 컴퓨터** 드롭다운 목록에서 **모든 컴퓨터**를 선택한 다음 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b7faa-143">For this example, select **All Computers** from the **TARGET COMPUTERS** drop-down list and then click **Save**.</span></span>

    ![배포 범위 선택](./media/mac-deploy/jamf-all-settings-computer-mgmt-add-target.png)

14. <span data-ttu-id="b7faa-145">이제 Microsoft Edge 배포 정책을 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7faa-145">At this point you can review the Microsoft Edge deployment policy.</span></span> <span data-ttu-id="b7faa-146">배포 옵션이 요구 사항에 맞으면 **완료**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b7faa-146">If the deployment options meet your requirements, click **Done**.</span></span>

    ![완료 클릭](./media/mac-deploy/jamf-all-settings-computer-mgmt-finish-add-deployment.png)

    > [!NOTE]
    > <span data-ttu-id="b7faa-148">언제든지 배포 정책으로 돌아와서 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7faa-148">You can return to a deployment policy at any time to change settings.</span></span>

<span data-ttu-id="b7faa-149">축하합니다!</span><span class="sxs-lookup"><span data-stu-id="b7faa-149">Congratulations!</span></span> <span data-ttu-id="b7faa-150">macOS용 Microsoft Edge 배포를 위한 Jamf 구성을 완료했습니다.</span><span class="sxs-lookup"><span data-stu-id="b7faa-150">You’ve just finished configuring Jamf to deploy Microsoft Edge for macOS.</span></span> <span data-ttu-id="b7faa-151">정의한 트리거 조건이 참이면 패키지가 지정한 컴퓨터에 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7faa-151">When the trigger condition you defined is true, the package will get deployed to the computers you specified.</span></span>

## <span data-ttu-id="b7faa-152">기타 참조</span><span class="sxs-lookup"><span data-stu-id="b7faa-152">See also</span></span>

- [<span data-ttu-id="b7faa-153">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="b7faa-153">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="b7faa-154">Jamf.com</span><span class="sxs-lookup"><span data-stu-id="b7faa-154">Jamf.com</span></span>](https://www.jamf.com/)
- [<span data-ttu-id="b7faa-155">Microsoft Intune과 Jamf 통합</span><span class="sxs-lookup"><span data-stu-id="b7faa-155">Integrate Jamf with Microsoft Intune</span></span>](https://docs.microsoft.com/intune/conditional-access-integrate-jamf)
