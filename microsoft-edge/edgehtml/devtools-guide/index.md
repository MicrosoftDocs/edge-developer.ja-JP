---
description: Microsoft Edge (EdgeHTML) 開発者ツールを理解する
title: Microsoft Edge (EdgeHTML) 開発者ツール
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 89fdbcdf10d10c57836067ca7d02afa3fd48cbc9
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234585"
---
# <span data-ttu-id="56d1d-104">Microsoft Edge (EdgeHTML) 開発者ツール</span><span class="sxs-lookup"><span data-stu-id="56d1d-104">Microsoft Edge (EdgeHTML) Developer Tools</span></span>  

[!INCLUDE [new-devtools-version-note](../includes/new-devtools-version-note.md)]  

<span data-ttu-id="56d1d-105">Microsoft Edge \(EdgeHTML \) DevTools は、[TypeScript][|::ref1::|Index] で構築され、[オープン ソース][GithubMicrosoftChakracore] で動作し、最新のフロントエンド ワークフローを対象として最適化された [スタンドアロン Windows 10 アプリ][MicrosoftStoreEdgeDevtoolsPreview] として Microsoft Store で利用できます。</span><span class="sxs-lookup"><span data-stu-id="56d1d-105">The Microsoft Edge \(EdgeHTML\) DevTools are built with [TypeScript][|::ref1::|Index], powered by [open source][GithubMicrosoftChakracore], optimized for modern front-end workflows, and now available as a [standalone Windows 10 app][MicrosoftStoreEdgeDevtoolsPreview] in the Microsoft Store!</span></span>  

<span data-ttu-id="56d1d-106">最新の機能の詳細については、「[Windows 10 の最新の更新プログラムの DevTools (EdgeHTML 18)][DevtoolsGuideEdgehtmlWhatsnew]」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56d1d-106">For more on the latest features, check out [DevTools in the latest update of Windows 10 (EdgeHTML 18)][DevtoolsGuideEdgehtmlWhatsnew].</span></span>  

## <span data-ttu-id="56d1d-107">コア ツール</span><span class="sxs-lookup"><span data-stu-id="56d1d-107">Core tools</span></span>  

:::image type="complex" source="./media/devtools.png" alt-text="Microsoft Edge (EdgeHTML) DevTools":::
   <span data-ttu-id="56d1d-109">Microsoft Edge (EdgeHTML) DevTools</span><span class="sxs-lookup"><span data-stu-id="56d1d-109">Microsoft Edge (EdgeHTML) DevTools</span></span>
:::image-end:::

<!--![Microsoft Edge \(EdgeHTML\) DevTools][ImageDevtoolsEdgehtml]  -->  

<span data-ttu-id="56d1d-110">Microsoft Edge \(EdgeHTML \) DevTools には、以下のものがあります。</span><span class="sxs-lookup"><span data-stu-id="56d1d-110">The Microsoft Edge \(EdgeHTML\) DevTools include:</span></span>  

*   <span data-ttu-id="56d1d-111">[要素][DevtoolsGuideEdgehtml|::ref2::|] は、パネルHTML および CSS の編集、アクセシビリティのプロパティの検査、イベント リスナーの表示、DOM 変異のブレークポイントの設定を行います。</span><span class="sxs-lookup"><span data-stu-id="56d1d-111">An [Elements][DevtoolsGuideEdgehtml|::ref2::|] panel to edit HTML and CSS, inspect accessibility properties, view event listeners, and set DOM mutation breakpoints</span></span>  
*   <span data-ttu-id="56d1d-112">[コンソール][DevtoolsGuideEdgehtml|::ref3::|] は、ログ メッセージを表示およびフィルタリングし、JavaScript オブジェクトと DOM ノードを検査し、選択したウィンドウやフレームのコンテキストでの JavaScript を実行します。</span><span class="sxs-lookup"><span data-stu-id="56d1d-112">A [Console][DevtoolsGuideEdgehtml|::ref3::|] to view and filter log messages, inspect JavaScript objects and DOM nodes, and run JavaScript in the context of the selected window or frame</span></span>  
*   <span data-ttu-id="56d1d-113">[デバッガー][DevtoolsGuideEdgehtml|::ref4::|] は、コードのステップ実行、ウォッチポイントとブレークポイントの設定、コードのライブ編集、Web ストレージおよび cookie キャッシュの検査を行います。</span><span class="sxs-lookup"><span data-stu-id="56d1d-113">A [Debugger][DevtoolsGuideEdgehtml|::ref4::|] to step through code, set watches and breakpoints, live edit your code, and inspect your web storage and cookie caches</span></span>  
*   <span data-ttu-id="56d1d-114">[ネットワーク][DevtoolsGuideEdgehtml|::ref5::|] パネルは、ネットワークとブラウザーのキャッシュからの要求や応答を監視および検査します。</span><span class="sxs-lookup"><span data-stu-id="56d1d-114">A [Network][DevtoolsGuideEdgehtml|::ref5::|] panel to monitor and inspect requests and responses from the network and browser cache</span></span>  
*   <span data-ttu-id="56d1d-115">[パフォーマンス][DevtoolsGuideEdgehtml|::ref6::|] パネルは、サイトに必要な時間とシステム リソースをプロファイルします。</span><span class="sxs-lookup"><span data-stu-id="56d1d-115">A [Performance][DevtoolsGuideEdgehtml|::ref6::|] panel to profile the time and system resources required by your site</span></span>  
*   <span data-ttu-id="56d1d-116">[メモリ][DevtoolsGuideEdgehtml|::ref7::|] パネルは、メモリ リソースの使用状況を測定し、コード ランタイムの異なる状態でヒープ スナップショットを比較します。</span><span class="sxs-lookup"><span data-stu-id="56d1d-116">A [Memory][DevtoolsGuideEdgehtml|::ref7::|] panel to measure your use of memory resources and compare heap snapshots at different states of code runtime</span></span>  
*   <span data-ttu-id="56d1d-117">[ストレージ][DevtoolsGuideEdgehtml|::ref8::|] パネルは、Web ストレージ、IndexedDB、cookie、および キャッシュ データを検査および管理します。</span><span class="sxs-lookup"><span data-stu-id="56d1d-117">A [Storage][DevtoolsGuideEdgehtml|::ref8::|] panel for inspecting and managing your web storage, IndexedDB, cookies and cache data</span></span>  
*   <span data-ttu-id="56d1d-118">[サービス ワーカー][DevtoolsGuideEdgehtmlServiceworkers] パネルは、サービス ワーカーを管理およびデバッグします。</span><span class="sxs-lookup"><span data-stu-id="56d1d-118">A [Service Workers][DevtoolsGuideEdgehtmlServiceworkers] panel for managing and debugging your service workers</span></span>  
*   <span data-ttu-id="56d1d-119">[エミュレーション][DevtoolsGuideEdgehtml|::ref9::|] パネルは、異なるブラウザー プロファイル、画面解像度、GPS の位置座標でサイトをテストします。</span><span class="sxs-lookup"><span data-stu-id="56d1d-119">An [Emulation][DevtoolsGuideEdgehtml|::ref9::|] panel to test your site with different browser profiles, screen resolutions, and GPS location coordinates</span></span>  

<span data-ttu-id="56d1d-120">[フィードバックと機能のリクエスト](#getting-in-touch-with-the-microsoft-edge-devtools-team) をどんどん送ってください!</span><span class="sxs-lookup"><span data-stu-id="56d1d-120">Please keep sending your [feedback and feature requests](#getting-in-touch-with-the-microsoft-edge-devtools-team)!</span></span>  

> [!TIP]
> <span data-ttu-id="56d1d-121">[Microsoft Edge \(EdgeHTML\) は、どのブラウザーからでも無料でお試しいただけます][BrowserstackEdgehtml]。</span><span class="sxs-lookup"><span data-stu-id="56d1d-121">[Test on Microsoft Edge \(EdgeHTML\) free from any browser][BrowserstackEdgehtml].</span></span>  
> <span data-ttu-id="56d1d-122">Microsoft Edge は [BrowserStack][BrowserstackEdgehtml] と提携して、Microsoft Edge \(EdgeHTML) のライブ テストおよび自動テストを無料で提供しています。</span><span class="sxs-lookup"><span data-stu-id="56d1d-122">The Microsoft Edge team partnered with [BrowserStack][BrowserstackEdgehtml] to provide free live and automated testing on Microsoft Edge \(EdgeHTML\).</span></span>  

## <span data-ttu-id="56d1d-123">Microsoft ストア アプリ</span><span class="sxs-lookup"><span data-stu-id="56d1d-123">Microsoft Store app</span></span>  

<span data-ttu-id="56d1d-124">**Microsoft Edge \(EdgeHTML \) DevTools** は、ブラウザー内での \(`F12`\) のツール環境に加えて、[Microsoft Store から Windows 10 アプリ][MicrosoftStoreEdgeDevtoolsPreview] スタンドアロン版として [現在使用可能][DevtoolsGuideEdgehtmlWhatsnew] です。</span><span class="sxs-lookup"><span data-stu-id="56d1d-124">The **Microsoft Edge \(EdgeHTML\) DevTools** are [now available][DevtoolsGuideEdgehtmlWhatsnew] as a standalone [Windows 10 app from the Microsoft Store][MicrosoftStoreEdgeDevtoolsPreview], in addition to the in-browser \(`F12`\) tooling experience.</span></span>  <span data-ttu-id="56d1d-125">ストア バージョンでは、ローカルとリモートのページ　ターゲットを開くために [**セレクター**] パネルが表示されます。これには、DevTools インスタンス間で簡単に切り替えられるようにタブ レイアウトが用意されています。</span><span class="sxs-lookup"><span data-stu-id="56d1d-125">With the store version comes a **chooser** panel for attaching to open local and remote page targets and a tabbed layout for easy switching between DevTools instances.</span></span>  

### <span data-ttu-id="56d1d-126">ローカル デバッグ</span><span class="sxs-lookup"><span data-stu-id="56d1d-126">Local debugging</span></span>  

<span data-ttu-id="56d1d-127">ページをローカルでデバッグするのは、Microsoft Edge DevTools アプリを起動するだけでできます。</span><span class="sxs-lookup"><span data-stu-id="56d1d-127">To debug a page locally, simply launch the Microsoft Edge DevTools app.</span></span>  <span data-ttu-id="56d1d-128">セレクターの [**ローカル**] パネルには、[Edge ブラウザーを開く] タブを含むすべてのアクティブな EdgeHTML コンテンツのプロセスが表示されます。これには、[PWA][PwasEdgehtmlIndex] \(`WWAHost.exe`プロセス \)、および [webview][HostingWebview] コントロールなどが含まれます。</span><span class="sxs-lookup"><span data-stu-id="56d1d-128">The **Local** panel of the chooser displays all of the active EdgeHTML content processes, including open Edge browser tabs, running [PWAs][PwasEdgehtmlIndex] \(`WWAHost.exe` processes\), and [webview][HostingWebview] controls.</span></span>  <span data-ttu-id="56d1d-129">目的のターゲットを選択して、DevTools の新しいタブ インスタンスをアタッチして開きます。</span><span class="sxs-lookup"><span data-stu-id="56d1d-129">Select your desired target to attach and open a new tab instance of the DevTools.</span></span>  

:::image type="complex" source=".//media/chooser_local.png" alt-text="DevTools アプリ ローカル パネル":::
   <span data-ttu-id="56d1d-131">DevTools アプリ ローカル パネル</span><span class="sxs-lookup"><span data-stu-id="56d1d-131">DevTools app Local panel</span></span>
:::image-end:::

<!--![DevTools app Local panel][ImageDevtoolsGuideEdgehtmlChooselocal]  -->  

### <span data-ttu-id="56d1d-132">リモート デバッグ</span><span class="sxs-lookup"><span data-stu-id="56d1d-132">Remote debugging</span></span>  

<span data-ttu-id="56d1d-133">Microsoft Edge DevTools アプリは、新しくリリースされた [DevTools プロトコル][DevtoolsProtocolEdgehtmlIndex] を介して、リモート コンピューター上のページをデバッグするための基本的なサポートを導入しています。</span><span class="sxs-lookup"><span data-stu-id="56d1d-133">The Microsoft Edge DevTools app introduces basic support for debugging pages on a remote machine via our newly released [DevTools Protocol][DevtoolsProtocolEdgehtmlIndex].</span></span>  <span data-ttu-id="56d1d-134">最新のリリースでは、[デバッガー][DevtoolsGuideEdgehtml|::ref10::|]、[要素][DevtoolsGuideEdgehtml|::ref11::|] (読み取り専用操作の場合)、および [コンソール][DevtoolsGuideEdgehtml|::ref12::|] パネルの主な機能にリモート アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="56d1d-134">With the latest release comes remote access to core functionality in the [Debugger][DevtoolsGuideEdgehtml|::ref10::|], [Elements][DevtoolsGuideEdgehtml|::ref11::|] \(for read-only operations\), and [Console][DevtoolsGuideEdgehtml|::ref12::|] panels.</span></span>  <span data-ttu-id="56d1d-135">リモート デバッグは、Microsoft Edge \(EdgeHTML \) が動作しているデスクトップ ホストに限定されており、他の EdgeHTML ホストと Windows 10デバイスについては、将来のリリースでサポートされる予定です。</span><span class="sxs-lookup"><span data-stu-id="56d1d-135">Remote debugging is limited to Microsoft Edge \(EdgeHTML\) running desktop hosts, with support for other EdgeHTML hosts and Windows 10 devices coming in future releases.</span></span>  

<span data-ttu-id="56d1d-136">始めるには、[*Microsoft Edge DevTools*][DevtoolsProtocolEdgehtmlClientsEdgePreview] の [DevTools プロトコル][DevtoolsProtocolEdgehtmlIndex] ドキュメントにあるセクションを確認してください。</span><span class="sxs-lookup"><span data-stu-id="56d1d-136">To get started, check out the [*Microsoft Edge DevTools*][DevtoolsProtocolEdgehtmlClientsEdgePreview] section of the [DevTools Protocol][DevtoolsProtocolEdgehtmlIndex] docs.</span></span>  

:::image type="complex" source="./media/chooser_remote.png" alt-text="DevTools アプリのリモート パネル":::
   <span data-ttu-id="56d1d-138">DevTools アプリのリモート パネル</span><span class="sxs-lookup"><span data-stu-id="56d1d-138">DevTools app Remote panel</span></span>
:::image-end:::

<!--![DevTools app Remote panel][ImageDevtoolsGuideEdgehtmlRemote]  -->  

## <span data-ttu-id="56d1d-139">一般的なショートカット</span><span class="sxs-lookup"><span data-stu-id="56d1d-139">General Shortcuts</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="56d1d-140">すべてのショートカットは、最新バージョンの Windows で確認されています。</span><span class="sxs-lookup"><span data-stu-id="56d1d-140">All shortcuts have been verified in the most recent version of Windows.</span></span>  
> <span data-ttu-id="56d1d-141">ショートカットを使用できない場合は、Windows のコピーを更新してください。</span><span class="sxs-lookup"><span data-stu-id="56d1d-141">If you are unable to use a shortcut, please update your copy of Windows.</span></span>  

<span data-ttu-id="56d1d-142">これらのショートカットは、DevTools のメイン ウィンドウを制御し、すべてのツールで動作します。</span><span class="sxs-lookup"><span data-stu-id="56d1d-142">These shortcuts control the main DevTools window and should work across all tools.</span></span>  

| <span data-ttu-id="56d1d-143">操作</span><span class="sxs-lookup"><span data-stu-id="56d1d-143">Action</span></span> | <span data-ttu-id="56d1d-144">ショートカット</span><span class="sxs-lookup"><span data-stu-id="56d1d-144">Shortcut</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="56d1d-145">DevTools の表示/非表示 \(最後に表示されたパネルに表示される \)</span><span class="sxs-lookup"><span data-stu-id="56d1d-145">Show/Hide DevTools \(opens to last viewed panel\)</span></span> | `F12`<span data-ttu-id="56d1d-146">, `Ctrl`+`Shift`+</span><span class="sxs-lookup"><span data-stu-id="56d1d-146">, `Ctrl`+`Shift`+</span></span>`I` |  
| <span data-ttu-id="56d1d-147">ドッキングの切り替え \ （ドッキングなし / 一番下/右 \）</span><span class="sxs-lookup"><span data-stu-id="56d1d-147">Toggle docking \(Undock/Bottom/Right\)</span></span> | `Ctrl`+`Shift`+`D` |  
| <span data-ttu-id="56d1d-148">ファイルを開く</span><span class="sxs-lookup"><span data-stu-id="56d1d-148">Open file</span></span> | `Ctrl`<span data-ttu-id="56d1d-149">+`P`, `Ctrl`+</span><span class="sxs-lookup"><span data-stu-id="56d1d-149">+`P`, `Ctrl`+</span></span>`O` |  
| <span data-ttu-id="56d1d-150">デバッガーで編集不可の HTML ソース コードを表示する</span><span class="sxs-lookup"><span data-stu-id="56d1d-150">Show non-editable HTML source code in Debugger</span></span> | `Ctrl`+`U` |  
| <span data-ttu-id="56d1d-151">他のツールの下部にあるコンソールの表示/非表示</span><span class="sxs-lookup"><span data-stu-id="56d1d-151">Show/hide Console at the bottom of any other tool</span></span>  | `Ctrl`+`` ` `` |  
| <span data-ttu-id="56d1d-152">要素に切り替える \(DOM Explorer \)</span><span class="sxs-lookup"><span data-stu-id="56d1d-152">Switch to Elements \(DOM Explorer\)</span></span> | `Ctrl`+`1` |  
| <span data-ttu-id="56d1d-153">コンソールに切り替える</span><span class="sxs-lookup"><span data-stu-id="56d1d-153">Switch to Console</span></span> |  `Ctrl`+`2` |  
| <span data-ttu-id="56d1d-154">デバッガーに切り替える</span><span class="sxs-lookup"><span data-stu-id="56d1d-154">Switch to Debugger</span></span> | `Ctrl`+`3` |  
| <span data-ttu-id="56d1d-155">ネットワークに切り替える</span><span class="sxs-lookup"><span data-stu-id="56d1d-155">Switch to Network</span></span> | `Ctrl`+`4` |  
| <span data-ttu-id="56d1d-156">パフォーマンスに切り替える</span><span class="sxs-lookup"><span data-stu-id="56d1d-156">Switch to Performance</span></span> | `Ctrl`+`5` |  
| <span data-ttu-id="56d1d-157">メモリに切り替える</span><span class="sxs-lookup"><span data-stu-id="56d1d-157">Switch to Memory</span></span> | `Ctrl`+`6` |  
| <span data-ttu-id="56d1d-158">エミュレーションに切り替える</span><span class="sxs-lookup"><span data-stu-id="56d1d-158">Switch to Emulation</span></span> | `Ctrl`+`7` |  
| <span data-ttu-id="56d1d-159">ヘルプ ドキュメント</span><span class="sxs-lookup"><span data-stu-id="56d1d-159">Help Document</span></span> | `F1` |  
| <span data-ttu-id="56d1d-160">次のツール</span><span class="sxs-lookup"><span data-stu-id="56d1d-160">Next tool</span></span> | `Ctrl`+`F6` |  
| <span data-ttu-id="56d1d-161">前のツール</span><span class="sxs-lookup"><span data-stu-id="56d1d-161">Previous tool</span></span> | `Ctrl`+`Shift`+`F6` |  
| <span data-ttu-id="56d1d-162">前のツール \(履歴から \)</span><span class="sxs-lookup"><span data-stu-id="56d1d-162">Previous tool \(from history\)</span></span> | `Ctrl`+`Shift`+`[` |  
| <span data-ttu-id="56d1d-163">次のツール \(履歴から \)</span><span class="sxs-lookup"><span data-stu-id="56d1d-163">Next tool \(from history\)</span></span> | `Ctrl`+`Shift`+`]` |  
| <span data-ttu-id="56d1d-164">次のサブフレーム</span><span class="sxs-lookup"><span data-stu-id="56d1d-164">Next Subframe</span></span> | `F6` |  
| <span data-ttu-id="56d1d-165">前のサブフレーム</span><span class="sxs-lookup"><span data-stu-id="56d1d-165">Previous Subframe</span></span> | `Shift`+`F6` |  
| <span data-ttu-id="56d1d-166">[検索] ボックス内の次の一致</span><span class="sxs-lookup"><span data-stu-id="56d1d-166">Next match in Search box</span></span> | `F3` |  
| <span data-ttu-id="56d1d-167">[検索] ボックス内の前の一致</span><span class="sxs-lookup"><span data-stu-id="56d1d-167">Previous match in Search box</span></span> | `Shift`+`F3` |  
| <span data-ttu-id="56d1d-168">[検索] ボックス内の検索</span><span class="sxs-lookup"><span data-stu-id="56d1d-168">Find in search box</span></span> | `Ctrl`+`F` |  
| <span data-ttu-id="56d1d-169">一番下にある [コンソール] にフォーカスを移動する</span><span class="sxs-lookup"><span data-stu-id="56d1d-169">Give focus to console at the bottom</span></span> | `Alt`+`Shift`+`I` |  
| <span data-ttu-id="56d1d-170">コンソールに DevTools を起動する</span><span class="sxs-lookup"><span data-stu-id="56d1d-170">Launch DevTools to Console</span></span> | `Ctrl`+`Shift`+`J` |  
| <span data-ttu-id="56d1d-171">ページを更新する</span><span class="sxs-lookup"><span data-stu-id="56d1d-171">Refresh the page</span></span> | `Ctrl`<span data-ttu-id="56d1d-172">+`Shift`+`F5`, `Ctrl`+</span><span class="sxs-lookup"><span data-stu-id="56d1d-172">+`Shift`+`F5`, `Ctrl`+</span></span>`R` |  

> [!NOTE]
> <span data-ttu-id="56d1d-173">デバッグ中にブレークポイントで一時停止している場合、**ページを更新** アクションが最初にランタイムを再開します。</span><span class="sxs-lookup"><span data-stu-id="56d1d-173">If you are debugging and paused at a breakpoint, the **Refresh the page** action resumes the runtime first.</span></span>  

## <span data-ttu-id="56d1d-174">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="56d1d-174">Getting in touch with the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="56d1d-175">フィードバックをお送りください。 Microsoft Edge \(EdgeHTML \) DevTools の改善にご協力ください。</span><span class="sxs-lookup"><span data-stu-id="56d1d-175">Please send your feedback to help improve the Microsoft Edge \(EdgeHTML\) DevTools for you!</span></span>  <span data-ttu-id="56d1d-176">ツール \(`F12` \) を開き、[[フィードバック の送信](#microsoft-edge-edgehtml-developer-tools)] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="56d1d-176">Simply open the tools \(`F12`\) and select the [Send feedback](#microsoft-edge-edgehtml-developer-tools) button.</span></span>  

<span data-ttu-id="56d1d-177">[Windows Insider][WindowsInsiderProgram] に加入して、[DevTools に搭載される最新機能][DevtoolsGuideEdgehtmlWhatsnew] をプレビューしてください。</span><span class="sxs-lookup"><span data-stu-id="56d1d-177">Become a [Windows Insider][WindowsInsiderProgram] to preview the [latest features coming to the DevTools][DevtoolsGuideEdgehtmlWhatsnew].</span></span>  <span data-ttu-id="56d1d-178">Windows フィードバック Hub アプリを使用して、一般的な Windows の提案や問題に関する情報を投稿、記録、追跡して、サポートを受けることができます。</span><span class="sxs-lookup"><span data-stu-id="56d1d-178">Use the Windows Feedback Hub app to post, up-vote, track and get support for general Windows suggestions and problems.</span></span>  

<!-- image links  -->  

<!--[ImageDevtoolsEdgehtml]: /microsoft-edge/devtools-guide/media/devtools.png "Microsoft Edge (EdgeHTML) DevTools"  -->  
<!--[ImageDevtoolsGuideEdgehtmlChooselocal]: /microsoft-edge/devtools-guide/media/chooser_local.png "DevTools app Local panel"  -->  
<!--[ImageDevtoolsGuideEdgehtmlRemote]: /microsoft-edge/devtools-guide/media/chooser_remote.png "DevTools app Remote panel"  -->  

<!-- links  -->  

[DevtoolsGuideEdgehtmlConsole]: /microsoft-edge/devtools-guide/console "コンソール"  
[DevtoolsGuideEdgehtmlDebugger]: /microsoft-edge/devtools-guide/debugger "デバッガー"  
[DevtoolsGuideEdgehtmlElements]: /microsoft-edge/devtools-guide/elements "要素"  
[DevtoolsGuideEdgehtmlEmulation]: /microsoft-edge/devtools-guide/emulation "エミュレーション"  
[DevtoolsGuideEdgehtmlMemory]: /microsoft-edge/devtools-guide/memory "メモリ"  
[DevtoolsGuideEdgehtmlNetwork]: /microsoft-edge/devtools-guide/network "ネットワーク"  
[DevtoolsGuideEdgehtmlPerformance]: /microsoft-edge/devtools-guide/performance "パフォーマンス"  
[DevtoolsGuideEdgehtmlServiceworkers]: /microsoft-edge/devtools-guide/service-workers "サービス ワーカー"  
[DevtoolsGuideEdgehtmlStorage]: /microsoft-edge/devtools-guide/storage "ストレージ"  
[DevtoolsGuideEdgehtmlWhatsnew]: /microsoft-edge/devtools-guide/whats-new "最新の Windows 10 更新プログラムの DevTools (EdgeHTML 18)"  
[DevtoolsProtocolEdgehtmlIndex]: /microsoft-edge/devtools-protocol/index "Microsoft Edge (EdgeHTML) DevTools プロトコル"  
[DevtoolsProtocolEdgehtmlClientsEdgePreview]: /microsoft-edge/devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview "Microsoft Edge の DevTools プレビュー - DevTools プロトコル クライアント"  
[HostingWebview]: /microsoft-edge/hosting/webview "Windows 10 アプリの WebView (EdgeHTML)"  
[PwasEdgehtmlIndex]: /microsoft-edge/progressive-web-apps-edgehtml/index "Windows でのプログレッシブ Web アプリ (EdgeHTML)"  

[MicrosoftStoreEdgeDevtoolsPreview]: https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj "Microsoft Edge DevTools プレビュー"  

[WindowsInsiderProgram]: https://insider.windows.com "Windows Insider Program"  

[BrowserstackEdgehtml]: https://www.browserstack.com/test-on-microsoft-edge-browser "無料の Microsoft Edge ブラウザー テスト | BrowserStack"  

[GithubMicrosoftChakracore]: https://github.com/Microsoft/ChakraCore "microsoft/ChakraCore | GitHub"  

[TypeScriptIndex]: https://www.typescriptlang.org "TypeScript"  
