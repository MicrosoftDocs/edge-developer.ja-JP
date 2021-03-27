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
# <a name="match-patterns"></a><span data-ttu-id="15e9c-104">一致パターン</span><span class="sxs-lookup"><span data-stu-id="15e9c-104">Match Patterns</span></span>

<span data-ttu-id="15e9c-105">ホストのアクセス許可とコンテンツ スクリプトの一致は、一致パターンで定義された一連の URL に基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="15e9c-105">Host permissions and content script matching are based on a set of URLs defined by match patterns.</span></span>  <span data-ttu-id="15e9c-106">一致パターンは、基本的には許可されたスキーム ( 、 で始まる URL であり、 ' ' 文字 `http` `https` `file` `ftp` を `*` 含めることができます。</span><span class="sxs-lookup"><span data-stu-id="15e9c-106">A match pattern is essentially a URL that begins with a permitted scheme (`http`, `https`, `file`, or `ftp`, and that can contain '`*`' characters.</span></span>  <span data-ttu-id="15e9c-107">特別なパターンは `<all_urls>` 、許可されたスキームで始まる任意の URL と一致します。</span><span class="sxs-lookup"><span data-stu-id="15e9c-107">The special pattern `<all_urls>` matches any URL that starts with a permitted scheme.</span></span>  <span data-ttu-id="15e9c-108">各一致パターンには、次の 3 つの部分があります。</span><span class="sxs-lookup"><span data-stu-id="15e9c-108">Each match pattern has 3 parts:</span></span>  

*   <span data-ttu-id="15e9c-109">_スキーム_— たとえば、または `http` `file`</span><span class="sxs-lookup"><span data-stu-id="15e9c-109">_scheme_ — for example, `http` or `file` or</span></span> `*`  

> [!NOTE]
> <span data-ttu-id="15e9c-110">URL への `file` アクセスは自動ではありません。</span><span class="sxs-lookup"><span data-stu-id="15e9c-110">Access to `file` URLs is not automatic.</span></span>  <span data-ttu-id="15e9c-111">ユーザーは、[拡張機能の管理] ページにアクセスし、要求する拡張機能ごとに `file` アクセスをオプトインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="15e9c-111">The user must visit the Extensions management page and opt in to `file` access for each Extension that requests it.</span></span>  

*   `_host_` <span data-ttu-id="15e9c-112">— たとえば、 `www.google.com` または `*.google.com` `*` 、 ; スキームがファイルの場合、ホスト パーツはありません。</span><span class="sxs-lookup"><span data-stu-id="15e9c-112">— for example, `www.google.com` or `*.google.com` or `*`; if the scheme is file, there is no host part.</span></span>  
*   `_path_` <span data-ttu-id="15e9c-113">— 、、 `/*` `/foo*` `/foo/bar` などです。</span><span class="sxs-lookup"><span data-stu-id="15e9c-113">— for example, `/*`, `/foo*`, or `/foo/bar`.</span></span>  <span data-ttu-id="15e9c-114">パスはホストアクセス許可に存在する必要がありますが、常にとして扱います `/*` 。</span><span class="sxs-lookup"><span data-stu-id="15e9c-114">The path must be present in a host permission, but is always treated as `/*`.</span></span>  

<span data-ttu-id="15e9c-115">基本的な構文:</span><span class="sxs-lookup"><span data-stu-id="15e9c-115">The basic syntax:</span></span>  

```shell
<url-pattern> := <scheme>://<host><path>
<scheme> := '*' | 'http' | 'https' | 'file' | 'ftp'
<host> := '*' | '*.' <any char except '/' and '*'>+
<path> := '/' <any chars>
```  

<span data-ttu-id="15e9c-116">意味は、スキーム、ホスト、またはパス パーツの中にあるかどうか `*` によって異なります。</span><span class="sxs-lookup"><span data-stu-id="15e9c-116">The meaning of `*` depends on whether it is in the scheme, host, or path part.</span></span>  <span data-ttu-id="15e9c-117">スキームがである場合 `*` 、スキームは 、または 、 または 、 `http` `https` のいずれかと一致します `file` `ftp` 。</span><span class="sxs-lookup"><span data-stu-id="15e9c-117">If the scheme is `*`, then it matches either `http` or `https`, and not `file`, or `ftp`.</span></span>  <span data-ttu-id="15e9c-118">ホストが単なる場合 `*` は、任意のホストと一致します。</span><span class="sxs-lookup"><span data-stu-id="15e9c-118">If the host is just `*`, then it matches any host.</span></span> <span data-ttu-id="15e9c-119">ホストが指定されている `*.hostname` 場合は、指定したホストまたはサブドメインと一致します。</span><span class="sxs-lookup"><span data-stu-id="15e9c-119">If the host is `*.hostname`, then it matches the specified host or any of the subdomains.</span></span>  <span data-ttu-id="15e9c-120">[パス] セクションでは、それぞれ `*` 0 文字以上に一致します。</span><span class="sxs-lookup"><span data-stu-id="15e9c-120">In the path section, each `*` matches 0 or more characters.</span></span>  <span data-ttu-id="15e9c-121">次の表に、有効なパターンを示します。</span><span class="sxs-lookup"><span data-stu-id="15e9c-121">The following table shows some valid patterns.</span></span>  

| <span data-ttu-id="15e9c-122">パターン</span><span class="sxs-lookup"><span data-stu-id="15e9c-122">Pattern</span></span> | <span data-ttu-id="15e9c-123">機能</span><span class="sxs-lookup"><span data-stu-id="15e9c-123">What it does</span></span> | <span data-ttu-id="15e9c-124">一致する URL の例</span><span class="sxs-lookup"><span data-stu-id="15e9c-124">Examples of matching URLs</span></span> |  
|:--- |:--- |:--- |  
| `http://*/*` | <span data-ttu-id="15e9c-125">http スキームを使用する URL と一致する</span><span class="sxs-lookup"><span data-stu-id="15e9c-125">Matches any URL that uses the http scheme</span></span> | `http://www.google.com` `http://example.org/foo/bar.html` |  
| `http://*/foo*` | <span data-ttu-id="15e9c-126">パスがで始まる限り、任意のホストで http スキームを使用する URL と一致します。</span><span class="sxs-lookup"><span data-stu-id="15e9c-126">Matches any URL that uses the http scheme, on any host, as long as the path starts with</span></span> `/foo` | `http://example.com/foo/bar.html` `http://www.google.com/foo` |  
| `https://*.google.com/foo*bar` | <span data-ttu-id="15e9c-127">パスがで始まりで終わる限り、https スキームを使用する任意の URL がホスト `google.com` \(、\など) にある場合に `www.google.com` `docs.google.com` `google.com` `/foo` 一致します。</span><span class="sxs-lookup"><span data-stu-id="15e9c-127">Matches any URL that uses the https scheme, is on a `google.com` host \(such as `www.google.com`, `docs.google.com`, or `google.com`\), as long as the path starts with `/foo` and ends with</span></span> `bar` | `https://www.google.com/foo/baz/bar` `https://docs.google.com/foobar` |  
| `http://example.org/foo/bar.html` | <span data-ttu-id="15e9c-128">指定した URL と一致する</span><span class="sxs-lookup"><span data-stu-id="15e9c-128">Matches the specified URL</span></span> | `http://example.org/foo/bar.html` |  
|`file:///foo*` | <span data-ttu-id="15e9c-129">パスがで始まるローカル ファイルと一致する</span><span class="sxs-lookup"><span data-stu-id="15e9c-129">Matches any local file whose path starts with</span></span> `/foo` | `file:///foo/bar.html` `file:///foo` |  
| `http://127.0.0.1/*` | <span data-ttu-id="15e9c-130">スキームを使用し、ホスト上にある `http` URL と一致する</span><span class="sxs-lookup"><span data-stu-id="15e9c-130">Matches any URL that uses the `http` scheme and is on the host</span></span> `127.0.0.1` | `http://127.0.0.1` `http://127.0.0.1/foo/bar.html` |  
| `*://mail.google.com/*` | <span data-ttu-id="15e9c-131">で始まる URL または で始まる URL に `http://mail.google.com` 一致 `https://mail.google.com` します。</span><span class="sxs-lookup"><span data-stu-id="15e9c-131">Matches any URL that starts with `http://mail.google.com` or `https://mail.google.com`.</span></span> | `http://mail.google.com/foo/baz/bar` `https://mail.google.com/foobar` |  
| `<all_urls>` | <span data-ttu-id="15e9c-132">許可されたスキームを使用する URL に一致します。</span><span class="sxs-lookup"><span data-stu-id="15e9c-132">Matches any URL that uses a permitted scheme.</span></span> <span data-ttu-id="15e9c-133">\(許可されるスキームの一覧については、このセクションの先頭を参照してください。\)</span><span class="sxs-lookup"><span data-stu-id="15e9c-133">\(See the beginning of this section for the list of permitted schemes.\)</span></span> | `http://example.org/foo/bar.html` `file:///bar/baz.html` |  

<span data-ttu-id="15e9c-134">パターンの一致の例を `_invalid_` 次に示します。</span><span class="sxs-lookup"><span data-stu-id="15e9c-134">Here are some examples of `_invalid_` pattern matches:</span></span>

| <span data-ttu-id="15e9c-135">パターンが悪い</span><span class="sxs-lookup"><span data-stu-id="15e9c-135">Bad pattern</span></span> | <span data-ttu-id="15e9c-136">それが悪い理由</span><span class="sxs-lookup"><span data-stu-id="15e9c-136">Why it is bad</span></span> |  
|:--- |:--- |  
| `http://www.foo.com` | <span data-ttu-id="15e9c-137">×</span><span class="sxs-lookup"><span data-stu-id="15e9c-137">No</span></span> `_path_` |  
| `http://*foo/bar` | <span data-ttu-id="15e9c-138">ホスト `*` 内の ' ' は、 ' または `.` ' の後にのみ続 `/` くことができます。</span><span class="sxs-lookup"><span data-stu-id="15e9c-138">'`*`' in the host can be followed only by a '`.`' or '`/`'</span></span> |  
| `http://foo.*.bar/baz` | <span data-ttu-id="15e9c-139">' ' `*` が ' の場合 `_host_` は、最初の文字である必要があります</span><span class="sxs-lookup"><span data-stu-id="15e9c-139">If '`*`' is in the `_host_`, it must be the first character</span></span> |  
| `http:/bar` | <span data-ttu-id="15e9c-140">区切り `_scheme_` 記号 \(' `/` ' が見つからない場合は" `//` "\)</span><span class="sxs-lookup"><span data-stu-id="15e9c-140">Missing `_scheme_` separator \('`/`' should be "`//`"\)</span></span> |  
| `foo://*` | <span data-ttu-id="15e9c-141">ライセンスが無効</span><span class="sxs-lookup"><span data-stu-id="15e9c-141">Invalid</span></span> `_scheme_` |  

<span data-ttu-id="15e9c-142">一部のスキームは、すべてのコンテキストでサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="15e9c-142">Some schemes are not supported in all contexts.</span></span>

> [!NOTE]
> <span data-ttu-id="15e9c-143">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="15e9c-143">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="15e9c-144">元のページは次 [のページに表示されます](https://developer.chrome.com/extensions/match_patterns)。</span><span class="sxs-lookup"><span data-stu-id="15e9c-144">The original page is found [here](https://developer.chrome.com/extensions/match_patterns).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="15e9c-146">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="15e9c-146">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
