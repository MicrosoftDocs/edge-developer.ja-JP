---
description: Microsoft Edge DevTools のソースパネルで、ファイルの表示と編集、スニペットの作成、JavaScript の作成、ワークスペースのセットアップを行います。
title: ソース パネルの概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 971ee6e112daaba828a8b754b63eee73ea51e99e
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125329"
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

# <span data-ttu-id="8ea20-104">ソース パネルの概要</span><span class="sxs-lookup"><span data-stu-id="8ea20-104">Sources panel overview</span></span>  

<span data-ttu-id="8ea20-105">Microsoft Edge DevTools **ソース** パネルを使用して、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="8ea20-105">Use the Microsoft Edge DevTools **Sources** panel to perform the following actions.</span></span>  

*   <span data-ttu-id="8ea20-106">[ファイルを表示](#view-files)します。</span><span class="sxs-lookup"><span data-stu-id="8ea20-106">[View files](#view-files).</span></span>  
*   <span data-ttu-id="8ea20-107">[CSS と JavaScript を編集](#edit-css-and-javascript)します。</span><span class="sxs-lookup"><span data-stu-id="8ea20-107">[Edit CSS and JavaScript](#edit-css-and-javascript).</span></span>  
*   <span data-ttu-id="8ea20-108">[JavaScript の **スニペット** を作成して保存](#create-save-and-run-snippets)します。これは、どのページでも実行できます。</span><span class="sxs-lookup"><span data-stu-id="8ea20-108">[Create and save **Snippets** of JavaScript](#create-save-and-run-snippets), which you may run on any page.</span></span>  <span data-ttu-id="8ea20-109">**スニペット** は bookmarklets に似ています。</span><span class="sxs-lookup"><span data-stu-id="8ea20-109">**Snippets** are similar to bookmarklets.</span></span>  
*   <span data-ttu-id="8ea20-110">[JavaScript をデバッグ](#debug-javascript)します。</span><span class="sxs-lookup"><span data-stu-id="8ea20-110">[Debug JavaScript](#debug-javascript).</span></span>  
*   <span data-ttu-id="8ea20-111">[ワークスペースをセットアップ](#set-up-a-workspace)して、devtools で行った変更がファイルシステムのコードに保存されるようにします。</span><span class="sxs-lookup"><span data-stu-id="8ea20-111">[Set up a Workspace](#set-up-a-workspace), so that changes you make in DevTools get saved to the code on your file system.</span></span>  
    
## <span data-ttu-id="8ea20-112">ファイルの表示</span><span class="sxs-lookup"><span data-stu-id="8ea20-112">View files</span></span>  

<span data-ttu-id="8ea20-113">**ページ**ウィンドウを使用して、ページに読み込まれたすべてのリソースを表示します。</span><span class="sxs-lookup"><span data-stu-id="8ea20-113">Use the **Page** pane to view all of the resources that the page has loaded.</span></span>

:::image type="complex" source="./media/sources-page-pane.msft.png" alt-text="ページウィンドウ" lightbox="./media/sources-page-pane.msft.png":::
   <span data-ttu-id="8ea20-115">**ページ**ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="8ea20-115">The **Page** pane</span></span>  
:::image-end:::  

<span data-ttu-id="8ea20-116">**ページ**ウィンドウの構成:</span><span class="sxs-lookup"><span data-stu-id="8ea20-116">How the **Page** pane is organized:</span></span>  
*   <span data-ttu-id="8ea20-117">上の図のような最上位のレベルは、 `top` [HTML フレーム][W3CHtml4Frames]を表します。</span><span class="sxs-lookup"><span data-stu-id="8ea20-117">The top-level, such as `top` in the previous figure, represents an [HTML frame][W3CHtml4Frames].</span></span>  <span data-ttu-id="8ea20-118">`top`アクセスしたすべてのページで [検索] を選びます。</span><span class="sxs-lookup"><span data-stu-id="8ea20-118">Find `top` on every page that you visit.</span></span>  `top` <span data-ttu-id="8ea20-119">メイン文書のフレームを表します。</span><span class="sxs-lookup"><span data-stu-id="8ea20-119">represents the main document frame.</span></span>  
*   <span data-ttu-id="8ea20-120">上の図のように、第2レベルは `docs.microsoft.com` [起点][HtmlstandardOrigin]を表します。</span><span class="sxs-lookup"><span data-stu-id="8ea20-120">The second-level, such as `docs.microsoft.com` in the previous figure, represents an [origin][HtmlstandardOrigin].</span></span>  
*   <span data-ttu-id="8ea20-121">第3レベルの第4レベルは、その起点から読み込まれたディレクトリとリソースを表します。</span><span class="sxs-lookup"><span data-stu-id="8ea20-121">The third-level, fourth-level, and so on, represent directories and resources that were loaded from that origin.</span></span>  <span data-ttu-id="8ea20-122">たとえば、前の図では、リソースへの完全なパス `devtools-guide-chromium` は</span><span class="sxs-lookup"><span data-stu-id="8ea20-122">For example, in the previous figure the full path to the resource `devtools-guide-chromium` is</span></span> `docs.microsoft.com/en-us/microsoft-edge/devtools-guide-chromium`  
    
<span data-ttu-id="8ea20-123">**ページ**ウィンドウでファイルをクリックして、[**エディター** ] ウィンドウでコンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="8ea20-123">Click a file in the **Page** pane to view the contents in the **Editor** pane.</span></span>  <span data-ttu-id="8ea20-124">任意の種類のファイルを表示できます。</span><span class="sxs-lookup"><span data-stu-id="8ea20-124">You may view any type of file.</span></span>  <span data-ttu-id="8ea20-125">画像の場合、画像のプレビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8ea20-125">For images, a preview of the image is displayed.</span></span>  

:::image type="complex" source="./media/sources-editor-pane.msft.png" alt-text="ページウィンドウ" lightbox="./media/sources-editor-pane.msft.png":::
   <span data-ttu-id="8ea20-127">[ `a4d10f71.index-docs.js` **エディター** ] ウィンドウでのコンテンツの表示</span><span class="sxs-lookup"><span data-stu-id="8ea20-127">View the contents of `a4d10f71.index-docs.js` in the **Editor** pane</span></span>  
:::image-end:::  

## <span data-ttu-id="8ea20-128">CSS と JavaScript を編集する</span><span class="sxs-lookup"><span data-stu-id="8ea20-128">Edit CSS and JavaScript</span></span>  

<span data-ttu-id="8ea20-129">[ **エディター** ] ウィンドウを使って、CSS と JavaScript を編集します。</span><span class="sxs-lookup"><span data-stu-id="8ea20-129">Use the **Editor** pane to edit CSS and JavaScript.</span></span>  <span data-ttu-id="8ea20-130">DevTools はページを更新して、新しいコードを実行します。</span><span class="sxs-lookup"><span data-stu-id="8ea20-130">DevTools updates the page to run your new code.</span></span>  <span data-ttu-id="8ea20-131">たとえば、次のようなスタイルルールを追加して CSS ファイルを編集するとします。</span><span class="sxs-lookup"><span data-stu-id="8ea20-131">For example, if you edit a CSS file by adding the style rule below:</span></span>

```css
.metadata.page-metadata {
    color: red;
}
```

<span data-ttu-id="8ea20-132">この変更はすぐに有効になります。</span><span class="sxs-lookup"><span data-stu-id="8ea20-132">That change should take effect immediately.</span></span>

:::image type="complex" source="./media/edit-css.msft.png" alt-text="ページウィンドウ" lightbox="./media/edit-css.msft.png":::
   <span data-ttu-id="8ea20-134">[ **エディター** ] ウィンドウで [CSS の編集] を行うと、字幕のテキストの色が赤に変更されます。</span><span class="sxs-lookup"><span data-stu-id="8ea20-134">Edit CSS in the **Editor** pane to change the text color of the subtitle to red</span></span>  
:::image-end:::  

<span data-ttu-id="8ea20-135">CSS の変更は直ちに有効になります。保存する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8ea20-135">CSS changes take effect immediately, no save needed.</span></span>  <span data-ttu-id="8ea20-136">JavaScript の変更を有効にするに `Control` + `S` は、\ (Windows、Linux \) または `Command` + `S` \ (macOS \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ea20-136">For JavaScript changes to take effect, select `Control`+`S` \(Windows, Linux\) or `Command`+`S` \(macOS\).</span></span>  <span data-ttu-id="8ea20-137">DevTools ではスクリプトは再実行されないため、関数内で行うことができるのは JavaScript の変更のみです。</span><span class="sxs-lookup"><span data-stu-id="8ea20-137">DevTools does not re-run a script, so the only JavaScript changes that take effect are those that you make inside of functions.</span></span>  <span data-ttu-id="8ea20-138">たとえば、次の図では、"実行されない" という点に注意 `console.log('A')` `console.log('B')` してください。</span><span class="sxs-lookup"><span data-stu-id="8ea20-138">For example, in the following figure, notice how `console.log('A')` does not run, whereas `console.log('B')` does.</span></span>  <span data-ttu-id="8ea20-139">DevTools を変更した後でスクリプト全体を再実行すると、テキストは `A` **本体**に記録されます。</span><span class="sxs-lookup"><span data-stu-id="8ea20-139">If DevTools re-runs the entire script after making the change, then the text `A` would have been logged to the **Console**.</span></span>  

:::image type="complex" source="./media/edit-js.msft.png" alt-text="ページウィンドウ" lightbox="./media/edit-js.msft.png":::
   <span data-ttu-id="8ea20-141">[ **エディター** ] ウィンドウでの JavaScript の編集</span><span class="sxs-lookup"><span data-stu-id="8ea20-141">Editing JavaScript in the **Editor** pane</span></span>  
:::image-end:::  

<span data-ttu-id="8ea20-142">DevTools は、ページの読み込み時に CSS と JavaScript の変更を消去します。</span><span class="sxs-lookup"><span data-stu-id="8ea20-142">DevTools erases your CSS and JavaScript changes when you reload the page.</span></span>  <span data-ttu-id="8ea20-143">ファイルシステムへの変更を保存する方法については、「 [ワークスペースを設定](#set-up-a-workspace) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea20-143">Navigate to [Set up a Workspace](#set-up-a-workspace) to learn how to save the changes to your file system.</span></span>  

## <span data-ttu-id="8ea20-144">スニペットの作成、保存、および実行</span><span class="sxs-lookup"><span data-stu-id="8ea20-144">Create, save, and run Snippets</span></span>  

<span data-ttu-id="8ea20-145">スニペットは、任意のページで実行できるスクリプトです。</span><span class="sxs-lookup"><span data-stu-id="8ea20-145">Snippets are scripts which you may run on any page.</span></span>  <span data-ttu-id="8ea20-146">JQuery ライブラリをページに挿入するために、 **コンソール**に次のコードを繰り返し入力して、 **コンソール**から jquery コマンドを実行できるようにするとします。</span><span class="sxs-lookup"><span data-stu-id="8ea20-146">Imagine that you repeatedly type out the following code in the **Console**, in order to insert the jQuery library into a page, so that you may run jQuery commands from the **Console**:</span></span>  

```javascript
let script = document.createElement('script');
script.src = 'https://code.jquery.com/jquery-3.2.1.min.js';
script.crossOrigin = 'anonymous';
script.integrity = 'sha256-hwg4gsxgFZhOsEEamdOYGBf13FyQuiTwlAQgxVSNgt4=';
document.head.appendChild(script);
```  

<span data-ttu-id="8ea20-147">代わりに、このコードを **スニペット** として保存し、ボタンをクリックするだけで、必要に応じて実行することができます。</span><span class="sxs-lookup"><span data-stu-id="8ea20-147">Instead, you may save this code in a **Snippet** and run it with a couple of button clicks, any time you need it.</span></span>  <span data-ttu-id="8ea20-148">DevTools は、 **スニペット** をファイルシステムに保存します。</span><span class="sxs-lookup"><span data-stu-id="8ea20-148">DevTools saves the **Snippet** to your file system.</span></span>  

:::image type="complex" source="./media/snippet.msft.png" alt-text="ページウィンドウ" lightbox="./media/snippet.msft.png":::
   <span data-ttu-id="8ea20-150">JQuery ライブラリをページに挿入する**スニペット**</span><span class="sxs-lookup"><span data-stu-id="8ea20-150">A **Snippet** that inserts the jQuery library into a page</span></span>  
:::image-end:::  

<span data-ttu-id="8ea20-151">**スニペット**を実行するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8ea20-151">To run a **Snippet**:</span></span>

*   <span data-ttu-id="8ea20-152">[ **スニペット** ] ウィンドウを使ってファイルを開き、[ **実行** ] ([ ![ 実行] ボタン) を選び ][ImageRunIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="8ea20-152">Open the file using the **Snippets** pane, and choose **Run** \(![The Run button][ImageRunIcon]\).</span></span>  
*   <span data-ttu-id="8ea20-153">**[コマンドメニュー][DevtoolsGuideChromiumCommandMenuIndex]** を開き、文字を削除し、スニペットの名前を入力して、 `>` `!` を選択し**Snippet** `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="8ea20-153">Open the **[Command Menu][DevtoolsGuideChromiumCommandMenuIndex]**, delete the `>` character, type `!`, type the name of your **Snippet**, then select `Enter`.</span></span>  
    
<span data-ttu-id="8ea20-154">詳細については [、任意のページから「コードのスニペットを実行][DevtoolsGuideChromiumJavascriptSnippets] する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea20-154">Navigate to [Run Snippets Of Code From Any Page][DevtoolsGuideChromiumJavascriptSnippets] to learn more.</span></span>

## <span data-ttu-id="8ea20-155">デバッグ JavaScript</span><span class="sxs-lookup"><span data-stu-id="8ea20-155">Debug JavaScript</span></span>  

<span data-ttu-id="8ea20-156">JavaScript を使って問題が発生した場所を推測するのではなく `console.log()` 、Microsoft Edge devtools デバッグツールの使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="8ea20-156">Rather than using `console.log()` to infer where your JavaScript is going wrong, consider using the Microsoft Edge DevTools debugging tools, instead.</span></span>  <span data-ttu-id="8ea20-157">一般的な考え方として、ブレークポイントを設定します。これは、コードの中で意図的に停止しています。その後、コードの実行時に1行ずつ手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8ea20-157">The general idea is to set a breakpoint, which is an intentional stopping place in your code, and then step through the runtime of your code, one line at a time.</span></span>  <span data-ttu-id="8ea20-158">コードをステップ実行するときに、現在定義されているすべてのプロパティと変数の値の表示と変更、 **コンソール**での JavaScript の実行などを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="8ea20-158">As you step through the code, you may view and change the values of all currently-defined properties and variables, run JavaScript in the **Console**, and more.</span></span>

<span data-ttu-id="8ea20-159">「 [デバッグ JavaScript の概要][DevtoolsGuideChromiumJavascriptIndex] 」に移動して、devtools でのデバッグの基礎を学びましょう。</span><span class="sxs-lookup"><span data-stu-id="8ea20-159">Navigate to [Get Started With Debugging JavaScript][DevtoolsGuideChromiumJavascriptIndex] to learn the basics of debugging in DevTools.</span></span>

:::image type="complex" source="./media/debugging.msft.png" alt-text="ページウィンドウ" lightbox="./media/debugging.msft.png":::
   <span data-ttu-id="8ea20-161">デバッグ JavaScript</span><span class="sxs-lookup"><span data-stu-id="8ea20-161">Debug JavaScript</span></span>  
:::image-end:::  

## <span data-ttu-id="8ea20-162">ワークスペースを設定する</span><span class="sxs-lookup"><span data-stu-id="8ea20-162">Set up a Workspace</span></span>  

<span data-ttu-id="8ea20-163">既定では、[ **ソース** ] パネルでファイルを編集すると、ページを読み込むときにその変更が失われます。</span><span class="sxs-lookup"><span data-stu-id="8ea20-163">By default, when you edit a file in the **Sources** panel, those changes are lost when you reload the page.</span></span>  <span data-ttu-id="8ea20-164">**ワークスペース** を使用すると、devtools で行った変更をファイルシステムに保存することができます。</span><span class="sxs-lookup"><span data-stu-id="8ea20-164">**Workspaces** enable you to save the changes that you make in DevTools to your file system.</span></span>  <span data-ttu-id="8ea20-165">基本的に、DevTools はコードエディターとして使うことができます。</span><span class="sxs-lookup"><span data-stu-id="8ea20-165">Essentially, DevTools is able to be used as your code editor.</span></span>

<span data-ttu-id="8ea20-166">作業を開始するには、「 [ワークスペースでファイルを編集][DevtoolsGuideChromiumWorkspacesIndex] する」に移動します。</span><span class="sxs-lookup"><span data-stu-id="8ea20-166">Navigate to [Edit Files With Workspaces][DevtoolsGuideChromiumWorkspacesIndex] to get started.</span></span>

## <span data-ttu-id="8ea20-167">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="8ea20-167">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](./includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageRunIcon]: ./media/run-snippet-icon.msft.png  

<!-- links -->  

[DevtoolsGuideChromiumCommandMenuIndex]: ./command-menu/index.md "Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する"  
[DevtoolsGuideChromiumJavascriptIndex]: ./javascript/index.md "Microsoft Edge DevTools のデバッグ JavaScript の概要"  
[DevtoolsGuideChromiumJavascriptSnippets]: ./javascript/snippets.md "Microsoft Edge DevTools を使用して、任意のページで JavaScript のスニペットを実行します。"  
[DevtoolsGuideChromiumWorkspacesIndex]: ./workspaces/index.md "ワークスペースを使用してファイルを編集する"  

[HtmlstandardOrigin]: https://html.spec.whatwg.org/multipage/origin.html#origin "オリジン-HTML 標準"  

[W3CHtml4Frames]: https://w3.org/TR/html401/present/frames.html "フレーム |勧告"  

> [!NOTE]
> <span data-ttu-id="8ea20-174">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="8ea20-174">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="8ea20-175">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/sources) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="8ea20-175">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/sources) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="8ea20-177">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="8ea20-177">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
