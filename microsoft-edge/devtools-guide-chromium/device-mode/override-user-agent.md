---
description: '[ネットワーク条件] ツールを開き、[自動的に選択] を無効にし、リストから選択するか、カスタム文字列を入力します。'
title: DevTools からユーザー エージェント文字列をMicrosoft Edgeする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 50d831847342c749cd36f203998351d53325a6f8
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564295"
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
# <a name="override-the-user-agent-string-from-microsoft-edge-devtools"></a><span data-ttu-id="486d2-104">DevTools からユーザー エージェント文字列をMicrosoft Edgeする</span><span class="sxs-lookup"><span data-stu-id="486d2-104">Override the user agent string from Microsoft Edge DevTools</span></span>  

<span data-ttu-id="486d2-105">DevTools[からユーザー エージェント][MDNUserAgent]文字列をMicrosoft Edgeするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="486d2-105">To override the [user agent][MDNUserAgent] string from Microsoft Edge DevTools:</span></span>  

1.  <span data-ttu-id="486d2-106">`Control`+`Shift`+`P` \(Windows, Linux\) または `Command`+`Shift`+`P` \(macOS\) を選択して、**コマンド メニュー** を開きます。</span><span class="sxs-lookup"><span data-stu-id="486d2-106">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    :::image type="complex" source="../media/device-mode-console-command-menu.msft.png" alt-text="コマンド メニュー" lightbox="../media/device-mode-console-command-menu.msft.png":::
       <span data-ttu-id="486d2-108">**コマンド メニュー**</span><span class="sxs-lookup"><span data-stu-id="486d2-108">The **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="486d2-109">[ネットワーク `network conditions` 条件の **表示] を選択し**、[ネットワーク条件] ツール `Enter` **を開きます** 。</span><span class="sxs-lookup"><span data-stu-id="486d2-109">Type `network conditions`, choose **Show Network conditions**, and select `Enter` to open the **Network conditions** tool.</span></span>  
1.  <span data-ttu-id="486d2-110">[ユーザー エージェント **] セクション** で、[自動的に選択する] **チェック ボックスをオフ** にします。</span><span class="sxs-lookup"><span data-stu-id="486d2-110">In the **User agent** section, turn off the **Select automatically** checkbox.</span></span>  
    
    :::image type="complex" source="../media/device-mode-console-network-conditions-user-agent-select-automatically-deselected.msft.png" alt-text="[自動的に選択] をオフにする" lightbox="../media/device-mode-console-network-conditions-user-agent-select-automatically-deselected.msft.png":::
       <span data-ttu-id="486d2-112">[自動的に **選択] をオフにする**</span><span class="sxs-lookup"><span data-stu-id="486d2-112">Turn off **Select automatically**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="486d2-113">リストからユーザー エージェント文字列を選択するか、独自のカスタム文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="486d2-113">Choose a user agent string from the list, or enter your own custom string.</span></span>  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="486d2-114">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="486d2-114">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MDNUserAgent]: https://developer.mozilla.org/docs/Glossary/User_agent "ユーザー エージェント |MDN"  

> [!NOTE]
> <span data-ttu-id="486d2-116">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="486d2-116">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="486d2-117">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/device-mode/override-user-agent) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="486d2-117">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/device-mode/override-user-agent) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="486d2-119">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="486d2-119">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
