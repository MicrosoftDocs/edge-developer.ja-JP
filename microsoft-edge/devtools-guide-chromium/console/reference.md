---
description: DevTools のコンソール UI のすべての機能と動作に関するMicrosoft Edge参照。
title: コンソールリファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/13/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: adc3f6c33d6e1a2f6c7db8336c5ab803e76c3307
ms.sourcegitcommit: 2e516a92272e38d8073603f860ae49f944718670
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "11483272"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->
# <a name="console-reference"></a><span data-ttu-id="0b5b0-104">コンソールリファレンス</span><span class="sxs-lookup"><span data-stu-id="0b5b0-104">Console reference</span></span>  

<span data-ttu-id="0b5b0-105">この記事は、DevTools コンソールに関連する機能Microsoft Edgeです。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-105">This article is a reference of features related to the Microsoft Edge DevTools Console.</span></span>  <span data-ttu-id="0b5b0-106">コンソールを使用してログに記録されたメッセージを表示し、JavaScript を実行する方法について既に理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-106">It assumes you're already familiar with using the Console to view logged messages and run JavaScript.</span></span>  <span data-ttu-id="0b5b0-107">表示されない場合は、[コンソールで [JavaScript][DevtoolsConsoleConsoleJavascript] を実行する方法を開始する] および [コンソールでのメッセージのログ記録の [開始] に移動します][DevtoolsConsoleConsoleLog]。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-107">If not, navigate to [Get started with running JavaScript in the Console][DevtoolsConsoleConsoleJavascript] and [Get started with logging messages in the Console][DevtoolsConsoleConsoleLog].</span></span>  

<span data-ttu-id="0b5b0-108">関数の API 参照を探している場合は、[コンソール API リファレンス] `console.log()` [に移動します][DevToolsConsoleApi]。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-108">If you're looking for the API reference on functions like `console.log()`, navigate to [Console API Reference][DevToolsConsoleApi].</span></span>  <span data-ttu-id="0b5b0-109">次のような関数の参照については、「 `monitorEvents()` コンソール ユーティリティ API [リファレンス」に移動します][DevToolsConsoleUtilities]。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-109">For the reference on functions like `monitorEvents()`, navigate to [Console Utilities API Reference][DevToolsConsoleUtilities].</span></span>  

## <a name="open-the-console"></a><span data-ttu-id="0b5b0-110">コンソールを開く</span><span class="sxs-lookup"><span data-stu-id="0b5b0-110">Open the Console</span></span>  

<span data-ttu-id="0b5b0-111">コンソールは **、上部ウィンドウ** の [ツールとして](#open-the-console-tool) 、またはドロワーで [ツールとして開く場合があります](#open-the-console-tool-in-the-drawer)。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-111">You may open the **Console** as a [tool in the upper pane](#open-the-console-tool) or as a [tool in the Drawer](#open-the-console-tool-in-the-drawer).</span></span>  

### <a name="open-the-console-tool"></a><span data-ttu-id="0b5b0-112">コンソール ツールを開く</span><span class="sxs-lookup"><span data-stu-id="0b5b0-112">Open the Console tool</span></span>  

<span data-ttu-id="0b5b0-113">`Control` + `Shift` + `J` \(Windows Linux\) または `Command` + `Option` + `J` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-113">Select `Control`+`Shift`+`J` \(Windows, Linux\) or `Command`+`Option`+`J` \(macOS\).</span></span>  

:::image type="complex" source="../media/console-hello-console.msft.png" alt-text="コンソール ツール" lightbox="../media/console-hello-console.msft.png":::
   <span data-ttu-id="0b5b0-115">コンソール**ツール**</span><span class="sxs-lookup"><span data-stu-id="0b5b0-115">The **Console** tool</span></span>  
:::image-end:::  

<span data-ttu-id="0b5b0-116">コマンド メニューから**コンソール ツール**を[開][DevtoolsCommandMenuIndex]くには、パネル バッジが横にある [コンソールの表示] コマンドを入力して `Console` 実行します。 \*\*\*\* \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="0b5b0-116">To open the **Console** tool from the [Command Menu][DevtoolsCommandMenuIndex], type `Console` and then run the **Show Console** command that has the **Panel** badge next to it.</span></span>  

:::image type="complex" source="../media/console-command-menu-show-console.msft.png" alt-text="コマンドを実行してコンソール ツールを表示する" lightbox="../media/console-command-menu-show-console.msft.png":::
   <span data-ttu-id="0b5b0-118">コマンドを実行してコンソール ツール **を表示** する</span><span class="sxs-lookup"><span data-stu-id="0b5b0-118">Run the command to display the **Console** tool</span></span>  
:::image-end:::  

### <a name="open-the-console-tool-in-the-drawer"></a><span data-ttu-id="0b5b0-119">ドロワーでコンソール ツールを開く</span><span class="sxs-lookup"><span data-stu-id="0b5b0-119">Open the Console tool in the Drawer</span></span>  

<span data-ttu-id="0b5b0-120">`Esc` **[DevTools \(** \) のカスタマイズと制御] を選択 `...` または選択し、[コンソール ドロワー**の表示] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-120">Select `Esc` or choose **Customize and control DevTools** \(`...`\) and then choose **Show console drawer**.</span></span>  

:::image type="complex" source="../media/console-elements-customize-control-devtools-show-console-drawer.msft.png" alt-text="コンソール ドロワーの表示" lightbox="../media/console-elements-customize-control-devtools-show-console-drawer.msft.png":::
   **<span data-ttu-id="0b5b0-122">コンソール ドロワーの表示</span><span class="sxs-lookup"><span data-stu-id="0b5b0-122">Show console drawer</span></span>**  
:::image-end:::  

<span data-ttu-id="0b5b0-123">[引き出し] が DevTools ウィンドウの下部に表示されます。コンソール ツール **が開** きます。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-123">The Drawer pops up at the bottom of your DevTools window, with the **Console** tool open.</span></span>  

:::image type="complex" source="../media/console-elements-console-drawer-hello-world.msft.png" alt-text="ドロワーのコンソール ツール" lightbox="../media/console-elements-console-drawer-hello-world.msft.png":::
   <span data-ttu-id="0b5b0-125">ドロ **ワー** のコンソール **ツール**</span><span class="sxs-lookup"><span data-stu-id="0b5b0-125">The **Console** tool in the **Drawer**</span></span>  
:::image-end:::  

<span data-ttu-id="0b5b0-126">[コマンド]**メニューから [** コンソール] ツールを[開][DevtoolsCommandMenuIndex]き、その横に [引き出し] バッジがある [コンソールの表示] コマンド `Console` を入力して実行します。 \*\*\*\* \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="0b5b0-126">To open the **Console** tool from the [Command Menu][DevtoolsCommandMenuIndex], type `Console` and then run the **Show Console** command that has the **Drawer** badge next to it.</span></span>  

:::image type="complex" source="../media/console-command-menu-show-console.msft.png" alt-text="コマンドを実行して、ドロワーに **Console** ツールを表示する" lightbox="../media/console-command-menu-show-console.msft.png":::
   <span data-ttu-id="0b5b0-128">コマンドを実行して、ドロワー **にコンソール** ツールを表示 **する**</span><span class="sxs-lookup"><span data-stu-id="0b5b0-128">Run the command to display the **Console** tool in the **Drawer**</span></span>  
:::image-end:::  

### <a name="open-console-settings"></a><span data-ttu-id="0b5b0-129">Open Console 設定</span><span class="sxs-lookup"><span data-stu-id="0b5b0-129">Open Console Settings</span></span>  

<span data-ttu-id="0b5b0-130">[**コンソール] メニュー設定**\( ![ [コンソール] 設定 ](../media/settings-button-icon.msft.png) \) ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-130">Choose the **Console Settings** \(![Console Settings icon](../media/settings-button-icon.msft.png)\) button.</span></span>  

:::image type="complex" source="../media/console-settings-group-similar-empty.msft.png" alt-text="コンソール 設定" lightbox="../media/console-settings-group-similar-empty.msft.png":::
   **<span data-ttu-id="0b5b0-132">コンソール 設定</span><span class="sxs-lookup"><span data-stu-id="0b5b0-132">Console Settings</span></span>**  
:::image-end:::  

<span data-ttu-id="0b5b0-133">次のリンクでは、各設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-133">The following links explain each setting.</span></span>  

*   [<span data-ttu-id="0b5b0-134">ネットワークを非表示にする</span><span class="sxs-lookup"><span data-stu-id="0b5b0-134">Hide network</span></span>](#hide-network-messages)  
*   [<span data-ttu-id="0b5b0-135">ログを保持する</span><span class="sxs-lookup"><span data-stu-id="0b5b0-135">Preserve log</span></span>](#persist-messages-across-page-loads)  
*   [<span data-ttu-id="0b5b0-136">選択したコンテキストのみ</span><span class="sxs-lookup"><span data-stu-id="0b5b0-136">Selected context only</span></span>](#filter-out-messages-from-different-contexts)  
*   [<span data-ttu-id="0b5b0-137">類似のグループ</span><span class="sxs-lookup"><span data-stu-id="0b5b0-137">Group similar</span></span>](#turn-off-message-grouping)  
*   [<span data-ttu-id="0b5b0-138">ログ XMLHttpRequests</span><span class="sxs-lookup"><span data-stu-id="0b5b0-138">Log XMLHttpRequests</span></span>](#log-xhr-and-fetch-requests)  
*   [<span data-ttu-id="0b5b0-139">熱心な評価</span><span class="sxs-lookup"><span data-stu-id="0b5b0-139">Eager evaluation</span></span>](#turn-off-eager-evaluation)  
*   [<span data-ttu-id="0b5b0-140">履歴からのオートコンプリート</span><span class="sxs-lookup"><span data-stu-id="0b5b0-140">Autocomplete from history</span></span>](#turn-off-autocomplete-from-history)  
<!--*   Evaluate triggers user activation  -->  
    
### <a name="open-the-console-sidebar"></a><span data-ttu-id="0b5b0-141">コンソール サイドバーを開く</span><span class="sxs-lookup"><span data-stu-id="0b5b0-141">Open the Console Sidebar</span></span>  

<span data-ttu-id="0b5b0-142">サイドバーを表示 **するには、[コンソール サイドバー**を **表示する** ]を選択します。(Show ![ console sidebar ](../media/show-console-sidebar-icon.msft.png) \)。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-142">To display the **Sidebar**, choose **Show console sidebar** \(![Show console sidebar](../media/show-console-sidebar-icon.msft.png)\).</span></span>  <span data-ttu-id="0b5b0-143">サイドバー **はフィルター** 処理に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-143">The **Sidebar** is helps you filter.</span></span>  

:::image type="complex" source="../media/console-sidebar-drawer-empty.msft.png" alt-text="コンソール サイドバー" lightbox="../media/console-sidebar-drawer-empty.msft.png":::
   **<span data-ttu-id="0b5b0-145">コンソール サイドバー</span><span class="sxs-lookup"><span data-stu-id="0b5b0-145">Console Sidebar</span></span>**  
:::image-end:::  

## <a name="view-messages"></a><span data-ttu-id="0b5b0-146">メッセージの表示</span><span class="sxs-lookup"><span data-stu-id="0b5b0-146">View messages</span></span>  

<span data-ttu-id="0b5b0-147">このセクションには、コンソールでのメッセージの表示方法を変更する機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-147">This section contains features that change how messages are presented in the Console.</span></span>  <span data-ttu-id="0b5b0-148">実践的なチュートリアルの場合は、[メッセージの表示] [に移動します][DevtoolsConsoleIndexInspectFilterInformationOnCurrentWebpage]。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-148">For a hands-on walkthrough, navigate to [View messages][DevtoolsConsoleIndexInspectFilterInformationOnCurrentWebpage].</span></span>  

### <a name="turn-off-message-grouping"></a><span data-ttu-id="0b5b0-149">メッセージのグループ化をオフにする</span><span class="sxs-lookup"><span data-stu-id="0b5b0-149">Turn off message grouping</span></span>  

<span data-ttu-id="0b5b0-150">コンソールの既定のメッセージ グループ化動作をオフ\*\*\*\* にするには[](#open-console-settings)、[コンソール] ウィンドウを開設定[類似グループ] の横にあるチェック ボックスを**オンにします**。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-150">To turn off the default message grouping behavior of the **Console**, [open Console Settings](#open-console-settings) and choose the checkbox next to **Group similar**.</span></span>  <span data-ttu-id="0b5b0-151">たとえば、[ [ログ XHR] と [フェッチ要求] に移動します](#log-xhr-and-fetch-requests)。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-151">For an example, navigate to [Log XHR and Fetch requests](#log-xhr-and-fetch-requests).</span></span>  

### <a name="log-xhr-and-fetch-requests"></a><span data-ttu-id="0b5b0-152">ログ XHR 要求とフェッチ要求</span><span class="sxs-lookup"><span data-stu-id="0b5b0-152">Log XHR and Fetch requests</span></span>  

<span data-ttu-id="0b5b0-153">すべての要求と要求をコンソールに記録するには、[コンソール] ウィンドウを開き設定 `XMLHttpRequest` `Fetch` **[ログ XMLHttpRequests]** の[横](#open-console-settings)\*\*\*\* にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-153">To log all `XMLHttpRequest` and `Fetch` requests to the **Console** as each happens, [open Console Settings](#open-console-settings) and choose the checkbox next to **Log XMLHttpRequests**.</span></span>  

:::image type="complex" source="../media/console-xhr-fetch.msft.png" alt-text="ログ XMLHttpRequest および Fetch 要求" lightbox="../media/console-xhr-fetch.msft.png":::
   <span data-ttu-id="0b5b0-155">ログ `XMLHttpRequest` と `Fetch` 要求</span><span class="sxs-lookup"><span data-stu-id="0b5b0-155">Log `XMLHttpRequest` and `Fetch` requests</span></span>  
:::image-end:::  

<span data-ttu-id="0b5b0-156">前の図のトップ メッセージには、コンソールの既定のグループ化動作が表示 **されます**。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-156">The top message in previous figure displays the default grouping behavior of the **Console**.</span></span>  <!--  In the following figure, the same log is displayed after you [turn off message grouping](#turn-off-message-grouping).  -->  

<!--  
> ##### Old Figure 9  
> How the logged `XMLHttpRequest` and `Fetch` requests look after ungrouping  
> :::image type="complex" source="../media/console-xhr-fetch-all.msft.png" alt-text="How the logged XMLHttpRequest and Fetch requests look after ungrouping" lightbox="../media/console-xhr-fetch-all.msft.png":::
>    How the logged XMLHttpRequest and Fetch requests look after ungrouping  
> :::image-end:::  
-->  

<!--todo: add example for ungrouping console items  -->  

### <a name="persist-messages-across-page-loads"></a><span data-ttu-id="0b5b0-157">ページの読み込み中にメッセージを保持する</span><span class="sxs-lookup"><span data-stu-id="0b5b0-157">Persist messages across page loads</span></span>  

<span data-ttu-id="0b5b0-158">新しい Web ページを読み込むと、既定のアクションによってコンソールがクリア **されます**。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-158">When you load a new webpage, the default action clears the **Console**.</span></span>  <span data-ttu-id="0b5b0-159">ページの読み込み時にメッセージを保持するには、[コンソール] 設定を開き、[ログの保持] の[横](#open-console-settings)にあるチェック ボックス**をオンにします**。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-159">To persist messages across page loads, [open Console Settings](#open-console-settings) and choose the checkbox next to **Preserve Log**.</span></span>  

### <a name="hide-network-messages"></a><span data-ttu-id="0b5b0-160">ネットワーク メッセージを非表示にする</span><span class="sxs-lookup"><span data-stu-id="0b5b0-160">Hide network messages</span></span>  

<span data-ttu-id="0b5b0-161">既定のアクションは、Microsoft Edgeメッセージをコンソールにログに記録**します**。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-161">The default action for Microsoft Edge is to logs network messages to the **Console**.</span></span>  <span data-ttu-id="0b5b0-162">次の図では、選択したメッセージはの HTTP 状態コードを表します `429` 。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-162">In the following figure, the chosen message represents an HTTP status code of `429`.</span></span>  

:::image type="complex" source="../media/console-show-network.msft.png" alt-text="コンソールの 429 メッセージ" lightbox="../media/console-show-network.msft.png":::
   <span data-ttu-id="0b5b0-164">コンソール `429` 内の **メッセージ**</span><span class="sxs-lookup"><span data-stu-id="0b5b0-164">A `429` message in the **Console**</span></span>  
:::image-end:::  

<span data-ttu-id="0b5b0-165">ネットワーク メッセージを非表示にするには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-165">To hide network messages, complete the following actions.</span></span>  

1.  <span data-ttu-id="0b5b0-166">[コンソール を開設定。](#open-console-settings)</span><span class="sxs-lookup"><span data-stu-id="0b5b0-166">[Open Console Settings](#open-console-settings).</span></span>  
1.  <span data-ttu-id="0b5b0-167">[ネットワークの非表示] の横にある **チェック ボックスをオンにします**。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-167">Choose the checkbox next to **Hide Network**.</span></span>  
    
## <a name="filter-messages"></a><span data-ttu-id="0b5b0-168">フィルター メッセージ</span><span class="sxs-lookup"><span data-stu-id="0b5b0-168">Filter messages</span></span>  

<span data-ttu-id="0b5b0-169">コンソールでメッセージをフィルター処理する多くの方法 **があります**。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-169">Many ways exist to filter out messages in the **Console**.</span></span>  

### <a name="filter-out-browser-messages"></a><span data-ttu-id="0b5b0-170">ブラウザー メッセージをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="0b5b0-170">Filter out browser messages</span></span>  

<span data-ttu-id="0b5b0-171">[コンソール サイドバーを開き](#open-the-console-sidebar)**、[# ユーザー**メッセージ] を選択して、Web ページの JavaScript から送信されたメッセージのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-171">[Open the Console Sidebar](#open-the-console-sidebar) and choose **# user messages** to only display messages that came from the JavaScript of the webpage.</span></span>  

:::image type="complex" source="../media/console-sidebar-drawer-user-messages.msft.png" alt-text="ユーザー メッセージの表示" lightbox="../media/console-sidebar-drawer-user-messages.msft.png":::
   <span data-ttu-id="0b5b0-173">ユーザー メッセージの表示</span><span class="sxs-lookup"><span data-stu-id="0b5b0-173">Display user messages</span></span>  
:::image-end:::  

### <a name="filter-by-log-level"></a><span data-ttu-id="0b5b0-174">ログ レベルでフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="0b5b0-174">Filter by log level</span></span>  

<span data-ttu-id="0b5b0-175">DevTools は、各メソッド `console.*` に 4 つの重大度レベルの 1 つを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-175">DevTools assigns each `console.*` method one of the four severity levels.</span></span>  

*   `Error`  
*   `Info`  
*   `Verbose`  
*   `Warning`  
    
<span data-ttu-id="0b5b0-176">たとえば、 `console.log()` グループ内ですが `Info` 、 `console.error()` グループ内 `Error` にあるとします。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-176">For example, `console.log()` is in the `Info` group, but `console.error()` is in the `Error` group.</span></span>  <span data-ttu-id="0b5b0-177">コンソール [API リファレンスでは][DevToolsConsoleApi] 、該当する各メソッドの重大度レベルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-177">The [Console API Reference][DevToolsConsoleApi] describes the severity level of each applicable method.</span></span>  <span data-ttu-id="0b5b0-178">ブラウザーがコンソールにログに記録するメッセージには、重大度レベルもあります。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-178">Every message that the browser logs to the Console has a severity level too.</span></span>  <span data-ttu-id="0b5b0-179">興味がないメッセージのレベルは非表示にできます。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-179">You may hide any level of messages that you're not interested in.</span></span>  <span data-ttu-id="0b5b0-180">たとえば、メッセージにのみ関心がある場合は、他の 3 つの `Error` グループを非表示にできます。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-180">For example, if you're only interested in `Error` messages, you may hide the other three groups.</span></span>  

<span data-ttu-id="0b5b0-181">メッセージをフィルター処理するには、[ログ レベル] **ドロップダウン** を選択し、[ `Verbose` 、 、 、 ] `Info` `Warning` を選択します `Error` 。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-181">To filter the messages, choose the **Log Levels** dropdown and choose `Verbose`, `Info`, `Warning`, or `Error`.</span></span>  

:::image type="complex" source="../media/console-log-level-default-levels.msft.png" alt-text="[ログ レベル] ドロップダウン" lightbox="../media/console-log-level-default-levels.msft.png":::
   <span data-ttu-id="0b5b0-183">[ **ログ レベル]** ドロップダウン</span><span class="sxs-lookup"><span data-stu-id="0b5b0-183">The **Log Levels** dropdown</span></span>  
:::image-end:::  

<span data-ttu-id="0b5b0-184">ログ レベルを使用してフィルター処理するには、コンソール[サイドバー](#open-the-console-sidebar)を開\*\*\*\* き、[エラー]、[**警告\*\*\*\*]、[情報**]、または [詳細] の順に**選択します**。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-184">To use the log level to filter, [open the Console Sidebar](#open-the-console-sidebar) and then choose **Errors**, **Warnings**, **Info**, or **Verbose**.</span></span>  

:::image type="complex" source="../media/console-sidebar-warnings.msft.png" alt-text="サイドバーを使用して警告を表示する" lightbox="../media/console-sidebar-warnings.msft.png":::
   <span data-ttu-id="0b5b0-186">サイドバーを使用して警告を表示する</span><span class="sxs-lookup"><span data-stu-id="0b5b0-186">Use the Sidebar to view warnings</span></span>  
:::image-end:::  

### <a name="filter-messages-by-url"></a><span data-ttu-id="0b5b0-187">URL でメッセージをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="0b5b0-187">Filter messages by URL</span></span>  

<span data-ttu-id="0b5b0-188">URL `url:` の後に URL を入力して、その URL から送信されたメッセージのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-188">Type `url:` followed by a URL to only view messages that came from that URL.</span></span>  <span data-ttu-id="0b5b0-189">入力後 `url:` 、DevTools は関連するすべての URL を表示します。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-189">After you type `url:`, DevTools displays all relevant URLs.</span></span>  <span data-ttu-id="0b5b0-190">ドメインも機能します。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-190">Domains also work.</span></span>  <span data-ttu-id="0b5b0-191">たとえば、メッセージをログに記録する場合は、これら 2 つのスクリプトの `https://example.com/a.js` `https://example.com/b.js` `url:https://example.com` メッセージに集中できます。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-191">For example, if `https://example.com/a.js` and `https://example.com/b.js` are logging messages, `url:https://example.com` allows you to focus on the messages from these two scripts.</span></span>  

:::image type="complex" source="../media/console-filter-text.msft.png" alt-text="URL フィルター" lightbox="../media/console-filter-text.msft.png":::
   <span data-ttu-id="0b5b0-193">URL フィルター</span><span class="sxs-lookup"><span data-stu-id="0b5b0-193">A URL filter</span></span>  
:::image-end:::  

<span data-ttu-id="0b5b0-194">URL からメッセージを非表示にする場合は `-url:` 、「.</span><span class="sxs-lookup"><span data-stu-id="0b5b0-194">To hide messages from a URL, type `-url:`.</span></span>  <span data-ttu-id="0b5b0-195">これは、負の URL フィルターです。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-195">It's a negative URL filter.</span></span>  

:::image type="complex" source="../media/console-negative-filter-text.msft.png" alt-text="URL に一致するメッセージをすべて非表示にする負の https://b.wal.co URL フィルター" lightbox="../media/console-negative-filter-text.msft.png":::
   <span data-ttu-id="0b5b0-197">URL に一致するメッセージをすべて非表示にする負の `https://b.wal.co` URL フィルター</span><span class="sxs-lookup"><span data-stu-id="0b5b0-197">A negative URL filter that hides all messages that match the `https://b.wal.co` URL</span></span>
:::image-end:::  

<span data-ttu-id="0b5b0-198">1 つの URL からのメッセージを表示するには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-198">To display messages from a single URL, complete the following actions.</span></span>  

1.  <span data-ttu-id="0b5b0-199">[コンソール サイドバーを開きます](#open-the-console-sidebar)。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-199">[Open the Console Sidebar](#open-the-console-sidebar).</span></span>  
1.  <span data-ttu-id="0b5b0-200">[# **ユーザー メッセージ] セクションを** 展開します。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-200">Expand the **# user messages** section.</span></span>  
1.  <span data-ttu-id="0b5b0-201">フォーカスするメッセージを含むスクリプトの URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-201">Choose the URL of the script that contains the messages on which you want to focus.</span></span>  
    
:::image type="complex" source="../media/console-filter-text-specified.msft.png" alt-text="ユーザーから送信されたメッセージを表示wp-ad.min.js" lightbox="../media/console-filter-text-specified.msft.png":::
   <span data-ttu-id="0b5b0-203">から来たメッセージを表示する</span><span class="sxs-lookup"><span data-stu-id="0b5b0-203">Display the messages that came from</span></span> `wp-ad.min.js`  
:::image-end:::  

### <a name="filter-out-messages-from-different-contexts"></a><span data-ttu-id="0b5b0-204">さまざまなコンテキストからのメッセージをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="0b5b0-204">Filter out messages from different contexts</span></span>  

<span data-ttu-id="0b5b0-205">Web ページに広告 \(ad\) が含まれるとします。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-205">Suppose that you have an advertisement \(ad\) on your webpage.</span></span>  <span data-ttu-id="0b5b0-206">広告はコンソールに埋め込まれている `<iframe>` ので、コンソールに多数のメッセージが生成 **されます**。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-206">The ad is embedded in an `<iframe>` and generates many messages in your **Console**.</span></span>  <span data-ttu-id="0b5b0-207">広告が別の[JavaScript](#choose-javascript-context)コンテキストで実行されている場合、メッセージを非表示にする[1](#open-console-settings)つの方法として、[コンソール 設定] を開き、[選択されたコンテキストのみ] の横にあるチェック ボックスを**オンにします**。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-207">Because the ad is running in a different [JavaScript context](#choose-javascript-context), one way to hide the messages is to [open Console Settings](#open-console-settings) and choose the checkbox next to **Selected Context Only**.</span></span>  

### <a name="filter-out-messages-that-dont-match-a-regular-expression-pattern"></a><span data-ttu-id="0b5b0-208">正規表現パターンに一致しないメッセージをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="0b5b0-208">Filter out messages that don't match a regular expression pattern</span></span>  

<span data-ttu-id="0b5b0-209">[フィルター] テキスト ボックスに正規表現を入力して、そのパターンに一致しないメッセージを `/[gm][ta][mi]/` フィルター処理します。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="0b5b0-209">Type a regular expression such as `/[gm][ta][mi]/` in the **Filter** textbox to filter out any messages that don't match that pattern.</span></span>  <span data-ttu-id="0b5b0-210">DevTools は、メッセージ テキストにパターンが見つかったか、メッセージがログに記録される原因となるスクリプトをチェックします。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-210">DevTools checks if the pattern is found in the message text or the script that caused the message to be logged.</span></span>  

:::image type="complex" source="../media/console-filter-regex.msft.png" alt-text="正規表現と一致しないメッセージをフィルター処理する" lightbox="../media/console-filter-regex.msft.png":::
   <span data-ttu-id="0b5b0-212">正規表現に一致しないメッセージを `/[gm][ta][mi]/` フィルター処理する</span><span class="sxs-lookup"><span data-stu-id="0b5b0-212">Filter out any messages that don't match the `/[gm][ta][mi]/` regex expression</span></span>  
:::image-end:::  

## <a name="run-javascript"></a><span data-ttu-id="0b5b0-213">JavaScript の実行</span><span class="sxs-lookup"><span data-stu-id="0b5b0-213">Run JavaScript</span></span>  

<span data-ttu-id="0b5b0-214">このセクションでは、コンソールでの JavaScript の実行に関連する機能について説明 **します**。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-214">This section contains features related to running JavaScript in the **Console**.</span></span>  <span data-ttu-id="0b5b0-215">実践的なチュートリアルの場合は、[JavaScript の実行 [] に移動します][DevtoolsConsoleConsoleJavascript]。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-215">For a hands-on walkthrough, navigate to [Run JavaScript][DevtoolsConsoleConsoleJavascript].</span></span>  

### <a name="rerun-expressions-from-history"></a><span data-ttu-id="0b5b0-216">履歴から式を再実行する</span><span class="sxs-lookup"><span data-stu-id="0b5b0-216">Rerun expressions from history</span></span>  

<span data-ttu-id="0b5b0-217">コンソール `Up Arrow` で前に実行した JavaScript 式の履歴を循環する場合に選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-217">Select `Up Arrow` to cycle through the history of JavaScript expressions that you ran earlier in the **Console**.</span></span>  <span data-ttu-id="0b5b0-218">この式 `Enter` を再度実行する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-218">Select `Enter` to run that expression again.</span></span>  

### <a name="watch-the-value-of-an-expression-in-real-time-with-live-expressions"></a><span data-ttu-id="0b5b0-219">Live Expression を使用して、式の値をリアルタイムで確認する</span><span class="sxs-lookup"><span data-stu-id="0b5b0-219">Watch the value of an expression in real time with Live Expressions</span></span>  

<span data-ttu-id="0b5b0-220">コンソールで同じ JavaScript 式を繰り\*\*\*\* 返し入力すると、Live 式の作成が簡単になる**場合があります**。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-220">If you find yourself typing the same JavaScript expression in the **Console** repeatedly, you may find it easier to create a **Live Expression**.</span></span>  <span data-ttu-id="0b5b0-221">Live **Expression を使用**すると、式を 1 回入力し、本体の上部にピン留め **します**。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-221">With **Live Expressions**, you type an expression once and then pin it to the top of your **Console**.</span></span>  <span data-ttu-id="0b5b0-222">式の値は、ほぼリアルタイムで更新されます。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-222">The value of the expression updates in near real time.</span></span>  <span data-ttu-id="0b5b0-223">[ライブ式 [を使用して JavaScript 式Real-Timeを監視する] に移動します][DevToolsConsoleLiveExpressions]。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-223">Navigate to [Watch JavaScript Expression Values In Real-Time With Live Expressions][DevToolsConsoleLiveExpressions].</span></span>  

### <a name="turn-off-eager-evaluation"></a><span data-ttu-id="0b5b0-224">熱心な評価をオフにする</span><span class="sxs-lookup"><span data-stu-id="0b5b0-224">Turn off Eager Evaluation</span></span>  

<span data-ttu-id="0b5b0-225">**熱心な評価** では、コンソールに JavaScript 式を入力すると、戻り値のプレビューが表示 **されます**。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-225">**Eager Evaluation** displays a preview of the return value as you type JavaScript expressions in the **Console**.</span></span>  <span data-ttu-id="0b5b0-226">戻り値のプレビューをオフにするには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-226">To turn off the return value previews, complete the following actions.</span></span>  

1.  <span data-ttu-id="0b5b0-227">[コンソール を開設定。](#open-console-settings)</span><span class="sxs-lookup"><span data-stu-id="0b5b0-227">[Open Console Settings](#open-console-settings).</span></span>  
1.  <span data-ttu-id="0b5b0-228">[熱心な評価] の横にある **チェック ボックスをオフにします**。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-228">Remove the checkbox next to **Eager Evaluation**.</span></span>  
    
### <a name="turn-off-autocomplete-from-history"></a><span data-ttu-id="0b5b0-229">履歴からオートコンプリートをオフにする</span><span class="sxs-lookup"><span data-stu-id="0b5b0-229">Turn off autocomplete from history</span></span>  

<span data-ttu-id="0b5b0-230">式を入力すると、コンソールのオートコンプリート ポップアップ ウィンドウに、前\*\*\*\* に実行した式が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-230">As you type out an expression, the autocomplete popup window for the **Console** displays expressions that you ran earlier.</span></span>  <span data-ttu-id="0b5b0-231">式には、文字があらかじめ付 `>` けされています。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-231">The expressions are pre-pended with the `>` character.</span></span>  <span data-ttu-id="0b5b0-232">履歴からの式の表示を停止するには[](#open-console-settings)、[コンソール] 設定を開き、[履歴からオートコンプリート] チェック ボックスの横にあるチェック ボックス**をオフ**にします。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-232">To stop displaying expressions from your history, [open Console Settings](#open-console-settings) and remove the checkbox next to **Autocomplete From History** checkbox.</span></span>  

> [!NOTE]
> <span data-ttu-id="0b5b0-233">次の図では、 `document.querySelector('a')` `document.querySelector('img')` 前に評価された式を示します。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-233">In the following figure, `document.querySelector('a')` and `document.querySelector('img')` are expressions that were evaluated earlier.</span></span>  

:::image type="complex" source="../media/console-filter-text-autofilter-history.msft.png" alt-text="オートコンプリートのポップアップ メニューには、履歴の式が表示されます。" lightbox="../media/console-filter-text-autofilter-history.msft.png":::
   <span data-ttu-id="0b5b0-235">オートコンプリートのポップアップ メニューには、履歴の式が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-235">The autocomplete popup menu displays expressions from history</span></span>  
:::image-end:::  

### <a name="choose-javascript-context"></a><span data-ttu-id="0b5b0-236">JavaScript コンテキストの選択</span><span class="sxs-lookup"><span data-stu-id="0b5b0-236">Choose JavaScript context</span></span>  

<span data-ttu-id="0b5b0-237">**JavaScript Context**ドロップダウンの既定のオプションは**top**で、[][MdnDocsGlossaryBrowsingContext]メイン Web ページの閲覧コンテキストを表します。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-237">The default option for the **JavaScript Context** dropdown is **top**, which represents the [browsing context][MdnDocsGlossaryBrowsingContext] of the main webpage.</span></span>  

:::image type="complex" source="../media/console-dom-level-top.msft.png" alt-text="[JavaScript コンテキスト] ドロップダウン" lightbox="../media/console-dom-level-top.msft.png":::
   <span data-ttu-id="0b5b0-239">**[JavaScript コンテキスト] ドロップダウン**</span><span class="sxs-lookup"><span data-stu-id="0b5b0-239">The **JavaScript Context** dropdown</span></span>  
:::image-end:::  

<span data-ttu-id="0b5b0-240">Web ページに広告が埋め込まれているとします `<iframe>` 。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-240">Suppose you have an ad on your webpage embedded in an `<iframe>`.</span></span>  <span data-ttu-id="0b5b0-241">JavaScript を実行して広告の DOM を調整する場合。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-241">You want to run JavaScript to tweak the DOM of the ad.</span></span>  <span data-ttu-id="0b5b0-242">最初に、[JavaScript コンテキスト] ドロップダウンから広告の参照 **コンテキストを選択** します。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-242">First, choose the browsing context of the ad from the **JavaScript Context** dropdown.</span></span>  

:::image type="complex" source="../media/console-dom-level-multiple.msft.png" alt-text="別の JavaScript コンテキストを選択する" lightbox="../media/console-dom-level-multiple.msft.png":::
   <span data-ttu-id="0b5b0-244">別の JavaScript コンテキストを選択する</span><span class="sxs-lookup"><span data-stu-id="0b5b0-244">Choose a different JavaScript context</span></span>  
:::image-end:::  

## <a name="clear-the-console"></a><span data-ttu-id="0b5b0-245">コンソールをクリアする</span><span class="sxs-lookup"><span data-stu-id="0b5b0-245">Clear the Console</span></span>  

<span data-ttu-id="0b5b0-246">コンソールをクリア **するには**、次のワークフローを完了します。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-246">To clear the **Console**, complete any of the following workflows.</span></span>  

*   <span data-ttu-id="0b5b0-247">[Clear **Console** \( ![ Clear Console ](../media/clear-console-button-icon.msft.png) \) ] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-247">Choose the **Clear Console** \(![Clear Console](../media/clear-console-button-icon.msft.png)\) button.</span></span>  
*   <span data-ttu-id="0b5b0-248">メッセージにカーソルを置き、コンテキスト メニュー \(右クリック\) を開き、[コンソールのクリア] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-248">Hover on a message, open the contextual menu \(right-click\), and choose **Clear Console**.</span></span>  
*   <span data-ttu-id="0b5b0-249">コンソール `clear()` に入力 **し、 を** 選択します `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-249">Enter `clear()` in the **Console** and select `Enter`.</span></span>  
*   <span data-ttu-id="0b5b0-250">Web `console.clear()` ページの JavaScript から実行します。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-250">Run `console.clear()` from the JavaScript for your webpage.</span></span>  
*   <span data-ttu-id="0b5b0-251">コンソール `Control` + `L` がフォーカス**されている間**に選択します。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-251">Select `Control`+`L` while the **Console** is in focus.</span></span>  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="0b5b0-252">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="0b5b0-252">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleApi]: ./api.md "コンソール API リファレンス |Microsoft Docs"  
[DevtoolsConsoleConsoleLog]: ./console-log.md "コンソール ツール でメッセージをログに記録|Microsoft Docs"  
[DevtoolsConsoleConsoleJavascript]: ./console-javascript.md "JavaScript 環境としてのコンソール |Microsoft Docs"  
[DevtoolsConsoleIndex]: .index.md "コンソール ウィンドウを使用|Microsoft Docs"  
[DevtoolsConsoleIndexInspectFilterInformationOnCurrentWebpage]: ./index.md#inspect-and-filter-information-on-the-current-webpage "現在の Web ページ の情報を検査してフィルター処理|Microsoft Docs"  
[DevtoolsConsoleLiveExpressions]: ./live-expressions.md "Live 式を使用して JavaScript の変更を監視|Microsoft Docs"  
[DevtoolsConsoleUtilities]: ./utilities.md "コンソール ユーティリティ API リファレンス |Microsoft Docs"  

[DevtoolsCommandMenuIndex]: ../command-menu/index.md "[DevTools コマンド] メニューの [Microsoft Edgeを使用してコマンドを実行|Microsoft Docs"  

[MdnDocsGlossaryBrowsingContext]: https://developer.mozilla.org/docs/Glossary/Browsing_context "参照コンテキスト |MDN"  

> [!NOTE]
> <span data-ttu-id="0b5b0-262">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-262">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="0b5b0-263">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/console/reference) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-263">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="0b5b0-265">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="0b5b0-265">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
