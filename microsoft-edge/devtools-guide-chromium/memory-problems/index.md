---
description: Microsoft Edgeと DevTools を使用して、メモリ リーク、メモリの大きさ、頻繁なガベージ コレクションなど、ページのパフォーマンスに影響するメモリの問題を見つける方法について説明します。
title: メモリの問題を修正する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 3b2405d23dd6ee349484c9ba66d195e3ed12144b
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11565030"
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
# <a name="fix-memory-problems"></a>メモリの問題を修正する  

Microsoft Edgeと DevTools を使用して、メモリ リーク、メモリの大きさ、頻繁なガベージ コレクションなど、ページのパフォーマンスに影響するメモリの問題を見つける方法について説明します。  

### <a name="summary"></a>要約  

*   ブラウザー タスク マネージャーでページが現在使用しているメモリMicrosoft Edge確認します。  
*   [メモリ] パネルを使用して、時間の間にメモリ使用量 **を視覚化** します。  
*   ヒープ スナップショットを使用して、デタッチされた DOM ツリー \(メモリ リークの一般的な原因\) **を特定します**。  
*   タイムライン上の Allocation インストルメンテーションを使用して、JavaScript ヒープ \(JS ヒープ\) で新しいメモリが割り当てられている **場合を確認します**。  

## <a name="overview"></a>概要  

**RAIL**パフォーマンス モデルの精神では、パフォーマンスの取り組みの焦点はユーザーである必要があります。  

<!--todo: add RAIL section when available  -->  

メモリの問題は、ユーザーが認識できる場合が多いので重要です。  ユーザーは、次の方法でメモリの問題を認識する可能性があります。  

*   **ページのパフォーマンスは時間の間に徐々に悪化します**。  これは、メモリ リークの症状である可能性があります。  メモリ リークとは、ページ内のバグによって、ページが時間の間に徐々に多くのメモリを使用する場合です。  
*   **ページのパフォーマンスは一貫して悪いです**。  これは、メモリが大きかった場合に発生する可能性があります。  メモリが大きかったのは、ページが最適なページ速度に必要なメモリを超えるメモリを使用する場合です。  
*   **ページのパフォーマンスが遅れているか、頻繁に一時停止します**。  これは、ガベージ コレクションが頻繁に発生する場合があります。  ガベージ コレクションは、ブラウザーがメモリを再利用する場合です。  ブラウザーは、これがいつ行なうのかを決定します。  コレクション中は、実行中のすべてのスクリプトが一時停止されます。  そのため、ブラウザーがガベージ コレクションを多く行っている場合、スクリプト ランタイムは多くの一時停止を受け取るつもりです。  

### <a name="memory-bloat-how-much-is-too-much"></a>メモリが大きすぎる: どのくらい "多すぎます"?  

メモリ リークは簡単に定義できます。  サイトが徐々に多くのメモリを使用している場合は、リークが発生します。  ただし、メモリが大きくなった場合は、ピン留めするのが少し難しくなります。  「メモリを使いすぎ」と見なす条件は何ですか?  

デバイスやブラウザーによって機能が異なるので、ハード番号はありません。  高級スマートフォンでスムーズに動作するページと同じページが、ローエンド スマートフォンでクラッシュする可能性があります。  

ここで重要なのは、RAIL モデルを使用してユーザーに焦点を当てる方法です。  ユーザーに人気のあるデバイスを確認し、それらのデバイスでページをテストします。  エクスペリエンスが一貫して悪い場合、ページがそれらのデバイスのメモリ機能を超える可能性があります。  

## <a name="monitor-memory-use-in-realtime-with-the-microsoft-edge-browser-task-manager"></a>ブラウザー タスク マネージャーでメモリ使用量をリアルタイムMicrosoft Edge監視する  

メモリの問題Microsoft Edge調査の開始点として、[ブラウザー タスク マネージャー] を使用します。  ブラウザー Microsoft Edgeマネージャーは、ページが現在使用しているメモリの量を示すリアルタイム モニターです。  

1.  メイン `Shift` + `Esc` メニューを選択または移動Microsoft Edge[**** その他のツール] [ブラウザー タスク マネージャー] を選択して、[ブラウザー タスク マネージャー] Microsoft Edge  >  **** 開きます。  
    
    :::image type="complex" source="../media/memory-problems-bing-settings-more-tools-browser-task-manager.msft.png" alt-text="ブラウザー タスク Microsoft Edgeを開く" lightbox="../media/memory-problems-bing-settings-more-tools-browser-task-manager.msft.png":::
       図 1: ブラウザー タスク マネージャー Microsoft Edge開く  
    :::image-end:::  
    
1.  ブラウザー タスク マネージャーのテーブル ヘッダー Microsoft Edgeし、コンテキスト メニュー \(右クリック\) を開き **、JavaScript メモリを有効にします**。  
    
    :::image type="complex" source="../media/memory-problems-bing-browser-task-manager-javascript-memory.msft.png" alt-text="JavaScript メモリを有効にする" lightbox="../media/memory-problems-bing-browser-task-manager-javascript-memory.msft.png":::
       図 2: JavaScript メモリを有効にする  
    :::image-end:::  
    
これら 2 つの列は、ページがメモリを使用している方法について異なる点を示します。  

*   [ **メモリ] 列** は、ネイティブ メモリを表します。  DOM ノードはネイティブ メモリに格納されます。  この値が増えている場合は、DOM ノードが作成されます。  
*   **[JavaScript Memory] 列**は、JS ヒープを表します。  この列には、2 つの値が含まれます。  必要な値は、ライブ番号 \(かっこ内の番号\) です。  ライブ番号は、ページ上の到達可能なオブジェクトが使用しているメモリの量を表します。  この数が増えている場合は、新しいオブジェクトが作成されているか、既存のオブジェクトが増えています。  

<!--*   live number reference: https://groups.google.com/d/msg/google-chrome-developer-tools/aTMVGoNM0VY/bLmf3l2CpJ8J  -->  

## <a name="visualize-memory-leaks-with-performance-panel"></a>[パフォーマンス] パネルでメモリ リークを視覚化する  

また、調査の開始点として [パフォーマンス] パネルを使用することもできます。  [パフォーマンス] パネルを使用すると、ページのメモリ使用量を時間の間に視覚化できます。  

1.  DevTools **の [** パフォーマンス] パネルを開きます。  
1.  [メモリ] **チェック ボックスを** オンにします。  
1.  [録音を行います][DevtoolsEvaluatePerformanceReferenceRecord]。  

> [!TIP]
> 強制ガベージ コレクションを使用して記録を開始および終了する方法をお試しください。  ガベージ コレクションを強制するには、記録中に **[ガベージ**フォース ガベージ コレクション ![ の収集] ][ImageForceGarbageCollectionIcon] ボタンを選択します。  

メモリ記録のデモンストレーションを行う場合は、以下のコードを検討してください。  

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

コードで参照されるボタンが選択されるたび、10,000 ノードがドキュメント本文に追加され、100 万文字の文字列が配列に `div` `x` プッシュ `x` されます。  前のコード サンプルを実行すると、次の図のように **[パフォーマンス** ] パネルに記録が生成されます。  

:::image type="complex" source="../media/memory-problems-glitch-example-1-performance-memory.msft.png" alt-text="単純な成長" lightbox="../media/memory-problems-glitch-example-1-performance-memory.msft.png":::
   図 3: 単純な成長  
:::image-end:::  

最初に、ユーザー インターフェイスについて説明します。  [**概要]** ウィンドウ**** \(NET \の下) の**HEAP**グラフは、JS ヒープを表します。  [概要] **ウィンドウの** 下に [カウンター **] ウィンドウ** があります。  メモリ使用量は、JS ヒープ \(Overview pane\の**HEAP**グラフと同じ)、ドキュメント、DOM ノード、リスナー、GPU メモリによって分解されます。 ****  グラフから非表示にするチェック ボックスをオフにします。  

次に、前の図と比較したコードの分析を行います。  ノード カウンター \(緑のグラフ\) を確認すると、コードと完全に一致します。  ノード数は、個別のステップで増加します。  ノード数が増加するごとに呼び出しである可能性があります `grow()` 。  JS ヒープ グラフ \(青いグラフ\) は、単純ではありません。  ベスト プラクティスに従って、最初のディップは実際には強制ガベージ コレクション \(ガベージ フォース ガベージ コレクション の収集ボタン\**** ![ を選択) ][ImageForceGarbageCollectionIcon] です。  記録が進むにつれて、JS ヒープ サイズのスパイクが表示されます。  これは自然で予想されます。JavaScript コードは、選択したボタンごとに DOM ノードを作成し、100 万文字の文字列を作成するときに多くの作業を行います。  ここでの重要な点は、JS ヒープが開始した \(強制的なガベージ コレクション\の後のポイントである "beginning" ) よりも高く終わるという事実です。  実際には、JS ヒープ サイズまたはノード サイズが増加するパターンを見た場合、メモリ リークが定義される可能性があります。  

<!--todo: the Heap snapshots and Profiles panel are not found in Edge  -->  

## <a name="discover-detached-dom-tree-memory-leaks-with-heap-snapshots"></a>ヒープ スナップショットを使用して、デタッチされた DOM ツリーのメモリ リークを検出する  

DOM ノードは、ページ上で実行されている DOM ツリーまたは JavaScript コードからノードへの参照がない場合にのみガベージ コレクションされます。  ノードは DOM ツリーから削除されると"デタッチ" と言いますが、一部の JavaScript は引き続きそれを参照します。  デタッチされた DOM ノードは、メモリ リークの一般的な原因です。  このセクションでは、DevTools のヒープ プロファイサーを使用して、デタッチされたノードを識別する方法について説明します。  

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

コードで参照されるボタンを選択すると、10 人の子 `ul` を持つノードが作成 `li` されます。  ノードはコードによって参照されますが、DOM ツリーには存在しないので、それぞれが切り離されます。  

ヒープ スナップショットは、デタッチされたノードを識別する 1 つの方法です。  名前が示すように、ヒープ スナップショットは、スナップショットの時点でのページの JS オブジェクトと DOM ノード間のメモリの分散方法を示します。  

スナップショットを作成するには、DevTools を開き、[**** メモリ] パネルに**** 移動し、[スナップショットの取得] ボタンの [ヒープ スナップショット] ラジオ >**選択**します。  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot.msft.png" alt-text="ヒープ スナップショットの取得" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot.msft.png":::
   図 4: ヒープ スナップショットの取得  
:::image-end:::  

スナップショットの処理と読み込みには時間がかかる場合があります。  完了したら、左側のパネル **\(HEAP SNAPSHOTS**\という名前) から選択します。  

[ `Detached` クラス フィルター **] テキスト ボックスに** 入力して、デタッチされた DOM ツリーを検索します。  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached.msft.png" alt-text="デタッチされたノードのフィルター処理" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached.msft.png":::
   図 5: デタッチされたノードのフィルター処理  
:::image-end:::  

カラットを展開して、切り離されたツリーを調査します。  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded.msft.png" alt-text="デタッチされたツリーの調査" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded.msft.png":::
   図 6: デタッチされたツリーの調査  
:::image-end:::  

<!--Nodes highlighted yellow have direct references to them from the JavaScript code.  Nodes highlighted red do not have direct references.  They are only alive because they are part of the tree for the yellow node.  In general, you want to focus on the yellow nodes.  Fix your code so that the yellow node is not alive for longer than it needs to be, and you also get rid of the red nodes that are part of the tree for the yellow node.  -->

さらに調査するノードを選択します。  [オブジェクト **] ウィンドウ** で、参照しているコードの詳細を確認できます。  たとえば、次の図では、変数 `detachedNodes` はノードを参照しています。  特定のメモリ リークを修正するには、変数を使用するコードを調査し、不要になったときにノードへの参照が削除される `detachedUNode` 必要があります。  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded-selected.msft.png" alt-text="ノードの調査" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded-selected.msft.png":::
   図 7: ノードの調査  
:::image-end:::  

<!--todo: the allocation timeline does not appear in the DevTools in Edge  -->  

## <a name="identify-js-heap-memory-leaks-with-allocation-instrumentation-on-timeline"></a>タイムライン上の Allocation インストルメンテーションを使用して JS ヒープ メモリ リークを特定する  

**タイムライン上の割り当て** インストルメンテーションは、JS ヒープ内のメモリ リークを追跡するのに役立つもう 1 つのツールです。  

次の **コードを使用して、タイムラインで割**  り当てインストルメンテーションを示します。  

```javascript
var x = [];
function grow() {
    x.push(new Array(1000000).join('x'));
}
document.getElementById('grow').addEventListener('click', grow);
```  

コードで参照されるボタンがプッシュされるごとに、配列に 100 万文字の文字列が追加 `x` されます。  

割り当てインストルメンテーションをタイムラインに記録するには、DevTools を開き、[メモリ] パネルに移動し****、[タイムライン上の割り当てインストルメンテーション] ラジオ ボタンを選択**** し、[スタート] ボタンを選択し、メモリ リークの原因と思われるアクションを実行し、完了したら [記録ヒープ プロファイルの記録を停止する] ボタンを選択します。 **** **** ![ ][ImageStopRecordingIcon]  

記録中に、次の図のように、タイムラインの Allocation インストルメンテーションに青いバーが表示される場合に注意してください。  

:::image type="complex" source="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-all.msft.png" alt-text="新しい割り当て" lightbox="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-all.msft.png":::
   図 8: 新しい割り当て  
:::image-end:::  

これらの青いバーは、新しいメモリ割り当てを表します。  これらの新しいメモリ割り当ては、メモリ リークの候補です。  バーを拡大してコンストラクター ウィンドウをフィルター処理して****、指定した期間に割り当てられたオブジェクトのみを表示できます。  

:::image type="complex" source="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused.msft.png" alt-text="拡大された割り当てタイムライン" lightbox="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused.msft.png":::
   図 9: 拡大割り当てのタイムライン  
:::image-end:::  

オブジェクトを展開し、値を選択して、[オブジェクト] ウィンドウに詳細を **表示** します。  たとえば、次の図では、新しく割り当てられたオブジェクトの詳細で、スコープ内の変数に割り当 `x` てられたかどうかを示 `Window` します。  

:::image type="complex" source="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused-constructor-expanded.msft.png" alt-text="オブジェクトの詳細" lightbox="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused-constructor-expanded.msft.png":::
   図 10: オブジェクトの詳細  
:::image-end:::  

## <a name="investigate-memory-allocation-by-function"></a>関数別にメモリ割り当てを調査する  

割り **当てサンプリング プロファイル** の種類を使用して、JavaScript 関数によるメモリ割り当てを表示します。  

:::image type="complex" source="../media/memory-problems-glitch-example-05-memory-allocation-sampling.msft.png" alt-text="レコードの割り当てサンプリング" lightbox="../media/memory-problems-glitch-example-05-memory-allocation-sampling.msft.png":::
   図 11: レコード割り当てサンプリング  
:::image-end:::  

1.  [割り当 **てサンプリング] ラジオ ボタン** を選択します。  ページにワーカーが表示されている場合は、[スタート] ボタンの横にあるドロップダウン メニューを使用して、プロファイル **ターゲットとして選択** できます。  
1.  [スタート] **ボタンを選択** します。  
1.  調査する Web ページのアクションを完了します。  
1.  すべての操作 **が完了** したら、[停止] ボタンを選択します。  

DevTools は、関数別のメモリ割り当ての内訳を示します。  既定のビューは **Heavy (Bottom Up)** で、最もメモリが割り当てられた関数が上部に表示されます。  

:::image type="complex" source="../media/memory-problems-glitch-example-05-memory-allocation-sampling-heavy-bottom-up.msft.png" alt-text="割り当てサンプリング" lightbox="../media/memory-problems-glitch-example-05-memory-allocation-sampling-heavy-bottom-up.msft.png":::
   図 12: 割り当てサンプリング  
:::image-end:::  

## <a name="spot-frequent-garbage-collections"></a>頻繁なガベージ コレクションを見つける  

ページが頻繁に一時停止する場合は、ガベージ コレクションの問題が発生する可能性があります。  

ブラウザー タスク マネージャーまたはパフォーマンス メモリMicrosoft Edgeを使用して、頻繁なガベージ コレクションを見つける方法があります。  ブラウザー タスク Microsoft Edgeでは、頻繁にメモリまたは**JavaScript** **** メモリの値が上昇および低下し、ガベージ コレクションが頻繁に発生します。  パフォーマンスの記録では、JS ヒープまたはノード 数グラフへの頻繁な変更 \(立ち上がりおよび立ち下がり\) は、頻繁なガベージ コレクションを示します。  

問題を特定した後、タイムラインの記録で Allocation イン**** ストルメンテーションを使用して、メモリが割り当てられている場所と割り当てを引き起こしている関数を確認できます。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageForceGarbageCollectionIcon]: ../media/collect-garbage-icon.msft.png  
[ImageStopRecordingIcon]: ../media/stop-recording-icon.msft.png  

<!-- links -->  

[DevtoolsEvaluatePerformanceReferenceRecord]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#record-performance "レコードのパフォーマンス - パフォーマンス分析リファレンス"  

<!--[RAIL]: /profile/evaluate-performance/rail  -->
<!--[recording]: /profile/evaluate-performance/timeline-tool#make-a-recording ""  -->  

<!--[hngd]: https://jsfiddle.net/kaycebasques/tmtbw8ef/  -->  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/memory-problems/index) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
