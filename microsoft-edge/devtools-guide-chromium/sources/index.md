---
description: ファイルの表示と編集、スニペットの作成、JavaScript のデバッグ、Microsoft Edge DevTools の [ソース] パネルでのワークスペースの設定。
title: ソース パネルの概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 開発, f12 ツール, devtools
ms.openlocfilehash: 4677bf82d3506a4b8d6336ded7ab557b794fd3df
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397763"
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

# <a name="sources-panel-overview"></a><span data-ttu-id="6c9bc-104">ソース パネルの概要</span><span class="sxs-lookup"><span data-stu-id="6c9bc-104">Sources panel overview</span></span>  

<span data-ttu-id="6c9bc-105">Microsoft Edge DevTools **ソース** パネルを使用して、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-105">Use the Microsoft Edge DevTools **Sources** panel to perform the following actions.</span></span>  

*   <span data-ttu-id="6c9bc-106">[ファイルを表示します](#display-files)。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-106">[Display files](#display-files).</span></span>  
*   <span data-ttu-id="6c9bc-107">[CSS と JavaScript を編集](#edit-css-and-javascript)。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-107">[Edit CSS and JavaScript](#edit-css-and-javascript).</span></span>  
*   <span data-ttu-id="6c9bc-108">[任意の Web **ページで** 実行できる JavaScript](#create-save-and-run-snippets)のスニペットを作成して保存します。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-108">[Create and save **Snippets** of JavaScript](#create-save-and-run-snippets), which you may run on any webpage.</span></span>  <span data-ttu-id="6c9bc-109">**スニペット** は bookmarklets に似ています。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-109">**Snippets** are similar to bookmarklets.</span></span>  
*   <span data-ttu-id="6c9bc-110">[JavaScript をデバッグ](#debug-javascript)。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-110">[Debug JavaScript](#debug-javascript).</span></span>  
*   <span data-ttu-id="6c9bc-111">[ワークスペースをセット アップ](#set-up-a-workspace)して、DevTools で行った変更がファイル システムのコードに保存されるようにします。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-111">[Set up a Workspace](#set-up-a-workspace), so that changes you make in DevTools get saved to the code on your file system.</span></span>  
    
## <a name="display-files"></a><span data-ttu-id="6c9bc-112">ファイルの表示</span><span class="sxs-lookup"><span data-stu-id="6c9bc-112">Display files</span></span>  

<span data-ttu-id="6c9bc-113">[ページ] **パネルを使用** します。をクリックして、ページが読み込まれたすべてのリソースを表示します。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-113">Use the **Page** panel; to display all of the resources that the page has loaded.</span></span>

:::image type="complex" source="../media/sources-page-pane.msft.png" alt-text="[ページ] パネル" lightbox="../media/sources-page-pane.msft.png":::
   <span data-ttu-id="6c9bc-115">[ **ページ]** パネル</span><span class="sxs-lookup"><span data-stu-id="6c9bc-115">The **Page** panel</span></span>  
:::image-end:::  

<span data-ttu-id="6c9bc-116">**ページ**ウィンドウの構成:</span><span class="sxs-lookup"><span data-stu-id="6c9bc-116">How the **Page** pane is organized:</span></span>  
*   <span data-ttu-id="6c9bc-117">`top`上の図のような最上位のレベルは、[HTML フレーム][W3CHtml4Frames]を表します。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-117">The top-level, such as `top` in the previous figure, represents an [HTML frame][W3CHtml4Frames].</span></span>  <span data-ttu-id="6c9bc-118">`top`アクセスしたすべてのページで [検索]します。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-118">Find `top` on every page that you visit.</span></span>  `top` <span data-ttu-id="6c9bc-119">メイン文書のフレームを表します。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-119">represents the main document frame.</span></span>  
*   <span data-ttu-id="6c9bc-120">`docs.microsoft.com`上の図のように、第 2 レベルは [起点][HtmlstandardOrigin]を表します。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-120">The second-level, such as `docs.microsoft.com` in the previous figure, represents an [origin][HtmlstandardOrigin].</span></span>  
*   <span data-ttu-id="6c9bc-121">第 3 レベル、第 4 レベルとそれ以降は、その起点から読み込まれたディレクトリとリソースを表します。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-121">The third-level, fourth-level, and so on, represent directories and resources that were loaded from that origin.</span></span>  <span data-ttu-id="6c9bc-122">たとえば、前の図では、リソースへの完全なパス `devtools-guide-chromium` は</span><span class="sxs-lookup"><span data-stu-id="6c9bc-122">For example, in the previous figure the full path to the resource `devtools-guide-chromium` is</span></span> `docs.microsoft.com/en-us/microsoft-edge/devtools-guide-chromium`  
    
<span data-ttu-id="6c9bc-123">[ページ] パネルでファイル **を選択** して、[エディター] ウィンドウにコンテンツ **を表示** します。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-123">Choose a file in the **Page** panel to display the contents in the **Editor** pane.</span></span>  <span data-ttu-id="6c9bc-124">任意の種類のファイルを表示できます。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-124">You may display any type of file.</span></span>  <span data-ttu-id="6c9bc-125">画像の場合、画像のプレビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-125">For images, a preview of the image is displayed.</span></span>  

:::image type="complex" source="../media/sources-editor-pane.msft.png" alt-text="[エディター] ウィンドウにa4d10f71.index-docs.jsの内容を表示する" lightbox="../media/sources-editor-pane.msft.png":::
   <span data-ttu-id="6c9bc-127">エディター パネルに内容 `a4d10f71.index-docs.js` を **表示** する</span><span class="sxs-lookup"><span data-stu-id="6c9bc-127">Display the contents of `a4d10f71.index-docs.js` in the **Editor** panel</span></span>  
:::image-end:::  

## <a name="edit-css-and-javascript"></a><span data-ttu-id="6c9bc-128">CSS と JavaScript を編集する</span><span class="sxs-lookup"><span data-stu-id="6c9bc-128">Edit CSS and JavaScript</span></span>  

<span data-ttu-id="6c9bc-129">[ **エディター** ] ウィンドウを使って、CSS と JavaScript を編集します。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-129">Use the **Editor** pane to edit CSS and JavaScript.</span></span>  <span data-ttu-id="6c9bc-130">DevTools はページを更新して、新しいコードを実行します。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-130">DevTools updates the page to run your new code.</span></span>  <span data-ttu-id="6c9bc-131">たとえば、次のようなスタイル ルールを追加して CSS ファイルを編集するとします。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-131">For example, if you edit a CSS file by adding the style rule below:</span></span>

```css
.metadata.page-metadata {
    color: red;
}
```

<span data-ttu-id="6c9bc-132">この変更はすぐに有効になります。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-132">That change should take effect immediately.</span></span>

:::image type="complex" source="../media/edit-css.msft.png" alt-text="[エディター] ウィンドウでCSS の編集を行うと、字幕のテキストの色が赤に変更されます。" lightbox="../media/edit-css.msft.png":::
   <span data-ttu-id="6c9bc-134">[ **エディター** ] ウィンドウで [CSS の編集] を行うと、字幕のテキストの色が赤に変更されます。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-134">Edit CSS in the **Editor** pane to change the text color of the subtitle to red</span></span>  
:::image-end:::  

<span data-ttu-id="6c9bc-135">CSS の変更は直ちに有効になります。保存する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-135">CSS changes take effect immediately, no save needed.</span></span>  <span data-ttu-id="6c9bc-136">JavaScript の変更を有効にするには`Control`+`S` [\(Windows, Linux\)] または`Command`+`S` [\(macOS\)] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-136">For JavaScript changes to take effect, select `Control`+`S` \(Windows, Linux\) or `Command`+`S` \(macOS\).</span></span>  <span data-ttu-id="6c9bc-137">DevTools ではスクリプトは再実行されないため、 JavaScript の変更で有効にできるのは、関数内で行う変更のみです。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-137">DevTools does not re-run a script, so the only JavaScript changes that take effect are those that you make inside of functions.</span></span>  <span data-ttu-id="6c9bc-138">たとえば、次の図でどのような場合に `console.log('A')`実行されないか、それに対して `console.log('B')` 実行されるかに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-138">For example, in the following figure, notice how `console.log('A')` does not run, whereas `console.log('B')` does.</span></span>  <span data-ttu-id="6c9bc-139">DevTools が変更後にスクリプト全体を再び実行すると、テキストは `A` コンソールに記録 **されます**。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-139">If DevTools re-runs the entire script after making the change, then the text `A` is logged to the **Console**.</span></span>  

:::image type="complex" source="../media/edit-js.msft.png" alt-text="[エディター] ウィンドウでの JavaScript の編集" lightbox="../media/edit-js.msft.png":::
   <span data-ttu-id="6c9bc-141">エディター パネルでの JavaScript **の** 編集</span><span class="sxs-lookup"><span data-stu-id="6c9bc-141">Editing JavaScript in the **Editor** panel</span></span>  
:::image-end:::  

<span data-ttu-id="6c9bc-142">ページを更新すると、DevTools は CSS と JavaScript の変更を消去します。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-142">DevTools erases your CSS and JavaScript changes when you refresh the page.</span></span>  <span data-ttu-id="6c9bc-143">ファイル システムへの変更を保存する方法については、「 [ワークスペースのセット アップ](#set-up-a-workspace)」へ移動して参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-143">Navigate to [Set up a Workspace](#set-up-a-workspace) to learn how to save the changes to your file system.</span></span>  

## <a name="create-save-and-run-snippets"></a><span data-ttu-id="6c9bc-144">スニペットの作成、保存、および実行</span><span class="sxs-lookup"><span data-stu-id="6c9bc-144">Create, save, and run Snippets</span></span>  

<span data-ttu-id="6c9bc-145">スニペットは、任意のページで実行できるスクリプトです。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-145">Snippets are scripts which you may run on any page.</span></span>  <span data-ttu-id="6c9bc-146">jQuery ライブラリをページに挿入するために、コンソールで\*\*\*\* 次のコードを繰り返し入力して、コンソールから jQuery コマンドを実行できると**します**。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-146">Imagine that you repeatedly type out the following code in the **Console**, in order to insert the jQuery library into a page, so that you may run jQuery commands from the **Console**.</span></span>  

```javascript
let script = document.createElement('script');
script.src = 'https://code.jquery.com/jquery-3.2.1.min.js';
script.crossOrigin = 'anonymous';
script.integrity = 'sha256-hwg4gsxgFZhOsEEamdOYGBf13FyQuiTwlAQgxVSNgt4=';
document.head.appendChild(script);
```  

<span data-ttu-id="6c9bc-147">代わりに、このコードを **スニペット** として保存すれば、ボタンを 1、2 回クリックするだけで、必要に応じて実行することができます。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-147">Instead, you may save this code in a **Snippet** and run it with a couple of button clicks, any time you need it.</span></span>  <span data-ttu-id="6c9bc-148">DevTools は、 **スニペット** をファイル システムに保存します。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-148">DevTools saves the **Snippet** to your file system.</span></span>  

:::image type="complex" source="../media/snippet.msft.png" alt-text="JQuery ライブラリをページに挿入するスニペット" lightbox="../media/snippet.msft.png":::
   <span data-ttu-id="6c9bc-150">JQuery ライブラリをページに挿入する**スニペット**</span><span class="sxs-lookup"><span data-stu-id="6c9bc-150">A **Snippet** that inserts the jQuery library into a page</span></span>  
:::image-end:::  

<span data-ttu-id="6c9bc-151">**スニペット**を実行するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-151">To run a **Snippet**:</span></span>

*   <span data-ttu-id="6c9bc-152">[スニペット] パネルを使用 **してファイルを開** き、[ **実行** ] \( [実行] ![ ボタン ][ImageRunIcon] \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-152">Open the file using the **Snippets** panel, and choose **Run** \(![The Run button][ImageRunIcon]\).</span></span>  
*   <span data-ttu-id="6c9bc-153">コマンド メニュー [を開き、][DevtoolsGuideChromiumCommandMenuIndex]文字を削除 `>` し、タイプし、スニペットの名前を `!` **入力**して、 を選択します `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-153">Open the [Command Menu][DevtoolsGuideChromiumCommandMenuIndex], delete the `>` character, type `!`, type the name of your **Snippet**, and then select `Enter`.</span></span>  
    
<span data-ttu-id="6c9bc-154">詳細については「[任意のページからコードのスニペットを実行][DevtoolsGuideChromiumJavascriptSnippets]」へ移動して参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-154">Navigate to [Run Snippets Of Code From Any Page][DevtoolsGuideChromiumJavascriptSnippets] to learn more.</span></span>

## <a name="debug-javascript"></a><span data-ttu-id="6c9bc-155">JavaScript のデバッグ </span><span class="sxs-lookup"><span data-stu-id="6c9bc-155">Debug JavaScript</span></span>  

<span data-ttu-id="6c9bc-156">`console.log()` を使って JavaScript に問題が発生した場所を推測するのではなく、Microsoft Edge DevTools デバッグ ツールの使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-156">Rather than using `console.log()` to infer where your JavaScript is going wrong, consider using the Microsoft Edge DevTools debugging tools, instead.</span></span>  <span data-ttu-id="6c9bc-157">一般的な考え方として、ブレーク ポイントを設定します。これは、コードの中で意図的に停止する場所です。その後、コードの実行時に 1 行ずつ手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-157">The general idea is to set a breakpoint, which is an intentional stopping place in your code, and then step through the runtime of your code, one line at a time.</span></span>  <span data-ttu-id="6c9bc-158">コードをステップ実行すると、現在定義されているプロパティと変数の値を表示および変更し、コンソールで JavaScript **を実行**できます。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-158">As you step through the code, you may display and change the values of all currently-defined properties and variables, run JavaScript in the **Console**, and more.</span></span>

<span data-ttu-id="6c9bc-159">「[JavaScript のデバッグの概要][DevtoolsGuideChromiumJavascriptIndex]」に移動して、DevTools でのデバッグの基礎を学びます。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-159">Navigate to [Get Started With Debugging JavaScript][DevtoolsGuideChromiumJavascriptIndex] to learn the basics of debugging in DevTools.</span></span>

:::image type="complex" source="../media/debugging.msft.png" alt-text="JavaScript のデバッグ " lightbox="../media/debugging.msft.png":::
   <span data-ttu-id="6c9bc-161">JavaScript のデバッグ </span><span class="sxs-lookup"><span data-stu-id="6c9bc-161">Debug JavaScript</span></span>  
:::image-end:::  

## <a name="set-up-a-workspace"></a><span data-ttu-id="6c9bc-162">ワークスペースを設定する</span><span class="sxs-lookup"><span data-stu-id="6c9bc-162">Set up a Workspace</span></span>  

<span data-ttu-id="6c9bc-163">既定では、[ソース] ツールでファイルを\*\*\*\* 編集すると、ページを更新するとそれらの変更は失われます。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-163">By default, when you edit a file in the **Sources** tool, those changes are lost when you refresh the page.</span></span>  <span data-ttu-id="6c9bc-164">**ワークスペース** を使用すると、DevTools で行った変更をファイル システムに保存することができます。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-164">**Workspaces** enable you to save the changes that you make in DevTools to your file system.</span></span>  <span data-ttu-id="6c9bc-165">基本的に、DevTools はコード エディターとして使うことができます。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-165">Essentially, DevTools is able to be used as your code editor.</span></span>

<span data-ttu-id="6c9bc-166">作業を開始するには、「[ワークスペースでファイルを編集][DevtoolsGuideChromiumWorkspacesIndex]」に移動します。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-166">Navigate to [Edit Files With Workspaces][DevtoolsGuideChromiumWorkspacesIndex] to get started.</span></span>

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="6c9bc-167">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="6c9bc-167">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageRunIcon]: ../media/run-snippet-icon.msft.png  

<!-- links -->  

[DevtoolsGuideChromiumCommandMenuIndex]: ../command-menu/index.md "Microsoft Edge DevTools コマンド メニュー を使用してコマンドを実行|Microsoft Docs"  
[DevtoolsGuideChromiumJavascriptIndex]: ../javascript/index.md "Microsoft Edge DevTools の JavaScript のデバッグの|Microsoft Docs"  
[DevtoolsGuideChromiumJavascriptSnippets]: ../javascript/snippets.md "Microsoft Edge DevTools を使用して任意のページで JavaScript のスニペットを実行|Microsoft Docs"  
[DevtoolsGuideChromiumWorkspacesIndex]: ../workspaces/index.md "Workspaces を使用してファイルを編集|Microsoft Docs"  

[HtmlstandardOrigin]: https://html.spec.whatwg.org/multipage/origin.html#origin "Origin |HTML 標準"  

[W3CHtml4Frames]: https://w3.org/TR/html401/present/frames.html "フレーム |W3C"  

> [!NOTE]
> <span data-ttu-id="6c9bc-174">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-174">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="6c9bc-175">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/sources) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-175">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/sources) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="6c9bc-177">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="6c9bc-177">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
