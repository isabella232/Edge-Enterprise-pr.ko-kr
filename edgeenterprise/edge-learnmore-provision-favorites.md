---
title: Microsoft Edge용 즐겨찾기 프로비전
ms.author: capoon
author: dan-wesley
manager: abutcher
ms.date: 09/29/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge용 즐겨찾기 프로비전
ms.openlocfilehash: 94bd42573bdbc0fd1b971ded1c82e5fe152acc54
ms.sourcegitcommit: 854dd73eb168960c0eb4b483f81a8efe88806a64
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2020
ms.locfileid: "11088714"
---
# Microsoft Edge용 즐겨찾기 프로비전

고객 피드백을 기반으로 즐겨찾기를 프로비저닝하도록 개선을 하였습니다. Microsoft Edge 버전 85부터는 관리자가 더 이상 즐겨찾기에 프로비전할 파일을 수동으로 만들 필요가 없습니다. 관리자는 Microsoft Edge UI를 사용하여 즐겨찾기 및 폴더를 추가하여 그룹 정책으로 내보낼 수 있는 파일을 생성할 수 있습니다.

이 문서에서는 조직에 대한 즐겨찾기 및 폴더 집합을 프로비전하는 방법에 대해 설명합니다. [즐겨찾기 구성](https://docs.microsoft.com//DeployEdge/microsoft-edge-policies#configure-favorites) 정책을 사용하여 즐겨찾기 및 폴더를 프로비전할 수 있습니다.

> [!NOTE]
> 이 문서는 Microsoft Edge 버전 85 이상에 적용됩니다.

## 필수 구성 요소 및 권장 사항

- Microsoft Edge 버전 85를 사용하며 그룹 정책에 알맞은 관리 템플릿을 설치한 경우
- Microsoft Edge에서 새 프로필을 사용하여 이러한 즐겨찾기를 프로비전하는 것이 좋습니다. 해당 프로필과 함께 저장된 모든 즐겨찾기가 내보내기에 포함됩니다.  

## 즐겨찾기 및 폴더 프로비전

다음 단계를 사용하여 사용자에 대한 즐겨찾기와 폴더를 프로비전합니다.

1. Microsoft Edge 주소 표시줄로 이동하고 다음 URL을 입력합니다. *edge://flags/#edge-favorites-admin-export*.
2. **관리자용 즐겨찾기 구성 내보내기** 아래의 드롭다운 목록에서 **사용**을 선택한 다음 **다시 시작**을 클릭합니다.

3. *edge://favorites* **즐겨찾기** 페이지로 이동하여 프로비전하려는 즐겨찾기나 폴더를 추가할 수 있습니다.

<!--
4. On the **Favorites bar**, click **Add folder**. The folder structure of favorites that are set in the profile you're using will be reflected in the folder you provision for your users. The next screenshot shows "Managed favorites", the folder we'll use to provision favorites.

   ![Add a folder](media/edge-learnmore-provision-favorites/provision-favorites-add-folder.png)

   > [!TIP]
   > Add existing folders that contain favorites you want to provision for your users.

5. Select "Managed favorites" and then click **Add favorite**. The next screenshot shows the favorite we've added.

   ![Add a favorite](media/edge-learnmore-provision-favorites/provision-favorites-add-favorite.png)-->

4. 즐겨찾기와 폴더를 추가하는 작업을 완료 시, 이들을 **즐겨찾기 구성** 정책에서 사용될 수 있도록 내보내기를 합니다. 주소 표시줄로 이동하고 *edge://favorites*로 이동한 후, 줄임표 "**...**"를 클릭하고 **즐겨찾기 구성 내보내기**를 선택합니다. 다음 스크린샷은 즐겨찾기를 프로비저닝할 때 사용할 수 있는 옵션을 보여줍니다.

   ![즐겨찾기 작업을 하기 위한 메뉴 옵션](media/edge-learnmore-provision-favorites/provision-favorites-menu-options.png)

5. **즐겨찾기 구성 내보내기**에서 사용자에게 표시되는 폴더의 이름을 제공합니다. 폴더 이름을 입력하고 사용하려는 플랫폼 형식을 선택합니다. **클립보드로 복사**를 클릭합니다. 다음 스크린샷은 폴더 이름에 대한 "관리형 즐겨찾기"를 보여주고 플랫폼은 Windows입니다.

   ![Windows 폴더로 즐겨찾기를 내보내기 위한 대화 상자입니다.](media/edge-learnmore-provision-favorites/provision-favorites-export.png)

6. 그룹 정책 편집기를 열고, *컴퓨터 구성/관리 템플릿/* 으로 이동하고 **즐겨찾기 구성**을 선택합니다. "즐겨찾기 구성" 정책을 사용하도록 설정합니다. **옵션:** 에서 즐겨찾기 구성 텍스트 영역에서 내보낸 콘텐츠를 붙여 넣은 다음 **적용**을 클릭합니다. 다음 스크린샷은 5단계에서의 "관리형 즐겨찾기" 폴더의 예시를 보여줍니다.

   ![Gpedit을 사용하여 "즐겨찾기 구성" 정책을 설정하고 구성합니다.](media/edge-learnmore-provision-favorites/provision-favorites-gpedit.png)

7. **확인**또는 **적용**을 클릭하여 이 정책 설정을 저장합니다.

## 참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)