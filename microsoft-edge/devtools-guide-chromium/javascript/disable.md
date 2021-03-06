---
description: コマンド メニューを開き、[JavaScript を無効にする] コマンドを実行します。
title: Microsoft Edge DevTools で JavaScript を無効にする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 2067944fa17c332dd15ffb3ef97afe02d35685ed
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398561"
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

# <a name="disable-javascript-with-microsoft-edge-devtools"></a><span data-ttu-id="7ba16-104">Microsoft Edge DevTools で JavaScript を無効にする</span><span class="sxs-lookup"><span data-stu-id="7ba16-104">Disable JavaScript with Microsoft Edge DevTools</span></span>  

<span data-ttu-id="7ba16-105">JavaScript が無効になっている場合の Web ページの外観と動作を表示するには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="7ba16-105">Complete the following actions to display how a webpage looks and behaves when JavaScript is disabled.</span></span>  

1.  <span data-ttu-id="7ba16-106">[Microsoft Edge DevTools を開きます][DevToolsOpen]。</span><span class="sxs-lookup"><span data-stu-id="7ba16-106">[Open Microsoft Edge DevTools][DevToolsOpen].</span></span>  
1.  <span data-ttu-id="7ba16-107">`Control`+`Shift`+`P` \(Windows, Linux\) または `Command`+`Shift`+`P` \(macOS\) を選択して、**コマンド メニュー** を開きます。</span><span class="sxs-lookup"><span data-stu-id="7ba16-107">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    :::image type="complex" source="../media/javascript-console-command.msft.png" alt-text="コマンド メニュー" lightbox="../media/javascript-console-command.msft.png":::
       <span data-ttu-id="7ba16-109">**コマンド メニュー**</span><span class="sxs-lookup"><span data-stu-id="7ba16-109">The **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="7ba16-110">入力を開始 `javascript` し **、[JavaScript を無効**にする] を選択し、コマンド `Enter` を実行する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="7ba16-110">Start typing `javascript`, choose **Disable JavaScript**, and then select `Enter` to run the command.</span></span>  <span data-ttu-id="7ba16-111">JavaScript が無効になりました。</span><span class="sxs-lookup"><span data-stu-id="7ba16-111">JavaScript is now disabled.</span></span>  
    
    :::image type="complex" source="../media/javascript-console-command-javascript.msft.png" alt-text="コマンド メニューで [JavaScript を無効にする] を選択します。" lightbox="../media/javascript-console-command-javascript.msft.png":::
       <span data-ttu-id="7ba16-113">コマンド **メニューで [JavaScript** を無効にする] **を選択します。**</span><span class="sxs-lookup"><span data-stu-id="7ba16-113">Choose **Disable JavaScript** in the **Command Menu**</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="7ba16-114">[ソース] の横にある黄色の **警告** アイコンは、JavaScript が無効になっていることを通知します。</span><span class="sxs-lookup"><span data-stu-id="7ba16-114">The yellow warning icon next to **Sources** reminds you that JavaScript is disabled.</span></span>  
    
    :::image type="complex" source="../media/javascript-console-javascript-disabled-warning.msft.png" alt-text="[ソース] の横にある警告アイコン" lightbox="../media/javascript-console-javascript-disabled-warning.msft.png":::
       <span data-ttu-id="7ba16-116">[ソース] の横にある **警告アイコン**</span><span class="sxs-lookup"><span data-stu-id="7ba16-116">The warning icon next to **Sources**</span></span>  
    :::image-end:::  
    
<span data-ttu-id="7ba16-117">DevTools を開いている限り、JavaScript はタブで無効なままです。</span><span class="sxs-lookup"><span data-stu-id="7ba16-117">JavaScript remains disabled in the tab for as long as you have DevTools open.</span></span>  

<span data-ttu-id="7ba16-118">ページを更新して、読み込み中に Web ページが JavaScript に依存するかどうかと方法を確認できます。</span><span class="sxs-lookup"><span data-stu-id="7ba16-118">You may want to refresh the page to review if and how the webpage depends on JavaScript while loading.</span></span>  

<span data-ttu-id="7ba16-119">JavaScript を再び有効にするには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="7ba16-119">To re-enable JavaScript, complete the following actions.</span></span>  

*   <span data-ttu-id="7ba16-120">コマンド メニュー **を再度開** き、コマンドを実行 `Enable JavaScript` します。</span><span class="sxs-lookup"><span data-stu-id="7ba16-120">Open the **Command Menu** again and run the `Enable JavaScript` command.</span></span>  
*   <span data-ttu-id="7ba16-121">DevTools を閉じます。</span><span class="sxs-lookup"><span data-stu-id="7ba16-121">Close DevTools.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="7ba16-122">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="7ba16-122">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsOpen]: ../open/index.md "Microsoft Edge DevTools を開く | Microsoft Docs"  

> [!NOTE]
> <span data-ttu-id="7ba16-124">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="7ba16-124">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="7ba16-125">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/disable) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="7ba16-125">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/disable) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="7ba16-127">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="7ba16-127">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
