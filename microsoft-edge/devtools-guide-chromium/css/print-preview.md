---
title: Microsoft Edge の DevTools を印刷プレビューモード (CSS 印刷メディアの種類) に強制する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/27/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 659120414597273b15657377c33c800e0c83b7cb
ms.sourcegitcommit: 5cdc1626d5581b79c0f2ac4ea62e7f1974ebfa57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "10601839"
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





# <span data-ttu-id="ef970-103">Microsoft Edge の DevTools を印刷プレビューモード (CSS 印刷メディアの種類) に強制する</span><span class="sxs-lookup"><span data-stu-id="ef970-103">Force Microsoft Edge DevTools Into Print Preview Mode (CSS Print Media Type)</span></span>   



<span data-ttu-id="ef970-104">[印刷メディアクエリ][MDNUsingMediaQueries]は、ページがどのように印刷されるかを制御します。</span><span class="sxs-lookup"><span data-stu-id="ef970-104">The [print media query][MDNUsingMediaQueries] controls how your page looks when printed.</span></span>  <span data-ttu-id="ef970-105">ページを印刷プレビューモードにするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ef970-105">To force your page into print preview mode:</span></span>  

1.  <span data-ttu-id="ef970-106">`Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows \) または `Command` + `Shift` + `P` \ **Command Menu**(macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="ef970-106">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    > ##### <span data-ttu-id="ef970-107">図 1</span><span class="sxs-lookup"><span data-stu-id="ef970-107">Figure 1</span></span>  
    > <span data-ttu-id="ef970-108">**コマンドメニュー**</span><span class="sxs-lookup"><span data-stu-id="ef970-108">The **Command Menu**</span></span>  
    > ![コマンドメニュー][ImageCommandMenu]  
    
1.  <span data-ttu-id="ef970-110">入力し `rendering` て、[**レンダリングの表示**] を選択し、を押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="ef970-110">Type `rendering`, select **Show Rendering**, and then press `Enter`.</span></span>  
1.  <span data-ttu-id="ef970-111">[ **CSS メディアのエミュレート**] で [**印刷**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="ef970-111">Under **Emulate CSS media** select **print**.</span></span>  
    
    > ##### <span data-ttu-id="ef970-112">図 2</span><span class="sxs-lookup"><span data-stu-id="ef970-112">Figure 2</span></span>  
    > <span data-ttu-id="ef970-113">印刷プレビューモード</span><span class="sxs-lookup"><span data-stu-id="ef970-113">Print preview mode</span></span>  
    > ![印刷プレビューモード][ImagePrintMode]  
    
<span data-ttu-id="ef970-115">ここでは、他の web ページと同じように、CSS を表示したり変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="ef970-115">From here, you can view and change your CSS, like any other web page.</span></span>  <span data-ttu-id="ef970-116">「 [CSS の表示と変更」の「使用を開始する」を][DevToolsCSSGetStarted]参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef970-116">See [Get Started With Viewing And Changing CSS][DevToolsCSSGetStarted].</span></span>  

 



<!-- image links -->  

[ImageCommandMenu]: /microsoft-edge/devtools-guide-chromium/media/css-console-command-menu-rendering.msft.png "図 1: コマンドメニュー"  
[ImagePrintMode]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-qs-rendering-emulate-css-media-print.msft.png "図 2: 印刷プレビューモード"  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール"  
[DevToolsCSSGetStarted]: /microsoft-edge/devtools-guide-chromium/css/index "CSS の表示と変更を始める"  

[MDNUsingMediaQueries]: https://developer.mozilla.org/docs/Web/CSS/Media_Queries/Using_media_queries "メディアクエリを使用する |MDN"  

> [!NOTE]
> <span data-ttu-id="ef970-122">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="ef970-122">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="ef970-123">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/css/print-preview)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="ef970-123">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/css/print-preview) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="ef970-125">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="ef970-125">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
