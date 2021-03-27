---
description: エッジ (クロム) 拡張機能のエンタープライズ ポリシードキュメント。
title: 一致パターン
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/17/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium, 拡張機能の開発, ブラウザー拡張機能, アドオン, パートナー センター, 開発者
ms.openlocfilehash: fcb87b62cac063c7663f575fa3d992b187408c28
ms.sourcegitcommit: bff24ab1f0a66aaf4c7f5ff81cea3eb28c6d8380
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "11461249"
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
# <a name="match-patterns"></a>一致パターン

ホストのアクセス許可とコンテンツ スクリプトの一致は、一致パターンで定義された一連の URL に基づいて行います。  一致パターンは、基本的には許可されたスキーム ( 、 で始まる URL であり、 ' ' 文字 `http` `https` `file` `ftp` を `*` 含めることができます。  特別なパターンは `<all_urls>` 、許可されたスキームで始まる任意の URL と一致します。  各一致パターンには、次の 3 つの部分があります。  

*   _スキーム_— たとえば、または `http` `file` `*`  

> [!NOTE]
> URL への `file` アクセスは自動ではありません。  ユーザーは、[拡張機能の管理] ページにアクセスし、要求する拡張機能ごとに `file` アクセスをオプトインする必要があります。  

*   `_host_` — たとえば、 `www.google.com` または `*.google.com` `*` 、 ; スキームがファイルの場合、ホスト パーツはありません。  
*   `_path_` — 、、 `/*` `/foo*` `/foo/bar` などです。  パスはホストアクセス許可に存在する必要がありますが、常にとして扱います `/*` 。  

基本的な構文:  

```shell
<url-pattern> := <scheme>://<host><path>
<scheme> := '*' | 'http' | 'https' | 'file' | 'ftp'
<host> := '*' | '*.' <any char except '/' and '*'>+
<path> := '/' <any chars>
```  

意味は、スキーム、ホスト、またはパス パーツの中にあるかどうか `*` によって異なります。  スキームがである場合 `*` 、スキームは 、または 、 または 、 `http` `https` のいずれかと一致します `file` `ftp` 。  ホストが単なる場合 `*` は、任意のホストと一致します。 ホストが指定されている `*.hostname` 場合は、指定したホストまたはサブドメインと一致します。  [パス] セクションでは、それぞれ `*` 0 文字以上に一致します。  次の表に、有効なパターンを示します。  

| パターン | 機能 | 一致する URL の例 |  
|:--- |:--- |:--- |  
| `http://*/*` | http スキームを使用する URL と一致する | `http://www.google.com` `http://example.org/foo/bar.html` |  
| `http://*/foo*` | パスがで始まる限り、任意のホストで http スキームを使用する URL と一致します。 `/foo` | `http://example.com/foo/bar.html` `http://www.google.com/foo` |  
| `https://*.google.com/foo*bar` | パスがで始まりで終わる限り、https スキームを使用する任意の URL がホスト `google.com` \(、\など) にある場合に `www.google.com` `docs.google.com` `google.com` `/foo` 一致します。 `bar` | `https://www.google.com/foo/baz/bar` `https://docs.google.com/foobar` |  
| `http://example.org/foo/bar.html` | 指定した URL と一致する | `http://example.org/foo/bar.html` |  
|`file:///foo*` | パスがで始まるローカル ファイルと一致する `/foo` | `file:///foo/bar.html` `file:///foo` |  
| `http://127.0.0.1/*` | スキームを使用し、ホスト上にある `http` URL と一致する `127.0.0.1` | `http://127.0.0.1` `http://127.0.0.1/foo/bar.html` |  
| `*://mail.google.com/*` | で始まる URL または で始まる URL に `http://mail.google.com` 一致 `https://mail.google.com` します。 | `http://mail.google.com/foo/baz/bar` `https://mail.google.com/foobar` |  
| `<all_urls>` | 許可されたスキームを使用する URL に一致します。 \(許可されるスキームの一覧については、このセクションの先頭を参照してください。\) | `http://example.org/foo/bar.html` `file:///bar/baz.html` |  

パターンの一致の例を `_invalid_` 次に示します。

| パターンが悪い | それが悪い理由 |  
|:--- |:--- |  
| `http://www.foo.com` | × `_path_` |  
| `http://*foo/bar` | ホスト `*` 内の ' ' は、 ' または `.` ' の後にのみ続 `/` くことができます。 |  
| `http://foo.*.bar/baz` | ' ' `*` が ' の場合 `_host_` は、最初の文字である必要があります |  
| `http:/bar` | 区切り `_scheme_` 記号 \(' `/` ' が見つからない場合は" `//` "\) |  
| `foo://*` | ライセンスが無効 `_scheme_` |  

一部のスキームは、すべてのコンテキストでサポートされていません。

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> 元のページは次 [のページに表示されます](https://developer.chrome.com/extensions/match_patterns)。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
