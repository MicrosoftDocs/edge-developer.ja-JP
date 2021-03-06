---
description: Microsoft Edge DevTools ヒープ プロファイラーを使用してヒープ スナップショットを記録し、メモリ リークを見つける方法について説明します。
title: ヒープ スナップショットを記録する方法
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: ce7a6f972bed386f96312808428bd74f1241668f
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397805"
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

# <a name="how-to-record-heap-snapshots"></a>ヒープ スナップショットを記録する方法  

Microsoft Edge DevTools ヒープ プロファイラーを使用してヒープ スナップショットを記録し、メモリ リークを見つける方法について説明します。  

Microsoft Edge DevTools ヒープ プロファイラーは、ページの JavaScript オブジェクトと関連する DOM ノードによるメモリの分布を表示します。  JavaScript ヒープ \(JS heap\) スナップショットの取得、メモリ グラフの分析、スナップショットの比較、メモリ リークの検出に使用します。  [オブジェクト保持 [ツリー] に移動します][DevtoolsMemoryProblems101ObjectsRetainingTree]。  

## <a name="take-a-snapshot"></a>スナップショットを作成する  

[メモリ] **パネルで** 、[スナップショットの取得] **を選択し**、[スタート] を **選択します**。  `Ctrl` + `E` \(Windows, Linux\) または `Cmd` + `E` \(macOS\) を選択できます。  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots.msft.png" alt-text="プロファイルの種類を選択する" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots.msft.png":::
   プロファイルの種類を選択する  
:::image-end:::  

**スナップショットは** 、最初はレンダラー プロセス メモリに格納されます。  スナップショットは、スナップショット アイコンを選択して表示するときに、オンデマンドで DevTools に転送されます。  

スナップショットが DevTools に読み込まれ、解析された後、スナップショット タイトルの下の番号が表示され、到達可能な JavaScript オブジェクトの合計サイズ [が表示されます][DevtoolsMemoryProblems101ObjectSizes]。  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all.msft.png" alt-text="到達可能なオブジェクトの合計サイズ" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all.msft.png":::
   到達可能なオブジェクトの合計サイズ  
:::image-end:::  

> [!NOTE]
> スナップショットには、到達可能なオブジェクトだけが含まれます。  また、スナップショットの取得は常にガベージ コレクションから始まります。  

## <a name="clear-snapshots"></a>スナップショットのクリア  

[ **すべてのプロファイルをクリアする** ] アイコンを選択して、スナップショット \(DevTools とレンダラー プロセスに関連付けられているメモリの両方)を削除します。  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all-hover-clear-all-profiles.msft.png" alt-text="スナップショットの削除" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all-hover-clear-all-profiles.msft.png":::
   スナップショットの削除  
:::image-end:::  

DevTools ウィンドウを閉じると、レンダラー プロセスに関連付けられたメモリからプロファイルは削除されません。  DevTools を再度開くと、以前に作成されたスナップショットすべてがスナップショットの一覧に再び表示されます。  

> [!NOTE]
> この散布オブジェクトの例を [試し][GlitchDevtoolsMemoryExample03] 、ヒープ プロファイラーを使用してプロファイルを作成します。  \(object\) アイテムの割り当ての数が表示されます。  

## <a name="view-snapshots"></a>スナップショットの表示  

タスクごとに異なる視点からスナップショットを表示します。  

**概要ビューには、** コンストラクター名でグループ化されたオブジェクトが表示されます。  コンストラクター名でグループ化された型に基づいてオブジェクト \(およびメモリ使用\) を検索する場合に使用します。  DOM リークの追跡に **特に役立ちます**。

<!--todo: add profile memory problems memory diagnosis (tracking down DOM leaks) section when available  -->  

**比較ビュー**.  2 つのスナップショットの違いを表示します。  操作の前と後の 2 つの \(or more\) メモリ スナップショットを比較する場合に使用します。  解放されたメモリと参照カウントでデルタを検査すると、メモリ リークの有無と原因を確認できます。  

**Containment ビュー**.  ヒープの内容の探索を許可します。  **Containment ビューは** 、オブジェクト構造のより良いビューを提供し、グローバル名前空間 \(window\) で参照されているオブジェクトを分析して、オブジェクトを保持しているオブジェクトを見つけるのに役立つ。  クロージャを分析し、低レベルでオブジェクトに飛び込む場合に使用します。  

ビューを切り替える場合は、ビューの上部にあるセレクターを使用します。  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-view-dropdown.msft.png" alt-text="ビューの切り替えセレクター" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-view-dropdown.msft.png":::
   ビューの切り替えセレクター  
:::image-end:::  

> [!NOTE]
> 一部のプロパティが JavaScript ヒープに格納される場合があります。  ネイティブ コードを実行する getter を使用して実装されたプロパティはキャプチャされません。  また、数値などの文字列以外の値はキャプチャされません。  

### <a name="summary-view"></a>概要ビュー  

最初は、スナップショットが [概要] ビューに開き、オブジェクトの合計が表示され、インスタンスを表示するために展開される場合があります。  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-retainers.msft.png" alt-text="概要ビュー" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-retainers.msft.png":::
   **概要ビュー**  
:::image-end:::  

トップ レベルのエントリは"合計" 行です。  

| トップ レベルのエントリ | 説明 |  
|:--- |:--- |  
| **コンストラクター** | このコンストラクターを使用して作成されたオブジェクトを表します。  |  
| **距離** | ノードの最短の単純パスを使用してルートまでの距離を表示します。  |  
| **浅いサイズ** | 特定のコンストラクター関数によって作成されたオブジェクトの浅いサイズの合計を表示します。  浅いサイズは、オブジェクトが保持するメモリのサイズです (通常、配列と文字列は浅いサイズが大きくなります\)。  [オブジェクトの [サイズ] に移動します][DevtoolsMemoryProblems101ObjectSizes]。  |  
| **保持サイズ** | 同じオブジェクト セットの中で保持される最大サイズを表示します。  オブジェクトが削除された後に解放できるメモリのサイズ \(および依存が到達不能になった\) は、保持されたサイズと呼ばれる。  [オブジェクトの [サイズ] に移動します][DevtoolsMemoryProblems101ObjectSizes]。  |  

<!--| **Number of object instances** | Displayed in the # column.  |  -->  

上部ビューで合計行を展開すると、すべてのインスタンスが表示されます。  インスタンスごとに、浅いサイズと保持されたサイズが対応する列に表示されます。  文字の後の番号はオブジェクトの一意の ID で、オブジェクトごとにヒープ スナップショット `@` を比較できます。  

黄色のオブジェクトは JavaScript 参照を持ち、赤いオブジェクトは、黄色の背景を持つノードから参照されるデタッチノードです。  

**ヒープ プロファイラーのさまざまなコンストラクター \(group\) エントリは何に対応しますか?**  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-highlight.msft.png" alt-text="コンストラクター グループ" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-highlight.msft.png":::
   **コンストラクター グループ**  
:::image-end:::  

| コンストラクター \(group\) エントリ | 説明 |  
|:--- |:--- |  
| **\(global property\)** | グローバル オブジェクト \(\など) とによって参照される `window` オブジェクトとの間の中間オブジェクト。  オブジェクトがコンストラクターを使用して作成され、グローバル オブジェクトによって保持されている場合、保持パスは `Person` として表される場合があります `[global] > \(global property\) > Person` 。  これは、オブジェクトが互いに直接参照する標準とは対照的です。  パフォーマンス上の理由から、中間オブジェクトが存在します。  グローバルは定期的に変更され、プロパティ アクセスの最適化はグローバル 以外のオブジェクトに対して適切な処理を行います。グローバルオブジェクトには適用できません。  |  
| **\(roots\)** | 保持ツリー ビューのルート エントリは、選択したオブジェクトへの参照を持つエンティティです。  エントリは、エンジン固有の目的でエンジンによって作成された参照である場合があります。  エンジンには参照オブジェクトのキャッシュがありますが、そのような参照はすべて弱く、本当に強力な参照が存在しない場合にオブジェクトが収集されるのを防ぐ必要はありません。  |  
| **\(closure\)** | 関数クロージャを介したオブジェクトのグループへの参照の数。  |  
| **\(array, string, number, regexp\)** | Array、String、Number、または正規表現を参照するプロパティを持つオブジェクト型のリスト。  |  
| **\(コンパイルされたコード\)** | コンパイルされたコードに関連するすべて。  スクリプトは関数に似ていますが、本文に対応 `<script>` します。  SharedFunctionInfos \(SFI\) は、関数とコンパイル済みコードの間に存在するオブジェクトです。  通常、関数にはコンテキストが含まれていますが、SFIs はコンテキストを使用できません。  |  
| **HTMLDivElement** **、HTMLAnchorElement、DocumentFragment**など。 ****  | コードによって参照される特定の型の要素またはドキュメント オブジェクトへの参照。  |  

<!--todo: add heap profiling summary section when available -->  

### <a name="comparison-view"></a>比較ビュー  

複数のスナップショットを互いに比較して、リークされたオブジェクトを検索します。  特定のアプリケーション操作でリークが発生しない \(たとえば、通常は、ドキュメントを開いて閉じるなど、直接操作と逆方向の操作のペアを作成しない場合は、ガベージ\を残さない方が良い) を確認するには、次のシナリオに従います。  

1.  操作を実行する前にヒープ スナップショットを作成します。  
1.  操作を実行する \(何らかの方法でページを操作し、リークを引き起こしている可能性があります\)。  
1.  逆方向の操作を実行する \(反対の操作を行い、数回繰り返す\)。  
1.  2 番目のヒープ スナップショットを作成し、このヒープ スナップショットのビューを比較に変更 **し**、スナップショット **1 と比較します**。  
    
比較ビュー **では** 、2 つのスナップショットの違いが表示されます。  合計エントリを展開すると、追加および削除されたオブジェクト インスタンスが表示されます。  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-comparison-dropdown.msft.png" alt-text="比較ビュー" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-comparison-dropdown.msft.png":::
   **比較** ビュー  
:::image-end:::  

<!--todo: add HeapProfilingComparison section when available  -->  

### <a name="containment-view"></a>Containment ビュー  

Containment **ビュー** は基本的に、アプリケーションのオブジェクト構造の "鳥の目" です。  これにより、関数クロージャの内部を覗き見し、JavaScript オブジェクトを構成する仮想マシン \(VM\) 内部オブジェクトを観察し、アプリケーションが非常に低いレベルで使用するメモリの量を理解できます。  

| 格納ビューのエントリ ポイント | 説明 |  
|:--- |:--- |  
| **DOMWindow オブジェクト** | JavaScript コードのグローバル オブジェクト。  |  
| **GC ルート** | VM のガベージによって使用される実際の GC ルート。  GC ルートは、組み込みのオブジェクト マップ、シンボル テーブル、VM スレッド スタック、コンパイル キャッシュ、ハンドル スコープ、およびグローバル ハンドルで構成されます。  |  
| **ネイティブ オブジェクト** | JavaScript 仮想マシン \(JavaScript VM\) 内のブラウザー オブジェクトを "プッシュ" して、DOM ノード、CSS ルールなど、オートメーションを許可します。  |  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-containment-dropdown.msft.png" alt-text="Containment ビュー" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-containment-dropdown.msft.png":::
   **Containment** ビュー  
:::image-end:::  

<!--todo: add heap profiling containment section when available  -->  

> [!TIP]
> クロージャに関するヒント。  スナップショット内のクロージャを簡単に区別するために、関数に名前を付ける。  たとえば、この例では名前付き関数を使用しない場合です。  
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
> 次のコード スニペットでは、名前付き関数を使用します。  
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
> > クロージャが [メモリに与 `eval` ][GlitchDevtoolsMemoryExample07] える影響を分析するために悪い理由のこの例を試してみてください。  この例では、ヒープ割り当ての記録を行う方法について [説明][GlitchDevtoolsMemoryExample08]します。  
> 

## <a name="look-up-color-coding"></a>色分けを見る  

オブジェクトのプロパティとプロパティの値は、さまざまな種類を持ち、色付けされます。  各プロパティには、4 つの種類の 1 つがあります。  

| プロパティの種類 | 説明 |  
|:--- |:--- |  
| **a: プロパティ** | \(dot\) 演算子を使用してアクセスされる名前を持つ通常のプロパティ、または `.` `[` `]` \(brackets\) 表記など `["foo bar"]` です。  |  
| **0: 要素** | \(brackets\) 表記を使用してアクセスされる、数値インデックス `[` `]` を持つ通常のプロパティ。  |  
| **a: context var** |  関数のクロージャ内から変数名でアクセスできる関数コンテキスト内の変数。  |  
| **a: system prop** | JavaScript のコードからアクセスできない JavaScript VM によって追加されたプロパティ。  |  

指定されたオブジェクトには `System` 、対応する JavaScript 型が含まれています。  それぞれは、Javascript VM のオブジェクト システム実装の一部です。  V8 は、ユーザーの JS オブジェクトと同じヒープ内のほとんどの内部オブジェクトを割り当てます。  したがって、これらは V8 の内部です。  

## <a name="find-a-specific-object"></a>特定のオブジェクトを検索する  

収集されたヒープ内のオブジェクトを見つけるには、オブジェクト ID を使用 `Ctrl` + `F` して検索して指定します。  

## <a name="uncover-dom-leaks"></a>DOM リークを検出する  

ヒープ プロファイラーには、ブラウザー ネイティブ オブジェクト \(DOM ノード、CSS ルール\) と JavaScript オブジェクト間の双方向の依存関係を反映する機能があります。
これは、切り離された DOM サブツリーが浮いているのを忘れた場合に、見えないリークが発生しているのを発見するのに役立ちます。  

DOM リークは、思ったよりも大きい場合があります。  次のサンプルを検討してください。  GC の#treeですか?  

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

関連する親 \(parentNode\) への参照を再帰的に保持します。 `#leaf` `#tree` したがって、leafRef が nullified の場合にのみ `#tree` 、GC の候補の下にある WHOLE ツリーになります。  

:::image type="complex" source="../media/memory-problems-tree-gc.msft.png" alt-text="DOM サブツリー" lightbox="../media/memory-problems-tree-gc.msft.png":::
   DOM サブツリー  
:::image-end:::  

> [!NOTE]
> 例: リークしている [DOM][GlitchDevtoolsMemoryExample06] ノードのこの例を試して、リークする可能性のある場所と、それを検出する方法を理解します。  また、DOM リークが予想以上に大きいという [この例を見る場合があります][GlitchDevtoolsMemoryExample09]。  

DOM リークとメモリ分析の基本について詳しくは [、Gonzalo Ruiz][GonzaloRuizdeVillaMemory] de Villa の Microsoft Edge DevTools を使用してメモリ リークの検索とデバッグを行います。  

<!--  
> [!NOTE]
> Example: Try this **demo** to play with detached DOM trees.  
-->  

<!--todo: add heap profiling dom leaks section when available  -->  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsMemoryProblems101ObjectSizes]: ./memory-101.md#object-sizes "オブジェクトサイズ - メモリ用語|Microsoft Docs"  
[DevtoolsMemoryProblems101ObjectsRetainingTree]: ./memory-101.md#objects-retaining-tree "ツリーを保持するオブジェクト - メモリ用語|Microsoft Docs"  

<!--[DevToolsHeapProfilingComparison]: https://developer.alphabet.com/devtools/docs/heap-profiling-comparison ""  -->  
<!--[DevToolsHeapProfilingContainment]: https://developer.alphabet.com/devtools/docs/heap-profiling-containment ""  -->  
<!--[DevtoolsHeapProfilingDomLeaks]: https://developer.alphabet.com/devtools/docs/heap-profiling-dom-leaks ""  -->  
<!--[DevToolsHeapProfilingSummary]: https://developer.alphabet.com/devtools/docs/heap-profiling-summary ""  -->  
<!--[DevtoolsProfileMemoryProblemsDiagnosisCausesMemoryLeaks]: ../profile/memory-problems/memory-diagnosis#narrow-down-causes-of-memory-leaks ""  -->  

[GlitchDevtoolsMemoryExample03]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-03.html "example-03.html - Microsoft Edge (クロム) DevTools |Glitch"  
[GlitchDevtoolsMemoryExample06]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-06.html "example-06.html - Microsoft Edge (クロム) DevTools |Glitch"  
[GlitchDevtoolsMemoryExample07]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-07.html "example-07.html - Microsoft Edge (クロム) DevTools |Glitch"  
[GlitchDevtoolsMemoryExample08]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-08.html "example-08.html - Microsoft Edge (クロム) DevTools |Glitch"  
[GlitchDevtoolsMemoryExample09]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-09.html "example-09.html - Microsoft Edge (クロム) DevTools |Glitch"  
[GlitchDevtoolsMemoryExample10]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-10.html "example-10.html - Microsoft Edge (クロム) DevTools |Glitch"  

[GonzaloRuizdeVillaMemory]: https://slid.es/gruizdevilla/memory "メモリ |スライド"  

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> 元のページはここで [見](https://developers.google.com/web/tools/chrome-devtools/memory-problems/heap-snapshots) つかり [、Meggin Kearney][MegginKearney] \(Technical Writer\) によって作成されています。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
