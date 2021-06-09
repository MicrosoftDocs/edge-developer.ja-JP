---
description: レンダリング ツールの \"エミュレート CSS メディア機能 prefers-color-scheme\" ドロップダウン リストを使用して、ダーク テーマとライト テーマ (ダーク モードとライト モード) のコントラストの問題を確認します。
title: 暗いテーマと明るいテーマのコントラストの問題を確認する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 052c75b610ec872329f387e46819867f299a8ca9
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597528"
---
# <a name="check-for-contrast-issues-with-dark-theme-and-light-theme"></a>暗いテーマと明るいテーマのコントラストの問題を確認する

<!-- Rendering tool: Emulate CSS media feature prefers-color-scheme -->

色のアクセシビリティをテストする場合、コントラストの問題をテストする必要があるさまざまな表示色のテーマがある可能性があります。

ほとんどのオペレーティング システムには、ダーク モードとライト モードが用意されています。  WEB ページは、CSS メディア クエリを使用して、このオペレーティング システム設定に対応できます。  これらのテーマをテストし、レンダリング ツールの CSS オプションを使用して、オペレーティング システム設定を変更せずに CSS メディア クエリ `prefers-color-scheme` **をテスト** できます。

例として、アクセシビリティテストのデモ ページには、明るいテーマと暗いテーマが含まれています。  デモ ページは、オペレーティング システムから暗いテーマまたは明るいテーマ設定を継承します。  DevTools を使用して、ライト スキームに設定されているオペレーティング システムをシミュレートし、デモ Web ページを更新すると **、Issues** ツールには 2 つの代わりに 6 つの色コントラストの問題が表示されます。  (別の番号が表示される場合があります)。


優先する色テーマのユーザーの選択をエミュレートするには、次の方法を実行します。

1.  ブラウザーの [新しいタブでアクセシビリティ テストデモ Web][DevToolsA11yErrorsDemopage] ページを開き **、F12** を選択して DevTools を開きます。

1.  **[Esc] を**選択して、DevTools の下部にあるドロワーを開きます。  ドロワー **+** の上部にあるアイコンを選択してツールの一覧を表示し、[レンダリング] を **選択します**。  レンダリング ツールが表示されます。

1.  [CSS メディア **のエミュレート] 機能の [** 優先する配色] ドロップダウン リストで、[優先する配色: 明るい **] を選択します**。      Web ページは、 を使用して再レンダリングされます `light-theme.css` 。


    :::image type="complex" source="../media/a11y-testing-simulating-light-mode.msft.png" alt-text="レンダリング ツールを使用してライト モードをシミュレートし、ドキュメントの他のテーマをトリガーする" lightbox="../media/a11y-testing-simulating-light-mode.msft.png":::
        レンダリング ツールを使用してライト モードをシミュレートし、ドキュメントの他のテーマをトリガーする
    :::image-end:::


1.  [問題 **] ツールを選択** し、[アクセシビリティ] **セクションを展開** します。  さまざまな要因に応じて、警告が `Insufficient color contrast` 表示される場合があります。 「影響を **受けるリソース」には** 、色のコントラストが不十分な 6 つの要素があります。
    
    :::image type="complex" source="../media/a11y-testing-new-contrast-issues-in-light-mode.msft.png" alt-text="光のテーマが変更されたため、新しいコントラストの問題が検出されました" lightbox="../media/a11y-testing-new-contrast-issues-in-light-mode.msft.png":::
        光のテーマが変更されたため、新しいコントラストの問題が検出されました
    :::image-end:::
    
    デモ ページでは、ページの **[寄** 附状況] セクションはライト モードでは読み取り不能であり、変更する必要があります。 
    
    :::image type="complex" source="../media/a11y-testing-donation-state-light-contrast.msft.png" alt-text="[寄附状況] セクションには、光モードでのコントラストの問題があります。" lightbox="../media/a11y-testing-donation-state-light-contrast.msft.png":::
        [ **寄附状況]** セクションには、光モードでのコントラストの問題があります。
    :::image-end:::
    
1.  DevTools で[要素****] ツールを選択し****、macOS の [Windows/Linux] または [Command+ **F]** の順に選択します。  HTML **** DOM ツリー内で検索する [検索] テキスト ボックスが表示されます。
 
1.  を `scheme` 入力します。  次の CSS メディア クエリが見つかり、対応する CSS ファイルを更新できます。

    ```html
    <link rel="stylesheet" href="css/light-theme.css" media="(prefers-color-scheme: light), (prefers-color-scheme: no-preference)">
    <link rel="stylesheet" href="css/dark-theme.css" media="(prefers-color-scheme: dark)">
    ```


## <a name="see-also"></a>関連項目

*  [暗いまたは明るい配色のシミュレーション][DevToolsColorSchemeSimulation]
*  [DevTools を使用したアクセシビリティ テストの概要](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsColorSchemeSimulation]: ./preferred-color-scheme-simulation.md "暗いまたは明るい配色のシミュレーション |Microsoft Docs"
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "アクセシビリティテストのデモ web ページ |GitHub"
