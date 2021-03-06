---
description: 結合、ミニファイ、またはコンパイルした後でも、クライアント側のコードを読み取り可能でデバッグ可能な状態に保つ。
title: 前処理されたコードをソース コードにマップする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 3240e437a917dd7074a0584b91dcc6c34576ca24
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564050"
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
# <a name="map-preprocessed-code-to-source-code"></a>前処理されたコードをソース コードにマップする  

結合、ミニファイ、またはコンパイルした後でも、クライアント側のコードを読み取り可能でデバッグ可能な状態に保つ。  ソース マップを使用して、ソース コードをコンパイル済みコードにマップします。  

### <a name="summary"></a>要約  

*   ソース コードをマップソース コードにマップするには、ソース コードを使用します。  その後、元のソースでコンパイルされたコードを読み取り、デバッグできます。  
*   ソース データを生成できるプリプロセッサのみを使用マップ。  
*   Web サーバーがソース サーバーにサービスを提供マップ。  
    
<!--todo: add link to preprocessors capable of producing Source Maps when section is available -->  
<!--[]: /web/tools/setup/setup-preprocessors?#supported_preprocessors ""  -->  

## <a name="get-started-with-preprocessors"></a>プリプロセッサの使用を開始する  

この記事では、DevTools Sources ツールで JavaScript Source マップ操作する方法について説明します。  <!--For a first overview of what preprocessors are, how each may help, and how Source Maps work; navigate to Set Up CSS & JS Preprocessors.  -->  

<!--todo: add link to Set Up CSS & JS Preprocessors when section is available -->  
<!--[]: /web/tools/setup/setup-preprocessors#debugging-and-editing-preprocessed-content ""  -->  

## <a name="use-a-supported-preprocessor"></a>サポートされているプリプロセッサを使用する  

ソース マップを作成できるミニフィアを使用します。  <!--For the most popular options, navigate to preprocessor support section.  -->  拡張ビューの場合は、[ソース マップ: 言語 [、ツール、その他の情報][GitHubWikiSourceMapsLanguagesTools] Wiki ページ] に移動します。  

<!--todo: add link to display the preprocessor support section when section is available -->  
<!--[]: /web/tools/setup/setup-preprocessors?#supported_preprocessors ""  -->  

次の種類のプリプロセッサは、一般的に Source ファイルと組み合わせてマップ。  

*   Transpilers \([Babel][BabelJS], [Traceur][GitHubWikiGoogleTraceurCompiler]\)  
*   Compilers \([Closure Compiler][GitHubGoogleClosureCompiler], [TypeScript][|::ref1::|Main], [CoffeeScript][|::ref2::|Main], [Dart][DartMain]\)  
*   Minifiers \([UglifyJS][GitHubMishooUglifyJS]\)  
    
## <a name="source-maps-in-devtools-sources-tool"></a>DevTools マップツールのソース ソース  

プリプロセッサマップソース を使用すると、DevTools は、マイニングされたファイルに加えて元のファイルを読み込む原因です。  次に、元のオブジェクトを使用してブレークポイントを設定し、コードをステップ実行します。  一方、Microsoft Edgeコードが実際に実行されています。  コードを実行すると、実稼働環境で開発サイトを実行しているような錯覚が生じ得る。  

DevTools で Source マップを実行する場合、JavaScript がコンパイルされていないと、参照する個々の JavaScript ファイルすべてが表示されます。  DevTools マップソース マッピングを使用していますが、基になる機能は実際にコンパイルされたコードを実行します。  エラー、ログ、およびブレークポイントは、すばらしいデバッグのために開発コードにマップされます。  したがって、実際には、実稼働環境で開発サイトを実行しているという錯覚が生じられます。  

### <a name="enable-source-maps-in-settings"></a>設定でソース マップを有効にする  

ソース マップは既定で有効になっています<!-- \(as of Microsoft Edge 39\)-->を選択しますが、それらをダブル チェックまたは有効にする場合。最初に DevTools を開き **、[DevTools** \( \) をカスタマイズして `...` 制御する] を **>設定。**  [基本設定 **] ウィンドウの**[ソース]**で****、[JavaScript**ソース の有効化] をオンマップ。  [CSS ソースを有効にする **] をオンにマップ。**  

:::image type="complex" source="../media/javascript-settings-preferences-sources-enable-javascript-source-maps.msft.png" alt-text="ソース の有効化マップ" lightbox="../media/javascript-settings-preferences-sources-enable-javascript-source-maps.msft.png":::
   **JavaScript ソース の有効化マップ**  
:::image-end:::  

### <a name="debugging-with-source-maps"></a>ソース ファイルを使用したデバッグマップ  

コードとソース ファイルをデバッグマップ、ソース マップ 2 つの場所で表示されます。  

1.  コンソール \(source へのリンクは、生成されたファイルではなく、元のファイルである必要があります\)  
1.  コード \(呼び出し履歴内のリンクをステップ実行すると、元のソース ファイル\) が開きます。  
    
<!--todo: add link to debugging your code when section is available -->  
<!--[DebugBreakpointsStepCode]: ../debug/breakpoints/step-code.md ""  -->  

## <a name="sourceurl-and-displayname"></a>@sourceURLおよび displayName  

ソース マップ仕様の一部ではないが、evals を操作するときに開発 `@sourceURL` をはるかに容易にすることができます。  ヘルパーはプロパティと同様に表示 `//# sourceMappingURL` され、Source Map V3 の仕様に記載されています。  

回避された次の特別なコメントをコードに含め、evals とインライン スクリプトとスタイルの名前を付け、それぞれの名前が DevTools に論理的な名前として表示されます。  

```javascript
//# sourceURL=source.coffee
```  

次のページに移動します。  

*   [デモ][CssNinjaDemoSourceMapping]

次のアクションを実行します。  

1.  DevTools を開き、[ソース] **ツールに移動** します。  
1.  [コード名: 入力] フィールド **にファイル名を** 入力します。  
1.  コンパイル ボタン **を選択** します。  
1.  CoffeeScript ソースから評価された合計を示すアラートが表示されます。  
    
[ソース] サブパネル **を** 展開すると、前に入力したカスタム ファイル名を含む新しいファイルが表示されます。  ダブルクリックしてこのファイルを表示すると、元のソース用にコンパイルされた JavaScript が含まれる。  ただし、最後の行には、元 `// @sourceURL` のソース ファイルを示すコメントがあります。  これは、言語の抽象化を操作する場合にデバッグに役立つ場合があります。  

:::image type="complex" source="../media/javascript-sources-page-coffeeeeeeee.msft.png" alt-text="sourceURL の使用" lightbox="../media/javascript-sources-page-coffeeeeeeee.msft.png":::
   作業 `sourceURL`  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る

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
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> 元のページはここで[](https://developers.google.com/web/tools/chrome-devtools/javascript/source-maps)見つかり[、Meggin Kearney][MegginKearney] \(Tech Writer\) と[Paul Bakaus][PaulBakaus] \(Open Web Developer Advocate, Google: Tools, Performance, Animation, UX\) によって作成されています。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
[MegginKearney]: https://developers.google.com/web/resources/contributors#meggin-kearney  
[PaulBakaus]: https://developers.google.com/web/resources/contributors#paul-bakaus  
