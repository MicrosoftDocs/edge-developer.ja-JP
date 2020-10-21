---
description: 本体を開き、ライブ式を作成して、式を "activeElement" に設定します。
title: フォーカスされている要素を追跡する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: a0d0861494db87e546443c0f3a1d4f531412300c
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125308"
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

# <span data-ttu-id="cb407-104">フォーカスされている要素を追跡する</span><span class="sxs-lookup"><span data-stu-id="cb407-104">Track Which Element Has Focus</span></span>  

<span data-ttu-id="cb407-105">ページのキーボードナビゲーションのアクセシビリティをテストするとします。</span><span class="sxs-lookup"><span data-stu-id="cb407-105">Suppose that you are testing the keyboard navigation accessibility of a page.</span></span>  <span data-ttu-id="cb407-106">キーを使用してページ内を移動するときに `Tab` 、フォーカスがある要素が非表示になることがあるため、フォーカスリングが消えることがあります。</span><span class="sxs-lookup"><span data-stu-id="cb407-106">When navigating the page with the `Tab` key, the focus ring sometimes disappears because the element that has focus is hidden.</span></span>  

<span data-ttu-id="cb407-107">DevTools で優先要素を追跡するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="cb407-107">Complete the following actions to track the focused element in DevTools.</span></span>  

1.  <span data-ttu-id="cb407-108">**本体**を開きます。</span><span class="sxs-lookup"><span data-stu-id="cb407-108">Open the **Console**.</span></span>  
1.  <span data-ttu-id="cb407-109">[ **ライブ式の作成** ] \ ( ![ ライブ式 ][ImageCreateIcon] の作成 \) を選びます。</span><span class="sxs-lookup"><span data-stu-id="cb407-109">Choose **Create Live Expression** \(![Create Live Expression][ImageCreateIcon]\).</span></span>  
    
    :::image type="complex" source="../media/accessibility-console-create-live-expression-empty.msft.png" alt-text="ライブ式を作成する" lightbox="../media/accessibility-console-create-live-expression-empty.msft.png":::
       <span data-ttu-id="cb407-111">ライブ式を作成する</span><span class="sxs-lookup"><span data-stu-id="cb407-111">Create a Live Expression</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="cb407-112">「`document.activeElement`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="cb407-112">Type `document.activeElement`.</span></span>  
1.  <span data-ttu-id="cb407-113">**ライブ式**UI の外側をクリックして保存します。</span><span class="sxs-lookup"><span data-stu-id="cb407-113">Click outside of the **Live Expression** UI to save.</span></span>  
    
<span data-ttu-id="cb407-114">以下に表示される値 `document.activeElement` は、式の結果です。</span><span class="sxs-lookup"><span data-stu-id="cb407-114">The value that you see below `document.activeElement` is the result of the expression.</span></span>  

<span data-ttu-id="cb407-115">この式は常に優先要素を表しているため、フォーカスがある要素を常に追跡する方法が用意されました。</span><span class="sxs-lookup"><span data-stu-id="cb407-115">Since that expression always represents the focused element, you now have a way to always keep track of which element has focus.</span></span>  

*   <span data-ttu-id="cb407-116">結果にマウスポインターを合わせて、ビューポート内の優先要素を強調表示します。</span><span class="sxs-lookup"><span data-stu-id="cb407-116">Hover over the result to highlight the focused element in the viewport.</span></span>  
*   <span data-ttu-id="cb407-117">結果を右クリックし、[要素 **パネルで** 表示] を選択して、 **[要素] パネルの** DOM ツリーに要素を表示します。</span><span class="sxs-lookup"><span data-stu-id="cb407-117">Right-click the result and choose **Reveal in Elements panel** to show the element in the DOM Tree on the **Elements** panel.</span></span>  
*   <span data-ttu-id="cb407-118">結果を右クリックし、[ **グローバル変数として保存** ] を選択して、 **コンソール**で使うことができるノードへの可変参照を作成します。</span><span class="sxs-lookup"><span data-stu-id="cb407-118">Right-click the result and choose **Store as global variable** to create a variable reference to the node that you are able to use in the **Console**.</span></span>  

## <span data-ttu-id="cb407-119">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="cb407-119">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageCreateIcon]: ../media/create-live-expression-icon.msft.png  

<!-- links -->  

> [!NOTE]
> <span data-ttu-id="cb407-120">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="cb407-120">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="cb407-121">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/accessibility/focus) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="cb407-121">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/accessibility/focus) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="cb407-123">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="cb407-123">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
