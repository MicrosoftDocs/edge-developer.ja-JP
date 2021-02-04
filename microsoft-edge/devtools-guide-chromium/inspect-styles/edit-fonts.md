---
description: Microsoft Edge DevTools の [スタイル] ウィンドウを使用して CSS フォントのスタイルと設定を変更する方法について説明します。
title: DevTools の [スタイル] ウィンドウで CSS フォントのスタイルと設定を編集する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/03/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 928f7abb0f74839708cbe5c904ad321109ae33f0
ms.sourcegitcommit: 12c30ad4ab2664d17c9b7e9d59d7a3cda60ff65c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2021
ms.locfileid: "11313263"
---
# [スタイル] ウィンドウで CSS フォントのスタイルと設定を編集する  

:::image type="icon" source="../media/experimental-tag-14px.msft.png":::

Web 上の文字体裁は、ユーザー エクスペリエンスの重要な部分です。  企業のブランド ガイドラインを満たして、さまざまなデバイスでコンテンツが期待通り表示される必要があります。  テキストは、サイズと行の高さを使用して読みやすくする必要があります。  ユーザーは、個々のニーズに合わせてフォントのサイズを変更できます。  ユーザー デバイスで特定のフォントを使用できない場合は、フォールバック フォント オプションを提供する必要があります。  

CSS は、最近の文字体裁をより良くサポートします。  テキストのサイズを定義するには、多数の異なる CSS 単位を使用できます。  また、フォント サイズ、間隔、行の高さ、その他の入力ミス機能に影響を与えるいくつかの CSS プロパティがあります。  

文字体裁を簡単に操作するために、表示フォント**** エディターが [スタイル] ウィンドウ**に表示**されます。  フォント設定を変更すると、変更がブラウザーに即座にレンダリングされます。  すべて、CSS に関する詳細な知識がない。  

現在、[スタイル **] ウィンドウ機能内** の [新しいフォント エディターを有効にする] ツールは試験的であり [、Microsoft Edge 開発者][DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures]ツールで有効にする必要があります。  

[スタイル] ウィンドウ **の CSS** (フォント定義またはインライン スタイル) には、視覚的なフォント エディターを開くアイコンが自動的に **表示されます**。  ビジュアル フォント エディターを **開く場合は**、[フォント エディター **] アイコンを選択** します。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/font-editor-icon.msft.png" alt-text="フォント設定を編集する [スタイル] ウィンドウのアイコン" lightbox="../media/font-editor-icon.msft.png":::
         フォント設定を編集 **する [** スタイル] ウィンドウのアイコン  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/font-editor-open.msft.png" alt-text="[スタイル] ウィンドウの上部に表示されるフォント エディター" lightbox="../media/font-editor-open.msft.png":::
         [ **スタイル] ウィンドウ** の上部にフォント エディター **が開** きます。  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

ビジュアル フォント エディターのすべてのフィールド **は、[** スタイル] ウィンドウの CSS の値から **設定** されます。  たとえば、[スタイル] ウィンドウで定義を設定すると、行の高さテキスト フィールドが表示され、単位ドロップダウン `line-height` `160%` **** `160` が表示されます `%` 。  また、スライダーはテキスト フィールドの値と一致する設定に自動的に設定されます。  

フォント **エディターは、** フォント ファミリ セレクターと CSS プロパティ エディターの 2 つの部分で構成されます。  

## フォント ファミリ セレクター  

フォント ファミリ セレクターは、ビジュアル フォント エディターの **上部です**。  CSS ルールのフォントを選択するには、CSS エディターでフォント ファミリ **セレクターを使用** します。  CSS ルールごとにメインフォントとフォールバック フォントを選択できます。  

:::image type="complex" source="../media/font-editor-font-family.msft.png" alt-text="[スタイル] ウィンドウの上部でフォント エディターが開き、フォント ファミリ セレクターが強調表示されている" lightbox="../media/font-editor-font-family.msft.png":::
   [ **スタイル] ウィンドウの** 上部でフォント エディター **が開** き、フォント ファミリ **セレクターが** 強調表示されている  
:::image-end:::  

[フォント **ファミリ] ドロップダウンを** 使用して、フォントの一覧から選択します。  フォントは 4 つのグループに分けられます。  

1.  計算されたフォント。[スタイル] ウィンドウのスタイルシートで使用できる **フォント** です。  
1.  システム フォント。現在のオペレーティング システムで使用可能なフォントです。  
1.  汎用フォント ファミリ (または `serif` `sans-serif` .  
1.  Global values, such as `inherit` , `initial` , and `unset` .  
    
:::image type="complex" source="../media/font-editor-font-family-list.msft.png" alt-text="[スタイル] ウィンドウの上部でフォント エディターが開き、フォント ファミリ セレクターが強調表示されている" lightbox="../media/font-editor-font-family-list.msft.png":::
   [ **スタイル] ウィンドウの** 上部でフォント エディター **が開** き、フォント ファミリ **セレクターが** 強調表示されている  
:::image-end:::  

フォントを選択すると、フォールバック フォントを選択するために別のドロップダウン メニューが表示されます。  最大 8 つのフォールバック フォントを選択できます。  フォントを削除するには、[フォント ファミリの削除 **] アイコンを選択** します。  

<!--:::image type="complex" source="../media/font-editor-defining-fonts.msft.png" alt-text="The font editor with a defined list of fonts and fallback fonts" lightbox="../media/font-editor-defining-fonts.msft.png":::
   The **Font Editor** with a defined list of fonts and fallback fonts highlighted
:::image-end:::  -->

> [!NOTE]
> フォント ファミリのグローバル値を選択した場合、CSS にはフォールバックが設定されていないので、別のドロップダウンは表示されません。  

## CSS プロパティ エディター  

CSS フォントのプロパティは、ビジュアル フォント エディターの下部で **変更できます**。  UI コントロールを使用して、フォント サイズ、行の高さ、フォントの太さ、文字の間隔を変更できます。  変更内容はブラウザーで直ちに適用されます。  

:::image type="complex" source="../media/font-editor-css-properties.msft.png" alt-text="CSS プロパティが強調表示された [スタイル] ウィンドウの上部にフォント エディターが開きます。" lightbox="../media/font-editor-css-properties.msft.png":::
   [ **スタイル] ウィンドウの** 上部でフォント エディター **が開** き、CSS プロパティが強調表示されている  
:::image-end:::  

また、ビジュアル フォント エディターを使用して CSS 単位を **変換することもできます**。  たとえば、[フォント サイズ] スライダーが最初に設定されている**** CSS ルールでこのツールを使用できます `16 pixels` 。  ここで、unit ドロップダウンを使用して、値を選択します `em` 。  表示 `1 em` される値は次の値です `16 pixels` 。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/font-editor-setting-to-16px.msft.png" alt-text="フォント サイズを 16 ピクセルに変更する" lightbox="../media/font-editor-setting-to-16px.msft.png":::
         フォント サイズを次の値に変更します。 `16 pixels`  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/font-editor-converted-to-em.msft.png" alt-text="unit ドロップダウンを開き、em に変換する" lightbox="../media/font-editor-converted-to-em.msft.png":::
         変換する単位ドロップダウンを開く `em`  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

Unit ドロップダウンには、使用可能なすべての数値 CSS ユニットが用意されています。  フォント サイズ、行の高さ、フォントの太さ、および間隔はすべて異なる単位で使用されます。  テキスト ボックスにフォーカスがある場合は、キーとキーを選択して設定 `arrow up` `arrow down` を微調整できます。  キーボードでスライダーを使う場合は、キーとキー `arrow left` を選択 `arrow down` します。  

CSS プロパティ エディターには、事前設定されたキーワードも含まれています。  あらかじめ設定されているキーワードを使う場合は、右側にあるアイコンを選択 `Toggle Input Type` します。  UI が変更され、プリセット キーワードのドロップダウンが表示されます。  スライダーや他の UI コントロールを使って UI に戻る場合は、もう一度アイコンを `Toggle Input Type` 選択します。  

:::image type="complex" source="../media/font-editor-preset-font-sizes.msft.png" alt-text="事前設定されたキーワード インターフェイスを開く" lightbox="../media/font-editor-preset-font-sizes.msft.png":::
   事前設定されたキーワード インターフェイスを開く  
:::image-end:::  

## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsIndex]: ../index.md "Microsoft Edge (Chromium) 開発者ツール | Microsoft Docs"  
[DevtoolsExperimentalFeaturesIndex]: ../experimental-features/index.md "試験的な機能|Microsoft Docs"  
[DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures]: ../experimental-features/index.md#turn-on-experimental-features "試験的機能を有効にする - 試験的機能 | Microsoft Docs"  
