---
description: '[問題] ツールの [アクセシビリティ] セクションを使用して、アクセシビリティの問題について Web ページを自動的にテストします。'
title: アクセシビリティの問題について Web ページを自動的にテストする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 986a021d2fd390cd45bd53dcfc37a83d58ed2338
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597496"
---
# <a name="automatically-test-a-webpage-for-accessibility-issues"></a>アクセシビリティの問題について Web ページを自動的にテストする

[**問題]** ツールには****、[アクセシビリティ] セクションが含まれています。画像に代替テキストが見つからない、フォーム フィールドのラベルが見つからない、テキストの色のコントラストが不十分ななどの問題を自動的に報告します。  Issues **ツール** は **、DevTools** の下部にあるドロワー内にあります。  この記事では、アクセシビリティ テストのデモ Web ページを使用して、問題ツールの **[アクセシビリティ** ] セクションを **使用** します。

Issues ツールを開く方法は **次** のとおりです。
*  DevTools **の右上にある** [問題] カウンター ![ \( Issues counter ](../media/issues-counter-icon.msft.png) \) を選択します。
*  要素ツール **の DOM** ツリーで **、Shift キー** を押しながら要素の波線下線をクリックします。
*  [コマンド] **メニューで、** と `issues` 入力し、[問題の表示 **] を選択します**。


## <a name="view-the-accessibility-section-of-the-issues-tool"></a>[問題] ツールの [アクセシビリティ] セクションを表示する

1.  ブラウザーの [新しいタブでアクセシビリティ テストデモ Web][DevToolsA11yErrorsDemopage] ページを開き **、F12** を選択して DevTools を開きます。  右上には、自動的に検出された問題の数と共に、問題カウンター \( **Issues** counter \) が音声バブル アイコンとして ![ ](../media/issues-counter-icon.msft.png) 表示されます。  ブラウザーに別の番号が表示され、DevTools を使用すると番号が更新される場合があります。

    :::image type="complex" source="../media/a11y-testing-issues-tracker.msft.png" alt-text="現在のドキュメントに存在する問題の数を示す DevTools の Issues カウンター" lightbox="../media/a11y-testing-issues-tracker.msft.png":::
        現在 **のドキュメントに** 存在する問題の数を示す DevTools の Issues カウンター
    :::image-end:::

1.  [問題 **] カウンターを選択します**。  Issues **ツール** が開き **、DevTools** の下部にあるドロワーに表示されます。

    :::image type="complex" source="../media/a11y-testing-accessibility-issues.msft.png" alt-text="[問題] ツールに表示されるアクセシビリティの警告" lightbox="../media/a11y-testing-accessibility-issues.msft.png":::
        [問題] ツールに表示されるアクセシビリティの警告
    :::image-end:::

1.  [問題 **] タブで** 、[アクセシビリティ] **セクションを展開** します。


## <a name="verify-that-input-fields-have-labels"></a>入力フィールドにラベルが含まれています。

入力フィールドにラベルが接続されているかどうかを確認するには、[問題] ツール**** を使用して、Web ページ全体を自動的にチェックし、[アクセシビリティ] セクションでこの問題**を報告**します。

1.  ブラウザーの [新しいタブでアクセシビリティ テストデモ Web][DevToolsA11yErrorsDemopage] ページを開き **、F12** を選択して DevTools を開きます。

1.  右上の [問題]**** カウンター \( ![ Issues counter ](../media/issues-counter-icon.msft.png) \) を選択します。  Issues **ツール** が開き **、DevTools** の下部にあるドロワーに表示されます。

1.  [問題 **] タブで** 、[アクセシビリティ] **セクションを展開** します。

1.  [警告] を **展開します** `Form elements must have labels: Element has no title attribute Element has no placeholder attribute` 。

1. [要素で **開く] リンクを選択** します。

    :::image type="complex" source="../media/a11y-testing-inspect-problematic-element.msft.png" alt-text="[問題] ツールでリンクを選択した後に問題のある HTML を表示する要素ツール" lightbox="../media/a11y-testing-inspect-problematic-element.msft.png":::
        [問題] ツールでリンクを選択した後に問題のある HTML を **表示する要素** ツール :::image-end:::

    要素 **ツールが** 開き、DOM ツリーで要素が強調表示されます。  [ **スタイル]** ウィンドウには、要素に適用された CSS ルールが表示されます。  次のコードが表示されます。

    ```html
    <label>Search</label>
    <input type="search">
    <input type="submit" value="go">
    ```

    上記のコードでは、要素と特定の要素との間に接続が行われるため、要素が正 `label` `label` しく使用 `input` されません。  要素を特定 `label` の要素に接続 `input` するには、次のオプションを使用します。
    *   要素内で `input` 要素をネスト `label` します。
    *   要素に `label` 、要素の `for` 属性に一致する `id` 属性を追加 `input` します。

    要素間の接続の不足をテストする別の方法があります。 [要素 **] ツール** で `<label>Search</label>` 、DOM ツリーで要素を選択します。  Web ページで、フォーカスは検索ラベルにのみ表示され****、入力テキスト ボックスには表示されません。  正しい実装では、入力テキスト ボックスと `search` 検索ラベルに **フォーカスが置** かされます。

1.  正しい接続の例として、寄付フォームの **[その** 他] ラベルを選択します。  一致する値と属性値があるため、フォーカス インジケーター ボックスが****[その他] ラベルの横の入力テキスト ボックス `for` に正しく `id` 表示されます。

1.  [問題 **] ツールで、[** さらに読 **む** ] を選択して、問題の詳細を確認します。  新しいタブでリンクを開く場合は **、Ctrl**キーを押しながら Windows/Linux のリンクをクリックするか、コマンドで macOS のリンク + ******** + **** をクリックします。

    :::image type="complex" source="../media/a11y-testing-more-information-links.msft.png" alt-text="問題に関する詳細な情報を示す [問題] タブのリンク" lightbox="../media/a11y-testing-more-information-links.msft.png":::
        問題に関 **する詳細** な情報を示す [問題] タブのリンク
    :::image-end:::


## <a name="verify-that-images-have-alt-text"></a>イメージに代替テキストが含まれています。

基本的なアクセシビリティテストでは、画像に代替テキスト (alt _テキストとも呼_ばれる) が用意されている必要があります。

画像に対して代替テキストが提供されているかどうかを自動的に確認するには、[**** アクセシビリティ] セクションがある [問題]**ツールを使用**します。  Issues **ツール** は、DevTools **の下部** にあるドロワーにあります。

1.  ブラウザーの [新しいタブでアクセシビリティ テストデモ Web][DevToolsA11yErrorsDemopage] ページを開き **、F12** を選択して DevTools を開きます。

1.  [問題] **ツールを開** くには **、DevTools** の右上にある [問題] カウンターを選択します。

1.  [問題 **] タブで** 、警告を展開します `Images must have alternate text: Element has no title attribute` 。  代替テキストがないイメージのインスタンスは 4 種類です。

    :::image type="complex" source="../media/a11y-testing-images-without-alt.msft.png" alt-text="代替テキストが見つからない問題ツールレポート画像" lightbox="../media/a11y-testing-images-without-alt.msft.png":::
        代替テキストが見つからない問題ツールレポート画像
    :::image-end:::

詳細については、[イメージ] に移動 [するには、代替テキストが必要です](https://dequeuniversity.com/rules/axe/4.1/image-alt)。


## <a name="verify-that-text-colors-have-enough-contrast"></a>テキストの色に十分なコントラストが設定されているのを確認する

テキストの色のコントラストが十分かどうかを自動的に確認するには****、[アクセシビリティ] セクションがある [問題]**ツールを使用**します。  Issues **ツール** は、DevTools **の下部** にあるドロワーにあります。

1.  ブラウザーの [新しいタブでアクセシビリティ テストデモ Web][DevToolsA11yErrorsDemopage] ページを開き **、F12** を選択して DevTools を開きます。

1.  [問題] **ツールを開** くには **、DevTools** の右上にある [問題] カウンターを選択します。  デモ Web ページの 2 つの要素のコントラストが十分ではないという警告が表示される場合があります。

    :::image type="complex" source="../media/a11y-testing-contrast-issues.msft.png" alt-text="[問題] ツールで報告されたコントラストの問題" lightbox="../media/a11y-testing-contrast-issues.msft.png":::
        [問題] ツールで報告されたコントラストの問題
    :::image-end:::

1.  設定によっては、[問題] タブ**** に、色のコントラストが不十分でテキスト コンテンツの読み取りが困難になる可能性があるという警告**が表示される場合があります**。   この警告を展開し、[影響を受けるリソース **] を展開できます**。  要素の一覧が表示され、十分なコントラストを持つ要素の一覧が表示されます。


1.  要素を選択 `li.high` します。  レンダリングされた Web ページでは **、[Donate]** セクションの **[犬** ] リンクが強調表示され、小さな情報オーバーレイが表示されます。  これは、要素ツールの DOM ツリー内の要素にカーソルを合わせると表示されるオーバーレイと **同** じです。

    :::image type="complex" source="../media/a11y-testing-element-with-contrast-issues.msft.png" alt-text="[影響を受けるリソース] セクションでリンクを選択した後に強調表示された Web ページ内の要素" lightbox="../media/a11y-testing-element-with-contrast-issues.msft.png":::
        [影響を受けるリソース] セクションでリンクを選択した後に強調表示された Web**ページ内の要素**
    :::image-end:::


### <a name="wavy-underlines-in-the-dom-tree-indicate-automatically-detected-issues"></a>DOM ツリーの波の下線は、自動的に検出された問題を示します 

要素ツールの DOM ツリー **は、HTML** 内で直接問題に波線を付け、下線を付けフラグを設定します。  これらの問題は、問題ツール **によって報告** されます。  下線 **が波打つ** 要素を Shift キーを押しながらクリックすると、[問題] **ツールが** 表示されます。

1.  要素ツール **の DOM** ツリーで **、Shift キー** を押しながら要素をクリックします。この要素の下に波 `<input type="search">` 線が表示されます `input` 。  [ **問題] ツールが** 表示され、その要素の問題が表示されます。

    :::image type="complex" source="../media/a11y-testing-wavy-underlines.msft.png" alt-text="DOM ビューに波の下線がある要素に問題がある" lightbox="../media/a11y-testing-wavy-underlines.msft.png":::
        DOM ビューに波の下線がある要素に問題がある
    :::image-end:::


## <a name="see-also"></a>関連項目

*  [DevTools の問題ツールの問題Microsoft Edge見つけて修正する][DevToolsIssuesTool]
*  [DevTools を使用したアクセシビリティ テストの概要](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsIssuesTool]: ../issues/index.md "Microsoft Edge DevTools の問題を見つけて解決するツール | Microsoft Docs"
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "アクセシビリティテストのデモ web ページ |GitHub"
