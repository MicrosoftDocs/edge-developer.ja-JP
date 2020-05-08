---
description: Microsoft Edge (EdgeHTML) 開発者ツールについて理解する
title: Microsoft Edge (EdgeHTML) 開発者ツール
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/05/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge、web 開発、f12 ツール、devtools
experimental: true
experiment_id: 51fe4b97-3e55-41
localization_priority: Priority
ms.openlocfilehash: 56edfa3aa39fc20d37d95fb8fde029a702732336
ms.sourcegitcommit: 985cfb79a64951afd5beb7981b26afbed30a8972
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "10629505"
---
# <span data-ttu-id="c759b-104">Microsoft Edge (EdgeHTML) 開発者ツール</span><span class="sxs-lookup"><span data-stu-id="c759b-104">Microsoft Edge (EdgeHTML) Developer Tools</span></span>  

[!INCLUDE [new-devtools-version-note](includes/new-devtools-version-note.md)]  

<span data-ttu-id="c759b-105">Microsoft Edge \ (EdgeHTML \) DevTools は、新しいフロントエンドワークフローに最適化された、[オープンソース][GithubMicrosoftChakracore]を使った[TypeScript][|::ref1::|Index]を使用して構築され、microsoft Store で[スタンドアロン Windows 10 アプリ][MicrosoftStoreEdgeDevtoolsPreview]として利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c759b-105">The Microsoft Edge \(EdgeHTML\) DevTools are built with [TypeScript][|::ref1::|Index], powered by [open source][GithubMicrosoftChakracore], optimized for modern front-end workflows, and now available as a [standalone Windows 10 app][MicrosoftStoreEdgeDevtoolsPreview] in the Microsoft Store!</span></span>  

<span data-ttu-id="c759b-106">最新機能の詳細については、「 [Windows 10 の最新の更新プログラム (EdgeHTML 18) での Devtools」][DevtoolsGuideEdgehtmlWhatsnew]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c759b-106">For more on the latest features, check out [DevTools in the latest update of Windows 10 (EdgeHTML 18)][DevtoolsGuideEdgehtmlWhatsnew].</span></span>  

## <span data-ttu-id="c759b-107">コアツール</span><span class="sxs-lookup"><span data-stu-id="c759b-107">Core tools</span></span>  

:::image type="complex" source="./devtools-guide/media/devtools.png" alt-text="Microsoft Edge (EdgeHTML) DevTools":::
   <span data-ttu-id="c759b-109">Microsoft Edge (EdgeHTML) DevTools</span><span class="sxs-lookup"><span data-stu-id="c759b-109">Microsoft Edge (EdgeHTML) DevTools</span></span>
:::image-end:::

<!--![Microsoft Edge \(EdgeHTML\) DevTools][ImageDevtoolsEdgehtml]  -->  

<span data-ttu-id="c759b-110">Microsoft Edge \ (EdgeHTML \) DevTools には以下のものがあります。</span><span class="sxs-lookup"><span data-stu-id="c759b-110">The Microsoft Edge \(EdgeHTML\) DevTools include:</span></span>  

*   <span data-ttu-id="c759b-111">HTML と CSS の編集、アクセシビリティプロパティの検査、イベントリスナーの表示、DOM 変異のブレークポイントの設定を行うための[要素][DevtoolsGuideEdgehtml|::ref2::|]パネル</span><span class="sxs-lookup"><span data-stu-id="c759b-111">An [Elements][DevtoolsGuideEdgehtml|::ref2::|] panel to edit HTML and CSS, inspect accessibility properties, view event listeners, and set DOM mutation breakpoints</span></span>  
*   <span data-ttu-id="c759b-112">ログメッセージを表示してフィルター処理し、JavaScript オブジェクトと DOM ノードを検査し、選択したウィンドウまたはフレームのコンテキストで JavaScript を実行する[本体][DevtoolsGuideEdgehtml|::ref3::|]</span><span class="sxs-lookup"><span data-stu-id="c759b-112">A [Console][DevtoolsGuideEdgehtml|::ref3::|] to view and filter log messages, inspect JavaScript objects and DOM nodes, and run JavaScript in the context of the selected window or frame</span></span>  
*   <span data-ttu-id="c759b-113">コードをステップ実行して、ウォッチとブレークポイントを設定し、コードをリアルタイムで編集し、web ストレージと cookie キャッシュを検査する[デバッガー][DevtoolsGuideEdgehtml|::ref4::|]</span><span class="sxs-lookup"><span data-stu-id="c759b-113">A [Debugger][DevtoolsGuideEdgehtml|::ref4::|] to step through code, set watches and breakpoints, live edit your code, and inspect your web storage and cookie caches</span></span>  
*   <span data-ttu-id="c759b-114">ネットワークとブラウザーのキャッシュから要求と応答を監視および検査するための[ネットワーク][DevtoolsGuideEdgehtml|::ref5::|]パネル</span><span class="sxs-lookup"><span data-stu-id="c759b-114">A [Network][DevtoolsGuideEdgehtml|::ref5::|] panel to monitor and inspect requests and responses from the network and browser cache</span></span>  
*   <span data-ttu-id="c759b-115">サイトで必要な時間とシステムリソースをプロファイルするための[パフォーマンス][DevtoolsGuideEdgehtml|::ref6::|]パネル</span><span class="sxs-lookup"><span data-stu-id="c759b-115">A [Performance][DevtoolsGuideEdgehtml|::ref6::|] panel to profile the time and system resources required by your site</span></span>  
*   <span data-ttu-id="c759b-116">メモリリソースの使用を測定し、コードランタイムのさまざまな状態でヒープスナップショットを比較するための[メモリ][DevtoolsGuideEdgehtml|::ref7::|]パネル</span><span class="sxs-lookup"><span data-stu-id="c759b-116">A [Memory][DevtoolsGuideEdgehtml|::ref7::|] panel to measure your use of memory resources and compare heap snapshots at different states of code runtime</span></span>  
*   <span data-ttu-id="c759b-117">Web ストレージ、IndexedDB、cookies、キャッシュデータを検査および管理するための[ストレージ][DevtoolsGuideEdgehtml|::ref8::|]パネル</span><span class="sxs-lookup"><span data-stu-id="c759b-117">A [Storage][DevtoolsGuideEdgehtml|::ref8::|] panel for inspecting and managing your web storage, IndexedDB, cookies and cache data</span></span>  
*   <span data-ttu-id="c759b-118">サービスワーカーを管理およびデバッグするための[サービスワーカー][DevtoolsGuideEdgehtmlServiceworkers]パネル</span><span class="sxs-lookup"><span data-stu-id="c759b-118">A [Service Workers][DevtoolsGuideEdgehtmlServiceworkers] panel for managing and debugging your service workers</span></span>  
*   <span data-ttu-id="c759b-119">さまざまなブラウザープロファイル、画面解像度、GPS 位置座標を使ってサイトをテストする[エミュレーション][DevtoolsGuideEdgehtml|::ref9::|]パネル</span><span class="sxs-lookup"><span data-stu-id="c759b-119">An [Emulation][DevtoolsGuideEdgehtml|::ref9::|] panel to test your site with different browser profiles, screen resolutions, and GPS location coordinates</span></span>  

<span data-ttu-id="c759b-120">[フィードバックと機能のリクエストを](#feedback)送信してください。</span><span class="sxs-lookup"><span data-stu-id="c759b-120">Please keep sending your [feedback and feature requests](#feedback)!</span></span>  

> [!TIP]
> <span data-ttu-id="c759b-121">[Microsoft Edge \ (EdgeHTML \) で任意のブラウザーから無料でテスト][BrowserstackEdgehtml]します。</span><span class="sxs-lookup"><span data-stu-id="c759b-121">[Test on Microsoft Edge \(EdgeHTML\) free from any browser][BrowserstackEdgehtml].</span></span>  
> <span data-ttu-id="c759b-122">Microsoft Edge チームは、 [Browserstack][BrowserstackEdgehtml]と提携して、microsoft edge \ (EdgeHTML \) での無料のライブテストと自動テストを提供します。</span><span class="sxs-lookup"><span data-stu-id="c759b-122">The Microsoft Edge team partnered with [BrowserStack][BrowserstackEdgehtml] to provide free live and automated testing on Microsoft Edge \(EdgeHTML\).</span></span>  

## <span data-ttu-id="c759b-123">Microsoft ストア アプリ</span><span class="sxs-lookup"><span data-stu-id="c759b-123">Microsoft Store app</span></span>  

<span data-ttu-id="c759b-124">**Microsoft Edge \ (EdgeHTML \) DevTools**は、ブラウザー内 \`F12\`(\) のツールエクスペリエンスに加えて、 [microsoft ストアからスタンドアロンの Windows 10 アプリ][MicrosoftStoreEdgeDevtoolsPreview]として[利用できるようになりました][DevtoolsGuideEdgehtmlWhatsnew]。</span><span class="sxs-lookup"><span data-stu-id="c759b-124">The **Microsoft Edge \(EdgeHTML\) DevTools** are [now available][DevtoolsGuideEdgehtmlWhatsnew] as a standalone [Windows 10 app from the Microsoft Store][MicrosoftStoreEdgeDevtoolsPreview], in addition to the in-browser \(`F12`\) tooling experience.</span></span>  <span data-ttu-id="c759b-125">ストアバージョンでは、ローカルとリモートのページターゲットを開くための**セレクター**パネルが用意されています。これには、devtools インスタンス間で簡単に切り替えるためのタブ付きレイアウトが用意されています。</span><span class="sxs-lookup"><span data-stu-id="c759b-125">With the store version comes a **chooser** panel for attaching to open local and remote page targets and a tabbed layout for easy switching between DevTools instances.</span></span>  

### <span data-ttu-id="c759b-126">ローカルデバッグ</span><span class="sxs-lookup"><span data-stu-id="c759b-126">Local debugging</span></span>  

<span data-ttu-id="c759b-127">ページをローカルでデバッグするには、Microsoft Edge DevTools アプリを起動するだけです。</span><span class="sxs-lookup"><span data-stu-id="c759b-127">To debug a page locally, simply launch the Microsoft Edge DevTools app.</span></span>  <span data-ttu-id="c759b-128">セレクターの**ローカル**パネルには、開いている [Edge browser] タブ、 [pwas][PwasEdgehtmlIndex] \ (`WWAHost.exe`プロセス \)、 [webview][HostingWebview]コントロールなど、すべてのアクティブな EdgeHTML コンテンツプロセスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c759b-128">The **Local** panel of the chooser displays all of the active EdgeHTML content processes, including open Edge browser tabs, running [PWAs][PwasEdgehtmlIndex] \(`WWAHost.exe` processes\), and [webview][HostingWebview] controls.</span></span>  <span data-ttu-id="c759b-129">目的のターゲットを選択して、DevTools の新しいタブインスタンスを添付して開きます。</span><span class="sxs-lookup"><span data-stu-id="c759b-129">Select your desired target to attach and open a new tab instance of the DevTools.</span></span>  

:::image type="complex" source="./devtools-guide/media/chooser_local.png" alt-text="DevTools アプリのローカルパネル":::
   <span data-ttu-id="c759b-131">DevTools アプリのローカルパネル</span><span class="sxs-lookup"><span data-stu-id="c759b-131">DevTools app Local panel</span></span>
:::image-end:::

<!--![DevTools app Local panel][ImageDevtoolsGuideEdgehtmlChooselocal]  -->  

### <span data-ttu-id="c759b-132">リモートデバッグ</span><span class="sxs-lookup"><span data-stu-id="c759b-132">Remote debugging</span></span>  

<span data-ttu-id="c759b-133">Microsoft Edge DevTools アプリは、新しくリリースされた[Devtools プロトコル][DevtoolsProtocolEdgehtmlIndex]を使ってリモートコンピューター上のページをデバッグするための基本的なサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="c759b-133">The Microsoft Edge DevTools app introduces basic support for debugging pages on a remote machine via our newly released [DevTools Protocol][DevtoolsProtocolEdgehtmlIndex].</span></span>  <span data-ttu-id="c759b-134">最新のリリースでは、[デバッガー][DevtoolsGuideEdgehtml|::ref10::|]のコア機能へのリモートアクセス、[要素][DevtoolsGuideEdgehtml|::ref11::|]\ (読み取り専用操作の場合)、[コンソール][DevtoolsGuideEdgehtml|::ref12::|]パネルが使用されています。</span><span class="sxs-lookup"><span data-stu-id="c759b-134">With the latest release comes remote access to core functionality in the [Debugger][DevtoolsGuideEdgehtml|::ref10::|], [Elements][DevtoolsGuideEdgehtml|::ref11::|] \(for read-only operations\), and [Console][DevtoolsGuideEdgehtml|::ref12::|] panels.</span></span>  <span data-ttu-id="c759b-135">リモートデバッグは、デスクトップホストを実行している Microsoft Edge \ (EdgeHTML \) に限定され、将来のリリースで使用される他の EdgeHTML ホストと Windows 10 デバイスをサポートします。</span><span class="sxs-lookup"><span data-stu-id="c759b-135">Remote debugging is limited to Microsoft Edge \(EdgeHTML\) running desktop hosts, with support for other EdgeHTML hosts and Windows 10 devices coming in future releases.</span></span>  

<span data-ttu-id="c759b-136">はじめに、 [Devtools プロトコル][DevtoolsProtocolEdgehtmlIndex]ドキュメントの[*Microsoft Edge devtools*][DevtoolsProtocolEdgehtmlClientsEdgePreview]セクションを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c759b-136">To get started, check out the [*Microsoft Edge DevTools*][DevtoolsProtocolEdgehtmlClientsEdgePreview] section of the [DevTools Protocol][DevtoolsProtocolEdgehtmlIndex] docs.</span></span>  

:::image type="complex" source="./devtools-guide/media/chooser_remote.png" alt-text="DevTools アプリのリモートパネル":::
   <span data-ttu-id="c759b-138">DevTools アプリのリモートパネル</span><span class="sxs-lookup"><span data-stu-id="c759b-138">DevTools app Remote panel</span></span>
:::image-end:::

<!--![DevTools app Remote panel][ImageDevtoolsGuideEdgehtmlRemote]  -->  

## <span data-ttu-id="c759b-139">一般的なショートカットキー</span><span class="sxs-lookup"><span data-stu-id="c759b-139">General Shortcuts</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="c759b-140">最新バージョンの Windows では、すべてのショートカットが確認されています。</span><span class="sxs-lookup"><span data-stu-id="c759b-140">All shortcuts have been verified in the most recent version of Windows.</span></span>  
> <span data-ttu-id="c759b-141">ショートカットを使用できない場合は、Windows のコピーを更新してください。</span><span class="sxs-lookup"><span data-stu-id="c759b-141">If you are unable to use a shortcut, please update your copy of Windows.</span></span>  

<span data-ttu-id="c759b-142">これらのショートカットは、主要な DevTools ウィンドウを制御し、すべてのツールで動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c759b-142">These shortcuts control the main DevTools window and should work across all tools.</span></span>  

| <span data-ttu-id="c759b-143">操作</span><span class="sxs-lookup"><span data-stu-id="c759b-143">Action</span></span> | <span data-ttu-id="c759b-144">キー</span><span class="sxs-lookup"><span data-stu-id="c759b-144">Shortcut</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="c759b-145">DevTools の表示/非表示を切り替える \ (最後に表示したパネルに表示されます)</span><span class="sxs-lookup"><span data-stu-id="c759b-145">Show/Hide DevTools \(opens to last viewed panel\)</span></span> | `F12`<span data-ttu-id="c759b-146">, `Ctrl`+`Shift`+</span><span class="sxs-lookup"><span data-stu-id="c759b-146">, `Ctrl`+`Shift`+</span></span>`I` |  
| <span data-ttu-id="c759b-147">ドッキングの切り替え \ (アンドック/ボトム/右)</span><span class="sxs-lookup"><span data-stu-id="c759b-147">Toggle docking \(Undock/Bottom/Right\)</span></span> | `Ctrl`+`Shift`+`D` |  
| <span data-ttu-id="c759b-148">ファイルを開く</span><span class="sxs-lookup"><span data-stu-id="c759b-148">Open file</span></span> | `Ctrl`<span data-ttu-id="c759b-149">+`P`, `Ctrl`+</span><span class="sxs-lookup"><span data-stu-id="c759b-149">+`P`, `Ctrl`+</span></span>`O` |  
| <span data-ttu-id="c759b-150">デバッガーで編集不可の HTML ソースコードを表示する</span><span class="sxs-lookup"><span data-stu-id="c759b-150">Show non-editable HTML source code in Debugger</span></span> | `Ctrl`+`U` |  
| <span data-ttu-id="c759b-151">他のツールの下部に本体の表示/非表示を切り替える</span><span class="sxs-lookup"><span data-stu-id="c759b-151">Show/hide Console at the bottom of any other tool</span></span>  | `Ctrl`+`` ` `` |  
| <span data-ttu-id="c759b-152">要素に切り替える \ (DOM Explorer \)</span><span class="sxs-lookup"><span data-stu-id="c759b-152">Switch to Elements \(DOM Explorer\)</span></span> | `Ctrl`+`1` |  
| <span data-ttu-id="c759b-153">コンソールに切り替える</span><span class="sxs-lookup"><span data-stu-id="c759b-153">Switch to Console</span></span> |  `Ctrl`+`2` |  
| <span data-ttu-id="c759b-154">デバッガーに切り替える</span><span class="sxs-lookup"><span data-stu-id="c759b-154">Switch to Debugger</span></span> | `Ctrl`+`3` |  
| <span data-ttu-id="c759b-155">ネットワークに切り替える</span><span class="sxs-lookup"><span data-stu-id="c759b-155">Switch to Network</span></span> | `Ctrl`+`4` |  
| <span data-ttu-id="c759b-156">パフォーマンスに切り替える</span><span class="sxs-lookup"><span data-stu-id="c759b-156">Switch to Performance</span></span> | `Ctrl`+`5` |  
| <span data-ttu-id="c759b-157">メモリに切り替える</span><span class="sxs-lookup"><span data-stu-id="c759b-157">Switch to Memory</span></span> | `Ctrl`+`6` |  
| <span data-ttu-id="c759b-158">エミュレーションに切り替える</span><span class="sxs-lookup"><span data-stu-id="c759b-158">Switch to Emulation</span></span> | `Ctrl`+`7` |  
| <span data-ttu-id="c759b-159">ヘルプドキュメント</span><span class="sxs-lookup"><span data-stu-id="c759b-159">Help Document</span></span> | `F1` |  
| <span data-ttu-id="c759b-160">次のツール</span><span class="sxs-lookup"><span data-stu-id="c759b-160">Next tool</span></span> | `Ctrl`+`F6` |  
| <span data-ttu-id="c759b-161">前のツール</span><span class="sxs-lookup"><span data-stu-id="c759b-161">Previous tool</span></span> | `Ctrl`+`Shift`+`F6` |  
| <span data-ttu-id="c759b-162">前のツール \ (履歴から)</span><span class="sxs-lookup"><span data-stu-id="c759b-162">Previous tool \(from history\)</span></span> | `Ctrl`+`Shift`+`[` |  
| <span data-ttu-id="c759b-163">次のツール \ (履歴から)</span><span class="sxs-lookup"><span data-stu-id="c759b-163">Next tool \(from history\)</span></span> | `Ctrl`+`Shift`+`]` |  
| <span data-ttu-id="c759b-164">次のサブフレーム</span><span class="sxs-lookup"><span data-stu-id="c759b-164">Next Subframe</span></span> | `F6` |  
| <span data-ttu-id="c759b-165">前のサブフレーム</span><span class="sxs-lookup"><span data-stu-id="c759b-165">Previous Subframe</span></span> | `Shift`+`F6` |  
| <span data-ttu-id="c759b-166">検索ボックス内の次の検索結果</span><span class="sxs-lookup"><span data-stu-id="c759b-166">Next match in Search box</span></span> | `F3` |  
| <span data-ttu-id="c759b-167">検索ボックス内の前の一致</span><span class="sxs-lookup"><span data-stu-id="c759b-167">Previous match in Search box</span></span> | `Shift`+`F3` |  
| <span data-ttu-id="c759b-168">[検索] ボックスで検索</span><span class="sxs-lookup"><span data-stu-id="c759b-168">Find in search box</span></span> | `Ctrl`+`F` |  
| <span data-ttu-id="c759b-169">フォーカスをコンソールの下部に移動する</span><span class="sxs-lookup"><span data-stu-id="c759b-169">Give focus to console at the bottom</span></span> | `Alt`+`Shift`+`I` |  
| <span data-ttu-id="c759b-170">コンソールで DevTools を起動する</span><span class="sxs-lookup"><span data-stu-id="c759b-170">Launch DevTools to Console</span></span> | `Ctrl`+`Shift`+`J` |  
| <span data-ttu-id="c759b-171">ページを最新の情報に更新する</span><span class="sxs-lookup"><span data-stu-id="c759b-171">Refresh the page</span></span> | `Ctrl`<span data-ttu-id="c759b-172">+`Shift`+`F5`, `Ctrl`+</span><span class="sxs-lookup"><span data-stu-id="c759b-172">+`Shift`+`F5`, `Ctrl`+</span></span>`R` |  

> [!NOTE]
> <span data-ttu-id="c759b-173">デバッグしてブレークポイントで一時停止している場合、"**ページを更新**する" アクションでは最初にランタイムが再開されます。</span><span class="sxs-lookup"><span data-stu-id="c759b-173">If you are debugging and paused at a breakpoint, the **Refresh the page** action resumes the runtime first.</span></span>  

## <span data-ttu-id="c759b-174">フィードバック</span><span class="sxs-lookup"><span data-stu-id="c759b-174">Feedback</span></span>  

<span data-ttu-id="c759b-175">Microsoft Edge \ (EdgeHTML \) DevTools の向上に役立てるため、フィードバックを送信してください。</span><span class="sxs-lookup"><span data-stu-id="c759b-175">Please send your feedback to help improve the Microsoft Edge \(EdgeHTML\) DevTools for you!</span></span>  <span data-ttu-id="c759b-176">ツール \ (`F12`\) を開いて、[[フィードバックの送信](#microsoft-edge-edgehtml-developer-tools)] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="c759b-176">Simply open the tools \(`F12`\) and select the [Send feedback](#microsoft-edge-edgehtml-developer-tools) button.</span></span>  

<span data-ttu-id="c759b-177">[Windows Insider][WindowsInsiderProgram]になると、 [devtools の最新機能][DevtoolsGuideEdgehtmlWhatsnew]をプレビューできます。</span><span class="sxs-lookup"><span data-stu-id="c759b-177">Become a [Windows Insider][WindowsInsiderProgram] to preview the [latest features coming to the DevTools][DevtoolsGuideEdgehtmlWhatsnew].</span></span>  <span data-ttu-id="c759b-178">Windows フィードバック Hub アプリを使用して、Windows の一般的な提案と問題の投稿、事後投票、追跡、サポートを行います。</span><span class="sxs-lookup"><span data-stu-id="c759b-178">Use the Windows Feedback Hub app to post, up-vote, track and get support for general Windows suggestions and problems.</span></span>  

<!-- image links  -->  

<!--[ImageDevtoolsEdgehtml]: /microsoft-edge/devtools-guide/media/devtools.png "Microsoft Edge (EdgeHTML) DevTools"  -->  
<!--[ImageDevtoolsGuideEdgehtmlChooselocal]: /microsoft-edge/devtools-guide/media/chooser_local.png "DevTools app Local panel"  -->  
<!--[ImageDevtoolsGuideEdgehtmlRemote]: /microsoft-edge/devtools-guide/media/chooser_remote.png "DevTools app Remote panel"  -->  

<!-- links  -->  

[DevtoolsGuideEdgehtmlConsole]: /microsoft-edge/devtools-guide/console "コンソ"  
[DevtoolsGuideEdgehtmlDebugger]: /microsoft-edge/devtools-guide/debugger "ブレーク"  
[DevtoolsGuideEdgehtmlElements]: /microsoft-edge/devtools-guide/elements "エレメント"  
[DevtoolsGuideEdgehtmlEmulation]: /microsoft-edge/devtools-guide/emulation "エミュレーション"  
[DevtoolsGuideEdgehtmlMemory]: /microsoft-edge/devtools-guide/memory "メモリライザーカード"  
[DevtoolsGuideEdgehtmlNetwork]: /microsoft-edge/devtools-guide/network "ネットワーク"  
[DevtoolsGuideEdgehtmlPerformance]: /microsoft-edge/devtools-guide/performance "処理"  
[DevtoolsGuideEdgehtmlServiceworkers]: /microsoft-edge/devtools-guide/service-workers "サービス員"  
[DevtoolsGuideEdgehtmlStorage]: /microsoft-edge/devtools-guide/storage "容量"  
[DevtoolsGuideEdgehtmlWhatsnew]: /microsoft-edge/devtools-guide/whats-new "最新の Windows 10 更新プログラム (EdgeHTML 18) の DevTools"  
[DevtoolsProtocolEdgehtmlIndex]: /microsoft-edge/devtools-protocol/index "Microsoft Edge (EdgeHTML) DevTools プロトコル"  
[DevtoolsProtocolEdgehtmlClientsEdgePreview]: /microsoft-edge/devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview "Microsoft Edge DevTools のプレビュー-DevTools プロトコルクライアント"  
[HostingWebview]: /microsoft-edge/hosting/webview "Windows 10 アプリ用 WebView (EdgeHTML)"  
[PwasEdgehtmlIndex]: /microsoft-edge/progressive-web-apps-edgehtml/index "Windows のプログレッシブ Web アプリ (EdgeHTML)"  

[MicrosoftStoreEdgeDevtoolsPreview]: https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj "Microsoft Edge DevTools プレビュー"  

[WindowsInsiderProgram]: https://insider.windows.com "Windows Insider プログラム"  

[BrowserstackEdgehtml]: https://www.browserstack.com/test-on-microsoft-edge-browser "Microsoft Edge ブラウザーの無料テストBrowserStack"  

[GithubMicrosoftChakracore]: https://github.com/Microsoft/ChakraCore "microsoft/ChakraCore |GitHub"  

[TypeScriptIndex]: https://www.typescriptlang.org "TypeScript"  
