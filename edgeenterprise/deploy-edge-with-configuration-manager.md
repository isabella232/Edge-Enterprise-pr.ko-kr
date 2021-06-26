---
title: System Center Configuration Manager를 사용하여 Microsoft Edge 배포
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/08/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: SCCM(System Center Configuration Manager)를 사용하여 Microsoft Edge를 배포하는 방법을 알아봅니다.
ms.openlocfilehash: b403c8924a0f970aaadff2e1b20ebd05c0641a96
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2021
ms.locfileid: "11617548"
---
# <a name="deploy-microsoft-edge-using-system-center-configuration-manager"></a><span data-ttu-id="3ca5b-103">System Center Configuration Manager를 사용하여 Microsoft Edge 배포</span><span class="sxs-lookup"><span data-stu-id="3ca5b-103">Deploy Microsoft Edge using System Center Configuration Manager</span></span>

<span data-ttu-id="3ca5b-104">이 문서에서는 SCCM(System Center Configuration Manager)을 사용하여 Microsoft Edge 배포를 자동화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-104">This article shows you how to automate a Microsoft Edge deployment by using System Center Configuration Manager (SCCM).</span></span>

>[!NOTE]
><span data-ttu-id="3ca5b-105">이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-105">This article applies to Microsoft Edge version 77 or later.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="3ca5b-106">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="3ca5b-106">Before you begin</span></span>

<span data-ttu-id="3ca5b-107">[Configuration Manager에서 응용 프로그램 관리 소개](/sccm/apps/understand/introduction-to-application-management)를 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-107">Review the information in [Introduction to application management in Configuration Manager](/sccm/apps/understand/introduction-to-application-management).</span></span> <span data-ttu-id="3ca5b-108">이 응용 프로그램 관리 문서는 이 문서에 사용된 용어를 이해하는 데 도움이 되며, 응용 프로그램을 설치하기 위해 사이트를 준비하는 방법을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-108">This application management article will help you understand the terminology used in this article and is a guide to preparing your site to install applications.</span></span>

<span data-ttu-id="3ca5b-109">[Microsoft Edge엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)에서 Microsoft Edge 엔터프라이즈 설치 파일(**MicrosoftEdgeDevEnterpriseX64.msi** 및/또는 **MicrosoftEdgeDevEnterpriseX86.msi**)을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-109">Download the Microsoft Edge Enterprise installation files (**MicrosoftEdgeDevEnterpriseX64.msi** and/or **MicrosoftEdgeDevEnterpriseX86.msi**) from the [Microsoft Edge Enterprise landing page](https://aka.ms/EdgeEnterprise).</span></span>

<span data-ttu-id="3ca5b-110">Microsoft Edge 설치 파일을 액세스할 수 있는 네트워크 위치에 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-110">Make sure you store the Microsoft Edge installation files in an accessible network location.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="3ca5b-111">응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="3ca5b-111">Create the application</span></span>

<span data-ttu-id="3ca5b-112">응용 프로그램은 Configuration Manager 마법사를 사용하여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-112">You'll create the application using a Configuration Manager wizard.</span></span>

### <a name="start-the-create-application-wizard-and-create-the-application"></a><span data-ttu-id="3ca5b-113">응용 프로그램 만들기 마법사를 시작하고 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="3ca5b-113">Start the Create Application Wizard and create the application</span></span>  

1. <span data-ttu-id="3ca5b-114">Configuration Manager 콘솔에서 **소프트웨어 라이브러리** > **응용 프로그램 관리** > **응용 프로그램**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-114">In the Configuration Manager console, click **Software Library** > **Application Management** > **Applications**.</span></span>  

2. <span data-ttu-id="3ca5b-115">**홈** 탭의 **만들기** 그룹에서 **응용 프로그램 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-115">On the **Home** tab, in the **Create** group, click **Create Application**.</span></span> <span data-ttu-id="3ca5b-116">또는 탐색 모음에서 **응용 프로그램**을 마우스 오른쪽 단추로 클릭한 다음 **응용 프로그램 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-116">Or, right-click on **Applications** in the navigation bar and then click **Create Application**.</span></span>

    ![응용 프로그램 만들기](./media/edge-ent-deployment-sccm/edge-ent-create-app-1.png)

3. <span data-ttu-id="3ca5b-118">**응용 프로그램 만들기 마법사**의 **일반** 페이지에서 **설치 파일에서 이 응용 프로그램에 대한 정보 자동 검색** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-118">On the **General** page of the **Create Application Wizard**, choose **Automatically detect information about this application from installation files**.</span></span> <span data-ttu-id="3ca5b-119">그러면 마법사에서 일부 정보가 설치 .msi 파일에서 추출된 정보로 미리 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-119">This pre-populates some of the information in the wizard with information that's extracted from the installation .msi file.</span></span> <span data-ttu-id="3ca5b-120">다음 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-120">Provide the following information:</span></span>  

   - <span data-ttu-id="3ca5b-121">**유형**: **Windows Installer(\*.msi 파일)** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-121">**Type**: Choose **Windows Installer (\*.msi file)**.</span></span>  

   - <span data-ttu-id="3ca5b-122">**위치**: 설치 파일 **MicrosoftEdgeDevEnterpriseX64.msi** 또는 **MicrosoftEdgeDevEnterpriseX86.msi**의 위치를 입력합니다(또는 **찾아보기**를 클릭하여 위치를 선택).</span><span class="sxs-lookup"><span data-stu-id="3ca5b-122">**Location**: Type the location (or click **Browse** to select the location) of the installation file **MicrosoftEdgeDevEnterpriseX64.msi** or **MicrosoftEdgeDevEnterpriseX86.msi**.</span></span> <span data-ttu-id="3ca5b-123">Configuration Manager가 설치 파일을 찾을 수 있도록 위치를 *\\\Server\Share\File* 형식으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-123">Note that the location must be specified in the form *\\\Server\Share\File* for Configuration Manager to locate the installation files.</span></span>  

   <span data-ttu-id="3ca5b-124">다음은 **이 응용 프로그램에 대한 설정 지정** 페이지의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-124">Your **Specify settings for this application** page will look like the following example:</span></span>  

    ![이 응용 프로그램에 대한 설정 지정](./media/edge-ent-deployment-sccm/edge-ent-create-app-2.png)

4. <span data-ttu-id="3ca5b-126">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-126">Click **Next**.</span></span> <span data-ttu-id="3ca5b-127">**가져온 정보** 페이지의 **자세히**에서 가져온 응용 프로그램 및 모든 관련 파일에 대한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-127">Under **Details** on the **Imported Information** page, you'll see information about the application and any associated files that were imported.</span></span> <span data-ttu-id="3ca5b-128">마법사를 계속하려면 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-128">Click **Next** to continue with the wizard.</span></span>  

    ![가져온 정보 보기](./media/edge-ent-deployment-sccm/edge-ent-create-app-3.png)

5. <span data-ttu-id="3ca5b-130">**일반 정보** 페이지에서 응용 프로그램에 대한 정보를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-130">On the **General Information** page, you can add more information about the application.</span></span> <span data-ttu-id="3ca5b-131">예: 소프트웨어 버전, 관리자 설명 및 게시자.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-131">For example, Software version, Administrator comments, and Publisher.</span></span> <span data-ttu-id="3ca5b-132">이 정보를 활용하여 Configuration Manager 콘솔에서 응용 프로그램을 정렬하고 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-132">You can use this information to to help you sort and find the application in the Configuration Manager console.</span></span>

   <span data-ttu-id="3ca5b-133">또한 **설치 프로그램** 필드를 사용하여 PC에 응용 프로그램을 설치하는 데 사용되는 전체 명령줄을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-133">You can also use the **Installation program** field to specify the full command line that will be used to install the application on PCs.</span></span> <span data-ttu-id="3ca5b-134">이를 편집하여 자체 속성(예: 무인 설치의 경우 **/q**)을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-134">You can edit this to add your own properties (for example, **/q** for an unattended installation).</span></span>

   <span data-ttu-id="3ca5b-135">다음 스크린샷은 **이 응용 프로그램에 대한 정보 지정** 필드가 사용되는 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-135">The following screenshot shows an example where the **Specify information about this application** fields are used.</span></span>

   ![응용 프로그램 메타데이터 지정](./media/edge-ent-deployment-sccm/edge-ent-create-app-5.png)

6. <span data-ttu-id="3ca5b-137">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-137">Click **Next**.</span></span>
7. <span data-ttu-id="3ca5b-138">**요약** 페이지에서 **자세히** 아래에 있는 응용 프로그램 설정을 확인한 다음 마법사 사용을 마칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-138">On the **Summary** page, you can confirm your application settings under **Details** and then finish using the wizard.</span></span> <span data-ttu-id="3ca5b-139">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-139">Click **Next**.</span></span>  

    ![응용 프로그램 설정 세부 정보](./media/edge-ent-deployment-sccm/edge-ent-create-app-6.png)

8. <span data-ttu-id="3ca5b-141">**완료** 페이지에서 **닫기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-141">On the **Completion** page, click **Close**.</span></span>

    ![성공 대화 상자](./media/edge-ent-deployment-sccm/edge-ent-create-app-7.png)

<span data-ttu-id="3ca5b-143">응용 프로그램 만들기가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-143">You've finished creating the application.</span></span> <span data-ttu-id="3ca5b-144">Configuration Manager에서 다음 단계를 수행하여 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-144">Use the following steps to see it in Configuration Manager:</span></span>

- <span data-ttu-id="3ca5b-145">**소프트웨어 라이브러리** 작업 영역 선택</span><span class="sxs-lookup"><span data-stu-id="3ca5b-145">select the **Software Library** workspace</span></span>
- <span data-ttu-id="3ca5b-146">**응용 프로그램 관리** 확장</span><span class="sxs-lookup"><span data-stu-id="3ca5b-146">expand **Application Management**</span></span>
- <span data-ttu-id="3ca5b-147">**응용 프로그램** 클릭.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-147">click **Applications**.</span></span>

<span data-ttu-id="3ca5b-148">다음 스크린샷은 이 문서에 사용된 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-148">The following screenshot shows the example used for this article.</span></span>  

![응용 프로그램](./media/edge-ent-deployment-sccm/edge-ent-create-app-8.png)

## <a name="change-application-properties-and-deployment-settings"></a><span data-ttu-id="3ca5b-150">응용 프로그램 속성 및 배포 설정 변경</span><span class="sxs-lookup"><span data-stu-id="3ca5b-150">Change application properties and deployment settings</span></span>

<span data-ttu-id="3ca5b-151">응용 프로그램을 만든 후, 필요한 경우 응용 프로그램 설정을 구체화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-151">After you create an application, you can refine the application settings if you need to.</span></span> <span data-ttu-id="3ca5b-152">응용 프로그램 속성을 확인하려면</span><span class="sxs-lookup"><span data-stu-id="3ca5b-152">To look at the application properties:</span></span>

- <span data-ttu-id="3ca5b-153">응용 프로그램을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-153">select the application</span></span>
- <span data-ttu-id="3ca5b-154">**홈**>**속성**에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-154">in **Home**>**Properties**, click **Properties**.</span></span>  

   ![응용 프로그램 속성을 구성합니다.](./media/edge-ent-deployment-sccm/edge-ent-create-app-req-1.png)

 <span data-ttu-id="3ca5b-156">**<application name\> 응용 프로그램 속성** 대화 상자 페이지에 응용 프로그램의 동작을 변경하기 위해 구성할 수 있는 항목을 탭 형식 보기가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-156">In the **<application name\> Application Properties** dialog page, you'll see a tabbed view of the items that you can configure to change the behavior of the application.</span></span> <span data-ttu-id="3ca5b-157">구성할 수 있는 설정에 대한 자세한 내용은 [응용 프로그램 만들기](/sccm/apps/deploy-use/create-applications)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-157">For more information about the settings you can configure, see [Create applications](/sccm/apps/deploy-use/create-applications).</span></span>

<span data-ttu-id="3ca5b-158">이 예제에서는 응용 프로그램 배포 유형의 일부 속성을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-158">For this example, you'll change some properties of the application's deployment type.</span></span> <span data-ttu-id="3ca5b-159">배포 속성을 변경하려면</span><span class="sxs-lookup"><span data-stu-id="3ca5b-159">To change the deployment properties:</span></span>

1. <span data-ttu-id="3ca5b-160">**배포 유형** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-160">Click the **Deployment Types** tab.</span></span>
2. <span data-ttu-id="3ca5b-161">**배포 유형:** 에서 응용 프로그램 **이름**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-161">Under **Deployment types:**, select the application **Name**</span></span>
3. <span data-ttu-id="3ca5b-162">**편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-162">Click **Edit**.</span></span>

   ![배포 유형 편집](./media/edge-ent-deployment-sccm/edge-ent-create-app-req-2.png)

### <a name="add-a-requirement-to-the-deployment-type"></a><span data-ttu-id="3ca5b-164">배포 유형에 요구 사항 추가</span><span class="sxs-lookup"><span data-stu-id="3ca5b-164">Add a requirement to the deployment type</span></span>

 <span data-ttu-id="3ca5b-165">요구 사항은 장치에 응용 프로그램을 설치하기 전에 충족해야 하는 조건을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-165">Requirements specify conditions that must be met before an application is installed on a device.</span></span> <span data-ttu-id="3ca5b-166">기본 제공 요구 사항에서 선택하거나 직접 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-166">You can choose from built-in requirements or you can create your own.</span></span> <span data-ttu-id="3ca5b-167">예를 들어 설치 파일의 대상 프로세서 아키텍처에 따라 Windows 10 **x86** 또는 **x64**에서 실행되는 PC에만 응용 프로그램을 설치하는 요구 사항을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-167">For example, you can add a requirement that the application will only be installed on PCs that are running Windows 10 **x86** or **x64**, depending on the installation file's target processor architecture.</span></span> <span data-ttu-id="3ca5b-168">이 예제에서는 Windows 10 **x86**을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-168">In this example, you'll specify Windows 10 **x86**.</span></span>

1. <span data-ttu-id="3ca5b-169">방금 연 배포 유형 속성 페이지에서 **요구 사항** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-169">From the deployment type properties page you just opened, click the **Requirements** tab.</span></span>

2. <span data-ttu-id="3ca5b-170">**추가**를 클릭하여 **요구 사항 만들기** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-170">Click **Add** to open the **Create Requirement** dialog.</span></span>

    ![요구 사항 만들기](./media/edge-ent-deployment-sccm/edge-ent-create-app-req-3.png)

3. <span data-ttu-id="3ca5b-172">**요구 사항 만들기** 대화 상자에서 다음 정보를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-172">In the **Create Requirement** dialog box, specify the following information:</span></span>

    - <span data-ttu-id="3ca5b-173">**범주**: **장치**</span><span class="sxs-lookup"><span data-stu-id="3ca5b-173">**Category**: **Device**</span></span>  

    - <span data-ttu-id="3ca5b-174">**조건**: **운영 체제**</span><span class="sxs-lookup"><span data-stu-id="3ca5b-174">**Condition**: **Operating system**</span></span>  

    - <span data-ttu-id="3ca5b-175">**규칙 유형**: **값**</span><span class="sxs-lookup"><span data-stu-id="3ca5b-175">**Rule type**: **Value**</span></span>  

    - <span data-ttu-id="3ca5b-176">**연산자**: **다음 중 하나**</span><span class="sxs-lookup"><span data-stu-id="3ca5b-176">**Operator**: **One of**</span></span>  

    - <span data-ttu-id="3ca5b-177">운영 체제 목록에서 **Windows 10** > **모든 Windows 10(32비트)** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-177">From the operating systems list, select **Windows 10** > **All Windows 10 (32-bit)**.</span></span>  

    <span data-ttu-id="3ca5b-178">완료되면 대화 상자가 다음 스크린샷 예와 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-178">When you're finished, the dialog will look like the following screenshot example:</span></span>

    ![요구 사항 추가](./media/edge-ent-deployment-sccm/edge-ent-create-app-req-4.png)

4. <span data-ttu-id="3ca5b-180">**확인**을 클릭하여 열려 있는 각 속성 페이지를 닫고 Configuration Manager 콘솔의 **응용 프로그램** 목록으로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-180">Click **OK** to close each open property page and return to the **Applications** list in the Configuration Manager console.</span></span>  

## <a name="add-the-application-content-to-a-distribution-point"></a><span data-ttu-id="3ca5b-181">배포 지점에 응용 프로그램 콘텐츠 추가</span><span class="sxs-lookup"><span data-stu-id="3ca5b-181">Add the application content to a distribution point</span></span>  

<span data-ttu-id="3ca5b-182">PC에 업데이트된 응용 프로그램을 배포하려면 응용 프로그램 콘텐츠가 배포 지점에 복사되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-182">To deploy the updated application to PCs, make sure that the application content is copied to a distribution point.</span></span> <span data-ttu-id="3ca5b-183">PC는 배포 지점에 액세스하여 응용 프로그램을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-183">PCs access the distribution point to install the application.</span></span>  

>[!TIP]
><span data-ttu-id="3ca5b-184">Configuration Manager의 배포 지점 및 콘텐츠 관리에 대한 자세한 내용은 [System Center Configuration Manager의 콘텐츠 배포 및 관리](/sccm/core/servers/deploy/configure/deploy-and-manage-content)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-184">To find out more about distribution points and content management in Configuration Manager, see [Deploy and manage content for System Center Configuration Manager](/sccm/core/servers/deploy/configure/deploy-and-manage-content).</span></span>  

1. <span data-ttu-id="3ca5b-185">Configuration Manager 콘솔에서 **소프트웨어 라이브러리**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-185">In the Configuration Manager console, click **Software Library**.</span></span>  

2. <span data-ttu-id="3ca5b-186">**소프트웨어 라이브러리** 작업 영역에서 **응용 프로그램**을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-186">In the **Software Library** workspace, expand **Applications**.</span></span> <span data-ttu-id="3ca5b-187">응용 프로그램 목록에서 만든 응용 프로그램을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-187">Select the application you created in the list of applications.</span></span>

3. <span data-ttu-id="3ca5b-188">**홈** 탭의 **배포** 그룹에서 **콘텐츠 배포**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-188">On the **Home** tab in the **Deployment** group, click **Distribute Content**.</span></span>  

4. <span data-ttu-id="3ca5b-189">**콘텐츠 배포 마법사**의 **일반** 페이지에서 응용 프로그램 이름이 올바른지 확인하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-189">On the **General** page of the **Distribute Content Wizard**, check that the application name is correct, and then click **Next**.</span></span>  

5. <span data-ttu-id="3ca5b-190">**콘텐츠** 페이지에서 배포 지점에 복사할 정보를 검토하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-190">On the **Content** page, review the information that will be copied to the distribution point, and then click **Next**.</span></span>  

6. <span data-ttu-id="3ca5b-191">**콘텐츠 대상** 페이지에서 **추가**를 클릭하여 응용 프로그램 콘텐츠를 설치할 컬렉션, 배포 지점 또는 배포 지점 그룹을 하나 이상 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-191">On the **Content Destination** page, click **Add** to select one or more collections, distribution points, or distribution point groups on which to install the application content.</span></span>

7. <span data-ttu-id="3ca5b-192">마법사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-192">Complete the wizard.</span></span>

<span data-ttu-id="3ca5b-193">**배포 상태** > **콘텐츠 상태**에서 응용 프로그램 콘텐츠가 **모니터링** 작업 영역에서 배포 지점으로 성공적으로 복사되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-193">You can check that the application content was copied successfully to the distribution point from the **Monitoring** workspace, under **Distribution Status** > **Content Status**.</span></span>  

## <a name="deploy-the-application"></a><span data-ttu-id="3ca5b-194">응용 프로그램 배포</span><span class="sxs-lookup"><span data-stu-id="3ca5b-194">Deploy the application</span></span>  

<span data-ttu-id="3ca5b-195">그런 다음 응용 프로그램을 계층 구조의 장치 컬렉션에 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-195">Next, deploy the application to a device collection in your hierarchy.</span></span> <span data-ttu-id="3ca5b-196">이 예제에서는 응용 프로그램을 **모든 시스템** 장치 컬렉션에 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-196">In this example, you deploy the application to the **All Systems** device collection.</span></span>  

>[!TIP]
><span data-ttu-id="3ca5b-197">앞서 선택한 요구 사항 때문에 지정된 프로세서 아키텍처의 Windows 10 컴퓨터만 응용 프로그램을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-197">Remember that only Windows 10 computers of the specified processor architecture will install the application because of the requirements that you selected earlier.</span></span>  

1. <span data-ttu-id="3ca5b-198">Configuration Manager 콘솔에서 **소프트웨어 라이브러리** > **응용 프로그램 관리** > **응용 프로그램**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-198">In the Configuration Manager console, click **Software Library** > **Application Management** > **Applications**.</span></span>

2. <span data-ttu-id="3ca5b-199">응용 프로그램 목록에서 앞서 만든 응용 프로그램을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-199">From the list of applications, select the application that you created earlier.</span></span> <span data-ttu-id="3ca5b-200">그런 다음 **홈** 탭의 **배포** 그룹에서 **배포**를 클릭하거나 응용 프로그램을 마우스 오른쪽 단추로 클릭하고 **배포**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-200">Then, on the **Home** tab in the **Deployment** group, click **Deploy**, or right-click the application and select **Deploy**.</span></span>

    ![응용 프로그램 배포](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-1.png)

3. <span data-ttu-id="3ca5b-202">**소프트웨어 배포 마법사**의 **일반** 페이지에서 **찾아보기**를 클릭하여 응용 프로그램을 배포할 장치 컬렉션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-202">On the **General** page of the **Deploy Software Wizard**, click **Browse** to select the device collection to which you want to deploy the application.</span></span>

    ![설치 파일 찾기](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-2.png)

4. <span data-ttu-id="3ca5b-204">**콘텐츠** 페이지에서 PC가 응용 프로그램을 설치하는 데 사용할 배포 지점이 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-204">On the **Content** page, check that the distribution point from which you want PCs to install the application is selected.</span></span>

    ![배포 지점 지정](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-6.png)

5. <span data-ttu-id="3ca5b-206">**배포 설정** 페이지에서 배포 작업이 **설치**로 설정되어 있고 배포 목적이 **필수**로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-206">On the **Deployment Settings** page, make sure that the deployment action is set to **Install**, and the deployment purpose is set to **Required**.</span></span>

    ![배포 설정 구성](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-8.png)

    >[!TIP]
    ><span data-ttu-id="3ca5b-208">배포 목적을 **필수**로 설정하여 설정된 요구 사항을 충족하는 PC에 해당 응용 프로그램이 설치되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-208">By setting the deployment purpose to **Required**, you make sure that the application is installed on PCs that meet the requirements that you set.</span></span> <span data-ttu-id="3ca5b-209">이 값을 **사용 가능**으로 설정하면 사용자가 소프트웨어 센터에서 요청할 경우 응용 프로그램을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-209">If you set this value to **Available**, then users can install the application on demand from Software Center.</span></span>  

6. <span data-ttu-id="3ca5b-210">**예약** 페이지에서 응용 프로그램을 설치할 시기를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-210">On the **Scheduling** page, you can configure when the application will be installed.</span></span> <span data-ttu-id="3ca5b-211">이 예제에서는 **사용 가능 시간 후 가능한 한 빨리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-211">For this example, select **As soon as possible after the available time**.</span></span>

    ![배포 예약](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-9.png)

7. <span data-ttu-id="3ca5b-213">**사용자 환경** 페이지에서 원하는 값을 선택하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-213">On the **User Experience** page, select your desired values and click **Next**.</span></span>

    ![사용자 환경 지정](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-10.png)

8. <span data-ttu-id="3ca5b-215">원하는 경고 옵션을 지정하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-215">Specify your desired alert options and click **Next**.</span></span>

    ![경고 설정 지정](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-11.png)

9. <span data-ttu-id="3ca5b-217">마법사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-217">Complete the wizard.</span></span>

<span data-ttu-id="3ca5b-218">다음 **응용 프로그램 모니터링** 섹션에 있는 정보를 사용하여 응용 프로그램 배포의 상태를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-218">Use the information in the following **Monitor the application** section to see the status of your application deployment.</span></span>  

## <a name="monitor-the-application"></a><span data-ttu-id="3ca5b-219">응용 프로그램 모니터링</span><span class="sxs-lookup"><span data-stu-id="3ca5b-219">Monitor the application</span></span>

 <span data-ttu-id="3ca5b-220">이 섹션에서는 방금 배포한 응용 프로그램의 배포 상태를 간략히 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-220">In this section, you'll take a quick look at the deployment status of the application that you just deployed.</span></span>  

### <a name="to-review-the-deployment-status"></a><span data-ttu-id="3ca5b-221">배포 상태를 검토하려면</span><span class="sxs-lookup"><span data-stu-id="3ca5b-221">To review the deployment status</span></span>  

1. <span data-ttu-id="3ca5b-222">Configuration Manager 콘솔에서 **모니터링** > **배포**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-222">In the Configuration Manager console, click **Monitoring** > **Deployments**.</span></span>  

2. <span data-ttu-id="3ca5b-223">배포 목록에서 응용 프로그램을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-223">From the list of deployments, select the application.</span></span>

    ![배포 모니터링](./media/edge-ent-deployment-sccm/edge-ent-monitor-deployment.png)

3. <span data-ttu-id="3ca5b-225">**홈** 탭의 **배포** 그룹에서 **상태 보기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-225">On the **Home** tab in the **Deployment** group, click **View Status**.</span></span>  

4. <span data-ttu-id="3ca5b-226">다음 탭 중 하나를 선택하여 응용 프로그램 배포에 대한 상태 업데이트를 자세히 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-226">Select one of the following tabs to see more status updates about the application deployment:</span></span>  

    - <span data-ttu-id="3ca5b-227">**성공**: 응용 프로그램이 표시된 PC에 설치되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-227">**Success**: The application installed successfully on the indicated PCs.</span></span>  

    - <span data-ttu-id="3ca5b-228">**진행 중**: 응용 프로그램 설치가 아직 끝나지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-228">**In Progress**: The application has not yet finished installing.</span></span>  

    - <span data-ttu-id="3ca5b-229">**오류**: 표시된 PC에 응용 프로그램을 설치하는 동안 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-229">**Error**: An error occurred installing the application on the indicated PCs.</span></span> <span data-ttu-id="3ca5b-230">오류에 대한 자세한 내용도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-230">Further information about the error is also displayed.</span></span>  

    - <span data-ttu-id="3ca5b-231">**요구 사항에 맞지 않음**: 표시된 장치에서 사용자가 구성한 요구 사항에 맞지 않아 설치를 시도하지 않았습니다(이 예제에서는 Windows 10에서 실행되지 않기 때문).</span><span class="sxs-lookup"><span data-stu-id="3ca5b-231">**Requirements Not Met**: No installation attempt was made on the indicated devices because they did not meet the requirements you configured (in this example, because they do not run on Windows 10.)</span></span>

    - <span data-ttu-id="3ca5b-232">**알 수 없음**: Configuration Manager에서 배포 상태를 보고할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-232">**Unknown**: Configuration Manager was unable to report the status of the deployment.</span></span> <span data-ttu-id="3ca5b-233">나중에 다시 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-233">Check back again later.</span></span>  

    >[!TIP]
    ><span data-ttu-id="3ca5b-234">응용 프로그램 배포를 모니터링하는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-234">There are several ways you can monitor application deployments.</span></span> <span data-ttu-id="3ca5b-235">자세한 내용은 [System Center Configuration Manager 콘솔에서 응용 프로그램 모니터링](/sccm/apps/deploy-use/monitor-applications-from-the-console)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-235">For more information, see [Monitor applications from the System Center Configuration Manager console](/sccm/apps/deploy-use/monitor-applications-from-the-console).</span></span>  

## <a name="end-user-experience"></a><span data-ttu-id="3ca5b-236">최종 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="3ca5b-236">End-user experience</span></span>  

<span data-ttu-id="3ca5b-237">Configuration Manager에서 관리되고 지정된 프로세서 아키텍처의 Windows 10을 실행 중인 PC가 있는 사용자에게는 Microsoft Edge Dev 응용 프로그램을 설치해야 한다는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-237">Users who have PCs that are managed by Configuration Manager and are running Windows 10 of the specified processor architecture, will see a message telling them that they must install the Microsoft Edge Dev application.</span></span> <span data-ttu-id="3ca5b-238">이 설치 옵션을 수락하면 응용 프로그램이 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ca5b-238">When they accept this installation option, the application is installed.</span></span>  

## <a name="see-also"></a><span data-ttu-id="3ca5b-239">기타 참조</span><span class="sxs-lookup"><span data-stu-id="3ca5b-239">See also</span></span>

- [<span data-ttu-id="3ca5b-240">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="3ca5b-240">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="3ca5b-241">System Center Configuration Manager를 사용하여 응용 프로그램 만들기 및 배포</span><span class="sxs-lookup"><span data-stu-id="3ca5b-241">Create and deploy an application with System Center Configuration Manager</span></span>](/sccm/apps/get-started/create-and-deploy-an-application)