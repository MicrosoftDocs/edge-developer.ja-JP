---
title: どの要素にフォーカスがあるかを追跡する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/18/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: a1bcb7e97357d1348b363ecd4842d1b6a78feb45
ms.sourcegitcommit: 8bfa239274e7a4856b961b9cf163b08d96463c10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2020
ms.locfileid: "10581532"
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





# <span data-ttu-id="1e822-103">どの要素にフォーカスがあるかを追跡する</span><span class="sxs-lookup"><span data-stu-id="1e822-103">Track Which Element Has Focus</span></span>   



<span data-ttu-id="1e822-104">ページのキーボードナビゲーションのアクセシビリティをテストするとします。</span><span class="sxs-lookup"><span data-stu-id="1e822-104">Suppose that you are testing the keyboard navigation accessibility of a page.</span></span>  <span data-ttu-id="1e822-105">キーを使用してページ内を移動するときに `Tab` 、フォーカスがある要素が非表示になることがあるため、フォーカスリングが消えることがあります。</span><span class="sxs-lookup"><span data-stu-id="1e822-105">When navigating the page with the `Tab` key, the focus ring sometimes disappears because the element that has focus is hidden.</span></span>  <span data-ttu-id="1e822-106">DevTools で優先要素を追跡するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1e822-106">To track the focused element in DevTools:</span></span>  

1.  <span data-ttu-id="1e822-107">**本体**を開きます。</span><span class="sxs-lookup"><span data-stu-id="1e822-107">Open the **Console**.</span></span>  
1.  <span data-ttu-id="1e822-108">[**ライブ式** ![ の作成] をクリックし ][ImageCreateIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="1e822-108">Click **Create Live Expression** ![Create Live Expression][ImageCreateIcon].</span></span>  

    > ##### <span data-ttu-id="1e822-109">図 1</span><span class="sxs-lookup"><span data-stu-id="1e822-109">Figure 1</span></span>  
    > <span data-ttu-id="1e822-110">**ライブ式**の作成</span><span class="sxs-lookup"><span data-stu-id="1e822-110">Creating a **Live Expression**</span></span>  
    > ![ライブ式の作成][ImageLiveExpression]  
    
1.  <span data-ttu-id="1e822-112">「`document.activeElement`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="1e822-112">Type `document.activeElement`.</span></span>
1.  <span data-ttu-id="1e822-113">**ライブ式**UI の外側をクリックして保存します。</span><span class="sxs-lookup"><span data-stu-id="1e822-113">Click outside of the **Live Expression** UI to save.</span></span>

<span data-ttu-id="1e822-114">以下に表示される値 `document.activeElement` は、式の結果です。</span><span class="sxs-lookup"><span data-stu-id="1e822-114">The value that you see below `document.activeElement` is the result of the expression.</span></span>  
<span data-ttu-id="1e822-115">この式は常に優先要素を表しているため、フォーカスがある要素を常に追跡する方法が用意されました。</span><span class="sxs-lookup"><span data-stu-id="1e822-115">Since that expression always represents the focused element, you now have a way to always keep track of which element has focus.</span></span>  

*   <span data-ttu-id="1e822-116">結果にマウスポインターを合わせて、ビューポート内の優先要素を強調表示します。</span><span class="sxs-lookup"><span data-stu-id="1e822-116">Hover over the result to highlight the focused element in the viewport.</span></span>  
*   <span data-ttu-id="1e822-117">結果を右クリックし、[要素**パネルで**表示] を選択して、 **[要素] パネルの**DOM ツリーに要素を表示します。</span><span class="sxs-lookup"><span data-stu-id="1e822-117">Right-click the result and select **Reveal in Elements panel** to show the element in the DOM Tree on the **Elements** panel.</span></span>  
*   <span data-ttu-id="1e822-118">結果を右クリックし、[**グローバル変数として保存**] を選択して、**コンソール**で使うことができるノードへの可変参照を作成します。</span><span class="sxs-lookup"><span data-stu-id="1e822-118">Right-click the result and select **Store as global variable** to create a variable reference to the node that you are able to use in the **Console**.</span></span>  

<!--## Feedback   -->  



<!-- image links -->  

[ImageCreateIcon]: /microsoft-edge/devtools-guide-chromium/media/create-live-expression-icon.msft.png  

[ImageLiveExpression]: /microsoft-edge/devtools-guide-chromium/media/accessibility-console-create-live-expression-empty.msft.png "図 1: ライブ式の作成"  

<!-- links -->  

> [!NOTE]
> <span data-ttu-id="1e822-120">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="1e822-120">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="1e822-121">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/accessibility/focus)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome devtools & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="1e822-121">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/accessibility/focus) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools & Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="1e822-123">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="1e822-123">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
