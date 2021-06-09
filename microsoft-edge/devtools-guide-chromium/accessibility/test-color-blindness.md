---
description: '[レンダリング] ツールの [エミュレートビジョンの欠陥] ドロップダウン リストを使用して、色覚を持つユーザーが Web ページを使用できる点を確認します。'
title: 色覚を持つユーザーがページを使用できると確認する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 54cd7230f0402bfeb4b5ee28d2bcd0947794676f
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597529"
---
# <a name="verify-that-the-page-is-usable-by-people-with-color-blindness"></a>色覚を持つユーザーがページを使用できると確認する

<!-- Rendering tool: Emulate vision deficiencies: Protanopia -->

色覚を持つユーザーが Web ページを使用できるのを確認**** するには、[レンダリング] ツールで 、[エミュレートビジョンの欠陥] ドロップダウン リスト**を**使用します。

アクセシビリティ テストのデモ Web ページでは、異なる寄付の状態で色が区別の唯一の手段として使用されます。
*  緑は、大量の寄付が受け取られたという意味です。
*  黄色は、中程度の量の寄付が受け取られたという意味です。
*  赤は、少ない量の寄付が受け取られたという意味です。

ただし、すべてのユーザーにこれらの色が意図した通り表示されるとは限らない。  レンダリング ツールの **[ビジョン**の不備**** をエミュレートする] 機能を使用すると、異なるビジョンを持つユーザーがデザインをどのように認識するのかシミュレーションすることで、このデザインが十分ではないと分かっています。


色覚を持つユーザーが Web ページを使用できるかどうかを確認するには、次の方法を実行します。

1.  ブラウザーの [新しいタブでアクセシビリティ テストデモ Web][DevToolsA11yErrorsDemopage] ページを開き **、F12** を選択して DevTools を開きます。

1.  **[Esc] を**選択して、DevTools の下部にあるドロワーを開きます。  ドロワー **+** の上部にあるアイコンを選択してツールの一覧を表示し、[レンダリング] を **選択します**。  

1.  [エミュレート **ビジョンの欠陥] ドロップダウン リスト** で **、[Protanopia] を選択します**。  _Protanopia は_ 赤色光に対する感度が低下し、緑、赤、黄色の区別が難しくなります。

    :::image type="complex" source="../media/a11y-testing-simulating-protanopia.msft.png" alt-text="protanopia を持つユーザーとしてドキュメントを表示すると、ドキュメントが表示されます" lightbox="../media/a11y-testing-simulating-protanopia.msft.png":::
        protanopia を持つユーザーとしてドキュメントを表示すると、ドキュメントが表示されます
    :::image-end:::
    
1.  [レンダリング **] ツールの** [ **ビジョンの不備をエミュレートする]** の下で、[エミュレーションなし] **を選択して** シミュレーションを削除します。


## <a name="see-also"></a>関連項目

*  [エミュレートビジョンの欠陥][DevToolsVisionDeficiencies]- Protanopia、Deuteranopia、Tritanopia、および Achromatopsia を含む、エミュレートビジョンの欠陥ドロップダウン リスト内のアイテムを定義します。 ****
*  [DevTools を使用したアクセシビリティ テストの概要](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsVisionDeficiencies]: ./emulate-vision-deficiencies.md "ビジョンの欠陥をエミュレート|Microsoft Docs"
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "アクセシビリティテストのデモ web ページ |GitHub"
