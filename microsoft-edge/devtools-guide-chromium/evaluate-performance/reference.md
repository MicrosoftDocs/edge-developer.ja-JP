---
title: 業績分析のリファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/29/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: acd6e3e68f89096cf80c08f0d0c3430ab31eaec1
ms.sourcegitcommit: 50991a04c18283a8890ae33fcc3491c0476c7684
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2020
ms.locfileid: "10611749"
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







# 業績分析のリファレンス   



このページでは、パフォーマンスの分析に関連する Microsoft Edge DevTools の機能について包括的にご参照ください。  

[Microsoft Edge DevTools][MicrosoftEdgeDevTools]を使用してページのパフォーマンスを分析する方法については、ガイド付きチュートリアルの「[実行時のパフォーマンスの分析][DevtoolsEvaluatePerformanceGettingStarted]」をご覧ください。  

## レコードのパフォーマンス   

### 実行時のパフォーマンスを記録する   

読み込みとは異なり、実行中にページのパフォーマンスを分析する場合は、実行時のパフォーマンスを記録します。  

1.  分析対象のページに移動します。  
1.  DevTools で [**パフォーマンス**] タブをクリックします。  
1.  [**レコードの記録**] をクリックし ![ ][ImageRecordIcon] ます。  
    
    > ##### 図 1  
    > **Record**  
    > ![Record][ImageRecord]  

1.  ページを操作します。  DevTools は、操作の結果として発生するすべてのページアクティビティを記録します。  
1.  [**記録**] をもう一度クリックするか、[**停止**] をクリックして記録を停止します。  

### 読み込みのパフォーマンスの記録   

実行時とは異なり、読み込み中にページのパフォーマンスを分析する場合は、読み込みのパフォーマンスを記録します。  

1.  分析対象のページに移動します。  
1.  DevTools の [**パフォーマンス**] パネルを開きます。  
1.  [**ページ** ![ の更新ページの更新] をクリックし ][ImageRefreshPageIcon] ます。  DevTools では、ページが更新されている間はパフォーマンスのメトリックが記録され、読み込みが完了してから数秒間、自動的に記録が停止します。  
    
    > ##### 図 2  
    > **ページの更新**  
    > ![ページの更新][ImageRefreshPage]  

DevTools は、ほとんどのアクティビティが発生したレコーディングの部分に自動的にズームインします。  

> ##### 図 3  
> ページ読み込みの記録  
> ![ページ読み込みの記録][ImageLoadRecording]  

### 記録中にスクリーンショットをキャプチャする   

記録中にすべてのフレームのスクリーンショットをキャプチャするには、[**スクリーンショット**] チェックボックスをオンにします。  

> ##### 図 4  
> **スクリーンショット**のチェックボックス  
> ![スクリーンショットのチェックボックス][ImageScreenshots]  

スクリーンショットを操作する方法について[は、「スクリーンショットを表示](#view-a-screenshot)する」をご覧ください。  

### 記録中にガベージコレクションを強制する   

ページを記録しているときに、[ガーベジコレクトの**収集**] をクリックして ![ ][ImageCollectGarbageIcon] ガベージコレクションを強制します。  

> ##### 図 5  
> ガーベジの収集  
> ![ガーベジの収集][ImageCollectGarbage]  

### レコーディング設定を表示する   

[**キャプチャ設定**キャプチャの設定] をクリックして、 ![ ][ImageCaptureSettingsIcon] devtools がパフォーマンスの記録をキャプチャする方法に関連するその他の設定を表示します。  

> ##### 図 6  
> [**キャプチャの設定**] セクション  
> ![[キャプチャの設定] セクション][ImageCaptureSettings]  

### JavaScript のサンプルを無効にする   

記録の**メイン**セクションには、記録中に呼び出された JavaScript 関数の詳細なコールスタックが既定で表示されます。  次の呼び出し履歴を無効にするには:  

1.  [**キャプチャの設定**] メニューを開きます。  「[レコーディング設定を表示する」を](#show-recording-settings)ご覧ください。  
1.  [ **JavaScript のサンプルを無効**にする] チェックボックスをオンにします。  
1.  ページの記録を取ります。  

[図 7](#figure-7)と[図 8](#figure-8)は、JavaScript サンプルの無効化と有効化の違いを示しています。  サンプリングが無効になっている場合、記録の**メイン**セクションは、JavaScript のすべての呼び出し履歴を省略しているため、非常に短くなります。  

> ##### 図 7  
> JS サンプルが無効になっている場合のレコーディングの例  
> ![JS サンプルが無効になっている場合のレコーディングの例][ImageJSSamplesDisabled]  

> ##### 図 8  
> JS サンプルが有効になっている場合のレコーディングの例  
> ![JS サンプルが有効になっている場合のレコーディングの例][ImageJSSamplesEnabled]  

### 記録中にネットワークを調整する   

記録中にネットワークを調整するには:  

1.  [**キャプチャの設定**] メニューを開きます。  「[レコーディング設定を表示する」を](#show-recording-settings)ご覧ください。  
1.  **ネットワーク**を適切な調整レベルに設定します。  

### 記録中に CPU を調整する   

記録中に CPU を調整するには:  

1.  [**キャプチャの設定**] メニューを開きます。  「[レコーディング設定を表示する」を](#show-recording-settings)ご覧ください。  
1.  **CPU**を目的の調整レベルに設定します。  

調整は、コンピューターの機能を基準とします。  たとえば、 **2 倍速の遅延**オプションを使うと、CPU は通常の2倍の速度で動作します。  モバイルデバイスのアーキテクチャはデスクトップとノート pc とは大きく異なりますので、DevTools はモバイルデバイスの Cpu を実際にシミュレートするわけではありません。  

### 高度な描画インストルメンテーションを有効にする   

詳細な描画インストルメンテーションを表示するには:  

1.  [**キャプチャの設定**] メニューを開きます。  「[レコーディング設定を表示する」を](#show-recording-settings)ご覧ください。  
1.  **[高度な描画インストルメンテーション (低速) を有効にする**] チェックボックスをオンにします。  

ペイント情報を操作する方法については、「[レイヤーの表示](#view-layers-information)と[ペイントプロファイラーの表示](#view-paint-profiler)」を参照してください。  

## レコーディングを保存する   

レコーディングを保存するには、右クリックして、[**プロファイルの保存**] を選択します。  

> ##### 図 9  
> **プロフィールの保存**  
> ![プロフィールの保存][ImageSaveProfile]  

## レコーディングを読み込む   

レコーディングを読み込むには、右クリックして、[**プロファイルの読み込み**] を選択します。  

> ##### 図 10  
> **プロファイルの読み込み**  
> ![プロファイルの読み込み][ImageLoadProfile]  

## 前の記録をクリアする   

レコーディングを作成した後、[レコーディングのクリア]**を押して** ![ 、[ ][ImageClearRecordingIcon] **パフォーマンス**] パネルからその記録をクリアします。  

> ##### 図 11  
> レコーディングのクリア  
> ![レコーディングのクリア][ImageClearRecording]  

## パフォーマンスの記録を分析する   

[実行時のパフォーマンス](#record-runtime-performance)または[レコードの読み込みのパフォーマンス](#record-load-performance)を記録すると、**パフォーマンス**パネルに多くのデータが表示され、発生した処理のパフォーマンスを分析できます。  

### レコーディングの一部を選択する   

[**概要**] でマウスを左右にドラッグして、レコーディングの一部を選択します。  **概要**は、 **FPS**、 **CPU**、および**ネット**チャートを含むセクションです。  

> ##### 図 12  
> 概要の上でマウスをドラッグしてズーム  
> ![概要の上でマウスをドラッグしてズーム][ImageZoom]  

キーボードを使用して部分を選択するには、次の操作を行います。  

1.  **メイン**セクションの背景をクリックするか、[**操作**]、[**ネットワーク**]、[ **GPU**] などの横にあるセクションのいずれかをクリックします。  このキーボードワークフローは、これらのセクションのいずれかがフォーカスされている場合にのみ動作します。  
1.  それぞれ、、、[左へ移動]、[縮小]、 `W` `A` `S` [右へ移動] の各キーを使用し `D` ます。  

トラックパッドを使用して部分を選択するには、次の操作を行います。  

1.  [**概要**] セクションまたは [**詳細**] セクションの上にマウスポインターを置きます。  [**概要**] セクションは、 **FPS**、 **CPU**、および**正味**グラフを含む領域です。  [**詳細**] セクションは、**メイン**セクション、[**操作**] セクションなどを含む領域です。  
1.  2本の指で上方向にスワイプして縮小し、左方向にスワイプして左へ移動し、下方向にスワイプしてズームインし、右にスワイプして右に移動します。  

**メイン**セクションまたはそのいずれかの近隣にある長い炎のグラフをスクロールするには、上下にドラッグしてクリックしたままにします。  左または右にドラッグして、録音中の部分を移動します。  

### アクティビティを検索する   

[ `Control` + `F` \ (Windows \)] または [ `Command` + `F` \ (macOS \)] を押して、**パフォーマンス**パネルの下部にある [検索] ボックスを開きます。  

> ##### 図 13  
> ウィンドウの下部にある [検索] ボックスで regex を使用して、で始まるすべてのアクティビティを検索する `E`  
> ![検索ボックス][ImageSearch]  

クエリに一致するアクティビティを移動するには、次の操作を行います。  

*   **前** ![ と次のボタンを使用し ][ImagePreviousIcon] **Next** ![ ][ImageNextIcon] ます。  
*   を押して [前へ] を選択するか、[ `Shift` + `Enter` 次へ] を `Enter` 選択します。  

クエリの設定を変更するには:  

*   大文字と**小文字を**区別 ![ ][ImageSearchCaseIcon] します。クエリの大文字と小文字を区別します。  
*   **Regex** ![ ][ImageSearchRegexIcon] クエリで正規表現を使用するには、regex regex を押します。  

検索ボックスを非表示にするには、 **[キャンセル**] をクリックします。  

### メインスレッドアクティビティの表示   

**メイン**セクションを使って、ページのメインスレッドで発生したアクティビティを表示します。  

> ##### 図 14  
> **メイン**セクション  
> ![メインセクション][ImageMain]  

イベントをクリックすると、[**概要**] タブにそのイベントの詳細情報が表示されます。 DevTools では、選択したイベントの概要が示されます。  

> ##### 図 15  
> [ `anonymous` **概要**] タブの関数についての詳細  
> ![匿名関数の詳細については、[概要] タブを参照してください。][ImageMainEventSummary]  

DevTools は、炎グラフによるメインスレッドアクティビティを表します。  X 軸は、時間の経過に伴う記録を表します。  Y 軸は、呼び出しスタックを表します。  一番上にあるイベントは、その下にあるイベントを発生させます。  

> ##### 図 16  
> **メイン**セクションの炎のグラフ  
> ![炎のグラフ][ImageFlameChart]  

[図 16](#figure-16)では、イベントが53で発生しました `click` `Function Call` `activitytabs.js` 。  次 `Function Call` に、匿名関数が呼び出されたことを確認します。  呼び出された匿名関数が呼び出され `a` ます。これが呼び出され `wait` `Minor GC` ます。  

DevTools では、スクリプトのランダムな色が割り当てられます。  [図 16](#figure-16)では、1つのスクリプトからの関数の呼び出しは色が緑色になります。  別のスクリプトからの呼び出しは、色ベージュになります。  濃い黄色はスクリプトアクティビティを表し、紫色のイベントはレンダリングアクティビティを表します。  これらの暗い黄と紫色のイベントは、すべての記録で一貫しています。  

JavaScript 呼び出しの詳細な炎グラフを非表示にする場合は、「 [javascript のサンプルを無効](#disable-javascript-samples)にする」を参照してください。  JS サンプルが無効になっている場合は、図16などの上位レベルのイベントのみが表示され `Event: click` `Function Call` ます。 [Figure 16](#figure-16)  

### テーブルのアクティビティを表示する   

ページを記録したら、**メイン**セクションに依存してアクティビティを分析する必要はありません。  DevTools には、アクティビティを分析するための3つの表形式ビューも用意されています。  各ビューには、次のような操作があります。  

*   最も作業を引き起こしているルートアクティビティを表示するには、[ [**通話ツリー** ] タブ](#the-call-tree-tab)を使用します。  
*   最も多くの時間を費やしたアクティビティを表示する場合は、[ [**ボトムアップ**] タブ](#the-bottom-up-tab)を使用します。  
*   記録中に発生した順番でアクティビティを表示する場合は、 [[**イベントログ**] タブ](#the-event-log-tab)を使用します。  

> [!NOTE]
> 次の3つのセクションはすべて同じデモを示しています。  [アクティビティ] タブの[デモ][ActivityTabsDemo]で、自分でデモを実行します。  

#### ルートアクティビティ   

[**通話ツリー** ] タブ、[**ボトムアップ**] タブ、[**イベントログ**] の各セクションで説明されている**ルートアクティビティ**の概念について説明します。  

ルートアクティビティは、ブラウザーが何らかの操作を実行する原因となります。  たとえば、ページをクリックすると、ブラウザーで `Event` ルートアクティビティとしてアクティビティが発生します。  これにより、ハンドラーが実行される `Event` 可能性があります。  

**メイン**セクションの炎チャートでは、ルートアクティビティはグラフの一番上にあります。  [**コールツリー** ] タブと [**イベントログ**] タブでは、ルートアクティビティはトップレベルのアイテムです。  

ルートアクティビティの例について[は、「通話ツリー」タブ](#the-call-tree-tab)をご覧ください。  

#### [通話ツリー] タブ   

[**呼び出しツリー** ] タブを使用して、最も作業を発生させる[ルートアクティビティ](#root-activities)を表示します。  

[**通話ツリー** ] タブには、レコーディングの選択した部分のアクティビティのみが表示されます。  部分の選択方法については[、「レコーディングの一部を選択](#select-a-portion-of-a-recording)する」を参照してください。  

> ##### 図 17  
> [**通話ツリー** ] タブ  
> ![[通話ツリー] タブ][ImageCallTree]  

[図 17](#figure-17)では、"and" などの [**アクティビティ**] 列の項目の最上位レベルを示してい `Evaluate Script` `Parse HTML` ます。  入れ子は、呼び出しスタックを表します。  たとえば、[図 17](#figure-17)の場合は、という原因 `Parse HTML` `Evaluate Script` `Compile Script` と `(anonymous)` なります。  

**Self time**は、そのアクティビティに直接費やした時間を表します。  **合計時間**は、そのアクティビティまたはいずれかの子に費やした時間を表します。  

[**自己時刻**]、[**時間の合計**]、または [**アクティビティ**] をクリックして、テーブルをその列で並べ替えます。  

[**フィルター** ] テキストボックスを使用して、アクティビティ名ごとにイベントをフィルター処理します。  

既定では、**グループ化**メニューは [**グループ化なし**] に設定されます。  [**グループ化**] メニューを使用して、さまざまな条件に基づいてアクティビティテーブルを並べ替えます。  

[最も**重いスタック**を表示] をクリックし ![ ][ImageShowHeaviestStackIcon] て、**アクティビティ**テーブルの右側に別のテーブルを表示します。  [アクティビティ] をクリックして、最も**重いスタック**テーブルにデータを入力します。  最も大きな**スタック**テーブルには、選択したアクティビティのどの子が最も時間がかかるかが示されます。  

#### [ボトムアップ] タブ   

[**ボトムアップ**] タブを使用して、集計で最も時間のかかるアクティビティを表示します。  

**下**のタブには、レコーディングの選択した部分のアクティビティのみが表示されます。  部分の選択方法については[、「レコーディングの一部を選択](#select-a-portion-of-a-recording)する」を参照してください。  

> ##### 図18  
> [**ボトムアップ**] タブ  
> ![[ボトムアップ] タブ][ImageBottomUp]  

[図 18](#figure-18)の**メイン**セクションの炎のグラフでは、ほとんどの時間が実行されていたことについて説明し `Parse HTML` ます。  [図 18](#figure-18)の一番**下**のタブにある一番上のアクティビティは `Parse HTML` です。  <!--In the flame chart of [Figure 18](#figure-18), the yellow below the calls to `wait` are actually thousands of `Minor GC` calls.  -->  **下**のタブでは、次の最も負荷の高いアクティビティが表示されて `Layout` います。  

[**自己時刻**] 列は、すべてのオカレンスにわたって、そのアクティビティで直接費やした合計時間を表します。  

[**合計時間**」列は、そのアクティビティまたはいずれかの子に費やした集計時間を表します。  

#### [イベントログ] タブ   

[**イベントログ**] タブを使用して、記録中に発生した順序でアクティビティを表示します。  

[**イベントログ**] タブには、記録の選択されている部分のアクティビティのみが表示されます。  部分の選択方法については[、「レコーディングの一部を選択](#select-a-portion-of-a-recording)する」を参照してください。  

> ##### 図19  
> [**イベントログ**] タブ  
> ![[イベントログ] タブ][ImageEventLog]  

[**開始時刻**] 列は、そのアクティビティが開始されたポイントを表します。レコーディングの開始日を基準としています。  たとえば、 `175.7 ms` [図 19](#figure-19)で選択したアイテムの開始時刻は、記録を開始した後にアクティビティが175.7 ミリ秒で開始されたことを意味します。  

**Self time**列は、そのアクティビティに直接費やした時間を表します。  

**合計時間**列は、そのアクティビティまたはその子のいずれかに直接費やした時間を表します。  

[**開始時刻**]、[**自己時刻**]、または [**合計時間**] をクリックして、テーブルをその列で並べ替えます。

[**フィルター** ] テキストボックスを使って、名前でアクティビティをフィルター処理します。  

[**継続時間**] メニューを使用して、1ミリ秒または15ミリ秒未満のアクティビティを除外します。  既定では、[**期間**] メニューは [**すべて**] に設定されており、すべてのアクティビティが表示されます。  

**読み込み**、**スクリプト**、**レンダリング**、または**Painting**のチェックボックスを無効にして、それらのカテゴリのすべてのアクティビティをフィルター処理します。  

### GPU アクティビティの表示   

**Gpu セクションの**gpu アクティビティを表示します。  

> ##### 図20  
> **GPU**セクション  
> ![GPU セクション][ImageGpu]  

### ラスターアクティビティを表示する   

**ラスターセクションで**ラスターアクティビティを表示します。  

> ##### 図21  
> **ラスター**セクション  
> ![ラスターセクション][ImageRaster]  

### ビューの操作   

記録中に発生したユーザー操作を見つけて分析するには、[**対話**] セクションを使用します。  

> ##### 図22  
> [**操作**] セクション  
> ![[操作] セクション][ImageInteractions]  

対話式の下部にある赤い線は、メインスレッドの待機に費やされた時間を表します。  

[ファイルの**概要**] タブで、操作をクリックして詳細情報を表示します。  

### 1秒あたりのフレーム数 (FPS) の分析   

DevTools には、1秒あたりのフレームの分析方法が多数用意されています。  

*   [ **Fps**チャート](#the-fps-chart)を使用して、記録中の fps の概要を把握します。  
*   [[**フレーム**] セクション](#the-frames-section)を使用して、特定のフレームの所要時間を表示します。  
*   ページの実行時に、fps のリアルタイムの推定に**fps メーター**を使用します。  詳しく[は、「FPS メーターでリアルタイムのフレームを表示する](#view-frames-per-second-in-realtime-with-the-fps-meter)」をご覧ください。  

#### FPS グラフ   

**FPS**グラフは、記録中のフレームレートの概要を示しています。  通常、緑色のバーが大きくなるほど、フレームレートが向上します。  

**FPS**グラフの上に赤いバーが表示されるのは、ユーザーエクスペリエンスが損なわれている可能性が高いため、フレームレートが低下するという警告です。  

> ##### 図23  
> FPS グラフ  
> ![FPS グラフ][ImageFpsChart]  

#### [フレーム] セクション   

**フレーム**セクションでは、特定のフレームの所要時間が正確に示されます。  

Frame の上にマウスポインターを移動すると、ヒントが表示され、詳細情報が表示されます。  

> ##### 図24  
> フレーム上のマウスポインター  
> ![フレーム上のマウスポインター][ImageFramesSection]  

フレームをクリックすると、[**概要**] タブに、フレームに関するさらに詳しい情報が表示されます。 DevTools では、選択したフレームが青色で示されます。  

> ##### 図25  
> [**概要**] タブでのフレームの表示  
> ![[概要] タブでのフレームの表示][ImageFrameSummary]  

### ネットワーク要求を表示する   

[**ネットワーク**] セクションを展開すると、記録中に発生した、ウォーターフォールのネットワーク要求が表示されます。  

> ##### 図26  
> [**ネットワーク**] セクション  
> ![[ネットワーク] セクション][ImageNetworkRequest]  

要求は、次のように色分けされます。  

*   HTML: 青  
*   CSS: 紫  
*   JS: 黄  
*   画像: 緑  

[ファイルの**概要**] タブで要求をクリックすると、詳細情報が表示されます。 たとえば、[図 26](#figure-26)の [**概要**] タブには、[**ネットワーク**] セクションで選択された青い要求についての詳細情報が表示されています。  

要求の左上の濃い青色の正方形は、優先度の高い要求であることを意味します。  薄い青色の正方形は、優先度が低いことを意味します。  たとえば、[図 26](#figure-26)では、選択されている要求の優先度が高く、緑色の1つが低い優先度であることを示します。  

[図 27](#figure-27)では、要求は `www.bing.com` 左側の線で表され、中央に暗い部分と薄い部分があるバー、右側に線が表示されます。  [図 28](#figure-28)は、[**ネットワーク**] パネルの [**タイミング**] タブに表示される同じ要求の対応表現を示しています。  2つの表現が相互にマップされる方法を次に示します。

*   左側の行は、一連のイベントを含むすべての項目になり `Connection Start` ます。  つまり、これはすべて、排他的な前にあり `Request Sent` ます。  
*   バーの光部分は `Request Sent` と `Waiting (TTFB)` です。  
*   バーの暗い部分は `Content Download` です。  
*   適切な行は、基本的にメインスレッドの待機に費やされた時間です。  これは、[**タイミング**] タブには表示されません。  

> ##### 図27  
> 要求の線の表示 `www.bing.com`  
> ![Www.bing.com 要求の線の表示][ImageLineBar]  

> ##### 図28  
> 要求の [**タイミング**] タブの表示 `www.bing.com`  
> ![[ネットワーク] セクション][ImageTiming]  

### メモリメトリックの表示   

[**メモリ**] チェックボックスを有効にして、最後の記録からメモリ指標を表示します。  

> ##### 図29  
> **メモリ**チェックボックス  
> ![メモリチェックボックス][ImageMemory]  

DevTools で、[**概要**] タブの上に新しい**メモリ**グラフが表示されます。 また、[**ヒープ**] という新しいグラフも表示**されます**。  **ヒープ**グラフは、**メモリ**グラフの**JS ヒープ**行と同じ情報を提供します。  

> ##### 図30  
> メモリメトリック、[**概要**] タブの上  
> ![メモリメトリック][ImageMemoryMetrics]  

グラフ上の色付きの線は、グラフ上の色付きのチェックボックスにマップされます。  
チェックボックスを無効にして、そのカテゴリをグラフから非表示にする。  

グラフには、現在選択されているレコーディングの領域のみが表示されます。  たとえば、[図 30](#figure-30)の**メモリ**グラフでは、400 ms マークの前後にあるメモリ使用量のみが 1750 ms マークに表示されます。  

### レコーディングの一部の継続時間を表示する   

**Network**や**Main**などのセクションを分析するときに、特定のイベントの所要時間をより正確に予測する必要がある場合があります。  長押しして長押しし、 `Shift` 左または右にドラッグしてレコーディングの一部を選択します。  選択範囲の一番下にある DevTools は、その部分の所要時間を示します。  

> ##### 図31  
> `9.47ms`選択した部分の一番下にあるタイムスタンプは、その部分の所要時間を示します。  
> ![レコーディングの一部の継続時間を表示する][ImageDuration]  

### スクリーンショットを表示する   

スクリーンショットを有効にする方法については、「[記録中のスクリーンショットのキャプチャ](#capture-screenshots-while-recording)」をご覧ください。  

**概要**にマウスポインターを合わせると、その時点でページがどのように表示されたかを示すスクリーンショットが表示されます。  **概要**は、 **CPU**、 **FPS**、および**ネット**チャートを含むセクションです。  

> ##### 図32  
> スクリーンショットの表示  
> ![スクリーンショットの表示][ImageViewScreenshot]  

**フレーム**セクションのフレームをクリックしてスクリーンショットを表示することもできます。  DevTools では、[**概要**] タブにスクリーンショットの小さなバージョンが表示されます。  

> ##### 図33  
> フレームセクションのフレームをクリックすると、 `233.9ms` そのフレームのスクリーンショットが [**概要**] タブに表示さ**Frames**れます。  
> ![[概要] タブのスクリーンショットの表示][ImageFrameScreenshotSummary]  

[**概要**] タブでサムネイルをクリックして、スクリーンショットを拡大します。  

> ##### 図34  
> [**概要**] タブでサムネイルをクリックすると、devtools のスクリーンショットが表示されます。  
> ![[概要] タブのスクリーンショットを拡大する][ImageFrameScreenshotZoom]  

### レイヤー情報の表示   

フレームに関する高度なレイヤー情報を表示するには、次の操作を行います。  

1.  [高度な描画インストルメンテーションを有効に](#enable-advanced-paint-instrumentation)します。  
1.  **フレームセクションで**フレームを選択します。  [開発ツール] では、[新しい**レイヤー** ] タブの [**イベントログ**] タブの横に、レイヤーに関する情報が表示されます。  
    
    > ##### 図35  
    > [**レイヤー** ] ウィンドウ  
    > ![[レイヤー] ウィンドウ][ImageLayers]  
    
レイヤーをポイントすると、図の中で強調表示されます。  

> ##### 図36  
> 強調表示されたレイヤー **#39**  
> ![レイヤーの強調表示][ImageLayerHover]  

ダイアグラムを移動するには、次の操作を行います。  

*   **Pan Mode** ![ ][ImagePanModeIcon] X 軸と Y 軸に沿って移動するには、[パンモード] パンモードをクリックします。  
*   Z 軸に沿って回転させるには、[**回転モード**] をクリックし ![ ][ImageRotateModeIcon] ます。  
*   [**変形** ![ のリセット] をクリックして ][ImageResetTransformIcon] 、図を元の位置にリセットします。  

### ペイントプロファイラーの表示   

ペイントイベントに関する詳細情報を表示するには、次の操作を行います。  

1.  [高度な描画インストルメンテーションを有効に](#enable-advanced-paint-instrumentation)します。  
1.  **メイン**セクションで**Paint**イベントを選択します。  
    
    > ##### 図37  
    > [**ペイントプロファイラー** ] タブ  
    > ![[ペイントプロファイラー] タブ][ImagePaintProfiler]  
    
## [レンダリング] タブでのレンダリングのパフォーマンスの分析   

[**レンダリング**] タブの機能を使用すると、ページのレンダリングパフォーマンスを視覚化できます。  

[**レンダリング**] タブを開くには、次の操作を行います。  

1.  [コマンドメニューを開き][DevToolsCommandMenu]ます。  
1.  入力を開始し `Rendering` 、を選択し `Show Rendering` ます。  DevTools は、DevTools ウィンドウの下部にある [**レンダリング**] タブを表示します。  
    
    > ##### 図38  
    > [**レンダリング**] タブ  
    > ![[レンダリング] タブ][ImageRenderingTab]  
    
### FPS メーターを使ってリアルタイムで1秒あたりのフレームを表示する   

**FPS メーター**は、ビューポートの右上隅に表示されるオーバーレイです。  ページの実行時に、リアルタイムでの FPS の推定値が提供されます。  **FPS メーター**を開くには:  

1.  [**レンダリング**] タブを開きます。 「[レンダリングのパフォーマンスを分析する」を](#analyze-rendering-performance-with-the-rendering-tab)ご覧ください。  
1.  [ **FPS メーター** ] チェックボックスをオンにします。  
    
    > ##### 図39  
    > FPS メーター  
    > ![FPS メーター][ImageFpsMeter]  
    
### ペイントの点滅でリアルタイムで描画イベントを表示する   

[ペイントのフラッシュ] を使って、ページ上のすべての描画イベントをリアルタイムで表示します。  ページの一部が再描画されるたびに、DevTools でそのセクションの輪郭が緑色で示されます。  

ペイントのフラッシュを有効にするには:  

1.  [**レンダリング**] タブを開きます。 「[レンダリングのパフォーマンスを分析する」を](#analyze-rendering-performance-with-the-rendering-tab)ご覧ください。  
1.  [**ペイントの点滅**] チェックボックスをオンにします。  
    
    > ##### 図40  
    > **ペイントの点滅**  
    > ![ペイントの点滅][ImagePaintFlashing]  
    
### レイヤーの枠線を使用してレイヤーを重ねて表示する   

レイヤー境界**線**を使用して、レイヤーの境界線とタイルをページの上に重ねて表示します。  

レイヤーの境界線を有効にするには:  

1.  [**レンダリング**] タブを開きます。 「[レンダリングのパフォーマンスを分析する」を](#analyze-rendering-performance-with-the-rendering-tab)ご覧ください。  
1.  [**レイヤー罫線**] チェックボックスをオンにします。  
    
    > ##### 図41  
    > **レイヤーの枠線**  
    > ![レイヤーの枠線][ImageLayerBorders]  
    
色 codings の説明については、のコメントを参照してください [`debug_colors.cc`][ChromiumDebugColors] 。  

### スクロールパフォーマンスの問題をリアルタイムで見つける   

スクロールパフォーマンスの問題を使って、スクロールに関連するイベントリスナーを持つページの要素を特定し、ページのパフォーマンスに悪影響を与える可能性があります。  
DevTools では、青緑で問題が発生する可能性のある要素について説明します。  

スクロールパフォーマンスの問題を表示するには:  

1.  [**レンダリング**] タブを開きます。 「[レンダリングのパフォーマンスを分析する」を](#analyze-rendering-performance-with-the-rendering-tab)ご覧ください。  
1.  [**パフォーマンスの問題のスクロール**] チェックボックスをオンにします。  
 
    > ##### 図42  
    > **スクロールパフォーマンスの問題**は、非レイヤーのビューポートに制約のあるオブジェクトによってパフォーマンスの低下が発生する可能性があることを示します。  
    > ![スクロールパフォーマンスの問題は、非レイヤーのビューポートに制約のあるオブジェクトによってパフォーマンスの低下が発生する可能性があることを示します。][ImageScrollingPerformanceIssues]  
    

<!--    -->  



<!-- image links -->  

[ImageCaptureSettingsIcon]: /microsoft-edge/devtools-guide-chromium/media/capture-settings-icon.msft.png  
[ImageClearRecordingIcon]: /microsoft-edge/devtools-guide-chromium/media/clear-recording-icon.msft.png  
[ImageCollectGarbageIcon]: /microsoft-edge/devtools-guide-chromium/media/collect-garbage-icon.msft.png  
[ImageNextIcon]: /microsoft-edge/devtools-guide-chromium/media/next-icon.msft.png  
[ImagePanModeIcon]: /microsoft-edge/devtools-guide-chromium/media/pan-mode-icon.msft.png  
[ImagePreviousIcon]: /microsoft-edge/devtools-guide-chromium/media/previous-icon.msft.png  
[ImageRecordIcon]: /microsoft-edge/devtools-guide-chromium/media/record-icon.msft.png
[ImageRefreshPageIcon]: /microsoft-edge/devtools-guide-chromium/media/refresh-page-icon.msft.png  
[ImageResetTransformIcon]: /microsoft-edge/devtools-guide-chromium/media/reset-transform-icon.msft.png  
[ImageRotateModeIcon]: /microsoft-edge/devtools-guide-chromium/media/rotate-mode-icon.msft.png  
[ImageSearchCaseIcon]: /microsoft-edge/devtools-guide-chromium/media/search-case-icon.msft.png  
[ImageSearchRegexIcon]: /microsoft-edge/devtools-guide-chromium/media/search-regex-icon.msft.png  
[ImageShowHeaviestStackIcon]: /microsoft-edge/devtools-guide-chromium/media/show-heaviest-stack-icon.msft.png  

[ImageRecord]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-record-highlight.msft.png "図 1: レコード"  
[ImageRefreshPage]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-refresh-button.msft.png "図 2: ページの更新"  
[ImageLoadRecording]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-refreshed.msft.png "図 3: ページ読み込みの記録"  
[ImageScreenshots]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-capture-screenshots-checkbox.msft.png "図 4: [スクリーンショット] チェックボックス"  
[ImageCollectGarbage]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-collect-garbage-button.msft.png "図 5: ガーベジの収集"  
[ImageCaptureSettings]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-capture-settings-button-open-drawer.msft.png "図 6: [キャプチャの設定] セクション"  
[ImageJSSamplesDisabled]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-on.msft.png "図 7: JS サンプルが無効になっている場合のレコーディングの例"  
[ImageJSSamplesEnabled]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off.msft.png "図 8: JS サンプルが有効な場合のレコーディングの例"  
[ImageSaveProfile]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-save-profile.msft.png "図 9: プロファイルの保存"  
[ImageLoadProfile]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-load-profile.msft.png "図 10: プロファイルの読み込み"  
[ImageClearRecording]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-clear-button.msft.png "図 11: レコーディングをクリアする"  
[ImageZoom]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-zoom-highlighted.msft.png "図 12: 概要の上でマウスをドラッグしてズームする"  
[ImageSearch]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-search-regex.msft.png "図 13: 検索ボックス"  
[ImageMain]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-main-zoomed.msft.png "図 14: メインセクション"  
[ImageMainEventSummary]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-summary-me.msft.png "図 15: 匿名関数の詳細については、[概要] タブを参照してください。"  
[ImageFlameChart]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-main-flame-chart.msft.png "図 16: 炎の図"  
[ImageCallTree]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-call-tree.msft.png "図 17: [通話ツリー] タブ"  
[ImageBottomUp]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-bottoms-up.msft.png "図 18: ボトムアップタブ"  
[ImageEventLog]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-event-log.msft.png "図 19: [イベントログ] タブ"  
[ImageGpu]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-gpu-zoomed.msft.png "図 20: GPU セクション"  
[ImageRaster]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-raster.msft.png "図 21: ラスターセクション"  
[ImageInteractions]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-interactions-animation.msft.png "図 22: [操作] セクション"  
[ImageFpsChart]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-fps-highlight.msft.png "図 23: FPS グラフ"  
[ImageFramesSection]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-frames-hover.msft.png "図 24: フレームの上にマウスポインターを置く"  
[ImageFrameSummary]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-frames-summary.msft.png "図 25: [概要] タブのフレームの表示"  
[ImageNetworkRequest]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-network.msft.png "図 26: [ネットワーク] セクション"  
[ImageLineBar]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-bing-performance-network.msft.png "図 27: www.bing.com 要求のラインバー表現"  
[ImageTiming]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-bing-network-timing.msft.png "図 28: [ネットワーク] セクション"  
[ImageMemory]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-memory-highlight.msft.png "図 29: メモリチェックボックス"  
[ImageMemoryMetrics]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-memory-chart.msft.png "図 30: メモリの測定値"  
[ImageDuration]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-main-duration.msft.png "図 31: レコーディングの一部の継続時間を表示する"  
[ImageViewScreenshot]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-screenshots-hover.msft.png "図 32: スクリーンショットの表示"  
[ImageFrameScreenshotSummary]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-summary-preview.msft.png "図 33: [概要] タブのスクリーンショットの表示"  
[ImageFrameScreenshotZoom]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-summary-preview-select.msft.png "図 34: [概要] タブのスクリーンショットを拡大する"  
[ImageLayers]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-layers-all.msft.png "図 35: [レイヤー] ウィンドウ"  
[ImageLayerHover]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-frames-document-nav-bar-highlighted.msft.png "図 36: レイヤーの強調表示"  
[ImagePaintProfiler]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-paint-profiler.msft.png "図 37: [ペイントプロファイラー] タブ"  
[ImageRenderingTab]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-console-drawer-rendering.msft.png "図 38: [レンダリング] タブ"  
[ImageFpsMeter]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-jank-console-rendering-frame-rate.msft.png "図 39: FPS メーター"  
[ImagePaintFlashing]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-jank-console-rendering-paint-flashing.msft.png "図 40: ペイントが点滅する"  
[ImageLayerBorders]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-devtools-console-rendering-layer-borders.msft.png "図 41: レイヤーの境界線"  
[ImageScrollingPerformanceIssues]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-bing-console-drawer-rendering-scrolling-performance-issues.msft.png "図 42: スクロールパフォーマンスの問題は、非レイヤーのビューポートの制約を受けると、スクロールのパフォーマンスに悪影響を与える可能性があることを示す"  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール"  
[DevToolsCommandMenu]: /microsoft-edge/devtools-guide-chromium/command-menu/index#open-the-command-menu "コマンドメニューを開きます (Microsoft Edge の DevTools コマンドメニューを使用してコマンドを実行します)。"  
[DevtoolsEvaluatePerformanceGettingStarted]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/index "実行時のパフォーマンスの分析を開始する"  

[ActivityTabsDemo]: https://microsoft-edge-chromium-devtools.glitch.me/perf/activitytabs.html "アクティビティタブのデモ"  

[ChromiumDebugColors]: https://cs.chromium.org/chromium/src/cc/debug/debug_colors.cc "debug_colors cc-コードの検索"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/reference)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
