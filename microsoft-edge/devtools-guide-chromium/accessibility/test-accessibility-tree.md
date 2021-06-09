---
description: アクセシビリティ ツリーでキーボードとスクリーン リーダーのサポートを確認します。
title: キーボードとスクリーン リーダーのサポートについては、アクセシビリティ ツリーを確認してください。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 0ab5e5609485505d1ad5fa6e2fffced9af25edcb
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597543"
---
# <a name="check-the-accessibility-tree-for-keyboard-and-screen-reader-support"></a>キーボードとスクリーン リーダーのサポートについては、アクセシビリティ ツリーを確認してください。

<!-- Accessibility tab: Accessibility Tree -->

いくつかの DevTools 機能は、キーボードとスクリーン リーダーのサポートをチェックします。  検査ツール **を使用** して各ページ要素のアクセシビリティを個別に確認すると、かなり時間がかかる場合があります。  Web ページを確認する別の方法は、アクセシビリティ ツリー **を使用する方法です**。  アクセシビリティ **ツリーは、** ページがスクリーン リーダーなどの支援テクノロジに提供する情報を示します。

アクセシビリティ **ツリーは** DOM ツリーのサブセットであり、スクリーン リーダーにページの内容を表示する場合に役立つ DOM ツリーの要素を含む。  アクセシビリティ**ツリーは、[** 要素]**ツールの**[**** アクセシビリティ] タブ ([スタイル] タブの近く)**にあります**。


デモ ページでアクセシビリティ ツリーを使用して確認するには、次のコマンドを実行します。

1.  アクセシビリティ テスト [のデモ Web ページを新しい][DevToolsA11yErrorsDemopage] タブで開きます。 次に **、[F12] を** 選択して DevTools を開きます。

1.  DevTools **の左上隅** にある [検査] アイコン \( [検査] アイコン \) ボタンを選択して、ボタンが強調表示 ![ (青) ](../media/inspect-icon.msft.png) にします。

1.  レンダリングされた Web ページの [寄付]**セクションで****、[100] ボタンにカーソルを合**わせる。  [ **検査]** ツール オーバーレイが表示されます。

1.  レンダリングされた Web ページで **、[100] ボタンを選択** します。  DevTools では、[ **要素] ツール** が表示されます。  DOM ツリーには `div` **、100 ボタンの要素が表示** されます。  [ **スタイル]** ウィンドウには、要素の CSS 設定が表示されます。

1.  [スタイル] タブの **右側にある** [アクセシビリティ] **タブを選択** します。 要素 **のアクセシビリティ ツリー** が表示され、展開されます。

:::image type="complex" source="../media/a11y-testing-accessibility-tree.msft.png" alt-text="アクセシビリティ ツリー ツールの [寄附フォーム] ボタン" lightbox="../media/a11y-testing-accessibility-tree.msft.png":::
    アクセシビリティ ツリー ツールの [寄附フォーム] ボタン
:::image-end:::

名前を持たなかったり、(要素など) の役割を持つツリー内の要素は、キーボード ユーザーや支援テクノロジを使用しているユーザーが使用できないので、問題になります。 `generic` `div`


## <a name="see-also"></a>関連項目

*  [アクセシビリティ ツリーで要素の位置を表示する][DevtoolsAccessibilityAccessibilityTabViewTree]
*  [DevTools を使用したアクセシビリティ テストの概要](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevtoolsAccessibilityAccessibilityTabViewTree]: accessibility-tab.md#view-the-position-of-an-element-in-the-accessibility-tree "アクセシビリティ ツリーの要素の位置を表示する - [アクセシビリティ] タブを使用してアクセシビリティをテスト|Microsoft Docs"
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "アクセシビリティテストのデモ web ページ |GitHub"
