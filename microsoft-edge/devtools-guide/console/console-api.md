---
description: コンソール API を使ってプログラムでコードのデバッグとプロファイルを行う
title: DevTools-本体と本体の API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、コンソール api
ms.custom: seodec18
ms.openlocfilehash: d722934c3694c3c23e367141158ad45f6d03b175
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570529"
---
# コンソール API

*CONSOLE API*は、グローバルオブジェクトを通じて Devtools 本体へのコマンドラインとプログラムによるアクセスを提供し `console` 、次のことを可能にします。

 - コードから[カスタムメッセージをログに記録](#logging-custom-messages)する
 - [オブジェクトと要素を検査](#inspecting-objects-and-elements)して情報を記録する
 - アサーション、タイマー、カウンターを設定して、[コードのテストと測定を行う](#testing-and-measuring)
 - [ヒープのスナップショットを取得](#taking-heap-snapshots)して、実行しているコードのメモリ使用量を評価し、メモリリークを特定する
 - [Callstacks をトレース](#tracing-callstacks)して、コードの呼び出し元を把握してください。 
 - [ログ出力を整理](#organizing-log-output)してデバッグを効率化する

Microsoft Edge で現在サポートされているコマンドと書式設定パラメーターを次に示します。 主要なブラウザーでも同じように動作します。

## カスタムメッセージのログ記録

コードでは、次のようなさまざまな種類のカスタムメッセージをコンソールに送信できます。

メッセージの種類  | &nbsp;   |
:------------------- | :------ |
[**error ()**](https://developer.mozilla.org/docs/Web/API/Console/error)と[ **exception ()**](https://developer.mozilla.org/docs/Web/API/Console/error)| 重大なエラーとエラー
[**warn ()**](https://developer.mozilla.org/docs/Web/API/Console/warn) | 考えられるエラーまたは予期しない動作 
[**info ()**](https://developer.mozilla.org/docs/Web/API/Console/info) | 役立つが、重要ではない情報
[**log ()**](https://developer.mozilla.org/docs/Web/API/Console/log)と[ **debug ()**](https://developer.mozilla.org/docs/Web/API/Console/log) | 一般的なデバッグ (本体にシステム警告アイコンを生成しない)

   
これらは、Microsoft Edge から生成された他のメッセージと共に、コンソールパネルからグループ化してフィルター処理することができます。 すべてのカスタムメッセージメソッドには、string (message) パラメーターとオプションの書式置換パラメーターが必要です。 Microsoft Edge では、次の書式設定オプションがサポートされています。

Format パラメーター | &nbsp;
:------------------- | :--- |
**% b** | バイナリ
**% c** | インライン CSS スタイル (以下の例を参照)
**% d**、 **% i** | Integer 
**% f** | Float  
**% s** | String 
**% x** | 16進数 
**% e** | 指数 

たとえば、次のようにして、ログメッセージに文字列と整数の変数を含めます。

```javascript
var myText = 'pieces';
var myVal = 5;
console.log("The number of %s is %d.", myText, myVal);
```

>`The number of pieces is 5.`

次に、インライン CSS () を使用してログメッセージに緑の強調表示効果を追加する方法について説明し `%c` ます。

```javascript
console.log("%cHighlight this log message in green", "background-color: #10ff00; text-transform: uppercase;");
```

![インラインスタイルを使用したコンソールログ](../media/console_api_css.png)

## オブジェクトと要素の検査

Inspectable オブジェクトは、展開可能なノードを含む折りたたまれたツリービューのコンソールに表示されます。 コンソールは、DOM ノード (div など) または JavaScript オブジェクト (イベントなど) を送信するかどうかを検出し、検出された型として自動的に表示します。

特定の出力を強制的に指定することもできます。

コマンド | &nbsp;
:------------------- | :--- |
[**dir ()**](https://developer.mozilla.org/docs/Web/API/Console/dir) | Inspectable JavaScript オブジェクトとして表示されます
[**dirxml ()**](https://developer.mozilla.org/docs/Web/API/Console/dirxml) | Inspectable DOM ノードとして表示されます

たとえば、本体を開いて、 `<div id='main'>` このページの要素の次の出力を比較してみてください。

```javascript
console.dir(document.querySelector('#main'));
console.dirxml(document.querySelector('#main'));
```

!["Dir" と "dirxml" の出力の比較](../media/console_api_dir.png)

### [**要素**] パネルでの要素の選択

すぐにレイアウトとスタイルのデバッグを行うために、ページの HTML ツリーコンテキスト内の要素をコンソールから直接選ぶことができます。

コマンド | &nbsp;
:------------------- | :--- |
**select ()** | **要素**パネルに切り替えて、指定された要素にフォーカスを設定します。

たとえば、このページで本体を開いて、次のように入力します。

```javascript
console.select(document.querySelector("body"));
```

DevTools が [**要素**] パネルに切り替わり (まだ現在のものではない場合)、 [*HTML ツリービュー*](../elements.md#html-tree-view)でフォーカスを指定された要素に設定します。

![Select メソッドの例](../media/console_api_select.png)

## テストと測定

### コードをテストする

単体テストのコードに本体 API テストアサーションを追加し、ブラウザーで実行されるコードをデバッグします。

コマンド | &nbsp;
:------------ | :-------------
[**assert ()**](https://developer.mozilla.org/docs/Web/API/Console/assert) | 指定した式が*false*に評価された場合に本体のエラーメッセージを記録します。

テスト可能なアサーションとして指定した論理式に加えて、オプションのメッセージと書式設定パラメーターを追加することもできます。これには、他の[カスタムコンソールメッセージ](#logging-custom-messages)と同じように使用できます。 次に、例を示します。

```javascript
var x = 26.8;
console.assert(x < 25, 'The value of x is %f (it is NOT less than %i)', x, 25);
```

!["Assert" メソッドの例](../media/console_api_assert.png)

### コードの実行回数をカウントする

コードでカウンターを設定することで、周囲のコードが実行される回数を追跡することができます。 カウンターを設定すると、コードが期待どおりに実行されるようになり、パフォーマンスのボトルネックを診断するのに役立ちます。

コマンド | &nbsp;
:------------ | :-------------
[**count ()**](https://developer.mozilla.org/docs/Web/API/Console/count) | 指定されたラベルの*count ()* 回数が実行された回数をインクリメントしてログに記録します。
[**countReset ()**](https://developer.mozilla.org/docs/Web/API/Console/countReset) | 指定されたカウンターラベルのカウントを0にリセットします。

たとえば、次のような行をコンソールで実行します。

```javascript
console.count('My Counter');
console.count('My Counter');
console.countReset('My Counter');
console.count('My Counter');
```

 . . . 結果は次のようになります。
> 自分のカウンター: 1

### コードのタイミングを調整する

ラベル付きタイマーを使って、特定の操作を完了するまでの時間を測定するコードをインストルメント化します。

コマンド | &nbsp;
:------------ | :-------------
[**時刻 ()**](https://developer.mozilla.org/docs/Web/API/Console/time) | 指定されたラベルのタイマーを開始します。
[**timeEnd ()**](https://developer.mozilla.org/docs/Web/API/Console/timeEnd) | 指定されたラベルのタイマーを終了し、経過時間 (ミリ秒単位) を報告します。
[**timeStamp ()**](https://developer.mozilla.org/docs/Web/API/Console/timeStamp) | 現在のシステム時刻 (ミリ秒単位) を報告します。

たとえば、次の行をコンソールで実行してみてください。

```javascript
console.time('My Timer');
console.timeEnd('My Timer');
```

### ヒープスナップショットの取得

ヒープのスナップショットを取得して、実行しているコードのメモリ使用量を評価し、メモリリークを特定します。

コマンド | &nbsp;
:------------ | :-------------
**Heapsnapshot () の場合** | 現在の JavaScript ヒープと割り当てられているオブジェクトに関する詳細をキャプチャします。

ヒープスナップショットを取得するためには、DevTools[メモリプロファイラー](../memory.md#toolbar)が実行されている必要があります。 各スナップショットは、[**メモリ**](../memory.md)パネルのスナップショットの[*概要*](../memory.md#snapshot-summary)のタイルとして表示され、さらに検査できます。

## トレース callstacks

コードの呼び出し元、実行されているコード、実行にかかる時間を理解することは、遅く、または予期しない動作を分析するときに役立ちます。 スタックトレースには、コードから到達するために実行された実行パスが、トレース要求からパスを上向きに表示されます。 

コマンド | &nbsp;
:------------ | :-------------
[**trace ()**](https://developer.mozilla.org/docs/Web/API/Console/trace) | 現在のスクリプト実行呼び出し履歴のトレースを出力します。

たとえば、次のコードをコンソールで実行します。

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

. . . 次のスタックトレースが出力されます。
> console. trace () (eval コード: 8: 3) を、eval コード (eval コード:14: 1) で (eval コード: 2: 3)
> 
> console. trace () at c (eval コード: 8: 3) で、d (eval コード: 5: 3) を評価コード (eval コード:15: 1) で実行します。

## ログ出力を整理する

単に以前のコンソール出力をすべてクリアするには、 *console. ()* (または) を使用 `CTRL + L` します。 これにより、本体のコマンド履歴の backstack は消去されません (上下の方向キーを使って引き続きスキャンできます)。

コマンド | &nbsp;
:------------ | :-------------
[**clear ()**](https://developer.mozilla.org/docs/Web/API/Console/clear) | 以前の本体の出力をすべてクリアします。

コードによって多くのコンソールメッセージが出力される場合は、次のコマンドを使用して、入れ子になったブロックに視覚的に整理できます。

 コマンド | &nbsp;
:------------ | :-------------
[**group ()**](https://developer.mozilla.org/docs/Web/API/Console/group) | 指定された (省略可能) ラベルを使って、コンソール出力に対して新しいレベルの入れ子を開始します。
[**groupCollapsed れている ()**](https://developer.mozilla.org/docs/Web/API/Console/groupCollapsed) | 指定された (省略可能) ラベルを使って、コンソール出力に対して新しいレベルの入れ子を開始します。ただし、グループ化コントロールは既定で折りたたまれており、(矢印コントロールをクリックして) 子出力を表示する必要があります。
[**groupEnd ()**](https://developer.mozilla.org/docs/Web/API/Console/groupEnd) | 指定されたラベルのネストグループを終了します。

たとえば、コンソールで次のコマンドを入力します。

```javascript
console.groupCollapsed('Group 1');
console.log('In Group 1');
console.groupCollapsed('Group 1.1');
console.log('In Group 1.1');
console.groupEnd('Group 1.1');
console.groupEnd('Group 1');
console.log('No longer in a group');
```

. . . 次に、*グループ 1*と*グループの 1.1*コントロールを展開して、ログのコメントがどのようにネストされているかを確認します。

![コンソールでのメッセージのグループ化](../media/console_api_group.png)

JavaScript オブジェクトまたは配列を単純なリストではなく、表形式でビジュアル化することができます。 そのためには、 *console ()* コマンドを使うことができます。

コマンド | &nbsp;
:------------ | :-------------
[**table ()**](https://developer.mozilla.org/docs/Web/API/Console/table) | 指定した配列またはオブジェクトを、表形式でコンソールに出力します。

たとえば、次のオブジェクト配列を使用します。

```javascript
var orders = [{'Size':'XL', 'Quantity':1},{'Size':'M', 'Quantity':3}, {'Size':'L', 'Quantity':2}];
console.table(orders);
```

. . . コンソールに次の表のように表示されます。

![コンソールでオブジェクト配列を表として表示する](../media/console_api_table.png)
