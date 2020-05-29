---
description: Edge (Chromium) 拡張機能のエンタープライズポリシードキュメント。
title: マッチパターン
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/05/2019
ms.topic: article
ms.prod: microsoft-edge-chromium
keywords: edge-chromium、拡張機能の開発、ブラウザーの拡張、アドオン、パートナーセンター、開発者
ms.openlocfilehash: 16f54fcdc127822e89e050c367a681d886b0c8d0
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569579"
---
# マッチパターン

ホストのアクセス許可とコンテンツスクリプトの一致は、一致パターンによって定義された一連の Url に基づいています。  一致パターンは、基本的に、許可されたスキーム (、、、 `http` `https` または) で始まり、 `file` `ftp` "" 文字を含むことができる URL です `*` 。  特殊なパターンは、 `<all_urls>` 許可されたスキームで始まる任意の URL と一致します。  各一致パターンには3つの部分があります。  

*   _スキーム_: `http` or `file` など `*`  

> [!NOTE]
> Url へのアクセス `file` は、自動的には行われません。  ユーザーは、[拡張機能の管理] ページにアクセスして、 `file` 要求された各拡張機能へのアクセスをオプトインする必要があります。  

*   `_host_` —たとえば、またはのように `www.google.com` `*.google.com` `*` スキームがファイルの場合は、ホスト部分がありません。  
*   `_path_` —、、 `/*` `/foo*` またはなど `/foo/bar` 。  パスはホストのアクセス許可に存在する必要がありますが、常にとして扱われ `/*` ます。  

基本的な構文:  

```shell
<url-pattern> := <scheme>://<host><path>
<scheme> := '*' | 'http' | 'https' | 'file' | 'ftp'
<host> := '*' | '*.' <any char except '/' and '*'>+
<path> := '/' <any chars>
```  

の意味は、 `*` スキーム、ホスト、または path 部分のどちらであるかによって異なります。  スキームがの場合は、 `*` またはのどちらかに一致し `http` `https` `file` `ftp` ます。  ホストが単なる場合は `*` 、いずれかのホストと一致します。 ホストがの場合は `*.hostname` 、指定したホストまたは任意のサブドメインと一致します。  [Path] セクションでは、それぞれが `*` 0 以上の文字に一致します。  次の表は、有効なパターンを示しています。  

| 実線 | 機能 | 一致する Url の例 |  
|:--- |:--- |:--- |  
| `http://*/*` | Http スキームを使用する URL と一致する | `http://www.google.com` `http://example.org/foo/bar.html` |  
| `http://*/foo*` | パスが指定されている限り、任意のホストで http スキームを使用する URL を検索します。 `/foo` | `http://example.com/foo/bar.html` `http://www.google.com/foo` |  
| `https://*.google.com/foo*bar` | 指定された URL が https スキームを使っている場合は、 `google.com` (、、、\ などの) ホスト上で、 `www.google.com` `docs.google.com` `google.com` パスの先頭 `/foo` と末尾が `bar` | `https://www.google.com/foo/baz/bar` `https://docs.google.com/foobar` |  
| `http://example.org/foo/bar.html` | 指定した URL と一致します | `http://example.org/foo/bar.html` |  
|`file:///foo*` | Path で始まる任意のローカルファイルを検索します。 `/foo` | `file:///foo/bar.html` `file:///foo` |  
| `http://127.0.0.1/*` | スキームを使って `http` いて、ホスト上にある URL を検索します。 `127.0.0.1` | `http://127.0.0.1` `http://127.0.0.1/foo/bar.html` |  
| `*://mail.google.com/*` | またはで始まる任意の URL を検索 `http://mail.google.com` `https://mail.google.com` します。 | `http://mail.google.com/foo/baz/bar` `https://mail.google.com/foobar` |  
| `<all_urls>` | 許可されたスキームを使用する任意の URL を検索します。 \ (許可されているスキームの一覧については、このセクションの先頭を参照してください。 \) | `http://example.org/foo/bar.html` `file:///bar/baz.html` |  

パターンマッチの例をいくつか紹介し `_invalid_` ます。

| 不適切なパターン | 問題がある理由 |  
|:--- |:--- |  
| `http://www.foo.com` | なし `_path_` |  
| `http://*foo/bar` | ホストの ' `*` ' は、' `.` ' または `/` ' ' のみにすることができます。 |  
| `http://foo.*.bar/baz` | ' `*` ' がの場合は `_host_` 、最初の文字である必要があります。 |  
| `http:/bar` | 区切り文字がありません `_scheme_` \ (' `/` ' が "\" である必要があります `//` ) |  
| `foo://*` | ライセンスが無効 `_scheme_` |  

一部のスキームは、すべてのコンテキストでサポートされていません。

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developer.chrome.com/extensions/match_patterns/)にあります。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
