---
description: Microsoft Edge DevTools ヒーププロファイラーを使用してヒープスナップショットを記録し、メモリリークを検出する方法について説明します。
title: ヒープスナップショットの記録方法
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 15692b0258de6db66c0b58a2659348a6e849aaca
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993472"
---
<!-- Copyright Meggin Kearney 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->

# ヒープスナップショットの記録方法  

Microsoft Edge DevTools ヒーププロファイラーを使用してヒープスナップショットを記録し、メモリリークを検出する方法について説明します。  

Microsoft Edge DevTools ヒーププロファイラーは、JavaScript オブジェクトとページの関連する DOM ノードによるメモリ分布を示しています。  これは、JavaScript ヒープ \ (JS ヒープ) スナップショットの取得、メモリグラフの分析、スナップショットの比較、メモリリークの検出に使用します。  「 [オブジェクトを保持するツリー][DevtoolsMemoryProblems101ObjectsRetainingTree]」もご覧ください。  

## スナップショットを撮る  

[ **メモリ** ] パネルで、[ **スナップショット**の作成] を選択し、[ **開始**] をクリックします。  `Ctrl` + `E` \ (Windows \) または `Cmd` + `E` \ (macOS \) を押すこともできます。  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots.msft.png" alt-text="プロファイルの種類の選択" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots.msft.png":::
   プロファイルの種類の選択  
:::image-end:::  

**スナップショット** は、最初はレンダラープロセスメモリに格納されます。  スナップショットは、スナップショットアイコンをクリックして表示すると、DevTools に転送されます。  

スナップショットが DevTools に読み込まれ、解析されると、スナップショットのタイトルの下に表示される数値が表示され、 [アクセス可能な JavaScript オブジェクトの合計サイズ][DevtoolsMemoryProblems101ObjectSizes]が示されます。  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all.msft.png" alt-text="到達可能なオブジェクトの合計サイズ" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all.msft.png":::
   到達可能なオブジェクトの合計サイズ  
:::image-end:::  

> [!NOTE]
> スナップショットには、到達可能なオブジェクトのみが含まれます。  また、スナップショットの取得は、常にガベージコレクションで開始されます。  

## スナップショットをクリアする  

[ **すべてのプロファイルをクリア** ] アイコンをクリックして、スナップショットを削除します (devtools から、およびレンダラープロセスに関連付けられているすべてのメモリの両方)。  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all-hover-clear-all-profiles.msft.png" alt-text="スナップショットを削除する" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all-hover-clear-all-profiles.msft.png":::
   スナップショットを削除する  
:::image-end:::  

DevTools ウィンドウを閉じると、レンダラープロセスに関連するメモリからプロファイルが削除されることはありません。  DevTools を再び開くと、以前に使用していたスナップショットがすべて、スナップショットの一覧に再び表示されます。  

> [!NOTE]
> この例では、 [散在][GlitchDevtoolsMemoryExample03] しているオブジェクトの例を試して、ヒーププロファイラーを使ってそのオブジェクトをプロファイルしています。  いくつかの \ (オブジェクト \) 項目の割り当てが表示されます。  

## スナップショットの表示  

さまざまなタスクについてさまざまな視点からスナップショットを表示します。  

[**概要] ビュー**は、コンストラクター名によってグループ化されたオブジェクトを示しています。  このオブジェクトを使うと、コンストラクター名によってグループ化された型に基づいて、オブジェクト \ (およびメモリ使用量) を簡単に探すことができます。  これは、 **DOM リークを追跡**する場合に特に便利です。

<!--todo: add profile memory problems memory diagnosis (tracking down DOM leaks) section when available  -->  

**比較ビュー**。  2つのスナップショットの差を表示します。  操作の前後の2つ以上のメモリスナップショットを比較するために使います。  解放されたメモリと参照カウントでデルタを調べると、メモリリークの有無と原因を確認できます。  

**コンテインメントビュー**。  ヒープの内容を調査できます。  **コンテインメントビュー** では、オブジェクト構造の詳細が表示され、グローバル名前空間 \ (ウィンドウ \) で参照されているオブジェクトを分析して、オブジェクトをどのように維持しているかを確認できます。  これを使って、クロージャを分析し、オブジェクトを低レベルで見ていきます。  

ビューを切り替えるには、ビューの上部にあるセレクターを使用します。  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-view-dropdown.msft.png" alt-text="ビューセレクターの切り替え" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-view-dropdown.msft.png":::
   ビューセレクターの切り替え  
:::image-end:::  

> [!NOTE]
> すべてのプロパティが JavaScript ヒープに保存されるわけではありません。  ネイティブコードを実行する getter を使って実装されたプロパティはキャプチャされません。  また、数値などの文字列以外の値はキャプチャされません。  

### サマリービュー  

最初に、スナップショットが [概要] ビューで開き、次のようにオブジェクトの合計が表示されます。これは、インスタンスを表示するために展開することができます。  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-retainers.msft.png" alt-text="サマリービュー" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-retainers.msft.png":::
   **サマリー** ビュー  
:::image-end:::  

トップレベルのエントリは、"合計" 行です。  

| トップレベルのエントリ | 説明 |  
|:--- |:--- |  
| **コンストラクター** | このコンストラクターを使用して作成されたすべてのオブジェクトを表します。  |  
| **距離** | ノードの最短のシンプルパスを使用してルートへの距離を表示します。  |  
| **浅いサイズ** | 特定のコンストラクター関数で作成されたすべてのオブジェクトの浅いサイズの合計を表示します。  緩斜面サイズとは、オブジェクトによって保持されているメモリのサイズです (一般的には、配列と文字列の緩斜面サイズが大きくなります)。  「 [オブジェクトサイズ][DevtoolsMemoryProblems101ObjectSizes]」もご覧ください。  |  
| **保持サイズ** | 同じオブジェクトセット間で保持される最大のサイズを表示します。  オブジェクトが削除された後に解放できるメモリのサイズ \ (および依存関係がなくなります) は、保持されているサイズと呼ばれます。  「 [オブジェクトサイズ][DevtoolsMemoryProblems101ObjectSizes]」もご覧ください。  |  

<!--| **Number of object instances** | Displayed in the # column.  |  -->  

上のビューで合計行を展開すると、すべてのインスタンスが表示されます。  各インスタンスについて、"浅い" と "保持されるサイズ" が対応する列に表示されます。  文字の後に `@` 表示される数値は、オブジェクトの一意の ID です。ヒープスナップショットは、オブジェクトごとに比較できます。  

黄色のオブジェクトには JavaScript 参照と赤のオブジェクトがあり、いずれかが黄色の背景で参照される切り離されたノードであることに注意してください。  

**ヒーププロファイラーのさまざまなコンストラクター \ (グループ \) エントリに対応するものは何ですか?**  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-highlight.msft.png" alt-text="コンストラクターグループ" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-highlight.msft.png":::
   **コンストラクター** グループ  
:::image-end:::  

| コンストラクター \ (グループ \) エントリ | 説明 |  
|:--- |:--- |  
| **\ (グローバルプロパティ \)** | グローバルオブジェクトの間 ( `window` \) とそれが参照するオブジェクトの間の中間オブジェクト。  コンストラクターを使ってオブジェクトを作成 `Person` し、グローバルオブジェクトで保持している場合、保持パスは次のようになり `[global] > \(global property\) > Person` ます。  これは、オブジェクトが互いに直接参照する場合とは対照的です。  中間オブジェクトは、パフォーマンス上の理由で存在します。  グローバル変数は定期的に変更され、プロパティアクセスの最適化が行われます。グローバルでないオブジェクトには、グローバルには適用されません。  |  
| **\ (ルート \)** | 保持ツリービューのルートエントリは、選択したオブジェクトを参照するエンティティです。  エンジン固有の目的で、エンジンによって作成された参照をエントリにすることもできます。  エンジンには参照オブジェクトをキャッシュしていますが、このような参照はすべて脆弱であり、実際には厳密な参照がないため、オブジェクトは収集されません。  |  
| **\ (休業)** | 関数クロージャによってオブジェクトのグループに対する参照の数。  |  
| **\ (配列, 文字列, 数値, regexp \)** | 配列、文字列、数値、または正規表現を参照するプロパティを持つオブジェクト型のリスト。  |  
| **\ (コンパイル済みコード)** | コンパイル済みコードに関連するすべて。  スクリプトは関数と似ていますが、本文に対応してい `<script>` ます。  SharedFunctionInfos 機能 \ (SFI \) は、関数とコンパイルされたコードの間に位置するオブジェクトです。  関数は通常、コンテキストを持ちますが、SFIs はできません。  |  
| **HTMLDivElement**、 **HTMLAnchorElement**、 **documentfragment**など。  | コードで参照されている特定の型の要素またはドキュメントオブジェクトへの参照。  |  

<!--todo: add heap profiling summary section when available -->  

### 比較ビュー  

リークしたオブジェクトを検索するには、複数のスナップショットを相互に比較します。  特定のアプリケーションの操作によってリークが発生しないことを確認するには (たとえば、ドキュメントを開いて、それを閉じるときに、通常は1組の直接操作と逆方向の操作のペアである)、次のシナリオに従うことができます。  

1.  操作を実行する前に、ヒープスナップショットを取得します。  
1.  操作を実行します (リークの原因と思われる何らかの方法でページを操作します)。  
1.  逆の操作を実行します (反対の操作を行って、何度も繰り返します)。  
1.  2つ目のヒープスナップショットを取得し、そのビューを**スナップショット 1**と比較して**比較**します。  
    
[ **比較** ] ビューでは、2つのスナップショットの差が表示されます。  合計項目を展開すると、追加または削除されたオブジェクトインスタンスが表示されます。  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-comparison-dropdown.msft.png" alt-text="比較ビュー" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-comparison-dropdown.msft.png":::
   **比較** ビュー  
:::image-end:::  

<!--todo: add HeapProfilingComparison section when available  -->  

### コンテインメントビュー  

**コンテインメント**ビューは、基本的には、アプリケーションのオブジェクト構造の "鳥の視点" ビューです。  この機能を使用すると、JavaScript オブジェクトを構成する仮想マシン \ (VM) 内部オブジェクトを監視したり、アプリケーションが非常に低レベルで使用しているメモリ量を把握したりすることができます。  

| コンテインメントビューのエントリポイント | 説明 |  
|:--- |:--- |  
| **DOMWindow オブジェクト** | JavaScript コードのグローバルオブジェクト。  |  
| **GC ルート** | VM のガーベジで使用される実際の GC ルート。  GC ルートは、組み込みのオブジェクトマップ、シンボルテーブル、VM スレッドスタック、コンパイルキャッシュ、ハンドルスコープ、グローバルハンドルで構成されています。  |  
| **ネイティブオブジェクト** | ブラウザーオブジェクトは、JavaScript 仮想マシンの内部に "プッシュされました" (JavaScript VM \) で、オートメーション (DOM ノード、CSS ルールなど) を許可します。  |  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-containment-dropdown.msft.png" alt-text="コンテインメントビュー" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-containment-dropdown.msft.png":::
   **コンテインメント** ビュー  
:::image-end:::  

<!--todo: add heap profiling containment section when available  -->  

> [!TIP]
> クロージャに関するヒント。  スナップショットのクロージャを簡単に区別できるように、関数に名前を指定します。  たとえば、次の例では、名前付き関数は使用されません。  
> 
> ```javascript
> function createLargeClosure() {
>     var largeStr = new Array(1000000).join('x');
>     var lC = function() { // this is NOT a named function
>         return largeStr;
>     };
>     return lC;
> }
> ```  
> 
> 以下のコードスニペットでは、名前付き関数を使用しています。  
> 
> ```javascript
> function createLargeClosure() {
>     var largeStr = new Array(1000000).join('x');
>     var lC = function lC() { // this IS a named function
>         return largeStr;
>     };
>     return lC;
> }
> ```  
> 
> <!--  
> :::image type="complex" source="../media/memory-problems-domleaks.msft.png" alt-text="Name functions to distinguish between closures" lightbox="../media/memory-problems-domleaks.msft.png":::
>    Name functions to distinguish between closures  
> :::image-end:::  
> -->  
> 
> > [!NOTE]
> > この例では、メモリ上でのクロージャの影響を分析するための悪を示して [ `eval` い][GlitchDevtoolsMemoryExample07] ます。  また、この例では、 [ヒープ割り当て][GlitchDevtoolsMemoryExample08]の記録に関する次の例を参考にしてください。  
> 

## 色のコーディングを検索する  

オブジェクトのプロパティとプロパティ値の型が異なり、それに応じて色付けされます。  各プロパティには、4つの型のいずれかが含まれています。  

| プロパティの種類 | 説明 |  
|:--- |:--- |  
| **a: プロパティ** | 名前を付けた標準プロパティ `.` 。 \ (ドット \) 演算子、または `[` `]` \ (かっこ \) 表記を使用してアクセスし `["foo bar"]` ます。  |  
| **0: 要素** | `[` `]` \ (かっこ \) 表記法によってアクセスされる、数値インデックスを持つ標準プロパティ。  |  
| **a: context var** |  関数の中で変数名によってアクセスできる関数のコンテキスト内の変数。  |  
| **a: システムの prop** | Javascript の VM によって追加されたプロパティ。 JavaScript コードからはアクセスできません。  |  

として指定 `System` されているオブジェクトは、JavaScript の型に対応していません。  それぞれは、Javascript VM のオブジェクトシステム実装の一部です。  V8 は、内部オブジェクトのほとんどを、ユーザーの JS オブジェクトと同じヒープに割り当てます。  そのため、これらは V8 の内部構造にすぎません。  

## 特定のオブジェクトを検索する  

収集されたヒープ内のオブジェクトを検索するには、を使用 `Ctrl` + `F` してオブジェクト ID を指定します。  

## DOM リークの発見  

ヒーププロファイラーには、ブラウザーのネイティブオブジェクトの間で双方向の依存関係 (DOM ノード、CSS ルール \)、JavaScript オブジェクトの間で双方向の依存関係を反映する機能があります。
これにより、デタッチした切り離された DOM サブツリーを回避して、非表示のリークが発生する可能性があります。  

DOM リークは想像よりも大きくなることがあります。  次の例について考えてみましょう。  #Tree GC はいつですか?  

```javascript
var select = document.querySelector;
var treeRef = select("#tree");
var leafRef = select("#leaf");
var body = select("body");
body.removeChild(treeRef);
//#tree in not GC yet due to treeRef
treeRef = null;
//#tree is not GC yet due to indirect
//reference from leafRef
leafRef = null;
//#NOW able to be #tree GC
```  

は、 `#leaf` 関連する親 \ (parentNode \) への参照を保持し、 `#tree` leafRef が nullified の場合にのみ、GC の候補の下にあるツリー全体を示し `#tree` ます。  

:::image type="complex" source="../media/memory-problems-tree-gc.msft.png" alt-text="DOM サブツリー" lightbox="../media/memory-problems-tree-gc.msft.png":::
   DOM サブツリー  
:::image-end:::  

> [!NOTE]
> 例: リークしている可能性のある [DOM ノード][GlitchDevtoolsMemoryExample06] を理解し、それを検出する方法については、次の例をご覧ください。  次の例では、 [DOM リークが予想よりも大きくなって][GlitchDevtoolsMemoryExample09]います。  

DOM のリークとメモリ分析の基礎の詳細については、「 [Microsoft Edge DevTools によるメモリリークの検出とデバッグ][GonzaloRuizdeVillaMemory] Gonzalo Ruiz de Villa」を参照してください。  

<!--  
> [!NOTE]
> Example: Try this **demo** to play with detached DOM trees.  
-->  

<!--todo: add heap profiling dom leaks section when available  -->  

## Microsoft Edge DevTools チームと連絡を取り合う  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsMemoryProblems101ObjectSizes]: ./memory-101.md#object-sizes "オブジェクトサイズ-メモリの用語 |Microsoft ドキュメント"  
[DevtoolsMemoryProblems101ObjectsRetainingTree]: ./memory-101.md#objects-retaining-tree "ツリーメモリの用語を保持するオブジェクト |Microsoft ドキュメント"  

<!--[DevToolsHeapProfilingComparison]: https://developer.alphabet.com/devtools/docs/heap-profiling-comparison ""  -->  
<!--[DevToolsHeapProfilingContainment]: https://developer.alphabet.com/devtools/docs/heap-profiling-containment ""  -->  
<!--[DevtoolsHeapProfilingDomLeaks]: https://developer.alphabet.com/devtools/docs/heap-profiling-dom-leaks ""  -->  
<!--[DevToolsHeapProfilingSummary]: https://developer.alphabet.com/devtools/docs/heap-profiling-summary ""  -->  
<!--[DevtoolsProfileMemoryProblemsDiagnosisCausesMemoryLeaks]: ../profile/memory-problems/memory-diagnosis#narrow-down-causes-of-memory-leaks ""  -->  

[GlitchDevtoolsMemoryExample03]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-03.html "example-03.html-Microsoft Edge (Chromium) DevTools |故障"  
[GlitchDevtoolsMemoryExample06]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-06.html "example-06.html-Microsoft Edge (Chromium) DevTools |故障"  
[GlitchDevtoolsMemoryExample07]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-07.html "example-07.html-Microsoft Edge (Chromium) DevTools |故障"  
[GlitchDevtoolsMemoryExample08]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-08.html "example-08.html-Microsoft Edge (Chromium) DevTools |故障"  
[GlitchDevtoolsMemoryExample09]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-09.html "example-09.html-Microsoft Edge (Chromium) DevTools |故障"  
[GlitchDevtoolsMemoryExample10]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-10.html "example-10.html-Microsoft Edge (Chromium) DevTools |故障"  

[GonzaloRuizdeVillaMemory]: https://slid.es/gruizdevilla/memory "メモリ |スライド"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/memory-problems/heap-snapshots) にあり、 [Meggin Kearney][MegginKearney] \ (テクニカルライター \) によって作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
