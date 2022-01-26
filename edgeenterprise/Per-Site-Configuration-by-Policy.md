---
title: 정책에 따라 사이트당 구성
ms.author: collw
author: dan-wesley
manager: laurawi
ms.date: 01/04/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 정책에 따라 사이트당 구성
ms.openlocfilehash: 147f14fdd09f56161bf03ca88b5e6107ba9c88c5
ms.sourcegitcommit: e7f3098d8b7d91cae20b5778a71a87daababc312
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "12297870"
---
# <a name="per-site-configuration-by-policy"></a>정책에 따라 사이트당 구성

이 문서에서는 정책에 따라 사이트당 구성을 설명하고 브라우저가 사이트에서 페이지 로드를 처리하는 방법에 대해 설명합니다.

## <a name="the-browser-as-a-decision-maker"></a>의사 결정자인 브라우저

모든 페이지 로드의 일부로 브라우저는 많은 결정을 내립니다. 이러한 결정에는 특정 API를 사용할 수 있는지, 리소스 부하를 허용할지, 스크립트를 실행할 수 있는지 여부가 포함됩니다.

대부분의 경우 브라우저 결정은 다음과 같은 입력으로 제어됩니다.

- 사용자 설정
- 결정을 내릴 페이지의 URL입니다.

웹 Internet Explorer 각 결정을 URLAction이라고 합니다. 자세한 내용은 [URL 작업 플래그를 참조하세요.](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537178%28v%3dvs.85%29) URLAction, Enterprise 정책 및 인터넷 제어판의 사용자 설정은 브라우저가 각 결정을 처리하는 방법을 제어했습니다.  

이 Microsoft Edge 대부분의 사이트당 사용 권한은 와일드카드 지원이 제한된 간단한 구문을 사용하여 표현된 설정 및 정책에 의해 제어됩니다. Windows 보안 영역은 여전히 몇 가지 구성 결정에 사용됩니다.

## <a name="windows-security-zones"></a>Windows 보안 영역

사용자 또는 관리자에 대한 구성을 간소화하기 위해 레거시 플랫폼은 사이트를 5개의 보안 영역 중 하나에 분류했습니다. 이러한 보안 영역은 로컬 컴퓨터, 로컬 인트라넷, 신뢰할 수 있는, 인터넷 및 제한된 사이트입니다.

페이지 로드 결정을 내릴 때 브라우저는 웹 사이트를 영역으로 매핑한 다음 해당 영역의 URLAction 설정을 참조하여 어떤 작업을 할지 결정합니다. "내 인트라넷의 인증 과제를 자동으로 충족"처럼 적절한 기본값은 대부분의 사용자가 기본 설정을 변경할 필요가 없습니다.

사용자는 인터넷 제어판 사용하여 특정 사이트를 영역에 할당하고 각 영역에 대한 사용 권한 결과를 구성할 수 있습니다. 관리되는 환경에서 관리자는 그룹 정책 사용하여 특정 사이트를 영역에 할당하고("사이트 간 할당 목록" 정책을 통해) 영역별로 URLActions에 대한 설정을 지정할 수 있습니다. 사이트에 대한 수동 관리 또는 사용자 할당 이외에도 다른추론은 사이트를 로컬 인트라넷 영역 에 [할당할 수 있습니다.](/archive/blogs/ieinternals/the-intranet-zone) 특히 점 없는 호스트 이름(예: `http://payroll` )이 인트라넷 영역으로 할당됩니다. 프록시 구성 스크립트를 사용하는 경우 프록시를 무시하도록 구성된 모든 사이트는 인트라넷 영역에 매핑됩니다.

Microsoft Edge 레거시는 몇 가지 간소화된 변경 내용으로 Internet Explorer 선행 작업에서 영역 아키텍처를 상속했습니다.

- Windows의 5가지 기본 제공 영역은 인터넷(인터넷), 신뢰할 수 있는 영역(인트라넷+신뢰할 수 있음) 및 로컬 컴퓨터의 3개 영역으로 축소되었습니다. 제한된 사이트 영역이 제거되었습니다.
- URLAction 매핑에 대한 영역 간 매핑이 브라우저에 하드 코딩되어 인터넷 제어판 그룹 정책 및 설정을 무시했습니다.

## <a name="per-site-permissions-in-microsoft-edge"></a>사이트의 사이트 Microsoft Edge

Microsoft Edge 영역은 제한적으로 Windows 보안 있습니다. 대신  [정책](/deployedge/microsoft-edge-policies)을 통해 관리자에게 사이트별 구성을 제공하는 대부분의 사용 권한 및 기능은  [URL 필터 형식](/DeployEdge/edge-learnmmore-url-list-filter%20format) 규칙 목록에 의존합니다.

최종 사용자가 처럼 설정 페이지를 열면 다양한 사용 권한에 대한 긴 구성 스위치 및 `edge://settings/content/siteDetails?site=https://example.com` 목록 목록이 표시됩니다. 사용자는 페이지 설정 드롭다운에서 다양한 위젯 및 토글을 검색하고 사용하는 동안 선택을 하는 **** 대신 페이지 페이지를 직접 사용하는   경우가 거의 없습니다. 이 목록은 주소 표시줄에서 잠금 아이콘을 선택하면 표시됩니다. 주소 표시줄의 오른쪽 가장자리에 있는 다양한 프롬프트나 단추를 사용할 수도 있습니다. 다음 스크린샷에는 페이지 정보의 예가 나와 있습니다.

:::image type="content" source="media/per-site-configuration-by-policy/edge-page-info.png" alt-text="브라우저의 현재 페이지에 대한 페이지 정보 및 설정입니다.":::

기업에서는 그룹 정책을 사용하여 브라우저의 동작을 제어하는 개별 정책에 대한 사이트 목록을 설정할 수 있습니다. 이러한 정책을 찾으 Microsoft Edge [](/deployedge/microsoft-edge-policies)그룹 정책 설명서를 열고 "ForUrls"를 검색하여 로드된 사이트의 URL에 따라 동작을 허용하고 차단하는 정책을   찾으세요. 대부분의 관련 설정은 콘텐츠 그룹 정책 섹션에 [설정](/deployedge/microsoft-edge-policies#content-settings) 나열됩니다.

또한 이름에 "Default"가 포함되어 지정한 설정의 기본 동작을 제어하는 많은 정책이 있습니다.

대부분의 설정은 가명(WebSerial, WebMIDI)으로, 기본값에서 설정을 변경할 이유가 없는 경우가 자주 있습니다.

## <a name="security-zones-inmicrosoft-edge"></a>보안 영역의 Microsoft Edge

이 Microsoft Edge 주로 URL 필터 형식을 사용하는 개별 정책에 의존하는 반면, 일부 경우에는 기본적으로 Windows 보안 영역이 계속 사용됩니다. 이 방법은 지금까지 영역 구성에 의존해오는 엔터프라이즈의 배포를 간소화합니다.

다음 동작은 영역 정책에 의해 제어됩니다.

- Kerberos 또는 NTLM(Windows 통합 인증) 자격 증명을 자동으로 해제할지 여부를 결정
- 파일 다운로드 처리 방법 결정
- Internet Explorer 모드의 경우

## <a name="credential-release"></a>자격 증명 릴리스

기본적으로 Microsoft Edge 통합 인증을 자동으로 Windows 또는 사용자에게 수동 인증 프롬프트가 표시될지 여부를  `URLACTION_CREDENTIALS_USE`  평가합니다. [AuthServerAllowlist](/deployedge/microsoft-edge-policies#authserverallowlist) 사이트 목록 정책을 구성하면 영역 정책에 대한 컨설팅이 차단됩니다.

## <a name="file-downloads"></a>파일 다운로드

파일 다운로드의 출처에 대한 증거("웹의[표시"라고도](https://textslashplain.com/2016/04/04/downloads-and-the-mark-of-the-web/)알려지며 인터넷 영역에서 다운로드한 파일에 대해 기록됩니다. Windows 셸, Microsoft Office 등의 다른 응용 프로그램은 파일 처리 방법을 결정 할 때 이 원본 증거를 고려할 수 있습니다.

Windows 보안 영역 정책이 응용 프로그램 시작 및 안전하지 않은 파일 다운로드 설정을 사용하지 않도록 구성된 경우 Microsoft Edge 다운로드 관리자가 해당 영역의 사이트에서 파일 다운로드를 차단합니다. 사용자에게 "다운로드할 수 없습니다 . 차단된" 메모가 표시될 것입니다.  

## <a name="ie-mode"></a>IE 모드

 [IE 모드에서 모든 인트라넷 사이트를 열도록](/deployedge/edge-ie-mode#configure-all-intranet-sites) IE 모드를 구성할 수 있습니다. 이 구성을 사용할 Microsoft Edge IE 모드에서 열지 여부를 결정하면 URL의 영역이 평가됩니다. 이러한 초기 결정 이외에 IE 모드 탭은 실제로 Internet Explorer 실행되고 있으며, 그 결과로 IE 모드 탭은 모든 정책 결정에 대한 영역 설정을 Internet Explorer 평가합니다.

## <a name="summary"></a>요약

대부분의 경우 Microsoft Edge 설정은 기본값으로 둘 수 있습니다. 모든 사이트 또는 특정 사이트의 기본값을 변경하려는 관리자는 적절한 그룹 정책을 사용하여 사이트 목록 또는 기본 동작을 지정할 수 있습니다. 자격 증명 릴리스, 파일 다운로드 및 IE 모드와 같은 일부 경우에는 관리자가 영역 설정을 구성하여 동작을 Windows 보안 있습니다.

## <a name="frequently-asked-questions"></a>질문과 대답

### <a name="can-the-url-filter-format-match-on-a-sites-ip-address"></a>URL 필터 형식이 사이트의 IP 주소와 일치할 수 있나요?

아니요. 형식은 허용 목록 및 차단 목록에 대한 IP 범위 지정을 지원하지 않습니다. 개별 **IP**리터럴 사양을 지원하지만 이러한 규칙은 사용자가 말한 리터럴(예: )을 사용하여 사이트로 이동하는 경우만 `http://127.0.0.1/` 준수됩니다. 호스트 이름(`http://localhost`)을 사용하는 경우 호스트의 확인된 IP가 필터 나열 IP와 일치하더라도 IP 리터럴 규칙이 적용되지 않습니다.

### <a name="can-url-filters-matchdotless-host-names"></a>URL 필터가 점 없는 호스트 이름과 일치할 수 있나요?

아니요. 각 호스트 이름(예: `https://payroll` , `https://stock` `https://who` 등)을 나열해야 합니다.

호스트 이름이 다음 형식이 될 수 있도록 인트라넷을 구성할 수 있을 만큼 충분히 앞당기고 있는 경우 모범 사례를 구현한 것입니다.

- `https://payroll.contoso-intranet.com`

- `https://timecard.contoso-intranet.com`

- `https://sharepoint.contoso-intranet.com`

이전 시나리오에서는 ***.contoso-intranet.com**각 정책을 구성할 수 있으며 전체 인트라넷이   옵트인됩니다.

## <a name="see-also"></a>기타 참조

- [Microsoft Edge 설명서](./index.yml)
- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)
