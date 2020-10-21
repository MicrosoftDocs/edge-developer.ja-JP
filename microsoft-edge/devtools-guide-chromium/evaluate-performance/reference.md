---
description: Microsoft Edge DevTools でのパフォーマンスの記録と分析に関するすべての方法を参照します。
title: パフォーマンス分析リファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: d135f83273842a1e128df0bb346f0f126e2fbe8d
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125140"
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

このページでは、パフォーマンスの分析に関連する Microsoft Edge DevTools の機能について包括的にご参照ください。  

[Microsoft Edge DevTools][MicrosoftEdgeDevTools]を使ってページのパフォーマンスを分析する方法については、ガイド付きチュートリアルの「[実行時のパフォーマンスの分析][DevtoolsEvaluatePerformanceGettingStarted]」を参照してください。  

## レコードのパフォーマンス  

### 実行時のパフォーマンスを記録する  

読み込みとは異なり、実行中にページのパフォーマンスを分析する場合は、実行時のパフォーマンスを記録します。  

1.  分析対象のページに移動します。  
1.  DevTools で [ **パフォーマンス** ] タブをクリックします。  
1.  [ **レコード** \ ( ![ レコードアイコン ][ImageRecordIcon] \)] を選びます。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-record-highlight.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-record-highlight.msft.png":::
       **Record**  
    :::image-end:::  
    
1.  ページを操作します。  DevTools は、操作の結果として発生するすべてのページアクティビティを記録します。  
1.  [ **記録** ] をもう一度選択するか、[ **停止** ] を選択して記録を停止します。  
    
### 読み込みのパフォーマンスの記録  

実行時とは異なり、読み込み中にページのパフォーマンスを分析する場合は、読み込みのパフォーマンスを記録します。  

1.  分析対象のページに移動します。  
1.  DevTools の [ **パフォーマンス** ] パネルを開きます。  
1.  [ **ページの更新** ] を選び ![ ます (ページを更新 ][ImageRefreshPageIcon] します)。  DevTools では、ページが更新されている間はパフォーマンスのメトリックが記録され、読み込みが完了してから数秒間、自動的に記録が停止します。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-refresh-button.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-refresh-button.msft.png":::
       **ページの更新**  
    :::image-end:::  
    
DevTools は、ほとんどのアクティビティが発生したレコーディングの部分に自動的にズームインします。  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-refreshed.msft.png":::
   ページ読み込みの記録  
:::image-end:::  

### 記録中にスクリーンショットをキャプチャする  

記録中にすべてのフレームのスクリーンショットをキャプチャするには、[ **スクリーンショット** ] チェックボックスをオンにします。  

:::image type="complex" source="../media/evaluate-performance-performance-capture-screenshots-checkbox.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-capture-screenshots-checkbox.msft.png":::
   **スクリーンショット**のチェックボックス  
:::image-end:::  

スクリーン [ショットを表示](#view-a-screenshot) して、スクリーンショットを操作する方法を学習します。  

### 記録中にガベージコレクションを強制する  

ページの記録中に、ガーベジコレクションを強制するには、[ガーベジの **収集** \ ![ ] (ガーベジアイコンの収集 ][ImageCollectGarbageIcon] ) を選択します。  

:::image type="complex" source="../media/evaluate-performance-performance-collect-garbage-button.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-collect-garbage-button.msft.png":::
   ガーベジの収集  
:::image-end:::  

### レコーディング設定を表示する  

[ **キャプチャの設定** ] ( ![ キャプチャ設定) を選択 ][ImageCaptureSettingsIcon] すると、devtools がパフォーマンスの記録をキャプチャする方法に関連するその他の設定を表示できます。  

:::image type="complex" source="../media/evaluate-performance-performance-capture-settings-button-open-drawer.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-capture-settings-button-open-drawer.msft.png":::
   [ **キャプチャの設定** ] セクション  
:::image-end:::  

### JavaScript のサンプルを無効にする  

記録の **メイン** セクションには、記録中に呼び出された JavaScript 関数の詳細なコールスタックが既定で表示されます。  次の呼び出し履歴を無効にするには:  

1.  [ **キャプチャの設定** ] メニューを開きます。  [ [レコーディング設定の表示]](#show-recording-settings)に移動します。  
1.  [ **JavaScript のサンプルを無効** にする] チェックボックスをオンにします。  
1.  ページの記録を取ります。  
    
次の2つの図は、JavaScript サンプルの無効化と有効化の違いを示しています。  サンプリングが無効になっている場合、記録の **メイン** セクションは、JavaScript のすべての呼び出し履歴を省略しているため、非常に短くなります。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-on.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-on.msft.png":::
         JS サンプルが無効になっている場合のレコーディングの例  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off.msft.png":::
         JS サンプルが有効になっている場合のレコーディングの例  
      :::image-end:::  
   :::column-end:::
:::row-end:::

### 記録中にネットワークを調整する  

記録中にネットワークを調整するには:  

1.  [ **キャプチャの設定** ] メニューを開きます。  [ [レコーディング設定の表示]](#show-recording-settings)に移動します。  
1.  **ネットワーク**を適切な調整レベルに設定します。  
    
### 記録中に CPU を調整する  

記録中に CPU を調整するには:  

1.  [ **キャプチャの設定** ] メニューを開きます。  [ [レコーディング設定の表示]](#show-recording-settings)に移動します。  
1.  **CPU**を目的の調整レベルに設定します。  
    
調整は、コンピューターの機能を基準とします。  たとえば、 **2 倍速の遅延** オプションを使うと、CPU は通常の2倍の速度で動作します。  モバイルデバイスのアーキテクチャはデスクトップとノート pc とは大きく異なりますので、DevTools はモバイルデバイスの Cpu を実際にシミュレートするわけではありません。  

### 高度な描画インストルメンテーションを有効にする  

詳細な描画インストルメンテーションを表示するには:  

1.  [ **キャプチャの設定** ] メニューを開きます。  [ [レコーディング設定の表示]](#show-recording-settings)に移動します。  
1.  **[高度な描画インストルメンテーション (低速) を有効にする**] チェックボックスをオンにします。  

ペイント情報を操作する方法については、「 [レイヤーの表示](#view-layers-information) と [ペイントプロファイラーの表示](#view-paint-profiler)」を参照してください。  

## レコーディングを保存する  

レコーディングを保存するには、右クリックして、[ **プロファイルの保存**] を選択します。  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-save-profile.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-save-profile.msft.png":::
   **プロフィールの保存**  
:::image-end:::  

## レコーディングを読み込む  

レコーディングを読み込むには、右クリックして、[ **プロファイルの読み込み**] を選択します。  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-load-profile.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-load-profile.msft.png":::
   **プロファイルの読み込み**  
:::image-end:::  

## 前の記録をクリアする  

レコーディングを作成したら、[ **レコーディングのクリア** ] (録音アイコンの ![ クリア) を押して、[ ][ImageClearRecordingIcon] **パフォーマンス** ] パネルからその記録をクリアします。  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-clear-button.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-clear-button.msft.png":::
   **レコーディングのクリア**  
:::image-end:::  

## パフォーマンスの記録を分析する  

[実行時のパフォーマンス](#record-runtime-performance)または[レコードの読み込みのパフォーマンス](#record-load-performance)を記録すると、**パフォーマンス**パネルに多くのデータが表示され、発生した処理のパフォーマンスを分析できます。  

### レコーディングの一部を選択する  

[ **概要** ] でマウスを左右にドラッグして、レコーディングの一部を選択します。  **概要**は、 **FPS**、 **CPU**、および**ネット**チャートを含むセクションです。  

:::image type="complex" source="../media/evaluate-performance-performance-zoom-highlighted.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-zoom-highlighted.msft.png":::
   **概要**の上でマウスをドラッグして拡大  
:::image-end:::  

キーボードを使用して部分を選択するには、次の操作を行います。  

1.  **メイン**セクションの背景をクリックするか、[**操作**]、[**ネットワーク**]、[ **GPU**] などの横にあるセクションのいずれかをクリックします。  このキーボードワークフローは、これらのセクションのいずれかがフォーカスされている場合にのみ動作します。  
1.  それぞれ、、、[左へ移動]、[縮小]、 `W` `A` `S` [右へ移動] の各キーを使用し `D` ます。  

トラックパッドを使用して部分を選択するには、次の操作を行います。  

1.  [ **概要** ] セクションまたは [ **詳細** ] セクションの上にマウスポインターを置きます。  [ **概要** ] セクションは、 **FPS**、 **CPU**、および **正味** グラフを含む領域です。  [ **詳細** ] セクションは、 **メイン** セクション、[ **操作** ] セクションなどを含む領域です。  
1.  2本の指で上方向にスワイプして縮小し、左方向にスワイプして左へ移動し、下方向にスワイプしてズームインし、右にスワイプして右に移動します。  

**メイン**セクションまたはそのいずれかの近隣にある長い炎のグラフをスクロールするには、上下にドラッグしてクリックしたままにします。  左または右にドラッグして、録音中の部分を移動します。  

### アクティビティを検索する  

[ `Control` + `F` \ (Windows, Linux \)] または [\ (macOS \)] を選択して、 `Command` + `F` **パフォーマンス**パネルの下部にある [検索] ボックスを開きます。  

:::image type="complex" source="../media/evaluate-performance-performance-search-regex.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-search-regex.msft.png":::
   検索ボックス  
:::image-end:::  

クエリに一致するアクティビティを移動するには、次の操作を行います。  

*   **前**の \ ( ![ 前の ][ImagePreviousIcon] \) と**次**の \ (次の \) ボタンを使用し ![ ][ImageNextIcon] ます。  
*   [前へ] を選択するか、[次へ] を選択し `Shift` + `Enter` `Enter` ます。  

クエリの設定を変更するには:  

*   [ **大文字** と小文字を区別する] を押して ![ ][ImageSearchCaseIcon] 、クエリの大文字と小文字を区別します。  
*   **Regex** ![ ][ImageSearchRegexIcon] クエリで正規表現を使用するには、regex \ (regex \) を押します。  

検索ボックスを非表示にするには、 **[キャンセル**] をクリックします。  

### メインスレッドアクティビティの表示  

**メイン**セクションを使って、ページのメインスレッドで発生したアクティビティを表示します。  

:::image type="complex" source="../media/evaluate-performance-performance-main-zoomed.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-main-zoomed.msft.png":::
   **メイン**セクション  
:::image-end:::  

イベントをクリックすると、[ **概要** ] タブにそのイベントの詳細情報が表示されます。 DevTools では、選択したイベントの概要が示されます。  

:::image type="complex" source="../media/evaluate-performance-performance-summary-me.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-summary-me.msft.png":::
   [ `anonymous` **概要** ] タブの関数についての詳細  
:::image-end:::  

DevTools は、炎グラフによるメインスレッドアクティビティを表します。  X 軸は、時間の経過に伴う記録を表します。  Y 軸は、呼び出しスタックを表します。  一番上にあるイベントは、その下にあるイベントを発生させます。  

:::image type="complex" source="../media/evaluate-performance-performance-main-flame-chart.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-main-flame-chart.msft.png":::
   炎のグラフ  
:::image-end:::  

上の図では、 `click` イベントが53で発生し `Function Call` `activitytabs.js` ています。  次 `Function Call` に、匿名関数が呼び出されたことを確認します。  呼び出された匿名関数が呼び出され `a` ます。これが呼び出され `wait` `Minor GC` ます。  

DevTools では、スクリプトのランダムな色が割り当てられます。  前の図では、1つのスクリプトからの関数呼び出しは色が緑になっています。  別のスクリプトからの呼び出しは、色ベージュになります。  濃い黄色はスクリプトアクティビティを表し、紫色のイベントはレンダリングアクティビティを表します。  これらの暗い黄と紫色のイベントは、すべての記録で一貫しています。  

JavaScript 呼び出しの詳細な炎グラフを非表示にする場合は、「 [javascript サンプルを無効](#disable-javascript-samples) にする」に移動します。  JS サンプルが無効になっている場合は、前の図などの上位レベルのイベントのみが表示され `Event: click` `Function Call` ます。  

### テーブルのアクティビティを表示する  

ページを記録したら、 **メイン** セクションに依存してアクティビティを分析する必要はありません。  DevTools には、アクティビティを分析するための3つの表形式ビューも用意されています。  各ビューには、次のような操作があります。  

*   最も作業を引き起こしているルートアクティビティを表示するには、[ [通話ツリー] タブ](#the-call-tree-tab)を使用します。  
*   最も多くの時間を費やしたアクティビティを表示する場合は、[ [Bottom-Up] タブ](#the-bottom-up-tab)を使用します。  
*   記録中に発生した順番でアクティビティを表示する場合は、 [[イベントログ] タブ](#the-event-log-tab)を使用します。  
    
> [!NOTE]
> 次の3つのセクションはすべて同じデモを示しています。  [アクティビティ] タブの [デモ][ActivityTabsDemo]で、自分でデモを実行します。  

#### ルートアクティビティ  

[**通話ツリー** ] タブ、[**ボトムアップ**] タブ、[**イベントログ**] の各セクションで説明されている**ルートアクティビティ**の概念について説明します。  

ルートアクティビティは、ブラウザーが何らかの操作を実行する原因となります。  たとえば、ページをクリックすると、ブラウザーで `Event` ルートアクティビティとしてアクティビティが発生します。  これにより、ハンドラーが実行される `Event` 可能性があります。  

**メイン**セクションの炎チャートでは、ルートアクティビティはグラフの一番上にあります。  [ **コールツリー** ] タブと [ **イベントログ** ] タブでは、ルートアクティビティはトップレベルのアイテムです。  

ルートアクティビティの例について [は、[通話ツリー] タブ](#the-call-tree-tab) に移動します。  

#### [通話ツリー] タブ  

[ **呼び出しツリー** ] タブを使用して、最も作業を発生させる [ルートアクティビティ](#root-activities) を表示します。  

[ **通話ツリー** ] タブには、レコーディングの選択した部分のアクティビティのみが表示されます。  部分を選択する方法については [、「記録の一部を選択する」](#select-a-portion-of-a-recording) を参照してください。  

:::image type="complex" source="../media/evaluate-performance-performance-call-tree.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-call-tree.msft.png":::
   [ **通話ツリー** ] タブ  
:::image-end:::  

上の図では、"and" など、" **アクティビティ** " 列の項目の最上位レベルが `Evaluate Script` `Parse HTML` ルートアクティビティです。  入れ子は、呼び出しスタックを表します。  たとえば、上の図のように、という問題が `Parse HTML` 発生しました `Evaluate Script` `Compile Script` `(anonymous)` 。  

**Self time** は、そのアクティビティに直接費やした時間を表します。  **合計時間** は、そのアクティビティまたはいずれかの子に費やした時間を表します。  

列によってテーブルが並べ替えられるように、[ **自己時間**]、[ **合計時間**]、または [ **アクティビティ** ] を選択します。  

[ **フィルター** ] テキストボックスを使用して、アクティビティ名ごとにイベントをフィルター処理します。  

既定では、 **グループ化** メニューは [ **グループ化なし**] に設定されます。  [ **グループ化** ] メニューを使用して、さまざまな条件に基づいてアクティビティテーブルを並べ替えます。  

**Show Heaviest Stack** ![ ][ImageShowHeaviestStackIcon] **アクティビティ**テーブルの右側に別のテーブルを表示するには、[最も高いスタックを表示] を選びます。  [アクティビティ] をクリックして、最も **重いスタック** テーブルにデータを入力します。  最も大きな **スタック** テーブルには、選択したアクティビティのどの子が最も時間がかかるかが示されます。  

#### [Bottom-Up] タブ  

[ **ボトムアップ** ] タブを使用して、集計で最も時間のかかるアクティビティを表示します。  

**下**のタブには、レコーディングの選択した部分のアクティビティのみが表示されます。  部分を選択する方法については [、「記録の一部を選択する」](#select-a-portion-of-a-recording) を参照してください。  

:::image type="complex" source="../media/evaluate-performance-performance-bottoms-up.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-bottoms-up.msft.png":::
   [ **ボトムアップ** ] タブ  
:::image-end:::  

前の図の **メイン** セクションの炎のグラフでは、ほとんどの時間が実行されていた時間に移動 `Parse HTML` します。  前の図の **下部** にある [上位] タブのアクティビティは `Parse HTML` です。  <!--In the flame chart of the previous figure, the yellow below the calls to `wait` are actually thousands of `Minor GC` calls.  -->  **下**のタブに移動します。次に、最も負荷の高いアクティビティは `Layout` です。  

[ **自己時刻** ] 列は、すべてのオカレンスにわたって、そのアクティビティで直接費やした合計時間を表します。  

[ **合計時間** 」列は、そのアクティビティまたはいずれかの子に費やした集計時間を表します。  

#### [イベントログ] タブ  

[ **イベントログ** ] タブを使用して、記録中に発生した順序でアクティビティを表示します。  

[ **イベントログ** ] タブには、記録の選択されている部分のアクティビティのみが表示されます。  部分を選択する方法については [、「記録の一部を選択する」](#select-a-portion-of-a-recording) を参照してください。  

:::image type="complex" source="../media/evaluate-performance-performance-event-log.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-event-log.msft.png":::
   [ **イベントログ** ] タブ  
:::image-end:::  

[ **開始時刻** ] 列は、そのアクティビティが開始されたポイントを表します。レコーディングの開始日を基準としています。  たとえば、 `175.7 ms` 前の図で選んだ項目の開始時刻は、記録を開始した後にアクティビティが175.7 ミリ秒で開始されたことを意味します。  

**Self time**列は、そのアクティビティに直接費やした時間を表します。  

**合計時間**列は、そのアクティビティまたはその子のいずれかに直接費やした時間を表します。  

[ **開始時刻**]、[ **自己時刻**]、または [ **合計時間** ] を選択して、その列を基準にしてテーブルを並べ替えます。

[ **フィルター** ] テキストボックスを使って、名前でアクティビティをフィルター処理します。  

[ **継続時間** ] メニューを使用して、1ミリ秒または15ミリ秒未満のアクティビティを除外します。  既定では、[ **期間** ] メニューは [ **すべて**] に設定されており、すべてのアクティビティが表示されます。  

**読み込み**、**スクリプト**、**レンダリング**、または**Painting**のチェックボックスを無効にして、それらのカテゴリのすべてのアクティビティをフィルター処理します。  

### GPU アクティビティの表示  

**Gpu セクションの**gpu アクティビティを表示します。  

:::image type="complex" source="../media/evaluate-performance-performance-gpu-zoomed.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-gpu-zoomed.msft.png":::
   **GPU**セクション  
:::image-end:::  

### ラスターアクティビティを表示する  

**ラスターセクションで**ラスターアクティビティを表示します。  

:::image type="complex" source="../media/evaluate-performance-performance-raster.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-raster.msft.png":::
   **ラスター**セクション  
:::image-end:::  

### ビューの操作  

記録中に発生したユーザー操作を見つけて分析するには、[ **対話** ] セクションを使用します。  

:::image type="complex" source="../media/evaluate-performance-performance-interactions-animation.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-interactions-animation.msft.png":::
   [ **操作** ] セクション  
:::image-end:::  

対話式の下部にある赤い線は、メインスレッドの待機に費やされた時間を表します。  

[ファイルの **概要** ] タブで、操作をクリックして詳細情報を表示します。  

### 1秒あたりのフレーム数 (FPS) の分析  

DevTools には、1秒あたりのフレームの分析方法が多数用意されています。  

*   [Fps チャート](#the-fps-chart)を使用して、記録中の fps の概要を把握します。  
*   [[フレーム] セクション](#the-frames-section)を使用して、特定のフレームの所要時間を表示します。  
*   ページの実行時に、fps のリアルタイムの推定に **fps メーター** を使用します。  [FPS メーターでリアルタイムのフレーム/秒を表示するには、次の](#view-frames-per-second-in-realtime-with-the-fps-meter)操作を行います。  
    
#### FPS グラフ  

**FPS**グラフは、記録中のフレームレートの概要を示しています。  通常、緑色のバーが大きくなるほど、フレームレートが向上します。  

**FPS**グラフの上に赤いバーが表示されるのは、ユーザーエクスペリエンスが損なわれている可能性が高いため、フレームレートが低下するという警告です。  

:::image type="complex" source="../media/evaluate-performance-performance-fps-highlight.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-fps-highlight.msft.png":::
   **FPS**グラフ  
:::image-end:::  

#### [フレーム] セクション  

**フレーム**セクションでは、特定のフレームの所要時間が正確に示されます。  

Frame の上にマウスポインターを移動すると、ヒントが表示され、詳細情報が表示されます。  

:::image type="complex" source="../media/evaluate-performance-performance-frames-hover.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-frames-hover.msft.png":::
   フレームの上にマウスポインターを置く  
:::image-end:::  

フレームをクリックすると、[ **概要** ] タブに、フレームに関するさらに詳しい情報が表示されます。 DevTools では、選択したフレームが青色で示されます。  

:::image type="complex" source="../media/evaluate-performance-performance-frames-summary.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-frames-summary.msft.png":::
   [ **概要** ] タブでフレームを表示する  
:::image-end:::  

### ネットワーク要求を表示する  

[ **ネットワーク** ] セクションを展開すると、記録中に発生した、ウォーターフォールのネットワーク要求が表示されます。  

:::image type="complex" source="../media/evaluate-performance-performance-network.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-network.msft.png":::
   [ **ネットワーク** ] セクション  
:::image-end:::  

要求は、次のように色分けされます。  

*   HTML: 青  
*   CSS: 紫  
*   JS: 黄  
*   画像: 緑  
    
[ファイルの **概要** ] タブで要求をクリックすると、詳細情報が表示されます。 たとえば、上の図では、[ **概要** ] タブには、[ **ネットワーク** ] セクションで選択された青い要求についての詳細情報が表示されています。  

要求の左上の濃い青色の正方形は、優先度の高い要求であることを意味します。  薄い青色の正方形は、優先度が低いことを意味します。  たとえば、前の図では、青色の選択された要求の優先度は高く、緑の1つは優先度の低いものです。  

次の図のうちの1つ目では、要求は `www.bing.com` 左側にある線で表され、中央に暗い部分と薄い部分があるバー、右側に線が表示されます。  次の図の2に、[**ネットワーク**] パネルの [**タイミング**] タブに表示される同じ要求の対応表現を示します。  2つの表現が相互にマップされる方法を次に示します。

*   左側の行は、一連のイベントを含むすべての項目になり `Connection Start` ます。  つまり、これはすべて、排他的な前にあり `Request Sent` ます。  
*   バーの光部分は `Request Sent` と `Waiting (TTFB)` です。  
*   バーの暗い部分は `Content Download` です。  
*   適切な行は、基本的にメインスレッドの待機に費やされた時間です。  これは、[ **タイミング** ] タブには表示されません。  
    
:::row:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-bing-performance-network.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-bing-performance-network.msft.png":::
         要求の線の表示 `www.bing.com`  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-bing-network-timing.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-bing-network-timing.msft.png":::
         **ネットワーク**ツール  
::: イメージ終了:::  
   :::column-end:::
:::row-end:::

### メモリメトリックの表示  

[ **メモリ** ] チェックボックスを有効にして、最後の記録からメモリ指標を表示します。  

:::image type="complex" source="../media/evaluate-performance-performance-memory-highlight.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-memory-highlight.msft.png":::
   **メモリ**チェックボックス  
:::image-end:::  

DevTools で、[**概要**] タブの上に新しい**メモリ**グラフが表示されます。 また、[**ヒープ**] という新しいグラフも表示**されます**。  **ヒープ**グラフは、**メモリ**グラフの**JS ヒープ**行と同じ情報を提供します。  

:::image type="complex" source="../media/evaluate-performance-performance-memory-chart.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-memory-chart.msft.png":::
   メモリメトリック  
:::image-end:::  

グラフ上の色付きの線は、グラフ上の色付きのチェックボックスにマップされます。  
チェックボックスを無効にして、そのカテゴリをグラフから非表示にする。  

グラフには、現在選択されているレコーディングの領域のみが表示されます。  たとえば、上の図では、 **メモリ** グラフは 400 ms マークの前後にあるメモリ使用量のみを 1750 ms マークに示しています。  

### レコーディングの一部の継続時間を表示する  

**Network**や**Main**などのセクションを分析するときに、特定のイベントの所要時間をより正確に予測する必要がある場合があります。  長押しして長押しし、 `Shift` 左または右にドラッグしてレコーディングの一部を選択します。  選択範囲の一番下にある DevTools は、その部分の所要時間を示します。  

:::image type="complex" source="../media/evaluate-performance-performance-main-duration.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-main-duration.msft.png":::
   レコーディングの一部の継続時間を表示する  
:::image-end:::  

### スクリーンショットを表示する  

[記録中にスクリーンショットをキャプチャ](#capture-screenshots-while-recording)して、スクリーンショットを有効にする方法について説明します。  

**概要**にマウスポインターを合わせると、その時点でページがどのように表示されたかを示すスクリーンショットが表示されます。  **概要**は、 **CPU**、 **FPS**、および**ネット**チャートを含むセクションです。  

:::image type="complex" source="../media/evaluate-performance-performance-screenshots-hover.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-screenshots-hover.msft.png":::
   スクリーンショットを表示する  
:::image-end:::  

**フレーム**セクションのフレームをクリックしてスクリーンショットを表示することもできます。  DevTools では、[ **概要** ] タブにスクリーンショットの小さなバージョンが表示されます。  

:::image type="complex" source="../media/evaluate-performance-performance-summary-preview.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-summary-preview.msft.png":::
   [ **概要** ] タブにスクリーンショットを表示する  
:::image-end:::  

[ **概要** ] タブでサムネイルをクリックして、スクリーンショットを拡大します。  

:::image type="complex" source="../media/evaluate-performance-performance-summary-preview-select.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-summary-preview-select.msft.png":::
   [ **概要** ] タブでスクリーンショットを拡大する  
:::image-end:::  

### レイヤー情報の表示  

フレームに関する高度なレイヤー情報を表示するには、次の操作を行います。  

1.  [高度な描画インストルメンテーションを有効に](#enable-advanced-paint-instrumentation)します。  
1.  **フレームセクションで**フレームを選択します。  [開発ツール] では、[新しい **レイヤー** ] タブの [ **イベントログ** ] タブの横に、レイヤーに関する情報が表示されます。  
    
    :::image type="complex" source="../media/evaluate-performance-layers-all.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-layers-all.msft.png":::
       [ **レイヤー** ] ウィンドウ  
    :::image-end:::  
    
レイヤーをポイントすると、図の中で強調表示されます。  

:::image type="complex" source="../media/evaluate-performance-performance-frames-document-nav-bar-highlighted.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-frames-document-nav-bar-highlighted.msft.png":::
   レイヤーを強調表示する  
:::image-end:::  

ダイアグラムを移動するには、次の操作を行います。  

*   **Pan Mode** ![ ][ImagePanModeIcon] X 軸と Y 軸に沿って移動するには、[パンモード] (pan モード \) を選択します。  
*   Z 軸に沿って回転するには、[ **回転モード** \ ( ![ 回転モード ][ImageRotateModeIcon] \)] を選びます。  
*   [ **変換のリセット** ] ( ![ 変形 ][ImageResetTransformIcon] のリセット) を選択して、図を元の位置にリセットします。  
    
### ペイントプロファイラーの表示  

ペイントイベントに関する詳細情報を表示するには、次の操作を行います。  

1.  [高度な描画インストルメンテーションを有効に](#enable-advanced-paint-instrumentation)します。  
1.  **メイン**セクションで**Paint**イベントを選択します。  
    
    :::image type="complex" source="../media/evaluate-performance-paint-profiler.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-paint-profiler.msft.png":::
       [ **ペイントプロファイラー** ] タブ  
    :::image-end:::  
    
## [レンダリング] タブでのレンダリングのパフォーマンスの分析  

[ **レンダリング** ] タブの機能を使用すると、ページのレンダリングパフォーマンスを視覚化できます。  

[ **レンダリング** ] タブを開くには、次の操作を行います。  

1.  [コマンドメニューを開き][DevToolsCommandMenu]ます。  
1.  入力を開始し `Rendering` 、を選択し `Show Rendering` ます。  DevTools は、DevTools ウィンドウの下部にある [ **レンダリング** ] タブを表示します。  
    
    :::image type="complex" source="../media/evaluate-performance-console-drawer-rendering.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-console-drawer-rendering.msft.png":::
       [ **レンダリング** ] タブ  
    :::image-end:::  
    
### FPS メーターを使ってリアルタイムで1秒あたりのフレームを表示する  

**FPS メーター**は、ビューポートの右上隅に表示されるオーバーレイです。  ページの実行時に、リアルタイムでの FPS の推定値が提供されます。  **FPS メーター**を開くには:  

1.  [ **レンダリング** ] タブを開きます。 Na [[レンダリング] タブを使って、レンダリングのパフォーマンスを分析](#analyze-rendering-performance-with-the-rendering-tab)します。  
1.  [ **FPS メーター** ] チェックボックスをオンにします。  
    
    :::image type="complex" source="../media/evaluate-performance-jank-console-rendering-frame-rate.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-jank-console-rendering-frame-rate.msft.png":::
       **FPS メーター**  
    :::image-end:::  
    
### ペイントの点滅でリアルタイムで描画イベントを表示する  

[ペイントのフラッシュ] を使って、ページ上のすべての描画イベントをリアルタイムで表示します。  ページの一部が再描画されるたびに、DevTools でそのセクションの輪郭が緑色で示されます。  

ペイントのフラッシュを有効にするには:  

1.  [ **レンダリング** ] タブを開きます。 [[レンダリング] タブで移動して、レンダリングのパフォーマンスを分析](#analyze-rendering-performance-with-the-rendering-tab)します。  
1.  [ **ペイントの点滅** ] チェックボックスをオンにします。  
    
    :::image type="complex" source="../media/evaluate-performance-jank-console-rendering-paint-flashing.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-jank-console-rendering-paint-flashing.msft.png":::
       **ペイントの点滅**  
    :::image-end:::  
    
### レイヤーの枠線を使用してレイヤーを重ねて表示する  

レイヤー境界 **線** を使用して、レイヤーの境界線とタイルをページの上に重ねて表示します。  

レイヤーの境界線を有効にするには:  

1.  [ **レンダリング** ] タブを開きます。 [[レンダリング] タブで移動して、レンダリングのパフォーマンスを分析](#analyze-rendering-performance-with-the-rendering-tab)します。  
1.  [ **レイヤー罫線** ] チェックボックスをオンにします。  
    
    :::image type="complex" source="../media/evaluate-performance-devtools-console-rendering-layer-borders.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-devtools-console-rendering-layer-borders.msft.png":::
       **レイヤーの枠線**  
    :::image-end:::  
    
Debug_colors のコメントに移動して、codings の説明を参照してください[。][ChromiumDebugColors]  

### スクロールパフォーマンスの問題をリアルタイムで見つける  

スクロールパフォーマンスの問題を使って、スクロールに関連するイベントリスナーを持つページの要素を特定し、ページのパフォーマンスに悪影響を与える可能性があります。  
DevTools では、青緑で問題が発生する可能性のある要素について説明します。  

スクロールパフォーマンスの問題を表示するには:  

1.  [ **レンダリング** ] タブを開きます。 [[レンダリング] タブで移動して、レンダリングのパフォーマンスを分析](#analyze-rendering-performance-with-the-rendering-tab)します。  
1.  [ **パフォーマンスの問題のスクロール** ] チェックボックスをオンにします。  
    
    :::image type="complex" source="../media/evaluate-performance-bing-console-drawer-rendering-scrolling-performance-issues.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-bing-console-drawer-rendering-scrolling-performance-issues.msft.png":::
       **スクロールパフォーマンスの問題** は、非レイヤーのビューポートに制約のあるオブジェクトによってパフォーマンスの低下が発生する可能性があることを示します。  
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

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  
[DevToolsCommandMenu]: ../command-menu/index.md#open-the-command-menu "コマンドメニューを開きます。 [Microsoft Edge DevTools] コマンドメニューでコマンドを実行します。Microsoft ドキュメント"  
[DevtoolsEvaluatePerformanceGettingStarted]: ./index.md "実行時のパフォーマンスの分析を開始する |Microsoft ドキュメント"  

[ActivityTabsDemo]: https://microsoft-edge-chromium-devtools.glitch.me/perf/activitytabs.html "アクティビティタブのデモ |故障"  

[ChromiumDebugColors]: https://cs.chromium.org/chromium/src/cc/debug/debug_colors.cc "debug_colors cc-コードの検索"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/reference) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
