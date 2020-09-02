---
title: Microsoft Edge 보안 개요
ms.author: srugh
author: srugh
manager: seanlyn
ms.date: 04/29/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 보안 배포 개요
ms.openlocfilehash: f22f2dcbace00cd535d201950c2af488c708525b
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980766"
---
# <span data-ttu-id="74721-103">Microsoft Edge 보안 개요</span><span class="sxs-lookup"><span data-stu-id="74721-103">Overview of Microsoft Edge security</span></span>
  
<span data-ttu-id="74721-104">엔터프라이즈 IT 관리자는 회사 네트워크 및 장치를 악의적인 공격으로부터 보호하고 회사 데이터의 무단 액세스 및 누출을 방지하면서 수많은 기존 및 새로운 보안 문제를 지속적으로 직면하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74721-104">IT admins in the enterprise are constantly facing a myriad of existing and emerging security challenges while protecting the corporate network and devices from malicious attacks and preventing unauthorized access and leaks of corporate data.</span></span> <span data-ttu-id="74721-105">Microsoft Edge는 이러한 문제를 해결하는 데 도움이 되는 여러 가지 독자적인 기능을 기본 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="74721-105">Microsoft Edge provides several natively built, unique capabilities that help address these challenges.</span></span>

> [!NOTE]
> <span data-ttu-id="74721-106">이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="74721-106">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="74721-107">조건부 액세스</span><span class="sxs-lookup"><span data-stu-id="74721-107">Conditional Access</span></span>

<span data-ttu-id="74721-108">클라우드 리소스를 관리할 때 클라우드 보안의 주요 측면은 ID와 액세스입니다.</span><span class="sxs-lookup"><span data-stu-id="74721-108">A key aspect of cloud security is identity and access when it comes to managing your cloud resources.</span></span> <span data-ttu-id="74721-109">모바일 중심, 클라우드 중심 세계에서 사용자는 어디서나 다양한 장치와 앱을 사용하여 조직의 리소스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74721-109">In a mobile-first, cloud-first world, users can access your organization's resources using a variety of devices and apps from anywhere.</span></span> <span data-ttu-id="74721-110">따라서 누가 리소스에 액세스할 수 있는지에 초점을 맞추는 것만으로는 충분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="74721-110">As a result of this, just focusing on who can access a resource is not sufficient.</span></span> <span data-ttu-id="74721-111">리소스에 액세스하는 방법도 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74721-111">You also need to factor in how a resource is accessed.</span></span> <span data-ttu-id="74721-112">Azure AD(Azure Active Directory) 조건부 액세스를 통해 보안과 생산성 사이의 균형을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74721-112">Azure Active Directory (Azure AD) Conditional Access helps you master the balance between security and productivity.</span></span>

### <span data-ttu-id="74721-113">Microsoft Edge에서 조건부 액세스 보호 리소스에 액세스</span><span class="sxs-lookup"><span data-stu-id="74721-113">Accessing Conditional Access protected resources in Microsoft Edge</span></span>

<span data-ttu-id="74721-114">Microsoft Edge는 Azure AD 조건부 액세스를 기본적으로 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="74721-114">Microsoft Edge natively supports Azure AD Conditional Access.</span></span> <span data-ttu-id="74721-115">별도의 확장 프로그램을 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74721-115">There's no need to install a separate extension.</span></span> <span data-ttu-id="74721-116">엔터프라이즈 Azure AD 자격 증명을 사용하여 Microsoft Edge 프로필에 로그인하면 Microsoft Edge는 조건부 액세스를 사용하여 보호된 엔터프라이즈 클라우드 리소스에 대한 원활한 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="74721-116">When you're signed into a Microsoft Edge profile with enterprise Azure AD credentials, Microsoft Edge allows seamless access to enterprise cloud resources protected using Conditional Access.</span></span>

<span data-ttu-id="74721-117">규정을 준수하는 장치에서 리소스에 액세스하는 ID는 프로필에서의 ID와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74721-117">On a compliant device, the identity accessing the resource should match the identity on the profile.</span></span>  <span data-ttu-id="74721-118">그렇지 않으면 다음 스크린샷과 같은 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="74721-118">If it doesn't, you'll see a message like the one in the next screenshot.</span></span> <span data-ttu-id="74721-119">스크린샷 예에서 "testadmin@evostsoneboxtest.com"은 리소스에 액세스하는 데 필요한 로그인 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="74721-119">In the screenshot example, "testadmin@evostsoneboxtest.com" is the sign-in account needed to access the resource.</span></span>

![브라우저의 조건부 액세스 메시지](./media/edge-security/microsoft-edge-security-conditional-access.png)

<span data-ttu-id="74721-121">계속하려면 필요한 프로필(있는 경우)로 전환하거나 일치하는 ID를 사용하여 프로필을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74721-121">To continue, you have to switch to the required profile (if you have one) or create a profile with matching identity.</span></span>

<span data-ttu-id="74721-122">로그인하고 프로필 작업을 수행하려면 브라우저의 오른쪽 위 모서리에 있는 계정 사진을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="74721-122">To sign in and work with your profile, click the account picture in the top right corner of the browser.</span></span> <span data-ttu-id="74721-123">드롭다운 메뉴를 사용하여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74721-123">You can use the dropdown menu to:</span></span>

- <span data-ttu-id="74721-124">다른 프로필을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="74721-124">Select another profile.</span></span> <span data-ttu-id="74721-125">프로필 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="74721-125">Click the profile name.</span></span>
- <span data-ttu-id="74721-126">프로필을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="74721-126">Create a profile.</span></span> <span data-ttu-id="74721-127">**프로필 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="74721-127">Click **Add a profile**.</span></span>
- <span data-ttu-id="74721-128">프로필을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="74721-128">Manage your profiles.</span></span> <span data-ttu-id="74721-129">**프로필 설정 관리**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="74721-129">Click **Manage profile settings**.</span></span>

<span data-ttu-id="74721-130">이 지원은 모든 지원되는 Windows 및 macOS 버전을 포함하여 모든 플랫폼에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74721-130">This support is available across all platforms, including all supported versions of Windows and macOS.</span></span>

### <span data-ttu-id="74721-131">Azure Active Directory에서 조건부 액세스를 배포하는 방법</span><span class="sxs-lookup"><span data-stu-id="74721-131">How to deploy Conditional Access in Azure Active Directory</span></span>

<span data-ttu-id="74721-132">[조건부 액세스 배포](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access)는 Azure Active Directory에서 조건부 액세스를 배포할 수 있는 자세한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="74721-132">[Deploy Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) provides a detailed guide to help deploy Conditional Access in Azure Active Directory.</span></span>

## <span data-ttu-id="74721-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="74721-133">See also</span></span>

- [<span data-ttu-id="74721-134">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="74721-134">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="74721-135">비디오: 보안, 호환성 및 관리 용이성</span><span class="sxs-lookup"><span data-stu-id="74721-135">Video: Security, compatibility, and manageability</span></span>](/microsoft-edge-video-security-compatibility-manageability.md)
