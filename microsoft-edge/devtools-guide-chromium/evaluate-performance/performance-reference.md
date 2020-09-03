---
description: タイムラインイベントモードでは、記録を作成するときにトリガーされるすべてのイベントが表示されます。  タイムラインイベントのリファレンスを使って、各タイムラインイベントの種類について詳しく知ることができます。
title: タイムライン イベント リファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 624035636e2231cf1f3cd1e2ba0fdda7e2e4fa00
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "10992849"
---
<!-- Copyright Meggin Kearney and Flavio Copes

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->





# タイムライン イベント リファレンス   




タイムラインイベントモードでは、記録を作成するときにトリガーされるすべてのイベントが表示されます。  タイムラインイベントのリファレンスを使って、各タイムラインイベントの種類について詳しく知ることができます。  

## 一般的なタイムラインイベントプロパティ  

一部の詳細は、すべての種類のイベントに存在しますが、一部のイベントの種類にしか適用されません。  このセクションでは、さまざまなイベントの種類に共通するプロパティを示します。  特定のイベントの種類に固有のプロパティについては、次に示すイベントの種類に関する参照で示されています。  

| プロパティ | 表示されるタイミング |  
|:--- |:--- |  
| 集計時間 | **入れ子になっ**たイベントのイベントについては、各カテゴリのイベントによって実行される時間。 |  
| 通話スタック | **子イベント**を持つイベントについては、各カテゴリのイベントによって行われる時間。 |  
| CPU 時間 | 記録されたイベントに要した CPU 時間。 |  
| 詳細 | イベントに関するその他の詳細。 |  
| Duration (タイムスタンプ \) | すべての子のイベントが完了するまでの時間。[タイムスタンプ] は、記録を開始したタイミングを基準とした、イベントが発生した時刻です。 |  
| セルフタイム | その子のいずれかがなくてもイベントはどのくらいの時間がかかります。 |  
| 使用されたヒープサイズ | イベントが記録されたときにアプリケーションによって使用されたメモリの量と、前回のサンプリング以降、使用されたヒープサイズのデルタ \ (+/-\) が変化します。 |  

<!--todo: add nested and child events (timelinetool) section when available -->  

## イベントの読み込み  

このセクションには、カテゴリとそのプロパティの読み込みに属するイベントが一覧表示されます。  

| イベント | 説明 |  
|:--- |:--- |  
| HTML の解析 |  Microsoft Edge は、HTML 解析アルゴリズムを実行しました。 |  
| 読み込みを完了する |  ネットワーク要求が完了しました。 |  
| データの受信 |  要求のデータが受信されました。  1つ以上の受信データイベントがあります。 |  
| 応答を受信する |  要求からの最初の HTTP 応答。 |  
| リクエストを送信 |  ネットワーク要求が送信されました。 |  

### イベントプロパティの読み込み  

| プロパティ | 説明 |  
|:--- |:--- |  
| リソース | 要求されたリソースの URL です。 |  
| Preview | 要求されたリソースのプレビュー \ (images のみ)。 |  
| Request メソッド | 要求 (\ など) に使用される HTTP メソッド `GET` `POST` 。 |  
| ステータス コード | HTTP 応答コード。 |  
| MIME の種類 | 要求されたリソースの MIME の種類。 |  
| エンコードされたデータの長さ | 要求されたリソースの長さ (バイト単位) です。 |  

## スクリプトイベント  

このセクションには、スクリプトカテゴリとそのプロパティに属するイベントが一覧表示されます。  

| イベント | 説明 |  
|:--- |:--- |  
| アニメーションフレームが発生した | スケジュールされたアニメーションフレームが起動され、そのコールバックハンドラーが呼び出されます。 |  
| アニメーションフレームのキャンセル |  スケジュールされたアニメーションのフレームが取り消されました。 |  
| GC イベント |  ガーベジコレクションが行われました。 |  
| DOMContentLoaded |  [Domcontentloaded イベント][MDNWindowDOMContentLoadedEvent]がブラウザーによって起動されました。  このイベントは、すべてのページの DOM コンテンツが読み込まれて解析されたときに発生します。 |  
| スクリプトの評価 | スクリプトが評価されました。 |  
| イベント | JavaScript イベント ( `mousedown` 、、など `key` )。 |  
| 関数呼び出し | 最上位レベルの JavaScript 関数の呼び出しが行われました (ブラウザーが JavaScript エンジン \ に入力した場合にのみ表示されます)。 |  
| インストールタイマー | タイマーは [Setinterval ()][MDNWindowOrWorkerGlobalScopeSetInterval] または [setTimeout ()][MDNWindowOrWorkerGlobalScopeSetTimeout]を使って作成されました。 |  
| アニメーションフレームを要求する | 通話によって `requestAnimationFrame()` 新しいフレームがスケジュールされました。 |  
| タイマーを削除する | 以前に作成したタイマーが消去されました。 |  
| 時間 |  " [Console. time ()][ConsoleApiTime]" というスクリプト。 |  
| 終了時刻 | " [Console. timeEnd ()][ConsoleApiTimeEnd]" というスクリプト。 |  
| タイマーが発生した | またはでスケジュールされていたタイマーが起動しました `setInterval()` `setTimeout()` 。 |  
| XHR のレディ状態の変更 | XMLHTTPRequest のレディ状態が変更されました。 |  
| XHR 読み込み | `XMLHTTPRequest`読み込みが完了しました。 |  

### スクリプトイベントプロパティ  

| プロパティ | 説明 |  
|:--- |:--- |  
| タイマー ID | タイマー ID。 |  
| タイムアウト | タイマーによって指定されたタイムアウト。 |  
| 繰り返し | タイマーを繰り返すかどうかを指定するブール値。 |  
| 関数呼び出し | 呼び出された関数。 |  

## レンダリングイベント  

このセクションには、レンダリングカテゴリとそのプロパティに属するイベントが一覧表示されます。  

| イベント | 説明 |  
|:--- |:--- |  
| レイアウトの無効化 | ページレイアウトは DOM の変更によって無効にされました。 |  
| レイアウト | ページレイアウトが完了しました。 |  
| スタイルの再計算 | Microsoft Edge で再計算された要素のスタイル。 |  
| Scroll | 入れ子になったビューのコンテンツがスクロールされました。 |  

### イベントプロパティのレンダリング  

| プロパティ | 説明 |  
|:--- |:--- |  
| レイアウトの無効化 | レイアウトレコードの場合、レイアウトが無効になる原因となったコードのスタックトレース。 |  
| レイアウトが必要なノード | レイアウトレコードの場合は、relayout が開始される前に、必要なレイアウトとしてマークされたノードの数。  これらは通常、開発者コードによって無効にされたノードに加えて、relayout ルートまでのパスを示しています。 |  
| レイアウトツリーのサイズ | レイアウトレコードの場合、relayout ルート \ (Microsoft Edge が relayout を開始するノード) の下にあるノードの合計数です。 |  
| レイアウトの範囲 | 可能な値は `Partial` \ (再レイアウトの境界は DOM の一部) または `Whole document` です。 |  
| 影響を受ける要素 | スタイルの再計算には、スタイル再計算によって影響を受ける要素の数を指定します。 |  
| 無効になったスタイル | スタイルレコードの再計算には、スタイルの無効化を引き起こしたコードのスタックトレースを提供します。 |  

## 描画イベント  

このセクションには、Painting カテゴリとそのプロパティに属するイベントが一覧表示されます。  

| イベント | 説明 |  
|:--- |:--- |  
| 複合レイヤー | Microsoft Edge レンダリングエンジン用の合成画像レイヤー。 |  
| 画像のデコード | 画像リソースがデコードされました。 |  
| 画像のサイズ変更 | 画像がネイティブの寸法からサイズ変更されました。 |  
| ペイント | 合成レイヤーは、ディスプレイの領域に対して描画されました。  ペイントレコードの上にマウスポインターを置くと、更新されたディスプレイの領域が強調表示されます。 |  

### Painting イベントプロパティ  

| プロパティ | 説明 |  
|:--- |:--- |  
| 場所 | Paint イベントの場合は、ペイントの四角形の x 座標と y 座標を使用します。 |  
| 各 | Paint イベントの場合は、塗装領域の高さと幅。 |  

 



<!-- image links -->  

<!-- links -->

[ConsoleApiTime]: /microsoft-edge/devtools-guide-chromium/console/api#time "タイムコンソール API リファレンス"  
[ConsoleApiTimeEnd]: /microsoft-edge/devtools-guide-chromium/console/api#timeend "timeEnd-本体の API リファレンス"  
<!--[EvaluatePerformanceTimelineTool]: timeline-tool "How to Use the Timeline Tool"  -->

[MDNWindowDOMContentLoadedEvent]: https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded "Window: DOMContentLoaded イベント |MDN"  
[MDNWindowOrWorkerGlobalScopeSetInterval]: https://developer.mozilla.org/docs/Web/API/WindowTimers/setInterval "WindowOrWorkerGlobalScope Interval () |MDN"  
[MDNWindowOrWorkerGlobalScopeSetTimeout]: https://developer.mozilla.org/docs/Web/API/WindowTimers/setTimeout "WindowOrWorkerGlobalScope () |MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/performance-reference) にあり、 [Meggin Kearney][MegginKearney] \ (Tech Writer \) と [Flavio Copes][FlavioCopes] \ (完全なスタック開発者) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
[FlavioCopes]: https://developers.google.com/web/resources/contributors/flaviocopes  
