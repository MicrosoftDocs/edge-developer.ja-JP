---
title: Microsoft Edge DevTools をカスタマイズする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: f34f2e3c02b0c66ee02f4810827f3adb51a60abc
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882745"
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





# <span data-ttu-id="9d53a-103">Microsoft Edge DevTools をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="9d53a-103">Customize Microsoft Edge DevTools</span></span>   

  

<span data-ttu-id="9d53a-104">このページでは、Microsoft Edge DevTools をカスタマイズする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9d53a-104">This page lists the ways to customize Microsoft Edge DevTools.</span></span>  

## <span data-ttu-id="9d53a-105">設定</span><span class="sxs-lookup"><span data-stu-id="9d53a-105">Settings</span></span>   

<span data-ttu-id="9d53a-106">**設定**  > **環境設定**には、devtools をカスタマイズするための多くのオプションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9d53a-106">**Settings** > **Preferences** contains many options for customizing DevTools.</span></span>  

<span data-ttu-id="9d53a-107">[設定] を開くには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9d53a-107">To open Settings, do one of the following:</span></span>  

*   <span data-ttu-id="9d53a-108">`F1`DevTools がフォーカスされているときに、を押します。</span><span class="sxs-lookup"><span data-stu-id="9d53a-108">Press `F1` while DevTools is in focus.</span></span>  
*   <span data-ttu-id="9d53a-109">**メインメニュー**を開き、[**設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9d53a-109">Open the **Main Menu** and then select **Settings**.</span></span>  

> ##### <span data-ttu-id="9d53a-110">図 1</span><span class="sxs-lookup"><span data-stu-id="9d53a-110">Figure 1</span></span>  
> <span data-ttu-id="9d53a-111">設定</span><span class="sxs-lookup"><span data-stu-id="9d53a-111">Settings</span></span>  
> ![設定][ImageSettings]  

## <span data-ttu-id="9d53a-113">ドロアー</span><span class="sxs-lookup"><span data-stu-id="9d53a-113">Drawer</span></span>   

<span data-ttu-id="9d53a-114">**ドロワー**には、多くの非表示機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9d53a-114">The **Drawer** contains many hidden features.</span></span>  

<span data-ttu-id="9d53a-115">を押して `Escape` 、引き出しを開くか、閉じます。</span><span class="sxs-lookup"><span data-stu-id="9d53a-115">Press `Escape` to open or close the Drawer.</span></span>  

> ##### <span data-ttu-id="9d53a-116">図 2</span><span class="sxs-lookup"><span data-stu-id="9d53a-116">Figure 2</span></span>  
> <span data-ttu-id="9d53a-117">ドロワー</span><span class="sxs-lookup"><span data-stu-id="9d53a-117">The Drawer</span></span>  
> ![ドロワー][ImageDrawerExample]  

<span data-ttu-id="9d53a-119">[**その他]** をクリックして ![ ][ImageMoreIcon] 、他の引き出しタブを開きます。</span><span class="sxs-lookup"><span data-stu-id="9d53a-119">Click **More** ![More][ImageMoreIcon]  to open other Drawer tabs.</span></span>  

> ##### <span data-ttu-id="9d53a-120">図 3</span><span class="sxs-lookup"><span data-stu-id="9d53a-120">Figure 3</span></span>  
> <span data-ttu-id="9d53a-121">引き出しタブを開くためのボタン</span><span class="sxs-lookup"><span data-stu-id="9d53a-121">The button for opening Drawer tabs</span></span>  
> ![引き出しタブを開くためのボタン][ImageMoreDrawerTabs]  

## <span data-ttu-id="9d53a-123">パネルの順序を変更する</span><span class="sxs-lookup"><span data-stu-id="9d53a-123">Reorder panels</span></span>   

<span data-ttu-id="9d53a-124">パネルタブをクリックし、ドラッグして順序を変更します。</span><span class="sxs-lookup"><span data-stu-id="9d53a-124">Click and drag a panel tab to change its ordering.</span></span>  <span data-ttu-id="9d53a-125">カスタムタブの順序は、DevTools セッション間で維持されます。</span><span class="sxs-lookup"><span data-stu-id="9d53a-125">Your custom tab order persists across DevTools sessions.</span></span>  

> [!NOTE]
> <span data-ttu-id="9d53a-126">既定では、[ネットワークパネル] タブは左側の4番目のタブにあります。</span><span class="sxs-lookup"><span data-stu-id="9d53a-126">By default, the Network panel tab is usually the fourth from the left.</span></span>  <span data-ttu-id="9d53a-127">[図 4](#figure-4)では、左側の最初のものです。</span><span class="sxs-lookup"><span data-stu-id="9d53a-127">In [Figure 4](#figure-4), it is the first from the left.</span></span>  

> ##### <span data-ttu-id="9d53a-128">図 4</span><span class="sxs-lookup"><span data-stu-id="9d53a-128">Figure 4</span></span>  
> <span data-ttu-id="9d53a-129">カスタムタブオーダーが表示された DevTools ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="9d53a-129">A DevTools window with a custom tab ordering</span></span>    
> ![カスタムパネルタブの順序が表示された DevTools ウィンドウ][ImageCustomTabOrdering]  

## <span data-ttu-id="9d53a-131">DevTools の配置を変更する</span><span class="sxs-lookup"><span data-stu-id="9d53a-131">Change DevTools placement</span></span>   

<span data-ttu-id="9d53a-132">「 [Microsoft Edge DevTools の配置][DevToolsPlacement]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d53a-132">See [Microsoft Edge DevTools Placement][DevToolsPlacement].</span></span>  

> ##### <span data-ttu-id="9d53a-133">図 5</span><span class="sxs-lookup"><span data-stu-id="9d53a-133">Figure 5</span></span>  
> <span data-ttu-id="9d53a-134">アンドックした DevTools</span><span class="sxs-lookup"><span data-stu-id="9d53a-134">Undocked DevTools</span></span>  
> ![アンドックした DevTools][ImageUndock]  

## <span data-ttu-id="9d53a-136">濃色テーマ</span><span class="sxs-lookup"><span data-stu-id="9d53a-136">Dark theme</span></span>   

<span data-ttu-id="9d53a-137">「[濃色テーマを有効にする」を][DarkTheme]参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d53a-137">See [Enable Dark Theme][DarkTheme].</span></span>  

> ##### <span data-ttu-id="9d53a-138">図 6</span><span class="sxs-lookup"><span data-stu-id="9d53a-138">Figure 6</span></span>  
> <span data-ttu-id="9d53a-139">濃色テーマ</span><span class="sxs-lookup"><span data-stu-id="9d53a-139">The dark theme</span></span>  
> ![濃色テーマ][ImageDarkTheme]  

## <span data-ttu-id="9d53a-141">テスト</span><span class="sxs-lookup"><span data-stu-id="9d53a-141">Experiments</span></span>   

<span data-ttu-id="9d53a-142">DevTools の実験を有効にするには:</span><span class="sxs-lookup"><span data-stu-id="9d53a-142">To enable DevTools experiments:</span></span>  

1.  <span data-ttu-id="9d53a-143">に移動 `edge://flags/#enable-devtools-experiments` します。</span><span class="sxs-lookup"><span data-stu-id="9d53a-143">Go to `edge://flags/#enable-devtools-experiments`.</span></span>  
1.  <span data-ttu-id="9d53a-144">**[有効]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d53a-144">Click **Enable**.</span></span>  
1.  <span data-ttu-id="9d53a-145">ページの下部にある [**今すぐ**再起動] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d53a-145">Click **Relaunch Now**, at the bottom of the page.</span></span>  

<span data-ttu-id="9d53a-146">次に DevTools を開くと、[[設定](#settings)] に "**実験**" という新しいページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d53a-146">The next time you open DevTools, a new page is displayed called **Experiments** in [Settings](#settings).</span></span>  

   

  

<!-- image links -->  

[ImageMoreIcon]: /microsoft-edge/devtools-guide-chromium/media/more-icon.msft.png  

[ImageSettings]: /microsoft-edge/devtools-guide-chromium/media/customize-settings-preferences.msft.png "図 1: 設定"  
[ImageDrawerExample]: /microsoft-edge/devtools-guide-chromium/media/customize-drawer-open.msft.png "図 2: ドロワー"  
[ImageMoreDrawerTabs]: /microsoft-edge/devtools-guide-chromium/media/customize-drawer-open-more-tools.msft.png "図 3: [引き出し] タブを開くためのボタン"  
[ImageCustomTabOrdering]: /microsoft-edge/devtools-guide-chromium/media/customize-network-first-position.msft.png "図 4: カスタムパネルタブの順序が表示された DevTools ウィンドウ"  
[ImageUndock]: /microsoft-edge/devtools-guide-chromium/media/customize-dev-tools-dock-side.msft.png "図 5: アンドックした DevTools"  
[ImageDarkTheme]: /microsoft-edge/devtools-guide-chromium/media/customize-settings-appearance-theme.msft.png "図 6: 濃色テーマ"  

<!-- links -->  

[DevToolsPlacement]: /microsoft-edge/devtools-guide-chromium/customize/placement "Microsoft Edge DevTools の配置を変更する (ドッキング解除、下へのドッキング、左へのドッキング)"  
[DarkTheme]: /microsoft-edge/devtools-guide-chromium/customize/dark-theme "Microsoft Edge DevTools でダークテーマを有効にする"  

> [!NOTE]
> <span data-ttu-id="9d53a-155">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="9d53a-155">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="9d53a-156">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/customize/index)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="9d53a-156">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/customize/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="9d53a-158">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="9d53a-158">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
