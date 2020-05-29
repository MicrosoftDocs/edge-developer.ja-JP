---
title: ソースパネルの概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: c61d1bda030ce729b0b217b95a9143508d1f51f8
ms.sourcegitcommit: 5cdc1626d5581b79c0f2ac4ea62e7f1974ebfa57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "10601909"
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
   limitations under the License. -->






# <span data-ttu-id="9c279-103">ソースパネルの概要</span><span class="sxs-lookup"><span data-stu-id="9c279-103">Sources Panel Overview</span></span> 



<span data-ttu-id="9c279-104">Microsoft Edge DevTools**ソース**パネルを使用して、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9c279-104">Use the Microsoft Edge DevTools **Sources** panel to:</span></span>

*   <span data-ttu-id="9c279-105">[ファイルを表示](#view-files)します。</span><span class="sxs-lookup"><span data-stu-id="9c279-105">[View files](#view-files).</span></span>  
*   <span data-ttu-id="9c279-106">[CSS と JavaScript を編集](#edit-css-and-javascript)します。</span><span class="sxs-lookup"><span data-stu-id="9c279-106">[Edit CSS and JavaScript](#edit-css-and-javascript).</span></span>  
*   <span data-ttu-id="9c279-107">[JavaScript の**スニペット**を作成して保存](#create-save-and-run-snippets)します。これは、どのページでも実行できます。</span><span class="sxs-lookup"><span data-stu-id="9c279-107">[Create and save **Snippets** of JavaScript](#create-save-and-run-snippets), which you may run on any page.</span></span>  <span data-ttu-id="9c279-108">**スニペット**は bookmarklets に似ています。</span><span class="sxs-lookup"><span data-stu-id="9c279-108">**Snippets** are similar to bookmarklets.</span></span>  
*   <span data-ttu-id="9c279-109">[JavaScript をデバッグ](#debug-javascript)します。</span><span class="sxs-lookup"><span data-stu-id="9c279-109">[Debug JavaScript](#debug-javascript).</span></span>  
*   <span data-ttu-id="9c279-110">[ワークスペースをセットアップ](#set-up-a-workspace)して、devtools で行った変更がファイルシステムのコードに保存されるようにします。</span><span class="sxs-lookup"><span data-stu-id="9c279-110">[Set up a Workspace](#set-up-a-workspace), so that changes you make in DevTools get saved to the code on your file system.</span></span>  

## <span data-ttu-id="9c279-111">ファイルの表示</span><span class="sxs-lookup"><span data-stu-id="9c279-111">View files</span></span> 

<span data-ttu-id="9c279-112">**ページ**ウィンドウを使用して、ページに読み込まれたすべてのリソースを表示します。</span><span class="sxs-lookup"><span data-stu-id="9c279-112">Use the **Page** pane to view all of the resources that the page has loaded.</span></span>

> ##### <span data-ttu-id="9c279-113">図 1</span><span class="sxs-lookup"><span data-stu-id="9c279-113">Figure 1</span></span>  
> <span data-ttu-id="9c279-114">**ページ**ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="9c279-114">The **Page** pane</span></span>  
> ![図 1: ページウィンドウ][ImageSourcesPagePane]  

<span data-ttu-id="9c279-116">**ページ**ウィンドウの構成:</span><span class="sxs-lookup"><span data-stu-id="9c279-116">How the **Page** pane is organized:</span></span>  
*   <span data-ttu-id="9c279-117">図1のような最上位レベルは、 `top` [HTML フレーム][W3CHtml4Frames]を[**Figure 1**](#figure-1)表します。</span><span class="sxs-lookup"><span data-stu-id="9c279-117">The top-level, such as `top` in [**Figure 1**](#figure-1), represents an [HTML frame][W3CHtml4Frames].</span></span>  <span data-ttu-id="9c279-118">`top`アクセスしたすべてのページで [検索] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9c279-118">Find `top` on every page that you visit.</span></span> `top` <span data-ttu-id="9c279-119">メイン文書のフレームを表します。</span><span class="sxs-lookup"><span data-stu-id="9c279-119">represents the main document frame.</span></span>  
*   <span data-ttu-id="9c279-120">第2レベルは、 `docs.microsoft.com` [**図 1**](#figure-1)のように、[原点][HtmlstandardOrigin]を表します。</span><span class="sxs-lookup"><span data-stu-id="9c279-120">The second-level, such as `docs.microsoft.com` in [**Figure 1**](#figure-1), represents an [origin][HtmlstandardOrigin].</span></span>  
*   <span data-ttu-id="9c279-121">第3レベルの第4レベルは、その起点から読み込まれたディレクトリとリソースを表します。</span><span class="sxs-lookup"><span data-stu-id="9c279-121">The third-level, fourth-level, and so on, represent directories and resources that were loaded from that origin.</span></span>  <span data-ttu-id="9c279-122">たとえば、[**図 1**](#figure-1)では、次のようにリソースの完全なパス `devtools-guide-chromium` があります。</span><span class="sxs-lookup"><span data-stu-id="9c279-122">For example, in [**Figure 1**](#figure-1) the full path to the resource `devtools-guide-chromium` is</span></span> `docs.microsoft.com/en-us/microsoft-edge/devtools-guide-chromium`  

<span data-ttu-id="9c279-123">**ページ**ウィンドウでファイルをクリックして、[**エディター** ] ウィンドウでコンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="9c279-123">Click a file in the **Page** pane to view the contents in the **Editor** pane.</span></span>  <span data-ttu-id="9c279-124">任意の種類のファイルを表示できます。</span><span class="sxs-lookup"><span data-stu-id="9c279-124">You may view any type of file.</span></span> <span data-ttu-id="9c279-125">画像の場合、画像のプレビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c279-125">For images, you see a preview of the image.</span></span>  

> ##### <span data-ttu-id="9c279-126">図 2</span><span class="sxs-lookup"><span data-stu-id="9c279-126">Figure 2</span></span>  
> <span data-ttu-id="9c279-127">[ `a4d10f71.index-docs.js` **エディター** ] ウィンドウでのコンテンツの表示</span><span class="sxs-lookup"><span data-stu-id="9c279-127">Viewing the contents of `a4d10f71.index-docs.js` in the **Editor** pane</span></span>  
> ![図 2. ][ImageSourcesEditorPane]  

## <span data-ttu-id="9c279-130">CSS と JavaScript を編集する</span><span class="sxs-lookup"><span data-stu-id="9c279-130">Edit CSS and JavaScript</span></span> 

<span data-ttu-id="9c279-131">[**エディター** ] ウィンドウを使って、CSS と JavaScript を編集します。</span><span class="sxs-lookup"><span data-stu-id="9c279-131">Use the **Editor** pane to edit CSS and JavaScript.</span></span>  <span data-ttu-id="9c279-132">DevTools はページを更新して、新しいコードを実行します。</span><span class="sxs-lookup"><span data-stu-id="9c279-132">DevTools updates the page to run your new code.</span></span> <span data-ttu-id="9c279-133">たとえば、次のようなスタイルルールを追加して CSS ファイルを編集するとします。</span><span class="sxs-lookup"><span data-stu-id="9c279-133">For example, if you edit a CSS file by adding the style rule below:</span></span>

```css
.metadata.page-metadata {
    color: red;
}
```

<span data-ttu-id="9c279-134">変更がすぐに反映されることがわかります。</span><span class="sxs-lookup"><span data-stu-id="9c279-134">You should see that change take effect immediately.</span></span>

> ##### <span data-ttu-id="9c279-135">図 3</span><span class="sxs-lookup"><span data-stu-id="9c279-135">Figure 3</span></span>  
> <span data-ttu-id="9c279-136">[**エディター** ] ウィンドウで CSS を編集して、字幕のテキストの色を赤に変更する</span><span class="sxs-lookup"><span data-stu-id="9c279-136">Editing CSS in the **Editor** pane to change the text color of the subtitle to red</span></span>  
> ![図 3. ][ImageEditCSS]  

<span data-ttu-id="9c279-139">CSS の変更は直ちに有効になります。保存する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9c279-139">CSS changes take effect immediately, no save needed.</span></span> <span data-ttu-id="9c279-140">JavaScript の変更を有効にするに `Control` + `S` は、\ (Windows \) または `Command` + `S` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="9c279-140">For JavaScript changes to take effect, press `Control`+`S` \(Windows\) or `Command`+`S` \(macOS\).</span></span> <span data-ttu-id="9c279-141">DevTools ではスクリプトは再実行されないため、関数内で行うことができるのは JavaScript の変更のみです。</span><span class="sxs-lookup"><span data-stu-id="9c279-141">DevTools does not re-run a script, so the only JavaScript changes that take effect are those that you make inside of functions.</span></span>  <span data-ttu-id="9c279-142">たとえば、[**図 4**](#figure-4)では、次のように動作しないことを確認し `console.log('A')` `console.log('B')` ます。</span><span class="sxs-lookup"><span data-stu-id="9c279-142">For example, in [**Figure 4**](#figure-4) note how `console.log('A')` does not run, whereas `console.log('B')` does.</span></span> <span data-ttu-id="9c279-143">DevTools で変更を行った後でスクリプト全体を再実行すると、テキストは `A` **本体**に記録されます。</span><span class="sxs-lookup"><span data-stu-id="9c279-143">If DevTools re-ran the entire script after making the change, then the text `A` would have been logged to the **Console**.</span></span>  

> ##### <span data-ttu-id="9c279-144">図 4</span><span class="sxs-lookup"><span data-stu-id="9c279-144">Figure 4</span></span>  
> <span data-ttu-id="9c279-145">[**エディター** ] ウィンドウでの JavaScript の編集</span><span class="sxs-lookup"><span data-stu-id="9c279-145">Editing JavaScript in the **Editor** pane</span></span>  
> ![図 4: ][ImageEditJS]  

<span data-ttu-id="9c279-148">DevTools は、ページの読み込み時に CSS と JavaScript の変更を消去します。</span><span class="sxs-lookup"><span data-stu-id="9c279-148">DevTools erases your CSS and JavaScript changes when you reload the page.</span></span> <span data-ttu-id="9c279-149">ファイルシステムへの変更を保存する方法については、「[ワークスペースを設定](#set-up-a-workspace)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c279-149">See [Set up a Workspace](#set-up-a-workspace) to learn how to save the changes to your file system.</span></span>  

## <span data-ttu-id="9c279-150">スニペットの作成、保存、および実行</span><span class="sxs-lookup"><span data-stu-id="9c279-150">Create, save, and run Snippets</span></span> 

<span data-ttu-id="9c279-151">スニペットは、任意のページで実行できるスクリプトです。</span><span class="sxs-lookup"><span data-stu-id="9c279-151">Snippets are scripts which you may run on any page.</span></span> <span data-ttu-id="9c279-152">JQuery ライブラリをページに挿入するために、**コンソール**に次のコードを繰り返し入力して、**コンソール**から jquery コマンドを実行できるようにするとします。</span><span class="sxs-lookup"><span data-stu-id="9c279-152">Imagine that you repeatedly type out the following code in the **Console**, in order to insert the jQuery library into a page, so that you may run jQuery commands from the **Console**:</span></span>  

```javascript
let script = document.createElement('script');
script.src = 'https://code.jquery.com/jquery-3.2.1.min.js';
script.crossOrigin = 'anonymous';
script.integrity = 'sha256-hwg4gsxgFZhOsEEamdOYGBf13FyQuiTwlAQgxVSNgt4=';
document.head.appendChild(script);
```  

<span data-ttu-id="9c279-153">代わりに、このコードを**スニペット**として保存し、ボタンをクリックするだけで、必要に応じて実行することができます。</span><span class="sxs-lookup"><span data-stu-id="9c279-153">Instead, you may save this code in a **Snippet** and run it with a couple of button clicks, any time you need it.</span></span>  <span data-ttu-id="9c279-154">DevTools は、**スニペット**をファイルシステムに保存します。</span><span class="sxs-lookup"><span data-stu-id="9c279-154">DevTools saves the **Snippet** to your file system.</span></span>  

> ##### <span data-ttu-id="9c279-155">図 5</span><span class="sxs-lookup"><span data-stu-id="9c279-155">Figure 5</span></span>  
> <span data-ttu-id="9c279-156">JQuery ライブラリをページに挿入する**スニペット**</span><span class="sxs-lookup"><span data-stu-id="9c279-156">A **Snippet** that inserts the jQuery library into a page</span></span>  
> ![図 5: ][ImageSnippet]  

<span data-ttu-id="9c279-159">**スニペット**を実行するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9c279-159">To run a **Snippet**:</span></span>

*   <span data-ttu-id="9c279-160">[**スニペット**] ウィンドウでファイルを開き **、[** ![ 実行] ボタンをクリックし ][ImageRunIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="9c279-160">Open the file via the **Snippets** pane, and click **Run** ![The Run button][ImageRunIcon].</span></span>  
*   <span data-ttu-id="9c279-161">**[コマンドメニュー][DevtoolsGuideChromiumCommandMenuIndex]** を開き、文字を削除して、スニペットの名前を入力し、 `>` `!` enter キーを押し**Snippet** `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="9c279-161">Open the **[Command Menu][DevtoolsGuideChromiumCommandMenuIndex]**, delete the `>` character, type `!`, type the name of your **Snippet**, then press `Enter`.</span></span>  

<span data-ttu-id="9c279-162">詳細については[、「任意のページからコードのスニペットを実行][DevtoolsGuideChromiumJavascriptSnippets]する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c279-162">See [Run Snippets Of Code From Any Page][DevtoolsGuideChromiumJavascriptSnippets] to learn more.</span></span>


## <span data-ttu-id="9c279-163">デバッグ JavaScript</span><span class="sxs-lookup"><span data-stu-id="9c279-163">Debug JavaScript</span></span> 

<span data-ttu-id="9c279-164">JavaScript を使って問題が発生した場所を推測するのではなく `console.log()` 、Microsoft Edge devtools デバッグツールの使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="9c279-164">Rather than using `console.log()` to infer where your JavaScript is going wrong, consider using the Microsoft Edge DevTools debugging tools, instead.</span></span> <span data-ttu-id="9c279-165">一般的な考え方として、ブレークポイントを設定します。これは、コードの中で意図的に停止しています。その後、コードの実行時に1行ずつ手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9c279-165">The general idea is to set a breakpoint, which is an intentional stopping place in your code, and then step through the runtime of your code, one line at a time.</span></span> <span data-ttu-id="9c279-166">コードをステップ実行するときに、現在定義されているすべてのプロパティと変数の値の表示と変更、**コンソール**での JavaScript の実行などを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9c279-166">As you step through the code, you may view and change the values of all currently-defined properties and variables, run JavaScript in the **Console**, and more.</span></span>

<span data-ttu-id="9c279-167">「[デバッグ JavaScript の概要][DevtoolsGuideChromiumJavascriptIndex]」を参照して、devtools でのデバッグの基礎を学習してください。</span><span class="sxs-lookup"><span data-stu-id="9c279-167">See [Get Started With Debugging JavaScript][DevtoolsGuideChromiumJavascriptIndex] to learn the basics of debugging in DevTools.</span></span>

> ##### <span data-ttu-id="9c279-168">図 6</span><span class="sxs-lookup"><span data-stu-id="9c279-168">Figure 6</span></span>  
> <span data-ttu-id="9c279-169">JavaScript のデバッグ</span><span class="sxs-lookup"><span data-stu-id="9c279-169">Debugging JavaScript</span></span>  
> ![図 6. ][ImageDebugging]  

## <span data-ttu-id="9c279-172">ワークスペースを設定する</span><span class="sxs-lookup"><span data-stu-id="9c279-172">Set up a Workspace</span></span> 

<span data-ttu-id="9c279-173">既定では、[**ソース**] パネルでファイルを編集すると、ページを読み込むときにその変更が失われます。</span><span class="sxs-lookup"><span data-stu-id="9c279-173">By default, when you edit a file in the **Sources** panel, those changes are lost when you reload the page.</span></span>  <span data-ttu-id="9c279-174">**ワークスペース**を使用すると、devtools で行った変更をファイルシステムに保存することができます。</span><span class="sxs-lookup"><span data-stu-id="9c279-174">**Workspaces** enable you to save the changes that you make in DevTools to your file system.</span></span>  <span data-ttu-id="9c279-175">これにより、基本的に、コードエディターとして DevTools を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="9c279-175">Essentially, this lets you use DevTools as your code editor.</span></span>

<span data-ttu-id="9c279-176">始めるには、「[ワークスペースでファイルを編集][DevtoolsGuideChromiumWorkspacesIndex]する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c279-176">See [Edit Files With Workspaces][DevtoolsGuideChromiumWorkspacesIndex] to get started.</span></span>

 



<!-- image links -->  

[ImageRunIcon]: /microsoft-edge/devtools-guide-chromium/media/run-snippet-icon.msft.png  

[ImageSourcesPagePane]: /microsoft-edge/devtools-guide-chromium/media/sources-page-pane.msft.png "図 1: ページウィンドウ"  
[ImageSourcesEditorPane]: /microsoft-edge/devtools-guide-chromium/media/sources-editor-pane.msft.png "図 2: a4d10f71 の内容をエディターウィンドウで表示する"  
[ImageEditCSS]: /microsoft-edge/devtools-guide-chromium/media/edit-css.msft.png "図 3: [エディター] ウィンドウで CSS を編集して、字幕のテキストの色を赤に変更する"  
[ImageEditJS]: /microsoft-edge/devtools-guide-chromium/media/edit-js.msft.png "図 4: [エディター] ウィンドウで JavaScript を編集する"  
[ImageSnippet]: /microsoft-edge/devtools-guide-chromium/media/snippet.msft.png "図 5: jQuery ライブラリをページに挿入するスニペット"  
[ImageDebugging]: /microsoft-edge/devtools-guide-chromium/media/debugging.msft.png "図 6: JavaScript のデバッグ"  

<!-- links -->  

[DevtoolsGuideChromiumCommandMenuIndex]: /microsoft-edge/devtools-guide-chromium/command-menu/index "Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する"  
[DevtoolsGuideChromiumJavascriptIndex]: /microsoft-edge/devtools-guide-chromium/javascript/index "Microsoft Edge DevTools のデバッグ JavaScript の概要"  
[DevtoolsGuideChromiumJavascriptSnippets]: /microsoft-edge/devtools-guide-chromium/javascript/snippets "Microsoft Edge DevTools を使用して、任意のページで JavaScript のスニペットを実行します。"  
[DevtoolsGuideChromiumWorkspacesIndex]: /microsoft-edge/devtools-guide-chromium/workspaces/index "ワークスペースを使用してファイルを編集する"  

[HtmlstandardOrigin]: https://html.spec.whatwg.org/multipage/origin.html#origin "オリジン-HTML 標準"  

[W3CHtml4Frames]: https://w3.org/TR/html401/present/frames.html "フレーム |勧告"  

> [!NOTE]
> <span data-ttu-id="9c279-189">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="9c279-189">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="9c279-190">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/sources)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="9c279-190">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/sources) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="9c279-192">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="9c279-192">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
