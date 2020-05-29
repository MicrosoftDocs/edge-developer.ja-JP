---
title: Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 748008b347a3498008748b9c3f9ecc1445c47f12
ms.sourcegitcommit: 5cdc1626d5581b79c0f2ac4ea62e7f1974ebfa57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "10601748"
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





# <span data-ttu-id="f3470-103">Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する</span><span class="sxs-lookup"><span data-stu-id="f3470-103">Run Commands With The Microsoft Edge DevTools Command Menu</span></span>   

  

<span data-ttu-id="f3470-104">コマンドメニューを使うと、Microsoft Edge の DevTools UI をすばやく移動し、 [JavaScript を無効][JavascriptDisable]にするなどの一般的な作業を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="f3470-104">The Command Menu provides a fast way to navigate the Microsoft Edge DevTools UI and accomplish common tasks, such as [disabling JavaScript][JavascriptDisable].</span></span>  <span data-ttu-id="f3470-105">コマンド[パレット][VisualStudioCodeUICommandPalette]と呼ばれる Visual Studio コードと同様の機能 (コマンドメニューの元のインスピレーション) に精通していることがあります。</span><span class="sxs-lookup"><span data-stu-id="f3470-105">You may be familiar with a similar feature in Visual Studio Code called the [Command Palette][VisualStudioCodeUICommandPalette], which was the original inspiration for the Command Menu.</span></span>  

> ##### <span data-ttu-id="f3470-106">図 1</span><span class="sxs-lookup"><span data-stu-id="f3470-106">Figure 1</span></span>  
> <span data-ttu-id="f3470-107">コマンドメニューを使用して JavaScript を無効にする</span><span class="sxs-lookup"><span data-stu-id="f3470-107">Using the Command Menu to disable JavaScript</span></span>  
> ![コマンドメニューを使用して JavaScript を無効にする][ImageDisableJS]  

## <span data-ttu-id="f3470-109">コマンドメニューを開く</span><span class="sxs-lookup"><span data-stu-id="f3470-109">Open the Command Menu</span></span>   

<span data-ttu-id="f3470-110">`Control` + `Shift` + `P` \ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="f3470-110">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\).</span></span> <span data-ttu-id="f3470-111">または、[ **DevTools のカスタマイズと制御**] をクリックし、[ `...` **コマンドの実行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f3470-111">Or click **Customize And Control DevTools** `...` and then select **Run Command**.</span></span>  

> ##### <span data-ttu-id="f3470-112">図 2</span><span class="sxs-lookup"><span data-stu-id="f3470-112">Figure 2</span></span>  
> <span data-ttu-id="f3470-113">コマンドの実行</span><span class="sxs-lookup"><span data-stu-id="f3470-113">Run Command</span></span>  
> ![コマンドの実行][ImageRunCommand]  

## <span data-ttu-id="f3470-115">使用可能なその他の操作を表示する</span><span class="sxs-lookup"><span data-stu-id="f3470-115">See other available actions</span></span>   

<span data-ttu-id="f3470-116">[コマンドメニューを[開く]](#open-the-command-menu)でアウトライン表示されたワークフローを使用した場合、コマンドメニューが開き、コマンドメニューの `>` テキストボックスの先頭に文字が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3470-116">If you use the workflow outlined in [Open the Command Menu](#open-the-command-menu), the Command Menu opens with a `>` character prepended to the Command Menu text box.</span></span>  

> ##### <span data-ttu-id="f3470-117">図 3</span><span class="sxs-lookup"><span data-stu-id="f3470-117">Figure 3</span></span>  
> <span data-ttu-id="f3470-118">コマンド文字</span><span class="sxs-lookup"><span data-stu-id="f3470-118">The command character</span></span>  
> ![コマンド文字][ImageCommandCharacter]  

<span data-ttu-id="f3470-120">`>`文字と入力を削除し `?` て、コマンドメニューから利用可能なその他の操作を確認します。</span><span class="sxs-lookup"><span data-stu-id="f3470-120">Delete the `>` character and type `?` to see other actions that are available from the Command Menu.</span></span>  

> ##### <span data-ttu-id="f3470-121">図 4</span><span class="sxs-lookup"><span data-stu-id="f3470-121">Figure 4</span></span>  
> <span data-ttu-id="f3470-122">その他の使用可能なアクション</span><span class="sxs-lookup"><span data-stu-id="f3470-122">Other available actions</span></span>  
> ![その他の使用可能なアクション][ImageActions]  

 



<!-- image links -->  

[ImageDisableJS]: /microsoft-edge/devtools-guide-chromium/media/command-menu-run-command-java.msft.png "図 1: コマンドメニューを使用して JavaScript を無効にする"  
[ImageRunCommand]: /microsoft-edge/devtools-guide-chromium/media/command-menu-options-run-command.msft.png "図 2: コマンドの実行"  
[ImageCommandCharacter]: /microsoft-edge/devtools-guide-chromium/media/command-menu-run-command.msft.png "図 3: コマンド文字"  
[ImageActions]: /microsoft-edge/devtools-guide-chromium/media/command-menu-help.msft.png "図 4: 使用可能なその他の操作"  

<!-- links -->  

[JavascriptDisable]: /microsoft-edge/devtools-guide-chromium/javascript/disable "Microsoft Edge DevTools で JavaScript を無効にする"  

[VisualStudioCodeUICommandPalette]: https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette "コマンドパレット-Visual Studio コード UI"  

> [!NOTE]
> <span data-ttu-id="f3470-130">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="f3470-130">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="f3470-131">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/command-menu/index)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="f3470-131">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/command-menu/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="f3470-133">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="f3470-133">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
