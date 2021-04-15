---
description: コンソールに同じ JavaScript 式を繰り返し入力する場合は、代わりに Live 式を試してください。
title: Live 式を使用して JavaScript 式の値をリアルタイムで確認する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/13/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 51b7aa5119775f43861a84c1055ac9149a626d8a
ms.sourcegitcommit: 2e516a92272e38d8073603f860ae49f944718670
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "11483143"
---
# <a name="monitor-changes-in-javascript-using-live-expressions"></a>Live 式を使用して JavaScript の変更を監視する  

**Live 式は** 、多くの変更を行う JavaScript 式を監視する優れた方法です。    読み取りおよび移動する多くのコンソール メッセージを持つ代わりに、特定の JavaScript 式をコンソールの上部にピン留め **することもできます**。  

## <a name="add-a-new-live-expression"></a>新しいライブ式を追加する  

開始するには、[フィルター] **テキスト ボックスの** 横にある [ライブ式の作成] \(eye\) **ボタンを** 選択します。  選択すると、新しい式を入力するテキスト ボックスが表示されます。  

:::image type="complex" source="../media/console-live-expressions-new.msft.png" alt-text="[新しいライブ式] ボタンを選択してテキスト ボックスを開き、式を入力します。" lightbox="../media/console-live-expressions-new.msft.png":::
    式を `New live expression` 入力するテキスト ボックスを開くボタンを選択する  
:::image-end:::  

**Live 式には** 、任意の有効な JavaScript 式を指定できます。  これを試す場合は、次のアクションを実行します。  

1.  [Live **式] テキスト ボックスを** 開きます。  
1.  「`document.activeElement`」と入力します。  
1.  式を保存するには、次のいずれかの操作を実行します。  
    *   `Control` + `Enter` \(Windows, Linux\) または `Command` + `Enter` \(macOS\) を選択します。  
    *   [Live 式] **テキスト ボックスの外側を** 選択します。  
        
式がライブで表示され、 `body` 結果として表示されます。  

:::image type="complex" source="../media/console-live-expressions-document-active-element.msft.png" alt-text="document.activeElement の Live 式は、結果として本文を表示します。" lightbox="../media/console-live-expressions-document-active-element.msft.png":::
    結果として本文 `document.activeElement` を表示するライブ式  
:::image-end:::  

Web ページを移動すると、値が変更されます。  たとえば、次の図では、Web ページで検索メニューを開き、式が値 `button.nav-bar-button.focus-visible` として表示されます。  

:::image type="complex" source="../media/console-live-expressions-document-active-element-nav-button.msft.png" alt-text="Live 式の値を変更するには、Web ページ上の異なる要素を操作します。" lightbox="../media/console-live-expressions-document-active-element-nav-button.msft.png":::
    Live 式の値を **変更するには、Web**ページ上の異なる要素を操作します。  
:::image-end:::  

値を再度変更するには、Web ページの [検索] テキスト ボックスを開いて選択します。  

:::image type="complex" source="../media/console-live-expressions-document-active-element-search.msft.png" alt-text="Web ページ内の別の要素に移動して Live 式を更新する" lightbox="../media/console-live-expressions-document-active-element-search.msft.png":::
    Web ページ内の別の要素に移動して Live **式を更新する**  
:::image-end:::  

## <a name="remove-live-expressions"></a>ライブ式の削除  

Live **式は** 、アクティブにしている限り使用できます。  Live 式を削除 **するには**、その横 `x` にある式を選択します。  

:::image type="complex" source="../media/console-live-expressions-remove.msft.png" alt-text="Live 式を削除するには、その横にある x を選択します。" lightbox="../media/console-live-expressions-remove.msft.png":::
    Live 式 **を削除するには**、その横 `x` にある式を選択します。  
:::image-end:::  

## <a name="replace-console-logging-with-live-expressions"></a>コンソール ログを Live 式に置き換える  

必要な数の式を作成し、ブラウザー セッションとウィンドウ間で各式を保持できます。  **Live 式** は、デバッグ ワークフローのノイズを削減する方法です。  

たとえば、現在の Web ページでマウスの動きを監視します。  [ログ マウス [の移動] デモに][GithubMicrosoftedgeDevtoolssamplesConsoleMousemoveHtml]移動し、 **コンソール**を開き、マウスを動かして、多くの情報を含むログを表示します。  

:::image type="complex" source="../media/console-live-expression-mouse-logging.msft.png" alt-text="コンソールはマウスの位置に関する多くの情報を表示します" lightbox="../media/console-live-expression-mouse-logging.msft.png":::
    **コンソールは** マウスの位置に関する多くの情報を表示します  
:::image-end:::  

大量の情報はデバッグ プロセスを遅くするだけでなく、確認する変更を見逃しがちです。  コンソールにより **多くの** メッセージが表示され、マウスを移動すると、確認する値が画面をスクロールオフします。  

別の **方法として Live 式** を試す場合は、次のアクションを実行します。  

1.  ログデモなしで [マウスの動きに移動します][GithubMicrosoftedgeDevtoolssamplesConsoleMouseNoLogHtml]。  
1.  の **Live 式を作成** `x` します `y` 。  
    
Live Expressions を**使用する場合**は、常に画面の同じ部分に情報を**** 取得し、あまり変更しない値のコンソール ログを保持します。

:::image type="complex" source="../media/console-live-expressions-x-and-y.msft.png" alt-text="マウスの x 位置と y 位置を Live 式として表示する" lightbox="../media/console-live-expressions-x-and-y.msft.png":::
    マウスの位置を Live 式 `x` `y` **として表示する**  
:::image-end:::  

**Live Expressions** はコンピューター上で排他的に実行され、表示するコード内で何も変更する必要はありません。  **Live 式** は、デバッグする情報のみを表示するための最適な方法です。  また **、Live Expressions を使用** すると、ユーザーのコンピューターのノイズを制限できます。

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[GithubMicrosoftedgeDevtoolssamplesConsoleMousemoveHtml]: https://microsoftedge.github.io/DevToolsSamples/console/mousemove.html "コンソール メッセージの例: テーブル の使用|GitHub"  
[GithubMicrosoftedgeDevtoolssamplesConsoleMouseNoLogHtml]: https://microsoftedge.github.io/DevToolsSamples/console/mousemove-no-log.html "ログを記録せずにマウス|GitHub"  
