---
description: サポートされているマニフェストキー、および既知の問題と Chrome の互換性がないことに関する情報を検索します。
title: 拡張機能-サポートされているマニフェストキー
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者
ms.openlocfilehash: deeff12251d25efaed1b40c98594c616a0d9c99a
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569531"
---
# サポートされているマニフェストキー  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

すべての拡張機能には、manifest という名前の JSON 形式のマニフェストファイルがあります。 このファイルは、拡張子の名前からアクセス許可までの重要な情報を提供します。 以下のメモで指定されていない限り、Microsoft Edge のマニフェストプロパティは Chrome と同じ実装に従います。

[Microsoft Edge の JSON マニフェストファイル](./supported-manifest-keys/json-manifest-example.md)の例を次に示します。

## 必要なキー

次のキーが必要です。

Key | 既知の問題 | Chrome の非互換性
:------------ | :------------- | :--------------
[著作者](https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/author)  | | 
[name](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/name) | | |
[version](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/version) | | |

## 推奨されるキー

以下のキーをお勧めします。

Key | 既知の問題 | Chrome の非互換性
:------------ | :------------- | :--------------
browser_specific_settings | | ブラウザーで拡張機能の優先状態を示します。 今後のリリースでは、拡張機能の評判、またはユーザーのアドレスバーに既にあるボタンの合計数などの要因に応じて、ブラウザーはそれを考慮することができない場合があります。 これは、アイコンの既定の位置を示すために使うことができ `browserAction` ます。 </br></br> `"browser_specific_settings": {`</br>&nbsp;&nbsp;&nbsp;&nbsp;`"edge": {`</br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`"browser_action_next_to_addressbar": true`</br>&nbsp;&nbsp;&nbsp;&nbsp;`}`</br>`}` </br></br> Chrome ではサポートされていません。|
[default_locale](https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/default_locale)| | |
[description](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/description) | | |
[アイコン](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/icons) | | |
[manifest_version](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/manifest_version) | | Microsoft Edge では現在無視されています。



## browser_action または page_action キー

次のいずれかのキーのみを含めることができます (またはなし)。

Key | 既知の問題 | Chrome の非互換性
:------------ | :------------- | :--------------
[browser_action](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/browser_action)  | | Microsoft Edge では、次の構文はサポートされていません。  `browser_action : {"default_icon" : "icon.png" }`   <br/>アイコンのサイズを指定する必要があります。 <br/>優先サイズ: 20px、25px、30px、40px。 <br/> サポートされているその他のサイズ: 19px、35px、38px。|
[page_action](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/page_action) | | Microsoft Edge では、次の構文はサポートされていません。  `page_action : {"default_icon" : "icon.png" }`   <br/>アイコンのサイズを指定する必要があります。 <br/>優先サイズ: 20px、25px、30px、40px。 <br/>サポートされているその他のサイズ: 19px、35px、38px。|

## オプションのキー

次のキーは省略可能です。

Key | 既知の問題 | Chrome の非互換性
:------------ | :------------- | :--------------
[背景](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/background) | | Persistent は、Microsoft Edge の必須フィールドです。
[content_scripts](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/content_scripts)  | | |
[content_security_policy](https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/content_security_policy)  | ページのコンテンツセキュリティポリシーは、websocket をコンテンツスクリプトでブロックし、未定義の例外を生成します。 | Microsoft Edge extensions は現在、[既定のポリシー制限](https://developer.mozilla.org/Add-ons/WebExtensions/Content_Security_Policy#Default_content_security_policy)のみをサポートしています。 `script-src 'self'; object-src 'self'` |
[シークレットウィンドウ](https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/incognito) | | | 
key  | | |
options_page | | |
[権限](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/permissions)  | | |
short_name  | | |
[web_accessible_resources](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/web_accessible_resources) | | |

### サポートされているアクセス許可
次の[権限](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/permissions)がサポートされています。


| 許可         | 説明                                                                                                                                                                                                                                                                         |
|:-------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| \ <all_urls \ >       | バックグラウンドとコンテンツのスクリプトが、追加の[権限](https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/permissions#Host_permissions)を持つすべての web ページとやり取りできるようにします。                                                                                  |
| contextMenus       | API へのアクセスを提供 `contextMenus` します。 これにより、Microsoft Edge のコンテキストメニューへの項目の追加が可能になります。                                                                                                                                                                                     |
| cookie            | API へのアクセスを提供 `cookies` します。 これにより、cookie のクエリと変更を有効にし、変更時に通知を受け取ることができます。                                                                                                                                                           |
| 位置        | `geolocation`ユーザーに許可を求めることなく、拡張機能で HTML5 API を使用できるようにします。                                                                                                                                                                                   |
| アイドル               | API へのアクセスを提供 `idle` します。 これにより、コンピューターのアイドル状態が変更されたときを検出できます。                                                                                                                                                                                    |
| ストレージ            | API へのアクセスを提供 `storage` します。 これにより、ユーザーデータの保存、取得、および変更の追跡が可能になります。                                                                                                                                                                             |
| タブ               | `tabs`ブラウザーのタブシステムを操作するための API へのアクセスを提供します。 これにより、各タブに関連付けられた Url など、ブラウザーでタブの作成、変更、再配置を行うことができます。                                                                                       |
| unlimitedStorage   | (システムリソースによっては) 5MB ではなく、実質無制限のストレージを使用でき[ます。](https://developer.mozilla.org/Add-ons/WebExtensions/API/storage/local) [キーと値のペアごとの最大記憶域] は、システムリソースに応じて、5MB から実質無制限に増加します。 |
| Web ナビゲーション      | API へのアクセスを提供 `webNavigation` します。 これにより、ナビゲーション要求の状態に関する通知を受け取ることができます。                                                                                                                                                              |
| webRequest         | API へのアクセスを提供 `webRequest` します。 これにより、トラフィックの監視と分析、送信中の要求の受信、ブロック、または変更を行うことができます。                                                                                                                               |
| webRequestBlocking | 拡張 `webRequest` でブロック中に API を使う場合は必須です。                                                                                                                                                                                                           |

'""'
