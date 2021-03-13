---
title: Microsoft Edge 브라우저 정책 설명서
ms.author: stmoody
author: dan-wesley
manager: tahills
ms.date: 03/12/2021
audience: ITPro
ms.topic: reference
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
ms.custom: ''
description: Microsoft Edge 브라우저에서 지원하는 모든 정책에 대한 Windows 및 Mac 설명서
ms.openlocfilehash: cecadd38a07c6be0153744657c5bef037bd665c7
ms.sourcegitcommit: 24e26d393e87acb59300bcca6529a9be57c530cf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/13/2021
ms.locfileid: "11408650"
---
# <a name="microsoft-edge---policies"></a>Microsoft Edge - 정책

최신 버전의 Microsoft Edge에는 다음과 같은 정책이 포함되어 있습니다. 이러한 정책을 사용하여 조직에서 Microsoft Edge의 실행 방식을 구성할 수 있습니다.

Microsoft Edge의 업데이트 방법 및 시기를 제어하는 데 사용되는 추가 정책 집합에 대한 자세한 내용은 [Microsoft Edge 업데이트 정책 참조](microsoft-edge-update-policies.md)를 참조하세요.

Microsoft Edge에 대한 권장 보안 구성 기준 설정에 대해 [Microsoft 보안 규정 준수 툴킷](https://www.microsoft.com/download/details.aspx?id=55319)을 다운로드할 수 있습니다. 자세한 내용은 [Microsoft 보안 기준 블로그](https://techcommunity.microsoft.com/t5/microsoft-security-baselines/bg-p/Microsoft-Security-Baselines)를 참조하세요.


> [!NOTE]
> 이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.

## <a name="available-policies"></a>사용 가능한 정책

이 표에서는 이번 릴리스의 Microsoft Edge에서 사용할 수 있는 모든 브라우저 관련 그룹 정책을 보여 줍니다. 특정 정책에 대해 자세히 알아보려면 표의 링크를 사용하세요.

- [Application Guard 설정](#application-guard-settings)
- [캐스트](#cast)
- [콘텐츠 설정](#content-settings)
- [기본 검색 공급자](#default-search-provider)
- [Extensions](#extensions)
- [HTTP 인증](#http-authentication)
- [키오스크 모드 설정](#kiosk-mode-settings)
- [관리 효율성](#manageability)
- [기본 메시지](#native-messaging)
- [암호 관리자 및 보호](#password-manager-and-protection)
- [성능](#performance)
- [인쇄](#printing)
- [프록시 서버](#proxy-server)
- [절전 탭 설정](#sleeping-tabs-settings)
- [SmartScreen 설정](#smartscreen-settings)
- [시작, 홈 페이지 및 새 탭 페이지](#startup-home-page-and-new-tab-page)
- [추가 정보](#additional)


### [*<a name="application-guard-settings"></a>Application Guard 설정*](#application-guard-settings-policies)

|정책 이름|캡션|
|-|-|
|[ApplicationGuardContainerProxy](#applicationguardcontainerproxy)|Application Guard 컨테이너 프록시|
|[ApplicationGuardFavoritesSyncEnabled](#applicationguardfavoritessyncenabled)|응용 프로그램 보호 즐겨찾기 동기화 사용|
### [*<a name="cast"></a>캐스트*](#cast-policies)

|정책 이름|캡션|
|-|-|
|[EnableMediaRouter](#enablemediarouter)|Google Cast 사용|
|[ShowCastIconInToolbar](#showcasticonintoolbar)|도구 모음에 캐스트 아이콘 표시|
### [*<a name="content-settings"></a>콘텐츠 설정*](#content-settings-policies)

|정책 이름|캡션|
|-|-|
|[Autoselectcertificateurl](#autoselectcertificateforurls)|해당 사이트의 클라이언트 인증서를 자동으로 선택|
|[CookiesAllowedForUrls](#cookiesallowedforurls)|특정 사이트에서 쿠키 허용|
|[CookiesBlockedForUrls](#cookiesblockedforurls)|특정 사이트에서 쿠키 차단|
|[CookiesSessionOnlyForUrls](#cookiessessiononlyforurls)|특정 웹 사이트의 쿠키를 현재 세션으로 제한|
|[DefaultCookiesSetting](#defaultcookiessetting)|쿠키 구성|
|[DefaultFileSystemReadGuardSetting](#defaultfilesystemreadguardsetting)|읽기를 위해 파일 시스템 API 사용 제어|
|[DefaultFileSystemWriteGuardSetting](#defaultfilesystemwriteguardsetting)|쓰기를 위해 파일 시스템 API 사용 제어|
|[DefaultGeolocationSetting](#defaultgeolocationsetting)|기본 지리적 위치 설정|
|[DefaultImagesSetting](#defaultimagessetting)|기본 이미지 설정|
|[DefaultInsecureContentSetting](#defaultinsecurecontentsetting)|비보안 콘텐츠 예외를 사용하여 제어|
|[DefaultJavaScriptSetting](#defaultjavascriptsetting)|기본 JavaScript 설정|
|[DefaultNotificationsSetting](#defaultnotificationssetting)|기본 알림 설정|
|[DefaultPluginsSetting](#defaultpluginssetting)|기본 Adobe Flash 설정(obsolete)|
|[DefaultPopupsSetting](#defaultpopupssetting)|기본 팝업 창 설정|
|[DefaultWebBluetoothGuardSetting](#defaultwebbluetoothguardsetting)|웹 블루투스 API의 사용 제어|
|[DefaultWebUsbGuardSetting](#defaultwebusbguardsetting)|WebUSB API의 사용 제어|
|[FileSystemReadAskForUrls](#filesystemreadaskforurls)|해당 사이트에서 파일 시스템 API를 통해 읽기 권한 허용|
|[FileSystemReadBlockedForUrls](#filesystemreadblockedforurls)|해당 사이트에서 파일 시스템 API를 통해 읽기 권한 차단|
|[FileSystemWriteAskForUrls](#filesystemwriteaskforurls)|이 사이트에서 파일 및 디렉터리에 대한 쓰기 액세스 허용|
|[FileSystemWriteBlockedForUrls](#filesystemwriteblockedforurls)|이 사이트에서 파일 및 디렉터리에 대한 쓰기 액세스 차단|
|[ImagesAllowedForUrls](#imagesallowedforurls)|해당 사이트에서 이미지 허용|
|[ImagesBlockedForUrls](#imagesblockedforurls)|특정 사이트에서 이미지 차단|
|[InsecureContentAllowedForUrls](#insecurecontentallowedforurls)|지정된 사이트에서 비보안 콘텐츠 허용|
|[InsecureContentBlockedForUrls](#insecurecontentblockedforurls)|지정된 사이트에서 비보안 콘텐츠 차단|
|[JavaScriptAllowedForUrls](#javascriptallowedforurls)|특정 사이트에서 JavaScript 허용|
|[JavaScriptBlockedForUrls](#javascriptblockedforurls)|특정 사이트에서 JavaScript 차단|
|[LegacySameSiteCookieBehaviorEnabled](#legacysamesitecookiebehaviorenabled)|기본 레거시 SameSite 쿠키 동작 설정 사용|
|[LegacySameSiteCookieBehaviorEnabledForDomainList](#legacysamesitecookiebehaviorenabledfordomainlist)|지정된 사이트에서 쿠키에 대한 레거시 SameSite 동작으로 되돌리기|
|[NotificationsAllowedForUrls](#notificationsallowedforurls)|특정 사이트에서 알림 허용|
|[NotificationsBlockedForUrls](#notificationsblockedforurls)|특정 사이트에서 알림 차단|
|[PluginsAllowedForUrls](#pluginsallowedforurls)|특정 사이트에서 Adobe Flash 플러그인 허용(obsolete)|
|[PluginsBlockedForUrls](#pluginsblockedforurls)|특정 사이트에서 Adobe Flash 플러그인 차단(obsolete)|
|[PopupsAllowedForUrls](#popupsallowedforurls)|특정 사이트에서 팝업 창 허용|
|[PopupsBlockedForUrls](#popupsblockedforurls)|특정 사이트에서 팝업 창 차단|
|[RegisteredProtocolHandlers](#registeredprotocolhandlers)|프로토콜 처리기 등록|
|[SpotlightExperiencesAndRecommendationsEnabled](#spotlightexperiencesandrecommendationsenabled)|사용자가 Microsoft 서비스에 대한 사용자 지정 배경 이미지와 텍스트, 제안, 알림
및 팁을 받을 수 있는지 여부를 선택합니다|
|[WebUsbAllowDevicesForUrls](#webusballowdevicesforurls)|특정 USB 장치에 연결할 특정 사이트에 대한 액세스 권한 부여|
|[WebUsbAskForUrl](#webusbaskforurls)|특정 사이트에서 WebUSB 허용|
|[WebUsbBlockedForUrls](#webusbblockedforurls)|특정 사이트에서 WebUSB 차단|
### [*<a name="default-search-provider"></a>기본 검색 공급자*](#default-search-provider-policies)

|정책 이름|캡션|
|-|-|
|[DefaultSearchProviderEnabled](#defaultsearchproviderenabled)|기본 검색 공급자 사용|
|[DefaultSearchProviderEncodings](#defaultsearchproviderencodings)|기본 검색 공급자 인코딩|
|[DefaultSearchProviderImageURL](#defaultsearchproviderimageurl)|기본 검색 공급자에 대한 이미지 검색 기능 지정|
|[DefaultSearchProviderImageURLPostParams](#defaultsearchproviderimageurlpostparams)|POST를 사용하는 이미지 URL에 대한 매개 변수|
|[DefaultSearchProviderKeyword](#defaultsearchproviderkeyword)|기본 검색 공급자 키워드|
|[DefaultSearchProviderName](#defaultsearchprovidername)|기본 검색 공급자 이름|
|[DefaultSearchProviderSearchURL](#defaultsearchprovidersearchurl)|기본 검색 공급자 검색 URL|
|[DefaultSearchProviderSuggestURL](#defaultsearchprovidersuggesturl)|제안에 대한 기본 검색 공급자 URL|
|[NewTabPageSearchBox](#newtabpagesearchbox)|새 탭 페이지 검색창 환경 구성|
### [*<a name="extensions"></a>Extensions*](#extensions-policies)

|정책 이름|캡션|
|-|-|
|[BlockExternalExtensions](#blockexternalextensions)|외부 확장이 설치되지 않도록 차단압니다.|
|[ExtensionAllowedTypes](#extensionallowedtypes)|허용된 확장 유형 구성|
|[ExtensionInstallAllowlist](#extensioninstallallowlist)|특정 확장 설치 허용|
|[ExtensionInstallBlocklist](#extensioninstallblocklist)|설치할 수 없는 확장 제어|
|[ExtensionInstallForcelist](#extensioninstallforcelist)|자동으로 설치되는 확장 제어|
|[ExtensionInstallSources](#extensioninstallsources)|확장 및 사용자 스크립트 설치 원본 구성|
|[ExtensionSettings](#extensionsettings)|확장 관리 설정 구성|
### [*<a name="http-authentication"></a>HTTP 인증*](#http-authentication-policies)

|정책 이름|캡션|
|-|-|
|[AllowCrossOriginAuthPrompt](#allowcrossoriginauthprompt)|Allow cross-origin HTTP Authentication prompts|
|[AuthNegotiateDelegateAllowlist](#authnegotiatedelegateallowlist)|Microsoft Edge에서 사용자 자격 증명을 위임할 수 있는 서버 목록 지정|
|[AuthSchemes](#authschemes)|지원되는 인증 구성표|
|[AuthServerAllowlist](#authserverallowlist)|허용되는 인증 서버 목록 구성|
|[BasicAuthOverHttpEnabled](#basicauthoverhttpenabled)|HTTP에 대한 기본 인증 허용|
|[DisableAuthNegotiateCnameLookup](#disableauthnegotiatecnamelookup)|Kerberos 인증 협상 시 CNAME 조회 해제|
|[EnableAuthNegotiatePort](#enableauthnegotiateport)|Kerberos SPN에 표준이 아닌 포트 포함|
|[NtlmV2Enabled](#ntlmv2enabled)|NTLMv2 인증 사용 여부 제어|
|[WindowsHelloForHTTPAuthEnabled](#windowshelloforhttpauthenabled)|HTTP용 Windows Hello 인증 사용|
### [*<a name="kiosk-mode-settings"></a>키오스크 모드 설정*](#kiosk-mode-settings-policies)

|정책 이름|캡션|
|-|-|
|[KioskAddressBarEditingEnabled](#kioskaddressbareditingenabled)|키오스크 모드 공개 검색 환경에 대해 주소 표시줄 편집을 구성|
|[KioskDeleteDownloadsOnExit](#kioskdeletedownloadsonexit)|Microsoft Edge가 닫히는 경우 키오스크 세션의 일부로 다운로드한 파일을 삭제|
### [*<a name="manageability"></a>관리 효율성*](#manageability-policies)

|정책 이름|캡션|
|-|-|
|[MAMEnabled](#mamenabled)|모바일 앱 관리 사용|
### [*<a name="native-messaging"></a>기본 메시지*](#native-messaging-policies)

|정책 이름|캡션|
|-|-|
|[NativeMessagingAllowlist](#nativemessagingallowlist)|사용자가 사용할 수 있는 기본 메시지 호스트 제어|
|[NativeMessagingBlocklist](#nativemessagingblocklist)|기본 메시지 차단 목록 구성|
|[NativeMessagingUserLevelHosts](#nativemessaginguserlevelhosts)|사용자 수준 기본 메시지 호스트 허용(관리자 권한없이 설치됨)|
### [*<a name="password-manager-and-protection"></a>암호 관리자 및 보호*](#password-manager-and-protection-policies)

|정책 이름|캡션|
|-|-|
|[PasswordManagerEnabled](#passwordmanagerenabled)|암호 관리자에 암호 저장 사용|
|[PasswordMonitorAllowed](#passwordmonitorallowed)|암호가 안전하지 않은 것으로 확인되면 사용자에게 알림 허용|
|[PasswordProtectionChangePasswordURL](#passwordprotectionchangepasswordurl)|암호 변경 URL 구성|
|[PasswordProtectionLoginURLs](#passwordprotectionloginurls)|암호 보호 서비스에서 암호 보호 서비스가 솔트 암호 캐시를 캡처해야 하는 엔터프라이즈 로그인 URL 목록 구성|
|[PasswordProtectionWarningTrigger](#passwordprotectionwarningtrigger)|암호 보호 경고 트리거 구성|
|[PasswordRevealEnabled](#passwordrevealenabled)|암호 노출 사용 단추|
### [*<a name="performance"></a>성능*](#performance-policies)

|정책 이름|캡션|
|-|-|
|[StartupBoostEnabled](#startupboostenabled)|시작 부스트 활성화|
### [*<a name="printing"></a>인쇄*](#printing-policies)

|정책 이름|캡션|
|-|-|
|[DefaultPrinterSelection](#defaultprinterselection)|기본 프린터 선택 규칙|
|[PrintHeaderFooter](#printheaderfooter)|머리글 및 바닥글 인쇄|
|[PrintPreviewUseSystemDefaultPrinter](#printpreviewusesystemdefaultprinter)|시스템 기본 프린터를 기본 프린터로 설정|
|[PrintRasterizationMode](#printrasterizationmode)|인쇄 래스터화 모드|
|[PrinterTypeDenyList](#printertypedenylist)|거부 목록에서 프린터 유형을 사용하지 않도록 설정|
|[PrintingAllowedBackgroundGraphicsModes](#printingallowedbackgroundgraphicsmodes)|배경 그래픽 인쇄 모드 제한|
|[PrintingBackgroundGraphicsDefault](#printingbackgroundgraphicsdefault)|기본 배경 그래픽 인쇄 모드|
|[PrintingEnabled](#printingenabled)|인쇄 사용|
|[PrintingPaperSizeDefault](#printingpapersizedefault)|기본 인쇄 페이지 크기|
|[UseSystemPrintDialog](#usesystemprintdialog)|시스템 인쇄 대화 상자를 사용하여 인쇄|
### [*<a name="proxy-server"></a>프록시 서버*](#proxy-server-policies)

|정책 이름|캡션|
|-|-|
|[ProxyBypassList](#proxybypasslist)|프록시 무시 규칙 구성(사용하지 않음)|
|[ProxyMode](#proxymode)|프록시 서버 설정 구성(사용하지 않음)|
|[ProxyPacUrl](#proxypacurl)|프록시 .pac 파일 URL 설정(사용하지 않음)|
|[ProxyServer](#proxyserver)|프록시 서버 주소 또는 URL 구성(사용하지 않음)|
|[ProxySettings](#proxysettings)|프록시 설정|
### [*<a name="sleeping-tabs-settings"></a>절전 탭 설정*](#sleeping-tabs-settings-policies)

|정책 이름|캡션|
|-|-|
|[SleepingTabsBlockedForUrls](#sleepingtabsblockedforurls)|특정 사이트에서 절전 탭 차단|
|[SleepingTabsEnabled](#sleepingtabsenabled)|절전 모드 탭 구성|
|[SleepingTabsTimeout](#sleepingtabstimeout)|절전 탭에 대한 백그라운드 탭 비활성 시간 제한 설정|
### [*<a name="smartscreen-settings"></a>SmartScreen 설정*](#smartscreen-settings-policies)

|정책 이름|캡션|
|-|-|
|[PreventSmartScreenPromptOverride](#preventsmartscreenpromptoverride)|사이트에 대한 Microsoft Defender SmartScreen 프롬프트 무시 방지|
|[PreventSmartScreenPromptOverrideForFiles](#preventsmartscreenpromptoverrideforfiles)|다운로드에 대한 Microsoft Defender SmartScreen 경고 무시 방지|
|[SmartScreenAllowListDomains](#smartscreenallowlistdomains)|Microsoft Defender SmartScreen이 경고를 트리거하지 않는 도메인 목록 구성|
|[SmartScreenEnabled](#smartscreenenabled)|Microsoft Defender SmartScreen 구성|
|[SmartScreenForTrustedDownloadsEnabled](#smartscreenfortrusteddownloadsenabled)|신뢰할 수 있는 출처에서 다운로드 시 Microsoft Defender SmartScreen 강제 확인|
|[SmartScreenPuaEnabled](#smartscreenpuaenabled)|잠재적으로 원치 않는 앱을 차단하도록 Microsoft Defender SmartScreen 구성|
### [*<a name="startupcomma-home-page-and-new-tab-page"></a>시작&comma; 홈 페이지 및 새 탭 페이지*](#startup-home-page-and-new-tab-page-policies)

|정책 이름|캡션|
|-|-|
|[HomepageIsNewTabPage](#homepageisnewtabpage)|새 탭 페이지를 홈 페이지로 설정|
|[HomepageLocation](#homepagelocation)|홈 페이지 URL 구성|
|[NewTabPageAllowedBackgroundTypes](#newtabpageallowedbackgroundtypes)|새 탭 페이지 레이아웃에 허용되는 배경 유형 구성|
|[NewTabPageCompanyLogo](#newtabpagecompanylogo)|새 탭 페이지 회사 로고 설정(구식)|
|[NewTabPageHideDefaultTopSites](#newtabpagehidedefaulttopsites)|새 탭 페이지에서 기본 상위 사이트 숨기기|
|[NewTabPageLocation](#newtabpagelocation)|새 탭 페이지 URL 구성|
|[NewTabPageManagedQuickLinks](#newtabpagemanagedquicklinks)|새 탭 페이지 빠른 링크 설정|
|[NewTabPagePrerenderEnabled](#newtabpageprerenderenabled)|더 빠른 렌더링을 위해 새 탭 페이지의 미리 로드 활성화|
|[NewTabPageSetFeedType](#newtabpagesetfeedtype)|Microsoft Edge 새 탭 페이지 환경 구성(사용되지 않음)|
|[RestoreOnStartup](#restoreonstartup)|시작 시 수행하는 작업|
|[RestoreOnStartupURLs](#restoreonstartupurls)|브라우저 시작 시 열리는 사이트|
|[ShowHomeButton](#showhomebutton)|도구 모음에서 홈 단추 표시|
### [*<a name="additional"></a>추가 정보*](#additional-policies)

|정책 이름|캡션|
|-|-|
|[AddressBarMicrosoftSearchInBingProviderEnabled](#addressbarmicrosoftsearchinbingproviderenabled)|주소 표시줄의 Bing 제안에서 Microsoft Search 사용|
|[AdsSettingForIntrusiveAdsSites](#adssettingforintrusiveadssites)|간섭 광고가 포함된 사이트에 대한 광고 설정|
|[AllowDeletingBrowserHistory](#allowdeletingbrowserhistory)|브라우저 및 다운로드 기록 삭제 사용|
|[AllowFileSelectionDialogs](#allowfileselectiondialogs)|파일 선택 대화 상자 허용|
|[AllowPopupsDuringPageUnload](#allowpopupsduringpageunload)|페이지를 언로딩하는 동안 팝업 표시 허용(사용되지 않음)|
|[AllowSurfGame](#allowsurfgame)|서핑 게임 허용|
|[AllowSyncXHRInPageDismissal](#allowsyncxhrinpagedismissal)|페이지를 해제하는 동안 페이지에서 동기 XHR 요청 전송 허용(사용되지 않음)|
|[AllowTokenBindingForUrls](#allowtokenbindingforurls)|Microsoft Edge에서 토큰 바인딩을 설정하려는 사이트 목록 구성|
|[AllowTrackingForUrls](#allowtrackingforurls)|특정 사이트에 대한 추적 방지 예외 구성|
|[AlternateErrorPagesEnabled](#alternateerrorpagesenabled)|웹 페이지를 찾을 수 없는 경우 비슷한 페이지 제안|
|[AlwaysOpenPdfExternally](#alwaysopenpdfexternally)|외부에서 항상 PDF 파일 열기|
|[AmbientAuthenticationInPrivateModesEnabled](#ambientauthenticationinprivatemodesenabled)|InPrivate 및 게스트 프로필에 대한 앰비언트 인증 사용|
|[AppCacheForceEnabled](#appcacheforceenabled)|AppCache 기능이 기본적으로 해제되어 있더라도 다시 사용할 수 있도록 허용|
|[ApplicationLocaleValue](#applicationlocalevalue)|응용 프로그램 로캘 설정|
|[AudioCaptureAllowed](#audiocaptureallowed)|오디오 캡처 허용 또는 차단|
|[AudioCaptureAllowedUrls](#audiocaptureallowedurls)|권한 요청 없이 오디오 캡처 장치에 액세스할 수 있는 사이트|
|[AudioSandboxEnabled](#audiosandboxenabled)|오디오 샌드박스 실행 허용|
|[AutoImportAtFirstRun](#autoimportatfirstrun)|처음 실행 시 다른 브라우저의 데이터 및 설정 자동으로 가져오기|
|[AutoLaunchProtocolsFromOrigins](#autolaunchprotocolsfromorigins)|사용자에게 묻지 않고 목록에 있는 원본에서 외부 응용 프로그램을 실행할 수 있는 프로토콜 목록 정의|
|[AutoOpenAllowedForURLs](#autoopenallowedforurls)|AutoOpenFileTypes를 적용할 수 있는 URL|
|[AutoOpenFileTypes](#autoopenfiletypes)|다운로드 시 자동으로 열려야 하는 파일 형식 목록|
|[AutofillAddressEnabled](#autofilladdressenabled)|주소에 자동 채우기 사용|
|[AutofillCreditCardEnabled](#autofillcreditcardenabled)|신용 카드에 자동 채우기 사용|
|[AutoplayAllowed](#autoplayallowed)|웹 사이트에 미디어 자동 실행 허용|
|[BackgroundModeEnabled](#backgroundmodeenabled)|Microsoft Edge 종료 후 백그라운드 앱 계속 실행|
|[BackgroundTemplateListUpdatesEnabled](#backgroundtemplatelistupdatesenabled)|서식 파일을 사용하는 컬렉션 및 기타 기능에 대해 사용 가능한 서식 파일 목록의 백그라운드 업데이트 사용|
|[BingAdsSuppression](#bingadssuppression)|Bing 검색 결과에서 모든 광고 차단|
|[BlockThirdPartyCookies](#blockthirdpartycookies)|타사 쿠키 차단|
|[BrowserAddProfileEnabled](#browseraddprofileenabled)|ID 플라이아웃 메뉴 또는 설정 페이지에서 프로필 만들기 사용|
|[BrowserGuestModeEnabled](#browserguestmodeenabled)|게스트 모드 사용|
|[BrowserNetworkTimeQueriesEnabled](#browsernetworktimequeriesenabled)|브라우저 네트워크 시간 서비스에 쿼리 허용|
|[BrowserSignin](#browsersignin)|브라우저 로그인 설정|
|[BrowsingDataLifetime](#browsingdatalifetime)|데이터 수명 설정 검색|
|[BuiltInDnsClientEnabled](#builtindnsclientenabled)|기본 제공 DNS 클라이언트 사용|
|[BuiltinCertificateVerifierEnabled](#builtincertificateverifierenabled)|서버 인증서를 확인하는 데 기본 제공 인증서 검증 도구를 사용할지 여부 결정(사용되지 않음)|
|[CertificateTransparencyEnforcementDisabledForCas](#certificatetransparencyenforcementdisabledforcas)|subjectPublicKeyInfo 해시 목록에 대한 인증서 투명도 적용 해제|
|[CertificateTransparencyEnforcementDisabledForLegacyCas](#certificatetransparencyenforcementdisabledforlegacycas)|레거시 인증 기관 목록에 대한 인증서 투명도 적용 해제|
|[CertificateTransparencyEnforcementDisabledForUrls](#certificatetransparencyenforcementdisabledforurls)|특정 URL에 대한 인증서 투명도 적용 해제|
|[ClearBrowsingDataOnExit](#clearbrowsingdataonexit)|Microsoft Edge 종료 시 데이터 검색 삭제|
|[ClearCachedImagesAndFilesOnExit](#clearcachedimagesandfilesonexit)|Microsoft Edge 종료 시 캐시된 이미지 및 파일 삭제|
|[ClickOnceEnabled](#clickonceenabled)|사용자가 ClickOnce 프로토콜을 사용하여 파일을 열 수 있도록 허용|
|[CollectionsServicesAndExportsBlockList](#collectionsservicesandexportsblocklist)|지정된 서비스 목록에 대한 액세스를 차단하고 컬렉션에서 대상 내보내기|
|[CommandLineFlagSecurityWarningsEnabled](#commandlineflagsecuritywarningsenabled)|명령줄 플래그에 대한 보안 경고 사용|
|[ComponentUpdatesEnabled](#componentupdatesenabled)|Microsoft Edge에서 구성 요소 업데이트 사용|
|[ConfigureDoNotTrack](#configuredonottrack)|Do Not Track 구성|
|[ConfigureFriendlyURLFormat](#configurefriendlyurlformat)|Microsoft Edge에서 복사된 URL의 기본 붙여넣기 서식을 구성하고 추가 형식이 사용자에게 제공되는지 확인|
|[ConfigureOnPremisesAccountAutoSignIn](#configureonpremisesaccountautosignin)|Azure AD 도메인 계정이 없는 경우 Active Directory 도메인 계정으로 자동 로그인 구성|
|[ConfigureOnlineTextToSpeech](#configureonlinetexttospeech)|온라인 텍스트 음성 변환 구성|
|[ConfigureShare](#configureshare)|공유 환경 구성|
|[CustomHelpLink](#customhelplink)|사용자 지정 도움말 링크 지정|
|[DNSInterceptionChecksEnabled](#dnsinterceptionchecksenabled)|DNS 차단 검사 사용|
|[DefaultBrowserSettingEnabled](#defaultbrowsersettingenabled)|Microsoft Edge를 기본 브라우저로 설정|
|[DefaultSearchProviderContextMenuAccessAllowed](#defaultsearchprovidercontextmenuaccessallowed)|기본 검색 공급자에 상황에 맞는 메뉴 검색 액세스 허용|
|[DefaultSensorsSetting](#defaultsensorssetting)|기본 센서 설정|
|[DefaultSerialGuardSetting](#defaultserialguardsetting)|직렬 API 사용 제어|
|[DefinePreferredLanguages](#definepreferredlanguages)|사이트에서 언어를 지원하는 경우 웹 사이트에서 표시할 기본 설정 언어 순서가 지정된 목록 정의|
|[DelayNavigationsForInitialSiteListDownload](#delaynavigationsforinitialsitelistdownload)|탭 탐색 전에 엔터프라이즈 모드 사이트 목록을 사용하도록 요청|
|[DeleteDataOnMigration](#deletedataonmigration)|마이그레이션 시 이전 브라우저 데이터 삭제|
|[DeveloperToolsAvailability](#developertoolsavailability)|개발자 도구를 사용할 수 있는 위치 제어|
|[DiagnosticData](#diagnosticdata)|브라우저를 사용하는 데 필요한 선택적 진단 데이터 보내기|
|[DirectInvokeEnabled](#directinvokeenabled)|사용자가 DirectInvoke 프로토콜을 사용하여 파일을 열 수 있도록 허용|
|[Disable3DAPIs](#disable3dapis)|3D 그래픽 API에 대한 지원 해제|
|[DisableScreenshots](#disablescreenshots)|스크린샷 기능 해제|
|[DiskCacheDir](#diskcachedir)|디스크 캐시 디렉터리 설정|
|[DiskCacheSize](#diskcachesize)|디스크 캐시 크기를 바이트 단위로 설정|
|[DnsOverHttpsMode](#dnsoverhttpsmode)|DoH(DNS over HTTPS) 모드 제어|
|[DnsOverHttpsTemplates](#dnsoverhttpstemplates)|원하는 DoH(DNS over HTTPS) 확인자의 URI 서식 파일 지정|
|[DownloadDirectory](#downloaddirectory)|다운로드 디렉터리 설정|
|[DownloadRestrictions](#downloadrestrictions)|다운로드 제한 허용|
|[EdgeCollectionsEnabled](#edgecollectionsenabled)|컬렉션 기능 사용|
|[EdgeShoppingAssistantEnabled](#edgeshoppingassistantenabled)|Microsoft Edge에서 쇼핑 사용|
|[EditFavoritesEnabled](#editfavoritesenabled)|사용자가 즐겨찾기를 편집할 수 있도록 허용|
|[EnableDeprecatedWebPlatformFeatures](#enabledeprecatedwebplatformfeatures)|GP 이름: 제한된 시간 동안 사용되지 않는 웹 플랫폼 기능 다시 사용(obsolete)|
|[EnableDomainActionsDownload](#enabledomainactionsdownload)|Microsoft에서 도메인 작업 다운로드 사용(사용되지 않음)|
|[EnableOnlineRevocationChecks](#enableonlinerevocationchecks)|온라인 OCSP/CRL 검사 사용|
|[EnableSha1ForLocalAnchors](#enablesha1forlocalanchors)|로컬 트러스트 앵커에서 발급한 경우 SHA-1을 사용하여 서명한 인증서 허용(사용되지 않음)|
|[EnterpriseHardwarePlatformAPIEnabled](#enterprisehardwareplatformapienabled)|Managed Extensions에서 엔터프라이즈 하드웨어 플랫폼 API를 사용할 수 있도록 허용|
|[EnterpriseModeSiteListManagerAllowed](#enterprisemodesitelistmanagerallowed)|엔터프라이즈 모드 사이트 목록 관리자 도구에 대한 액세스 허용|
|[ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](#exemptdomainfiletypepairsfromfiletypedownloadwarnings)|도메인에서 지정된 파일 형식에 대한 다운로드 파일 형식 확장자 기반 경고 비활성화|
|[ExperimentationAndConfigurationServiceControl](#experimentationandconfigurationservicecontrol)|실험 및 구성 서비스와의 통신 제어|
|[ExternalProtocolDialogShowAlwaysOpenCheckbox](#externalprotocoldialogshowalwaysopencheckbox)|외부 프로토콜 대화 상자에서 "항상 열기" 확인란 표시|
|[FamilySafetySettingsEnabled](#familysafetysettingsenabled)|사용자가 가족 보호 및 키즈 모드를 구성할 수 있도록 허용|
|[FavoritesBarEnabled](#favoritesbarenabled)|즐겨찾기 모음 사용|
|[ForceBingSafeSearch](#forcebingsafesearch)|Bing 유해 정보 차단 적용|
|[ForceCertificatePromptsOnMultipleMatches](#forcecertificatepromptsonmultiplematches)|"AutoSelectCertificateForUrls"를 사용하여 구성한 사이트에 대해 일치하는 인증서가 여러 개인 경우 Microsoft Edge에서 자동으로 인증서를 선택할 것인지 여부 지정|
|[ForceEphemeralProfiles](#forceephemeralprofiles)|임시 프로필 사용 설정|
|[ForceGoogleSafeSearch](#forcegooglesafesearch)|Google 유해 정보 차단 적용|
|[ForceLegacyDefaultReferrerPolicy](#forcelegacydefaultreferrerpolicy)|no-referrer-when-downgrade의 기본 참조자 정책 사용(사용되지 않음)|
|[ForceNetworkInProcess](#forcenetworkinprocess)|브라우저 프로세스에서 네트워킹 코드 실행 강제(사용되지 않음)|
|[ForceSync.](#forcesync)|브라우저 데이터를 강제로 동기화하고 동기화 동의 프롬프트를 표시 안 함|
|[ForceYouTubeRestrict](#forceyoutuberestrict)|최소 YouTube 제한 모드 강제|
|[FullscreenAllowed](#fullscreenallowed)|전체 화면 모드 허용|
|[GloballyScopeHTTPAuthCacheEnabled](#globallyscopehttpauthcacheenabled)|전역 범위 HTTP 인증 캐시 사용|
|[GoToIntranetSiteForSingleWordEntryInAddressBar](#gotointranetsiteforsinglewordentryinaddressbar)|주소 표시줄에서 단일 단어 항목을 검색하는 대신 직접 인트라넷 사이트 탐색 강제|
|[HSTSPolicyBypassList](#hstspolicybypasslist)|HSTS 정책 확인을 무시하는 이름 목록 구성|
|[HardwareAccelerationModeEnabled](#hardwareaccelerationmodeenabled)|가능한 경우 하드웨어 가속 사용|
|[HideFirstRunExperience](#hidefirstrunexperience)|첫 실행 환경 및 시작 화면 숨김|
|[HideInternetExplorerRedirectUXForIncompatibleSitesEnabled](#hideinternetexplorerredirectuxforincompatiblesitesenabled)|Microsoft Edge에서 일회성 리디렉션 대화 상자 및 배너 숨기기|
|[ImportAutofillFormData](#importautofillformdata)|자동 채우기 양식 데이터 가져오기 허용|
|[ImportBrowserSettings](#importbrowsersettings)|브라우저 설정 가져오기 허용|
|[ImportCookies](#importcookies)|쿠키 가져오기 허용|
|[ImportExtensions](#importextensions)|확장 가져오기 허용|
|[ImportFavorites](#importfavorites)|즐겨찾기 가져오기 허용|
|[ImportHistory](#importhistory)|검색 기록 가져오기 허용|
|[ImportHomepage](#importhomepage)|홈페이지 설정 가져오기 허용|
|[ImportOpenTabs](#importopentabs)|열린 탭 가져오기 허용|
|[ImportPaymentInfo](#importpaymentinfo)|결제 정보 가져오기 허용|
|[ImportSavedPasswords](#importsavedpasswords)|저장된 암호 가져오기 허용|
|[ImportSearchEngine](#importsearchengine)|검색 엔진 설정 가져오기 허용|
|[ImportShortcuts](#importshortcuts)|바로 가기 가져오기 허용|
|[InPrivateModeAvailability](#inprivatemodeavailability)|InPrivate 모드 가용성 구성|
|[InsecureFormsWarningsEnabled](#insecureformswarningsenabled)|안전하지 않은 양식에 대한 경고 설정|
|[IntensiveWakeUpThrottlingEnabled](#intensivewakeupthrottlingenabled)|IntensiveWakeUpThrottling 기능 제어|
|[InternetExplorerIntegrationEnhancedHangDetection](#internetexplorerintegrationenhancedhangdetection)|Internet Explorer 모드에 대한 향상된 중지 검색 구성|
|[InternetExplorerIntegrationLevel](#internetexplorerintegrationlevel)|Internet Explorer 통합 구성|
|[InternetExplorerIntegrationLocalFileAllowed](#internetexplorerintegrationlocalfileallowed)|Internet Explorer 모드에서 로컬 파일 시작 허용|
|[InternetExplorerIntegrationLocalFileExtensionAllowList](#internetexplorerintegrationlocalfileextensionallowlist)|Internet Explorer 모드 파일 확장명 허용 목록에서 로컬 파일 열기|
|[InternetExplorerIntegrationLocalFileShowContextMenu](#internetexplorerintegrationlocalfileshowcontextmenu)|Internet Explorer 모드에서 링크를 여는 상황에 맞는 메뉴 표시|
|[InternetExplorerIntegrationSiteList](#internetexplorerintegrationsitelist)|엔터프라이즈 모드 사이트 목록 구성|
|[InternetExplorerIntegrationSiteRedirect](#internetexplorerintegrationsiteredirect)|Internet Explorer 모드 페이지에서 시작 시 구성되지 않은 사이트에 대한 "페이지 내" 탐색 동작 방법 지정|
|[InternetExplorerIntegrationTestingAllowed](#internetexplorerintegrationtestingallowed)|Internet Explorer 모드 테스트 허용|
|[IntranetRedirectBehavior](#intranetredirectbehavior)|인트라넷 리디렉션 동작|
|[IsolateOrigins](#isolateorigins)|특정 원본에 대해 사이트 격리 사용|
|[LocalProvidersEnabled](#localprovidersenabled)|로컬 공급자의 제안 허용|
|[ManagedConfigurationPerOrigin](#managedconfigurationperorigin)|웹 사이트의 관리되는 구성 값을 특정 원본으로 설정|
|[ManagedFavorites](#managedfavorites)|즐겨찾기 구성|
|[ManagedSearchEngines](#managedsearchengines)|검색 엔진 관리|
|[MaxConnectionsPerProxy](#maxconnectionsperproxy)|프록시 서버에 대한 최대 동시 연결 수|
|[MediaRouterCastAllowAllIPs](#mediaroutercastallowallips)|모든 IP 주소의 캐스트 장치에 Google Cast 연결 허용|
|[MetricsReportingEnabled](#metricsreportingenabled)|사용 현황 및 크래시 관련 데이터 보고 사용(사용되지 않음)|
|[NativeWindowOcclusionEnabled](#nativewindowocclusionenabled)|네이티브 창 폐색 사용(사용되지 않음)|
|[NavigationDelayForInitialSiteListDownloadTimeout](#navigationdelayforinitialsitelistdownloadtimeout)|엔터프라이즈 모드 사이트 목록에 대한 탭 탐색 지연 시간 제한 설정|
|[NetworkPredictionOptions](#networkpredictionoptions)|네트워크 예측 사용|
|[NonRemovableProfileEnabled](#nonremovableprofileenabled)|사용자에게 항상 회사 또는 학교 계정으로 자동 로그인되는 기본 프로필이 있는지 여부 구성|
|[OverrideSecurityRestrictionsOnInsecureOrigin](#overridesecurityrestrictionsoninsecureorigin)|비보안 원본에 대해 보안 제한이 적용되는 위치 제어|
|[PaymentMethodQueryEnabled](#paymentmethodqueryenabled)|웹 사이트에서 사용 가능한 결제 방법을 쿼리하도록 허용|
|[PersonalizationReportingEnabled](#personalizationreportingenabled)|Microsoft에 검색 기록을 보내어 광고, 검색, 뉴스를 개인 설정하도록 허용|
|[PinningWizardAllowed](#pinningwizardallowed)|작업 표시줄에 고정 마법사 허용|
|[ProactiveAuthEnabled](#proactiveauthenabled)|자동 관리 인증 사용(사용하지 않음)|
|[PromotionalTabsEnabled](#promotionaltabsenabled)|전체 탭 프로모션 콘텐츠 사용|
|[PromptForDownloadLocation](#promptfordownloadlocation)|다운로드한 파일을 저장할 위치 묻기|
|[QuicAllowed](#quicallowed)|QUIC 프로토콜 허용|
|[QuickViewOfficeFilesEnabled](#quickviewofficefilesenabled)|Microsoft Edge에서 QuickView Office 파일 기능 관리|
|[RedirectSitesFromInternetExplorerPreventBHOInstall](#redirectsitesfrominternetexplorerpreventbhoinstall)|호환되지 않는 사이트를 Internet Explorer에서 Microsoft Edge로 리디렉션하는 BHO 설치 방지|
|[RedirectSitesFromInternetExplorerRedirectMode](#redirectsitesfrominternetexplorerredirectmode)|호환되지 않는 사이트를 Internet Explorer에서 Microsoft Edge로 리디렉션|
|[RelaunchNotification](#relaunchnotification)|사용자에게 보류 중인 업데이트에 대해 브라우저의 재시작을 권장하거나 필요함을 알림|
|[RelaunchNotificationPeriod](#relaunchnotificationperiod)|업데이트 알림 기간 설정|
|[RendererCodeIntegrityEnabled](#renderercodeintegrityenabled)|렌더러 코드 무결성 사용|
|[RequireOnlineRevocationChecksForLocalAnchors](#requireonlinerevocationchecksforlocalanchors)|로컬 트러스트 앵커에 대한 온라인 OCSP/CRL 검사 필요 여부 지정|
|[ResolveNavigationErrorsUseWebService](#resolvenavigationerrorsusewebservice)|웹 서비스를 사용하여 탐색 오류 해결 설정|
|[RestrictSigninToPattern](#restrictsignintopattern)|Microsoft Edge 기본 계정으로 사용할 수 있는 계정 제한|
|[RoamingProfileLocation](#roamingprofilelocation)|로밍 프로필 디렉터리 설정|
|[RoamingProfileSupportEnabled](#roamingprofilesupportenabled)|Microsoft Edge 프로필 데이터에 대한 로밍 복사본을 사용할 수 있도록 설정|
|[RunAllFlashInAllowMode](#runallflashinallowmode)|Adobe Flash 콘텐츠 설정을 모든 콘텐츠로 확장(obsolete)|
|[SSLErrorOverrideAllowed](#sslerroroverrideallowed)|HTTPS 경고 페이지에서 사용자가 계속할 수 있도록 허용|
|[SSLErrorOverrideAllowedForOrigins](#sslerroroverrideallowedfororigins)|사용자가 특정 출처에 대한 HTTPS 경고 페이지에서 계속하도록 허용|
|[SSLVersionMin](#sslversionmin)|최소 TLS 버전 사용(사용되지 않음)|
|[SaveCookiesOnExit](#savecookiesonexit)|Microsoft Edge가 닫힐 때 쿠키 저장|
|[SavingBrowserHistoryDisabled](#savingbrowserhistorydisabled)|브라우저 기록 저장 사용 안 함|
|[ScreenCaptureAllowed](#screencaptureallowed)|화면 캡처 허용 또는 거부|
|[ScrollToTextFragmentEnabled](#scrolltotextfragmentenabled)|URL 조각에 지정된 텍스트로 스크롤 사용|
|[SearchSuggestEnabled](#searchsuggestenabled)|검색 제안 사용|
|[SecurityKeyPermitAttestation](#securitykeypermitattestation)|직접 보안 키 증명을 사용하기 위한 권한이 필요 없는 웹 사이트 또는 도메인|
|[SendIntranetToInternetExplorer](#sendintranettointernetexplorer)|Internet Explorer에 모든 인트라넷 사이트 보내기|
|[SendSiteInfoToImproveServices](#sendsiteinfotoimproveservices)|Microsoft 서비스를 개선하기 위해 사이트 정보 전송(사용되지 않음)|
|[SensorsAllowedForUrls](#sensorsallowedforurls)|특정 사이트의 센서에 대한 액세스 허용|
|[SensorsBlockedForUrls](#sensorsblockedforurls)|특정 사이트의 센서에 대한 액세스 차단|
|[SerialAskForUrls](#serialaskforurls)|특정 사이트에서 직렬 API 허용|
|[SerialBlockedForUrls](#serialblockedforurls)|특정 사이트에서 직렬 API 차단|
|[ShowMicrosoftRewards](#showmicrosoftrewards)|Microsoft Rewards 환경 표시|
|[ShowOfficeShortcutInFavoritesBar](#showofficeshortcutinfavoritesbar)|즐겨 찾기 모음에 Microsoft Office 바로 가기 표시(사용되지 않음)|
|[ShowRecommendationsEnabled](#showrecommendationsenabled)|Microsoft Edge의 추천 및 홍보 알림 허용|
|[SignedHTTPExchangeEnabled](#signedhttpexchangeenabled)|SXG(Signed HTTP Exchange) 지원 사용|
|[SitePerProcess](#siteperprocess)|모든 사이트에 대해 사이트 격리 사용|
|[SmartActionsBlockList](#smartactionsblocklist)|서비스 목록에 대한 스마트 동작 차단|
|[SpeechRecognitionEnabled](#speechrecognitionenabled)|Configure Speech Recognition|
|[SpellcheckEnabled](#spellcheckenabled)|맞춤법 검사 사용|
|[SpellcheckLanguage](#spellchecklanguage)|특정 맞춤법 검사 언어 사용|
|[SpellcheckLanguageBlocklist](#spellchecklanguageblocklist)|맞춤법 검사 언어 강제 사용 해제|
|[StricterMixedContentTreatmentEnabled](#strictermixedcontenttreatmentenabled)|혼합 콘텐츠에 대해 더 엄격한 처리 사용(구식)|
|[SuppressUnsupportedOSWarning](#suppressunsupportedoswarning)|지원되지 않는 OS 경고 표시 안 함|
|[SyncDisabled](#syncdisabled)|Microsoft 동기화 서비스를 사용하여 데이터 동기화 사용 해제|
|[SyncTypesListDisabled](#synctypeslistdisabled)|동기화에서 제외되는 유형의 목록 구성|
|[TLS13HardeningForLocalAnchorsEnabled](#tls13hardeningforlocalanchorsenabled)|로컬 트러스트 앵커에 대한 TLS 1.3 보안 기능 사용(구식)|
|[TLSCipherSuiteDenyList](#tlsciphersuitedenylist)|비활성화할 TLS 암호화 그룹 지정|
|[TabFreezingEnabled](#tabfreezingenabled)|배경 탭 고정 허용|
|[TargetBlankImpliesNoOpener](#targetblankimpliesnoopener)|_blank를 대상으로 하는 링크에 대해 window.opener를 설정하지 마세요.|
|[TaskManagerEndProcessEnabled](#taskmanagerendprocessenabled)|브라우저 작업 관리자에서 프로세스 종료 사용|
|[TotalMemoryLimitMb](#totalmemorylimitmb)|단일 Microsoft Edge 인스턴스에서 사용할 수 있는 메모리 용량(MB) 제한 설정|
|[TrackingPrevention](#trackingprevention)|사용자의 웹 검색 활동 추적 차단|
|[TranslateEnabled](#translateenabled)|번역 사용|
|[URLAllowlist](#urlallowlist)|허용되는 URL 목록 정의|
|[URLBlocklist](#urlblocklist)|URL 목록에 대한 액세스 차단|
|[UpdatePolicyOverride](#updatepolicyoverride)|Microsoft Edge 업데이트가 Microsoft Edge에서 사용 가능한 업데이트를 처리하는 방법을 지정합니다.|
|[UserAgentClientHintsEnabled](#useragentclienthintsenabled)|사용자 에이전트 클라이언트 힌트 기능 사용(사용되지 않음)|
|[UserDataDir](#userdatadir)|사용자 데이터 디렉터리 설정|
|[UserDataSnapshotRetentionLimit](#userdatasnapshotretentionlimit)|긴급 롤백이 있을 경우 사용하기 위해 보관된 사용자 데이터 스냅샷 수를 제한합니다|
|[UserFeedbackAllowed](#userfeedbackallowed)|사용자 피드백 허용|
|[VerticalTabsAllowed](#verticaltabsallowed)|브라우저 측면의 탭에 대한 수직 레이아웃의 가용성 구성|
|[VideoCaptureAllowed](#videocaptureallowed)|비디오 캡처 허용 또는 차단|
|[VideoCaptureAllowedUrls](#videocaptureallowedurls)|권한 요청 없이 비디오 캡처 장치에 액세스할 수 있는 사이트|
|[WPADQuickCheckEnabled](#wpadquickcheckenabled)|WPAD 최적화 설정|
|[WebAppInstallForceList](#webappinstallforcelist)|강제 설치된 웹 앱 목록 구성|
|[WebCaptureEnabled](#webcaptureenabled)|Microsoft Edge에서 웹 캡처 기능을 사용하도록 설정|
|[WebComponentsV0Enabled](#webcomponentsv0enabled)|M84까지 웹 구성 요소 v0 API 다시 사용(사용되지 않음)|
|[WebDriverOverridesIncompatiblePolicies](#webdriveroverridesincompatiblepolicies)|WebDriver가 호환되지 않는 정책을 재정의하도록 허용(사용되지 않음)|
|[WebRtcAllowLegacyTLSProtocols](#webrtcallowlegacytlsprotocols)|WebRTC에서 레거시 TLS/DTLS 다운그레이드 허용(사용되지 않음)|
|[WebRtcLocalIpsAllowedUrls](#webrtclocalipsallowedurls)|WebRTC로 로컬 IP 주소 노출 관리|
|[WebRtcLocalhostIpHandling](#webrtclocalhostiphandling)|WebRTC로 로컬 IP 주소 노출 제한|
|[WebRtcUdpPortRange](#webrtcudpportrange)|WebRTC로 로컬 UDP 포트 범위 제한|
|[WebWidgetAllowed](#webwidgetallowed)|웹 위젯 설정|
|[WebWidgetIsEnabledOnStartup](#webwidgetisenabledonstartup)|Windows 시작 시 웹 위젯 허용|
|[WinHttpProxyResolverEnabled](#winhttpproxyresolverenabled)|Windows 프록시 해결 프로그램 사용(사용되지 않음)|
|[WindowOcclusionEnabled](#windowocclusionenabled)|창 폐색 사용|




  ## <a name="application-guard-settings-policies"></a>Application Guard 설정 정책

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="applicationguardcontainerproxy"></a>ApplicationGuardContainerProxy

  #### <a name="application-guard-container-proxy"></a>Application Guard 컨테이너 프록시

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 84 이상

  #### <a name="description"></a>설명

  Microsoft Edge Application Guard에 대한 프록시 설정을 구성합니다.
이 정책을 사용하도록 설정하면 Microsoft Edge Application Guard에서 프록시 구성의 다른 원본을 무시합니다.

이 정책을 구성하지 않으면 Microsoft Edge Application Guard는 호스트의 프록시 구성을 사용합니다.

이 정책은 Application Guard(호스트) 외부의 Microsoft Edge 프록시 구성에는 영향을 주지 않습니다.

ProxyMode 필드를 사용하면 Microsoft Edge Application Guard에서 사용되는 프록시 서버를 지정할 수 있습니다.

ProxyPacUrl 필드는 프록시 .pac 파일의 URL입니다.

ProxyServer 필드는 프록시 서버의 URL입니다.

'direct' 값을 'ProxyMode'로 선택하면 다른 모든 필드는 무시됩니다.

'auto_detect' 값을 'ProxyMode'로 선택하면 다른 모든 필드는 무시됩니다.

'fixed_servers' 값을 'ProxyMode'로 선택하면 'ProxyServer' 필드가 사용됩니다.

'pac_script' 값을 'ProxyMode'로 선택하면 'ProxyPacUrl' 필드가 사용됩니다.

이중 프록시를 통한 Application Guard 트래픽을 식별하는 방법에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2134653](https://go.microsoft.com/fwlink/?linkid=2134653)을 방문하세요.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - Dictionary

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ApplicationGuardContainerProxy
  - GP 이름: Application Guard 컨테이너 프록시
  - GP 경로(필수): 관리 템플릿/Microsoft Edge/Application Guard 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: ApplicationGuardContainerProxy
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\ApplicationGuardContainerProxy = {
  "ProxyMode": "direct", 
  "ProxyPacUrl": "https://internal.site/example.pac", 
  "ProxyServer": "123.123.123.123:8080"
}
```

  ##### <a name="compact-example-value"></a>예제 값 압축:

  ```
  SOFTWARE\Policies\Microsoft\Edge\ApplicationGuardContainerProxy = {"ProxyMode": "direct", "ProxyPacUrl": "https://internal.site/example.pac", "ProxyServer": "123.123.123.123:8080"}
  ```
  

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="applicationguardfavoritessyncenabled"></a>ApplicationGuardFavoritesSyncEnabled

  #### <a name="application-guard-favorites-sync-enabled"></a>응용 프로그램 보호 즐겨찾기 동기화 사용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 90 이상

  #### <a name="description"></a>설명

  이 정책을 사용하면 응용 프로그램 보호가 사용하도록 설정된 Microsoft Edge 컴퓨터/장치에서 호스트에서 컨테이너로 즐겨찾기 동기화를 허용합니다.

[ManagedFavorites](#managedfavorites)가 구성된 경우 해당 즐겨찾기도 컨테이너에 동기화됩니다.

이 정책을 사용하도록 설정한 경우 컨테이너에서 즐겨찾기 편집을 사용할 수 없습니다. 따라서 컨테이너 브라우저의 UI에서 즐겨찾기 추가 및 즐겨찾기 폴더 추가 단추가 흐리게 표시됩니다.

이 정책을 사용하지 않도록 설정하거나 구성하지 않은 경우 호스트의 즐겨찾기들이 컨테이너에 공유되지 않습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ApplicationGuardFavoritesSyncEnabled
  - GP 이름: Application Guard 즐겨찾기 동기화 사용
  - GP 경로(필수): 관리 템플릿/Microsoft Edge/Application Guard 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로(권장): 해당 없음
  - 값 이름: ApplicationGuardFavoritesSyncEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ## <a name="cast-policies"></a>캐스트 정책

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="enablemediarouter"></a>EnableMediaRouter

  #### <a name="enable-google-cast"></a>Google Cast 사용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  Google Cast를 사용하려면 해당 정책을 사용하도록 설정합니다. 사용자는 앱 메뉴, 페이지 상황에 맞는 메뉴, 캐스팅이 가능한 웹 사이트의 미디어 제어 및 캐스트 도구 모음 아이콘(표시된 경우)에서 해당 정책을 시작할 수 있습니다.

Google Cast를 사용 해제려면 해당 정책을 사용하지 않도록 설정합니다.

기본적으로 Google Cast는 사용하도록 설정되어 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: EnableMediaRouter
  - GP 이름: Google Cast 사용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/캐스트
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: EnableMediaRouter
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: EnableMediaRouter
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="showcasticonintoolbar"></a>ShowCastIconInToolbar

  #### <a name="show-the-cast-icon-in-the-toolbar"></a>도구 모음에 캐스트 아이콘 표시

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  도구 모음이나 오버플로 메뉴에서 캐스트 도구 모음 아이콘을 표시하려면 해당 정책을 True로 설정합니다. 사용자는 해당 정책을 제거할 수 없습니다.

해당 정책을 구성하지 않거나 사용하지 않도록 설정하면 사용자는 상황에 맞는 메뉴를 사용하여 아이콘을 고정하거나 제거할 수 있습니다.

[EnableMediaRouter](#enablemediarouter) 정책을 False로 설정한 경우에는 해당 정책이 무시되고 도구 모음 아이콘이 표시되지 않습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ShowCastIconInToolbar
  - GP 이름: 도구 모음에 캐스트 아이콘 표시
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/캐스트
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: ShowCastIconInToolbar
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ShowCastIconInToolbar
  - 예를 들어 값:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ## <a name="content-settings-policies"></a>콘텐츠 설정 정책

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="autoselectcertificateforurls"></a>Autoselectcertificateurl

  #### <a name="automatically-select-client-certificates-for-these-sites"></a>해당 사이트의 클라이언트 인증서를 자동으로 선택

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  정책을 설정하면 Microsoft Edge가 클라이언트 인증서를 자동으로 선택할 수 있는 사이트를 지정하는 URL 패턴 목록을 만들 수 있습니다. 그 값은 문자열화된 JSON 사전의 배열로서 각각 {"패턴": "$URL _PATTERN", "필터": $FILTER} 형식을 가지고 있으며 여기서 $URL _PATTERN은 콘텐츠 설정 패턴입니다. $FILTER는 브라우저에서 자동으로 선택하는 클라이언트 인증서를 제한합니다. 필터와 무관하게 서버의 인증서 요청과 일치하는 인증서만 선택됩니다.

$FILTER 구역 사용법에 대한 예시입니다.

* $FILTER가 { "발급자": {"CN": "$ISSUER _CN"} }으로 설정된 경우, CommonName $ISSUER _CN을 통해 인증서로 발급된 클라이언트 인증서만이 선택됩니다.

* $FILTER에 "발급자"와 "제목" 섹션이 모두 있는 경우 두 조건을 모두 만족하는 클라이언트 인증서만 선택됩니다.

* $FILTER에 "O" 값이 포함된 "제목" 섹션이 포함된 경우 인증서가 선택되려면 지정된 값과 일치하는 최소 한 개의 조직이 필요합니다.

* $FILTER에 "OU" 값이 있는 "제목" 섹션이 포함된 경우 인증서가 선택되려면 지정된 값과 일치하는 최소 한 개의 조직의 단위가 필요합니다.

* $FILTER가 {}로 설정된 경우 클라이언트 인증서의 선택은 추가적으로 제한되지 않습니다. 웹 서버에서 제공하는 필터는 계속 적용됨에 유의합니다.

정책을 설정하지 않은 상태로 두면 모든 사이트에 대한 autoselection이 없습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: AutoSelectCertificateForUrls
  - GP 이름: 해당 사이트의 클라이언트 인증서를 자동으로 선택
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/콘텐츠 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\AutoSelectCertificateForUrls
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\AutoSelectCertificateForUrls\1 = "{\"pattern\":\"https://www.contoso.com\",\"filter\":{\"ISSUER\":{\"CN\":\"certificate issuer name\", \"L\": \"certificate issuer location\", \"O\": \"certificate issuer org\", \"OU\": \"certificate issuer org unit\"}, \"SUBJECT\":{\"CN\":\"certificate subject name\", \"L\": \"certificate subject location\", \"O\": \"certificate subject org\", \"OU\": \"certificate subject org unit\"}}}"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: AutoSelectCertificateForUrls
  - 예를 들어 값:
``` xml
<array>
  <string>{"pattern":"https://www.contoso.com","filter":{"ISSUER":{"CN":"certificate issuer name", "L": "certificate issuer location", "O": "certificate issuer org", "OU": "certificate issuer org unit"}, "SUBJECT":{"CN":"certificate subject name", "L": "certificate subject location", "O": "certificate subject org", "OU": "certificate subject org unit"}}}</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="cookiesallowedforurls"></a>CookiesAllowedForUrls

  #### <a name="allow-cookies-on-specific-sites"></a>특정 사이트에서 쿠키 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  쿠키를 설정하기 위해 허용되는 URL 패턴을 기반으로 사이트 목록을 정의합니다.

해당 정책을 구성하지 않으면 [DefaultCookiesSetting](#defaultcookiessetting) 정책(설정된 경우) 또는 사용자의 개인 구성의 전역 기본 값이 모든 사이트에 대해 사용됩니다.

자세한 내용은 [CookiesBlockedForUrls](#cookiesblockedforurls) 및 [CookiesSessionOnlyForUrls](#cookiessessiononlyforurls) 정책을 참조하세요.

다음 세 가지 정책 사이에 URL 패턴 설정이 충돌할 수 없다는 점에 유의하세요.

- [CookiesBlockedForUrls](#cookiesblockedforurls)

- CookiesAllowedForUrls

- [CookiesSessionOnlyForUrls](#cookiessessiononlyforurls)

유효한 url 패턴에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)을(를) 참조하세요. 별표*는 해당 정책에 허용되는 값이 아닙니다.

쿠키가 작업 종료 시 삭제되지 않도록 하려면 [SaveCookiesOnExit](#savecookiesonexit) 정책을 구성합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: CookiesAllowedForUrls
  - GP 이름: 특정 사이트에서 쿠키 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/콘텐츠 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\CookiesAllowedForUrls
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\CookiesAllowedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\CookiesAllowedForUrls\2 = "[*.]contoso.edu"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: CookiesAllowedForUrls
  - 예를 들어 값:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="cookiesblockedforurls"></a>CookiesBlockedForUrls

  #### <a name="block-cookies-on-specific-sites"></a>특정 사이트에서 쿠키 차단

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  쿠키를 설정할 수 없는 URL 패턴을 기반으로 사이트 목록을 정의합니다.

해당 정책을 구성하지 않으면 [DefaultCookiesSetting](#defaultcookiessetting) 정책(설정된 경우) 또는 사용자의 개인 구성의 전역 기본 값이 모든 사이트에 대해 사용됩니다.

자세한 내용은 [CookiesAllowedForUrls](#cookiesallowedforurls) 및 [CookiesSessionOnlyForUrls](#cookiessessiononlyforurls) 정책을 참조하세요.

다음 세 가지 정책 사이에 URL 패턴 설정이 충돌할 수 없다는 점에 유의하세요.

- CookiesBlockedForUrls

- [CookiesAllowedForUrls](#cookiesallowedforurls)

- [CookiesSessionOnlyForUrls](#cookiessessiononlyforurls)

유효한 URL 패턴에 관한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)을(를) 참조하세요. 별표*는 해당 정책에 허용되는 값이 아닙니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: CookiesBlockedForUrls
  - GP 이름: 특정 사이트에서 쿠키 차단
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/콘텐츠 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\CookiesBlockedForUrls
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\CookiesBlockedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\CookiesBlockedForUrls\2 = "[*.]contoso.edu"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: CookiesBlockedForUrls
  - 예를 들어 값:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="cookiessessiononlyforurls"></a>CookiesSessionOnlyForUrls

  #### <a name="limit-cookies-from-specific-websites-to-the-current-session"></a>특정 웹 사이트의 쿠키를 현재 세션으로 제한

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  사용자가 정의한 URL 패턴과 일치하는 웹 사이트로 인해 생성된 쿠키는 세션이 종료되면 (창이 닫히는 경우) 삭제됩니다.

패턴과 일치하지 않는 웹 사이트에서 생성된 쿠키는 [DefaultCookiesSetting](#defaultcookiessetting) 정책 (설정된 경우) 또는 사용자의 개인 구성에 의해 제어됩니다. 해당 정책을 구성하지 않는 경우에도 기본 동작이 됩니다.

Microsoft Edge가 배경 모드에서 실행되고 있는 경우 마지막 창이 닫힐 때 세션이 종료되지 않을 수 있습니다. 즉, 창을 닫을 때 쿠키가 지워지지 않습니다. Microsoft Edge를 배경 모드로 실행하는 경우 수행되는 작업을 구성하는 방법에 대한 자세한 내용은 [BackgroundModeEnabled](#backgroundmodeenabled) 정책을 참조하세요.

[CookiesAllowedForUrls](#cookiesallowedforurls) 및 [CookiesBlockedForUrls](#cookiesblockedforurls) 정책을 사용하여 쿠키를 만들 수 있는 웹 사이트를 제어할 수도 있습니다.

다음 세 가지 정책 사이에 URL 패턴 설정이 충돌할 수 없다는 점에 유의하세요.

- [CookiesBlockedForUrls](#cookiesblockedforurls)

- [CookiesAllowedForUrls](#cookiesallowedforurls)

- CookiesSessionOnlyForUrls

유효한 URL 패턴에 관한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)을(를) 참조하세요. 별표*는 해당 정책에 허용되는 값이 아닙니다.

[RestoreOnStartup](#restoreonstartup) 정책을 설정하여 이전 세션에서 URL을 복원하는 경우 해당 정책은 무시되고 쿠키는 해당 사이트에 대해 영구적으로 저장됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: CookiesSessionOnlyForUrls
  - GP 이름: 특정 웹 사이트의 쿠키를 현재 세션으로 제한
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/콘텐츠 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\CookiesSessionOnlyForUrls
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\CookiesSessionOnlyForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\CookiesSessionOnlyForUrls\2 = "[*.]contoso.edu"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: CookiesSessionOnlyForUrls
  - 예를 들어 값:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="defaultcookiessetting"></a>DefaultCookiesSetting

  #### <a name="configure-cookies"></a>쿠키 구성

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  웹 사이트에서 사용자의 장치에 쿠키를 생성할 수 있는지 여부를 제어합니다. 해당 정책 모두 또는 없음 - 모든 웹 사이트에서 쿠키를 생성하거나 생성하지 않도록 허용할 수 있습니다. 해당 정책을 사용하여 특정 웹 사이트의 쿠키를 사용하도록 설정할 수 없습니다.

세션 종료 시 쿠키를 삭제하려면 해당 정책을 'SessionOnly'로 설정합니다. Microsoft Edge가 배경 모드에서 실행되고 있는 경우 마지막 창이 닫힐 때 세션이 종료되지 않을 수 있습니다. 즉, 창을 닫을 때 쿠키가 지워지지 않습니다. Microsoft Edge를 배경 모드로 실행하는 경우 수행되는 작업을 구성하는 방법에 대한 자세한 내용은 [BackgroundModeEnabled](#backgroundmodeenabled) 정책을 참조하세요.

해당 정책을 구성하지 않으면 기본적으로 'AllowCookies'이 사용되고 사용자는 Microsoft Edge 설정에서 해당 설정을 변경할 수 있습니다. (사용자가 해당 설정을 변경할 수 없게 하려면 정책을 설정합니다.)

정책 옵션 매핑:

* AllowCookies (1) = 모든 사이트에서 쿠키 생성 허용

* BlockCookies (2) = 모든 사이트에서 쿠키 생성 허용 안 함

* SessionOnly (4) = [SaveCookiesOnExit](#savecookiesonexit)에 나열된 항목을 제외하고 세션 기간 동안 쿠키를 유지

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: DefaultCookiesSetting
  - GP 이름: 쿠키 구성
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/콘텐츠 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: DefaultCookiesSetting
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: DefaultCookiesSetting
  - 예를 들어 값:
``` xml
<integer>1</integer>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="defaultfilesystemreadguardsetting"></a>DefaultFileSystemReadGuardSetting

  #### <a name="control-use-of-the-file-system-api-for-reading"></a>읽기를 위해 파일 시스템 API 사용 제어

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (86 이상)

  #### <a name="description"></a>설명

  이 정책을 3으로 설정하면 웹 사이트에서 파일 시스템 API를 사용하여 호스트 운영 체제의 파일 시스템에 대한 읽기 액세스를 요청할 수 있습니다. 이 정책을 2로 설정하면 액세스가 거부됩니다.

이 정책을 설정하지 않으면 웹 사이트에서 액세스를 요청할 수 있습니다. 사용자는 이 설정을 변경할 수 있습니다.

정책 옵션 매핑:

* BlockFileSystemRead (2) = 어떤 사이트도 파일 시스템 API를 통해 파일 및 디렉토리에 대한 읽기 액세스를 요청하도록 허용하지 않습니다.

* AskFileSystemRead (3) = 사이트에서 파일 시스템 API를 통해 파일 및 디렉토리에 대한 읽기 액세스 권한을 사용자에게 요청하도록 허용합니다.

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: DefaultFileSystemReadGuardSetting
  - GP 이름: 읽기를 위해 파일 시스템 API 사용 제어
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/콘텐츠 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: DefaultFileSystemReadGuardSetting
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000002
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: DefaultFileSystemReadGuardSetting
  - 예를 들어 값:
``` xml
<integer>2</integer>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="defaultfilesystemwriteguardsetting"></a>DefaultFileSystemWriteGuardSetting

  #### <a name="control-use-of-the-file-system-api-for-writing"></a>쓰기를 위해 파일 시스템 API 사용 제어

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (86 이상)

  #### <a name="description"></a>설명

  이 정책을 3으로 설정하면 웹 사이트에서 파일 시스템 API를 사용하여 호스트 운영 체제의 파일 시스템에 대한 쓰기 액세스를 요청할 수 있습니다. 이 정책을 2로 설정하면 액세스가 거부됩니다.

이 정책을 설정하지 않으면 웹 사이트에서 액세스를 요청할 수 있습니다. 사용자는 이 설정을 변경할 수 있습니다.

정책 옵션 매핑:

* BlockFileSystemWrite (2) = 어떤 사이트도 파일 및 디렉토리에 대한 쓰기 권한을 요청하도록 허용하지 않습니다.

* AskFileSystemWrite (3) = 사이트에서 사용자에게 파일 및 디렉터리에 대한 쓰기 액세스 권한을 요청하도록 허용합니다.

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: DefaultFileSystemWriteGuardSetting
  - GP 이름: 쓰기를 위해 파일 시스템 API 사용 제어
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/콘텐츠 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: DefaultFileSystemWriteGuardSetting
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000002
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: DefaultFileSystemWriteGuardSetting
  - 예를 들어 값:
``` xml
<integer>2</integer>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="defaultgeolocationsetting"></a>DefaultGeolocationSetting

  #### <a name="default-geolocation-setting"></a>기본 지리적 위치 설정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  웹 사이트에서 사용자의 실제 위치를 추적할 수 있는지 여부를 설정합니다. 기본적으로 추적을 허용('AllowGeolocation')하거나 기본적으로 추적을 거부('BlockGeolocation')하거나 웹 사이트에서 위치를 요청할 때마다 사용자에게 추적을 요청('AskGeolocation')하도록 할 수 있습니다.

해당 정책을 구성하지 않으면 'AskGeolocation'이 사용되고 사용자는 해당 설정을 변경할 수 있습니다.

정책 옵션 매핑:

* AllowGeolocation (1) = 사이트에서 사용자의 실제 위치를 추적하도록 허용

* BlockGeolocation (2) = 모든 사이트에서 사용자의 실제 위치를 추적하도록 허용 안 함

* AskGeolocation (3) = 사이트에서 사용자의 실제 위치를 추적하려고 할 때마다 확인

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: DefaultGeolocationSetting
  - GP 이름: 기본 지리적 위치 설정
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/콘텐츠 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: DefaultGeolocationSetting
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: DefaultGeolocationSetting
  - 예를 들어 값:
``` xml
<integer>1</integer>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="defaultimagessetting"></a>DefaultImagesSetting

  #### <a name="default-images-setting"></a>기본 이미지 설정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  웹 사이트에서 이미지를 표시할 수 있는지 여부를 설정합니다. 모든 사이트에서 이미지를 허용('AllowImages')하거나 모든 사이트에서 이미지를 차단('BlockImages')할 수 있습니다.

해당 정책을 구성하지 않으면 기본적으로 이미지가 표시되도록 허용되며 사용자는 해당 설정을 변경할 수 있습니다.

정책 옵션 매핑:

* AllowImages (1) = 모든 사이트에서 모든 이미지를 표시하도록 허용

* BlockImages (2) = 모든 사이트에서 이미지를 표시하도록 허용 안 함

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: DefaultImagesSetting
  - GP 이름: 기본 이미지 설정
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/콘텐츠 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: DefaultImagesSetting
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: DefaultImagesSetting
  - 예를 들어 값:
``` xml
<integer>1</integer>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="defaultinsecurecontentsetting"></a>DefaultInsecureContentSetting

  #### <a name="control-use-of-insecure-content-exceptions"></a>비보안 콘텐츠 예외를 사용하여 제어

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (80 이상)

  #### <a name="description"></a>설명

  사용자가 예외를 추가하여 특정 사이트에 대해 혼합 콘텐츠를 허용할 수 있는지 여부를 설정할 수 있습니다.

해당 정책은 [InsecureContentAllowedForUrls](#insecurecontentallowedforurls) 및 [InsecureContentBlockedForUrls](#insecurecontentblockedforurls) 정책을 사용하여 특정 URL 패턴에 대해 재정의될 수 있습니다.

해당 정책을 설정하지 않은 경우 사용자는 예외를 추가하여 차단할 수 있는 혼합 콘텐츠를 허용할 수 있고 선택적으로 차단할 수 있는 혼합 콘텐츠에 대해 자동 업그레이드를 해제할 수 있습니다.

정책 옵션 매핑:

* BlockInsecureContent (2) = 모든 사이트에서 혼합 콘텐츠를 불러오도록 허용 안 함

* AllowExceptionsInsecureContent (3) = 사용자가 혼합 콘텐츠를 허용하는 예외를 추가하도록 허용

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: DefaultInsecureContentSetting
  - GP 이름: 비보안 콘텐츠 예외를 사용하여 제어
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/콘텐츠 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: DefaultInsecureContentSetting
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000002
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: DefaultInsecureContentSetting
  - 예를 들어 값:
``` xml
<integer>2</integer>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="defaultjavascriptsetting"></a>DefaultJavaScriptSetting

  #### <a name="default-javascript-setting"></a>기본 JavaScript 설정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  웹 사이트에서 JavaScript를 실행할 수 있는지 여부를 설정합니다. 모든 사이트에 대해 허용(’AllowJavaScript')하거나 모든 사이트에 대해 차단('BlockJavaScript')할 수 있습니다.

해당 정책을 구성하지 않으면 기본적으로 모든 사이트에서 JavaScript를 실행할 수 있고 사용자는 해당 설정을 변경할 수 있습니다.

정책 옵션 매핑:

* AllowJavaScript (1) = 모든 사이트에서 JavaScript 실행 허용

* BlockJavaScript (2) = 모든 사이트에서 JavaScript 실행 허용 안 함

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: DefaultJavaScriptSetting
  - GP 이름: 기본 JavaScript 설정
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/콘텐츠 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: DefaultJavaScriptSetting
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: DefaultJavaScriptSetting
  - 예를 들어 값:
``` xml
<integer>1</integer>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="defaultnotificationssetting"></a>DefaultNotificationsSetting

  #### <a name="default-notification-setting"></a>기본 알림 설정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  웹 사이트에서 바탕 화면 알림을 표시할 수 있는지 여부를 설정합니다. 기본적으로 알림 표시를 허용('AllowNotifications')하거나 기본적으로 알림 표시를 거부('BlockNotifications')하거나 웹 사이트에서 알림을 표시하려고 할 때마다 사용자에게 요청('AskNotifications')하도록 할 수 있습니다.

해당 정책을 구성하지 않으면 기본적으로 알림이 표시되도록 허용되며 사용자는 해당 설정을 변경할 수 있습니다.

정책 옵션 매핑:

* AllowNotifications (1) = 사이트에서 바탕 화면 알림을 표시하도록 허용

* BlockNotifications (2) = 모든 사이트에서 바탕 화면 알림을 표시하도록 허용 안 함

* AskNotifications (3) = 사이트에서 바탕 화면 알림을 표시하려고 할 때마다 확인

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: DefaultNotificationsSetting
  - GP 이름: 기본 알림 설정
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/콘텐츠 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: DefaultNotificationsSetting
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000002
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: DefaultNotificationsSetting
  - 예를 들어 값:
``` xml
<integer>2</integer>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="defaultpluginssetting"></a>DefaultPluginsSetting

  #### <a name="default-adobe-flash-setting-obsolete"></a>기본 Adobe Flash 설정(obsolete)

  
  >OBSOLETE: 이 정책은 더 이상 사용되지 않으며 Microsoft Edge 87 이후에는 작동하지 않습니다.
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 macOS(77부터 87까지)

  #### <a name="description"></a>설명

  Flash가 Microsoft Edge에서 더 이상 지원되지 않으므로 이 정책이 적용되지 않습니다.

[PluginsAllowedForUrls](#pluginsallowedforurls) 및 [PluginsBlockedForUrls](#pluginsblockedforurls)를 먼저 확인한 다음 이 정책을 확인합니다. 옵션은 'ClickToPlay' 및 'BlockPlugins' 입니다. 이 정책을 ' BlockPlugins '로 설정하면 이 플러그 인은 모든 웹 사이트에서 거부됩니다. 'ClickToPlay'를 사용하면 Flash 플러그 인이 실행되지만 사용자는 자리 표시자를 클릭하여 시작합니다.

해당 정책을 구성하지 않으면 사용자는 해당 설정을 수동으로 변경할 수 있습니다.

참고: 자동 재생은 [PluginsAllowedForUrls](#pluginsallowedforurls) 정책에 명시적으로 나열된 도메인에만 적용됩니다. 모든 사이트에 대해 자동 재생을 켜려면 허용된 URL 목록에 http://* 및 https://*를 추가합니다.

정책 옵션 매핑:

* BlockPlugins (2) = Adobe Flash 플러그인 차단

* ClickToPlay (3) = 재생하려면 클릭

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: DefaultPluginsSetting
  - GP 이름: 기본 Adobe Flash 설정(obsolete)
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/콘텐츠 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: DefaultPluginsSetting
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000002
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: DefaultPluginsSetting
  - 예를 들어 값:
``` xml
<integer>2</integer>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="defaultpopupssetting"></a>DefaultPopupsSetting

  #### <a name="default-pop-up-window-setting"></a>기본 팝업 창 설정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  웹 사이트에서 팝업 창을 표시할 수 있는지 여부를 설정합니다. 모든 웹 사이트에서 팝업 창을 허용('AllowPopups')하거나 모든 사이트에서 팝업 창을 차단('BlockPopups')할 수 있습니다.

해당 정책을 구성하지 않으면 기본적으로 팝업 창이 차단되며 사용자는 해당 설정을 변경할 수 있습니다.

정책 옵션 매핑:

* AllowPopups (1) = 모든 사이트에서 팝업 창을 표시하도록 허용

* BlockPopups (2) = 모든 사이트에서 팝업을 표시하도록 허용 안 함

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: DefaultPopupsSetting
  - GP 이름: 기본 팝업 창 설정
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/콘텐츠 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: DefaultPopupsSetting
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: DefaultPopupsSetting
  - 예를 들어 값:
``` xml
<integer>1</integer>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="defaultwebbluetoothguardsetting"></a>DefaultWebBluetoothGuardSetting

  #### <a name="control-use-of-the-web-bluetooth-api"></a>웹 블루투스 API의 사용 제어

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  웹 사이트에서 가까운 블루투스 장치에 액세스할 수 있는지 여부를 제어합니다. 액세스를 완벽하게 차단하거나 사이트에서 블루투스 장치에 액세스하려고 할 때마다 사용자에게 요청하도록 할 수 있습니다.

해당 정책을 구성하지 않으면 기본값('AskWebBluetooth', 매번 사용자에게 요청함을 의미)이 사용되고 사용자는 해당 설정을 변경할 수 있습니다.

정책 옵션 매핑:

* BlockWebBluetooth (2) = 모든 사이트에서 웹 블루투스 API를 통해 Bluetooth 장치에 대한 액세스를 요청하도록 허용 안 함

* AskWebBluetooth (3) = 사이트에서 가까운 Bluetooth 장치에 대한 액세스 권한 부여를 사용자에게 요청하도록 허용

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: DefaultWebBluetoothGuardSetting
  - GP 이름: 웹 블루투스 API의 사용 제어
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/콘텐츠 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: DefaultWebBluetoothGuardSetting
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000002
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: DefaultWebBluetoothGuardSetting
  - 예를 들어 값:
``` xml
<integer>2</integer>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="defaultwebusbguardsetting"></a>DefaultWebUsbGuardSetting

  #### <a name="control-use-of-the-webusb-api"></a>WebUSB API의 사용 제어

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  웹 사이트에서 연결된 USB 장치에 액세스할 수 있는지 여부를 설정합니다. 액세스를 완벽하게 차단하거나 웹 사이트에서 연결된 USB 장치에 액세스하려고 할 때마다 사용자에게 요청할 수 있습니다.

[WebUsbAskForUrls](#webusbaskforurls) 및 [WebUsbBlockedForUrls](#webusbblockedforurls) 정책을 사용하여 특정 URL 패턴에 대해 해당 정책을 재정의할 수 있습니다.

해당 정책을 구성하지 않으면 사이트에서 사용자에게 연결된 USB 장치에 기본적으로 액세스할 수 있는지('AskWebUsb') 여부를 요청할 수 있으며 사용자는 해당 설정을 변경할 수 있습니다.

정책 옵션 매핑:

* BlockWebUsb (2) = 모든 사이트에서 WebUSB API를 통해 USB 장치에 대한 액세스를 요청하도록 허용 안 함

* AskWebUsb (3) = 사이트에서 연결된 USB 장치에 대한 액세스 권한 부여를 사용자에게 요청하도록 허용

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: DefaultWebUsbGuardSetting
  - GP 이름: WebUSB API의 사용 제어
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/콘텐츠 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: DefaultWebUsbGuardSetting
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000002
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: DefaultWebUsbGuardSetting
  - 예를 들어 값:
``` xml
<integer>2</integer>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="filesystemreadaskforurls"></a>FileSystemReadAskForUrls

  #### <a name="allow-read-access-via-the-file-system-api-on-these-sites"></a>해당 사이트에서 파일 시스템 API를 통해 읽기 권한 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (86 이상)

  #### <a name="description"></a>설명

  정책을 설정하면 파일 시스템 API를 통해 호스트 운영 체제의 파일 시스템에 있는 파일 또는 디렉토리에 대한 읽기 액세스 권한을 사용자에게 부여하도록 요청할 수 있는 사이트를 지정하는 URL 패턴을 나열할 수 있습니다.

정책을 설정하지 않으면 [DefaultFileSystemReadGuardSetting](#defaultfilesystemreadguardsetting)가 설정된 경우 모든 사이트에 적용됩니다. 그렇지 않은 경우에는 사용자의 개인 설정이 적용됩니다.

URL 패턴은 [FileSystemReadBlockedForUrls](#filesystemreadblockedforurls)과 충돌할 수 없습니다. URL이 두 가지 모두와 일치하는 경우 두 가지 정책 모두 우선권이 없습니다.

유효한 URL 패턴에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)을(를) 참조하세요. 별표*는 해당 정책에 허용되는 값이 아닙니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: FileSystemReadAskForUrls
  - GP 이름: 해당 사이트에서 파일 시스템 API를 통해 읽기 권한 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/콘텐츠 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로(필수): SOFTWARE\Policies\Microsoft\Edge\FileSystemReadAskForUrls
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\FileSystemReadAskForUrls\1 = "https://www.example.com"
SOFTWARE\Policies\Microsoft\Edge\FileSystemReadAskForUrls\2 = "[*.]example.edu"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: FileSystemReadAskForUrls
  - 예를 들어 값:
``` xml
<array>
  <string>https://www.example.com</string>
  <string>[*.]example.edu</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="filesystemreadblockedforurls"></a>FileSystemReadBlockedForUrls

  #### <a name="block-read-access-via-the-file-system-api-on-these-sites"></a>해당 사이트에서 파일 시스템 API를 통해 읽기 권한 차단

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (86 이상)

  #### <a name="description"></a>설명

  정책을 설정하면 파일 시스템 API를 통해 호스트 운영 체제의 파일 시스템에 있는 파일 또는 디렉토리에 대한 읽기 액세스 권한을 사용자에게 부여하도록 요청할 수 있는 사이트를 지정하는 URL 패턴을 나열할 수 있습니다.

정책을 설정하지 않으면 [DefaultFileSystemReadGuardSetting](#defaultfilesystemreadguardsetting)가 설정된 경우 모든 사이트에 적용됩니다. 그렇지 않은 경우에는 사용자의 개인 설정이 적용됩니다.

URL 패턴은 [FileSystemReadAskForUrls](#filesystemreadaskforurls)과 충돌할 수 없습니다. URL이 두 가지 모두와 일치하는 경우 두 가지 정책 모두 우선권이 없습니다.

유효한 URL 패턴에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)을(를) 참조하세요. 별표*는 해당 정책에 허용되는 값이 아닙니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: FileSystemReadBlockedForUrls
  - GP 이름: 해당 사이트에서 파일 시스템 API를 통해 읽기 권한 차단
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/콘텐츠 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\Policies\Microsoft\Edge\FileSystemReadBlockedForUrls
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\FileSystemReadBlockedForUrls\1 = "https://www.example.com"
SOFTWARE\Policies\Microsoft\Edge\FileSystemReadBlockedForUrls\2 = "[*.]example.edu"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: FileSystemReadBlockedForUrls
  - 예를 들어 값:
``` xml
<array>
  <string>https://www.example.com</string>
  <string>[*.]example.edu</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="filesystemwriteaskforurls"></a>FileSystemWriteAskForUrls

  #### <a name="allow-write-access-to-files-and-directories-on-these-sites"></a>이 사이트에서 파일 및 디렉터리에 대한 쓰기 액세스 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (86 이상)

  #### <a name="description"></a>설명

  정책을 설정하면 호스트 운영 체제의 파일 시스템에 있는 파일 또는 디렉토리에 대한 읽기 액세스 권한을 사용자에게 부여하도록 요청할 수 있는 사이트를 지정하는 URL 패턴을 나열할 수 있습니다.

정책을 설정하지 않으면 [DefaultFileSystemWriteGuardSetting](#defaultfilesystemwriteguardsetting)가 설정된 경우 모든 사이트에 적용됩니다. 그렇지 않은 경우에는 사용자의 개인 설정이 적용됩니다.

URL 패턴은 [FileSystemWriteBlockedForUrls](#filesystemwriteblockedforurls)과 충돌할 수 없습니다. URL이 두 가지 모두와 일치하는 경우 두 가지 정책 모두 우선권이 없습니다.

유효한 URL 패턴에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)을(를) 참조하세요. 별표*는 해당 정책에 허용되는 값이 아닙니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: FileSystemWriteAskForUrls
  - GP 이름: 이 사이트에서 파일 및 디렉터리에 대한 쓰기 액세스 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/콘텐츠 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\Policies\Microsoft\Edge\FileSystemWriteAskForUrls
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\FileSystemWriteAskForUrls\1 = "https://www.example.com"
SOFTWARE\Policies\Microsoft\Edge\FileSystemWriteAskForUrls\2 = "[*.]example.edu"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: FileSystemWriteAskForUrls
  - 예를 들어 값:
``` xml
<array>
  <string>https://www.example.com</string>
  <string>[*.]example.edu</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="filesystemwriteblockedforurls"></a>FileSystemWriteBlockedForUrls

  #### <a name="block-write-access-to-files-and-directories-on-these-sites"></a>이 사이트에서 파일 및 디렉터리에 대한 쓰기 액세스 차단

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (86 이상)

  #### <a name="description"></a>설명

  정책을 설정하면 호스트 운영 체제의 파일 시스템에 있는 파일 또는 디렉토리에 대한 읽기 액세스 권한을 사용자에게 부여하도록 요청할 수 있는 사이트를 지정하는 URL 패턴을 나열할 수 있습니다.

정책을 설정하지 않으면 [DefaultFileSystemWriteGuardSetting](#defaultfilesystemwriteguardsetting)가 설정된 경우 모든 사이트에 적용됩니다. 그렇지 않은 경우에는 사용자의 개인 설정이 적용됩니다.

URL 패턴은 [FileSystemWriteAskForUrls](#filesystemwriteaskforurls)과 충돌할 수 없습니다. URL이 두 가지 모두와 일치하는 경우 두 가지 정책 모두 우선권이 없습니다.

유효한 URL 패턴에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)을(를) 참조하세요. 별표*는 해당 정책에 허용되는 값이 아닙니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: FileSystemWriteBlockedForUrls
  - GP 이름: 이 사이트에서 파일 및 디렉터리에 대한 쓰기 액세스 차단
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/콘텐츠 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로(필수): SOFTWARE\Policies\Microsoft\Edge\FileSystemWriteBlockedForUrls
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\FileSystemWriteBlockedForUrls\1 = "https://www.example.com"
SOFTWARE\Policies\Microsoft\Edge\FileSystemWriteBlockedForUrls\2 = "[*.]example.edu"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: FileSystemWriteBlockedForUrls
  - 예를 들어 값:
``` xml
<array>
  <string>https://www.example.com</string>
  <string>[*.]example.edu</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="imagesallowedforurls"></a>ImagesAllowedForUrls

  #### <a name="allow-images-on-these-sites"></a>해당 사이트에서 이미지 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  이미지를 표시할 수 있는 URL 패턴을 기반으로 사이트 목록을 정의합니다.

해당 정책을 구성하지 않으면 [DefaultImagesSetting](#defaultimagessetting) 정책(설정된 경우) 또는 사용자의 개인 구성에서 모든 사이트에 대해 전역 기본 값이 사용됩니다.

유효한 URL 패턴에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)을(를) 참조하세요. 별표*는 해당 정책에 허용되는 값이 아닙니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ImagesAllowedForUrls
  - GP 이름: 해당 사이트에서 이미지 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/콘텐츠 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\ImagesAllowedForUrls
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\ImagesAllowedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\ImagesAllowedForUrls\2 = "[*.]contoso.edu"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ImagesAllowedForUrls
  - 예를 들어 값:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="imagesblockedforurls"></a>ImagesBlockedForUrls

  #### <a name="block-images-on-specific-sites"></a>특정 사이트에서 이미지 차단

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  이미지 표시를 허용하지 않는 URL 패턴을 기반으로 사이트 목록을 정의합니다.

해당 정책을 구성하지 않으면 [DefaultImagesSetting](#defaultimagessetting) 정책(설정된 경우) 또는 사용자의 개인 구성의 전역 기본 값이 모든 사이트에 대해 사용됩니다.

유효한 URL 패턴에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)을(를) 참조하세요. 별표*는 해당 정책에 허용되는 값이 아닙니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ImagesBlockedForUrls
  - GP 이름: 특정 사이트에서 이미지 차단
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/콘텐츠 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\ImagesBlockedForUrls
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\ImagesBlockedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\ImagesBlockedForUrls\2 = "[*.]contoso.edu"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ImagesBlockedForUrls
  - 예를 들어 값:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="insecurecontentallowedforurls"></a>InsecureContentAllowedForUrls

  #### <a name="allow-insecure-content-on-specified-sites"></a>지정된 사이트에서 비보안 콘텐츠 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (80 이상)

  #### <a name="description"></a>설명

  비보안 혼합 콘텐츠(HTTPS 사이트의 HTTP 콘텐츠)를 표시할 수 있는 사이트를 지정하는 URL 패턴 목록을 생성합니다.

해당 정책을 구성하지 않으면 차단할 수 있는 혼합 콘텐츠가 차단되고 선택적 차단할 수 있는 혼합 콘텐츠가 업그레이드됩니다. 그러나 사용자가 특정 사이트에 대해 비보안 혼합 콘텐츠를 허용하도록 예외를 설정할 수 있습니다.

유효한 URL 패턴에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)을(를) 참조하세요. 별표*는 해당 정책에 허용되는 값이 아닙니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: InsecureContentAllowedForUrls
  - GP 이름: 지정된 사이트에서 비보안 콘텐츠 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/콘텐츠 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\InsecureContentAllowedForUrls
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\InsecureContentAllowedForUrls\1 = "https://www.example.com"
SOFTWARE\Policies\Microsoft\Edge\InsecureContentAllowedForUrls\2 = "[*.]example.edu"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: InsecureContentAllowedForUrls
  - 예를 들어 값:
``` xml
<array>
  <string>https://www.example.com</string>
  <string>[*.]example.edu</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="insecurecontentblockedforurls"></a>InsecureContentBlockedForUrls

  #### <a name="block-insecure-content-on-specified-sites"></a>지정된 사이트에서 비보안 콘텐츠 차단

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (80 이상)

  #### <a name="description"></a>설명

  차단할 수 있는(예: 능동) 혼합 콘텐츠(즉, HTTPS 사이트의 HTTP 콘텐츠)의 표시를 허용하지 않으며 선택적 차단할 수 있는 혼합 콘텐츠의 업그레이드를 사용하지 않도록 설정하는 사이트를 지정하는 URL 패턴 목록을 생성합니다.

해당 정책을 구성하지 않으면 차단할 수 있는 혼합 콘텐츠가 차단되고 선택적 차단할 수 있는 혼합 콘텐츠가 업그레이드됩니다. 그러나 사용자가 특정 사이트에 대해 비보안 혼합 콘텐츠를 허용하도록 예외를 설정할 수 있습니다.

유효한 URL 패턴에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)을(를) 참조하세요. 별표*는 해당 정책에 허용되는 값이 아닙니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: InsecureContentBlockedForUrls
  - GP 이름: 지정된 사이트에서 비보안 콘텐츠 차단
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/콘텐츠 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\InsecureContentBlockedForUrls
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\InsecureContentBlockedForUrls\1 = "https://www.example.com"
SOFTWARE\Policies\Microsoft\Edge\InsecureContentBlockedForUrls\2 = "[*.]example.edu"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: InsecureContentBlockedForUrls
  - 예를 들어 값:
``` xml
<array>
  <string>https://www.example.com</string>
  <string>[*.]example.edu</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="javascriptallowedforurls"></a>JavaScriptAllowedForUrls

  #### <a name="allow-javascript-on-specific-sites"></a>특정 사이트에서 JavaScript 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  JavaScript를 실행하기 위해 허용되는 URL 패턴을 기반으로 사이트 목록을 정의합니다.

해당 정책을 구성하지 않으면 [DefaultJavaScriptSetting](#defaultjavascriptsetting) 정책(설정된 경우) 또는 사용자의 개인 구성의 전역 기본 값이 모든 사이트에 대해 사용됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: JavaScriptAllowedForUrls
  - GP 이름: 특정 사이트에서 JavaScript 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/콘텐츠 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\JavaScriptAllowedForUrls
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\JavaScriptAllowedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\JavaScriptAllowedForUrls\2 = "[*.]contoso.edu"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: JavaScriptAllowedForUrls
  - 예를 들어 값:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="javascriptblockedforurls"></a>JavaScriptBlockedForUrls

  #### <a name="block-javascript-on-specific-sites"></a>특정 사이트에서 JavaScript 차단

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  JavaScript의 실행이 허용되지 않는 URL 패턴을 기반으로 사이트 목록을 정의합니다.

해당 정책을 구성하지 않으면 [DefaultJavaScriptSetting](#defaultjavascriptsetting) 정책(설정된 경우) 또는 사용자의 개인 구성의 전역 기본 값이 모든 사이트에 대해 사용됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: JavaScriptBlockedForUrls
  - GP 이름: 특정 사이트에서 JavaScript 차단
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/콘텐츠 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\JavaScriptBlockedForUrls
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\JavaScriptBlockedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\JavaScriptBlockedForUrls\2 = "[*.]contoso.edu"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: JavaScriptBlockedForUrls
  - 예를 들어 값:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="legacysamesitecookiebehaviorenabled"></a>LegacySameSiteCookieBehaviorEnabled

  #### <a name="enable-default-legacy-samesite-cookie-behavior-setting"></a>기본 레거시 SameSite 쿠키 동작 설정 사용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (80 이상)

  #### <a name="description"></a>설명

  모든 쿠키를 레거시 SameSite 동작으로 되돌립니다. 레거시 동작으로 되돌리면 SameSite 특성을 지정하지 않은 쿠키가 "SameSite=없음"으로 간주되고, "SameSite=없음" 쿠키에 대한 요구 사항을 제거하여 "Secure" 특성을 전달하고 두 개의 사이트가 동일한지 평가 시 구성표 비교를 생략합니다.

이 정책을 설정하지 않은 경우, 쿠키에 대한 기본 SameSite 동작은 SameSite-by-default 기능, Cookies-without-SameSite-must-be-secure 기능 그리고 Schemeful Same-Site에 대한 기타 구성 원본에 따라 달라집니다. 이러한 기능은 또한 필드 트라이얼이나 edge://flags에 있는 same-site-by-default-cookies 플래그, cookies-without-same-site-must-be-secure 플래그 혹은 schemeful-same-site 플래그에 의해 구성될 수 있습니다.

정책 옵션 매핑:

* DefaultToLegacySameSiteCookieBehavior (1) = 모든 사이트의 쿠키에 대해 레거시 SameSite 동작으로 되돌림

* DefaultToSameSiteByDefaultCookieBehavior (2) = 모든 사이트의 쿠키에 대해 SameSite-by-default 동작 사용

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: LegacySameSiteCookieBehaviorEnabled
  - GP 이름: 기본 레거시 SameSite 쿠키 동작 설정 사용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/콘텐츠 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: LegacySameSiteCookieBehaviorEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: LegacySameSiteCookieBehaviorEnabled
  - 예를 들어 값:
``` xml
<integer>1</integer>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="legacysamesitecookiebehaviorenabledfordomainlist"></a>LegacySameSiteCookieBehaviorEnabledForDomainList

  #### <a name="revert-to-legacy-samesite-behavior-for-cookies-on-specified-sites"></a>지정된 사이트에서 쿠키에 대한 레거시 SameSite 동작으로 되돌리기

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (80 이상)

  #### <a name="description"></a>설명

  지정된 패턴과 일치하는 도메인에 대해 설정된 쿠키는 레거시 SameSite 동작으로 돌아갑니다.

레거시 동작으로 되돌리면 SameSite 특성을 지정하지 않은 쿠키가 "SameSite=없음"으로 간주되고, "SameSite=없음" 쿠키에 대한 요구 사항을 제거하여 "Secure" 특성을 전달하고 두 개의 사이트가 동일한지 평가 시 구성표 비교를 생략합니다.

해당 정책을 설정하지 않으면 전역 기본값이 사용됩니다. 전역 기본값은 사용자가 지정하는 패턴으로 다루지 않는 도메인의 쿠키에도 사용됩니다.

전역 기본값은 [LegacySameSiteCookieBehaviorEnabled](#legacysamesitecookiebehaviorenabled) 정책을 사용하여 구성할 수 있습니다. [LegacySameSiteCookieBehaviorEnabled](#legacysamesitecookiebehaviorenabled)를 설정하지 않은 경우 전역 기본값은 다른 구성 소스로 돌아갑니다.

해당 정책에서 사용자가 나열하는 패턴은 URL이 아니라 도메인으로 취급되므로 구성표 또는 포트를 지정할 수 없다는 점에 유의하세요.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: LegacySameSiteCookieBehaviorEnabledForDomainList
  - GP 이름: 지정된 사이트에서 쿠키에 대한 레거시 SameSite 동작으로 되돌리기
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/콘텐츠 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\LegacySameSiteCookieBehaviorEnabledForDomainList
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\LegacySameSiteCookieBehaviorEnabledForDomainList\1 = "www.example.com"
SOFTWARE\Policies\Microsoft\Edge\LegacySameSiteCookieBehaviorEnabledForDomainList\2 = "[*.]example.edu"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: LegacySameSiteCookieBehaviorEnabledForDomainList
  - 예를 들어 값:
``` xml
<array>
  <string>www.example.com</string>
  <string>[*.]example.edu</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="notificationsallowedforurls"></a>NotificationsAllowedForUrls

  #### <a name="allow-notifications-on-specific-sites"></a>특정 사이트에서 알림 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  알림을 표시할 수 있는 사이트를 지정하는 URL 패턴 목록을 만들 수 있습니다.

해당 정책을 설정하지 않으면 전역 기본값이 모든 사이트에 사용됩니다. 이 기본값은 설정한 경우 [DefaultNotificationsSetting](#defaultnotificationssetting) 정책에서 가져오고, 설정하지 않으면 사용자의 개인 구성에서 가져옵니다. 유효한 URL 패턴에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)을(를) 참조하세요.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: NotificationsAllowedForUrls
  - GP 이름: 특정 사이트에서 알림 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/콘텐츠 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\NotificationsAllowedForUrls
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\NotificationsAllowedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\NotificationsAllowedForUrls\2 = "[*.]contoso.edu"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: NotificationsAllowedForUrls
  - 예를 들어 값:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="notificationsblockedforurls"></a>NotificationsBlockedForUrls

  #### <a name="block-notifications-on-specific-sites"></a>특정 사이트에서 알림 차단

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  알림을 표시할 수 없는 사이트를 지정하는 URL 패턴 목록을 만들 수 있습니다.

해당 정책을 설정하지 않으면 전역 기본값이 모든 사이트에 사용됩니다. 이 기본값은 설정한 경우 [DefaultNotificationsSetting](#defaultnotificationssetting) 정책에서 가져오고, 설정하지 않으면 사용자의 개인 구성에서 가져옵니다. 유효한 URL 패턴에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)을(를) 참조하세요.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: NotificationsBlockedForUrls
  - GP 이름: 특정 사이트에서 알림 차단
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/콘텐츠 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\NotificationsBlockedForUrls
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\NotificationsBlockedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\NotificationsBlockedForUrls\2 = "[*.]contoso.edu"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: NotificationsBlockedForUrls
  - 예를 들어 값:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="pluginsallowedforurls"></a>PluginsAllowedForUrls

  #### <a name="allow-the-adobe-flash-plug-in-on-specific-sites-obsolete"></a>특정 사이트에서 Adobe Flash 플러그인 허용(obsolete)

  
  >OBSOLETE: 이 정책은 더 이상 사용되지 않으며 Microsoft Edge 87 이후에는 작동하지 않습니다.
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 macOS(77부터 87까지)

  #### <a name="description"></a>설명

  Flash가 Microsoft Edge에서 더 이상 지원되지 않으므로 이 정책이 적용되지 않습니다.

Adobe Flash 플러그인을 실행할 수 있는 URL 패턴을 기반으로 사이트 목록을 정의합니다.

해당 정책을 구성하지 않으면 [DefaultPluginsSetting](#defaultpluginssetting) 정책(설정된 경우) 또는 사용자의 개인 구성의 전역 기본 값이 모든 사이트에 대해 사용됩니다.

유효한 URL 패턴에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)을(를) 참조하세요. 그러나, M85로 시작하는 호스트 내의 '\*' 및 '[\*.]' 와일드카드 패턴은 이 정책에서 더 이상 지원되지 않습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: PluginsAllowedForUrls
  - GP 이름: 특정 사이트에서 Adobe Flash 플러그인 허용(obsolete)
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/콘텐츠 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\PluginsAllowedForUrls
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\PluginsAllowedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\PluginsAllowedForUrls\2 = "http://contoso.edu:8080"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: PluginsAllowedForUrls
  - 예를 들어 값:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>http://contoso.edu:8080</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="pluginsblockedforurls"></a>PluginsBlockedForUrls

  #### <a name="block-the-adobe-flash-plug-in-on-specific-sites-obsolete"></a>특정 사이트에서 Adobe Flash 플러그인 차단(obsolete)

  
  >OBSOLETE: 이 정책은 더 이상 사용되지 않으며 Microsoft Edge 87 이후에는 작동하지 않습니다.
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 macOS(77부터 87까지)

  #### <a name="description"></a>설명

  Flash가 Microsoft Edge에서 더 이상 지원되지 않으므로 이 정책이 적용되지 않습니다.

Adobe Flash의 실행을 차단하는 URL 패턴을 기반으로 사이트 목록을 정의합니다.

해당 정책을 구성하지 않으면 [DefaultPluginsSetting](#defaultpluginssetting) 정책(설정된 경우) 또는 사용자의 개인 구성의 전역 기본 값이 모든 사이트에 대해 사용됩니다.

유효한 URL 패턴에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)을(를) 참조하세요. 그러나, M85로 시작하는 호스트 내의 '\*' 및 '[\*.]' 와일드카드 패턴은 이 정책에서 더 이상 지원되지 않습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: PluginsBlockedForUrls
  - GP 이름: 특정 사이트에서 Adobe Flash 플러그인 차단(obsolete)
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/콘텐츠 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\PluginsBlockedForUrls
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\PluginsBlockedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\PluginsBlockedForUrls\2 = "http://contoso.edu:8080"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: PluginsBlockedForUrls
  - 예를 들어 값:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>http://contoso.edu:8080</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="popupsallowedforurls"></a>PopupsAllowedForUrls

  #### <a name="allow-pop-up-windows-on-specific-sites"></a>특정 사이트에서 팝업 창 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  팝업 창을 열 수 있는 URL 패턴을 기반으로 사이트 목록을 정의합니다. 별표*는 해당 정책에 허용되는 값이 아닙니다.

해당 정책을 구성하지 않으면 [DefaultPopupsSetting](#defaultpopupssetting) 정책(설정된 경우) 또는 사용자의 개인 구성의 전역 기본 값이 모든 사이트에 대해 사용됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: PopupsAllowedForUrls
  - GP 이름: 특정 사이트에서 팝업 창 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/콘텐츠 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\PopupsAllowedForUrls
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\PopupsAllowedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\PopupsAllowedForUrls\2 = "[*.]contoso.edu"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: PopupsAllowedForUrls
  - 예를 들어 값:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="popupsblockedforurls"></a>PopupsBlockedForUrls

  #### <a name="block-pop-up-windows-on-specific-sites"></a>특정 사이트에서 팝업 창 차단

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  팝업 창 열기를 차단하는 URL 패턴을 기반으로 사이트 목록을 정의합니다. 별표*는 해당 정책에 허용되는 값이 아닙니다.

해당 정책을 구성하지 않으면 [DefaultPopupsSetting](#defaultpopupssetting) 정책(설정된 경우) 또는 사용자의 개인 구성의 전역 기본 값이 모든 사이트에 대해 사용됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: PopupsBlockedForUrls
  - GP 이름: 특정 사이트에서 팝업 창 차단
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/콘텐츠 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\PopupsBlockedForUrls
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\PopupsBlockedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\PopupsBlockedForUrls\2 = "[*.]contoso.edu"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: PopupsBlockedForUrls
  - 예를 들어 값:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="registeredprotocolhandlers"></a>RegisteredProtocolHandlers

  #### <a name="register-protocol-handlers"></a>프로토콜 처리기 등록

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  이 정책을 설정(권장 전용)하여 프로토콜 처리기 목록을 등록합니다. 이 목록은 사용자가 등록한 프로토콜 처리기와 병합되며, 두 경우 모두 사용할 수 있습니다.

프로토콜 처리기 등록 방법:

- 프로토콜 속성을 구성표로 설정(예: ‘mailto’)
- URL 속성을 ‘protocol’ 필드에 지정된 구성표를 처리하는 응용 프로그램의 URL 속성으로 설정합니다. 패턴에는 처리된 URL로 대체되는 '%s' 자리 표시자가 포함될 수 있습니다.

사용자는 이 정책에서 등록한 프로토콜 처리기를 제거할 수 없습니다. 그러나 사용자는 새 기본 프로토콜 처리기를 설치하여 기존 프로토콜 처리기를 재정의할 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 아니요
  - 권장 사항: 예
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - Dictionary

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: RegisteredProtocolHandlers
  - GP 이름: 프로토콜 처리기 등록
  - GP 경로 (필수): 해당 없음
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/콘텐츠 설정
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): 해당 없음
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: RegisteredProtocolHandlers
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\RegisteredProtocolHandlers = [
  {
    "default": true, 
    "protocol": "mailto", 
    "url": "https://mail.contoso.com/mail/?extsrc=mailto&url=%s"
  }
]
```

  ##### <a name="compact-example-value"></a>예제 값 압축:

  ```
  SOFTWARE\Policies\Microsoft\Edge\RegisteredProtocolHandlers = [{"default": true, "protocol": "mailto", "url": "https://mail.contoso.com/mail/?extsrc=mailto&url=%s"}]
  ```
  

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: RegisteredProtocolHandlers
  - 예를 들어 값:
``` xml
<key>RegisteredProtocolHandlers</key>
<array>
  <dict>
    <key>default</key>
    <true/>
    <key>protocol</key>
    <string>mailto</string>
    <key>url</key>
    <string>https://mail.contoso.com/mail/?extsrc=mailto&url=%s</string>
  </dict>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="spotlightexperiencesandrecommendationsenabled"></a>SpotlightExperiencesAndRecommendationsEnabled

  #### <a name="choose-whether-users-can-receive-customized-background-images-and-text-suggestions-notifications"></a>사용자가 Microsoft 서비스에 대한 사용자 지정 배경 이미지와 텍스트, 제안, 알림
및 팁을 받을 수 있는지 여부를 선택합니다

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 86 이상

  #### <a name="description"></a>설명

  사용자가 Microsoft 서비스에 대한 사용자 지정 배경 이미지와 텍스트, 제안, 알림 및 팁을 받을 수 있는지 여부를 선택합니다.

이 설정을 사용하거나 구성하지 않으면 스포트라이트 환경과 권장 사항이 켜집니다.

이 설정을 사용하지 않으면 스포트라이트 환경과 권장 사항이 꺼집니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: SpotlightExperiencesAndRecommendationsEnabled
  - GP 이름: 사용자가 Microsoft 서비스에 대한 사용자 지정 배경 이미지와 텍스트, 제안, 알림 및 팁을 받을 수 있는지 여부를 선택합니다
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/콘텐츠 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: SpotlightExperiencesAndRecommendationsEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="webusballowdevicesforurls"></a>WebUsbAllowDevicesForUrls

  #### <a name="grant-access-to-specific-sites-to-connect-to-specific-usb-devices"></a>특정 USB 장치에 연결할 특정 사이트에 대한 액세스 권한 부여

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  지정 공급 업체 및 제품 ID로 USB 장치에 대한 액세스 권한을 자동으로 부여하는 사이트를 지정하는 URL 목록을 설정할 수 있습니다. 목록에 있는 각 항목에는 정책이 유효하도록 하려면 장치 및 URL이 모두 포함되어 있어야 합니다. 장치의 각 항목에는 공급 업체 ID 및 제품 ID 필드가 포함될 수 있습니다. 생략되는 모든 ID는 한 가지 예외가 포함된 와일드 카드로 취급되며 해당 예외란 공급 업체 ID가 지정되지 않고는 제품 ID를 지정할 수 없다는 것입니다. 그렇지 않은 경우에는 정책이 유효하지 않으며 무시됩니다.

USB 사용 권한 모델은 요청 사이트의 URL("URL 요청")과 최상위 프레임 사이트의 URL(“URL 포함”)을 사용하여 요청 URL에 USB 장치 액세스 권한을 부여합니다. 요청 사이트가 IFrame에 로드된 경우 요청 URL은 포함 URL과 다를 수 있습니다. 따라서 "urls" 필드에 쉼표로 구분된 최대 2개의 URL 문자열을 포함하여 각각 요청 및 포함 URL을 지정할 수 있습니다. URL이 하나만 지정된 경우 해당 USB 장치에 대한 액세스 권한은 요청 사이트의 URL이 포함 상태에 관계없이 해당 URL과 일치하는 경우에 부여됩니다. "urls"의 URL은 유효한 URL이어야 합니다. 그렇지 않으면 해당 정책이 무시됩니다.

해당 정책을 설정하지 않은 상태로 남겨두면 [DefaultWebUsbGuardSetting](#defaultwebusbguardsetting) 정책(설정된 경우) 또는 사용자의 개인 구성에서 모든 사이트에 대해 전역 기본 값이 사용됩니다.

해당 정책의 URL 패턴은 [WebUsbBlockedForUrls](#webusbblockedforurls)를 통해 구성한 패턴과 충돌하지 않아야 합니다. 충돌이 발생하는 경우 해당 정책은 [WebUsbBlockedForUrls](#webusbblockedforurls) 및 [WebUsbAskForUrls](#webusbaskforurls)를 통해 우선됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - Dictionary

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: WebUsbAllowDevicesForUrls
  - GP 이름: 특정 USB 장치에 연결할 특정 사이트에 대한 액세스 권한 부여
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/콘텐츠 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: WebUsbAllowDevicesForUrls
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\WebUsbAllowDevicesForUrls = [
  {
    "devices": [
      {
        "product_id": 5678, 
        "vendor_id": 1234
      }
    ], 
    "urls": [
      "https://contoso.com", 
      "https://fabrikam.com"
    ]
  }
]
```

  ##### <a name="compact-example-value"></a>예제 값 압축:

  ```
  SOFTWARE\Policies\Microsoft\Edge\WebUsbAllowDevicesForUrls = [{"devices": [{"product_id": 5678, "vendor_id": 1234}], "urls": ["https://contoso.com", "https://fabrikam.com"]}]
  ```
  

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: WebUsbAllowDevicesForUrls
  - 예를 들어 값:
``` xml
<key>WebUsbAllowDevicesForUrls</key>
<array>
  <dict>
    <key>devices</key>
    <array>
      <dict>
        <key>product_id</key>
        <integer>5678</integer>
        <key>vendor_id</key>
        <integer>1234</integer>
      </dict>
    </array>
    <key>urls</key>
    <array>
      <string>https://contoso.com</string>
      <string>https://fabrikam.com</string>
    </array>
  </dict>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="webusbaskforurls"></a>WebUsbAskForUrl

  #### <a name="allow-webusb-on-specific-sites"></a>특정 사이트에서 WebUSB 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  사용자에게 USB 장치에 대한 액세스를 요청할 수 있는 URL 패턴을 기반으로 사이트 목록을 정의합니다.

해당 정책을 구성하지 않으면 [DefaultWebUsbGuardSetting](#defaultwebusbguardsetting) 정책(설정된 경우) 또는 사용자의 개인 구성의 전역 기본 값이 모든 사이트에 대해 사용됩니다.

해당 정책에 정의된 URL 패턴과 [WebUsbBlockedForUrls](#webusbblockedforurls) 정책에서 구성한 패턴과 충돌할 수 없습니다. URL을 허용하거나 차단할 수 없습니다. 유효한 URL 패턴에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)을(를) 참조하세요.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: WebUsbAskForUrls
  - GP 이름: 특정 사이트에서 WebUSB 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/콘텐츠 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\WebUsbAskForUrls
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\WebUsbAskForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\WebUsbAskForUrls\2 = "[*.]contoso.edu"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: WebUsbAskForUrls
  - 예를 들어 값:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="webusbblockedforurls"></a>WebUsbBlockedForUrls

  #### <a name="block-webusb-on-specific-sites"></a>특정 사이트에서 WebUSB 차단

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  사용자에게 USB 장치에 대한 액세스를 요청할 수 없는 URL 패턴을 기반으로 사이트 목록을 정의합니다.

해당 정책을 구성하지 않으면 [DefaultWebUsbGuardSetting](#defaultwebusbguardsetting) 정책(설정된 경우) 또는 사용자의 개인 구성의 전역 기본 값이 모든 사이트에 대해 사용됩니다.

해당 정책의 URL 패턴은 [WebUsbAskForUrls](#webusbaskforurls) 정책에서 구성한 패턴과 충돌할 수 없습니다. URL을 허용하거나 차단할 수 없습니다.  유효한 URL 패턴에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)을(를) 참조하세요.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: WebUsbBlockedForUrls
  - GP 이름: 특정 사이트에서 WebUSB 차단
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/콘텐츠 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\WebUsbBlockedForUrls
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\WebUsbBlockedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\WebUsbBlockedForUrls\2 = "[*.]contoso.edu"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: WebUsbBlockedForUrls
  - 예를 들어 값:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ## <a name="default-search-provider-policies"></a>기본 검색 공급자 정책

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="defaultsearchproviderenabled"></a>DefaultSearchProviderEnabled

  #### <a name="enable-the-default-search-provider"></a>기본 검색 공급자 사용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  기본 검색 공급자를 사용할 수 있는 기능을 설정할 수 있습니다.

해당 정책을 사용하면 사용자가 주소 표시줄에 입력하여 검색어를 검색할 수 있습니다. (입력한 내용이 URL이 아닌 경우)

나머지 기본 검색 정책을 사용하도록 설정하여 사용할 기본 검색 공급자를 지정할 수 있습니다. 해당 내용이 비어 있거나(구성 되지 않음) 잘못 구성된 경우 사용자는 기본 공급자를 선택할 수 있습니다.

해당 정책을 사용하지 않도록 설정하면 사용자는 주소 표시줄에서 검색할 수 없습니다.

해당 정책을 사용하거나 사용하지 않도록 설정하면 사용자는 해당 정책을 변경하거나 재정의할 수 없습니다.

해당 정책을 구성하지 않으면 기본 검색 공급자가 사용되고 사용자는 기본 검색 공급자를 선택하고 검색 공급자 목록을 설정할 수 있습니다.

이 정책은 Microsoft Active Directory 도메인에 가입된 윈도우즈 인스턴스, 장치 관리를 위해 등록된 윈도우즈 10 Pro 또는 Enterprise 인스턴스 또는 MDM을 통해 관리되거나 MCX를 통해 도메인에 가입된 MacOS 인스턴스에서만 사용할 수 있습니다..

Microsoft Edge 84부터 이 정책을 권장 정책으로 설정할 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: DefaultSearchProviderEnabled
  - GP 이름: 기본 검색 공급자 사용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/기본 검색 공급자
  - GP 경로(권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/기본 검색 공급자
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: DefaultSearchProviderEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: DefaultSearchProviderEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="defaultsearchproviderencodings"></a>DefaultSearchProviderEncodings

  #### <a name="default-search-provider-encodings"></a>기본 검색 공급자 인코딩

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  검색 공급자가 지원하는 문자 인코딩을 지정합니다. 인코딩은 UTF-8, GB2312, ISO-8859-1과 같은 코드 페이지 이름입니다. 인코딩은 제공된 순서대로 시도됩니다.

해당 정책은 선택 사항입니다. 해당 정책을 구성하지 않으면 기본값 UTF-8이 사용됩니다.

해당 정책은 [DefaultSearchProviderEnabled](#defaultsearchproviderenabled) 및 [DefaultSearchProviderSearchURL](#defaultsearchprovidersearchurl) 정책을 사용하도록 설정한 경우에만 적용됩니다.

Microsoft Edge 84부터 이 정책을 권장 정책으로 설정할 수 있습니다. 사용자가 이미 기본 검색 공급자를 설정한 경우 이 권장 정책에 의해 구성된 기본 검색 공급자는 사용자가 선택할 수 있는 검색 공급자 목록에 추가되지 않습니다. 원하는 동작인 경우 [ManagedSearchEngines](#managedsearchengines) 정책을 사용하세요.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: DefaultSearchProviderEncodings
  - GP 이름: 기본 검색 공급자 인코딩
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/기본 검색 공급자
  - GP 경로(권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/기본 검색 공급자
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\DefaultSearchProviderEncodings
  - 경로(권장): SOFTWARE\정책\Microsoft\Edge\Recommended\DefaultSearchProviderEncodings
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\DefaultSearchProviderEncodings\1 = "UTF-8"
SOFTWARE\Policies\Microsoft\Edge\DefaultSearchProviderEncodings\2 = "UTF-16"
SOFTWARE\Policies\Microsoft\Edge\DefaultSearchProviderEncodings\3 = "GB2312"
SOFTWARE\Policies\Microsoft\Edge\DefaultSearchProviderEncodings\4 = "ISO-8859-1"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: DefaultSearchProviderEncodings
  - 예를 들어 값:
``` xml
<array>
  <string>UTF-8</string>
  <string>UTF-16</string>
  <string>GB2312</string>
  <string>ISO-8859-1</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="defaultsearchproviderimageurl"></a>DefaultSearchProviderImageURL

  #### <a name="specifies-the-search-by-image-feature-for-the-default-search-provider"></a>기본 검색 공급자에 대한 이미지 검색 기능 지정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  이미지 검색에 사용되는 검색 엔진에 대한 URL을 지정합니다. 검색 요청은 GET 메서드를 사용하여 전송됩니다.

해당 정책은 선택 사항입니다. 해당 정책을 구성하지 않으면 이미지 검색을 사용할 수 없습니다.

Bing 이미지 검색 URL을 다음과 같이 지정: '{bing:baseURL}images/detail/search?iss=sbiupload&FORM=ANCMS1#enterInsights'.

Google 이미지 검색 URL을 다음과 같이 지정:
'{google: baseURL}searchbyimage/upload'

이미지 검색 구성을 완료하려면 [DefaultSearchProviderImageURLPostParams](#defaultsearchproviderimageurlpostparams) 정책을 참조하세요.

해당 정책은 [DefaultSearchProviderEnabled](#defaultsearchproviderenabled) 및 [DefaultSearchProviderSearchURL](#defaultsearchprovidersearchurl) 정책을 사용하도록 설정한 경우에만 적용됩니다.

Microsoft Edge 84부터 이 정책을 권장 정책으로 설정할 수 있습니다. 사용자가 이미 기본 검색 공급자를 설정한 경우 이 권장 정책에 의해 구성된 기본 검색 공급자는 사용자가 선택할 수 있는 검색 공급자 목록에 추가되지 않습니다. 원하는 동작인 경우 [ManagedSearchEngines](#managedsearchengines) 정책을 사용하세요.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: DefaultSearchProviderImageURL
  - GP 이름: 기본 검색 공급자에 대한 이미지 검색 기능 지정
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/기본 검색 공급자
  - GP 경로(권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/기본 검색 공급자
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: DefaultSearchProviderImageURL
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
"https://search.contoso.com/searchbyimage/upload"
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: DefaultSearchProviderImageURL
  - 예를 들어 값:
``` xml
<string>https://search.contoso.com/searchbyimage/upload</string>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="defaultsearchproviderimageurlpostparams"></a>DefaultSearchProviderImageURLPostParams

  #### <a name="parameters-for-an-image-url-that-uses-post"></a>POST를 사용하는 이미지 URL에 대한 매개 변수

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  해당 정책을 사용하면 POST를 사용하는 이미지 검색이 수행될 때 사용되는 매개 변수가 지정됩니다. 해당 정책은 쉼표로 구분된 이름/값 쌍으로 구성됩니다. 이전 예제에서 값이 {imageThumbnail}과 같은 템플릿 매개 변수인 경우 이는 실제 이미지 축소판 그림 데이터로 바뀝니다. 해당 정책은 [DefaultSearchProviderEnabled](#defaultsearchproviderenabled) 및 [DefaultSearchProviderSearchURL](#defaultsearchprovidersearchurl) 정책을 사용하도록 설정한 경우에만 적용됩니다.

Bing 이미지 검색 URL 게시 매개 변수를 다음과 같이 지정: 'imageBin={google:imageThumbnailBase64}'

Google 이미지 검색 URL 게시 매개 변수를 다음과 같이 지정: 'encoded_image={google:imageThumbnail},image_url={google:imageURL},sbisrc={google:imageSearchSource},original_width={google:imageOriginalWidth},original_height={google:imageOriginalHeight}'

해당 정책을 설정하지 않으면 GET 메서드를 사용하여 이미지 검색 요청이 전송됩니다.

Microsoft Edge 84부터 이 정책을 권장 정책으로 설정할 수 있습니다. 사용자가 이미 기본 검색 공급자를 설정한 경우 이 권장 정책에 의해 구성된 기본 검색 공급자는 사용자가 선택할 수 있는 검색 공급자 목록에 추가되지 않습니다. 원하는 동작인 경우 [ManagedSearchEngines](#managedsearchengines) 정책을 사용하세요.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: DefaultSearchProviderImageURLPostParams
  - GP 이름: POST를 사용하는 이미지 URL에 대한 매개 변수
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/기본 검색 공급자
  - GP 경로(권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/기본 검색 공급자
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: DefaultSearchProviderImageURLPostParams
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
"content={imageThumbnail},url={imageURL},sbisrc={SearchSource}"
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: DefaultSearchProviderImageURLPostParams
  - 예를 들어 값:
``` xml
<string>content={imageThumbnail},url={imageURL},sbisrc={SearchSource}</string>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="defaultsearchproviderkeyword"></a>DefaultSearchProviderKeyword

  #### <a name="default-search-provider-keyword"></a>기본 검색 공급자 키워드

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  해당 공급자에 대한 검색을 트리거하기 위해 주소 표시줄에서 사용하는 바로 가기인 키워드를 지정합니다.

해당 정책은 선택 사항입니다. 해당 정책을 구성하지 않으면 키워드는 검색 공급자를 활성화하지 않습니다.

해당 정책은 [DefaultSearchProviderEnabled](#defaultsearchproviderenabled) 및 [DefaultSearchProviderSearchURL](#defaultsearchprovidersearchurl) 정책을 사용하도록 설정한 경우에만 적용됩니다.

Microsoft Edge 84부터 이 정책을 권장 정책으로 설정할 수 있습니다. 사용자가 이미 기본 검색 공급자를 설정한 경우 이 권장 정책에 의해 구성된 기본 검색 공급자는 사용자가 선택할 수 있는 검색 공급자 목록에 추가되지 않습니다. 원하는 동작인 경우 [ManagedSearchEngines](#managedsearchengines) 정책을 사용하세요.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: DefaultSearchProviderKeyword
  - GP 이름: 기본 검색 공급자 키워드
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/기본 검색 공급자
  - GP 경로(권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/기본 검색 공급자
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: DefaultSearchProviderKeyword
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
"mis"
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: DefaultSearchProviderKeyword
  - 예를 들어 값:
``` xml
<string>mis</string>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="defaultsearchprovidername"></a>DefaultSearchProviderName

  #### <a name="default-search-provider-name"></a>기본 검색 공급자 이름

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  기본 검색 공급자의 이름을 지정합니다.

해당 정책을 사용하면 기본 검색 공급자의 이름을 설정합니다.

해당 정책을 사용하지 않거나 비어있는 채로 남겨둔 경우 검색 URL에서 지정한 호스트 이름이 사용됩니다.

'DefaultSearchProviderName'은 DTBC-0008에 설정된 암호화된 검색 공급자에 해당하는 조직에서 승인한 암호화된 검색 공급자에 설정되어야 합니다. 해당 정책은 [DefaultSearchProviderEnabled](#defaultsearchproviderenabled) 및 [DefaultSearchProviderSearchURL](#defaultsearchprovidersearchurl) 정책을 사용하도록 설정한 경우에만 적용됩니다.

Microsoft Edge 84부터 이 정책을 권장 정책으로 설정할 수 있습니다. 사용자가 이미 기본 검색 공급자를 설정한 경우 이 권장 정책에 의해 구성된 기본 검색 공급자는 사용자가 선택할 수 있는 검색 공급자 목록에 추가되지 않습니다. 원하는 동작인 경우 [ManagedSearchEngines](#managedsearchengines) 정책을 사용하세요.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: DefaultSearchProviderName
  - GP 이름: 기본 검색 공급자 이름
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/기본 검색 공급자
  - GP 경로(권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/기본 검색 공급자
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: DefaultSearchProviderName
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
"My Intranet Search"
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: DefaultSearchProviderName
  - 예를 들어 값:
``` xml
<string>My Intranet Search</string>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="defaultsearchprovidersearchurl"></a>DefaultSearchProviderSearchURL

  #### <a name="default-search-provider-search-url"></a>기본 검색 공급자 검색 URL

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  기본 검색에 사용되는 검색 엔진에 대한 URL을 지정합니다. URL에는 쿼리 시간에서 사용자를 검색하는 용어로 대체되는 '{searchTerms}' 문자열이 포함됩니다.

Bing 검색 URL을 다음과 같이 지정:

'{bing:baseURL}search?q={searchTerms}'

Google 검색 URL을 다음과 같이 지정: '{google:baseURL}search?q={searchTerms}&{google:RLZ}{google:originalQueryForSuggestion}{google:assistedQueryStats}{google:searchFieldtrialParameter}{google:searchClient}{google:sourceId}ie={inputEncoding}’

해당 정책은 [DefaultSearchProviderEnabled](#defaultsearchproviderenabled) 정책을 설정하는 경우에 필요합니다. 이후 정책을 사용하지 않는 경우 해당 정책은 무시됩니다.

Microsoft Edge 84부터 이 정책을 권장 정책으로 설정할 수 있습니다. 사용자가 이미 기본 검색 공급자를 설정한 경우 이 권장 정책에 의해 구성된 기본 검색 공급자는 사용자가 선택할 수 있는 검색 공급자 목록에 추가되지 않습니다. 원하는 동작인 경우 [ManagedSearchEngines](#managedsearchengines) 정책을 사용하세요.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: DefaultSearchProviderSearchURL
  - GP 이름: 기본 검색 공급자 검색 URL
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/기본 검색 공급자
  - GP 경로(권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/기본 검색 공급자
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: DefaultSearchProviderSearchURL
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
"https://search.contoso.com/search?q={searchTerms}"
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: DefaultSearchProviderSearchURL
  - 예를 들어 값:
``` xml
<string>https://search.contoso.com/search?q={searchTerms}</string>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="defaultsearchprovidersuggesturl"></a>DefaultSearchProviderSuggestURL

  #### <a name="default-search-provider-url-for-suggestions"></a>제안에 대한 기본 검색 공급자 URL

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  검색 제안을 제공하는 데 사용되는 검색 엔진에 대한 URL을 지정합니다. URL에는 쿼리 시간에서 사용자가 지금까지 검색한 텍스트로 대체되는 '{searchTerms}' 문자열이 포함됩니다.

해당 정책은 선택 사항입니다. 해당 정책을 구성하지 않으면 사용자는 검색 제안을 볼 수 없습니다. 해당 검색 기록 및 즐겨찾기에서 제안이 표시됩니다.

Bing의 제안 URL은 다음과 같이 지정할 수 있습니다.

'{bing:baseURL}qbox?query={searchTerms}'

Google의 제안 URL은 다음과 같이 지정할 수 있습니다. '{google:baseURL}complete/search?output=chrome&q={searchTerms}'

해당 정책은 [DefaultSearchProviderEnabled](#defaultsearchproviderenabled) 및 [DefaultSearchProviderSearchURL](#defaultsearchprovidersearchurl) 정책을 사용하도록 설정한 경우에만 적용됩니다.

Microsoft Edge 84부터 이 정책을 권장 정책으로 설정할 수 있습니다. 사용자가 이미 기본 검색 공급자를 설정한 경우 이 권장 정책에 의해 구성된 기본 검색 공급자는 사용자가 선택할 수 있는 검색 공급자 목록에 추가되지 않습니다. 원하는 동작인 경우 [ManagedSearchEngines](#managedsearchengines) 정책을 사용하세요.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: DefaultSearchProviderSuggestURL
  - GP 이름: 제안에 대한 기본 검색 공급자 URL
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/기본 검색 공급자
  - GP 경로(권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/기본 검색 공급자
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: DefaultSearchProviderSuggestURL
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
"https://search.contoso.com/suggest?q={searchTerms}"
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: DefaultSearchProviderSuggestURL
  - 예를 들어 값:
``` xml
<string>https://search.contoso.com/suggest?q={searchTerms}</string>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="newtabpagesearchbox"></a>NewTabPageSearchBox

  #### <a name="configure-the-new-tab-page-search-box-experience"></a>새 탭 페이지 검색창 환경 구성

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS(85 이상)

  #### <a name="description"></a>설명

  새 탭 페이지 검색 상자에서 "검색 상자(권장)" 또는 "주소 표시줄"을 사용하여 새 탭에서 검색하도록 구성할 수 있습니다. 이 정책은 다음 두 정책을 설정하여 검색 엔진을 Bing 이외의 값으로 설정한 경우에만 사용할 수 있습니다. [DefaultSearchProviderEnabled](#defaultsearchproviderenabled) 및 [DefaultSearchProviderSearchURL](#defaultsearchprovidersearchurl)입니다.

 해당 정책을 사용하지 않도록 설정하거나 구성하지 않고 다음과 같은 경우:

- 주소 표시줄 기본 검색 엔진이 Bing인 경우 새 탭 페이지에서 검색창을 사용하여 새 탭을 검색합니다.
- 주소 표시줄 기본 검색 엔진이 Bing이 아닌 경우 새 탭을 검색할 때 사용자에게 추가 선택 사항("주소 표시줄 사용")이 나타납니다.


이 정책을 활성화하고 다음과 같이 설정한 경우:

- "검색창(권장)"('bing'), 새 탭 페이지는 검색창을 사용하여 새 탭을 검색합니다.
- "주소 표시줄"('리디렉션'), 새 탭 페이지 검색창은 주소 표시줄을 사용하여 새 탭을 검색합니다.

정책 옵션 매핑:

* bing (bing) = 검색창(권장)

* 리디렉션(redirect) = 주소 표시줄

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: NewTabPageSearchBox
  - GP 이름: 새 탭 페이지 검색창 환경 구성
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/기본 검색 공급자
  - GP 경로(권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/기본 검색 공급자
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: NewTabPageSearchBox
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
"bing"
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: NewTabPageSearchBox
  - 예를 들어 값:
``` xml
<string>bing</string>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ## <a name="extensions-policies"></a>확장 정책

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="blockexternalextensions"></a>BlockExternalExtensions

  #### <a name="blocks-external-extensions-from-being-installed"></a>외부 확장이 설치되지 않도록 차단압니다.

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS 88 이상

  #### <a name="description"></a>설명

  외부 확장 설치를 제어합니다.

이 설정을 사용하도록 설정하면 외부 확장 설치가 차단됩니다.

이 설정을 사용하지 않도록 설정하거나 설정하지 않으면 외부 확장을 설치할 수 있습니다.

외부 확장 및 설치는 https://docs.microsoft.com/microsoft-edge/extensions-chromium/developer-guide/alternate-distribution-options에서 설명합니다.


  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: BlockExternalExtensions
  - GP 이름: 외부 확장 설치를 차단합니다.
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/확장
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로(권장): 해당 없음
  - 값 이름: BlockExternalExtensions
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: BlockExternalExtensions
  - 값 예시:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="extensionallowedtypes"></a>ExtensionAllowedTypes

  #### <a name="configure-allowed-extension-types"></a>허용된 확장 유형 구성

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  정책을 설정하면 Microsoft Edge에 설치될 수 있는 앱과 확장명, 이들이 상호 작용할 수 있는 호스트를 제어하고 런타임 액세스를 제한할 수 있습니다.

이 정책을 설정하지 않으면 허용되는 확장명 및 앱 형식에 제한이 없습니다.

목록에 없는 형식의 확장명과 앱은 설치되지 않습니다. 각 값은 다음 문자열 중 하나이어야 합니다.

* "확장"

* "테마"

* "user_script"

* "hosted_app"

이러한 형식에 대한 자세한 내용은 Microsoft Edge 확장 설명서를 참조하세요.

참고: 이 정책은 또한 [ExtensionInstallForcelist](#extensioninstallforcelist)를 사용하여 강제로 설치되는 확장명 및 앱에도 영향을 줍니다.

  #### <a name="supported-features"></a>지원되는 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ExtensionAllowedTypes
  - GP 이름: 허용된 확장 형식 구성
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/확장
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\ExtensionAllowedTypes
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\ExtensionAllowedTypes\1 = "hosted_app"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ExtensionAllowedTypes
  - 예를 들어 값:
``` xml
<array>
  <string>hosted_app</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="extensioninstallallowlist"></a>ExtensionInstallAllowlist

  #### <a name="allow-specific-extensions-to-be-installed"></a>특정 확장 설치 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  이 정책을 설정하면 차단 목록이 적용되지 않는 확장이 지정됩니다.

차단 목록 값이 *이면 모든 확장이 차단되어 사용자는 허용 목록에 나열된 확장만 설치할 수 있습니다.

기본적으로 모든 확장이 허용됩니다. 그러나 정책에 따라 확장을 금지한 경우 허용되는 확장 목록을 사용하여 해당 정책을 변경할 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ExtensionInstallAllowlist
  - GP 이름: 특정 확장 설치 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/확장
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\ExtensionInstallAllowlist
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\ExtensionInstallAllowlist\1 = "extension_id1"
SOFTWARE\Policies\Microsoft\Edge\ExtensionInstallAllowlist\2 = "extension_id2"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ExtensionInstallAllowlist
  - 예를 들어 값:
``` xml
<array>
  <string>extension_id1</string>
  <string>extension_id2</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="extensioninstallblocklist"></a>ExtensionInstallBlocklist

  #### <a name="control-which-extensions-cannot-be-installed"></a>설치할 수 없는 확장 제어

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  사용자가 설치할 수 없는 확장을 지정할 수 있습니다. 이미 설치된 확장이 차단된 경우 사용자의 사용 설정 방법 없이 비활성화됩니다. 차단 목록에서 비활성화된 확장이 제거되면 자동으로 다시 활성화됩니다.

차단 목록 값 '\*'은 허용 목록에 명시적으로 나열되지 않는 한 모든 확장이 차단됨을 의미합니다.

해당 정책을 설정하지 않은 경우 사용자는 Microsoft Edge에서 모든 확장을 설치할 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ExtensionInstallBlocklist
  - GP 이름: 설치할 수 없는 확장 제어
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/확장
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\ExtensionInstallBlocklist
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\ExtensionInstallBlocklist\1 = "extension_id1"
SOFTWARE\Policies\Microsoft\Edge\ExtensionInstallBlocklist\2 = "extension_id2"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ExtensionInstallBlocklist
  - 예를 들어 값:
``` xml
<array>
  <string>extension_id1</string>
  <string>extension_id2</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="extensioninstallforcelist"></a>ExtensionInstallForcelist

  #### <a name="control-which-extensions-are-installed-silently"></a>자동으로 설치되는 확장 제어

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  이 정책을 설정하여 사용자의 개입 없이 자동으로 설치되는 앱 및 확장 목록을 지정합니다. 사용자는 이 설정을 제거하거나 해제할 수 없습니다. 사용 권한은 enterprise.deviceAttributes 및 enterprise.platformKeys 확장 API를 포함하여 암시적으로 부여됩니다. 참고: 이 2개의 API는 강제 설치되지 않은 앱 및 확장에 사용할 수 없습니다.

이 정책을 설정하지 않으면 자동으로 설치되는 앱 또는 확장이 없으며 사용자가 Microsoft Edge에서 앱을 제거할 수 있습니다.

이 정책은 [ExtensionInstallBlocklist](#extensioninstallblocklist) 정책을 대체합니다. 이전에 강제 설치된 앱 또는 확장이 이 목록에서 제거되는 경우, Microsoft Edge에서 자동으로 제거합니다.

Microsoft Windows 인스턴스에서 Microsoft Edge 추가 기능 웹 사이트 외부의 앱과 확장 기능은 해당 인스턴스가 Microsoft Active Directory 도메인에 가입되고 Windows 10 Pro를 실행하는 경우에만 강제 설치될 수 있습니다.

MacOS 인스턴스에서, Microsoft Edge 추가 기능 웹 사이트 외부의 앱 및 확장 기능은 해당 인스턴스가 MDM을 통해 관리되거나 MCX를 통해 도메인에 가입되는 경우에만 강제 설치될 수 있습니다.

모든 확장의 소스 코드는 사용자가 개발자 도구를 사용하여 변경하고 잠재적으로 확장을 기능하지 못하도록 렌더링할 수 있습니다. 이 문제가 우려되는 경우, DeveloperToolsDisabled 정책을 구성합니다.

정책의 각 목록 항목은 확장 ID를 포함하는 문자열이며 선택적으로 세미콜론(;)으로 구분되는 "업데이트" URL입니다. 확장 ID는 개발자 모드에서(예: edge://extensions 등) 찾을 수 있는 32자의 문자열입니다. "업데이트" URL은 지정된 경우, 업데이트 매니페스트 XML 문서( [https://go.microsoft.com/fwlink/?linkid=2095043](https://go.microsoft.com/fwlink/?linkid=2095043) )를 가리켜야 합니다. 기본적으로 Microsoft Edge 추가 기능 웹 사이트의 업데이트 URL이 사용됩니다. 이 정책에 설정된 "업데이트" URL은 초기 설치에만 사용됩니다. 확장의 후속 업데이트는 확장의 매니페스트에 있는 업데이트 URL을 사용합니다.

참고: 이 정책은 InPrivate 모드에 적용되지 않습니다. 호스팅 확장에 대해 자세히 읽어보세요(https://docs.microsoft.com/microsoft-edge/extensions-chromium/enterprise/hosting-and-updating).

  #### <a name="supported-features"></a>지원되는 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ExtensionInstallForcelist
  - GP 이름: 자동으로 설치되는 확장 제어
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/확장
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\ExtensionInstallForcelist
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\ExtensionInstallForcelist\1 = "gbchcmhmhahfdphkhkmpfmihenigjmpp;https://edge.microsoft.com/extensionwebstorebase/v1/crx"
SOFTWARE\Policies\Microsoft\Edge\ExtensionInstallForcelist\2 = "abcdefghijklmnopabcdefghijklmnop"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ExtensionInstallForcelist
  - 예를 들어 값:
``` xml
<array>
  <string>gbchcmhmhahfdphkhkmpfmihenigjmpp;https://edge.microsoft.com/extensionwebstorebase/v1/crx</string>
  <string>abcdefghijklmnopabcdefghijklmnop</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="extensioninstallsources"></a>ExtensionInstallSources

  #### <a name="configure-extension-and-user-script-install-sources"></a>확장 및 사용자 스크립트 설치 원본 구성

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  확장 및 테마를 설치할 수 있는 URL을 정의합니다.

패키지를 edge://extensions page로 끌어서 놓을 필요 없이 직접 확장 및 테마를 설치할 수 있는 URL을 정의합니다.

해당 목록에 있는 각 항목은 확장 스타일 일치 패턴입니다. ([https://go.microsoft.com/fwlink/?linkid=2095039](https://go.microsoft.com/fwlink/?linkid=2095039)참조) 사용자는 해당 목록에 있는 항목과 일치하는 모든 URL에서 간편하게 항목을 설치할 수 있습니다. *.crx 파일의 위치 및 다운로드를 시작하는 페이지(즉, 참조 페이지) 모두 해당 패턴에서 허용되어야 합니다. 인증이 필요한 위치에서 파일을 호스팅하지 마세요.

[ExtensionInstallBlocklist](#extensioninstallblocklist) 정책이 해당 정책보다 우선됩니다. 차단 목록에 있는 모든 확장은 해당 목록의 사이트에서 가져온 경우에도 설치할 수 없습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ExtensionInstallSources
  - GP 이름: 확장 및 사용자 스크립트 설치 원본 구성
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/확장
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\ExtensionInstallSources
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\ExtensionInstallSources\1 = "https://corp.contoso.com/*"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ExtensionInstallSources
  - 예를 들어 값:
``` xml
<array>
  <string>https://corp.contoso.com/*</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="extensionsettings"></a>ExtensionSettings

  #### <a name="configure-extension-management-settings"></a>확장 관리 설정 구성

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  이 정책을 설정하면 기존 확장 관련 정책에 의해 제어되는 설정을 포함하여 Microsoft Edge의 확장 관리 설정이 제어됩니다. 이 정책은 설정될 수 있는 모든 레거시 정책을 대체합니다.

해당 정책은 확장 ID 또는 업데이트 URL을 해당 특정 설정에만 매핑합니다. 이 정책에서 사용자 지정 구성이 없는 모든 확장에 적용되는 특수 ID "*"에 대해 기본 구성을 설정할 수 있습니다. 업데이트 URL을 사용할 경우 확장 매니페스트([https://go.microsoft.com/fwlink/?linkid=2095043](https://go.microsoft.com/fwlink/?linkid=2095043))에 설명된 정확한 업데이트 URL이 있는 확장에 구성이 적용됩니다.

특정 타사 스토어의 확장을 차단하려면 해당 스토어에 대한 update_url만 차단하면 됩니다. 예를 들어 Chrome 웹 스토어의 확장을 차단하려는 경우 다음 JSON을 사용할 수 있습니다.

{"update_url:https://clients2.google.com/service/update2/crx":{"installation_mode":"blocked"}}

이전 예제의 JSON을 사용하여 스토어가 차단된 경우에도 [ExtensionInstallForcelist](#extensioninstallforcelist) 및 [ExtensionInstallAllowlist를](#extensioninstallallowlist) 사용하여 특정 확장을 허용/강제로 설치할 수 있습니다.

참고: Microsoft Active Directory 도메인에 가입되지 않은 Windows 인스턴스의 경우, 강제 설치가 Microsoft Edge 추가 기능 웹 사이트에 나열된 앱 및 확장으로 제한됩니다.


  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - Dictionary

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ExtensionSettings
  - GP 이름: 확장 관리 설정 구성
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/확장
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: ExtensionSettings
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\ExtensionSettings = {
  "*": {
    "allowed_types": [
      "hosted_app"
    ], 
    "blocked_install_message": "Custom error message.", 
    "blocked_permissions": [
      "downloads", 
      "bookmarks"
    ], 
    "install_sources": [
      "https://company-intranet/apps"
    ], 
    "installation_mode": "blocked", 
    "runtime_allowed_hosts": [
      "*://good.contoso.com"
    ], 
    "runtime_blocked_hosts": [
      "*://*.contoso.com"
    ]
  }, 
  "abcdefghijklmnopabcdefghijklmnop": {
    "blocked_permissions": [
      "history"
    ], 
    "installation_mode": "allowed", 
    "minimum_version_required": "1.0.1"
  }, 
  "bcdefghijklmnopabcdefghijklmnopa": {
    "allowed_permissions": [
      "downloads"
    ], 
    "installation_mode": "force_installed", 
    "runtime_allowed_hosts": [
      "*://good.contoso.com"
    ], 
    "runtime_blocked_hosts": [
      "*://*.contoso.com"
    ], 
    "update_url": "https://contoso.com/update_url"
  }, 
  "cdefghijklmnopabcdefghijklmnopab": {
    "blocked_install_message": "Custom error message.", 
    "installation_mode": "blocked"
  }, 
  "defghijklmnopabcdefghijklmnopabc,efghijklmnopabcdefghijklmnopabcd": {
    "blocked_install_message": "Custom error message.", 
    "installation_mode": "blocked"
  }, 
  "fghijklmnopabcdefghijklmnopabcde": {
    "blocked_install_message": "Custom removal message.", 
    "installation_mode": "removed"
  }, 
  "update_url:https://www.contoso.com/update.xml": {
    "allowed_permissions": [
      "downloads"
    ], 
    "blocked_permissions": [
      "wallpaper"
    ], 
    "installation_mode": "allowed"
  }
}
```

  ##### <a name="compact-example-value"></a>예제 값 압축:

  ```
  SOFTWARE\Policies\Microsoft\Edge\ExtensionSettings = {"*": {"allowed_types": ["hosted_app"], "blocked_install_message": "Custom error message.", "blocked_permissions": ["downloads", "bookmarks"], "install_sources": ["https://company-intranet/apps"], "installation_mode": "blocked", "runtime_allowed_hosts": ["*://good.contoso.com"], "runtime_blocked_hosts": ["*://*.contoso.com"]}, "abcdefghijklmnopabcdefghijklmnop": {"blocked_permissions": ["history"], "installation_mode": "allowed", "minimum_version_required": "1.0.1"}, "bcdefghijklmnopabcdefghijklmnopa": {"allowed_permissions": ["downloads"], "installation_mode": "force_installed", "runtime_allowed_hosts": ["*://good.contoso.com"], "runtime_blocked_hosts": ["*://*.contoso.com"], "update_url": "https://contoso.com/update_url"}, "cdefghijklmnopabcdefghijklmnopab": {"blocked_install_message": "Custom error message.", "installation_mode": "blocked"}, "defghijklmnopabcdefghijklmnopabc,efghijklmnopabcdefghijklmnopabcd": {"blocked_install_message": "Custom error message.", "installation_mode": "blocked"}, "fghijklmnopabcdefghijklmnopabcde": {"blocked_install_message": "Custom removal message.", "installation_mode": "removed"}, "update_url:https://www.contoso.com/update.xml": {"allowed_permissions": ["downloads"], "blocked_permissions": ["wallpaper"], "installation_mode": "allowed"}}
  ```
  

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ExtensionSettings
  - 예를 들어 값:
``` xml
<key>ExtensionSettings</key>
<dict>
  <key>*</key>
  <dict>
    <key>allowed_types</key>
    <array>
      <string>hosted_app</string>
    </array>
    <key>blocked_install_message</key>
    <string>Custom error message.</string>
    <key>blocked_permissions</key>
    <array>
      <string>downloads</string>
      <string>bookmarks</string>
    </array>
    <key>install_sources</key>
    <array>
      <string>https://company-intranet/apps</string>
    </array>
    <key>installation_mode</key>
    <string>blocked</string>
    <key>runtime_allowed_hosts</key>
    <array>
      <string>*://good.contoso.com</string>
    </array>
    <key>runtime_blocked_hosts</key>
    <array>
      <string>*://*.contoso.com</string>
    </array>
  </dict>
  <key>abcdefghijklmnopabcdefghijklmnop</key>
  <dict>
    <key>blocked_permissions</key>
    <array>
      <string>history</string>
    </array>
    <key>installation_mode</key>
    <string>allowed</string>
    <key>minimum_version_required</key>
    <string>1.0.1</string>
  </dict>
  <key>bcdefghijklmnopabcdefghijklmnopa</key>
  <dict>
    <key>allowed_permissions</key>
    <array>
      <string>downloads</string>
    </array>
    <key>installation_mode</key>
    <string>force_installed</string>
    <key>runtime_allowed_hosts</key>
    <array>
      <string>*://good.contoso.com</string>
    </array>
    <key>runtime_blocked_hosts</key>
    <array>
      <string>*://*.contoso.com</string>
    </array>
    <key>update_url</key>
    <string>https://contoso.com/update_url</string>
  </dict>
  <key>cdefghijklmnopabcdefghijklmnopab</key>
  <dict>
    <key>blocked_install_message</key>
    <string>Custom error message.</string>
    <key>installation_mode</key>
    <string>blocked</string>
  </dict>
  <key>defghijklmnopabcdefghijklmnopabc,efghijklmnopabcdefghijklmnopabcd</key>
  <dict>
    <key>blocked_install_message</key>
    <string>Custom error message.</string>
    <key>installation_mode</key>
    <string>blocked</string>
  </dict>
  <key>fghijklmnopabcdefghijklmnopabcde</key>
  <dict>
    <key>blocked_install_message</key>
    <string>Custom removal message.</string>
    <key>installation_mode</key>
    <string>removed</string>
  </dict>
  <key>update_url:https://www.contoso.com/update.xml</key>
  <dict>
    <key>allowed_permissions</key>
    <array>
      <string>downloads</string>
    </array>
    <key>blocked_permissions</key>
    <array>
      <string>wallpaper</string>
    </array>
    <key>installation_mode</key>
    <string>allowed</string>
  </dict>
</dict>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ## <a name="http-authentication-policies"></a>HTTP 인증 정책

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="allowcrossoriginauthprompt"></a>AllowCrossOriginAuthPrompt

  #### <a name="allow-cross-origin-http-authentication-prompts"></a>Allow cross-origin HTTP Authentication prompts

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  Controls whether third-party images on a page can show an authentication prompt.

일반적으로 피싱 방어로는 해당 기능을 사용할 수 없습니다. 이 정책을 구성하지 않으면 사용하지 않도록 설정되고 타사 이미지는 인증 프롬프트를 표시할 수 없습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: AllowCrossOriginAuthPrompt
  - GP 이름: 교차 원본 HTTP 인증 프롬프트 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/HTTP 인증
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: AllowCrossOriginAuthPrompt
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: AllowCrossOriginAuthPrompt
  - 예를 들어 값:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="authnegotiatedelegateallowlist"></a>AuthNegotiateDelegateAllowlist

  #### <a name="specifies-a-list-of-servers-that-microsoft-edge-can-delegate-user-credentials-to"></a>Microsoft Edge에서 사용자 자격 증명을 위임할 수 있는 서버 목록 지정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  Microsoft Edge에서 위임할 수 있는 서버 목록을 구성합니다.

여러 서버 이름을 쉼표로 구분합니다. 와일드카드(*)를 사용할 수 있습니다.

해당 정책을 구성하지 않으면 Microsoft Edge에서 서버가 인트라넷으로 검색되더라도 사용자 자격 증명을 위임하지 않습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 문자열

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: AuthNegotiateDelegateAllowlist
  - GP 이름: Microsoft Edge에서 사용자 자격 증명을 위임할 수 있는 서버 목록 지정
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/HTTP 인증
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: AuthNegotiateDelegateAllowlist
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
"contoso.com"
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: AuthNegotiateDelegateAllowlist
  - 예를 들어 값:
``` xml
<string>contoso.com</string>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="authschemes"></a>AuthSchemes

  #### <a name="supported-authentication-schemes"></a>지원되는 인증 구성표

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  지원되는 HTTP 인증 구성표를 지정합니다.

'basic', 'digest', 'ntlm', 'negotiate'의 값을 사용하여 정책을 구성할 수 있습니다. 쉼표로 여러 값을 구분합니다.

해당 정책을 구성하지 않으면 네 가지 구성표가 모두 사용됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 문자열

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: AuthSchemes
  - GP 이름: 지원되는 인증 구성표
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/HTTP 인증
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: AuthSchemes
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
"basic,digest,ntlm,negotiate"
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: AuthSchemes
  - 예를 들어 값:
``` xml
<string>basic,digest,ntlm,negotiate</string>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="authserverallowlist"></a>AuthServerAllowlist

  #### <a name="configure-list-of-allowed-authentication-servers"></a>허용되는 인증 서버 목록 구성

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  통합 인증을 사용하도록 설정할 서버를 지정합니다. 통합 인증은 Microsoft Edge에서 프록시 또는 해당 목록의 서버에서 인증 챌린지를 받은 경우에만 사용할 수 있습니다.

여러 서버 이름을 쉼표로 구분합니다. 와일드카드(*)를 사용할 수 있습니다.

해당 정책을 구성하지 않으면 Microsoft Edge에서 서버가 인트라넷에 있는지 여부를 감지하려고 시도하여 IWA 요청에만 응답하게 됩니다. 서버가 인터넷에 있으면 Microsoft Edge에서 해당 서버로부터의 IWA 요청을 무시합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 문자열

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: AuthServerAllowlist
  - GP 이름: 허용된 인증 서버 목록 구성
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/HTTP 인증
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: AuthServerAllowlist
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
"*contoso.com,contoso.com"
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: AuthServerAllowlist
  - 예를 들어 값:
``` xml
<string>*contoso.com,contoso.com</string>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="basicauthoverhttpenabled"></a>BasicAuthOverHttpEnabled

  #### <a name="allow-basic-authentication-for-http"></a>HTTP에 대한 기본 인증 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS 88 이상

  #### <a name="description"></a>설명

  해당 정책을 사용하도록 설정하거나 설정하지 않은 경우 비보안 HTTP를 통해 받은 기본 인증 문제가 허용됩니다.

해당 정책을 사용하지 않도록 설정하면 기본 인증 체계의 비보안 HTTP 요청이 차단되고 보안 HTTPS만 허용됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: BasicAuthOverHttpEnabled
  - GP 이름: HTTP에 대해 기본 인증 허용
  - GP 경로(필수): 관리 템플릿/Microsoft Edge/HTTP 인증
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로(권장): 해당 없음
  - 값 이름: BasicAuthOverHttpEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: BasicAuthOverHttpEnabled
  - 값 예시:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="disableauthnegotiatecnamelookup"></a>DisableAuthNegotiateCnameLookup

  #### <a name="disable-cname-lookup-when-negotiating-kerberos-authentication"></a>Kerberos 인증 협상 시 CNAME 조회 해제

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  생성된 Kerberos SPN이 정식 DNS 이름(CNAME) 또는 입력한 원본 이름을 기반으로 하는지 여부를 확인합니다.

해당 정책을 사용하면 CNAME 조회가 생략되고 서버 이름(입력한 대로)이 사용됩니다.

해당 정책을 사용하지 않도록 설정하거나 구성하지 않으면 서버의 정식 이름이 사용됩니다.  정식 이름은 CNAME 조회를 통해 결정됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: DisableAuthNegotiateCnameLookup
  - GP 이름: Kerberos 인증 협상 시 CNAME 조회 해제
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/HTTP 인증
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: DisableAuthNegotiateCnameLookup
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: DisableAuthNegotiateCnameLookup
  - 예를 들어 값:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="enableauthnegotiateport"></a>EnableAuthNegotiatePort

  #### <a name="include-non-standard-port-in-kerberos-spn"></a>Kerberos SPN에 표준이 아닌 포트 포함

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  생성된 Kerberos SPN에 표준이 아닌 포트가 포함되어야 하는지 여부를 지정합니다.

해당 정책을 사용하도록 설정하고 사용자에게 URL에 표준이 아닌 포트(80 또는 443이 아닌 포트)가 포함된 경우 해당 포트는 생성된 Kerberos SPN에 포함됩니다.

해당 정책을 구성하지 않거나 사용하지 않도록 설정하는 경우 발생된 Kerberos SPN에는 어떤 경우에도 포트가 포함되지 않습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: EnableAuthNegotiatePort
  - GP 이름: Kerberos SPN에 표준이 아닌 포트 포함
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/HTTP 인증
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: EnableAuthNegotiatePort
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: EnableAuthNegotiatePort
  - 예를 들어 값:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="ntlmv2enabled"></a>NtlmV2Enabled

  #### <a name="control-whether-ntlmv2-authentication-is-enabled"></a>NTLMv2 인증 사용 여부 제어

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - MacOS (77 이상)

  #### <a name="description"></a>설명

  NTLMv2를 사용할 수 있는지 여부를 제어합니다.

모든 최신 버전의 Samba 및 Windows 서버는 NTLMv2를 지원합니다. 인증 보안이 약화되므로 이전 버전과의 호환성 문제를 해결하기 위해 NTLMv2를 사용하지 않도록 설정해야 합니다.

해당 정책을 구성하지 않으면 기본적으로 NTLMv2가 사용됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: NtlmV2Enabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="windowshelloforhttpauthenabled"></a>WindowsHelloForHTTPAuthEnabled

  #### <a name="windows-hello-for-http-auth-enabled"></a>HTTP용 Windows Hello 인증 사용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 90 이상

  #### <a name="description"></a>설명

  Windows 자격 증명 UI가 NTLM에 응답하고 인증 챌린지를 협상하는 데 사용되어야 하는지 여부를 표시합니다.

해당 정책을 사용하지 않도록 설정하면, 기본 사용자 이름과 암호 프롬프트가 NTLM에 응답하고 챌린지를 협상하는 데 사용됩니다. 해당 정책을 사용하도록 설정하거나 구성하지 않으면 Windows 자격 증명 UI가 사용됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: WindowsHelloForHTTPAuthEnabled
  - GP 이름: HTTP용 Windows Hello 인증 사용
  - GP 경로(필수): 관리 템플릿/Microsoft Edge/HTTP 인증
  - GP 경로(권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자가 재정의할 수 있습니다)/HTTP 인증
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로(권장): SOFTWARE\정책\Microsoft\Edge\권장
  - 값 이름: WindowsHelloForHTTPAuthEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ## <a name="kiosk-mode-settings-policies"></a>키오스크 모드 설정 정책

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="kioskaddressbareditingenabled"></a>KioskAddressBarEditingEnabled

  #### <a name="configure-address-bar-editing-for-kiosk-mode-public-browsing-experience"></a>키오스크 모드 공개 검색 환경에 대해 주소 표시줄 편집을 구성

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - On Windows and macOS since 87 or later

  #### <a name="description"></a>설명

  이 정책은 공개 검색 환경을 사용하는 동안 Microsoft Edge 키오스크 모드에만 적용됩니다.

이 정책을 사용하도록 설정하거나 구성하지 않은 경우 사용자가 주소 표시줄의 URL을 변경할 수 있습니다.

이 정책을 사용하지 않도록 설정하면 사용자가 주소 표시줄에서 URL을 변경할 수 없습니다.

키오스크 모드를 구성하는 방법에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2137578](https://go.microsoft.com/fwlink/?linkid=2137578)를 참조하세요.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: KioskAddressBarEditingEnabled
  - GP 이름: 키오스크 모드 공개 검색 환경에 대해 주소 표시줄 편집 구성
  - GP 경로(필수): 관리 템플릿/Microsoft Edge/키오스크 모드 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: KioskAddressBarEditingEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: KioskAddressBarEditingEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="kioskdeletedownloadsonexit"></a>KioskDeleteDownloadsOnExit

  #### <a name="delete-files-downloaded-as-part-of-kiosk-session-when-microsoft-edge-closes"></a>Microsoft Edge가 닫히는 경우 키오스크 세션의 일부로 다운로드한 파일을 삭제

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows (87 이상)

  #### <a name="description"></a>설명

  이 정책은 Microsoft Edge 키오스크 모드에만 적용됩니다.

이 정책을 사용하도록 설정하면 키오스크 세션의 일부로 다운로드한 파일이 Microsoft Edge를 닫을 때마다 삭제됩니다.

이 정책을 사용하지 않도록 설정하거나 구성하지 않는 경우, Microsoft Edge가 닫힐 때 키오스크 세션의 일부로 다운로드된 파일이 삭제되지 않습니다.

키오스크 모드를 구성하는 방법에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2137578](https://go.microsoft.com/fwlink/?linkid=2137578)를 참조하세요.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: KioskDeleteDownloadsOnExit
  - GP 이름: Microsoft Edge가 닫히는 경우 키오스크 세션의 일부로 다운로드된 파일 삭제
  - GP 경로(필수): 관리 템플릿/Microsoft Edge/키오스크 모드 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: KioskDeleteDownloadsOnExit
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ## <a name="manageability-policies"></a>관리 가능성 정책

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="mamenabled"></a>MAMEnabled

  #### <a name="mobile-app-management-enabled"></a>모바일 앱 관리 사용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 macOS(89 이상)

  #### <a name="description"></a>설명

  Microsoft Edge 브라우저가 Intune 응용 프로그램 관리 서비스에서 정책을 검색하고 사용자 프로필에 적용할 수 있도록 허용합니다.

해당 정책을 사용하도록 설정하거나 구성하지 않은 경우 MAM(모바일 앱 관리) 정책을 적용할 수 있습니다.

해당 정책을 사용하지 않도록 설정할 경우, Microsoft Edge가 Intune과 통신하여 MAM 정책을 요청하지 않습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: MAMEnabled
  - GP 이름: 모바일 앱 관리 사용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/관리 가능성
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로(권장): 해당 없음
  - 값 이름: MAMEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: MAMEnabled
  - 예를 들어 값:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ## <a name="native-messaging-policies"></a>기본 메시지 정책

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="nativemessagingallowlist"></a>NativeMessagingAllowlist

  #### <a name="control-which-native-messaging-hosts-users-can-use"></a>사용자가 사용할 수 있는 기본 메시지 호스트 제어

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  정책을 설정하면 거부 목록이 적용되지 않는 기본 메시징 호스트를 지정합니다. 거부 목록 값 *는 명시적으로 허용되지 않는 한 모든 기본 메시징 호스트가 거부된다는 것을 의미합니다.

모든 기본 메시징 호스트는 기본적으로 허용됩니다. 그러나 정책에 의해 기본 메시징 호스트가 거부된 경우 관리자는 허용 목록을 사용하여 해당 정책을 변경할 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: NativeMessagingAllowlist
  - GP 이름: 사용자가 사용할 수 있는 기본 메시지 호스트 제어
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/기본 메시지
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\NativeMessagingAllowlist
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\NativeMessagingAllowlist\1 = "com.native.messaging.host.name1"
SOFTWARE\Policies\Microsoft\Edge\NativeMessagingAllowlist\2 = "com.native.messaging.host.name2"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: NativeMessagingAllowlist
  - 예를 들어 값:
``` xml
<array>
  <string>com.native.messaging.host.name1</string>
  <string>com.native.messaging.host.name2</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="nativemessagingblocklist"></a>NativeMessagingBlocklist

  #### <a name="configure-native-messaging-block-list"></a>기본 메시지 차단 목록 구성

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  이 정책을 설정하면 로드되지 않아야 하는 기본 메시징 호스트가 지정됩니다. 거부 목록 값 *는 명시적으로 허용되지 않는 한 모든 기본 메시징 호스트가 거부된다는 것을 의미합니다.

해당 정책을 설정하지 않은 경우 Microsoft Edge는 설치된 모든 기본 메시징 호스트를 로드합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: NativeMessagingBlocklist
  - GP 이름: 기본 메시지 차단 목록 구성
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/기본 메시지
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\NativeMessagingBlocklist
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\NativeMessagingBlocklist\1 = "com.native.messaging.host.name1"
SOFTWARE\Policies\Microsoft\Edge\NativeMessagingBlocklist\2 = "com.native.messaging.host.name2"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: NativeMessagingBlocklist
  - 예를 들어 값:
``` xml
<array>
  <string>com.native.messaging.host.name1</string>
  <string>com.native.messaging.host.name2</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="nativemessaginguserlevelhosts"></a>NativeMessagingUserLevelHosts

  #### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a>사용자 수준 기본 메시지 호스트 허용(관리자 권한없이 설치됨)

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  해당 정책을 사용함으로 설정하거나 설정하지 않은 경우 Microsoft Edge는 사용자 수준에서 설치된 기본 메시징 호스트를 사용할 수 있습니다.

해당 정책을 사용 안함으로 설정하면 Microsoft Edge는 이같은 호스트가 시스템 수준으로 설치된 경우에만 사용할 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: NativeMessagingUserLevelHosts
  - GP 이름: 사용자 수준 기본 메시지 호스트 허용(관리자 권한없이 설치됨)
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/기본 메시지
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: NativeMessagingUserLevelHosts
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: NativeMessagingUserLevelHosts
  - 예를 들어 값:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ## <a name="password-manager-and-protection-policies"></a>암호 관리자 및 보호 정책

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="passwordmanagerenabled"></a>PasswordManagerEnabled

  #### <a name="enable-saving-passwords-to-the-password-manager"></a>암호 관리자에 암호 저장 사용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  Microsoft Edge에서 사용자 암호를 저장하도록 설정합니다.

해당 정책을 사용하면 사용자가 Microsoft Edge에서 암호를 저장할 수 있습니다. 다음에 사이트 방문 시 Microsoft Edge에서 암호를 자동으로 입력합니다.

해당 정책을 사용하지 않도록 설정하면 사용자는 새 암호를 저장할 수 없지만 이전에 저장한 암호를 계속 사용할 수 있습니다.

해당 정책을 사용하거나 사용하지 않도록 설정하면 사용자는 Microsoft Edge에서 해당 정책을 변경하거나 재정의할 수 없습니다. 해당 정책을 구성하지 않으면 사용자는 암호를 저장할 수 있고 해당 기능을 해제할 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: PasswordManagerEnabled
  - GP 이름: 암호 관리자에 암호 저장 사용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/암호 관리자 및 보호
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/암호 관리자 및 보호
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: PasswordManagerEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: PasswordManagerEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="passwordmonitorallowed"></a>PasswordMonitorAllowed

  #### <a name="allow-users-to-be-alerted-if-their-passwords-are-found-to-be-unsafe"></a>암호가 안전하지 않은 것으로 확인되면 사용자에게 알림 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 85 이상

  #### <a name="description"></a>설명

  Microsoft Edge가 사용자 암호를 모니터하도록 허용합니다.

이 정책을 활성화하고 사용자가 정책 사용에 동의하면 Microsoft Edge에 저장된 암호 중 하나라도 안전하지 않은 것으로 발견되면 사용자에게 경고합니다. Microsoft Edge에 경고가 표시되며 이 정보는 설정 > 암호 > 암호 모니터에서도 확인할 수 있습니다.

이 정책을 비활성화하면 사용자에게 이 기능을 사용할 수 있는 권한을 요청하지 않습니다. 해당 암호는 검색되지 않으며 경고도 표시되지 않습니다.

정책을 활성화하거나 구성하지 않으면 사용자가 이 기능을 켜거나 끌 수 있습니다.

Microsoft Edge에서 안전하지 않은 암호를 찾는 방법에 대해 자세히 알아보려면 다음을 참조하세요. [https://go.microsoft.com/fwlink/?linkid=2133833](https://go.microsoft.com/fwlink/?linkid=2133833)

추가 지침:

이 정책은 중요한 문구와 함께 권장 및 필수로 설정할 수 있습니다.

필수 활성화: 개별 사용자 동의가 특정 사용자에 대해 이 기능을 사용하기 위한 전제 조건이므로 이 정책에는 필수 활성화 설정이 없습니다. 정책을 필수로 설정한 경우 설정의 UI가 변경되지 않으며, edge://policy에 다음 오류 메시지가 표시됩니다.

오류 상태 메시지의 예: "암호 모니터는 개별 사용자의 동의를 얻어야하기 때문에 이 정책 값은 무시됩니다. 조직의 사용자에게 설정 > 프로필 > 암호로 이동하여 해당 기능을 켜도록 요청할 수 있습니다. "

권장 활성화: 정책을 권장 활성화로 설정하면 설정의 UI는 '꺼짐' 상태로 유지되지만, 마우스로 가리킬 시 "조직에서 이 설정에 대한 특정 값을 권장했지만 다른 값을 선택하셨습니다" 라는 설명이 표시되는 서류 가방 아이콘이 옆에 표시됩니다. 

필수 및 권장 비활성화: 이 두 가지 상태 모두 정상적인 방식으로 작동하며, 일반적인 캡션이 사용자에게 표시됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: PasswordMonitorAllowed
  - GP 이름: 암호가 안전하지 않은 것으로 확인되면 사용자에게 알림 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/암호 관리자 및 보호
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/암호 관리자 및 보호
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: PasswordMonitorAllowed
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="passwordprotectionchangepasswordurl"></a>PasswordProtectionChangePasswordURL

  #### <a name="configure-the-change-password-url"></a>암호 변경 URL 구성

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  변경 암호 URL(HTTP 및 HTTPS 구성표에만 해당)을 구성합니다.

암호 보호 서비스에서 브라우저에 경고를 표시한 후 사용자를 해당 URL로 보내 암호를 변경하도록 합니다.

해당 정책을 사용하면 암호 보호 서비스에서 사용자를 해당 URL로 보내 암호를 변경하도록 합니다.

해당 정책을 사용하지 않도록 설정하거나 구성하지 않으면 암호 보호 서비스에서 사용자를 암호 변경 URL로 리디렉션하지 않습니다.

이 정책은 Microsoft Active Directory 도메인에 가입된 윈도우즈 인스턴스, 장치 관리를 위해 등록된 윈도우즈 10 Pro 또는 Enterprise 인스턴스 또는 MDM을 통해 관리되거나 MCX를 통해 도메인에 가입된 MacOS 인스턴스에서만 사용할 수 있습니다..

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: PasswordProtectionChangePasswordURL
  - GP 이름: 암호 변경 URL 구성
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/암호 관리자 및 보호
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: PasswordProtectionChangePasswordURL
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
"https://contoso.com/change_password.html"
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: PasswordProtectionChangePasswordURL
  - 예를 들어 값:
``` xml
<string>https://contoso.com/change_password.html</string>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="passwordprotectionloginurls"></a>PasswordProtectionLoginURLs

  #### <a name="configure-the-list-of-enterprise-login-urls-where-the-password-protection-service-should-capture-salted-hashes-of-a-password"></a>암호 보호 서비스에서 암호 보호 서비스가 솔트 암호 캐시를 캡처해야 하는 엔터프라이즈 로그인 URL 목록 구성

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  Microsoft Edge에서 솔트 암호 해시를 캡처하고 암호 재사용 감지에 사용하는 엔터프라이즈 로그인 URL 목록(HTTP 및 HTTPS 구성표만 해당)을 구성합니다.

해당 정책을 사용하면 암호 보호 서비스에서 정의된 URL에서 암호 지문을 캡처합니다.

해당 정책을 사용하지 않도록 설정하거나 구성하지 않으면 암호 지문을 캡처하지 않습니다.

이 정책은 Microsoft Active Directory 도메인에 가입된 윈도우즈 인스턴스, 장치 관리를 위해 등록된 윈도우즈 10 Pro 또는 Enterprise 인스턴스 또는 MDM을 통해 관리되거나 MCX를 통해 도메인에 가입된 MacOS 인스턴스에서만 사용할 수 있습니다..

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: PasswordProtectionLoginURLs
  - GP 이름: 암호 보호 서비스에서 암호 보호 서비스가 솔트 암호 캐시를 캡처해야 하는 엔터프라이즈 로그인 URL 목록 구성
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/암호 관리자 및 보호
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\PasswordProtectionLoginURLs
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\PasswordProtectionLoginURLs\1 = "https://contoso.com/login.html"
SOFTWARE\Policies\Microsoft\Edge\PasswordProtectionLoginURLs\2 = "https://login.contoso.com"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: PasswordProtectionLoginURLs
  - 예를 들어 값:
``` xml
<array>
  <string>https://contoso.com/login.html</string>
  <string>https://login.contoso.com</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="passwordprotectionwarningtrigger"></a>PasswordProtectionWarningTrigger

  #### <a name="configure-password-protection-warning-trigger"></a>암호 보호 경고 트리거 구성

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  암호 보호 경고를 트리거할 시기를 제어할 수 있습니다. 암호 보호는 사용자가 잠재적으로 의심된 사이트에서 보호된 암호를 재사용하는 경우 경고를 알립니다.

[PasswordProtectionLoginURLs](#passwordprotectionloginurls) 및 [PasswordProtectionChangePasswordURL](#passwordprotectionchangepasswordurl) 정책을 사용하여 보호할 암호를 구성할 수 있습니다.

예외: [PasswordProtectionLoginURLs](#passwordprotectionloginurls) 및 [PasswordProtectionChangePasswordURL](#passwordprotectionchangepasswordurl)에 나열된 사이트에 대한 암호를 비롯하여 [SmartScreenAllowListDomains](#smartscreenallowlistdomains)에 나열된 사이트에 대한 암호만 암호 보호 경고를 트리거하지 않습니다.

암호 보호 경고를 표시하지 않으려면 'PasswordProtectionWarningOff'로 설정합니다.

사용자가 non-allowlisted 사이트에서 보호된 암호를 재사용하는 경우 암호 보호 경고를 표시하려면 'PasswordProtectionWarningOnPasswordReuse'로 설정합니다.

해당 정책을 사용하지 않도록 설정하거나 구성하지 않으면 경고 트리거가 표시되지 않습니다.

정책 옵션 매핑:

* PasswordProtectionWarningOff (0) = 암호 보호 경고 꺼짐

* PasswordProtectionWarningOnPasswordReuse (1) = 암호를 재사용하면 암호 보호 경고가 트리거됨

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: PasswordProtectionWarningTrigger
  - GP 이름: 암호 보호 경고 트리거 구성
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/암호 관리자 및 보호
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: PasswordProtectionWarningTrigger
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: PasswordProtectionWarningTrigger
  - 예를 들어 값:
``` xml
<integer>1</integer>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="passwordrevealenabled"></a>PasswordRevealEnabled

  #### <a name="enable-password-reveal-button"></a>암호 노출 사용 단추

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - On Windows and macOS since 87 or later

  #### <a name="description"></a>설명

  웹 사이트 암호 입력 필드의 브라우저 암호 노출 단추의 기본 표시를 구성할 수 있도록 합니다. 

이 정책을 사용하도록 설정하거나 구성하지 않으면 브라우저의 사용자 설정은 기본적으로 암호 노출 단추를 표시합니다.

이 정책을 사용하지 않도록 설정하면 브라우저의 사용자 설정은 암호 노출 단추를 표시하지 않습니다.

접근성을 위해 사용자는 기본 정책에서 브라우저 설정을 변경할 수 있습니다.

이 정책은 브라우저 암호 노출 단추에만 영향을 주며 웹 사이트의 사용자 지정 노출 단추에는 영향을 주지 않습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 아니요
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: PasswordRevealEnabled
  - GP 이름: 암호 노출 사용 단추
  - GP 경로 (필수): 해당 없음
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/암호 관리자 및 보호
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): 해당 없음
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: PasswordRevealEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: PasswordRevealEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ## <a name="performance-policies"></a>성능 정책

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="startupboostenabled"></a>StartupBoostEnabled

  #### <a name="enable-startup-boost"></a>시작 부스트 활성화

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows (88 이상)

  #### <a name="description"></a>설명

  Microsoft Edge 프로세스를 OS 로그인에서 시작하고 마지막 브라우저 창이 닫힌 후 백그라운드에서 다시 시작하도록 합니다.

Microsoft Edge가 배경 모드에서 실행되고 있는 경우 마지막 창이 닫힐 때 브라우저가 종료되지 않을 수 있으며 창이 닫힐 때 백그라운드에서 브라우저가 다시 시작되지 않습니다. Microsoft Edge 배경 모드 동작을 구성한 이후 수행되는 작업에 대한 자세한 내용은 [BackgroundModeEnabled](#backgroundmodeenabled) 정책을 참조하세요.

해당 정책을 사용하면 시작 부스트가 설정됩니다.

해당 정책을 사용하지 않으면 시작 부스트가 해제됩니다.

해당 정책을 구성하지 않으면 시작 부스트가 처음에 해제되어 있거나 설정되어 있을 수 있습니다. 사용자는 edge://settings/system에서 해당 동작을 구성할 수 있습니다.

시작 부스트에 대해 자세히 알아보기: [https://go.microsoft.com/fwlink/?linkid=2147018](https://go.microsoft.com/fwlink/?linkid=2147018)

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: StartupBoostEnabled
  - GP 이름: 시작 부스트 사용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/성능
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/성능
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: StartupBoostEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ## <a name="printing-policies"></a>인쇄 정책

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="defaultprinterselection"></a>DefaultPrinterSelection

  #### <a name="default-printer-selection-rules"></a>기본 프린터 선택 규칙

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  Microsoft Edge 기본 프린터 선택 규칙을 재정의합니다. 해당 정책은 사용자가 페이지를 처음 인쇄하려고 할 때 Microsoft Edge에서 기본 프린터를 선택하는 규칙을 결정합니다.

해당 정책을 설정하면 Microsoft Edge에서 지정된 모든 특성과 일치하는 프린터를 찾고 해당 프린터를 기본 프린터로 사용합니다. 조건을 충족하는 프린터가 여러 개 있는 경우 일치하는 첫 번째 프린터가 사용됩니다.

해당 정책을 구성하지 않거나 시간 제한 내에 일치하는 프린터를 찾지 못한 경우 기본 제공된 PDF 프린터를 기본 프린터로 선택하고 PDF 프린터가 없으면 기본 프린터를 선택하지 않습니다.

해당 값은 다음 구성표를 따르는 JSON 개체로 구문 분석됩니다. { "type": "object", "properties": { "idPattern": { "description": "Regular expression to match printer id.", "type": "string" }, "namePattern": { "description": "Regular expression to match printer display name.", "type": "string" } } }

필드를 생략하면 모든 값이 일치함을 의미합니다. 예를 들어 연결을 지정하지 않으면 인쇄 미리 보기에서 모든 유형의 로컬 프린터를 검색하기 시작합니다. 정규식 패턴은 JavaScript RegExp 구문을 따라야 하고 대/소문자를 구분해야 합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: DefaultPrinterSelection
  - GP 이름: 기본 프린터 선택 규칙
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/인쇄
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: DefaultPrinterSelection
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
"{ \"idPattern\": \".*public\", \"namePattern\": \".*Color\" }"
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: DefaultPrinterSelection
  - 예를 들어 값:
``` xml
<string>{ "idPattern": ".*public", "namePattern": ".*Color" }</string>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="printheaderfooter"></a>PrintHeaderFooter

  #### <a name="print-headers-and-footers"></a>머리글 및 바닥글 인쇄

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  인쇄 대화 상자에서 ‘머리글 및 바닥글'을 강제로 설정하거나 해제합니다.

해당 정책을 구성하지 않으면 사용자는 머리글 및 바닥글 인쇄 여부를 결정할 수 있습니다.

해당 정책을 사용하지 않도록 설정하면 사용자는 머리글 및 바닥글을 인쇄할 수 없습니다.

해당 정책을 사용하도록 설정하면 사용자는 항상 머리글 및 바닥글을 인쇄합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: PrintHeaderFooter
  - GP 이름: 머리글 및 바닥글 인쇄
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/인쇄
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/인쇄
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: PrintHeaderFooter
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: PrintHeaderFooter
  - 예를 들어 값:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="printpreviewusesystemdefaultprinter"></a>PrintPreviewUseSystemDefaultPrinter

  #### <a name="set-the-system-default-printer-as-the-default-printer"></a>시스템 기본 프린터를 기본 프린터로 설정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  Microsoft Edge에서 최근 사용한 프린터 대신 인쇄 미리 보기에서 기본 선택 항목으로 시스템 기본 프린터를 사용하도록 지시합니다.

해당 정책을 사용하지 않도록 설정하거나 구성하지 않으면 인쇄 미리 보기에서 최근에 사용한 프린터를 기본 대상 선택으로 사용합니다.

해당 정책을 사용하면 인쇄 미리 보기에서 OS 시스템 기본 프린터를 기본 대상 선택으로 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: PrintPreviewUseSystemDefaultPrinter
  - GP 이름: 시스템 기본 프린터를 기본 프린터로 설정
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/인쇄
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/인쇄
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: PrintPreviewUseSystemDefaultPrinter
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: PrintPreviewUseSystemDefaultPrinter
  - 예를 들어 값:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="printrasterizationmode"></a>PrintRasterizationMode

  #### <a name="print-rasterization-mode"></a>인쇄 래스터화 모드

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 90 이상

  #### <a name="description"></a>설명

  Windows에서 Microsoft Edge가 인쇄하는 방법을 제어합니다.

Windows에서 포스트스크립트가 아닌 프린터로 인쇄할 경우 인쇄 작업을 래스터화하여 올바르게 인쇄해야 하는 경우가 있습니다.

이 정책을 '전체'로 설정하거나 구성하지 않으면 필요한 경우 Microsoft Edge에서 전체 페이지 래스터화를 수행합니다.

이 정책을 '빠름'으로 설정하면 Microsoft Edge에서 래스터화 양을 줄여 인쇄 작업 크기를 줄이고 인쇄 속도를 높일 수 있습니다.

정책 옵션 매핑:

* 전체(0) = 전체 페이지 래스터화

* 빠름(1) = 가능한 경우 래스터화 방지

이 정책을 구성할 때 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>ADMX(그룹 정책) 정보

  - GP 고유 이름: PrintRasterizationMode
  - GP 이름: 인쇄 래스터화 모드
  - GP 경로(필수): 관리 템플릿/Microsoft Edge/인쇄
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로(권장): 해당 없음
  - 값 이름: PrintRasterizationMode
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="printertypedenylist"></a>PrinterTypeDenyList

  #### <a name="disable-printer-types-on-the-deny-list"></a>거부 목록에서 프린터 유형을 사용하지 않도록 설정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS 88 이상

  #### <a name="description"></a>설명

  거부 목록에 있는 프린터 유형을 검색하거나 해당 기능을 가져오지 않습니다.

모든 프린터 유형을 거부 목록에 배치하면 문서의 인쇄 대상이 없으므로 인쇄가 효과적으로 비활성화됩니다.

이 정책을 구성하지 않거나 프린터 목록이 비어 있으면 모든 프린터 유형을 검색할 수 있습니다.

프린터 대상에는 확장 프린터와 로컬 프린터가 포함됩니다. 확장 프린터는 인쇄 공급자 대상이라고도 하며 Microsoft Edge 확장에 속하는 대상을 포함합니다.
로컬 프린터는 기본 인쇄 대상이라고도 하며 로컬 컴퓨터 및 공유 네트워크 프린터에서 사용할 수 있는 대상을 포함합니다.

정책 옵션 매핑:

* privet (privet) = Zeroconf 기반 (mDNS + DNS-SD) 프로토콜 대상

* extension (extension) = 확장 기반 대상

* pdf (pdf) = ‘PDF로 저장’ 대상

* local (local) = 로컬 프린터 대상

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: PrinterTypeDenyList
  - GP 이름: 거부 목록에서 프린터 유형을 사용하지 않도록 설정
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/인쇄
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\Policies\Microsoft\Edge\PrinterTypeDenyList
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\PrinterTypeDenyList\1 = "local"
SOFTWARE\Policies\Microsoft\Edge\PrinterTypeDenyList\2 = "privet"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: PrinterTypeDenyList
  - 예제 값:
``` xml
<array>
  <string>local</string>
  <string>privet</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="printingallowedbackgroundgraphicsmodes"></a>PrintingAllowedBackgroundGraphicsModes

  #### <a name="restrict-background-graphics-printing-mode"></a>배경 그래픽 인쇄 모드 제한

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 macOS(89 이상)

  #### <a name="description"></a>설명

  배경 그래픽 인쇄 모드를 제한합니다. 해당 정책을 설정하지 않은 경우 배경 그래픽 인쇄에는 제한이 없습니다.

정책 옵션 매핑:

* 모든 경우(모든 경우) = 배경 그래픽을 사용 그리고 사용하지 않고 인쇄할 수 있도록 허용

* 사용(사용) = 배경 그래픽을 사용해야 인쇄 허용

* 사용 안함(사용 안함) = 배경 그래픽을 사용하지 않아야 인쇄 허용

이 정책을 구성할 때 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: PrintingAllowedBackgroundGraphicsModes
  - GP 이름: 배경 그래픽 인쇄 모드 제한
  - GP 경로(필수): 관리 템플릿/Microsoft Edge/인쇄
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로(권장): 해당 없음
  - 값 이름: PrintingAllowedBackgroundGraphicsModes
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
"enabled"
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: PrintingAllowedBackgroundGraphicsModes
  - 값 예시:
``` xml
<string>enabled</string>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="printingbackgroundgraphicsdefault"></a>PrintingBackgroundGraphicsDefault

  #### <a name="default-background-graphics-printing-mode"></a>기본 배경 그래픽 인쇄 모드

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 macOS(89 이상)

  #### <a name="description"></a>설명

  배경 그래픽 인쇄에 마지막으로 사용된 설정을 재정의합니다.
이 설정을 사용하면 배경 그래픽 인쇄가 사용하도록 설정됩니다.
이 설정을 사용하지 않도록 설정하면 배경 그래픽 인쇄를 사용할 수 없습니다.

정책 옵션 매핑:

* 사용(사용) = 기본적으로 배경 그래픽 인쇄 모드 사용 설정

* 사용 안함(사용 안함) = 기본적으로 배경 그래픽 인쇄 모드를 사용 안함으로 설정

이 정책을 구성할 때 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: PrintingBackgroundGraphicsDefault
  - GP 이름: 기본 배경 그래픽 인쇄 모드
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/인쇄
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로(권장): 해당 없음
  - 값 이름: PrintingBackgroundGraphicsDefault
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
"enabled"
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: PrintingBackgroundGraphicsDefault
  - 예를 들어 값:
``` xml
<string>enabled</string>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="printingenabled"></a>PrintingEnabled

  #### <a name="enable-printing"></a>인쇄 사용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  Microsoft Edge에서 인쇄할 수 있으며 해당 설정을 사용자가 변경하지 못하도록 합니다.

해당 정책을 사용하도록 설정하거나 구성하지 않으면 사용자가 인쇄할 수 있습니다.

해당 정책을 사용하지 않도록 설정하면 사용자는 Microsoft Edge에서 인쇄할 수 없습니다. 렌치 메뉴, 확장, JavaScript 응용 프로그램 등에서 인쇄를 해제합니다. 사용자는 인쇄하는 동안 Microsoft Edge를 우회하는 플러그인에서 계속 인쇄할 수 있습니다. 예를 들어 특정 Adobe Flash 응용 프로그램의 상황에 맞는 메뉴에서 인쇄 옵션을 사용할 수 있는데 이는 해당 정책에서 다루지 않습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: PrintingEnabled
  - GP 이름: 인쇄 사용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/인쇄
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: PrintingEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: PrintingEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="printingpapersizedefault"></a>PrintingPaperSizeDefault

  #### <a name="default-printing-page-size"></a>기본 인쇄 페이지 크기

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (86 이상)

  #### <a name="description"></a>설명

  기본 인쇄 페이지 크기를 재정의합니다.

목록에 필요한 용지 크기가 없는 경우 이름에 나열된 형식 중 하나 또는 '사용자 지정'을 포함해야 합니다. '사용자 지정' 값이 제공되면 custom_size 속성을 지정해야 합니다. 이는 원하는 높이와 너비를 마이크로 미터 단위로 설명합니다. 그렇지 않은 경우에는 custom_size 속성을 지정할 수 없습니다. 이러한 규칙을 위반하는 정책은 무시됩니다.

사용자가 선택한 프린터에서 페이지 크기를 사용할 수 없는 경우 이 정책은 무시됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - Dictionary

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: PrintingPaperSizeDefault
  - GP 이름: 기본 인쇄 페이지 크기
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/인쇄
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: PrintingPaperSizeDefault
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\PrintingPaperSizeDefault = {
  "custom_size": {
    "height": 297000, 
    "width": 210000
  }, 
  "name": "custom"
}
```

  ##### <a name="compact-example-value"></a>예제 값 압축:

  ```
  SOFTWARE\Policies\Microsoft\Edge\PrintingPaperSizeDefault = {"custom_size": {"height": 297000, "width": 210000}, "name": "custom"}
  ```
  

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: PrintingPaperSizeDefault
  - 예를 들어 값:
``` xml
<key>PrintingPaperSizeDefault</key>
<dict>
  <key>custom_size</key>
  <dict>
    <key>height</key>
    <integer>297000</integer>
    <key>width</key>
    <integer>210000</integer>
  </dict>
  <key>name</key>
  <string>custom</string>
</dict>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="usesystemprintdialog"></a>UseSystemPrintDialog

  #### <a name="print-using-system-print-dialog"></a>시스템 인쇄 대화 상자를 사용하여 인쇄

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  인쇄 미리 보기 대신 시스템 인쇄 대화 상자를 표시합니다.

해당 정책을 사용하면 사용자가 페이지를 인쇄할 때 Microsoft Edge에서 기본 제공된 인쇄 미리 보기 대신 시스템 인쇄 대화 상자를 엽니다.

해당 정책을 구성하지 않거나 사용하지 않도록 설정하면 인쇄 명령에서 Microsoft Edge 인쇄 미리 보기 화면을 트리거합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: UseSystemPrintDialog
  - GP 이름: 시스템 인쇄 대화 상자를 사용하여 인쇄
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/인쇄
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: UseSystemPrintDialog
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: UseSystemPrintDialog
  - 예를 들어 값:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ## <a name="proxy-server-policies"></a>프록시 서버 정책

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="proxybypasslist"></a>ProxyBypassList

  #### <a name="configure-proxy-bypass-rules-deprecated"></a>프록시 무시 규칙 구성(사용하지 않음)

  >DEPRECATED: 해당 정책은 사용되지 않습니다. 현재 지원되고 있지만 이후 릴리스에서는 더 이상 사용되지 않을 예정입니다.
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  해당 정책은 더 이상 사용되지 않습니다. 대신 [ProxySettings](#proxysettings)를 사용하세요. Microsoft Edge 버전 91에서 작동하지 않습니다.

Microsoft Edge가 모든 프록시를 우회하는 호스트 목록을 정의합니다.

해당 정책은 [ProxySettings](#proxysettings) 정책이 지정되지 않고 사용자가 [ProxyMode](#proxymode) 정책에서 fixed_servers를 선택한 경우에만 적용됩니다. 프록시 정책을 구성하기 위해 다른 모드를 선택한 경우 해당 정책을 사용하지 않도록 설정하거나 구성하지 않아야 합니다.

해당 정책을 사용하면 Microsoft Edge가 프록시를 사용하지 않는 호스트 목록을 만들 수 있습니다.

해당 정책을 구성하지 않으면 Microsoft Edge가 프록시를 우회하는 호스트 목록이 생성되지 않습니다. 프록시 정책을 설정하는 다른 방법을 지정한 경우 해당 정책을 구성하지 않아야 합니다.

자세한 예제를 보려면 [https://go.microsoft.com/fwlink/?linkid=2094936](https://go.microsoft.com/fwlink/?linkid=2094936)으로 이동하세요.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ProxyBypassList
  - GP 이름: 프록시 무시 규칙 구성(사용하지 않음)
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/프록시 서버
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: ProxyBypassList
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
"https://www.contoso.com, https://www.fabrikam.com"
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ProxyBypassList
  - 예를 들어 값:
``` xml
<string>https://www.contoso.com, https://www.fabrikam.com</string>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="proxymode"></a>ProxyMode

  #### <a name="configure-proxy-server-settings-deprecated"></a>프록시 서버 설정 구성(사용하지 않음)

  >DEPRECATED: 해당 정책은 사용되지 않습니다. 현재 지원되고 있지만 이후 릴리스에서는 더 이상 사용되지 않을 예정입니다.
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  해당 정책은 더 이상 사용되지 않습니다. 대신 [ProxySettings](#proxysettings)를 사용하세요. Microsoft Edge 버전 91에서 작동하지 않습니다.

해당 정책을 사용 설정하면 Microsoft Edge에서 사용하는 프록시 서버를 지정할 수 있으며 사용자가 프록시 설정을 변경하지 못하도록 합니다. Microsoft Edge는 명령줄에서 지정한 모든 프록시 관련 옵션을 무시합니다. 해당 정책은 [ProxySettings](#proxysettings) 정책이 지정되지 않은 경우에만 적용됩니다.

다음 옵션 중 하나를 선택하면 다른 옵션은 무시됩니다.
  * direct = 프록시 서버를 사용하지 않고 항상 직접 연결
  * system = 시스템 프록시 설정 사용
  * auto_detect = 프록시 설정 자동 검색

다음 옵션을 사용하도록 선택하는 경우:
  * fixed_servers = 고정 프록시 서버 [ProxyServer](#proxyserver) 및 [ProxyBypassList](#proxybypasslist)를 사용하여 추가 옵션을 지정할 수 있습니다.
  * pac_script = .pac 프록시 스크립트 [ProxyPacUrl](#proxypacurl)을 사용하여 프록시 .pac 파일에 대한 URL을 설정합니다.

자세한 예제를 보려면 [https://go.microsoft.com/fwlink/?linkid=2094936](https://go.microsoft.com/fwlink/?linkid=2094936)으로 이동하세요.

해당 정책을 구성하지 않으면 사용자는 자신의 프록시 설정을 선택할 수 있습니다.

정책 옵션 매핑:

* ProxyDisabled (direct) = 프록시 사용 안 함

* ProxyAutoDetect (auto_detect) = 프록시 설정 자동 검색

* ProxyPacScript (pac_script) = .pac 프록시 스크립트 사용

* ProxyFixedServers (fixed_servers) = 고정 프록시 서버 사용

* ProxyUseSystem (system) = 시스템 프록시 설정 사용

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ProxyMode
  - GP 이름: 프록시 서버 설정 구성(사용하지 않음)
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/프록시 서버
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: ProxyMode
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
"direct"
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ProxyMode
  - 예를 들어 값:
``` xml
<string>direct</string>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="proxypacurl"></a>ProxyPacUrl

  #### <a name="set-the-proxy-pac-file-url-deprecated"></a>프록시 .pac 파일 URL 설정(사용하지 않음)

  >DEPRECATED: 해당 정책은 사용되지 않습니다. 현재 지원되고 있지만 이후 릴리스에서는 더 이상 사용되지 않을 예정입니다.
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  해당 정책은 더 이상 사용되지 않습니다. 대신 [ProxySettings](#proxysettings)를 사용하세요. Microsoft Edge 버전 91에서 작동하지 않습니다.

프록시 자동 구성(PAC) 파일의 URL을 지정합니다.

해당 정책은 [ProxySettings](#proxysettings) 정책이 지정되지 않고 사용자가 [ProxyMode](#proxymode) 정책에서 pac_script를 선택한 경우에만 적용됩니다. 프록시 정책을 구성하기 위해 다른 모드를 선택한 경우 해당 정책을 사용하지 않도록 설정하거나 구성하지 않아야 합니다.

해당 정책을 사용하면 PAC 파일의 URL을 지정하여 브라우저가 특정 웹 사이트를 가져오는 데 적합한 프록시 서버를 자동으로 선택하는 방법을 정의할 수 있습니다.

해당 정책을 사용하지 않도록 설정하거나 구성하지 않으면 PAC 파일을 지정하지 않습니다. 프록시 정책을 설정하는 다른 방법을 지정한 경우 해당 정책을 구성하지 않아야 합니다.

자세한 예제를 보려면 [https://go.microsoft.com/fwlink/?linkid=2094936](https://go.microsoft.com/fwlink/?linkid=2094936)을 참조하세요.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ProxyPacUrl
  - GP 이름: 프록시 .pac 파일 URL 설정(사용하지 않음)
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/프록시 서버
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: ProxyPacUrl
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
"https://internal.contoso.com/example.pac"
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ProxyPacUrl
  - 예를 들어 값:
``` xml
<string>https://internal.contoso.com/example.pac</string>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="proxyserver"></a>ProxyServer

  #### <a name="configure-address-or-url-of-proxy-server-deprecated"></a>프록시 서버 주소 또는 URL 구성(사용하지 않음)

  >DEPRECATED: 해당 정책은 사용되지 않습니다. 현재 지원되고 있지만 이후 릴리스에서는 더 이상 사용되지 않을 예정입니다.
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  해당 정책은 더 이상 사용되지 않습니다. 대신 [ProxySettings](#proxysettings)를 사용하세요. Microsoft Edge 버전 91에서 작동하지 않습니다.

프록시 서버의 URL을 지정합니다.

해당 정책은 [ProxySettings](#proxysettings) 정책이 지정되지 않고 사용자가 [ProxyMode](#proxymode) 정책에서 fixed_servers를 선택한 경우에만 적용됩니다. 프록시 정책을 구성하기 위해 다른 모드를 선택한 경우 해당 정책을 사용하지 않도록 설정하거나 구성하지 않아야 합니다.

해당 정책을 사용하면 해당 정책이 구성한 프록시 서버가 모든 URL에 사용됩니다.

해당 정책을 사용하지 않도록 설정하거나 구성하지 않으면 해당 프록시 모드에서 사용자는 자신의 프록시 설정을 선택할 수 있습니다. 프록시 정책을 설정하는 다른 방법을 지정한 경우 해당 정책을 구성하지 않아야 합니다.

추가 옵션 및 자세한 예제는 [https://go.microsoft.com/fwlink/?linkid=2094936](https://go.microsoft.com/fwlink/?linkid=2094936)을 참조하세요.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ProxyServer
  - GP 이름: 프록시 서버 주소 또는 URL 구성(사용하지 않음)
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/프록시 서버
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: ProxyServer
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
"123.123.123.123:8080"
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ProxyServer
  - 예를 들어 값:
``` xml
<string>123.123.123.123:8080</string>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="proxysettings"></a>ProxySettings

  #### <a name="proxy-settings"></a>프록시 설정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  Microsoft Edge에 대한 프록시 설정을 구성합니다.

해당 정책을 사용하면 Microsoft Edge에서 명령줄에서 지정한 모든 프록시 관련 옵션을 무시합니다.

해당 정책을 구성하지 않으면 사용자는 자신의 프록시 설정을 선택할 수 있습니다.

해당 정책은 다음 개별 정책을 재정의합니다.

[ProxyMode](#proxymode)
[ProxyPacUrl](#proxypacurl)
[ProxyServer](#proxyserver)
[ProxyBypassList](#proxybypasslist)

[ProxySettings](#proxysettings) 정책 설정에서 다음 필드를 수락합니다.
  * ProxyMode, Microsoft Edge에서 사용되는 프록시 서버를 지정할 수 있으며 사용자가 프록시 설정을 변경하지 못하도록 합니다.
  * ProxyPacUrl, 프록시 .pac 파일의 URL
  * ProxyServer, 프록시 서버의 URL
  * ProxyBypassList, Microsoft Edge에서 우회하는 프록시 호스트 목록

ProxyMode에서 다음의 값을 선택하는 경우:
  * direct, 프록시가 사용되지 않으며 다른 모든 필드는 무시됩니다.
  * system, 시스템의 프록시가 사용되며 다른 모든 필드는 무시됩니다.
  * auto_detect, 다른 모든 필드는 무시됩니다.
  * fixed_servers, the ProxyServer and ProxyBypassList 필드가 사용됩니다.
  * pac_script, ProxyPacUrl 및 ProxyBypassList 필드가 사용됩니다.

자세한 예제를 보려면 [https://go.microsoft.com/fwlink/?linkid=2094936](https://go.microsoft.com/fwlink/?linkid=2094936)으로 이동하세요.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - Dictionary

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ProxySettings
  - GP 이름: 프록시 설정
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/프록시 서버
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: ProxySettings
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\ProxySettings = {
  "ProxyBypassList": "https://www.example1.com,https://www.example2.com,https://internalsite/", 
  "ProxyMode": "pac_script", 
  "ProxyPacUrl": "https://internal.site/example.pac", 
  "ProxyServer": "123.123.123.123:8080"
}
```

  ##### <a name="compact-example-value"></a>예제 값 압축:

  ```
  SOFTWARE\Policies\Microsoft\Edge\ProxySettings = {"ProxyBypassList": "https://www.example1.com,https://www.example2.com,https://internalsite/", "ProxyMode": "pac_script", "ProxyPacUrl": "https://internal.site/example.pac", "ProxyServer": "123.123.123.123:8080"}
  ```
  

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ProxySettings
  - 예를 들어 값:
``` xml
<key>ProxySettings</key>
<dict>
  <key>ProxyBypassList</key>
  <string>https://www.example1.com,https://www.example2.com,https://internalsite/</string>
  <key>ProxyMode</key>
  <string>pac_script</string>
  <key>ProxyPacUrl</key>
  <string>https://internal.site/example.pac</string>
  <key>ProxyServer</key>
  <string>123.123.123.123:8080</string>
</dict>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ## <a name="sleeping-tabs-settings-policies"></a>절전 탭 설정 정책

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="sleepingtabsblockedforurls"></a>SleepingTabsBlockedForUrls

  #### <a name="block-sleeping-tabs-on-specific-sites"></a>특정 사이트에서 절전 탭 차단

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS 88 이상

  #### <a name="description"></a>설명

  절전 탭을 사용하여 절전 모드로 전환할 수 없는 URL 패턴을 기반 사이트 목록을 정의합니다.

정책 [SleepingTabsEnabled](#sleepingtabsenabled)를 사용하지 않도록 설정한 경우 이 목록은 사용되지 않으며 어떤 사이트도 절전 모드로 자동 전환되지 않습니다.

이 정책을 구성하지 않으면, 사용자의 개인 구성이 차단하지 않는 경우를 제외하고 모든 사이트를 대기 모드로 전환할 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: SleepingTabsBlockedForUrls
  - GP 이름: 특정 사이트에서 절전 탭 차단
  - GP 경로(필수): 관리 템플릿/Microsoft Edge/절전 탭 설정
  - GP 경로(권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자가 재정의할 수 있음)/절전 모드 탭 설정
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로(필수): SOFTWARE\Policies\Microsoft\Edge\SleepingTabsBlockedForUrls
  - 경로(권장): SOFTWARE\Policies\Microsoft\Edge\Recommended\SleepingTabsBlockedForUrls
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\SleepingTabsBlockedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\SleepingTabsBlockedForUrls\2 = "[*.]contoso.edu"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: SleepingTabsBlockedForUrls
  - 값 예시:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="sleepingtabsenabled"></a>SleepingTabsEnabled

  #### <a name="configure-sleeping-tabs"></a>절전 모드 탭 구성

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS 88 이상

  #### <a name="description"></a>설명

  이 정책 설정을 통해 절전 모드 탭을 설정할지 여부를 구성할 수 있습니다. 절전 탭은 유휴 배경 탭을 절전 모드로 전환하여 CPU, 배터리 및 메모리 사용량을 줄입니다. Microsoft Edge는 경험적 접근을 사용하여 디스플레이 알림, 사운드 재생 및 비디오 스트림과 같이 백그라운드에서 유용한 작업을 수행하는 탭을 절전 모드로 전환하는 것을 방지합니다. 기본적으로 절전 모드 탭은 켜져 있습니다.

개별 사이트가 [SleepingTabsBlockedForUrls](#sleepingtabsblockedforurls) 정책을 구성하여 절전되는 것을 차단할 수 있습니다.

이 설정을 사용하면 절전 탭이 켜집니다.

이 설정을 사용하지 않도록 설정하면 절전 탭이 꺼집니다.

이 설정을 구성하지 않는 경우 사용자는 절전 모드 탭을 사용할지 여부를 선택할 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: SleepingTabsEnabled
  - GP 이름: 절전 모드 탭 구성
  - GP 경로(필수): 관리 템플릿/Microsoft Edge/절전 탭 설정
  - GP 경로(권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자가 재정의할 수 있음)/절전 모드 탭 설정
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로(권장): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 값 이름: SleepingTabsEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: SleepingTabsEnabled
  - 값 예시:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="sleepingtabstimeout"></a>SleepingTabsTimeout

  #### <a name="set-the-background-tab-inactivity-timeout-for-sleeping-tabs"></a>절전 탭에 대한 백그라운드 탭 비활성 시간 제한 설정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS 88 이상

  #### <a name="description"></a>설명

  절전 모드 탭을 사용하도록 설정한 경우 비활성 백그라운드 탭이 자동으로 절전 모드로 전환되고 이 후 이 정책 설정으로 시간 제한(초)을 구성할 수 있습니다. 기본적으로 이 제한 시간은 7,200초(2시간)입니다.

탭은 [SleepingTabsEnabled](#sleepingtabsenabled) 정책을 사용하도록 설정한 경우 또는 구성되지 않은 경우, 그리고 사용자가 절전 탭 설정을 사용하도록 설정한 경우에만 절전 모드로 자동 전환됩니다.

이 정책을 구성하지 않으면 사용자가 시간 제한 값을 선택할 수 있습니다.

정책 옵션 매핑:

* 5분(300) = 5분 비활성

* 15분(900) = 15분 비활성

* 30분(1800) = 30분 비활성

* 1시간(3600) = 1시간 비활성

* 2시간(7200) = 2시간 비활성

* 3시간(10800) = 3시간 비활성

* 6시간(21600) = 6시간 비활성

* 12시간(43200) = 12시간 비활성

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: SleepingTabsTimeout
  - GP 이름: 절전 탭에 대한 백그라운드 탭 비활성 시간 제한 설정
  - GP 경로(필수): 관리 템플릿/Microsoft Edge/절전 탭 설정
  - GP 경로(권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자가 재정의할 수 있음)/절전 모드 탭 설정
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로(권장): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 값 이름: SleepingTabsTimeout
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000384
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: SleepingTabsTimeout
  - 예를 들어 값:
``` xml
<integer>900</integer>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ## <a name="smartscreen-settings-policies"></a>SmartScreen 설정 정책

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="preventsmartscreenpromptoverride"></a>PreventSmartScreenPromptOverride

  #### <a name="prevent-bypassing-microsoft-defender-smartscreen-prompts-for-sites"></a>사이트에 대한 Microsoft Defender SmartScreen 프롬프트 무시 방지

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  해당 정책 설정을 통해 사용자가 잠재적인 악성 웹 사이트에 대한 Microsoft Defender SmartScreen 경고를 재정의할 수 있는지 여부를 결정할 수 있습니다.

해당 설정을 사용하면 사용자는 Microsoft Defender SmartScreen 경고를 무시할 수 없으며 해당 사이트로 이동할 수 없습니다.

해당 설정을 사용하지 않도록 설정하거나 구성하지 않으면 사용자는 Microsoft Defender SmartScreen 경고를 무시하고 해당 사이트로 이동할 수 있습니다.

이 정책은 Microsoft Active Directory 도메인에 가입된 윈도우즈 인스턴스, 장치 관리를 위해 등록된 윈도우즈 10 Pro 또는 Enterprise 인스턴스 또는 MDM을 통해 관리되거나 MCX를 통해 도메인에 가입된 MacOS 인스턴스에서만 사용할 수 있습니다..

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: PreventSmartScreenPromptOverride
  - GP 이름: 사이트에 대한 Microsoft Defender SmartScreen 프롬프트 무시 방지
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/SmartScreen 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: PreventSmartScreenPromptOverride
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: PreventSmartScreenPromptOverride
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="preventsmartscreenpromptoverrideforfiles"></a>PreventSmartScreenPromptOverrideForFiles

  #### <a name="prevent-bypassing-of-microsoft-defender-smartscreen-warnings-about-downloads"></a>다운로드에 대한 Microsoft Defender SmartScreen 경고 무시 방지

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows (77 이상)
  - MacOS (79 이상)

  #### <a name="description"></a>설명

  해당 정책을 사용하면 사용자는 확인되지 않은 다운로드에 대한 Microsoft Defender SmartScreen 경고를 재정의할 수 있는지 여부를 결정할 수 있습니다.

해당 정책을 사용하면 조직의 사용자는 Microsoft Defender SmartScreen 경고를 무시할 수 없고 확인되지 않은 다운로드를 완료할 수 없습니다.

해당 정책을 사용하지 않도록 설정하거나 구성하지 않으면 사용자는 Microsoft Defender SmartScreen 경고를 무시하고 확인되지 않은 다운로드를 완료할 수 있습니다.

이 정책은 Microsoft Active Directory 도메인에 가입된 윈도우즈 인스턴스, 장치 관리를 위해 등록된 윈도우즈 10 Pro 또는 Enterprise 인스턴스 또는 MDM을 통해 관리되거나 MCX를 통해 도메인에 가입된 MacOS 인스턴스에서만 사용할 수 있습니다..

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: PreventSmartScreenPromptOverrideForFiles
  - GP 이름: 다운로드에 대한 Microsoft Defender SmartScreen 경고 무시 방지
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/SmartScreen 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: PreventSmartScreenPromptOverrideForFiles
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: PreventSmartScreenPromptOverrideForFiles
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="smartscreenallowlistdomains"></a>SmartScreenAllowListDomains

  #### <a name="configure-the-list-of-domains-for-which-microsoft-defender-smartscreen-wont-trigger-warnings"></a>Microsoft Defender SmartScreen이 경고를 트리거하지 않는 도메인 목록 구성

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  Microsoft Defender SmartScreen 신뢰할 수 있는 도메인 목록을 구성합니다. 즉, Microsoft Defender SmartScreen은 원본 URL이 해당 도메인에 일치할 경우 피싱 소프트웨어 및 기타 맬웨어 등과 같은 잠재적 악성 리소스를 확인하지 않습니다.
Microsoft Defender SmartScreen 다운로드 보호 서비스는 해당 도메인에서 호스트되는 다운로드를 확인하지 않습니다.

해당 정책을 사용하면 Microsoft Defender SmartScreen이 해당 도메인을 신뢰합니다.
해당 정책을 사용하지 않거나 설정하지 않으면 기본 Microsoft Defender SmartScreen 보호가 모든 리소스에 적용됩니다.

이 정책은 Microsoft Active Directory 도메인에 가입된 윈도우즈 인스턴스, 장치 관리를 위해 등록된 윈도우즈 10 Pro 또는 Enterprise 인스턴스 또는 MDM을 통해 관리되거나 MCX를 통해 도메인에 가입된 MacOS 인스턴스에서만 사용할 수 있습니다..
또한 해당 정책은 조직에서 Microsoft Defender Advanced Threat Protection을 사용하도록 설정한 경우에는 적용되지 않는다는 점에 유의하세요. 대신 Microsoft Defender 보안 센터에서 허용 및 차단 목록을 구성해야 합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: SmartScreenAllowListDomains
  - GP 이름: Microsoft Defender SmartScreen이 경고를 트리거하지 않는 도메인 목록 구성
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/SmartScreen 설정
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\SmartScreenAllowListDomains
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\SmartScreenAllowListDomains\1 = "mydomain.com"
SOFTWARE\Policies\Microsoft\Edge\SmartScreenAllowListDomains\2 = "myuniversity.edu"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: SmartScreenAllowListDomains
  - 예를 들어 값:
``` xml
<array>
  <string>mydomain.com</string>
  <string>myuniversity.edu</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="smartscreenenabled"></a>SmartScreenEnabled

  #### <a name="configure-microsoft-defender-smartscreen"></a>Microsoft Defender SmartScreen 구성

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  해당 정책 설정을 통해 Microsoft Defender SmartScreen의 설정 여부를 구성할 수 있습니다. Microsoft Defender SmartScreen은 경고 메시지를 제공하여 잠재적인 피싱 메일 및 악성 소프트웨어로부터 사용자를 보호합니다. 기본적으로 Microsoft Defender SmartScreen은 설정되어 있습니다.

해당 설정을 사용하면 Microsoft Defender SmartScreen은 설정됩니다.

해당 설정을 사용하지 않으면 Microsoft Defender SmartScreen은 해제됩니다.

해당 설정을 구성하지 않으면 사용자는 Windows Defender SmartScreen의 사용 여부를 선택할 수 있습니다.

이 정책은 Microsoft Active Directory 도메인에 가입된 윈도우즈 인스턴스, 장치 관리를 위해 등록된 윈도우즈 10 Pro 또는 Enterprise 인스턴스 또는 MDM을 통해 관리되거나 MCX를 통해 도메인에 가입된 MacOS 인스턴스에서만 사용할 수 있습니다..

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: SmartScreenEnabled
  - GP 이름: Microsoft Defender SmartScreen 구성
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/SmartScreen 설정
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/SmartScreen 설정
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: SmartScreenEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: SmartScreenEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="smartscreenfortrusteddownloadsenabled"></a>SmartScreenForTrustedDownloadsEnabled

  #### <a name="force-microsoft-defender-smartscreen-checks-on-downloads-from-trusted-sources"></a>신뢰할 수 있는 출처에서 다운로드 시 Microsoft Defender SmartScreen 강제 확인

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows (78 이상)

  #### <a name="description"></a>설명

  해당 정책 설정을 사용하여 Microsoft Defender SmartScreen이 신뢰할 수 있는 소스에서 다운로드 평판을 확인할지 여부를 구성할 수 있습니다.

해당 설정을 사용하도록 설정하거나 구성하지 않으면 Microsoft Defender SmartScreen이 소스와 상관없이 다운로드 평판을 확인합니다.

해당 설정을 사용하지 않으면 Microsoft Defender SmartScreen이 신뢰할 수 있는 소스에서 다운로드하는 경우 다운로드 평판을 확인하지 않습니다.

해당 정책은 장치 관리에 등록된 Microsoft Active Directory 도메인, Windows 10 Pro나 엔터프라이즈 인스턴스에 가입한 Windows 인스턴스에만 사용할 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: SmartScreenForTrustedDownloadsEnabled
  - GP 이름: 신뢰할 수 있는 소스에서 다운로드 시 Microsoft Defender SmartScreen 강제 확인
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/SmartScreen 설정
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/SmartScreen 설정
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: SmartScreenForTrustedDownloadsEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="smartscreenpuaenabled"></a>SmartScreenPuaEnabled

  #### <a name="configure-microsoft-defender-smartscreen-to-block-potentially-unwanted-apps"></a>잠재적으로 원치 않는 앱을 차단하도록 Microsoft Defender SmartScreen 구성

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (80 이상)

  #### <a name="description"></a>설명

  해당 정책 설정을 통해 Microsoft Defender SmartScreen을 사용하여 잠재적으로 필요하지 않은 앱의 차단 설정 여부를 구성할 수 있습니다. Microsoft Defender SmartScreen을 사용하여 잠재적으로 필요하지 않은 앱 차단 기능은 웹 사이트에서 호스트하는 애드웨어, 코인 마이너, 번들웨어 및 기타 낮은 평판 앱으로부터 사용자를 보호하는 데 도움이 되는 경고 메시지를 제공합니다. Microsoft Defender SmartScreen을 사용하여 잠재적으로 필요하지 않은 앱 차단 기능은 기본적으로 해제되어 있습니다.

해당 설정을 사용하면 Microsoft Defender SmartScreen을 사용하여 잠재적으로 필요하지 않은 앱 차단 기능이 설정됩니다.

해당 설정을 사용하지 않으면 Microsoft Defender SmartScreen을 사용하여 잠재적으로 필요하지 않은 앱 차단 기능이 해제됩니다.

해당 설정을 구성하지 않으면 사용자는 Microsoft Defender SmartScreen을 사용하여 잠재적으로 필요하지 않은 앱 차단 기능의 사용 여부를 선택할 수 있습니다.

이 정책은 Microsoft Active Directory 도메인에 가입된 윈도우즈 인스턴스, 장치 관리를 위해 등록된 윈도우즈 10 Pro 또는 Enterprise 인스턴스 또는 MDM을 통해 관리되거나 MCX를 통해 도메인에 가입된 MacOS 인스턴스에서만 사용할 수 있습니다..

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: SmartScreenPuaEnabled
  - GP 이름: 잠재적으로 필요하지 않은 앱을 차단하도록 Microsoft Defender SmartScreen 구성
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/SmartScreen 설정
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/SmartScreen 설정
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: SmartScreenPuaEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: SmartScreenPuaEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ## <a name="startupcomma-home-page-and-new-tab-page-policies"></a>시작&comma; 홈 페이지 및 새 탭 페이지 정책

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="homepageisnewtabpage"></a>HomepageIsNewTabPage

  #### <a name="set-the-new-tab-page-as-the-home-page"></a>새 탭 페이지를 홈 페이지로 설정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  Microsoft Edge에서 기본 홈 페이지를 구성합니다. 홈 페이지를 지정하는 URL 또는 새 탭 페이지로 설정할 수 있습니다.

해당 정책을 사용하면 항상 홈 페이지에서 새 탭 페이지를 사용하며 홈 페이지 URL 위치는 무시됩니다.

해당 정책을 사용하지 않도록 설정하는 경우 URL이 'edge://newtab'으로 설정되어 있지 않으면 사용자의 홈 페이지는 새 탭 페이지가 될 수 없습니다.

해당 정책을 구성하지 않으면 새 탭 페이지가 홈 페이지인지 여부를 선택할 수 있습니다.

이 정책은 Microsoft Active Directory 도메인에 가입된 윈도우즈 인스턴스, 장치 관리를 위해 등록된 윈도우즈 10 Pro 또는 Enterprise 인스턴스 또는 MDM을 통해 관리되거나 MCX를 통해 도메인에 가입된 MacOS 인스턴스에서만 사용할 수 있습니다..

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: HomepageIsNewTabPage
  - GP 이름: 새 탭 페이지를 홈 페이지로 설정
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/시작, 홈 페이지 및 새 탭 페이지
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/시작, 홈 페이지 및 새 탭 페이지
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: HomepageIsNewTabPage
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: HomepageIsNewTabPage
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="homepagelocation"></a>HomepageLocation

  #### <a name="configure-the-home-page-url"></a>홈 페이지 URL 구성

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  Microsoft Edge에서 기본 홈 페이지 URL을 구성합니다.

홈 페이지는 홈 단추로 열리는 페이지입니다. 시작할 때 열리는 페이지는 [RestoreOnStartup](#restoreonstartup) 정책으로 제어됩니다.

여기에서 URL을 설정하거나 홈 페이지를 설정하여 새 탭 페이지를 열 수 있습니다. 새 탭 페이지를 열도록 선택하는 경우 해당 정책이 적용되지 않습니다.

해당 정책을 사용하면 사용자는 홈 페이지 URL을 변경할 수 없지만 홈 페이지에서 새 탭 페이지를 사용하도록 선택할 수 있습니다.

해당 정책을 사용하지 않도록 설정하거나 구성하지 않으면 [HomepageIsNewTabPage](#homepageisnewtabpage) 정책을 사용하도록 설정하지 않는 한 사용자는 자신의 홈 페이지를 선택할 수 있습니다.

이 정책은 Microsoft Active Directory 도메인에 가입된 윈도우즈 인스턴스, 장치 관리를 위해 등록된 윈도우즈 10 Pro 또는 Enterprise 인스턴스 또는 MDM을 통해 관리되거나 MCX를 통해 도메인에 가입된 MacOS 인스턴스에서만 사용할 수 있습니다..

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: HomepageLocation
  - GP 이름: 홈 페이지 URL 구성
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/시작, 홈 페이지 및 새 탭 페이지
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/시작, 홈 페이지 및 새 탭 페이지
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: HomepageLocation
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
"https://www.contoso.com"
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: HomepageLocation
  - 예를 들어 값:
``` xml
<string>https://www.contoso.com</string>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="newtabpageallowedbackgroundtypes"></a>NewTabPageAllowedBackgroundTypes

  #### <a name="configure-the-background-types-allowed-for-the-new-tab-page-layout"></a>새 탭 페이지 레이아웃에 허용되는 배경 유형 구성

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (86 이상)

  #### <a name="description"></a>설명

  Microsoft Edge에서 새 탭 페이지 레이아웃에 허용되는 배경 이미지 유형을 구성할 수 있습니다.

이 정책을 구성하지 않으면 새 탭 페이지의 모든 배경 이미지 유형을 사용할 수 있습니다.

정책 옵션 매핑:

* DisableImageOfTheDay (1) = 일일 배경 이미지 유형 사용 안 함

* DisableCustomImage (2) = 사용자 지정 배경 이미지 유형 사용 안 함

* DisableAll (3) = 모든 배경 이미지 유형 사용 안 함

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: NewTabPageAllowedBackgroundTypes
  - GP 이름: 새 탭 페이지 레이아웃에 허용되는 배경 유형 구성
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/시작, 홈 페이지 및 새 탭 페이지
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: NewTabPageAllowedBackgroundTypes
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000002
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: NewTabPageAllowedBackgroundTypes
  - 예를 들어 값:
``` xml
<integer>2</integer>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="newtabpagecompanylogo"></a>NewTabPageCompanyLogo

  #### <a name="set-new-tab-page-company-logo-obsolete"></a>새 탭 페이지 회사 로고 설정(구식)

  
  >사용되지 않음: 이 정책은 더 이상 사용되지 않으며 Microsoft Edge 85 이후에는 작동하지 않습니다.
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (79 이상, 85까지)

  #### <a name="description"></a>설명

  이 정책은 운영 요구 사항의 변경 때문에 예상대로 작동하지 않습니다. 따라서 이 정책은 오래되어 사용하지 않는 것이 좋습니다.

Microsoft Edge의 새 탭 페이지에서 사용하는 회사 로고를 지정합니다.

해당 정책은 JSON 형식으로 로고를 나타내는 문자열로 구성되어야 합니다. 예: { "default_logo": { "url": "https://www.contoso.com/logo.png", "hash": "cd0aa9856147b6c5b4ff2b7dfee5da20aa38253099ef1b4a64aced233c9afe29" }, "light_logo": { "url": "https://www.contoso.com/light_logo.png", "hash": "517d286edb416bb2625ccfcba9de78296e90da8e32330d4c9c8275c4c1c33737" } }

Microsoft Edge에서는 다운로드 무결성을 확인하는 데 사용되는 로고 및 해당 암호 해시(SHA-256)를 다운로드할 수 있는 URL을 지정하여 해당 정책을 구성합니다. 로고는 PNG 또는 SVG 형식이어야 하며 파일 크기는 16MB를 넘지않아야 합니다. 로고는 다운로드되고 캐시되며 URL 또는 해시가 변경될 때마다 다시 다운로드됩니다. URL은 인증 없이 액세스할 수 있어야 합니다.

'default_logo'는 필수 요소이며 배경 이미지가 없는 경우에 사용됩니다. 'light_logo'가 제공되면 사용자의 새 탭 페이지에 배경 이미지가 있는 경우에 사용됩니다. 왼쪽 맞춤 및 세로로 가운데 맞춤이 되는 투명한 배경이 포함된 가로 로고를 사용하는 것이 좋습니다. 로고의 최소 높이는 32픽셀이어야 하고 가로 세로 비율은 1:1에서 4:1 사이여야 합니다. 'default_logo'에는 흰색/검은색 배경에 대한 적절한 대비가 이루어져 있어야 합니다. 반면 'light_logo'는 배경 이미지에 대한 적절한 대비가 이루어져 있어야 합니다.

해당 정책을 사용하면 Microsoft Edge에서 새 탭 페이지에 지정된 로고를 다운로드하고 표시합니다. 사용자는 로고를 재정의하거나 숨길 수 없습니다.

해당 정책을 사용하지 않도록 설정하거나 구성하지 않으면 Microsoft Edge에서 새 탭 페이지에 회사 로고 또는 Microsoft 로고를 표시하지 않습니다.

SHA-256 해시를 확인하는 데 도움이 필요한 경우 https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-filehash을 참조하세요.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - Dictionary

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: NewTabPageCompanyLogo
  - GP 이름: 새 탭 페이지 회사 로고 설정(구식)
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/시작, 홈 페이지 및 새 탭 페이지
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: NewTabPageCompanyLogo
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\NewTabPageCompanyLogo = {
  "default_logo": {
    "hash": "cd0aa9856147b6c5b4ff2b7dfee5da20aa38253099ef1b4a64aced233c9afe29", 
    "url": "https://www.contoso.com/logo.png"
  }, 
  "light_logo": {
    "hash": "517d286edb416bb2625ccfcba9de78296e90da8e32330d4c9c8275c4c1c33737", 
    "url": "https://www.contoso.com/light_logo.png"
  }
}
```

  ##### <a name="compact-example-value"></a>예제 값 압축:

  ```
  SOFTWARE\Policies\Microsoft\Edge\NewTabPageCompanyLogo = {"default_logo": {"hash": "cd0aa9856147b6c5b4ff2b7dfee5da20aa38253099ef1b4a64aced233c9afe29", "url": "https://www.contoso.com/logo.png"}, "light_logo": {"hash": "517d286edb416bb2625ccfcba9de78296e90da8e32330d4c9c8275c4c1c33737", "url": "https://www.contoso.com/light_logo.png"}}
  ```
  

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: NewTabPageCompanyLogo
  - 예를 들어 값:
``` xml
<key>NewTabPageCompanyLogo</key>
<dict>
  <key>default_logo</key>
  <dict>
    <key>hash</key>
    <string>cd0aa9856147b6c5b4ff2b7dfee5da20aa38253099ef1b4a64aced233c9afe29</string>
    <key>url</key>
    <string>https://www.contoso.com/logo.png</string>
  </dict>
  <key>light_logo</key>
  <dict>
    <key>hash</key>
    <string>517d286edb416bb2625ccfcba9de78296e90da8e32330d4c9c8275c4c1c33737</string>
    <key>url</key>
    <string>https://www.contoso.com/light_logo.png</string>
  </dict>
</dict>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="newtabpagehidedefaulttopsites"></a>NewTabPageHideDefaultTopSites

  #### <a name="hide-the-default-top-sites-from-the-new-tab-page"></a>새 탭 페이지에서 기본 상위 사이트 숨기기

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  Microsoft Edge의 새 탭 페이지에서 기본 상위 사이트를 숨깁니다.

해당 정책을 True로 설정하면 기본 상위 사이트 타일이 숨겨집니다.

해당 정책을 False로 설정하거나 구성하지 않으면 기본 상위 사이트 타일이 계속 표시됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: NewTabPageHideDefaultTopSites
  - GP 이름: 새 탭 페이지에서 기본 상위 사이트 숨기기
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/시작, 홈 페이지 및 새 탭 페이지
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: NewTabPageHideDefaultTopSites
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: NewTabPageHideDefaultTopSites
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="newtabpagelocation"></a>NewTabPageLocation

  #### <a name="configure-the-new-tab-page-url"></a>새 탭 페이지 URL 구성

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  새 탭 페이지에 대해 기본 URL을 구성합니다.

이 정책의 권장 버전은 현재 작동하지 않으며 필수 버전과 동일하게 작동합니다.

해당 정책은 새 탭이 생성될 때(새 창이 열려 있는 경우 포함) 열리는 페이지를 확인합니다. 새 탭 페이지로 열리도록 설정한 경우 시작 페이지에도 영향을 미칩니다.

해당 정책은 시작 시 열리는 페이지를 확인하지 않으며 [RestoreOnStartup](#restoreonstartup) 정책에 의해 제어됩니다. 새 탭 페이지로 열리도록 설정한 경우 홈 페이지에 영향을 미치지 않습니다.

해당 정책을 구성하지 않으면 기본 새 탭 페이지가 사용됩니다.

해당 정책 및 [NewTabPageSetFeedType](#newtabpagesetfeedtype) 정책을 *구성하면* 해당 정책이 우선됩니다.

빈 탭을 선호하는 경우 사용해야 할 올바른 URL은 "about://blank"이 아니라 "about:blank”입니다.

이 정책은 Microsoft Active Directory 도메인에 가입된 윈도우즈 인스턴스, 장치 관리를 위해 등록된 윈도우즈 10 Pro 또는 Enterprise 인스턴스 또는 MDM을 통해 관리되거나 MCX를 통해 도메인에 가입된 MacOS 인스턴스에서만 사용할 수 있습니다..

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: NewTabPageLocation
  - GP 이름: 새 탭 페이지 URL 구성
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/시작, 홈 페이지 및 새 탭 페이지
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/시작, 홈 페이지 및 새 탭 페이지
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: NewTabPageLocation
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
"https://www.fabrikam.com"
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: NewTabPageLocation
  - 예를 들어 값:
``` xml
<string>https://www.fabrikam.com</string>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="newtabpagemanagedquicklinks"></a>NewTabPageManagedQuickLinks

  #### <a name="set-new-tab-page-quick-links"></a>새 탭 페이지 빠른 링크 설정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (79 이상)

  #### <a name="description"></a>설명

  기본적으로 Microsoft Edge는 사용자가 추가한 바로 가기 키와 검색 기록을 기반으로 하는 상위 사이트에서 새 탭 페이지에 빠른 링크를 표시합니다. 해당 정책을 사용하면 새 탭 페이지에서 JSON 개체로 표시되는 최대 3개의 빠른 링크 타일을 구성할 수 있습니다.

[ { "url": "https://www.contoso.com", "title": "Contoso Portal", "pinned": true/false }, ... ]

'url' 필드는 필수입니다. 'title' 및 'pinned'는 선택 사항입니다. 'title'이 제공되지 않으면 URL이 기본 제목으로 사용됩니다. 'pinned'가 제공되지 않는 경우 기본값은 False입니다.

Microsoft Edge는 이를 나열된 순서 대로 왼쪽에서 오른쪽으로 표시하며 고정된 모든 타일이 고정되지 않은 타일보다 먼저 표시됩니다.

해당 정책이 필수로 설정된 경우 'pinned' 필드가 무시되고 모든 타일이 고정됩니다. 해당 타일은 사용자가 삭제할 수 없으며 항상 빠른 링크 목록 맨 앞에 표시됩니다.

해당 정책이 권장 대로 설정되면 고정된 타일은 목록에 유지되지만 사용자는 해당 타일을 편집하고 삭제할 수 있습니다. 고정되지 않은 빠른 링크 타일은 기본 상위 사이트처럼 작동하며 다른 웹 사이트를 더 자주 방문하는 경우 목록에서 제거됩니다. 해당 정책을 통해 고정되지 않은 링크를 기존 브라우저 프로필에 적용하는 경우 해당 링크는 사용자의 검색 기록과 비교되는 방식에 따라 전혀 표시되지 않을 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - Dictionary

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: NewTabPageManagedQuickLinks
  - GP 이름: 새 탭 페이지 빠른 링크 설정
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/시작, 홈 페이지 및 새 탭 페이지
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/시작, 홈 페이지 및 새 탭 페이지
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: NewTabPageManagedQuickLinks
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\NewTabPageManagedQuickLinks = [
  {
    "pinned": true, 
    "title": "Contoso Portal", 
    "url": "https://contoso.com"
  }, 
  {
    "title": "Fabrikam", 
    "url": "https://fabrikam.com"
  }
]
```

  ##### <a name="compact-example-value"></a>예제 값 압축:

  ```
  SOFTWARE\Policies\Microsoft\Edge\NewTabPageManagedQuickLinks = [{"pinned": true, "title": "Contoso Portal", "url": "https://contoso.com"}, {"title": "Fabrikam", "url": "https://fabrikam.com"}]
  ```
  

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: NewTabPageManagedQuickLinks
  - 예를 들어 값:
``` xml
<key>NewTabPageManagedQuickLinks</key>
<array>
  <dict>
    <key>pinned</key>
    <true/>
    <key>title</key>
    <string>Contoso Portal</string>
    <key>url</key>
    <string>https://contoso.com</string>
  </dict>
  <dict>
    <key>title</key>
    <string>Fabrikam</string>
    <key>url</key>
    <string>https://fabrikam.com</string>
  </dict>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="newtabpageprerenderenabled"></a>NewTabPagePrerenderEnabled

  #### <a name="enable-preload-of-the-new-tab-page-for-faster-rendering"></a>더 빠른 렌더링을 위해 새 탭 페이지의 미리 로드 활성화

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS(85 이상)

  #### <a name="description"></a>설명

  이 정책을 구성하면 새 탭 페이지 미리 로드가 활성화되고 사용자는 이 설정을 변경할 수 없습니다. 이 정책을 구성하지 않으면 미리 로드가 활성화되고 사용자가 이 설정을 변경할 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: NewTabPagePrerenderEnabled
  - GP 이름: 더 빠른 렌더링을 위해 새 탭 페이지의 미리 로드 활성화
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/시작, 홈 페이지 및 새 탭 페이지
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/시작, 홈 페이지 및 새 탭 페이지
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: NewTabPagePrerenderEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: NewTabPagePrerenderEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="newtabpagesetfeedtype"></a>NewTabPageSetFeedType

  #### <a name="configure-the-microsoft-edge-new-tab-page-experience-deprecated"></a>Microsoft Edge 새 탭 페이지 환경 구성(사용되지 않음)

  >DEPRECATED: 해당 정책은 사용되지 않습니다. 현재 지원되고 있지만 이후 릴리스에서는 더 이상 사용되지 않을 예정입니다.
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (79 이상)

  #### <a name="description"></a>설명

  새 버전의 엔터프라이즈 새 탭 페이지에서 다양한 콘텐츠 형식들 사이에 더 이상 선택하지 않아도 되기 때문에 이 정책을 더 이상 사용하지 않고 있습니다. 대신에 Microsoft 365 관리 센터를 통해 사용자에게 제공되는 콘텐츠를 제어할 수 있습니다. Microsoft 365 관리 센터로 이동하려면 관리자 계정으로 https://admin.microsoft.com에 로그인합니다. 이 정책은 Microsoft Edge 버전 90 이후 더 이상 사용되지 않습니다.

새 탭 페이지에서 Microsoft 뉴스 또는 Office 365 피드 환경을 선택할 수 있습니다.

해당 정책을 ‘News’로 설정하면 사용자에게 새 탭 페이지에서 Microsoft 뉴스 피드 환경이 표시됩니다.

해당 정책을 ‘Office’로 설정하면 Azure Active Directory 브라우저 로그인 사용자에게 새 탭 페이지에서 Office 365 피드 환경이 표시됩니다.

해당 정책을 사용하지 않도록 설정하거나 구성하지 않은 경우

- Azure Active Directory 브라우저 로그인을 사용하는 사용자에게 Office 365 새 탭 페이지 피드 환경을 비롯하여 표준 새 탭 페이지 피드 환경을 제공됩니다.

- Azure Active Directory 브라우저 로그인이 없는 사용자에게는 표준 새 탭 페이지 환경이 표시됩니다.

해당 정책 및 [NewTabPageLocation](#newtabpagelocation) 정책을 *구성하면* [NewTabPageLocation](#newtabpagelocation) 정책이 우선됩니다.

기본 설정: 사용하지 않도록 설정하거나 구성하지 않음

정책 옵션 매핑:

* News (0) = Microsoft 뉴스 피드 환경

* Office (1) = Office 365 피드 환경

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: NewTabPageSetFeedType
  - GP 이름: Microsoft Edge 새 탭 페이지 환경 구성(사용되지 않음)
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/시작, 홈 페이지 및 새 탭 페이지
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/시작, 홈 페이지 및 새 탭 페이지
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: NewTabPageSetFeedType
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: NewTabPageSetFeedType
  - 예를 들어 값:
``` xml
<integer>0</integer>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="restoreonstartup"></a>RestoreOnStartup

  #### <a name="action-to-take-on-startup"></a>시작 시 수행하는 작업

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  Microsoft Edge가 시작할 때 작동하는 방식을 지정합니다.

시작할 때 새 탭이 항상 열리도록 하려면 'RestoreOnStartupIsNewTabPage'를 선택합니다.

Microsoft Edge가 마지막으로 종료 시 열리는 URL을 다시 열려면 'RestoreOnStartupIsLastSession'을 선택합니다. 검색 세션이 원래 대로 복원됩니다. 해당 옵션은 세션에 의존하는 일부 설정이나 종료 시 작업을 수행하는 일부 설정을 사용하지 않도록 설정합니다. (예: 종료 또는 세션 전용 쿠키에서 검색 데이터 지우기)

특정 URL 집합을 열려면 'RestoreOnStartupIsURLs'를 선택합니다.

해당 설정을 사용하지 않도록 설정하면 구성되지 않은 상태로 두는 것과 같습니다. 사용자는 Microsoft Edge에서 해당 설정을 변경할 수 있습니다.

이 정책은 Microsoft Active Directory 도메인에 가입된 윈도우즈 인스턴스, 장치 관리를 위해 등록된 윈도우즈 10 Pro 또는 Enterprise 인스턴스 또는 MDM을 통해 관리되거나 MCX를 통해 도메인에 가입된 MacOS 인스턴스에서만 사용할 수 있습니다..

정책 옵션 매핑:

* RestoreOnStartupIsNewTabPage (5) = 새 탭 열기

* RestoreOnStartupIsLastSession (1) = 마지막 세션 복원

* RestoreOnStartupIsURLs (4) = URL 목록 열기

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: RestoreOnStartup
  - GP 이름: 시작 시 수행하는 작업
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/시작, 홈 페이지 및 새 탭 페이지
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/시작, 홈 페이지 및 새 탭 페이지
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: RestoreOnStartup
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000004
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: RestoreOnStartup
  - 예를 들어 값:
``` xml
<integer>4</integer>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="restoreonstartupurls"></a>RestoreOnStartupURLs

  #### <a name="sites-to-open-when-the-browser-starts"></a>브라우저 시작 시 열리는 사이트

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  브라우저 시작 시 자동으로 열리는 웹 사이트 목록을 지정합니다. 해당 정책을 구성하지 않으면 시작 시 사이트를 열지 않습니다.

해당 정책은 [RestoreOnStartup](#restoreonstartup) 정책을 'URL 목록 열기' (4)로 설정하는 경우에만 작동할 수 있습니다.

이 정책은 Microsoft Active Directory 도메인에 가입된 윈도우즈 인스턴스, 장치 관리를 위해 등록된 윈도우즈 10 Pro 또는 Enterprise 인스턴스 또는 MDM을 통해 관리되거나 MCX를 통해 도메인에 가입된 MacOS 인스턴스에서만 사용할 수 있습니다..

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: RestoreOnStartupURLs
  - GP 이름: 브라우저 시작 시 열리는 사이트
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/시작, 홈 페이지 및 새 탭 페이지
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/시작, 홈 페이지 및 새 탭 페이지
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\RestoreOnStartupURLs
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended\RestoreOnStartupURLs
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\RestoreOnStartupURLs\1 = "https://contoso.com"
SOFTWARE\Policies\Microsoft\Edge\RestoreOnStartupURLs\2 = "https://www.fabrikam.com"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: RestoreOnStartupURLs
  - 예를 들어 값:
``` xml
<array>
  <string>https://contoso.com</string>
  <string>https://www.fabrikam.com</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="showhomebutton"></a>ShowHomeButton

  #### <a name="show-home-button-on-toolbar"></a>도구 모음에서 홈 단추 표시

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  Microsoft Edge 도구 모음에서 홈 단추를 표시합니다.

해당 정책을 사용하면 항상 홈 단추가 표시됩니다. 해당 정책을 사용하지 않도록 설정하면 단추가 표시되지 않습니다.

해당 정책을 구성하지 않으면 사용자는 홈 단추를 표시할지 여부를 선택할 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ShowHomeButton
  - GP 이름: 도구 모음에서 홈 단추 표시
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/시작, 홈 페이지 및 새 탭 페이지
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/시작, 홈 페이지 및 새 탭 페이지
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: ShowHomeButton
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ShowHomeButton
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ## <a name="additional-policies"></a>추가 정책

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="addressbarmicrosoftsearchinbingproviderenabled"></a>AddressBarMicrosoftSearchInBingProviderEnabled

  #### <a name="enable-microsoft-search-in-bing-suggestions-in-the-address-bar"></a>주소 표시줄의 Bing 제안에서 Microsoft Search 사용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (81 이상)

  #### <a name="description"></a>설명

  사용자가 주소 표시줄에 검색 문자열을 입력하는 경우 주소 표시줄의 제안 목록의 Bing에서 관련 Microsoft 검색 제안을 표시할 수 있습니다. 해당 정책을 사용하도록 설정하거나 구성하지 않으면 사용자는 Microsoft Edge 주소 표시줄 제안 목록에서 Bing의 Microsoft 검색에서 제공하는 내부 결과를 확인할 수 있습니다. Bing 결과에서 Microsoft 검색을 보려면 사용자는 해당 조직의 Azure AD 계정을 사용하여 Microsoft Edge에 로그인해야 합니다.
해당 정책을 사용하지 않도록 설정하면 사용자는 Microsoft Edge 주소 표시줄 제안 목록에서 내부 결과를 확인할 수 없습니다.
Microsoft Edge 버전 89부터 Bing이 사용자의 기본 검색 제공자가 아닌 경우에도 Bing의 Microsoft Search 추천 사항을 사용할 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: AddressBarMicrosoftSearchInBingProviderEnabled
  - GP 이름: 주소 표시줄의 Bing 제안에서 Microsoft 검색 사용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: AddressBarMicrosoftSearchInBingProviderEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: AddressBarMicrosoftSearchInBingProviderEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="adssettingforintrusiveadssites"></a>AdsSettingForIntrusiveAdsSites

  #### <a name="ads-setting-for-sites-with-intrusive-ads"></a>간섭 광고가 포함된 사이트에 대한 광고 설정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (78 이상)

  #### <a name="description"></a>설명

  간섭 광고가 포함된 사이트에서 광고 차단 여부를 제어합니다.

정책 옵션 매핑:

* AllowAds (1) = 모든 사이트에서 광고 허용

* BlockAds (2) = 간섭 광고가 포함된 사이트에서 광고 차단 (기본값)

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: AdsSettingForIntrusiveAdsSites
  - GP 이름: 간섭 광고가 포함된 사이트에 대한 광고 설정
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: AdsSettingForIntrusiveAdsSites
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: AdsSettingForIntrusiveAdsSites
  - 예를 들어 값:
``` xml
<integer>1</integer>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="allowdeletingbrowserhistory"></a>AllowDeletingBrowserHistory

  #### <a name="enable-deleting-browser-and-download-history"></a>브라우저 및 다운로드 기록 삭제 사용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  브라우저 기록 및 다운로드 기록을 삭제하고 사용자는 해당 설정을 변경할 수 없습니다.

해당 정책을 사용하지 않도록 설정한 경우에도 검색 및 다운로드 기록이 보존되도록 보장하지 않습니다. 사용자는 기록 데이터베이스 파일을 직접 편집하거나 삭제할 수 있고 브라우저 자체에서 만료 기간에 따라 제거되거나 일부 기록 항목을 언제든지 보관할 수도 있다는 점에 유의하세요.

해당 정책을 사용하도록 설정하거나 구성하지 않으면 사용자는 탐색 및 다운로드 기록을 삭제할 수 있습니다.

해당 정책을 사용하지 않도록 설정하면 사용자는 탐색과 다운로드 기록을 삭제할 수 없으며 기록 동기화가 해제됩니다.

해당 정책을 사용하는 경우 [ClearBrowsingDataOnExit](#clearbrowsingdataonexit) 정책을 사용하지 않아야 합니다. 두 정책 모두 데이터 삭제를 처리하기 때문입니다. 두 정책을 모두 사용하는 경우 해당 정책을 구성하는 방법에 관계 없이 Microsoft Edge 종료 시 [ClearBrowsingDataOnExit](#clearbrowsingdataonexit) 정책이 우선되어 모든 데이터가 삭제됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: AllowDeletingBrowserHistory
  - GP 이름: 브라우저 및 다운로드 기록 삭제 사용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: AllowDeletingBrowserHistory
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: AllowDeletingBrowserHistory
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="allowfileselectiondialogs"></a>AllowFileSelectionDialogs

  #### <a name="allow-file-selection-dialogs"></a>파일 선택 대화 상자 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  Microsoft Edge에 파일 선택 대화 상자를 표시하여 로컬 파일에 대한 액세스를 허용합니다.

해당 정책을 사용하도록 설정하거나 구성하지 않으면 사용자는 파일 선택 대화 상자를 평소 대로 열 수 있습니다.

해당 정책을 사용하지 않도록 설정하면 사용자가 파일 선택 대화 상자(예: 즐겨찾기 가져오기, 파일 업로드 또는 링크 저장)를 트리거하는 작업을 수행할 때마다 메시지가 대신 표시되고 사용자는 파일 선택 대화 상자에서 취소를 클릭한 것으로 간주됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: AllowFileSelectionDialogs
  - GP 이름: 파일 선택 대화 상자 허용
  - GP 경로(필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: AllowFileSelectionDialogs
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: AllowFileSelectionDialogs
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="allowpopupsduringpageunload"></a>AllowPopupsDuringPageUnload

  #### <a name="allows-a-page-to-show-popups-during-its-unloading-obsolete"></a>페이지를 언로딩하는 동안 팝업 표시 허용(사용되지 않음)

  
  >사용되지 않음: 이 정책은 더 이상 사용되지 않으며 Microsoft Edge 87 이후에는 작동하지 않습니다.
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 macOS(78부터 87까지)

  #### <a name="description"></a>설명

  해당 정책을 사용하면 관리자는 언로드가 진행되는 동안 페이지에 팝업을 표시할 수 있음을 지정할 수 있습니다.

해당 정책을 사용하도록 설정하면 페이지는 언로드될 때 팝업을 표시할 수 있습니다.

해당 정책을 사용하지 않거나 설정하지 않으면 페이지는 언로드될 때 팝업을 표시할 수 없습니다. 이는 사양(https://html.spec.whatwg.org/#apis-for-creating-and-navigating-browsing-contexts-by-name))에 따라 같습니다.

이 정책은 Microsoft Edge 88에서 제거되었고 설정된 경우 무시됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: AllowPopupsDuringPageUnload
  - GP 이름: 페이지를 언로딩하는 동안 팝업 표시(사용되지 않음)를 허용합니다.
  - GP 경로(필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: AllowPopupsDuringPageUnload
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: AllowPopupsDuringPageUnload
  - 예를 들어 값:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="allowsurfgame"></a>AllowSurfGame

  #### <a name="allow-surf-game"></a>서핑 게임 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (83 이상)

  #### <a name="description"></a>설명

  해당 정책을 사용하지 않도록 설정하면 사용자는 장치가 오프라인이거나 사용자가 edge://surf로 이동하는 경우 서핑 게임을 플레이할 수 없습니다.

해당 정책을 사용하도록 설정하거나 구성하지 않으면 사용자는 서핑 게임을 플레이할 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: AllowSurfGame
  - GP 이름: 서핑 게임 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: AllowSurfGame
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: AllowSurfGame
  - 예를 들어 값:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="allowsyncxhrinpagedismissal"></a>AllowSyncXHRInPageDismissal

  #### <a name="allow-pages-to-send-synchronous-xhr-requests-during-page-dismissal-deprecated"></a>페이지를 해제하는 동안 페이지에서 동기 XHR 요청 전송 허용(사용되지 않음)

  >DEPRECATED: 해당 정책은 사용되지 않습니다. 현재 지원되고 있지만 이후 릴리스에서는 더 이상 사용되지 않을 예정입니다.
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (79 이상)

  #### <a name="description"></a>설명

  이 정책은 페이지가 해제되는 동안 동기 XHR 요청을 불허하도록 하는 변경과 호환되지 않는 것으로 확인되는 경우 엔터프라이즈에서 웹 콘텐츠를 업데이트하는 데 더 많은 시간을 주기 위한 목적으로만 만들어진 단기 메커니즘이므로 더 이상 사용되지 않습니다. Microsoft Edge 버전 93에서는 작동하지 않습니다.

해당 정책을 사용하면 페이지가 해제되는 동안 페이지에서 동기 XHR 요청을 보내도록 지정할 수 있습니다.

해당 정책을 사용하면 페이지가 해제되는 동안 페이지에서 동기 XHR 요청을 보낼 수 있습니다.

해당 정책을 사용하지 않도록 설정하거나 구성하지 않으면 페이지가 해제되는 동안 페이지에서 동기 XHR 요청을 보낼 수 없습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: AllowSyncXHRInPageDismissal
  - GP 이름: 페이지를 해제하는 동안 페이지에서 동기 XHR 요청 전송 허용(사용되지 않음)
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: AllowSyncXHRInPageDismissal
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: AllowSyncXHRInPageDismissal
  - 예를 들어 값:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="allowtokenbindingforurls"></a>AllowTokenBindingForUrls

  #### <a name="configure-the-list-of-sites-for-which-microsoft-edge-will-attempt-to-establish-a-token-binding-with"></a>Microsoft Edge에서 토큰 바인딩을 설정하려는 사이트 목록 구성

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows (83 이상)

  #### <a name="description"></a>설명

  브라우저에서 토큰 바인딩 프로토콜을 수행하려는 사이트에 대해 URL 패턴 목록을 구성합니다.
해당 목록에 있는 도메인의 경우 브라우저에서 토큰 바인딩 ClientHello를 TLS 핸드셰이크에 전송합니다. (https://tools.ietf.org/html/rfc8472) 참조)
서버가 유효한 ServerHello 응답을 사용하여 응답하는 경우 브라우저는 다음 https 요청에서 토큰 바인딩 메시지를 생성하고 전송합니다. 자세한 내용은 https://tools.ietf.org/html/rfc8471를 참조하세요.

해당 목록이 비어 있으면 토큰 바인딩을 사용할 수 없습니다.

해당 정책은 Windows 10 장치에서 가상 보안 모드 기능을 사용하는 경우에만 사용할 수 있습니다.

Microsoft Edge 86부터는 이 정책이 더 이상 동적 새로 고침을 지원하지 않습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: AllowTokenBindingForUrls
  - GP 이름: Microsoft Edge에서 토큰 바인딩을 설정하려는 사이트 목록 구성
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\AllowTokenBindingForUrls
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\AllowTokenBindingForUrls\1 = "mydomain.com"
SOFTWARE\Policies\Microsoft\Edge\AllowTokenBindingForUrls\2 = "[*.]mydomain2.com"
SOFTWARE\Policies\Microsoft\Edge\AllowTokenBindingForUrls\3 = "[*.].mydomain2.com"

```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="allowtrackingforurls"></a>AllowTrackingForUrls

  #### <a name="configure-tracking-prevention-exceptions-for-specific-sites"></a>특정 사이트에 대한 추적 방지 예외 구성

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (78 이상)

  #### <a name="description"></a>설명

  추적 방지에서 제외되는 URL 패턴 목록을 구성합니다.

해당 정책을 구성하면 구성된 URL 패턴 목록이 추적 방지에서 제외됩니다.

해당 정책을 구성하지 않으면 ‘사용자의 웹 검색 활동 추적 차단” 정책(설정된 경우) 또는 사용자의 개인 구성의 전역 기본 값이 모든 사이트에 대해 사용됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: AllowTrackingForUrls
  - GP 이름: 특정 사이트에 대한 추적 방지 예외 구성
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\AllowTrackingForUrls
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\AllowTrackingForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\AllowTrackingForUrls\2 = "[*.]contoso.edu"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: AllowTrackingForUrls
  - 예를 들어 값:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="alternateerrorpagesenabled"></a>AlternateErrorPagesEnabled

  #### <a name="suggest-similar-pages-when-a-webpage-cant-be-found"></a>웹 페이지를 찾을 수 없는 경우 비슷한 페이지 제안

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (80 이상)

  #### <a name="description"></a>설명

  Microsoft Edge에서 웹 서비스에 대한 연결을 발급하여 URL을 생성하고 DNS 오류와 같은 연결 문제에 대한 제안을 검색할 수 있도록 허용합니다.

해당 정책을 사용하면 웹 서비스를 사용하여 URL을 생성하고 네트워크 오류에 대한 제안을 검색합니다.

해당 정책을 사용하지 않도록 설정하면 웹 서비스에 대한 호출은 없으며 표준 오류 페이지가 표시됩니다.

해당 정책을 구성하지 않으면 Microsoft Edge에서는 edge://settings/privacy의 서비스에 설정된 사용자 선호도를 고려합니다.
특히 사용자가 설정하거나 해제할 수 있는 **웹 페이지를 찾을 수 없는 경우 유사한 페이지 제안** 토글이 있습니다. 해당 정책(AlternateErrorPagesEnabled)을 사용하도록 설정한 경우 웹 페이지를 찾을 수 없을 때 유사한 페이지를 제안하도록 설정되지만 사용자가 토글을 사용하여 설정을 변경할 수 없다는 점에 유의하세요. 해당 정책을 사용하지 않도록 설정한 경우 웹 페이지를 찾을 수 없을 때 유사한 페이지를 제안하도록 설정하지 않으며 사용자가 토글을 사용하여 설정을 변경할 수 없습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: AlternateErrorPagesEnabled
  - GP 이름: 웹 페이지를 찾을 수 없는 경우 유사한 페이지 제안
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: AlternateErrorPagesEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 개인 설정 키 이름: AlternateErrorPagesEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="alwaysopenpdfexternally"></a>AlwaysOpenPdfExternally

  #### <a name="always-open-pdf-files-externally"></a>외부에서 항상 PDF 파일 열기

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  Microsoft Edge에서 내부 PDF 뷰어를 사용하지 않도록 설정합니다.

해당 정책을 사용하면 Microsoft Edge에서 PDF 파일을 다운로드로 처리하고 사용자가 기본 응용 프로그램을 사용하여 해당 파일을 열 수 있도록 합니다.

Microsoft Edge가 기본 PDF 판독기인 경우 PDF 파일은 다운로드되지 않습니다. Microsoft Edge에서 계속 열립니다.

해당 정책을 구성하지 않거나 사용하지 않도록 설정하면 Microsoft Edge에서 PDF 파일을 엽니다. (사용자가 사용하지 않도록 설정하지 않은 경우)

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: AlwaysOpenPdfExternally
  - GP 이름: 외부에서 항상 PDF 파일 열기
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: AlwaysOpenPdfExternally
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: AlwaysOpenPdfExternally
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="ambientauthenticationinprivatemodesenabled"></a>AmbientAuthenticationInPrivateModesEnabled

  #### <a name="enable-ambient-authentication-for-inprivate-and-guest-profiles"></a>InPrivate 및 게스트 프로필에 대한 앰비언트 인증 사용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (81 이상)

  #### <a name="description"></a>설명

  Microsoft Edge에서 InPrivate 및 게스트 프로필에 대해 앰비언트 인증을 허용하거나 허용하지 않도록 해당 정책을 구성합니다.

앰비언트 인증이란 NTLM/Kerberos/협상 챌린지/반응 구성표를 통해 명시적 자격 증명을 제공하지 않을 경우 기본 자격 증명을 사용하는 http 인증입니다.

'RegularOnly'로 정책을 설정한 경우 정규 세션에 대해서만 앰비언트 인증을 허용합니다. InPrivate 및 게스트 세션은 앰비언트 인증을 허용하지 않습니다.

'InPrivateAndRegular'로 정책을 설정한 경우 InPrivate 및 정규 세션에 대해서만 앰비언트 인증을 허용합니다. 게스트 세션은 앰비언트 인증을 허용하지 않습니다.

'GuestAndRegular'로 정책을 설정한 경우 게스트 및 정규 세션에 대해서만 앰비언트 인증을 허용합니다. InPrivate 세션은 앰비언트 인증을 허용하지 않습니다.

‘모두’로 정책을 설정한 경우 모든 세션에 대해서 앰비언트 인증을 허용합니다.

일반 프로필에는 항상 앰비언트 인증이 허용된다는 점에 유의하세요.

Microsoft Edge 81버전 이상에서 해당 정책이 설정되지 않으면 앰비언트 인증은 정규 세션에 대해서만 사용할 수 있습니다.

정책 옵션 매핑:

* RegularOnly (0) = 정규 세션에서만 앰비언트 인증 사용

* InPrivateAndRegular (1) = InPrivate 및 정규 세션에서 앰비언트 인증 사용

* GuestAndRegular (2) = 게스트 및 정규 세션에서 앰비언트 인증 사용

* 모두 (3) = 정규, InPrivate 및 게스트 세션에서 앰비언트 인증 사용

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 이름: AmbientAuthenticationInPrivateModesEnabled
  - GP 이름: InPrivate 및 게스트 프로필에 대한 앰비언트 인증 사용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: AmbientAuthenticationInPrivateModesEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: AmbientAuthenticationInPrivateModesEnabled
  - 예를 들어 값:
``` xml
<integer>0</integer>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="appcacheforceenabled"></a>AppCacheForceEnabled

  #### <a name="allows-the-appcache-feature-to-be-re-enabled-even-if-its-turned-off-by-default"></a>AppCache 기능이 기본적으로 해제되어 있더라도 다시 사용할 수 있도록 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS(84 이상)

  #### <a name="description"></a>설명

  이 정책을 true로 설정하면 기본적으로 Microsoft Edge의 AppCache를 사용할 수 없는 경우에도 AppCache가 활성화됩니다.

이 정책을 false로 설정하거나 아무것도 설정하지 않으면 AppCache가 Microsoft Edge의 기본값을 따릅니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: AppCacheForceEnabled
  - GP 이름: AppCache 기능이 기본적으로 해제되어 있더라도 다시 사용할 수 있도록 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: AppCacheForceEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: AppCacheForceEnabled
  - 예를 들어 값:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="applicationlocalevalue"></a>ApplicationLocaleValue

  #### <a name="set-application-locale"></a>응용 프로그램 로캘 설정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows (77 이상)

  #### <a name="description"></a>설명

  Microsoft Edge에서 응용 프로그램 로캘을 구성하고 사용자가 로캘을 변경하지 못하도록 합니다.

해당 정책을 사용하면 Microsoft Edge에서 지정된 로캘을 사용합니다. 구성된 로캘이 지원되지 않는 경우 대신 'en-US'가 사용됩니다.

해당 설정을 사용하지 않도록 설정하거나 구성하지 않으면 Microsoft Edge에서 사용자가 지정한 기본 설정 로캘 (구성된 경우) 또는 대체 로캘 'en-US' 중 하나를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 문자열

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ApplicationLocaleValue
  - GP 이름: 응용 프로그램 로캘 설정
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: ApplicationLocaleValue
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
"en"
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="audiocaptureallowed"></a>AudioCaptureAllowed

  #### <a name="allow-or-block-audio-capture"></a>오디오 캡처 허용 또는 차단

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  사용자에게 오디오 캡처 장치에 대한 웹 사이트 액세스 권한을 부여할지 여부를 설정하도록 허용합니다. 해당 정책은 [AudioCaptureAllowedUrls](#audiocaptureallowedurls) 목록에 구성된 URL을 제외한 모든 URL에 적용됩니다.

해당 정책을 사용하도록 설정하거나 구성하지 않으면 (기본 설정) 사용자에게 [AudioCaptureAllowedUrls](#audiocaptureallowedurls) 목록의 URL 외에 오디오 캡처 액세스를 선택하라는 메시지가 표시됩니다. 목록에 나열된 URL에는 메시지가 표시되지 않고 액세스 권한이 부여됩니다.

해당 정책을 사용하지 않도록 설정하는 경우 사용자에게 메시지가 표시되지 않고 [AudioCaptureAllowedUrls](#audiocaptureallowedurls)에서 구성된 URL로만 오디오 캡처에 액세스할 수 있습니다.

해당 정책은 내장형 마이크 뿐만 아니라 모든 유형의 오디오 입력에 영향을 줍니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: AudioCaptureAllowed
  - GP 이름: 오디오 캡처 허용 또는 차단
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: AudioCaptureAllowed
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: AudioCaptureAllowed
  - 예를 들어 값:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="audiocaptureallowedurls"></a>AudioCaptureAllowedUrls

  #### <a name="sites-that-can-access-audio-capture-devices-without-requesting-permission"></a>권한 요청 없이 오디오 캡처 장치에 액세스할 수 있는 사이트

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  사용자에게 사용 권한을 묻지 않고 오디오 캡처 장치를 사용할 수 있는 URL 패턴을 기반으로 웹 사이트를 지정합니다. 해당 목록의 패턴은 요청 URL의 보안 원본과 일치합니다. 일치하는 경우 자동으로 오디오 캡처 장치에 대한 액세스 권한이 부여됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: AudioCaptureAllowedUrls
  - GP 이름: 권한 요청 없이 오디오 캡처 장치에 액세스할 수 있는 사이트
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\AudioCaptureAllowedUrls
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\AudioCaptureAllowedUrls\1 = "https://www.contoso.com/"
SOFTWARE\Policies\Microsoft\Edge\AudioCaptureAllowedUrls\2 = "https://[*.]contoso.edu/"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: AudioCaptureAllowedUrls
  - 예를 들어 값:
``` xml
<array>
  <string>https://www.contoso.com/</string>
  <string>https://[*.]contoso.edu/</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="audiosandboxenabled"></a>AudioSandboxEnabled

  #### <a name="allow-the-audio-sandbox-to-run"></a>오디오 샌드박스 실행 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (81 이상)

  #### <a name="description"></a>설명

  해당 정책은 오디오 프로세스 샌드박스를 제어합니다.

해당 정책을 사용하면 오디오 프로세스는 샌드 박싱된 상태에서 실행됩니다.

해당 정책을 사용하지 않도록 설정하면 오디오 프로세스가 샌드박싱되지 않은 상태에서 실행되고 WebRTC 오디오 처리 모듈은 렌더러 프로세스에서 실행됩니다.
이 경우 사용자가 오디오 하위 시스템을 샌드박싱되지 않은 상태에서 실행하는 것과 관련된 보안 위험에 노출된 채로 있게 됩니다.

해당 정책을 구성하지 않으면 플랫폼에 따라 다를 수 있는 오디오 샌드박스의 기본 구성이 사용됩니다.

해당 정책은 사용자가 샌드박스를 방해하는 보안 소프트웨어 설정을 사용하는 경우 엔터프라이즈에 해당 오디오 샌드박스를 사용하지 않도록 설정하는 유연성을 제공하는 데 그 목적이 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: AudioSandboxEnabled
  - GP 이름: 오디오 샌드박스 실행 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: AudioSandboxEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: AudioSandboxEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="autoimportatfirstrun"></a>AutoImportAtFirstRun

  #### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a>처음 실행 시 다른 브라우저의 데이터 및 설정 자동으로 가져오기

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  해당 정책을 사용하면 지정된 브라우저에서 지원되는 모든 데이터 형식 및 설정을 처음 실행 시 자동으로 가져옵니다. 처음 실행 환경에서는 가져오기 섹션도 건너뜁니다.

Microsoft Edge 레거시의 브라우저 데이터는 항상 해당 정책 값에 상관 없이 처음 실행 시 자동으로 마이그레이션됩니다.

해당 정책을 'FromDefaultBrowser'로 설정하면 관리 장치의 기본 브라우저에 해당하는 데이터 형식을 가져오게 됩니다.

해당 정책의 값으로 지정된 브라우저가 관리된 장치에 없으면 Microsoft Edge에서 사용자에게 알림 없이 간단히 가져오기를 건너뜁니다.

해당 정책을 'DisabledAutoImport'로 설정하면 처음 실행 환경의 가져오기 섹션을 완전히 건너뛰고 Microsoft Edge에서 브라우저 데이터 및 설정을 자동으로 가져오지 않습니다.

해당 정책을 'FromInternetExplorer' 값으로 설정하면 Internet Explorer에서 다음 데이터 형식을 가져옵니다.
1. 즐겨찾기 또는 책갈피
2. 저장된 암호
3. 검색 엔진
4. 검색 기록
5. 홈페이지

해당 정책을 'FromGoogleChrome' 값으로 설정하면 Google Chrome에서 다음 데이터 형식을 가져옵니다.
1. 즐겨찾기
2. 저장된 암호
3. 주소 및 기타
4. 결제 정보
5. 검색 기록
6. 설정
7. 탭 고정 및 열기
8. Extensions
9. 쿠키

참고: Google Chrome에서 가져오는 데이터 형식에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2120835](https://go.microsoft.com/fwlink/?linkid=2120835)을 참조하세요.

이 정책을 'FromSafari' 값으로 설정하면 사용자 데이터를 더 이상 Microsoft Edge로 가져오지 않습니다. 이것은 전체 디스크 액세스가 Mac에서 작동하는 방식 때문입니다.
MacOS Mojave 이상에서는 더 이상 Safari 데이터를 Microsoft Edge에 자동으로 가져올 수 없습니다.

Microsoft Edge 버전 83에서 시작하는 경우 해당 정책을 'FromMozillaFirefox' 값으로 설정하면 Mozilla Firefox에서 다음 데이터 형식을 가져옵니다.
1. 즐겨찾기 또는 책갈피
2. 저장된 암호
3. 주소 및 기타
4. 검색 기록

관리된 장치에서 특정 데이터 형식을 가져오지 못하도록 제한하려면 [ImportAutofillFormData](#importautofillformdata), [ImportBrowserSettings](#importbrowsersettings), [ImportFavorites](#importfavorites) 등의 다른 정책과 함께 해당 정책을 사용할 수 있습니다.

정책 옵션 매핑:

* FromDefaultBrowser (0) = 기본 브라우저에서 지원되는 모든 데이터 형식 및 설정을 자동으로 가져옴

* FromInternetExplorer (1) = Internet Explorer에서 지원되는 모든 데이터 형식 및 설정을 자동으로 가져옴

* FromGoogleChrome (2) = Google Chrome에서 지원되는 모든 데이터 형식 및 설정을 자동으로 가져옴

* FromSafari (3) = Safari에서 지원되는 모든 데이터 형식 및 설정을 자동으로 가져옴

* DisabledAutoImport (4) = 자동 가져오기 기능을 사용하지 않으며 처음 실행 환경의 가져오기 섹션을 건너뜀

* FromMozillaFirefox (5) = Mozilla Firefox에서 지원되는 모든 데이터 형식 및 설정을 자동으로 가져옴

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: AutoImportAtFirstRun
  - GP 이름: 처음 실행 시 다른 브라우저의 데이터 및 설정 자동으로 가져오기
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: AutoImportAtFirstRun
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000002
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: AutoImportAtFirstRun
  - 예를 들어 값:
``` xml
<integer>2</integer>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="autolaunchprotocolsfromorigins"></a>AutoLaunchProtocolsFromOrigins

  #### <a name="define-a-list-of-protocols-that-can-launch-an-external-application-from-listed-origins-without-prompting-the-user"></a>사용자에게 묻지 않고 목록에 있는 원본에서 외부 응용 프로그램을 실행할 수 있는 프로토콜 목록 정의

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS(85 이상)

  #### <a name="description"></a>설명

  사용자에게 묻지 않고 외부 응용 프로그램을 시작할 수 있는 프로토콜 목록과 각 프로토콜에 대해 허용된 원본 패턴의 관련 목록을 설정할 수 있습니다. 프로토콜을 나열하는 경우 후행 구분 기호를 포함하면 안 됩니다. 예를 들어 "skype:" 또는 "skype://" 대신 "skype"를 나열합니다.

이 정책을 구성하는 경우 프로토콜은 다음과 같은 경우에만 정책에서 프롬프트 없이 외부 응용 프로그램을 실행할 수 있습니다.

- 프로토콜이 나열된 경우

- 프로토콜을 시작하려는 사이트의 출처가 해당 프로토콜의 allow_origins 목록의 출처 패턴 중 하나와 일치하는 경우

두 조건 중 하나가 해당되지 않는 경우, 정책에 따라 외부 프로토콜 실행 프롬프트가 생략되지 않습니다.

이 정책을 구성하지 않으면 프롬프트 없이 어떤 프로토콜도 실행할 수 없습니다. 사용자는 [ExternalProtocolDialogShowAlwaysOpenCheckbox](#externalprotocoldialogshowalwaysopencheckbox) 정책이 비활성화로 설정되지 않는 한 프로토콜별/사이트별로 프롬프트를 선택 해제할 수 있습니다. 이 정책은 사용자가 설정한 프로토콜별/사이트별 프롬프트 예외에 영향을 주지 않습니다.

원본 일치 패턴은 [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)에서 설명하는 [URLBlocklist](#urlblocklist) 정책과 유사한 형식을 사용합니다.

그러나 이 정책에 대한 원본 일치 패턴에는 "/path" 또는 "@query" 요소가 포함될 수 없습니다. "/Path" 또는 "@query" 요소가 포함된 모든 패턴은 무시됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - Dictionary

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: AutoLaunchProtocolsFromOrigins
  - GP 이름: 사용자에게 묻지 않고 목록에 있는 원본에서 외부 응용 프로그램을 실행할 수 있는 프로토콜 목록 정의
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: AutoLaunchProtocolsFromOrigins
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\AutoLaunchProtocolsFromOrigins = [
  {
    "allowed_origins": [
      "example.com", 
      "http://www.example.com:8080"
    ], 
    "protocol": "spotify"
  }, 
  {
    "allowed_origins": [
      "https://example.com", 
      "https://.mail.example.com"
    ], 
    "protocol": "teams"
  }, 
  {
    "allowed_origins": [
      "*"
    ], 
    "protocol": "outlook"
  }
]
```

  ##### <a name="compact-example-value"></a>예제 값 압축:

  ```
  SOFTWARE\Policies\Microsoft\Edge\AutoLaunchProtocolsFromOrigins = [{"allowed_origins": ["example.com", "http://www.example.com:8080"], "protocol": "spotify"}, {"allowed_origins": ["https://example.com", "https://.mail.example.com"], "protocol": "teams"}, {"allowed_origins": ["*"], "protocol": "outlook"}]
  ```
  

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: AutoLaunchProtocolsFromOrigins
  - 예를 들어 값:
``` xml
<key>AutoLaunchProtocolsFromOrigins</key>
<array>
  <dict>
    <key>allowed_origins</key>
    <array>
      <string>example.com</string>
      <string>http://www.example.com:8080</string>
    </array>
    <key>protocol</key>
    <string>spotify</string>
  </dict>
  <dict>
    <key>allowed_origins</key>
    <array>
      <string>https://example.com</string>
      <string>https://.mail.example.com</string>
    </array>
    <key>protocol</key>
    <string>teams</string>
  </dict>
  <dict>
    <key>allowed_origins</key>
    <array>
      <string>*</string>
    </array>
    <key>protocol</key>
    <string>outlook</string>
  </dict>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="autoopenallowedforurls"></a>AutoOpenAllowedForURLs

  #### <a name="urls-where-autoopenfiletypes-can-apply"></a>AutoOpenFileTypes를 적용할 수 있는 URL

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS(85 이상)

  #### <a name="description"></a>설명

  [AutoOpenFileTypes](#autoopenfiletypes)가 적용될 URL 목록입니다. 이 정책은 다운로드 선반 ... > "항상 이 유형의 파일을 엽니다" 메뉴 항목을 통해 사용자가 설정한 자동으로 열리는 값에 영향을 미치지 않습니다.

이 정책에서 URL을 설정하면 URL이 이 집합의 일부이며 파일 형식이 [AutoOpenFileTypes](#autoopenfiletypes)에 나열된 경우에만 정책에 따라 파일이 자동으로 열립니다. 두 조건 중 하나가 해당되지 않으면 정책에 따라 다운로드가 자동으로 열리지 않습니다.

이 정책을 설정하지 않으면 파일 형식이 [AutoOpenFileTypes](#autoopenfiletypes)인 모든 다운로드가 자동으로 열립니다.

[https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)에 따라 URL 패턴의 형식을 지정해야 합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: AutoOpenAllowedForURLs
  - GP 이름: AutoOpenFileTypes를 적용할 수 있는 URL
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로(필수): SOFTWARE\Policies\Microsoft\Edge\AutoOpenAllowedForURLs
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\AutoOpenAllowedForURLs\1 = "example.com"
SOFTWARE\Policies\Microsoft\Edge\AutoOpenAllowedForURLs\2 = "https://ssl.server.com"
SOFTWARE\Policies\Microsoft\Edge\AutoOpenAllowedForURLs\3 = "hosting.com/good_path"
SOFTWARE\Policies\Microsoft\Edge\AutoOpenAllowedForURLs\4 = "https://server:8080/path"
SOFTWARE\Policies\Microsoft\Edge\AutoOpenAllowedForURLs\5 = ".exact.hostname.com"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: AutoOpenAllowedForURLs
  - 예를 들어 값:
``` xml
<array>
  <string>example.com</string>
  <string>https://ssl.server.com</string>
  <string>hosting.com/good_path</string>
  <string>https://server:8080/path</string>
  <string>.exact.hostname.com</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="autoopenfiletypes"></a>AutoOpenFileTypes

  #### <a name="list-of-file-types-that-should-be-automatically-opened-on-download"></a>다운로드 시 자동으로 열려야 하는 파일 형식 목록

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS(85 이상)

  #### <a name="description"></a>설명

  이 정책은 다운로드 시 자동으로 열려야 하는 파일 형식 목록을 설정합니다. 참고: 파일 형식을 나열할 때 줄 간격 구분 기호를 포함해서는 안 되므로 ".txt" 대신 "txt" 를 나열해야 합니다.

기본적으로 이 파일 형식은 모든 URL에서 자동으로 열립니다. [AutoOpenAllowedForURLs](#autoopenallowedforurls) 정책을 사용하여 이러한 파일 형식이 자동으로 열리는 URL을 제한할 수 있습니다.

자동으로 열려야 하는 유형의 파일은 여전히 활성화된 Microsoft Defender SmartScreen 검사의 대상이 되며 이러한 검사에 실패하면 열리지 않습니다.

사용자가 자동으로 열도록 이미 지정한 파일 형식은 다운로드할 때 계속 수행됩니다. 사용자가 계속해서 다른 파일 형식을 자동으로 열리도록 지정할 수 있습니다.

이 정책을 설정하지 않으면 사용자가 이미 지정한 파일 형식만 다운로드할 때 자동으로 열립니다.

이 정책은 Microsoft Active Directory 도메인에 가입된 윈도우즈 인스턴스, 장치 관리를 위해 등록된 윈도우즈 10 Pro 또는 Enterprise 인스턴스 또는 MDM을 통해 관리되거나 MCX를 통해 도메인에 가입된 MacOS 인스턴스에서만 사용할 수 있습니다..

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: AutoOpenFileTypes
  - GP 이름: 다운로드 시 자동으로 열려야 하는 파일 형식 목록
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로(필수): SOFTWARE\Policies\Microsoft\Edge\AutoOpenFileTypes
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\AutoOpenFileTypes\1 = "exe"
SOFTWARE\Policies\Microsoft\Edge\AutoOpenFileTypes\2 = "txt"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: AutoOpenFileTypes
  - 예를 들어 값:
``` xml
<array>
  <string>exe</string>
  <string>txt</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="autofilladdressenabled"></a>AutofillAddressEnabled

  #### <a name="enable-autofill-for-addresses"></a>주소에 자동 채우기 사용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  자동 채우기 기능을 사용하도록 설정하면 사용자는 이전에 저장한 정보를 사용하여 웹 양식에서 주소 정보를 자동으로 완성할 수 있습니다.

해당 정책을 사용하지 않도록 설정하면 자동 채우기는 주소 정보를 제안하거나 입력하지 않으며 웹을 검색하는 동안 사용자가 제출하는 추가 주소 정보를 저장하지 않습니다.

해당 정책을 사용하거나 구성하지 않으면 사용자는 사용자 인터페이스에서 주소에 대해 자동 채우기를 제어할 수 있습니다.

해당 정책을 사용하지 않도록 설정하는 경우 결제 및 암호 양식을 제외한 모든 웹 양식에 대한 모든 활동도 중지된다는 점에 유의하세요. 추가 항목이 저장되는 것이 아니므로 Microsoft Edge에서 이전 항목을 제안하거나 자동으로 채우지 않습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: AutofillAddressEnabled
  - GP 이름: 주소에 자동 채우기 사용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: AutofillAddressEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: AutofillAddressEnabled
  - 예를 들어 값:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="autofillcreditcardenabled"></a>AutofillCreditCardEnabled

  #### <a name="enable-autofill-for-credit-cards"></a>신용 카드에 자동 채우기 사용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  Microsoft Edge의 자동 채우기 기능을 사용하도록 설정하면 사용자는 이전에 저장한 정보를 사용하여 웹 양식에서 신용 카드 정보를 자동으로 완성할 수 있습니다.

해당 정책을 사용하지 않도록 설정하면 자동 채우기는 신용 카드 정보를 제안하거나 입력하지 않으며 웹을 검색하는 동안 사용자가 제출하는 추가 신용 카드 정보를 저장하지 않습니다.

해당 정책을 사용하거나 구성하지 않으면 사용자는 신용 카드에 대해 자동 채우기를 제어할 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: AutofillCreditCardEnabled
  - GP 이름: 신용 카드에 자동 채우기 사용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: AutofillCreditCardEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: AutofillCreditCardEnabled
  - 예를 들어 값:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="autoplayallowed"></a>AutoplayAllowed

  #### <a name="allow-media-autoplay-for-websites"></a>웹 사이트에 미디어 자동 실행 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (78 이상)

  #### <a name="description"></a>설명

  해당 정책은 웹 사이트에 대한 미디어 자동 실행 정책을 설정합니다.

기본 설정인 "구성되지 않음"은 현재 미디어 자동 실행 설정을 고려하며 사용자가 자동 실행 설정을 구성할 수 있도록 합니다.

"사용"으로 설정하면 미디어 자동 실행이 "허용"으로 설정됩니다.  모든 웹 사이트에서 미디어 자동 실행이 허용됩니다. 사용자가 해당 정책을 재정의할 수 없습니다.

"사용 안 함"으로 설정하면 미디어 자동 실행이 "차단"으로 설정됩니다.  웹 사이트에서 미디어 자동 실행이 차단됩니다. 사용자가 해당 정책을 재정의할 수 없습니다.

해당 정책을 적용하려면 탭을 닫았다가 다시 열어야 합니다.


  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: AutoplayAllowed
  - GP 이름: 웹 사이트에 미디어 자동 실행 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: AutoplayAllowed
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: AutoplayAllowed
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="backgroundmodeenabled"></a>BackgroundModeEnabled

  #### <a name="continue-running-background-apps-after-microsoft-edge-closes"></a>Microsoft Edge 종료 후 백그라운드 앱 계속 실행

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows (77 이상)

  #### <a name="description"></a>설명

  Microsoft Edge 프로세스를 OS 로그인에서 시작하고 마지막 브라우저 창이 닫힌 후 계속 실행할 수 있도록 합니다. 해당 시나리오에서는 백그라운드 앱과 현재 검색 세션이 세션 쿠키를 포함하여 계속 활성 상태로 유지됩니다. 열려 있는 백그라운드 프로세스는 시스템 트레이에 아이콘을 표시하고 언제 어디서나 종료할 수 있습니다.

해당 정책을 사용하면 백그라운드 모드가 설정됩니다.

해당 정책을 사용하지 않으면 백그라운드 모드가 해제됩니다.

해당 정책을 구성하지 않으면 처음에 배경 모드가 해제되고 사용자는 edge://settings/system에서 해당 동작을 구성할 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: BackgroundModeEnabled
  - GP 이름: Microsoft Edge 종료 후 백그라운드 앱 계속 실행
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: BackgroundModeEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="backgroundtemplatelistupdatesenabled"></a>BackgroundTemplateListUpdatesEnabled

  #### <a name="enables-background-updates-to-the-list-of-available-templates-for-collections-and-other-features-that-use-templates"></a>서식 파일을 사용하는 컬렉션 및 기타 기능에 대해 사용 가능한 서식 파일 목록의 백그라운드 업데이트 사용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (79 이상)

  #### <a name="description"></a>설명

  서식 파일을 사용하는 컬렉션 및 기타 기능에 대해 사용 가능한 서식 파일 목록의 백그라운드 업데이트를 사용하거나 사용하지 않도록 설정할 수 있습니다.  서식 파일은 페이지가 컬렉션에 저장될 때 웹 페이지에서 서식 메타 데이터를 추출하기 위해 사용됩니다.

해당 설정을 사용하도록 설정하거나 구성하지 않으면 사용 가능한 서식 파일 목록이 Microsoft 서비스의 백그라운드에서 24시간 마다 다운로드됩니다.

해당 설정을 사용하지 않으면 사용 가능한 서식 파일 목록은 요청 시 다운로드됩니다. 해당 유형의 다운로드는 컬렉션 및 기타 기능에 대한 성능을 저하시킬 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: BackgroundTemplateListUpdatesEnabled
  - GP 이름: 서식 파일을 사용하는 컬렉션 및 기타 기능에 대해 사용 가능한 서식 파일 목록의 백그라운드 업데이트 사용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: BackgroundTemplateListUpdatesEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: BackgroundTemplateListUpdatesEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="bingadssuppression"></a>BingAdsSuppression

  #### <a name="block-all-ads-on-bing-search-results"></a>Bing 검색 결과에서 모든 광고 차단

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (83 이상)

  #### <a name="description"></a>설명

  Bing.com에서 광고 없는 검색 환경을 사용하도록 설정합니다.

해당 정책을 사용하면 사용자는 Bing.com에서 검색하고 광고 없는 검색 환경을 이용할 수 있습니다. 동시에 유해 정보 차단 설정은 '고급'으로 설정되고 사용자가 변경할 수 없습니다.

해당 정책을 구성하지 않으면 기본 환경은 Bing.com에서 검색 결과에 광고를 포함합니다. 유해 정보 차단 기능은 기본적으로 '보통'으로 설정되며 사용자가 변경할 수 있습니다.

해당 정책은 Microsoft에서 EDU 테넌트로 식별된 K-12 SKU에서만 사용할 수 있습니다.

해당 정책에 대한 자세한 내용 또는 다음의 시나리오를 사용자에게 적용하려면 [https://go.microsoft.com/fwlink/?linkid=2119711](https://go.microsoft.com/fwlink/?linkid=2119711)을 참조하세요.

* .EDU 테넌트가 있으면 해당 정책이 작동하지 않습니다.

* 광고 무료 검색 환경을 위한 IP 허용 목록이 있습니다.

* Microsoft Edge 레거시에서 광고 없는 검색 환경을 사용하고 있으며 새 버전의 Microsoft Edge로 업그레이드해야 합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: BingAdsSuppression
  - GP 이름: Bing 검색 결과에서 모든 광고 차단
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: BingAdsSuppression
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: BingAdsSuppression
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="blockthirdpartycookies"></a>BlockThirdPartyCookies

  #### <a name="block-third-party-cookies"></a>타사 쿠키 차단

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  주소 표시줄에 있는 도메인에서 나오지 않은 웹 페이지 요소를 차단하여 쿠키를 설정하지 않도록 합니다.

해당 정책을 사용하면 주소 표시줄에 있는 도메인에서 나오지 않은 웹 페이지 요소로 쿠키를 설정할 수 없습니다.

해당 정책을 사용하지 않도록 설정하는 경우 주소 표시줄에 있는 도메인 외에서 나온 웹 페이지 요소로 쿠키를 설정할 수 있습니다.

해당 정책을 구성하지 않으면 타사 쿠키를 사용할 수 있지만 사용자는 해당 설정을 변경할 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: BlockThirdPartyCookies
  - GP 이름: 타사 쿠키 차단
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: BlockThirdPartyCookies
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: BlockThirdPartyCookies
  - 예를 들어 값:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="browseraddprofileenabled"></a>BrowserAddProfileEnabled

  #### <a name="enable-profile-creation-from-the-identity-flyout-menu-or-the-settings-page"></a>ID 플라이아웃 메뉴 또는 설정 페이지에서 프로필 만들기 사용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  사용자가 **프로필 추가** 옵션을 사용하여 새 프로필을 만들도록 합니다.
해당 정책을 사용하도록 설정하거나 구성하지 않으면 Microsoft Edge에서 사용자가 ID 플라이 아웃 메뉴 또는 설정 페이지에서 **프로필 추가**를 사용하여 새 프로필을 만들 수 있도록 합니다.

해당 정책을 사용하지 않도록 설정하면 사용자는 ID 플라이 아웃 메뉴 또는 설정 페이지에서 새 프로필을 추가할 수 없습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: BrowserAddProfileEnabled
  - GP 이름: ID 플라이아웃 메뉴 또는 설정 페이지에서 프로필 만들기 사용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: BrowserAddProfileEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: BrowserAddProfileEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="browserguestmodeenabled"></a>BrowserGuestModeEnabled

  #### <a name="enable-guest-mode"></a>게스트 모드 사용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  Microsoft Edge에서 게스트 프로필을 사용할 수 있도록 옵션을 설정합니다. 게스트 프로필에서 브라우저는 기존 프로필에서 검색 데이터를 가져오지 않으며 모든 게스트 프로필이 닫히면 검색 데이터를 삭제합니다.

해당 정책을 사용하도록 설정하거나 구성하지 않으면 Microsoft Edge에서 사용자가 게스트 프로필을 검색할 수 있습니다.

해당 정책을 사용하지 않도록 설정하면 Microsoft Edge에서 사용자가 게스트 프로필을 검색할 수 없습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: BrowserGuestModeEnabled
  - GP 이름: 게스트 모드 사용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: BrowserGuestModeEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: BrowserGuestModeEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="browsernetworktimequeriesenabled"></a>BrowserNetworkTimeQueriesEnabled

  #### <a name="allow-queries-to-a-browser-network-time-service"></a>브라우저 네트워크 시간 서비스에 쿼리 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  Microsoft Edge가 경우에 따라 브라우저 네트워크 시간 서비스에 쿼리를 전송하는 것을 방지하여 정확한 타임 스탬프를 검색합니다.

해당 정책을 사용하지 않도록 설정하면 Microsoft Edge가 브라우저 네트워크 시간 서비스에 대한 쿼리 전송을 중지합니다.

해당 정책을 사용하도록 설정하거나 구성하지 않으면 Microsoft Edge에서 경우에 따라 브라우저 네트워크 시간 서비스에 쿼리를 전송합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: BrowserNetworkTimeQueriesEnabled
  - GP 이름: 브라우저 네트워크 시간 서비스에 쿼리 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: BrowserNetworkTimeQueriesEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: BrowserNetworkTimeQueriesEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="browsersignin"></a>BrowserSignin

  #### <a name="browser-sign-in-settings"></a>브라우저 로그인 설정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  사용자가 계정으로 Microsoft Edge에 로그인하고 동기화 및 SSO(Single Sign-On)과 같은 계정 관련 서비스를 사용할 수 있는지 여부를 지정합니다. 동기화 가용성을 제어하려면 대신 [SyncDisabled](#syncdisabled) 정책을 사용합니다.

해당 정책을 '사용 안 함'으로 설정하는 경우 [NonRemovableProfileEnabled](#nonremovableprofileenabled) 정책은 브라우저 프로필에서 자동으로 로그인 생성을 하지 못하도록 설정하므로 [NonRemovableProfileEnabled](#nonremovableprofileenabled) 정책도 사용하지 않도록 설정해야 합니다. 두 정책 모두 설정된 경우 Microsoft Edge에서 [NonRemovableProfileEnabled](#nonremovableprofileenabled) 정책이 사용하지 않도록 설정한 경우처럼 '브라우저 로그인 사용 안 함' 정책을 사용하고 작동합니다.

해당 정책을 '사용'으로 설정하면 사용자는 브라우저에 로그인할 수 있습니다. 브라우저에 로그인할 수 있다고 해서 기본적으로 동기화가 설정되어 있음을 의미하지는 않습니다. 사용자가 별도로 옵트인하여해당 기능을 사용해야 합니다.

해당 정책을 '강제'로 설정하는 경우 사용자는 브라우저를 사용하려면 프로필에 로그인해야 합니다. 기본적으로 해당 기능을 사용하면 도메인 관리자가 동기화를 사용하지 않도록 설정하거나 [SyncDisabled](#syncdisabled) 정책을 사용하지 않는 한 사용자는 계정에 동기화할지 여부를 선택할 수 있습니다. [BrowserGuestModeEnabled](#browserguestmodeenabled) 정책의 기본값은 False로 설정됩니다.

해당 정책을 구성하지 않으면 사용자는 브라우저 로그인 옵션을 사용하도록 설정하고 해당 옵션을 사용할 것인지 여부를 결정할 수 있습니다.

정책 옵션 매핑:

* 사용 안 함 (0) = 브라우저 로그인 사용 안 함

* 사용 (1) = 브라우저 로그인 사용

* 강제 (2) = 사용자가 브라우저를 사용하도록 강제 로그인

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: BrowserSignin
  - GP 이름: 브라우저 로그인 설정
  - GP 경로(필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로(권장): 해당 없음
  - 값 이름: BrowserSignin
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000002
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: BrowserSignin
  - 예를 들어 값:
``` xml
<integer>2</integer>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="browsingdatalifetime"></a>BrowsingDataLifetime

  #### <a name="browsing-data-lifetime-settings"></a>데이터 수명 설정 검색

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 macOS(89 이상)

  #### <a name="description"></a>설명

  Microsoft Edge에 대한 검색 데이터 수명 설정을 구성합니다.
이 정책은 선택한 검색 데이터의 수명을 제어합니다. 동기화를 사용하도록 설정한 경우 해당 정책은 효과가 없습니다.
사용 가능한 데이터 형식은 'browsing_history', 'download_history', 'cookies_and_other_site_data', 'cached_images_and_files', 'password_signin', 'autofill', 'site_settings' 및 'hosted_app_data'입니다.
Microsoft Edge는 'time_to_live_in_hours'보다 오래된 선택한 유형의 데이터를 정기적으로 제거합니다. 데이터 삭제는 특정 간격을 두고 시행되므로 일부 데이터는 좀 더 오래 보관될 수 있지만 예상 ‘time_to_live_in_hours’보다 두 배 이상 오래 보관되지는 않습니다.


  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - Dictionary

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: BrowsingDataLifetime
  - GP 이름: 검색 데이터 수명 설정
  - GP 경로(필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로(권장): 해당 없음
  - 값 이름: BrowsingDataLifetime
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\BrowsingDataLifetime = [
  {
    "data_types": [
      "browsing_history"
    ], 
    "time_to_live_in_hours": 24
  }, 
  {
    "data_types": [
      "password_signin", 
      "autofill"
    ], 
    "time_to_live_in_hours": 12
  }
]
```

  ##### <a name="compact-example-value"></a>예제 값 압축:

  ```
  SOFTWARE\Policies\Microsoft\Edge\BrowsingDataLifetime = [{"data_types": ["browsing_history"], "time_to_live_in_hours": 24}, {"data_types": ["password_signin", "autofill"], "time_to_live_in_hours": 12}]
  ```
  

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: BrowsingDataLifetime
  - 값 예시:
``` xml
<key>BrowsingDataLifetime</key>
<array>
  <dict>
    <key>data_types</key>
    <array>
      <string>browsing_history</string>
    </array>
    <key>time_to_live_in_hours</key>
    <integer>24</integer>
  </dict>
  <dict>
    <key>data_types</key>
    <array>
      <string>password_signin</string>
      <string>autofill</string>
    </array>
    <key>time_to_live_in_hours</key>
    <integer>12</integer>
  </dict>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="builtindnsclientenabled"></a>BuiltInDnsClientEnabled

  #### <a name="use-built-in-dns-client"></a>기본 제공 DNS 클라이언트 사용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  기본 제공 DNS 클라이언트를 사용할지 여부를 제어합니다.

이 정책은 DNS 서버(운영 체제 DNS 클라이언트 또는 Microsoft Edge의 기본 제공 DNS 클라이언트)와 통신하는 데 사용되는 소프트웨어 스택을 제어합니다. 이 정책은 사용되는 DNS 서버에 영향을 주지 않습니다. 예를 들어 운영 체제가 엔터프라이즈 DNS 서버를 사용하도록 구성된 경우 기본 제공 DNS 클라이언트에서 동일한 서버를 사용하게 됩니다. 또한 DNS-over-HTTPS가 사용되는지도 제어하지 않습니다. Microsoft Edge는 항상 DNS-over-HTTPS 요청에 대해 기본 제공 확인자를 사용합니다. DNS-over-HTTPS 제어에 대한 자세한 내용은 [DnsOverHttpsMode](#dnsoverhttpsmode) 정책을 참조하세요.

해당 정책을 사용하면 기본 제공 DNS 클라이언트(사용 가능한 경우)가 사용됩니다.

해당 정책을 사용하지 않도록 설정하면 기본 제공 DNS 클라이언트는 DNS-over-HTTPS를 사용 중일 때만 사용됩니다.

해당 정책을 구성하지 않으면 기본 제공 DNS 클라이언트가 macOS 및 Android에서 기본적으로 사용하도록 설정됩니다(개인 DNS와 VPN을 모두 사용할 수 없는 경우).

  #### <a name="supported-features"></a>지원되는 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: BuiltInDnsClientEnabled
  - GP 이름: 기본 제공 DNS 클라이언트 사용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: BuiltInDnsClientEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: BuiltInDnsClientEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="builtincertificateverifierenabled"></a>BuiltinCertificateVerifierEnabled

  #### <a name="determines-whether-the-built-in-certificate-verifier-will-be-used-to-verify-server-certificates-deprecated"></a>서버 인증서를 확인하는 데 기본 제공 인증서 검증 도구를 사용할지 여부 결정(사용되지 않음)

  >DEPRECATED: 해당 정책은 사용되지 않습니다. 현재 지원되고 있지만 이후 릴리스에서는 더 이상 사용되지 않을 예정입니다.
  
  #### <a name="supported-versions"></a>지원 버전:

  - MacOS (83 이상)

  #### <a name="description"></a>설명

  이 정책은 엔터프라이즈에 환경을 업데이트할 수 있는 더 많은 시간을 제공하고, 기본 제공 인증서 확인자와 호환되지 않는 경우 문제를 보고하는 단기 메커니즘으로만 제공되므로 더 이상 사용되지 않습니다.

Mac OS X에서 레거시 인증서 검증 도구에 대한 지원이 제거될 예정인 경우 Microsoft Edge 버전 92에서 작동하지 않습니다.


  #### <a name="supported-features"></a>지원되는 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: BuiltinCertificateVerifierEnabled
  - 예를 들어 값:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="certificatetransparencyenforcementdisabledforcas"></a>CertificateTransparencyEnforcementDisabledForCas

  #### <a name="disable-certificate-transparency-enforcement-for-a-list-of-subjectpublickeyinfo-hashes"></a>subjectPublicKeyInfo 해시 목록에 대한 인증서 투명도 적용 해제

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  subjectPublicKeyInfo 해시 목록에 대한 인증서 투명도 요구 사항의 적용을 해제합니다.

해당 정책을 사용하면 지정된 subjectPublicKeyInfo 해시 중 하나를 사용하는 인증서를 포함한 인증서 체인에 대해 인증서 투명성 공개 요구 사항을 사용할 수 없습니다. 이 경우 인증서가 제대로 공개되지 않았으므로 신뢰할 수 없어도 엔터프라이즈 호스트에 계속 사용할 수 있습니다.

해당 정책을 설정했을 때 인증서 투명성 적용을 사용하지 않으려면 다음 조건 중 하나를 충족해야 합니다.
1. 해시는 서버 인증서의 subjectPublicKeyInf에 대한 것입니다.
2. 해시는 인증서 체인의 CA 인증서에 표시되는 subjectPublicKeyInfo에 대한 것이며 CA 인증서는 X.509v3 nameConstraints 확장을 통해 제한되고 하나 이상의 directoryName nameConstraints는 permittedSubtrees에 존재하며 directoryName에 organizationName 특성이 포함되어 있습니다.
3. 해시는 인증서 체인의 CA 인증서에 표시되는 subjectPublicKeyInfo에 대한 것이며 CA 인증서는 인증서 Subject의 organizationName 특성을 하나 이상 가지고 서버 인증서에는 동일한 수의 organizationName 특성이 동일한 순서로 포함되며 byte-for-byte의 동일한 값이 포함됩니다.

subjectPublicKeyInfo 해시는 해시 알고리즘 이름인 "/" 문자를 연결하여 지정되며 해시 알고리즘의 Base64 인코딩은 지정된 인증서의 DER 인코딩 subjectPublicKeyInfo에 적용됩니다. 해당 Base64 인코딩은 RFC 7469, 섹션 2.4에 정의된 대로 SPKI 지문과 같은 형식입니다. 인식할 수 없는 해시 알고리즘은 무시됩니다. 이번에 유일하게 지원된 해시 알고리즘은 "sha256"입니다.

해당 정책을 사용하지 않도록 설정하거나 구성하지 않으면 인증서 투명성을 통해 공개하도록 요구되는 모든 인증서가 인증서 투명성 정책에 따라 공개되지 않은 경우 신뢰할 수 없는 것으로 처리됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: CertificateTransparencyEnforcementDisabledForCas
  - GP 이름: subjectPublicKeyInfo 해시 목록에 대한 인증서 투명도 적용 해제
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\CertificateTransparencyEnforcementDisabledForCas
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\CertificateTransparencyEnforcementDisabledForCas\1 = "sha256/AAAAAAAAAAAAAAAAAAAAAA=="
SOFTWARE\Policies\Microsoft\Edge\CertificateTransparencyEnforcementDisabledForCas\2 = "sha256//////////////////////w=="

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: CertificateTransparencyEnforcementDisabledForCas
  - 예를 들어 값:
``` xml
<array>
  <string>sha256/AAAAAAAAAAAAAAAAAAAAAA==</string>
  <string>sha256//////////////////////w==</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="certificatetransparencyenforcementdisabledforlegacycas"></a>CertificateTransparencyEnforcementDisabledForLegacyCas

  #### <a name="disable-certificate-transparency-enforcement-for-a-list-of-legacy-certificate-authorities"></a>레거시 인증 기관 목록에 대한 인증서 투명도 적용 해제

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  레거시 인증 기관(Cas) 목록에 대한 인증서 투명도 적용을 해제합니다.

해당 정책을 사용하면 지정된 subjectPublicKeyInfo 해시 중 하나를 사용하는 인증서를 포함한 인증서 체인에 대해 인증서 투명성 공개 요구 사항을 사용할 수 없습니다. 이 경우 인증서가 제대로 공개되지 않았으므로 신뢰할 수 없어도 엔터프라이즈 호스트에 계속 사용할 수 있습니다.

인증서 투명성 적용을 사용하지 않도록 설정하려면 레거시 인증 기관(CA)으로 인식되는 CA 인증서에 표시되는 subjectPublicKeyInfo에 해시를 설정해야 합니다. 레거시 CA는 Microsoft Edge에서 지원하는 하나 이상의 운영 체제에서 기본적으로 공개적으로 신뢰할 수 있는 CA입니다.

사용자는 해시 알고리즘 이름인 "/" 문자를 연결하여 지정되는 subjectPublicKeyInfo 해시를 지정하고 해시 알고리즘의 Base64 인코딩은 지정된 인증서의 DER 인코딩 subjectPublicKeyInfo에 적용됩니다. 해당 Base64 인코딩은 RFC 7469, 섹션 2.4에 정의된 대로 SPKI 지문과 같은 형식입니다. 인식할 수 없는 해시 알고리즘은 무시됩니다. 이번에 유일하게 지원된 해시 알고리즘은 "sha256"입니다.

해당 정책을 구성하지 않으면 인증서 투명성을 통해 공개하도록 요구되는 모든 인증서가 인증서 투명성 정책에 따라 공개되지 않은 경우 신뢰할 수 없는 것으로 처리됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: CertificateTransparencyEnforcementDisabledForLegacyCas
  - GP 이름: 레거시 인증 기관 목록에 대한 인증서 투명도 적용 해제
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\CertificateTransparencyEnforcementDisabledForLegacyCas
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\CertificateTransparencyEnforcementDisabledForLegacyCas\1 = "sha256/AAAAAAAAAAAAAAAAAAAAAA=="
SOFTWARE\Policies\Microsoft\Edge\CertificateTransparencyEnforcementDisabledForLegacyCas\2 = "sha256//////////////////////w=="

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: CertificateTransparencyEnforcementDisabledForLegacyCas
  - 예를 들어 값:
``` xml
<array>
  <string>sha256/AAAAAAAAAAAAAAAAAAAAAA==</string>
  <string>sha256//////////////////////w==</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="certificatetransparencyenforcementdisabledforurls"></a>CertificateTransparencyEnforcementDisabledForUrls

  #### <a name="disable-certificate-transparency-enforcement-for-specific-urls"></a>특정 URL에 대한 인증서 투명도 적용 해제

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  목록에 나열된 URL에 대해 인증서 투명성 요구 사항을 적용하지 않도록 설정합니다.

해당 정책을 사용하면 인증서 투명도를 통해 지정된 URL의 호스트 이름에 대한 인증서를 공개할 수 없습니다. 이 경우 인증서가 제대로 공개되지 않았으므로 신뢰할 수 없는 인증서를 사용할 수 있지만 해당 호스트에 대해 잘못 발급된 인증서를 검색하기 더 어려워질 수 있습니다.

[https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)에 따라 URL 패턴을 구성합니다. 인증서는 구성표, 포트 또는 경로에 관계 없이 지정된 호스트 이름에 대해 유효하므로 URL의 호스트 이름 부분만 고려됩니다. 와일드카드 호스트는 지원되지 않습니다.

해당 정책을 구성하지 않으면 인증서 투명성을 통해 공개해야 하는 모든 인증서가 공개되지 않는 경우 신뢰할 수 없는 것으로 처리됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: CertificateTransparencyEnforcementDisabledForUrls
  - GP 이름: 특정 URL에 대한 인증서 투명도 적용 해제
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\CertificateTransparencyEnforcementDisabledForUrls
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\CertificateTransparencyEnforcementDisabledForUrls\1 = "contoso.com"
SOFTWARE\Policies\Microsoft\Edge\CertificateTransparencyEnforcementDisabledForUrls\2 = ".contoso.com"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: CertificateTransparencyEnforcementDisabledForUrls
  - 예를 들어 값:
``` xml
<array>
  <string>contoso.com</string>
  <string>.contoso.com</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="clearbrowsingdataonexit"></a>ClearBrowsingDataOnExit

  #### <a name="clear-browsing-data-when-microsoft-edge-closes"></a>Microsoft Edge 종료 시 데이터 검색 삭제

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (78 이상)

  #### <a name="description"></a>설명

  Microsoft Edge 종료 시 Microsoft Edge는 기본적으로 데이터를 삭제하지 않습니다. 데이터 검색에는 양식, 암호 및 방문한 웹 사이트에서 입력한 정보가 포함되어 있습니다.

해당 정책을 사용하면 Microsoft Edge를 종료할 때마다 모든 데이터 검색이 삭제됩니다. 해당 정책을 사용하면 [DefaultCookiesSetting](#defaultcookiessetting) 정책을 구성한 방식 보다 우선됩니다.

해당 정책을 사용하지 않도록 설정하거나 구성하지 않으면 사용자는 설정에서 데이터 검색 삭제 옵션을 구성할 수 있습니다.

해당 정책을 사용하면 [AllowDeletingBrowserHistory](#allowdeletingbrowserhistory) 또는 [ClearCachedImagesAndFilesOnExit](#clearcachedimagesandfilesonexit) 정책을 구성하지 않아야 합니다. 두 정책 모두 데이터 검색을 삭제하는 정책이기 때문입니다. 이전 정책과 해당 정책을 구성하는 경우 Microsoft Edge 종료 시 [AllowDeletingBrowserHistory](#allowdeletingbrowserhistory) 또는 [ClearCachedImagesAndFilesOnExit](#clearcachedimagesandfilesonexit) 정책을 구성한 방식에 상관 없이 모든 데이터 검색이 삭제됩니다.

끝낼 때 삭제할 수 없도록 쿠키를 제외하려면 [SaveCookiesOnExit](#savecookiesonexit) 정책을 구성 합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ClearBrowsingDataOnExit
  - GP 이름: Microsoft Edge 종료 시 데이터 검색 삭제
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: ClearBrowsingDataOnExit
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ClearBrowsingDataOnExit
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="clearcachedimagesandfilesonexit"></a>ClearCachedImagesAndFilesOnExit

  #### <a name="clear-cached-images-and-files-when-microsoft-edge-closes"></a>Microsoft Edge 종료 시 캐시된 이미지 및 파일 삭제

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (83 이상)

  #### <a name="description"></a>설명

  Microsoft Edge 종료 시 Microsoft Edge는 기본적으로 캐시된 이미지를 삭제하지 않습니다.

해당 정책을 사용하면 Microsoft Edge를 종료할 때마다 캐시된 모든 이미지가 삭제됩니다.

해당 정책을 사용하지 않도록 설정하면 사용자는 edge://settings/clearBrowsingDataOnClose에서 캐시된 이미지 및 파일 옵션을 구성할 수 없습니다.

해당 정책을 구성하지 않으면 사용자는 종료 시 캐시된 이미지 및 파일의 삭제 여부를 선택할 수 있습니다.

해당 정책을 사용하지 않도록 설정하면 [ClearBrowsingDataOnExit](#clearbrowsingdataonexit) 정책을 사용하지 않아야 합니다. 두 정책 모두 데이터 삭제를 처리하기 때문입니다. 두 정책을 모두 사용하면 Microsoft Edge 종료 시 [ClearCachedImagesAndFilesOnExit](#clearcachedimagesandfilesonexit) 정책을 구성하는 방법에 관계 없이 [ClearBrowsingDataOnExit](#clearbrowsingdataonexit) 정책이 우선되어 모든 데이터가 삭제됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ClearCachedImagesAndFilesOnExit
  - GP 이름: Microsoft Edge 종료 시 캐시된 이미지 및 파일 삭제
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: ClearCachedImagesAndFilesOnExit
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ClearCachedImagesAndFilesOnExit
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="clickonceenabled"></a>ClickOnceEnabled

  #### <a name="allow-users-to-open-files-using-the-clickonce-protocol"></a>사용자가 ClickOnce 프로토콜을 사용하여 파일을 열 수 있도록 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows (78 이상)

  #### <a name="description"></a>설명

  사용자가 ClickOnce 프로토콜을 사용하여 파일을 열 수 있도록 허용합니다. ClickOnce 프로토콜을 사용하면 웹 사이트에서 사용자의 컴퓨터나 장치에 있는 ClickOnce 파일 처리기를 사용하여 특정 URL에서 브라우저가 파일을 열도록 요청할 수 있습니다.

해당 정책을 사용하면 사용자는 ClickOnce 프로토콜을 사용하여 파일을 열 수 있습니다. 해당 정책은 edge://flags/page에서 사용자의 ClickOnce 설정을 재정의합니다.

해당 정책을 사용하지 않도록 설정하면 사용자는 ClickOnce 프로토콜을 사용하여 파일을 열 수 없습니다. 대신 브라우저를 사용하여 파일 시스템에 파일을 저장합니다. 해당 정책은 edge://flags/page에서 사용자의 ClickOnce 설정을 재정의합니다.

이 정책을 구성하지 않으면 Microsoft Edge 87 이전 버전의 사용자는 기본적으로 ClickOnce 프로토콜을 사용하여 파일을 열 수 없습니다. 그러나 사용자에게 edge://flags/page에서 ClickOnce 프로토콜을 사용할 수 있도록 설정하는 옵션이 있습니다. Microsoft Edge 버전 87 이상을 사용하는 사용자는 기본적으로 ClickOnce 프로토콜을 사용하여 파일을 열 수 있지만 edge://flags/page를 사용하여 ClickOnce 프로토콜을 사용하지 않도록 설정하는 옵션이 있습니다.

ClickOnce를 사용하지 않도록 설정하면 ClickOnce 응용 프로그램(.application 파일)이 제대로 시작되지 않을 수 있습니다.

ClickOnce에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2103872](https://go.microsoft.com/fwlink/?linkid=2103872) 및 [https://go.microsoft.com/fwlink/?linkid=2099880](https://go.microsoft.com/fwlink/?linkid=2099880)를 참조하세요.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ClickOnceEnabled
  - GP 이름: 사용자가 ClickOnce 프로토콜을 사용하여 파일을 열 수 있도록 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: ClickOnceEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="collectionsservicesandexportsblocklist"></a>CollectionsServicesAndExportsBlockList

  #### <a name="block-access-to-a-specified-list-of-services-and-export-targets-in-collections"></a>지정된 서비스 목록에 대한 액세스를 차단하고 컬렉션에서 대상 내보내기

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (86 이상)

  #### <a name="description"></a>설명

  Microsoft Edge의 컬렉션 기능에서 사용자가 액세스할 수 없는 특정 서비스를 나열하고 대상을 내보냅니다. 여기에는 Bing에서 추가 데이터를 표시하고 Microsoft 제품 또는 외부 파트너에 컬렉션을 내보내는 작업이 포함됩니다.

이 정책을 사용하면 지정된 목록과 일치하는 서비스 및 내보내기 대상이 차단됩니다.

해당 정책을 구성하지 않으면 허용될 수 있는 서비스 및 내보내기 대상에 대한 제한 사항이 적용되지 않습니다.

정책 옵션 매핑:

* pinterest_suggestions (pinterest_suggestions) = Pinterest 제안

* collections_share (collections_share) = 컬렉션 공유

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: CollectionsServicesAndExportsBlockList
  - GP 이름: 지정된 서비스 목록에 대한 액세스를 차단하고 컬렉션에서 대상 내보내기
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\Policies\Microsoft\Edge\CollectionsServicesAndExportsBlockList
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\CollectionsServicesAndExportsBlockList\1 = "pinterest_suggestions"
SOFTWARE\Policies\Microsoft\Edge\CollectionsServicesAndExportsBlockList\2 = "collections_share"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: CollectionsServicesAndExportsBlockList
  - 예를 들어 값:
``` xml
<array>
  <string>pinterest_suggestions</string>
  <string>collections_share</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="commandlineflagsecuritywarningsenabled"></a>CommandLineFlagSecurityWarningsEnabled

  #### <a name="enable-security-warnings-for-command-line-flags"></a>명령줄 플래그에 대한 보안 경고 사용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (78 이상)

  #### <a name="description"></a>설명

  해당 정책을 사용하지 않도록 설정하면 잠재적인 위험 가능성이 있는 명령줄 플래그를 사용하여 Microsoft Edge를 시작할 때 보안 경고가 표시되지 않습니다.

해당 정책을 사용하거나 설정하지 않은 경우 해당 명령줄 플래그를 사용하여 Microsoft Edge를 시작할 때 보안 경고가 표시됩니다.

예를 들어  --disable-gpu-sandbox 플래그는 다음의 경고를 생성합니다: 지원되지 않는 명령줄 플래그(disable-gpu-sandbox)를 사용하고 있습니다. 이는 안정성과 보안 위험을 야기합니다.

이 정책은 Microsoft Active Directory 도메인에 가입된 윈도우즈 인스턴스, 장치 관리를 위해 등록된 윈도우즈 10 Pro 또는 Enterprise 인스턴스 또는 MDM을 통해 관리되거나 MCX를 통해 도메인에 가입된 MacOS 인스턴스에서만 사용할 수 있습니다..

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: CommandLineFlagSecurityWarningsEnabled
  - GP 이름: 명령줄 플래그에 대한 보안 경고 사용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: CommandLineFlagSecurityWarningsEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: CommandLineFlagSecurityWarningsEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="componentupdatesenabled"></a>ComponentUpdatesEnabled

  #### <a name="enable-component-updates-in-microsoft-edge"></a>Microsoft Edge에서 구성 요소 업데이트 사용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  해당 정책을 사용하도록 설정하거나 구성하지 않으면 Microsoft Edge에서 구성 요소 업데이트를 사용할 수 있습니다.

해당 정책을 사용하지 않거나 False로 설정하면 Microsoft Edge의 모든 구성 요소에 대해 구성 요소 업데이트를 사용할 수 없습니다.

하지만 일부 구성 요소는 해당 정책에서 제외됩니다. 여기에는 브라우저 동작을 크게 변경하지 않거나 보안에 중요한 실행 코드를 포함하지 않는 모든 구성 요소가 포함됩니다. 즉, 해당 정책을 사용하지 않도록 설정한 경우에도 "보안상 중요" 라고 간주되는 업데이트는 계속 적용됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ComponentUpdatesEnabled
  - GP 이름: Microsoft Edge에서 구성 요소 업데이트 사용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: ComponentUpdatesEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ComponentUpdatesEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="configuredonottrack"></a>ConfigureDoNotTrack

  #### <a name="configure-do-not-track"></a>Do Not Track 구성

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  추적 정보를 요청하는 웹 사이트로 Do Not Track 요청의 전송 여부를 지정합니다. Do Not Track을 요청하면 방문한 웹 사이트에서 검색 작업을 추적 안 함으로 간주합니다. 기본적으로 Microsoft Edge에서는 Do Not Track 요청을 전송하지 않지만 사용자가 해당 기능을 설정하여 전송할 수 있습니다.

해당 정책을 사용하면 Do Not Track 요청이 추적 정보를 요청하는 웹 사이트로 항상 전송됩니다.

해당 정책을 사용하지 않도록 설정하면 요청이 전송되지 않습니다.

해당 정책을 구성하지 않으면 사용자는 해당 요청을 전송할지 여부를 선택할 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ConfigureDoNotTrack
  - GP 이름: Do Not Track 구성
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: ConfigureDoNotTrack
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ConfigureDoNotTrack
  - 예를 들어 값:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="configurefriendlyurlformat"></a>ConfigureFriendlyURLFormat

  #### <a name="configure-the-default-paste-format-of-urls-copied-from-microsoft-edge-and-determine-if-additional-formats-will-be-available-to-users"></a>Microsoft Edge에서 복사된 URL의 기본 붙여넣기 서식을 구성하고 추가 형식이 사용자에게 제공되는지 확인

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows (87 이상)
  - MacOS (88 이상)

  #### <a name="description"></a>설명

  FriendlyURLs를 사용하도록 설정하면 Microsoft Edge에서 URL의 추가 표현을 계산하여 클립보드에 놓습니다.

이 정책은 사용자가 외부 응용 프로그램에 붙여 넣을 때 또는 '다른 이름으로 붙여넣기' 상황에 맞는 메뉴 항목이 없이 Microsoft Edge 내에서 붙여 넣을 때의 서식을 구성합니다.

구성한 경우, 이 정책이 사용자를 대신하여 선택을 합니다. Edge://settings/shareCopyPaste의 옵션이 회색으로 표시되고 '다른 이름으로 붙여넣기' 상황에 맞는 메뉴의 옵션은 사용할 수 없게 됩니다.

* 구성되지 않음 = 사용자가 원하는 붙여 넣기 서식을 선택할 수 있습니다. 기본적으로 이 설정은 간편 URL 형식으로 설정됩니다. Microsoft Edge에서 '다른 이름으로 붙여넣기' 메뉴를 사용할 수 있습니다.

* 1 = 추가 서식이 클립보드에 저장되지 않습니다. Microsoft Edge에는 '다른 이름으로 붙여넣기' 상황에 맞는 메뉴 항목이 없으며, 붙여 넣을 수 있는 유일한 형식은 일반 텍스트 URL 형식이 있게 됩니다. 사실상 간편 URL 기능을 사용할 수 없게 됩니다.

* 3 = 사용자가 서식 있는 텍스트를 받아들이는 표면에 붙여 넣을 때마다 간편 URL을 가져옵니다. 서식 있는 표면이 아닌 경우에도 일반 URL을 계속 사용할 수 있습니다. Microsoft Edge에서 '다른 이름으로 붙여넣기' 메뉴가 없게 됩니다.

* 4 = (현재 사용되지 않음)

일부 붙여넣기 대상 및/또는 웹 사이트에서 더 풍부한 형식이 제대로 지원되지 않을 수 있습니다. 따라서 이 정책을 구성하는 경우, 일반 URL 옵션을 사용하는 것이 좋습니다.

정책 옵션 매핑:

* 일반 텍스트(1) = 페이지 제목과 같은 추가 정보가 없는 일반 URL 이 정책을 구성하는 경우 이 옵션을 선택하는 것이 좋습니다. 자세한 내용은 설명을 참조하십시오.

* TitledHyperlink(3) = 제목이 있는 하이퍼링크: 복사된 URL을 가리키는 하이퍼링크이지만 표시되는 텍스트는 대상 페이지의 제목입니다. 이는 간편 URL 형식입니다.

* WebPreview(4) = 출시 예정입니다. 설정된 경우, '일반 URL'과 동일하게 작동합니다.

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ConfigureFriendlyURLFormat
  - GP 이름: Microsoft Edge에서 복사된 URL의 기본 붙여넣기 서식을 구성하고 추가 형식이 사용자에게 제공되는지 확인
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: ConfigureFriendlyURLFormat
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000003
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ConfigureFriendlyURLFormat
  - 예를 들어 값:
``` xml
<integer>3</integer>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="configureonpremisesaccountautosignin"></a>ConfigureOnPremisesAccountAutoSignIn

  #### <a name="configure-automatic-sign-in-with-an-active-directory-domain-account-when-there-is-no-azure-ad-domain-account"></a>Azure AD 도메인 계정이 없는 경우 Active Directory 도메인 계정으로 자동 로그인 구성

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows (81 이상)

  #### <a name="description"></a>설명

  사용자의 컴퓨터가 도메인에 가입되어 있고 해당 환경이 하이브리드에 가입되어 있지 않은 경우 Active Directory 계정을 사용하여 자동으로 로그인할 수 있습니다. 대신 사용자가 해당 Azure Active Directory 계정을 사용하여 자동으로 로그인하도록 하려면 Azure AD에 가입(자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2118197](https://go.microsoft.com/fwlink/?linkid=2118197) 참조)하거나 사용자의 환경이 하이브리드에 가입(자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2118365](https://go.microsoft.com/fwlink/?linkid=2118365) 참조)되도록 합니다.

실행되는 첫 번째 프로필이 로그인되지 않거나 자동 로그인이 이전에 일어나지 않았다면 Microsoft Edge는 매 실행 시작 시 이 정책을 사용하여 로그인을 시도합니다.

[BrowserSignin](#browsersignin) 정책을 사용하지 않도록 구성한 경우 해당 정책은 아무 영향을 주지 않습니다.

해당 정책을 사용하도록 설정하고 'SignInAndMakeDomainAccountNonRemovable'로 설정하면 Microsoft Edge는 해당 Active Directory 계정을 사용하여 도메인에 가입된 컴퓨터에 있는 사용자에게 자동으로 로그인합니다.

해당 정책을 ‘사용 안 함’으로 설정하거나 해당 정책을 설정하지 않으면 Microsoft Edge는 Active Directory 계정을 사용하여 도메인에 가입된 컴퓨터에 있는 사용자에게 자동으로 로그인하지 않습니다.

Microsoft Edge 89 이후부터 동기화가 사용되지 않도록 설정되어 있는 기존 온-프레미스 프로필이 있고 컴퓨터가 이제 하이브리드 가입이 된 경우 예를 들어 Azure AD 계정이 있는 경우, 전체 Azure AD 동기화 기능을 얻을 수 있도록 온-프레미스 프로필을 Azure AD 프로필로 자동 업그레이드합니다.

정책 옵션 매핑:

* 사용 안 함 (0) = 사용 안 함

* SignInAndMakeDomainAccountNonRemovable (1) = 로그인 및 제거할 수 없는 도메인 계정 생성

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ConfigureOnPremisesAccountAutoSignIn
  - GP 이름: Azure AD 도메인 계정이 없는 경우 Active Directory 도메인 계정으로 자동 로그인 구성
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: ConfigureOnPremisesAccountAutoSignIn
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="configureonlinetexttospeech"></a>ConfigureOnlineTextToSpeech

  #### <a name="configure-online-text-to-speech"></a>온라인 텍스트 음성 변환 구성

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  브라우저가 Azure 인지 서비스의 부분인 온라인 텍스트를 음성으로 변환하는 기능의 음성 글꼴을 사용할 수 있는지 여부를 설정합니다. 해당 음성 글꼴은 사전 설치된 시스템의 음성 글꼴 보다 품질이 높습니다.

해당 정책을 사용하도록 설정하거나 구성하지 않으면 SpeechSynthesis API를 사용하는 웹 기반 응용 프로그램에서 온라인 텍스트 음성 기능의 음성 글꼴을 사용할 수 있습니다.

해당 정책을 사용하지 않도록 설정하면 음성 글꼴을 사용할 수 없습니다.

해당 기능에 대한 자세한 내용은 다음을 참조하세요. SpeechSynthesis API: [https://go.microsoft.com/fwlink/?linkid=2110038](https://go.microsoft.com/fwlink/?linkid=2110038) 인지 서비스: [https://go.microsoft.com/fwlink/?linkid=2110141](https://go.microsoft.com/fwlink/?linkid=2110141)

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ConfigureOnlineTextToSpeech
  - GP 이름: 온라인 텍스트 음성 변환 구성
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: ConfigureOnlineTextToSpeech
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ConfigureOnlineTextToSpeech
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="configureshare"></a>ConfigureShare

  #### <a name="configure-the-share-experience"></a>공유 환경 구성

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows (83 이상)

  #### <a name="description"></a>설명

  해당 정책을 'ShareAllowed' (기본값)로 설정하면 사용자는 Microsoft Edge의 설정 및 추가 메뉴에서 Windows 10 공유 환경에 액세스하여 시스템에서 다른 앱을 공유할 수 있습니다.

해당 정책을 'ShareDisallowed'로 설정하면 사용자는 Windows 10 공유 환경에 액세스할 수 없습니다. 도구 모음에 공유 단추가 있는 경우 해당 단추를 숨깁니다.

정책 옵션 매핑:

* ShareAllowed (0) = 공유 환경 사용 허용

* ShareDisallowed (1) = 공유 환경 사용 허용 안 함

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ConfigureShare
  - GP 이름: 공유 환경 구성
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: ConfigureShare
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="customhelplink"></a>CustomHelpLink

  #### <a name="specify-custom-help-link"></a>사용자 지정 도움말 링크 지정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (79 이상)

  #### <a name="description"></a>설명

  도움말 메뉴 또는 F1 키에 대한 링크를 지정합니다.

해당 정책을 사용하면 관리자는 도움말 메뉴 또는 F1 키에 대한 링크를 지정할 수 있습니다.

해당 정책을 사용하지 않도록 설정하거나 구성하지 않으면 도움말 메뉴 또는 F1 키에 대한 기본 링크가 사용됩니다.

이 정책은 Microsoft Active Directory 도메인에 가입된 윈도우즈 인스턴스, 장치 관리를 위해 등록된 윈도우즈 10 Pro 또는 Enterprise 인스턴스 또는 MDM을 통해 관리되거나 MCX를 통해 도메인에 가입된 MacOS 인스턴스에서만 사용할 수 있습니다..

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: CustomHelpLink
  - GP 이름: 사용자 지정 도움말 링크 지정
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: CustomHelpLink
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
"https://go.microsoft.com/fwlink/?linkid=2080734"
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: CustomHelpLink
  - 예를 들어 값:
``` xml
<string>https://go.microsoft.com/fwlink/?linkid=2080734</string>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="dnsinterceptionchecksenabled"></a>DNSInterceptionChecksEnabled

  #### <a name="dns-interception-checks-enabled"></a>DNS 차단 검사 사용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (80 이상)

  #### <a name="description"></a>설명

  해당 정책은 DNS 차단 검사를 사용하지 않도록 설정하는 데 사용할 수 있는 로컬 스위치를 구성합니다. 해당 검사에서는 브라우저가 알려지지 않은 호스트 이름을 리디렉션하는 프록시에 속하는지 여부를 검색하려고 합니다.

네트워크 구성이 알려진 엔터프라이즈 환경에서는 해당 검색이 필요하지 않을 수 있습니다. 해당 기능을 사용하지 않도록 설정하면 시작 시 추가 DNS 및 HTTP 트래픽과 각 DNS 구성 변경을 방지할 수 있습니다.

해당 정책을 사용하거나 설정하지 않으면 DNS 차단 검사가 수행됩니다.

해당 정책을 사용하지 않도록 설정하면 DNS 차단 검사가 수행되지 않습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: DNSInterceptionChecksEnabled
  - GP 이름: DNS 차단 검사 사용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: DNSInterceptionChecksEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: DNSInterceptionChecksEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="defaultbrowsersettingenabled"></a>DefaultBrowserSettingEnabled

  #### <a name="set-microsoft-edge-as-default-browser"></a>Microsoft Edge를 기본 브라우저로 설정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 7 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  이 정책을 True로 설정하면 Microsoft Edge는 항상 시작 시 기본 브라우저인지 확인하고 가능하면 자동으로 등록합니다.

이 정책을 False로 설정하면 Microsoft Edge는 이 정책이 기본값인지 확인하는 것이 중지되며 이 옵션에 대한 사용자 컨트롤을 해제합니다.

이 정책을 설정하지 않으면 Microsoft Edge에서 사용자가 기본값인지 여부를 제어하고, 기본값이 아닌 경우 사용자 알림을 표시할지 여부를 제어하도록 할 수 있습니다.

Windows 관리자용 참고: 해당 정책은 Windows 7을 실행하는 PC에서만 작동합니다. 이후 버전의 Windows에서는 Microsoft Edge를 https 및 http 프로토콜(선택적으로 ftp 프로토콜 및 .html, .htm, .pdf, .svg, .webp와 같은 파일 형식)에 대한 처리기로 설정하는 “기본 응용 프로그램 연결” 파일을 배포해야 합니다. 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2094932](https://go.microsoft.com/fwlink/?linkid=2094932)을 참조하세요.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: DefaultBrowserSettingEnabled
  - GP 이름: Microsoft Edge를 기본 브라우저로 설정
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: DefaultBrowserSettingEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: DefaultBrowserSettingEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="defaultsearchprovidercontextmenuaccessallowed"></a>DefaultSearchProviderContextMenuAccessAllowed

  #### <a name="allow-default-search-provider-context-menu-search-access"></a>기본 검색 공급자에 상황에 맞는 메뉴 검색 액세스 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS(85 이상)

  #### <a name="description"></a>설명

  상황에 맞는 메뉴에서 기본 검색 공급자를 사용할 수 있습니다.

이 정책을 사용하지 않으면 기본 검색 공급자 및 사이드바 검색에 의존하는 검색 상황에 맞는 메뉴 항목을 사용할 수 없습니다.

이 정책을 사용하도록 설정하였거나 설정하지 않은 경우에는 기본 검색 공급자 및 사이드바 검색에 대한 상황에 맞는 메뉴 항목을 사용할 수 있습니다.

정책 값은 [DefaultSearchProviderEnabled](#defaultsearchproviderenabled) 정책을 사용하는 경우에만 적용되며, 그렇지 않은 경우에는 해당되지 않습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: DefaultSearchProviderContextMenuAccessAllowed
  - GP 이름: 기본 검색 공급자에 상황에 맞는 메뉴 검색 액세스 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: DefaultSearchProviderContextMenuAccessAllowed
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: DefaultSearchProviderContextMenuAccessAllowed
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="defaultsensorssetting"></a>DefaultSensorsSetting

  #### <a name="default-sensors-setting"></a>기본 센서 설정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (86 이상)

  #### <a name="description"></a>설명

  웹 사이트에서 모션 및 광 센서와 같은 센서에 액세스하고 사용할 수 있는지 여부를 설정합니다. 웹 사이트에서 센서에 대한 액세스를 완전히 차단 또는 허용할 수 있습니다.

정책을 1로 설정하면 웹 사이트에서 센서에 액세스하여 사용할 수 있습니다. 정책을 2로 설정하면 센서에 대한 액세스가 거부됩니다.

[SensorsAllowedForUrls](#sensorsallowedforurls) 및 [SensorsBlockedForUrls](#sensorsblockedforurls) 정책을 사용하여 특정 URL 패턴에 대해 해당 정책을 재정의할 수 있습니다.

해당 정책을 구성하지 않으면 웹 사이트에서 센서에 액세스하여 사용할 수 있으며 사용자는 이 설정을 변경할 수 있습니다. 이는 [SensorsAllowedForUrls](#sensorsallowedforurls) 및 [SensorsBlockedForUrls](#sensorsblockedforurls)의 전역 기본값입니다.

정책 옵션 매핑:

* AllowSensors (1) = 사이트에서 센서에 액세스하도록 허용

* BlockSensors (2) = 모든 사이트에서 센서에 액세스를 허용하지 않음

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: DefaultSensorsSetting
  - GP 이름: 기본 센서 설정
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: DefaultSensorsSetting
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000002
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: DefaultSensorsSetting
  - 예를 들어 값:
``` xml
<integer>2</integer>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="defaultserialguardsetting"></a>DefaultSerialGuardSetting

  #### <a name="control-use-of-the-serial-api"></a>직렬 API 사용 제어

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (86 이상)

  #### <a name="description"></a>설명

  웹 사이트에서 직렬 포트에 액세스할 수 있는지를 설정합니다. 액세스를 완벽하게 차단하거나 웹 사이트에서 직렬 포트에 액세스할 때마다 사용자에게 요청할 수 있습니다.

정책을 3으로 설정하면 웹 사이트에서 직렬 포트에 대한 액세스를 요청할 수 있습니다. 정책을 2로 설정하면 직렬 포트에 대한 액세스가 거부됩니다.

[SerialAskForUrls](#serialaskforurls) 및 [SerialBlockedForUrls](#serialblockedforurls) 정책을 사용하여 특정 URL 패턴에 대해 해당 정책을 재정의할 수 있습니다.

이 정책을 구성하지 않으면 기본적으로 웹 사이트에서 사용자에게 직렬 포트에 액세스할 수 있는지 여부를 요청할 수 있으며 사용자는 해당 설정을 변경할 수 있습니다.

정책 옵션 매핑:

* BlockSerial (2) = 사이트에서 직렬 API를 통해 직렬 포트에 대한 액세스 요청을 허용하지 않음

* AskSerial (3) = 사이트에서 사용자에게 직렬 포트 액세스 권한 요청을 허용함

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: DefaultSerialGuardSetting
  - GP 이름: 직렬 API의 사용 제어
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: DefaultSerialGuardSetting
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000002
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: DefaultSerialGuardSetting
  - 예를 들어 값:
``` xml
<integer>2</integer>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="definepreferredlanguages"></a>DefinePreferredLanguages

  #### <a name="define-an-ordered-list-of-preferred-languages-that-websites-should-display-in-if-the-site-supports-the-language"></a>사이트에서 언어를 지원하는 경우 웹 사이트에서 표시할 기본 설정 언어 순서가 지정된 목록 정의

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 macOS(89 이상)

  #### <a name="description"></a>설명

  Microsoft Edge에서 웹 사이트로 보내는 언어 변형을 Accept-Language 요청 HTTP 헤더의 일부로 구성하고 사용자가 Microsoft Edge 설정에서 기본 설정 언어의 순서를 추가, 제거 또는 변경할 수 없게 합니다. Microsoft Edge에서 표시하거나 페이지를 번역하기 위해 제공하는 언어를 변경하려는 사용자는 이 정책에 구성된 언어만 선택할 수 있습니다.

이 정책을 사용하면 해당 사이트에 특정된 다른 로직이 표시 언어를 결정하지 않는 한, 사이트가 지원하는 목록의 첫 번째 언어로 사이트가 표시됩니다. 이 정책에 정의된 언어 변형은 [SpellcheckLanguage](#spellchecklanguage) 정책의 일부로 구성된 언어를 재정의합니다.

이 정책을 구성하지 않거나 사용하지 않을 경우 Microsoft Edge가 웹 사이트에 특정 사용자에 대한 기본 설정 언어를 Accept-Language request HTTP 헤더의 일부로 전송합니다.

유효한 언어 변형에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2148854](https://go.microsoft.com/fwlink/?linkid=2148854)을(를) 참조하세요.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: DefinePreferredLanguages
  - GP 이름: 사이트에서 언어를 지원하는 경우 웹 사이트에서 표시할 기본 설정 언어의 순서가 정해진 목록 정의
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: DefinePreferredLanguages
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
"en-US,fr,es"
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: DefinePreferredLanguages
  - 값 예시:
``` xml
<string>en-US,fr,es</string>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="delaynavigationsforinitialsitelistdownload"></a>DelayNavigationsForInitialSiteListDownload

  #### <a name="require-that-the-enterprise-mode-site-list-is-available-before-tab-navigation"></a>탭 탐색 전에 엔터프라이즈 모드 사이트 목록을 사용하도록 요청

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 84 이상

  #### <a name="description"></a>설명

  브라우저가 초기 엔터프라이즈 모드 사이트 목록을 다운로드할 때까지 Microsoft Edge 탭의 탐색 대기 여부를 지정할 수 있습니다. 이 설정은 브라우저 홈페이지가 Internet Explorer 모드로 로드되어야 하는 시나리오를 위한 것으로, IE 모드가 활성화된 후 브라우저를 먼저 실행하는 것이 중요합니다. 이 시나리오가 없는 경우 홈페이지를 로드하는 성능을 저하시킬 수 있기 때문에이 설정을 사용하지 않는 것이 좋습니다. 이 설정은 IE 모드가 활성화된 후 브라우저에서 처음 실행되는 경우와 같이 Microsoft Edge에 캐시된 엔터프라이즈 모드 사이트 목록이 없는 경우에만 적용됩니다.

해당 설정은 다음과 함께 작동됩니다. [InternetExplorerIntegrationLevel](#internetexplorerintegrationlevel) 정책은 'IEMode' 및 [InternetExplorerIntegrationSiteList](#internetexplorerintegrationsitelist) 정책으로 설정합니다. 여기서 목록에는 하나 이상의 항목이 있습니다.

이 정책의 시간 제한 동작은 [NavigationDelayForInitialSiteListDownloadTimeout](#navigationdelayforinitialsitelistdownloadtimeout) 정책을 사용하여 구성할 수 있습니다.

이 정책을 ‘모두’로 설정하면 Microsoft Edge에 캐시된 버전의 엔터프라이즈 모드 사이트 목록이 없는 경우 브라우저가 사이트 목록을 다운로드할 때까지 탭 탐색이 지연됩니다. 사이트 목록으로 Internet Explorer 모드에서 열리도록 구성한 사이트는 브라우저를 처음 탐색할 때에도 Internet Explorer 모드로 로드됩니다. Http:, https:, file:, ftp 외의 다른 체계가 있는 사이트와 같이 Internet Explorer에서 열리도록 구성할 수 없는 사이트는 Edge 모드에서 탐색이 지연되지 않으며 즉시 로드됩니다.

이 정책을 ‘없음’으로 설정하거나 구성하지 않으면 Microsoft Edge에 캐시된 버전의 엔터프라이즈 모드 사이트 목록이 없으면 탭이 즉시 탐색되며 브라우저가 엔터프라이즈 모드 사이트 목록을 다운로드할 때까지 기다리지 않습니다. 사이트 목록으로 Internet Explorer 모드에서 열도록 구성된 사이트는 브라우저가 엔터프라이즈 모드 사이트 목록 다운로드를 완료할 때까지 Microsoft Edge 모드에서 열립니다.

정책 옵션 매핑:

* 없음 (0) = 없음

* 모두 (1) = 모든 적합한 탐색

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: DelayNavigationsForInitialSiteListDownload
  - GP 이름: 탭 탐색 전에 엔터프라이즈 모드 사이트 목록을 사용하도록 요청
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: DelayNavigationsForInitialSiteListDownload
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="deletedataonmigration"></a>DeleteDataOnMigration

  #### <a name="delete-old-browser-data-on-migration"></a>마이그레이션 시 이전 브라우저 데이터 삭제

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows (83 이상)

  #### <a name="description"></a>설명

  해당 정책은 Microsoft Edge 버전 81 이상으로 마이그레이션한 후 Microsoft Edge 레거시에서 사용자 검색 데이터를 삭제할지 여부를 결정합니다.

해당 정책이 “사용”으로 설정된 경우 Microsoft Edge 버전 81 이상으로 마이그레이션한 후 Microsoft Edge 레거시에서 모든 검색 데이터를 삭제합니다. 기존 검색 데이터에도 영향을 주려면 Microsoft Edge 버전 81 이상으로 마이그레이션하기 전에 해당 정책을 설정해야 합니다.

해당 정책을 "사용 안 함"으로 설정하거나 정책을 구성하지 않은 경우 Microsoft Edge 버전 83 이상으로 마이그레이션한 후에 사용자 검색 데이터가 삭제되지 않습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: DeleteDataOnMigration
  - GP 이름: 마이그레이션 시 이전 브라우저 데이터 삭제
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: DeleteDataOnMigration
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="developertoolsavailability"></a>DeveloperToolsAvailability

  #### <a name="control-where-developer-tools-can-be-used"></a>개발자 도구를 사용할 수 있는 위치 제어

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  개발자 도구를 사용할 수 있는 위치를 제어합니다.

해당 정책을 'DeveloperToolsDisallowedForForceInstalledExtensions' (기본값)으로 설정하면 사용자는 일반적으로 개발자 도구 및 JavaScript 콘솔에 액세스할 수 있지만 엔터프라이즈 정책으로 설치한 확장의 컨텍스트에서는 액세스할 수 없습니다.

해당 정책을 'DeveloperToolsAllowed'로 설정하면 사용자는 엔터프라이즈 정책으로 설치한 확장을 포함하여 모든 컨텍스트에서 개발자 도구 및 JavaScript 콘솔에 액세스할 수 있습니다.

해당 정책을 'DeveloperToolsDisallowed'로 설정하면 사용자는 개발자 도구에 액세스할 수 없거나 웹 사이트 요소를 검사할 수 없습니다. 개발자 도구 또는 JavaScript 콘솔을 여는 바로 가기 키 및 메뉴 또는 상황에 맞는 메뉴 항목을 사용할 수 없습니다.

정책 옵션 매핑:

* DeveloperToolsDisallowedForForceInstalledExtensions (0) = 엔터프라이즈 정책으로 설치한 확장에서 개발자 도구를 차단하고 다른 컨텍스트 허용

* DeveloperToolsAllowed (1) = 개발자 도구 사용 허용

* DeveloperToolsDisallowed (2) = 개발자 도구 사용 허용 안 함

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: DeveloperToolsAvailability
  - GP 이름: 개발자 도구를 사용할 수 있는 위치 제어
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: DeveloperToolsAvailability
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000002
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: DeveloperToolsAvailability
  - 예를 들어 값:
``` xml
<integer>2</integer>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="diagnosticdata"></a>DiagnosticData

  #### <a name="send-required-and-optional-diagnostic-data-about-browser-usage"></a>브라우저를 사용하는 데 필요한 선택적 진단 데이터 보내기

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 7 및 MacOS(86 이상)

  #### <a name="description"></a>설명

  이 정책은 브라우저 사용에 대한 필수 및 선택적 진단 데이터를 Microsoft로 전송하는 것을 제어합니다.

필요한 진단 데이터가 수집되어 Microsoft Edge를 최신 상태로 유지하고 예상대로 작동합니다.

옵션 진단 데이터에는 브라우저 사용 방법, 방문하는 웹 사이트 및 제품 및 서비스 개선을 위해 Microsoft에 보내는 충돌 보고서에 대한 데이터가 포함됩니다.

이 정책은 Windows 10 장치에서 지원되지 않습니다. Windows 10에서 이 데이터 수집을 제어하려면 IT 관리자가 Windows 진단 데이터 그룹 정책을 사용해야 합니다. 이 정책은 Windows 버전에 따라 '원격 분석 허용' 또는 '진단 데이터 허용'으로 설정됩니다. Windows 10 진단 데이터 컬렉션에 대해 자세히 알아보세요.[https://go.microsoft.com/fwlink/?linkid=2099569](https://go.microsoft.com/fwlink/?linkid=2099569)

다음 설정 중 하나를 사용하여 이 정책을 구성합니다.

'끔(Off)'은 필수 진단 데이터 수집과 옵션 진단 데이터 수집을 끕니다. 이 옵션은 권장되지 않습니다.

' RequiredData '는 필수 진단 데이터를 보내므로 선택적 진단 데이터 수집은 해제합니다. Microsoft Edge는 Microsoft Edge의 보안을 최신 상태로 유지하고 예상대로 작동하는 데 필요한 진단 데이터를 전송합니다.

'옵션 데이터'는 브라우저 사용량, 방문한 웹 사이트, 제품 및 서비스 개선을 위해 Microsoft로 전송된 충돌 보고서를 포함하는 선택적 진단 데이터를 전송합니다.

Windows 7/macOS에서 이 정책은 Microsoft로 필수 및 선택적 데이터 전송을 제어합니다.

해당 정책을 구성하거나 사용 해제하지 않으면 Microsoft Edge는 사용자의 기본 설정의 기본값이 됩니다.

정책 옵션 매핑:

* Off (0) = 꺼짐(권장하지 않음)

* RequiredData (1) = 필수 데이터

* OptionalData (2) = 선택적 데이터

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: DiagnosticData
  - GP 이름: 브라우저를 사용하는 데 필요한 선택적 진단 데이터 보내기
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: DiagnosticData
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000002
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: DiagnosticData
  - 예를 들어 값:
``` xml
<integer>2</integer>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="directinvokeenabled"></a>DirectInvokeEnabled

  #### <a name="allow-users-to-open-files-using-the-directinvoke-protocol"></a>사용자가 DirectInvoke 프로토콜을 사용하여 파일을 열 수 있도록 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows (78 이상)

  #### <a name="description"></a>설명

  사용자가 DirectInvoke 프로토콜을 사용하여 파일을 열 수 있도록 허용합니다. DirectInvoke 프로토콜을 사용하면 웹 사이트에서 사용자의 컴퓨터나 장치에 있는 특정 파일 처리기를 사용하여 특정 URL에서 브라우저가 파일을 열도록 요청할 수 있습니다.

해당 정책을 사용하도록 설정하거나 구성하지 않으면 사용자는 DirectInvoke 프로토콜을 사용하여 파일을 열 수 있습니다.

해당 정책을 사용하지 않도록 설정하면 사용자는 DirectInvoke 프로토콜을 사용하여 파일을 열 수 없습니다. 대신 파일 시스템에 파일을 저장합니다.

참고: DirectInvoke를 사용하지 않도록 설정하면 특정 Microsoft SharePoint Online 기능이 예상대로 작동하지 않을 수 있습니다.

DirectInvoke에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2103872](https://go.microsoft.com/fwlink/?linkid=2103872) 및 [https://go.microsoft.com/fwlink/?linkid=2099871](https://go.microsoft.com/fwlink/?linkid=2099871)를 참조하세요.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: DirectInvokeEnabled
  - GP 이름: 사용자가 DirectInvoke 프로토콜을 사용하여 파일을 열 수 있도록 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: DirectInvokeEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="disable3dapis"></a>Disable3DAPIs

  #### <a name="disable-support-for-3d-graphics-apis"></a>3D 그래픽 API에 대한 지원 해제

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  웹 페이지에서 GPU(그래픽 처리 장치)에 액세스하지 못하도록 합니다. 특히 웹 페이지는 WebGL API에 액세스할 수 없으며 플러그 인은 Pepper 3D API를 사용할 수 없습니다.

해당 정책을 구성하지 않거나 사용하지 않도록 설정하면 웹 페이지에서 WebGL API를 사용할 수 있고 플러그 인에서 Pepper 3D API를 사용할 수 있습니다. 기본적으로 Microsoft Edge에서 해당 API를 사용하기 위해 명령줄 인수가 계속 전달될 수 있습니다.

[HardwareAccelerationModeEnabled](#hardwareaccelerationmodeenabled) 정책을 False로 설정하는 경우 'Disable3DAPIs' 정책 설정은 무시됩니다. 'Disable3DAPIs' 정책을 True로 설정하는 것과 동일합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: Disable3DAPIs
  - GP 이름: 3D 그래픽 API에 대한 지원 해제
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: Disable3DAPIs
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: Disable3DAPIs
  - 예를 들어 값:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="disablescreenshots"></a>DisableScreenshots

  #### <a name="disable-taking-screenshots"></a>스크린샷 기능 해제

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  사용자가 브라우저 페이지의 스크린샷을 사용할 수 있는지 여부를 제어합니다.

해당 기능을 사용하는 경우 사용자는 바로 가기 키 또는 확장 API를 사용하여 스크린샷를 사용할 수 없습니다.

해당 정책을 사용하지 않거나 구성하지 않으면 사용자는 스크린샷을 사용할 수 있습니다.

해당 정책은 브라우저 자체 내에서 사용하는 스크린샷을 제어한다는 점에에 유의하세요. 해당 정책을 사용하는 경우에도 사용자가 브라우저 외부의 일부 메서드를 사용하여(운영 체제 기능이나 다른 응용 프로그램을 사용하는 등) 스크린샷을 계속 사용할 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: DisableScreenshots
  - GP 이름: 스크린샷 기능 해제
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: DisableScreenshots
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: DisableScreenshots
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="diskcachedir"></a>DiskCacheDir

  #### <a name="set-disk-cache-directory"></a>디스크 캐시 디렉터리 설정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  캐시된 파일을 저장하는 데 사용할 디렉터리를 구성합니다.

해당 정책을 사용하면 사용자가 '--disk-cache-dir' 플래그를 지정했는지 여부에 관계 없이 Microsoft Edge는 제공된 디렉터리를 사용합니다. 데이터 손실 또는 기타 예기치 않은 오류가 발생하지 않도록 하려면 Microsoft Edge에서 해당 콘텐츠를 관리하기 때문에 볼륨의 루트 디렉터리나 다른 목적에 사용되는 디렉터리로 해당 정책을 구성하지 마세요.

디렉터리 및 경로 지정 시 사용할 수 있는 변수의 목록은 [https://go.microsoft.com/fwlink/?linkid=2095041](https://go.microsoft.com/fwlink/?linkid=2095041)을 참조하세요.

해당 정책을 구성하지 않으면 기본 캐시 디렉터리가 사용되고 사용자는 '--disk-cache-dir' 명령줄 플래그로 해당 기본값을 재정의할 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 문자열

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: DiskCacheDir
  - GP 이름: 디스크 캐시 디렉터리 설정
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: DiskCacheDir
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
"${user_home}/Edge_cache"
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: DiskCacheDir
  - 예를 들어 값:
``` xml
<string>${user_home}/Edge_cache</string>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="diskcachesize"></a>DiskCacheSize

  #### <a name="set-disk-cache-size-in-bytes"></a>디스크 캐시 크기를 바이트 단위로 설정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  디스크에 파일을 저장하는 데 사용되는 캐시 크기(바이트)를 구성합니다.

해당 정책을 사용하면 사용자가 '--disk-cache-size' 플래그를 지정했는지 여부에 관계 없이 Microsoft Edge는 제공된 캐시 크기를 사용합니다. 해당 정책에 지정된 값은 하드 경계가 아니라 캐싱 시스템에 대한 제안입니다. 일부 메가바이트 아래에 있는 값은 너무 작아서 적절한 최소값으로 반올림됩니다.

해당 정책의 값을 0으로 설정하면 기본 캐시 크기가 사용되고 사용자는 변경할 수 없습니다.

해당 정책을 구성하지 않으면 기본 크기가 사용되지만 사용자는 '--disk-cache-size' 플래그로 크기를 재정의할 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: DiskCacheSize
  - GP 이름: 디스크 캐시 크기를 바이트 단위로 설정
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: DiskCacheSize
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x06400000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: DiskCacheSize
  - 예를 들어 값:
``` xml
<integer>104857600</integer>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="dnsoverhttpsmode"></a>DnsOverHttpsMode

  #### <a name="control-the-mode-of-dns-over-https"></a>DoH(DNS over HTTPS) 모드 제어

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (83 이상)

  #### <a name="description"></a>설명

  DoH(DNS over HTTPS) 확인 프로그램 모드 제어 해당 정책은 각 쿼리에 대해 기본 모드만 설정한다는 점에 유의하세요. 해당 모드는 DoH(DNS over HTTPS) 서버 호스트 이름을 확인하는 요청과 같은 특별한 유형의 쿼리를 재정의할 수 있습니다.

"해제" 모드는 DoH(DNS over HTTPS)를 사용하지 않도록 설정합니다.

"자동" 모드는 DoH(DNS over HTTPS) 서버를 사용할 수 있는 경우 먼저 DoH(DNS over HTTPS) 쿼리를 전송하고 오류가 발생하는 경우 비보안 쿼리를 전송하는 것으로 대체할 수 있습니다.

"보안" 모드는 DoH(DNS over HTTPS) 쿼리만 전송하며 오류가 발생하는 경우 확인에 실패합니다.

해당 정책을 구성하지 않으면 브라우저에서 사용자가 구성한 시스템 확인 프로그램과 연결된 확인 프로그램에 DoH(DNS over HTTPS) 요청을 전송할 수 있습니다.

정책 옵션 매핑:

* 끄기 (off) = DoH(DNS over-HTTPS) 사용 안 함

* 자동 (automatic) = 비보안 대체를 사용하여 DoH(DNS over-HTTPS) 사용

* 보안 (secure) = 비보안 대체를 사용하지 않고 DoH(DNS over-HTTPS) 사용

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: DnsOverHttpsMode
  - GP 이름: DoH(DNS over HTTPS) 모드 제어
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: DnsOverHttpsMode
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
"off"
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: DnsOverHttpsMode
  - 예를 들어 값:
``` xml
<string>off</string>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="dnsoverhttpstemplates"></a>DnsOverHttpsTemplates

  #### <a name="specify-uri-template-of-desired-dns-over-https-resolver"></a>원하는 DoH(DNS over HTTPS) 확인자의 URI 서식 파일 지정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (83 이상)

  #### <a name="description"></a>설명

  필요한 DoH(DNS over HTTPS) 확인 프로그램의 URI 서식 파일을 지정합니다. 여러 DNS over-HTTPS 확인 프로그램을 지정하려면 해당 URI 서식 파일을 공백으로 구분합니다.

[DnsOverHttpsMode](#dnsoverhttpsmode)를 "보안"으로 설정한 경우 해당 정책을 설정해야 하며 비워 둘 수 없습니다.

[DnsOverHttpsMode](#dnsoverhttpsmode)를 "자동"으로 설정한 경우 해당 정책이 설정되고 지정된 URI 서식 파일이 사용됩니다. 해당 정책을 설정하지 않은 경우 하드 코드된 매핑은 사용자의 현재 DNS 확인 프로그램을 동일한 공급자가 운영하는 DoH 확인 프로그램으로 업그레이드하는 데 사용됩니다.

URI 서식 파일에 DNS 변수가 포함된 경우 확인 프로그램에 대한 요청은 GET을 사용합니다. 그렇지 않으면 요청은 POST를 사용합니다.

서식이 올바르지 않은 서식 파일은 무시됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: DnsOverHttpsTemplates
  - GP 이름: 필요한 DoH(DNS over HTTPS) 확인자의 URI 서식 파일 지정
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: DnsOverHttpsTemplates
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
"https://dns.example.net/dns-query{?dns}"
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: DnsOverHttpsTemplates
  - 예를 들어 값:
``` xml
<string>https://dns.example.net/dns-query{?dns}</string>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="downloaddirectory"></a>DownloadDirectory

  #### <a name="set-download-directory"></a>다운로드 디렉터리 설정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  파일 다운로드 시 사용할 디렉터리를 구성합니다.

해당 정책을 사용하면 Microsoft Edge는 사용자가 디렉터리를 지정했거나 다운로드할 때마다 다운로드 위치를 선택하라는 메시지가 나타나도록 선택했는지 여부와 관계 없이 제공된 디렉터리를 사용합니다. 사용할 수 있는 변수의 목록은 [https://go.microsoft.com/fwlink/?linkid=2095041](https://go.microsoft.com/fwlink/?linkid=2095041)을 참조하세요.

해당 정책을 사용하지 않도록 설정하거나 구성하지 않으면 기본 다운로드 디렉터리가 사용되므로 사용자는 이를 변경할 수 있습니다.

잘못된 경로를 설정하는 경우 Microsoft Edge는 기본적으로 사용자의 기본 다운로드 디렉터리를 사용합니다.

경로로 지정된 폴더가 없는 경우 다운로드는 사용자에게 다운로드를 저장할 위치를 묻는 메시지가 나타나도록 트리거합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: DownloadDirectory
  - GP 이름: 다운로드 디렉터리 설정
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: DownloadDirectory
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
"\n      Linux-based OSes (including Mac): /home/${user_name}/Downloads\n      Windows: C:\\Users\\${user_name}\\Downloads"
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: DownloadDirectory
  - 예를 들어 값:
``` xml
<string>
      Linux-based OSes (including Mac): /home/${user_name}/Downloads
      Windows: C:\Users\${user_name}\Downloads</string>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="downloadrestrictions"></a>DownloadRestrictions

  #### <a name="allow-download-restrictions"></a>다운로드 제한 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  사용자가 보안 결정을 재정의할 수 있도록 허용하지 않고 Microsoft Edge에서 완전히 차단하는 다운로드 유형을 구성합니다.

'BlockDangerousDownloads'를 설정하여 Microsoft Defender SmartScreen 경고를 실행하는 경우를 제외하고 모든 다운로드를 허용합니다.

'BlockPotentiallyDangerousDownloads'를 설정하여 잠재적으로 위험하거나 원치 않는 다운로드에 대해 Microsoft Defender SmartScreen 경고를 실행하는 경우를 제외하고 모든 다운로드를 허용합니다.

'BlockAllDownloads'를 설정하여 모든 다운로드를 차단합니다.

해당 정책을 구성하지 않거나 'DefaultDownloadSecurity' 옵션을 설정하는 경우 다운로드는 Microsoft Defender SmartScreen 분석 결과를 기반으로 하는 일반적인 보안 제한을 통해 진행됩니다.

해당 제한은 웹 페이지 콘텐츠의 다운로드 뿐만 아니라 '다운로드 링크...' 상황에 맞는 메뉴 옵션에 적용됩니다. 해당 제한은 현재 표시되는 페이지를 저장하거나 다운로드하는 경우에만 적용됩니다. 인쇄 옵션의 PDF로 저장 옵션에는 적용되지 않습니다.

Microsoft Defender SmartScreen에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2094934](https://go.microsoft.com/fwlink/?linkid=2094934)을 참조하세요.

정책 옵션 매핑:

* DefaultDownloadSecurity (0) = 특별한 제한 없음

* BlockDangerousDownloads (1) = 위험한 다운로드 차단

* BlockPotentiallyDangerousDownloads (2) = 잠재적으로 위험하거나 사용자 동의 없는 다운로드 차단

* BlockAllDownloads (3) = 모든 다운로드 차단

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: DownloadRestrictions
  - GP 이름: 다운로드 제한 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: DownloadRestrictions
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000002
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: DownloadRestrictions
  - 예를 들어 값:
``` xml
<integer>2</integer>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="edgecollectionsenabled"></a>EdgeCollectionsEnabled

  #### <a name="enable-the-collections-feature"></a>컬렉션 기능 사용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (78 이상)

  #### <a name="description"></a>설명

  사용자가 모음 기능에 액세스하도록 허용하여 Office 통합으로 콘텐츠를 더 효율적으로 수집, 구성, 공유 및 내보낼 수 있습니다.

해당 정책을 사용하도록 설정하거나 구성하지 않으면 사용자는 Microsoft Edge에서 모음 기능에 액세스하고 사용할 수 있습니다.

해당 정책을 사용하지 않도록 설정하면 사용자는 Microsoft Edge에서 모음에 액세스하고 사용할 수 없습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: EdgeCollectionsEnabled
  - GP 이름: 컬렉션 기능 사용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: EdgeCollectionsEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: EdgeCollectionsEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="edgeshoppingassistantenabled"></a>EdgeShoppingAssistantEnabled

  #### <a name="shopping-in-microsoft-edge-enabled"></a>Microsoft Edge에서 쇼핑 사용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - On Windows and macOS since 87 or later

  #### <a name="description"></a>설명

  이 정책을 사용해서 사용자는 쇼핑 중인 제품 가격을 비교하거나 사용 중인 웹사이트의 쿠폰을 받거나 체크 아웃 시 쿠폰을 자동 적용할 수 있습니다.

해당 정책을 사용하도록 설정하거나 구성하지 않을 경우 소매 도메인에 가격 비교, 쿠폰, 리베이트와 같은 쇼핑 기능이 자동으로 적용됩니다. 현재 소매업체의 쿠폰과 다른 소매업체의 가격을 서버에서 가져옵니다.

이 정책 쇼핑 기능을 사용하지 않도록 설정하면 소매 도메인에 대한 가격 비교와 쿠폰, 리베이트가 자동으로 검색되지 않습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: EdgeShoppingAssistantEnabled
  - GP 이름: Microsoft Edge에서 쇼핑 사용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: EdgeShoppingAssistantEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: EdgeShoppingAssistantEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="editfavoritesenabled"></a>EditFavoritesEnabled

  #### <a name="allows-users-to-edit-favorites"></a>사용자가 즐겨찾기를 편집할 수 있도록 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  해당 정책을 사용하면 사용자는 즐겨찾기를 추가, 제거 및 수정할 수 있습니다. 해당 정책을 구성하지 않으면 해당 작업은 기본 동작이 됩니다.

해당 정책을 사용하지 않도록 설정하면 사용자는 즐겨찾기를 추가, 제거 또는 수정할 수 없습니다. 사용자는 기존 즐겨찾기를 계속 사용할 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: EditFavoritesEnabled
  - GP 이름: 사용자가 즐겨찾기를 편집할 수 있도록 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: EditFavoritesEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: EditFavoritesEnabled
  - 예를 들어 값:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="enabledeprecatedwebplatformfeatures"></a>EnableDeprecatedWebPlatformFeatures

  #### <a name="re-enable-deprecated-web-platform-features-for-a-limited-time-obsolete"></a>제한된 시간 동안 사용되지 않는 웹 플랫폼 기능 다시 사용(obsolete)

  
  >OBSOLETE: 이 정책은 더 이상 사용되지 않으며 Microsoft Edge 86 이후에는 작동하지 않습니다.
  #### <a name="supported-versions"></a>지원 버전:

  - On Windows and macOS since 77, until 86

  #### <a name="description"></a>설명

  이 정책은 개인 웹 플랫폼 기능 deprecations를 관리 하는 데 사용 되기 때문에 더 이상 사용 되지 않습니다.

사용되지 않는 웹 플랫폼 기능 목록을 임시로 다시 사용할 수 있도록 지정합니다.

해당 정책을 사용하면 제한된 시간 동안 사용되지 않는 웹 플랫폼 기능을 다시 사용할 수 있습니다. 기능은 문자열 태그로 식별됩니다.

해당 정책을 구성하지 않고 목록이 비어 있거나 기능이 지원되는 문자열 태그 중 하나와 일치하지 않는 경우 사용되지 않는 모든 웹 플랫폼 기능은 계속 사용할 수 없습니다.

위의 플랫폼에서 정책 자체가 지원되는 동안 사용할 수 있는 기능은 모든 플랫폼에서 사용하지 못할 수 있습니다. 사용되지 않는 모든 웹 플랫폼 기능을 다시 사용할 수 없습니다. 아래에 명시적으로 나열된 기능만 제한된 기간 동안에만 다시 사용할 수 있으며 기능별로 다릅니다. https://bit.ly/blinkintents에서 웹 플랫폼 기능 변경 목적을 검토할 수 있습니다.

문자열 태그의 일반적인 형식은 [DeprecatedFeatureName] _EffectiveUntil[yyyymmdd]입니다.

정책 옵션 매핑:

* ExampleDeprecatedFeature (ExampleDeprecatedFeature_EffectiveUntil20080902) = 2008년 9월 2일까지 ExampleDeprecatedFeature API 사용 가능

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: EnableDeprecatedWebPlatformFeatures
  - GP 이름: 제한된 시간 동안 사용되지 않는 웹 플랫폼 기능 다시 사용(obsolete)
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - Path (필수): SOFTWARE\정책\Microsoft\Edge\EnableDeprecatedWebPlatformFeatures
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\EnableDeprecatedWebPlatformFeatures\1 = "ExampleDeprecatedFeature_EffectiveUntil20080902"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: EnableDeprecatedWebPlatformFeatures
  - 예를 들어 값:
``` xml
<array>
  <string>ExampleDeprecatedFeature_EffectiveUntil20080902</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="enabledomainactionsdownload"></a>EnableDomainActionsDownload

  #### <a name="enable-domain-actions-download-from-microsoft-obsolete"></a>Microsoft에서 도메인 작업 다운로드 사용(사용되지 않음)

  
  >사용되지 않음: 이 정책은 더 이상 사용되지 않으며 Microsoft Edge 84 이후에는 작동하지 않습니다.
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상, 84까지)

  #### <a name="description"></a>설명

  충돌하는 상태를 방지하기 위해 이 정책이 작동하지 않습니다. 해당 정책은 도메인 작업 목록의 다운로드를 사용하거나 사용하지 않도록 설정하는 데 사용되었지만 항상 필요한 상태를 만들지는 못했습니다. 다운로드를 처리하는 실험 및 구성 서비스에는 서비스에서 다운로드할 내용을 구성하는 고유한 정책이 있습니다. 대신 [ExperimentationAndConfigurationServiceControl](#experimentationandconfigurationservicecontrol) 정책을 사용하세요.

Microsoft Edge에서 도메인 작업은 브라우저가 웹에서 제대로 작동하는 데 도움이 되는 일련의 호환성 기능을 나타냅니다.

Microsoft는 호환성을 위해 특정 도메인에 대해 수행할 작업 목록을 유지합니다. 예를 들어 Microsoft Edge에서 새 사용자 에이전트 문자열로 인해 웹 사이트가 손상되면 브라우저는 웹 사이트의 사용자 에이전트 문자열을 재정의할 수 있습니다. 각 해당 작업은 일시적이며 Microsoft에서는 사이트 소유자와 관련된 문제를 해결하려고 시도합니다.

브라우저 시작 후 주기적으로 수행되면 브라우저에서 수행할 호환성 작업의 최신 목록을 포함하는 실험 및 구성 서비스에 연결합니다. 해당 목록은 최초 검색된 이후 로컬에 저장되므로 이후의 요청은 서버 복사가 변경된 경우에만 목록을 업데이트합니다.

해당 정책을 사용하면 도메인 작업의 목록이 실험 및 구성 서비스에서 계속 다운로드됩니다.

해당 정책을 사용하지 않으면 도메인 작업의 목록이 실험 및 구성 서비스에서 더 이상 다운로드되지 않습니다.

해당 정책을 구성하지 않은면 도메인 작업의 목록이 실험 및 구성 서비스에서 계속 다운로드됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: EnableDomainActionsDownload
  - GP 이름: Microsoft에서 도메인 작업 다운로드 사용(사용되지 않음)
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: EnableDomainActionsDownload
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: EnableDomainActionsDownload
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="enableonlinerevocationchecks"></a>EnableOnlineRevocationChecks

  #### <a name="enable-online-ocspcrl-checks"></a>온라인 OCSP/CRL 검사 사용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  온라인 해지 검사는 상당한 보안 이점을 제공하지 못하며 기본적으로 사용하지 않도록 설정되어 있습니다.

해당 정책을 사용하면 Microsoft Edge가 소프트 오류, 온라인 OCSP/CRL 검사를 수행합니다. "소프트 오류"는 해지 서버에 연결할 수 없는 경우 인증서가 유효한 것으로 간주되었음을 의미합니다.

해당 정책을 사용하지 않도록 설정하거나 구성하지 않으면 Microsoft Edge에서 온라인 해지 검사를 수행하지 않습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: EnableOnlineRevocationChecks
  - GP 이름: 온라인 OCSP/CRL 검사 사용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: EnableOnlineRevocationChecks
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: EnableOnlineRevocationChecks
  - 예를 들어 값:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="enablesha1forlocalanchors"></a>EnableSha1ForLocalAnchors

  #### <a name="allow-certificates-signed-using-sha-1-when-issued-by-local-trust-anchors-deprecated"></a>로컬 트러스트 앵커에서 발급한 경우 SHA-1을 사용하여 서명한 인증서 허용(사용되지 않음)

  >DEPRECATED: 해당 정책은 사용되지 않습니다. 현재 지원되고 있지만 이후 릴리스에서는 더 이상 사용되지 않을 예정입니다.
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS(85 이상)

  #### <a name="description"></a>설명

  이 설정을 사용하면 Microsoft Edge는 인증서 체인이 로컬에 설치된 루트 인증서에 연결되고 그 외에는 유효하지 않은 경우 SHA-1로 서명되어 보안된 연결을 사용할 수 있습니다.

이 정책은 SHA-1 서명을 허용하는 OS(운영 체제) 인증서 확인 스택에 따라 다릅니다. OS 업데이트에서 SHA-1 인증서의 OS 처리를 변경하는 경우 이 정책의 효력이 더 이상 없을 수 있습니다.  또한 이 정책은 엔터프라이즈에서 SHA-1을 제거하는 데 시간을 벌어주는 임시 해결 방법으로 고안되었습니다. 이 정책은 2021년 중반에 릴리스될 Microsoft Edge 92 릴리스에서 제거될 예정입니다.

이 정책을 설정하지 않거나 False로 설정하거나 SHA-1 인증서 체인을 신뢰할 수 있는 인증서 루트로 설정하지 않는 경우 Microsoft Edge는 SHA-1로 서명된 인증서를 허용하지 않습니다.

이 정책은 Microsoft Active Directory 도메인에 가입된 윈도우즈 인스턴스, 장치 관리를 위해 등록된 윈도우즈 10 Pro 또는 Enterprise 인스턴스 또는 MDM을 통해 관리되거나 MCX를 통해 도메인에 가입된 MacOS 인스턴스에서만 사용할 수 있습니다..

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: EnableSha1ForLocalAnchors
  - GP 이름: 로컬 트러스트 앵커에서 발급한 경우 SHA-1을 사용하여 서명한 인증서 허용(사용되지 않음)
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: EnableSha1ForLocalAnchors
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: EnableSha1ForLocalAnchors
  - 예를 들어 값:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="enterprisehardwareplatformapienabled"></a>EnterpriseHardwarePlatformAPIEnabled

  #### <a name="allow-managed-extensions-to-use-the-enterprise-hardware-platform-api"></a>Managed Extensions에서 엔터프라이즈 하드웨어 플랫폼 API를 사용할 수 있도록 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (78 이상)

  #### <a name="description"></a>설명

  해당 정책을 사용하도록 설정하면 엔터프라이즈 정책에서 설치한 확장은 엔터프라이즈 하드웨어 플랫폼 API를 사용할 수 있습니다.
해당 정책을 사용하지 않거나 설정하지 않으면 엔터프라이즈 하드웨어 플랫폼 API를 사용할 수 있는 확장은 없습니다.
해당 정책은 구성 요소 확장에도 적용됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: EnterpriseHardwarePlatformAPIEnabled
  - GP 이름: 관리 확장에서 엔터프라이즈 하드웨어 플랫폼 API를 사용할 수 있도록 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: EnterpriseHardwarePlatformAPIEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: EnterpriseHardwarePlatformAPIEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="enterprisemodesitelistmanagerallowed"></a>EnterpriseModeSiteListManagerAllowed

  #### <a name="allow-access-to-the-enterprise-mode-site-list-manager-tool"></a>엔터프라이즈 모드 사이트 목록 관리자 도구에 대한 액세스 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 86 이상

  #### <a name="description"></a>설명

  사용자가 엔터프라이즈 모드 사이트 목록 관리자를 사용할 수 있는지 설정할 수 있습니다.

이 정책을 사용하면 사용자가 edge://compat 페이지에서 엔터프라이즈 모드 사이트 관리자 탐색 단추를 볼 수 있습니다. 그런 다음 도구를 탐색하여 사용합니다.

이 정책을 사용하지 않거나 구성하지 않는 경우 사용자에게 엔터프라이즈 모드 사이트 목록 관리자 탐색 단추가 표시되지 않으며 사용자는 이를 사용할 수 없습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: EnterpriseModeSiteListManagerAllowed
  - GP 이름: 엔터프라이즈 모드 사이트 목록 관리자 도구에 대한 액세스 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: EnterpriseModeSiteListManagerAllowed
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="exemptdomainfiletypepairsfromfiletypedownloadwarnings"></a>ExemptDomainFileTypePairsFromFileTypeDownloadWarnings

  #### <a name="disable-download-file-type-extension-based-warnings-for-specified-file-types-on-domains"></a>도메인에서 지정된 파일 형식에 대한 다운로드 파일 형식 확장자 기반 경고 비활성화

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS(85 이상)

  #### <a name="description"></a>설명

  이 정책을 사용하면 파일 형식 확장명 기반 다운로드 경고에서 제외될 해당 도메인 목록으로 파일 형식 확장명 사전을 만들 수 있습니다. 이렇게 하면 엔터프라이즈 관리자는 나열된 도메인과 연결된 파일에 대한 파일 형식 확장자 기반 다운로드 경고를 차단할 수 있습니다. 예를 들어, "jnlp" 확장자가 "website1.com" 과 연결된 경우, 사용자는 "website1.com" 에서 "jnlp" 파일을 다운로드할 때 경고가 표시되지 않지만 "website2.com" 에서 "jnlp" 파일을 다운로드할 때 다운로드 경고가 표시됩니다.

이 정책에서 식별된 도메인에 대해 지정된 파일 형식 확장자가 있는 파일은 여전히 혼합 콘텐츠 다운로드 경고 및 Microsoft Defender SmartScreen 경고와 같은 비파일 형식 확장자 기반 보안 경고가 적용됩니다.

이 정책을 사용하지 않거나 구성하지 않으면 확장 프로그램 기반 다운로드 경고를 트리거하는 파일 형식이 사용자에게 경고를 표시합니다.

이 정책을 활성화한 경우:

* [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)에 따라 URL 패턴의 형식을 지정해야 합니다.
* 입력한 파일 형식 확장자는 소문자 ASCII여야 합니다. 파일 형식 확장자를 나열할 때 줄 간격 구분 기호를 포함해서는 안 되므로 ".jnlp" 대신 "jnlp" 를 나열해야 합니다.

예제:

다음 예제 값은 *.contoso.com 도메인에 대한 swf, exe 및 jnlp 확장자에 대한 파일 형식 확장자 기반 다운로드 경고를 방지합니다. 사용자에게 exe 및 jnlp 파일에 대한 다른 도메인의 파일 형식 확장자 기반 다운로드 경고가 표시되지만 swf 파일에는 표시되지 않습니다.

[ { "file_extension": "jnlp", "domains": ["contoso.com"] }, { "file_extension": "exe", "domains": ["contoso.com"] }, { "file_extension": "swf", "domains": ["*"] } ]

앞의 예는 모든 도메인에 대해 "swf" 파일에 대한 파일 형식 확장자 기반 다운로드 경고를 비표시하는 것을 보여주지만 보안 문제로 인해 위험한 파일 형식 확장자에 대한 모든 도메인에 대해 이러한 경고를 비표시하는 것은 권장되지 않습니다. 이 예제에서는 단지 이 작업을 수행하는 기능을 보여줍니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ExemptDomainFileTypePairsFromFileTypeDownloadWarnings
  - GP 이름: 도메인에서 지정된 파일 형식에 대한 다운로드 파일 형식 확장자 기반 경고 비활성화
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로(필수): SOFTWARE\Policies\Microsoft\Edge\ExemptDomainFileTypePairsFromFileTypeDownloadWarnings
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\ExemptDomainFileTypePairsFromFileTypeDownloadWarnings\1 = {"domains": ["https://contoso.com", "contoso2.com"], "file_extension": "jnlp"}
SOFTWARE\Policies\Microsoft\Edge\ExemptDomainFileTypePairsFromFileTypeDownloadWarnings\2 = {"domains": ["*"], "file_extension": "swf"}

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ExemptDomainFileTypePairsFromFileTypeDownloadWarnings
  - 예를 들어 값:
``` xml
<array>
  <string>{'domains': ['https://contoso.com', 'contoso2.com'], 'file_extension': 'jnlp'}</string>
  <string>{'domains': ['*'], 'file_extension': 'swf'}</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="experimentationandconfigurationservicecontrol"></a>ExperimentationAndConfigurationServiceControl

  #### <a name="control-communication-with-the-experimentation-and-configuration-service"></a>실험 및 구성 서비스와의 통신 제어

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  Microsoft Edge에서 실험 및 구성 서비스는 실험 및 구성 페이로드를 배포하는 데 사용됩니다.

실험 페이로드는 Microsoft에서 테스트 및 피드백을 위해 사용하는 개발 기능 중 초기의 목록으로 구성됩니다.

구성 페이로드는 Microsoft가 사용자 환경을 최적화하기 위해 Microsoft Edge를 배포하려고 하는 설정 목록으로 구성됩니다. 예를 들어 구성 페이로드는 Microsoft Edge가 실험 및 구성 서비스에 대한 요청을 전송하는 빈도를 지정하여 최신 페이로드를 검색할 수 있습니다.

뿐만 아니라 구성 페이로드에는 호환성을 위해 특정 도메인을 실행할 수 있는 작업 목록이 포함될 수도 있습니다. 예를 들어 Microsoft Edge에서 새 사용자 에이전트 문자열로 인해 웹 사이트가 손상되면 브라우저는 웹 사이트의 사용자 에이전트 문자열을 재정의할 수 있습니다. 각 해당 작업은 일시적이며 Microsoft에서는 사이트 소유자와 관련된 문제를 해결하려고 시도합니다.

해당 정책을 'FullMode' 모드로 설정하면 전체 페이로드는 실험 및 구성 서비스에서 다운로드됩니다. 여기에는 실험 및 구성 페이로드가 모두 포함됩니다.

해당 정책을 'ConfigurationsOnlyMode' 모드로 설정하면 구성 페이로드만 전달됩니다.

해당 정책을 'RestrictedMode'로 설정하면 실험 및 구성 서비스와의 통신이 완전히 중지됩니다.

해당 정책을 구성하지 않은 경우 안정된 베타 채널의 관리 장치에서 'ConfigurationsOnlyMode’와 동일하게 작동합니다.

해당 정책을 구성하지 않은 경우 관리되지 않은 장치에서 'FullMode'와 동일하게 작동합니다.

정책 옵션 매핑:

* FullMode (2) = 구성 및 실험 검색

* ConfigurationsOnlyMode (1) = 구성만 검색

* RestrictedMode (0) = 실험 및 구성 서비스와 통신 사용 안 함

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ExperimentationAndConfigurationServiceControl
  - GP 이름: 실험 및 구성 서비스와의 통신 제어
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: ExperimentationAndConfigurationServiceControl
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000002
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ExperimentationAndConfigurationServiceControl
  - 예를 들어 값:
``` xml
<integer>2</integer>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="externalprotocoldialogshowalwaysopencheckbox"></a>ExternalProtocolDialogShowAlwaysOpenCheckbox

  #### <a name="show-an-always-open-checkbox-in-external-protocol-dialog"></a>외부 프로토콜 대화 상자에서 "항상 열기" 확인란 표시

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (79 이상)

  #### <a name="description"></a>설명

  해당 정책은 외부 프로토콜 시작 확인 프롬프트에서 "해당 사이트에서 해당 유형의 링크를 항상 열 수 있도록 허용" 확인란의 표시 여부를 제어합니다. 이 정책은 https:// 링크에만 적용됩니다.

해당 정책을 사용하도록 설정하는 경우 외부 프로토콜 확인 메시지가 표시되면 사용자는 "항상 허용"을 선택하여 해당 사이트의 프로토콜에 대한 이후의 모든 확인 메시지를 건너뛸 수 있습니다.

해당 정책을 사용하지 않도록 설정하는 경우 "항상 허용" 확인란이 표시되지 않습니다. 외부 프로토콜이 호출될 때마다 사용자에게 확인 메시지가 표시됩니다.

Microsoft Edge 83 이전에는 이 정책을 구성하지 않으면 "항상 허용" 확인란이 표시되지 않습니다. 외부 프로토콜이 호출될 때마다 사용자에게 확인 메시지가 표시됩니다.

Microsoft Edge 83에서 이 정책을 구성하지 않으면 edge://flags에서 "프로토콜 시작 프롬프트 기본 설정 기억 사용” 플래그로 확인란 표시가 제어됩니다.

Microsoft Edge 84부터 이 정책을 구성하지 않으면 외부 프로토콜 확인 메시지가 표시될 때 사용자는 "항상 허용"을 선택하여 해당 사이트의 프로토콜에 대한 이후의 모든 확인 메시지를 건너뛸 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ExternalProtocolDialogShowAlwaysOpenCheckbox
  - GP 이름: 외부 프로토콜 대화 상자에서 "항상 열기" 확인란 표시
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: ExternalProtocolDialogShowAlwaysOpenCheckbox
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ExternalProtocolDialogShowAlwaysOpenCheckbox
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="familysafetysettingsenabled"></a>FamilySafetySettingsEnabled

  #### <a name="allow-users-to-configure-family-safety-and-kids-mode"></a>사용자가 가족 보호 및 키즈 모드를 구성할 수 있도록 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (83 이상)

  #### <a name="description"></a>설명

  이 정책은 브라우저에서 두 개의 가족 안전 관련 기능을 비활성화합니다. 이렇게 하면 설정 내부의 패밀리 페이지가 숨겨지고 edge://settings/family 탐색이 차단됩니다. 패밀리 설정 페이지에는 Microsoft Family Safety 안전 기능이 있는 패밀리 그룹에서 사용할 수 있는 기능이 설명되어 있습니다. 가족 보호에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2098432](https://go.microsoft.com/fwlink/?linkid=2098432)을 참조하세요. 또한 이 정책은 Microsoft Edge 90에서 시작하여 사용자 지정 테마가 있는 친숙한 검색 모드인 키즈 모드를 비활성화하고 장치 암호가 종료되어야 하는 목록 검색을 허용합니다. 키즈 모드에 대한 자세한 내용은 다음을 참조하세요. ([https://go.microsoft.com/fwlink/?linkid=2146910](https://go.microsoft.com/fwlink/?linkid=2146910))

이 정책을 사용하거나 구성하지 않으면 설정에 패밀리 페이지가 표시되고 키즈 모드를 사용할 수 있습니다.

이 정책을 실행 중지하면 패밀리 페이지가 표시되지 않고 키즈 모드가 숨겨집니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: FamilySafetySettingsEnabled
  - GP 이름: 사용자가 가족 보호 및 키즈 모드를 구성할 수 있도록 허용
  - GP 경로(필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: FamilySafetySettingsEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: FamilySafetySettingsEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="favoritesbarenabled"></a>FavoritesBarEnabled

  #### <a name="enable-favorites-bar"></a>즐겨찾기 모음 사용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  즐겨찾기 모음을 사용하거나 사용하지 않도록 설정합니다.

해당 정책을 사용하면 사용자에게 즐겨찾기 모음이 표시됩니다.

해당 정책을 사용하지 않으면 사용자에게 즐겨찾기 모음이 표시되지 않습니다.

해당 정책을 구성하지 않으면 사용자는 즐겨찾기 모음 사용 여부를 결정할 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: FavoritesBarEnabled
  - GP 이름: 즐겨찾기 모음 사용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: FavoritesBarEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: FavoritesBarEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="forcebingsafesearch"></a>ForceBingSafeSearch

  #### <a name="enforce-bing-safesearch"></a>Bing 유해 정보 차단 적용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  Bing 웹 검색의 쿼리가 지정된 값으로 설정된 유해 정보 차단 기능으로 수행되는지 확인합니다. 사용자는 해당 설정을 변경할 수 없습니다.

해당 정책을 'BingSafeSearchNoRestrictionsMode’로 구성하면 Bing 검색의 유해 정보 차단 기능은 bing.com 값으로 돌아갑니다.

해당 정책을 'BingSafeSearchModerateMode'로 구성하면 유해 정보 차단 기능에서 보통 설정이 사용됩니다. 보통 설정은 성인용 비디오와 이미지를 필터링하지만 검색 결과에서 텍스트를 필터링하지 않습니다.

해당 정책을 'BingSafeSearchStrictMode'로 구성하면 유해 정보 차단 기능에서 고급 설정이 사용됩니다. 고급 설정은 성인용 텍스트, 이미지 및 비디오를 필터링합니다.

해당 정책을 사용하지 않도록 설정하거나 구성하지 않으면 Bing 검색에서 유해 정보 차단 기능이 적용되지 않으므로 사용자는 bing.com에서 원하는 값을 설정할 수 있습니다.

정책 옵션 매핑:

* BingSafeSearchNoRestrictionsMode (0) = Bing에서 검색 제한 구성 안 함

* BingSafeSearchModerateMode (1) = Bing에서 보통 검색 제한 구성

* BingSafeSearchStrictMode (2) = Bing에서 고급 검색 제한 구성

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ForceBingSafeSearch
  - GP 이름: Bing 유해 정보 차단 적용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: ForceBingSafeSearch
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ForceBingSafeSearch
  - 예를 들어 값:
``` xml
<integer>0</integer>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="forcecertificatepromptsonmultiplematches"></a>ForceCertificatePromptsOnMultipleMatches

  #### <a name="configure-whether-microsoft-edge-should-automatically-select-a-certificate-when-there-are-multiple-certificate-matches-for-a-site-configured-with-autoselectcertificateforurls"></a>"AutoSelectCertificateForUrls"를 사용하여 구성한 사이트에 대해 일치하는 인증서가 여러 개인 경우 Microsoft Edge에서 자동으로 인증서를 선택할 것인지 여부 지정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (81 이상)

  #### <a name="description"></a>설명

  사용할 수 있는 인증서가 여러 개 있고 사이트가 [AutoSelectCertificateForUrls](#autoselectcertificateforurls) 정책으로 구성된 경우 사용자에게 인증서를 선택하라는 메시지의 표시 여부를 토글합니다. 사이트에 대해 [AutoSelectCertificateForUrls](#autoselectcertificateforurls) 정책을 구성하지 않으면 사용자에게 항상 인증서를 선택하라는 메시지가 표시됩니다.

해당 정책을 True로 설정하면 두 개 이상의 인증서가 있는 경우 Microsoft Edge에서 [AutoSelectCertificateForUrls](#autoselectcertificateforurls) 정책에 정의된 목록에서 사이트에 대한 인증서를 선택하라는 메시지를 사용자에게 표시합니다.

해당 정책을 False로 설정하거나 구성하지 않으면 인증서와 일치하는 항목이 여러 개 있는 경우에도 Microsoft Edge에서 인증서를 자동으로 선택합니다. 사용자에게 [AutoSelectCertificateForUrls](#autoselectcertificateforurls) 정책에 정의된 목록에서 사이트에 대한 인증서를 선택하라는 메시지가 표시되지 않습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ForceCertificatePromptsOnMultipleMatches
  - GP 이름: "AutoSelectCertificateForUrls"를 사용하여 구성한 사이트에 대해 일치하는 인증서가 여러 개인 경우 Microsoft Edge에서 자동으로 인증서를 선택할 것인지 여부 구성
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: ForceCertificatePromptsOnMultipleMatches
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ForceCertificatePromptsOnMultipleMatches
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="forceephemeralprofiles"></a>ForceEphemeralProfiles

  #### <a name="enable-use-of-ephemeral-profiles"></a>임시 프로필 사용 설정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  사용자 프로필의 임시 모드 전환 여부를 제어합니다. 세션이 시작되면 임시 프로필이 생성되고 세션이 종료되면 삭제되며 사용자의 원본 프로필과 연결됩니다.

해당 정책을 사용하면 프로필이 임시 모드로 실행됩니다. 이로 인해 사용자는 해당 장치에 검색 데이터를 저장하지 않고도 자신의 장치에서 작업을 수행할 수 있습니다. 예를 들어 OS 정책으로 해당 정책을 사용하면(예: Windows에서 GPO를 사용하여) 시스템의 모든 프로필에 적용됩니다.

해당 정책을 사용하지 않도록 설정하거나 구성하지 않으면 사용자는 브라우저에 로그인할 때 일반 프로필을 가져옵니다.

임시 모드에서 프로필 데이터는 사용자 세션의 기간 동안만 디스크에 저장됩니다. 브라우저가 닫힌 후에는 브라우저 기록, 확장 및 해당 데이터와 같은 기능, 쿠키와 같은 웹 데이터, 웹 데이터베이스를 저장하지 않습니다. 따라서 사용자는 수동으로 디스크에 데이터를 다운로드하거나 페이지를 저장하거나 인쇄할 수 있습니다. 사용자가 동기화를 사용하도록 설정한 경우 모든 데이터가 일반 프로필과 마찬가지로 동기화 계정에서 보존됩니다. 명시적으로 해당 기능을 사용하지 않도록 설정하지 않는 한 사용자는 임시 모드에서 InPrivate 검색을 사용할 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ForceEphemeralProfiles
  - GP 이름: 임시 프로필 사용 설정
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: ForceEphemeralProfiles
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ForceEphemeralProfiles
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="forcegooglesafesearch"></a>ForceGoogleSafeSearch

  #### <a name="enforce-google-safesearch"></a>Google 유해 정보 차단 적용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  유해 정보 차단 기능을 활성으로 설정한 상태에서 Google 웹 검색의 쿼리를 실행하도록 하고 사용자가 해당 설정을 변경하지 못하도록 합니다.

해당 정책을 사용하면 Google 검색의 유해 정보 차단 기능이 항상 활성 상태가 됩니다.

해당 정책을 사용하지 않도록 설정하거나 구성하지 않으면 Google 검색의 유해 정보 차단 기능이 적용되지 않습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ForceGoogleSafeSearch
  - GP 이름: Google 유해 정보 차단 적용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: ForceGoogleSafeSearch
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ForceGoogleSafeSearch
  - 예를 들어 값:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="forcelegacydefaultreferrerpolicy"></a>ForceLegacyDefaultReferrerPolicy

  #### <a name="use-a-default-referrer-policy-of-no-referrer-when-downgrade-obsolete"></a>no-referrer-when-downgrade의 기본 참조자 정책 사용(사용되지 않음)

  
  >사용되지 않음: 이 정책은 사용되지 않으며 Microsoft Edge 88 이후로는 작동하지 않습니다.
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 macOS(81부터 88까지)

  #### <a name="description"></a>설명

  이 정책은 엔터프라이즈에서 새 기본 참조자 정책과 호환되지 않는 것으로 확인된 경우 웹 콘텐츠를 업데이트할 시간을 더 주기 위한 단기적 메커니즘일 뿐이기 때문에 작동하지 않습니다.

Microsoft Edge의 기본 참조자 정책은 no-referrer-when-downgrade의 값에서 보다 안전한 strict-origin-when-cross-origin으로 강화됩니다.

이 엔터프라이즈 정책을 사용하도록 설정하면 Microsoft Edge의 기본 참조자 정책이 no-referrer-when-downgrade의 이전 값으로 설정됩니다.

이 엔터프라이즈 정책은 기본적으로 사용하지 않도록 설정되어 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ForceLegacyDefaultReferrerPolicy
  - GP 이름: no-referrer-when-downgrade의 기본 참조자 정책 사용(사용되지 않음)
  - GP 경로(필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: ForceLegacyDefaultReferrerPolicy
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ForceLegacyDefaultReferrerPolicy
  - 예를 들어 값:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="forcenetworkinprocess"></a>ForceNetworkInProcess

  #### <a name="force-networking-code-to-run-in-the-browser-process-obsolete"></a>브라우저 프로세스에서 네트워킹 코드 실행 강제(사용되지 않음)

  
  >사용되지 않음: 이 정책은 더 이상 사용되지 않으며 Microsoft Edge 83 이후에는 작동하지 않습니다.
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 78~83

  #### <a name="description"></a>설명

  이 정책은 엔터프라이즈에 네트워킹 API 연결에 의존하지 않는 타사 소프트웨어로 마이그레이션할 수 있는 시간을 더 주기 위한 목적만을 가진 단기 메커니즘으로서 더 이상 작동하지 않습니다. 프록시 서버는 LSP 및 Win32 API 패치 보다 권장됩니다.

해당 정책은 브라우저 프로세스에서 네트워킹 코드를 강제로 실행합니다.

해당 정책은 기본적으로 사용하지 않도록 설정되어 있습니다. 해당 정책을 사용하도록 설정하면 사용자는 네트워킹 프로세스가 샌드 박싱될 때 보안 문제에 노출될 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ForceNetworkInProcess
  - GP 이름: 브라우저 프로세스에서 네트워킹 코드 실행 강제(사용되지 않음)
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: ForceNetworkInProcess
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="forcesync"></a>ForceSync.

  #### <a name="force-synchronization-of-browser-data-and-do-not-show-the-sync-consent-prompt"></a>브라우저 데이터를 강제로 동기화하고 동기화 동의 프롬프트를 표시 안 함

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (86 이상)

  #### <a name="description"></a>설명

  Microsoft Edge에서 데이터 동기화를 강제적으로 하게 합니다. 또한 이 정책은 사용자가 동기화를 끌 수 없게 합니다.

이 정책을 구성하지 않으면 사용자가 동기화를 켜거나 끌 수 있습니다. 이 정책을 사용하면 사용자는 동기화를 끌 수 없습니다.

이 정책이 의도한 대로 작동하려면 [BrowserSignin](#browsersignin) 정책을 구성하지 않거나 또는 사용함으로 설정해야합니다. [BrowserSignin](#browsersignin)이 사용하지 않도록 설정되어 있으면 [ForceSync](#forcesync)가 영향을 받지 않습니다.

[SyncDisabled](#syncdisabled)를 구성하지 않거나 False로 설정해야 합니다. True로 설정하면 [ForceSync](#forcesync)에 영향을 주지 않습니다.

0 = 동기화를 자동으로 시작하지 않고 동기화 동의 표시(기본값) 1 = Azure AD/Azure AD- 사용자 프로필이 저하되고 동기화 동의 프롬프트가 표시되지 않음

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ForceSync
  - GP 이름: 브라우저 데이터를 강제로 동기화하고 동기화 동의 프롬프트를 표시 안 함
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: ForceSync
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ForceSync
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="forceyoutuberestrict"></a>ForceYouTubeRestrict

  #### <a name="force-minimum-youtube-restricted-mode"></a>최소 YouTube 제한 모드 강제

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  YouTube에서 최소 제한 모드를 적용하고 사용자가 덜 제한된 모드를 선택하지 못하도록 합니다.

‘고급’으로 설정하여 YouTube에 고급 제한 모드를 적용합니다.

‘보통’으로 설정하여 사용자가 YouTube에서 보통 제한 모드 및 고급 제한 모드만 사용하도록 적용합니다. 제한 모드를 사용하지 않도록 설정할 수 없습니다.

‘해제’로 설정하거나 해당 정책을 구성하지 않으면 YouTube에 제한 모드를 적용하지 않습니다. YouTube 정책과 같은 외부 정책으로 제한 모드를 계속 적용할 수 있습니다.

정책 옵션 매핑:

* 해제 (0) = YouTube에서 제한 모드 적용 안 함

* 보통 (1) = YouTube에서 보통 제한 모드 이상 적용

* 고급 (2) = YouTube에 고급 제한 모드 적용

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ForceYouTubeRestrict
  - GP 이름: 최소 YouTube 제한 모드 강제
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: ForceYouTubeRestrict
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ForceYouTubeRestrict
  - 예를 들어 값:
``` xml
<integer>0</integer>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="fullscreenallowed"></a>FullscreenAllowed

  #### <a name="allow-full-screen-mode"></a>전체 화면 모드 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows (77 이상)

  #### <a name="description"></a>설명

  전체 화면 모드의 가용성 설정 - 모든 Microsoft Edge UI가 숨겨지고 웹 콘텐츠만 표시됩니다.

해당 정책을 사용하도록 설정하거나 구성하지 않으면 적절한 사용 권한이 있는 사용자, 앱 및 확장이 전체 화면 모드를 입력할 수 있습니다.

해당 정책을 사용하지 않도록 설정하면 사용자, 앱 및 확장이 전체 화면 모드를 입력할 수 없습니다.

전체 화면 모드가 비활성화된 경우 명령줄을 사용하여 키오스크 모드에서 Microsoft Edge를 열 수 없습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: FullscreenAllowed
  - GP 이름: 전체 화면 모드 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: FullscreenAllowed
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="globallyscopehttpauthcacheenabled"></a>GloballyScopeHTTPAuthCacheEnabled

  #### <a name="enable-globally-scoped-http-auth-cache"></a>전역 범위 HTTP 인증 캐시 사용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (81 이상)

  #### <a name="description"></a>설명

  해당 정책은 HTTP 서버 인증 자격 증명을 사용하여 프로필 캐시당 단일 전역을 구성합니다.

해당 정책을 사용하지 않거나 설정하지 않으면 브라우저에서는 상위 사이트에 따라 HTTP 서버 인증 자격 증명의 범위를 지정하는 80 버전 기준의 사이트 간 인증을 기본 동작으로 사용합니다. 따라서 두 사이트에서 동일한 인증 도메인의 리소스를 사용하는 경우 두 사이트의 컨텍스트에 관계 없이 각각의 자격 증명을 제공해야 합니다. 캐시된 프록시 자격 증명은 사이트 간에 다시 사용됩니다.

해당 정책을 사용하면 한 사이트의 컨텍스트에 입력한 HTTP 인증 자격 증명이 다른 사이트의 컨텍스트에서 자동으로 사용됩니다.

해당 정책을 사용하면 사이트는 일부 유형의 사이트 간 공격에 노출될 수 있으며 사용자는 URL에 포함된 자격 증명을 사용하여 HTTP 인증 캐시에 엔트리를 추가함으로써 쿠키 없이도 사이트 간에 추적할 수 있습니다.

해당 정책은 기업에게 레거시 동작에 따라 로그인 프로시저를 업데이트하는 기회를 제공하기 위한 것이며 추후 제거됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: GloballyScopeHTTPAuthCacheEnabled
  - GP 이름: 전역 범위 HTTP 인증 캐시 사용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: GloballyScopeHTTPAuthCacheEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: GloballyScopeHTTPAuthCacheEnabled
  - 예를 들어 값:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="gotointranetsiteforsinglewordentryinaddressbar"></a>GoToIntranetSiteForSingleWordEntryInAddressBar

  #### <a name="force-direct-intranet-site-navigation-instead-of-searching-on-single-word-entries-in-the-address-bar"></a>주소 표시줄에서 단일 단어 항목을 검색하는 대신 직접 인트라넷 사이트 탐색 강제

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (78 이상)

  #### <a name="description"></a>설명

  해당 정책을 사용하면 주소 표시줄에 입력한 텍스트가 문장 부호 없는 단일 단어인 경우 주소 표시줄 제안 목록의 상위 자동 제안 결과가 인트라넷 사이트를 탐색합니다.

문장 부호 없는 단일 단어 입력 시 기본 탐색은 입력된 텍스트와 일치하는 인트라넷 사이트 탐색을 수행합니다.

해당 정책을 사용하면 텍스트가 문장 부호 없는 단일 단어인 경우 주소 표시줄 제안 목록의 두 번째 자동 제안 결과가 입력된 대로 웹 검색을 정확하게 수행합니다. 웹 검색을 방지하는 정책이 설정되지 않은 경우 기본 검색 공급자가 사용됩니다.

해당 정책을 사용하면 다음과 같은 두 가지 영향을 미칠 수 있습니다.

일반적으로 기록 항목으로 확인되는 단일 단어 쿼리에 대한 응답으로 사이트에 대한 탐색은 더 이상 일어나지 않습니다. 대신 브라우저에서 조직 인트라넷에 존재하지 않을 수 있는 내부 사이트로 탐색을 시도합니다. 이 경우 404 오류가 발생합니다.

자주 사용하는 단일 단어 검색 용어로 검색을 올바르게 수행하려면 검색 제안을 수동으로 선택해야 합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: GoToIntranetSiteForSingleWordEntryInAddressBar
  - GP 이름: 주소 표시줄에서 단일 단어 항목을 검색하는 대신 직접 인트라넷 사이트 탐색 강제
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: GoToIntranetSiteForSingleWordEntryInAddressBar
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: GoToIntranetSiteForSingleWordEntryInAddressBar
  - 예를 들어 값:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="hstspolicybypasslist"></a>HSTSPolicyBypassList

  #### <a name="configure-the-list-of-names-that-will-bypass-the-hsts-policy-check"></a>HSTS 정책 확인을 무시하는 이름 목록 구성

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (79 이상)

  #### <a name="description"></a>설명

  해당 목록에 지정된 호스트 이름은 잠재적으로 "http://"에서 "https://"로 요청을 업그레이드할 수 있는 HSTS 정책 검사에서 제외됩니다. 해당 정책에는 단일 레이블 호스트 이름만 사용할 수 있습니다. 호스트 이름을 정식화해야 합니다. 모든 IDN을 해당 A-레이블 서식으로 변환해야 하며 모든 ASCII 문자는 소문자여야 합니다. 해당 정책은 지정된 특정 호스트 이름에만 적용됩니다. 목록에 있는 이름의 하위 도메인에는 적용되지 않습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: HSTSPolicyBypassList
  - GP 이름: HSTS 정책 확인을 무시하는 이름 목록 구성
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\HSTSPolicyBypassList
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\HSTSPolicyBypassList\1 = "meet"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: HSTSPolicyBypassList
  - 예를 들어 값:
``` xml
<array>
  <string>meet</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="hardwareaccelerationmodeenabled"></a>HardwareAccelerationModeEnabled

  #### <a name="use-hardware-acceleration-when-available"></a>가능한 경우 하드웨어 가속 사용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  사용 가능한 경우 하드웨어 가속을 사용할지 여부를 지정합니다. 해당 정책을 사용하도록 설정하거나 구성하지 않으면 GPU 기능이 명시적으로 차단되지 않는 한 하드웨어 가속을 사용할 수 있습니다.

해당 정책을 사용하지 않도록 설정하면 하드웨어 가속을 사용할 수 없습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: HardwareAccelerationModeEnabled
  - GP 이름: 가능한 경우 하드웨어 가속 사용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: HardwareAccelerationModeEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: HardwareAccelerationModeEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="hidefirstrunexperience"></a>HideFirstRunExperience

  #### <a name="hide-the-first-run-experience-and-splash-screen"></a>첫 실행 환경 및 시작 화면 숨김

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (80 이상)

  #### <a name="description"></a>설명

  해당 정책을 사용하면 처음 실행 환경과 시작 화면이 사용자가 처음으로 Microsoft Edge를 실행할 때 표시되지 않습니다.

처음 실행 환경에 표시되는 구성 옵션의 경우 브라우저에서 기본적으로 다음과 같이 설정됩니다.

-새 탭 페이지에서 피드 유형은 MSN News로 레이아웃은 Inspirational로 설정됩니다.

-Windows 계정이 Azure AD 또는 MSA 유형인 경우 사용자는 계속 Microsoft Edge에 자동으로 로그인됩니다.

- 동기화는 기본적으로 사용하지 않도록 설정되고 사용자에게 브라우저 시작 시 동기화할 것인지 선택하라는 메시지가 표시됩니다. [ForceSync](#forcesync) 또는 [SyncDisabled](#syncdisabled) 정책을 사용하여 동기화 및 동기화 동의 확인 프롬프트를 구성할 수 있습니다.

해당 정책을 사용하지 않도록 설정하거나 구성하지 않으면 처음 실행 환경 및 시작 화면이 표시됩니다.

참고: 처음 실행 환경에서 사용자에게 표시되는 특정 구성 옵션은 다른 특정 정책을 사용하여 관리할 수도 있습니다. 해당 정책과 함께 HideFirstRunExperience 정책을 사용하여 관리된 장치에 대한 특정 브라우저 환경을 구성할 수 있습니다. 일부 다른 정책은 다음과 같습니다.

-[AutoImportAtFirstRun](#autoimportatfirstrun)

-[NewTabPageLocation](#newtabpagelocation)

-[NewTabPageSetFeedType](#newtabpagesetfeedtype)

-[ForceSync](#forcesync)

-[SyncDisabled](#syncdisabled)

-[BrowserSignin](#browsersignin)

-[NonRemovableProfileEnabled](#nonremovableprofileenabled)

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: HideFirstRunExperience
  - GP 이름: 처음 실행 환경 및 시작 화면 숨김
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: HideFirstRunExperience
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: HideFirstRunExperience
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="hideinternetexplorerredirectuxforincompatiblesitesenabled"></a>HideInternetExplorerRedirectUXForIncompatibleSitesEnabled

  #### <a name="hide-the-one-time-redirection-dialog-and-the-banner-on-microsoft-edge"></a>Microsoft Edge에서 일회성 리디렉션 대화 상자 및 배너 숨기기

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows (87 이상)

  #### <a name="description"></a>설명

  이 정책은 일회성 리디렉션 대화 상자와 배너를 사용하지 않도록 설정하는 옵션을 제공합니다. 이 정책을 사용하도록 설정하면 사용자는 일회성 대화 상자와 배너를 모두 볼 수 없습니다.
사용자가 Internet Explorer에서 호환되지 않는 웹 사이트를 접할 때 계속 Microsoft Edge로 리디렉션되지만 해당 검색 데이터는 가져오지 않습니다.

- 이 정책을 사용하도록 설정하면 사용자에게 일회성 리디렉션 대화 상자와 배너가 표시되지 않습니다. 리디렉션이 발생하는 경우 사용자의 검색 데이터를 가져올 수 없습니다.

- 이 정책을 사용하지 않도록 설정하거나 구성하지 않으면 최초 리디렉션 시 리디렉션 대화 상자가 표시되고 리디렉션으로 시작하는 세션에서 영구적 리디렉션 배너가 사용자에게 표시됩니다. 사용자의 검색 데이터는 사용자가 그러한 리디렉션(사용자가 일회성 대화 상자에서 동의하는 경우에만 해당)을 접할 때마다 가져오게 됩니다.


  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: HideInternetExplorerRedirectUXForIncompatibleSitesEnabled
  - GP 이름: Microsoft Edge에서 일회성 리디렉션 대화 상자 및 배너 숨기기
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: HideInternetExplorerRedirectUXForIncompatibleSitesEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="importautofillformdata"></a>ImportAutofillFormData

  #### <a name="allow-importing-of-autofill-form-data"></a>자동 채우기 양식 데이터 가져오기 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  사용자가 다른 브라우저에서 Microsoft Edge로 자동 채우기 양식 데이터를 가져올 수 있도록 허용합니다.

해당 정책을 사용하면 자동 채우기 데이터를 수동으로 가져오는 옵션이 자동으로 선택됩니다.

해당 정책을 사용하지 않도록 설정하면 처음 실행 시 양식 데이터 자동 채우기를 가져오지 않으며 사용자가 수동으로 가져올 수 없습니다.

해당 정책을 구성하지 않으면 처음 실행 시 데이터 자동 채우기를 가져오며 사용자가 추후에 세션을 검색하는 동안 해당 데이터를 수동으로 가져올지 여부를 선택할 수 있습니다.

해당 정책을 권장 사항으로 설정할 수 있습니다. 즉, Microsoft Edge가 처음 실행 시 자동 채우기 데이터를 가져오지만 사용자가 수동으로 가져오는 동안 **데이터 자동 채우기** 옵션을 선택하거나 선택 취소할 수 있습니다.

**참고**: 해당 정책은 현재 Google Chrome (Windows 7, 8, 10 및 MacOS에서) 및 Mozilla Firefox (Windows 7, 8, 10 및 MacOS에서)에서 가져오기를 관리합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ImportAutofillFormData
  - GP 이름: 자동 채우기 양식 데이터 가져오기 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: ImportAutofillFormData
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ImportAutofillFormData
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="importbrowsersettings"></a>ImportBrowserSettings

  #### <a name="allow-importing-of-browser-settings"></a>브라우저 설정 가져오기 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (78 이상)

  #### <a name="description"></a>설명

  사용자가 다른 브라우저에서 Microsoft Edge로 브라우저 설정을 가져올 수 있도록 허용합니다.

해당 정책을 사용하면 **브라우저 데이터 가져오기** 대화 상자에서 **브라우저 설정** 확인란이 자동으로 선택됩니다.

해당 정책을 사용하지 않도록 설정하면 처음 실행 시 브라우저 설정을 가져오지 않으며 사용자가 수동으로 가져올 수 없습니다.

해당 정책을 구성하지 않으면 처음 실행 시 브라우저 설정을 가져오며 사용자가 추후에 세션을 검색하는 동안 해당 설정을 수동으로 가져올지 여부를 선택할 수 있습니다.

해당 정책을 권장 사항으로 설정할 수 있습니다. 즉, Microsoft Edge가 처음 실행 시 설정을 가져오지만 사용자가 수동으로 가져오는 동안 **브라우저 설정** 옵션을 선택하거나 선택 취소할 수 있습니다.

**참고**: 해당 정책은 현재 Google Chrome (Windows 7, 8, 10 및 MacOS에서) 가져오기를 관리합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ImportBrowserSettings
  - GP 이름: 브라우저 설정 가져오기 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: ImportBrowserSettings
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ImportBrowserSettings
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="importcookies"></a>ImportCookies

  #### <a name="allow-importing-of-cookies"></a>쿠키 가져오기 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (81 이상)

  #### <a name="description"></a>설명

  사용자가 다른 브라우저에서 Microsoft Edge로 쿠키를 가져올 수 있도록 허용합니다.

해당 정책을 사용하지 않으면 처음 실행 시 쿠키를 가져오지 않습니다.

해당 정책을 구성하지 않으면 처음 실행 시 쿠키를 가져옵니다.

해당 정책을 권장 사항으로 설정할 수 있습니다. 즉, Microsoft Edge가 처음 실행 시 쿠키를 가져옵니다.

**참고**: 해당 정책은 현재 Google Chrome (Windows 7, 8, 10 및 MacOS에서) 가져오기를 관리합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ImportCookies
  - GP 이름: 쿠키 가져오기 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: ImportCookies
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ImportCookies
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="importextensions"></a>ImportExtensions

  #### <a name="allow-importing-of-extensions"></a>확장 가져오기 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (81 이상)

  #### <a name="description"></a>설명

  사용자가 다른 브라우저에서 Microsoft Edge로 확장을 가져올 수 있도록 허용합니다.

해당 정책을 사용하면 **브라우저 데이터 가져오기** 대화 상자에서 **확장** 확인란이 자동으로 선택됩니다.

해당 정책을 사용하지 않도록 설정하면 처음 실행 시 확장을 가져오지 않으며 사용자가 수동으로 가져올 수 없습니다.

해당 정책을 구성하지 않으면 처음 실행 시 확장을 가져오며 사용자가 추후에 세션을 검색하는 동안 해당 확장을 수동으로 가져올지 여부를 선택할 수 있습니다.

해당 정책을 권장 사항으로 설정할 수 있습니다. 즉, Microsoft Edge가 처음 실행 시 확장을 가져오지만 사용자가 수동으로 가져오는 동안 **즐겨찾기** 옵션을 선택하거나 선택 취소할 수 있습니다.

**참고**: 해당 정책은 현재 Google Chrome (Windows 7, 8, 10 및 MacOS에서) 가져오기를 지원합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ImportExtensions
  - GP 이름: 확장 가져오기 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: ImportExtensions
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ImportExtensions
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="importfavorites"></a>ImportFavorites

  #### <a name="allow-importing-of-favorites"></a>즐겨찾기 가져오기 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  사용자가 다른 브라우저에서 Microsoft Edge로 즐겨찾기를 가져올 수 있도록 허용합니다.

해당 정책을 사용하면 **브라우저 데이터 가져오기** 대화 상자에서 **즐겨찾기** 확인란이 자동으로 선택됩니다.

해당 정책을 사용하지 않도록 설정하면 처음 실행 시 즐겨찾기를 가져오지 않으며 사용자가 수동으로 가져올 수 없습니다.

해당 정책을 구성하지 않으면 처음 실행 시 즐겨찾기를 가져오며 사용자가 추후에 세션을 검색하는 동안 해당 즐겨찾기를 수동으로 가져올지 여부를 선택할 수 있습니다.

해당 정책을 권장 사항으로 설정할 수 있습니다. 즉, Microsoft Edge가 처음 실행 시 즐겨찾기를 가져오지만 사용자가 수동으로 가져오는 동안 **즐겨찾기** 옵션을 선택하거나 선택 취소할 수 있습니다.

**참고**: 해당 정책은 현재 Internet Explorer (Windows 7, 8, 10에서), Google Chrome (Windows 7, 8, 10 및 MacOS에서), Mozilla Firefox (Windows 7, 8, 10 및 MacOS에서) 및 Apple Safari (MacOS에서) 브라우저에서 가져오기를 관리합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ImportFavorites
  - GP 이름: 즐겨찾기 가져오기 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: ImportFavorites
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ImportFavorites
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="importhistory"></a>ImportHistory

  #### <a name="allow-importing-of-browsing-history"></a>검색 기록 가져오기 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  사용자가 다른 브라우저에서 Microsoft Edge로 검색 기록을 가져올 수 있도록 허용합니다.

해당 정책을 사용하면 **브라우저 데이터 가져오기** 대화 상자에서 **검색 기록** 확인란이 자동으로 선택됩니다.

해당 정책을 사용하지 않도록 설정하면 처음 실행 시 검색 기록 데이터를 가져오지 않으며 사용자가 수동으로 가져올 수 없습니다.

해당 정책을 구성하지 않으면 처음 실행 시 검색 기록 데이터를 가져오며 사용자가 추후에 세션을 검색하는 동안 해당 데이터를 수동으로 가져올지 여부를 선택할 수 있습니다.

해당 정책을 권장 사항으로 설정할 수 있습니다. 즉, Microsoft Edge가 처음 실행 시 검색 기록을 가져오지만 사용자가 수동으로 가져오는 동안 **기록** 옵션을 선택하거나 선택 취소할 수 있습니다.

**참고**: 해당 정책은 현재 Internet Explorer (Windows 7, 8, 10에서), Google Chrome (Windows 7, 8, 10 및 MacOS에서), Mozilla Firefox (Windows 7, 8, 10 및 MacOS에서) 및 Apple Safari (MacOS에서) 브라우저에서 가져오기를 관리합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ImportHistory
  - GP 이름: 검색 기록 가져오기 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: ImportHistory
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ImportHistory
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="importhomepage"></a>ImportHomepage

  #### <a name="allow-importing-of-home-page-settings"></a>홈페이지 설정 가져오기 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  사용자가 다른 브라우저에서 Microsoft Edge로 홈페이지 설정을 가져올 수 있도록 허용합니다.

해당 정책을 사용하면 홈페이지 설정을 수동으로 가져오는 옵션이 자동으로 선택됩니다.

해당 정책을 사용하지 않도록 설정하면 처음 실행 시 홈페이지 설정을 가져오지 않으며 사용자가 수동으로 가져올 수 없습니다.

해당 정책을 구성하지 않으면 처음 실행 시 홈페이지 설정을 가져오며 사용자가 추후에 세션을 검색하는 동안 해당 데이터를 수동으로 가져올지 여부를 선택할 수 있습니다.

해당 정책을 권장 사항으로 설정할 수 있습니다. 즉, Microsoft Edge가 처음 실행 시 홈페이지 설정을 가져오지만 사용자가 수동으로 가져오는 동안 **홈페이지** 옵션을 선택하거나 선택 취소할 수 있습니다.

**참고**: 해당 정책은 현재 Internet Explorer (Windows 7, 8, 10에서) 가져오기를 관리합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ImportHomepage
  - GP 이름: 홈페이지 설정 가져오기 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: ImportHomepage
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ImportHomepage
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="importopentabs"></a>ImportOpenTabs

  #### <a name="allow-importing-of-open-tabs"></a>열린 탭 가져오기 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (79 이상)

  #### <a name="description"></a>설명

  사용자가 다른 브라우저에서 Microsoft Edge로 열린 고정 탭을 가져올 수 있도록 허용합니다.

해당 정책을 사용하면 **브라우저 데이터 가져오기** 대화 상자에서 **열린 탭** 확인란이 자동으로 선택됩니다.

해당 정책을 사용하지 않도록 설정하면 처음 실행 시 열린 탭을 가져오지 않으며 사용자가 수동으로 가져올 수 없습니다.

해당 정책을 구성하지 않으면 처음 실행 시 열린 탭을 가져오며 사용자가 추후에 세션을 검색하는 동안 해당 탭을 수동으로 가져올지 여부를 선택할 수 있습니다.

해당 정책을 권장 사항으로 설정할 수 있습니다. 즉, Microsoft Edge가 처음 실행 시 열린 탭을 가져오지만 사용자가 수동으로 가져오는 동안 **열린 탭** 옵션을 선택하거나 선택 취소할 수 있습니다.

**참고**: 해당 정책은 현재 Google Chrome (Windows 7, 8, 10 및 MacOS에서) 가져오기를 지원합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ImportOpenTabs
  - GP 이름: 열린 탭 가져오기 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: ImportOpenTabs
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ImportOpenTabs
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="importpaymentinfo"></a>ImportPaymentInfo

  #### <a name="allow-importing-of-payment-info"></a>결제 정보 가져오기 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  사용자가 다른 브라우저에서 Microsoft Edge로 결제 정보를 가져올 수 있도록 허용합니다.

해당 정책을 사용하면 **브라우저 데이터 가져오기** 대화 상자에서 **결제 정보** 확인란이 자동으로 선택됩니다.

해당 정책을 사용하지 않도록 설정하면 처음 실행 시 결제 정보를 가져오지 않으며 사용자가 수동으로 가져올 수 없습니다.

해당 정책을 구성하지 않으면 처음 실행 시 결제 정보를 가져오며 사용자가 추후에 세션을 검색하는 동안 해당 정보를 수동으로 가져올지 여부를 선택할 수 있습니다.

해당 정책을 권장 사항으로 설정할 수 있습니다. 즉, Microsoft Edge가 처음 실행 시 결제 정보를 가져오지만 사용자가 수동으로 가져오는 동안 **결제 정보** 옵션을 선택하거나 선택 취소할 수 있습니다.

**참고**: 해당 정책은 현재 Google Chrome (Windows 7, 8, 10 및 MacOS에서) 가져오기를 관리합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ImportPaymentInfo
  - GP 이름: 결제 정보 가져오기 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: ImportPaymentInfo
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ImportPaymentInfo
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="importsavedpasswords"></a>ImportSavedPasswords

  #### <a name="allow-importing-of-saved-passwords"></a>저장된 암호 가져오기 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  사용자가 다른 브라우저에서 Microsoft Edge로 저장된 암호를 가져올 수 있도록 허용합니다.

해당 정책을 사용하면 저장된 암호를 수동으로 가져오는 옵션이 자동으로 선택됩니다.

해당 정책을 사용하지 않도록 설정하면 처음 실행 시 저장된 암호를 가져오지 않으며 사용자가 수동으로 가져올 수 없습니다.

해당 정책을 구성하지 않으면 처음 실행 시 저장된 암호를 가져오며 사용자가 추후에 세션을 검색하는 동안 해당 암호를 수동으로 가져올지 여부를 선택할 수 있습니다.

해당 정책을 권장 사항으로 설정할 수 있습니다. 즉, Microsoft Edge가 처음 실행 시 암호를 가져오지만 사용자가 수동으로 가져오는 동안 **암호** 옵션을 선택하거나 선택 취소할 수 있습니다.

**참고**: 해당 정책은 현재 Internet Explorer (Windows 7, 8, 10에서), Google Chrome (Windows 7, 8, 10 및 MacOS에서) 및 Mozilla Firefox (Windows 7, 8, 10 및 MacOS에서) 브라우저에서 가져오기를 관리합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ImportSavedPasswords
  - GP 이름: 저장된 암호 가져오기 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: ImportSavedPasswords
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ImportSavedPasswords
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="importsearchengine"></a>ImportSearchEngine

  #### <a name="allow-importing-of-search-engine-settings"></a>검색 엔진 설정 가져오기 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  사용자가 다른 브라우저에서 Microsoft Edge로 검색 엔진 설정을 가져올 수 있도록 허용합니다.

해당 정책을 사용하면 검색 엔진 설정을 가져오는 옵션이 자동으로 선택됩니다.

해당 정책을 사용하지 않도록 설정하면 처음 실행 시 검색 엔진 설정을 가져오지 않으며 사용자가 수동으로 가져올 수 없습니다.

해당 정책을 구성하지 않으면 처음 실행 시 검색 엔진 설정을 가져오며 사용자가 추후에 세션을 검색하는 동안 해당 데이터를 수동으로 가져올지 여부를 선택할 수 있습니다.

해당 정책을 권장 사항으로 설정할 수 있습니다. 즉, Microsoft Edge가 처음 실행 시 검색 엔진 설정을 가져오지만 사용자가 수동으로 가져오는 동안 **검색 엔진** 옵션을 선택하거나 선택 취소할 수 있습니다.

**참고**: 해당 정책은 현재 Internet Explorer (Windows 7, 8, 10에서) 가져오기를 관리합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ImportSearchEngine
  - GP 이름: 검색 엔진 설정 가져오기 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: ImportSearchEngine
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ImportSearchEngine
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="importshortcuts"></a>ImportShortcuts

  #### <a name="allow-importing-of-shortcuts"></a>바로 가기 가져오기 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (81 이상)

  #### <a name="description"></a>설명

  사용자가 다른 브라우저에서 Microsoft Edge로 바로가기를 가져올 수 있도록 허용합니다.

해당 정책을 사용하지 않으면 처음 실행 시 바로가기를 가져오지 않습니다.

해당 정책을 구성하지 않으면 처음 실행 시 바로가기를 가져옵니다.

해당 정책을 권장 사항으로 설정할 수 있습니다. 즉, Microsoft Edge가 처음 실행 시 바로가기를 가져옵니다.

**참고**: 해당 정책은 현재 Google Chrome (Windows 7, 8, 10 및 MacOS에서) 가져오기를 관리합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ImportShortcuts
  - GP 이름: 바로 가기 가져오기 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: ImportShortcuts
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ImportShortcuts
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="inprivatemodeavailability"></a>InPrivateModeAvailability

  #### <a name="configure-inprivate-mode-availability"></a>InPrivate 모드 가용성 구성

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  사용자가 Microsoft Edge에서 InPrivate 모드로 페이지를 열 수 있는지 여부를 지정합니다.

해당 정책을 구성하지 않거나 '사용'으로 설정하면 사용자는 InPrivate 모드로 페이지를 열 수 있습니다.

해당 정책을 ‘사용 안 함’으로 설정하면 사용자는 InPrivate 모드를 사용할 수 없습니다.

해당 정책을 ‘강제’로 설정하면 InPrivate 모드를 항상 사용합니다.

정책 옵션 매핑:

* 사용 (0) = InPrivate 모드 사용 가능

* 사용 안 함 (1) = InPrivate 모드 사용 안 함

* 강제 (2) = InPrivate 모드 사용 강제

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: InPrivateModeAvailability
  - GP 이름: InPrivate 모드 가용성 구성
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: InPrivateModeAvailability
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: InPrivateModeAvailability
  - 예를 들어 값:
``` xml
<integer>1</integer>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="insecureformswarningsenabled"></a>InsecureFormsWarningsEnabled

  #### <a name="enable-warnings-for-insecure-forms"></a>안전하지 않은 양식에 대한 경고 설정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (86 이상)

  #### <a name="description"></a>설명

  이 정책은 브라우저의 보안(HTTPS) 사이트에 포함된 안전하지 않은 양식(HTTP를 통해 전송되는 양식)의 처리를 제어합니다.
이 정책을 사용하거나 설정하지 않으면 안전하지 않은 양식이 제출될 때 전체 페이지 경고가 표시됩니다. 또한, 포커스를 받을 때 양식 필드 옆에 경고 풍선이 표시되며 해당 양식에 대해 자동 채우기를 사용할 수 없습니다.
이 정책을 사용하지 않도록 설정하면 안전하지 않은 양식에 대한 경고가 표시되지 않으며 자동 채우기가 정상적으로 작동합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: InsecureFormsWarningsEnabled
  - GP 이름: 안전하지 않은 양식에 대한 경고 설정
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: InsecureFormsWarningsEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: InsecureFormsWarningsEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="intensivewakeupthrottlingenabled"></a>IntensiveWakeUpThrottlingEnabled

  #### <a name="control-the-intensivewakeupthrottling-feature"></a>IntensiveWakeUpThrottling 기능 제어

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS(85 이상)

  #### <a name="description"></a>설명

  IntensiveWakeUpThrottling 기능을 사용하면 배경 탭의 Javascript 타이머가 공격적으로 스로틀링되고 결합되며, 페이지가 5분 이상 배경에 머문 후 분당 1회 이하로 실행됩니다.

이는 웹 표준을 준수하는 기능이지만 특정 작업을 1분까지 지연시킴으로써 일부 웹사이트의 기능을 손상시킬 수 있습니다. 그러나 이 기능을 사용하면 상당한 CPU와 배터리 절감 효과가 발생합니다. 자세한 내용은 https://bit.ly/30b1XR4을 참조하십시오.

이 정책을 사용하면 기능이 강제로 활성화되며 사용자는 이 설정을 무시할 수 없습니다.
이 정책을 사용하지 않으면 기능이 강제로 비활성화되며 사용자는 이 설정을 무시할 수 없습니다.
이 정책을 구성하지 않으면 해당 기능은 자체 내부 로직으로 제어됩니다. 사용자가 수동으로 이 설정을 구성할 수 있습니다.

렌더러 프로세스당 정책이 적용되며, 렌더러 프로세스가 시작될 때 정책 설정의 가장 최근의 값이 적용됩니다. 로드된 모든 탭이 일관된 정책 설정을 받도록 하려면 전체 재시작이 필요합니다. 프로세스가 이 정책의 다른 값으로 실행되는 것은 영향을 주지 않습니다.


  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: IntensiveWakeUpThrottlingEnabled
  - GP 이름: IntensiveWakeUpThrottling 기능 제어
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: IntensiveWakeUpThrottlingEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: IntensiveWakeUpThrottlingEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="internetexplorerintegrationenhancedhangdetection"></a>InternetExplorerIntegrationEnhancedHangDetection

  #### <a name="configure-enhanced-hang-detection-for-internet-explorer-mode"></a>Internet Explorer 모드에 대한 향상된 중지 검색 구성

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 84 이상

  #### <a name="description"></a>설명

  향상된 중지 검색은 독립실행형 Internet Explorer에서 사용하는 것보다 Internet Explorer 모드에서 중지된 웹페이지를 탐지하는 더 세분화된 방법입니다. 웹페이지가 멈춘 경우 브라우저에서 완화 조치를 적용하여 브라우저가 나머지 부분에서 중지되는 것을 방지합니다.

이 설정을 활성화하면 웹사이트와 호환되지 않는 문제가 발생할 경우 향상된 중지 검색 기능을 사용할 수 있습니다. 독립실행형 Internet Explorer가 아닌 Internet Explorer 모드에서 "(웹 사이트)가 응답 하지 않음"과 같은 알림이 표시되는 경우에만 이 정책을 비활성화하는 것이 좋습니다.

해당 설정은 다음과 함께 작동됩니다. [InternetExplorerIntegrationLevel](#internetexplorerintegrationlevel) 정책은 'IEMode' 및 [InternetExplorerIntegrationSiteList](#internetexplorerintegrationsitelist) 정책으로 설정합니다. 여기서 목록에는 하나 이상의 항목이 있습니다.

이 정책을 '사용'으로 설정하거나 구성하지 않으면 Internet Explorer 모드에서 실행 중인 웹 사이트에서 향상된 중지 검색을 사용하게 됩니다.

이 정책을 '사용 안 함'으로 설정하면 향상된 중지 검색이 비활성화되고 사용자는 기본 Internet Explorer 중지 검색 동작을 사용할 수 있습니다.

Internet Explorer 모드에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2094210](https://go.microsoft.com/fwlink/?linkid=2094210)을 참조하세요.

정책 옵션 매핑:

* 사용 안 함 (0) = 향상된 중지 검색 사용 안 함

* 사용 (1) = 향상된 중지 검색 사용함

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: InternetExplorerIntegrationEnhancedHangDetection
  - GP 이름: Internet Explorer 모드에 대한 향상된 중지 검색 구성
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: InternetExplorerIntegrationEnhancedHangDetection
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="internetexplorerintegrationlevel"></a>InternetExplorerIntegrationLevel

  #### <a name="configure-internet-explorer-integration"></a>Internet Explorer 통합 구성

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows (77 이상)

  #### <a name="description"></a>설명

  Internet Explorer 모드에 대해 최적의 환경을 구성하는 방법에 대한 지침은 [https://go.microsoft.com/fwlink/?linkid=2094210](https://go.microsoft.com/fwlink/?linkid=2094210)을 참조하세요.

정책 옵션 매핑:

* 없음 (0) = 없음

* IEMode (1) = Internet Explorer 모드

* NeedIE (2) = Internet Explorer 11

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: InternetExplorerIntegrationLevel
  - GP 이름: Internet Explorer 통합 구성
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: InternetExplorerIntegrationLevel
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="internetexplorerintegrationlocalfileallowed"></a>InternetExplorerIntegrationLocalFileAllowed

  #### <a name="allow-launching-of-local-files-in-internet-explorer-mode"></a>Internet Explorer 모드에서 로컬 파일 시작 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows (88 이상)

  #### <a name="description"></a>설명

  이 정책은 명령줄에 지정된 로컬 파일을 사용하여 Microsoft Edge를 Internet Explorer 모드로 시작하는 데 사용되는(예:mode-file-url) 명령줄 인수의 가용성을 제어합니다.

이 설정은 [InternetExplorerIntegrationLevel](#internetexplorerintegrationlevel)이 'IEMode'로 설정되어 있는 경우와 함께 작동합니다.

이 정책을 true로 설정하거나 구성하지 않으면 사용자가 Internet Explorer 모드에서 로컬 파일을 시작하는 데(예: mode-file-url) 명령줄 인수를 사용할 수 있습니다.

이 정책을 false로 설정하면 사용자는 Internet Explorer 모드에서 로컬 파일을 시작하는 데(예: mode-file-url) 명령줄 인수를 사용할 수 없습니다.

Internet Explorer 모드에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2094210](https://go.microsoft.com/fwlink/?linkid=2094210)을 참조하세요.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: InternetExplorerIntegrationLocalFileAllowed
  - GP 이름: Internet Explorer 모드에서 로컬 파일 시작 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: InternetExplorerIntegrationLocalFileAllowed
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="internetexplorerintegrationlocalfileextensionallowlist"></a>InternetExplorerIntegrationLocalFileExtensionAllowList

  #### <a name="open-local-files-in-internet-explorer-mode-file-extension-allow-list"></a>Internet Explorer 모드 파일 확장명 허용 목록에서 로컬 파일 열기

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows (88 이상)

  #### <a name="description"></a>설명

  이 정책은 파일 확장명에 따라 Internet Explorer 모드로 시작할 수 있는 file:// URL을 제한합니다.

이 설정은 [InternetExplorerIntegrationLevel](#internetexplorerintegrationlevel)이 'IEMode'로 설정되어 있는 경우와 함께 작동합니다.

file:/// URL을 Internet Explorer 모드에서 실행하도록 요청하면 URL이 Internet Explorer 모드에서 실행되도록 하려면 URL의 파일 확장명이 이 목록에 있어야 합니다. Internet Explorer 모드에서 열리지 못하도록 차단된 URL이 대신 Edge 모드에서 열립니다.

이 정책을 특수 값 "*"로 설정하거나 구성하지 않으면 모든 파일 확장명이 허용됩니다.

Internet Explorer 모드에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2094210](https://go.microsoft.com/fwlink/?linkid=2094210)을 참조하세요.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: InternetExplorerIntegrationLocalFileExtensionAllowList
  - GP 이름: Internet Explorer 모드 파일 확장명 허용 목록에서 로컬 파일 열기
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\Policies\Microsoft\Edge\InternetExplorerIntegrationLocalFileExtensionAllowList
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\InternetExplorerIntegrationLocalFileExtensionAllowList\1 = ".mht"
SOFTWARE\Policies\Microsoft\Edge\InternetExplorerIntegrationLocalFileExtensionAllowList\2 = ".pdf"
SOFTWARE\Policies\Microsoft\Edge\InternetExplorerIntegrationLocalFileExtensionAllowList\3 = ".vsdx"

```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="internetexplorerintegrationlocalfileshowcontextmenu"></a>InternetExplorerIntegrationLocalFileShowContextMenu

  #### <a name="show-context-menu-to-open-a-link-in-internet-explorer-mode"></a>Internet Explorer 모드에서 링크를 여는 상황에 맞는 메뉴 표시

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows (88 이상)

  #### <a name="description"></a>설명

  이 정책은 file:// 링크의 상황에 맞는 메뉴에서 '새 Internet Explorer 모드에서 링크 열기' 옵션의 표시 여부를 제어합니다.

이 설정은 [InternetExplorerIntegrationLevel](#internetexplorerintegrationlevel)이 'IEMode'로 설정되어 있는 경우와 함께 작동합니다.

이 정책을 true로 설정하면 '새 Internet Explorer 모드 탭에서 링크 열기' 상황에 맞는 메뉴 항목을 file:// 링크에 사용할 수 있습니다.

이 정책을 false로 설정하거나 구성하지 않으면 상황에 맞는 메뉴 항목이 추가되지 않습니다.

Internet Explorer 모드에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2094210](https://go.microsoft.com/fwlink/?linkid=2094210)을 참조하세요.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: InternetExplorerIntegrationLocalFileShowContextMenu
  - GP 이름: Internet Explorer 모드에서 링크를 여는 상황에 맞는 메뉴 표시
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: InternetExplorerIntegrationLocalFileShowContextMenu
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="internetexplorerintegrationsitelist"></a>InternetExplorerIntegrationSiteList

  #### <a name="configure-the-enterprise-mode-site-list"></a>엔터프라이즈 모드 사이트 목록 구성

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows (78 이상)

  #### <a name="description"></a>설명

  Internet Explorer 모드에 대해 최적의 환경을 구성하는 방법에 대한 지침은 [https://go.microsoft.com/fwlink/?linkid=2094210](https://go.microsoft.com/fwlink/?linkid=2094210)을 참조하세요.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 문자열

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: InternetExplorerIntegrationSiteList
  - GP 이름: 엔터프라이즈 모드 사이트 목록 구성
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: InternetExplorerIntegrationSiteList
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
"https://internal.contoso.com/sitelist.xml"
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="internetexplorerintegrationsiteredirect"></a>InternetExplorerIntegrationSiteRedirect

  #### <a name="specify-how-in-page-navigations-to-unconfigured-sites-behave-when-started-from-internet-explorer-mode-pages"></a>Internet Explorer 모드 페이지에서 시작 시 구성되지 않은 사이트에 대한 "페이지 내" 탐색 동작 방법 지정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows (81 이상)

  #### <a name="description"></a>설명

  “페이지 내” 탐색은 현재 페이지의 링크, 스크립트 또는 양식에서 시작됩니다. 이전의 “페이지 내” 탐색 시도가 서버측으로 리디렉션될 수도 있습니다. 반대로 사용자는 브라우저 컨트롤을 사용하여 여러 방법으로 현재 페이지와 독립적인 “페이지 내”가 아닌 탐색을 시작할 수 있습니다. 예를 들어 주소 표시줄, 뒤로 단추 또는 즐겨찾기 링크를 사용합니다.

해당 설정을 사용하면 Internet Explorer 모드에서 로드된 페이지에서 구성되지 않은 사이트로의 탐색(엔터프라이즈 모드 사이트 목록에서 구성되지 않음)을 Microsoft Edge로 다시 전환하거나 Internet Explorer 모드에 유지할 것인지를 지정할 수 있습니다.

해당 설정은 다음과 함께 작동됩니다. [InternetExplorerIntegrationLevel](#internetexplorerintegrationlevel) 정책은 'IEMode' 및 [InternetExplorerIntegrationSiteList](#internetexplorerintegrationsitelist) 정책으로 설정합니다. 여기서 목록에는 하나 이상의 항목이 있습니다.

해당 정책을 사용하지 않도록 설정하거나 구성하지 않으면 Internet Explorer 모드에서 열리도록 구성된 사이트만 해당 모드에서 열립니다. Internet Explorer 모드에서 열리도록 구성되지 않은 사이트는 Microsoft Edge로 다시 리디렉션됩니다.

해당 정책을 ‘기본값’으로 설정하면 Internet Explorer 모드에서 열리도록 구성된 사이트만 해당 모드에서 열립니다. Internet Explorer 모드에서 열리도록 구성되지 않은 사이트는 Microsoft Edge로 다시 리디렉션됩니다.

해당 정책을 ‘AutomaticNavigationsOnly’로 설정하면 구성되지 않은 사이트에 대한 모든 자동 탐색(예: 302 리디렉션)이 Internet Explorer 모드로 유지되는 것을 제외하고 기본 환경을 가져옵니다.

해당 정책을 ‘AllInPageNavigations’로 설정하면 IE 모드로 로드된 페이지에서 구성되지 않은 사이트로의 모든 탐색은 Internet Explorer 모드(최소 권장)로 유지됩니다.

Internet Explorer 모드에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2105106](https://go.microsoft.com/fwlink/?linkid=2105106)을 참조하세요.

정책 옵션 매핑:

* 기본값 (0) = 기본값

* AutomaticNavigationsOnly (1) = Internet Explorer 모드에서 자동 탐색만 유지

* AllInPageNavigations (2) = Internet Explorer 모드에서 모든 페이지 내 탐색 유지

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: InternetExplorerIntegrationSiteRedirect
  - GP 이름: Internet Explorer 모드 페이지에서 시작 시 구성되지 않은 사이트에 대한 "페이지 내" 탐색 동작 방법 지정
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: InternetExplorerIntegrationSiteRedirect
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="internetexplorerintegrationtestingallowed"></a>InternetExplorerIntegrationTestingAllowed

  #### <a name="allow-internet-explorer-mode-testing"></a>Internet Explorer 모드 테스트 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 86 이상

  #### <a name="description"></a>설명

  해당 정책을 사용하면 사용자는 Microsoft Edge에서 Internet Explorer 모드 탭을 열어 Internet Explorer 모드의 응용 프로그램을 테스트할 수 있습니다.

사용자는 'Internet Explorer 모드에서 사이트 열기'를 선택하여 “추가 도구” 메뉴 내에서 해당 작업을 수행할 수 있습니다.

또한 사용자는 'Edge 모드로 사이트 열기' 옵션을 사용하여 사이트 목록에서 응용 프로그램을 제거할 필요 없이 최신 브라우저에서 응용 프로그램을 테스트할 수 있습니다.

해당 설정은 다음과 함께 작동됩니다. [InternetExplorerIntegrationLevel](#internetexplorerintegrationlevel) 정책은 'IEMode' 및 [InternetExplorerIntegrationSiteList](#internetexplorerintegrationsitelist) 정책으로 설정합니다. 여기서 목록에는 하나 이상의 항목이 있습니다.

해당 정책을 사용하면 'Internet Explorer 모드에서 사이트 열기' 옵션이 “추가 도구” 아래에 표시됩니다. 사용자는 이 탭에서 Internet Explorer 모드의 해당 사이트를 볼 수 있습니다. ‘Edge 모드에서 사이트 열기’의 다른 옵션도 “추가 도구” 아래에 표시되며 사이트 목록에서 제거하지 않고 최신 브라우저에서 사이트를 테스트하는 데 도움이 됩니다.

해당 정책을 사용하지 않도록 설정하거나 구성하지 않으면 사용자는 “추가 도구” 메뉴 아래의 'Internet Explorer 모드로 열기' 및 'Edge 모드 에서 열기' 옵션을 볼 수 없습니다. 그러나 사용자는 --ie-모드-테스트 플래그를 사용하여 이러한 옵션을 구성할 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: InternetExplorerIntegrationTestingAllowed
  - GP 이름: Internet Explorer 모드 테스트 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: InternetExplorerIntegrationTestingAllowed
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="intranetredirectbehavior"></a>IntranetRedirectBehavior

  #### <a name="intranet-redirection-behavior"></a>인트라넷 리디렉션 동작

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS 88 이상

  #### <a name="description"></a>설명

  이 정책은 DNS 차단 검사를 통해 인트라넷 리디렉션 동작을 구성합니다. 해당 검사에서는 브라우저가 알려지지 않은 호스트 이름을 리디렉션하는 프록시에 속하는지 여부를 검색하려고 합니다.

이 정책이 구성되어 있지 않으면 브라우저에서 DNS 가로채기 확인 및 인트라넷 리디렉션 제안의 기본 동작을 사용합니다. M88에서는 기본적으로 활성화되지만 이후 릴리스에서는 기본적으로 비활성화됩니다.

[DNSInterceptionChecksEnabled](#dnsinterceptionchecksenabled)는 DNS 차단 검사를 사용하지 않도록 설정할 수 있는 관련 정책입니다 그러나 이 정책은 인트라넷 리디렉션 인포바를 별도로 제어하고 나중에 확장될 수 있는 보다 유연한 버전입니다.
[DNSInterceptionChecksEnabled](#dnsinterceptionchecksenabled) 또는 이 정책에서 차단 검사를 비활성화하도록 요청합니다. 그러면 검사가 비활성화됩니다.
이 정책에서 DNS 가로채기를 사용하지 않도록 설정했지만 [GoToIntranetSiteForSingleWordEntryInAddressBar](#gotointranetsiteforsinglewordentryinaddressbar)가 사용하도록 설정된 경우 단일 단어 쿼리로 인해 인트라넷이 계속 탐색됩니다.

정책 옵션 매핑:

* Default (0) = 기본 브라우저 동작을 사용합니다.

* DisableInterceptionChecksDisableInfobar (1) = DNS 차단 검사 및 did-you-mean "http://intranetsite/" 인포바를 사용하지 않도록 설정합니다.

* DisableInterceptionChecksEnableInfobar (2) = DNS 차단 검사를 사용하지 않도록 설정하고 did-you-mean "http://intranetsite/" 인포바를 허용합니다.

* EnableInterceptionChecksEnableInfobar (3) = DNS 차단 검사 및 did-you-mean "http://intranetsite/" 인포바를 허용합니다.

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: IntranetRedirectBehavior
  - GP 이름: 인트라넷 리디렉션 동작
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: IntranetRedirectBehavior
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: IntranetRedirectBehavior
  - 예를 들어 값:
``` xml
<integer>1</integer>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="isolateorigins"></a>IsolateOrigins

  #### <a name="enable-site-isolation-for-specific-origins"></a>특정 원본에 대해 사이트 격리 사용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  원본 자체 프로세스에서 원본을 격리 상태로 실행하도록 지정합니다.

해당 정책은 하위 도메인의 이름을 따서 명명된 원본을 격리합니다. 예를 들어 https://contoso.com/을(를) 지정하면 https://foo.contoso.com/이(가) https://contoso.com/ 사이트의 일부로 격리될 수 있습니다.

해당 정책을 사용하면 쉼표로 구분된 목록에 있는 각 명명된 원본은 자체 프로세스에서 실행됩니다.

해당 정책을 사용하지 않으면 'IsolateOrigins' 및 'SitePerProcess' 기능을 모두 사용할 수 없습니다. 사용자는 계속 'IsolateOrigins' 정책을 사용하도록 명령줄 플래그를 통해 직접 설정할 수 있습니다.

해당 정책을 구성하지 않으면 사용자는 해당 설정을 변경할 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 문자열

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: IsolateOrigins
  - GP 이름: 특정 원본에 대해 사이트 격리 사용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: IsolateOrigins
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
"https://contoso.com/,https://fabrikam.com/"
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: IsolateOrigins
  - 예를 들어 값:
``` xml
<string>https://contoso.com/,https://fabrikam.com/</string>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="localprovidersenabled"></a>LocalProvidersEnabled

  #### <a name="allow-suggestions-from-local-providers"></a>로컬 공급자의 제안 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (83 이상)

  #### <a name="description"></a>설명

  Microsoft Edge의 주소 표시줄 및 자동 제안 목록에서 장치(로컬 공급자)에 대한 제안 공급자로부터 제안을 허용합니다. (예: 즐겨찾기 및 검색 기록)

해당 정책을 사용하면 로컬 공급자의 제안이 사용됩니다.

해당 정책을 사용하지 않으면 로컬 공급자의 제안이 사용되지 않습니다. 로컬 기록 및 로컬 즐겨찾기 제안이 표시되지 않습니다.

해당 정책을 구성하지 않으면 로컬 공급자의 제안이 허용되지만 사용자가 설정 토글 키를 사용하여 해당 사항을 변경할 수 있습니다.

해당 기능을 사용하지 않도록 정책이 적용된 경우 일부 기능을 사용할 수 없다는 점에 유의하세요. 예를 들어 [SavingBrowserHistoryDisabled](#savingbrowserhistorydisabled) 정책을 사용하도록 설정한 경우에는 검색 기록 제안을 사용할 수 없습니다.

해당 정책을 적용하려면 브라우저를 다시 시작해야 합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: LocalProvidersEnabled
  - GP 이름: 로컬 공급자의 제안 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: LocalProvidersEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: LocalProvidersEnabled
  - 예를 들어 값:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="managedconfigurationperorigin"></a>ManagedConfigurationPerOrigin

  #### <a name="sets-managed-configuration-values-for-websites-to-specific-origins"></a>웹 사이트의 관리되는 구성 값을 특정 원본으로 설정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 macOS 버전 90 이상

  #### <a name="description"></a>설명

  이 정책을 설정하면 주어진 원본에 대한 관리되는 구성 API의 반환 값이 정의됩니다.

 관리되는 구성 API는 navigator.device.getManagedConfiguration() javascript 호출을 통해 액세스할 수 있는 키-값 구성입니다. 이 API는 [WebAppInstallForceList를](#webappinstallforcelist) 통해 강제로 설치된 웹 응용 프로그램에 해당하는 원본에서만 사용할 수 있습니다.


  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - Dictionary

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ManagedConfigurationPerOrigin
  - GP 이름: 웹 사이트에 대한 관리되는 구성 값을 특정 원본으로 설정
  - GP 경로(필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로(권장): 해당 없음
  - 값 이름: ManagedConfigurationPerOrigin
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\ManagedConfigurationPerOrigin = [
  {
    "managed_configuration_hash": "asd891jedasd12ue9h", 
    "managed_configuration_url": "https://static.contoso.com/configuration.json", 
    "origin": "https://www.contoso.com"
  }, 
  {
    "managed_configuration_hash": "djio12easd89u12aws", 
    "managed_configuration_url": "https://static.contoso.com/configuration2.json", 
    "origin": "https://www.example.com"
  }
]
```

  ##### <a name="compact-example-value"></a>예제 값 압축:

  ```
  SOFTWARE\Policies\Microsoft\Edge\ManagedConfigurationPerOrigin = [{"managed_configuration_hash": "asd891jedasd12ue9h", "managed_configuration_url": "https://static.contoso.com/configuration.json", "origin": "https://www.contoso.com"}, {"managed_configuration_hash": "djio12easd89u12aws", "managed_configuration_url": "https://static.contoso.com/configuration2.json", "origin": "https://www.example.com"}]
  ```
  

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ManagedConfigurationPerOrigin
  - 값 예시:
``` xml
<key>ManagedConfigurationPerOrigin</key>
<array>
  <dict>
    <key>managed_configuration_hash</key>
    <string>asd891jedasd12ue9h</string>
    <key>managed_configuration_url</key>
    <string>https://static.contoso.com/configuration.json</string>
    <key>origin</key>
    <string>https://www.contoso.com</string>
  </dict>
  <dict>
    <key>managed_configuration_hash</key>
    <string>djio12easd89u12aws</string>
    <key>managed_configuration_url</key>
    <string>https://static.contoso.com/configuration2.json</string>
    <key>origin</key>
    <string>https://www.example.com</string>
  </dict>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="managedfavorites"></a>ManagedFavorites

  #### <a name="configure-favorites"></a>즐겨찾기 구성

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  관리된 즐겨찾기 목록을 구성합니다.

해당 정책에서 즐겨찾기 목록을 생성합니다. 각 즐겨찾기에는 즐겨찾기의 이름 및 대상이 포함된 "이름" 및 "URL" 키가 포함되어 있습니다. "URL" 키 없이 즐겨찾기를 정의하여 하위 폴더를 구성할 수 있지만 위에 정의된 대로 즐겨찾기 목록을 포함하는 추가 "하위" 키를 사용하여서도 하위 폴더를 구성할 수 있습니다. (일부는 다시 폴더가 될 수 있음) Microsoft Edge는 주소 표시줄을 통해 제출된 것처럼 불완전한 URL을 수정합니다. (예: "microsoft.com"이 "https://microsoft.com/"이 됨)

해당 즐겨찾기는 사용자가 수정할 수 없는 폴더에 배치됩니다. (하지만 사용자가 즐겨찾기 모음에서 해당 폴더를 숨기도록 선택할 수 있음) 기본적으로 폴더 이름은 "관리된 즐겨찾기"이지만 원하는 폴더 이름을 값으로 하는 “toplevel_name” 키를 포함하는 사전을 즐겨찾기 목록에 추가하여 이름을 변경할 수 있습니다.

관리된 즐겨찾기는 사용자 계정에 동기화되지 않으므로 확장을 사용하여 수정할 수 없습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - Dictionary

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ManagedFavorites
  - GP 이름: 즐겨찾기 구성
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: ManagedFavorites
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\ManagedFavorites = [
  {
    "toplevel_name": "My managed favorites folder"
  }, 
  {
    "name": "Microsoft", 
    "url": "microsoft.com"
  }, 
  {
    "name": "Bing", 
    "url": "bing.com"
  }, 
  {
    "children": [
      {
        "name": "Microsoft Edge Insiders", 
        "url": "www.microsoftedgeinsider.com"
      }, 
      {
        "name": "Microsoft Edge", 
        "url": "www.microsoft.com/windows/microsoft-edge"
      }
    ], 
    "name": "Microsoft Edge links"
  }
]
```

  ##### <a name="compact-example-value"></a>예제 값 압축:

  ```
  SOFTWARE\Policies\Microsoft\Edge\ManagedFavorites = [{"toplevel_name": "My managed favorites folder"}, {"name": "Microsoft", "url": "microsoft.com"}, {"name": "Bing", "url": "bing.com"}, {"children": [{"name": "Microsoft Edge Insiders", "url": "www.microsoftedgeinsider.com"}, {"name": "Microsoft Edge", "url": "www.microsoft.com/windows/microsoft-edge"}], "name": "Microsoft Edge links"}]
  ```
  

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ManagedFavorites
  - 예를 들어 값:
``` xml
<key>ManagedFavorites</key>
<array>
  <dict>
    <key>toplevel_name</key>
    <string>My managed favorites folder</string>
  </dict>
  <dict>
    <key>name</key>
    <string>Microsoft</string>
    <key>url</key>
    <string>microsoft.com</string>
  </dict>
  <dict>
    <key>name</key>
    <string>Bing</string>
    <key>url</key>
    <string>bing.com</string>
  </dict>
  <dict>
    <key>children</key>
    <array>
      <dict>
        <key>name</key>
        <string>Microsoft Edge Insiders</string>
        <key>url</key>
        <string>www.microsoftedgeinsider.com</string>
      </dict>
      <dict>
        <key>name</key>
        <string>Microsoft Edge</string>
        <key>url</key>
        <string>www.microsoft.com/windows/microsoft-edge</string>
      </dict>
    </array>
    <key>name</key>
    <string>Microsoft Edge links</string>
  </dict>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="managedsearchengines"></a>ManagedSearchEngines

  #### <a name="manage-search-engines"></a>검색 엔진 관리

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  최대 10 개의 검색 엔진 목록을 구성할 수 있습니다. 이 중 하나는 기본 검색 엔진으로 표시되어야 합니다.
인코딩을 지정하지 않아도 됩니다. Microsoft Edge 80에서 시작하는 suggest_url 매개 변수 및 image_search_url 매개 변수는 선택 사항입니다. 선택적 매개 변수인 image_search_post_params (쉼표로 구분된 이름/값 쌍으로 구성됨)는 Microsoft Edge 80에서 시작하여 사용할 수 있습니다.

Microsoft Edge 83에서 시작하는 allow_search_engine_discovery 선택적 매개 변수를 사용하여 검색 엔진을 검색할 수 있습니다. 해당 매개 변수는 목록의 첫 번째 항목이어야 합니다. allow_search_engine_discovery를 지정하지 않은 경우 기본적으로 검색 엔진을 검색할 수 없습니다. Microsoft Edge 84부터 이 정책을 권장 정책으로 설정하여 검색 공급자 검색을 허용할 수 있습니다. Allow_search_engine_discovery 선택적 매개 변수는 추가할 필요가 없습니다.

해당 정책을 사용하면 사용자가 목록에서 모든 검색 엔진을 추가, 제거 또는 변경할 수 없습니다. 사용자는 기본 검색 엔진을 목록의 모든 검색 엔진으로 설정할 수 있습니다.

해당 정책을 사용하지 않도록 설정하거나 구성하지 않으면 사용자는 검색 엔진 목록을 원하는 대로 변경할 수 있습니다.

[DefaultSearchProviderSearchURL](#defaultsearchprovidersearchurl) 정책이 설정된 경우 해당 정책(ManagedSearchEngines)은 무시됩니다. 해당 정책의 적용을 마치려면 사용자는 브라우저를 다시 시작해야 합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - Dictionary

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ManagedSearchEngines
  - GP 이름: 검색 엔진 관리
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: ManagedSearchEngines
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\ManagedSearchEngines = [
  {
    "allow_search_engine_discovery": true
  }, 
  {
    "is_default": true, 
    "keyword": "example1.com", 
    "name": "Example1", 
    "search_url": "https://www.example1.com/search?q={searchTerms}", 
    "suggest_url": "https://www.example1.com/qbox?query={searchTerms}"
  }, 
  {
    "image_search_post_params": "content={imageThumbnail},url={imageURL},sbisrc={SearchSource}", 
    "image_search_url": "https://www.example2.com/images/detail/search?iss=sbiupload", 
    "keyword": "example2.com", 
    "name": "Example2", 
    "search_url": "https://www.example2.com/search?q={searchTerms}", 
    "suggest_url": "https://www.example2.com/qbox?query={searchTerms}"
  }, 
  {
    "encoding": "UTF-8", 
    "image_search_url": "https://www.example3.com/images/detail/search?iss=sbiupload", 
    "keyword": "example3.com", 
    "name": "Example3", 
    "search_url": "https://www.example3.com/search?q={searchTerms}", 
    "suggest_url": "https://www.example3.com/qbox?query={searchTerms}"
  }, 
  {
    "keyword": "example4.com", 
    "name": "Example4", 
    "search_url": "https://www.example4.com/search?q={searchTerms}"
  }
]
```

  ##### <a name="compact-example-value"></a>예제 값 압축:

  ```
  SOFTWARE\Policies\Microsoft\Edge\ManagedSearchEngines = [{"allow_search_engine_discovery": true}, {"is_default": true, "keyword": "example1.com", "name": "Example1", "search_url": "https://www.example1.com/search?q={searchTerms}", "suggest_url": "https://www.example1.com/qbox?query={searchTerms}"}, {"image_search_post_params": "content={imageThumbnail},url={imageURL},sbisrc={SearchSource}", "image_search_url": "https://www.example2.com/images/detail/search?iss=sbiupload", "keyword": "example2.com", "name": "Example2", "search_url": "https://www.example2.com/search?q={searchTerms}", "suggest_url": "https://www.example2.com/qbox?query={searchTerms}"}, {"encoding": "UTF-8", "image_search_url": "https://www.example3.com/images/detail/search?iss=sbiupload", "keyword": "example3.com", "name": "Example3", "search_url": "https://www.example3.com/search?q={searchTerms}", "suggest_url": "https://www.example3.com/qbox?query={searchTerms}"}, {"keyword": "example4.com", "name": "Example4", "search_url": "https://www.example4.com/search?q={searchTerms}"}]
  ```
  

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ManagedSearchEngines
  - 예를 들어 값:
``` xml
<key>ManagedSearchEngines</key>
<array>
  <dict>
    <key>allow_search_engine_discovery</key>
    <true/>
  </dict>
  <dict>
    <key>is_default</key>
    <true/>
    <key>keyword</key>
    <string>example1.com</string>
    <key>name</key>
    <string>Example1</string>
    <key>search_url</key>
    <string>https://www.example1.com/search?q={searchTerms}</string>
    <key>suggest_url</key>
    <string>https://www.example1.com/qbox?query={searchTerms}</string>
  </dict>
  <dict>
    <key>image_search_post_params</key>
    <string>content={imageThumbnail},url={imageURL},sbisrc={SearchSource}</string>
    <key>image_search_url</key>
    <string>https://www.example2.com/images/detail/search?iss=sbiupload</string>
    <key>keyword</key>
    <string>example2.com</string>
    <key>name</key>
    <string>Example2</string>
    <key>search_url</key>
    <string>https://www.example2.com/search?q={searchTerms}</string>
    <key>suggest_url</key>
    <string>https://www.example2.com/qbox?query={searchTerms}</string>
  </dict>
  <dict>
    <key>encoding</key>
    <string>UTF-8</string>
    <key>image_search_url</key>
    <string>https://www.example3.com/images/detail/search?iss=sbiupload</string>
    <key>keyword</key>
    <string>example3.com</string>
    <key>name</key>
    <string>Example3</string>
    <key>search_url</key>
    <string>https://www.example3.com/search?q={searchTerms}</string>
    <key>suggest_url</key>
    <string>https://www.example3.com/qbox?query={searchTerms}</string>
  </dict>
  <dict>
    <key>keyword</key>
    <string>example4.com</string>
    <key>name</key>
    <string>Example4</string>
    <key>search_url</key>
    <string>https://www.example4.com/search?q={searchTerms}</string>
  </dict>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="maxconnectionsperproxy"></a>MaxConnectionsPerProxy

  #### <a name="maximum-number-of-concurrent-connections-to-the-proxy-server"></a>프록시 서버에 대한 최대 동시 연결 수

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  프록시 서버에 대한 최대 동시 연결 수를 지정합니다.

일부 프록시 서버는 클라이언트 당 많은 수의 동시 연결을 처리할 수 없습니다. 해당 정책을 더 낮은 값으로 설정하면 이를 해결할 수 있습니다.

해당 정책의 값은 100 보다 낮고 6 보다 커야 합니다. 기본값은 32입니다.

일부 웹 앱은 한 번에 여러 연결을 사용하는 것으로 알려져 있습니다. 32 아래로 최대 연결 수를 낮추면 해당 웹 앱 중 많은 앱이 열려있는 경우 브라우저 네트워킹 중단으로 이어질 수 있습니다.

해당 정책을 구성하지 않으면 기본값(32)이 사용됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: MaxConnectionsPerProxy
  - GP 이름: 프록시 서버에 대한 최대 동시 연결 수
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: MaxConnectionsPerProxy
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000020
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: MaxConnectionsPerProxy
  - 예를 들어 값:
``` xml
<integer>32</integer>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="mediaroutercastallowallips"></a>MediaRouterCastAllowAllIPs

  #### <a name="allow-google-cast-to-connect-to-cast-devices-on-all-ip-addresses"></a>모든 IP 주소의 캐스트 장치에 Google Cast 연결 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  해당 정책을 사용하면 Google Cast는 RFC1918/RFC4193 비공개 주소 뿐만 아니라 모든 IP 주소의 캐스트 장치에 연결할 수 있습니다.

해당 정책을 사용하지 않으면 Google Cast는 RFC1918/RFC4193 비공개 주소의 캐스트 장치에 연결이 제한됩니다.

해당 정책을 구성하지 않으면 Google Cast는 CastAllowAllIPs 기능을 사용하도록 설정하지 않은 경우 RFC1918/RFC4193 비공개 주소의 캐스트 장치에만 연결합니다.

[EnableMediaRouter](#enablemediarouter) 정책을 사용하지 않으면 해당 정책은 효과가 없습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: MediaRouterCastAllowAllIPs
  - GP 이름: 모든 IP 주소의 캐스트 장치에 Google Cast 연결 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: MediaRouterCastAllowAllIPs
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: MediaRouterCastAllowAllIPs
  - 예를 들어 값:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="metricsreportingenabled"></a>MetricsReportingEnabled

  #### <a name="enable-usage-and-crash-related-data-reporting-obsolete"></a>사용 현황 및 크래시 관련 데이터 보고 사용(사용되지 않음)

  
  >사용되지 않음: 이 정책은 사용되지 않으며 Microsoft Edge 88 이후로는 작동하지 않습니다.
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 macOS(77부터 88까지)

  #### <a name="description"></a>설명

  해당 정책은 더 이상 지원되지 않습니다. 이는 [DiagnosticData](#diagnosticdata)(Windows 7, Windows 8 및 macOS) 및 Win 10에서 원격 분석 허용([https://go.microsoft.com/fwlink/?linkid=2099569](https://go.microsoft.com/fwlink/?linkid=2099569))으로 대체됩니다.

이 정책은 Microsoft Edge에서 Microsoft로의 사용 현황 및 크래시 관련 데이터 보고를 사용하도록 설정합니다.

사용 현황 및 충돌 관련 데이터 보고를 Microsoft에 보내려면 이 정책을 사용하도록 설정합니다. 이 정책을 사용하지 않도록 설정하여 데이터를 Microsoft에 보내지 않도록 합니다. 두 경우 모두 사용자가 정책 설정을 변경하거나 재정의할 수 없습니다.

Windows 10에서 해당 정책을 구성하지 않으면 Microsoft Edge는 Windows 진단 데이터 설정의 기본값이 됩니다. 해당 정책을 사용하면 Microsoft Edge는 Windows 진단 데이터 설정이 고급 또는 전체로 설정된 경우에만 사용 현황 데이터를 전송합니다. 해당 정책을 사용하지 않으면 Microsoft Edge는 사용 현황 데이터를 전송하지 않습니다. 크래시 관련 데이터는 Windows 진단 데이터 설정에 따라 전송됩니다. Windows 진단 데이터 설정에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2099569](https://go.microsoft.com/fwlink/?linkid=2099569)을 참조하세요.

Windows 7, Windows 8 및 MacOS에서 해당 정책이 사용 현황 및 크래시 관련 데이터 전송을 제어합니다. 해당 정책을 구성하지 않으면 Microsoft Edge는 사용자의 기본 설정의 기본값이 됩니다.

이 정책을 사용하려면[SendSiteInfoToImproveServices](#sendsiteinfotoimproveservices) 을 사용으로 설정해야 합니다. [MetricsReportingEnabled](#metricsreportingenabled) 또는 [SendSiteInfoToImproveServices](#sendsiteinfotoimproveservices)가 구성되지 않았거나 사용하지 않도록 설정된 경우 이 데이터는 Microsoft로 보내지지 않습니다.

이 정책은 Microsoft Active Directory 도메인에 가입된 윈도우즈 인스턴스, 장치 관리를 위해 등록된 윈도우즈 10 Pro 또는 Enterprise 인스턴스 또는 MDM을 통해 관리되거나 MCX를 통해 도메인에 가입된 MacOS 인스턴스에서만 사용할 수 있습니다..

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: MetricsReportingEnabled
  - GP 이름: 사용 현황 및 크래시 관련 데이터 보고 사용(사용되지 않음)
  - GP 경로(필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: MetricsReportingEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: MetricsReportingEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="nativewindowocclusionenabled"></a>NativeWindowOcclusionEnabled

  #### <a name="enable-native-window-occlusion-deprecated"></a>네이티브 창 폐색 사용(사용되지 않음)

  >DEPRECATED: 해당 정책은 사용되지 않습니다. 현재 지원되고 있지만 이후 릴리스에서는 더 이상 사용되지 않을 예정입니다.
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 84 이상

  #### <a name="description"></a>설명

  이 정책은 더 이상 사용되지 않습니다. '[WindowOcclusionEnabled'](#windowocclusionenabled) 정책을 대신 사용하세요. Microsoft Edge 버전 92에서는 작동하지 않습니다.

Microsoft Edge에서 기본 창 폐색을 사용합니다.

해당 설정을 사용하면 CPU 및 전원 소비량을 줄일 수 있고 Microsoft Edge는 창이 다른 창에 포함된 경우 이를 감지하고 작업 페인팅 픽셀을 일시 중단합니다.

이 설정을 사용하지 않으면 Microsoft Edge는 창이 다른 창에 가려진 경우 이를 감지하지 않습니다.

이 정책을 설정하지 않으면 폐색 감지가 사용됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: NativeWindowOcclusionEnabled
  - GP 이름: 네이티브 창 폐색 사용(사용되지 않음)
  - GP 경로(필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: NativeWindowOcclusionEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="navigationdelayforinitialsitelistdownloadtimeout"></a>NavigationDelayForInitialSiteListDownloadTimeout

  #### <a name="set-a-timeout-for-delay-of-tab-navigation-for-the-enterprise-mode-site-list"></a>엔터프라이즈 모드 사이트 목록에 대한 탭 탐색 지연 시간 제한 설정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 84 이상

  #### <a name="description"></a>설명

  브라우저가 초기 엔터프라이즈 모드 사이트 목록을 다운로드할 때까지 탐색을 기다리는 Microsoft Edge 탭의 시간 제한을 몇 초 단위로 설정할 수 있습니다.

이 설정은 다음과 함께 작동합니다. [InternetExplorerIntegrationLevel](#internetexplorerintegrationlevel)은 'IEMode' 및 [InternetExplorerIntegrationSiteList](#internetexplorerintegrationsitelist) 정책으로 설정되어 있으며, 이 정책은 목록에 하나 이상의 항목이 있으며 [DelayNavigationsForInitialSiteListDownload](#delaynavigationsforinitialsitelistdownload)는 "모든 적합한 탐색" (1)으로 설정되어 있습니다.

탭은 엔터프라이즈 모드 사이트 목록이 다운로드될 때까지 이 시간 제한보다 오래 기다리지 않습니다. 시간 제한이 만료되면 브라우저가 엔터프라이즈 모드 사이트 목록을 다운로드하지 않은 경우 Microsoft Edge 탭은 계속 탐색합니다. 시간 제한 값은 1초~20초 사이입니다.

이 정책의 시간 제한을 기본값 2초보다 큰 값으로 설정하면 2초 후에 정보 표시줄이 사용자에게 표시됩니다. 정보 표시줄에는 엔터프라이즈 모드 사이트 목록 다운로드가 완료될 때까지 기다리는 것을 그만둘 수 있는 버튼이 있습니다.

이 정책을 구성하지 않으면 2초의 시간 제한 기본값이 사용됩니다. 이 기본값은 차후에 변경될 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: NavigationDelayForInitialSiteListDownloadTimeout
  - GP 이름: 엔터프라이즈 모드 사이트 목록에 대한 탭 탐색 지연 시간 제한 설정
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: NavigationDelayForInitialSiteListDownloadTimeout
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x0000000a
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="networkpredictionoptions"></a>NetworkPredictionOptions

  #### <a name="enable-network-prediction"></a>네트워크 예측 사용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  네트워크 예측을 사용하도록 설정하고 사용자가 해당 설정을 변경하지 못하도록 합니다.

이를 통해 DNS 프리페치, TCP 및 SSL 사전 연결 및 웹 페이지의 미리 렌더링을 제어합니다.

해당 정책을 구성하지 않으면 네트워크 예측이 사용되지만 사용자가 이를 변경할 수 있습니다.

정책 옵션 매핑:

* NetworkPredictionAlways (0) = 모든 네트워크 연결에 대한 네트워크 작업 예측

* NetworkPredictionWifiOnly (1) = 지원되지 않음. 이 값을 사용하는 경우 '모든 네트워크 연결에 대한 네트워크 작업을 예측’(0)이 설정된 것처럼 처리

* NetworkPredictionNever (2) = 모든 네트워크 연결에 대한 네트워크 작업 예측 안 함

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: NetworkPredictionOptions
  - GP 이름: 네트워크 예측 사용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: NetworkPredictionOptions
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000002
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: NetworkPredictionOptions
  - 예를 들어 값:
``` xml
<integer>2</integer>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="nonremovableprofileenabled"></a>NonRemovableProfileEnabled

  #### <a name="configure-whether-a-user-always-has-a-default-profile-automatically-signed-in-with-their-work-or-school-account"></a>사용자에게 항상 회사 또는 학교 계정으로 자동 로그인되는 기본 프로필이 있는지 여부 구성

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows (78 이상)

  #### <a name="description"></a>설명

  해당 정책은 사용자가 사용자의 회사 또는 학교 계정으로 자동 로그인되는 Microsoft Edge 프로필을 제거할 수 있는지 여부를 결정합니다.

해당 정책을 사용하면 Windows에서 사용자의 회사 또는 학교 계정으로 제거할 수 없는 프로필이 생성됩니다. 해당 프로필은 로그아웃하거나 제거할 수 없습니다. 프로필이 온-프레미스 계정 또는 OS 로그인 계정과 일치하는 Azure AD 계정으로 로그인한 경우에만 프로필이 제거될 수 없습니다.

해당 정책을 사용하지 않도록 설정하거나 구성하지 않으면 사용자는 Windows에서 사용자의 회사 또는 학교 계정으로 자동 로그인되는 프로필을 로그아웃하거나 제거할 수 있습니다.

브라우저 로그인을 구성하려면 [BrowserSignin](#browsersignin) 정책을 사용합니다.

해당 정책은 장치 관리에 등록된 Microsoft Active Directory 도메인, Windows 10 Pro나 엔터프라이즈 인스턴스에 가입한 Windows 인스턴스에만 사용할 수 있습니다.

Microsoft Edge 89 이후부터는 동기화가 사용하지 않도록 설정되어 있는 기존 온-프레미스 프로필이 있고 컴퓨터가 하이브리드 가입된 경우, 온-프레미스 프로필을 Azure AD 프로필에 자동 업그레이드하고, 새로운 제거 불가능한 Azure AD 프로필을 만드는 대신 해당 프로필을 제거 불가능하도록 만듭니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: NonRemovableProfileEnabled
  - GP 이름: 사용자에게 항상 회사 또는 학교 계정으로 자동 로그인되는 기본 프로필이 있는지 여부 구성
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: NonRemovableProfileEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="overridesecurityrestrictionsoninsecureorigin"></a>OverrideSecurityRestrictionsOnInsecureOrigin

  #### <a name="control-where-security-restrictions-on-insecure-origins-apply"></a>비보안 원본에 대해 보안 제한이 적용되는 위치 제어

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  비보안 원본에 대해 보안 제한이 적용되지 않는 원본(URL) 또는 호스트 이름 패턴(예: "*.contoso.com") 목록을 지정합니다.

해당 정책을 사용하면 TLS를 배포할 수 없는 레거시 응용 프로그램에 대해 허용된 출처를 지정하거나 내부 웹 개발용 스테이징 서버를 설정하여 개발자가 스테이징 서버에 TLS를 배포할 필요 없이 안전한 컨텍스트를 필요로 하는 기능을 테스트할 수 있습니다. 해당 정책은 또한 원본이 Omnibox에서 "보안되지 않음" 레이블이 지정되지 않도록 방지할 수 있습니다.

해당 정책에서 URL 목록을 설정하는 것은 같은 URL의 쉼표로 구분된 목록에서 '--unsafely-treat-insecure-origin-as-secure' 명령줄 플래그를 설정하는 것과 동일한 효과를 갖습니다. 해당 정책을 사용하면 명령줄 플래그를 재정의합니다.

보안 컨텍스트에 대한 자세한 내용은 https://www.w3.org/TR/secure-contexts/을 참조하세요.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: OverrideSecurityRestrictionsOnInsecureOrigin
  - GP 이름: 비보안 원본에 대해 보안 제한이 적용되는 위치 제어
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - Path (필수): SOFTWARE\정책\Microsoft\Edge\OverrideSecurityRestrictionsOnInsecureOrigin
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\OverrideSecurityRestrictionsOnInsecureOrigin\1 = "http://testserver.contoso.com/"
SOFTWARE\Policies\Microsoft\Edge\OverrideSecurityRestrictionsOnInsecureOrigin\2 = "*.contoso.com"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: OverrideSecurityRestrictionsOnInsecureOrigin
  - 예를 들어 값:
``` xml
<array>
  <string>http://testserver.contoso.com/</string>
  <string>*.contoso.com</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="paymentmethodqueryenabled"></a>PaymentMethodQueryEnabled

  #### <a name="allow-websites-to-query-for-available-payment-methods"></a>웹 사이트에서 사용 가능한 결제 방법을 쿼리하도록 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (80 이상)

  #### <a name="description"></a>설명

  웹 사이트에서 사용자가 결제 방법을 저장했는지에 대해 확인 여부를 설정할 수 있습니다.

해당 정책을 사용하지 않으면 PaymentRequest.canMakePayment 또는 PaymentRequest.hasEnrolledInstrument API를 사용하는 웹 사이트에서 사용 가능한 결제 방법이 없다는 알림이 표시됩니다.

해당 정책을 사용하거나 설정하지 않으면 웹 사이트에서 사용자가 결제 방법을 저장했는지 여부를 확인할 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: PaymentMethodQueryEnabled
  - GP 이름: 웹 사이트에서 사용 가능한 결제 방법을 쿼리하도록 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: PaymentMethodQueryEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: PaymentMethodQueryEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="personalizationreportingenabled"></a>PersonalizationReportingEnabled

  #### <a name="allow-personalization-of-ads-search-and-news-by-sending-browsing-history-to-microsoft"></a>Microsoft에 검색 기록을 보내어 광고, 검색, 뉴스를 개인 설정하도록 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (80 이상)

  #### <a name="description"></a>설명

  해당 정책을 사용하면 Microsoft에서 광고, 검색, 뉴스 및 기타 Microsoft 서비스를 개인 설정하는 데 사용되는 사용자의 Microsoft Edge 검색 기록을 모으지 못하도록 합니다.

해당 설정은 Microsoft 계정을 가진 사용자만 사용할 수 있습니다. 해당 설정은 하위 계정 또는 엔터프라이즈 계정에는 사용할 수 없습니다.

해당 정책을 사용하지 않도록 설정하면 사용자는 해당 설정을 변경하거나 재정의할 수 없습니다. 해당 정책을 사용하도록 설정하거나 구성하지 않으면 Microsoft Edge는 사용자의 기본 설정의 기본값이 됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: PersonalizationReportingEnabled
  - GP 이름: Microsoft에 검색 기록을 보내어 광고, 검색, 뉴스를 개인 설정하도록 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: PersonalizationReportingEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: PersonalizationReportingEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="pinningwizardallowed"></a>PinningWizardAllowed

  #### <a name="allow-pin-to-taskbar-wizard"></a>작업 표시줄에 고정 마법사 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows (80 이상)

  #### <a name="description"></a>설명

  Microsoft Edge는 작업 표시줄에 고정 마법사를 사용하여 사용자가 추천 사이트를 작업 표시줄에 고정할 수 있도록 합니다. 작업 표시줄에 고정 마법사 기능은 기본적으로 사용하도록 설정되어 있으며 설정 및 기타 메뉴를 통해 사용자가 액세스할 수 있습니다.

해당 정책을 사용하도록 설정하거나 구성하지 않으면 사용자는 설정 및 기타 메뉴에서 작업 표시줄에 고정 마법사를 호출할 수 있습니다. 마법사는 프로토콜 시작을 통해서도 호출할 수 있습니다.

해당 정책을 사용하지 않도록 설정하면 메뉴에서 작업 표시줄에 고정 마법사를 사용할 수 없으며 프로토콜 시작을 통해 호출할 수 없습니다.

작업 표시줄에 고정 마법사를 사용하거나 사용하지 않도록 설정하는 사용자 설정을 사용할 수 없습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: PinningWizardAllowed
  - GP 이름: 작업 표시줄에 고정 마법사 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: PinningWizardAllowed
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="proactiveauthenabled"></a>ProactiveAuthEnabled

  #### <a name="enable-proactive-authentication-deprecated"></a>자동 관리 인증 사용(사용하지 않음)

  >DEPRECATED: 해당 정책은 사용되지 않습니다. 현재 지원되고 있지만 이후 릴리스에서는 더 이상 사용되지 않을 예정입니다.
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  이 정책은 브라우저 로그인과는 독립적으로 작동하지 않기 때문에 더 이상 사용되지 않습니다. Microsoft Edge 버전 91에서 작동하지 않습니다. 브라우저 로그인을 구성하려면 [BrowserSignin](#browsersignin) 정책을 사용합니다.

Microsoft Edge에서 자동 관리 인증 설정 여부를 구성할 수 있습니다.

이 정책을 실행하면 Microsoft Edge는 브라우저에 로그인된 계정을 사용하여 웹 사이트 및 서비스에 대해 원활하게 인증하려고 합니다.

이 정책을 실행 중지하면 Microsoft Edge는 SSO(Single Sign-On)를 사용하여 웹 사이트 또는 서비스로 인증하려고 시도하지 않습니다. 엔터프라이즈 새 탭 페이지와 같은 인증된 환경은 작동하지 않습니다(예: 최근 및 권장 Office 문서를 사용할 수 없음).

해당 정책을 구성하지 않으면 자동 관리 인증이 설정됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ProactiveAuthEnabled
  - GP 이름: 자동 인증 사용(사용하지 않음)
  - GP 경로(필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: ProactiveAuthEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ProactiveAuthEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="promotionaltabsenabled"></a>PromotionalTabsEnabled

  #### <a name="enable-full-tab-promotional-content"></a>전체 탭 프로모션 콘텐츠 사용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  전체 탭 프로모션 또는 교육용 콘텐츠의 프레젠테이션을 제어합니다. 해당 설정은 사용자가 Microsoft Edge에 로그인하는 데 도움이 되는 시작 페이지의 프레젠테이션을 제어하고 기본 브라우저를 선택하거나 제품 기능에 대해 알아봅니다.

해당 정책을 사용하거나(True로 설정) 구성하지 않으면 Microsoft Edge에서 사용자에게 제품 정보를 제공하는 전체 탭 콘텐츠를 표시할 수 있습니다.

해당 정책을 사용하지 않으면(False로 설정) Microsoft Edge에서 사용자에게 전체 탭 콘텐츠를 표시할 수 없습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: PromotionalTabsEnabled
  - GP 이름: 전체 탭 프로모션 콘텐츠 사용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: PromotionalTabsEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: PromotionalTabsEnabled
  - 예를 들어 값:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="promptfordownloadlocation"></a>PromptForDownloadLocation

  #### <a name="ask-where-to-save-downloaded-files"></a>다운로드한 파일을 저장할 위치 묻기

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  다운로드하기 전에 파일을 저장할 위치에 대한 요청 여부를 설정합니다.

해당 정책을 사용하면 다운로드하기 전에 각 파일을 저장할 위치를 묻는 메시지가 사용자에게 표시됩니다. 구성하지 않으면 위치를 묻지 않고 파일은 자동으로 기본 위치에 저장됩니다.

해당 정책을 구성하지 않으면 사용자는 해당 설정을 변경할 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: PromptForDownloadLocation
  - GP 이름: 다운로드한 파일을 저장할 위치 묻기
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: PromptForDownloadLocation
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: PromptForDownloadLocation
  - 예를 들어 값:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="quicallowed"></a>QuicAllowed

  #### <a name="allow-quic-protocol"></a>QUIC 프로토콜 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  Microsoft Edge에서 QUIC 프로토콜을 사용할 수 있습니다.

해당 정책을 사용하도록 설정하거나 구성하지 않으면 QUIC 프로토콜을 사용할 수 있습니다.

해당 정책을 사용하지 않도록 설정하면 QUIC 프로토콜은 차단됩니다.

QUIC는 현재 TCP를 사용하는 웹 응용 프로그램의 성능을 개선할 수 있는 전송 계층 네트워크 프로토콜입니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: QuicAllowed
  - GP 이름: QUIC 프로토콜 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: QuicAllowed
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: QuicAllowed
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="quickviewofficefilesenabled"></a>QuickViewOfficeFilesEnabled

  #### <a name="manage-quickview-office-files-capability-in-microsoft-edge"></a>Microsoft Edge에서 QuickView Office 파일 기능 관리

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 macOS 버전 90 이상

  #### <a name="description"></a>설명

  사용자가 OneDrive 또는 SharePoint에 없는 Office 파일을 웹에서 볼 수 있는지 여부를 설정할 수 있습니다. (예: Word 문서, PowerPoint 프레젠테이션 및 Excel 스프레드시트)

이 정책을 사용하도록 설정하거나 구성하지 않은 경우 파일을 다운로드하는 대신 Office Viewer를 사용하여 Microsoft Edge에서 이러한 파일을 볼 수 있습니다.

이 정책을 사용하지 않도록 설정하면 이러한 파일이 다운로드되어 볼 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: QuickViewOfficeFilesEnabled
  - GP 이름: Microsoft Edge에서 QuickView Office 파일 관리
  - GP 경로(필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로(권장): 해당 없음
  - 값 이름: QuickViewOfficeFilesEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: QuickViewOfficeFilesEnabled
  - 값 예시:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="redirectsitesfrominternetexplorerpreventbhoinstall"></a>RedirectSitesFromInternetExplorerPreventBHOInstall

  #### <a name="prevent-install-of-the-bho-to-redirect-incompatible-sites-from-internet-explorer-to-microsoft-edge"></a>호환되지 않는 사이트를 Internet Explorer에서 Microsoft Edge로 리디렉션하는 BHO 설치 방지

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows (87 이상)

  #### <a name="description"></a>설명

  이 설정을 사용하여 최신 브라우저가 필요한 사이트에 대해 호환되지 않는 사이트를 Internet Explorer에서 Microsoft Edge로 리디렉션하는 BHO(브라우저 도우미 개체) 설치를 차단할지 여부를 지정할 수 있습니다.

이 정책을 사용하도록 설정하면 BHO가 설치되지 않습니다. 이미 설치되어 있는 경우, 다음 Microsoft Edge 업데이트에서 제거됩니다.

이 정책이 구성되지 않았거나 사용하지 않도록 설정된 경우 BHO가 설치됩니다.

BHO는 호환되지 않는 사이트의 리디렉션을 수행하는 데 필요하지만, 리디렉션의 발생 여부는 또한 [RedirectSitesFromInternetExplorerRedirectMode](#redirectsitesfrominternetexplorerredirectmode)가 제어합니다.

이 정책에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2141715](https://go.microsoft.com/fwlink/?linkid=2141715)을 참조

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: RedirectSitesFromInternetExplorerPreventBHOInstall
  - GP 이름: 호환되지 않는 사이트를 Internet Explorer에서 Microsoft Edge로 리디렉션하는 BHO 설치 방지
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: RedirectSitesFromInternetExplorerPreventBHOInstall
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="redirectsitesfrominternetexplorerredirectmode"></a>RedirectSitesFromInternetExplorerRedirectMode

  #### <a name="redirect-incompatible-sites-from-internet-explorer-to-microsoft-edge"></a>호환되지 않는 사이트를 Internet Explorer에서 Microsoft Edge로 리디렉션

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows (87 이상)

  #### <a name="description"></a>설명

  이 설정을 사용하면 Internet Explorer가 최신 브라우저를 필요로 하는 사이트로의 탐색을 Microsoft Edge로 리디렉션할지를 지정할 수 있습니다.

이 정책을 구성하지 않거나 "Sitelist"로 설정하면 M87부터는 Internet Explorer에서 최신 브라우저를 필요로 하는 사이트를 Microsoft Edge로 리디렉션합니다.

사이트가 Internet Explorer에서 Microsoft Edge로 리디렉션되는 경우, 이전 콘텐츠가 없는 경우에 해당 사이트를 로드하기 시작한 Internet Explorer 탭은 닫힙니다. 그렇지 않은 경우, 사이트를 Microsoft Edge로 리디렉션한 이유를 설명하는 Microsoft 도움말 페이지로 이동됩니다.

IE에서 사이트를 로드하기 위해 Microsoft Edge가 시작되는 경우, 해당 사이트는 최신 브라우저에서 가장 효과적으로 작동한다고 설명하는 정보 표시줄이 사용자에게 표시됩니다.

이 정책을 '사용 안 함'으로 설정하면 Internet Explorer에서 Microsoft Edge로 어떠한 트래픽도 리디렉션하지 않습니다.

이 정책에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2141715](https://go.microsoft.com/fwlink/?linkid=2141715)을 참조

정책 옵션 매핑:

* Disable(0) = 사용 안 함

* Sitelist(1) = 호환되지 않는 사이트의 목록을 기준으로 사이트를 리디렉션

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: RedirectSitesFromInternetExplorerRedirectMode
  - GP이름: 호환되지 않는 사이트를 Internet Explorer에서 Microsoft Edge로 리디렉션
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: RedirectSitesFromInternetExplorerRedirectMode
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="relaunchnotification"></a>RelaunchNotification

  #### <a name="notify-a-user-that-a-browser-restart-is-recommended-or-required-for-pending-updates"></a>사용자에게 보류 중인 업데이트에 대해 브라우저의 재시작을 권장하거나 필요함을 알림

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  보류 중인 업데이트를 적용하려면 Microsoft Edge를 재시작해야 함을 사용자에게 알립니다.

해당 정책을 구성하지 않으면 Microsoft Edge는 상단 메뉴 모음의 오른쪽 끝에 휴지통 아이콘을 추가하고 사용자에게 브라우저를 재시작하여 업데이트를 적용하라는 메시지를 표시합니다.

해당 정책을 사용하고 '권장'으로 설정하면 사용자에게 재시작을 권장하는 경고 메시지가 반복적으로 표시됩니다. 사용자는 해당 경고를 해제하고 재시작을 연기할 수 있습니다.

해당 정책을 '필수'로 설정하면 알림 기간이 지나자마자 브라우저를 자동으로 재시작하라는 경고 메시지가 반복적으로 표시됩니다. 기본 기간은 7일입니다. [RelaunchNotificationPeriod](#relaunchnotificationperiod) 정책을 사용하여 해당 기간을 구성할 수 있습니다.

브라우저가 다시 시작되면 사용자의 세션이 복원됩니다.

정책 옵션 매핑:

* 권장 (1) = 권장 - 재시작을 권장하는 반복적인 메시지를 사용자에게 표시

* 필수 (2) = 필수 - 재시작을 요구하는 반복적인 메시지를 사용자에게 표시

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: RelaunchNotification
  - GP 이름: 사용자에게 보류 중인 업데이트에 대해 브라우저의 재시작을 권장하거나 필요함을 알림
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: RelaunchNotification
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: RelaunchNotification
  - 예를 들어 값:
``` xml
<integer>1</integer>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="relaunchnotificationperiod"></a>RelaunchNotificationPeriod

  #### <a name="set-the-time-period-for-update-notifications"></a>업데이트 알림 기간 설정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  사용자에게 보류 중인 업데이트를 적용하기 위해 Microsoft Edge OS 장치를 재시작해야 한다는 알림을 받는 기간을 ms 단위로 설정할 수 있습니다.

해당 기간을 초과하면 사용자에게 업데이트가 필요하다는 알림을 반복적으로 표시합니다. Microsoft Edge의 경우 앱 메뉴가 변경되어 알림 기간의 1/3이 경과하면 재시작이 필요하다는 알림을 표시합니다. 해당 알림은 알림 기간의 2/3가 경과하면 색이 변경되고 전체 알림 기간이 경과하면 다시 색이 변경됩니다. [RelaunchNotification](#relaunchnotification) 정책에서 사용할 수 있는 추가 알림은 해당 일정과 동일합니다.

해당 정책을 설정하지 않으면 기본 기간은 6억 480만ms (1주)입니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: RelaunchNotificationPeriod
  - GP 이름: 업데이트 알림 기간 설정
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: RelaunchNotificationPeriod
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x240c8400
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: RelaunchNotificationPeriod
  - 예를 들어 값:
``` xml
<integer>604800000</integer>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="renderercodeintegrityenabled"></a>RendererCodeIntegrityEnabled

  #### <a name="enable-renderer-code-integrity"></a>렌더러 코드 무결성 사용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows (78 이상)

  #### <a name="description"></a>설명

  정책을 사용으로 설정하거나 설정하지 않은 채로 두면 렌더러 코드 무결성이 켜집니다.
정책을 사용 안함으로 설정하면, 알 수 없는 잠재적으로 적대적인 코드가 Microsoft Edge의 렌더러 프로세스 내에서 로드될 수 있어 Microsoft Edge의 보안 및 안정성에 치명적인 영향을 미치게 됩니다. Microsoft Edge의 렌더러 프로세스 내에서 반드시 실행해야 하는 타사 소프트웨어와의 호환성 문제가 있는 경우에만 정책을 끕니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: RendererCodeIntegrityEnabled
  - GP 이름: 렌더러 코드 무결성 사용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: RendererCodeIntegrityEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="requireonlinerevocationchecksforlocalanchors"></a>RequireOnlineRevocationChecksForLocalAnchors

  #### <a name="specify-if-online-ocspcrl-checks-are-required-for-local-trust-anchors"></a>로컬 트러스트 앵커에 대한 온라인 OCSP/CRL 검사 필요 여부 지정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows (77 이상)

  #### <a name="description"></a>설명

  온라인 해지 검사(OCSP/CRL 검사)의 필요 여부를 제어합니다. Microsoft Edge에서 해지 상태 정보를 가져올 수 없는 경우 해당 인증서는 해지된 것으로("하드 오류") 처리됩니다.

해당 정책을 사용하면 Microsoft Edge에서 유효성 검사에 성공하고 로컬로 설치된 CA 인증서로 서명된 서버 인증서에 대해 해지 검사를 항상 수행합니다.

해당 정책을 구성하지 않거나 사용하지 않도록 설정하면 Microsoft Edge는 기존 온라인 해지 검사 설정을 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: RequireOnlineRevocationChecksForLocalAnchors
  - GP 이름: 로컬 트러스트 앵커에 대한 온라인 OCSP/CRL 검사 필요 여부 지정
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: RequireOnlineRevocationChecksForLocalAnchors
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="resolvenavigationerrorsusewebservice"></a>ResolveNavigationErrorsUseWebService

  #### <a name="enable-resolution-of-navigation-errors-using-a-web-service"></a>웹 서비스를 사용하여 탐색 오류 해결 설정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  Microsoft Edge에서 호텔 및 공항 Wi-fi와 같은 경우 네트워크 연결을 위해 웹 서비스에 데이터 없는 연결을 실행할 수 있습니다.

해당 정책을 사용하면 웹 서비스를 사용하여 네트워크 연결을 테스트합니다.

해당 정책을 사용하지 않으면 Microsoft Edge에서 기본 API를 사용하여 네트워크 연결 및 탐색 문제의 해결을 시도합니다.

**참고**: Windows 8 이상 버전의 Windows를 제외하고 Microsoft Edge는 *항상* 기본 API를 사용하여 연결 문제를 해결합니다.

해당 정책을 구성하지 않으면 Microsoft Edge에서는 edge://settings/privacy의 서비스에 설정된 사용자 선호도를 고려합니다.
특히 사용자가 설정하거나 해제할 수 있는 **탐색 오류를 해결하는 데 도움이 되는 웹 서비스 사용** 토글이 있습니다. 해당 정책(ResolveNavigationErrorsUseWebService)을 사용하도록 설정한 경우 **탐색 오류를 해결하는 데 도움이 되는 웹 서비스 사용** 설정이 켜져 있지만 사용자는 토글을 사용하여 해당 설정을 변경할 수 없습니다. 해당 정책을 사용하지 않도록 설정한 경우 **탐색 오류를 해결하는 데 도움이 되는 웹 서비스 사용** 설정이 꺼져 있고 사용자는 토글을 사용하여 해당 설정을 변경할 수 없습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ResolveNavigationErrorsUseWebService
  - GP 이름: 웹 서비스를 사용하여 탐색 오류 해결 설정
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: ResolveNavigationErrorsUseWebService
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ResolveNavigationErrorsUseWebService
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="restrictsignintopattern"></a>RestrictSigninToPattern

  #### <a name="restrict-which-accounts-can-be-used-as-microsoft-edge-primary-accounts"></a>Microsoft Edge 기본 계정으로 사용할 수 있는 계정 제한

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  Microsoft Edge에서 브라우저 기본 계정으로 설정할 수 있는 계정을 결정합니다. (동기화 옵트인 흐름 중에 선택한 계정)

사용자가 해당 패턴과 일치하지 않는 사용자 이름을 사용하여 브라우저 기본 계정을 구성하려고 하면 해당 계정이 차단되고 해당 오류 메시지가 표시됩니다. 패턴에 대한 Perl 스타일 정규식을 사용하여 여러 계정과 일치하도록 이 정책을 구성할 수 있습니다. 패턴 일치는 대/소문자를 구분합니다. 사용되는 정규식 규칙에 대한 자세한 내용은 https://go.microsoft.com/fwlink/p/?linkid=2133903을(를) 참조하세요.

해당 정책을 구성하지 않거나 공백으로 두면 사용자는 모든 계정을 Microsoft Edge의 브라우저 기본 계정으로 설정할 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: RestrictSigninToPattern
  - GP 이름: Microsoft Edge 기본 계정으로 사용할 수 있는 계정 제한
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: RestrictSigninToPattern
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
".*@contoso.com"
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: RestrictSigninToPattern
  - 예를 들어 값:
``` xml
<string>.*@contoso.com</string>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="roamingprofilelocation"></a>RoamingProfileLocation

  #### <a name="set-the-roaming-profile-directory"></a>로밍 프로필 디렉터리 설정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 85 이상

  #### <a name="description"></a>설명

  프로필의 로밍 복사본을 저장하는 데 사용할 디렉터리를 구성합니다.

이 정책을 활성화하고 [RoamingProfileSupportEnabled](#roamingprofilesupportenabled) 정책을 사용하도록 설정한 경우 Microsoft Edge는 제공된 디렉터리를 사용하여 프로필의 로밍 복사본을 저장합니다. [RoamingProfileSupportEnabled](#roamingprofilesupportenabled) 정책을 사용하지 않도록 설정하거나 구성하지 않으면 이 정책에 저장된 값이 사용되지 않습니다.

사용할 수 있는 변수의 목록은 [https://go.microsoft.com/fwlink/?linkid=2095041](https://go.microsoft.com/fwlink/?linkid=2095041)을(를) 참조하세요.

이 정책을 구성하지 않으면 기본 로밍 프로필 경로가 사용됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 문자열

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: RoamingProfileLocation
  - GP 이름: 로밍 프로필 디렉터리 설정
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: RoamingProfileLocation
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
"${roaming_app_data}\\edge-profile"
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="roamingprofilesupportenabled"></a>RoamingProfileSupportEnabled

  #### <a name="enable-using-roaming-copies-for-microsoft-edge-profile-data"></a>Microsoft Edge 프로필 데이터에 대한 로밍 복사본을 사용할 수 있도록 설정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 85 이상

  #### <a name="description"></a>설명

  Windows에서 로밍 프로필을 사용하려면 이 정책을 사용합니다. Microsoft Edge 프로필(즐겨찾기 및 기본 설정)에 저장된 설정은 로밍 사용자 프로필 폴더(또는 [RoamingProfileLocation](#roamingprofilelocation) 정책을 통해 관리자가 지정한 위치)에 저장된 파일에도 저장됩니다.

이 정책을 사용하지 않도록 설정하거나 구성하지 않으면 정규 로컬 프로필만 사용됩니다.

[SyncDisabled](#syncdisabled)는 클라우드 동기화만 사용하지 않도록 설정하며 이 정책에 영향을 끼치지 않습니다.

로밍 사용자 프로필 사용에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2150058](https://go.microsoft.com/fwlink/?linkid=2150058)을(를) 참조하세요.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: RoamingProfileSupportEnabled
  - GP 이름: Microsoft Edge 프로필 데이터에 대한 로밍 복사본을 사용할 수 있도록 설정
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: RoamingProfileSupportEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="runallflashinallowmode"></a>RunAllFlashInAllowMode

  #### <a name="extend-adobe-flash-content-setting-to-all-content-obsolete"></a>Adobe Flash 콘텐츠 설정을 모든 콘텐츠로 확장(obsolete)

  
  >OBSOLETE: 이 정책은 더 이상 사용되지 않으며 Microsoft Edge 87 이후에는 작동하지 않습니다.
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 macOS(77부터 87까지)

  #### <a name="description"></a>설명

  Flash가 Microsoft Edge에서 더 이상 지원되지 않으므로 이 정책이 적용되지 않습니다.

해당 정책을 사용하면 사용자 또는 엔터프라이즈 정책에 따라 콘텐츠 설정에서 Adobe Flash를 허용하도록 설정된 웹 사이트에 포함된 모든 Adobe Flash 콘텐츠가 실행됩니다. 여기에는 다른 원본 및/또는 작은 콘텐츠의 콘텐츠가 포함됩니다.

Adobe Flash를 실행할 수 있는 웹 사이트를 제어하려면 [DefaultPluginsSetting](#defaultpluginssetting), [PluginsAllowedForUrls](#pluginsallowedforurls) 및 [PluginsBlockedForUrls](#pluginsblockedforurls) 정책의 사양을 참조하세요.

해당 정책을 사용하지 않도록 설정하거나 구성하지 않으면 다른 원본 (바로 위에 언급 된 세 가지 정책에 지정되지 않은 사이트) 또는 작은 콘텐츠에 있는 Adobe Flash 콘텐츠가 차단될 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: RunAllFlashInAllowMode
  - GP 이름: Adobe Flash 콘텐츠 설정을 모든 콘텐츠로 확장(obsolete)
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: RunAllFlashInAllowMode
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: RunAllFlashInAllowMode
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="sslerroroverrideallowed"></a>SSLErrorOverrideAllowed

  #### <a name="allow-users-to-proceed-from-the-https-warning-page"></a>HTTPS 경고 페이지에서 사용자가 계속할 수 있도록 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  Microsoft Edge에서 사용자가 SSL 오류가 있는 사이트를 방문할 때 경고 페이지를 표시합니다.

해당 정책을 사용하거나 구성하지 않으면(기본값) 사용자는 해당 경고 페이지를 클릭할 수 있습니다.

해당 정책을 사용하지 않으면 사용자는 경고 페이지를 클릭할 수 없습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: SSLErrorOverrideAllowed
  - GP 이름: HTTPS 경고 페이지에서 사용자가 계속할 수 있도록 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: SSLErrorOverrideAllowed
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: SSLErrorOverrideAllowed
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="sslerroroverrideallowedfororigins"></a>SSLErrorOverrideAllowedForOrigins

  #### <a name="allow-users-to-proceed-from-the-https-warning-page-for-specific-origins"></a>사용자가 특정 출처에 대한 HTTPS 경고 페이지에서 계속하도록 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 macOS 버전 90 이상

  #### <a name="description"></a>설명

  Microsoft Edge는 사용자가 SSL 오류가 있는 사이트를 방문할 때 경고 페이지를 표시합니다.

[SSLErrorOverrideAllowed](#sslerroroverrideallowed) 정책을 사용하거나 구성하지 않으면 이 정책은 아무 것도 수행하지 않습니다.

[SSLErrorOverrideAllowed](#sslerroroverrideallowed) 정책을 사용하지 않은 경우 이 정책을 구성하면 사용자가 SSL 오류 페이지를 통해 계속 클릭할 수 있는 사이트의 원본 패턴 목록을 구성할 수 있습니다. 사용자는 이 목록에 없는 원본에서 SSL 오류 페이지를 클릭할 수 없습니다.

이 정책을 구성하지 않으면 [SSLErrorOverrideAllowed](#sslerroroverrideallowed) 정책이 모든 사이트에 적용됩니다.

유효한 원본 패턴에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322) 을 참조하세요. *(별표)는 이 정책에 허용되는 값이 아닙니다. 이 정책은 원본 기준으로만 일치하므로 URL 패턴의 모든 경로나 쿼리는 무시됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>ADMX(그룹 정책) 정보

  - GP 고유 이름: SSLErrorOverrideAllowedForOrigins
  - GP 이름: 사용자가 특정 출처에 대한 HTTPS 경고 페이지에서 계속할 수 있도록 허용
  - GP 경로(필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로(필수): SOFTWARE\Policies\Microsoft\Edge\SSLErrorOverrideAllowedForOrigins
  - 경로(권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\SSLErrorOverrideAllowedForOrigins\1 = "https://www.example.com"
SOFTWARE\Policies\Microsoft\Edge\SSLErrorOverrideAllowedForOrigins\2 = "[*.]example.edu"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: SSLErrorOverrideAllowedForOrigins
  - 예제 값:
``` xml
<array>
  <string>https://www.example.com</string>
  <string>[*.]example.edu</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="sslversionmin"></a>SSLVersionMin

  #### <a name="minimum-tls-version-enabled-deprecated"></a>최소 TLS 버전 사용(사용되지 않음)

  >사용되지 않음: 해당 정책은 사용되지 않습니다. 현재 지원되고 있지만 이후 릴리스에서는 더 이상 사용되지 않을 예정입니다.
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  버전 91(2021년 5월경)부터 Microsoft Edge에서 TLS 1.0/1.1 경고 표시 안 됨 지원이 제거되고 해당 정책이 작동하지 않게 됩니다.

지원되는 최소 버전의 TLS를 설정합니다. 해당 정책을 구성하지 않으면 Microsoft Edge에서 TLS 1.0 및 TLS 1.1에 대한 오류를 표시하지만 사용자는 무시할 수 있습니다.

이 정책을 사용하는 경우 Microsoft Edge는 지정한 버전보다 낮은 SSL/TLS 버전을 사용하지 않습니다. 인식할 수 없는 모든 값은 무시됩니다.

정책 옵션 매핑:

* TLSv1 (tls1) = TLS 1.0

* TLSv1.1 (tls1.1) = TLS 1.1

* TLSv1.2 (tls1.2) = TLS 1.2

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: SSLVersionMin
  - GP 이름: 최소 TLS 버전 사용(사용되지 않음)
  - GP 경로(필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: SSLVersionMin
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
"tls1"
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: SSLVersionMin
  - 예를 들어 값:
``` xml
<string>tls1</string>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="savecookiesonexit"></a>SaveCookiesOnExit

  #### <a name="save-cookies-when-microsoft-edge-closes"></a>Microsoft Edge가 닫힐 때 쿠키 저장

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (86 이상)

  #### <a name="description"></a>설명

  이 정책을 사용하면 브라우저를 닫을 때 지정된 쿠키 집합이 삭제되지 않습니다. 이 정책은 다음 경우에만 유효합니다.
- '쿠키 및 기타 사이트 데이터' 토글은 설정/개인 정보 및 서비스/닫기 또는 가까운 곳에서 검색 데이터 지우기에서 구성됩니다.
- [ClearBrowsingDataOnExit](#clearbrowsingdataonexit) 정책을 사용하고 있거나
- 정책 [DefaultCookiesSetting](#defaultcookiessetting)은 '세션 기간 동안 쿠키 유지'로 설정됩니다.

모든 세션에서 쿠키가 보존되는 URL 패턴을 기반으로 사이트 목록을 정의할 수 있습니다.

참고: 사용자가 계속해서 쿠키 사이트 목록을 편집하여 Url을 추가하거나 제거할 수 있습니다. 그러나 관리자가 추가한 Url은 제거할 수 없습니다.

이 정책을 사용하면 브라우저를 닫을 때 쿠키 목록이 지워지지 않습니다.

이 정책을 사용하지 않도록 설정하거나 구성하지 않으면 사용자의 개인 구성이 사용됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: SaveCookiesOnExit
  - GP 이름: Microsoft Edge가 닫힐 때 쿠키 저장
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\Policies\Microsoft\Edge\SaveCookiesOnExit
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\SaveCookiesOnExit\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\SaveCookiesOnExit\2 = "[*.]contoso.edu"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: SaveCookiesOnExit
  - 예를 들어 값:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="savingbrowserhistorydisabled"></a>SavingBrowserHistoryDisabled

  #### <a name="disable-saving-browser-history"></a>브라우저 기록 저장 사용 안 함

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  브라우저 기록 저장을 사용하지 않도록 설정하고 사용자가 해당 설정을 변경하지 못하도록 합니다.

해당 정책을 사용하면 검색 기록은 저장되지 않습니다. 또한 탭 동기화를 사용하지 않도록 설정합니다.

해당 정책을 사용하지 않도록 설정하거나 구성하지 않으면 검색 기록이 저장됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: SavingBrowserHistoryDisabled
  - GP 이름: 브라우저 기록 저장 사용 안 함
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: SavingBrowserHistoryDisabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: SavingBrowserHistoryDisabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="screencaptureallowed"></a>ScreenCaptureAllowed

  #### <a name="allow-or-deny-screen-capture"></a>화면 캡처 허용 또는 거부

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (83 이상)

  #### <a name="description"></a>설명

  해당 정책을 사용하거나 구성하지 않은 경우 웹 페이지에서 화면 캡처를 위한 화면 공유 API(예: getDisplayMedia() 또는 데스크톱 캡처 확장 API)를 사용할 수 있습니다.
해당 정책을 사용하지 않도록 설정하면 화면 공유 API가 호출되지 않습니다. 예를 들어 웹 기반 온라인 모임을 사용하는 경우 비디오나 화면 공유가 작동하지 않습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ScreenCaptureAllowed
  - GP 이름: 화면 캡처 허용 또는 거부
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: ScreenCaptureAllowed
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ScreenCaptureAllowed
  - 예를 들어 값:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="scrolltotextfragmentenabled"></a>ScrollToTextFragmentEnabled

  #### <a name="enable-scrolling-to-text-specified-in-url-fragments"></a>URL 조각에 지정된 텍스트로 스크롤 사용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (83 이상)

  #### <a name="description"></a>설명

  해당 기능을 사용하면 하이퍼링크 및 주소 표시줄 URL 탐색은 웹 페이지의 특정 텍스트를 대상으로 하고 웹 페이지 로드가 완료된 이후까지 스크롤됩니다.

해당 정책을 사용하거나 구성하지 않으면 URL을 통한 특정 텍스트 조각에 대해 웹 페이지 스크롤이 설정됩니다.

해당 정책을 사용하지 않으면 URL을 통한 특정 텍스트 조각에 대해 웹 페이지 스크롤이 설정되지 않습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ScrollToTextFragmentEnabled
  - GP 이름: URL 조각에 지정된 텍스트로 스크롤 사용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: ScrollToTextFragmentEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ScrollToTextFragmentEnabled
  - 예를 들어 값:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="searchsuggestenabled"></a>SearchSuggestEnabled

  #### <a name="enable-search-suggestions"></a>검색 제안 사용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  Microsoft Edge의 주소 표시줄 및 자동 제안 목록에서 웹 검색 제안을 사용하도록 설정하고 사용자가 해당 정책을 변경하지 못하도록 합니다.

해당 정책을 사용하면 웹 검색 제안이 사용됩니다.

해당 정책을 사용하지 않으면 웹 검색 제안이 사용되지 않지만 로컬 기록 및 로컬 즐겨찾기 제안이 계속 표시됩니다. 해당 정책을 사용하지 않으면 입력한 문자나 방문한 URL 모두 Microsoft에 대한 원격 분석에 포함되지 않습니다.

해당 정책이 설정되지 않으면 검색 제안이 사용하도록 설정되어 있지만 사용자가 이를 변경할 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: SearchSuggestEnabled
  - GP 이름: 검색 제안 사용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: SearchSuggestEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: SearchSuggestEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="securitykeypermitattestation"></a>SecurityKeyPermitAttestation

  #### <a name="websites-or-domains-that-dont-need-permission-to-use-direct-security-key-attestation"></a>직접 보안 키 증명을 사용하기 위한 권한이 필요 없는 웹 사이트 또는 도메인

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  보안 키의 증명 인증서 요청 시 명시적인 사용자 권한이 필요하지 않은 웹 사이트 및 도메인을 지정합니다. 또한 개인 증명을 사용할 수 있음을 나타내는 보안 키로 신호가 전송됩니다. 이를 제외하고 사이트에서 보안 키 증명을 요청할 때마다 사용자에게 메시지가 표시됩니다.

https://contoso.com/some/path)과 같은 사이트는 오직 U2F appID로 일치합니다. contoso.com과 같은 도메인은 오직 webauthn RP ID로 일치합니다. 지정된 사이트에 대한 U2F 및 webauthn API를 모두 처리하려면 appID URL과 도메인을 모두 포함해야 합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: SecurityKeyPermitAttestation
  - GP 이름: 직접 보안 키 증명을 사용하기 위한 권한이 필요 없는 웹 사이트 또는 도메인
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\SecurityKeyPermitAttestation
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\SecurityKeyPermitAttestation\1 = "https://contoso.com"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: SecurityKeyPermitAttestation
  - 예를 들어 값:
``` xml
<array>
  <string>https://contoso.com</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="sendintranettointernetexplorer"></a>SendIntranetToInternetExplorer

  #### <a name="send-all-intranet-sites-to-internet-explorer"></a>Internet Explorer에 모든 인트라넷 사이트 보내기

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows (77 이상)

  #### <a name="description"></a>설명

  Internet Explorer 모드에 대해 최적의 환경을 구성하는 방법에 대한 지침은 [https://go.microsoft.com/fwlink/?linkid=2094210](https://go.microsoft.com/fwlink/?linkid=2094210)을 참조하세요.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: SendIntranetToInternetExplorer
  - GP 이름: Internet Explorer에 모든 인트라넷 사이트 보내기
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: SendIntranetToInternetExplorer
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="sendsiteinfotoimproveservices"></a>SendSiteInfoToImproveServices

  #### <a name="send-site-information-to-improve-microsoft-services-obsolete"></a>Microsoft 서비스를 개선하기 위해 사이트 정보 전송(사용되지 않음)

  
  >사용되지 않음: 이 정책은 사용되지 않으며 Microsoft Edge 88 이후로는 작동하지 않습니다.
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 macOS(77부터 88까지)

  #### <a name="description"></a>설명

  해당 정책은 더 이상 지원되지 않습니다. 이는 [DiagnosticData](#diagnosticdata)(Windows 7, Windows 8 및 macOS) 및 Win 10에서 원격 분석 허용([https://go.microsoft.com/fwlink/?linkid=2099569](https://go.microsoft.com/fwlink/?linkid=2099569))으로 대체됩니다.

해당 정책은 Microsoft Edge에서 방문한 웹 사이트에 대한 정보를 Microsoft에 전송하여 검색과 같은 서비스를 개선하도록 허용합니다.

해당 정책을 사용하면 Microsoft Edge에서 방문하는 웹 사이트에 대한 정보를 Microsoft로 보낼 수 있습니다. 해당 정책을 사용하지 않으면 Microsoft Edge에서 방문하는 웹 사이트에 대한 정보를 Microsoft로 보낼 수 없습니다. 두 경우 모두 사용자가 정책 설정을 변경하거나 재정의할 수 없습니다.

Windows 10에서 해당 정책을 구성하지 않으면 Microsoft Edge는 Windows 진단 데이터 설정의 기본값이 됩니다. 해당 정책을 사용하도록 설정하면 Microsoft Edge는 Windows 진단 데이터 설정이 전체로 설정된 경우에만 방문하는 웹 사이트에 대한 정보를 보냅니다. 이 정책을 사용하지 않도록 설정하면 Microsoft Edge는 방문하는 웹 사이트에 대한 정보를 보내지 않습니다. Windows 진단 데이터 설정에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2099569](https://go.microsoft.com/fwlink/?linkid=2099569)을 참조하세요.

Windows 7, Windows8 및 macOS에서 해당 정책은 방문한 웹 사이트에 대한 정보 전송을 제어합니다. 해당 정책을 구성하지 않으면 Microsoft Edge는 사용자의 기본 설정의 기본값이 됩니다.

이 정책을 사용 하려면 [MetricsReportingEnabled](#metricsreportingenabled)을 사용으로 설정해야 합니다. [SendSiteInfoToImproveServices](#sendsiteinfotoimproveservices) 또는 [MetricsReportingEnabled](#metricsreportingenabled)가 구성되지 않았거나 사용하지 않도록 설정된 경우 이 데이터는 Microsoft로 보내지지 않습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: SendSiteInfoToImproveServices
  - GP 이름: Microsoft 서비스를 개선하기 위해 사이트 정보 보내기(사용되지 않음)
  - GP 경로(필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: SendSiteInfoToImproveServices
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: SendSiteInfoToImproveServices
  - 예를 들어 값:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="sensorsallowedforurls"></a>SensorsAllowedForUrls

  #### <a name="allow-access-to-sensors-on-specific-sites"></a>특정 사이트의 센서에 대한 액세스 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (86 이상)

  #### <a name="description"></a>설명

  URL 패턴을 기반으로 동작 및 광 센서와 같은 센서에 액세스하고 사용할 수 있는 사이트 목록을 정의합니다.

이 정책을 구성하지 않으면 [DefaultSensorsSetting](#defaultsensorssetting) 정책(설정된 경우) 또는 사용자의 개인 구성의 전역 기본값이 모든 사이트에 대해 사용됩니다.

이 정책과 일치하지 않는 URL 패턴의 경우 다음 우선 순위가 사용됩니다. [SensorsBlockedForUrls](#sensorsblockedforurls) 정책(일치하는 경우), [DefaultSensorsSetting](#defaultsensorssetting) 정책(설정된 경우), 또는 사용자 개인 설정.

이 정책에 정의된 URL 패턴은 [WebUsbAskForUrls](#sensorsblockedforurls) 정책에서 구성한 패턴과 충돌할 수 없습니다. URL을 허용하거나 차단할 수 없습니다.

유효한 URL 패턴에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)을(를) 참조하세요.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: SensorsAllowedForUrls
  - GP 이름: 특정 사이트의 센서에 대한 액세스 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로(필수): SOFTWARE\Policies\Microsoft\Edge\SensorsAllowedForUrls
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\SensorsAllowedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\SensorsAllowedForUrls\2 = "[*.]contoso.edu"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: SensorsAllowedForUrls
  - 예를 들어 값:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="sensorsblockedforurls"></a>SensorsBlockedForUrls

  #### <a name="block-access-to-sensors-on-specific-sites"></a>특정 사이트의 센서에 대한 액세스 차단

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (86 이상)

  #### <a name="description"></a>설명

  URL 패턴을 기반으로 동작 및 광 센서와 같은 센서에 액세스할 수 없는 사이트 목록을 정의합니다.

이 정책을 구성하지 않으면 [DefaultSensorsSetting](#defaultsensorssetting) 정책(설정된 경우) 또는 사용자의 개인 구성의 전역 기본값이 모든 사이트에 대해 사용됩니다.

이 정책과 일치하지 않는 URL 패턴의 경우 다음 우선 순위가 사용됩니다. [SensorsAllowedForUrls](#sensorsallowedforurls) 정책(일치하는 경우), [DefaultSensorsSetting](#defaultsensorssetting) 정책(설정된 경우), 또는 사용자 개인 설정.

이 정책에 정의된 URL 패턴은 [SensorsAllowedForUrls](#sensorsallowedforurls) 정책에서 구성한 패턴과 충돌할 수 없습니다. URL을 허용하거나 차단할 수 없습니다.

유효한 URL 패턴에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)을(를) 참조하세요.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: SensorsBlockedForUrls
  - GP 이름: 특정 사이트의 센서에 대한 액세스 차단
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\Policies\Microsoft\Edge\SensorsBlockedForUrls
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\SensorsBlockedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\SensorsBlockedForUrls\2 = "[*.]contoso.edu"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: SensorsBlockedForUrls
  - 예를 들어 값:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="serialaskforurls"></a>SerialAskForUrls

  #### <a name="allow-the-serial-api-on-specific-sites"></a>특정 사이트에서 직렬 API 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (86 이상)

  #### <a name="description"></a>설명

  사용자에게 직렬 포트에 대한 액세스를 요청할 수 있는 URL 패턴을 기반으로 사이트 목록을 정의합니다.

해당 정책을 구성하지 않으면 [DefaultSerialGuardSetting](#defaultserialguardsetting) 정책(설정된 경우) 또는 사용자의 개인 구성의 전역 기본 값이 모든 사이트에 대해 사용됩니다.

이 정책과 일치하지 않는 URL 패턴의 경우 다음 우선 순위가 사용됩니다. [SerialBlockedForUrls](#serialblockedforurls) 정책(일치하는 경우), [DefaultSerialGuardSetting](#defaultserialguardsetting) 정책(설정된 경우), 또는 사용자 개인 설정.

이 정책에 정의된 URL 패턴은 [SerialBlockedForUrls](#serialblockedforurls) 정책에서 구성한 패턴과 충돌할 수 없습니다. URL을 허용하거나 차단할 수 없습니다.

유효한 URL 패턴에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)을(를) 참조하세요.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: SerialAskForUrls
  - GP 이름: 특정 사이트에서 직렬 API 허용
  - GP 경로(필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\Policies\Microsoft\Edge\SerialAskForUrls
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\SerialAskForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\SerialAskForUrls\2 = "[*.]contoso.edu"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: SerialAskForUrls
  - 예를 들어 값:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="serialblockedforurls"></a>SerialBlockedForUrls

  #### <a name="block-the-serial-api-on-specific-sites"></a>특정 사이트에서 직렬 API 차단

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (86 이상)

  #### <a name="description"></a>설명

  사용자에게 직렬 포트에 대한 액세스를 요청할 수 없는 URL 패턴을 기반으로 사이트 목록을 정의합니다.

해당 정책을 구성하지 않으면 [DefaultSerialGuardSetting](#defaultserialguardsetting) 정책(설정된 경우) 또는 사용자의 개인 구성의 전역 기본 값이 모든 사이트에 대해 사용됩니다.

이 정책과 일치하지 않는 URL 패턴의 경우 다음 우선 순위가 사용됩니다. [SerialAskForUrls](#serialaskforurls) 정책(일치하는 경우), [DefaultSerialGuardSetting](#defaultserialguardsetting) 정책(설정된 경우), 또는 사용자 개인 설정.

이 정책의 URL 패턴은 [SerialAskForUrls](#serialaskforurls) 정책에서 구성한 패턴과 충돌할 수 없습니다. URL을 허용하거나 차단할 수 없습니다.

유효한 URL 패턴에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)을(를) 참조하세요.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: SerialBlockedForUrls
  - GP 이름: 특정 사이트에서 직렬 API 차단
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\Policies\Microsoft\Edge\SerialBlockedForUrls
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\SerialBlockedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\SerialBlockedForUrls\2 = "[*.]contoso.edu"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: SerialBlockedForUrls
  - 예를 들어 값:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="showmicrosoftrewards"></a>ShowMicrosoftRewards

  #### <a name="show-microsoft-rewards-experiences"></a>Microsoft Rewards 환경 표시

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS 88 이상

  #### <a name="description"></a>설명

  Microsoft Rewards 환경 및 알림을 표시합니다.
이 정책을 활성화한 경우:
   - 검색에서 Microsoft 계정 사용자(Azure AD 계정 제외)는 Microsoft Edge 사용자 프로필에서 Microsoft Rewards 경험을 볼 수 있습니다.
   - Microsoft Edge 설정에서 Microsoft Rewards를 사용하도록 설정하는 설정이 활성화되고 켜집니다.

이 정책을 비활성화하는 경우:
   - 검색에서 Microsoft 계정 사용자(Azure AD 계정 제외)는 Microsoft Edge 사용자 프로필에서 Microsoft Rewards 경험을 볼 수 없습니다.
   - Microsoft Edge 설정에서 Microsoft Rewards를 사용하지 않도록 설정되고 꺼집니다.

이 정책을 구성하지 않은 경우:
   - 검색에서 Microsoft 계정 사용자(Azure AD 계정 제외)는 Microsoft Edge 사용자 프로필에서 Microsoft Rewards 경험을 볼 수 있습니다.
   - Microsoft Edge 설정에서 Microsoft Rewards를 사용하도록 설정하는 설정이 활성화되고 켜집니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ShowMicrosoftRewards
  - GP 이름: Microsoft Rewards 환경 표시
  - GP 경로(필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로(권장): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 값 이름: ShowMicrosoftRewards
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ShowMicrosoftRewards
  - 값 예시:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="showofficeshortcutinfavoritesbar"></a>ShowOfficeShortcutInFavoritesBar

  #### <a name="show-microsoft-office-shortcut-in-favorites-bar-deprecated"></a>즐겨 찾기 모음에 Microsoft Office 바로 가기 표시(사용되지 않음)

  >DEPRECATED: 해당 정책은 사용되지 않습니다. 현재 지원되고 있지만 이후 릴리스에서는 더 이상 사용되지 않을 예정입니다.
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  이 정책은 운영 요구 사항의 변경 때문에 예상대로 작동하지 않습니다. Therefore it's deprecated and should not be used.

즐겨찾기 모음에서 Office.com에 대한 바로 가기 포함 여부를 지정합니다. Microsoft Edge에 로그인한 사용자의 경우 바로 가기는 사용자를 Microsoft Office 앱과 문서로 이동시킵니다. 해당 정책을 사용하거나 구성하지 않으면 사용자는 즐겨찾기 모음 상황에 맞는 메뉴에서 토글을 변경하여 바로 가기 표시 여부를 선택할 수 있습니다.
이 정책을 사용하지 않으면 바로 가기가 표시되지 않습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ShowOfficeShortcutInFavoritesBar
  - GP 이름: 즐겨찾기 모음에 Microsoft Office 바로 가기 표시(사용되지 않음)
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: ShowOfficeShortcutInFavoritesBar
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ShowOfficeShortcutInFavoritesBar
  - 예를 들어 값:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="showrecommendationsenabled"></a>ShowRecommendationsEnabled

  #### <a name="allow-recommendations-and-promotional-notifications-from-microsoft-edge"></a>Microsoft Edge의 추천 및 홍보 알림 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 macOS(89 이상)

  #### <a name="description"></a>설명

  이 정책 설정을 통해 직원이 Microsoft Edge에서 권장 사항 및 제품 지원 알림을 받을지 여부를 결정할 수 있습니다.

이 설정을 사용하도록 설정하거나 구성하지 않은 경우 직원은 Microsoft Edge에서 추천/알림을 받게 됩니다.

이 설정을 사용하지 않도록 설정하면 직원은 Microsoft Edge에서 추천/알림을 받지 않습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: ShowRecommendationsEnabled
  - GP 이름: Microsoft Edge의 권장 사항 및 홍보 알림 허용
  - GP 경로(필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로(권장): 해당 없음
  - 값 이름: ShowRecommendationsEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: ShowRecommendationsEnabled
  - 값 예시:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="signedhttpexchangeenabled"></a>SignedHTTPExchangeEnabled

  #### <a name="enable-signed-http-exchange-sxg-support"></a>SXG(Signed HTTP Exchange) 지원 사용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (78 이상)

  #### <a name="description"></a>설명

  SXG(Signed HTTP Exchange) 지원을 사용하도록 설정합니다.

해당 정책을 설정하지 않거나 사용하면 Microsoft Edge에서 SXG(Signed HTTP Exchange)로 서비스된 웹 콘텐츠를 허용합니다.

해당 정책을 사용하지 않으면 SXG(Signed HTTP Exchange)를 로드할 수 없습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: SignedHTTPExchangeEnabled
  - GP 이름: SXG(Signed HTTP Exchange) 지원 사용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: SignedHTTPExchangeEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: SignedHTTPExchangeEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="siteperprocess"></a>SitePerProcess

  #### <a name="enable-site-isolation-for-every-site"></a>모든 사이트에 대해 사이트 격리 사용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  'SitePerProcess' 정책은 사용자가 모든 사이트를 격리하는 기본 동작을 옵트아웃하는 것을 차단하는 데 사용할 수 있습니다. [IsolateOrigins](#isolateorigins) 정책을 사용하여 세분화된 원본을 추가로 격리할 수도 있다는 점에 유의하세요.

해당 정책을 사용하면 사용자는 각 사이트가 자체 프로세스에서 실행하는 기본 동작을 옵트아웃할 수 없습니다.

해당 정책을 사용하지 않도록 설정하거나 구성하지 않으면 사용자는 사이트 격리를 옵트아웃할 수 있습니다.  정책을 사용하지 않도록 설정하거나 구성하지 않으면(예: edge://flags에서 "사이트 격리 사용 안함" 항목을 사용하여) 사이트 격리가 해제되지 않습니다.


  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: SitePerProcess
  - GP 이름: 모든 사이트에 대해 사이트 격리 사용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: SitePerProcess
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: SitePerProcess
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="smartactionsblocklist"></a>SmartActionsBlockList

  #### <a name="block-smart-actions-for-a-list-of-services"></a>서비스 목록에 대한 스마트 동작 차단

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 macOS(89 이상)

  #### <a name="description"></a>설명

  스마트 작업을 표시하지 않는 특정 서비스(예: PDF)를 나열합니다. (스마트 작업은 Microsoft Edge의 전체 및 미니 상황에 맞는 메뉴에서 사용할 수 있는 "정의"와 같은 작업입니다.)

정책을 사용하도록 설정하는 경우:
   - 미니 및 전체 상황에 맞는 메뉴의 스마트 작업은 해당 목록과 일치하는 서비스의 모든 프로필에 대해 사용하지 않도록 설정됩니다.
   - 사용자는 주어진 목록과 일치하는 서비스에 대한 텍스트 선택에서 미니 및 전체 상황에 맞는 메뉴에 스마트 작업이 표시되지 않습니다.
   - Microsoft Edge 설정에서 미니 및 전체 상황에 맞는 메뉴의 스마트 작업은 해당 목록과 일치하는 서비스에 대해 사용하지 않도록 설정됩니다.

해당 정책을 사용하지 않도록 설정하거나 구성하지 않은 경우
   - 미니 및 전체 상황에 맞는 메뉴의 스마트 작업은 모든 프로필에 대해 사용하도록 설정됩니다.
   - 사용자는 텍스트 선택 시 최소 및 전체 컨텍스트 메뉴에서 스마트 작업을 볼 수 있습니다.
   - Microsoft Edge 설정에서 미니 및 전체 상황에 맞는 메뉴의 스마트 작업이 활성화됩니다.

정책 옵션 매핑:

* smart_actions_pdf (smart_actions_pdf) = PDF의 스마트 작업

이 정책을 구성할 때 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: SmartActionsBlockList
  - GP 이름: 서비스 목록에 대한 스마트 동작 차단
  - GP 경로(필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로(필수): SOFTWARE\Policies\Microsoft\Edge\SmartActionsBlockList
  - 경로 (권장): SOFTWARE\정책SOFTWARE\Policies\Microsoft\Edge\Recommended\SmartActionsBlockList
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\SmartActionsBlockList\1 = "smart_actions_pdf"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: SmartActionsBlockList
  - 예를 들어 값:
``` xml
<array>
  <string>smart_actions_pdf</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="speechrecognitionenabled"></a>SpeechRecognitionEnabled

  #### <a name="configure-speech-recognition"></a>Configure Speech Recognition

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - On Windows and macOS since 87 or later

  #### <a name="description"></a>설명

  Set whether websites can use the W3C Web Speech API to recognize speech from the user. The Microsoft Edge implementation of the Web Speech API uses Azure Cognitive Services, so voice data will leave the machine.

If you enable or don't configure this policy, web-based applications that use the Web Speech API can use Speech Recognition.

If you disable this policy, Speech Recognition is not available through the Web Speech API.

Read more about this feature here: SpeechRecognition API: [https://go.microsoft.com/fwlink/?linkid=2143388](https://go.microsoft.com/fwlink/?linkid=2143388) Cognitive Services: [https://go.microsoft.com/fwlink/?linkid=2143680](https://go.microsoft.com/fwlink/?linkid=2143680)

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP unique name: SpeechRecognitionEnabled
  - GP name: Configure Speech Recognition
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - Value Name: SpeechRecognitionEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - Preference Key Name: SpeechRecognitionEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="spellcheckenabled"></a>SpellcheckEnabled

  #### <a name="enable-spellcheck"></a>맞춤법 검사 사용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  해당 정책을 사용하도록 설정하거나 구성하지 않으면 사용자는 맞춤법 검사를 사용할 수 있습니다.

해당 정책을 사용하지 않으면 사용자는 맞춤법 검사를 사용할 수 없으며 [SpellcheckLanguage](#spellchecklanguage) 및 [SpellcheckLanguageBlocklist](#spellchecklanguageblocklist) 정책도 사용할 수 없습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: SpellcheckEnabled
  - GP 이름: 맞춤법 검사 사용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: SpellcheckEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: SpellcheckEnabled
  - 예를 들어 값:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="spellchecklanguage"></a>SpellcheckLanguage

  #### <a name="enable-specific-spellcheck-languages"></a>특정 맞춤법 검사 언어 사용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows (77 이상)

  #### <a name="description"></a>설명

  맞춤법 검사에 여러 언어를 사용하도록 설정합니다. 인식할 수 없는 사용자 지정 언어는 무시됩니다.

해당 정책을 사용하면 지정된 언어 뿐만 아니라 사용자가 사용할 수 있는 모든 언어에 대해 맞춤법 검사를 사용할 수 있습니다.

해당 정책을 구성하지 않거나 사용하지 않도록 설정하면 사용자의 맞춤법 검사 기본 설정이 변경되지 않습니다.

[SpellcheckEnabled](#spellcheckenabled) 정책을 사용하지 않도록 설정하면 해당 정책은 효과가 없습니다.

'SpellcheckLanguage’ 및 [SpellcheckLanguageBlocklist](#spellchecklanguageblocklist) 정책 모두에 언어를 포함하는 경우 맞춤법 검사 언어를 사용할 수 있습니다.

지원 언어: af, bg, ca, cs, cy, da, de, el, en-AU, en-CA, en-GB, en-US, es, es-419, es-AR, es-ES, es-MX, es-US, et, fa, fo, fr, he, hi, hr, hu, id, it, ko, lt, lv, nb, nl, pl, pt-BR, pt-PT, ro, ru, sh, sk, sl, sq, sr, sv, ta, tg, tr, uk, vi.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: SpellcheckLanguage
  - GP 이름: 특정 맞춤법 검사 언어 사용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\SpellcheckLanguage
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\SpellcheckLanguage\1 = "fr"
SOFTWARE\Policies\Microsoft\Edge\SpellcheckLanguage\2 = "es"

```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="spellchecklanguageblocklist"></a>SpellcheckLanguageBlocklist

  #### <a name="force-disable-spellcheck-languages"></a>맞춤법 검사 언어 강제 사용 해제

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows (78 이상)

  #### <a name="description"></a>설명

  맞춤법 검사 언어를 강제로 사용 해제합니다. 해당 목록에서 인식할 수 없는 언어는 무시됩니다.

해당 정책을 사용하면 지정된 언어에 대해 맞춤법 검사가 사용되지 않습니다. 사용자는 계속 목록에 없는 언어에 대해 맞춤법 검사를 사용하거나 사용하지 않도록 설정할 수 있습니다.

해당 정책을 설정하지 않거나 사용하지 않도록 설정하면 사용자의 맞춤법 검사 기본 설정이 변경되지 않습니다.

[SpellcheckEnabled](#spellcheckenabled) 정책을 사용하지 않도록 설정하면 해당 정책은 효과가 없습니다.

[SpellcheckLanguage](#spellchecklanguage) 및 ‘SpellcheckLanguageBlocklist’ 정책 모두에 언어를 포함하는 경우 맞춤법 검사 언어를 사용할 수 있습니다.

현재 지원 언어: af, bg, ca, cs, da, de, el, en-AU, en-CA, en-GB, en-US, es, es-419, es-AR, es-ES, es-MX, es-US, et, fa, fo, fr, he, hi, hr, hu, id, it, ko, lt, lv, nb, nl, pl, pt-BR, pt-PT, ro, ru, sh, sk, sl, sq, sr, sv, ta, tg, tr, uk, vi.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: SpellcheckLanguageBlocklist
  - GP 이름: 맞춤법 검사 언어 강제 사용 해제
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\SpellcheckLanguageBlocklist
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\SpellcheckLanguageBlocklist\1 = "fr"
SOFTWARE\Policies\Microsoft\Edge\SpellcheckLanguageBlocklist\2 = "es"

```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="strictermixedcontenttreatmentenabled"></a>StricterMixedContentTreatmentEnabled

  #### <a name="enable-stricter-treatment-for-mixed-content-obsolete"></a>혼합 콘텐츠에 대해 더 엄격한 처리 사용(구식)

  
  >사용되지 않음: 이 정책은 더 이상 사용되지 않으며 Microsoft Edge 84 이상에서는 작동하지 않습니다.
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 macOS(81부터 84까지)

  #### <a name="description"></a>설명

  이 정책은 웹 콘텐츠가 더욱 엄격한 혼합 콘텐츠 처리와 호환되지 않는 것으로 확인된 경우, 엔터프라이즈에 웹 콘텐츠를 업데이트하기 위한 더 많은 시간을 주기 위한 단기 매커니즘이므로 작동하지 않습니다.

해당 정책은 브라우저에서 혼합 콘텐츠(HTTPS 사이트의 HTTP 콘텐츠)에 대한 처리를 제어합니다.

해당 정책을 True로 설정하거나 설정하지 않으면 오디오 및 비디오 혼합 콘텐츠는 자동으로 HTTPS(즉, 리소스를 HTTPS를 통해 사용할 수 없는 경우 대체 없이 URL이 HTTPS로 다시 작성됨)로 업그레이드되고 이미지 혼합 콘텐츠의 경우 URL 표시줄에 '안전하지 않음' 경고가 표시됩니다.

해당 정책을 False로 설정하면 오디오 및 비디오에 대한 자동 업그레이드를 사용할 수 없으며 이미지에 대해 경고가 표시되지 않습니다.

해당 정책은 오디오, 비디오, 이미지 외에 다른 유형의 혼합 콘텐츠에는 효과가 없습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: StricterMixedContentTreatmentEnabled
  - GP 이름: 혼합 콘텐츠에 대해 더 엄격한 처리 사용(구식)
  - GP 경로(필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: StricterMixedContentTreatmentEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: StricterMixedContentTreatmentEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="suppressunsupportedoswarning"></a>SuppressUnsupportedOSWarning

  #### <a name="suppress-the-unsupported-os-warning"></a>지원되지 않는 OS 경고 표시 안 함

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  더 이상 지원되지 않는 컴퓨터 또는 운영 체제에서 Microsoft Edge 실행 시 나타나는 경고를 표시하지 않습니다.

해당 정책이 False이거나 설정되지 않은 경우 지원되지 않는 컴퓨터 또는 운영 체제에 경고가 표시됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: SuppressUnsupportedOSWarning
  - GP 이름: 지원되지 않는 OS 경고 표시 안 함
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: SuppressUnsupportedOSWarning
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: SuppressUnsupportedOSWarning
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="syncdisabled"></a>SyncDisabled

  #### <a name="disable-synchronization-of-data-using-microsoft-sync-services"></a>Microsoft 동기화 서비스를 사용하여 데이터 동기화 사용 해제

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  Microsoft Edge에서 데이터 동기화를 사용하지 않도록 설정합니다. 해당 정책은 또한 동기화 동의 확인 프롬프트가 나타나지 않도록 합니다.

이 정책은 클라우드 동기화만 사용하지 않도록 설정하며 [RoamingProfileSupportEnabled](#roamingprofilesupportenabled) 정책에 영향을 미치지 않습니다.

해당 정책을 설정하지 않거나 권장대로 적용하면 사용자는 동기화를 설정하거나 해제할 수 있습니다. 해당 정책을 필수로 적용하면 사용자는 동기화를 설정할 수 없습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: SyncDisabled
  - GP 이름: Microsoft 동기화 서비스를 사용하여 데이터 동기화 사용 해제
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: SyncDisabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: SyncDisabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="synctypeslistdisabled"></a>SyncTypesListDisabled

  #### <a name="configure-the-list-of-types-that-are-excluded-from-synchronization"></a>동기화에서 제외되는 유형의 목록 구성

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (83 이상)

  #### <a name="description"></a>설명

  해당 정책을 사용하면 지정된 모든 데이터 형식이 동기화에서 제외됩니다. 해당 정책을 사용하여 Microsoft Edge 동기화 서비스로 업로드되는 데이터 형식을 제한할 수 있습니다.

해당 정책에 대한 다음 데이터 형식 중 하나를 제공할 수 있습니다. "favorites", "settings", "passwords", "addressesAndMore", "extensions", "history", "openTabs" 및 “collections” 해당 데이터 형식 이름은 대/소문자를 구분해야 한다는 점에 유의하세요.

사용자는 사용하지 않도록 설정된 데이터 형식을 재정의할 수 없습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: SyncTypesListDisabled
  - GP 이름: 동기화에서 제외되는 유형의 목록 구성
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\SyncTypesListDisabled
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\SyncTypesListDisabled\1 = "favorites"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: SyncTypesListDisabled
  - 예를 들어 값:
``` xml
<array>
  <string>favorites</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="tls13hardeningforlocalanchorsenabled"></a>TLS13HardeningForLocalAnchorsEnabled

  #### <a name="enable-a-tls-13-security-feature-for-local-trust-anchors-obsolete"></a>로컬 트러스트 앵커에 대한 TLS 1.3 보안 기능 사용(구식)

  
  >사용되지 않음: 이 정책은 더 이상 사용되지 않으며 Microsoft Edge 85 이후에는 작동하지 않습니다.
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상, 85까지)

  #### <a name="description"></a>설명

  이 정책은 영향을 받는 프록시를 업그레이드할 수 있는 시간을 더 많이 주기 위한 단기 메커니즘으로만 의도되었기 때문에 작동하지 않습니다.

해당 정책은 다운그레이드 공격에 대한 연결을 보호하는 TLS 1.3의 보안 기능을 제어합니다. 해당 기능은 이전 버전과 호환이 가능하며 호환되는 TLS 1.2 서버 또는 프록시에 대한 연결에는 효과가 없습니다. 그러나 일부 TLS-차단 프록시의 이전 버전은 구현 결함 때문에 호환되지 않는 문제가 발생할 수 있습니다.

해당 정책을 사용하거나 설정하지 않으면 Microsoft Edge에서 모든 연결에 대해 해당 보안 보호를 사용하도록 설정합니다.

해당 정책을 사용하지 않도록 설정하면 Microsoft Edge는 로컬로 설치된 CA 인증서를 사용하여 인증된 연결에 대해 해당 보안 보호를 사용하지 않습니다. 해당 보호 기능은 공개적으로 신뢰할 수 있는 CA 인증서를 사용하여 인증된 연결에 대해 항상 사용할 수 있습니다.

해당 정책은 영향을 받는 프록시를 테스트하고 업그레이드하는 데 사용될 수 있습니다. 영향을 받는 프록시는 ERR_TLS13_DOWNGRADE_DETECTED 오류 코드와 함께 연결에 실패할 것으로 예상됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: TLS13HardeningForLocalAnchorsEnabled
  - GP 이름: 로컬 트러스트 앵커에 대한 TLS 1.3 보안 기능 사용(구식)
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: TLS13HardeningForLocalAnchorsEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: TLS13HardeningForLocalAnchorsEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="tlsciphersuitedenylist"></a>TLSCipherSuiteDenyList

  #### <a name="specify-the-tls-cipher-suites-to-disable"></a>비활성화할 TLS 암호화 그룹 지정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS(85 이상)

  #### <a name="description"></a>설명

  TLS 연결이 비활성화된 암호화 그룹 목록을 구성합니다.

이 정책을 구성하면 TLS 연결을 설정할 때 구성된 암호화 그룹 목록이 사용되지 않습니다.

이 정책을 구성하지 않으면 브라우저가 사용할 TLS 암호화 그룹을 선택합니다.

비활성화할 설정할 암호화 그룹 값은 16비트 16진수 값으로 지정됩니다. 값은 IANA(Internet Assigned Numbers Authority) 레지스트리에 의해 할당됩니다.

TLS 1.3 암호화 그룹 TLS_AES_128_GCM_SHA256(0x1301)은 TLS 1.3에 필요하며이 정책으로 비활성화할 수 없습니다.

이 정책은 QUIC 기반 연결에는 영향을 미치지 않습니다. QUIC는 [QuicAllowed](#quicallowed) 정책을 통해 끌 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: TLSCipherSuiteDenyList
  - GP 이름: 비활성화할 TLS 암호 제품군 지정
  - GP 경로(필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로(필수): SOFTWARE\Policies\Microsoft\Edge\TLSCipherSuiteDenyList
  - 경로(권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\TLSCipherSuiteDenyList\1 = "0x1303"
SOFTWARE\Policies\Microsoft\Edge\TLSCipherSuiteDenyList\2 = "0xcca8"
SOFTWARE\Policies\Microsoft\Edge\TLSCipherSuiteDenyList\3 = "0xcca9"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: TLSCipherSuiteDenyList
  - 예를 들어 값:
``` xml
<array>
  <string>0x1303</string>
  <string>0xcca8</string>
  <string>0xcca9</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="tabfreezingenabled"></a>TabFreezingEnabled

  #### <a name="allow-freezing-of-background-tabs"></a>배경 탭 고정 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (79 이상)

  #### <a name="description"></a>설명

  Microsoft Edge에서 최소 5분 간 백그라운드에 있는 탭의 고정 여부를 제어합니다.

탭을 고정하면 CPU, 배터리 및 메모리 사용이 감소합니다. Microsoft Edge에서는 화면 표시, 소리 재생, 스트림 비디오 등과 같이 백그라운드에서 유용하게 사용할 수 있는 탭이 고정되지 않도록 경험적 접근을 사용합니다.

해당 정책을 사용하도록 설정하거나 구성하지 않으면 최소 5분 이상 백그라운드에 있는 탭이 고정될 수 있습니다.

해당 정책을 사용하지 않으면 탭이 고정되지 않습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: TabFreezingEnabled
  - GP 이름: 배경 탭 고정 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: TabFreezingEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: TabFreezingEnabled
  - 예를 들어 값:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="targetblankimpliesnoopener"></a>TargetBlankImpliesNoOpener

  #### <a name="do-not-set-windowopener-for-links-targeting-_blank"></a>_blank를 대상으로 하는 링크에 대해 window.opener를 설정하지 마세요.

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS 88 이상

  #### <a name="description"></a>설명

  해당 정책을 사용하도록 설정하거나 설정하지 않은 경우 앵커에서 rel="opener"를 지정하지 않은 이상 window.opener 속성이 null로 설정됩니다.

해당 정책을 사용하지 않도록 설정하면, _blank를 대상으로 하는 팝업이 팝업을 열기로 요청한 페이지(JavaScript를 통해)에 액세스할 수 있도록 허용됩니다.

이 정책은 Microsoft Edge 버전 95에서 사용되지 않습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: TargetBlankImpliesNoOpener
  - GP 이름: _blank를 대상으로 하는 링크에 대해 window.opener를 설정하지 마세요.
  - GP 경로(필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로(권장): 해당 없음
  - 값 이름: TargetBlankImpliesNoOpener
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: TargetBlankImpliesNoOpener
  - 예를 들어 값:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="taskmanagerendprocessenabled"></a>TaskManagerEndProcessEnabled

  #### <a name="enable-ending-processes-in-the-browser-task-manager"></a>브라우저 작업 관리자에서 프로세스 종료 사용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  해당 정책을 사용하도록 설정하거나 구성하지 않으면 사용자는 브라우저의 작업 관리자에서 프로세스를 끝낼 수 있습니다. 해당 정책을 사용하지 않도록 설정하면 사용자는 프로세스를 끝낼 수 없으며 브라우저의 작업 관리자에서 프로세스 종료 단추가 비활성화됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: TaskManagerEndProcessEnabled
  - GP 이름: 브라우저 작업 관리자에서 프로세스 종료 사용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: TaskManagerEndProcessEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: TaskManagerEndProcessEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="totalmemorylimitmb"></a>TotalMemoryLimitMb

  #### <a name="set-limit-on-megabytes-of-memory-a-single-microsoft-edge-instance-can-use"></a>단일 Microsoft Edge 인스턴스에서 사용할 수 있는 메모리 용량(MB) 제한 설정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (80 이상)

  #### <a name="description"></a>설명

  메모리를 절약하기 위해 탭이 삭제되기 전에 단일 Microsoft Edge 인스턴스가 사용할 수 잇는 메모리 용량을 구성합니다. 탭에서 사용하는 메모리는 해제되고 전환 시 탭이 다시 로드됩니다.

해당 정책을 사용하면 브라우저에서 제한을 초과한 경우 탭을 삭제하기 시작하여 메모리를 절약할 수 있습니다. 하지만 브라우저가 항상 제한 내에서 실행하는 것은 아닙니다. 1024 아래의 값은 모두 1024로 반올림됩니다.

해당 정책을 설정하지 않으면 브라우저는 컴퓨터에서 실제 메모리 용량이 낮은 경우를 감지했을 때만 메모리 저장을 시도합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: TotalMemoryLimitMb
  - GP 이름: 단일 Microsoft Edge 인스턴스에서 사용할 수 있는 메모리 용량(MB) 제한 설정
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: TotalMemoryLimitMb
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000800
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: TotalMemoryLimitMb
  - 예를 들어 값:
``` xml
<integer>2048</integer>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="trackingprevention"></a>TrackingPrevention

  #### <a name="block-tracking-of-users-web-browsing-activity"></a>사용자의 웹 검색 활동 추적 차단

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (78 이상)

  #### <a name="description"></a>설명

  웹 사이트에서 사용자의 웹 검색 활동을 추적하지 못하도록 차단 여부를 결정할 수 있습니다.

해당 정책을 사용하지 않도록 설정하거나 구성하지 않으면 사용자는 추적 방지 수준을 직접 설정할 수 있습니다.

정책 옵션 매핑:

* TrackingPreventionOff (0) = 꺼짐(추적 방지 없음)

* TrackingPreventionBasic (1) = 기본 (유해한 추적기를 차단, 콘텐츠 및 광고의 개인화)

* TrackingPreventionBalanced (2) = 균형 (유해한 추적기 및 사용자가 방문하지 않은 사이트의 추적기를 차단, 콘텐츠 및 광고의 개인화 감소)

* TrackingPreventionStrict (3) = 고급 (유해한 추적기 및 모든 사이트의 대부분의 추적기를 차단, 콘텐츠 및 광고의 개인화 최소 사이트의 일부 기능 작동 안 함)

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: TrackingPrevention
  - GP 이름: 사용자의 웹 검색 활동 추적 차단
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: TrackingPrevention
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000002
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: TrackingPrevention
  - 예를 들어 값:
``` xml
<integer>2</integer>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="translateenabled"></a>TranslateEnabled

  #### <a name="enable-translate"></a>번역 사용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  Microsoft Edge에서 통합 Microsoft 번역 서비스를 사용하도록 설정합니다.

해당 정책을 사용하면 Microsoft Edge는 적절한 경우 통합 번역 플라이 아웃을 표시하고 상황에 맞는 메뉴를 마우스 오른쪽 단추로 클릭하고 번역 옵션을 표시하여 사용자에게 번역 기능을 제공합니다.

해당 정책을 사용하지 않도록 설정하면 기본 제공되는 모든 번역 기능을 사용할 수 없습니다.

해당 정책을 구성하지 않으면 사용자는 번역 기능의 사용 여부를 선택할 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: TranslateEnabled
  - GP 이름: 번역 사용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 관리 템플릿/Microsoft Edge - 기본 설정(사용자 재정의 가능)/
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): SOFTWARE\정책\Microsoft\Edge\Recommended
  - 값 이름: TranslateEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: TranslateEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="urlallowlist"></a>URLAllowlist

  #### <a name="define-a-list-of-allowed-urls"></a>허용되는 URL 목록 정의

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  이 정책을 설정하면 [URLBlocklist](#urlblocklist)를 예외로 하고, 나열된 URL에 대한 액세스를 제공합니다.

[https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)에 따라 URL 패턴의 형식을 지정합니다.

해당 정책을 사용하여 제한적인 차단 목록에 대한 예외를 열 수 있습니다. 예를 들어 차단 목록에 '\*'를 포함하여 모든 요청을 차단한 다음, 이 정책을 사용하여 제한된 URL 목록의 액세스를 허용할 수 있습니다. 해당 정책을 사용하여 특정 구성표, 다른 도메인의 하위 도메인, 포트 또는 특정 경로에 대한 예외를 열 수 있습니다.

특정 필터는 URL을 차단할지 또는 허용할지 여부를 결정합니다. 허용 목록은 차단 목록 보다 우선합니다.

해당 정책은 1000개의 항목으로 제한됩니다. 이후의 항목은 무시됩니다.

이 정책을 사용하면 브라우저가 "전화:" 또는 "ssh:"와 같은 프로토콜의 프로토콜 처리기로 등록된 외부 응용 프로그램을 자동으로 호출할 수도 있습니다.

해당 정책을 구성하지 않으면 [URLBlocklist](#urlblocklist) 정책의 차단 목록에 대한 예외는 없습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: URLAllowlist
  - GP 이름: 허용되는 URL 목록 정의
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\URLAllowlist
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\URLAllowlist\1 = "contoso.com"
SOFTWARE\Policies\Microsoft\Edge\URLAllowlist\2 = "https://ssl.server.com"
SOFTWARE\Policies\Microsoft\Edge\URLAllowlist\3 = "hosting.com/good_path"
SOFTWARE\Policies\Microsoft\Edge\URLAllowlist\4 = "https://server:8080/path"
SOFTWARE\Policies\Microsoft\Edge\URLAllowlist\5 = ".exact.hostname.com"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: URLAllowlist
  - 예를 들어 값:
``` xml
<array>
  <string>contoso.com</string>
  <string>https://ssl.server.com</string>
  <string>hosting.com/good_path</string>
  <string>https://server:8080/path</string>
  <string>.exact.hostname.com</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="urlblocklist"></a>URLBlocklist

  #### <a name="block-access-to-a-list-of-urls"></a>URL 목록에 대한 액세스 차단

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  차단된 URL 패턴(사용자가 로드할 수 없음)을 기반으로 사이트 목록을 정의합니다.

[https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)에 따라 URL 패턴의 형식을 지정합니다.

[URLAllowlist](#urlallowlist) 정책에서 예외를 정의할 수 있습니다. 해당 정책은 1000개의 항목으로 제한됩니다. 이후의 항목은 무시됩니다.

내부 'edge://*' URL을 차단하지 않는 것이 좋습니다. 이 경우 예기치 않은 오류가 발생할 수 있다는 점에 유의하세요.

해당 정책은 페이지가 JavaScript를 통해 동적으로 업데이트되는 것을 방지하지 않습니다. 예를 들어 'contoso.com/abc'를 차단하는 경우 사용자는 'contoso.com'을 방문하고 링크를 클릭하여 페이지가 새로고침되지 않는 한 'contoso.com/abc'를 계속 방문할 수 있습니다.

해당 정책을 구성하지 않으면 URL은 차단되지 않습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: URLBlocklist
  - GP 이름: URL 목록에 대한 액세스 차단
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\URLBlocklist
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\URLBlocklist\1 = "contoso.com"
SOFTWARE\Policies\Microsoft\Edge\URLBlocklist\2 = "https://ssl.server.com"
SOFTWARE\Policies\Microsoft\Edge\URLBlocklist\3 = "hosting.com/bad_path"
SOFTWARE\Policies\Microsoft\Edge\URLBlocklist\4 = "https://server:8080/path"
SOFTWARE\Policies\Microsoft\Edge\URLBlocklist\5 = ".exact.hostname.com"
SOFTWARE\Policies\Microsoft\Edge\URLBlocklist\6 = "file://*"
SOFTWARE\Policies\Microsoft\Edge\URLBlocklist\7 = "custom_scheme:*"
SOFTWARE\Policies\Microsoft\Edge\URLBlocklist\8 = "*"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: URLBlocklist
  - 예를 들어 값:
``` xml
<array>
  <string>contoso.com</string>
  <string>https://ssl.server.com</string>
  <string>hosting.com/bad_path</string>
  <string>https://server:8080/path</string>
  <string>.exact.hostname.com</string>
  <string>file://*</string>
  <string>custom_scheme:*</string>
  <string>*</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="updatepolicyoverride"></a>UpdatePolicyOverride

  #### <a name="specifies-how-microsoft-edge-update-handles-available-updates-from-microsoft-edge"></a>Microsoft Edge 업데이트가 Microsoft Edge에서 사용 가능한 업데이트를 처리하는 방법을 지정합니다.

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - MacOS(89 이상)

  #### <a name="description"></a>설명

  이 정책을 사용하도록 설정하면 다음 중 구성된 옵션에 따라 Microsoft Edge 업데이트가 Microsoft Edge에 대한 업데이트를 처리합니다.

- 자동 업데이트만: 업데이트는 정기 업데이트 확인에서 검색된 경우에만 적용됩니다.

- 수동 업데이트만: 업데이트는 사용자가 수동 업데이트 확인을 실행하는 경우에만 적용됩니다. (일부 앱은 이 옵션에 대한 인터페이스를 제공하지 않습니다.)

수동 업데이트를 선택하는 경우 Microsoft 자동 업데이트를 사용하여 정기적으로 업데이트를 확인해야 합니다.

이 정책을 실행하고 구성하지 않으면 Microsoft Edge Update가 자동으로 업데이트를 확인합니다.


정책 옵션 매핑:

* automatic-silent-only (automatic-silent-only) = 업데이트는 정기적인 업데이트 확인에 의해 발견된 경우에만 적용됩니다.

* manual-only (manual-only) = 업데이트는 사용자가 수동 업데이트 검사를 실행할 때만 적용됩니다. (일부 앱은 이 옵션에 대한 인터페이스를 제공하지 않습니다.)

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 예
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 문자열

  

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: UpdatePolicyOverride
  - 예제 값:
``` xml
<string>automatic-silent-only</string>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="useragentclienthintsenabled"></a>UserAgentClientHintsEnabled

  #### <a name="enable-the-user-agent-client-hints-feature-deprecated"></a>사용자 에이전트 클라이언트 힌트 기능 사용(사용되지 않음)

  >DEPRECATED: 해당 정책은 사용되지 않습니다. 현재 지원되고 있지만 이후 릴리스에서는 더 이상 사용되지 않을 예정입니다.
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (86 이상)

  #### <a name="description"></a>설명

  이 정책은 사용자-에이전트 클라이언트 힌트 기능과 호환되지 않는 경우 기업이 웹 콘텐츠를 업데이트할 수 있는 시간을 더 많이 주기 위한 단기 메커니즘이기 때문에 더 이상 사용되지 않습니다. Microsoft Edge 버전 93에서는 작동하지 않습니다.

사용자 에이전트 힌트 기능을 사용하면 사용자 브라우저(예: 브라우저 버전) 및 환경(예: 시스템 아키텍처)에 대한 정보를 제공하는 세분화된 요청 헤더가 전송됩니다.

이는 추가 기능이지만, 새 헤더로 인해 요청에 포함될 수 있는 문자를 제한하는 일부 웹사이트가 중단될 수도 있습니다.

이 정책을 사용하거나 이 정책을 구성하지 않는 경우 사용자 에이전트 클라이언트 힌트 기능을 사용합니다. 이 정책을 사용하지 않는 경우 이 기능을 사용할 수 없습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: UserAgentClientHintsEnabled
  - GP 이름: 사용자 에이전트 클라이언트 힌트 기능 사용(사용되지 않음)
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: UserAgentClientHintsEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: Useragentclienthsenabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="userdatadir"></a>UserDataDir

  #### <a name="set-the-user-data-directory"></a>사용자 데이터 디렉터리 설정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  사용자 데이터를 저장하는 데 사용할 디렉터리를 설정합니다.

해당 정책을 사용하면 사용자가 '--user-data-dir' 플래그를 설정했는지 여부에 관계 없이 Microsoft Edge는 지정된 디렉터리를 사용합니다.

해당 정책을 사용하지 않으면 기본 프로필 경로가 사용되지만 사용자가 '--user-data-dir' 플래그를 사용하여 경로를 재정의할 수 있습니다. 사용자는 프로필 경로의 edge://version/에서 프로필에 대한 디렉터리를 찾을 수 있습니다.

데이터 손실 또는 기타 예기치 않은 오류가 발생하지 않도록 하려면 Microsoft Edge에서 해당 콘텐츠를 관리하기 때문에 볼륨의 루트 디렉터리나 다른 목적에 사용되는 디렉터리로 해당 정책을 구성하지 마세요.

사용할 수 있는 변수의 목록은 [https://go.microsoft.com/fwlink/?linkid=2095041](https://go.microsoft.com/fwlink/?linkid=2095041)을 참조하세요.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 문자열

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: UserDataDir
  - GP 이름: 사용자 데이터 디렉터리 설정
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: UserDataDir
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
"${users}/${user_name}/Edge"
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: UserDataDir
  - 예를 들어 값:
``` xml
<string>${users}/${user_name}/Edge</string>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="userdatasnapshotretentionlimit"></a>UserDataSnapshotRetentionLimit

  #### <a name="limits-the-number-of-user-data-snapshots-retained-for-use-in-case-of-emergency-rollback"></a>긴급 롤백이 있을 경우 사용하기 위해 보관된 사용자 데이터 스냅샷 수를 제한합니다

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 86 이상

  #### <a name="description"></a>설명

  각 주요 버전 업데이트 후 Microsoft Edge는 임시 버전 롤백이 필요한 이후 긴급한 상황에 사용할 사용자의 검색 데이터 일부에 대한 스냅샷을 만듭니다. 사용자에게 해당 스냅샷이 있는 버전에 임시 롤백이 수행되면 스냅샷의 데이터가 복원됩니다. 이렇게 하면 사용자가 책갈피와 자동 채우기 데이터 같은 설정을 유지할 수 있습니다.

이 정책을 설정하지 않으면 3개 스냅샷의 기본값이 사용됩니다.

이 정책을 설정하면 사용자가 설정한 제한을 준수하기 위해 필요에 따라 이전 스냅샷이 삭제됩니다. 이 정책을 0으로 설정하면 스냅샷이 만들어지지 않습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 정수

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: UserDataSnapshotRetentionLimit
  - GP 이름: 긴급 롤백이 있을 경우 사용하기 위해 보관된 사용자 데이터 스냅샷 수를 제한합니다
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: UserDataSnapshotRetentionLimit
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000003
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="userfeedbackallowed"></a>UserFeedbackAllowed

  #### <a name="allow-user-feedback"></a>사용자 피드백 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  Microsoft Edge는 Edge 피드백 기능(기본적으로 사용)을 사용하여 사용자가 피드백, 제안 또는 고객 조사를 전송하고 브라우저와 관련된 문제를 보고할 수 있도록 합니다. 또한 기본적으로 사용자는 Edge 피드백 기능을 사용하지 않도록 설정(해제) 할 수 없습니다.

해당 정책을 사용하도록 설정하거나 구성하지 않으면 사용자는 Edge 피드백을 호출할 수 있습니다.

해당 정책을 사용하지 않도록 설정하면 사용자는 Edge 피드백을 호출할 수 없습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: UserFeedbackAllowed
  - GP 이름: 사용자 피드백 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: UserFeedbackAllowed
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: UserFeedbackAllowed
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="verticaltabsallowed"></a>VerticalTabsAllowed

  #### <a name="configures-availability-of-a-vertical-layout-for-tabs-on-the-side-of-the-browser"></a>브라우저 측면의 탭에 대한 수직 레이아웃의 가용성 구성

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS 88 이상

  #### <a name="description"></a>설명

  탭이 상단 대신 브라우저 측면에 수직으로 정렬된 대체 레이아웃에 사용자가 액세스할 수 있는지 여부를 구성합니다.
탭이 여러 개 열려 있는 경우 이 레이아웃을 통해 탭을 보다 효율적으로 보고 관리할 수 있습니다. 사이트 제목을 더 잘 볼 수 있고 정렬된 아이콘을 더 쉽게 검색할 수 있으며 탭을 관리하고 닫을 수 있는 공간이 더 넓습니다.

이 정책을 실행 중지하면 수직 탭 레이아웃을 사용자의 옵션으로 사용할 수 없습니다.

이 정책을 실행하거나 구성하지 않으면 탭 레이아웃은 여전히 맨 위에 있지만 사용자는 측면의 수직 탭을 켤 수 있는 옵션을 사용할 수 있습니다.


  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: VerticalTabsAllowed
  - GP 이름: 브라우저 측면의 탭에 대해 수직 레이아웃의 가용성 구성
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: VerticalTabsAllowed
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: VerticalTabsAllowed
  - 예제 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="videocaptureallowed"></a>VideoCaptureAllowed

  #### <a name="allow-or-block-video-capture"></a>비디오 캡처 허용 또는 차단

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  사이트에서 비디오를 캡처할 수 있는지 여부를 제어합니다.

해당 정책을 사용하도록 설정하거나 구성하지 않은 경우(기본값) 사용자에게 묻지 않고 액세스 권한이 부여되는 [VideoCaptureAllowedUrls](#videocaptureallowedurls) 정책 목록에서 구성한 URL을 제외한 모든 사이트에 대해 비디오 캡처 액세스 관련 메시지가 표시됩니다.

해당 정책을 사용하지 않도록 설정하는 경우 사용자에게 메시지가 표시되지 않고 [VideoCaptureAllowedUrls](#videocaptureallowedurls) 정책에서 구성된 URL로만 비디오 캡처를 사용할 수 있습니다.

해당 정책은 내장형 카메라 뿐만 아니라 모든 유형의 비디오 입력에 영향을 줍니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: VideoCaptureAllowed
  - GP 이름: 비디오 캡처 허용 또는 차단
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: VideoCaptureAllowed
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: VideoCaptureAllowed
  - 예를 들어 값:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="videocaptureallowedurls"></a>VideoCaptureAllowedUrls

  #### <a name="sites-that-can-access-video-capture-devices-without-requesting-permission"></a>권한 요청 없이 비디오 캡처 장치에 액세스할 수 있는 사이트

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  사용자에게 사용 권한을 묻지 않고 비디오 캡처 장치를 사용할 수 있는 URL 패턴을 기반으로 웹 사이트를 지정합니다. 해당 목록의 패턴은 요청 URL의 보안 원본과 일치합니다. 일치하는 경우 자동으로 비디오 캡처 장치에 대한 액세스 권한이 부여됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: VideoCaptureAllowedUrls
  - GP 이름: 권한 요청 없이 비디오 캡처 장치에 액세스할 수 있는 사이트
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\VideoCaptureAllowedUrls
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\VideoCaptureAllowedUrls\1 = "https://www.contoso.com/"
SOFTWARE\Policies\Microsoft\Edge\VideoCaptureAllowedUrls\2 = "https://[*.]contoso.edu/"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: VideoCaptureAllowedUrls
  - 예를 들어 값:
``` xml
<array>
  <string>https://www.contoso.com/</string>
  <string>https://[*.]contoso.edu/</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="wpadquickcheckenabled"></a>WPADQuickCheckEnabled

  #### <a name="set-wpad-optimization"></a>WPAD 최적화 설정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  Microsoft Edge에서 WPAD(웹 프록시 자동 검색) 최적화를 해제할 수 있습니다.

해당 정책을 사용하지 않도록 설정하면 WPAD 최적화가 해제되어 DNS 기반 WPAD 서버에 대해 브라우저가 더 오래 대기합니다.

해당 정책을 사용하도록 설정하거나 구성하지 않으면 WPAD 최적화를 사용할 수 있습니다.

해당 정책의 사용 설정 여부나 방식에 관계 없이 사용자는 WPAD 최적화 설정을 변경할 수 없습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: WPADQuickCheckEnabled
  - GP 이름: WPAD 최적화 설정
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: WPADQuickCheckEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: WPADQuickCheckEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="webappinstallforcelist"></a>WebAppInstallForceList

  #### <a name="configure-list-of-force-installed-web-apps"></a>강제 설치된 웹 앱 목록 구성

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (80 이상)

  #### <a name="description"></a>설명

  사용자의 상호 작용이 없이 자동으로 설치되는 웹 앱의 목록 그리고 제거 또는 해제할 수 없는 사용자를 지정하려면 이 정책을 구성합니다.

정책의 각 목록 항목은 필수 구성원이 있는 개체입니다. URL(설치할 웹 앱의 URL)

및 3개 선택적 구성원:
- default_launch_container(웹 앱이 여는 창 모드를 지정합니다. 새 탭이 기본값입니다.)

- create_desktop_shortcut(Linux 및 Microsoft Windows 데스크톱 바로 가기를 만들려면 true입니다.)

- fallback_app_name(Microsoft Edge 90부터는 PWA(Progressive Web App)가 아닌 경우 앱 이름을 재정의하거나, PWA이지만 설치를 완료하기 전에 인증이 필요한 경우 임시로 설치된 앱 이름을 재정의할 수 있습니다.)

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - Dictionary

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: WebAppInstallForceList
  - GP 이름: 강제 설치된 웹 앱 목록 구성
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: WebAppInstallForceList
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\WebAppInstallForceList = [
  {
    "create_desktop_shortcut": true, 
    "default_launch_container": "window", 
    "url": "https://www.contoso.com/maps"
  }, 
  {
    "default_launch_container": "tab", 
    "url": "https://app.contoso.edu"
  }, 
  {
    "default_launch_container": "window", 
    "fallback_app_name": "Editor", 
    "url": "https://app.contoso.com/editor"
  }
]
```

  ##### <a name="compact-example-value"></a>예제 값 압축:

  ```
  SOFTWARE\Policies\Microsoft\Edge\WebAppInstallForceList = [{"create_desktop_shortcut": true, "default_launch_container": "window", "url": "https://www.contoso.com/maps"}, {"default_launch_container": "tab", "url": "https://app.contoso.edu"}, {"default_launch_container": "window", "fallback_app_name": "Editor", "url": "https://app.contoso.com/editor"}]
  ```
  

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: WebAppInstallForceList
  - 예를 들어 값:
``` xml
<key>WebAppInstallForceList</key>
<array>
  <dict>
    <key>create_desktop_shortcut</key>
    <true/>
    <key>default_launch_container</key>
    <string>window</string>
    <key>url</key>
    <string>https://www.contoso.com/maps</string>
  </dict>
  <dict>
    <key>default_launch_container</key>
    <string>tab</string>
    <key>url</key>
    <string>https://app.contoso.edu</string>
  </dict>
  <dict>
    <key>default_launch_container</key>
    <string>window</string>
    <key>fallback_app_name</key>
    <string>Editor</string>
    <key>url</key>
    <string>https://app.contoso.com/editor</string>
  </dict>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="webcaptureenabled"></a>WebCaptureEnabled

  #### <a name="enable-web-capture-feature-in-microsoft-edge"></a>Microsoft Edge에서 웹 캡처 기능을 사용하도록 설정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - On Windows and macOS since 87 or later

  #### <a name="description"></a>설명

  사용자가 수동 입력 도구를 사용하여 웹 콘텐츠를 캡처하고 캡처에 주석을 달 수 있게 해주는 Microsoft Edge의 웹 캡처 기능을 사용하도록 설정합니다.
이 정책을 사용하도록 설정하거나 구성하지 않으면 상황에 맞는 메뉴, 설정 및 기타 메뉴에 웹 캡처 옵션이 표시되고, 바로 가기 키(CTRL+SHIFT+S)를 사용하여 웹 캡처 옵션이 표시됩니다.
이 정책을 사용하지 않도록 설정하면 사용자는 Microsoft Edge에서 웹 캡처 기능에 액세스할 수 없습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: WebCaptureEnabled
  - GP 이름: Microsoft Edge에서 웹 캡처 기능을 사용하도록 설정
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: WebCaptureEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: WebCaptureEnabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="webcomponentsv0enabled"></a>WebComponentsV0Enabled

  #### <a name="re-enable-web-components-v0-api-until-m84-obsolete"></a>M84까지 웹 구성 요소 v0 API 다시 사용(사용되지 않음)

  
  >사용되지 않음: 이 정책은 더 이상 사용되지 않으며 Microsoft Edge 84 이후에는 작동하지 않습니다.
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS 80~84

  #### <a name="description"></a>설명

  이 정책은 Microsoft Edge 버전 85까지 이러한 기능을 선택적으로 다시 사용하도록 허용했기 때문에 작동하지 않습니다. 웹 구성 요소 v0 API(쉐도우 DOM v0, 사용자 지정 요소 v0 및 HTML 가져오기)는 2018년에 사용되지 않았습니다. 기본적으로 Microsoft Edge 버전 80부터 비활성화되어 있습니다.

해당 정책을 True로 설정하면 모든 사이트에 대해 웹 구성 요소 v0 기능을 사용할 수 있습니다.

해당 정책을 False로 설정하거나 설정하지 않으면 Microsoft Edge 버전 80부터 시작하여 웹 구성 요소 v0 기능을 기본적으로 사용하지 않도록 설정됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: WebComponentsV0Enabled
  - GP 이름: M84까지 웹 구성 요소 v0 API 다시 사용(사용되지 않음)
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: WebComponentsV0Enabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: WebComponentsV0Enabled
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="webdriveroverridesincompatiblepolicies"></a>WebDriverOverridesIncompatiblePolicies

  #### <a name="allow-webdriver-to-override-incompatible-policies-deprecated"></a>WebDriver가 호환되지 않는 정책을 재정의하도록 허용 (사용되지 않음)

  >DEPRECATED: 해당 정책은 사용되지 않습니다. 현재 지원되고 있지만 이후 릴리스에서는 더 이상 사용되지 않을 예정입니다.
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상, 84까지)

  #### <a name="description"></a>설명

  WebDriver가 이제 모든 기존 정책과 호환되므로 이 정책이 작동하지 않습니다.

해당 정책을 사용하면 WebDriver 기능 사용자는 작업을 방해할 수 있는 정책을 재정의할 수 있습니다.

현재 해당 정책은 [SitePerProcess](#siteperprocess) 및 [IsolateOrigins](#isolateorigins) 정책을 사용하지 않도록 설정합니다.

해당 정책을 사용하면 WebDriver는 호환되지 않는 정책을 재정의할 수 있습니다.
해당 정책을 사용하지 않거나 구성하지 않으면 WebDriver는 호환되지 않는 정책을 재정의할 수 없습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: WebDriverOverridesIncompatiblePolicies
  - GP 이름: WebDriver가 호환되지 않는 정책을 재정의하도록 허용 (사용되지 않음)
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: WebDriverOverridesIncompatiblePolicies
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: WebDriverOverridesIncompatiblePolicies
  - 예를 들어 값:
``` xml
<true/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="webrtcallowlegacytlsprotocols"></a>WebRtcAllowLegacyTLSProtocols

  #### <a name="allow-legacy-tlsdtls-downgrade-in-webrtc-deprecated"></a>WebRTC에서 레거시 TLS/DTLS 다운그레이드 허용(사용되지 않음)

  >DEPRECATED: 해당 정책은 사용되지 않습니다. 현재 지원되고 있지만 이후 릴리스에서는 더 이상 사용되지 않을 예정입니다.
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS 88 이상

  #### <a name="description"></a>설명

  이 정책을 사용하면 WebRTC 피어 연결이 오래된 버전의 TLS/DTLS(DTLS 1.0, TLS 1.0 및 TLS 1.1) 프로토콜로 다운그레이드할 수 있습니다.
이 정책을 실행 중지하거나 설정하지 않으면 이러한 TLS/DTLS 버전이 실행 중지됩니다.

이 정책은 임시 정책이며 이후 버전의 Microsoft Edge에서 제거됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: WebRtcAllowLegacyTLSProtocols
  - GP 이름: WebRTC에서 레거시 TLS/DTLS 다운그레이드 허용(사용되지 않음)
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: WebRtcAllowLegacyTLSProtocols
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000000
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: WebRtcAllowLegacyTLSProtocols
  - 예를 들어 값:
``` xml
<false/>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="webrtclocalipsallowedurls"></a>WebRtcLocalIpsAllowedUrls

  #### <a name="manage-exposure-of-local-ip-addressess-by-webrtc"></a>WebRTC로 로컬 IP 주소 노출 관리

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (80 이상)

  #### <a name="description"></a>설명

  로컬 IP 주소가 WebRTC로 노출되는 원본(URL) 또는 호스트 이름 패턴(예: "*contoso.com*") 목록을 지정합니다.

해당 정책을 사용하고 원본(URL) 또는 호스트 이름 패턴 목록을 설정하는 경우 edge://flags/#enable-webrtc-hide-local-ips-with-mdns를 사용하도록 설정할 때 WebRTC에서 목록에 있는 패턴과 일치하는 케이스에 대해 로컬 IP 주소를 노출합니다.

해당 정책을 사용하지 않도록 설정하거나 구성하지 않고 edge://flags/#enable-webrtc-hide-local-ips-with-mdns를 사용하도록 설정한 경우 WebRTC는 로컬 IP 주소를 노출하지 않습니다. 로컬 IP 주소는 mDNS 호스트 이름으로 숨겨집니다.

해당 정책을 사용 또는 사용하지 않도록 설정하거나 구성하지 않고 edge://flags/#enable-webrtc-hide-local-ips-with-mdns를 사용하지 않도록 설정한 경우 WebRTC는 로컬 IP 주소를 노출합니다.

해당 정책은 관리자가 필요로 할 수 있는 로컬 IP 주소의 보호를 약화시킬 수 있다는 점에 유의하세요.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 문자열 목록

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: WebRtcLocalIpsAllowedUrls
  - GP 이름: WebRTC로 로컬 IP 주소 노출 관리
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge\WebRtcLocalIpsAllowedUrls
  - 경로 (권장): 해당 없음
  - 값 이름: 1, 2, 3, ...
  - 값 형식: REG_SZ 목록

  ##### <a name="example-value"></a>예를 들어 값:

```
SOFTWARE\Policies\Microsoft\Edge\WebRtcLocalIpsAllowedUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\WebRtcLocalIpsAllowedUrls\2 = "*contoso.com*"

```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: WebRtcLocalIpsAllowedUrls
  - 예를 들어 값:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>*contoso.com*</string>
</array>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="webrtclocalhostiphandling"></a>WebRtcLocalhostIpHandling

  #### <a name="restrict-exposure-of-local-ip-address-by-webrtc"></a>WebRTC로 로컬 IP 주소 노출 제한

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  WebRTC가 사용자의 로컬 IP 주소를 노출하는지 여부를 설정할 수 있습니다.

해당 정책을 ‘AllowAllInterfaces’ 또는 ‘AllowPublicAndPrivateInterfaces’로 설정한 경우 WebRTC는 로컬 IP 주소를 노출합니다.

해당 정책을 ‘AllowPublicInterfaceOnly’ 또는 ‘DisableNonProxiedUdp’로 설정한 경우 WebRTC는 로컬 IP 주소를 노출하지 않습니다.

해당 정책을 설정하지 않거나 사용하지 않도록 설정한 경우 WebRTC는 로컬 IP 주소를 노출합니다.

정책 옵션 매핑:

* AllowAllInterfaces (기본값) = 모든 인터페이스를 허용합니다. 로컬 IP 주소를 노출함

* AllowPublicAndPrivateInterfaces (default_public_and_private_interfaces) = http 기본 경로를 통해 공개 및 개인 인터페이스를 허용합니다. 로컬 IP 주소를 노출함

* AllowPublicInterfaceOnly (default_public_interface_only) = http 기본 경로를 통해 공개 인터페이스를 허용합니다. 로컬 IP 주소를 노출 안 함

* DisableNonProxiedUdp (disable_non_proxied_udp) = 프록시 서버가 UDP를 지원하지 않으면 TCP를 사용합니다. 로컬 IP 주소를 노출 안 함

이 정책을 구성할 시 위의 정보를 사용합니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 문자열

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: WebRtcLocalhostIpHandling
  - GP 이름: WebRTC로 로컬 IP 주소 노출 제한
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: WebRtcLocalhostIpHandling
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
"default"
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: WebRtcLocalhostIpHandling
  - 예를 들어 값:
``` xml
<string>default</string>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="webrtcudpportrange"></a>WebRtcUdpPortRange

  #### <a name="restrict-the-range-of-local-udp-ports-used-by-webrtc"></a>WebRTC로 로컬 UDP 포트 범위 제한

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 및 MacOS (77 이상)

  #### <a name="description"></a>설명

  WebRTC에서 사용하는 UDP 포트 범위를 지정된 포트 간격(끝점 포함)으로 제한합니다.

해당 정책을 구성하여 WebRTC에서 사용할 수 있는 로컬 UDP 포트 범위를 지정합니다.

해당 정책을 구성하지 않거나 빈 문자열 또는 잘못된 포트 범위로 설정하는 경우 WebRTC는 제공된 모든 로컬 UDP 포트를 사용할 수 있습니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 문자열

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: WebRtcUdpPortRange
  - GP 이름: WebRTC로 로컬 UDP 포트 범위 제한
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: WebRtcUdpPortRange
  - 값 형식: REG_SZ

  ##### <a name="example-value"></a>예를 들어 값:

```
"10000-11999"
```

  #### <a name="mac-information-and-settings"></a>Mac 정보 및 설정
  
  - 기본 설정 키 이름: WebRtcUdpPortRange
  - 예를 들어 값:
``` xml
<string>10000-11999</string>
```
  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="webwidgetallowed"></a>WebWidgetAllowed

  #### <a name="enable-the-web-widget"></a>웹 위젯 설정

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows (88 이상)

  #### <a name="description"></a>설명

  웹 위젯을 사용하도록 설정합니다. 해당 설정을 사용하면 사용자는 위젯을 사용하여 바탕 화면 또는 응용 프로그램에서 웹을 검색할 수 있습니다. 위젯은 웹 제안을 표시하고 Microsoft Edge에서 모든 웹 검색을 여는 검색 상자를 제공합니다. 검색 상자는 검색(Bing에서 제공) 및 URL 제안을 제공합니다. 위젯에는 사용자가 새 Microsoft Edge 브라우저 탭 또는 창에서 msn.com에 대한 자세한 정보를 보기 위해 클릭할 수 있는 피드 타일도 포함되어 있습니다. 피드 타일에 광고가 포함될 수 있습니다. 위젯은 Microsoft Edge 설정 또는 Microsoft Edge의 “추가 도구” 메뉴에서 실행할 수 있습니다.

해당 정책을 사용하도록 설정하거나 구성하지 않으면 웹 위젯이 모든 프로필에 대해 자동으로 활성화됩니다.
Microsoft Edge 설정에서 사용자에게 위젯을 실행하는 옵션이 표시됩니다.
Microsoft Edge 설정에서 사용자에게 Windows 시작 시(자동 시작) 위젯을 실행하는 메뉴 항목이 표시됩니다.
[WebWidgetIsEnabledOnStartup](#webwidgetisenabledonstartup) 정책을 사용하는 경우 시작 시 위젯을 활성화하는 옵션이 설정됩니다.
[WebWidgetIsEnabledOnStartup](#webwidgetisenabledonstartup) 정책을 사용하지 않도록 설정하거나 구성하지 않으면 시작 시 위젯을 활성화하는 옵션이 해제됩니다.
사용자에게 Microsoft Edge "추가 도구" 메뉴에서 위젯을 실행하는 메뉴 항목이 표시됩니다. 사용자는 "추가 도구"에서 위젯을 실행할 수 있습니다.
시스템 트레이의 "종료" 옵션을 사용하거나 작업 표시줄에서 직접 종료하여 위젯을 해제할 수 있습니다. 자동 시작 옵션이 활성화된 경우 시스템 재부팅 시 위젯이 다시 실행됩니다.

해당 정책을 사용하지 않도록 설정하는 경우 모든 프로필에 대해 웹 위젯을 사용할 수 없습니다.
Microsoft Edge 설정에서 위젯을 실행하는 옵션이 사용하지 않도록 설정됩니다.
Windows 시작 시(자동 시작) 위젯을 실행하는 옵션이 사용하지 않도록 설정됩니다.
Microsoft Edge “추가 도구” 메뉴에서 위젯을 실행하는 옵션이 사용하지 않도록 설정됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: WebWidgetAllowed
  - GP 이름: 웹 위젯 설정
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: WebWidgetAllowed
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="webwidgetisenabledonstartup"></a>WebWidgetIsEnabledOnStartup

  #### <a name="allow-the-web-widget-at-windows-startup"></a>Windows 시작 시 웹 위젯 허용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows (88 이상)

  #### <a name="description"></a>설명

  Windows 시작 시 웹 위젯을 실행할 수 있습니다.

활성화된 경우 Windows 시작 시 기본적으로 웹 위젯 실행됩니다.
[WebWidgetAllowed](#webwidgetallowed) 정책을 통해 위젯을 사용하지 않도록 설정된 경우 해당 정책은 Windows 시작 시 위젯을 실행하지 않습니다.

해당 정책을 사용하지 않도록 설정하는 경우 Windows 시작 시 모든 프로필에 대해 웹 위젯을 실행하지 않습니다.
Windows 시작 시 웹 위젯을 실행하는 옵션은 Microsoft Edge 설정에서 사용하지 않도록 설정되고 해제됩니다.

해당 정책을 구성하지 않으면 Windows 시작 시 모든 프로필에 대해 웹 위젯을 실행하지 않습니다.
Windows 시작 시 웹 위젯을 실행하는 옵션은 Microsoft Edge 설정에서 해제됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: WebWidgetIsEnabledOnStartup
  - GP 이름: Windows 시작 시 웹 위젯 허용
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: WebWidgetIsEnabledOnStartup
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="winhttpproxyresolverenabled"></a>WinHttpProxyResolverEnabled

  #### <a name="use-windows-proxy-resolver-deprecated"></a>Windows 프록시 해결 프로그램 사용(사용되지 않음)

  >DEPRECATED: 해당 정책은 사용되지 않습니다. 현재 지원되고 있지만 이후 릴리스에서는 더 이상 사용되지 않을 예정입니다.
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 84 이상

  #### <a name="description"></a>설명

  이 정책은 향후 릴리스에서 유사한 기능으로 대체될 예정이므로 더 이상 사용되지 않습니다. https://crbug.com/1032820을(를) 참조하세요.

Windows를 사용하여 Microsoft Edge에 내장된 프록시 확인자 대신 모든 브라우저 네트워킹에 대한 프록시를 확인합니다. Windows 프록시 확인자는 DirectAccess/NRPT와 같은 Windows 프록시 기능을 활성화합니다.

이 정책은 https://crbug.com/644030에서 설명하는 문제와 함께 제공됩니다. [ProxyPacUrl](#proxypacurl) 정책을 통해 설정된 PAC 파일을 포함하여 Windows 코드에서 PAC 파일을 가져오고 실행합니다. PAC 파일에 대한 네트워크 가져오기는 Microsoft Edge 코드 대신 Windows를 통해 수행되므로 [DnsOverHttpsMode](#dnsoverhttpsmode)와 같은 네트워크 정책은 PAC 파일에 대한 네트워크 가져오기에 적용되지 않습니다.

이 정책을 사용하면 Windows 프록시 확인자가 사용됩니다.

이 정책을 사용하지 않거나 구성하지 않으면 Microsoft Edge 프록시 확인자가 사용됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 아니요 - 브라우저 재시작 필요

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>그룹 정책(ADMX) 정보

  - GP 고유 이름: WinHttpProxyResolverEnabled
  - GP 이름: Windows 프록시 해결 프로그램 사용(사용되지 않음)
  - GP 경로 (필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로 (권장): 해당 없음
  - 값 이름: WinHttpProxyResolverEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  

  [맨 위로 이동](#microsoft-edge---policies)

  ### <a name="windowocclusionenabled"></a>WindowOcclusionEnabled

  #### <a name="enable-window-occlusion"></a>창 폐색 사용

  
  
  #### <a name="supported-versions"></a>지원 버전:

  - Windows 89 이상

  #### <a name="description"></a>설명

  Microsoft Edge에서 창 폐색을 사용합니다.

해당 설정을 사용하면 CPU 및 전원 소비량을 줄일 수 있고 Microsoft Edge는 창이 다른 창에 포함된 경우 이를 감지하고 작업 페인팅 픽셀을 일시 중단합니다.

해당 설정을 사용하지 않으면 Microsoft Edge는 창이 다른 창에 포함된 경우 이를 감지하지 않습니다.

해당 정책을 설정하지 않으면 창 숨기기 감지가 사용됩니다.

  #### <a name="supported-features"></a>지원 기능:

  - 필수 사항: 예
  - 권장 사항: 아니요
  - 동적 정책 새로 고침: 예

  #### <a name="data-type"></a>데이터 형식:

  - 부울

  #### <a name="windows-information-and-settings"></a>Windows 정보 및 설정

  ##### <a name="group-policy-admx-info"></a>ADMX(그룹 정책) 정보

  - GP 고유 이름: WindowOcclusionEnabled
  - GP 이름: 창 폐색 사용
  - GP 경로(필수): 관리 템플릿/Microsoft Edge/
  - GP 경로 (권장): 해당 없음
  - GP ADMX 파일 이름: MSEdge.admx

  ##### <a name="windows-registry-settings"></a>Windows 레지스트리 설정

  - 경로 (필수): SOFTWARE\정책\Microsoft\Edge
  - 경로(권장): 해당 없음
  - 값 이름: WindowOcclusionEnabled
  - 값 형식: REG_DWORD

  ##### <a name="example-value"></a>예를 들어 값:

```
0x00000001
```

  

  [맨 위로 이동](#microsoft-edge---policies)


## <a name="see-also"></a>참고 항목

- [Microsoft Edge 구성](configure-microsoft-edge.md)
- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
- [Microsoft Office 보안 기준 블로그](https://techcommunity.microsoft.com/t5/microsoft-security-baselines/bg-p/Microsoft-Security-Baselines)