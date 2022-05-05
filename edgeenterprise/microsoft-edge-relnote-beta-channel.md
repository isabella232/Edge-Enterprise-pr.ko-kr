---
title: 베타 채널 용 Microsoft Edge 릴리스 정보
ms.author: leahtu
author: dan-wesley
manager: srugh
ms.date: 04/27/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 베타 채널 용 Microsoft Edge 릴리스 정보
ms.openlocfilehash: 41f9efd48fa9afef215c2fd8e6499b2840ec256c
ms.sourcegitcommit: 592f6e40b13e28af588473b2a75c3ae697e5db2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2022
ms.locfileid: "12505371"
---
# <a name="release-notes-for-microsoft-edge-beta-channel"></a>Microsoft Edge 베타 채널에 대한 릴리스 정보

이 릴리스 정보는 Microsoft Edge 베타 채널에 포함된 새로운 기능 및 비보안 업데이트에 대한 정보를 제공합니다. 이러한 릴리스 정보의 보관된 버전은 [Microsoft Edge Beta 채널의 보관된 릴리스 정보](./microsoft-edge-relnote-archive-beta-channel.md)에서 사용할 수 있습니다.

> [!NOTE]
> Microsoft Edge 웹 플랫폼은 사용자 환경, 보안 및 개인 정보 개선을 위해 지속적으로 진화하고 있습니다. 자세히 알아보려면 [Microsoft Edge에 적용될 사이트 호환성에 영향을 미치는 변경 사항](/microsoft-edge/web-platform/site-impacting-changes)을 참조하세요.

## <a name="version-1010121031-april-27"></a>버전 101.0.1210.31: 4월 27일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-1010121026-april-22"></a>버전 101.0.1210.26: 4월 22일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-1010121019-april-18"></a>버전 101.0.1210.19: 4월 18일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-1010121014-april-12"></a>버전 101.0.1210.14: 4월 12일

다양한 버그와 성능 문제를 해결했습니다.

### <a name="feature-updates"></a>기능 업데이트

- **Enterprise 사이트 목록 관리자의 향상된 기능** 이제 엔터프라이즈 사이트 목록에서 Microsoft Edge Internet Explorer 간에 공유 쿠키를 구성할 수 있습니다. [edge://compat/SiteListManager Enterprise 사이트 목록 관리자](/deployedge/edge-ie-mode-site-list-manager)*에 액세스할* 수 있습니다.

## <a name="version-1010121010-april-8"></a>버전 101.0.1210.10: 4월 8일

### <a name="feature-updates"></a>기능 업데이트

- **기본 프로필을 설정하는 기능입니다.** [EdgeDefaultProfileEnabled](/DeployEdge/microsoft-edge-policies#edgedefaultprofileenabled) 정책을 사용하면 사용된 마지막 프로필이 아닌 브라우저를 열 때 사용할 기본 프로필을 설정할 수 있습니다. 매개 변수를 지정한 경우에는 `--profile-directory` 이 정책을 적용할 수 없습니다.

- **클라이언트 인증서 전환기.** 이 기능은 사용자가 http 인증서 인증이 필요한 사이트를 방문할 때 기억되는 인증서를 지우고 인증서 선택기를 다시 표시할 수 있는 방법을 제공합니다. 이 작업은 Microsoft Edge 수동으로 종료하지 않고 수행할 수 있습니다.

- **즐겨찾기 모음에서 PWA(프로그레시브 Web Apps)를 시작합니다.** PWA 시작 환경의 향상된 기능은 도구 모음에 추가할 수 있는 앱 아이콘으로 시작됩니다.

- **"다른 저장소에서 확장 허용" 설정을 관리합니다.** [ControlDefaultStateOfAllowExtensionFromOtherStoresSettingEnabled](/DeployEdge/microsoft-edge-policies#controldefaultstateofallowextensionfromotherstoressettingenabled) 정책을 사용하여 "다른 저장소에서 확장 허용" 설정의 기본 상태를 제어합니다.

### <a name="policy-updates"></a>정책 업데이트

#### <a name="new-policies"></a>새로운 정책

- [ConfigureKeyboardShortcuts](/DeployEdge/microsoft-edge-policies#configurekeyboardshortcuts) - 바로 가기 키를 사용하지 않도록 설정할 명령 목록 구성
- [ControlDefaultStateOfAllowExtensionFromOtherStoresSettingEnabled](/DeployEdge/microsoft-edge-policies#controldefaultstateofallowextensionfromotherstoressettingenabled) - 다른 저장소 설정에서 확장 허용의 기본 상태 구성
- [EdgeAssetDeliveryServiceEnabled](/DeployEdge/microsoft-edge-policies#edgeassetdeliveryserviceenabled) - 기능이 Asset Delivery Service에서 자산을 다운로드하도록 허용
- [EdgeDefaultProfileEnabled](/DeployEdge/microsoft-edge-policies#edgedefaultprofileenabled) - 기본 프로필 설정 사용
- [InternetExplorerModeEnableSavePageAs](/DeployEdge/microsoft-edge-policies#internetexplorermodeenablesavepageas) - Internet Explorer 모드에서와 같이 저장 페이지 허용
- [KioskSwipeGesturesEnabled](/DeployEdge/microsoft-edge-policies#kioskswipegesturesenabled) - Microsoft Edge 키오스크 모드에서 살짝 밀기 제스처 사용
- [MicrosoftOfficeMenuEnabled](/DeployEdge/microsoft-edge-policies#microsoftofficemenuenabled) - 사용자가 Microsoft Office 메뉴에 액세스할 수 있도록 허용
- [SiteSafetyServicesEnabled](/DeployEdge/microsoft-edge-policies#sitesafetyservicesenabled) - 사용자가 사이트 안전 서비스를 구성할 수 있도록 허용

#### <a name="deprecated-policy"></a>더 이상 사용되지 않는 정책

- [ForceCertificatePromptsOnMultipleMatches](/DeployEdge/microsoft-edge-policies#forcecertificatepromptsonmultiplematches) - "AutoSelectCertificateForUrls"로 구성된 사이트에 대해 인증서 일치가 여러 개 있는 경우 Microsoft Edge 인증서를 자동으로 선택해야 하는지 여부를 구성합니다.

#### <a name="obsoleted-policy"></a>폐기된 정책

- [WebSQLInThirdPartyContextEnabled](/DeployEdge/microsoft-edge-policies#websqlinthirdpartycontextenabled) - 타사 컨텍스트의 WebSQL을 강제로 다시 사용하도록 설정


## <a name="version-1000118527-march-31"></a>버전 100.0.1185.27: 3월 31일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-1000118523-march-28"></a>버전 100.0.1185.23: 3월 28일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-1000118517-march-23"></a>버전 100.0.1185.17: 3월 23일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-1000118512-march-18"></a>버전 100.0.1185.12: 3월 18일

다양한 버그와 성능 문제를 해결했습니다.

### <a name="feature-updates"></a>기능 업데이트

- **Microsoft 365 응용 프로그램 프로토콜 활성화 간소화.** 이제 신뢰할 수 있는 Microsoft 클라우드 저장소 서비스의 Microsoft 365 응용 프로그램 프로토콜 활성화가 SharePoint 하위 도메인 및 Microsoft OneDrive URL을 비롯한 특정 Microsoft 365 응용 프로그램을 직접 시작합니다. 원할 경우 [AutoLaunchProtocolsComponentEnabled](/deployedge/microsoft-edge-policies#autolaunchprotocolscomponentenabled) 및 [AutoLaunchProtocolsFromOrigins](/deployedge/microsoft-edge-policies#autolaunchprotocolsfromorigins) 정책을 사용하여 응용 프로그램 프로토콜 활성화 프롬프트를 사용하도록 설정하고, 경고를 사용하거나 사용하지 않도록 설정하는 다른 응용 프로그램 및 서비스를 정의할 수 있습니다.

## <a name="version-1000118510-march-17"></a>버전 100.0.1185.10: 3월 17일

### <a name="feature-updates"></a>기능 업데이트

- **IE 모드에 대한 클라우드 사이트 목록 관리 환경 개선** Microsoft 365 관리 Center의 사이트 목록에서 Microsoft Edge 및 Internet Explorer for IE 모드 간의 세션 쿠키 공유를 구성할 수 있습니다. **참고:** 제어된 기능 롤아웃입니다. 이 기능이 표시되지 않으면 롤아웃을 계속 진행하면서 다시 확인하세요.

- **Microsoft Outlook 및 파일 탐색기에서 PDF 파일을 미리 봅니다.** 쉽고 풍부한 읽기 전용 미리 보기로 PDF 파일을 볼 수 있습니다.  Outlook 데스크톱 PDF 첨부 파일 또는 파일 탐색기 사용하는 로컬 PDF 파일에 사용할 수 있습니다.  

- **모든 데스크톱 디바이스에 웹앱 동기화가 설치되었습니다.** 애플리케이션으로 설치된 웹 사이트 또는 PWA(프로그레시브 Web Apps)는 로그인하고 동기화를 사용하도록 설정한 모든 데스크톱 디바이스에서 동기화됩니다. 설치할 수 있는 "사용 가능한 앱"으로 표시됩니다. 한 디바이스에서 제거된 앱은 모든 디바이스에서 제거를 동기화합니다.

### <a name="policy-updates"></a>정책 업데이트

#### <a name="new-policies"></a>새로운 정책

- [AdsTransparencyEnabled](/DeployEdge/microsoft-edge-policies#adstransparencyenabled) - 광고 투명도 기능을 사용할 수 있는지 구성
- [DefaultWebHidGuardSetting](/DeployEdge/microsoft-edge-policies#defaultwebhidguardsetting) - WebHID API의 사용 제어
- [HideRestoreDialogEnabled](/DeployEdge/microsoft-edge-policies#hiderestoredialogenabled) - 브라우저 충돌 후 복원 페이지 대화 상자 숨기기
- [PDFSecureMode](/DeployEdge/microsoft-edge-policies#pdfsecuremode) - 기본 PDF 판독기에서 보안 모드 및 인증서 기반 디지털 서명 유효성 검사
- [PromptOnMultipleMatchingCertificates](/DeployEdge/microsoft-edge-policies#promptonmultiplematchingcertificates) - 여러 인증서가 일치하는 경우 인증서를 선택하라는 메시지 표시
- [WebHidAskForUrls](/DeployEdge/microsoft-edge-policies#webhidaskforurls) - 이러한 사이트에서 WebHID API 허용
- [WebHidBlockedForUrls](/DeployEdge/microsoft-edge-policies#webhidblockedforurls) - 이러한 사이트에서 WebHID API 차단

#### <a name="deprecated-policy"></a>더 이상 사용되지 않는 정책

- [BackgroundTemplateListUpdatesEnabled](/DeployEdge/microsoft-edge-policies#backgroundtemplatelistupdatesenabled) - 서식 파일을 사용하는 컬렉션 및 기타 기능에 대해 사용 가능한 서식 파일 목록의 백그라운드 업데이트 사용

#### <a name="obsoleted-policy"></a>폐기된 정책

- [AllowSyncXHRInPageDismissal](/DeployEdge/microsoft-edge-policies#allowsyncxhrinpagedismissal) - 페이지를 해제하는 동안 페이지에서 동기 XHR 요청 전송 허용

## <a name="version-990115039-march-10"></a>버전 99.0.1150.39: 3월 10일

### <a name="feature-updates"></a>기능 업데이트

- **IE 모드에 대한 클라우드 사이트 목록 관리 환경 개선** [InternetExplorerIntegrationCloudUserSitesReporting](/deployedge/microsoft-edge-policies#internetexplorerintegrationcloudusersitesreporting) 및 [InternetExplorerIntegrationCloudNeutralSitesReporting](/deployedge/microsoft-edge-policies#internetexplorerintegrationcloudneutralsitesreporting) 정책을 사용하여 사이트 피드백 보고를 구성하여 엔터프라이즈 사이트 목록의 간격을 식별합니다. Microsoft 365 관리 Center의 Microsoft Edge 사이트 목록 환경에서 사용자의 로컬 사이트 목록 URL 및 잠재적으로 잘못 구성된 중립 사이트 URL을 볼 수 있습니다. 자세한 내용은 [Microsoft 365 관리 센터에서 사이트 피드백 보기를](/deployedge/edge-ie-mode-cloud-site-list-mgmt#view-site-feedback-on-the-microsoft-365-admin-center-1) 참조하세요.  **참고:** 제어된 기능 롤아웃입니다. 이 기능이 표시되지 않으면 롤아웃을 계속 진행하면서 다시 확인하세요.

## <a name="version-990115030-march-2"></a>버전 99.0.1150.30: 3월 2일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-990115025-february-25"></a>버전 99.0.1150.25: 2월 25일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-990115021-february-22"></a>버전 99.0.1150.21: 2월 22일

다양한 버그와 성능 문제를 해결했습니다.

## <a name="version-990115016-february-14"></a>버전 99.0.1150.16: 2월 14일

다양한 버그와 성능 문제를 해결했습니다.

<!--- From Version 99.0.1150.11: February 9 to Version 98.0.1108.27: January 19 --->
<!-- archive from Version 98.0.1108.23: January 14 to Version 97.0.1072.28: December 8 -->
<!--- Version 97.0.1072.21: December 1 to Version 96.0.1054.13: November 5  --->
<!--- archive from Version 96.0.1054.8: November 1 to Version 95.0.1020.14: October 5  --->
<!-- archive from version 95.0.1020.9: September 28 to version 94.0.992.14: September 7 -->
<!-- archive from Version 94.0.992.9: September 2 to Version 92.0.902.40: July 6 -->
<!--Archive from Version 92.0.902.22: June 21 to Version 89.0.774.23: February 8  -->
<!-- Archive from Version 87.0.664.18: October 26 to to version 89.0.774.18: February 3 --->
<!-- Archive from Version 87.0.664.12: October 20 to version 86.0.622.15: September 14 -->
<!--- Archived to version 86.0.622.11: September 9 ---->
<!--- Archived to version 85.0.564.18: July 28 ---->

## <a name="see-also"></a>참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)

