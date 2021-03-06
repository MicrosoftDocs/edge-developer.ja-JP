---
description: Microsoft Edge DevTools のコンソール UI に関連するすべての機能と動作に関する包括的なリファレンス。
title: コンソールリファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 1aed46486240dea19420e8b7cb52b6758f1f528b
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399163"
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

# <a name="console-reference"></a><span data-ttu-id="5a9c3-104">コンソールリファレンス</span><span class="sxs-lookup"><span data-stu-id="5a9c3-104">Console reference</span></span>  

<span data-ttu-id="5a9c3-105">このページは、Microsoft Edge DevTools コンソールに関連する機能の参照です。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-105">This page is a reference of features related to the Microsoft Edge DevTools Console.</span></span>  <span data-ttu-id="5a9c3-106">コンソールを使用してログに記録されたメッセージを表示し、JavaScript を実行する方法について既に理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-106">It assumes that you are already familiar with using the Console to view logged messages and run JavaScript.</span></span>  <span data-ttu-id="5a9c3-107">ない場合は、[コンソールでの [JavaScript][DevToolsConsoleJavascript] の実行の開始] および [コンソールでのログ メッセージの開始 [] に移動します][DevToolsConsoleLog]。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-107">If not, navigate to [Get Started With Running JavaScript In The Console][DevToolsConsoleJavascript] and [Get Started With Logging Messages In The Console][DevToolsConsoleLog].</span></span>  

<span data-ttu-id="5a9c3-108">関数の API 参照を探している場合は、[コンソール API リファレンス] `console.log()` [に移動します][DevToolsConsoleApi]。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-108">If you are looking for the API reference on functions like `console.log()`, navigate to [Console API Reference][DevToolsConsoleApi].</span></span>  <span data-ttu-id="5a9c3-109">次のような関数の参照については、「 `monitorEvents()` コンソール ユーティリティ API [リファレンス」に移動します][DevToolsConsoleUtilities]。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-109">For the reference on functions like `monitorEvents()`, navigate to [Console Utilities API Reference][DevToolsConsoleUtilities].</span></span>  

## <a name="open-the-console"></a><span data-ttu-id="5a9c3-110">コンソールを開く</span><span class="sxs-lookup"><span data-stu-id="5a9c3-110">Open the Console</span></span>  

<span data-ttu-id="5a9c3-111">コンソールは **、上部ウィンドウ** の [ツールとして](#open-the-console-tool) 、またはドロワーで [ツールとして開く場合があります](#open-the-console-tool-in-the-drawer)。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-111">You may open the **Console** as a [tool in the upper pane](#open-the-console-tool) or as a [tool in the Drawer](#open-the-console-tool-in-the-drawer).</span></span>  

### <a name="open-the-console-tool"></a><span data-ttu-id="5a9c3-112">コンソール ツールを開く</span><span class="sxs-lookup"><span data-stu-id="5a9c3-112">Open the Console tool</span></span>  

<span data-ttu-id="5a9c3-113">`Control` + `Shift` + `J` \(Windows, Linux\) または `Command` + `Option` + `J` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-113">Select `Control`+`Shift`+`J` \(Windows, Linux\) or `Command`+`Option`+`J` \(macOS\).</span></span>  

:::image type="complex" source="../media/console-hello-console.msft.png" alt-text="コンソール ツール" lightbox="../media/console-hello-console.msft.png":::
   <span data-ttu-id="5a9c3-115">コンソール**ツール**</span><span class="sxs-lookup"><span data-stu-id="5a9c3-115">The **Console** tool</span></span>  
:::image-end:::  

<span data-ttu-id="5a9c3-116">コマンド メニューから**コンソール**ツールを[開][DevToolsCommandMenu]くには、入力を開始し、パネル バッジが横にある [コンソールの表示] `Console` **コマンド**を実行します。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="5a9c3-116">To open the **Console** tool from the [Command Menu][DevToolsCommandMenu], start typing `Console` and then run the **Show Console** command that has the **Panel** badge next to it.</span></span>  

:::image type="complex" source="../media/console-command-menu-show-console.msft.png" alt-text="コンソール パネルを表示するコマンド" lightbox="../media/console-command-menu-show-console.msft.png":::
   <span data-ttu-id="5a9c3-118">コンソール ツールを表示 **する** コマンド</span><span class="sxs-lookup"><span data-stu-id="5a9c3-118">The command to show the **Console** tool</span></span>  
:::image-end:::  

### <a name="open-the-console-tool-in-the-drawer"></a><span data-ttu-id="5a9c3-119">ドロワーでコンソール ツールを開く</span><span class="sxs-lookup"><span data-stu-id="5a9c3-119">Open the Console tool in the Drawer</span></span>  

<span data-ttu-id="5a9c3-120">`Escape` **[DevTools のカスタマイズと制御]** \( \) を選択 `...` または選択し、[コンソール ドロワー**の表示] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-120">Select `Escape` or choose **Customize And Control DevTools** \(`...`\) and then choose **Show console drawer**.</span></span>  

:::image type="complex" source="../media/console-elements-customize-control-devtools-show-console-drawer.msft.png" alt-text="コンソール ドロワーの表示" lightbox="../media/console-elements-customize-control-devtools-show-console-drawer.msft.png":::
   **<span data-ttu-id="5a9c3-122">コンソール ドロワーの表示</span><span class="sxs-lookup"><span data-stu-id="5a9c3-122">Show console drawer</span></span>**  
:::image-end:::  

<span data-ttu-id="5a9c3-123">[引き出し] が DevTools ウィンドウの下部に表示されます。コンソール ツール **が開** きます。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-123">The Drawer pops up at the bottom of your DevTools window, with the **Console** tool open.</span></span>  

:::image type="complex" source="../media/console-elements-console-drawer-hello-world.msft.png" alt-text="ドロワーのコンソール ツール" lightbox="../media/console-elements-console-drawer-hello-world.msft.png":::
   <span data-ttu-id="5a9c3-125">ドロ **ワー** のコンソール **ツール**</span><span class="sxs-lookup"><span data-stu-id="5a9c3-125">The **Console** tool in the **Drawer**</span></span>  
:::image-end:::  

<span data-ttu-id="5a9c3-126">コマンド メニューから**コンソール ツール**を[開][DevToolsCommandMenu]くには、入力を開始し、その横にドロワー バッジがある [コンソールの表示] コマンド `Console` を実行します。 \*\*\*\* \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="5a9c3-126">To open the **Console** tool from the [Command Menu][DevToolsCommandMenu], start typing `Console` and then run the **Show Console** command that has the **Drawer** badge next to it.</span></span>  

:::image type="complex" source="../media/console-command-menu-show-console.msft.png" alt-text="ドロワーに **Console** ツールを表示するコマンド" lightbox="../media/console-command-menu-show-console.msft.png":::
   <span data-ttu-id="5a9c3-128">ドロワーにコンソール ツール **を** 表示する **コマンド**</span><span class="sxs-lookup"><span data-stu-id="5a9c3-128">The command to show the **Console** tool in the **Drawer**</span></span>  
:::image-end:::  

### <a name="open-console-settings"></a><span data-ttu-id="5a9c3-129">コンソールの設定を開く</span><span class="sxs-lookup"><span data-stu-id="5a9c3-129">Open Console Settings</span></span>  

<span data-ttu-id="5a9c3-130">[ **コンソール設定]** \( ![ [コンソール設定] アイコン ][ImageSettingsButtonIcon] \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-130">Choose **Console Settings** \(![Console Settings icon][ImageSettingsButtonIcon]\).</span></span>  

:::image type="complex" source="../media/console-settings-group-similar-empty.msft.png" alt-text="コンソール設定" lightbox="../media/console-settings-group-similar-empty.msft.png":::
   **<span data-ttu-id="5a9c3-132">コンソール設定</span><span class="sxs-lookup"><span data-stu-id="5a9c3-132">Console Settings</span></span>**  
:::image-end:::  

<span data-ttu-id="5a9c3-133">以下のリンクでは、各設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-133">The links below explain each setting:</span></span>  

*   [**<span data-ttu-id="5a9c3-134">ネットワークを非表示にする</span><span class="sxs-lookup"><span data-stu-id="5a9c3-134">Hide Network</span></span>**](#hide-network-messages)  
*   [**<span data-ttu-id="5a9c3-135">ログの保持</span><span class="sxs-lookup"><span data-stu-id="5a9c3-135">Preserve Log</span></span>**](#persist-messages-across-page-loads)  
*   [**<span data-ttu-id="5a9c3-136">選択したコンテキストのみ</span><span class="sxs-lookup"><span data-stu-id="5a9c3-136">Selected Context Only</span></span>**](#filter-out-messages-from-different-contexts)  
*   [**<span data-ttu-id="5a9c3-137">グループ類似</span><span class="sxs-lookup"><span data-stu-id="5a9c3-137">Group Similar</span></span>**](#disable-message-grouping)  
*   [**<span data-ttu-id="5a9c3-138">Log XmlHttpRequests</span><span class="sxs-lookup"><span data-stu-id="5a9c3-138">Log XmlHttpRequests</span></span>**](#log-xhr-and-fetch-requests)  
*   [**<span data-ttu-id="5a9c3-139">熱心な評価</span><span class="sxs-lookup"><span data-stu-id="5a9c3-139">Eager Evaluation</span></span>**](#disable-eager-evaluation)  
*   [**<span data-ttu-id="5a9c3-140">履歴からのオートコンプリート</span><span class="sxs-lookup"><span data-stu-id="5a9c3-140">Autocomplete From History</span></span>**](#disable-autocomplete-from-history)  
    
### <a name="open-the-console-sidebar"></a><span data-ttu-id="5a9c3-141">コンソール サイドバーを開く</span><span class="sxs-lookup"><span data-stu-id="5a9c3-141">Open the Console Sidebar</span></span>  

<span data-ttu-id="5a9c3-142">[Show **Console Sidebar** \( Show Console Sidebar \) ] を選択してサイドバーを表示します。これはフィルター処理 ![ ][ImageShowConsoleSidebarIcon] に便利です。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-142">Choose **Show Console Sidebar** \(![Show Console Sidebar][ImageShowConsoleSidebarIcon]\) to show the Sidebar, which is useful for filtering.</span></span>  

:::image type="complex" source="../media/console-sidebar-drawer-empty.msft.png" alt-text="コンソール サイドバー" lightbox="../media/console-sidebar-drawer-empty.msft.png":::
   <span data-ttu-id="5a9c3-144">**コンソール** サイドバー</span><span class="sxs-lookup"><span data-stu-id="5a9c3-144">**Console** Sidebar</span></span>  
:::image-end:::  

## <a name="view-messages"></a><span data-ttu-id="5a9c3-145">メッセージの表示</span><span class="sxs-lookup"><span data-stu-id="5a9c3-145">View messages</span></span>  

<span data-ttu-id="5a9c3-146">このセクションには、コンソールでのメッセージの表示方法を変更する機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-146">This section contains features that change how messages are presented in the Console.</span></span>  <span data-ttu-id="5a9c3-147">実践的なチュートリアルの場合は、[メッセージの表示] [に移動します][DevToolsConsoleViewMessages]。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-147">For a hands-on walkthrough, navigate to [View messages][DevToolsConsoleViewMessages].</span></span>  

### <a name="disable-message-grouping"></a><span data-ttu-id="5a9c3-148">メッセージのグループ化を無効にする</span><span class="sxs-lookup"><span data-stu-id="5a9c3-148">Disable message grouping</span></span>  

<span data-ttu-id="5a9c3-149">[[コンソールの設定] を](#open-console-settings) 開き、[ **グループ]** を無効にして、コンソールの既定のメッセージ グループ化動作を無効にします。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-149">[Open Console Settings](#open-console-settings) and disable **Group similar** to disable the default message grouping behavior of the Console.</span></span>  <span data-ttu-id="5a9c3-150">たとえば、[ [ログ XHR] と [フェッチ要求] に移動します](#log-xhr-and-fetch-requests)。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-150">For an example, navigate to [Log XHR and Fetch requests](#log-xhr-and-fetch-requests).</span></span>  

### <a name="log-xhr-and-fetch-requests"></a><span data-ttu-id="5a9c3-151">ログ XHR 要求とフェッチ要求</span><span class="sxs-lookup"><span data-stu-id="5a9c3-151">Log XHR and Fetch requests</span></span>  

<span data-ttu-id="5a9c3-152">[[コンソールの設定]](#open-console-settings) を開き **、[ログ XMLHttpRequests]** を有効にして、発生したすべての要求を `XMLHttpRequest` コンソールに `Fetch` 記録します。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-152">[Open Console Settings](#open-console-settings) and enable **Log XMLHttpRequests** to log all `XMLHttpRequest` and `Fetch` requests to the Console as they happen.</span></span>  

:::image type="complex" source="../media/console-xhr-fetch.msft.png" alt-text="ログ XMLHttpRequest および Fetch 要求" lightbox="../media/console-xhr-fetch.msft.png":::
   <span data-ttu-id="5a9c3-154">ログ `XMLHttpRequest` と `Fetch` 要求</span><span class="sxs-lookup"><span data-stu-id="5a9c3-154">Log `XMLHttpRequest` and `Fetch` requests</span></span>  
:::image-end:::  
<span data-ttu-id="5a9c3-155">前の図のトップ メッセージには、コンソールの既定のグループ化動作が表示 **されます**。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-155">The top message in previous figure displays the default grouping behavior of the **Console**.</span></span>  <!--  In the following figure, the same log is displayed after [disabling message grouping](#disable-message-grouping).  -->  

<!--  
> ##### Old Figure 9  
> How the logged `XMLHttpRequest` and `Fetch` requests look after ungrouping  
> :::image type="complex" source="../media/console-xhr-fetch-all.msft.png" alt-text="How the logged XMLHttpRequest and Fetch requests look after ungrouping" lightbox="../media/console-xhr-fetch-all.msft.png":::
>    How the logged XMLHttpRequest and Fetch requests look after ungrouping  
> :::image-end:::  
-->  

<!--todo: add example for ungrouping console items  -->  

### <a name="persist-messages-across-page-loads"></a><span data-ttu-id="5a9c3-156">ページの読み込み中にメッセージを保持する</span><span class="sxs-lookup"><span data-stu-id="5a9c3-156">Persist messages across page loads</span></span>  

<span data-ttu-id="5a9c3-157">既定では、新しいページを読み込むたびにコンソールがクリアされます。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-157">By default the Console clears whenever you load a new page.</span></span>  <span data-ttu-id="5a9c3-158">ページの読み込み時にメッセージを保持するには、[ [コンソール設定] を開](#open-console-settings) き、[ログの保持] **チェック ボックスをオン** にします。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-158">To persist messages across page loads, [Open Console Settings](#open-console-settings) and then enable the **Preserve Log** checkbox.</span></span>  

### <a name="hide-network-messages"></a><span data-ttu-id="5a9c3-159">ネットワーク メッセージを非表示にする</span><span class="sxs-lookup"><span data-stu-id="5a9c3-159">Hide network messages</span></span>  

<span data-ttu-id="5a9c3-160">既定では、ブラウザーはネットワーク メッセージをコンソールに記録 **します**。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-160">By default the browser logs network messages to the **Console**.</span></span>  <span data-ttu-id="5a9c3-161">次の図では、選択したメッセージはの HTTP 状態コードを表します `429` 。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-161">In the following figure, the selected message represents an HTTP status code of `429`.</span></span>  

:::image type="complex" source="../media/console-show-network.msft.png" alt-text="コンソールの 429 メッセージ" lightbox="../media/console-show-network.msft.png":::
   <span data-ttu-id="5a9c3-163">コンソール `429` 内の **メッセージ**</span><span class="sxs-lookup"><span data-stu-id="5a9c3-163">A `429` message in the **Console**</span></span>  
:::image-end:::  
<span data-ttu-id="5a9c3-164">ネットワーク メッセージを非表示にする方法:</span><span class="sxs-lookup"><span data-stu-id="5a9c3-164">To hide network messages:</span></span>  

1.  <span data-ttu-id="5a9c3-165">[[コンソール設定] を開きます](#open-console-settings)。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-165">[Open Console Settings](#open-console-settings).</span></span>  
1.  <span data-ttu-id="5a9c3-166">[ネットワークの **非表示] チェック ボックスを** オンにします。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-166">Enable the **Hide Network** checkbox.</span></span>  
    
## <a name="filter-messages"></a><span data-ttu-id="5a9c3-167">フィルター メッセージ</span><span class="sxs-lookup"><span data-stu-id="5a9c3-167">Filter messages</span></span>  

<span data-ttu-id="5a9c3-168">コンソールでメッセージをフィルター処理する方法は多数あります。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-168">There are many ways to filter out messages in the Console.</span></span>  

### <a name="filter-out-browser-messages"></a><span data-ttu-id="5a9c3-169">ブラウザー メッセージをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="5a9c3-169">Filter out browser messages</span></span>  

<span data-ttu-id="5a9c3-170">[コンソール サイドバーを開き](#open-the-console-sidebar) 、[ **ユーザー** メッセージ] を選択して、ページの JavaScript から送信されたメッセージのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-170">[Open the Console Sidebar](#open-the-console-sidebar) and choose **User Messages** to only show messages that came from the JavaScript of the page.</span></span>  

:::image type="complex" source="../media/console-sidebar-drawer-user-messages.msft.png" alt-text="ユーザー メッセージの表示" lightbox="../media/console-sidebar-drawer-user-messages.msft.png":::
   <span data-ttu-id="5a9c3-172">ユーザー メッセージの表示</span><span class="sxs-lookup"><span data-stu-id="5a9c3-172">View user messages</span></span>  
:::image-end:::  

### <a name="filter-by-log-level"></a><span data-ttu-id="5a9c3-173">ログ レベルでフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="5a9c3-173">Filter by log level</span></span>  

<span data-ttu-id="5a9c3-174">DevTools は、各 `console.*` メソッドに重大度レベルを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-174">DevTools assigns each `console.*` method a severity level.</span></span>  <span data-ttu-id="5a9c3-175">4 つのレベルがあります `Verbose` 。 `Info` `Warning` `Error`</span><span class="sxs-lookup"><span data-stu-id="5a9c3-175">There are 4 levels: `Verbose`, `Info`, `Warning`, and `Error`.</span></span>  <span data-ttu-id="5a9c3-176">たとえば、 `console.log()` グループ内 `Info` ですが、グループ `console.error()` 内 `Error` です。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-176">For example, `console.log()` is in the `Info` group, whereas `console.error()` is in the `Error` group.</span></span>  <span data-ttu-id="5a9c3-177">コンソール [API リファレンスでは][DevToolsConsoleApi] 、該当する各メソッドの重大度レベルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-177">The [Console API Reference][DevToolsConsoleApi] describes the severity level of each applicable method.</span></span>  <span data-ttu-id="5a9c3-178">ブラウザーがコンソールにログに記録するメッセージには、重大度レベルもあります。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-178">Every message that the browser logs to the Console has a severity level too.</span></span>  <span data-ttu-id="5a9c3-179">興味がないメッセージのレベルは非表示にできます。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-179">You may hide any level of messages that you are not interested in.</span></span>  <span data-ttu-id="5a9c3-180">たとえば、メッセージにのみ関心がある場合は、 `Error` 他の 3 つのグループを非表示にできます。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-180">For example, if you are only interested in `Error` messages, you may hide the other 3 groups.</span></span>  

<span data-ttu-id="5a9c3-181">[ログ レベル **] ドロップダウンを** 選択して、メッセージ `Verbose` を有効または `Info` `Warning` 無効 `Error` にします。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-181">Choose the **Log Levels** dropdown to enable or disable `Verbose`, `Info`, `Warning` or `Error` messages.</span></span>  

:::image type="complex" source="../media/console-log-level-default-levels.msft.png" alt-text="[ログ レベル] ドロップダウン" lightbox="../media/console-log-level-default-levels.msft.png":::
   <span data-ttu-id="5a9c3-183">[ **ログ レベル]** ドロップダウン</span><span class="sxs-lookup"><span data-stu-id="5a9c3-183">The **Log Levels** dropdown</span></span>  
:::image-end:::  

<span data-ttu-id="5a9c3-184">コンソール サイドバーを開き、エラー、警告、情報、または詳細を選択\*\*\*\* して、\*\*\*\* ログ レベル**でフィルター**処理**することもできます**。 [](#open-the-console-sidebar)</span><span class="sxs-lookup"><span data-stu-id="5a9c3-184">You may also filter by log level by [opening the Console Sidebar](#open-the-console-sidebar) and thenchoosing **Errors**, **Warnings**, **Info**, or **Verbose**.</span></span>  

:::image type="complex" source="../media/console-sidebar-warnings.msft.png" alt-text="サイドバーを使用して警告を表示する" lightbox="../media/console-sidebar-warnings.msft.png":::
   <span data-ttu-id="5a9c3-186">サイドバーを使用して警告を表示する</span><span class="sxs-lookup"><span data-stu-id="5a9c3-186">Use the Sidebar to view warnings</span></span>  
:::image-end:::  

### <a name="filter-messages-by-url"></a><span data-ttu-id="5a9c3-187">URL でメッセージをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="5a9c3-187">Filter messages by URL</span></span>  

<span data-ttu-id="5a9c3-188">URL `url:` の後に URL を入力して、その URL から送信されたメッセージのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-188">Type `url:` followed by a URL to only view messages that came from that URL.</span></span>  <span data-ttu-id="5a9c3-189">DevTools と `url:` 入力すると、関連するすべての URL が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-189">After you type `url:` DevTools shows all relevant URLs.</span></span>  <span data-ttu-id="5a9c3-190">ドメインも機能します。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-190">Domains also work.</span></span>  <span data-ttu-id="5a9c3-191">たとえば、メッセージをログに記録する場合は、これら 2 つのスクリプトからのメッセージ `https://example.com/a.js` `https://example.com/b.js` `url:https://example.com` に集中できます。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-191">For example, if `https://example.com/a.js` and `https://example.com/b.js` are logging messages, `url:https://example.com` enables you to focus on the messages from these 2 scripts.</span></span>  

:::image type="complex" source="../media/console-filter-text.msft.png" alt-text="URL フィルター" lightbox="../media/console-filter-text.msft.png":::
   <span data-ttu-id="5a9c3-193">URL フィルター</span><span class="sxs-lookup"><span data-stu-id="5a9c3-193">A URL filter</span></span>  
:::image-end:::  

<span data-ttu-id="5a9c3-194">その `-url:` URL からメッセージを非表示にする場合は、入力します。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-194">Type `-url:` to hide messages from that URL.</span></span>  <span data-ttu-id="5a9c3-195">これは、負の URL フィルターと呼ばれる。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-195">This is called a negative URL filter.</span></span>  

:::image type="complex" source="../media/console-negative-filter-text.msft.png" alt-text="URL に一致するメッセージをすべて非表示にする負の https://b.wal.co URL フィルター" lightbox="../media/console-negative-filter-text.msft.png":::
   <span data-ttu-id="5a9c3-197">URL に一致するメッセージをすべて非表示にする負の `https://b.wal.co` URL フィルター</span><span class="sxs-lookup"><span data-stu-id="5a9c3-197">A negative URL filter that hides all messages that match the `https://b.wal.co` URL</span></span>
:::image-end:::  

<span data-ttu-id="5a9c3-198">単一の URL からのメッセージを表示[](#open-the-console-sidebar)するには、コンソール サイドバーを開き\*\*\*\*、[ユーザー メッセージ] セクションを展開し、フォーカスするメッセージを含むスクリプトの URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-198">You may also show messages from a single URL by [opening the Console Sidebar](#open-the-console-sidebar), expanding the **User Messages** section, and thenchoosing the URL of the script containing the messages on which you want to focus.</span></span>  

:::image type="complex" source="../media/console-filter-text-specified.msft.png" alt-text="ユーザーから送信されたメッセージを表示wp-ad.min.js" lightbox="../media/console-filter-text-specified.msft.png":::
   <span data-ttu-id="5a9c3-200">から来たメッセージを表示する</span><span class="sxs-lookup"><span data-stu-id="5a9c3-200">View the messages that came from</span></span> `wp-ad.min.js`  
:::image-end:::  

### <a name="filter-out-messages-from-different-contexts"></a><span data-ttu-id="5a9c3-201">さまざまなコンテキストからのメッセージをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="5a9c3-201">Filter out messages from different contexts</span></span>  

<span data-ttu-id="5a9c3-202">ページに広告 \(ad\) が含まれるとします。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-202">Suppose that you have an advertisement \(ad\) on your page.</span></span>  <span data-ttu-id="5a9c3-203">広告は a に埋め込まれているので、コンソールで多くの `<iframe>` メッセージを生成しています。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-203">The ad is embedded in an `<iframe>` and is generating a lot of messages in your Console.</span></span>  <span data-ttu-id="5a9c3-204">広告は別の[JavaScript](#select-javascript-context)コンテキストで実行されているので、メッセージを非表示にする方法の[](#open-console-settings)1 つは、[コンソール設定] を開き、[選択されたコンテキストのみ] チェック ボックスを**オンにします**。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-204">Because the ad is running in a different [JavaScript context](#select-javascript-context), one way to hide the messages is to [open Console Settings](#open-console-settings) and turn on the **Selected Context Only** checkbox.</span></span>  

### <a name="filter-out-messages-that-do-not-match-a-regular-expression-pattern"></a><span data-ttu-id="5a9c3-205">正規表現パターンに一致しないメッセージをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="5a9c3-205">Filter out messages that do not match a regular expression pattern</span></span>  

<span data-ttu-id="5a9c3-206">[フィルター] テキスト ボックスに正規表現を入力して、そのパターンに一致しないメッセージ `/[gm][ta][mi]/` をフィルター処理します。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="5a9c3-206">Type a regular expression such as `/[gm][ta][mi]/` in the **Filter** text box to filter out any messages that do not match that pattern.</span></span>  <span data-ttu-id="5a9c3-207">DevTools は、メッセージ テキストにパターンが見つかったか、メッセージがログに記録される原因となるスクリプトをチェックします。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-207">DevTools checks if the pattern is found in the message text or the script that caused the message to be logged.</span></span>  

:::image type="complex" source="../media/console-filter-regex.msft.png" alt-text="正規表現に一致しないメッセージをフィルター処理する" lightbox="../media/console-filter-regex.msft.png":::
   <span data-ttu-id="5a9c3-209">正規表現に一致しないメッセージを `/[gm][ta][mi]/` フィルター処理する</span><span class="sxs-lookup"><span data-stu-id="5a9c3-209">Filter out any messages that do not match the `/[gm][ta][mi]/` regex expression</span></span>  
:::image-end:::  

## <a name="run-javascript"></a><span data-ttu-id="5a9c3-210">JavaScript の実行</span><span class="sxs-lookup"><span data-stu-id="5a9c3-210">Run JavaScript</span></span>  

<span data-ttu-id="5a9c3-211">このセクションでは、コンソールでの JavaScript の実行に関連する機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-211">This section contains features related to running JavaScript in the Console.</span></span>  <span data-ttu-id="5a9c3-212">実践的なチュートリアルの場合は、[JavaScript の実行 [] に移動します][DevToolsConsoleOverviewJavascript]。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-212">For a hands-on walkthrough, navigate to [Run JavaScript][DevToolsConsoleOverviewJavascript].</span></span>  

### <a name="re-run-expressions-from-history"></a><span data-ttu-id="5a9c3-213">履歴から式を再実行する</span><span class="sxs-lookup"><span data-stu-id="5a9c3-213">Re-run expressions from history</span></span>  

<span data-ttu-id="5a9c3-214">コンソールで前に実行した JavaScript 式の履歴を循環するキー `Up Arrow` を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-214">Select the `Up Arrow` key to cycle through the history of JavaScript expressions that you ran earlier in the Console.</span></span>  <span data-ttu-id="5a9c3-215">この式 `Enter` を再度実行する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-215">Select `Enter` to run that expression again.</span></span>  

### <a name="watch-the-value-of-an-expression-in-real-time-with-live-expressions"></a><span data-ttu-id="5a9c3-216">Live Expression を使用して、リアルタイムで式の値を確認する</span><span class="sxs-lookup"><span data-stu-id="5a9c3-216">Watch the value of an expression in real-time with Live Expressions</span></span>  

<span data-ttu-id="5a9c3-217">コンソールで同じ JavaScript 式を繰り返し入力すると、Live 式の作成が簡単になる **場合があります**。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-217">If you find yourself typing the same JavaScript expression in the Console repeatedly, you may find it easier to create a **Live Expression**.</span></span>  <span data-ttu-id="5a9c3-218">Live **Expression を使用すると** 、一度式を入力し、本体の上部にピン留めします。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-218">With **Live Expressions** you type an expression once and then pin it to the top of your Console.</span></span>  <span data-ttu-id="5a9c3-219">式の値は、ほぼリアルタイムで更新されます。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-219">The value of the expression updates in near real-time.</span></span>  <span data-ttu-id="5a9c3-220">[ライブ式 [を使用して JavaScript 式Real-Timeを監視する] に移動します][DevToolsConsoleLiveExpressions]。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-220">Navigate to [Watch JavaScript Expression Values In Real-Time With Live Expressions][DevToolsConsoleLiveExpressions].</span></span>  

### <a name="disable-eager-evaluation"></a><span data-ttu-id="5a9c3-221">一時的な評価を無効にする</span><span class="sxs-lookup"><span data-stu-id="5a9c3-221">Disable Eager Evaluation</span></span>  

<span data-ttu-id="5a9c3-222">コンソールに JavaScript 式を入力すると、 **その** 式の戻り値のプレビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-222">As you type JavaScript expressions in the Console, **Eager Evaluation** shows a preview of the return value for that expression.</span></span>  <span data-ttu-id="5a9c3-223">[[コンソールの設定] を](#open-console-settings) 開き、[ **熱心な評価** ] チェック ボックスを無効にして、戻り値のプレビューをオフにします。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-223">[Open Console Settings](#open-console-settings) and disable the **Eager Evaluation** checkbox to turn off the return value previews.</span></span>  

### <a name="disable-autocomplete-from-history"></a><span data-ttu-id="5a9c3-224">履歴からオートコンプリートを無効にする</span><span class="sxs-lookup"><span data-stu-id="5a9c3-224">Disable autocomplete from history</span></span>  

<span data-ttu-id="5a9c3-225">式を入力すると、コンソールのオートコンプリート ポップアップ ウィンドウに、前に実行した式が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-225">As you type out an expression, the autocomplete popup window for the Console shows expressions that you ran earlier.</span></span>  <span data-ttu-id="5a9c3-226">これらの式の先頭には、文字が付加 `>` されます。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-226">These expressions are prepended with the `>` character.</span></span>  <span data-ttu-id="5a9c3-227">[[コンソール設定] を](#open-console-settings) 開き、[ **履歴からオートコンプリート** ] チェック ボックスをオフにして、履歴からの式の表示を停止します。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-227">[Open Console Settings](#open-console-settings) and disable the **Autocomplete From History** checkbox to stop showing expressions from your history.</span></span>  

> [!NOTE]
> <span data-ttu-id="5a9c3-228">次の図では、 `document.querySelector('a')` `document.querySelector('img')` 前に評価された式を示します。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-228">In the following figure, `document.querySelector('a')` and `document.querySelector('img')` are expressions that were evaluated earlier.</span></span>  

:::image type="complex" source="../media/console-filter-text-autofilter-history.msft.png" alt-text="オートコンプリート ポップアップに履歴の式が表示される" lightbox="../media/console-filter-text-autofilter-history.msft.png":::
   <span data-ttu-id="5a9c3-230">オートコンプリート ポップアップに履歴の式が表示される</span><span class="sxs-lookup"><span data-stu-id="5a9c3-230">The autocomplete popup displays expressions from history</span></span>  
:::image-end:::  

### <a name="select-javascript-context"></a><span data-ttu-id="5a9c3-231">JavaScript コンテキストの選択</span><span class="sxs-lookup"><span data-stu-id="5a9c3-231">Select JavaScript context</span></span>  

<span data-ttu-id="5a9c3-232">既定では **、JavaScript Context ドロップダウン**は\*\*\*\* top に設定され[][MDNBrowsingContext]、メイン ドキュメントの参照コンテキストを表します。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-232">By default the **JavaScript Context** dropdown is set to **top**, which represents the [browsing context][MDNBrowsingContext] of the main document.</span></span>  

:::image type="complex" source="../media/console-dom-level-top.msft.png" alt-text="[JavaScript コンテキスト] ドロップダウン" lightbox="../media/console-dom-level-top.msft.png":::
   <span data-ttu-id="5a9c3-234">**[JavaScript コンテキスト] ドロップダウン**</span><span class="sxs-lookup"><span data-stu-id="5a9c3-234">The **JavaScript Context** dropdown</span></span>  
:::image-end:::  

<span data-ttu-id="5a9c3-235">ページに広告が埋め込まれているとします `<iframe>` 。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-235">Suppose you have an ad on your page embedded in an `<iframe>`.</span></span>  <span data-ttu-id="5a9c3-236">広告の DOM を調整するために JavaScript を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-236">You want to run JavaScript in order to tweak the DOM of the ad.</span></span>  <span data-ttu-id="5a9c3-237">まず、[JavaScript コンテキスト] ドロップダウンから広告の参照コンテキスト **を選択する必要** があります。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-237">You should first select the browsing context of the ad from the **JavaScript Context** dropdown.</span></span>  

:::image type="complex" source="../media/console-dom-level-multiple.msft.png" alt-text="別の JavaScript コンテキストを選択する" lightbox="../media/console-dom-level-multiple.msft.png":::
   <span data-ttu-id="5a9c3-239">別の JavaScript コンテキストを選択する</span><span class="sxs-lookup"><span data-stu-id="5a9c3-239">Choose a different JavaScript context</span></span>  
:::image-end:::  

## <a name="clear-the-console"></a><span data-ttu-id="5a9c3-240">コンソールをクリアする</span><span class="sxs-lookup"><span data-stu-id="5a9c3-240">Clear the Console</span></span>  

<span data-ttu-id="5a9c3-241">コンソールをクリアするには、次のワークフローを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-241">You may use any of the following workflows to clear the Console:</span></span>  

*   <span data-ttu-id="5a9c3-242">[Clear **Console** \( ![ Clear Console ][ImageClearConsoleIcon] \] )を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-242">Choose **Clear Console** \(![Clear Console][ImageClearConsoleIcon]\).</span></span>  
*   <span data-ttu-id="5a9c3-243">メッセージにカーソルを置き、コンテキスト メニュー \(righ-click\) を開き、[コンソールのクリア] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-243">Hover on a message, open the contextual menu \(righ-click\), and choose **Clear Console**.</span></span>  
*   <span data-ttu-id="5a9c3-244">コンソール `clear()` に入力 **し、 を** 選択します `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-244">Enter `clear()` in the **Console** and select `Enter`.</span></span>  
*   <span data-ttu-id="5a9c3-245">Web `console.clear()` ページの JavaScript から実行します。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-245">Run `console.clear()` from the JavaScript for your webpage.</span></span>  
*   <span data-ttu-id="5a9c3-246">コンソール `Control` + `L` がフォーカス**されている間**に選択します。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-246">Select `Control`+`L` while the **Console** is in focus.</span></span>  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="5a9c3-247">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="5a9c3-247">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageClearConsoleIcon]: ../media/clear-console-button-icon.msft.png  
[ImageSettingsButtonIcon]: ../media/settings-button-icon.msft.png  
[ImageShowConsoleSidebarIcon]: ../media/show-console-sidebar-icon.msft.png  

<!-- links -->  

[DevToolsCommandMenu]: ../command-menu/index.md "[Microsoft Edge DevTools コマンド] メニューメニューを使用してコマンドを実行|Microsoft Docs"  
[DevToolsConsoleViewMessages]: ./index.md#viewing-logged-messages "ログに記録されたメッセージの表示 - コンソールの概要|Microsoft Docs"  
[DevToolsConsoleApi]: ./api.md "コンソール API リファレンス |Microsoft Docs"  
[DevToolsConsoleOverviewJavascript]: ./index.md#running-javascript "JavaScript の実行 - コンソールの概要|Microsoft Docs"  
[DevToolsConsoleJavascript]: ./javascript.md "コンソール サーバーで JavaScript を実行する方法を|Microsoft Docs"  
[DevToolsConsoleLiveExpressions]: ./live-expressions.md "Live Expression を使用して JavaScript 式の値をリアルタイムで|Microsoft Docs"  
[DevToolsConsoleLog]: ./log.md "コンソール ウィンドウでメッセージをログに記録する方法を|Microsoft Docs"  
[DevToolsConsoleUtilities]: ./utilities.md "コンソール ユーティリティ API リファレンス |Microsoft Docs"  

[MDNBrowsingContext]: https://developer.mozilla.org/docs/Glossary/Browsing_context "参照コンテキスト |MDN"  

> [!NOTE]
> <span data-ttu-id="5a9c3-257">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-257">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="5a9c3-258">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/console/reference) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-258">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="5a9c3-260">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="5a9c3-260">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
