---
description: スニペットは、Microsoft Edge DevTools のソースパネル内で作成および実行できる小さなスクリプトです。  どのページからでもアクセスして実行できます。  スニペットを実行すると、現在開いているページのコンテキストから実行されます。
title: Microsoft Edge DevTools を使用して、任意のページで JavaScript のスニペットを実行します。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: e353da76a5c354d834b69708c8a8c9e8dbdf9934
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "11124741"
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

# <span data-ttu-id="fb263-106">Microsoft Edge DevTools を使用して、任意のページで JavaScript のスニペットを実行します。</span><span class="sxs-lookup"><span data-stu-id="fb263-106">Run snippets of JavaScript on any page with Microsoft Edge DevTools</span></span>  

<span data-ttu-id="fb263-107">同じコードを [コンソール][DevtoolsConsoleIndex] で繰り返し実行していることがわかった場合は、代わりにスニペットとしてコードを保存することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="fb263-107">If you find yourself running the same code in the [Console][DevtoolsConsoleIndex] repeatedly, consider saving the code as a Snippet instead.</span></span>  <span data-ttu-id="fb263-108">スニペットは、[ [ソース][DevToolsSourcesPanel] ] パネルで作成したスクリプトです。</span><span class="sxs-lookup"><span data-stu-id="fb263-108">Snippets are scripts that you author in the [Sources][DevToolsSourcesPanel] panel.</span></span>  <span data-ttu-id="fb263-109">このページの JavaScript のコンテキストにアクセスできるので、どのページでも実行できます。</span><span class="sxs-lookup"><span data-stu-id="fb263-109">They have access to the JavaScript context of the page, and you can run them on any page.</span></span>  <span data-ttu-id="fb263-110">スニペットは、 [bookmarklets][WikiBookmarklet]の代わりとなります。</span><span class="sxs-lookup"><span data-stu-id="fb263-110">Snippets are an alternative to [bookmarklets][WikiBookmarklet].</span></span>  
<span data-ttu-id="fb263-111">Firefox DevTools には、 [書い][MDNScratchpad]というスニペットのような機能があります。</span><span class="sxs-lookup"><span data-stu-id="fb263-111">Firefox DevTools has a feature similar to Snippets called [Scratchpad][MDNScratchpad].</span></span>  

<span data-ttu-id="fb263-112">たとえば、次の図は、左側の DevTools ホームページと右側にあるスニペットソースコードを示しています。</span><span class="sxs-lookup"><span data-stu-id="fb263-112">For example, in the following figure shows the DevTools homepage on the left and some Snippet source code on the right.</span></span>  

:::image type="complex" source="../media/javascript-sources-snippets-split-screen.msft.png" alt-text="スニペットを実行する前のページの外観" lightbox="../media/javascript-sources-snippets-split-screen.msft.png":::
   <span data-ttu-id="fb263-114">スニペットを実行する前のページの外観</span><span class="sxs-lookup"><span data-stu-id="fb263-114">How the page looks before running the Snippet</span></span>  
:::image-end:::  

<span data-ttu-id="fb263-115">前の図のスニペットソースコード。</span><span class="sxs-lookup"><span data-stu-id="fb263-115">The Snippet source code from the previous figure.</span></span>  

```javascript
console.log('Hello, Snippets!');
document.body.innerHTML = '';
var p = document.createElement('p');
p.textContent = 'Hello, Snippets!';
document.body.appendChild(p);
```  

<span data-ttu-id="fb263-116">次の図では、スニペットを実行した後にページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fb263-116">In the following figure, the page appears after running the Snippet.</span></span>  <span data-ttu-id="fb263-117">**本体の引き出し**がポップアップ表示され、スニペットのログが記録され、 `Hello, Snippets!` ページの内容が完全に変更されます。</span><span class="sxs-lookup"><span data-stu-id="fb263-117">The **Console Drawer** pops up to display the `Hello, Snippets!` message that the Snippet logs, and the content of the page changes completely.</span></span>  

:::image type="complex" source="../media/javascript-sources-snippets-split-screen-after.msft.png" alt-text="スニペットを実行する前のページの外観" lightbox="../media/javascript-sources-snippets-split-screen-after.msft.png":::
   <span data-ttu-id="fb263-119">スニペットの実行後のページの外観</span><span class="sxs-lookup"><span data-stu-id="fb263-119">How the page looks after running the Snippet</span></span>  
:::image-end:::  

## <span data-ttu-id="fb263-120">[スニペット] ウィンドウを開く</span><span class="sxs-lookup"><span data-stu-id="fb263-120">Open the Snippets pane</span></span>  

<span data-ttu-id="fb263-121">[ **スニペット** ] ウィンドウにスニペットの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fb263-121">The **Snippets** pane lists your Snippets.</span></span>  <span data-ttu-id="fb263-122">スニペットを編集するには、スニペットを [ **スニペット** ] ウィンドウから開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb263-122">When you want to edit a Snippet, you need to open it from the **Snippets** pane.</span></span>  

:::image type="complex" source="../media/javascript-sources-snippets-pane.msft.png" alt-text="スニペットを実行する前のページの外観" lightbox="../media/javascript-sources-snippets-pane.msft.png":::
   <span data-ttu-id="fb263-124">[ **スニペット** ] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="fb263-124">The **Snippets** pane</span></span>  
:::image-end:::  

### <span data-ttu-id="fb263-125">[スニペット] ウィンドウをマウスで開く</span><span class="sxs-lookup"><span data-stu-id="fb263-125">Open the Snippets pane with a mouse</span></span>  

1.  <span data-ttu-id="fb263-126">[ **ソース** ] タブをクリックして、[ **ソース** ] パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="fb263-126">Click the **Sources** tab to open the **Sources** panel.</span></span>  <span data-ttu-id="fb263-127">通常、 **ページ** ウィンドウは既定で開かれます。</span><span class="sxs-lookup"><span data-stu-id="fb263-127">The **Page** pane usually opens by default.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-pane.msft.png" alt-text="スニペットを実行する前のページの外観" lightbox="../media/javascript-sources-page-pane.msft.png":::
       <span data-ttu-id="fb263-129">左側に**ページ**ウィンドウが開いている [**ソース**] パネル</span><span class="sxs-lookup"><span data-stu-id="fb263-129">The **Sources** panel with the **Page** pane open on the left</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="fb263-130">[ **スニペット** ] タブをクリックして、[ **スニペット** ] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="fb263-130">Click the **Snippets** tab to open the **Snippets** pane.</span></span>  <span data-ttu-id="fb263-131">スニペットオプションにアクセスするには、[**その他のタブ**] ([その他] タブ) を選択する必要がある場合があり ![ ][ImageMoreTabsIcon] ます。 **Snippets**</span><span class="sxs-lookup"><span data-stu-id="fb263-131">You might need to choose **More Tabs** \(![More Tabs][ImageMoreTabsIcon]\) in order to access the **Snippets** option.</span></span>  
    
### <span data-ttu-id="fb263-132">[スニペット] ウィンドウでコマンドメニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="fb263-132">Open the Snippets pane with the Command Menu</span></span>  

1.  <span data-ttu-id="fb263-133">DevTools 内の任意の場所にカーソルをフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="fb263-133">Focus your cursor somewhere inside of DevTools.</span></span>  
1.  <span data-ttu-id="fb263-134">`Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows, Linux \) または `Command` + `Shift` + `P` \ (macOS \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="fb263-134">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu.</span></span>  
1.  <span data-ttu-id="fb263-135">入力を開始し `Snippets` 、[ **スニペットの表示**] を選択して、コマンドを `Enter` 実行します。</span><span class="sxs-lookup"><span data-stu-id="fb263-135">Start typing `Snippets`, choose **Show Snippets**, and then select `Enter` to run the command.</span></span>  
    
    :::image type="complex" source="../media/javascript-search-show-snippets.msft.png" alt-text="スニペットを実行する前のページの外観" lightbox="../media/javascript-search-show-snippets.msft.png":::
       <span data-ttu-id="fb263-137">[ **スニペットの表示** ] コマンド</span><span class="sxs-lookup"><span data-stu-id="fb263-137">The **Show Snippets** command</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="fb263-138">スニペットを作成する</span><span class="sxs-lookup"><span data-stu-id="fb263-138">Create Snippets</span></span>  

### <span data-ttu-id="fb263-139">ソースパネルを使用してスニペットを作成する</span><span class="sxs-lookup"><span data-stu-id="fb263-139">Create a Snippet through the Sources panel</span></span>  

1.  <span data-ttu-id="fb263-140">[ [**スニペット**] ウィンドウを開き](#open-the-snippets-pane)ます。</span><span class="sxs-lookup"><span data-stu-id="fb263-140">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="fb263-141">[ **新しいスニペット**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="fb263-141">Choose **New snippet**.</span></span>  
1.  <span data-ttu-id="fb263-142">スニペットの名前を入力し、[ `Enter` 保存] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fb263-142">Enter a name for your Snippet then select `Enter` to save.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-snippets-naming.msft.png" alt-text="スニペットを実行する前のページの外観" lightbox="../media/javascript-sources-snippets-naming.msft.png":::
       <span data-ttu-id="fb263-144">スニペットに名前を指定する</span><span class="sxs-lookup"><span data-stu-id="fb263-144">Name a Snippet</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="fb263-145">コマンドメニューを使用してスニペットを作成する</span><span class="sxs-lookup"><span data-stu-id="fb263-145">Create a Snippet through the Command Menu</span></span>  

1.  <span data-ttu-id="fb263-146">DevTools 内の任意の場所にカーソルをフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="fb263-146">Focus your cursor somewhere inside of DevTools.</span></span>  
1.  <span data-ttu-id="fb263-147">`Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows, Linux \) または `Command` + `Shift` + `P` \ (macOS \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="fb263-147">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu.</span></span>  
1.  <span data-ttu-id="fb263-148">入力を開始し `Snippet` 、[ **新しいスニペットの作成**] を選択し `Enter` て、コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fb263-148">Start typing `Snippet`, choose **Create new snippet**, then select `Enter` to run the command.</span></span>  
    
    :::image type="complex" source="../media/javascript-search-create-new-snippet.msft.png" alt-text="スニペットを実行する前のページの外観" lightbox="../media/javascript-search-create-new-snippet.msft.png":::
       <span data-ttu-id="fb263-150">新しいスニペットを作成するためのコマンド</span><span class="sxs-lookup"><span data-stu-id="fb263-150">The command for creating a new Snippet</span></span>  
    :::image-end:::  
    
<span data-ttu-id="fb263-151">新しいスニペットにカスタム名を付ける場合は、「 [スニペットの名前変更](#rename-snippets) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb263-151">See [Rename Snippets](#rename-snippets) if you'd like to give your new Snippet a custom name.</span></span>  

## <span data-ttu-id="fb263-152">スニペットを編集する</span><span class="sxs-lookup"><span data-stu-id="fb263-152">Edit Snippets</span></span>  

1.  <span data-ttu-id="fb263-153">[ [**スニペット**] ウィンドウを開き](#open-the-snippets-pane)ます。</span><span class="sxs-lookup"><span data-stu-id="fb263-153">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="fb263-154">[ **スニペット** ] ウィンドウで、編集するスニペットの名前をクリックして、 **コードエディター**で開きます。</span><span class="sxs-lookup"><span data-stu-id="fb263-154">In the **Snippets** pane click the name of the Snippet that you want to edit in order to open it in the **Code Editor**.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-snippets-editor-saved.msft.png" alt-text="スニペットを実行する前のページの外観" lightbox="../media/javascript-sources-snippets-editor-saved.msft.png":::
       <span data-ttu-id="fb263-156">**コードエディター**</span><span class="sxs-lookup"><span data-stu-id="fb263-156">The **Code Editor**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="fb263-157">**コードエディター**を使用して、スニペットに JavaScript を追加します。</span><span class="sxs-lookup"><span data-stu-id="fb263-157">Use the **Code Editor** to add JavaScript to your Snippet.</span></span>  
1.  <span data-ttu-id="fb263-158">スニペットの名前の横にアスタリスクが表示される場合は、コードが保存されていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="fb263-158">When an asterisk appears next to the name of your Snippet it means you have unsaved code.</span></span> <span data-ttu-id="fb263-159">`Control` + `S` 保存するには、\ (Windows、Linux \) または `Command` + `S` \ (macOS \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="fb263-159">Select `Control`+`S` \(Windows, Linux\) or `Command`+`S` \(macOS\) to save.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-snippets-editor-unsaved.msft.png" alt-text="スニペットを実行する前のページの外観" lightbox="../media/javascript-sources-snippets-editor-unsaved.msft.png":::
       <span data-ttu-id="fb263-161">まだ保存されていないコードを示すスニペット名の横に表示されるアスタリスク</span><span class="sxs-lookup"><span data-stu-id="fb263-161">An asterisk next to the Snippet name, which indicates unsaved code</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="fb263-162">スニペットの実行</span><span class="sxs-lookup"><span data-stu-id="fb263-162">Run Snippets</span></span>  

### <span data-ttu-id="fb263-163">[ソース] パネルからスニペットを実行する</span><span class="sxs-lookup"><span data-stu-id="fb263-163">Run a Snippet from the Sources panel</span></span>  

1.  <span data-ttu-id="fb263-164">[ [**スニペット**] ウィンドウを開き](#open-the-snippets-pane)ます。</span><span class="sxs-lookup"><span data-stu-id="fb263-164">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="fb263-165">実行するスニペットの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fb263-165">Click the name of the Snippet that you want to run.</span></span>  <span data-ttu-id="fb263-166">スニペットが **コードエディター**で開きます。</span><span class="sxs-lookup"><span data-stu-id="fb263-166">The Snippet opens in the **Code Editor**.</span></span>  
1.  <span data-ttu-id="fb263-167">[ **Run スニペット**\ ( ![ スニペットを実行し ][ImageRunSnippetIcon] ます)] または [\ ( `Control` + `Enter` Windows、Linux \)] または [ `Command` + `Enter` \ (macOS \)] を選びます。</span><span class="sxs-lookup"><span data-stu-id="fb263-167">Choose **Run Snippet** \(![Run Snippet][ImageRunSnippetIcon]\), or select `Control`+`Enter` \(Windows, Linux\) or `Command`+`Enter` \(macOS\).</span></span>  
    
### <span data-ttu-id="fb263-168">コマンドメニューを使用してスニペットを実行する</span><span class="sxs-lookup"><span data-stu-id="fb263-168">Run a Snippet with the Command Menu</span></span>  

1.  <span data-ttu-id="fb263-169">DevTools 内の任意の場所にカーソルをフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="fb263-169">Focus your cursor somewhere inside of DevTools.</span></span>  
1.  <span data-ttu-id="fb263-170">`Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows, Linux \) または `Command` + `Shift` + `P` \ (macOS \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="fb263-170">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu.</span></span>  
1.  <span data-ttu-id="fb263-171">文字を削除 `>` して、 `!` 実行するスニペットの名前の後に文字を入力します。</span><span class="sxs-lookup"><span data-stu-id="fb263-171">Delete the `>` character and type the `!` character followed by the name of the Snippet that you want to run.</span></span>  
    
    :::image type="complex" source="../media/javascript-search-run-command.msft.png" alt-text="スニペットを実行する前のページの外観" lightbox="../media/javascript-search-run-command.msft.png":::
       <span data-ttu-id="fb263-173">**コマンドメニュー**からのスニペットの実行</span><span class="sxs-lookup"><span data-stu-id="fb263-173">Running a Snippet from the **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="fb263-174">`Enter`スニペットを実行する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="fb263-174">Select `Enter` to run the Snippet.</span></span>  

## <span data-ttu-id="fb263-175">スニペットの名前変更</span><span class="sxs-lookup"><span data-stu-id="fb263-175">Rename Snippets</span></span>  

1.  <span data-ttu-id="fb263-176">[ [**スニペット**] ウィンドウを開き](#open-the-snippets-pane)ます。</span><span class="sxs-lookup"><span data-stu-id="fb263-176">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="fb263-177">スニペット名を右クリックし、[ **名前の変更**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fb263-177">Right-click the Snippet name and choose **Rename**.</span></span>  
    
## <span data-ttu-id="fb263-178">スニペットを削除する</span><span class="sxs-lookup"><span data-stu-id="fb263-178">Delete Snippets</span></span>  

1.  <span data-ttu-id="fb263-179">[ [**スニペット**] ウィンドウを開き](#open-the-snippets-pane)ます。</span><span class="sxs-lookup"><span data-stu-id="fb263-179">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="fb263-180">スニペット名を右クリックし、[ **削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fb263-180">Right-click the Snippet name and choose **Remove**.</span></span>  
    
## <span data-ttu-id="fb263-181">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="fb263-181">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageMoreTabsIcon]: ../media/more-tabs-icon.msft.png  
[ImageRunSnippetIcon]: ../media/run-snippet-icon.msft.png  

<!-- links -->  

[DevtoolsConsoleIndex]: ../console/index.md "本体の概要 |Microsoft ドキュメント"  
[DevToolsSourcesPanel]: ../sources.md "ソースパネルの概要 |Microsoft ドキュメント"  

[MDNScratchpad]: https://developer.mozilla.org/docs/Tools/Scratchpad "書い |MDN"  
[WikiBookmarklet]: https://en.wikipedia.org/wiki/Bookmarklet "Bookmarklet-Wikipedia"  

> [!NOTE]
> <span data-ttu-id="fb263-186">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="fb263-186">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="fb263-187">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/snippets) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="fb263-187">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/snippets) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="fb263-189">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="fb263-189">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
