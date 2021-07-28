---
title: 자체 호스트 Microsoft Edge 확장
ms.author: aspoddar
author: AndreaLBarr
manager: balajek
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 엔터프라이즈에서 Microsoft Edge 확장을 패키지하고 자체 호스팅하는 방법을 알아봅니다.
ms.openlocfilehash: 8b0e9ed346848f7ee9330c51f6a1c9274df89371
ms.sourcegitcommit: 9088e839e82d80c72460586e9af0610c6ca71b83
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2021
ms.locfileid: "11676115"
---
# <a name="self-host-microsoft-edge-extensions"></a>자체 호스트 Microsoft Edge 확장

이 문서에서는 자체 웹 사이트에서 호스트할 확장을 패키징하기 위한 기본 지침을 제공합니다. 또한 조직의 장치 및 사용자에게 확장을 배포하는 방법에 대한 지침도 포함되어 있습니다.

## <a name="prerequisites"></a>필수 구성 요소

자체 확장을 자체 호스트하려면 확장 및 해당 매니페스트 파일에 대한 자체 웹 호스팅 서비스를 제공해야 합니다.

 다음 단계에서는 확장을 이미 만들었고, XML 파일 작업 경험이 있고, 그룹 정책 구성에 대한 실무 지식이 있고, Windows 레지스트리를 사용하는 방법을 알고 있다고 가정합니다.

## <a name="publish-an-extension"></a>확장 게시

확장을 게시하기 전에 CRX(Chrome 확장명) 파일로 압축해야 합니다. 다음 단계를 지침으로 사용하여 확장을 CRX 파일로 압축합니다.

1. Microsoft Edge 주소 표시줄에서 *edge://extensions*로 이동하여 **개발자 모드**를 사용하도록 설정(아직 사용하도록 설정되지 않은 경우)합니다.
2. **설치된 확장**에서 **팩 확장**을 클릭하여 CRX 파일을 만듭니다.
3. **팩 확장** 대화 상자를 사용하여 확장 원본이 있는 디렉터리를 찾습니다. 디렉터리를 선택한 다음 **팩 확장**을 클릭합니다.  이렇게 하면 PEM 파일과 함께 CRX 파일이 생성됩니다. 확장에 버전을 업데이트하는 데 필요하므로 PEM 파일을 저장합니다. 다음 스크린샷은 확장의 루트 디렉터리를 찾기 위한 **팩 확장** 대화 상자를 보여줍니다.

   :::image type="content" source="media/microsoft-edge-manage-extensions-webstore/manage-extensions-pack-dialog.png" alt-text="확장의 소스 코드를 찾기 위한 팩 확장 대화 상자입니다.":::

   > [!IMPORTANT]
   > PEM 파일은 확장의 키이며 향후 업데이트에 필요하므로 안전한 위치에 저장합니다.

4. CRX 파일을 확장 창으로 끌어서 로드해야 합니다.
5. 확장을 테스트하고 ID 필드(CRX ID) 및 버전 번호를 기록해 둡니다. 나중에 이 정보가 필요합니다. 다음 스크린샷은 CRX ID가 있는 테스트 확장을 보여줍니다.

   :::image type="content" source="media/microsoft-edge-manage-extensions-webstore/manage-extensions-test-extension.png" alt-text="CRX ID를 보여주는 확장 예제":::

6. CRX 파일을 호스트에 업로드하고 다운로드할 위치의 URL을 확인합니다. 이 정보는 XML 매니페스트 파일에 필요합니다.
7. 앱/확장 ID, 다운로드 URL 및 버전을 사용하여 매니페스트 XML 파일을 만들려면 다음 필드를 정의합니다.  

   - **앱 ID** - 5단계의 확장 ID
   - **코드베이스** - 6단계에서 CRX 파일의 다운로드 위치
   - **버전** - 확장 매니페스트에 지정된 버전과 일치해야 하는 앱/확장 버전입니다.

   다음 코드 조각은 XML 매니페스트 파일의 예를 보여줍니다.

   ```xml
   <?xml version='1.0' encoding='UTF-8'?> 
   <gupdate xmlns='http://www.google.com/update2/response' protocol='2.0'> 
     <app appid='ekilpdeokbpjmminmhfcgkncmmohmfeb'> 
     <updatecheck codebase='https://app.somecompany.com/extensionfolder/helloworld.crx' version='1.0' /> 
     </app> 
   </gupdate> 
   ```

   자세한 내용은 [Microsoft Edge에서 자동 업데이트 확장 - Microsoft Edge Development](/microsoft-edge/extensions-chromium/enterprise/auto-update)를 참조하세요.

8. 완료된 XML 파일을 다운로드할 수 있는 위치에 업로드하고 URL을 확인합니다. 이 URL은 그룹 정책을 사용하여 확장을 설치할 때 필요합니다. [개인적으로 호스팅된 확장 배포](#distribute-a-privately-hosted-extension)를 참조합니다.

   > [!IMPORTANT]
   > 확장의 호스팅 위치에는 인증이 필요하지 않습니다. 사용 가능한 모든 위치에서 사용자 장치로 액세스할 수 있어야 합니다.

## <a name="publish-updates-to-an-extension"></a>확장에 업데이트 게시

업데이트된 확장을 변경하고 테스트한 후 게시할 수 있습니다. 다음 단계를 지침으로 사용하여 업데이트를 게시합니다.

1. 다음 구문을 사용하여 확장 manifest.JSON 파일의 버전 번호를 더 높은 숫자로 변경합니다. `"version":"versionString"`. "version":"1.0"인 경우 "version":"1.1" 또는 "1.0"보다 높은 숫자로 업데이트할 수 있습니다.
2. 이전 단계에서 매니페스트 파일에 넣은 번호와 일치하도록 XML 파일의 "버전" `<updatecheck>`을(를) 업데이트합니다. 예를 들어:<br>`<updatecheck codebase='https://app.somecompany.com/extensionfolder/helloworld.crx' version='1.1' />`
3. 새 변경 내용을 포함하는 CRX 파일을 만듭니다. *edge://extensions*로 이동하여 **개발자 모드**를 사용하도록 설정합니다.
4. **팩 확장**을 클릭하고 확장 원본의 디렉터리로 이동합니다.

   > [!IMPORTANT]
   > CRX 파일을 처음 만들었을 때 생성 및 저장한 것과 동일한 PEM 파일을 사용합니다. 동일한 PEM 파일을 사용하지 않는 경우 확장의 앱 ID가 변경되어 업데이트가 새 확장명으로 처리됩니다.

5. CRX 파일을 확장 창으로 끌어서 놓고 로드되는지 확인합니다. 이 작업 후에 확장을 사용할 수 없습니다. 확장의 CRX ID를 ExtensionInstallAllowList 정책에 추가하도록 설정하려면 
6. 업데이트된 확장을 테스트합니다.
7. 이전 CRX 파일 및 XML 파일을 업데이트된 확장명의 새로운 파일로 바꿉니다.

확장의 변경 내용은 다음 정책 동기화 주기 중에 선택됩니다. 확장 업데이트에 대한 자세한 내용은 [URL 업데이트](/microsoft-edge/extensions-chromium/enterprise/auto-update#update-url) 및 [매니페스트 업데이트](/microsoft-edge/extensions-chromium/enterprise/auto-update#updated-manifest)를 참조하세요.

## <a name="distribute-a-privately-hosted-extension"></a>개인적으로 호스팅된 확장 배포

CRX 파일이 호스트되는 위치의 링크를 공유할 수 있으며, 사용자가 브라우저에 URL을 입력하는 즉시 확장이 다운로드되고 설치됩니다. 사용자는 edge://extensions 페이지에서 확장을 사용하도록 설정할 수 있습니다. 사용자가 자체 호스트된 확장을 설치할 수 있도록 허용하려면 [ExtensionInstallAllowList](/deployedge/microsoft-edge-policies#extensioninstallallowlist) 정책에 확장 CRX ID를 추가하고 CRX 파일이 호스팅되는 위치의 URL을 [ExtensionInstallSources](/deployedge/microsoft-edge-policies#extensioninstallsources) 정책에 추가해야 합니다.

또는 그룹 정책 [ExtensionInstallForceList](/deployedge/microsoft-edge-manage-extensions-policies#force-install-an-extension)를 사용하여 사용자 장치에 확장을 강제 설치할 수 있습니다.

선택한 사용자, 장치 또는 둘 다에 이러한 정책을 적용할 수 있습니다. 정책 업데이트는 즉각적이지 않으며 정책 설정을 적용하는 데 시간이 걸립니다.

## <a name="see-also"></a>참고 항목

- [엔터프라이즈에서 Microsoft Edge 확장 관리](microsoft-edge-manage-extensions.md)
- [그룹 정책을 사용하여 Microsoft Edge 확장 관리](microsoft-edge-manage-extensions-policies.md)
- [ExtensionSettings 정책에 대한 자세한 가이드](microsoft-edge-manage-extensions-ref-guide.md)
- [Microsoft Edge 확장에 대한 FAQ](microsoft-edge-manage-extensions-faq.md)
- [Microsoft Edge Enterprise 방문 페이지](https://aka.ms/EdgeEnterprise)
