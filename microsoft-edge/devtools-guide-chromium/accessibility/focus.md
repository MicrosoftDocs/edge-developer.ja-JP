---
description: コンソールを開き、Live 式を作成し、式を document.activeElement に設定します。
title: フォーカスされている要素を追跡する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 2c2040c690441fb33c802cf454dc7a1e3f33c494
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439171"
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

# <a name="track-which-element-has-focus"></a><span data-ttu-id="d88e8-104">フォーカスされている要素を追跡する</span><span class="sxs-lookup"><span data-stu-id="d88e8-104">Track which element has focus</span></span>  

<span data-ttu-id="d88e8-105">ページのキーボード ナビゲーションアクセシビリティをテストするとします。</span><span class="sxs-lookup"><span data-stu-id="d88e8-105">Suppose that you are testing the keyboard navigation accessibility of a page.</span></span>  <span data-ttu-id="d88e8-106">キーを使用してページを移動すると、フォーカスのある要素が非表示のため、フォーカス リング `Tab` が表示されなくなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d88e8-106">When navigating the page with the `Tab` key, the focus ring sometimes disappears because the element that has focus is hidden.</span></span>  

<span data-ttu-id="d88e8-107">DevTools でフォーカスされた要素を追跡するには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="d88e8-107">Complete the following actions to track the focused element in DevTools.</span></span>  

1.  <span data-ttu-id="d88e8-108">コンソールを **開きます**。</span><span class="sxs-lookup"><span data-stu-id="d88e8-108">Open the **Console**.</span></span>  
1.  <span data-ttu-id="d88e8-109">[Live **Expression \(** Create ![ Live Expression ](../media/create-live-expression-icon.msft.png) \] を選択します)。</span><span class="sxs-lookup"><span data-stu-id="d88e8-109">Choose **Create Live Expression** \(![Create Live Expression](../media/create-live-expression-icon.msft.png)\).</span></span>  
    
    :::image type="complex" source="../media/accessibility-console-create-live-expression-empty.msft.png" alt-text="Live 式の作成" lightbox="../media/accessibility-console-create-live-expression-empty.msft.png":::
       <span data-ttu-id="d88e8-111">Live 式の作成</span><span class="sxs-lookup"><span data-stu-id="d88e8-111">Create a Live Expression</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="d88e8-112">「`document.activeElement`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="d88e8-112">Type `document.activeElement`.</span></span>  
1.  <span data-ttu-id="d88e8-113">保存する Live 式 UI **の外部を** 選択します。</span><span class="sxs-lookup"><span data-stu-id="d88e8-113">Choose outside of the **Live Expression** UI to save.</span></span>  
    
<span data-ttu-id="d88e8-114">次に示す値 `document.activeElement` は、式の結果です。</span><span class="sxs-lookup"><span data-stu-id="d88e8-114">The value displayed below `document.activeElement` is the result of the expression.</span></span>  

<span data-ttu-id="d88e8-115">この式は常にフォーカスされた要素を表すので、フォーカスがある要素を常に追跡できます。</span><span class="sxs-lookup"><span data-stu-id="d88e8-115">Since that expression always represents the focused element, you now have a way to always keep track of which element has focus.</span></span>  

*   <span data-ttu-id="d88e8-116">結果にカーソルを合わせると、ビューポート内のフォーカスされた要素が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="d88e8-116">Hover on the result to highlight the focused element in the viewport.</span></span>  
*   <span data-ttu-id="d88e8-117">結果にカーソルを合わせると、コンテキスト メニュー \(右クリック\) を開き、[要素] パネルで [表示] を選択して、要素ツールの DOM ツリーに要素を**表示**します。</span><span class="sxs-lookup"><span data-stu-id="d88e8-117">Hover on the result, open the contextual menu \(right-click\), and choose **Reveal in Elements panel** to show the element in the DOM Tree on the **Elements** tool.</span></span>  
*   <span data-ttu-id="d88e8-118">結果にカーソルを置き、コンテキスト メニュー \(右クリック\) を開き、[グローバル変数として格納] を選択して、コンソールで使用できるノードへの変数参照を作成**します**。</span><span class="sxs-lookup"><span data-stu-id="d88e8-118">Hover on the result, open the contextual menu \(right-click\), and choose **Store as global variable** to create a variable reference to the node that you are able to use in the **Console**.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="d88e8-119">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="d88e8-119">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

> [!NOTE]
> <span data-ttu-id="d88e8-120">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="d88e8-120">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="d88e8-121">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/accessibility/focus) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="d88e8-121">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/accessibility/focus) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="d88e8-123">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="d88e8-123">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
