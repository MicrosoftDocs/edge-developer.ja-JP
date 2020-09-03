---
description: Microsoft Edge DevTools コンソールで利用できる便利なコマンドの参照。
title: コンソールユーティリティ API リファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 2882d980e6da45072cab4b028ceb1838a9078064
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993108"
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

# コンソールユーティリティ API リファレンス  

コンソールユーティリティ API には、一般的なタスク (DOM 要素の選択と検査、読み取り可能な形式でのデータの表示、プロファイラーの停止と開始、DOM イベントの監視) を実行するための便利なコマンドのコレクションが含まれています。  

> [!WARNING]
> 次のコマンドは、Microsoft Edge DevTools コンソールでのみ動作します。  スクリプトから実行した場合、コマンドは機能しません。  

およびその他のメソッドを探してい `console.log()` `console.error()` `console.*` ますか?  「 [コンソール API リファレンス][DevToolsConsoleApi]」をご覧ください。  

## 最近評価された式  

```console
$_
```  

直近に評価された式の値を返します。  

次の図では、単純な式 \ (\ `2 + 2` ) が評価されています。  `$_`プロパティが評価され、同じ値が含まれます。  

:::image type="complex" source="../media/console-arithmatic.msft.png" alt-text="$ _ は、最近評価された式です。" lightbox="../media/console-arithmatic.msft.png":::
   図 1:  `$_` 前回評価された式  
:::image-end:::  

次の図では、評価式には最初に名前の配列が含まれています。  評価して `$_.length` 配列の長さを確認します。変更された値は、 `$_` 最新の評価済みの式になり `4` ます。  

:::image type="complex" source="../media/console-array-length.msft.png" alt-text="新しいコマンドが評価されたときの $ _ 変更" lightbox="../media/console-array-length.msft.png":::
   図 2:  `$_` 新しいコマンドの評価時の変更点  
:::image-end:::  

## 最近選んだ要素または JavaScript オブジェクト  

```console
$0
```  

最後に選択された要素または JavaScript オブジェクトを返します。  `$1` 最後に選択された2番目の値を返します。  、、、、 `$0` `$1` およびコマンドは、 `$2` `$3` `$4` **要素** パネル内で検査された最後の5つの DOM 要素、または **メモリ** パネルで選択された最後の5つの JavaScript ヒープオブジェクトへの履歴参照として機能します。  

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

次の図では、[ `img` **要素** ] パネルで要素が選択されています。  **本体**のドロアーで、 `$0` 評価が完了し、同じ要素が表示されます。  

:::image type="complex" source="../media/console-image-highlighted-$0.msft.png" alt-text="$0" lightbox="../media/console-image-highlighted-$0.msft.png":::
   図 3: `$0`  
:::image-end:::  

次の図では、同じページで選択された別の要素が画像に表示されています。  現在選択されている `$0` 要素を参照して `$1` いますが、以前に選択されていた要素を返します。  

:::image type="complex" source="../media/console-image-highlighted-$1.msft.png" alt-text="$1" lightbox="../media/console-image-highlighted-$1.msft.png":::
   図 4: `$1`  
:::image-end:::  

## クエリセレクター  

```console
$(selector, [startNode])
```  

指定された CSS セレクターで最初の DOM 要素への参照を返します。  このメソッドは、 [ドキュメントの querySelector ()][MDNDocumentQuerySelector] メソッドのエイリアスです。  

次の図では、文書内の最初の要素への参照 `<img>` が返されます。  

:::image type="complex" source="../media/console-element-selector-image.msft.png" alt-text="$ (' Img ')" lightbox="../media/console-element-selector-image.msft.png":::
   図 5: `$('img')`  
:::image-end:::  

返された結果にポインターを置いて、コンテキストメニュー \ (右クリック \) を開き、[ **要素パネルで** 表示] を選択して DOM で見つけるか、表示されたらページ上に **スクロール** して表示します。  

次の図では、現在選択されている要素への参照が返され、src プロパティが表示されます。  

:::image type="complex" source="../media/console-element-selector-image-source.msft.png" alt-text="$ (' Img ') src" lightbox="../media/console-element-selector-image-source.msft.png":::
   図 6: `$('img').src`  
:::image-end:::  

このメソッドは、要素を検索する "element" またはノードを指定する2番目のパラメーター startNode もサポートしています。  パラメーターの既定値は `document` です。  

次の図では、最初 `img` の要素がであり、 `title--image` 正しく表示され `src` ます。  

:::image type="complex" source="../media/console-element-selector-image-filter-source.msft.png" alt-text="$ (' Img '、ドキュメントの querySelector (' タイトル--image ')) src" lightbox="../media/console-element-selector-image-filter-source.msft.png":::
   図 7: `$('img', document.querySelector('title--image')).src`  
:::image-end:::  

> [!NOTE]
> 使用している jQuery などのライブラリを使用している場合、 `$` 機能は上書きされ、 `$` そのライブラリの実装に対応します。  

## すべてのクエリセレクター  

```console
$$(selector, [startNode])
```  

指定された CSS セレクターに一致する要素の配列を返します。  このメソッドは、 [querySelectorAll ()][MDNDocumentQuerySelectorAll] メソッドを呼び出すことと同じです。  

次のコードサンプルと図では、を使用して、 `$$()` 現在のドキュメント内のすべての要素の配列を作成 `<img>` し、各要素のプロパティの値を表示し `src` ます。  

```console
var images = $$('img');
for (each in images) {
    console.log(images[each].src);
}
```  

:::image type="complex" source="../media/console-element-selector-image-all.msft.png" alt-text="$ $ () を使用して、ドキュメント内のすべての画像を選択し、ソースを表示する" lightbox="../media/console-element-selector-image-all.msft.png":::
   図 8: `$$()` ドキュメント内のすべての画像を選択してソースを表示するために使用する  
:::image-end:::  

このメソッドは、要素を検索する要素またはノードを指定する2番目の parameter startNode もサポートしています。  パラメーターの既定値は `document` です。  

次のコードサンプルと図では、前のコードサンプルと図を変更したバージョンを使って、選択した `$$()` `<img>` ノードの後に現在の文書内に出現するすべての要素の配列を作成します。  

```console
var images = $$('img', document.querySelector(`title--image`));
for (each in images) {
   console.log(images[each].src);
}
```  

:::image type="complex" source="../media/console-element-selector-image-filter-all.msft.png" alt-text="$ $ () を使用して、文書内の指定された <div> 要素の後に表示されるすべての画像を選択して、ソースを表示する" lightbox="../media/console-element-selector-image-filter-all.msft.png":::
   図 9: `$$()` 文書内の指定された要素の後に表示されるすべての画像を選択して `<div>` ソースを表示する  
:::image-end:::  

> [!NOTE]
> コンソールを押して、 `Shift` + `Enter` スクリプトを実行せずに、新しい行を開始します。  

## X  

```console
$x(path, [startNode])
```  

指定された XPath 式と一致する DOM 要素の配列を返します。  

次のコードサンプルと図では、ページ上のすべての `<p>` 要素が返されます。  

```console
$x("//p")
```  

:::image type="complex" source="../media/console-array-xpath.msft.png" alt-text="XPath セレクターを使用する" lightbox="../media/console-array-xpath.msft.png":::
   図 10: XPath セレクターを使用する  
:::image-end:::  

次のコードサンプルと図では、要素を `<p>` 含むすべての要素 `<a>` が返されます。  

```console
$x("//p[a]")
```  

:::image type="complex" source="../media/console-array-xpath-sub-element.msft.png" alt-text="より複雑な XPath セレクターを使用する" lightbox="../media/console-array-xpath-sub-element.msft.png":::
   図 11: より複雑な XPath セレクターを使用する  
:::image-end:::  

他のセレクターコマンドと同様に、 `$x(path)` `startNode` 要素を検索する要素またはノードを指定する、オプションの2番目のパラメーターを持ちます。  

:::image type="complex" source="../media/console-array-xpath-startnode.msft.png" alt-text="StartNode で XPath セレクターを使用する" lightbox="../media/console-array-xpath-startnode.msft.png":::
   図 12: で XPath セレクターを使用する `startNode`  
:::image-end:::  

## clear  

```console
clear()
```  

履歴の本体をクリアします。  

```console
clear()
```  

## copy  

```console
copy(object)
```  

メソッドによって、 `copy(object)` 指定したオブジェクトの文字列表現がクリップボードにコピーされます。  

```console
copy($0)
```  

## デバッグ  

```console
debug(method)
```  

>[!NOTE]
> [Chromium 問題 #1050237][MonorailIssue1050237]は、関数のバグを追跡 `debug()` しています。  この問題が発生した場合は、代わりに [ブレークポイントを使用][DevtoolsJavascriptBreakpoints] してみてください。  

指定したメソッドを要求すると、デバッガーが呼び出され、 **ソース** パネルのメソッド内で中断されます。これにより、コードをステップ実行してデバッグすることができます。  

```console
debug("debug");
```  

:::image type="complex" source="../media/console-debug-text.msft.png" alt-text="Debug () を使用したメソッド内の中断" lightbox="../media/console-debug-text.msft.png":::
   図 13: メソッド内での区切り `debug()`  
:::image-end:::  

`undebug(method)`メソッドの中断を停止するには、または UI を使ってすべてのブレークポイントを無効にする場合に使用します。  

ブレークポイントの詳細については、「 [ブレークポイントでコードを一時停止][DevToolsJavascriptBreakpoints]する」を参照してください。  

## dir  

```console
dir(object)
```  

指定したオブジェクトのすべてのプロパティのオブジェクトスタイルの一覧を表示します。  このメソッドは、 [console. dir ()][MDNConsoleDir] メソッドのエイリアスです。  

本体でを評価して、 `document.head` タグとタグの間に HTML を表示し `<head>` `</head>` ます。  次のコードサンプルと図では、コンソールで使用した後にオブジェクトスタイルの一覧が表示され `console.dir()` ます。  

```console
document.head;
dir(document.head);
```  

:::image type="complex" source="../media/console-dir-document-head-expanded.msft.png" alt-text="Dir () メソッドを使ってドキュメントをログに記録します。" lightbox="../media/console-dir-document-head-expanded.msft.png":::
   図 14: `document.head` メソッドを使用してログを記録する `dir()`  
:::image-end:::  

詳細については、 [`console.dir()`][DevToolsConsoleApiConsoleDirObject] 本体 API のエントリを参照してください。  

## dirxml  

```console
dirxml(object)
```  

[ **要素** ] タブに表示されるように、指定したオブジェクトの XML 表現を印刷します。 このメソッドは、console の [dirxml ()][MDNConsoleDirxml] メソッドと同じです。  

## 検査  

```console
inspect(object/method)
```  

適切なパネル (DOM 要素の場合は **要素** パネル、JavaScript ヒープオブジェクトの場合は **メモリ** パネル) で、指定された要素またはオブジェクトを開き、選択します。  

次のコードサンプルと図は、[ `document.body` **要素** ] パネルで開きます。  

```console
inspect(document.body);
```  

:::image type="complex" source="../media/console-inspect-document-body.msft.png" alt-text="検査 () での要素の検査" lightbox="../media/console-inspect-document-body.msft.png":::
   図 15: の要素を調べる `inspect()`  
:::image-end:::  

検査するメソッドを渡すとき、メソッドは **ソース** パネルでドキュメントを開き、調べることができます。  

## getEventListeners  

```console
getEventListeners(object)
```  

指定したオブジェクトに登録されているイベントリスナーを返します。  戻り値は、登録されている各イベントの種類 (やなど) の配列を含むオブジェクトです `click` `keydown` 。  各配列のメンバーは、各型に登録されているリスナーを記述するオブジェクトです。  次のコードサンプルの図は、ドキュメントオブジェクトに登録されているすべてのイベントリスナーを示しています。  

```console
getEventListeners(document);
```  

:::image type="complex" source="../media/console-elements-event-listeners-console-get-event-listeners-document.msft.png" alt-text="GetEventListeners を使った出力 (ドキュメント)" lightbox="../media/console-elements-event-listeners-console-get-event-listeners-document.msft.png":::
   図 16: を使用した場合の結果 `getEventListeners(document)`  
:::image-end:::  

指定したオブジェクトに複数のリスナーが登録されている場合、この配列には各リスナーのメンバーが含まれます。  次の図に、イベントのドキュメント要素に登録されている2つのイベントリスナーを示し `click` ます。  

:::image type="complex" source="../media/console-elements-event-listeners-console-get-event-listeners-document-expanded-1.msft.png" alt-text="複数のリスナー" lightbox="../media/console-elements-event-listeners-console-get-event-listeners-document-expanded-1.msft.png":::
   図 17: 複数のリスナー  
:::image-end:::  

次の各オブジェクトをさらに拡張して、プロパティを確認できます。  

:::image type="complex" source="../media/console-elements-event-listeners-console-get-event-listeners-document-2.msft.png" alt-text="リスナーオブジェクトの展開ビュー" lightbox="../media/console-elements-event-listeners-console-get-event-listeners-document-2.msft.png":::
   図 18: リスナーオブジェクトの展開ビュー  
:::image-end:::  

## キー  

```console
keys(object)
```  

指定したオブジェクトに属するプロパティの名前を含む配列を返します。  同じプロパティの関連する値を取得するには、を使用 `values()` します。  

たとえば、アプリケーションが次のオブジェクトを定義したとします。  

```console
var player1 = { "name":  "Ted", "level": 42 }
```  

次のコードサンプルと図では、 `player1` 入力と本体への入力前に、その結果がグローバル名前空間 \ (簡潔さ) で定義されていることを前提としてい `keys(player1)` `values(player1)` ます。  

```console
keys(player1)

values(player1)
```  

:::image type="complex" source="../media/console-keys-values.msft.png" alt-text="Keys () コマンドと values () コマンド" lightbox="../media/console-keys-values.msft.png":::
   図 19: `keys()` および `values()` コマンド  
:::image-end:::  

## モニター  

```console
monitor(method)
```  

メソッドが呼び出されたときにメソッドに渡された引数と共に、メソッド名を示すメッセージをコンソールに記録します。  

```console
function sum(x, y) {
    return x + y;
}
monitor(sum);
```  

:::image type="complex" source="../media/console-function-monitor-sum.msft.png" alt-text="Monitor () メソッド" lightbox="../media/console-function-monitor-sum.msft.png":::
   図 20: `monitor()` メソッド  
:::image-end:::  

`unmonitor(method)`監視を停止するために使用します。  

## monitorEvents  

```console
monitorEvents(object[, events])
```  

指定したイベントのいずれかが指定したオブジェクトで発生した場合、イベントオブジェクトは本体に記録されます。  監視する1つのイベント、一連のイベント、または定義済みのイベントコレクションにマップされる汎用イベント型のいずれかを指定できます。  次のコードサンプルと図を参照してください。  

次のモニターは、window オブジェクトのすべてのサイズ変更イベントを監視します。  

```console
monitorEvents(window, "resize");
```  

:::image type="complex" source="../media/console-monitor-events-resize-window.msft.png" alt-text="モニタリングウィンドウのサイズ変更イベント" lightbox="../media/console-monitor-events-resize-window.msft.png":::
   図 21: ウィンドウのサイズ変更イベントの監視  
:::image-end:::  

次の例では、window オブジェクトの両方のイベントとイベントを監視する配列を定義して `resize` `scroll` います。  

```console
monitorEvents(window, ["resize", "scroll"]);
```  

また、使用可能なイベントの種類のいずれかを指定することもできます。これは、事前定義された一連のイベントにマップされる文字列です。  以下の表に、利用可能なイベントの種類と関連付けられているイベントマッピングを示します。  

| イベントの種類 | 対応するマップされたイベント |  
|:--- |:--- |  
| `mouse` | "click"、"dblclick"、"mousedown"、"mousemove"、"mouseout"、"mousewheel"、"mouseup"、"" |  
| `key` | "keydown"、"keypress"、"keyup"、"textInput" |  
| `touch` | "touchcancel", "touchend", "touchmove", "touchstart" |  
| `control` | "ぼかし"、"変更"、"フォーカス"、"リセット"、"サイズ変更"、"スクロール"、"選択"、"送信"、"ズーム" |  

次のコードサンプルでは、 `key` 入力テキストフィールドのイベントに対応するイベントの種類が、[ `key` **要素** ] パネルで現在選択されています。  

```console
monitorEvents($0, "key");
```  

次の図では、テキストフィールドに文字を入力した後のサンプル出力が表示されています。  

:::image type="complex" source="../media/console-monitor-events-type-t-y.msft.png" alt-text="主要イベントの監視" lightbox="../media/console-monitor-events-type-t-y.msft.png":::
   図 22: 主要イベントの監視  
:::image-end:::  

## profile  

```console
profile([name])
```  

省略可能な名前で JavaScript CPU プロファイリングセッションを開始します。  Profile [end ()](#profileend) メソッドは、プロファイルを完了し、 **メモリ** パネルに結果を表示します。  <!--See also [Speed Up JavaScript Runtime][DevToolsRenderingToolsJSRuntime].  -->  

1.  メソッドを実行して `profile()` プロファイリングを開始します。  
    
    ```console
    profile("My profile")
    ```  
    
1.  プロファイルを停止して、**メモリ**パネルに結果を表示するには、 [profileend ()](#profileend)メソッドを実行します。  

プロファイルは入れ子にすることもできます。  次のコードサンプルと図では、注文に関係なく同じ結果が得られます。  

```console
profile('A');
profile('B');
profileEnd('A');
profileEnd('B');
```  

> [!NOTE]
> 複数の CPU プロファイルを同時に操作することができます。また、複数の CPU プロファイルを作成順序で閉じる必要はありません。  

## profileEnd  

```console
profileEnd([name])
```  

JavaScript CPU のプロファイリングセッションを完了し、 **メモリ** パネルに結果を表示します。  [Profile ()](#profile)メソッドを実行している必要があります。  <!--See also [Speed Up JavaScript Runtime][DevToolsRenderingToolsJSRuntime].  -->  

1.  [Profile ()](#profile)メソッドを実行してプロファイリングを開始します。  
1.  メソッドを実行して `profileEnd()` プロファイリングを停止し、 **メモリ** パネルに結果を表示します。  
    
    ```console
    profileEnd("My profile")
    ```  

プロファイルは入れ子にすることもできます。  次のコードサンプルと図は、順序に関係なく同じ結果になります。  

```console
profile('A');
profile('B');
profileEnd('A');
profileEnd('B');
```  

結果は、 **メモリ** パネルにヒープスナップショットとして表示されます。  

:::image type="complex" source="../media/console-memory-multiple-cpu-profiles.msft.png" alt-text="グループ化されたプロファイル" lightbox="../media/console-memory-multiple-cpu-profiles.msft.png":::
   図 23: グループ化されたプロファイル  
:::image-end:::  

> [!NOTE]
> 複数の CPU プロファイルを同時に操作することができます。また、複数の CPU プロファイルを作成順序で閉じる必要はありません。  

## queryObjects  

```console
queryObjects(Constructor)
```  

指定したコンストラクターで作成されたオブジェクトの配列を返します。  のスコープ `queryObjects()` は、現在選択されているランタイムコンテキスト (本体) です。

:::row:::
   :::column span="1":::
      ```console
      queryObjects(promise)
      ```  
      
      All を返し `Promises` ます。  
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
      
      を使用してインスタンス化されたすべてのオブジェクトを返し `new functionName()` ます。  
   :::column-end:::
:::row-end:::  

---  

## '95'5c  

```console
table(data[, columns])
```  

列見出しを省略できるデータオブジェクトに基づいて、テーブルの書式設定でオブジェクトデータをログに記録します。  次のコードサンプルと図では、コンソールの表を使って名前のリストが表示されています。  

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

:::image type="complex" source="../media/console-table-display.msft.png" alt-text="Table () メソッドの結果" lightbox="../media/console-table-display.msft.png":::
   図 24: メソッドの結果 `table()`  
:::image-end:::  

## undebug  

```console
undebug(method)
```  

メソッドが呼び出されたときにデバッガーが呼び出されなくなるように、指定されたメソッドのデバッグを停止します。  

```console
undebug(getData);
```  

## 未停止  

```console
unmonitor(method)
```  

指定したメソッドの監視を停止します。  このメソッドは、 [monitor ()](#monitor) メソッドと連携して使用されます。  

```console
unmonitor(getData);
```  

## イベントを監視しない  

```console
unmonitorEvents(object[, events])
```  

指定したオブジェクトおよびイベントの監視イベントを停止します。  たとえば、次の例では、window オブジェクトのイベント監視がすべて停止しています。  

```console
unmonitorEvents(window);
```  

オブジェクトの特定のイベントの監視を選択的に停止することもできます。  たとえば、次のコードでは、現在選択されている要素のすべての `mouse` イベントを監視し、イベントの監視を停止します (多くの場合、 `mousemove` 本体の出力のノイズを軽減します)。  

```console
monitorEvents($0, "mouse");
unmonitorEvents($0, "mousemove");
```  

## values  

```console
values(object)
```  

指定したオブジェクトに属するすべてのプロパティの値を含む配列を返します。  

```console
values(object);
```  

<!-- links -->  

[DevToolsConsoleApi]: /microsoft-edge/devtools-guide-chromium/console/api "本体の API リファレンス"  
[DevToolsConsoleApiConsoleDirObject]: /microsoft-edge/devtools-guide-chromium/console/api#dir "dir-本体の API リファレンス"  
[DevToolsJavascriptBreakpoints]: /microsoft-edge/devtools-guide-chromium/javascript/breakpoints "Microsoft Edge DevTools のブレークポイントでコードを一時停止する方法"  
[DevToolsRenderingToolsJSRuntime]: /microsoft-edge/devtools-guide-chromium/rendering-tools/js-runtime "JavaScript の実行時間を短縮する"  

[MDNConsoleDir]: https://developer.mozilla.org/docs/Web/API/Console/dir "Console. dir () |MDN"  
[MDNConsoleDirxml]: https://developer.mozilla.org/docs/Web/API/Console/dirxml "Console. dirxml () |MDN"  
[MDNDocumentQuerySelector]: https://developer.mozilla.org/docs/Web/API/Document/querySelector "ドキュメントの querySelector () |MDN"  
[MDNDocumentQuerySelectorAll]: https://developer.mozilla.org/docs/Web/API/Document/querySelectorAll "QuerySelectorAll () |MDN"  

[MonorailIssue1050237]: https://bugs.chromium.org/p/chromium/issues/detail?id=1050237 "問題 1050237: debug (関数) が機能しません |Monorail アウト"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/console/utilities) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
