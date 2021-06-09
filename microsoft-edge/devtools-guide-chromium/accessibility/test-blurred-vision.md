---
description: Web ページがぼやけたビジョンで使用できると確認するには、[レンダリング] ツールで [エミュレートビジョンの欠陥] ドロップダウン リストを使用します。
title: ページがぼやけたビジョンで使用できると確認する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 2fc1a1cf7746591573fce07946c7fb11abf42705
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597531"
---
# <a name="verify-that-the-page-is-usable-with-blurred-vision"></a>ページがぼやけたビジョンで使用できると確認する

<!-- Rendering tool: Emulate vision deficiencies: Blurred vision -->

ぼやけたビジョンをシミュレートするには、[ **レンダリング] ツールの [** ビジョンの不備をエミュレート **する] メニューを使用** します。  デモ Web ページでこの機能を使用すると、上部メニューのテキストのドロップ シャドウによって、メニュー項目の読み取りが難しい場合があります。

ぼやけたビジョンで Web ページが使用できるかどうかを確認するには、次の方法を実行します。

1.  ブラウザーの [新しいタブでアクセシビリティ テストデモ Web][DevToolsA11yErrorsDemopage] ページを開き **、F12** を選択して DevTools を開きます。

1.  **[Esc] を**選択して、DevTools の下部にあるドロワーを開きます。  ドロワー **+** の上部にあるアイコンを選択してツールの一覧を表示し、[レンダリング] を **選択します**。  

1.  [ビジョン **の不備をエミュレートする] ドロップダウン** リストで、[ぼ **やけたビジョン] を選択します**。

    :::image type="complex" source="../media/a11y-testing-simulating-blur.msft.png" alt-text="ぼやけたページをシミュレートする" lightbox="../media/a11y-testing-simulating-blur.msft.png":::
        ぼやけたページをシミュレートする
    :::image-end:::

    CSS プロパティ `text-shadow` を使用すると、メニュー項目のテキストが上部メニューで読みにくくなっている点に注意してください。 たとえば、「ホーム **」、「Pet**を採用 **する」、** その他のメニュー項目を確認します。
    
1.  レンダリング ツール**の [エミュレート**ビジョンの欠陥]******で**、[エミュレーションなし] を選択して、ぼやけたビジョン シミュレーションを削除します。


## <a name="see-also"></a>関連項目

*  [視覚欠陥をエミュレートする](emulate-vision-deficiencies.md)
*  [DevTools を使用したアクセシビリティ テストの概要](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "アクセシビリティテストのデモ web ページ |GitHub"
