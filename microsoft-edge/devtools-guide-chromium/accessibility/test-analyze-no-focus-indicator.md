---
description: リンク上のフォーカス状態に対する CSS 擬似クラス ルールが欠けているので、サイドバー メニューでキーボード フォーカスが表示されなかっているのを分析し、リンクにアウトライン設定がないリンクを組み合わせたもの。
title: サイドバー メニューのキーボード フォーカスの表示不足を分析する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 3626de9bdc2cce266efafe4b1b2e8fff501a74f7
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597542"
---
# <a name="analyze-the-lack-of-indication-of-keyboard-focus-in-a-sidebar-menu"></a>サイドバー メニューのキーボード フォーカスの表示不足を分析する

<!-- Inspect tool, and CSS rules: pseudo-classes for states -->

アクセシビリティ テストのデモ ページでは、キーボードを使用する場合、青いリンクを含むサイドバー ナビゲーション メニューは、フォーカスのあるリンクを視覚的に示す必要があります。  サイドバー メニューがキーボード ユーザーにとってわかりにくい理由を確認するために、リンクアウトラインの CSS プロパティと共に、CSS 擬似クラスのルールを検索します `hover` `focus` 。  

この分析では、サイドバー ナビゲーション メニューのリンクにキーボード フォーカスが表示されるのが不十分な理由が分かっています。
*  リンク `a` には、 の CSS プロパティ設定 `outline: none` があります。
*  リンク `a` には、状態に対する CSS 擬似クラス ルール `:focus` が欠けている。

CSS に移動するには、[検査] ツールを**** 使用してサイドバー のナビゲーション メニューで青いリンクを強調表示し、そのリンクを定義する要素の DOM ツリーと CSS を `a` 表示します。

1.  ブラウザーの [新しいタブでアクセシビリティ テストデモ Web][DevToolsA11yErrorsDemopage] ページを開き **、F12** を選択して DevTools を開きます。

1.  DevTools **の左上隅** にある [検査] アイコン \( Inspect icon \) ボタンを選択して、ボタンが強調表示 ![ ](../media/inspect-icon.msft.png) (青) にします。

1.  サイドバーのナビゲーション メニューの青 **い Cats** リンクの上にカーソルを合わせる。  [検査] オーバーレイが表示され、要素が `a` キーボードフォーカス可能な状態を示します。  ただし、オーバーレイでは、リンクにフォーカスがある場合に視覚的な表示が表示されるというメッセージは表示されます。

    次に、このリンクの CSS スタイルを調します。
 
1.  サイドバーの **ナビゲーション メニュー** で [Cats] リンクを選択します。  [ **検査** ] ツールがオフにされ、[ **要素** ] ツールが開き、DOM ツリー内の `a` ノードが強調表示されます。

1.  [スタイル] **タブを選択** します。 CSS ルールが `#sidebar nav li a` 表示され、行番号へのリンクが表示されます `styles.css` 。

    :::image type="complex" source="../media/a11y-testing-menu-link.msft.png" alt-text="メニュー内のリンクのソース コードと適用されたスタイルの検査" lightbox="../media/a11y-testing-menu-link.msft.png":::
        メニュー内のリンクのソース コードと適用されたスタイルの検査
    :::image-end:::
    
1.  CSS ファイルへのリンクを選択します。  CSS ファイルがソース ツール **内で開** きます。

    :::image type="complex" source="../media/a11y-testing-menu-link-styles.msft.png" alt-text="ソース ツールのリンクに適用されるスタイル" lightbox="../media/a11y-testing-menu-link-styles.msft.png":::
        ソース ツールのリンクに適用されるスタイル
    :::image-end:::
    
ページのスタイルには、マウスを使用するときにどのメニュー項目をオンにしているかを示す状態の CSS 擬似クラス ルール `hover` があります `#sidebar nav li a:hover` 。  ただし、キーボードを使用するときにどのメニュー項目を表示する状態の CSS 擬似クラス ルール `focus` はありません `#sidebar nav li a:focus` 。など。

また、リンクには CSS プロパティ設定 `outline: none` が .  これは、キーボードを使用して要素にフォーカスを当てるときに、ブラウザーが自動的に要素に追加するアウトラインを削除する一般的な方法です。  スタイルを `focus` 使用しない場合は、ユーザーに混乱が生じます。


## <a name="see-also"></a>関連項目 

*  [フォーカスされている要素を追跡する](focus.md)
*  [DevTools を使用したアクセシビリティ テストの概要](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "アクセシビリティテストのデモ web ページ |GitHub"
