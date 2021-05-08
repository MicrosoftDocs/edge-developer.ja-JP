---
description: DevTools の [スタイル] ウィンドウを使用して CSS フォントのスタイルと設定をMicrosoft Edgeします。
title: DevTools の [スタイル] ウィンドウで CSS フォントのスタイルと設定を編集する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/11/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
no-loc:
- Enable new font editor tool within the Styles pane
ms.openlocfilehash: 5d9074ca65f9cb98662a1bc181f70ead4c4232e1
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439494"
---
# <a name="edit-css-font-styles-and-settings-in-the-styles-pane"></a>[スタイル] ウィンドウで CSS フォントのスタイルと設定を編集する  

:::image type="icon" source="../media/experimental-tag-14px.msft.png":::

Web 上のタイポグラフィは、ユーザー エクスペリエンスの重要な部分です。  企業のブランド ガイドラインを満たして、さまざまなデバイスでコンテンツが期待通り表示されるのを確認する必要があります。  テキストは、サイズと行の高さを使用して読みやすくする必要があります。  ユーザーは、個々のニーズに合わせてフォントのサイズを変更できます。  特定のフォントがユーザー デバイスで使用できない場合は、フォールバック フォント オプションを指定する必要があります。  

CSS では、近年のタイポグラフィのサポートが向上しています。  テキストのサイズを定義するには、数十種類の CSS 単位を使用できます。  また、フォント サイズ、間隔、行の高さ、その他の入力ミス機能に影響を与える CSS プロパティもいくつか用意されています。  

タイポグラフィの操作を簡単にするために、Visual **Font Editor** が [スタイル] ウィンドウ **に表示** されます。  フォント設定を変更すると、変更はブラウザーですぐにレンダリングされます。  CSS に関する詳細な知識がないすべて。  

現在、 **Enable new font editor tool within the Styles pane** この機能は実験的であり、開発者向けツールで有効[にするMicrosoft Edge必要があります][DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures]。  

[スタイル] ウィンドウ **の CSS** (フォント定義またはインライン スタイル) には、ビジュアル フォント エディターを開くアイコンが自動的に **表示されます**。  ビジュアル フォント エディターを **開くには、[** フォント エディター] **アイコンを選択** します。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/font-editor-icon.msft.png" alt-text="フォント設定を編集する [スタイル] ウィンドウのアイコン" lightbox="../media/font-editor-icon.msft.png":::
         フォント設定を編集する **[スタイル** ] ウィンドウのアイコン  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/font-editor-open.msft.png" alt-text="[スタイル] ウィンドウの上部で [フォント エディター] が開きます" lightbox="../media/font-editor-open.msft.png":::
         [ **スタイル] ウィンドウ** の上部で [フォント エディター] **が開** きます  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

ビジュアル フォント エディターのすべてのフィールド **は、[** スタイル] ウィンドウの CSS の値から **設定** されます。  たとえば、定義は [スタイル] ウィンドウに設定され、行の高さテキスト フィールドが表示され、単位ドロップダウン `line-height` `160%` **** `160` が表示されます `%` 。  また、スライダーはテキスト フィールドの値と一致する自動的に設定されます。  

フォント **エディターは、** フォント ファミリ セレクターと CSS プロパティ エディターの 2 つの部分で構成されます。  

## <a name="the-font-family-selector"></a>フォント ファミリ セレクター  

フォント ファミリ セレクターは、ビジュアル フォント エディターの上部 **です**。  CSS ルールのフォントを選択するには、CSS エディターで[フォント ファミリ] **セレクターを使用** します。  CSS ルールごとにメイン フォントとフォールバック フォントを選択できます。  

:::image type="complex" source="../media/font-editor-font-family.msft.png" alt-text="[フォント ファミリ] セレクターが強調表示された [スタイル] ウィンドウの上部にある [フォント エディター] が開きます。" lightbox="../media/font-editor-font-family.msft.png":::
   [ **フォント ファミリ]** セレクターが強調表示された [ **スタイル** ] ウィンドウの上部にある **[** フォント エディター] が開きます。  
:::image-end:::  

[フォント **ファミリ] ドロップダウンを** 使用して、フォントの一覧から選択します。  フォントは 4 つのグループに編成されます。  

1.  [スタイル] ウィンドウのスタイルシートで使用できるフォントである、計算された **フォント** 。  
1.  現在のオペレーティング システムで使用できるフォントであるシステム フォント。  
1.  または などの汎用フォント `serif` ファミリ `sans-serif` 。  
1.  グローバル値 (、 `inherit` `initial` `unset` など)  
    
:::image type="complex" source="../media/font-editor-font-family-list.msft.png" alt-text="フォント ファミリ セレクターが強調表示された [スタイル] ウィンドウの上部で開くフォント エディター" lightbox="../media/font-editor-font-family-list.msft.png":::
   [ **フォント ファミリ]** セレクターが強調表示された [ **スタイル** ] ウィンドウの上部にある **[** フォント エディター] が開きます。  
:::image-end:::  

フォントを選択すると、フォールバック フォントを選択する別のドロップダウン メニューが表示されます。  最大 8 つのフォールバック フォントを選択できます。  フォントを削除するには、[フォント ファミリの削除 **] アイコンを選択** します。  

<!--:::image type="complex" source="../media/font-editor-defining-fonts.msft.png" alt-text="The font editor with a defined list of fonts and fallback fonts" lightbox="../media/font-editor-defining-fonts.msft.png":::
   The **Font Editor** with a defined list of fonts and fallback fonts highlighted
:::image-end:::  -->

> [!NOTE]
> フォント ファミリのグローバル値を選択した場合は、CSS でフォールバックが行ななわず、別のドロップダウンは取得されません。  

## <a name="the-css-properties-editor"></a>CSS プロパティ エディター  

ビジュアル フォント エディターの下部で CSS フォント プロパティを **変更できます**。  UI コントロールを使用して、フォント サイズ、行の高さ、フォントの太さ、文字の間隔を変更できます。  変更はブラウザーで直ちに適用されます。  

:::image type="complex" source="../media/font-editor-css-properties.msft.png" alt-text="CSS プロパティが強調表示された [スタイル] ウィンドウの上部でフォント エディターが開きます" lightbox="../media/font-editor-css-properties.msft.png":::
   CSS **プロパティが強調表示** された [スタイル] **ウィンドウの** 上部でフォント エディターが開きます。  
:::image-end:::  

ビジュアル フォント エディターを使用して CSS 単位を **変換することもできます**。  たとえば、[フォント サイズ] スライダーが最初にに設定されている**** CSS ルールでツールを使用できます `16 pixels` 。  次に、単位ドロップダウンを使用して値を選択します `em` 。  表示 `1 em` される値はに等しくなります `16 pixels` 。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/font-editor-setting-to-16px.msft.png" alt-text="フォント サイズを 16 ピクセルに変更する" lightbox="../media/font-editor-setting-to-16px.msft.png":::
         フォント サイズを次に変更する `16 pixels`  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/font-editor-converted-to-em.msft.png" alt-text="単位ドロップダウンを開き、em に変換する" lightbox="../media/font-editor-converted-to-em.msft.png":::
         変換する単位ドロップダウンを開きます。 `em`  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

[単位] ドロップダウンには、使用可能なすべての数値 CSS 単位が用意されています。  フォント サイズ、行の高さ、フォントの太さ、および間隔は、すべて異なる単位を使用します。  テキスト ボックスにフォーカスがある場合は、キーとキーを選択して設定 `arrow up` `arrow down` を微調整できます。  キーボードでスライダーを使用するには、キーとキー `arrow left` を選択 `arrow down` します。  

CSS プロパティ エディターには、事前設定されたキーワードも含まれています。  プリセット キーワードを使用するには、右側でアイコンを選択 `Toggle Input Type` します。  UI が変更され、プリセット キーワードのドロップダウンが表示されます。  スライダーなどの UI コントロールを使用して UI に戻る場合は、もう一度アイコン `Toggle Input Type` を選択します。  

:::image type="complex" source="../media/font-editor-preset-font-sizes.msft.png" alt-text="プリセット キーワード インターフェイスを開く" lightbox="../media/font-editor-preset-font-sizes.msft.png":::
   プリセット キーワード インターフェイスを開く  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsIndex]: ../index.md "Microsoft Edge (Chromium) 開発者ツール | Microsoft Docs"  
[DevtoolsExperimentalFeaturesIndex]: ../experimental-features/index.md "実験的な機能|Microsoft Docs"  
[DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures]: ../experimental-features/index.md#turn-on-experimental-features "試験的機能を有効にする - 試験的機能 | Microsoft Docs"  
