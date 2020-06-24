---
title: Microsoft Edge DevTools を配色のプレビューモードに強制する (CSS は配色パターンを優先)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/18/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 94c5369f0eb35059933be7f6202a4f64450629cd
ms.sourcegitcommit: d7fdb67df0fe73fa5ae96e5a69a847d07941d0a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "10758111"
---
# <span data-ttu-id="5d787-103">モーションシミュレーションの減少</span><span class="sxs-lookup"><span data-stu-id="5d787-103">Reduced Motion Simulation</span></span>  

<span data-ttu-id="5d787-104">Web 製品のアニメーションには、アクセシビリティの問題がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5d787-104">Animation in web products may be an accessibility problem.</span></span>  <span data-ttu-id="5d787-105">オペレーティングシステムは、アニメーションをオフにするオプションを含めることで問題を解決します。これにより、ユーザーの混乱と、発作のトリガーなどの正常性関連の問題を回避することができます。</span><span class="sxs-lookup"><span data-stu-id="5d787-105">Operating Systems deal with the problem by including an option to turn off animations to avoid user confusion and potential health related problems such as triggering seizures.</span></span>  <span data-ttu-id="5d787-106">Web では、ユーザーがアニメーションを表示しないようにしているかどうかを検出するために、[アニメーションの[優先][MDNPrefersReducedMotion]] という CSS メディアクエリを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="5d787-106">On the web, you may use the [prefers-reduced-motion][MDNPrefersReducedMotion] CSS Media Query to detect if users prefer to not see any animations.</span></span>  <span data-ttu-id="5d787-107">製品では、アニメーションコードをテストにラップして、影響を受けるユーザーに対してアニメーションが表示されないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="5d787-107">In your product, you may wrap your animation code in a test to avoid animations showing up for the affected users.</span></span>  

```css
@media (prefers-reduced-motion: reduce) {
  /* in case the .header element has an animation, turn it off */
  .header {
  animation: none;
  }
}
```  

<span data-ttu-id="5d787-108">[Microsoft Edge DevTools][DevtoolsGuideChromiumMain]を使うと、オペレーティングシステムを変更せずに、このようなアニメーション設定をシミュレートすることができます。</span><span class="sxs-lookup"><span data-stu-id="5d787-108">Using the [Microsoft Edge DevTools][DevtoolsGuideChromiumMain], you may simulate this reduced motion setting without having to change your operating system.</span></span>  

1.  <span data-ttu-id="5d787-109">**コマンドメニュー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="5d787-109">Open the **Command Menu**.</span></span>  
    1.  <span data-ttu-id="5d787-110">`Control` + `Shift` + `P` Windows または macOS を押し `Command` + `Shift` + `P` ます。</span><span class="sxs-lookup"><span data-stu-id="5d787-110">Press `Control`+`Shift`+`P`  on Windows or `Command`+`Shift`+`P` on macOS.</span></span>  
        
        :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="コマンドメニュー" lightbox="../media/css-console-command-menu-rendering.msft.png":::
           <span data-ttu-id="5d787-112">**コマンドメニュー**</span><span class="sxs-lookup"><span data-stu-id="5d787-112">The **Command Menu**</span></span>  
        :::image-end:::   
        
1.  <span data-ttu-id="5d787-113">「 `reduced` 」と入力してシミュレーションのオンとオフを切り替えます。</span><span class="sxs-lookup"><span data-stu-id="5d787-113">Type `reduced`, to turn the simulation on and off.</span></span>  <span data-ttu-id="5d787-114">オプションを選択して、キーを押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="5d787-114">Select the option and press `Enter`.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-qs-select-reduced-motion-command-menu.msft.png" alt-text="コマンドメニューの [アニメーションの優先設定] の設定をオンまたはオフにする" lightbox="../media/css-elements-styles-qs-select-reduced-motion-command-menu.msft.png":::
       <span data-ttu-id="5d787-116">**コマンドメニュー**の [**アニメーションの優先**設定] の設定をオンまたはオフにする</span><span class="sxs-lookup"><span data-stu-id="5d787-116">Turn on or off the **prefers reduced motion** setting from **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="5d787-117">現在のページを更新して、アニメーションがオフになっているか表示されているかをテストします。</span><span class="sxs-lookup"><span data-stu-id="5d787-117">Refresh the current page to test whether your animations are turned off or visible.</span></span>  
    
<!-- image links -->  

[ImageCommandMenu]: /microsoft-edge/devtools-guide-chromium/media/css-console-command-menu-rendering.msft.png "図 1: コマンドメニュー"  
[ImageToggleReducedMotionFromCommandMenu]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-qs-select-reduced-motion-command-menu.msft.png "図 2: コマンドパレットからのアニメーションの軽減"

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 開発者ツール Microsoft |Microsoft ドキュメント"  

[MDNPrefersReducedMotion]: https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-motion "低優先-モーション |MDN"  