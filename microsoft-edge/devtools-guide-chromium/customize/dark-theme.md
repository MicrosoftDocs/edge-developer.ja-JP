---
title: Microsoft Edge DevTools でダークテーマを有効にする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 46a6d1aab30689a0d4b1f3fb20bf3521abd2017a
ms.sourcegitcommit: 67ce64f810afdb304844bae0f3918d4e9108dcec
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2020
ms.locfileid: "10601340"
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





# <span data-ttu-id="44a1a-103">Microsoft Edge DevTools でダークテーマを有効にする</span><span class="sxs-lookup"><span data-stu-id="44a1a-103">Enable Dark Theme In Microsoft Edge DevTools</span></span>   

  

<span data-ttu-id="44a1a-104">[[設定](#set-up-dark-theme-from-settings)] または[コマンドメニュー](#set-up-dark-theme-from-the-command-menu)で、ダークテーマを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="44a1a-104">You may enable dark theme in [Settings](#set-up-dark-theme-from-settings) or the [Command Menu](#set-up-dark-theme-from-the-command-menu).</span></span>  

> ##### <span data-ttu-id="44a1a-105">図 1</span><span class="sxs-lookup"><span data-stu-id="44a1a-105">Figure 1</span></span>  
> <span data-ttu-id="44a1a-106">濃色テーマ</span><span class="sxs-lookup"><span data-stu-id="44a1a-106">The dark theme</span></span>  
> ![濃色テーマ][ImageDarkTheme]  

## <span data-ttu-id="44a1a-108">設定からダークテーマを設定する</span><span class="sxs-lookup"><span data-stu-id="44a1a-108">Set up dark theme from Settings</span></span>   

1.  <span data-ttu-id="44a1a-109">[開発**ツールのカスタマイズと制御**] をクリックして、[ `...` **設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="44a1a-109">Click **Customize And Control DevTools** `...` and then select **Settings**.</span></span>  <span data-ttu-id="44a1a-110">または、を押して**設定**を開くこともでき `F1` ます。</span><span class="sxs-lookup"><span data-stu-id="44a1a-110">You may also open **Settings** by pressing `F1`.</span></span>  

> ##### <span data-ttu-id="44a1a-111">図 2</span><span class="sxs-lookup"><span data-stu-id="44a1a-111">Figure 2</span></span>  
> <span data-ttu-id="44a1a-112">設定を開く</span><span class="sxs-lookup"><span data-stu-id="44a1a-112">Opening Settings</span></span>  
> ![設定を開く][ImageOpenSettings]  

1.  <span data-ttu-id="44a1a-114">[**環境設定**] ウィンドウの **[外観**] で、[**テーマ**] ドロップダウンをクリックし、[**濃色**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="44a1a-114">On the **Preferences** pane,  under **Appearance**, click on the **Theme** drop-down, and select **Dark**.</span></span>  

> ##### <span data-ttu-id="44a1a-115">図 3</span><span class="sxs-lookup"><span data-stu-id="44a1a-115">Figure 3</span></span>  
> <span data-ttu-id="44a1a-116">基本設定</span><span class="sxs-lookup"><span data-stu-id="44a1a-116">Preferences</span></span>  
> ![基本設定][ImagePreferences]  

## <span data-ttu-id="44a1a-118">コマンドメニューから濃色テーマを設定する</span><span class="sxs-lookup"><span data-stu-id="44a1a-118">Set up dark theme from the Command Menu</span></span>   

1.  <span data-ttu-id="44a1a-119">[コマンドメニューを開き][CommandMenu]ます。</span><span class="sxs-lookup"><span data-stu-id="44a1a-119">[Open the Command Menu][CommandMenu].</span></span>  
1.  <span data-ttu-id="44a1a-120">入力を開始し、[ `dark` **濃色テーマに切り替える**] コマンドを選択し、を押して `Enter` コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="44a1a-120">Start typing `dark`, select the **Switch To Dark Theme** command, and then press `Enter` to run the command.</span></span>  

> ##### <span data-ttu-id="44a1a-121">図 4</span><span class="sxs-lookup"><span data-stu-id="44a1a-121">Figure 4</span></span>  
> <span data-ttu-id="44a1a-122">[濃色テーマ] コマンド</span><span class="sxs-lookup"><span data-stu-id="44a1a-122">The dark theme command</span></span>  
> ![[濃色テーマ] コマンド][ImageDarkThemeCommand]  

   



<!-- image links -->  

[ImageDarkTheme]: /microsoft-edge/devtools-guide-chromium/media/customize-elements-styles-console-dark-theme.msft.png "図 1: 濃色テーマ"  
[ImageOpenSettings]: /microsoft-edge/devtools-guide-chromium/media/customize-options-settings.msft.png "図 2: 設定を開く"  
[ImagePreferences]: /microsoft-edge/devtools-guide-chromium/media/customize-settings-preferences-appearance-theme-dark.msft.png "図 3: 環境設定"  
[ImageDarkThemeCommand]: /microsoft-edge/devtools-guide-chromium/media/customize-command-menu-dark.msft.png "図 4: [濃色テーマ] コマンド"  

<!-- links -->  

[CommandMenu]: /microsoft-edge/devtools-guide-chromium/command-menu/index "コマンドメニュー"  

> [!NOTE]
> <span data-ttu-id="44a1a-129">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="44a1a-129">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="44a1a-130">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/customize/dark-theme)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="44a1a-130">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/customize/dark-theme) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="44a1a-132">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="44a1a-132">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
