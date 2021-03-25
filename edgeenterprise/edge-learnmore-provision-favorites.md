---
title: Microsoft Edge용 즐겨찾기 프로비전
ms.author: capoon
author: dan-wesley
manager: abutcher
ms.date: 09/29/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge용 즐겨찾기 프로비전
ms.openlocfilehash: 67627fa10806435d76cecae00f79867bc5af03df
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447602"
---
# <a name="provision-favorites-for-microsoft-edge"></a><span data-ttu-id="34048-103">Microsoft Edge용 즐겨찾기 프로비전</span><span class="sxs-lookup"><span data-stu-id="34048-103">Provision favorites for Microsoft Edge</span></span>

<span data-ttu-id="34048-104">고객 피드백을 기반으로 즐겨찾기를 프로비저닝하도록 개선을 하였습니다.</span><span class="sxs-lookup"><span data-stu-id="34048-104">Based on customer feedback, we've made improvements to provisioning favorites.</span></span> <span data-ttu-id="34048-105">Microsoft Edge 버전 85부터는 관리자가 더 이상 즐겨찾기에 프로비전할 파일을 수동으로 만들 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="34048-105">Starting with Microsoft Edge version 85, Admins no longer have to manually craft a file to provision favorites.</span></span> <span data-ttu-id="34048-106">관리자는 Microsoft Edge UI를 사용하여 즐겨찾기 및 폴더를 추가하여 그룹 정책으로 내보낼 수 있는 파일을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34048-106">Admins can add favorites and folders using the Microsoft Edge UI to generate a file that can be exported to a group policy.</span></span>

<span data-ttu-id="34048-107">이 문서에서는 조직에 대한 즐겨찾기 및 폴더 집합을 프로비전하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="34048-107">This article describes how to provision a set of favorites and folders for your organization.</span></span> <span data-ttu-id="34048-108">[즐겨찾기 구성](//DeployEdge/microsoft-edge-policies#configure-favorites) 정책을 사용하여 즐겨찾기 및 폴더를 프로비전할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34048-108">You can use the [Configure favorites](//DeployEdge/microsoft-edge-policies#configure-favorites) policy to provision favorites and folders.</span></span>

> [!NOTE]
> <span data-ttu-id="34048-109">이 문서는 Microsoft Edge 버전 85 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="34048-109">This article applies to Microsoft Edge version 85 or later.</span></span>

## <a name="prerequisites-and-recommendations"></a><span data-ttu-id="34048-110">필수 구성 요소 및 권장 사항</span><span class="sxs-lookup"><span data-stu-id="34048-110">Prerequisites and recommendations</span></span>

- <span data-ttu-id="34048-111">Microsoft Edge 버전 85를 사용하며 그룹 정책에 알맞은 관리 템플릿을 설치한 경우</span><span class="sxs-lookup"><span data-stu-id="34048-111">Microsoft Edge version 85 with the appropriate administrative template installed for group policies.</span></span>
- <span data-ttu-id="34048-112">Microsoft Edge에서 새 프로필을 사용하여 이러한 즐겨찾기를 프로비전하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="34048-112">We recommend that you use a new profile in Microsoft Edge to provision these favorites.</span></span> <span data-ttu-id="34048-113">해당 프로필과 함께 저장된 모든 즐겨찾기가 내보내기에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="34048-113">All favorites that are saved with the profile will be included in the export.</span></span>  

## <a name="provision-favorites-and-folders"></a><span data-ttu-id="34048-114">즐겨찾기 및 폴더 프로비전</span><span class="sxs-lookup"><span data-stu-id="34048-114">Provision favorites and folders</span></span>

<span data-ttu-id="34048-115">다음 단계를 사용하여 사용자에 대한 즐겨찾기와 폴더를 프로비전합니다.</span><span class="sxs-lookup"><span data-stu-id="34048-115">Use the following steps to provision favorites and folders for your users.</span></span>

1. <span data-ttu-id="34048-116">Microsoft Edge 주소 표시줄로 이동하고 다음 URL을 입력합니다. *edge://flags/#edge-favorites-admin-export*.</span><span class="sxs-lookup"><span data-stu-id="34048-116">Go to the Microsoft Edge address bar and type this URL: *edge://flags/#edge-favorites-admin-export*.</span></span>
2. <span data-ttu-id="34048-117">**관리자용 즐겨찾기 구성 내보내기** 아래의 드롭다운 목록에서 **사용**을 선택한 다음 **다시 시작**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="34048-117">Under **Favorites configuration export for administrators**, pick **Enabled** from the dropdown list and then click **Restart**.</span></span>

3. <span data-ttu-id="34048-118">*edge://favorites* **즐겨찾기** 페이지로 이동하여 프로비전하려는 즐겨찾기나 폴더를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34048-118">Go to the **Favorites** page at *edge://favorites* so you can add the favorites and folders that you want to provision.</span></span>

<!--
4. On the **Favorites bar**, click **Add folder**. The folder structure of favorites that are set in the profile you're using will be reflected in the folder you provision for your users. The next screenshot shows "Managed favorites", the folder we'll use to provision favorites.

   ![Add a folder](media/edge-learnmore-provision-favorites/provision-favorites-add-folder.png)

   > [!TIP]
   > Add existing folders that contain favorites you want to provision for your users.

5. Select "Managed favorites" and then click **Add favorite**. The next screenshot shows the favorite we've added.

   ![Add a favorite](media/edge-learnmore-provision-favorites/provision-favorites-add-favorite.png)-->

4. <span data-ttu-id="34048-119">즐겨찾기와 폴더를 추가하는 작업을 완료 시, 이들을 **즐겨찾기 구성** 정책에서 사용될 수 있도록 내보내기를 합니다.</span><span class="sxs-lookup"><span data-stu-id="34048-119">When you finish adding favorites and folders you'll export them so they can be used by the **Configure favorites** policy.</span></span> <span data-ttu-id="34048-120">주소 표시줄로 이동하고 *edge://favorites*로 이동한 후, 줄임표 "**...**"를 클릭하고 **즐겨찾기 구성 내보내기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="34048-120">Go to the address bar and navigate to *edge://favorites*, click the ellipsis "**…**" and choose **Export favorites configuration**.</span></span> <span data-ttu-id="34048-121">다음 스크린샷은 즐겨찾기를 프로비저닝할 때 사용할 수 있는 옵션을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="34048-121">The next screenshot shows the options you have when provisioning favorites.</span></span>

   ![즐겨찾기 작업을 하기 위한 메뉴 옵션](media/edge-learnmore-provision-favorites/provision-favorites-menu-options.png)

5. <span data-ttu-id="34048-123">**즐겨찾기 구성 내보내기**에서 사용자에게 표시되는 폴더의 이름을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="34048-123">Under **Export your favorites configuration** you provide a name for the folder that your users will see.</span></span> <span data-ttu-id="34048-124">폴더 이름을 입력하고 사용하려는 플랫폼 형식을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="34048-124">Type the Folder name and pick the Platform format you want to use.</span></span> <span data-ttu-id="34048-125">**클립보드로 복사**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="34048-125">Click **Copy to clipboard**.</span></span> <span data-ttu-id="34048-126">다음 스크린샷은 폴더 이름에 대한 "관리형 즐겨찾기"를 보여주고 플랫폼은 Windows입니다.</span><span class="sxs-lookup"><span data-stu-id="34048-126">The next screenshot shows "Managed favorites" for the folder name and the platform is Windows.</span></span>

   ![Windows 폴더로 즐겨찾기를 내보내기 위한 대화 상자입니다.](media/edge-learnmore-provision-favorites/provision-favorites-export.png)

6. <span data-ttu-id="34048-128">그룹 정책 편집기를 열고, *컴퓨터 구성/관리 템플릿/* 으로 이동하고 **즐겨찾기 구성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="34048-128">Open the Group Policy Editor, navigate to *Computer Configuration/Administrative Templates/* and pick **Configure Favorites**.</span></span> <span data-ttu-id="34048-129">"즐겨찾기 구성" 정책을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="34048-129">Enable the "Configure Favorites" policy.</span></span> <span data-ttu-id="34048-130">**옵션:** 에서 즐겨찾기 구성 텍스트 영역에서 내보낸 콘텐츠를 붙여 넣은 다음 **적용**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="34048-130">Under **Options:**, paste the exported contents in the Configure favorites text area then click **Apply**.</span></span> <span data-ttu-id="34048-131">다음 스크린샷은 5단계에서의 "관리형 즐겨찾기" 폴더의 예시를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="34048-131">The next screenshot shows an example of the "Managed favorites" folder from step 5.</span></span>

   ![Gpedit을 사용하여 "즐겨찾기 구성" 정책을 설정하고 구성합니다.](media/edge-learnmore-provision-favorites/provision-favorites-gpedit.png)

7. <span data-ttu-id="34048-133">**확인**또는 **적용**을 클릭하여 이 정책 설정을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="34048-133">Click **OK** or **Apply** to safe the policy settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="34048-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="34048-134">See also</span></span>

- [<span data-ttu-id="34048-135">Microsoft Edge Enterprise 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="34048-135">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)