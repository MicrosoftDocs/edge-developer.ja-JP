---
description: '[ネットワーク] パネルを使用して、ページリソース要求を監視およびプロファイルする'
title: DevTools-ネットワーク
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、ネットワーク、読み込み時間、http、https、ブラウザキャッシュ、HAR
ms.custom: seodec18
ms.openlocfilehash: 0b190f5163f9b7a9f9920877a94577177053e4f6
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569664"
---
# <span data-ttu-id="a2447-104">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="a2447-104">Network</span></span>

<span data-ttu-id="a2447-105">ネットワークパネルを使用して、**ネットワーク**経由で送信された要求と応答を監視、検査、およびプロファイルします。</span><span class="sxs-lookup"><span data-stu-id="a2447-105">Use the **Network** panel to monitor, inspect and profile the requests and responses sent over the wire.</span></span> <span data-ttu-id="a2447-106">これにより、次のことが可能になります。</span><span class="sxs-lookup"><span data-stu-id="a2447-106">With it, you can:</span></span>

 - <span data-ttu-id="a2447-107">ページによって行わ[れたすべてのリソース要求の記録を参照する](#network-summary)</span><span class="sxs-lookup"><span data-stu-id="a2447-107">[Browse a record of all the resource requests](#network-summary) made by the page</span></span>
 - <span data-ttu-id="a2447-108">新規ユーザーと返送する[サイトの読み込み時間を測定](#summary-bar)する</span><span class="sxs-lookup"><span data-stu-id="a2447-108">[Measure the load time of your site](#summary-bar) for new and returning users</span></span> 
 - <span data-ttu-id="a2447-109">ページとネットワークの間でやり取りさ[れるヘッダー、メッセージ本文、パラメーター、cookie を検査する](#request-details)</span><span class="sxs-lookup"><span data-stu-id="a2447-109">[Inspect the headers, message bodies, parameters, and cookies](#request-details) exchanged between your page and the network</span></span>
 - <span data-ttu-id="a2447-110">サイトの読み込み時間で[ボトルネックを引き起こすネットワークイベントを特定する](#timings)</span><span class="sxs-lookup"><span data-stu-id="a2447-110">[Identify the network events causing bottlenecks](#timings) in the load time of your site</span></span>

![Microsoft Edge DevTools ネットワークパネル](./media/network.png)

## <span data-ttu-id="a2447-112">ネットワークの概要</span><span class="sxs-lookup"><span data-stu-id="a2447-112">Network summary</span></span>

<span data-ttu-id="a2447-113">DevTools を開くと、既定でネットワークプロファイリングが有効になります。</span><span class="sxs-lookup"><span data-stu-id="a2447-113">When you open  DevTools, network profiling is turned on by default.</span></span> <span data-ttu-id="a2447-114">Active browser タブからのすべてのネットワークトラフィックは [ネットワーク] の概要リストに記録されます。これは、*ネットワーク*よりもさまざまな devtools パネルで作業している場合でも同様です。</span><span class="sxs-lookup"><span data-stu-id="a2447-114">All the network traffic from your active browser tab is recorded in the network summary list, even while you are working in a different  DevTools panel than *Network*.</span></span>

![進行中のネットワークプロファイリングインジケーター](./media/network_profile_indicator.png)

### <span data-ttu-id="a2447-116">ツール バー</span><span class="sxs-lookup"><span data-stu-id="a2447-116">Toolbar</span></span>

<span data-ttu-id="a2447-117">このツールバーには、ページのネットワークアクティビティのプロファイリングとフィルター処理を行うためのコントロールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="a2447-117">The toolbar provides controls for profiling and filtering the network activity of your page.</span></span> 

![ネットワークプロファイラーのツールバー](./media/network_toolbar.png)

1. <span data-ttu-id="a2447-119">[**プロファイリングセッションの開始/停止**]: 既定では、ネットワークプロファイリングは有効になり、ネットワークトラフィックはネットワーク[**プロファイラー**](#network-request-list)の一覧に記録されます。</span><span class="sxs-lookup"><span data-stu-id="a2447-119">**Start / Stop profiling session**: By default, network profiling is turned on, and network traffic will be logged in the [**Network profiler**](#network-request-list) list.</span></span> <span data-ttu-id="a2447-120">[ **Stop** ()] ボタンを使用して、ネットワークキャプチャをオフにすることができ `Ctrl+E` ます。</span><span class="sxs-lookup"><span data-stu-id="a2447-120">You can turn off network capture with the **Stop** (`Ctrl+E`) button.</span></span>

2. <span data-ttu-id="a2447-121">**Har としてエクスポート**: 現在のネットワークプロファイリングセッション ( `Ctrl+S` ) を JSON 形式の[HTTP アーカイブ (har)](https://dvcs.w3.org/hg/webperf/raw-file/tip/specs/HAR/Overview.html)ファイルとして保存することができます。</span><span class="sxs-lookup"><span data-stu-id="a2447-121">**Export as HAR**: You can save the current network profiling session (`Ctrl+S`) as a JSON-formatted [HTTP Archive (HAR)](https://dvcs.w3.org/hg/webperf/raw-file/tip/specs/HAR/Overview.html) file.</span></span> 

3. <span data-ttu-id="a2447-122">[**コンテンツタイプフィルター**]: 特定のコンテンツ要求 (*ドキュメント、スタイルシート、画像、スクリプト、メディア、フォント、xhr など*) でネットワーク要求リストをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="a2447-122">**Content type filter**: Filter the network request list by specific content requests (*Documents, Style sheets, Images, Scripts, Media, Fonts, XHR, Other*).</span></span> <span data-ttu-id="a2447-123">既定では、すべてのコンテンツタイプが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2447-123">By default all content types are shown.</span></span>

4. <span data-ttu-id="a2447-124">**検索**: フィルター ( `Ctrl+F` ) 指定した検索文字列を含むエントリ名 (リソースパス) によって、ネットワーク要求リストをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="a2447-124">**Find**: Filter (`Ctrl+F`) the network request list by entry names (resource paths) containing a specified search string.</span></span>

5. <span data-ttu-id="a2447-125">**常にサーバーから更新**: 押し下げこのボタンは、ブラウザーキャッシュではなく、ネットワークからページリソースを強制的に読み込みます。</span><span class="sxs-lookup"><span data-stu-id="a2447-125">**Always refresh from server**: Depressing this button will force page resources to load from the network rather than the browser cache.</span></span> <span data-ttu-id="a2447-126">を押すと、1回だけネットワークからページを更新することができ `Ctrl+F5` ます。</span><span class="sxs-lookup"><span data-stu-id="a2447-126">You can refresh the page from  network a single time by pressing `Ctrl+F5`.</span></span>

6. <span data-ttu-id="a2447-127">**すべてのネットワーク要求についてサービスワーカーをスキップ**する: 登録されているサービスワーカーをネットワークプロキシとして無効にします。</span><span class="sxs-lookup"><span data-stu-id="a2447-127">**Bypass Service Worker for all network requests**: Disable your registered service workers as network proxies.</span></span> 

7. <span data-ttu-id="a2447-128">クリアボタン</span><span class="sxs-lookup"><span data-stu-id="a2447-128">Clear buttons</span></span>

   - <span data-ttu-id="a2447-129">**キャッシュの消去**: ブラウザーキャッシュに保存されているすべてのリソースを削除します (ページの読み込みを初めて実行したときにエミュレートします)。</span><span class="sxs-lookup"><span data-stu-id="a2447-129">**Clear cache**: Removes all resources stored in the browser cache (and emulates a first-time experience loading the page).</span></span>
   - <span data-ttu-id="a2447-130">[ **Cookie のクリア**]: 指定したドメインのすべての cookie を削除します (サイトの初回起動時のエクスペリエンスをエミュレートします)。</span><span class="sxs-lookup"><span data-stu-id="a2447-130">**Clear cookies**: Removes all cookies for the given domain (and emulates a first-time experience of the site).</span></span>
   - <span data-ttu-id="a2447-131">**[移動] でエントリをクリア**: ページの移動時に記録されたトラフィックをクリアします。</span><span class="sxs-lookup"><span data-stu-id="a2447-131">**Clear entries on navigate**: Recorded traffic is cleared upon page navigation.</span></span> <span data-ttu-id="a2447-132">これは既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="a2447-132">This is turned on by default.</span></span>
   - <span data-ttu-id="a2447-133">[**セッションのクリア**]: ネットワークの**概要**リストからすべてのネットワーク要求エントリをクリアします。</span><span class="sxs-lookup"><span data-stu-id="a2447-133">**Clear session**: Clears all network request entries from the **Network summary** list.</span></span>

### <span data-ttu-id="a2447-134">ネットワーク要求リスト</span><span class="sxs-lookup"><span data-stu-id="a2447-134">Network request list</span></span>

<span data-ttu-id="a2447-135">すべてのネットワークトラフィックは、一覧に記録されます (ナビゲーションの際に、手動でオフにした場合、または DevTools が閉じられるまで)。</span><span class="sxs-lookup"><span data-stu-id="a2447-135">All network traffic is recorded to a list (until cleared upon navigation, manually cleared, or  DevTools are closed).</span></span> <span data-ttu-id="a2447-136">エントリをクリックすると[、要求の](#request-details)詳細な表示が開きます。</span><span class="sxs-lookup"><span data-stu-id="a2447-136">Clicking on any entry will open a more [detailed view of the request](#request-details).</span></span>

![ネットワーク要求リスト](./media/network_request_list.png)

<span data-ttu-id="a2447-138">ネットワーク要求リストには、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a2447-138">The network request list includes the following info:</span></span> 

<span data-ttu-id="a2447-139">列</span><span class="sxs-lookup"><span data-stu-id="a2447-139">Column</span></span> | <span data-ttu-id="a2447-140">説明</span><span class="sxs-lookup"><span data-stu-id="a2447-140">Description</span></span> 
:------------ | :------------- 
**<span data-ttu-id="a2447-141">Name (名前)</span><span class="sxs-lookup"><span data-stu-id="a2447-141">Name</span></span>** | <span data-ttu-id="a2447-142">要求の名前と URL パス</span><span class="sxs-lookup"><span data-stu-id="a2447-142">Name and URL path of the request</span></span>
**<span data-ttu-id="a2447-143">プロトコル</span><span class="sxs-lookup"><span data-stu-id="a2447-143">Protocol</span></span>** |  <span data-ttu-id="a2447-144">要求のプロトコルの種類 ( *HTTPS、HTTP/2*など)</span><span class="sxs-lookup"><span data-stu-id="a2447-144">Type of protocol for the request (such as *HTTPS, HTTP/2*)</span></span>
**<span data-ttu-id="a2447-145">メソッド</span><span class="sxs-lookup"><span data-stu-id="a2447-145">Method</span></span>** |    <span data-ttu-id="a2447-146">要求に使用される[HTTP メソッド](https://developer.mozilla.org/docs/Web/HTTP/Methods)</span><span class="sxs-lookup"><span data-stu-id="a2447-146">[HTTP method](https://developer.mozilla.org/docs/Web/HTTP/Methods) used for the request</span></span>
**<span data-ttu-id="a2447-147">結果</span><span class="sxs-lookup"><span data-stu-id="a2447-147">Result</span></span>** |    <span data-ttu-id="a2447-148">[HTTP 応答状態](https://developer.mozilla.org/docs/Web/HTTP/Status)コード</span><span class="sxs-lookup"><span data-stu-id="a2447-148">[HTTP response status](https://developer.mozilla.org/docs/Web/HTTP/Status)  code</span></span>
**<span data-ttu-id="a2447-149">コンテンツ タイプ</span><span class="sxs-lookup"><span data-stu-id="a2447-149">Content type</span></span>** |  <span data-ttu-id="a2447-150">要求されたメディアの種類 ([MIME の種類](https://en.wikipedia.org/wiki/Media_type))</span><span class="sxs-lookup"><span data-stu-id="a2447-150">Type of media requested ([MIME type](https://en.wikipedia.org/wiki/Media_type))</span></span>
**<span data-ttu-id="a2447-151">受信</span><span class="sxs-lookup"><span data-stu-id="a2447-151">Received</span></span>** | <span data-ttu-id="a2447-152">サーバーによって配信されたときの応答のサイズ (キャッシュされた応答に対しては計算されません)</span><span class="sxs-lookup"><span data-stu-id="a2447-152">Size of the response as delivered by the server (not calculated for cached responses)</span></span>
**<span data-ttu-id="a2447-153">Time</span><span class="sxs-lookup"><span data-stu-id="a2447-153">Time</span></span>** |  <span data-ttu-id="a2447-154">サーバーの応答を読み込む時間 (キャッシュされた応答に対して計算されません)</span><span class="sxs-lookup"><span data-stu-id="a2447-154">Time to load the server response (not calculated for cached responses)</span></span>
**<span data-ttu-id="a2447-155">・</span><span class="sxs-lookup"><span data-stu-id="a2447-155">Initiator</span></span>** | <span data-ttu-id="a2447-156">要求の開始を担当するサブシステム (*パーサー、リダイレクト、スクリプトなど*)</span><span class="sxs-lookup"><span data-stu-id="a2447-156">Subsystem responsible for initiating the request (such as *Parser, Redirect, Script, Other*)</span></span>
**<span data-ttu-id="a2447-157">タイムライン</span><span class="sxs-lookup"><span data-stu-id="a2447-157">Timeline</span></span>** | <span data-ttu-id="a2447-158">要求のネットワークイベント (*ストール、解決 (DNS)、接続 (TCP)、SSL、送信、待機 (TTFB)、ダウンロード*など) のための視覚的なタイムライン。</span><span class="sxs-lookup"><span data-stu-id="a2447-158">Visual timeline for the network events of the request (such as *Stalled, Resolving(DNS), Connecting(TCP), SSL, Sending, Waiting(TTFB), Downloading*).</span></span> <span data-ttu-id="a2447-159">グラフの上にマウスポインターを置くと、ネットワーク[ネットワークのタイミング](#timings)がより細かく分類されます。</span><span class="sxs-lookup"><span data-stu-id="a2447-159">Hovering over the chart provides the more granular breakdown of network [network timings](#timings)).</span></span>

### <span data-ttu-id="a2447-160">サマリーバー</span><span class="sxs-lookup"><span data-stu-id="a2447-160">Summary bar</span></span>

<span data-ttu-id="a2447-161">**ネットワーク**パネルの下部にあるバーには、ネットワークプロファイリングセッション中の HTTP ネットワークのエラー、要求、データ転送、読み込み時間の合計数が表示されます (つまり、devtools が開かれ、ネットワークトラフィックが記録されているため)。</span><span class="sxs-lookup"><span data-stu-id="a2447-161">The bar at the bottom of **Network** panel summarizes the total number of HTTP network errors, requests, data transfered, and load times during the network profiling session (i.e., since  DevTools were opened and recording network traffic).</span></span>

![ネットワークの概要バー](./media/network_summary_bar.png)

<span data-ttu-id="a2447-163">[**経過時間**] は、プロファイリングセッションの開始と、最後のリソースがネットワークからダウンロードされた時刻の間の時間を意味します。</span><span class="sxs-lookup"><span data-stu-id="a2447-163">**Elapsed time** means the time between the start of the profiling session and when the last resource was downloaded from the network.</span></span> <span data-ttu-id="a2447-164">ブラウザーキャッシュから取得されたリソースは、この番号に時間を計上しません。</span><span class="sxs-lookup"><span data-stu-id="a2447-164">Resources fetched from the browser cache do not accrue time to this number.</span></span> 

<span data-ttu-id="a2447-165">**DOM 読み込み時間**は、プロファイリングセッションの開始と、ページドキュメントの構造が読み込まれ解析されたことを示すために[domcontentloaded](https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded)イベントが発生した時刻を示します (ただし、すべてのスタイルシート、画像、サブフレームは存在しません)。</span><span class="sxs-lookup"><span data-stu-id="a2447-165">**DOM load time** means the time between the start of the profiling session and when the [DOMContentLoaded](https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded) event was fired to indicate that the structure of the page document has been loaded and parsed (though not necessarily any stylesheets, images or subframes).</span></span>

<span data-ttu-id="a2447-166">[**ページの読み込み時間]** は、プロファイリングセッションの開始時点と、ページドキュメント (およびそのすべてのリソース) が完全に読み込まれたことを示す[load](https://developer.mozilla.org/docs/Web/Events/load)イベントが発生したタイミングを意味します。</span><span class="sxs-lookup"><span data-stu-id="a2447-166">**Page load time** time means the time between the start of the profiling session and when the [load](https://developer.mozilla.org/docs/Web/Events/load) event was fired to indicate that the page document (and all its resources) has been fully loaded.</span></span>

## <span data-ttu-id="a2447-167">リクエストの詳細</span><span class="sxs-lookup"><span data-stu-id="a2447-167">Request details</span></span>

<span data-ttu-id="a2447-168">[[**ネットワークの概要**](#network-summary)] ボックスの一覧のエントリをクリックすると、[[**要求の詳細**](#request-details)] ウィンドウが開き、次の各タブに詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2447-168">Clicking on any entry in the [**Network summary**](#network-summary) list will open the [**Request details**](#request-details) pane with further information in each of the following tabs.</span></span>

![ネットワーク要求の詳細ウィンドウ](./media/network_request_details.png)

### <span data-ttu-id="a2447-170">ヘッダー</span><span class="sxs-lookup"><span data-stu-id="a2447-170">Headers</span></span>
<span data-ttu-id="a2447-171">サーバーから送受信された[HTTP ヘッダー](https://developer.mozilla.org/docs/Web/HTTP/Headers)を表示します。</span><span class="sxs-lookup"><span data-stu-id="a2447-171">Displays the [HTTP headers](https://developer.mozilla.org/docs/Web/HTTP/Headers) sent to and received from the server.</span></span> <span data-ttu-id="a2447-172">ヘッダーエントリを右クリックして、 `Ctrl+C` クリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="a2447-172">Right-click on any header entry to copy it (`Ctrl+C`) to the clipboard.</span></span> <span data-ttu-id="a2447-173">キーを押す `Shift` か、all () を選択して、エントリを複数選択することもでき `Ctrl+A` ます。</span><span class="sxs-lookup"><span data-stu-id="a2447-173">You can also multi-select entries by holding down the `Shift` key or select all (`Ctrl+A`).</span></span>

### <span data-ttu-id="a2447-174">本文</span><span class="sxs-lookup"><span data-stu-id="a2447-174">Body</span></span>
<span data-ttu-id="a2447-175">要求と応答のペイロードの本文データ (存在する場合) を表示します。</span><span class="sxs-lookup"><span data-stu-id="a2447-175">Displays the body data (if available) of the request and response payloads.</span></span>

<span data-ttu-id="a2447-176">画像コンテンツは、寸法とサイズのデータと共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2447-176">Image content is displayed with dimensions and size data.</span></span>

<span data-ttu-id="a2447-177">テキストコンテンツは、より読みやすく**するために**、表示されている縮小したコンテンツを**きれい**に書式設定するオプションが含まれる (読み取り専用) エディターに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2447-177">Text content appears in a (read-only) editor with options to format minified content with **Pretty print** and/or **Word wrap** for easier readability.</span></span>

![[要求の詳細] ウィンドウの [本文] タブ](./media/network_details_body.png)

### <span data-ttu-id="a2447-179">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a2447-179">Parameters</span></span>
<span data-ttu-id="a2447-180">GET 要求のクエリ文字列パラメーターを表示します。</span><span class="sxs-lookup"><span data-stu-id="a2447-180">Displays query string parameters for GET requests.</span></span> <span data-ttu-id="a2447-181">POST 要求のパラメーターはヘッダーで送信されますが、GET 要求にはそれらの要求が URL で含まれます。</span><span class="sxs-lookup"><span data-stu-id="a2447-181">While the parameters of POST requests are sent in the headers, GET requests include them in the URL.</span></span> <span data-ttu-id="a2447-182">読みやすくするために、ここで分割されています。</span><span class="sxs-lookup"><span data-stu-id="a2447-182">They're broken out here for easier reading.</span></span>

<span data-ttu-id="a2447-183">任意の行を右クリックして、 `Ctrl+C` クリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="a2447-183">Right-click on any row to copy it (`Ctrl+C`) to the clipboard.</span></span> <span data-ttu-id="a2447-184">キーを押す `Shift` か、all () を選択して、エントリを複数選択することもでき `Ctrl+A` ます。</span><span class="sxs-lookup"><span data-stu-id="a2447-184">You can also multi-select entries by holding down the `Shift` key or select all (`Ctrl+A`).</span></span>

### <span data-ttu-id="a2447-185">Cookie</span><span class="sxs-lookup"><span data-stu-id="a2447-185">Cookies</span></span>
<span data-ttu-id="a2447-186">キーと値のペアとして送信または受信される cookie を表示します。</span><span class="sxs-lookup"><span data-stu-id="a2447-186">Displays cookies that are sent or received as key/value pairs.</span></span>

<span data-ttu-id="a2447-187">任意の行を右クリックして、 `Ctrl+C` クリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="a2447-187">Right-click on any row to copy it (`Ctrl+C`) to the clipboard.</span></span> <span data-ttu-id="a2447-188">キーを押す `Shift` か、all () を選択して、エントリを複数選択することもでき `Ctrl+A` ます。</span><span class="sxs-lookup"><span data-stu-id="a2447-188">You can also multi-select entries by holding down the `Shift` key or select all (`Ctrl+A`).</span></span>

<span data-ttu-id="a2447-189">指定したドメインに対して保存されている cookie は、[ツールバー](#network-summary)で消去できます ([**cookie のクリア**] ボタン)。</span><span class="sxs-lookup"><span data-stu-id="a2447-189">You can clear the stored cookies for the given domain from the [Toolbar](#network-summary) (**Clear cookies** button).</span></span> 

### <span data-ttu-id="a2447-190">切り替え</span><span class="sxs-lookup"><span data-stu-id="a2447-190">Timings</span></span>

<span data-ttu-id="a2447-191">[**タイミング**] タブには、選択したリソースの読み込みに関連するネットワークイベントのタイムラインが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2447-191">The **Timings** tab provides a timeline of network events involved in the loading of the selected resource.</span></span> <span data-ttu-id="a2447-192">これは、[ネットワーク要求リスト](#network-request-list)の [*タイムライン*] 列にある情報に似ていますが、要求キューでの待機時間 (*ストール*)、DNS 解決、TCP 接続の確立など、ネットワーク経由で送信された要求につながるイベントも含まれています。</span><span class="sxs-lookup"><span data-stu-id="a2447-192">This is similar to the information found in the *Timeline* column of the [Network request list](#network-request-list), but also includes the events leading up to the request being sent over the wire, such as time spent waiting (*Stalled*) in the request queue, DNS resolution, and establishing the TCP connection.</span></span> 

![[要求の詳細] ウィンドウの [タイミング] タブ](./media/network_details_timings.png)

<span data-ttu-id="a2447-194">他のリソースへのリダイレクションまたはその他のリソースへのリダイレクションが示されている。リンクをクリックすると、[ネットワーク[要求の詳細](#request details)] ウィンドウでフォーカスがそのリソースに設定されます。</span><span class="sxs-lookup"><span data-stu-id="a2447-194">Redirections to/from other resources are noted, and clicking on the link will set focus to that resource in the network [request details](#request details) pane.</span></span>

<span data-ttu-id="a2447-195">キャッシュから読み込まれたリソースはネットワーク待ち時間の影響を受けないため、ネットワーク*タイミング*グラフは表示されません。</span><span class="sxs-lookup"><span data-stu-id="a2447-195">Resouces loaded from the cache are not affected by network latency, so no network *Timings* chart will display.</span></span>

![キャッシュから読み込まれたリダイレクトされたリソース](./media/network_details_timings_cache_redirect.png)

<span data-ttu-id="a2447-197">ここでは、特定のリソースに関して表示される可能性のあるさまざまなネットワークイベントを時系列順に示します。</span><span class="sxs-lookup"><span data-stu-id="a2447-197">Here are the different network events you might see for a given resource, in chronological order:</span></span>

#### <span data-ttu-id="a2447-198">停止</span><span class="sxs-lookup"><span data-stu-id="a2447-198">Stalled</span></span>

<span data-ttu-id="a2447-199">要求キューで利用可能なネットワーク接続の待機に費やされた時間です。</span><span class="sxs-lookup"><span data-stu-id="a2447-199">Time spent waiting for an available network connection in the request queue.</span></span> <span data-ttu-id="a2447-200">HTTP 1.0/1.1 の場合、Microsoft Edge では、1つのホストにつき最大6つの同時 TCP 接続を許可します。</span><span class="sxs-lookup"><span data-stu-id="a2447-200">For HTTP 1.0/1.1, Microsoft Edge allows a maximum of six (6) simultaneous TCP connections per hostname.</span></span> 

#### <span data-ttu-id="a2447-201">解決 (DNS)</span><span class="sxs-lookup"><span data-stu-id="a2447-201">Resolving (DNS)</span></span>

<span data-ttu-id="a2447-202">DNS ([ドメインネームシステム](https://en.wikipedia.org/wiki/Domain_Name_System)) 内のリソースのホスト名の IP アドレスの検索に費やした時間。</span><span class="sxs-lookup"><span data-stu-id="a2447-202">Time spent looking up the IP address for the hostname of the resource in the DNS ([Domain Name System](https://en.wikipedia.org/wiki/Domain_Name_System)).</span></span>

#### <span data-ttu-id="a2447-203">接続 (TCP)</span><span class="sxs-lookup"><span data-stu-id="a2447-203">Connecting (TCP)</span></span>

<span data-ttu-id="a2447-204">TCP ([伝送制御プロトコル](https://en.wikipedia.org/wiki/Transmission_Control_Protocol)) 接続を確立するために費やされた時間。</span><span class="sxs-lookup"><span data-stu-id="a2447-204">Time spent establishing the TCP ([Transmission Control Protocol](https://en.wikipedia.org/wiki/Transmission_Control_Protocol)) connection.</span></span>

#### <span data-ttu-id="a2447-205">方式</span><span class="sxs-lookup"><span data-stu-id="a2447-205">SSL</span></span>

<span data-ttu-id="a2447-206">ホストの[プロキシサーバー](https://en.wikipedia.org/wiki/Proxy_server)との SSL ([Secure Sockets layer](https://en.wikipedia.org/wiki/Transport_Layer_Security)) 接続のネゴシエーションに費やされた時間。</span><span class="sxs-lookup"><span data-stu-id="a2447-206">Time spent negotiating a SSL ([Secure Sockets Layer](https://en.wikipedia.org/wiki/Transport_Layer_Security))  connection with the [proxy server](https://en.wikipedia.org/wiki/Proxy_server) for the host.</span></span>

#### <span data-ttu-id="a2447-207">とき</span><span class="sxs-lookup"><span data-stu-id="a2447-207">Sending</span></span>

<span data-ttu-id="a2447-208">リソース要求の送信に費やした時間です。</span><span class="sxs-lookup"><span data-stu-id="a2447-208">Time spent sending the resource request.</span></span>

#### <span data-ttu-id="a2447-209">待機中 (TTFB)</span><span class="sxs-lookup"><span data-stu-id="a2447-209">Waiting (TTFB)</span></span>

<span data-ttu-id="a2447-210">ホストサーバーからの応答の最初のバイト ("最初のバイト"、または*TTFB*) への待機時間。</span><span class="sxs-lookup"><span data-stu-id="a2447-210">Time spent waiting for the first byte of the response from the host server ("time to first byte", or *TTFB*).</span></span>

#### <span data-ttu-id="a2447-211">ダウンロード</span><span class="sxs-lookup"><span data-stu-id="a2447-211">Downloading</span></span>

<span data-ttu-id="a2447-212">サーバーからの応答の読み取りに費やされた時間です。</span><span class="sxs-lookup"><span data-stu-id="a2447-212">Time spent reading the response from the server.</span></span>

## <span data-ttu-id="a2447-213">ショートカット</span><span class="sxs-lookup"><span data-stu-id="a2447-213">Shortcuts</span></span>

| <span data-ttu-id="a2447-214">操作</span><span class="sxs-lookup"><span data-stu-id="a2447-214">Action</span></span>                         | <span data-ttu-id="a2447-215">キー</span><span class="sxs-lookup"><span data-stu-id="a2447-215">Shortcut</span></span>     |
|:-------------------------------|:-------------|
| <span data-ttu-id="a2447-216">プロファイリングセッションの開始/停止</span><span class="sxs-lookup"><span data-stu-id="a2447-216">Start / Stop profiling session</span></span> | `Ctrl` + `E` |
| <span data-ttu-id="a2447-217">HAR としてエクスポート</span><span class="sxs-lookup"><span data-stu-id="a2447-217">Export as HAR</span></span>                  | `Ctrl` + `S` |
| <span data-ttu-id="a2447-218">検索</span><span class="sxs-lookup"><span data-stu-id="a2447-218">Find</span></span>                           | `Ctrl` + `F` |
| <span data-ttu-id="a2447-219">コピー</span><span class="sxs-lookup"><span data-stu-id="a2447-219">Copy</span></span>                           | `Ctrl` + `C` |

## <span data-ttu-id="a2447-220">既知の問題</span><span class="sxs-lookup"><span data-stu-id="a2447-220">Known Issues</span></span>

### <span data-ttu-id="a2447-221">ネットワークコレクションエージェントを起動できませんでした。</span><span class="sxs-lookup"><span data-stu-id="a2447-221">The network collection agent failed to start.</span></span>

<span data-ttu-id="a2447-222">このエラーメッセージが表示される場合: ネットワーク**収集エージェントがネットワークツールで起動できなかっ**た場合は、次の手順に従って回避策を実行します。</span><span class="sxs-lookup"><span data-stu-id="a2447-222">If you see this error message: **The network collection agent failed to start** in the Network tool, follow these steps for a workaround.</span></span>

1. <span data-ttu-id="a2447-223">キーを押し `Windows Key`  +  `R` ます。</span><span class="sxs-lookup"><span data-stu-id="a2447-223">Press `Windows Key` + `R`.</span></span>

2. <span data-ttu-id="a2447-224">[実行] ダイアログボックスで、「 **services.msc**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="a2447-224">In the Run dialog, enter **services.msc**.</span></span>
![既知の問題-1](./media/known_issues_1.PNG)

3. <span data-ttu-id="a2447-226">**Microsoft (R) Diagnostics Hub Standard コレクタサービス**を探して右クリックします。</span><span class="sxs-lookup"><span data-stu-id="a2447-226">Locate the **Microsoft (R) Diagnostics Hub Standard Collector Service** and right-click it.</span></span>
![既知の問題-2](./media/known_issues_2.PNG)

4. <span data-ttu-id="a2447-228">**Microsoft (R) Diagnostics Hub Standard コレクタサービス**を再起動します。</span><span class="sxs-lookup"><span data-stu-id="a2447-228">Restart the **Microsoft (R) Diagnostics Hub Standard Collector Service**.</span></span>
![既知の問題-3](./media/known_issues_3.PNG)

5. <span data-ttu-id="a2447-230">Microsoft Edge 開発者ツールとタブを閉じます。新しいタブを開き、目的のページに移動して、キーを押し `F12` ます。</span><span class="sxs-lookup"><span data-stu-id="a2447-230">Close the Microsoft Edge Developer Tools and the tab. Open a new tab, navigate to your page, and press `F12`.</span></span>

6. <span data-ttu-id="a2447-231">[**ネットワーク**] の横に再生バッジと web ページのネットワーク要求が表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="a2447-231">You should now see a Play badge next to **Network** and the network requests for your webpage.</span></span>
![既知の問題-4](./media/known_issues_4-network.PNG)

<span data-ttu-id="a2447-233">まだ問題が発生していますか?</span><span class="sxs-lookup"><span data-stu-id="a2447-233">Still running into problems?</span></span> <span data-ttu-id="a2447-234">フィードバックの**送信**アイコンを使ってフィードバックをお送りください。</span><span class="sxs-lookup"><span data-stu-id="a2447-234">Please send us your feedback using the **Send feedback** icon!</span></span> 

![既知の問題-5](./media/known_issues_5.PNG)

### <span data-ttu-id="a2447-236">ネットワークコレクションエージェントを停止できませんでした。</span><span class="sxs-lookup"><span data-stu-id="a2447-236">The network collection agent failed to stop.</span></span>

<span data-ttu-id="a2447-237">このエラーメッセージが表示される場合は、ネットワークツールで**ネットワークコレクションエージェントを停止できませんでし**た。回避策については、次の手順を実行してください。</span><span class="sxs-lookup"><span data-stu-id="a2447-237">If you see this error message: **The network collection agent failed to stop** in the Network tool, follow these steps for a workaround.</span></span>

1. <span data-ttu-id="a2447-238">キーを押し `Windows Key`  +  `R` ます。</span><span class="sxs-lookup"><span data-stu-id="a2447-238">Press `Windows Key` + `R`.</span></span>

2. <span data-ttu-id="a2447-239">[実行] ダイアログボックスで、「 **services.msc**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="a2447-239">In the Run dialog, enter **services.msc**.</span></span>
![既知の問題-1](./media/known_issues_1.PNG)

3. <span data-ttu-id="a2447-241">**Microsoft (R) Diagnostics Hub Standard コレクタサービス**を探して右クリックします。</span><span class="sxs-lookup"><span data-stu-id="a2447-241">Locate the **Microsoft (R) Diagnostics Hub Standard Collector Service** and right-click it.</span></span>
![既知の問題-2](./media/known_issues_2.PNG)

4. <span data-ttu-id="a2447-243">**Microsoft (R) Diagnostics Hub Standard コレクタサービス**を再起動します。</span><span class="sxs-lookup"><span data-stu-id="a2447-243">Restart the **Microsoft (R) Diagnostics Hub Standard Collector Service**.</span></span>
![既知の問題-3](./media/known_issues_3.PNG)

5. <span data-ttu-id="a2447-245">Microsoft Edge 開発者ツールとタブを閉じます。新しいタブを開き、目的のページに移動して、キーを押し `F12` ます。</span><span class="sxs-lookup"><span data-stu-id="a2447-245">Close the Microsoft Edge Developer Tools and the tab. Open a new tab, navigate to your page, and press `F12`.</span></span>

6. <span data-ttu-id="a2447-246">[**ネットワーク**] の横に再生バッジと web ページのネットワーク要求が表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="a2447-246">You should now see a Play badge next to **Network** and the network requests for your webpage.</span></span>
![既知の問題-4](./media/known_issues_4-network.PNG)

<span data-ttu-id="a2447-248">まだ問題が発生していますか?</span><span class="sxs-lookup"><span data-stu-id="a2447-248">Still running into problems?</span></span> <span data-ttu-id="a2447-249">フィードバックの**送信**アイコンを使ってフィードバックをお送りください。</span><span class="sxs-lookup"><span data-stu-id="a2447-249">Please send us your feedback using the **Send feedback** icon!</span></span> 

![既知の問題-5](./media/known_issues_5.PNG)
