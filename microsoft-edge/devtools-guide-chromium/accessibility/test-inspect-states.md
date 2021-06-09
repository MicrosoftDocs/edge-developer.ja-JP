---
description: '[要素の状態の切り替え] を使用して、[スタイル] ウィンドウで、ホバー状態の間のテキストのコントラストなど、要素のすべての状態のアクセシビリティを検査します。'
title: 要素のすべての状態のアクセシビリティを確認する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 129a89f94925de24a4e649bd91f513de031d6b4a
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597524"
---
# <a name="verify-accessibility-of-all-states-of-elements"></a>要素のすべての状態のアクセシビリティを確認する

<!-- 5. STYLES: TOGGLE STATE -->

状態中のテキストの色のコントラストなど、要素のすべての状態のアクセシビリティを確認 `hover` します。  検査 **ツールは** 、一度に 1 つの状態のアクセシビリティの問題を報告します。  要素のさまざまな状態のアクセシビリティを確認するには、[スタイル] タブ**** で、この記事で説明するように**\:hov** (**Toggle Element State**) を選択します。 まず、[検査] ツールを使用して状態**** シミュレーションが必要な理由を示し、次に状態シミュレーションの使い方を示します。


## <a name="checking-text-color-contrast-in-the-default-state"></a>既定の状態でテキストの色のコントラストを確認する

<!-- Inspect tool: information overlay: Accessibility section: Contrast row -->

[問題] ツールの色コントラストの自動テスト**** に加えて、[検査] ツールを**** 使用して、個々のページ要素のコントラストが十分かどうかを確認することもできます。  コントラスト情報を使用できる場合は、[ **検査** ] オーバーレイにコントラスト比とチェック ボックス項目が表示されます。  緑色のチェック マーク アイコンは十分なコントラストを示し、黄色の警告アイコンはコントラストが十分でなかったと示します。

たとえば、サイドバーのナビゲーション メニューのリンクには十分なコントラストがあります。  ただし、[寄附金**の**状態] セクションの緑色の **[** 犬] リスト アイテムには十分なコントラストが存在しないので、[検査] オーバーレイで警告が**表示されます。**

:::row:::
    :::column:::
        :::image type="complex" source="../media/a11y-testing-enough-contrast.msft.png" alt-text="[検査] オーバーレイに示すように、サイドバー ナビゲーション メニューのリンクには十分なコントラストがあります。" lightbox="../media/a11y-testing-enough-contrast.msft.png":::
            [検査] オーバーレイに示すように、サイドバー ナビゲーション メニューのリンクには十分なコントラスト **があります** 。 :::image-end:::
    :::column-end:::
    :::column:::
        :::image type="complex" source="../media/a11y-testing-not-enough-contrast.msft.png" alt-text="十分なコントラストを持つ要素は、Inspect オーバーレイの警告によってフラグが設定されます。" lightbox="../media/a11y-testing-not-enough-contrast.msft.png":::
            十分なコントラストを持つ要素は、Inspect オーバーレイの警告によって **フラグが設定** されます。 :::image-end:::
    :::column-end:::
:::row-end:::
        

## <a name="hovering-when-the-inspect-tool-is-active-doesnt-show-the-text-color-contrast-for-the-hover-state"></a>[検査] ツールがアクティブなときにホバーしても、ホバー状態のテキストと色のコントラストが表示される

検査 **ツールの** 情報オーバーレイは、1 つの状態のみを表します。  ページ上の要素の状態は異なる場合があります。そのすべてがテストする必要があります。  たとえば、アクセシビリティ テストデモ ページのメニューの上にマウス ポインターを置くと、色を変更するアニメーションが表示されます。 次の手順を実行します。

1.  アクセシビリティ テスト [のデモ Web ページを新しい][DevToolsA11yErrorsDemopage] タブで開きます。

1.  サイドバーのナビゲーション メニューの青いメニュー項目にカーソルを合わせる。  各アイテムにアニメーションが含めら注意してください。

    :::image type="complex" source="../media/a11y-testing-hover.msft.png" alt-text="マウス ポインターがマウス ポインターの上にあるとき、異なる色を示すメニュー項目" lightbox="../media/a11y-testing-hover.msft.png":::
        マウス ポインターがマウス ポインターの上にあるとき、異なる色を示すメニュー項目
    :::image-end:::
    
次に、[検査] ツールを使用します。 [検査] ツールを使用すると、メニュー項目の上にマウス ポインターを置くと、メニュー項目のアニメーションは実行されません。  [検査] ツールを使用すると、スタイルの状態がトリガーされないので、コントラスト比をテストするためにメニュー項目の状態に `hover` `hover` 到達できない。  
    
アニメーションが実行されていないことを確認するには、次の手順を実行します。
    
1.  DevTools **の左上隅** にある [検査] ボタン \( [検査] ボタン \) を選択して、アイコンが ![ 強調表示 (青) ](../media/inspect-icon.msft.png) にします。

1.  サイドバーのナビゲーション メニューの青いリンクにカーソルを合わせる。  メニュー項目のアニメーションは実行されません。 代わりに、メニュー項目は、flexbox オーバーレイの色と強調表示を使用して表示されます。

ページ上の要素の状態が異なる可能性があるため、十分なテキストのコントラストを確認するには、この方法では十分ではありません。


## <a name="use-state-simulation-to-simulate-the-hover-state-of-an-animated-menu-item"></a>状態シミュレーションを使用して、アニメーションメニュー項目のホバー状態をシミュレートする 

<!-- Elements tool: Styles pane: Toggle Element State -->

[検査 **]** ツールがアクティブな場合は、アニメーション要素の上にカーソルを置く代わりに、メニュー項目の状態をシミュレートする必要があります。  メニュー 項目の状態をシミュレートするには、[スタイル] ウィンドウの状態シミュレーション **を使用** します。  [ **スタイル]** ウィンドウには **\:hov** (**要素**の状態の切り替え) ボタンが表示され、Force 要素の状態というラベルが付いたチェック ボックスのグループ **が表示されます**。

[検査] ツールを使用している間にホバー状態を有効にする方法は次の方法です。

1.  まだ開いていない場合は、アクセシビリティ テストのデモ Web ページを [新しいタブ][DevToolsA11yErrorsDemopage] で開きます。 次に **、[F12] を** 選択して DevTools を開きます。

1.  DevTools **の左上隅** にある [ツールの検査] ボタン \( Inspect tool button \) を選択して、アイコンが強調表示 ![ ](../media/inspect-icon.msft.png) (青) にします。

1.  表示された Web ページで、サイドバーのナビゲーション メニューで青い **Cats** リンクを選択します。  要素 **ツールが** 開き、要素が `<a href="#cats">Cats</a>` 選択されます。

    :::image type="complex" source="../media/a11y-testing-inspecting-link-to-hover.msft.png" alt-text="要素ツールでホバー状態を持つ要素を検査する" lightbox="../media/a11y-testing-inspecting-link-to-hover.msft.png":::
        要素ツールでホバー状態を持つ要素を検査する
    :::image-end:::

1.  [スタイル] **タブを選択** します。 選択した要素には、CSS に適用される状態がありますが、[スタイル] ウィンドウ `a` `hover` には **表示** されません。 

1.  [スタイル **] ウィンドウ** で、スタイル ルールの右側にある `#sidebar nav li a` リンクを選択 `styles.css` します。  [ **ソース] ツールが** 開きます。  次に、CSS 擬似クラス ルールを検索します `#sidebar nav li a:hover` 。  このルールは、検査ツールがアクティブ **な場合** は実行されません。  次の手順で、この状態ルールの実行をシミュレートします。

1.  [要素] **ツールを** 選択します。  次に、[スタイル] **ウィンドウ** で **、[:hov] (** 要素の状態の切り替え)**ボタンを**選択します。  チェック **ボックスの Force 要素** の状態グループが表示されます。

    :::image type="complex" source="../media/a11y-testing-state-simulation.msft.png" alt-text="すべてのオプションを表示する状態シミュレーション ツール" lightbox="../media/a11y-testing-state-simulation.msft.png":::
        すべてのオプションを表示する状態シミュレーション ツール
    :::image-end:::

1.  **[:hover] チェック ボックスを**オンにします。  DOM では、要素の左側に黄色のドットが表示され、要素がシミュレートされた状態 `<a href="#cats">Cats</a>` であることを示します。  [ **キャッツ** ] メニュー項目が、ポインターをホバーした場合と同様に Web ページに表示されます。  メニュー項目のアニメーションが実行される可能性があります。

    :::image type="complex" source="../media/a11y-testing-hover-simulated.msft.png" alt-text="ホバー状態をシミュレートする DevTools" lightbox="../media/a11y-testing-hover-simulated.msft.png":::
        ホバー状態をシミュレートする DevTools
    :::image-end:::

    シミュレートされた状態を適用した後、次のように、もう**** 一度[検査] ツールを使用して、ユーザーが上にカーソルを置いた場合の要素のコントラストを確認できます。

1.  DevTools **の左上隅** にある [検査] \( Inspector icon \) ボタンを選択して、アイコンが強調表示 ![ ](../media/inspect-icon.msft.png) (青) にします。

1.  サイドバーのナビゲーション メニューの青 **い Cats** リンクの上にカーソルを合わせる。  シミュレートされたホバー アニメーションのため、リンクは薄い青色になります。  [**検査]** ツールの情報オーバーレイが表示され、[コントラスト] 行にオレンジ**** 色の感嘆符が表示され、コントラストが十分に高くなかったことを示します。

    :::image type="complex" source="../media/a11y-testing-hover-contrast-testing.msft.png" alt-text="シミュレートされたホバー状態の要素のコントラストをテストする" lightbox="../media/a11y-testing-hover-contrast-testing.msft.png":::
        シミュレートされたホバー状態の要素のコントラストをテストする
    :::image-end:::

状態シミュレーションは、キーボード ユーザーのニーズなど、さまざまなユーザー ニーズを考慮したかどうかを確認する場合にも便利です。  Force 要素の **状態チェック** ボックスを使用すると、状態をシミュレートして、フォーカスがあるときに UI が変更されていない `:focus` 状態を検出できます。 要素にフォーカスがある場合のインジケーターの不足は問題です。


## <a name="see-also"></a>関連項目

*  [DevTools を使用したアクセシビリティ テストの概要](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "アクセシビリティテストのデモ web ページ |GitHub"
