---
title: Microsoft Edge용 Windows 업데이트
ms.author: jtkim
author: dan-wesley
manager: srugh
ms.date: 02/05/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge에 대한 Windows 업데이트입니다.
ms.openlocfilehash: 880e5a591ee23ff852981e73fe4fc4cd815be9ad
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447152"
---
# <a name="windows-updates-to-support-the-next-version-of-microsoft-edge"></a><span data-ttu-id="c042b-103">다음 버전 Microsoft Edge를 지원하기 위한 Windows 업데이트</span><span class="sxs-lookup"><span data-stu-id="c042b-103">Windows updates to support the next version of Microsoft Edge</span></span>

<span data-ttu-id="c042b-104">이 문서에서는 다음 버전 Microsoft Edge를 지원하기 위해 Windows를 업데이트하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c042b-104">This article describes how Windows will be updated to support the next version of Microsoft Edge.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c042b-105">Microsoft Edge 레거시 서비스 종료에 대한 Microsoft Edge [제품](https://aka.ms/EdgeLegacyEOS) 팀 블로그 게시물을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c042b-105">Refer to the Microsoft Edge product team [blog post](https://aka.ms/EdgeLegacyEOS) about Microsoft Edge Legacy end of service.</span></span>

> [!NOTE]
> <span data-ttu-id="c042b-106">이 문서는 Microsoft Edge 안정 채널에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c042b-106">This article applies to the Microsoft Edge Stable channel.</span></span>

## <a name="microsoft-edge-and-the-windows-release-cycle"></a><span data-ttu-id="c042b-107">Microsoft Edge 및 Windows 릴리스 주기</span><span class="sxs-lookup"><span data-stu-id="c042b-107">Microsoft Edge and the Windows release cycle</span></span>

<span data-ttu-id="c042b-108">다음 버전 Microsoft Edge는 더 빈번하고 더 유연한 업데이트 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c042b-108">The next version of Microsoft Edge features more frequent and more flexible updating capabilities.</span></span> <span data-ttu-id="c042b-109">브라우저 릴리스가 Windows 주요 릴리스에 연결되어 있지 않기 때문에 운영 체제는 다음 버전 Microsoft Edge가 Windows에 원활하게 적용되도록 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="c042b-109">Because browser releases aren't bound to the Windows major releases, changes will be made to the operating system to ensure that the next version of Microsoft Edge fits seamlessly into Windows.</span></span> <span data-ttu-id="c042b-110">따라서 기능 업데이트는 (대략) 6주 주기로 릴리스됩니다.</span><span class="sxs-lookup"><span data-stu-id="c042b-110">As a result, feature updates will be released on a 6-week cycle (approximately).</span></span> <span data-ttu-id="c042b-111">보안 및 호환성 업데이트는 필요한 경우 제공될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="c042b-111">Security and compatibility updates will be shipped as needed.</span></span>

## <a name="updates-and-the-user-experience"></a><span data-ttu-id="c042b-112">업데이트와 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="c042b-112">Updates and the user experience</span></span>

<span data-ttu-id="c042b-113">업데이트는 다음 버전 Microsoft Edge의 안정 채널이 설치될 때까지 사용자 환경을 변경하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c042b-113">Updates won’t change the user experience until the Stable channel of the next version of Microsoft Edge is installed.</span></span> <span data-ttu-id="c042b-114">Microsoft Edge Beta, Dev 또는 Canary를 설치하면 Windows 변경 사항이 트리거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c042b-114">Installing Microsoft Edge Beta, Dev, or Canary won’t trigger any changes in Windows.</span></span> <span data-ttu-id="c042b-115">이러한 브라우저 릴리스는 기존 브라우저와 나란히 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="c042b-115">These browser releases will be installed alongside existing browsers.</span></span>

<span data-ttu-id="c042b-116">모든 업데이트가 적용되고 다음 버전 Microsoft Edge의 안정 채널이 시스템 수준에서 설치되면 다음 변경 사항이 시스템에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c042b-116">When all the updates are applied AND the Stable channel of the next version of Microsoft Edge is installed at the system-level, the following changes will take effect on the system:</span></span>

- <span data-ttu-id="c042b-117">현재 버전 Microsoft Edge의 모든 시작 메뉴 핀, 타일 및 바로 가기가 다음 버전 Microsoft Edge으로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="c042b-117">All start menu pins, tiles, and shortcuts for the current version of Microsoft Edge will migrate to the next version of Microsoft Edge.</span></span>
- <span data-ttu-id="c042b-118">현재 버전 Microsoft Edge의 모든 작업 표시줄 핀 및 바로 가기가 다음 버전 Microsoft Edge으로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="c042b-118">All taskbar pins and shortcuts for the current version of Microsoft Edge will migrate to the next version of Microsoft Edge.</span></span>
- <span data-ttu-id="c042b-119">다음 버전 Microsoft Edge는 작업 표시줄에 고정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c042b-119">The next version of Microsoft Edge will be pinned to the taskbar.</span></span> <span data-ttu-id="c042b-120">현재 버전 Microsoft Edge이 이미 고정되어 있는 경우 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="c042b-120">If the current version of Microsoft Edge is already pinned, it will be replaced.</span></span>
- <span data-ttu-id="c042b-121">다음 버전 Microsoft Edge가 바탕 화면에 바로 가기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c042b-121">The next version of Microsoft Edge will add a shortcut to the desktop.</span></span> <span data-ttu-id="c042b-122">현재 버전 Microsoft Edge 바로 가기가 이미 있는 경우 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="c042b-122">If the current version of Microsoft Edge already has a shortcut, it will be replaced.</span></span>
- <span data-ttu-id="c042b-123">기본적으로 Microsoft Edge가 처리하는 대부분의 프로토콜이 다음 버전 Microsoft Edge으로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="c042b-123">Most protocols that Microsoft Edge handles by default will be migrated to the next version of Microsoft Edge.</span></span>
- <span data-ttu-id="c042b-124">현재 버전 Microsoft Edge는 설정, 모든 앱 및 모든 파일 또는 프로토콜 지원 대화 상자를 포함하여 OS의 모든 UX 화면에서 숨겨집니다.</span><span class="sxs-lookup"><span data-stu-id="c042b-124">Current Microsoft Edge will be hidden from all UX surfaces in the OS, including settings, all apps, and any file or protocol support dialogs.</span></span>
- <span data-ttu-id="c042b-125">현재 버전 Microsoft Edge를 시작하려는 모든 시도는 다음 버전 Microsoft Edge로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="c042b-125">All attempts to launch the current version of Microsoft Edge will redirect to the next version of Microsoft Edge.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c042b-126">사용자 수준 설치는 이러한 동작을 트리거하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c042b-126">User-level installs won’t trigger these behaviors.</span></span>

<span data-ttu-id="c042b-127">위 변경 내용과 함께 다음 버전 Microsoft Edge의 안정 채널이 설치되어 있는지 여부에 관계없이 발생하는 변경 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c042b-127">Along with the previous changes, there are changes that will happen regardless of whether the Stable channel of the next version of Microsoft Edge is installed.</span></span>

- <span data-ttu-id="c042b-128">Microsoft Edge는 다음 버전 Microsoft Edge가 지원하지 않는 전자책 및 XML 프로토콜의 등록을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="c042b-128">Microsoft Edge will de-register for the books and XML protocols that the next version of Microsoft Edge doesn't support.</span></span> <span data-ttu-id="c042b-129">사용자가 이러한 프로토콜을 열려고 하면 기본 앱을 선택하라는 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c042b-129">Users attempting to open these protocols will get a dialog that prompts them to choose a default app.</span></span> <span data-ttu-id="c042b-130">[전자책을 계속 읽으려면 ePub 앱 다운로드](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fsupport.microsoft.com%2Fhelp%2F4517840&data=02%7C01%7Cv-danwes%40microsoft.com%7Cc9f8571b880549c30fcf08d72be5eaf9%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637026138803983526&sdata=qtb3DvVZQ6H%2FFXnBievkl%2B%2BngAQXwl340PcH8kRc3y4%3D&reserved=0)에서 전자책 지원에 대한 자세한 내용을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="c042b-130">Learn more about changes to books support at [Download an ePub app to keep reading e-books](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fsupport.microsoft.com%2Fhelp%2F4517840&data=02%7C01%7Cv-danwes%40microsoft.com%7Cc9f8571b880549c30fcf08d72be5eaf9%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637026138803983526&sdata=qtb3DvVZQ6H%2FFXnBievkl%2B%2BngAQXwl340PcH8kRc3y4%3D&reserved=0).</span></span>

## <a name="timeline"></a><span data-ttu-id="c042b-131">타임라인</span><span class="sxs-lookup"><span data-stu-id="c042b-131">Timeline</span></span>

<span data-ttu-id="c042b-132">설명한 환경을 지원하기 위해 필요한 변경 사항은 각 Windows 버전에 대한 세 가지 업데이트와 함께 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="c042b-132">The changes needed to support the described experience will be delivered with three updates for different versions of Windows.</span></span>

### <a name="windows-versions-1903-and-1909"></a><span data-ttu-id="c042b-133">Windows 버전 1903 및 1909</span><span class="sxs-lookup"><span data-stu-id="c042b-133">Windows versions 1903 and 1909</span></span>

- <span data-ttu-id="c042b-134">2019년 8월 보안 업데이트와 함께 제공되는 선택적 2019년 7월 업데이트의 첫 번째 변경 내용 집합.</span><span class="sxs-lookup"><span data-stu-id="c042b-134">First set of changes in optional July 2019 update, delivered with the August 2019 security update.</span></span>
- <span data-ttu-id="c042b-135">2019년 9월 보안 업데이트와 함께 제공되는 선택적 2019년 8월 업데이트의 두 번째 변경 내용 집합.</span><span class="sxs-lookup"><span data-stu-id="c042b-135">Second set of changes in the optional August 2019 update, delivered with the September 2019 security update.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c042b-136">이 업데이트에서는 Microsoft Edge가 XML 프로토콜의 등록을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="c042b-136">This is the update where Microsoft Edge will de-register for the XML protocol.</span></span>

- <span data-ttu-id="c042b-137">2019년 10월 보안 업데이트와 함께 제공되는 선택적 2019년 9월 업데이트의 세 번째 변경 내용 집합.</span><span class="sxs-lookup"><span data-stu-id="c042b-137">Third set of changes in the optional September 2019 update, delivered with the October 2019 security update.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c042b-138">이 업데이트에서는 Microsoft Edge가 더 이상 전자책을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c042b-138">This is the update where Microsoft Edge will no longer support eBooks.</span></span>

### <a name="windows-versions-1709-1803-and-1809"></a><span data-ttu-id="c042b-139">Windows 버전 1709, 1803 및 1809</span><span class="sxs-lookup"><span data-stu-id="c042b-139">Windows versions 1709, 1803, and 1809</span></span>

- <span data-ttu-id="c042b-140">2019년 9월 보안 업데이트와 함께 제공되는 선택적 2019년 8월 업데이트의 첫 번째 변경 내용 집합.</span><span class="sxs-lookup"><span data-stu-id="c042b-140">First set of changes in an optional August 2019 update, delivered with the September 2019 security update.</span></span>
- <span data-ttu-id="c042b-141">2019년 10월 보안 업데이트와 함께 제공되는 선택적 2019년 9월 업데이트의 두 번째 변경 내용 집합.</span><span class="sxs-lookup"><span data-stu-id="c042b-141">Second set of changes in an optional September 2019 update, delivered with the October 2019 security update.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c042b-142">이 업데이트에서는 Microsoft Edge가 XML 프로토콜의 등록을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="c042b-142">This is the update where Microsoft Edge will de-register for the XML protocol.</span></span>

- <span data-ttu-id="c042b-143">2019년 11월 보안 업데이트와 함께 제공되는 선택적 2019년 10월 업데이트의 세 번째 변경 내용 집합.</span><span class="sxs-lookup"><span data-stu-id="c042b-143">Third set of changes in an optional October 2019 update, delivered with the November 2019 security update.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c042b-144">이 업데이트에서는 Microsoft Edge가 더 이상 전자책을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c042b-144">This is the update where Microsoft Edge will no longer support eBooks.</span></span>

<span data-ttu-id="c042b-145">다음 표에서는 각 변경 내용 집합의 특정 업데이트에 대한 세부 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c042b-145">The following table gives the details for specific updates in each set of changes.</span></span>

| <span data-ttu-id="c042b-146">Windows10</span><span class="sxs-lookup"><span data-stu-id="c042b-146">Windows 10</span></span> | <span data-ttu-id="c042b-147">추가 정보</span><span class="sxs-lookup"><span data-stu-id="c042b-147">More Information</span></span> | <span data-ttu-id="c042b-148">필수 다운로드</span><span class="sxs-lookup"><span data-stu-id="c042b-148">Required Download</span></span> |
|--|--|--|
| <span data-ttu-id="c042b-149">버전 1709</span><span class="sxs-lookup"><span data-stu-id="c042b-149">Version 1709</span></span> | [<span data-ttu-id="c042b-150">KB4525241</span><span class="sxs-lookup"><span data-stu-id="c042b-150">KB4525241</span></span>](https://support.microsoft.com/help/4525241/windows-10-update-kb4525241) | [<span data-ttu-id="c042b-151">Windows 10 버전 1709에 대한 누적 업데이트</span><span class="sxs-lookup"><span data-stu-id="c042b-151">Cumulative Update for Windows 10 Version 1709</span></span>](https://www.catalog.update.microsoft.com/Search.aspx?q=4525241) |
| <span data-ttu-id="c042b-152">버전 1803</span><span class="sxs-lookup"><span data-stu-id="c042b-152">Version 1803</span></span>  | [<span data-ttu-id="c042b-153">KB4525237</span><span class="sxs-lookup"><span data-stu-id="c042b-153">KB4525237</span></span>](https://support.microsoft.com/help/4525237/windows-10-update-kb4525237) | [<span data-ttu-id="c042b-154">Windows 10 버전 1803에 대한 누적 업데이트</span><span class="sxs-lookup"><span data-stu-id="c042b-154">Cumulative Update for Windows 10 Version 1803</span></span>](https://www.catalog.update.microsoft.com/Search.aspx?q=KB4525237) |
| <span data-ttu-id="c042b-155">버전 1809</span><span class="sxs-lookup"><span data-stu-id="c042b-155">Version 1809</span></span>  | [<span data-ttu-id="c042b-156">KB4523205</span><span class="sxs-lookup"><span data-stu-id="c042b-156">KB4523205</span></span>](https://support.microsoft.com/help/4523205/windows-10-update-kb4523205) | [<span data-ttu-id="c042b-157">Windows 10 버전 1809에 대한 누적 업데이트</span><span class="sxs-lookup"><span data-stu-id="c042b-157">Cumulative Update for Windows 10 Version 1809</span></span>](https://www.catalog.update.microsoft.com/Search.aspx?q=4523205) |
| <span data-ttu-id="c042b-158">버전 1903 및 1909</span><span class="sxs-lookup"><span data-stu-id="c042b-158">Version 1903 and 1909</span></span> |[<span data-ttu-id="c042b-159">KB4517389</span><span class="sxs-lookup"><span data-stu-id="c042b-159">KB4517389</span></span>](https://support.microsoft.com/help/4517389/windows-10-update-kb4517389)  | [<span data-ttu-id="c042b-160">Windows 10 버전 1903 및 1909에 대한 누적 업데이트</span><span class="sxs-lookup"><span data-stu-id="c042b-160">Cumulative Update for Windows 10 Version 1903 and 1909</span></span>](https://www.catalog.update.microsoft.com/Search.aspx?q=4517389) |

## <a name="see-also"></a><span data-ttu-id="c042b-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c042b-161">See also</span></span>

- [<span data-ttu-id="c042b-162">Microsoft Edge 엔터프라이즈 방문 페이지</span><span class="sxs-lookup"><span data-stu-id="c042b-162">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="c042b-163">Microsoft Edge 설명서</span><span class="sxs-lookup"><span data-stu-id="c042b-163">Microsoft Edge documentation</span></span>](./index.yml)