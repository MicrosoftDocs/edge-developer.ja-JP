---
description: ページ上の [検査] ツールの情報オーバーレイを使用して、既定の状態でテキストの色のコントラストを確認します。このオーバーレイには、コントラスト情報を含むアクセシビリティ セクションがあります。
title: 検査ツールを使用して既定の状態でテキストの色のコントラストを確認する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: ade9fd6d685f6f7cea6311b1645a527ece352a38
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597494"
---
# <a name="check-text-color-contrast-in-the-default-state-using-the-inspect-tool"></a>検査ツールを使用して既定の状態でテキストの色のコントラストを確認する

<!-- Inspect tool: information overlay: Accessibility section: Contrast row -->

[検査] ツールを使用して、既定の状態でテキストの色のコントラスト **を確認** します。  Web**ページ上**の検査ツールの情報オーバーレイには、コントラスト情報を含む**アクセシビリティ****セクションがあります**。

[検査] ツールの情報オーバーレイを使用して既定の状態のテキストと色のコントラストを確認するには、次の手順を実行します。

<!-- Inspect tool -->
テキストを含む要素の場合、 **検査** ツールの情報オーバーレイには次の情報が表示されます。
*  テキストと背景色のコントラスト比。
*  十分なコントラストを持つ要素の緑色のチェック マーク アイコン。
*  コントラストが十分ではない要素の黄色の警告アイコン。

場合によっては、ブラウザーを明るいテーマまたは暗いテーマに設定すると、コントラストが影響を受ける場合があります。

例として、デモ ページでは、サイドバー ナビゲーション メニューの青いリンクのコントラストは十分ですが、[寄附金の**** 状態] セクションの緑色の **[犬**] リンクには十分なコントラストが含めではありません。  次のように、検査ツールを **使用して** これらの要素を確認します。

1.  アクセシビリティ テスト [のデモ Web ページを新しい][DevToolsA11yErrorsDemopage] タブで開きます。 次に **、[F12] を** 選択して DevTools を開きます。

1.  DevTools **の左上** 隅にある [検査] ボタン \( Inspect button \) ボタンを選択して、アイコンが強調表示 ![ (青) ](../media/inspect-icon.msft.png) にします。

1.  レンダリングされた Web ページで、サイドバー ナビゲーション メニューの青い **Cats** リンクにカーソルを合わせる。  [ **検査]** ツールの情報オーバーレイが表示されます。  情報オーバーレイ **の [アクセシビリティ** ] セクションで、緑のチェックマークが **[** コントラスト] 行に表示され、この要素のテキストの色と背景色のコントラストが十分であることを示します。

    :::image type="complex" source="../media/a11y-testing-enough-contrast.msft.png" alt-text="[検査] ツールに示すように、メニュー項目には十分なコントラストがあります。" lightbox="../media/a11y-testing-enough-contrast.msft.png":::
        [検査] ツールに示すように、メニュー項目には十分なコントラストがあります。
    :::image-end:::

1.  レンダリングされた Web ページの [寄附状況] **セクション** で、[犬] リンクの上に **マウス ポインターを合** わせる。  [**検査**] ツールの情報オーバーレイには、コントラスト行にオレンジ色**** の感嘆符が表示され、この要素にはテキストと背景色のコントラストが十分に存在しないという点が示されます。

    :::image type="complex" source="../media/a11y-testing-not-enough-contrast.msft.png" alt-text="検査ツールの警告に示すように、コントラストが十分ではない要素" lightbox="../media/a11y-testing-not-enough-contrast.msft.png":::
        検査ツールの警告に示すように、コントラストが十分ではない要素
    :::image-end:::


## <a name="different-options-to-inspect-text-color-contrast-in-devtools"></a>DevTools でテキストと色のコントラストを検査するためのさまざまなオプション

テキストの色のコントラストを調するには、次の DevTools 機能を使用します。

*  [検査 **] ツール** (Web ページ上の情報オーバーレイとして) を使用して、個々のページ要素に十分なテキストと色のコントラストが設定されているかどうかを確認します。  検査 **ツール** の情報オーバーレイには、 **コントラスト情報行** を含むアクセシビリティ **セクションが** 含まれます。  [ **検査] ツール** には、現在の状態のテキストコントラスト情報だけが表示されます。  この方法については、現在の記事で説明します。

*  テキスト **と背景色** のコントラストが十分ではない場合、Issues ツールは Web ページ全体の色コントラストの問題を自動的に報告します。  この方法については、「テキストの色 [に十分なコントラストが含まれるか確認する」を参照してください](test-issues-tool.md#verify-that-text-colors-have-enough-contrast)。

*  「要素のすべての状態のアクセシビリティを確認する」で説明されているスタイル ウィンドウで Toggle Element State を使用して、状態などの既定以外の状態 `hover` [をエミュレートします](test-inspect-states.md)。 **** ****


## <a name="see-also"></a>関連項目

*  [要素のすべての状態のアクセシビリティを確認する][DevtoolsAccessibilityTestInspectStates]
*  [[検査] ツールを使用して、Web ページの上にカーソルを移動してアクセシビリティの問題を検出する](test-inspect-tool.md)
*  [DevTools を使用したアクセシビリティ テストの概要](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevtoolsAccessibilityTestInspectStates]: test-inspect-states.md "要素のすべての状態のアクセシビリティを確認|Microsoft Docs"
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "アクセシビリティテストのデモ web ページ |GitHub"
