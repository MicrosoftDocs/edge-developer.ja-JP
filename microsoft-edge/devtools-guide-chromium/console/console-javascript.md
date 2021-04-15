---
description: JavaScript 環境として Microsoft Edge Developer Tools 内でコンソール ツールを使用する方法について説明します。
title: JavaScript 環境としてのコンソール
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/13/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, JavaScript, Web 開発, f12 ツール, devtools
ms.openlocfilehash: f75ac6d728c9a69542b2f58df85248759267f76d
ms.sourcegitcommit: 2e516a92272e38d8073603f860ae49f944718670
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "11483536"
---
# <a name="the-console-as-a-javascript-environment"></a>JavaScript 環境としてのコンソール  

ブラウザー **DevTools** 内のコンソール ツールは [REPL 環境][WikiReadEvalPrintLoop] です。  これは、直ちに実行される JavaScript を **コンソール** に記述できるという意味です。

これを試す場合は、次のアクションを実行します。  

1.  コンソールを **開きます**。  
    *   `Control` + `Shift` + `J` \(Windows, Linux\) または `Command` + `Option` + `J` \(macOS\) を選択します。  
1.  「`2 + 2`」と入力します。  コンソール **では、** 入力中に次 `4` の行に結果が既に表示されます。  この `Eager evaluation` 機能は、有効な JavaScript を記述するのに役立ちます。  間違っているかどうか、または有効な結果が存在するかどうかを入力すると、結果が表示されます。  

:::image type="complex" source="../media/console-javascript-eager-evaluation.msft.png" alt-text="コンソールは、入力時に 2 + 2 ライブの結果を表示します。" lightbox="../media/console-javascript-eager-evaluation.msft.png":::
   **コンソールは** 、入力時に `2 + 2` ライブの結果を表示します  
:::image-end:::  

[コンソール] を選択すると、JavaScript コマンドが実行され、結果が表示され、次の `Enter` コマンドを記述できます。 ****  

:::image type="complex" source="../media/console-javascript-several-expressions.msft.png" alt-text="複数の JavaScript 式を連続して実行する" lightbox="../media/console-javascript-several-expressions.msft.png":::
   複数の JavaScript 式を連続して実行する  
:::image-end:::  

## <a name="autocompletion-to-write-complex-expressions"></a>複雑な式を記述するオートコンプリート

最後の例は恐ろしいと思われるかもしれませんが****、コンソールは優れたオートコンプリート機能を使用して複雑な JavaScript を記述するのに役立ちます。  この機能は、以前知らなかったメソッドについて学ぶのに最適な方法です。  

これを試す場合は、次のアクションを実行します。  

1.  「`doc`」と入力します。  
1.  ドロップダウン `document` メニューから選択します。  
1.  キーを `tab` 選択して選択します。  
1.  「`.bo`」と入力します。  
1.  を `tab` 選択して取得します `document.body` 。  
1.  現在の Web ページの本文で使用可能なプロパティとメソッドの大きな一覧を取得するには、別のプロパティ `.` を入力します。  

:::image type="complex" source="../media/console-javascript-autocomplete.msft.png" alt-text="JavaScript 式のコンソールオートコンプリート" lightbox="../media/console-javascript-autocomplete.msft.png":::
   JavaScript**式の**コンソールオートコンプリート  
:::image-end:::  

## <a name="console-history"></a>コンソールの履歴

他の多くのコマンド ライン エクスペリエンスと同様に、コマンドの履歴も持っています。  前 `Arrow Up` に入力したコマンドを表示する場合に選択します。  オートコンプリートでは、以前に入力したコマンドの履歴も保持されます。  以前のコマンドの最初の数文字を入力すると、テキスト ボックスに以前の選択肢が表示されます。  

また、**コンソールには、** 生活を容易にする[][DevtoolsConsoleUtilities]ユーティリティメソッドもいくつか用意されています。  たとえば、コンソールで実行した最後の式の結果が常 `$_` に含 **まれるとします**。

:::image type="complex" source="../media/console-javascript-console-history.msft.png" alt-text="コンソール$ $_ 式には、常に最後の結果が含まれる" lightbox="../media/console-javascript-console-history.msft.png":::
    コンソール `$_` の式には**** 常に最後の結果が含まれる  
:::image-end:::  

## <a name="multiline-edits"></a>複数行の編集

既定では、 **コンソールには JavaScript** 式を記述する行が 1 行しか表示されません。  を選択すると、コードが実行されます `Enter` 。 1 行の制限は、ユーザーをイライラさせる可能性があります。  1 行の制限を回避するには、代わりに `Shift` + `Enter` を選択します `Enter` 。  次の例では、表示される値は、すべての行が順番に実行された結果です。  

:::image type="complex" source="../media/console-javascript-multiline.msft.png" alt-text="Shift + Enter キーを押して複数行の JavaScript を記述すると、結果の値が順番に実行されます。" lightbox="../media/console-javascript-multiline.msft.png":::
   複数 `Shift` + `Enter` 行の JavaScript を記述する場合に選択すると、結果の値が順番に実行されます。  
:::image-end:::  

コンソールで複数行のステートメントを開始すると****、自動的に認識されインデントされます。  たとえば、中かっこでブロック ステートメントを開始する場合です。  

:::image type="complex" source="../media/console-javascript-automatic-lineindent.msft.png" alt-text="コンソールでは、中かっことインデントを使用して複数行式が既に認識されています。" lightbox="../media/console-javascript-automatic-lineindent.msft.png":::
    **コンソール** では、中かっことインデントを使用して複数行式が既に認識されています。  
:::image-end:::  

## <a name="network-requests-using-top-level-await"></a>トップ レベルの await() を使用したネットワーク要求  

独自のスクリプト以外に、**コンソール**は任意[][GithubTc39ProposalTopLevelAwait]の非同期 JavaScript を実行するためのトップ レベルの await をサポートしています。  たとえば、非同期関数で `fetch` ステートメントをラップ `await` せずに API を使用します。  

Microsoft Edge Developer Tools for microsoft Edge Developer Tools for Visual Studio [GitHub][GithubMicrosoftVscodeEdgeDevtools] リポジトリで最後の 50 の問題を取得するには、次のアクションを実行します。  

1.  コンソールを **開きます**。  
1.  次のコード スニペットをコピーして貼り付け、10 エントリを含むオブジェクトを取得します。  
    
    ```javascript
    await ( await fetch(
    'https://api.github.com/repos/microsoft/vscode-edge-devtools/issues?state=all&per_page=50&page=1'
    )).json();
    ```  
    
:::image type="complex" source="../media/console-javascript-top-level-await.msft.png" alt-text="コンソールは、トップ レベルの非同期フェッチ要求の結果を表示します。" lightbox="../media/console-javascript-top-level-await.msft.png":::
    **コンソール** は、トップ レベルの非同期要求の結果を表示 `fetch` します。  
:::image-end:::  

多くの情報が表示されますので、10 のエントリを認識するのは難しいです。  幸いなことに、log メソッドを使用して、興味のある情報 `console.table()` のみを受け取る場合があります。  

:::image type="complex" source="../media/console-javascript-filtered-with-table.msft.png" alt-text="console.table を使用して、人間が読み取り可能な形式で最後の結果を表示する" lightbox="../media/console-javascript-filtered-with-table.msft.png":::
    使用して人間が読み取り可能な形式で最後の結果を表示する `console.table`  
:::image-end:::  

式から返されるデータを再利用するには、Console のユーティリティ `copy()` メソッドを使用 **します**。  次のコード スニペットは要求を送信し、応答からクリップボードにデータをコピーします。  

```javascript
copy(await (await fetch(
'https://api.github.com/repos/microsoft/vscode-edge-devtools/issues?state=all&per_page=50&page=1'
)).json())
```  

JavaScript **の機能** を実践し、簡単な計算を行う最適な方法としてコンソールを使用します。  実際の機能は、window オブジェクトにアクセスできる [という事実][MdnDocsWebApiWindow] です。  コンソールで [DOM を操作できます][DevtoolsConsoleConsoleDomInteraction]。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleConsoleDomInteraction]: ./console-dom-interaction.md "コンソールを使用して DOM ファイルを操作|Microsoft Docs"  
[DevtoolsConsoleUtilities]: ./utilities.md "コンソール ユーティリティ API リファレンス |Microsoft Docs"  

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools | GitHub"  

[GithubTc39ProposalTopLevelAwait]: https://github.com/tc39/proposal-top-level-await "ECMAScript 提案: トップ レベルの await - tc39/proposal-top-level-await |GitHub"

[MdnDocsWebApiWindow]: https://developer.mozilla.org/docs/Web/API/Window "ウィンドウ |MDN"  

[WikiReadEvalPrintLoop]: https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop "Read-eval-print ループ |Wikipedia"  
