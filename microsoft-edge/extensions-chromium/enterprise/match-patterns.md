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
# <span data-ttu-id="59f79-104">マッチパターン</span><span class="sxs-lookup"><span data-stu-id="59f79-104">Match Patterns</span></span>

<span data-ttu-id="59f79-105">ホストのアクセス許可とコンテンツスクリプトの一致は、一致パターンによって定義された一連の Url に基づいています。</span><span class="sxs-lookup"><span data-stu-id="59f79-105">Host permissions and content script matching are based on a set of URLs defined by match patterns.</span></span>  <span data-ttu-id="59f79-106">一致パターンは、基本的に、許可されたスキーム (、、、 `http` `https` または) で始まり、 `file` `ftp` "" 文字を含むことができる URL です `*` 。</span><span class="sxs-lookup"><span data-stu-id="59f79-106">A match pattern is essentially a URL that begins with a permitted scheme (`http`, `https`, `file`, or `ftp`, and that can contain '`*`' characters.</span></span>  <span data-ttu-id="59f79-107">特殊なパターンは、 `<all_urls>` 許可されたスキームで始まる任意の URL と一致します。</span><span class="sxs-lookup"><span data-stu-id="59f79-107">The special pattern `<all_urls>` matches any URL that starts with a permitted scheme.</span></span>  <span data-ttu-id="59f79-108">各一致パターンには3つの部分があります。</span><span class="sxs-lookup"><span data-stu-id="59f79-108">Each match pattern has 3 parts:</span></span>  

*   <span data-ttu-id="59f79-109">_スキーム_: `http` or `file` など</span><span class="sxs-lookup"><span data-stu-id="59f79-109">_scheme_ — for example, `http` or `file` or</span></span> `*`  

> [!NOTE]
> <span data-ttu-id="59f79-110">Url へのアクセス `file` は、自動的には行われません。</span><span class="sxs-lookup"><span data-stu-id="59f79-110">Access to `file` URLs is not automatic.</span></span>  <span data-ttu-id="59f79-111">ユーザーは、[拡張機能の管理] ページにアクセスして、 `file` 要求された各拡張機能へのアクセスをオプトインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="59f79-111">The user must visit the Extensions management page and opt in to `file` access for each Extension that requests it.</span></span>  

*   `_host_` <span data-ttu-id="59f79-112">—たとえば、またはのように `www.google.com` `*.google.com` `*` スキームがファイルの場合は、ホスト部分がありません。</span><span class="sxs-lookup"><span data-stu-id="59f79-112">— for example, `www.google.com` or `*.google.com` or `*`; if the scheme is file, there is no host part.</span></span>  
*   `_path_` <span data-ttu-id="59f79-113">—、、 `/*` `/foo*` またはなど `/foo/bar` 。</span><span class="sxs-lookup"><span data-stu-id="59f79-113">— for example, `/*`, `/foo*`, or `/foo/bar`.</span></span>  <span data-ttu-id="59f79-114">パスはホストのアクセス許可に存在する必要がありますが、常にとして扱われ `/*` ます。</span><span class="sxs-lookup"><span data-stu-id="59f79-114">The path must be present in a host permission, but is always treated as `/*`.</span></span>  

<span data-ttu-id="59f79-115">基本的な構文:</span><span class="sxs-lookup"><span data-stu-id="59f79-115">The basic syntax:</span></span>  

```shell
<url-pattern> := <scheme>://<host><path>
<scheme> := '*' | 'http' | 'https' | 'file' | 'ftp'
<host> := '*' | '*.' <any char except '/' and '*'>+
<path> := '/' <any chars>
```  

<span data-ttu-id="59f79-116">の意味は、 `*` スキーム、ホスト、または path 部分のどちらであるかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="59f79-116">The meaning of `*` depends on whether it is in the scheme, host, or path part.</span></span>  <span data-ttu-id="59f79-117">スキームがの場合は、 `*` またはのどちらかに一致し `http` `https` `file` `ftp` ます。</span><span class="sxs-lookup"><span data-stu-id="59f79-117">If the scheme is `*`, then it matches either `http` or `https`, and not `file`, or `ftp`.</span></span>  <span data-ttu-id="59f79-118">ホストが単なる場合は `*` 、いずれかのホストと一致します。</span><span class="sxs-lookup"><span data-stu-id="59f79-118">If the host is just `*`, then it matches any host.</span></span> <span data-ttu-id="59f79-119">ホストがの場合は `*.hostname` 、指定したホストまたは任意のサブドメインと一致します。</span><span class="sxs-lookup"><span data-stu-id="59f79-119">If the host is `*.hostname`, then it matches the specified host or any of the subdomains.</span></span>  <span data-ttu-id="59f79-120">[Path] セクションでは、それぞれが `*` 0 以上の文字に一致します。</span><span class="sxs-lookup"><span data-stu-id="59f79-120">In the path section, each `*` matches 0 or more characters.</span></span>  <span data-ttu-id="59f79-121">次の表は、有効なパターンを示しています。</span><span class="sxs-lookup"><span data-stu-id="59f79-121">The following table shows some valid patterns.</span></span>  

| <span data-ttu-id="59f79-122">実線</span><span class="sxs-lookup"><span data-stu-id="59f79-122">Pattern</span></span> | <span data-ttu-id="59f79-123">機能</span><span class="sxs-lookup"><span data-stu-id="59f79-123">What it does</span></span> | <span data-ttu-id="59f79-124">一致する Url の例</span><span class="sxs-lookup"><span data-stu-id="59f79-124">Examples of matching URLs</span></span> |  
|:--- |:--- |:--- |  
| `http://*/*` | <span data-ttu-id="59f79-125">Http スキームを使用する URL と一致する</span><span class="sxs-lookup"><span data-stu-id="59f79-125">Matches any URL that uses the http scheme</span></span> | `http://www.google.com` `http://example.org/foo/bar.html` |  
| `http://*/foo*` | <span data-ttu-id="59f79-126">パスが指定されている限り、任意のホストで http スキームを使用する URL を検索します。</span><span class="sxs-lookup"><span data-stu-id="59f79-126">Matches any URL that uses the http scheme, on any host, as long as the path starts with</span></span> `/foo` | `http://example.com/foo/bar.html` `http://www.google.com/foo` |  
| `https://*.google.com/foo*bar` | <span data-ttu-id="59f79-127">指定された URL が https スキームを使っている場合は、 `google.com` (、、、\ などの) ホスト上で、 `www.google.com` `docs.google.com` `google.com` パスの先頭 `/foo` と末尾が</span><span class="sxs-lookup"><span data-stu-id="59f79-127">Matches any URL that uses the https scheme, is on a `google.com` host \(such as `www.google.com`, `docs.google.com`, or `google.com`\), as long as the path starts with `/foo` and ends with</span></span> `bar` | `https://www.google.com/foo/baz/bar` `https://docs.google.com/foobar` |  
| `http://example.org/foo/bar.html` | <span data-ttu-id="59f79-128">指定した URL と一致します</span><span class="sxs-lookup"><span data-stu-id="59f79-128">Matches the specified URL</span></span> | `http://example.org/foo/bar.html` |  
|`file:///foo*` | <span data-ttu-id="59f79-129">Path で始まる任意のローカルファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="59f79-129">Matches any local file whose path starts with</span></span> `/foo` | `file:///foo/bar.html` `file:///foo` |  
| `http://127.0.0.1/*` | <span data-ttu-id="59f79-130">スキームを使って `http` いて、ホスト上にある URL を検索します。</span><span class="sxs-lookup"><span data-stu-id="59f79-130">Matches any URL that uses the `http` scheme and is on the host</span></span> `127.0.0.1` | `http://127.0.0.1` `http://127.0.0.1/foo/bar.html` |  
| `*://mail.google.com/*` | <span data-ttu-id="59f79-131">またはで始まる任意の URL を検索 `http://mail.google.com` `https://mail.google.com` します。</span><span class="sxs-lookup"><span data-stu-id="59f79-131">Matches any URL that starts with `http://mail.google.com` or `https://mail.google.com`.</span></span> | `http://mail.google.com/foo/baz/bar` `https://mail.google.com/foobar` |  
| `<all_urls>` | <span data-ttu-id="59f79-132">許可されたスキームを使用する任意の URL を検索します。</span><span class="sxs-lookup"><span data-stu-id="59f79-132">Matches any URL that uses a permitted scheme.</span></span> <span data-ttu-id="59f79-133">\ (許可されているスキームの一覧については、このセクションの先頭を参照してください。 \)</span><span class="sxs-lookup"><span data-stu-id="59f79-133">\(See the beginning of this section for the list of permitted schemes.\)</span></span> | `http://example.org/foo/bar.html` `file:///bar/baz.html` |  

<span data-ttu-id="59f79-134">パターンマッチの例をいくつか紹介し `_invalid_` ます。</span><span class="sxs-lookup"><span data-stu-id="59f79-134">Here are some examples of `_invalid_` pattern matches:</span></span>

| <span data-ttu-id="59f79-135">不適切なパターン</span><span class="sxs-lookup"><span data-stu-id="59f79-135">Bad pattern</span></span> | <span data-ttu-id="59f79-136">問題がある理由</span><span class="sxs-lookup"><span data-stu-id="59f79-136">Why it is bad</span></span> |  
|:--- |:--- |  
| `http://www.foo.com` | <span data-ttu-id="59f79-137">なし</span><span class="sxs-lookup"><span data-stu-id="59f79-137">No</span></span> `_path_` |  
| `http://*foo/bar` | <span data-ttu-id="59f79-138">ホストの ' `*` ' は、' `.` ' または `/` ' ' のみにすることができます。</span><span class="sxs-lookup"><span data-stu-id="59f79-138">'`*`' in the host can be followed only by a '`.`' or '`/`'</span></span> |  
| `http://foo.*.bar/baz` | <span data-ttu-id="59f79-139">' `*` ' がの場合は `_host_` 、最初の文字である必要があります。</span><span class="sxs-lookup"><span data-stu-id="59f79-139">If '`*`' is in the `_host_`, it must be the first character</span></span> |  
| `http:/bar` | <span data-ttu-id="59f79-140">区切り文字がありません `_scheme_` \ (' `/` ' が "\" である必要があります `//` )</span><span class="sxs-lookup"><span data-stu-id="59f79-140">Missing `_scheme_` separator \('`/`' should be "`//`"\)</span></span> |  
| `foo://*` | <span data-ttu-id="59f79-141">ライセンスが無効</span><span class="sxs-lookup"><span data-stu-id="59f79-141">Invalid</span></span> `_scheme_` |  

<span data-ttu-id="59f79-142">一部のスキームは、すべてのコンテキストでサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="59f79-142">Some schemes are not supported in all contexts.</span></span>

> [!NOTE]
> <span data-ttu-id="59f79-143">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="59f79-143">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="59f79-144">元のページは[ここ](https://developer.chrome.com/extensions/match_patterns/)にあります。</span><span class="sxs-lookup"><span data-stu-id="59f79-144">The original page is found [here](https://developer.chrome.com/extensions/match_patterns/).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="59f79-146">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="59f79-146">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
