---
description: '[レンダリング] タブを開き、"print" > "CSS メディアのエミュレート" を選択します。'
title: Microsoft Edge の DevTools を印刷プレビューモード (CSS 印刷メディアの種類) に強制する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: d4e8e06d60461ac4cdcab8686a18a0698d52f6e3
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125119"
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

# <span data-ttu-id="a5f81-104">Microsoft Edge の DevTools を印刷プレビューモード (CSS 印刷メディアの種類) に強制する</span><span class="sxs-lookup"><span data-stu-id="a5f81-104">Force Microsoft Edge DevTools into Print Preview mode (CSS Print Media Type)</span></span>  

<span data-ttu-id="a5f81-105">[印刷メディアクエリ][MDNUsingMediaQueries]は、ページがどのように印刷されるかを制御します。</span><span class="sxs-lookup"><span data-stu-id="a5f81-105">The [print media query][MDNUsingMediaQueries] controls how your page looks when printed.</span></span>  <span data-ttu-id="a5f81-106">ページを印刷プレビューモードにするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a5f81-106">To force your page into print preview mode:</span></span>  

1.  <span data-ttu-id="a5f81-107">`Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows, Linux \) または `Command` + `Shift` + `P` \ **Command Menu**(macOS \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5f81-107">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="コマンドメニュー" lightbox="../media/css-console-command-menu-rendering.msft.png":::
       <span data-ttu-id="a5f81-109">**コマンドメニュー**</span><span class="sxs-lookup"><span data-stu-id="a5f81-109">The **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="a5f81-110">「」と入力し `rendering` 、[レンダリングの **表示**] を選択して、を選択し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="a5f81-110">Type `rendering`, choose **Show Rendering**, and then select `Enter`.</span></span>  
1.  <span data-ttu-id="a5f81-111">[ **CSS メディアのエミュレート** ] で [ **印刷**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a5f81-111">Under **Emulate CSS media** choose **print**.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-qs-rendering-emulate-css-media-print.msft.png" alt-text="コマンドメニュー" lightbox="../media/css-elements-styles-qs-rendering-emulate-css-media-print.msft.png":::
       <span data-ttu-id="a5f81-113">印刷プレビューモード</span><span class="sxs-lookup"><span data-stu-id="a5f81-113">Print preview mode</span></span>  
    :::image-end:::  
    
<span data-ttu-id="a5f81-114">ここでは、他の web ページと同じように、CSS を表示したり変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="a5f81-114">From here, you can view and change your CSS, like any other web page.</span></span>  <span data-ttu-id="a5f81-115">「 [CSS の表示と変更」の「使用を開始する」を][DevToolsCSSGetStarted]参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5f81-115">See [Get Started With Viewing And Changing CSS][DevToolsCSSGetStarted].</span></span>  

## <span data-ttu-id="a5f81-116">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="a5f81-116">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  
[DevToolsCSSGetStarted]: ./index.md "CSS の表示と変更の概要 |Microsoft ドキュメント"  

[MDNUsingMediaQueries]: https://developer.mozilla.org/docs/Web/CSS/Media_Queries/Using_media_queries "メディアクエリを使用する |MDN"  

> [!NOTE]
> <span data-ttu-id="a5f81-120">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="a5f81-120">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="a5f81-121">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/css/print-preview) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="a5f81-121">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/css/print-preview) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="a5f81-123">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="a5f81-123">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
