---
description: コンソールに同じ JavaScript 式を繰り返し入力する場合は、代わりに Live 式を試してください。
title: Live 式を使用して JavaScript 式の値をリアルタイムで確認する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: af920de1c395489dc09b83f3cc0f24814c4f5cbe
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439227"
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

# <a name="watch-javascript-expression-values-in-real-time-with-live-expressions"></a><span data-ttu-id="f72e8-104">Live 式を使用して JavaScript 式の値をリアルタイムで確認する</span><span class="sxs-lookup"><span data-stu-id="f72e8-104">Watch JavaScript expression values in real-time with Live Expressions</span></span>  

<span data-ttu-id="f72e8-105">コンソールで同じ JavaScript 式を繰り返し入力すると、Live 式の作成が簡単になる **場合があります**。</span><span class="sxs-lookup"><span data-stu-id="f72e8-105">If you find yourself typing the same JavaScript expression in the Console repeatedly, you may find it easier to create a **Live Expression**.</span></span>  <span data-ttu-id="f72e8-106">Live **Expression を使用すると** 、一度式を入力し、本体の上部にピン留めします。</span><span class="sxs-lookup"><span data-stu-id="f72e8-106">With **Live Expressions** you type an expression once and then pin it to the top of your Console.</span></span>  <span data-ttu-id="f72e8-107">式の値は、ほぼリアルタイムで更新されます。</span><span class="sxs-lookup"><span data-stu-id="f72e8-107">The value of the expression updates in near real-time.</span></span>  

## <a name="create-a-live-expression"></a><span data-ttu-id="f72e8-108">Live 式の作成</span><span class="sxs-lookup"><span data-stu-id="f72e8-108">Create a Live Expression</span></span>  

1.  <span data-ttu-id="f72e8-109">[コンソールを開きます][DevToolsConsoleReferenceOpenConsole]。</span><span class="sxs-lookup"><span data-stu-id="f72e8-109">[Open the Console][DevToolsConsoleReferenceOpenConsole].</span></span>  
1.  <span data-ttu-id="f72e8-110">[Live **Expression \(** Create ![ Live Expression ](../media/create-live-expression-icon.msft.png) \] を選択します)。</span><span class="sxs-lookup"><span data-stu-id="f72e8-110">Choose **Create Live Expression** \(![Create Live Expression](../media/create-live-expression-icon.msft.png)\).</span></span>  <span data-ttu-id="f72e8-111">[Live **Expression]** テキスト ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f72e8-111">The **Live Expression** text box appears.</span></span>  
    
    :::image type="complex" source="../media/console-create-live-expression.msft.png" alt-text="[Live 式] テキスト ボックスに document.activeElement と入力する" lightbox="../media/console-create-live-expression.msft.png":::
       <span data-ttu-id="f72e8-113">[Live `document.activeElement` 式] **テキスト ボックスに入力** する</span><span class="sxs-lookup"><span data-stu-id="f72e8-113">Typing `document.activeElement` into the **Live Expression** text box</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f72e8-114">`Control` + `Enter` \(Windows,Linux\) または `Command` + `Enter` \(macOS\) を選択して式を保存するか、[Live 式] テキスト ボックスの外側を選択します。</span><span class="sxs-lookup"><span data-stu-id="f72e8-114">Select `Control`+`Enter` \(Windows, Linux\) or `Command`+`Enter` \(macOS\) to save the expression, or choose outside of the **Live Expression** textbox.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="f72e8-115">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="f72e8-115">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsConsoleReferenceOpenConsole]: ./reference.md#open-the-console "コンソール - コンソール リファレンス を開|Microsoft Docs"  

> [!NOTE]
> <span data-ttu-id="f72e8-117">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="f72e8-117">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="f72e8-118">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/console/live-expressions) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="f72e8-118">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/live-expressions) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="f72e8-120">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="f72e8-120">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
