---
title: 위험할 수 있는 파일 다운로드 식별 및 중단
ms.author: kvice
author: AndreaLBarr
manager: srugh
ms.date: 01/10/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 위험할 Microsoft Edge 파일을 식별하고 다운로드를 중단하는 방법 이해
ms.openlocfilehash: 436c85248ef4012d75a9786c36e8f48d53f720d1
ms.sourcegitcommit: e7f3098d8b7d91cae20b5778a71a87daababc312
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "12298196"
---
# <a name="identify-and-interrupt-downloads-of-potentially-dangerous-files"></a>위험할 수 있는 파일 다운로드 식별 및 중단

Microsoft Edge 형식 정책 구성 요소는 파일 다운로드를 관리하기 위한 "위험성" 수준으로 파일을 분류합니다. 무해한 파일(예: 파일)은 자유롭게 다운로드할 수 있는 반면, a와 같은 위험할 수 있는 파일은 더 높은 수준의 준비를 `.txt` `.dll` 거치게 됩니다. 이 보안은 보다 보안에 민감한 사용자 환경을 제공합니다.

## <a name="how-microsoft-edge-determines-the-danger-level-of-a-file-type"></a>파일 Microsoft Edge 위험 수준을 결정하는 방법

Microsoft Edge 브라우저에서 해당 파일 형식 정책을 Chromium 상속합니다. 이러한 파일 형식 및 해당 분류는 [download_file_types.asciipb 파일에서 볼 수](https://source.chromium.org/chromium/chromium/src/+/main:components/safe_browsing/core/resources/download_file_types.asciipb;drc=af17ad3f07c1d8a24381eb7669bec0c2ffb86521) 있습니다. 이 파일에는 , 또는 **의**세 가지 값 danger_level 각 형식에 1개의 danger_level 있는 `DANGEROUS` 것이 `NOT_DANGEROUS` `ALLOW_ON_USER_GESTURE` 표시됩니다.

다음과 같은 두 가지 분류는 간단합니다.

- **NOT_DANGEROUS** 다운로드 요청이 우발적이어도 파일을 다운로드할 수 있습니다.
- **DANGEROUS**는 다운로드가 장치를 손상시킬 수 있다는 것을 브라우저가 항상 사용자에게 경고해야 한다는 것을 의미합니다.

세 번째 설정인 **ALLOW_ON_USER_GESTURE** 더 미묘합니다. 이러한 파일은 잠재적으로 위험할 수 있지만 사용자가 다운로드를 요청하는 경우 무해할 수 있습니다. Microsoft Edge 조건 중 하나에 충족되는 경우 이러한 다운로드를 자동으로 계속할 수 있습니다.

- 다운로드를 [](https://textslashplain.com/2020/05/18/browser-basics-user-gestures/) 시작한 네트워크 요청과 연결된 사용자 제스처가 있습니다. 예를 들어 사용자가 다운로드 링크를 클릭한 경우입니다.
- 가장 최근 자정(즉, 어제 또는 이전) 이전에 참조 출처(다운로드로 연결되는 페이지)를 방문한 기록이 있습니다. 이 기록된 방문은 사용자가 사이트를 방문한 기록을 찾은 경우를 암시합니다.

또한 사용자가 상황에 맞는 메뉴로 저장 명령을 사용하여 **** 링크를 명시적으로 시작하거나, 브라우저의 주소 표시줄에 직접 다운로드 URL을 입력하거나, 파일이 안전하다는 Microsoft Defender SmartScreen 다운로드가 자동으로 계속됩니다.

> [!NOTE]
> 버전 91부터는 Microsoft Edge 제스처가 없는 다운로드가 중단됩니다.

## <a name="user-experience-for-downloads-that-lack-a-gesture"></a>제스처가 없는 다운로드에 대한 사용자 환경

위험할 수 있는 유형에 대한 다운로드가 필요한 제스처 없이 시작되는 경우 Microsoft Edge "차단"으로 나타 내포되어 있습니다. 라는 `Keep` 명령은 `Delete` ...에서 사용할 수 **있습니다.** 사용자가 다운로드를 계속하거나 취소할 수 있도록 다운로드 항목에 대한 (타원) 옵션입니다.

:::image type="content" source="media/microsoft-edge-security-Download-interruptions/Dowload-was-blocked.png" alt-text="다운로드가 차단되고, 사용자가 다운로드를 유지하거나 삭제할 수 있습니다.":::

페이지에 `edge://downloads` 동일한 옵션이 표시됩니다. 다음 스크린샷은 이러한 옵션의 예를 보여 주며 예제입니다.

:::image type="content" source="media/microsoft-edge-security-Download-interruptions/msg-keep-delete-option.png" alt-text="다운로드가 차단되지만 사용자가 다운로드를 유지하거나 삭제할 수 있습니다.":::

## <a name="enterprise-controls-for-downloads"></a>Enterprise 컨트롤 다운로드

매일 사용하는 사이트에 대한 다운로드 중단이 발생하지 않는 반면, 거의 사용하지 않는 사이트에서는 합법적인 다운로드가 발생할 수 있습니다. 엔터프라이즈의 사용자 환경을 간소화하기 위해 그룹 정책을 사용할 수 있습니다.

기업은 [ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](/deployedge/microsoft-edge-policies#exemptdomainfiletypepairsfromfiletypedownloadwarnings)를 사용하여 특정 사이트에서 중단 없이 다운로드할 수 있는 파일 형식을 지정할 수 있습니다. 예를 들어 다음 정책을 사용하면 XML 파일을 중단 없이 contoso.com woodgrovebank.com 다운로드할 수 있으며 모든 사이트에서 MSG 파일을 다운로드할 수 있습니다.

`[{"file_extension":"xml","domains":["contoso.com", "woodgrovebank.com"]},
{"file_extension":"msg", "domains": ["*"]}]`

## <a name="file-types-requiring-a-gesture"></a>제스처가 필요한 파일 형식

최신 [파일 형식 정책](https://source.chromium.org/chromium/chromium/src/+/main:components/safe_browsing/core/resources/download_file_types.asciipb;drc=af17ad3f07c1d8a24381eb7669bec0c2ffb86521)은 Chromium 소스 코드에 게시됩니다. 2021년 5월 기준으로 하나 이상의 OS 플랫폼에서 `danger_level`/`ALLOW_ON_USER_GESTURE`의 파일 형식은 다음과 같습니다.
`crx, pl, py, pyc, pyo, pyw, rb, efi, oxt, msi, msp, mst, ade, adp, mad, maf, mag, mam, maq, mar, mas, mat, mav, maw, mda, mdb, mde, mdt, mdw, mdz, accdb, accde, accdr, accda, ocx, ops, paf, pcd, pif, plg, prf, prg, pst, cpi, partial, xrm-ms, rels, svg, xml, xsl, xsd, ps1, ps1xml, ps2, ps2xml, psc1, psc2, js, jse, vb, vbe, vbs, vbscript, ws, wsc, wsf, wsh, msh, msh1, msh2, mshxml, msh1xml, msh2xml, ad, app, application, appref-ms, asp, asx, bas, bat, chi, chm, cmd, com, cpl, crt, cer, der, eml, exe, fon, fxp, hlp, htt, inf, ins, inx, isu, isp, job, lnk, mau, mht, mhtml, mmc, msc, msg, reg, rgs, scr, sct, search-ms, settingcontent-ms, shb, shs, slk, u3p, vdx, vsx, vtx, vsdx, vssx, vstx, vsdm, vssm, vstm, vsd, vsmacros, vss, vst, vsw, xnk, cdr, dart, dc42, diskcopy42, dmg, dmgpart, dvdr, dylib, img, imgpart, ndif, service, smi, sparsebundle, sparseimage, toast, udif, action, definition, wflow, caction, as, cpgz, command, mpkg, pax, workflow, xip, mobileconfig, configprofile, internetconnect, networkconnect, pkg, deb, pet, pup, rpm, slp, out, run, bash, csh, ksh, sh, shar, tcsh, desktop, dex,apk`

## <a name="the-file-type-danger-level-may-vary-by-operating-system"></a>파일 형식 위험 수준은 운영 체제에 따라 다를 수 있습니다.

파일 형식 설정은 클라이언트 OS 플랫폼에 따라 달라지는 경우가 있습니다. 예를 들어 파일이 Mac에서 위험하지는 않은 반면 파일은 Mac에서 위험하지 `.exe` `.applescript` Windows.
