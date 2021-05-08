---
description: マニフェストで API のアクセス許可を宣言する方法について説明します。
title: 拡張マニフェストで API アクセス許可を宣言する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/17/2021
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: edge-chromium, 拡張機能の開発, ブラウザー拡張機能, アドオン, パートナー センター, 開発者
ms.openlocfilehash: 987279a8072388d3fd47ee8b7cbf5f9bb3c483e0
ms.sourcegitcommit: bff24ab1f0a66aaf4c7f5ff81cea3eb28c6d8380
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "11461547"
---
<!-- Copyright A. W. Fuchs

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  
# <a name="declare-api-permissions-in-extension-manifests"></a>拡張マニフェストで API アクセス許可を宣言する  

ほとんどの API を使用するには `chrome.*` 、拡張機能でマニフェストで宣言 `permissions` する必要があります。  次の表からアクセス許可文字列を使用してアクセス許可を宣言するか、同様の文字列に一致するパターンを使用できます。  アクセス許可は、拡張機能がマルウェアによって侵害された場合に、拡張機能を制限するのに役立ちます。  権限の警告を使用して拡張機能をインストールする前に、一部のアクセス許可がユーザーに表示される場合があります。  

API でマニフェストでアクセス許可を宣言する必要がある場合は、その API のドキュメントを参照して、必要なアクセス許可を理解してください。  たとえば、[API] ページStorage、アクセス許可を宣言する方法について説明 `storage` します。  

次のコード スニペットでは、マニフェスト ファイルでアクセス許可を宣言する方法について説明します。  

```json
"permissions": [
  "tabs",
  "bookmarks",
  "http://www.blogger.com/",
  "http://*.google.com/",
  "unlimitedStorage"
]
```  

次の表に、マニフェストで使用する現在使用可能なアクセス許可文字列と説明を示します。  

| アクセス許可文字列 | 詳細 |  
|:--- |:--- |  
| `activeTab` | 仕様に従って拡張機能にアクセス許可が付与される要求 `activeTab` 。 |  
| `alarms` | 拡張機能に API へのアクセス権を与 `chrome.alarms` えます。 |  
| `background` | 拡張機能Microsoft Edge長い寿命を持つ可能性がある場合に、早期に起動し、遅くシャットダウンするようにします。  インストールされている拡張機能にアクセス許可がある場合、Microsoft Edge は、ユーザーがユーザーのコンピューターにログインするとすぐに、ユーザーがコンピューターを起動する前に、目に見え `background` Microsoft Edge。  また、ユーザーがMicrosoft Edge終了するまで、最後のウィンドウが閉じても、このアクセス許可によって実行 `background` Microsoft Edge。  このアクセス許可は、ブラウザーで無効になっている拡張機能には影響を与えることはできません。  アクセス `background` 許可は、通常、バックグラウンド ページで使用されます。 |  
| `bookmarks` | 拡張機能に API へのアクセス権を与 `chrome.bookmarks` えます。 |  
| `browsingData` | 拡張機能に API へのアクセス権を与 `chrome.browsingData` えます。 |  
| `certificateProvider` | 拡張機能に API へのアクセス権を与 `chrome.certificateProvider` えます。 |  
| `clipboardRead` | 拡張機能で使用する場合は必須 `document.execCommand('paste')` です。 |  
| `clipboardWrite` | 拡張機能の使用またはを `document.execCommand('copy')` 示します `document.execCommand('cut')` 。 |  
| `contentSettings` | 拡張機能に API へのアクセス権を与 `chrome.contentSettings` えます。 |  
| `contextMenus` | 拡張機能に API へのアクセス権を与 `chrome.contextMenus` えます。 |  
| `cookies` | 拡張機能に API へのアクセス権を与 `chrome.cookies` えます。 |  
| `debugger` | 拡張機能に API へのアクセス権を与 `chrome.debugger` えます。 |  
| `declarativeContent` | 拡張機能に API へのアクセス権を与 `chrome.declarativeContent` えます。 |  
| `declarativeNetRequest` | 拡張機能に API へのアクセス権を与 `chrome.declarativeNetRequest` えます。 |  
| `declarativeNetRequestFeedback` | API 内のイベントとメソッドへの拡張機能アクセスを許可し、一致する宣言型ルールに関する `chrome.declarativeNetRequest` 情報を返します。 |  
| `declarativeWebRequest` | 拡張機能に API へのアクセス権を与 `chrome.declarativeWebRequest` えます。 |  
| `desktopCapture` | 拡張機能に API へのアクセス権を与 `chrome.desktopCapture` えます。 |  
| `documentScan` | 拡張機能に API へのアクセス権を与 `chrome.documentScan` えます。 |  
| `downloads` | 拡張機能に API へのアクセス権を与 `chrome.downloads` えます。 |  
| `enterprise.deviceAttributes` | 拡張機能に API へのアクセス権を与 `chrome.enterprise.deviceAttributes` えます。 |  
| `enterprise.hardwarePlatform` | 拡張機能に API へのアクセス権を与 `chrome.enterprise.hardwarePlatform` えます。 |  
| `enterprise.networkingAttributes` | 拡張機能に API へのアクセス権を与 `chrome.enterprise.networkingAttributes` えます。 |  
| `enterprise.platformKeys` | 拡張機能に API へのアクセス権を与 `chrome.enterprise.platformKeys` えます。 |  
| `experimental` | 拡張機能が API を使用する場合は必須 `chrome.experimental.*` です。 |  
| `fileBrowserHandler` | 拡張機能に API へのアクセス権を与 `chrome.fileBrowserHandler` えます。 |  
| `fileSystemProvider` | 拡張機能に API へのアクセス権を与 `chrome.fileSystemProvider` えます。 |  
| `fontSettings` | 拡張機能に API へのアクセス権を与 `chrome.fontSettings` えます。 |  
| `geolocation` | ユーザーにアクセス許可を求めることなく、拡張機能で位置情報 API を使用できます。 |  
| `history` | 拡張機能に API へのアクセス権を与 `chrome.history` えます。 |  
| `identity` | 拡張機能に API へのアクセス権を与 `chrome.identity` えます。 |  
| `idle` | 拡張機能に API へのアクセス権を与 `chrome.idle` えます。 |  
| `loginState` | 拡張機能に API へのアクセス権を与 `chrome.loginState` えます。 |  
| `management` | 拡張機能に API へのアクセス権を与 `chrome.management` えます。 |  
| `nativeMessaging` | ネイティブ メッセージング API への拡張機能アクセス権を提供します。 |  
| `notifications` | 拡張機能に API へのアクセス権を与 `chrome.notifications` えます。 |  
| `pageCapture` | 拡張機能に API へのアクセス権を与 `chrome.pageCapture` えます。 |  
| `platformKeys` | 拡張機能に API へのアクセス権を与 `chrome.platformKeys` えます。 |  
| `power` | 拡張機能に API へのアクセス権を与 `chrome.power` えます。 |  
| `printerProvider` | 拡張機能に API へのアクセス権を与 `chrome.printerProvider` えます。 |  
| `printing` | 拡張機能に API へのアクセス権を与 `chrome.printing` えます。 |  
| `printingMetrics` | 拡張機能に API へのアクセス権を与 `chrome.printingMetrics` えます。 |  
| `privacy` | 拡張機能に API へのアクセス権を与 `chrome.privacy` えます。 |  
| `processes` | 拡張機能に API へのアクセス権を与 `chrome.processes` えます。 |  
| `proxy` | 拡張機能に API へのアクセス権を与 `chrome.proxy` えます。 |  
| `scripting` | 拡張機能に API へのアクセス権を与 `chrome.scripting` えます。 |  
| `search` | 拡張機能に API へのアクセス権を与 `chrome.search` えます。 |  
| `sessions` | 拡張機能に API へのアクセス権を与 `chrome.sessions` えます。 |  
| `signedInDevices` | 拡張機能に API へのアクセス権を与 `chrome.signedInDevices` えます。 |  
| `storage` | 拡張機能に API へのアクセス権を与 `chrome.storage` えます。 |  
| `system.cpu` | 拡張機能に API へのアクセス権を与 `chrome.system.cpu` えます。 |  
| `system.display` | 拡張機能に API へのアクセス権を与 `chrome.system.display` えます。 |  
| `system.memory` | 拡張機能に API へのアクセス権を与 `chrome.system.memory` えます。 |  
| `system.storage` | 拡張機能に API へのアクセス権を与 `chrome.system.storage` えます。 |  
| `tabCapture` | 拡張機能に API へのアクセス権を与 `chrome.tabCapture` えます。 |  
| `tabGroups` | 拡張機能に API へのアクセス権を与 `chrome.tabGroups` えます。 |  
| `tabs` | 複数の API で使用される可能性があるオブジェクトの特権フィールドへの拡張機能アクセス権を `Tab` `chrome.tabs` 提供します `chrome.windows` 。  多くの場合、拡張機能は、これらの API を使用するためのアクセス許可を宣言 `tabs` する必要があります。 |  
| `topSites` | 拡張機能に API へのアクセス権を与 `chrome.topSites` えます。 |  
| `tts` | 拡張機能に API へのアクセス権を与 `chrome.tts` えます。 |  
| `ttsEngine` | 拡張機能に API へのアクセス権を与 `chrome.ttsEngine` えます。 |  
| `unlimitedStorage` | データベースやローカル ストレージ ファイルなどのクライアント側データを格納するための制限なしクォータを提供します。  このアクセス許可がない場合、拡張機能は 5 MB のローカル ストレージに制限されます。 |  
| `vpnProvider` | 拡張機能に API へのアクセス権を与 `chrome.vpnProvider` えます。 |  
| `wallpaper` | 拡張機能に API へのアクセス権を与 `chrome.wallpaper` えます。 |  
| `webNavigation` | 拡張機能に API へのアクセス権を与 `chrome.webNavigation` えます。 |  
| `webRequest` | 拡張機能に API へのアクセス権を与 `chrome.webRequest` えます。 |  
| `webRequestBlocking` | 拡張機能が API を使用して `chrome.webRequest` 要求をブロックする場合は必須です。 |  

<!-- links -->  

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> 元のページは次 [のページに表示されます](https://developer.chrome.com/docs/extensions/mv3/declare_permissions/)。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
