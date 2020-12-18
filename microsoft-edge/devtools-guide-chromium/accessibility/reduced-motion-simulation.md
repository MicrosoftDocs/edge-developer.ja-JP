---
description: 開発者ツールを使用して、縮小されたモーションをシミュレートします。
title: 開発者ツールを使用して縮小モーションをシミュレートする (CSS Prefers Reduced Motion)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 0e5243e01ca6c9344dceffb0bf004dadccc3d4d7
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230790"
---
# <span data-ttu-id="3beb0-104">モーション シミュレーションの削減</span><span class="sxs-lookup"><span data-stu-id="3beb0-104">Reduced Motion Simulation</span></span>  

<span data-ttu-id="3beb0-105">Web 製品のアニメーションはアクセシビリティの問題である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3beb0-105">Animation in web products may be an accessibility problem.</span></span>  <span data-ttu-id="3beb0-106">オペレーティング システムは、ユーザーの混乱や、発作のトリガーなどの潜在的な健康関連の問題を回避するためにアニメーションをオフにするオプションを含めて、この問題に対処します。</span><span class="sxs-lookup"><span data-stu-id="3beb0-106">Operating Systems deal with the problem by including an option to turn off animations to avoid user confusion and potential health related problems such as triggering seizures.</span></span>  <span data-ttu-id="3beb0-107">Web では、ユーザーがアニメーションを表示しない場合に [、prefers-reduced-motion][MDNPrefersReducedMotion] CSS Media Query を使用して検出できます。</span><span class="sxs-lookup"><span data-stu-id="3beb0-107">On the web, you may use the [prefers-reduced-motion][MDNPrefersReducedMotion] CSS Media Query to detect if users prefer to not see any animations.</span></span>  <span data-ttu-id="3beb0-108">製品では、影響を受けるユーザーにアニメーションが表示されるのを避けるために、テストでアニメーション コードをラップすることができます。</span><span class="sxs-lookup"><span data-stu-id="3beb0-108">In your product, you may wrap your animation code in a test to avoid animations showing up for the affected users.</span></span>  

```css
@media (prefers-reduced-motion: reduce) {
  /* in case the .header element has an animation, turn it off */
  .header {
    animation: none;
  }
}
```  

<span data-ttu-id="3beb0-109">Microsoft [Edge DevTools を][DevtoolsIndex]使用すると、オペレーティング システムを変更することなく、この縮小されたモーション設定をシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="3beb0-109">Using the [Microsoft Edge DevTools][DevtoolsIndex], you may simulate this reduced motion setting without having to change your operating system.</span></span>  

1.  <span data-ttu-id="3beb0-110">コマンド メニュー **を開きます**。</span><span class="sxs-lookup"><span data-stu-id="3beb0-110">Open the **Command Menu**.</span></span>  
    1.  <span data-ttu-id="3beb0-111">`Control` + `Shift` + `P` Windows/Linux または `Command` + `Shift` + `P` macOS で選択します。</span><span class="sxs-lookup"><span data-stu-id="3beb0-111">Select `Control`+`Shift`+`P` on Windows/Linux or `Command`+`Shift`+`P` on macOS.</span></span>  
        
        :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="コマンド メニュー" lightbox="../media/css-console-command-menu-rendering.msft.png":::
           <span data-ttu-id="3beb0-113">**コマンド メニュー**</span><span class="sxs-lookup"><span data-stu-id="3beb0-113">The **Command Menu**</span></span>  
        :::image-end:::  
        
1.  <span data-ttu-id="3beb0-114">シミュレーション `reduced` をオンまたはオフにする場合は、「入力」と入力します。</span><span class="sxs-lookup"><span data-stu-id="3beb0-114">Type `reduced`, to turn the simulation on and off.</span></span>  <span data-ttu-id="3beb0-115">オプションを選択し、選択します `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="3beb0-115">Choose the option and select `Enter`.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-qs-select-reduced-motion-command-menu.msft.png" alt-text="コマンド メニューの [優先されるモーションの縮小] 設定をオンまたはオフにする" lightbox="../media/css-elements-styles-qs-select-reduced-motion-command-menu.msft.png":::
       <span data-ttu-id="3beb0-117">コマンド メニューの [優先されるモーション **の縮小] 設定を** オンまたは **オフにする**</span><span class="sxs-lookup"><span data-stu-id="3beb0-117">Turn on or off the **prefers reduced motion** setting from **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="3beb0-118">現在のページを更新して、アニメーションがオフになっているか表示されているかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="3beb0-118">Refresh the current page to test whether your animations are turned off or visible.</span></span>  
    
<!-- links -->  

[DevtoolsIndex]: ../index.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  

[MDNPrefersReducedMotion]: https://developer.mozilla.org/docs/Web/CSS/@media/prefers-reduced-motion "prefers-reduced-motion |MDN"  
