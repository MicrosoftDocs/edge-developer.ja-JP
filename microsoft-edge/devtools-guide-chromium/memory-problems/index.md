---
description: Microsoft Edge と DevTools を使って、ページのパフォーマンスに影響するメモリの問題を見つける方法について説明します。これには、メモリリーク、メモリの膨張、ガベージコレクションの頻度などがあります。
title: メモリの問題を解決する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: ef820353f81eb3fd791433e9c53434dff3b10a60
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "10992779"
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

# メモリの問題を解決する  

Microsoft Edge と DevTools を使って、ページのパフォーマンスに影響するメモリの問題を見つける方法について説明します。これには、メモリリーク、メモリの膨張、ガベージコレクションの頻度などがあります。  

### まとめ  

*   Microsoft Edge Browser のタスクマネージャーで現在ページで使用されているメモリの量を確認します。  
*   メモリ使用量を時間の経過と共に **メモリ** パネルでビジュアル化します。  
*   **ヒープスナップショット**を使用して、デタッチされた DOM ツリー (メモリリークの一般的な原因) を特定します。  
*   新しいメモリが JavaScript ヒープ \ (JS ヒープ) に割り当てられている場合は、 **タイムラインの割り当てインストルメンテーション**で確認できます。  

## 概要  

**鉄道**のパフォーマンスモデルの精神においては、パフォーマンスの取り組みの焦点をユーザーにする必要があります。  

<!--todo: add RAIL section when available  -->  

メモリの問題は、ユーザーによって気が付きされることが多いために重要です。  次の方法で、メモリの問題が発生する可能性があります。  

*   **ページのパフォーマンスが時間の経過と共に悪化**します。  これは、メモリリークの症状である可能性があります。  メモリリークは、ページ内のバグにより、ページが時間の経過と共により多くのメモリをより多く使用している場合に発生します。  
*   **ページのパフォーマンスが一貫して悪く**なります。  これは、メモリの膨張の症状である可能性があります。  メモリの膨張とは、ページが最適なページ速度に必要とするよりも多くのメモリを使用することです。  
*   **ページのパフォーマンスが遅れているか、または頻繁に一時停止するように表示され**ます。  これは、ガベージコレクションが頻繁に発生する可能性が高いと考えられます。  ガベージコレクションは、ブラウザーがメモリを再収集したときに表示されます。  この問題が発生すると、ブラウザーによって決定されます。  コレクション中には、実行中のすべてのスクリプトが一時停止されます。  そのため、ブラウザーが大量にガベージコレクションを実行している場合、スクリプトランタイムはあまり中断されません。  

### メモリ量の増大: "多すぎますか?"  

メモリリークは簡単に定義できます。  サイトでより多くのメモリを使用している場合は、リークが発生しています。  ただし、メモリの膨張は、ピン留めが少し困難です。  "過剰なメモリを使用しています" とは何ですか?  

デバイスやブラウザーによって機能が異なるため、ここでは、ハード番号はありません。  ハイエンドのスマートフォンでスムーズに実行される同じページが、ローエンドのスマートフォンでクラッシュすることがあります。  

ここで重要なのは、鉄道モデルを使用し、ユーザーに焦点を合わせることです。  ユーザーが使用しているデバイスを確認し、それらのデバイスでページをテストします。  エクスペリエンスが一貫して悪い場合は、ページがこれらのデバイスのメモリ機能を超えている可能性があります。  

## Microsoft Edge Browser タスクマネージャーを使用してリアルタイムでメモリ使用量を監視する  

Microsoft Edge ブラウザーのタスクマネージャーを使用して、メモリの問題の調査を開始します。  Microsoft Edge Browser のタスクマネージャーは、ページが現在使用しているメモリの量を示すリアルタイムモニターです。  

1.  `Shift` + `Esc` Microsoft edge のメインメニューをクリックするか、[**その他のツール**] を選択して、  >  **Browser Task Manager** microsoft edge browser のタスクマネージャーを開きます。  
    
    :::image type="complex" source="../media/memory-problems-bing-settings-more-tools-browser-task-manager.msft.png" alt-text="Microsoft Edge Browser のタスクマネージャーを開く" lightbox="../media/memory-problems-bing-settings-more-tools-browser-task-manager.msft.png":::
       図 1: Microsoft Edge ブラウザーのタスクマネージャーを開く  
    :::image-end:::  
    
1.  Microsoft Edge Browser タスクマネージャーのテーブルの見出しにマウスポインターを置いて、コンテキストメニュー \ (右クリック \) を開き、 **JavaScript メモリ**を有効にします。  
    
    :::image type="complex" source="../media/memory-problems-bing-browser-task-manager-javascript-memory.msft.png" alt-text="JavaScript メモリを有効にする" lightbox="../media/memory-problems-bing-browser-task-manager-javascript-memory.msft.png":::
       図 2: JavaScript メモリを有効にする  
    :::image-end:::  
    
この2つの列は、ページがどのようにメモリを使用しているかについて、さまざまなことを示します。  

*   **Memory**列は、ネイティブメモリを表します。  DOM ノードは、ネイティブメモリに格納されます。  この値が増加すると、DOM ノードが作成されます。  
*   **JavaScript メモリ**列は、JS ヒープを表します。  この列には2つの値が含まれています。  目的の値は、実際の番号 \ (かっこで囲まれた数値) です。  実際の番号は、ページ上の到達可能なオブジェクトが使用しているメモリの量を示します。  この数値が増加している場合は、新しいオブジェクトが作成されているか、既存のオブジェクトが増加しています。  

<!--*   live number reference: https://groups.google.com/d/msg/google-chrome-developer-tools/aTMVGoNM0VY/bLmf3l2CpJ8J  -->  

## パフォーマンスパネルを使用したメモリリークの視覚化  

また、パフォーマンスパネルを調査の開始点として使用することもできます。  パフォーマンスパネルを使用すると、時間の経過に伴うページのメモリ使用量をビジュアル化することができます。  

1.  DevTools で [ **パフォーマンス** ] パネルを開きます。  
1.  [ **メモリ** ] チェックボックスをオンにします。  
1.  [レコーディングを作成][DevtoolsEvaluatePerformanceReferenceRecord]します。  

> [!TIP]
> 記録を開始して、強制ガベージコレクションで終了することをお勧めします。  **collect garbage** ![ 記録中にガベージ ][ImageForceGarbageCollectionIcon] コレクションを強制的に実行するには、[ガベージコレクションの強制実行] ボタンを選択します。  

メモリ記録を示すには、次のコードを検討してください。  

```javascript
var x = [];
function grow() {
    for (var i = 0; i < 10000; i++) {
        document.body.appendChild(document.createElement('div'));
    }
    x.push(new Array(1000000).join('x'));
}
document.getElementById('grow').addEventListener('click', grow);
```  

コードで参照されているボタンが押されるたびに、1万 `div` ノードがドキュメントの本文に追加され、100万 `x` 文字の文字列が配列にプッシュされ `x` ます。  前のコードサンプルを実行すると、次の図のような [ **パフォーマンス** ] パネルに記録が生成されます。  

:::image type="complex" source="../media/memory-problems-glitch-example-1-performance-memory.msft.png" alt-text="単純な成長" lightbox="../media/memory-problems-glitch-example-1-performance-memory.msft.png":::
   図 3: 単純な成長  
:::image-end:::  

まず、ユーザーインターフェイスについて説明します。  **概要**ウィンドウの**ヒープ**グラフ \ ( **NET**\) は、JS ヒープを表します。  [ **概要** ] ウィンドウの下には、[ **カウンター** ] ウィンドウがあります。  ここでは、JS ヒープ (**概要**ウィンドウの**ヒープ**グラフと同じ)、ドキュメント、DOM ノード、リスナー、および GPU メモリの使用状況を確認できます。  チェックボックスを無効にすると、グラフから非表示になります。  

これで、前の図と比較したコードの分析が実行されました。  Node カウンター (緑のグラフ \) を見ると、コードに一致していることを確認できます。  個別の手順でノードカウントが増加します。  ノード数が増加すると、がに `grow()` なります。  JS ヒープグラフ \ (青色のグラフ \) は、それほど簡単ではありません。  ベストプラクティスに従うと、最初の dip は、実際には強制的なガベージコレクションです。 (  **ガベージ**コレクションの強制ガベージコレクションボタンを押すと実現 ![ ][ImageForceGarbageCollectionIcon] できます)。  レコーディングの進行に応じて、JS ヒープサイズのスパイクを確認できます。  これは自然であり、予想される結果です。 JavaScript コードは、ボタンを押すたびに DOM ノードを作成し、100万文字の文字列を作成するときに多くの作業を実行します。  ここでの重要なポイントは、JS ヒープの終了日が開始日よりも大きくなります (ここでは、"先頭" は強制ガベージコレクションの後にあります)。  実際の環境では、JS ヒープサイズまたはノードサイズが増加するというパターンが表示された場合、メモリリークが発生する可能性があります。  

<!--todo: the Heap snapshots and Profiles panel are not found in Edge  -->  

## ヒープスナップショットによるデタッチされた DOM ツリーメモリリークの検出  

DOM ノードは、ページ上で実行されている DOM ツリーまたは JavaScript コードからノードへの参照がない場合にのみガベージコレクションされます。  ノードは、DOM ツリーから削除されたときに "デタッチ" されますが、一部の JavaScript ではそのノードを引き続き参照します。  デタッチされた DOM ノードは、メモリリークの一般的な原因です。  このセクションでは、DevTools でのヒーププロファイラーを使って、デタッチされているノードを特定する方法について説明します。  

デタッチされた DOM ノードの簡単な例を次に示します。  

```javascript
var detachedTree;

function create() {
    var ul = document.createElement('ul');
    for (var i = 0; i < 10; i++) {
        var li = document.createElement('li');
        ul.appendChild(li);
    }
    detachedTree = ul;
}
document.getElementById('create').addEventListener('click', create);
```  

コードで参照されているボタンを選ぶと、 `ul` 10 個の子を持つノードが作成され `li` ます。  ノードはコードによって参照されますが、DOM ツリーには存在しないため、それぞれがデタッチされます。  

ヒープスナップショットは、デタッチされたノードを特定する方法の1つです。  名前として、ヒープスナップショットは、スナップショットの時点で、ページの JS オブジェクトと DOM ノードの間でメモリがどのように配分されるかを示しています。  

スナップショットを作成するには、DevTools を開き、[ **メモリ** ] パネルに移動して、[ **ヒープスナップショット** ] ラジオボタンを選択し、[ **スナップショットを撮る** ] ボタンを押します。  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot.msft.png" alt-text="ヒープスナップショットの取得" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot.msft.png":::
   図 4: ヒープスナップショットを撮る  
:::image-end:::  

スナップショットの処理と読み込みに時間がかかる場合があります。  完了したら、左側のパネル \ (名前付き **ヒープスナップショット**) から選択します。  

`Detached`デタッチされた DOM ツリーを検索するには、**クラスフィルター**のテキストボックスに入力します。  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached.msft.png" alt-text="デタッチしたノードのフィルター処理" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached.msft.png":::
   図 5: デタッチしたノードのフィルター処理  
:::image-end:::  

Carats を展開して、デタッチされたツリーを調査します。  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded.msft.png" alt-text="デタッチしたツリーの調査" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded.msft.png":::
   図 6: デタッチしたツリーの調査  
:::image-end:::  

<!--Nodes highlighted yellow have direct references to them from the JavaScript code.  Nodes highlighted red do not have direct references.  They are only alive because they are part of the tree for the yellow node.  In general, you want to focus on the yellow nodes.  Fix your code so that the yellow node is not alive for longer than it needs to be, and you also get rid of the red nodes that are part of the tree for the yellow node.  -->

ノードを選択して、さらに詳しく調べます。  [ **オブジェクト** ] ウィンドウには、参照しているコードに関する詳細情報が表示されます。  たとえば、次の図では、変数がそのノードを参照していることを確認でき `detachedNodes` ます。  この特定のメモリリークを解決するには、変数を使うコードを調べて、不要 `detachedUNode` になったときにノードへの参照が削除されるようにする必要があります。  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded-selected.msft.png" alt-text="ノードの調査" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded-selected.msft.png":::
   図 7: ノードの調査  
:::image-end:::  

<!--todo: the allocation timeline does not appear in the DevTools in Edge  -->  

## タイムライン上の割り当てインストルメンテーションを使用して JS ヒープメモリリークを特定する  

**タイムライン上の割り当てインストルメンテーション** は、JS ヒープのメモリリークを追跡するのに役立つ別のツールです。  

次のコードを使用して、 **タイムラインの割り当てインストルメンテーション**  を示します。  

```javascript
var x = [];
function grow() {
    x.push(new Array(1000000).join('x'));
}
document.getElementById('grow').addEventListener('click', grow);
```  

コードで参照されているボタンが押されるたびに、配列に100万文字の文字列が追加され `x` ます。  

タイムライン上に割り当てインストルメンテーションを記録するには、[DevTools] を開き、[ **メモリ** ] パネルに移動して、[ **タイムライン上の割り当てインストルメンテーション** ] を選びます。次に、[ **スタート** ] ボタンを押して、メモリリークの原因であると思われる操作を実行し、完了したら [ **記録**終了] をクリックし ![ ][ImageStopRecordingIcon] ます。  

記録中に、次の図のように、タイムライン上の割り当てインストルメンテーションで青色のバーが表示されているかどうかを確認します。  

:::image type="complex" source="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-all.msft.png" alt-text="新しい割り当て" lightbox="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-all.msft.png":::
   図 8: 新しい割り当て  
:::image-end:::  

これらの青いバーは、新しいメモリ割り当てを表します。  これらの新しいメモリ割り当ては、メモリリークの候補です。  バーを拡大して、指定した期間内に割り当てられたオブジェクトのみを表示するように、 **コンストラクター** ウィンドウをフィルター処理することができます。  

:::image type="complex" source="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused.msft.png" alt-text="拡大された割り当てタイムライン" lightbox="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused.msft.png":::
   図 9: 割り当てのタイムラインを拡大する  
:::image-end:::  

オブジェクトを展開し、[ **オブジェクト** ] ウィンドウで値を選択して詳細を表示します。  たとえば、次の図では、新しく割り当てられたオブジェクトの詳細を表示することで、スコープ内の変数に割り当てられていることを確認でき `x` `Window` ます。  

:::image type="complex" source="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused-constructor-expanded.msft.png" alt-text="オブジェクトの詳細" lightbox="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused-constructor-expanded.msft.png":::
   図 10: オブジェクトの詳細  
:::image-end:::  

## 関数によるメモリ割り当てを調べる  

**アロケーションサンプリング**プロファイリング型を使って、JavaScript 関数によるメモリ割り当てを表示します。  

:::image type="complex" source="../media/memory-problems-glitch-example-05-memory-allocation-sampling.msft.png" alt-text="レコード割り当てのサンプリング" lightbox="../media/memory-problems-glitch-example-05-memory-allocation-sampling.msft.png":::
   図 11: 割り当てのサンプリングの記録  
:::image-end:::  

1.  [ **割り当てのサンプリング** ] ラジオボタンを選択します。  ページに作業者がいる場合、[ **スタート** ] ボタンの横にあるドロップダウンメニューを使用して、そのユーザーをプロファイリングターゲットとして選ぶことができます。  
1.  [ **スタート** ] ボタンを押します。  
1.  調査するページに対して操作を実行します。  
1.  すべての操作が完了したら、[ **停止** ] ボタンを押します。  

DevTools には、関数によるメモリ割り当ての内訳が表示されます。  既定のビューは **ヘビー (ボトムアップ)** で、最も多くのメモリを割り当てた関数が表示されます。  

:::image type="complex" source="../media/memory-problems-glitch-example-05-memory-allocation-sampling-heavy-bottom-up.msft.png" alt-text="割り当てのサンプリング" lightbox="../media/memory-problems-glitch-example-05-memory-allocation-sampling-heavy-bottom-up.msft.png":::
   図 12: 割り当てのサンプリング  
:::image-end:::  

## 頻繁にガベージコレクションを見つける  

ページが頻繁に一時停止するように見える場合は、ガベージコレクションの問題が発生する可能性があります。  

Microsoft Edge Browser タスクマネージャーまたはパフォーマンスメモリ記録を使って、頻繁にガベージコレクションを見つけることができます。  Microsoft Edge ブラウザータスクマネージャーでは、頻繁に増加している **メモリ** または **JavaScript メモリ** 値がガベージコレクションの頻度を頻繁に表しています。  パフォーマンスの記録では、頻繁な変更 (上昇と下降) から JS ヒープまたはノードカウントグラフは、頻繁なガベージコレクションを示しています。  

問題を特定した後は、 **タイムライン記録での割り当てインストルメンテーション** を使って、メモリが割り当てられている場所と割り当ての原因となっている関数を確認できます。  

<!-- image links -->  

[ImageForceGarbageCollectionIcon]: ../media/collect-garbage-icon.msft.png  
[ImageStopRecordingIcon]: ../media/stop-recording-icon.msft.png  

<!-- links -->  

[DevtoolsEvaluatePerformanceReferenceRecord]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#record-performance "レコードパフォーマンス-パフォーマンス分析のリファレンス"  

<!--[RAIL]: /profile/evaluate-performance/rail  -->
<!--[recording]: /profile/evaluate-performance/timeline-tool#make-a-recording ""  -->  

<!--[hngd]: https://jsfiddle.net/kaycebasques/tmtbw8ef/  -->  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/memory-problems/index) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
