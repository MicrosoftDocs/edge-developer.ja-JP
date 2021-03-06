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

# <a name="force-microsoft-edge-devtools-into-print-preview-mode"></a><span data-ttu-id="ff7af-104">Microsoft Edge DevTools を印刷プレビュー モードに強制する</span><span class="sxs-lookup"><span data-stu-id="ff7af-104">Force Microsoft Edge DevTools into Print Preview mode</span></span>  

<span data-ttu-id="ff7af-105">印刷 [メディア クエリは、][MDNUsingMediaQueries] 印刷時のページの外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="ff7af-105">The [print media query][MDNUsingMediaQueries] controls how your page looks when printed.</span></span>  <span data-ttu-id="ff7af-106">ページを印刷プレビュー モードに設定するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="ff7af-106">To force your page into print preview mode:</span></span>  

1.  <span data-ttu-id="ff7af-107">`Control`+`Shift`+`P` \(Windows, Linux\) または `Command`+`Shift`+`P` \(macOS\) を選択して、**コマンド メニュー** を開きます。</span><span class="sxs-lookup"><span data-stu-id="ff7af-107">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="コマンド メニュー" lightbox="../media/css-console-command-menu-rendering.msft.png":::
       <span data-ttu-id="ff7af-109">**コマンド メニュー**</span><span class="sxs-lookup"><span data-stu-id="ff7af-109">The **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ff7af-110">[レンダリング `rendering` の表示] **を選択し**、[選択] を選択します `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="ff7af-110">Type `rendering`, choose **Show Rendering**, and then select `Enter`.</span></span>  
1.  <span data-ttu-id="ff7af-111">[CSS **メディアのエミュレート] で**、[印刷] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="ff7af-111">Under **Emulate CSS media**, choose **print**.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-qs-rendering-emulate-css-media-print.msft.png" alt-text="印刷プレビュー モード" lightbox="../media/css-elements-styles-qs-rendering-emulate-css-media-print.msft.png":::
       <span data-ttu-id="ff7af-113">印刷プレビュー モード</span><span class="sxs-lookup"><span data-stu-id="ff7af-113">Print preview mode</span></span>  
    :::image-end:::  
    
<span data-ttu-id="ff7af-114">ここから、他の Web ページと同様に CSS を表示および変更できます。</span><span class="sxs-lookup"><span data-stu-id="ff7af-114">From here, you may display and change your CSS, like any other web page.</span></span>  <span data-ttu-id="ff7af-115">[CSS の [表示と変更の開始] に移動します][DevToolsCSSGetStarted]。</span><span class="sxs-lookup"><span data-stu-id="ff7af-115">Navigate to [Get Started With Viewing And Changing CSS][DevToolsCSSGetStarted].</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="ff7af-116">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="ff7af-116">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (クロム) 開発者向け|Microsoft Docs"  
[DevToolsCSSGetStarted]: ./index.md "CSS ファイルの表示と変更の|Microsoft Docs"  

[MDNUsingMediaQueries]: https://developer.mozilla.org/docs/Web/CSS/Media_Queries/Using_media_queries "メディア クエリの使用|MDN"  

> [!NOTE]
> <span data-ttu-id="ff7af-120">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="ff7af-120">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="ff7af-121">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/css/print-preview) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="ff7af-121">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/css/print-preview) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="ff7af-123">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="ff7af-123">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
