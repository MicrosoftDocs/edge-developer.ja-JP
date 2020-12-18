---
description: サポートされているマニフェスト キーとその既知の問題/Chrome の非互換性に関する情報を検索します。
title: 拡張機能 - サポートされているマニフェスト キー
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, 開発者
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: f8413193ddb834eb7e31e4101c2b027c48bc501d
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235044"
---
# サポートされるマニフェスト キー  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

すべての拡張機能には、JSON 形式のマニフェスト ファイルが含まれています。このマニフェスト ファイルはmanifest.jsされます。 このファイルは、名前からアクセス許可まで、拡張子に関する重要な情報を提供します。 次のメモで指定されていない限り、Microsoft Edge のマニフェスト プロパティは Chrome と同じ実装に従います。

Microsoft Edge JSON マニフェスト ファイルの [例を次に示します](./supported-manifest-keys/json-manifest-example.md)。

## 必要なキー

次のキーが必要です。

キー | 既知の問題 | Chrome の非互換性
:------------ | :------------- | :--------------
[author](https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/author)  | | 
[name](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/name) | | |
[version](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/version) | | |

## 推奨されるキー

次のキーをお勧めします。

キー | 既知の問題 | Chrome の非互換性
:------------ | :------------- | :--------------
browser_specific_settings | | ブラウザーでの拡張機能の優先状態を示します。 ブラウザーでは、拡張機能の評価などの要因や、ユーザーのアドレス バーに既に表示されているボタンの総数に応じて、今後のリリースでブラウザーで考慮する必要がある場合と、考慮しない場合があります。 これは、アイコンの既定の位置を示すために使用 `browserAction` できます。 </br></br> `"browser_specific_settings": {`</br>&nbsp;&nbsp;&nbsp;&nbsp;`"edge": {`</br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`"browser_action_next_to_addressbar": true`</br>&nbsp;&nbsp;&nbsp;&nbsp;`}`</br>`}` </br></br> Chrome ではサポートされていません。|
[default_locale](https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/default_locale)| | |
[description](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/description) | | |
[アイコン](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/icons) | | |
[manifest_version](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/manifest_version) | | Microsoft Edge では現在無視されています。



## browser_actionキーまたはpage_actionキー

次のキーの 1 つのみを含め (またはなし) できます。

キー | 既知の問題 | Chrome の非互換性
:------------ | :------------- | :--------------
[browser_action](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/browser_action)  | | Microsoft Edge では、次の構文はサポートされていません。  `browser_action : {"default_icon" : "icon.png" }`   <br/>アイコンのサイズを指定する必要があります。 <br/>優先サイズ: 20px、25px、30px、40px。 <br/> その他のサポートされるサイズ: 19px、35px、38px。|
[page_action](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/page_action) | | Microsoft Edge では、次の構文はサポートされていません。  `page_action : {"default_icon" : "icon.png" }`   <br/>アイコンのサイズを指定する必要があります。 <br/>優先サイズ: 20px、25px、30px、40px。 <br/>その他のサポートされるサイズ: 19px、35px、38px。|

## オプションのキー

次のキーは省略可能です。

キー | 既知の問題 | Chrome の非互換性
:------------ | :------------- | :--------------
[背景](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/background) | | 永続的は、Microsoft Edge の必須フィールドです。
[content_scripts](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/content_scripts)  | | |
[content_security_policy](https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/content_security_policy)  | ページのコンテンツ セキュリティ ポリシーは、コンテンツ スクリプト内の WebSockets をブロックし、未定義の例外を生成します。 | 現在、Microsoft Edge 拡張機能は既定の [ポリシー制限のみをサポートしています](https://developer.mozilla.org/Add-ons/WebExtensions/Content_Security_Policy#Default_content_security_policy)。 `script-src 'self'; object-src 'self'` |
[incognito](https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/incognito) | | | 
key  | | |
options_page | | |
[permissions](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/permissions)  | | |
short_name  | | |
[web_accessible_resources](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/web_accessible_resources) | | |

### サポートされているアクセス許可
次の [アクセス許可](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/permissions) がサポートされています。


| 許可         | 説明                                                                                                                                                                                                                                                                         |
|:-------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| \<all_urls\>       | バックグラウンド スクリプトとコンテンツ スクリプトで、追加の特権を持つすべての Web ページを [操作できます](https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/permissions#Host_permissions)。                                                                                  |
| contextMenus       | API へのアクセスを `contextMenus` 提供します。 これにより、Microsoft Edge のコンテキスト メニューに項目を追加できます。                                                                                                                                                                                     |
| cookie            | API へのアクセスを `cookies` 提供します。 これにより、Cookie のクエリと変更、および変更時に通知を受け取る機能が有効です。                                                                                                                                                           |
| geolocation        | ユーザーにアクセス許可を求めずに、拡張機能で HTML5 `geolocation` API を使用できます。                                                                                                                                                                                   |
| idle               | API へのアクセスを `idle` 提供します。 これにより、コンピューターのアイドル状態が変化する時間を検出できます。                                                                                                                                                                                    |
| ストレージ            | API へのアクセスを `storage` 提供します。 これにより、ユーザー データに対する変更の保存、取得、および追跡が可能です。                                                                                                                                                                             |
| tabs               | ブラウザーのタブ システム `tabs` を操作するための API へのアクセスを提供します。 これにより、ブラウザーのタブ (各タブに関連付けられた URL を含む) を作成、変更、および並び替えできます。                                                                                       |
| unlimitedStorage   | [storage.local で、5](https://developer.mozilla.org/Add-ons/WebExtensions/API/storage/local) MB ではなく無制限の記憶域を持つ (システム リソースに応じて) 許可します。 キー値ペアあたりの最大記憶域も 5 MB から無制限に増加します (システム リソースによって異なる)。 |
| webNavigation      | API へのアクセスを `webNavigation` 提供します。 これにより、ナビゲーション要求の状態に関する通知を受信できます。                                                                                                                                                              |
| webRequest         | API へのアクセスを `webRequest` 提供します。 これにより、トラフィックの監視と分析、およびインフライトでの要求の傍受、ブロック、または変更が可能です。                                                                                                                               |
| webRequestBlocking | 拡張機能が API をブロックする `webRequest` 方法で使用する場合は必須です。                                                                                                                                                                                                           |

'""'
