---
description: コマンド メニューを開く方法、コマンドを実行する方法、その他のアクションを確認する方法などのガイド。
title: Microsoft Edge DevTools コマンド メニューを使用してコマンドを実行する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: b815934da73f9f023629564da7bea14da166ff9b
ms.sourcegitcommit: 16e2f7232196a57a70b979bbf8b663774b7ddc20
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/25/2021
ms.locfileid: "11519192"
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

# <a name="run-commands-with-the-microsoft-edge-devtools-command-menu"></a><span data-ttu-id="d5289-104">Microsoft Edge DevTools コマンド メニューを使用してコマンドを実行する</span><span class="sxs-lookup"><span data-stu-id="d5289-104">Run commands with the Microsoft Edge DevTools Command Menu</span></span>  

<span data-ttu-id="d5289-105">コマンド メニューを使用すると、Microsoft Edge DevTools UI を迅速に移動し、JavaScript の無効化などの一般的なタスク [を実行できます][JavascriptDisable]。</span><span class="sxs-lookup"><span data-stu-id="d5289-105">The Command Menu provides a fast way to navigate the Microsoft Edge DevTools UI and accomplish common tasks, such as [disabling JavaScript][JavascriptDisable].</span></span>  <span data-ttu-id="d5289-106">コマンド メニューの元のインスピレーションVisual Studioと呼ばれる Microsoft Visual Studio コードの[][VisualStudioCodeUICommandPalette]同様の機能についてよく知っているかもしれません。</span><span class="sxs-lookup"><span data-stu-id="d5289-106">You may be familiar with a similar feature in Microsoft Visual Studio Code called the [Command Palette][VisualStudioCodeUICommandPalette], which was the original inspiration for the Command Menu.</span></span>  

:::image type="complex" source="../media/command-menu-run-command-java.msft.png" alt-text="コマンド メニューを使用して JavaScript を無効にする" lightbox="../media/command-menu-run-command-java.msft.png":::
   <span data-ttu-id="d5289-108">コマンド メニューを使用して JavaScript を無効にする</span><span class="sxs-lookup"><span data-stu-id="d5289-108">Using the Command Menu to disable JavaScript</span></span>  
:::image-end:::  

## <a name="open-the-command-menu"></a><span data-ttu-id="d5289-109">コマンド メニューを開く</span><span class="sxs-lookup"><span data-stu-id="d5289-109">Open the Command Menu</span></span>  

<span data-ttu-id="d5289-110">`Control` + `Shift` + `P` \(Windows, Linux\) または `Command` + `Shift` + `P` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="d5289-110">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\).</span></span> <span data-ttu-id="d5289-111">または、[ **コマンドの実行] で [DevTools** `...` \( \) のカスタマイズと制御> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d5289-111">Or choose **Customize And Control DevTools** \(`...`\) > **Run Command**.</span></span>  

:::image type="complex" source="../media/command-menu-options-run-command.msft.png" alt-text="コマンドの実行" lightbox="../media/command-menu-options-run-command.msft.png":::
   <span data-ttu-id="d5289-113">コマンドの実行</span><span class="sxs-lookup"><span data-stu-id="d5289-113">Run Command</span></span>  
:::image-end:::  

## <a name="display-other-available-actions"></a><span data-ttu-id="d5289-114">その他の使用可能なアクションを表示する</span><span class="sxs-lookup"><span data-stu-id="d5289-114">Display other available actions</span></span>  

<span data-ttu-id="d5289-115">[コマンド メニューを開く][](#open-the-command-menu)で説明されているワークフローを使用すると、コマンド メニューが開き、[コマンド メニュー] テキスト ボックスに文字があらかじめ `>` 入力されています。</span><span class="sxs-lookup"><span data-stu-id="d5289-115">If you use the workflow outlined in [Open the Command Menu](#open-the-command-menu), the Command Menu opens with a `>` character pre-pended to the Command Menu text box.</span></span>  

:::image type="complex" source="../media/command-menu-run-command.msft.png" alt-text="コマンド文字" lightbox="../media/command-menu-run-command.msft.png":::
   <span data-ttu-id="d5289-117">コマンド文字</span><span class="sxs-lookup"><span data-stu-id="d5289-117">The command character</span></span>  
:::image-end:::  

<span data-ttu-id="d5289-118">コマンド メニュー `>` から使用できる `?` 他のアクションを表示するには、文字と種類を削除します。</span><span class="sxs-lookup"><span data-stu-id="d5289-118">Delete the `>` character and type `?` to display other actions that are available from the Command Menu.</span></span>  

:::image type="complex" source="../media/command-menu-help.msft.png" alt-text="その他の使用可能なアクション" lightbox="../media/command-menu-help.msft.png":::
   <span data-ttu-id="d5289-120">その他の使用可能なアクション</span><span class="sxs-lookup"><span data-stu-id="d5289-120">Other available actions</span></span>  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="d5289-121">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="d5289-121">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[JavascriptDisable]: ../javascript/disable.md "Microsoft Edge DevTools を使用して JavaScript を無効|Microsoft Docs"  

[VisualStudioCodeUICommandPalette]: https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette "コマンド パレット - Visual Studio コード UI"  

> [!NOTE]
> <span data-ttu-id="d5289-124">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="d5289-124">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="d5289-125">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/command-menu/index) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="d5289-125">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/command-menu/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="d5289-127">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="d5289-127">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
