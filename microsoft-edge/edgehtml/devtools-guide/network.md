---
description: ネットワーク パネルを使用してページ リソース要求を監視およびプロファイルする
title: DevTools - Network
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, ネットワーク, 読み込み時間, http, https, ブラウザー キャッシュ, HAR
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 261226c7210d978f11290816c81355bb0142dee9
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234820"
---
# <span data-ttu-id="87f81-104">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="87f81-104">Network</span></span>

<span data-ttu-id="87f81-105">ネットワーク パネル **を使用** して、ネットワークを使用して送信された要求と応答を監視、検査、プロファイルします。</span><span class="sxs-lookup"><span data-stu-id="87f81-105">Use the **Network** panel to monitor, inspect and profile the requests and responses sent over the wire.</span></span> <span data-ttu-id="87f81-106">この方法を使用すると、次の方法を行います。</span><span class="sxs-lookup"><span data-stu-id="87f81-106">With it, you can:</span></span>

 - <span data-ttu-id="87f81-107">[ページによって行われたすべてのリソース要求の](#network-summary) レコードを参照する</span><span class="sxs-lookup"><span data-stu-id="87f81-107">[Browse a record of all the resource requests](#network-summary) made by the page</span></span>
 - <span data-ttu-id="87f81-108">[新規ユーザーと復帰ユーザーに対するサイト](#summary-bar) の読み込み時間を測定する</span><span class="sxs-lookup"><span data-stu-id="87f81-108">[Measure the load time of your site](#summary-bar) for new and returning users</span></span> 
 - <span data-ttu-id="87f81-109">[ページとネットワークの間で](#request-details) 交換されるヘッダー、メッセージのボディ、パラメーター、Cookie を検査する</span><span class="sxs-lookup"><span data-stu-id="87f81-109">[Inspect the headers, message bodies, parameters, and cookies](#request-details) exchanged between your page and the network</span></span>
 - <span data-ttu-id="87f81-110">[サイトの読み込み時間でボトルネックの](#timings) 原因となっているネットワーク イベントを特定する</span><span class="sxs-lookup"><span data-stu-id="87f81-110">[Identify the network events causing bottlenecks](#timings) in the load time of your site</span></span>

![Microsoft Edge DevTools ネットワーク パネル](./media/network.png)

## <span data-ttu-id="87f81-112">ネットワークの概要</span><span class="sxs-lookup"><span data-stu-id="87f81-112">Network summary</span></span>

<span data-ttu-id="87f81-113">DevTools を開いた場合、ネットワーク プロファイリングは既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="87f81-113">When you open  DevTools, network profiling is turned on by default.</span></span> <span data-ttu-id="87f81-114">Active Browser タブからのすべてのネットワーク トラフィックは、Network とは異なる DevTools パネルで作業している間でも、ネットワークの概要リストに記録 *されます*。</span><span class="sxs-lookup"><span data-stu-id="87f81-114">All the network traffic from your active browser tab is recorded in the network summary list, even while you are working in a different  DevTools panel than *Network*.</span></span>

![進行中のネットワーク プロファイリング インジケーター](./media/network_profile_indicator.png)

### <span data-ttu-id="87f81-116">ツール バー</span><span class="sxs-lookup"><span data-stu-id="87f81-116">Toolbar</span></span>

<span data-ttu-id="87f81-117">ツール バーには、ページのネットワーク アクティビティをプロファイリングおよびフィルター処理するコントロールがあります。</span><span class="sxs-lookup"><span data-stu-id="87f81-117">The toolbar provides controls for profiling and filtering the network activity of your page.</span></span> 

![ネットワーク プロファイラー ツール バー](./media/network_toolbar.png)

1. <span data-ttu-id="87f81-119">**プロファイリング セッションの開始/** 停止 : 既定では、ネットワーク プロファイリングが有効になっていて、ネットワーク トラフィックがネットワーク プロファイラーの一 [**覧に記録**](#network-request-list) されます。</span><span class="sxs-lookup"><span data-stu-id="87f81-119">**Start / Stop profiling session**: By default, network profiling is turned on, and network traffic will be logged in the [**Network profiler**](#network-request-list) list.</span></span> <span data-ttu-id="87f81-120">[停止 ( ) ] ボタンを使用してネットワーク **キャプチャ** `Ctrl+E` をオフにできます。</span><span class="sxs-lookup"><span data-stu-id="87f81-120">You can turn off network capture with the **Stop** (`Ctrl+E`) button.</span></span>

2. <span data-ttu-id="87f81-121">**HAR としてエクスポート**: 現在のネットワーク プロファイリング セッション ( ) を JSON 形式の `Ctrl+S` HTTP アーカイブ [(HAR)](https://dvcs.w3.org/hg/webperf/raw-file/tip/specs/HAR/Overview.html) ファイルとして保存できます。</span><span class="sxs-lookup"><span data-stu-id="87f81-121">**Export as HAR**: You can save the current network profiling session (`Ctrl+S`) as a JSON-formatted [HTTP Archive (HAR)](https://dvcs.w3.org/hg/webperf/raw-file/tip/specs/HAR/Overview.html) file.</span></span> 

3. <span data-ttu-id="87f81-122">**コンテンツ タイプ フィルター**: 特定のコンテンツ要求 (ドキュメント、スタイル シート、*イメージ、スクリプト、メディア、フォント、XHR、その*他) でネットワーク要求リストをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="87f81-122">**Content type filter**: Filter the network request list by specific content requests (*Documents, Style sheets, Images, Scripts, Media, Fonts, XHR, Other*).</span></span> <span data-ttu-id="87f81-123">既定では、すべてのコンテンツ タイプが表示されます。</span><span class="sxs-lookup"><span data-stu-id="87f81-123">By default all content types are shown.</span></span>

4. <span data-ttu-id="87f81-124">**Find**: Filter ( `Ctrl+F` ) the network request list by entry names (resource paths) containing a specified search string.</span><span class="sxs-lookup"><span data-stu-id="87f81-124">**Find**: Filter (`Ctrl+F`) the network request list by entry names (resource paths) containing a specified search string.</span></span>

5. <span data-ttu-id="87f81-125">**常にサーバーから更新**: このボタンを押すと、ページ リソースがブラウザー キャッシュではなくネットワークから読み込まれる状態になります。</span><span class="sxs-lookup"><span data-stu-id="87f81-125">**Always refresh from server**: Depressing this button will force page resources to load from the network rather than the browser cache.</span></span> <span data-ttu-id="87f81-126">You can refresh the page from network a single time by pressing `Ctrl+F5` .</span><span class="sxs-lookup"><span data-stu-id="87f81-126">You can refresh the page from  network a single time by pressing `Ctrl+F5`.</span></span>

6. <span data-ttu-id="87f81-127">**すべてのネットワーク要求にサービス ワーカーをバイパス**する : 登録済みのサービス ワーカーをネットワーク プロキシとして無効にします。</span><span class="sxs-lookup"><span data-stu-id="87f81-127">**Bypass Service Worker for all network requests**: Disable your registered service workers as network proxies.</span></span> 

7. <span data-ttu-id="87f81-128">ボタンをクリアする</span><span class="sxs-lookup"><span data-stu-id="87f81-128">Clear buttons</span></span>

   - <span data-ttu-id="87f81-129">**キャッシュの**クリア: ブラウザー キャッシュに格納されているリソースをすべて削除します (また、ページの読み込みを初めて実行するエクスペリエンスをエミュレートします)。</span><span class="sxs-lookup"><span data-stu-id="87f81-129">**Clear cache**: Removes all resources stored in the browser cache (and emulates a first-time experience loading the page).</span></span>
   - <span data-ttu-id="87f81-130">**Cookie の**クリア : 特定のドメインのすべての Cookie を削除します (また、サイトの初回エクスペリエンスをエミュレートします)。</span><span class="sxs-lookup"><span data-stu-id="87f81-130">**Clear cookies**: Removes all cookies for the given domain (and emulates a first-time experience of the site).</span></span>
   - <span data-ttu-id="87f81-131">**移動時にエントリをクリア**する : 記録されたトラフィックは、ページ ナビゲーション時にクリアされます。</span><span class="sxs-lookup"><span data-stu-id="87f81-131">**Clear entries on navigate**: Recorded traffic is cleared upon page navigation.</span></span> <span data-ttu-id="87f81-132">これは既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="87f81-132">This is turned on by default.</span></span>
   - <span data-ttu-id="87f81-133">**セッションの**クリア: ネットワークの概要リストからすべてのネットワーク要求 **エントリをクリア** します。</span><span class="sxs-lookup"><span data-stu-id="87f81-133">**Clear session**: Clears all network request entries from the **Network summary** list.</span></span>

### <span data-ttu-id="87f81-134">ネットワーク要求リスト</span><span class="sxs-lookup"><span data-stu-id="87f81-134">Network request list</span></span>

<span data-ttu-id="87f81-135">すべてのネットワーク トラフィックが一覧に記録されます (ナビゲーション時にクリアするか、手動でクリアするか、DevTools を閉じます)。</span><span class="sxs-lookup"><span data-stu-id="87f81-135">All network traffic is recorded to a list (until cleared upon navigation, manually cleared, or  DevTools are closed).</span></span> <span data-ttu-id="87f81-136">任意のエントリをクリックすると、要求のより [詳細なビューが開きます](#request-details)。</span><span class="sxs-lookup"><span data-stu-id="87f81-136">Clicking on any entry will open a more [detailed view of the request](#request-details).</span></span>

![ネットワーク要求リスト](./media/network_request_list.png)

<span data-ttu-id="87f81-138">ネットワーク要求リストには、次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="87f81-138">The network request list includes the following info:</span></span> 

<span data-ttu-id="87f81-139">列</span><span class="sxs-lookup"><span data-stu-id="87f81-139">Column</span></span> | <span data-ttu-id="87f81-140">説明</span><span class="sxs-lookup"><span data-stu-id="87f81-140">Description</span></span> 
:------------ | :------------- 
**<span data-ttu-id="87f81-141">Name (名前)</span><span class="sxs-lookup"><span data-stu-id="87f81-141">Name</span></span>** | <span data-ttu-id="87f81-142">要求の名前と URL パス</span><span class="sxs-lookup"><span data-stu-id="87f81-142">Name and URL path of the request</span></span>
**<span data-ttu-id="87f81-143">プロトコル</span><span class="sxs-lookup"><span data-stu-id="87f81-143">Protocol</span></span>** |  <span data-ttu-id="87f81-144">要求のプロトコルの種類 *(HTTPS、HTTP/2 など*)</span><span class="sxs-lookup"><span data-stu-id="87f81-144">Type of protocol for the request (such as *HTTPS, HTTP/2*)</span></span>
**<span data-ttu-id="87f81-145">メソッド</span><span class="sxs-lookup"><span data-stu-id="87f81-145">Method</span></span>** |    <span data-ttu-id="87f81-146">[要求に](https://developer.mozilla.org/docs/Web/HTTP/Methods) 使用される HTTP メソッド</span><span class="sxs-lookup"><span data-stu-id="87f81-146">[HTTP method](https://developer.mozilla.org/docs/Web/HTTP/Methods) used for the request</span></span>
**<span data-ttu-id="87f81-147">結果</span><span class="sxs-lookup"><span data-stu-id="87f81-147">Result</span></span>** |    <span data-ttu-id="87f81-148">[HTTP 応答状態](https://developer.mozilla.org/docs/Web/HTTP/Status)  コード</span><span class="sxs-lookup"><span data-stu-id="87f81-148">[HTTP response status](https://developer.mozilla.org/docs/Web/HTTP/Status)  code</span></span>
**<span data-ttu-id="87f81-149">コンテンツ タイプ</span><span class="sxs-lookup"><span data-stu-id="87f81-149">Content type</span></span>** |  <span data-ttu-id="87f81-150">要求されたメディアの種類[(MIME タイプ](https://en.wikipedia.org/wiki/Media_type))</span><span class="sxs-lookup"><span data-stu-id="87f81-150">Type of media requested ([MIME type](https://en.wikipedia.org/wiki/Media_type))</span></span>
**<span data-ttu-id="87f81-151">受信</span><span class="sxs-lookup"><span data-stu-id="87f81-151">Received</span></span>** | <span data-ttu-id="87f81-152">サーバーによって配信される応答のサイズ (キャッシュされた応答では計算されません)</span><span class="sxs-lookup"><span data-stu-id="87f81-152">Size of the response as delivered by the server (not calculated for cached responses)</span></span>
**<span data-ttu-id="87f81-153">時間</span><span class="sxs-lookup"><span data-stu-id="87f81-153">Time</span></span>** |  <span data-ttu-id="87f81-154">サーバー応答を読み込む時間 (キャッシュされた応答では計算されません)</span><span class="sxs-lookup"><span data-stu-id="87f81-154">Time to load the server response (not calculated for cached responses)</span></span>
**<span data-ttu-id="87f81-155">Initiator</span><span class="sxs-lookup"><span data-stu-id="87f81-155">Initiator</span></span>** | <span data-ttu-id="87f81-156">要求を開始するサブシステム ( *パーサー、リダイレクト、スクリプト、その*他など)</span><span class="sxs-lookup"><span data-stu-id="87f81-156">Subsystem responsible for initiating the request (such as *Parser, Redirect, Script, Other*)</span></span>
**<span data-ttu-id="87f81-157">タイムライン</span><span class="sxs-lookup"><span data-stu-id="87f81-157">Timeline</span></span>** | <span data-ttu-id="87f81-158">要求のネットワーク イベント *(Stalled、Resolving(DNS)、Connecting(TCP)、SSL、Sending、Waiting(TTFB)、Downloading*など) の視覚的なタイムライン。</span><span class="sxs-lookup"><span data-stu-id="87f81-158">Visual timeline for the network events of the request (such as *Stalled, Resolving(DNS), Connecting(TCP), SSL, Sending, Waiting(TTFB), Downloading*).</span></span> <span data-ttu-id="87f81-159">グラフにカーソルを合わせると、ネットワーク ネットワークのタイミングの詳細 [が表示されます](#timings)。</span><span class="sxs-lookup"><span data-stu-id="87f81-159">Hovering over the chart provides the more granular breakdown of network [network timings](#timings)).</span></span>

### <span data-ttu-id="87f81-160">概要バー</span><span class="sxs-lookup"><span data-stu-id="87f81-160">Summary bar</span></span>

<span data-ttu-id="87f81-161">ネットワーク パネルの下部にある\*\*\*\* バーには、ネットワーク プロファイリング セッション中の HTTP ネットワーク エラー、要求、データ転送、および読み込み時間の合計が要約されます (DevTools が開いてネットワーク トラフィックを記録した後)。</span><span class="sxs-lookup"><span data-stu-id="87f81-161">The bar at the bottom of **Network** panel summarizes the total number of HTTP network errors, requests, data transfered, and load times during the network profiling session (i.e., since  DevTools were opened and recording network traffic).</span></span>

![ネットワークの概要バー](./media/network_summary_bar.png)

<span data-ttu-id="87f81-163">**経過時間とは** 、プロファイリング セッションの開始から最後のリソースがネットワークからダウンロードされた時刻の間の時間を意味します。</span><span class="sxs-lookup"><span data-stu-id="87f81-163">**Elapsed time** means the time between the start of the profiling session and when the last resource was downloaded from the network.</span></span> <span data-ttu-id="87f81-164">ブラウザー キャッシュからフェッチされたリソースは、この数に時間が発生しない。</span><span class="sxs-lookup"><span data-stu-id="87f81-164">Resources fetched from the browser cache do not accrue time to this number.</span></span> 

<span data-ttu-id="87f81-165">**DOM** の読み込み時間とは、プロファイリング セッションの開始から [DOMContentLoaded](https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded) イベントが発生して、ページ ドキュメントの構造が読み込まれ、解析された (必ずしもスタイルシート、イメージ、またはサブフレームではない) かどうかを示す時間を意味します。</span><span class="sxs-lookup"><span data-stu-id="87f81-165">**DOM load time** means the time between the start of the profiling session and when the [DOMContentLoaded](https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded) event was fired to indicate that the structure of the page document has been loaded and parsed (though not necessarily any stylesheets, images or subframes).</span></span>

<span data-ttu-id="87f81-166">**ページ読み**込み時間とは、プロファイリング セッションの開始から、ページ ドキュメント[](https://developer.mozilla.org/docs/Web/Events/load)(およびすべてのリソース) が完全に読み込まれたと示す load イベントが発生した時刻の間の時間を意味します。</span><span class="sxs-lookup"><span data-stu-id="87f81-166">**Page load time** time means the time between the start of the profiling session and when the [load](https://developer.mozilla.org/docs/Web/Events/load) event was fired to indicate that the page document (and all its resources) has been fully loaded.</span></span>

## <span data-ttu-id="87f81-167">要求の詳細</span><span class="sxs-lookup"><span data-stu-id="87f81-167">Request details</span></span>

<span data-ttu-id="87f81-168">[ネットワークの概要] ボックス[\*\*\*\*](#network-summary)の一覧のエントリをクリック[\*\*\*\*](#request-details)すると、[要求の詳細] ウィンドウが開き、次の各タブに詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="87f81-168">Clicking on any entry in the [**Network summary**](#network-summary) list will open the [**Request details**](#request-details) pane with further information in each of the following tabs.</span></span>

![ネットワーク要求の詳細ウィンドウ](./media/network_request_details.png)

### <span data-ttu-id="87f81-170">ヘッダー</span><span class="sxs-lookup"><span data-stu-id="87f81-170">Headers</span></span>
<span data-ttu-id="87f81-171">サーバーに [送信およびサーバー](https://developer.mozilla.org/docs/Web/HTTP/Headers) から受信した HTTP ヘッダーを表示します。</span><span class="sxs-lookup"><span data-stu-id="87f81-171">Displays the [HTTP headers](https://developer.mozilla.org/docs/Web/HTTP/Headers) sent to and received from the server.</span></span> <span data-ttu-id="87f81-172">任意のヘッダー エントリを右クリックして、クリップボードにコピー `Ctrl+C` します。</span><span class="sxs-lookup"><span data-stu-id="87f81-172">Right-click on any header entry to copy it (`Ctrl+C`) to the clipboard.</span></span> <span data-ttu-id="87f81-173">キーを押しながらエントリを複数選択したり、すべて () `Shift` を選択したりもできます `Ctrl+A` 。</span><span class="sxs-lookup"><span data-stu-id="87f81-173">You can also multi-select entries by holding down the `Shift` key or select all (`Ctrl+A`).</span></span>

### <span data-ttu-id="87f81-174">本文</span><span class="sxs-lookup"><span data-stu-id="87f81-174">Body</span></span>
<span data-ttu-id="87f81-175">要求と応答のペイロードの本文データ (使用可能な場合) を表示します。</span><span class="sxs-lookup"><span data-stu-id="87f81-175">Displays the body data (if available) of the request and response payloads.</span></span>

<span data-ttu-id="87f81-176">画像コンテンツは、サイズとサイズのデータと一緒に表示されます。</span><span class="sxs-lookup"><span data-stu-id="87f81-176">Image content is displayed with dimensions and size data.</span></span>

<span data-ttu-id="87f81-177">テキスト コンテンツは (読み取り専用) エディターに表示され、読み\*\*\*\* やすくするために、プレビュー印刷や**Word**の折り返しを使用して、最小化されたコンテンツを書式設定するためのオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="87f81-177">Text content appears in a (read-only) editor with options to format minified content with **Pretty print** and/or **Word wrap** for easier readability.</span></span>

![[要求の詳細] ウィンドウの [本文] タブ](./media/network_details_body.png)

### <span data-ttu-id="87f81-179">パラメーター</span><span class="sxs-lookup"><span data-stu-id="87f81-179">Parameters</span></span>
<span data-ttu-id="87f81-180">GET 要求のクエリ文字列パラメーターを表示します。</span><span class="sxs-lookup"><span data-stu-id="87f81-180">Displays query string parameters for GET requests.</span></span> <span data-ttu-id="87f81-181">POST 要求のパラメーターはヘッダーで送信されるが、GET 要求はそれらを URL に含める。</span><span class="sxs-lookup"><span data-stu-id="87f81-181">While the parameters of POST requests are sent in the headers, GET requests include them in the URL.</span></span> <span data-ttu-id="87f81-182">読みやすくするために、この記事で取り上がっています。</span><span class="sxs-lookup"><span data-stu-id="87f81-182">They're broken out here for easier reading.</span></span>

<span data-ttu-id="87f81-183">任意の行を右クリックして、クリップボードにコピー `Ctrl+C` ( ) します。</span><span class="sxs-lookup"><span data-stu-id="87f81-183">Right-click on any row to copy it (`Ctrl+C`) to the clipboard.</span></span> <span data-ttu-id="87f81-184">キーを押しながらエントリを複数選択したり、すべて () `Shift` を選択したりもできます `Ctrl+A` 。</span><span class="sxs-lookup"><span data-stu-id="87f81-184">You can also multi-select entries by holding down the `Shift` key or select all (`Ctrl+A`).</span></span>

### <span data-ttu-id="87f81-185">Cookie</span><span class="sxs-lookup"><span data-stu-id="87f81-185">Cookies</span></span>
<span data-ttu-id="87f81-186">キーと値のペアとして送信または受信される Cookie を表示します。</span><span class="sxs-lookup"><span data-stu-id="87f81-186">Displays cookies that are sent or received as key/value pairs.</span></span>

<span data-ttu-id="87f81-187">任意の行を右クリックして、クリップボードにコピー `Ctrl+C` ( ) します。</span><span class="sxs-lookup"><span data-stu-id="87f81-187">Right-click on any row to copy it (`Ctrl+C`) to the clipboard.</span></span> <span data-ttu-id="87f81-188">キーを押しながらエントリを複数選択したり、すべて () `Shift` を選択したりもできます `Ctrl+A` 。</span><span class="sxs-lookup"><span data-stu-id="87f81-188">You can also multi-select entries by holding down the `Shift` key or select all (`Ctrl+A`).</span></span>

<span data-ttu-id="87f81-189">特定のドメインに保存されている Cookie は、ツール[](#network-summary)バー ([Cookie のクリア] ボタン)**から消去**できます。</span><span class="sxs-lookup"><span data-stu-id="87f81-189">You can clear the stored cookies for the given domain from the [Toolbar](#network-summary) (**Clear cookies** button).</span></span> 

### <span data-ttu-id="87f81-190">タイミング</span><span class="sxs-lookup"><span data-stu-id="87f81-190">Timings</span></span>

<span data-ttu-id="87f81-191">[ **タイミング] タブ** には、選択したリソースの読み込みに関係するネットワーク イベントのタイムラインが表示されます。</span><span class="sxs-lookup"><span data-stu-id="87f81-191">The **Timings** tab provides a timeline of network events involved in the loading of the selected resource.</span></span> <span data-ttu-id="87f81-192">これは、ネットワーク要求リストの *[タイムライン*] 列にある[](#network-request-list)情報に似ていますが、要求キューでの待機に費やされた時間 (*ス*トール) や DNS 解決、TCP 接続の確立など、ネットワークを通じて送信される要求に至るイベントも含まれます。</span><span class="sxs-lookup"><span data-stu-id="87f81-192">This is similar to the information found in the *Timeline* column of the [Network request list](#network-request-list), but also includes the events leading up to the request being sent over the wire, such as time spent waiting (*Stalled*) in the request queue, DNS resolution, and establishing the TCP connection.</span></span> 

![[要求の詳細] ウィンドウの [タイミング] タブ](./media/network_details_timings.png)

<span data-ttu-id="87f81-194">他のリソースとの間のリダイレクトが表示され、リンクをクリックすると、ネットワーク要求の詳細ウィンドウ内のそのリソース [にフォーカスが設定](#request details) されます。</span><span class="sxs-lookup"><span data-stu-id="87f81-194">Redirections to/from other resources are noted, and clicking on the link will set focus to that resource in the network [request details](#request details) pane.</span></span>

<span data-ttu-id="87f81-195">キャッシュから読み込まれたリソースはネットワーク待機時間の影響を受けないので、ネットワーク *タイミング* チャートは表示されません。</span><span class="sxs-lookup"><span data-stu-id="87f81-195">Resouces loaded from the cache are not affected by network latency, so no network *Timings* chart will display.</span></span>

![キャッシュから読み込まれたリダイレクトされたリソース](./media/network_details_timings_cache_redirect.png)

<span data-ttu-id="87f81-197">特定のリソースに対して発生する可能性があるさまざまなネットワーク イベントを、時系列順に次に示します。</span><span class="sxs-lookup"><span data-stu-id="87f81-197">Here are the different network events you might see for a given resource, in chronological order:</span></span>

#### <span data-ttu-id="87f81-198">ストール</span><span class="sxs-lookup"><span data-stu-id="87f81-198">Stalled</span></span>

<span data-ttu-id="87f81-199">要求キューで利用可能なネットワーク接続を待機する時間。</span><span class="sxs-lookup"><span data-stu-id="87f81-199">Time spent waiting for an available network connection in the request queue.</span></span> <span data-ttu-id="87f81-200">HTTP 1.0/1.1 の場合、Microsoft Edge はホスト名ごとに最大 6 つの同時 TCP 接続を許可します。</span><span class="sxs-lookup"><span data-stu-id="87f81-200">For HTTP 1.0/1.1, Microsoft Edge allows a maximum of six (6) simultaneous TCP connections per hostname.</span></span> 

#### <span data-ttu-id="87f81-201">解決 (DNS)</span><span class="sxs-lookup"><span data-stu-id="87f81-201">Resolving (DNS)</span></span>

<span data-ttu-id="87f81-202">DNS (ドメイン ネーム システム) 内のリソースのホスト名の IP アドレスの検索に費やされた[時間](https://en.wikipedia.org/wiki/Domain_Name_System)。</span><span class="sxs-lookup"><span data-stu-id="87f81-202">Time spent looking up the IP address for the hostname of the resource in the DNS ([Domain Name System](https://en.wikipedia.org/wiki/Domain_Name_System)).</span></span>

#### <span data-ttu-id="87f81-203">接続 (TCP)</span><span class="sxs-lookup"><span data-stu-id="87f81-203">Connecting (TCP)</span></span>

<span data-ttu-id="87f81-204">TCP (伝送制御プロトコル) 接続の確立[に費](https://en.wikipedia.org/wiki/Transmission_Control_Protocol)やされた時間。</span><span class="sxs-lookup"><span data-stu-id="87f81-204">Time spent establishing the TCP ([Transmission Control Protocol](https://en.wikipedia.org/wiki/Transmission_Control_Protocol)) connection.</span></span>

#### <span data-ttu-id="87f81-205">SSL</span><span class="sxs-lookup"><span data-stu-id="87f81-205">SSL</span></span>

<span data-ttu-id="87f81-206">ホストのプロキシ サーバーとの SSL[(Secure Sockets Layer)](https://en.wikipedia.org/wiki/Transport_Layer_Security)接続のネゴ [シエート](https://en.wikipedia.org/wiki/Proxy_server) に費やされた時間。</span><span class="sxs-lookup"><span data-stu-id="87f81-206">Time spent negotiating a SSL ([Secure Sockets Layer](https://en.wikipedia.org/wiki/Transport_Layer_Security))  connection with the [proxy server](https://en.wikipedia.org/wiki/Proxy_server) for the host.</span></span>

#### <span data-ttu-id="87f81-207">送信</span><span class="sxs-lookup"><span data-stu-id="87f81-207">Sending</span></span>

<span data-ttu-id="87f81-208">リソース要求の送信に費やされた時間。</span><span class="sxs-lookup"><span data-stu-id="87f81-208">Time spent sending the resource request.</span></span>

#### <span data-ttu-id="87f81-209">Waiting (TTFB)</span><span class="sxs-lookup"><span data-stu-id="87f81-209">Waiting (TTFB)</span></span>

<span data-ttu-id="87f81-210">ホスト サーバーからの応答の最初のバイト ("time to first byte"、または *TTFB)* を待機するために費やされた時間。</span><span class="sxs-lookup"><span data-stu-id="87f81-210">Time spent waiting for the first byte of the response from the host server ("time to first byte", or *TTFB*).</span></span>

#### <span data-ttu-id="87f81-211">ダウンロード</span><span class="sxs-lookup"><span data-stu-id="87f81-211">Downloading</span></span>

<span data-ttu-id="87f81-212">サーバーからの応答の読み取りに費やされた時間。</span><span class="sxs-lookup"><span data-stu-id="87f81-212">Time spent reading the response from the server.</span></span>

## <span data-ttu-id="87f81-213">ショートカット</span><span class="sxs-lookup"><span data-stu-id="87f81-213">Shortcuts</span></span>

| <span data-ttu-id="87f81-214">操作</span><span class="sxs-lookup"><span data-stu-id="87f81-214">Action</span></span>                         | <span data-ttu-id="87f81-215">ショートカット</span><span class="sxs-lookup"><span data-stu-id="87f81-215">Shortcut</span></span>     |
|:-------------------------------|:-------------|
| <span data-ttu-id="87f81-216">プロファイリング セッションの開始/停止</span><span class="sxs-lookup"><span data-stu-id="87f81-216">Start / Stop profiling session</span></span> | `Ctrl` + `E` |
| <span data-ttu-id="87f81-217">HAR としてエクスポート</span><span class="sxs-lookup"><span data-stu-id="87f81-217">Export as HAR</span></span>                  | `Ctrl` + `S` |
| <span data-ttu-id="87f81-218">検索</span><span class="sxs-lookup"><span data-stu-id="87f81-218">Find</span></span>                           | `Ctrl` + `F` |
| <span data-ttu-id="87f81-219">コピー</span><span class="sxs-lookup"><span data-stu-id="87f81-219">Copy</span></span>                           | `Ctrl` + `C` |

## <span data-ttu-id="87f81-220">既知の問題</span><span class="sxs-lookup"><span data-stu-id="87f81-220">Known Issues</span></span>

### <span data-ttu-id="87f81-221">ネットワーク コレクション エージェントの開始に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="87f81-221">The network collection agent failed to start.</span></span>

<span data-ttu-id="87f81-222">このエラー メッセージが表示された場合: **ネットワーク コレクション** エージェントがネットワーク ツールで起動できなかった場合は、次の手順に従って回避策を確認してください。</span><span class="sxs-lookup"><span data-stu-id="87f81-222">If you see this error message: **The network collection agent failed to start** in the Network tool, follow these steps for a workaround.</span></span>

1. <span data-ttu-id="87f81-223">を押 `Windows Key`  +  `R` します。</span><span class="sxs-lookup"><span data-stu-id="87f81-223">Press `Windows Key` + `R`.</span></span>

2. <span data-ttu-id="87f81-224">[ファイル名を指定して実行] ダイアログボックスに **、「services.msc」と入力します**。</span><span class="sxs-lookup"><span data-stu-id="87f81-224">In the Run dialog, enter **services.msc**.</span></span>
![既知の問題-1](./media/known_issues_1.PNG)

3. <span data-ttu-id="87f81-226">Microsoft **(R) Diagnostics Hub Standard Collector Service** を見つけて右クリックします。</span><span class="sxs-lookup"><span data-stu-id="87f81-226">Locate the **Microsoft (R) Diagnostics Hub Standard Collector Service** and right-click it.</span></span>
![既知の問題-2](./media/known_issues_2.PNG)

4. <span data-ttu-id="87f81-228">Microsoft **(R) Diagnostics Hub Standard Collector Service を再起動します**。</span><span class="sxs-lookup"><span data-stu-id="87f81-228">Restart the **Microsoft (R) Diagnostics Hub Standard Collector Service**.</span></span>
![既知の問題- 3](./media/known_issues_3.PNG)

5. <span data-ttu-id="87f81-230">Microsoft Edge 開発者ツールとタブを閉じます。新しいタブを開き、ページに移動して、押します `F12` 。</span><span class="sxs-lookup"><span data-stu-id="87f81-230">Close the Microsoft Edge Developer Tools and the tab. Open a new tab, navigate to your page, and press `F12`.</span></span>

6. <span data-ttu-id="87f81-231">ネットワークと Web ページのネットワーク要求\*\*\*\* の横に再生バッジが表示されます。</span><span class="sxs-lookup"><span data-stu-id="87f81-231">You should now see a Play badge next to **Network** and the network requests for your webpage.</span></span>
![既知の問題- 4](./media/known_issues_4-network.PNG)

<span data-ttu-id="87f81-233">それでも問題が発生しますか?</span><span class="sxs-lookup"><span data-stu-id="87f81-233">Still running into problems?</span></span> <span data-ttu-id="87f81-234">フィードバックの送信アイコンを使用して、フィードバック **をお送り** ください。</span><span class="sxs-lookup"><span data-stu-id="87f81-234">Please send us your feedback using the **Send feedback** icon!</span></span> 

![既知の問題- 5](./media/known_issues_5.PNG)

### <span data-ttu-id="87f81-236">ネットワーク コレクション エージェントの停止に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="87f81-236">The network collection agent failed to stop.</span></span>

<span data-ttu-id="87f81-237">このエラー メッセージが表示された **場合:** ネットワーク コレクション エージェントがネットワーク ツールで停止できなかった場合は、次の手順に従って回避策を確認してください。</span><span class="sxs-lookup"><span data-stu-id="87f81-237">If you see this error message: **The network collection agent failed to stop** in the Network tool, follow these steps for a workaround.</span></span>

1. <span data-ttu-id="87f81-238">を押 `Windows Key`  +  `R` します。</span><span class="sxs-lookup"><span data-stu-id="87f81-238">Press `Windows Key` + `R`.</span></span>

2. <span data-ttu-id="87f81-239">[ファイル名を指定して実行] ダイアログボックスに **、「services.msc」と入力します**。</span><span class="sxs-lookup"><span data-stu-id="87f81-239">In the Run dialog, enter **services.msc**.</span></span>
![既知の問題-1](./media/known_issues_1.PNG)

3. <span data-ttu-id="87f81-241">Microsoft **(R) Diagnostics Hub Standard Collector Service** を見つけて右クリックします。</span><span class="sxs-lookup"><span data-stu-id="87f81-241">Locate the **Microsoft (R) Diagnostics Hub Standard Collector Service** and right-click it.</span></span>
![既知の問題-2](./media/known_issues_2.PNG)

4. <span data-ttu-id="87f81-243">Microsoft **(R) Diagnostics Hub Standard Collector Service を再起動します**。</span><span class="sxs-lookup"><span data-stu-id="87f81-243">Restart the **Microsoft (R) Diagnostics Hub Standard Collector Service**.</span></span>
![既知の問題- 3](./media/known_issues_3.PNG)

5. <span data-ttu-id="87f81-245">Microsoft Edge 開発者ツールとタブを閉じます。新しいタブを開き、ページに移動して、押します `F12` 。</span><span class="sxs-lookup"><span data-stu-id="87f81-245">Close the Microsoft Edge Developer Tools and the tab. Open a new tab, navigate to your page, and press `F12`.</span></span>

6. <span data-ttu-id="87f81-246">ネットワークと Web ページのネットワーク要求\*\*\*\* の横に再生バッジが表示されます。</span><span class="sxs-lookup"><span data-stu-id="87f81-246">You should now see a Play badge next to **Network** and the network requests for your webpage.</span></span>
![既知の問題- 4](./media/known_issues_4-network.PNG)

<span data-ttu-id="87f81-248">それでも問題が発生しますか?</span><span class="sxs-lookup"><span data-stu-id="87f81-248">Still running into problems?</span></span> <span data-ttu-id="87f81-249">フィードバックの送信アイコンを使用して、フィードバック **をお送り** ください。</span><span class="sxs-lookup"><span data-stu-id="87f81-249">Please send us your feedback using the **Send feedback** icon!</span></span> 

![既知の問題- 5](./media/known_issues_5.PNG)
