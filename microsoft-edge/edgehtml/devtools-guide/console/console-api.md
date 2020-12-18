---
description: コンソール API を使用してコードをプログラムでデバッグし、プロファイルを作成する
title: DevTools - コンソール - コンソール API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, コンソール API
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 46a74b80b504358ff7dbea40970528c8e2b228cf
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234480"
---
# コンソール API

コンソール *API は* 、グローバル オブジェクトを介して DevTools コンソールへのコマンドラインおよびプログラムによるアクセスを提供し、次の操作 `console` を実行できます。

 - [コードからのカスタム メッセージ](#logging-custom-messages) をログに記録する
 - [オブジェクトと要素を検査し](#inspecting-objects-and-elements) 、その情報を記録する
 - [アサーション、タイマー、カウンターを](#testing-and-measuring) 設定してコードをテストおよび測定する
 - [ヒープのスナップショットを作成して](#taking-heap-snapshots) 実行中のコードのメモリ消費量を評価し、メモリ リークを特定する
 - [呼び出し履歴をトレース](#tracing-callstacks) して、コードの呼び出し先を把握する 
 - [ログ出力を整理して](#organizing-log-output) デバッグを効率化する

Microsoft Edge で現在サポートされているコマンドと書式設定パラメーターを次に示します。 主要なブラウザーでも同様に動作します。

## カスタム メッセージのログ記録

コードは、次に示すいくつかの種類のカスタム メッセージをコンソールに送信できます。

メッセージの種類  | &nbsp;   |
:------------------- | :------ |
[**error()**](https://developer.mozilla.org/docs/Web/API/Console/error) と [**exception()**](https://developer.mozilla.org/docs/Web/API/Console/error)| 重大なエラーとエラー
[**warn()**](https://developer.mozilla.org/docs/Web/API/Console/warn) | 考えられるエラーまたは予期しない動作 
[**info()**](https://developer.mozilla.org/docs/Web/API/Console/info) | 有用だが重要ではない情報
[**log()**](https://developer.mozilla.org/docs/Web/API/Console/log) と [**debug()**](https://developer.mozilla.org/docs/Web/API/Console/log) | 一般的なデバッグ (コンソールでシステム通知アイコンを生成しない)

   
コンソール パネルから Microsoft Edge から生成された他のメッセージと共に、これらをグループ化してフィルター処理できます。 すべてのカスタム メッセージ メソッドには、文字列 (メッセージ) パラメーターとオプションの形式置換パラメーターが必要です。 Microsoft Edge では、次の書式設定オプションがサポートされています。

Format パラメーター | &nbsp;
:------------------- | :--- |
**%b** | バイナリ
**%c** | インライン CSS スタイル (下記の例を参照)
**%d** **、%i** | Integer 
**%f** | Float  
**%s** | String 
**%x** | 16 進数 
**%e** | Exponent 

たとえば、ログ メッセージに文字列変数と整数変数を含める方法を次に示します。

```javascript
var myText = 'pieces';
var myVal = 5;
console.log("The number of %s is %d.", myText, myVal);
```

>`The number of pieces is 5.`

インライン CSS ( ) を使用してログ メッセージに緑色の強調表示効果を追加する方法を次に示します `%c` 。

```javascript
console.log("%cHighlight this log message in green", "background-color: #10ff00; text-transform: uppercase;");
```

![インライン スタイルを含むコンソール ログ](../media/console_api_css.png)

## オブジェクトと要素の検査

検査可能なオブジェクトは、展開可能なノードを持つ折りたたみツリー ビューのコンソールに表示されます。 コンソールは、DOM ノード (div など) または JavaScript オブジェクト (イベントなど) を送信するかどうかを検出し、検出された型として自動的に表示します。

特定の出力を強制できます。

コマンド | &nbsp;
:------------------- | :--- |
[**dir()**](https://developer.mozilla.org/docs/Web/API/Console/dir) | 検査可能な JavaScript オブジェクトとして表示
[**dirxml()**](https://developer.mozilla.org/docs/Web/API/Console/dirxml) | 検査可能な DOM ノードとして表示

たとえば、コンソールを開いて、このページの要素について次の `<div id='main'>` 出力を比較してみてください。

```javascript
console.dir(document.querySelector('#main'));
console.dirxml(document.querySelector('#main'));
```

!['dir' と 'dirxml' の出力の比較](../media/console_api_dir.png)

### [要素] パネルで要素 **を選択** する

ページの HTML ツリー コンテキスト内の要素をコンソールから直接選択して、すぐにレイアウトとスタイルをデバッグできます。

コマンド | &nbsp;
:------------------- | :--- |
**select()** | 要素パネルに **切り替** え、指定した要素にフォーカスを設定します。

たとえば、このページでコンソールを開き、次のコマンドを入力します。

```javascript
console.select(document.querySelector("body"));
```

DevTools は、要素パネル****(現在のパネルではない場合) に切り替わり[*、HTML*](../elements.md#html-tree-view)ツリー ビューで指定された要素にフォーカスを設定します。

!['select' メソッドの例](../media/console_api_select.png)

## テストと測定

### コードのテスト

本体 API テスト アサーションをコードに追加して、コードをブラウザーで実行する場合の単体テストとデバッグを行います。

コマンド | &nbsp;
:------------ | :-------------
[**assert()**](https://developer.mozilla.org/docs/Web/API/Console/assert) | 指定された式が false と評価された場合、コンソール エラー メッセージをログに記録 *します*。

テスト可能なアサーションとして指定する論理式に加えて、他のカスタム コンソール メッセージと同様に、オプションのメッセージおよび書式設定パラメーター [を追加できます](#logging-custom-messages)。 次に、例を示します。

```javascript
var x = 26.8;
console.assert(x < 25, 'The value of x is %f (it is NOT less than %i)', x, 25);
```

!['assert' メソッドの例](../media/console_api_assert.png)

### コード内の実行をカウントする

コード内にカウンターを設定して、周囲のコードが実行された回数を追跡できます。 カウンターを設定すると、コードが期待通り実行され、パフォーマンスのボトルネックの診断に役立ちます。

コマンド | &nbsp;
:------------ | :-------------
[**count()**](https://developer.mozilla.org/docs/Web/API/Console/count) | 指定されたラベルのカウント *()* が実行された回数を増分し、ログに記録します。
[**countReset()**](https://developer.mozilla.org/docs/Web/API/Console/countReset) | 指定したカウンター ラベルのカウントを 0 にリセットします。

たとえば、コンソールで次の行を実行します。

```javascript
console.count('My Counter');
console.count('My Counter');
console.countReset('My Counter');
console.count('My Counter');
```

 . . . 結果は次の結果になります。
> マイ カウンター: 1

### コードのタイミングを設定する

ラベル付きタイマーを使ってコードをインストルメント化し、特定の操作を完了するのにかかる時間を測定します。

コマンド | &nbsp;
:------------ | :-------------
[**time()**](https://developer.mozilla.org/docs/Web/API/Console/time) | 指定されたラベルでタイマーを開始します。
[**timeEnd()**](https://developer.mozilla.org/docs/Web/API/Console/timeEnd) | 指定されたラベルでタイマーを終了し、経過時間 (ミリ秒) を報告します。
[**timeStamp()**](https://developer.mozilla.org/docs/Web/API/Console/timeStamp) | 現在のシステム時間をミリ秒単位で報告します。

たとえば、コンソールで次の行を実行してみてください。

```javascript
console.time('My Timer');
console.timeEnd('My Timer');
```

### ヒープ スナップショットの取得

ヒープのスナップショットを作成して、実行中のコードのメモリ消費量を評価し、メモリ リークを特定します。

コマンド | &nbsp;
:------------ | :-------------
**takeHeapSnapshot()** | 現在の JavaScript ヒープとその割り当てられたオブジェクトに関する詳細をキャプチャします。

ヒープ スナップショットを取得 [するには、DevTools](../memory.md#toolbar) メモリ プロファイラーが実行されている必要があります。 各スナップショットは、メモリ パネルの [*[Snapshot]*](../memory.md#snapshot-summary) (スナップショット) の概要にタイルとして表示され、 [**さらに詳しい**](../memory.md) 調査が行えます。

## 呼び出し履歴のトレース

コードの呼び出しの場所、実行されているコード、および実行にかかる時間を把握すると、速度の低下や予期しない動作の分析に役立ちます。 スタック トレースは、トレース要求からパスの上方向に向かって、コードが到達するためにかかった実行パスを示します。 

コマンド | &nbsp;
:------------ | :-------------
[**trace()**](https://developer.mozilla.org/docs/Web/API/Console/trace) | 現在のスクリプト実行コールスタックのトレースを出力します。

たとえば、コンソールで次のコードを実行します。

```javascript
function a(){
  c();
}
function b(){
  c();
}
function c(){
  console.trace()
}
function d(){
  b();
}

a();
d();
```

. . . は、次のスタック トレースを出力します。
> console.trace() at c (eval code:8:3) at a (eval code:2:3) at eval code (eval code:14:1)
> 
> console.trace() at c (eval code:8:3) at b (eval code:5:3) at d (eval code:11:3) at eval code (eval code:15:1)

## ログ出力を整理する

以前のすべてのコンソール出力をクリアするには *、console.clear() (または) を* 使用します `CTRL + L` 。 これにより、コンソール コマンド履歴のバックスタックはクリアされません (上方向キーと下方向キーを使用してスキャンできます)。

コマンド | &nbsp;
:------------ | :-------------
[**clear()**](https://developer.mozilla.org/docs/Web/API/Console/clear) | 以前のすべてのコンソール出力をクリアします。

コードで多くのコンソール メッセージを出力する場合は、次のコマンドを使用して、入れ子になったブロックに視覚的に整理できます。

 コマンド | &nbsp;
:------------ | :-------------
[**group()**](https://developer.mozilla.org/docs/Web/API/Console/group) | 指定された (オプションの) ラベルを使用して、コンソール出力の新しいレベルの入れ子を開始します。
[**groupCollapsed()**](https://developer.mozilla.org/docs/Web/API/Console/groupCollapsed) | 指定された (オプション) ラベルを使用してコンソール出力の新しいレベルの入れ子を開始しますが、グループ化コントロールは既定で折りたたみ、(矢印コントロールをクリックして) 展開して子出力を表示する必要があります。
[**groupEnd()**](https://developer.mozilla.org/docs/Web/API/Console/groupEnd) | 指定したラベルのネスト グループを終了します。

たとえば、コンソールに次のコマンドを入力してみてください。

```javascript
console.groupCollapsed('Group 1');
console.log('In Group 1');
console.groupCollapsed('Group 1.1');
console.log('In Group 1.1');
console.groupEnd('Group 1.1');
console.groupEnd('Group 1');
console.log('No longer in a group');
```

. . . 次に、 *グループ 1* とグループ *1.1* のコントロールを展開して、ログ コメントがどのように入れ子になっているか確認します。

![コンソールでのメッセージのグループ化](../media/console_api_group.png)

場合によっては、フラットリストではなく、表形式で JavaScript オブジェクトまたは配列を視覚化する方が簡単な場合があります。 このためには *、console.table() コマンドを使用* できます。

コマンド | &nbsp;
:------------ | :-------------
[**table()**](https://developer.mozilla.org/docs/Web/API/Console/table) | 指定された配列またはオブジェクトを表形式でコンソールに出力します。

たとえば、次のオブジェクト配列です。

```javascript
var orders = [{'Size':'XL', 'Quantity':1},{'Size':'M', 'Quantity':3}, {'Size':'L', 'Quantity':2}];
console.table(orders);
```

. . . コンソールで次の表としてレンダリングされます。

![コンソールにオブジェクト配列をテーブルとして表示する](../media/console_api_table.png)
