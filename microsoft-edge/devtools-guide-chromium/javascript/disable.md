---
description: コマンド メニューを開き、[JavaScript を無効にする] コマンドを実行します。
title: Microsoft Edge DevTools で JavaScript を無効にする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 665181b14e6fa5e86950a27822d52395f49f5b92
ms.sourcegitcommit: 16e2f7232196a57a70b979bbf8b663774b7ddc20
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/25/2021
ms.locfileid: "11519353"
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

# <a name="disable-javascript-with-microsoft-edge-devtools"></a><span data-ttu-id="79be3-104">Microsoft Edge DevTools で JavaScript を無効にする</span><span class="sxs-lookup"><span data-stu-id="79be3-104">Disable JavaScript with Microsoft Edge DevTools</span></span>  

<span data-ttu-id="79be3-105">ブラウザーで JavaScript がサポートされていない場合の Web ページの表示方法を確認するには、JavaScript を一時的にオフにします。</span><span class="sxs-lookup"><span data-stu-id="79be3-105">To review how your webpage renders when a browser doesn't have JavaScript support, temporarily turn off JavaScript.</span></span>

<span data-ttu-id="79be3-106">JavaScript をオフにした場合の Web ページの表示方法と動作を調べるには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="79be3-106">Complete the following actions to examine how a webpage displays and behaves when you turn off JavaScript.</span></span>  

1.  <span data-ttu-id="79be3-107">[Microsoft Edge DevTools を開きます][DevToolsOpen]。</span><span class="sxs-lookup"><span data-stu-id="79be3-107">[Open Microsoft Edge DevTools][DevToolsOpen].</span></span>  
1.  <span data-ttu-id="79be3-108">`Control`+`Shift`+`P` \(Windows, Linux\) または `Command`+`Shift`+`P` \(macOS\) を選択して、**コマンド メニュー** を開きます。</span><span class="sxs-lookup"><span data-stu-id="79be3-108">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    :::image type="complex" source="../media/javascript-console-command.msft.png" alt-text="コマンド メニュー" lightbox="../media/javascript-console-command.msft.png":::
       <span data-ttu-id="79be3-110">**コマンド メニュー**</span><span class="sxs-lookup"><span data-stu-id="79be3-110">The **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="79be3-111">入力を開始 `javascript` し **、[JavaScript を無効**にする] を選択し、コマンド `Enter` を実行する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="79be3-111">Start typing `javascript`, choose **Disable JavaScript**, and then select `Enter` to run the command.</span></span>  <span data-ttu-id="79be3-112">JavaScript が無効になりました。</span><span class="sxs-lookup"><span data-stu-id="79be3-112">JavaScript is now disabled.</span></span>  
    
    :::image type="complex" source="../media/javascript-console-command-javascript.msft.png" alt-text="コマンド メニューで [JavaScript を無効にする] を選択します。" lightbox="../media/javascript-console-command-javascript.msft.png":::
       <span data-ttu-id="79be3-114">コマンド **メニューで [JavaScript** を無効にする] **を選択します。**</span><span class="sxs-lookup"><span data-stu-id="79be3-114">Choose **Disable JavaScript** in the **Command Menu**</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="79be3-115">[ソース] の横にある黄色の **警告** アイコンは、JavaScript が無効になっていることを通知します。</span><span class="sxs-lookup"><span data-stu-id="79be3-115">The yellow warning icon next to **Sources** reminds you that JavaScript is disabled.</span></span>  
    
    :::image type="complex" source="../media/javascript-console-javascript-disabled-warning.msft.png" alt-text="[ソース] の横にある警告アイコン" lightbox="../media/javascript-console-javascript-disabled-warning.msft.png":::
       <span data-ttu-id="79be3-117">[ソース] の横にある **警告アイコン**</span><span class="sxs-lookup"><span data-stu-id="79be3-117">The warning icon next to **Sources**</span></span>  
    :::image-end:::  
    
<span data-ttu-id="79be3-118">DevTools を開いている限り、JavaScript はタブで無効なままです。</span><span class="sxs-lookup"><span data-stu-id="79be3-118">JavaScript remains disabled in the tab for as long as you have DevTools open.</span></span>  

<span data-ttu-id="79be3-119">ページを更新して、読み込み中に Web ページが JavaScript に依存するかどうかと方法を確認できます。</span><span class="sxs-lookup"><span data-stu-id="79be3-119">You may want to refresh the page to review if and how the webpage depends on JavaScript while loading.</span></span>  

<span data-ttu-id="79be3-120">JavaScript を再び有効にするには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="79be3-120">To re-enable JavaScript, complete the following actions.</span></span>  

*   <span data-ttu-id="79be3-121">コマンド メニュー **を再度開** き、コマンドを実行 `Enable JavaScript` します。</span><span class="sxs-lookup"><span data-stu-id="79be3-121">Open the **Command Menu** again and run the `Enable JavaScript` command.</span></span>  
*   <span data-ttu-id="79be3-122">DevTools を閉じます。</span><span class="sxs-lookup"><span data-stu-id="79be3-122">Close DevTools.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="79be3-123">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="79be3-123">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsOpen]: ../open/index.md "Microsoft Edge DevTools を開く | Microsoft Docs"  

> [!NOTE]
> <span data-ttu-id="79be3-125">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="79be3-125">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="79be3-126">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/disable) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="79be3-126">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/disable) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="79be3-128">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="79be3-128">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
