---
title: Microsoft Edge DevTools を使用して、任意のページで JavaScript のスニペットを実行します。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/18/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: aa9f7e96c7e379c1fe537ffba730e08990e0c20a
ms.sourcegitcommit: ecdc4287fa25a18cb4ddcaf43fcce3b396c3314c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/17/2020
ms.locfileid: "10581818"
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





# <span data-ttu-id="5a72c-103">Microsoft Edge DevTools を使用して、任意のページで JavaScript のスニペットを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a72c-103">Run Snippets Of JavaScript On Any Page With Microsoft Edge DevTools</span></span>   



<span data-ttu-id="5a72c-104">同じコードを[コンソール][DevtoolsConsoleIndex]で繰り返し実行していることがわかった場合は、代わりにスニペットとしてコードを保存することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="5a72c-104">If you find yourself running the same code in the [Console][DevtoolsConsoleIndex] repeatedly, consider saving the code as a Snippet instead.</span></span>  <span data-ttu-id="5a72c-105">スニペットは、[ [**ソース**] パネル][DevToolsSourcesPanel]で作成したスクリプトです。</span><span class="sxs-lookup"><span data-stu-id="5a72c-105">Snippets are scripts that you author in the [**Sources** panel][DevToolsSourcesPanel].</span></span>  <span data-ttu-id="5a72c-106">このページの JavaScript のコンテキストにアクセスできるので、どのページでも実行できます。</span><span class="sxs-lookup"><span data-stu-id="5a72c-106">They have access to the JavaScript context of the page, and you can run them on any page.</span></span>  <span data-ttu-id="5a72c-107">スニペットは、 [bookmarklets][WikiBookmarklet]の代わりとなります。</span><span class="sxs-lookup"><span data-stu-id="5a72c-107">Snippets are an alternative to [bookmarklets][WikiBookmarklet].</span></span>  
<span data-ttu-id="5a72c-108">Firefox DevTools には、[書い][MDNScratchpad]というスニペットのような機能があります。</span><span class="sxs-lookup"><span data-stu-id="5a72c-108">Firefox DevTools has a feature similar to Snippets called [Scratchpad][MDNScratchpad].</span></span>  

<span data-ttu-id="5a72c-109">たとえば、[**図 1**](#figure-1)では、左側の devtools ホームページと右側にあるスニペットソースコードを示しています。</span><span class="sxs-lookup"><span data-stu-id="5a72c-109">For example, [**Figure 1**](#figure-1) shows the DevTools homepage on the left and some Snippet source code on the right.</span></span>  

> ##### <span data-ttu-id="5a72c-110">図 1</span><span class="sxs-lookup"><span data-stu-id="5a72c-110">Figure 1</span></span>  
> <span data-ttu-id="5a72c-111">スニペットを実行する前のページの外観</span><span class="sxs-lookup"><span data-stu-id="5a72c-111">How the page looks before running the Snippet</span></span>  
> ![スニペットを実行する前のページの外観][ImageSnippetSplitScreen]  

<span data-ttu-id="5a72c-113">[**図 1**](#figure-1)のスニペットソースコード:</span><span class="sxs-lookup"><span data-stu-id="5a72c-113">The Snippet source code from [**Figure 1**](#figure-1):</span></span>  

```javascript
console.log('Hello, Snippets!');
document.body.innerHTML = '';
var p = document.createElement('p');
p.textContent = 'Hello, Snippets!';
document.body.appendChild(p);
```  

<span data-ttu-id="5a72c-114">[**図 2**](#figure-2)は、スニペットの実行後にページがどのように見えるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="5a72c-114">[**Figure 2**](#figure-2) shows how the page looks after running the Snippet.</span></span>  <span data-ttu-id="5a72c-115">**本体の引き出し**がポップアップ表示され、スニペットのログが記録され、 `Hello, Snippets!` ページの内容が完全に変更されます。</span><span class="sxs-lookup"><span data-stu-id="5a72c-115">The **Console Drawer** pops up to display the `Hello, Snippets!` message that the Snippet logs, and the content of the page changes completely.</span></span>  

> ##### <span data-ttu-id="5a72c-116">図 2</span><span class="sxs-lookup"><span data-stu-id="5a72c-116">Figure 2</span></span>  
> <span data-ttu-id="5a72c-117">スニペットの実行後のページの外観</span><span class="sxs-lookup"><span data-stu-id="5a72c-117">How the page looks after running the Snippet</span></span>  
> ![スニペットの実行後のページの外観][ImageSnippetSplitScreenAfter]  

## <span data-ttu-id="5a72c-119">[スニペット] ウィンドウを開く</span><span class="sxs-lookup"><span data-stu-id="5a72c-119">Open the Snippets pane</span></span>   

<span data-ttu-id="5a72c-120">[**スニペット**] ウィンドウにスニペットの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a72c-120">The **Snippets** pane lists your Snippets.</span></span>  <span data-ttu-id="5a72c-121">スニペットを編集するには、スニペットを [**スニペット**] ウィンドウから開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a72c-121">When you want to edit a Snippet, you need to open it from the **Snippets** pane.</span></span>  

> ##### <span data-ttu-id="5a72c-122">図 3</span><span class="sxs-lookup"><span data-stu-id="5a72c-122">Figure 3</span></span>  
> <span data-ttu-id="5a72c-123">[**スニペット**] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="5a72c-123">The **Snippets** pane</span></span>  
> ![[スニペット] ウィンドウ][ImageSnippetsPane]  

### <span data-ttu-id="5a72c-125">[スニペット] ウィンドウをマウスで開く</span><span class="sxs-lookup"><span data-stu-id="5a72c-125">Open the Snippets pane with a mouse</span></span>   

1.  <span data-ttu-id="5a72c-126">[**ソース**] タブをクリックして、[**ソース**] パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="5a72c-126">Click the **Sources** tab to open the **Sources** panel.</span></span>  <span data-ttu-id="5a72c-127">通常、**ページ**ウィンドウは既定で開かれます。</span><span class="sxs-lookup"><span data-stu-id="5a72c-127">The **Page** pane usually opens by default.</span></span>  

    > ##### <span data-ttu-id="5a72c-128">図 4</span><span class="sxs-lookup"><span data-stu-id="5a72c-128">Figure 4</span></span>  
    > <span data-ttu-id="5a72c-129">左側に**ページ**ウィンドウが開いている [**ソース**] パネル</span><span class="sxs-lookup"><span data-stu-id="5a72c-129">The **Sources** panel with the **Page** pane open on the left</span></span>  
    > ![左側にページウィンドウが開いている [ソース] パネル][ImageSourcesPageEmpty]  

1.  <span data-ttu-id="5a72c-131">[**スニペット**] タブをクリックして、[**スニペット**] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="5a72c-131">Click the **Snippets** tab to open the **Snippets** pane.</span></span>  <span data-ttu-id="5a72c-132">スニペットオプションにアクセスするには、[その他の**タブ**] タブをクリックする必要がある場合があり ![ ][ImageMoreTabsIcon] ます**Snippets** 。</span><span class="sxs-lookup"><span data-stu-id="5a72c-132">You might need to click **More Tabs** ![More Tabs][ImageMoreTabsIcon] in order to access the **Snippets** option.</span></span>  

### <span data-ttu-id="5a72c-133">[スニペット] ウィンドウでコマンドメニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="5a72c-133">Open the Snippets pane with the Command Menu</span></span>   

1.  <span data-ttu-id="5a72c-134">DevTools 内の任意の場所にカーソルをフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="5a72c-134">Focus your cursor somewhere inside of DevTools.</span></span>  
1.  <span data-ttu-id="5a72c-135">`Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="5a72c-135">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu.</span></span>  
1.  <span data-ttu-id="5a72c-136">入力を開始し `Snippets` 、[**スニペットの表示**] を選択します。次に、を押して `Enter` コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a72c-136">Start typing `Snippets`, select **Show Snippets**, and then press `Enter` to run the command.</span></span>  

    > ##### <span data-ttu-id="5a72c-137">図 5</span><span class="sxs-lookup"><span data-stu-id="5a72c-137">Figure 5</span></span>  
    > <span data-ttu-id="5a72c-138">[**スニペットの表示**] コマンド</span><span class="sxs-lookup"><span data-stu-id="5a72c-138">The **Show Snippets** command</span></span>  
    > ![[スニペットの表示] コマンド][ImageShowSnippetsSearch]  

## <span data-ttu-id="5a72c-140">スニペットを作成する</span><span class="sxs-lookup"><span data-stu-id="5a72c-140">Create Snippets</span></span>   

### <span data-ttu-id="5a72c-141">ソースパネルを使用してスニペットを作成する</span><span class="sxs-lookup"><span data-stu-id="5a72c-141">Create a Snippet through the Sources panel</span></span>   

1.  <span data-ttu-id="5a72c-142">[ [**スニペット**] ウィンドウを開き](#open-the-snippets-pane)ます。</span><span class="sxs-lookup"><span data-stu-id="5a72c-142">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="5a72c-143">[**新しいスニペット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a72c-143">Click **New snippet**.</span></span>  
1.  <span data-ttu-id="5a72c-144">スニペットの名前を入力し、を押して `Enter` 保存します。</span><span class="sxs-lookup"><span data-stu-id="5a72c-144">Enter a name for your Snippet then press `Enter` to save.</span></span>  

    > ##### <span data-ttu-id="5a72c-145">図 6</span><span class="sxs-lookup"><span data-stu-id="5a72c-145">Figure 6</span></span>  
    > <span data-ttu-id="5a72c-146">スニペットに名前を付ける</span><span class="sxs-lookup"><span data-stu-id="5a72c-146">Naming a Snippet</span></span>  
    > ![スニペットに名前を付ける][ImageSnippetName]  

### <span data-ttu-id="5a72c-148">コマンドメニューを使用してスニペットを作成する</span><span class="sxs-lookup"><span data-stu-id="5a72c-148">Create a Snippet through the Command Menu</span></span>   

1.  <span data-ttu-id="5a72c-149">DevTools 内の任意の場所にカーソルをフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="5a72c-149">Focus your cursor somewhere inside of DevTools.</span></span>  
1.  <span data-ttu-id="5a72c-150">`Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="5a72c-150">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu.</span></span>  
1.  <span data-ttu-id="5a72c-151">入力を開始し `Snippet` て、[**新しいスニペットの作成**] を選択し、を押して `Enter` コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a72c-151">Start typing `Snippet`, select **Create new snippet**, then press `Enter` to run the command.</span></span>  

    > ##### <span data-ttu-id="5a72c-152">図 7</span><span class="sxs-lookup"><span data-stu-id="5a72c-152">Figure 7</span></span>  
    > <span data-ttu-id="5a72c-153">新しいスニペットを作成するためのコマンド</span><span class="sxs-lookup"><span data-stu-id="5a72c-153">The command for creating a new Snippet</span></span>  
    > ![新しいスニペットを作成するためのコマンド][ImageCreateSnippetSearch]  

<span data-ttu-id="5a72c-155">新しいスニペットにカスタム名を付ける場合は、「[スニペットの名前変更](#rename-snippets)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a72c-155">See [Rename Snippets](#rename-snippets) if you'd like to give your new Snippet a custom name.</span></span>  

## <span data-ttu-id="5a72c-156">スニペットを編集する</span><span class="sxs-lookup"><span data-stu-id="5a72c-156">Edit Snippets</span></span>   

1.  <span data-ttu-id="5a72c-157">[ [**スニペット**] ウィンドウを開き](#open-the-snippets-pane)ます。</span><span class="sxs-lookup"><span data-stu-id="5a72c-157">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="5a72c-158">[**スニペット**] ウィンドウで、編集するスニペットの名前をクリックして、**コードエディター**で開きます。</span><span class="sxs-lookup"><span data-stu-id="5a72c-158">In the **Snippets** pane click the name of the Snippet that you want to edit in order to open it in the **Code Editor**.</span></span>  

    > ##### <span data-ttu-id="5a72c-159">図 8</span><span class="sxs-lookup"><span data-stu-id="5a72c-159">Figure 8</span></span>  
    > <span data-ttu-id="5a72c-160">コードエディター</span><span class="sxs-lookup"><span data-stu-id="5a72c-160">The Code Editor</span></span>  
    > ![コードエディター][ImageSnippetEditor]  

1.  <span data-ttu-id="5a72c-162">**コードエディター**を使用して、スニペットに JavaScript を追加します。</span><span class="sxs-lookup"><span data-stu-id="5a72c-162">Use the **Code Editor** to add JavaScript to your Snippet.</span></span>  
1.  <span data-ttu-id="5a72c-163">スニペットの名前の横にアスタリスクが表示される場合は、コードが保存されていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="5a72c-163">When an asterisk appears next to the name of your Snippet it means you have unsaved code.</span></span> <span data-ttu-id="5a72c-164">`Control` + `S` 保存するには、\ (Windows \) または `Command` + `S` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="5a72c-164">Press `Control`+`S` \(Windows\) or `Command`+`S` \(macOS\) to save.</span></span>  

    > ##### <span data-ttu-id="5a72c-165">図 9</span><span class="sxs-lookup"><span data-stu-id="5a72c-165">Figure 9</span></span>  
    > <span data-ttu-id="5a72c-166">まだ保存されていないコードを示すスニペット名の横に表示されるアスタリスク</span><span class="sxs-lookup"><span data-stu-id="5a72c-166">An asterisk next to the Snippet name, which indicates unsaved code</span></span>  
    > ![まだ保存されていないコードを示すスニペット名の横に表示されるアスタリスク][ImageUnsavedSnippet]  

## <span data-ttu-id="5a72c-168">スニペットの実行</span><span class="sxs-lookup"><span data-stu-id="5a72c-168">Run Snippets</span></span>   

### <span data-ttu-id="5a72c-169">[ソース] パネルからスニペットを実行する</span><span class="sxs-lookup"><span data-stu-id="5a72c-169">Run a Snippet from the Sources panel</span></span>   

1.  <span data-ttu-id="5a72c-170">[ [**スニペット**] ウィンドウを開き](#open-the-snippets-pane)ます。</span><span class="sxs-lookup"><span data-stu-id="5a72c-170">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="5a72c-171">実行するスニペットの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a72c-171">Click the name of the Snippet that you want to run.</span></span>  <span data-ttu-id="5a72c-172">スニペットが**コードエディター**で開きます。</span><span class="sxs-lookup"><span data-stu-id="5a72c-172">The Snippet opens in the **Code Editor**.</span></span>  
1.  <span data-ttu-id="5a72c-173">[ **Run Snippet**スニペット ![ 実行スニペットの実行] をクリックする ][ImageRunSnippetIcon] か、 `Control` + `Enter` \ (Windows \) または `Command` + `Enter` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="5a72c-173">Click **Run Snippet** ![Run Snippet][ImageRunSnippetIcon], or press `Control`+`Enter` \(Windows\) or `Command`+`Enter` \(macOS\).</span></span>  

### <span data-ttu-id="5a72c-174">コマンドメニューを使用してスニペットを実行する</span><span class="sxs-lookup"><span data-stu-id="5a72c-174">Run a Snippet with the Command Menu</span></span>   

1.  <span data-ttu-id="5a72c-175">DevTools 内の任意の場所にカーソルをフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="5a72c-175">Focus your cursor somewhere inside of DevTools.</span></span>  
1.  <span data-ttu-id="5a72c-176">`Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="5a72c-176">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu.</span></span>  
1.  <span data-ttu-id="5a72c-177">文字を削除 `>` して、 `!` 実行するスニペットの名前の後に文字を入力します。</span><span class="sxs-lookup"><span data-stu-id="5a72c-177">Delete the `>` character and type the `!` character followed by the name of the Snippet that you want to run.</span></span>  

    > ##### <span data-ttu-id="5a72c-178">図 10</span><span class="sxs-lookup"><span data-stu-id="5a72c-178">Figure 10</span></span>  
    > <span data-ttu-id="5a72c-179">コマンドメニューからのスニペットの実行</span><span class="sxs-lookup"><span data-stu-id="5a72c-179">Running a Snippet from the Command Menu</span></span>  
    > ![コマンドメニューからのスニペットの実行][ImageRunSnippetCommand]  

1.  <span data-ttu-id="5a72c-181">を押して `Enter` スニペットを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a72c-181">Press `Enter` to run the Snippet.</span></span>  

## <span data-ttu-id="5a72c-182">スニペットの名前変更</span><span class="sxs-lookup"><span data-stu-id="5a72c-182">Rename Snippets</span></span>   

1.  <span data-ttu-id="5a72c-183">[ [**スニペット**] ウィンドウを開き](#open-the-snippets-pane)ます。</span><span class="sxs-lookup"><span data-stu-id="5a72c-183">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="5a72c-184">スニペット名を右クリックし、[**名前の変更**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a72c-184">Right-click the Snippet name and select **Rename**.</span></span>  

## <span data-ttu-id="5a72c-185">スニペットを削除する</span><span class="sxs-lookup"><span data-stu-id="5a72c-185">Delete Snippets</span></span>   

1.  <span data-ttu-id="5a72c-186">[ [**スニペット**] ウィンドウを開き](#open-the-snippets-pane)ます。</span><span class="sxs-lookup"><span data-stu-id="5a72c-186">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="5a72c-187">スニペット名を右クリックし、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a72c-187">Right-click the Snippet name and select **Remove**.</span></span>  

 



<!-- image links -->  

[ImageMoreTabsIcon]: /microsoft-edge/devtools-guide-chromium/media/more-tabs-icon.msft.png  
[ImageRunSnippetIcon]: /microsoft-edge/devtools-guide-chromium/media/run-snippet-icon.msft.png  

[ImageSnippetSplitScreen]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-snippets-split-screen.msft.png "図 1: スニペットを実行する前にページがどのように表示されるか"  
[ImageSnippetSplitScreenAfter]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-snippets-split-screen-after.msft.png "図 2: スニペットの実行後のページの外観"  
[ImageSnippetsPane]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-snippets-pane.msft.png "図 3: [スニペット] ウィンドウ"  
[ImageSourcesPageEmpty]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-page-pane.msft.png "図 4: 左側にページウィンドウが開いている [ソース] パネル"  
[ImageShowSnippetsSearch]: /microsoft-edge/devtools-guide-chromium/media/javascript-search-show-snippets.msft.png "図 5: [スニペットの表示] コマンド"  
[ImageSnippetName]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-snippets-naming.msft.png "図 6: スニペットに名前を付ける"  
[ImageCreateSnippetSearch]: /microsoft-edge/devtools-guide-chromium/media/javascript-search-create-new-snippet.msft.png "図 7: 新しいスニペットを作成するためのコマンド"  
[ImageSnippetEditor]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-snippets-editor-saved.msft.png "図 8: コードエディター"  
[ImageUnsavedSnippet]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-snippets-editor-unsaved.msft.png "図 9: スニペット名の横に表示されるアスタリスク。まだ保存されていないコードを示します。"  
[ImageRunSnippetCommand]: /microsoft-edge/devtools-guide-chromium/media/javascript-search-run-command.msft.png "図 10: コマンドメニューからスニペットを実行する"  

<!-- links -->  

[DevtoolsConsoleIndex]: ../console/index.md "本体の概要"  
[DevToolsSourcesPanel]: ../sources.md "ソースパネルの概要"  

[MDNScratchpad]: https://developer.mozilla.org/docs/Tools/Scratchpad "書い |MDN"  
[WikiBookmarklet]: https://en.wikipedia.org/wiki/Bookmarklet "Bookmarklet-Wikipedia"  

> [!NOTE]
> <span data-ttu-id="5a72c-202">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="5a72c-202">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="5a72c-203">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/snippets)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="5a72c-203">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/snippets) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="5a72c-205">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="5a72c-205">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
