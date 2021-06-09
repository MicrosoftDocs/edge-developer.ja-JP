---
description: 開発者ツールを使用して、縮小されたモーションをシミュレートします。
title: 開発者ツールを使用して縮小モーションをシミュレートする (CSS Prefers Reduced Motion)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 7244c2e80bbf9070214b6abd02583792c785953c
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597058"
---
# <a name="reduced-motion-simulation"></a><span data-ttu-id="2b55f-104">モーション シミュレーションの削減</span><span class="sxs-lookup"><span data-stu-id="2b55f-104">Reduced motion simulation</span></span>  

<span data-ttu-id="2b55f-105">Web 製品のアニメーションはアクセシビリティの問題である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2b55f-105">Animation in web products may be an accessibility problem.</span></span>  <span data-ttu-id="2b55f-106">オペレーティング システムは、ユーザーの混乱や、発作のトリガーなど、潜在的な健康関連の問題を回避するためにアニメーションをオフにするオプションを含めて、この問題に対処します。</span><span class="sxs-lookup"><span data-stu-id="2b55f-106">Operating systems deal with this problem by including an option to turn off animations to avoid user confusion and potential health-related problems, such as triggering seizures.</span></span>  

<span data-ttu-id="2b55f-107">Web ページでは、優先的に縮小された [CSS][MDNPrefersReducedMotion] メディア クエリを使用して、ユーザーがアニメーションを表示することを好むかどうかを検出できます。</span><span class="sxs-lookup"><span data-stu-id="2b55f-107">On a webpage, you can use the [prefers-reduced-motion][MDNPrefersReducedMotion] CSS media query to detect whether the user prefers to display any animations.</span></span>  <span data-ttu-id="2b55f-108">次に、テストでアニメーション コードをラップし、条件付きでアニメーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="2b55f-108">Then wrap your animation code in a test, to conditionally run animations.</span></span>  

```css
@media (prefers-reduced-motion: reduce) {
  /* in case the .header element has an animation, turn it off */
  .header {
    animation: none;
  }
}
```  

<span data-ttu-id="2b55f-109">次に、次のようにコードをテストします。</span><span class="sxs-lookup"><span data-stu-id="2b55f-109">Then test your code, as follows.</span></span>

<span data-ttu-id="2b55f-110">オペレーティング システムの設定を変更せずに、オペレーティング システムの縮小モーション設定をシミュレートするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2b55f-110">To simulate the operating system's reduced motion setting, without having to change your operating system setting:</span></span>

1.  <span data-ttu-id="2b55f-111">**コマンド メニュー** を開きます。</span><span class="sxs-lookup"><span data-stu-id="2b55f-111">Open the **Command Menu**.</span></span>  
    1.  <span data-ttu-id="2b55f-112">`Control` + `Shift` + `P` [Windows/Linux または `Command` + `Shift` + `P` macOS で選択します。</span><span class="sxs-lookup"><span data-stu-id="2b55f-112">Select `Control`+`Shift`+`P` on Windows/Linux or `Command`+`Shift`+`P` on macOS.</span></span>  
        
        :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="コマンド メニュー" lightbox="../media/css-console-command-menu-rendering.msft.png":::
           <span data-ttu-id="2b55f-114">**コマンド メニュー**</span><span class="sxs-lookup"><span data-stu-id="2b55f-114">The **Command Menu**</span></span>  
        :::image-end:::  
        
1.  <span data-ttu-id="2b55f-115">`reduced`「」と入力して、シミュレーションのオンとオフを切り替えます。</span><span class="sxs-lookup"><span data-stu-id="2b55f-115">Type `reduced`, to turn the simulation on and off.</span></span>  <span data-ttu-id="2b55f-116">オプションを選択して選択します `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="2b55f-116">Choose the option and select `Enter`.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-qs-select-reduced-motion-command-menu.msft.png" alt-text="[コマンド メニュー] から低いモーション設定をオンまたはオフにする" lightbox="../media/css-elements-styles-qs-select-reduced-motion-command-menu.msft.png":::
       <span data-ttu-id="2b55f-118">[コマンド メニュー] から低い **モーション設定をオン** または **オフにする**</span><span class="sxs-lookup"><span data-stu-id="2b55f-118">Turn on or off the **prefers reduced motion** setting from **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="2b55f-119">Web ページを更新し、アニメーションが実行されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="2b55f-119">Refresh the webpage and check whether your animations run.</span></span>


## <a name="see-also"></a><span data-ttu-id="2b55f-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="2b55f-120">See also</span></span>

* <span data-ttu-id="2b55f-121">[UI アニメーションをオフに](test-reduced-ui-motion.md) した状態でページが使用可能になっていることを確認する - 説明付きデモ ページを使用したチュートリアル。</span><span class="sxs-lookup"><span data-stu-id="2b55f-121">[Verify that the page is usable with UI animation turned off](test-reduced-ui-motion.md) - A walkthrough using a demo page, with explanations.</span></span>

    
<!-- links -->  
[DevtoolsIndex]: ../index.md "Microsoft Edge (Chromium) 開発者ツール | Microsoft Docs"  
[MDNPrefersReducedMotion]: https://developer.mozilla.org/docs/Web/CSS/@media/prefers-reduced-motion "縮小モーション を優先|MDN"  
