---
title: 開発者ツールを使用して、軽減される動きをシミュレートする (CSS 優先運動の減少)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/18/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: f1bf90de4ac1832fff07e9ac963c26f92adeea2c
ms.sourcegitcommit: 0048eb692d49eab4755c0c3ef6866e6a9122d579
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "10843985"
---
# <span data-ttu-id="ac373-103">モーションシミュレーションの減少</span><span class="sxs-lookup"><span data-stu-id="ac373-103">Reduced Motion Simulation</span></span>  

<span data-ttu-id="ac373-104">Web 製品のアニメーションには、アクセシビリティの問題がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ac373-104">Animation in web products may be an accessibility problem.</span></span>  <span data-ttu-id="ac373-105">オペレーティングシステムは、アニメーションをオフにするオプションを含めることで問題を解決します。これにより、ユーザーの混乱と、発作のトリガーなどの正常性関連の問題を回避することができます。</span><span class="sxs-lookup"><span data-stu-id="ac373-105">Operating Systems deal with the problem by including an option to turn off animations to avoid user confusion and potential health related problems such as triggering seizures.</span></span>  <span data-ttu-id="ac373-106">Web では、ユーザーがアニメーションを表示しないようにしているかどうかを検出するために、[アニメーションの[優先][MDNPrefersReducedMotion]] という CSS メディアクエリを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="ac373-106">On the web, you may use the [prefers-reduced-motion][MDNPrefersReducedMotion] CSS Media Query to detect if users prefer to not see any animations.</span></span>  <span data-ttu-id="ac373-107">製品では、アニメーションコードをテストにラップして、影響を受けるユーザーに対してアニメーションが表示されないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="ac373-107">In your product, you may wrap your animation code in a test to avoid animations showing up for the affected users.</span></span>  

```css
@media (prefers-reduced-motion: reduce) {
  /* in case the .header element has an animation, turn it off */
  .header {
    animation: none;
  }
}
```  

<span data-ttu-id="ac373-108">[Microsoft Edge DevTools][DevtoolsGuideChromiumMain]を使うと、オペレーティングシステムを変更せずに、このようなアニメーション設定をシミュレートすることができます。</span><span class="sxs-lookup"><span data-stu-id="ac373-108">Using the [Microsoft Edge DevTools][DevtoolsGuideChromiumMain], you may simulate this reduced motion setting without having to change your operating system.</span></span>  

1.  <span data-ttu-id="ac373-109">**コマンドメニュー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="ac373-109">Open the **Command Menu**.</span></span>  
    1.  <span data-ttu-id="ac373-110">`Control` + `Shift` + `P` Windows または macOS を押し `Command` + `Shift` + `P` ます。</span><span class="sxs-lookup"><span data-stu-id="ac373-110">Press `Control`+`Shift`+`P`  on Windows or `Command`+`Shift`+`P` on macOS.</span></span>  
        
        :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="コマンドメニュー" lightbox="../media/css-console-command-menu-rendering.msft.png":::
           <span data-ttu-id="ac373-112">**コマンドメニュー**</span><span class="sxs-lookup"><span data-stu-id="ac373-112">The **Command Menu**</span></span>  
        :::image-end:::   
        
1.  <span data-ttu-id="ac373-113">「 `reduced` 」と入力してシミュレーションのオンとオフを切り替えます。</span><span class="sxs-lookup"><span data-stu-id="ac373-113">Type `reduced`, to turn the simulation on and off.</span></span>  <span data-ttu-id="ac373-114">オプションを選択して、キーを押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="ac373-114">Select the option and press `Enter`.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-qs-select-reduced-motion-command-menu.msft.png" alt-text="コマンドメニューの [アニメーションの優先設定] の設定をオンまたはオフにする" lightbox="../media/css-elements-styles-qs-select-reduced-motion-command-menu.msft.png":::
       <span data-ttu-id="ac373-116">**コマンドメニュー**の [**アニメーションの優先**設定] の設定をオンまたはオフにする</span><span class="sxs-lookup"><span data-stu-id="ac373-116">Turn on or off the **prefers reduced motion** setting from **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ac373-117">現在のページを更新して、アニメーションがオフになっているか表示されているかをテストします。</span><span class="sxs-lookup"><span data-stu-id="ac373-117">Refresh the current page to test whether your animations are turned off or visible.</span></span>  
    
<!-- image links -->  

[ImageCommandMenu]: /microsoft-edge/devtools-guide-chromium/media/css-console-command-menu-rendering.msft.png "図 1: コマンドメニュー"  
[ImageToggleReducedMotionFromCommandMenu]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-qs-select-reduced-motion-command-menu.msft.png "図 2: コマンドパレットからのアニメーションの軽減"

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 開発者ツール Microsoft |Microsoft ドキュメント"  

[MDNPrefersReducedMotion]: https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-motion "低優先-モーション |MDN"  
