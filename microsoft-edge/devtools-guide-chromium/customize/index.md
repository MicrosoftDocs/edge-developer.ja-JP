---
description: DevTools をカスタマイズする方法Microsoft Edgeリスト
title: DevTools Microsoft Edgeカスタマイズする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 0be3219579794dca28f71e336da1154f31f2d2be
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564386"
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
# <a name="customize-microsoft-edge-devtools"></a>DevTools Microsoft Edgeカスタマイズする  

このページでは、DevTools をカスタマイズするMicrosoft Edge示します。  

## <a name="settings"></a>設定  

**設定**  > **基本設定には**、DevTools をカスタマイズするための多くのオプションが含まれている。  

ファイルを開設定、次のいずれかの操作を実行します。  

*   `F1`DevTools がフォーカスされている間に選択します。  
*   [メイン メニュー **] を開**き、[メニュー]**を設定。**  
    
:::image type="complex" source="../media/customize-settings-preferences.msft.png" alt-text="設定" lightbox="../media/customize-settings-preferences.msft.png":::
   **設定**  
:::image-end:::  

## <a name="drawer"></a>ドロワー  

ドロ **ワー** は、選択したツールが表示される 2 番目のパネルです。  

ドロワーを \(または close\) **で開**く場合は、 を選択します `Escape` 。  

:::image type="complex" source="../media/customize-drawer-open.msft.png" alt-text="ドロワー" lightbox="../media/customize-drawer-open.msft.png":::
   ドロ **ワー**  
:::image-end:::  

既定では、一部のツールはメイン パネルで開き、他のツールはドロワーに表示 **されます**。  [ **その他** ] \( `...` \) を選択して、ドロワーでツールを開 **きます**。  

:::image type="complex" source="../media/customize-drawer-open-more-tools.msft.png" alt-text="ドロワーを開くボタン" lightbox="../media/customize-drawer-open-more-tools.msft.png":::
   ドロワーを開く **ボタン**  
:::image-end:::  

メイン パネルと引き出しの間でツールを移動できます。  

*   ツールを引き出しからメイン パネルに移動するには、ツールにカーソルを合わせると、コンテキスト メニュー \(右クリック\) を開き、[上へ移動] を **選択します**。  
    
    :::image type="complex" source="../media/move-from-drawer.msft.png" alt-text="ドロワーからメイン パネルにツールを移動する" lightbox="../media/move-from-drawer.msft.png":::
       ドロワーからメイン **パネル** にツールを移動する  
    :::image-end:::  
    
*   メイン パネルから引き出しにツールを移動するには、ツールにマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[下へ移動] を **選択します**。  
    
    :::image type="complex" source="../media/move-to-drawer.msft.png" alt-text="メイン パネルからドロワーにツールを移動する" lightbox="../media/move-to-drawer.msft.png":::
       メイン パネルからドロワーにツールを **移動する**
    :::image-end:::  
    

## <a name="reorder-panels"></a>パネルの並べ替え  

ツールを選択してドラッグして順序を変更します。  カスタム ツールの順序は、DevTools セッション全体で保持されます。  

> [!NOTE]
> 既定では、ネットワーク **ツール** は通常、左から 4 番目です。  次の図では、ネットワーク **ツール** は左から 1 つ目です。  

:::image type="complex" source="../media/customize-network-first-position.msft.png" alt-text="パネル内の Devtools のカスタム順序" lightbox="../media/customize-network-first-position.msft.png":::
   パネル内の Devtools のカスタム順序  
:::image-end:::  

## <a name="change-devtools-placement"></a>DevTools の配置を変更する  

[[DevTools Microsoft Edge] に移動します][DevToolsPlacement]。  

:::image type="complex" source="../media/customize-dev-tools-dock-side.msft.png" alt-text="ドッキングされていない DevTools" lightbox="../media/customize-dev-tools-dock-side.msft.png":::
   ドッキングされていない DevTools  
:::image-end:::  

## <a name="dark-theme"></a>濃色テーマ  

[暗いテーマ [を有効にする] に移動します][DarkTheme]。  

:::image type="complex" source="../media/customize-settings-appearance-theme.msft.png" alt-text="暗いテーマ" lightbox="../media/customize-settings-appearance-theme.msft.png":::
   暗いテーマ  
:::image-end:::  

## <a name="experiments"></a>テスト  

DevTools 実験を有効にするには、次のアクションを実行します。  

1.  `edge://flags/#enable-devtools-experiments` に移動します。  
1.  [有効 **にする] を選択します**。  
1.  ページ **の下部にある [今すぐ**再起動] を選択します。  

次回 DevTools を開く場合は、[**実験**] という名前の新しい[ページ](#settings)が [テスト] 設定。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームに連絡する  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageMoreIcon]: ../media/more-icon.msft.png  

<!-- links -->  

[DevToolsPlacement]: ./placement.md "Microsoft Edge DevTools の配置を変更 | Microsoft Docs"  
[DarkTheme]: ./dark-theme.md "DevTools サーバーで暗いMicrosoft Edgeを有効|Microsoft Docs"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/customize/index) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
