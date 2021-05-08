---
description: JavaScript エラーは開発者ツールによって報告され、コンソールでそれぞれデバッグされます
title: コンソールを使用したエラーの追跡
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/13/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: ebd12f8932332b3e63162ab6952577bdb43bbccd
ms.sourcegitcommit: 2e516a92272e38d8073603f860ae49f944718670
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "11483534"
---
# <a name="debug-errors-reported-in-console"></a>コンソールで報告されたデバッグ エラー  

コンソールの最初のエクスペリエンス **は、スクリプト** のエラーである可能性があります。  これを試す場合は、 [コンソール ツールで報告された JavaScript エラーに移動します][GithubMicrosoftedgeDevtoolssamplesConsoleErrorHtml]。  

ブラウザーで DevTools を開いた場合は、上部の右側のボタンに Web ページのエラーが表示されます。  
ボタンを選択してコンソールに移動 **し** 、エラーの詳細を表示します。  

:::image type="complex" source="../media/console-debug-displays-error.msft.png" alt-text="DevTools は、コンソールでエラーに関する詳細情報を提供します。" lightbox="../media/console-debug-displays-error.msft.png":::
   DevTools は、コンソールでエラーに関する詳細情報を提供 **します。**  
:::image-end:::  

この情報から、エラーがファイルの 16 行目にあると収集 `error.html` できます。  コンソールの右側にあるリンクを選択すると、[ソース] ツールにアクセスし、エラーが発生したコード行 `error.html:16` を強調表示します。 **** ****  

:::image type="complex" source="../media/console-debug-displays-in-sources.msft.png" alt-text="ソース ツールは、エラーの原因となるコード行を強調表示します。" lightbox="../media/console-debug-displays-in-sources.msft.png":::
   ソース **ツールは** 、エラーの原因となるコード行を強調表示します。  
:::image-end:::  

スクリプトは、ドキュメントの最初の要素 `h2` を取得し、その周囲に赤い枠線を描画します。  ただし、 `h2` 要素が存在しないので、スクリプトは失敗します。  

## <a name="find-and-debug-network-issues"></a>ネットワークの問題の検索とデバッグ  

コンソールがレポートするその他 **の** エラーは、ネットワーク エラーです。  アクションで表示するには、コンソールで報告された [ネットワーク エラーに移動します][GithubMicrosoftedgeDevtoolssamplesConsoleNetworkErrorHtml]。  

:::image type="complex" source="../media/console-debug-network-error.msft.png" alt-text="コンソールにネットワークと JavaScript エラーが表示される" lightbox="../media/console-debug-network-error.msft.png":::
   **コンソールに** ネットワークと JavaScript エラーが表示される  
:::image-end:::  

データが取得されないので、表は表示されますが `loading` 、Web ページには何も変更されません。  コンソールで **、次**の 2 つのエラーが発生しました。  

*   HTTP メソッドで始まり `GET` 、URI が続くネットワーク エラー。  
*   エラー `Uncaught (in promise) TypeError: data.forEach is not a function` 。  
    
コンソールでリンク `network-error.html:40` を選択すると、DevTools によってソース ツール**にアクセス**できます。 ****  問題のあるコード行が強調表示され `error` 、\( \) ボタンが `x` 続きます。  エラー メッセージを `Failed to load resource: the server responded with a status of 404 ()` 表示するには、エラー **** \( `x` \) ボタンを選択します。  


:::row:::
   :::column span="":::
      :::image type="complex" source="../media/console-debug-network-error-code-line.msft.png" alt-text="Web ページへのリンクを選択し、エラーが発生するコード行が [ソース] ツールを開きます" lightbox="../media/console-debug-network-error-code-line.msft.png":::
         Web ページへのリンクを選択し、エラーが発生するコード行が [ソース] ツール **を開** きます  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/console-debug-network-error-sources.msft.png" alt-text="JavaScript でエラーを見つけるには、Sources ツールを使用します。" lightbox="../media/console-debug-network-error-sources.msft.png":::
         JavaScript でエラーを見つけるには、Sources ツール **を使用** します。  
      :::image-end:::  
   :::column-end:::
:::row-end:::

この例では、要求された URL が見つからないというエラーメッセージが表示されます。  次に、次のアクションを実行してネットワーク ツール **を開** きます。  

1.  コンソールを **開きます**。  
1.  エラーに関連付けられている URI を選択します。  
    
:::image type="complex" source="../media/console-debug-network-error-url.msft.png" alt-text="リソースが読み込まれなかった後、コンソールにエラーの HTTP 状態コードが表示される" lightbox="../media/console-debug-network-error-url.msft.png":::
   **リソース** が読み込まれなかった後、コンソールにエラーの HTTP 状態コードが表示される  
:::image-end:::  

:::row:::
    :::column:::
        :::image type="complex" source="../media/console-debug-network-error-network.msft.png" alt-text="ネットワーク ツールは、失敗した要求の詳細を表示します。" lightbox="../media/console-debug-network-error-network.msft.png":::
           ネットワーク **ツールは** 、失敗した要求の詳細を表示します。  
        :::image-end:::  
    :::column-end:::
    :::column:::
        :::image type="complex" source="../media/console-debug-network-error-network-detail.msft.png" alt-text="ネットワーク ツールでヘッダーを検査すると、より多くの洞察が得られる可能性があります" lightbox="../media/console-debug-network-error-network-detail.msft.png":::
           ネットワーク ツールでヘッダーを検査 **すると** 、より多くの洞察が得られる可能性があります  
        :::image-end:::  
    :::column-end:::
:::row-end:::  

問題は何でしたか?  2 つのスラッシュ文字 \( `//` \) は、単語の後に要求された URI で発生します `repos` 。  [ソース] **ツールを開** き、行 26 を調します。  末尾のスラッシュ文字 \( `/` \) は、基本 URI の末尾に発生します。  

:::image type="complex" source="../media/console-debug-network-error-code-error.msft.png" alt-text="ソース ツールは、エラーが発生したコード行を表示します。" lightbox="../media/console-debug-network-error-code-error.msft.png":::
   ソース **ツールは、** エラーが発生したコード行を表示します。  
:::image-end:::  

コンソールでエラーを確認するには、[ **コンソール**] で報告 [された固定ネットワーク エラーに移動します][GithubMicrosoftedgeDevtoolssamplesConsoleNetworkErrorFixedHtml]。  

:::image type="complex" source="../media/console-debug-network-error-fixed.msft.png" alt-text="エラーのない例では、エラーから情報が読み込GitHub表示されます。" lightbox="../media/console-debug-network-error-fixed.msft.png":::
   エラーのない例では、エラーから情報が読み込GitHub表示されます。  
:::image-end:::  

以前のユーザー エクスペリエンスを回避するために、防御的なコーディング手法を提供してください。  また、コードがエラーをキャッチし、コンソールに **それぞれ表示します**。  [コンソールと [UI] で [ネットワーク エラー報告] に移動し][GithubMicrosoftedgeDevtoolssamplesConsoleNetworkErrorReportedHtml] 、次の項目を確認します。  

*   何か問題が起こったことをユーザーに UI を提供します。  
*   コンソールで **、** コードからのネットワーク エラーに関する有用な情報を提供します。  
    
:::image type="complex" source="../media/console-debug-network-error-report.msft.png" alt-text="エラーをキャッチして報告する例" lightbox="../media/console-debug-network-error-report.msft.png":::
   エラーをキャッチして報告する例  
:::image-end:::  

次のコード スニペットは、メソッド (特に行) を使用してエラー `handleErrors` をキャッチして報告 `throw Error` します。  

```javascript
const handleErrors = (response) => {
    if (!response.ok) {
        let message = 'Could not load the information'
        document.querySelector('tbody').innerHTML = `
        <tr><td colspan=3>Error ${message}</td></tr>
        `;
        throw Error(response.status + ' ' + response.statusText);
    }
    return response;
};
```  

## <a name="create-errors-and-traces-in-the-console"></a>コンソールでエラーとトレースを作成する

前のセクション `throw Error` の例に加え、コンソールで異なるエラーやトレースの問題を作成 **することもできます**。  
作成された 2 つのエラー メッセージをコンソールに表示 **するには、[** コンソールでエラー レポートとアサーションを作成 [する] に移動します][GithubMicrosoftedgeDevtoolssamplesConsoleErrorAssertHtml]。  

:::image type="complex" source="../media/console-debug-error-assert.msft.png" alt-text="コンソールから作成されたエラー メッセージ" lightbox="../media/console-debug-error-assert.msft.png":::
   コンソールから作成された **エラー メッセージ**  
:::image-end:::  

次のコード スニペットは、前の例で使用しました。  

```javascript
function first(name) { second(name); }
function second(name) { third(name); }
function third(name) {
    if (!name) {
        console.error(`Name isn't defined :(`)
    } else {
        console.assert(
            name.length <= 8, 
            `"${name} is not less than eight letters"`
        );
    }
}
first();
first('Console');
first('Microsoft Edge Canary');
```  

お互いに連続して要求する 3 つの関数があります。  

*   `first()`  
*   `second()`  
*   `third()`  
    
各引数は `name` 、もう一方に送信します。  関数では、引数が存在するかどうかを確認し、引数が存在しない場合は、名前が定義されていないというエラー `third()` `name` をログに記録します。  定義 `name` されている場合は、このメソッドを使用して、引数の長が 8 文字 `assert()` `name` 未満の場合にチェックします。  次のパラメーターを `first()` 使用して、関数を 3 回要求します。  

*   関数内のメソッドをトリガー `console.error()` する引数 `third()` はありません。  
*   引数が存在し、8 文字より短いので、関数のパラメーターとしての用語はエラー `Console` `first()` `name` を引き起こしません。  
*   パラメーターとしての `Microsoft Edge Canary` 語句を関数に指定すると、パラメーターが 8 文字を超えるので、メソッドはエラー `first()` `console.assert()` を報告します。  
    
条件付きエラー `console.assert()` レポートを作成するには、このメソッドを使用します。  次の 2 つの例は同じ結果を持っていますが、1 つは追加のステートメントを必要 `if{}` とします。  

```javascript
let x = 20;
if (x < 40) { console.error(`${x} is too small`) };
console.assert(x >= 40, `${x} is too small`) 
```  

> [!IMPORTANT]
> コードの 2 行目と 3 行目は同じテストを実行します。  アサーションは負の結果を記録する必要があるから、ケースとアサーション `x < 40` `if` のテスト `x >= 40` を行います。  

どの関数が別の関数を要求するのか分からない場合は、メソッドを使用して、現在の関数にアクセスするために要求される関数 `console.trace()` を追跡します。  コンソールにトレースを表示するには、[ **コンソール**でトレースを [作成する] に移動します][GithubMicrosoftedgeDevtoolssamplesConsoleTraceHtml]。  

```javascript
function here() {there()}
function there() {everywhere()}
function everywhere() {
    console.trace();
}
here();
there();
```  

結果は、名前が付いたトレースを表示し、2 番目の例では名前 `here()` `there()` `everywhere()` が付いたトレースになります `everywhere()` 。  

:::image type="complex" source="../media/console-debug-trace.msft.png" alt-text="コンソールから作成されたトレース" lightbox="../media/console-debug-trace.msft.png":::
   コンソールから作成された **トレース**  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[GithubMicrosoftedgeDevtoolssamplesConsoleErrorHtml]: https://microsoftedge.github.io/DevToolsSamples/console/error.html "コンソール ツール で報告された JavaScript エラー|GitHub"  
[GithubMicrosoftedgeDevtoolssamplesConsoleErrorAssertHtml]: https://microsoftedge.github.io/DevToolsSamples/console/error-assert.html "コンソール ウィンドウでエラー レポートとアサーションを作成|GitHub"  
[GithubMicrosoftedgeDevtoolssamplesConsoleNetworkErrorHtml]: https://microsoftedge.github.io/DevToolsSamples/console/network-error.html "コンソール ウィンドウで報告されたネットワーク エラー|GitHub"  
[GithubMicrosoftedgeDevtoolssamplesConsoleNetworkErrorFixedHtml]: https://microsoftedge.github.io/DevToolsSamples/console/network-error-fixed.html "コンソール ウィンドウで報告されたネットワーク エラーを修正|GitHub"  
[GithubMicrosoftedgeDevtoolssamplesConsoleNetworkErrorReportedHtml]: https://microsoftedge.github.io/DevToolsSamples/console/network-error-reported.html "コンソールと UI のネットワーク エラー報告|GitHub"  
[GithubMicrosoftedgeDevtoolssamplesConsoleTraceHtml]: https://microsoftedge.github.io/DevToolsSamples/console/trace.html "コンソール ウィンドウでトレースを作成|GitHub"  
