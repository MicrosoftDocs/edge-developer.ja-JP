---
description: スニペットは、Microsoft Edge DevTools の Sources ツール内で作成して実行できる小さなスクリプトです。  任意の Web ページからリソースにアクセスして実行できます。  スニペットを実行すると、現在開いている Web ページのコンテキストから実行されます。
title: Microsoft Edge DevTools を使用して、任意のページで JavaScript のスニペットを実行します。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 89b028177016a9194a67bbbe44d08572e5755f95
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230958"
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

# <span data-ttu-id="88452-106">Microsoft Edge DevTools を使用して任意の Web ページで JavaScript のスニペットを実行する</span><span class="sxs-lookup"><span data-stu-id="88452-106">Run snippets of JavaScript on any webpage with Microsoft Edge DevTools</span></span>  

<span data-ttu-id="88452-107">コンソールで同じコードを繰り返 [し実行][DevtoolsConsoleIndex] している場合は、コードをスニペットとして保存してください。</span><span class="sxs-lookup"><span data-stu-id="88452-107">If you are running the same code in the [Console][DevtoolsConsoleIndex] repeatedly, consider saving the code as a Snippet instead.</span></span>  <span data-ttu-id="88452-108">スニペットは、ソース ツールで作成 [するスクリプト][DevToolsSourcesTool] です。</span><span class="sxs-lookup"><span data-stu-id="88452-108">Snippets are scripts that you author in the [Sources][DevToolsSourcesTool] tool.</span></span>  <span data-ttu-id="88452-109">スニペットは Web ページの JavaScript コンテキストにアクセスできます。スニペットは任意の Web ページで実行できます。</span><span class="sxs-lookup"><span data-stu-id="88452-109">Snippets have access to the JavaScript context of the webpage, and you may run snippets on any webpage.</span></span>  <span data-ttu-id="88452-110">ほとんどの Web ページのセキュリティ設定では、スニペット内の他のスクリプトの読み込みがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="88452-110">The security settings of most webpages block from loading other scripts in Snippets.</span></span>  <span data-ttu-id="88452-111">このため、すべてのコードを 1 つのファイルに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="88452-111">For that reason, you must include all your code in one file.</span></span>  

<span data-ttu-id="88452-112">スニペットは、スニペットが[][WikiBookmarklet]DevTools でのみ実行される点が異なるブックマークレットに代わる方法であり、URL の許容される長さに限定されません。</span><span class="sxs-lookup"><span data-stu-id="88452-112">Snippets are an alternative to [bookmarklets][WikiBookmarklet] with the difference that Snippets only run in DevTools and are not limited to the allowed length of a URL.</span></span>  

<span data-ttu-id="88452-113">スニペットの使用は、サード パーティの Web ページでいくつかの変更を行う優れた方法です。</span><span class="sxs-lookup"><span data-stu-id="88452-113">Using Snippets is an excellent way to change a few things in a third-party webpage.</span></span>  <span data-ttu-id="88452-114">スニペットのコード変更は現在の Web ページに追加され、同じコンテキストで実行されます。</span><span class="sxs-lookup"><span data-stu-id="88452-114">Code changes in Snippets are added to the current webpage and run in the same context.</span></span>  <span data-ttu-id="88452-115">Web ページの既存のコードを変更する方法の詳細については、[上書き] に [移動します][DevtoolsJavascriptOverrides]。</span><span class="sxs-lookup"><span data-stu-id="88452-115">For more information about changing the existing code of a webpage, navigate to [Overrides][DevtoolsJavascriptOverrides].</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="88452-116">たとえば、次の図では、左側の DevTools ホームページと、いくつかのスニペット ソース コードを右側に示しています。</span><span class="sxs-lookup"><span data-stu-id="88452-116">For example, in the following figure shows the DevTools homepage on the left and some Snippet source code on the right.</span></span>  
      
      :::image type="complex" source="../media/javascript-sources-snippets-split-screen.msft.png" alt-text="スニペットを実行する前" lightbox="../media/javascript-sources-snippets-split-screen.msft.png":::
         <span data-ttu-id="88452-118">スニペットを実行する前の Web ページ</span><span class="sxs-lookup"><span data-stu-id="88452-118">The webpage before running the Snippet</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="88452-119">スニペットを実行する前の Web ページのスニペット ソース コード。</span><span class="sxs-lookup"><span data-stu-id="88452-119">The Snippet source code from the webpage before running the Snippet.</span></span>  
      
      ```javascript
      console.log('Hello, Snippets!');
      document.body.innerHTML = '';
      var p = document.createElement('p');
      p.textContent = 'Hello, Snippets!';
      document.body.appendChild(p);
      ```
   :::column-end:::
:::row-end:::  

<span data-ttu-id="88452-120">次の図では、スニペットの実行後に Web ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="88452-120">In the following figure, the webpage appears after running the Snippet.</span></span>  <span data-ttu-id="88452-121">コンソール **ドロワー** が表示され、スニペットによってログに記録されるメッセージが表示され、Web ページの内容が `Hello, Snippets!` 完全に変更されます。</span><span class="sxs-lookup"><span data-stu-id="88452-121">The **Console Drawer** pops up to display the `Hello, Snippets!` message that the Snippet logs, and the content of the webpage changes completely.</span></span>  

:::image type="complex" source="../media/javascript-sources-snippets-split-screen-after.msft.png" alt-text="スニペットの実行後の Web ページ" lightbox="../media/javascript-sources-snippets-split-screen-after.msft.png":::
   <span data-ttu-id="88452-123">スニペットの実行後の Web ページ</span><span class="sxs-lookup"><span data-stu-id="88452-123">The webpage after running the Snippet</span></span>  
:::image-end:::  

## <span data-ttu-id="88452-124">[スニペット] ウィンドウを開く</span><span class="sxs-lookup"><span data-stu-id="88452-124">Open the Snippets pane</span></span>  

<span data-ttu-id="88452-125">[ **スニペット] ウィンドウ** には、スニペットが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="88452-125">The **Snippets** pane lists your Snippets.</span></span>  <span data-ttu-id="88452-126">スニペットを編集する場合は、[スニペット] ウィンドウからスニペットを **開く必要** があります。</span><span class="sxs-lookup"><span data-stu-id="88452-126">When you want to edit a Snippet, you need to open it from the **Snippets** pane.</span></span>  

:::image type="complex" source="../media/javascript-sources-snippets-pane.msft.png" alt-text="[スニペット] ウィンドウ" lightbox="../media/javascript-sources-snippets-pane.msft.png":::
   <span data-ttu-id="88452-128">[ **スニペット]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="88452-128">The **Snippets** pane</span></span>  
:::image-end:::  

### <span data-ttu-id="88452-129">マウスを使用して [スニペット] ウィンドウを開く</span><span class="sxs-lookup"><span data-stu-id="88452-129">Open the Snippets pane with a mouse</span></span>  

1.  <span data-ttu-id="88452-130">[ソース **] タブを** 選択して、ソース **ツールを開** きます。</span><span class="sxs-lookup"><span data-stu-id="88452-130">Choose the **Sources** tab to open the **Sources** tool.</span></span>  <span data-ttu-id="88452-131">通常 **、ページ** ウィンドウは既定で開きます。</span><span class="sxs-lookup"><span data-stu-id="88452-131">The **Page** pane usually opens by default.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-pane.msft.png" alt-text="左側に [ページ] ウィンドウが開いているソース ツール" lightbox="../media/javascript-sources-page-pane.msft.png":::
       <span data-ttu-id="88452-133">左側 **にページ** ウィンドウ **が開いている** ソース ツール</span><span class="sxs-lookup"><span data-stu-id="88452-133">The **Sources** tool with the **Page** pane open on the left</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="88452-134">[スニペット **] タブを** 選択して 、[スニペット] ウィンドウ **を開** きます。</span><span class="sxs-lookup"><span data-stu-id="88452-134">Choose the **Snippets** tab to open the **Snippets** pane.</span></span>  <span data-ttu-id="88452-135">スニペット オプションにアクセスするには、 **その他の** タブ \( その他のタブ ![ ][ImageMoreTabsIcon] \) を選択 **する必要があります** 。</span><span class="sxs-lookup"><span data-stu-id="88452-135">You may need to choose **More Tabs** \(![More Tabs][ImageMoreTabsIcon]\) to access the **Snippets** option.</span></span>  
    
### <span data-ttu-id="88452-136">コマンド メニューで [スニペット] ウィンドウを開く</span><span class="sxs-lookup"><span data-stu-id="88452-136">Open the Snippets pane with the Command Menu</span></span>  

1.  <span data-ttu-id="88452-137">DevTools のどこかにカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="88452-137">Focus your cursor somewhere in DevTools.</span></span>  
1.  <span data-ttu-id="88452-138">`Control` + `Shift` + `P` \(Windows, Linux\) または `Command` + `Shift` + `P` \(macOS\) を選択してコマンド メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="88452-138">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu.</span></span>  
1.  <span data-ttu-id="88452-139">「入力 `Snippets` 」と入力し **、[スニペットの表示**] を選択し、コマンドの `Enter` 実行を選択します。</span><span class="sxs-lookup"><span data-stu-id="88452-139">Type `Snippets`, choose **Show Snippets**, and then select `Enter` to run the command.</span></span>  
    
    :::image type="complex" source="../media/javascript-search-show-snippets.msft.png" alt-text="[スニペットの表示] コマンド" lightbox="../media/javascript-search-show-snippets.msft.png":::
       <span data-ttu-id="88452-141">[ **スニペットの表示]** コマンド</span><span class="sxs-lookup"><span data-stu-id="88452-141">The **Show Snippets** command</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="88452-142">スニペットを作成する</span><span class="sxs-lookup"><span data-stu-id="88452-142">Create Snippets</span></span>  

### <span data-ttu-id="88452-143">[ソース] パネルを使用してスニペットを作成する</span><span class="sxs-lookup"><span data-stu-id="88452-143">Create a Snippet through the Sources panel</span></span>  

1.  <span data-ttu-id="88452-144">[[スニペット **] ウィンドウを開** きます](#open-the-snippets-pane)。</span><span class="sxs-lookup"><span data-stu-id="88452-144">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="88452-145">[新 **しいスニペット] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="88452-145">Choose **New snippet**.</span></span>  
1.  <span data-ttu-id="88452-146">スニペットの名前を入力し、保存を `Enter` 選択します。</span><span class="sxs-lookup"><span data-stu-id="88452-146">Enter a name for your Snippet then select `Enter` to save.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-snippets-naming.msft.png" alt-text="スニペットに名前を付け" lightbox="../media/javascript-sources-snippets-naming.msft.png":::
       <span data-ttu-id="88452-148">スニペットに名前を付け</span><span class="sxs-lookup"><span data-stu-id="88452-148">Name a Snippet</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="88452-149">コマンド メニューを使用してスニペットを作成する</span><span class="sxs-lookup"><span data-stu-id="88452-149">Create a Snippet through the Command Menu</span></span>  

1.  <span data-ttu-id="88452-150">DevTools のどこかにカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="88452-150">Focus your cursor somewhere in DevTools.</span></span>  
1.  <span data-ttu-id="88452-151">`Control` + `Shift` + `P` \(Windows, Linux\) または `Command` + `Shift` + `P` \(macOS\) を選択してコマンド メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="88452-151">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu.</span></span>  
1.  <span data-ttu-id="88452-152">「入力 `Snippet` 」と入力し **、[新しいスニペットの作成]** を選択し、コマンド `Enter` の実行を選択します。</span><span class="sxs-lookup"><span data-stu-id="88452-152">Type `Snippet`, choose **Create new snippet**, then select `Enter` to run the command.</span></span>  
    
    :::image type="complex" source="../media/javascript-search-create-new-snippet.msft.png" alt-text="新しいスニペットを作成するためのコマンド" lightbox="../media/javascript-search-create-new-snippet.msft.png":::
       <span data-ttu-id="88452-154">新しいスニペットを作成するためのコマンド</span><span class="sxs-lookup"><span data-stu-id="88452-154">The command for creating a new Snippet</span></span>  
    :::image-end:::  
    
<span data-ttu-id="88452-155">新しいスニペットの名前をカスタム名で変更するには、[スニペットの名前の変更 [] に移動します](#rename-snippets)。</span><span class="sxs-lookup"><span data-stu-id="88452-155">To rename your new Snippet with a custom name, navigate to [Rename Snippets](#rename-snippets).</span></span>  

## <span data-ttu-id="88452-156">スニペットの編集</span><span class="sxs-lookup"><span data-stu-id="88452-156">Edit Snippets</span></span>  

1.  <span data-ttu-id="88452-157">[[スニペット **] ウィンドウを開** きます](#open-the-snippets-pane)。</span><span class="sxs-lookup"><span data-stu-id="88452-157">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="88452-158">[ **スニペット] ウィンドウ** で、編集するスニペットの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="88452-158">In the **Snippets** pane, choose the name of the Snippet that you want to edit.</span></span>  <span data-ttu-id="88452-159">コード エディターで **開きます**。</span><span class="sxs-lookup"><span data-stu-id="88452-159">It opens in the **Code Editor**.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-snippets-editor-saved.msft.png" alt-text="コード エディター" lightbox="../media/javascript-sources-snippets-editor-saved.msft.png":::
       <span data-ttu-id="88452-161">コード **エディター**</span><span class="sxs-lookup"><span data-stu-id="88452-161">The **Code Editor**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="88452-162">コード エディター **を使用して** 、スニペットに JavaScript を追加します。</span><span class="sxs-lookup"><span data-stu-id="88452-162">Use the **Code Editor** to add JavaScript to your Snippet.</span></span>  
1.  <span data-ttu-id="88452-163">スニペットの名前の横にアスタリスクが表示されている場合は、コードが保存されていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="88452-163">When an asterisk appears next to the name of your Snippet, it means you have unsaved code.</span></span>  <span data-ttu-id="88452-164">`Control` + `S` \(Windows, Linux\) または `Command` + `S` \(macOS\) を選択して保存します。</span><span class="sxs-lookup"><span data-stu-id="88452-164">Select `Control`+`S` \(Windows, Linux\) or `Command`+`S` \(macOS\) to save.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-snippets-editor-unsaved.msft.png" alt-text="スニペット名の横にあるアスタリスクは、保存されていないコードを示します" lightbox="../media/javascript-sources-snippets-editor-unsaved.msft.png":::
       <span data-ttu-id="88452-166">スニペット名の横にあるアスタリスクは、保存されていないコードを示します</span><span class="sxs-lookup"><span data-stu-id="88452-166">An asterisk next to the Snippet name indicates unsaved code</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="88452-167">スニペットを実行する</span><span class="sxs-lookup"><span data-stu-id="88452-167">Run Snippets</span></span>  

### <span data-ttu-id="88452-168">[ソース] パネルからスニペットを実行する</span><span class="sxs-lookup"><span data-stu-id="88452-168">Run a Snippet from the Sources panel</span></span>  

1.  <span data-ttu-id="88452-169">[[スニペット **] ウィンドウを開** きます](#open-the-snippets-pane)。</span><span class="sxs-lookup"><span data-stu-id="88452-169">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="88452-170">実行するスニペットの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="88452-170">Choose the name of the Snippet that you want to run.</span></span>  <span data-ttu-id="88452-171">スニペットがコード エディターで **開きます**。</span><span class="sxs-lookup"><span data-stu-id="88452-171">The Snippet opens in the **Code Editor**.</span></span>  
1.  <span data-ttu-id="88452-172">[**スニペットの実行**\ ( ![ スニペットの実行 \ ) を ][ImageRunSnippetIcon] 選択するか `Control` + `Enter` 、\(Windows, Linux\) `Command` + `Enter` または \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="88452-172">Choose **Run Snippet** \(![Run Snippet][ImageRunSnippetIcon]\), or select `Control`+`Enter` \(Windows, Linux\) or `Command`+`Enter` \(macOS\).</span></span>  
    
### <span data-ttu-id="88452-173">コマンド メニューを使用してスニペットを実行する</span><span class="sxs-lookup"><span data-stu-id="88452-173">Run a Snippet with the Command Menu</span></span>  

1.  <span data-ttu-id="88452-174">DevTools のどこかにカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="88452-174">Focus your cursor somewhere in DevTools.</span></span>  
1.  <span data-ttu-id="88452-175">`Control` + `Shift` + `P` \(Windows, Linux\) または `Command` + `Shift` + `P` \(macOS\) を選択してコマンド メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="88452-175">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu.</span></span>  
1.  <span data-ttu-id="88452-176">文字を `>` 削除し、その `!` 文字の後に実行するスニペットの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="88452-176">Delete the `>` character and type the `!` character followed by the name of the Snippet that you want to run.</span></span>  
    
    :::image type="complex" source="../media/javascript-search-run-command.msft.png" alt-text="コマンド メニューからのスニペットの実行" lightbox="../media/javascript-search-run-command.msft.png":::
       <span data-ttu-id="88452-178">コマンド メニューからのスニペット **の実行**</span><span class="sxs-lookup"><span data-stu-id="88452-178">Running a Snippet from the **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="88452-179">スニペット `Enter` を実行する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="88452-179">Select `Enter` to run the Snippet.</span></span>  

## <span data-ttu-id="88452-180">スニペットの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="88452-180">Rename Snippets</span></span>  

1.  <span data-ttu-id="88452-181">[[スニペット **] ウィンドウを開** きます](#open-the-snippets-pane)。</span><span class="sxs-lookup"><span data-stu-id="88452-181">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="88452-182">スニペット名をポイントし、コンテキスト メニュー \(右クリック\) を開き、[名前の変更] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="88452-182">Hover on the Snippet name, open the contextual menu \(right-click\), and choose **Rename**.</span></span>  
    
## <span data-ttu-id="88452-183">スニペットを削除する</span><span class="sxs-lookup"><span data-stu-id="88452-183">Delete Snippets</span></span>  

1.  <span data-ttu-id="88452-184">[[スニペット **] ウィンドウを開** きます](#open-the-snippets-pane)。</span><span class="sxs-lookup"><span data-stu-id="88452-184">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="88452-185">スニペット名をポイントし、コンテキスト メニュー \(右クリック\) を開き、[削除] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="88452-185">Hover on the Snippet name, open the contextual menu \(right-click\), and choose **Remove**.</span></span>  
    
## <span data-ttu-id="88452-186">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="88452-186">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageMoreTabsIcon]: ../media/more-tabs-icon.msft.png  
[ImageRunSnippetIcon]: ../media/run-snippet-icon.msft.png  

<!-- links -->  

[DevtoolsConsoleIndex]: ../console/index.md "コンソールの概要 |Microsoft Docs"  
[DevToolsSourcesTool]: ../sources/index.md "ソース ツールの概要 |Microsoft Docs"  
[DevtoolsJavascriptOverrides]: ./overrides.md "Overrides |Microsoft Docs"  

[MDNScratchpad]: https://developer.mozilla.org/docs/Tools/Scratchpad "スクラッチパッド |MDN"  
[WikiBookmarklet]: https://en.wikipedia.org/wiki/Bookmarklet "Bookmarklet |Wikipedia"  

> [!NOTE]
> <span data-ttu-id="88452-192">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="88452-192">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="88452-193">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/snippets) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="88452-193">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/snippets) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="88452-195">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="88452-195">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
