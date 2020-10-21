---
description: コマンドメニューを開き、[JavaScript を無効にする] コマンドを実行します。
title: Microsoft Edge DevTools で JavaScript を無効にする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 4a200e2faa303a12d46fe2daf7ba89226a985b1f
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "11124720"
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

# <span data-ttu-id="d3cb2-104">Microsoft Edge DevTools で JavaScript を無効にする</span><span class="sxs-lookup"><span data-stu-id="d3cb2-104">Disable JavaScript With Microsoft Edge DevTools</span></span>  

<span data-ttu-id="d3cb2-105">JavaScript が無効になっている場合に、web ページの外観と動作を確認するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="d3cb2-105">Complete the following actions to see how a web page looks and behaves when JavaScript is disabled.</span></span>  

1.  <span data-ttu-id="d3cb2-106">[Microsoft Edge DevTools を開き][DevToolsOpen]ます。</span><span class="sxs-lookup"><span data-stu-id="d3cb2-106">[Open Microsoft Edge DevTools][DevToolsOpen].</span></span>  
1.  <span data-ttu-id="d3cb2-107">`Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows, Linux \) または `Command` + `Shift` + `P` \ **Command Menu**(macOS \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="d3cb2-107">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    :::image type="complex" source="../media/javascript-console-command.msft.png" alt-text="コマンドメニュー" lightbox="../media/javascript-console-command.msft.png":::
       <span data-ttu-id="d3cb2-109">**コマンドメニュー**</span><span class="sxs-lookup"><span data-stu-id="d3cb2-109">The **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="d3cb2-110">入力を開始し `javascript` 、[ **JavaScript を無効**にする] を選択して、 `Enter` コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d3cb2-110">Start typing `javascript`, choose **Disable JavaScript**, and then select `Enter` to run the command.</span></span>  <span data-ttu-id="d3cb2-111">JavaScript が無効になりました。</span><span class="sxs-lookup"><span data-stu-id="d3cb2-111">JavaScript is now disabled.</span></span>  
    
    :::image type="complex" source="../media/javascript-console-command-javascript.msft.png" alt-text="コマンドメニュー" lightbox="../media/javascript-console-command-javascript.msft.png":::
       <span data-ttu-id="d3cb2-113">**コマンドメニュー**の [ **JavaScript を無効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d3cb2-113">Choose **Disable JavaScript** in the **Command Menu**</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="d3cb2-114">[ **ソース** ] の横にある黄色の警告アイコンは、JavaScript が無効になっていることを通知します。</span><span class="sxs-lookup"><span data-stu-id="d3cb2-114">The yellow warning icon next to **Sources** reminds you that JavaScript is disabled.</span></span>  
    
    :::image type="complex" source="../media/javascript-console-javascript-disabled-warning.msft.png" alt-text="コマンドメニュー" lightbox="../media/javascript-console-javascript-disabled-warning.msft.png":::
       <span data-ttu-id="d3cb2-116">**ソース**の横にある警告アイコン</span><span class="sxs-lookup"><span data-stu-id="d3cb2-116">The warning icon next to **Sources**</span></span>  
    :::image-end:::  
    
<span data-ttu-id="d3cb2-117">DevTools が開いている限り、タブ内の JavaScript は無効のままです。</span><span class="sxs-lookup"><span data-stu-id="d3cb2-117">JavaScript remains disabled in the tab for as long as you have DevTools open.</span></span>  

<span data-ttu-id="d3cb2-118">読み込み中にページが JavaScript に依存するかどうかとその方法を確認するには、ページの再読み込みが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="d3cb2-118">You may want to reload the page to see if and how the page depends on JavaScript while loading.</span></span>  

<span data-ttu-id="d3cb2-119">JavaScript を再び有効にするには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="d3cb2-119">To re-enable JavaScript, complete the following actions.</span></span>  

*   <span data-ttu-id="d3cb2-120">もう一度 **コマンドメニュー** を開き、コマンドを実行し `Enable JavaScript` ます。</span><span class="sxs-lookup"><span data-stu-id="d3cb2-120">Open the **Command Menu** again and run the `Enable JavaScript` command.</span></span>  
*   <span data-ttu-id="d3cb2-121">DevTools を閉じます。</span><span class="sxs-lookup"><span data-stu-id="d3cb2-121">Close DevTools.</span></span>  

## <span data-ttu-id="d3cb2-122">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="d3cb2-122">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsOpen]: ../open.md "Microsoft Edge DevTools を開く |Microsoft ドキュメント"  

> [!NOTE]
> <span data-ttu-id="d3cb2-124">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="d3cb2-124">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="d3cb2-125">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/disable) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="d3cb2-125">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/disable) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="d3cb2-127">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="d3cb2-127">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
