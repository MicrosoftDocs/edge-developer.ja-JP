---
description: スニペットは、DevTools の Sources ツール内で作成および実行できる小Microsoft Edgeです。  Web ページからリソースにアクセスして実行できます。  スニペットを実行すると、現在開いている Web ページのコンテキストから実行されます。
title: DevTools を使用して任意の Web ページで JavaScript のスニペットMicrosoft Edge実行する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 00c612a1573c7446711a2dc9d22985c83140eecd
ms.sourcegitcommit: 16e2f7232196a57a70b979bbf8b663774b7ddc20
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/25/2021
ms.locfileid: "11519430"
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

# <a name="run-snippets-of-javascript-on-any-webpage-with-microsoft-edge-devtools"></a><span data-ttu-id="9025c-106">DevTools を使用して任意の Web ページで JavaScript のスニペットMicrosoft Edge実行する</span><span class="sxs-lookup"><span data-stu-id="9025c-106">Run snippets of JavaScript on any webpage with Microsoft Edge DevTools</span></span>  

<span data-ttu-id="9025c-107">コンソールで同じコードを繰り返[][DevtoolsConsoleIndex]し実行している場合は、コードをスニペットとして保存してください。</span><span class="sxs-lookup"><span data-stu-id="9025c-107">If you are running the same code in the [Console][DevtoolsConsoleIndex] repeatedly, consider saving the code as a Snippet instead.</span></span>  <span data-ttu-id="9025c-108">スニペットは、ソース ツールで作成する [スクリプト][DevToolsSourcesTool] です。</span><span class="sxs-lookup"><span data-stu-id="9025c-108">Snippets are scripts that you author in the [Sources][DevToolsSourcesTool] tool.</span></span>  <span data-ttu-id="9025c-109">スニペットは Web ページの JavaScript コンテキストにアクセスし、任意の Web ページでスニペットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="9025c-109">Snippets have access to the JavaScript context of the webpage, and you may run snippets on any webpage.</span></span>  <span data-ttu-id="9025c-110">ほとんどの Web ページのセキュリティ設定は、スニペットに他のスクリプトを読み込むのをブロックします。</span><span class="sxs-lookup"><span data-stu-id="9025c-110">The security settings of most webpages block from loading other scripts in Snippets.</span></span>  <span data-ttu-id="9025c-111">このため、すべてのコードを 1 つのファイルに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="9025c-111">For that reason, you must include all your code in one file.</span></span>  

<span data-ttu-id="9025c-112">スニペットは、スニペットが[][WikiBookmarklet]DevTools でのみ実行されるという違いを持つブックマークレットの代わりであり、URL の許可される長さに限定されません。</span><span class="sxs-lookup"><span data-stu-id="9025c-112">Snippets are an alternative to [bookmarklets][WikiBookmarklet] with the difference that Snippets only run in DevTools and are not limited to the allowed length of a URL.</span></span>  

<span data-ttu-id="9025c-113">スニペットの使用は、サードパーティの Web ページでいくつかの変更を行う優れた方法です。</span><span class="sxs-lookup"><span data-stu-id="9025c-113">Using Snippets is an excellent way to change a few things in a third-party webpage.</span></span>  <span data-ttu-id="9025c-114">スニペットのコードの変更は、現在の Web ページに追加され、同じコンテキストで実行されます。</span><span class="sxs-lookup"><span data-stu-id="9025c-114">Code changes in Snippets are added to the current webpage and run in the same context.</span></span>  <span data-ttu-id="9025c-115">Web ページの既存のコードを変更する方法の詳細については [、「Overrides」に移動します][DevtoolsJavascriptOverrides]。</span><span class="sxs-lookup"><span data-stu-id="9025c-115">For more information about changing the existing code of a webpage, navigate to [Overrides][DevtoolsJavascriptOverrides].</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="9025c-116">たとえば、次の図に、左側の DevTools ホームページと、右側のスニペット ソース コードを示します。</span><span class="sxs-lookup"><span data-stu-id="9025c-116">For example, in the following figure shows the DevTools homepage on the left and some Snippet source code on the right.</span></span>  
      
      :::image type="complex" source="../media/javascript-sources-snippets-split-screen.msft.png" alt-text="スニペットを実行する前に" lightbox="../media/javascript-sources-snippets-split-screen.msft.png":::
         <span data-ttu-id="9025c-118">スニペットを実行する前の Web ページ</span><span class="sxs-lookup"><span data-stu-id="9025c-118">The webpage before running the Snippet</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="9025c-119">スニペットを実行する前の Web ページのスニペット ソース コード。</span><span class="sxs-lookup"><span data-stu-id="9025c-119">The Snippet source code from the webpage before running the Snippet.</span></span>  
      
      ```javascript
      console.log('Hello, Snippets!');
      document.body.innerHTML = '';
      var p = document.createElement('p');
      p.textContent = 'Hello, Snippets!';
      document.body.appendChild(p);
      ```
   :::column-end:::
:::row-end:::  

<span data-ttu-id="9025c-120">次の図では、スニペットの実行後に Web ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9025c-120">In the following figure, the webpage appears after running the Snippet.</span></span>  <span data-ttu-id="9025c-121">コンソール **ドロワー** がポップアップ表示され、スニペットによってログに記録されるメッセージが表示され、Web ページの内容 `Hello, Snippets!` が完全に変更されます。</span><span class="sxs-lookup"><span data-stu-id="9025c-121">The **Console Drawer** pops up to display the `Hello, Snippets!` message that the Snippet logs, and the content of the webpage changes completely.</span></span>  

:::image type="complex" source="../media/javascript-sources-snippets-split-screen-after.msft.png" alt-text="スニペットの実行後の Web ページ" lightbox="../media/javascript-sources-snippets-split-screen-after.msft.png":::
   <span data-ttu-id="9025c-123">スニペットの実行後の Web ページ</span><span class="sxs-lookup"><span data-stu-id="9025c-123">The webpage after running the Snippet</span></span>  
:::image-end:::  

## <a name="open-the-snippets-tab"></a><span data-ttu-id="9025c-124">[スニペット] タブを開く</span><span class="sxs-lookup"><span data-stu-id="9025c-124">Open the Snippets tab</span></span>  

<span data-ttu-id="9025c-125">左側 **の [** ナビゲーター] ウィンドウの [ **スニペット** ] タブに、スニペットの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9025c-125">The **Snippets** tab, in the **Navigator** pane on the left, lists your Snippets.</span></span>  <span data-ttu-id="9025c-126">スニペットを編集する場合は、[スニペット] タブから **スニペットを開く必要** があります。</span><span class="sxs-lookup"><span data-stu-id="9025c-126">When you want to edit a Snippet, you need to open it from the **Snippets** tab.</span></span>  

:::image type="complex" source="../media/javascript-sources-snippets-pane.msft.png" alt-text="[スニペット] タブ" lightbox="../media/javascript-sources-snippets-pane.msft.png":::
   <span data-ttu-id="9025c-128">[ **スニペット]** タブ</span><span class="sxs-lookup"><span data-stu-id="9025c-128">The **Snippets** tab</span></span>  
:::image-end:::  

### <a name="open-the-snippets-tab-with-a-mouse"></a><span data-ttu-id="9025c-129">マウスで [スニペット] タブを開く</span><span class="sxs-lookup"><span data-stu-id="9025c-129">Open the Snippets tab with a mouse</span></span>  

1.  <span data-ttu-id="9025c-130">[ソース] **タブを選択** します。 [ **ソース] ツール** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9025c-130">Choose the **Sources** tab.  The **Sources** tool appears.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-pane.msft.png" alt-text="左側の [ページ] タブを開いた [ソース] ツール" lightbox="../media/javascript-sources-page-pane.msft.png":::
       <span data-ttu-id="9025c-132">左側 **の [** ページ] タブ **を開** いた [ソース] ツール</span><span class="sxs-lookup"><span data-stu-id="9025c-132">The **Sources** tool with the **Page** tab open on the left</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9025c-133">左側の **[ナビゲーター]** ウィンドウで、[スニペット] **タブを選択** します。 スニペット オプションに **アクセスするには** 、[その他のタブ] \( More **tabs** \) を選択 ![ する必要 ](../media/more-tabs-icon.msft.png) があります。</span><span class="sxs-lookup"><span data-stu-id="9025c-133">In the **Navigator** pane (on the left), choose the **Snippets** tab.  To access the **Snippets** option, you may need to choose **More tabs** \(![More tabs](../media/more-tabs-icon.msft.png)\).</span></span>  
    
### <a name="open-the-snippets-tab-with-the-command-menu"></a><span data-ttu-id="9025c-134">コマンド メニューで [スニペット] タブを開く</span><span class="sxs-lookup"><span data-stu-id="9025c-134">Open the Snippets tab with the Command Menu</span></span>  

1.  <span data-ttu-id="9025c-135">DevTools で何かを選択して、DevTools にフォーカスを設定します。</span><span class="sxs-lookup"><span data-stu-id="9025c-135">Select anything in DevTools, so that DevTools has focus.</span></span>  
1.  <span data-ttu-id="9025c-136">`Control` + `Shift` + `P` コマンド メニューを開Windows \(Windows Linux\) または `Command` + `Shift` + `P` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="9025c-136">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu.</span></span>  
1.  <span data-ttu-id="9025c-137">[ `Snippets` スニペットの **表示] を選択**し、コマンドを `Enter` 実行する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="9025c-137">Type `Snippets`, choose **Show Snippets**, and then select `Enter` to run the command.</span></span>  
    
    :::image type="complex" source="../media/javascript-search-show-snippets.msft.png" alt-text="[スニペットの表示] コマンド" lightbox="../media/javascript-search-show-snippets.msft.png":::
       <span data-ttu-id="9025c-139">[ **スニペットの表示]** コマンド</span><span class="sxs-lookup"><span data-stu-id="9025c-139">The **Show Snippets** command</span></span>  
    :::image-end:::  
    
## <a name="create-snippets"></a><span data-ttu-id="9025c-140">スニペットの作成</span><span class="sxs-lookup"><span data-stu-id="9025c-140">Create Snippets</span></span>  

### <a name="create-a-snippet-through-the-sources-tool"></a><span data-ttu-id="9025c-141">ソース ツールを使用してスニペットを作成する</span><span class="sxs-lookup"><span data-stu-id="9025c-141">Create a Snippet through the Sources tool</span></span>  

1.  <span data-ttu-id="9025c-142">[[スニペット] タブを開きます](#open-the-snippets-tab)。</span><span class="sxs-lookup"><span data-stu-id="9025c-142">[Open the Snippets tab](#open-the-snippets-tab).</span></span>  
1.  <span data-ttu-id="9025c-143">[新 **しいスニペット] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="9025c-143">Choose **New snippet**.</span></span>  
1.  <span data-ttu-id="9025c-144">スニペットの名前を入力し、[. `Enter`</span><span class="sxs-lookup"><span data-stu-id="9025c-144">Enter a name for your Snippet, and then select `Enter`.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-snippets-naming.msft.png" alt-text="スニペットに名前を付け" lightbox="../media/javascript-sources-snippets-naming.msft.png":::
       <span data-ttu-id="9025c-146">スニペットに名前を付け</span><span class="sxs-lookup"><span data-stu-id="9025c-146">Name a Snippet</span></span>  
    :::image-end:::  
    
### <a name="create-a-snippet-through-the-command-menu"></a><span data-ttu-id="9025c-147">コマンド メニューからスニペットを作成する</span><span class="sxs-lookup"><span data-stu-id="9025c-147">Create a Snippet through the Command Menu</span></span>  

1.  <span data-ttu-id="9025c-148">DevTools のどこかにカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="9025c-148">Focus your cursor somewhere in DevTools.</span></span>  
1.  <span data-ttu-id="9025c-149">`Control` + `Shift` + `P` コマンド メニューを開Windows \(Windows Linux\) または `Command` + `Shift` + `P` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="9025c-149">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu.</span></span>  
1.  <span data-ttu-id="9025c-150">[ `Snippet` 新しいスニペットの **作成] を**選択し、コマンド `Enter` を実行する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="9025c-150">Type `Snippet`, choose **Create new snippet**, then select `Enter` to run the command.</span></span>  
    
    :::image type="complex" source="../media/javascript-search-create-new-snippet.msft.png" alt-text="新しいスニペットを作成するためのコマンド" lightbox="../media/javascript-search-create-new-snippet.msft.png":::
       <span data-ttu-id="9025c-152">新しいスニペットを作成するためのコマンド</span><span class="sxs-lookup"><span data-stu-id="9025c-152">The command for creating a new Snippet</span></span>  
    :::image-end:::  
    
<span data-ttu-id="9025c-153">カスタム名を使用して新しいスニペットの名前を変更するには、[スニペットの名前の変更 [] に移動します](#rename-snippets)。</span><span class="sxs-lookup"><span data-stu-id="9025c-153">To rename your new Snippet with a custom name, navigate to [Rename Snippets](#rename-snippets).</span></span>  

## <a name="edit-snippets"></a><span data-ttu-id="9025c-154">スニペットの編集</span><span class="sxs-lookup"><span data-stu-id="9025c-154">Edit Snippets</span></span>  

1.  <span data-ttu-id="9025c-155">[[スニペット] タブを開きます](#open-the-snippets-tab)。</span><span class="sxs-lookup"><span data-stu-id="9025c-155">[Open the Snippets tab](#open-the-snippets-tab).</span></span>  
1.  <span data-ttu-id="9025c-156">[スニペット **] タブ** で、編集するスニペットの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="9025c-156">In the **Snippets** tab, choose the name of the Snippet that you want to edit.</span></span>  <span data-ttu-id="9025c-157">コード エディターで **開きます**。</span><span class="sxs-lookup"><span data-stu-id="9025c-157">It opens in the **Code Editor**.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-snippets-editor-saved.msft.png" alt-text="コード エディター" lightbox="../media/javascript-sources-snippets-editor-saved.msft.png":::
       <span data-ttu-id="9025c-159">コード **エディター**</span><span class="sxs-lookup"><span data-stu-id="9025c-159">The **Code Editor**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9025c-160">コード エディター **を使用して** 、スニペットに JavaScript を追加します。</span><span class="sxs-lookup"><span data-stu-id="9025c-160">Use the **Code Editor** to add JavaScript to your Snippet.</span></span>  
1.  <span data-ttu-id="9025c-161">スニペットの名前の横にアスタリスクが表示される場合は、コードが保存されていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="9025c-161">When an asterisk appears next to the name of your Snippet, it means you have unsaved code.</span></span>  <span data-ttu-id="9025c-162">`Control` + `S` \(Windows Linux\) または `Command` + `S` \(macOS\) を選択して保存します。</span><span class="sxs-lookup"><span data-stu-id="9025c-162">Select `Control`+`S` \(Windows, Linux\) or `Command`+`S` \(macOS\) to save.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-snippets-editor-unsaved.msft.png" alt-text="スニペット名の横にあるアスタリスクは、保存されていないコードを示します" lightbox="../media/javascript-sources-snippets-editor-unsaved.msft.png":::
       <span data-ttu-id="9025c-164">スニペット名の横にあるアスタリスクは、保存されていないコードを示します</span><span class="sxs-lookup"><span data-stu-id="9025c-164">An asterisk next to the Snippet name indicates unsaved code</span></span>  
    :::image-end:::  
    
## <a name="run-snippets"></a><span data-ttu-id="9025c-165">スニペットの実行</span><span class="sxs-lookup"><span data-stu-id="9025c-165">Run Snippets</span></span>  

### <a name="run-a-snippet-from-the-sources-tool"></a><span data-ttu-id="9025c-166">ソース ツールからスニペットを実行する</span><span class="sxs-lookup"><span data-stu-id="9025c-166">Run a Snippet from the Sources tool</span></span>  

1.  <span data-ttu-id="9025c-167">[[スニペット] タブを開きます](#open-the-snippets-tab)。</span><span class="sxs-lookup"><span data-stu-id="9025c-167">[Open the Snippets tab](#open-the-snippets-tab).</span></span>  
1.  <span data-ttu-id="9025c-168">実行するスニペットの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="9025c-168">Choose the name of the Snippet that you want to run.</span></span>  <span data-ttu-id="9025c-169">コード エディターでスニペット **が開きます**。</span><span class="sxs-lookup"><span data-stu-id="9025c-169">The Snippet opens in the **Code Editor**.</span></span>  
1.  <span data-ttu-id="9025c-170">[ **スニペットの実行** \( ![ Run Snippet ](../media/run-snippet-icon.msft.png) \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="9025c-170">Choose **Run snippet** \(![Run Snippet](../media/run-snippet-icon.msft.png)\).</span></span>
    
### <a name="run-a-snippet-with-the-command-menu"></a><span data-ttu-id="9025c-171">コマンド メニューを使用してスニペットを実行する</span><span class="sxs-lookup"><span data-stu-id="9025c-171">Run a Snippet with the Command Menu</span></span>  

1.  <span data-ttu-id="9025c-172">DevTools のどこかにカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="9025c-172">Focus your cursor somewhere in DevTools.</span></span>  
1.  <span data-ttu-id="9025c-173">`Control` + `Shift` + `P` コマンド メニューを開Windows \(Windows Linux\) または `Command` + `Shift` + `P` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="9025c-173">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu.</span></span>  
1.  <span data-ttu-id="9025c-174">文字を削除し、実行するスニペットの名前の後に文字 `>` `!` を入力します。</span><span class="sxs-lookup"><span data-stu-id="9025c-174">Delete the `>` character and type the `!` character followed by the name of the Snippet that you want to run.</span></span>  
    
    :::image type="complex" source="../media/javascript-search-run-command.msft.png" alt-text="コマンド メニューからスニペットを実行する" lightbox="../media/javascript-search-run-command.msft.png":::
       <span data-ttu-id="9025c-176">コマンド メニューからスニペット **を実行する**</span><span class="sxs-lookup"><span data-stu-id="9025c-176">Running a Snippet from the **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9025c-177">スニペット `Enter` を実行する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="9025c-177">Select `Enter` to run the Snippet.</span></span>  

## <a name="rename-snippets"></a><span data-ttu-id="9025c-178">スニペットの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="9025c-178">Rename Snippets</span></span>  

1.  <span data-ttu-id="9025c-179">[[スニペット] タブを開きます](#open-the-snippets-tab)。</span><span class="sxs-lookup"><span data-stu-id="9025c-179">[Open the Snippets tab](#open-the-snippets-tab).</span></span>  
1.  <span data-ttu-id="9025c-180">スニペット名をポイントし、コンテキスト メニュー \(右クリック\) を開き、[名前の変更] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="9025c-180">Hover on the Snippet name, open the contextual menu \(right-click\), and choose **Rename**.</span></span>  
    
## <a name="delete-snippets"></a><span data-ttu-id="9025c-181">スニペットの削除</span><span class="sxs-lookup"><span data-stu-id="9025c-181">Delete Snippets</span></span>  

1.  <span data-ttu-id="9025c-182">[[スニペット] タブを開きます](#open-the-snippets-tab)。</span><span class="sxs-lookup"><span data-stu-id="9025c-182">[Open the Snippets tab](#open-the-snippets-tab).</span></span>  
1.  <span data-ttu-id="9025c-183">スニペット名をポイントし、コンテキスト メニュー \(右クリック\) を開き、[削除] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="9025c-183">Hover on the Snippet name, open the contextual menu \(right-click\), and choose **Remove**.</span></span>  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="9025c-184">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="9025c-184">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleIndex]: ../console/index.md "コンソールの概要|Microsoft Docs"  
[DevToolsSourcesTool]: ../sources/index.md "ソース ツールの概要|Microsoft Docs"  
[DevtoolsJavascriptOverrides]: ./overrides.md "オーバーライド|Microsoft Docs"  

[MDNScratchpad]: https://developer.mozilla.org/docs/Tools/Scratchpad "Scratchpad |MDN"  
[WikiBookmarklet]: https://en.wikipedia.org/wiki/Bookmarklet "Bookmarklet |Wikipedia"  

> [!NOTE]
> <span data-ttu-id="9025c-190">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="9025c-190">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="9025c-191">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/snippets) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="9025c-191">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/snippets) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="9025c-193">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="9025c-193">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
