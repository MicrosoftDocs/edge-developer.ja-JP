---
description: Tab キーと Enter キーを使用してキーボードのサポートを確認します。
title: Tab キーと Enter キーを使用してキーボードのサポートを確認する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 48151e16a9059b5ebaadca36f29447d4ad3be8c7
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597491"
---
# <a name="check-for-keyboard-support-by-using-the-tab-and-enter-keys"></a>Tab キーと Enter キーを使用してキーボードのサポートを確認する


すべてのユーザーがポインターまたはタッチ デバイスを持っている必要があります。また、すべてのユーザーが作成した Web プロジェクトを表示できる場合ではありません。  これは、ユーザー インターフェイスが少なくともキーボードで動作することが重要な理由です。  キーを使用して、Web ページ上の各フォーム コントロールにフォーカスを移動し、キーを使用してフォームを `Tab` `Enter` 送信できます。

キーボード ユーザーの Web ページの使いやすさは、次の方法でテストできます。
*  キーボード、特に 、、 `Tab` および `Shift` + `Tab` キーを使用 `Enter` します。  この方法については、この記事で説明します。
*  [検査] ツールを使用して、個々の要素のキーボードサポートを **確認** します。  [検査] ツールの情報オーバーレイには、 **キーボード** フォーカス可能な行を含むアクセシビリティ **セクションが含** まれます。  
*  キーボード サポート **の問題** については、[問題] レポート **の [アクセシビリティ** ] セクションを確認します。

マウスではなくキーボードを使用してデモ ページでアクセシビリティの問題を確認するには、次の手順を実行します。

1.  ブラウザーの [新しいタブで][DevToolsA11yErrorsDemopage] アクセシビリティ テストデモ Web ページを開きます。

1.  キーボードを使用してデモ ドキュメントを移動し、キーを使用して要素から `Tab` `Shift` + `Tab` 要素に移動します。  デモ Web ページで、キー `Tab` が最初にセクション内の検索フォームにフォーカスを移動 `header` します。

1.  ボタン `Tab` にフォーカスを置く場合は選択し、フォーカス `Enter` されたボタンをクリックします。  たとえば、デモ ページで[検索] フィールドにフォーカスを置くを選択し、検索を送信 `Tab` **** `Enter` するを選択します。  この方法では、移動ボタンを選択した場合と同じ結果 **が得** られます。  [検索 `Enter` ] フォームの送信を **選択すると** 、正しく動作します。

1.  もう一 `Tab` 度選択します。  フォーカスを置く次の要素は、アウトライン**** で示されている Web ページのセクションの最初の [その他] `content` リンクです。
    
    :::image type="complex" source="../media/a11y-testing-keyboard-focus-on-element.msft.png" alt-text="キーボードと 'Tab' キーを使用してドキュメントを移動します。 ドキュメント内のリンクにフォーカスが表示されます。" lightbox="../media/a11y-testing-keyboard-focus-on-element.msft.png":::
        キーボードとタブ キーを使用してドキュメントを移動する。 ドキュメント内のリンクにフォーカスが表示されます。
    :::image-end:::
    
1.  最後 `Tab` の [その他] リンクを渡すまで、さらに数回 **選択** します。  ページが上にスクロールし、ページの要素に表示されているように見えるが、どの要素かを知る方法はありません。

1.  左下の URL に注意してください。  画面の左下を見た場合 (またはスクリーン リーダーを使用する場合) は、ブラウザーに Cats リンクがポイントする URL **** `#cats` () が表示されるので、青いリンクを含むサイドバー ナビゲーション メニューに表示されます。

    :::image type="complex" source="../media/a11y-testing-lack-of-focus-style.msft.png" alt-text="フォーカス スタイルが不足すると、現在ドキュメントのどこにいるかはわかりません。 唯一のヒントは、画面の左下隅にリンク ターゲットが表示される場合です。" lightbox="../media/a11y-testing-lack-of-focus-style.msft.png":::
        フォーカス スタイルが不足すると、現在ドキュメントのどこにいるかはわかりません。 唯一のヒントは、画面の左下隅にリンク ターゲットを表示します。
    :::image-end:::

1.  もう `Tab` 一度選択して、寄付フォームの入力フィールドにアクセスします。  ただし、 を選択すると、テキスト ボックスの上のボタンにアクセスできない `Tab` 。 キーボードを使用して **、50、100、または** **** **200**のボタンにフォーカスを置いて選択することはできません。  また、選択 `Enter` しても、寄付フォームは送信されます。

    :::image type="complex" source="../media/a11y-testing-form-field-with-outline.msft.png" alt-text="寄附フォームのキーボードアクセス可能な要素は、テキスト入力フィールドのみです。" lightbox="../media/a11y-testing-form-field-with-outline.msft.png":::
        寄附フォームのキーボードアクセス可能な要素は、テキスト入力フィールドのみです。
    :::image-end:::
    
1.  もう一度選択すると、ページの上部のナビゲーション バーにフォーカスが置き、ホーム 、Adopt `Tab` a **** **Pet、Donate、Jobs、** および About Us**** のメニュー ボタンが**表示されます**。 ****  フォーカス `Tab` の `Shift` + アウトラインで示されているメニュー ボタンにフォーカスを置くまたは `Tab` 選択します。  次に `Enter` 、Web ページのそのセクションにアクセスする場合に選択します。

    :::image type="complex" source="../media/a11y-testing-menu-with-outline.msft.png" alt-text="メイン メニューには強調表示とフォーカスアウトラインが表示され、キーボードにアクセスできます。" lightbox="../media/a11y-testing-menu-with-outline.msft.png":::
        メイン メニューには強調表示とフォーカスアウトラインが表示され、キーボードにアクセスできます。
    :::image-end:::
    
上記のチュートリアルに基づいて、修正が必要な次の問題が見つかりました。

*  キーボードを使用する場合、サイドバーナビゲーション メニューの青いリンクは、フォーカスがあるリンクを視覚的に示す必要があります。  詳細については、「サイドバー メニューのキーボード フォーカスの表示不足を分析 [する」に移動します](test-analyze-no-focus-indicator.md)。

*  寄付フォームでは、金額ボタンと [寄付] **ボタンは** キーボードでは機能しません。  詳細については、「フォームでのキーボードサポートの不足 [を分析する」に移動します](test-analyze-no-keyboard-support.md)。

*  ページのセクションを通じたキーボード アクセスの順序が正しくありません。  サイドバーのナビゲーション メニュー **に移動する** 前に、ドキュメント内のすべての [その他] リンクを移動します。  キーがサイドバーのナビゲーション メニューにフォーカスを置くまでには、すべてのページ コンテンツ `Tab` が既に走査されています。 サイドバーのナビゲーション メニューは、ページ コンテンツに簡単にアクセスできるように意図されています。  この問題を解決する方法の詳細については、「ソース オーダー ビューアーを使用してキーボード [サポートをテストする」に移動します](test-tab-key-source-order-viewer.md)。


## <a name="see-also"></a>関連項目

*  [DevTools を使用したアクセシビリティ テストの概要](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "アクセシビリティテストのデモ web ページ |GitHub"
