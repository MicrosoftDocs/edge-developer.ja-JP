---
description: Microsoft Edge DevTools をカスタマイズする方法の一覧
title: Microsoft Edge DevTools をカスタマイズする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/22/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 5822fa087244fdfafdefe040709058411040ea45
ms.sourcegitcommit: 12c30ad4ab2664d17c9b7e9d59d7a3cda60ff65c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2021
ms.locfileid: "11313024"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->

# Microsoft Edge DevTools をカスタマイズする  

このページでは、Microsoft Edge DevTools をカスタマイズする方法を示します。  

## 設定  

**設定**  > **基本設定には**、DevTools をカスタマイズするための多くのオプションが含まれている。  

[設定] を開くには、次のいずれかの操作を実行します。  

*   `F1`DevTools にフォーカスがある間に選択します。  
*   メイン メニューを **開き、[** 設定] を **選択します**。  
    
:::image type="complex" source="../media/customize-settings-preferences.msft.png" alt-text="設定" lightbox="../media/customize-settings-preferences.msft.png":::
   **設定**  
:::image-end:::  

## ドロワー  

ドロ **ワー** は、選択したツールが表示される 2 番目のパネルです。  

ドロワーを \(または閉じる\ を開く) **には**、選択します `Escape` 。  

:::image type="complex" source="../media/customize-drawer-open.msft.png" alt-text="ドロワー" lightbox="../media/customize-drawer-open.msft.png":::
   ドロ **ワー**  
:::image-end:::  

既定では、一部のツールはメイン パネルで開き、他のツールはドロワーに表示 **されます**。  Choose **More** \( `...` \) to open a tool in the **Drawer**.  

:::image type="complex" source="../media/customize-drawer-open-more-tools.msft.png" alt-text="ドロワーを開くボタン" lightbox="../media/customize-drawer-open-more-tools.msft.png":::
   ドロワーを開く **ボタン**  
:::image-end:::  

メイン パネルとドロワーの間でツールを移動できます。  

*   ドロワーからメイン パネルにツールを移動するには、ツールをポイントし、コンテキスト メニュー \(右クリック\) を開き、[一番上に移動] を **選択します**。  
    
    :::image type="complex" source="../media/move-from-drawer.msft.png" alt-text="ドロワーからメイン パネルにツールを移動する" lightbox="../media/move-from-drawer.msft.png":::
       ドロワーからメイン **パネル** にツールを移動する  
    :::image-end:::  
    
*   メイン パネルからドロワーにツールを移動するには、ツールをポイントし、コンテキスト メニュー \(右クリック\) を開き、[下へ移動] を **選択します**。  
    
    :::image type="complex" source="../media/move-to-drawer.msft.png" alt-text="メイン パネルからドロワーにツールを移動する" lightbox="../media/move-to-drawer.msft.png":::
       メイン パネルからドロワーにツールを移動 **する**
    :::image-end:::  
    

## パネルを並べ替える  

ツールを選択してドラッグし、順序を変更します。  カスタム ツールの順序は、DevTools セッション間で保持されます。  

> [!NOTE]
> 既定では、 **通常、ネットワーク** ツールは左から 4 番目です。  次の図では、[ **ネットワーク** ] パネルは左から 1 つ目です。  

:::image type="complex" source="../media/customize-network-first-position.msft.png" alt-text="パネルでの Devtools のカスタム順序" lightbox="../media/customize-network-first-position.msft.png":::
   パネルでの Devtools のカスタム順序  
:::image-end:::  

## DevTools の配置を変更する  

[「Microsoft Edge DevTools Placement」を参照してください][DevToolsPlacement]。  

:::image type="complex" source="../media/customize-dev-tools-dock-side.msft.png" alt-text="ドッキングされていない DevTools" lightbox="../media/customize-dev-tools-dock-side.msft.png":::
   ドッキングされていない DevTools  
:::image-end:::  

## 濃色テーマ  

「濃色 [テーマを有効にする」をご覧ください][DarkTheme]。  

:::image type="complex" source="../media/customize-settings-appearance-theme.msft.png" alt-text="濃色テーマ" lightbox="../media/customize-settings-appearance-theme.msft.png":::
   濃色テーマ  
:::image-end:::  

## テスト  

DevTools 実験を有効にするには、次の操作を実行します。  

1.  に移動します `edge://flags/#enable-devtools-experiments` 。  
1.  Choose **Enable**.  
1.  ページ **の下部にある [今すぐ**再起動] を選択します。  

次回 DevTools を開く時に、[設定] に **Experiments** という名前の新しいページが表示 [されます](#settings)。  

## Microsoft Edge DevTools チームに連絡する  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageMoreIcon]: ../media/more-icon.msft.png  

<!-- links -->  

[DevToolsPlacement]: ./placement.md "Microsoft Edge DevTools の配置を変更 | Microsoft Docs"  
[DarkTheme]: ./dark-theme.md "Microsoft Edge DevTools アプリケーションで濃色テーマを|Microsoft Docs"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/customize/index) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
