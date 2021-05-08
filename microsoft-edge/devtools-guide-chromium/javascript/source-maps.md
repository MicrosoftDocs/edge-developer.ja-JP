---
description: 結合、ミニファイ、またはコンパイルした後でも、クライアント側のコードを読み取り可能でデバッグ可能な状態に保つ。
title: 前処理されたコードをソース コードにマップする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: c04d1ec02b188cc7ec8ab2598b395dbeb4431c46
ms.sourcegitcommit: 16e2f7232196a57a70b979bbf8b663774b7ddc20
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/25/2021
ms.locfileid: "11519416"
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

# <a name="map-preprocessed-code-to-source-code"></a><span data-ttu-id="dfc5f-104">前処理されたコードをソース コードにマップする</span><span class="sxs-lookup"><span data-stu-id="dfc5f-104">Map preprocessed code to source code</span></span>  

<span data-ttu-id="dfc5f-105">結合、ミニファイ、またはコンパイルした後でも、クライアント側のコードを読み取り可能でデバッグ可能な状態に保つ。</span><span class="sxs-lookup"><span data-stu-id="dfc5f-105">Keep your client-side code readable and debuggable even after you combine, minify, or compile it.</span></span>  <span data-ttu-id="dfc5f-106">ソース マップを使用して、ソース コードをコンパイル済みコードにマップします。</span><span class="sxs-lookup"><span data-stu-id="dfc5f-106">Use source maps to map your source code to your compiled code.</span></span>  

### <a name="summary"></a><span data-ttu-id="dfc5f-107">まとめ</span><span class="sxs-lookup"><span data-stu-id="dfc5f-107">Summary</span></span>  

*   <span data-ttu-id="dfc5f-108">ソース コードをマップソース コードにマップするには、ソース コードを使用します。</span><span class="sxs-lookup"><span data-stu-id="dfc5f-108">Use Source Maps to map minified code to source code.</span></span>  <span data-ttu-id="dfc5f-109">その後、元のソースでコンパイルされたコードを読み取り、デバッグできます。</span><span class="sxs-lookup"><span data-stu-id="dfc5f-109">You are then able to read and debug compiled code in the original source.</span></span>  
*   <span data-ttu-id="dfc5f-110">ソース データを生成できるプリプロセッサのみを使用マップ。</span><span class="sxs-lookup"><span data-stu-id="dfc5f-110">Only use pre-processors capable of producing Source Maps.</span></span>  
*   <span data-ttu-id="dfc5f-111">Web サーバーがソース サーバーにサービスを提供マップ。</span><span class="sxs-lookup"><span data-stu-id="dfc5f-111">Verify that your web server is able to serve Source Maps.</span></span>  
    
<!--todo: add link to preprocessors capable of producing Source Maps when section is available -->  
<!--[]: /web/tools/setup/setup-preprocessors?#supported_preprocessors ""  -->  

## <a name="get-started-with-preprocessors"></a><span data-ttu-id="dfc5f-112">プリプロセッサの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="dfc5f-112">Get started with preprocessors</span></span>  

<span data-ttu-id="dfc5f-113">この記事では、DevTools Sources ツールで JavaScript Source マップ操作する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dfc5f-113">This article explains how to interact with JavaScript Source Maps in the DevTools Sources tool.</span></span>  <!--For a first overview of what preprocessors are, how each may help, and how Source Maps work; navigate to Set Up CSS & JS Preprocessors.  -->  

<!--todo: add link to Set Up CSS & JS Preprocessors when section is available -->  
<!--[]: /web/tools/setup/setup-preprocessors#debugging-and-editing-preprocessed-content ""  -->  

## <a name="use-a-supported-preprocessor"></a><span data-ttu-id="dfc5f-114">サポートされているプリプロセッサを使用する</span><span class="sxs-lookup"><span data-stu-id="dfc5f-114">Use a supported preprocessor</span></span>  

<span data-ttu-id="dfc5f-115">ソース マップを作成できるミニフィアを使用します。</span><span class="sxs-lookup"><span data-stu-id="dfc5f-115">Use a minifier that is capable of creating source maps.</span></span>  <!--For the most popular options, navigate to preprocessor support section.  -->  <span data-ttu-id="dfc5f-116">拡張ビューの場合は、[ソース マップ: 言語 [、ツール、その他の情報][GitHubWikiSourceMapsLanguagesTools] Wiki ページ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="dfc5f-116">For an extended view, navigate to [Source maps: languages, tools and other info][GitHubWikiSourceMapsLanguagesTools] wiki page.</span></span>  

<!--todo: add link to display the preprocessor support section when section is available -->  
<!--[]: /web/tools/setup/setup-preprocessors?#supported_preprocessors ""  -->  

<span data-ttu-id="dfc5f-117">次の種類のプリプロセッサは、一般的に Source ファイルと組み合わせてマップ。</span><span class="sxs-lookup"><span data-stu-id="dfc5f-117">The following types of preprocessors are commonly used in combination with Source Maps:</span></span>  

*   <span data-ttu-id="dfc5f-118">Transpilers \([Babel][BabelJS], [Traceur][GitHubWikiGoogleTraceurCompiler]\)</span><span class="sxs-lookup"><span data-stu-id="dfc5f-118">Transpilers \([Babel][BabelJS], [Traceur][GitHubWikiGoogleTraceurCompiler]\)</span></span>  
*   <span data-ttu-id="dfc5f-119">Compilers \([Closure Compiler][GitHubGoogleClosureCompiler], [TypeScript][|::ref1::|Main], [CoffeeScript][|::ref2::|Main], [Dart][DartMain]\)</span><span class="sxs-lookup"><span data-stu-id="dfc5f-119">Compilers \([Closure Compiler][GitHubGoogleClosureCompiler], [TypeScript][|::ref1::|Main], [CoffeeScript][|::ref2::|Main], [Dart][DartMain]\)</span></span>  
*   <span data-ttu-id="dfc5f-120">Minifiers \([UglifyJS][GitHubMishooUglifyJS]\)</span><span class="sxs-lookup"><span data-stu-id="dfc5f-120">Minifiers \([UglifyJS][GitHubMishooUglifyJS]\)</span></span>  
    
## <a name="source-maps-in-devtools-sources-tool"></a><span data-ttu-id="dfc5f-121">DevTools マップツールのソース ソース</span><span class="sxs-lookup"><span data-stu-id="dfc5f-121">Source Maps in DevTools Sources tool</span></span>  

<span data-ttu-id="dfc5f-122">プリプロセッサマップソース を使用すると、DevTools は、マイニングされたファイルに加えて元のファイルを読み込む原因です。</span><span class="sxs-lookup"><span data-stu-id="dfc5f-122">Source Maps from preprocessors cause DevTools to load your original files in addition to your minified ones.</span></span>  <span data-ttu-id="dfc5f-123">次に、元のオブジェクトを使用してブレークポイントを設定し、コードをステップ実行します。</span><span class="sxs-lookup"><span data-stu-id="dfc5f-123">You then use the originals to set breakpoints and step through code.</span></span>  <span data-ttu-id="dfc5f-124">一方、Microsoft Edgeコードが実際に実行されています。</span><span class="sxs-lookup"><span data-stu-id="dfc5f-124">Meanwhile, Microsoft Edge is actually running your minified code.</span></span>  <span data-ttu-id="dfc5f-125">コードを実行すると、実稼働環境で開発サイトを実行しているような錯覚が生じ得る。</span><span class="sxs-lookup"><span data-stu-id="dfc5f-125">The running of the code gives you the illusion of running a development site in production.</span></span>  

<span data-ttu-id="dfc5f-126">DevTools で Source マップを実行する場合、JavaScript がコンパイルされていないと、参照する個々の JavaScript ファイルすべてが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dfc5f-126">When running Source Maps in DevTools, you should notice that the JavaScript is not compiled and all of the individual JavaScript files it references are displayed.</span></span>  <span data-ttu-id="dfc5f-127">DevTools マップソース マッピングを使用していますが、基になる機能は実際にコンパイルされたコードを実行します。</span><span class="sxs-lookup"><span data-stu-id="dfc5f-127">Source Maps in DevTools is using source mapping, but the underlying functionality actually runs the compiled code.</span></span>  <span data-ttu-id="dfc5f-128">エラー、ログ、およびブレークポイントは、すばらしいデバッグのために開発コードにマップされます。</span><span class="sxs-lookup"><span data-stu-id="dfc5f-128">Any errors, logs, and breakpoints map to the dev code for awesome debugging.</span></span>  <span data-ttu-id="dfc5f-129">したがって、実際には、実稼働環境で開発サイトを実行しているという錯覚が生じられます。</span><span class="sxs-lookup"><span data-stu-id="dfc5f-129">So in effect it gives you the illusion that you are running a dev site in production.</span></span>  

### <a name="enable-source-maps-in-settings"></a><span data-ttu-id="dfc5f-130">設定でソース マップを有効にする</span><span class="sxs-lookup"><span data-stu-id="dfc5f-130">Enable Source Maps in settings</span></span>  

<span data-ttu-id="dfc5f-131">ソース マップは既定で有効になっています</span><span class="sxs-lookup"><span data-stu-id="dfc5f-131">Source Maps are enabled by default</span></span><!-- \(as of Microsoft Edge 39\)--><span data-ttu-id="dfc5f-132">を選択しますが、それらをダブル チェックまたは有効にする場合。最初に DevTools を開き **、[DevTools** \( \) をカスタマイズして `...` 制御する] を **>設定。**</span><span class="sxs-lookup"><span data-stu-id="dfc5f-132">, but if you want to double-check or enable them; first open DevTools, choose **Customize and control DevTools** \(`...`\) > **Settings**.</span></span>  <span data-ttu-id="dfc5f-133">[基本設定 **] ウィンドウの**[ソース]**で\*\*\*\*、[JavaScript**ソース の有効化] をオンマップ。</span><span class="sxs-lookup"><span data-stu-id="dfc5f-133">On the **Preferences** pane, under **Sources**, turn on **Enable JavaScript Source Maps**.</span></span>  <span data-ttu-id="dfc5f-134">[CSS ソースを有効にする **] をオンにマップ。**</span><span class="sxs-lookup"><span data-stu-id="dfc5f-134">You may also turn on the **Enable CSS Source Maps**.</span></span>  

:::image type="complex" source="../media/javascript-settings-preferences-sources-enable-javascript-source-maps.msft.png" alt-text="ソース の有効化マップ" lightbox="../media/javascript-settings-preferences-sources-enable-javascript-source-maps.msft.png":::
   **<span data-ttu-id="dfc5f-136">JavaScript ソース の有効化マップ</span><span class="sxs-lookup"><span data-stu-id="dfc5f-136">Enable JavaScript Source Maps</span></span>**  
:::image-end:::  

### <a name="debugging-with-source-maps"></a><span data-ttu-id="dfc5f-137">ソース ファイルを使用したデバッグマップ</span><span class="sxs-lookup"><span data-stu-id="dfc5f-137">Debugging with Source Maps</span></span>  

<span data-ttu-id="dfc5f-138">コードとソース ファイルをデバッグマップ、ソース マップ 2 つの場所で表示されます。</span><span class="sxs-lookup"><span data-stu-id="dfc5f-138">When debugging your code and Source Maps enabled, Source Maps show in two places:</span></span>  

1.  <span data-ttu-id="dfc5f-139">コンソール \(source へのリンクは、生成されたファイルではなく、元のファイルである必要があります\)</span><span class="sxs-lookup"><span data-stu-id="dfc5f-139">In the console \(the link to source should be the original file, not the generated one\)</span></span>  
1.  <span data-ttu-id="dfc5f-140">コード \(呼び出し履歴内のリンクをステップ実行すると、元のソース ファイル\) が開きます。</span><span class="sxs-lookup"><span data-stu-id="dfc5f-140">When stepping through code \(the links in the call stack should open the original source file\)</span></span>  
    
<!--todo: add link to debugging your code when section is available -->  
<!--[DebugBreakpointsStepCode]: ../debug/breakpoints/step-code.md ""  -->  

## <a name="sourceurl-and-displayname"></a><span data-ttu-id="dfc5f-141">@sourceURLおよび displayName</span><span class="sxs-lookup"><span data-stu-id="dfc5f-141">@sourceURL and displayName</span></span>  

<span data-ttu-id="dfc5f-142">ソース マップ仕様の一部ではないが、evals を操作するときに開発 `@sourceURL` をはるかに容易にすることができます。</span><span class="sxs-lookup"><span data-stu-id="dfc5f-142">While not part of the Source Map spec, the `@sourceURL` allows you to make development much easier when working with evals.</span></span>  <span data-ttu-id="dfc5f-143">ヘルパーはプロパティと同様に表示 `//# sourceMappingURL` され、Source Map V3 の仕様に記載されています。</span><span class="sxs-lookup"><span data-stu-id="dfc5f-143">The helper is displayed similar to the `//# sourceMappingURL` property and is mentioned in the Source Map V3 specifications.</span></span>  

<span data-ttu-id="dfc5f-144">回避された次の特別なコメントをコードに含め、evals とインライン スクリプトとスタイルの名前を付け、それぞれの名前が DevTools に論理的な名前として表示されます。</span><span class="sxs-lookup"><span data-stu-id="dfc5f-144">By including the following special comment in your code, which is evaled, you are able to name evals and inline scripts and styles so each appears as more logical names in your DevTools.</span></span>  

```javascript
//# sourceURL=source.coffee
```  

<span data-ttu-id="dfc5f-145">次のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="dfc5f-145">Navigate to the following page.</span></span>  

*   [<span data-ttu-id="dfc5f-146">デモ</span><span class="sxs-lookup"><span data-stu-id="dfc5f-146">demo</span></span>][CssNinjaDemoSourceMapping]

<span data-ttu-id="dfc5f-147">次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="dfc5f-147">Complete the following actions.</span></span>  

1.  <span data-ttu-id="dfc5f-148">DevTools を開き、[ソース] **ツールに移動** します。</span><span class="sxs-lookup"><span data-stu-id="dfc5f-148">Open DevTools and navigate to the **Sources** tool.</span></span>  
1.  <span data-ttu-id="dfc5f-149">[コード名: 入力] フィールド **にファイル名を** 入力します。</span><span class="sxs-lookup"><span data-stu-id="dfc5f-149">Enter in a filename into the **Name your code:** input field.</span></span>  
1.  <span data-ttu-id="dfc5f-150">コンパイル ボタン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="dfc5f-150">Choose the **compile** button.</span></span>  
1.  <span data-ttu-id="dfc5f-151">CoffeeScript ソースから評価された合計を示すアラートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dfc5f-151">An alert appears, showing the evaluated sum from the CoffeeScript source.</span></span>  
    
<span data-ttu-id="dfc5f-152">[ソース] サブパネル **を** 展開すると、前に入力したカスタム ファイル名を含む新しいファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dfc5f-152">If you expand the **Sources** sub-panel you now display a new file with the custom filename you entered earlier.</span></span>  <span data-ttu-id="dfc5f-153">ダブルクリックしてこのファイルを表示すると、元のソース用にコンパイルされた JavaScript が含まれる。</span><span class="sxs-lookup"><span data-stu-id="dfc5f-153">If you double-click to view this file, it contains the compiled JavaScript for the original source.</span></span>  <span data-ttu-id="dfc5f-154">ただし、最後の行には、元 `// @sourceURL` のソース ファイルを示すコメントがあります。</span><span class="sxs-lookup"><span data-stu-id="dfc5f-154">On the last line, however, is a `// @sourceURL` comment indicating the original source file.</span></span>  <span data-ttu-id="dfc5f-155">これは、言語の抽象化を操作する場合にデバッグに役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="dfc5f-155">This may help you with debugging while working with language abstractions.</span></span>  

:::image type="complex" source="../media/javascript-sources-page-coffeeeeeeee.msft.png" alt-text="sourceURL の使用" lightbox="../media/javascript-sources-page-coffeeeeeeee.msft.png":::
   <span data-ttu-id="dfc5f-157">作業</span><span class="sxs-lookup"><span data-stu-id="dfc5f-157">Work with</span></span> `sourceURL`  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="dfc5f-158">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="dfc5f-158">Getting in touch with the Microsoft Edge DevTools team</span></span>

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[BabelJS]: https://babeljs.io "Babel は JavaScript コンパイラです"  

[CoffeeScriptMain]: https://coffeescript.org "CoffeeScript"  

[CssNinjaDemoSourceMapping]: https://www.thecssninja.com/demo/source_mapping/compile.html "//# sourceURL eval 名前付けの簡単な例"  

[DartMain]: https://www.dartlang.org "ダーツプログラミング言語"  

[GitHubGoogleClosureCompiler]: https://github.com/google/closure-compiler "google/closure-compiler |GitHub"  

[GitHubMishooUglifyJS]: https://github.com/mishoo/UglifyJS "mishoo/UglifyJS |GitHub"  

[GitHubWikiSourceMapsLanguagesTools]: https://github.com/ryanseddon/source-map/wiki/Source-maps:-languages,-tools-and-other-info "ソース マップ: 言語、ツール、その他の情報|GitHub Wiki"  

[GitHubWikiGoogleTraceurCompiler]: https://github.com/google/traceur-compiler/wiki/Getting-Started "Getting Started - google/traceur-compiler |GitHub Wiki"  

[TypeScriptMain]: https://www.typescriptlang.org "TypeScript"  

> [!NOTE]
> <span data-ttu-id="dfc5f-168">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="dfc5f-168">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="dfc5f-169">元のページはここで[](https://developers.google.com/web/tools/chrome-devtools/javascript/source-maps)見つかり[、Meggin Kearney][MegginKearney] \(Tech Writer\) と[Paul Bakaus][PaulBakaus] \(Open Web Developer Advocate, Google: Tools, Performance, Animation, UX\) によって作成されています。</span><span class="sxs-lookup"><span data-stu-id="dfc5f-169">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/source-maps) and is authored by [Meggin Kearney][MegginKearney] \(Tech Writer\) and [Paul Bakaus][PaulBakaus] \(Open Web Developer Advocate, Google: Tools, Performance, Animation, and UX\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="dfc5f-171">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="dfc5f-171">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
[PaulBakaus]: https://developers.google.com/web/resources/contributors/pbakaus  
