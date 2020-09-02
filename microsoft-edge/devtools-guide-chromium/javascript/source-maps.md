---
title: ソース コードに前処理コードをマッピングする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 35aa864c20def5f5cd11979d6239e8316c1acbca
ms.sourcegitcommit: b88d2a55a59db8373ff2bac275d3730977bf19c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2020
ms.locfileid: "10986144"
---
<!-- Copyright Meggin Kearney and Paul Bakaus

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  

# <span data-ttu-id="9cec6-103">前処理したコードをソースコードにマップする</span><span class="sxs-lookup"><span data-stu-id="9cec6-103">Map preprocessed code to source code</span></span>  

<span data-ttu-id="9cec6-104">クライアント側のコードは、結合、ミニ方法、またはコンパイルした後でも、読みやすく、デバッグ可能な状態にしておきます。</span><span class="sxs-lookup"><span data-stu-id="9cec6-104">Keep your client-side code readable and debuggable even after you combine, minify, or compile it.</span></span>  <span data-ttu-id="9cec6-105">ソースマップを使って、ソースコードをコンパイル済みのコードにマップします。</span><span class="sxs-lookup"><span data-stu-id="9cec6-105">Use source maps to map your source code to your compiled code.</span></span>  

### <span data-ttu-id="9cec6-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="9cec6-106">Summary</span></span>  

*   <span data-ttu-id="9cec6-107">ソースマップを使用して、minified コードをソースコードにマップします。</span><span class="sxs-lookup"><span data-stu-id="9cec6-107">Use Source Maps to map minified code to source code.</span></span> <span data-ttu-id="9cec6-108">これで、元のソースでコンパイルされたコードの読み取りとデバッグを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9cec6-108">You are then able to read and debug compiled code in the original source.</span></span>  
*   <span data-ttu-id="9cec6-109">ソースマップを生成できるプリプロセッサのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="9cec6-109">Only use pre-processors capable of producing Source Maps.</span></span>  
*   <span data-ttu-id="9cec6-110">Web サーバーがソースマップを提供できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9cec6-110">Verify that your web server is able to serve Source Maps.</span></span>  
    
<!--todo: add link to preprocessors capable of producing Source Maps when section is available -->  
<!--[]: /web/tools/setup/setup-preprocessors?#supported_preprocessors ""  -->  

## <span data-ttu-id="9cec6-111">プリプロセッサの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="9cec6-111">Get started with preprocessors</span></span>  

<span data-ttu-id="9cec6-112">この記事では、DevTools ソースパネルで JavaScript ソースマップを操作する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9cec6-112">This article explains how to interact with JavaScript Source Maps in the DevTools Sources Panel.</span></span>  <!--For a first overview of what preprocessors are, how each may help, and how Source Maps work; see Set Up CSS & JS Preprocessors.  -->  

<!--todo: add link to Set Up CSS & JS Preprocessors when section is available -->  
<!--[]: /web/tools/setup/setup-preprocessors#debugging-and-editing-preprocessed-content ""  -->  

## <span data-ttu-id="9cec6-113">サポートされているプリプロセッサを使用する</span><span class="sxs-lookup"><span data-stu-id="9cec6-113">Use a supported preprocessor</span></span>  

<span data-ttu-id="9cec6-114">ソースマップを作成できるミニ識別子を使う必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cec6-114">You need to use a minifier that is capable of creating source maps.</span></span>  <!--For the most popular options, see the preprocessor support section.  -->  <span data-ttu-id="9cec6-115">拡張ビューの場合は、「 [ソースマップ: 言語、ツール、その他の情報][GitHubWikiSourceMapsLanguagesTools] wiki」ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cec6-115">For an extended view, see the [Source maps: languages, tools and other info][GitHubWikiSourceMapsLanguagesTools] wiki page.</span></span>  

<!--todo: add link to see the preprocessor support section when section is available -->  
<!--[]: /web/tools/setup/setup-preprocessors?#supported_preprocessors ""  -->  

<span data-ttu-id="9cec6-116">次の種類のプリプロセッサは、通常、ソースマップと組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="9cec6-116">The following types of preprocessors are commonly used in combination with Source Maps:</span></span>  

*   <span data-ttu-id="9cec6-117">Transpilers \ ([Babel][BabelJS]、 [traceur][GitHubWikiGoogleTraceurCompiler]\)</span><span class="sxs-lookup"><span data-stu-id="9cec6-117">Transpilers \([Babel][BabelJS], [Traceur][GitHubWikiGoogleTraceurCompiler]\)</span></span>  
*   <span data-ttu-id="9cec6-118">コンパイラ \ ([閉鎖コンパイラ][GitHubGoogleClosureCompiler]、 [TypeScript][|::ref1::|Main]、 [CoffeeScript][|::ref2::|Main]、 [Dart][DartMain]\)</span><span class="sxs-lookup"><span data-stu-id="9cec6-118">Compilers \([Closure Compiler][GitHubGoogleClosureCompiler], [TypeScript][|::ref1::|Main], [CoffeeScript][|::ref2::|Main], [Dart][DartMain]\)</span></span>  
*   <span data-ttu-id="9cec6-119">Minifiers \ ([UglifyJS][GitHubMishooUglifyJS]\)</span><span class="sxs-lookup"><span data-stu-id="9cec6-119">Minifiers \([UglifyJS][GitHubMishooUglifyJS]\)</span></span>  
    
## <span data-ttu-id="9cec6-120">DevTools ソースパネルのソースマップ</span><span class="sxs-lookup"><span data-stu-id="9cec6-120">Source Maps in DevTools Sources panel</span></span>  

<span data-ttu-id="9cec6-121">プリプロセッサからソースマップを使用すると、既存のファイルに加えて、展開されたファイルを読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="9cec6-121">Source Maps from preprocessors cause DevTools to load your original files in addition to your minified ones.</span></span>  <span data-ttu-id="9cec6-122">次に、元のコードを使って、ブレークポイントとステップのコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="9cec6-122">You then use the originals to set breakpoints and step through code.</span></span>  <span data-ttu-id="9cec6-123">一方、Microsoft Edge では、実際にはミニバーコードが実行されています。</span><span class="sxs-lookup"><span data-stu-id="9cec6-123">Meanwhile, Microsoft Edge is actually running your minified code.</span></span> <span data-ttu-id="9cec6-124">これにより、開発サイトが運用環境で実行されるようになります。</span><span class="sxs-lookup"><span data-stu-id="9cec6-124">This gives you the illusion of running a development site in production.</span></span>  

<span data-ttu-id="9cec6-125">DevTools でソースマップを実行する場合は、JavaScript がコンパイルされておらず、参照される個々の JavaScript ファイルをすべて表示できることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9cec6-125">When running Source Maps in DevTools, you should notice that the JavaScript is not compiled and you are able to see all the individual JavaScript files it references.</span></span>  <span data-ttu-id="9cec6-126">これはソースマッピングを使用していますが、バックグラウンドで実際にコンパイル済みコードが実行されています。</span><span class="sxs-lookup"><span data-stu-id="9cec6-126">This is using source mapping, but behind the scenes actually runs the compiled code.</span></span>  <span data-ttu-id="9cec6-127">すべてのエラー、ログ、ブレークポイントは、awesome デバッギングの開発コードにマップされます。</span><span class="sxs-lookup"><span data-stu-id="9cec6-127">Any errors, logs, and breakpoints map to the dev code for awesome debugging!</span></span>  <span data-ttu-id="9cec6-128">そのため、実際には、開発サイトを運用環境で実行しているように見えます。</span><span class="sxs-lookup"><span data-stu-id="9cec6-128">So in effect it gives you the illusion that you are running a dev site in production.</span></span>  

### <span data-ttu-id="9cec6-129">[設定] でソースマップを有効にする</span><span class="sxs-lookup"><span data-stu-id="9cec6-129">Enable Source Maps in settings</span></span>  

<span data-ttu-id="9cec6-130">ソースマップは既定で有効になっています</span><span class="sxs-lookup"><span data-stu-id="9cec6-130">Source Maps are enabled by default</span></span> <!--\(as of Microsoft Edge 39\)--><span data-ttu-id="9cec6-131">でも、これをダブルチェックまたは有効にする必要がある場合は、まず、DevTools の **カスタマイズと制御** をクリックして、[ `...` **設定**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9cec6-131">, but if you want to double-check or enable them; first open DevTools, click the **Customize and control DevTools** \(`...`\) button, and select **Settings**.</span></span>  <span data-ttu-id="9cec6-132">[ **環境設定** ] ウィンドウの [ **ソース**] で、[ **JavaScript ソースマップを有効にする**] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="9cec6-132">On the **Preferences** pane, under **Sources**, check **Enable JavaScript Source Maps**.</span></span>  <span data-ttu-id="9cec6-133">また、「 **CSS ソースマップを有効に**する」をオンにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9cec6-133">You may also check **Enable CSS Source Maps**.</span></span>  

:::image type="complex" source="../media/javascript-settings-preferences-sources-enable-javascript-source-maps.msft.png" alt-text="ソースマップを有効にする" lightbox="../media/javascript-settings-preferences-sources-enable-javascript-source-maps.msft.png":::
   **<span data-ttu-id="9cec6-135">JavaScript ソースマップを有効にする</span><span class="sxs-lookup"><span data-stu-id="9cec6-135">Enable JavaScript Source Maps</span></span>**  
:::image-end:::  

### <span data-ttu-id="9cec6-136">ソースマップを使ったデバッグ</span><span class="sxs-lookup"><span data-stu-id="9cec6-136">Debugging with Source Maps</span></span>  

<span data-ttu-id="9cec6-137">コードをデバッグし、ソースマップを有効にすると、ソースマップは次の2つの場所に表示されます。</span><span class="sxs-lookup"><span data-stu-id="9cec6-137">When debugging your code and Source Maps enabled, Source Maps show in two places:</span></span>  

1.  <span data-ttu-id="9cec6-138">コンソールで \ (ソースへのリンクは元のファイルであり、生成されたものではありません)</span><span class="sxs-lookup"><span data-stu-id="9cec6-138">In the console \(the link to source should be the original file, not the generated one\)</span></span>  
1.  <span data-ttu-id="9cec6-139">コードをステップ実行している場合 (通話スタック内のリンクは元のソースファイルを開く必要があります)。</span><span class="sxs-lookup"><span data-stu-id="9cec6-139">When stepping through code \(the links in the call stack should open the original source file\)</span></span>  
    
<!--todo: add link to debugging your code when section is available -->  
<!--[DebugBreakpointsStepCode]: ../debug/breakpoints/step-code.md ""  -->  

## <span data-ttu-id="9cec6-140">@sourceURL and displayName</span><span class="sxs-lookup"><span data-stu-id="9cec6-140">@sourceURL and displayName</span></span>  

<span data-ttu-id="9cec6-141">ソースマップ仕様の一部ではありませんが、を使用すると、 `@sourceURL` evals を操作するときに、開発をより簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9cec6-141">While not part of the Source Map spec, the `@sourceURL` allows you to make development much easier when working with evals.</span></span>  <span data-ttu-id="9cec6-142">このヘルパーは、プロパティに非常に類似 `//# sourceMappingURL` しており、実際にはソースマップ V3 の仕様について説明されています。</span><span class="sxs-lookup"><span data-stu-id="9cec6-142">This helper looks very similar to the `//# sourceMappingURL` property and is actually mentioned in the Source Map V3 specifications.</span></span>  

<span data-ttu-id="9cec6-143">コードに次の特殊なコメントを含めることによって、evals とインラインのスクリプトとスタイルに名前を付けて、それぞれが DevTools でより論理的な名前として表示されるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="9cec6-143">By including the following special comment in your code, which is be evaled, you are able to name evals and inline scripts and styles so each appears as more logical names in your DevTools.</span></span>  

```javascript
//# sourceURL=source.coffee
```  

<span data-ttu-id="9cec6-144">次のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="9cec6-144">Navigate to the following page.</span></span>  

*   [<span data-ttu-id="9cec6-145">デモ</span><span class="sxs-lookup"><span data-stu-id="9cec6-145">demo</span></span>][CssNinjaDemoSourceMapping]

<span data-ttu-id="9cec6-146">次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="9cec6-146">Complete the following actions.</span></span>  

1.  <span data-ttu-id="9cec6-147">DevTools を開き、[ **ソース** ] パネルに移動します。</span><span class="sxs-lookup"><span data-stu-id="9cec6-147">Open the DevTools and go to the **Sources** panel.</span></span>  
1.  <span data-ttu-id="9cec6-148">[ **Code:** input] フィールドにファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="9cec6-148">Enter in a filename into the **Name your code:** input field.</span></span>  
1.  <span data-ttu-id="9cec6-149">[ **コンパイル** ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9cec6-149">Click on the **compile** button.</span></span>  
1.  <span data-ttu-id="9cec6-150">警告が表示され、CoffeeScript ソースから評価された合計が示されます。</span><span class="sxs-lookup"><span data-stu-id="9cec6-150">An alert appears with the evaluated sum from the CoffeeScript source.</span></span>  
    
<span data-ttu-id="9cec6-151">[ **ソース** ] サブパネルを展開すると、前に入力したカスタムファイル名を含む新しいファイルが表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="9cec6-151">If you expand the **Sources** sub-panel you now see a new file with the custom filename you entered earlier.</span></span>  <span data-ttu-id="9cec6-152">このファイルをダブルクリックして表示すると、元のソースのコンパイル済み JavaScript が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9cec6-152">If you double-click to view this file it contains the compiled JavaScript for the original source.</span></span>  <span data-ttu-id="9cec6-153">ただし、最後の行には、 `// @sourceURL` 元のソースファイルを示すコメントがあります。</span><span class="sxs-lookup"><span data-stu-id="9cec6-153">On the last line, however, is a `// @sourceURL` comment indicating the original source file.</span></span>  <span data-ttu-id="9cec6-154">これは、言語の抽象化を操作しているときに、デバッグに役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="9cec6-154">This may help you with debugging while working with language abstractions.</span></span>  

:::image type="complex" source="../media/javascript-sources-page-coffeeeeeeee.msft.png" alt-text="SourceURL を使用する" lightbox="../media/javascript-sources-page-coffeeeeeeee.msft.png":::
   <span data-ttu-id="9cec6-156">共同作業</span><span class="sxs-lookup"><span data-stu-id="9cec6-156">Work with</span></span> `sourceURL`  
:::image-end:::  

## <span data-ttu-id="9cec6-157">Microsoft Edge DevTools チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="9cec6-157">Getting in touch with the Microsoft Edge DevTools team</span></span>

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[BabelJS]: https://babeljs.io "Babel は JavaScript コンパイラです"  

[CoffeeScriptMain]: https://coffeescript.org "CoffeeScript"  

[CssNinjaDemoSourceMapping]: https://www.thecssninja.com/demo/source_mapping/compile.html "# SourceURL eval の簡単な例"  

[DartMain]: https://www.dartlang.org "Dart プログラミング言語"  

[GitHubGoogleClosureCompiler]: https://github.com/google/closure-compiler "google/クロージャ-コンパイラ |GitHub"  

[GitHubMishooUglifyJS]: https://github.com/mishoo/UglifyJS "mishoo/UglifyJS |GitHub"  

[GitHubWikiSourceMapsLanguagesTools]: https://github.com/ryanseddon/source-map/wiki/Source-maps:-languages,-tools-and-other-info "ソースマップ: 言語、ツール、その他の情報 |GitHub wiki"  

[GitHubWikiGoogleTraceurCompiler]: https://github.com/google/traceur-compiler/wiki/Getting-Started "はじめに-google/traceur-compiler |GitHub wiki"  

[TypeScriptMain]: https://www.typescriptlang.org "TypeScript"  

> [!NOTE]
> <span data-ttu-id="9cec6-167">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="9cec6-167">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="9cec6-168">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/source-maps) にあり、 [Meggin Kearney][MegginKearney] \ (Tech Writer \) と [Paul Bakaus][PaulBakaus] \ (Open Web 開発者の立場、Google: ツール、パフォーマンス、アニメーション、UX) によって作成されています。</span><span class="sxs-lookup"><span data-stu-id="9cec6-168">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/source-maps) and is authored by [Meggin Kearney][MegginKearney] \(Tech Writer\) and [Paul Bakaus][PaulBakaus] \(Open Web Developer Advocate, Google: Tools, Performance, Animation, and UX\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="9cec6-170">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="9cec6-170">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
[PaulBakaus]: https://developers.google.com/web/resources/contributors/pbakaus  
