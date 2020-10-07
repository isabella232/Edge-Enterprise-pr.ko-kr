---
title: AD(Active Directory) 사용자를 위한 온-프레미스 동기화
ms.author: scottbo
author: dan-wesley
manager: silvanam
ms.date: 10/05/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: AD(Active Directory) 사용자를 위한 온-프레미스 동기화
ms.openlocfilehash: ce7fd912bc8cbd71e12444d58073e43df6b138db
ms.sourcegitcommit: bd68077356a944b99a424d03b444b04aa60272dd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2020
ms.locfileid: "11099747"
---
# <span data-ttu-id="4b70c-103">AD(Active Directory) 사용자를 위한 온-프레미스 동기화</span><span class="sxs-lookup"><span data-stu-id="4b70c-103">On-premises sync for Active Directory (AD) users</span></span>

<span data-ttu-id="4b70c-104">이 문서에서는 AD(Active Directory) 사용자가 Microsoft 클라우드 서비스에 연결하지 않고 Microsoft Edge 즐겨찾기 및 컴퓨터 설정을 로밍하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4b70c-104">This article explains how Active Directory (AD) users can roam Microsoft Edge favorites and settings between computers without connecting to Microsoft cloud services.</span></span>

> [!NOTE]
> <span data-ttu-id="4b70c-105">이 문서는 Microsoft Edge 버전 85 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b70c-105">This article applies to Microsoft Edge version 85 or later.</span></span>

## <span data-ttu-id="4b70c-106">소개</span><span class="sxs-lookup"><span data-stu-id="4b70c-106">Introduction</span></span>

<span data-ttu-id="4b70c-107">Microsoft Edge에서 사용자 데이터를 동기화하려면 일반적으로 Microsoft 계정 또는 Azure Active Directory(Azure AD) 계정과 Microsoft 클라우드 서비스에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b70c-107">Syncing user data in Microsoft Edge normally requires either a Microsoft Account or an Azure Active Directory (Azure AD) account, and a connection to Microsoft cloud services.</span></span> <span data-ttu-id="4b70c-108">Microsoft Edge는 온-프레미스 동기화를 통해 Active Directory 사용자의 즐겨찾기 및 설정을 서로 다른 컴퓨터 간에 이동할 수 있는 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="4b70c-108">With on-premises sync, Microsoft Edge saves an Active Directory user's favorites and settings to a file that can be moved between different computers.</span></span> <span data-ttu-id="4b70c-109">온-프레미스 동기화는 이를 허용하는 프로파일에 대해 클라우드 동기화를 방해하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4b70c-109">On-premises sync doesn't interfere with cloud syncing for those profiles that allow it.</span></span>

## <span data-ttu-id="4b70c-110">작동 방식</span><span class="sxs-lookup"><span data-stu-id="4b70c-110">How it works</span></span>

<span data-ttu-id="4b70c-111">Microsoft Edge를 사용하면 프로필을 AD(Active Directory) 계정에 연결할 수 있으므로 클라우드 동기화에 사용할 수 없습니다. 온-프레미스 동기화를 사용하도록 설정하면 AD 프로필의 데이터가 profile.pb라는 파일에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b70c-111">Microsoft Edge allows profiles to be associated with Active Directory (AD) accounts, which can't be used with cloud sync. When on-premises sync is enabled, the data from the AD profile is saved to a file named profile.pb.</span></span> <span data-ttu-id="4b70c-112">기본적으로 이 파일은 *%APPDATA%/Microsoft/Edge*에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b70c-112">By default, this file is stored in *%APPDATA%/Microsoft/Edge*.</span></span> <span data-ttu-id="4b70c-113">이 파일을 작성한 후 다른 컴퓨터 간에 파일을 이동할 수 있으며 각 컴퓨터에서 사용자 데이터를 읽고 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b70c-113">After this file is written, it can be moved between different computers, and user data will be read and written on each computer.</span></span>

## <span data-ttu-id="4b70c-114">온-프레미스 동기화 사용</span><span class="sxs-lookup"><span data-stu-id="4b70c-114">Use on-premises sync</span></span>

<span data-ttu-id="4b70c-115">온-프레미스 동기화를 사용하려면 동기화를 활성화하고, 프로파일을 AD 계정에 연결한 후 선택적으로 사용자 데이터의 위치를 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b70c-115">To use on-premises sync, you have to enable it, associate a profile with an AD account, and optionally, change the location of the user data.</span></span>

### <span data-ttu-id="4b70c-116">온-프레미스 동기화 사용</span><span class="sxs-lookup"><span data-stu-id="4b70c-116">Enable on-premises sync</span></span>

<span data-ttu-id="4b70c-117">Microsoft Edge에서 온사이트 동기화를 사용하도록 설정하려면[RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled) 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4b70c-117">To enable on-premises sync in Microsoft Edge, configure the [RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled) policy.</span></span>

### <span data-ttu-id="4b70c-118">프로필이 Active Directory 계정과 연결되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4b70c-118">Ensure that a profile is associated with an Active Directory account</span></span>

<span data-ttu-id="4b70c-119">온-프레미스 동기화는 AD(Active Directory) 계정과 연결된 프로필에서만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="4b70c-119">On-premises sync only works with the profile associated with an Active Directory (AD) account.</span></span> <span data-ttu-id="4b70c-120">이러한 프로필이 없으면 온-프레미스 동기화가 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4b70c-120">If no such profile exists, on-premises sync will not function.</span></span> <span data-ttu-id="4b70c-121">사용자가 AD 계정으로 로그온하도록 하려면 [ConfigureOnPremisesAccountAutoSignIn](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#configureonpremisesaccountautosignin) 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4b70c-121">To ensure that users sign on with an AD account, configure the [ConfigureOnPremisesAccountAutoSignIn](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#configureonpremisesaccountautosignin) policy.</span></span>

### <span data-ttu-id="4b70c-122">사용자 데이터의 위치 변경(선택적)</span><span class="sxs-lookup"><span data-stu-id="4b70c-122">Change the location of the user data (optional)</span></span>

<span data-ttu-id="4b70c-123">기본적으로 사용자 데이터는 *%APPDATA%/Microsoft/Edge*에 있는 **profile.pb**라는 이름의 파일에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b70c-123">By default, the user data is stored in a filed named **profile.pb** in *%APPDATA%/Microsoft/Edge*.</span></span> <span data-ttu-id="4b70c-124">이 파일의 위치를 변경하려면[RoamingProfileLocation](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilelocation) 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4b70c-124">To change the location of this file, configure the [RoamingProfileLocation](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilelocation) policy.</span></span>

## <span data-ttu-id="4b70c-125">온-프레미스 동기화를 사용하도록 설정한 경우 사용자 환경이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b70c-125">Changes in the user experience when on-premises sync is enabled</span></span>

<span data-ttu-id="4b70c-126">온-프레미스 동기화를 사용하도록 설정하면 사용자에게 동기화를 사용하도록 요청되지 않습니다. 또한 사용자는 동기화 설정에서 동기화를 해제할 수 없으며 온-프레미스 동기화가 지원하지 않는 동기화 유형을 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4b70c-126">When on-premises sync is enabled, users won't be asked to enable sync. In addition, users can't turn off sync in Sync settings, and they can't turn on sync types that aren't supported by on-premises sync.</span></span>

## <span data-ttu-id="4b70c-127">사내에서 사용 정보를 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="4b70c-127">On-premises sync usage notes</span></span>

### <span data-ttu-id="4b70c-128">동일한 컴퓨터에서 클라우드 동기화 및 온-프레미스 동기화를 실행하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b70c-128">Running cloud sync and on-premises sync on the same computer</span></span>

<span data-ttu-id="4b70c-129">온-프레미스 동기화는 클라우드 동기화를 방해하지 않습니다. Microsoft Edge에 클라우드에 동기화하는 여러 Microsoft 계정 또는 Azure Active Directory 프로파일이 있는 경우 온-프레미스 동기화가 설정된 동안 이러한 프로파일이 계속 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b70c-129">On-premises sync doesn't interfere with cloud sync. If Microsoft Edge has multiple Microsoft Account or Azure Active Directory profiles that sync to the cloud, these profiles will continue to sync while on-premises sync is enabled.</span></span>

### <span data-ttu-id="4b70c-130">한 번에 둘 이상의 컴퓨터에서 Microsoft Edge를 실행하는 것은 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4b70c-130">Running Microsoft Edge on more than one computer at a time isn't recommended</span></span>

<span data-ttu-id="4b70c-131">온-프레미스 동기화는 컴퓨터 간에 사용자 데이터 파일을 이동하는 방식으로 작동하므로 온-프레미스 동기화는 동시 세션 간의 변경 내용을 동기화하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4b70c-131">Because on-premises sync works by moving a user data file between computers, on-premises sync doesn't sync changes between simultaneous sessions.</span></span> <span data-ttu-id="4b70c-132">이러한 이유로 한 번에 한 대의 컴퓨터에서 사용할 경우 온-프레미스 동기화가 가장 잘 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="4b70c-132">For this reason, on-premises sync works best when used on one computer at a time.</span></span> <span data-ttu-id="4b70c-133">동시에 실행되는 온-프레미스 세션이 있는 경우 다음에 브라우저 세션을 시작할 때 컴퓨터의 데이터를 다른 컴퓨터의 데이터로 예기치 않게 덮어쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b70c-133">If there are simultaneous on-premises sessions running, data on any of the computers may be unexpectedly overwritten by data from another computer the next time you start a browser session.</span></span>

> [!NOTE]
> <span data-ttu-id="4b70c-134">온-프레미스 동기화를 사용하도록 설정하면 Microsoft Edge가 **profile.pb** 파일을 잠급니다.</span><span class="sxs-lookup"><span data-stu-id="4b70c-134">Microsoft Edge locks the **profile.pb** file when on-premises sync is enabled.</span></span> <span data-ttu-id="4b70c-135">폴더 리디렉션을 사용하여 서로 다른 시스템 간에 단일 **profile.pb** 파일을 공유하는 경우 해당 파일을 사용하는 Microsoft Edge 인스턴스 하나만 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b70c-135">If folder redirection is used to share a single **profile.pb** file between different computers, then only one instance of Microsoft Edge using that file can be started.</span></span>

### <span data-ttu-id="4b70c-136">온-프레미스 동기화와 함께 다른 동기화 정책을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4b70c-136">Using other sync policies with on-premises sync</span></span>

<span data-ttu-id="4b70c-137">[SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled) 정책을 사용하여 원하는 경우 즐겨찾기 또는 설정 동기화를 선택적으로 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b70c-137">The [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled) policy can be used to selectively disable either favorites or settings sync if desired.</span></span> <span data-ttu-id="4b70c-138">[SyncDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#syncdisabled) 정책이 활성 상태인 경우 온-프레미스 동기화도 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b70c-138">If the [SyncDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#syncdisabled) policy is active, then on-premises sync is disabled as well.</span></span>  

## <span data-ttu-id="4b70c-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b70c-139">See also</span></span>

- [<span data-ttu-id="4b70c-140">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="4b70c-140">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="4b70c-141">Microsoft Edge 및 Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="4b70c-141">Microsoft Edge and Enterprise State Roaming</span></span>](microsoft-edge-enterprise-state-roaming.md)
- [<span data-ttu-id="4b70c-142">Microsoft Edge Enterprise Sync</span><span class="sxs-lookup"><span data-stu-id="4b70c-142">Microsoft Edge Enterprise Sync</span></span>](microsoft-edge-enterprise-sync.md)
