---
description: Web ページにカーソルを合わせると、アクセシビリティの問題を検出するには、[検査] ツールを使用します。
title: '[検査] ツールを使用して、Web ページの上にカーソルを移動してアクセシビリティの問題を検出する'
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: c95116d38e5b0bda88af43ef8bfde4204b8cb372
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597498"
---
# <a name="use-the-inspect-tool-to-detect-accessibility-issues-by-hovering-over-the-webpage"></a>[検査] ツールを使用して、Web ページの上にカーソルを移動してアクセシビリティの問題を検出する

[ **検査]** ツールは、レンダリングされた Web ページにカーソルを合わせると、アクセシビリティ情報を含む個々の要素に関する情報を表示します。
これに対し **、Issues ツールは** Web ページ全体の問題を自動的に報告します。

ツール **の** 検査ボタン \( ![ Inspect ](../media/inspect-icon.msft.png) \) は、DevTools の左上隅にあります。  [ツールの検査] **ボタンを** 選択すると、ボタンが青に変り、検査ツールがアクティブ **であることを** 示します。

[検査] **ツール** がアクティブな場合、レンダリングされた Web ページ上の任意の要素の上にホバーすると、[検査] オーバーレイが **表示** されます。 このオーバーレイには、その要素に関する一般的な情報とアクセシビリティ情報が表示されます。  [ **検査] オーバーレイの** [アクセシビリティ] **セクション** には、テキストの色のコントラスト、スクリーン リーダーのテキスト、キーボードのサポートに関する情報が表示されます。

:::image type="complex" source="../media/a11y-testing-basics-inspector-overlay.msft.png" alt-text="要素の領域をマルチカラー オーバーレイとして表示し、要素の詳細を大きな情報オーバーレイとして表示する検査ツール" lightbox="../media/a11y-testing-basics-inspector-overlay.msft.png":::
    要素 **の** 領域をマルチカラー オーバーレイとして表示し、要素の詳細を大きな情報オーバーレイとして表示する検査ツール
:::image-end:::


## <a name="check-individual-elements-for-text-contrast-screen-reader-text-and-keyboard-support"></a>テキストのコントラスト、スクリーン リーダーのテキスト、キーボードのサポートについて個々の要素を確認する

<!-- Inspect tool: Accessibility section of overlay -->

1.  ブラウザーの [新しいタブでアクセシビリティ テストデモ Web][DevToolsA11yErrorsDemopage] ページを開き **、F12** を選択して DevTools を開きます。

1.  アイコンが **強調表示** (青) の場合は、DevTools の左上隅にある [検査\( Inspect \) ] ![ ](../media/inspect-icon.msft.png) ボタンを選択します。

    :::image type="complex" source="../media/a11y-testing-basics-inspector.msft.png" alt-text="[検査] ツールを有効にする場合は、[検査] ボタン" lightbox="../media/a11y-testing-basics-inspector.msft.png":::
        [検査] ツールを **有効にする** 場合は、[ **検査]** ボタン
    :::image-end:::

1.  レンダリングされたデモ Web ページの任意の要素にカーソルを合わせる。  [ **検査]** ツールは、レンダリングされた Web ページ内の要素の下に情報オーバーレイを表示します。

    :::image type="complex" source="../media/a11y-testing-basics-inspector-overlay.msft.png" alt-text="要素のレイアウトをマルチカラー オーバーレイとして表示し、要素の詳細を大きな情報オーバーレイとして表示する検査ツール" lightbox="../media/a11y-testing-basics-inspector-overlay.msft.png":::
        要素 **の** レイアウトをマルチカラー オーバーレイとして表示し、要素の詳細を大きな情報オーバーレイとして表示する検査ツール
    :::image-end:::

Inspect オーバーレイの下部 **には、** 次の情報を含む **アクセシビリティ** セクションがあります。

*   **コントラスト** は、低ビジョンのユーザーが要素を理解できるかどうかを定義します。  [WCAG ガイドライン][WCAG]で定義されているコントラスト比は、十分なコントラスト (緑色のチェック マーク アイコン) または十分ではない (オレンジ色の感嘆符アイコン) かどうかを示します。 [][W3CContrastRatio]

*   **名前** と **役割は** 、スクリーン リーダーなどの支援テクノロジが要素について報告する機能です。
    *   Name **は** 、要素のテキスト コンテンツ `a` です。  要素の場合 `<a href="/">About Us</a>` 、 **検査ツールに** 表示される名前は "About Us" です。
    *   要素**の Role。**  これは、通常、要素名です `article` `img` 。、、 `link` `heading` などです。  要素 `div` と `span` を . と呼ばれます `generic` 。

*   **キーボードフォーカス可能は** 、ユーザーが入力デバイスに関係なく要素に到達できるかどうかを示します。
    *   緑色のチェック マーク アイコンは、要素がキーボードフォーカス可能な状態を示します。
    *   斜めの線が付く灰色の円は、要素がキーボードフォーカス可能でなかったかどうかを示します。


## <a name="additional-information-in-the-inspect-overlay"></a>[検査] オーバーレイの追加情報

<!-- general info about the Inspect tool, not particularly focused on accessibility -->

[ユーザー補助]**セクションの**上にある Inspect**** オーバーレイの上部には、要素の次の詳細が一覧表示されます。

*   レイアウトの種類。 要素が flexbox またはグリッドを使用して配置されている場合、アイコン \(![グリッド レイアウト アイコン](../media/grid-icon.msft.png)\) が表示されます。
*   要素の名前 (、 `h1` `h2` `div` など)。
*   要素のサイズをピクセル単位で指定します。
*   色見本 (または小さな色付き四角形) として、文字列 (など) としての色 `#336699` 。
*   サイズやフォント ファミリなどのフォント情報。
*   余白とパディング (ピクセル単位)。


## <a name="identify-nested-regions-using-color-highlighting"></a>色の強調表示を使用して入れ子になった領域を識別する 

<!-- general info about the Inspect tool, not particularly focused on accessibility -->

情報オーバーレイに加えて **、Inspect** ツールには、Elements ツールの DOM ツリーでのホバーに似た領域の色 **付けも提供** されます。

1.  ブラウザーの [新しいタブでアクセシビリティ テストデモ Web][DevToolsA11yErrorsDemopage] ページを開き **、F12** を選択して DevTools を開きます。

1.  DevTools **の左上** 隅にある [検査] ボタン \( Inspect tool icon \) を選択して、ボタンが強調表示 ![ (青) ](../media/inspect-icon.msft.png) にします。

1.  レンダリングされたデモ Web ページの別の部分にカーソルを合わせる。  Web ページ内の各要素が複数色のオーバーレイで表示されます。 この複数色のオーバーレイは、要素内の入れ子になった領域を表示できます。 たとえば、Cats の左余白にカーソルを **合わせるとします**。  [ **検査]** ツールは、さまざまな色で **[Cats]** セクションのいくつかの四角形の部分を強調表示し、Web ページの CSS フレックスボックス定義の結果として得られたレイアウトを示します。

:::image type="complex" source="../media/inspect-tool-flexbox-overlay.msft.png" alt-text="検査ツールを使用する場合のマルチカラー フレックスボックス オーバーレイと情報オーバーレイ" lightbox="../media/inspect-tool-flexbox-overlay.msft.png":::
    検査ツールを使用する場合のマルチカラー フレックスボックス オーバーレイと情報**オーバーレイ**
:::image-end:::

グリッド オーバーレイまたはフレックスボックス オーバーレイを構成するには、[ **要素** ] ツールで 、[レイアウト] タブ **を選択** します。 詳細については、「CSS グリッドの検査 [」に移動します](..\css\grid.md)。


## <a name="use-the-inspect-tool-to-hover-over-the-webpage-to-highlight-the-dom-and-css"></a>[検査] ツールを使用して Web ページにカーソルを合わせると、DOM と CSS が強調表示されます。

<!-- general info about the Inspect tool, not particularly focused on accessibility -->

1.  ブラウザーの [新しいタブでアクセシビリティ テストデモ Web][DevToolsA11yErrorsDemopage] ページを開き **、F12** を選択して DevTools を開きます。

1.  DevTools **の左上** 隅にある [検査] ボタン \( Inspect tool \) を選択して、ボタンが強調表示 ![ (青) ](../media/inspect-icon.msft.png) にします。

1.  [要素] **ツールを** 選択します。

1.  [検査 **] ツール** がアクティブな状態で、レンダリングされた Web ページの別の部分にカーソルを合わせる。  要素ツール **では** 、HTML DOM ツリーが自動的に展開され、カーソルを移動した要素に関する情報が表示されます。  ホバーしても、[スタイル] ウィンドウ **は** 更新されません。

1.  レンダリングされた Web ページ内の任意の要素を選択します。  要素 **ツールが** 自動的に開き、DOM ツリーに要素の HTML が表示されます。 ツールは、[スタイル] ウィンドウの要素に適用された CSS も **表示** します。  レンダリングされた Web ページで要素を選択すると、[検査] ツールが **オフ** になります。

:::image type="complex" source="../media/a11y-testing-basics-inspector-selected-element.msft.png" alt-text="選択した要素の詳細が [要素] ツールに表示されます。" lightbox="../media/a11y-testing-basics-inspector-selected-element.msft.png":::
    選択した要素の詳細が [要素] ツール **に表示** されます。
:::image-end:::

レンダリングされたページで要素を選択したら、[アクセシビリティ] タブ ([スタイル] タブの近**** く) を使用して**** アクセシビリティ ツリーを表示し、ソースオーダー ビューアーを**使用できます**。 ****


## <a name="see-also"></a>関連項目

*  [ノードの検査](../dom/index.md#inspect-a-node)
*  [検査ツールを使用して既定の状態でテキストの色のコントラストを確認する](test-inspect-text-contrast.md)
*  [DevTools を使用したアクセシビリティ テストの概要](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "アクセシビリティテストのデモ web ページ |GitHub"
[W3CContrastRatio]: https://www.w3.org/TR/WCAG21/#dfn-contrast-ratio "コントラスト比|W3C"
[WCAG]: https://www.w3.org/TR/WCAG21/ "Web コンテンツ アクセシビリティ ガイドライン |W3C"
