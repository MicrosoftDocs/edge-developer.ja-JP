---
title: 本体のリファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 51a85c3dad121dcb42633390de9b4e817074546e
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10982478"
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





# <span data-ttu-id="c500b-103">本体のリファレンス</span><span class="sxs-lookup"><span data-stu-id="c500b-103">Console Reference</span></span>   



<span data-ttu-id="c500b-104">このページでは、Microsoft Edge DevTools コンソールに関連する機能のリファレンスを示します。</span><span class="sxs-lookup"><span data-stu-id="c500b-104">This page is a reference of features related to the Microsoft Edge DevTools Console.</span></span>  <span data-ttu-id="c500b-105">ログに記録されたメッセージを表示して JavaScript を実行するには、既にコンソールを使用していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="c500b-105">It assumes that you are already familiar with using the Console to view logged messages and run JavaScript.</span></span>  <span data-ttu-id="c500b-106">表示されない場合は、「 [コンソールでの JavaScript の実行を開始する][DevToolsConsoleJavascript] 」を参照してください。 [コンソールでのメッセージの記録を開始][DevToolsConsoleLog]します。</span><span class="sxs-lookup"><span data-stu-id="c500b-106">If not, see [Get Started With Running JavaScript In The Console][DevToolsConsoleJavascript] and [Get Started With Logging Messages In The Console][DevToolsConsoleLog].</span></span>  

<span data-ttu-id="c500b-107">API 参照を検索する場合は、 `console.log()` 「 [コンソール API リファレンス][DevToolsConsoleApi]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c500b-107">If you are looking for the API reference on functions like `console.log()` see [Console API Reference][DevToolsConsoleApi].</span></span>  <span data-ttu-id="c500b-108">次のような関数のリファレンスについ `monitorEvents()` ては、「 [コンソールユーティリティ API リファレンス][DevToolsConsoleUtilities]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c500b-108">For the reference on functions like `monitorEvents()`, see [Console Utilities API Reference][DevToolsConsoleUtilities].</span></span>  

## <span data-ttu-id="c500b-109">本体を開く</span><span class="sxs-lookup"><span data-stu-id="c500b-109">Open the Console</span></span>   

<span data-ttu-id="c500b-110">コンソールは、引き出しの [パネル](#open-the-console-panel) または [タブ](#open-the-console-tab-in-the-drawer)として開くことができます。</span><span class="sxs-lookup"><span data-stu-id="c500b-110">You may open the Console as a [panel](#open-the-console-panel) or as a [tab in the Drawer](#open-the-console-tab-in-the-drawer).</span></span>  

### <span data-ttu-id="c500b-111">コンソールパネルを開く</span><span class="sxs-lookup"><span data-stu-id="c500b-111">Open the Console panel</span></span>   

<span data-ttu-id="c500b-112">`Control` + `Shift` + `J` \ (Windows \) または `Command` + `Option` + `J` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="c500b-112">Press `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\).</span></span>  

:::image type="complex" source="../media/console-hello-console.msft.png" alt-text="コンソールパネル" lightbox="../media/console-hello-console.msft.png":::
   <span data-ttu-id="c500b-114">**コンソール**パネル</span><span class="sxs-lookup"><span data-stu-id="c500b-114">The **Console** panel</span></span>  
:::image-end:::  

<span data-ttu-id="c500b-115">[コマンドメニュー][DevToolsCommandMenu]からコンソールパネルを開くには、入力を開始してから `Console` 、その横にある**パネル**バッジのある [**コンソールの表示**] コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c500b-115">To open the Console panel from the [Command Menu][DevToolsCommandMenu], start typing `Console` and then run the **Show Console** command that has the **Panel** badge next to it.</span></span>  

:::image type="complex" source="../media/console-command-menu-show-console.msft.png" alt-text="コンソールパネルを表示するコマンド" lightbox="../media/console-command-menu-show-console.msft.png":::
   <span data-ttu-id="c500b-117">**コンソール**パネルを表示するコマンド</span><span class="sxs-lookup"><span data-stu-id="c500b-117">The command to show the **Console** panel</span></span>  
:::image-end:::  

### <span data-ttu-id="c500b-118">ドロワーで [コンソール] タブを開く</span><span class="sxs-lookup"><span data-stu-id="c500b-118">Open the Console tab in the Drawer</span></span>   

<span data-ttu-id="c500b-119">[ `Escape` **カスタマイズと制御** ] を押します。 [(\)] をクリックして、[ `...` **コンソールドローワの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c500b-119">Press `Escape` or click **Customize And Control DevTools** \(`...`\) and then select **Show console drawer**.</span></span>  

:::image type="complex" source="../media/console-elements-customize-control-devtools-show-console-drawer.msft.png" alt-text="コンソールのドローワを表示" lightbox="../media/console-elements-customize-control-devtools-show-console-drawer.msft.png":::
   **<span data-ttu-id="c500b-121">コンソールのドローワを表示</span><span class="sxs-lookup"><span data-stu-id="c500b-121">Show console drawer</span></span>**  
:::image-end:::  

<span data-ttu-id="c500b-122">[ **コンソール** ] タブを開いた状態で、[devtools] ウィンドウの下部に引き出しがポップアップ表示されます。</span><span class="sxs-lookup"><span data-stu-id="c500b-122">The Drawer pops up at the bottom of your DevTools window, with the **Console** tab open.</span></span>  

:::image type="complex" source="../media/console-elements-console-drawer-hello-world.msft.png" alt-text="ドローワの [コンソール] タブ" lightbox="../media/console-elements-console-drawer-hello-world.msft.png":::
   <span data-ttu-id="c500b-124">**ドローワ**の [**コンソール**] タブ</span><span class="sxs-lookup"><span data-stu-id="c500b-124">The **Console** tab in the **Drawer**</span></span>  
:::image-end:::  

<span data-ttu-id="c500b-125">[コマンドメニュー][DevToolsCommandMenu]から [コンソール] タブを開くには、入力を開始してから `Console` 、横にある**ドローワ**バッジが付いている [ **console を表示**] コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c500b-125">To open the Console tab from the [Command Menu][DevToolsCommandMenu], start typing `Console` and then run the **Show Console** command that has the **Drawer** badge next to it.</span></span>  

:::image type="complex" source="../media/console-command-menu-show-console.msft.png" alt-text="[コンソール] タブをドローワに表示するコマンド" lightbox="../media/console-command-menu-show-console.msft.png":::
   <span data-ttu-id="c500b-127">[**コンソール**] タブを**ドローワ**に表示するコマンド</span><span class="sxs-lookup"><span data-stu-id="c500b-127">The command to show the **Console** tab in the **Drawer**</span></span>  
:::image-end:::  

### <span data-ttu-id="c500b-128">コンソールの設定を開く</span><span class="sxs-lookup"><span data-stu-id="c500b-128">Open Console Settings</span></span>   

<span data-ttu-id="c500b-129">[ **コンソールの設定** ] ( ![ コンソール ][ImageSettingsButtonIcon] の設定) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c500b-129">Click **Console Settings** \(![Console Settings][ImageSettingsButtonIcon]\).</span></span>  

:::image type="complex" source="../media/console-settings-group-similar-empty.msft.png" alt-text="本体の設定" lightbox="../media/console-settings-group-similar-empty.msft.png":::
   **<span data-ttu-id="c500b-131">本体の設定</span><span class="sxs-lookup"><span data-stu-id="c500b-131">Console Settings</span></span>**  
:::image-end:::  

<span data-ttu-id="c500b-132">以下のリンクでは、各設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="c500b-132">The links below explain each setting:</span></span>  

*   [**<span data-ttu-id="c500b-133">ネットワークの非表示</span><span class="sxs-lookup"><span data-stu-id="c500b-133">Hide Network</span></span>**](#hide-network-messages)  
*   [**<span data-ttu-id="c500b-134">ログを保存する</span><span class="sxs-lookup"><span data-stu-id="c500b-134">Preserve Log</span></span>**](#persist-messages-across-page-loads)  
*   [**<span data-ttu-id="c500b-135">選択されたコンテキストのみ</span><span class="sxs-lookup"><span data-stu-id="c500b-135">Selected Context Only</span></span>**](#filter-out-messages-from-different-contexts)  
*   [**<span data-ttu-id="c500b-136">類似グループ</span><span class="sxs-lookup"><span data-stu-id="c500b-136">Group Similar</span></span>**](#disable-message-grouping)  
*   [**<span data-ttu-id="c500b-137">ログ XmlHttpRequests</span><span class="sxs-lookup"><span data-stu-id="c500b-137">Log XmlHttpRequests</span></span>**](#log-xhr-and-fetch-requests)  
*   [**<span data-ttu-id="c500b-138">一括評価</span><span class="sxs-lookup"><span data-stu-id="c500b-138">Eager Evaluation</span></span>**](#disable-eager-evaluation)  
*   [**<span data-ttu-id="c500b-139">履歴からのオートコンプリート</span><span class="sxs-lookup"><span data-stu-id="c500b-139">Autocomplete From History</span></span>**](#disable-autocomplete-from-history)  
    
### <span data-ttu-id="c500b-140">コンソールサイドバーを開く</span><span class="sxs-lookup"><span data-stu-id="c500b-140">Open the Console Sidebar</span></span>   

<span data-ttu-id="c500b-141">[ **コンソールサイドバーの表示** ] ![ ][ImageShowConsoleSidebarIcon] をクリックすると、サイドバーが表示され、フィルター処理に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c500b-141">Click **Show Console Sidebar** \(![Show Console Sidebar][ImageShowConsoleSidebarIcon]\) to show the Sidebar, which is useful for filtering.</span></span>  

:::image type="complex" source="../media/console-sidebar-drawer-empty.msft.png" alt-text="本体のサイドバー" lightbox="../media/console-sidebar-drawer-empty.msft.png":::
   <span data-ttu-id="c500b-143">**本体** 記事</span><span class="sxs-lookup"><span data-stu-id="c500b-143">**Console** Sidebar</span></span>  
:::image-end:::  

## <span data-ttu-id="c500b-144">メッセージを表示する</span><span class="sxs-lookup"><span data-stu-id="c500b-144">View messages</span></span>   

<span data-ttu-id="c500b-145">このセクションには、コンソールでのメッセージの表示方法を変更する機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c500b-145">This section contains features that change how messages are presented in the Console.</span></span>  <span data-ttu-id="c500b-146">実践的なチュートリアルについては、「 [メッセージを表示][DevToolsConsoleViewMessages] する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c500b-146">See [View messages][DevToolsConsoleViewMessages] for a hands-on walkthrough.</span></span>  

### <span data-ttu-id="c500b-147">メッセージのグループ化を無効にする</span><span class="sxs-lookup"><span data-stu-id="c500b-147">Disable message grouping</span></span>   

<span data-ttu-id="c500b-148">コンソールの[[設定](#open-console-settings)] を開いて、**同様のグループ**を無効にして、コンソールの既定のメッセージグループ化動作を無効にします。</span><span class="sxs-lookup"><span data-stu-id="c500b-148">[Open Console Settings](#open-console-settings) and disable **Group similar** to disable the default message grouping behavior of the Console.</span></span>  <span data-ttu-id="c500b-149">例については [、「XHR をログに記録する要求を取得](#log-xhr-and-fetch-requests) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c500b-149">See [Log XHR and Fetch requests](#log-xhr-and-fetch-requests) for an example.</span></span>  

### <span data-ttu-id="c500b-150">XHR と Fetch 要求をログに記録する</span><span class="sxs-lookup"><span data-stu-id="c500b-150">Log XHR and Fetch requests</span></span>   

<span data-ttu-id="c500b-151">[[コンソールの設定](#open-console-settings)] を開いて、**ログ XMLHttpRequests**を有効にして、発生した場合に、すべて `XMLHttpRequest` の要求と本体の要求をログに記録し `Fetch` ます。</span><span class="sxs-lookup"><span data-stu-id="c500b-151">[Open Console Settings](#open-console-settings) and enable **Log XMLHttpRequests** to log all `XMLHttpRequest` and `Fetch` requests to the Console as they happen.</span></span>  

:::image type="complex" source="../media/console-xhr-fetch.msft.png" alt-text="XMLHttpRequest と Fetch 要求をログに記録する" lightbox="../media/console-xhr-fetch.msft.png":::
   <span data-ttu-id="c500b-153">ログ `XMLHttpRequest` と `Fetch` 要求</span><span class="sxs-lookup"><span data-stu-id="c500b-153">Log `XMLHttpRequest` and `Fetch` requests</span></span>  
:::image-end:::  
<span data-ttu-id="c500b-154">前の図の上部のメッセージには、 **本体**の既定のグループ化動作が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c500b-154">The top message in previous figure displays the default grouping behavior of the **Console**.</span></span>  <!--  In the following figure, the same log is displayed after [disabling message grouping](#disable-message-grouping).  -->  

<!--  
> ##### Old Figure 9  
> How the logged `XMLHttpRequest` and `Fetch` requests look after ungrouping  
> :::image type="complex" source="../media/console-xhr-fetch-all.msft.png" alt-text="How the logged XMLHttpRequest and Fetch requests look after ungrouping" lightbox="../media/console-xhr-fetch-all.msft.png":::
>    How the logged XMLHttpRequest and Fetch requests look after ungrouping  
> :::image-end:::  
-->  

<!--todo: add example for ungrouping console items  -->  

### <span data-ttu-id="c500b-155">ページの読み込み中にメッセージを保持する</span><span class="sxs-lookup"><span data-stu-id="c500b-155">Persist messages across page loads</span></span>   

<span data-ttu-id="c500b-156">既定では、新しいページを読み込むたびに本体がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="c500b-156">By default the Console clears whenever you load a new page.</span></span>  <span data-ttu-id="c500b-157">ページの読み込み中にメッセージを保持するには、[ [コンソールの設定](#open-console-settings) ] を開き、[ **ログの保持** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="c500b-157">To persist messages across page loads, [Open Console Settings](#open-console-settings) and then enable the **Preserve Log** checkbox.</span></span>  

### <span data-ttu-id="c500b-158">ネットワークメッセージを非表示にする</span><span class="sxs-lookup"><span data-stu-id="c500b-158">Hide network messages</span></span>   

<span data-ttu-id="c500b-159">既定では、ブラウザーはネットワークメッセージを **コンソール**に記録します。</span><span class="sxs-lookup"><span data-stu-id="c500b-159">By default the browser logs network messages to the **Console**.</span></span>  <span data-ttu-id="c500b-160">次の図では、選択されたメッセージは、の HTTP 状態コードを表して `429` います。</span><span class="sxs-lookup"><span data-stu-id="c500b-160">In the following figure, the selected message represents an HTTP status code of `429`.</span></span>  

:::image type="complex" source="../media/console-show-network.msft.png" alt-text="コンソールの429メッセージ" lightbox="../media/console-show-network.msft.png":::
   <span data-ttu-id="c500b-162">`429`**本体**のメッセージ</span><span class="sxs-lookup"><span data-stu-id="c500b-162">A `429` message in the **Console**</span></span>  
:::image-end:::  
<span data-ttu-id="c500b-163">ネットワークメッセージを非表示にするには:</span><span class="sxs-lookup"><span data-stu-id="c500b-163">To hide network messages:</span></span>  

1.  <span data-ttu-id="c500b-164">[[コンソールの設定](#open-console-settings)] を開きます。</span><span class="sxs-lookup"><span data-stu-id="c500b-164">[Open Console Settings](#open-console-settings).</span></span>  
1.  <span data-ttu-id="c500b-165">[ **ネットワークを非表示** にする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="c500b-165">Enable the **Hide Network** checkbox.</span></span>  
    
## <span data-ttu-id="c500b-166">メッセージをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="c500b-166">Filter messages</span></span>   

<span data-ttu-id="c500b-167">コンソールでメッセージをフィルター処理するには、さまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="c500b-167">There are many ways to filter out messages in the Console.</span></span>  

### <span data-ttu-id="c500b-168">ブラウザーメッセージをフィルターで除外する</span><span class="sxs-lookup"><span data-stu-id="c500b-168">Filter out browser messages</span></span>   

<span data-ttu-id="c500b-169">[コンソールのサイドバーを開き](#open-the-console-sidebar) 、[ **ユーザーメッセージ** ] をクリックして、そのページの JavaScript から送信されたメッセージのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="c500b-169">[Open the Console Sidebar](#open-the-console-sidebar) and click **User Messages** to only show messages that came from the JavaScript of the page.</span></span>  

:::image type="complex" source="../media/console-sidebar-drawer-user-messages.msft.png" alt-text="ユーザーメッセージを表示する" lightbox="../media/console-sidebar-drawer-user-messages.msft.png":::
   <span data-ttu-id="c500b-171">ユーザーメッセージを表示する</span><span class="sxs-lookup"><span data-stu-id="c500b-171">View user messages</span></span>  
:::image-end:::  

### <span data-ttu-id="c500b-172">ログレベルでフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="c500b-172">Filter by log level</span></span>   

<span data-ttu-id="c500b-173">DevTools `console.*` は、各メソッドに重大度レベルを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c500b-173">DevTools assigns each `console.*` method a severity level.</span></span>  <span data-ttu-id="c500b-174">4つのレベルがあります。、、、 `Verbose` `Info` `Warning` 、 `Error` です。</span><span class="sxs-lookup"><span data-stu-id="c500b-174">There are 4 levels: `Verbose`, `Info`, `Warning`, and `Error`.</span></span>  <span data-ttu-id="c500b-175">たとえば、 `console.log()` はグループ内にありますが、 `Info` `console.error()` はグループ内にあり `Error` ます。</span><span class="sxs-lookup"><span data-stu-id="c500b-175">For example, `console.log()` is in the `Info` group, whereas `console.error()` is in the `Error` group.</span></span>  <span data-ttu-id="c500b-176">[コンソール API リファレンス][DevToolsConsoleApi]では、適用可能な各メソッドの重大度レベルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c500b-176">The [Console API Reference][DevToolsConsoleApi] describes the severity level of each applicable method.</span></span>  <span data-ttu-id="c500b-177">ブラウザーが本体に記録するすべてのメッセージには、重要度のレベルもあります。</span><span class="sxs-lookup"><span data-stu-id="c500b-177">Every message that the browser logs to the Console has a severity level too.</span></span>  <span data-ttu-id="c500b-178">目的のメッセージのレベルをすべて非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c500b-178">You may hide any level of messages that you are not interested in.</span></span>  <span data-ttu-id="c500b-179">たとえば、メッセージだけを知りたい場合は、 `Error` 他の3つのグループを非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c500b-179">For example, if you are only interested in `Error` messages, you may hide the other 3 groups.</span></span>  

<span data-ttu-id="c500b-180">[ **ログレベル** ] ドロップダウンをクリックして、 `Verbose` `Info` `Warning` またはメッセージを有効または無効にし `Error` ます。</span><span class="sxs-lookup"><span data-stu-id="c500b-180">Click the **Log Levels** dropdown to enable or disable `Verbose`, `Info`, `Warning` or `Error` messages.</span></span>  

:::image type="complex" source="../media/console-log-level-default-levels.msft.png" alt-text="[ログレベル] ドロップダウン" lightbox="../media/console-log-level-default-levels.msft.png":::
   <span data-ttu-id="c500b-182">[ **ログレベル** ] ドロップダウン</span><span class="sxs-lookup"><span data-stu-id="c500b-182">The **Log Levels** dropdown</span></span>  
:::image-end:::  

<span data-ttu-id="c500b-183">また、 [コンソールサイドバーを開い](#open-the-console-sidebar) て、[ **エラー**]、[ **警告**]、[ **情報**]、または [ **詳細**] をクリックして、ログレベルでフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="c500b-183">You may also filter by log level by [opening the Console Sidebar](#open-the-console-sidebar) and then clicking **Errors**, **Warnings**, **Info**, or **Verbose**.</span></span>  

:::image type="complex" source="../media/console-sidebar-warnings.msft.png" alt-text="サイドバーを使用して警告を表示する" lightbox="../media/console-sidebar-warnings.msft.png":::
   <span data-ttu-id="c500b-185">サイドバーを使用して警告を表示する</span><span class="sxs-lookup"><span data-stu-id="c500b-185">Use the Sidebar to view warnings</span></span>  
:::image-end:::  

### <span data-ttu-id="c500b-186">URL でメッセージをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="c500b-186">Filter messages by URL</span></span>   

<span data-ttu-id="c500b-187">その URL を入力すると、その URL に由来する `url:` メッセージのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c500b-187">Type `url:` followed by a URL to only view messages that came from that URL.</span></span>  <span data-ttu-id="c500b-188">「Devtools」と入力すると、 `url:` 関連するすべての url が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c500b-188">After you type `url:` DevTools shows all relevant URLs.</span></span>  <span data-ttu-id="c500b-189">ドメインも機能します。</span><span class="sxs-lookup"><span data-stu-id="c500b-189">Domains also work.</span></span>  <span data-ttu-id="c500b-190">たとえば、 `https://example.com/a.js` `https://example.com/b.js` メッセージがログに記録されている場合は、 `url:https://example.com` これら2つのスクリプトからのメッセージに集中することができます。</span><span class="sxs-lookup"><span data-stu-id="c500b-190">For example, if `https://example.com/a.js` and `https://example.com/b.js` are logging messages, `url:https://example.com` enables you to focus on the messages from these 2 scripts.</span></span>  

:::image type="complex" source="../media/console-filter-text.msft.png" alt-text="URL フィルター" lightbox="../media/console-filter-text.msft.png":::
   <span data-ttu-id="c500b-192">URL フィルター</span><span class="sxs-lookup"><span data-stu-id="c500b-192">A URL filter</span></span>  
:::image-end:::  

<span data-ttu-id="c500b-193">`-url:`その URL からのメッセージを非表示にするように入力します。</span><span class="sxs-lookup"><span data-stu-id="c500b-193">Type `-url:` to hide messages from that URL.</span></span>  <span data-ttu-id="c500b-194">これは、否定 URL フィルターと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="c500b-194">This is called a negative URL filter.</span></span>  

:::image type="complex" source="../media/console-negative-filter-text.msft.png" alt-text="Url に一致するすべてのメッセージを非表示にする負の URL フィルター https://b.wal.co" lightbox="../media/console-negative-filter-text.msft.png":::
   <span data-ttu-id="c500b-196">Url に一致するすべてのメッセージを非表示にする負の URL フィルター `https://b.wal.co`</span><span class="sxs-lookup"><span data-stu-id="c500b-196">A negative URL filter that hides all messages that match the `https://b.wal.co` URL</span></span>
:::image-end:::  

<span data-ttu-id="c500b-197">[コンソールサイドバーを開い](#open-the-console-sidebar)て、[**ユーザーメッセージ**] セクションを展開し、フォーカスを移動するメッセージを含むスクリプトの url をクリックして、1つの url からのメッセージを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="c500b-197">You may also show messages from a single URL by [opening the Console Sidebar](#open-the-console-sidebar), expanding the **User Messages** section, and then clicking the URL of the script containing the messages on which you want to focus.</span></span>  

:::image type="complex" source="../media/console-filter-text-specified.msft.png" alt-text="wp-ad.min.js から送信されたメッセージを表示する" lightbox="../media/console-filter-text-specified.msft.png":::
   <span data-ttu-id="c500b-199">送信元のメッセージを表示する</span><span class="sxs-lookup"><span data-stu-id="c500b-199">View the messages that came from</span></span> `wp-ad.min.js`  
:::image-end:::  

### <span data-ttu-id="c500b-200">さまざまなコンテキストからのメッセージをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="c500b-200">Filter out messages from different contexts</span></span>   

<span data-ttu-id="c500b-201">ページに広告 \ (広告 \) があるものとします。</span><span class="sxs-lookup"><span data-stu-id="c500b-201">Suppose that you have an advertisement \(ad\) on your page.</span></span>  <span data-ttu-id="c500b-202">広告がに埋め込まれていて、 `<iframe>` 本体に大量のメッセージが生成されています。</span><span class="sxs-lookup"><span data-stu-id="c500b-202">The ad is embedded in an `<iframe>` and is generating a lot of messages in your Console.</span></span>  <span data-ttu-id="c500b-203">広告は別の [JavaScript コンテキスト](#select-javascript-context)で実行されているため、メッセージを非表示にする方法の1つとして、 [コンソール設定を開い](#open-console-settings) て、 **選択したコンテキストのみ** のチェックボックスを有効にする方法があります。</span><span class="sxs-lookup"><span data-stu-id="c500b-203">Because the ad is running in a different [JavaScript context](#select-javascript-context), one way to hide the messages is to [open Console Settings](#open-console-settings) and enable the **Selected Context Only** checkbox.</span></span>  

### <span data-ttu-id="c500b-204">正規表現パターンに一致しないメッセージをフィルターで除外する</span><span class="sxs-lookup"><span data-stu-id="c500b-204">Filter out messages that do not match a regular expression pattern</span></span>   

<span data-ttu-id="c500b-205">[ `/[gm][ta][mi]/` **フィルター** ] テキストボックスに、そのパターンに一致しないすべてのメッセージをフィルター処理するための正規表現を入力します。</span><span class="sxs-lookup"><span data-stu-id="c500b-205">Type a regular expression such as `/[gm][ta][mi]/` in the **Filter** text box to filter out any messages that do not match that pattern.</span></span>  <span data-ttu-id="c500b-206">DevTools は、メッセージテキストまたはメッセージの記録を引き起こしたスクリプトで、パターンが検出されたかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="c500b-206">DevTools checks if the pattern is found in the message text or the script that caused the message to be logged.</span></span>  

:::image type="complex" source="../media/console-filter-regex.msft.png" alt-text="Regex の式と一致しないメッセージをすべてフィルターで除外する" lightbox="../media/console-filter-regex.msft.png":::
   <span data-ttu-id="c500b-208">Regex の式に一致しないメッセージをすべてフィルターで除外する `/[gm][ta][mi]/`</span><span class="sxs-lookup"><span data-stu-id="c500b-208">Filter out any messages that do not match the `/[gm][ta][mi]/` regex expression</span></span>  
:::image-end:::  

## <span data-ttu-id="c500b-209">JavaScript の実行</span><span class="sxs-lookup"><span data-stu-id="c500b-209">Run JavaScript</span></span>   

<span data-ttu-id="c500b-210">このセクションには、本体での JavaScript の実行に関連する機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c500b-210">This section contains features related to running JavaScript in the Console.</span></span>  <span data-ttu-id="c500b-211">実践的なチュートリアルについては、「 [JavaScript を実行][DevToolsConsoleOverviewJavascript] する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c500b-211">See [Run JavaScript][DevToolsConsoleOverviewJavascript] for a hands-on walkthrough.</span></span>  

### <span data-ttu-id="c500b-212">履歴からの式の再実行</span><span class="sxs-lookup"><span data-stu-id="c500b-212">Re-run expressions from history</span></span>   

<span data-ttu-id="c500b-213">キーを押して、 `Up Arrow` コンソールで前に実行した JavaScript 式の履歴を順に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="c500b-213">Press the `Up Arrow` key to cycle through the history of JavaScript expressions that you ran earlier in the Console.</span></span>  <span data-ttu-id="c500b-214">を押して `Enter` その式を再実行します。</span><span class="sxs-lookup"><span data-stu-id="c500b-214">Press `Enter` to run that expression again.</span></span>  

### <span data-ttu-id="c500b-215">ライブ式を使用して、式の値をリアルタイムで見る</span><span class="sxs-lookup"><span data-stu-id="c500b-215">Watch the value of an expression in real-time with Live Expressions</span></span>   

<span data-ttu-id="c500b-216">コンソールで同じ JavaScript 式を繰り返し入力したことがわかった場合は、 **ライブ式**の作成が簡単になることがあります。</span><span class="sxs-lookup"><span data-stu-id="c500b-216">If you find yourself typing the same JavaScript expression in the Console repeatedly, you may find it easier to create a **Live Expression**.</span></span>  <span data-ttu-id="c500b-217">**ライブ式**で式を1回入力し、本体の先頭に固定します。</span><span class="sxs-lookup"><span data-stu-id="c500b-217">With **Live Expressions** you type an expression once and then pin it to the top of your Console.</span></span>  <span data-ttu-id="c500b-218">この式の値は、ほぼリアルタイムで更新されます。</span><span class="sxs-lookup"><span data-stu-id="c500b-218">The value of the expression updates in near real-time.</span></span>  <span data-ttu-id="c500b-219">詳しく [は、「ライブ式を使って JavaScript の式値をリアルタイムで見る][DevToolsConsoleLiveExpressions]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c500b-219">See [Watch JavaScript Expression Values In Real-Time With Live Expressions][DevToolsConsoleLiveExpressions].</span></span>  

### <span data-ttu-id="c500b-220">一括評価を無効にする</span><span class="sxs-lookup"><span data-stu-id="c500b-220">Disable Eager Evaluation</span></span>   

<span data-ttu-id="c500b-221">本体に JavaScript の式を入力すると、その式の戻り値のプレビュー **が表示さ** れます。</span><span class="sxs-lookup"><span data-stu-id="c500b-221">As you type JavaScript expressions in the Console, **Eager Evaluation** shows a preview of the return value for that expression.</span></span>  <span data-ttu-id="c500b-222">[[本体の設定](#open-console-settings)] を開き、[先行の**評価**] チェックボックスをオフにして戻り値のプレビューをオフにします。</span><span class="sxs-lookup"><span data-stu-id="c500b-222">[Open Console Settings](#open-console-settings) and disable the **Eager Evaluation** checkbox to turn off the return value previews.</span></span>  

### <span data-ttu-id="c500b-223">履歴からオートコンプリートを無効にする</span><span class="sxs-lookup"><span data-stu-id="c500b-223">Disable autocomplete from history</span></span>   

<span data-ttu-id="c500b-224">式を入力すると、本体の [オートコンプリート] ポップアップウィンドウに、前に実行した式が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c500b-224">As you type out an expression, the autocomplete popup window for the Console shows expressions that you ran earlier.</span></span>  <span data-ttu-id="c500b-225">これらの式は文字で先頭に付けられ `>` ます。</span><span class="sxs-lookup"><span data-stu-id="c500b-225">These expressions are prepended with the `>` character.</span></span>  <span data-ttu-id="c500b-226">[[コンソールの設定](#open-console-settings)] を開いて、[履歴の**オートコンプリート**] チェックボックスをオフにして、履歴からの式の表示を停止します。</span><span class="sxs-lookup"><span data-stu-id="c500b-226">[Open Console Settings](#open-console-settings) and disable the **Autocomplete From History** checkbox to stop showing expressions from your history.</span></span>  

> [!NOTE]
> <span data-ttu-id="c500b-227">次の図で `document.querySelector('a')` は、 `document.querySelector('img')` 前に評価された式を示します。</span><span class="sxs-lookup"><span data-stu-id="c500b-227">In the following figure, `document.querySelector('a')` and `document.querySelector('img')` are expressions that were evaluated earlier.</span></span>  

:::image type="complex" source="../media/console-filter-text-autofilter-history.msft.png" alt-text="オートコンプリートのポップアップには、履歴の式が表示される" lightbox="../media/console-filter-text-autofilter-history.msft.png":::
   <span data-ttu-id="c500b-229">オートコンプリートのポップアップには、履歴の式が表示される</span><span class="sxs-lookup"><span data-stu-id="c500b-229">The autocomplete popup displays expressions from history</span></span>  
:::image-end:::  

### <span data-ttu-id="c500b-230">JavaScript のコンテキストを選ぶ</span><span class="sxs-lookup"><span data-stu-id="c500b-230">Select JavaScript context</span></span>   

<span data-ttu-id="c500b-231">既定では、 **JavaScript コンテキスト** のドロップダウンは [ **先頭**] に設定されています。これは、メインドキュメントの [閲覧コンテキスト][MDNBrowsingContext] を表します。</span><span class="sxs-lookup"><span data-stu-id="c500b-231">By default the **JavaScript Context** dropdown is set to **top**, which represents the [browsing context][MDNBrowsingContext] of the main document.</span></span>  

:::image type="complex" source="../media/console-dom-level-top.msft.png" alt-text="JavaScript コンテキストのドロップダウン" lightbox="../media/console-dom-level-top.msft.png":::
   <span data-ttu-id="c500b-233">**JavaScript コンテキスト**のドロップダウン</span><span class="sxs-lookup"><span data-stu-id="c500b-233">The **JavaScript Context** dropdown</span></span>  
:::image-end:::  

<span data-ttu-id="c500b-234">ページに広告が埋め込まれていると `<iframe>` します。</span><span class="sxs-lookup"><span data-stu-id="c500b-234">Suppose you have an ad on your page embedded in an `<iframe>`.</span></span>  <span data-ttu-id="c500b-235">広告の DOM を調整するために JavaScript を実行します。</span><span class="sxs-lookup"><span data-stu-id="c500b-235">You want to run JavaScript in order to tweak the DOM of the ad.</span></span>  <span data-ttu-id="c500b-236">まず、 **JavaScript のコンテキスト** ドロップダウンから広告の閲覧コンテキストを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c500b-236">You should first select the browsing context of the ad from the **JavaScript Context** dropdown.</span></span>  

:::image type="complex" source="../media/console-dom-level-multiple.msft.png" alt-text="別の JavaScript コンテキストを選択する" lightbox="../media/console-dom-level-multiple.msft.png":::
   <span data-ttu-id="c500b-238">別の JavaScript コンテキストを選択する</span><span class="sxs-lookup"><span data-stu-id="c500b-238">Select a different JavaScript context</span></span>  
:::image-end:::  

## <span data-ttu-id="c500b-239">本体をクリアする</span><span class="sxs-lookup"><span data-stu-id="c500b-239">Clear the Console</span></span>   

<span data-ttu-id="c500b-240">次のいずれかのワークフローを使用して本体をクリアすることができます。</span><span class="sxs-lookup"><span data-stu-id="c500b-240">You may use any of the following workflows to clear the Console:</span></span>  

*   <span data-ttu-id="c500b-241">[ **コンソールのクリア** ] ( ![ コンソール ][ImageClearConsoleIcon] のクリア) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c500b-241">Click **Clear Console** \(![Clear Console][ImageClearConsoleIcon]\).</span></span>  
*   <span data-ttu-id="c500b-242">メッセージを右クリックし、[ **コンソールのクリア**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c500b-242">Right-click a message and then select **Clear Console**.</span></span>  
*   <span data-ttu-id="c500b-243">`clear()`コンソールに入力して、キーを押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="c500b-243">Type `clear()` in the Console and then press `Enter`.</span></span>  
*   <span data-ttu-id="c500b-244">`console.clear()`Web ページの JavaScript から通話を発信します。</span><span class="sxs-lookup"><span data-stu-id="c500b-244">Call `console.clear()` from the JavaScript for your webpage.</span></span>  
*   <span data-ttu-id="c500b-245">`Control` + `L` コンソールがフォーカスされているときにを押します。</span><span class="sxs-lookup"><span data-stu-id="c500b-245">Press `Control`+`L` while the Console is in focus.</span></span>  
    
<!--
 

  
-->  

<!-- image links -->  

[ImageClearConsoleIcon]: ../media/clear-console-button-icon.msft.png  
[ImageSettingsButtonIcon]: ../media/settings-button-icon.msft.png  
[ImageShowConsoleSidebarIcon]: ../media/show-console-sidebar-icon.msft.png  

<!-- links -->  

[DevToolsCommandMenu]: ../command-menu/index.md "Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する |Microsoft ドキュメント"  
[DevToolsConsoleViewMessages]: ./index.md#viewing-logged-messages "ログメッセージの表示-本体の概要 |Microsoft ドキュメント"  
[DevToolsConsoleApi]: ./api.md "コンソール API リファレンス |Microsoft ドキュメント"  
[DevToolsConsoleOverviewJavascript]: ./index.md#running-javascript "JavaScript の実行-本体の概要 |Microsoft ドキュメント"  
[DevToolsConsoleJavascript]: ./javascript.md "本体の JavaScript の実行を開始する |Microsoft ドキュメント"  
[DevToolsConsoleLiveExpressions]: ./live-expressions.md "ライブ式を使用して JavaScript の式値をリアルタイムで見る |Microsoft ドキュメント"  
[DevToolsConsoleLog]: ./log.md "コンソールでのメッセージの記録を開始する |Microsoft ドキュメント"  
[DevToolsConsoleUtilities]: ./utilities.md "コンソールユーティリティ API リファレンス |Microsoft ドキュメント"  

[MDNBrowsingContext]: https://developer.mozilla.org/docs/Glossary/Browsing_context "ブラウジングコンテキスト |MDN"  

> [!NOTE]
> <span data-ttu-id="c500b-255">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="c500b-255">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="c500b-256">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/console/reference) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="c500b-256">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="c500b-258">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="c500b-258">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
