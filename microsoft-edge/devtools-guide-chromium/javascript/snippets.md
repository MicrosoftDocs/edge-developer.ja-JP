---
description: スニペットは、Microsoft Edge DevTools のソースツールで作成および実行できる小さなスクリプトです。  どの web ページからでも、リソースにアクセスして実行することができます。  スニペットを実行すると、現在開いている web ページのコンテキストから実行されます。
title: Microsoft Edge DevTools を使用して、任意のページで JavaScript のスニペットを実行します。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/29/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 3542243f7fa886865ced47d47991cd9b11001e2e
ms.sourcegitcommit: 9dcaf598f3930bcfab9f93ff63463beb98274de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2020
ms.locfileid: "11145121"
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

# <span data-ttu-id="e55cb-106">Microsoft Edge DevTools を使用して、任意の web ページで JavaScript のスニペットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e55cb-106">Run snippets of JavaScript on any webpage with Microsoft Edge DevTools</span></span>  

<span data-ttu-id="e55cb-107">[コンソール][DevtoolsConsoleIndex]で同じコードを繰り返し実行する場合は、代わりにスニペットとしてコードを保存することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="e55cb-107">If you are running the same code in the [Console][DevtoolsConsoleIndex] repeatedly, consider saving the code as a Snippet instead.</span></span>  <span data-ttu-id="e55cb-108">スニペットは、 [ソース][DevToolsSourcesTool] ツールで作成したスクリプトです。</span><span class="sxs-lookup"><span data-stu-id="e55cb-108">Snippets are scripts that you author in the [Sources][DevToolsSourcesTool] tool.</span></span>  <span data-ttu-id="e55cb-109">スニペットは、web ページの JavaScript コンテキストにアクセスできます。また、スニペットはどの web ページでも実行できます。</span><span class="sxs-lookup"><span data-stu-id="e55cb-109">Snippets have access to the JavaScript context of the webpage, and you may run snippets on any webpage.</span></span>  <span data-ttu-id="e55cb-110">ほとんどの web ページブロックのセキュリティ設定では、スニペットで他のスクリプトを読み込むことができません。</span><span class="sxs-lookup"><span data-stu-id="e55cb-110">The security settings of most webpages block from loading other scripts in Snippets.</span></span>  <span data-ttu-id="e55cb-111">そのため、すべてのコードを1つのファイルに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="e55cb-111">For that reason, you must include all your code in one file.</span></span>  

<span data-ttu-id="e55cb-112">スニペットは、 [bookmarklets][WikiBookmarklet] の代わりとなるものです。スニペットは、devtools でのみ実行され、URL の許容される長さに制限されないという違いがあります。</span><span class="sxs-lookup"><span data-stu-id="e55cb-112">Snippets are an alternative to [bookmarklets][WikiBookmarklet] with the difference that Snippets only run in DevTools and are not limited to the allowed length of a URL.</span></span>  

<span data-ttu-id="e55cb-113">スニペットの使用は、サードパーティの web ページでいくつかの項目を変更する優れた方法です。</span><span class="sxs-lookup"><span data-stu-id="e55cb-113">Using Snippets is an excellent way to change a few things in a third-party webpage.</span></span>  <span data-ttu-id="e55cb-114">スニペットのコードの変更は、現在の web ページに追加され、同じコンテキストで実行されます。</span><span class="sxs-lookup"><span data-stu-id="e55cb-114">Code changes in Snippets are added to the current webpage and run in the same context.</span></span>  <span data-ttu-id="e55cb-115">Web ページの既存のコードを変更する方法について詳しくは、[ [上書き][DevtoolsJavascriptOverrides]] に移動してください。</span><span class="sxs-lookup"><span data-stu-id="e55cb-115">For more information about changing the existing code of a webpage, navigate to [Overrides][DevtoolsJavascriptOverrides].</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="e55cb-116">たとえば、次の図は、左側の DevTools ホームページと右側にあるスニペットソースコードを示しています。</span><span class="sxs-lookup"><span data-stu-id="e55cb-116">For example, in the following figure shows the DevTools homepage on the left and some Snippet source code on the right.</span></span>  
      
      :::image type="complex" source="../media/javascript-sources-snippets-split-screen.msft.png" alt-text="スニペットを実行する前に" lightbox="../media/javascript-sources-snippets-split-screen.msft.png":::
         <span data-ttu-id="e55cb-118">スニペットを実行する前の web ページ</span><span class="sxs-lookup"><span data-stu-id="e55cb-118">The webpage before running the Snippet</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="e55cb-119">スニペットを実行する前の web ページのスニペットソースコード。</span><span class="sxs-lookup"><span data-stu-id="e55cb-119">The Snippet source code from the webpage before running the Snippet.</span></span>  
      
      ```javascript
      console.log('Hello, Snippets!');
      document.body.innerHTML = '';
      var p = document.createElement('p');
      p.textContent = 'Hello, Snippets!';
      document.body.appendChild(p);
      ```
   :::column-end:::
:::row-end:::  

<span data-ttu-id="e55cb-120">次の図は、スニペットを実行した後に web ページが表示されることを示しています。</span><span class="sxs-lookup"><span data-stu-id="e55cb-120">In the following figure, the webpage appears after running the Snippet.</span></span>  <span data-ttu-id="e55cb-121">**本体の引き出し**がポップアップ表示され、スニペットがログに記録され、 `Hello, Snippets!` web ページの内容が完全に変更されます。</span><span class="sxs-lookup"><span data-stu-id="e55cb-121">The **Console Drawer** pops up to display the `Hello, Snippets!` message that the Snippet logs, and the content of the webpage changes completely.</span></span>  

:::image type="complex" source="../media/javascript-sources-snippets-split-screen-after.msft.png" alt-text="スニペットを実行した後の web ページ" lightbox="../media/javascript-sources-snippets-split-screen-after.msft.png":::
   <span data-ttu-id="e55cb-123">スニペットを実行した後の web ページ</span><span class="sxs-lookup"><span data-stu-id="e55cb-123">The webpage after running the Snippet</span></span>  
:::image-end:::  

## <span data-ttu-id="e55cb-124">[スニペット] ウィンドウを開く</span><span class="sxs-lookup"><span data-stu-id="e55cb-124">Open the Snippets pane</span></span>  

<span data-ttu-id="e55cb-125">[ **スニペット** ] ウィンドウにスニペットの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e55cb-125">The **Snippets** pane lists your Snippets.</span></span>  <span data-ttu-id="e55cb-126">スニペットを編集するには、スニペットを [ **スニペット** ] ウィンドウから開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="e55cb-126">When you want to edit a Snippet, you need to open it from the **Snippets** pane.</span></span>  

:::image type="complex" source="../media/javascript-sources-snippets-pane.msft.png" alt-text="[スニペット] ウィンドウ" lightbox="../media/javascript-sources-snippets-pane.msft.png":::
   <span data-ttu-id="e55cb-128">[ **スニペット** ] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="e55cb-128">The **Snippets** pane</span></span>  
:::image-end:::  

### <span data-ttu-id="e55cb-129">[スニペット] ウィンドウをマウスで開く</span><span class="sxs-lookup"><span data-stu-id="e55cb-129">Open the Snippets pane with a mouse</span></span>  

1.  <span data-ttu-id="e55cb-130">[ **ソース** ] タブを選択して、 **ソース** ツールを開きます。</span><span class="sxs-lookup"><span data-stu-id="e55cb-130">Choose the **Sources** tab to open the **Sources** tool.</span></span>  <span data-ttu-id="e55cb-131">通常、 **ページ** ウィンドウは既定で開かれます。</span><span class="sxs-lookup"><span data-stu-id="e55cb-131">The **Page** pane usually opens by default.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-pane.msft.png" alt-text="左側にページウィンドウが表示されたソースツール" lightbox="../media/javascript-sources-page-pane.msft.png":::
       <span data-ttu-id="e55cb-133">左側に**ページ**ウィンドウが表示された**ソース**ツール</span><span class="sxs-lookup"><span data-stu-id="e55cb-133">The **Sources** tool with the **Page** pane open on the left</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="e55cb-134">[ **スニペット** ] タブを選択して、[ **スニペット** ] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="e55cb-134">Choose the **Snippets** tab to open the **Snippets** pane.</span></span>  <span data-ttu-id="e55cb-135">[スニペット] オプションにアクセスするには、[**その他のタブ**] ([ ![ その他のタブ \]) を選択する必要がある場合があり ][ImageMoreTabsIcon] ます。 **Snippets**</span><span class="sxs-lookup"><span data-stu-id="e55cb-135">You may need to choose **More Tabs** \(![More Tabs][ImageMoreTabsIcon]\) to access the **Snippets** option.</span></span>  
    
### <span data-ttu-id="e55cb-136">[スニペット] ウィンドウでコマンドメニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="e55cb-136">Open the Snippets pane with the Command Menu</span></span>  

1.  <span data-ttu-id="e55cb-137">DevTools 内の任意の場所にカーソルを置きます。</span><span class="sxs-lookup"><span data-stu-id="e55cb-137">Focus your cursor somewhere in DevTools.</span></span>  
1.  <span data-ttu-id="e55cb-138">`Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows, Linux \) または `Command` + `Shift` + `P` \ (macOS \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="e55cb-138">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu.</span></span>  
1.  <span data-ttu-id="e55cb-139">入力し `Snippets` 、[ **スニペットの表示**] を選択して、コマンドを実行し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="e55cb-139">Type `Snippets`, choose **Show Snippets**, and then select `Enter` to run the command.</span></span>  
    
    :::image type="complex" source="../media/javascript-search-show-snippets.msft.png" alt-text="[スニペットの表示] コマンド" lightbox="../media/javascript-search-show-snippets.msft.png":::
       <span data-ttu-id="e55cb-141">[ **スニペットの表示** ] コマンド</span><span class="sxs-lookup"><span data-stu-id="e55cb-141">The **Show Snippets** command</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="e55cb-142">スニペットを作成する</span><span class="sxs-lookup"><span data-stu-id="e55cb-142">Create Snippets</span></span>  

### <span data-ttu-id="e55cb-143">ソースパネルを使用してスニペットを作成する</span><span class="sxs-lookup"><span data-stu-id="e55cb-143">Create a Snippet through the Sources panel</span></span>  

1.  <span data-ttu-id="e55cb-144">[ [**スニペット**] ウィンドウを開き](#open-the-snippets-pane)ます。</span><span class="sxs-lookup"><span data-stu-id="e55cb-144">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="e55cb-145">[ **新しいスニペット**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e55cb-145">Choose **New snippet**.</span></span>  
1.  <span data-ttu-id="e55cb-146">スニペットの名前を入力し、[ `Enter` 保存] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e55cb-146">Enter a name for your Snippet then select `Enter` to save.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-snippets-naming.msft.png" alt-text="スニペットに名前を指定する" lightbox="../media/javascript-sources-snippets-naming.msft.png":::
       <span data-ttu-id="e55cb-148">スニペットに名前を指定する</span><span class="sxs-lookup"><span data-stu-id="e55cb-148">Name a Snippet</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="e55cb-149">コマンドメニューを使用してスニペットを作成する</span><span class="sxs-lookup"><span data-stu-id="e55cb-149">Create a Snippet through the Command Menu</span></span>  

1.  <span data-ttu-id="e55cb-150">DevTools 内の任意の場所にカーソルを置きます。</span><span class="sxs-lookup"><span data-stu-id="e55cb-150">Focus your cursor somewhere in DevTools.</span></span>  
1.  <span data-ttu-id="e55cb-151">`Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows, Linux \) または `Command` + `Shift` + `P` \ (macOS \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="e55cb-151">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu.</span></span>  
1.  <span data-ttu-id="e55cb-152">「 `Snippet` **新規スニペットの作成**」を選択し、 `Enter` コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e55cb-152">Type `Snippet`, choose **Create new snippet**, then select `Enter` to run the command.</span></span>  
    
    :::image type="complex" source="../media/javascript-search-create-new-snippet.msft.png" alt-text="新しいスニペットを作成するためのコマンド" lightbox="../media/javascript-search-create-new-snippet.msft.png":::
       <span data-ttu-id="e55cb-154">新しいスニペットを作成するためのコマンド</span><span class="sxs-lookup"><span data-stu-id="e55cb-154">The command for creating a new Snippet</span></span>  
    :::image-end:::  
    
<span data-ttu-id="e55cb-155">新しいスニペットの名前をカスタム名に変更するには、[スニペット名の [変更](#rename-snippets)] に移動します。</span><span class="sxs-lookup"><span data-stu-id="e55cb-155">To rename your new Snippet with a custom name, navigate to [Rename Snippets](#rename-snippets).</span></span>  

## <span data-ttu-id="e55cb-156">スニペットを編集する</span><span class="sxs-lookup"><span data-stu-id="e55cb-156">Edit Snippets</span></span>  

1.  <span data-ttu-id="e55cb-157">[ [**スニペット**] ウィンドウを開き](#open-the-snippets-pane)ます。</span><span class="sxs-lookup"><span data-stu-id="e55cb-157">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="e55cb-158">[ **スニペット** ] ウィンドウで、編集するスニペットの名前を選びます。</span><span class="sxs-lookup"><span data-stu-id="e55cb-158">In the **Snippets** pane, choose the name of the Snippet that you want to edit.</span></span>  <span data-ttu-id="e55cb-159">**コードエディター**で開きます。</span><span class="sxs-lookup"><span data-stu-id="e55cb-159">It opens in the **Code Editor**.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-snippets-editor-saved.msft.png" alt-text="コードエディター" lightbox="../media/javascript-sources-snippets-editor-saved.msft.png":::
       <span data-ttu-id="e55cb-161">**コードエディター**</span><span class="sxs-lookup"><span data-stu-id="e55cb-161">The **Code Editor**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="e55cb-162">**コードエディター**を使用して、スニペットに JavaScript を追加します。</span><span class="sxs-lookup"><span data-stu-id="e55cb-162">Use the **Code Editor** to add JavaScript to your Snippet.</span></span>  
1.  <span data-ttu-id="e55cb-163">スニペットの名前の横にアスタリスクが表示される場合は、コードが保存されていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="e55cb-163">When an asterisk appears next to the name of your Snippet, it means you have unsaved code.</span></span>  <span data-ttu-id="e55cb-164">`Control` + `S` 保存するには、\ (Windows、Linux \) または `Command` + `S` \ (macOS \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="e55cb-164">Select `Control`+`S` \(Windows, Linux\) or `Command`+`S` \(macOS\) to save.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-snippets-editor-unsaved.msft.png" alt-text="スニペット名の横にあるアスタリスクは、保存されていないコードを示します。" lightbox="../media/javascript-sources-snippets-editor-unsaved.msft.png":::
       <span data-ttu-id="e55cb-166">スニペット名の横にあるアスタリスクは、保存されていないコードを示します。</span><span class="sxs-lookup"><span data-stu-id="e55cb-166">An asterisk next to the Snippet name indicates unsaved code</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="e55cb-167">スニペットの実行</span><span class="sxs-lookup"><span data-stu-id="e55cb-167">Run Snippets</span></span>  

### <span data-ttu-id="e55cb-168">[ソース] パネルからスニペットを実行する</span><span class="sxs-lookup"><span data-stu-id="e55cb-168">Run a Snippet from the Sources panel</span></span>  

1.  <span data-ttu-id="e55cb-169">[ [**スニペット**] ウィンドウを開き](#open-the-snippets-pane)ます。</span><span class="sxs-lookup"><span data-stu-id="e55cb-169">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="e55cb-170">実行するスニペットの名前を選びます。</span><span class="sxs-lookup"><span data-stu-id="e55cb-170">Choose the name of the Snippet that you want to run.</span></span>  <span data-ttu-id="e55cb-171">スニペットが **コードエディター**で開きます。</span><span class="sxs-lookup"><span data-stu-id="e55cb-171">The Snippet opens in the **Code Editor**.</span></span>  
1.  <span data-ttu-id="e55cb-172">[ **Run スニペット**\ ( ![ スニペットを実行し ][ImageRunSnippetIcon] ます)] または [\ ( `Control` + `Enter` Windows、Linux \)] または [ `Command` + `Enter` \ (macOS \)] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e55cb-172">Choose **Run Snippet** \(![Run Snippet][ImageRunSnippetIcon]\), or select `Control`+`Enter` \(Windows, Linux\) or `Command`+`Enter` \(macOS\).</span></span>  
    
### <span data-ttu-id="e55cb-173">コマンドメニューを使用してスニペットを実行する</span><span class="sxs-lookup"><span data-stu-id="e55cb-173">Run a Snippet with the Command Menu</span></span>  

1.  <span data-ttu-id="e55cb-174">DevTools 内の任意の場所にカーソルを置きます。</span><span class="sxs-lookup"><span data-stu-id="e55cb-174">Focus your cursor somewhere in DevTools.</span></span>  
1.  <span data-ttu-id="e55cb-175">`Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows, Linux \) または `Command` + `Shift` + `P` \ (macOS \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="e55cb-175">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu.</span></span>  
1.  <span data-ttu-id="e55cb-176">文字を削除 `>` して、 `!` 実行するスニペットの名前の後に文字を入力します。</span><span class="sxs-lookup"><span data-stu-id="e55cb-176">Delete the `>` character and type the `!` character followed by the name of the Snippet that you want to run.</span></span>  
    
    :::image type="complex" source="../media/javascript-search-run-command.msft.png" alt-text="コマンドメニューからのスニペットの実行" lightbox="../media/javascript-search-run-command.msft.png":::
       <span data-ttu-id="e55cb-178">**コマンドメニュー**からのスニペットの実行</span><span class="sxs-lookup"><span data-stu-id="e55cb-178">Running a Snippet from the **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="e55cb-179">`Enter`スニペットを実行する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="e55cb-179">Select `Enter` to run the Snippet.</span></span>  

## <span data-ttu-id="e55cb-180">スニペットの名前変更</span><span class="sxs-lookup"><span data-stu-id="e55cb-180">Rename Snippets</span></span>  

1.  <span data-ttu-id="e55cb-181">[ [**スニペット**] ウィンドウを開き](#open-the-snippets-pane)ます。</span><span class="sxs-lookup"><span data-stu-id="e55cb-181">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="e55cb-182">スニペット名の上にカーソルを置いてコンテキストメニューを開き (\ [\] を右クリックし)、[ **名前の変更**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e55cb-182">Hover on the Snippet name, open the contextual menu \(right-click\), and choose **Rename**.</span></span>  
    
## <span data-ttu-id="e55cb-183">スニペットを削除する</span><span class="sxs-lookup"><span data-stu-id="e55cb-183">Delete Snippets</span></span>  

1.  <span data-ttu-id="e55cb-184">[ [**スニペット**] ウィンドウを開き](#open-the-snippets-pane)ます。</span><span class="sxs-lookup"><span data-stu-id="e55cb-184">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="e55cb-185">スニペット名の上にカーソルを置いて、コンテキストメニューを開き (\ [\] を右クリックし)、[ **削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e55cb-185">Hover on the Snippet name, open the contextual menu \(right-click\), and choose **Remove**.</span></span>  
    
## <span data-ttu-id="e55cb-186">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="e55cb-186">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageMoreTabsIcon]: ../media/more-tabs-icon.msft.png  
[ImageRunSnippetIcon]: ../media/run-snippet-icon.msft.png  

<!-- links -->  

[DevtoolsConsoleIndex]: ../console/index.md "本体の概要 |Microsoft ドキュメント"  
[DevToolsSourcesTool]: ../sources.md "ソースツールの概要 |Microsoft ドキュメント"  
[DevtoolsJavascriptOverrides]: ./overrides.md "Overrides |Microsoft ドキュメント"  

[MDNScratchpad]: https://developer.mozilla.org/docs/Tools/Scratchpad "書い |MDN"  
[WikiBookmarklet]: https://en.wikipedia.org/wiki/Bookmarklet "Bookmarklet |Wikipedia"  

> [!NOTE]
> <span data-ttu-id="e55cb-192">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="e55cb-192">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="e55cb-193">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/snippets) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="e55cb-193">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/snippets) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="e55cb-195">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="e55cb-195">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
