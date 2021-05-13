---
description: DevTools でパフォーマンスを記録および分析するためのすべての方法Microsoft Edge参照。
title: パフォーマンス分析リファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 5cd7c4aee6eb5f0c48f783e250efa1ef69010fc4
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564351"
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
# <a name="performance-analysis-reference"></a>パフォーマンス分析リファレンス  

このページは、パフォーマンスの分析に関連Microsoft Edge DevTools 機能の包括的なリファレンスです。  

[DevTools][MicrosoftEdgeDevTools][はじめに][DevtoolsEvaluatePerformanceGettingStarted]を使用してページのパフォーマンスを分析する方法に関するガイド付きチュートリアルについては、「ランタイム パフォーマンスの分析」に移動Microsoft Edgeします。  

## <a name="record-performance"></a>レコードのパフォーマンス  

### <a name="record-runtime-performance"></a>実行時のパフォーマンスを記録する  

読み込みではなく、実行中のページのパフォーマンスを分析する場合は、実行時のパフォーマンスを記録します。  

1.  分析するページに移動します。  
1.  DevTools **で** パフォーマンス ツールを開きます。  
1.  **[Record** \( Record icon ![ ](../media/record-icon.msft.png) \] を選択します)。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-record-highlight.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-record-highlight.msft.png":::
       **Record**  
    :::image-end:::  
    
1.  ページを操作します。  DevTools は、操作の結果として発生するページアクティビティを記録します。  
1.  もう一 **度 [録音]** を選択するか、[ **停止] を選択して** 記録を停止します。  
    
### <a name="record-load-performance"></a>レコードの読み込みパフォーマンス  

実行中ではなく、読み込み中にページのパフォーマンスを分析する場合は、読み込みパフォーマンスを記録します。  

1.  分析するページに移動します。  
1.  DevTools **の** [パフォーマンス] パネルを開きます。  
1.  [更新 **] ページ** \( Refresh Page ![ ](../media/refresh-page-icon.msft.png) \) を選択します。  DevTools は、ページの更新中にパフォーマンス 指標を記録し、読み込み完了から数秒後に自動的に記録を停止します。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-refresh-button.msft.png" alt-text="[更新] ページ" lightbox="../media/evaluate-performance-performance-refresh-button.msft.png":::
       **[更新] ページ**  
    :::image-end:::  
    
DevTools は、ほとんどのアクティビティが発生した記録部分を自動的に拡大表示します。  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed.msft.png" alt-text="ページ読み込み記録" lightbox="../media/evaluate-performance-performance-refreshed.msft.png":::
   ページ読み込み記録  
:::image-end:::  

### <a name="capture-screenshots-while-recording"></a>記録中にスクリーンショットをキャプチャする  

[スクリーンショット] チェック **ボックスをオン** にすると、記録中にすべてのフレームのスクリーンショットがキャプチャされます。  

:::image type="complex" source="../media/evaluate-performance-performance-capture-screenshots-checkbox.msft.png" alt-text="[スクリーンショット] チェック ボックス" lightbox="../media/evaluate-performance-performance-capture-screenshots-checkbox.msft.png":::
   [ **スクリーンショット] チェック** ボックス  
:::image-end:::  

[スクリーンショット [の表示] に移動](#view-a-screenshot) して、スクリーンショットを操作する方法を確認します。  

### <a name="force-garbage-collection-while-recording"></a>記録中にガベージ コレクションを強制する  

ページの記録中に、[ガベージを収集 **する]** \( ガベージ アイコン \) を選択してガベージ コレクション ![ ](../media/collect-garbage-icon.msft.png) を強制します。  

:::image type="complex" source="../media/evaluate-performance-performance-collect-garbage-button.msft.png" alt-text="ガベージの収集" lightbox="../media/evaluate-performance-performance-collect-garbage-button.msft.png":::
   ガベージの収集  
:::image-end:::  

### <a name="show-recording-settings"></a>記録設定を表示する  

DevTools **がパフォーマンス** 記録をキャプチャする方法に関連するその他の設定を公開するには、[ ![ キャプチャ設定 ](../media/capture-settings-icon.msft.png) \( Capture settings \) を選択します。  

:::image type="complex" source="../media/evaluate-performance-performance-capture-settings-button-open-drawer.msft.png" alt-text="[キャプチャ設定] セクション" lightbox="../media/evaluate-performance-performance-capture-settings-button-open-drawer.msft.png":::
   [**キャプチャ設定]** セクション  
:::image-end:::  

### <a name="disable-javascript-samples"></a>JavaScript サンプルを無効にする  

既定では、レコーディング **のメイン セクション** には、レコーディング中に呼び出された JavaScript 関数の詳細な呼び出し履歴が表示されます。  これらの呼び出し履歴を無効にするには、次の手順を実行します。  

1.  [キャプチャ設定 **] メニューを開** きます。  [記録設定 [の表示] に移動します](#show-recording-settings)。  
1.  [JavaScript サンプルを **無効にする] チェック ボックスをオン** にします。  
1.  ページの記録を取ります。  
    
次の 2 つの図は、JavaScript サンプルの無効化と有効化の違いを示しています。  録音 **の** Main セクションは、すべての JavaScript 呼び出しスタックを省略しますので、サンプリングが無効になっている場合にはるかに短くなります。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-on.msft.png" alt-text="JS サンプルが無効になっている場合の記録の例" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-on.msft.png":::
         JS サンプルが無効になっている場合の記録の例  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off.msft.png" alt-text="JS サンプルを有効にした場合の記録の例" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off.msft.png":::
         JS サンプルを有効にした場合の記録の例  
      :::image-end:::  
   :::column-end:::
:::row-end:::

### <a name="throttle-the-network-while-recording"></a>記録中にネットワークを調整する  

記録中にネットワークを調整するには、次の操作を行います。  

1.  [キャプチャ設定 **] メニューを開** きます。  [記録設定 [の表示] に移動します](#show-recording-settings)。  
1.  ネットワーク **を** 調整の目的のレベルに設定します。  
    
### <a name="throttle-the-cpu-while-recording"></a>記録中に CPU を調整する  

記録中に CPU を調整するには、次の操作を行います。  

1.  [キャプチャ設定 **] メニューを開** きます。  [記録設定 [の表示] に移動します](#show-recording-settings)。  
1.  **CPU を**調整の目的のレベルに設定します。  
    
調整は、コンピューターの機能を基準にしています。  たとえば **、2 倍のスローダウン オプションを使用** すると、CPU の動作は通常の 2 倍遅くなります。  DevTools は、モバイル デバイスのアーキテクチャがデスクトップやラップトップのアーキテクチャと大違いなので、モバイル デバイスの CPU を実際にシミュレートする必要があります。  

### <a name="turn-on-advanced-paint-instrumentation"></a>高度なペイントインストルメンテーションを有効にする  

ペイントインストルメンテーションの詳細を表示するには、次の手順を実行します。  

1.  [キャプチャ設定 **] メニューを開** きます。  [記録設定 [の表示] に移動します](#show-recording-settings)。  
1.  [高度な **ペイントインストルメンテーションを有効にする (低速)] チェック ボックスをオン** にします。  

ペイント情報を操作する方法については、「レイヤーの表示」[](#view-layers-information)と「ペイント プロファイラーの表示[」に移動します](#view-paint-profiler)。  

## <a name="save-a-recording"></a>録音を保存する  

記録を保存するには、コンテキスト メニュー \(右クリック\) を開き、[プロファイルの保存] **を選択します**。  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-save-profile.msft.png" alt-text="プロファイルの保存" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-save-profile.msft.png":::
   **プロファイルの保存**  
:::image-end:::  

## <a name="load-a-recording"></a>レコーディングを読み込む  

記録を読み込むには、コンテキスト メニュー \(右クリック\) を開き、[プロファイルの読み込み] **を選択します**。  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-load-profile.msft.png" alt-text="プロファイルの読み込み" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-load-profile.msft.png":::
   **プロファイルの読み込み**  
:::image-end:::  

## <a name="clear-the-previous-recording"></a>前の記録をクリアする  

録音を行った後、[記録を **クリアする** ]\( [録音のクリア] アイコン \) を選択して、[パフォーマンス] パネルからその ![ ](../media/clear-recording-icon.msft.png) 録音を **クリア** します。  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-clear-button.msft.png" alt-text="録音のクリア" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-clear-button.msft.png":::
   **録音のクリア**  
:::image-end:::  

## <a name="analyze-a-performance-recording"></a>パフォーマンス記録を分析する  

実行時の[パフォーマンスまたはレコードの](#record-runtime-performance)[読み](#record-load-performance)込みパフォーマンス**** を記録した後、パフォーマンス パネルには、発生した処理のパフォーマンスを分析するための多くのデータが表示されます。  

### <a name="select-a-portion-of-a-recording"></a>録音の一部を選択する  

マウスを [概要] の左または右に **ドラッグして** 、録音の一部を選択します。  Overview**は****、FPS、CPU、および** **NET**グラフを含む**セクション**です。  

:::image type="complex" source="../media/evaluate-performance-performance-zoom-highlighted.msft.png" alt-text="ズームするには、概要の上にマウスをドラッグします" lightbox="../media/evaluate-performance-performance-zoom-highlighted.msft.png":::
   ズームするには、概要の上に **マウスを** ドラッグします  
:::image-end:::  

キーボードを使用して部分を選択するには、次の操作を行います。  

1.  [メイン] セクションの**背景**を選択するか、その横にある [インタラクション] 、[ネットワーク] 、**または [GPU]** などの**セクションを選択**します。 ****  このキーボード ワークフローは、これらのセクションの 1 つがフォーカスされている場合にのみ機能します。  
1.  、 、 キーを使用して、それぞれ拡大、左、縮小、 `W` `A` `S` `D` 右に移動します。  

トラックパッドを使用して部分を選択するには、次のアクションを実行します。  

1.  [概要] セクションまたは [詳細] **セクション** の上にマウスポインター **を移動** します。  [ **概要** ] セクションは **、FPS、CPU、および** **NET**グラフを含む **領域** です。  [ **詳細]** セクションは、[メイン] セクション、[ **操作** ] セクションを **含む領域** です。  
1.  2 本の指を使用して、上にスワイプして縮小し、左にスワイプして左に移動し、下にスワイプして拡大し、右にスワイプして右に移動します。  

[メイン] セクションまたは隣接する**** 任意の領域で長いフレーム グラフをスクロールするには、上下にドラッグしながら長押しします。  左右にドラッグして、選択した録音部分を移動します。  

### <a name="search-activities"></a>検索アクティビティ  

`Control` + `F` \(Windows、Linux\) または `Command` + `F` \(macOS\)**** を選択して、[パフォーマンス] パネルの下部にある検索ボックスを開きます。  

:::image type="complex" source="../media/evaluate-performance-performance-search-regex.msft.png" alt-text="検索ボックス" lightbox="../media/evaluate-performance-performance-search-regex.msft.png":::
   検索ボックス  
:::image-end:::  

クエリに一致するアクティビティを移動するには、次の操作を行います。  

*   [前 **の** \( ![ 前 ](../media/previous-icon.msft.png) の \) ] ボタンと [ **次** へ] \( ![ Next ](../media/next-icon.msft.png) \) ボタンを使用します。  
*   前 `Shift` + `Enter` の項目を選択するか、次 `Enter` の項目を選択します。  

クエリ設定を変更するには、次のコマンドを実行します。  

*   クエリ **で大文字と** 小文字を区別するには、[大文字と小文字を区別 ![ ](../media/search-case-icon.msft.png) する]を選択します。  
*   クエリ **で正規表現** を ![ ](../media/search-regex-icon.msft.png) 使用するには、Regex \( Regex \) を選択します。  

検索ボックスを非表示にする場合は、[キャンセル] を **選択します**。  

### <a name="view-main-thread-activity"></a>メイン スレッドアクティビティの表示  

[メイン] **セクション** を使用して、ページのメイン スレッドで発生したアクティビティを表示します。  

:::image type="complex" source="../media/evaluate-performance-performance-main-zoomed.msft.png" alt-text="[メイン] セクション" lightbox="../media/evaluate-performance-performance-main-zoomed.msft.png":::
   [ **メイン]** セクション  
:::image-end:::  

イベントを選択すると、[概要] パネルにイベントの詳細 **が表示** されます。  DevTools は、選択したイベントの概要を示します。  

:::image type="complex" source="../media/evaluate-performance-performance-summary-me.msft.png" alt-text="[概要] パネルの匿名関数の詳細" lightbox="../media/evaluate-performance-performance-summary-me.msft.png":::
   [概要] パネル `anonymous` の関数**の詳細**  
:::image-end:::  

DevTools は、フレーム グラフを使用したメイン スレッド アクティビティを表します。  x 軸は、時間の間の記録を表します。  y 軸は呼び出し履歴を表します。  上のイベントは、その下のイベントを引き起こします。  

:::image type="complex" source="../media/evaluate-performance-performance-main-flame-chart.msft.png" alt-text="炎のグラフ" lightbox="../media/evaluate-performance-performance-main-flame-chart.msft.png":::
   炎のグラフ  
:::image-end:::  

前の図では、イベント `click` によって `Function Call` 53 行目に `activitytabs.js` in が発生しました。  以下 `Function Call` に、匿名関数が実行されたと確認します。  要求された 、要求 `a` された匿名 `wait` 関数 `Minor GC` 。  

DevTools はスクリプトにランダムな色を割り当てる。  前の図では、1 つのスクリプトからの関数要求は淡緑色です。  別のスクリプトからの要求は、色はベージュです。  濃い黄色はスクリプト アクティビティを表し、紫色のイベントはレンダリング アクティビティを表します。  これらの濃い黄色と紫色のイベントは、すべての録音で一貫しています。  

JavaScript [要求の詳細な](#disable-javascript-samples) フレーム グラフを非表示にする場合は、[JavaScript サンプルを無効にする] に移動します。  JS サンプルが無効になっている場合は、前の図のような高レベルの `Event: choose` `Function Call` イベントだけが表示 `str` されます。  

### <a name="view-activities-in-a-table"></a>テーブル内のアクティビティを表示する  

ページを記録した後は、アクティビティを分析するために[ **メイン** ] セクションのみに依存する必要があります。  DevTools には、アクティビティを分析するための 3 つの表形式ビューも用意されています。  各ビューでは、アクティビティについて異なる視点を示します。  

*   最も作業の原因となるルート アクティビティを表示する場合は、[呼び出しツリー] [パネルを使用](#the-call-tree-panel) します。  
*   最も多くの時間が直接費やされたアクティビティを表示する場合は、ボトム [アップ パネルを使用](#the-bottom-up-panel) します。  
*   記録中にアクティビティが発生した順序で表示する場合は、[イベント ログ] パネル [を使用](#the-event-log-panel) します。  
    
> [!NOTE]
> 次の 3 つのセクションはすべて同じデモを参照します。  アクティビティ タブのデモでデモ [を自分で実行します][ActivityTabsDemo]。  

#### <a name="root-activities"></a>ルート アクティビティ  

ここでは、コール ツリー**パネル、ボトム**アップ パネル、および**** イベント ログ**** パネルに記載されているルート アクティビティの概念**について説明**します。  

ルート アクティビティは、ブラウザーが何らかの作業を行う原因となるアクティビティです。  たとえば、Web ページを選択すると、ブラウザーはルート `Event` アクティビティとしてアクティビティを実行します。  そのため `Event` 、ハンドラーが実行される可能性があります。  

[メイン] セクションのフレーム **グラフでは** 、ルート アクティビティはグラフの上部に表示されます。  [呼 **び出しツリー]** **パネルと [イベント ログ] パネル** では、ルート アクティビティがトップ レベルのアイテムです。  

ルート アクティビティ [の例については、[呼び](#the-call-tree-panel) 出しツリー] パネルに移動します。  

#### <a name="the-call-tree-panel"></a>[呼び出しツリー] パネル  

[呼び **出しツリー] パネル** を使用して、最 [も多くの作業を引き起](#root-activities) こすルート アクティビティを表示します。  

[ **呼び出しツリー]** パネルには、録音の選択した部分の間にのみアクティビティが表示されます。  [録音の [一部を選択する] に](#select-a-portion-of-a-recording) 移動して、部分を選択する方法について学習します。  

:::image type="complex" source="../media/evaluate-performance-performance-call-tree.msft.png" alt-text="[呼び出しツリー] パネル" lightbox="../media/evaluate-performance-performance-call-tree.msft.png":::
   [ **呼び出しツリー]** パネル  
:::image-end:::  

前の図では、[アクティビティ] 列のアイテムのトップ**** レベル (ルート アクティビティなど) `Evaluate Script` `Parse HTML` を示します。  入れ子は呼び出し履歴を表します。  たとえば、前の図では、 `Parse HTML` 原因と原因が `Evaluate Script` `Compile Script` . `(anonymous)`  

**Self Time は** 、そのアクティビティに直接費やされた時間を表します。  **[合計時間** ] は、そのアクティビティまたはすべての子で費やされた時間を表します。  

[**自己時間]、[****合計時間]、** または [**アクティビティ]** を選択して、その列でテーブルを並べ替える。  

[フィルター] **テキスト ボックス** を使用して、アクティビティ名でイベントをフィルター処理します。  

既定では、[ **グループ化] メニュー** は [グループ化なし **] に設定されています**。  [グループ **化] メニューを使用** して、さまざまな条件に基づいてアクティビティ テーブルを並べ替える。  

[ **最も重いスタック** \( 最も重いスタック \を表示する] を選択して、アクティビティ テーブルの右側に別のテーブル ![ ](../media/show-heaviest-stack-icon.msft.png) を **表示** します。  最も重いスタック テーブルを設定 **するアクティビティを選択** します。  [ **最も重いスタック]** テーブルには、選択したアクティビティの子の実行に最も時間がかかった時間が表示されます。  

#### <a name="the-bottom-up-panel"></a>[Bottom-Up] パネル  

ボトムアップ **パネルを使用して** 、集計で最も時間がかかったアクティビティを直接表示します。  

ボトム **アップ パネルには、** 記録の選択した部分の間にのみアクティビティが表示されます。  [録音の [一部を選択する] に](#select-a-portion-of-a-recording) 移動して、部分を選択する方法について学習します。  

:::image type="complex" source="../media/evaluate-performance-performance-bottoms-up.msft.png" alt-text="[Bottom-Up] パネル" lightbox="../media/evaluate-performance-performance-bottoms-up.msft.png":::
   [ **ボトムアップ]** パネル  
:::image-end:::  

前の **図のメイン** セクションのフレーム グラフで、ほとんどすべての時間が実行に費やされた状態に移動します `Parse HTML` 。  前の図の **ボトムアップ パネルの** トップ アクティビティはです `Parse HTML` 。  <!--In the flame chart of the previous figure, the yellow below the calls to `wait` are actually thousands of `Minor GC` calls.  -->  [ボトムアップ] **パネルに移動** します。次に最も高価なアクティビティは `Layout` です。  

[Self **Time]** 列は、すべての発生回数にわたって、そのアクティビティに直接費やされた集計時間を表します。  

[ **合計時間]** 列は、そのアクティビティまたは子の合計時間を表します。  

#### <a name="the-event-log-panel"></a>[イベント ログ] パネル  

[イベント **ログ] パネル** を使用して、記録中にアクティビティが発生した順序でアクティビティを表示します。  

[ **イベント ログ] パネル** には、記録の選択した部分の間にのみアクティビティが表示されます。  [録音の [一部を選択する] に](#select-a-portion-of-a-recording) 移動して、部分を選択する方法について学習します。  

:::image type="complex" source="../media/evaluate-performance-performance-event-log.msft.png" alt-text="[イベント ログ] パネル" lightbox="../media/evaluate-performance-performance-event-log.msft.png":::
   [ **イベント ログ]** パネル  
:::image-end:::  

[ **開始時刻]** 列は、記録の開始位置を基準として、そのアクティビティが開始されたポイントを表します。  たとえば、前の図の選択したアイテムの開始時刻は、記録の開始後 `175.7 ms` にアクティビティが 175.7 ミリ秒を開始したという意味です。  

[Self **Time]** 列は、そのアクティビティに直接費やされた時間を表します。  

[ **合計時間]** 列は、そのアクティビティまたは子の中で直接費やされた時間を表します。  

[**開始時刻]、[****自己時間]、** または [**合計**時間] を選択して、その列でテーブルを並べ替える。

[フィルター] **テキスト ボックス** を使用して、アクティビティを名前でフィルター処理します。  

[期間 **] メニューを** 使用して、1 ミリ秒未満または 15 ミリ秒未満のアクティビティをフィルター処理します。  既定では、[ **期間] メニュー** は [すべて] に **設定**され、すべてのアクティビティが表示されます。  

これらのカテゴリ**からすべての**アクティビティ**をフィルター処理**するには、[**** 読み込み **]、[スクリプト]、[レンダリング**]、または [ペイント] チェック ボックスを無効にします。  

### <a name="view-gpu-activity"></a>GPU アクティビティの表示  

[GPU] セクションで GPU アクティビティ **を表示** します。  

:::image type="complex" source="../media/evaluate-performance-performance-gpu-zoomed.msft.png" alt-text="[GPU] セクション" lightbox="../media/evaluate-performance-performance-gpu-zoomed.msft.png":::
   **[GPU]** セクション  
:::image-end:::  

### <a name="view-raster-activity"></a>ラスター アクティビティの表示  

[ラスター] セクションでラスター アクティビティ **を表示** します。  

:::image type="complex" source="../media/evaluate-performance-performance-raster.msft.png" alt-text="[ラスター] セクション" lightbox="../media/evaluate-performance-performance-raster.msft.png":::
   [ **ラスター]** セクション  
:::image-end:::  

### <a name="view-interactions"></a>操作の表示  

[操作 **] セクションを** 使用して、記録中に発生したユーザー操作を検索して分析します。  

:::image type="complex" source="../media/evaluate-performance-performance-interactions-animation.msft.png" alt-text="[対話] セクション" lightbox="../media/evaluate-performance-performance-interactions-animation.msft.png":::
   [ **対話]** セクション  
:::image-end:::  

操作の下部にある赤い線は、メイン スレッドの待機に費やされた時間を表します。  

操作を選択して、その詳細を [概要] パネル **に表示** します。  

### <a name="analyze-frames-per-second-fps"></a>1 秒あたりのフレーム数の分析 (FPS)  

DevTools には、1 秒あたりのフレーム数を分析するさまざまな方法があります。  

*   FPS [グラフを使用して](#the-fps-chart) 、記録期間中の FPS の概要を取得します。  
*   [ [フレーム] セクションを使用](#the-frames-section) して、特定のフレームにかかった時間を表示します。  
*   ページの **実行時に、FPS** のリアルタイム推定値として FPS メーターを使用します。  FPS メーターを [使用してリアルタイムで 1 秒あたりのフレーム数を表示するに移動します](#view-frames-per-second-in-realtime-with-the-fps-meter)。  
    
#### <a name="the-fps-chart"></a>FPS グラフ  

**FPS グラフ**は、記録期間中のフレーム レートの概要を示します。  一般に、緑のバーが大きいほど、フレーム レートが向上します。  

FPS グラフの上の **赤い** バーは、フレーム レートが低く低下し、ユーザーのエクスペリエンスに害を与えた可能性があるという警告です。  

:::image type="complex" source="../media/evaluate-performance-performance-fps-highlight.msft.png" alt-text="FPS グラフ" lightbox="../media/evaluate-performance-performance-fps-highlight.msft.png":::
   **FPS グラフ**  
:::image-end:::  

#### <a name="the-frames-section"></a>[フレーム] セクション  

[ **フレーム]** セクションでは、特定のフレームにかかった時間を正確に示します。  

フレームにマウス ポインターを合わせると、ヒントに関する詳細が表示されます。  

:::image type="complex" source="../media/evaluate-performance-performance-frames-hover.msft.png" alt-text="フレームにカーソルを合わせる" lightbox="../media/evaluate-performance-performance-frames-hover.msft.png":::
   フレームにカーソルを合わせる  
:::image-end:::  

[概要] パネルでフレームの詳細を表示するには、フレーム **を選択** します。  DevTools は、選択したフレームの輪郭を青で示します。  

:::image type="complex" source="../media/evaluate-performance-performance-frames-summary.msft.png" alt-text="[概要] パネルでフレームを表示する" lightbox="../media/evaluate-performance-performance-frames-summary.msft.png":::
   [概要] パネルでフレーム **を表示** する  
:::image-end:::  

### <a name="view-network-requests"></a>ネットワーク要求の表示  

[ネットワーク **] セクションを** 展開して、記録中に発生したネットワーク要求のウォーターフォールを表示します。  

:::image type="complex" source="../media/evaluate-performance-performance-network.msft.png" alt-text="[ネットワーク] セクション" lightbox="../media/evaluate-performance-performance-network.msft.png":::
   [ **ネットワーク]** セクション  
:::image-end:::  

要求は、次のように色分けされています。  

*   HTML: 青  
*   CSS: Purple  
*   JS: 黄色  
*   画像: 緑  
    
要求を選択して、その詳細を [概要] パネル **で表示** します。  たとえば、前の図では、[概要]**** パネルに、[ネットワーク] セクションで選択されている青色の要求に関する詳細が**表示**されています。  

要求の左上の濃い青色の四角形は、優先度の高い要求を意味します。  明るい青の四角形は優先度の低い四角形を意味します。  たとえば、前の図では、青色の選択された要求の優先度が高く、下の緑色の要求は優先度が低くなります。  

次の図の 1st では、要求は左側の行、中央に濃い部分と明るい部分を持つバー、右側の線で表 `www.bing.com` されます。  次の図の 2nd では、ネットワーク ツールのタイミング パネルに同**** じ要求の対応する表現を**示**します。  これら 2 つの表現が互いにマップされる方法を次に示します。

*   左側の行は、イベントのグループまでの `Connection Start` すべてです。すべて含まれています。  言い換えれば、前のすべてです `Request Sent` 。排他的です。  
*   バーの明るい部分は `Request Sent` 、 です `Waiting (TTFB)` 。  
*   バーの暗い部分はです `Content Download` 。  
*   正しい行は、基本的にメイン スレッドの待機に費やされた時間です。  これは、[タイミング] パネルでは **表** されません。  
    
:::row:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-bing-performance-network.msft.png" alt-text="要求の行バー www.bing.com 表示" lightbox="../media/evaluate-performance-bing-performance-network.msft.png":::
         要求の行バー `www.bing.com` 表現  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-bing-network-timing.msft.png" alt-text="ネットワーク ツール" lightbox="../media/evaluate-performance-bing-network-timing.msft.png":::
         ネットワーク**ツール**  
: ::image-end:::  
   :::column-end:::
:::row-end:::

### <a name="view-memory-metrics"></a>メモリ メトリックを表示する  

[メモリ] チェック **ボックスを** オンにすると、前回の記録のメモリ メトリックスが表示されます。  

:::image type="complex" source="../media/evaluate-performance-performance-memory-highlight.msft.png" alt-text="[メモリ] チェック ボックス" lightbox="../media/evaluate-performance-performance-memory-highlight.msft.png":::
   [ **メモリ]** チェック ボックス  
:::image-end:::  

DevTools は、[概要] **パネルの上** に新しいメモリ グラフ **を表示** します。  NET グラフの下には **、HEAP** と呼ばれる新しいグラフ **があります**。  **HEAP グラフ**は、メモリ グラフの**JS ヒープ**行と同じ情報を**提供**します。  

:::image type="complex" source="../media/evaluate-performance-performance-memory-chart.msft.png" alt-text="メモリ メトリック" lightbox="../media/evaluate-performance-performance-memory-chart.msft.png":::
   メモリ メトリック  
:::image-end:::  

グラフの色付き線は、グラフの上の色付きチェック ボックスにマップされます。  
グラフからそのカテゴリを非表示にするには、チェック ボックスを無効にします。  

グラフには、現在選択されている記録の領域だけが表示されます。  たとえば、前の図では、メモリ**** グラフは 400 ミリ秒のマークから 1750 ミリ秒のマークの周りのメモリ使用量のみを示しています。  

### <a name="view-the-duration-of-a-portion-of-a-recording"></a>記録の一部の期間を表示する  

Network や**Main****** などのセクションを分析する場合、特定のイベントにかかった時間の正確な推定値が必要な場合があります。  録音 `Shift` の一部を選択するには、長押し、左または右にドラッグします。  選択内容の下部に、DevTools はその部分にかかった時間を示します。  

:::image type="complex" source="../media/evaluate-performance-performance-main-duration.msft.png" alt-text="記録の一部の期間を表示する" lightbox="../media/evaluate-performance-performance-main-duration.msft.png":::
   記録の一部の期間を表示する  
:::image-end:::  

### <a name="view-a-screenshot"></a>スクリーンショットの表示  

[記録中 [にスクリーンショットをキャプチャ](#capture-screenshots-while-recording) する] に移動して、スクリーンショットを有効にする方法を確認します。  

[概要] **にカーソル** を合わせると、記録中にページがどのように表示されたのかのスクリーンショットが表示されます。  概要**は**、CPU、FPS、および**NET****** グラフを含む**セクション**です。  

:::image type="complex" source="../media/evaluate-performance-performance-screenshots-hover.msft.png" alt-text="スクリーンショットの表示" lightbox="../media/evaluate-performance-performance-screenshots-hover.msft.png":::
   スクリーンショットの表示  
:::image-end:::  

[フレーム] セクションでフレームを選択してスクリーンショットを **表示** することもできます。  DevTools は、[概要] パネルに小さなバージョンの **スクリーンショットを表示** します。  

:::image type="complex" source="../media/evaluate-performance-performance-summary-preview.msft.png" alt-text="[概要] パネルでスクリーンショットを表示する" lightbox="../media/evaluate-performance-performance-summary-preview.msft.png":::
   [概要] パネルでスクリーンショット **を表示** する  
:::image-end:::  

[概要] パネルでサムネイル **を選択** して、スクリーンショットを拡大します。  

:::image type="complex" source="../media/evaluate-performance-performance-summary-preview-select.msft.png" alt-text="[概要] パネルからスクリーンショットを拡大する" lightbox="../media/evaluate-performance-performance-summary-preview-select.msft.png":::
   [概要] パネルからスクリーンショット **を拡大** する  
:::image-end:::  

### <a name="view-layers-information"></a>レイヤー情報の表示  

フレームに関する高度なレイヤー情報を表示するには、次の方法を使用します。  

1.  [高度なペイントインストルメンテーションを有効にする](#turn-on-advanced-paint-instrumentation)。  
1.  [フレーム] セクションでフレーム **を選択** します。  DevTools は、新しい [レイヤー]**** パネルの [イベント ログ] パネルの横に、レイヤーに関する**情報を表示**します。  
    
    :::image type="complex" source="../media/evaluate-performance-layers-all.msft.png" alt-text="[レイヤー] ウィンドウ" lightbox="../media/evaluate-performance-layers-all.msft.png":::
       [ **レイヤー]** ウィンドウ  
    :::image-end:::  
    
レイヤーにカーソルを合わせると、図で強調表示されます。  

:::image type="complex" source="../media/evaluate-performance-performance-frames-document-nav-bar-highlighted.msft.png" alt-text="レイヤーを強調表示する" lightbox="../media/evaluate-performance-performance-frames-document-nav-bar-highlighted.msft.png":::
   レイヤーを強調表示する  
:::image-end:::  

図を移動するには、次の方法を実行します。  

*   X **軸と** Y 軸に沿って移動するには、[パン モード\] (パン モード ![ ](../media/pan-mode-icon.msft.png) \) を選択します。  
*   Z **軸に沿って** 回転するには、[回転 ![ モード ](../media/rotate-mode-icon.msft.png) \] を選択します。  
*   [Reset **Transform** \( ![ Reset Transform \) ] を ](../media/reset-transform-icon.msft.png) 選択して、ダイアグラムを元の位置にリセットします。  
    
### <a name="view-paint-profiler"></a>ペイント プロファイラーの表示  

ペイント イベントに関する詳細な情報を表示するには、次の方法を実行します。  

1.  [をオンにする](#turn-on-advanced-paint-instrumentation)。  
1.  [メイン]**セクションペイント**イベントを**選択**します。  
    
    :::image type="complex" source="../media/evaluate-performance-paint-profiler.msft.png" alt-text="[ペイントプロファイル] パネル" lightbox="../media/evaluate-performance-paint-profiler.msft.png":::
       [**プロファイルペイント]** パネル  
    :::image-end:::  
    
## <a name="analyze-rendering-performance-with-the-rendering-tool"></a>レンダリング ツールを使用してレンダリングパフォーマンスを分析する  

[レンダリング] パネルの **機能を使用** して、ページのレンダリングパフォーマンスを視覚化します。  

レンダリング ツール **を開く** 方法:  

1.  [コマンド メニューを開きます][DevToolsCommandMenu]。  
1.  入力を開始 `Rendering` して選択します `Show Rendering` 。  DevTools は **、DevTools** ウィンドウの下部にレンダリング ツールを表示します。  
    
    :::image type="complex" source="../media/evaluate-performance-console-drawer-rendering.msft.png" alt-text="レンダリング ツール" lightbox="../media/evaluate-performance-console-drawer-rendering.msft.png":::
       レンダリング**ツール**  
    :::image-end:::  
    
### <a name="view-frames-per-second-in-realtime-with-the-fps-meter"></a>FPS メーターを使用してリアルタイムでフレーム/秒を表示する  

**FPS メーターは**、ビューポートの右上隅に表示されるオーバーレイです。  ページの実行に合った FPS のリアルタイム推定値を提供します。  FPS メーターを **開く方法**:  

1.  レンダリング ツール **を開** きます。  [レンダリング ツールを使用してレンダリングパフォーマンスを分析します](#analyze-rendering-performance-with-the-rendering-tool)。  
1.  [FPS メーター] **チェック ボックスをオン** にします。  
    
    :::image type="complex" source="../media/evaluate-performance-jank-console-rendering-frame-rate.msft.png" alt-text="FPS メーター" lightbox="../media/evaluate-performance-jank-console-rendering-frame-rate.msft.png":::
       **FPS メーター**  
    :::image-end:::  
    
### <a name="view-painting-events-in-realtime-with-paint-flashing"></a>フラッシュを使用してリアルタイムでペイント イベントをペイントする  

ページペイントすべてのペイント イベントのリアルタイム ビューを取得するには、[フラッシュ] を使用します。  ページの一部が再描画されるたびに、DevTools は、そのセクションのアウトラインを緑色で示します。  

フラッシュを有効ペイント、次のアクションを実行します。  

1.  レンダリング ツール **を開** きます。  [レンダリング ツール [を使用してレンダリングパフォーマンスを分析する] に移動します](#analyze-rendering-performance-with-the-rendering-tool)。  
1.  [フラッシュ] チェック**ボックスペイントオン**にします。  
    
    :::image type="complex" source="../media/evaluate-performance-jank-console-rendering-paint-flashing.msft.png" alt-text="ペイント点滅" lightbox="../media/evaluate-performance-jank-console-rendering-paint-flashing.msft.png":::
       **ペイント点滅**  
    :::image-end:::  
    
### <a name="view-an-overlay-of-layers-with-layer-borders"></a>[レイヤーの罫線] を使用してレイヤーのオーバーレイを表示する  

レイヤー **罫線を使用** して、ページの上部にレイヤーの罫線とタイルのオーバーレイを表示します。  

[レイヤー罫線] を有効にする場合は、次の操作を実行します。  

1.  レンダリング ツール **を開** きます。  [レンダリング ツール [を使用してレンダリングパフォーマンスを分析する] に移動します](#analyze-rendering-performance-with-the-rendering-tool)。  
1.  [レイヤーの罫 **線] チェック ボックスをオン** にします。  
    
    :::image type="complex" source="../media/evaluate-performance-devtools-console-rendering-layer-borders.msft.png" alt-text="レイヤーの罫線" lightbox="../media/evaluate-performance-devtools-console-rendering-layer-borders.msft.png":::
       **レイヤーの罫線**  
    :::image-end:::  
    
[debug_colors.cc のコメント][ChromiumDebugColors]に移動して、色分けについて説明します。  

### <a name="find-scroll-performance-issues-in-realtime"></a>リアルタイムでスクロールパフォーマンスの問題を見つける  

スクロールパフォーマンスの問題を使用して、ページのパフォーマンスを低下させる可能性のあるスクロールに関連するイベント リスナーを持つページの要素を識別します。  
DevTools は、teal の潜在的に問題のある要素の概要を示します。  

スクロール パフォーマンスの問題を表示するには、次の操作を実行します。 

1.  レンダリング ツール **を開** きます。  [レンダリング ツール [を使用してレンダリングパフォーマンスを分析する] に移動します](#analyze-rendering-performance-with-the-rendering-tool)。  
1.  [パフォーマンスの **問題のスクロール] チェック ボックスをオン** にします。  
    
    :::image type="complex" source="../media/evaluate-performance-bing-console-drawer-rendering-scrolling-performance-issues.msft.png" alt-text="スクロールパフォーマンスの問題は、レイヤー以外のビューポートに制約のあるオブジェクトがスクロールのパフォーマンスに影響を与える可能性を示します" lightbox="../media/evaluate-performance-bing-console-drawer-rendering-scrolling-performance-issues.msft.png":::
       **スクロールパフォーマンスの問題は、** レイヤー以外のビューポートに制約のあるオブジェクトがスクロールのパフォーマンスに影響を与える可能性を示します  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft Docs"  
[DevToolsCommandMenu]: ../command-menu/index.md#open-the-command-menu "コマンド メニューを開く - DevTools コマンド Microsoft Edgeコマンド メニューを使用してコマンドを実行|Microsoft Docs"  
[DevtoolsEvaluatePerformanceGettingStarted]: ./index.md "ランタイム パフォーマンス の分析の開始|Microsoft Docs"  

[ActivityTabsDemo]: https://microsoft-edge-chromium-devtools.glitch.me/perf/activitytabs.html "アクティビティ タブのデモ |グリッチ"  

[ChromiumDebugColors]: https://cs.chromium.org/chromium/src/cc/debug/debug_colors.cc "debug_colors.cc - コード検索"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/reference) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
