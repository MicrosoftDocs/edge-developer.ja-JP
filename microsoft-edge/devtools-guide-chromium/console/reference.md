---
title: 本体のリファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: bd2a610b48905c6651663d490b9c9f1a0a8c7674
ms.sourcegitcommit: 5cdc1626d5581b79c0f2ac4ea62e7f1974ebfa57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "10601787"
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





# <span data-ttu-id="c2d95-103">本体のリファレンス</span><span class="sxs-lookup"><span data-stu-id="c2d95-103">Console Reference</span></span>   



<span data-ttu-id="c2d95-104">このページでは、Microsoft Edge DevTools コンソールに関連する機能のリファレンスを示します。</span><span class="sxs-lookup"><span data-stu-id="c2d95-104">This page is a reference of features related to the Microsoft Edge DevTools Console.</span></span>  <span data-ttu-id="c2d95-105">ログに記録されたメッセージを表示して JavaScript を実行するには、既にコンソールを使用していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="c2d95-105">It assumes that you are already familiar with using the Console to view logged messages and run JavaScript.</span></span>  <span data-ttu-id="c2d95-106">表示されない場合は、「[コンソールでの JavaScript の実行を開始する][DevToolsConsoleJavascript]」を参照してください。[コンソールでのメッセージの記録を開始][DevToolsConsoleLog]します。</span><span class="sxs-lookup"><span data-stu-id="c2d95-106">If not, see [Get Started With Running JavaScript In The Console][DevToolsConsoleJavascript] and [Get Started With Logging Messages In The Console][DevToolsConsoleLog].</span></span>  

<span data-ttu-id="c2d95-107">API 参照を検索する場合は、 `console.log()` 「[コンソール API リファレンス][DevToolsConsoleApi]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c2d95-107">If you are looking for the API reference on functions like `console.log()` see [Console API Reference][DevToolsConsoleApi].</span></span>  <span data-ttu-id="c2d95-108">`monitorEvents()`「[コンソールユーティリティ API リファレンス][DevToolsConsoleUtilities]」などの関数のリファレンスについては、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2d95-108">For the reference on functions like `monitorEvents()` see [Console Utilities API Reference][DevToolsConsoleUtilities].</span></span>  

## <span data-ttu-id="c2d95-109">本体を開く</span><span class="sxs-lookup"><span data-stu-id="c2d95-109">Open the Console</span></span>   

<span data-ttu-id="c2d95-110">コンソールは、引き出しの[パネル](#open-the-console-panel)または[タブ](#open-the-console-tab-in-the-drawer)として開くことができます。</span><span class="sxs-lookup"><span data-stu-id="c2d95-110">You may open the Console as a [panel](#open-the-console-panel) or as a [tab in the Drawer](#open-the-console-tab-in-the-drawer).</span></span>  

### <span data-ttu-id="c2d95-111">コンソールパネルを開く</span><span class="sxs-lookup"><span data-stu-id="c2d95-111">Open the Console panel</span></span>   

<span data-ttu-id="c2d95-112">`Control` + `Shift` + `J` \ (Windows \) または `Command` + `Option` + `J` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="c2d95-112">Press `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\).</span></span>  

> ##### <span data-ttu-id="c2d95-113">図 1</span><span class="sxs-lookup"><span data-stu-id="c2d95-113">Figure 1</span></span>  
> <span data-ttu-id="c2d95-114">コンソールパネル</span><span class="sxs-lookup"><span data-stu-id="c2d95-114">The Console panel</span></span>  
> ![コンソールパネル][ImageConsolePanel]  

<span data-ttu-id="c2d95-116">[コマンドメニュー][DevToolsCommandMenu]からコンソールパネルを開くには、入力を開始してから `Console` 、その横にある**パネル**バッジのある [**コンソールの表示**] コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c2d95-116">To open the Console panel from the [Command Menu][DevToolsCommandMenu], start typing `Console` and then run the **Show Console** command that has the **Panel** badge next to it.</span></span>  

> ##### <span data-ttu-id="c2d95-117">図 2</span><span class="sxs-lookup"><span data-stu-id="c2d95-117">Figure 2</span></span>  
> <span data-ttu-id="c2d95-118">コンソールパネルを表示するためのコマンド</span><span class="sxs-lookup"><span data-stu-id="c2d95-118">The command for showing the Console panel</span></span>  
> ![コンソールパネルを表示するためのコマンド][ImageCommandShowConsole]  

### <span data-ttu-id="c2d95-120">ドロワーで [コンソール] タブを開く</span><span class="sxs-lookup"><span data-stu-id="c2d95-120">Open the Console tab in the Drawer</span></span>   

<span data-ttu-id="c2d95-121">[ `Escape` **カスタマイズと制御**] をクリックして、[ `...` **コンソールドローワの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2d95-121">Press `Escape` or click **Customize And Control DevTools** `...` and then select **Show console drawer**.</span></span>  

> ##### <span data-ttu-id="c2d95-122">図 3</span><span class="sxs-lookup"><span data-stu-id="c2d95-122">Figure 3</span></span>  
> <span data-ttu-id="c2d95-123">コンソールのドローワを表示</span><span class="sxs-lookup"><span data-stu-id="c2d95-123">Show console drawer</span></span>  
> ![コンソールのドローワを表示][ImageShowConsoleDrawer]  

<span data-ttu-id="c2d95-125">[**コンソール**] タブを開いた状態で、[devtools] ウィンドウの下部に引き出しがポップアップ表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2d95-125">The Drawer pops up at the bottom of your DevTools window, with the **Console** tab open.</span></span>  

> ##### <span data-ttu-id="c2d95-126">図 4</span><span class="sxs-lookup"><span data-stu-id="c2d95-126">Figure 4</span></span>  
> <span data-ttu-id="c2d95-127">ドローワの [コンソール] タブ</span><span class="sxs-lookup"><span data-stu-id="c2d95-127">The Console tab in the Drawer</span></span>  
> ![ドローワの [コンソール] タブ][ImageDrawerConsole]  

<span data-ttu-id="c2d95-129">[コマンドメニュー][DevToolsCommandMenu]から [コンソール] タブを開くには、入力を開始してから `Console` 、横にある**ドローワ**バッジが付いている [ **console を表示**] コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c2d95-129">To open the Console tab from the [Command Menu][DevToolsCommandMenu], start typing `Console` and then run the **Show Console** command that has the **Drawer** badge next to it.</span></span>  

> ##### <span data-ttu-id="c2d95-130">図 5</span><span class="sxs-lookup"><span data-stu-id="c2d95-130">Figure 5</span></span>  
> <span data-ttu-id="c2d95-131">ドロワーの [コンソール] タブを表示するためのコマンド</span><span class="sxs-lookup"><span data-stu-id="c2d95-131">The command for showing the Console tab in the Drawer</span></span>  
> ![ドロワーの [コンソール] タブを表示するためのコマンド][ImageShowDrawerCommand]  

### <span data-ttu-id="c2d95-133">コンソールの設定を開く</span><span class="sxs-lookup"><span data-stu-id="c2d95-133">Open Console Settings</span></span>   

<span data-ttu-id="c2d95-134">[**本体の設定**] ![ コンソール設定をクリックし ][ImageSettingsButtonIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="c2d95-134">Click **Console Settings** ![Console Settings][ImageSettingsButtonIcon].</span></span>  

> ##### <span data-ttu-id="c2d95-135">図 6</span><span class="sxs-lookup"><span data-stu-id="c2d95-135">Figure 6</span></span>  
> <span data-ttu-id="c2d95-136">本体の設定</span><span class="sxs-lookup"><span data-stu-id="c2d95-136">Console Settings</span></span>  
> ![本体の設定][ImageConsoleSettings]  

<span data-ttu-id="c2d95-138">以下のリンクでは、各設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="c2d95-138">The links below explain each setting:</span></span>  

*   [**<span data-ttu-id="c2d95-139">ネットワークの非表示</span><span class="sxs-lookup"><span data-stu-id="c2d95-139">Hide Network</span></span>**](#hide-network-messages)  
*   [**<span data-ttu-id="c2d95-140">ログを保存する</span><span class="sxs-lookup"><span data-stu-id="c2d95-140">Preserve Log</span></span>**](#persist-messages-across-page-loads)  
*   [**<span data-ttu-id="c2d95-141">選択されたコンテキストのみ</span><span class="sxs-lookup"><span data-stu-id="c2d95-141">Selected Context Only</span></span>**](#filter-out-messages-from-different-contexts)  
*   [**<span data-ttu-id="c2d95-142">類似グループ</span><span class="sxs-lookup"><span data-stu-id="c2d95-142">Group Similar</span></span>**](#disable-message-grouping)  
*   [**<span data-ttu-id="c2d95-143">ログ XmlHttpRequests</span><span class="sxs-lookup"><span data-stu-id="c2d95-143">Log XmlHttpRequests</span></span>**](#log-xhr-and-fetch-requests)  
*   [**<span data-ttu-id="c2d95-144">一括評価</span><span class="sxs-lookup"><span data-stu-id="c2d95-144">Eager Evaluation</span></span>**](#disable-eager-evaluation)  
*   [**<span data-ttu-id="c2d95-145">履歴からのオートコンプリート</span><span class="sxs-lookup"><span data-stu-id="c2d95-145">Autocomplete From History</span></span>**](#disable-autocomplete-from-history)  

### <span data-ttu-id="c2d95-146">コンソールサイドバーを開く</span><span class="sxs-lookup"><span data-stu-id="c2d95-146">Open the Console Sidebar</span></span>   

<span data-ttu-id="c2d95-147">[**コンソールサイドバーの表示**] ![ をクリックすると ][ImageShowConsoleSidebarIcon] 、サイドバーが表示され、フィルター処理に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c2d95-147">Click **Show Console Sidebar** ![Show Console Sidebar][ImageShowConsoleSidebarIcon] to show the Sidebar, which is useful for filtering.</span></span>  

> ##### <span data-ttu-id="c2d95-148">図 7</span><span class="sxs-lookup"><span data-stu-id="c2d95-148">Figure 7</span></span>  
> <span data-ttu-id="c2d95-149">本体のサイドバー</span><span class="sxs-lookup"><span data-stu-id="c2d95-149">Console Sidebar</span></span>  
> ![本体のサイドバー][ImageConsoleSidebar]  

## <span data-ttu-id="c2d95-151">メッセージを表示する</span><span class="sxs-lookup"><span data-stu-id="c2d95-151">View messages</span></span>   

<span data-ttu-id="c2d95-152">このセクションには、コンソールでのメッセージの表示方法を変更する機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c2d95-152">This section contains features that change how messages are presented in the Console.</span></span>  <span data-ttu-id="c2d95-153">実践的なチュートリアルについては、「[メッセージを表示][DevToolsConsoleViewMessages]する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c2d95-153">See [View messages][DevToolsConsoleViewMessages] for a hands-on walkthrough.</span></span>  

### <span data-ttu-id="c2d95-154">メッセージのグループ化を無効にする</span><span class="sxs-lookup"><span data-stu-id="c2d95-154">Disable message grouping</span></span>   

<span data-ttu-id="c2d95-155">コンソールの[[設定](#open-console-settings)] を開いて、**同様のグループ**を無効にして、コンソールの既定のメッセージグループ化動作を無効にします。</span><span class="sxs-lookup"><span data-stu-id="c2d95-155">[Open Console Settings](#open-console-settings) and disable **Group similar** to disable the default message grouping behavior of the Console.</span></span>  <span data-ttu-id="c2d95-156">例については[、「XHR をログに記録する要求を取得](#log-xhr-and-fetch-requests)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2d95-156">See [Log XHR and Fetch requests](#log-xhr-and-fetch-requests) for an example.</span></span>  

### <span data-ttu-id="c2d95-157">XHR と Fetch 要求をログに記録する</span><span class="sxs-lookup"><span data-stu-id="c2d95-157">Log XHR and Fetch requests</span></span>   

<span data-ttu-id="c2d95-158">[[コンソールの設定](#open-console-settings)] を開いて、**ログ XMLHttpRequests**を有効にして、発生した場合に、すべて `XMLHttpRequest` の要求と本体の要求をログに記録し `Fetch` ます。</span><span class="sxs-lookup"><span data-stu-id="c2d95-158">[Open Console Settings](#open-console-settings) and enable **Log XMLHttpRequests** to log all `XMLHttpRequest` and `Fetch` requests to the Console as they happen.</span></span>  

> ##### <span data-ttu-id="c2d95-159">図 8</span><span class="sxs-lookup"><span data-stu-id="c2d95-159">Figure 8</span></span>  
> <span data-ttu-id="c2d95-160">ログ `XMLHttpRequest` と `Fetch` 要求</span><span class="sxs-lookup"><span data-stu-id="c2d95-160">Logging `XMLHttpRequest` and `Fetch` requests</span></span>  
> ![XMLHttpRequest とフェッチ要求のログ記録][ImageXhrGrouped]  

<span data-ttu-id="c2d95-162">[図 8](#figure-8)の上位のメッセージは、本体の既定のグループ化動作を示しています。</span><span class="sxs-lookup"><span data-stu-id="c2d95-162">The top message in [Figure 8](#figure-8) shows the default grouping behavior of the Console.</span></span>  <!--  [Figure 9](#figure-9) shows how the same log looks after [disabling message grouping](#disable-message-grouping).  -->  

<!--

> ##### Old Figure 9  
> How the logged `XMLHttpRequest` and `Fetch` requests look after ungrouping  
> ![How the logged XMLHttpRequest and Fetch requests look after ungrouping][ImageXhrUngrouped]  

-->

<!--todo: add example for ungrouping console items  -->  

### <span data-ttu-id="c2d95-163">ページの読み込み中にメッセージを保持する</span><span class="sxs-lookup"><span data-stu-id="c2d95-163">Persist messages across page loads</span></span>   

<span data-ttu-id="c2d95-164">既定では、新しいページを読み込むたびに本体がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="c2d95-164">By default the Console clears whenever you load a new page.</span></span>  <span data-ttu-id="c2d95-165">ページの読み込み中にメッセージを保持するには、[[コンソールの設定](#open-console-settings)] を開き、[**ログの保持**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="c2d95-165">To persist messages across page loads, [Open Console Settings](#open-console-settings) and then enable the **Preserve Log** checkbox.</span></span>  

### <span data-ttu-id="c2d95-166">ネットワークメッセージを非表示にする</span><span class="sxs-lookup"><span data-stu-id="c2d95-166">Hide network messages</span></span>   

<span data-ttu-id="c2d95-167">既定では、ブラウザーはネットワークメッセージを**コンソール**に記録します。</span><span class="sxs-lookup"><span data-stu-id="c2d95-167">By default the browser logs network messages to the **Console**.</span></span>  <span data-ttu-id="c2d95-168">たとえば、[図 9](#figure-9)で選んだメッセージは、の状態コードを表し `429` ます。</span><span class="sxs-lookup"><span data-stu-id="c2d95-168">For example, the selected message in [Figure 9](#figure-9) represents a status code of `429`.</span></span>  

> ##### <span data-ttu-id="c2d95-169">図 9</span><span class="sxs-lookup"><span data-stu-id="c2d95-169">Figure 9</span></span>  
> <span data-ttu-id="c2d95-170">コンソールの429メッセージ</span><span class="sxs-lookup"><span data-stu-id="c2d95-170">A 429 message in the Console</span></span>  
> <span data-ttu-id="c2d95-171">![コンソールの429メッセージ][Image429Message]</span><span class="sxs-lookup"><span data-stu-id="c2d95-171">![A 429 message in the Console][Image429Message]</span></span>  

<span data-ttu-id="c2d95-172">ネットワークメッセージを非表示にするには:</span><span class="sxs-lookup"><span data-stu-id="c2d95-172">To hide network messages:</span></span>  

1.  <span data-ttu-id="c2d95-173">[[コンソールの設定](#open-console-settings)] を開きます。</span><span class="sxs-lookup"><span data-stu-id="c2d95-173">[Open Console Settings](#open-console-settings).</span></span>  
1.  <span data-ttu-id="c2d95-174">[**ネットワークを非表示**にする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="c2d95-174">Enable the **Hide Network** checkbox.</span></span>  

## <span data-ttu-id="c2d95-175">メッセージをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="c2d95-175">Filter messages</span></span>   

<span data-ttu-id="c2d95-176">コンソールでメッセージをフィルター処理するには、さまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="c2d95-176">There are many ways to filter out messages in the Console.</span></span>  

### <span data-ttu-id="c2d95-177">ブラウザーメッセージをフィルターで除外する</span><span class="sxs-lookup"><span data-stu-id="c2d95-177">Filter out browser messages</span></span>   

<span data-ttu-id="c2d95-178">[コンソールのサイドバーを開き](#open-the-console-sidebar)、[**ユーザーメッセージ**] をクリックして、そのページの JavaScript から送信されたメッセージのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="c2d95-178">[Open the Console Sidebar](#open-the-console-sidebar) and click **User Messages** to only show messages that came from the JavaScript of the page.</span></span>  

> ##### <span data-ttu-id="c2d95-179">図 10</span><span class="sxs-lookup"><span data-stu-id="c2d95-179">Figure 10</span></span>  
> <span data-ttu-id="c2d95-180">ユーザーメッセージの表示</span><span class="sxs-lookup"><span data-stu-id="c2d95-180">Viewing user messages</span></span>  
> <span data-ttu-id="c2d95-181">![ユーザーメッセージの表示][ImageUserMessages]</span><span class="sxs-lookup"><span data-stu-id="c2d95-181">![Viewing user messages][ImageUserMessages]</span></span>  

### <span data-ttu-id="c2d95-182">ログレベルでフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="c2d95-182">Filter by log level</span></span>   

<span data-ttu-id="c2d95-183">DevTools `console.*` は、各メソッドに重大度レベルを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c2d95-183">DevTools assigns each `console.*` method a severity level.</span></span>  <span data-ttu-id="c2d95-184">4つのレベルがあります。、、、 `Verbose` `Info` `Warning` 、 `Error` です。</span><span class="sxs-lookup"><span data-stu-id="c2d95-184">There are 4 levels: `Verbose`, `Info`, `Warning`, and `Error`.</span></span>  <span data-ttu-id="c2d95-185">たとえば、 `console.log()` はグループ内にありますが、 `Info` `console.error()` はグループ内にあり `Error` ます。</span><span class="sxs-lookup"><span data-stu-id="c2d95-185">For example, `console.log()` is in the `Info` group, whereas `console.error()` is in the `Error` group.</span></span>  <span data-ttu-id="c2d95-186">[コンソール API リファレンス][DevToolsConsoleApi]では、適用可能な各メソッドの重大度レベルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c2d95-186">The [Console API Reference][DevToolsConsoleApi] describes the severity level of each applicable method.</span></span>  <span data-ttu-id="c2d95-187">ブラウザーが本体に記録するすべてのメッセージには、重要度のレベルもあります。</span><span class="sxs-lookup"><span data-stu-id="c2d95-187">Every message that the browser logs to the Console has a severity level too.</span></span>  <span data-ttu-id="c2d95-188">目的のメッセージのレベルをすべて非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c2d95-188">You may hide any level of messages that you are not interested in.</span></span>  <span data-ttu-id="c2d95-189">たとえば、メッセージだけを知りたい場合は、 `Error` 他の3つのグループを非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c2d95-189">For example, if you are only interested in `Error` messages, you may hide the other 3 groups.</span></span>  

<span data-ttu-id="c2d95-190">[**ログレベル**] ドロップダウンをクリックして、 `Verbose` `Info` `Warning` またはメッセージを有効または無効にし `Error` ます。</span><span class="sxs-lookup"><span data-stu-id="c2d95-190">Click the **Log Levels** dropdown to enable or disable `Verbose`, `Info`, `Warning` or `Error` messages.</span></span>  

> ##### <span data-ttu-id="c2d95-191">図 11</span><span class="sxs-lookup"><span data-stu-id="c2d95-191">Figure 11</span></span>  
> <span data-ttu-id="c2d95-192">[**ログレベル**] ドロップダウン</span><span class="sxs-lookup"><span data-stu-id="c2d95-192">The **Log Levels** dropdown</span></span>  
> <span data-ttu-id="c2d95-193">![ログレベル] ドロップダウンリスト[ImageLogLevels]</span><span class="sxs-lookup"><span data-stu-id="c2d95-193">![The Log Levels dropdown][ImageLogLevels]</span></span>  

<span data-ttu-id="c2d95-194">また、[コンソールサイドバーを開い](#open-the-console-sidebar)て、[**エラー**]、[**警告**]、[**情報**]、または [**詳細**] をクリックして、ログレベルでフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="c2d95-194">You may also filter by log level by [opening the Console Sidebar](#open-the-console-sidebar) and then clicking **Errors**, **Warnings**, **Info**, or **Verbose**.</span></span>  

> ##### <span data-ttu-id="c2d95-195">図 12</span><span class="sxs-lookup"><span data-stu-id="c2d95-195">Figure 12</span></span>  
> <span data-ttu-id="c2d95-196">サイドバーを使用して警告を表示する</span><span class="sxs-lookup"><span data-stu-id="c2d95-196">Using the Sidebar to view warnings</span></span>  
> <span data-ttu-id="c2d95-197">![サイドバーを使って警告を表示][ImageSidebarWarnings]</span><span class="sxs-lookup"><span data-stu-id="c2d95-197">![Using the Sidebar to view warnings][ImageSidebarWarnings]</span></span>  

### <span data-ttu-id="c2d95-198">URL でメッセージをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="c2d95-198">Filter messages by URL</span></span>   

<span data-ttu-id="c2d95-199">その URL を入力すると、その URL に由来する `url:` メッセージのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2d95-199">Type `url:` followed by a URL to only view messages that came from that URL.</span></span>  <span data-ttu-id="c2d95-200">「Devtools」と入力すると、 `url:` 関連するすべての url が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2d95-200">After you type `url:` DevTools shows all relevant URLs.</span></span>  <span data-ttu-id="c2d95-201">ドメインも機能します。</span><span class="sxs-lookup"><span data-stu-id="c2d95-201">Domains also work.</span></span>  <span data-ttu-id="c2d95-202">たとえば、 `https://example.com/a.js` `https://example.com/b.js` メッセージがログに記録されている場合は、 `url:https://example.com` これら2つのスクリプトからのメッセージに集中することができます。</span><span class="sxs-lookup"><span data-stu-id="c2d95-202">For example, if `https://example.com/a.js` and `https://example.com/b.js` are logging messages, `url:https://example.com` enables you to focus on the messages from these 2 scripts.</span></span>  

> ##### <span data-ttu-id="c2d95-203">図 13</span><span class="sxs-lookup"><span data-stu-id="c2d95-203">Figure 13</span></span>  
> <span data-ttu-id="c2d95-204">URL フィルター</span><span class="sxs-lookup"><span data-stu-id="c2d95-204">A URL filter</span></span>  
> <span data-ttu-id="c2d95-205">![URL フィルター][ImageUrlFilter]</span><span class="sxs-lookup"><span data-stu-id="c2d95-205">![A URL filter][ImageUrlFilter]</span></span>  

<span data-ttu-id="c2d95-206">`-url:`その URL からのメッセージを非表示にするように入力します。</span><span class="sxs-lookup"><span data-stu-id="c2d95-206">Type `-url:` to hide messages from that URL.</span></span>  <span data-ttu-id="c2d95-207">これは、否定 URL フィルターと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="c2d95-207">This is called a negative URL filter.</span></span>  

> ##### <span data-ttu-id="c2d95-208">図 14</span><span class="sxs-lookup"><span data-stu-id="c2d95-208">Figure 14</span></span>  
> <span data-ttu-id="c2d95-209">URL に一致するすべてのメッセージを非表示にする負の URL フィルター</span><span class="sxs-lookup"><span data-stu-id="c2d95-209">A negative URL filter that hides all messages matching the URL</span></span> `https://b.wal.co`  
> <span data-ttu-id="c2d95-210">![URL に一致するすべてのメッセージを非表示にする負の URL フィルター https://b.wal.co ][ImageNegativeUrlFilter1]</span><span class="sxs-lookup"><span data-stu-id="c2d95-210">![A negative URL filter that hides all messages matching the URL https://b.wal.co][ImageNegativeUrlFilter1]</span></span>  

<span data-ttu-id="c2d95-211">[コンソールサイドバーを開い](#open-the-console-sidebar)て、[**ユーザーメッセージ**] セクションを展開し、フォーカスを移動するメッセージを含むスクリプトの url をクリックして、1つの url からのメッセージを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="c2d95-211">You may also show messages from a single URL by [opening the Console Sidebar](#open-the-console-sidebar), expanding the **User Messages** section, and then clicking the URL of the script containing the messages on which you want to focus.</span></span>  

> ##### <span data-ttu-id="c2d95-212">図 15</span><span class="sxs-lookup"><span data-stu-id="c2d95-212">Figure 15</span></span>  
> <span data-ttu-id="c2d95-213">送信元のメッセージを表示する</span><span class="sxs-lookup"><span data-stu-id="c2d95-213">Viewing the messages that came from</span></span> `wp-ad.min.js`  
> <span data-ttu-id="c2d95-214">![Wp-ad からのメッセージを表示する][ImageNegativeUrlFilter2]</span><span class="sxs-lookup"><span data-stu-id="c2d95-214">![Viewing the messages that came from wp-ad.min.js][ImageNegativeUrlFilter2]</span></span>  

### <span data-ttu-id="c2d95-215">さまざまなコンテキストからのメッセージをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="c2d95-215">Filter out messages from different contexts</span></span>   

<span data-ttu-id="c2d95-216">ページに広告 \ (広告 \) があるものとします。</span><span class="sxs-lookup"><span data-stu-id="c2d95-216">Suppose that you have an advertisement \(ad\) on your page.</span></span>  <span data-ttu-id="c2d95-217">広告がに埋め込まれていて、 `<iframe>` 本体に大量のメッセージが生成されています。</span><span class="sxs-lookup"><span data-stu-id="c2d95-217">The ad is embedded in an `<iframe>` and is generating a lot of messages in your Console.</span></span>  <span data-ttu-id="c2d95-218">広告は別の[JavaScript コンテキスト](#select-javascript-context)で実行されているため、メッセージを非表示にする方法の1つとして、[コンソール設定を開い](#open-console-settings)て、**選択したコンテキストのみ**のチェックボックスを有効にする方法があります。</span><span class="sxs-lookup"><span data-stu-id="c2d95-218">Because the ad is running in a different [JavaScript context](#select-javascript-context), one way to hide the messages is to [open Console Settings](#open-console-settings) and enable the **Selected Context Only** checkbox.</span></span>  

### <span data-ttu-id="c2d95-219">正規表現パターンに一致しないメッセージをフィルターで除外する</span><span class="sxs-lookup"><span data-stu-id="c2d95-219">Filter out messages that do not match a regular expression pattern</span></span>   

<span data-ttu-id="c2d95-220">[ `/[gm][ta][mi]/` **フィルター** ] テキストボックスに、そのパターンに一致しないすべてのメッセージをフィルター処理するための正規表現を入力します。</span><span class="sxs-lookup"><span data-stu-id="c2d95-220">Type a regular expression such as `/[gm][ta][mi]/` in the **Filter** text box to filter out any messages that do not match that pattern.</span></span>  <span data-ttu-id="c2d95-221">DevTools は、メッセージテキストまたはメッセージの記録を引き起こしたスクリプトで、パターンが検出されたかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="c2d95-221">DevTools checks if the pattern is found in the message text or the script that caused the message to be logged.</span></span>  

> ##### <span data-ttu-id="c2d95-222">図 16</span><span class="sxs-lookup"><span data-stu-id="c2d95-222">Figure 16</span></span>  
> <span data-ttu-id="c2d95-223">一致しないメッセージをフィルターで除外する</span><span class="sxs-lookup"><span data-stu-id="c2d95-223">Filtering out any messages that do not match</span></span> `/[gm][ta][mi]/`  
> <span data-ttu-id="c2d95-224">![Regex の式と一致しないメッセージをフィルター処理する][ImageRegExFilter]</span><span class="sxs-lookup"><span data-stu-id="c2d95-224">![Filtering out any messages that do not match regex expression][ImageRegExFilter]</span></span>  

## <span data-ttu-id="c2d95-225">JavaScript を実行する</span><span class="sxs-lookup"><span data-stu-id="c2d95-225">Run JavaScript</span></span>   

<span data-ttu-id="c2d95-226">このセクションには、本体での JavaScript の実行に関連する機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c2d95-226">This section contains features related to running JavaScript in the Console.</span></span>  <span data-ttu-id="c2d95-227">実践的なチュートリアルについては、「 [JavaScript を実行][DevToolsConsoleOverviewJavascript]する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2d95-227">See [Run JavaScript][DevToolsConsoleOverviewJavascript] for a hands-on walkthrough.</span></span>  

### <span data-ttu-id="c2d95-228">履歴からの式の再実行</span><span class="sxs-lookup"><span data-stu-id="c2d95-228">Re-run expressions from history</span></span>   

<span data-ttu-id="c2d95-229">キーを押して、 `Up Arrow` コンソールで前に実行した JavaScript 式の履歴を順に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="c2d95-229">Press the `Up Arrow` key to cycle through the history of JavaScript expressions that you ran earlier in the Console.</span></span>  <span data-ttu-id="c2d95-230">を押して `Enter` その式を再実行します。</span><span class="sxs-lookup"><span data-stu-id="c2d95-230">Press `Enter` to run that expression again.</span></span>  

### <span data-ttu-id="c2d95-231">ライブ式を使用して、式の値をリアルタイムで見る</span><span class="sxs-lookup"><span data-stu-id="c2d95-231">Watch the value of an expression in real-time with Live Expressions</span></span>   

<span data-ttu-id="c2d95-232">コンソールで同じ JavaScript 式を繰り返し入力したことがわかった場合は、**ライブ式**の作成が簡単になることがあります。</span><span class="sxs-lookup"><span data-stu-id="c2d95-232">If you find yourself typing the same JavaScript expression in the Console repeatedly, you may find it easier to create a **Live Expression**.</span></span>  <span data-ttu-id="c2d95-233">**ライブ式**で式を1回入力し、本体の先頭に固定します。</span><span class="sxs-lookup"><span data-stu-id="c2d95-233">With **Live Expressions** you type an expression once and then pin it to the top of your Console.</span></span>  <span data-ttu-id="c2d95-234">この式の値は、ほぼリアルタイムで更新されます。</span><span class="sxs-lookup"><span data-stu-id="c2d95-234">The value of the expression updates in near real-time.</span></span>  <span data-ttu-id="c2d95-235">詳しく[は、「ライブ式を使って JavaScript の式値をリアルタイムで見る][DevToolsConsoleLiveExpressions]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c2d95-235">See [Watch JavaScript Expression Values In Real-Time With Live Expressions][DevToolsConsoleLiveExpressions].</span></span>  

### <span data-ttu-id="c2d95-236">一括評価を無効にする</span><span class="sxs-lookup"><span data-stu-id="c2d95-236">Disable Eager Evaluation</span></span>   

<span data-ttu-id="c2d95-237">本体に JavaScript の式を入力すると、その式の戻り値のプレビュー**が表示さ**れます。</span><span class="sxs-lookup"><span data-stu-id="c2d95-237">As you type JavaScript expressions in the Console, **Eager Evaluation** shows a preview of the return value for that expression.</span></span>  <span data-ttu-id="c2d95-238">[[本体の設定](#open-console-settings)] を開き、[先行の**評価**] チェックボックスをオフにして戻り値のプレビューをオフにします。</span><span class="sxs-lookup"><span data-stu-id="c2d95-238">[Open Console Settings](#open-console-settings) and disable the **Eager Evaluation** checkbox to turn off the return value previews.</span></span>  

### <span data-ttu-id="c2d95-239">履歴からオートコンプリートを無効にする</span><span class="sxs-lookup"><span data-stu-id="c2d95-239">Disable autocomplete from history</span></span>   

<span data-ttu-id="c2d95-240">式を入力すると、本体の [オートコンプリート] ポップアップウィンドウに、前に実行した式が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2d95-240">As you type out an expression, the autocomplete popup window for the Console shows expressions that you ran earlier.</span></span>  <span data-ttu-id="c2d95-241">これらの式は文字で先頭に付けられ `>` ます。</span><span class="sxs-lookup"><span data-stu-id="c2d95-241">These expressions are prepended with the `>` character.</span></span>  <span data-ttu-id="c2d95-242">[[コンソールの設定](#open-console-settings)] を開いて、[履歴の**オートコンプリート**] チェックボックスをオフにして、履歴からの式の表示を停止します。</span><span class="sxs-lookup"><span data-stu-id="c2d95-242">[Open Console Settings](#open-console-settings) and disable the **Autocomplete From History** checkbox to stop showing expressions from your history.</span></span>  

> [!NOTE]
> <span data-ttu-id="c2d95-243">[図 17](#figure-17)で、 `document.querySelector('a')` `document.querySelector('img')` 前に評価した式を示します。</span><span class="sxs-lookup"><span data-stu-id="c2d95-243">In [Figure 17](#figure-17), `document.querySelector('a')` and `document.querySelector('img')` are expressions that were evaluated earlier.</span></span>  

> ##### <span data-ttu-id="c2d95-244">図 17</span><span class="sxs-lookup"><span data-stu-id="c2d95-244">Figure 17</span></span>  
> <span data-ttu-id="c2d95-245">履歴の式が表示されたオートコンプリートのポップアップ</span><span class="sxs-lookup"><span data-stu-id="c2d95-245">The autocomplete popup showing expressions from history</span></span>  
> <span data-ttu-id="c2d95-246">![履歴の式を表示するオートコンプリート] ポップアップ[Imagehistory オートコンプリート]</span><span class="sxs-lookup"><span data-stu-id="c2d95-246">![The autocomplete popup showing expressions from history][ImageHistoryAutocomplete]</span></span>  

### <span data-ttu-id="c2d95-247">JavaScript のコンテキストを選ぶ</span><span class="sxs-lookup"><span data-stu-id="c2d95-247">Select JavaScript context</span></span>   

<span data-ttu-id="c2d95-248">既定では、 **JavaScript コンテキスト**のドロップダウンは [**先頭**] に設定されています。これは、メインドキュメントの[閲覧コンテキスト][MDNBrowsingContext]を表します。</span><span class="sxs-lookup"><span data-stu-id="c2d95-248">By default the **JavaScript Context** dropdown is set to **top**, which represents the [browsing context][MDNBrowsingContext] of the main document.</span></span>  

> ##### <span data-ttu-id="c2d95-249">図18</span><span class="sxs-lookup"><span data-stu-id="c2d95-249">Figure 18</span></span>  
> <span data-ttu-id="c2d95-250">**JavaScript コンテキスト**のドロップダウン</span><span class="sxs-lookup"><span data-stu-id="c2d95-250">The **JavaScript Context** dropdown</span></span>  
> <span data-ttu-id="c2d95-251">![JavaScript コンテキスト] ドロップダウン[ImageJavascriptContext]</span><span class="sxs-lookup"><span data-stu-id="c2d95-251">![The JavaScript Context dropdown][ImageJavascriptContext]</span></span>  

<span data-ttu-id="c2d95-252">ページに広告が埋め込まれていると `<iframe>` します。</span><span class="sxs-lookup"><span data-stu-id="c2d95-252">Suppose you have an ad on your page embedded in an `<iframe>`.</span></span>  <span data-ttu-id="c2d95-253">広告の DOM を調整するために JavaScript を実行します。</span><span class="sxs-lookup"><span data-stu-id="c2d95-253">You want to run JavaScript in order to tweak the DOM of the ad.</span></span>  <span data-ttu-id="c2d95-254">まず、 **JavaScript のコンテキスト**ドロップダウンから広告の閲覧コンテキストを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2d95-254">You should first select the browsing context of the ad from the **JavaScript Context** dropdown.</span></span>  

> ##### <span data-ttu-id="c2d95-255">図19</span><span class="sxs-lookup"><span data-stu-id="c2d95-255">Figure 19</span></span>  
> <span data-ttu-id="c2d95-256">別の JavaScript コンテキストの選択</span><span class="sxs-lookup"><span data-stu-id="c2d95-256">Selecting a different JavaScript context</span></span>  
> <span data-ttu-id="c2d95-257">![別の JavaScript コンテキストの選択][ImageSelectContext]</span><span class="sxs-lookup"><span data-stu-id="c2d95-257">![Selecting a different JavaScript context][ImageSelectContext]</span></span>  

## <span data-ttu-id="c2d95-258">本体をクリアする</span><span class="sxs-lookup"><span data-stu-id="c2d95-258">Clear the Console</span></span>   

<span data-ttu-id="c2d95-259">次のいずれかのワークフローを使用して本体をクリアすることができます。</span><span class="sxs-lookup"><span data-stu-id="c2d95-259">You may use any of the following workflows to clear the Console:</span></span>  

*   <span data-ttu-id="c2d95-260">[**本体** ![ のクリア] ][ImageClearConsoleIcon] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c2d95-260">Click **Clear Console** ![Clear Console][ImageClearConsoleIcon].</span></span>  
*   <span data-ttu-id="c2d95-261">メッセージを右クリックし、[**コンソールのクリア**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2d95-261">Right-click a message and then select **Clear Console**.</span></span>  
*   <span data-ttu-id="c2d95-262">`clear()`コンソールに入力して、キーを押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="c2d95-262">Type `clear()` in the Console and then press `Enter`.</span></span>  
*   <span data-ttu-id="c2d95-263">`console.clear()`Web ページの JavaScript から通話を発信します。</span><span class="sxs-lookup"><span data-stu-id="c2d95-263">Call `console.clear()` from the JavaScript for your webpage.</span></span>  
*   <span data-ttu-id="c2d95-264">`Control` + `L` コンソールがフォーカスされているときにを押します。</span><span class="sxs-lookup"><span data-stu-id="c2d95-264">Press `Control`+`L` while the Console is in focus.</span></span>  

 



<!-- image links -->  

[ImageClearConsoleIcon]: /microsoft-edge/devtools-guide-chromium/media/clear-console-button-icon.msft.png  
[ImageSettingsButtonIcon]: /microsoft-edge/devtools-guide-chromium/media/settings-button-icon.msft.png  
[ImageShowConsoleSidebarIcon]: /microsoft-edge/devtools-guide-chromium/media/show-console-sidebar-icon.msft.png  

[ImageConsolePanel]: /microsoft-edge/devtools-guide-chromium/media/console-hello-console.msft.png "図 1: コンソールパネル"  
[ImageCommandShowConsole]: /microsoft-edge/devtools-guide-chromium/media/console-command-menu-show-console.msft.png "図 2: コンソールパネルを表示するためのコマンド"  
[ImageShowConsoleDrawer]: /microsoft-edge/devtools-guide-chromium/media/console-elements-customize-control-devtools-show-console-drawer.msft.png "図 3: 本体のドローワの表示"  
[ImageDrawerConsole]: /microsoft-edge/devtools-guide-chromium/media/console-elements-console-drawer-hello-world.msft.png "図 4: ドローワの [コンソール] タブ"  
[ImageShowDrawerCommand]: /microsoft-edge/devtools-guide-chromium/media/console-command-menu-show-console.msft.png "図 5: ドローワの [コンソール] タブを表示するためのコマンド"  
[ImageConsoleSettings]: /microsoft-edge/devtools-guide-chromium/media/console-settings-group-similar-empty.msft.png "図 6: 本体の設定"  
[ImageConsoleSidebar]: /microsoft-edge/devtools-guide-chromium/media/console-sidebar-drawer-empty.msft.png "図 7: 本体のサイドバー"  
[ImageXhrGrouped]: /microsoft-edge/devtools-guide-chromium/media/console-xhr-fetch.msft.png "図 8: XMLHttpRequest 要求とフェッチ要求のログ記録"  
<!--[ImageXhrUngrouped]: /microsoft-edge/devtools-guide-chromium/media/console-xhr-fetch-all.msft.png "Figure old 9: How the logged XMLHttpRequest and Fetch requests look after ungrouping"  -->  
[Image429Message]:/microsoft-edge/devtools-guide-chromium/media/console-show-network.msft.png "図 9: 本体の429メッセージ  
[ImageUserMessages]:/microsoft-edge/devtools-guide-chromium/media/console-sidebar-drawer-user-messages.msft.png "図 10: ユーザーメッセージの表示"  
[ImageLogLevels]:/microsoft-edge/devtools-guide-chromium/media/console-log-level-default-levels.msft.png "図 11: ログレベルのドロップダウン  
[ImageSidebarWarnings]:/microsoft-edge/devtools-guide-chromium/media/console-sidebar-warnings.msft.png "図 12: サイドバーを使って警告を表示する」を参照してください。  
[ImageUrlFilter]:/microsoft-edge/devtools-guide-chromium/media/console-filter-text.msft.png "図 13: URL フィルター"  
[ImageNegativeUrlFilter1]:/microsoft-edge/devtools-guide-chromium/media/console-negative-filter-text.msft.png "図 14: URL に一致するすべてのメッセージを非表示にする負 https://b.wal.co の url フィルター  
[ImageNegativeUrlFilter2]:/microsoft-edge/devtools-guide-chromium/media/console-filter-text-specified.msft.png "図 15: wp-ad から送信されたメッセージを表示する  
[Imager/microsoft-edge/devtools-guide-chromium/media/console-filter-regex.msft.png Exfilter]: "図 16: regex の式と一致しないメッセージをフィルターで除外する"
[ImageRegExFilter]: /microsoft-edge/devtools-guide-chromium/media/console-filter-regex.msft.png "Figure 16: Filtering out any messages that do not match regex expression"  
[Imagehistory オートコンプリート]:/microsoft-edge/devtools-guide-chromium/media/console-filter-text-autofilter-history.msft.png "図 17: 履歴の式を表示するオートコンプリートポップアップ
[ImageHistoryAutocomplete]: /microsoft-edge/devtools-guide-chromium/media/console-filter-text-autofilter-history.msft.png "Figure 17: The autocomplete popup showing expressions from history"  
[ImageJavascriptContext]:/microsoft-edge/devtools-guide-chromium/media/console-dom-level-top.msft.png "図 18: JavaScript のコンテキストのドロップダウン  
[ImageSelectContext]:/microsoft-edge/devtools-guide-chromium/media/console-dom-level-multiple.msft.png "図 19: 別の JavaScript コンテキストの選択"  

<!-- links -->  

[DevToolsCommandMenu]: /microsoft-edge/devtools-guide-chromium/command-menu/index "Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する"  
[DevToolsConsoleViewMessages]: /microsoft-edge/devtools-guide-chromium/console/index#viewing-logged-messages "ログメッセージの表示-コンソールの概要"  
[DevToolsConsoleApi]: /microsoft-edge/devtools-guide-chromium/console/api "本体の API リファレンス"  
[DevToolsConsoleOverviewJavascript]: /microsoft-edge/devtools-guide-chromium/console/index#running-javascript "JavaScript の実行-本体の概要"  
[DevToolsConsoleJavascript]: /microsoft-edge/devtools-guide-chromium/console/javascript "本体の JavaScript の実行を開始する"  
[DevToolsConsoleLiveExpressions]: /microsoft-edge/devtools-guide-chromium/console/live-expressions "ライブ式を使って JavaScript の式値をリアルタイムで見る"  
[DevToolsConsoleLog]: /microsoft-edge/devtools-guide-chromium/console/log "コンソールでのメッセージの記録を開始する"  
[DevToolsConsoleUtilities]: /microsoft-edge/devtools-guide-chromium/console/utilities "コンソールユーティリティ API リファレンス"  

[MDNBrowsingContext]: https://developer.mozilla.org/docs/Glossary/Browsing_context "ブラウジングコンテキスト |MDN"  

> [!NOTE]
> <span data-ttu-id="c2d95-293">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="c2d95-293">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="c2d95-294">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/console/reference)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="c2d95-294">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="c2d95-296">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="c2d95-296">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
