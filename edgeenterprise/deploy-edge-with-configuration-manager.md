---
title: System Center Configuration Manager를 사용하여 Microsoft Edge 배포
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: SCCM(System Center Configuration Manager)를 사용하여 Microsoft Edge를 배포하는 방법을 알아봅니다.
ms.openlocfilehash: b0efa986c7f230f455d052f8e003616e081e324a
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "11979669"
---
# <a name="deploy-microsoft-edge-using-system-center-configuration-manager"></a>System Center Configuration Manager를 사용하여 Microsoft Edge 배포

이 문서에서는 SCCM(System Center Configuration Manager)을 사용하여 Microsoft Edge 배포를 자동화하는 방법을 보여 줍니다.

>[!NOTE]
>이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.

## <a name="before-you-begin"></a>시작하기 전에

[Configuration Manager에서 응용 프로그램 관리 소개](/sccm/apps/understand/introduction-to-application-management)를 검토하세요. 이 응용 프로그램 관리 문서는 이 문서에 사용된 용어를 이해하는 데 도움이 되며, 응용 프로그램을 설치하기 위해 사이트를 준비하는 방법을 안내합니다.

[Microsoft Edge엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)에서 Microsoft Edge 엔터프라이즈 설치 파일(**MicrosoftEdgeDevEnterpriseX64.msi** 및/또는 **MicrosoftEdgeDevEnterpriseX86.msi**)을 다운로드합니다.

Microsoft Edge 설치 파일을 액세스할 수 있는 네트워크 위치에 저장해야 합니다.

## <a name="create-the-application"></a>응용 프로그램 만들기

응용 프로그램은 Configuration Manager 마법사를 사용하여 만듭니다.

### <a name="start-the-create-application-wizard-and-create-the-application"></a>응용 프로그램 만들기 마법사를 시작하고 응용 프로그램 만들기  

1. Configuration Manager 콘솔에서 **소프트웨어 라이브러리** > **응용 프로그램 관리** > **응용 프로그램**을 클릭합니다.  

2. **홈** 탭의 **만들기** 그룹에서 **응용 프로그램 만들기**를 클릭합니다. 또는 탐색 모음에서 **응용 프로그램**을 마우스 오른쪽 단추로 클릭한 다음 **응용 프로그램 만들기**를 클릭합니다.

    ![응용 프로그램 만들기](./media/edge-ent-deployment-sccm/edge-ent-create-app-1.png)

3. **응용 프로그램 만들기 마법사**의 **일반** 페이지에서 **설치 파일에서 이 응용 프로그램에 대한 정보 자동 검색** 확인란을 선택합니다. 그러면 마법사에서 일부 정보가 설치 .msi 파일에서 추출된 정보로 미리 채워집니다. 다음 정보를 입력합니다.  

   - **유형**: **Windows Installer(\*.msi 파일)** 를 선택합니다.  

   - **위치**: 설치 파일 **MicrosoftEdgeDevEnterpriseX64.msi** 또는 **MicrosoftEdgeDevEnterpriseX86.msi**의 위치를 입력합니다(또는 **찾아보기**를 클릭하여 위치를 선택). Configuration Manager가 설치 파일을 찾을 수 있도록 위치를 *\\\Server\Share\File* 형식으로 지정해야 합니다.  

   다음은 **이 응용 프로그램에 대한 설정 지정** 페이지의 예입니다.  

    ![이 응용 프로그램에 대한 설정 지정](./media/edge-ent-deployment-sccm/edge-ent-create-app-2.png)

4. **다음**을 클릭합니다. **가져온 정보** 페이지의 **자세히**에서 가져온 응용 프로그램 및 모든 관련 파일에 대한 정보를 볼 수 있습니다. 마법사를 계속하려면 **다음**을 클릭합니다.  

    ![가져온 정보 보기](./media/edge-ent-deployment-sccm/edge-ent-create-app-3.png)

5. **일반 정보** 페이지에서 응용 프로그램에 대한 정보를 추가할 수 있습니다. 예: 소프트웨어 버전, 관리자 설명 및 게시자. 이 정보를 활용하여 Configuration Manager 콘솔에서 응용 프로그램을 정렬하고 찾을 수 있습니다.

   또한 **설치 프로그램** 필드를 사용하여 PC에 응용 프로그램을 설치하는 데 사용되는 전체 명령줄을 지정할 수도 있습니다. 이를 편집하여 자체 속성(예: 무인 설치의 경우 **/q**)을 추가할 수 있습니다.

   다음 스크린샷은 **이 응용 프로그램에 대한 정보 지정** 필드가 사용되는 예를 보여 줍니다.

   ![응용 프로그램 메타데이터 지정](./media/edge-ent-deployment-sccm/edge-ent-create-app-5.png)

6. **다음**을 클릭합니다.
7. **요약** 페이지에서 **자세히** 아래에 있는 응용 프로그램 설정을 확인한 다음 마법사 사용을 마칠 수 있습니다. **다음**을 클릭합니다.  

    ![응용 프로그램 설정 세부 정보](./media/edge-ent-deployment-sccm/edge-ent-create-app-6.png)

8. **완료** 페이지에서 **닫기**를 클릭합니다.

    ![성공 대화 상자](./media/edge-ent-deployment-sccm/edge-ent-create-app-7.png)

응용 프로그램 만들기가 완료되었습니다. Configuration Manager에서 다음 단계를 수행하여 확인합니다.

- **소프트웨어 라이브러리** 작업 영역 선택
- **응용 프로그램 관리** 확장
- **응용 프로그램** 클릭.

다음 스크린샷은 이 문서에 사용된 예제를 보여 줍니다.  

![응용 프로그램](./media/edge-ent-deployment-sccm/edge-ent-create-app-8.png)

## <a name="change-application-properties-and-deployment-settings"></a>응용 프로그램 속성 및 배포 설정 변경

응용 프로그램을 만든 후, 필요한 경우 응용 프로그램 설정을 구체화할 수 있습니다. 응용 프로그램 속성을 확인하려면

- 응용 프로그램을 선택합니다.
- **홈**>**속성**에서 **속성**을 클릭합니다.  

   ![응용 프로그램 속성을 구성합니다.](./media/edge-ent-deployment-sccm/edge-ent-create-app-req-1.png)

 **<application name\> 응용 프로그램 속성** 대화 상자 페이지에 응용 프로그램의 동작을 변경하기 위해 구성할 수 있는 항목을 탭 형식 보기가 표시됩니다. 구성할 수 있는 설정에 대한 자세한 내용은 [응용 프로그램 만들기](/sccm/apps/deploy-use/create-applications)를 참조하세요.

이 예제에서는 응용 프로그램 배포 유형의 일부 속성을 변경합니다. 배포 속성을 변경하려면

1. **배포 유형** 탭을 클릭합니다.
2. **배포 유형:** 에서 응용 프로그램 **이름**을 선택합니다.
3. **편집**을 클릭합니다.

   ![배포 유형 편집](./media/edge-ent-deployment-sccm/edge-ent-create-app-req-2.png)

### <a name="add-a-requirement-to-the-deployment-type"></a>배포 유형에 요구 사항 추가

 요구 사항은 장치에 응용 프로그램을 설치하기 전에 충족해야 하는 조건을 지정합니다. 기본 제공 요구 사항에서 선택하거나 직접 만들 수 있습니다. 예를 들어 설치 파일의 대상 프로세서 아키텍처에 따라 Windows 10 **x86** 또는 **x64**에서 실행되는 PC에만 응용 프로그램을 설치하는 요구 사항을 추가할 수 있습니다. 이 예제에서는 Windows 10 **x86**을 지정합니다.

1. 방금 연 배포 유형 속성 페이지에서 **요구 사항** 탭을 클릭합니다.

2. **추가**를 클릭하여 **요구 사항 만들기** 대화 상자를 엽니다.

    ![요구 사항 만들기](./media/edge-ent-deployment-sccm/edge-ent-create-app-req-3.png)

3. **요구 사항 만들기** 대화 상자에서 다음 정보를 지정합니다.

    - **범주**: **장치**  

    - **조건**: **운영 체제**  

    - **규칙 유형**: **값**  

    - **연산자**: **다음 중 하나**  

    - 운영 체제 목록에서 **Windows 10** > **모든 Windows 10(32비트)** 를 선택합니다.  

    완료되면 대화 상자가 다음 스크린샷 예와 같이 표시됩니다.

    ![요구 사항 추가](./media/edge-ent-deployment-sccm/edge-ent-create-app-req-4.png)

4. **확인**을 클릭하여 열려 있는 각 속성 페이지를 닫고 Configuration Manager 콘솔의 **응용 프로그램** 목록으로 돌아갑니다.  

## <a name="add-the-application-content-to-a-distribution-point"></a>배포 지점에 응용 프로그램 콘텐츠 추가  

PC에 업데이트된 응용 프로그램을 배포하려면 응용 프로그램 콘텐츠가 배포 지점에 복사되었는지 확인합니다. PC는 배포 지점에 액세스하여 응용 프로그램을 설치합니다.  

>[!TIP]
>Configuration Manager의 배포 지점 및 콘텐츠 관리에 대한 자세한 내용은 [System Center Configuration Manager의 콘텐츠 배포 및 관리](/sccm/core/servers/deploy/configure/deploy-and-manage-content)를 참조하세요.  

1. Configuration Manager 콘솔에서 **소프트웨어 라이브러리**를 클릭합니다.  

2. **소프트웨어 라이브러리** 작업 영역에서 **응용 프로그램**을 확장합니다. 응용 프로그램 목록에서 만든 응용 프로그램을 선택합니다.

3. **홈** 탭의 **배포** 그룹에서 **콘텐츠 배포**를 클릭합니다.  

4. **콘텐츠 배포 마법사**의 **일반** 페이지에서 응용 프로그램 이름이 올바른지 확인하고 **다음**을 클릭합니다.  

5. **콘텐츠** 페이지에서 배포 지점에 복사할 정보를 검토하고 **다음**을 클릭합니다.  

6. **콘텐츠 대상** 페이지에서 **추가**를 클릭하여 응용 프로그램 콘텐츠를 설치할 컬렉션, 배포 지점 또는 배포 지점 그룹을 하나 이상 선택합니다.

7. 마법사를 완료합니다.

**배포 상태** > **콘텐츠 상태**에서 응용 프로그램 콘텐츠가 **모니터링** 작업 영역에서 배포 지점으로 성공적으로 복사되었는지 확인할 수 있습니다.  

## <a name="deploy-the-application"></a>응용 프로그램 배포  

그런 다음 응용 프로그램을 계층 구조의 장치 컬렉션에 배포합니다. 이 예제에서는 응용 프로그램을 **모든 시스템** 장치 컬렉션에 배포합니다.  

>[!TIP]
>앞서 선택한 요구 사항 때문에 지정된 프로세서 아키텍처의 Windows 10 컴퓨터만 응용 프로그램을 설치할 수 있습니다.  

1. Configuration Manager 콘솔에서 **소프트웨어 라이브러리** > **응용 프로그램 관리** > **응용 프로그램**을 클릭합니다.

2. 응용 프로그램 목록에서 앞서 만든 응용 프로그램을 선택합니다. 그런 다음 **홈** 탭의 **배포** 그룹에서 **배포**를 클릭하거나 응용 프로그램을 마우스 오른쪽 단추로 클릭하고 **배포**를 선택합니다.

    ![응용 프로그램 배포](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-1.png)

3. **소프트웨어 배포 마법사**의 **일반** 페이지에서 **찾아보기**를 클릭하여 응용 프로그램을 배포할 장치 컬렉션을 선택합니다.

    ![설치 파일 찾기](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-2.png)

4. **콘텐츠** 페이지에서 PC가 응용 프로그램을 설치하는 데 사용할 배포 지점이 선택되어 있는지 확인합니다.

    ![배포 지점 지정](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-6.png)

5. **배포 설정** 페이지에서 배포 작업이 **설치**로 설정되어 있고 배포 목적이 **필수**로 설정되어 있는지 확인합니다.

    ![배포 설정 구성](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-8.png)

    >[!TIP]
    >배포 목적을 **필수**로 설정하여 설정된 요구 사항을 충족하는 PC에 해당 응용 프로그램이 설치되도록 합니다. 이 값을 **사용 가능**으로 설정하면 사용자가 소프트웨어 센터에서 요청할 경우 응용 프로그램을 설치할 수 있습니다.  

6. **예약** 페이지에서 응용 프로그램을 설치할 시기를 구성할 수 있습니다. 이 예제에서는 **사용 가능 시간 후 가능한 한 빨리**를 선택합니다.

    ![배포 예약](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-9.png)

7. **사용자 환경** 페이지에서 원하는 값을 선택하고 **다음**을 클릭합니다.

    ![사용자 환경 지정](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-10.png)

8. 원하는 경고 옵션을 지정하고 **다음**을 클릭합니다.

    ![경고 설정 지정](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-11.png)

9. 마법사를 완료합니다.

다음 **응용 프로그램 모니터링** 섹션에 있는 정보를 사용하여 응용 프로그램 배포의 상태를 확인합니다.  

## <a name="monitor-the-application"></a>응용 프로그램 모니터링

 이 섹션에서는 방금 배포한 응용 프로그램의 배포 상태를 간략히 살펴봅니다.  

### <a name="to-review-the-deployment-status"></a>배포 상태를 검토하려면  

1. Configuration Manager 콘솔에서 **모니터링** > **배포**를 클릭합니다.  

2. 배포 목록에서 응용 프로그램을 선택합니다.

    ![배포 모니터링](./media/edge-ent-deployment-sccm/edge-ent-monitor-deployment.png)

3. **홈** 탭의 **배포** 그룹에서 **상태 보기**를 클릭합니다.  

4. 다음 탭 중 하나를 선택하여 응용 프로그램 배포에 대한 상태 업데이트를 자세히 확인합니다.  

    - **성공**: 응용 프로그램이 표시된 PC에 설치되었습니다.  

    - **진행 중**: 응용 프로그램 설치가 아직 끝나지 않았습니다.  

    - **오류**: 표시된 PC에 응용 프로그램을 설치하는 동안 오류가 발생했습니다. 오류에 대한 자세한 내용도 표시됩니다.  

    - **요구 사항에 맞지 않음**: 표시된 장치에서 사용자가 구성한 요구 사항에 맞지 않아 설치를 시도하지 않았습니다(이 예제에서는 Windows 10에서 실행되지 않기 때문).

    - **알 수 없음**: Configuration Manager에서 배포 상태를 보고할 수 없습니다. 나중에 다시 확인하세요.  

    >[!TIP]
    >응용 프로그램 배포를 모니터링하는 방법에는 여러 가지가 있습니다. 자세한 내용은 [System Center Configuration Manager 콘솔에서 응용 프로그램 모니터링](/sccm/apps/deploy-use/monitor-applications-from-the-console)을 참조하세요.  

## <a name="end-user-experience"></a>최종 사용자 환경  

Configuration Manager에서 관리되고 지정된 프로세서 아키텍처의 Windows 10을 실행 중인 PC가 있는 사용자에게는 Microsoft Edge Dev 응용 프로그램을 설치해야 한다는 메시지가 표시됩니다. 이 설치 옵션을 수락하면 응용 프로그램이 설치됩니다.  

## <a name="see-also"></a>기타 참조

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [System Center Configuration Manager를 사용하여 응용 프로그램 만들기 및 배포](/sccm/apps/get-started/create-and-deploy-an-application)