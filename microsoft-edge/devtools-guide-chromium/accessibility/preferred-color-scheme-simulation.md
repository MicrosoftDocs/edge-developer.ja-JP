---
Description: Microsoft Edge DevTools を強制的に配色プレビュー モードにします。
title: Microsoft Edge DevTools を強制的に配色プレビュー モードにする (CSS Prefers Color Scheme)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 29b0121a616a037fa11b61799efeffd201eb1821
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230797"
---
# <span data-ttu-id="0a26b-104">濃色または明るい配色のシミュレーション</span><span class="sxs-lookup"><span data-stu-id="0a26b-104">Dark or Light Color Scheme simulation</span></span>  

<span data-ttu-id="0a26b-105">オペレーティング システムには、アプリケーションを暗い色または明るい色で表示する方法があります。</span><span class="sxs-lookup"><span data-stu-id="0a26b-105">Operating systems have a way to display any application in darker or lighter colors.</span></span>  <span data-ttu-id="0a26b-106">濃色モードのオペレーティング システムで淡色テーマの Web 製品を使用すると、問題が発生し、一部のユーザーにとってアクセシビリティの問題になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0a26b-106">Having a web product that has a light theme in a dark mode operating system is grating and can be an accessibility issue for some users.</span></span>  <span data-ttu-id="0a26b-107">Web では [、prefers-color-scheme][MDNPrefersColorScheme] CSS Media Query を使用して、ユーザーが製品を濃色または明るい配色で表示することを希望する場合に検出できます。</span><span class="sxs-lookup"><span data-stu-id="0a26b-107">On the web, you may use the [prefers-color-scheme][MDNPrefersColorScheme] CSS Media Query to detect if users prefer to see your product in a darker or lighter colour scheme.</span></span>  <span data-ttu-id="0a26b-108">[Microsoft Edge DevTools を使][DevtoolsGuideChromiumMain]って、オペレーティング システム全体を変更することなく、暗いモードから明るいモードへの変更をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="0a26b-108">Use [Microsoft Edge DevTools][DevtoolsGuideChromiumMain] to simulate a change from dark to light mode without having to change the entire operating system.</span></span>  

1.  <span data-ttu-id="0a26b-109">コマンド メニュー **を開きます**。</span><span class="sxs-lookup"><span data-stu-id="0a26b-109">Open the **Command Menu**.</span></span>  
    1.  <span data-ttu-id="0a26b-110">`Control` + `Shift` + `P` Windows/Linux または `Command` + `Shift` + `P` macOS で選択します。</span><span class="sxs-lookup"><span data-stu-id="0a26b-110">Select `Control`+`Shift`+`P`  on Windows/Linux or `Command`+`Shift`+`P` on macOS.</span></span>  
        
        :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="コマンド メニュー" lightbox="../media/css-console-command-menu-rendering.msft.png":::
           <span data-ttu-id="0a26b-112">**コマンド メニュー**</span><span class="sxs-lookup"><span data-stu-id="0a26b-112">The **Command Menu**</span></span>  
        :::image-end:::  
        
1.  <span data-ttu-id="0a26b-113">Type, `emulate color` choose either Emulate CSS **prefers-color-scheme: dark** or Emulate CSS **prefers-color-scheme: light** and then select `Enter` .</span><span class="sxs-lookup"><span data-stu-id="0a26b-113">Type `emulate color`, choose either **Emulate CSS prefers-color-scheme: dark** or **Emulate CSS prefers-color-scheme: light** and then select `Enter`.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-qs-select-renderingmode-command-menu.msft.png" alt-text="コマンド メニューの配色オプション" lightbox="../media/css-elements-styles-qs-select-renderingmode-command-menu.msft.png":::
       <span data-ttu-id="0a26b-115">コマンド メニューの配 **色** オプション</span><span class="sxs-lookup"><span data-stu-id="0a26b-115">Color scheme option from **Command** Menu</span></span>  
    :::image-end:::  
    
    > [!IMPORTANT]
    > <span data-ttu-id="0a26b-116">`dark` `light` [DevTools][DevtoolsGuideChromiumCustomizeDarkTheme]のテーマを選択する方法も用意されています。</span><span class="sxs-lookup"><span data-stu-id="0a26b-116">Simply typing `dark` or `light` does not reveal the right tool, since there is also a way to [choose a theme for DevTools][DevtoolsGuideChromiumCustomizeDarkTheme].</span></span>  <span data-ttu-id="0a26b-117">何を選択する必要があるのか疑問に思う場合は、外観メニュー\*\*\*\* 項目ではなく、レンダリング メニュー項目を**選択**してください。</span><span class="sxs-lookup"><span data-stu-id="0a26b-117">If you are wondering what to choose, make sure that you are choosing a **rendering** menu item, not an **appearance** menu item.</span></span>  

1.  <span data-ttu-id="0a26b-118">配色を選択した後、現在のドキュメントを再読み込みし、シミュレートされたモードを確認します。</span><span class="sxs-lookup"><span data-stu-id="0a26b-118">After you choose a color scheme, reload the current document to see the simulated mode.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-qs-simulated-light-mode.msft.png" alt-text="Microsoft Edge DevTools 内のシミュレートされたライト モード" lightbox="../media/css-elements-styles-qs-simulated-light-mode.msft.png":::
       <span data-ttu-id="0a26b-120">Microsoft Edge DevTools 内のシミュレートされたライト モード</span><span class="sxs-lookup"><span data-stu-id="0a26b-120">Simulated light mode inside Microsoft Edge DevTools</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="0a26b-121">他の Web ページと同様に CSS を表示および変更します。</span><span class="sxs-lookup"><span data-stu-id="0a26b-121">View and change your CSS like any other web page.</span></span>  <span data-ttu-id="0a26b-122">詳細については、「CSS の表示と変更 [の開始」を参照してください][DevtoolsGuideChromiumCssIndex]。</span><span class="sxs-lookup"><span data-stu-id="0a26b-122">For more information, see [Get Started With Viewing And Changing CSS][DevtoolsGuideChromiumCssIndex].</span></span>  

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../index.md "Microsoft Edge (Chromium) 開発者ツール | Microsoft Docs"  
[DevtoolsGuideChromiumCustomizeDarkTheme]: ../customize/dark-theme.md "Microsoft Edge DevTools で濃色テーマを有効にする |Microsoft Docs"
[DevtoolsGuideChromiumCssIndex]: ../css/index.md "CSS の表示と変更を開始する |Microsoft Docs"  

[MDNPrefersColorScheme]: https://developer.mozilla.org/docs/Web/CSS/@media/prefers-color-scheme "prefers-color-scheme |MDN"  
