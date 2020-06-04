---
title: 前処理したコードをソースコードにマップする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/18/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: b48c67584b3f3253ada99e32c5dabfdccb2fa4de
ms.sourcegitcommit: ecdc4287fa25a18cb4ddcaf43fcce3b396c3314c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/17/2020
ms.locfileid: "10581797"
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





# 前処理したコードをソースコードにマップする   




クライアント側のコードは、結合、ミニ方法、またはコンパイルした後でも、読みやすく、デバッグ可能な状態にしておきます。  ソースマップを使って、ソースコードをコンパイル済みのコードにマップします。  

### まとめ  

*   ソースマップを使用して、minified コードをソースコードにマップします。 これで、元のソースでコンパイルされたコードの読み取りとデバッグを行うことができます。  
*   ソースマップを生成できるのはプリプロセッサだけです。  
*   Web サーバーがソースマップを提供できることを確認します。  

<!--todo: add link to preprocessors capable of producing Source Maps when section is available -->  
<!--[]: /web/tools/setup/setup-preprocessors?#supported_preprocessors ""  -->  

## プリプロセッサの使用を開始する  

この記事では、DevTools ソースパネルで JavaScript ソースマップを操作する方法について説明します。  <!--For a first overview of what preprocessors are, how each may help, and how Source Maps work; see Set Up CSS & JS Preprocessors.  -->  

<!--todo: add link to Set Up CSS & JS Preprocessors when section is available -->  
<!--[]: /web/tools/setup/setup-preprocessors#debugging-and-editing-preprocessed-content ""  -->  

## サポートされているプリプロセッサを使用する  

ソースマップを作成できるミニ識別子を使う必要があります。  <!--For the most popular options, see the preprocessor support section.  -->  拡張ビューの場合は、「[ソースマップ: 言語、ツール、その他の情報][GitHubWikiSourceMapsLanguagesTools]wiki」ページを参照してください。  

<!--todo: add link to see the preprocessor support section when section is available -->  
<!--[]: /web/tools/setup/setup-preprocessors?#supported_preprocessors ""  -->  

次の種類のプリプロセッサは、通常、ソースマップと組み合わせて使用されます。  

*   Transpilers \ ([Babel][BabelJS]、 [traceur][GitHubWikiGoogleTraceurCompiler]\)  
*   コンパイラ \ ([閉鎖コンパイラ][GitHubGoogleClosureCompiler]、 [TypeScript][|::ref1::|Main]、 [CoffeeScript][|::ref2::|Main]、 [Dart][DartMain]\)  
*   Minifiers \ ([UglifyJS][GitHubMishooUglifyJS]\)  

## DevTools ソースパネルのソースマップ  

プリプロセッサからソースマップを使用すると、既存のファイルに加えて、展開されたファイルを読み込むことができます。  次に、元のコードを使って、ブレークポイントとステップのコードを設定します。  一方、Microsoft Edge では、実際にはミニバーコードが実行されています。 これにより、開発サイトが運用環境で実行されるようになります。  

DevTools でソースマップを実行する場合は、JavaScript がコンパイルされておらず、参照される個々の JavaScript ファイルをすべて表示できることに注意してください。  これはソースマッピングを使用していますが、バックグラウンドで実際にコンパイル済みコードが実行されています。  すべてのエラー、ログ、ブレークポイントは、awesome デバッギングの開発コードにマップされます。  そのため、実際には、開発サイトを運用環境で実行しているように見えます。  

### [設定] でソースマップを有効にする  

ソースマップは既定で有効になっています <!--\(as of Microsoft Edge 39\)-->でも、これをダブルチェックまたは有効にする必要がある場合は、まず、DevTools の**カスタマイズと制御**のボタンをクリックし、[ `...` **設定**] を選択します。  [**環境設定**] ウィンドウの [**ソース**] で、[ **JavaScript ソースマップを有効にする**] をオンにします。  また、「 **CSS ソースマップを有効に**する」をオンにすることもできます。  

> ##### 図 1  
> ソースマップを有効にする  
> ![ソースマップを有効にする][ImageSourceMaps]  

### ソースマップを使ったデバッグ  

コードをデバッグし、ソースマップを有効にすると、ソースマップは次の2つの場所に表示されます。  

1.  コンソールで \ (ソースへのリンクは元のファイルであり、生成されたものではありません)  
1.  コードをステップ実行している場合 (通話スタック内のリンクは元のソースファイルを開く必要があります)。  

<!--todo: add link to debugging your code when section is available -->  
<!--[DebugBreakpointsStepCode]: https://docs.microsoft.com/microsoft-edge/devtools-guide-chromium/debug/breakpoints/step-code ""  -->  

## @sourceURL and displayName  

ソースマップ仕様の一部ではありませんが、を使用すると、 `@sourceURL` evals を操作するときに、開発をより簡単に行うことができます。  このヘルパーは、プロパティに非常に類似 `//# sourceMappingURL` しており、実際にはソースマップ V3 の仕様について説明されています。  

コードに次の特殊なコメントを含めることによって、evals とインラインのスクリプトとスタイルに名前を付けて、それぞれが DevTools でより論理的な名前として表示されるようにすることができます。  

```javascript
//# sourceURL=source.coffee
```  

次のページに移動します。  

*   [デモ][CssNinjaDemoSourceMapping]

次の手順を実行します。  

1.  DevTools を開き、[**ソース**] パネルに移動します。  
1.  [ **_Code:_** input] フィールドにファイル名を入力します。  
1.  [**コンパイル**] ボタンをクリックします。  
1.  警告が表示され、CoffeeScript ソースから評価された合計が示されます。  

[**_ソース_**] サブパネルを展開すると、前に入力したカスタムファイル名を含む新しいファイルが表示されるようになります。  このファイルをダブルクリックして表示すると、元のソースのコンパイル済み JavaScript が含まれます。  ただし、最後の行には、 `// @sourceURL` 元のソースファイルを示すコメントがあります。  これは、言語の抽象化を操作しているときに、デバッグに役立つ場合があります。  

> ##### 図 2
> SourceURL を使用する  
> ![SourceURL を使用する][ImageCoffeeScript]  

<!--## Feedback   -->  



<!-- image links -->  

[ImageSourceMaps]: /microsoft-edge/devtools-guide-chromium/media/javascript-settings-preferences-sources-enable-javascript-source-maps.msft.png "図 1: ソースマップを有効にする"  
[ImageCoffeeScript]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-page-coffeeeeeeee.msft.png "図 2: sourceURL を使用する"  

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
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/source-maps)にあり、 [Meggin Kearney][MegginKearney] \ (Tech Writer \) と[Paul Bakaus][PaulBakaus] \ (Open Web 開発者の立場、Google: ツール、パフォーマンス、アニメーション、UX) によって作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
[PaulBakaus]: https://developers.google.com/web/resources/contributors/pbakaus  