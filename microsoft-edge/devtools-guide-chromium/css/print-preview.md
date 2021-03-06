---
description: '[レンダリング] ツールを開き、[印刷時に CSS メディアをエミュレート>選択します。'
title: Microsoft Edge DevTools を印刷プレビュー モードに強制する (CSS 印刷メディアの種類)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 0123b7abf475212304f654c04bc232e3e96f0bda
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399079"
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

# <a name="force-microsoft-edge-devtools-into-print-preview-mode"></a>Microsoft Edge DevTools を印刷プレビュー モードに強制する  

印刷 [メディア クエリは、][MDNUsingMediaQueries] 印刷時のページの外観を制御します。  ページを印刷プレビュー モードに設定するには、次の方法を実行します。  

1.  `Control`+`Shift`+`P` \(Windows, Linux\) または `Command`+`Shift`+`P` \(macOS\) を選択して、**コマンド メニュー** を開きます。  
    
    :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="コマンド メニュー" lightbox="../media/css-console-command-menu-rendering.msft.png":::
       **コマンド メニュー**  
    :::image-end:::  
    
1.  [レンダリング `rendering` の表示] **を選択し**、[選択] を選択します `Enter` 。  
1.  [CSS **メディアのエミュレート] で**、[印刷] を **選択します**。  
    
    :::image type="complex" source="../media/css-elements-styles-qs-rendering-emulate-css-media-print.msft.png" alt-text="印刷プレビュー モード" lightbox="../media/css-elements-styles-qs-rendering-emulate-css-media-print.msft.png":::
       印刷プレビュー モード  
    :::image-end:::  
    
ここから、他の Web ページと同様に CSS を表示および変更できます。  [CSS の [表示と変更の開始] に移動します][DevToolsCSSGetStarted]。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (クロム) 開発者向け|Microsoft Docs"  
[DevToolsCSSGetStarted]: ./index.md "CSS ファイルの表示と変更の|Microsoft Docs"  

[MDNUsingMediaQueries]: https://developer.mozilla.org/docs/Web/CSS/Media_Queries/Using_media_queries "メディア クエリの使用|MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/css/print-preview) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
