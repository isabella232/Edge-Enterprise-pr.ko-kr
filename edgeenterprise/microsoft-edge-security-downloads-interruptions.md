---
title: 잠재적으로 위험한 파일 다운로드 중단
ms.author: kvice
author: AndreaLBarr
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 잠재적으로 위험한 파일 다운로드 중단
ms.openlocfilehash: 527b98b54cf03f6c116624296c63803b57a7f0c4
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642674"
---
# <a name="interrupting-downloads-of-potentially-dangerous-files"></a><span data-ttu-id="00dfc-103">잠재적으로 위험한 파일 다운로드 중단</span><span class="sxs-lookup"><span data-stu-id="00dfc-103">Interrupting Downloads of Potentially Dangerous Files</span></span>

<span data-ttu-id="00dfc-104">Microsoft Edge의 파일 형식 정책 구성 요소를 사용하면 무해한 파일(예: `.txt`개 파일)을 무료로 다운로드할 수 있도록 파일을 "위험도" 수준에 따라 분류할 수 있으며, 잠재적으로 위험한 파일(예: `.dll`개 파일)은 더 높은 수준의 검사를 받고 보안을 중시하는 사용자 환경에 노출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00dfc-104">Microsoft Edge’s File Type Policies component allows files to be classified by their level of “dangerousness”, such that harmless files (e.g. `.txt` files) can be downloaded freely, whilst potentially-dangerous files (e.g. `.dll` files) are subjected to a higher degree of vetting and a more security-conscious user-experience.</span></span>

## <a name="determining-the-danger-level-of-a-file-type"></a><span data-ttu-id="00dfc-105">파일 형식의 위험 수준 확인</span><span class="sxs-lookup"><span data-stu-id="00dfc-105">Determining the Danger Level of a File Type</span></span>

<span data-ttu-id="00dfc-106">Microsoft Edge는 업스트림 Chromium 브라우저에서 파일 형식 정책을 상속합니다. [여기](https://source.chromium.org/chromium/chromium/src/+/main:components/safe_browsing/core/resources/download_file_types.asciipb)에서 목록의 현재 내용을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00dfc-106">Microsoft Edge inherits its file type policies from the upstream Chromium browser; you can view the current contents of the list [here](https://source.chromium.org/chromium/chromium/src/+/main:components/safe_browsing/core/resources/download_file_types.asciipb).</span></span> <span data-ttu-id="00dfc-107">목록 내에 각 유형에 세 가지 값 `DANGEROUS`, `NOT_DANGEROUS` 또는 `ALLOW_ON_USER_GESTURE` 중 하나인 dangera_level 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="00dfc-107">Within the list, you’ll see that each type has a danger_level, which is one of three values: `DANGEROUS`, `NOT_DANGEROUS`, or `ALLOW_ON_USER_GESTURE`.</span></span>

<span data-ttu-id="00dfc-108">처음 두 가지는 간단합니다. **NOT_DANGEROUS**는 다운로드가 실수로 발생한 경우에도 파일을 안전하게 다운로드할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="00dfc-108">The first two are simple: **NOT_DANGEROUS** means that the file is safe to download, even if the download was accidental.</span></span> <span data-ttu-id="00dfc-109">**DANGEROUS**는 다운로드가 장치를 손상시킬 수 있다는 것을 브라우저가 항상 사용자에게 경고해야 한다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="00dfc-109">**DANGEROUS** means that the browser should always warn the user that the download may harm their device.</span></span>

<span data-ttu-id="00dfc-110">세 번째 설정은 **ALLOW_ON_USER_GESTURE**로 더 미세합니다.</span><span class="sxs-lookup"><span data-stu-id="00dfc-110">The third setting **ALLOW_ON_USER_GESTURE** is more subtle.</span></span> <span data-ttu-id="00dfc-111">이러한 파일은 잠재적으로 위험하지만 사용자가 다운로드를 요청한 경우 대부분 무해합니다.</span><span class="sxs-lookup"><span data-stu-id="00dfc-111">Such files are potentially dangerous, but most likely harmless if the user requested the download.</span></span> <span data-ttu-id="00dfc-112">다음 두 조건이 충족되면 Microsoft Edge에서 이러한 다운로드가 자동으로 진행되도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="00dfc-112">Microsoft Edge will allow such downloads to proceed automatically if two conditions are met:</span></span>

1. <span data-ttu-id="00dfc-113">다운로드를 시작한 네트워크 요청과 관련된 [사용자 제스처](https://textslashplain.com/2020/05/18/browser-basics-user-gestures/)가 있습니다(예: 사용자가 다운로드 링크를 클릭함).</span><span class="sxs-lookup"><span data-stu-id="00dfc-113">There is a [user gesture](https://textslashplain.com/2020/05/18/browser-basics-user-gestures/) associated with the network request that initiated the download (e.g., the user clicked a link to the download).</span></span>
2. <span data-ttu-id="00dfc-114">가장 최근 자정(즉, 어제 또는 그 이전) 이전에 참조 출처(다운로드로 연결되는 페이지)에 대한 사전 방문이 기록되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00dfc-114">There is a recorded prior visit to the referring origin (the page linking to the download) prior to the most recent midnight (i.e., yesterday or earlier).</span></span> <span data-ttu-id="00dfc-115">이는 사용자에게 사이트 방문 기록이 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="00dfc-115">This implies that the user has a history of visiting the site.</span></span>

<span data-ttu-id="00dfc-116">사용자가 **다른 이름으로 링크 저장** 메뉴 명령을 사용하여 다운로드를 명시적으로 시작했거나 브라우저 주소 표시줄에 다운로드 URL을 직접 입력하거나 Microsoft Defender SmartScreen에서 파일이 안전하다고 표시한 경우에도 다운로드가 자동으로 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="00dfc-116">The download will also proceed automatically if the user explicitly initiated it by using the **Save link as** context menu command, entered the download’s URL directly into the browser’s address bar, or if Microsoft Defender SmartScreen indicated that the file is safe.</span></span>

<span data-ttu-id="00dfc-117">**업데이트:** 버전 91부터는 Microsoft Edge가 필요한 제스처가 없는 다운로드를 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="00dfc-117">**Update:** Starting in version 91, Microsoft Edge will interrupt downloads that lack the required gesture.</span></span>

## <a name="user-experience-for-downloads-lacking-gestures"></a><span data-ttu-id="00dfc-118">제스처가 부족한 다운로드에 대한 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="00dfc-118">User Experience for Downloads Lacking Gestures</span></span>

<span data-ttu-id="00dfc-119">잠재적으로 위험한 유형의 다운로드가 필요한 제스처 없이 시작되면 Microsoft Edge는 다운로드가 "차단"되었다고 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="00dfc-119">If a download for a potentially dangerous type starts without the required gesture, Microsoft Edge states that the download “was blocked”.</span></span> <span data-ttu-id="00dfc-120">이름이 `Keep` 및 `Delete`인 명령은 ...에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00dfc-120">Commands named `Keep` and `Delete` are available from the …</span></span> <span data-ttu-id="00dfc-121">메뉴를 클릭하여 다운로드를 계속하거나 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00dfc-121">menu on the download item to allow the user to continue or cancel the download.</span></span>

:::image type="content" source="media/microsoft-edge-security-Download-interruptions/Dowload-was-blocked.png" alt-text="다운로드가 차단되었습니다.":::

<span data-ttu-id="00dfc-123">`edge://downloads` 페이지에서 사용자에게 동일한 옵션이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="00dfc-123">On the `edge://downloads`, page, the user will see the same options:</span></span>

:::image type="content" source="media/microsoft-edge-security-Download-interruptions/msg-keep-delete-option.png" alt-text="MSG 삭제 유지 옵션":::

## <a name="enterprise-controls"></a><span data-ttu-id="00dfc-125">엔터프라이즈 컨트롤</span><span class="sxs-lookup"><span data-stu-id="00dfc-125">Enterprise Controls</span></span>

<span data-ttu-id="00dfc-126">매일 사용하는 사이트에 대한 다운로드 중단이 발생하지 않는 반면, 거의 사용하지 않는 사이트에서는 합법적인 다운로드가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00dfc-126">While users are unlikely to encounter download interruptions for sites they use every day, they might encounter them for legitimate downloads on sites that they use rarely.</span></span> <span data-ttu-id="00dfc-127">엔터프라이즈의 사용자 환경을 간소화하기 위해 그룹 정책을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00dfc-127">To help streamline the user-experience for Enterprises, a Group Policy is available.</span></span>

<span data-ttu-id="00dfc-128">기업은 [ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](/deployedge/microsoft-edge-policies#exemptdomainfiletypepairsfromfiletypedownloadwarnings)를 사용하여 특정 사이트에서 중단 없이 다운로드할 수 있는 파일 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00dfc-128">Enterprises can use [ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](/deployedge/microsoft-edge-policies#exemptdomainfiletypepairsfromfiletypedownloadwarnings) to specify the filetypes that are allowed to download from specific sites without interruption.</span></span> <span data-ttu-id="00dfc-129">예를 들어 다음 정책을 사용하면 XML 파일을 중단 없이 contoso.com 및 woodgrovebank.com에서 다운로드하고 MSG 파일을 모든 사이트에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00dfc-129">For instance, the following policy allows XML files to download from contoso.com and woodgrovebank.com without interruption, and MSG files to download from any site.</span></span>

`[{"file_extension":"xml","domains":["contoso.com", "woodgrovebank.com"]},
{"file_extension":"msg", "domains": ["*"]}]`

## <a name="file-types-requiring-a-gesture"></a><span data-ttu-id="00dfc-130">제스처가 필요한 파일 형식</span><span class="sxs-lookup"><span data-stu-id="00dfc-130">File Types Requiring a Gesture</span></span>

<span data-ttu-id="00dfc-131">최신 [파일 형식 정책](https://source.chromium.org/chromium/chromium/src/+/main:components/safe_browsing/core/resources/download_file_types.asciipb)은 Chromium 소스 코드에 게시됩니다.</span><span class="sxs-lookup"><span data-stu-id="00dfc-131">The latest [file types policies](https://source.chromium.org/chromium/chromium/src/+/main:components/safe_browsing/core/resources/download_file_types.asciipb) are published in the Chromium source code.</span></span> <span data-ttu-id="00dfc-132">2021년 5월 기준으로 하나 이상의 OS 플랫폼에서 `danger_level`/`ALLOW_ON_USER_GESTURE`의 파일 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="00dfc-132">As of May 2021, file types with a `danger_level` of `ALLOW_ON_USER_GESTURE` on at least one OS platform include:</span></span>
`crx, pl, py, pyc, pyo, pyw, rb, efi, oxt, msi, msp, mst, ade, adp, mad, maf, mag, mam, maq, mar, mas, mat, mav, maw, mda, mdb, mde, mdt, mdw, mdz, accdb, accde, accdr, accda, ocx, ops, paf, pcd, pif, plg, prf, prg, pst, cpi, partial, xrm-ms, rels, svg, xml, xsl, xsd, ps1, ps1xml, ps2, ps2xml, psc1, psc2, js, jse, vb, vbe, vbs, vbscript, ws, wsc, wsf, wsh, msh, msh1, msh2, mshxml, msh1xml, msh2xml, ad, app, application, appref-ms, asp, asx, bas, bat, chi, chm, cmd, com, cpl, crt, cer, der, eml, exe, fon, fxp, hlp, htt, inf, ins, inx, isu, isp, job, lnk, mau, mht, mhtml, mmc, msc, msg, reg, rgs, scr, sct, search-ms, settingcontent-ms, shb, shs, slk, u3p, vdx, vsx, vtx, vsdx, vssx, vstx, vsdm, vssm, vstm, vsd, vsmacros, vss, vst, vsw, xnk, cdr, dart, dc42, diskcopy42, dmg, dmgpart, dvdr, dylib, img, imgpart, ndif, service, smi, sparsebundle, sparseimage, toast, udif, action, definition, wflow, caction, as, cpgz, command, mpkg, pax, workflow, xip, mobileconfig, configprofile, internetconnect, networkconnect, pkg, deb, pet, pup, rpm, slp, out, run, bash, csh, ksh, sh, shar, tcsh, desktop, dex,apk`

## <a name="danger-level-may-vary-by-operating-system"></a><span data-ttu-id="00dfc-133">위험 수준은 운영 체제에 따라 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00dfc-133">Danger Level May Vary By Operating System</span></span>

<span data-ttu-id="00dfc-134">파일 형식 설정은 클라이언트 OS 플랫폼에 따라 달라지는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00dfc-134">File type settings sometimes vary depending on the client OS platform.</span></span> <span data-ttu-id="00dfc-135">예를 들어 `.exe`은(는) Mac에서 위험하지 않고 `.applescript`은(는) Windows에서 무해합니다.</span><span class="sxs-lookup"><span data-stu-id="00dfc-135">For instance, an `.exe` is not dangerous on a Mac, while an `.applescript` is harmless on Windows.</span></span>
