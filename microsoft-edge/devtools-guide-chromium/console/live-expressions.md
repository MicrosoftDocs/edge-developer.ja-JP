---
description: 同じ JavaScript 式をコンソールに繰り返し入力していることがわかった場合は、代わりにライブ式を試してください。
title: ライブ式で Real-Time で JavaScript の式値を見る
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: f6787455863f738d0fa4e014ca8fc318ad83a9cb
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125231"
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

# <span data-ttu-id="436bb-104">ライブ式で Real-Time で JavaScript の式値を見る</span><span class="sxs-lookup"><span data-stu-id="436bb-104">Watch JavaScript Expression Values In Real-Time With Live Expressions</span></span>  

<span data-ttu-id="436bb-105">コンソールで同じ JavaScript 式を繰り返し入力したことがわかった場合は、 **ライブ式**の作成が簡単になることがあります。</span><span class="sxs-lookup"><span data-stu-id="436bb-105">If you find yourself typing the same JavaScript expression in the Console repeatedly, you might find it easier to create a **Live Expression**.</span></span>  <span data-ttu-id="436bb-106">**ライブ式**で式を1回入力し、本体の先頭に固定します。</span><span class="sxs-lookup"><span data-stu-id="436bb-106">With **Live Expressions** you type an expression once and then pin it to the top of your Console.</span></span>  <span data-ttu-id="436bb-107">この式の値は、ほぼリアルタイムで更新されます。</span><span class="sxs-lookup"><span data-stu-id="436bb-107">The value of the expression updates in near real-time.</span></span>  

## <span data-ttu-id="436bb-108">ライブ式を作成する</span><span class="sxs-lookup"><span data-stu-id="436bb-108">Create a Live Expression</span></span>  

1.  <span data-ttu-id="436bb-109">[本体を開き][DevToolsConsoleReferenceOpenConsole]ます。</span><span class="sxs-lookup"><span data-stu-id="436bb-109">[Open the Console][DevToolsConsoleReferenceOpenConsole].</span></span>  
1.  <span data-ttu-id="436bb-110">[ **ライブ式の作成** ] \ ( ![ ライブ式 ][ImageCreateLiveExpressionIcon] の作成 \) を選びます。</span><span class="sxs-lookup"><span data-stu-id="436bb-110">Choose **Create Live Expression** \(![Create Live Expression][ImageCreateLiveExpressionIcon]\).</span></span>  <span data-ttu-id="436bb-111">[ **ライブ式** ] テキストボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="436bb-111">The **Live Expression** text box appears.</span></span>  
    
    :::image type="complex" source="../media/console-create-live-expression.msft.png" alt-text="ライブ式のテキストボックスへの &quot;activeElement 要素の入力" lightbox="../media/console-create-live-expression.msft.png":::
       <span data-ttu-id="436bb-113">`document.activeElement`[**ライブ式**] テキストボックスへの入力</span><span class="sxs-lookup"><span data-stu-id="436bb-113">Typing `document.activeElement` into the **Live Expression** text box</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="436bb-114">`Control` + `Enter` 式を保存するには、[\ (Windows, Linux \)] または [ `Command` + `Enter` \ (macOS \)] を選択します。または、[**ライブ式**] ボックスの外側を選択します。</span><span class="sxs-lookup"><span data-stu-id="436bb-114">Select `Control`+`Enter` \(Windows, Linux\) or `Command`+`Enter` \(macOS\) to save the expression, or choose outside of the **Live Expression** textbox.</span></span>  

## <span data-ttu-id="436bb-115">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="436bb-115">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageCreateLiveExpressionIcon]: ../media/create-live-expression-icon.msft.png  

<!-- links -->  

[DevToolsConsoleReferenceOpenConsole]: ./reference.md#open-the-console "本体本体のリファレンスを開く |Microsoft ドキュメント"  

> [!NOTE]
> <span data-ttu-id="436bb-117">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="436bb-117">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="436bb-118">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/console/live-expressions) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="436bb-118">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/live-expressions) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="436bb-120">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="436bb-120">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
