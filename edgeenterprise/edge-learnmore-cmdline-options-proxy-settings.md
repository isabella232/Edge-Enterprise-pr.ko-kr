---
title: Microsoft Edge 프록시 설정
ms.author: brianalt
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: '명령줄 옵션을 사용하여 프록시 설정 구성 '
ms.openlocfilehash: 5a7a422813b751d2ed120bc5a287564600dba8e1
ms.sourcegitcommit: 592f6e40b13e28af588473b2a75c3ae697e5db2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2022
ms.locfileid: "12505491"
---
# <a name="how-to-use-microsoft-edge-command-line-options-to-configure-proxy-settings"></a>Microsoft Edge 명령줄 옵션을 사용하여 프록시 설정을 구성하는 방법

이 문서에서는 명령줄 옵션을 사용하여 기본 시스템 네트워크 설정을 재정의하는 방법을 설명합니다.

>[!NOTE]
>이 문서는 Microsoft Edge 버전 77 이상에 적용됩니다.

## <a name="system-network-settings"></a>시스템 네트워크 설정

Microsoft Edge 네트워크 스택은 기본적으로 시스템 네트워크 설정을 사용합니다. 이러한 설정에는 * 프록시 설정*과 *인증서 및 개인 키 저장소*가 포함됩니다.

사용자가 시스템 기본 프록시 설정을 사용하는 대신 다른 방법을 요청하는 시나리오가 있습니다. 이러한 시나리오를 지원하기 위해 Microsoft Edge에서는 사용자 지정 프록시 설정을 구성하는 데 사용할 수 있는 명령줄 옵션을 지원합니다.

이러한 명령줄 옵션은 **프록시 서버** 그룹의 다음 정책에 해당합니다.

- [ProxyBypassList](./microsoft-edge-policies.md#proxybypasslist)
- [ProxyMode](./microsoft-edge-policies.md#proxymode)
- [ProxyPacUrl](./microsoft-edge-policies.md#proxypacurl)
- [ProxyServer](./microsoft-edge-policies.md#proxyserver)
- [ProxySettings](./microsoft-edge-policies.md#proxysettings)

## <a name="command-line-options-for-proxy-settings"></a>프록시 설정 관련 명령줄 옵션

Microsoft Edge는 다음과 같은 프록시 관련 명령줄 옵션을 지원합니다.

 **`--no-proxy-server`**
 
시스템이 프록시를 사용하도록 구성되어 있더라도 Microsoft Edge에 프록시를 사용하지 않도록 지시합니다. 이는 제공된 다른 모든 프록시 설정을 재정의합니다.

**`--proxy-auto-detect`**

Mircrosoft Edge에 프록시 구성을 자동으로 감지하도록 지시합니다. `--proxy-server`가 구성된 경우 이 인수는 무시됩니다.

**`--proxy-server=<scheme>=<uri>[:<port>][;...] | <uri>[:<port>] | "direct://"`**

Microsoft Edge에 사용자 지정 프록시 구성을 사용하도록 지시합니다. 사용자 지정 프록시 구성은 세 가지 방법으로 지정할 수 있습니다.

1. url/포트 쌍에 세미콜론으로 구분된 목록 구성표 매핑을 제공합니다. 예를 들어 `--proxy-server="http=proxy1:8080;ftp=ftpproxy"`는 http URL에 HTTP 프록시 "proxy1:8080"을 사용하고 ftp URL에 HTTP 프록시 "ftpproxy:80"을 사용하도록 Microsoft Edge에 지시합니다.
2. 모든 URL에 사용할 선택적 포트가 있는 단일 uri를 제공합니다. 예를 들어 `--proxy-server="proxy2:8080"`은 모든 트래픽에 "proxy2:8080" 프록시를 사용합니다.
3. 특수 "direct://" 값을 사용합니다. 예를 들어 `--proxy-server="direct://"`는 모든 연결이 프록시를 사용하지 않도록 합니다. 

>[!NOTE]
>프록시를 사용할 수 없는 경우 프록시 및 대체를 사용하여 직접 이동하도록 Microsoft Edge를 구성할 수 있습니다. 예를 들면 `--proxy-server="http://proxy2:8080,direct://`입니다.

**`--proxy-bypass-list=(<trailing_domain>|<ip-address>)[:<port>][;...]`**

Microsoft Edge에 지정한 세미콜론으로 구분된 호스트 목록에 대해 지정하 프록시를 무시하도록 지시합니다. 이 플래그는 `--proxy-server`와 함께 사용해야 합니다.

>[!NOTE]
>후행 도메인 일치에는 "." 구분 기호가 필요하지 않습니다. "\*microsoft.com"은 "imicrosoft.com"과 일치합니다. 예를 들어 `--proxy-server="proxy2:8080" --proxy-bypass-list="*.microsoft.com;*example.com;127.0.0.1:8080"`는 포트 8080에서 \*.microsoft.com, example.com 및 127.0.0.1에 대한 요청을 제외하고 모든 호스트의 포트 8080에 프록시 서버 "proxy2"를 사용합니다. 이전 예제에서 imicrosoft.com 요청은 계속 프록시됩니다. 그러나 \*.example.com 대신 \*example.com이 지정되었기 때문에 iexample.com 요청은 프록시를 우회합니다.

**`--proxy-pac-url=<pac-file-url>`**

Microsoft Edge에 지정한 URL에서 PAC 파일을 사용하도록 지시합니다. 예를 들어 `--proxy-pac-url="https://wpad/proxy.pac"`은 **proxy.pac** 파일을 사용하여 URL 요청에 대한 프록시 정보를 확인하도록 Microsoft Edge에 지시합니다.

## <a name="content-license"></a>콘텐츠 라이선스

> [!NOTE]
> 이 페이지의 일부는 Chromium.org에서 생성 및 공유하고 [Creative Commons Attribution 4.0 국제 라이선스](http://creativecommons.org/licenses/by/4.0/)에 규정된 조건에 따라 사용되는 작업을 기반으로 합니다. 원래 페이지는 [여기](https://www.chromium.org/developers/design-documents/network-settings#TOC-Command-line-options-for-proxy-sett)에서 찾을 수 있습니다.
  
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />이 작업은 <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 국제 라이선스</a>에서 사용이 허가되었습니다.

## <a name="see-also"></a>참고 항목

- 고급 구성 설정 및 추가 옵션을 보려면 Chromium 오픈 소스 프로젝트에서 [프록시 설명서](https://chromium.googlesource.com/chromium/src/+/HEAD/net/docs/proxy.md)를 참조하세요.
- [Microsoft Edge 엔터프라이즈 방문 페이지](https://aka.ms/EdgeEnterprise)