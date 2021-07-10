---
title: AD(Active Directory) 사용자를 위한 온-프레미스 동기화
ms.author: collw
author: dan-wesley
manager: silvanam
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: AD(Active Directory) 사용자를 위한 온-프레미스 동기화
ms.openlocfilehash: f595c863193f2b3d383a6215ab7817a53bbf5ca6
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642444"
---
# <a name="on-premises-sync-for-active-directory-ad-users"></a><span data-ttu-id="fb0d9-103">AD(Active Directory) 사용자를 위한 온-프레미스 동기화</span><span class="sxs-lookup"><span data-stu-id="fb0d9-103">On-premises sync for Active Directory (AD) users</span></span>

<span data-ttu-id="fb0d9-104">이 문서에서는 AD(Active Directory) 사용자가 Microsoft 클라우드 서비스에 연결하지 않고 Microsoft Edge 즐겨찾기 및 컴퓨터 설정을 로밍하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-104">This article explains how Active Directory (AD) users can roam Microsoft Edge favorites and settings between computers without connecting to Microsoft cloud services.</span></span>

> [!NOTE]
> <span data-ttu-id="fb0d9-105">이 문서는 Microsoft Edge 버전 85 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-105">This article applies to Microsoft Edge version 85 or later.</span></span>

## <a name="introduction"></a><span data-ttu-id="fb0d9-106">소개</span><span class="sxs-lookup"><span data-stu-id="fb0d9-106">Introduction</span></span>

<span data-ttu-id="fb0d9-107">Microsoft Edge에서 사용자 데이터를 동기화하려면 일반적으로 Microsoft 계정 또는 Azure Active Directory(Azure AD) 계정과 Microsoft 클라우드 서비스에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-107">Syncing user data in Microsoft Edge normally requires either a Microsoft Account or an Azure Active Directory (Azure AD) account, and a connection to Microsoft cloud services.</span></span> <span data-ttu-id="fb0d9-108">Microsoft Edge는 온-프레미스 동기화를 통해 Active Directory 사용자의 즐겨찾기 및 설정을 서로 다른 컴퓨터 간에 이동할 수 있는 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-108">With on-premises sync, Microsoft Edge saves an Active Directory user's favorites and settings to a file that can be moved between different computers.</span></span> <span data-ttu-id="fb0d9-109">온-프레미스 동기화는 이를 허용하는 프로파일에 대해 클라우드 동기화를 방해하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-109">On-premises sync doesn't interfere with cloud syncing for those profiles that allow it.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="fb0d9-110">작동 방식</span><span class="sxs-lookup"><span data-stu-id="fb0d9-110">How it works</span></span>

<span data-ttu-id="fb0d9-111">Microsoft Edge를 사용하면 프로필을 AD(Active Directory) 계정에 연결할 수 있으므로 클라우드 동기화에 사용할 수 없습니다. 온-프레미스 동기화를 사용하도록 설정하면 AD 프로필의 데이터가 profile.pb라는 파일에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-111">Microsoft Edge allows profiles to be associated with Active Directory (AD) accounts, which can't be used with cloud sync. When on-premises sync is enabled, the data from the AD profile is saved to a file named profile.pb.</span></span> <span data-ttu-id="fb0d9-112">기본적으로 이 파일은 *%APPDATA%/Microsoft/Edge*에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-112">By default, this file is stored in *%APPDATA%/Microsoft/Edge*.</span></span> <span data-ttu-id="fb0d9-113">이 파일을 작성한 후 다른 컴퓨터 간에 파일을 이동할 수 있으며 각 컴퓨터에서 사용자 데이터를 읽고 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-113">After this file is written, it can be moved between different computers, and user data will be read and written on each computer.</span></span> <span data-ttu-id="fb0d9-114">Microsoft Edge는 이 파일에서만 읽기 및 쓰기를 합니다. 필요에 따라 파일이 이동되는지 확인하는 것은 관리자의 책임입니다.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-114">Microsoft Edge only reads and writes from this file; it is the admin's responsibility to ensure that the file is moved as needed.</span></span>

## <a name="use-on-premises-sync"></a><span data-ttu-id="fb0d9-115">온-프레미스 동기화 사용</span><span class="sxs-lookup"><span data-stu-id="fb0d9-115">Use on-premises sync</span></span>

<span data-ttu-id="fb0d9-116">온-프레미스 동기화를 사용하려면 동기화를 활성화하고, 프로파일을 AD 계정에 연결한 후 선택적으로 사용자 데이터의 위치를 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-116">To use on-premises sync, you have to enable it, associate a profile with an AD account, and optionally, change the location of the user data.</span></span>

### <a name="enable-on-premises-sync"></a><span data-ttu-id="fb0d9-117">온-프레미스 동기화 사용</span><span class="sxs-lookup"><span data-stu-id="fb0d9-117">Enable on-premises sync</span></span>

<span data-ttu-id="fb0d9-118">Microsoft Edge에서 온사이트 동기화를 사용하도록 설정하려면[RoamingProfileSupportEnabled](./microsoft-edge-policies.md#roamingprofilesupportenabled) 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-118">To enable on-premises sync in Microsoft Edge, configure the [RoamingProfileSupportEnabled](./microsoft-edge-policies.md#roamingprofilesupportenabled) policy.</span></span>

### <a name="ensure-that-a-profile-is-associated-with-an-active-directory-account"></a><span data-ttu-id="fb0d9-119">프로필이 Active Directory 계정과 연결되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-119">Ensure that a profile is associated with an Active Directory account</span></span>

<span data-ttu-id="fb0d9-120">온-프레미스 동기화는 AD(Active Directory) 계정과 연결된 프로필에서만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-120">On-premises sync only works with the profile associated with an Active Directory (AD) account.</span></span> <span data-ttu-id="fb0d9-121">이러한 프로필이 없으면 온-프레미스 동기화가 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-121">If no such profile exists, on-premises sync will not function.</span></span> <span data-ttu-id="fb0d9-122">사용자가 AD 계정으로 로그인하도록 하려면 [ConfigureOnPremisesAccountAutoSignIn](./microsoft-edge-policies.md#configureonpremisesaccountautosignin) 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-122">To ensure that users sign on with an AD account, configure the [ConfigureOnPremisesAccountAutoSignIn](./microsoft-edge-policies.md#configureonpremisesaccountautosignin) policy.</span></span> <span data-ttu-id="fb0d9-123">온-프레미스 동기화의 경우 Microsoft Edge는 AD에만 의존하여 사용자 데이터에 대한 ID를 설정하며 Microsoft Edge가 온-프레미스 데이터를 읽고 쓰는 방법과 관리자가 AD 사용자에 대해 로밍을 구성한 방법 간에는 직접적인 관계가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-123">For on-premises sync, Microsoft Edge only relies on AD to establish an identity for the user data, and there's no direct relationship between how Microsoft Edge reads and writes on-premises data to how the admin has configured roaming for an AD user.</span></span>

### <a name="change-the-location-of-the-user-data-optional"></a><span data-ttu-id="fb0d9-124">사용자 데이터의 위치 변경(선택적)</span><span class="sxs-lookup"><span data-stu-id="fb0d9-124">Change the location of the user data (optional)</span></span>

<span data-ttu-id="fb0d9-125">기본적으로 사용자 데이터는 *%APPDATA%/Microsoft/Edge*에 있는 **profile.pb**라는 이름의 파일에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-125">By default, the user data is stored in a filed named **profile.pb** in *%APPDATA%/Microsoft/Edge*.</span></span> <span data-ttu-id="fb0d9-126">이 파일의 위치를 변경하려면[RoamingProfileLocation](./microsoft-edge-policies.md#roamingprofilelocation) 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-126">To change the location of this file, configure the [RoamingProfileLocation](./microsoft-edge-policies.md#roamingprofilelocation) policy.</span></span>

## <a name="changes-in-the-user-experience-when-on-premises-sync-is-enabled"></a><span data-ttu-id="fb0d9-127">온-프레미스 동기화를 사용하도록 설정한 경우 사용자 환경이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-127">Changes in the user experience when on-premises sync is enabled</span></span>

<span data-ttu-id="fb0d9-128">온-프레미스 동기화를 사용하도록 설정하면 사용자에게 동기화를 사용하도록 요청되지 않습니다. 또한 사용자는 동기화 설정에서 동기화를 해제할 수 없으며 온-프레미스 동기화가 지원하지 않는 동기화 유형을 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-128">When on-premises sync is enabled, users won't be asked to enable sync. In addition, users can't turn off sync in Sync settings, and they can't turn on sync types that aren't supported by on-premises sync.</span></span>

## <a name="on-premises-sync-usage-notes"></a><span data-ttu-id="fb0d9-129">사내에서 사용 정보를 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-129">On-premises sync usage notes</span></span>

### <a name="running-cloud-sync-and-on-premises-sync-on-the-same-computer"></a><span data-ttu-id="fb0d9-130">동일한 컴퓨터에서 클라우드 동기화 및 온-프레미스 동기화를 실행하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-130">Running cloud sync and on-premises sync on the same computer</span></span>

<span data-ttu-id="fb0d9-131">온-프레미스 동기화는 클라우드 동기화를 방해하지 않습니다. Microsoft Edge에 클라우드에 동기화하는 여러 Microsoft 계정 또는 Azure Active Directory 프로파일이 있는 경우 온-프레미스 동기화가 설정된 동안 이러한 프로파일이 계속 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-131">On-premises sync doesn't interfere with cloud sync. If Microsoft Edge has multiple Microsoft Account or Azure Active Directory profiles that sync to the cloud, these profiles will continue to sync while on-premises sync is enabled.</span></span>

### <a name="running-microsoft-edge-on-more-than-one-computer-at-a-time-isnt-recommended"></a><span data-ttu-id="fb0d9-132">한 번에 둘 이상의 컴퓨터에서 Microsoft Edge를 실행하는 것은 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-132">Running Microsoft Edge on more than one computer at a time isn't recommended</span></span>

<span data-ttu-id="fb0d9-133">온-프레미스 동기화는 컴퓨터 간에 사용자 데이터 파일을 이동하는 방식으로 작동하므로 온-프레미스 동기화는 동시 세션 간의 변경 내용을 동기화하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-133">Because on-premises sync works by moving a user data file between computers, on-premises sync doesn't sync changes between simultaneous sessions.</span></span> <span data-ttu-id="fb0d9-134">이러한 이유로 한 번에 한 대의 컴퓨터에서 사용할 경우 온-프레미스 동기화가 가장 잘 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-134">For this reason, on-premises sync works best when used on one computer at a time.</span></span> <span data-ttu-id="fb0d9-135">동시에 실행되는 온-프레미스 세션이 있는 경우 다음에 브라우저 세션을 시작할 때 컴퓨터의 데이터를 다른 컴퓨터의 데이터로 예기치 않게 덮어쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-135">If there are simultaneous on-premises sessions running, data on any of the computers may be unexpectedly overwritten by data from another computer the next time you start a browser session.</span></span>

> [!NOTE]
> <span data-ttu-id="fb0d9-136">온-프레미스 동기화를 사용하도록 설정하면 Microsoft Edge가 **profile.pb** 파일을 잠급니다.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-136">Microsoft Edge locks the **profile.pb** file when on-premises sync is enabled.</span></span> <span data-ttu-id="fb0d9-137">폴더 리디렉션을 사용하여 서로 다른 시스템 간에 단일 **profile.pb** 파일을 공유하는 경우 해당 파일을 사용하는 Microsoft Edge 인스턴스 하나만 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-137">If folder redirection is used to share a single **profile.pb** file between different computers, then only one instance of Microsoft Edge using that file can be started.</span></span>

### <a name="using-other-sync-policies-with-on-premises-sync"></a><span data-ttu-id="fb0d9-138">온-프레미스 동기화와 함께 다른 동기화 정책을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-138">Using other sync policies with on-premises sync</span></span>

<span data-ttu-id="fb0d9-139">[SyncTypesListDisabled](./microsoft-edge-policies.md#synctypeslistdisabled) 정책을 사용하여 원하는 경우 즐겨찾기 또는 설정 동기화를 선택적으로 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-139">The [SyncTypesListDisabled](./microsoft-edge-policies.md#synctypeslistdisabled) policy can be used to selectively disable either favorites or settings sync if desired.</span></span> <span data-ttu-id="fb0d9-140">[SyncDisabled](./microsoft-edge-policies.md#syncdisabled) 정책은 온-프레미스 동기화에 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-140">The [SyncDisabled](./microsoft-edge-policies.md#syncdisabled) policy has no impact on on-premises sync.</span></span>

## <a name="see-also"></a><span data-ttu-id="fb0d9-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fb0d9-141">See also</span></span>

- [<span data-ttu-id="fb0d9-142">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="fb0d9-142">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="fb0d9-143">Microsoft Edge 및 Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="fb0d9-143">Microsoft Edge and Enterprise State Roaming</span></span>](microsoft-edge-enterprise-state-roaming.md)
- [<span data-ttu-id="fb0d9-144">Microsoft Edge Enterprise Sync</span><span class="sxs-lookup"><span data-stu-id="fb0d9-144">Microsoft Edge Enterprise Sync</span></span>](microsoft-edge-enterprise-sync.md)