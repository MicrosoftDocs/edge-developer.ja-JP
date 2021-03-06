---
description: Microsoft Edge DevTools でコードを一時停止できるすべての方法について説明します。
title: Microsoft Edge DevTools でブレークポイントを使用してコードを一時停止する方法
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 84077503d6c786244fc2ca4d54c349ae9f6d20d8
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398596"
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

# <a name="how-to-pause-your-code-with-breakpoints-in-microsoft-edge-devtools"></a>Microsoft Edge DevTools でブレークポイントを使用してコードを一時停止する方法  

ブレークポイントを使用して JavaScript コードを一時停止します。  このガイドでは、DevTools で使用できるブレークポイントの種類と、使用する時間と各種類の設定方法について説明します。  デバッグ プロセスの実践的なチュートリアルについては [、「Microsoft Edge DevTools][DevtoolsJavascriptIndex]での JavaScript のデバッグの開始」に移動します。  

## <a name="overview-of-when-to-use-each-breakpoint-type"></a>各ブレークポイントの種類を使用する場合の概要  

最もよく知られているブレークポイントの種類は、コード行です。  ただし、コード行のブレークポイントは、特に場所を正確に知らない場合や、大きなコードベースを使用している場合に設定が非効率的な場合があります。  他の種類のブレークポイントを使用する方法と時期を知ることにより、デバッグの時間を節約できます。  

| ブレークポイントの種類 | 一時停止する場合は、これを使用します。  |  
|:--- |:--- |  
| [コード行](#line-of-code-breakpoints) | コードの正確な領域。  |  
| [条件付きコード行](#conditional-line-of-code-breakpoints) | コードの正確な領域で、他の条件が true の場合のみ。  |  
| [DOM](#dom-change-breakpoints) | 特定の DOM ノードまたは子ノードを変更または削除するコード。  |  
| [XHR](#xhrfetch-breakpoints) | XHR URL に文字列パターンが含まれている場合。  |  
| [イベント リスナー](#event-listener-breakpoints) | イベントの実行後に実行されるコード (実行など `click` )。  |  
| [例外](#exception-breakpoints) | キャッチまたはキャッチされていない例外をスローするコード行で。  |  
| [機能](#function-breakpoints) | 特定のコマンド、関数、またはメソッドが実行されるたびに実行されます。  |  

## <a name="line-of-code-breakpoints"></a>コード行ブレークポイント  

調査する必要があるコードの正確な領域を知っている場合は、コード行ブレークポイントを使用します。  DevTools は、このコード行を実行する前に常に一時停止します。  

DevTools でコード行ブレークポイントを設定するには、次のコマンドを実行します。  

1.  [ソース] **ツールを選択** します。  
1.  ブレークするコード行を含むファイルを開きます。  
1.  コード行を移動します。  
1.  コード行の左側に行番号列があります。  選択します。  行番号列の横に赤いアイコンが表示されます。  
    
    :::image type="complex" source="../media/javascript-sources-page-js-breakpoint-30.msft.png" alt-text="コード行ブレークポイント" lightbox="../media/javascript-sources-page-js-breakpoint-30.msft.png":::
       コード行ブレークポイント  
    :::image-end:::  
    
### <a name="line-of-code-breakpoints-in-your-code"></a>コード内のコード行ブレークポイント  

コードから `debugger` メソッドを実行して、その行を一時停止します。  これは、DevTools [](#line-of-code-breakpoints)UI ではなく、コードでブレークポイントが設定されている点を除き、コード行ブレークポイントと同じです。  

```javascript
console.log('a');
console.log('b');
debugger;
console.log('c');
```  

### <a name="conditional-line-of-code-breakpoints"></a>条件付きコード行ブレークポイント  

調査する必要があるコードの正確な領域がわかっているが、他の条件が true の場合にのみ一時停止する場合は、条件付きコード行ブレークポイントを使用します。  

条件付きコード行ブレークポイントを設定するには、次のコマンドを実行します。  

1.  [ソース] **ツールを選択** します。  
1.  ブレークするコード行を含むファイルを開きます。  
1.  コード行を移動します。  
1.  コード行の左側に行番号列があります。  行番号にカーソルを合わせると、コンテキスト メニュー \(右クリック\) が開きます。  
1.  [条件付 **きブレークポイントの追加] を選択します**。  コード行の下にダイアログが表示されます。  
1.  ダイアログに条件を入力します。  
1.  ブレークポイント `Enter` をアクティブ化する場合に選択します。  行番号列の横にあるアイコン。  
    
    :::image type="complex" source="../media/javascript-sources-page-js-conditional-breakpoint.msft.png" alt-text="条件付きコード行ブレークポイント" lightbox="../media/javascript-sources-page-js-conditional-breakpoint.msft.png":::
       条件付きコード行ブレークポイント  
    :::image-end:::  
    
### <a name="manage-line-of-code-breakpoints"></a>コード行ブレークポイントの管理  

[ブレークポイント **] ウィンドウを使用** して、1 つの場所からコード行ブレークポイントを無効または削除します。  

:::image type="complex" source="../media/javascript-sources-page-js-breakpoints-16-33.msft.png" alt-text="[ブレークポイント] パネル" lightbox="../media/javascript-sources-page-js-breakpoints-16-33.msft.png":::
   [ **ブレークポイント]** パネル  
:::image-end:::  

*   エントリの横にあるチェック ボックスをオンにして、そのブレークポイントを無効にします。  
*   エントリにカーソルを合わせると、コンテキスト メニュー \(右クリック\) を開き、そのブレークポイントを削除します。  
*   [ブレークポイント] ウィンドウの任意の **場所** にマウス ポインターを移動し、コンテキスト メニュー \(右クリック\) を開いてすべてのブレークポイントを非アクティブ化するか、すべてのブレークポイントを無効にするか、すべてのブレークポイントを削除します。  すべてのブレークポイントを無効にした場合は、各ブレークポイントのチェックを外すのと同じです。  すべてのブレークポイントを非アクティブ化すると、DevTools は、すべてのコード行ブレークポイントを無視するように指示しますが、有効な状態を維持して、各ブレークポイントを再アクティブ化する場合と同じ状態になります。  
    
    :::image type="complex" source="../media/javascript-sources-page-js-breakpoints-deactivate-breakpoints.msft.png" alt-text="[ブレークポイント] ウィンドウで非アクティブ化されたブレークポイント" lightbox="../media/javascript-sources-page-js-breakpoints-deactivate-breakpoints.msft.png":::
       [ブレークポイント] ウィンドウで **非アクティブ化された** ブレークポイント  
    :::image-end:::  
    
## <a name="dom-change-breakpoints"></a>DOM の変更ブレークポイント  

DOM ノードまたは子を変更するコードを一時停止する場合は、DOM 変更ブレークポイントを使用します。  

DOM 変更ブレークポイントを設定するには、次の操作を行います。  

1.  [要素] **ツールを選択** します。  
1.  ブレークポイントを設定する要素を移動します。  
1.  要素にカーソルを合わせると、コンテキスト メニュー \(右クリック\) が開きます。  
1.  [ブレーク]**をポイントし**、[サブツリーの変更 **] 、[****属性の変更]**、または [ノードの削除]**を選択します**。  
    
    :::image type="complex" source="../media/javascript-elements-break-on-subtree-modifications.msft.png" alt-text="DOM 変更ブレークポイントを作成するためのコンテキスト メニュー" lightbox="../media/javascript-elements-break-on-subtree-modifications.msft.png":::
       DOM 変更ブレークポイントを作成するためのコンテキスト メニュー  
    :::image-end:::  
    
### <a name="types-of-dom-change-breakpoints"></a>DOM 変更ブレークポイントの種類  

*   **サブツリーの変更**。  現在選択されているノードの子が削除または追加された場合、または子の内容が変更された場合にトリガーされます。  子ノード属性の変更、または現在選択されているノードに対する変更ではトリガーされません。  
*   **属性の変更**: 現在選択されているノードで属性が追加または削除された場合、または属性値が変更された場合にトリガーされます。  
*   **ノードの削除**: 現在選択されているノードが削除されるとトリガーされます。  
    
## <a name="xhrfetch-breakpoints"></a>XHR/Fetch ブレークポイント  

XHR の要求 URL に指定された文字列が含まれている場合は、XHR ブレークポイントを使用します。  DevTools は、XHR がメソッドを実行するコード行で一時停止 `send()` します。  

> [!NOTE]
> この機能は、フェッチ [API 要求でも][MDNFetchApi] 機能します。  

これが役に立つ例の 1 つは、Web ページが正しくない URL を要求し、要求が正しくない原因となっている AJAX または Fetch ソース コードをすばやく見つける場合です。  

XHR ブレークポイントを設定するには、次のコマンドを実行します。  

1.  [ソース] **ツールを選択** します。  
1.  **[XHR ブレークポイント] パネルを展開**します。  
1.  [ブレークポイント **の追加] を選択します**。  
1.  折りたたむ文字列を入力します。  この文字列が XHR 要求 URL の任意の場所に存在する場合、DevTools は一時停止します。  
1.  選択 `Enter` して確認します。  
    
    :::image type="complex" source="../media/javascript-sources-page-js-xhr-fetch-breakpoints-org.msft.png" alt-text="XHR ブレークポイントの作成" lightbox="../media/javascript-sources-page-js-xhr-fetch-breakpoints-org.msft.png":::
       XHR ブレークポイントの作成  
    :::image-end:::  
    
## <a name="event-listener-breakpoints"></a>イベント リスナーのブレークポイント  

イベントが発生した後に実行されるイベント リスナー コードで一時停止する場合は、イベント リスナー ブレークポイントを使用します。  すべてのマウス イベントなど、イベントのカテゴリなどの特定のイベント `click` を選択できます。  

1.  [ソース] **ツールを選択** します。  
1.  [イベント リスナー **ブレークポイント] パネルを展開** します。  DevTools には、Animation などのイベント カテゴリの一覧が **表示されます**。  
1.  これらのカテゴリのいずれかを確認して、そのカテゴリのイベントが発生するたびに一時停止するか、カテゴリを展開して特定のイベントを確認します。  
    
    :::image type="complex" source="../media/javascript-sources-page-js-event-listener-breakpoints-device-deviceorientation.msft.png" alt-text="イベント リスナーブレークポイントの作成" lightbox="../media/javascript-sources-page-js-event-listener-breakpoints-device-deviceorientation.msft.png":::
       イベント リスナーブレークポイントの作成  
    :::image-end:::  
    
## <a name="exception-breakpoints"></a>例外ブレークポイント  

キャッチまたはキャッチされていない例外をスローするコード行で一時停止する場合は、例外ブレークポイントを使用します。  

1.  [ソース] **ツールを選択** します。  
1.  [ **例外時に一時停止** する] \( ![ [例外の一時停止 ][ImagePauseOnExceptionsIcon] ] \) を選択します。  有効にすると、アイコンが青色に変わります。  
    
    :::image type="complex" source="../media/javascript-sources-page-js-pause-on-exceptions.msft.png" alt-text="[例外時に一時停止] ボタン" lightbox="../media/javascript-sources-page-js-pause-on-exceptions.msft.png":::
       [ **例外時に一時停止]** ボタン  
    :::image-end:::  
    
1.  **省略可能です**。  キャッチされていない **例外に** 加えて、キャッチされた例外でも一時停止する場合は、[キャッチ例外の一時停止] チェック ボックスをオンにします。  
    
    :::image type="complex" source="../media/javascript-sources-page-js-paused-on-exception.msft.png" alt-text="キャッチされない例外で一時停止" lightbox="../media/javascript-sources-page-js-paused-on-exception.msft.png":::
       キャッチされない例外で一時停止  
    :::image-end:::  
    
## <a name="function-breakpoints"></a>関数のブレークポイント  

特定の関数が実行されるたびに一時停止する場合は、デバッグするコマンド、関数、またはメソッドがあるメソッド `debug(method)` `method` を実行します。  コード (ステートメント `debug()` など) に挿入するか `console.log()` 、DevTools コンソールからメソッドを実行できます。  `debug()` は、関数の最初 [の行](#line-of-code-breakpoints) にコード行ブレークポイントを設定するのと同じです。  

```javascript
function sum(a, b) {
    let result = a + b; // DevTools pauses on this line.
    return result;
}
debug(sum); // Pass the function object, not a string.
sum();
```  

### <a name="make-sure-the-target-function-is-in-scope"></a>ターゲット関数がスコープ内にあるか確認する  

DevTools は、デバッグする関数がスコープ内にない `ReferenceError` 場合に a をスローします。  

```javascript
(function () {
    function hey() {
        console.log('hey');
    }
    function yo() {
        console.log('yo');
    }
    debug(yo); // This works.
    yo();
})();
debug(hey); // This does not work.  hey() is out of scope.
```  

DevTools コンソールからメソッドを実行している場合は、ターゲット関数がスコープ内にあるのを確認するのが `debug()` 難しい場合があります。  1 つの戦略を次に示します。  

1.  関数が [スコープ内にある場所に](#line-of-code-breakpoints) コード行ブレークポイントを設定します。
1.  ブレークポイントをトリガーします。  
1.  コードがコード行ブレークポイントで一時停止されている間 `debug()` 、DevTools コンソールでメソッドを実行します。  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImagePauseOnExceptionsIcon]: ../media/pause-on-exceptions-icon.msft.png  

<!-- links -->  

[DevtoolsJavascriptIndex]: index.md "Microsoft Edge DevTools の JavaScript のデバッグの|Microsoft Docs"  

[MDNFetchApi]: https://developer.mozilla.org/docs/Web/API/Fetch_API "FETCH API |MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/breakpoints) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
