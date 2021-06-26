---
title: 엔터프라이즈용 Microsoft Edge 롤백
ms.author: collw
author: dan-wesley
manager: srugh
ms.date: 02/04/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge를 이전 버전으로 롤백하는 방법
ms.openlocfilehash: 38954f4b293470758b5484591779a3af52c6992c
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2021
ms.locfileid: "11617378"
---
# <a name="how-to-roll-back-microsoft-edge-to-a-previous-version"></a><span data-ttu-id="8ec3d-103">Microsoft Edge를 이전 버전으로 롤백하는 방법</span><span class="sxs-lookup"><span data-stu-id="8ec3d-103">How to roll back Microsoft Edge to a previous version</span></span>

<span data-ttu-id="8ec3d-104">이 문서에서는 롤백 기능을 사용하여 이전 버전의 Microsoft Edge로 롤백하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-104">This article describes how to roll back to a previous version of Microsoft Edge using the rollback feature.</span></span> <span data-ttu-id="8ec3d-105">이 기능에 대한 자세한 내용은 [비디오: Microsoft Edge 버전 롤백](microsoft-edge-video-version-rollback.md)을 시청하세요.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-105">To learn more about this feature, watch [Video: Microsoft Edge version rollback](microsoft-edge-video-version-rollback.md).</span></span>

>[!NOTE]
><span data-ttu-id="8ec3d-106">이 문서는 Microsoft Edge 버전 86 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-106">This article applies to Microsoft Edge version 86 or later.</span></span>

## <a name="introduction-to-rollback"></a><span data-ttu-id="8ec3d-107">롤백 소개</span><span class="sxs-lookup"><span data-stu-id="8ec3d-107">Introduction to rollback</span></span>

<span data-ttu-id="8ec3d-108">롤백을 사용하면 Microsoft Edge 브라우저 버전을 이전 버전으로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-108">Rollback lets you replace your Microsoft Edge browser version with an earlier version.</span></span> <span data-ttu-id="8ec3d-109">이 기능은 Microsoft Edge를 배포하는 기업을 위한 안전망으로 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-109">This feature is designed to be a safety net for enterprises deploying Microsoft Edge.</span></span> <span data-ttu-id="8ec3d-110">Microsoft Edge에 발생하는 문제를 해결하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-110">It provides a way to troubleshoot issues with Microsoft Edge.</span></span> <span data-ttu-id="8ec3d-111">롤백의 이점은 이전 브라우저 버전으로 쉽고 빠르게 전환할 수 있다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-111">The benefits of rollback are the ability to revert to previous browser version easily and quickly.</span></span> <span data-ttu-id="8ec3d-112">롤백을 수행하면 비즈니스 운영에 미치는 Microsoft Edge 문제의 잠재적인 영향을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-112">Rollback reduces the potential impact that a Microsoft Edge issue has on business operations.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="8ec3d-113">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="8ec3d-113">Before you begin</span></span>

<span data-ttu-id="8ec3d-114">롤백 기능이 Microsoft Edge 환경에 설치되는 방법을 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-114">It's important to understand how the rollback feature is installed in a Microsoft Edge environment.</span></span> <span data-ttu-id="8ec3d-115">직접 MSI를 사용하거나 Microsoft Edge 업데이트와 그룹 정책을 사용하여 다른 두 가지 방법을 사용하여 롤백을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-115">You can deploy rollback using two different methods: manually with an MSI or by using Microsoft Edge update and Group Policy.</span></span> <span data-ttu-id="8ec3d-116">또한 보다 원활한 배포를 위해 다양한 그룹 정책을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-116">We also wencourage using a selection of Group Policies for a smoother deployment.</span></span>

### <a name="recommendations"></a><span data-ttu-id="8ec3d-117">권장 사항</span><span class="sxs-lookup"><span data-stu-id="8ec3d-117">Recommendations</span></span>

<span data-ttu-id="8ec3d-118">롤백 기능은 Microsoft Edge 브라우저 업데이트에서 발생할 수 있는 문제를 해결 하는 임시 수정 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-118">The rollback feature is meant to be a temporary fix for issues you might find in a Microsoft Edge browser update.</span></span> <span data-ttu-id="8ec3d-119">최신 버전의 Microsoft Edge 브라우저를 설치하여 최신 보안 업데이트에서 제공하는 보호를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-119">We recommend that users install the latest version of the Microsoft Edge browser to use the protection provided by the latest security updates.</span></span> <span data-ttu-id="8ec3d-120">이전 버전으로 롤백하면 알려진 보안 문제에 노출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-120">Rollback to an earlier version risks exposure to known security issues.</span></span>

<span data-ttu-id="8ec3d-121">브라우저 버전을 일시적으로 롤백하려면 먼저 조직의 모든 사용자에 대해 동기화를 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-121">Before temporarily rolling back your browser version, we also highly recommend that you enable Sync for all the users in your organization.</span></span> <span data-ttu-id="8ec3d-122">동기화를 설정하지 않은 경우 영구적 검색 데이터 손실이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-122">If you don't turn on Sync, there's a risk of permanent browsing data loss.</span></span> <span data-ttu-id="8ec3d-123">동기화에 대한 자세한 내용은 [Microsoft Edge 동기화](microsoft-edge-enterprise-sync.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-123">For more information about Sync, see [Microsoft Edge Sync](microsoft-edge-enterprise-sync.md).</span></span>

> [!CAUTION]
> <span data-ttu-id="8ec3d-124">필요한 경우에만 롤백을 사용하세요. 항상 데이터가 손실될 위험이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-124">Only use rollback when necessary, there's always the risk of data loss.</span></span>

## <a name="enable-rollback-manually-with-an-msi"></a><span data-ttu-id="8ec3d-125">MSI를 사용하여 수동으로 롤백 설정</span><span class="sxs-lookup"><span data-stu-id="8ec3d-125">Enable rollback manually with an MSI</span></span>

<span data-ttu-id="8ec3d-126">MSI를 사용하여 수동으로 롤백하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-126">Use the following steps to roll back manually with an MSI.</span></span>

1. <span data-ttu-id="8ec3d-127">Microsoft Edge 업데이트를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-127">Disable Microsoft Edge Updates.</span></span>

   > [!NOTE]
   > <span data-ttu-id="8ec3d-128">최신 관리 템플릿을 설치하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-128">We recommend that you install the most current Administrative templates.</span></span> <span data-ttu-id="8ec3d-129">자세한 내용은 [Microsoft Edge 관리 템플릿 다운로드 및 설치](./configure-microsoft-edge.md#1-download-and-install-the-microsoft-edge-administrative-template)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-129">For more information, see [Download and install the Microsoft Edge administrative template](./configure-microsoft-edge.md#1-download-and-install-the-microsoft-edge-administrative-template).</span></span>

   - <span data-ttu-id="8ec3d-130">로컬 그룹 정책 편집기를 열고 *컴퓨터 구성>관리 템플릿>Microsoft Edge 업데이트>응용 프로그램>Microsoft Edge>* 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-130">Open the local Group Policy Editor and go to *Computer Configuration>Administrative Templates>Microsoft Edge Update>Applications>Microsoft Edge>*.</span></span>
   - <span data-ttu-id="8ec3d-131">**업데이트 정책 재정의**을 선택한 다음 **사용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-131">Select **Update policy override** and then select **Enabled**.</span></span>
   - <span data-ttu-id="8ec3d-132">**옵션**의 정책 드롭다운 목록에서 **업데이트 사용 안 함**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-132">Under **Options**, pick **Update disabled** from the Policy dropdown list.</span></span>

2. <span data-ttu-id="8ec3d-133">MSI를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-133">Get the MSI.</span></span>

   - <span data-ttu-id="8ec3d-134">[여기](https://www.microsoft.com/edge/business/download)에서 롤백할 버전용 MSI를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-134">Download the MSI for the version you want to roll back to [from here](https://www.microsoft.com/edge/business/download).</span></span>
   - <span data-ttu-id="8ec3d-135">MSI를 바탕 화면에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-135">Save the MSI to your desktop.</span></span>

3. <span data-ttu-id="8ec3d-136">Rollback 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-136">Run the rollback command.</span></span>

   - <span data-ttu-id="8ec3d-137">**관리자 권한으로 실행**을 사용하여 Windows 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-137">Open the Windows command prompt with **Run as administrator**.</span></span>
   - <span data-ttu-id="8ec3d-138">다음 명령을 입력합니다. 여기서 *C:\Users\username\Desktop\test* 는 다운로드한 MSI 경로이고 파일 이름은 .msi 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-138">Type the following command, where: *C:\Users\username\Desktop\test* is the path to the MSI you downloaded, and FileName is the name of the .msi file:</span></span><br>
 `C:\Users\username\Desktop\test>msiexec /I FileName.msi /qn ALLOWDOWNGRADE=1`<br>
     > [!NOTE]
     > <span data-ttu-id="8ec3d-139">Msiexec에 대한 자세한 내용은 [msiexec](/windows-server/administration/windows-commands/msiexec)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-139">For more information about msiexec, see [msiexec](/windows-server/administration/windows-commands/msiexec).</span></span>
   - <span data-ttu-id="8ec3d-140">Microsoft Edge를 닫고 다시 열어 롤백이 제대로 작동했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-140">Close and reopen Microsoft Edge to verify that the rollback worked.</span></span> <span data-ttu-id="8ec3d-141">**설정 및 추가**(ALT + F)에서 **설정**으로 이동하여 **Microsoft Edge 정보**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-141">Under **Settings and more** (ALT + F), go to **Settings** and select **About Microsoft Edge**.</span></span>

## <a name="enable-rollback-with-microsoft-edge-update-and-group-policy"></a><span data-ttu-id="8ec3d-142">Microsoft Edge 업데이트 및 그룹 정책을 사용하여 롤백 설정</span><span class="sxs-lookup"><span data-stu-id="8ec3d-142">Enable rollback with Microsoft Edge update and Group Policy</span></span>

<span data-ttu-id="8ec3d-143">다음 단계에 따라 Microsoft Edge 업데이트와 그룹 정책을 사용하여 롤백을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-143">Use the following steps to enable rollback with Microsoft Edge update and Group Policy.</span></span>

1. <span data-ttu-id="8ec3d-144">로컬 그룹 정책 편집기를 열고 *컴퓨터 구성>관리 템플릿>Microsoft Edge 업데이트>응용 프로그램>Microsoft Edge>* 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-144">Open the local Group Policy Editor and go to *Computer Configuration>Administrative Templates>Microsoft Edge Update>Applications>Microsoft Edge>*.</span></span>
2. <span data-ttu-id="8ec3d-145">**대상 버전으로 롤백**을 선택하고 **사용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-145">Select **Rollback to target version** and then select **Enabled**.</span></span>
3. <span data-ttu-id="8ec3d-146">**대상 버전 재정의**를 선택하고 롤백할 브라우저 버전을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-146">Select **Target version override** and pick the browser version you want to roll back to.</span></span>
4. <span data-ttu-id="8ec3d-147">**업데이트 정책 재정의**을 선택한 다음 **사용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-147">Select **Update policy override** and then select **Enabled**.</span></span> <span data-ttu-id="8ec3d-148">**옵션**의 정책 드롭다운 목록에서 다음 옵션 중 하나를 선택합니다(**업데이트 사용 안 함** 예외).</span><span class="sxs-lookup"><span data-stu-id="8ec3d-148">Under **Options**, pick one of the following options from the Policy dropdown list (except for **Update disabled**):</span></span>

   - <span data-ttu-id="8ec3d-149">항상 업데이트 허용</span><span class="sxs-lookup"><span data-stu-id="8ec3d-149">Always allow updates</span></span>
   - <span data-ttu-id="8ec3d-150">자동 업데이트만</span><span class="sxs-lookup"><span data-stu-id="8ec3d-150">Automatic silent updates only</span></span>

     > [!NOTE]
     > <span data-ttu-id="8ec3d-151">그룹 정책 업데이트를 강제적으로 실행하려면 `gpupdate /force`Windows 관리자 명령 프롬프트(관리자 권한으로 실행)에 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-151">To force a group policy update, type `gpupdate /force` at the Windows administrator Command Prompt (Run as administrator).</span></span>

5. <span data-ttu-id="8ec3d-152">**확인**을 클릭하여 정책 설정을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-152">Click **OK** to save the policy settings.</span></span> <span data-ttu-id="8ec3d-153">다음에 Microsoft Edge 업데이트에서 업데이트를 확인할 때 롤백이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-153">Rollback will happen the next time Microsoft Edge Update checks for an update.</span></span> <span data-ttu-id="8ec3d-154">업데이트를 바로 수행하려면 Microsoft Edge 업데이트 폴링 간격을 변경하거나 MSI를 사용하여 롤백을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-154">If you want the update to happen sooner, you can change the Microsoft Edge Update polling interval or enable rollback using an MSI.</span></span>

### <a name="common-rollback-errors"></a><span data-ttu-id="8ec3d-155">일반적인 롤백 오류</span><span class="sxs-lookup"><span data-stu-id="8ec3d-155">Common rollback errors</span></span>

<span data-ttu-id="8ec3d-156">다음 오류로 인해 롤백이 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-156">The following errors will prevent rollback:</span></span>

- <span data-ttu-id="8ec3d-157">입력이 지원되지 않는 대상 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-157">Input is an unsupported target version</span></span>
- <span data-ttu-id="8ec3d-158">입력이 존재하지 않는 대상 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-158">Input is a non-existent target version</span></span>
- <span data-ttu-id="8ec3d-159">입력 서식이 잘못 지정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-159">Input is incorrectly formatted</span></span>

### <a name="recommended-group-policies"></a><span data-ttu-id="8ec3d-160">권장되는 그룹 정책</span><span class="sxs-lookup"><span data-stu-id="8ec3d-160">Recommended Group Policies</span></span>

<span data-ttu-id="8ec3d-161">다음 그룹 정책 및 설정은 롤백하는 데 사용하는 것이 매우 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-161">The following group policies and settings are highly recommended for using rollback.</span></span>

#### <a name="sync-group-policies"></a><span data-ttu-id="8ec3d-162">동기화 그룹 정책</span><span class="sxs-lookup"><span data-stu-id="8ec3d-162">Sync Group Policies</span></span>

- <span data-ttu-id="8ec3d-163">ForceSync.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-163">ForceSync.</span></span> <span data-ttu-id="8ec3d-164">ForceSync를 사용으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-164">Set ForceSync to enabled.</span></span> <span data-ttu-id="8ec3d-165">이 정책은 모든 Azure AD(Azure Active Directory) 사용자에 대해 동기화를 강제로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-165">This policy will force enable Sync on all Azure Active Directory (Azure AD) users.</span></span> <span data-ttu-id="8ec3d-166">이 정책은 Microsoft Edge 버전 86 이상에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-166">This policy is only effective for Microsoft Edge versions 86 and later.</span></span>
- <span data-ttu-id="8ec3d-167">*동기화 정책에서 제외되는 유형의 목록 구성*을 사용하여 관리자는 사용자가 동기화할 수 있는 데이터를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-167">The *Configure the list of the types that are excluded from synchronization policy* allows admins to control what data can be synced by users.</span></span>

#### <a name="browser-restart-group-policies"></a><span data-ttu-id="8ec3d-168">브라우저 다시 시작 그룹 정책</span><span class="sxs-lookup"><span data-stu-id="8ec3d-168">Browser restart Group Policies</span></span>

<span data-ttu-id="8ec3d-169">롤백을 사용하도록 설정한 사용자가 다시 시작하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-169">We recommend forcing a restart on users after rollback is enabled.</span></span>

- <span data-ttu-id="8ec3d-170">*사용자에게 보류 중인 업데이트에 대해 브라우저의 재시작을 권장하거나 필요함을 알림*을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-170">Enable *Notify a user that a browser restart is recommended or required for pending updates*.</span></span> <span data-ttu-id="8ec3d-171">옵션에서 **필수**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-171">Under Options, select **Required**.</span></span>
- <span data-ttu-id="8ec3d-172">*업데이트 알림 기간 설정*을 사용하도록 설정한 다음 원하는 시간(밀리초)을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-172">Enable *Set the time period for update notifications* and then set the desired time in milliseconds.</span></span>

## <a name="snapshot"></a><span data-ttu-id="8ec3d-173">스냅샷</span><span class="sxs-lookup"><span data-stu-id="8ec3d-173">Snapshot</span></span>

<span data-ttu-id="8ec3d-174">스냅샷은 사용자 데이터 폴더의 버전 스탬프 사본입니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-174">A snapshot is a version stamped copy of the user data folder.</span></span> <span data-ttu-id="8ec3d-175">버전 업그레이드 중에는 이전 버전의 스냅샷이 만들어져 스냅샷 폴더에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-175">During a version upgrade, a snapshot of the previous version is made and stored in the snapshot folder.</span></span> <span data-ttu-id="8ec3d-176">롤백이 발생하면 버전이 일치하는 스냅샷이 새 사용자 데이터 폴더에 복사되고 스냅샷 폴더에서 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-176">After rollback occurs, a version matched snapshot will be copied into the new user data folder and deleted from the snapshot folder.</span></span> <span data-ttu-id="8ec3d-177">다운그레이드할 때 버전과 일치하는 스냅샷을 사용할 수 없는 경우 롤백은 동기화를 사용하여 사용자 데이터를 새 Microsoft Edge 버전에 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-177">If no version matched snapshot is available upon downgrade, rollback will rely on Sync to populate user data into the new Microsoft Edge version.</span></span>

<span data-ttu-id="8ec3d-178">[UserDataSnapshotRetentionLimit](./microsoft-edge-policies.md#userdatasnapshotretentionlimit) 그룹 정책을 사용하여 지정된 시간에 보존할 수 있는 스냅샷 수 제한을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-178">The [UserDataSnapshotRetentionLimit](./microsoft-edge-policies.md#userdatasnapshotretentionlimit) group policy allows you to set a limit for the number of snapshots that can be retained at any given time.</span></span> <span data-ttu-id="8ec3d-179">기본적으로 세 개의 스냅샷이 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-179">By default, three snapshots are kept.</span></span> <span data-ttu-id="8ec3d-180">0-5개의 스냅샷을 유지하도록 이 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-180">You can configure this policy to keep from 0-5 snapshots.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="8ec3d-181">질문과 대답</span><span class="sxs-lookup"><span data-stu-id="8ec3d-181">Frequently asked questions</span></span>

### <a name="manual-msi-rollback"></a><span data-ttu-id="8ec3d-182">수동 MSI 롤백</span><span class="sxs-lookup"><span data-stu-id="8ec3d-182">Manual MSI rollback</span></span>

#### <a name="what-generic-msi-failures-that-can-happen"></a><span data-ttu-id="8ec3d-183">어떤 일반적인 MSI 오류가 발생할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="8ec3d-183">What generic MSI failures that can happen?</span></span>

1. <span data-ttu-id="8ec3d-184">업데이트 그룹 정책 설치를 사용하지 않도록 설정하면 롤백이 일어나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-184">If the Install update group policy is disabled, rollback won't occur.</span></span>

   - <span data-ttu-id="8ec3d-185">롤백을 사용하려면 설치가 **사용**으로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-185">To use rollback, make sure Install is set to **Enabled**.</span></span> <span data-ttu-id="8ec3d-186">이 정책을 사용하지 않도록 설정하면 Microsoft Edge 채널을 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-186">When this policy is disabled, it prevents Microsoft Edge channels from being installed.</span></span> <span data-ttu-id="8ec3d-187">자세한 내용은 [설치](./microsoft-edge-update-policies.md#install)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-187">For more information, see [Install](./microsoft-edge-update-policies.md#install).</span></span>

2. <span data-ttu-id="8ec3d-188">Enlightenment 업데이트가 없는 경우, *Microsoft Edge Side by Side 브라우저 환경 허용*을 사용하도록 설정하지 않으면 Microsoft Edge 설치가 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-188">If Enlightenment Updates aren't present, Microsoft Edge installations will be blocked unless *Allow Microsoft Edge Side by Side browser experience* is enabled.</span></span>

   - <span data-ttu-id="8ec3d-189">Windows 버전 1903 및 1909의 경우: 마지막 업데이트가 2019년 10월 이전인 경우 이 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-189">For Windows versions 1903 and 1909: If your last update was before October 2019, you may have this issue.</span></span>
   - <span data-ttu-id="8ec3d-190">Windows 버전 1709, 1803 및 1809의 경우: 마지막 업데이트가 2019년 11월 이전인 경우 이 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-190">For Windows versions 1709, 1803, and 1809: If your last update was before November 2019, you may have this issue.</span></span><br>
<span data-ttu-id="8ec3d-191">자세한 내용은 [Microsoft Edge의 다음 버전을 지원하려면 Windows 업데이트](./microsoft-edge-sysupdate-windows-updates.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-191">For more information, see [Windows updates to support the next version of Microsoft Edge](./microsoft-edge-sysupdate-windows-updates.md)</span></span>

#### <a name="the-following-error-message-was-shown-after-using-the-command-prompt-and-rollback-didnt-occur-whats-wrong"></a><span data-ttu-id="8ec3d-192">명령 프롬프트를 사용한 후 다음 오류 메시지가 표시되었고 롤백이 수행되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-192">The following error message was shown after using the Command Prompt and rollback didn't occur.</span></span> <span data-ttu-id="8ec3d-193">문제가 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="8ec3d-193">What's wrong?</span></span>

![롤백 상태 메시지](./media/edge-learnmore-rollback/edge-rollback-cmd-flag-error.png)

<span data-ttu-id="8ec3d-195">*ALLOWDOWNGRADE=1*이 실행되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-195">*ALLOWDOWNGRADE=1* was not executed.</span></span>

### <a name="microsoft-edge-update-and-group-policy-rollback"></a><span data-ttu-id="8ec3d-196">Microsoft Edge 업데이트 및 그룹 정책 롤백</span><span class="sxs-lookup"><span data-stu-id="8ec3d-196">Microsoft Edge Update and Group Policy rollback</span></span>

#### <a name="i-set-rollback-to-target-version-enabled-update-policy-override-input-my-desired-browser-version-for-target-version-override-but-the-browser-version-wasnt-what-i-expected-whats-wrong"></a><span data-ttu-id="8ec3d-197">*대상 버전으로 롤백*을 설정하고 *업데이트 정책 재정의*를 사용하도록 설정하고 *대상 버전 재정의*에 대해 원하는 브라우저 버전을 입력했지만, 브라우저 버전이 예상했던 버전이 아니었습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-197">I set *Rollback to target version*, enabled *Update policy override*, input my desired browser version for *Target version override*, but the browser version wasn't what I expected.</span></span> <span data-ttu-id="8ec3d-198">문제가 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="8ec3d-198">What's wrong?</span></span>

<span data-ttu-id="8ec3d-199">다음은 롤백을 방해하는 몇 가지 일반적인 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-199">Some common errors that prevent rollback are:</span></span>

- <span data-ttu-id="8ec3d-200">대상 버전으로 롤백이 설정되지 않은 경우 롤백이 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-200">If Rollback to target version isn't set, rollback will not be executed.</span></span>
- <span data-ttu-id="8ec3d-201">대상 버전 재정의 설정에 다음 문제 중 하나가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-201">There are one of the following issues with the target version override setting:</span></span>

  - <span data-ttu-id="8ec3d-202">대상 버전 재정의가 지원되지 않는 대상 버전으로 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-202">Target version override is set to an unsupported target version.</span></span>
  - <span data-ttu-id="8ec3d-203">대상 버전 재정의가 존재하지 않는 대상 버전으로 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-203">Target version override is set to a non-existent target version.</span></span>
  - <span data-ttu-id="8ec3d-204">대상 버전 재정의 입력의 서식이 잘못 지정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-204">Target version override input is incorrectly formatted.</span></span>

- <span data-ttu-id="8ec3d-205">업데이트 정책 재정의가 "업데이트 사용 안 함"으로 설정된 경우, Microsoft Edge 업데이트에서 업데이트를 허용하지 않고 롤백이 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-205">If Update policy override is set to "Updates disabled", Microsoft Edge Update won't accept any updates and rollback isn't executed.</span></span>

### <a name="i-set-all-the-group-policies-correctly-but-rollback-didnt-execute-what-happened"></a><span data-ttu-id="8ec3d-206">모든 그룹 정책을 올바르게 설정했지만 롤백이 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-206">I set all the group policies correctly, but rollback didn't execute.</span></span> <span data-ttu-id="8ec3d-207">경우</span><span class="sxs-lookup"><span data-stu-id="8ec3d-207">What happened?</span></span>

<span data-ttu-id="8ec3d-208">Microsoft Edge 업데이트에서 아직 업데이트를 확인하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-208">Microsoft Edge Update hasn't run a check for updates yet.</span></span> <span data-ttu-id="8ec3d-209">기본적으로 자동 업데이트는 10시간마다 업데이트를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-209">By default, auto-update checks for updates every 10 hours.</span></span> <span data-ttu-id="8ec3d-210">자동 업데이트 확인 기간 재정의 그룹 정책으로 Microsoft Edge 업데이트의 폴링 간격을 변경하여 이 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-210">You can fix this issue by changing Microsoft Edge Update's polling interval with the Auto-update check period override group policy.</span></span> <span data-ttu-id="8ec3d-211">자세한 내용은 [AutoUpdateCheckPeriodMinutes](./microsoft-edge-update-policies.md#autoupdatecheckperiodminutes) 정책을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-211">For more information, see the [AutoUpdateCheckPeriodMinutes](./microsoft-edge-update-policies.md#autoupdatecheckperiodminutes) policy.</span></span>

### <a name="as-an-it-admin-i-followed-all-the-steps-for-rollback-correctly-only-a-portion-of-my-user-group-was-rolled-back-why-havent-the-other-users-been-rolled-back-yet"></a><span data-ttu-id="8ec3d-212">IT 관리자로서 롤백에 필요한 모든 단계를 올바르게 수행했습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-212">As an IT admin, I followed all the steps for rollback correctly.</span></span> <span data-ttu-id="8ec3d-213">사용자 그룹의 일부만 롤백되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-213">Only a portion of my user group was rolled back.</span></span> <span data-ttu-id="8ec3d-214">다른 사용자가 아직 롤백되지 않은 이유는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="8ec3d-214">Why haven't the other users been rolled back yet?</span></span>

<span data-ttu-id="8ec3d-215">그룹 정책 설정이 아직 모든 클라이언트에 동기화되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-215">The group policy setting hasn't synced to all the clients yet.</span></span> <span data-ttu-id="8ec3d-216">관리자가 그룹 정책을 설정할 때 클라이언트에서 이 설정을 즉시 받지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-216">When admins set a group policy, clients don't receive these settings instantaneously.</span></span> <span data-ttu-id="8ec3d-217">[원격 그룹 정책 강제 새로 고침](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/jj134201(v=ws.11))을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3d-217">You can [Force a Remote Group Policy Refresh](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/jj134201(v=ws.11)).</span></span>

## <a name="see-also"></a><span data-ttu-id="8ec3d-218">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8ec3d-218">See also</span></span>

- [<span data-ttu-id="8ec3d-219">Microsoft Edge Enterprise 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="8ec3d-219">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="8ec3d-220">비디오: Microsoft Edge 버전 롤백</span><span class="sxs-lookup"><span data-stu-id="8ec3d-220">Video: Microsoft Edge version rollback</span></span>](microsoft-edge-video-version-rollback.md)