---
title: Microsoft Edge 및 조건부 액세스
ms.author: srugh
author: srugh
manager: seanlyn
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge 및 조건부 액세스
ms.openlocfilehash: 27d93627f8a86ad821a00d6d78b7db352e9e557a
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642854"
---
# <a name="microsoft-edge-and-conditional-access"></a><span data-ttu-id="d71c9-103">Microsoft Edge 및 조건부 액세스</span><span class="sxs-lookup"><span data-stu-id="d71c9-103">Microsoft Edge and Conditional Access</span></span>
  
<span data-ttu-id="d71c9-104">이 문서에서는 Microsoft Edge에서 조건부 액세스를 지원하는 방법과 조건부 액세스로 보호되는 리소스에 액세스하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d71c9-104">This article describes how Microsoft Edge supports Conditional Access, and how to access resources protected by Conditional Access.</span></span>

> [!NOTE]
> <span data-ttu-id="d71c9-105">이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d71c9-105">This article applies to Microsoft Edge version 77 or later.</span></span>

<span data-ttu-id="d71c9-106">클라우드 리소스를 관리할 때 클라우드 보안의 주요 측면은 ID와 액세스입니다.</span><span class="sxs-lookup"><span data-stu-id="d71c9-106">A key aspect of cloud security is identity and access when it comes to managing your cloud resources.</span></span> <span data-ttu-id="d71c9-107">모바일 중심, 클라우드 중심 세계에서 사용자는 어디서나 다양한 장치와 앱을 사용하여 조직의 리소스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d71c9-107">In a mobile-first, cloud-first world, users can access your organization's resources using a variety of devices and apps from anywhere.</span></span> <span data-ttu-id="d71c9-108">따라서 누가 리소스에 액세스할 수 있는지에 초점을 맞추는 것만으로는 충분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d71c9-108">As a result of this, just focusing on who can access a resource is not sufficient.</span></span> <span data-ttu-id="d71c9-109">리소스에 액세스하는 방법도 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d71c9-109">You also need to factor in how a resource is accessed.</span></span> <span data-ttu-id="d71c9-110">Azure AD(Azure Active Directory) 조건부 액세스를 통해 보안과 생산성 사이의 균형을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d71c9-110">Azure Active Directory (Azure AD) Conditional Access helps you master the balance between security and productivity.</span></span>

## <a name="accessing-conditional-access-protected-resources-in-microsoft-edge"></a><span data-ttu-id="d71c9-111">Microsoft Edge에서 조건부 액세스 보호 리소스에 액세스</span><span class="sxs-lookup"><span data-stu-id="d71c9-111">Accessing Conditional Access protected resources in Microsoft Edge</span></span>

<span data-ttu-id="d71c9-112">Microsoft Edge는 Azure AD 조건부 액세스를 기본적으로 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d71c9-112">Microsoft Edge natively supports Azure AD Conditional Access.</span></span> <span data-ttu-id="d71c9-113">별도의 확장 프로그램을 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d71c9-113">There's no need to install a separate extension.</span></span> <span data-ttu-id="d71c9-114">엔터프라이즈 Azure AD 자격 증명을 사용하여 Microsoft Edge 프로필에 로그인하면 Microsoft Edge는 조건부 액세스를 사용하여 보호된 엔터프라이즈 클라우드 리소스에 대한 원활한 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="d71c9-114">When you're signed into a Microsoft Edge profile with enterprise Azure AD credentials, Microsoft Edge allows seamless access to enterprise cloud resources protected using Conditional Access.</span></span>

<span data-ttu-id="d71c9-115">규정을 준수하는 장치에서 리소스에 액세스하는 ID는 프로필에서의 ID와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d71c9-115">On a compliant device, the identity accessing the resource should match the identity on the profile.</span></span>  <span data-ttu-id="d71c9-116">그렇지 않으면 다음 스크린샷과 같은 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d71c9-116">If it doesn't, you'll see a message like the one in the next screenshot.</span></span> <span data-ttu-id="d71c9-117">스크린샷 예에서 "testadmin@evostsoneboxtest.com"은 리소스에 액세스하는 데 필요한 로그인 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="d71c9-117">In the screenshot example, "testadmin@evostsoneboxtest.com" is the sign-in account needed to access the resource.</span></span>

![브라우저의 조건부 액세스 메시지](./media/edge-security/microsoft-edge-security-conditional-access.png)

<span data-ttu-id="d71c9-119">계속하려면 필요한 프로필(있는 경우)로 전환하거나 일치하는 ID를 사용하여 프로필을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d71c9-119">To continue, you have to switch to the required profile (if you have one) or create a profile with matching identity.</span></span>

<span data-ttu-id="d71c9-120">로그인하고 프로필 작업을 수행하려면 브라우저의 오른쪽 위 모서리에 있는 계정 사진을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d71c9-120">To sign in and work with your profile, click the account picture in the top right corner of the browser.</span></span> <span data-ttu-id="d71c9-121">드롭다운 메뉴를 사용하여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d71c9-121">You can use the dropdown menu to:</span></span>

- <span data-ttu-id="d71c9-122">다른 프로필을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d71c9-122">Select another profile.</span></span> <span data-ttu-id="d71c9-123">프로필 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d71c9-123">Click the profile name.</span></span>
- <span data-ttu-id="d71c9-124">프로필을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d71c9-124">Create a profile.</span></span> <span data-ttu-id="d71c9-125">**프로필 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d71c9-125">Click **Add a profile**.</span></span>
- <span data-ttu-id="d71c9-126">프로필을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="d71c9-126">Manage your profiles.</span></span> <span data-ttu-id="d71c9-127">**프로필 설정 관리**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d71c9-127">Click **Manage profile settings**.</span></span>

<span data-ttu-id="d71c9-128">이 지원은 모든 지원되는 Windows 및 macOS 버전을 포함하여 모든 플랫폼에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d71c9-128">This support is available across all platforms, including all supported versions of Windows and macOS.</span></span>

### <a name="how-to-deploy-conditional-access-in-azure-active-directory"></a><span data-ttu-id="d71c9-129">Azure Active Directory에서 조건부 액세스를 배포하는 방법</span><span class="sxs-lookup"><span data-stu-id="d71c9-129">How to deploy Conditional Access in Azure Active Directory</span></span>

<span data-ttu-id="d71c9-130">[조건부 액세스 배포](/azure/active-directory/conditional-access/plan-conditional-access)는 Azure Active Directory에서 조건부 액세스를 배포할 수 있는 자세한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d71c9-130">[Deploy Conditional Access](/azure/active-directory/conditional-access/plan-conditional-access) provides a detailed guide to help deploy Conditional Access in Azure Active Directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="d71c9-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d71c9-131">See also</span></span>

- [<span data-ttu-id="d71c9-132">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="d71c9-132">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="d71c9-133">비디오: 보안, 호환성 및 관리 용이성</span><span class="sxs-lookup"><span data-stu-id="d71c9-133">Video: Security, compatibility, and manageability</span></span>](/microsoft-edge-video-security-compatibility-manageability.md)