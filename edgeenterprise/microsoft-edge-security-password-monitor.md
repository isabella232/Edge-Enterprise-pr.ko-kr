---
title: 사용자에 대해 암호 모니터 자동 사용
ms.author: supalsul
author: dan-wesley
manager: tulasim
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 사용자에 대해 암호 모니터 자동 사용
ms.openlocfilehash: 76fc4f0c0ce4bb59ba6b2d4d8a82b61592585918
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2021
ms.locfileid: "11643094"
---
# <a name="password-monitor-auto-enabled-for-users"></a><span data-ttu-id="408ca-103">사용자에 대해 암호 모니터 자동 사용</span><span class="sxs-lookup"><span data-stu-id="408ca-103">Password Monitor auto-enabled for users</span></span>

<span data-ttu-id="408ca-104">이 문서에서는 Microsoft Edge에서 선택한 사용자에 대해 암호 모니터를 설정하는 방법을 설명하고 관리자에게 모니터링 사용 방법을 제어하는 단계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="408ca-104">This article describes how Password Monitor in Microsoft Edge will be turned on for select users and gives admins the steps to control how monitoring is enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="408ca-105">이 문서는 Microsoft Edge 버전 88 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="408ca-105">This article applies to Microsoft Edge version 88 or later.</span></span>

## <a name="introduction-benefits-and-availability"></a><span data-ttu-id="408ca-106">소개, 이점 및 가용성</span><span class="sxs-lookup"><span data-stu-id="408ca-106">Introduction, benefits, and availability</span></span>

<span data-ttu-id="408ca-107">암호 모니터를 사용하면 Microsoft Edge 사용자가 온라인 누출에서 암호를 찾은 경우 이를 알려 온라인 계정을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="408ca-107">Password Monitor helps Microsoft Edge users protect their online accounts by informing them if any of their passwords have been found in an online leak.</span></span> <span data-ttu-id="408ca-108">악의적인 공격자들이 타사 앱 또는 웹 사이트에서 데이터를 도용하면 온라인 누출 또는 데이터 침해가 발생하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="408ca-108">Online leaks or data breaches happen when bad actors steal data from third-party apps or websites.</span></span> <span data-ttu-id="408ca-109">자세한 내용은 Microsoft Research 블로그에서 [암호 모니터: Microsoft Edge의 암호 보호](https://www.microsoft.com/research/blog/password-monitor-safeguarding-passwords-in-microsoft-edge/) 문서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="408ca-109">To learn more, see the [Password Monitor: Safeguarding passwords in Microsoft Edge](https://www.microsoft.com/research/blog/password-monitor-safeguarding-passwords-in-microsoft-edge/)  paper on the Microsoft Research Blog.</span></span>

### <a name="benefits"></a><span data-ttu-id="408ca-110">장점</span><span class="sxs-lookup"><span data-stu-id="408ca-110">Benefits</span></span>

<span data-ttu-id="408ca-111">이러한 온라인 공격의 빈도와 범위가 이러한 종류의 보호를 갖는 것이 모든 사람에 대해 필요해지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="408ca-111">Given the frequency and scope of these online attacks having this kind of protection has become necessary for everyone.</span></span> <span data-ttu-id="408ca-112">Microsoft Edge에는 손상된 것으로 알려진 암호에 대해 사용자의 저장된 암호를 안전하게 확인하고 일치가 발견되면 경고하는 기본 제공 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="408ca-112">Microsoft Edge has the built-in ability to securely check a user's saved passwords against passwords that are known to be compromised and alerts them if a match is found.</span></span>  

### <a name="availability"></a><span data-ttu-id="408ca-113">사용 가능한 시기</span><span class="sxs-lookup"><span data-stu-id="408ca-113">Availability</span></span>

<span data-ttu-id="408ca-114">암호 모니터는 1/21부터 안정 채널 버전 88에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="408ca-114">Password Monitor is available in Stable Channel version 88 starting 1/21.</span></span> <span data-ttu-id="408ca-115">출시는 서서히 적용될 예정이니 몇 주가 걸릴 수 있습니다. 설정 \*\*\*\* 프로필 암호 페이지에 다음 메시지와 컨트롤이  >  \*\*\*\*  >  \*\*\*\* 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="408ca-115">The rollout will be gradual and it could take a few weeks before you will see the following message and control in your **Settings** > **Profile** > **Password** page.</span></span>

:::image type="content" source="media/microsoft-edge-security-password-monitor/monitor-enable-option.png" alt-text="암호 모니터를 사용하도록 설정하는 옵션":::

## <a name="configure-group-policy-for-password-monitor"></a><span data-ttu-id="408ca-117">암호 모니터에 대한 그룹 정책 구성</span><span class="sxs-lookup"><span data-stu-id="408ca-117">Configure group policy for Password Monitor</span></span>

<span data-ttu-id="408ca-118">이 기능은 [PasswordMonitorAllowed](./microsoft-edge-policies.md#passwordmonitorallowed) 그룹 정책을 통해 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="408ca-118">This feature is controlled via the [PasswordMonitorAllowed](./microsoft-edge-policies.md#passwordmonitorallowed) group policy.</span></span>

<span data-ttu-id="408ca-119">정책을 사용하도록 설정한 후에도 사용자는 기능을 켜는 데 동의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="408ca-119">After the policy is enabled, users still need to provide consent to turn on the feature.</span></span> <span data-ttu-id="408ca-120">기능에 사용자의 중요한 개인 데이터(암호)가 포함되어 있기 때문에 동의가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="408ca-120">Consent is required because the feature contains user's sensitive and personal data (passwords).</span></span> <span data-ttu-id="408ca-121">그룹 정책을 사용하여 기능을 사용하지 않도록 설정한 경우 사용자는 이 설정을 오버라이드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="408ca-121">If the feature is disabled using group policy, users can't override this setting.</span></span>  

## <a name="enabling-password-monitor-for-users"></a><span data-ttu-id="408ca-122">사용자에 대해 암호 모니터 사용</span><span class="sxs-lookup"><span data-stu-id="408ca-122">Enabling Password Monitor for users</span></span>

<span data-ttu-id="408ca-123">암호 모니터 정책을 사용하도록 설정한 후 다양한 방법으로 사용자가 이 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="408ca-123">After the password monitor policy is enabled, there are different ways this feature is made available to users.</span></span>

- <span data-ttu-id="408ca-124">자동 사용.</span><span class="sxs-lookup"><span data-stu-id="408ca-124">Auto-enablement.</span></span> <span data-ttu-id="408ca-125">자신의 작업 계정(Active Directory 또는 Azure Active Directory)을 사용하여 로그인하고 암호를 동기화하는 사용자는 이 기능에 대해 자동으로 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="408ca-125">Users that are signed-in using their work account (Active Directory or Azure Active Directory) and syncing their passwords will be auto-enabled for this feature.</span></span> <span data-ttu-id="408ca-126">다음 스크린샷에 기능이 켜져 있는 경우 알림이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="408ca-126">They will  see the notification in the next screenshot informing them that the feature's turned on.</span></span>

  :::image type="content" source="media/microsoft-edge-security-password-monitor/monitor-enabled-notice.png" alt-text="암호 모니터가 알림을 사용함":::

-  <span data-ttu-id="408ca-128">명시적 동의를 얻어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="408ca-128">Getting explicit consent.</span></span> <span data-ttu-id="408ca-129">암호 동기화가 설정되지 않은 사용자에게 암호 모니터를 켜는 권한을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="408ca-129">Users that don’t have Password Sync turned on will be asked for permission to turn on Password Monitor.</span></span> <span data-ttu-id="408ca-130">다음 작업이 수행될 때 메시지가 표시될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="408ca-130">They will be prompted when the following actions happen:</span></span>
   - <span data-ttu-id="408ca-131">사용자가 새 암호를 저장하는 경우</span><span class="sxs-lookup"><span data-stu-id="408ca-131">When a user is saving a new password.</span></span>
 
     :::image type="content" source="media/microsoft-edge-security-password-monitor/monitor-save-pw-prompt.png" alt-text="암호를 저장하라는 메시지 표시":::

   - <span data-ttu-id="408ca-133">사용자가 저장된 암호를 사용하여 브라우저에 로그인한 경우</span><span class="sxs-lookup"><span data-stu-id="408ca-133">When a user has signed-in to the browser using a saved password.</span></span>
  
     :::image type="content" source="media/microsoft-edge-security-password-monitor/monitor-after-signin.png" alt-text="로그인 후 확인 메시지":::
   
- <span data-ttu-id="408ca-135">직접 활성화.</span><span class="sxs-lookup"><span data-stu-id="408ca-135">Direct activation.</span></span> <span data-ttu-id="408ca-136">사용자는 언제든지 \*\*설정 \*\* > **암호로** 이동하여 기능을 켜거나 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="408ca-136">Users can go to **Settings** > **Passwords** anytime and turn the feature On or Off.</span></span>

## <a name="user-scenarios-with-password-monitor-auto-enabled"></a><span data-ttu-id="408ca-137">암호 모니터 자동 사용이 가능한 사용자 시나리오</span><span class="sxs-lookup"><span data-stu-id="408ca-137">User scenarios with Password Monitor auto-enabled</span></span>

<span data-ttu-id="408ca-138">다음 표에서는 암호 모니터가 자동으로 사용하도록 설정되는 시나리오와 사용자 장치에서 암호 모니터가 어떻게 작동할지 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="408ca-138">The following table shows scenarios where Password Monitor is auto-enabled and how it will work on user devices.</span></span>

| <span data-ttu-id="408ca-139">시나리오</span><span class="sxs-lookup"><span data-stu-id="408ca-139">Scenario</span></span> | <span data-ttu-id="408ca-140">기본 조건</span><span class="sxs-lookup"><span data-stu-id="408ca-140">Base conditions</span></span> | <span data-ttu-id="408ca-141">영향</span><span class="sxs-lookup"><span data-stu-id="408ca-141">Impact</span></span> |
|--|--|--|
| <span data-ttu-id="408ca-142">동기화가 설정된 1</span><span class="sxs-lookup"><span data-stu-id="408ca-142">1 with Sync on</span></span> | <span data-ttu-id="408ca-143">동기화 설정</span><span class="sxs-lookup"><span data-stu-id="408ca-143">Sync ON</span></span><br><span data-ttu-id="408ca-144">이전에 사용할 수 있는 기능: 아니요</span><span class="sxs-lookup"><span data-stu-id="408ca-144">Feature enabled previously: No</span></span><br><span data-ttu-id="408ca-145">동의 UI에 대한 응답: 없음</span><span class="sxs-lookup"><span data-stu-id="408ca-145">Response to Consent UI: None</span></span> | <span data-ttu-id="408ca-146">기본적으로 사용하도록 설정된 기능은 브라우저가 시작된 후 2분 후에 풍선형으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="408ca-146">Feature enabled by default and a notice bubble is shown 2 min after browser starts.</span></span><br><span data-ttu-id="408ca-147">- 그 이후에 동기화가 꺼져 있는 경우 기능이 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="408ca-147">- If sync is turned off after that, the feature is disabled.</span></span><br><span data-ttu-id="408ca-148">- 동기화를 변경하기 전에 기능이 꺼져 있는 경우 동기화는 기능에 더 이상 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="408ca-148">-  Feature turned off before altering sync, sync will no longer affect the feature.</span></span>   |
| <span data-ttu-id="408ca-149">동기화가 설정된 2</span><span class="sxs-lookup"><span data-stu-id="408ca-149">2 with Sync on</span></span> | <span data-ttu-id="408ca-150">동기화 설정</span><span class="sxs-lookup"><span data-stu-id="408ca-150">Sync ON</span></span><br><span data-ttu-id="408ca-151">이전에 사용할 수 있는 기능: 예</span><span class="sxs-lookup"><span data-stu-id="408ca-151">Feature enabled previously: Yes</span></span><br><span data-ttu-id="408ca-152">동의 UI에 대한 응답: 없음</span><span class="sxs-lookup"><span data-stu-id="408ca-152">Response to Consent UI: None</span></span> | <span data-ttu-id="408ca-153">기능은 사용자 선택과 동일하게 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="408ca-153">Feature stays the same as user choice.</span></span>  <span data-ttu-id="408ca-154">거품이 표시되지 않는지와 기능 값에 대한 동기화 변경에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="408ca-154">Notice bubble isn't shown and there's no affect of sync change on feature value.</span></span>|
| <span data-ttu-id="408ca-155">3 동기화 해제</span><span class="sxs-lookup"><span data-stu-id="408ca-155">3 with Sync off</span></span> | <span data-ttu-id="408ca-156">동기화 해제</span><span class="sxs-lookup"><span data-stu-id="408ca-156">Sync Off</span></span><br><span data-ttu-id="408ca-157">이전에 사용할 수 있는 기능: 아니요</span><span class="sxs-lookup"><span data-stu-id="408ca-157">Feature enabled previously: No</span></span><br><span data-ttu-id="408ca-158">동의 UI에 대한 응답: 없음</span><span class="sxs-lookup"><span data-stu-id="408ca-158">Response to Consent UI: None</span></span> | <span data-ttu-id="408ca-159">동기화가 해제되어 기능이 계속 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="408ca-159">Sync will be off and the feature will stay disabled</span></span><br><span data-ttu-id="408ca-160">- 이후 사용자가 기능을 변경하지 않고 동기화를 켜면 해당 기능이 사용하도록 설정되어 있으며 동기화가 켜진 후 2분 후에 자동 활성화 알림이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="408ca-160">- At any point after that if user turns the sync on without altering the feature: the feature is enabled and auto-enablement notification is shown 2 minutes after Sync is turned on.</span></span> <br> <span data-ttu-id="408ca-161">- 동기화가 다시 꺼져 있는 경우 기능이 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="408ca-161">- If sync is turned off again, the  feature is disabled</span></span> <br><span data-ttu-id="408ca-162">- 동기화를 켜기 전에 기능이 변경된 경우 동기화는 암호 모니터에 더 이상 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="408ca-162">- If the feature is changed before turning on sync, sync will no longer affect Password Monitor.</span></span>  |  
| <span data-ttu-id="408ca-163">동기화 해제된 4개</span><span class="sxs-lookup"><span data-stu-id="408ca-163">4 with Sync off</span></span> | <span data-ttu-id="408ca-164">동기화 해제</span><span class="sxs-lookup"><span data-stu-id="408ca-164">Sync OFF</span></span><br><span data-ttu-id="408ca-165">이전에 사용할 수 있는 기능: 예</span><span class="sxs-lookup"><span data-stu-id="408ca-165">Feature enabled previously: Yes</span></span><br><span data-ttu-id="408ca-166">동의 UI에 대한 응답: 없음</span><span class="sxs-lookup"><span data-stu-id="408ca-166">Response to Consent UI: None</span></span> | <span data-ttu-id="408ca-167">기능은 사용자 선택과 동일하게 유지될 수 있으며 거품이 표시되지 않습니다. 또한 기능 값에 동기화 변경이 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="408ca-167">Feature stays the same as user choice, notice bubble isn't shown, and there's no effect of sync change on the feature value.</span></span>  |

<span data-ttu-id="408ca-168">또한 다음에 대한 정책을 통해 제한된 작업 계정을 사용하여 사용자가 로그인한 경우 이 기능은 자동으로 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="408ca-168">In addition, if a user is signed-in using a work account that is restricted via policies for any of the following, the feature will NOT be auto-enabled for them:</span></span>

- <span data-ttu-id="408ca-169">암호 모니터를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="408ca-169">Password Monitor is disabled</span></span>  
- <span data-ttu-id="408ca-170">암호 동기화를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="408ca-170">Password Sync is disabled</span></span>
- <span data-ttu-id="408ca-171">Microsoft 서버와 데이터 공유를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="408ca-171">Sharing of data with Microsoft servers is disabled</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="408ca-172">질문과 대답</span><span class="sxs-lookup"><span data-stu-id="408ca-172">Frequently Asked Questions</span></span>

### <a name="how-can-password-monitor-be-disabled-for-my-organization"></a><span data-ttu-id="408ca-173">조직에서 암호 모니터를 사용하지 않도록 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="408ca-173">How can Password Monitor be disabled for my organization?</span></span>

<span data-ttu-id="408ca-174">다음을 통해 조직의 암호 모니터를 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="408ca-174">You can disable Password Monitor for your organization by:</span></span>
- <span data-ttu-id="408ca-175">PasswordMonitorAllowed 그룹 정책 사용</span><span class="sxs-lookup"><span data-stu-id="408ca-175">Using the PasswordMonitorAllowed group policy.</span></span>
- <span data-ttu-id="408ca-176">데이터가 동기화되고 Microsoft 서버로 전송되지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="408ca-176">Stopping data from being synchronized and sent to Microsoft servers.</span></span>

  > [!NOTE]
  > <span data-ttu-id="408ca-177">암호 모니터는 사용자가 설정을 통해 기능을 켜는 데 명시적으로 동의한 경우 암호 동기화를 사용하지 않도록 설정한 경우에도 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="408ca-177">Password Monitor can work even if Password Sync is disabled, as long as the user has given explicit consent to turn the feature On or have turned it on themselves via Settings.</span></span>

### <a name="what-happens-if-a-user-for-whom-the-feature-has-been-auto-enabled-turns-password-monitor-off-via-settings"></a><span data-ttu-id="408ca-178">기능을 자동으로 사용하도록 설정한 사용자가 설정을 통해 암호 모니터를 끄면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="408ca-178">What happens if a user for whom the feature has been auto-enabled, turns Password Monitor off via Settings?</span></span>

<span data-ttu-id="408ca-179">사용자 설정이 그대로 유지되어 해당 사용자에 대해 기능이 비활성화된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="408ca-179">The user setting is honored and the feature will remain disabled for that user.</span></span> <span data-ttu-id="408ca-180">그러나 이전에 동의 프롬프트에 응답한 적이 없는 경우 동의 대화 상자가 다시 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="408ca-180">However, they might be shown a consent dialog again in case they've never previously responded to the consent prompt.</span></span>

## <a name="see-also"></a><span data-ttu-id="408ca-181">참고 항목</span><span class="sxs-lookup"><span data-stu-id="408ca-181">See also</span></span>

- [<span data-ttu-id="408ca-182">Microsoft Edge Enterprise 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="408ca-182">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)