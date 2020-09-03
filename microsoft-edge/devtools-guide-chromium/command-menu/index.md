---
description: コマンドメニューを開く方法、コマンドを実行する方法、その他の操作を表示する方法に関するガイド。
title: Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 54dead492e7d58053efab77c82a10e7e3c912460
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993199"
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





# <span data-ttu-id="c45f8-104">Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する</span><span class="sxs-lookup"><span data-stu-id="c45f8-104">Run Commands With The Microsoft Edge DevTools Command Menu</span></span>   

  

<span data-ttu-id="c45f8-105">コマンドメニューを使うと、Microsoft Edge の DevTools UI をすばやく移動し、 [JavaScript を無効][JavascriptDisable]にするなどの一般的な作業を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="c45f8-105">The Command Menu provides a fast way to navigate the Microsoft Edge DevTools UI and accomplish common tasks, such as [disabling JavaScript][JavascriptDisable].</span></span>  <span data-ttu-id="c45f8-106">コマンド [パレット][VisualStudioCodeUICommandPalette]と呼ばれる Visual Studio コードと同様の機能 (コマンドメニューの元のインスピレーション) に精通していることがあります。</span><span class="sxs-lookup"><span data-stu-id="c45f8-106">You may be familiar with a similar feature in Visual Studio Code called the [Command Palette][VisualStudioCodeUICommandPalette], which was the original inspiration for the Command Menu.</span></span>  

:::image type="complex" source="../media/command-menu-run-command-java.msft.png" alt-text="コマンドメニューを使用して JavaScript を無効にする" lightbox="../media/command-menu-run-command-java.msft.png":::
   <span data-ttu-id="c45f8-108">コマンドメニューを使用して JavaScript を無効にする</span><span class="sxs-lookup"><span data-stu-id="c45f8-108">Using the Command Menu to disable JavaScript</span></span>  
:::image-end:::  

## <span data-ttu-id="c45f8-109">コマンドメニューを開く</span><span class="sxs-lookup"><span data-stu-id="c45f8-109">Open the Command Menu</span></span>   

<span data-ttu-id="c45f8-110">`Control` + `Shift` + `P` \ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="c45f8-110">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\).</span></span> <span data-ttu-id="c45f8-111">または、[ **DevTools のカスタマイズと制御**] をクリックし、[ `...` **コマンドの実行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c45f8-111">Or click **Customize And Control DevTools** `...` and then select **Run Command**.</span></span>  

:::image type="complex" source="../media/command-menu-options-run-command.msft.png" alt-text="コマンドの実行" lightbox="../media/command-menu-options-run-command.msft.png":::
   <span data-ttu-id="c45f8-113">コマンドの実行</span><span class="sxs-lookup"><span data-stu-id="c45f8-113">Run Command</span></span>  
:::image-end:::  

## <span data-ttu-id="c45f8-114">使用可能なその他の操作を表示する</span><span class="sxs-lookup"><span data-stu-id="c45f8-114">See other available actions</span></span>   

<span data-ttu-id="c45f8-115">[ [コマンドメニューを開く](#open-the-command-menu)] でアウトライン表示されたワークフローを使用している場合、コマンドメニューが開き、 `>` コマンドメニューのテキストボックスに前に "延期" という文字が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c45f8-115">If you use the workflow outlined in [Open the Command Menu](#open-the-command-menu), the Command Menu opens with a `>` character pre-pended to the Command Menu text box.</span></span>  

:::image type="complex" source="../media/command-menu-run-command.msft.png" alt-text="コマンド文字" lightbox="../media/command-menu-run-command.msft.png":::
   <span data-ttu-id="c45f8-117">コマンド文字</span><span class="sxs-lookup"><span data-stu-id="c45f8-117">The command character</span></span>  
:::image-end:::  

<span data-ttu-id="c45f8-118">`>`文字と入力を削除し `?` て、コマンドメニューから利用可能なその他の操作を確認します。</span><span class="sxs-lookup"><span data-stu-id="c45f8-118">Delete the `>` character and type `?` to see other actions that are available from the Command Menu.</span></span>  

:::image type="complex" source="../media/command-menu-help.msft.png" alt-text="その他の使用可能なアクション" lightbox="../media/command-menu-help.msft.png":::
   <span data-ttu-id="c45f8-120">その他の使用可能なアクション</span><span class="sxs-lookup"><span data-stu-id="c45f8-120">Other available actions</span></span>  
:::image-end:::  

 



<!-- links -->  

[JavascriptDisable]: ../javascript/disable.md "Microsoft Edge DevTools で JavaScript を無効にする |Microsoft ドキュメント"  

[VisualStudioCodeUICommandPalette]: https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette "コマンドパレット-Visual Studio コード UI"  

> [!NOTE]
> <span data-ttu-id="c45f8-123">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="c45f8-123">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="c45f8-124">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/command-menu/index) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="c45f8-124">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/command-menu/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="c45f8-126">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="c45f8-126">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
