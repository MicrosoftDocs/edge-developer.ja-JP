---
description: '[レンダリング] タブを開き、"print" > CSS メディアをエミュレートする] を選択します。'
title: Microsoft Edge DevTools を印刷プレビュー モードに強制する (CSS 印刷メディア タイプ)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: a036e710de998f03e876126581956929d8652f1e
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230923"
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

# Microsoft Edge DevTools を印刷プレビュー モードに強制する (CSS Print Media Type)  

印刷 [メディア クエリは、][MDNUsingMediaQueries] 印刷時のページの外観を制御します。  ページを印刷プレビュー モードにする場合:  

1.  `Control`+`Shift`+`P` \(Windows, Linux\) または `Command`+`Shift`+`P` \(macOS\) を選択して、**コマンド メニュー** を開きます。  
    
    :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="コマンド メニュー" lightbox="../media/css-console-command-menu-rendering.msft.png":::
       **コマンド メニュー**  
    :::image-end:::  
    
1.  種類 `rendering` を入力し、[ **レンダリングの表示] を**選択して、次に選択します `Enter` 。  
1.  [CSS **メディアのエミュレート] で、[** 印刷] を **選択します**。  
    
    :::image type="complex" source="../media/css-elements-styles-qs-rendering-emulate-css-media-print.msft.png" alt-text="印刷プレビュー モード" lightbox="../media/css-elements-styles-qs-rendering-emulate-css-media-print.msft.png":::
       印刷プレビュー モード  
    :::image-end:::  
    
ここから、他の Web ページと同様に CSS を表示および変更できます。  CSS の [表示と変更の開始に移動します][DevToolsCSSGetStarted]。  

## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft Docs"  
[DevToolsCSSGetStarted]: ./index.md "CSS の表示と変更を開始する |Microsoft Docs"  

[MDNUsingMediaQueries]: https://developer.mozilla.org/docs/Web/CSS/Media_Queries/Using_media_queries "メディア クエリの使用 |MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/css/print-preview) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
