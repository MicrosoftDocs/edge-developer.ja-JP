---
title: Microsoft Edge の DevTools を印刷プレビューモード (CSS 印刷メディアの種類) に強制する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 6bf9605fc8dc4e43db88668ac1f0af35bf9aba66
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10982308"
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





# <span data-ttu-id="116c4-103">Microsoft Edge の DevTools を印刷プレビューモード (CSS 印刷メディアの種類) に強制する</span><span class="sxs-lookup"><span data-stu-id="116c4-103">Force Microsoft Edge DevTools into Print Preview mode (CSS Print Media Type)</span></span>   



<span data-ttu-id="116c4-104">[印刷メディアクエリ][MDNUsingMediaQueries]は、ページがどのように印刷されるかを制御します。</span><span class="sxs-lookup"><span data-stu-id="116c4-104">The [print media query][MDNUsingMediaQueries] controls how your page looks when printed.</span></span>  <span data-ttu-id="116c4-105">ページを印刷プレビューモードにするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="116c4-105">To force your page into print preview mode:</span></span>  

1.  <span data-ttu-id="116c4-106">`Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows \) または `Command` + `Shift` + `P` \ **Command Menu**(macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="116c4-106">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="コマンドメニュー" lightbox="../media/css-console-command-menu-rendering.msft.png":::
       <span data-ttu-id="116c4-108">**コマンドメニュー**</span><span class="sxs-lookup"><span data-stu-id="116c4-108">The **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="116c4-109">入力し `rendering` て、[ **レンダリングの表示**] を選択し、を押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="116c4-109">Type `rendering`, select **Show Rendering**, and then press `Enter`.</span></span>  
1.  <span data-ttu-id="116c4-110">[ **CSS メディアのエミュレート** ] で [ **印刷**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="116c4-110">Under **Emulate CSS media** select **print**.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-qs-rendering-emulate-css-media-print.msft.png" alt-text="印刷プレビューモード" lightbox="../media/css-elements-styles-qs-rendering-emulate-css-media-print.msft.png":::
       <span data-ttu-id="116c4-112">印刷プレビューモード</span><span class="sxs-lookup"><span data-stu-id="116c4-112">Print preview mode</span></span>  
    :::image-end:::  
    
<span data-ttu-id="116c4-113">ここでは、他の web ページと同じように、CSS を表示したり変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="116c4-113">From here, you can view and change your CSS, like any other web page.</span></span>  <span data-ttu-id="116c4-114">「 [CSS の表示と変更」の「使用を開始する」を][DevToolsCSSGetStarted]参照してください。</span><span class="sxs-lookup"><span data-stu-id="116c4-114">See [Get Started With Viewing And Changing CSS][DevToolsCSSGetStarted].</span></span>  

<!--  
 


-->  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  
[DevToolsCSSGetStarted]: ./index.md "CSS の表示と変更の概要 |Microsoft ドキュメント"  

[MDNUsingMediaQueries]: https://developer.mozilla.org/docs/Web/CSS/Media_Queries/Using_media_queries "メディアクエリを使用する |MDN"  

> [!NOTE]
> <span data-ttu-id="116c4-118">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="116c4-118">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="116c4-119">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/css/print-preview) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="116c4-119">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/css/print-preview) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="116c4-121">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="116c4-121">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
