---
title: Microsoft Edge DevTools で JavaScript を無効にする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 587f4780432b1b2b964462d2d7f5779f447f1313
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10982920"
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





# <span data-ttu-id="a049d-103">Microsoft Edge DevTools で JavaScript を無効にする</span><span class="sxs-lookup"><span data-stu-id="a049d-103">Disable JavaScript with Microsoft Edge DevTools</span></span>   



<span data-ttu-id="a049d-104">JavaScript が無効になっている場合に、web ページの外観と動作を確認するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a049d-104">To see how a web page looks and behaves when JavaScript is disabled.</span></span>  

1.  <span data-ttu-id="a049d-105">[Microsoft Edge DevTools を開き][DevToolsOpen]ます。</span><span class="sxs-lookup"><span data-stu-id="a049d-105">[Open Microsoft Edge DevTools][DevToolsOpen].</span></span>  
1.  <span data-ttu-id="a049d-106">`Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows \) または `Command` + `Shift` + `P` \ **Command Menu**(macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="a049d-106">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    :::image type="complex" source="../media/javascript-console-command.msft.png" alt-text="コマンドメニュー" lightbox="../media/javascript-console-command.msft.png":::
       <span data-ttu-id="a049d-108">**コマンドメニュー**</span><span class="sxs-lookup"><span data-stu-id="a049d-108">The **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="a049d-109">入力を開始し、[JavaScript を無効にする] を `javascript` 選択して、キーを押してコマンドを実行し**Disable JavaScript** `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="a049d-109">Start typing `javascript`, select **Disable JavaScript**, and then press `Enter` to run the command.</span></span>  <span data-ttu-id="a049d-110">JavaScript が無効になりました。</span><span class="sxs-lookup"><span data-stu-id="a049d-110">JavaScript is now disabled.</span></span>  
    
    :::image type="complex" source="../media/javascript-console-command-javascript.msft.png" alt-text="コマンドメニューの [JavaScript を無効にする] を選択します。" lightbox="../media/javascript-console-command-javascript.msft.png":::
       <span data-ttu-id="a049d-112">**コマンドメニュー**の [ **JavaScript を無効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a049d-112">Select **Disable JavaScript** in the **Command Menu**</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="a049d-113">[ **ソース** ] の横にある黄色の警告アイコンは、JavaScript が無効になっていることを通知します。</span><span class="sxs-lookup"><span data-stu-id="a049d-113">The yellow warning icon next to **Sources** reminds you that JavaScript is disabled.</span></span>  
    
    :::image type="complex" source="../media/javascript-console-javascript-disabled-warning.msft.png" alt-text="ソースの横にある警告アイコン" lightbox="../media/javascript-console-javascript-disabled-warning.msft.png":::
       <span data-ttu-id="a049d-115">**ソース**の横にある警告アイコン</span><span class="sxs-lookup"><span data-stu-id="a049d-115">The warning icon next to **Sources**</span></span>  
    :::image-end:::  
    
<span data-ttu-id="a049d-116">DevTools が開いている限り、JavaScript はこのタブでは無効のままです。</span><span class="sxs-lookup"><span data-stu-id="a049d-116">JavaScript remains disabled in this tab for as long as you have DevTools open.</span></span>  

<span data-ttu-id="a049d-117">読み込み中にページが JavaScript に依存するかどうかとその方法を確認するには、ページの再読み込みが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="a049d-117">You may want to reload the page to see if and how the page depends on JavaScript while loading.</span></span>  

<span data-ttu-id="a049d-118">JavaScript を再び有効にするには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="a049d-118">To re-enable JavaScript, complete the following actions.</span></span>  

*   <span data-ttu-id="a049d-119">もう一度 **コマンドメニュー** を開き、コマンドを実行し `Enable JavaScript` ます。</span><span class="sxs-lookup"><span data-stu-id="a049d-119">Open the **Command Menu** again and run the `Enable JavaScript` command.</span></span>  
*   <span data-ttu-id="a049d-120">DevTools を閉じます。</span><span class="sxs-lookup"><span data-stu-id="a049d-120">Close DevTools.</span></span>  

<!--  
## Feedback   


-->  

<!-- links -->  

[DevToolsOpen]: ../open.md "Microsoft Edge DevTools を開く |Microsoft ドキュメント"  

> [!NOTE]
> <span data-ttu-id="a049d-122">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="a049d-122">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="a049d-123">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/disable) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="a049d-123">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/disable) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="a049d-125">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="a049d-125">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
