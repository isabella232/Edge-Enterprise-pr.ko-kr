---
title: Microsoft Edge 동기화 문제 진단 및 해결
ms.author: collw
author: dan-wesley
manager: silvanam
ms.date: 03/08/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 관리자가 일반적인 엔터프라이즈 동기화 문제를 해결하고 해결하는 데 사용할 수 있는 지침 및 도구
ms.openlocfilehash: d934e1ad73500fcb7f15bcd7dd29cb0f905577c5
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2021
ms.locfileid: "11617908"
---
# <a name="diagnose-and-fix-microsoft-edge-sync-issues"></a><span data-ttu-id="7c77e-103">Microsoft Edge 동기화 문제 진단 및 해결</span><span class="sxs-lookup"><span data-stu-id="7c77e-103">Diagnose and fix Microsoft Edge sync issues</span></span>

<span data-ttu-id="7c77e-104">이 문서에서는 Azure AD(Azure Active Directory) 환경에서 가장 일반적으로 발생하는 동기화 문제에 대한 문제 해결 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-104">This article provides troubleshooting guidance for the most commonly encountered sync issues in an Azure Active Directory (Azure AD) environment.</span></span> <span data-ttu-id="7c77e-105">동기화 문제 해결에 필요한 로그를 수집하는 권장 도구도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-105">It also includes the recommended tools for gathering the logs needed for troubleshooting a sync issue.</span></span>

<span data-ttu-id="7c77e-106">사용자가 장치에서 브라우저 데이터를 동기화하는 데 문제가 있는 경우 [동기화 재설정](edge-learnmore-reset-data-in-cloud.md)을 시도할 수 있습니다. 그래도 문제가 해결되지 않는 경우 관리자 또는 지원 직원이 다음 지침을 사용하여 동기화 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-106">If a user is experiencing an issue syncing browser data across their devices they can try [resetting sync](edge-learnmore-reset-data-in-cloud.md). If this doesn't work, admins or support staff can use the following guidance to fix a sync issue.</span></span>

> [!NOTE]
> <span data-ttu-id="7c77e-107">달리 명시되지 않은 한 Microsoft Edge 버전 77 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-107">Applies to Microsoft Edge version 77 or later unless otherwise noted.</span></span>

## <a name="identity-issues-versus-sync-issues"></a><span data-ttu-id="7c77e-108">ID 문제와 동기화 문제</span><span class="sxs-lookup"><span data-stu-id="7c77e-108">Identity issues versus sync issues</span></span>

<span data-ttu-id="7c77e-109">시작하기 전에 ID 문제와 동기화 문제의 차이점을 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-109">Before you begin it's important to understand the difference between identity issues and sync issues.</span></span> <span data-ttu-id="7c77e-110">브라우저에서 사용자 ID를 유지하기 위한 인기 있는 사용 사례는 동기화를 지원하는 것입니다. 이러한 이유로 ID 문제는 동기화 문제와 자주 혼동됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-110">A popular use case for maintaining user identity in the browser is to support sync. For this reason, identity issues are frequently confused with sync issues.</span></span> <span data-ttu-id="7c77e-111">동기화 문제 해결을 시작하기 전에 ID와 동기화 문제의 차이점을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-111">Understand the difference between identity and sync issue before you start troubleshooting sync.</span></span>

<span data-ttu-id="7c77e-112">문제를 동기화 문제로 처리하기 전에 사용자가 유효한 계정으로 브라우저에 로그인했는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="7c77e-112">Before you treat an issue as a sync issue, check to see if the user is signed into the browser with a valid account.</span></span>

<span data-ttu-id="7c77e-113">다음 스크린샷에 ID 오류의 예가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-113">The next screenshot shows an example of an identity error.</span></span> <span data-ttu-id="7c77e-114">오류는 "**마지막 토큰 오류, EDGE_AUTH_ERROR: 3, 54, 3ea**"이며 *edge://sync-internals*(**자격 증명** 아래)에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-114">The error is "**Last Token Error, EDGE_AUTH_ERROR: 3, 54, 3ea**", which is found in *edge://sync-internals* under **Credentials**:</span></span>

:::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-identity-issue.png" alt-text="마지막 토큰 오류 EDGE_AUTH_ERROR: 3,54, 3ea":::

## <a name="common-sync-issues"></a><span data-ttu-id="7c77e-116">일반적인 동기화 문제</span><span class="sxs-lookup"><span data-stu-id="7c77e-116">Common sync issues</span></span>

### <a name="issue-cant-access-m365-or-azure-information-protection-subscription"></a><span data-ttu-id="7c77e-117">문제: M365 또는 Azure Information Protection 구독에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-117">Issue: Can't access M365 or Azure Information Protection subscription</span></span>

<span data-ttu-id="7c77e-118">만료된 후 새 구독으로 대체된 이전 M365 또는 AIP(Azure Information Protection) 구독이 있나요?</span><span class="sxs-lookup"><span data-stu-id="7c77e-118">Do you have a previous M365 or Azure Information Protection (AIP) subscription that expired and then replaced with a new subscription?</span></span> <span data-ttu-id="7c77e-119">있는 경우 테넌트 ID가 변경된 것이며 서비스 데이터를 다시 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-119">If so, then the tenant ID has changed and the service data needs to be reset.</span></span> <span data-ttu-id="7c77e-120">**암호화 오류가 발생했습니다** 문제에서 데이터를 다시 설정하는 방법에 대한 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c77e-120">See the instructions for resetting data in the **Cryptographer error encountered** issue.</span></span>

### <a name="issue-sync-is-not-available-for-this-account"></a><span data-ttu-id="7c77e-121">문제: "이 계정에 동기화를 사용할 수 없습니다."</span><span class="sxs-lookup"><span data-stu-id="7c77e-121">Issue: “Sync is not available for this account.”</span></span>

<span data-ttu-id="7c77e-122">Azure Active Directory 계정에 이 오류가 발생하거나 DISABLED_BY_ADMIN이 *edge://sync-internals*에 나타나면, 문제가 해결될 때까지 다음 절차의 단계를 순차적으로 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="7c77e-122">If this error is encountered for an Azure Active Directory account, or if DISABLED_BY_ADMIN appears in *edge://sync-internals*, follow the steps in the next procedure sequentially until the problem is fixed.</span></span>

> [!NOTE]
> <span data-ttu-id="7c77e-123">이 오류의 원인은 일반적으로 Azure Active Directory 테넌트에서 구성을 변경해야 하므로, 이러한 문제 해결 단계는 최종 사용자가 아니라 테넌트 관리자만 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-123">Because the source of this error is usually requires a configuration change in an Azure Active Directory tenant, these troubleshooting steps can only performed by a tenant admin and not by end users.</span></span>

1. <span data-ttu-id="7c77e-124">엔터프라이즈 테넌트에 지원되는 M365 구독이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-124">Verify that the enterprise tenant has a supported M365 subscription.</span></span> <span data-ttu-id="7c77e-125">사용 가능한 구독 유형의 현재 목록이 [여기에 제공됩니다](/azure/information-protection/activate-office365).</span><span class="sxs-lookup"><span data-stu-id="7c77e-125">The current list of available subscription types is [provided here](/azure/information-protection/activate-office365).</span></span> <span data-ttu-id="7c77e-126">테넌트에 지원되는 구독이 없는 경우 Azure Information Protection을 별도로 구매하거나 지원되는 구독 중 하나로 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-126">If the tenant doesn't have a supported subscription, they can either purchase Azure Information Protection separately, or upgrade to one of the supported subscriptions.</span></span>
2. <span data-ttu-id="7c77e-127">지원되는 구독을 사용할 수 있는 경우 테넌트에 사용 가능한 AIP(Azure Information Protection)가 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-127">If a supported subscription is available, verify that the tenant has Azure Information Protection (AIP) available.</span></span> <span data-ttu-id="7c77e-128">AIP 상태를 확인하고 필요한 경우 AIP를 활성화하는 지침은 [여기](/azure/information-protection/activate-office365)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-128">The instructions for checking the AIP status and, if necessary, activating AIP are [here](/azure/information-protection/activate-office365).</span></span>
3. <span data-ttu-id="7c77e-129">2단계에서 AIP가 활성 상태이지만 동기화가 여전히 작동하지 않는 것으로 표시되면 ESR(Enterprise State Roaming)을 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-129">If step 2 shows that AIP is active but sync still doesn't work, turn on Enterprise State Roaming (ESR).</span></span> <span data-ttu-id="7c77e-130">ESR을 사용하도록 설정하는 지침은 [여기](/azure/active-directory/devices/enterprise-state-roaming-enable)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-130">The instructions for enabling ESR are [here](/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span> <span data-ttu-id="7c77e-131">ESR이 계속 켜져 있을 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-131">Note that ESR does not need to stay on.</span></span> <span data-ttu-id="7c77e-132">이 단계로 문제가 해결될 경우 ESR을 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-132">You can turn off ESR if this step fixes the issue.</span></span>
4. <span data-ttu-id="7c77e-133">온보딩 정책을 통해 Azure Information Protection의 범위가 지정되지 않았는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-133">Confirm that Azure Information Protection is not scoped via an onboarding policy.</span></span> <span data-ttu-id="7c77e-134">[Get-AadrmOnboardingControlPolicy](/powershell/module/aadrm/get-aadrmonboardingcontrolpolicy?view=azureipps) PowerShell 애플릿을 사용하여 범위 지정이 활성화되어 있는지 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-134">You can use the [Get-AadrmOnboardingControlPolicy](/powershell/module/aadrm/get-aadrmonboardingcontrolpolicy?view=azureipps) PowerShell applet to see if scoping is enabled.</span></span> <span data-ttu-id="7c77e-135">다음 두 예제에서는 범위가 지정되지 않은 구성과 특정 보안 그룹으로 범위가 지정된 구성을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-135">The next two examples show an unscoped configuration and a configuration scoped to a specific security group.</span></span>

   ```powershell
    PS C:\Work\scripts\PowerShell> Get-AadrmOnboardingControlPolicy
 
    UseRmsUserLicense SecurityGroupObjectId                Scope
    ----------------- ---------------------                -----
                False 
   ```

   ```powershell

    PS C:\Work\scripts\PowerShell> Get-AadrmOnboardingControlPolicy
 
    UseRmsUserLicense SecurityGroupObjectId                Scope
    ----------------- ---------------------                -----
                False f1488a05-8196-40a6-9483-524948b90282   All
   ```

   <span data-ttu-id="7c77e-136">범위 지정을 사용하도록 설정한 경우 영향을 받는 사용자를 범위의 보안 그룹에 추가하거나 범위를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-136">If scoping is enabled, the affected user should either be added to the security group for the scope, or the scope should be removed.</span></span> <span data-ttu-id="7c77e-137">아래 예제에서 온보딩은 AIP 범위를 표시된 보안 그룹으로 지정했으며 범위 지정은 [Set-AadrmOnboardingControlPolicy](/powershell/module/aadrm/set-aadrmonboardingcontrolpolicy?view=azureipps) PowerShell 애플릿으로 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-137">In the example below, onboarding has scoped AIP to the indicated security group and the scoping should be removed with the [Set-AadrmOnboardingControlPolicy](/powershell/module/aadrm/set-aadrmonboardingcontrolpolicy?view=azureipps) PowerShell applet.</span></span>

5. <span data-ttu-id="7c77e-138">테넌트에서 IPCv3Service가 켜져 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-138">Confirm that the IPCv3Service is turned on in the tenant.</span></span> <span data-ttu-id="7c77e-139">[Get-AadrmConfiguration](/powershell/module/aadrm/get-aadrmconfiguration?view=azureipps) PowerShell 애플릿에는 서비스 상태가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-139">The [Get-AadrmConfiguration](/powershell/module/aadrm/get-aadrmconfiguration?view=azureipps)  PowerShell applet shows the status of the service.</span></span>

   :::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-scoped-cfg-example.png" alt-text="IPCv3Service를 사용하도록 설정되어 있는지 확인합니다.":::

6. <span data-ttu-id="7c77e-141">문제가 해결되지 않은 경우 [Microsoft Edge 지원](https://www.microsoftedgeinsider.com/support)에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="7c77e-141">If the issue isn't fixed, contact [Microsoft Edge support](https://www.microsoftedgeinsider.com/support).</span></span>

### <a name="issue-stuck-at-setting-up-sync-or-couldnt-connect-to-the-sync-server-retrying"></a><span data-ttu-id="7c77e-142">문제: "동기화 설정..." 또는 "동기화 서버에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-142">Issue: Stuck at "Setting up sync..." or “Couldn’t connect to the sync server.</span></span> <span data-ttu-id="7c77e-143">다시 시도..."에서 멈춰 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-143">Retrying…”</span></span>

1. <span data-ttu-id="7c77e-144">로그아웃을 시도한 다음 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-144">Try to sign out and then sign in.</span></span>
2. <span data-ttu-id="7c77e-145">*edge://sync-internals*로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-145">Go to *edge://sync-internals*.</span></span> <span data-ttu-id="7c77e-146">"**유형 정보**" 섹션에 다음 오류가 있는 경우 다음 문제 **암호화 오류가 발생했습니다**로 건너뛰세요.</span><span class="sxs-lookup"><span data-stu-id="7c77e-146">If under the "**Type info**" section the following error is present, then  skip to the following issue, **Cryptographer error encountered**.</span></span>

   `"Error:GenerateCryptoErrorsForTypes@../../components/sync/driver/data_type_manager_impl.cc:42, cryptographer error was encountered"`

3. <span data-ttu-id="7c77e-147">서버 엔드포인트 ping을 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-147">Try pinging the server endpoint.</span></span> <span data-ttu-id="7c77e-148">클라이언트용 서버 엔드포인트는 *edge://sync-internals*에서 이용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-148">The server endpoint for a client is available in *edge://sync-internals*.</span></span> <span data-ttu-id="7c77e-149">다음 스크린샷은 **환경 정보**의 엔드포인트 정보를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-149">The next screenshot shows endpoint information under **Environment Info**.</span></span>

   :::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-endpoint-info.png" alt-text="엔드포인트 정보":::

4. <span data-ttu-id="7c77e-151">서버 엔드포인트가 비어 있거나 서버를 ping할 수 없고 환경에 방화벽이 있는 경우 클라이언트 컴퓨터에서 필요한 서비스 엔드포인트를 사용할 수 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="7c77e-151">If the server endpoint is empty, or if server cannot be pinged and a firewall is present in the environment, confirm that the necessary service endpoints are available to the client computer.</span></span>

   - <span data-ttu-id="7c77e-152">Microsoft Edge 동기화 서비스 엔드포인트:</span><span class="sxs-lookup"><span data-stu-id="7c77e-152">Microsoft Edge sync service endpoints:</span></span>
     - [https://edge-enterprise.activity.windows.com](https://edge-enterprise.activity.windows.com)
     - [https://edge.activity.windows.com](https://edge.activity.windows.com)
    - <span data-ttu-id="7c77e-153">Azure Information Protection 엔드포인트:</span><span class="sxs-lookup"><span data-stu-id="7c77e-153">Azure Information Protection endpoints:</span></span>
      - <span data-ttu-id="7c77e-154">[https://api.aadrm.com](https://api.aadrm.com)(테넌트 대부분의 경우)</span><span class="sxs-lookup"><span data-stu-id="7c77e-154">[https://api.aadrm.com](https://api.aadrm.com) (for most tenants)</span></span>
      - <span data-ttu-id="7c77e-155">[https://api.aadrm.de](https://api.aadrm.de)(독일의 테넌트)</span><span class="sxs-lookup"><span data-stu-id="7c77e-155">[https://api.aadrm.de](https://api.aadrm.de) (for tenants in Germany)</span></span>
      - <span data-ttu-id="7c77e-156">[https://api.aadrm.cn](https://api.aadrm.cn)(중국의 테넌트)</span><span class="sxs-lookup"><span data-stu-id="7c77e-156">[https://api.aadrm.cn](https://api.aadrm.cn) (for tenants in China)</span></span>
   - <span data-ttu-id="7c77e-157">[Windows 알림 서비스 엔드포인트](/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config).</span><span class="sxs-lookup"><span data-stu-id="7c77e-157">[Windows Notification Service endpoints](/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config).</span></span>

5. <span data-ttu-id="7c77e-158">그래도 문제가 해결되지 않은 경우 [Microsoft Edge 지원](https://www.microsoftedgeinsider.com/support)에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="7c77e-158">If the issue still isn't fixed, contact [Microsoft Edge support](https://www.microsoftedgeinsider.com/support).</span></span>

### <a name="issue-cryptographer-error-encountered"></a><span data-ttu-id="7c77e-159">문제: 암호화 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-159">Issue: Cryptographer error encountered</span></span>

<span data-ttu-id="7c77e-160">이 오류는 **유형 정보** 아래 *edge://sync-internals*에서 볼 수 있으며 사용자의 서비스 측 데이터를 다시 설정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-160">This error is visible under **Type info** in *edge://sync-internals* and may mean that the user's service side data needs to be reset.</span></span> <span data-ttu-id="7c77e-161">다음 예에서는 암호화 오류 메시지를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-161">The following example shows a cryptography error message:</span></span>
<br><span data-ttu-id="7c77e-162">"Error:GenerateCryptoErrorsForTypes@../../components/sync/driver/data_type_manager_impl.cc:42, cryptographer error was encountered".</span><span class="sxs-lookup"><span data-stu-id="7c77e-162">"Error:GenerateCryptoErrorsForTypes@../../components/sync/driver/data_type_manager_impl.cc:42, cryptographer error was encountered".</span></span>

1. <span data-ttu-id="7c77e-163">Microsoft Edge를 다시 시작하고 *edge://sync-internals*로 이동하여 "**AAD 계정 키 상태**" 섹션을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-163">Restart Microsoft Edge and navigate to *edge://sync-internals* and check the “**AAD Account Key Status**” section</span></span>
   - <span data-ttu-id="7c77e-164">"마지막 MIP 결과"의 "성공": 암호화 오류는 서버 데이터가 분실된 키로 암호화될 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-164">"Success" in "Last MIP Result": the cryptographer error means server data might be encrypted with a lost key.</span></span> <span data-ttu-id="7c77e-165">동기화를 다시 시작하려면 데이터 재설정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-165">Data reset is needed to resume sync.</span></span>
   - <span data-ttu-id="7c77e-166">"마지막 MIP 결과"의 "사용 권한 없음": Azure AD 변경 또는 테넌트 구독 변경으로 인해 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-166">"No permissions" in "Last MIP Result": It is possibly caused by an Azure AD change or tenant subscription changes.</span></span> <span data-ttu-id="7c77e-167">동기화를 다시 시작하려면 데이터 재설정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-167">Data reset is needed to resume sync.</span></span>
   - <span data-ttu-id="7c77e-168">다른 오류는 서버 구성 문제를 의미할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c77e-168">Other errors may mean server configuration issues.</span></span>
2. <span data-ttu-id="7c77e-169">데이터 재설정이 필요한 경우 [클라우드에서 Microsoft Edge 데이터 다시 설정](edge-learnmore-reset-data-in-cloud.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c77e-169">If data reset is needed, see [Reset Microsoft Edge data in the cloud](edge-learnmore-reset-data-in-cloud.md).</span></span>

### <a name="issue-sync-has-been-turned-off-by-your-administrator"></a><span data-ttu-id="7c77e-170">문제: "관리자가 동기화를 해제했습니다."</span><span class="sxs-lookup"><span data-stu-id="7c77e-170">Issue: “Sync has been turned off by your administrator.”</span></span>

<span data-ttu-id="7c77e-171">[SyncDisabled](./microsoft-edge-policies.md#syncdisabled) 정책이 설정되지 않았는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="7c77e-171">Make sure that the [SyncDisabled policy](./microsoft-edge-policies.md#syncdisabled)  is not set.</span></span>

## <a name="see-also"></a><span data-ttu-id="7c77e-172">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7c77e-172">See also</span></span>

- [<span data-ttu-id="7c77e-173">Microsoft Edge Enterprise 동기화</span><span class="sxs-lookup"><span data-stu-id="7c77e-173">Microsoft Edge Enterprise Sync</span></span>](microsoft-edge-enterprise-sync.md)
- [<span data-ttu-id="7c77e-174">Microsoft Edge 및 Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="7c77e-174">Microsoft Edge and Enterprise State Roaming</span></span>](microsoft-edge-enterprise-state-roaming.md)
- [<span data-ttu-id="7c77e-175">Microsoft Edge Enterprise 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="7c77e-175">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)