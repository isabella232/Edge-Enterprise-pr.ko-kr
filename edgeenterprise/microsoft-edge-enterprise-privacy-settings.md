---
title: Microsoft Edge 엔터프라이즈 개인 정보 설정
ms.author: likravit
author: dan-wesley
manager: srugh
ms.date: 05/26/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 엔터프라이즈 개인 정보 설정 구성
ms.openlocfilehash: 2b7a33087ae5110c53d18b3192486d4ae62fa540
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980738"
---
# <span data-ttu-id="171e7-103">엔터프라이즈 개인 정보를 지원하도록 Microsoft Edge 정책 구성</span><span class="sxs-lookup"><span data-stu-id="171e7-103">Configure Microsoft Edge policies to support enterprise privacy</span></span>

<span data-ttu-id="171e7-104">Microsoft는 Microsoft Edge에서 데이터 수집을 선택하는 데 필요한 정보와 컨트롤을 엔터프라이즈에 제공하기 위해 최선을 다하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="171e7-104">Microsoft is committed to providing enterprises with the information and controls needed to make choices about data collection in Microsoft Edge.</span></span>

## <span data-ttu-id="171e7-105">개요</span><span class="sxs-lookup"><span data-stu-id="171e7-105">Overview</span></span>

<span data-ttu-id="171e7-106">기본적으로 Windows가 아닌 플랫폼에 배포된 Microsoft Edge는 진단 데이터 또는 사이트 정보가 Microsoft에 전송되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="171e7-106">By default, Microsoft Edge deployed on non-Windows platforms doesn't send diagnostic data or site information to Microsoft.</span></span> <span data-ttu-id="171e7-107">Windows 10에 Microsoft Edge가 배포되면 사용자의 [Windows 진단 데이터 설정](https://go.microsoft.com/fwlink/?linkid=2099569)을 기반으로 진단 데이터를 보내는 것이 기본입니다.</span><span class="sxs-lookup"><span data-stu-id="171e7-107">When Microsoft Edge is deployed on Windows 10, the default is to send diagnostic data based on the users' [Windows Diagnostic data setting](https://go.microsoft.com/fwlink/?linkid=2099569).</span></span>

<span data-ttu-id="171e7-108">다음 그룹 정책을 사용하여 Microsoft Edge가 조직에 대한 데이터 수집을 처리하는 방법을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="171e7-108">You can also configure how Microsoft Edge handles data collection for your organization with the following group policies:</span></span>

- <span data-ttu-id="171e7-109">[MetricsReportingEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#metricsreportingenabled) - 사용 및 충돌 관련 데이터보고를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="171e7-109">[MetricsReportingEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#metricsreportingenabled) - Enable usage and crash-related data reporting.</span></span>
- <span data-ttu-id="171e7-110">[SendSiteInfoToImproveServices](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sendsiteinfotoimproveservices) - Microsoft 서비스를 개선하기 위해 사이트 정보를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="171e7-110">[SendSiteInfoToImproveServices](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sendsiteinfotoimproveservices) - Send site information to improve Microsoft services.</span></span>

## <span data-ttu-id="171e7-111">정책 설정 구성</span><span class="sxs-lookup"><span data-stu-id="171e7-111">Configure policy settings</span></span>

<span data-ttu-id="171e7-112">시작하기 전에 최신 Microsoft Edge 정책 템플릿을 다운로드하고 사용합니다(자세한 내용은 [Microsoft Edge 구성](configure-microsoft-edge.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="171e7-112">Before you begin, download and use the latest Microsoft Edge Policy Template (For more information, see [Configure Microsoft Edge](configure-microsoft-edge.md).)</span></span>

### <span data-ttu-id="171e7-113">사용 현황 및 크래시 관련 데이터 보고를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="171e7-113">Enable usage and crash-related data reporting</span></span>

<span data-ttu-id="171e7-114">이 정책은 Microsoft Edge에서 Microsoft로의 사용 현황 및 크래시 관련 데이터 보고를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="171e7-114">This policy enables reporting of usage and crash-related data about Microsoft Edge to Microsoft.</span></span>

<span data-ttu-id="171e7-115">Microsoft Edge는 제품을 안전한 최신 상태로 유지하고 적절히 실행하는 데 필요한 필수 데이터 집합을 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="171e7-115">Microsoft Edge collects a set of required data that's necessary to keep the product up to date, secure, and performing properly.</span></span> <span data-ttu-id="171e7-116">이 데이터는 Microsoft Edge 설치에 대한 현재 데이터 수집 동의, 앱 버전 및 설치 상태에 대한 Microsoft Edge의 기본 장치 연결 및 구성 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="171e7-116">This data includes basic device connectivity and configuration information from Microsoft Edge about the current data collection consent, app version, and installation state about your installation of Microsoft Edge.</span></span><span data-ttu-id="171e7-117"> 이 데이터 수집은 정책을 사용하지 않음으로써 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="171e7-117"> This data collection can be turned off by disabling the policy.</span></span>

<span data-ttu-id="171e7-118">사용 현황 및 충돌 관련 데이터 보고를 Microsoft에 보내려면 이 정책을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="171e7-118">Enable this policy to send reporting of usage and crash-related data to Microsoft.</span></span> <span data-ttu-id="171e7-119">이 정책을 사용하지 않도록 설정하여 데이터를 Microsoft에 보내지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="171e7-119">Disable this policy to not send the data to Microsoft.</span></span> <span data-ttu-id="171e7-120">두 경우 모두 사용자가 정책 설정을 변경하거나 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="171e7-120">In both cases, users can't change or override the setting.</span></span>

<span data-ttu-id="171e7-121">Windows 10에서 Microsoft Edge가 실행되고 있는 경우:</span><span class="sxs-lookup"><span data-stu-id="171e7-121">When Microsoft Edge is running on Windows 10:</span></span>

- <span data-ttu-id="171e7-122">이 정책이 구성되지 않은 경우에는 기본적으로 Microsoft Edge에서 Windows 진단 데이터 설정이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="171e7-122">If this policy isn't configured, Microsoft Edge will default to the Windows diagnostic data setting.</span></span>
- <span data-ttu-id="171e7-123">이 정책을 사용하도록 설정하면 Microsoft Edge는 Windows 진단 데이터 설정이 **고급** 또는 **전체**로 설정된 경우에만 사용 현황 데이터를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="171e7-123">If this policy is enabled, Microsoft Edge will only send usage data if the Windows Diagnostic data setting is set to **Enhanced** or **Full**.</span></span>
- <span data-ttu-id="171e7-124">이 정책을 사용하지 않도록 설정하면 Microsoft Edge는 사용 현황 데이터를 보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="171e7-124">If this policy is disabled, Microsoft Edge will not send usage data.</span></span> <span data-ttu-id="171e7-125">크래시 관련 데이터는 Windows 진단 데이터 설정에 따라 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="171e7-125">Crash-related data is sent based on the Windows Diagnostic data setting.</span></span> <span data-ttu-id="171e7-126">[Windows 진단 데이터 설정](https://go.microsoft.com/fwlink/?linkid=2099569)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="171e7-126">[Learn more about Windows Diagnostic data settings](https://go.microsoft.com/fwlink/?linkid=2099569).</span></span>

<span data-ttu-id="171e7-127">Microsoft Edge가 Windows 7, 8 및 macOS에서 실행되는 경우:</span><span class="sxs-lookup"><span data-stu-id="171e7-127">When Microsoft Edge is running on Windows 7, 8, and macOS:</span></span>

- <span data-ttu-id="171e7-128">이 정책이 구성되지 않은 경우에는 기본적으로 Microsoft Edge에서 사용자의 기본 설정이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="171e7-128">If this policy isn't configured, Microsoft Edge will default to the user's preference.</span></span>

### <span data-ttu-id="171e7-129">Microsoft 서비스를 개선하기 위해 사이트 정보를 보냄</span><span class="sxs-lookup"><span data-stu-id="171e7-129">Send site information to improve Microsoft services</span></span>

<span data-ttu-id="171e7-130">이 정책은 Microsoft Edge에서 방문하는 웹 사이트에 대한 정보를 Microsoft에 전송하여 Microsoft 제품과 서비스를 개선하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="171e7-130">This policy enables sending information about websites visited in Microsoft Edge to Microsoft to improve Microsoft products and services such as search.</span></span>

<span data-ttu-id="171e7-131">Microsoft Edge에서 방문하는 웹 사이트에 대한 정보를 Microsoft로 보내려면 이 정책을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="171e7-131">Enable this policy to send information about websites visited in Microsoft Edge to Microsoft.</span></span> <span data-ttu-id="171e7-132">Microsoft Edge에서 방문하는 웹 사이트에 대한 정보를 Microsoft로 보내지 않으려면 이 정책을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="171e7-132">Disable this policy to not send information about the websites that are visited in Microsoft Edge to Microsoft.</span></span> <span data-ttu-id="171e7-133">두 경우 모두 사용자가 정책 설정을 변경하거나 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="171e7-133">In both cases, users can't change or override the setting.</span></span>

<span data-ttu-id="171e7-134">Windows 10에서 Microsoft Edge가 실행되고 있는 경우:</span><span class="sxs-lookup"><span data-stu-id="171e7-134">When Microsoft Edge is running on Windows 10:</span></span>

- <span data-ttu-id="171e7-135">이 정책이 구성되지 않은 경우에는 기본적으로 Microsoft Edge에서 Windows 진단 데이터 설정이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="171e7-135">If this policy isn't configured, Microsoft Edge will default to the Windows diagnostic data setting.</span></span>
- <span data-ttu-id="171e7-136">이 정책을 사용하도록 설정하면 Microsoft Edge는 Windows 진단 데이터 설정이 **전체**로 설정된 경우에만 방문하는 웹 사이트에 대한 정보를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="171e7-136">If this policy is enabled, Microsoft Edge will only send information about the websites that are visited if the Windows Diagnostic data setting is set to **Full**.</span></span>
- <span data-ttu-id="171e7-137">이 정책을 사용하지 않도록 설정하면 Microsoft Edge는 방문하는 웹 사이트에 대한 정보를 보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="171e7-137">If this policy is disabled, Microsoft Edge will not send info about websites visited.</span></span> <span data-ttu-id="171e7-138">[Windows 진단 데이터 설정에 대해 자세히 알아보십시오](https://go.microsoft.com/fwlink/?linkid=2099569).</span><span class="sxs-lookup"><span data-stu-id="171e7-138">To [learn more about Windows Diagnostic data settings](https://go.microsoft.com/fwlink/?linkid=2099569).</span></span>

<span data-ttu-id="171e7-139">Microsoft Edge가 Windows 7, 8 및 macOS에서 실행되는 경우:</span><span class="sxs-lookup"><span data-stu-id="171e7-139">When Microsoft Edge is running on Windows 7, 8, and macOS:</span></span>

- <span data-ttu-id="171e7-140">이 정책이 구성되지 않은 경우에는 기본적으로 Microsoft Edge에서 사용자의 기본 설정이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="171e7-140">If this policy isn't configured, Microsoft Edge will default to the user's preference.</span></span>

## <span data-ttu-id="171e7-141">구현 세부 정보</span><span class="sxs-lookup"><span data-stu-id="171e7-141">Implementation details</span></span>

<span data-ttu-id="171e7-142">Windows 10에서 Windows 진단 데이터 설정에 대한 종속성을 사용하여 구현을 이해하기 위해 다음 표에서는 **사용 현황 및 충돌 관련 데이터 보고를 사용하도록 설정** 및 **Microsoft 서비스를 개선하기 위해 사이트 정보를 보냄**이 구성되지 않은 경우의 구성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="171e7-142">For Windows 10 to understand our implementation with the dependency on the Windows Diagnostic data setting, the following table describes our configuration if **Enable usage and crash-related data reporting** and **Send site information to improve Microsoft services** were not configured.</span></span>

| <span data-ttu-id="171e7-143">Windows 진단 데이터 설정</span><span class="sxs-lookup"><span data-stu-id="171e7-143">Windows Diagnostic data setting</span></span> | <span data-ttu-id="171e7-144">사용 현황 및 크래시 관련 데이터 보고를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="171e7-144">Enable usage and crash-related data reporting</span></span> | <span data-ttu-id="171e7-145">Microsoft 서비스를 개선하기 위해 사이트 정보를 보냄</span><span class="sxs-lookup"><span data-stu-id="171e7-145">Send site information to improve Microsoft services</span></span> |
|---------------------------------|-----------------------------------------------|-----------------------------------------------------|
| <span data-ttu-id="171e7-146">보안</span><span class="sxs-lookup"><span data-stu-id="171e7-146">Security</span></span>                        | <span data-ttu-id="171e7-147">전송되지 않음</span><span class="sxs-lookup"><span data-stu-id="171e7-147">Not sent</span></span>                                      | <span data-ttu-id="171e7-148">전송되지 않음</span><span class="sxs-lookup"><span data-stu-id="171e7-148">Not sent</span></span>                                            |
| <span data-ttu-id="171e7-149">기본</span><span class="sxs-lookup"><span data-stu-id="171e7-149">Basic</span></span>                           | <span data-ttu-id="171e7-150">전송되지 않음</span><span class="sxs-lookup"><span data-stu-id="171e7-150">Not sent</span></span>                                      | <span data-ttu-id="171e7-151">전송되지 않음</span><span class="sxs-lookup"><span data-stu-id="171e7-151">Not sent</span></span>                                            |
| <span data-ttu-id="171e7-152">고급</span><span class="sxs-lookup"><span data-stu-id="171e7-152">Enhanced</span></span>                        | <span data-ttu-id="171e7-153">보냄</span><span class="sxs-lookup"><span data-stu-id="171e7-153">Sent</span></span>                                          | <span data-ttu-id="171e7-154">전송되지 않음</span><span class="sxs-lookup"><span data-stu-id="171e7-154">Not sent</span></span>                                            |
| <span data-ttu-id="171e7-155">전체</span><span class="sxs-lookup"><span data-stu-id="171e7-155">Full</span></span>                            | <span data-ttu-id="171e7-156">보냄</span><span class="sxs-lookup"><span data-stu-id="171e7-156">Sent</span></span>                                          | <span data-ttu-id="171e7-157">보냄</span><span class="sxs-lookup"><span data-stu-id="171e7-157">Sent</span></span>                                                |

<span data-ttu-id="171e7-158">Windows 10에 대한 구성이 위의 표에 따라 잘못 구성된 경우 더 낮은 데이터 수집 설정으로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="171e7-158">If your configurations for Windows 10 are misconfigured in accordance with the preceding table, we will fall back to the lesser data collection setting.</span></span>

<span data-ttu-id="171e7-159">예를 들어 다음과 같은 가치를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="171e7-159">For example:</span></span>

- <span data-ttu-id="171e7-160">"사용 현황 및 크래시 관련 데이터 보고를 사용하도록 설정" 정책을 **사용**으로 설정했지만 Windows 진단 데이터 설정이 **기본**으로 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="171e7-160">You set the "Enable usage and crash-related data reporting" policy to **Enabled** but the Windows Diagnostic data setting is set to **Basic**.</span></span> <span data-ttu-id="171e7-161">사용 현황 및 크래시 관련 데이터를 전송하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="171e7-161">We won't send usage and crash-related data.</span></span>
- <span data-ttu-id="171e7-162">"Microsoft 서비스를 개선하기 위해 사이트 정보를 보냄"이 \*\*사용 안 \*\*으로 설정되고 Windows 진단 데이터 설정이 **전체**로 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="171e7-162">You set the "Send site information to improve Microsoft services" policy to **Disabled** but the Windows Diagnostic data setting is set to **Full**.</span></span> <span data-ttu-id="171e7-163">사용자가 방문하는 사이트에 대한 정보를 전송하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="171e7-163">We won't send information about the sites that are visited.</span></span>

<span data-ttu-id="171e7-164">이전 설정에 대한 올바른 구현 방법은 "사용 현황 및 크래시 관련 데이터 보고를 사용하도록 설정" 정책을 **사용**으로 설정하고 Windows 진단 데이터 설정을 **고급** 또는 **전체**로 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="171e7-164">The correct implementation for the previous settings is to set the "Enable usage and crash-related data reporting" policy to **Enabled** and set the Windows Diagnostic data setting to **Enhanced** or **Full**.</span></span>

## <span data-ttu-id="171e7-165">추가 개인정보처리방침 옵션</span><span class="sxs-lookup"><span data-stu-id="171e7-165">Additional privacy policy options</span></span>

<span data-ttu-id="171e7-166">데이터 프라이버시와 관련된 다음 그룹 정책을 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="171e7-166">You may want to consider the following group policies related to data privacy:</span></span>

- <span data-ttu-id="171e7-167">특정 사이트에서 쿠키 차단</span><span class="sxs-lookup"><span data-stu-id="171e7-167">Block cookies on specific sites</span></span>
- <span data-ttu-id="171e7-168">타사 쿠키 차단</span><span class="sxs-lookup"><span data-stu-id="171e7-168">Block third-party cookies</span></span>
- <span data-ttu-id="171e7-169">Do Not Track 구성</span><span class="sxs-lookup"><span data-stu-id="171e7-169">Configure Do Not Track</span></span>
- <span data-ttu-id="171e7-170">InPrivate 모드 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="171e7-170">Disable InPrivate mode</span></span>

## <span data-ttu-id="171e7-171">기타 참조</span><span class="sxs-lookup"><span data-stu-id="171e7-171">See also</span></span>

- [<span data-ttu-id="171e7-172">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="171e7-172">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="171e7-173">Microsoft Edge 정책</span><span class="sxs-lookup"><span data-stu-id="171e7-173">Microsoft Edge policies</span></span>](microsoft-edge-policies.md)
- [<span data-ttu-id="171e7-174">Microsoft Edge 개인 정보 백서</span><span class="sxs-lookup"><span data-stu-id="171e7-174">Microsoft Edge Privacy Whitepaper</span></span>](https://docs.microsoft.com/microsoft-edge/privacy-whitepaper)
