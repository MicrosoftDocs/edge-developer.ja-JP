---
description: コンソール メッセージをフィルター処理する方法について説明します。
title: コンソールでのメッセージのフィルター処理の開始
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/13/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: b493bb790b48bc1c4dca0e6802d2f638099b7644
ms.sourcegitcommit: 2e516a92272e38d8073603f860ae49f944718670
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "11483553"
---
# <a name="filter-console-messages"></a>コンソール メッセージのフィルター  

Web をサーフィンすると、コンソール **にあらゆる種類** の情報が殺到している場合があります。  多くの場合、情報はユーザーに関係ありません。  デバッグ中に別の開発者がログに記録したライブ プロジェクトに関する情報など。  または、変更できない現在のサイトのパフォーマンスに関する違反と警告に関する詳細。  コンソールのフィルター オプションを使用してノイズを **低減するの** も理にかなっています。  

## <a name="filter-by-log-level"></a>ログ レベルでフィルター処理する  

オブジェクトの各メソッド `console` には、重大度レベルが関連付けされています。  重大度レベルは `Verbose` `Info` `Warning` 、、またはです `Error` 。  API ドキュメントに重大度レベルを [表示します][DevtoolsConsoleApi]。  たとえば `console.log()` 、-level `Info` メッセージですが `console.error()` `Error` 、-level メッセージです。  

コンソールでメッセージをフィルター処理 **するには**、[ログ レベル **] ドロップダウン メニューを** 使用します。  各レベルの状態を切り替えできます。  各レベルをオフにするには、各レベルの横にあるチェックマークを削除します。  

:::image type="complex" source="../media/console-filter-dropdown.msft.png" alt-text="ドロップダウン メニューは、ログ レベルを使用してコンソール メッセージをフィルター処理します。" lightbox="../media/console-filter-dropdown.msft.png":::
    ドロップダウン メニューは、ログ **レベルを使用** してコンソール メッセージをフィルター処理します。  
:::image-end:::  

フィルターは適用されませんので、次の図は数十のメッセージを表示します。  次に、メッセージの数を減らして管理します。  

:::image type="complex" source="../media/console-filter-displays-all.msft.png" alt-text="フィルター セットがない場合は、多くのコンソール メッセージが表示される可能性があります。" lightbox="../media/console-filter-displays-all.msft.png":::
    フィルター セットがない場合は、多くのコンソール メッセージが表示される可能性があります。  
:::image-end:::  

すべての警告レベルのメッセージを非表示にし、ノイズを減らします。  [ログ レベル] **ドロップダウンに移動** し、レベルのチェックを外 `Warnings` します。  

:::image type="complex" source="../media/console-filter-hide-warning.msft.png" alt-text="コンソール内のすべての警告レベルメッセージを非表示にし、ノイズの多くをフィルター処理する" lightbox="../media/console-filter-hide-warning.msft.png":::
    コンソール内のすべての警告レベルメッセージを非表示 **にし** 、ノイズの多くをフィルター処理する  
:::image-end:::  

## <a name="filter-by-text"></a>テキストによるフィルター  

詳細を確認する場合は、テキストを使用してメッセージをフィルター処理するには、[フィルター] テキスト ボックスに文字列 **を** 入力します。  たとえば、リソースの読み込みをブロックしているブラウザーに関するメッセージのみを表示するには、ボックス `block` に入力します。

:::image type="complex" source="../media/console-filter-text.msft.png" alt-text="単語ブロックを含むメッセージを表示します。" lightbox="../media/console-filter-text.msft.png":::
    単語を含むメッセージを表示します。 `block`  
:::image-end:::  

## <a name="filter-by-regular-expression"></a>正規表現によるフィルター

[正規表現は、][MdnDocsWebJavascriptGuideRegularExpressions] メッセージをフィルター処理する強力な方法です。  たとえば、[フィルター] `/^Tracking/` テキスト ボックス **に** 入力して、用語で始まるメッセージのみを表示します `Tracking` 。  正規表現に慣れていない場合 [、RegExr][|::ref1::|Main] は正規表現の使用について学ぶのに最適なリソースです。

:::image type="complex" source="../media/console-filter-regex.msft.png" alt-text="[フィルター] テキスト ボックスの正規表現を使用して、単語フィルターで始まるメッセージを表示します。" lightbox="../media/console-filter-regex.msft.png":::
    [フィルター] テキスト ボックスに正規表現を使用 `filter` して単語で始まるメッセージ **を** 表示します。  
:::image-end:::  

## <a name="filter-by-message-source"></a>メッセージ ソースによるフィルター  

また、表示するメッセージの種類と、コンソールのサイドバーを使用してそれぞれの発信 **元を** 定義 **することもできます**。  これを行うには、[コンソールサイドバーの **表示] ボタンを選択** します。  

:::image type="complex" source="../media/console-filter-sidebar-icon.msft.png" alt-text="サイドバーを開く場合は、サイドバーアイコン" lightbox="../media/console-filter-sidebar-icon.msft.png":::
    サイドバーを開 **く場合は**、[コンソールサイドバーの **表示] ボタンを選択** します。  
:::image-end:::  

サイドバーが **開いている** ときに、メッセージの全体の数と、それぞれの発信元を表示できます。  オプションは `All messages` `User Messages` 、、、、、 `Errors` `Warnings` `Info` です `Verbose` 。  

:::image type="complex" source="../media/console-filter-sidebar-open.msft.png" alt-text="コンソール サイドバーには、発信元の異なるソース メッセージが表示されます。" lightbox="../media/console-filter-sidebar-open.msft.png":::
    コンソール **サイドバーには、** 発信元の異なるソース メッセージが表示されます。  
:::image-end:::  

任意のオプションを選択して、その種類のメッセージのみを表示します。  たとえば、ユーザー メッセージを表示するには、[ユーザー メッセージ] オプションを選択して、ノイズを少なく表示します。

:::image type="complex" source="../media/console-filter-select-user-messages.msft.png" alt-text="サイドバーのフィルターを使用してコンソールにユーザー メッセージのみを表示する場合を選択します。" lightbox="../media/console-filter-select-user-messages.msft.png":::
    サイドバーのフィルターを使用してコンソールにユーザー **メッセージのみを** 表示する場合を選択 **します。**  
:::image-end:::  

さらにフィルターを適用して選択肢を展開するには、その横にある三角形のアイコンを選択します。  この方法では、特定のソースから発信されたメッセージのみを表示するための選択肢が多く表示されます。  

:::image type="complex" source="../media/console-filter-sidebar-open-arrow.msft.png" alt-text="矢印アイコンを選択すると、各セクションが展開されます" lightbox="../media/console-filter-sidebar-open-arrow.msft.png":::
    矢印アイコンを選択すると、各セクションが展開されます  
:::image-end:::  

:::image type="complex" source="../media/console-filter-user-message-by-source.msft.png" alt-text="種類とソースを使用してフィルター処理する新しいオプションを選択する" lightbox="../media/console-filter-user-message-by-source.msft.png":::
    種類とソースを使用してフィルター処理する新しいオプションを選択する  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleApi]: ./api.md "コンソール API リファレンス |Microsoft Docs"  

[MdnDocsWebJavascriptGuideRegularExpressions]: https://developer.mozilla.org/docs/Web/JavaScript/Guide/Regular_Expressions "正規表現|MDN"  

[RegExrMain]: https://regexr.com "RegExr"  
