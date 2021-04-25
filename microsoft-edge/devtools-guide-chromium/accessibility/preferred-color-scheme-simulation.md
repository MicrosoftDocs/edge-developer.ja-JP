---
description: Microsoft Edge DevTools を配色プレビュー モードに強制します。
title: Microsoft Edge DevTools を配色プレビュー モードに強制する (CSS 優先配色)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 1cdc9601e9e6fea1f6921c6cc40a1ed8232a0da8
ms.sourcegitcommit: 16e2f7232196a57a70b979bbf8b663774b7ddc20
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/25/2021
ms.locfileid: "11519150"
---
# <a name="dark-or-light-color-scheme-simulation"></a><span data-ttu-id="fa670-104">濃色または明るい配色のシミュレーション</span><span class="sxs-lookup"><span data-stu-id="fa670-104">Dark or Light Color Scheme simulation</span></span>  

<span data-ttu-id="fa670-105">オペレーティング システムでは、アプリケーションを暗い色または明るい色で表示できます。</span><span class="sxs-lookup"><span data-stu-id="fa670-105">Operating systems have a way to display any application in darker or lighter colors.</span></span>  <span data-ttu-id="fa670-106">暗いモードのオペレーティング システムで明るいテーマを持つ Web 製品はグレーティングであり、一部のユーザーにとってアクセシビリティの問題になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fa670-106">Having a web product that has a light theme in a dark mode operating system is grating and can be an accessibility issue for some users.</span></span>  <span data-ttu-id="fa670-107">Web では [、prefers-color-scheme][MDNPrefersColorScheme] CSS Media Query を使用して、ユーザーが製品を暗色または明るい配色で表示することを好む場合を検出できます。</span><span class="sxs-lookup"><span data-stu-id="fa670-107">On the web, you may use the [prefers-color-scheme][MDNPrefersColorScheme] CSS Media Query to detect if users prefer to display your product in a darker or lighter colour scheme.</span></span>  <span data-ttu-id="fa670-108">[Microsoft Edge DevTools を使用][DevtoolsIndex]すると、オペレーティング システム全体を変更することなく、暗いモードから明るいモードへの変更をシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="fa670-108">Use [Microsoft Edge DevTools][DevtoolsIndex] to simulate a change from dark to light mode without having to change the entire operating system.</span></span>  

1.  <span data-ttu-id="fa670-109">**コマンド メニュー** を開きます。</span><span class="sxs-lookup"><span data-stu-id="fa670-109">Open the **Command Menu**.</span></span>  
    1.  <span data-ttu-id="fa670-110">`Ctrl` + `Shift` + `P` \(Windows/Linux\) または `Command` + `Shift` + `P` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="fa670-110">Select `Ctrl`+`Shift`+`P` \(Windows/Linux\) or `Command`+`Shift`+`P` \(macOS\).</span></span>  
        
        :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="コマンド メニュー" lightbox="../media/css-console-command-menu-rendering.msft.png":::
           <span data-ttu-id="fa670-112">**コマンド メニュー**</span><span class="sxs-lookup"><span data-stu-id="fa670-112">The **Command Menu**</span></span>  
        :::image-end:::  
        
1.  <span data-ttu-id="fa670-113">[種類] を選択し、[CSS の優先する配色をエミュレートする: 濃い色] または [CSS を優先する配色をエミュレートする: 明るい] を選択し、 を `emulate color` 選択します\*\*\*\*\*\*\*\* `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="fa670-113">Type `emulate color`, choose either **Emulate CSS prefers-color-scheme: dark** or **Emulate CSS prefers-color-scheme: light** and then select `Enter`.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-qs-select-renderingmode-command-menu.msft.png" alt-text="コマンド メニューの配色オプション" lightbox="../media/css-elements-styles-qs-select-renderingmode-command-menu.msft.png":::
       <span data-ttu-id="fa670-115">コマンド メニューの配 **色** オプション</span><span class="sxs-lookup"><span data-stu-id="fa670-115">Color scheme option from **Command** Menu</span></span>  
    :::image-end:::  
    
    > [!IMPORTANT]
    > <span data-ttu-id="fa670-116">`dark` `light` [DevTools][DevtoolsCustomizeDarkTheme]のテーマを選択する方法も用意されています。</span><span class="sxs-lookup"><span data-stu-id="fa670-116">Simply typing `dark` or `light` does not reveal the right tool, since there is also a way to [choose a theme for DevTools][DevtoolsCustomizeDarkTheme].</span></span>  <span data-ttu-id="fa670-117">何を選ぶか疑問に思う場合は、外観メニュー項目ではなく、\*\*\*\* レンダリング メニュー項目を**選択してください**。</span><span class="sxs-lookup"><span data-stu-id="fa670-117">If you are wondering what to choose, make sure that you are choosing a **rendering** menu item, not an **appearance** menu item.</span></span>  

1.  <span data-ttu-id="fa670-118">配色を選択した後、現在のドキュメントを更新してシミュレートモードを表示します。</span><span class="sxs-lookup"><span data-stu-id="fa670-118">After you choose a color scheme, refresh the current document to display the simulated mode.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-qs-simulated-light-mode.msft.png" alt-text="Microsoft Edge DevTools 内のシミュレートされたライト モード" lightbox="../media/css-elements-styles-qs-simulated-light-mode.msft.png":::
       <span data-ttu-id="fa670-120">Microsoft Edge DevTools 内のシミュレートされたライト モード</span><span class="sxs-lookup"><span data-stu-id="fa670-120">Simulated light mode inside Microsoft Edge DevTools</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="fa670-121">他の Web ページと同様に CSS を表示および変更します。</span><span class="sxs-lookup"><span data-stu-id="fa670-121">View and change your CSS like any other web page.</span></span>  <span data-ttu-id="fa670-122">詳細については、「CSS の表示と変更 [を開始する」に移動します][DevtoolsCssIndex]。</span><span class="sxs-lookup"><span data-stu-id="fa670-122">For more information, navigate to [Get Started With Viewing And Changing CSS][DevtoolsCssIndex].</span></span>  

<!-- links -->  

[DevtoolsIndex]: ../index.md "Microsoft Edge (Chromium) 開発者ツール | Microsoft Docs"  
[DevtoolsCustomizeDarkTheme]: ../customize/dark-theme.md "Microsoft Edge DevTools サーバーで暗いテーマを有効|Microsoft Docs"
[DevtoolsCssIndex]: ../css/index.md "CSS の表示と変更の開始|Microsoft Docs"  

[MDNPrefersColorScheme]: https://developer.mozilla.org/docs/Web/CSS/@media/prefers-color-scheme "prefers-color-scheme |MDN"  
