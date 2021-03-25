---
title: Microsoft Edge 레거시 Microsoft Edge 정책에 매핑
ms.author: brianalt
author: brianalt
manager: srugh
ms.date: 02/10/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 레거시 Microsoft Edge 정책에 매핑
ms.openlocfilehash: f0ce58f3876bf9f02691d7d6bf2a7c7d1944fd24
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "11448002"
---
# <a name="microsoft-edge-legacy-to-microsoft-edge-policy-mapping"></a>Microsoft Edge 레거시 Microsoft Edge 정책에 매핑

이 문서에서는 Microsoft Edge 레거시(버전 45 이하) 그룹 정책(GP) 및 MDM(모바일 장치 관리) 설정을 관련 Microsoft Edge 버전 80 정책에 매핑합니다. Google Chrome 정책의 경우 [Google Chrome Microsoft Edge 정책에 매핑](microsoft-edge-policy-map-chrome-to-newedge.md) 문서를 참조하세요.

> [!NOTE]
> 아래 제공되는 매핑은 Microsoft Edge 버전 80의 초기 배포에 도움을 주기 위해 제공됩니다. 최신 정책의 확정된 목록은 다음을 참조하세요.
> - [브라우저 정책 참조](microsoft-edge-policies.md)
> - [업데이트 정책 참조](microsoft-edge-update-policies.md)

## <a name="microsoft-edge-legacy-to-microsoft-edge-policy-map"></a>Microsoft Edge 레거시에서 Microsoft Edge로 정책 매핑

|Microsoft Edge 레거시 GP|Microsoft Edge 레거시 MDM|Microsoft Edge 정책 <br> 및 GP 이름|
|-|-|-|
|[공유 책 폴더 허용](/microsoft-edge/deploy/available-policies#allow-a-shared-books-folder)|[UseSharedFolderForBooks](/windows/client-management/mdm/policy-csp-browser#browser-usesharedfolderforbooks)|해당 없음|
|[주소 표시줄 드롭다운 목록 제안 허용](/microsoft-edge/deploy/available-policies#allow-address-bar-drop-down-list-suggestions)|[AllowAddressBarDropdown](/windows/client-management/mdm/policy-csp-browser#browser-allowaddressbardropdown)|[SearchSuggestEnabled](./microsoft-edge-policies.md#searchsuggestenabled) <br> 검색 제안 허용|
|[Adobe Flash 허용](/microsoft-edge/deploy/available-policies#allow-adobe-flash)|[AllowFlash](/windows/client-management/mdm/policy-csp-browser#browser-allowflash)|[DefaultPluginsSetting](./microsoft-edge-policies.md#defaultpluginssetting) <br> 기본 Adobe Flash 설정|
|[종료 시 검색 데이터 지우기 허용](/microsoft-edge/deploy/available-policies#allow-clearing-browsing-data-on-exit)|[ClearBrowsingDataOnExit](/windows/client-management/mdm/policy-csp-browser#browser-clearbrowsingdataonexit)|[ClearBrowsingDataOnExit](./microsoft-edge-policies.md#clearbrowsingdataonexit) <br> Microsoft Edge가 닫힐 때 데이터 검색 지우기|
|[책 라이브러리에 대한 구성 업데이트 허용](/microsoft-edge/deploy/available-policies#allow-configuration-updates-for-the-books-library)|[AllowConfigurationUpdateForBooksLibrary](/windows/client-management/mdm/policy-csp-browser#browser-allowconfigurationupdateforbookslibrary)|해당 없음|
|[Cortana 허용](/microsoft-edge/deploy/available-policies#allow-cortana)|[AllowCortana](/windows/client-management/mdm/policy-csp-browser#browser-allowcortana)|해당 없음|
|[개발자 도구 허용](/microsoft-edge/deploy/available-policies#allow-developer-tools)|[AllowDeveloperTools](/windows/client-management/mdm/policy-csp-browser#browser-allowdevelopertools)|[DeveloperToolsAvailability](./microsoft-edge-policies.md#developertoolsavailability) <br> 개발자 도구를 사용할 수 있는 위치 제어|
|[책 탭에 대한 확장된 원격 분석 허용](/microsoft-edge/deploy/available-policies#allow-extended-telemetry-for-the-books-tab)|[EnableExtendedBooksTelemetry](/windows/client-management/mdm/policy-csp-browser#browser-enableextendedbookstelemetry)|해당 없음|
|[확장 허용](/microsoft-edge/deploy/available-policies#allow-extensions)|[AllowExtensions](/windows/client-management/mdm/policy-csp-browser#browser-allowextensions)|[ExtensionInstallBlockList](./microsoft-edge-policies.md#extensioninstallblocklist) <br> 설치할 수 없는 확장 제어 <br/><br/>_모든 확장을 차단하려면 "*"를 사용합니다._|
|[전체 화면 모드 허용](/microsoft-edge/deploy/group-policies/browser-settings-management-gp#allow-fullscreen-mode)|[AllowFullscreen](/windows/client-management/mdm/policy-csp-browser#browser-allowfullscreen)|[FullscreenAllowed](./microsoft-edge-policies.md#fullscreenallowed) <br> 전체 화면 모드 허용|
|[Microsoft 호환성 목록 허용](/microsoft-edge/deploy/available-policies#allow-microsoft-compatibility-list)|[AllowMicrosoftCompatibilityList](/windows/client-management/mdm/policy-csp-browser#browser-allowmicrosoftcompatibilitylist)|해당 없음|
|[Windows 시작 시, 시스템이 유휴 상태일 때 및 Microsoft Edge가 닫힐 때마다 Microsoft Edge가 사전 시작되도록 허용](/microsoft-edge/deploy/group-policies/prelaunch-preload-gp#allow-microsoft-edge-to-load-the-start-and-new-tab-page-at-windows-startup-and-each-time-microsoft-edge-is-closed)|[AllowPrelaunch](/windows/client-management/mdm/policy-csp-browser#browser-allowprelaunch)|해당 없음|
|[Windows 시작 및 Microsoft Edge가 닫힐 때마다 Microsoft Edge가 시작 및 새 탭 페이지를 시작하고 로드하도록 허용](/microsoft-edge/deploy/group-policies/prelaunch-preload-gp#allow-microsoft-edge-to-load-the-start-and-new-tab-page-at-windows-startup-and-each-time-microsoft-edge-is-closed)|[AllowTabPreloading](/windows/client-management/mdm/policy-csp-browser#browser-allowtabpreloading)|[BackgroundModeEnabled](./microsoft-edge-policies.md#backgroundmodeenabled) <br> Microsoft Edge가 닫힌 후 백그라운드 앱 계속 실행|
|[인쇄 허용](/microsoft-edge/deploy/group-policies/browser-settings-management-gp#allow-printing)|[AllowPrinting](/windows/client-management/mdm/policy-csp-browser#browser-allowprinting)|[PrintingEnabled](./microsoft-edge-policies.md#printingenabled) <br> 인쇄 사용|
|[기록 저장 허용](/microsoft-edge/deploy/group-policies/browser-settings-management-gp#allow-saving-history)|[AllowSavingHistory](/windows/client-management/mdm/policy-csp-browser#browser-allowsavinghistory)|[SavingBrowserHistoryDisabled](./microsoft-edge-policies.md#savingbrowserhistorydisabled) <br> 브라우저 기록 저장 사용 안 함|
|[검색 엔진 사용자 지정 허용](/microsoft-edge/deploy/available-policies#allow-search-engine-customization)|[AllowSearchEngineCustomization](/windows/client-management/mdm/policy-csp-browser#browser-allowsearchenginecustomization)|[기본 검색 공급자 정책을 참조하세요.](./microsoft-edge-policies.md#default-search-provider)|
|[확장의 테스트용으로 로드 허용](/microsoft-edge/deploy/group-policies/extensions-management-gp#allow-sideloading-of-extensions)|[AllowSideloadingExtensions](/windows/client-management/mdm/policy-csp-browser#browser-allowsideloadingextensions)|[ExtensionInstallBlocklist](./microsoft-edge-policies.md#extensioninstallblocklist)<br/>설치할 수 없는 확장 제어<br/>또는 [DeveloperToolsAvailability](./microsoft-edge-policies.md#developertoolsavailability)<br/>개발자 도구를 사용할 수 있는 위치 제어|
|[새 탭 페이지에서 웹 콘텐츠 허용](/microsoft-edge/deploy/available-policies#allow-web-content-on-new-tab-page)|[AllowWebContentOnNewTabPage](/windows/client-management/mdm/policy-csp-browser#browser-allowwebcontentonnewtabpage)|[NewTabPageLocation](./microsoft-edge-policies.md#newtabpagelocation) <br> 새 탭 페이지 URL 구성|
|[Microsoft Edge에 책 라이브러리 항상 표시](/microsoft-edge/deploy/available-policies#always-show-the-books-library-in-microsoft-edge)|[AlwaysEnableBooksLibrary](/windows/client-management/mdm/policy-csp-browser#browser-alwaysenablebookslibrary)|해당 없음|
|[추가 검색 엔진 구성](/microsoft-edge/deploy/available-policies#configure-additional-search-engines)|[ConfigureAdditionalSearchEngines](/windows/client-management/mdm/policy-csp-browser#browser-configureadditionalsearchengines)|[기본 검색 공급자 정책을 참조하세요.](./microsoft-edge-policies.md#default-search-provider)|
|[자동 채우기 구성](/microsoft-edge/deploy/available-policies#configure-autofill)|[AllowAutofill](/windows/client-management/mdm/policy-csp-browser#browser-allowautofill)|[AutofillAddressEnabled](./microsoft-edge-policies.md#autofilladdressenabled) <br> 주소에 자동 채우기 사용|
|[쿠키 구성](/microsoft-edge/deploy/group-policies/security-privacy-management-gp#configure-cookies)|[AllowCookies](/windows/client-management/mdm/policy-csp-browser#browser-allowcookies)|[DefaultCookiesSetting](./microsoft-edge-policies.md#defaultcookiessetting) <br> 쿠키 구성|
|[Do Not Track 구성](/microsoft-edge/deploy/available-policies#configure-do-not-track)|[AllowDoNotTrack](/windows/client-management/mdm/policy-csp-browser#browser-allowdonottrack)|[ConfigureDoNotTrack](./microsoft-edge-policies.md#configuredonottrack) <br> Do Not Track 구성|
|[즐겨찾기 모음 구성](/microsoft-edge/deploy/group-policies/favorites-management-gp#configure-favorites-bar)|[ConfigureFavoritesBar](/windows/client-management/mdm/policy-csp-browser#browser-configurefavoritesbar)|[FavoritesBarEnabled](./microsoft-edge-policies.md#favoritesbarenabled) <br> 즐겨찾기 모음 사용|
|[홈 단추 구성](/microsoft-edge/deploy/group-policies/home-button-gp#configure-home-button)|[ConfigureHomeButton](/windows/client-management/mdm/policy-csp-browser#browser-configurehomebutton)|[HomepageIsNewTabPage](./microsoft-edge-policies.md#homepageisnewtabpage) <br> 새 탭 페이지를 홈 페이지로 설정|
|[키오스크 모드 구성](/windows/client-management/mdm/policy-csp-browser#browser-configurekioskmode)|[ConfigureKioskMode](/windows/client-management/mdm/policy-csp-browser#browser-configurekioskmode)|해당 없음|
|[유휴 시간 초과 후 키오스크 재설정 구성](/windows/client-management/mdm/policy-csp-browser#browser-configurekioskresetafteridletimeout)|[ConfigureKioskResetAfterIdleTimeout](/windows/client-management/mdm/policy-csp-browser#browser-configurekioskresetafteridletimeout)|해당 없음|
|[Microsoft Edge 열기 구성](/microsoft-edge/deploy/group-policies/start-pages-gp#configure-open-microsoft-edge-with)|[ConfigureOpenEdgeWith](/windows/client-management/mdm/policy-csp-browser#browser-configureopenedgewith)|[RestoreOnStartup](./microsoft-edge-policies.md#restoreonstartup) <br> 시작할 때 수행하는 작업|
|[암호 관리자 구성](/microsoft-edge/deploy/available-policies#configure-password-manager)|[AllowPasswordManager](/windows/client-management/mdm/policy-csp-browser#browser-allowpasswordmanager)|[PasswordManagerEnabled](./microsoft-edge-policies.md#passwordmanagerenabled) <br> 암호 관리자에 암호 저장 사용|
|[팝업 차단 구성](/microsoft-edge/deploy/available-policies#configure-pop-up-blocker)|[AllowPopups](/windows/client-management/mdm/policy-csp-browser#browser-allowpopups)|[DefaultPopupsSetting](./microsoft-edge-policies.md#defaultpopupssetting) <br> 기본 팝업 창 설정|
|[Configure search suggestions in Address bar(주소 표시줄에서 검색 제안 구성)](/microsoft-edge/deploy/available-policies#configure-search-suggestions-in-address-bar)|[AllowSearchSuggestionsinAddressBar](/windows/client-management/mdm/policy-csp-browser#browser-allowsearchsuggestionsinaddressbar)|[기본 검색 공급자 정책을 참조하세요.](./microsoft-edge-policies.md#default-search-provider)|
|[시작 페이지 구성](/microsoft-edge/deploy/available-policies#configure-start-pages)|[HomePages](/windows/client-management/mdm/policy-csp-browser#browser-homepages)|[RestoreOnStartupURLS](./microsoft-edge-policies.md#restoreonstartupurls) <br> 브라우저가 시작될 때 열리는 사이트|
|[Adobe Flash 간편 실행 설정 구성](/microsoft-edge/deploy/available-policies#configure-the-adobe-flash-click-to-run-setting)|[AllowFlashClickToRun](/windows/client-management/mdm/policy-csp-browser#browser-allowflashclicktorun)|[DefaultPluginsSetting](./microsoft-edge-policies.md#defaultpluginssetting) <br> 기본 Adobe Flash 설정|
|[엔터프라이즈 모드 사이트 목록 구성](/microsoft-edge/deploy/available-policies#configure-the-enterprise-mode-site-list)|[EnterpriseModeSiteList](/windows/client-management/mdm/policy-csp-browser#browser-enterprisemodesitelist)|[InternetExplorerIntegrationSiteList](./microsoft-edge-policies.md#internetexplorerintegrationsitelist) <br> 엔터프라이즈 모드 사이트 목록 구성|
|[Windows Defender SmartScreen 구성](/microsoft-edge/deploy/available-policies#configure-windows-defender-smartscreen)|[AllowSmartScreen](/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen)|[SmartScreenEnabled](./microsoft-edge-policies.md#smartscreenenabled) <br> Microsoft Defender SmartScreen 구성|
|[시작 페이지 잠금 기능을 사용 안 함](/microsoft-edge/deploy/available-policies#disable-lockdown-of-start-pages)|[DisableLockdownOfStartPages](/windows/client-management/mdm/policy-csp-browser#browser-disablelockdownofstartpages)|[RestoreOnStartupURLS](./microsoft-edge-policies.md#restoreonstartupurls) <br> 브라우저가 시작될 때 열리는 사이트(권장 버전)|
|[동기화 안 함](/microsoft-edge/deploy/available-policies#do-not-sync)|[AllowSyncMySettings](/windows/client-management/mdm/policy-csp-browser#browser-allowsyncmysettings)|[SyncDisabled](./microsoft-edge-policies.md#syncdisabled) <br> Microsoft 동기화 서비스를 사용하여 데이터 동기화를 사용하지 않도록 설정|
|[브라우저 설정 동기화 안 함](/microsoft-edge/deploy/available-policies#do-not-sync-browser-settings)|[DoNotSyncBrowserSettings](/windows/client-management/mdm/policy-csp-experience#experience-donotsyncbrowsersetting)|해당 없음|
|[Internet Explorer와 Microsoft Edge 간에 즐겨찾기 동기화 유지](/microsoft-edge/deploy/available-policies#keep-favorites-in-sync-between-internet-explorer-and-microsoft-edge)|[SyncFavoritesBetweenIEAndMicrosoftEdge](/windows/client-management/mdm/policy-csp-browser#browser-syncfavoritesbetweenieandmicrosoftedge)|해당 없음|
|[about:flags 페이지에 대한 액세스 방지](/microsoft-edge/deploy/available-policies#prevent-access-to-the-aboutflags-page)|[PreventAccessToAboutFlagsInMicrosoftEdge](/windows/client-management/mdm/policy-csp-browser#browser-preventaccesstoaboutflagsinmicrosoftedge)|[URLBlocklist](./microsoft-edge-policies.md#urlblocklist) <br> URL 목록에 대한 액세스 차단 <br/><br/>_"Edge://flags"로 설정 예기치 않은 결과가 발생할 수 있으므로이 정책을 사용하여 edge://* 페이지를 차단하지 않는 것이 좋습니다._|
|[파일에 대한 Windows Defender SmartScreen 프롬프트 무시 방지](/microsoft-edge/deploy/available-policies#prevent-bypassing-windows-defender-smartscreen-prompts-for-files)|[PreventSmartScreenPromptOverrideForFiles](/windows/client-management/mdm/policy-csp-browser#browser-preventsmartscreenpromptoverrideforfiles)|[PreventSmartScreenPromptOverrideForFiles](./microsoft-edge-policies.md#preventsmartscreenpromptoverrideforfiles) <br> 다운로드에 대한 Microsoft Defender SmartScreen 경고 무시 방지|
|[사이트에 대한 Windows Defender SmartScreen 프롬프트 무시 방지](/microsoft-edge/deploy/available-policies#prevent-bypassing-windows-defender-smartscreen-prompts-for-sites)|[PreventSmartScreenPromptOverride](/windows/client-management/mdm/policy-csp-browser#browser-preventsmartscreenpromptoverride)|[PreventSmartScreenPromptOverride](./microsoft-edge-policies.md#preventsmartscreenpromptoverride) <br> 사이트에 대한 Microsoft Defender SmartScreen 프롬프트 무시 방지|
|[인증서 오류 재정의 방지](/microsoft-edge/deploy/group-policies/security-privacy-management-gp#prevent-certificate-error-overrides)|[PreventCertErrorOverrides](/windows/client-management/mdm/policy-csp-browser#browser-preventcerterroroverrides)|[SSLErrorOverrideAllowed](./microsoft-edge-policies.md#sslerroroverrideallowed) <br> HTTPS 경고 페이지에서 사용자가 계속할 수 있도록 허용|
|[Microsoft Edge에서 즐겨찾기 변경 금지](/microsoft-edge/deploy/available-policies#prevent-changes-to-favorites-on-microsoft-edge)|[LockdownFavorites](/windows/client-management/mdm/policy-csp-browser#browser-lockdownfavorites)|[EditFavoritesEnabled](./microsoft-edge-policies.md#editfavoritesenabled) <br> 사용자가 즐겨찾기를 편집할 수 있도록 허용|
|[시작 메뉴에 사이트를 고정할 때 Microsoft Edge에서 Live Tile 정보 수집 금지](/microsoft-edge/deploy/available-policies#prevent-microsoft-edge-from-gathering-live-tile-information-when-pinning-a-site-to-start)|[PreventLiveTileDataCollection](/windows/client-management/mdm/policy-csp-browser#browser-preventlivetiledatacollection)|해당 없음|
|[Microsoft Edge에서 첫 실행 웹 페이지 표시 금지](/microsoft-edge/deploy/available-policies#prevent-the-first-run-webpage-from-opening-on-microsoft-edge)|[PreventFirstRunPage](/windows/client-management/mdm/policy-csp-browser#browser-preventfirstrunpage)|[HideFirstRunExperience](./microsoft-edge-policies.md#hidefirstrunexperience) <br> 첫 실행 환경 및 시작 화면을 숨깁니다.|
|[필수 확장 해제 방지](/microsoft-edge/deploy/group-policies/extensions-management-gp#prevent-turning-off-required-extensions)|[PreventTurningOffRequiredExtensions](/windows/client-management/mdm/policy-csp-browser#browser-preventturningoffrequiredextensions)|[ExtensionInstallForcelist](./microsoft-edge-policies.md#extensioninstallforcelist) <br> 설치할 수 없는 확장 제어|
|[사용자가 브라우저 동기화를 설정하지 못하도록 방지](/microsoft-edge/deploy/available-policies#prevent-users-from-turning-on-browser-syncing)|[PreventUsersFromTurningOnBrowserSyncing](/windows/client-management/mdm/policy-csp-experience#experience-preventusersfromturningonbrowsersyncing)|해당 없음|
|[WebRTC에 LocalHost IP 주소를 사용하도록 허용 안 함](/microsoft-edge/deploy/available-policies#prevent-using-localhost-ip-address-for-webrtc)|[PreventUsingLocalHostIPAddressForWebRTC](/windows/client-management/mdm/policy-csp-browser#browser-preventusinglocalhostipaddressforwebrtc)|[WebRtcLocalhostIpHandling](./microsoft-edge-policies.md#webrtclocalhostiphandling) <br> WebRTC에 의한 로컬 IP 주소 노출 제한|
|[즐겨찾기 프로비전](/microsoft-edge/deploy/available-policies#provision-favorites)|[ProvisionFavorites](/windows/client-management/mdm/policy-csp-browser#browser-provisionfavorites)|[ManagedFavorites](./microsoft-edge-policies.md#managedfavorites) <br> 즐겨찾기 구성|
|[Internet Explorer 11에 모든 인트라넷 사이트 보내기](/microsoft-edge/deploy/available-policies#send-all-intranet-sites-to-internet-explorer-11)|[SendIntranetTraffictoInternetExplorer](/windows/client-management/mdm/policy-csp-browser#browser-sendintranettraffictointernetexplorer)|[SendIntranetToInternetExplorer](./microsoft-edge-policies.md#sendintranettointernetexplorer) <br> Internet Explorer에 모든 인트라넷 사이트 보내기|
|[기본 검색 엔진 설정](/microsoft-edge/deploy/available-policies#set-default-search-engine)|[SetDefaultSearchEngine](/windows/client-management/mdm/policy-csp-browser#browser-setdefaultsearchengine)|[기본 검색 공급자 정책을 참조하세요.](./microsoft-edge-policies.md#default-search-provider)|
|[홈 단추 URL 설정](/microsoft-edge/deploy/group-policies/home-button-gp#set-home-button-url)|[SetHomeButtonURL](/windows/client-management/mdm/policy-csp-browser#browser-sethomebuttonurl)|[HomepageLocation](./microsoft-edge-policies.md#homepagelocation) <br> 홈 페이지 URL을 구성합니다.|
|[새 탭 페이지 설정](/microsoft-edge/deploy/group-policies/new-tab-page-settings-gp#set-new-tab-page-url)|[SetNewTabPageURL](/windows/client-management/mdm/policy-csp-browser#browser-setnewtabpageurl)|[NewTabPageLocation](./microsoft-edge-policies.md#newtabpagelocation) <br> 새 탭 페이지 URL 구성|
|[Internet Explorer에서 사이트를 열 때 메시지 표시](/microsoft-edge/deploy/available-policies#show-message-when-opening-sites-in-internet-explorer)|[ShowMessageWhenOpeningSitesInInternetExplorer](/windows/client-management/mdm/policy-csp-browser#browser-showmessagewhenopeningsitesininternetexplorer)|해당 없음|
|[홈 단추 잠금 해제](/microsoft-edge/deploy/group-policies/home-button-gp#unlock-home-button)|[UnlockHomeButton](/windows/client-management/mdm/policy-csp-browser#browser-unlockhomebutton)|[ShowHomeButton ](./microsoft-edge-policies.md#showhomebutton) <br> 도구 모음의 홈 단추 표시(권장 버전)|


## <a name="see-also"></a>참고 항목
- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge 구성](configure-microsoft-edge.md)
-   [브라우저 정책 참조](microsoft-edge-policies.md)