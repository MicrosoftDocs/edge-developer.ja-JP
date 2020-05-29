---
title: ライブ式を使って JavaScript の式値をリアルタイムで見る
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: c388e44ca5507dd88ad9ad7b7ee985e658dfc569
ms.sourcegitcommit: 5cdc1626d5581b79c0f2ac4ea62e7f1974ebfa57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "10601741"
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





# <span data-ttu-id="75407-103">ライブ式を使って JavaScript の式値をリアルタイムで見る</span><span class="sxs-lookup"><span data-stu-id="75407-103">Watch JavaScript Expression Values In Real-Time With Live Expressions</span></span>   

  

<span data-ttu-id="75407-104">コンソールで同じ JavaScript 式を繰り返し入力したことがわかった場合は、**ライブ式**の作成が簡単になることがあります。</span><span class="sxs-lookup"><span data-stu-id="75407-104">If you find yourself typing the same JavaScript expression in the Console repeatedly, you might find it easier to create a **Live Expression**.</span></span>  <span data-ttu-id="75407-105">**ライブ式**で式を1回入力し、本体の先頭に固定します。</span><span class="sxs-lookup"><span data-stu-id="75407-105">With **Live Expressions** you type an expression once and then pin it to the top of your Console.</span></span>  <span data-ttu-id="75407-106">この式の値は、ほぼリアルタイムで更新されます。</span><span class="sxs-lookup"><span data-stu-id="75407-106">The value of the expression updates in near real-time.</span></span>  

## <span data-ttu-id="75407-107">ライブ式を作成する</span><span class="sxs-lookup"><span data-stu-id="75407-107">Create a Live Expression</span></span>   

1.  <span data-ttu-id="75407-108">[本体を開き][DevToolsConsoleReferenceOpenConsole]ます。</span><span class="sxs-lookup"><span data-stu-id="75407-108">[Open the Console][DevToolsConsoleReferenceOpenConsole].</span></span>  
1.  <span data-ttu-id="75407-109">[**ライブ式** ![ の作成] をクリックし ][ImageCreateLiveExpressionIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="75407-109">Click **Create Live Expression** ![Create Live Expression][ImageCreateLiveExpressionIcon].</span></span>  <span data-ttu-id="75407-110">[**ライブ式**] テキストボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="75407-110">The **Live Expression** text box appears.</span></span>  
    
    > ##### <span data-ttu-id="75407-111">図 1</span><span class="sxs-lookup"><span data-stu-id="75407-111">Figure 1</span></span>  
    > <span data-ttu-id="75407-112">`document.activeElement`[**ライブ式**] テキストボックスへの入力</span><span class="sxs-lookup"><span data-stu-id="75407-112">Typing `document.activeElement` into the **Live Expression** text box</span></span>  
    > ![ライブ式のテキストボックスへの "activeElement 要素の入力][ImageLiveExpressionTextbox]  
    
1.  <span data-ttu-id="75407-114">`Control` + `Enter` 式を保存するには、「\ (Windows \)」または「 `Command` + `Enter` \ (macOS \)」を入力するか、[**ライブ式**] テキストボックスの外側をクリックします。</span><span class="sxs-lookup"><span data-stu-id="75407-114">Type `Control`+`Enter` \(Windows\) or `Command`+`Enter` \(macOS\) to save the expression, or click outside of the **Live Expression** text box.</span></span>  

<!--todo: add reference open console (open the console) section when available  -->  

 



<!-- image links -->  

[ImageCreateLiveExpressionIcon]: /microsoft-edge/devtools-guide-chromium/media/create-live-expression-icon.msft.png  

[ImageLiveExpressionTextbox]: /microsoft-edge/devtools-guide-chromium/media/console-create-live-expression.msft.png "図 1: [ライブ式] テキストボックスへの "ドキュメントの入力" 要素"  

<!-- links -->  

[DevToolsConsoleReferenceOpenConsole]: /microsoft-edge/devtools-guide-chromium/console/reference#open-the-console "本体本体のリファレンスを開く"  

> [!NOTE]
> <span data-ttu-id="75407-117">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="75407-117">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="75407-118">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/console/live-expressions)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="75407-118">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/live-expressions) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="75407-120">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="75407-120">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
