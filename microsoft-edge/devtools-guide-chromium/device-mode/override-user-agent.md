---
title: Microsoft Edge DevTools からユーザーエージェント文字列を上書きする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/26/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 376e1550d0dc31f3b47b6badd6970076a8c13f91
ms.sourcegitcommit: 531ec8aa1f89b28bc4d271e8e995f846f2392bc3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2020
ms.locfileid: "10607308"
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





# <span data-ttu-id="4ac08-103">Microsoft Edge DevTools からユーザーエージェント文字列を上書きする</span><span class="sxs-lookup"><span data-stu-id="4ac08-103">Override The User Agent String From Microsoft Edge DevTools</span></span>   



<span data-ttu-id="4ac08-104">Microsoft Edge DevTools から[ユーザーエージェント][MDNUserAgent]文字列を上書きするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4ac08-104">To override the [user agent][MDNUserAgent] string from Microsoft Edge DevTools:</span></span>  

1.  <span data-ttu-id="4ac08-105">`Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows \) または `Command` + `Shift` + `P` \ **Command Menu**(macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="4ac08-105">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    > ##### <span data-ttu-id="4ac08-106">図 1</span><span class="sxs-lookup"><span data-stu-id="4ac08-106">Figure 1</span></span>  
    > <span data-ttu-id="4ac08-107">コマンドメニュー</span><span class="sxs-lookup"><span data-stu-id="4ac08-107">The Command Menu</span></span>  
    > ![コマンドメニュー][ImageCommandMenu]  
    
1.  <span data-ttu-id="4ac08-109">「 `network conditions` **ネットワーク**条件の表示」を選択し、を押して [ネットワークの `Enter` **条件**] タブを開きます。</span><span class="sxs-lookup"><span data-stu-id="4ac08-109">Type `network conditions`, select **Show Network conditions**, and press `Enter` to open the **Network conditions** tab.</span></span>  
1.  <span data-ttu-id="4ac08-110">[**ユーザーエージェント**] セクションで、 **[自動的に選択**する] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="4ac08-110">In the **User agent** section, disable the **Select automatically** checkbox.</span></span>  
    
    > ##### <span data-ttu-id="4ac08-111">図 2</span><span class="sxs-lookup"><span data-stu-id="4ac08-111">Figure 2</span></span>  
    > <span data-ttu-id="4ac08-112">**選択を自動的に無効に**する</span><span class="sxs-lookup"><span data-stu-id="4ac08-112">Disabling **Select automatically**</span></span>  
    > ![選択を自動的に無効にする][ImageUserAgentDisableSelectAutomatically]  
    
1.  <span data-ttu-id="4ac08-114">リストからユーザーエージェント文字列を選択するか、独自のカスタム文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="4ac08-114">Select a user agent string from the list, or enter your own custom string.</span></span>  

<!--## Feedback   -->  



<!-- image links -->  

[ImageCommandMenu]: /microsoft-edge/devtools-guide-chromium/media/device-mode-console-command-menu.msft.png "図 1: コマンドメニュー"  
[ImageUserAgentDisableSelectAutomatically]: /microsoft-edge/devtools-guide-chromium/media/device-mode-console-network-conditions-user-agent-select-automatically-deselected.msft.png "図 2: [選択を自動的に無効にする]"  

<!-- links -->  

[MDNUserAgent]: https://developer.mozilla.org/docs/Glossary/User_agent "ユーザーエージェント |MDN"  

> [!NOTE]
> <span data-ttu-id="4ac08-118">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="4ac08-118">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="4ac08-119">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/device-mode/override-user-agent)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="4ac08-119">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/device-mode/override-user-agent) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="4ac08-121">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="4ac08-121">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
