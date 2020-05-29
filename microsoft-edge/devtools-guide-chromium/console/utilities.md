---
title: コンソールユーティリティ API リファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 28b40f3f79928725d3d49418e01cf02247224370
ms.sourcegitcommit: 5cdc1626d5581b79c0f2ac4ea62e7f1974ebfa57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "10601797"
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

およびその他のメソッドを探してい `console.log()` `console.error()` `console.*` ますか?  「[コンソール API リファレンス][DevToolsConsoleApi]」をご覧ください。  

## 最近評価された式  

```console
$_
```  

直近に評価された式の値を返します。  

[図 1](#figure-1)では、単純な式 \ ( `2 + 2` \) が評価されます。  `$_`プロパティが評価され、同じ値が含まれます。  

> ##### 図 1  
> `$_` は、最後に評価された式です。  
> ![$ _ は、最近評価された式です。][ImageRecentExpression]  

[図 2](#figure-2)では、最初に評価式に名前の配列が含まれています。  評価して `$_.length` 配列の長さを確認します。変更された値は、 `$_` 最新の評価済みの式になり `4` ます。  

> ##### 図 2  
> `$_` 新しいコマンドの評価時の変更点  
> ![新しいコマンドが評価されたときの $ _ 変更][ImageChangedRecentExpression]  

## 最近選んだ要素または JavaScript オブジェクト  

```console
$0
```  

最後に選択された要素または JavaScript オブジェクトを返します。  `$1` 最後に選択された2番目の値を返します。  、、、、 `$0` `$1` およびコマンドは、 `$2` `$3` `$4` **要素**パネル内で検査された最後の5つの DOM 要素、または**メモリ**パネルで選択された最後の5つの JavaScript ヒープオブジェクトへの履歴参照として機能します。  

```console
$1
```  

```console
$2
```  

```console
$3
```  

```console
$4
```  

[図 3](#figure-3)では、[ `img` **要素**] パネルで要素が選択されています。  **本体**のドロアーで、 `$0` 評価が完了し、同じ要素が表示されます。  

> ##### 図 3  
> 、 `$0`  
> ![$0][ImageElement0]  

[図 4](#figure-4)では、同じページで選択された別の要素が画像に表示されています。  現在選択されている `$0` 要素を参照して `$1` いますが、以前に選択されていた要素を返します。  

> ##### 図 4  
> 、 `$1`  
> ![$1][ImageElement1]  

## クエリセレクター  

```console
$(selector, [startNode])
```  

指定された CSS セレクターで最初の DOM 要素への参照を返します。  このメソッドは、[ドキュメントの querySelector ()][MDNDocumentQuerySelector]メソッドのエイリアスです。  

[図 5](#figure-5)では、文書内の最初の要素への参照 `<img>` が返されます。  

> ##### 図 5  
> 、 `$('img')`  
> ![$ (' Img ')][ImageElementImg]  

返された結果を右クリックし、[**要素パネルで**表示] を選択して DOM で見つけます。または、[表示] に**スクロール**して、ページに表示します。  

[図 6](#figure-6)では、現在選択されている要素への参照が返され、src プロパティが表示されます。  

> ##### 図 6  
> 、 `$('img').src`  
> ![$ (' Img ') src][ImageElementImgSource]  

このメソッドは、要素を検索する "element" またはノードを指定する2番目のパラメーター startNode もサポートしています。  このパラメーターの既定値は `document` です。  

[図 7](#figure-7)では、最初 `img` の要素がであり、 `title--image` 正しく表示され `src` ます。  

> ##### 図 7  
> $ (' Img '、ドキュメントの querySelector (' タイトル--image ')) src  
> ![$ (' Img '、ドキュメントの querySelector (' タイトル--image ')) src][ImageElementImgNodeSource]  

> [!NOTE]
> 使用する jQuery などのライブラリを使用している場合 `$` 、この機能は上書きされ、 `$` そのライブラリの実装に対応します。  

## すべてのクエリセレクター  

```console
$$(selector, [startNode])
```  

指定された CSS セレクターに一致する要素の配列を返します。  このメソッドは、 [querySelectorAll ()][MDNDocumentQuerySelectorAll]メソッドを呼び出すことと同じです。  

[図 8](#figure-8)では、を使用して、 `$$()` 現在のドキュメント内のすべての要素の配列を作成 `<img>` し、各要素のプロパティの値を表示し `src` ます。  

```console
var images = $$('img');
for (each in images) {
    console.log(images[each].src);
}
```  

> ##### 図 8  
> `$$()`ドキュメント内のすべての画像を選択してソースを表示するために使用する  
> ![$ $ () を使用して、ドキュメント内のすべての画像を選択し、ソースを表示する][ImageArrayElementImgSource]  

このメソッドは、要素を検索する要素またはノードを指定する2番目の parameter startNode もサポートしています。  このパラメーターの既定値は `document` です。  

[図 9](#figure-9)では、変更されたバージョンの[図 8](#figure-8)を使用して、 `$$()` `<img>` 選択したノードの後に現在の文書内に出現するすべての要素の配列を作成します。  

```console
var images = $$('img', document.querySelector(`title--image`));
for (each in images) {
   console.log(images[each].src);
}
```  

> ##### 図 9  
> `$$()`文書内の指定された要素の後に表示されるすべての画像を選択してソースを表示するために使用する `<div>`  
> ![$ $ () を使用して、文書内の指定された <div> 要素の後に表示されるすべての画像を選択して、ソースを表示する][ImageArrayElementImgNodeSource]  

> [!NOTE]
> コンソールを押して、 `Shift` + `Enter` スクリプトを実行せずに、新しい行を開始します。  

## X  

```console
$x(path, [startNode])
```  

指定された XPath 式と一致する DOM 要素の配列を返します。  

[図 10](#figure-10)では、ページ上のすべての `<p>` 要素が返されます。  

```console
$x("//p")
```  

> ##### 図 10  
> XPath セレクターを使用する  
> ![XPath セレクターを使用する][ImageArrayXpath]  

[図 11](#figure-11)で `<p>` は、要素を含むすべての要素 `<a>` が返されます。  

```console
$x("//p[a]")
```  

> ##### 図 11  
> より複雑な XPath セレクターを使用する  
> ![より複雑な XPath セレクターを使用する][ImageArrayXpathChild]  

他のセレクターコマンドと同様に、 `$x(path)` `startNode` 要素を検索する要素またはノードを指定する、オプションの2番目のパラメーターを持ちます。  

> ##### 図 12  
> XPath セレクターの使い方 `startNode`  
> ![StartNode で XPath セレクターを使用する][ImageArrayXpathNode]  

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
> [Chromium 問題 #1050237][MonorailIssue1050237]は、関数のバグを追跡 `debug()` しています。  この問題が発生した場合は、代わりに[ブレークポイントを使用][DevtoolsJavascriptBreakpoints]してみてください。  

指定したメソッドを要求すると、デバッガーが呼び出され、**ソース**パネルのメソッド内で中断されます。これにより、コードをステップ実行してデバッグすることができます。  

```console
debug("debug");
```  

> ##### 図 13  
> メソッド内での区切り `debug()`  
> ![Debug () を使用したメソッド内の中断][ImageDebugMethod]  

`undebug(method)`メソッドの中断を停止するには、または UI を使ってすべてのブレークポイントを無効にする場合に使用します。  

ブレークポイントの詳細については、「[ブレークポイントでコードを一時停止][DevToolsJavascriptBreakpoints]する」を参照してください。  

## dir  

```console
dir(object)
```  

指定したオブジェクトのすべてのプロパティのオブジェクトスタイルの一覧を表示します。  このメソッドは、 [console. dir ()][MDNConsoleDir]メソッドのエイリアスです。  

本体でを評価して、 `document.head` タグとタグの間に HTML を表示し `<head>` `</head>` ます。  [図 14](#figure-14)では、コンソールで使用した後にオブジェクトスタイルの一覧が表示され `console.dir()` ます。  

```console
document.head;
dir(document.head);
```  

> ##### 図 14  
> ログ `document.head` 記録 `dir()` メソッド  
> ![Dir () メソッドを使ってドキュメントをログに記録します。][ImageLogObject]  

詳細については、 [`console.dir()`][DevToolsConsoleApiConsoleDirObject] 本体 API のエントリを参照してください。  

## dirxml  

```console
dirxml(object)
```  

[**要素**] タブに表示されるように、指定したオブジェクトの XML 表現を印刷します。 このメソッドは、console の[dirxml ()][MDNConsoleDirxml]メソッドと同じです。  

## 検査  

```console
inspect(object/method)
```  

適切なパネル (DOM 要素の場合は**要素**パネル、JavaScript ヒープオブジェクトの場合は**メモリ**パネル) で、指定された要素またはオブジェクトを開き、選択します。  

[図 15](#figure-15)では、[ `document.body` **要素**] パネルが開きます。  

```console
inspect(document.body);
```  

> ##### 図 15  
> 要素の検査 `inspect()`  
> ![検査 () での要素の検査][ImageInspectElement]  

検査するメソッドを渡すとき、メソッドは**ソース**パネルでドキュメントを開き、調べることができます。  

## getEventListeners  

```console
getEventListeners(object)
```  

指定したオブジェクトに登録されているイベントリスナーを返します。  戻り値は、登録されている各イベントの種類 (やなど) の配列を含むオブジェクトです `click` `keydown` 。  各配列のメンバーは、各型に登録されているリスナーを記述するオブジェクトです。  [図 16](#figure-16)では、ドキュメントオブジェクトに登録されているすべてのイベントリスナーが一覧表示されます。  

```console
getEventListeners(document);
```  

> ##### 図 16  
> を使用した出力 `getEventListeners(document)`  
> ![GetEventListeners を使った出力 (ドキュメント)][ImageGetListeners]  

指定したオブジェクトに複数のリスナーが登録されている場合、この配列には各リスナーのメンバーが含まれます。  [図 16](#figure-16)では、イベントのドキュメント要素に2つのイベントリスナーが登録されてい `click` ます。  

> ##### 図 17  
> 複数のリスナー  
> ![複数のリスナー][ImageMultipleListeners]  

次の各オブジェクトをさらに拡張して、プロパティを確認できます。  

> ##### 図18  
> リスナーオブジェクトの展開ビュー  
> ![リスナーオブジェクトの展開ビュー][ImageListenersExpanded]  

## キー  

```console
keys(object)
```  

指定したオブジェクトに属するプロパティの名前を含む配列を返します。  同じプロパティの関連する値を取得するには、を使用 `values()` します。  

たとえば、アプリケーションが次のオブジェクトを定義したとします。  

```console
var player1 = { "name":  "Ted", "level": 42 }
```  

[図 19](#figure-19)では、 `player1` 入力と本体の入力前のグローバル名前空間 \ (簡潔さ) で結果が定義されていることを前提としてい `keys(player1)` `values(player1)` ます。  

```console
keys(player1)
```  

```console
values(player1)
```  

> ##### 図19  
> `keys()`And `values()` コマンド  
> ![Keys () コマンドと values () コマンド][ImageConsoleKeysValues]  

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

> ##### 図20  
> `monitor()`メソッド  
> ![Monitor () メソッド][ImageConsoleMonitorSum]  

`unmonitor(method)`監視を停止するために使用します。  

## monitorEvents  

```console
monitorEvents(object[, events])
```  

指定したイベントのいずれかが指定したオブジェクトで発生した場合、イベントオブジェクトは本体に記録されます。  監視する1つのイベント、一連のイベント、または定義済みのイベントコレクションにマップされる汎用イベント型のいずれかを指定できます。  [図 21](#figure-21)を参照してください。  

次のモニターは、window オブジェクトのすべてのサイズ変更イベントを監視します。  

```console
monitorEvents(window, "resize");
```  

> ##### 図21  
> モニタリングウィンドウのサイズ変更イベント  
> ![モニタリングウィンドウのサイズ変更イベント][ImageMonitorResize]  

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

[図 22](#figure-22)では、 `key` 入力テキストフィールドのイベントに対応するイベントの種類が、[ `key` **要素**] パネルで現在選択されています。  

```console
monitorEvents($0, "key");
```  

[図 22](#figure-22)では、テキストフィールドに文字を入力した後のサンプル出力が表示されています。  

> ##### 図22  
> 主要イベントの監視  
> ![主要イベントの監視][ImageMonitorKey]  

## profile  

```console
profile([name])
```  

省略可能な名前で JavaScript CPU プロファイリングセッションを開始します。  Profile [end ()](#profileend)メソッドは、プロファイルを完了し、**メモリ**パネルに結果を表示します。  <!--See also [Speed Up JavaScript Runtime][DevToolsRenderingToolsJSRuntime].  -->  

1.  メソッドを実行して `profile()` プロファイリングを開始します。  
    
    ```console
    profile("My profile")
    ```  
    
1.  プロファイルを停止して、**メモリ**パネルに結果を表示するには、 [profileend ()](#profileend)メソッドを実行します。  

プロファイルは入れ子にすることもできます。  [図 23](#figure-23)では、結果は順序に関係なく同じです。  

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

JavaScript CPU のプロファイリングセッションを完了し、**メモリ**パネルに結果を表示します。  [Profile ()](#profile)メソッドを実行している必要があります。  <!--See also [Speed Up JavaScript Runtime][DevToolsRenderingToolsJSRuntime].  -->  

1.  [Profile ()](#profile)メソッドを実行してプロファイリングを開始します。  
1.  メソッドを実行して `profileEnd()` プロファイリングを停止し、**メモリ**パネルに結果を表示します。  
    
    ```console
    profileEnd("My profile")
    ```  

プロファイルは入れ子にすることもできます。  [図 23](#figure-23)では、結果は順序に関係なく同じです。  

```console
profile('A');
profile('B');
profileEnd('A');
profileEnd('B');
```  

結果は、**メモリ**パネルにヒープスナップショットとして表示されます。  

> ##### 図23  
> グループ化されたプロファイル  
> ![グループ化されたプロファイル][ImageGroupedProfiles]  

> [!NOTE]
> 複数の CPU プロファイルを同時に操作することができます。また、複数の CPU プロファイルを作成順序で閉じる必要はありません。  

## '95'5c  

```console
table(data[, columns])
```  

列見出しを省略できるデータオブジェクトに基づいて、テーブルの書式設定でオブジェクトデータをログに記録します。  [図 24](#figure-24)では、コンソールの表を使って名前のリストが表示されています。  

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

> ##### 図24  
> `table()`メソッド  
> ![Table () メソッド][ImageConsoleTable]  

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

指定したメソッドの監視を停止します。  これは、 [monitor ()](#monitor)メソッドと連携して使用されます。  

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

<!--   -->  



<!-- image links -->  

[ImageRecentExpression]: /microsoft-edge/devtools-guide-chromium/media/console-arithmatic.msft.png "図 1: $ _ は、最近評価された式です。"  
[ImageChangedRecentExpression]: /microsoft-edge/devtools-guide-chromium/media/console-array-length.msft.png "図 2: 新しいコマンドが評価されたときの $ _ の変更"  
[ImageElement0]: /microsoft-edge/devtools-guide-chromium/media/console-image-highlighted-$0.msft.png "図 3: $0"  
[ImageElement1]: /microsoft-edge/devtools-guide-chromium/media/console-image-highlighted-$1.msft.png "図 4: $1"  
[ImageElementImg]: /microsoft-edge/devtools-guide-chromium/media/console-element-selector-image.msft.png "図 5: $ (' img ')"  
[ImageElementImgSource]: /microsoft-edge/devtools-guide-chromium/media/console-element-selector-image-source.msft.png "図 6: $ (' img ') src"  
[ImageElementImgNodeSource]: /microsoft-edge/devtools-guide-chromium/media/console-element-selector-image-filter-source.msft.png "図 7: $ (' img '、ドキュメントの querySelector (' title--image '))。 src"  
[ImageArrayElementImgSource]: /microsoft-edge/devtools-guide-chromium/media/console-element-selector-image-all.msft.png "図 8: $ $ () を使用してドキュメント内のすべての画像を選択し、ソースを表示する"  
[ImageArrayElementImgNodeSource]: /microsoft-edge/devtools-guide-chromium/media/console-element-selector-image-filter-all.msft.png "図 9: $ $ () を使って、文書内の指定された <div> 要素の後に表示されるすべての画像を選択して、ソースを表示する"  
[ImageArrayXpath]: /microsoft-edge/devtools-guide-chromium/media/console-array-xpath.msft.png "図 10: XPath セレクターを使用する"  
[ImageArrayXpathChild]: /microsoft-edge/devtools-guide-chromium/media/console-array-xpath-sub-element.msft.png "図 11: より複雑な XPath セレクターを使用する"  
[ImageArrayXpathNode]: /microsoft-edge/devtools-guide-chromium/media/console-array-xpath-startnode.msft.png "図 12: startNode で XPath セレクターを使用する"  
[ImageDebugMethod]: /microsoft-edge/devtools-guide-chromium/media/console-debug-text.msft.png "図 13: debug () を使用したメソッド内の中断"  
[ImageLogObject]: /microsoft-edge/devtools-guide-chromium/media/console-dir-document-head-expanded.msft.png "図 14: dir () メソッドを使った文書の記録"  
[ImageInspectElement]: /microsoft-edge/devtools-guide-chromium/media/console-inspect-document-body.msft.png "図 15: 検査 () を使って要素を検査する"  
[ImageGetListeners]: /microsoft-edge/devtools-guide-chromium/media/console-elements-event-listeners-console-get-event-listeners-document.msft.png "図 16: getEventListeners を使った出力 (ドキュメント)"  
[ImageMultipleListeners]: /microsoft-edge/devtools-guide-chromium/media/console-elements-event-listeners-console-get-event-listeners-document-expanded-1.msft.png "図 17: 複数のリスナー"  
[ImageListenersExpanded]: /microsoft-edge/devtools-guide-chromium/media/console-elements-event-listeners-console-get-event-listeners-document-2.msft.png "図 18: リスナーオブジェクトの展開ビュー"  
[ImageConsoleKeysValues]: /microsoft-edge/devtools-guide-chromium/media/console-keys-values.msft.png "図 19: keys () および values () コマンド"  
[ImageConsoleMonitorSum]: /microsoft-edge/devtools-guide-chromium/media/console-function-monitor-sum.msft.png "図 20: monitor () メソッド"  
[ImageMonitorResize]: /microsoft-edge/devtools-guide-chromium/media/console-monitor-events-resize-window.msft.png "図 21: ウィンドウのサイズ変更イベントの監視"  
[ImageMonitorKey]: /microsoft-edge/devtools-guide-chromium/media/console-monitor-events-type-t-y.msft.png "図 22: 主要イベントの監視"  
[ImageGroupedProfiles]: /microsoft-edge/devtools-guide-chromium/media/console-memory-multiple-cpu-profiles.msft.png "図 23: グループ化されたプロファイル"  
[ImageConsoleTable]: /microsoft-edge/devtools-guide-chromium/media/console-table-display.msft.png "図 24: table () メソッド"  

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
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/console/utilities)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
