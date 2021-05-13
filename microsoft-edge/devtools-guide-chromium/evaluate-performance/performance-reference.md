---
description: タイムライン イベント モードでは、録音中にトリガーされたイベントすべてが表示されます。  タイムライン イベントの各種類の詳細については、タイムライン イベント参照を使用します。
title: Timeline イベントリファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: b8a15dd3503a891698d1f96bdc99946163d738ff
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564211"
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
# <a name="timeline-event-reference"></a>Timeline イベントリファレンス  

タイムライン イベント モードでは、録音中にトリガーされたイベントすべてが表示されます。  タイムライン イベントの各種類の詳細については、タイムライン イベント参照を使用します。  

## <a name="common-timeline-event-properties"></a>一般的なタイムライン イベントのプロパティ  

特定の詳細は、すべての種類のイベントに存在しますが、一部のイベントは特定のイベントの種類にのみ適用されます。  このセクションでは、さまざまなイベントの種類に共通するプロパティの一覧を示します。  特定のイベントの種類に固有のプロパティは、その後に続くイベントの種類の参照に一覧表示されます。  

| プロパティ | いつ表示されるか |  
|:--- |:--- |  
| 集計時間 | 入れ子になった **イベントの場合**、イベントの各カテゴリによって取られる時間。 |  
| 呼び出し履歴 | 子イベントを **持つイベントの**場合、イベントの各カテゴリによって取られた時間。 |  
| CPU 時間 | 記録されたイベントにかかった CPU 時間。 |  
| 詳細 | イベントに関するその他の詳細。 |  
| Duration \(at time-stamp\) | すべての子が完了するためにイベントにかかった時間。タイムスタンプは、イベントが発生した時刻で、記録が開始された時刻を基準として指定します。 |  
| 自己時間 | 子がいなくてもイベントにかかった時間。 |  
| 使用ヒープ サイズ | イベントの記録時にアプリケーションで使用されるメモリの量と、前回のサンプリング以降の使用ヒープ サイズのデルタ \(+/-\) の変化。 |  

<!--todo: add nested and child events (timelinetool) section when available -->  

## <a name="loading-events"></a>イベントの読み込み  

このセクションでは、読み込みカテゴリとそのプロパティに属するイベントの一覧を示します。  

| イベント | 説明 |  
|:--- |:--- |  
| HTML の解析 |  Microsoft Edge HTML 解析アルゴリズムを実行しました。 |  
| 読み込みを完了する |  ネットワーク要求が完了しました。 |  
| データの受信 |  要求のデータが受信された。  1 つ以上の受信データ イベントがあります。 |  
| 応答の受信 |  要求からの最初の HTTP 応答。 |  
| 要求の送信 |  ネットワーク要求が送信されました。 |  

### <a name="loading-event-properties"></a>イベント プロパティの読み込み  

| プロパティ | 説明 |  
|:--- |:--- |  
| リソース | 要求されたリソースの URL。 |  
| Preview | 要求されたリソース \(images only\) のプレビュー。 |  
| Request メソッド | 要求 \( または 、 `GET` たとえば `POST` \) に使用される HTTP メソッド。 |  
| ステータス コード | HTTP 応答コード。 |  
| MIME の種類 | 要求されたリソースの MIME の種類。 |  
| エンコードされたデータの長さ | 要求されたリソースの長さ (バイト単位)。 |  

## <a name="scripting-events"></a>スクリプト イベント  

このセクションでは、Scripting カテゴリとそのプロパティに属するイベントの一覧を示します。  

| イベント | 説明 |  
|:--- |:--- |  
| アニメーション フレームの作成 | スケジュールされたアニメーション フレームが起動され、コールバック ハンドラーが呼び出されます。 |  
| アニメーション フレームの取り消し |  スケジュールされたアニメーション フレームが取り消されました。 |  
| GC イベント |  ガベージ コレクションが発生しました。 |  
| DOMContentLoaded |  [DOMContentLoaded イベントは][MDNWindowDOMContentLoadedEvent]ブラウザーによって発生しました。  このイベントは、ページのすべての DOM コンテンツが読み込まれ、解析されると発生します。 |  
| スクリプトの評価 | スクリプトが評価されました。 |  
| イベント | JavaScript イベント \(たとえば `mousedown` `key` 、、\)。 |  
| 関数呼び出し | トップ レベルの JavaScript 関数呼び出しが行われた \(ブラウザーが JavaScript エンジン\に入った場合にのみ表示されます)。 |  
| インストール タイマー | [setInterval() または setTimeout() を][MDNWindowOrWorkerGlobalScopeSetInterval]使用[してタイマーが作成されました][MDNWindowOrWorkerGlobalScopeSetTimeout]。 |  
| アニメーション フレームの要求 | 新 `requestAnimationFrame()` しいフレームをスケジュールした呼び出し。 |  
| タイマーの削除 | 以前に作成したタイマーがクリアされました。 |  
| Time |  [console.time() というスクリプト][ConsoleApiTime]。 |  
| タイム エンド | [console.timeEnd()][ConsoleApiTimeEnd]というスクリプト。 |  
| タイマーの発生 | またはでスケジュールされたタイマーが `setInterval()` 発生 `setTimeout()` しました。 |  
| XHR Ready State Change | XMLHTTPRequest の準備状態が変更されました。 |  
| XHR の読み込み | 読 `XMLHTTPRequest` み込みが完了しました。 |  

### <a name="scripting-event-properties"></a>スクリプト イベントのプロパティ  

| プロパティ | 説明 |  
|:--- |:--- |  
| タイマー ID | タイマー ID。 |  
| タイムアウト | タイマーで指定されたタイムアウト。 |  
| 繰り返し | タイマーが繰り返される場合を指定するブール値。 |  
| 関数呼び出し | 呼び出された関数。 |  

## <a name="rendering-events"></a>レンダリング イベント  

このセクションでは、レンダリング カテゴリとそのプロパティに属するイベントの一覧を示します。  

| イベント | 説明 |  
|:--- |:--- |  
| レイアウトを無効にする | DOM の変更によってページ レイアウトが無効にされました。 |  
| レイアウト | ページ レイアウトが完了しました。 |  
| スタイルの再計算 | Microsoft Edge要素のスタイルを再計算します。 |  
| Scroll | 入れ子になったビューの内容がスクロールされました。 |  

### <a name="rendering-event-properties"></a>レンダリング イベントのプロパティ  

| プロパティ | 説明 |  
|:--- |:--- |  
| レイアウトが無効 | Layout レコードの場合、レイアウトを無効にしたコードのスタック トレース。 |  
| レイアウトが必要なノード | Layout レコードの場合、リレーアウトが開始される前に必要なレイアウトとしてマークされたノードの数。  これらは通常、開発者コードによって無効にされたノードと、ルートを中継する上方向のパスです。 |  
| レイアウト ツリーのサイズ | Layout レコードの場合、リレーアウト ルート \(リレーアウトを開始するノード\)のMicrosoft Edge数です。 |  
| レイアウト スコープ | 可能な値 `Partial` は \(再レイアウト境界は DOM\の一部) または `Whole document` です。 |  
| 影響を受ける要素 | [スタイル レコードの再計算] では、スタイル再計算の影響を受ける要素の数を指定します。 |  
| スタイルが無効 | [スタイル レコードの再計算] では、スタイルが無効になる原因となるコードのスタック トレースを提供します。 |  

## <a name="painting-events"></a>ペイント イベント  

このセクションでは、Painting カテゴリとそのプロパティに属するイベントの一覧を示します。  

| イベント | 説明 |  
|:--- |:--- |  
| コンポジット レイヤー | レンダリング エンジンの合成Microsoft Edgeレイヤー。 |  
| 画像デコード | イメージ リソースがデコードされました。 |  
| イメージのサイズ変更 | イメージのサイズは、ネイティブディメンションから変更されました。 |  
| ペイント | 合成されたレイヤーは、ディスプレイの領域にペイントされました。  レコードの上にペイントすると、更新された表示領域が強調表示されます。 |  

### <a name="painting-event-properties"></a>イベントプロパティのペイント  

| プロパティ | 説明 |  
|:--- |:--- |  
| 場所 | イベントペイント、ペイント四角形の x 座標と y 座標を指定します。 |  
| ディメンション | イベントペイント描画領域の高さと幅を指定します。 |  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->

[ConsoleApiTime]: /microsoft-edge/devtools-guide-chromium/console/api#time "time - コンソール API リファレンス"  
[ConsoleApiTimeEnd]: /microsoft-edge/devtools-guide-chromium/console/api#timeend "timeEnd - コンソール API リファレンス"  
<!--[EvaluatePerformanceTimelineTool]: timeline-tool "How to Use the Timeline Tool"  -->

[MDNWindowDOMContentLoadedEvent]: https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded "ウィンドウ: DOMContentLoaded イベント |MDN"  
[MDNWindowOrWorkerGlobalScopeSetInterval]: https://developer.mozilla.org/docs/Web/API/WindowTimers/setInterval "WindowOrWorkerGlobalScope.setInterval() |MDN"  
[MDNWindowOrWorkerGlobalScopeSetTimeout]: https://developer.mozilla.org/docs/Web/API/WindowTimers/setTimeout "WindowOrWorkerGlobalScope.setTimeout() |MDN"  

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> 元のページ [はここで見](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/performance-reference) つかり [、Meggin Kearney][MegginKearney] \(Tech Writer\) と [Flavio Copes \(Full Stack][FlavioCopes] Developer\) によって作成されています。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
[MegginKearney]: https://developers.google.com/web/resources/contributors#meggin-kearney  
[FlavioCopes]: https://developers.google.com/web/resources/contributors#flavio-copes  
