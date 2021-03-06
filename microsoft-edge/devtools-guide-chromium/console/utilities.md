---
description: Microsoft Edge DevTools コンソールで使用できる便利なコマンドの参照。
title: コンソール ユーティリティ API リファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: e7253bf5402a03d1659f56ba083bb87e93b3af38
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398827"
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

# <a name="console-utilities-api-reference"></a>コンソール ユーティリティ API リファレンス  

コンソール ユーティリティ API には、DOM 要素の選択と検査、読み取り可能な形式でのデータの表示、プロファイラーの停止と開始、DOM イベントの監視など、一般的なタスクを実行するための便利なコマンドのコレクションが含まれています。  

> [!WARNING]
> 次のコマンドは、Microsoft Edge DevTools コンソールでのみ機能します。  スクリプトから実行すると、コマンドは機能しません。  

メソッドと `console.log()` メソッド `console.error()` の残りの部分については、[コンソール API リファレンス] `console.*` [に移動します][DevToolsConsoleApi]。  

## <a name="recently-evaluated-expression"></a>最近評価された式  

```console
$_
```  

最近評価された式の値を返します。  

次の図では、単純な式 \( `2 + 2` \) が評価されます。  その `$_` 後、同じ値を含むプロパティが評価されます。  

:::image type="complex" source="../media/console-arithmatic.msft.png" alt-text="$_ は、最近評価された式です。" lightbox="../media/console-arithmatic.msft.png":::
   図 1:  `$_` 最も最近評価された式  
:::image-end:::  

次の図では、評価された式には最初に名前の配列が含まれます。  配列の長さを見つけるために評価すると、変更に格納された値が最新の評価式 `$_.length` `$_` になります `4` 。  

:::image type="complex" source="../media/console-array-length.msft.png" alt-text="$しいコマンドが評価される場合の $_ の変更" lightbox="../media/console-array-length.msft.png":::
   図 2:  `$_` 新しいコマンドが評価される場合の変更点  
:::image-end:::  

## <a name="recently-chosen-element-or-javascript-object"></a>最近選択した要素または JavaScript オブジェクト  

```console
$0
```  

最近選択した要素または JavaScript オブジェクトを返します。  `$1` 2 番目に最近選択した 1 つを返します。などです。  、 、 、 、およびコマンドは、Elements ツール内で検査された最後の 5 つの DOM 要素、またはメモリ ツールで選択された最後の 5 つの JavaScript ヒープ オブジェクトへの履歴参照として `$0` `$1` `$2` `$3` `$4` **機能**します。 ****  

:::row:::
   :::column span="1":::
      ```console
      $0
      ```  
   :::column-end:::
   :::column span="1":::
      ```console
      $1
      ```  
   :::column-end:::
   :::column span="1":::
      ```console
      $2
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      ```console
      $3
      ```  
   :::column-end:::
   :::column span="1":::
      ```console
      $4
      ```  
   :::column-end:::
   :::column span="1":::
   :::column-end:::
:::row-end:::  

次の図では、要素 `img` ツールで要素が **選択** されています。  コンソール ドロ **ワーで** 、 `$0` 評価され、同じ要素が表示されます。  

:::image type="complex" source="../media/console-image-highlighted-$0.msft.png" alt-text="$0" lightbox="../media/console-image-highlighted-$0.msft.png":::
   図 3: `$0`  
:::image-end:::  

次の図では、同じページで選択されている別の要素を示しています。  ここで `$0` 、新しく選択した要素を参照し、前に選択した要素 `$1` を返します。  

:::image type="complex" source="../media/console-image-highlighted-$1.msft.png" alt-text="$1" lightbox="../media/console-image-highlighted-$1.msft.png":::
   図 4: `$1`  
:::image-end:::  

## <a name="query-selector"></a>クエリ セレクター  

```console
$(selector, [startNode])
```  

指定した CSS セレクターを持つ最初の DOM 要素への参照を返します。  このメソッドは [、document.querySelector() メソッドのエイリアス][MDNDocumentQuerySelector] です。  

次の図では、ドキュメントの最初の `<img>` 要素への参照が返されます。  

:::image type="complex" source="../media/console-element-selector-image.msft.png" alt-text="$('img')" lightbox="../media/console-element-selector-image.msft.png":::
   図 5: `$('img')`  
:::image-end:::  

返された結果にカーソルを合わせると、コンテキスト メニュー \(右クリック\) を開き、[要素パネルで表示]******を選択して**DOM で検索するか、[表示] にスクロールしてページに表示します。  

次の図では、現在選択されている要素への参照が返され、src プロパティが表示されます。  

:::image type="complex" source="../media/console-element-selector-image-source.msft.png" alt-text="$('img').src" lightbox="../media/console-element-selector-image-source.msft.png":::
   図 6: `$('img').src`  
:::image-end:::  

このメソッドは、要素を検索する "要素" または Node を指定する 2 番目のパラメーター startNode もサポートします。  パラメーターの既定値はです `document` 。  

次の図では、最初の要素 `img` が見つかり、正 `title--image` しく表示 `src` されます。  

:::image type="complex" source="../media/console-element-selector-image-filter-source.msft.png" alt-text="$('img', document.querySelector('title--image')).src" lightbox="../media/console-element-selector-image-filter-source.msft.png":::
   図 7: `$('img', document.querySelector('title--image')).src`  
:::image-end:::  

> [!NOTE]
> 使用する jQuery などのライブラリを使用している場合、機能は上書きされ、そのライブラリの実装 `$` `$` に対応します。  

## <a name="query-selector-all"></a>クエリ セレクター すべて  

```console
$$(selector, [startNode])
```  

指定した CSS セレクターに一致する要素の配列を返します。  このメソッドは [、document.querySelectorAll() メソッドの実行と同][MDNDocumentQuerySelectorAll] じです。  

次のコード サンプルと図では、現在のドキュメント内のすべての要素の配列を作成し、各要素のプロパティの値 `$$()` `<img>` `src` を表示します。  

```console
var images = $$('img');
for (each in images) {
    console.log(images[each].src);
}
```  

:::image type="complex" source="../media/console-element-selector-image-all.msft.png" alt-text="$$() を使用してドキュメント内のすべての画像を選択し、ソースを表示する" lightbox="../media/console-element-selector-image-all.msft.png":::
   図 8: 文書 `$$()` 内のすべての画像を選択し、ソースを表示する使用  
:::image-end:::  

このメソッドは、要素を検索する要素または Node を指定する 2 番目のパラメーター startNode もサポートします。  パラメーターの既定値はです `document` 。  

次のコード サンプルと図では、前のコード サンプルと図の変更バージョンを使用して、選択したノードの後に現在のドキュメントに表示されるすべての要素の配列 `$$()` `<img>` を作成します。  

```console
var images = $$('img', document.querySelector(`title--image`));
for (each in images) {
   console.log(images[each].src);
}
```  

:::image type="complex" source="../media/console-element-selector-image-filter-all.msft.png" alt-text="$$() を使用して、指定した div <の後に表示>を選択し、ソースを表示する" lightbox="../media/console-element-selector-image-filter-all.msft.png":::
   図 9: 文書内の指定された要素の後に表示される画像を選択し、ソース `$$()` `<div>` を表示する場合に使用する  
:::image-end:::  

> [!NOTE]
> スクリプト `Shift` + `Enter` を実行せずに新しい行を開始するには、コンソールで選択します。  

## <a name="xpath"></a>XPath  

```console
$x(path, [startNode])
```  

指定した XPath 式に一致する DOM 要素の配列を返します。  

次のコード サンプルと図では、ページ上のすべての要素 `<p>` が返されます。  

```console
$x("//p")
```  

:::image type="complex" source="../media/console-array-xpath.msft.png" alt-text="XPath セレクターの使用" lightbox="../media/console-array-xpath.msft.png":::
   図 10: XPath セレクターの使用  
:::image-end:::  

次のコード サンプルと図では、要素を含む `<p>` すべての要素 `<a>` が返されます。  

```console
$x("//p[a]")
```  

:::image type="complex" source="../media/console-array-xpath-sub-element.msft.png" alt-text="より複雑な XPath セレクターの使用" lightbox="../media/console-array-xpath-sub-element.msft.png":::
   図 11: より複雑な XPath セレクターの使用  
:::image-end:::  

他のセレクター コマンドと同様に、要素を検索する要素または Node を指定するオプションの 2 番目の `$x(path)` `startNode` パラメーターがあります。  

:::image type="complex" source="../media/console-array-xpath-startnode.msft.png" alt-text="startNode で XPath セレクターを使用する" lightbox="../media/console-array-xpath-startnode.msft.png":::
   図 12: XPath セレクターを使用する `startNode`  
:::image-end:::  

## <a name="clear"></a>clear  

```console
clear()
```  

履歴のコンソールをクリアします。  

```console
clear()
```  

## <a name="copy"></a>copy  

```console
copy(object)
```  

この `copy(object)` メソッドは、指定したオブジェクトの文字列表現をクリップボードにコピーします。  

```console
copy($0)
```  

## <a name="debug"></a>デバッグ  

```console
debug(method)
```  

>[!NOTE]
> クロム [の問題#1050237][MonorailIssue1050237] 関数のバグを追跡 `debug()` しています。  問題が発生した場合は、代 [わりにブレークポイントを使用][DevtoolsJavascriptBreakpoints] してみてください。  

指定したメソッドを要求すると、デバッガーが呼び出され、ソース ツールの**** メソッド内でブレークされ、コードをステップ実行してデバッグできます。  

```console
debug("debug");
```  

:::image type="complex" source="../media/console-debug-text.msft.png" alt-text="debug() を使用してメソッド内でブレークする" lightbox="../media/console-debug-text.msft.png":::
   図 13: メソッド内でのブレーク `debug()`  
:::image-end:::  

メソッド `undebug(method)` のブレークを停止したり、UI を使用してすべてのブレークポイントを無効にしたりするために使用します。  

ブレークポイントの詳細については、「ブレークポイントを使用してコード [を一時停止する」に移動します][DevToolsJavascriptBreakpoints]。  

## <a name="dir"></a>dir  

```console
dir(object)
```  

指定したオブジェクトのすべてのプロパティのオブジェクト スタイルの一覧を表示します。  このメソッドは [console.dir() メソッドのエイリアス][MDNConsoleDir] です。  

コンソール `document.head` で評価し、タグとタグの間に HTML `<head>` を表示 `</head>` します。  次のコード サンプルと図では、コンソールで使用した後にオブジェクト スタイルの一覧 `console.dir()` が表示されます。  

```console
document.head;
dir(document.head);
```  

:::image type="complex" source="../media/console-dir-document-head-expanded.msft.png" alt-text="dir() メソッドを使用して document.head をログに記録する" lightbox="../media/console-dir-document-head-expanded.msft.png":::
   図 14: メソッドによる `document.head` `dir()` ログ記録  
:::image-end:::  

詳細については、コンソール [`console.dir()`][DevToolsConsoleApiConsoleDirObject] API のエントリに移動します。  

## <a name="dirxml"></a>dirxml  

```console
dirxml(object)
```  

要素ツールに表示される、指定したオブジェクトの XML 表現を **印刷** します。  このメソッドは [console.dirxml() メソッドと同][MDNConsoleDirxml] じです。  

## <a name="inspect"></a>検査  

```console
inspect(object/method)
```  

適切なパネルで、指定した要素またはオブジェクト (DOM 要素の**** 要素ツールまたは JavaScript**** ヒープ オブジェクトのメモリ ツール) を開いて選択します。  

次のコード サンプルと図では、要素 `document.body` ツールで **開** きます。  

```console
inspect(document.body);
```  

:::image type="complex" source="../media/console-inspect-document-body.msft.png" alt-text="inspect() を使用して要素を検査する" lightbox="../media/console-inspect-document-body.msft.png":::
   図 15: で要素を検査する `inspect()`  
:::image-end:::  

検査するメソッドを渡す場合、メソッドは[ソース]**** ツールでドキュメントを開き、検査を行います。  

## <a name="geteventlisteners"></a>getEventListeners  

```console
getEventListeners(object)
```  

指定したオブジェクトに登録されているイベント リスナーを返します。  戻り値は、登録されているイベントの種類 \(または \など) ごとに配列を含む `click` オブジェクト `keydown` です。  各配列のメンバーは、各型に登録されているリスナーを表すオブジェクトです。  次のコード サンプルの図では、ドキュメント オブジェクトに登録されているイベント リスナーのすべてが一覧表示されます。  

```console
getEventListeners(document);
```  

:::image type="complex" source="../media/console-elements-event-listeners-console-get-event-listeners-document.msft.png" alt-text="getEventListeners(document) の使用の出力" lightbox="../media/console-elements-event-listeners-console-get-event-listeners-document.msft.png":::
   図 16: 使用の結果 `getEventListeners(document)`  
:::image-end:::  

指定したオブジェクトに複数のリスナーが登録されている場合、配列にはリスナーごとにメンバーが含まれる。  次の図では、イベントの document 要素に 2 つのイベント リスナーが登録 `click` されています。  

:::image type="complex" source="../media/console-elements-event-listeners-console-get-event-listeners-document-expanded-1.msft.png" alt-text="複数のリスナー" lightbox="../media/console-elements-event-listeners-console-get-event-listeners-document-expanded-1.msft.png":::
   図 17: 複数のリスナー  
:::image-end:::  

次の各オブジェクトをさらに展開して、プロパティを確認できます。  

:::image type="complex" source="../media/console-elements-event-listeners-console-get-event-listeners-document-2.msft.png" alt-text="リスナー オブジェクトの拡張ビュー" lightbox="../media/console-elements-event-listeners-console-get-event-listeners-document-2.msft.png":::
   図 18: リスナー オブジェクトの拡張ビュー  
:::image-end:::  

## <a name="keys"></a>キー  

```console
keys(object)
```  

指定したオブジェクトに属するプロパティの名前を含む配列を返します。  同じプロパティの関連する値を取得するには、 を使用します `values()` 。  

たとえば、アプリケーションが次のオブジェクトを定義したとします。  

```console
var player1 =   
```  

次のコード サンプルと図では、入力する前とコンソールでグローバル名前空間 \(簡易\) で定義されたと `player1` `keys(player1)` `values(player1)` 仮定します。  

```console
keys(player1)

values(player1)
```  

:::image type="complex" source="../media/console-keys-values.msft.png" alt-text="keys() コマンドと values() コマンド" lightbox="../media/console-keys-values.msft.png":::
   図 19: `keys()` and `values()` コマンド  
:::image-end:::  

## <a name="monitor"></a>モニター  

```console
monitor(method)
```  

呼び出されたメソッドに渡される引数と共に、メソッド名を示すメッセージをコンソールにログに記録します。  

```console
function sum(x, y) {
    return x + y;
}
monitor(sum);
```  

:::image type="complex" source="../media/console-function-monitor-sum.msft.png" alt-text="monitor() メソッド" lightbox="../media/console-function-monitor-sum.msft.png":::
   図 20: `monitor()` メソッド  
:::image-end:::  

監視 `unmonitor(method)` を停止するために使用します。  

## <a name="monitorevents"></a>monitorEvents  

```console
monitorEvents(object[, events])
```  

指定したオブジェクトで指定されたイベントの 1 つが発生すると、イベント オブジェクトはコンソールに記録されます。  監視する 1 つのイベント、イベントの配列、または定義済みのイベント のコレクションにマップされる一般的なイベントの種類のいずれかを指定できます。  次のコード サンプルと図を確認します。  

次に、window オブジェクト上のすべてのサイズ変更イベントを監視します。  

```console
monitorEvents(window, "resize");
```  

:::image type="complex" source="../media/console-monitor-events-resize-window.msft.png" alt-text="ウィンドウのサイズ変更イベントの監視" lightbox="../media/console-monitor-events-resize-window.msft.png":::
   図 21: 監視ウィンドウのサイズ変更イベント  
:::image-end:::  

次に、window オブジェクトの両方とイベントを監視 `resize` `scroll` する配列を定義します。  

```console
monitorEvents(window, ["resize", "scroll"]);
```  

使用可能なイベントの種類の 1 つ、定義済みのイベント セットにマップする文字列を指定することもできます。  次の表に、使用可能なイベントの種類と関連付けられたイベント マッピングを示します。  

| イベントの種類 | 対応するマップされたイベント |  
|:--- |:--- |  
| `mouse` | "click"、"dblclick"、"mousedown"、"mousemove"、"mouseout"、"mouseover"、"mouseup"、"mousewheel" |  
| `key` | "keydown"、"keypress"、"keyup"、"textInput" |  
| `touch` | "touchcancel", "touchend", "touchmove", "touchstart" |  
| `control` | "ぼかし"、"change"、"focus"、"reset"、"resize"、"scroll"、"select"、"submit"、"zoom" |  

次のコード サンプルでは、入力テキスト フィールドのイベントに対応するイベントの種類が現在、要素 `key` `key` ツールで **選択** されています。  

```console
monitorEvents($0, "key");
```  

次の図では、テキスト フィールドに文字を入力した後の出力例が表示されます。  

:::image type="complex" source="../media/console-monitor-events-type-t-y.msft.png" alt-text="主要なイベントの監視" lightbox="../media/console-monitor-events-type-t-y.msft.png":::
   図 22: キー イベントの監視  
:::image-end:::  

## <a name="profile"></a>profile  

```console
profile([name])
```  

オプションの名前で JavaScript CPU プロファイリング セッションを開始します。  [profileEnd() メソッドは](#profileend)プロファイルを完了し、結果を Memory ツールに**表示**します。  <!--Navigate to [Speed Up JavaScript Runtime][DevToolsRenderingToolsJSRuntime].  -->  

1.  プロファイリングを `profile()` 開始するには、メソッドを実行します。  
    
    ```console
    profile("My profile")
    ```  
    
1.  [profileEnd() メソッド](#profileend)を実行してプロファイリングを停止し、結果を Memory ツールに**表示**します。  

プロファイルは入れ子にされる場合があります。  次のコード サンプルと図では、順序に関係なく結果は同じです。  

```console
profile('A');
profile('B');
profileEnd('A');
profileEnd('B');
```  

> [!NOTE]
> 複数の CPU プロファイルが同時に動作する場合があります。作成順序で各 CPU プロファイルを閉じる必要はありません。  

## <a name="profileend"></a>profileEnd  

```console
profileEnd([name])
```  

JavaScript CPU プロファイリング セッションを完了し、結果をメモリ ツールに **表示** します。  [profile() メソッドを実行している必要](#profile)があります。  <!--Navigate to [Speed Up JavaScript Runtime][DevToolsRenderingToolsJSRuntime].  -->  

1.  [profile() メソッドを実行](#profile)してプロファイリングを開始します。  
1.  このメソッド `profileEnd()` を実行して、プロファイリングを停止し、結果をメモリ ツールに **表示** します。  
    
    ```console
    profileEnd("My profile")
    ```  

プロファイルは入れ子にされる場合があります。  次のコード サンプルと図では、順序に関係なく結果は同じです。  

```console
profile('A');
profile('B');
profileEnd('A');
profileEnd('B');
```  

結果は、メモリ ツールのヒープ スナップショットとして **表示** されます。  

:::image type="complex" source="../media/console-memory-multiple-cpu-profiles.msft.png" alt-text="グループ化されたプロファイル" lightbox="../media/console-memory-multiple-cpu-profiles.msft.png":::
   図 23: グループ化されたプロファイル  
:::image-end:::  

> [!NOTE]
> 複数の CPU プロファイルが同時に動作する場合があります。作成順序で各 CPU プロファイルを閉じる必要はありません。  

## <a name="queryobjects"></a>queryObjects  

```console
queryObjects(Constructor)
```  

指定したコンストラクターで作成されたオブジェクトの配列を返します。  スコープは `queryObjects()` 、コンソールで現在選択されているランタイム コンテキストです。

:::row:::
   :::column span="1":::
      ```console
      queryObjects(promise)
      ```  
      
      all を返します `Promises` 。  
   :::column-end:::
   :::column span="1":::
      ```console
      queryObjects(HTMLElement)
      ```  
      
      すべての HTML 要素を返します。  
   :::column-end:::
   :::column span="1":::
      ```console
      queryObjects(functionName)
      ```  
      
      を使用してインスタンス化されたすべてのオブジェクトを返します `new functionName()` 。  
   :::column-end:::
:::row-end:::  

---  

## <a name="table"></a>table  

```console
table(data[, columns])
```  

オプションの列見出しを使用して、データ オブジェクトに基づいてテーブルの書式設定を使用してオブジェクト データをログに記録します。  次のコード サンプルと図では、コンソール内のテーブルを使用する名前の一覧が表示されます。  

```console
var names = {
    0:  {
        firstName:  "John",
        lastName:  "Smith"
    },
    1:  {
        firstName:  "Jane",
        lastName:  "Doe"
    }
};
table(names);
```  

:::image type="complex" source="../media/console-table-display.msft.png" alt-text="table() メソッドの結果" lightbox="../media/console-table-display.msft.png":::
   図 24: メソッドの `table()` 結果  
:::image-end:::  

## <a name="undebug"></a>undebug  

```console
undebug(method)
```  

指定したメソッドのデバッグを停止し、メソッドが呼び出されるとデバッガーが呼び出されなくなりました。  

```console
undebug(getData);
```  

## <a name="unmonitor"></a>unmonitor  

```console
unmonitor(method)
```  

指定したメソッドの監視を停止します。  このメソッドは monitor() メソッドと一 [緒に使用](#monitor) されます。  

```console
unmonitor(getData);
```  

## <a name="unmonitorevents"></a>unmonitorEvents  

```console
unmonitorEvents(object[, events])
```  

指定したオブジェクトとイベントの監視イベントを停止します。  たとえば、次の例では、window オブジェクト上のすべてのイベント監視を停止します。  

```console
unmonitorEvents(window);
```  

また、オブジェクトの特定のイベントの監視を選択的に停止することもできます。  たとえば、次のコードは、現在選択されている要素のすべてのイベントの監視を開始し、イベントの監視を停止します \(コンソール出力のノイズを低減 `mouse` `mousemove` する場合があります\)。  

```console
monitorEvents($0, "mouse");
unmonitorEvents($0, "mousemove");
```  

## <a name="values"></a>値  

```console
values(object)
```  

指定したオブジェクトに属するすべてのプロパティの値を含む配列を返します。  

```console
values(object);
```  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsConsoleApi]: /microsoft-edge/devtools-guide-chromium/console/api "コンソール API リファレンス"  
[DevToolsConsoleApiConsoleDirObject]: /microsoft-edge/devtools-guide-chromium/console/api#dir "dir - コンソール API リファレンス"  
[DevToolsJavascriptBreakpoints]: /microsoft-edge/devtools-guide-chromium/javascript/breakpoints "Microsoft Edge DevTools でブレークポイントを使用してコードを一時停止する方法"  
[DevToolsRenderingToolsJSRuntime]: /microsoft-edge/devtools-guide-chromium/rendering-tools/js-runtime "JavaScript ランタイムの高速化"  

[MDNConsoleDir]: https://developer.mozilla.org/docs/Web/API/Console/dir "Console.dir() |MDN"  
[MDNConsoleDirxml]: https://developer.mozilla.org/docs/Web/API/Console/dirxml "Console.dirxml() |MDN"  
[MDNDocumentQuerySelector]: https://developer.mozilla.org/docs/Web/API/Document/querySelector "Document.querySelector() |MDN"  
[MDNDocumentQuerySelectorAll]: https://developer.mozilla.org/docs/Web/API/Document/querySelectorAll "Document.querySelectorAll() |MDN"  

[MonorailIssue1050237]: https://bugs.chromium.org/p/chromium/issues/detail?id=1050237 "問題 1050237: debug(function) が動作|モノレール"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/console/utilities) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
