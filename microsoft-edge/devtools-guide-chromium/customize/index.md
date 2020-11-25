---
description: Microsoft Edge DevTools をカスタマイズする方法の一覧
title: Microsoft Edge DevTools をカスタマイズする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/20/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 682ff78b6a5272c1f6462648d64241448838edac
ms.sourcegitcommit: 080759f68a0a158f10dc20d20c14e222ace1be84
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2020
ms.locfileid: "11189987"
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

**設定**  > **環境設定**には、devtools をカスタマイズするための多くのオプションが含まれています。  

[設定] を開くには、次のいずれかの操作を実行します。  

*   `F1`DevTools がフォーカスされているときにを選択します。  
*   **メインメニュー**を開き、[**設定**] を選択します。  
    
:::image type="complex" source="../media/customize-settings-preferences.msft.png" alt-text="設定" lightbox="../media/customize-settings-preferences.msft.png":::
   **設定**  
:::image-end:::  

## ドロアー  

**引き出し**は、選択したツールが表示される2番目のパネルです。  

**引き出し**を開く (または閉じる) には、を選択し `Escape` ます。  

:::image type="complex" source="../media/customize-drawer-open.msft.png" alt-text="ドロワー" lightbox="../media/customize-drawer-open.msft.png":::
   **ドロワー**  
:::image-end:::  

既定では、一部のツールはメインパネルに表示されますが、その他のツールは **引き出し**に表示されます。  [ **詳細** \ ()] を選ん `...` で、 **引き出し**でツールを開きます。  

:::image type="complex" source="../media/customize-drawer-open-more-tools.msft.png" alt-text="引き出しを開くためのボタン" lightbox="../media/customize-drawer-open-more-tools.msft.png":::
   **引き出し**を開くためのボタン  
:::image-end:::  

メインパネルとドロアーの間でツールを移動することができます。  

*   引き出しからメインパネルにツールを移動するには、ツールをポイントしてコンテキストメニューを開き (\ を右クリックし)、[ **先頭へ移動**] を選択します。  
    
    :::image type="complex" source="../media/move-from-drawer.msft.png" alt-text="引き出しからメインパネルに移動ツール" lightbox="../media/move-from-drawer.msft.png":::
       **引き出し**からメインパネルに移動ツール  
    :::image-end:::  
    
*   メインパネルから引き出しにツールを移動するには、ツールをポイントしてコンテキストメニューを開き (\ を右クリックし)、[ **下へ移動**] を選択します。  
    
    :::image type="complex" source="../media/move-to-drawer.msft.png" alt-text="メインパネルからドローワへの移動ツール" lightbox="../media/move-to-drawer.msft.png":::
       メインパネルから**ドローワ**への移動ツール
    :::image-end:::  
    

## パネルの順序を変更する  

ツールを選択してドラッグし、順序を変更します。  カスタムツールの順序は、DevTools セッション間で保持されます。  

> [!NOTE]
> 既定では、 **ネットワーク** ツールは左側の4番目のツールです。  次の図では、[ **ネットワーク** ] パネルは左側の最初のものです。  

:::image type="complex" source="../media/customize-network-first-position.msft.png" alt-text="パネル内の Devtools のカスタム順序" lightbox="../media/customize-network-first-position.msft.png":::
   パネル内の Devtools のカスタム順序  
:::image-end:::  

## DevTools の配置を変更する  

「 [Microsoft Edge DevTools の配置][DevToolsPlacement]」を参照してください。  

:::image type="complex" source="../media/customize-dev-tools-dock-side.msft.png" alt-text="アンドックした DevTools" lightbox="../media/customize-dev-tools-dock-side.msft.png":::
   アンドックした DevTools  
:::image-end:::  

## 濃色テーマ  

「 [濃色テーマを有効にする」を][DarkTheme]参照してください。  

:::image type="complex" source="../media/customize-settings-appearance-theme.msft.png" alt-text="濃色テーマ" lightbox="../media/customize-settings-appearance-theme.msft.png":::
   濃色テーマ  
:::image-end:::  

## テスト  

DevTools の実験を有効にするには、次の操作を実行します。  

1.  に移動 `edge://flags/#enable-devtools-experiments` します。  
1.  [ **有効にする**] を選びます。  
1.  ページの下部にある [ **今すぐ**再起動] を選びます。  

次に DevTools を開くと、[[設定](#settings)] に "**実験**" という名前の新しいページが表示されます。  

## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageMoreIcon]: ../media/more-icon.msft.png  

<!-- links -->  

[DevToolsPlacement]: ./placement.md "Microsoft Edge DevTools の配置を変更する |Microsoft ドキュメント"  
[DarkTheme]: ./dark-theme.md "Microsoft Edge DevTools でダークテーマを有効にする |Microsoft ドキュメント"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/customize/index) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
