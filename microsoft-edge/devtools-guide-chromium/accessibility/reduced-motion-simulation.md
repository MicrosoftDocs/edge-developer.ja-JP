---
description: 開発者ツールを使用して、縮小されたモーションをシミュレートします。
title: 開発者ツールを使用して縮小モーションをシミュレートする (CSS Prefers Reduced Motion)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 29cdbd7492665e819315910b3f743d444470cc12
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397868"
---
# <a name="reduced-motion-simulation"></a><span data-ttu-id="e8623-104">モーション シミュレーションの削減</span><span class="sxs-lookup"><span data-stu-id="e8623-104">Reduced motion simulation</span></span>  

<span data-ttu-id="e8623-105">Web 製品のアニメーションはアクセシビリティの問題である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e8623-105">Animation in web products may be an accessibility problem.</span></span>  <span data-ttu-id="e8623-106">オペレーティング システムは、ユーザーの混乱や、発作のトリガーなどの潜在的な正常性関連の問題を回避するためにアニメーションをオフにするオプションを含めて、この問題に対処します。</span><span class="sxs-lookup"><span data-stu-id="e8623-106">Operating Systems deal with the problem by including an option to turn off animations to avoid user confusion and potential health related problems such as triggering seizures.</span></span>  <span data-ttu-id="e8623-107">Web では、ユーザーがアニメーションを実行したり表示したりすることを好むのを検出するために、優先的に縮小 [されたモーション][MDNPrefersReducedMotion] CSS メディア クエリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e8623-107">On the web, you may use the [prefers-reduced-motion][MDNPrefersReducedMotion] CSS Media Query to detect if users prefer to not run or display any animations.</span></span>  <span data-ttu-id="e8623-108">製品では、影響を受けるユーザーにアニメーションが表示されるのを避けるために、テストでアニメーション コードをラップできます。</span><span class="sxs-lookup"><span data-stu-id="e8623-108">In your product, you may wrap your animation code in a test to avoid animations showing up for the affected users.</span></span>  

```css
@media (prefers-reduced-motion: reduce) {
  /* in case the .header element has an animation, turn it off */
  .header {
    animation: none;
  }
}
```  

<span data-ttu-id="e8623-109">Microsoft [Edge DevTools を使用][DevtoolsIndex]すると、オペレーティング システムを変更することなく、この縮小モーション設定をシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="e8623-109">Using the [Microsoft Edge DevTools][DevtoolsIndex], you may simulate this reduced motion setting without having to change your operating system.</span></span>  

1.  <span data-ttu-id="e8623-110">コマンド メニュー **を開きます**。</span><span class="sxs-lookup"><span data-stu-id="e8623-110">Open the **Command Menu**.</span></span>  
    1.  <span data-ttu-id="e8623-111">`Control` + `Shift` + `P` Windows/Linux または `Command` + `Shift` + `P` macOS で選択します。</span><span class="sxs-lookup"><span data-stu-id="e8623-111">Select `Control`+`Shift`+`P` on Windows/Linux or `Command`+`Shift`+`P` on macOS.</span></span>  
        
        :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="コマンド メニュー" lightbox="../media/css-console-command-menu-rendering.msft.png":::
           <span data-ttu-id="e8623-113">**コマンド メニュー**</span><span class="sxs-lookup"><span data-stu-id="e8623-113">The **Command Menu**</span></span>  
        :::image-end:::  
        
1.  <span data-ttu-id="e8623-114">`reduced`「」と入力して、シミュレーションのオンとオフを切り替えます。</span><span class="sxs-lookup"><span data-stu-id="e8623-114">Type `reduced`, to turn the simulation on and off.</span></span>  <span data-ttu-id="e8623-115">オプションを選択して選択します `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="e8623-115">Choose the option and select `Enter`.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-qs-select-reduced-motion-command-menu.msft.png" alt-text="[コマンド メニュー] から低いモーション設定をオンまたはオフにする" lightbox="../media/css-elements-styles-qs-select-reduced-motion-command-menu.msft.png":::
       <span data-ttu-id="e8623-117">[コマンド メニュー] から低い **モーション設定をオン** または **オフにする**</span><span class="sxs-lookup"><span data-stu-id="e8623-117">Turn on or off the **prefers reduced motion** setting from **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="e8623-118">現在のページを更新して、アニメーションがオフになっているか表示されているかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="e8623-118">Refresh the current page to test whether your animations are turned off or visible.</span></span>  
    
<!-- links -->  

[DevtoolsIndex]: ../index.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  

[MDNPrefersReducedMotion]: https://developer.mozilla.org/docs/Web/CSS/@media/prefers-reduced-motion "縮小モーション を優先|MDN"  
