---
description: Microsoft Edge 開発者ツールについて理解する
title: Microsoft Edge 開発者ツール
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/20/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: edgehtml
keywords: microsoft edge、web 開発、f12 ツール、devtools
experimental: false
experiment_id: 51fe4b97-3e55-41
ms.openlocfilehash: 3aee2ab67c6e703a0a31b58b5bf985a23fcbb481
ms.sourcegitcommit: b88d2a55a59db8373ff2bac275d3730977bf19c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2020
ms.locfileid: "10986221"
---
# <span data-ttu-id="58800-104">Microsoft Edge 開発者ツール</span><span class="sxs-lookup"><span data-stu-id="58800-104">Microsoft Edge Developer Tools</span></span>  

> [!NOTE]
> <span data-ttu-id="58800-105">Microsoft Edge の DevTools は、web 開発者が web サイトを構築およびテストするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="58800-105">The Microsoft Edge DevTools help web developers build and test websites.</span></span>  <span data-ttu-id="58800-106">作成ツールを誤って開いた場合は、そのまま押して `F12` 閉じます。</span><span class="sxs-lookup"><span data-stu-id="58800-106">If you accidentally opened the DevTools, just press `F12` to close.</span></span>  

<span data-ttu-id="58800-107">Microsoft Edge の DevTools は、新しいフロントエンドワークフローに最適化された[オープンソース](https://github.com/Microsoft/ChakraCore)を使用した[TypeScript](https://www.typescriptlang.org/)で構築され、microsoft Store で[スタンドアロンの Windows 10 アプリ](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj)として利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="58800-107">The Microsoft Edge DevTools are built with [TypeScript](https://www.typescriptlang.org/), powered by [open source](https://github.com/Microsoft/ChakraCore), optimized for modern front-end workflows, and now available as a [standalone Windows 10 app](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj) in the Microsoft Store!</span></span>

<span data-ttu-id="58800-108">最新機能の詳細については、「 [*Windows 10 の最新の更新プログラム (EdgeHTML 17) での Devtools」*](./devtools-guide/whats-new.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58800-108">For more on the latest features, check out [*DevTools in the latest update of Windows 10 (EdgeHTML 17)*](./devtools-guide/whats-new.md).</span></span>

## <span data-ttu-id="58800-109">コア ツール</span><span class="sxs-lookup"><span data-stu-id="58800-109">Core tools</span></span>

![Microsoft Edge DevTools](./devtools-guide/media/devtools.png)

<span data-ttu-id="58800-111">Microsoft Edge の DevTools には以下のものがあります。</span><span class="sxs-lookup"><span data-stu-id="58800-111">The Microsoft Edge DevTools include:</span></span>

 - <span data-ttu-id="58800-112">HTML と CSS の編集、アクセシビリティプロパティの検査、イベントリスナーの表示、DOM 変異のブレークポイントの設定を行うための [**要素**](./devtools-guide/elements.md) パネル</span><span class="sxs-lookup"><span data-stu-id="58800-112">An [**Elements**](./devtools-guide/elements.md) panel to edit HTML and CSS, inspect accessibility properties, view event listeners, and set DOM mutation breakpoints</span></span>
 - <span data-ttu-id="58800-113">ログメッセージを表示してフィルター処理し、JavaScript オブジェクトと DOM ノードを検査し、選択したウィンドウまたはフレームのコンテキストで JavaScript を実行する[**本体**](./devtools-guide/console.md)</span><span class="sxs-lookup"><span data-stu-id="58800-113">A [**Console**](./devtools-guide/console.md) to view and filter log messages, inspect JavaScript objects and DOM nodes, and run JavaScript in the context of the selected window or frame</span></span>
 - <span data-ttu-id="58800-114">コードをステップ実行して、ウォッチとブレークポイントを設定し、コードをリアルタイムで編集し、web ストレージと cookie キャッシュを検査する[**デバッガー**](./devtools-guide/debugger.md)</span><span class="sxs-lookup"><span data-stu-id="58800-114">A [**Debugger**](./devtools-guide/debugger.md) to step through code, set watches and breakpoints, live edit your code, and inspect your web storage and cookie caches</span></span>
 - <span data-ttu-id="58800-115">ネットワークとブラウザーのキャッシュから要求と応答を監視および検査するための [**ネットワーク**](./devtools-guide/network.md) パネル</span><span class="sxs-lookup"><span data-stu-id="58800-115">A [**Network**](./devtools-guide/network.md) panel to monitor and inspect requests and responses from the network and browser cache</span></span> 
 - <span data-ttu-id="58800-116">サイトで必要な時間とシステムリソースをプロファイルするための [**パフォーマンス**](./devtools-guide/performance.md) パネル</span><span class="sxs-lookup"><span data-stu-id="58800-116">A [**Performance**](./devtools-guide/performance.md) panel to profile the time and system resources required by your site</span></span>
 - <span data-ttu-id="58800-117">メモリリソースの使用を測定し、コード実行のさまざまな状態でヒープスナップショットを比較するための [**メモリ**](./devtools-guide/memory.md) パネル</span><span class="sxs-lookup"><span data-stu-id="58800-117">A [**Memory**](./devtools-guide/memory.md) panel to measure your use of memory resources and compare heap snapshots at different states of code execution</span></span>
 - <span data-ttu-id="58800-118">さまざまなブラウザープロファイル、画面解像度、GPS 位置座標を使ってサイトをテストする [**エミュレーション**](./devtools-guide/emulation.md) パネル</span><span class="sxs-lookup"><span data-stu-id="58800-118">An [**Emulation**](./devtools-guide/emulation.md) panel to test your site with different browser profiles, screen resolutions, and GPS location coordinates</span></span>

<span data-ttu-id="58800-119">[フィードバックと機能のリクエストを](#getting-in-touch-with-the-microsoft-edge-devtools-team)送信してください。</span><span class="sxs-lookup"><span data-stu-id="58800-119">Please keep sending your [feedback and feature requests](#getting-in-touch-with-the-microsoft-edge-devtools-team).</span></span>

> [!TIP]
> <span data-ttu-id="58800-120">**[どのブラウザーからでも、Microsoft edge で無料でテスト](https://developer.microsoft.com/microsoft-edge/tools/remote/)** できます。 [browserstack](https://www.browserstack.com/test-on-microsoft-edge-browser#live-cloud) と提携して、microsoft edge で無料のライブおよび自動テストを提供します。</span><span class="sxs-lookup"><span data-stu-id="58800-120">**[Test on Microsoft Edge free from any browser](https://developer.microsoft.com/microsoft-edge/tools/remote/)**: We partnered with [BrowserStack](https://www.browserstack.com/test-on-microsoft-edge-browser#live-cloud) to provide free live and automated testing on Microsoft Edge.</span></span>

## <span data-ttu-id="58800-121">Microsoft ストア アプリ</span><span class="sxs-lookup"><span data-stu-id="58800-121">Microsoft Store app</span></span>

<span data-ttu-id="58800-122">**Microsoft Edge DevTools**は、ブラウザー内 () のツールエクスペリエンスに加えて、 [microsoft Store からスタンドアロンの Windows 10 アプリ](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab)として[プレビューできるようになりました](./devtools-guide/whats-new.md) `F12` 。</span><span class="sxs-lookup"><span data-stu-id="58800-122">The **Microsoft Edge DevTools** are [now available for preview](./devtools-guide/whats-new.md) as a standalone [Windows 10 app from the Microsoft Store](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab), in addition to the in-browser (`F12`) tooling experience.</span></span> <span data-ttu-id="58800-123">ストア バージョンでは、ローカルとリモートのページ　ターゲットを開くために [*セレクター*] パネルが表示されます。これには、DevTools インスタンス間で簡単に切り替えられるようにタブ レイアウトが用意されています。</span><span class="sxs-lookup"><span data-stu-id="58800-123">With the store version comes a *chooser* panel for attaching to open local and remote page targets and a tabbed layout for easy switching between DevTools instances.</span></span>

### <span data-ttu-id="58800-124">ローカル デバッグ</span><span class="sxs-lookup"><span data-stu-id="58800-124">Local debugging</span></span>

<span data-ttu-id="58800-125">ページをローカルでデバッグするには、 *Microsoft Edge DevTools* アプリを起動するだけです。</span><span class="sxs-lookup"><span data-stu-id="58800-125">To debug a page locally, simply launch the *Microsoft Edge DevTools* app.</span></span> <span data-ttu-id="58800-126">セレクターの **ローカル** パネルには、開いている [Edge browser] タブ、実行中の [pwas](./progressive-web-apps-edgehtml/index.md) (*WWAHost.exe* プロセス)、 [webview](./webview.md) コントロールなど、アクティブなすべての EdgeHTML コンテンツプロセスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="58800-126">The **Local** panel of the chooser will display all of the active EdgeHTML content processes, including open Edge browser tabs, running [PWAs](./progressive-web-apps-edgehtml/index.md) (*WWAHost.exe* processes), and [webview](./webview.md) controls.</span></span> <span data-ttu-id="58800-127">目的のターゲットをクリックして、DevTools の新しいタブインスタンスを添付して開きます。</span><span class="sxs-lookup"><span data-stu-id="58800-127">Click on your desired target to attach and open a new tab instance of the DevTools.</span></span>

![DevTools アプリ ローカル パネル](./devtools-guide/media/chooser_local.png)

### <span data-ttu-id="58800-129">リモート デバッグ</span><span class="sxs-lookup"><span data-stu-id="58800-129">Remote debugging</span></span>

<span data-ttu-id="58800-130">*Microsoft Edge devtools*アプリは、新しくリリースされた[**devtools プロトコル**](./devtools-protocol/index.md)を使ってリモートコンピューター上のページをデバッグするための基本的なサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="58800-130">The *Microsoft Edge DevTools* app introduces basic support for debugging pages on a remote machine via our newly released [**DevTools Protocol**](./devtools-protocol/index.md).</span></span> <span data-ttu-id="58800-131">このリリースでは、 [**デバッガー**](./devtools-guide/debugger.md) パネルのマイナスキャッシュ検査 (Web Storage、Service Worker、cache API、IndexedDB の場合) へのリモートアクセスが可能になります。</span><span class="sxs-lookup"><span data-stu-id="58800-131">With this release comes remote access to core funtionality in the [**Debugger**](./devtools-guide/debugger.md) panel, minus cache inspection (for Web storage, Service worker, Cache API, and IndexedDB).</span></span> <span data-ttu-id="58800-132">リモートデバッグは、*デスクトップ*ホストを実行している*Microsoft Edge*に限定され、将来のリリースで使用される他の EdgeHTML ホストと Windows 10 デバイスをサポートします。</span><span class="sxs-lookup"><span data-stu-id="58800-132">Remote debugging is limited to *Microsoft Edge* running *desktop* hosts, with support for other EdgeHTML hosts and Windows 10 devices coming in future releases.</span></span>

<span data-ttu-id="58800-133">始めるには、[*Microsoft Edge DevTools*](./devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview) の [DevTools プロトコル](./devtools-protocol/index.md) ドキュメントにあるセクションを確認してください。</span><span class="sxs-lookup"><span data-stu-id="58800-133">To get started, check out the [*Microsoft Edge DevTools*](./devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview) section of the [DevTools Protocol](./devtools-protocol/index.md) docs.</span></span>

![DevTools アプリのリモート パネル](./devtools-guide/media/chooser_remote.png)

## <span data-ttu-id="58800-135">一般的なショートカット</span><span class="sxs-lookup"><span data-stu-id="58800-135">General Shortcuts</span></span>

<span data-ttu-id="58800-136">これらのショートカットは、メインの [DevTools] ウィンドウを制御するか、すべてのツールで動作します。</span><span class="sxs-lookup"><span data-stu-id="58800-136">These shortcuts control the main DevTools window and/or work across all tools.</span></span>

<span data-ttu-id="58800-137">操作</span><span class="sxs-lookup"><span data-stu-id="58800-137">Action</span></span> | <span data-ttu-id="58800-138">ショートカット</span><span class="sxs-lookup"><span data-stu-id="58800-138">Shortcut</span></span>
:------------ | :-------------
<span data-ttu-id="58800-139">DevTools の表示/非表示 (最後に表示したパネルに表示されます)</span><span class="sxs-lookup"><span data-stu-id="58800-139">Show/Hide DevTools (opens to last viewed panel)</span></span> | <span data-ttu-id="58800-140">F12、Ctrl + Shift + I</span><span class="sxs-lookup"><span data-stu-id="58800-140">F12, Ctrl+Shift+I</span></span>
<span data-ttu-id="58800-141">ドッキングの切り替え (ドッキング/ボトム/右)</span><span class="sxs-lookup"><span data-stu-id="58800-141">Toggle docking (Undock/Bottom/Right)</span></span> | <span data-ttu-id="58800-142">Ctrl + Shift + D</span><span class="sxs-lookup"><span data-stu-id="58800-142">Ctrl+Shift+D</span></span> 
<span data-ttu-id="58800-143">デバッガーで編集不可の HTML ソース コードを表示する</span><span class="sxs-lookup"><span data-stu-id="58800-143">Show non-editable HTML source code in Debugger</span></span> | <span data-ttu-id="58800-144">Ctrl + U</span><span class="sxs-lookup"><span data-stu-id="58800-144">Ctrl+U</span></span>
<span data-ttu-id="58800-145">他のツールの下部にあるコンソールの表示/非表示</span><span class="sxs-lookup"><span data-stu-id="58800-145">Show/hide Console at the bottom of any other tool</span></span>  | <span data-ttu-id="58800-146">Ctrl +**\`**</span><span class="sxs-lookup"><span data-stu-id="58800-146">Ctrl+**\`**</span></span>
<span data-ttu-id="58800-147">要素に切り替える (DOM Explorer)</span><span class="sxs-lookup"><span data-stu-id="58800-147">Switch to Elements (DOM Explorer)</span></span> | <span data-ttu-id="58800-148">Ctrl + 1</span><span class="sxs-lookup"><span data-stu-id="58800-148">Ctrl+1</span></span>
<span data-ttu-id="58800-149">コンソールに切り替える</span><span class="sxs-lookup"><span data-stu-id="58800-149">Switch to Console</span></span> |  <span data-ttu-id="58800-150">Ctrl + 2</span><span class="sxs-lookup"><span data-stu-id="58800-150">Ctrl+2</span></span>
<span data-ttu-id="58800-151">デバッガーに切り替える</span><span class="sxs-lookup"><span data-stu-id="58800-151">Switch to Debugger</span></span> | <span data-ttu-id="58800-152">Ctrl + 3</span><span class="sxs-lookup"><span data-stu-id="58800-152">Ctrl+3</span></span>
<span data-ttu-id="58800-153">ネットワークに切り替える</span><span class="sxs-lookup"><span data-stu-id="58800-153">Switch to Network</span></span> | <span data-ttu-id="58800-154">Ctrl + 4</span><span class="sxs-lookup"><span data-stu-id="58800-154">Ctrl+4</span></span>
<span data-ttu-id="58800-155">パフォーマンスに切り替える</span><span class="sxs-lookup"><span data-stu-id="58800-155">Switch to Performance</span></span> | <span data-ttu-id="58800-156">Ctrl + 5</span><span class="sxs-lookup"><span data-stu-id="58800-156">Ctrl+5</span></span>
<span data-ttu-id="58800-157">メモリに切り替える</span><span class="sxs-lookup"><span data-stu-id="58800-157">Switch to Memory</span></span> | <span data-ttu-id="58800-158">Ctrl + 6</span><span class="sxs-lookup"><span data-stu-id="58800-158">Ctrl+6</span></span>
<span data-ttu-id="58800-159">エミュレーションに切り替える</span><span class="sxs-lookup"><span data-stu-id="58800-159">Switch to Emulation</span></span> | <span data-ttu-id="58800-160">Ctrl + 7</span><span class="sxs-lookup"><span data-stu-id="58800-160">Ctrl+7</span></span>
<span data-ttu-id="58800-161">ヘルプ ドキュメント</span><span class="sxs-lookup"><span data-stu-id="58800-161">Help Document</span></span> | <span data-ttu-id="58800-162">F1</span><span class="sxs-lookup"><span data-stu-id="58800-162">F1</span></span>
<span data-ttu-id="58800-163">次のツール</span><span class="sxs-lookup"><span data-stu-id="58800-163">Next tool</span></span> | <span data-ttu-id="58800-164">Ctrl + F6</span><span class="sxs-lookup"><span data-stu-id="58800-164">Ctrl+F6</span></span>
<span data-ttu-id="58800-165">前のツール</span><span class="sxs-lookup"><span data-stu-id="58800-165">Previous tool</span></span> | <span data-ttu-id="58800-166">Ctrl + Shift + F6</span><span class="sxs-lookup"><span data-stu-id="58800-166">Ctrl+Shift+F6</span></span>
<span data-ttu-id="58800-167">前のツール (履歴から)</span><span class="sxs-lookup"><span data-stu-id="58800-167">Previous tool (from history)</span></span> | <span data-ttu-id="58800-168">Ctrl + Shift + [</span><span class="sxs-lookup"><span data-stu-id="58800-168">Ctrl+Shift+[</span></span>
<span data-ttu-id="58800-169">次のツール (履歴から)</span><span class="sxs-lookup"><span data-stu-id="58800-169">Next tool (from history)</span></span> | <span data-ttu-id="58800-170">Ctrl + Shift +]</span><span class="sxs-lookup"><span data-stu-id="58800-170">Ctrl+Shift+]</span></span>
<span data-ttu-id="58800-171">次のサブフレーム</span><span class="sxs-lookup"><span data-stu-id="58800-171">Next Subframe</span></span>    | <span data-ttu-id="58800-172">F6</span><span class="sxs-lookup"><span data-stu-id="58800-172">F6</span></span>
<span data-ttu-id="58800-173">前のサブフレーム</span><span class="sxs-lookup"><span data-stu-id="58800-173">Previous Subframe</span></span> | <span data-ttu-id="58800-174">Shift + F6</span><span class="sxs-lookup"><span data-stu-id="58800-174">Shift+F6</span></span>
<span data-ttu-id="58800-175">[検索] ボックス内の次の一致</span><span class="sxs-lookup"><span data-stu-id="58800-175">Next match in Search box</span></span> | <span data-ttu-id="58800-176">F3</span><span class="sxs-lookup"><span data-stu-id="58800-176">F3</span></span>
<span data-ttu-id="58800-177">[検索] ボックス内の前の一致</span><span class="sxs-lookup"><span data-stu-id="58800-177">Previous match in Search box</span></span> | <span data-ttu-id="58800-178">Shift + F3</span><span class="sxs-lookup"><span data-stu-id="58800-178">Shift+F3</span></span>
<span data-ttu-id="58800-179">[検索] ボックス内の検索</span><span class="sxs-lookup"><span data-stu-id="58800-179">Find in search box</span></span> | <span data-ttu-id="58800-180">Ctrl + F</span><span class="sxs-lookup"><span data-stu-id="58800-180">Ctrl+F</span></span>
<span data-ttu-id="58800-181">一番下にある [コンソール] にフォーカスを移動する</span><span class="sxs-lookup"><span data-stu-id="58800-181">Give focus to console at the bottom</span></span> | <span data-ttu-id="58800-182">Alt + Shift + I</span><span class="sxs-lookup"><span data-stu-id="58800-182">Alt+Shift+I</span></span>
<span data-ttu-id="58800-183">ドッキング/ドッキング解除ツール (ドッキングの切り替え)</span><span class="sxs-lookup"><span data-stu-id="58800-183">Dock/undock tools (toggle docking)</span></span> | <span data-ttu-id="58800-184">Ctrl + P</span><span class="sxs-lookup"><span data-stu-id="58800-184">Ctrl+P</span></span>  
<span data-ttu-id="58800-185">コンソールに DevTools を起動する</span><span class="sxs-lookup"><span data-stu-id="58800-185">Launch DevTools to Console</span></span> | <span data-ttu-id="58800-186">Ctrl + Shift + J</span><span class="sxs-lookup"><span data-stu-id="58800-186">Ctrl+Shift+J</span></span>
<span data-ttu-id="58800-187">ページを最新の情報に更新してください。</span><span class="sxs-lookup"><span data-stu-id="58800-187">Refresh the page.</span></span> <span data-ttu-id="58800-188">**注:** ブレークポイントでデバッグと一時停止を行っている場合は、まず実行を再開します。</span><span class="sxs-lookup"><span data-stu-id="58800-188">**Note:** if you're debugging and paused at a breakpoint, this resumes execution first.</span></span> | <span data-ttu-id="58800-189">Ctrl + Shift + F5 または Ctrl + R</span><span class="sxs-lookup"><span data-stu-id="58800-189">Ctrl+Shift+F5 or Ctrl+R</span></span>

## <span data-ttu-id="58800-190">Microsoft Edge DevTools チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="58800-190">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](./devtools-guide-chromium/includes/contact-devtools-team-note.md)]  
