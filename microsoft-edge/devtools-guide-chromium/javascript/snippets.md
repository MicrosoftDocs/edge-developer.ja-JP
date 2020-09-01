---
title: Microsoft Edge DevTools を使用して、任意のページで JavaScript のスニペットを実行します。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 3a5ae986e3080a0b6a8b1bf34b0e0efc44c90303
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10982020"
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





# <span data-ttu-id="878e2-103">Microsoft Edge DevTools を使用して、任意のページで JavaScript のスニペットを実行します。</span><span class="sxs-lookup"><span data-stu-id="878e2-103">Run snippets of JavaScript on any page with Microsoft Edge DevTools</span></span>   



<span data-ttu-id="878e2-104">同じコードを [コンソール][DevtoolsConsoleIndex] で繰り返し実行していることがわかった場合は、代わりにスニペットとしてコードを保存することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="878e2-104">If you find yourself running the same code in the [Console][DevtoolsConsoleIndex] repeatedly, consider saving the code as a Snippet instead.</span></span>  <span data-ttu-id="878e2-105">スニペットは、[ [ソース][DevToolsSourcesPanel] ] パネルで作成したスクリプトです。</span><span class="sxs-lookup"><span data-stu-id="878e2-105">Snippets are scripts that you author in the [Sources][DevToolsSourcesPanel] panel.</span></span>  <span data-ttu-id="878e2-106">このページの JavaScript のコンテキストにアクセスできるので、どのページでも実行できます。</span><span class="sxs-lookup"><span data-stu-id="878e2-106">They have access to the JavaScript context of the page, and you can run them on any page.</span></span>  <span data-ttu-id="878e2-107">スニペットは、 [bookmarklets][WikiBookmarklet]の代わりとなります。</span><span class="sxs-lookup"><span data-stu-id="878e2-107">Snippets are an alternative to [bookmarklets][WikiBookmarklet].</span></span>  
<span data-ttu-id="878e2-108">Firefox DevTools には、 [書い][MDNScratchpad]というスニペットのような機能があります。</span><span class="sxs-lookup"><span data-stu-id="878e2-108">Firefox DevTools has a feature similar to Snippets called [Scratchpad][MDNScratchpad].</span></span>  

<span data-ttu-id="878e2-109">たとえば、次の図は、左側の DevTools ホームページと右側にあるスニペットソースコードを示しています。</span><span class="sxs-lookup"><span data-stu-id="878e2-109">For example, in the following figure shows the DevTools homepage on the left and some Snippet source code on the right.</span></span>  

:::image type="complex" source="../media/javascript-sources-snippets-split-screen.msft.png" alt-text="スニペットを実行する前のページの外観" lightbox="../media/javascript-sources-snippets-split-screen.msft.png":::
   <span data-ttu-id="878e2-111">スニペットを実行する前のページの外観</span><span class="sxs-lookup"><span data-stu-id="878e2-111">How the page looks before running the Snippet</span></span>  
:::image-end:::  

<span data-ttu-id="878e2-112">前の図のスニペットソースコード。</span><span class="sxs-lookup"><span data-stu-id="878e2-112">The Snippet source code from the previous figure.</span></span>  

```javascript
console.log('Hello, Snippets!');
document.body.innerHTML = '';
var p = document.createElement('p');
p.textContent = 'Hello, Snippets!';
document.body.appendChild(p);
```  

<span data-ttu-id="878e2-113">次の図では、スニペットを実行した後にページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="878e2-113">In the following figure, the page appears after running the Snippet.</span></span>  <span data-ttu-id="878e2-114">**本体の引き出し**がポップアップ表示され、スニペットのログが記録され、 `Hello, Snippets!` ページの内容が完全に変更されます。</span><span class="sxs-lookup"><span data-stu-id="878e2-114">The **Console Drawer** pops up to display the `Hello, Snippets!` message that the Snippet logs, and the content of the page changes completely.</span></span>  

:::image type="complex" source="../media/javascript-sources-snippets-split-screen-after.msft.png" alt-text="スニペットの実行後のページの外観" lightbox="../media/javascript-sources-snippets-split-screen-after.msft.png":::
   <span data-ttu-id="878e2-116">スニペットの実行後のページの外観</span><span class="sxs-lookup"><span data-stu-id="878e2-116">How the page looks after running the Snippet</span></span>  
:::image-end:::  

## <span data-ttu-id="878e2-117">[スニペット] ウィンドウを開く</span><span class="sxs-lookup"><span data-stu-id="878e2-117">Open the Snippets pane</span></span>   

<span data-ttu-id="878e2-118">[ **スニペット** ] ウィンドウにスニペットの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="878e2-118">The **Snippets** pane lists your Snippets.</span></span>  <span data-ttu-id="878e2-119">スニペットを編集するには、スニペットを [ **スニペット** ] ウィンドウから開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="878e2-119">When you want to edit a Snippet, you need to open it from the **Snippets** pane.</span></span>  

:::image type="complex" source="../media/javascript-sources-snippets-pane.msft.png" alt-text="[スニペット] ウィンドウ" lightbox="../media/javascript-sources-snippets-pane.msft.png":::
   <span data-ttu-id="878e2-121">[ **スニペット** ] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="878e2-121">The **Snippets** pane</span></span>  
:::image-end:::  

### <span data-ttu-id="878e2-122">[スニペット] ウィンドウをマウスで開く</span><span class="sxs-lookup"><span data-stu-id="878e2-122">Open the Snippets pane with a mouse</span></span>   

1.  <span data-ttu-id="878e2-123">[ **ソース** ] タブをクリックして、[ **ソース** ] パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="878e2-123">Click the **Sources** tab to open the **Sources** panel.</span></span>  <span data-ttu-id="878e2-124">通常、 **ページ** ウィンドウは既定で開かれます。</span><span class="sxs-lookup"><span data-stu-id="878e2-124">The **Page** pane usually opens by default.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-pane.msft.png" alt-text="左側にページウィンドウが開いている [ソース] パネル" lightbox="../media/javascript-sources-page-pane.msft.png":::
       <span data-ttu-id="878e2-126">左側に**ページ**ウィンドウが開いている [**ソース**] パネル</span><span class="sxs-lookup"><span data-stu-id="878e2-126">The **Sources** panel with the **Page** pane open on the left</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="878e2-127">[ **スニペット** ] タブをクリックして、[ **スニペット** ] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="878e2-127">Click the **Snippets** tab to open the **Snippets** pane.</span></span>  <span data-ttu-id="878e2-128">スニペットオプションにアクセスするには、[**その他のタブ**] ([ ![ その他のタブ \]) をクリックする必要がある場合があり ][ImageMoreTabsIcon] ます。 **Snippets**</span><span class="sxs-lookup"><span data-stu-id="878e2-128">You might need to click **More Tabs** \(![More Tabs][ImageMoreTabsIcon]\) in order to access the **Snippets** option.</span></span>  
    
### <span data-ttu-id="878e2-129">[スニペット] ウィンドウでコマンドメニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="878e2-129">Open the Snippets pane with the Command Menu</span></span>   

1.  <span data-ttu-id="878e2-130">DevTools 内の任意の場所にカーソルをフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="878e2-130">Focus your cursor somewhere inside of DevTools.</span></span>  
1.  <span data-ttu-id="878e2-131">`Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="878e2-131">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu.</span></span>  
1.  <span data-ttu-id="878e2-132">入力を開始し `Snippets` 、[ **スニペットの表示**] を選択します。次に、を押して `Enter` コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="878e2-132">Start typing `Snippets`, select **Show Snippets**, and then press `Enter` to run the command.</span></span>  
    
    :::image type="complex" source="../media/javascript-search-show-snippets.msft.png" alt-text="[スニペットの表示] コマンド" lightbox="../media/javascript-search-show-snippets.msft.png":::
       <span data-ttu-id="878e2-134">[ **スニペットの表示** ] コマンド</span><span class="sxs-lookup"><span data-stu-id="878e2-134">The **Show Snippets** command</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="878e2-135">スニペットを作成する</span><span class="sxs-lookup"><span data-stu-id="878e2-135">Create Snippets</span></span>   

### <span data-ttu-id="878e2-136">ソースパネルを使用してスニペットを作成する</span><span class="sxs-lookup"><span data-stu-id="878e2-136">Create a Snippet through the Sources panel</span></span>   

1.  <span data-ttu-id="878e2-137">[ [**スニペット**] ウィンドウを開き](#open-the-snippets-pane)ます。</span><span class="sxs-lookup"><span data-stu-id="878e2-137">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="878e2-138">[ **新しいスニペット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="878e2-138">Click **New snippet**.</span></span>  
1.  <span data-ttu-id="878e2-139">スニペットの名前を入力し、を押して `Enter` 保存します。</span><span class="sxs-lookup"><span data-stu-id="878e2-139">Enter a name for your Snippet then press `Enter` to save.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-snippets-naming.msft.png" alt-text="スニペットに名前を指定する" lightbox="../media/javascript-sources-snippets-naming.msft.png":::
       <span data-ttu-id="878e2-141">スニペットに名前を指定する</span><span class="sxs-lookup"><span data-stu-id="878e2-141">Name a Snippet</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="878e2-142">コマンドメニューを使用してスニペットを作成する</span><span class="sxs-lookup"><span data-stu-id="878e2-142">Create a Snippet through the Command Menu</span></span>   

1.  <span data-ttu-id="878e2-143">DevTools 内の任意の場所にカーソルをフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="878e2-143">Focus your cursor somewhere inside of DevTools.</span></span>  
1.  <span data-ttu-id="878e2-144">`Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="878e2-144">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu.</span></span>  
1.  <span data-ttu-id="878e2-145">入力を開始し `Snippet` て、[ **新しいスニペットの作成**] を選択し、を押して `Enter` コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="878e2-145">Start typing `Snippet`, select **Create new snippet**, then press `Enter` to run the command.</span></span>  
    
    :::image type="complex" source="../media/javascript-search-create-new-snippet.msft.png" alt-text="新しいスニペットを作成するためのコマンド" lightbox="../media/javascript-search-create-new-snippet.msft.png":::
       <span data-ttu-id="878e2-147">新しいスニペットを作成するためのコマンド</span><span class="sxs-lookup"><span data-stu-id="878e2-147">The command for creating a new Snippet</span></span>  
    :::image-end:::  
    
<span data-ttu-id="878e2-148">新しいスニペットにカスタム名を付ける場合は、「 [スニペットの名前変更](#rename-snippets) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="878e2-148">See [Rename Snippets](#rename-snippets) if you'd like to give your new Snippet a custom name.</span></span>  

## <span data-ttu-id="878e2-149">スニペットを編集する</span><span class="sxs-lookup"><span data-stu-id="878e2-149">Edit Snippets</span></span>   

1.  <span data-ttu-id="878e2-150">[ [**スニペット**] ウィンドウを開き](#open-the-snippets-pane)ます。</span><span class="sxs-lookup"><span data-stu-id="878e2-150">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="878e2-151">[ **スニペット** ] ウィンドウで、編集するスニペットの名前をクリックして、 **コードエディター**で開きます。</span><span class="sxs-lookup"><span data-stu-id="878e2-151">In the **Snippets** pane click the name of the Snippet that you want to edit in order to open it in the **Code Editor**.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-snippets-editor-saved.msft.png" alt-text="コードエディター" lightbox="../media/javascript-sources-snippets-editor-saved.msft.png":::
       <span data-ttu-id="878e2-153">**コードエディター**</span><span class="sxs-lookup"><span data-stu-id="878e2-153">The **Code Editor**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="878e2-154">**コードエディター**を使用して、スニペットに JavaScript を追加します。</span><span class="sxs-lookup"><span data-stu-id="878e2-154">Use the **Code Editor** to add JavaScript to your Snippet.</span></span>  
1.  <span data-ttu-id="878e2-155">スニペットの名前の横にアスタリスクが表示される場合は、コードが保存されていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="878e2-155">When an asterisk appears next to the name of your Snippet it means you have unsaved code.</span></span> <span data-ttu-id="878e2-156">`Control` + `S` 保存するには、\ (Windows \) または `Command` + `S` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="878e2-156">Press `Control`+`S` \(Windows\) or `Command`+`S` \(macOS\) to save.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-snippets-editor-unsaved.msft.png" alt-text="まだ保存されていないコードを示すスニペット名の横に表示されるアスタリスク" lightbox="../media/javascript-sources-snippets-editor-unsaved.msft.png":::
       <span data-ttu-id="878e2-158">まだ保存されていないコードを示すスニペット名の横に表示されるアスタリスク</span><span class="sxs-lookup"><span data-stu-id="878e2-158">An asterisk next to the Snippet name, which indicates unsaved code</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="878e2-159">スニペットの実行</span><span class="sxs-lookup"><span data-stu-id="878e2-159">Run Snippets</span></span>   

### <span data-ttu-id="878e2-160">[ソース] パネルからスニペットを実行する</span><span class="sxs-lookup"><span data-stu-id="878e2-160">Run a Snippet from the Sources panel</span></span>   

1.  <span data-ttu-id="878e2-161">[ [**スニペット**] ウィンドウを開き](#open-the-snippets-pane)ます。</span><span class="sxs-lookup"><span data-stu-id="878e2-161">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="878e2-162">実行するスニペットの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="878e2-162">Click the name of the Snippet that you want to run.</span></span>  <span data-ttu-id="878e2-163">スニペットが **コードエディター**で開きます。</span><span class="sxs-lookup"><span data-stu-id="878e2-163">The Snippet opens in the **Code Editor**.</span></span>  
1.  <span data-ttu-id="878e2-164">[**スニペットの実行**] ( ![ スニペット ][ImageRunSnippetIcon] の実行) をクリックするか、 `Control` + `Enter` \ (Windows \) または `Command` + `Enter` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="878e2-164">Click **Run Snippet** \(![Run Snippet][ImageRunSnippetIcon]\), or press `Control`+`Enter` \(Windows\) or `Command`+`Enter` \(macOS\).</span></span>  
    
### <span data-ttu-id="878e2-165">コマンドメニューを使用してスニペットを実行する</span><span class="sxs-lookup"><span data-stu-id="878e2-165">Run a Snippet with the Command Menu</span></span>   

1.  <span data-ttu-id="878e2-166">DevTools 内の任意の場所にカーソルをフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="878e2-166">Focus your cursor somewhere inside of DevTools.</span></span>  
1.  <span data-ttu-id="878e2-167">`Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="878e2-167">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu.</span></span>  
1.  <span data-ttu-id="878e2-168">文字を削除 `>` して、 `!` 実行するスニペットの名前の後に文字を入力します。</span><span class="sxs-lookup"><span data-stu-id="878e2-168">Delete the `>` character and type the `!` character followed by the name of the Snippet that you want to run.</span></span>  
    
    :::image type="complex" source="../media/javascript-search-run-command.msft.png" alt-text="コマンドメニューからのスニペットの実行" lightbox="../media/javascript-search-run-command.msft.png":::
       <span data-ttu-id="878e2-170">**コマンドメニュー**からのスニペットの実行</span><span class="sxs-lookup"><span data-stu-id="878e2-170">Running a Snippet from the **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="878e2-171">を押して `Enter` スニペットを実行します。</span><span class="sxs-lookup"><span data-stu-id="878e2-171">Press `Enter` to run the Snippet.</span></span>  

## <span data-ttu-id="878e2-172">スニペットの名前変更</span><span class="sxs-lookup"><span data-stu-id="878e2-172">Rename Snippets</span></span>   

1.  <span data-ttu-id="878e2-173">[ [**スニペット**] ウィンドウを開き](#open-the-snippets-pane)ます。</span><span class="sxs-lookup"><span data-stu-id="878e2-173">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="878e2-174">スニペット名を右クリックし、[ **名前の変更**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="878e2-174">Right-click the Snippet name and select **Rename**.</span></span>  
    
## <span data-ttu-id="878e2-175">スニペットを削除する</span><span class="sxs-lookup"><span data-stu-id="878e2-175">Delete Snippets</span></span>   

1.  <span data-ttu-id="878e2-176">[ [**スニペット**] ウィンドウを開き](#open-the-snippets-pane)ます。</span><span class="sxs-lookup"><span data-stu-id="878e2-176">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="878e2-177">スニペット名を右クリックし、[ **削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="878e2-177">Right-click the Snippet name and select **Remove**.</span></span>  
    
<!--  
 


-->  

<!-- image links -->  

[ImageMoreTabsIcon]: ../media/more-tabs-icon.msft.png  
[ImageRunSnippetIcon]: ../media/run-snippet-icon.msft.png  

<!-- links -->  

[DevtoolsConsoleIndex]: ../console/index.md "本体の概要 |Microsoft ドキュメント"  
[DevToolsSourcesPanel]: ../sources.md "ソースパネルの概要 |Microsoft ドキュメント"  

[MDNScratchpad]: https://developer.mozilla.org/docs/Tools/Scratchpad "書い |MDN"  
[WikiBookmarklet]: https://en.wikipedia.org/wiki/Bookmarklet "Bookmarklet-Wikipedia"  

> [!NOTE]
> <span data-ttu-id="878e2-182">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="878e2-182">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="878e2-183">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/snippets) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="878e2-183">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/snippets) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="878e2-185">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="878e2-185">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
