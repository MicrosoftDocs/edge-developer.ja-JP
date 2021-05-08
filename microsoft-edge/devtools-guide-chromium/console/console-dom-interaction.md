---
description: コンソール ツールを使用してブラウザーで現在の Web ページを操作する方法の概要
title: コンソールを使用して DOM を操作する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/13/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 80b0e4368b1c8feaf28a58ac2e3bd9c1ea2f1f92
ms.sourcegitcommit: 2e516a92272e38d8073603f860ae49f944718670
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "11483540"
---
# <a name="use-the-console-to-interact-with-the-dom"></a>コンソールを使用して DOM を操作する

コンソール **ツール** は、情報をログに [記録][DevtoolsConsoleConsoleLog] したり、任意の JavaScript を [実行したりするだけのツールではない][DevtoolsConsoleConsoleJavascript]。  また、ブラウザーで Web ページを操作する場合にも便利です。  スクリプト環境バージョンの Inspect ツールと **考** えます。  

## <a name="read-from-the-dom"></a>DOM から読み取る

Web ページのヘッダーを参照するには、次のアクションを実行します。  

1.  コンソールを **開きます**。
    *   `Control` + `Shift` + `J` \(Windows Linux\) または `Command` + `Option` + `J` \(macOS\) を選択します。  
1.  コンソールに次のコード スニペットを入力またはコピーして貼り **付けます**。  
    
    ```javascript
    document.querySelector('header')
    ```  
    
:::image type="complex" source="../media/console-dom-get-reference.msft.png" alt-text="コンソールでヘッダーへの参照を取得するには、document.querySelector を使用します。" lightbox="../media/console-dom-get-reference.msft.png":::
    コンソールでヘッダーへの参照を取得するには、 `document.querySelector`  
:::image-end:::  

HTML 結果の `Shift` + `Tab` 上でマウス カーソルを選択または移動すると、DevTools によってヘッダーが強調表示されます。  

:::image type="complex" source="../media/console-dom-highlight-element.msft.png" alt-text="DevTools は、コンソールで選択したセクションを強調表示します。" lightbox="../media/console-dom-highlight-element.msft.png":::
    DevTools は、コンソールで選択したセクションを強調表示 **します。**  
:::image-end:::  

## <a name="manipulate-the-dom"></a>DOM を操作する

Web ページも操作できます。  たとえば、次をコピーして貼り付けるか、コンソールに**** 入力すると、ヘッダーの周囲に緑色の枠線が表示されます。

```javascript
document.querySelector('header').style.border = '2em solid green'
```  

:::image type="complex" source="../media/console-dom-add-border.msft.png" alt-text="要素に罫線を追加するには、コンソールを使用します。" lightbox="../media/console-dom-add-border.msft.png":::
    要素に罫線を追加するには、コンソールを使用 **します。**  
:::image-end:::  

Web ページの複雑さによっては、操作する適切な要素を見つけるのが困難な場合があります。  ただし、検査ツールを **使用して** 役立つ場合があります。  ヘッダー内のパーツを `Documentation` 操作するとします。

:::image type="complex" source="../media/console-dom-highlight-documentation.msft.png" alt-text="画面に検査する要素を表示する" lightbox="../media/console-dom-highlight-documentation.msft.png":::
    画面に検査する要素を表示する  
:::image-end:::  

操作する要素への直接参照を取得するには、次のアクションを実行します。  

1.  要素を **選択するには、[検査** ] ツールを使用します。  

    :::image type="complex" source="../media/console-dom-use-inspector-to-get-element.msft.png" alt-text="要素を選択するには、インスペクター ツールを使用します。" lightbox="../media/console-dom-use-inspector-to-get-element.msft.png":::
        要素を選択するには、インスペクター ツール **を使用** します。  
    :::image-end:::  
    
1.  選択すると、DevTools が要素ツールに **ジャンプ** します。  
1.  DOM ビュー `...` の要素の横にあるメニューを選択します。  
    
    :::image type="complex" source="../media/console-dom-overflow-menu-in-elements.msft.png" alt-text="選択した要素が Elements ツールの DOM ツリーに表示され、オーバーフロー メニューを選択してより多くの機能を取得します" lightbox="../media/console-dom-overflow-menu-in-elements.msft.png":::
        選択した要素が Elements ツールの DOM ツリーに **表示され、** オーバーフロー メニューを選択してより多くの機能を取得します  
    :::image-end:::  
    
1.  コンテキスト メニューを開き、[. `Copy`  >  `Copy JS Path`  
    
    :::image type="complex" source="../media/console-dom-copy-JS-path.msft.png" alt-text="要素ツールの DOM ビューの要素から JavaScript パスをコピーする" lightbox="../media/console-dom-copy-JS-path.msft.png":::
        要素ツールの DOM ビューの要素から JavaScript パスを **コピー** する  
    :::image-end:::  
    
1.  コンソールに戻り **、** コマンドを貼り付けます。  
    
リンクのテキストをに変更するには `My Playground` 、以前に貼 `.textContent = "My Playground"` り付けしたコマンドに追加します。  

:::image type="complex" source="../media/console-dom-change-content.msft.png" alt-text="コンソールを使用して要素のコンテンツを変更する" lightbox="../media/console-dom-change-content.msft.png":::
    コンソールを **使用して** 要素のコンテンツを変更する  
:::image-end:::  

コンソールで実行する JavaScript DOM 操作を使用 **します**。  使い方を便利にするために、 **コンソールには** いくつかのヘルパー メソッドが付属しています。  

## <a name="helpful-console-utility-methods"></a>便利なコンソール ユーティリティメソッド  

多くの便利な方法とショートカットは、コンソール ユーティリティ [として使用できます][DevtoolsConsoleUtilities]。  いくつかのメソッドは非常に強力で、おそらく過去に一連のステートメントとして `console.log()` 書いたものです。

### <a name="the-power-to-the-"></a>$ のパワー

コンソール `$` には特別な機能があります****。jQueryから覚えている可能性があります。

*   `$_` 最後のコマンドの結果を格納します。  したがって、入力して選択 `2 + 2` し `Enter` 、次に入力 `$_` すると、 **コンソールに表示** されます `4` 。
*   `$0` to `$4` は、最後に検査された要素のスタックが `$0` 常に最新の要素です。  したがって、前の例では、インスペクター ツールで要素**** を選択し、同じ効果を得 `$0.textContent = "My Playground"` るという入力を行いました。
*   `$x()` を使用すると、XPATH を使用して DOM 要素を選択できます。
*   `$()` と `$$()` の短いバージョン `document.querySelector()` です `document.querySelectorAll()` 。  
    
たとえば、次のコード スニペットは、web ページ内のすべてのリンクを取得し(\の短い場合)、リンクを並べ替え可能なテーブルとして表示して、たとえば、Excel にコピーして貼 `$$('a')` `document.querySelectorAll('a')` り付けます。

```javascript
console.table($$('a'),['href','text']);
```  

:::image type="complex" source="../media/console-dom-get-all-links.msft.png" alt-text="Web ページ内のすべてのリンクを取得し、結果を表として表示する" lightbox="../media/console-dom-get-all-links.msft.png":::
    Web ページ内のすべてのリンクを取得し、結果を表として表示する  
:::image-end:::  

ただし、情報を表示したくないが、データとして取得する場合。  この `$$('a')` ショートカットは、アンカー リンクと各プロパティのすべてのプロパティを提供します。  問題は、リンクと関連するテキストだけが必要な場合です。  

:::image type="complex" source="../media/console-dom-too-much-link-information.msft.png" alt-text="$$ ショートカットは、あまりにも多くの情報を返します" lightbox="../media/console-dom-too-much-link-information.msft.png":::
    ショートカット `$$` が戻す情報が多すぎます  
:::image-end:::  

ショートカット `$$` には興味深い追加機能があります。  純粋な方法を返す代わりに、ショートカットを使用すると `NodeList` `document.querySelectorAll()` `$$` 、すべてのメソッドが `Array` 表示されます。  必要 `map()` な情報に情報を減らすには、メソッドを使用します。  

```javascript
$$('a').map(a => {
    return {url: a.href, text: a.innerText}
})
```  

コード スニペットは、すべてのリンクの配列をオブジェクトとプロパティとして `url` 返 `text` します。  

:::image type="complex" source="../media/console-dom-filter-link-data.msft.png" alt-text="$$ のマップを使用して最小限に情報をフィルター処理する" lightbox="../media/console-dom-filter-link-data.msft.png":::
    map on を `$$` 使用して最小限の情報にフィルターを適用する  
:::image-end:::  

まだ行っていませんが、いくつかのリンクは Web ページへの内部リンクまたは空のテキストです。  内部リンクを削除するには、filter メソッドを使用します。  

```javascript
$$('a').map(a => {
    return {text: a.innerText, url: a.href}
}).filter(a => {
    return a.text !== '' && !a.url.match('docs.microsoft.com')
})
```  

:::image type="complex" source="../media/console-dom-filter-out-empty-links.msft.png" alt-text="空でないリンクを取得し、外部リンクを取得する" lightbox="../media/console-dom-filter-out-empty-links.msft.png":::
    空でないリンクを取得し、外部リンクを取得する  
:::image-end:::  

Web ページの最初に表示される通り、これらの要素を変更することもできます。  たとえば、次のコード スニペットは、すべての外部リンクの周囲に緑の枠線を作成します。

```javascript
$$('a[href^="https://"]').forEach(
  a => a.style.border = '1px solid green'
)
```  

:::image type="complex" source="../media/console-dom-highlight-links.msft.png" alt-text="すべての外部リンクを強調表示するには、各リンクの周囲に緑の枠線を追加します。" lightbox="../media/console-dom-highlight-links.msft.png":::
    すべての外部リンクを強調表示するには、各リンクの周囲に緑の枠線を追加します。  
:::image-end:::  

複雑な JavaScript を記述して結果をフィルター処理する代わりに、CSS セレクターの機能を使用します。  

インライン イメージではない Web ページ上のすべてのイメージのテーブルと情報を作成するには、次 `src` `alt` のアクションを実行します。  

1.  コンソールを **開きます**。  
1.  次のコード スニペットを入力またはコピーして貼り付けます。  

```javascript
console.table($$('img:not([src^=data])'), ['src','alt'])
```  

:::image type="complex" source="../media/console-dom-complex-CSS-selector.msft.png" alt-text="要素を選択するには、複雑な CSS セレクターを使用します。" lightbox="../media/console-dom-complex-CSS-selector.msft.png":::
    要素を選択するには、複雑な CSS セレクターを使用します。  
:::image-end:::  

さらに複雑な例の準備はできましたか?  この記事のようなマークダウンから生成された HTML Web ページには、各見出しの自動 ID 値が含まれるので、そのセクションへの深いリンクが可能になります。  たとえば、 に `# New features` 対する変更 `<h1 id="new-features">New features</h1>` 。  

コピーして貼り付けるすべての自動見出しの一覧を表示するには、次の操作を実行します。  

1.  コンソールを **開きます**。  
1.  次のコード スニペットを入力またはコピーして貼り付けます。  

```javascript
let out = '';
$$('#main [id]').filter(
    elm => {return elm.nodeName.startsWith('H')}
).forEach(elm => {
   out += elm.innerText + "\n" + 
          document.location.href + '#' +
          elm.id + "\n";
});
console.log(out);
```  

結果は、各見出しのコンテンツを含むテキストの後に、その見出しを示す完全な URL が続きます。  

:::image type="complex" source="../media/console-dom-get-generated-headings.msft.png" alt-text="Web ページからすべての見出しと生成された URL を取得する" lightbox="../media/console-dom-get-generated-headings.msft.png":::
    Web ページからすべての見出しと生成された URL を取得する  
:::image-end:::  

### <a name="clean-up-with-clear-and-copy"></a>クリアとコピーでクリーンアップする

コンソールで開発すると **、** 問題が発生する可能性があります。  コピーして貼り付ける間に結果を選択しようとするとイライラする場合があります。  次の 2 つのユーティリティ メソッドが役立ちます。  

*   `copy()` クリップボードに与える内容をコピーします。  この `copy()` メソッドは、最後の結果をコピーするメソッドと組み合 `$_` わせするときに特に便利です。
*   `clear()` コンソールをクリア**します。**

### <a name="read-and-monitor-events"></a>イベントの読み取りおよび監視

Console の他の 2 つの興味深いユーティリティ **メソッドは** 、イベント処理を扱います。

*   `getEventListeners(node)` ノードのすべてのイベント リスナーを一覧表示します。
*   `monitorEvents(node, events)` ノードで発生するイベントを監視およびログに記録します。

Web ページの最初のフォームに割り当てられているすべてのイベント リスナーを一覧表示するには、次のアクションを実行します。  

1.  コンソールを **開きます**。  
1.  次のコード スニペットを入力またはコピーして貼り付けます。  
    
    ```javascript
    getEventListeners($('form')); 
    ```  

:::image type="complex" source="../media/console-dom-get-form-events.msft.png" alt-text="Web ページの最初のフォームのすべてのイベント リスナーを取得する" lightbox="../media/console-dom-get-form-events.msft.png":::
    Web ページの最初のフォームのすべてのイベント リスナーを取得する  
:::image-end:::  

監視すると、指定した要素に何かが変更されるごとに、 **コンソール** で通知を受け取ります。  リッスンするイベントを 2 番目のパラメーターとして定義します。  監視するイベントを定義することが重要です。それ以外の場合は、要素に発生するイベントが報告されます。

スクロール、ウィンドウのサイズ変更****、またはユーザーが検索フォームに入力する度にコンソールで通知を取得するには、次の操作を実行します。  

1.  コンソールを **開きます**。  
1.  次のコード スニペットを入力またはコピーして貼り付けます。  
    
    ```javascript
    monitorEvents(window, ['resize', 'scroll']);
    monitorEvents($0, 'keyup');
    ```  
    
:::image type="complex" source="../media/console-dom-monitor-events.msft.png" alt-text="コンソールには、ウィンドウで発生するスクロール イベントが表示されます。" lightbox="../media/console-dom-monitor-events.msft.png":::
    **コンソールには** 、ウィンドウで発生するスクロール イベントが表示されます。  
:::image-end:::  

現在選択されている要素に対するキー アクションをログに記録するには、ヘッダーの検索フォームにフォーカスを合わせ、いくつかのキーを選択します。  

:::image type="complex" source="../media/console-dom-monitor-key-events.msft.png" alt-text="コンソールは、フォームで発生するキーアップ イベントを表示します。" lightbox="../media/console-dom-monitor-key-events.msft.png":::
    **コンソールには** 、 `keyup` フォーム上で発生するイベントが表示されます。  
:::image-end:::  

停止するには、次のコード スニペットを使用して設定した監視を削除します。  

```javascript
unmonitorEvents(window, ['resize', 'scroll']);
unmonitorEvents($0, 'key');
```  

## <a name="reuse-dom-manipulation-scripts"></a>DOM 操作スクリプトの再利用

コンソールから DOM を操作すると便利な場合 **があります**。  開発プラットフォームとしてコンソールの制限 **が発生する** 可能性があります。  良いニュースは [、DevTools][DevtoolsSourcesIndex] の Sources ツールが完全に機能する開発環境を提供しているというニュースです。  [ソース **] ツールで** 、次の操作を実行できます。  

*   コンソールのスクリプトを **スニペット** として [保存します][DevToolsJavascriptSnippets]。  
*   キーボード ショートカットまたはエディターを使用して Web ページでスクリプトを実行します。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleConsoleJavascript]: ./console-javascript.md "JavaScript 環境としてのコンソール |Microsoft Docs"  
[DevtoolsConsoleConsoleLog]: ./console-log.md "コンソール ツール にログイン|Microsoft Docs"  
[DevtoolsConsoleUtilities]: ./utilities.md "コンソール ユーティリティ API リファレンス |Microsoft Docs"  

[DevToolsJavascriptSnippets]: ../javascript/snippets.md "DevTools を使用して任意のページで JavaScript のスニペットMicrosoft Edge実行|Microsoft Docs"  
[DevtoolsSourcesIndex]: ../sources/index.md "ソース ツールの概要|Microsoft Docs"  
