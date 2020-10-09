---
title: 베타 채널 용 Microsoft Edge 릴리스 정보
ms.author: aguta
author: dan-wesley
manager: srugh
ms.date: 10/07/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 베타 채널 용 Microsoft Edge 릴리스 정보
ms.openlocfilehash: 3108af527697a15875bc615deb6c3efe19a120d3
ms.sourcegitcommit: 5dceccd6f882ce46ed53b8aa9247e115ce5adc7a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104583"
---
# Microsoft Edge 베타 채널에 대한 릴리스 정보

이 릴리스 정보는 Microsoft Edge 베타 채널에 포함된 새로운 기능 및 비보안 업데이트에 대한 정보를 제공합니다.

> [!IMPORTANT]
> [Microsoft Edge 채널 릴리스에서 이 업데이트](https://blogs.windows.com/msedgedev/2020/03/20/update-stable-channel-releases/)를 참조하세요.

## 버전 86.0.622.36 : 10월 7일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 86.0.622.31: 10월 1일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 86.0.622.28: 9월 28일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 86.0.622.15: 9월 14일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 86.0.622.11: 9월 9일

### 기능 업데이트

* **Internet Explorer 모드:**

   * 사용자가 Microsoft UI(사용자 인터페이스)를 사용하여 Internet Explorer 모드에서 사이트를 테스트할 수 있습니다. Microsoft Edge 버전 86부터 관리자는 테스트 목적으로 또는 사이트 목록 XML에 사이트가 추가될 때까지 사용자가 Internet Explorer 모드에서 탭을 로드할 수 있도록 UI 옵션을 사용할 수 있습니다.

* **다운로드 관리자를 사용하여 디스크에서 다운로드를 삭제합니다.** 이제 사용자는 브라우저를 떠나지 않고 디스크에서 다운로드한 파일을 삭제할 수 있습니다. 새로운 다운로드 삭제 기능은 다운로드 쉘프 또는 다운로드 페이지의 컨텍스트 메뉴 내에 있습니다.

* **이전 Microsoft Edge 버전으로 롤백합니다.** 롤백 기능을 통해 관리자는 최신 버전의 Microsoft Edge에 문제가 있는 경우 정상 버전의 Microsoft Edge로 돌아갈 수 있습니다.
[자세한 내용을 알아보세요](edge-learnmore-rollback.md).

* **기업 전체에서 기본적으로 동기화를 사용하도록 강제 설정합니다.**  관리자는 기본적으로 [ForceSync](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#forcesync) 정책을 사용하여 Azure AD(Azure Active Directory) 계정에 대한 동기화를 사용하도록 설정할 수 있습니다.

* **PDF 업데이트:**

  * PDF 문서에 대한 목차입니다. 버전 86부터 Microsoft Edge는 사용자가 PDF 문서를 쉽게 탐색할 수 있도록 목차를 지원합니다.
  * 소형 폼 팩터 화면에서 모든 PDF 기능에 액세스합니다. 화면 크기가 작은 장치에서 Microsoft Edge PDF 판독기의 모든 기능에 액세스합니다.
  * PDF 파일의 형광펜을 지원합니다. 이 업데이트를 통해 사용자는 디지털 펜을 사용하여 실제 형광펜과 용지와 같은 방식으로 PDF 파일의 텍스트를 직접 강조 표시할 수 있습니다.
  * PDF 스크롤이 향상되었습니다. 이제 긴 PDF 문서를 탐색하는 동안 자유롭게 스크롤할 수 있습니다.

* **Windows 7, 8 및 8.1에서 자동으로 프로필이 전환됩니다.** 현재 Windows 10의 Microsoft Edge에서 사용할 수 있는 자동 프로필 스위칭이 하위 수준 Windows(Windows 7, 8, 8.1)로 확장됩니다. 자세한 내용은 [자동 프로필 전환](https://blogs.windows.com/msedgedev/2020/04/30/automatic-profile-switching/) 블로그 게시물을 참조하시기 바랍니다.

* **Microsoft Edge 추가 기능 웹 사이트에서 검색 쿼리를 입력하기 시작하면 자동 완료 제안이 표시됩니다.** 자동 완료를 사용하면 전체 문자열을 입력할 필요 없이 검색 쿼리를 빠르게 완료할 수 있습니다. 이 기능은 사용자가 올바른 철자를 기억할 필요가 없고 표시되는 사용 가능한 옵션 중에서 선택할 수 있으므로 유용합니다.

* **HTML5 Application Cache API를 제거합니다.**  Microsoft Edge 버전 86부터는 웹 페이지를 오프라인으로 사용할 수 있는 기존 Application Cache API가 Microsoft Edge에서 제거되고 있습니다. 웹 개발자는 응용 프로그램 캐시 API를 서비스 작업자로 교체하는 방법에 대한 정보를 위해 [WebDev 문서](https://web.dev/appcache-removal/)을(를) 검토해야 합니다.  중요: Microsoft Edge 버전 90까지 더 이상 사용되지 않는 Application Cache API를 사이트에서 계속 사용할 수 있도록 [AppCache OriginTrial 토큰](https://developers.chrome.com/origintrials/#/view_trial/1776670052997660673)을(를) 요청할 수 있습니다.

* **보안:**

  * 보안 DNS(DNS-over-HTTPS) 지원을 제공합니다.  Microsoft Edge 버전 86부터는 관리되지 않는 디바이스에서 보안 DNS를 제어하는 설정을 사용할 수 있습니다. 이러한 설정은 관리 디바이스의 사용자가 액세스할 수 없지만 IT 관리자는 [damperhtps 모드](https://docs.microsoft.com/deployedge/microsoft-edge-policies#dnsoverhttpsmode) 그룹 정책을 사용하여 보안 DNS를 사용하거나 사용하지 않도록 설정할 수 있습니다.
  * Microsoft Edge는 온라인 누출에서 암호가 발견되면 사용자에게 경고합니다. Microsoft Edge는 암호를 알려진 차단된 자격 증명 저장소와 비교하여 확인하고 일치 항목이 발견되면 사용자에게 알립니다.

* **그룹 정책을 사용하여 사용자 지정 이미지를 새 탭 페이지(NTP)에 추가합니다.** Microsoft Edge 버전 86부터 NTP에는 기본 이미지를 사용자 지정 사용자 제공 이미지로 바꾸는 옵션이 있습니다. 이 이미지의 속성을 관리하는 기능도 그룹 정책에서 지원됩니다.

* **사용자 지정된 바로 가기 키를 VS Code에 일치시킵니다.** Microsoft Edge DevTools는 이제 편집기/IDE와 일치하도록 DevTools의 바로 가기 키 사용자 지정을 지원합니다. Microsoft Edge 84에서는 DevTools 바로 가기 키를 VS Code에 일치시키는 기능을 추가했습니다.

* **하위 수준 Windows 및 MacOS에 대해 [MetricsReportingEnabled]( https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#metricsreportingenabled) 및 [SendSiteInformationToEnhancedServices]( https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sendsiteinfotoimproveservices) 정책을 바꿉니다.** 이러한 정책은 Microsoft Edge 버전 86에서 더 이상 사용되지 않으며 Microsoft Edge 버전 89에서는 사용되지 않습니다.<br>
이러한 정책은 Windows 10에서 [원격측정 허용](https://go.microsoft.com/fwlink/?linkid=2099569) 및 다른 모든 플랫폼에 대한 새 [진단 데이터](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#diagnosticdata) 정책으로 대체됩니다. 이를 통해 사용자는 Microsoft for Windows 7, 8, 8.1 및 MacOS로 전송되는 진단 데이터를 관리할 수 있습니다.

* **SameSite=Lax 쿠키(기본값)**. 웹 보안 및 개인 정보 보호를 향상시키기 위해 기본적으로 쿠키 기본값이 [SameSite=Lax](https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie/SameSite) 처리로 설정됩니다.  즉, 쿠키는 타사 컨텍스트에서만 전송되고 타사에 보낸 요청의 경우에는 생략됩니다. 이와 같이 변경하면 타사 리소스에 대한 쿠키가 있어야 제대로 작동하는 웹 사이트에서 호환성에 영향을 줄 수 있습니다. 이와 같은 쿠키를 허용하려면 웹 개발자가 쿠키를 설정할 때 명시적 `SameSite=none` 및 `Secure` 특성을 추가하여 타사 컨텍스트에서 설정하고 해당 컨텍스트로 보내야 하는 쿠키를 표시할 수 있습니다. 해당 변경에서 특정 사이트를 제외하려는 기업에서는 [LegacySameSiteCookieBehaviorEnabledForDomainList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#legacysamesitecookiebehaviorenabledfordomainlist) 정책을 사용하여 해당 작업을 하거나 [LegacySameSiteCookieBehaviorEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#legacysamesitecookiebehaviorenabled) 정책을 사용하여 모든 사이트에서 변경 내용을 옵트아웃할 수 있습니다.

### 정책 업데이트

#### 새로운 정책

19개의 새로운 정책이 추가되었습니다. [Microsoft Edge Enterprise 랜딩 페이지](https://aka.ms/EdgeEnterprise)에서 업데이트된 관리 템플릿을 다운로드합니다. 다음과 같은 새 정책이 추가되었습니다.

- [CollectionsServicesAndExportsBlockList](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#collectionsservicesandexportsblocklist) - 지정된 서비스 목록에 대한 액세스를 차단하고 컬렉션에서 대상을 내보내기합니다.
- [DefaultSensorSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultsensorssetting) - 기본 센서 설정입니다.
- [DefaultSerialGuardSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultserialguardsetting) - 직렬 API의 사용을 제어합니다.
- [진단 데이터](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#diagnosticdata) - 브라우저 사용에 대한 필수 및 선택적 진단 데이터를 전송합니다.
- [EnterpriseModeSiteListManagerAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#enterprisemodesitelistmanagerallowed) - 엔터프라이즈 모드 사이트 목록 관리자 도구에 대한 액세스를 허용합니다.
- [ForceSync](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#forcesync) - 브라우저 데이터의 동기화를 강제 적용하고 동기화 동의 메시지를 표시하지 않습니다.
- [InsecureFormsWarningsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#insecureformswarningsenabled) - 안전하지 않은 양식에 대해 경고를 사용합니다.
- [InternetExplorerIntegrationTestingAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#internetexplorerintegrationtestingallowed) - Internet Explorer 모드 테스트를 허용합니다.
- [SpotlightExperiencesAndRecommendationsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#spotlightexperiencesandrecommendationsenabled) - 사용자가 Microsoft 서비스에 대한 사용자 지정 배경 이미지와 텍스트, 제안 사항, 알림 및 팁을 받을 수 있는지 여부를 선택합니다.
- [NewTabPageAllowedBackgroundTypes](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#newtabpageallowedbackgroundtypes) - 새 탭 페이지 레이아웃에 허용된 배경 유형을 구성합니다.
- [SaveCookiesOnExit](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#savecookiesonexit) - Microsoft Edge가 닫힐 때 쿠키를 저장합니다.
- [SensorsAllowedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sensorsallowedforurls) - 특정 사이트의 센서에 대한 액세스를 허용합니다.
- [SensorsBlockedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sensorsblockedforurls) - 특정 사이트의 센서에 대한 액세스를 차단합니다.
- [SerialAskForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#serialaskforurls) - 특정 사이트에서 직렬 API를 허용합니다.
- [SerialBlockedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#serialblockedforurls) - 특정 사이트에서 직렬 API를 차단합니다.
- [URLBlocklist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#urlblocklist) - URL 목록에 대한 액세스를 차단합니다.
- [URLLowlist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#urlallowlist) - 허용된 URL 목록을 정의합니다.
- [UserAgentClientHintsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#useragentclienthintsenabled) - 사용자-에이전트 클라이언트 힌트 기능을 사용하도록 설정합니다.
- [UserDataSnapshotRetentionLimit](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#userdatasnapshotretentionlimit) - 비상 롤백 시 사용하기 위해 보존된 사용자 데이터 스냅샷 수를 제한합니다.

#### 사용되지 않는 정책

- [MetricsReportingEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#metricsreportingenabled) - 사용 및 충돌 관련 데이터보고를 사용하도록 설정합니다.
- [SendSiteInfoToImproveServices](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sendsiteinfotoimproveservices) - Microsoft 서비스를 개선하기 위해 사이트 정보를 보냅니다.

#### 폐기된 정책

[TLS13HardeningForLocalAnchorsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#tls13hardeningforlocalanchorsenabled) - 로컬 신뢰 앵커에 대한 TLS 1.3 보안 기능을 사용하세요.

#### 변경된 정책 캡션

[NativeWindowCocclusionEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#nativewindowocclusionenabled) - 원본 창 숨김을 사용합니다.

#### 변경된 정책 설명

- [AdsSettingForIntrusiveAdsSites](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#adssettingforintrusiveadssites)
- [AllowTokenBindingForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#allowtokenbindingforurls)
- [AmbientAuthenticationInPrivateModesEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#ambientauthenticationinprivatemodesenabled)
- [ApplicationGuardContainerProxy](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#applicationguardcontainerproxy)
- [AutoImportAtFirstRun](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#autoimportatfirstrun)
- [AutoOpenFileTypes](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#autoopenfiletypes)
- [BrowserSignin](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#browsersignin)
- [ClearBrowsingDataOnExit](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#clearbrowsingdataonexit) 
- [ClickOnceEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#clickonceenabled)
- [CommandLineFlagSecurityWarningsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#commandlineflagsecuritywarningsenabled)
- [ConfigureOnPremisesAccountAutoSignIn](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#configureonpremisesaccountautosignin)
- [ConfigureShare](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#configureshare)
- [CookiesAllowedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#cookiesallowedforurls)
- [CustomHelpLink](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#customhelplink)
- [DefaultCookiesSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultcookiessetting)
- [DefaultGeolocationSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultgeolocationsetting)
- [DefaultImagesSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultimagessetting)
- [DefaultInsecureContentSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultinsecurecontentsetting)
- [DefaultJavaScriptSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultjavascriptsetting)
- [DefaultNotificationsSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultnotificationssetting)
- [DefaultPluginsSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultpluginssetting)
- [DefaultPopupsSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultpopupssetting)
- [DefaultSearchProviderEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultsearchproviderenabled)
- [DefaultWebBluetoothGuardSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultwebbluetoothguardsetting)
- [DefaultWebUsbGuardSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultwebusbguardsetting)
- [DelayNavigationsForInitialSiteListDownload](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#delaynavigationsforinitialsitelistdownload)
- [DeveloperToolsAvailability](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#developertoolsavailability)
- [EnableSha1ForLocalAnchors](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#enablesha1forlocalanchors)
- [DownloadRestrictions](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#downloadrestrictions)
- [EnableDeprecatedWebPlatformFeatures](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#enabledeprecatedwebplatformfeatures)
- [WinHttpProxyResolverEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#winhttpproxyresolverenabled)
- [ExperimentationAndConfigurationServiceControl](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#experimentationandconfigurationservicecontrol)
- [ExternalProtocolDialogShowAlwaysOpenCheckbox](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#externalprotocoldialogshowalwaysopencheckbox)
- [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)
- [ForceBingSafeSearch](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#forcebingsafesearch)
- [ForceYouTubeRestrict](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#forceyoutuberestrict)
- [HomepageIsNewTabPage](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#homepageisnewtabpage)
- [HomepageLocation](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#homepagelocation)
- [InPrivateModeAvailability](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#inprivatemodeavailability)
- [InternetExplorerIntegrationEnhancedHangDetection](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#internetexplorerintegrationenhancedhangdetection)
- [InternetExplorerIntegrationLevel](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#internetexplorerintegrationlevel)
- [InternetExplorerIntegrationSiteRedirect](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#internetexplorerintegrationsiteredirect)
- [LegacySameSiteCookieBehaviorEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#legacysamesitecookiebehaviorenabled)
- [NativeWindowOcclusionEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#nativewindowocclusionenabled)
- [NavigationDelayForInitialSiteListDownloadTimeout](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#navigationdelayforinitialsitelistdownloadtimeout)
- [NetworkPredictionOptions](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#networkpredictionoptions)
- [NewTabPageLocation](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#newtabpagelocation)
- [NewTabPageSearchBox](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#newtabpagesearchbox)
- [NewTabPageSetFeedType](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#newtabpagesetfeedtype)
- [NonRemovableProfileEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#nonremovableprofileenabled)
- [PasswordProtectionWarningTrigger](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#passwordprotectionwarningtrigger)
- [PasswordProtectionLoginURLs](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#passwordprotectionloginurls)
- [PasswordProtectionChangePasswordURL](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#passwordprotectionchangepasswordurl)
- [PluginsAllowedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#pluginsallowedforurls)
- [PluginsBlockedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#pluginsblockedforurls)
- [PreventSmartScreenPromptOverride](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#preventsmartscreenpromptoverride)
- [PreventSmartScreenPromptOverrideForFiles](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#preventsmartscreenpromptoverrideforfiles)
- [ProxyMode](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxymode)
- [RegisteredProtocolHandlers](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#registeredprotocolhandlers)
- [RelaunchNotification](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#relaunchnotification)
- [RestoreOnStartup](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#restoreonstartup)
- [RestoreOnStartupURLs](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#restoreonstartupurls)
- [RestrictSigninToPattern](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#restrictsignintopattern)
- [SSLVersionMin](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sslversionmin)
- [SmartScreenAllowListDomains](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#smartscreenallowlistdomains)
- [SmartScreenEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#smartscreenenabled)
- [SmartScreenForTrustedDownloadsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#smartscreenfortrusteddownloadsenabled)
- [SmartScreenPuaEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled)
- [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled)
- [TrackingPrevention](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#trackingprevention)
- [WebRtcLocalhostIpHandling](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webrtclocalhostiphandling)

<!-- end 86 -->

## 버전 85.0.564.41: 8월 25일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 85.0.564.40: 8월 21일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 85.0.564.36: 8월 17일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 85.0.564.30: 8월 10일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 85.0.564.23: 8월 3일

다양한 버그와 성능 문제를 해결했습니다.

<!--- BEGIN 85 ---->
## 버전 85.0.564.18: 7월 28일

### 기능 업데이트

- **즐겨찾기 및 설정의 온-프레미스 동기화** 이제 클라우드 동기화 없이도 사용자 환경 내에서 Active Directory 프로필 간에 브라우저 즐겨찾기 및 설정을 동기화할 수 있습니다.

- **Microsoft Edge 그룹 정책 지원 - 신뢰할 수 있는 사이트 + 앱 콤보가 확인 프롬프트 없이 실행됩니다.** 관리자가 확인 프롬프트 없이 시작할 수 있는 신뢰할 수 있는 사이트 + 앱 조합을 추가할 수 있는 그룹 정책 지원이 추가되었습니다. 이렇게 하면 관리자가 앱 프로토콜이 포함된 URL로 이동할 때 최종 사용자가 확인 메시지를 표시하지 않도록 신뢰할 수 있는 프로토콜/원본 조합(예: Microsoft 365 앱)을 구성할 수 있습니다.

- **PDF 형광펜 도구** 이 도구를 PDF 도구 모음에 추가하여 중요한 텍스트를 쉽게 강조 표시할 수 있습니다.

- **스토리지 Access API를 사용할 수 있습니다**. 사용자가 브라우저의 현재 구성에 의해 차단될 수 있는 스토리지를 허용하려는 직접적인 의도를 제공한 경우 Storage Access API를 통해 타사 컨텍스트에서 타사 스토리지에 액세스할 수 있습니다. 자세한 내용은 [스토리지 액세스 API](https://www.chromestatus.com/feature/5612590694662144)을(를) 참조하시기 바랍니다.

- **Send to OneNote는 Microsoft Edge Collections에서 사용할 수 있습니다**. 모음에서 수집한 정보를 OneNote에 보내 더 큰 프로젝트에 추가하고 다른 사람들과 협업할 수 있게 되어 모두가 들떠 있습니다! 또한 Microsoft Edge 85에서는 MSA 및 Azure Active Directory의 *Office for Mac* 제품(Word, Excel 및 OneNote)에 컨텐츠를 전송할 수 있습니다.

- **DevTools가 업데이트** 다음 업데이트에 대한 자세한 내용은 [DevTools의 새로운 기능(Microsoft Edge 85)](https://docs.microsoft.com/microsoft-edge/devtools-guide-chromium/whats-new/2020/06/devtools)을(를) 참조하시기 바랍니다.

   - Microsoft Edge DevTools는 Surface Duo 에뮬레이션을 지원합니다. Microsoft Edge DevTools는 Surface Duo를 에뮬레이트하여 듀얼 스크린 장치에서 웹 콘텐츠가 어떻게 표시되는지 테스트할 수 있습니다. DevTools에서 이 실험을 실행하려면 Windows에서 Ctrl+Shift+M을 누르거나 MacOS에서 Command+Shift+M을 눌러 장치 모드로 들어간 다음 장치 드롭다운 목록에서 Surface Duo를 선택합니다.
   - Microsoft Edge DevTools를 사용하면 바로 가기 키를 VS Code에 연결할 수 있습니다. Microsoft Edge DevTools는 편집기/IDE와 일치하도록 DevTools의 바로 가기 키 사용자 지정을 지원합니다. Microsoft Edge 85에서는 DevTools 바로 가기 키를 VS Code에 일치시키는 기능을 추가하고 있습니다. 이러한 변경은 VS Code 및 DevTools 전체에서 생산적으로 증가하는 데 도움이 됩니다.

### 정책 업데이트

#### 새로운 정책

13개의 새로운 정책이 추가되었습니다. [Microsoft Edge Enterprise 랜딩 페이지](https://aka.ms/EdgeEnterprise)에서 업데이트된 관리 템플릿을 다운로드합니다. 다음과 같은 새 정책이 추가되었습니다.

- [AutoLaunchProtocolsFromOrigins](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#autolaunchprotocolsfromorigins) - 사용자에게 묻지 않고 나열된 원본에서 외부 애플리케이션을 실행할 수 있는 프로토콜 목록 정의
- [AutoOpenAllowedForURLs](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#autoopenallowedforurls) - AutoOpenFileTypes를 적용할 수 있는 URL
- [AutoOpenFileTypes](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#autoopenfiletypes) - 다운로드 시 자동으로 열어야 하는 파일 형식 목록
- [DefaultSearchProviderContextMenuAccess허용됨](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultsearchprovidercontextmenuaccessallowed) - 기본 검색 공급자의 상황에 맞는 메뉴 검색 액세스 허용합니다.
- [EnableSha1ForLocalAchors](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#enablesha1forlocalanchors) - 로컬 트러스트 앵커에서 발급한 경우 SHA-1을 사용하여 서명한 인증서 허용합니다.
- [ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#exemptdomainfiletypepairsfromfiletypedownloadwarnings) - 도메인에서 지정된 파일 형식에 대해 파일 형식 확장명 기반 주의 다운로드를 사용설정 해제합니다.
- [IntensiveWakeUpThrottlingEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#intensivewakeupthrottlingenabled) - IntegratedWakeUpThrotling 기능 제어
- [NewTabPagePrerenderEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#newtabpageprerenderenabled) - 렌더링 속도를 높이기 위해 새 탭 페이지의 사전 로드 사용
- [NewTabPageSearchBox](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#newtabpagesearchbox) - 새 탭 페이지 검색 상자 환경 구성
- [PasswordMonitorAllowed ](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#passwordmonitorallowed) - 암호가 안전하지 않은 경우 사용자에게 경고를 보낼 수 있도록 허용
- [RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled) - Microsoft Edge 프로파일 데이터에 로밍 복사본 사용
- [ RoamingProfileLocation ](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilelocation) - 로밍 프로파일 디렉토리 설정
- [TLSCipherSuiteDenyList](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#tlsciphersuitedenylist) - 사용하지 않도록 설정할 TLS 암호 그룹을 지정

#### 폐기된 정책

- [EnableDomainActionsDownload](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#enabledomainactionsdownload) - Microsoft에서 도메인 작업 다운로드 사용
- [WebComponentsV0Enabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webcomponentsv0enabled) - M84까지 웹 구성 요소 v0 API를 다시 사용하도록 설정합니다.
- [ WebDriverOverridesIncompatiblePolicies ](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webdriveroverridesincompatiblepolicies)- 웹 드라이버가 비호환 정책을 재정의하도록 허용

<!--- END ---->

## 버전 84.0.522.35: 7월 9일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 84.0.522.28: 6월 26일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 84.0.522.26: 6월 24일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 84.0.522.20: 6월 15일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 84.0.522.15: 7월 8일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 84.0.522.11: 6월 2일

### 기능 업데이트

- 이 버전의 Microsoft Edge는 Internet Explore 모드에 대한 개선된 사이트 목록 다운로드 항목을 제공합니다.  캐시 사이트 목록이 없는 경우 Internet Explorere 모드 사이트 목록의 다운로드 지연 시간을 0초(60초 지연에서 개선)로 줄였습니다. Internet Explorer 모드 홈페이지 탐색이 사이트 목록이 다운로드 될 때까지 지연되는 경우 그룹 지원 정책을 추가 했습니다. 자세한 내용은 [DelayNavigationsForInitialSiteListDownload](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#delaynavigationsforinitialsitelistdownload) policy를 참조하세요.

- Microsoft Edge에서 이제 Windows 10에서 "관리자 권한으로 실행"하고 있는 사용자가 브라우저에 로그인 할 수 있도록 허용합니다. 이것은 Windows 서버 혹은 원격 데스크톱 및 샌드박스 시나리오에서 Microsoft Edge를 실행하는 고객에게 도움이 됩니다.

- Microsoft Edge는 이제 전체 화면 모드에서 전체 마우스를 지원합니다. 이제 전체 화면 모드를 종료 하지 않고도 마우스를 사용하여 탭, 주소 표시줄 및 기타 항목에 액세스할 수 있습니다.

- 온라인 구입 개선 저장 된 직불 또는 신용 카드에 소비자 지정 애칭을 추가합니다. 이제 온라인으로 구매할 때 신용 카드를 구별 및 구분할 수 있습니다. 직불 또는 신용 카드에 애칭을 정하면 자동 충전 지불 방식을 선택 할 때 올바른 카드를 선택 할 수 있습니다.

- TLS/1.0 및 TLS/1.1은 기본적으로 사용 하지 않도록 설정 되어 있습니다. 영향받는 사이트 검색하기 위해 *edge://flags/#display-legacy-tls-warnings*를 설정하여 플래그가 Microsoft Edge로 하여금 레거시 TLS 프로토콜을 필요로 하는 페이지를 로드할 때 차단하지 않은 “안전하지 않은” 알림을 표시하도록 합니다. [SSLVersionMin](https://docs.microsoft.com/deployedge/microsoft-edge-policies#sslversionmin) 정책은 TLS/1.0 및 TLS/1.1을 다시 사용하도록 허용 합니다. 이 정책은 적어도 Microsoft Edge 버전 88 까지는 계속 사용할 수 있습니다. 자세한 내용은 [사이트 호환성-Microsoft Edge로 들어오는 변화에 영향](https://docs.microsoft.com/microsoft-edge/web-platform/site-impacting-changes)을 참조하세요.

- 컬렉션 개선:

  - 노트 기능이 추가 되어 컬렉션에 있는 항목에 메모 또는 주석을 추가할 수 있습니다. 노트를 그룹화하여 컬렉션의 항목을 정렬 하는 경우에도 항목에 계속 첨부되어 있습니다. 이 새로운 기능을 사용해 보세요. 항목을 마우스 오른쪽 단추로 클릭하고 "메모 추가"를 선택합니다.
  - 컬렉션에서 노트의 배경색을 변경할 수 있습니다. 색 코드를 사용하여 정보를 구성하고 생산성을 향상 시킬 수 있습니다.
  - 성능이 크게 향상 되어 이전 버전의 Microsoft Edge 보다 훨씬 적은 시간에 컬렉션을 Excel로 내보낼 수 있습니다.

- 추가 Microsoft Edge API 지원:

  - 저장소 액세스 API. 이 API를 사용하면 사용자가 브라우저의 현재 구성에 따라 차단되는 저장소를 허용하는 직접 의도가 제공되는 경우 3자 콘텐츠에서 1차 저장소에 액세스를 허용 합니다.

    사용자에게 개인 정보 보호가 점차 더 중요해 지듯 모든 3자 저장소 액세스를 차단하는 것과 같은 엄격한 브라우저 기본값과 사용자 옵트인 설정이 점차 보편화 되고 있습니다. 이 설정을 사용하면 개인 정보 보호를 개선하고 알 수 없는 사용자나 신뢰하지 않은 사용자로부터의 원치 않는 액세스를 차단함과 동시에 사용자가 보기를 원하는 콘텐츠를 차단하는 원치 않는 부작용이 발생할 수 있습니다 (예: 소셜 미디어 및 미디어 포함된 콘텐츠).

  - 기본 파일 시스템 API을 통해 파일 또는 폴더를 편집 할 수 있는 권한을 사이트에 제공할 수 있는 기본 파일 시스템 API.

- PDF 개선:

  - PDF를 소리 내어 읽기를 사용하면 사용자는 중요한 다른 작업을 수행 하면서 PDF 콘텐츠를 들을 수 있습니다. 오디오 시각적 학습자가 콘텐츠 읽기에 중점을 두고 손쉽게 배울 수도 있습니다.
  - PDF 파일 편집 기능이 개선 되었습니다. 이제 PDF를 편집할 때마다 복사본을 저장하는 대신 PDF 편집 내용을 다시 파일에 저장할 수 있습니다.

- 이제 Microsoft Edge에서 몰입형 독자 번역을 사용할 수 있습니다. 사용자가 몰입형 독자 보기를 열면 페이지를 원하는 언어로 번역하기 옵션이 표시됩니다.

- DevTools는 VS 코드를 포함 하는 편집기/IDE에 맞게 바로 가기 키를 사용자 지정 하는 기능을 지원 합니다.

### 정책 업데이트

#### 새로운 정책

새 정책 5개를 추가했습니다. [Microsoft Edge Enterprise 랜딩 페이지](https://aka.ms/EdgeEnterprise)에서 업데이트된 관리 템플릿을 다운로드합니다. 다음과 같은 새 정책이 추가되었습니다.

- [AppCacheForceEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#appcacheforceenabled) - 이름: AppCache 기능이 기본적으로 해제되어 있더라도 다시 사용할 수 있도록 허용
- [ApplicationGuardContainerProxy](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#applicationguardcontainerproxy) - 응용 프로그램 보호 컨테이너 프록시
- [DelayNavigationsForInitialSiteListDownload](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#delaynavigationsforinitialsitelistdownload) - 탭 탐색 전에 엔터프라이즈 모드 사이트 목록을 사용하도록 요청
- [NativeWindowOcclusionEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#nativewindowocclusionenabled) - 원시 창 숨김을 사용합니다.
- [NavigationDelayForInitialSiteListDownloadTimeout](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#navigationdelayforinitialsitelistdownloadtimeout) - 엔터프라이즈 모드 사이트 목록에 대한 탭 탐색 지연 시간 설정

#### 더 이상 사용되지 않는 정책

- [AllowSyncXHRInPageDismissal](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#allowsyncxhrinpagedismissal) - 페이지를 해제하는 동안 페이지에서 동기 XHR 요청 전송 허용
- [BuiltinCertificateVerifierEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#builtincertificateverifierenabled) - 서버 인증서를 확인하는 데 기본 제공 인증서 검증 도구를 사용할지 여부를 결정합니다.
- [ StricterMixedContentTreatmentEnabled ](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#strictermixedcontenttreatmentenabled) -혼합 컨텐츠에 대해 보다 엄격한 처리를 사용합니다.

#### 폐기된 정책

[ForceNetworkInProcess](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#forcenetworkinprocess) 브라우저 프로세스에서 네트워킹 코드의 실행 강제

<!-- end 84 -->

## 버전 83.0.478.44: 6월 1일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 83.0.478.37: 5월 20일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 83.0.478.33: 5월 15일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 83.0.478.28: 5월 7일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 83.0.478.25: 5월 4일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 83.0.478.18: 4월 27일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 83.0.478.13: 4월 22일

### 기능 업데이트

- Microsoft Defender SmartScreen 개선 사항: 로드 시 리디렉션하는 유해 사이트에 대해 강화된 보안, Microsoft Defender SmartScreen 보안 페이지를 사용하여 유해 사이트를 완전히 대체하는 최상위 프레임 차단 기능 등 Microsoft Defender SmartScreen 서비스에 대한 몇 가지 사항을 개선했습니다. 최상위 프레임 차단 기능은 유해 사이트로부터 오디오 및 기타 미디어의 재생을 차단하여 보다 간편하고 복잡하지 않은 환경을 제공합니다.

- 사용자 피드백을 반영하여 사용자는 이제 브라우저를 닫을 때 특정 쿠키가 자동으로 제거되는 것을 제외할 수 있습니다. 이 선택 사항은 해당 기능은 사용자가 로그아웃을 원하지 않지만 브라우저를 닫을 때 다른 모든 쿠키를 제거하기를 원하는 사이트가 있는 경우에 유용합니다. 해당 기능을 사용하려면 *edge://settings/clearBrowsingDataOnClose*로 이동하고 “쿠키 및 기타 사이트 데이터”를 설정하거나 해제합니다.

- 이제 전체 프로필에서 보다 간편하게 작업 콘텐츠를 확인할 수 있도록 자동 프로필 전환 기능을 사용할 수 있습니다. 회사에서 여러 프로필을 사용하는 경우 개인 프로필에서 회사나 학교 계정의 인증이 필요한 사이트로 이동하여 프로필을 확인할 수 있습니다. 해당 변경 감지된 경우 인증하지 않고 해당 사이트에 액세스할 수 있도록 회사 프로필로 전환하라는 메시지가 표시됩니다. 전환하려는 회사 프로필을 선택하면 해당 웹 사이트는 회사 프로필에서 열립니다. 프로필 전환 기능이 사용자의 회사 및 개인 데이터를 별도로 유지하고 더욱 간편하게 회사 콘텐츠에 액세스하는 데 도움이 될 것입니다. 이 기능을 통해 프로필을 전환하라는 메시지가 표시되지 않도록 하려면 이 메시지를 다시 표시 안 함 옵션을 선택하여 메시지가 표시되지 않게 할 수 있습니다.

- 컬렉션 기능 개선:
  - 끌어서 놓기를 사용하여 컬렉션을 열지 않고 항목을 컬렉션에 추가할 수 있습니다. 끌어서 놓기를 수행하는 동안 항목을 추가할 컬렉션 목록에서 위치를 선택할 수도 있습니다.
  - 컬렉션에 항목을 한 번에 하나씩 추가하지 않고 여러 항목을 추가할 수 있습니다. 여러 항목을 추가하려면 항목을 선택한 다음 컬렉션으로 끕니다. 또는 항목을 선택한 다음 마우스 오른쪽 단추로 클릭하고 항목을 추가할 컬렉션을 선택할 수 있습니다.

- Edge 창에서 모든 탭을 개별적으로 추가하지 않고도 새 컬렉션에 추가할 수 있습니다. 모든 탭을 추가하려면 아무 탭에서 마우스 오른쪽 단추를 클릭하고 "새 컬렉션에 모든 탭 추가"를 선택합니다.

- 이제 확장 동기화를 사용할 수 있습니다. 이제 모든 장치에서 확장을 동기화할 수 있습니다! Microsoft 및 Chrome 스토어 모두에서 가져온 확장이 Microsoft Edge와 동기화됩니다. 해당 기능을 사용하려면 메뉴 표시줄에서 타원형의 (**…**)을(를) 클릭하고 **설정**을 선택합니다. 사용자의 프로필에서 **동기화**를 클릭하고 동기화 옵션을 확인합니다. **프로필/동기화**에서 설정/해제를 사용하여 확장을 활성화합니다. [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled) 그룹 정책을 사용하여 확장 동기화를 해제할 수 있습니다.

- 차단된 비보안 다운로드에 대한 다운로드 관리 페이지의 메시지가 개선되었습니다.

- 몰입형 리더 개선 사항:
  - 몰입형 리더에서 말하는 음성 경험 부분의 부사에 대한 지원이 추가되었습니다. 몰입형 리더에서 기사를 읽는 동안 문법 도구를 열고 품사 내 부사를 켜서 페이지의 모든 부사를 강조 표시하세요.
  - 웹 페이지에서 콘텐츠를 선택하고 몰입형 리더에서 여는 기능을 추가했습니다. 이 기능을 사용하면 사용자가 모든 웹 사이트에서 몰입형 리더와 줄 포커스, 소리내어 읽기와 같은 모든 학습 도구를 사용할 수 있습니다.

- 링크 의사는 URL을 잘못 입력한 사용자에게 호스트 수정 및 검색 쿼리를 제공 합니다. 예를 들어 다음과 같은 가치를 제공해야 합니다. <br>
사용자가 "powerbi를 "powerbbi".com으로 잘못 입력함. 링크 의사는 수정사항으로 “powerbi”.com을 제시하며 사용자가 원하는 것이 다를 경우에 대비해 “powerbbi” 링크 검색을 생성합니다.

- 사용자가 특정 사이트에 대한 외부 프로토콜을 실행하기로 한 결정을 저장할 수 있도록 합니다. 사용자는이 기능을 사용 하거나 사용 하지 않도록 [ExternalProtocolDialogShowAlwaysOpenCheckbox]( https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#externalprotocoldialogshowalwaysopencheckbox) 정책을 구성할 수 있습니다.

- 사용자는 Microsoft Edge **설정**에서 직접 Microsoft Edge를 기본 브라우저로 설정할 수 있습니다. 사용자가 운영 시스템 설정에서 검색하는 대신 브라우저 자체에서 기본 브라우저를 변경하기 용이하도록 합니다. 이 기능을 사용하기 위해서는 *edge://settings/defaultBrowser*로 이동하고 **기본으로 설정** 클릭.

- 새로운 신규 디버깅 지원을 포함한 몇 DevTools 업데이트, UI 개선 등. 세부 내용은 [DevTools 새로운 소식(Microsoft Edge 83)](https://docs.microsoft.com/microsoft-edge/devtools-guide-chromium/whats-new/2020/03/devtools)을 참조하세요.

### 정책 업데이트

#### 새로운 정책

새 정책 15개를 추가했습니다. [Microsoft Edge Enterprise 랜딩 페이지](https://aka.ms/EdgeEnterprise)에서 업데이트된 관리 템플릿을 다운로드합니다. 다음과 같은 새 정책이 추가되었습니다.

- [AllowSurfGame](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#allowsurfgame) - 게임 서핑을 허용합니다.
- [AllowTokenBindingForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#allowtokenbindingforurls) - Microsoft Edge에서 토큰 바인딩을 설정하려는 사이트 목록을 구성합니다.
- [BingAdsSuppression](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#bingadssuppression) - Bing 검색 결과에 대해 모든 광고를 차단합니다.
- [BuiltinCertificateVerifierEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#builtincertificateverifierenabled) - 서버 인증서를 확인하는 데 기본 제공 인증서 검증 도구를 사용할지 여부를 결정합니다.
- [ClearCachedImagesAndFilesOnExit](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#clearcachedimagesandfilesonexit) - Microsoft Edge를 종료할 때 캐시된 이미지 및 파일을 삭제합니다.
- [ConfigureShare](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#configureshare) - 공유 환경을 구성합니다.
- [DeleteDataOnMigration](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#deletedataonmigration) - 마이그레이션에서 이전 브라우저 데이터를 삭제합니다.
- [DnsOverHttpsMode](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#dnsoverhttpsmode) - DoH(DNS over HTTPS) 모드를 제어합니다.
- [DnsOverHttpsTemplates](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#dnsoverhttpstemplates) - 원하는 DoH(DNS over HTTPS) 확인자의 URI 서식 파일을 지정합니다.
- [FamilySafetySettingsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#familysafetysettingsenabled) - 사용자가 가족 보호를 구성할 수 있도록 허용합니다.
- [LocalProvidersEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#localprovidersenabled) - 로컬 공급자의 제안을 허용합니다.
- [ScrollToTextFragmentEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#scrolltotextfragmentenabled) - URL 조각에 지정된 텍스트로 스크롤할 수 있습니다.
- [ScreenCaptureAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#screencaptureallowed) - 화면 캡처를 허용하거나 거부합니다.
- [SynctypesListdisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled) - 동기화에서 제외되는 유형의 목록을 구성합니다.
- [NativeWindowOcclusionEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#nativewindowocclusionenabled) - 원시 창 숨김을 사용합니다.

#### 더 이상 사용되지 않는 정책

이 릴리스에서는 다음 정책이 계속 작동합니다. 이 정책들은 향후 릴리스에서는 "폐기"될 것입니다.

[EnableDomainActionsDownload](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#enabledomainactionsdownload) Microsoft에서 도메인 작업 다운로드 가능

<!--  end 83 -->

## 버전 81.0.416.60: 4월 20일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 81.0.416.58: 4월 17일

보안 업데이트.

## 버전 81.0.416.50: 4월 10일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 81.0.416.45: 4월 3일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 81.0.416.41: 3월 30일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 81.0.416.34: 3월 17일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 81.0.416.31: 3월 12일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 81.0.416.28: 3월 9일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 81.0.416.20: 2월 28일

다양한 버그와 성능 문제를 해결했습니다.

## 버전 81.0.416.12: 2월 20일

### 기능 업데이트

- 이제 컬렉션을 사용할 수 있습니다. 주소 표시줄 옆에 있는 컬렉션 아이콘을 클릭하여 시작할 수 있습니다. 이 작업을 수행하면 컬렉션을 만들고 편집하고 볼 수 있는 컬렉션 창이 열립니다. 사용자가 웹에서 수행한 작업을 기반으로 컬렉션을 디자인했습니다. 쇼핑객, 여행자, 교사 또는 학생인 경우 컬렉션이 도움이 될 수 있습니다. [자세한 내용을 알아보세요](https://blogs.windows.com/msedgedev/2019/12/09/improvements-collections-sync-microsoft-edge/#LuDPRDUDCgdgdOVt.97).

- 일관성을 유지하려면 Microsoft Edge 도구 모음에서 컬렉션 버튼 제거(도구 모음에서 숨기기)를 허용하세요.

- 온-프레미스 Active Directory 계정 자동 로그인은 이를 설정한 조직만을 대상으로 합니다.  사용자가 이미 온-프레미스 AD 계정으로 로그인한 경우 해당 계정에서 로그아웃될 수 있습니다. 이제 사용자는 운영 체제에서 기본 계정이 MSA 또는 Azure AD 계정인 경우에만 기본 계정으로 자동 로그인됩니다. 관리자는 ConfigureOnPremisesAccountAutoSignIn 정책을 사용하는 온-프레미스 AD 계정으로 자동 로그인을 설정할 수 있습니다.

- Application Guard 이제 컨테이너에서 확장 지원을 사용할 수 있습니다.

- Internet Explorer 모드에서 열도록 구성된 페이지로 이동할 때 Internet Explorer가 설치되지 않았음을 사용자에게 알리는 메시지를 추가했습니다.

- z-인덱스 스택 컨텍스트를 디버깅하는 데 도움이 되는 새로운 기능으로 Microsoft Edge DevTools의 3D 보기 도구를 업데이트했습니다. 3D 보기는 색상 및 스태킹을 사용하여 DOM(문서 개체 모델) 깊이를 표시하며 z-인덱스 보기는 페이지의 여러 스태킹 컨텍스트를 분리하는 데 도움이 됩니다. [자세한 내용을 알아보세요](https://blogs.windows.com/msedgedev/2020/01/23/debug-z-index-3d-view-edge-devtools/).

- F12 Dev 도구를 10 개의 새로운 언어로 현지화하여 나머지 브라우저에서 사용되는 언어와 일치합니다. [자세한 내용을 알아보세요](https://blogs.windows.com/msedgedev/2020/02/04/localizing-edge-devtools/).

- 돌비 비전 재생에 대한 지원이 추가되었습니다. 돌비 비전 사용 Windows 10 빌드 17134(2018년 4월 업데이트) 웹사이트에서 돌비 비전 콘텐츠를 표시할 수 있습니다. [Netflix](https://help.netflix.com/en/node/42384)에서 Dolby Vision 컨텐츠를 활성화하는 방법을 참조하세요.

- Microsoft Edge는 이제 중복 즐겨찾기를 식별 및 제거하고 동일한 이름의 폴더를 병합할 수 있습니다. 이 도구에 액세스하려면 브라우저 툴바에서 별표를 클릭하고 "중복 즐겨찾기 제거"를 선택하십시오.  변경 사항을 확인할 수 있으며 즐겨찾기에 대한 모든 업데이트가 디바이스 간에 동기화됩니다.

- 어두운 테마의 일반 브라우징 창을 InPrivate 창과 구별하기가 어려울 수 있다고 들었습니다. 두 창 프레임이 모두 어둡기 때문입니다. 오른쪽 상단 모서리에 있는 새로운 솔리드 InPrivate 탄환은 사용자가 InPrivate를 탐색하고 있는지 확인하도록 도와줍니다.

- 올바른 브라우저 프로필에서 외부 링크를 여세요. *edge://settings/multiProfileSettings*에서 외부 앱용으로 열린 링크에 대한 기본 프로필을 선택하십시오.

- 이전에 계정으로 로그인한 후 다른 계정으로 브라우저 프로필에 로그인하는 사용자에게 경고를 보내는 알림 기능이 추가되었습니다. 이는 의도하지 않은 데이터 병합을 방지하는 데 도움이 됩니다.

- Microsoft 계정에 결제 카드를 저장한 경우 결제 양식을 작성하는 동안 Microsoft Edge에서 사용할 수 있습니다. Microsoft 계정의 카드는 데스크톱 장치간에 동기화되며 2단계 인증(CVC 코드 및 Microsoft ID) 후 전체 세부 정보가 웹 사이트와 공유됩니다. 더욱 편리하도록 인증하는 동안 장치에서 카드 사본을 안전하게 저장하도록 선택할 수 있습니다.

- 줄 포커스는 컨텐츠를 읽을 때 제한된 부분에 집중하려는 사용자를 위해 설계되었습니다. 사용자는 한 번에 1, 3 또는 5줄에 초점을 유지하고 나머지 페이지는 흐리게 하여 사용자가 방해받지 않고 집중하여 읽을 수 있도록 합니다. 사용자는 터치 또는 화살표 키를 사용하여 스크롤할 수 있으며 그에 따라 초점이 이동합니다.

- Microsoft Edge는 이제 Windows 플랫폼 8.1 이상에서 Windows Speller와 통합되었습니다. 이 통합은 더 많은 언어 사전에 액세스할 수 있고 Windows 사용자 지정 사전을 사용할 수 있는 기능으로 더 많은 언어 지원을 제공합니다. OS 언어 설정에 언어가 추가되고 Microsoft Edge 설정에서 언어 맞춤법 검사 토글이 활성화된 경우 사용자에게 추가 조치가 필요하지 않습니다.

- Microsoft Edge를 사용하여 PDF 문서를 열면 사용자는 하이라이트를 만들고 색상을 변경하고 하이라이트를 삭제할 수 있습니다. 이는 나중에 문서의 중요한 부분을 참조하고 공동 작업하는 데 도움이 됩니다.

- 웹에 최적화된 긴 PDF 문서가 로딩될 때 사용자가 보고 있는 페이지는 나머지 문서가 로딩되는 동안 빠르게 병렬로 로드됩니다.

- 이제 F9 키를 누르기만 하면 웹사이트에 대한 몰입형 리더를 쉽게 시작할 수 있습니다.

- 이제 키보드 단축키(Ctrl + Shift + U)를 사용하여 소리내어 읽기를 더 쉽게 시작할 수 있습니다.

### 정책 업데이트

#### 새로운 정책

새 정책 12개를 추가했습니다. [Microsoft Edge Enterprise 랜딩 페이지](https://aka.ms/EdgeEnterprise)에서 업데이트된 관리 템플릿을 다운로드합니다. 다음과 같은 새 정책이 추가되었습니다.

- [ AmbientAuthenticationInPrivateModesEnabled ](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#ambientauthenticationinprivatemodesenabled)-InPrivate 및 게스트 프로필에 대한 주변 인증을 사용합니다. 
- [AudioSandboxEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#audiosandboxenabled) - 오디오 샌드박스를 실행할 수 있도록 합니다.
- [ForceLegacyDefaultReferrerPolicy](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#forcelegacydefaultreferrerpolicy) - 다운 그레이드할 때 참조되지 않는 기본 참조 정책을 사용합니다.
- [GloballyScopeHTTPAuthCacheEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#globallyscopehttpauthcacheenabled) - 전역적으로 범위가 지정된 HTTP 인증 캐시를 활성화합니다.
- [ImportExtensions](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#importextensions) - 확장명 가져오기를 허용합니다.
- [ImportCookies](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#importcookies) - 쿠키를 가져올 수 있습니다.
- [ImportShortcuts](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#importshortcuts) - 바로 가기 가져오기를 허용합니다.
- [InternetExplorerIntegrationSiteRedirect](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#internetexplorerintegrationsiteredirect)-Internet Explorer 모드 페이지에서 시작할 때 구성되지 않은 사이트에 대한 "페이지 내" 탐색 작동 방식을 지정하십시오.
- [OmniboxMSBProviderEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#omniboxmsbproviderenabled) - omnibox에서 비즈니스용 Business 공급자 검색 기능을 사용하도록 설정합니다. 
- [ StricterMixedContentTreatmentEnabled ](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#strictermixedcontenttreatmentenabled) -혼합 컨텐츠에 대해 보다 엄격한 처리를 사용합니다.
- [TLS13HardeningForLocalAnchorsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#tls13hardeningforlocalanchorsenabled) - 로컬 신뢰 앵커에 대한 TLS 1.3 보안 기능을 사용하세요.
- [ConfigureOnPremisesAccountAutoSignIn](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#configureonpremisesaccountautosignin) - Azure AD 도메인 계정이 없는 경우 Active Directory 도메인 계정으로 자동 로그인을 구성하십시오.

#### 더 이상 사용되지 않는 정책

이 릴리스에서는 다음 정책이 계속 작동합니다. 이 정책들은 향후 릴리스에서는 "폐기"될 것입니다.

- [WebComponentsV0Enabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webcomponentsv0enabled) - M84까지 웹 구성 요소 v0 API를 다시 사용하도록 설정합니다.
- [WebDriverOverridesIncompatiblePolicies](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webdriveroverridesincompatiblepolicies)-WebDriver가 호환되지 않는 것으로 다시 정의될 수 있습니다.

## 참고 항목

- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
