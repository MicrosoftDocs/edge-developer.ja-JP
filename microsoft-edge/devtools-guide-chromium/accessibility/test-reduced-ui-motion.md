---
description: '[レンダリング] ツールの [CSS メディアのエミュレート] 機能を使用して、UI アニメーションがオフ (縮小モーション) で Web ページが使用可能になっていることを確認します。'
title: ページが UI アニメーションをオフにした状態で使用できる状態になっていることを確認する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: ec30925b706b4b1c6dfaaa6ce66a38fab8759ac2
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597495"
---
# <a name="verify-that-the-page-is-usable-with-ui-animation-turned-off"></a>ページが UI アニメーションをオフにした状態で使用できる状態になっていることを確認する

Web ページは、オペレーティング システムでアニメーションをオフにしたユーザーにアニメーションを表示しない必要があります。  アニメーションは、製品の使いやすさに役立ちますが、気晴らし、混乱、または吐き気を引き起こす可能性があります。

Web ページが UI アニメーションをオフ (縮小モーション) で使用できる**** 状態にすることを確認するには、レンダリング ツールで **、[CSS**メディアのエミュレート] 機能を使用して、低モーションを優先するドロップダウン リストを使用します。

アクセシビリティ テストのデモ Web ページで、オペレーティング システムでアニメーションをオフにしたり、DevTools を使用してその設定をエミュレートしたりすると、サイドバー ナビゲーション メニューのリンクを選択しても、Web ページはスムーズなスクロールを使用しない。  これは、メディア クエリで CSS の滑らかなスクロール設定をラップし、レンダリング ツールを使用**** して縮小されたアニメーションのオペレーティング システム設定をエミュレートすることによって実現されます。

アニメーションをオフにした状態でページが使用できるかどうかを確認するには、次の方法を実行します。

1.  ブラウザーの [新しいタブでアクセシビリティ テストデモ Web][DevToolsA11yErrorsDemopage] ページを開き **、F12** を選択して DevTools を開きます。

1.  DevTools の上部で [ソース****] ツールを選択し、左側**** の [ナビゲーション] ウィンドウで [ `styles.css` .  CSS ファイルが [エディター] ウィンドウ **に表示** されます。

1.  macOS**で Ctrl + F** Windows/Linux または Command + **F**を選択し、 と入力します `@media` 。  次の CSS メディア クエリが表示され、Web ページで使用されます。

    ```css
    @media (prefers-reduced-motion: no-preference) {
      html {
        scroll-behavior: smooth;
      }
    }
    ```

    次に、次のように、オペレーティング システム設定をエミュレートしてアニメーションを削減します。

1.  **[Esc] を**選択して、DevTools の下部にあるドロワーを開きます。  ドロワー **の上部にある** [その他のツール ( )] ボタンを選択してツールの一覧を表示し、[レンダリング **+** ] を **選択します**。  

1.  [CSS メディア **のエミュレート] 機能で、[** 縮小モーションを優先する] ドロップダウン リストで、[優先する縮小モーション: 縮小] **を選択します**。

    :::image type="complex" source="../media/a11y-testing-simulating-reduced-motion.msft.png" alt-text="縮小されたモーションと、ユーザーが必要なときにのみスムーズなスクロールが実行される CSS をシミュレートする" lightbox="../media/a11y-testing-simulating-reduced-motion.msft.png":::
        縮小されたモーションと、ユーザーが必要なときにのみスムーズなスクロールが実行される CSS をシミュレートする
    :::image-end:::

1.  Web ページで、馬やアルパカスなどの青**いメニュー****項目を選択します**。  これで、スムーズスクロールアニメーションを使用するのではなく、選択したセクションまで Web ページが即座にスクロールします。

1.  [レンダリング]**ツールの**[CSS メディア機能の**エミュレート優先**縮小]**** の下で、[エミュレーションなし] を選択してこの設定を削除します。
   
デモ Web ページでは、上記のメディア クエリとエミュレーション設定を使用しても、次のアニメーションが実行されます。 Web 製品を構築する場合は、同様のすべてのアニメーションを修正してください。  
*  青いメニュー項目の上にマウス ポインターを置くと、その項目のアニメーションが表示されます。
*  その上にマウス ポインターを置くと、 **その他** のリンク上の円のアニメーションが表示されます。



## <a name="see-also"></a>関連項目

*  [モーション シミュレーションの削減](reduced-motion-simulation.md)
*  [DevTools を使用したアクセシビリティ テストの概要](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "アクセシビリティテストのデモ web ページ |GitHub"
