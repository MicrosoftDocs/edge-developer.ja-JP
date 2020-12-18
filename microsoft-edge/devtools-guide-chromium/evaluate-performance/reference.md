---
description: Microsoft Edge DevTools でパフォーマンスを記録および分析するためのすべての方法に関するリファレンスです。
title: パフォーマンス分析リファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: d5b6be92c1419ba880a94c62c3f586a740816622
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230762"
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

# パフォーマンス分析リファレンス  

このページは、パフォーマンスの分析に関連する Microsoft Edge DevTools 機能の包括的なリファレンスです。  

[Microsoft Edge DevTools][MicrosoftEdgeDevTools][を使用して][DevtoolsEvaluatePerformanceGettingStarted]ページのパフォーマンスを分析する方法に関するガイド付きチュートリアルについては、「ランタイム パフォーマンスの分析の開始」に移動します。  

## パフォーマンスを記録する  

### 実行時のパフォーマンスを記録する  

読み込みではなく、実行中のページのパフォーマンスを分析する場合は、実行時のパフォーマンスを記録します。  

1.  分析するページに移動します。  
1.  DevTools **の** [パフォーマンス] タブを選択します。  
1.  Choose **Record** \( ![ Record icon ][ImageRecordIcon] \).  
    
    :::image type="complex" source="../media/evaluate-performance-performance-record-highlight.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-record-highlight.msft.png":::
       **Record**  
    :::image-end:::  
    
1.  ページを操作します。  DevTools は、操作の結果として発生するページ アクティビティを記録します。  
1.  もう一 **度 [Record]** を選ぶか **、[Stop]** を選んでレコーディングを停止します。  
    
### 読み込みパフォーマンスを記録する  

実行中ではなく、読み込み中のページのパフォーマンスを分析する場合は、読み込みパフォーマンスを記録します。  

1.  分析するページに移動します。  
1.  DevTools **の** パフォーマンス パネルを開きます。  
1.  Choose **Refresh page** \( Refresh Page ![ ][ImageRefreshPageIcon] \).  DevTools は、ページの更新中にパフォーマンス メトリックを記録し、読み込み完了から数秒後に自動的に記録を停止します。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-refresh-button.msft.png" alt-text="ページを更新する" lightbox="../media/evaluate-performance-performance-refresh-button.msft.png":::
       **ページを更新する**  
    :::image-end:::  
    
DevTools は、ほとんどのアクティビティが発生した記録の部分を自動的に拡大します。  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed.msft.png" alt-text="ページ読み込み記録" lightbox="../media/evaluate-performance-performance-refreshed.msft.png":::
   ページ読み込み記録  
:::image-end:::  

### 記録中のスクリーンショットのキャプチャ  

**[Screenshots] チェック ボックスをオン**にして、記録中のすべてのフレームのスクリーンショットをキャプチャします。  

:::image type="complex" source="../media/evaluate-performance-performance-capture-screenshots-checkbox.msft.png" alt-text="[スクリーンショット] チェック ボックス" lightbox="../media/evaluate-performance-performance-capture-screenshots-checkbox.msft.png":::
   [ **スクリーンショット]** チェック ボックス  
:::image-end:::  

[スクリーンショット [の表示] に移動して](#view-a-screenshot) 、スクリーンショットを操作する方法を確認します。  

### 記録中にガベージ コレクションを強制する  

ページを記録している間に、[ガベージ**** の収集\ ( ガベージ アイコン \) を収集する] を選択して、ガベージ ![ ][ImageCollectGarbageIcon] コレクションを強制的に実行します。  

:::image type="complex" source="../media/evaluate-performance-performance-collect-garbage-button.msft.png" alt-text="ガベージを収集する" lightbox="../media/evaluate-performance-performance-collect-garbage-button.msft.png":::
   ガベージを収集する  
:::image-end:::  

### レコーディング設定を表示する  

DevTools **がパフォーマンス** 記録をキャプチャする方法に関連するその他の設定を公開するには、[Capture settings \( ![ Capture settings ][ImageCaptureSettingsIcon] \) ] を選択します。  

:::image type="complex" source="../media/evaluate-performance-performance-capture-settings-button-open-drawer.msft.png" alt-text="[キャプチャの設定] セクション" lightbox="../media/evaluate-performance-performance-capture-settings-button-open-drawer.msft.png":::
   [ **キャプチャの設定]** セクション  
:::image-end:::  

### JavaScript サンプルを無効にする  

既定では、レコーディングの **Main** セクションには、レコーディング中に呼び出された JavaScript 関数の詳細な呼び出し履歴が表示されます。  これらのコール スタックを無効にするには:  

1.  [キャプチャの **設定] メニューを開** きます。  [Show [recording settings] (レコーディング設定の表示) に移動します](#show-recording-settings)。  
1.  [JavaScript サンプル **を無効にする] チェック ボックスをオン** にします。  
1.  ページの記録を取ります。  
    
次の 2 つの図は、JavaScript サンプルの無効化と有効化の違いを示しています。  サンプリング **を** 無効にすると、すべての JavaScript 呼び出しスタックが省略されるので、レコーディングの Main セクションははるかに短くなります。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-on.msft.png" alt-text="JS サンプルが無効になっている場合の記録の例" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-on.msft.png":::
         JS サンプルが無効になっている場合の記録の例  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off.msft.png" alt-text="JS サンプルをオンにした場合の記録の例" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off.msft.png":::
         JS サンプルをオンにした場合の記録の例  
      :::image-end:::  
   :::column-end:::
:::row-end:::

### 記録中にネットワークを調整する  

記録中にネットワークを調整するには、次の操作を行います。  

1.  [キャプチャの **設定] メニューを開** きます。  [Show [recording settings] (レコーディング設定の表示) に移動します](#show-recording-settings)。  
1.  ネットワーク **を** 目的の調整レベルに設定します。  
    
### 記録中に CPU を調整する  

記録中に CPU を調整するには、次の操作を行います。  

1.  [キャプチャの **設定] メニューを開** きます。  [Show [recording settings] (レコーディング設定の表示) に移動します](#show-recording-settings)。  
1.  **CPU を**目的の調整レベルに設定します。  
    
調整は、コンピューターの機能に関連します。  たとえば **、2x の** スローダウン オプションでは、CPU の動作が通常よりも 2 倍遅くなります。  モバイル デバイスのアーキテクチャはデスクトップやノート PC のアーキテクチャと非常に異なっているので、DevTools はモバイル デバイスの CPU を実際にシミュレートするのではありません。  

### 高度なペイントインストルメンテーションを有効にする  

ペイントインストルメンテーションの詳細を表示するには:  

1.  [キャプチャの **設定] メニューを開** きます。  [Show [recording settings] (レコーディング設定の表示) に移動します](#show-recording-settings)。  
1.  [高度な **ペイントインストルメンテーションを有効にする (低速) チェック ボックスを** オンにします。  

ペイント情報を操作する方法については、「レイヤーの表示」[](#view-layers-information)と「ペイント プロファイラーの[表示」に移動します](#view-paint-profiler)。  

## レコーディングを保存する  

記録を保存するには、コンテキスト メニュー \(右クリック\) を開き、[プロファイルの保存] **を選択します**。  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-save-profile.msft.png" alt-text="プロファイルの保存" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-save-profile.msft.png":::
   **プロファイルの保存**  
:::image-end:::  

## レコーディングを読み込む  

レコーディングを読み込むには、コンテキスト メニュー \(右クリック\) を開き、[プロファイルの読み込み **] を選択します**。  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-load-profile.msft.png" alt-text="プロファイルの読み込み" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-load-profile.msft.png":::
   **プロファイルの読み込み**  
:::image-end:::  

## 前のレコーディングをクリアする  

レコーディングを行った後、Clear **recording** \( Clear recording icon \) を押して、パフォーマンス パネルからそのレコーディング ![ ][ImageClearRecordingIcon] を **クリア** します。  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-clear-button.msft.png" alt-text="レコーディングのクリア" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-clear-button.msft.png":::
   **レコーディングのクリア**  
:::image-end:::  

## パフォーマンス記録を分析する  

実行時の[パフォーマンスまたは](#record-runtime-performance)レコード読[](#record-load-performance)み込みパフォーマンスを**** 記録した後、パフォーマンス パネルには、発生したパフォーマンスを分析するための多くのデータが表示されます。  

### レコーディングの一部を選択する  

マウスを [概要] の左または右に **ドラッグ** して、レコーディングの一部を選択します。  概要**は****、FPS、CPU、および NET****** グラフを含む**セクション**です。  

:::image type="complex" source="../media/evaluate-performance-performance-zoom-highlighted.msft.png" alt-text="マウスを [概要] の上にドラッグしてズームする" lightbox="../media/evaluate-performance-performance-zoom-highlighted.msft.png":::
   マウスを [概要] の上 **にドラッグして** ズームする  
:::image-end:::  

キーボードを使って部分を選択するには:  

1.  Main セクションの背景 **、またはその**横にあるセクション (**操作**、ネットワーク **、GPU**など)**を選択**します。  このキーボード ワークフローは、これらのセクションの 1 つがフォーカスされている場合にのみ機能します。  
1.  拡大、左へ移動、縮小、右に移動するには、キー 、 `W` `A` `S` `D` を使用します。  

トラックパッドを使って部分を選択するには、次の操作を実行します。  

1.  [概要] セクションまたは [ **詳細] セクション** の上にマウス ポインター **を移動** します。  [**概要**] セクションは **、FPS、CPU、および**NET グラフを含む**領域**です。 ****  [ **詳細]** セクションは **、Main** セクションや [Interactions] **セクションを含** む領域です。  
1.  2 本の指でスワイプして縮小表示し、左にスワイプして左に移動し、下にスワイプして拡大し、右にスワイプして右に移動します。  

Main セクションまたは任意の隣接する**** グラフで長い横棒グラフをスクロールするには、上下にドラッグしながら長押しします。  左右にドラッグして、レコーディングの選択部分を移動します。  

### 検索アクティビティ  

`Control` + `F` \(Windows,Linux\) または `Command` + `F` \(macOS\)**** を選択して、パフォーマンス パネルの下部にある検索ボックスを開きます。  

:::image type="complex" source="../media/evaluate-performance-performance-search-regex.msft.png" alt-text="検索ボックス" lightbox="../media/evaluate-performance-performance-search-regex.msft.png":::
   検索ボックス  
:::image-end:::  

クエリに一致するアクティビティを移動するには:  

*   以前の**** \( ![ Previous \) ボタン ][ImagePreviousIcon] と Next \( **Next** \) ボタン ![ ][ImageNextIcon] を使用します。  
*   前 `Shift` + `Enter` の項目を選択するか、 `Enter` 次の項目を選択します。  

クエリ設定を変更するには:  

*   大文字 **と小文字を区別** する \( 大文字と小文字を区別する \) を押して、クエリ ![ ][ImageSearchCaseIcon] で大文字と小文字を区別します。  
*   **Regex** \( Regex \) キーを押して、クエリで ![ ][ImageSearchRegexIcon] 正規表現を使用します。  

検索ボックスを非表示にする場合は **、Cancel**キーを押します。  

### メイン スレッド アクティビティを表示する  

Main セクション **を使用** して、ページのメイン スレッドで発生したアクティビティを表示します。  

:::image type="complex" source="../media/evaluate-performance-performance-main-zoomed.msft.png" alt-text="Main セクション" lightbox="../media/evaluate-performance-performance-main-zoomed.msft.png":::
   Main **** セクション  
:::image-end:::  

イベントを選択すると、そのイベントに関する詳細が [概要] タブ **に表示** されます。 DevTools は、選択したイベントの概要を示します。  

:::image type="complex" source="../media/evaluate-performance-performance-summary-me.msft.png" alt-text="[概要] タブの匿名関数の詳細" lightbox="../media/evaluate-performance-performance-summary-me.msft.png":::
   [概要] `anonymous` タブの関数**の詳細**  
:::image-end:::  

DevTools は、メイン スレッド アクティビティを表し、グラフを表示します。  x 軸は、時間の過ごした記録を表します。  y 軸は呼び出し履歴を表します。  一番上のイベントは、その下のイベントを引き起こします。  

:::image type="complex" source="../media/evaluate-performance-performance-main-flame-chart.msft.png" alt-text="グラフ (グラフ)" lightbox="../media/evaluate-performance-performance-main-flame-chart.msft.png":::
   グラフ (グラフ)  
:::image-end:::  

前の図では、53 行目にイベント `click` `Function Call` `activitytabs.js` が発生しました。  次 `Function Call` に、匿名関数が実行されたと確認します。  要求された匿名関数 `a` 。要求 `wait` されました `Minor GC` 。  

DevTools は、スクリプトのランダムな色を割り当てします。  前の図では、1 つのスクリプトからの関数要求は薄い緑色で表示されています。  別のスクリプトからの要求は色分けされています。  濃い黄色はスクリプト アクティビティを表し、紫色のイベントはレンダリング アクティビティを表します。  これらの濃い黄色と紫色のイベントは、すべてのレコーディングで一貫しています。  

JavaScript 要求 [の詳細な](#disable-javascript-samples) グラフを非表示にする場合は、[JavaScript サンプルを無効にする] に移動します。  JS サンプルが無効になっている場合は、前の図のような、および前の図からの高レベル `Event: click` `Function Call` のイベントだけが表示 `str` されます。  

### テーブル内のアクティビティを表示する  

ページを記録した後は、Main セクションのみを使用してアクティビティ **を分析** する必要があります。  DevTools には、アクティビティを分析するための 3 つの表形式ビューもあります。  各ビューには、アクティビティに対する異なる視点があります。  

*   最も多くの作業を引き起こすルート アクティビティを表示する場合は、[呼び出 [しツリー] タブを使用します](#the-call-tree-tab)。  
*   最も時間が直接費やされたアクティビティを表示するには、次のBottom-Up [します](#the-bottom-up-tab)。  
*   記録中に発生した順序でアクティビティを表示する場合は、[イベント ログ] タブ [を使用します](#the-event-log-tab)。  
    
> [!NOTE]
> 次の 3 つのセクションはすべて同じデモを参照します。  アクティビティ タブのデモで [デモを自分で実行します][ActivityTabsDemo]。  

#### ルート アクティビティ  

ここでは、[コール ツリー]**** タブ******、[Bottom-Up]** タブ、および [Event **Log]** セクションに記載されているルート アクティビティの概念について説明します。  

ルート アクティビティは、ブラウザーが何らかの作業を行う原因となるアクティビティです。  たとえば、Web ページを選択すると、ブラウザーはルート `Event` アクティビティとしてアクティビティを実行します。  そのため `Event` 、ハンドラーが実行される可能性があります。  

Main セクションの **グラフでは、** ルート アクティビティがグラフの上部に表示されます。  [ **呼び出しツリー]** **タブと [イベント ログ] タブ** では、ルート アクティビティがトップ レベルの項目です。  

ルート アクティビティ [の例の [呼び出](#the-call-tree-tab) しツリー] タブに移動します。  

#### [呼び出しツリー] タブ  

[呼 **び出しツリー] タブ** を使用して、最も [多くの作業を引き起](#root-activities) こすルート アクティビティを表示します。  

[ **呼び出しツリー]** タブには、レコーディングの選択した部分のアクティビティだけが表示されます。  [記録の [一部を選択] に移動して](#select-a-portion-of-a-recording) 、部分を選択する方法を確認します。  

:::image type="complex" source="../media/evaluate-performance-performance-call-tree.msft.png" alt-text="[呼び出しツリー] タブ" lightbox="../media/evaluate-performance-performance-call-tree.msft.png":::
   [ **呼び出しツリー]** タブ  
:::image-end:::  

前の図では、[アクティビティ] 列のアイテムのトップ**** レベル (ルート アクティビティなど `Evaluate Script` ) `Parse HTML` です。  入れ子は呼び出し履歴を表します。  たとえば、前の図では、 `Parse HTML` 原因と原因が `Evaluate Script` 次 `Compile Script` のようになります `(anonymous)` 。  

**Self Time は** 、そのアクティビティに直接費やされた時間を表します。  **Total Time** は、そのアクティビティまたは任意の子に費やされた時間を表します。  

[Self **Time]、[Total** **Time]、または** **[Activity]** を選択して、テーブルをその列で並べ替える。  

[フィルター **] テキスト ボックス** を使用して、アクティビティ名でイベントをフィルター処理します。  

既定では、[ **グループ化] メニュー** は [グループ化なし **] に設定されています**。  [グループ **化] メニューを使用** して、さまざまな条件に基づいてアクティビティ テーブルを並べ替える。  

[Show **Heaviest Stack** \( Show Heaviest Stack \) ] を選択して、Activity テーブルの右側に別のテーブル ![ ][ImageShowHeaviestStackIcon] を **表示** します。  最も重いスタック テーブルを設定 **するアクティビティを選択** します。  最 **も重いスタック** テーブルには、選択したアクティビティの子の実行に最も時間がかかった時間が表示されます。  

#### [Bottom-Up] タブ  

[ **下へ上へ] タブを** 使用して、集計で最も時間を直接取ったアクティビティを表示します。  

[ **下へ上へ]** タブには、レコーディングの選択した部分の間のアクティビティだけが表示されます。  [記録の [一部を選択] に移動して](#select-a-portion-of-a-recording) 、部分を選択する方法を確認します。  

:::image type="complex" source="../media/evaluate-performance-performance-bottoms-up.msft.png" alt-text="[Bottom-Up] タブ" lightbox="../media/evaluate-performance-performance-bottoms-up.msft.png":::
   [ **下へ]** タブ  
:::image-end:::  

前の **図の Main** セクションのグラフグラフで、ほぼすべての時間が実行に費やされたグラフに移動します `Parse HTML` 。  前の図の [ **下から上** へ] タブの一番上のアクティビティは次の値です `Parse HTML` 。  <!--In the flame chart of the previous figure, the yellow below the calls to `wait` are actually thousands of `Minor GC` calls.  -->  最もコスト **の高い次** のアクティビティである [下向き] タブに移動します `Layout` 。  

[Self **Time]** 列は、すべての発生回数にわたって、そのアクティビティに直接費やされた合計時間を表します。  

[ **合計時間]** 列は、そのアクティビティまたは任意の子に費やされた合計時間を表します。  

#### [イベント ログ] タブ  

[イベント **ログ] タブを** 使用して、記録中に発生した順序でアクティビティを表示します。  

[ **イベント ログ] タブ** には、記録中に選択した部分のアクティビティだけが表示されます。  [記録の [一部を選択] に移動して](#select-a-portion-of-a-recording) 、部分を選択する方法を確認します。  

:::image type="complex" source="../media/evaluate-performance-performance-event-log.msft.png" alt-text="[イベント ログ] タブ" lightbox="../media/evaluate-performance-performance-event-log.msft.png":::
   [ **イベント ログ]** タブ  
:::image-end:::  

[ **開始時刻]** 列は、記録の開始位置を基準に、そのアクティビティが開始されたポイントを表します。  たとえば、前の図で選択したアイテムの開始時刻は、記録が開始した `175.7 ms` 後、アクティビティが 175.7 ミリ秒後に開始されたという意味です。  

[Self **Time] 列** は、そのアクティビティに直接費やされた時間を表します。  

[ **合計時間]** 列は、そのアクティビティまたは任意の子に直接費やされた時間を表します。  

[ **開始時刻]、[Self** **Time]、または** **[Total Time]** を選択して、テーブルをその列で並べ替える。

[フィルター **] テキスト ボックス** を使用して、アクティビティを名前でフィルター処理します。  

[期間 **] メニューを** 使用して、1 ミリ秒未満または 15 ミリ秒未満のアクティビティをフィルター処理します。  既定では、[ **期間] メニュー** は [すべて] に **設定され、** すべてのアクティビティが表示されます。  

[読み**込み****]、[スクリプト]、[****レンダリング]、** または [**描画**] チェック ボックスを無効にして、これらのカテゴリからすべてのアクティビティをフィルター処理します。  

### GPU アクティビティの表示  

GPU セクションで GPU アクティビティ **を表示** します。  

:::image type="complex" source="../media/evaluate-performance-performance-gpu-zoomed.msft.png" alt-text="GPU セクション" lightbox="../media/evaluate-performance-performance-gpu-zoomed.msft.png":::
   **GPU セクション**  
:::image-end:::  

### ラスター アクティビティを表示する  

[ラスター] セクションでラスター アクティビティ **を表示** します。  

:::image type="complex" source="../media/evaluate-performance-performance-raster.msft.png" alt-text="[ラスター] セクション" lightbox="../media/evaluate-performance-performance-raster.msft.png":::
   [ **ラスター]** セクション  
:::image-end:::  

### 操作の表示  

[操作 **] セクションを** 使用して、レコーディング中に発生したユーザー操作を見つけて分析します。  

:::image type="complex" source="../media/evaluate-performance-performance-interactions-animation.msft.png" alt-text="[操作] セクション" lightbox="../media/evaluate-performance-performance-interactions-animation.msft.png":::
   [ **操作]** セクション  
:::image-end:::  

対話式操作の下部にある赤い線は、メイン スレッドの待機に費やされた時間を表します。  

操作を選択すると、[概要] タブに詳細 **な情報が表示** されます。  

### 秒あたりのフレーム数を分析する (FPS)  

DevTools には、1 秒あたりのフレームを分析するさまざまな方法があります。  

*   [記録期間中の FPS](#the-fps-chart)の概要を取得するには、FPS グラフを使用します。  
*   [[Frames] セクションを使用](#the-frames-section)して、特定のフレームにかかった時間を表示します。  
*   ページの **実行中に FPS** のリアルタイム推定値として FPS メーターを使用します。  FPS メーターを使って、リアルタイムで [1 秒あたりのフレーム [数の表示] に移動します](#view-frames-per-second-in-realtime-with-the-fps-meter)。  
    
#### FPS グラフ  

**FPS グラフ**は、レコーディング中のフレーム レートの概要を示します。  一般に、緑のバーが大きいほど、フレーム レートが良くなります。  

FPS グラフの上の赤 **い** バーは、フレーム レートが低く低下し、ユーザーのエクスペリエンスに損害を与えた可能性があるという警告です。  

:::image type="complex" source="../media/evaluate-performance-performance-fps-highlight.msft.png" alt-text="FPS グラフ" lightbox="../media/evaluate-performance-performance-fps-highlight.msft.png":::
   **FPS グラフ**  
:::image-end:::  

#### [フレーム] セクション  

**[Frames]** セクションでは、特定のフレームにかかった時間を正確に示します。  

フレームの上にマウス ポインターを移動すると、そのフレームに関する詳細な情報を含むヒントが表示されます。  

:::image type="complex" source="../media/evaluate-performance-performance-frames-hover.msft.png" alt-text="フレームにカーソルを合わせる" lightbox="../media/evaluate-performance-performance-frames-hover.msft.png":::
   フレームにカーソルを合わせる  
:::image-end:::  

[概要] タブでフレームに関する詳細を表示するには、フレーム **を選択** します。 DevTools は、選択したフレームの輪郭を青で示します。  

:::image type="complex" source="../media/evaluate-performance-performance-frames-summary.msft.png" alt-text="[概要] タブでフレームを表示する" lightbox="../media/evaluate-performance-performance-frames-summary.msft.png":::
   [概要] タブでフレーム **を表示** する  
:::image-end:::  

### ネットワーク要求の表示  

[ネットワーク **] セクションを** 展開して、レコーディング中に発生したネットワーク要求のウォーターフォールを表示します。  

:::image type="complex" source="../media/evaluate-performance-performance-network.msft.png" alt-text="[ネットワーク] セクション" lightbox="../media/evaluate-performance-performance-network.msft.png":::
   [ **ネットワーク]** セクション  
:::image-end:::  

要求は、次のように色分けされています。  

*   HTML: Blue  
*   CSS: 紫色  
*   JS: Yellow  
*   画像: 緑  
    
詳細を表示する要求を [概要] タブ**で選択**します。 たとえば、前の図の [概要****] タブには、[ネットワーク] セクションで選択されている青色の要求に関する詳細が**表示**されています。  

要求の左上に濃い青色の正方形が表示されている場合は、優先度の高い要求です。  明るい青の正方形は優先順位が低いという意味です。  たとえば、前の図では、青の選択された要求の方が優先度が高く、下の緑色の要求は優先度が低くなります。  

次の図の 1 つ目では、要求は左側の行、中央に暗い部分と明るい部分を含むバー、右側に線で表されます。 `www.bing.com`  次の図の 2nd では、[ネットワーク] パネルの [タイミング]**** タブに同じ要求の対応する表現が**示**されています。  次に、これら 2 つの表現を互いにマップする方法を示します。

*   左側の行は、イベントのグループ `Connection Start` までのすべてです。  つまり、前のすべてで、排他的 `Request Sent` です。  
*   バーの明るい部分は、 `Request Sent` `Waiting (TTFB)` .  
*   バーの暗い部分は次の値です `Content Download` 。  
*   正しい行は、基本的にメイン スレッドの待機に費やされた時間です。  これは 、[タイミング] タブには **表示** されません。  
    
:::row:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-bing-performance-network.msft.png" alt-text="要求の行バー www.bing.comします。" lightbox="../media/evaluate-performance-bing-performance-network.msft.png":::
         要求の行バー `www.bing.com` 表現  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-bing-network-timing.msft.png" alt-text="ネットワーク ツール" lightbox="../media/evaluate-performance-bing-network-timing.msft.png":::
         ネットワーク**ツール**  
: ::image-end:::  
   :::column-end:::
:::row-end:::

### メモリ メトリックスを表示する  

[メモリ] チェック **ボックスを** オンにして、最後の記録のメモリ メトリックを表示します。  

:::image type="complex" source="../media/evaluate-performance-performance-memory-highlight.msft.png" alt-text="[メモリ] チェック ボックス" lightbox="../media/evaluate-performance-performance-memory-highlight.msft.png":::
   [ **メモリ]** チェック ボックス  
:::image-end:::  

DevTools は、[ **概要]** タブの上に新しい **メモリ グラフを表示** します。 また、NET グラフの下には **、HEAP** という新しいグラフ **があります**。  **HEAP グラフ**は、Memory グラフの**JS ヒープ**行と同じ情報を**提供**します。  

:::image type="complex" source="../media/evaluate-performance-performance-memory-chart.msft.png" alt-text="メモリメトリックス" lightbox="../media/evaluate-performance-performance-memory-chart.msft.png":::
   メモリメトリックス  
:::image-end:::  

グラフの色付き線は、グラフの上の色付きチェック ボックスにマップされます。  
チェック ボックスを無効にして、グラフからそのカテゴリを非表示にします。  

グラフには、現在選択されているレコーディングの領域だけが表示されます。  たとえば、前の図の [メモリ****] グラフには、400 ミリ秒のマークから 1750 ミリ秒のマークまでメモリ使用量だけが表示されています。  

### レコーディングの一部の期間を表示する  

Network や**Main****** などのセクションを分析する場合、特定のイベントにかかった時間を正確に見積もる必要がある場合があります。  録音 `Shift` の一部を選択するには、長押し、長押し、左右にドラッグします。  選択した部分の下部に、DevTools はその部分にかかった時間を示します。  

:::image type="complex" source="../media/evaluate-performance-performance-main-duration.msft.png" alt-text="レコーディングの一部の期間を表示する" lightbox="../media/evaluate-performance-performance-main-duration.msft.png":::
   レコーディングの一部の期間を表示する  
:::image-end:::  

### スクリーンショットを表示する  

記録中 [に [キャプチャ] のスクリーンショットに移動して](#capture-screenshots-while-recording) 、スクリーンショットを有効にする方法を確認します。  

[概要] **をポイント** すると、記録中にページがどのように表示されたのかのスクリーンショットが表示されます。  [ **概要** ] は **、CPU、FPS、および** **NET**のグラフを含む **セクション** です。  

:::image type="complex" source="../media/evaluate-performance-performance-screenshots-hover.msft.png" alt-text="スクリーンショットを表示する" lightbox="../media/evaluate-performance-performance-screenshots-hover.msft.png":::
   スクリーンショットを表示する  
:::image-end:::  

[フレーム] セクションでフレームを選択して、スクリーンショットを **表示** することもできます。  DevTools は、[概要] タブに小さいバージョンのスクリーンショット **を表示** します。  

:::image type="complex" source="../media/evaluate-performance-performance-summary-preview.msft.png" alt-text="[概要] タブでスクリーンショットを表示する" lightbox="../media/evaluate-performance-performance-summary-preview.msft.png":::
   [概要] タブでスクリーンショット **を表示** する  
:::image-end:::  

[概要] タブでサムネイル **を選択** して、スクリーンショットを拡大します。  

:::image type="complex" source="../media/evaluate-performance-performance-summary-preview-select.msft.png" alt-text="[概要] タブからスクリーンショットを拡大する" lightbox="../media/evaluate-performance-performance-summary-preview-select.msft.png":::
   [概要] タブからスクリーンショット **を拡大** する  
:::image-end:::  

### レイヤー情報の表示  

フレームに関する高度なレイヤー情報を表示するには:  

1.  [高度なペイントインストルメンテーションを有効にする](#turn-on-advanced-paint-instrumentation)。  
1.  [フレーム] セクションでフレーム **を選択** します。  DevTools は、[イベント ログ] タブ**** の横にある新しい [レイヤー] タブにレイヤーに関する**情報を表示**します。  
    
    :::image type="complex" source="../media/evaluate-performance-layers-all.msft.png" alt-text="[レイヤー] ウィンドウ" lightbox="../media/evaluate-performance-layers-all.msft.png":::
       [ **レイヤー]** ウィンドウ  
    :::image-end:::  
    
レイヤーの上にカーソルを合わせると、図内で強調表示されます。  

:::image type="complex" source="../media/evaluate-performance-performance-frames-document-nav-bar-highlighted.msft.png" alt-text="レイヤーを強調表示する" lightbox="../media/evaluate-performance-performance-frames-document-nav-bar-highlighted.msft.png":::
   レイヤーを強調表示する  
:::image-end:::  

図を移動するには:  

*   [ **パン モード** \( パン モード \) ] を ![ ][ImagePanModeIcon] 選択して、X 軸と Y 軸に沿って移動します。  
*   Z **軸に沿って** 回転するには、回転モード ![ ][ImageRotateModeIcon] \( 回転モード \) を選択します。  
*   図 **を元の位置** にリセットするには、Reset ![ Transform \( Reset Transform ][ImageResetTransformIcon] \) を選択します。  
    
### ペイント プロファイラーの表示  

ペイント イベントに関する詳細な情報を表示するには:  

1.  [オンにする](#turn-on-advanced-paint-instrumentation)。  
1.  Main セクション **でペイント** イベント **を選択** します。  
    
    :::image type="complex" source="../media/evaluate-performance-paint-profiler.msft.png" alt-text="[ペイント プロファイラー] タブ" lightbox="../media/evaluate-performance-paint-profiler.msft.png":::
       [ **ペイント プロファイラー]** タブ  
    :::image-end:::  
    
## [レンダリング] タブを使用してレンダリングパフォーマンスを分析する  

[レンダリング] タブの **機能を使用** して、ページのレンダリング パフォーマンスを視覚化します。  

[レンダリング] タブ **を開** く方法:  

1.  [コマンド メニューを開きます][DevToolsCommandMenu]。  
1.  入力を開始 `Rendering` し、選択します `Show Rendering` 。  DevTools は **、DevTools** ウィンドウの下部に [レンダリング] タブを表示します。  
    
    :::image type="complex" source="../media/evaluate-performance-console-drawer-rendering.msft.png" alt-text="[レンダリング] タブ" lightbox="../media/evaluate-performance-console-drawer-rendering.msft.png":::
       [ **レンダリング]** タブ  
    :::image-end:::  
    
### FPS メーターを使用してリアルタイムで 1 秒あたりのフレーム数を表示する  

**FPS メーターは**、ビューポートの右上隅に表示されるオーバーレイです。  ページの実行に合った FPS のリアルタイムの推定値を提供します。  FPS メーターを **開く方法**:  

1.  [レンダリング] **タブを開** きます。 Na [Analyze rendering performance with the Rendering tab](#analyze-rendering-performance-with-the-rendering-tab).  
1.  **[FPS メーター] チェック ボックスをオン**にします。  
    
    :::image type="complex" source="../media/evaluate-performance-jank-console-rendering-frame-rate.msft.png" alt-text="FPS メーター" lightbox="../media/evaluate-performance-jank-console-rendering-frame-rate.msft.png":::
       **FPS メーター**  
    :::image-end:::  
    
### ペイント フラッシュを使ってリアルタイムで描画イベントを表示する  

ページ上のすべてのペイント イベントのリアルタイム ビューを取得するには、ペイント フラッシュを使用します。  ページの一部が再描画されるたびに、DevTools によってそのセクションのアウトラインが緑色で表示されます。  

ペイント フラッシュを有効にする場合は、次の操作を実行します。  

1.  [レンダリング] **タブを開** きます。 [レンダリング] タブ [で [レンダリングパフォーマンスの分析] に移動します](#analyze-rendering-performance-with-the-rendering-tab)。  
1.  [ペイントの点滅 **] チェック ボックスをオン** にします。  
    
    :::image type="complex" source="../media/evaluate-performance-jank-console-rendering-paint-flashing.msft.png" alt-text="ペイントの点滅" lightbox="../media/evaluate-performance-jank-console-rendering-paint-flashing.msft.png":::
       **ペイントの点滅**  
    :::image-end:::  
    
### レイヤー罫線を使用してレイヤーのオーバーレイを表示する  

レイヤー **罫線を使用** して、ページの上にレイヤー罫線とタイルのオーバーレイを表示します。  

レイヤー罫線を有効にする場合は、次の操作を実行します。  

1.  [レンダリング] **タブを開** きます。 [レンダリング] タブ [で [レンダリングパフォーマンスの分析] に移動します](#analyze-rendering-performance-with-the-rendering-tab)。  
1.  [レイヤー罫 **線] チェック ボックスをオン** にします。  
    
    :::image type="complex" source="../media/evaluate-performance-devtools-console-rendering-layer-borders.msft.png" alt-text="レイヤー罫線" lightbox="../media/evaluate-performance-devtools-console-rendering-layer-borders.msft.png":::
       **レイヤー罫線**  
    :::image-end:::  
    
[debug_colors.cc][ChromiumDebugColors]のコメントに移動して、色分けについて説明します。  

### リアルタイムでスクロール パフォーマンスの問題を見つける  

スクロールパフォーマンスの問題を使用して、ページのパフォーマンスを低下させる可能性のあるスクロールに関連するイベント リスナーを持つページの要素を特定します。  
DevTools は、問題が発生する可能性のある要素の概要を小さい形で示します。  

スクロール パフォーマンスの問題を表示するには、次の操作を実行します。 

1.  [レンダリング] **タブを開** きます。 [レンダリング] タブ [で [レンダリングパフォーマンスの分析] に移動します](#analyze-rendering-performance-with-the-rendering-tab)。  
1.  **[Scrolling Performance Issues] チェック ボックスをオン**にします。  
    
    :::image type="complex" source="../media/evaluate-performance-bing-console-drawer-rendering-scrolling-performance-issues.msft.png" alt-text="スクロールのパフォーマンスの問題は、レイヤー以外のビューポートに制約のあるオブジェクトがスクロールのパフォーマンスを低下させる可能性を示します" lightbox="../media/evaluate-performance-bing-console-drawer-rendering-scrolling-performance-issues.msft.png":::
       **スクロールのパフォーマンスの問題は、** レイヤー以外のビューポートに制約のあるオブジェクトがスクロールのパフォーマンスを低下させる可能性を示します  
    :::image-end:::  
    
## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageCaptureSettingsIcon]: ../media/capture-settings-icon.msft.png  
[ImageClearRecordingIcon]: ../media/clear-recording-icon.msft.png  
[ImageCollectGarbageIcon]: ../media/collect-garbage-icon.msft.png  
[ImageNextIcon]: ../media/next-icon.msft.png  
[ImagePanModeIcon]: ../media/pan-mode-icon.msft.png  
[ImagePreviousIcon]: ../media/previous-icon.msft.png  
[ImageRecordIcon]: ../media/record-icon.msft.png
[ImageRefreshPageIcon]: ../media/refresh-page-icon.msft.png  
[ImageResetTransformIcon]: ../media/reset-transform-icon.msft.png  
[ImageRotateModeIcon]: ../media/rotate-mode-icon.msft.png  
[ImageSearchCaseIcon]: ../media/search-case-icon.msft.png  
[ImageSearchRegexIcon]: ../media/search-regex-icon.msft.png  
[ImageShowHeaviestStackIcon]: ../media/show-heaviest-stack-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft Docs"  
[DevToolsCommandMenu]: ../command-menu/index.md#open-the-command-menu "コマンド メニューを開く - Microsoft Edge DevTools コマンド メニューを使用してコマンドを実行する |Microsoft Docs"  
[DevtoolsEvaluatePerformanceGettingStarted]: ./index.md "ランタイム パフォーマンスの分析を開始する |Microsoft Docs"  

[ActivityTabsDemo]: https://microsoft-edge-chromium-devtools.glitch.me/perf/activitytabs.html "アクティビティ タブのデモ |不具合"  

[ChromiumDebugColors]: https://cs.chromium.org/chromium/src/cc/debug/debug_colors.cc "debug_colors.cc - コード検索"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/reference) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
